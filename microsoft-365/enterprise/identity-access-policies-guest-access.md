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
ms.openlocfilehash: ad1203543db1c2bd0ea9e9bdd3433aad58db320b
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898110"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>Principer för att tillåta gäst-och extern B2B-åtkomst
I den här artikeln beskrivs hur du justerar de rekommenderade vanliga principer för identitet och enheter för att tillåta B2B-konto åtkomst (gäst-och externa användare). Den här vägledningen bygger på [vanliga principer för identitets-och enhets åtkomst](identity-access-policies.md).

Dessa rekommendationer är avsedda att tillämpas på den **ursprungliga** skydds nivån. Men du kan ändra rekommendationerna baserat på hur **känsligt** och **starkt reglerade** skydd du behöver. 

Om du tillhandahåller en sökväg för B2B-användare som autentiseras med din Azure AD-klient ger dessa användare åtkomst till hela din miljö. B2B-användare har till gång till resurser som delas med dem (till exempel filer) inom de tjänster som beviljats i principer för villkorlig åtkomst.

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>Uppdatera vanliga principer för att tillåta och skydda gäst och extern åtkomst 

I följande diagram visas den vanliga policyn för identitets-och enhets åtkomst och visar (med en penna-ikon) vilka principer som du kan använda för att lägga till eller uppdatera för att skydda gäst och extern åtkomst. 

![Sammanfattning av princip uppdateringar för att skydda gäst åtkomst](../media/identity-access-ruleset-guest.png)

I följande tabell visas de principer som du måste uppdatera eller skapa nya. Gemensamma principer-länken till de associerade konfigurations anvisningarna i artikeln om [principer för åtkomst policys för identitet och enheter](identity-access-policies.md) .

|Skydds nivå|Principerna|Mer information|
|:---------------|:-------|:----------------|
|**Grundläggande**|[Kräv MFA alltid för gäst-och externa användare](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Skapa den nya regeln och Använd den bara för gäster och externa användare. Låt alla alternativ vara avmarkerade om du inte vill använda MFA.|
|        |[Kräv MFA när en inloggnings risk är *mellan* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Ändra regeln så att den exkluderar gäst-och externa användare.|
|        |[Kräv kompatibla PC-datorer](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Ändra regeln så att den exkluderar gäst-och externa användare.|

Om du vill inkludera eller exkludera gäster och externa användare i regler för villkorsstyrd åtkomst klickar du på fliken inkludera eller exkludera och markerar **alla gäster och externa användare**.

![skärm bild av kontroller för att exkludera gäster](../media/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Mer information

### <a name="guests-vs-external-users"></a>Gäster kontra externa användare
I Azure AD är gäst och externa användare desamma. Användar typen för båda dessa är gäster. Gäst användare är B2B-användare.

Microsoft Teams skiljer sig mellan gäst användare och externa användare inom programmet, men dessa båda är båda B2B-användare vid autentisering. Mer information om Teams gäst och externa användare finns i [Aktivera gäst och extern åtkomst till Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).

### <a name="require-mfa-always-for-guest-and-external-users"></a>Kräv MFA alltid för gäst-och externa användare
Den här regeln ber dig registrera sig för MFA i klient organisationen, oavsett om de är registrerade för MFA i sin hem klient organisation. När du får åtkomst till resurser i klient organisationen måste gäster och externa användare använda MFA för varje begäran. 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>Exkluderar gäst och externa användare från riskfyllda MFA
Även om organisationer kan tvinga fram riskbaserade principer för B2B-användare som använder identitets skydd finns det begränsningar i implementeringen av identitets skydd för B2B-samarbets användare i en resurs katalog på grund av deras identitet i sin Hem Katalog. På grund av dessa begränsningar rekommenderar Microsoft att du exkluderar gäst användare från riskfyllda principer och kräver att dessa användare alltid använder MFA. 

Mer information finns i [begränsningar för identitets skydd för B2B-samarbets användare](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users). 

### <a name="excluding-guest-and-external-users-from-device-management"></a>Exkludera gäst-och externa användare från enhets hantering 
Endast en organisation kan hantera en enhet. Om du inte utesluter gäst-och externa användare från principer som kräver att enheter efterlevs blockerar dessa användare. 

## <a name="next-steps"></a>Nästa steg

[Lär dig hur du aktiverar Teams villkorlig åtkomst](teams-access-policies.md)

