---
title: Förutsättningsarbeten för att implementera principer för identitets- och enhetsåtkomst – Microsoft 365 Enterprise | Microsoft-dokument
description: I artikeln beskrivs principerna för Microsofts rekommendationer om hur du tillämpar principer och konfigurationer för identitets- och enhetsåtkomst.
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: bfbb0481670b2f957bf240c261fcbafab96717b9
ms.sourcegitcommit: 98782ee4497d72232462c51a3071fae313282980
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44222595"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Förutsättningsarbete för att implementera principer för identitets- och enhetsåtkomst

I den här artikeln beskrivs förutsättningar som måste implementeras innan du kan distribuera de rekommenderade principerna för identitet och enhetsåtkomst. I den här artikeln beskrivs också standardplattformsklientkonfigurationerna som vi rekommenderar för att ge den bästa SSO-upplevelsen till dina användare, samt de tekniska förutsättningarna för villkorlig åtkomst.


## <a name="prerequisites"></a>Förutsättningar

Innan du implementerar de rekommenderade principerna för identitet och enhetsåtkomst finns det flera förutsättningar som din organisation måste uppfylla. I följande tabell beskrivs de förutsättningar som gäller för din miljö. 


| Konfiguration | Endast molnet | Active Directory med synkronisering av lösenordshÃ¤n |  Direktautentisering |  Federation med AD FS |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [Konfigurera synkronisering av lösenord hash](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Detta måste vara aktiverat för att identifiera läckta autentiseringsuppgifter och agera på dem för riskbaserad villkorlig åtkomst. **Anm.:** Detta krävs oavsett om din organisation använder hanterad autentisering, till exempel direktautentisering (PTA) eller federerad autentisering. |    | Ja | Ja | Ja |
| [Aktivera sömlös enkel inloggning](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) för att automatiskt logga in användare när de är på sina företagsenheter som är anslutna till företagets nätverk. |  | Ja | Ja |  |
| [Konfigurera namngivna nätverk](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD Identity Protection samlar in och analyserar alla tillgängliga sessionsdata för att generera en riskpoäng. Vi rekommenderar att du anger organisationens offentliga IP-intervall för nätverket i Azure AD namngivna nätverkskonfigurationen. Trafiken som kommer från dessa områden får en minskad riskpoäng och trafiken utanför företagsmiljön får en högre riskpoäng. | Ja  | Ja | Ja | Ja |
|[Registrera alla användare för återställning av lösenord för självbetjäning (SSPR) och MFA (Multifaktor authentication).](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged) Vi rekommenderar att du registrerar användare för Azure MFA i förväg. Azure AD Identity Protection använder Azure MFA för att utföra ytterligare säkerhetsverifiering. Dessutom rekommenderar vi användare att installera [Microsoft Authenticator-appen](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) och Microsoft Company Portal-appen på sina enheter för bästa inloggningsupplevelse. Dessa kan installeras från App Store för varje plattform. | Ja | Ja | Ja | Ja |
| [Aktivera automatisk enhetsregistrering av domänanslutna Windows-datorer](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). Villkorlig åtkomst kontrollerar att enheter som ansluter till appar är domänanslutna eller kompatibla. För att stödja detta på Windows-datorer måste enheten vara registrerad med Azure AD.  I den här artikeln beskrivs hur du konfigurerar automatisk enhetsregistrering. |   | Ja |  Ja |  Ja |
| **Förbered ditt supportteam.** Ha en plan för användare som inte kan slutföra MFA. Detta kan vara att lägga till dem i en grupp för undantag av principen eller registrera ny MFA-information för dem. Innan du gör någon av dessa säkerhetskänsliga ändringar måste du se till att den faktiska användaren gör begäran. Att kräva att användarnas chefer hjälper till med godkännandet är ett effektivt steg. | Ja | Ja | Ja | Ja |  
| [Konfigurera tillbakaskrivning av lösenord till lokal AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). Återställning av lösenord gör att Azure AD kan kräva att användare ändrar sina lokala lösenord när en högriskkontokompromiss identifieras. Du kan aktivera den här funktionen med Azure AD Connect på ett av två sätt: aktivera antingen återställning av **lösenord** i skärmen Valfria funktioner i installationsguiden för Azure AD Connect eller aktivera den via Windows PowerShell. |   | Ja | Ja | Ja |
| [Aktivera Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/enable). Med Azure AD Identity Protection kan du identifiera potentiella sårbarheter som påverkar organisationens identiteter och konfigurera en automatisk reparationsprincip till låg, medelstor och hög inloggningsrisk och användarrisk.  | Ja | Ja | Ja | Ja |
| **Aktivera modern autentisering** för [Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) och för [Skype för företag – Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). Modern autentisering är en förutsättning för att använda MFA (Multifaktorautentisering). Modern autentisering är aktiverad som standard för Office 2016-klienter, SharePoint Online och OneDrive för företag. | Ja | Ja | Ja | Ja |
||||||



## <a name="recommended-client-configurations"></a>Rekommenderade klientkonfigurationer
I det här avsnittet beskrivs standardkonfigurationerna för plattformsklient som vi rekommenderar för att ge den bästa SSO-upplevelsen till användarna, samt de tekniska förutsättningarna för villkorlig åtkomst.

### <a name="windows-devices"></a>Windows-enheter
Vi rekommenderar Windows 10 (version 1703 eller senare), eftersom Azure är utformat för att ge den smidigaste SSO-upplevelsen som är möjlig för både lokalt och Azure AD. Arbets- eller skolutgivna enheter bör konfigureras för att ansluta till Azure AD direkt eller om organisationen använder lokal AD-domänkoppling, bör dessa enheter [konfigureras för att automatiskt och tyst registrera sig hos Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

För BYOD Windows-enheter kan användare använda **Lägg till arbets- eller skolkonto**. Observera att Chrome-webbläsaranvändare på Windows 10 måste [installera ett tillägg](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) för att få samma smidiga inloggningsupplevelse som Edge/IE-användare. Om din organisation har domänanslutna Windows 7-enheter kan du installera Microsoft Workplace Join för datorer som inte är Windows [10-datorer Hämta paketet för att registrera](https://www.microsoft.com/download/details.aspx?id=53554) enheterna med Azure AD.

### <a name="ios-devices"></a>iOS-enheter
Vi rekommenderar att du installerar [Microsoft Authenticator-appen](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) på användarenheter innan du distribuerar principer för villkorlig åtkomst eller MFA. Appen bör åtminstone installeras när användare uppmanas att registrera sin enhet med Azure AD genom att lägga till ett arbets- eller skolkonto, eller när de installerar Intune-företagsportalappen för att registrera sin enhet i hanteringen. Detta beror på den konfigurerade principen för villkorlig åtkomst.

### <a name="android-devices"></a>Android-enheter
Vi rekommenderar användare att installera [Intune Company Portal-appen](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) och [Microsoft Authenticator-appen](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) innan principer för villkorlig åtkomst distribueras eller när det krävs under vissa autentiseringsförsök. Efter appinstallation kan användare bli ombedda att registrera sig hos Azure AD eller registrera sin enhet med Intune. Detta beror på den konfigurerade principen för villkorlig åtkomst.

Vi rekommenderar också att företagsägda enheter (COD) är standardiserade på OEM-tillverkare och versioner som stöder Android for Work eller Samsung Knox för att tillåta e-postkonton, hanteras och skyddas av Intune MDM-policy.


### <a name="recommended-email-clients"></a>Rekommenderade e-postklienter
Följande e-postklienter stöder modern autentisering och villkorlig åtkomst. 

|Plattform|Klient|Version/Anteckningar|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [Aktivera modern autentisering](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication), [Nödvändiga uppdateringar](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**Ios**|Outlook för iOS|[Senaste](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook för Android|[Senaste](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**Macos**|Outlook|2016|
|**Linux**|Stöds inte||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>Rekommenderade klientplattformar vid säkring av dokument
Följande klienter rekommenderas när en princip för säkra dokument har tillämpats.

|Plattform|Word/Excel/PowerPoint|OneNote|OneDrive-app|SharePoint-app|Synkroniseringsklient för OneDrive|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|Stöds|Stöds|EJ TILLÄMPLIGT|EJ TILLÄMPLIGT|Förhandsgranska<sup>*</sup>|
|Windows 8.1|Stöds|Stöds|EJ TILLÄMPLIGT|EJ TILLÄMPLIGT|Förhandsgranska<sup>*</sup>|
|Windows 10|Stöds|Stöds|EJ TILLÄMPLIGT|EJ TILLÄMPLIGT|Förhandsgranska<sup>*</sup>|
|Windows Phone 10|Stöds inte|Stöds inte|Stöds inte|Stöds inte|Stöds inte|
|Android|Stöds|Stöds|Stöds|Stöds|EJ TILLÄMPLIGT|
|Ios|Stöds|Stöds|Stöds|Stöds|EJ TILLÄMPLIGT|
|Macos|Offentlig förhandsversion|Offentlig förhandsversion|EJ TILLÄMPLIGT|EJ TILLÄMPLIGT|Stöds inte|
|Linux|Stöds inte|Stöds inte|Stöds inte|Stöds inte|Stöds inte|

<sup>*</sup>Läs mer om hur du använder villkorlig åtkomst med [OneDrive-synkroniseringsklienten](https://docs.microsoft.com/onedrive/enable-conditional-access).

### <a name="microsoft-365-client-support"></a>Klientsupport för Microsoft 365
Mer information om klientsupport finns i följande artiklar:
- [Stöd för Microsoft 365-klientapp – villkorlig åtkomst](https://docs.microsoft.com/office365/enterprise/office-365-client-support-conditional-access)
- [Stöd för Microsoft 365-klientappar – hantering av mobilappar](https://docs.microsoft.com/office365/enterprise/office-365-client-support-mobile-application-management)
- [Stöd för Microsoft 365-klientappar – modern autentisering](https://docs.microsoft.com/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>Skydda administratörskonton
Azure AD är ett enkelt sätt för dig att börja skydda administratörsåtkomst med en förkonfigurerad princip för villkorlig åtkomst. I Azure AD går du till **Villkorlig åtkomst** och letar efter den här principen – **Baslinjeprincip: Kräv MFA för administratörer (förhandsversion).** Välj den här principen och välj sedan **Använd principen omedelbart**. 

Den här principen kräver MFA för följande roller:
- Globala administratörer
- SharePoint-administratörer
- Exchange-administratörer
- Administratörer för villkorlig åtkomst
- Säkerhetsadministratörer

Mer information finns i [grundläggande säkerhetsprinciper för Azure AD-administratörskonton](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/).

Ytterligare rekommendationer inkluderar följande:
- Använd Azure AD Privileged Identity Management för att minska antalet beständiga administrativa konton. Se [Börja använda PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started). 
- [Använd hantering av privilegierad åtkomst i Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) för att skydda din organisation från överträdelser som kan använda befintliga privilegierade administratörskonton med stående åtkomst till känsliga data eller åtkomst till viktiga konfigurationsinställningar. 
- Använd endast administratörskonton för administration. Administratörer bör ha ett separat användarkonto för regelbunden icke-administrativ användning och endast använda sitt administrativa konto när det behövs för att slutföra en uppgift som är kopplad till deras jobbfunktion. [Microsoft 365-administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) har betydligt fler privilegier än Microsoft 365-tjänster.
- Följ metodtipsen för att skydda privilegierade konton i Azure AD enligt beskrivningen i den här [artikeln](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

## <a name="next-steps"></a>Nästa steg

[Konfigurera de gemensamma principerna för identitets- och enhetsåtkomst](identity-access-policies.md)

