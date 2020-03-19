---
title: Styrning av plan för Office 365-grupper
ms.reviewer: johasand
f1.keywords:
- NOCSH
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
search.appverid:
- BCS160
- MET150
- MOE150
- BSA160
description: Läs om hur du planerar för styrningav Office 365-grupper.
ms.openlocfilehash: b79da69995446aa7e61eea4d836e322743a7d2bb
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42807997"
---
# <a name="plan-for-governance-in-office-365-groups"></a>Planera för styrning i Office 365-grupper

Office 365-grupper har en omfattande uppsättning verktyg för att implementera alla styrningsfunktioner som din organisation kan behöva. Den här artikeln vägleder IT-proffsen att ställa rätt frågor för att avgöra deras krav på styrning och hur de ska uppfyllas baserat på deras organisationsprofil.

## <a name="why-office-365-groups"></a>Varför Office 365-grupper?
![bild desc](../../media/01.png)

Vi vet att organisationer idag använder en mångsidig verktygshelhet. Det finns ett team av utvecklare som använder teamchatt, chefer som skickar e-post och hela organisationen som ansluter via företagets sociala. Flera samarbetsverktyg används eftersom varje grupp är unik och har sina egna funktionella behov och arbetsstil. Vissa kommer bara att använda e-post medan andra kommer att leva främst i chatten. 

Om användarna känner att IT-verktygen inte passar deras behov kommer de sannolikt att ladda ner sin favoritkonsumentapp som stöder deras scenarier. Även om den här processen tillåter användare att komma igång snabbt, leder det till en frustrerande användarupplevelse i hela organisationen med flera inloggningar, svårigheter att dela och ingen enskild plats att visa innehåll. Detta koncept kallas "Shadow IT" och utgör en betydande risk för organisationer. Det minskar möjligheten att hantera användaråtkomst på ett enhetligt sätt, säkerställa säkerhets- och serviceefterlevnadsbehov.

Office 365-grupper ger användarna möjlighet och minskar risken för skugg-IT genom att i ett enda steg tillhandahålla många av de verktyg som behövs för att samarbeta. Med Office 365-grupper kan du välja en uppsättning personer som du vill samarbeta med och enkelt skapa en samling resurser som dessa personer kan dela med. Att manuellt tilldela behörigheter till resurser är ett objekt i det förflutna då tillägg av medlemmar i gruppen automatiskt ger de behörigheter som behövs för alla tillgångar som tillhandahålls av gruppen.

## <a name="technical-architecture"></a>Teknisk arkitektur

Det finns tre huvudsakliga kommunikationsmetoder som stöds av Office 365-grupper. Grupper kan skapas i dessa upplevelser och användas i Office 365-paketet:
- [Outlook](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2): samarbete via e-post med en delad gruppinkorg och kalender
- [Microsoft Teams](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2): en beständig chattbaserad arbetsyta där du kan ha informella, realtidssamtal kring en mängd olika ämnen, ordnade av specifika undergrupper
- [Yammer](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2): företagssocial erfarenhet för samarbete

> [!NOTE]
> Genom att skapa en ny grupp via andra teamwork-program , till exempel SharePoint, Planner eller Stream, skapas en grupp med en Outlook-kommunikationsmodalitet med möjlighet att ansluta till Microsoft Teams.

Beroende på var en grupp skapas etableras vissa resurser automatiskt, till exempel:
- [Inkorg](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22) - För e-postkonversationer mellan dina medlemmar. Denna inkorg har en e-postadress och kan ställas in för att acceptera meddelanden från personer utanför gruppen och även utanför din organisation, ungefär som en traditionell distributionslista.
 - [Kalender](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a) – För schemaläggning av händelser relaterade till gruppen
