---
title: Styrande åtkomst i Microsoft 365-grupper,-team och SharePoint
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Lär dig mer om hur du styr åtkomst i Microsoft 365-grupper,-team och SharePoint.
ms.openlocfilehash: 8b58016ffa421328e3c1442d4ed2364f2eedc37b
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662867"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Styrande åtkomst i Microsoft 365-grupper,-team och SharePoint

Det finns många kontroller som gör att du kan styra hur andra får åtkomst till resurser i grupper, team och SharePoint. Granska de här alternativen och fundera på hur de kan mappa till dina företags behov, känsligheten hos dina data och omfattningen på de personer som användarna måste samar beta med.

Följande tabell innehåller en snabb referens för de tillgängliga åtkomst kontrollerna i Microsoft 365. Mer information finns i följande avsnitt.

|Kategori|Beskrivning|Entitetsreferens|
|:-------|:----------|:--------|
|Ingå|||
||Identifiering av privata team|[Hantera identifiering av privata team i Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||Dynamiskt grupp medlemskap baserat på regler|[Skapa eller uppdatera en dynamisk grupp i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||Kontrol lera vem som kan dela filer, mappar och webbplatser.|[Konfigurera och hantera åtkomstförfrågningar](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|Villkorlig åtkomst|||
||Multifaktorautentisering|[Azure Multi-Factor-verifikation](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||Styra enhets åtkomst baserat på grupp-, grupp-eller plats känslighet.|[Använd känslighets etiketter för att skydda innehåll i Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Begränsa webbplats åtkomst för ohanterade enheter.|[Kontrol lera SharePoint Access från ohanterade enheter](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||Kontrol lera webbplats åtkomst baserat på plats|[Styra åtkomst till SharePoint-och OneDrive-data baserat på nätverks plats](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|Gäståtkomst|||
||Tillåta eller blockera SharePoint-delning från angivna domäner.|[Begränsa delning av SharePoint-och OneDrive-innehåll efter domän](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||Tillåta eller blockera grupp-eller grupp medlemskap från angivna domäner.|[Tillåta eller blockera inbjudningar för B2B-användare från specifika organisationer](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||Förhindra anonym delning.|[Inaktivera Alla-länkar](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)|
||Kontrol lera behörigheter för länkar för anonym åtkomst.|[Ange länk behörigheter för alla länkar](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||Kontrol lera förfallo tiden för länkar för anonym delning.|[Ange ett utgångsdatum för Alla-länkar](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||Kontrol lera vilken typ av delnings länk som visas för användarna som standard.|[Ändra standardlänktyp för en webbplats](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||Begränsa extern delning till vissa personer.|[Begränsa extern delning till angivna säkerhets grupper](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Kontrol lera gäst åtkomst till en grupp, grupp eller webbplats baserat på känslig information.|[Använd känslighets etiketter för att skydda innehåll i Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Inaktivera delnings alternativ.|[Begränsa delning i Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|Användar hantering|||
||Granska grupp-och grupp medlemskap regelbundet.|[Vad är en granskning av Azure AD Access?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||Automatisera åtkomst hantering till grupper och team.|[Vad är hantering av Azure AD Management?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||Tillåt eller förhindra att personer skapar privata kanaler i Teams.|[Hantera livs cykeln för privata kanaler i Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>Ingå

Medlemskap i team och grupper styrs av ägare. Medlemmar kan bjuda in andra, men Inbjudningarna skickas till ägarna för godkännande. Även om offentliga team och grupper kan upptäckas av alla i organisationen är det möjligt att kontrol lera om privata team och grupper är upptäckta:

- [Hantera identifiering av privata team i Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

Du kan hantera medlemskap i en grupp eller ett team dynamiskt baserat på vissa villkor, till exempel avdelning. I det här fallet kan medlemmar och ägare inte bjuda in personer till gruppen.

- [Skapa eller uppdatera en dynamisk grupp i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

Med SharePoint-webbplatser kan du lägga till ägare, medlemmar och besökare från grupp-eller grupp medlemskap. Beroende på dina behov kan du begränsa vem som kan bjuda in personer till webbplatsen. Beroende på känsligheten hos informationen på en viss webbplats kanske du vill begränsa vem som kan dela filer och mappar. Dessa restriktioner konfigureras av team-, grupp-eller webbplats ägaren:

- [Konfigurera och hantera åtkomstförfrågningar](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>Villkorlig åtkomst

Med Microsoft 365 kan du kräva multifaktorautentisering för både personer inom och utanför organisationen. Det finns många alternativ för omständigheterna när andra uppmanas att ange en andra faktor. Vi rekommenderar starkt att du distribuerar multifaktorautentisering för din organisation:

- [Azure Multi-Factor-verifikation](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

Om du har känslig information i vissa grupper och team kan du använda hanterings principer för enheter baserat på en grupp eller ett grupps känslighets etikett. Du kan blockera åtkomst helt och hållet från ohanterade enheter eller tillåta begränsad åtkomst via webben:

- [Använd känslighets etiketter för att skydda innehåll i Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

I SharePoint kan du begränsa åtkomsten till webbplatser från angivna nätverks platser.

- [Styra åtkomst till SharePoint-och OneDrive-data baserat på nätverks plats](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


Fler resurser:

- [Planera användning av villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [Översikt över Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [Kontrol lera SharePoint Access från ohanterade enheter](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Gäståtkomst

Du kan begränsa gäster baserat på domänen för e-postadressen. SharePoint erbjuder organisations-och sitespecifika inställningar för domän begränsning. Grupper och team använder listorna domän tillåta och neka i Azure AD. Se till att konfigurera båda inställningarna för att undvika oönskad delning och säkerställa en enhetlig användar upplevelse:

- [Begränsa delning av SharePoint-och OneDrive-innehåll efter domän](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [Tillåta eller blockera inbjudningar för B2B-användare från specifika organisationer](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

Med Microsoft 365 kan du dela filer och mappar anonymt genom att använda *alla* delnings länkar. *Alla* länkar kan vidarekopplas och alla som har länken kan komma åt det delade objektet. Beroende på känsligheten hos dina data kan du bestämma hur du vill att *alla* länkar ska användas-inklusive att stänga av dem helt, begränsa länk behörigheter till skrivskyddade eller ange en förfallo tid för dem:

- [Inaktivera Alla-länkar](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)

- [Ange länk behörigheter för alla länkar](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [Ange ett utgångsdatum för Alla-länkar](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

När du delar filer eller mappar har användarna flera länk typer att välja bland. För att minska risken för oavsiktlig olämplig delning kan du ändra standard länk typen som visas för användarna när de delar. Om du till exempel ändrar standardvärdet från *alla* länkar – som tillåter anonym åtkomst till *personer i dina organisations* länkar kan risken för oönskad extern delning av känslig information minskas:

- [Ändra standardlänktyp för en webbplats](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

Om din organisation har känslig information som du vill dela med gästerna, men inte är orolig för olämplig delning, kan du begränsa extern delning av filer och mappar till medlemmar i vissa säkerhets grupper. På så sätt kan du begränsa delning externt till en viss grupp med personer eller kräva att användarna vidtar utbildning kring en lämplig extern delning innan de läggs till i säkerhets gruppen:

- [Begränsa extern delning till angivna säkerhets grupper](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

Grupper och team har inställningar på organisations nivå som tillåter eller nekar gäst åtkomst. Även om du kan [begränsa gäst åtkomst till specifika team eller grupper med Microsoft PowerShell](per-group-guest-access.md)rekommenderar vi att du gör detta genom att använda en känslighets etikett. Med känslighets etiketter kan du automatiskt tillåta eller neka gäst åtkomst baserat på den etikett som används:

- [Använd känslighets etiketter för att skydda innehåll i Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

I Microsoft 365 kan du dela information på många olika sätt. Om du har känslig information och vill begränsa hur den delas kan du läsa alternativen för att begränsa delning:

- [Begränsa delning i Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

Fler resurser:

- [Konfigurera säkerhet samarbete med hjälp av Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [Metodtips för att dela filer och mappar med oautentiserade användare](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [Begränsa oavsiktlig exponering för filer när de delas med personer utanför organisationen](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [Skapa en säker miljö för gästdelning](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [Aktivera externt samarbete och hantera vem som kan bjuda in gäster](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Användar hantering

När grupper och team utvecklas i din organisation är det lämpligt att granska grupp-och grupp medlemskap regelbundet. Det här kan vara särskilt användbart för grupper och grupper med ändrings bara medlemskap, de som innehåller känslig information eller sådana som innehåller gäster. Du bör ställa in åtkomst granskningar för dessa team och grupper:

- [Vad är en granskning av Azure AD Access?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

Många organisationer har affärs samarbete med andra organisationer eller viktiga leverantörer som de samarbetar med. Det kan vara svårt att hantera användar hantering och åtkomst till resurser i dessa scenarier. Överväg att automatisera vissa användar hanterings uppgifter och till och med överföra vissa av dem till din partner organisation:

- [Vad är hantering av Azure AD Management?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

Privata kanaler i grupper möjliggör vissa konversationer och fildelning mellan en delmängd av grupp medlemmar. Beroende på dina företags behov kanske du vill tillåta eller blockera den här funktionen.

- [Privata kanaler i Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [Hantera livs cykeln för privata kanaler i Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

Fler resurser:

- [Azure Active Directory Identity styrelse](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a>Relaterade ämnen

[Säkerhet och efterlevnad för Microsoft Teams](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[Hantera delnings inställningar i SharePoint](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[Skapa och hantera ett externt nätverk i Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[Konfigurera Teams med tre skyddsnivåer](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
