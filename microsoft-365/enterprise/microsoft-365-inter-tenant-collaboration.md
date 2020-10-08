---
title: Samarbete mellan klient organisationer i Microsoft 365
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
description: Lär dig hur Microsoft 365 samarbetar mellan klienter och organisationer och gör att olika organisationer kan samar beta på ett säkert sätt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 00eacfc21d3223b5b9a1ad420cd5d1d85bf4ea8e
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384834"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Samarbete mellan klient organisationer i Microsoft 365

Anta att två organisationer, Fabrikam och contoso, har en Microsoft 365 för företag-klient organisation och att de vill arbeta tillsammans med flera olika projekt; vissa som körs under en begränsad tid och vissa som är pågående. Hur kan Fabrikam och contoso ge sina kontakter och grupper möjlighet att samar beta effektivt över sina olika Microsoft 365-klient organisationer på ett säkert sätt? Microsoft 365, tillsammans med Azure Active Directory (Azure AD) B2B-samarbete, ger flera alternativ. I den här artikeln beskrivs flera viktiga scenarier som kan övervägas med Fabrikam och contoso.
  
Alternativen för samarbete mellan olika innehavare för Microsoft 365 inkluderar användning av en central plats för filer och konversationer, dela kalendrar, använda snabb meddelanden, ljud/video samtal och att skydda åtkomsten till resurser och program. Använd följande tabeller för att välja lösningar och mer information.
  
## <a name="exchange-online-collaboration-options"></a>Samarbets alternativ för Exchange Online

