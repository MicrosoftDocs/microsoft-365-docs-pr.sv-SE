---
title: Rekommenderade principer för säker e-post – Microsoft 365 Enterprise | Microsoft Dokument
description: I artikeln beskrivs principerna för Microsoft-rekommendationer om hur du tillämpar e-postprinciper och e-konfigurationer.
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
ms.openlocfilehash: aea95dae0165eb23331b2fa24d5fc752df3f4345
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810021"
---
# <a name="policy-recommendations-for-securing-email"></a>Policyrekommendationer för att skydda e-post

I den här artikeln beskrivs hur du implementerar de rekommenderade identitets- och enhetsåtkomstprinciperna för att skydda organisationse-e-postklienter som stöder modern autentisering och villkorlig åtkomst. Den här vägledningen bygger på principerna [för gemensam identitet och enhetsåtkomst](identity-access-policies.md) och innehåller även några ytterligare rekommendationer.

Dessa rekommendationer baseras på tre olika nivåer av säkerhet och skydd som kan tillämpas baserat på granulariteten hos dina behov: **baslinje,** **känslig**och **mycket reglerad**. Du kan läsa mer om dessa säkerhetsnivåer och de rekommenderade klientoperativsystemen, refererade av dessa rekommendationer i den [rekommenderade introduktionen av säkerhetsprinciper och konfigurationer](microsoft-365-policies-configurations.md).

Dessa rekommendationer kräver att användarna använder moderna e-postklienter, inklusive Outlook för iOS och Android på mobila enheter. Outlook för iOS och Android ger stöd för de bästa funktionerna i Office 365. Dessa mobilappar är också utformad med säkerhetsfunktioner som stöder mobil användning och fungerar tillsammans med andra microsoft-molnsäkerhetsfunktioner. Mer information finns i Vanliga frågor och [svar om Outlook för iOS och Android](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq).

## <a name="updating-common-policies-to-include-email"></a>Uppdatera gemensamma principer för att inkludera e-post

Följande diagram illustrerar principerna för gemensam identitet och enhetsåtkomst och anger vilka principer som behöver uppdateras för att skydda e-post. Observera tillägg av en ny regel för Exchange Online för att blockera ActiveSync-klienter. Detta tvingar användningen av Outlook mobile.

![Sammanfattning av principuppdateringar för att skydda e-post](../media/identity-access-ruleset-mail.png)

Om du inkluderade Exchange Online och Outlook i området för principerna när du konfigurerar dem behöver du bara skapa den nya principen för att blockera ActiveSync-klienter. Granska principerna i följande tabell och antingen göra de rekommenderade tilläggen eller bekräfta att dessa redan ingår. Varje regel länkar till de associerade konfigurationsinstruktionerna i artikeln [Gemensamma identitets- och enhetsåtkomstprinciper.](identity-access-policies.md)

|Skyddsnivå|Politik|Mer information|
|:---------------|:-------|:----------------|
|**Originalplan**|[Kräv MFA när inloggningsrisken är *medelhög* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera Exchange Online i tilldelningen av molnappar|
|        |[Blockera klienter som inte stöder modern autentisering](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Inkludera Exchange Online i tilldelningen av molnappar|
|        |[Definiera principer för appskydd](identity-access-policies.md#high-risk-users-must-change-password)|Se till att Outlook finns med i listan över appar. Var noga med att uppdatera principen för varje plattform (iOS, Android, Windows)|
|        |[Kräv godkända appar](identity-access-policies.md#require-approved-apps)|Inkludera Exchange Online i listan över molnappar|
|        |[Kräv kompatibla datorer](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Inkludera Exchange Online i listan över molnappar|
|        |[Blockera ActiveSync-klienter](#block-activesync-clients)|Lägg till den nya principen| 
|**Känsliga**|[Kräv MFA när inloggningsrisken är *låg,* *medelhög* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)| Inkludera Exchange Online i tilldelningen av molnappar|
|         |[Kräv kompatibla datorer *och* mobila enheter](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Inkludera Exchange Online i listan över molnappar|
|**Mycket reglerad**|[*Kräver alltid* MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera Exchange Online i tilldelningen av molnappar|

## <a name="block-activesync-clients"></a>Blockera ActiveSync-klienter

Den här principen förhindrar att ActiveSync-klienter kringgå andra regler för villkorlig åtkomst. Regelkonfigurationen gäller endast ActiveSync-klienter. Genom att välja **Kräv godkänd klientapp**blockerar den här principen ActiveSync-klienter. Så här konfigurerar du den här principen:

1. Gå till [Azure-portalen](https://portal.azure.com)och logga in med dina autentiseringsuppgifter. När du har loggat in visas Azure-instrumentpanelen.

2. Välj **Azure Active Directory** på den vänstra menyn.

3. Välj **Villkorsstyrd åtkomst**under avsnittet **Säkerhet** .

4. Välj **Ny princip**.

5. Ange ett principnamn och välj sedan de **användare och grupper** som du vill använda principen för.

6. Välj **Molnappar**.

7. Välj **Välj appar**och välj Office **365 Exchange Online**. Välj **Välj** och **klar**.

8. Välj **Villkor**och välj sedan **Klientappar**.

9. För **Konfigurera**väljer du **Ja**. Kontrollera bara följande: **Mobilappar och stationära klienter** och **Exchange ActiveSync-klienter**. Välj **Done**.

10. Välj **Bevilja** i avsnittet **Access-kontroller.**

11. Välj **Bevilja åtkomst**, välj **Kräv godkänd klientapp**.  För flera kontroller väljer du **Kräv de markerade kontrollerna**och väljer sedan **Välj**.

12. Välj **Skapa**.

## <a name="setup-office-365-message-encryption"></a>Kryptering av Office 365-meddelande

Med de nya OME-funktionerna (Office 365 Message Encryption), som utnyttjar skyddsfunktionerna i Azure Information Protection, kan din organisation enkelt dela skyddad e-post med vem som helst på vilken enhet som helst. Användare kan skicka och ta emot skyddade meddelanden med andra Office 365-organisationer samt icke-Office 365-kunder med hjälp av Outlook.com, Gmail och andra e-posttjänster.

Mer information finns i [Konfigurera nya office 365-funktioner för meddelandekryptering](https://support.office.com/article/set-up-new-office-365-message-encryption-capabilities-7ff0c040-b25c-4378-9904-b1b50210d00e).

## <a name="next-steps"></a>Nästa steg

[Läs mer om principrekommendationer för att skydda SharePoint-webbplatser och -filer](sharepoint-file-access-policies.md)
