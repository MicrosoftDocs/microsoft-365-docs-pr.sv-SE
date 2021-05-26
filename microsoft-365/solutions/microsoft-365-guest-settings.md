---
title: Inställningar för gästdelning i Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
f1.keywords: NOCSH
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
recommendations: false
description: Läs mer om de inställningar för gästdelning som är tillgängliga i Microsoft 365 som kan påverka delning med personer utanför organisationen.
ms.openlocfilehash: b209477e2fa205ebb6b298b7fa9f37c21e2b3d7e
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625436"
---
# <a name="microsoft-365-guest-sharing-settings-reference"></a>Inställningar för gästdelning i Microsoft 365

I den här artikeln beskrivs de olika inställningarna som kan påverka delning med personer utanför organisationen för Microsoft 365-arbetsbelastningar: Teams, Microsoft-grupper, SharePoint och OneDrive. Dessa inställningar finns i administrationscentret för Azure Active Directory, Microsoft 365, Teams och SharePoint.

## <a name="azure-active-directory"></a>Azure Active Directory

**Administratörsroll:** Global administratör

Azure Active Directory är den katalogtjänst som används av Microsoft 365. Inställningarna för organisationsrelationer i Azure Active Directory påverkar direkt delning i Teams, Microsoft 365-grupper, SharePoint och OneDrive.

> [!NOTE]
> De här inställningarna påverkar bara SharePoint när [SharePoint- och OneDrive-integrering med Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview) har konfigurerats. I tabellen nedan förutsätts det att den har konfigurerats.

### <a name="external-collaboration-settings"></a>Inställningar för externt samarbete

