---
title: Hitta hot på olika enheter och e-postmeddelanden med avancerad jakt
description: Studera vanliga jaktscenarier och exempelfrågor som täcker enheter och e-postmeddelanden.
keywords: avancerad jakt, Office365-data, Windows-enheter, Office365-e-postmeddelanden normaliserar, e-postmeddelanden, hotjakt, cyberhotjakt, sökning, fråga, telemetri, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: ec7f9083401fdf7a2114d99ddd2dcc009411e34b
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633513"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a>Jakten på hot på olika enheter och e-postmeddelanden

**Gäller:**
- Microsoft Hotskydd



[Med avancerad jakt](advanced-hunting-overview.md) i Microsoft Threat Protection kan du proaktivt jaga efter hot på dina Windows-enheter och Microsoft-e-postmeddelanden. Här är några jaktscenarier och exempelfrågor som kan hjälpa dig att utforska hur du kan skapa frågor som täcker både enheter och e-postmeddelanden.

## <a name="obtain-user-accounts-from-email-addresses"></a>Hämta användarkonton från e-postadresser
När du skapar frågor över [tabeller som täcker enheter och e-postmeddelanden](advanced-hunting-schema-tables.md)måste du förmodligen skaffa användarnamn från avsändare eller mottagare e-postadresser. Så här använder du den lokala värden från *e-postadressen:*

```kusto
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

Den här normaliseringstekniken används i de efterföljande scenarierna.

## <a name="hunting-scenarios"></a>Jaktscenarier

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a>Kontrollera om filer från en känd skadlig avsändare finns på dina enheter
Om du antar att du känner till en e-postadress som skickar skadliga filer kan du köra den här frågan för att avgöra om det finns filer från den här avsändaren på dina enheter. Du kan till exempel använda den här frågan för att fastställa antalet enheter som påverkas av en distributionskampanj för skadlig kod.

```kusto
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
DeviceFileEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a>Granska inloggningsförsök efter mottagandet av skadliga e-postmeddelanden
Den här frågan hittar de 10 senaste inloggningarna som utförs av e-postmottagare inom 30 minuter efter att de fått kända skadliga e-postmeddelanden. Du kan använda den här frågan för att kontrollera om e-postmottagarnas konton har komprometterats.

```kusto
//Find logons that occurred right after malicious email was received
let MaliciousEmail=EmailEvents
| where MalwareFilterVerdict == "Malware" 
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmail
| join (
DeviceLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a>Granska PowerShell-aktiviteter efter mottagandet av e-postmeddelanden från känd skadlig avsändare
Skadliga e-postmeddelanden innehåller ofta dokument och andra specialtillverkade bilagor som kör PowerShell-kommandon för att leverera ytterligare nyttolaster. Om du är medveten om e-postmeddelanden som kommer från en känd skadlig avsändare kan du använda den här frågan för att lista och granska PowerShell-aktiviteter som inträffade inom 30 minuter efter att ett e-postmeddelande togs emot från avsändaren .  

```kusto
//Find PowerShell activities right after email was received from malicious sender
let x=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
x
| join (
DeviceProcessEvents
| where FileName =~ "powershell.exe"
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Använda delade frågor](advanced-hunting-shared-queries.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
