---
title: Slutet av livs cykel alternativen för grupper, team och Yammer
ms.reviewer: mmclean
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
description: Slutet av livs cykel alternativen för grupper, team och Yammer.
ms.openlocfilehash: 3720f63f99711a09d02675f10a7d639fe1bedc65
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377181"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>Slutet av livs cykel alternativen för grupper, team och Yammer

Microsoft 365-grupper och Microsoft Teams fungerar med en mängd olika anslutna tjänster. När en grupp eller ett team tas bort raderas de flesta uppgifterna i de anslutna tjänsterna också. I den här artikeln beskrivs hur du behåller informationen genom att flytta ut den från gruppen eller teamet innan du tar bort den.

En gemensam metod för grupper och team som inte längre behövs är att flytta filer från gruppen och lagra dem på en annan plats, till exempel ett SharePoint-dokumentbibliotek som fungerar som en databas eller ett arkiv. Den här övningen är baserad på en äldre formatmall där information lagras i filer och mappar och kommunikationen utförs via e-post.

I följande tabell visas de tjänster som är kopplade till grupper och team och viktiga typer av innehåll i var och en av dem:

|Tjänst|Innehålls typer|
|:------|:---------------|
|Teams|Kanal konversationer, filer i kanaler|
|Formulär|Undersöknings struktur och resultat|
|OneNote|Antecknings bok|
|Outlook|E-post och kalender|
|Planner|Information om projekt status och aktivitet|
|Automatisk strömförsörjning|Projektredovisning|
|Power BI|Data, rapporter och instrument paneler|
|Project på webben|Projektplaner|
|Översikt|Översikter|
|SharePoint|Filer, listor, wiki-data för team kanaler|
|Strömma|Videor|
|Yammer|Konversationer|

När du tar bort en grupp eller ett team raderas de flesta tillhör ande resurser också. Vissa av undantagen från detta inkluderar videor i ström – dessa finns kvar och ägs fortfarande av den person som laddade upp/registrerade dem, som gör flöden i Power automatiserat. Projekt-och översikts data i Project på webben finns kvar på CD-skivorna och kan återställas separat.

Grupper och team bevaras i en mjuk borttagning i 30 dagar och kan återställas när som helst. Men efter de 30 dagarna de och alla associerade resurser som tjänster och innehåll är fullständigt borttagna från Microsoft 365-miljön. Allt innehåll som skyddas av en bevarande princip är tillgängligt genom eDiscovery-sökningar.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>Frågor om livs cykeln för gruppanslutna tjänster

Det finns tre nyckelområden som grupp-och grupp ägarna och IT-administratörer måste tänka på när de tar bort en grupp eller ett team.

**Content**

Behöver innehållet bevaras när teamet inte längre fungerar eller saknas? Är det tillräckligt att lita på bevarande funktionerna i Microsoft 365 eller att det är en del av innehållet i appar och tjänster som inte ger möjlighet att bevaras? Behöver innehållet bevaras för hantering av Arkiv handlingar, för arkivering eller för framtida användning och referens ändamål?

De här frågorna måste tillfrågas innan något team arkiveras eller tas bort för att undvika förlust av data.

**Tjänster**

På innehållet i olika appar och tjänster måste de vara i sitt nuvarande arbets formulär? Om du till exempel vill att Power BI-rapporten ska vara tillgänglig, måste formulär resultaten vara tillgängliga i vyn visuell sammanfattning, är listorna i SharePoint länkad till eller inbäddat var som helst?

På liknande sätt som i innehålls övervägandet måste de här frågorna tillfrågas innan den underliggande gruppen tas bort eftersom det kanske inte räcker med att exportera innehållet.

**Gäst**

När gäster bjuds in till ett team skapar arbets flödet sin identitet i värd organisationens Azure Active Directory innan de läggs till i teamet. När ett team tas bort tas inte gäster bort från Azure Active Directory och det finns fortfarande kvar i Microsoft Teams-miljön. Medan gäster inte kan komma åt grupper, webbplatser, team eller innehåll som inte har delats med dem kan de fortfarande använda funktioner i Microsoft Teams, som att starta chatt, röst-och video samtal och använda appar.

En grupp eller grupp ägare kan bjuda in en extern användare att bli gäst i Azure Active Directory, lägga till dem i teamet samt ta bort dem från teamet. En team ägare kan inte ta bort gästen från Azure Active Directory – detta kan endast utföras av en global administratör eller användar administratör.

Därför är det viktigt att utföra gäst granskningar samt att förstå om gäster måste tas bort från Azure Active Directory när de raderas. Det kan finnas ett giltigt ärende för gäster att finnas kvar i katalogen, till exempel att vara medlem i en eller flera andra team eller använda andra Microsoft 365-eller Azure-tjänster.

