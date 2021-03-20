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
description: Skaffa IT-affischer som beskriver arkitekturmodeller, distribution och plattformsalternativ för SharePoint, Exchange, Skype för företag och Lync.
ms.openlocfilehash: 6c8aea1f6389c5007adb1800639488972483d5fb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905518"
---
# <a name="architectural-models-for-sharepoint-exchange-skype-for-business-and-lync"></a>Arkitekturmodeller för SharePoint, Exchange, Skype för företag och Lync

IT-affischerna i den här artikeln beskriver arkitekturmodellerna och distributionsalternativen för SharePoint, Exchange, Skype för företag och Lync. De innehåller också designinformation för distribution av SharePoint i Microsoft Azure.
  
Genom att använda Microsoft 365 kan du tillhandahålla välbekanta samarbets- och kommunikationstjänster via molnet. Med några få undantag är användarupplevelsen densamma oavsett om du underhåller en lokal distribution eller använder Microsoft 365. 

Den här enhetliga användarupplevelsen komplicerar beslutet för var du ska placera varje arbetsbelastning. Den tar även upp frågor:
  
- Hur väljer du en plattform för enskilda arbetsbelastningar?
    
- Är det rimligt att ha någon tjänst lokalt?
    
- I vilket scenario är en hybriddistribution lämplig?
    
- Hur passar Azure in i bilden?
    
- Vilka konfigurationer av Office-serverarbetsbelastningar stödjer Azure?
    
> [!TIP]
> De flesta affischerna i den här artikeln är tillgängliga på flera språk. De tillgängliga språken är kinesiska, engelska, franska, tyska, italienska, japanska, koreanska, portugisiska, ryska och spanska. Om du vill ladda ned en affisch på något av dessa språk väljer du Fler språk under **affischminiatyrbilden.**
  
Berätta vad du tycker! Skicka e-post till [oss cloudadopt@microsoft.com](mailto:cloudadopt@microsoft.com). 
  
Använd följande länkar för att få de affischer du behöver:
  
- **Arkitekturmodeller:** Använd dessa resurser för att hitta en idealisk plattform och konfiguration för SharePoint 2016 och Skype för företag 2015.
    
  - [Arkitekturmodeller i Microsoft SharePoint 2016](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_ArchModel)
    
  - [SharePoint Server 2016-databaser](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2016_Databases)
    
  - [Microsoft Skype för företag 2015-arkitekturmodeller](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SfB2015_ArchModel)
    
