---
title: Exempel på avancerad sökning för Microsoft Defender för Office 365
description: Kom igång med att söka efter e-posthot med avancerad sökning
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, custom detections, schema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ac49b4afde0951e7a034c5c11114afbc52c293
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/16/2021
ms.locfileid: "52965154"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>Exempel på avancerad sökning för Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

Vill du komma igång med att söka efter e-posthot med avancerad sökning? Prova det här:

Avsnittet [Komma igång](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) i artikeln [Microsoft Defender för Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) har en logisk tidig konfigurationsdel som ser ut så här:

1. Konfigurera allt med "Anti" i namnet.
   - Skydd mot skadlig programvara
   - Skydd mot nätfiske
   - Skräppostskydd
2. Konfigurera allt med "Valv" i namnet.
   - Säkra länkar
   - Säkra bifogade filer
3. Försvara arbets belastningarna (t. ex. SharePoint Online, OneDrive och Teams).
4. Skydda med automatisk rensning utan timme.

Tillsammans med en [länk](../office-365-security/protect-against-threats.md) kan du hoppa direkt in och få igång konfigurationen dag 1.

Det sista steget i **Komma igång** skyddar användare med **Automatisk rensning**, även kallat ZAP. Det kan vara mycket viktigt att veta om du har lyckats med ZAP:a ett misstänkt eller skadligt e-postmeddelande efter leverans.

Att snabbt kunna navigera till Kusto frågespråk för att leta efter problem är en fördel med konvergering av dessa två säkerhetscenter. Säkerhetsteam kan övervaka ZAP-misser genom att vidta nästa steg [här,](https://security.microsoft.com/advanced-hunting)under **Sökning** \> **efter avancerad sökning.**

1. På sidan Advanced Hunting klickar du på **Query**.
1. Kopiera frågan nedan till frågefönstret.
1. Välj **Kör fråga.**

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="Sidan Avancerad sökning (under Sök) med Fråga markerad högst upp i frågepanelen och kör en Kusto-fråga för att fånga ZAP-åtgärder under de senaste 7 dagarna.":::

Data från den här frågan visas i resultatpanelen under själva frågan. Resultaten innehåller information som ‘Enhetsnamn’, ‘KontoVisningsNamn’ och ‘ZapTid’ i en anpassningsbar resultatuppsättning. Resultat kan även exporteras för posterna. Om frågan är en du behöver igen väljer du **Spara** > **Spara som** och lägger till frågan i din lista med frågor, delade frågor eller communityfrågor.

## <a name="related-information"></a>Relaterad information
- [Avancerade metodtips för sökning](advanced-hunting-best-practices.md)
- [Översikt – Avancerad sökning](advanced-hunting-overview.md)
