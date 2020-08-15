---
title: Flytta grundläggande data till nya Microsoft 365 Data Center-geos
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0a35176a-e585-4dec-a90b-36be8314667f
f1.keywords:
- NOCSH
description: Lär dig mer om nya Office 365 Data Center-geos och hur du använder alternativet data de för att begära att dina grundläggande data flyttas till en ny geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9c1c838f52627e0ff2eee5b7fdbeef7aee55b137
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694292"
---
# <a name="moving-core-data-to-new-microsoft-365-datacenter-geos"></a>Flytta grundläggande data till nya Microsoft 365 Data Center-geos

Vi fortsätter att öppna nya data Center-geos för Microsoft 365-tjänster. De här nya datacenter-geos lägga till kapacitet och beräkna resurser för att stödja vår pågående kund efter frågan och förbruknings tillväxt. Dessutom ger det nya data Center geos in-Geo data de för grundläggande kunddata. 

Grundläggande kund data är en term som refererar till en delmängd kunddata, inklusive: 
- Innehåll för Exchange Online-postlådan (e-post, kalender poster och innehållet i e-postbilagor)
- SharePoint Online-webbinnehåll och filer som lagras på webbplatsen
- Filer som laddats upp till OneDrive för företag
- Teams chatt meddelanden, inklusive privata meddelanden, kanal meddelanden och bilder som används i chattar
  
Befintliga kunder som har sina grundläggande kund uppgifter lagrade i ett befintligt Data Center-geo påverkas inte av lanseringen av ett nytt Data Center geo. Vi presenterar inga unika funktioner, funktioner och certifikat certifiering med det nya data centret geo. Som kund i någon av de två geos kommer du att uppleva samma QoS-kvalitet, prestanda och säkerhets kontroller som du gjorde förut. Vi tillhandahåller befintliga kunder i tabellen nedan ett alternativ för att begära tidiga migration av organisationens grundläggande kund uppgifter på ett sätt som vilar mot deras nya data Center.
  
|**Kunder med klient organisationens registrerings land i**|**Föregående Data Center geo**|**Nytt Data Center geo**|**Geo-tillgängligt sedan**|
|:-----|:-----|:-----|:-----|
|**Japan**| Asien/Stilla havet | Japan | December 2014 |
|**Australien, Nya Zeeland, Fidji**| Asien/Stilla havet | Australien | Mars 2015 |
|**Indien**| Asien/Stilla havet | Indien | Oktober 2015 |
|**Kanada**| Nordamerika | Kanada | Maj 2016 |
|**Storbritannien**| Europa | Storbritannien | September 2016 |
|**Sydkorea**| Asien/Stilla havet | Sydkorea | April 2017 |
|**Frankrike**| Europa | Frankrike | Mars 2018 |
|**Förenade Arabemiraten**| Europa | Förenade Arabemiraten | Juni 2019 |
|**Sydafrika**| Europa | Sydafrika | Juli 2019 |
|**Schweiz, Liechtenstein**| Europa | Schweiz | December 2019 |
|**Tyskland**| Europa | Tyskland | December 2019 |
|**Norge**| Europa | Norge | April 2020 |
  
Nya kunder eller Office 365-klient organisationer som har skapats efter tillgänglighet av den nya data Center geo kommer att ha grundläggande kund uppgifter lagrade på nya data Center-geo automatiskt.


>[!Note]
>Vi startade Tyskland Data Center i december 2019. Nya Microsoft 365-kunder med en tysk signup-adress som är kopplad till deras klient organisation kommer att ha sina grundläggande kund uppgifter lagrade i andra Tyskland. Vi planerar att bjuda in från Europa till Tyskland för tyska kunder i framtiden. Idag kan Microsoft Cloud Germany/Deutschland kunder begära migrering till Office 365-tjänster i de nya tyska Data Center-regionerna. Mer information finns i [så här väljer du för migrering från Microsoft Cloud Tyskland (Microsoft Cloud Deutschland) till Office 365-tjänster](https://aka.ms/office365germanymoveoptin) .
>
  
En fullständig lista över alla data Center geos, data Center och plats för kunddata på rest är tillgängliga som en del av de [interaktiva Data Center-kartorna](https://office.com/datamaps). 
  
## <a name="data-residency-option"></a>Alternativet de

Vi tillhandahåller ett data de alternativ till befintliga Microsoft 365-kunder som omfattas av data Center geos som visas i tabellen ovan. Med det här alternativet kan kunder med data de-krav begära tidiga migration av organisationens viktigaste kund uppgifter till det nya data centret geo.  Microsoft kommer att erbjuda en tids gräns för alla berättigade kunder som kräver tidiga migration under registrerings fönstret.  Läs om [hur du kan begära en informations flyttnings](request-your-data-move.md) sida om du vill ha mer information om fönstret för din Geo och hur du kan registrera dig i programmet.  Data flyttningar kan ta upp till 24 månader efter en begäran om att slutföras.

Vi presenterar inga unika funktioner, funktioner och certifikat certifiering med det nya data centret geo.
    
Komplexiteten, precisionen och skalan där vi måste utföra data flyttningar inom en globalt styrd och automatiserad miljö hindrar oss från att dela när data flyttas för din klient organisation eller annan klient organisation. Kunderna får en bekräftelse i meddelande Center per deltagande tjänst när dess data flyttas. 
    
Data flyttas är en backend-åtgärd som påverkar slutanvändaren minimalt. Vilka funktioner som kan påverkas visas på [under och efter data flyttnings](during-and-after-your-data-move.md) sidan. Vi följer [service nivå avtalet för Microsoft Online Services (SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) för tillgänglighet så det finns inget som kunderna behöver för att förbereda för eller för att övervaka under flytten. Meddelande om underhåll av tjänster görs vid behov. 

Data flyttas till den nya data Center geoen utan kostnad till kunden.
    
## <a name="related-topics"></a>Relaterade ämnen 
 
[Så här efterfrågar du data flytten](request-your-data-move.md)
    
[Vanliga frågor om data förflyttning](data-move-faq.md)
  
[Ny datacenter-geos för Microsoft Dynamics CRM Online](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[Azure-tjänster efter region](https://azure.microsoft.com/regions/)
