---
title: Rekommenderade principer för säker e-post – Microsoft 365 för företag | Microsoft Docs
description: Här beskrivs principer för Microsofts rekommendationer om hur du använder e-postprinciper och konfigurationer.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
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
ms.openlocfilehash: 9a47789c48fa35335430d342948dfdad1b32e7bf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917338"
---
# <a name="policy-recommendations-for-securing-email"></a>Principrekommendationer för att skydda e-post

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)


I den här artikeln beskrivs hur du implementerar rekommenderade principer för identitets- och enhetsåtkomst för att skydda organisationens e-post- och e-postklienter som stöder modern autentisering och villkorsstyrd åtkomst. Den här vägledningen bygger på [gemensamma principer för identitet och enhetsåtkomst](identity-access-policies.md) och innehåller också några ytterligare rekommendationer.

Dessa rekommendationer baseras på tre olika nivåer av säkerhet och skydd som kan tillämpas utifrån detaljnivån för dina behov: **baslinje,** känslig och **mycket reglerad**. Du kan läsa mer om dessa säkerhetsnivåer och de rekommenderade klientoperativsystemet, som refereras av dessa rekommendationer i introduktionen till rekommenderade [säkerhetsprinciper och konfigurationer.](microsoft-365-policies-configurations.md)

De här rekommendationerna kräver att användarna använder moderna e-postklienter, inklusive Outlook för iOS och Android på mobila enheter. Outlook för iOS och Android har stöd för de bästa funktionerna i Office 365. De här outlook-mobilapparna är också uppbyggda av säkerhetsfunktioner som stöder mobil användning och fungerar tillsammans med andra molnsäkerhetsfunktioner i Microsoft. Mer information finns i Vanliga frågor och svar om Outlook för [iOS och Android.](/exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android-faq)

## <a name="update-common-policies-to-include-email"></a>Uppdatera vanliga principer så att e-post inkluderas

I följande diagram visas vilka principer som ska uppdateras från de gemensamma principerna för identitets- och enhetsåtkomst för att skydda e-post.

