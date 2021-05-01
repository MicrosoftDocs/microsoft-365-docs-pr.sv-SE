---
title: Exempel på nätfiskeattack
description: Gå igenom en exempelanalys av nätfiskeangrepp.
keywords: incidenter, aviseringar, undersöker, korrelation, attack, datorer, enheter, användare, identiteter, identiteter, postlåda, e-post, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fb3656a9d3f67d979c012d9cc316a10e65a72042
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114785"
---
# <a name="example-of-a-phishing-email-attack"></a>Exempel på nätfiskeattack

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**
- Microsoft 365 Defender

Microsoft 365 Defender kan hjälpa dig att identifiera skadliga bifogade filer som levereras via e-post. Eftersom [Office 365 Säkerhets-](https://protection.office.com/) och efterlevnadscenter är integrerat med Microsoft 365 Defender kan säkerhetsanalytiker se hot som kommer in från Office 365, till exempel via e-postbilagor.

En analytiker har till exempel tilldelats ett incident i flera steg.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="Exempel på incident i flera steg"::: 

På fliken **Aviseringar** för incidenten visas aviseringar från Defender för Office 365 och Microsoft Cloud App Security visas. Analytikern kan granska nedåt i Defender för att få Office 365 avisering genom att välja e-postmeddelanden. Informationen om aviseringen visas i sidofönstret.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="Exempel på en e-postavisering":::
 
Genom att rulla nedåt ytterligare visas mer information som visar skadliga filer och användare som har påverkats.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="Exempel på hur en e-postavisering påverkar användare och filer":::
  
Om **du väljer sidan** Öppna avisering kommer du till den specifika aviseringen där olika information kan visas mer ingående genom att klicka på länken. Själva e-postmeddelandet kan visas genom **att välja Visa meddelanden i Utforskaren** längst ned i panelen.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="Exempel på information om en avisering"::: 

Då kommer analytikern till sidan Threat Management där e-postmeddelandet Ämne, Mottagare, Avsändare och annan information visas. **ZAP** under **Specialåtgärder** meddelar analytikern att automatisk rensning har implementerats med nolltimmarsrensning. ZAP identifierar och tar automatiskt bort skadliga meddelanden och skräppostmeddelanden från postlådor i hela organisationen. Mer information finns i [ZAP (Zero-hour auto purge) i Exchange Online](../office-365-security/zero-hour-auto-purge.md).

Andra åtgärder kan vidtas på specifika meddelanden genom att välja **Åtgärder**. 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="Exempel på andra åtgärder som kan vidtas på e-postmeddelanden"::: 

## <a name="next-step"></a>Nästa steg

Se den [identitetsbaserade](first-incident-path-identity.md) attackundersökningssökvägen.

## <a name="see-also"></a>Se även

- [Översikt över incidenter](incidents-overview.md)
- [Analysera incidenter](investigate-incidents.md)
- [Hantera incidenter](manage-incidents.md)
