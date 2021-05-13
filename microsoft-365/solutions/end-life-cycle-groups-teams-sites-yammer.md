---
title: Livscykelalternativ för grupper, team och Yammer
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
description: Livscykelalternativ för grupper, team och Yammer.
ms.openlocfilehash: 468f41df747b6cf12d3f6619d79cb97248eba1d1
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346432"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>Livscykelalternativ för grupper, team och Yammer

Microsoft 365 Grupper och Microsoft Teams fungerar med flera anslutna tjänster. När en grupp eller ett team tas bort, tas även större delen av informationen i de anslutna tjänsterna bort. I den här artikeln beskrivs alternativ för att behålla information genom att flytta den från gruppen eller gruppen före borttagningen.

En vanlig metod för grupper som inte längre behövs är att flytta filerna från gruppen och arkivera dem på en annan plats, till exempel en SharePoint ett dokumentbibliotek. Den här övningen baseras på ett äldre sätt att arbeta där information lagras i filer och mappar, och kommunikation sker via e-post.

I följande tabell beskrivs de tjänster som är kopplade till grupper och team och viktiga typer av innehåll som finns i var och en av dem:

|Tjänst|Typer av innehåll|
|:------|:---------------|
|Teams|Kanalkonversationer, filer i kanaler|
|Forms|Undersökningsstruktur och undersökningsresultat|
|OneNote|Anteckningsbok|
|Outlook|E-post och kalender|
|Planner|Project status och uppgiftsinformation|
|Power Automate|Arbetsflöden|
|Power BI|Data, rapporter och instrumentpaneler|
|Project på webben|Project abonnemang|
|Översikt|Översikter|
|SharePoint|Filer, listor Teams wiki-data|
|Stream|Videor|
|Yammer|Konversationer|

När du tar bort en grupp eller ett team tas även de flesta av de associerade resurserna bort. Undantagen omfattar:

- Videor i Stream finns kvar och ägs av den person som har laddat upp/spelat in dem
- Flöden Power Automate finns kvar och ägs av den person som skapade dem.
- Project data i och översikt Project data på webben finns kvar i CDS och kan återställas separat.

Grupper och team har en mjuk borttagning i 30 dagar och kan återställas när som helst. Men efter de 30 dagarna rensas de och alla associerade resurser, till exempel tjänster och innehåll, från Microsoft 365 miljön. Allt innehåll som skyddas av en bevarandeprincip förblir tillgängligt via eDiscovery-sökningar.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>Överväganden vid slutet av livscykeln för gruppanslutna tjänster

Det finns tre viktiga områden som grupp- och gruppägare och IT-administratörer måste tänka på när en grupp eller ett team tas bort.

**Content**

Måste innehållet behållas när teamet inte längre finns där? Är det tillräckligt att förlita sig på bevarandefunktioner i Microsoft 365, eller är det en del av innehållet i program och tjänster som inte erbjuder bevarande? Måste innehållet behållas för arkivering, arkivering eller framtida användning och referenssyfte?

För att undvika eventuell dataförlust måste du ställa de här frågorna innan ett team arkiveras eller tas bort.

**Tjänster**

Måste innehållet vara i det aktuella arbetsformuläret? Måste rapporten Power BI vara tillgänglig? Måste formulärresultatet vara tillgängligt i den visuella sammanfattningsvyn? Är listorna i SharePoint länkade till eller inbäddade var som helst?

Dessa frågor måste ställas innan den underliggande gruppen tas bort eftersom det inte är tillräckligt att exportera innehållet.

**Gäster**

När gäster bjuds in till ett team skapas ett gästkonto i värdorganisationens Azure Active Directory lägger till dem i teamet. När ett team tas bort tas gäster inte bort från Azure Active Directory. Även om gäster inte kan komma åt grupper, webbplatser, team eller innehåll som inte har delats med dem, kan de fortfarande använda funktioner i Microsoft Teams som att starta chattar, röst- och videosamtal och använda appar.

En team- eller gruppägare kan bjuda in någon utanför organisationen till att bli gäst i Azure Active Directory genom att lägga till dem i ett team. Teamägare kan däremot inte ta bort gästen från Azure Active Directory. Borttagning av konton kan endast utföras av en global administratör eller användaradministratör.

Det är viktigt att utföra gästgranskningar och att förstå om gäster behöver tas bort från Azure Active Directory vid teamborttagning. Det kan finnas ett giltigt ärende för gäster som ska stanna kvar i katalogen, till exempel vara medlem i andra team eller använda andra Microsoft 365 eller Azure-tjänster.

