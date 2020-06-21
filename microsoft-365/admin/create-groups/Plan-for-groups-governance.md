---
title: Planera för gruppstyrning
ms.reviewer: johasand
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BSA160
description: Lär dig hur du planerar för styrning av Microsoft 365-grupper.
ms.openlocfilehash: 37d243b56de363985ecb9463dfe5eb182d9e40b1
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780499"
---
# <a name="plan-for-governance-in-groups"></a>Planera för styrning i grupp

Microsoft 365 Groups har en omfattande uppsättning verktyg för att implementera alla styrningsfunktioner som din organisation kan behöva. Den här artikeln hjälper IT-proffs att ställa rätt frågor för att avgöra deras krav på styrning och hur de ska uppfyllas baserat på deras organisationsprofil.

## <a name="why-microsoft-365-groups"></a>Varför Microsoft 365-grupper?
![bild desc](../../media/01.png)

Vi vet att organisationer idag använder en mångsidig verktygsuppsättning. Det finns ett team av utvecklare som använder teamchatt, chefer som skickar e-post och hela organisationen som ansluter till företagets sociala. Flera samarbetsverktyg används eftersom varje grupp är unik och har sina egna funktionella behov och arbetsstil. Vissa kommer endast att använda e-post medan andra kommer att bo främst i chatten. 

Om användarna anser att it-verktygen inte passar deras behov, kommer de sannolikt att ladda ner sin favorit konsument app som stöder deras scenarier. Även om den här processen tillåter användare att komma igång snabbt, leder det till en frustrerande användarupplevelse i hela organisationen med flera inloggningar, svårigheter att dela och ingen enskild plats att visa innehåll. Detta begrepp kallas "Shadow IT" och utgör en betydande risk för organisationer. Det minskar möjligheten att hantera användaråtkomst på ett enhetligt sätt, säkerställa säkerhet och behov av tjänstefterlevnad.

Microsoft 365 Groups ger användarna möjlighet och minskar risken för skugg-IT genom att i ett enda steg tillhandahålla många av de verktyg som behövs för att samarbeta. Med Microsoft 365 Groups kan du välja en uppsättning personer som du vill samarbeta med och enkelt skapa en samling resurser som dessa personer kan dela. Att manuellt tilldela behörigheter till resurser är ett förr som ett förflutet eftersom det automatiskt ger alla resurser som gruppen tillhandahåller om du lägger till medlemmar i gruppen.

## <a name="technical-architecture"></a>Teknisk arkitektur

Det finns tre huvudsakliga kommunikationsmetoder som stöds av Microsoft 365 Groups. Grupper kan skapas i dessa upplevelser och användas i Microsoft 365:
- Outlook: samarbete via e-post med en delad grupp inkorg och kalender
- Microsoft Teams: en beständig chattbaserad arbetsyta där du kan ha informella konversationer i realtid kring en mängd olika ämnen som organiseras av specifika undergrupper
- Yammer: social erfarenhet av företag för samarbete

> [!NOTE]
> Genom att skapa en ny grupp via andra teamwork-program – till exempel SharePoint, Planner eller Stream – skapas en grupp med en Outlook-inkorg och möjligheten att ansluta till Microsoft Teams.

