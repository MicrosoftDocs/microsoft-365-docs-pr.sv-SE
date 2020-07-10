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
localization_priority: Priority
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
ms.openlocfilehash: 56ca51e77b2ba4fa370a2814a7be9df1393c29dc
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083544"
---
# <a name="set-up-multi-factor-authentication"></a>Konfigurera multifaktorautentisering
  
Eftersom du har kunskap om [multifaktorautentisering (MFA) och dess stöd i Microsoft 365](multi-factor-authentication-microsoft-365.md) är det dags att konfigurera och distribuera det i din organisation.

Innan du börjar kontrollerar du om dessa särskilda villkor gäller för dig och vidtar lämpliga åtgärder:

- Om du har Office 2013-klienter på Windows-enheter kan du [aktivera modern autentisering](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).

- Om du har katalogtjänster från tredje part med Active Directory Federation Services (AD FS) konfigurerar du Microsoft Azure MFA-servern. Mer information finns i [avancerade scenarier med Azure multifaktorautentisering och VPN-lösningar från tredje part](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn).

Alla andra användare kommer att ombes utföra ytterligare autentisering vid behov. Gå till [metod och inställningar för tvåfaktorsautentisering](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device) för mer information.

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>Steg 1: Bestäm med vilken metod användarna ska uppmanas att använda MFA. 

> [!NOTE]
> Du måste vara global administratör för att kunna konfigurera eller ändra MFA. Det finns tre sätt att kräva att användarna använder MFA för inloggning. Mer information finns i [MFA-support i Microsoft 365](multi-factor-authentication-microsoft-365.md).

- Standardinställningar för säkerhet (rekommenderas för små företag)

  Om du har köpt din prenumeration eller utvärderingsversion efter den 21 oktober 2019 och plötsligt uppmanas att använda MFA, betyder det att [säkerhetsstandarder](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) har aktiverats automatiskt för prenumerationen.
  
  Säkerhetsstandarder aktiveras automatiskt för alla nya Microsoft 365-prenumerationer. Det innebär att alla användare måste konfigurera multifaktorautentisering (MFA) och installera Microsoft Authenticator-appen på deras mobila enheter.

  Alla användare måste använda Microsoft Authenticator-appen som en extra autentiseringsmetod och äldre autentisering blockeras. 

- Principer för villkorsstyrd åtkomst (rekommenderas för företag)

  Användare väljer den extra verifieringsmetoden när de registrerar sig för MFA.

- Konto per användare (rekommenderas inte)

  Användare väljer den extra verifieringsmetoden när de registrerar sig för MFA.

## <a name="step-2-test-mfa-on-your-pilot-users"></a>Steg 2. Testa MFA med dina pilotanvändare

Om du använder villkorsstyrda åtkomstprinciper eller MFA per användare (rekommenderas inte) kan du välja pilotanvändare i ditt företag eller din organisation för att testa registrering och inloggning med MFA. Exempel:

- För villkorsstyrda åtkomstprinciper kan du skapa en grupp med pilotanvändare och en princip som kräver MFA för gruppmedlemmarna och för alla appar. Lägg sedan till pilotanvändarnas användarkonton i gruppen.

- För MFA per användare kan du aktivera MFA för pilotanvändarnas användarkonton ett i taget.

Arbeta tillsammans med dina pilotanvändare för att ta itu med frågor och problem och förbered för en smidig distribution i organisationen.

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>Steg 3. Informera din organisation om att MFA kommer att tas i bruk

Använd e-postmeddelanden, affischer i korridorerna, gruppmöten eller officiella utbildningar för att säkerställa att dina anställda förstår:

- Varför MFA krävs för inloggning
- [Så här registrerar du dig för den extra autentiseringsmetoden](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [Så här loggar du in efter registrering](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [Så här ändrar du den extra autentiseringsmetoden](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [Så här hanterar du situationer som exempelvis en ny smartphone](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

Det viktigaste är att se till att dina anställda förstår ***när MFA-kravet kommer att införas*** så att de inte blir överraskade.

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>Steg 4. Distribuera kravet på MFA i din organisation eller till användarna

Distribuera multifaktorautentisering till de anställda utöver pilotanvändarna utifrån den metod du valt för MFA-kravet.

### <a name="security-defaults"></a>Standardinställningar för säkerhet

Du aktiverar eller inaktiverar säkerhetsinställningar för Azure Active Directory (Azure AD) i Microsoft Azure-portalen från fönstret **Egenskaper**.

1.  Logga in som global administratör på [Administrationscenter för Microsoft 365](https://admin.microsoft.com).
2.  Gå till sidan [Azure Active Directory – Egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3.  Längst ner på sidan väljer du **Hantera säkerhetsstandarder**.
4.  Välj **Ja** för att aktivera standardinställningar för säkerhet och **Nej** för att inaktivera dem och välj sedan **Spara**.

Om du har använt [originalprinciper för villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection) gör du så här för att gå över till att använda säkerhetsstandarder.

1.  Gå till sidan [principer för villkorsstyrd åtkomst](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2.  Välj alla originalprinciper som är **På** och ändra **Aktivera princip** till **Av**.
2.  Gå till sidan [Azure Active Directory – Egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4.  Längst ner på sidan väljer du **Hantera säkerhetsstandarder**.
5.  Välj **Ja** för att aktivera standardinställningar för säkerhet och **Nej** för att inaktivera dem och välj sedan **Spara**.

### <a name="conditional-access-policies"></a>Principer för villkorsstyrd åtkomst

Skapa, konfigurera och aktivera lämpliga principer som inkluderar den grupp användare som kräver MFA vid inloggning.

### <a name="per-user-mfa-not-recommended"></a>Multifaktorautentisering per användare (rekommenderas inte)

Aktivera användarkonton för MFA som motsvarar distributionen.

### <a name="supporting-your-employees"></a>Stöd till dina anställda

När dina medarbetare har registrerat sig och börjat logga in med MFA, behöver du se till att IT-experterna, IT-avdelningen och kundtjänsten kan besvara frågor och åtgärda problem snabbt.

I den här artikeln finns [information om hur du felsöker MFA-inloggning](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2). 


