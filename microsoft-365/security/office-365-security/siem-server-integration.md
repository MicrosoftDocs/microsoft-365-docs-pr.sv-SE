---
title: SIEM Server integration med Microsoft 365-tjänster och-program
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
description: Få en översikt över säkerhets information och SIEM Server integration med Microsoft 365-molntjänster och-program
ms.openlocfilehash: 0e582333615d11c500b114225435903cea386ade
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846406"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Integrering av säkerhets information och Event Management (SIEM) med Microsoft 365-tjänster och-program

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="summary"></a>Sammanfattning

Använder du din organisation för att få en server för säkerhets information och Event Management (SIEM)? Du kanske undrar hur det är integrerat med Microsoft 365 eller Office 365. I den här artikeln finns en lista med resurser som du kan använda för att integrera din SIEM-server med Microsoft 365-tjänster och-program.

> [!TIP]
> Om du inte har en SIEM-Server ännu och utforskar dina alternativ bör du överväga **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.

## <a name="do-i-need-a-siem-server"></a>Behöver jag en SIEM-Server?

Om du behöver en SIEM-Server beror på många faktorer, till exempel organisationens säkerhets krav och var dina data finns. Microsoft 365 innehåller en mängd olika säkerhetsfunktioner som uppfyller många organisationers säkerhets behov utan extra servrar, till exempel en SIEM-Server. Vissa organisationer har särskilda omständigheter som kräver användning av en SIEM-Server. Här är några exempel:

- *Fabrikam* har ett visst innehåll och program i lokaler och vissa i molnet (de har en hybrid moln distribution). Fabrikam har implementerat en SIEM-Server för att få säkerhets rapporter för allt innehåll och alla program.

- *Contoso* är en finans tjänst organisation som har särskilt stränga säkerhets krav. De har lagt till en SIEM-server i sin miljö för att utnyttja det extra säkerhets skydd de kräver.

## <a name="siem-server-integration-with-microsoft-365"></a>SIEM Server integration med Microsoft 365

En SIEM-Server kan ta emot data från en mängd olika Microsoft 365-tjänster och-program. I följande tabell visas flera Microsoft 365-tjänster och-program, tillsammans med SIEM och resurser för att få mer information.

****

|Microsoft 365-tjänsten eller-programmet|SIEM-Server data/metoder|Resurser för att få mer information|
|---|---|---|
|[Microsoft Defender för Office 365](office-365-atp.md)|Gransknings loggar|[SIEM integrering med Microsoft Defender för Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender för slut punkt](https://docs.microsoft.com/windows/security/threat-protection/)|HTTPS-slutpunkt med Azure värd <br/>REST API|[Dra aviseringar till dina SIEM-verktyg](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|Logg integrering|[SIEM integrering med säkerhet för Microsoft Cloud App](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> Ta en titt på [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview). Azure Sentinel kommer med anslutningar för Microsoft Solutions. Dessa kopplingar är tillgängliga "i kartongen" och möjliggör integrering i real tid. Du kan använda Azure Sentinel med Microsoft 365 Defender-lösningarna och Microsoft 365-tjänsterna, inklusive Office 365, Azure AD, Microsoft Defender för identitet, Microsoft Cloud App-säkerhet och mycket mer.

### <a name="audit-logging-must-be-turned-on"></a>Gransknings loggning måste aktive ras

Kontrol lera att gransknings loggning är aktiverat innan du konfigurerar SIEM.

- För SharePoint Online, OneDrive för företag och Azure Active Directory [aktive ras gransknings loggning i säkerhets & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).

- För Exchange Online, se [hantera granskning av post låda](../../compliance/enable-mailbox-auditing.md).

## <a name="more-resources"></a>Fler resurser

[Integrera säkerhetslösningar i Azure Defender *](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrera Microsoft Graph-säkerhetsfunktionerna med en SIEM](https://docs.microsoft.com/graph/security-integration)
