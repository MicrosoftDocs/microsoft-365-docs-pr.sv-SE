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
description: Integrera organisationens SIEM-server med Microsoft Defender för Office 365 och relaterade hothändelser i API:t för hantering av aktivitetshantering för Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f637750a31b5034d2ee1110ab0070fa6abcda49b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290399"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>SIEM-integrering med Microsoft Defender för Office 365

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Om organisationen använder en säkerhetsinformations- och händelsehanteringsserver (SIEM) kan du integrera Microsoft Defender för Office 365 med din SIEM-server. Du kan konfigurera den här integreringen med hjälp av API:t för hantering av [aktivitet i Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)

Med SIEM-integrering kan du visa information, till exempel skadlig kod eller phish som upptäckts av Microsoft Defender för Office 365, i dina SIEM-serverrapporter.

- Ett exempel på SIEM-integrering med Microsoft Defender för Office 365 finns i Tech Community-bloggen: Effektivisera soc-programmet med Defender för [Office 365 och O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)Management API.

- Mer information om API:er för hantering av Office 365 finns i översikten över [API:er för hantering i Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)

## <a name="how-siem-integration-works"></a>Så här fungerar SIEM-integrering

API:t för hantering av aktivitet i Office 365 hämtar information om användar-, administratörs-, system- och principåtgärder och händelser från organisationens Microsoft 365- och Azure Active Directory-aktivitetsloggar. Om din organisation har Microsoft Defender för Office 365 abonnemang 1 eller 2 eller Office 365 E5 kan du använda Microsoft Defender för [Office 365-schemat.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)

Nyligen lades händelser från automatiserad undersökning och svarsfunktioner i Microsoft Defender för [Office 365-abonnemang 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) till i API:t för hanteringsaktivitet i Office 365. Förutom att inkludera data om grundläggande undersökningsinformation, till exempel ID, namn och status, innehåller API:t även högnivåinformation om undersökningsåtgärder och enheter.

SIEM-servern eller något annat liknande system omröstningar om arbetsbelastningen **för audit.general** för åtkomstidentifieringshändelser. Mer information finns i Komma igång med API:er för hantering av [Office 365.](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Uppräkning: AuditLogRecordType – Typ: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

I följande tabell sammanfattas värdena för **AuditLogRecordType** som är relevanta för Microsoft Defender för Office 365-händelser:

|Value|Medlemsnamn|Beskrivning|
|---|---|---|
|28|ThreatIntelligence|Nätfiske- och skadlig kodhändelser från Exchange Online Protection och Microsoft Defender för Office 365.|
|41|ThreatIntelligenceUrl|Tid för blockering av säkra länkar och blockera åsidosättningshändelser från Microsoft Defender för Office 365.|
|47|ThreatIntelligenceAtpContent|Nätfiske- och skadlig kodhändelser för filer i SharePoint Online, OneDrive för företag och Microsoft Teams, från Microsoft Defender för Office 365.|
|64|AirInvestigation|Automatiserad undersökning och svarshändelser, till exempel undersökningsinformation och relevanta artefakter, från Microsoft Defender för Office 365 abonnemang 2.|
|

> [!IMPORTANT]
> Du måste vara global administratör eller ha säkerhetsadministratörsrollen tilldelad till Säkerhets- och efterlevnadscenter & för att konfigurera SIEM-integrering med Microsoft Defender för Office 365.
>
> Granskningsloggning måste aktiveras i Microsoft 365-miljön. Mer information finns i Aktivera eller [inaktivera granskningsloggsökning.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="see-also"></a>Se även

[Office 365 undersökning av hot och svar](office-365-ti.md)

[Automatiserad undersökning och svar (AIR) i Office 365](automated-investigation-response-office.md)

