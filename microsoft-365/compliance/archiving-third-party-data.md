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
ms.openlocfilehash: a51b298b934431a1be8a416dac1f831ddaca5ffe
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861209"
---
# <a name="archive-third-party-data"></a>Arkivera data från tredje part

Microsoft 365 kan administratörer använda datakopplingar för att importera och arkivera data från tredje part från plattformar för sociala medier, snabbmeddelanden och plattformar för dokumentsamarbete till postlådor i Microsoft 365 organisation. En av de största fördelarna med att använda datakopplingar för att importera och arkivera data från tredje part i Microsoft 365 är att du kan använda olika Microsoft 365-efterlevnadslösningar för dem när de har importerats. På så sätt kan du säkerställa att organisationens data som inte är Microsoft följer föreskrifter och standarder som påverkar organisationen.

## <a name="third-party-data-connectors"></a>Datakopplingar för tredje part

I följande tabell visas de datakopplingar från tredje part som är tillgängliga Microsoft 365 kompatibilitetscentret. Tabellen sammanfattar även de efterlevnadslösningar som du kan använda på data från tredje part efter att du importerat och arkiverat dem i Microsoft 365. I nästa [avsnitt finns](#overview-of-compliance-solutions-that-support-third-party-data) en mer detaljerad beskrivning av varje efterlevnadslösning och hur den kan vara till nytta för data från tredje part.

> [!TIP]
> Klicka på länken i **kolumnen med data från** tredje part om du vill ha stegvisa anvisningar för hur du skapar en koppling för den datatypen.

|Data från tredje part  |Bevarande av juridiska skäl|eDiscovery  |Inställningar för bevarande  |Hantering av arkivhandlingar  |Kommunikationsefterlevnad  |Hantering av insiderrisk  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Android <sup>1</sup>](archive-android-archiver-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[AT&T Network <sup>1</sup>](archive-att-network-archiver-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Bell Network <sup>1</sup>](archive-bell-network-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Bloomberg-meddelande](archive-bloomberg-message-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[CellTrust <sup>2</sup>](archive-celltrust-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Cisco Jabber på MS SQL <sup>2</sup>](archive-ciscojabberonmssql-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Cisco Jabber på Oracle <sup>2</sup>](archive-ciscojabberonoracle-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Cisco Jabber på PostgreSQL <sup>2</sup>](archive-ciscojabberonpostgresql-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[EML <sup>2</sup>](archive-eml-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[Företagsnummer <sup>1</sup>](archive-enterprise-number-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[FX Anslut <sup>2</sup>](archive-fxconnect-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Personalavdelningen](import-hr-data.md) ||||||![Bockmarkering](../media/checkmark.png)
|[ICE-chatt](archive-icechat-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Instant Bloomberg](archive-instant-bloomberg-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Jive <sup>2</sup>](archive-jive-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[LinkedIn](archive-linkedin-data.md)   |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[MS SQL Database <sup>2</sup>](archive-mssqldatabaseimporter-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[O2 Network <sup>1</sup>](archive-o2-network-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Fysisk aktivitet](import-physical-badging-data.md) ||||||![Bockmarkering](../media/checkmark.png)|
|[Pivot <sup>2</sup>](archive-pivot-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Redtail Speak <sup>2</sup>](archive-redtailspeak-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Reuters Dealing <sup>2</sup>](archive-reutersdealing-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Reuters Eikon <sup>2</sup>](archive-reuterseikon-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Reuters FX <sup>2</sup>](archive-reutersfx-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Salesforce Chatter <sup>2</sup>](archive-salesforcechatter-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[ServiceNow <sup>2</sup>](archive-servicenow-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[Slack eDiscovery <sup>2</sup>](archive-slack-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Hann <sup>2</sup>](archive-symphony-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[TELUS Network <sup>1</sup>](archive-telus-network-data.md)    |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Textavgränsad <sup>2</sup>](archive-text-delimited-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[Verizon Network <sup>1</sup>](archive-verizon-network-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Webex Teams <sup>2</sup>](archive-webexteams-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Webbsidor <sup>2</sup>](archive-webpagecapture-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[WeChat <sup>1</sup>](archive-wechat-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[WhatsApp <sup>1</sup>](archive-whatsapp-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Arbetsplats från Facebook <sup>2</sup>](archive-workplacefromfacebook-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[XIP <sup>2</sup>](archive-xip-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[XSLT/XML <sup>2</sup>](archive-xslt-xml-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|||
|[Yieldbroker <sup>2</sup>](archive-yieldbroker-data.md)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
|[Zooma möten <sup>2</sup>](archive-zoommeetings-data.md)     |![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)|![Bockmarkering](../media/checkmark.png)||
||||||||

> [!NOTE]
> <sup>1</sup> Data connector provided by TeleMessage. Innan du kan arkivera data i Microsoft 365 måste du arbeta med TeleMessage för att konfigurera deras arkiveringstjänst för din organisation. Mer information finns i avsnittet som krävs i de stegvisa instruktionerna för den här datatypen. TeleMessage-dataanslutningar är också tillgängliga GCC miljöer i Microsoft 365 för myndigheter i USA. Mer information finns i avsnittet [Dataanslutningar i molnet för myndigheter i USA i](#data-connectors-in-the-us-government-cloud) den här artikeln. <br/><br/><sup>2</sup> Datakoppling tillhandahålls av Veritas. Innan du kan arkivera data i Microsoft 365 måste du arbeta med Veritas för att konfigurera deras arkiveringstjänst för organisationen. Mer information finns i avsnittet som krävs i de stegvisa instruktionerna för den här datatypen.

Data från tredje part som listas i föregående tabell (utom hr-data och fysiska badgingdata) importeras till användarpostlådor. Motsvarande efterlevnadslösningar som stöder data från tredje part tillämpas på den användarpostlåda där data lagras.

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
|AT&T SMS/MMS Network Archiver | Ja | Nej | Nej |
|Bell SMS/MMS Network Archiver | Ja | Nej | Nej |
|Enterprise Number Archiver | Ja | Nej | Nej |
|O2 SMS och Voice Network Archiver | Ja         | Nej | Nej |
|TELUS SMS Network Archiver | Ja | Nej | Nej |
|Verizon SMS/MMS Network Archiver | Ja | Nej | Nej |
|WeChat Archiver | Ja | Nej | Nej |
|WhatsApp Archiver | Ja | Nej | Nej |
|||||

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Arbeta med en Microsoft-partner för att arkivera data från tredje part

Ett annat alternativ för att importera och arkivera data från tredje part är att organisationen arbetar med en Microsoft-partner. Om en datatyp från tredje part inte stöds av de dataanslutningar som är tillgängliga i Microsofts efterlevnadscenter kan du samarbeta med en partner som kan tillhandahålla en anpassad koppling som konfigureras för att extrahera objekt från tredjepartsdatakällan regelbundet och sedan ansluta till Microsoft-molnet via ett API från tredje part och importera dem till Microsoft 365. Partnerkopplingen konverterar också innehållet i ett objekt från datakällan från tredje part till ett e-postmeddelande och importerar det sedan till en postlåda i Microsoft 365.

En lista med partners som du kan arbeta med och den stegvisa processen för den här metoden finns i Arbeta med en partner för att arkivera data från tredje [part i Microsoft 365.](work-with-partner-to-archive-third-party-data.md)