## <a name="teams"></a>Teams

Teams-specifikt innehåll är främst i form av konversationer.

Det går inte att kopiera eller flytta konversationer i kanaler med hjälp av Microsoft Teams-funktionalitet. De kan dock exporteras med Graph API.

Om en bevarande princip tillämpas på Teams bevaras konversationerna och är tillgängliga via eDiscovery-sökningar. (Objekt som hittats i eDiscovery-sökningar kan exporteras, men det finns ingen kontext eller struktur från den ursprungliga källan – de är helt enkelt enskilda meddelanden.)

### <a name="archiving-a-team"></a>Arkivera ett team

Fördelen med att [arkivera ett team](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team) är att det ger fullständig åtkomst till teamet som det var, så att användarna kan fortfarande bläddra bland kanal samtal och öppna filer även om de inte är aktiva. Dessutom kan Teams inte arkiveras om det finns ett behov av att fortsätta att arbeta på dem (till exempel om det rör sig om en projekt förlängning).

När ett team arkiveras av en ägare är det skrivskyddat för medlemmar både för innehåll i gruppen samt om det är markerat, den associerade SharePoint-webbplatsen. Målet med den här åtgärden är att säkerställa att konversationer i kanaler bevaras i deras befintliga tillstånd, tillsammans med SharePoint-baserat innehåll som filer och wikis.

På SharePoint-webbplatsen finns inga synliga ändringar och det går inte att ändra några filer eller listor som den SharePoint-baserade behörighets gruppen för Microsoft 365-gruppen. Detta inkluderar OneNote-anteckningsbok för gruppen, som den lagras i biblioteket webbplats till gångar på SharePoint-webbplatsen.

När ett team arkiveras lyder den underliggande Microsoft 365-gruppen fortfarande på utgångs principen (om den är aktive rad) och ägaren måste fortsätta att förnya teamet.

När gruppens kanal konversationer och SharePoint-webbplatsens innehåll är skrivskyddat används inte samma för andra associerade tjänster:

- Planner-buckets och uppgifter kan fortfarande skapas, ändras och tas bort
- Formulär kan fortfarande ta emot inlägg
- Outlook-postlådan kan fortfarande ta emot e-postmeddelanden
- Power BI-instrumentpaneler, rapporter och data kan fortfarande ändras
- Projekt och översikter kan fortfarande redige ras i Project på webben
- Videoklipp kan fortfarande laddas upp, ändras och tas bort i ström
- Flödet i Power autoautomatisera kan fortfarande skapas, ändras, tas bort och fortsätter att köras (de kommer inte att fungera om de behövs för att skicka ett meddelande till en kanal i det arkiverade teamet)

## <a name="forms"></a>Formulär

Ett formulär kan flyttas från ett enskilt konto till en grupp, det går inte att flytta eller kopiera det från en grupp till en annan. Det finns tre tillgängliga alternativ för ett formulär när ett team tas bort.

**Duplicera formuläret**

Formulär kan [delas som mallar](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f), så att andra kan kopiera det till sitt eget konto eller en grupp. Detta bibehåller inte data från resultaten. endast formulär struktur, till exempel frågor och inställningar.

**Exportera resultat till ett kalkyl blad**

Om data för formulär Svaren måste finnas kvar kan du göra det genom [att exportera resultaten till ett Excel-kalkylblad](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af). Detta exporterar bara frågorna och deras svar som data-det inkluderar inte diagram som skapats med formulär.


**Ta bort formuläret**

När du tar bort gruppen kan du även [ta bort](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) associerade formulär genom att gruppera medlemmar direkt utan att vara ägare till gruppen – det är ett manuellt steg som inte ger någon ytterligare förmån.

## <a name="onenote"></a>OneNote

OneNote-anteckningsboken i en grupp lagras i biblioteket webbplats till gångar på den associerade SharePoint-webbplatsen. Även om du kan sprida filer till bärbara datorer i flera enskilda filer kan de inte helt enkelt kopieras och öppnas oberoende av varandra. I stället måste innehållet i OneNote-anteckningsboken flyttas eller exporteras med OneNote 2016.

**Flytta sidor och avsnitt till en annan antecknings bok**

[Individuellt flytta sidor eller avsnitt till en annan antecknings bok](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) ger ägarna en möjlighet att rensa sina data och bara ta bort det du behöver.

**Exportera hela antecknings boken som ett paket**

