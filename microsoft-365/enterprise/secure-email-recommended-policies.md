---
title: Säkra principer för rekommenderad e-post – Microsoft 365 Enterprise | Microsoft-dokument
description: I artikeln beskrivs policyerna för Microsofts rekommendationer om hur du tillämpar e-postprinciper och e-postkonfigurationer.
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
ms.openlocfilehash: dd35bf0d7439a19d7b1562e7a0d0681679b34c36
ms.sourcegitcommit: c079cc893cd1bd5d894b13814063a2f42238806e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/28/2020
ms.locfileid: "43035117"
---
# <a name="policy-recommendations-for-securing-email"></a>Policyrekommendationer för att skydda e-post

I den här artikeln beskrivs hur du implementerar de rekommenderade principerna för identitets- och enhetsåtkomst för att skydda organisationens e-post- och e-postklienter som stöder modern autentisering och villkorlig åtkomst. Den här vägledningen bygger på principerna [för gemensam identitet och enhetsåtkomst](identity-access-policies.md) och innehåller även några ytterligare rekommendationer.

Dessa rekommendationer baseras på tre olika nivåer av säkerhet och skydd som kan tillämpas baserat på de mest detaljerade behoven: **baslinje,** **känslig**och **starkt reglerad.** Du kan läsa mer om dessa säkerhetsnivåer och de rekommenderade klientoperativsystemen, som refereras av dessa rekommendationer i den rekommenderade introduktionen av [säkerhetsprinciper och konfigurationer](microsoft-365-policies-configurations.md).

Dessa rekommendationer kräver att användarna använder moderna e-postklienter, inklusive Outlook för iOS och Android på mobila enheter. Outlook för iOS och Android ger stöd för de bästa funktionerna i Office 365. Dessa mobila Outlook-appar är också arkitekterade med säkerhetsfunktioner som stöder mobilanvändning och fungerar tillsammans med andra Microsoft-molnsäkerhetsfunktioner. Mer information finns i [Vanliga frågor och svar om Outlook för iOS och Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).

## <a name="updating-common-policies-to-include-email"></a>Uppdatera vanliga principer så att de innehåller e-post

Följande diagram illustrerar de gemensamma principerna för identitet och enhetsåtkomst och anger vilka principer som behöver uppdateras för att skydda e-post. Observera tillägget av en ny regel för Exchange Online för att blockera ActiveSync-klienter. Detta tvingar användningen av Outlook mobile.

![Sammanfattning av principuppdateringar för att skydda e-post](../media/identity-access-ruleset-mail.png)

Om du inkluderade Exchange Online och Outlook i principernas omfattning när du konfigurerar dem behöver du bara skapa den nya principen för att blockera ActiveSync-klienter. Granska principerna i följande tabell och gör antingen de rekommenderade tilläggen eller bekräfta att dessa redan ingår. Varje regel länkar till tillhörande konfigurationsinstruktioner i artikeln [Gemensamma identitets- och enhetsåtkomstprinciper.](identity-access-policies.md)

|Skyddsnivå|Politik|Läs mer|
|:---------------|:-------|:----------------|
|**Baslinje**|[Kräv MFA när inloggningsrisken är *medelhög* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera Exchange Online i tilldelningen av molnappar|
|        |[Blockera klienter som inte stöder modern autentisering](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Inkludera Exchange Online i tilldelningen av molnappar|
|        |[Tillämpa APP-dataskyddsprinciper](identity-access-policies.md#apply-app-data-protection-policies)|Se till att Outlook ingår i listan över appar. Var noga med att uppdatera principen för varje plattform (iOS, Android, Windows)|
|        |[Kräv godkända appar och APP-skydd](identity-access-policies.md#require-approved-apps-and-app-protection)|Inkludera Exchange Online i listan över molnappar|
|        |[Kräv kompatibla datorer](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Inkludera Exchange Online i listan över molnappar|
|        |[Blockera ActiveSync-klienter](#block-activesync-clients)|Lägg till den här nya principen| 
|**Känslig**|[Kräv MFA när inloggningsrisken är *låg,* *medelhög* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| Inkludera Exchange Online i tilldelningen av molnappar|
|         |[Kräv kompatibla datorer *och* mobila enheter](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Inkludera Exchange Online i listan över molnappar|
|**Mycket reglerad**|[*Kräver alltid* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera Exchange Online i tilldelningen av molnappar|

## <a name="block-activesync-clients"></a>Blockera ActiveSync-klienter

Den här principen förhindrar att ActiveSync-klienter kringgår andra regler för villkorlig åtkomst. Regelkonfigurationen gäller endast ActiveSync-klienter. Genom att välja **[Kräv appskyddsprincip](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** blockerar den här principen ActiveSync-klienter. Information om hur du skapar den här principen finns i [Kräv appskyddsprincip för molnappåtkomst med villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Följ "Steg 2: Konfigurera en Azure AD-princip för villkorlig åtkomst för Exchange Online med ActiveSync (EAS)" i [Scenario 1: Office 365-appar kräver godkända appar med appskyddsprinciper](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), vilket förhindrar att Exchange ActiveSync-klienter utnyttjar grundläggande autentisering från att ansluta till Exchange Online.

## <a name="setup-office-365-message-encryption"></a>Konfigurera meddelandekryptering för Office 365

Med de nya ome-funktionerna (Message Encryption) för Office 365-meddelanden, som utnyttjar skyddsfunktionerna i Azure Information Protection, kan din organisation enkelt dela skyddad e-post med vem som helst på vilken enhet som helst. Användare kan skicka och ta emot skyddade meddelanden med andra Office 365-organisationer samt kunder som inte är Office 365-kunder med hjälp av Outlook.com, Gmail och andra e-posttjänster.

Mer information finns i [Konfigurera nya meddelandekrypteringsfunktioner för Office 365](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e).

## <a name="next-steps"></a>Nästa steg

[Lär dig mer om principrekommendationer för att skydda SharePoint-webbplatser och filer](sharepoint-file-access-policies.md)
