---
title: Interaktioner i grupper
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Interaktioner i grupper
ms.openlocfilehash: 9632debf1bc6fdd2fce061a4c535906410700175
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662875"
---
# <a name="groups-services-interactions"></a>Interaktioner i grupper

Microsoft 365-grupper ger en gemensam infrastruktur för ett antal tjänster och arbets belastningar inom Microsofts 365-plattform för att tillhandahålla en uppkopplad upplevelse för slutanvändarna. I sin kärna finns en Microsoft 365-grupp för att tillhandahålla:

- Ett sätt att hantera medlemskap (Azure AD)
- En plats för meddelanden och konversationer att genomföra (Exchange-postlåda, Microsoft Teams, Yammer)
- En plats där filer lagras (SharePoint)
- En kalender för schemaläggning (Exchange)
- En antecknings bok för att fånga anteckningar (OneNote)

När du skapar en grupp skapas ett antal andra resurser, men de visas inte förrän de har åtkomst till den första gången från tjänsten:

- En anslags tavla för att hantera grupp aktiviteter (Planner)
- En arbets yta för rapportering (Power BI)
- Ett område för delade videoklipp (Microsoft Stream)
- Ett område för delade formulär (formulär)

I Microsoft 365 kan andra tjänster samverka med Microsoft 365-grupper för att tillhandahålla ytterligare funktioner och funktioner för grupp medlemmar.
Exempel på detta är:

- Power app för appar
- Automatisera Power för arbets flöden
- Project på webben och översikt för Vattenfalls projektledning
- Teams för kanalbaserade konversationer
- Yammer för intressanta grupper

## <a name="user-interactions-with-groups"></a>Användar interaktion med grupper

Microsoft 365-grupper kan skapas och hanteras av olika gränssnitt, både för administratörer och slutanvändare. 

### <a name="administrative-experiences"></a>Administrativa upplevelser

Administratörer kan skapa och hantera Microsoft 365-grupper från flera olika administrations Center för arbets belastning, kommando rads gränssnitt som stöder skript samt anpassade program som fungerar tillsammans med Graph API. Det enda undantaget för detta är Yammer-grupper – som måste skapas från Yammer Web Interface.

**Relaterade inställningar**

Bland de olika administrativa gränssnitt som kan hantera grupp inställningar finns flera överlappande som du bör känna till.

**Administrationscenter för Microsoft 365**

I Microsoft 365 Admin Center är gäst åtkomst till grupper aktiverat som standard, vilket är möjligheten att tillåta ägare att lägga till gäster. Det finns inga fler kontroller på organisations nivå i det här administrations centret.

**Administrations Center för Azure AD**

Administrations centret för Azure AD erbjuder kontroller om användare kan skapa grupper eller tilldela ägare i Azure-portaler, samt giltighets datum och princip inställningar.

Administrations Center innehåller också ett antal åtgärder för kontroll av gäst inbjudningar som går utöver det som ingår i Microsoft 365 Admin Center, till exempel möjligheten att begränsa huruvida icke-ägare kan bjuda in gäster

**SharePoint**

SharePoint-webbplatser skapas med säkerhets grupper för ägare, medlem och besökare med de två första matchningarna till sina Microsoft 365-gruppmotparter. När medlemskap för SharePoint Online-webbplatser hanteras vanligt vis av den associerade Microsoft 365-gruppen är det inte en dubbelriktad relation. Alla ändringar av medlemskap på Microsoft 365-gruppnivån återspeglas i SharePoint, men om medlemskap ändras i SharePoint-gruppen visas inte detta i gruppen Microsoft 365.

### <a name="user-experiences"></a>Användar upplevelser

Slutanvändare kan skapa grupper från flera tjänster i Microsoft 365, och i andra kan de bara dela med en grupp.

Följande tjänster gör det möjligt att skapa grupper för slutanvändare:
                         
Outlook Planner-projekt för webben SharePoint-strömmar Microsoft Teams Yammer

**Begränsning av grupp skapande**

