---
layout: post
title: Deploying services with dependency in phases
description: 
date: 2019-09-29 00:00:00
comments_id: 
---

So now that we have a couple of downstream services that are referencing a resource deployed in an upstream service; let's look at how this dependency affects the way we deploy our app.

The short version is that:

- When you introduce a new dependency in your app you cannot deploy all the services concurrently.
- However, once these services have been deployed, you can do so.

#### First deployment

In our [resources repo]({{ site.backend_ext_resources_github_repo }}) we need to:

- Deploy the `database` and `uploads` service. These can be deployed concurrently.
- Then we can deploy the `auth` service.

TODO: UPDATE LINK

Next for the [API repo]({{ site.backend_ext_api_github_repo }}) for the first time, you have to:

- Deploy the `notes-api` first. This will export the value `dev-ExtApiGatewayRestApiId` and `dev-ExtApiGatewayRestApiRootResourceId`.
- Then deploy the `billing-api` next. This will export the value `ExtNotePurchasedTopicArn-dev`.
- Then deploy the `notify-job`.

Assuming that you are deploying to the `dev` stage.

If you were to deploy `billing-api` and `notify-job` concurrently, the `notify-job` will fail with the following CloudFormation error:

```
notify-job - No export named ExtNotePurchasedTopicArn-dev found.
```

This error is basically saying that the ARN referenced in its `serverless.yml` does not exist. This makes sense because we haven’t created it yet!

#### Subsequent deployments

Once all the services have been successfully deployed, you can deploy them all concurrently. This is because the referenced ARN has already been created.

#### Adding new dependencies

Say you add a new SNS topic in `billing-api` service and you want the `notify-job` service to subscribe to that topic. The first deployment after the change, will again fail if all the services are deployed concurrently. You need to deploy the `billing-api` service first, and then deploy the `notify-job` service.

We are almost ready to deploy our extended notes app. But before we can do that, let's configure our environments.

TODO: MOVE THE FOLLOWING SECTION TO AFTER THE ENVIRONMENTS HAVE BEEN CONFIGURED IN SEED

### Deploying through a CI

If you are using a CI, you'll need to deploy the above in phases. With [Seed](https://seed.run), we handle this using a concept of [Deploy Phases](https://seed.run/docs/configuring-deploy-phases).

### Managing deployment in phases for api

For our api repo, the dependencies look like:
```
notes-api > billing-api > notify-job
```
To break it down in detail:
- The `billing-api` service relies on the `notes-api` service for the API Gateway export.
- The `notify-job` service relies on the `billing-api` service for the SNS Topic export.
