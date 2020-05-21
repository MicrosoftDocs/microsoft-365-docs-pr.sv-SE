---
title: Grundläggande infrastruktur för Microsoft 365 för företag för andra än stora företag
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 05/15/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Gå igenom de förenklade faserna i den grundläggande infrastrukturen för Microsoft 365 för företag för andra organisationer än stora företag.
ms.openlocfilehash: caca093463e4a180f50c880a77fa18399103f069
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268391"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure-for-non-enterprises"></a>Grundläggande infrastruktur för Microsoft 365 för företag för andra än stora företag

Andra organisationer än stora företag kan också distribuera Microsoft 365 för företag och uppleva affärsvärdet för en integrerad och säker infrastruktur som gör det möjligt att samarbeta och frigöra kreativitet. Andra organisationer än stora företag har vanligtvis:

- En mindre del lokal IT-infrastruktur, t.ex. e-post och filservrar och en AD DS-domän (Active Directory Domain Services), eller ingen alls.
- En liten IT-personalstyrka, varav de flesta är IT-generalister snarare än specialister inom en specifik teknik eller ett kunskapsområde, t.ex. nätverk eller e-post.

För mindre organisationer erbjuder Microsoft [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business). Det finns dock anledningar till varför du kan behöva Microsoft 365 för företag, till exempel:

- Din organisation behöver mer eller kommer att behöva mer än 300 Microsoft 365-licenser, vilket är maximalt antal för Microsoft 365 Business.
- Din organisation behöver de avancerade funktionerna för produktivitet, rösttjänster, säkerhet och analys som inte finns i Microsoft 365 Business.

I den här artikeln beskrivs en förenklad distribution av den grundläggande infrastrukturen för Microsoft 365 för företag, som passar företag som inte har lika stora behov som storföretag.

## <a name="first-set-up-your-subscription"></a>Konfigurera först din prenumeration

Du måste konfigurera DNS-domänerna (Domain Name System) för prenumerationen. Om du redan har en Microsoft 365-prenumeration borde detta vara gjort. Annars följer du anvisningarna i [Lägga till en domän i Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).

