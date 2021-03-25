---
title: Nödvändiga åtgärder för att implementera principer för identitets- och enhetsåtkomst – Microsoft 365 för | Microsoft Docs
description: I den här artikeln beskrivs förutsättningarna för att uppfylla för att använda principer och konfigurationer för åtkomst till enheter.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
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
ms.openlocfilehash: 5bf879bed31f4a8ddea868f28084148c3ec8afae
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207019"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Nödvändiga åtgärder för att implementera principer för identitets- och enhetsåtkomst

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- Azure

I den här artikeln beskrivs vilka förutsättningar administratörer måste uppfylla för att kunna använda rekommenderade principer för identitet och enhetsåtkomst, och för att använda villkorsstyrd åtkomst. Dessutom diskuteras de rekommenderade standarderna för konfiguration av klientplattformar för bästa möjliga enkel inloggning (SSO).

## <a name="prerequisites"></a>Krav

Innan du använder de identitets- och enhetsåtkomstprinciper som rekommenderas måste organisationen uppfylla kraven. Kraven är olika för de olika identitets- och autentiseringsmodellerna som anges:

- Endast molnet
- Hybrid med synkronisering av lösenordshashar (PHS)
- Hybrid med direktautentisering (PTA)
- Extern

I följande tabell finns information om de nödvändiga funktionerna och deras konfiguration som gäller för alla identitetsmodeller, om inget annat anges.

|Konfiguration|Undantag|
|---|:---:|
|[Konfigurera PHS](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization).  Detta måste vara aktiverat för att identifiera läckta autentiseringsuppgifter och agera på dem för riskbaserad villkorsstyrd åtkomst. **Obs!** Detta är obligatoriskt oavsett om organisationen använder federerad autentisering.|Endast molnet|
|[Aktivera sömlös enkel inloggning för att](/azure/active-directory/connect/active-directory-aadconnect-sso) automatiskt logga in användare när de använder sina organisationsenheter som är anslutna till organisationens nätverk.|Endast molnet och externa|
|[Konfigurera namngivna platser](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations). Azure AD Identity Protection samlar in och analyserar alla tillgängliga sessionsdata för att skapa en risknivå. Vi rekommenderar att du anger organisationens offentliga IP-intervall för nätverket i konfigurationen av namngivna azure AD-platser. Trafik från dessa intervall ges lägre riskresultat och trafik utanför organisationsmiljön får högre risknivå.||
|[Registrera alla användare för självbetjäning för återställning av lösenord (SSPR) och multifaktorautentisering (MFA).](/azure/active-directory/authentication/concept-registration-mfa-sspr-converged) Vi rekommenderar att du registrerar användare för Azure AD Multi-Factor Authentication i förväg. Azure AD Identity Protection använder Azure AD Multi-Factor Authentication för att utföra ytterligare säkerhetsverifiering. För bästa inloggningsupplevelse rekommenderar vi dessutom att användarna installerar [appen Microsoft Authenticator](/azure/active-directory/user-help/microsoft-authenticator-app-how-to) och appen Microsoft Company Portal på sina enheter. De kan installeras från appbutiken för varje plattform.||
|[Aktivera automatisk enhetsregistrering för domänbaserade Windows-datorer.](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup) Villkorsstyrd åtkomst ser till att enheter som ansluter till appar är domänanslutna eller kompatibla. Enheten måste vara registrerad med Azure AD för att stödja detta på Windows-datorer.  I den här artikeln beskrivs hur du konfigurerar automatisk enhetsregistrering.|Endast molnet|
|**Förbered ditt supportteam**. Ha en plan för användare som inte kan slutföra MFA. Det kan vara att lägga till dem i en princip undantagsgrupp eller registrera ny MFA-information för dem. Innan du gör någon av dessa säkerhetskänsliga ändringar måste du se till att den faktiska användaren gör begäran. Att kräva att användarnas chefer hjälper till med godkännandet är ett effektivt steg.||
|[Konfigurera tillbakaskrivning av lösenord till lokal AD.](/azure/active-directory/active-directory-passwords-getting-started) Med tillbakaskrivning av lösenord kan Azure AD kräva att användarna ändrar sina lokala lösenord när en högriskkontokompromettering upptäcks. Du kan aktivera den här funktionen med Azure AD  Connect på ett av två sätt: antingen aktivera Tillbakaskrivning av lösenord på skärmen med valfria funktioner i installationsguiden för Azure AD Connect eller aktivera den via Windows PowerShell.|Endast molnet|
|[Konfigurera Lösenordsskydd i Azure AD.](/azure/active-directory/authentication/concept-password-ban-bad) Azure AD-lösenordsskydd upptäcker och blockerar kända svaga lösenord och deras varianter och kan också blockera ytterligare svaga termer som är specifika för din organisation. Standard globala förbjudna lösenordslistor tillämpas automatiskt på alla användare i en Azure AD-klient. Du kan definiera ytterligare poster i en anpassad förbjuden lösenordslista. När användare ändrar eller återställer sina lösenord kontrolleras dessa förbjudna lösenordslistor för att använda starka lösenord.||
|[Aktivera Azure Active Directory-identitetsskydd](/azure/active-directory/identity-protection/overview-identity-protection). Med Azure AD Identity Protection kan du upptäcka potentiella säkerhetsproblem som påverkar organisationens identiteter och konfigurera en automatiserad åtgärdsprincip för låg, medium och hög inloggningsrisk och användarrisk.||
|**Aktivera modern autentisering** för [Exchange Online och](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) Skype för företag – [Online.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) Modern autentisering krävs för att använda MFA. Modern autentisering är aktiverad som standard för Office 2016- och 2019-klienter, SharePoint och OneDrive för företag.||
|