Om hela antecknings boken måste sparas med den befintliga strukturen kan den [exporteras som en OneNote-paketfil](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) och sedan importeras till en ny plats. Du kan också använda det här om du vill behålla innehållet i en fil i stället för en befintlig struktur med flera filer.

**Skriva ut till PDF**

I scenarier där en del av innehållet i antecknings boken bara behöver bevaras för referens eller som Arkiv handlingar kan enskilda sidor [skrivas ut till PDF och lagras någon annan stans](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd).

## <a name="mailbox-and-calendar"></a>Post låda och kalender

Det är inte ovanligt att den gruppassocierade post lådan används, även om många konversationer kan ha utförts i team kanalerna. Post lådan lagrar bara e-postmeddelanden som har skickats direkt till den och inkluderar inte e-post som skickades direkt till kanaler.

I vissa fall kan de e-postmeddelanden som lagras i post lådan helt enkelt vara meddelanden om möten, uppdateringar för Planner-uppgifter och andra program eller systemgenererade meddelanden. Det är viktigt att innehållet i post lådan granskas för att avgöra om innehållet ska behållas eller tas bort.

Om en bevarande princip används för Exchange bevaras e-post och Kalender objekt och är tillgängliga via eDiscovery-sökningar.

**Exportera e-post och kalender**

Grupp-eller grupp medlemmar kan [Exportera innehållet i post lådan och kalendern till en PST-fil (Outlook data/privat lagring)](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91). Denna fil kan lagras någon annan stans, eller så kan innehållet importeras till en annan post låda. Den förra rekommenderas inte eftersom innehållet i PST-filen inte är sökbar utan att du öppnar det i Outlook, och själva filen kan skadas.

**DET utförda innehålls migrering**

Administratörer kan använda verktyg från tredje part för att migrera e-post och kalender innehåll mellan post lådor utan några åtgärder från användaren. En möjlig lagrings plats kan vara en delad post låda som skapas endast för att fungera som "Arkiv" i innehållet i gruppens post låda.

## <a name="planner"></a>Planner

Varje grupp eller team kan ha flera planer. Det är viktigt under offboarding processen för att säkerställa att varje plan är riktat mot att innehållet behålls. Precis som de andra produkterna finns det flera olika sätt att ta bort innehåll i Planner.

**Exportera planen till ett kalkyl blad**

Om det bara behövs att spara en kopia av planen för Arkiv handlingar, är det enklaste sättet att [Exportera planen till ett Excel-kalkylblad](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a). Det här är en envägs åtgärd, eftersom det inte går att importera abonnemang från ett kalkyl blad.

> [!IMPORTANT]
> Exportera en plan till Excel tar merparten av informationen i planen, men innehåller inte kommentarer, länkar eller filer.

**Kopiera och flytta uppgifter till ett annat abonnemang**

Även om det verkar som en lösning kan enskilda uppgifter bara [kopieras eller flyttas mellan planerna](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) inom samma grupp, vilket negerar fördelarna i om gruppen som är kopplad till planen tas bort.

**Kopiera hela planen**

Det går också att [Kopiera hela abonnemanget](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4). Detta kan dock inte vara till en befintlig grupp eller i samma grupp. Om du kopierar planen skapas en ny grupp. Om du kopierar hela planen tas det också inte med kommentarer, uppgifter, länkar, bifogade filer eller datum.

## <a name="power-automate"></a>Automatisk strömförsörjning

Flöden som har skapats i Power automatisera och kopplade till en grupp eller ett team tillhör inte gruppen, och i stället ägs de av skaparen och delas bara med andra användare och grupper. De påverkas inte om en grupp eller ett team tas bort.

**Ändra ägarskap för flödet**

Om arbets flödet måste fortsätta att fungera kan alla ägare helt enkelt lägga till andra användare eller Microsoft 365-grupper som ägare.

**Exportera flödet**

