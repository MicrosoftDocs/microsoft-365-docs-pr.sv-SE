---
title: Under och efter dataflytt
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.collection: SPO_Content
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: f47e3e09-b1dc-4b80-b6ea-fd6e0933407f
f1.keywords:
- NOCSH
description: Dataflyttningar är åtgärder i backend som utförs när Microsoft flyttar tjänster och associerade data för klientorganisationen till ett nytt datacenter geo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c0ea94a80de993d4d1341b8f9b19850d7149583f
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908119"
---
# <a name="during-and-after-your-data-move"></a>Under och efter dataflytt

Dataflyttningar är en backend-åtgärd med minimal påverkan för slutanvändarna. Ingen åtgärd krävs medan Microsoft flyttar varje tjänst och associerade data för klientorganisationen till ett nytt datacenter geo. Dataöverföring och validering sker i bakgrunden i förväg och påverkar användarna så lite som möjligt.
  
> [!NOTE]
> Flyttningar sker vid olika tidpunkter för varje tjänst. Resultatet blir att du ser den beskrivna nedsatta funktionen för varje tjänst vid olika tidpunkter. 
  
Titta på Microsoft 365 för att få en bekräftelse när du flyttar dig för varje Exchange Online, SharePoint Online Teams onlinechatttjänsten. Som du ser i tabellen nedan kan det ta upp till 24 månader efter registreringsperiodens slut för att slutföra grundläggande kunddata i vila flyttar till det nya datacentret.   

|**Kunder med registreringland i**|**Alla flyttningar slutförda av**|
|:-----|:-----|
|Australien, Nya Zeeland, Fiji  <br/> |1 juli 2022  <br/> |
|Japan   <br/> |1 juli 2022  <br/> |
|Indien  <br/> |1 juli 2022  <br/> |
|Kanada  <br/> |1 juli 2022  <br/> |
|Sydkorea  <br/> |1 juli 2022  <br/> |
|Storbritannien  <br/> |1 juli 2022  <br/> |
|Frankrike  <br/> |1 juli 2022  <br/> |
|Förenade Arabemiraten  <br/> |1 juli 2022  <br/> |
|Sydafrika  <br/> |1 juli 2022  <br/> |
|Schweiz, Liechtenstein  <br/> |1 juli 2022  <br/> |
|Norge  <br/> |1 november 2022  <br/> |
|Tyskland  <br/> |1 maj 2023  <br/> |
|Brasilien  <br/> |1 juni 2023  <br/> |

## <a name="exchange-online"></a>Exchange Online

Eftersom det tar tid att flytta varje användare till det nya datacentret geo för en enskild klientorganisation kommer vissa användare fortfarande att finnas i det gamla datacentret geo under flytten, medan andra kommer att finnas i det nya datacentret geo. Det innebär att vissa funktioner som innebär åtkomst till flera postlådor kanske inte fungerar helt under en period av flyttningsprocessen, som kan pågå i veckor. De här funktionerna beskrivs i följande avsnitt.
  
### <a name="open-shared-folder-in-outlook-web-access"></a>Öppna "Delad mapp" i Outlook Web Access

Vissa användare öppnar en delad e-postmapp från en annan postlåda (som användaren har läs- eller skrivbehörighet till) i Outlook Web Access med funktionen "Delad mapp". I följande tabell beskrivs hur åtkomst till delade mappar fungerar när en postlåda flyttas. Observera att användare med fullständig behörighet till en delad postlåda kan öppna postlådan med hjälp Outlook Web Access under flytten. 
  
|**Konfiguration**|**Beskrivning**|
|:-----|:-----|
|Användaren har behörighet som postlådemapp för en annan postlåda  <br/> |Potentiellt begränsat.  <br/> Om Användare A och Postlåda B inte har samma geo när klientorganisationen flyttas kan användare A inte öppna Postlåda B:s mapp i Outlook Web Access om användare A bara har behörighet till en viss mapp i Postlåda B.  <br/> Om du vill lägga till en delad mapp högerklickar du på användarnamnet i den vänstra navigeringsrutan och väljer Lägg **till delad mapp**.  <br/> |
|Användare med fullständig postlådebehörighet till en annan postlåda  <br/> |Fullt stöd.  <br/> Om Användare A har behörigheten "Fullständig åtkomst" till Postlåda B kan Användare A klicka på den delade mappen i den vänstra navigeringspanelen i Outlook Web Access för att öppna ett fönster som visar Postlåda B.  En användare kan öppna en delad postlåda Outlook Via Web Access under flytten utan att påverkas negativt. Begränsningen gäller endast delning på mappnivå i en postlåda.           |
  
