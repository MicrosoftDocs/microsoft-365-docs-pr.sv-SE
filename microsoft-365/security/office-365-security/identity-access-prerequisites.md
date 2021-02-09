---
title: Nödvändiga åtgärder för att implementera principer för identitets- och enhetsåtkomst – Microsoft 365 för | Microsoft Docs
description: I den här artikeln beskrivs förutsättningarna för att du ska kunna använda principer och konfigurationer för enhetsåtkomst.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
ms.date: 09/01/2020
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: e411eaa7874dee710cbb21dd02a4edd383003def
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142103"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Krav på att implementera principer för identitets- och enhetsåtkomst

I den här artikeln beskrivs vilka förutsättningar administratörer måste uppfylla för att använda rekommenderade principer för identitets- och enhetsåtkomst, och för att använda villkorsstyrd åtkomst. Dessutom beskrivs de rekommenderade standardinställningarna för att konfigurera klientplattformar så att du får bästa möjliga upplevelse med enkel inloggning (SSO).

## <a name="prerequisites"></a>Förutsättningar

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 abonnemang 1 och abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- Azure

Innan du använder de principer för identitets- och enhetsåtkomst som rekommenderas måste din organisation uppfylla kraven. Kraven är olika för de olika identitets- och autentiseringsmodellerna som visas:

- Endast molnet
- Hybrid med synkronisering av lösenordshashar (PHS)
- Hybrid med direktautentisering (PTA)
- Externa

I följande tabell visas information om nödvändiga funktioner och deras konfiguration som gäller för alla identitetsmodeller, om inget anges.

|Konfiguration|Undantag|
|---|:---:|
|[Konfigurera PHS.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)  Det måste vara aktiverat för att identifiera läckta autentiseringsuppgifter och agera utifrån dem för riskbaserad villkorsstyrd åtkomst. **Obs!** Detta krävs oavsett om organisationen använder federerad autentisering.|Endast molnet|
|[Aktivera sömlös enkel inloggning för att](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) automatiskt logga in användare när de är på sina organisationsenheter anslutna till organisationens nätverk.|Endast molnet och federerat|
|[Konfigurera namngivna nätverk.](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal) Azure AD Identity Protection samlar in och analyserar alla tillgängliga sessionsdata för att generera en risknivå. Vi rekommenderar att du anger organisationens offentliga IP-intervall för nätverket i konfigurationen av Azure AD-namngivna nätverk. Trafiken som kommer från dessa intervall får ett lägre riskresultat och trafiken utanför organisationsmiljön får högre riskpoäng.||
|[Registrera alla användare för självbetjäning för återställning av lösenord (SSPR) och multifaktorautentisering (MFA).](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged) Vi rekommenderar att du registrerar användare för Azure AD Multi-Factor Authentication i förväg. Azure AD Identity Protection använder Azure AD Multi-Factor Authentication för att utföra ytterligare säkerhetsverifiering. För att inloggningen ska bli så bra som möjligt rekommenderar vi dessutom att användarna installerar [appen Microsoft Authenticator](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) och appen Microsoft Company Portal på sina enheter. De kan installeras från appbutiken för varje plattform.||
|[Aktivera automatisk enhetsregistrering för domänaktivade Windows-datorer.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup) Villkorsstyrd åtkomst ser till att enheter som ansluter till appar är domänanslutna eller kompatibla. För att stödja detta på Windows-datorer måste enheten vara registrerad med Azure AD.  I den här artikeln beskrivs hur du konfigurerar automatisk enhetsregistrering.|Endast molnet|
|**Förbered ditt supportteam.** Ha en plan för användare som inte kan slutföra MFA. Det kan lägga till dem i en undantagsgrupp för principen eller registrera ny MFA-information för dem. Innan du gör någon av dessa säkerhetskänsliga ändringar måste du se till att den faktiska användaren gör begäran. Att kräva att användarnas chefer hjälper till med godkännande är ett effektivt steg.||
|[Konfigurera lösenords tillbakaskrivning till lokal AD.](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) Med lösenords tillbakaskrivning kan Azure AD kräva att användarna ändrar sina lokala lösenord när en högriskkontokompromettering identifieras. Du kan aktivera den här funktionen med Azure AD Connect på ett av två sätt: antingen aktivera **Tillbakaskrivning** av lösenord på skärmen med valfria funktioner i installationsguiden för Azure AD Connect eller aktivera den via Windows PowerShell.|Endast molnet|
|[Konfigurera lösenordsskydd i Azure AD.](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) Azure AD-lösenordsskydd upptäcker och blockerar kända svaga lösenord och deras varianter och kan också blockera ytterligare svaga termer som är specifika för din organisation. Standard globala förbjudna lösenordslistor tillämpas automatiskt på alla användare i en Azure AD-klient. Du kan definiera ytterligare poster i en anpassad förbjuden lösenordslista. När användare ändrar eller återställer sina lösenord kontrolleras dessa förbjudna lösenordslistor för att använda starka lösenord.||
|[Aktivera Azure Active Directory-identitetsskydd.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection) Med Azure AD Identity Protection kan du upptäcka potentiella säkerhetsproblem som påverkar organisationens identiteter och konfigurera en automatiserad åtgärdsprincip till låg, medelstor och hög inloggningsrisk och användarrisk.||
|**Aktivera modern autentisering** för [Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) och Skype för företag [– Online.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) Modern autentisering krävs för att använda MFA. Modern autentisering är aktiverad som standard för Office 2016- och 2019-klienter, SharePoint och OneDrive för företag.||
|

