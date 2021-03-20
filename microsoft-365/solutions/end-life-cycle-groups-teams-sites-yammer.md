---
title: Alternativ för slutet av livscykeln för grupper, team och Yammer
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
description: Alternativ för slutet av livscykeln för grupper, team och Yammer.
ms.openlocfilehash: 405d87c645118cf0ef318d4d68802d17da8c5673
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916136"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>Alternativ för slutet av livscykeln för grupper, team och Yammer

Microsoft 365 Grupper och Microsoft Teams fungerar med en mängd olika anslutna tjänster. När en grupp eller ett team tas bort, tas även större delen av informationen i de anslutna tjänsterna bort. I den här artikeln beskrivs alternativ för att behålla information genom att flytta den från gruppen eller gruppen innan du tar bort den.

En vanlig metod för grupper som inte längre behövs är att flytta filerna från gruppen och lagra dem på en annan plats, till exempel ett SharePoint-dokumentbibliotek som fungerar som en lagringsplats eller ett arkiv. Den här övningen baseras på ett äldre sätt att arbeta där information lagras i filer och mappar, och kommunikation sker via e-post.

I följande tabell beskrivs de tjänster som är kopplade till grupper och team och viktiga typer av innehåll som finns i var och en av dem:

|Tjänst|Typer av innehåll|
|:------|:---------------|
|Teams|Kanalkonversationer, filer i kanaler|
|Formulär|Undersökningsstruktur och undersökningsresultat|
|OneNote|Anteckningsbok|
|Outlook|E-post och kalender|
|Planner|Projektstatus och aktivitetsinformation|
|Power Automate|Arbetsflöden|
|Power BI|Data, rapporter och instrumentpaneler|
|Project på webben|Projektplaner|
|Översikt|Översikter|
|SharePoint|Filer, listor, Wiki-data för Teams-kanal|
|Strömma|Videor|
|Yammer|Konversationer|

När du tar bort en grupp eller ett team tas även de flesta av de associerade resurserna bort. Några av undantagen är videor i Stream– de finns kvar och ägs fortfarande av den person som har laddat upp/spelat in dem, på samma sätt som flöden i Power Automate. Project- och översiktsdata i Project på webben finns kvar i CDS och kan återställas separat.

Grupper och team har en mjuk borttagning i 30 dagar och kan återställas när som helst. Men efter de 30 dagarna tas de, och alla associerade resurser som tjänster och innehåll, helt bort från Microsoft 365-miljön. Allt innehåll som skyddas av en bevarandeprincip förblir tillgängligt via eDiscovery-sökningar.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>Överväganden vid slutet av livscykeln för gruppanslutna tjänster

Det finns tre viktiga områden som grupp- och gruppägare och IT-administratörer måste tänka på när en grupp eller ett team tas bort.

**Content**

Måste innehållet behållas när teamet inte längre fungerar eller finns kvar? Är det tillräckligt att förlita sig på bevarandefunktioner i Microsoft 365, eller är det en del av innehållet i program och tjänster som inte erbjuder bevarande? Måste innehållet behållas i arkiveringssyfte, i arkiveringssyfte eller i framtida användnings- och referenssyfte?

Dessa frågor måste ställas innan ett team arkiveras eller tas bort för att undvika eventuell dataförlust.

**Tjänster**

Måste innehållet, utöver innehållet i olika appar och tjänster, vara kvar i sina aktuella arbetsformulär? Måste till exempel Power BI-rapporten fortsätta vara tillgänglig, måste formulärresultaten vara tillgängliga i den visuella sammanfattningsvyn, är listorna i SharePoint länkade till eller inbäddade var som helst?

I likhet med innehållsöverväganden måste du ställa de här frågorna innan den underliggande gruppen tas bort eftersom det kanske inte är tillräckligt att bara exportera innehållet.

**Gäster**

När gäster bjuds in till ett team skapar arbetsflödet deras identitet i värdorganisationens Azure Active Directory innan de läggs till i teamet. När ett team tas bort tas gäster inte bort från Azure Active Directory och finns som sådana fortfarande i Microsoft Teams-miljön. Även om gäster inte kan komma åt grupper, webbplatser, team eller innehåll som inte har delats med dem, kan de fortfarande använda funktioner i Microsoft Teams, som att initiera chattar, röst- och videosamtal och använda appar.

En team- eller gruppägare kan bjuda in en extern användare till att bli gäst i Azure Active Directory, lägga till dem i teamet och ta bort dem från teamet. En teamägare kan dock inte ta bort gästen från Azure Active Directory – det kan endast utföras av en global administratör eller användaradministratör.