## <a name="teams"></a>Teams

Teams innehåll främst i form av konversationer.

Konversationer i kanaler kan inte kopieras eller flyttas med hjälp av ursprungliga Microsoft Teams funktioner. De kan däremot exporteras med hjälp av Graph API.

Om en bevarandeprincip tillämpas på alla Teams, behålls konversationerna och är tillgängliga via eDiscovery-sökningar. Med hjälp av avancerad eDiscovery kan du [återskapa Teams en chattkonversation](/microsoft-365/compliance/conversation-review-sets).


### <a name="archiving-a-team"></a>Arkivera ett team

Fördelen med [att arkivera ett team](/microsoftteams/archive-or-delete-a-team) är att det ger fullständig åtkomst till teamet som det var. Användare kan fortfarande bläddra i kanalkonversationer och öppna filer även om de inte är aktiva. Grupper kan dessutom inte arkiveras om de behöver fortsätta arbeta med dem (till exempel om ett projekt utökas).

När ett team arkiveras av en ägare är det inställt på skrivskyddat för medlemmar både för innehåll i teamet och, om det väljs, den associerade SharePoint webbplatsen. Syftet med den här åtgärden är att säkerställa att konversationer i kanaler bevaras i deras befintliga tillstånd, tillsammans med SharePoint-baserat innehåll som filer och wiki-flikar.

På SharePoint webbplats finns inga synliga ändringar. Det går dock inte att göra några ändringar i filer eller listor eftersom SharePoint-behörigheterna för Microsoft 365-gruppen är inställda **på Webbplatsbesökare.** Det omfattar OneNote anteckningsboken för gruppen, som lagras i biblioteket Webbplatstillgångar på den SharePoint webbplatsen.

När ett team arkiveras omfattas den underliggande Microsoft 365-gruppen fortfarande av förfalloprincipen (om denna anges), och ägaren måste därför fortsätta att förnya teamet.

Även om teamets kanalkonversationer och webbplatsinnehåll SharePoint är skrivskyddade tillämpas inte samma sak på andra associerade tjänster:

- Planner-buckets och uppgifter kan fortfarande skapas, ändras och tas bort.
- Formulär kan fortfarande ta emot inlämningar.
- Postlådan Outlook fortfarande ta emot e-postmeddelanden.
- Power BI instrumentpaneler, rapporter och data kan fortfarande ändras.
- Projekt och översikter kan fortfarande redigeras i Project på webben.
- Videor kan fortfarande laddas upp, ändras och tas bort i Stream.
- Flöden Power Automate fortfarande skapas, ändras, tas bort och fortsätter att köras. (De kommer att misslyckas men om det krävs för att publicera ett meddelande till en kanal för det arkiverade teamet.)

## <a name="forms"></a>Forms

Även om ett formulär kan flyttas från ett enskilt konto till en grupp kan det inte flyttas eller kopieras från en grupp till en annan. Det finns tre alternativ för formulär när ett team tas bort.

**Duplicera formuläret**

Formulär kan delas [som mallar,](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)så att andra användare kan kopiera dem till sina egna konton eller grupper. Detta behåller inte data från resultat som har lämnats in. endast formulärstruktur, till exempel frågor och inställningar.

**Exportera resultat till ett kalkylblad**

Om data för formulärsvaren måste behållas kan detta uppnås genom att exportera resultatet till ett [Excel kalkylblad.](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af) Frågorna och svaren exporteras då bara som data, och diagram som skapats med Forms ingår inte.

**Ta bort formuläret**

Även om borttagningen av gruppen också leder till att [](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) alla associerade formulär tas bort kan gruppmedlemmarna ta bort dem direkt utan att vara ägare till gruppen. Det här är dock ett manuellt steg som inte ger några ytterligare fördelar.

## <a name="onenote"></a>OneNote

Den OneNote anteckningsboken som ingår i en grupp lagras i biblioteket Webbplatstillgångar på den associerade SharePoint webbplatsen. Även om filer i anteckningsböcker ibland kan spridas över flera enskilda filer kan de inte kopieras och öppnas oberoende av varandra. Innehållet i anteckningsboken i OneNote måste flyttas eller exporteras med hjälp OneNote 2016.

**Flytta sidor och avsnitt till en annan anteckningsbok**

[Individuellt flytta sidor eller avsnitt till en annan](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) anteckningsbok ger ägare möjlighet att rensa sina data och bara ta med det som behöver behållas.

**Exportera hela anteckningsboken som ett paket**

