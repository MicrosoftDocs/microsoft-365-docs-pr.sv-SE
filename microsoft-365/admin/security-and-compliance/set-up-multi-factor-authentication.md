---
title: Konfigurera multifaktorautentisering för användare
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
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
ms.openlocfilehash: 609f6d929408dd15ff6f296dc405448140726c89
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644849"
---
# <a name="set-up-multi-factor-authentication"></a>Konfigurera multifaktorautentisering
  
Eftersom du har kunskap om [multifaktorautentisering (MFA) och dess stöd i Microsoft 365](multi-factor-authentication-microsoft-365.md) är det dags att konfigurera och distribuera det i din organisation.

> [!IMPORTANT]
> Om du har köpt din prenumeration eller utvärderingsversion efter den 21 oktober 2019 och uppmanas att använda MFA när du loggar in, betyder det att [standardinställningar för säkerhet](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) har aktiverats automatiskt för prenumerationen.


## <a name="before-you-begin"></a>Innan du börjar

- Du måste vara en global administratör för att hantera MFA. Mer information finns i [Om administratörsroller](../add-users/about-admin-roles.md).
- Om du har aktiverat MFA arv per person, [inaktivera MFA arv per person](#turn-off-legacy-per-person-mfa).
- Om du har Office 2013-klienter på Windows-enheter kan du [aktivera modern autentisering för Office 2013-kunder](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).
- Avancerat: Om du har katalogtjänster från tredje part med Active Directory Federation Services (AD FS) konfigurerar du Microsoft Azure Multi-Factor Authentication-server. Mer information finns i [avancerade scenarier med Azure multifaktorautentisering och VPN-lösningar från tredje part](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn).

## <a name="turn-security-defaults-on-or-off"></a>Aktivera eller inaktivera standardinställningar för säkerhet

För de flesta organisationer tillhandahåller standardinställningar för säkerhet en god nivå av ytterligare inloggningssäkerhet. Mer information finns i [Vad är standardinställningar för säkerhet?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

Om prenumerationen är ny kan standardinställningar för säkerhet redan vara aktiverat för dig automatiskt.

Du aktiverar eller inaktiverar säkerhetsinställningar för Azure Active Directory (Azure AD) i Microsoft Azure-portalen från fönstret **Egenskaper**.

1.  Logga in som global administratör på [Administrationscenter för Microsoft 365](https://admin.microsoft.com).
2.  I det vänstra navigeringsfältet väljer du **Visa alla** och under **Administratörscenter**väljer du **Azure Active Directory**.
3. I **Azure Active Directory administratörscenter** väljer du **Azure Active Directory** > **Egenskaper**.
3.  Längst ner på sidan väljer du **Hantera standardinställningar för säkerhet**.
4.  Välj **Ja** för att aktivera standardinställningar för säkerhet eller **Nej** för att inaktivera dem och välj sedan **Spara**.

Om du har använt [originalprinciper för villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection) blir du ombedd att inaktivera dem innan du går över till att använda säkerhetsstandarder.

1.  Gå till sidan [principer för villkorsstyrd åtkomst](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2.  Välj alla originalprinciper som är **På** och ändra **Aktivera princip** till **Av**.
2.  Gå till sidan [Azure Active Directory – Egenskaper](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4.  Längst ner på sidan väljer du **Hantera säkerhetsstandarder**.
5.  Välj **Ja** för att aktivera standardinställningar för säkerhet och **Nej** för att inaktivera dem och välj sedan **Spara**.

## <a name="use-conditional-access-policies"></a>Använd principer för villkorsstyrd åtkomst

Om din organisation har mer detaljerade säkerhetsbehov kan villkorsstyrd åtkomst ge dig större kontroll. Med villkorsstyrd åtkomst kan du skapa och definiera principer som reagerar på att inloggningshändelser och begära ytterligare åtgärder innan en användare beviljas åtkomst till ett program eller en tjänst.

> [!IMPORTANT]
> Inaktivera både MFA och standardinställningar för säkerhet innan du aktiverar principer för villkorsstyrd åtkomst. 

Villkorsstyrd åtkomst är tillgänglig för kunder som har köpt Azure AD Premium P1, och licenser som inkluderar detta, t. ex. Microsoft 365 Business Premium och Microsoft 365 E3. Mer information finns i [skapa en princip för villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa).

Riskbaserad villkorlig åtkomst är tillgänglig via Azure AD Premium P2-licens eller licenser som inkluderar detta, till exempel Microsoft 365 E5. Mer information finns i [Riskbaserad villkorsstyrd åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk).

Mer information om Azure AD P1 och P2 finns i [Azure Active Directory-priserna](https://azure.microsoft.com/pricing/details/active-directory/).

### <a name="turn-on-modern-authentication-for-your-organization"></a>Aktivera modern autentisering för din organisation

För de flesta prenumerationer aktiveras modern autentisering automatiskt, men om du köpte prenumerationen för länge sedan, är den kanske inte det. Detta måste aktiveras innan MFA fungerar på rätt sätt med Office-appar.

1. I administrationscenter för Microsoft 365 väljer du **Inställningar** > **org-inställningar i det vänstra navigeringsfältet**.
1. Under **Tjänster** väljer du **Modern autentisering**och kontrollerar att **Aktivera modern autentisering** är markerad i fönstret **Modern autentisering**. Välj **Spara ändringar**.

### <a name="turn-off-legacy-per-person-mfa"></a>Inaktivera MFA arv per person

Om du tidigare har aktiverat MFA måste du inaktivera det innan du aktiverar standardinställningar för säkerhet.

1. I administrationscenter för Microsoft 365, in det vänstra navigeringsfältet, väljer du **Användare** > **Aktiva användare**. 
1. På sidan **Aktiva användare** väljer du **Multifaktorautentisering**.
1. På sidan multifaktorautentisering väljer du varje användare och konfigurerar deras multifaktorstatus till **Inaktiverad**.

## <a name="next-steps"></a>Nästa steg
- [Så här registrerar du dig för den extra autentiseringsmetoden](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [Vad är: multifaktorautentisering](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [Så här loggar du in efter registrering](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [Så här ändrar du den extra autentiseringsmetoden](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)