Ett gemensamt sätt att styra Sprawl är att begränsa vilka användare som kan skapa dem. Detta kan bara göras om du begränsar skapandet av grupper. Detta påverkar möjligheten att skapa grupper från andra tjänster, där det kan vara nödvändigt för slutanvändaren. Microsoft 365-grupper stöder inte möjligheten att begränsa skapande av grupper från vissa appar eller tjänster medan de tillåts från andra.

Hur grupp skapande begränsas varierar mellan program och tjänster:


|App eller tjänst|Funktionerna|
|:-------------|:---------|
|Outlook|Alternativet **ny grupp** tas bort från menyn nytt på sidan kontakter|
|Planner|I den **nya planen** förklaras att grupp skapandet har inaktiverats och att du kan lägga till planen i en befintlig grupp|
|Projekt för webben och översikt|**Skapa grupp** -menyn förklarar hur grupp skapande är begränsat och föreslår användning av en befintlig grupp.|
|SharePoint|Du kan fortfarande skapa en grupp webbplats som inte är kopplad till en grupp.|
|Strömma|Alternativet **gruppera** visas inte under **menyn skapa**.|
|Teams|Användaren kan inte skapa ett team med en ny grupp, men du kan fortfarande skapa ett team som använder en befintlig grupp.<br><br>Knappen **skapa en grupp** ersätts med **Skapa team från en grupp**.|
|Yammer|Alternativet **skapa ett grupp namn** tas bort från huvud grupper och grupp navigering.|

## <a name="services-interactions-with-groups"></a>Tjänst interaktioner med grupper

Se grupperna i Microsoft 365-affisch för information om olika typer av grupper, hur de skapas och hanteras och några få rekommendationer.

