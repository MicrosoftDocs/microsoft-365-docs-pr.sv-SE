---
title: SIEM integrering med Microsoft Defender för Office 365
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
description: Integrera din organisations SIEM-server med Microsoft Defender för Office 365 och relaterade hot händelser i Office 365 Activity Management API.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 93ff1606130c60ceb46087d28bb26f9a6d27d330
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615666"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>SIEM integrering med Microsoft Defender för Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Om din organisation använder en säkerhets information och en server för Event Management (SIEM) kan du integrera Microsoft Defender för Office 365 med din SIEM-Server. Du kan ställa in denna integrering genom att använda [API för aktivitets hantering i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).

SIEM integrering gör att du kan visa information, till exempel skadlig program vara eller Phish som identifieras av Microsoft Defender för Office 365, i dina SIEM Server-rapporter.

- Om du vill se ett exempel på SIEM-integrering med Microsoft Defender för Office 365, se Tech (community) för [SOC med Defender för office 365 och O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

- Mer information om API-gränssnitten för Office 365 finns i [Översikt över API för office 365 Management](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).

## <a name="how-siem-integration-works"></a>Så fungerar SIEM-integrering

API: t för aktivitets hantering i Office 365 hämtar information om åtgärder och händelser för användare, administratörer, system och principer från organisationens Microsoft 365-och Azure Active Directory-aktivitets loggar. Om din organisation har Microsoft Defender för Office 365 abonnemang 1 eller 2 eller Office 365 E5 kan du använda [Microsoft Defender för office 365-schemat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).

Nyligen har händelser från automatiserade undersökningar och svars funktioner i [Microsoft Defender för office 365 abonnemang 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) lagts till i API för hanterings aktiviteten för Office 365. Förutom att inkludera uppgifter om grundläggande undersöknings uppgifter, till exempel ID, namn och status, innehåller API: n också information om undersöknings åtgärder och-enheter.

SIEM-servern eller liknande system avsöker **granskningen. allmänna** arbets belastning för att få åtkomst till identifierings händelser. Mer information finns i [komma igång med Office 365 Management API: er](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType-Type: EDM. Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

I följande tabell sammanfattas de värden för **AuditLogRecordType** som är relevanta för Microsoft Defender för Office 365-händelser:

|Value|Medlems namn|Beskrivning|
|---|---|---|
|28|ThreatIntelligence|Phishing-och malware-händelser från Exchange Online Protection och Microsoft Defender för Office 365.|
|41|ThreatIntelligenceUrl|Säkra länkar tids-och Blocks händelser från Microsoft Defender för Office 365.|
|47|ThreatIntelligenceAtpContent|Phishing-och malware-händelser för filer i SharePoint Online, OneDrive för företag och Microsoft Teams från Microsoft Defender för Office 365.|
|64|Luftprövning|Automatiserade undersökningar och svars händelser, till exempel information om undersökningar och relevanta artefakter, från Microsoft Defender för Office 365 abonnemang 2.|
|

> [!IMPORTANT]
> Du måste vara global administratör eller ha rollen som säkerhets administratör tilldelad för säkerhets & Compliance Center för att konfigurera SIEM-integrering med Microsoft Defender för Office 365.
>
> Gransknings loggning måste vara aktiverat för din Microsoft 365-miljö. Om du behöver hjälp kan du läsa [Aktivera och inaktivera gransknings loggs ökning](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="see-also"></a>Se även

[Office 365 undersökning av hot och svar](office-365-ti.md)

[Automatisk undersökning och svar (AIR) i Office 365](automated-investigation-response-office.md)

