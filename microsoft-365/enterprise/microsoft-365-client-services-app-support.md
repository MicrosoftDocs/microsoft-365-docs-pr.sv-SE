---
title: Microsoft 365 klient- och tjänstappsupport
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: I den här artikeln hittar du information Microsoft 365 om stöd för klient- och tjänstprogram.
ms.openlocfilehash: e380efffc1bf29cbd4d3a77d32e4d1f8b2994da3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905014"
---
# <a name="microsoft-365-client-and-services-app-support"></a>Microsoft 365 klient- och tjänstappsupport

Microsoft har stöd för ett brett utbud av säkerhets-, autentiserings- och efterlevnadsfunktioner för att skydda kunddata och gör att IT-administratörer kan anpassa principer i administrationscentret för Microsoft 365 för sina användare. Följande funktioner är bara en del av de många företagsfunktioner som du kan konfigurera beroende på din Microsoft 365 prenumeration.

## <a name="client-and-service-support"></a>Klient- och tjänstsupport

### <a name="continuous-access-evaluation-preview"></a>Utvärdering av kontinuerlig åtkomst (förhandsversion)

Kontinuerlig utvärdering av åtkomst implementeras genom att tjänster som Exchange Online, SharePoint Online och Teams kan prenumerera på kritiska händelser i Azure Active Directory så att dessa händelser kan utvärderas och tillämpas nära i realtid. Utvärdering av kritiska händelser förlitar sig inte på villkorsstyrda åtkomstprinciper, vilket är tillgängligt i alla klientorganisationen.

Följande händelser utvärderas för närvarande:

- Ett användarkonto tas bort eller inaktiveras
- Lösenordet för en användare ändras eller återställs
- Multifaktorautentisering är aktiverad för användaren
- Administratören återkallar uttryckligen alla uppdateringstoken för en användare
- Förhöjd användarrisk upptäckt av Azure AD Identity Protection

Mer information om kontinuerlig åtkomstutvärdering för support av klient- och tjänsterprogram finns i [Kontinuerlig åtkomstutvärdering (förhandsversion).](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)

## <a name="client-support"></a>Klientsupport

### <a name="certificate-based-authentication"></a>Certifikatbaserad autentisering

Certifikatbaserad autentisering (CBA) är användningen av ett digitalt certifikat för att identifiera en användare, dator eller enhet innan åtkomst till en resurs, ett nätverk, ett program eller en tjänst beviljas. Inom användarautentisering distribueras den ofta i samverkan med traditionella metoder som användarnamn och lösenord.

Vissa traditionella lösningar fungerar bara för användare, till exempel biometrisker och engångslösenord (OTP). Med certifikatbaserad autentisering kan samma lösning användas för alla slutpunkter. användare, enheter och den växande Internet of Things (IoT).

Mer information om certifikatbaserad autentisering för stöd för klient- och tjänstprogram finns i Microsoft 365 [klientappens support: Certifikatbaserad autentisering.](microsoft-365-client-support-certificate-based-authentication.md)

### <a name="conditional-access"></a>Villkorsstyrd åtkomst

Villkorlig åtkomst är det verktyg som används av Azure Active Directory för att föra samman signaler, fatta beslut och genomdriva principer för organisationsåtkomst. Villkorsstyrd åtkomst är kärnan i den nya identitetsdrivna kontrollmodellen.

Villkorsstyrda åtkomstprinciper är instruktioner för att bevilja åtkomst till resurser. Om en användare vill komma åt en resurs måste användaren slutföra en åtgärd. Vanliga signaler som villkorsstyrd åtkomst kan använda när man ska fatta ett beslut om principåtkomst är:

- Användar- eller gruppmedlemskap
- IP-platsinformation
- Enhetsinformation
- Programinformation
- Identifiering av risker i realtid och beräknad
- Microsoft Cloud App Security (MCAS)

När de här åtkomstbesluten ska fattas kan principerna vidta olika åtgärder:

- Principen kan blockera åtkomst: Den här konfigurationen är den mest restriktiva åtgärden och hindrar användaren från att komma åt resursen.
- Principen kan bevilja åtkomst: Den här konfigurationen är ett mindre restriktivt beslut och kan fortfarande kräva ett eller flera av följande alternativ:

    - Multifaktorautentisering
    - Den enhet som ska markeras som kompatibel
    - Enheten är Azure AD-hybrid ansluten
    - En godkänd klientapp
    - Princip för programskydd konfigurerad (förhandsversion)

Mer information om villkorsstyrd åtkomst för stöd för klient- och tjänsterprogram finns i:

