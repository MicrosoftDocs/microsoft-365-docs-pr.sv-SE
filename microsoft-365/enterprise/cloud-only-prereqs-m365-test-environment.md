---
title: Krav för identitets- och enhetsåtkomst för moln i din Microsoft 365-testmiljö
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
description: Skapa en Microsoft 365-miljö för att testa identitets- och enhetsåtkomst med kraven för molnautentisering.
ms.openlocfilehash: 927aa032e4181206b3a744da7076b696ac5cf4d4
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199555"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a>Krav för identitets- och enhetsåtkomst för moln i din Microsoft 365-testmiljö

*Den här testlabbguiden kan endast användas för Microsoft 365 för företagstestmiljöer.*

[Identitets- och enhetsåtkomstkonfigurationer](../security/office-365-security/microsoft-365-policies-configurations.md) är en uppsättning rekommenderade konfigurationer och villkorsstyrda åtkomstprinciper för att skydda åtkomsten till alla tjänster som är integrerade med Azure Active Directory (Azure AD).

I den här artikeln beskrivs hur du kan konfigurera en Microsoft 365-testmiljö som uppfyller kraven för [konfiguration av förutsättningar endast för moln](../security/office-365-security/identity-access-prerequisites.md#prerequisites) för identitets- och enhetsåtkomst.

Konfigurationen av testmiljön består av åtta faser. Du behöver:

1. Bygg ut din förenklade testmiljö
2. Konfigurera namngivna platser
3. Konfigurera lösenordsåterställning via självbetjäning
4. Konfigurera multifaktorautentisering
5. Aktivera automatisk enhetsregistrering för domänbaserade Windows-datorer
6. Konfigurera lösenordsskydd i Azure AD 
7. Aktivera Azure AD Identity Protection
8. Aktivera modern autentisering för Exchange Online och Skype för företag – Online

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a>Fas 1: Bygga ut din förenklade testmiljö för Microsoft 365

Följ anvisningarna i [Enkel baskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).
Här är konfigurationsresultatet.

![Den förenklade testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 
## <a name="phase-2-configure-named-locations"></a>Fas 2: Konfigurera namngivna platser

Bestäm först de offentliga IP-adresser eller adress intervall som används av din organisation.

Följ sedan anvisningarna i [Konfigurera namngivna platser i Azure Active Directory](/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) för att lägga till adresserna eller adressintervallen som namngivna platser. 

## <a name="phase-3-configure-self-service-password-reset"></a>Steg 3: Konfigurera självbetjäning för återställning av lösenord

Följ anvisningarna i [fas 3 i testlabbguiden för återställning av lösenord](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset). 

När du aktiverar återställning av lösenord för kontona i en särskild Azure AD-grupp lägger du till de här kontona i gruppen för **lösenordsåterställning**:

- Användare 2
- Användare 3
- Användare 4
- Användare 5

Testa lösen ordet bara för användar 2-konto.

## <a name="phase-4-configure-multi-factor-authentication"></a>Fas 4: Konfigurera multifaktorautentisering

Följ anvisningarna i [fas 2 i testlabbguiden för multifaktorautentisering](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) för följande användarkonton:

- Användare 2
- Användare 3
- Användare 4
- Användare 5

Testa endast multifaktorautentisering för kontot Användare 2.

## <a name="phase-5-enable-automatic-device-registration-of-domain-joined-windows-computers"></a>Steg 5: Aktivera automatisk enhetsregistrering på domänbaserade Windows-datorer 

Följ [de här anvisningarna](/azure/active-directory/devices/hybrid-azuread-join-plan) för att aktivera automatisk enhetsregistrering på domänbaserade Windows-datorer.

## <a name="phase-6-configure-azure-ad-password-protection"></a>Steg 6: Konfigurera lösenordsskydd i Azure AD 

Följ [dessa anvisningar](/azure/active-directory/authentication/concept-password-ban-bad) för att blockera kända svaga lösenord och deras varianter.

## <a name="phase-7-enable-azure-ad-identity-protection"></a>Fas 7: Aktivera Azure AD Identity Protection

Följ anvisningarna i [fas 2 i testlabbguiden för Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection). 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Fas 8: Aktivera modern autentisering för Exchange Online och Skype för företag – Online

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

Resultatet är en testmiljö som uppfyller kraven för den moln enda nödvändiga [konfigurationen för identiteter](../security/office-365-security/identity-access-prerequisites.md#prerequisites) och enhetsåtkomst. 

## <a name="next-step"></a>Nästa steg

Använd [vanliga identitets- och enhetsprinciper](../security/office-365-security/identity-access-policies.md) när du vill konfigurera de principer som bygger på kraven och skyddar identiteter och enheter.

## <a name="see-also"></a>Se även

[Fler testlabbguider för identitet](m365-enterprise-test-lab-guides.md#identity)

[Identitetsöversikt](identity-roadmap-microsoft-365.md)

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Dokumentation om Microsoft 365 för företag](/microsoft-365-enterprise/)
