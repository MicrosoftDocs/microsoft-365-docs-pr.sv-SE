---
title: Metoder och egenskaper för åtgärdsaktivitet
description: API-svaret innehåller aktiviteter & för säkerhetshantering som skapats i klientorganisationen. Du kan begära alla åtgärdsaktiviteter, bara en åtgärdsaktivitet eller information om exponerade enheter för en vald åtgärdsaktivitet.
keywords: apis, remediation, remediation api, get, remediation tasks,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f720d638ec469523a1d567dee9c01fa0974b0090
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061158"
---
# <a name="remediation-activity-methods-and-properties"></a>Metoder och egenskaper för åtgärdsaktivitet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

API-svaret innehåller [& åtgärder för](next-gen-threat-and-vuln-mgt.md)   säkerhetshantering som har skapats i klientorganisationen.  

## <a name="methods"></a>Metoder

Metod | Datatyp | Beskrivning
:---|:---|:---
[Lista alla åtgärder](get-remediation-all-activities.md) | Samling för undersökning | Returnerar information om alla åtgärder.
[Lista över exponerade enheter med en åtgärdsaktivitet](get-remediation-exposed-devices-activities.md) | Undersökningsentitet | Returnerar information om exponerade enheter för den angivna åtgärdsaktiviteten.
[Få en åtgärdsaktivitet efter ID](get-remediation-one-activity.md) | Undersökningsentitet | Returnerar information för den angivna åtgärdsaktiviteten.

Läs mer [om åtgärder](tvm-remediation.md).

## <a name="properties"></a>Egenskaper

Egenskaps-ID | Datatyp | Beskrivning
:---|:---|:---
kategori | Sträng | Kategori för åtgärdsaktiviteten (konfiguration av programvara/säkerhet)
completerEmail | Sträng | Om åtgärdsaktiviteten har slutförts manuellt av någon innehåller den här kolumnen deras e-postadress
completerId | Sträng | Om åtgärdsaktiviteten har slutförts manuellt av någon innehåller den här kolumnen deras objekt-ID
completionMethod | Sträng | En åtgärdsaktivitet kan slutföras "automatiskt" (om alla enheter korrigeras) eller "manuellt" av en person som väljer "markera som slutförd".
createdOn | DateTime | Tidpunkten då den här åtgärdsaktiviteten skapades
beskrivning | Sträng | Beskrivning av den här åtgärdsaktiviteten
dueOn | DateTime | Förfallodatum som skapare uppsättningen för den här åtgärdsaktiviteten
fixedDevices |  | Antalet enheter som har åtgärdats
id | Sträng | ID för den här åtgärdsaktiviteten
nameId | Sträng | Relaterade produktnamn
prioritet | Sträng | Prioritet för skaparuppsättningen för den här åtgärdsaktiviteten (Hög\Medel\Låg)
productId | Sträng | Relaterade produkt-ID
productivityImpactRemediationType | Sträng | Några konfigurationsändringar kunde endast begäras för enheter utan påverkan från användare. Det här värdet anger valet mellan "alla exponerade enheter" eller "endast enheter utan påverkan från användare".
rbacGroupNames | Sträng | Gruppnamn för relaterade enheter
recommendedProgram | Sträng | Rekommenderat program att uppgradera till
recommendedVendor | Sträng | Rekommenderad leverantör att uppgradera till
recommendedVersion | Sträng | Rekommenderad version att uppdatera/uppgradera till
relatedComponent | Sträng | Relaterad komponent i den här åtgärdsaktiviteten (som liknar den relaterade komponenten för en säkerhetsrekommendationer)
requesterEmail | Sträng | E-postadress skapad
requesterId | Sträng | Creator-objekt-ID
requesterNotes | Sträng | Anteckningarna (fri text) som skaparen har lagt till för den här åtgärdsaktiviteten
scid | Sträng | SCID för relaterad säkerhetsrekommendationer
status | Sträng | Status för åtgärdsaktivitet (Aktiv/slutförd)
statusLastModifiedOn | DateTime | Datum när statusfältet uppdaterades
targetDevices | Long | Antal exponerade enheter som denna åtgärd gäller för
rubrik | Sträng | Rubrik för den här åtgärdsaktiviteten
skriv | Sträng | Åtgärdstyp
vendorId | Sträng | Relaterade leverantörsnamn

## <a name="see-also"></a>Se även

- [Få en åtgärdsaktivitet efter ID](get-remediation-one-activity.md)

- [Lista alla åtgärder](get-remediation-all-activities.md)

- [Lista över exponerade enheter med en åtgärdsaktivitet](get-remediation-exposed-devices-activities.md)

- [Riskbaserade hot & sårbarhetshantering](next-gen-threat-and-vuln-mgt.md)

- [Svagheter i organisationen](tvm-weaknesses.md)