## <a name="recommended-client-configurations"></a>Rekommenderade klientkonfigurationer

I det här avsnittet beskrivs standardkonfigurationerna för plattformsklienter som vi rekommenderar för att ge användarna den bästa SSO-upplevelsen samt de tekniska förutsättningarna för villkorsstyrd åtkomst.

### <a name="windows-devices"></a>Windows-enheter

Vi rekommenderar Windows 10 (version 2004 eller senare), eftersom Azure är utformat för att tillhandahålla så smidig SSO-upplevelse som möjligt för både lokal miljö och Azure AD. Arbets- eller skolenheter bör konfigureras för att anslutas direkt till Azure AD, eller om organisationen använder lokal AD-domänkoppling, bör dessa enheter konfigureras för att automatiskt och utan att registreras i [Azure AD.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)

För BYOD Windows-enheter kan användare använda Lägg **till arbets- eller skolkonto.** Observera att användare av Google Chrome på Windows [](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) 10-enheter måste installera ett tillägg för att få samma smidiga inloggning som Microsoft Edge-användare. Om din organisation har domän anslutna Windows 8- eller 8.1-enheter kan du installera Microsoft Workplace Join för datorer som inte är Windows 10. [Ladda ned paketet för att](https://www.microsoft.com/download/details.aspx?id=53554) registrera enheterna i Azure AD.

### <a name="ios-devices"></a>iOS-enheter

Vi rekommenderar att du installerar [appen Microsoft Authenticator på](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) användarnas enheter innan du distribuerar villkorsstyrda åtkomst- eller MFA-principer. Som minst bör appen installeras när användare uppmanas att registrera sin enhet med Azure AD genom att lägga till ett arbets- eller skolkonto, eller när de installerar Intune-företagsportalappen för att registrera sin enhet i hanteringen. Det beror på den konfigurerade villkorsstyrda åtkomstprincipen.

### <a name="android-devices"></a>Android-enheter

Vi rekommenderar att användarna installerar [appen Intune Company Portal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) och Microsoft [Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) innan villkorsstyrda åtkomstprinciper distribueras eller när de krävs under vissa autentiseringsförsök. Efter appinstallationen kan användare uppmanas att registrera sig i Azure AD eller registrera sin enhet med Intune. Det här beror på den konfigurerade villkorsstyrda åtkomstprincipen.

Vi rekommenderar även att enheter som ägs av organisationen standardiserades på OEM-datorer och versioner som stöder Android för arbete eller Samsung Knox för att tillåta e-postkonton, att de hanteras och skyddas av Intune MDM-policy.

### <a name="recommended-email-clients"></a>Rekommenderade e-postklienter

Följande e-postklienter har stöd för modern autentisering och villkorlig åtkomst.

|Plattform|Klient|Version/anteckningar|
|---|---|---|
|**Windows**|Outlook|2019, 2016, 2013 <p> [Aktivera modern autentisering](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication) <p> [Uppdateringar som krävs](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook för iOS|[Senaste](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook för Android|[Senaste](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019 och 2016|
|**Linux**|Stöds inte||
|

### <a name="recommended-client-platforms-when-securing-documents"></a>Rekommenderade klientplattformar när du skyddar dokument

Följande klienter rekommenderas när en princip för säkra dokument har tillämpats.

|Plattform|Word/Excel/PowerPoint|OneNote|OneDrive-app|SharePoint-app|[OneDrive-synkroniseringsklient](https://docs.microsoft.com/onedrive/enable-conditional-access)|
|---|---|---|---|---|---|
|Windows 8.1|Stöds|Stöds|EJ TILLÄMPLIGT|EJ TILLÄMPLIGT|Stöds|
|Windows 10|Stöds|Stöds|EJ TILLÄMPLIGT|EJ TILLÄMPLIGT|Stöds|
|Android|Stöds|Stöds|Stöds|Stöds|Saknas|
|iOS|Stöds|Stöds|Stöds|Stöds|Saknas|
|macOS|Stöds|Stöds|EJ TILLÄMPLIGT|EJ TILLÄMPLIGT|Stöds inte|
|Linux|Stöds inte|Stöds inte|Stöds inte|Stöds inte|Stöds inte|
|

### <a name="microsoft-365-client-support"></a>Microsoft 365-klientstöd

Mer information om klientsupport i Microsoft 365 finns i följande artiklar:

- [Microsoft 365 Client App-support – villkorsstyrd åtkomst](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Stöd för Microsoft 365-klientappen – multifaktorautentisering](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md)

## <a name="protecting-administrator-accounts"></a>Skydda administratörskonton

För Microsoft 365 E3 eller E5 eller med separata Azure AD Premium P1- eller P2-licenser kan du kräva MFA för administratörskonton med en manuellt skapad villkorsstyrd åtkomstprincip. Mer [information finns i Villkorsstyrd åtkomst: Kräv MFA](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) för administratörer.

För utgåvor av Microsoft 365 eller Office 365 som inte stöder [villkorsstyrd](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) åtkomst kan du aktivera säkerhet som är standard för att kräva MFA för alla konton.

Här är ytterligare rekommendationer:

- Använd [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started) för att minska antalet beständiga administrativa konton.
- [Använd hantering av behörighetsbehörighet](../../compliance/privileged-access-management-overview.md) för att skydda organisationen från överträdelser som kan använda befintliga administratörskonton med stående åtkomst till känsliga data eller åtkomst till viktiga konfigurationsinställningar.
- Skapa och använd separata konton som endast har [tilldelats Microsoft 365-administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) *för administration.* Administratörer bör ha ett eget användarkonto för vanlig icke-administrativ användning och bara använda ett administratörskonto när det behövs för att slutföra en uppgift som är kopplad till deras roll eller jobbfunktion.
- Följ [de bästa metoderna](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) för att skydda behöriga konton i Azure AD.

## <a name="next-step"></a>Nästa steg

[![Steg 2: Konfigurera principer för gemensam identitet och åtkomst för villkorsstyrd åtkomst](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[Konfigurera vanliga principer för identitets- och enhetsåtkomst](identity-access-policies.md)
