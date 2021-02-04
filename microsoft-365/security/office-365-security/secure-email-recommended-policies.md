---
title: Rekommenderade principer för säker e-post – Microsoft 365 för företag| Microsoft Docs
description: Här beskrivs principer för Microsofts rekommendationer om hur du tillämpar e-postprinciper och konfigurationer.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 261c375aa17e4a3bc8f7d1b469d82621cf4ae45b
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097134"
---
# <a name="policy-recommendations-for-securing-email"></a>Principrekommendationer för att skydda e-post

I den här artikeln beskrivs hur du implementerar rekommenderade principer för identitets- och enhetsåtkomst för att skydda organisationens e-post- och e-postklienter som stöder modern autentisering och villkorsstyrd åtkomst. Den här vägledningen bygger på [principer för gemensamma identiteter och enhetsåtkomst](identity-access-policies.md) och innehåller också några ytterligare rekommendationer.

De här rekommendationerna baseras på tre olika nivåer av säkerhet och skydd som kan tillämpas utifrån dina behovs granularitet: **baslinje,** känslig och **mycket reglerad.** Du kan läsa mer om dessa säkerhetsnivåer och de rekommenderade klientoperativsystemet, som refereras av dessa rekommendationer i den rekommenderade introduktionen av säkerhetsprinciper [och konfigurationer.](microsoft-365-policies-configurations.md)

De här rekommendationerna kräver att användarna använder moderna e-postklienter, till exempel Outlook för iOS och Android på mobila enheter. Outlook för iOS och Android har stöd för de bästa funktionerna i Office 365. Outlook-mobilapparna är också uppbyggda med säkerhetsfunktioner som stöder mobil användning och samarbete med andra microsoft-molnsäkerhetsfunktioner. Mer information finns i vanliga frågor och svar om Outlook för [iOS och Android.](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)

## <a name="update-common-policies-to-include-email"></a>Uppdatera vanliga principer så att e-post inkluderas

För att skydda e-post illustrerar följande diagram vilka principer som ska uppdateras från de gemensamma principerna för identitets- och enhetsåtkomst.

