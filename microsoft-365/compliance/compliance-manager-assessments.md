---
title: Skapa och hantera utvärderingar i Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Skapa utvärderingar i Microsoft Compliance Manager för att hjälpa dig att uppfylla kraven i bestämmelser och certifieringar som är viktiga för din organisation.
ms.openlocfilehash: 4530f8544834c672b3ae1ebb70625ffe8f2ae4ae
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2021
ms.locfileid: "53148944"
---
# <a name="build-and-manage-assessments-in-compliance-manager"></a>Skapa och hantera utvärderingar i Efterlevnadshanteraren

**I den här artikeln:** Lär dig hur du anpassar Efterlevnadshanteraren för din organisation genom att skapa och hantera **utvärderingar.** Den här artikeln beskriver hur du skapar utvärderingar, organiserar dem i **grupper,** arbetar med **kontroller,** accepterar **uppdateringar** och exporterar **utvärderingsrapporter.**

## <a name="introduction-to-assessments"></a>Introduktion till utvärderingar

Med Efterlevnadshanteraren kan du skapa bedömningar som utvärderar din efterlevnad av bransch- och regionala bestämmelser som gäller för din organisation. Bedömningar bygger på ramverket för utvärderingsmallar, som innehåller de kontroller, förbättringsåtgärder och Microsoft-åtgärder som krävs för att slutföra utvärderingen. Genom att konfigurera de mest relevanta utvärderingarna för din organisation kan du implementera principer och driftsmetoder för att begränsa risken för efterlevnad.