Om hela anteckningsboken måste behållas med sin befintliga struktur kan den exporteras som en [OneNote-paketfil](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) och sedan importeras till en ny plats. I stället kan den användas som metod för att behålla innehållet i en enda fil i stället för den befintliga flerfilsstrukturen.

**Skriv ut till PDF**

I scenarier där en del av innehållet i anteckningsboken bara behöver behållas för referens eller som poster, kan enskilda sidor skrivas ut till PDF och [lagras någon annanstans.](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)

## <a name="mailbox-and-calendar"></a>Postlåda och kalender

Det är inte ovanligt att den grupp-associerade postlådan används, även om många konversationer har gjorts i teamkanaler. I postlådan lagras endast e-postmeddelanden som har skickats direkt till den och inte innehåller e-postmeddelanden som skickats direkt till kanaler.

I vissa fall kan e-postmeddelandena som lagras i postlådan vara meddelanden om möten, Planner-uppgiftsuppdateringar och andra app- eller systemgenererade meddelanden. Det är viktigt att innehållet i postlådan granskas för att avgöra om innehållet ska behållas eller tas bort.

Om en bevarandeprincip tillämpas i Exchange, behålls e-postmeddelanden och kalenderobjekt och är tillgängliga via eDiscovery-sökningar.

**Exportera e-post och kalender**

Grupp- eller gruppmedlemmar kan exportera innehållet i postlådan och kalendern till en [Outlook data-/Storage-fil (PST).](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91) Filen kan sedan lagras någon annanstans eller så kan innehållet importeras till en annan postlåda. Det förra rekommenderas inte eftersom innehållet i PST-filen inte är sökbart utan att öppna den i Outlook, och själva filen kan skadas med tiden.

**Innehållsmigrering utfördes av IT-utförd**

Administratörer kan använda verktyg från tredje part för att migrera e-post- och kalenderinnehåll mellan postlådor utan åtgärder från användare. En möjlig lagringsplats kan vara en delad postlåda som skapats enbart för att fungera som "arkiv" av gruppens postlådeinnehåll.

## <a name="planner"></a>Planner

Varje grupp eller team kan ha flera planer. Det är viktigt under processen med off-boarding att se till att bevarandekraven hanteras för varje plan. Precis som för de andra tjänsterna finns det flera olika metoder för off-board-innehåll i Planner.

**Exportera planen till ett kalkylblad**

Om det bara krävs att ha en kopia av planen för arkiveringsändamål är det enklast att exportera planen till ett [Excel kalkylblad.](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a) Det här är en envägsåtgärd – det finns inget alternativ för att importera planer från ett kalkylblad.

> [!IMPORTANT]
> Export av en plan Excel tar upp den mesta informationen i planen, men inkluderar inte kommentarer, länkar eller filer.

**Kopiera och flytta aktiviteter till en annan plan**

När du kopierar eller flyttar uppgifter till en annan plan verkar det som en lösning, men enskilda aktiviteter kan bara kopieras eller [flyttas mellan planer](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) inom samma grupp. Då backas inte data upp om gruppen som är kopplad till planen tas bort.

**Kopiera hela planen**

Du kan också kopiera [hela planen.](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4) Kopiering kan inte göras till en befintlig grupp. När planen kopieras skapas en ny grupp. När du dessutom kopierar hela planen inkluderas inte kommentarer, tilldelningar, länkar, bifogade filer eller datum.

## <a name="power-automate"></a>Power Automate

Flöden som Power Automate och som är kopplade till en grupp eller ett team tillhör inte gruppen. De ägs av skaparen och delas bara med andra användare och grupper. De påverkas därför inte om en grupp eller ett team tas bort.

**Ändra ägarskap för flödet**

Om flödet behöver fortsätta fungera kan alla ägare lägga till andra användare eller Microsoft 365 grupper som ägare.

**Exportera flödet**

