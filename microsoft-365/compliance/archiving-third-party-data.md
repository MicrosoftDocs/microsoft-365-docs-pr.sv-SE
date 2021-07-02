---
title: Arkivera data från tredje part
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du importerar data från tredje part från plattformar för sociala medier, snabbmeddelandeplattformar och dokumentsamarbete till Microsoft 365 postlådor.
ms.openlocfilehash: 76df1ffa7afdeeda9a35744e9e4bfffae4576ca9
ms.sourcegitcommit: 8c6a5db0dab99a82a69dd8a0a7c56af1cb825931
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53276959"
---
# <a name="archive-third-party-data-in-microsoft-365"></a>Arkivera data från tredje part i Microsoft 365

Microsoft 365 kan administratörer använda datakopplingar för att importera och arkivera data från tredje part från plattformar för sociala medier, snabbmeddelanden och plattformar för dokumentsamarbete till postlådor i Microsoft 365 organisation. En av de största fördelarna med att använda datakopplingar för att importera och arkivera data från tredje part i Microsoft 365 är att du kan använda olika Microsoft 365-efterlevnadslösningar för dem när de har importerats. På så sätt kan du säkerställa att organisationens data som inte är Microsoft följer föreskrifter och standarder som påverkar organisationen.

## <a name="third-party-data-connectors"></a>Datakopplingar för tredje part

I Microsoft 365 Efterlevnadscenter finns inbyggda dataanslutningar från tredje part från Microsoft för att importera data från olika datakällor, till exempel LinkedIn, Instant Bloomberg och Twitter, och datakopplingar som stöder Insider-riskhanteringslösningen. Förutom dessa dataanslutningar arbetar Microsoft tillsammans med följande partner för att tillhandahålla många fler tredjepartsdatakopplingar i Microsoft 365 Efterlevnadscenter. Din organisation arbetar med dessa partner för att konfigurera arkiveringstjänsten innan en motsvarande datakoppling skapas i Microsoft 365 Efterlevnadscenter.

