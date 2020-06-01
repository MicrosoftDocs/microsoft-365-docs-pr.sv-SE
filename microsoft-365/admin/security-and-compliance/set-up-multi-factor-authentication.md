---
title: Konfigurera multifaktorautentisering för användare
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Lär dig hur du konfigurerar multifaktorautentisering för din organisation.
monikerRange: o365-worldwide
ms.openlocfilehash: c84c66cc051363fbc582abfb5521f922440b6801
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432385"
---
# <a name="set-up-multi-factor-authentication"></a>Konfigurera multifaktorautentisering
  
Baserat på din förståelse av [MFA (Multi Factor Authentication) och dess stöd i Microsoft 365](multi-factor-authentication-microsoft-365.md)är det dags att konfigurera den och distribuera den till din organisation.

Innan du börjar, ta reda på om dessa särskilda villkor gäller för dig och vidta lämpliga åtgärder:

- Om du har Office 2013-klienter på Windows-enheter [aktiverar du Modern autentisering](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).

- Om du har katalogtjänster från tredje part med Active Directory Federation Services (AD FS) konfigurerar du Azure MFA Server. Mer information finns i [avancerade scenarier med Azure Multi-Factor Authentication och VPN-lösningar från tredje part.](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>Steg 1: Bestäm metoden för att kräva att användarna använder MFA

> [!NOTE]
> Du måste vara global administratör för att kunna konfigurera eller ändra MFA. Det finns tre sätt att kräva att användarna använder MFA för inloggningar. Mer information finns [i MFA-supporten i Microsoft 365.](multi-factor-authentication-microsoft-365.md)

- Standardvärden för säkerhet (rekommenderas för småföretag)

  Om du har köpt din prenumeration eller utvärderingsversion efter den 21 oktober 2019 och du oväntat uppmanas att ange MFA har [säkerhetsinställningarna aktiverats](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) automatiskt för din prenumeration.
  
  Varje ny Microsoft 365-prenumeration har automatiskt aktiverat säkerhetsstandarder. Det innebär att alla användare måste konfigurera MFA och installera Microsoft Authenticator-appen på sin mobila enhet.

  Alla användare måste använda Microsoft Authenticator-appen eftersom deras ytterligare verifieringsmetod och äldre autentisering blockeras. 

- Principer för villkorlig åtkomst (rekommenderas för företag)

  Användare väljer ytterligare verifieringsmetod under MFA-registrering.

- Per användarkonto (rekommenderas inte)

  Användare väljer ytterligare verifieringsmetod under MFA-registrering.

## <a name="step-2-test-mfa-on-your-pilot-users"></a>Steg 2. Testa MFA på dina pilotanvändare

Om du använder principer för villkorlig åtkomst eller MFA (rekommenderas inte för användare) väljer du pilotanvändare i ditt företag eller din organisation för att testa MFA-registrering och inloggningar. Till exempel:

- För principer för villkorlig åtkomst skapar du en pilotanvändargrupp och en princip som kräver MFA för medlemmarna i gruppen och för alla appar. Lägg sedan till pilotanvändarens konton i gruppen.

- För MFA per användare aktiverar du MFA för pilotanvändarnas användarkonton en gång.

Arbeta med pilotanvändarna för att ta itu med frågor och problem för att förbereda en smidig utrullning till din organisation.

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>Steg 3. Informera din organisation om att MFA kommer

Använd e-postaviseringar, hallaffischer, gruppmöten eller formell utbildning för att se till att dina anställda förstår:

- Varför MFA krävs för inloggningar
- [Så här registrerar du dig för ytterligare verifieringsmetod](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [Så här loggar du in efter registreringen](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [Så här ändrar du sin ytterligare verifieringsmetod](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [Hur man hanterar situationer som en ny smart telefon](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

Viktigast av allt, se till att dina anställda förstår ***när MFA kravet kommer att införas*** så att det inte förvånar dem.

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>Steg 4. Distribuera MFA-kravet till din organisation eller användare

Baserat på din valda MFA-kravmetod, distribuera MFA-autentisering till de anställda utanför dina pilottestare.

### <a name="security-defaults"></a>Standardinställningar för säkerhet

Du aktiverar eller inaktiverar säkerhetsstandarder från **egenskapsfönstret** för Azure Active Directory (Azure AD) i Azure-portalen.

1.  Logga in på [Microsoft 365-administrationscentret](https://admin.microsoft.com) med globala administratörsuppgifter.
2.  Gå till [sidan Azure Active Directory - Egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3.  Längst ner på sidan väljer du **Hantera säkerhetsstandarder**.
4.  Välj **Ja** om du vill aktivera standardvärden för säkerhet och **Nej** om du vill inaktivera standardvärden för säkerhet och välj sedan **Spara**.

Om du har använt [grundläggande principer för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)går du vidare till att använda säkerhetsstandarder.

1.  Gå till [sidan Villkorlig åtkomst - Principer](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2.  Välj varje baslinjeprincip som är **På** och ange **Aktivera princip** till **Av**.
2.  Gå till [sidan Azure Active Directory - Egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4.  Längst ner på sidan väljer du **Hantera säkerhetsstandarder**.
5.  Välj **Ja** om du vill aktivera standardvärden för säkerhet och **Nej** om du vill inaktivera standardvärden för säkerhet och välj sedan **Spara**.

### <a name="conditional-access-policies"></a>Principer för villkorsstyrd åtkomst

Skapa, konfigurera och aktivera lämpliga principer som innehåller den grupp användare som kräver MFA för inloggning.

### <a name="per-user-mfa-not-recommended"></a>MFA per användare (rekommenderas inte)

Aktivera användarkonton för MFA som motsvarar din distribution.

### <a name="supporting-your-employees"></a>Stöd till dina anställda

När dina anställda registrerar sig och börjar logga in med MFA, se till att dina IT-specialister, IT-avdelning eller helpdesk kan svara på frågor och åtgärda problem snabbt.

I den här artikeln finns [information om felsökning av MFA-inloggningar](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2). 


