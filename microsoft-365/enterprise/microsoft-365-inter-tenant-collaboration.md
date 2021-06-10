---
title: Microsoft 365 samarbete mellan klientorganisationen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Lär dig Microsoft 365 samarbete fungerar mellan olika klientorganisationer och organisationer, så att olika organisationer kan samarbeta säkert.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b4ff55d9bc355a03e7f7336bd01d3c19a60d2d31
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923284"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Microsoft 365 samarbete mellan klientorganisationen

Anta att två organisationer, Fabrikam och Contoso, har var och en en Microsoft 365 för företag-klientorganisation och att de vill samarbeta på flera olika projekt. Vissa körs under en begränsad tid och en del pågår. Hur kan Fabrikam och Contoso göra det möjligt för deras personer och team att samarbeta mer effektivt i deras Microsoft 365-klientorganisation på ett säkert sätt? Microsoft 365, i kombination med Azure Active Directory B2B-samarbete (Azure AD) ger flera alternativ. I den här artikeln beskrivs flera viktiga scenarier som Fabrikam och Contoso kan överväga.
  
Microsoft 365 alternativ för samarbete mellan olika klientorganisationen omfattar att använda en central plats för filer och konversationer, dela kalendrar, använda snabbmeddelanden, ljud-/videosamtal för kommunikation och att säkerställa åtkomst till resurser och program. Välj lösningar och läs mer i följande tabeller.
  
## <a name="exchange-online-collaboration-options"></a>Exchange Online för samarbete

| Delningsmål | Administrativ åtgärd | Information |
|:-----|:-----|:-----|
|Dela kalendrar med en annan Microsoft 365 organisation |Administratörer kan konfigurera olika nivåer av kalenderåtkomst i Exchange Online så att företag kan samarbeta med andra företag och låta användare dela scheman (ledig/upptagen-information) med andra. | <ul><li>[Delning](/exchange/sharing/sharing) </li><li> [Organisationsrelationer](/exchange/sharing/organization-relationships/organization-relationships) </li><li> [Skapa en organisationsrelation](/exchange/sharing/organization-relationships/create-an-organization-relationship) </li><li> [Ändra en organisationsrelation ](/exchange/sharing/organization-relationships/modify-an-organization-relationship) </li><li> [Ta bort en organisationsrelation](/exchange/sharing/organization-relationships/remove-an-organization-relationship) </li><li> [Dela kalendrar med externa användare](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) </li></ul> |
|Styra hur användare delar sina kalendrar med personer utanför organisationen | Administratörer tillämpar delningsprinciper på användarnas postlådor för att styra vem den kan delas med och vilken åtkomstnivå som beviljas |  <ul><li> [Delningsprinciper](/exchange/sharing/sharing-policies/sharing-policies) </li><li> [Skapa en delningsprincip](/exchange/sharing/sharing-policies/create-a-sharing-policy) </li><li> [Tillämpa en delningsprincip på postlådor](/exchange/sharing/sharing-policies/apply-a-sharing-policy) </li><li> [Ändra, inaktivera eller ta bort en delningsprincip](/exchange/sharing/sharing-policies/modify-a-sharing-policy) </li></ul> |
|Konfigurera säkra e-postkanaler och kontrollera e-postflödet med partnerorganisationer | Administratörer skapar kopplingar för att göra e-postutbytet bättre med en partnerorganisation eller tjänstleverantör. Kopplingarna tillämpar kryptering via TLS (Transport Layer Security) samt tillåter begränsningar för domännamn eller IP-adressintervall som dina partners skickar e-post från. |  <ul><li> [Hur Exchange Online TLS för att skydda e-postanslutningar](../compliance/exchange-online-uses-tls-to-secure-email-connections.md) </li><li> [Konfigurera e-postflöde med kopplingar](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) </li><li> [Fjärrdomäner](/exchange/mail-flow-best-practices/remote-domains/remote-domains) </li><li> [Konfigurera en anslutare för ett säkert e-postflöde med en partnerorganisation](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner) </li><li> [Metodtips för e-postflöde (översikt)](/exchange/mail-flow-best-practices/mail-flow-best-practices) </li></ul> |
   
## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>SharePoint Alternativ för OneDrive för företag online och i samarbete