- [Veritas](#veritas-data-connectors)

- [TeleMessage](#telemessage-data-connectors)

- [17a-4 LLC](#17a-4-data-connectors)

- [CellTrust](#celltrust-data-connectors)

Data från tredje part som listas i nästa avsnitt (förutom HR-data och fysiska badgingdata som används för Microsoft 365 Insider-riskhanteringslösningen) importeras till användarnas postlådor. De Microsoft 365 efterlevnadslösningar som stöder data från tredje part tillämpas på den användarpostlåda där data lagras.

### <a name="microsoft-data-connectors"></a>Microsoft-datakontakter

I följande tabell visas de inbyggda datakopplingarna från tredje part som är tillgängliga i Microsoft 365 Efterlevnadscenter. Tabellen sammanfattar även de efterlevnadslösningar som du kan använda efter att du har importerat och arkiverat data från tredje Microsoft 365. I avsnittet [Översikt över efterlevnadslösningar](#overview-of-compliance-solutions-that-support-third-party-data) som stöder data från tredje part finns en mer detaljerad beskrivning av varje efterlevnadslösning och hur den har stöd för data från tredje part.

Klicka på länken i **kolumnen med data från** tredje part om du vill ha stegvisa anvisningar för hur du skapar en koppling för den datatypen.

|Data från tredje part  |Bevarande av juridiska skäl|eDiscovery  |Inställningar för bevarande  |Hantering av arkivhandlingar  |Kommunikationsefterlevnad  |Hantering av insiderrisk  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Bloomberg-meddelande](archive-bloomberg-message-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[Personalavdelningen](import-hr-data.md) ||||||![Bockmarkering](../media/checkmark.png)
|[ICE-chatt](archive-icechat-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[LinkedIn](archive-linkedin-data.md)   |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[Fysisk aktivitet](import-physical-badging-data.md) ||||||![Bockmarkering](../media/checkmark.png)|
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
||||||||

### <a name="veritas-data-connectors"></a>Veritas-datakopplingar

Tabellen i det här avsnittet innehåller de datakopplingar från tredje part som är tillgängliga i samarbete med Veritas. Tabellen sammanfattar även de efterlevnadslösningar som du kan använda på data från tredje part efter att du har importerat och arkiverat dem i Microsoft 365. I avsnittet [Översikt över efterlevnadslösningar](#overview-of-compliance-solutions-that-support-third-party-data) som stöder data från tredje part finns en mer detaljerad beskrivning av varje efterlevnadslösning och hur den har stöd för data från tredje part.

Innan du kan arkivera data från tredje part i Microsoft 365 måste du arbeta med Veritas och konfigurera deras arkiveringstjänst (kallas *Merge1*) för organisationen. Om du vill ha mer information klickar du på länken i **datakolumnen** från tredje part om du vill gå till steg-för-steg-instruktionerna för att skapa en koppling för den datatypen.

|Data från tredje part  |Bevarande av juridiska skäl|eDiscovery  |Inställningar för bevarande  |Hantering av arkivhandlingar  |Kommunikationsefterlevnad  |Hantering av insiderrisk  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust](archive-celltrust-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Cisco Jabber på MS SQL](archive-ciscojabberonmssql-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Cisco Jabber på Oracle](archive-ciscojabberonoracle-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Cisco Jabber på PostgreSQL](archive-ciscojabberonpostgresql-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[EML](archive-eml-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[FX-anslutning](archive-fxconnect-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Jive](archive-jive-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[MS SQL-databas](archive-mssqldatabaseimporter-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[Pivot](archive-pivot-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Redtail Speak](archive-redtailspeak-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Reuters Dealing](archive-reutersdealing-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Reuters Eikon](archive-reuterseikon-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Reuters FX](archive-reutersfx-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[RingCentral](archive-ringcentral-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[Salesforce Chatter](archive-salesforcechatter-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[ServiceNow](archive-servicenow-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[EDiscovery för slack](archive-slack-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Symphony](archive-symphony-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Textavgränsad](archive-text-delimited-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[Webex Teams](archive-webexteams-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Webbsidor](archive-webpagecapture-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[Arbetsplats från Facebook](archive-workplacefromfacebook-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[XIP](archive-xip-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[XSLT/XML](archive-xslt-xml-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[Yieldbroker](archive-yieldbroker-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Zooma möten](archive-zoommeetings-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
||||||||

### <a name="telemessage-data-connectors"></a>TeleMessage-datakontakter

Tabellen i det här avsnittet innehåller de datakopplingar från tredje part som är tillgängliga i samarbete med TeleMessage. Tabellen sammanfattar även de efterlevnadslösningar som du kan använda på data från tredje part efter att du har importerat och arkiverat dem i Microsoft 365. I avsnittet [Översikt över efterlevnadslösningar](#overview-of-compliance-solutions-that-support-third-party-data) som stöder data från tredje part finns en mer detaljerad beskrivning av varje efterlevnadslösning och hur den har stöd för data från tredje part.

Innan du kan arkivera data från tredje Microsoft 365 måste du arbeta med TeleMessage och konfigurera deras arkiveringstjänst för organisationen. Om du vill ha mer information klickar du på länken i **datakolumnen** från tredje part om du vill gå till steg-för-steg-instruktionerna för att skapa en koppling för den datatypen.

TeleMessage-dataanslutningar är också tillgängliga GCC miljöer i Microsoft 365 för myndigheter i USA. Mer information finns i avsnittet [Dataanslutningar i molnet för myndigheter i USA i](#data-connectors-in-the-us-government-cloud) den här artikeln.

|Data från tredje part  |Bevarande av juridiska skäl|eDiscovery  |Inställningar för bevarande  |Hantering av arkivhandlingar  |Kommunikationsefterlevnad  |Hantering av insiderrisk  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android](archive-android-archiver-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[AT&T Network](archive-att-network-archiver-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Bell-nätverk](archive-bell-network-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Företagsnummer](archive-enterprise-number-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[O2-nätverk](archive-o2-network-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[TELUS-nätverk](archive-telus-network-data.md)    |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Verizon-nätverk](archive-verizon-network-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[WeChat](archive-wechat-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[WhatsApp](archive-whatsapp-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
||||||||

### <a name="17a-4-data-connectors"></a>17a-4 datakopplingar

Tabellen i det här avsnittet innehåller de datakopplingar från tredje part som är tillgängliga i samarbete med 17a-4 LLC. Tabellen sammanfattar även de efterlevnadslösningar som du kan använda på data från tredje part efter att du har importerat och arkiverat dem i Microsoft 365. I avsnittet [Översikt över efterlevnadslösningar](#overview-of-compliance-solutions-that-support-third-party-data) som stöder data från tredje part finns en mer detaljerad beskrivning av varje efterlevnadslösning och hur den har stöd för data från tredje part.

Innan du kan arkivera data från tredje part i Microsoft 365 måste du arbeta med Veritas och konfigurera deras arkiveringstjänst (som kallas *DataParser)* för organisationen. Om du vill ha mer information klickar du på länken i **datakolumnen** från tredje part om du vill gå till steg-för-steg-instruktionerna för att skapa en koppling för den datatypen.

|Data från tredje part  |Bevarande av juridiska skäl|eDiscovery  |Inställningar för bevarande  |Hantering av arkivhandlingar  |Kommunikationsefterlevnad  |Hantering av insiderrisk  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[BlackBerry](archive-17a-4-blackberry-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Bloomberg](archive-17a-4-bloomberg-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Cisco Jabber](archive-17a-4-cisco-jabber-data.md)   |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Cisco Webex](archive-17a-4-webex-teams-data.md)   |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[FactSet](archive-17a-4-factset-data.md)    |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Fuze](archive-17a-4-fuze-data.md)    |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[FX-anslutning](archive-17a-4-fxconnect-data.md)    |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[ICE-chatt](archive-17a-4-ice-im-data.md)    |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[InvestEdge](archive-17a-4-investedge-data.md)    |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Konversationsmoln för LivePerson](archive-17a-4-liveperson-data.md)    |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Quip](archive-17a-4-quip-data.md)    |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Refinitiv Eikon Messenger](archive-17a-4-refinitiv-messenger-data.md)    |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[ServiceNow](archive-17a-4-servicenow-data.md)    |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Slack](archive-17a-4-slack-data.md)    |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[SQL](archive-17a-4-sql-database-data.md)    |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Symphony](archive-17a-4-symphony-data.md)    |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Zooma](archive-17a-4-zoom-data.md)    |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
||||||||

### <a name="celltrust-data-connectors"></a>CellTrust-datakopplingar

Tabellen i det här avsnittet innehåller den datakoppling från tredje part som är tillgänglig i samarbete med CellTrust. Tabellen sammanfattar även de efterlevnadslösningar som du kan använda på data från tredje part efter att du har importerat och arkiverat dem i Microsoft 365. I avsnittet [Översikt över efterlevnadslösningar](#overview-of-compliance-solutions-that-support-third-party-data) som stöder data från tredje part finns en mer detaljerad beskrivning av varje efterlevnadslösning och hur den har stöd för data från tredje part.

Innan du kan arkivera data från tredje part i Microsoft 365 måste du arbeta med CellTrust och konfigurera deras arkiveringstjänst (kallas *CellTrust SL2)* för organisationen. Om du vill ha mer information klickar du på länken i **kolumnen data** från tredje part för att gå till steg-för-steg-instruktionerna för att skapa en CellTrust SL2-koppling.

|Data från tredje part  |Bevarande av juridiska skäl|eDiscovery  |Inställningar för bevarande  |Hantering av arkivhandlingar  |Kommunikationsefterlevnad  |Hantering av insiderrisk  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[CellTrust SL2](archive-data-from-celltrustsl2.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
||||||||

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>Översikt över efterlevnadslösningar som stöder data från tredje part

I följande avsnitt beskrivs några av de saker som Microsoft 365-efterlevnadslösningar kan hjälpa dig att hantera data från tredje part som listas i föregående tabell.

### <a name="litigation-hold"></a>Bevarande av juridiska skäl

Du placerar bevarande [av juridiska skäl](create-a-litigation-hold.md) på en användarpostlåda för att behålla data från tredje part. När du skapar ett väntande företag kan du ange varaktigheten (kallas även tidsbaserat holdat) så att borttagna och ändrade data från tredje part behålls under en angiven tidsperiod och sedan tas bort permanent från postlådan. Du kan också bara behålla innehåll på obestämd tid (kallas oändligt *bevarande)* eller tills bevarande av juridiska skäl har tagits bort.

### <a name="ediscovery"></a>eDiscovery

De tre primära eDiscovery-verktygen i Microsoft 365 är Innehållssökning, Bas-eDiscovery och Advanced eDiscovery.

- **[Innehållssökning](content-search.md).** Du kan använda verktyget för innehållssökning för att söka i postlådor efter data från tredje part som du har importerat. Du kan använda sökfrågor och villkor för att begränsa sökresultaten och exportera sökresultatet.

- **[Core eDiscovery](get-started-core-ediscovery.md).** Det här verktyget bygger på de grundläggande sök- och exportfunktionerna genom att du kan skapa ärenden så att du kan styra vem som kan komma åt ärendedata, placera ett ärende i användarpostlådor eller postlådeinnehåll som matchar sökvillkor. Det innebär att du kan placera ett eDiscovery-hold på data från tredje part som har importerats till användarnas postlådor.

- **[Advanced eDiscovery](overview-ediscovery-20.md).** Det här kraftfulla verktyget utökar funktionen för bas-eDiscovery genom att låta dig lägga till biblioteksman i ett ärende, sätta objekt av godtyckliga objekt i förvaring och sedan läsa in en granskare från tredje part i en granskning för vidare analys, till exempel teman och dubblettidentifiering. När du har läser in data från tredje part i en granskningsuppsättning kan du köra frågor och filtrera dem efter en begränsad resultatuppsättning.

   Både Bas-eDiscovery och Advanced eDiscovery kan du hantera tredjepartsdata som kan vara relevanta för organisationens juridiska eller interna undersökningar.

### <a name="retention-settings"></a>Inställningar för bevarande

Du kan tillämpa en [bevarandeprincip på](retention.md) användarnas postlådor för att behålla och sedan ta bort data från tredje part (och annat innehåll i postlådan) när lagringsperioden gått ut. Du kan också använda bevarandeprinciper för att ta bort data från tredje part under en viss ålder eller använda bevarandeetiketter för att utlösa en [dispositionsgranskning](disposition.md) när lagringstiden för data från tredje part löper ut.

### <a name="records-management"></a>Hantering av arkivhandlingar

Med [funktionen för](records-management.md) hantering av arkivhandlingar Microsoft 365 du deklarera data från tredje part som arkivhandlingar. Det kan göras manuellt av användare som använder en bevarandeetikett som markerar data från tredje part i postlådan som arkivering. Du kan även använda bevarandeetiketter automatiskt genom att identifiera känslig information, nyckelord eller innehållstyper i data från tredje part.

### <a name="communication-compliance"></a>Kommunikationsefterlevnad

Du kan använda [kommunikationsefterlevnad](communication-compliance.md) för att undersöka data från tredje part och kontrollera att de är kompatibla med organisationens datastandarder. Det kan du göra genom att identifiera, samla in och vidta åtgärdsåtgärder för olämpliga meddelanden i organisationen. Du kan till exempel övervaka data från tredje part som du importerar för anstötligt språk, känslig information och regelefterlevnad.

### <a name="insider-risk-management"></a>Hantering av insiderrisk

Signaler från data från tredje part, t.ex. [](insider-risk-management.md) selektiva HR-data, kan användas av Insider-riskhanteringslösningen för att minimera interna risker genom att låta dig identifiera, undersöka och agera på riskfyllda aktiviteter i organisationen. Till exempel används data som importerats av HR-datakopplingen som riskindikatorer för att identifiera avgående datastöld av anställda.

## <a name="data-connectors-in-the-us-government-cloud"></a>Datakopplingar i molnet för myndigheter i USA

Som tidigare nämnts är dataanslutningar från TeleMessage tillgängliga i molnet för myndigheter i USA. I följande tabell visas de specifika myndighetsmiljöer som stöder varje TeleMessage-datakoppling. Mer information om amerikanska myndigheters moln finns i [Microsoft 365 för myndigheter i USA.](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/microsoft-365-government-how-to-buy)

|Datakoppling för TeleMessage  |GCC  |GCC Hög  |DoD  |
|:---------|:---------|:---------|:---------|
|Android-arkivering | Ja | Nej | Nej |
|AT&T SMS/MMS-nätverksarkivering | Ja | Nej | Nej |
|Bell SMS/MMS-nätverksarkivering | Ja | Nej | Nej |
|Enterprise nummerarkivering | Ja | Nej | Nej |
|O2 SMS och Voice Network Archiver | Ja         | Nej | Nej |
|TELUS SMS Network Archiver | Ja | Nej | Nej |
|Verizon SMS/MMS nätverksarkivering | Ja | Nej | Nej |
|WhatsApp-arkivering | Ja | Nej | Nej |
|||||

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Arbeta med en Microsoft-partner för att arkivera data från tredje part

Ett annat alternativ för att importera och arkivera data från tredje part är att organisationen arbetar med en Microsoft-partner. Om en datatyp från tredje part inte stöds av de dataanslutningar som är tillgängliga i Microsofts efterlevnadscenter kan du samarbeta med en partner som kan tillhandahålla en anpassad koppling som konfigureras för att extrahera objekt från tredjepartsdatakällan regelbundet och sedan ansluta till Microsoft-molnet via ett API från tredje part och importera dem till Microsoft 365. Partnerkopplingen konverterar också innehållet i ett objekt från datakällan från tredje part till ett e-postmeddelande och importerar det sedan till en postlåda i Microsoft 365.

En lista med partners som du kan arbeta med och den stegvisa processen för den här metoden finns i Arbeta med en partner för att arkivera data från tredje [part i Microsoft 365.](work-with-partner-to-archive-third-party-data.md)