| Dela mål | Administrativ åtgärd | Instruktions information |
|:-----|:-----|:-----|
|Dela kalendrar med en annan Microsoft 365-organisation |Administratörer kan konfigurera olika nivåer av kalender åtkomst i Exchange Online så att företag kan samar beta med andra företag och låta användare dela schemaläggning (ledig/upptagen) med andra. | <ul><li>[Delning](https://technet.microsoft.com/library/jj916670%28v=exchg.150%29.aspx) </li><li> [Organisations relationer](https://technet.microsoft.com/library/jj916658%28v=exchg.150%29.aspx) </li><li> [Skapa en organisations relation](https://technet.microsoft.com/library/jj916671%28v=exchg.150%29.aspx) </li><li> [Ändra en organisations relation ](https://technet.microsoft.com/library/jj916659%28v=exchg.150%29.aspx) </li><li> [Ta bort en organisations relation](https://technet.microsoft.com/library/jj916657%28v=exchg.150%29.aspx) </li><li> [Dela kalendrar med externa användare](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) </li></ul> |
|Kontrol lera hur användarna delar sina kalendrar med personer utanför organisationen | Administratörer tillämpar delnings principer för användarnas post lådor för att kontrol lera vem den kan delas med och vilken behörighets nivå som beviljats |  <ul><li> [Delnings principer](https://technet.microsoft.com/library/jj916673%28v=exchg.150%29.aspx) </li><li> [Skapa en delnings princip](https://technet.microsoft.com/library/jj916676%28v=exchg.150%29.aspx) </li><li> [Tillämpa en delnings princip på post lådor](https://technet.microsoft.com/library/jj916672%28v=exchg.150%29.aspx) </li><li> [Ändra, inaktivera eller ta bort en delnings princip](https://technet.microsoft.com/library/jj916674%28v=exchg.150%29.aspx) </li></ul> |
|Konfigurera säkra e-postkanaler och styra e-postflödet med partner organisationer | Administratörer skapar anslutningar för att skydda e-postutbyten med en partner organisation eller tjänste leverantör. Kopplingarna upprätthåller kryptering via Transport Layer Security (TLS) samt tillåta begränsningar för domän namn eller IP-adressintervall som dina partners skickar e-post från. |  <ul><li> [Så här använder Exchange Online TLS för att skydda e-postanslutningar](https://technet.microsoft.com/library/mt163898.aspx) </li><li> [Konfigurera e-postflöde med kopplingar](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx) </li><li> [Fjärrdomäner](https://technet.microsoft.com/library/jj966211%28v=exchg.150%29.aspx) </li><li> [Konfigurera Connector för säkert e-postflöde med en partner organisation](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx) </li><li> [Metod tips för e-postflöde (översikt)](https://technet.microsoft.com/library/0e6cd9d5-ad3e-418a-8ea9-3bf33332c491%28v=exchg.150%29) </li></ul> |
   
## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>Samarbets alternativ för SharePoint Online och OneDrive för företag

| Dela mål | Administrativ åtgärd | Instruktions information |
|:-----|:-----|:-----|
|Dela webbplatser och dokument med externa användare | Administratörer konfigurerar delning på klient organisations-eller webbplats samlings nivå för autentiserat, arbets-eller skol konto eller gäst konton |  <ul><li> [Hantera extern delning för SharePoint Online-miljön](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) </li><li> [Begränsa delning av SharePoint-och OneDrive-innehåll efter domän](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) </li><li> [Använda SharePoint Online som en extra nät lösning för företag – företag (B2B)](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) </li></ul> |
|Spåra och kontrol lera extern delning för slutanvändare | OneDrive för företag-filägare och SharePoint Online-slutanvändare konfigurerar webbplats-och dokument delning och etablerar aviseringar för att spåra delning |  <ul><li> [Konfigurera aviseringar för extern delning för OneDrive för företag](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) </li><li> [Dela SharePoint-filer eller-mappar](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) </li></ul> |
   
## <a name="skype-for-business-collaboration-options"></a>Samarbets alternativ för Skype för företag

| Dela mål | Administrativ åtgärd | Instruktions information |
|:-----|:-----|:-----|
|Skype för företag – online-snabb meddelanden, samtal och närvaro med andra Skype för företag-användare | Administratörer kan aktivera Skype för företag – Online-användare för snabb meddelanden, ringa röst-och video samtal och se närvaro med användare i en annan Microsoft 365-klient organisation. | [Låt användare kontakta externa Skype för företag-användare](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94)| 
|Skype för företag – online-snabb meddelanden, samtal och närvaro med Skype-användare | Administratörer kan aktivera Skype för företag – Online-användare för att chatta, ringa och se närvaron hos Skype-användare. | [Låt Skype för företag-användare lägga till Skype-kontakter](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460)| 
   
## <a name="azure-ad-b2b-collaboration-options"></a>Samarbets alternativ för Azure AD B2B

| Dela mål | Administrativ åtgärd | Instruktions information |
|:-----|:-----|:-----|
|Azure AD B2B-samarbete – innehålls delning genom att lägga till externa användare i en grupp i en organisations katalog | En global administratör för en Microsoft 365-klient organisation kan bjuda in personer i en annan Microsoft 365-klient organisation att gå med i sin katalog, lägga till externa användare i en grupp och ge åtkomst till innehåll, till exempel SharePoint-webbplatser och bibliotek för gruppen. |  <ul><li> [Vad är Azure AD B2B-samarbets för hands version?](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) </li><li> [Azure AD B2B: nya uppdateringar gör samarbets enkelt](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) </li><li> [Extern delning och Azure Active Directory B2B-samarbete](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-o365-external-user) </li><li> [Azure Active Directory B2B-samarbets-API och anpassning](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-api) </li><li> [Azure AD och Identity show: Azure AD B2B-samarbete (företag till företag)](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) </li></ul> |
   
## <a name="microsoft-365-collaboration-options"></a>Microsoft 365 samarbets alternativ

| Dela mål | Administrativ åtgärd | Instruktions information |
|:-----|:-----|:-----|
|Microsoft 365-grupper – e-post, kalender, OneNote och delade filer på en central plats | Grupper stöds i Business Essentials, Business Premium, Education och Enterprise, E1-, E3-och E5-abonnemangen. Personer i en Microsoft 365-innehavare kan skapa en grupp och bjuda in personer i en annan Microsoft 365-klient organisation som gäst användare. Gäller även för Dynamics CRM. |  <ul><li> [Läs mer om Microsoft 365-grupper](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) </li><li> [Gäst åtkomst i Microsoft 365-grupper](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) </li><li> [Distribuera Microsoft 365-grupper](https://technet.microsoft.com/library/dn896591.aspx) </li></ul> |
   
## <a name="yammer-collaboration-options"></a>Samarbets alternativ för Yammer

| Dela mål | Administrativ åtgärd | Instruktions information |
|:-----|:-----|:-----|
|Yammer – samarbete genom ett socialt nätverk för företag | Såvida inte möjligheten att skapa externa grupper är inaktiverat av en Yammer-administratör kan användare skapa externa grupper för att samar beta i Yammer via konversationer, till exempel och följa inlägg, dela filer och chatta online. | [Skapa och hantera externa grupper i Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a)| 
   
## <a name="teams-collaboration-options"></a>Samarbets alternativ för Teams

|Dela mål|Administrativ åtgärd|Instruktions information|
|:-----|:-----|:-----|
|Samar beta i Teams med användare utanför organisationen | En global administratör för att bjuda in Microsoft 365-klient organisationen måste aktivera externt samarbete i Teams. Globala administratörer och team ägare kommer nu att kunna bjuda in alla som har en e-postadress att samar beta i Teams.  <br/> Administratörer kan även hantera och redigera gäster som redan finns i innehavaren. |  <ul><li> [Auktorisera gäst åtkomst](https://docs.microsoft.com/microsoftteams/teams-dependencies) </li><li> [Aktivera och inaktivera gäst åtkomst i Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) </li><li> [Använda PowerShell för att styra gäst åtkomst](https://docs.microsoft.com/microsoftteams/guest-access-powershell) </li><li> [Check lista för gäst åtkomst](https://docs.microsoft.com/microsoftteams/guest-access-checklist) </li><li> [Visa gäst användare](https://docs.microsoft.com/microsoftteams/view-guests) </li><li> [Redigera gäst användar information](https://docs.microsoft.com/microsoftteams/edit-guests-information) </li></ul> |
|Team ägare kan bjuda in och hantera hur gäster samarbetar i sina team.  |Team ägare har ytterligare kontroller för vad gästerna kan göra inom sina team. |  <ul><li> [Lägg till gäster](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) </li><li> [Lägga till en gäst i ett team](https://docs.microsoft.com/microsoftteams/add-guests) </li><li> [Hantera gäst åtkomst i Teams](https://docs.microsoft.com/microsoftteams/manage-guests) </li><li> [Se vem som är med i ett team eller i en kanal](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) </li></ul> |
|Gäster från andra klient organisationer kan visa innehåll i Teams och samar beta med andra medlemmar | Ingen. | [Åtkomst upplevelsen](https://docs.microsoft.com/microsoftteams/guest-experience)| 

## <a name="power-bi-collaboration-options"></a>Samarbets alternativ för Power BI

| Dela mål | Administrativ åtgärd | Instruktions information |
|:-----|:-----|:-----|
|Power BI gör att externa gäst användare kan använda innehåll som delas av dem via länkar. Detta gör att användare i organisationen kan distribuera innehåll på ett säkert sätt i hela organisationen.<br/> | Power BI-administratören kan kontrol lera om användare kan bjuda in externa användare att visa innehåll i organisationen.| [Distribuera Power BI-innehåll till externa gäst användare med Azure AD B2B](https://docs.microsoft.com/power-bi/service-admin-azure-ad-b2b) | 
 
## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>Poäng för att vara medveten om Microsoft 365 samarbete mellan innehavare

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>Delning av användar konton, licenser, prenumerationer och lagring

Varje organisation har sina egna användar konton, identiteter, säkerhets grupper, prenumerationer, licenser och lagring. Personer använder samarbets funktionerna i Microsoft 365 tillsammans med delnings principer och säkerhets inställningar för att ge till gång till nödvändig information när du behåller kontroll över företagets till gångar.
  
- **Användar konton:** Konton kan inte delas eller dubbleras mellan klient organisationer eller partitioner i den lokala Active Directory Domain Services. 
    
- **Licenser &amp; prenumerationer 365:** licenser från licens planer (kallas även SKU: er eller Microsoft 365-abonnemang) ger användarna åtkomst till de Microsoft 365-tjänster som är definierade för dessa abonnemang. 
    
- **Lagring:** I Microsoft 365-licensavtalet hanteras program varu begränsningar och begränsningar för SharePoint Online separat från gränserna för lagrings utrymme. Lagrings gränser för post lådor konfigureras och hanteras med Exchange Online. I båda fallen kan lagring inte delas mellan innehavare. 
    
### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>Kan vi dela domän namn områden över Microsoft 365-klient organisationer?

Nej. Organisationens domän namn, till exempel fabrikam.com eller tailspintoys.com, kan bara associeras och användas med en enda Microsoft 365-klient. Varje klient organisation måste ha ett eget namn område. UPN-, SMTP-och SIP-namnområden kan inte delas mellan innehavare.
  
### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>Vad händer med hybrid komponenter och Microsoft 365 samarbete mellan innehavare?

Lokala hybrid komponenter, till exempel en Exchange-organisation och Azure AD Connect, kan inte delas upp på flera klient organisationer.
 

