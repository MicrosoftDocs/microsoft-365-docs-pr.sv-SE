---
title: Arkitekturmodeller för SharePoint, Exchange, Skype för företag och Lync
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/16/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
ms.assetid: 5b49fa68-f8f2-4705-af96-5f5475e8539a
search.appverid:
- MET150
description: Få IT-affischer som beskriver alternativen för arkitektur, distribution och plattform för SharePoint, Exchange, Skype för företag och Lync.
ms.openlocfilehash: 6d5cda89fb67f5c41dcf161abe7258c4600ee8ce
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919826"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>Arkitekturmodeller för SharePoint, Exchange, Skype för företag och Lync

IT-förhands granskning i den här artikeln beskriver arkitektur-och distributions alternativ för SharePoint, Exchange, Skype för företag och Lync. De ger också design information för att distribuera SharePoint i Microsoft Azure.
  
Genom att använda Microsoft 365 kan du tillhandahålla välbekanta samarbets-och kommunikations tjänster via molnet. Med några få undantag är användar upplevelsen detsamma likadan oavsett om du håller på att underhålla en lokal distribution eller använder Microsoft 365. 

Den här enhetliga användar upplevelsen är ett problem med beslutet att placera varje arbets belastning. Det ger också frågor:
  
- Hur väljer jag en plattform för enskilda arbets belastningar?
    
- Är det lämpligt att förvara all lokal tjänst?
    
- I vilket fall är en hybrid distribution lämplig?
    
- Hur passar Azure in i bilden?
    
- Vilka konfigurationer av arbets belastning för Office Server fungerar med Azure?
    
> [!TIP]
> De flesta förhands granskningar i den här artikeln är tillgängliga på flera språk. Tillgängliga språk inkluderar kinesiska, engelska, franska, tyska, italienska, japanska, koreanska, portugisiska, ryska och spanska. Om du vill ladda ned en affisch på något av de här språken väljer du **fler språk** under miniatyr bilden.
  
Låt oss veta vad du tycker! Skicka e-post till oss på [cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com). 
  
Använd följande länkar för att få de affischer du behöver:
  
