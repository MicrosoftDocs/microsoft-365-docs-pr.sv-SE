---
title: Reglerar åtkomst i Microsoft 365 grupper, Teams och SharePoint
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
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Läs mer om hur du styr åtkomst Microsoft 365 grupper, Teams och SharePoint.
ms.openlocfilehash: 3e0485813a264fe9042e0de9596ba07e50ef72a3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538153"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Reglerar åtkomst i Microsoft 365 grupper, Teams och SharePoint

Det finns många kontroller som gör att du kan styra hur personer får åtkomst till resurser i grupper, team och SharePoint. Gå igenom de här alternativen och fundera på hur de kan mappa till dina affärsbehov, dina datas känslighet och vilka personer som användarna behöver samarbeta med.

Följande tabell innehåller en snabbreferens för de åtkomstkontroller som är tillgängliga i Microsoft 365. Ytterligare information ges i följande avsnitt.

|Kategori|Beskrivning|Referens|
|:-------|:----------|:--------|
|Medlemskap|||
||Identifiering av privata team|[Hantera identifiering av privata team i Microsoft Teams](/microsoftteams/manage-discovery-of-private-teams)|
||Dynamiskt gruppmedlemskap baserat på regler|[Skapa eller uppdatera en dynamisk grupp i Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)|
||Styr vem som kan dela filer, mappar och webbplatser.|[Konfigurera och hantera åtkomstförfrågningar](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|Villkorlig åtkomst|||
||Multifaktorautentisering|[Azure AD Multi-Factor Authentication](/azure/active-directory/authentication/concept-mfa-howitworks)|
||Styr enhetsåtkomsten baserat på gruppens, gruppens eller webbplatsens känslighet.|[Använd känslighetsetiketter för att skydda innehåll i Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Begränsa webbplatsåtkomsten för ohanterade enheter.|[Styra SharePoint åtkomst från ohanterade enheter](/sharepoint/control-access-from-unmanaged-devices)|
||Kontrollera webbplatsåtkomst baserat på plats|[Hantera åtkomst till SharePoint och OneDrive data baserat på nätverksplats](/sharepoint/control-access-based-on-network-location)|
|Gäståtkomst|||
||Tillåt eller blockera SharePoint delning från angivna domäner.|[Begränsa delning av SharePoint och OneDrive innehåll per domän](/sharepoint/restricted-domains-sharing)|
||Tillåta eller blockera team- eller gruppmedlemskap från angivna domäner.|[Tillåta eller blockera inbjudningar till B2B-användare från specifika organisationer](/azure/active-directory/b2b/allow-deny-list)|
||Förhindra anonym delning.|[Inaktivera Alla-länkar](./share-limit-accidental-exposure.md#turn-off-anyone-links)|
||Kontrollera behörigheterna för anonyma åtkomstlänkar.|[Ange länkbehörigheter för länkar för alla](./best-practices-anonymous-sharing.md#set-link-permissions)|
||Kontrollera förfallotiden för anonyma delningslänkar.|[Ange ett utgångsdatum för Alla-länkar](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)|
||Styr delningslänken som visas för användarna som standard.|[Ändra standardlänktyp för en webbplats](/sharepoint/change-default-sharing-link)|
||Begränsa extern delning till specifika personer.|[Begränsa extern delning till angivna säkerhetsgrupper](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Kontrollera gäståtkomst till en grupp, grupp eller webbplats baserat på informationskänslighet.|[Använd känslighetsetiketter för att skydda innehåll i Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Inaktivera delningsalternativ.|[Begränsa delning i Microsoft 365](./microsoft-365-limit-sharing.md)|
|Användarhantering|||
||Granska grupp- och gruppmedlemskap regelbundet.|[Vad är azure AD-åtkomstgranskningar?](/azure/active-directory/governance/access-reviews-overview)|
||Automatisera åtkomsthanteringen för grupper och team.|[Vad är hantering av Azure AD-berättigande?](/azure/active-directory/governance/entitlement-management-overview)|
||Tillåt eller blockera personer från att skapa privata kanaler i Teams.|[Hantera livscykeln för privata kanaler i Microsoft Teams](/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>Medlemskap

Medlemskap i team och grupper styrs av ägare. Medlemmar kan bjuda in andra, men inbjudningarna skickas till ägare för godkännande. Offentliga team och grupper kan upptäckas av alla i organisationen, men du kan styra om privata team och grupper ska kunna upptäckas:

- [Hantera identifiering av privata team i Microsoft Teams](/microsoftteams/manage-discovery-of-private-teams)

Du kan hantera medlemskap i en grupp eller ett team dynamiskt baserat på vissa villkor, till exempel avdelning. I det här fallet kan medlemmar och ägare inte bjuda in personer till teamet. Dynamiska grupper använder metadata som du definierar i Azure Active Directory för att styra vem som är medlem i gruppen. Se till att de metadata som du använder är fullständiga och uppdaterade eftersom felaktiga metadata kan leda till att användare lämnas utanför grupper eller att felaktiga användare läggs till.

- [Skapa eller uppdatera en dynamisk grupp i Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)

SharePoint-webbplatser möjligheten att lägga till ägare, medlemmar och besökare utanför grupp- eller teammedlemskap. Beroende på dina behov kan du begränsa vem som kan bjuda in personer till webbplatsen. Beroende på hur känslig informationen på en viss webbplats är kan du dessutom begränsa vem som kan dela filer och mappar. Dessa begränsningar konfigureras av gruppen, gruppen eller webbplatsägaren:

- [Konfigurera och hantera åtkomstförfrågningar](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>Villkorlig åtkomst

Med Microsoft 365 kan du kräva multifaktorautentisering för både personer inom och utanför organisationen. Det finns många alternativ för situationen när personer uppmanas att ange en andra faktor för autentisering. Vi rekommenderar att du distribuerar multifaktorautentisering för organisationen:

- [Azure AD Multi-Factor Authentication](/azure/active-directory/authentication/concept-mfa-howitworks)

Om du har känslig information i vissa grupper och team kan du tillämpa principer för enhetshantering baserat på en grupps eller gruppens känslighetsetikett. Du kan blockera åtkomst helt från ohanterade enheter eller tillåta begränsad, endast webbåtkomst:

- [Använd känslighetsetiketter för att skydda innehåll i Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser](../compliance/sensitivity-labels-teams-groups-sites.md)

I SharePoint kan du begränsa åtkomsten till webbplatser från angivna nätverksplatser.

- [Hantera åtkomst till SharePoint och OneDrive data baserat på nätverksplats](/sharepoint/control-access-based-on-network-location)


Fler resurser:

- [Planera en distribution av villkorsstyrd åtkomst](/azure/active-directory/conditional-access/plan-conditional-access)

- [Microsoft Intune översikt](/mem/intune/fundamentals/what-is-intune)

- [Styra SharePoint åtkomst från ohanterade enheter](/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Gäståtkomst

Du kan begränsa gäster baserat på domänen för deras e-postadress. SharePoint erbjuder organisationsomfattande och webbplatsspecifika domänbegränsningsinställningar. Grupper och Teams använder listorna tillåt och nekade domäner i Azure AD. Se till att konfigurera båda inställningarna för att undvika oönskad delning och säkerställa en enhetlig användarupplevelse:

- [Begränsa delning av SharePoint och OneDrive innehåll per domän](/sharepoint/restricted-domains-sharing)

- [Tillåta eller blockera inbjudningar till B2B-användare från specifika organisationer](/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 tillåter anonym delning av filer och mappar med hjälp av *Alla som* delar länkar. *Alla* länkar kan vidarebefordras och alla som har länken kan komma åt det delade objektet. Beroende på dina datas känslighet kan  du överväga att styra hur Alla-länkar används – inklusive att inaktivera dem helt, begränsa länkbehörigheter till skrivskyddat eller ange en förfallotid för dem:

- [Inaktivera Alla-länkar](./share-limit-accidental-exposure.md#turn-off-anyone-links)

- [Ange länkbehörigheter för länkar för alla](./best-practices-anonymous-sharing.md#set-link-permissions)

- [Ange ett utgångsdatum för Alla-länkar](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)

När du delar filer eller mappar har användarna flera länktyper att välja bland. Du kan minska risken för olämplig delning genom att ändra standardlänktypen som visas för användare när de delar. Om du till exempel  ändrar standardinställningen från Alla-länkar – som tillåter anonym åtkomst – till Personer i din organisation kan det minska risken för oönskad extern delning av känslig information: 

- [Ändra standardlänktyp för en webbplats](/sharepoint/change-default-sharing-link)

Om din organisation har känsliga data som du behöver dela med gäster, men du är orolig för olämplig delning, kan du begränsa extern delning av filer och mappar till medlemmar i angivna säkerhetsgrupper. På så sätt kan du begränsa delning externt till en viss grupp av personer, eller kräva att dina användare utbildar sig om lämplig extern delning innan de lägger till dem i säkerhetsgruppen:

- [Begränsa extern delning till angivna säkerhetsgrupper](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

Grupper och Teams har inställningar på organisationsnivå som tillåter eller nekar gäståtkomst. Du kan begränsa gäståtkomst till vissa team eller grupper genom att använda [Microsoft PowerShell,](per-group-guest-access.md)men vi rekommenderar att du gör det med hjälp av en känslighetsetikett. Med känslighetsetiketter kan du automatiskt tillåta eller neka gäståtkomst baserat på den etikett som används:

- [Använd känslighetsetiketter för att skydda innehåll i Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser](../compliance/sensitivity-labels-teams-groups-sites.md)

I en miljö där du ofta bjuder in gäster till grupper och team kan du överväga att konfigurera regelbundna granskningar av gäståtkomst. Ägare kan uppmanas att granska gäster i sina grupper och team och godkänna eller neka åtkomst.

- [Konfigurera granskning av gäståtkomst](/microsoft-365/solutions/create-secure-guest-sharing-environment#set-up-guest-access-reviews)

Microsoft 365 finns många olika sätt att dela information. Om du har känslig information och vill begränsa hur den delas kan du läsa alternativen för att begränsa delning:

- [Begränsa delning i Microsoft 365](./microsoft-365-limit-sharing.md)

Fler resurser:

- [Konfigurera säkerhet samarbete med hjälp av Microsoft 365](./setup-secure-collaboration-with-teams.md)

- [Metodtips för att dela filer och mappar med oautentiserade användare](./best-practices-anonymous-sharing.md)

- [Begränsa oavsiktlig exponering för filer när de delas med personer utanför organisationen](./share-limit-accidental-exposure.md)

- [Skapa en säker miljö för gästdelning](./create-secure-guest-sharing-environment.md)

- [Aktivera B2B externt samarbete och hantera vem som kan bjuda in gäster](/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Användarhantering

När grupper och team utvecklas i organisationen är det bra att regelbundet granska team- och gruppmedlemskap. Det kan vara särskilt användbart för grupper och grupper med ett annat medlemskap, de som innehåller känslig information eller grupper som innehåller gäster. Överväg att skapa åtkomstgranskningar för dessa team och grupper:

- [Vad är azure AD-åtkomstgranskningar?](/azure/active-directory/governance/access-reviews-overview)

Många organisationer har företagssamarbeten med andra organisationer eller viktiga leverantörer som de samarbetar på djupet med. Användarhantering och åtkomst till resurser kan vara svåra att hantera i de här scenarierna. Du kan även automatisera vissa användarhanteringsuppgifter och även lägga över en del av dem till din partnerorganisation:

- [Vad är hantering av Azure AD-berättigande?](/azure/active-directory/governance/entitlement-management-overview)

Privata kanaler i Teams tillåter begränsad konversation och fildelning mellan en delmängd teammedlemmar. Beroende på dina specifika affärsbehov kanske du vill tillåta eller blockera den här funktionen.

- [Privata kanaler i Microsoft Teams](/MicrosoftTeams/private-channels)

- [Hantera livscykeln för privata kanaler i Microsoft Teams](/MicrosoftTeams/private-channels-life-cycle-management)

Fler resurser:

- [Azure Active Directory Identitetsstyrning](/azure/active-directory/governance)

## <a name="related-topics"></a>Relaterade ämnen

[Planering av samarbetsstyrning steg för steg](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Skapa din plan för samarbetesstyrning](collaboration-governance-first.md)

[Säkerhet och efterlevnad för Microsoft Teams](/microsoftteams/security-compliance-overview)

[Hantera delningsinställningar i SharePoint](/sharepoint/turn-external-sharing-on-or-off)

[Skapa och hantera ett externt nätverk i Yammer](/yammer/work-with-external-users/create-and-manage-an-external-network)

[Konfigurera Teams med tre skyddsnivåer](./configure-teams-three-tiers-protection.md)