## <a name="sharepoint-online"></a>SharePoint Online

När SharePoint Online flyttas flyttas även data för följande tjänster:
  
- One Drive för företag
    
- Microsoft 365 Videotjänster
    
- Office i en webbläsare
    
-  Microsoft 365 Apps för företag
    
- Visio Pro för Microsoft 365
    
När vi har flyttat klart SharePoint onlinedata kan du se några av följande effekter.
  
### <a name="microsoft-365-video-services"></a>Microsoft 365 Videotjänster

- Dataflyttning för video tar längre tid än flyttningar för resten av innehållet i SharePoint Online.
    
- När SharePoint onlineinnehåll flyttas finns det en tidsram då videor inte kan spelas upp.
    
- Vi tar bort de transkodade kopiorna från det tidigare datacentret och transkodar dem igen i det nya datacentret.
    
### <a name="search"></a>Söka

När vi flyttar dina data SharePoint Online migrerar vi dina sökindex och sökinställningar till en ny plats. Fram till dess **att vi** har slutfört flytten av dina SharePoint Online-data fortsätter vi att hjälpa dina användare från indexet på den ursprungliga platsen. På den nya platsen börjar sökningen automatiskt crawla innehållet när vi har flyttat klart dina SharePoint Online-data. Från och med nu tar vi dina användare från det migrerade indexet. Ändringar av innehåll som gjorts efter migreringen tas inte med i det migrerade indexet förrän crawlningen hämtar dem. De flesta kunder märker inte att resultaten är mindre nya direkt efter att vi har flyttat deras SharePoint Online-data, men vissa kunder kan uppleva att det minskar freshness under de första 24–48 timmarna 
  
Följande sökfunktioner påverkas:
  
- Sökresultat och sökningsresultat webbdelar: Resultaten inkluderar inte ändringar som gjorts efter migreringen förrän crawlningen hämtar dem. 
    
- Delve: Delve omfattar inte ändringar som gjorts efter migreringen förrän crawlningen hämtar dem.
    
- Popularitet och sökrapporter för webbplatsen: Antal för Excel-rapporter på den nya platsen inkluderar endast migrerade antal och antal från användningsrapporter som har körts efter att vi SharePoint Online-data. Alla antal från interimperioden går förlorade och kan inte återställas. Den här perioden är vanligtvis några dagar. Vissa kunder kan uppleva kortare eller längre förluster.
    
- Videoportal: Visa antal och statistik för videoportalen beror på statistiken för Excel-rapporter, så visa antal och statistik för videoportalen går förlorad under samma tidsperiod som för Excel-rapporter.
    
- eDiscovery: Objekt som ändrats under migreringen visas inte förrän crawlningen hämtar ändringarna.
    
- DLP (Data Loss Protection): Principer tillämpas inte på objekt som ändras förrän crawlningen hämtar ändringarna.

Som en del av migreringen ändras standardområdet och allt nytt innehåll lagras i vila i det nya standardområdet. Befintligt innehåll flyttas i bakgrunden utan att påverkas i upp till 90 dagar efter den första ändringen av dataplatsen SharePoint Online i administrationscentret.

## <a name="microsoft-teams"></a>Microsoft Teams

Förutom att Exchange Online, SharePoint Online och OneDrive för företag migrerar Microsoft Teams till det lokala datacentret.

- Teams chattmeddelanden, inklusive privata meddelanden och kanalmeddelanden.
- Teams bilder som används i chattar.

Teams lagras på SharePoint Online och Teams lagras i OneDrive för företag. Röstmeddelanden, kalender, chatthistorik och kontakter lagras i Exchange Online. I många fall är Exchange Online, SharePoint Online och OneDrive för företag redan används av kunden i det lokala datacentret geo och är även en del av Microsoft 365-migreringsprogrammet för berättigade kundländer.

## <a name="skype-for-business"></a>Skype för företag

Skype för företag är inte längre tillgängliga.  [Skype för företag Online dras tillbaka](/lifecycle/announcements/skype-for-business-online-retirement) den 31 juli 2021. Efter det är tjänsten inte längre tillgänglig. 
  
## <a name="related-topics"></a>Relaterade ämnen 
 
[Hur du begär din dataflytt](request-your-data-move.md)
    
[Vanliga frågor och svar om dataflytt](data-move-faq.yml)
  
[Nya geodatadatadata för Microsoft Dynamics CRM Online](/power-platform/admin/new-datacenter-regions)
  
[Azure-tjänster efter region](https://azure.microsoft.com/regions/)