Därför är det viktigt att utföra gästgranskningar och att förstå om gäster behöver tas bort från Azure Active Directory vid teamborttagning. Det kan finnas ett giltigt fall för gäster att bli kvar i katalogen, till exempel vara medlem i ett eller flera andra team eller använda andra Microsoft 365- eller Azure-tjänster.

## <a name="teams"></a>Teams

Teams-specifikt innehåll består främst av konversationer.

Konversationer i kanaler kan inte kopieras eller flyttas med hjälp av ursprungliga Microsoft Teams-funktioner. De kan däremot exporteras med hjälp av Graph API.

Om en bevarandeprincip tillämpas på Teams behålls konversationerna och är tillgängliga via eDiscovery-sökningar. (Objekt som hittades i eDiscovery-sökningar kan exporteras, men det finns inget sammanhang eller någon struktur från den ursprungliga källan – de är bara enskilda meddelanden.)

### <a name="archiving-a-team"></a>Arkivera ett team

Fördelen med att arkivera ett [team](/microsoftteams/archive-or-delete-a-team) är att det ger fullständig åtkomst till teamet som det var, så att användarna fortfarande kan bläddra i kanalkonversationer och öppna filer även om de inte är aktiva. Dessutom kan grupper vara oskadliga om det finns ett behov av att fortsätta arbeta med dem (t.ex. i händelse av ett projekttillägg).

När ett team arkiveras av en ägare är det inställt på skrivskyddat för medlemmar både för innehåll inom gruppen och för den associerade SharePoint-webbplatsen, om det är markerat. Syftet med den här åtgärden är att se till att konversationer i kanaler bevaras i deras befintliga tillstånd, tillsammans med SharePoint-baserat innehåll som filer och wiki-flikar.

På SharePoint-webbplatsen finns det inga synliga ändringar, men inga ändringar kan göras i filer eller listor som den SharePoint-baserade behörighetsgruppen för Microsoft 365-gruppen är inställd på nivån Webbplatsbesökare. Det inkluderar gruppens OneNote-anteckningsbok eftersom den lagras i biblioteket Webbplatstillgångar på SharePoint-webbplatsen.

När ett team arkiveras omfattas den underliggande Microsoft 365-gruppen fortfarande av förfalloprincipen (om sådan finns) och ägaren måste därför fortsätta att förnya teamet.

Även om teamets kanalkonversationer och SharePoint-webbplatsinnehåll är skrivskyddade tillämpas inte samma sak på andra associerade tjänster:

- Planner-buckets och -uppgifter kan fortfarande skapas, ändras och tas bort
- Formulär kan fortfarande ta emot inlämningar
- Outlook-postlådan kan fortfarande ta emot e-postmeddelanden
- Instrumentpaneler, rapporter och data i Power BI kan fortfarande ändras
- Projekt och översikter kan fortfarande redigeras i Project på webben
- Videor kan fortfarande laddas upp, ändras och tas bort i Stream
- Flöden i Power Automate kan fortfarande skapas, ändras, tas bort och fortsätta köras (de kommer att misslyckas om de behövs för att publicera ett meddelande på en kanal för det arkiverade teamet)

## <a name="forms"></a>Formulär

Även om ett formulär kan flyttas från ett enskilt konto till en grupp kan det inte flyttas eller kopieras från en grupp till en annan. Det finns tre alternativ för formulär när ett team tas bort.

**Duplicera formuläret**

Formulär kan delas [som mallar,](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)så att andra användare kan kopiera dem till sina egna konton eller grupper. Detta behåller inte data från resultat som har lämnats in. endast formulärstruktur, till exempel frågor och inställningar.

**Exportera resultat till ett kalkylblad**

Om data för formulärsvaren måste behållas kan detta uppnås genom att [exportera resultaten till ett Excel-kalkylblad.](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af) Frågorna och svaren exporteras då bara som data, utan diagram som skapats med Forms.


**Ta bort formuläret**

Även om borttagningen av gruppen också leder till att [](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) alla associerade formulär tas bort kan gruppmedlemmarna ta bort dem direkt utan att vara ägare till gruppen – men det här är ett manuellt steg som inte ger några ytterligare fördelar.

## <a name="onenote"></a>OneNote

OneNote-anteckningsboken som ingår i en grupp lagras i biblioteket Webbplatstillgångar på den associerade SharePoint-webbplatsen. Även om filer i anteckningsböcker ibland kan spridas över flera enskilda filer kan de inte bara kopieras och öppnas oberoende av varandra. I stället måste innehållet i OneNote-anteckningsboken flyttas eller exporteras med hjälp av OneNote 2016.

**Flytta sidor och avsnitt till en annan anteckningsbok**

[Individuellt flytta sidor eller avsnitt till en annan](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) anteckningsbok ger ägare möjlighet att rensa sina data och bara ta med det som behöver behållas.

