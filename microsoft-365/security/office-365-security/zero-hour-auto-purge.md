---
title: Automatisk rensning på noll timmar - skydd mot skräppost och skadlig kod
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: Zap (Zero-hour auto purge) är en e-postskyddsfunktion som identifierar meddelanden med skräppost eller skadlig kod som redan har levererats till användarnas inkorgar och sedan gör det skadliga innehållet ofarligt. Hur ZAP gör detta beror på vilken typ av skadligt innehåll som upptäckts.
ms.openlocfilehash: 6616281a98487c7edd7ca7721ade9a8510f6a21f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806464"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>Automatisk rensning på noll timmar - skydd mot skräppost och skadlig kod

## <a name="overview"></a>Översikt

Zap (Zero-hour auto purge) är en e-postskyddsfunktion som identifierar meddelanden med phish, spam eller skadlig kod som redan har levererats till användarnas inkorgar och sedan gör det skadliga innehållet ofarligt. Hur ZAP gör detta beror på vilken typ av skadligt innehåll som upptäckts. E-post kan zapped på grund av e-postinnehåll, webbadresser eller bilagor.

ZAP är tillgängligt med standardexchange onlineskydd som ingår i alla Office 365-prenumerationer som innehåller Exchange Online-postlådor.

## <a name="how-zap-works"></a>Hur ZAP fungerar

Office 365 uppdaterar anti-spam-motor och malware signaturer i realtid på en daglig basis. Användarna kan dock fortfarande få skadliga meddelanden levererade till sina inkorgar av olika anledningar, bland annat om innehållet är weaponized efter att ha levererats till användare. ZAP tar upp detta genom att kontinuerligt övervaka uppdateringar av Office 365-skräppost- och malware-signaturerna. ZAP kan hitta och ta bort tidigare levererade meddelanden som redan finns i användarnas inkorgar.

ZAP-åtgärden är sömlös för postlådans användare. de meddelas inte om ett e-postmeddelande flyttas. 

Tillåt listor, [regler för e-postflöde](use-transport-rules-to-configure-bulk-email-filtering.md) (kallas även transportregler) och slutanvändarregler eller ytterligare filter har företräde framför ZAP.

### <a name="malware-zap"></a>Malware ZAP

För nyupptäckt skadlig kod flyttar ZAP hela meddelandet, inklusive dess bilaga, till karantän för skadlig kod. Meddelanden flyttas oavsett lässtatus för e-postmeddelandet. Om vi får en malware signal för ett meddelande i processen för dynamisk leverans skanning, zap kommer att ta en Flytta till Skräp åtgärder på meddelandet. Då kommer det att tillåta dynamisk leverans att slutföra tiden för leverans skanning och vidta lämpliga åtgärder.

Zap-kod är aktiverat som standard i malware-principen. Du kan inaktivera ZAP för skadlig kod med parametern *ZapEnabled* på [Cmdlet Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) i Exchange Online PowerShell eller Exchange Online Protection PowerShell. Malware ZAP kan också aktiveras eller inaktiveras genom att redigera malware policy i Säkerhets-och Compliance Center.

### <a name="phish-zap"></a>Phish ZAP

För e-post som identifieras som phish efter leverans, ZAP vidtar åtgärder enligt spam politik som täcker en viss användare, oavsett lässtatus för posten. Om åtgärden För principPhish är inställd på att *inte* vidta åtgärder (Lägg till X-header, Ändra ämne, Ingen åtgärd) kommer ZAP inte att vidta några åtgärder på e-postmeddelandet. Om phish-åtgärden är inställd på Flytta till skräppost flyttar ZAP meddelandet till skräppostmappen i användarens inkorg. **För alla andra Phish åtgärder (Omdirigera, Ta bort, Karantän) ZAP kommer att flytta meddelandet till phish Karantän**. Läs nedan för konfigurationskrav och undantag. Läs mer om hur du [konfigurerar dina principer för skräppostfilter](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) här.

Phish ZAP är aktiverat som standard i skräppostpolicyn. Phish ZAP kan inaktiveras med hjälp av *phishZapEnabled* [parametern Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy), en EOP cmdlet.

### <a name="spam-zap"></a>Spam ZAP

För e-post som identifieras som skräppost efter leverans vidtar ZAP åtgärder enligt skräppostpolicyn som täcker den specifika användaren, endast om meddelandet är oläst.  Om åtgärden För skräppost är inställd på att inte vidta åtgärder (Lägg till X-header, Ändra ämne, Ingen åtgärd) kommer ZAP inte att vidta några åtgärder på e-postmeddelandet. Om åtgärden Skräppost är inställd på Flytta till skräppost flyttar ZAP meddelandet till skräppostmappen i användarens inkorg. **För alla andra Spam-åtgärder (Omdirigering, Ta bort, Karantän) ZAP kommer att flytta meddelandet till spam Karantän**. Läs nedan för konfigurationskrav och undantag. Läs mer om hur du [konfigurerar dina principer för skräppostfilter](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) här.

Spam ZAP är aktiverat som standard i skräppostpolicyn. Du kan inaktivera Spam ZAP med hjälp av parametern *SpamZapEnabled* [för Set-HostedContentFilterPolicy-cmdlet](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) i Exchange Online PowerShell eller Exchange Online Protection PowerShell.

### <a name="phish-and-spam-zap-requirements-exclusions-and-notices"></a>Phish och Spam ZAP krav, undantag och meddelanden

