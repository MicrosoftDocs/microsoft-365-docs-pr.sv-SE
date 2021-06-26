---
title: Arbeta med utvärderingsmallar i Microsoft Compliance Manager
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
description: Förstå hur du använder och hanterar mallar för att skapa bedömningar i Microsoft Compliance Manager. Skapa och ändra mallar med hjälp av en formaterad Excel fil.
ms.openlocfilehash: 2d20fa69345f2ff2624252972cb0e017e401f0dd
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149136"
---
# <a name="working-with-assessment-templates-in-compliance-manager"></a>Arbeta med utvärderingsmallar i Efterlevnadshanteraren

**I den här artikeln:** Förstå **hur mallar fungerar** och hur du hanterar **dem** från sidan med utvärderingsmallar. Få instruktioner för **hur** du  skapar **nya** mallar, utökar och ändrar befintliga mallar, formaterar dina malldata med **Excel** och exporterar **mallrapporter.**

> [!IMPORTANT]
> De utvärderingsmallar som är tillgängliga för din organisation beror på ditt licensavtal. [Granska informationen](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="templates-overview"></a>Översikt över mallar

En mall är ett ramverk av kontroller för att skapa en utvärdering i Efterlevnadshanteraren. Vår omfattande uppsättning mallar kan hjälpa din organisation att uppfylla nationella, regionala och branschspecifika krav som styr insamling och användning av data. Vi hänvisar till mallar med samma namn som deras underliggande certifiering eller bestämmelser, till exempel EU GDPR-mallen och ISO/IEC 27701:2019-mallen.

## <a name="template-availability-and-licensing"></a>Malltillgänglighet och licensiering

Vilka mallar som är tillgängliga för användning baseras på din organisations licensavtal[(visa licensinformation).](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager) Det finns två kategorier av mallar: inkluderade och premium.

#### <a name="included-and-premium-templates"></a>Inkluderade och premiummallar

1. **Mallar som** ingår tilldelas genom din licens och täcker viktiga bestämmelser och krav.
2. **Premium mallar** kan köpas för att utöka biblioteket och täcka specifika behov. När du har köpt kan du skapa så många utvärderingar från en mall som behövs. [Läs om hur du kan köpa premiummallar.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)

Visa en [fullständig lista över mallar](compliance-manager-templates-list.md).

#### <a name="active-and-inactive-templates"></a>Aktiva och inaktiva mallar

Mallar visar en aktiveringsstatus som antingen aktiv eller inaktiv:

- En mall anses vara **aktiv** när du har skapat en bedömning från den mallen.
- En mall anses **vara inaktiv** om din organisation inte använder den för en utvärdering.

När du köper en premiummall och skapar en bedömning utifrån den, är den mallen aktiv i ett år. Ditt köp förnyas automatiskt om du inte avbryter.

Du kan även prova premiummallar under en provperiod. Utvärderingslicenser gäller i upp till 25 mallar i 30 dagar. När utvärderingsversionen börjar ska mallarna bli tillgängliga i klientorganisationen inom 48 timmar. Försök kan aktiveras via Administrationscenter för Microsoft 365.

#### <a name="activated-templates-counter"></a>Räknare för aktiverade mallar

Sidan för utvärderings- och utvärderingsmallar **har en aktiverad mallräknare** längst upp. På räknaren visas antalet mallar som används av det antal som du är berättigad att använda i enlighet med ditt licensavtal. Mallanvändning räknas på certifieringsnivån.

Om räknaren till exempel visar 2/5 betyder det att din organisation har aktiverat 2 mallar av de 5 som är tillgängliga för användning.

Om räknaren visar 5/2 betyder det att organisationen överskrider sina gränser och behöver köpa 3 av de premiummallar som används.

Mer information finns i [Licensvägledning för Efterlevnadshanteraren.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)

## <a name="view-and-manage-templates"></a>Visa och hantera mallar

På sidan utvärderingsmallar i Efterlevnadshanteraren visas en lista med mallar och viktig information om dem. Listan innehåller mallar som tillhandahålls av Efterlevnadshanteraren samt alla mallar som din organisation har ändrat eller skapat. Du kan använda filter för att hitta en mall baserat på certifiering, produktomfattning, land, bransch, vem som skapade den och om mallen har aktiverats för utvärdering.

Välj en mall på raden så att informationssidan visas. Den här sidan innehåller en beskrivning av mallen och ytterligare information om certifiering, omfattning och kontroller. På den här sidan kan du välja lämpliga knappar för att skapa en utvärdering, exportera malldata till Excel eller ändra mallen.

## <a name="format-template-data-with-excel"></a>Formatera malldata med Excel

Det Excel (ladda ned ett[exempel)](https://go.microsoft.com/fwlink/?linkid=2124865)som används för att skapa eller ändra mallar har ett specifikt format och schema som måste användas för att importeras korrekt till Efterlevnadshanteraren. Den innehåller fyra flikar, av vilka tre är obligatoriska:

1. [Mall](#template-tab) (obligatoriskt)
2. [ControlFamily](#controlfamily-tab) (obligatoriskt)
3. [Åtgärder](#actions-tab) (obligatoriskt)
4. [Dimensioner](#dimensions-tab) (valfritt)

När du fyller i ett kalkylblad med malldata måste kalkylbladet ha flikarna i den ordning som anges **ovan,** annars importeras inte dina data till en mall.

##### <a name="template-tab"></a>Fliken Mall

Fliken **Mall** är obligatorisk. Informationen på den här fliken ger metadata om mallen. Det finns fyra obligatoriska kolumner. Kolumnerna måste behålla ordningen på det Excel bladet som anges nedan. Du kan lägga till en egen **kolumn efter** de fyra kolumnerna för att ge dina egna mått. Om du gör det måste du lägga till dem på **fliken** Mått.

- **rubrik**: Det här är rubriken för mallen, som måste vara unik. Det kan inte dela ett namn med en annan mall som du har i Efterlevnadshanteraren, inklusive dina egna mallar eller en mall för Efterlevnadshanteraren.

- **produkt:** Detta är en obligatorisk dimension. Lista den produkt som är kopplad till mallen.

- **certifiering**: Det här är den regel som du använder för mallen.

- **inScopeServices:** Det här är tjänsterna i produkten som den här utvärderingsadressen (om du till exempel angett Office 365 som produkt kan Microsoft Teams vara en omfattningstjänst). Du kan lista flera tjänster avgränsade med två semikolon.

> [!NOTE]
> De data du infogar i **produkten och** **certifieringscellerna** kan inte redigeras efter att du har importerat kalkylbladet för att skapa eller anpassa en mall. En grupp kan inte heller innehålla två utvärderingar som har samma kombination av **produkt/certifiering.** Du kan ha flera mallar med samma kombination för produkt/certifiering.

##### <a name="controlfamily-tab"></a>Fliken ControlFamily

Du **måste ha fliken ControlFamily.**  De obligatoriska kolumnerna på den här fliken, som måste följa den ordning som anges i exempelkalkylbladet, är:

- **controlName:** Det här är kontrollnamnet från certifieringen, standarden eller förordningen, som vanligtvis är någon typ av ID. Kontrollnamn måste vara unika i en mall. Du kan inte ha flera kontroller med samma namn i kalkylbladet.

- **controlFamily:** Ange ett ord eller en fras för kontrollenFamily, som identifierar en omfattande gruppering av kontroller. En kontrollFamily behöver inte vara unik. Den kan finnas med flera gånger i ett kalkylblad. Samma kontrollFamily kan också visas i flera mallar, men de har inga relationer till varandra. Alla kontrollerFamily måste mappas till minst en kontroll.

- **controlTitle**: Ange en rubrik för kontrollen. Medan controlName är en referenskod är rubriken ett RTF-format som vanligtvis förekommer i etiska bestämmelser.

- **controlDescription**: Ange en beskrivning av kontrollen.

- **controlActionTitle:** Det här är titeln på en åtgärd som du vill ska relatera till den här kontrollen. Du kan lägga till flera åtgärder genom att separera med två semikolon utan blanksteg emellan. Varje kontroll som du listar måste innehålla minst en åtgärd, och åtgärden måste finnas  (vilket innebär att du kan lista en åtgärd som du har listat på fliken Åtgärder i samma kalkylblad, en åtgärd som finns i en annan mall eller en åtgärd som skapats av Microsoft). Olika kontroller kan referera till samma åtgärd.

##### <a name="actions-tab"></a>Fliken Åtgärder

Fliken **Åtgärder** är obligatorisk.  Den utser förbättringsåtgärder som hanteras av din organisation och inte av Microsoft, som redan finns i Efterlevnadshanteraren. De obligatoriska kolumnerna för den här fliken, som måste följa den ordning som anges i exempelkalkylbladet, är:

- **actionTitle:** Det här är rubriken för din åtgärd och är ett obligatoriskt fält. Namnet du anger måste vara unikt. **Viktigt!** Om du refererar till en åtgärd som du redan äger (t.ex. i en annan mall) och du ändrar något av elementen i den i de efterföljande kolumnerna, sprids ändringarna till samma åtgärd i andra mallar.

- **implementationType**: I det här obligatoriska fältet anger du en av de tre implementeringstyperna nedan:
    - **Drift** – åtgärder som implementeras av personer och processer för att skydda sekretess, integritet och tillgänglighet för organisationssystem, tillgångar, data och personal (till exempel: säkerhetsmedvetenhet och utbildning)
    - **Teknik** – åtgärder som slutförs med hjälp av teknik och mekanismer som ingår i maskinvaran, programvaran eller komponenterna i den inbyggda programvaran i informationssystemet för att skydda konfidentialitet, integritet och tillgänglighet för organisationssystem och data (exempel: multifaktorautentisering)
    - **Dokumentation** – åtgärder som implementeras genom dokumenterade principer och metoder för att upprätta och definiera de kontroller som krävs för att skydda sekretess, integritet och tillgänglighet för organisationssystem, tillgångar, data och personal (exempel: en informationssäkerhetspolicy)

- **actionScore**: Ange ett numeriskt poängvärde för åtgärden i det här fältet. Värdet måste vara ett helt tal mellan 1 och 99. får inte vara 0, null eller tomt. Ju högre värde, desto större värde kan du få för att förbättra din efterlevnad. I bilden nedan visas hur Efterlevnadshanterarens resultat styr:

![Efterlevnadshanteraren styr punktvärden](../media/compliance-score-action-scoring.png "Efterlevnadshanteraren styr punktvärden")

- **actionDescriptionTitle**: Det här är rubriken på beskrivningen och är obligatoriskt. Med den här beskrivningsrubriken kan du ha samma åtgärd i flera mallar och visa en annan beskrivning i varje mall.  Det här fältet hjälper dig att förtydliga vilken mall beskrivningen refererar till. I de flesta fall kan du ange namnet på mallen som du skapar i det här fältet.

- **actionDescription**: Ange en beskrivning av åtgärden. Du kan använda formatering som fet text och hyperlänkar. Det här fältet är obligatoriskt.

- **dimension-Action Purpose:** Det här är ett valfritt fält. Om du tar med det måste rubriken innehålla "dimension-"-prefixet. De dimensioner som du tar med här används som filter i Efterlevnadshanteraren och visas på informationssidan för förbättringsåtgärder i Efterlevnadshanteraren.

##### <a name="dimensions-tab"></a>Fliken Mått

Fliken **Mått** är valfri. Men om du refererar till en dimension någon annanstans måste du ange den här om den inte finns i en mall som du redan har skapat eller i en Microsoft-mall. Kolumnerna för den här fliken anges nedan:

- **dimensionKey**: lista som "produkt", "certifieringar", "åtgärdssyfte"
- **dimensionValue**: exempel: Office 365, HIPPA, Preventative,Aktivering

När du exporterar en befintlig mall har det exporterade kalkylbladet fliken **Mått,** som innehåller alla dimensioner som används i mallen.

## <a name="create-an-assessment-template"></a>Skapa en utvärderingsmall

Om du vill skapa en egen mall för anpassade utvärderingar använder du det specialformaterade Excel-kalkylbladet för att sammanställa nödvändiga kontrolldata. När du har slutfört kalkylbladet importerar du det till Efterlevnadshanteraren.

#### <a name="required-roles"></a>Roller som krävs

Endast användare med rollen Global administratör eller Efterlevnadshanteraren kan skapa och ändra mallar. Läs mer om [roller och behörigheter.](compliance-manager-setup.md#set-user-permissions-and-assign-roles)

### <a name="create-new-template-in-compliance-manager"></a>Skapa ny mall i Efterlevnadshanteraren

1. Gå till sidan **för utvärderingsmallar** i Efterlevnadshanteraren.
2. Välj **Skapa ny mall**. En guide för att skapa mallar öppnas.
3. Välj den typ av mall du vill skapa. I det här fallet väljer **du Skapa en anpassad mall** och sedan **Nästa.**
4. På skärmen **Upload väljer** du  Bläddra för att hitta och ladda upp den formaterade Excel filen med alla obligatoriska malldata.
5. Om det inte är problem med filen visas namnet på den fil som har laddats upp. Gå vidare genom att klicka på **Nästa.** (Om du behöver ändra filen väljer du Upload **annan fil**).
    - Om det finns ett fel med filen förklarar ett felmeddelande högst upp vad som är fel. Du måste åtgärda filen och ladda upp den igen. Fel uppstår om kalkylbladet är felaktigt formaterat eller om det finns ogiltig information i vissa fält.
6. På **skärmen Granska och** slutför visas antalet förbättringsåtgärder och -kontroller och mallens högsta poäng. När du är redo att godkänna väljer **du Skapa mall.** (Om du behöver göra ändringar väljer du **Tillbaka**.)
7. På den sista skärmen bekräftar du att en ny mall har skapats. Välj **Klar** för att avsluta guiden.
8. Du kommer till den nya mallens informationssida, där du kan [skapa din utvärdering.](compliance-manager-assessments.md#create-assessments)

## <a name="extend-an-assessment-template"></a>Utöka en utvärderingsmall

Efterlevnadshanteraren ger dig möjlighet att lägga till egna kontroller och förbättringsåtgärder i en befintlig Microsoft-mall. Den här processen kallas för att utöka en Microsoft-mall. När du utökar en mall kan den fortfarande få uppdateringar som släppts av Microsoft, vilket kan hända när det finns ändringar i den relaterade lagstiftningen eller produkten (se Acceptera [uppdateringar av utvärderingar](compliance-manager-assessments.md#accept-updates-to-assessments)).

För att förbereda behöver du sätta ihop ett specialformaterat Excel för att importera nödvändiga malldata. Filen Excel samma format som beskrivs ovan, men det finns särskilda krav för tillägg. Se följande ytterligare punkter för att förhindra fel:

- Kalkylbladet ska bara innehålla de åtgärder och kontroller som du vill lägga till i utvärderingen.
- Kalkylbladet kan inte innehålla någon av de kontroller eller åtgärder som redan finns i utvärderingen som du vill ändra.
- Överväg att inkludera "anknytning" i mallens titel, till exempel tillägget "GDPR – [ditt företagsnamn]." Det gör det enklare att i  listan på sidan för utvärderingsmallar identifiera sig som skild från standardmallen från Microsoft eller en anpassad mall med ett liknande namn.

När du har formaterat kalkylbladet följer du stegen nedan.

1. Gå till sidan **Utvärderingsmallar** och välj **Skapa ny mall**. En guide för att skapa mallar öppnas.

2. Välj den typ av mall du vill skapa. I det här fallet väljer **du Utöka en Microsoft-mall** och **sedan Välj Microsoft-mall**.

3. Ett utfällningsfönster för mallval visas till höger på skärmen med en lista över alla mallar och deras status som aktiv eller inaktiv. Räknare **för aktiverade** mallar visar hur många mallar som för närvarande används av det totala antal som är tillgängliga att använda. Om du är över gränsen visas ett meddelande i meddelandefältet.

4. Ett utfällningsfönster för mallval visas till höger på skärmen. Använd **Sök** för att använda filter för att hitta den mall du vill använda

5. När du har hittat mallen väljer du alternativknappen till vänster om dess namn och väljer **sedan Spara**.

6. På nästa skärm visas den mall du har valt. Om det är korrekt väljer du **Nästa.** (Om det är felaktigt väljer **du Välj en annan mall** för att välja igen.)

7. På skärmen **Upload väljer** du  Bläddra för att hitta och ladda upp den formaterade Excel filen med alla obligatoriska malldata.

8. Om det inte är problem med filen visas namnet på den fil som laddats upp på nästa skärm. Välj **Nästa** för att fortsätta (om du behöver ändra filen väljer du Ändra **Upload annan fil**).

    - Om det är problem med filen visas ett felmeddelande högst upp som förklarar vad som är fel. Du måste åtgärda och ladda upp filen på ny tid. Fel uppstår om kalkylbladet är felaktigt formaterat eller om det finns ogiltig information i vissa fält.

9. På **skärmen Granska och** slutför visas antalet förbättringsåtgärder och -kontroller och mallens högsta poäng. Välj Nästa när du är redo att **godkänna.** (Om du behöver göra ändringar väljer du **Upload en annan fil**.)

10. På den sista skärmen bekräftar du att en ny mall har skapats. Välj **Klar** för att avsluta guiden.

11. Du kommer till den nya mallens informationssida. Härifrån kan du skapa din utvärdering genom att välja **Skapa bedömning.** Vägledning finns i [Skapa och hantera utvärderingar.](compliance-manager-assessments.md#create-assessments)

## <a name="modify-a-template"></a>Ändra en mall

Du kanske vill ändra en mall som du redan har skapat, till exempel lägga till kontroller eller lägga till eller ta bort förbättringsåtgärder. Processen liknar processen för att skapa mallar på så sätt att du laddar upp formaterade Excel filen med dina malldata.

Det finns dock information som du bör känna till när du formaterar filen med ändringar av befintliga malldata. **Vi rekommenderar att du granskar de här instruktionerna noggrant så att du inte skriver över befintliga data som du vill behålla.**

### <a name="format-your-excel-file-to-modify-an-existing-template"></a>Formatera Excel för att ändra en befintlig mall

Välj den **mall du** vill ändra på sidan med utvärderingsmallar, så visas   dess informationssida. Välj sedan **Exportera till Excel**. En Excel fil med alla dina malldata laddas ned. Spara filen lokalt.

Om du vill arbeta med den här filen går du till ett avsnitt nedan för att snabbt hitta de instruktioner du behöver:

- [Redigera huvudmallens attribut](#edit-the-main-template-attributes)
- [Lägga till en förbättringsåtgärd](#add-an-improvement-action)
- [Redigera information för en förbättringsåtgärd](#edit-an-improvement-actions-information)
- [Ändra namnet på en förbättringsåtgärd](#change-an-improvement-actions-name)
- [Ta bort en förbättringsåtgärd](#remove-an-improvement-action)
- [Ta bort en kontroll](#remove-a-control)

#### <a name="edit-the-main-template-attributes"></a>Redigera huvudmallens attribut

På fliken **Mallar** kan du redigera  vad som helst i rubrikkolumnen, **iScopeServices-kolumnen** och i andra kolumner som du kan ha lagt till. Du kan dock inte redigera något i produkten eller **certifieringskolumnerna.** 

#### <a name="add-an-improvement-action"></a>Lägga till en förbättringsåtgärd

1. Gå till **fliken** Åtgärder. Lägg till din information i de obligatoriska fälten på den första tomma raden under dina befintliga åtgärder.
2. Gå till **fliken ControlFamily.** Leta reda på raden som innehåller kontrollen som förbättringsåtgärden mappar till. Lägg till den nya åtgärden i kolumnen **ControlActionTitle** på raden (kom ihåg att avgränsa flera åtgärder i det här fältet med två semikolon, inget blanksteg emellan).
3. Spara kalkylbladet.

#### <a name="edit-an-improvement-actions-information"></a>Redigera information för en förbättringsåtgärd

Du kan ändra information för alla förbättringsåtgärder *förutom rubriken*. Du kan redigera alla celler från kolumn B och framåt, och när du importerar filen tillbaka till mallen innehåller förbättringsåtgärderna i mallen nu de uppdaterade data.

Du kan inte redigera **actionTitle** (kolumn A) eftersom efterlevnadshanteraren i så fall ser det som en ny förbättringsåtgärd. Läs instruktionerna direkt nedan om du vill ändra namnet på en förbättringsåtgärd.

#### <a name="change-an-improvement-actions-name"></a>Ändra namnet på en förbättringsåtgärd

Om du vill ändra namnet på en förbättringsåtgärd måste du uttryckligen ange i kalkylbladet att du ersätter ett befintligt namn med ett nytt namn. Gör så här:

1. På fliken **Åtgärder** i kalkylbladet lägger du till en ny kolumn i kalkylbladet efter kolumn A.
2. I den nya kolumnen, som nu är kolumn B, placerad som rubrik på rad 1: **oldActionTitle**.
3. Kopiera innehållet i kolumn A och klistra in dem i kolumn B. Det placerar de befintliga rubrikerna för förbättringsåtgärden, som är vad du vill ändra, i kolumn B.
4. Ta bort det gamla namnet i kolumn A, **actionTitle**, och ersätt det med det nya namnet för förbättringsåtgärden.

Observera att åtgärdsrubriker, både för dina förbättringsåtgärder och för Microsoft-åtgärder, måste skrivas på engelska för att det ska kunna identifieras när det refereras till i kontroller.

#### <a name="remove-an-improvement-action"></a>Ta bort en förbättringsåtgärd

Om du vill ta bort en förbättringsåtgärd från en mall måste du ta bort den från alla kontroller som refererar till den. Följ stegen nedan för att ändra kalkylbladet:

1. Sök efter titeln på den förbättringsåtgärd du vill ta bort på fliken **ControlFamily.**
2. Ta bort rubriken för förbättringsåtgärden i cellerna där den visas. Om förbättringsåtgärden är den enda åtgärden på raden tar du bort hela raden (vilket tar bort kontrollen).
3. På fliken **Åtgärder** tar du bort raden som innehåller den förbättringsåtgärd som du tar bort.
4. Spara kalkylbladet.

När du importerar kalkylbladet tillbaka till mallen tas förbättringsåtgärden bort från mallen.

Om du tar bort en förbättringsåtgärd från en mall tas inte förbättringsåtgärden bort helt från Efterlevnadshanteraren. Den åtgärden kan fortfarande refereras till av en annan mall.

#### <a name="remove-a-control"></a>Ta bort en kontroll

Om du vill ta bort en kontroll ändrar du kalkylbladet genom att följa stegen nedan och sedan importera kalkylbladet på nytt:

1. På fliken **ControlFamily** hittar du den kontroll du vill ta bort i **kolumnen controlName.**
2. Ta bort raden för kontrollen.
    - Om den här borttagna kontrollen innehåller förbättringsåtgärder som inte refereras till av någon annan kontroll måste du ta bort de förbättringsåtgärderna från **fliken** Åtgärder. Annars får du ett verifieringsfel.

3. Spara kalkylbladet.

När du importerar kalkylbladet till mallen igen tas kontrollen bort från mallen.

### <a name="modify-template-info-in-compliance-manager"></a>Ändra mallinformation i Efterlevnadshanteraren

Följ de Excel när filen har slutförts och sparats.

1. Öppna utvärderingsmallssidan igen och välj mallen. Välj Ändra mall på mallens **informationssida för att** påbörja ändringsguiden.
2. På skärmen **Upload väljer** du Bläddra för **att hitta** och ladda upp Excel filen.
3. Om det inte är problem med filen visas namnet på den fil som laddats upp på nästa skärm. Välj **Nästa** för att fortsätta (om du behöver ändra filen väljer du Ändra **Upload annan fil**).
    - Om det är problem med filen visas ett felmeddelande högst upp som förklarar vad som är fel. Du måste åtgärda filen och ladda upp den igen. Fel uppstår om kalkylbladet är felaktigt formaterat eller om det finns ogiltig information i vissa fält.

4. På **skärmen Granska och** slutför visas antalet förbättringsåtgärder och -kontroller och mallens högsta poäng. Välj Nästa när du är redo att **godkänna.**
5. På den sista skärmen bekräftar du att mallen har ändrats. Välj **Klar** för att avsluta guiden.

Mallen innehåller nu de ändringar du har gjort. Alla utvärderingar som använder den här ändrade mallen visar nu väntande uppdateringar och du måste acceptera uppdateringarna av utvärderingarna för att återspegla ändringarna som gjorts i mallen. Läs mer om [uppdateringar av utvärderingar.](compliance-manager-assessments.md#accept-updates-to-assessments)

> [!NOTE]
> Om du använder Compliance Manager på ett annat språk än engelska kommer du att märka att en del text visas på engelska när du exporterar en mall till Excel. Rubrikerna för åtgärder (både dina förbättringsåtgärder och Microsoft-åtgärder) måste vara på engelska för att kunna identifieras av kontroller. Om du ändrar en åtgärdstitel ska du skriva den på engelska så att filimporterna blir rätt.

## <a name="export-a-template"></a>Exportera en mall

Du kan Excel en fil som innehåller alla data i en mall. Du måste exportera en mall för att kunna ändra den eftersom det här är den Excel redigerar och laddar upp i [ändringsprocessen.](#modify-a-template)

Om du vill exportera mallen går du till sidan med mallinformation och väljer **knappen Exportera Excel** mall.

Observera att när du exporterar en mall som du utökat från en efterlevnadshanteraren-mall, kommer den exporterade filen bara att innehålla de attribut som du lagt till i mallen. Den exporterade filen innehåller inte de ursprungliga malldata som tillhandahålls av Microsoft. Om du vill ha en sådan rapport följer du anvisningarna [för att exportera en utvärderingsrapport.](compliance-manager-assessments.md#export-an-assessment-report)