Därefter måste du konfigurera ytterligare säkerhet för Microsoft 365. Följ anvisningarna i [Konfigurera ökad säkerhet](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

## <a name="phase-1-networking"></a>Fas 1: Nätverk

Organisationer som inte är stora företag har vanligtvis lokala Internetanslutningar på varje kontor och använder inte proxyservrar, brandväggar eller enheter för paketkontroll. Den Internetleverantör som betjänar varje kontor har en regional lokal DNS-server så att trafiken dirigeras till den Microsoft 365-nätverksplats som ligger närmast dina kontor och de lokala användarna. Mer information finns i [Konfigurera lokala Internetanslutningar för varje kontor](networking-dns-resolution-same-location.md).

Därför behöver du bara verifiera med din Internetleverantör att anslutningen på var och en av dina kontorsplatser:

- Använder en regional lokal DNS-server.
- Passar för nuvarande och framtida behov allteftersom användarna börjar använda fler Microsoft 365-molntjänster.

Om du använder proxyservrar, brandväggar eller enheter för paketkontroll kan du läsa [Konfigurera förbikoppling av trafik](networking-configure-proxies-firewalls.md) för mer information om hur du optimerar prestanda för Microsoft 365-tjänster.

### <a name="your-configuration-so-far"></a>Din konfiguration hittills

Här är en visuell sammanfattning med fas 1-elementet markerat. **Din organisation** kan bestå av flera kontor, som vart och ett har en lokal Internetanslutning med en Internetleverantör som använder en regional lokal DNS-server. Via Internetleverantören kan användarna på varje kontor nå närmaste Microsoft 365-nätverksplats och resurserna för Microsoft 365-prenumerationen.

![Din organisation efter nätverksfasen](../media/deploy-foundation-infrastructure-non-enterprises/networking-config.png)

## <a name="phase-2-identity"></a>Fas 2: Identitet

Alla anställda i din organisation måste kunna logga in, vilket kräver ett användarkonto i Azure Active Directory-klientorganisationen (Azure AD) för Microsoft 365 för företag-prenumerationen. Grupper används sedan för att hålla samman användarkonton och andra grupper för att kommunicera och få tillgång till resurser som kräver behörighet, t.ex. en SharePoint Online-webbplats eller ett team. 

### <a name="administrator-accounts"></a>Administratörskonton

Skydda dina användarkonton för global administratör genom att kräva starka lösenord och multifaktorautentisering (MFA). Mer information finns i [Skydda globala administratörskonton](identity-create-protect-global-admins.md#protect-global-administrator-accounts).

Om din organisation kräver hög säkerhet och du har Microsoft 365 E5, använder du Azure AD Privileged Identity Management för att aktivera just-in-time-administratörsåtkomst. Mer information finns i [Konfigurera globala administratörer på begäran](identity-create-protect-global-admins.md#identity-pim).

### <a name="recommendations-for-groups"></a>Rekommendationer för grupper

Om du har en lokal AD DS-domän fortsätter du att använda dessa grupper i Microsoft 365 för företag som grupper i Azure AD.

Om du inte har en lokal AD DS-domän skapar du säkerhetsgrupper i Azure AD med dessa säkerhetsnivåer.

| Säkerhetsnivå | Beskrivning | Exempel |
|:-------|:-----|:-----|
| Grundläggande | Det här är en minimal standard för att skydda data och identiteter och enheter som har åtkomst till dina data. <BR><BR> Det här är vanligtvis den största delen av organisationens data som hanteras av de flesta av användarna. | Grupper för personal som jobbar på fältet och med kunder, till exempel försäljning, marknadsföring, support, administration och tillverkning. |
| Känslig | Det här är ytterligare skydd för en underuppsättning av dina data som måste skyddas mer än på grundläggande nivå. Dessa grupper innehåller användare som använder och skapar känsliga data som är avsedda för avdelningar och projekt som inte är avsedda att bli tillgängliga för alla. | Produkt- eller marknadsgrupper som utvecklar kommande produkter |
| Strikt reglerad | Det här är den högsta skyddsnivån för en liten mängd data som är strikt sekretessbelagda, vilka kan vara intellektuella egendomar eller affärshemligheter eller data som måste följa säkerhetsföreskrifter. |  Forskningsteam och juridiska och ekonomiska team, eller team som lagrar eller använder kund- eller partnerdata. |
||||

### <a name="hybrid-identity"></a>Hybrididentitet

Om du har en lokal AD DS-domän måste du synkronisera uppsättningen användarkonton, grupper och kontakter för din domän med Azure AD-klientorganisationen för din Microsoft 365 för företag-prenumeration. För andra än stora företag konfigurerar du Azure AD Connect på en server med synkronisering av lösenordshash (PHS). Mer information finns i [Synkronisera identiteter](identity-add-user-accounts.md#synchronize-identities-for-hybrid-identity).

### <a name="more-secure-user-access-with-conditional-access-policies"></a>Säkrare användaråtkomst med principer för villkorsstyrd åtkomst

Med Azure AD utvärderas villkoren för användarinloggningar, och principer för villkorsstyrd åtkomst kan användas för att bevilja eller neka åtkomst och för att vidta fler åtgärder som måste utföras för att slutföra inloggningen. Om till exempel Azure AD fastställer att inloggningen sker under medelhög eller hög risknivå, kan det krävas att användaren utför MFA för att slutföra inloggningen.

Du kan använda principer för villkorsstyrd åtkomst för användarkonton eller grupper. Om du vill göra det enklare att använda principer för villkorsstyrd åtkomst skapar du följande Azure AD-säkerhetsgrupper i din organisation:

- BASELINE

  Innehåller grupper eller användarkonton för användare med åtkomst till grundläggande data.

- SENSITIVE

  Innehåller grupper eller användarkonton för användare med åtkomst till känsliga data.

- HIGHLY-REGULATED

  Innehåller grupper eller användarkonton för användare med åtkomst till strikt reglerade data.

- COND-ACCESS-EXCLUDE

  En tom grupp som du kan använda för att tillfälligt undanta en användare från principer för villkorsstyrd åtkomst.

Här följer en lista över principer för villkorsstyrd åtkomst i Azure AD att aktivera eller skapa.

| Princip för villkorsstyrd åtkomst i Azure AD | Grupper som den gäller för |
|:------|:-----|
| Grundläggande princip: Kräv MFA för administratörer | Principen gäller för administratörsroller, så inga grupper måste anges. Principen behöver bara aktiveras. Alla efterföljande principer måste skapas och aktiveras. |
| Blockera klienter som inte har stöd för modern autentisering | Välj Alla användare i principinställningarna. |
| Kräv MFA när inloggningsrisken är medelhög eller hög (kräver Microsoft 365 E5) | BASELINE |
| Kräv MFA när inloggningsrisken är låg, medel eller hög (kräver Microsoft 365 E5) | SENSITIVE |
| Kräv alltid MFA | HIGHLY-REGULATED |
| Kräv godkända appar på iOS- och Android-enheter | BASELINE, SENSITIVE, HIGHLY-REGULATED |
| Kräv kompatibla PC-datorer | BASELINE |
| Kräv kompatibla PC-datorer och iOS- och Android-enheter | SENSITIVE, HIGHLY-REGULATED |
|||

Det här är användarriskprincipen Azure AD Identity Protection (kräver Microsoft 365 E5) som du kan skapa och aktivera.

| Användarriskprincipen Azure AD Identity Protection | Grupper som den gäller för |
|:------|:-----|
| Användare med hög risk måste byta lösenord | Välj Alla användare i principinställningarna. |
|||

Mer information finns i [Vanliga principer för identitets- och enhetsåtkomst](identity-access-policies.md).

### <a name="groups-for-easier-management"></a>Grupper för enklare hantering

Här är några av de funktioner som kan göra grupp- och licenshantering lättare för dig.

| Funktion | Användning |
|:------|:-----|
| Grupphantering för självbetjäning | Tillåt hantering av Azure AD-grupper för gruppägare istället för IT-personal. Mer information finns i [Grupphantering för självbetjäning](identity-use-group-management.md#allow-users-to-create-and-manage-their-own-groups). |
| Dynamiskt gruppmedlemskap | Konfigurera automatiskt tillägg eller borttagning av användarkonton från Azure AD-grupper baserat på användarkontons attribut, t.ex. avdelning eller land. Mer information finns i [Dynamiskt gruppmedlemskap](identity-use-group-management.md#set-up-dynamic-group-membership). |
| Gruppbaserad licensiering | Använd gruppmedlemskap för att automatiskt tilldela eller ta bort licenser för användarkonton. Mer information finns i [Gruppbaserad licensiering](identity-use-group-management.md#set-up-automatic-licensing). |
|  |  |

Om du använder gruppbaserad licensiering kan du skapa en grupp med namnet LICENSED för användarkontonamn som tilldelats en Microsoft 365 för företag-licens.

### <a name="monitor-user-access"></a>Övervaka användaråtkomst

Om du har Microsoft 365 E5 kan du med hjälp av Azure AD Identity Protection övervaka och analysera användarinloggningar för att upptäcka angrepp mot autentiseringsuppgifter. Mer information finns i [Skydda mot obehörig inloggning](identity-secure-user-sign-ins.md#protect-against-credential-compromise).

### <a name="your-configuration-so-far"></a>Din konfiguration hittills

Här är en visuell sammanfattning av identitetsfasen för hybrididentitet, med befintliga och nya element markerade.

![Din organisation efter identitetsfasen för hybrididentitet](../media/deploy-foundation-infrastructure-non-enterprises/identity-config.png)
 
De nya och markerade hybrididentitetselementen inkluderar:
 
|||
|:------:|:-----|
| ![En lokal AD DS-domän med användarkonton och grupper](../media/deploy-foundation-infrastructure-non-enterprises/identity-adds.png) | En lokal AD DS-domän med användarkonton och grupper. |
| ![En Windows-baserad server med Azure AD Connect](../media/deploy-foundation-infrastructure-non-enterprises/identity-aadconnect.png) | En Windows-baserad server med Azure AD Connect. |
| ![Synkroniserad uppsättning av AD DS-användarkonton och grupper i Azure AD](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts.png) | Synkroniserad uppsättning av AD DS-användarkonton och grupper i Azure AD. |
| ![Azure AD-inställningar för autentisering, skydd av globala konton och enklare hantering av grupper och licenser](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | Azure AD-inställningar för autentisering, skydd av globala konton och enklare hantering av grupper och licenser. |
| ![Principer för villkorsstyrd åtkomst i Azure AD](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | Principer för villkorsstyrd åtkomst i Azure AD. |
|||

Här är en visuell sammanfattning av fasen för helt molnbaserad identitet, med nya element markerade.

![Din organisation efter identitetsfasen för helt molnbaserad identitet](../media/deploy-foundation-infrastructure-non-enterprises/identity-config-cloud-only.png)
 
De nya och markerade elementen för helt molnbaserad identitet inbegriper:
 
|||
|:------:|:-----|
| ![Användarkonton och grupper i Azure AD](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts-cloud-only.png) | Användarkonton och grupper i Azure AD. |
| ![Azure AD-inställningar för autentisering, skydd av globala konton och enklare hantering av grupper och licenser](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | Azure AD-inställningar för autentisering, skydd av globala konton och enklare hantering av grupper och licenser. |
| ![Principer för villkorsstyrd åtkomst i Azure AD](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | Principer för villkorsstyrd åtkomst i Azure AD. |
|||

## <a name="phase-3-windows-10-enterprise"></a>Fas 3: Windows 10 Enterprise

Här är dina alternativ för att säkerställa att dina Windows 10 Enterprise-enheter är integrerade i identitets- och säkerhetsinfrastrukturen för Microsoft 365 för företag:

- Hybrid (du har en lokal AD DS-domän)

  Varje befintlig Windows 10 Enterprise-enhet som redan är ansluten till din AD DS-domän, ska du ansluta till Azure AD-klientorganisationen. Mer information finns i [Konfigurera hybridanslutna Azure Active Directory-enheter](https://go.microsoft.com/fwlink/p/?linkid=872870).

  Varje ny Windows 10 Enterprise-enhet ska du ansluta till din AD DS-domän, och sedan ansluta dem till Azure AD-klientorganisationen.

  Varje Windows 10 Enterprise-enhet ska du registrera för hantering av mobila enheter. Anvisningar finns i [Registrera en Windows 10-enhet med Intune med hjälp av en grupprincip](https://go.microsoft.com/fwlink/p/?linkid=872871).

- Endast molnet (du har inte en lokal AD DS-domän)

  Anslut varje Windows 10 Enterprise-enhet till Azure AD-klientorganisationen för din prenumeration.

  Mer information finns [Ansluta din arbetsenhet till organisationens nätverk](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network).


När du har installerat och anslutit, installerar varje Windows 10 Enterprise-enhet automatiskt uppdateringar från molntjänsten Windows Update för företag. Det finns vanligtvis inget behov av att konfigurera en infrastruktur för distribution och installation av Windows 10-uppdateringar i organisationer som inte är stora företag.

### <a name="your-configuration-so-far"></a>Din konfiguration hittills

Här är en visuell sammanfattning av Windows 10 Enterprise-fasen med nya element markerade.

![Din organisation efter Windows 10 Enterprise-fasen](../media/deploy-foundation-infrastructure-non-enterprises/win10-config.png)
 
De nya och markerade Windows 10 Enterprise-elementen inkluderar:

|||
|:------:|:-----|
| ![Windows 10 Enterprise installerat på Windows-enheter](../media/deploy-foundation-infrastructure-non-enterprises/win10-device.png) | Windows 10 Enterprise installerat på Windows-enheter, med en lokal bärbar dator som exempel. |
| ![Volume Licensing Service Center](../media/deploy-foundation-infrastructure-non-enterprises/win10-cloud.png) | Volume Licensing Service Center, som innehåller avbildningar för nya installationer av Windows 10 Enterprise, och tjänsten Windows Update för företag, som innehåller de senaste uppdateringarna. |
|||

## <a name="phase-4-microsoft-365-apps-for-enterprise"></a>Fas 4: Microsoft 365-applikationer för företag

Microsoft 365 Enterprise innehåller Microsoft 365-applikationer för företag, prenumerationsversionen av Microsoft Office. Som Office 2016 eller Office 2019 installeras Microsoft 365-applikationer för företag direkt på dina klientenheter. Microsoft 365-applikationer för företag får däremot regelbundet uppdateringar som innehåller nya funktioner. Mer information finns i [Om Microsoft 365-applikationer för företag](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).

För andra organisationer än stora företag installerar du Microsoft 365-applikationer för företag manuellt på enheterna, som kan omfatta Windows-, iOS- och Android-enheter. Detta kan göras som en del av att förbereda en ny enhet för användning, eller av användaren som en del av introduktionsprocessen.

I båda fallen loggar administratören eller användaren in på Office 365-portalen på https://portal.office.com. På fliken **Microsoft Office Home** klickar du på **Installera Office** och genomför installationsprocessen.

Funktionsuppdateringar för Microsoft 365-applikationer för företag laddas ned varje månad av alla datorer där de är installerade. Det finns vanligtvis inget behov av att konfigurera en infrastruktur för distribution av uppdateringar för Microsoft 365-applikationer för företag i organisationer som inte är stora företag. 

### <a name="your-configuration-so-far"></a>Din konfiguration hittills

Här är en visuell sammanfattning av fasen för Microsoft 365-applikationer för företag med nya element markerade.

![Din organisation efter fasen för Microsoft 365-applikationer för företag](../media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-config.png)
 
De nya och markerade elementen för Microsoft 365-applikationer för företag omfattar:
 
|||
|:------:|:-----|
| ![Microsoft 365-applikationer för företag installerat på enheter](../media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-device.png) | Microsoft 365-applikationer för företag installerat på enheter, med en lokal bärbar dator som exempel. |
| ![Office Content Delivery Network (CDN) för Microsoft 365-applikationer för företag](../media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-cdn.png) | Office Content Delivery Network (CDN) för Microsoft 365-applikationer för företag, som enheterna har tillgång till för uppdateringar för Microsoft 365-applikationer för företag. |
|||

## <a name="phase-5-mobile-device-management"></a>Fas 5: Hantering av mobila enheter

Microsoft 365 för företag innehåller Microsoft Intune för hantering av mobila enheter. Med Intune kan du hantera enheter för Windows, iOS, Android och macOS och skydda åtkomsten till organisationens resurser, inklusive data. I Intune används användar-, grupp- och datorkonton för Azure AD.

Intune tillhandahåller två typer av hantering av mobila enheter:

- MDM (Mobile Device Management) är när enheter registreras i Intune. När de har registrerats är de hanterade enheter och kan ta emot principer, regler och inställningar som används av din organisation. Dessa typer av enheter ägs vanligtvis av din organisation och utfärdas till dina anställda.

- Användare med egna personliga enheter kanske inte vill registrera sina enheter eller att de hanteras av Intune med dina principer och inställningar. Men du måste ändå skydda organisationens resurser och data. I det här scenariot kan du skydda dina appar med MAM (hantering av mobilprogram).  

Intune-principer kan upprätthålla enhetsefterlevnad och programskydd. Här följer en lista över Intune-principer som du kan skapa.

| Intune-principer | Grupper som den gäller för |
|:------|:-----|
| Policy för enhetsefterlevnad för Windows | BASELINE, SENSITIVE, HIGHLY-REGULATED |
| Policy för enhetsefterlevnad för iOS | SENSITIVE, HIGHLY-REGULATED |
| Enhetsefterlevnad för macOS | SENSITIVE, HIGHLY-REGULATED |
| Policy för enhetsefterlevnad för Android och Android Enterprise | SENSITIVE, HIGHLY-REGULATED |
| Appskyddsprincip för iOS | BASELINE, SENSITIVE, HIGHLY-REGULATED |
| Appskyddsprincip för macOS | BASELINE, SENSITIVE, HIGHLY-REGULATED |
| Appskyddsprincip för Android och Android Enterprise | BASELINE, SENSITIVE, HIGHLY-REGULATED |
|||
    
Mer information finns i [Vanliga principer för identitets- och enhetsåtkomst](identity-access-policies.md).

### <a name="your-configuration-so-far"></a>Din konfiguration hittills

Här är en visuell sammanfattning av fasen för hantering av mobila enheter, med nya element markerade.

![Din organisation efter fasen för hantering av mobila enheter](../media/deploy-foundation-infrastructure-non-enterprises/mdm-config.png)
 
De nya och markerade elementen för hantering av mobila enheter inkluderar:

|||
|:------:|:-----|
| ![Enheter som är registrerade i Intune](../media/deploy-foundation-infrastructure-non-enterprises/mdm-device.png) | Enheter som är registrerade i Intune, som visar en lokal bärbar dator med Windows 10 Enterprise som exempel. |
| ![Intune-principer för enhetsefterlevnad och programskydd](../media/deploy-foundation-infrastructure-non-enterprises/mdm-policies.png) | Intune-principer för enhetsefterlevnad och programskydd. |
|||

## <a name="phase-6-information-protection"></a>Fas 6: Informationsskydd

Microsoft 365 för företag har en mängd funktioner för informationsskydd som gör att du kan hantera klassificering av data på olika sätt genom att tillämpa olika nivåer av styrning, säkerhet och skydd. 

Normal korrespondens mellan de flesta anställda och de dokument som de arbetar med behöver till exempel en viss grundläggande skyddsnivå. Ekonomiposter, kunddata och intellektuell egendom kräver en högre skyddsnivå.

Det första steget för en strategi för informationsskydd är att fastställa skyddsnivåer. Många organisationer använder de här nivåerna, som redan används för principer för villkorsstyrd åtkomst:

- Grundläggande

  Exempel är normal företagskommunikation (e-post) och filer för administrations-, försäljnings- och supportpersonal.

- Känslig

  Exempel är ekonomisk och juridisk information och data för forskning och utveckling för nya produkter eller tjänster.

- Strikt reglerad

  I exemplen ingår personligt identifierbar information om kunder och partner och organisationens strategiska planer eller intellektuella egendom.

Baserat på dessa datasäkerhetsnivåer är nästa steg att identifiera och implementera:

- Vanliga typer av känslig information

  Microsoft 365 tillhandahåller ett brett urval av olika typer av känslig information, t.ex. sjukvård och kreditkortsnummer. Om du inte hittar den du behöver i den angivna listan kan du skapa din egen.

- Kvarhållningsetiketter

  Om du vill följa organisationens principer och regionala bestämmelser kan du behöva ange hur länge vissa typer av dokument eller dokument med specifikt innehåll ska behållas. Du kan implementera det för e-post och dokument med hjälp av kvarhållningsetiketter. Kvarhållningsetiketter kan också användas tillsammans med DLP-principer (dataförlustskydd) som kan begränsa delning av filer eller e-post utanför din organisation.

- Känslighetsetiketter

  Du kan märka e-post eller dokument med en beskrivande känslighetsetikett så att ytterligare säkerhetsnivåer kan tillämpas. Exempel är vattenstämplar, kryptering och behörigheter, som anger vem som har behörighet att komma åt e-postmeddelandet eller dokumentet och vad de har tillåtelse att göra.

Mer information finns i [Klassificeringstyper i Microsoft 365](infoprotect-configure-classification.md#microsoft-365-classification-types).

Om du använder känslighetsetiketter med behörigheter kan du behöva skapa ytterligare säkerhetsgrupper för att definiera vem som får göra vad med e-post och dokument som har tillämpade känslighetsetiketter. 

Du måste till exempel skapa känslighetsetiketten RESEARCH för att skydda e-post och dokument i forskningsteam. Du fastställer att:

- Forskare måste ha möjlighet att ändra dokument som har markerats med känslighetsetiketten RESEARCH.
- Medarbetare som inte är forskare bara ska ha möjlighet att visa dokument som har markerats med känslighetsetiketten RESEARCH. 

Det innebär att du måste skapa och hantera två ytterligare Microsoft 365-grupper:

- RESEARCH-ALL
- RESEARCH-VIEW

Dessa grupper och deras behörigheter blir en del av konfigurationen för känslighetsetiketten RESEARCH.

För känslighetsetiketter som konfigurerats med gruppbaserade behörigheter, måste du hantera medlemskap för dessa grupper.

### <a name="your-configuration-so-far"></a>Din konfiguration hittills

Här är en visuell sammanfattning av fasen för informationsskydd med nya element markerade.

![Din organisation efter informationsskyddsfasen](../media/deploy-foundation-infrastructure-non-enterprises/info-protect-config.png)
 
De nya och markerade elementen för informationsskydd inkluderar:
 
|||
|:------:|:-----|
| ![Känslighetsetiketter för de tre säkerhetsnivåerna](../media/deploy-foundation-infrastructure-non-enterprises/info-protect-labels.png) | Känslighetsetiketter för de tre säkerhetsnivåerna som användare kan använda för dokument och e-post. |
|||

Anpassade informationstyper och kvarhållningsetiketter visas inte.

## <a name="onboarding"></a>Introduktioner

Med din infrastruktur för Microsoft 365 för företag kan du enkelt introducera dina anställda.

### <a name="a-new-windows-10-enterprise-device"></a>En ny Windows 10 Enterprise-enhet

Innan du ger en anställd en ny Windows 10 Enterprise-enhet:

- För hybrididentitet

  Anslut enheten till AD DS-domänen, anslut enheten till Azure AD-klientorganisationen och registrera sedan enheten i Intune.

- För identitet endast för molnet

  Anslut enheten till Azure AD-klientorganisationen.

### <a name="existing-employee-with-an-ad-ds-user-account"></a>Befintlig anställd med ett AD DS-användarkonto

Som en del av den första introduktionen för din organisation vid användning av hybrididentitet, lägger du till AD DS-användarkontot i följande Azure AD-grupper:

- LICENSED
- Lämpliga AD DS- eller Azure AD-säkerhetsgrupper som är medlemmar i Azure AD-grupperna BASELINE, SENSITIVE och HIGHLY-REGULATED 
- Grupper av känslighetsetiketter (efter behov)

En befintlig anställd ska redan ha lagts till i lämplig arbetsgrupp, avdelning och regional AD DS-grupp.

Du kan lägga till ett användarkonto i flera Azure AD-grupper i administrationscentret för Microsoft 365. Från användarkontots egenskaper klickar du på **Hantera grupper > Lägg till medlemskap**.

Om du vill använda PowerShell kan du läsa den här [nedladdningsbara Excel-arbetsboken](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/deploy-foundation-infrastructure-non-enterprises/Group-License-Mgmt-PowerShell.xlsx), som genererar PowerShell-kommandon baserat på ett specifikt användarkonto och valda gruppnamn.

### <a name="new-employee-with-a-cloud-only-user-account"></a>Ny anställd med ett användarkonto för endast molnet

Som en del av den första introduktionen för din organisation vid användning av identitet för endast molnet, lägger du till det nya användarkontot i följande grupper:

- LICENSED
- Lämpliga Azure AD-säkerhetsgrupper som är medlemmar i Azure AD-grupperna BASELINE, SENSITIVE och HIGHLY-REGULATED
- Arbetsgrupp, avdelning och regionala grupper
- Grupper av känslighetsetiketter (efter behov)

### <a name="initial-sign-in-to-microsoft-365"></a>Första inloggning till Microsoft 365

För första gången som medarbetarna loggar in på Microsoft 365, instruerar du dem att:

1. Logga in på sina enheter med användarkontouppgifterna.
2. Logga in på Office 365-portalen med hjälp av en webbläsare på https://portal.office.com.
3. På **startfliken för Office 365** klickar du på **Installera Office** för att installera Microsoft 365-applikationer för företag på deras enhet.

## <a name="end-results"></a>Slutresultat

Här visas resultatet av att konfigurera den grundläggande infrastrukturen för Microsoft 365 för företag för din organisation, som inte är ett större företag.

### <a name="infrastructure-results"></a>Infrastrukturresultat

Efter utbyggnad och konfiguration av din Microsoft 365 för företag-infrastruktur bör du ha:

- En lokal Internetanslutning för vart och ett av dina kontor med tillräcklig bandbredd som tillhandahålls av en Internetleverantör som använder en regional lokal DNS-server.
- För hybrididentitet: Azure AD Connect som körs på en server som synkroniserar din lokala AD DS-domän med Azure AD-klientorganisationen.
- Dessa grupper:
  - LICENSED
  - COND-ACCESS-EXCLUDE
  - Lämpliga AD DS- eller Azure AD-säkerhetsgrupper som även är medlemmar i Azure AD-grupperna BASELINE, SENSITIVE och HIGHLY-REGULATED 
  - Arbetsgrupp, avdelning och regionala grupper
  - Grupper av känslighetsetiketter för Microsoft 365 (efter behov)
- Principer för villkorsstyrd åtkomst för Azure AD-inloggning som använder Azure AD-grupperna BASELINE, SENSITIVE, HIGHLY-REGULATED och COND-ACCESS-EXCLUDE.
- Principer för Intune-program och enhetsefterlevnad.
- Vanliga typer av känslig information (efter behov).
- Kvarhållningsetiketter (efter behov).
- Känslighetsetiketter (efter behov).

Här är en visuell sammanfattning av infrastrukturen om organisationen använder hybrididentitet, som inkluderar din AD DS-domän, en Azure AD Connect-server och synkroniserade AD DS-användare och -grupper.

![Sammanfattning av infrastrukturen om organisationen använder hybrididentitet](../media/deploy-foundation-infrastructure-non-enterprises/final-hybrid-config.png)
 
Här är en visuell sammanfattning av infrastrukturen om organisationen använder helt molnbaserad identitet.
 
![Sammanfattning av infrastrukturen om organisationen använder helt molnbaserad identitet](../media/deploy-foundation-infrastructure-non-enterprises/final-cloud-only-config.png)

### <a name="employee-results"></a>Resultat för personal

Efter introduktionen ska varje anställd ha följande:

- En fungerande lokal nätverkssökväg från sin enhet till Microsoft 365-molntjänsterna i respektive region.
- Ett användarkonto med följande gruppmedlemskap:
   - LICENSED
   - Lämpliga AD DS- eller Azure AD-säkerhetsgrupper, som även är medlemmar i Azure AD-grupperna BASELINE, SENSITIVE och HIGHLY-REGULATED för principer för villkorsstyrd åtkomst 
   - Lämplig arbetsgrupp, avdelning och regionala grupper
   - Grupper av känslighetsetiketter för Microsoft 365 (efter behov)
- En Windows 10 Enterprise-enhet som:
   - är ansluten till Azure AD-klientorganisationen (endast molnet) eller till både Azure AD-klientorganisationen och AD DS-domänen (hybrid).
   - uppdateras automatiskt med de senaste produkt- och säkerhetsförbättringarna för Windows 10 Enterprise.
   - har Microsoft 365-applikationer för företag installerat, som automatiskt uppdateras med de senaste produkt- och säkerhetsförbättringarna för Office-produkter.
   - är registrerad i Intune och omfattas av efterlevnads- och appskyddsprinciper för Intune-enheter.

## <a name="next-step"></a>Nästa steg

Distribuera dina [arbetsbelastningar](deploy-workloads.md) så att de drar nytta av funktioner och konfigurationen i din grundläggande infrastruktur för Microsoft 365 för företag.
