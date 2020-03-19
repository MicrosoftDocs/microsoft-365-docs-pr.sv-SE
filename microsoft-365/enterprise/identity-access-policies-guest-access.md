---
title: Identitets- och enhetsåtkomstpolicyer för att tillåta gäst och extern B2B-åtkomst – Microsoft 365 Enterprise | Microsoft Dokument
description: Beskriver den rekommenderade villkorligåtkomst och relaterade principer för att skydda åtkomsten för gäst och externa användare.
author: BrendaCarter
manager: johmar
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 8276dcf85f6c5fd61e01e67deee4fea35c1a15c4
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42807657"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>Policyer för att tillåta gäst och extern B2B-åtkomst
I den här artikeln beskrivs hur du justerar de rekommenderade vanliga identitets- och enhetsåtkomstprinciperna så att B2B-kontoåtkomst (gäst och externa användare) kan justeras. Den här vägledningen bygger på principerna [för gemensam identitet och enhetsåtkomst](identity-access-policies.md).

Dessa rekommendationer är utformade för att gälla **för baslinjenivån** för skydd. Du kan dock justera rekommendationerna baserat på granulariteten i dina behov av **känsligt** och **starkt reglerat** skydd. 

Att tillhandahålla en sökväg för B2B-användare att autentisera med din Azure AD-klient ger inte dessa användare åtkomst till hela din miljö. B2B-användare har bara tillgång till resurser som delas med dem (t.ex. filer) inom de tjänster som beviljas i principerna för villkorsbehörighet.

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>Uppdatera de gemensamma principerna för att tillåta och skydda gäst och extern åtkomst 

Följande diagram illustrerar principerna för gemensam identitet och enhetsåtkomst och anger (med en pennikon) vilka principer som ska läggas till eller uppdateras för att skydda gäst och extern åtkomst. 

![Sammanfattning av principuppdateringar för att skydda gäståtkomst](../media/identity-access-ruleset-guest.png)

I följande tabell visas de principer som du antingen behöver uppdatera eller skapa nya. De gemensamma principerna länkar till de associerade konfigurationsinstruktionerna i artikeln [Gemensamma identitets- och enhetsåtkomstprinciper.](identity-access-policies.md)

|Skyddsnivå|Politik|Mer information|
|:---------------|:-------|:----------------|
|**Originalplan**|[Kräv MFA alltid för gäst- och externa användare](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Skapa den här nya regeln och tillämpa den endast för gäster och externa användare. Under inloggningsrisk lämnar du alla alternativ omarkerade för att alltid genomdriva MFA.|
|        |[Kräv MFA när inloggningsrisken är *medelhög* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Ändra den här regeln om du vill utesluta gästanvändare och externa användare.|
|        |[Kräv kompatibla datorer](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Ändra den här regeln om du vill utesluta gästanvändare och externa användare.|

Om du vill inkludera eller utesluta gäster och externa användare i regler för villkorlig åtkomst klickar du på fliken Inkludera eller uteslut och kontrollerar **Alla gäster och externa användare**.

![skärminspelning av kontroller för att utesluta gäster](../media/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Mer information

### <a name="guests-vs-external-users"></a>Gäster kontra externa användare
I Azure AD är gäst och externa användare desamma. Användartypen för båda dessa är Gäst. Gästanvändare är B2B-användare.

Microsoft Teams skiljer mellan gästanvändare och externa användare i appen, men dessa är båda B2B-användare när de autentiseras. Mer information om Teams-gäst och externa användare finns i [Aktivera gäst och extern åtkomst för Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).

### <a name="require-mfa-always-for-guest-and-external-users"></a>Kräv MFA alltid för gäst- och externa användare
Den här regeln uppmanar gästerna att registrera dig för MFA i din klientorganisation, oavsett om de är registrerade för MFA i sin hemklient. När du använder resurser i din klientmåste gäster och externa användare använda MFA för varje begäran. 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>Exklusive gäst- och externa användare från riskbaserad MFA
Organisationer kan tillämpa riskbaserade principer för B2B-användare som använder identitetsskydd, men det finns begränsningar i implementeringen av användare av identitetsskydd för B2B-samarbete i en resurskatalog på grund av deras identitet som finns i deras hem Katalog. På grund av dessa begränsningar rekommenderar Microsoft att du utesluter gästanvändare från riskbaserade MFA-principer och kräver att dessa användare alltid använder MFA. 

Mer information finns i [Begränsningar av identitetsskydd för B2B-samarbetsanvändare](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users). 

### <a name="excluding-guest-and-external-users-from-device-management"></a>Exklusive gäst- och externa användare från enhetshantering 
Endast en organisation kan hantera en enhet. Om du inte utesluter gästanvändare och externa användare från principer som kräver enhetsefterlevnad blockerar dessa principer dessa användare. 

## <a name="next-steps"></a>Nästa steg

[Läs om hur du aktiverar teams villkorlig åtkomst](teams-access-policies.md)

