---
title: SharePoint 2007 – Migreringsalternativ att överväga
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPS150
- OSU140
- SPO160
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: 66325a43-5816-4f8e-81ba-c11b71345b7c
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: Den här artikeln innehåller information för användare som använder SharePoint Server 2007 som hjälper dem att planera uppgraderingen.
ms.openlocfilehash: 38c4713b7dfb705c99d970c5f68a37b031c951a5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924886"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>SharePoint 2007 – Migreringsalternativ att överväga

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Supporten för Microsoft SharePoint 2007 och SharePoint Server 2007 har nu gått ut. Det är dags att uppgradera! Den här artikeln innehåller information om migreringsalternativen.
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>Vanliga uppgraderingsstrategier för SharePoint

Det finns flera metoder för att uppgradera en SharePoint Server-miljö. Här är några exempel på uppgraderingsmetoder om du har en Microsoft Office SharePoint Server 2007-servergrupp:
  
- Databas bifoga
    
- Sida vid sida-uppgradering
    
- Uppgradering på plats
    
- Hybriduppgradering (på plats med frikopplade databaser/separat databaskopplad)
    
- SharePoint-hybrider (ansluta online till lokal SharePoint)
    
- Flytta data manuellt mellan webbplatssamlingar eller bibliotek
    
- FastTrack-guideuppgradering till Microsoft 365[(distributionsrådgivaren för SharePoint Online)](https://aka.ms/spoguidance)
    
- API-migrering till SharePoint Online (SPO) i Microsoft 365
    
Vad passar bäst för dig?
  
När du ska uppgradera är det viktigt att du vet vad servergruppen gör och används till. Det sätt som andra använder SharePoint-servergruppen hjälper dig att välja bland alternativen.
  
> [!TIP]
> Microsoft Office SharePoint Server 2007 har också en stegvis uppgradering som inte tas upp här. En lista med stegspecifika uppgraderingsartiklar finns i Översikt över slutet på supporten för [SharePoint Server 2007.](sharepoint-2007-end-of-support.md) 
  
Kom ihåg att kontrollera [produktlivscykeln](https://support.microsoft.com/lifecycle/search) och systemkraven för den version av SharePoint som du uppgraderar till. Det här är så att du ska veta när nästa uppgradering blir nödvändig (om du till exempel stannar vid en äldre produkt som SharePoint Server 2010 för att planera ytterligare uppgraderingar måste du känna till supportdatumet) och att du vet att du har den maskinvara som krävs för planen. 
  
Om du planerar att lägga över vissa eller alla SharePoint-webbplatser till Microsoft 365 i molnet ska du nu skapa ett bokmärke för en länk till tjänstbeskrivningarna [för Microsoft 365 och Office 365.](/office365/servicedescriptions/office-365-service-descriptions-technet-library) Du behöver tjänstbeskrivningarna för att lära dig mer om SharePoint Online-funktioner och hur de skiljer sig från lokala SharePoint Server. Uppgradera funktionella Microsoft Office SharePoint Server 2007-servergrupper. Om installationen har skadade webbplatser åtgärdar du dem innan du uppgraderar.
  
## <a name="a-note-about-managing-risk"></a>En kommentar om att hantera risker

Metoder som "sida vid sida" är viktiga i schemat för uppgraderingslogiken. När du uppgraderar sida vid sida behåller du din Microsoft Office SharePoint Server 2007-servergrupp, men bygger en servergrupp för nästa version (SharePoint Server 2010) på ny maskinvara. Det här är bra på tre sätt:
  
1. Du har ett ställe där du kan ta säkerhetskopior av Microsoft Office SharePoint Server 2007-databaser för att uppgradera dem separat med hjälp av databas bifoga.
    
2. Om du kommer fram till att endast ett litet antal viktiga dokumentbibliotek och annan information används i Microsoft Office SharePoint Server 2007-servergruppen kan du välja att manuellt flytta data från Microsoft Office SharePoint Server 2007 till SharePoint Server 2010, eller att endast ta specifika webbplatser till nästa version (vilket kan underlätta jobbet).
    
3. Ju mindre du gör med Microsoft Office SharePoint Server 2007-servergruppen desto säkrare är de data som servergruppen innehåller när du uppgraderar.
    
Metoder som In-Place-uppgradering kommer att agera direkt på Microsoft Office SharePoint Server 2007-servergruppen, vilket ger färre enkla alternativ för att avbryta en uppgraderingsväg och börja om från den ursprungliga miljön. Ta i så stor utsträckning som möjligt med vissa säkerhetsåtgärder (som att ta och testa säkerhetskopior av den ursprungliga miljön). Om din Microsoft Office SharePoint Server 2007-servergrupp till exempel är virtuell och du dupliceras för säkerhetskopiering och återställning, bör du säkerhetskopiera och återställa de mest aktuella databaserna innan tjänstfönstret för uppgraderingen. Om du vet att du har möjlighet att återställa säkerhetskopior av databasen kan du inte bara tänka på fel, du får även sinnesro.
  
> [!TIP]
> Metodtipsdokument för uppgradering finns för [Microsoft Office SharePoint Server 2007,](/previous-versions/office/sharepoint-2007-products-and-technologies/cc261992(v=office.12)) [SharePoint Server 2010,](/previous-versions/office/sharepoint-server-2010/cc261992(v=office.14)) [SharePoint Server 2013](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)och [SharePoint Server 2016.](/SharePoint/upgrade-and-update/best-practices-for-upgrade) Du kan också söka efter [Microsoft-partner](https://partnercenter.microsoft.com/pcv/search) som har erfarenhet av uppgraderingar eller Microsoft 365-migreringar. 
  
## <a name="make-your-plan"></a>Gör upp en plan

Om du behöver uppgradera behöver du en plan, och en storlek passar inte alla i dessa fall. Planen kan vara så enkel som att "Skapa en Microsoft 365-prenumeration med SharePoint Online, registrera en domän och omdirigera personer att spara sina filer där". Och det är det kanske inte. Beslutet är ditt, och det beror på dina och användarnas behov.
  
> [!NOTE]
> Det är riskabelt att köra programvara vars livscykel har avslutats. Produkter där supporten har slut korrigeras inte längre när problem hittas. Det innebär också att det inte kommer att finnas några säkerhetskorrigeringar om det uppstår nya säkerhetshot, eftersom det inte längre finns stöd för produkter med slutet av livscykeln. Undvik den situationen! 
  
### <a name="first-know-your-farm"></a>Först måste du känna servergruppen

När du uppgraderar ska besluten baseras på vad servergruppen gör för organisationen. Vilka behov uppfyller den? Vad är dess roll? Varje servergrupp i företaget kan ha olika roller. Vissa SharePoint-farms kan vara  *kritiska*  , vissa kan vara filarkiv för säker förvaring. Om servergruppen innehåller många roller samtidigt kan du behöva veta vad webbplatssamlingar, webbplatser eller dokumentbibliotek gör, eventuella anpassningar och hur viktiga de är. Det kan verka som en massa arbete att analysera data på den här nivån, men det sparar tid och arbete att bemästra domänen innan du uppgraderar eller migrerar den. När du känner till alla rörliga delar och de viktigaste bitarna vet du också vad du har blivit ingrodd och kan lämna kvar. Den kunskapen är bara till nytta i framtiden. 
  
Så vad säger användarna är viktigast med SharePoint Server-servergruppen?
  
- Inbyggda SharePoint-funktioner
    
- Den stora data corpus (t.ex. ett arkiv med filer)
    
- Tillgänglighet
    
- Kritiska appar, webbdelar eller dokument i servergruppen (verksamhetskritiska servergrupp)
    
- De standarder för efterlevnad som uppfylls
    
- Anpassningar
    
Om du kör något som är viktigt för företaget från SharePoint-servergruppen, till exempel om den fungerar som en stor katalog med kritiska data om klienttjänstkraven, kan du sätta ett bock bredvid Kritiska appar, men även Tillgänglighet. Det innebär att företaget skulle påverkas om du inte kunde använda SharePoint på ett tag. På samma sätt kan du kontrollera Anpassningar eftersom de kritiska tjänster servergruppen erbjuder baseras på anpassad kod, webbplatsdefinitioner eller ett antal anpassningar som fungerar tillsammans.
  
Om SharePoint har uppfyllt dina behov utan att du behöver göra något utöver det som finns inbyggt i programvaran, och du oftast uppdaterar programvaran och utför administration och underhåll, kanske du har valt Inbyggda SharePoint-versioner. Det här kan också vara orsaken till att du sitter på en äldre version av SharePoint. Med andra ord, den gör redan det du behöver den och du har inte behövt uppgradera än så länge på supporten för Microsoft Office SharePoint Server 2007.
  
När du listar upp de här sakerna i en punktlista skapar du kriterier för uppgraderingen. Vilken uppgradering som helst måste med andra ord kunna övervägas för att uppfylla det här fältet. På så sätt kan du utesluta metoder som inte passar för dina behov.
  
### <a name="a-simple-sample-plan"></a>Ett exempel på en enkel plan

Det kan behöva vara ett bredare beslut med ledningen och andra administratörer på den väg din SharePoint-uppgradering ska ta. SharePoint Server-administratörer samarbetar ofta med Microsoft SQL Server-administratörer, och även med nätverks- och säkerhetsteam. När det finns många intressenter kan du behöva skapa ett avtal för eller justera din plan för uppgradering och migrering. Om du till exempel migrerar data så att en del av företaget ska använda SharePoint Online i Microsoft 365 måste du förmodligen justera eller testa prestanda i nätverket. Berörda grupper bör informeras i förväg.
  
I det här enkla exemplet visas förslag från en SharePoint-administratör och sedan den plan som alla intressenter kommit överens om. Dokumentera för tydlighets skull alla överenskommelser och beslut.
  
Planen börjar efter en detaljerad analys av en servergrupp och försöker identifiera servergruppens roll, smärtpunkter och annan viktig information som gör det möjligt att begränsa vissa uppgraderingsalternativ. Därefter in kommer ett förslag från en SharePoint-administratör och intressenterna kommer överens om en handlingsplan.
  
Min "viktigaste" punktlista:
  
- Tillgänglighet, inbyggda funktioner i SharePoint och efterlevnadsstandarder.
    
- De flesta data finns i tre webbplatssamlingar, där en mötesarbetsyta som används av ett utvecklingsteam är särskilt viktig och används mycket i olika tidszoner världen över.
    
- Det finns 17 andra webbplatser som används ofta.
    
- Två dokumentbibliotek (Mötesarbetsyta och Dokument i rotwebbplatssamlingen) är större än de andra (fler än 8 000 dokument var). Vi har ett stort antal arkiverade dokument och listor med kalkylbladsbilagor.
    
- Det finns fjorton listor med bibliotek som innehåller känsliga data och som måste följa villkoren för efterlevnad.
    
- Vi MÅSTE ha möjlighet att göra kvar- och e-discovery oavsett var vi befinner oss.
    
- Vissa av dessa data MÅSTE vara lokala, på grund av regler för informationsekunder.
    
 **Alternativ för uppgradering och migrering:**
  
| Ja | Nej |
|:-----|:-----|
|Uppgradera databaser med databas bifoga  <br/> |Uppgradering på plats  <br/> |
|Uppgradera med farms sida vid sida  <br/> |Hybriduppgradering  <br/> |
|Api-migrering till SPO i Microsoft 365 (för personliga webbplatsdata)  <br/> |SharePoint Hybrid (behövs inte ännu)  <br/> |
|Viss manuell datamigrering till SharePoint Online för kritiska data  <br/> |FastTrack-guideuppgradering till Microsoft 365  <br/> |
   
 **Föreslagen plan:**
  
Uppgradera lokalt med versioner av SharePoint sida vid sida, en del virtualiserade, så att vi kan uppgradera databaserna först. Gå från SharePoint 2007 till SharePoint 2010. Administratörer och utvecklar testar den resulterande servergruppen. Användare testar den resulterande servergruppen. Åtgärda eventuella problem som dyker upp under den här tiden. Uppgradera återigen SharePoint 2010-databaser till SharePoint 2013 sida vid sida. Testa. Användartest/pilottest. Åtgärda eventuella problem som dyker upp under den här tiden.
  
- Överväg om en sammanslagen hybrid med SPO uppfyller dina behov.
    
- Överväg [FastTrack-hjälp](https://fasttrack.microsoft.com) om du vill uppgradera till SharePoint Online härifrån. 
    
- Avgör om några webbplatssamlingar kan läggas på en Microsoft 365-prenumeration. (Microsoft 365 uppfyller många [efterlevnadsstandarder.](/compliance/regulatory/offering-home) Microsoft 365 har [eDiscovery](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) och kan få [plats](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) via Compliance Centre.) 
    
Fortsätt annars med en uppgradering sida vid sida till SharePoint Server 2016.
  
> [!NOTE]
> Mellan de rekommendationer som administratörerna kommer med under planeringen av uppgraderingen och de faktiska processerna pågår samtal med andra intressenter som uppgraderingen måste ta del av. Ibland kan administratörer bli tvingad att ändra sina planer av ekonomisk ekonomi. Oavsett vilket beslut ni kommer fram till bör du dokumentera den plan ni kommit överens om i framtiden. Den kan se ut ungefär så här: 
  
 **Min handlingsplan:**
  
Lokalt använder vi en virtuell miljö för att skapa standardinställningar för SharePoint Server 2010 och 2013. SharePoint Server 2016 kommer att byggas på ny maskinvara som uppfyller systemkraven för 2016. Vi kommer att använda databas bifogad databas för att uppgradera databaser från SharePoint 2007 via alla versioner mellan den och SharePoint Server 2016. Grundläggande anpassningar återskapas och testas för närvarande i SharePoint Server 2016-miljön, om de inbyggda funktionerna inte redan uppfyller våra behov. Om vi lyckas kommer vi att ha en lokal servergrupp på ny maskinvara med uppgraderade databaser och färre anpassningar. Vi kommer att bifoga uppgraderade innehållsdatabaser till nya webbplatssamlingar i SharePoint Server 2013, testa, användartesta/pilottesta och sedan göra en DNS-kontroll till den nya SharePoint Server 2016-miljön för direktanvändning.
  
- Vi kommer inte att överväga Federerad hybrid mellan SharePoint Server 2016 och SharePoint Online just nu.
    
- Uppskattningsvis kan 35 % av våra webbplatser omvandlas till nya SPO-webbplatser med egna domäner, eller slutligen omvandlas till OneDrive för företag-lagring. Vi letar efter andra möjligheter att omvandla webbplatser eller att dirigera nya webbplatser till SPO.
    
- En del av den här delen av migreringen kommer att ske manuellt genom att dra och släppa till personliga webbplatser i OneDrive för företag, och en del kommer att ske via migrerings-API:t.
    
Mer detaljerade anvisningar eller länkar till specifika uppgraderingsbeskrivningar bör följa en plan. MOSS 2007-datorn ska inte inaktiveras, och virtuella miljöer ska bevaras för jämförelse. Uppgraderingen slutförs dock när användare omdirigeras till SharePoint Server 2016.
  
Andra viktiga faktorer när du väljer metod är den totala kostnaden för uppgraderingen och tidskostnaden (du kan läsa mer om det här i artikeln med en översikt över SharePoint-migrering). Du kommer dock ha mycket nytta av att planera i förväg, både när det gäller att uppfylla förväntningar, att fatta bra beslut och att sätta ramar för hur framgången kommer att se ut.
  
## <a name="related-links"></a>Relaterade länkar

[Resurser som hjälper dig att uppgradera från Office 2007-servrar och -klienter](upgrade-from-office-2007-servers-and-products.md)
  
[Microsoft Lifecycle-policy och livscykelsökning](https://support.microsoft.com/lifecycle)
  
[Sök efter Microsoft-partner som kan hjälpa dig med uppgradering eller migrering](https://partnercenter.microsoft.com/pcv/search)
