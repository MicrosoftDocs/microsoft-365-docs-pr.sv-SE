---
title: SIEM-serverintegrering med Microsoft 365-tjänster och -program
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Få en översikt över SIEM-serverintegrering (Security Information and Event Management) med dina Microsoft 365-molntjänster och -program
ms.openlocfilehash: c52f24c6260c890b1f6d8612efacb78f9b08be86
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035266"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Siem-serverintegration (Security Information and Event Management) med Microsoft 365-tjänster och -program

## <a name="summary"></a>Sammanfattning

Använder eller planerar din organisation att skaffa en SIEM-server (Security Information and Event Management). Du kanske undrar hur den integreras med Microsoft 365 eller Office 365. Den här artikeln innehåller en lista över resurser som du kan använda för att integrera din SIEM-server med Microsoft 365-tjänster och -program.

> [!TIP]
> Om du inte har en SIEM-server ännu och utforskar dina alternativ bör du överväga **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.

## <a name="do-i-need-a-siem-server"></a>Behöver jag en SIEM-server?

Om du behöver en SIEM-server beror på många faktorer, till exempel organisationens säkerhetskrav och var dina data finns. Microsoft 365 innehåller en mängd olika säkerhetsfunktioner som uppfyller många organisationers säkerhetsbehov utan ytterligare servrar, till exempel en SIEM-server. Vissa organisationer har särskilda omständigheter som kräver användning av en SIEM-server. Här är några exempel:

- *Fabrikam* har visst innehåll och program lokalt, och vissa i molnet (de har en hybridmolndistribution). För att få säkerhetsrapporter över allt innehåll och alla program har Fabrikam implementerat en SIEM-server.

- *Contoso* är en organisation för finansiella tjänster som har särskilt stränga säkerhetskrav. De har lagt till en SIEM-server i sin miljö för att dra nytta av det extra säkerhetsskydd de behöver.

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM-serverintegrering med Microsoft 365

En SIEM-server kan ta emot data från en mängd olika Microsoft 365-tjänster och -program. I följande tabell visas flera Microsoft 365-tjänster och -program, tillsammans med SIEM-serverindata och resurser för att lära dig mer.

||||
|---|---|---|
|**Microsoft 365-tjänst eller program**|**SIEM-serveringångar/metoder**|**Resurser för att få mer information**|
|[Office 365 Avancerat skydd](office-365-atp.md)|Granskningsloggar|[SIEM-integrering med avancerat hotskydd i Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender Avancerat skydd](https://docs.microsoft.com/windows/security/threat-protection/)|HTTPS-slutpunkt som finns i Azure <br/>REST API|[Dra varningar till dina SIEM-verktyg](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|Loggintegrering|[SIEM-integrering med Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> Ta en titt på [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview). Azure Sentinel levereras med kopplingar för Microsoft-lösningar. Dessa kopplingar är tillgängliga "out of the box" och ger för integration i realtid. Du kan använda Azure Sentinel med dina Microsoft Threat Protection-lösningar och Microsoft 365-tjänster, inklusive Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security med mera.

### <a name="audit-logging-must-be-turned-on"></a>Granskningsloggning måste vara aktiverat

Kontrollera att granskningsloggning är aktiverat innan du konfigurerar INTEGRERING av SIEM-servrar.

- För SharePoint Online, OneDrive för företag och Azure Active Directory [aktiveras granskningsloggning i Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).

- För Exchange Online finns i [Hantera granskning av postlådan](../../compliance/enable-mailbox-auditing.md).

## <a name="more-resources"></a>Fler resurser

[Integrera säkerhetslösningar i Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrera Microsoft Graph Security API-varningar med en SIEM](https://docs.microsoft.com/graph/security-integration)
