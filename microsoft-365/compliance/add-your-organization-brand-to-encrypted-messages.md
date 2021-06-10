---
title: Lägga till organisationens varumärke i krypterade meddelanden
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Lär Office 365 hur globala administratörer kan använda företagets varumärke i krypterade e-postmeddelanden & innehållet på krypteringsportalen.
ms.openlocfilehash: 2898e12ad00d11cd9eb2f3be5d817ef113607e79
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162547"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a>Lägga till organisationens varumärke i meddelandekrypteringskryptering i Microsoft 365 för företag

Du kan använda företagets varumärke för att anpassa utseendet på din organisations e-postmeddelanden och krypteringsportalen. Du måste tillämpa global administratörsbehörighet på ditt arbets- eller skolkonto innan du kan komma igång. När du har de här behörigheterna kan du använda cmdletarna Get-OMEConfiguration och Set-OMEConfiguration Windows PowerShell för att anpassa de här delarna av krypterade e-postmeddelanden:
  
- Inledande text

- Ansvarsfriskrivningstext

- URL till din organisations sekretesspolicy

- Text i OME-portalen

- Logotyp som visas i e-postmeddelandet och OME-portalen, eller om du ska använda en logotyp alls

- Bakgrundsfärg i e-postmeddelandet och OME-portalen

Du kan också när som helst återgå till standardinställningen.

Om du vill ha mer kontroll kan du använda Office 365 Advanced Message Encryption skapa flera mallar för krypterade e-postmeddelanden som kommer från organisationen. Använd de här mallarna för att styra delar av slutanvändarupplevelsen. Ange till exempel om mottagare kan använda Google, Yahoo och Microsoft-konton för att logga in på krypteringsportalen. Använd mallar för att uppfylla flera användningsfall, till exempel:

- Enskilda avdelningar, till exempel ekonomi, försäljning och så vidare.

- Olika produkter

- Olika geografiska regioner eller länder

- Om du vill tillåta att e-postmeddelanden återkallas

- Om du vill att e-postmeddelanden som skickas till externa mottagare ska upphöra att gälla efter ett angivet antal dagar.

När du har skapat mallarna kan du använda dem i krypterade e-postmeddelanden genom att Exchange e-postflödesregler. Om du har Office 365 Advanced Message Encryption kan du återkalla alla e-postmeddelanden som du har profilerat med hjälp av dessa mallar.

## <a name="work-with-ome-branding-templates"></a>Arbeta med varumärkesmallar för OME

Du kan ändra flera funktioner i en varumärkesmall. Du kan ändra, men inte ta bort, standardmallen. Om du har Avancerad meddelandekryptering kan du också skapa, ändra och ta bort anpassade mallar. Använd Windows PowerShell att arbeta med en varumärkesmall i taget.

- [Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) – Ändra standardmallen för profilering eller en anpassad varumärkesmall som du har skapat.
- [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) – Skapa en ny varumärkesmall, endast avancerad meddelandekryptering.
- [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) – Ta bort en anpassad varumärkesmall, endast avancerad meddelandekryptering. Du kan inte ta bort standardmallen för profilering.
  
## <a name="modify-an-ome-branding-template"></a>Ändra en OME-varumärkesmall

Använd Windows PowerShell att ändra en varumärkesmall i taget. Om du har Avancerad meddelandekryptering kan du också skapa, ändra och ta bort anpassade mallar.

