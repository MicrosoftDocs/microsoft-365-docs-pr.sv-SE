---
title: Krav för identitets- och enhetsåtkomst för synkronisering av lösenordshash i din Microsoft 365-testmiljö
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Skapa en Microsoft 365-miljö för att testa identitets- och enhetsåtkomst med kraven för autentisering av synkronisering av lösenordshash.
ms.openlocfilehash: 63f433d5297139fcc7f6eb8bd5383a6593c29388
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399449"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a>Krav för identitets- och enhetsåtkomst för synkronisering av lösenordshash i din Microsoft 365-testmiljö

*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*

[Konfigurationer för identitets-och enhets åtkomst](../security/office-365-security/microsoft-365-policies-configurations.md) är en uppsättning konfigurationer och villkorsstyrda åtkomst principer för att skydda åtkomst till alla tjänster i Microsoft 365 för företag som är integrerade med Azure Active Directory (Azure AD).

I den här artikeln beskrivs hur du kan konfigurera en Microsoft 365-testmiljö som uppfyller kraven för [konfiguration av Active Directory med förutsättningar för synkronisering av lösenordshash](../security/office-365-security/identity-access-prerequisites.md#prerequisites) för identitets- och enhetsåtkomst.

Konfigurationen av testmiljön består av åtta faser:

1.  Skapa ett simulerat företag med testmiljö för synkronisering av lösenordshash
2.  Konfigurera enkel inloggning med Azure AD
3.  Konfigurera namngivna platser
4.  Konfigurera tillbakaskrivning av lösenord
5.  Konfigurera lösenordsåterställning via självbetjäning för alla användarkonton
6.  Konfigurera multifaktorautentisering för alla användarkonton
7.  Aktivera Azure AD Identity Protection
8.  Aktivera modern autentisering för Exchange Online och Skype för företag – Online

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a>Fas 1: Bygg ut det simulerade företaget med lösenordshash-synkronisering för Microsoft 365-testmiljön

Följ anvisningarna i [Synkronisering av hash-lösenord](password-hash-sync-m365-ent-test-environment.md).
Här är konfigurationsresultatet.

![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a>Fas 2: Konfigurera enkel inloggning med Azure AD

Följ anvisningarna i [fas 2 i testlabbguiden för enkel inloggning med Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).

## <a name="phase-3-configure-named-locations"></a>Fas 3: Konfigurera namngivna platser

Bestäm först de offentliga IP-adresser eller adress intervall som används av din organisation.

Följ sedan anvisningarna i [Konfigurera namngivna platser i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) för att lägga till adresserna eller adressintervallen som namngivna platser. 

## <a name="phase-4-configure-password-writeback"></a>Fas 4: Konfigurera tillbakaskrivning av lösenord

Följ anvisningarna i [fas 2 i testlabbguiden för tillbakaskrivning av lösenord](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

## <a name="phase-5-configure-self-service-password-reset"></a>Fas 5: Konfigurera lösenordsåterställning via självbetjäning

Följ anvisningarna i [fas 3 i testlabbguiden för återställning av lösenord](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset). 

När du aktiverar återställning av lösenord för kontona i en särskild Azure AD-grupp lägger du till de här kontona i gruppen för **lösenordsåterställning**:

- Användare 2
- Användare 3
- Användare 4
- Användare 5

Testa lösen ordet bara för användar 2-konto.

## <a name="phase-6-configure-multi-factor-authentication"></a>Fas 6: Konfigurera multifaktorautentisering

Följ anvisningarna i [fas 2 i testlabbguiden för multifaktorautentisering](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) för följande användarkonton:

- Användare 2
- Användare 3
- Användare 4
- Användare 5

Testa endast multifaktorautentisering för kontot Användare 2.

## <a name="phase-7-enable-azure-ad-identity-protection"></a>Fas 7: Aktivera Azure AD Identity Protection

Följ anvisningarna i [fas 2 i testlabbguiden för Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection). 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Fas 8: Aktivera modern autentisering för Exchange Online och Skype för företag – Online

Följ [dessa anvisningar](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later) för Exchange Online. 

För Skype för företag – Online:

1. Anslut till [Skype för företag – Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

2. Kör det här kommandot.

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. Kör följande kommando för att verifiera att ändringen genomfördes.

  ```powershell
  Get-CsOAuthConfiguration
  ```

Resultatet är en testmiljö som uppfyller kraven för [konfiguration av Active Directory med förutsättningar för synkronisering av lösenordshash](../security/office-365-security/identity-access-prerequisites.md#prerequisites) för identitets- och enhetsåtkomst. 

## <a name="next-step"></a>Nästa steg

Använd [vanliga identitets- och enhetsprinciper](identity-access-policies.md) när du vill konfigurera de principer som bygger på kraven och skyddar identiteter och enheter.

## <a name="see-also"></a>Se även

[Fler testlabbguider för identitet](m365-enterprise-test-lab-guides.md#identity)

[Identitets översikt](identity-roadmap-microsoft-365.md)

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