> [!IMPORTANT]
> den tidigare *ZapEnabled* cmdlet parameter som kontrollerade både Phish och Spam ZAP kommer att **avbokas 1 februari 2020**. Om du har skrivit några skript som använder parametern ZapEnabled rekommenderar vi att du uppdaterar dem så att de använder SpamZapEnabled och PhishZapEnabled. Under övergångsperioden kommer alla 3 parametrar (ZapEnabled, PhishZapEnabled och SpamZapEnabled) att vara tillgängliga via cmdleten. Tills uttryckligen anges via UI eller PowerShell, PhishZapEnabled och SpamZapEnabled kommer att visa ett ärvt värde från ZapEnabled parametern. När de nya parametrarna har ställts in kommer de inte längre att ärva från parametern ZapEnabled. När den är föråldrad zapEnabled kommer inte att ha någon inverkan på PhishZapEnabled eller SpamZapEnabled egenskaper och ZapEnabled kommer att tas bort från listan över parametrar i cmdlets.

ZAP kommer inte att flytta något meddelande till Karantän som är i färd med dynamisk leverans skanning, eller som redan har en Malware dom med en ersatt bilaga. Om en phish eller spam signal tas emot för dessa typer av meddelanden och Spam politik / Phish åtgärder är inställd på att vidta vissa åtgärder (Flytta till Skräp, Omdirigera, Ta bort, Karantän) då ZAP kommer standard till en "Flytta till Skräp" åtgärd. För att ZAP ska kunna vidta en åtgärd för att flytta till skräppost i ett meddelande måste användaren ha aktiverat skräppostskydd med standardinställningarna för skräppost. (Mer information om användaralternativ i Outlook finns ändra [skyddsnivån i skräppostfiltret.)](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)

## <a name="how-to-see-if-zap-moved-your-message"></a>Så här ser du om ZAP har flyttat ditt meddelande

För att avgöra om ZAP har flyttat meddelandet kan du använda antingen [rapporten Statusför hotskydd](view-email-security-reports.md#threat-protection-status-report) eller [Threat Explorer (och identifiering i realtid).](threat-explorer.md) Observera att ZAP som systemåtgärd inte är inloggad i granskningsloggar för utbytespostlådan. 
 
## <a name="disable-zap"></a>Inaktivera ZAP

Information om hur du ansluter till Exchange Online PowerShell finns i [Anslut till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Information om hur du ansluter till Exchange Online Protection PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

### <a name="disable-malware-zap"></a>Inaktivera Malware ZAP **

Malware ZAP kan inaktiveras via *ZapEnabled-parametern* på [Cmdlet Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) i Exchange Online PowerShell eller Exchange Online Protection PowerShell. Malware ZAP kan också aktiveras eller inaktiveras genom att redigera malware policy i Säkerhets-och Compliance Center.

I det här exemplet inaktiveras ZAP i filterprincipen för skadlig kod med namnet "Test".

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

Detaljerad syntax- och parameterinformation finns i [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).

### <a name="disable-phish-zap-and-spam-zap"></a>Inaktivera Phish ZAP och Spam ZAP

Om du vill inaktivera Phish och Spam ZAP för din O365-klientorganisation, eller en uppsättning användare, använder du *phishzapenabled* och *spamZapEnabled-parametrarna* [för Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy), en EOP-cmdlet.

I följande exempel inaktiveras phish och spam ZAP för en innehållsfilterprincip med namnet "Test".

```Powershell
Set-HostedContentFilterPolicy -Identity Test -PhishZapEnabled $false -SpamZapEnabled $false
```

Detaljerad syntax- och parameterinformation finns [i Ange ContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy).

## <a name="faq"></a>Vanliga frågor och svar

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>Vad händer om ett legitimt meddelande flyttas till skräppostmappen?

Du bör följa den normala rapporteringsprocessen för [falskt positiva](prevent-email-from-being-marked-as-spam.md). Den enda anledningen till att meddelandet skulle flyttas från inkorgen till skräppostmappen skulle bero på att tjänsten har fastställt att meddelandet var skräppost eller skadligt.

### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>Vad gör jag om jag använder karantänen för Office 365 i stället för skräppostmappen?

ZAP kommer att vidta åtgärder i enlighet med konfigurationen av phish och spam åtgärdinställningar i din Anti-spam politik. Se ovan för mer information om malware, Phish och Spam ZAP.

### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>Vad händer om jag har en anpassad regel för e-postflöde (Block/ Tillåt regel)?

Regler som skapats av administratörer (regler för e-postflöde) eller Blockera och Tillåt regler har företräde. Sådana meddelanden är undantagna från funktionsvillkoren så att e-postflödet följer regelåtgärden (Blockera/tillåt regel).

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a>Vad händer om ett meddelande flyttas till en annan mapp (t.ex. inkorgsregel)?

ZAP fungerar fortfarande i det här fallet, om inte meddelandet har tagits bort eller är i Skräppost.

### <a name="does-zap-change-the-email-header"></a>Har ZAP ändra e-huvudet?

En ZAP-åtgärd gör inga ändringar i ett e-postmeddelandes rubrik.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Hur påverkar ZAP postlådor på Hold?

ZAP tar inte bort meddelanden från spärrade postlådor och tar därför inte en åtgärd för flytta till karantän på meddelanden. Meddelanden flyttas fortfarande till skräppostmappen om de anges av principen. 

[Klicka här för mer information om brevlådan innehar.](https://docs.microsoft.com/exchange/policy-and-compliance/holds/holds?view=exchserver-2019)

## <a name="related-topics"></a>Relaterade ämnen

[Skydd mot skräppost i Office 365](anti-spam-protection.md)

[Block email spam with the Office 365 spam filter to prevent false negative issues](reduce-spam-email.md)