| Delningsmål | Administrativ åtgärd | Information |
|:-----|:-----|:-----|
|Dela webbplatser och dokument med externa användare | Administratörer konfigurerar delning på klientorganisations- eller webbplatssamlingsnivå för autentiserade Microsoft-konton, autentiserade arbets- eller skolkonton eller gästkonton |  <ul><li> [Hantera extern delning i SharePoint Online-miljön](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) </li><li> [Begränsa delning av SharePoint och OneDrive innehåll per domän](/sharepoint/restricted-domains-sharing) </li><li> [Använda SharePoint Online som en B2B-extranätlösning (företag till företag)](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) </li></ul> |
|Spåra och kontrollera extern delning för slutanvändare | OneDrive för företag filägare och e SharePoint online-slutanvändare konfigurerar webbplats- och dokumentdelning och skapar meddelanden för att spåra delning |  <ul><li> [Konfigurera meddelanden om extern delning för OneDrive för företag](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) </li><li> [Dela SharePoint filer eller mappar](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) </li></ul> |
   
## <a name="skype-for-business-collaboration-options"></a>Skype för företag för samarbete

| Delningsmål | Administrativ åtgärd | Information |
|:-----|:-----|:-----|
|Skype för företag Online – snabbmeddelanden, samtal och närvaro med andra Skype för företag användare | Administratörer kan göra det möjligt för Skype för företag-användare online att använda snabbmeddelanden, ringa ljud-/videosamtal och se närvaro för användare i en Microsoft 365 klientorganisation. | [Låt användare kontakta externa Skype för företag-användare](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94)| 
|Skype för företag Online – snabbmeddelanden, samtal och närvaro med Skype (konsument) användare | Administratörer kan göra det möjligt Skype för företag-användare i Online att använda snabbmeddelanden, ringa samtal och se Skype (konsument) användare. | [Låt Skype för företag lägga till Skype kontakter](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460)| 
   
## <a name="azure-ad-b2b-collaboration-options"></a>Samarbetsalternativ för Azure AD B2B

| Delningsmål | Administrativ åtgärd | Information |
|:-----|:-----|:-----|
|Azure AD B2B-samarbete – innehållsdelning genom att lägga till externa användare i en grupp i organisationens katalog | En global administratör för en Microsoft 365-klientorganisation kan bjuda in personer i en annan Microsoft 365-klientorganisation att ansluta till katalogen, lägga till de externa användarna i en grupp och bevilja åtkomst till innehåll, till exempel SharePoint-webbplatser och bibliotek för gruppen. |  <ul><li> [Vad är förhandsversion av Azure AD B2B-samarbete?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) </li><li> [Azure AD B2B: Nya uppdateringar gör det enkelt att sortera mellan företag](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) </li><li> [Extern delning och Azure Active Directory B2B-samarbete](/azure/active-directory/active-directory-b2b-o365-external-user) </li><li> [Azure Active Directory API och anpassning av B2B-samarbete](/azure/active-directory/active-directory-b2b-api) </li><li> [Azure AD och identitetsvisning: Azure AD B2B-samarbete (företag till företag)](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) </li></ul> |
   
## <a name="microsoft-365-collaboration-options"></a>Microsoft 365 för samarbete

| Delningsmål | Administrativ åtgärd | Information |
|:-----|:-----|:-----|
|Microsoft 365 Grupper – E-post, kalender OneNote och delade filer på en central plats | Grupper stöds i abonnemangen Business Essentials, Business Premium, Education och Enterprise E1, E3 och E5. Personer i en Microsoft 365 klientorganisation kan skapa en grupp och bjuda in personer i en Microsoft 365 klientorganisation som gästanvändare. Gäller även för Dynamics CRM. |  <ul><li> [Läs mer om Microsoft 365-grupper](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) </li><li> [Gäståtkomst i Microsoft 365 grupper](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) </li><li> [Distribuera Microsoft 365 grupper](/previous-versions/dynamicscrm-2016/administering-dynamics-365/dn896591(v=crm.8)) </li></ul> |
   
## <a name="yammer-collaboration-options"></a>Yammer för samarbete

| Delningsmål | Administrativ åtgärd | Information |
|:-----|:-----|:-----|
|Yammer – samarbete via ett socialt medium för företag | Om inte möjligheten att skapa externa grupper inaktiveras av en Yammer-administratör kan användare skapa externa grupper för att samarbeta i Yammer genom konversationer, möjligheten att gilla och följa inlägg, dela filer och chatta online. | [Skapa och hantera externa grupper i Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a)| 
   