[![Sammanfattning av principuppdateringar för att skydda åtkomsten till Teams och dess beroende tjänster](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

[Visa en större version av den här bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

Observera att det finns en ny princip för Exchange Online som blockerar ActiveSync-klienter. Det här tvingar fram användningen av Outlook Mobile.

Om du inkluderade Exchange Online och Outlook i omfattningen av principerna när du konfigurerade dem behöver du bara skapa den nya principen för att blockera ActiveSync-klienter. Granska principerna som visas i följande tabell och gör antingen de rekommenderade tilläggen eller bekräfta att dessa redan finns med. Varje princip länkar till de tillhörande konfigurationsanvisningarna i [Commons principer för identitets- och enhetsåtkomst.](identity-access-policies.md)

|Skyddsnivå|Principer|Mer information|
|---|---|---|
|**Grundläggande**|[Kräv MFA när inloggningsrisken är *medelhög* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Ta med Exchange Online i tilldelningen av molnappar|
||[Blockera klienter som inte har stöd för modern autentisering](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Ta med Exchange Online i tilldelningen av molnappar|
||[Använda principer för APP-dataskydd](identity-access-policies.md#apply-app-data-protection-policies)|Se till att Outlook ingår i listan med program. Se till att uppdatera principen för varje plattform (iOS, Android, Windows)|
||[Kräv godkända appar och APPskydd](identity-access-policies.md#require-approved-apps-and-app-protection)|Ta med Exchange Online i listan med molnappar|
||[Kräv kompatibla PC-datorer](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Ta med Exchange Online i listan med molnappar|
||[Blockera ActiveSync-klienter](#block-activesync-clients)|Lägg till den här nya principen|
|**Känslig**|[Kräv MFA när inloggningsrisken är *låg,* *medel* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Ta med Exchange Online i tilldelningen av molnappar|
||[Kräv kompatibla datorer *och* mobila enheter](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Ta med Exchange Online i listan med molnappar|
|**Strikt reglerad**|[*Kräv* alltid MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Ta med Exchange Online i tilldelningen av molnappar|
|

## <a name="block-activesync-clients"></a>Blockera ActiveSync-klienter

Den här principen förhindrar ActiveSync-klienter från att åsidosätta andra villkorsstyrda åtkomstprinciper. Principkonfigurationen gäller endast för ActiveSync-klienter. Genom att **[välja Kräv programskyddsprincip](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** blockerar den här principen ActiveSync-klienter. Information om hur du skapar den här principen finns i [Kräv programskyddsprincip för molnbaserad åtkomst med villkorsstyrd åtkomst.](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)

- Följ "Steg 2: Konfigurera en princip för villkorlig åtkomst i Azure AD för Exchange Online med ActiveSync (EAS)" i [Scenario 1: Office 365-appar](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)kräver godkända appar med appskyddsprinciper, vilket förhindrar att Exchange ActiveSync-klienter utnyttjar grundläggande autentisering från att ansluta till Exchange Online.

Du kan också använda autentiseringsprinciper för [att inaktivera grundläggande autentisering,](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)vilket tvingar alla klientåtkomstförfrågningar att använda modern autentisering.

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Begränsa åtkomsten till Exchange Online från Outlook på webben

Du kan begränsa möjligheten för användare att ladda ned bifogade filer från Outlook på webben på umnaged-enheter. Användare på dessa enheter kan visa och redigera filerna med hjälp av Office Online utan att det läcker ut och lagras på enheten. Du kan också blockera användare från att se bifogade filer på en ohanterad enhet.

Här är stegen:

1. [Ansluta till en Fjärr-PowerShell-session i Exchange Online.](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)
2. Om du inte redan har en OWA-postlådeprincip skapar du en med [cmdleten New-OwaMailboxPolicy.](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy)
3. Om du vill tillåta visning av bifogade filer men ingen nedladdning använder du det här kommandot:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. Om du vill blockera bifogade filer använder du det här kommandot:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. Skapa en ny princip för villkorsstyrd åtkomst i Azure-portalen med följande inställningar:

   **Uppgifter** \> **Användare och grupper:** Välj lämpliga användare och grupper som ska inkluderas eller undantas.

   **Uppgifter** \> **Molnappar eller -åtgärder** \> **Molnappar** \> **Inkludera** \> **Välj appar:** Välj **Office 365 Exchange Online**

   **Access-kontroller** \> **Session:** Välj **Använd appanvändningsbegränsningar**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>Kräv att iOS- och Android-enheter måste använda Outlook

För att säkerställa att användare av iOS- och Android-enheter bara kan komma åt arbets- eller skolinnehåll med Outlook för iOS och Android behöver du en princip för villkorsstyrd åtkomst som riktar dessa potentiella användare.

Se anvisningarna för hur du konfigurerar den här principen i Hantera åtkomst till samarbete via [meddelande med Hjälp av Outlook för iOS och Android.]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)

## <a name="set-up-message-encryption"></a>Konfigurera meddelandekryptering

Med de nya funktionerna för meddelandekryptering i Office 365 (OME), som utnyttjar skyddsfunktioner i Azure Information Protection, kan din organisation enkelt dela skyddad e-post med vem som helst på valfri enhet. Användare kan skicka och ta emot skyddade meddelanden med andra Microsoft 365-organisationer och icke-kunder som använder Outlook.com, Gmail och andra e-posttjänster.

Mer information finns i Konfigurera nya funktioner för meddelandekryptering i [Office 365.](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)

## <a name="next-steps"></a>Nästa steg

![Steg 4: Principer för Microsoft 365-molnappar](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurera villkorsstyrda åtkomstprinciper för:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
