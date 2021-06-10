---
title: Introduktion till prestandajustering för SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: I den här artikeln förklaras vilka specifika aspekter du måste tänka på när du skapar sidor för bästa prestanda i SharePoint Online.
ms.openlocfilehash: 6f40243c9d6a1657b6716a071288f5b4fb018164
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909744"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a>Introduktion till prestandajustering för SharePoint Online

I den här artikeln förklaras vilka specifika aspekter du måste tänka på när du skapar sidor för bästa prestanda i SharePoint Online.
     
## <a name="sharepoint-online-metrics"></a>SharePoint Onlinemått

Följande breda mått för SharePoint Online ger verkliga data om prestanda:
  
- Hur snabbt sidor läses in
    
- Hur många tur och returresor som krävs per sida
    
- Problem med tjänsten
    
- Andra saker som kan medföra försämrad prestanda
    
### <a name="conclusions-reached-because-of-the-data"></a>Beslut som har uppnåtts på grund av data

Data talar om för oss:
  
- De flesta sidor fungerar bra på SharePoint Online.
    
- Det går mycket snabbt att läsa in sidor som inte är anpassade.
    
- OneDrive för företag, gruppwebbplatser och systemsidor, till exempel _layouts och så vidare, är snabba att läsa in.
    
- Den långsammaste procenten av alla SharePoint tar mer än 5 000 millisekunder att läsa in.
    
Ett enkelt prestandatest du kan använda är att mäta prestandan genom att jämföra inläsningstiden för din egen portal med inläsningstiden för startsidan OneDrive för företag eftersom den inte har så många anpassade funktioner. Supporten ber dig gärna att göra det första steget när du felsöker prestandaproblem i nätverket.
  
## <a name="use-a-standard-user-account-when-checking-performance"></a>Använda ett vanligt användarkonto när du kontrollerar prestanda

En administratör för webbplatssamlingen, webbplatsägare, redaktör eller deltagare tillhör ytterligare säkerhetsgrupper, har ytterligare behörigheter och har därför ytterligare element som läses SharePoint in på en sida.
  
Det här gäller SharePoint lokalt och i SharePoint Online, men i ett lokalt scenario kommer skillnaderna inte att vara lika lätta att se som i SharePoint Online.
  
Om du vill utvärdera hur en sida kommer att se ut för användare bör du använda ett standardanvändarkonto för att undvika inläsning av redigeringskontroller och extra trafik relaterad till säkerhetsgrupper.
  
## <a name="connection-categories-for-performance-tuning"></a>Anslutningskategorier för prestandajustering

Du kan kategorisera anslutningarna mellan servern och användaren i tre huvudkomponenter. Tänk på dessa när du SharePoint onlinesidor och vill ha insyn i inläsningstider.
  
- **Server** Servrarna som Microsoft är värd för i datacenter.
    
- **Nätverk** Microsofts nätverk, Internet och ditt lokala nätverk mellan datacentret och dina användare.
    
- **Webbläsare** Här läses sidan in.
    
I de här tre anslutningarna finns vanligtvis fem orsaker till 95 % av alla långsamma sidor. Var och en av de här orsakerna tas upp i den här artikeln:
  
- Navigeringsproblem
    
- Innehåll som återställs
    
- Stora filer
    
- Många förfrågningar till servern
    
- Bearbetning av webbdel
    
### <a name="server-connection"></a>Serveranslutning

Många av de problem som påverkar prestandan SharePoint lokalt gäller även för SharePoint Online.
  
Som förväntat har du mycket större kontroll över hur servrar fungerar lokalt med SharePoint. Med SharePoint online är saker lite annorlunda. Ju mer arbete du får en server att göra, desto längre tid tar det att återge en sida. Med SharePoint är den största boven i det här avseendet komplexa sidor med flera webbdelar.
  
SharePoint Server lokalt
  
