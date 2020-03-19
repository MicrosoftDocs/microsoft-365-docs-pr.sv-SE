---
title: Ett nödvändigt arbete för att implementera identitets- och enhetsåtkomstprinciper – Microsoft 365 Enterprise | Microsoft Dokument
description: I artikeln beskrivs principerna för Microsoft-rekommendationer om hur du tillämpar principer och konfigurationer för identitets- och enhetsåtkomst.
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
ms.openlocfilehash: c1af88f489072490777cc6f2c7edfc66fd038bdf
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42811461"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Förutsättningsarbete för att implementera identitets- och enhetsåtkomstprinciper

I den här artikeln beskrivs de förutsättningar som måste implementeras innan du kan distribuera de rekommenderade identitets- och enhetsåtkomstprinciperna. I den här artikeln beskrivs också standardkonfigurationerna för plattformens klientsom vi rekommenderar att de ger användarna den bästa SSO-upplevelsen samt de tekniska förutsättningarna för villkorlig åtkomst.


## <a name="prerequisites"></a>Förutsättningar

Innan du implementerar de rekommenderade identitets- och enhetsåtkomstprinciperna finns det flera förutsättningar som organisationen måste uppfylla. I följande tabell beskrivs de förutsättningar som gäller för din miljö. 


| Konfiguration | Endast molnet | Active Directory med lösenordshash-synkronisering |  Direktautentisering |  Federation med AD FS |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [Konfigurera lösenordhashsynkronisering](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Detta måste vara aktiverat för att identifiera läckta autentiseringsuppgifter och agera på dem för riskbaserad villkorlig åtkomst. **Obs:** Detta krävs oavsett om din organisation använder hanterad autentisering, till exempel genomströmningsautentisering (PTA) eller federerad autentisering. |    | Ja | Ja | Ja |
| [Aktivera sömlös enkel inloggning](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) för att automatiskt logga in användare när de är på sina företagsenheter som är anslutna till företagets nätverk. |  | Ja | Ja |  |
| [Konfigurera namngivna nätverk](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD Identity Protection samlar in och analyserar alla tillgängliga sessionsdata för att generera en riskpoäng. Vi rekommenderar att du anger organisationens offentliga IP-intervall för nätverket i Azure AD-nätverkskonfigurationen. Trafiken som kommer från dessa områden får en minskad riskvärdering och trafik utanför företagsmiljön får en högre riskpoäng. | Ja  | Ja | Ja | Ja |
|[Registrera alla användare för självbetjäning av lösenordsåterställning (SSPR) och multifaktorautentisering (MFA).](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged) Vi rekommenderar att du registrerar användare för Azure MFA i förväg. Azure AD Identity Protection använder Azure MFA för att utföra ytterligare säkerhetsverifiering. För bästa inloggningsupplevelse rekommenderar vi dessutom att användarna installerar [Microsoft Authenticator-appen](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) och Microsoft Company Portal-appen på sina enheter. Dessa kan installeras från App Store för varje plattform. | Ja | Ja | Ja | Ja |
| [Aktivera automatisk enhetsregistrering av domänanslutna Windows-datorer](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). Villkorlig åtkomst kommer att se till att enheter som ansluter till appar är domänanslutna eller kompatibla. För att stödja detta på Windows-datorer måste enheten registreras hos Azure AD.  I den här artikeln beskrivs hur du konfigurerar automatisk enhetsregistrering. |   | Ja |  Ja |  Ja |
| **Förbered ditt supportteam**. Ha en plan på plats för användare som inte kan slutföra MFA. Detta kan vara att lägga till dem i en principundantagsgrupp eller registrera ny MFA-information för dem. Innan du gör någon av dessa säkerhetskänsliga ändringar måste du se till att den faktiska användaren gör begäran. Att kräva att användarnas chefer hjälper till med godkännandet är ett effektivt steg. | Ja | Ja | Ja | Ja |  
| [Konfigurera tillbakaskrivning av lösenord till lokal AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). Med tillbakaskrivning av lösenord kan Azure AD kräva att användare ändrar sina lokala lösenord när en högriskkontokompromiss upptäcks. Du kan aktivera den här funktionen med Azure AD Connect på ett av två sätt: aktivera **lösenordsnedskrivning** på valfria funktioner i installationsguiden för Azure AD Connect eller aktivera den via Windows PowerShell. |   | Ja | Ja | Ja |
| [Aktivera Azure Active Directory Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/enable). Azure AD Identity Protection gör att du kan identifiera potentiella säkerhetsproblem som påverkar organisationens identiteter och konfigurera en automatiserad reparationsprincip till låg, medelhög och hög inloggningsrisk och användarrisk.  | Ja | Ja | Ja | Ja |
| **Aktivera modern autentisering** för [Exchange Online](https://support.office.com/article/Enable-or-disable-modern-authentication-in-Exchange-Online-58018196-f918-49cd-8238-56f57f38d662) och Skype för [företag Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). Modern autentisering är en förutsättning för att använda multifaktorautentisering (MFA). Modern autentisering är aktiverad som standard för Office 2016-klienter, SharePoint Online och OneDrive för företag. | Ja | Ja | Ja | Ja |
||||||



## <a name="recommended-client-configurations"></a>Rekommenderade klientkonfigurationer
I det här avsnittet beskrivs standardkonfigurationerna för plattformsklienten som vi rekommenderar ger användarna den bästa SSO-upplevelsen samt de tekniska förutsättningarna för villkorlig åtkomst.

### <a name="windows-devices"></a>Windows-enheter
Vi rekommenderar Windows 10 (version 1703 eller senare), eftersom Azure är utformat för att ge den smidigaste SSO-upplevelsen möjligt för både lokal och Azure AD. Arbets- eller skolutfärdade enheter bör konfigureras för att ansluta sig till Azure AD direkt eller om organisationen använder lokal AD-domänkoppling, bör dessa enheter [konfigureras för att automatiskt och tyst registrera sig hos Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

För BYOD Windows-enheter kan användare använda **Lägg till arbets- eller skolkonto**. Observera att Chrome-webbläsaranvändare på Windows 10 måste [installera ett tillägg](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) för att få samma smidiga inloggningsupplevelse som Edge/IE-användare. Om din organisation har domänanslutna Windows 7-enheter kan du också installera Microsoft Workplace Join för datorer som inte är Windows 10 [Ladda ned paketet för att registrera](https://www.microsoft.com/download/details.aspx?id=53554) enheterna med Azure AD.

### <a name="ios-devices"></a>iOS-enheter
Vi rekommenderar att du installerar [Microsoft Authenticator-appen](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) på användarenheter innan du distribuerar villkorsstyrd åtkomst eller MFA-principer. Appen bör installeras åtminstone när användare uppmanas att registrera sin enhet med Azure AD genom att lägga till ett arbets- eller skolkonto, eller när de installerar Portalappen Intune company för att registrera sin enhet i hanteringen. Detta beror på den konfigurerade principen för villkorlig åtkomst.

### <a name="android-devices"></a>Android-enheter
Vi rekommenderar att användare installerar [appen Intune Company Portal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) och Microsoft [Authenticator-appen](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) innan principer för villkorlig åtkomst distribueras eller när det behövs under vissa autentiseringsförsök. Efter appinstallationen kan användare bli ombedda att registrera sig hos Azure AD eller registrera sin enhet med Intune. Detta beror på den konfigurerade principen för villkorlig åtkomst.

Vi rekommenderar också att företagsägda enheter (COD) är standardiserade på OEM-tillverkare och versioner som stöder Android for Work eller Samsung Knox för att tillåta e-postkonton, hanteras och skyddas av Intune MDM-policy.


### <a name="recommended-email-clients"></a>Rekommenderade e-postklienter
Följande e-postklienter stöder modern autentisering och villkorlig åtkomst. 

|Plattform|Klient|Version/Anteckningar|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [Aktivera modern autentisering](https://support.office.com/article/Enable-Modern-Authentication-for-Office-2013-on-Windows-devices-7dc1c01a-090f-4971-9677-f1b192d6c910), Nödvändiga [uppdateringar](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**Ios**|Outlook för iOS|[Senaste](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook för Android|[Senaste](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**Macos**|Outlook|2016|
|**Linux**|Stöds inte||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>Rekommenderade klientplattformar när dokument säkras
Följande klienter rekommenderas när en princip för säkra dokument har tillämpats.

|Plattform|Word/Excel/PowerPoint|OneNote|OneDrive-app|SharePoint-app|Synkroniseringsklient för OneDrive|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|Stöds|Stöds|EJ TILLÄMPLIGT|EJ TILLÄMPLIGT|Förhandsgranska<sup>*</sup>|
|Windows 8.1|Stöds|Stöds|EJ TILLÄMPLIGT|EJ TILLÄMPLIGT|Förhandsgranska<sup>*</sup>|
|Windows 10|Stöds|Stöds|EJ TILLÄMPLIGT|EJ TILLÄMPLIGT|Förhandsgranska<sup>*</sup>|
|Windows Phone 10|Stöds inte|Stöds inte|Stöds inte|Stöds inte|Stöds inte|
|Android|Stöds|Stöds|Stöds|Stöds|EJ TILLÄMPLIGT|
|Ios|Stöds|Stöds|Stöds|Stöds|EJ TILLÄMPLIGT|
|Macos|Offentlig förhandsgranskning|Offentlig förhandsgranskning|EJ TILLÄMPLIGT|EJ TILLÄMPLIGT|Stöds inte|
|Linux|Stöds inte|Stöds inte|Stöds inte|Stöds inte|Stöds inte|

<sup>*</sup>Läs mer om hur du använder villkorlig åtkomst med [OneDrive-synkroniseringsklienten](https://support.office.com/article/Azure-Active-Directory-conditional-access-with-the-OneDrive-sync-client-on-Windows-028d73d7-4b86-4ee0-8fb7-9a209434b04e).

### <a name="office-365-client-support"></a>Support för Office 365-klienten
Mer information om Office 365-klientsupport finns i följande artiklar:
- [Support för Office 365 Client App - villkorlig åtkomst](https://docs.microsoft.com/office365/enterprise/office-365-client-support-conditional-access)
- [Support för Office 365 Client App - Hantering av mobila program](https://docs.microsoft.com/office365/enterprise/office-365-client-support-mobile-application-management)
- [Support för Office 365 Client App - Modern autentisering](https://docs.microsoft.com/office365/enterprise/office-365-client-support-modern-authentication)

## <a name="protecting-administrator-accounts"></a>Skydda administratörskonton
Azure AD är ett enkelt sätt för dig att börja skydda administratörsåtkomst med en förkonfigurerad princip för villkorlig åtkomst. I Azure AD går du till **Villkorlig åtkomst** och letar efter den här principen – **Baslinjeprincip: Kräv MFA för administratörer (förhandsgranskning).** Välj den här principen och välj sedan **Använd principen omedelbart**. 

Den här principen kräver MAKROEKONOMISKA krav för följande roller:
- Globala administratörer
- SharePoint-administratörer
- Exchange-administratörer
- Administratörer med villkorlig åtkomst
- Säkerhetsadministratörer

Mer information finns i [Grundläggande säkerhetsprincip för Azure AD-administratörskonton](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/).

Ytterligare rekommendationer inkluderar följande:
- Använd Azure AD Privileged Identity Management för att minska antalet beständiga administrativa konton. Se [Börja använda PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started). 
- [Använd privilegierad åtkomsthantering i Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) för att skydda din organisation från överträdelser som kan använda befintliga privilegierade administratörskonton med stående åtkomst till känsliga data eller åtkomst till kritiska konfigurationsinställningar. 
- Använd endast administratörskonton för administration. Administratörer bör ha ett separat användarkonto för regelbunden icke-administrativ användning och endast använda sitt administrativa konto när det behövs för att slutföra en uppgift som är associerad med deras jobbfunktion. [Office 365-administratörsroller](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d) har betydligt fler privilegier än Office 365-tjänster.
- Följ metodtips för att skydda privilegierade konton i Azure AD enligt beskrivningen i den här [artikeln](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

## <a name="next-steps"></a>Nästa steg

[Konfigurera de gemensamma identitets- och enhetsåtkomstprinciperna](identity-access-policies.md)