[![Miniatyrbild av infografiken för grupper](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)

Följande tabell innehåller en översikt över Microsoft 365-grupper interaktioner med olika tjänster:

|Produkt|Funktioner|Fungerar tjänsten<br>finns utan en grupp?|Kan tjänsten<br>skapa en grupp?|Tar bort<br>instans ta bort gruppen?|
|:---|:---|:---|:---|:---|
|Azure AD|Medlemskap, grupp kontroller, gäster|Ja|Ja|Ja|
|Exchange|Kalender, post låda|Ja|Ja|Ja|
|Formulärautentisering|Omformning|Ja|Nej|Nej|
|OneNote|Antecknings bok|Ja|Nej|Nej|
|Planner|Uppgifts tavla|Nej|Ja|Ja|
|Power app-appen|Program|Ja|Nej|Nej|
|Automatisk strömförsörjning|Arbets|Ja|Nej|Nej|
|Power BI (klassisk)|Workspace|Nej|Ja|Ja|
|Power BI (ny)|Workspace|Ja|Nej|Ja|
|Project för webben|Projektplan|Ja|Ja|Nej|
|Översikt|Översikt|Ja|Ja|Nej|
|SharePoint|Webbplatsmallar|Ja|Ja|Ja|
|Strömma|Kanal, video|Ja|Ja|Ja|
|Teams|Grupp|Nej|Ja|Ja|
|Yammer|Grupp|Ja|Ja|Ja|

Medan tabellen ovan tillhandahåller en översikt över grupp samverkan med Microsoft 365-tjänster finns det ett antal Nuances och tag som du bör förstå. Följande avsnitt innehåller en mer ingående titt på de specifika arbets belastningarna och deras interaktioner med grupper.

## <a name="azure-ad"></a>Azure AD

Azure AD tillhandahåller de underliggande funktionerna för identitets hantering i Microsoft 365.

**Viktiga funktioner i grupper**

- Grupp medlemskap
- Namngivnings princip
- Förfallo princip
- Gäst
- Begränsning av grupp skapande

**Kan Azure AD skapa en grupp?**

Ja, Microsoft 365-grupper kan skapas från Azure AD antingen via administrations webb portalen, via PowerShell eller Graph API.

**Existerar Azure AD utan en grupp?**

Ja, Azure AD utför ett stort antal tjänster som inte har någon relation till Microsoft 365-grupper. Alla Microsoft 365-grupper representeras som ett objekt i Azure AD.

**Kan det finnas flera instanser av Azure AD per grupp?**

Nej, det finns bara en instans av Azure AD.

**Kan Azure AD associeras med flera grupper?**

Ja, eftersom Azure AD är den underliggande plattformen som tillhandahåller grupp medlems tjänsten.

**Kan Azure ADs Association med en grupp ändring?**

Nej, Azure AD är den underliggande plattformen där det finns grupper.

**Tar du bort instansen?**

Om du tar bort gruppen i Azure AD raderas relevanta grupprelaterade tjänster och innehåll.

## <a name="teams"></a>Teams

Teams är en chatt-centrerad arbets yta som syftar till att förbättra samarbetet genom att tillhandahålla ett interaktivt gränssnitt för att interagera med en mängd olika Microsoft-och tredje parts tjänster.

När ett team skapas döljs som standard den post låda och kalender som är kopplad till Microsoft 365-gruppen från både den globala adress listan i Exchange och Outlook. Det här kan åsidosättas manuellt av en administratör om användaren vill använda både Outlook och Teams i samma Microsoft 365-grupp.

**Viktiga funktioner i grupper**

- Konversationer
- Kanaler & flikar
- Tider

**Kan grupper skapa en grupp?**

Ja, skapa ett nytt team skapar en ny Microsoft 365-grupp. Det går också att skapa ett team för en befintlig grupp som för tillfället inte har någon.

**Existerar Teams utan en grupp?**

Nej, det är inte möjligt för ett team att existera utan en grupp.

**Kan det finnas flera team per grupp?**

Nej, relationen mellan ett team och en grupp är 1:1.

**Kan ett team vara associerat med flera grupper?**

Nej, själva teamet kan bara kopplas till en grupp.

**Kan teamets associering med en grupp ändring?**

Nej, teamet kan bara vara kopplade till den grupp som den ursprungligen var kopplad till.

**Tar du bort gruppen?**

Ja, om du tar bort teamet i Microsoft Teams tas gruppen, de gruppassocierade tjänsterna och innehållet bort.

## <a name="exchange"></a>Exchange

Exchange Online tillhandahåller meddelanden, kalender, kontakter och tillhör ande funktioner. I kontexten för en grupp är det bara en enskild resurs som är kopplad – i motsats till en hel tjänst instans.

**Viktiga funktioner i grupper**

- Post låda och kalender
- Möjlighet att skicka e-post till alla grupp medlemmar
- Lagring av Team kanal konversationer för eDiscovery-syften, Planner-kommentarer

**Kan Exchange skapa en grupp?**

Ja, det är möjligt att skapa en grupp från administrations centret för Exchange Online och från Outlook. Du kan också konvertera distributions listor för Exchange till Microsoft 365 Groups.

**Finns det ingen grupp med Exchange?**

Ja, Exchange Online erbjuder ett antal tjänster, inklusive delade post lådor och kalendrar, utan grupp koppling.

**Kan det finnas flera instanser av Exchange-postlådor eller-kalendrar per grupp?**

Nej, det kan bara finnas en Exchange Online-postlåda och kalender för en grupp.

**Kan Exchange-postlådor och-kalendrar associeras med flera grupper?**

Nej, post lådan och kalendern har en 1:1-relation med gruppen. Det går att dela post lådan med andra användare eller grupper, men detta utgör ingen form av tjänst koppling.

**Kan Exchange-postlådan eller kalenderns associering med en grupp ändring?**

Nej, post lådan och kalendern kan inte ändras till en annan grupp. Innehållet kan dock flyttas från en post låda till en annan i Outlook eller med hjälp av ett verktyg från tredje part.

**Tar du bort gruppen?**

Ja, om du tar bort post lådan i Exchange tas gruppen bort samt gruppassocierade tjänster och innehåll.

## <a name="forms"></a>Formulärautentisering

Formulär ger webbaserade undersökningar och test.

**Viktiga funktioner i grupper**

- Ägandes Kap för formulär

**Kan formulär skapa en grupp?**

Nej, det går inte att skapa en grupp.

**Finns det någon som inte är en grupp?**

Ja, undersökningar och test kan skapas direkt i ett slutanvändares konto.

**Kan det finnas flera former per grupp?**

Ja, det kan finnas flera formulär kopplade till en grupp.

**Kan formulär vara kopplade till flera grupper?**

Nej, ett formulär kan bara kopplas till en grupp.

**Kan ett formulärs koppling till en grupp ändring?**

Nej, när ett formulär är associerat med en grupp (antingen direkt i eller ägarskap från en person) kan den inte flyttas till en annan grupp.

**Tar du bort gruppen?**

Nej, det går inte att ta bort en grupp från formulär gränssnittet, endast enskilda formulär.

## <a name="onenote"></a>OneNote

OneNote är en digital antecknings bok. Den OneNote-anteckningsbok som har skapats med en grupp är en fil på den associerade SharePoint-webbplatsen och inte i en gruppansluten tjänst.

**Viktiga funktioner i grupper**

- Delad antecknings bok (lagrad i det gruppassocierade SharePoint-biblioteket)

**Kan OneNote skapa en grupp?**

Nej, OneNote-programmet kan inte skapa en grupp.

**Finns det ingen grupp med OneNote-anteckningsböcker?**

Ja, antecknings böcker kan skapas direkt i OneDrive eller på andra delade platser.

**Kan det finnas flera OneNote-anteckningsböcker per grupp?**

Ja, en antecknings bok skapas som standard och andra kan läggas till, men alla länkar till OneNote från gruppassocierade tjänster kommer alltid till standard antecknings boken.

**Kan en OneNote-anteckningsbok vara kopplad till flera grupper?**

Nej, antecknings boken är lagrad i det gruppassocierade SharePoint-biblioteket och länkad från olika gränssnitt. Den kan delas med andra grupper på samma sätt som den kan delas med enskilda personer.

**Kan antecknings bokens förening med en grupp ändring?**

Nej, antecknings boken är kopplad till gruppen och kan kommas åt direkt från andra grupp anslutna tjänster, men innehållet kan flyttas från en antecknings bok till en annan i OneNote-programmet.

**Tar du bort gruppen?**

Nej, om du har tagit bort OneNote-anteckningsboken kan det finnas felaktiga länkar i vissa av de gruppassocierade tjänsterna.

## <a name="planner"></a>Planner

Planner är en lättviktig tjänst för aktivitets hantering.

**Viktiga funktioner i grupper**

- Anslags tavla för att hantera grupp aktiviteter

**Kan Planner skapa en grupp?**

Ja, skapandet av en plan skapar en ny grupp.

**Finns det en Planner-tavla utan grupp?**

Nej, en plan måste kopplas till en grupp.

**Kan det finnas flera planer per grupp?**

Ja, det kan finnas flera planer per grupp.

**Kan en plan associeras med flera grupper?**

Nej, en plan är bara avsedd för grupp medlemskap för att fastställa åtkomst.

**Kan en plans förening med en grupp ändring?**

Nej, om du kopierar en plan skapas en ny grupp.

> [!NOTE]
> En grupp som skapats i ett annat program visas inte i Planner automatiskt för en användare. För att få åtkomst till anslags tavlan måste de öppna den från ett annat gruppbaserade gränssnitt, till exempel Outlook.

**Tar du bort gruppen?**

Ja, om du tar bort planen raderas gruppen och tillhör ande gruppassocierade tjänster och innehåll.

## <a name="power-apps"></a>Power Apps

Power Apps ger en arbets yta för program utveckling utan kod.

**Viktiga funktioner i grupper**

- Appar kan delas med en grupp som ska köras och ändras

**Kan Power Apps skapa en grupp?**

Nej, Power app kan inte skapa en Microsoft 365-grupp.

**Finns det några Power Apps utan en grupp?**

Ja, appar kan skapas i Power app och lagras i det här kontot i Creator innan de delas eller publiceras.

**Kan det finnas flera program per grupp?**

Ja, det kan finnas flera program som delas med en grupp.

**Kan appar vara kopplade till flera grupper?**

Ja, en app kan delas med flera grupper.

**Kan ett program associeras med en grupp ändring?**

Ja, eftersom kopplingen mellan Power Apps och en Microsoft 365-grupp endast är gemensam – programmet finns fortfarande kvar med skaparen.

> [!IMPORTANT]
> [Grupper måste aktive ras innan appar kan delas med dem](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).

**Tar du bort gruppen?**

Nej, programmen är inte anslutna till den andra gruppen än de som delas med dem.

## <a name="power-automate"></a>Automatisk strömförsörjning

Power Automation (tidigare Microsoft-flöde) tillhandahåller arbets flöden och automatiserings tjänster.

**Viktiga funktioner i grupper**

- Arbets flöden kan delas med en grupp för att köras och ändras.

**Kan automatisk start skapa en grupp?**

Nej, Power autoautomatisera kan inte skapa en Microsoft 365-grupp i kontexten för att vara associerad med en.

Det är möjligt att skapa ett flöde som utför olika operationer, till exempel att skapa en Azure AD-säkerhetsgrupp eller uppdatera medlemskap för en Microsoft 365-grupp.

**Finns det fler än en grupp?**

Ja, flöden kan skapas i Power automatisering och lagras i det här kontot i Creator innan de delas eller publiceras.

**Kan det finnas flera flöden per grupp?**

Ja, det kan finnas flera flöden som delas med en grupp.

**Kan ett flöde kopplas till flera grupper?**

Ja, ett flöde kan delas med flera grupper.

**Kan flödet kopplas till en grupp?**

Ja, eftersom kopplingen mellan Power automatisering och en Microsoft 365-grupp endast är gemensam – flödet finns fortfarande kvar med skaparen.

**Tar du bort en grupp?**

Nej, som Power app, är inte flödena anslutna till den andra gruppen än de som delas med dem.

## <a name="power-bi-classic"></a>Power BI (klassisk)

Power BI tillhandahåller interaktiva data-drivna instrument paneler och rapporter.

**Viktiga funktioner i grupper**

- Data rapportering

**Kan Power BI skapa en grupp?**

Om du skapar en klassisk arbets yta skapas en Microsoft 365-grupp.

**Finns det en klassisk Power BI-arbetsyta utan en grupp?**

Nej, [en klassisk arbets yta i Power BI måste kopplas till en grupp](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).

**Kan det finnas flera Power BI-arbetsytor per grupp?**

Nej, relationen mellan en klassisk arbets yta och en grupp är 1:1.

**Kan en arbets yta vara kopplad till flera grupper?**

Tekniskt Nej, när den klassiska arbets ytan skapas med gruppen kan innehållet delas utanför gruppen med användare och säkerhets grupper.

**Kan arbets ytans koppling till en grupp ändring?**

Nej, den klassiska arbets ytan är kopplad till gruppen, men innehållet kan flyttas från en arbets yta till en annan inom Power BI-gränssnittet eller genom att exportera innehåll lokalt.

**Tar du bort gruppen?**

Ja, om du tar bort arbets ytan i Power BI tas grupp-och gruppassocierade tjänster och innehåll bort.

## <a name="power-bi-new"></a>Power BI (ny)

Power BI tillhandahåller interaktiva data-drivna instrument paneler och rapporter.

När du skapar en ny arbets yta i Power BI skapar inte en Microsoft 365-grupp, vilket skapar en ny grupp (inte klassisk) i Power BI.

**Viktiga funktioner i grupper**

- Data rapportering

**Kan Power BI skapa en grupp?**

Nej, det går inte att skapa en Microsoft 365-grupp från det nya Power BI-gränssnittet.

**Finns den nya Power BI-arbetsytan utan grupp?**

Ja, det är möjligt att ha rapporter och arbets ytor som har skapats i Power BI och som inte är kopplade till Microsoft 365 Groups.

**Kan det finnas flera arbets ytor per grupp?**

Ja, [flera arbets ytor som skapas av Power BI kan delas med en enda grupp](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).

**Kan en arbets yta vara kopplad till flera grupper?**

Nej, en arbets yta som har skapats i Power BI kan bara kopplas till en enda grupp.

**Kan en arbets yta ha en koppling till en grupp ändring?**

Ja och nej. En arbets yta som har skapats i Power BI kan bara kopplas till en enskild grupp åt gången men kan ändra associeringen när som helst. En arbets yta som har skapats i Power BI av en grupp är permanent kopplad till gruppen.

**Tar du bort gruppen?**

Ja, om du tar bort arbets ytan i Power BI tas grupp-och gruppassocierade tjänster och innehåll bort.

## <a name="project-for-the-web"></a>Project för webben

Project för webben ger möjlighet att skapa projektplaner, Gantt-scheman och översikter.
Viktiga funktioner i grupper.

- Projektplaner

**Kan Project skapa en grupp?**

Ja, det är möjligt att skapa en ny Microsoft 365-grupp direkt från Project för webben.

**Existerar projekt utan en grupp?**

Ja, projekt kan existera utan att vara kopplade till en Microsoft 365-grupp, men tilldelning av uppgifter kräver grupp koppling.

**Kan det finnas flera projekt per grupp?**

Ja, det går att koppla ihop flera projekt i en och samma grupp.

**Kan Project associeras med flera grupper?**

Nej, ett projekt kan bara kopplas till en grupp.

**Kan ett projekts associering med en grupp ändring?**

Nej, när kopplingen med en grupp har upprättats kan den inte ändras.

**Tar du bort gruppen?**

Nej, om du tar bort projektet i Project för webben raderas inte gruppen.

## <a name="roadmap"></a>Översikt

Med översikt kan du skapa projekt översikter med Project för webben och Project Online.

**Viktiga funktioner i grupper**

- Projekt översikter

**Kan du skapa en grupp?**

Ja, det är möjligt att skapa en ny Microsoft 365-grupp direkt från översikten.

**Finns det ingen grupp i översikten?**

Ja, planerna kan existera utan att vara kopplade till en Microsoft 365-grupp, men det krävs grupp koppling för att dela översikten.

**Kan det finnas flera översikter per grupp?**

Ja, det går att ansluta flera översikter till en enda grupp.

**Kan en översikt vara kopplad till flera grupper?**

Nej, en översikt kan bara kopplas till en grupp.

**Går det att göra en översikt över en grupp?**

Nej, när kopplingen med en grupp har upprättats kan den inte ändras.

**Tar du bort gruppen?**

Nej, det tar inte bort gruppen om du tar bort översikten.

## <a name="sharepoint"></a>SharePoint

SharePoint är en webbaserad innehålls hanterings plattform som tillhandahåller bland annat lagrings tjänster för ett antal Microsoft 365-tjänster.

**Viktiga funktioner i grupper**

- Dokument bibliotek
- Bibliotek för lagring av OneNote-anteckningsbok
- Lagring av Teams-wiki-filer

**Kan SharePoint skapa en grupp?**

Ja, när du skapar en grupp webbplats i SharePoint skapas en Microsoft 365-grupp som standard. Det går också att skapa en grupp och, om du vill, ett team för en befintlig webbplats.

**Finns det ingen grupp med SharePoint-webbplatser?**

Ja, SharePoint erbjuder ett antal icke-gruppassocierade tjänster och webbplatser som kommunikations-och nav webbplatser. 

**Kan det finnas flera webbplatser per grupp?**

Nej, det kan bara finnas en webbplats per grupp. Privata kanaler i Teams använder ytterligare webbplatser som inte är anslutna till gruppen.

**Kan webbplatser vara kopplade till flera grupper?**

Tekniskt Nej, men när en webbplats skapas med en grupp kan innehållet delas med andra grupper.

**Kan en webbplats ha en koppling till en grupp ändring?**

Nej, själva webbplatsen är kopplad till gruppen, men innehållet kan flyttas från en webbplats till en annan inom SharePoint-gränssnittet genom att exportera innehåll lokalt eller med hjälp av ett verktyg från tredje part.

**Tar du bort gruppen?**

Ja, om du tar bort webbplatsen i SharePoint tas grupp-och gruppassocierade tjänster bort.

## <a name="stream"></a>Strömma

Microsoft Stream är en video värd-och delnings plattform.

**Viktiga funktioner i grupper**

- Video lagring
- Inspelning av Teams-möte
- Video kanaler

**Kan strömmar skapa en grupp?**

Ja, det är möjligt att skapa en ny Microsoft 365-grupp direkt från strömmen.

**Finns det en ström utan grupp?**

Ja, video kanaler och videor kan finnas i ström utan att vara kopplade till en grupp.

**Kan det finnas flera videor och kanaler per grupp?**

Ja, det kan finnas flera videor och kanaler i varje grupp.

**Kan en video eller kanal kopplas till flera grupper?**

Ja, medan en video eller kanal skapas med en grupp kan den delas med andra grupper.

**Kan kopplingen till en grupp ändras?**

Ja och nej; videor i strömmen ägs av den ursprungliga avladdaren eller Mötes inspelningen och kan kopplas till alla grupper, men video kanaler kan bara kopplas till den grupp de ursprungligen skapades i.

**Tar du bort en grupp?**

Nej, det tar inte bort gruppen om du tar bort videoklipp eller kanaler. Om du tar bort själva gruppen i strömmen tas gruppassocierade tjänster och innehåll bort, förutom själva videoklippen.

## <a name="yammer"></a>Yammer

Yammer är en social plattform för företag som är utformad för att kunna främja community-engagemang inom och mellan organisationer.

Om du skapar en community (tidigare "grupp") i Yammer skapas en post låda, men för närvarande används inte detta.

En Microsoft 365-grupp som är kopplad till Yammer kan inte användas med ett team i Microsoft Teams.

**Viktiga funktioner i grupper**

- Konversations område

**Kan Yammer skapa en Microsoft 365-grupp?**

Ja, om du skapar en ny grupp i Yammer skapas en ny Microsoft 365-grupp, om plattformarna är anslutna och användaren har möjlighet att skapa en grupp.

Det går inte att skapa en Yammer-grupp med tillhör ande Microsoft 365-grupp i gränssnitt och tjänster som inte är i Yammer.

**Finns det en Yammer-grupp utan en Microsoft 365-grupp?**

Ja, det är möjligt att skapa en Yammer-grupp utan en Microsoft 365-grupp.

Om Yammer-plattformen inte är ansluten till Microsoft 365-grupper, eller om användare inte har möjlighet att skapa en Microsoft 365-grupp, skapas Yammer-grupper utan Microsoft 365-gruppkoppling.

**Kan det finnas flera Yammer-grupper per Microsoft 365-grupp?**

Nej, relationen mellan en Yammer-grupp och en Microsoft 365-grupp är 1:1.

**Kan en Yammer-grupp associeras med flera Microsoft 365-grupper?**

Nej, Yammer-gruppen kan bara kopplas till en enda Microsoft 365-grupp. Det är möjligt att inlägg delas med eller flyttas till andra Yammer-grupper.

**Kan en Yammer-grupps koppling till en Microsoft 365-grupp ändras?**

Nej, Yammer-gruppen kan bara associeras med den Microsoft 365-grupp som den ursprungligen var kopplad till.

**Tar du bort Yammer-gruppen ta bort gruppen Microsoft 365?**

Ja, om du tar bort gruppen i Yammer tas tillhör ande Microsoft-grupper och gruppassocierade tjänster och innehåll bort.

