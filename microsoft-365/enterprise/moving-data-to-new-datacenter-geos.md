---
title: Flytta basdata till nya Microsoft 365 geodatadata
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
description: Läs mer om Office 365 datacenter geos och hur du använder alternativet data som lagras för att begära att dina kärndata flyttas till en ny geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 60e04525843e8e7557eab2f804680d6d5dddd4d8
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904098"
---
# <a name="moving-core-data-to-new-microsoft-365-datacenter-geos"></a>Flytta basdata till nya Microsoft 365 geodatadata

Vi fortsätter att öppna nya datacenter geos för Microsoft 365 tjänster. Dessa nya datacenter geos lägger till kapacitet och beräknar resurser för att stödja vår pågående kundbehov och användningstillväxt. Det nya datacentret geos erbjuder dessutom geodata som används för basdata. 

Baskunddata är en term som refererar till en delmängd kunddata, inklusive: 
- Exchange Online innehållet i postlådan (brödtext, kalenderposter och innehållet i e-postbilagor)
- SharePoint Onlinewebbplatsinnehåll och filer som lagrats på webbplatsen
- Filer som laddats upp till OneDrive för företag
- Teams chattmeddelanden, inklusive privata meddelanden, kanalmeddelanden och bilder som används i chattar
  
Befintliga kunder som har sina grundläggande kunddata lagrade i ett befintligt datacenter geo påverkas inte av lanseringen av ett nytt datacenter geo. Vi introducerar inga unika funktioner, funktioner eller efterlevnadscertifieringar med det nya datacentret geo. Som kund i någon av dessa två geos får du samma tjänstekvalitet, prestanda- och säkerhetskontroller som du gjorde tidigare. Vi erbjuder befintliga kunder som visas i tabellen under ett alternativ för att begära tidig migrering av organisationens kärndata i vila till det nya datacentret.
  
|**Kunder med klientorganisationsland i**|**Tidigare geodatadata**|**Nytt datacenter geo**|**Geo tillgängligt sedan**|
|:-----|:-----|:-----|:-----|
|**Japan**| Asien/Stillahavsområdet | Japan  | December 2014 |
|**Australien, Nya Zeeland, Fiji**| Asien/Stillahavsområdet | Australien | Mars 2015 |
|**Indien**| Asien/Stillahavsområdet | Indien | Oktober 2015 |
|**Kanada**| USA | Kanada | Maj 2016 |
|**Storbritannien**| EU | Storbritannien | September 2016 |
|**Sydkorea**| Asien/Stillahavsområdet | Sydkorea | April 2017 |
|**Frankrike**| EU | Frankrike | Mars 2018 |
|**Förenade Arabemiraten**| EU | Förenade Arabemiraten | Juni 2019 |
|**Sydafrika**| EU | Sydafrika | Juli 2019 |
|**Schweiz, Liechtenstein**| EU | Schweiz | December 2019 |
|**Tyskland**| EU | Tyskland | December 2019 |
|**Norge**| EU | Norge | April 2020 |
|**Brasilien**| Amerika | Brasilien | November 2020 |

Från och med den 1 oktober 2020 är kunder med en Office 365 Education-prenumeration som ingår i klientorganisationen inte berättigade till migrering.

En fullständig lista över alla datacenter geos, datacenter och platsen för kunddata i vila är tillgänglig som en del av interaktiva [datacenterkartor.](https://office.com/datamaps) 
  
## <a name="data-residency-option"></a>Alternativet Datahem

Vi tillhandahåller ett alternativ för datalagring för berättigade Microsoft 365 som täcks av de datacenter geos som anges i tabellen ovan. Med det här alternativet kan berättigade kunder med datalagringskrav begära migrering av organisationens grundläggande kunddata i vila till det nya datacentret.  Microsoft kommer att erbjuda en tidsgräns för alla berättigade kunder som begär migrering under registreringsfönstret.  Gå till [sidan Begära dataflyttning](request-your-data-move.md) för mer information om fönstret för öppen registrering för geodatadatacentret och stegen för att registrera dig i programmet.  Dataflyttningar kan ta upp till 24 månader efter att begäran har avslutats.

Vi introducerar inga unika funktioner, funktioner eller efterlevnadscertifieringar med det nya datacentret geo.
    
Den komplexitet, precision och skala som vi behöver för att utföra dataflyttningar i en globalt drivs och automatiserad miljö hindrar oss från att dela när en dataflyttning förväntas slutföras för din klientorganisation eller någon annan enskild klientorganisation. Kunder får en bekräftelse i meddelandecentret per deltagande tjänst när dataflyttningen är klar. 
    
Dataflyttningar är en tjänsteåtgärd i backend med minimal påverkan för slutanvändarna. Funktioner som kan påverkas visas på sidan [Under och efter dataflyttningen.](during-and-after-your-data-move.md) Vi följer tjänstnivåavtalet [för Microsoft Online Services (SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) för tillgänglighet så att det inte finns något som kunderna behöver förbereda sig för eller övervaka under flytten. Meddelande om eventuellt underhåll av tjänsten görs om det behövs. 

Dataflyttningar till det nya datacentrets geo slutförs utan extra kostnad för kunden.
    
## <a name="related-topics"></a>Relaterade ämnen 
 
[Hur du begär din dataflytt](request-your-data-move.md)
    
[Vanliga frågor och svar om dataflytt](data-move-faq.md)
  
[Nya geodatadatadata för Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions)
  
[Azure-tjänster efter region](https://azure.microsoft.com/regions/)

[Teams av ett Microsoft 365 med flera geoaktiverade innehavare](/microsoftteams/teams-experience-o365odb-spo-multi-geo)
