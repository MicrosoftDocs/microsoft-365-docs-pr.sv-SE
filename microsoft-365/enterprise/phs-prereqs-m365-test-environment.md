---
title: Krav för identitets- och enhetsåtkomst för synkronisering av lösenordshash i din Microsoft 365-testmiljö
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Skapa en Microsoft 365-miljö för att testa identitets- och enhetsåtkomst med kraven för autentisering av synkronisering av lösenordshash.
ms.openlocfilehash: a3b02167bc3c1d2e7bc809d227ce5537114ffff9
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199447"
---
# <a name="identity-and-device-access-prerequisites-for-password-hash-synchronization-in-your-microsoft-365-test-environment"></a>Krav för identitets- och enhetsåtkomst för synkronisering av lösenordshash i din Microsoft 365-testmiljö

*Den här testlabbguiden kan endast användas Microsoft 365 för företagstestmiljöer.*

[Identitets- och enhetsåtkomstkonfigurationer](../security/office-365-security/microsoft-365-policies-configurations.md) är en uppsättning konfigurationer och villkorsstyrda åtkomstprinciper för att skydda åtkomsten till alla tjänster i Microsoft 365 för företag som är integrerade med Azure Active Directory (Azure AD).

I den här artikeln beskrivs hur du konfigurerar en Microsoft 365 testmiljö som uppfyller kraven för [hybrid](../security/office-365-security/identity-access-prerequisites.md#prerequisites) med synkronisering av lösenordshashar för autentisering som krävs för identitets- och enhetsåtkomst.

Det finns tio faser för att konfigurera testmiljön:

1. Skapa ett simulerat företag med testmiljö för synkronisering av lösenordshash
2. Konfigurera enkel inloggning med Azure AD
3. Konfigurera namngivna platser
4. Konfigurera tillbakaskrivning av lösenord
5. Konfigurera lösenordsåterställning via självbetjäning för alla användarkonton
6. Konfigurera multifaktorautentisering för alla användarkonton
7. Aktivera automatisk enhetsregistrering för domän-Windows datorer
8. Konfigurera lösenordsskydd i Azure AD 
9. Aktivera Azure AD Identity Protection
10. Aktivera modern autentisering för Exchange Online och Skype för företag – Online

## <a name="phase-1-build-out-your-simulated-enterprise-with-password-hash-sync-microsoft-365-test-environment"></a>Fas 1: Bygg ut det simulerade företaget med lösenordshash-synkronisering för Microsoft 365-testmiljön

Följ anvisningarna i [testlabbguiden för synkronisering av](password-hash-sync-m365-ent-test-environment.md) lösenordshashar.
Här är konfigurationsresultatet.

![Det simulerade företaget med testmiljö för synkronisering av lösenordshash](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a>Fas 2: Konfigurera enkel inloggning med Azure AD

Följ anvisningarna i [fas 2 i testlabbguiden för enkel inloggning med Azure AD](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).

## <a name="phase-3-configure-named-locations"></a>Fas 3: Konfigurera namngivna platser

Bestäm först de offentliga IP-adresser eller adress intervall som används av din organisation.

Följ sedan anvisningarna i [Konfigurera namngivna platser i Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) för att lägga till adresserna eller adressintervallen som namngivna platser. 

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

## <a name="phase-7-enable-automatic-device-registration-of-domain-joined-windows-computers"></a>Steg 7: Aktivera automatisk enhetsregistrering för domänbaserade Windows datorer 

Följ [de här anvisningarna](/azure/active-directory/devices/hybrid-azuread-join-plan) för att aktivera automatisk enhetsregistrering för domän-Windows datorer.

## <a name="phase-8-configure-azure-ad-password-protection"></a>Steg 8: Konfigurera lösenordsskydd i Azure AD 

Följ [dessa anvisningar](/azure/active-directory/authentication/concept-password-ban-bad) för att blockera kända svaga lösenord och deras varianter.

## <a name="phase-9-enable-azure-ad-identity-protection"></a>Fas 9: Aktivera Azure AD Identity Protection

Följ anvisningarna i [fas 2 i testlabbguiden för Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection). 

## <a name="phase-10-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Fas 10: Aktivera modern autentisering för Exchange Online och Skype för företag Online

Följ [dessa anvisningar](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later) för Exchange Online. 

För Skype för företag – Online:

1. Anslut till [Skype för företag – Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

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

Använd [vanliga identitets- och enhetsprinciper](../security/office-365-security/identity-access-policies.md) när du vill konfigurera de principer som bygger på kraven och skyddar identiteter och enheter.

## <a name="see-also"></a>Se även

[Fler testlabbguider för identitet](m365-enterprise-test-lab-guides.md#identity)

[Identitetsöversikt](identity-roadmap-microsoft-365.md)

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Dokumentation om Microsoft 365 för företag](/microsoft-365-enterprise/)