- **Plattform:** Använd de här resurserna till att fastställa en idealisk plattform och konfiguration för SharePoint 2013, Exchange 2013 och Lync 2013.
    
  - [SharePoint 2013-plattformsalternativ](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#SP2013_Options)
    
  - [Plattformsalternativ för Exchange 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Exch2013_options)
    
  - [Plattformsalternativ för Lync 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Lync2013_Options)
    
- **SharePoint Server 2013** i Azure: Använd dessa IT-affischer för att utforma och konfigurera SharePoint Server 2013-arbetsbelastningar i Azure-infrastrukturtjänster.
    
  - [Webbplatser i Azure med SharePoint Server 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#Azure_sharepoint2013)
    
  - [Designexempel: Internetwebbplatser i Azure för SharePoint 2013](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#DesignSampleInternetSites)
    
  - [SharePoint-katastrofåterställning till Azure](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md#sharepoint_recovery_Azure)
    
## <a name="architectural-models-posters"></a>Affischer för arkitekturmodeller

IT-affischerna för SharePoint 2016 och Skype för företag 2015 är ett sätt att jämföra distributionsmetoder i ett lättskrivet format. Affischerna listar alla konfigurations- eller plattformsalternativ. De ger följande information för varje alternativ:
  
- **Översikt:** En kort sammanfattning av plattformen, inklusive ett konceptuellt diagram.
    
- **Bäst för:** Vanliga scenarier som är idealiska för plattformen.
    
- **Licenskrav:** De licenser du behöver för distribution.
    
- **Arkitekturuppgifter:** De beslut du behöver fatta som arkitekt.
    
- **IT-proffs på uppgifter och** ansvarsområden: De dagliga ansvarsområden som din IT-personal behöver planera för.
    
<a name="SP2016_ArchModel"> </a>
### <a name="microsoft-sharepoint-server-2016-architectural-models"></a>Microsoft SharePoint Server 2016 arkitekturmodeller

|Objekt|Beskrivning|
|---|---|
|[![Miniatyrbild för affischen för arkitekturmodeller i SharePoint Server 2016.](../media/7d3e590c-1f3b-42cf-920d-9edac8fa3e04.png)          ](https://www.microsoft.com/download/details.aspx?id=52650) <br/> [PDF](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.pdf)  \| [Visio](https://download.microsoft.com/download/4/F/A/4FA0F94B-EE2F-41DB-A047-D9864FEF41E9/SharePoint2016ArchitecturalModels.vsdx)  \| [Fler språk](https://www.microsoft.com/download/details.aspx?id=52650)|Den här IT-affischen beskriver de lokala konfigurationer för SharePoint Online, Azure och SharePoint som beslutsfattare och lösningsarkitekter behöver känna till. <br/><br/> - **SharePoint Online (SaaS)**: Använd SharePoint via en saaS-prenumerationsmodell (programvara som en tjänst). <br/> - **SharePoint-hybrid:** Flytta Dina SharePoint-webbplatser och -appar till molnet i din egen takt. <br/> - **SharePoint i Azure (IaaS)**: Utöka din lokala miljö till Azure och distribuera SharePoint 2016-servrar där. (Den här modellen rekommenderas för miljöer för hög tillgänglighet eller katastrofåterställning och utvecklings-/testmiljöer.) <br/> - **Lokal SharePoint:** Planera, distribuera, underhålla och anpassa SharePoint-miljön i ett datacenter som du har.|
   
<a name="SP2016_Databases"> </a>
### <a name="sharepoint-server-2016-databases"></a>SharePoint Server 2016-databaser

|Objekt|Beskrivning|
|---|---|
|[![Miniatyrbild för postern SharePoint Server 2016-databaser.](../media/c53e9de7-3bf8-446d-8766-e6700c8dd8e1.png)](https://www.microsoft.com/download/details.aspx?id=55041) <br/> [PDF](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.pdf)  \| [Visio](https://download.microsoft.com/download/D/5/D/D5DC1121-8BC5-4953-834F-1B5BB03EB691/DBrefguideSPS2016_tabloid.vsdx)  \| [Fler språk](https://www.microsoft.com/download/details.aspx?id=55041)|Den här IT-affischen är en lathund för SharePoint Server 2016-databaser. Mer information visas för varje databas: <br/><br/> - Storlek <br/> - Skalningsvägledning <br/> - I/O-mönster <br/> - Krav <br/><br/>  På första sidan visas SharePoint-systemdatabaser och tjänstprogram som har flera databaser. På den andra sidan visas alla tjänstprogram som har enskilda databaser. <br/><br/>  Mer information finns i [Databastyper och beskrivningar i SharePoint Server 2016.](/SharePoint/technical-reference/database-types-and-descriptions)|
   
<a name="SfB2015_ArchModel"> </a>
### <a name="microsoft-skype-for-business-2015-architectural-models"></a>Microsoft Skype för företag 2015- arkitekturmodeller

|Objekt|Beskrivning|
|---|---|
|[![Miniatyrbild för affischen för modeller av arkitektur i Skype för företag.](../media/132288c0-6ae4-4394-88ab-b57dae367714.png)](https://www.microsoft.com/download/details.aspx?id=55022) <br/> [PDF](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)  \| [Visio](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)  \| [Fler språk](https://www.microsoft.com/download/details.aspx?id=55022)|Den här affischen beskriver Skype för företag – Online, lokal, hybrid och moln-PBX (Private Branch Exchange). Dessutom beskrivs integrering med Exchange- och SharePoint-konfigurationer som beslutsfattare och lösningsarkitekter behöver känna till. <br/><br/> Affischen är avsedd för IT-proffs som vill informera om grundläggande arkitekturmodeller som kan användas med Skype för företag – Online och Skype för företag lokalt. <br/><br/>Börja med den konfiguration som bäst passar organisationens behov och planer. Fundera över och använd andra konfigurationer efter behov. Du kanske t.ex. vill överväga integrering med Exchange och SharePoint eller en lösning som utnyttjar Microsoft Cloud PBX-erbjudandet.|
   
## <a name="platform-options-posters"></a>Affischer med plattformsalternativ

IT-affischerna för SharePoint 2013, Exchange 2013 och Lync 2013 är ett sätt att snabbt jämföra distributionsmetoderna. Alla affischer listar alla konfigurationer och plattformsalternativ. Här finns följande information för varje alternativ:
  
- **Översikt:** En kort sammanfattning av plattformen, inklusive ett konceptuellt diagram.
    
- **Bäst för:** Vanliga scenarier som är idealiska för plattformen.
    
- **Licenskrav:** De licenser du behöver för distribution.
    
- **Arkitekturuppgifter:** De beslut du behöver fatta som arkitekt.
    
- **IT-proffs på uppgifter och** ansvarsområden: De dagliga ansvarsområden som din IT-personal behöver planera för.
    
<a name="SP2013_Options"> </a>
## <a name="sharepoint-2013-platform-options"></a>SharePoint 2013-plattformsalternativ

|Objekt|Beskrivning|
|---|---|
|[![Miniatyrbild av affischen Plattformsalternativ för SharePoint 2013.](../media/SP-PlatformOptions.jpg)](https://www.microsoft.com/download/details.aspx?id=40332) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=324594)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=324593)  \| [Fler språk](https://www.microsoft.com/download/details.aspx?id=40332)|För beslutsfattare och arkitekter i företaget visar den här affischen plattformsalternativen för SharePoint 2013, SharePoint i Microsoft 365, lokal hybrid med Microsoft 365- och Azure-distributioner och distributioner endast lokalt. Den innehåller en översikt över varje arkitektur, rekommendationer, licenskrav och listor över uppgifter för arkitekt och IT-proffs för varje plattform. På affischen framhävs flera SharePoint-lösningar på Azure.|
   
<a name="Exch2013_options"> </a>
## <a name="exchange-2013-platform-options"></a>Plattformsalternativ för Exchange 2013

|Objekt|Beskrivning|
|---|---|
|[![Miniatyrbild av affischen Alternativ för Exchange-plattform.](../media/ITPro-Other-Exchange2013PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=42676) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=398740)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=398742)  \| [Fler språk](https://www.microsoft.com/download/details.aspx?id=42676)|Den här affischen beskriver plattformsalternativen för Exchange 2013 för företags beslutsfattare och arkitekter. Kunder kan välja mellan Exchange Online med Microsoft 365, Exchange-hybrid, Exchange Server lokalt och värdbaserade Exchange. Affischen beskriver varje arkitekturalternativ, inklusive de perfekta scenarierna för var och en, licenskrav och IT-ansvar.|
   
<a name="Lync2013_Options"> </a>
## <a name="lync-2013-platform-options"></a>Plattformsalternativ för Lync 2013

|Objekt|Beskrivning|
|---|---|
|[![Miniatyrbild av affischen Plattformsalternativ för Lync 2013.](../media/Lync-PlatformOptions.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41677) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkID=391837)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkID=391839)  \| [Fler språk](https://www.microsoft.com/download/details.aspx?id=41677)|Den här affischen beskriver plattformsalternativen för Lync 2013 för företags beslutsfattare och arkitekter. Kunderna kan välja mellan Lync Online med Microsoft 365, Lync-hybrid, lokal Lync Server och Lyncs värdbaserade värd. IT-affischen beskriver alla arkitekturalternativ (och vilket alternativ som passar perfekt för var och en, licenskrav och IT-ansvar).|
   
<a name="Lync2013_Options"> </a>
## <a name="sharepoint-in-azure-solutions-posters"></a>SharePoint i Azure-lösningsaffischer

IT-affischerna för SharePoint i Azure visar Azure-baserade lösningar som använder SharePoint Server 2013.
  
<a name="Azure_sharepoint2013"> </a>
### <a name="internet-sites-in-microsoft-azure-using-sharepoint-server-2013"></a>Internetwebbplatser i Microsoft Azure med SharePoint Server 2013

|Objekt|Beskrivning|
|---|---|
|[![Bild av Internetwebbplatser i Azure med hjälp av SharePoint Server 2013-affischen.](../media/MS-AZ-SPInternetSites.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41992) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392552)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392551)  \| [Fler språk](https://www.microsoft.com/download/details.aspx?id=41992)|På den här affischen beskrivs viktiga designaktiviteter och rekommenderad arkitektur för Internet-webbplatser i Azure.  <br/><br/> Mer information finns i följande artiklar:  <br/><br/> - [Webbplatser i Azure med SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Azure-arkitekturer för SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="DesignSampleInternetSites"> </a>
### <a name="internet-sites-in-azure-for-sharepoint-2013"></a>Webbplatser i Azure för SharePoint 2013

|Objekt|Beskrivning|
|---|---|
|[![Bild av internetwebbplatserna i Microsoft Azure för SharePoint Server 2013-affischen.](../media/MS-AZ-InternetSitesDesignSample.jpg)          ](https://www.microsoft.com/download/details.aspx?id=41991) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392549)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392548)  \| [Fler språk](https://www.microsoft.com/download/details.aspx?id=41991)|Använd det här designexempel som utgångspunkt för din egen arkitektur för en webbplats på Internet i Azure med SharePoint Server 2013. <br/><br/> Mer information finns i följande artiklar:  <br/><br/> - [Webbplatser i Azure med SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md) <br/> - [Azure-arkitekturer för SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
<a name="sharepoint_recovery_Azure"> </a>
### <a name="sharepoint-disaster-recovery-to-microsoft-azure"></a>SharePoint-katastrofåterställning till Microsoft Azure

|Objekt|Beskrivning|
|---|---|
|[![Bild av affischen för SharePoint-katastrofåterställningsprocessen till Azure.](../media/SP-DR-Azure.png)          ](https://www.microsoft.com/download/details.aspx?id=41993) <br/> [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555)  \| [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)  \| [Fler språk](https://www.microsoft.com/download/details.aspx?id=41993)|Den här IT-affischen visar arkitekturprinciper för en katastrofåterställningsmiljö i Azure. <br/><br/> Mer information finns i följande artiklar:  <br/><br/> - [SharePoint Server 2013-katastrofåterställning i Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md) <br/> - [Azure-arkitekturer för SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md)|
   
## <a name="see-also"></a>Se även

- [Microsoft 365-lösning och arkitekturcenter](../solutions/index.yml)
  
- [Microsoft Cloud-arkitekturmodeller](../solutions/cloud-architecture-models.md)
  
- [Testlabbguider för Microsoft 365](m365-enterprise-test-lab-guides.md)
  
- [Hybridlösningar](hybrid-solutions.md)