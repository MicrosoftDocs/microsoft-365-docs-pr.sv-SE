---
title: SIEM-integrering med avancerat hotskydd
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0527a998e7049960df840c7756ef5deaafaf5ade
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035278"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>SIEM-integrering med avancerat hotskydd

Om din organisation använder en SIEM-server (Security Incident and Event Management) kan du integrera Office 365 Advanced Threat Protection med DIN SIEM-server. Med SIEM-integrering kan du visa information, till exempel skadlig kod eller phish som upptäckts av Office 365 Advanced Protection, i dina SIEM-serverrapporter. Om du vill konfigurera SIEM-integrering använder du [API:et för Aktivitetshantering i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

Api:et för Aktivitetshantering i Office 365 hämtar information om användar-, administratörs-, system- och principåtgärder och händelser från organisationens Microsoft 365 för företag och Azure Active Directory-aktivitetsloggar. [Schemat för avancerat skydd mot hot i Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) fungerar med avancerat skydd mot hot, så om din organisation har Office 365 Advanced Threat Protection Plan 1 eller Plan 2 eller Office 365 E5 kan du fortfarande använda samma API för din SIEM-serverintegration. 

Som en del av våra senaste uppdateringar har vi också lagt till händelser från automatiska undersöknings- och svarsfunktioner i Office 365 ATP-abonnemang 2 inom Office 365 Management Activity API. Förutom att inkludera data om grundläggande undersökningsinformation som ID, namn och status, innehåller den också information på hög nivå om undersökningsåtgärder och enheter.   

SIEM-servern eller något annat liknande system bör avsöka **audit.general-arbetsbelastningen** för att komma åt identifieringshändelser. Mer information finns [i Komma igång med API:er för hantering av Office 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). Dessutom är följande värden för **AuditLogRecordType** relevanta för Office 365 ATP-händelser:

### <a name="enum-auditlogrecordtype---type-edmint32"></a>Uppräkning: AuditLogRecordType - Typ: Edm.Int32

#### <a name="auditlogrecordtype"></a>AuditLogRecordType

|Value|Medlemmens namn|Beskrivning|
|:-----|:-----|:-----|
|28|HotIntelligens|Nätfiske- och skadlig kodhändelser från Exchange Online Protection och Office 365 Advanced Threat Protection.|
|41|ThreatIntelligenceUrl|ATP Safe Links tid för block- och blockera åsidosättningshändelser från Office 365 Advanced Threat Protection.|
|47|ThreatIntelligenceAtpContent|Nätfiske- och skadlig kodhändelser för filer i SharePoint Online, OneDrive för företag och Microsoft Teams från Office 365 Advanced Threat Protection.|
|64|Luftutredning|Automatiserade undersöknings- och svarshändelser, till exempel undersökningsinformation och relevanta artefakter från Office 365 Advanced Threat Protection Plan 2.|


> [!IMPORTANT]
> Du måste vara global administratör eller ha rollen säkerhetsadministratör tilldelad för Security & Compliance Center för att konfigurera SIEM-integrering med Office 365 Advanced Threat Protection.<br/>Granskningsloggning måste vara aktiverat för din Microsoft 365-miljö. Information om hur du får hjälp med detta finns i [Aktivera eller inaktivera granskningsloggsökning](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="related-topics"></a>Relaterade ämnen

[Office 365 undersökning av hot och svar](office-365-ti.md)

[Automatisk undersökning och svar (AIR) i Office 365](automated-investigation-response-office.md)

[Office 365 Avancerat skydd](office-365-atp.md)

[Smarta rapporter och insikter &amp; i Security Compliance Center](reports-and-insights-in-security-and-compliance.md)
  
[Behörigheter i &amp; Säkerhetsefterlevnadscenter](permissions-in-the-security-and-compliance-center.md)
  