- **Arkitektur modeller** : Använd de här resurserna för att fastställa din ideal plattform och konfiguration för SharePoint 2016 och Skype för företag 2015.
    
  - [Microsoft SharePoint 2016-arkitektur modeller](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [SharePoint Server 2016-databaser](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Arkitektur modeller för Microsoft Skype för företag 2015](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **Plattform** : Använd de här resurserna för att fastställa din ideal plattform och konfiguration för SharePoint 2013, Exchange 2013 och Lync 2013.
    
  - [SharePoint 2013-plattforms alternativ](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Alternativ för Exchange 2013-plattform](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Lync 2013-plattforms alternativ](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **SharePoint server 2013 i Azure** : Använd de här IT-förhands granskningarna för att designa och konfigurera SharePoint Server 2013-arbets belastning i Azure Infrastructure Services.
    
  - [Internet webbplatser i Azure med SharePoint Server 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [Design exempel: Internet-webbplatser i Azure för SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [SharePoint-återställning till Azure](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>Affisch modeller

IT-affischen för SharePoint 2016 och Skype för företag 2015 är ett sätt att jämföra distributions metoder i ett lättanvänt format. Affischerna visar alla konfigurations-eller plattforms alternativ. De innehåller följande information för varje alternativ:
  
- **Översikt** : en kort sammanfattning av plattformen, inklusive ett konceptuellt diagram.
    
- **Bäst för** : vanliga scenarier som passar plattformen.
    
- **Licens krav** : de licenser du behöver för distribution.
    
- **Arkitektur uppgifter** : de beslut som du måste skapa som arkitekt.
    
- **IT-uppgifter eller ansvars områden** : de dagliga ansvars områden som IT-personalen måste planera för.
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-server-2016-architectural-models"></a>Microsoft SharePoint Server 2016-arkitektur modeller

|Objekt|Beskrivning|
|---|---|
|[![Miniatyr för SharePoint Server 2016-arkitekturen för affischer.](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf)  \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx)  \| [Fler språk](https://www.microsoft.com/download/details.aspx?id=52650)|Det här är en affisch som beskriver de lokala konfigurationerna för SharePoint Online, Azure och SharePoint som affärs besluts fattare och lösnings arkitekter måste känna till. <br/><br/> - **SharePoint Online (SaaS)** : konsumera SharePoint via en program vara som tjänst för abonnemang (SaaS). <br/> - **SharePoint-hybrid** : flytta dina SharePoint-webbplatser och-appar till molnet i din egen takt. <br/> - **SharePoint i Azure (IaaS)** : utöka din lokala miljö till Azure och distribuera SharePoint 2016-servrar där. (Den här modellen rekommenderas för hög tillgänglighet eller katastrof återställning och utvecklings miljöer.) <br/> - **SharePoint lokalt** : planera, distribuera, underhålla och anpassa din SharePoint-miljö i ett Data Center som du upprätthåller.|
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>SharePoint Server 2016-databaser

|Objekt|Beskrivning|
|---|---|
|[![Miniatyr för SharePoint Server 2016-databaserna för affisch.](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf)  \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx)  \| [Fler språk](https://www.microsoft.com/download/details.aspx?id=55041)|Denna IT-affisch är en snabb referens för SharePoint Server 2016-databaser. Du kommer att se information för varje databas: <br/><br/> -Storlek <br/> -Skalnings vägledning <br/> -I/O-mönster <br/> -Krav <br/><br/>  Den första sidan visar de SharePoint-systemdatabaser och tjänst program som har flera databaser. På den andra sidan visas alla tjänst program som har enskilda databaser. <br/><br/>  Mer information finns i [databas typer och beskrivningar i SharePoint Server 2016](https://docs.microsoft.com/SharePoint/technical-reference/database-types-and-descriptions).|
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Arkitektur modeller för Microsoft Skype för företag 2015

|Objekt|Beskrivning|
|---|---|
|[![Miniatyr bild för arkitektur modellerna för Skype för företag – affisch.](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)  \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)  \| [Fler språk](https://www.microsoft.com/download/details.aspx?id=55022)|Denna affisch beskriver Skype för företag – Online, lokal-, hybrid-och moln privat gren Exchange (PBX). Den beskriver också integrering med Exchange-och SharePoint-konfigurationer som företags besluts fattare och lösnings arkitekter måste känna till. <br/><br/> Affischen är avsedd för IT-tekniker att få kännedom om de grundläggande arkitektur modellerna genom vilka Skype för företag – Online och lokal Skype för företag kan utnyttjas. <br/><br/>Börja med den konfiguration som bäst passar organisationens behov och abonnemang. Överväg att använda andra konfigurationer efter behov. Du kanske till exempel vill integrera med Exchange och SharePoint eller en lösning som utnyttjar Microsofts Cloud PBX-erbjudande.|
   
## <a name="platform-options-posters"></a>Affischer för plattforms alternativ

IT-affischer för SharePoint 2013, Exchange 2013 och Lync 2013 ger en överblick över distributions metoderna. Varje affisch visar alla konfigurationer eller plattforms alternativ. Den innehåller följande information för varje alternativ:
  
- **Översikt** : en kort sammanfattning av plattformen, inklusive ett konceptuellt diagram.
    
- **Bäst för** : vanliga scenarier som passar plattformen.
    
- **Licens krav** : de licenser du behöver för distribution.
    
- **Arkitektur uppgifter** : de beslut som du måste skapa som arkitekt.
    
- **IT-uppgifter eller ansvars områden** : de dagliga ansvars områden som IT-personalen måste planera för.
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>SharePoint 2013-plattforms alternativ

|Objekt|Beskrivning|
|---|---|
|[![Miniatyr bild av SharePoint 2013-plattforms alternativ för affisch.](../media/SP-PlatformOptions.jpg)](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593)  \| [Fler språk](https://www.microsoft.com/download/details.aspx?id=40332)|För företags besluts fattare och arkitekter visar den här affischen plattforms alternativen för SharePoint 2013, SharePoint i Microsoft 365, lokal hybrid med Microsoft 365, Azure och lokala distributioner. Den innehåller en översikt över varje arkitektur, rekommendationer, licens krav och listor över arkitekt-och IT-uppgifter för varje plattform. Affischen visar flera SharePoint-lösningar på Azure.|
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Alternativ för Exchange 2013-plattform

|Objekt|Beskrivning|
|---|---|
|[![Miniatyr bild av alternativen för att överföra Exchange-plattformar.](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742)  \| [Fler språk](https://www.microsoft.com/download/details.aspx?id=42676)|För företags besluts fattare och arkitekter beskriver den här affischen plattforms alternativen för Exchange 2013. Kunderna kan välja mellan Exchange Online med Microsoft 365, hybrid Exchange, Exchange Server lokalt och värdbaserad Exchange. Affischen visar alla olika arkitektur alternativ, inklusive de ideala scenarierna för var och en av licens kraven och IT-ansvar.|
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Lync 2013-plattforms alternativ

|Objekt|Beskrivning|
|---|---|
|[![Miniatyr bild av Lync 2013 Platform alternativ affisch.](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839)  \| [Fler språk](https://www.microsoft.com/download/details.aspx?id=41677)|För företags besluts fattare och arkitekter beskriver den här affischen plattforms alternativen för Lync 2013. Kunderna kan välja från Lync Online med Microsoft 365, hybrid Lync, Lync Server lokalt och värdbaserade Lync. IT-affischen visar alla arkitektur alternativ, inklusive de ideala scenarierna för var och en av licens kraven och IT-ansvar.|
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>SharePoint i en Azure Solutions-affisch

IT-affisch för SharePoint i Azure show Azure-baserade lösningar som använder SharePoint Server 2013.
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>Internet-webbplatser i Microsoft Azure med SharePoint Server 2013

|Objekt|Beskrivning|
|---|---|
|[![Bild på Internet webbplatser i Azure med SharePoint Server 2013-affisch.](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)  \| [Fler språk](https://www.microsoft.com/download/details.aspx?id=41992)|Denna affisch som beskriver viktiga design aktiviteter och Rekommenderad arkitektur för Internet-webbplatser i Azure.  <br/><br/> Mer information finns i följande artiklar:  <br/><br/> - [Internet webbplatser i Azure med SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Azure-arkitekturer för SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="DesignSampleInternetSites"> </a>
### <a name="internet-sites-in-azure-for-sharepoint-2013"></a>Internet webbplatser i Azure för SharePoint 2013

|Objekt|Beskrivning|
|---|---|
|[![Bild på Internet webbplatserna i Microsoft Azure för SharePoint Server 2013 affisch.](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)  \| [Fler språk](https://www.microsoft.com/download/details.aspx?id=41991)|Använd det här design exemplet som utgångs punkt för din egen arkitektur på en Internet-webbplats i Azure med SharePoint Server 2013. <br/><br/> Mer information finns i följande artiklar:  <br/><br/> - [Internet webbplatser i Azure med SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Azure-arkitekturer för SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>SharePoint-återställning till Microsoft Azure

|Objekt|Beskrivning|
|---|---|
|[![Bild av affischen för återställnings processen för SharePoint i Azure.](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)  \| [Fler språk](https://www.microsoft.com/download/details.aspx?id=41993)|Denna IT-affisch visar arkitektur principer för en katastrof återställnings miljö i Azure. <br/><br/> Mer information finns i följande artiklar:  <br/><br/> - [SharePoint Server 2013 katastrof återställning i Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [Azure-arkitekturer för SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
## <a name="see-also"></a>Se även

- [Microsoft 365-center för lösningar och arkitektur](../solutions/solution-architecture-center.md)
  
- [Microsoft Cloud-arkitekturmodeller](../solutions/cloud-architecture-models.md)
  
- [Microsoft 365 test labb guider](m365-enterprise-test-lab-guides.md)
  
- [Hybridlösningar](hybrid-solutions.md)

