---
title: Microsoft 365 kompatibilitet
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Läs mer om Microsoft 365 av efterlevnadslösningar genom att använda dataanslutningar från tredje part och Microsoft Graph API:er.
ms.openlocfilehash: 1fed5ac72c7dbfa4b1be370ec03678e1beecdcd2
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651062"
---
# <a name="microsoft-365-compliance-extensibility"></a>Microsoft 365 kompatibilitet

Microsoft 365 efterlevnadslösningar hjälper organisationer att på ett smart sätt bedöma sina efterlevnadsrisker, styra och skydda känsliga data och på ett effektivt sätt uppfylla kraven i regelverken. Microsoft 365 kompatibilitet är mycket omfattande i utökningsscenarier och gör det möjligt för organisationer att anpassa, utvidga, integrera, accelerera och stödja sina efterlevnadslösningar.

Det finns två viktiga byggblock för utökningsbarhet för efterlevnad:

- **Datakopplingar**. Används för att importera och arkivera data som inte är Microsoft-data så Microsoft 365 använda skydds- och hanteringsfunktioner för data från tredje part.

- **API:er.** Ger programmeringsåtkomst till Microsoft 365 kompatibilitetsfunktioner.

## <a name="data-connectors"></a>Datakopplingar

Microsoft tillhandahåller dataanslutningar från tredje part som kan konfigureras i Microsoft 365 kompatibilitetscenter. En lista över datakopplingar som tillhandahålls av Microsoft finns i tabellen [Datakopplingar från tredje](archiving-third-party-data.md#third-party-data-connectors) part. Tabellen med datakopplingar från tredje part innehåller också en sammanfattning av de efterlevnadslösningar som du kan använda på data från tredje part efter att du har importerat och arkiverat data i Microsoft 365 samt länkar till stegvisa instruktioner för varje koppling.

Mer information om Microsoft 365 datakopplingar finns i Arkivera data från [tredje part.](archiving-third-party-data.md) Om en datatyp från tredje part inte stöds av de dataanslutningar som är tillgängliga i Microsoft 365-efterlevnadscentret kan du arbeta med en partner som kan ge dig en anpassad koppling. En lista över partner som du kan arbeta med och den stegvisa processen för den här metoden finns i Arbeta med en partner för att arkivera [data från tredje part.](work-with-partner-to-archive-third-party-data.md)

### <a name="prerequisites-for-data-connectors"></a>Förutsättningar för datakopplingar

Många av de datakopplingar som är tillgängliga i Microsoft 365 efterlevnadscenter för att importera och arkivera data från tredje part kräver att du förbereder och utför konfigurationsuppgifter i tredjepartsdatakällan. Dessa förutsättningar beskrivs i detalj för varje datakoppling från tredje part.

För dataanslutningar i Microsoft 365 efterlevnadscenter som tillhandahålls av en av Microsofts partners behöver organisationen en affärsrelation med partnern innan du kan distribuera en koppling.

Du hittar licenskraven för tredjepartsdataanslutningar i dokumentet om Microsoft 365 [för efterlevnadslicensiering.](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)

## <a name="apis"></a>API:er

Microsoft 365 api:er för efterlevnad finns tillgängliga i API:erna för Microsoft Information Protection SDK, Microsoft Graph API och API Office 365 Management Activity. Vissa API:er för efterlevnad är en del av en ny uppsättning API:er för säkerhet och efterlevnad som gör det möjligt för utvecklare för Microsoft 365-kunder, oberoende programvaruleverantörer, systemintegratorer och hanterade säkerhetstjänstleverantörer att skapa säkerhet- och efterlevnadslösningar av hög värde.

Mer information om hur du kommer åt Graph API:er finns i [Översikt över Microsoft Graph](/graph/overview).

### <a name="microsoft-information-protection-mip-sdk"></a>Microsoft Information Protection (MIP) SDK

MIP SDK visar märknings- och skyddstjänster från säkerhets- Microsoft 365 och efterlevnadscenter till tredjepartsprogram och -tjänster. Utvecklare kan använda SDK till att skapa inbyggt stöd för att använda etiketter och skydd på filer. Utvecklare kan bestämma vilka åtgärder som ska vidtas när specifika etiketter upptäcks och skäl till MIP-krypterad information.

Användningsfall för högnivå-MIP SDK omfattar:

- Ett branschprogram som tillämpar klassificeringsetiketter på filer som exporteras.

- Ett program för CAD/CAM-design som har inbyggt stöd för MIP-märkning.

- En säkerhetslösning för molnåtkomst eller dataförlustskydd som kan kryptera data med Azure Information Protection.

Mer information om MIP SDK, förutsättningar, ytterligare scenarier och exempel finns i [MIP SDK Overview](/information-protection/develop/overview).

### <a name="microsoft-graph-api-for-teams-dlp"></a>Microsoft Graph API för Teams DLP

[Funktioner för skydd mot dataförlust (DLP)](dlp-microsoft-teams.md) används ofta i stora Microsoft Teams särskilt i organisationer som har flyttats över till distansarbete. Tidigare i år meddelade [vi den offentliga förhandsversionen](https://developer.microsoft.com/graph/blogs/announcing-change-notifications-for-microsoft-teams-messages/) av API:t för ändringsmeddelande Graph Microsoft för meddelanden i Teams. Med detta API kan utvecklare skapa appar som kan lyssna på Microsoft Teams meddelanden i realtid och sedan implementera DLP-scenarier för både kunder och partner. Med Microsofts Graph kan du dessutom använda DLP-åtgärder på Teams meddelanden.

De här två API:erna utgör Microsofts Graph API för Teams DLP. Du kan komma igång genom att prova [exempelappen](https://github.com/microsoftgraph/csharp-webhook-with-resource-data). Mer information om Microsoft Teams webhooks för meddelanden finns i [dokumentationen](/graph/api/subscription-post-subscriptions).

Information om licenskraven för Teams DLP finns i [Microsoft 365 om säkerhets- och & efterlevnad.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-data-loss-prevention-for-teams)

### <a name="microsoft-graph-api-for-ediscovery-preview"></a>Microsoft Graph API för eDiscovery (förhandsversion)

Med [Advanced eDiscovery](overview-ediscovery-20.md)kan organisationer upptäcka data där de bor och hantera fler end-to-end-eDiscovery-arbetsflöden med intelligenta maskininlärning- och analysfunktioner för att minska data till relevant uppsättning – allt samtidigt som data stannar inom gränsen för säkerhet och efterlevnad i Microsoft 365.

Graph API:er för Advanced eDiscovery kan användas för att skapa och hantera ärenden, granska uppsättningar och granska uppsättningsfrågor på ett skalbart och upprepningsbart sätt. Det gör att kunder och partners kan skapa appar och arbetsflöden för att automatisera vanliga och återkommande processer som att skapa ärenden och hantera dokument och juridiska ärenden.

Den första uppsättningen Graph API:er för eDiscovery är tillgängliga i offentlig förhandsversion. Vi planerar att lägga till fler funktioner i slutet av kalenderåret. Mer information om dessa API:er och andra uppdateringar för Advanced eDiscovery finns i den här [bloggen.](https://aka.ms/Ignite2020AeDAA)

Information om licenskraven för Advanced eDiscovery och API finns i avsnittet "eDiscovery" i vägledningen för licensiering Microsoft 365 om [säkerhet och & efterlevnad.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#ediscovery)

### <a name="microsoft-graph-api-for-teams-export-preview"></a>Microsoft Graph API för Teams (förhandsversion)

EIA (Enterprise Information Archiving) för Microsoft Teams är ett viktigt scenario för våra kunder eftersom det gör att de kan lösa kraven i lagstiftningen. Utöver våra inbyggda funktioner för arkivering av innehåll i Microsoft Teams kan kunder och partner nu använda Teams Exportera API:er för att lösa scenarier med anpassade program och integrering. På Teams export-API:er finns stöd för massexport (upp till 200 förfrågningar per sekund/per app/klientorganisation) Teams och bifogade filer i meddelanden. Borttagna meddelanden kan också kommas åt via API:t i upp till 30 dagar efter att de tagits bort. Mer information om dessa Teams och hur du använder dem i programmen finns i Exportera innehåll med MICROSOFT TEAMS [Exportera API:er.](/microsoftteams/export-teams-content)

Information om licenskraven för användning av API:Teams export-API:er finns i Microsoft 365 om [licensieringsvägledning för & regelefterlevnad.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

### <a name="microsoft-graph-connector-apis-preview"></a>Microsoft Graph-API:er (förhandsversion)

Med [Microsoft Graph -anslutningar](/microsoftsearch/connectors-overview)kan organisationer indexera data från tredje part så att de visas i Microsofts sökresultat. Den här funktionen utökar de typer av innehållskällor som är sökbara i dina program Microsoft 365 produktivitetsappar och det bredare Microsoft-ekosystemet. Data från tredje part kan lagras lokalt eller i offentliga eller privata moln. Från och Advanced eDiscovery vi att aktivera utvecklarförhandsvisning av inbyggda efterlevnadsvärden för Microsoft 365 anslutna appar. Det gör det möjligt att efterlevnad för appar som integrerar i Microsoft 365-ekosystemet för att ge användarna möjlighet till smidig efterlevnad. Mer information om hur du använder Microsoft Graph Connector-API:er i programvyn finns i Skapa, uppdatera och ta bort anslutningar i [Microsoft Graph.](/graph/search-index-manage-connections)

