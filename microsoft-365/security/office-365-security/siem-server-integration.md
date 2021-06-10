---
title: SIEM-serverintegrering med Microsoft 365 och program
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Få en översikt över säkerhetsinformation och händelsehantering (SIEM) serverintegrering med dina Microsoft 365 och program
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bea8aa3914da4b813f3928eddbb6df9c98ef6605
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599953"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Säkerhetsinformation och händelsehantering (SIEM)-serverintegrering med Microsoft 365 och program

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>Sammanfattning

Använder eller planerar din organisation att skaffa en säkerhetsinformations- och händelsehanteringsserver (SIEM) ? Du kanske undrar hur det går att integrera med Microsoft 365 eller Office 365. Den här artikeln innehåller en lista över resurser som du kan använda för att integrera DIN SIEM-server Microsoft 365 tjänster och program.

> [!TIP]
> Om du inte har en SIEM-server ännu och utforskar alternativen kan du överväga **[att Microsoft Azure Sentinel.](/azure/sentinel/overview)**

## <a name="do-i-need-a-siem-server"></a>Behöver jag en SIEM-server?

Om du behöver en SIEM-server beror på många faktorer, till exempel organisationens säkerhetskrav och var dina data finns. Microsoft 365 innehåller ett brett utbud av säkerhetsfunktioner som uppfyller många organisationers säkerhetsbehov utan ytterligare servrar, till exempel en SIEM-server. Vissa organisationer har särskilda omständigheter som kräver användningen av en SIEM-server. Här är några exempel:

- *Fabrikam* har en del innehåll och program lokalt och en del i molnet (de har en hybridmolndistribution). För att få säkerhetsrapporter för allt innehåll och alla program har Fabrikam implementerat en SIEM-server.

- *Contoso* är en organisation för finansiella tjänster som har särskilt strikta säkerhetskrav. De har lagt till en SIEM-server i miljön för att kunna dra nytta av det extra säkerhetsskydd de behöver.

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM-serverintegrering med Microsoft 365

En SIEM-server kan ta emot data från en mängd Microsoft 365 tjänster och program. I följande tabell visas flera Microsoft 365-tjänster och -program, tillsammans med SIEM-serverindata och -resurser för mer information.

****

|Microsoft 365 Tjänst eller program|SIEM-serverindata/-metoder|Resurser för att få mer information|
|---|---|---|
|[Microsoft Defender för Office 365](defender-for-office-365.md)|Granskningsloggar|[SIEM-integrering med Microsoft Defender för Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender för Endpoint](/windows/security/threat-protection/)|HTTPS-slutpunkt med Azure som värd <p> REST API|[Dra aviseringar till dina SIEM-verktyg](../defender-endpoint/configure-siem.md)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)|Loggintegrering|[SIEM-integrering med Microsoft Cloud App Security](/cloud-app-security/siem)|
|

> [!TIP]
> Ta en titt på [Azure Sentinel](/azure/sentinel/overview). Azure Sentinel levereras med kopplingar för Microsoft-lösningar. Dessa kopplingar är tillgängliga "utan att använda" och ger integration i realtid. Du kan använda Azure Sentinel med dina Microsoft 365 Defender-lösningar och Microsoft 365-tjänster, inklusive Office 365, Azure AD, Microsoft Defender för identitet, Microsoft Cloud App Security med mera.

### <a name="audit-logging-must-be-turned-on"></a>Granskningsloggning måste vara aktiverat

Kontrollera att granskningsloggning är aktiverat innan du konfigurerar SIEM-serverintegrering.

- För SharePoint Online, OneDrive för företag och Azure Active Directory är granskningsloggning aktiverad i Säkerhets- & [efterlevnadscenter.](../../compliance/turn-audit-log-search-on-or-off.md)

- Mer Exchange Online finns i Hantera [granskning av postlåda.](../../compliance/enable-mailbox-auditing.md)

## <a name="more-resources"></a>Fler resurser

[Integrera säkerhetslösningar i Azure Defender](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrera Microsoft Graph-säkerhets-API-aviseringar med ett SIEM](/graph/security-integration)