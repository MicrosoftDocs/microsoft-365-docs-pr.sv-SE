---
title: Identitets-och enhets åtkomst principer för att tillåta gäst och extern B2B-åtkomst-Microsoft 365 för företag | Microsoft-dok
description: Här beskrivs rekommenderade villkor för villkorlig åtkomst och relaterade principer för att skydda gäst-och externa användare.
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: c2c01278831433c02e5c869dba83f223eea57d27
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683241"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>Principer för att tillåta gäst-och extern B2B-åtkomst

I den här artikeln beskrivs hur du justerar de rekommenderade vanliga principer för identitets-och enhets åtkomst för att tillåta åtkomst för gäst och externa användare som har ett Azure Active Directory (Azure AD)-konto. Den här vägledningen bygger på [vanliga principer för identitets-och enhets åtkomst](identity-access-policies.md).

Dessa rekommendationer är avsedda att tillämpas på den **ursprungliga** skydds nivån. Men du kan också justera rekommendationerna baserat på hur många olika behov du har för **känsligt** och **starkt reglerat** skydd.

Om du tillhandahåller en sökväg för B2B-konton för att autentisera med din Azure AD-klient får inte dessa konton åtkomst till hela din miljö. B2B-användare och deras konton har till gång till resurser som delas med dem (till exempel filer) inom de tjänster som beviljats i principer för villkorsstyrd åtkomst.

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>Uppdatera vanliga principer för att tillåta och skydda gäst och extern åtkomst

För att skydda gäst-och extern åtkomst med Azure AD B2B-konton illustrerar följande diagram vilka principer du kan lägga till eller uppdatera från principer för åtkomst till gemensam identitet och enhet.

[![Sammanfattning av princip uppdateringar för att skydda gäst åtkomst](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[Visa en större version av bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

I följande tabell visas de principer som du måste skapa och uppdatera. Gemensamma principer-länken till de associerade konfigurations anvisningarna i artikeln om [principer för åtkomst policys för identitet och enheter](identity-access-policies.md) .

|Skydds nivå|Principerna|Mer information|
|---|---|---|
|**Grundläggande**|[Kräv MFA alltid för gäst-och externa användare](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Skapa den här nya principen och konfigurera: <ul><li> För **uppgifter > användare och grupper > inkludera** väljer **du Välj användare och grupper** och sedan **alla gäst-och externa användare**. </li><li> För **tilldelningar > villkor > inloggning** ska du låta alla alternativ vara avmarkerade så att multifaktorautentisering alltid används (MFA).</li>|
||[Kräv MFA när en inloggnings risk är *mellan* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Ändra den här principen så att den exkluderar gäst-och externa användare.|
||[Kräv kompatibla PC-datorer](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Ändra den här principen så att den exkluderar gäst-och externa användare.|

Om du vill inkludera eller exkludera gäst-och externa användare i principer för villkorsstyrd åtkomst för **uppgifter > användare och grupper > inkludera** eller **exkludera** markerar du **alla gäst-och externa användare**.

![skärm bild av kontroller för att exkludera gäst och externa användare](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Mer information

### <a name="guest-and-external-access-with-microsoft-teams"></a>Gäst och extern åtkomst med Microsoft Teams

Microsoft Teams definierar följande:

- **Gäst åtkomst** använder ett Azure AD B2B-konto som kan läggas till som medlem i ett team och få åtkomst till kommunikationen och resurserna i teamet.

- **Extern åtkomst** är för en extern användare som inte har ett B2B-konto. Extern åtkomst kan inkludera inbjudningar och deltagande i samtal, chattar och möten, men inte grupp medlemskap och åtkomst till teamens resurser.

Mer information finns i [jämförelsen mellan gäst och extern åtkomst för Teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).

Se [Policy rekommendationer för att skydda Teams, grupper och filer](teams-access-policies.md) för att få mer information om att skydda identitets-och enhets åtkomst principer för Teams.

### <a name="require-mfa-always-for-guest-and-external-users"></a>Kräv MFA alltid för gäst-och externa användare

Den här principen ber dig registrera gäster för MFA i klient organisationen, oavsett om de är registrerade för MFA i sin hem klient organisation. När du får åtkomst till resurser i klient organisationen måste gäst och externa användare använda MFA för varje begäran.

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>Exkluderar gäst och externa användare från riskfyllda MFA

Trots att organisationer kan använda riskbaserade principer för B2B-användare som använder Azure AD Identity Protection finns det begränsningar i implementeringen av Azure AD Identity Protection för B2B-samarbets användare i en resurs katalog på grund av deras identitet i sin Hem Katalog. På grund av dessa begränsningar rekommenderar Microsoft att du exkluderar gäst användare från riskfyllda principer och kräver att dessa användare alltid använder MFA.

Mer information finns i [begränsningar för identitets skydd för B2B-samarbets användare](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).

### <a name="excluding-guest-and-external-users-from-device-management"></a>Exkludera gäst-och externa användare från enhets hantering

Endast en organisation kan hantera en enhet. Om du inte utesluter gäst-och externa användare från principer som kräver att enheter efterlevs blockerar dessa användare.

## <a name="next-step"></a>Nästa steg

![Steg 4: principer för Microsoft 365-molnappar](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurera principer för villkorsstyrd åtkomst för:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
