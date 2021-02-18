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
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Få en översikt över säkerhetsinformation och händelsehantering (SIEM) serverintegrering med Microsoft 365-molntjänster och -program
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b4490d52cbd403bf4ce2cc3f3fb3c5a91c5646b9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290387"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Säkerhetsinformation och händelsehantering (SIEM) serverintegrering med Microsoft 365-tjänster och -program

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>Sammanfattning

Använder eller planerar organisationen en säkerhetsinformations- och händelsehanteringsserver (SIEM)? Du kanske undrar hur det är integrerat med Microsoft 365 eller Office 365. Den här artikeln innehåller en lista över resurser som du kan använda för att integrera DIN SIEM-server med Microsoft 365-tjänster och -program.

> [!TIP]
> Om du inte har en SIEM-server ännu och utforskar alternativen kan du överväga **[Microsoft Azure Sentinel.](https://docs.microsoft.com/azure/sentinel/overview)**

## <a name="do-i-need-a-siem-server"></a>Behöver jag en SIEM-server?

Om du behöver en SIEM-server beror på många faktorer, till exempel organisationens säkerhetskrav och var dina data finns. Microsoft 365 innehåller ett brett utbud av säkerhetsfunktioner som uppfyller många organisationers säkerhetsbehov utan ytterligare servrar, till exempel en SIEM-server. Vissa organisationer har särskilda omständigheter som kräver användningen av en SIEM-server. Här är några exempel:

- *Fabrikam* har en del innehåll och program lokalt och vissa i molnet (de har en hybridmolndistribution). För att få fram säkerhetsrapporter i allt innehåll och i alla program har Fabrikam implementerat en SIEM-server.

- *Contoso* är en organisation för finansiella tjänster som har särskilt strikta säkerhetskrav. De har lagt till en SIEM-server i sin miljö för att dra nytta av det extra säkerhetsskydd som de kräver.

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM-serverintegrering med Microsoft 365

En SIEM-server kan ta emot data från en mängd olika Microsoft 365-tjänster och -program. I följande tabell finns flera Microsoft 365-tjänster och -program samt SIEM-serverindata och resurser för mer information.

****

|Microsoft 365-tjänst eller -program|SIEM-serverindata/-metoder|Resurser för att få mer information|
|---|---|---|
|[Microsoft Defender för Office 365](office-365-atp.md)|Granskningsloggar|[SIEM-integrering med Microsoft Defender för Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender för Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)|HTTPS-slutpunkt i Azure <p> REST API|[Dra aviseringar till dina SIEM-verktyg](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|Loggintegrering|[SIEM-integrering med Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> Ta en titt på [Azure Sentinel.](https://docs.microsoft.com/azure/sentinel/overview) Azure Sentinel levereras med kopplingar för Microsoft-lösningar. De här anslutningarna är tillgängliga så att de kan integreras i realtid. Du kan använda Azure Sentinel med dina Microsoft 365 Defender-lösningar och Microsoft 365-tjänster, inklusive Office 365, Azure AD, Microsoft Defender för identitet, Microsoft Cloud App Security med mera.

### <a name="audit-logging-must-be-turned-on"></a>Granskningsloggning måste vara aktiverad

Kontrollera att granskningsloggning är aktiverad innan du konfigurerar SIEM-serverintegrering.

- För SharePoint Online, OneDrive för företag och Azure Active Directory är granskningsloggning aktiverad i Säkerhets- [& Efterlevnadscenter.](../../compliance/turn-audit-log-search-on-or-off.md)

- Mer information om Exchange Online finns i [Hantera granskning av postlådor.](../../compliance/enable-mailbox-auditing.md)

## <a name="more-resources"></a>Fler resurser

[Integrera säkerhetslösningar i Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrera Microsoft Graph-säkerhets-API-aviseringar med en SIEM](https://docs.microsoft.com/graph/security-integration)
