---
title: Interaktion mellan grupptjänster
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Interaktion mellan grupptjänster
ms.openlocfilehash: f9b0d7ca61d55e3d23aa94577fc8257073b26675
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539209"
---
# <a name="groups-services-interactions"></a>Interaktion mellan grupptjänster

Microsoft 365 Grupper är ett vanligt material för flera tjänster och arbetsbelastningar på Microsoft 365-plattformen för att ge slutanvändarna en uppkopplad upplevelse. Det finns en grupp Microsoft 365 tillhandahåller följande:

- Ett sätt att hantera medlemskapet (Azure AD)
- En plats där meddelanden och konversationer äger rum (Exchange postlåda, Microsoft Teams, Yammer)
- En plats där filer ska lagras (SharePoint)
- En kalender för schemaläggning (Exchange)
- En anteckningsbok för att spara anteckningar (OneNote)

När grupper skapas etableras även ett antal andra resurser, men de visas inte förrän första gången nås från tjänsten:

- En tavla för hantering av gruppuppgifter (Planner)
- En arbetsyta för rapportering (Power BI)
- Ett område för delade videor (Microsoft Stream)
- Ett område för delade formulär (formulär)

I Microsoft 365 funktioner kan andra tjänster interagera med Microsoft 365 grupper för att ge ytterligare funktioner till gruppmedlemmarna.
Exempel på detta är:

- Power Apps för appar
- Power Automate för arbetsflöden
- Project på webben och Översikt över vattenfallsbaserad projekthantering
- Teams för kanalbaserade konversationer
- Yammer för intressegrupper

## <a name="user-interactions-with-groups"></a>Användarinteraktion med grupper

Microsoft 365 Grupper kan skapas och hanteras från en mängd olika gränssnitt, både av administratörer och slutanvändare. 

### <a name="administrative-experiences"></a>Administrativa funktioner

Administratörer kan skapa och hantera Microsoft 365 grupper från flera av administrationscentret för arbetsbelastningen, kommandoradsgränssnitt som stöder skript samt egna appar som interagerar med Graph API. Det enda undantaget är Yammer grupper – som måste skapas från Yammer webbgränssnittet.

**Relaterade inställningar**

I de olika administrativa gränssnitten som kan hantera gruppinställningar finns det flera överlappningar som du bör känna till.

**Administrationscentret för Microsoft 365**

I Microsoft 365 är gäståtkomst i grupper aktiverad som standard, vilket är möjligheten att låta ägare lägga till gäster. Det finns inga ytterligare kontroller på organisationsnivå för grupper i det här administrationscentret.

**Administrationscenter för Azure AD**

I administrationscentret för Azure AD finns kontroller för huruvida användare kan skapa grupper eller tilldela ägare i Azure-portaler, samt inställningar för förfallo- och namnprinciper.

Administrationscentret innehåller också ett antal åtgärder för gästinbjudan som går utöver de som finns i Microsoft 365-administrationscentret, till exempel möjlighet att begränsa huruvida icke-ägare också kan bjuda in gäster

**SharePoint**

SharePoint skapas med säkerhetsgrupper som ägare, medlemmar och besökare, med de två första som matchar deras Microsoft 365-gruppmotsvarsvarumer. Medlemskap för SharePoint onlinewebbplatser hanteras i allmänhet av den associerade Microsoft 365-gruppen, men det är inte en dubbelriktad relation. Ändringar av medlemskap på Microsoft 365-gruppnivå återspeglas i SharePoint, men om medlemskapet ändras i SharePoint-gruppen återspeglas inte detta i Microsoft 365-gruppen.

### <a name="user-experiences"></a>Användarupplevelser

Slutanvändarna kan skapa grupper från flera av tjänsterna Microsoft 365 och i andra kan de bara dela med en grupp.

Följande tjänster gör det möjligt att skapa grupper av slutanvändare:
                         
Outlook Planner Project för webben SharePoint Streama Microsoft Teams Yammer

**Begränsning när grupper skapas**