[![Sammanfattning av principuppdateringar för att skydda åtkomsten till Teams och dess beroende tjänster](../../media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-mail.png)

Observera tillägget av en ny princip för Exchange Online för att blockera ActiveSync-klienter. Det här tvingar fram användningen av Outlook Mobile.

Om du inkluderade Exchange Online och Outlook i omfattningen av principerna när du konfigurerade dem behöver du bara skapa den nya principen för att blockera ActiveSync-klienter. Granska principerna som visas i följande tabell och gör antingen de rekommenderade tilläggen eller bekräfta att dessa redan finns med. Varje princip länkar till de associerade konfigurationsanvisningarna i [Vanliga principer för identitets- och enhetsåtkomst.](identity-access-policies.md)

|Skyddsnivå|Principer|Mer information|
|---|---|---|
|**Grundläggande**|[Kräv MFA när inloggningsrisken är *medium* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera Exchange Online när du ska använda molnappar|
||[Blockera klienter som inte har stöd för modern autentisering](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Inkludera Exchange Online när du ska använda molnappar|
||[Använda principer för APP-dataskydd](identity-access-policies.md#apply-app-data-protection-policies)|Se till att Outlook ingår i listan med program. Se till att uppdatera principen för varje plattform (iOS, Android, Windows)|
||[Kräv godkända appar och appskydd](identity-access-policies.md#require-approved-apps-and-app-protection)|Ta med Exchange Online i listan med molnappar|
||[Kräv kompatibla PC-datorer](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Ta med Exchange Online i listan över molnappar|
||[Blockera ActiveSync-klienter](#block-activesync-clients)|Lägg till den här nya principen|
|**Känslig**|[Kräv MFA när inloggningsrisken är *låg,* *medelstor* eller *hög*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera Exchange Online när du ska använda molnappar|
||[Kräv kompatibla datorer *och* mobila enheter](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Ta med Exchange Online i listan med molnappar|
|**Strikt reglerad**|[*Kräv* alltid MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Inkludera Exchange Online när du ska använda molnappar|
|

## <a name="block-activesync-clients"></a>Blockera ActiveSync-klienter

Den här principen förhindrar att ActiveSync-klienter kringgår andra villkorsstyrda åtkomstprinciper. Principkonfigurationen gäller endast För ActiveSync-klienter. Genom att **[välja Kräv appskyddsprincip](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)** blockerar den här principen ActiveSync-klienter. Information om hur du skapar den här principen finns i [Kräv programskyddsprincip för molnbaserad appåtkomst med villkorsstyrd åtkomst.](/azure/active-directory/conditional-access/app-protection-based-conditional-access)

- Följ "Steg 2: Konfigurera en villkorsbaserad åtkomstprincip för Azure AD för Exchange Online med ActiveSync (EAS)" i [Scenario 1: Office 365-appar](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)kräver godkända appar med appskyddsprinciper, vilket förhindrar att Exchange ActiveSync-klienter utnyttjar grundläggande autentisering från att ansluta till Exchange Online.

Du kan också använda autentiseringsprinciper för att [inaktivera grundläggande](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)autentisering, som tvingar alla klientåtkomstförfrågningar att använda modern autentisering.

## <a name="limit-access-to-exchange-online-from-outlook-on-the-web"></a>Begränsa åtkomsten till Exchange Online från Outlook på webben

Du kan begränsa möjligheten för användare att ladda ned bifogade filer från Outlook på webben på umnagerade enheter. Användare på dessa enheter kan visa och redigera filerna med hjälp av Office Online utan att läcka och lagra filerna på enheten. Du kan också blockera användare från att se bifogade filer på en ohanterad enhet.

Här är stegen:

1. [Ansluta till en Fjärrsession i PowerShell för Exchange Online.](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)
2. Om du inte redan har en OWA-postlådeprincip skapar du en med cmdleten [New-OwaMailboxPolicy.](/powershell/module/exchange/new-owamailboxpolicy)
3. Om du vill tillåta visning av bifogade filer men ingen nedladdning kan du använda det här kommandot:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnly
   ```

4. Använd det här kommandot om du vill blockera bifogade filer:

   ```powershell
   Set-OwaMailboxPolicy -Identity Default -ConditionalAccessPolicy ReadOnlyPlusAttachmentsBlocked
   ```

5. Skapa en ny princip för villkorsstyrd åtkomst i Azure-portalen med följande inställningar:

   **Uppgifter** \> **Användare och grupper:** Välj lämpliga användare och grupper som ska inkluderas och exkluderas.

   **Uppgifter** \> **Molnappar eller -åtgärder** \> **Molnappar** \> **Inkludera** \> **Välj appar:** Välj **Office 365 Exchange Online**

   **Access-kontroller** \> **Session:** Välj **Använd apptvingade begränsningar**

## <a name="require-that-ios-and-android-devices-must-use-outlook"></a>Kräv att iOS- och Android-enheter måste använda Outlook

Om du vill säkerställa att användare av iOS- och Android-enheter bara kan komma åt arbets- eller skolinnehåll med Outlook för iOS och Android behöver du en princip för villkorsstyrd åtkomst som riktar sig till dessa potentiella användare.

Se anvisningarna för hur du konfigurerar principen i [Hantera åtkomst till samarbete via meddelanden med Outlook för iOS och Android.]( https://docs.microsoft.com/mem/intune/apps/app-configuration-policies-outlook#apply-conditional-access)

## <a name="set-up-message-encryption"></a>Konfigurera meddelandekryptering

Med de nya funktionerna för meddelandekryptering i Office 365 (OME), som utnyttjar skyddsfunktioner i Azure Information Protection, kan din organisation enkelt dela skyddad e-post med vem som helst på valfri enhet. Användare kan skicka och ta emot skyddade meddelanden med andra Microsoft 365-organisationer och icke-kunder som använder Outlook.com, Gmail och andra e-posttjänster.

Mer information finns i Konfigurera [nya funktioner för meddelandekryptering i Office 365.](../../compliance/set-up-new-message-encryption-capabilities.md)

## <a name="next-steps"></a>Nästa steg

![Steg 4: Principer för Microsoft 365-molnappar](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Konfigurera principer för villkorsstyrd åtkomst för:

- [Microsoft Teams](teams-access-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)