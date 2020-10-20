---
title: SIEM integrering med avancerat skydd
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integrera din organisations SIEM-server med Office 365 Avancerat skydd och relaterade hot händelser i Office 365 Activity Management API.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c4c92fc45546d3d8022a3925baa9c10f9bd0090b
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600559"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>SIEM integrering med avancerat skydd

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Om din organisation använder en säkerhets information och en server för Event Management (SIEM) kan du integrera Office 365 Avancerat skydd (Office 365 ATP) med din SIEM-Server. Du kan ställa in denna integrering genom att använda [API för aktivitets hantering i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

SIEM integrering gör att du kan visa information, till exempel skadlig program vara eller Phish som identifieras av Office 365 ATP, i SIEM Server-rapporter. 

- Om du vill se ett exempel på SIEM-integrering med Office 365 ATP kan du läsa [Tech Community-bloggen: förbättra SOC i office 365 ATP och O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

- Mer information om API-gränssnitten för Office 365 finns i [Översikt över API för office 365 Management](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).

## <a name="how-siem-integration-works"></a>Så fungerar SIEM-integrering

API: t för aktivitets hantering i Office 365 hämtar information om åtgärder och händelser för användare, administratörer, system och principer från organisationens Microsoft 365-och Azure Active Directory-aktivitets loggar. Om organisationen har Office 365 ATP 1 eller 2 eller Office 365 E5 kan du använda [office 365 ATP-schemat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).  

Nyligen genomförda händelser från automatiserade undersökningar och svars funktioner i [office 365 ATP-abonnemang 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) har lagts till i API för hanterings aktiviteten för Office 365. Förutom att inkludera uppgifter om grundläggande undersöknings uppgifter, till exempel ID, namn och status, innehåller API: n också information om undersöknings åtgärder och-enheter.

SIEM-servern eller liknande system avsöker **granskningen. allmänna** arbets belastning för att få åtkomst till identifierings händelser. Mer information finns i [komma igång med Office 365 Management API: er](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). 

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType-Type: EDM. Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

I följande tabell sammanfattas de värden i **AuditLogRecordType** som är relevanta för Office 365 ATP-händelser:

|Värde|Medlems namn|Beskrivning|
|---|---|---|
|28|ThreatIntelligence|Phishing-och malware-händelser från Exchange Online Protection och Office 365 ATP.|
|41|ThreatIntelligenceUrl|Säkra länkar tids-och Blocks händelser från Office 365 ATP.|
|47|ThreatIntelligenceAtpContent|Phishing-och malware-händelser för filer i SharePoint Online, OneDrive för företag och Microsoft Teams från Office 365 ATP.|
|64|Luftprövning|Automatiserade undersökningar och svars händelser, till exempel information om undersökningar och relevanta artefakter, från Office 365 ATP-abonnemang 2.|
|

> [!IMPORTANT]
> Du måste vara global administratör eller ha rollen som säkerhets administratör tilldelad för säkerhets & efterlevnad för att konfigurera SIEM-integrering med Office 365 Avancerat skydd.<br/>Gransknings loggning måste vara aktiverat för din Microsoft 365-miljö. Om du behöver hjälp kan du läsa [Aktivera och inaktivera gransknings loggs ökning](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="see-also"></a>Se även

[Office 365 undersökning av hot och svar](office-365-ti.md)

[Automatisk undersökning och svar (AIR) i Office 365](automated-investigation-response-office.md)