Beroende på var en grupp skapas etableras vissa resurser automatiskt, till exempel:
- [Inkorg](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) - För e-postkonversationer mellan gruppmedlemmar. Den här inkorgen har en e-postadress och kan ställas in för att acceptera meddelanden från personer utanför gruppen och även utanför organisationen, ungefär som en traditionell distributionslista.
 - [Kalender](https://support.microsoft.com/office/0cf1ad68-1034-4306-b367-d75e9818376a) – För schemaläggning av händelser relaterade till gruppen
- [SharePoint-gruppwebbplats](https://support.microsoft.com/office/75545757-36c3-46a7-beed-0aaa74f0401e) – En central databas för information, länkar och innehåll som rör din grupp
- [SharePoint-dokumentbibliotek](https://support.microsoft.com/office/749bc73b-90c9-4760-9b6f-9aa1cf01b403) – En central plats för gruppen att lagra och dela filer
- [OneNote-anteckningsbok](https://support.microsoft.com/office/e768fafa-8f9b-4eac-8600-65aa10b2fe97) – För att samla in idéer, forskning och information
- [Planerare](https://support.microsoft.com/office/4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) – För att tilldela och hantera projektaktiviteter bland gruppmedlemmarna
- [Yammer-gruppen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) – En vanlig plats att föra konversationer och dela information
- Microsoft Teams – En chattbaserad arbetsyta i Microsoft 365

Mer information om vilka resurser som skapas för varje grupp finns i [Lär dig mer om Microsoft 365 Groups](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).

> [!NOTE]
> När en ny Microsoft 365-grupp skapas via Yammer eller Teams visas inte gruppen i Outlook eller adressboken eftersom den primära kommunikationen mellan dessa användare sker i deras respektive klienter. Yammer-grupper kan inte anslutas till Microsoft Teams.

## <a name="where-to-start-a-conversation"></a>Var du ska starta en konversation
Det finns flera platser där du kan föra en konversation i Microsoft 365. Att förstå var en konversation ska starta kan hjälpa organisationer att definiera en strategi för kommunikation.

![bild desc](../../media/03.png)

- Team: chattbaserad arbetsyta (samarbete med hög hastighet) – inre slinga
   - Byggd för samarbete med de människor du arbetar med varje dag
  - Sätter information till användarnas fingertoppar i en enda upplevelse
  - Lägga till flikar, kopplingar och robotar
  - Livechatt, ljud-/videokonferenser, inspelade möten

- Yammer: anslut över org (företag social) - yttre slinga
  - Praktiska grupper av människor som delar ett gemensamt intresse eller sakkunskap men som inte nödvändigtvis arbetar tillsammans varje dag
  - Ledarskapsanslutning, lärande samhällen, rollbaserade samhällen

- Outlook-grupper: modern DL (e-postbaserat samarbete)
  - Allestädes närvarande för riktad kommunikation
  - Uppgradera DLs till Microsoft 365-grupper – [Varför ska du uppgradera?](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

- SharePoint – Kärninnehållssamarbete för alla Microsoft 365-grupper
  - Varje grupp får en ansluten SharePoint-gruppwebbplats
  - Dela innehåll, skapa anpassade sidor och skapa författarnyheter
  - [Ansluta](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview) befintliga SharePoint-gruppwebbplatser till nya Microsoft 365-grupper

##  <a name="managing-and-governing-microsoft-365-at-scale"></a>Hantera och styra Microsoft 365 i stor skala

Microsoft 365 Groups har en omfattande uppsättning verktyg för att implementera alla styrningsfunktioner som din organisation kan behöva. I följande avsnitt beskrivs funktionerna, rekommenderar bästa praxis och vägledning för att ställa rätt frågor för att fastställa kraven för styrning och hur de ska uppfyllas.

**I detta avsnitt:**
- [Styra vem som kan skapa Microsoft 365-grupper](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#control-who-can-create-office-365-groups)
- [Gruppera mjuk borttagning och återställning](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-soft-delete-and-restore)
- [Gruppnamngivningsprincip](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-naming-policy)
- [Policy för gruppens förfallodatum](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-expiration-policy)
- [Grupp gäståtkomst](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-guest-access)
- [Grupprinciper & informationsskydd](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-policies--information-protection)
- [Uppgradera traditionella samarbetsverktyg](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#upgrade-traditional-collaboration-tools)
- [Rapporter från grupper](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#groups-reporting)

### <a name="control-who-can-create-microsoft-365-groups"></a><a name="control-who-can-create-office-365-groups"></a>Styra vem som kan skapa Microsoft 365-grupper
Grupper kan skapas av slutanvändare från flera slutpunkter, inklusive Outlook, SharePoint, Teams och andra miljöer.

![bild desc](../../media/04.png)
> [!Tip]
>- Starkt överväga självbetjäning för att ge gruppägare.
>- Dokumentera och kommunicera hur du begär en grupp.
>- Gå tillbaka till vem som kan skapa grupper under molnresan.
>- Överväg att använda dynamiskt medlemskap för att konfigurera säkerhetsgruppens medlemmar för att kontrollera gruppskapande.
>- Utvärdera vilka grupper scenarier kan hanteras via ett dynamiskt medlemskap och tillåta självbetjäning för resten.

Det finns tre primära modeller för etablering i grupper: öppna, IT-ledda och kontrollerade. I följande tabell beskrivs fördelarna med varje modell.

| Modell          | Fördelar                                                   |
| -------------- | ------------------------------------------------------------ |
| Öppna (standard) | Användare kan skapa sina egna grupper efter behov utan att behöva vänta på, eller bry sig om IT. |
| IT-ledda         | Användare begär en grupp från IT. IT kan vägleda dem i valet av de bästa samarbetsverktygen för deras behov. |
| Kontrollerade     | Gruppskapande begränsat till specifika personer, team eller tjänster. Mer information finns i [Hantera vem som kan skapa Microsoft 365-grupper](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups). |

Din organisation kan ha särskilda krav för att implementera strikta kontroller för vem som kan skapa grupper. Använd följande tabell för att fatta beslut om vilken etableringsmodell som passar din organisation.

|         |         |         |
|---------|---------|---------|
|![bild desc](../../media/decision_point.png)|Beslutspunkter|<ul><li>Vilken etableringsmodell passar organisationens krav?</li><li>Kräver din organisation att gruppen begränsar gruppskapandet till administratörer?</li><li>Kräver din organisation att gruppen begränsar gruppskapandet till medlemmar i säkerhetsgruppen?</li><li>Kräver din organisation att vissa grupper skapas dynamiskt baserat på användarattribut, till exempel avdelning?</li></ul>|
|![bild desc](../../media/next_steps.png)|Nästa steg|<ul><li>Dokumentera organisationens krav för att skapa grupper och grupper.</li><li>Planera att implementera dessa krav som en del av grupputrullningen.</li><li>Kommunicera och publicera dina policyer för att informera användarna om det beteende de kan förvänta sig</li><li>Planera att implementera dynamiskt medlemskap där så är tillämpligt.</li></ul>|

> [!Important]
> Begränsa grupp- och teamskapande kan minska användarnas produktivitet eftersom många Microsoft 365-tjänster kräver att grupper skapas för att tjänsten ska fungera. Mer information finns i [Varför styra vem som skapar Microsoft 365-grupper?](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide%23why-control-who-creates-office-365-groups)

#### <a name="resources"></a>*Resurser*
- [Hantera vem som kan skapa Microsoft 365-grupper](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide)
- [Fylla i grupper dynamiskt baserat på objektattribut](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-with-advanced-rules)
- [Så här ändrar du standardinställningen för Microsoft 365 Groups for Outlook, till offentliga eller privata](https://support.microsoft.com/office/36236e39-26d3-420b-b0ac-8072d2d2bedc)
- [Synkronisera säkerhetsgrupper med gruppmedlemskap](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Syncing-Security-Groups-with-team-membership/ba-p/241959)

### <a name="group-soft-delete-and-restore"></a><a name="group-soft-delete-and-restore"></a>Gruppera mjuk borttagning och återställning
Om du har tagit bort en Microsoft 365-grupp har den som standard behållits i 30 dagar. Den här 30-dagarsperioden kallas "mjuk borttagning" eftersom du fortfarande kan återställa gruppen. Efter 30 dagar tas gruppen och det tillhörande innehållet bort permanent och kan inte återställas.

> [!Tip]
>- Kommunicera återställningsprocessen till användarna.
>- Träna ditt helpdesk-team.
>- Spåra kommande grupper som tas bort med PowerShell-skriptet.

|         |         |         |
|---------|---------|---------|
|![bild desc](../../media/decision_point.png)|Beslutspunkter|<ul><li>Kräver du att vissa tillgångar ska arkiveras för långsiktig lagring?</li><li>Har du vissa lagringskrav för din organisation?</li></ul>|
|![bild desc](../../media/next_steps.png)|Nästa steg|<ul><li>Kommunicera och publicera principer för borttagning och återställning för att informera användarna om det beteende de kan förvänta sig </li><li> Dokumentera organisationens krav för övervakning av borttagna grupper.</li><li>Planera att implementera dessa krav som en del av grupputrullningen.</li></ul>|

> [!Important]
>During the "soft-delete" period if a user tries to access the site they will get a 403 forbidden message. After this period if the user tries to access the site they will get a 404 not found message.

#### <a name="resources"></a>*Resurser*
- [Återställa en borttagen Microsoft 365-grupp](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group?ui=en-US&rs=en-001&ad=US)
- [Återställa en borttagen Microsoft 365-grupp i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)
- [Ta bort grupper med hjälp av cmdleten Remove-UnifiedGroup](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)

### <a name="group-naming-policy"></a><a name="group-naming-policy"></a>Gruppnamngivningsprincip
En namngivningsprincip kan hjälpa dig och dina användare att identifiera funktionen för gruppen, medlemskap, geografisk region eller vem som skapade gruppen. Namngivningsprincipen kan också hjälpa till att kategorisera grupper i adressboken. Du kan använda principen för att blockera specifika ord från att användas i gruppnamn och alias.

> [!Tip]
> - Använd korta strängar som suffix.
> - Använd attribut med värden.
> - Var inte för kreativ, total namnlängd har högst 264 tecken.
> - Ladda upp organisationens specifika blockerade ord för att begränsa användningen.


|         |         |         |
|---------|---------|---------|
|![bild desc](../../media/decision_point.png)|Beslutspunkter|<ul><li>Kräver din organisation en specifik namngivningskonvention för grupper?</li><li>Kräver din organisation namngivningskonventionen för alla arbetsbelastningar?</li><li>Har din organisation specifika ord som du vill hindra användare från att använda?</li></ul>|
|![bild desc](../../media/next_steps.png)|Nästa steg|<ul><li>Dokumentera organisationens krav för namngivningsgrupper. </li><li> Planera att implementera dessa krav som en del av grupputrullningen.</li><li> Kommunicera och publicera namngivningsprinciper och standarder för att informera användarna.</li></ul>|

> [!Important]
>Namngivningsprincipen tillämpas på grupper som skapas i alla grupparbetsbelastningar (som Outlook, Microsoft Teams, SharePoint, Planner, Yammer osv.). Den tillämpas på både gruppnamnet och gruppaliaset. Den tillämpas när en användare skapar en grupp och när gruppnamn eller alias redigeras för en befintlig grupp.

#### <a name="resources"></a>*Resurser*
- [Namngivningsprincip för Microsoft 365 Grupper](https://docs.microsoft.com/office365/admin/create-groups/groups-naming-policy)
- [Framtvinga en namngivningsprincip för Microsoft 365-grupper i Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=868340)
- [Azure Active Directory-cmdletar för att konfigurera gruppinställningar](https://go.microsoft.com/fwlink/?linkid=868341)
- [Förhandsgranska funktioner för gruppnamngivning](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/NamingPolicy)

### <a name="group-expiration-policy"></a><a name="group-expiration-policy"></a>Policy för gruppens förfallodatum
Administratörer kan ange en förfalloperiod och alla grupper som når slutet av den perioden och som inte förnyas tas bort. Förfallotiden börjar när gruppen skapas eller på det datum då den senast förnyades. Gruppägare skickas automatiskt ett e-postmeddelande före förfallodatumet som gör att de kan förnya gruppen för ett annat utgångsdatum. Aktiva grupper förnyas automatiskt.

När du har angett att en grupp ska upphöra att gälla:
- Ägare av gruppen meddelas att förnya gruppen som utgångsdatum närmar sig
- Alla grupper som inte förnyas tas bort
- Alla grupper som tas bort kan återställas inom 30 dagar av gruppägarna eller administratören

> [!Tip]
> - Pilot med specifika grupper från början.
> - Välj inaktiva grupper baserat på aktivitetsrapporten i Microsoft 365 administrationscenter.
> - Kommunicera förnyelseprocess till gruppägare.
> - Ombord på ditt helpdesk-team.
> - Se till att grupper har flera ägare och konfigurera e-post för överblivna grupper.


|         |         |         |
|---------|---------|---------|
|![bild desc](../../media/decision_point.png)|Beslutspunkter|<ul><li>Kräver din organisation att du anger ett utgångsdatum för team?</li><li>Bestäm strategin för att hantera överblivna grupper.</li></ul>|
|![bild desc](../../media/next_steps.png)|Nästa steg|<ul><li>Dokumentera organisationens krav på gruppens förfallodatum, datalagring och arkivering.</li><li>Planera att implementera dessa krav som en del av grupputrullningen.</li><li>Planera att implementera ett anpassat jobb för att rapportera om grupper som har enskilda ägare eller är ägarlösa. </li></ul>|

> [!Important]
>När du ändrar förfalloprincipen beräknas tjänsten om förfallodatumet för varje grupp. Den börjar alltid räkna från det datum då gruppen skapades och tillämpar sedan den nya förfalloprincipen.

#### <a name="resources"></a>*Resurser*
- [Förfalloprincip för Microsoft 365-grupper](https://docs.microsoft.com/microsoft-365/admin/create-groups/office-365-groups-expiration-policy)
- [Konfigurera principen för förfallodatum för Microsoft 365-grupper](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

### <a name="group-guest-access"></a><a name="group-guest-access"></a>Grupp gäståtkomst
Administratörer kan styra om gäståtkomst till Microsoft 365-grupper ska tillåtas för hela organisationen eller för enskilda Microsoft 365-grupper. De kan också styra vem som kan tillåta att gästerna läggs till i grupper.
>[!Tip]
>- Aktivera gäståtkomst på klientnivå. Blockera om det behövs för specifika grupper.
>- Styra med hjälp av tillåt/blockera gästdomäner, gästombjudarroll, åtkomstgranskningar, användarvillkor.
>- Spåra gästanvändaraktivitet via granskningsloggar.

|         |         |         |
|---------|---------|---------|
|![bild desc](../../media/decision_point.png)|Beslutspunkter|<ul><li>Behöver du begränsa möjligheten att lägga till gäster i lag per grupp?</li><li> Kräver din organisation att du lägger fram relevanta ansvarsfriskrivningar för juridiska krav eller efterlevnadskrav?</li><li>Har din organisation behov av att minska den administrativa överhuvudet för att lägga till och ta bort användare?</li><li>Förväntar sig din organisation granskningskontroller för gäst/extern åtkomst?</li></ul>|
|![bild desc](../../media/next_steps.png)|Nästa steg|<ul><li>Dokumentkrav för gäst/extern åtkomst för vissa klassificerade grupper, inklusive kvarhållningsperiod och förekomst.</li><li>Dokumentorganisationens krav för vilka grupper som kräver användningsvillkor och åtkomstgranskning. </li><li>Utför recensioner för att effektivt hantera gruppmedlemskap för både interna användare och gästanvändare.</li></ul>|


#### <a name="resources"></a>*Resurser*
- [Samarbeta med personer utanför organisationen](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization)
- [Hantera gäståtkomst i Microsoft 365-grupper](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups)
- [Gäståtkomst i Microsoft 365-grupper](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)
- [Azure AD-åtkomstgranskningar](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)
- [Funktionen Användningsvillkor för Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-tou)
- [Google Federation](https://docs.microsoft.com/azure/active-directory/b2b/google-federation)

### <a name="group-policies--information-protection"></a><a name="group-policies--information-protection"></a>Grupprinciper & informationsskydd
Microsoft 365 Groups bygger på de avancerade säkerhets- och efterlevnadsfunktionerna i Microsoft 365 och stöder klassificeringar, granskning och rapportering, efterlevnadsinnehållssökning, e-identifiering, legal hold och bevarandeprinciper.
>[!Tip]
>- Konfigurera klassificering, användningsriktlinjer och etiketter som är anpassade till organisationens behov.
>- Bevarandeprinciper kan definieras oberoende av etiketter.
>- Revisionsgrupper verksamhet: skapande, radering, etc.
>- Hantera gruppsekretess och gäståtkomst baserat på klassificering.

|         |         |         |
|---------|---------|---------|
|![bild desc](../../media/decision_point.png)|Beslutspunkter|<ul><li>Har din organisation specifika användningskrav som måste meddelas alla användare?</li><li>Kräver din organisation klassificeringar av allt innehåll?</li><li>Kräver din organisation att innehåll ska behållas under en viss tidsperiod?</li><li>Kräver din organisation att specifika principer för datalagring tillämpas på grupper?</li><li>Förväntar sig din organisation att kräva möjligheten att arkivera inaktiva grupper för att bevara innehållet?</li><li>Behöver gruppskapare möjlighet att tilldela organisationsspecifika klassificeringar till team?</li></ul>|
|![bild desc](../../media/next_steps.png)|Nästa steg|<ul><li>Dokumentera organisationens användningsriktlinjer för grupper</li><li>Dokumentera organisationens krav för klassificering.</li><li>Bestäm de principer som ska tillämpas baserat på klassificeringen t.ex.</li><li>Definiera känslighetsetiketterna för din organisation och vilka skyddsinställningar du vill ska associeras.</li><li>Definiera en etikettprincip för att styra vilka användare och grupper som ser dessa etiketter.</li><li>Konfigurera [förhandsgranskningen av känslighetsetiketten för grupper](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) och börja klassificera grupperna i organisationen.</li><li>Planera att implementera dessa krav som en del av grupputrullningen.</li></ul>|


#### <a name="resources"></a>*Resurser*
- [Länka till användningsriktlinjerna för Microsoft 365-grupper](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#link-to-your-office-365-groups-usage-guidelines)
- [Skapa klassificeringar för Office-grupper i organisationen](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- [Konfigurera gruppinställningar](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets)
- [Översikt över bevarandeprinciper](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)
- [Översikt över känslighetsetiketter](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)
- [Översikt över etiketter](https://docs.microsoft.com/microsoft-365/compliance/labels)
- [Söka i granskningsloggen](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)
- [Skapa eller ta bort en juridisk spärr på plats](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)
- [Skapa en bevarandeprincip](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)
- [Köra en innehållssökning i Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/content-search)
- [Mass skapa och publicera kvarhållningsetiketter med hjälp av PowerShell](https://docs.microsoft.com/microsoft-365/compliance/bulk-create-publish-labels-using-powershell)

### <a name="upgrade-traditional-collaboration-tools"></a><a name="upgrade-traditional-collaboration-tools"></a>Uppgradera traditionella samarbetsverktyg
I åratal har organisationer förlitat sig på distributionsgrupper för att kommunicera och samarbeta med grupper av människor både inom och utanför företaget. Nu erbjuder dock Microsoft 365 Groups i Outlook en mer kraftfull lösning för samarbete. Dessutom är det viktigt att kunna ansluta en Microsoft 365-grupp till en befintlig SharePoint-webbplats om du vill modernisera webbplatsen.

>[!Tip]
>- Uppgradera enkelt alla dina kvalificerade distributionslistor på några sekunder via Administrationscentret för Exchange eller med PowerShell-cmdlets.
>- Anslut befintliga SharePoint-gruppwebbplatser till nya Microsoft 365-grupper.

|         |         |         |
|---------|---------|---------|
|![bild desc](../../media/decision_point.png)|Beslutspunkter|<ul><li>Har din organisation distributionslistor som inte är [berättigade till](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists#how-do-i-check-which-dls-are-eligible-for-upgrade) uppgradering?<li>Bestäm vilken typ av grupp som är den distributionslista som bäst migreras till.</li></ul>|
|![bild desc](../../media/next_steps.png)|Nästa steg|<ul><li>Identifiera vilka distributionslistor som skulle vara kandidater för uppgradering till Microsoft 365-grupper.</li><li>Analysera dina befintliga SharePoint-gruppwebbplatser för att se vilka webbplatser som är redo att vara gruppanslutna.</li><li>Låt andra team i ditt företag veta att du uppgraderade din distributionsgrupp och vilka åtgärder du tog för att göra det framgångsrikt!</li></ul>|


#### <a name="resources"></a>*Resurser*
- [Uppgradera distributionslistor (DL) till grupper i Outlook](https://aka.ms/whyupgradedls)
- Uppgradera med ett klick via Administrationscenter för Exchange eller via [PowerShell-skript](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists)
- [Migrera distributionslistor till Microsoft 365 Groups - Hjälp om administratörer](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)
- [Ansluta befintliga SharePoint-webbplatser till Microsoft 365-grupper:](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group)
- [Analysera och använda skannerdata](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group-scanner)
- [Moderniseringsskanner för SharePoint](https://github.com/SharePoint/sp-dev-modernization/tree/master/Tools/SharePoint.Modernization) (ett verktyg som finns på GitHub)

### <a name="groups-reporting"></a><a name="groups-reporting"></a>Rapporter från grupper
Instrumentpanelen Microsoft 365 Reports visar aktivitetsöversikten för Microsoft-produkter i organisationen. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt.
> [!TIP]
>- Du kan använda grupprapporterna för att få insikter om aktiviteten i Microsoft 365-grupper i organisationen och se hur många grupper som skapas och används.
>-Microsoft 365 Groups rapport kan visas för trender under de senaste 7 dagarna, 30 dagar, 90 dagar eller 180 dagar.
>- Övervaka gruppaktivitet över grupppostlörlådekonversationer, gruppwebbplats/filaktivitet, information om gruppmedlemskap inklusive externa medlemsantal.
>- Övervaka regelbundet för att nå ut till gruppägare i aktiva grupper för att lära sig använda ärenden och förstärka dem internt.
>- Utnyttja Power BI-innehållspaket för ytterligare insikter.


|         |         |         |
|---------|---------|---------|
|![bild desc](../../media/decision_point.png)|Beslutspunkter|<ul><li>Kräver din organisation regelbundna rapporter för att förstå användningen av Microsoft 365-grupper?<li>Kräver din organisation rapportering om alla grupper som har externa medlemmar?</li></ul>|
|![bild desc](../../media/next_steps.png)|Nästa steg|<ul><li>Dokumentera organisationens krav för att regelbundet granska gruppers aktivitetsrapporter.</li></ul>|


#### <a name="resources"></a>*Resurser*
- [Microsoft 365-rapporter i administrationscentret](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)
- [Innehållspaket för office 365-införande](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics)
- [Azure AD-innehållspaket](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-power-bi-content-pack-how-to)
- [Aktivitets-API för Microsoft Graph-grupper](https://developer.microsoft.com/graph/docs/api-reference/v1.0/resources/office_365_groups_activity_reports)
- [Microsoft 365 Groups-rapport (enhetliga grupper)](https://gallery.technet.microsoft.com/office/Office-365-Groups-Report-7e3e161b)
- [Granskningsaktivitetsrapporter i Azure Active Directory-portalen](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-audit-logs)
- [Microsoft Graph - Använd deltafråga för att spåra ändringar](https://docs.microsoft.com/graph/delta-query-overview)

## <a name="getting-started-based-on-your-cloud-adoption-journey"></a>Komma igång baserat på din resa för molnanvändning

Microsoft 365 Groups tillhandahåller en omfattande uppsättning styrningsfunktioner som din organisation kan behöva. Överväg följande organisationsprofiler som vägledning för att förstå bästa praxis, ställ rätt frågor för att fastställa kraven för styrning och hur de ska uppfyllas.

**Tänk på följande organisationsprofiler:**
- Småföretag
- Medelstora företag
- Reglerat eller företagande

### <a name="small-business"></a>Småföretag
Tänk dig en organisation som har distribuerat Microsoft 365 med minst Exchange Online- och SharePoint Online-licenser som innehåller Business Essentials- och Business Premium-abonnemangen och Enterprise E1-, E3- och E5-abonnemangen utan Azure Active Director Premium-licensiering.

| Scenen | Beskrivning |
| --------------- | ------------------------------------------------------------ |
| Vägledning |<ul><li>Överväg en etableringsmodell för självbetjäning.</li><li> Grupper i Outlook & SharePoint-webbplatser är [privata som standard](https://techcommunity.microsoft.com/t5/Office-365-Groups/Groups-in-Outlook-and-Group-connected-team-sites-are-now-private/m-p/186395).</li><li> Grupper kan skapas genom att uppgradera befintliga distributionslistor (DLs) antingen en efter en eller i grupp via PowerShell. Se [Distributionslistor för uppgraderar till Microsoft 365-grupper](https://docs.microsoft.com/microsoft-365/admin/manage/upgrade-distribution-lists).</li><li> Aktivera gäståtkomst men styr med hjälp av tillåt/blockera gästdomäner.</li><li> Använd grupprapportering för att få insikter om hur användare använder grupper.</li><li> Överväg att skapa ett Microsoft Teams-team för hela organisationen som ett sätt för alla att vara en del av ett enda team för samarbete. </li></ul>|
| Nästa steg      |<ul><li>Överväg att använda [platsdesign och platsskript](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview) för att definiera standarddesignen för kontroller med hjälp av de åtgärder som definierats i [JSON-schemareferensen](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema).</li><li>Granska [grupper som rapporterar](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups).</li><li>Spåra totala grupper och inaktiva/aktiva grupper.</li><li>Spåra både Exchange- och SharePoint-lagring som används.</li><li>Visa gruppaktivitet över grupppostlådekonversationer, gruppwebbplats/filaktivitet osv.</li></ul> |

### <a name="medium-sized-business"></a>Medelstora företag
Utöver ovanstående rekommendationer bör följande gäller för medelstora företag som har distribuerat Microsoft 365 med minst en Enterprise E3/E5 med Azure Active Directory Premium P1-licenser.

| Scenen | Beskrivning |
| --------------- | ------------------------------------------------------------ |
| Vägledning |<ul><li>Besluta om en öppen eller IT-ledd etableringsmodell.</li><li> Överväg att skapa vissa grupper som är knutna till [dynamiska medlemskapsregler](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) baserat på Azure AD-attribut som Avdelning</li><li> Definiera klassificeringar inom din organisation t.ex.</li><li>  Definiera principerna baserat på klassificering, till exempel kvarhållning och känslighet.</li><li> SharePoint är innehållstjänsten för varje Microsoft 365-grupp. Överväg att utforma och [distribuera SharePoint Online-webbplatser för tre skyddsnivåer](https://docs.microsoft.com/office365/enterprise/deploy-sharepoint-online-sites-for-three-tiers-of-protection) (baslinje, känslig och mycket konfidentiell). Mer information om dessa tre skyddsnivåer finns i [Säkra SharePoint Online-webbplatser och filer](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files).</li><li> Både offentliga och privata grupper visas som standard i GAL. Bestäm vilka grupper du vill ska visas i gal-grupper som skapats utanför Microsoft Teams.  Använd [cmdleten Set-UnifiedGroup](https://technet.microsoft.com/library/mt238274(v=exchg.160).aspx) för att dölja specifika grupper.</li></ul> |
| Nästa steg      |<ul><li>Definiera riktlinjer för [användning](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets) för att utbilda användarna om metodtips som hjälper till att hålla deras grupper effektiva och utbilda dem i interna innehållsprinciper. Till exempel förstå klassificeringar, principer och procedurer. </li><li>Definiera grupplivscykelperioden som grupper måste förnyas eller tas bort - utgångsprincipen.</li><li>Överväg att skapa följande anpassade jobb för att implementera principer baserat på klassificeringar.</li><li>Ställ in sekretess till privat.</li><li>Inaktivera externt medlemskap/delning. </li><li>E-postmeddelanden för att meddela gruppmedlemmar för grupper [utan ägare](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732).</li><li>Genomdriva ägarpolicy (min. 2 ägare).</li><li> Definiera bevarandeprinciper för grupper baserat på klassificering. </li><li>Översikt över bevarandeprinciper.</li><li>Använda Powershell för att identifiera grupper med en klassificering och [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy?view=exchange-ps).</li><li>Överväg att använda platsdesign och platsskript för att definiera kontrollerna med hjälp av de åtgärder som definierats i [JSON-schemareferensen](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema).</li><li>Överväg att skapa [en enkel platskatalog med hjälp av en webbplatsdesign](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-trigger-flow-tutorial) och Microsoft Flow. När en webbplats skapas med hjälp av denna webbplats design, information om webbplatsen fångas och skrivas till en lista. </li></ul>|

### <a name="regulated-or-enterprise"></a>Reglerat eller företagande
Utöver ovanstående rekommendationer överväga följande för starkt reglerade eller stora företag som myndigheter, finansiella tjänster eller hälso-och sjukvård som har distribuerat Office 365 med minst en Enterprise E3/E5 med Azure Active Directory Premium P1/P2 licenser.

| Scenen | Beskrivning |
| --------------- | ------------------------------------------------------------ |
| Vägledning |<ul><li> Definiera principer för datastyrning av Den SharePoint-webbplats som är associerad med gruppen baserat på klassificering.</li><li>[Skydda SharePoint Online-filer med etiketter och DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</li><li>[Skydda SharePoint Online-filer med Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</li><li> Gruppplats som etablerats i regionen som är kopplad till användarens önskade dataplats ([multi-geo](https://docs.microsoft.com/office365/enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-office-365)).</li><li> Medlemskap recensioner för grupper med externa medlemmar ([tillgång recensioner](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-access-reviews-overview)).</li><li>Se till att anställda eller gästanvändare ser relevanta ansvarsfriskrivningar för juridiska krav eller efterlevnadskrav innan de får åtkomst. [(användarvillkor).](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou)</li><li>Identifiera och rapportera om Microsoft 365-grupper med en viss [klassificering som också har externa användare](https://techcommunity.microsoft.com/t5/Office-365-Groups/Sample-Powershell-to-identify-groups-with-HBI-classification-and/m-p/215561).</li><li>Hemliga grupper där medlemskap som behövde döljas måste skapas med cmdleten [New-UnifiedGroup](https://technet.microsoft.com/library/mt219359(v=exchg.160).aspx) (med växeln HiddenGroup-MembershipEnabled) när gruppen skapas.</li><li>Definiera [känslighetsetiketterna](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) för organisationen för att [begränsa åtkomsten till innehåll genom att använda kryptering](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) och publicera till specifika Microsoft 365-grupper.</li><li>Förhindra att känsligt innehåll lämnar organisationen på enheter som kör Windows med [känslighetsetiketter med Windows Informationsskydd](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553). |
| Nästa steg      | <ul><li> Använd webbplatsdesign och platsskript för att definiera [standardåtgärder](https://developer.microsoft.com/office/blogs/site-scripts-site-designs-summer-2018-update/) som inträffar när en ny plats skapas. Konfigurera till exempel [inställningen för extern delning](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-apply-external-sharing-setting) eller [utlösa ett Microsoft Flow för att anropa en Azure-funktion](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-azure-function) för att tillämpa konfigurationer som inte stöds internt. </li><li> Dokumentkrav för att [skydda SharePoint Online-filer med etiketter och DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) till webbplatser som är kopplade till Microsoft 365-grupper.</li><li>Dokumentera organisationens krav på [säkra SharePoint Online-webbplatser och filer](https://docs.microsoft.com/microsoft-365/security/office-365-security/secure-sharepoint-online-sites-and-files) som är anslutna till Microsoft 365-grupper. </li><li>Dokumentera organisationens krav på att publicera [känslighetsetiketter](hhttps://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) till specifika användare eller grupper för att skydda innehåll.</li></ul> |

## <a name="groups-management-capability-planning-checklist"></a>Checklista för planering av funktioner för grupphantering

Ett antal grupprelaterade kontroller kan administreras via Azure Active Directory. Mer information om hur du konfigurerar gruppinställningar finns i [Azure Active Directory-cmdletar för att konfigurera gruppinställningar](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).

Använd följande tabell för att avgöra vilka funktioner du behöver för att distribuera dina organisationers krav. Det hjälper dig att avgöra vilka licenser du behöver så att du kan planera i förväg.

| **Kapacitet**      | **Information**                                    | **Azure AD Premium-licens krävs** | **Beslut** |
| ------------------- | ---------------------------------------------- | ------------------------------------- | ------------ |
| Gruppnamngivningsprincip | Använd Prefix-Suffix-baserade, anpassade blockerade ord. | P1 (S1)                                    |      Tbd     |
| Gruppklassificering | Tilldela klassificeringar till team. | P1 (S1)                                    |   Tbd        |
| Grupp gäståtkomst | Tillåt eller förhindra att gäster läggs till i grupper. | Nej                                    |  Tbd        |
| Skapa grupper | Begränsa gruppskapandet till administratörer. | Nej                                    |   Tbd        |
| Skapa grupper | Begränsa gruppskapandet till medlemmar i säkerhetsgruppen. | P1 (S1)                                    |     Tbd      |
| Riktlinjer för gruppanvändning | Ange en länk till riktlinjerna för gruppanvändning som ska visas på alla slutpunkter för gruppskapande. | P1 (S1)                                    |   Tbd        |
| Dolt medlemskap | Dölja medlemmarna i Microsoft 365-gruppen från användare som inte är medlemmar i gruppen | Nej                                    |   Tbd        |
| Princip för förfallodatum | Hantera livscykeln för Microsoft 365-grupper genom att ange en förfalloprincip. | P1 (S1)                                    |  Tbd        |
| Gruppaktivitetsrapporter | Få insikter om aktiviteten i Microsoft 365-grupper i organisationen och se hur många Microsoft 365-grupper som skapas och används. | Nej                                    |    Tbd       |
| Loggperiodsprincip | Behålla eller ta bort data under en viss tidsperiod genom att ange bevarandeprinciper för Microsoft 365-grupper i Security & Compliance Center. **Obs:** För att använda den här funktionen krävs licensiering av Office 365 Enterprise E3 eller senare. | Nej                                    |    Tbd       |
| Policy för förebyggande av dataförlust | Identifiera känslig information på microsoft 365-gruppanslutna webbplatser och förhindra oavsiktlig delning. **Obs:** För att använda den här funktionen krävs licensiering av Office 365 Enterprise E3 eller senare. | Nej                                    |     Tbd      |
| Arkivera och återställa | Arkivera ett team när det inte längre är aktivt men du vill behålla det som referens eller återaktivera i framtiden. | Nej                                    |   Tbd        |
| Access Recensioner | Utföra recensioner för att effektivt hantera gruppmedlemskap för både interna användare och gästanvändare | P2 (S2)                                    |   Tbd       |
| Användarvillkor | En enkel metod som organisationer kan använda för att presentera information för slutanvändare. Den här presentationen säkerställer att användarna ser relevanta ansvarsfriskrivningar för juridiska krav eller efterlevnadskrav. | P1 (S1)                                    |         Tbd  |