## <a name="teams-collaboration-options"></a>Teams för samarbete

|Delningsmål|Administrativ åtgärd|Information|
|:-----|:-----|:-----|
|Samarbeta i Teams med användare utanför organisationen | En global administratör för den Microsoft 365-klientorganisationen måste aktivera externt samarbete i Teams. Globala administratörer och teamägare kan nu bjuda in alla med en e-postadress att samarbeta i Teams.  <br/> Administratörer kan också hantera och redigera gäster som redan finns i deras klientorganisation. |  <ul><li> [Auktorisera gäståtkomst](/microsoftteams/teams-dependencies) </li><li> [Aktivera eller inaktivera gäståtkomst i Teams](/microsoftteams/set-up-guests) </li><li> [Använda PowerShell för att styra gäståtkomst](/microsoftteams/guest-access-powershell) </li><li> [Checklista för gäståtkomst](/microsoftteams/guest-access-checklist) </li><li> [Visa gästanvändare](/microsoftteams/view-guests) </li><li> [Redigera information om gästanvändare](/microsoftteams/edit-guests-information) </li></ul> |
|Teamägare kan bjuda in och hantera hur gäster samarbetar i sina team.  |Teamägare har ytterligare kontroller på vad gästerna kan göra i sina team. |  <ul><li> [Lägga till gäster](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) </li><li> [Lägga till en gäst i ett team](/microsoftteams/add-guests) </li><li> [Hantera gäståtkomst i Teams](/microsoftteams/manage-guests) </li><li> [Se vem som är med i ett team eller i en kanal](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) </li></ul> |
|Gäster från andra klientorganisationar kan visa innehåll i Teams och samarbeta med andra medlemmar | Ingen. | [Gäståtkomst](/microsoftteams/guest-experience)| 

## <a name="power-bi-collaboration-options"></a>Power BI för samarbete

| Delningsmål | Administrativ åtgärd | Information |
|:-----|:-----|:-----|
|Power BI externa gästanvändare använder innehåll som delas till dem via länkar. Det gör att användare i organisationen kan distribuera innehåll på ett säkert sätt i organisationer.<br/> | Administratören Power BI styra om användarna kan bjuda in externa användare att visa innehåll inom organisationen.| [Distribuera Power BI innehåll till externa gästanvändare med Azure AD B2B](/power-bi/service-admin-azure-ad-b2b) | 
 
## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>Vad du bör tänka på Microsoft 365 samarbete mellan klientorganisationen

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>Delning av användarkonton, licenser, prenumerationer och lagring

Varje organisation har sina egna användarkonton, identiteter, säkerhetsgrupper, prenumerationer, licenser och lagring. Personer använder samarbetsfunktionerna i Microsoft 365 tillsammans med delningsprinciper och säkerhetsinställningar för att ge tillgång till den information som behövs och samtidigt behålla kontrollen över företagets tillgångar.
  
- **Användarkonton:** Konton kan inte delas eller dupliceras mellan klientorganisationen eller partitioner i de lokala Active Directory Domain Services. 
    
- **&amp; Licensprenumerationer:** I Microsoft 365 ger licenser från licensabonnemang (kallas även för SKU:er eller Microsoft 365-abonnemang) användarna åtkomst till de Microsoft 365-tjänster som är definierade för dessa abonnemang. 
    
- **Storage:** I Microsoft 365 licensplaner hanteras programvarubegränsningar för SharePoint Online separat från lagringsbegränsningar för postlådor. Lagringsbegränsningar för postlådor konfigureras och hanteras med hjälp av Exchange Online. I båda scenarierna kan lagring inte delas mellan klientorganisationen. 
    
### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>Kan vi dela domännamnområden mellan Microsoft 365 klientorganisation?

Nej. Organisationsdomännamn, till exempel fabrikam.com eller tailspintoys.com, kan bara associeras och användas med en enda Microsoft 365 klientorganisation. Varje klientorganisation måste ha ett eget namnområde. UPN-, SMTP- och SIP-namnområden kan inte delas mellan klientorganisationen.
  
### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>Vad gäller för hybridkomponenter Microsoft 365 samarbete mellan klientorganisationen?

Lokala hybridkomponenter, till exempel en Exchange organisation och Azure AD Anslut, kan inte delas upp mellan flera klientorganisationar.
