---
layout: post
title: මෙම නිබන්ධනය කා සඳහා ද?
date: 2020-08-22 00:00:00
lang: si
ref: who-is-this-guide-for
comments_id: who-is-this-guide-for/96
---

මේ නිබන්ධනය serverless යෙදුම් හදන්න ඉගෙනගන්න කැමති මෘදුකාංග සංවර්ධකයන් වෙනුවෙන් නිර්මාණය කර තිබෙනවා. frontend සහ backend පැති දෙකම ආවරණය වෙන විදිහට පියවරෙන් පියවර අනුගමනය කළ හැකි මඟපෙන්වීමක් ලබා දීම තුළින් serverless යෙදුම් නිර්මාණය කිරීම පිළිබඳ විවිධ අංශ ආවරණය වනු ඇතැයි අපි බලාපොරොත්තු වෙනවා. මේ ගැන අන්තර්ජාලයේ විවිධ තැන්වල තවත් නිබන්ධන තිබුණත් මේ ආකාරයේ serverless යෙදුම් සංවර්ධනය පිළිබඳ සම්පූර්ණ නිබන්ධනයක් තිබීම ඉතා ප්‍රයෝජනවත්. මේ නිබන්ධනය මූලිකවම, serverless යෙදුම් සංවර්ධනය පිළිබද සම්මතයන් පැහැදිලි කිරීමට වඩා හුදෙක් serverless යෙදුම් සංවර්ධනය කර අන්තර්ජාලයේ පලකිරීම පිලිබඳ දැනගත යුතු සියලු තොරතුරු ආවරණය කිරීම අරමුණු කොට නිර්මාණය කොට තිබෙනවා. 

ඔබ සමහර විට backend පැත්ත දන්න, නමුත් serverless යෙදුම් වල frontend පැත්ත ගැන වැඩිදුර ඉගෙනගන්න කැමති කෙනෙක් වෙන්න පුළුවන්. එහෙමත් නැත්නම් frontend පැත්ත දන්න නමුත් backend පැත්ත ගැන වැඩිදුර දැනගන්න කැමති කෙනෙක් වෙන්නත් පුළුවන්. මේ කොහොම වුණත්, මේ නිබන්ධනය ඔබේ ඉගෙනුම් අවශ්‍යතා සම්පූර්ණ කරනු ඇති.

දැනට මේ නිබන්ධනය සම්පූර්ණයෙන්ම නිර්මාණය කරලා තියෙන්නේ JavaScript සංවර්ධකයන් වෙනුවෙන්. අපි ඉස්සරහට වෙනත් පරිගණක භාෂා ගැනත් අවධානය යොමු කරාවි. නමුත් JavaScript යොදා ගැනීම හොද ආරම්භයක් කියලා අපි හිතනවා, මොකද JavaScript භාවිත කරලා සම්පුර්ණයෙන්ම වෙබ් අඩවියක ඉදිරි අන්තය (frontend) සහ පසු අන්තය (backend) යන දෙකම සංවර්ධනය කරන්න පුළුවන් නිසා.

පුද්ගලිකව, serverless විදිහට වෙබ් යෙදුම් නිර්මාණය කිරීම අපි කළ දැවැන්ත අනාවරණයක්. ඒ නිසා අපි ඉගෙනගත් දේ බෙදාගත හැකි යමක් නිර්මාණය කරන්න අපිට අවශ්‍ය වුණා. ඔබට අපි ගැන [**මෙතනින්**]({{ site.sst_url }}) වැඩිදුර දැනගන්න පුළුවන් සහ මේ තාක්ෂණය භාවිත කරලා හදපු ආකෘති යෙදුම් ගැන [මෙතනින්]({% link showcase.md %}) ගිහින් බලන්නත් පුළුවන්. 

ඉතින්, මේ නිබන්ධනයෙන් ආවරණය වෙන්නේ මොනවද කියලා දැනගෙන ම අපි ඉගෙනීම ආරම්භ කරමු.
