---
title: Säkra e-postprinciper – Microsoft 365 Enterprise | Microsoft-dok
description: Beskriver policyerna för Microsoft-rekommendationer om hur du använder e-postprinciper och konfigurationer.
author: brendacarter
manager: laurawi
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
- remotework
ms.openlocfilehash: c2eabd160cf221f7e2bb7b81f07c205135476cc9
ms.sourcegitcommit: d6b641d0ef92f4176da9f4a98d3d5aa3d4f2e184
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/11/2020
ms.locfileid: "46617180"
---
# <a name="policy-recommendations-for-securing-email"></a>Policy rekommendationer för att skydda e-post

I den här artikeln beskrivs hur du implementerar de rekommenderade principer för identitet och enheter för att skydda organisatoriska e-post-och e-postklienter som stöder modern och villkorlig åtkomst. Den här vägledningen bygger på den [vanliga policyn för identitets-och enhets åtkomst](identity-access-policies.md) och innehåller dessutom ytterligare några rekommendationer.

Dessa rekommendationer är baserade på tre olika nivåer av säkerhet och skydd som kan användas baserat på hur olika behov fungerar: **bas linje**, **känslig**och **högreglerad**. Du kan läsa mer om de här säkerhets nivåerna och de rekommenderade klient operativ systemen som hänvisas till av de här rekommendationerna i de [rekommenderade säkerhets reglerna och konfigurationerna](microsoft-365-policies-configurations.md).

Dessa rekommendationer kräver att användarna använder moderna e-postklienter, inklusive Outlook för iOS och Android på mobila enheter. Outlook för iOS och Android tillhandahåller stöd för de bästa funktionerna i Office 365. Dessa mobila Outlook-appar är också utformad med säkerhets funktioner som har stöd för mobil användning och arbetar tillsammans med andra säkerhets funktioner för Microsoft Cloud. Mer information finns i [vanliga frågor om Outlook för iOS och Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).

## <a name="updating-common-policies-to-include-email"></a>Uppdatera gemensamma principer för att inkludera e-post

Följande diagram illustrerar den vanliga principer för identitets-och enhets åtkomst och visar vilka principer som måste uppdateras för att skydda e-post. Observera tillägget av en ny regel för Exchange Online för att blockera ActiveSync-klienter. Detta framtvingar användning av Outlook Mobile.

![Sammanfattning av princip uppdateringar för att skydda e-post](../media/identity-access-ruleset-mail.png)

[Visa en större version av bilden](https://raw.githubusercontent.com/MicrosoftDocs/microsoft-365-docs/public/microsoft-365/media/identity-access-ruleset-mail.png)

Om du har inkluderat Exchange Online och Outlook enligt principernas omfattning när du ställer in dem behöver du bara skapa den nya principen för att blockera ActiveSync-klienter. Granska de principer som visas i tabellen nedan och gör de rekommenderade tilläggen, eller bekräfta att dessa redan är med. Varje regel länkar till de associerade konfigurations anvisningarna i artikeln om [åtkomst principer för allmänna identiteter och enheter](identity-access-policies.md) .

|Skydds nivå|Principerna|Mer information|
|:---------------|:-------|:----------------|
|**Grundläggande**|[Kräv MFA när en inloggnings risk är *mellan* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera Exchange Online i tilldelning av moln program|
|        |[Blockera klienter som inte har stöd för modern autentisering](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Inkludera Exchange Online i tilldelning av moln program|
|        |[Tillämpa program data skydds policy](identity-access-policies.md#apply-app-data-protection-policies)|Kontrol lera att Outlook ingår i listan med program. Se till att uppdatera policyn för varje plattform (iOS, Android, Windows)|
|        |[Kräv godkända appar och program skydd](identity-access-policies.md#require-approved-apps-and-app-protection)|Ta med Exchange Online i listan med moln program|
|        |[Kräv kompatibla PC-datorer](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Ta med Exchange Online i listan över moln program|
|        |[Blockera ActiveSync-klienter](#block-activesync-clients)|Lägg till den här nya principen| 
|**Känslig**|[Kräv MFA när en inloggnings risk är *låg*, *medium* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| Inkludera Exchange Online i tilldelning av moln program|
|         |[Kräv kompatibla datorer *och* mobila enheter](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Ta med Exchange Online i listan med moln program|
|**Strikt reglerad**|[Kräv *alltid* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera Exchange Online i tilldelning av moln program|

## <a name="block-activesync-clients"></a>Blockera ActiveSync-klienter

Den här principen hindrar ActiveSync-klienter från att kringgå andra regler för villkorlig åtkomst. Regel konfigurationen gäller endast för ActiveSync-klienter. Om du väljer **[Kräv program skydds princip](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** spärrar den här principen ActiveSync-klienter. Information om hur du skapar den här principen finns i [Kräv program skydds princip för Cloud App Access med villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Följ anvisningarna i "steg 2: Konfigurera en princip för villkorsstyrd åtkomst för Azure AD för Exchange Online med ActiveSync (EAS)" i [Scenario 1: Office 365-appar kräver godkända appar med program skydds principer](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), som hindrar Exchange ActiveSync-klienterna från att ansluta till Exchange Online.

## <a name="set-up-message-encryption"></a>Konfigurera meddelande kryptering

Med de nya funktionerna för Office 365 Message Encryption (OME), som utnyttjar skydds funktionerna i Azure information Protection, kan din organisation enkelt dela skyddat e-postmeddelande med alla på valfri enhet. Användare kan skicka och ta emot skyddade meddelanden med andra Microsoft 365-organisationer samt icke-kunder som använder Outlook.com, Gmail och andra e-posttjänster.

Mer information finns i [Konfigurera nya funktioner för kryptering av Office 365-meddelanden](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities).

## <a name="next-steps"></a>Nästa steg

[Lär dig mer om policy rekommendationer för att skydda SharePoint-webbplatser och-filer](sharepoint-file-access-policies.md)