Om flödet inte behöver fortsätta fungera, men det måste bevaras för potentiell [](https://flow.microsoft.com/blog/import-export-bap-packages/) framtida användning, kan det exporteras som en fil och importeras igen senare.

## <a name="power-bi"></a>Power BI

Power BI data och arbetsytor kan fungera oberoende av grupper och grupper och liksom andra arbetsbelastningar erbjuder olika sätt att bli off-boarded.

**Kopiera rapporter till en annan arbetsyta**

Om du behöver rapporten när gruppen eller teamet har tagits bort kan den kopieras från den befintliga arbetsytan till en annan arbetsyta [i Power BI](/power-bi/connect-data/service-datasets-copy-reports).

**Exportera data från en instrumentpanel eller rapport**

Om rapporten inte längre behöver vara aktiv men data måste behållas kan den istället exporteras till en [Excel.](/power-bi/visuals/power-bi-visualization-export-data)

## <a name="project"></a>Project

Projekt och översikter som Project för webben är kopplade till Microsoft 365 grupper och har en liknande off-boarding som Power BI.

**Tilldela projektet till en annan grupp**

Om projektet behöver bevaras i dess funktionella tillstånd utöver gruppens livscykel kan det tilldelas till en annan [Microsoft 365 grupp.](/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) Det kan du göra med Dynamics 365 Administrationscenter.

**Exportera data från projektet eller översikten**

Med Dynamics 365 Administrationscenter är det möjligt att exportera [användardata från projektet till](/project-for-the-web/export-user-data-from-project-for-the-web) ett kalkylblad. Data kan också exporteras till en Project (. MPP) och XML-filformat genom att använda PowerShell.

## <a name="sharepoint"></a>SharePoint

Alla filer i teamkanaler lagras på den SharePoint webbplatsen för den associerade gruppen. I vissa fall kan annat innehåll än dokument finnas i SharePoint, till exempel listor eller sidor.

Filer lagras vanligen på tre primära platser på en SharePoint webbplats:

- Sidor – biblioteket Webbplatssidor
- Bilder som används på sidor – biblioteket Webbplatstillgångar
- Filer i kanaler – biblioteket Dokument
- Wiki-sidor – Teams wiki-databibliotek

Om webbplatsen har en eller flera underwebbplatser måste processen för off-boarding upprepas för varje underwebbplats. Om teamet innehåller privata kanaler finns det en separat SharePoint för varje kanal.

När du tar bort filer från en grupp eller ett team är det viktigt att tänka på att de kan delas med användare som inte är medlemmar i gruppen eller teamet. Du kanske vill meddela den väntande ändringen till dem.

**Ladda ned filer**

Filer som lagras SharePoint i ett av biblioteken som nämns ovan kan [laddas ned till en lokal dator.](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)

**Flytta filer**

Dessutom kan filer flyttas till [en annan plats inom SharePoint till exempel ett bibliotek på en annan webbplats.](https://support.office.com/article/00e2f483-4df3-46be-a861-1f5f0c1a87bc)

**Exportera lista**

Data som lagras SharePoint listor kan exporteras till ett [kalkylblad Excel och](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)importeras igen till en lista på en annan webbplats.

Alternativt kan ett verktyg från tredje part användas för att migrera listan mellan webbplatser för att behålla funktioner, listvyer, formatering och andra attribut.

**"Exportera" wiki-filer**

Wiki-innehåll i teamkanaler lagras i en HTML-formaterad fil i ett dedikerat bibliotek med tillhörande SharePoint webbplats. De kan inte enkelt exporteras och importeras till en annan kanal wiki men kan konverteras till en HTML-fil och öppnas som en webbsida.

## <a name="microsoft-stream"></a>Microsoft Stream

Precis Power Automate videor i Stream som är kopplade till en grupp eller ett team faktiskt inte ägs av gruppen och tas inte bort när gruppen tas bort. Videor i Stream ägs av den person som har laddat upp eller skapat videon, även om de lägger till användare eller grupper som ägare. Möten som spelas in Teams en kanal ägs av den person som startade inspelningen.

**Lägga till andra ägare**

Eftersom videon behålls i Stream när gruppen tas bort kan den ursprungliga ägaren dela videon med andra användare och grupper, och även lägga till [dem som ägare.](/stream/portal-edit-video)

**Ladda ned videon**

I scenarier där videon inte behöver behållas i Stream eller behöver lagras på en annan plats, till exempel ett system för hantering av arkivhandlingar, kan en ägare ladda ned [den lokalt.](/stream/portal-download-video)

## <a name="yammer"></a>Yammer

Till skillnad från konversationer i Microsoft Teams har Yammer alternativ för att flytta eller exportera konversationer både för användare och administratörer.

**Flytta konversationer till en annan grupp eller community**

Konversationer kan flyttas till en Yammer grupp av alla användare, inte bara ägare eller administratörer. Det går i både den [klassiska versionen Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872) de nya [Yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) gränssnitten.

**Exportera nätverksdata**

Yammer nätverksadministratörer [exporterar nätverksdata](/yammer/manage-security-and-compliance/export-yammer-enterprise-data). Om du gör det exporteras emellertid alla konversationer för hela nätverket. Den resulterande exporten innehåller grupp-ID. Det går att filtrera konversationer baserat på detta ID.