En vanlig metod för att styra utstråningen av team är att begränsa vilka användare som kan skapa dem. Det kan bara göras genom att begränsa skapandet av grupper. Det här påverkar möjligheten att skapa grupper från andra tjänster där det kan vara nödvändigt för slutanvändaren. Microsoft 365 Grupper stöder inte möjligheten att begränsa skapandet av grupper från vissa appar eller tjänster samtidigt som det är tillåtet från andra.

Upplevelsen av att skapa gruppbegränsningar varierar mellan program och tjänster:


|App eller tjänst|Upplevelse|
|:-------------|:---------|
|Outlook|**Alternativet Ny** grupp tas bort från menyn Nytt på sidan Personer|
|Planner|**Ny plan** förklarar att skapande av grupper har inaktiverats och ger möjlighet att lägga till planen i en befintlig grupp|
|Project för webben och Översikt|**På menyn Skapa** grupp förklaras att skapandet av grupper är begränsat och föreslår att en befintlig grupp används.|
|SharePoint|Det går fortfarande att skapa en gruppwebbplats som inte är ansluten till en grupp.|
|Stream|**Gruppalternativet** visas inte under **menyn Skapa.**|
|Teams|Användaren kan inte skapa ett team med en ny grupp men kan fortfarande skapa ett team som använder en befintlig grupp.<br><br>**Knappen Skapa ett team** ersätts med **Skapa team från en grupp.**|
|Yammer|**Alternativet Skapa en grupp** tas bort från huvudnavigeringen för grupper/communities.|

## <a name="services-interactions-with-groups"></a>Interaktion mellan tjänster med grupper

I postern Grupper Microsoft 365 du information om olika typer av grupper, hur de skapas och hanteras samt några rekommendationer om styrning.