**Exportera hela anteckningsboken som ett paket**

Om hela anteckningsboken måste behållas med den befintliga strukturen kan den exporteras som en [OneNote-paketfil](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) och sedan importeras till en ny plats. Alternativt kan det här användas som en metod för att behålla innehållet i en enda fil i stället för den befintliga flerfilsstrukturen.

**Skriv ut till PDF**

I scenarier där en del av innehållet i anteckningsboken bara behöver behållas för referens eller som poster, kan enskilda sidor skrivas ut till PDF och [lagras någon annanstans.](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)

## <a name="mailbox-and-calendar"></a>Postlåda och kalender

Det är inte ovanligt att den grupp-associerade postlådan används, även om många konversationer har gjorts i teamkanaler. Postlådan lagrar bara e-postmeddelanden som skickats direkt till den och inkluderar inte e-postmeddelanden som skickats direkt till kanaler.

I vissa fall kan e-postmeddelandena som lagras i postlådan vara meddelanden om möten, Planner-uppgiftsuppdateringar och andra app- eller systemgenererade meddelanden. Det är viktigt att innehållet i postlådan granskas för att avgöra om innehållet ska behållas eller tas bort.

Om en bevarandeprincip tillämpas på Exchange behålls e-postmeddelanden och kalenderobjekt och är tillgängliga via eDiscovery-sökningar.

**Exportera e-post och kalender**

Grupp- eller gruppmedlemmar kan exportera innehållet i postlådan och kalendern till [en Outlook-fil med data/personlig lagring (PST).](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91) Filen kan sedan lagras någon annanstans eller så kan innehållet importeras till en annan postlåda. Den förra filen rekommenderas inte eftersom innehållet i PST-filen inte är sökbart utan att öppna den i Outlook och själva filen kan skadas med tiden.

**Innehållsmigrering utfördes av IT-utförd**

Administratörer kan använda verktyg från tredje part för att migrera e-post- och kalenderinnehåll mellan postlådor utan åtgärder från användare. En möjlig lagringsplats kan vara en delad postlåda som skapats enbart för att fungera som "arkiv" av gruppens postlådeinnehåll.

## <a name="planner"></a>Planner

Varje grupp eller team kan ha flera planer. Under offboarding-processen är det viktigt att se till att varje plan tar upp huruvida dess innehåll ska behållas. Precis som för de andra produkterna finns det flera olika metoder för offboard-innehåll i Planner.

**Exportera planen till ett kalkylblad**

Om det bara krävs att ha en kopia av planen för registrering är det enklaste sättet att exportera planen till [ett Excel-kalkylblad.](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a) Det här är en envägsåtgärd eftersom det inte finns något alternativ för att importera planer från ett kalkylblad.

> [!IMPORTANT]
> Export av en plan till Excel tar den mesta informationen inom planen, men kommer inte att innehålla kommentarer, länkar eller filer.

**Kopiera och flytta aktiviteter till en annan plan**

Även om detta verkar vara en [](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) lösning kan enskilda aktiviteter bara kopieras eller flyttas mellan planer inom samma grupp, vilket negerar förmånen om gruppen som är kopplad till planen tas bort.

**Kopiera hela planen**

Det går även att [kopiera hela planen.](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4) Detta kan dock inte gäller för en befintlig grupp eller ens inom samma grupp. När planen kopieras skapas en ny grupp. När du dessutom kopierar hela planen inkluderas inte kommentarer, tilldelningar, länkar, bifogade filer eller datum.

## <a name="power-automate"></a>Power Automate

Flöden som skapats i Power Automate och som är kopplade till en grupp eller ett team tillhör inte gruppen och ägs i stället av skaparen och delas inte med andra användare och grupper. De påverkas inte om en grupp eller ett team tas bort.

**Ändra ägarskap för flödet**

Om arbetsflödet måste fortsätta fungera kan alla ägare helt enkelt lägga till andra användare eller Microsoft 365-grupper som ägare.

**Exportera flödet**