- [SharePoint-gruppwebbplats](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e) – En central databas för information, länkar och innehåll som rör din grupp
- [SharePoint-dokumentbibliotek](https://support.office.com/article/share-group-files-749bc73b-90c9-4760-9b6f-9aa1cf01b403) – En central plats för gruppen att lagra och dela filer
- [OneNote Notebook](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97) – För insamling av idéer, forskning och information
- [Planerare](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) – för att tilldela och hantera projektuppgifter mellan dina gruppmedlemmar
- [Yammer Group](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2) - En gemensam plats att ha samtal och dela information
- Microsoft Teams – En chattbaserad arbetsyta i Office 365

Mer information om vilka resurser som skapas för varje grupp finns i [Lär dig mer om Office 365-grupper](https://support.office.com/article/learn-about-office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

> [!NOTE]
> När en ny Office 365-grupp skapas via Yammer eller Teams visas gruppen inte i Outlook eller adressboken eftersom den primära kommunikationen mellan dessa användare sker i deras respektive klienter.

> [!IMPORTANT]
> När en ny Yammer-grupp skapas skapar inte gruppen Office 365 en grupppostlåda eller kalenderresurs. Därför kan en Yammer-grupp inte anslutas till Microsoft Teams. Se [Yammer och grupper](https://docs.microsoft.com/yammer/manage-yammer-groups/yammer-and-office-365-groups)

## <a name="where-to-start-a-conversation"></a>Var du ska starta en konversation
Det finns flera ställen där du kan föra en konversation i Office 365. Om du förstår var en konversation ska startas kan organisationer definiera en kommunikationsstrategi.

![bild desc](../../media/02.png)

- Team: chattbaserad arbetsyta (samarbete med hög hastighet) – inre loop
   - Byggd för samarbete med de människor du arbetar med varje dag
  - Sätter information till hands för användarna i en enda upplevelse
  - Lägga till flikar, kontakter och robotar
  - Livechatt, ljud-/videokonferenser, inspelade möten.

- Yammer: anslut över org (enterprise social) - yttre slinga
  - Communities of Practice - Tvärfunktionella grupper av människor som delar ett gemensamt intresse eller expertis men inte nödvändigtvis arbetar tillsammans på en daglig basis
  - Ledarskapsförbindelse, inlärningsgemenskaper, rollbaserade samhällen

- Outlook-grupper: moderna DL (e-postbaserat samarbete)
  - Allestädes närvarande för riktad kommunikation
  - Uppgradera DLs till Office 365-grupper – [Varför bör du uppgradera?](https://support.office.com/article/why-you-should-upgrade-your-distribution-lists-to-groups-in-outlook-7fb3d880-593b-4909-aafa-950dd50ce188)

- SharePoint – Core-innehållssamarbete för alla Office 365-grupper
  - Varje grupp får en ansluten SharePoint-gruppwebbplats
  - Dela innehåll, skapa anpassade sidor och författare nyheter
  - [Ansluta](https://docs.microsoft.com/sharepoint/dev/features/groupify/groupify-overview) befintliga SharePoint-gruppwebbplatser till nya Office 365-grupper

![bild desc](../../media/03.png)

##  <a name="managing-and-governing-office-365-at-scale"></a>Hantera och styra Office 365 i stor skala

Office 365-grupper har en omfattande uppsättning verktyg för att implementera alla styrningsfunktioner som din organisation kan behöva. I följande avsnitt beskrivs funktionerna, rekommenderar bästa praxis och ger vägledning för att ställa rätt frågor för att fastställa kraven för styrning och hur de ska uppfyllas.

**I detta avsnitt:**
- [Styra vem som kan skapa Office 365-grupper](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#control-who-can-create-office-365-groups)
- [Gruppera mjuk borttagning och återställning](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-soft-delete-and-restore)
- [Princip för gruppnamn](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-naming-policy)
- [Princip för förfallodatum för grupper](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-expiration-policy)
- [Tillgång till gruppgäst](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-guest-access)
- [Grupprinciper & informationsskydd](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#group-policies--information-protection)
- [Uppgradera traditionella samarbetsverktyg](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#upgrade-traditional-collaboration-tools)
- [Grupper som rapporterar](https://docs.microsoft.com/office365/admin/create-groups/plan-for-groups-governance#groups-reporting)

### <a name="control-who-can-create-office-365-groups"></a>Styra vem som kan skapa Office 365-grupper
Grupper kan skapas av slutanvändare från flera slutpunkter, inklusive Outlook, SharePoint, Microsoft Teams och andra miljöer.

![bild desc](../../media/04.png)
> [!Tip]
>- Anser starkt självbetjäning för att stärka gruppägare.
>- Dokumentera och kommunicera hur du begär en grupp.
>- Se över vem som kan skapa grupper under din molnresa.
>- Överväg att använda dynamiskt medlemskap för att konfigurera säkerhetsgruppens medlemmar för att styra gruppskapande.
>- Utvärdera vilka grupper scenarier som kan hanteras via ett dynamiskt medlemskap och tillåta självbetjäning för resten.

Det finns tre primära modeller för etablering i grupper: Öppna, IT-ledda eller kontrollerade. I följande tabell beskrivs fördelarna med varje modell.

| Modell          | Fördelar                                                   |
| -------------- | ------------------------------------------------------------ |
| Öppna (standard) | Användare kan skapa sina egna grupper efter behov utan att behöva vänta på, eller bry sig om IT. |
| IT-ledda         | Användare begär en grupp från IT. IT kan vägleda dem att välja de bästa samarbetsverktygen för deras behov. |
| Kontrollerade     | Gruppskapande som är begränsat till specifika personer, team eller tjänster. Mer information finns i [Hantera vilka som kan skapa Office 365-grupper](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618). |

Din organisation kan ha specifika krav för att implementera strikta kontroller för vem som kan skapa grupper. Använd följande tabell för att fatta beslut om vilken etableringsmodell som passar din organisation.

|         |         |         |
|---------|---------|---------|
|![bild desc](../../media/decision_point.png)|Beslutspunkter|<ul><li>Vilken etableringsmodell passar dina organisationskrav?</li><li>Kräver din organisation att du begränsar gruppskapandet till administratörer?</li><li>Kräver din organisation att du begränsar gruppskapandet till medlemmar i säkerhetsgruppen?</li><li>Kräver din organisation att vissa grupper skapas dynamiskt baserat på användarattribut, till exempel avdelning?</li></ul>|
|![bild desc](../../media/next_steps.png)|Nästa steg|<ul><li>Dokumentera organisationens krav på grupp- och teamskapande.</li><li>Planera att implementera dessa krav som en del av gruppdistributionen.</li><li>Kommunicera och publicera dina policyer för att informera användarna om det beteende de kan förvänta sig</li><li>Planera att genomföra dynamiskt medlemskap där så är tillämpligt.</li></ul>|

> [!Important]
> Att begränsa grupp- och teamskapande kan göra användarna långsammare eftersom många Office 365-tjänster kräver att grupper skapas för att tjänsten ska fungera. Mer information finns i [Varför styra vem som skapar Office 365-grupper?](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide%23why-control-who-creates-office-365-groups)

#### <a name="resources"></a>*Resurser*
- [Hantera vem som kan skapa Office 365-grupper](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups?view=o365-worldwide)
- [Fylla i grupper dynamiskt baserat på objektattribut](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-with-advanced-rules)
- [Så här ändrar du standardinställningen för Office 365-grupper för Outlook, till offentliga eller privata](https://support.office.com/article/office-365-groups-in-outlook-private-by-default-36236e39-26d3-420b-b0ac-8072d2d2bedc)
- [Synkronisera säkerhetsgrupper med gruppmedlemskap](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Syncing-Security-Groups-with-team-membership/ba-p/241959)

### <a name="group-soft-delete-and-restore"></a>Gruppera mjuk borttagning och återställning
En Office 365-grupp som du tagit bort sparas som regel i 30 dagar. Den här 30-dagarsperioden kallas "mjuk borttagning" eftersom du fortfarande kan återställa gruppen. Efter 30 dagar tas gruppen och det tillhörande innehållet bort permanent och kan inte återställas.

> [!Tip]
>- Kommunicera återställningsprocessen till användarna.
>- Träna ditt helpdeskteam.
>- Spåra kommande grupper som tas bort med PowerShell-skriptet.

|         |         |         |
|---------|---------|---------|
|![bild desc](../../media/decision_point.png)|Beslutspunkter|<ul><li>Kräver du att vissa tillgångar ska arkiveras för långsiktig lagring?</li><li>Har du vissa lagringskrav för din organisation?</li></ul>|
|![bild desc](../../media/next_steps.png)|Nästa steg|<ul><li>Kommunicera och publicera policyerna för att informera användarna om det beteende de kan förvänta sig </li><li> Dokumentera organisationens krav för övervakning av borttagna grupper.</li><li>Planera att implementera dessa krav som en del av gruppdistributionen.</li></ul>|

> [!Important]
>Om en användare försöker komma åt webbplatsen under perioden "mjuk borttagning" får de ett meddelande med 403 - Förbjudet. Om användaren försöker komma åt webbplatsen efter den här perioden får de ett meddelande med 404 - Hittades inte

#### <a name="resources"></a>*Resurser*
- [Återställa en borttagen Office 365-grupp](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54?ui=en-US&rs=en-001&ad=US)
- [Återställa en borttagen Office 365-grupp i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-restore-deleted)
- [Ta bort grupper med hjälp av cmdleten Remove-UnifiedGroup](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)

### <a name="group-naming-policy"></a>Princip för gruppnamn
En namngivningsprincip kan hjälpa dig och användarna att identifiera funktionen för gruppen, medlemskap, geografisk region eller vem som skapade gruppen. Namngivningsprincipen kan också hjälpa till att kategorisera grupper i adressboken. Du kan använda principen för att blockera specifika ord från att användas i gruppnamn och alias.

> [!Tip]
> - Använd korta strängar som suffix.
> - Använd attribut med värden.
> - Var inte för kreativ, den totala namnlängden har högst 264 tecken.
> - Ladda upp dina organisationsspecifika blockerade ord för att begränsa användningen.


|         |         |         |
|---------|---------|---------|
|![bild desc](../../media/decision_point.png)|Beslutspunkter|<ul><li>Kräver din organisation en specifik namngivningskonvention för grupper?</li><li>Kräver din organisation namngivningskonventionen för alla arbetsbelastningar?</li><li>Har din organisation specifika ord som du vill hindra användare från att använda?</li></ul>|
|![bild desc](../../media/next_steps.png)|Nästa steg|<ul><li>Dokumentera organisationens krav för namngivningsgrupper. </li><li> Planera att implementera dessa krav som en del av gruppdistributionen.</li><li> Kommunicera och publicera namngivningsprinciper och standarder för att informera användarna.</li></ul>|

> [!Important]
>Namngivningsprincipen tillämpas på grupper som skapas i alla gruppers arbetsbelastningar (som Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc). Den tillämpas på både gruppnamnet och gruppaliaset. Den tillämpas när en användare skapar en grupp och när gruppnamn eller alias redigeras för en befintlig grupp.

#### <a name="resources"></a>*Resurser*
- [Namngivningsprincip för Office 365-grupper](https://docs.microsoft.com/office365/admin/create-groups/groups-naming-policy)
- [Tillämpa en namngivningsprincip för Office 365-grupper i Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=868340)
- [Azure Active Directory-cmdlets för konfigurera gruppinställningar](https://go.microsoft.com/fwlink/?linkid=868341)
- [Förhandsgranska funktioner för gruppnamngivning](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/NamingPolicy)

### <a name="group-expiration-policy"></a>Princip för förfallodatum för grupper
Administratörer kan ange en förfallotid och alla grupper som når slutet av den perioden och inte förnyas tas bort. Förfallotiden börjar när gruppen skapas eller det datum då den senast förnyades. Gruppägare skickas automatiskt ett e-postmeddelande före förfallodagen som gör att de kan förnya gruppen för ett annat utgångsdatum.

När du har angett att en grupp ska upphöra att gälla:
- Ägare av gruppen meddelas att förnya gruppen som utgångsdatum närmar sig
- Alla grupper som inte förnyas tas bort
- Alla grupper som tas bort kan återställas inom 30 dagar av gruppägarna eller administratören

> [!Tip]
> - Pilot med specifika grupper inledningsvis.
> - Välj inaktiva grupper baserat på aktivitetsrapporten i Administrationscentret för Microsoft 365.
> - Kommunicera förnyelseprocessen till gruppägare.
> - Ombord på ditt helpdesk-team.
> - Se till att grupper har flera ägare och konfigurera e-post för överblivna grupper.


|         |         |         |
|---------|---------|---------|
|![bild desc](../../media/decision_point.png)|Beslutspunkter|<ul><li>Kräver din organisation att ange ett utgångsdatum för team?</li><li>Bestäm strategin för att hantera föräldralösa grupper?</li></ul>|
|![bild desc](../../media/next_steps.png)|Nästa steg|<ul><li>Dokumentera organisationens krav på gruppförfallodatum, datalagring och arkivering.</li><li>Planera att implementera dessa krav som en del av gruppdistributionen.</li><li>Planera att implementera ett anpassat jobb för att rapportera om grupper som har enskilda ägare eller som är ägarlösa. </li></ul>|

> [!Important]
>När du ändrar förfalloprincipen beräknas tjänsten om utgångsdatumet för varje grupp. Den börjar alltid räkna från det datum då gruppen skapades och tillämpar sedan den nya förfalloprincipen.

#### <a name="resources"></a>*Resurser*
- [Förfalloprincip för Office 365-grupper](https://support.office.com/article/Office-365-Group-Expiration-Policy-8d253fe5-0e09-4b3c-8b5e-f48def064733?ui=en-US&rs=en-US&ad=US)
- [Konfigurera förfalloprincipen för Office 365-grupper](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-lifecycle)

### <a name="group-guest-access"></a>Tillgång till gruppgäst
Administratörer kan styra om gäståtkomst till Office 365-grupper för hela organisationen eller för enskilda Office 365-grupper ska tillåtas. De kan också styra vem som kan tillåta gäster att läggas till i grupper.
>[!Tip]
>- Aktivera gäståtkomst på klientnivå. Om det behövs blockerar du för specifika grupper.
>- Styra använda tillåt / blockera gästdomäner, gäst inbjudaroll, åtkomstrecensioner, användarvillkor.
>- Spåra gästanvändaraktivitet via granskningsloggar.

|         |         |         |
|---------|---------|---------|
|![bild desc](../../media/decision_point.png)|Beslutspunkter|<ul><li>Behöver du begränsa möjligheten att lägga till gäster i lag per grupp?</li><li> Behöver din organisation presentera relevanta ansvarsfriskrivningar för juridiska krav eller efterlevnadskrav?</li><li>Har din organisation behov av att minska administrativa överhuvudet för att lägga till och ta bort användare?</li><li>Förväntar sig din organisation granskningskontroller för gäst/extern åtkomst?</li></ul>|
|![bild desc](../../media/next_steps.png)|Nästa steg|<ul><li>Dokumentkrav för gäst/extern åtkomst för vissa klassificerade grupper, inklusive kvarhållningsperiod och förekomst.</li><li>Dokumentorganisations krav för vilka grupper kräver användarvillkor och åtkomstgranskning. </li><li>Utför granskningar för att effektivt hantera gruppmedlemskap för både interna användare och gästanvändare.</li></ul>|


#### <a name="resources"></a>*Resurser*
- [Hantera gäståtkomst i Office 365-grupper](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups)
- [Gäståtkomst i Office 365-grupper](https://support.office.com/article/Guest-access-in-Office-365-Groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)
- [Gäståtkomst i Office 365-grupper – hjälp för administratörer](https://support.office.com/article/Guest-access-to-Office-365-groups-Admin-Help-7c713d74-a144-4eab-92e7-d50df526ff96)
- [Azure AD-åtkomstrecensioner](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)
- [Funktionen Användningsvillkor för Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-tou)
- [Google Federation](https://docs.microsoft.com/azure/active-directory/b2b/google-federation)
- [Auktorisera gäståtkomst i Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-dependencies)

### <a name="group-policies--information-protection"></a>Grupprinciper & informationsskydd
Office 365-grupper bygger på avancerade säkerhets- och efterlevnadsfunktioner i Office 365 och stöder klassificeringar, granskning och rapportering, efterlevnadsinnehållssökning, e-identifiering, Juridiskspärr och bevarandeprinciper.
>[!Tip]
>- Konfigurera klassificering, användningsriktlinjer och etiketter som är anpassade till organisationens behov.
>- Bevarandeprinciper kan definieras oberoende av etiketter.
>- Granskningsgruppers verksamhet: skapande, radering osv.
>- Hantera gruppsekretess och gäståtkomst baserat på klassificering.

|         |         |         |
|---------|---------|---------|
|![bild desc](../../media/decision_point.png)|Beslutspunkter|<ul><li>Har din organisation specifika användningskrav som måste meddelas alla användare?</li><li>Kräver din organisation klassificeringar av allt innehåll?</li><li>Kräver din organisation att innehåll ska behållas under en viss tidsperiod?</li><li>Kräver din organisation att specifika principer för datalagring ska ap-psbesa till grupper?</li><li>Förväntar sig din organisation att kräva möjligheten att arkivera inaktiva grupper för att bevara innehållet?</li><li>Behöver gruppskapare möjlighet att tilldela organisationsspecifika klassificeringar till team?</li></ul>|
|![bild desc](../../media/next_steps.png)|Nästa steg|<ul><li>Dokumentera organisationens användningsriktlinjer för grupper</li><li>Dokumentera organisationens krav på klassificering.</li><li>Bestäm vilka principer som ska tillämpas baserat på klassificeringen, t.ex.</li><li>Definiera känslighetsetiketterna för din organisation och vilka skyddsinställningar du vill associera.</li><li>Definiera en etikettprincip för att styra vilka användare och grupper som ser etiketterna.</li><li>Konfigurera [förhandsgranskningen av gruppens känslighetsetikett](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) och börja klassificera grupperna i organisationen.</li><li>Planera att implementera dessa krav som en del av gruppdistributionen.</li></ul>|


#### <a name="resources"></a>*Resurser*
- [Länka till användningsriktlinjerna för Office 365-grupper](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#link-to-your-office-365-groups-usage-guidelines)
- [Skapa klassificeringar för Office-grupper i organisationen](https://docs.microsoft.com/office365/enterprise/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)
- [Konfigurera gruppinställningar](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets)
- [Översikt över bevarandeprinciper](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Översikt över känslighetsetiketter](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)
- [Översikt över etiketter](https://docs.microsoft.com/office365/securitycompliance/labels)
- [Sök i granskningsloggen](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance)
- [Skapa eller ta bort en juridisk spärr på plats](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)
- [Skapa en bevarandeprincip](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Köra en innehållssökning i Office 365 Security & Compliance Center](https://docs.microsoft.com/Office365/SecurityCompliance/content-search)
- [Massskapa och publicera kvarhållningsetiketter med PowerShell](https://docs.microsoft.com/office365/securitycompliance/bulk-create-publish-labels-using-powershell)

### <a name="upgrade-traditional-collaboration-tools"></a>Uppgradera traditionella samarbetsverktyg
I åratal har organisationer förlitat sig på distributionsgrupper för att kommunicera och samarbeta med grupper av människor både inom och utanför företaget. Men nu erbjuder Office 365-grupper i Outlook en mer kraftfull lösning för samarbete. Det är dessutom viktigt att kunna ansluta en Office 365-grupp till en befintlig SharePoint-webbplats om du vill modernisera webbplatsen.

>[!Tip]
>- Uppgradera enkelt alla dina kvalificerade distributionslistor på några sekunder via Administrationscentret för Exchange eller använda PowerShell-cmdlets.
>- Anslut befintliga SharePoint-gruppwebbplatser till nya Office 365-grupper.

|         |         |         |
|---------|---------|---------|
|![bild desc](../../media/decision_point.png)|Beslutspunkter|<ul><li>Har din organisation distributionslistor som inte är [kvalificerade](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists#how-do-i-check-which-dls-are-eligible-for-upgrade) för uppgradering?<li>Ta reda på vilken typ av grupp som är den distributionslista som bäst migreras till?</li></ul>|
|![bild desc](../../media/next_steps.png)|Nästa steg|<ul><li>Identifiera vilka distributionslistor som skulle vara kandidater för uppgradering till Office 365-grupper.</li><li>Analysera dina befintliga SharePoint-gruppwebbplatser för att se vilka webbplatser som är redo att vara gruppanslutna.</li><li>Låt andra team i ditt företag veta att du uppgraderade din distributionsgrupp och vilka åtgärder du vidtog för att göra den framgångsrik!</li></ul>|


#### <a name="resources"></a>*Resurser*
- [DDl (Upgrade Distribution Lists) till grupper i Outlook](https://aka.ms/whyupgradedls):
- [Varför du bör uppgradera din DL till grupper i Outlook](https://aka.ms/whyupgradedls)
- Uppgradera med ett klick via Exchange administrationscenter eller via [PowerShell-skript](https://support.office.com/article/Migrate-distribution-lists-to-Office-365-Groups-Admin-help-787d7a75-e201-46f3-a242-f698162ff09f?ui=en-US&rs=en-US&ad=US)
- [Migrera distributionslistor till Office 365-grupper – hjälp för administratörer](https://docs.microsoft.com/office365/admin/manage/upgrade-distribution-lists)
- [Ansluta befintliga SharePoint-webbplatser till Office 365-grupper:](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group)
- [Analysera och använda skannerdata](https://docs.microsoft.com/sharepoint/dev/transform/modernize-connect-to-office365-group-scanner)
- [SharePoint-moderniseringssskanner (ett](https://github.com/SharePoint/sp-dev-modernization/tree/master/Tools/SharePoint.Modernization) verktyg som finns på GitHub)

### <a name="groups-reporting"></a>Grupper som rapporterar
I Office 365-instrumentpanelen Rapporter ser du en översikt över aktiviteter i Office 365-produkter i din organisation. Här kan du gå in på detaljnivå i rapporter för enskilda produkter för att få bättre insikter om aktiviteterna inom varje produkt.
> [!TIP]
>- Du kan använda aktivitetsrapporterna Grupper för att få insikter i aktiviteten för Office 365-grupper i organisationen och se hur många grupper som skapas och används.
>-Rapporten Office 365-grupper kan visas för trender under de senaste 7 dagarna, 30 dagarna, 90 dagarna eller 180 dagarna.
>- Övervaka gruppaktivitet över grupppostlådekonversationer, gruppwebbplats/fileraktivitet, information kring gruppmedlemskap inklusive externa medlemsantal.
>- Övervaka regelbundet för att nå ut till gruppägare av aktiva grupper för att lära sig användningsfall och förstärka dem internt.
>- Utnyttja Power BI-innehållspaket för ytterligare insikter.


|         |         |         |
|---------|---------|---------|
|![bild desc](../../media/decision_point.png)|Beslutspunkter|<ul><li>Kräver din organisation regelbundna rapporter för att förstå användningen av Office 365-grupper?<li>Kräver din organisation rapportering om alla grupper som har externa medlemmar?</li></ul>|
|![bild desc](../../media/next_steps.png)|Nästa steg|<ul><li>Dokumentera organisationens krav för att regelbundet granska grupperaktivitetsrapporter.</li></ul>|


#### <a name="resources"></a>*Resurser*
- [Office 365-rapporter i administrationscentret](https://support.office.com/article/Office-365-Reports-in-the-admin-center-Office-365-groups-a27f1a99-3557-4f85-9560-a28e3d822a40)
- [Innehållspaket för antagande av Office 365](https://support.office.com/article/Office-365-Adoption-Content-Pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)
- [Azure AD-innehållspaket](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-power-bi-content-pack-how-to)
- [Aktivitets-API för Microsoft Graph-grupper](https://developer.microsoft.com/graph/docs/api-reference/v1.0/resources/office_365_groups_activity_reports)
- [Rapport över Office 365-grupper (enhetliga grupper)](https://gallery.technet.microsoft.com/office/Office-365-Groups-Report-7e3e161b)
- [Granskningsaktivitetsrapporter i Azure Active Directory-portalen](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-audit-logs)
- [Microsoft Graph - Använd deltafråga för att spåra ändringar](https://docs.microsoft.com/graph/delta-query-overview)

## <a name="getting-started-based-on-your-cloud-adoption-journey"></a>Komma igång baserat på din molnadoptionsresa

Office 365-grupper innehåller en omfattande uppsättning styrningsfunktioner som din organisation kan behöva. Betrakta följande organisationsprofiler som vägledning för att förstå metodtips, ställa rätt frågor för att fastställa kraven för styrning och hur du uppfyller dem.

**Tänk på följande organisationsprofiler:**
- Small Business
- Medelstora företag
- Reglerat eller Företag

### <a name="small-business"></a>Småföretag
Överväg en organisation som har distribuerat Office 365 med minst Exchange Online- och SharePoint Online-licenser som innehåller Business Essentials- och Business Premium-abonnemangen och Enterprise E1-, E3- och E5-abonnemangen utan Azure Active Director Premium Licensiering.

| Scenen | Beskrivning |
| --------------- | ------------------------------------------------------------ |
| Vägledning |<ul><li>Överväg en självbetjäningsmodell</li><li> Grupper i Outlook & SharePoint-webbplatser är [privata som standard](https://techcommunity.microsoft.com/t5/Office-365-Groups/Groups-in-Outlook-and-Group-connected-team-sites-are-now-private/m-p/186395).</li><li> Grupper kan skapas genom att uppgradera befintliga distributionslistor (DLs) antingen en efter en eller i bulk via PowerShell. Se [Uppgradera distributionslistor till Office 365-grupper](https://support.office.com/article/Upgrade-distribution-lists-to-Office-365-Groups-in-Outlook-787D7A75-E201-46F3-A242-F698162FF09F).</li><li> Aktivera gäståtkomst men styr med hjälp av tillåt/blockera gästdomäner.</li><li> Använd grupprapportering för att få insikter om hur användare använder grupper.</li><li> Överväg att skapa ett organisationsövergripande Microsoft Teams som ett sätt för alla att vara en del av ett enda team för samarbete. </li></ul>|
| Nästa steg      |<ul><li>Överväg att använda [platsdesign och platsskript](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-overview) för att definiera standarddesignen till kontroller med hjälp av de åtgärder som definierats i [JSON-schemareferensen](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema).</li><li>Granska [rapporter om grupper](https://support.office.com/article/Office-365-Reports-in-the-admin-center-Office-365-groups-a27f1a99-3557-4f85-9560-a28e3d822a40)</li><li>Spåra totalt antal grupper och inaktiva/aktiva grupper</li><li>Spåra både Exchange- och SharePoint-lagring som används</li><li>Visa gruppaktivitet över grupppostlådekonversationer, gruppwebbplats/filaktivitet etc.</li></ul> |

### <a name="medium-sized-business"></a>Medelstora företag
Utöver ovanstående rekommendationer bör du tänka på följande för medelstora företag som har distribuerat Office 365 med minst ett Enterprise E3/E5 med Azure Active Directory Premium P1-licenser.

| Scenen | Beskrivning |
| --------------- | ------------------------------------------------------------ |
| Vägledning |<ul><li>Besluta om en öppen eller IT-ledd etableringsmodell.</li><li> Överväg att skapa vissa grupper som är kopplade till [dynamiska medlemskapsregler](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) baserat på Azure AD-attribut som Avdelning</li><li> Definiera klassificeringar inom din organisation t.ex.</li><li>  Definiera principer baserat på klassificering, till exempel kvarhållning och känslighet.</li><li> SharePoint är innehållstjänsten för varje Office 365-grupp. Överväg att utforma och [distribuera SharePoint Online-webbplatser för tre nivåer av skydd](https://docs.microsoft.com/office365/enterprise/deploy-sharepoint-online-sites-for-three-tiers-of-protection) (baslinje, känslig och mycket konfidentiell). Mer information om dessa tre skyddsnivåer finns i [Säkra SharePoint Online-webbplatser och -filer](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files).</li><li> Både offentliga och privata grupper listas som standard i GAL. Bestäm vilka grupper du vill ska visas i GRUPPEN GAL specifikt som skapats utanför Microsoft Teams.  Använd [Cmdlets](https://technet.microsoft.com/library/mt238274(v=exchg.160).aspx) "HiddenFromAddressListsEnabled" eller HidefromExchangeClients för att dölja specifika grupper </li></ul> |
| Nästa steg      |<ul><li>Definiera [användningsriktlinjer](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-groups-settings-cmdlets) för att utbilda användarna om metodtips som hjälper till att hålla deras grupper effektiva och utbilda dem om interna innehållsprinciper. Till exempel förstå klassificeringar, policyer och procedurer. </li><li>Definiera grupplivscykel som grupper måste förnyas eller tas bort - principen för utgående utgång.</li><li>Överväg att skapa följande anpassade jobb för att implementera principer baserat på klassificeringar.</li><li>Ställ in sekretessen på privat.</li><li>Inaktivera externt medlemskap/delning. </li><li>E-postmeddelanden för att meddela gruppmedlemmar för grupper [utan ägare](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</li><li>Genomdriva ägarpolicy (min. 2 ägare).</li><li> Definiera bevarandeprinciper för grupper baserat på klassificering. </li><li>Översikt över bevarandeprinciper.</li><li>Använda Powershell för att identifiera grupper med en klassificering [och Ange ComplianceCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy?view=exchange-ps).</li><li>Överväg att använda platsdesign och platsskript för att definiera kontrollerna med hjälp av de åtgärder som definierats i [JSON-schemareferensen](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-json-schema).</li><li>Överväg att skapa [en enkel platskatalog med hjälp av en webbplatsdesign](https://docs.microsoft.com/sharepoint/dev/declarative-customization/site-design-trigger-flow-tutorial) och Microsoft Flow. När en webbplats skapas med hjälp av den här webbplatsdesignen fångas information om webbplatsen och skrivs till en lista. </li></ul>|

### <a name="regulated-or-enterprise"></a>Reglerat eller Företag
Utöver ovanstående rekommendationer överväga följande för starkt reglerade eller stora företag som statliga, finansiella tjänster eller hälso-och sjukvård som har distribuerat Office 365 med minst ett Enterprise E3/E5 med Azure Active Directory Premium P1/P2 licenser.

| Scenen | Beskrivning |
| --------------- | ------------------------------------------------------------ |
| Vägledning |<ul><li> Definiera principer för datastyrning av SharePoint-webbplatsen som är associerad med gruppen baserat på klassificering.</li><li>[Skydda SharePoint Online-filer med Office 365-etiketter och DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).</li><li>[Skydda SharePoint Online-filer med Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection).</li><li> Gruppwebbplats som etablerats i region som är knuten till användarens plats för önskade data[(multigeo).](https://docs.microsoft.com/office365/enterprise/multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-office-365)</li><li> Medlemsrecensioner för grupper med externa medlemmar ([åtkomstgranskningar](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-access-reviews-overview)).</li><li>Se till att anställda eller gästanvändare ser relevanta ansvarsfriskrivningar för juridiska krav eller efterlevnadskrav innan de får åtkomst. [(användningsvillkor).](https://docs.microsoft.com/azure/active-directory/governance/active-directory-tou)</li><li>Identifiera och rapportera om Office 365-grupper med en viss [klassificering som också har externa användare](https://techcommunity.microsoft.com/t5/Office-365-Groups/Sample-Powershell-to-identify-groups-with-HBI-classification-and/m-p/215561).</li><li>Hemliga grupper där medlemskap behövde döljas måste skapas med cmdleten [New-UnifiedGroup](https://technet.microsoft.com/library/mt219359(v=exchg.160).aspx) (med doldgruppsaktiverad switch) på gruppskapande.</li><li>Definiera [känslighetsetiketterför](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels) organisationen för att [begränsa åtkomsten till innehåll genom att använda kryptering](https://docs.microsoft.com/Office365/SecurityCompliance/encryption-sensitivity-labels) och publicera till specifika Office 365-grupper.</li><li>Förhindra att känsligt innehåll lämnar organisationen på enheter som kör Windows med hjälp av [känslighetsetiketter med Windows Information Protection](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553). |
| Nästa steg      | <ul><li> Använd webbplatsdesign och platsskript för att definiera [standardåtgärder](https://developer.microsoft.com/office/blogs/site-scripts-site-designs-summer-2018-update/) som uppstår när en ny webbplats skapas. Konfigurera till exempel [extern delningsinställning](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-apply-external-sharing-setting) eller [utlösa ett Microsoft Flow för att anropa en Azure-funktion](https://github.com/SharePoint/sp-dev-site-scripts/tree/master/samples/site-azure-function) för att tillämpa konfigurationer som inte stöds internt. </li><li> Dokumentkrav för [att skydda SharePoint Online-filer med Office 365-etiketter och DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) till webbplatser som är associerade med Office 365-grupper.</li><li>Dokumentorganisationskrav till [Säkra SharePoint Online-webbplatser och filer](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files) som är anslutna till Office 365-grupper. </li><li>Dokumentorganisationskrav för att publicera [känslighetsetiketter](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels) för specifika användare eller grupper för att skydda innehåll.</li></ul> |

## <a name="groups-management-capability-planning-checklist"></a>Checklista för kapacitetsplanering för grupper

Ett antal grupprelaterade kontroller kan administreras via Azure Active Directory. Mer information om hur du konfigurerar gruppinställningar finns i [Azure Active Directory-cmdlets för att konfigurera gruppinställningar](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets).

Använd följande tabell för att avgöra vilka funktioner du behöver för att distribuera dina organisationskrav. Det hjälper dig att avgöra vilka licenser du behöver så att du kan planera i förväg.

| **Kapacitet**      | **Information**                                    | **Azure AD Premium-licens krävs** | **Beslut** |
| ------------------- | ---------------------------------------------- | ------------------------------------- | ------------ |
| Princip för gruppnamn | Använd Prefix-Suffix-baserade, anpassade blockerade ord. | P1 (P1)                                    |      Tbd     |
| Gruppklassificering | Tilldela klassificeringar till team. | P1 (P1)                                    |   Tbd        |
| Tillgång till gruppgäst | Tillåt eller förhindra att gäster läggs till i grupper. | Nej                                    |  Tbd        |
| Gruppskapande | Begränsa gruppskapande till administratörer. | Nej                                    |   Tbd        |
| Gruppskapande | Begränsa gruppskapande till medlemmar i säkerhetsgruppen. | P1 (P1)                                    |     Tbd      |
| Riktlinjer för gruppanvändning | Ange en länk för riktlinjerna för gruppanvändning som ska visas på alla slutpunkter för gruppskapande. | P1 (P1)                                    |   Tbd        |
| Dolt medlemskap | Dölja medlemmarna i Office 365-gruppen från användare som inte är medlemmar i gruppen | Nej                                    |   Tbd        |
| Princip för förfallodatum | Hantera livscykeln för Office 365-grupper genom att ange en förfalloprincip. | P1 (P1)                                    |  Tbd        |
| Gruppaktivitetsrapporter | Få insikter om aktiviteten för Office 365-grupper i organisationen och se hur många Office 365-grupper som skapas och används. | Nej                                    |    Tbd       |
| Loggperiodsprincip | Lagra eller ta bort data under en viss tidsperiod genom att ange lagringsprinciper för Office 365-grupper i säkerhets- &-kompatibilitetscenter. **Obs:** Med den här funktionen krävs licensiering av Office 365 Enterprise E3 eller högre. | Nej                                    |    Tbd       |
| Policy för förebyggande av dataförlust | Identifiera känslig information i Office 365-gruppens anslutna webbplatser och förhindra oavsiktlig delning. **Obs:** Med den här funktionen krävs licensiering av Office 365 Enterprise E3 eller högre. | Nej                                    |     Tbd      |
| Arkivera och återställa | Arkivera ett team när det inte längre är aktivt men du vill behålla det runt som referens eller att återaktivera i framtiden. | Nej                                    |   Tbd        |
| Få tillgång till recensioner | Utföra granskningar för att effektivt hantera gruppmedlemskap för både interna användare och gästanvändare | P2 (P2)                                    |   Tbd       |
| Användarvillkor | En enkel metod som organisationer kan använda för att presentera information för slutanvändare. Den här presentationen säkerställer att användarna ser relevanta ansvarsfriskrivningar för juridiska krav eller efterlevnadskrav. | P1 (P1)                                    |         Tbd  |