![Skärmbild av lokal server](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
SharePoint Online
  
![Skärmbild av server online](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
Med SharePoint Online kan vissa sidförfrågningar faktiskt anropa flera servrar. Du kan få en matris med förfrågningar mellan servrar för en enskild begäran. Dessa interaktioner kostar mycket ur ett inläsningsperspektiv och gör att sidor läses in långsamt.
  
Här är några exempel på sådana interaktioner mellan servrar:
  
- Webb till SQL servrar
    
- Webb till programservrar
    
En annan sak som kan göra att serverinteraktioner tar lång tid är cachemissar. Till skillnad från lokala SharePoint finns det en liten möjlighet att du träffar samma server för en sida du besökt tidigare. Det här gör cachelagringen av objekt inaktuell.
  
### <a name="network-connection"></a>Nätverksanslutning

Med en lokal SharePoint som inte använder ett WAN kan du använda en snabb anslutning mellan datacentret och slutanvändarna. I allmänhet är det enkelt att hantera saker ur ett nätverksperspektiv.
  
Med SharePoint Online finns det några fler faktorer att tänka på: till exempel:
  
- Microsoft-nätverket
    
- The Internet
    
- Internetleverantören
    
Oavsett vilken version av SharePoint (och vilket nätverk) du använder är saker som vanligtvis gör att nätverket är upptaget:
  
- Stora nyttolaster
    
- Många filer
    
- Stora fysiska avstånd till servern
    
En funktion som du kan dra nytta av SharePoint Online är Microsoft-CDN (Content Delivery Network). En CDN är i princip en samling servrar som distribuerats över flera datacenter. Med en CDN kan innehållet på sidor lagras på en server nära klienten även om klienten är långt från den ursprungliga SharePoint servern. Microsoft kommer att använda detta mer i framtiden för att lagra lokala instanser av sidor som inte kan anpassas, till exempel startsidan för SharePoint Online-administratör. Mer information om CDN finns i [Nätverk för innehållsleverans.](content-delivery-networks.md)
  
En sak som du måste vara medveten om men kanske inte kan göra så mycket åt är Internetleverantörens anslutningshastighet. Ett enkelt testverktyg för hastighet kan ge information om anslutningshastigheten.
  
### <a name="browser-connection"></a>Webbläsaranslutning

Det finns några faktorer att tänka på när det gäller webbläsare ur ett prestandaperspektiv.
  
Att besöka komplexa sidor kommer att påverka prestandan. De flesta webbläsare bara har en liten cache (cirka 90 MB), medan en genomsnittlig webbsida normalt är cirka 1,6 MB. Det tar inte lång tid att använda upp den.
  
Bandbredd kan också vara ett problem. Om en användare till exempel visar videoklipp i en annan session kommer detta att påverka prestandan för SharePoint sidan. Du kan inte hindra användare från att direktuppspela media, men du kan styra hur en sida läses in för användarna.
  
Läs följande artiklar för olika anpassningsmetoder SharePoint onlinesidor och andra metodtips som hjälper dig att uppnå optimala prestanda.
  
- [Navigeringsalternativ för SharePoint Online](navigation-options-for-sharepoint-online.md)
    
- [Använda verktyget Siddiagnostik för SharePoint Online](page-diagnostics-for-spo.md)
    
- [Bildoptimering för SharePoint Online](image-optimization-for-sharepoint-online.md)
    
- [Fördröja inläsning av bilder och JavaScript i SharePoint Online](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [Förgrening och sammanslagning i SharePoint Online](minification-and-bundling-in-sharepoint-online.md)
    
- [Använda Office 365 Content Delivery Network (CDN) med SharePoint Online](use-microsoft-365-cdn-with-spo.md)
    
- [Använda webbdel för innehållssökning i stället för webbdel för innehållsfråga för att förbättra prestanda SharePoint Online](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [Kapacitetsplanering och belastningstestning av SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [Diagnostisering av prestandaproblem med SharePoint Online](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [Använda objektcachen med SharePoint Online](using-the-object-cache-with-sharepoint-online.md)
    
- [Så här gör du för att: Undvika begränsningar och blockeringar SharePoint Online](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)