**Navigering:** [administrationscentret för Azure Active Directory](https://aad.portal.azure.com) > Azure Active Directory > externa identiteter > Inställningar för externt samarbete

![Skärmbild av sidan med inställningar för organisationsrelationer i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

| Inställning | Standard | Beskrivning |
|:-----|:-----|:-----|
|Gästanvändarbehörighet|Gästanvändare har begränsad åtkomst till egenskaper och medlemskap i katalogobjekt|Avgör vilka [behörigheter som gäster har i Azure Active Directory](/azure/active-directory/fundamentals/users-default-permissions).|
|Inställningar för gästinbjudning|Alla i organisationen kan bjuda in gästanvändare, inklusive gäster och icke-administratörer|Avgör om gäster, medlemmar och administratörer kan bjuda in gäster till organisationen.<br><br> Den här inställningen påverkar Microsoft 365-delningsupplevelser som Team och SharePoint.|
|Aktivera självbetjäning för gäster att registrera via användarflöden|Nej|Fastställer om du kan skapa användarflöden som tillåter att någon registrerar sig för ett program som du har skapat och skapar ett nytt gästkonto.|
|Samarbetsbegränsningar|Tillåt att inbjudningar skickas till alla domäner|Med den här inställningen kan du ange en lista över tillåtna eller blockerade domäner för delning. När tillåtna domäner anges kan delningsinbjudningar bara skickas till dessa domäner. När blockerade domäner anges kan delningsinbjudningar inte skickas till de domänerna.<br><br> Den här inställningen påverkar Microsoft 365-delningsupplevelser som Team och SharePoint. Du kan tillåta eller blockera domäner på en mer detaljerad nivå med hjälp av domänfiltrering i SharePoint eller Teams.|

Dessa inställningar påverkar hur användare bjuds in till katalogen. De påverkar inte delning med gäster som redan finns i katalogen.

## <a name="microsoft-365"></a>Microsoft 365

**Administratörsroll:** Global administratör

Administrationscenter för Microsoft 365 har inställningar på organisationsnivå för delning och för Microsoft 365-grupper.

### <a name="sharing"></a>Delning

**Navigering:** [Administrationscenter för Microsoft 365](https://admin.microsoft.com) > Inställningar > Organisationsinställningar > fliken Säkerhet och sekretess > Delning

![Skärmbild av gästdelningsinställningen för säkerhet och sekretess i Microsoft 365-administrationscentret](../media/sharepoint-security-privacy-sharing-setting.png)

| Inställning | Standard | Beskrivning |
|:-----|:-----|:-----|
|Låt användarna lägga till nya gäster i organisationen|På|När du har angett **Ja** kan Azure AD-medlemmar bjuda in gäster via Azure AD. Om du har angett **Nej** kan de inte göra det. När du har angett **Ja** kan Microsoft 365-gruppmedlemmar bjuda in gäster med ägargodkännande. Om du har angett **Nej** kan Microsoft 365-gruppmedlemmar bjuda in gäster med ägargodkännande, men ägarna måste vara globala administratörer för att kunna godkänna. <br><br>Observera att **Medlemmar kan bjuda in** gäller medlemmar i Azure AD (inte gäster) och inte webbplats- eller gruppmedlemmar i Microsoft 365. <br><br>Den här motsvarar inställningen **Medlemmar kan bjuda in** i Azure Active Directory för relationer i organisationen.|

### <a name="microsoft-365-groups"></a>Microsoft 365-grupper

**Navigering:** [Administrationscenter för Microsoft 365](https://admin.microsoft.com) > Inställningar > Inställningar > Microsoft 365-grupper

![Skärmbild av gästinställningarna för Microsoft 365-grupper i administrationscenter för Microsoft 365](../media/office-365-groups-guest-settings.png)

| Inställning | Standard | Beskrivning |
|:-----|:-----|:-----|
|Låt gruppmedlemmar utanför organisationen få åtkomst till gruppinnehåll|På|När den här inställningen är **På** kan gäster komma åt gruppinnehåll. När den är **Av** kan de inte det. Den här inställningen ska vara **På** i alla situationer där gästanvändare interagerar med Microsoft 365-grupper eller Teams.|
|Låt gruppägare lägga till personer utanför organisationen i grupper|På|När inställningen är **På** kan ägare av Microsoft 365-grupper eller Teams bjuda in nya gäster till gruppen. När den är **Av** kan ägare endast bjuda in gäster som redan finns i katalogen.|

Dessa är inställningar på organisationsnivå. Mer information om hur du ändrar de här inställningarna på gruppnivå genom att använda PowerShell finns under[Skapa inställningar för en viss grupp](/azure/active-directory/users-groups-roles/groups-settings-cmdlets#create-settings-for-a-specific-group).

## <a name="teams"></a>Teams

Huvudinställningen för gäståtkomst i Teams **Tillåt gäståtkomst i Teams** måste vara **På** för att övriga gästinställningar ska vara tillgängliga.

**Administratörsroll:** Teams-tjänstadministratör

### <a name="guest-access"></a>Gäståtkomst

**Navigering:** [Administrationscenter för Teams](https://admin.teams.microsoft.com) > Organisationsomfattande inställningar > Gäståtkomst

![Skärmbild av inställningen för gäståtkomst i Teams](../media/teams-guest-access-toggle.png)

| Inställning | Standard | Beskrivning |
|:-----|:-----|:-----|
|Tillåt gäståtkomst i Teams|Av|Övergripande inställning för att aktivera och inaktivera gäståtkomst i Teams. Det kan ta upp till 24 timmar för den här inställningen att verkställas efter att den har ändrats.|

### <a name="guest-calling"></a>Gästsamtal

**Navigering:** [Administrationscenter för Teams](https://admin.teams.microsoft.com) > Organisationsomfattande inställningar > Gäståtkomst

![Skärmbild av alternativ för gästsamtal i Teams](../media/teams-guest-calling-setting.png)

| Inställning | Standard | Beskrivning |
|:-----|:-----|:-----|
|Ring privata samtal|På|När inställningen är **På** kan gäster ringa peer-to-peer-samtal i Teams. När den är **Av** kan de inte göra det.|

### <a name="guest-meeting"></a>Gästmöten

**Navigering:** [Administrationscenter för Teams](https://admin.teams.microsoft.com) > Organisationsomfattande inställningar > Gäståtkomst

![Skärmbild av inställningar för gästmöten i Teams](../media/teams-guest-meeting-settings.png)

| Inställning | Standard | Beskrivning |
|:-----|:-----|:-----|
|Tillåt IP-video|På|När inställningen är **På** kan gäster använda video i samtal och möten. När den är **Av** kan de inte det.|
|Skärmdelningsläge|Hela skärmen|När inställningen är **Inaktiverad** kan gäster inte dela sina skärmar i Teams. När den är inställd på **Enstaka program** kan gäster bara dela ett program på skärmen. När den är inställd på **Hela skärmen** kan gäster välja att dela ett program eller hela skärmen.|
|Tillåt möte nu|På|När inställningen är **På** kan gäster använda funktionen Möte nu i Teams. När den är **Av** kan de inte det.|

### <a name="guest-messaging"></a>Gästmeddelanden

**Navigering:** [Administrationscenter för Teams](https://admin.teams.microsoft.com) > Organisationsomfattande inställningar > Gäståtkomst

![Skärmbild av inställningar för gästmeddelanden i Teams](../media/teams-guest-messaging-settings.png)

| Inställning | Standard | Beskrivning |
|:-----|:-----|:-----|
|Redigera skickade meddelanden|På|När inställningen är **På** kan gäster redigera meddelanden som de skickat tidigare. När den är **Av** kan de inte göra det.|
|Ta bort skickade meddelanden|På|När inställningen är **På** kan gäster ta bort meddelanden som de skickat tidigare. När den är **Av** kan de inte göra det.|
|Chatt|På|När inställningen är **På** kan gäster använda chatten i Teams. När den är **Av** kan de inte det.|
|Använda Giphys i konversationer|På|När inställningen är **På** kan gäster använda animerade bilder i konversationer. När den är **Av** kan de inte det.|
|Klassificering av Giphy-innehåll|Måttlig|När inställningen har angetts som **Tillåt allt innehåll** kan gäster infoga alla animerade bilder i chattar, oavsett innehållsklassificering. När inställningen har angetts som **Måttlig** kan gäster infoga animerade bilder i chattar, men det finns en måttlig begränsning för innehåll som är olämpligt för barn. När inställningen har angetts som **Strikt** kan gäster infoga animerade bilder i chattar, men de kan inte infoga innehåll som är olämpligt för barn.|
|Använda memes i konversationer|På|När inställningen är **På** kan gäster använda memes i konversationer. När den är **Av** kan de inte det.|
|Använda dekaler i konversationer|På|När inställningen är **På** kan gäster använda dekaler i konversationer. När den är **Av** kan de inte det.|
|Tillåt avancerade läsare för att visa meddelanden|På|När inställningen är **På** kan gäster visa meddelanden i avancerade läsare. När den är **Av** kan de inte det.|

## <a name="sharepoint-and-onedrive-organization-level"></a>SharePoint och OneDrive (organisationsnivå)

**Administratörsroll:** SharePoint-administrator

De här inställningarna påverkar alla webbplatser i organisationen. De påverkar inte Microsoft 365-grupper eller Teams direkt, men vi rekommenderar att du justerar inställningarna i enlighet med inställningarna för Microsoft 365-grupper och Teams för att undvika användningsproblem. (Om gästdelning till exempel är tillåtet i Teams men inte i SharePoint, har gästerna i Teams inte åtkomst till fliken Filer eftersom Teams-filer lagras i SharePoint.)

### <a name="sharepoint-and-onedrive-sharing-settings"></a>Delningsinställningar för SharePoint och OneDrive

Eftersom OneDrive är en webbplatshierarki i SharePoint påverkar delningsinställningarna på organisationsnivå OneDrive direkt, precis som för andra SharePoint-webbplatser.

**Navigering:** Administrationscenter för SharePoint > Delning

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)

| Inställning | Standard | Beskrivning |
|:-----|:-----|:-----|
|SharePoint|Alla|De mest tillåtande delningsbehörigheterna för SharePoint-webbplatser.|
|OneDrive|Alla|De mest tillåtande delningsbehörigheterna för OneDrive-webbplatser. Den här inställningen kan inte vara mer tillåtande än SharePoint-inställningen.|

### <a name="sharepoint-and-onedrive-advanced-sharing-settings"></a>Avancerade delningsinställningar för SharePoint och OneDrive

**Navigering:** Administrationscenter för SharePoint > Delning

![Skärmbild av ytterligare delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-advanced-sharing-settings.png)

| Inställning | Standard | Beskrivning |
|:-----|:-----|:-----|
|Begränsa extern delning per domän|Av|Med den här inställningen kan du ange en lista över tillåtna eller blockerade domäner för delning. När tillåtna domäner anges kan delningsinbjudningar bara skickas till dessa domäner. När blockerade domäner anges kan delningsinbjudningar inte skickas till de domänerna.<br><br> Den här inställningen påverkar alla SharePoint- och OneDrive-webbplatser i organisationen.|
|Gäster måste logga in med det konto som delningsinbjudningar skickas till|Av|Hindrar gäster från att acceptera inbjudningar till webbplatsdelningar med en annan e-postadress än den som inbjudan skickades till.<br><br>[SharePoint- och OneDrive-integrering med Azure AD B2B (förhandsversion)](/sharepoint/sharepoint-azureb2b-integration-preview) använder inte den här inställningen eftersom alla gäster läggs till i katalogen utifrån den e-postadress som inbjudan skickades till. Det går inte att komma åt webbplatsen med alternativa e-postadresser.|
|Tillåt gäster att dela objekt som de inte äger|På|När inställningen är **På** kan gäster dela objekt som de inte äger med andra användare eller gäster. När den är **Av** kan de inte det. Gäster kan alltid dela objekt som de har fullständig kontroll över.|

### <a name="sharepoint-and-onedrive-file-and-folder-link-settings"></a>Inställningar för fil- och mapplänkar för SharePoint och OneDrive

När filer och mappar delas i SharePoint och OneDrive får delningsmottagare en länk med behörighet till filen eller mappen i stället för att få direktåtkomst till filen eller mappen. Det finns flera typer av länkar och du kan välja vilken standardtyp för länkar som ska visas för användare när de delar en fil eller mapp. Du kan också ange behörigheter och förfalloalternativ för *Alla*-länkar.

**Navigering:** Administrationscenter för SharePoint > Delning

![Skärmbild av delningsinställningar för filer och mappar för SharePoint på organisationsnivå](../media/sharepoint-organization-files-folders-sharing-settings.png)

| Inställning | Standard | Beskrivning |
|:-----|:-----|:-----|
|Fil- och mapplänkar|Alla som har länken|Anger vilken delningslänk som visas som standard när en användare delar en fil eller mapp. Användare kan ändra alternativet innan de delar. Om standardinställningen är **Alla som har länken** och *Alla* är delning inte tillåten för en viss webbplats, och **Endast personer i din organisation** visas som standard för den webbplatsen.|
|Länkarna måste upphöra att gälla inom så här många dagar|Av (upphör inte)|*Alla*-länken upphör efter det angivna antalet dagar efter att den har skapats. Länkar som har upphört kan inte förnyas. Skapa en ny länk om du vill fortsätta att dela efter förfallotiden.|
|Filbehörigheter|Visa och redigera|Anger filbehörighetsnivåer som är tillgängliga för användare när de skapar en *Alla*-länk. Om **Visa** har valts kan användare bara skapa *Alla*-fillänkar med visningsbehörigheter. Om **Visa och redigera** har valts kan användare välja mellan behörigheter för att visa och visa och redigera när de skapar länken.|
|Mappbehörigheter|Visa, redigera och ladda upp|Anger mappbehörighetsnivåer som är tillgängliga för användare när de skapar en *Alla*-länk. Om **Visa** har valts kan användare bara skapa *Alla*-mapplänkar med visningsbehörigheter. Om **Visa, redigera och ladda upp** har valts kan användare välja mellan behörigheter för att visa och visa, redigera och ladda upp när de skapar länken.|

### <a name="sharepoint-and-onedrive-security-group-settings"></a>Inställningar för säkerhetsgrupper i SharePoint och OneDrive

Om du vill begränsa vilka som kan dela med gäster i SharePoint och OneDrive begränsar du delning till personer i särskilda säkerhetsgrupper. De här inställningarna påverkar inte delning via Microsoft 365-grupper eller Teams. Gäster som bjuds in via en grupp eller Teams har också åtkomst till den associerade webbplatsen, men dokument- och mappdelning kan endast göras av personer i de angivna säkerhetsgrupperna.

**Navigering:** Administrationscenter för SharePoint > Delning > Begränsa extern delning till specifika säkerhetsgrupper

![Skärmbild av delningsinställningar för säkerhetsgrupper i SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-security-groups.png)

| Inställning | Standard | Beskrivning |
|:-----|:-----|:-----|
|Tillåt endast användare i valda säkerhetsgrupper att dela med autentiserade externa användare|Av|När **På** kan bara personer i de angivna säkerhetsgrupperna dela med personer utanför organisationen. Bara länkar för *Vissa personer* är tillgängliga. Delning med *Alla* inaktiveras, såvida inte **Tillåt endast användare i valda säkerhetsgrupper att dela med autentiserade användare och med hjälp av anonyma länkar** också är **På**|
|Tillåt endast användare i valda säkerhetsgrupper att dela med autentiserade användare och med hjälp av anonyma länkar|Av|När inställningen är **På** kan bara personerna i de angivna säkerhetsgrupperna dela med gäster. Både länkar för *Alla* och *Vissa personer* är tillgängliga.|

Båda inställningarna kan användas samtidigt. Om en användare ingår i säkerhetsgrupper som angetts för båda inställningarna, kommer den högre behörighetsnivån att gälla (*Alla* plus *Vissa användare*). Kapslade säkerhetsgrupper stöds.

## <a name="sharepoint-site-level"></a>SharePoint (webbplatsnivå)

**Administratörsroll:** SharePoint-administrator

Eftersom de här inställningarna åsidosätts av inställningarna för hela organisationen för SharePoint, kan inställningen för webbplatsdelning ändras om någon inställning på organisationsnivå ändras. Om du väljer en inställning här och inställningen på organisationsnivå ställs in senare på ett mer begränsat värde, kommer den här webbplatsen att fungera enligt det mer begränsade värdet. Om du till exempel väljer **Alla** och inställningen på organisationsnivå ställs in senare på **Nya och befintliga gäster** kommer webbplatsen bara att tillåta nya och befintliga gäster. Om inställningen på organisationsnivå ställs in på **Alla** kan webbplatsen återigen tillåta *Alla*-länkar.

### <a name="site-sharing"></a>Webbplatsdelning

Du kan ange behörigheter för gästdelning för varje webbplats i SharePoint. Den här inställningen gäller både webbplatsdelning och delning av filer och mappar. (*Alla*-delning är inte tillgänglig för webbplatsdelning. Om du väljer **Alla** kan användarna dela filer och mappar genom att använda *Alla*-länkar och webbplatsen med nya och befintliga gäster.)

Om webbplatsen har en känslighetsetikett kan den etiketten styra de externa delningsinställningarna. Mer information finns i [Använd känslighetsetiketter för att skydda innehåll i Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser](../compliance/sensitivity-labels-teams-groups-sites.md).

**Navigering:** Administrationscenter för SharePoint > Aktiva webbplatser > välj webbplats > fliken Principer > Redigera extern delning

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

| Inställning | Standard | Beskrivning |
|:-----|:-----|:-----|
|Webbplatsinnehåll kan delas med|Varierar efter webbplatstyp (se tabellen nedan)|Anger vilken typ av extern delning som tillåts för webbplatsen. Alternativ som är tillgängliga här åsidosätts av delningsinställningarna på organisationsnivå för SharePoint.|

### <a name="site-file-and-folder-link-settings"></a>Webbplatsinställningar för fil- och mapplänk

Du kan ange standardinställningar för länktyp och behörigheter samt förfalloinställningar för *Alla*-länkar för varje webbplats. När inställningarna anges på webbplatsnivå kan de åsidosättas av inställningarna på organisationsnivå. Tänk på att om *Alla*-länkar inaktiveras på organisationsnivå blir inte *Alla* en tillgänglig länktyp på webbplatsnivå.

**Navigering:** Administrationscenter för SharePoint > Aktiva webbplatser > välj webbplats > fliken Principer > Redigera extern delning

![Skärmbild av inställningar för länkdelning för SharePoint på webbplatsnivå](../media/sharepoint-site-link-sharing-settings.png)

| Inställning | Standard | Beskrivning |
|:-----|:-----|:-----|
|Begränsa delning per domän|Av|Med den här inställningen kan du ange en lista över tillåtna eller blockerade domäner för delning. När tillåtna domäner anges kan delningsinbjudningar bara skickas till dessa domäner. När blockerade domäner anges kan delningsinbjudningar inte skickas till de domänerna.<br><br> Den här inställningen kan inte åsidosätta domänbegränsningar som anges på organisations- eller Azure AD-nivå.|
|Standardtyp för delningslänk|Samma som inställningarna på organisationsnivå|Med den här inställningen kan du ange standarddelningslänken som visas för användarna på webbplatsen. Alternativet *Samma som inställningarna på organisationsnivå* definieras av en kombination av inställningar för delning på organisations- och webbplatsnivå.|
|Avancerade inställningar för Alla-länkar|Samma som inställningarna på organisationsnivå|*Alla*-länken upphör efter det angivna antalet dagar efter att den har skapats för en fil på den här webbplatsen. Länkar som har upphört kan inte förnyas. Skapa en ny länk om du vill fortsätta att dela efter förfallotiden.|
|Standardbehörighet för länk|Samma som inställningarna på organisationsnivå|Med den här inställningen kan du ange standardbehörighet (Visa eller Redigera) för delning av länkar som skapas för filer på webbplatsen.|

### <a name="default-site-sharing-settings"></a>Standardinställningar för webbplatsdelning

I tabellen nedan visas standardinställningen för delning för varje webbplatstyp.

| Webbplatstyp | Standardinställning för delning |
|:-----|:-----|
|Klassisk|**Endast personer i organisationen**|
|OneDrive|**Alla**|
|Gruppanslutna webbplatser (inklusive Teams)|**Nya och befintliga gäster** om inställningen för Microsoft 365-grupper **Låt gruppägare lägga till personer utanför organisationen i grupper** är **På** – annars **Endast befintliga gäster**.|
|Kommunikation|**Endast personer i organisationen**|
|Moderna webbplatser utan grupp (#STS3-gruppwebbplats)|**Endast personer i organisationen**|

> [!NOTE]
> Rotwebbplatsen för kommunikation (tenant-name.sharepoint.com) har standardinställningen **Alla** för delning.

## <a name="see-also"></a>Se även

[Översikt över extern SharePoint- och OneDrive-delning](/sharepoint/external-sharing-overview)

[Gäståtkomst i Microsoft Teams](/MicrosoftTeams/guest-access)

[Lägga till gäster i Microsoft 365-grupper](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)