[![Miniatyrbild av infografiken för grupper](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)

Följande tabell innehåller en översikt över hur Microsoft 365 grupper interagerar med olika tjänster:

|Produkt|Funktioner|Gör tjänsten<br>finns det ingen grupp?|Kan tjänsten<br>skapa en grupp?|Tar bort<br>instans ta bort gruppen?|
|:---|:---|:---|:---|:---|
|Azure AD|Medlemskap, gruppkontroller, gäster|Ja|Ja|Ja|
|Exchange|Kalender, postlåda|Ja|Ja|Ja|
|Forms|Formulär|Ja|Nej|Nej|
|OneNote|Anteckningsbok|Ja|Nej|Nej|
|Planner|Uppgiftstavla|Nej|Ja|Ja|
|Power Apps appen|Program|Ja|Nej|Nej|
|Power Automate|Arbetsflöde|Ja|Nej|Nej|
|Power BI (klassisk)|Workspace|Nej|Ja|Ja|
|Power BI (nytt)|Workspace|Ja|Nej|Ja|
|Project för webben|Project abonnemang|Ja|Ja|Nej|
|Översikt|Översikt|Ja|Ja|Nej|
|SharePoint|Webbplats|Ja|Ja|Ja|
|Stream|Kanal, video|Ja|Ja|Ja|
|Teams|Team|Nej|Ja|Ja|
|Yammer|Grupp|Ja|Ja|Ja|

Även om tabellen ovan ger en översikt över gruppinteraktion med Microsoft 365 tjänster, finns det ett antal nyanser och inveckligheter som du bör förstå. I följande avsnitt får du en mer detaljerad bild av de specifika arbetsbelastningara och deras interaktioner med grupper.

## <a name="azure-ad"></a>Azure AD

Azure AD tillhandahåller underliggande identitetshanteringsfunktioner i hela Microsoft 365.

**Huvudfunktioner för grupper**

- Gruppmedlemskap
- Namnprincip
- Förfalloprincip
- Gäster
- Begränsning av skapande av grupp

**Kan Azure AD skapa en grupp?**

Ja, Microsoft 365 grupper kan skapas från Azure AD via administrationswebbportalen, via PowerShell eller via Graph API.

**Finns Azure AD utan grupp?**

Ja, Azure AD utför ett stort antal tjänster som inte har någon relation till Microsoft 365 Groups. Varje Microsoft 365 representeras som ett objekt i Azure AD.

**Kan det finnas flera instanser av Azure AD per grupp?**

Nej, det finns bara en instans av Azure AD.

**Kan Azure AD associeras med flera grupper?**

Ja, eftersom Azure AD är den underliggande plattform som tillhandahåller tjänsten för gruppmedlemskap.

**Kan Azure AD:s koppling till en grupp ändras?**

Nej, Azure AD är den underliggande plattformen där grupper finns.

**Raderas gruppen om instansen tas bort?**

Om du tar bort gruppen i Azure AD tas relevanta grupprelaterade tjänster och relevant innehåll bort.

## <a name="teams"></a>Teams

Teams är en chattcentreerad arbetsyta som försöker förbättra samarbetet genom att tillhandahålla ett enda gränssnitt som interagerar med olika Microsoft- och tredjepartstjänster.

Som standard döljs postlådan och kalendern som är kopplad till Microsoft 365-gruppen från både den globala adresslistan i Exchange och Outlook. Administratören kan manuellt åsidosätta detta om användaren vill använda både Outlook och Teams i samma Microsoft 365 grupp.

**Huvudfunktioner för grupper**

- Konversationer
- Kanaler & flikar
- Möten

**Kan Teams skapa en grupp?**

Ja, när du skapar ett nytt team skapas en ny Microsoft 365 grupp. Det går även att skapa ett team för en befintlig grupp som inte har någon för närvarande.

**Finns grupper utan en grupp?**

Nej, det går inte att ha ett team utan en grupp.

**Kan det finnas flera team per grupp?**

Nej, relationen mellan ett team och en grupp är 1:1.

**Kan ett team associeras med flera grupper?**

Nej, själva teamet kan bara associeras med en enda grupp.

**Kan ett teams koppling till en grupp ändras?**

Nej, teamet kan aldrig bara associeras med gruppen som det ursprungligen var kopplat till.

**Raderas gruppen om du tar bort teamet?**

Ja, om du tar Microsoft Teams gruppen i gruppen tas gruppen, grupprelaterade tjänster och innehåll bort.

## <a name="exchange"></a>Exchange

Exchange Online får meddelandefunktioner, kalenderfunktioner, kontakter och tillhörande funktioner. Inom en grupp är endast en enda resurs associerad – i motsats till en hel tjänstinstans.

**Huvudfunktioner för grupper**

- Postlåda och kalender
- Möjlighet att skicka e-post till alla gruppmedlemmar
- Storage av Teams kanalkonversationer i eDiscovery-syfte, Planner-kommentarer

**Kan Exchange skapa en grupp?**

Ja, det går att skapa en grupp Exchange Online administrationscentret och från Outlook. Du kan också konvertera Exchange distributionslistor till Microsoft 365 grupper.

**Finns Exchange någon grupp?**

Ja, Exchange Online tillhandahåller ett antal tjänster, inklusive delade postlådor och kalendrar, utan någon gruppassociatorganisation.

**Kan det finnas flera instanser Exchange postlådor eller kalendrar per grupp?**

Nej, det kan bara finnas Exchange Online postlåda och kalender för en grupp.

**Kan Exchange postlådor och kalendrar associeras med flera grupper?**

Nej, postlådan och kalendern har en 1:1-relation med gruppen. Det går att dela postlådan med andra användare eller grupper, men det skapar ingen form av tjänstassociating.

**Kan Exchange postlådans eller kalenderns koppling till en grupp ändras?**

Nej, postlådan och kalendern kan inte ändras till en annan grupp. Innehållet kan dock flyttas från en postlåda till en annan inom Outlook eller med hjälp av ett verktyg från tredje part.

**Tas gruppen bort när du tar bort postlådan?**

Ja, om du tar Exchange postlådan i ett e-postkonto tas gruppen samt grupprelaterade tjänster och innehåll bort.

## <a name="forms"></a>Forms

Forms tillhandahåller webbaserade undersökningar och test.

**Huvudfunktioner för grupper**

- Äganderätt till formulär

**Kan formulär skapa en grupp?**

Nej, Formulär kan inte skapa en grupp.

**Finns formulär utan grupp?**

Ja, undersökningar och test kan skapas direkt i en slutanvändares konto.

**Kan det finnas flera formulär per grupp?**

Ja, det kan finnas flera formulär kopplade till en grupp.

**Kan formulär kopplas till flera grupper?**

Nej, ett formulär kan bara associeras med en enda grupp.

**Kan ett formulärs koppling till en grupp ändras?**

Nej, när ett formulär är kopplat till en grupp (skapas direkt i, eller ägarskap som överförs från en enskild person) kan det inte flyttas till en annan grupp.

**Tas gruppen bort när du tar bort formuläret?**

Nej, det går inte att ta bort en grupp från Forms-gränssnittet, bara enskilda formulär.

## <a name="onenote"></a>OneNote

OneNote är ett digitalt anteckningsboksprogram. Den OneNote som skapats med en grupp är en fil på den associerade SharePoint-webbplatsen i stället för en gruppansluten tjänst.

**Huvudfunktioner för grupper**

- Delad anteckningsbok (lagrad i det grupprelaterade SharePoint anteckningsboksbiblioteket)

**Kan OneNote skapa en grupp?**

Nej, OneNote kan inte skapa en grupp.

**Finns OneNote utan grupp?**

Ja, anteckningsböcker kan skapas direkt i OneDrive eller på andra delade platser.

**Kan det finnas flera OneNote anteckningsböcker per grupp?**

Ja, en anteckningsbok skapas som standard och andra kan läggas till, men alla länkar till OneNote från grupprelaterade tjänster går alltid till standardanteckningsboken.

**Kan en OneNote associeras med flera grupper?**

Nej, anteckningsboken lagras i det grupprelaterade SharePoint och länkas från olika gränssnitt. Men den kan delas med andra grupper på samma sätt som den kan delas med enskilda personer.

**Kan anteckningsbokens koppling till en grupp ändras?**

Nej, själva anteckningsboken är kopplad till gruppen och kan kommas åt direkt från andra gruppanslutna tjänster, men innehållet kan flyttas från en anteckningsbok till en annan i OneNote program.

**Tas gruppen bort när du tar bort anteckningsboken?**

Nej, men om anteckningsboken OneNote bort kan det finnas brutna länkar i vissa grupprelaterade tjänster.

## <a name="planner"></a>Planner

Planner är en enkel tjänst för uppgiftshantering för grupper.

**Huvudfunktioner för grupper**

- Tavla för hantering av gruppuppgifter

**Kan Planner skapa en grupp?**

Ja, när du skapar en plan skapas en ny grupp.

**Finns det en Planner-tavla utan en grupp?**

Nej, en plan måste vara kopplad till en grupp.

**Kan det finnas flera planer per grupp?**

Ja, det kan finnas flera planer per grupp.

**Kan en plan associeras med flera grupper?**

Nej, en plan förlitar sig enbart på gruppmedlemskapet för att avgöra åtkomsten.

**Kan en plans koppling till en grupp ändras?**

Nej, men när en plan kopieras skapas en ny grupp.

> [!NOTE]
> En grupp som har skapats av ett annat program visas inte automatiskt i Planner för en användare. För att komma åt tavlan först måste de öppna den från ett annat gruppbaserat gränssnitt, till exempel från Outlook.

**Tas gruppen bort när planen tas bort?**

Ja, om du tar bort planen tas gruppen och grupprelaterade tjänster och innehåll bort.

## <a name="power-apps"></a>Power Apps

Power Apps en arbetsyta för apputveckling utan kod.

**Huvudfunktioner för grupper**

- Appar kan delas med en grupp som ska köras och ändras

**Kan Power Apps skapa en grupp?**

Nej, Power Apps inte skapa en Microsoft 365 grupp.

**Finns Power Apps utan en grupp?**

Ja, appar kan skapas i Power Apps och finnas i creators-kontot tills de delas eller publiceras.

**Kan det finnas flera appar per grupp?**

Ja, det kan finnas flera program som delas med en grupp.

**Kan appar kopplas till flera grupper?**

Ja, en app kan delas med flera grupper.

**Kan en apps koppling till en grupp ändras?**

Ja, eftersom kopplingen mellan Power Apps och en Microsoft 365 bara delas – appen finns fortfarande kvar hos skaparen.

> [!IMPORTANT]
> [Grupper måste vara säkerhetsaktiverade innan appar kan delas med dem.](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)

**Raderas gruppen om du tar bort programmet?**

Nej, apparna är inte kopplade till den andra gruppen än den som delas med dem.

## <a name="power-automate"></a>Power Automate

Power Automate (kallades tidigare för Microsoft Flow) innehåller arbetsflöden och automatiseringstjänster.

**Huvudfunktioner för grupper**

- Arbetsflöden kan delas med en grupp som ska köras och ändras.

**Kan Power Automate skapa en grupp?**

Nej, Power Automate kan inte skapa Microsoft 365 grupp i samband med att den kopplas till en.

Det går dock att skapa ett flöde som utför olika åtgärder, till exempel skapa en Azure AD-säkerhetsgrupp eller uppdatera medlemskap i en Microsoft 365 grupp.

**Finns flöden utan grupp?**

Ja, flöden kan skapas inom Power Automate och finnas i creators-kontot tills de delas eller publiceras.

**Kan det finnas flera flöden per grupp?**

Ja, det kan finnas flera flöden som delas med en grupp.

**Kan ett flöde associeras med flera grupper?**

Ja, ett flöde kan delas med flera grupper.

**Kan ett flödes koppling till en grupp ändras?**

Ja, eftersom kopplingen mellan Power Automate och en Microsoft 365 bara delas – finns flödet fortfarande kvar hos skaparen.

**Tas gruppen bort när du tar bort ett flöde?**

Nej, Power Apps inte direkt till den andra gruppen än den som delas med dem.

## <a name="power-bi-classic"></a>Power BI (klassisk)

Power BI interaktiva datadrivna instrumentpaneler och rapporter.

**Huvudfunktioner för grupper**

- Datarapportering

**Kan Power BI skapa en grupp?**

Ja, när du skapar en klassisk arbetsyta skapas Microsoft 365 grupp.

**Finns det Power BI klassiska arbetsytan utan en grupp?**

Nej, [en klassisk arbetsyta i Power BI måste associeras med en grupp](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).

**Kan det finnas Power BI arbetsytor per grupp?**

Nej, relationen mellan en klassisk arbetsyta och en grupp är 1:1.

**Kan en arbetsyta kopplas till flera grupper?**

Tekniskt sett är det inget, men när den klassiska arbetsytan skapas med gruppen kan innehållet delas utanför gruppen med användare och säkerhetsgrupper.

**Kan arbetsytans koppling till en grupp ändras?**

Nej, den klassiska arbetsytan är kopplad till gruppen, men innehållet kan flyttas från en arbetsyta till en annan i Power BI gränssnittet eller genom att exportera innehåll lokalt.

**Tas gruppen bort när du tar bort arbetsytan?**

Ja, om du tar bort arbetsytan Power BI grupp- och grupprelaterade tjänster och innehåll.

## <a name="power-bi-new"></a>Power BI (nytt)

Power BI interaktiva datadrivna instrumentpaneler och rapporter.

När du skapar en ny arbetsyta i Power BI skapas inte en Microsoft 365-grupp, och om du skapar en grupp på något annat sätt skapas en ny (inte klassisk) arbetsyta i Power BI.

**Huvudfunktioner för grupper**

- Datarapportering

**Kan Power BI skapa en grupp?**

Nej, det går inte att skapa en Microsoft 365 från det nya Power BI gränssnittet.

**Finns den nya Power BI arbetsytan utan en grupp?**

Ja, det går att skapa rapporter och arbetsytor i Power BI som inte är kopplade Microsoft 365 grupper.

**Kan det finnas flera arbetsytor per grupp?**

Ja, [flera arbetsytor som skapas Power BI kan delas med en enda grupp](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).

**Kan en arbetsyta kopplas till flera grupper?**

Nej, en arbetsyta som skapats Power BI bara kan kopplas till en enda grupp.

**Kan en arbetsytas koppling till en grupp ändras?**

Ja och nej. En arbetsyta som Power BI kan bara associeras med en enskild grupp i taget, men du kan när som helst ändra kopplingen. En arbetsyta som Power BI av en grupp är permanent kopplad till den gruppen.

**Tas gruppen bort när du tar bort arbetsytan?**

Ja, om du tar bort arbetsytan Power BI gruppen och grupprelaterade tjänster och innehåll tas bort.

## <a name="project-for-the-web"></a>Project för webben

Project för webben har möjlighet att skapa projektplaner, Gantt-diagram och översikter.
Huvudfunktioner för grupper.

- Project abonnemang

**Kan Project för webben skapa en grupp?**

Ja, det går att skapa en ny Microsoft 365 direkt från Project för webben.

**Finns det projekt utan en grupp?**

Ja, det kan finnas projekt utan att vara kopplade Microsoft 365 en grupp, men tilldelning av aktiviteter kräver gruppassociat koppling.

**Kan det finnas flera projekt per grupp?**

Ja, det går att ansluta flera projekt i en enda grupp.

**Kan projektet associeras med flera grupper?**

Nej, ett projekt kan bara associeras med en enda grupp.

**Kan ett projekts koppling till en grupp ändras?**

Nej, när kopplingen till en grupp har upprättats kan den inte ändras.

**Tas gruppen bort när du tar bort projektet?**

Nej, gruppen tas inte bort om Project för webben tas bort.

## <a name="roadmap"></a>Översikt

Översikt ger möjlighet att skapa projektöversikter med Project för webben och Project Online.

**Huvudfunktioner för grupper**

- Project översikter

**Kan Översikt skapa en grupp?**

Ja, det går att skapa en ny Microsoft 365 direkt från översikten.

**Finns Översikt utan grupp?**

Ja, översikter kan finnas utan att vara kopplade till Microsoft 365 grupp, men för delning av översikten krävs gruppassociat koppling.

**Kan det finnas flera översikter per grupp?**

Ja, det går att ansluta flera översikter till en enda grupp.

**Kan en översikt associeras med flera grupper?**

Nej, en översikt kan bara associeras med en enda grupp.

**Kan en översiktsorganisation med en grupp ändras?**

Nej, när kopplingen till en grupp har upprättats kan den inte ändras.

**Tas gruppen bort när du tar bort översikten?**

Nej, gruppen tas inte bort när du tar bort översikten.

## <a name="sharepoint"></a>SharePoint

SharePoint är en webbaserad innehållshanteringsplattform som bland annat tillhandahåller lagringstjänster för ett antal Microsoft 365 tjänster.

**Huvudfunktioner för grupper**

- Dokumentbibliotek
- Bibliotek för lagring av OneNote anteckningsbok
- Storage av Teams wiki-filer

**Kan SharePoint skapa en grupp?**

Ja, när du skapar en gruppwebbplats i SharePoint skapas en Microsoft 365 grupp som standard. Det går även att skapa en grupp och, om du vill, ett team för en befintlig webbplats.

**Finns SharePoint webbplatser utan en grupp?**

Ja, SharePoint erbjuder ett antal icke-grupprelaterade tjänster och webbplatser, till exempel kommunikations- och navplatser. 

**Kan det finnas flera webbplatser per grupp?**

Nej, det kan bara finnas en webbplats per grupp. Privata kanaler i Teams använder ytterligare webbplatser som inte är kopplade till gruppen.

**Kan webbplatser kopplas till flera grupper?**

Tekniskt sett är det inget, men när en webbplats skapas med en grupp kan innehållet delas med andra grupper.

**Kan en webbplats koppling till en grupp ändras?**

Nej, själva webbplatsen är kopplad till gruppen, men innehållet kan flyttas från en webbplats till en annan i SharePoint-gränssnittet, genom att exportera innehåll lokalt eller med hjälp av ett tredjepartsverktyg.

**Raderas gruppen om du tar bort webbplatsen?**

Ja, om du tar bort SharePoint gruppwebbplatser tas grupp- och grupprelaterade tjänster och innehåll bort.

## <a name="stream"></a>Stream

Microsoft Stream är en videovärd och delningsplattform.

**Huvudfunktioner för grupper**

- Videolagring
- Teams mötesinspelning
- Videokanaler

**Kan Stream skapa en grupp?**

Ja, det går att skapa en ny Microsoft 365 direkt från Stream.

**Finns Stream utan en grupp?**

Ja, videokanaler och videor kan finnas i Stream utan att vara kopplade till en grupp.

**Kan det finnas flera videor och kanaler per grupp?**

Ja, det kan finnas flera videor och kanaler i varje grupp.

**Kan en video eller kanal associeras med flera grupper?**

Ja, medan en video eller kanal skapas med en grupp kan den delas med andra grupper.

**Kan kopplingen till en grupp ändras?**

Ja och nej. Videor i Stream ägs av den ursprungliga uppladdaren eller mötesinspelaren och kan därför kopplas till valfri grupp, men videokanaler kan bara kopplas till gruppen de ursprungligen skapades i.

**Tas gruppen bort när du tar bort videor eller kanaler?**

Nej, gruppen tas inte bort när du tar bort videor eller kanaler. Men om du tar bort själva gruppen i Stream tas grupprelaterade tjänster och innehåll bort, förutom själva videoklippen.

## <a name="yammer"></a>Yammer

Yammer är en social plattform för företag som utformats för att främja community-engagemang inom och mellan organisationer.

När du skapar en community (kallades tidigare "grupp") i Yammer en postlåda, men detta används för närvarande inte.

En Microsoft 365 grupp som är associerad med Yammer kan inte användas med ett team i Microsoft Teams.

**Huvudfunktioner för grupper**

- Konversationsområdet

**Kan Yammer skapa en Microsoft 365 grupp?**

Ja, om du skapar en ny grupp i Yammer skapas en ny Microsoft 365-grupp, om plattformarna är anslutna och användaren har möjlighet att skapa en grupp.

En Yammer grupp med associerad Microsoft 365 kan inte skapas i något gränssnitt eller någon annan tjänst än Yammer sig.

**Finns det Yammer grupp utan en Microsoft 365 grupp?**

Ja, det går att skapa en Yammer grupp utan en Microsoft 365 grupp.

Om Yammer-plattformen inte är ansluten till Microsoft 365-grupper eller om användarna inte kan skapa en Microsoft 365-grupp skapas Yammer-grupper utan någon Microsoft 365-gruppassociatorganisation.

**Kan det finnas flera Yammer per Microsoft 365 grupp?**

Nej, förhållandet mellan en Yammer och en Microsoft 365 är 1:1.

**Kan en Yammer associeras med flera Microsoft 365 grupper?**

Nej, gruppen Yammer bara associeras med en enda Microsoft 365 grupp. Inlägg kan delas med eller flyttas till andra Yammer grupper.

**Kan en Yammer grupps koppling till en grupp Microsoft 365 gruppändring?**

Nej, gruppen Yammer någonsin bara associeras med den Microsoft 365 gruppen som den ursprungligen var associerad med.

**Tas gruppen Yammer bort en Microsoft 365 grupp?**

Ja, om du tar bort gruppen Yammer microsoft-relaterade grupper och grupprelaterade tjänster och innehåll tas bort.

## <a name="related-topics"></a>Relaterade ämnen

[Planering av samarbetsstyrning steg för steg](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Skapa din plan för samarbetesstyrning](collaboration-governance-first.md)