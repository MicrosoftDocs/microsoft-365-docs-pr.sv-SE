---
title: Krav för identitets- och enhetsåtkomst för moln i din Microsoft 365-testmiljö
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
description: Skapa en Microsoft 365-miljö för att testa identitets- och enhetsåtkomst med kraven för molnautentisering.
ms.openlocfilehash: aa18e1a9943ec12465737f6c3f2e12c1fa49e2a3
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398883"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a>Krav för identitets- och enhetsåtkomst för moln i din Microsoft 365-testmiljö

*Den här test laboratorie guiden kan endast användas för test miljöer med Microsoft 365 för företags nätverk.*

[Konfigurationer för identitets-och enhets åtkomst](../security/office-365-security/microsoft-365-policies-configurations.md) är en uppsättning konfigurationer och villkorsstyrda åtkomst principer för att skydda åtkomst till alla tjänster som är integrerade med Azure Active Directory (Azure AD).

I den här artikeln beskrivs hur du kan konfigurera en Microsoft 365-testmiljö som uppfyller kraven för [konfiguration av förutsättningar endast för moln](../security/office-365-security/identity-access-prerequisites.md#prerequisites) för identitets- och enhetsåtkomst.

Konfigurationen av testmiljön består av sju faser:

1.  Bygg ut din förenklade testmiljö
2.  Konfigurera namngivna platser
3.  Konfigurera tillbakaskrivning av lösenord
4.  Konfigurera lösenordsåterställning via självbetjäning
5.  Konfigurera multifaktorautentisering
6.  Aktivera Azure AD Identity Protection
7.  Aktivera modern autentisering för Exchange Online och Skype för företag – Online

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a>Fas 1: Bygga ut din förenklade testmiljö för Microsoft 365

Följ anvisningarna i [Enkel baskonfiguration](lightweight-base-configuration-microsoft-365-enterprise.md).
Här är konfigurationsresultatet.

![Den förenklade testmiljön för Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a>Fas 2: Konfigurera namngivna platser

Bestäm först de offentliga IP-adresser eller adress intervall som används av din organisation.

Följ sedan anvisningarna i [Konfigurera namngivna platser i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) för att lägga till adresserna eller adressintervallen som namngivna platser. 

## <a name="phase-3-configure-password-writeback"></a>Fas 3: Konfigurera tillbakaskrivning av lösenord

Följ anvisningarna i [fas 2 i testlabbguiden för tillbakaskrivning av lösenord](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

## <a name="phase-4-configure-self-service-password-reset"></a>Fas 4: Konfigurera lösenordsåterställning via självbetjäning

Följ anvisningarna i [fas 3 i testlabbguiden för återställning av lösenord](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset). 

När du aktiverar återställning av lösenord för kontona i en särskild Azure AD-grupp lägger du till de här kontona i gruppen för **lösenordsåterställning**:

- Användare 2
- Användare 3
- Användare 4
- Användare 5

Testa lösen ordet bara för användar 2-konto.

## <a name="phase-5-configure-multi-factor-authentication"></a>Fas 5: Konfigurera multifaktorautentisering

Följ anvisningarna i [fas 2 i testlabbguiden för multifaktorautentisering](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) för följande användarkonton:

- Användare 2
- Användare 3
- Användare 4
- Användare 5

Testa endast multifaktorautentisering för kontot Användare 2.

## <a name="phase-6-enable-azure-ad-identity-protection"></a>Fas 6: Aktivera Azure AD Identity Protection

Följ anvisningarna i [fas 2 i testlabbguiden för Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection). 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Fas 7: Aktivera modern autentisering för Exchange Online och Skype för företag – Online

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

Resultatet är en testmiljö som uppfyller kraven för [konfiguration av förutsättningar endast för moln](../security/office-365-security/identity-access-prerequisites.md#prerequisites) för identitets- och enhetsåtkomst. 

## <a name="next-step"></a>Nästa steg

Använd [vanliga identitets- och enhetsprinciper](identity-access-policies.md) när du vill konfigurera de principer som bygger på kraven och skyddar identiteter och enheter.

## <a name="see-also"></a>Se även

[Fler testlabbguider för identitet](m365-enterprise-test-lab-guides.md#identity)

[Identitets översikt](identity-roadmap-microsoft-365.md)

[Testlabbguider för Microsoft 365 för företag](m365-enterprise-test-lab-guides.md)

[Översikt över Microsoft 365 för företag](microsoft-365-overview.md)

[Microsoft 365 för företags dokumentation](https://docs.microsoft.com/microsoft-365-enterprise/)