## <a name="recommended-client-configurations"></a>Rekommenderade klientkonfigurationer

I det här avsnittet beskrivs standardkonfigurationerna för plattformsklienter som vi rekommenderar för att ge bästa möjliga SSO-upplevelse för användarna samt de tekniska förutsättningarna för villkorsstyrd åtkomst.

### <a name="windows-devices"></a>Windows-enheter

Vi rekommenderar Windows 10 (version 2004 eller senare), eftersom Azure är utformat för att tillhandahålla så smidig SSO-upplevelse som möjligt för både lokal och Azure AD. Arbets- eller skolenheter bör konfigureras för att ansluta till Azure AD direkt, eller om organisationen använder en lokal AD-domänkoppling bör de enheterna konfigureras för att automatiskt och utan att registreras i tyst läge i [Azure AD.](/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup)

För BYOD Windows-enheter kan användarna använda Lägg **till arbets- eller skolkonto.** Observera att användare av Google Chrome på Windows [](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) 10-enheter måste installera ett tillägg för att få samma smidiga inloggning som Microsoft Edge-användare. Om din organisation har domänkopplingar till Windows 8- eller 8.1-enheter kan du även installera Microsoft Workplace Join för icke-Windows 10-datorer. [Ladda ned paketet för att](https://www.microsoft.com/download/details.aspx?id=53554) registrera enheterna i Azure AD.

### <a name="ios-devices"></a>iOS-enheter

Vi rekommenderar att du installerar [appen Microsoft Authenticator på](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) användarnas enheter innan du distribuerar villkorsstyrd åtkomst eller MFA-principer. Som ett minimum bör appen installeras när användare uppmanas att registrera sin enhet med Azure AD genom att lägga till ett arbets- eller skolkonto, eller när de installerar appen Intune-företagsportal för att registrera sin enhet i hantering. Det här beror på den konfigurerade villkorsstyrda åtkomstprincipen.

### <a name="android-devices"></a>Android-enheter

Vi rekommenderar att användarna installerar [appen Intune-företagsportal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) och [Microsoft Authenticator-appen](/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) innan villkorsstyrda åtkomstprinciper distribueras eller när det krävs under vissa autentiseringsförsök. Efter appinstallationen kan användarna uppmanas att registrera sig i Azure AD eller registrera sin enhet med Intune. Det här beror på den konfigurerade villkorsstyrda åtkomstprincipen.

Vi rekommenderar även att enheter som ägs av organisationen standardiseras på OEMM och versioner som stöder Android för arbete eller Samsung Knox för att tillåta e-postkonton, att de hanteras och skyddas av Intune MDM-policy.

### <a name="recommended-email-clients"></a>Rekommenderade e-postklienter

Följande e-postklienter har stöd för modern autentisering och villkorlig åtkomst.

|Plattform|Klient|Version/Anteckningar|
|---|---|---|
|**Windows**|Outlook|2019, 2016, 2013 <p> [Aktivera modern autentisering](../../admin/security-and-compliance/enable-modern-authentication.md) <p> [Nödvändiga uppdateringar](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook för iOS|[Senaste](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook för Android|[Senaste](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2019 och 2016|
|**Linux**|Stöds inte||
|

### <a name="recommended-client-platforms-when-securing-documents"></a>Rekommenderade klientplattformar när du skyddar dokument

Följande klienter rekommenderas när en princip för säkra dokument har tillämpats.

|Plattform|Word/Excel/PowerPoint|OneNote|OneDrive-appen|SharePoint-app|[OneDrive-synkroniseringsklient](/onedrive/enable-conditional-access)|
|---|---|---|---|---|---|
|Windows 8.1|Stöds|Stöds|EJ TILLÄMPLIGT|EJ TILLÄMPLIGT|Stöds|
|Windows 10|Stöds|Stöds|EJ TILLÄMPLIGT|EJ TILLÄMPLIGT|Stöds|
|Android|Stöds|Stöds|Stöds|Stöds|Uppgift saknas|
|iOS|Stöds|Stöds|Stöds|Stöds|Uppgift saknas|
|macOS|Stöds|Stöds|EJ TILLÄMPLIGT|EJ TILLÄMPLIGT|Stöds inte|
|Linux|Stöds inte|Stöds inte|Stöds inte|Stöds inte|Stöds inte|
|

### <a name="microsoft-365-client-support"></a>Microsoft 365-klientsupport

Mer information om klientsupport i Microsoft 365 finns i följande artiklar:

- [Microsoft 365 Client App-support – villkorsstyrd åtkomst](../../enterprise/microsoft-365-client-support-conditional-access.md)
- [Support för Microsoft 365-klientappen – multifaktorautentisering](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md)

## <a name="protecting-administrator-accounts"></a>Skydda administratörskonton

För Microsoft 365 E3 eller E5 eller med separata Azure AD Premium P1- eller P2-licenser kan du kräva MFA för administratörskonton med en manuellt skapad princip för villkorsstyrd åtkomst. Mer [information finns i Villkorsstyrd åtkomst: Kräv MFA](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) för administratörer.

För versioner av Microsoft 365 eller Office 365 som inte stöder [villkorsstyrd](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) åtkomst kan du aktivera säkerhetsinställningar så att MFA krävs för alla konton.

Här är några ytterligare rekommendationer:

- Använd [Azure AD Privileged Identity Management](/azure/active-directory/privileged-identity-management/pim-getting-started) för att minska antalet beständiga administrativa konton.
- [Använd hantering av privilegierad](../../compliance/privileged-access-management-overview.md) åtkomst för att skydda organisationen från överträdelser som kan använda befintliga administratörskonton med stående åtkomst till känsliga data eller åtkomst till viktiga konfigurationsinställningar.
- Skapa och använd separata konton som endast tilldelas [Microsoft 365-administratörsroller](../../admin/add-users/about-admin-roles.md) *för administration.* Administratörer bör ha sina egna användarkonton för normal icke-administrativ användning och bara använda ett administrativt konto när det behövs för att slutföra en uppgift som hör till deras roll eller befattning.
- Följ [de bästa metoderna](/azure/active-directory/admin-roles-best-practices) för att skydda behöriga konton i Azure AD.

## <a name="next-step"></a>Nästa steg

[![Steg 2: Konfigurera gemensamma principer för identitet och åtkomst för villkorsstyrd åtkomst](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-2.png)](identity-access-policies.md)

[Konfigurera gemensamma principer för identitet och enhetsåtkomst](identity-access-policies.md)