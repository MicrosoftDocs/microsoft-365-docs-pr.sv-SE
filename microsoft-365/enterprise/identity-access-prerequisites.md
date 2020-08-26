---
title: Nödvändigt arbete för implementering av identitets-och enhets åtkomst principer – Microsoft 365 för företag | Microsoft-dok
description: Beskriver policyer för Microsoft-rekommendationer om hur du tillämpar åtkomst principer och konfigurationer för identiteter och enheter.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: a81e17cad1722c58f5bf13b2a36c16fc2ff5cba4
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898046"
---
# <a name="prerequisite-work-for-implementing-identity-and-device-access-policies"></a>Nödvändigt arbete för implementering av identitets-och enhets åtkomst principer

I den här artikeln beskrivs förutsättningar som måste implementeras innan du kan distribuera Rekommenderad identitet och enhets åtkomst principer. I den här artikeln beskrivs också de standardinställningar för Platform-klient vi rekommenderar att tillhandahålla den bästa SSO-upplevelsen för användarna, samt de tekniska kraven för villkorlig åtkomst.


## <a name="prerequisites"></a>Förutsättningar

Innan du implementerar Rekommenderad identitet och åtkomst principer måste du ha flera förutsättningar för att organisationen ska kunna mötas. I följande tabell beskrivs de förutsättningar som gäller för din miljö. 


