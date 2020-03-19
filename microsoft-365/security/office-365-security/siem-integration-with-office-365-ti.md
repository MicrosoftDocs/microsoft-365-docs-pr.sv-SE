---
title: SIEM-integrering med Office 365 Avancerat hotskydd
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
description: Integrera organisationens SIEM-server med Office 365 Advanced Threat Protection och relaterade hothändelser i Office 365 Activity Management API.
ms.openlocfilehash: 8a870e02a37ea7f4961d0b8dc42a49cb59d2bace
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42807652"
---
# <a name="siem-integration-with-office-365-advanced-threat-protection"></a>SIEM-integrering med Office 365 Avancerat hotskydd

Om din organisation använder en SIEM-server (Security Incident and Event Management) kan du integrera Office 365 Advanced Threat Protection med SIEM-servern. Med SIEM-integrering kan du visa information, till exempel skadlig kod eller phish som upptäckts av Office 365 Advanced Protection, i SIEM-serverrapporterna. Om du vill konfigurera SIEM-integrering använder du [API:et för Aktivitetshantering i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

Office 365 Activity Management API hämtar information om åtgärder och åtgärder och händelser för användare, administratörer, system och principer från organisationens Aktivitetsloggar för Office 365 och Azure Active Directory. [Office 365 Advanced Threat Protection-schemat](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) fungerar med avancerat hotskydd, så om din organisation har Office 365 Advanced Threat Protection Plan 1 eller Plan 2 eller Office 365 E5 kan du fortfarande använda samma API för din SIEM-serverintegrering. 

Som en del av våra senaste uppdateringar har vi också lagt till händelser från automatiska undersöknings- och svarsfunktioner i Office 365 ATP Plan 2 i Api:et för Office 365 Management Activity. Förutom att inkludera data om centrala undersökningsdetaljer som ID, namn och status innehåller den även information på hög nivå om utredningsåtgärder och enheter.   

SIEM-servern eller något annat liknande system bör avsöka **den audit.general-arbetsbelastningen** för att komma åt identifieringshändelser. Mer information finns i [Komma igång med Office 365 Management API:er](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). Dessutom är följande värden för **AuditLogRecordType** relevanta för Office 365 ATP-händelser:

### <a name="enum-auditlogrecordtype---type-edmint32"></a>Uppräkning: AuditLogRecordType - Typ: Edm.Int32

#### <a name="auditlogrecordtype"></a>Granskaloggposttyp

|Value|Medlemsnamn|Beskrivning|
|:-----|:-----|:-----|
|28|HotIntelligens|Händelser med nätfiske och skadlig kod från Exchange Online Protection och Office 365 Advanced Threat Protection.|
|41|ThreatIntelligenceUrl|TIME-of-block-händelser och blockera ATP-säkerhetslänkar och blockera åsidosätta händelser från Office 365 Advanced Threat Protection.|
|47|ThreatIntelligenceAtpContent|Händelser för nätfiske och skadlig kod för filer i SharePoint Online, OneDrive för företag och Microsoft Teams från Office 365 Advanced Threat Protection.|
|64|Flygutredning|Automatiserade gransknings- och svarshändelser, till exempel undersökningsinformation och relevanta artefakter från Office 365 Advanced Threat Protection Plan 2.|


> [!IMPORTANT]
> Du måste vara en global Office 365-administratör eller ha rollen säkerhetsadministratör som tilldelats säkerhets& Compliance Center för att konfigurera SIEM-integrering med Office 365 Advanced Threat Protection.<br/>Granskningsloggning måste vara aktiverad för din Office 365-miljö. Information om hur du får hjälp med detta finns [i Aktivera eller inaktivera sökningen i granskningsloggen för Office 365](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="related-topics"></a>Relaterade ämnen

[Office 365 hotutredning och svar](office-365-ti.md)

[Automatiserad undersökning och svar (AIR) i Office 365](automated-investigation-response-office.md)

[Office 365 Avancerat hotskydd](office-365-atp.md)

[Smarta rapporter och insikter i Office &amp; 365 Security Compliance Center](reports-and-insights-in-security-and-compliance.md)
  
[Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
  
