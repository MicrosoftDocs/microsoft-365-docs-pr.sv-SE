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
ms.date: 11/22/2019
ms.collection:
- M365-security-compliance
description: Integrera din organisations SIEM-server med Office 365 Avancerat skydd och relaterade hot händelser i Office 365 Activity Management API.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b3ed2efd2b59397853623ffcec93e8011793ab43
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656605"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>SIEM integrering med avancerat skydd

Om din organisation använder en säkerhets tillbuds Server (SIEM) kan du integrera Office 365 Avancerat skydd med din SIEM-Server. SIEM integrering gör att du kan visa information, till exempel skadlig program vara eller Phish som identifieras av Office 365 Avancerat skydd, i SIEM Server-rapporter. Om du vill ställa in SIEM-integrering använder du [API för aktivitets hantering i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).

API: t för aktivitets hantering i Office 365 hämtar information om åtgärder och händelser för användare, administratörer, system och principer från organisationens Microsoft 365 för företag-och Azure Active Directory-aktivitets loggar. Det avancerade [hotet Protection-schemat för office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) fungerar med avancerat skydd, så om din organisation har Office 365-prenumerationen för avancerat skydd 1 eller abonnemang 2 eller Office 365 E5 kan du fortfarande använda samma API för din Siem Server-integrering.

Som en del av de senaste uppdateringarna har vi också lagt till händelser från automatiserade undersökningar och svars funktioner i Office 365 ATP-abonnemang 2 i administrations aktivitets API för Office 365. Förutom att inkludera uppgifter om grundläggande undersöknings uppgifter, till exempel ID, namn och status, innehåller den också information om undersöknings åtgärder och-enheter.

SIEM-servern eller liknande system ska **Granska granskningen. allmän** arbets belastning för att få åtkomst till identifierings händelser. Mer information finns i [komma igång med Office 365 Management API: er](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). Dessutom är följande värden för **AuditLogRecordType** relevanta för Office 365 ATP-händelser:

### <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType-Type: EDM. Int32

#### <a name="auditlogrecordtype"></a>AuditLogRecordType

****

|Value|Medlems namn|Beskrivning|
|---|---|---|
|28|ThreatIntelligence|Phishing-och malware-händelser från Exchange Online Protection och Office 365 Avancerat skydd.|
|41|ThreatIntelligenceUrl|ATP-säkra länkar tids-för-blockera och blockera händelser från Office 365 Avancerat skydd.|
|47|ThreatIntelligenceAtpContent|Phishing-och malware-händelser för filer i SharePoint Online, OneDrive för företag och Microsoft Teams från Office 365 Avancerat skydd.|
|64|Luftprövning|Automatiserade undersökningar och svars händelser, till exempel information om undersökningar och relevanta artefakter från Office 365 Avancerat skydds abonnemang 2.|
|

> [!IMPORTANT]
> Du måste vara global administratör eller ha rollen som säkerhets administratör tilldelad för säkerhets & efterlevnad för att konfigurera SIEM-integrering med Office 365 Avancerat skydd.<br/>Gransknings loggning måste vara aktiverat för din Microsoft 365-miljö. Om du behöver hjälp kan du läsa [Aktivera och inaktivera gransknings loggs ökning](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="related-topics"></a>Relaterade ämnen

[Office 365 undersökning av hot och svar](office-365-ti.md)

[Automatisk undersökning och svar (AIR) i Office 365](automated-investigation-response-office.md)

[Office 365 Avancerat skydd](office-365-atp.md)

[Smarta rapporter och insikter i säkerhetsrelaterade &amp; Center](reports-and-insights-in-security-and-compliance.md)

[Behörigheter i säkerhetsrelaterade &amp; Center](permissions-in-the-security-and-compliance-center.md)
