---
title: SIEM-integrering med Microsoft Defender för Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integrera organisationens SIEM-server med Microsoft Defender för Office 365 och relaterade hothändelser i API:t för hantering av office 365-aktivitet.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a456ee970015aea5936ae86ec009cb2ff46e99c2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072505"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>SIEM-integrering med Microsoft Defender för Office 365

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Om organisationen använder en säkerhetsinformations- och händelsehanteringsserver (SIEM) kan du integrera Microsoft Defender för Office 365 med DIN SIEM-server. Du kan konfigurera denna integrering med hjälp av [API:t för hantering av Office 365-aktivitet.](/office/office-365-management-api/office-365-management-activity-api-reference)

Med SIEM-integrering kan du visa information, t.ex. skadlig kod eller phish som upptäckts av Microsoft Defender för Office 365, i dina SIEM-serverrapporter.

- Ett exempel på SIEM-integrering med Microsoft Defender för Office 365 finns i Tech Community-bloggen: Öka effektiviteten i SOC med Defender för [Office 365 och O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)Management API.

- Mer information om Office 365-hanterings-API:er finns i Översikt över [Office 365-hanterings-API:er.](/office/office-365-management-api/office-365-management-apis-overview)

## <a name="how-siem-integration-works"></a>Så här fungerar SIEM-integrering

API:t för hantering av aktivitet i Office 365 hämtar information om användar-, administratörs-, system- och principåtgärder och -händelser från organisationens Microsoft 365- och Azure Active Directory-aktivitetsloggar. Om din organisation har Microsoft Defender för Office 365 abonnemang 1 eller 2 eller Office 365 E5 kan du använda Microsoft Defender för [Office 365-schemat.](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)

Nyligen lades händelser från automatiserad undersökning och svarsfunktioner i Microsoft Defender för [Office 365 abonnemang 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) till i API:t för hanteringsaktivitet i Office 365. Förutom att inkludera data om grundläggande undersökningsinformation som ID, namn och status innehåller API:et även hög nivå-information om undersökningsåtgärder och enheter.

SIEM-servern eller något annat liknande system avsöker arbetsbelastningen **audit.general** för att komma åt identifieringshändelser. Mer information finns i Komma [igång med API:er för Hantering av Office 365.](/office/office-365-management-api/get-started-with-office-365-management-apis)

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Uppräkning: AuditLogRecordType – Typ: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

I följande tabell sammanfattas värdena för **AuditLogRecordType** som är relevanta för Microsoft Defender för Office 365-händelser:

|Value|Medlemsnamn|Beskrivning|
|---|---|---|
|28|ThreatIntelligence|Nätfiske- och skadlig programvara från Exchange Online Protection och Microsoft Defender för Office 365.|
|41|ThreatIntelligenceUrl|Tid för blockering av säkra länkar och blockera åsidosättningshändelser från Microsoft Defender för Office 365.|
|47|ThreatIntelligenceAtpContent|Nätfiske- och skadlig kod för filer i SharePoint Online, OneDrive för företag och Microsoft Teams från Microsoft Defender för Office 365.|
|64|AirInvestigation|Automatisk undersökning och svarshändelser, till exempel undersökningsinformation och relevanta artefakter, från Microsoft Defender för Office 365 abonnemang 2.|
|

> [!IMPORTANT]
> Du måste vara global administratör eller ha säkerhetsadministratörsrollen tilldelad till Säkerhets- och &-efterlevnadscenter för att konfigurera SIEM-integrering med Microsoft Defender för Office 365.
>
> Granskningsloggning måste vara aktiverad i Microsoft 365-miljön. Om du behöver hjälp med detta kan du [gå till Aktivera eller inaktivera granskningsloggsökning.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="see-also"></a>Se även

[Office 365 undersökning av hot och svar](office-365-ti.md)

[Automatiserad undersökning och svar (AIR) i Office 365](automated-investigation-response-office.md)