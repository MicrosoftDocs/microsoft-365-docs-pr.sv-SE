---
title: 'Microsoft 365 Defender tillbuds-API: er och resurs typen för incidenten'
description: Lär dig mer om metoderna och egenskaperna för resurs typen incident i Microsoft 365 Defender
keywords: incident, incidenter, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 372c939f5eed29832725e6b048735040ca7391d6
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719340"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365 Defender-incidenter API och resurs typen för incidenten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gäller för:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Vissa uppgifter gäller för FÖRLANSERADE produkter som kan komma att ändras väsentligt innan de saluförs. Microsoft lämnar inga garantier, uttryckliga eller underförstådda, med avseende på informationen som tillhandahålls här.

En [olycka](incidents-overview.md) är en samling relaterade aviseringar som hjälper dig att beskriva en attack. Händelser från olika enheter i organisationen aggregeras automatiskt efter Microsoft 365 Defender. Du kan använda API-programatically för att få åtkomst till din organisations incidenter och relaterade aviseringar.

## <a name="quotas-and-resource-allocation"></a>Kvoter och resurstilldelning

Du kan begära upp till 50 samtal per minut eller 1500 samtal per timme. Varje metod har också sina egna kvoter. Mer information om metod specifika kvoter finns i respektive artikel för den metod du vill använda.

En `429` http-svarskod visar att du har nått en kvot, antingen av antalet begär Anden som skickats eller via utsatt tid för drift. Svars texten inkluderar tiden tills den kvot du nådde återställs.

## <a name="permissions"></a>Behörigheter

För incident API krävs olika typer av behörigheter för varje metod. Mer information om vilka behörigheter som krävs finns i respektive metod.

## <a name="methods"></a>Verifieringsmetoder

Metod | Returtyp | Beskrivning
-|-|-
[Lista incidenter](api-list-incidents.md) | [Incident](api-incident.md) lista | Få en lista över incidenter.
[Uppdatera incident](api-update-incidents.md) | [Händelse](api-incident.md) | Uppdatera en specifik olycka.

## <a name="request-body-response-and-examples"></a>Begära brödtext, svar och exempel

Se de olika metod artiklarna för att få mer information om hur man skapar en begäran eller tolkar ett svar samt för praktiska exempel.

## <a name="common-properties"></a>Gemensamma egenskaper

Egenskap | Type (Typ) | Beskrivning
-|-|-
incidentId | tids | Unikt ID för incidenten.
redirectIncidentId | null-värde långa | Incident-ID för den aktuella incidenten slogs samman till.
incidentName | strängvärdet | Namnet på incidenten.
createdTime | DateTimeOffset | Datum och tid (i UTC) då incidenten skapades.
lastUpdateTime | DateTimeOffset | Datum och tid (i UTC) då incidenten senast uppdaterades.
Tilldelat | strängvärdet | Ägaren till incidenten.
allvarlighets grad | Enum | Allvarlighets grad för incidenten. Möjliga värden är: ```UnSpecified``` , ```Informational``` , ```Low``` , ```Medium``` och ```High``` .
status | Enum | Anger den aktuella statusen för incidenten. Möjliga värden är: ```Active``` , ```Resolved``` och ```Redirected``` .
nomenklatur | Enum | Specifikation av felet. Möjliga värden är: ```Unknown``` , ```FalsePositive``` , ```TruePositive``` .
bedömning | Enum | Anger hur incidenten ska visas. Möjliga värden är: ```NotAvailable``` , ```Apt``` , ```Malware``` , ```SecurityPersonnel``` , ```SecurityTesting``` , ```UnwantedSoftware``` , ```Other``` .
taggen | sträng lista | Lista över incident koder.
larm | Aviserings lista | Lista med relaterade aviseringar. Se exemplen på API-dokumentation för [samtal](api-list-incidents.md) .

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över Microsoft 365 Defender API](api-overview.md)
- [Incident översikt](incidents-overview.md)
- [API för List frågor](api-list-incidents.md)
- [Uppdatera API för incident](api-update-incidents.md)