Alla dina utvärderingar visas på fliken Utvärderingar i Efterlevnadshanteraren. Läs mer om [hur du filtrerar vyn över dina utvärderingar och tolkar statustillstånd](compliance-manager-setup.md#assessments-page).

> [!IMPORTANT]
> Vilka mallar som är tillgängliga för din organisation för att skapa bedömningar beror på ditt licensavtal. [Granska licensinformationen](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="data-protection-baseline-default-assessment"></a>Standardutvärdering av dataskyddsbaslinje

Microsoft tillhandahåller en standardutvärdering i **Compliance** Manager för den grundläggande Microsoft 365 du vill **komma igång.** Den här baslinjeutvärderingen har en uppsättning kontroller för viktiga bestämmelser och standarder för dataskydd och allmän datastyrning. Den här baslinjen ritar främst element från NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) och ISO (International Organization for Standardization), samt från FedRAMP (Federal Risk and Authorization Management Program) och GDPR (General Data Protection Regulation of the Eu).

Den här utvärderingen används för att beräkna din ursprungliga efterlevnadspoäng första gången du kommer till Efterlevnadshanteraren innan du konfigurerar andra utvärderingar. Efterlevnadshanteraren samlar in initiala signaler från dina Microsoft 365 lösningar. Du kan direkt se hur organisationen fungerar i förhållande till viktiga standarder och bestämmelser för dataskydd, och se förslag på förbättringsåtgärder att vidta.

Efterlevnadshanteraren blir mer användbar när du skapar och hanterar dina egna utvärderingar för att uppfylla organisationens behov.

## <a name="understand-groups-before-creating-assessments"></a>Förstå grupper innan du skapar utvärderingar

När du skapar en utvärdering måste du tilldela den till en grupp. Grupper är behållare som gör att du kan ordna utvärderingar på ett sätt som är logiskt för dig, till exempel per år eller bestämmelser, eller baserat på din organisations avdelningar eller områden. Därför rekommenderar vi att du planerar en grupperingsstrategi innan du skapar utvärderingar.

Nedan finns exempel på två grupper och deras underliggande utvärderingar:

- **FFIEC IS assessment 2020**
  - FFIEC IS
- **Datasäkerhets- och sekretessutvärderingar**
  - ISO 27001:2013
  - ISO 27018:2014

När två olika utvärderingar i samma grupp delar förbättringsåtgärder som du hanterar kommer alla uppdateringar som du gör i en åtgärds implementeringsinformation eller status automatiskt att synkroniseras i hela gruppen. Med den här synkroniseringen kan du implementera en förbättringsåtgärd och uppfylla flera krav samtidigt.

### <a name="create-a-group"></a>Skapa en grupp

Du kan skapa en grupp när du skapar en ny bedömning. Grupper kan inte skapas som fristående enheter.

### <a name="what-to-know-when-working-with-groups"></a>Vad du ska veta när du arbetar med grupper

- En grupp måste innehålla minst en bedömning.
- Gruppnamn måste vara unika inom organisationen.
- Grupper har inte säkerhetsegenskaper. Alla behörigheter är kopplade till utvärderingar.
- När du har lagt till en bedömning för en grupp kan gruppering inte ändras.
- Om du lägger till en ny utvärdering i en befintlig grupp kopieras vanlig information från utvärderingar i den gruppen till den nya utvärderingen.
- Relaterade utvärderingskontroller i olika utvärderingar inom samma grupp uppdateras automatiskt när de är slutförda.
- När en ändring görs av en förbättring som visas i flera grupper återspeglas den ändringen i alla fall av den förbättringsåtgärden.
- Grupper kan innehålla utvärderingar för samma certifiering eller föreskrifter, men varje grupp kan bara innehålla en utvärdering för ett visst produktcertifieringspar. En grupp kan till exempel inte innehålla två utvärderingar för Office 365 och NIST CSF. En grupp kan innehålla flera utvärderingar för samma produkt endast om motsvarande certifiering eller bestämmelser för var och en är olika.
- Om du tar bort en bedömning bryts relationen mellan utvärderingen och gruppen.
- Grupper kan inte tas bort manuellt.

## <a name="create-assessments"></a>Skapa utvärderingar

> [!NOTE]
> Endast användare som har rollen Global administratör, Efterlevnadshanteraren och Utvärderingshanteraren kan skapa och ändra utvärderingar. Läs mer om [roller och behörigheter.](compliance-manager-setup.md#set-user-permissions-and-assign-roles)

Följ de här anvisningarna om du vill börja skapa utvärderingar.

1. Veta vilken grupp du ska tilldela din utvärdering till eller är redo att skapa en ny för den här utvärderingen.

2. Öppna utvärderingsguiden. Du kan komma åt det här utfällfönstret från en av två platser:
    - Gå till **utvärderingssidan** i Efterlevnadshanteraren och välj **Lägg till bedömning**. eller
    - Leta reda på den mall du vill använda på **fliken Utvärderingsmallar,** visa dess information och välj **Skapa bedömning.** Då fylls guidens mallvalsfält i automatiskt.

3. **Välj en mall:** Om du inte redan har valt en mall i steg 2 väljer du en mall som ska fungera som grund för utvärderingen. Du ser en lista över mallar indelade i kategorierna Ingår och Premium (se [Malltyper](compliance-manager-templates.md#template-availability-and-licensing) för mer information). Välj alternativknappen bredvid den valda mallen och välj sedan **Nästa**.

4. **Namn och grupp:** Ange de här egenskaperna för att identifiera din utvärdering och tilldela den till en grupp.
    - **Namn**: Ange ett namn för utvärderingen i **fältet Utvärderingsnamn.** Utvärderingsnamn måste vara unika i grupper. Om namnet på din utvärdering matchar namnet på en annan bedömning i en viss grupp får du ett felmeddelande där du uppmanas att skapa ett annat namn.
    - **Grupp**: Tilldela din utvärdering till en grupp. Du kan antingen:
        - Välj **Använd befintlig grupp för** att tilldela den till en grupp som du redan har skapat. eller
        - Välj **Skapa ny grupp för** att skapa en ny grupp och tilldela den här utvärderingen till den:
            - Fastställ ett namn på gruppen och ange det i fältet under alternativknappen.
            - Du kan **kopiera data från en befintlig grupp,** till exempel implementerings- och testningsinformation och dokument, genom att markera lämpliga rutor.

    Välj Nästa när du är **klar.**

5. **Granska och slutför:** Den sista skärmen i guiden visar mallen, namnet och gruppen som valts för utvärderingen. Du kan redigera de här inställningarna via länkarna på skärmen, så att du kommer tillbaka till de relevanta stegen i guiden. Välj Skapa utvärdering när du **är klar.**

6. På nästa skärm bekräftar du att du har skapat den nya utvärderingen. Välj **Klar** för att stänga guiden så visas informationssidan för din nya utvärdering på skärmen.

Om du ser en **utvärderingsskärm** som misslyckades när **du har valt Skapa** utvärdering väljer du Försök **igen** för att skapa din utvärdering igen.

Du kan ändra namnet på utvärderingen efter att  du skapat den genom att välja knappen Redigera namn i det övre högra hörnet på [utvärderingssidan.](#monitor-assessment-progress-and-controls)

## <a name="monitor-assessment-progress-and-controls"></a>Övervaka utvärderingsförloppet och kontroller

Varje utvärdering har en informationssida som ger en snabb överblick över dina framsteg när du genomför utvärderingen. På sidan visas förloppet för slutförande av kontroller samt teststatus för viktiga förbättringsåtgärder i kontrollerna.

### <a name="overview-tab"></a>Fliken Översikt

Översiktsfliken innehåller ett diagram som visar hur mycket du vill slutföra utvärderingen i procent. Det här diagrammet innehåller en uppdelning av punkter från åtgärder du äger och poäng från åtgärder som ägs av Microsoft så att du kan se hur många fler poäng du behöver för att slutföra utvärderingen.

De viktigaste förbättringsåtgärderna för kontroller i utvärderingen anges i den ordning de ger störst möjlighet att tjäna poäng. Det associerade diagrammet visar den sammantagna teststatusen för dina förbättringsåtgärder så att du snabbt kan avgöra vad som har testats och vad som fortfarande behöver göras.

Om du vill komma åt enskilda förbättringsåtgärder går **du till fliken** Kontroller eller fliken **Förbättringsåtgärder.**

### <a name="controls-tab"></a>Fliken Kontroller

På fliken kontroller visas detaljerad information om varje kontroll som mappats till utvärderingen. Ett **diagram över kontrollstatus** visar status för kontroller efter familj, så att du snabbt kan se vilka grupper av kontroller som behöver uppmärksammas.

Nedanför diagrammet visas en tabell med detaljerad information om varje kontroll inom utvärderingen. Kontroller är grupperade efter kontrollfamilj. Expandera varje familjenamn och visa de enskilda kontrollerna som finns i den. Informationen som visas för varje kontroll omfattar:

- **Kontrollrubrik**
- **Status:** Återspeglar teststatusen för förbättringsåtgärderna i kontrollen 
    - **Godkänd** – alla förbättringsåtgärder har teststatusen "godkänd" eller så överförs minst en och resten är "utanför omfattningen"
    -  **Misslyckades** – minst en förbättringsåtgärd har teststatusen "misslyckades"
    - **Ingen** – alla förbättringsåtgärder har inte testats
    - **Utanför omfattningen –** alla förbättringsåtgärder är inte utrymmena för den här utvärderingen
    - **Pågående** – förbättringsåtgärder har en annan status än de som anges ovan, som kan innehålla "pågående", "delvis kredit" eller "oupptäckta"
- **Kontroll-ID:** Kontrollens ID-nummer, som tilldelats genom motsvarande bestämmelser, standard eller princip
- **Poäng uppnåt:** antalet poäng som intjänas genom att utföra åtgärder av det totala antalet uppnåliga poäng 
- **Dina åtgärder:** antalet åtgärder som slutförts av det totala antalet åtgärder som ska utföras
- **Microsoft-åtgärder:** antalet åtgärder som slutförts av Microsoft 

Om du vill visa information om en kontroll markerar du den på raden i tabellen. På sidan med kontrollinformation visas ett diagram som visar teststatus för åtgärderna i kontrollen. I en tabell under diagrammet visas viktiga förbättringsåtgärder för den kontrollen.

Välj en förbättringsåtgärd i listan för att granska informationssidan för förbättringsåtgärden. På informationssidorna visas teststatus, implementeringsanteckningar och lansering i den rekommenderade lösningen.

### <a name="your-improvement-actions-tab"></a>Fliken för förbättringsåtgärder

På fliken för förbättringsåtgärder visas alla kontroller i utvärderingen som hanteras av din organisation. Statusfältet visar den sammanslagna teststatusen för dina förbättringsåtgärder i utvärderingen så att du snabbt kan avgöra vad som har testats och vad som fortfarande behöver göras. Under stapeln finns en fullständig lista över förbättringsåtgärder och nyckeldetaljer, inklusive: teststatus, antal potentiella och upparbetade poäng, tillhörande föreskrifter och standarder, tillämplig lösning, åtgärdstyp och kontrollfamilj. Läs mer om [hur åtgärder bidrar till ditt efterlevnadsresultat.](compliance-score-calculation.md#action-types-and-points)

Välj en förbättringsåtgärd för att visa informationssidan och välj **länken Starta nu** för att öppna lösningen för att vidta åtgärder.

### <a name="microsoft-actions-tab"></a>Fliken Microsoft-åtgärder

På fliken Microsoft-åtgärder visas alla åtgärder i utvärderingen som hanteras av Microsoft. Listan visar viktiga åtgärder, bland annat: teststatus, poäng som bidrar till din övergripande efterlevnadspoäng, tillhörande bestämmelser och standarder, tillämplig lösning, åtgärdstyp och kontrollfamilj. Välj en förbättringsåtgärd för att visa informationssidan.

Läs mer om [hur kontroller och förbättringsåtgärder spåras och poängs.](compliance-score-calculation.md)

## <a name="accept-updates-to-assessments"></a>Acceptera uppdateringar av utvärderingar

När en uppdatering är tillgänglig för en utvärdering visas ett meddelande och du kan välja att acceptera uppdateringen eller skjuta upp den till en senare tid.

### <a name="what-causes-an-update"></a>Vad som orsakar en uppdatering

En utvärderingsuppdatering inträffar när det finns underliggande malländringar som påverkar poängsättning. Ändringar kan innefatta justering av kontrollmappning eller annan vägledning baserat på ändringar i föreskrifter eller produktändringar. Utvärderingsuppdateringar kan komma från din organisation (till exempel när [en anpassad mall ändras)](compliance-manager-templates.md#modify-a-template)och från Microsoft.

Om Microsoft uppdaterar en mall för Efterlevnadshanteraren som du har utökat ärver din utvärdering dessa uppdateringar när du har accepterat dem. Din utvärdering behåller de ytterligare attribut som du använt för utvärderingen när du utökade den.

Anpassade utvärderingar som du skapar får inte några malluppdateringar från Microsoft. Anpassade utvärderingar kan få uppdateringar av förbättringsåtgärder, men Microsoft-uppdateringar för kontroll av mappning mellan utvärderingar och förbättringsåtgärder gäller inte för anpassade mallar.

> [!NOTE]
> Uppdateringar av utvärderingar gäller endast på gruppnivå. Om du har två utvärderingar byggda från samma mall som finns i två olika grupper, har varje utvärdering ett väntande uppdateringsmeddelande och du måste godkänna uppdateringen för varje bedömning i respektive grupp för sig.

#### <a name="where-youll-see-assessment-update-notifications"></a>Var du ser meddelanden om utvärderingsuppdatering

På sidan utvärderingsinformation visas även **etiketten Väntande** uppdatering bredvid utvärderingen med en uppdatering. Välj utvärderingen för att komma till dess informationssida.

Ett meddelande högst upp på sidan med bedömningsinformation visar att det finns en uppdatering för utvärderingen. Välj knappen **Granska uppdatering** i banderollen om du vill granska specifika ändringar och godkänna eller skjuta på uppdateringen.

Sidan med utvärderingsinformation kan också lista förbättringsåtgärder som har **etiketten Väntande** uppdatering bredvid sig. Dessa uppdateringar är för specifika ändringar av själva förbättringsåtgärderna och måste godkännas separat. Mer [information finns i Acceptera uppdateringar för förbättringsåtgärder.](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)

#### <a name="review-update-to-accept-or-defer"></a>Granska uppdatering för att acceptera eller skjuta på

När du **har valt** Granska uppdatering från sidan utvärderingsinformation visas ett utfällt fönster till höger på skärmen. Det utfällande fönstret innehåller viktig information nedan om den väntande uppdateringen:

- Mallrubriken
- Källan till uppdateringen (Microsoft, din organisation eller en viss användare)
- Datumet då uppdateringen skapades
- En översikt som förklarar uppdateringen
- Specifik information om ändringarna, inklusive påverkan på efterlevnadsresultatet, hur långt utvärderingen kommer att slutföras och det specifika antalet ändringar av förbättringsåtgärder och kontroller.

Om du **väljer länken Uppdaterad** mall hämtas en Excel fil som innehåller styrdata för versionen av mallen med de väntande uppdateringarna. Om du **väljer länken Aktuell** mall laddas en fil av den befintliga mallen ned utan ändringarna.

Om du vill acceptera uppdateringen och göra ändringarna i din utvärdering väljer du **Acceptera uppdatering.** Godkända ändringar är permanenta.

Om du **väljer** Avbryt tillämpas uppdateringen inte på utvärderingen. Meddelandet Väntar på uppdatering visas fortfarande **tills** du accepterar uppdateringen.

**Därför rekommenderar vi att du accepterar uppdateringar**

Genom att acceptera uppdateringar får du de senaste råden om hur du använder lösningar och vidtar lämpliga förbättringsåtgärder som hjälper dig att uppfylla kraven för certifieringen.

**Varför det kan vara bra att skjuta på en uppdatering**

Om du är mitt i en utvärdering kanske du vill vara säker på att du är klar med arbetet med det innan du accepterar en uppdatering av utvärderingen som kan störa kontrollmappningen. Du kan skjuta upp uppdateringen ett senare tillfälle genom att välja **Avbryt** i den utfällade granskningsuppdateringen.

## <a name="export-an-assessment-report"></a>Exportera en utvärderingsrapport

Du kan exportera en utvärdering till en Excel fil för intressenter i organisationen eller för externa granskare och såser. På sidan utvärderingsinformation väljer du knappen **Generera rapport** längst upp på sidan, som skapar en Excel fil som du kan spara och dela.

Rapporten är en ögonblicksbild av utvärderingen efter datum och tid för exporten. Den innehåller information om kontroller som hanteras av både dig och Microsoft, inklusive implementeringsstatus, testdatum och testresultat.

## <a name="delete-an-assessment"></a>Ta bort en bedömning

Om du tar bort en utvärdering tas den bort från listan på utvärderingssidan. Observera följande viktiga punkter om att ta bort utvärderingar:

- **Borttagning av en bedömning är permanent. kan du inte få tillbaka den.** Om du vill använda samma bedömning igen måste du skapa den igen.
- Om förbättringsåtgärderna i utvärderingen inte förekommer i någon annan bedömning, tas de bort när utvärderingen tas bort.
- Vi rekommenderar [att du exporterar en](#export-an-assessment-report) rapport av utvärderingen innan du tar bort den permanent.

Följ stegen nedan om du vill ta bort en bedömning:

1. Välj den **utvärdering** du vill ta bort från utvärderingssidan för att öppna utvärderingssidan.

2. Välj **Ta bort** utvärdering i det övre högra hörnet på skärmen.

3. Ett fönster visas där du uppmanas att bekräfta att du vill ta bort utvärderingen permanent. Välj **Ta bort bedömning** för att stänga fönstret. Du får ett bekräftelsefönster på att din utvärdering har tagits bort från Efterlevnadshanteraren.

Om du tar bort den enda utvärderingen i en grupp tas även den gruppen bort från Efterlevnadshanteraren.

> [!NOTE]
> Du kan inte ta bort alla dina utvärderingar. Organisationer behöver minst en utvärdering för att Efterlevnadshanteraren ska fungera korrekt. Om utvärderingen som du vill ta bort är den enda, lägger du till en annan bedömning innan du tar bort den andra utvärderingen.