Om arbetsflödet inte behöver fortsätta fungera, men det måste bevaras för potentiell framtida användning, kan det exporteras som en fil och [importeras](https://flow.microsoft.com/blog/import-export-bap-packages/) igen senare.

## <a name="power-bi"></a>Power BI

Power BI-data och -arbetsytor kan fungera oberoende av grupper och grupper och liksom andra arbetsbelastningar erbjuder olika sätt att bli offboarded.

**Kopiera rapporter till en annan arbetsyta**

Om rapporten behöver bevaras i dess funktionella tillstånd utöver gruppens eller gruppens livscykel kan den kopieras från den befintliga arbetsytan till en annan arbetsyta [i Power BI.](/power-bi/connect-data/service-datasets-copy-reports)

**Exportera data från en instrumentpanel eller rapport**

Om rapporten inte längre behöver vara aktiv men data måste behållas kan den också exporteras [till Excel.](/power-bi/visuals/power-bi-visualization-export-data)

## <a name="project"></a>Project

Projekt och översikter som skapats i Project på webben kan kopplas till Microsoft 365-grupper och erbjuder metoder för offboarding som liknar Power BI.

**Tilldela projektet till en annan grupp**

Om projektet behöver bevaras i dess funktionella tillstånd utöver gruppens livscykel kan det tilldelas till en annan [Microsoft 365-grupp](/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) med hjälp av Dynamics 365 Administrationscenter.

**Exportera data från projektet eller översikten**

Med dynamics 365 Administrationscenter är det möjligt att exportera [användardata](/project-for-the-web/export-user-data-from-project-for-the-web) från projektet till ett kalkylblad, eller om du använder ett PowerShell-skript kan data exporteras till Project-fil (. MPP) och XML-filformat.

## <a name="sharepoint"></a>SharePoint
Alla filer i teamkanaler lagras i dokumentbiblioteket på SharePoint-webbplatsen för den associerade gruppen. I vissa fall kan annat innehåll än dokument finnas i SharePoint, till exempel listor eller sidor.
Filer lagras vanligen på tre primära platser på en SharePoint-webbplats:

- Sidor – biblioteket Webbplatssidor
- Bilder som används på sidor – biblioteket Webbplatstillgångar
- Filer i kanaler – biblioteket Dokument
- Wiki-sidor – Teams Wiki-databibliotek

Om webbplatsen har en eller flera underwebbplatser som ligger under den måste offboardingprocessen upprepas för varje underwebbplats. Om teamet innehåller privata kanaler finns det en separat SharePoint-webbplats för varje kanal.

När du tar bort filer från en grupp eller ett team är det viktigt att tänka på att de kan delas med användare som inte är medlemmar i gruppen (vare sig interna eller externa i organisationen), och det kan därför vara värt att informera om den väntande ändringen till dem.

**Ladda ned filer**

För filer som lagras i SharePoint i ett av de bibliotek som nämns ovan kan dessa [laddas ned till en lokal dator.](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)

**Flytta filer**

Dessutom kan filer flyttas till en annan plats i SharePoint, till exempel ett bibliotek på en annan webbplats.
Referens: https://support.office.com/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc

**Exportera lista** Data som lagras i SharePoint-listor kan [exporteras till ett Excel-kalkylblad](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)och importeras igen till en lista på en annan webbplats.

Alternativt kan ett verktyg från tredje part användas för att migrera listan mellan webbplatser för att behålla funktioner, listvyer, formatering och andra attribut.

**"Exportera" wiki-filer**

Wiki-innehåll i teamkanaler lagras i en HTML-formaterad fil i ett dedikerat bibliotek på den associerade SharePoint-webbplatsen. De kan inte enkelt exporteras och importeras till en annan kanal wiki men kan konverteras till en HTML-fil och öppnas som en webbsida.

## <a name="microsoft-stream"></a>Microsoft Stream

Precis som Power Automate ägs inte videor i Stream som är kopplade till en grupp eller ett team av gruppen och tas inte bort när gruppen tas bort. Videor i Stream ägs av den person som har laddat upp eller skapat videon, även om de lägger till användare eller grupper som ägare. Detta är även fallet för möten som spelas in i en Teams-kanal. de ägs av den person som startade inspelningen.

**Lägga till andra ägare**

Eftersom videon sparas i Stream oavsett borttagning av grupp, kan den ursprungliga ägaren dela videon med andra användare och grupper, och även lägga till [dem som ägare.](/stream/portal-edit-video)

**Ladda ned videon**

I scenarier där videon inte behöver behållas i Strömmen eller behöver lagras på en annan plats, till exempel ett system för hantering av arkivhandlingar, kan en ägare ladda ned [den lokalt](/stream/portal-download-video)

## <a name="yammer"></a>Yammer

Till skillnad från konversationer i Microsoft Teams erbjuder Yammer både alternativ för användare och administratörer för att flytta eller exportera konversationer.

**Flytta konversationer till en annan grupp eller community**

Alla användare kan flytta konversationer till en annan Yammer-grupp, inte bara ägare eller administratörer. Det här går både i den [klassiska Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872)och i de [nya Yammer-gränssnitten.](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680)

**Exportera nätverksdata**

Nätverksadministratörer i Yammer kan [exportera nätverksdata](/yammer/manage-security-and-compliance/export-yammer-enterprise-data), men om du gör det exporteras alla konversationer för hela nätverket. Den resulterande exporten visar dock grupp-ID:t, så det är möjligt att filtrera konversationer utifrån detta.