1. Om du använder ett arbets- eller skolkonto med global administratörsbehörighet i din organisation startar du Windows PowerShell en session och ansluter till Exchange Online. För instruktioner se: [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Använd Set-OMEConfiguration cmdlet enligt beskrivningen i [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) eller använd följande grafik och tabell för vägledning.

![Anpassningsbara e-postdelar](../media/ome-template-breakout.png)

|**Så här anpassar du den här funktionen i krypteringsupplevelsen**|**Använd de här kommandona**|
|:-----|:-----|
|Bakgrundsfärg|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> **Exempel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> Mer information om bakgrundsfärger finns i avsnittet [Bakgrundsfärger längre](#background-color-reference) fram i den här artikeln.|
|Logotyp|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> **Exempel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> Filformat som stöds: .png, .jpg, .bmp eller .tiff  <br/> Optimal storlek på logotypfilen: mindre än 40 kB  <br/> Optimal storlek på logotypbild: 170 x 70 bildpunkter. Om bilden överskrider de här måtten ändrar tjänsten storlek på din logotyp för visning i portalen. Tjänsten ändrar inte själva grafikfilen. För bästa resultat bör du använda optimal storlek.|
|Text bredvid avsändarens namn och e-postadress|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> **Exempel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|Text som visas på knappen "Läs upp meddelande"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> **Exempel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|Text som visas under knappen "Läs meddelande"|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> **Exempel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|URL för länken Sekretesspolicy|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> **Exempel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|Ansvarsfriskrivningsutdrag i e-postmeddelandet som innehåller det krypterade meddelandet|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **Exempel:** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|Text som visas högst upp i visningsportalen för krypterade e-postmeddelanden|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **Exempel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|Aktivera eller inaktivera autentisering med ett lösenord för den här anpassade mallen|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> **Exempel:** <br/>Så här aktiverar du lösenord för en gång för den här anpassade mallen <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> Inaktivera lösenord för en gång för den här anpassade mallen <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|Aktivera eller inaktivera autentisering med Microsoft-, Google- eller Yahoo-identiteter för den här anpassade mallen|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> **Exempel:** <br/>Så här aktiverar du sociala ID för den här anpassade mallen <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> Så här inaktiverar du sociala ID för den här anpassade mallen <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a>Skapa en OME-varumärkesmall (avancerad meddelandekryptering)

Om du har Office 365 Advanced Message Encryption kan du skapa anpassade varumärkesmallar för din organisation med hjälp av cmdleten [New-OMEConfiguration.](/powershell/module/exchange/new-omeconfiguration) När du har skapat mallen kan du ändra mallen med hjälp av cmdleten Set-OMEConfiguration som beskrivs i Ändra en [OME-varumärkesmall.](#modify-an-ome-branding-template) Du kan skapa flera mallar.

Så här skapar du en ny anpassad varumärkesmall:

1. Om du använder ett arbets- eller skolkonto med global administratörsbehörighet i din organisation startar du Windows PowerShell en session och ansluter till Exchange Online. För instruktioner se: [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Använd [cmdleten New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) för att skapa en ny mall.

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   Ett exempel:

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a>Returnera standardmallen för varumärkesmall till dess ursprungliga värden

Om du vill ta bort alla ändringar från standardmallen, inklusive varumärkesanpassningar och så vidare, slutför du de här stegen:
  
1. Om du använder ett arbets- eller skolkonto med global administratörsbehörighet i din organisation startar du Windows PowerShell en session och ansluter till Exchange Online. För instruktioner se: [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Använd **cmdleten Set-OMEConfiguration** enligt beskrivningen i [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration). Om du vill ta bort organisationens anpassningar av ansvarsfriskrivningstext, e-posttext och portaltext anger du värdet som en tom `""` sträng. För alla bildvärden, till exempel Logotyp, ställer du in värdet på  `"$null"` .

   I följande tabell beskrivs standardinställningen för krypteringsalternativ.

   |Om du vill återställa den här funktionen i krypteringen till standardtexten och standardbilden|Använd de här kommandona|
   |:-----|:-----|
   |Standardtext som medföljer krypterade e-postmeddelanden.  Standardtexten visas ovanför instruktionerna för att visa krypterade meddelanden|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> **Exempel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |Ansvarsfriskrivningsutdrag i e-postmeddelandet som innehåller det krypterade meddelandet|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> **Exempel:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |Text som visas högst upp i visningsportalen för krypterade e-postmeddelanden|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> **Exempel som återställer till standard:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |Logotyp|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> **Exempel som återställer till standard:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |Bakgrundsfärg|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> **Exempel som återställer till standard:** <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a>Ta bort en anpassad varumärkesmall (Avancerad meddelandekryptering)

Du kan bara ta bort anpassade mallar som du har skapat. Du kan inte ta bort standardmallen för profilering.

Så här tar du bort en anpassad varumärkesmall:
  
1. Om du använder ett arbets- eller skolkonto med global administratörsbehörighet i din organisation startar du Windows PowerShell en session och ansluter till Exchange Online. För instruktioner se: [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Använd **cmdleten Remove-OMEConfiguration** enligt följande:

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   Ett exempel:

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   Mer information finns i [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration).

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a>Skapa en Exchange e-postflödesregel som tillämpar din anpassade profilering på krypterade e-postmeddelanden

När du antingen har ändrat standardmallen eller skapat nya varumärkesmallar kan du skapa Exchange-postflödesregler för att tillämpa din anpassade profilering utifrån vissa villkor. En sådan regel kommer att tillämpa anpassad profilering i följande scenarier:

- Om e-postmeddelandet krypterades manuellt av slutanvändaren med hjälp Outlook eller Outlook på webben, tidigare Outlook Web App

- Om e-postmeddelandet automatiskt krypterades av Exchange e-postflödesregel eller princip för dataförlustskydd

Mer information om hur du skapar en Exchange-postflödesregel som tillämpar kryptering finns i Definiera e-postflödesregler för att [kryptera e-postmeddelanden i Office 365](define-mail-flow-rules-to-encrypt-email.md).

1. Använd ett arbets- eller skolkonto som har beviljats global administratörsbehörighet i en webbläsare och logga [in på Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Välj **panelen** Admin.

3. Välj Microsoft 365 administrationscenter i **administrationscentret** \> **för Exchange**.

4. I EAC går du till **E-postflödesregler** \>  och väljer **Ny** ny ikon Skapa en ![ ny ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regel.** Mer information om hur du använder EAC finns Exchange [administrationscenter i Exchange Online](/exchange/exchange-admin-center).

5. I **Namn** anger du ett namn på regeln, till exempel Profilering för säljavdelningen.

6. I **Använd den här regeln** om väljer du villkoret **Avsändaren** finns i organisationen och andra villkor som du vill använda i listan med tillgängliga villkor. Du kanske till exempel vill använda en viss varumärkesmall för:

   - Alla krypterade e-postmeddelanden som skickas från medlemmar på ekonomiavdelningen
   - Krypterade e-postmeddelanden som skickas med ett visst nyckelord, till exempel "Extern" eller "Partner"
   - Krypterade e-postmeddelanden som skickas till en viss domän

7. Från **Gör följande väljer du** Ändra **meddelandets säkerhet Tillämpa** anpassad anpassning på \> **OME-meddelanden.** Välj sedan en varumärkesmall i listrutan.

8. (Valfritt) Du kan konfigurera e-postflödesregeln så att kryptering och anpassad profilering tillämpas. Från **Gör följande väljer** du Ändra **meddelandets säkerhet** och sedan Apply Meddelandekryptering i Office 365 and rights **protection**. Välj en RMS-mall i listan, **välj Spara** och välj sedan **OK.**
  
   Listan med mallar innehåller standardmallar och alternativ samt eventuella anpassade mallar som du skapar. Om listan är tom, kontrollera att du har Meddelandekryptering i Office 365 med de nya funktionerna. Instruktioner finns i [Konfigurera nya Meddelandekryptering i Office 365 funktioner.](set-up-new-message-encryption-capabilities.md) Mer information om standardmallar finns i Konfigurera [och hantera mallar för Azure Information Protection.](/information-protection/deploy-use/configure-policy-templates) Mer information om alternativet **Vidarebefordra inte finns i** alternativet Vidarebefordra inte för [e-postmeddelanden.](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) Mer information om det enda **alternativet för kryptering finns** i Alternativet Kryptera endast för [e-postmeddelanden.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

   Välj **Lägg till åtgärd** om du vill ange en annan åtgärd.

## <a name="background-color-reference"></a>Bakgrundsfärgreferens

Färgnamnen som du kan använda för bakgrundsfärgen är begränsade. I stället för ett färgnamn kan du använda ett hexkodsvärde (#RRGGBB). Du kan använda ett hexkodvärde som motsvarar ett färgnamn eller så kan du använda ett anpassat hexkodsvärde. Se till att omge det hexadecigrafiska kodvärdet med citattecken (till exempel `"#f0f8ff"` ).

De tillgängliga namnen på bakgrundsfärgerna och deras motsvarande hexadexkodvärden beskrivs i följande tabell.

|**Färgnamn**|**Färgkod**|
|---|---|
|`aliceblue`|#f0f8ff|
|`antiquewhite`|#faebd7|
|`aqua`|#00ffff|
|`aquamarine`|#7fffd4|
|`azure`|#f0ffff|
|`beige`|#f5f5dc|
|`bisque`|#ffe4c4|
|`black`|#000000|
|`blanchedalmond`|#ffebcd|
|`blue`|#0000ff|
|`blueviolet`|#8a2be2|
|`brown`|#a52a2a|
|`burlywood`|#deb887|
|`cadetblue`|#5f9ea0|
|`chartreuse`|#7fff00|
|`chocolate`|#d2691e|
|`coral`|#ff7f50|
|`cornflowerblue`|#6495ed|
|`cornsilk`|#fff8dc|
|`crimson`|#dc143c|
|`cyan`|#00ffff|
|`darkblue`|#00008b|
|`darkcyan`|#008b8b|
|`darkgoldenrod`|#b8860b|
|`darkgray`|#a9a9a9|
|`darkgreen`|#006400|
|`darkkhaki`|#bdb76b|
|`darkmagenta`|#8b008b|
|`darkolivegreen`|#556b2f|
|`darkorange`|#ff8c00|
|`darkorchid`|#9932cc|
|`darkred`|#8b0000|
|`darksalmon`|#e9967a|
|`darkseagreen`|#8fbc8f|
|`darkslateblue`|#483d8b|
|`darkslategray`|#2f4f4f|
|`darkturquoise`|#00ced1|
|`darkviolet`|#9400d3|
|`deeppink`|#ff1493|
|`deepskyblue`|#00bfff|
|`dimgray`|#696969|
|`dodgerblue`|#1e90ff|
|`firebrick`|#b22222|
|`floralwhite`|#fffaf0|
|`forestgreen`|#228b22|
|`fuchsia`|#ff00ff|
|`gainsboro`|#dcdcdc|
|`ghostwhite`|#f8f8ff|
|`gold`|#ffd700|
|`goldenrod`|#daa520|
|`gray`|#808080|
|`green`|#008000|
|`greenyellow`|#adff2f|
|`honeydew`|#f0fff0|
|`hotpink`|#ff69b4|
|`indianred`|#cd5c5c|
|`indigo`|#4b0082|
|`ivory`|#fffff0|
|`khaki`|#f0e68c|
|`lavender`|#e6e6fa|
|`lavenderblush`|#fff0f5|
|`lawngreen`|#7cfc00|
|`lemonchiffon`|#fffacd|
|`lightblue`|#add8e6|
|`lightcoral`|#f08080|
|`lightcyan`|#e0ffff|
|`lightgoldenrodyellow`|#fafad2|
|`lightgray`|#d3d3d3|
|`lightgrey`|#d3d3d3|
|`lightgreen`|#90ee90|
|`lightpink`|#ffb6c1|
|`lightsalmon`|#ffa07a|
|`lightseagreen`|#20b2aa|
|`lightskyblue`|#87cefa|
|`lightslategray`|#778899|
|`lightsteelblue`|#b0c4de|
|`lightyellow`|#ffffe0|
|`lime`|#00ff00|
|`limegreen`|#32cd32|
|`linen`|#faf0e6|
|`magenta`|#ff00ff|
|`maroon`|#800000|
|`mediumaquamarine`|#66cdaa|
|`mediumblue`|#0000cd|
|`mediumorchid`|#ba55d3|
|`mediumpurple`|#9370db|
|`mediumseagreen`|#3cb371|
|`mediumslateblue`|#7b68ee|
|`mediumspringgreen`|#00fa9a|
|`mediumturquoise`|#48d1cc|
|`mediumvioletred`|#c71585|
|`midnightblue`|#191970|
|`mintcream`|#f5fffa|
|`mistyrose`|#ffe4e1|
|`moccasin`|#ffe4b5|
|`navajowhite`|#ffdead|
|`navy`|#000080|
|`oldlace`|#fdf5e6|
|`olive`|#808000|
|`olivedrab`|#6b8e23|
|`orange`|#ffa500|
|`orangered`|#ff4500|
|`orchid`|#da70d6|
|`palegoldenrod`|#eee8aa|
|`palegreen`|#98fb98|
|`paleturquoise`|#afeeee|
|`palevioletred`|#db7093|
|`papayawhip`|#ffefd5|
|`peachpuff`|#ffdab9|
|`peru`|#cd853f|
|`pink`|#ffc0cb|
|`plum`|#dda0dd|
|`powderblue`|#b0e0e6|
|`purple`|#800080|
|`red`|#ff0000|
|`rosybrown`|#bc8f8f|
|`royalblue`|#4169e1|
|`saddlebrown`|#8b4513|
|`salmon`|#fa8072|
|`sandybrown`|#f4a460|
|`seagreen`|#00ff00|
|`seashell`|#fff5ee|
|`sienna`|#a0522d|
|`silver`|#c0c0c0|
|`skyblue`|#87ceeb|
|`slateblue`|#6a5acd|
|`slategray`|#708090|
|`snow`|#fffafa|
|`springgreen`|#00ff7f|
|`steelblue`|#4682b4|
|`tan`|#d2b48c|
|`teal`|#008080|
|`thistle`|#d8bfd8|
|`tomato`|#ff6347|
|`turquoise`|#40e0d0|
|`violet`|#ee82ee|
|`wheat`|#f5deb3|
|`white`|#ffffff|
|`whitesmoke`|#f5f5f5|
|`yellow`|#ffff00|
|`yellowgreen`|#9acd32|