- [Microsoft 365 Stöd för klientprogram: Enhetsbaserad villkorsstyrd åtkomst](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a>Hantering av mobilprogram

Användare får ofta åtkomst till både organisationsdokument och personliga dokument, e-post och data från samma mobila enhet. Dessa enheter ägs ofta personligen och bör konfigureras för att skydda både organisationsdata och användarens personliga integritet.

När en användare får åtkomst till organisationsdata måste organisationen vara säker på att organisationsprinciper, till exempel konfigurationsprinciper och skyddsprinciper, tillämpas för att skydda organisationsdata på enheten. Dessutom bör användarens personliga innehåll på enheten ligga kvar utanför organisationens kontroll.

För organisations hanterat innehåll kan du använda principer för programhantering för att styra hur data kan nås, delas och användas med hjälp av Microsoft Intune. Följande åtgärder stöds till exempel:

- Fjärr-rensning av innehållet i den hanterade organisationen (kallas även organisationsdata)
- Förhindra att organisationsinnehåll klistras in på platser utanför organisationen
- Kräv PIN-kod för åtkomst till organisationsinnehåll
- Förhindra att hanterade appar körs på jailbroken eller rotade enheter
- Förhindra att organisationsinnehåll sparas till leverantörer av molnlagring som inte godkänts
- Förhindra att innehåll som inte godkänts överförs till hanterade program
- Tillåt åtkomst till organisationsinnehåll endast efter att principer har tillämpats
- Leverera programkonfiguration för att hantera programmets beteende och inställningar
- Begränsa det hanterade programmet till en definierad identitet genom att inaktivera funktioner för flera identiteter eller personlig användning

Mer information om hantering av mobilprogram med Microsoft Intune finns i [Vad är Microsoft Intune för programhantering?](/mem/intune/apps/app-management)

### <a name="multi-factor-authentication"></a>Multifaktorautentisering

[Multi-Factor Authentication (MFA) är en metod för datoråtkomstkontroll där en användare beviljas åtkomst endast efter att ha presenterat flera olika bevis för en autentiseringsmekanism. Den här metoden använder vanligtvis minst två av följande kategorier:

- Kunskap (något de känner till)
- Innehavarn (något de har)
- Inherence (något de är)

Mer information om multifaktorautentisering för stöd för klient- och tjänsterprogram finns Microsoft 365 [support för klientappen: Multifaktorautentisering.](microsoft-365-client-support-multi-factor-authentication.md)

### <a name="single-sign-on"></a>Enkel inloggning

Enkel inloggning (SSO) ger säkerhet och enkelhet när användarna loggar in i program i Azure Active Directory. Med enkel inloggning loggar användarna in en gång med ett konto för att få åtkomst till lokala ad ds-enheter (Active Directory Domain Services), saaS-program (programvara som en tjänst) och webbprogram i organisationen.

Mer information om enkel inloggning för support för klient- och tjänster finns i Microsoft 365 [klientappens support: Enkel inloggning.](microsoft-365-client-support-single-sign-on.md)

## <a name="services-support"></a>Support för tjänster

### <a name="modern-authentication"></a>Modern autentisering

Modern autentisering gör det möjligt för kunder att autentisera sig mot Office 365 och för innehavaradministratörer att tillämpa specifika autentiseringskrav under hela Office 365, till exempel:

- Stöd för multifaktorautentisering för administrativ interaktion med innehavare och tjänster och slutanvändarens interaktion med program och deras data
- Villkorlig åtkomst
- SAML-baserad inloggning från tredjepartsidentitetsleverantör
- Smartkortslogg på persondatorer
- Certifikatbaserad autentisering på mobila enheter
- Det krävs inte längre överföring av autentiseringsuppgifter över grundläggande autentisering.

Mer information om stöd för moderna autentiseringstjänster finns i [Autentisering kontra auktorisering](/azure/active-directory/develop/authentication-vs-authorization).

### <a name="azure-active-directory-conditional-access"></a>Villkorsstyrd åtkomst i Azure Active Directory

Azure Active Directory (Azure AD) med villkorsstyrda åtkomstregler kan kunder kontrollera åtkomsten till onlinetjänster, baserat på attribut, till exempel enhetsefterlevnad eller nätverksplats. Följande lösningar kan användas:

- Azure AD multifaktorautentiseringsbaserad villkorsstyrd åtkomst
- Azure AD platsbaserad villkorsstyrd åtkomst
- Enhetsbaserad villkorsstyrd åtkomst i Azure AD

Azure AD Regler för villkorsstyrd åtkomst tillämpas per program och är tillgängliga för kunder att styra åtkomsten baserat på olika villkor. Med [Mobile Device Management (MDM) eller Intune](/mem/intune/fundamentals/what-is-device-management)måste kunderna kunna begränsa åtkomsten till Microsoft 365 till endast de användare som använder en organisationsenhet eller som har registrerat sin personliga enhet för hantering. Kunder kan till exempel konfigurera regler för villkorsstyrd åtkomst för att framtvinga kontroller som:

- Tillåt endast åtkomst från enheter som är domän anslutna eller domänkompatibla
- Framtvinga multifaktorautentisering för all åtkomst Exchange Online tjänster

Mer information om villkorsstyrd Azure Active Directory finns i [Vad är villkorsstyrd åtkomst?](/azure/active-directory/conditional-access/overview)

### <a name="tls-12-support"></a>Stöd för TLS 1.2

För att våra kunder ska få bästa möjliga kryptering planerar Microsoft att upphöra med stödet för TLS-versionerna 1.0 och 1.1 i Office 365 och Office 365 GCC.

Vi förstår att din data är viktig, och vi är måna om transparensen om ändringar som kan påverka din användning av tjänsten TLS. Vi rekommenderar att alla kombinationer av klientserver och webbläsarserver använder TLS 1.2 (eller en senare version) för att upprätthålla anslutningen till Office 365 tjänster. Du kan behöva uppdatera vissa kombinationer av klient- och webbläsarservrar.

Mer information om support och tjänster med TLS 1.2 finns i Förbereda [för TLS 1.2 i Office 365 och Office 365 GCC.](../compliance/prepare-tls-1.2-in-office-365.md)