Om arbets flödet inte behöver fortsätta att fungera men det måste bevaras för att du ska kunna använda den senare, kan det [exporteras som en fil](https://flow.microsoft.com/blog/import-export-bap-packages/) och importeras igen.

## <a name="power-bi"></a>Power BI

Power BI-data och-arbets ytor kan fungera oberoende av grupper och team och som andra arbets belastningar ger olika sätt att offboarded.

**Kopiera rapporter till en annan arbets yta**

Om rapporten måste bevaras i sitt funktions tillstånd bortom gruppens eller teamets giltighets tid kan den [kopieras från den befintliga arbets ytan till en annan arbets yta i Power BI](https://docs.microsoft.com/power-bi/connect-data/service-datasets-copy-reports).

**Exportera data från en instrument panel eller rapport**

Om rapporten inte längre behöver vara aktiv, men data måste bevaras kan de [exporteras till Excel](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).

## <a name="project"></a>Project

Projekt och översikter som har skapats i Project på webben kan kopplas till Microsoft 365-grupper och ger råd för offboarding liknande Power BI.

**Tilldela projektet till en annan grupp**

Om projektet måste bevaras i sitt funktions tillstånd bortom gruppens eller teamets giltighets tid kan den [tilldelas till en annan Microsoft 365-grupp](https://docs.microsoft.com/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) i administrations centret för Dynamics 365.

**Exportera data från projektet eller översikten**

Att använda administrations centret för Dynamics 365 är att [Exportera användar data från projektet](https://docs.microsoft.com/project-for-the-web/export-user-data-from-project-for-the-web) till ett kalkyl blad, eller om du använder ett PowerShell-skript kan data exporteras till projekt fil (. MPP) och XML-filformat.

## <a name="sharepoint"></a>SharePoint
Alla filer i team kanaler lagras i dokument biblioteket på SharePoint-webbplatsen för den associerade gruppen. I vissa fall kan andra delar än dokument finnas i SharePoint, till exempel listor och sidor.
Filer lagras vanligt vis på tre primära platser på en SharePoint-webbplats:

- Sidor-bibliotek för webbplats sidor
- Bilder som används på sidor – bibliotek för webbplats till gångar
- Filer i kanaler – dokument bibliotek
- Wiki-sidor – wiki-Databibliotek

Om webbplatsen innehåller en eller flera under webbplatser måste processen offboarding upprepas för varje under webbplats. Om teamet innehåller privata kanaler finns det en separat SharePoint-webbplats för varje kanal.

Det är viktigt att du tar bort filer från en grupp eller ett team för att betrakta att de kan delas med användare som inte är medlemmar i gruppen eller teamet (oavsett om det är en intern eller extern organisation), och till exempel att det kan vara lämpligt att meddela dem.

**Ladda ned filer**

När det gäller filer som lagras i SharePoint i ett av de bibliotek som nämns ovan kan de [hämtas till en lokal dator](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05).

**Flytta filer**

Dessutom kan filer flyttas till en annan plats i SharePoint, till exempel ett bibliotek på en annan webbplats.
Entitetsreferens https://support.office.com/en-us/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc

**Exportera lista** Data som lagras i SharePoint-listor kan [exporteras till ett Excel-kalkylblad](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)och importeras till en lista på en annan webbplats.

Alternativt kan du använda ett verktyg från tredje part för att migrera listan mellan webbplatser för att behålla funktionen, listvyer, formatering och andra attribut.

**"Exportera" wiki-filer**

Wiki-innehåll i grupp kanaler lagras i en HTML-formaterad fil i ett dedikerat bibliotek på den associerade SharePoint-webbplatsen. De kan inte enkelt exporteras och importeras till en annan kanal-wiki men kan konverteras till en HTML-fil och öppnas som en webb sida.

## <a name="microsoft-stream"></a>Microsoft Stream

På samma sätt som Power automatisering är det videoklipp som är kopplat till en grupp eller ett team som inte ägs av gruppen och inte tas bort när gruppen tas bort. Videor i strömmen ägs av den person som laddade upp eller skapade videon, även om de lägger till användare eller grupper som ägare. Detta gäller även för möten som registrerats i en Teams-kanal; de ägs av personen som startade inspelningen.

**Lägga till andra ägare**

Eftersom videon behålls i ström, oavsett grupp borttagning, kan den ursprungliga ägaren [dela videon med andra användare och grupper, även lägga till dem som ägare](https://docs.microsoft.com/stream/portal-edit-video).

**Ladda ner videon**

I scenarier där videon inte behöver bevaras i ström eller måste lagras på en alternativ plats, till exempel ett system för hantering av Arkiv handlingar, kan en ägare [Ladda ner den lokalt](https://docs.microsoft.com/stream/portal-download-video)

## <a name="yammer"></a>Yammer

Till skillnad från konversationer i Microsoft Teams erbjuder Yammer både användare och administratörer för att flytta eller exportera konversationer.

**Flytta konversationer till en annan grupp eller community**

Konversationer kan flyttas till en annan Yammer-grupp av en användare, inte bara ägare eller administratörer. Det är möjligt både i den [klassiska Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872)och i de [nya Yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) -gränssnitten.

**Exportera nätverks data**

Yammer-administratörer kan utföra en [export av nätverks data](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data), men då kommer alla konversationer för hela nätverket att exporteras. I den resulterande exporten visas emellertid grupp-ID: t, så det är möjligt att filtrera konversationer baserat på det här.