| Konfiguration | Endast molnet | Active Directory med Lösenordssynkronisering för lösen ord |  Direktautentisering |  Federation med AD FS |
| :------------- | :-----------: | :--------------: | :------------: | :------------: |
|  [Konfigurera synkronisering av lösen ord](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization). Detta måste vara aktiverat för att upptäcka läcka autentiseringsuppgifter och för att fungera med en riskfylld, villkorlig åtkomst. **Obs!** Det här är obligatoriskt oavsett om din organisation använder hanterad inloggning, till exempel vidarekoppling (PTA) eller federerad behörighet. |    | Ja | Ja | Ja |
| [Aktivera sömlös enkel inloggning](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso) för att automatiskt signera användare när de är på deras företags enheter som är anslutna till företagets nätverk. |  | Ja | Ja |  |
| [Konfigurera namngivna nätverk](https://docs.microsoft.com/azure/active-directory/active-directory-known-networks-azure-portal). Azure AD Identity Protection samlar in och analyserar alla tillgängliga sessionsdata för att generera risk poäng. Vi rekommenderar att du anger din organisations offentliga IP-adressintervall för ditt nätverk i konfiguration av Azure AD med namnet Networks. Trafik från dessa områden ges minskad risk Poäng och trafik utanför företags miljön ges ett högre risk poäng. | Ja  | Ja | Ja | Ja |
|[Registrera alla användare för självbetjäning för återställning av lösen ord (SSPR) och multifaktorautentisering (MFA)](https://docs.microsoft.com/azure/active-directory/authentication/concept-registration-mfa-sspr-converged). Vi rekommenderar att du registrerar användare för Azure MFA i förväg. Azure AD Identity Protection använder Azure MFA för att utföra ytterligare säkerhets verifiering. För bästa inloggnings upplevelse rekommenderar vi att användare installerar [Microsoft Authenticator-appen](https://docs.microsoft.com/azure/active-directory/user-help/microsoft-authenticator-app-how-to) och Microsoft-företagsportalsappen på sina enheter. De här kan installeras från App Store för varje plattform. | Ja | Ja | Ja | Ja |
| [Aktivera automatisk registrering av en domänansluten Windows-dator](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup). Villkorsstyrd åtkomst säkerställer att enheter som ansluter till program är domänansluten eller kompatibla. För att du ska kunna använda detta på Windows-datorer måste enheten vara registrerad med Azure AD.  I den här artikeln beskrivs hur du konfigurerar automatisk registrering av enheter. |   | Ja |  Ja |  Ja |
| **Förbered support teamet**. Ha en plan för användare som inte kan slutföra MFA. Detta kan läggas till i en princip undantags grupp eller Registrera ny MFA-information för dem. Innan du gör något av följande säkerhets känsliga ändringar måste du se till att den faktiska användaren gör det. Att kräva att användarnas chefer får hjälp med godkännandet är ett effektivt steg. | Ja | Ja | Ja | Ja |  
| [Konfigurera tillbakaskrivning för lösen ord för lokal annons](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started). Med Lösenordssynkronisering kan Azure AD begära att användarna ändrar sina lokala lösen ord när ett högrisk problem upptäcks. Du kan aktivera den här funktionen med Azure AD Connect på ett av två sätt: aktivera **Ångra lösen ord** på skärmen valfria funktioner i installations guiden för Azure AD Connect eller aktivera den via Windows PowerShell. |   | Ja | Ja | Ja |
| [Aktivera Azure Active Directory](https://docs.microsoft.com/azure/active-directory/identity-protection/enable)-kryptering. Azure AD Identity Protection gör att du kan upptäcka potentiella sårbarheter som påverkar organisationens identitet och konfigurera en automatisk reparations princip för att Visa riskerna med låg, medelhög och stor inloggning och användare.  | Ja | Ja | Ja | Ja |
| **Aktivera modern lösenordsautentisering** för [Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online) och för [Skype för företag – Online](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). Modern verifiering är en förutsättning för att använda multifaktorautentisering. Modern autentisering är aktive rad som standard för Office 2016-klienter, SharePoint Online och OneDrive för företag. | Ja | Ja | Ja | Ja |
||||||



## <a name="recommended-client-configurations"></a>Rekommenderade klientkonfigurationer
I det här avsnittet beskrivs de standardinställningar för Platform-klient vi rekommenderar att tillhandahålla den bästa SSO-upplevelsen för användarna, samt de tekniska kraven för villkorlig åtkomst.

### <a name="windows-devices"></a>Windows-enheter
Vi rekommenderar Windows 10 (version 1703 eller senare) eftersom Azure är utformat för att tillhandahålla det smidigaste SSO-gränssnittet för både lokalt och Azure AD. Arbets-eller skolbaserade enheter ska konfigureras för att ansluta till Azure AD direkt eller om organisationen använder lokal AD-domänansluten-anslutning ska dessa enheter [konfigureras att automatiskt och tyst registrera med Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-automatic-device-registration-setup).

För BYOD Windows-enheter kan användare använda **Lägg till arbets-eller skol konto**. Observera att Chrome-Browser-användare i Windows 10 måste [Installera ett tillägg](https://chrome.google.com/webstore/detail/windows-10-accounts/ppnbnpeolgkicgegkbkbjmhlideopiji?utm_source=chrome-app-launcher-info-dialog) för att få samma smidiga inloggnings upplevelse som användare i Edge/IE. Om din organisation har domänanslutna Windows 7-enheter kan du även installera Microsoft Workplace Join för datorer som inte har Windows 10 [Ladda ner paketet och registrera](https://www.microsoft.com/download/details.aspx?id=53554) enheterna med Azure AD.

### <a name="ios-devices"></a>iOS-enheter
Vi rekommenderar att du installerar [Microsoft Authenticator-appen](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) på användarnas enheter innan du distribuerar villkorsstyrd åtkomst eller MFA-principer. Du bör minst installera programmet när användarna ska registrera sin enhet med Azure AD genom att lägga till ett arbets-eller skol konto, eller när de installerar programmet Intune-företagsportalsappen för att registrera enheten i hanteringen. Detta beror på den konfigurerade principen för villkorsstyrd åtkomst.

### <a name="android-devices"></a>Android-enheter
Vi rekommenderar att användare installerar [programmet Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal&hl=en) -företagsportalsappen och [Microsoft Authenticator-appen](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) innan principer för villkorsstyrd åtkomst distribueras eller när det behövs under vissa autentiseringsförsök. Efter programinstallationen kan användarna uppmanas att registrera sig med Azure AD eller registrera sin enhet med Intune. Detta beror på den konfigurerade principen för villkorsstyrd åtkomst.

Vi rekommenderar även att företagsägda enheter (COD) standardiseras på OEM-tillverkare och versioner som stöder Android för arbete eller Samsung KNOX för att tillåta e-postkonton, hanteras och skyddas av Intune MDM policy.


### <a name="recommended-email-clients"></a>Rekommenderade e-postklienter
Följande e-postklienter stöder modern och villkorlig åtkomst. 

|Plattform|Klient|Version/anteckningar|
|:-------|:-----|:------------|
|**Windows**|Outlook|2016, 2013 [Aktivera modern verifikation](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication), [nödvändiga uppdateringar](https://support.office.com/article/Outlook-Updates-472c2322-23a4-4014-8f02-bbc09ad62213)|
|**iOS**|Outlook för iOS|[RelatesTo](https://itunes.apple.com/us/app/microsoft-outlook-email-and-calendar/id951937596?mt=8)|
|**Android**|Outlook för Android|[RelatesTo](https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en)|
|**macOS**|Outlook|2016|
|**Linux**|Stöds inte||
|||


### <a name="recommended-client-platforms-when-securing-documents"></a>Rekommenderade klient plattformar när du skyddar dokument
Följande klienter rekommenderas när en princip för säker dokument tillämpas.

|Plattform|Word/Excel/PowerPoint|OneNote|OneDrive-appen|SharePoint-App|OneDrive-synkroniseringsklient|
|:-------|:-----|:------------|:-------|:-------------|:-----|
|Windows 7|Stöds|Stöds|EJ TILLÄMPLIGT|EJ TILLÄMPLIGT|Automatisk<sup>*</sup>|
|Windows 8,1|Stöds|Stöds|EJ TILLÄMPLIGT|EJ TILLÄMPLIGT|Automatisk<sup>*</sup>|
|Windows 10|Stöds|Stöds|EJ TILLÄMPLIGT|EJ TILLÄMPLIGT|Automatisk<sup>*</sup>|
|Windows Phone 10|Stöds inte|Stöds inte|Stöds inte|Stöds inte|Stöds inte|
|Android|Stöds|Stöds|Stöds|Stöds|Saknas|
|iOS|Stöds|Stöds|Stöds|Stöds|Saknas|
|macOS|Offentlig för hands version|Offentlig för hands version|EJ TILLÄMPLIGT|EJ TILLÄMPLIGT|Stöds inte|
|Linux|Stöds inte|Stöds inte|Stöds inte|Stöds inte|Stöds inte|

<sup>*</sup> Läs mer om hur du använder villkorlig åtkomst med [OneDrive-synkroniseringsklienten](https://docs.microsoft.com/onedrive/enable-conditional-access).

### <a name="microsoft-365-client-support"></a>Support för Microsoft 365-klienter
Mer information om support för klienter finns i följande artiklar:
- [Microsoft 365-klientprogram – villkorlig åtkomst](microsoft-365-client-support-conditional-access.md)
- [Microsoft 365-klientprogram – modern-verifikation](microsoft-365-client-support-modern-authentication.md)

## <a name="protecting-administrator-accounts"></a>Skydda administratörs konton
Azure AD är ett enkelt sätt att börja skydda administratörs åtkomst med en förkonfigurerad princip för villkorsstyrd åtkomst. Gå till **villkorlig åtkomst** i Azure AD och leta efter den här policyn – **bas linje princip: Kräv MFA för administratörer (för hands version)**. Välj den här principen och välj sedan **Använd policy omedelbart**. 

Den här principen kräver MFA för följande roller:
- Globala administratörer
- SharePoint-administratörer
- Exchange-administratörer
- Administratörer för villkorsstyrd åtkomst
- Säkerhets administratörer

Mer information finns i avsnittet [grundläggande säkerhets principer för administratörs konton för Azure AD](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/22/baseline-security-policy-for-azure-ad-admin-accounts-in-public-preview/).

Ytterligare rekommendationer är bland annat:
- Använd Azure AD privilegie rad identitets hantering för att minska antalet beständiga administratörs konton. Se [börja använda PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-getting-started). 
- [Använd hanteringen av privilegie rad åtkomst](../compliance/privileged-access-management-overview.md) för att skydda din organisation från intrång som kan använda befintliga administratörs konton med åtkomst till känsliga data eller åtkomst till viktiga konfigurations inställningar. 
- Använd endast administratörs konton för administration. Administratörer bör ha ett separat användar konto för regelbunden icke-administrativ användning och bara använda sitt administratörs konto när det behövs för att slutföra en aktivitet som är kopplad till deras jobb funktion. [Microsoft 365-administratörs](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) roller har betydligt fler privilegier än Microsoft 365-tjänster.
- Följ de bästa metoderna för att skydda privilegierade konton i Azure AD enligt beskrivningen i den här [artikeln](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

## <a name="next-steps"></a>Nästa steg

[Konfigurera principer för åtkomst för identitet och enheter](identity-access-policies.md)

