---
title: Konfigurera principer för villkorsstyrd åtkomst
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig att kräva MFA och konfigurera villkorsstyrda åtkomstprinciper för Microsoft 365 för företag.
ms.openlocfilehash: dcb79ed060dd15fd288cdcfb9e3739a788f5fbc2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912192"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>Kräv multifaktorautentisering och konfigurera principer för villkorsstyrd åtkomst

Du skyddar åtkomsten till dina data med principer för multifaktorautentisering och villkorsstyrd åtkomst. Dessa ger betydande ytterligare säkerhet. Microsoft tillhandahåller en uppsättning grundläggande principer för villkorsstyrd åtkomst som rekommenderas för alla kunder. Grundläggande principer är en uppsättning fördefinierade principer som hjälper till att skydda organisationer mot många vanliga attacker. Dessa vanliga attacker kan vara lösenordsattacker, uppspelning och nätfiske.

De här principerna kräver att administratörer och användare anger en andra form av autentisering (kallas multifaktorautentisering eller MFA) under vissa förhållanden. Om en användare i organisationen till exempel försöker logga in på Microsoft 365 från ett annat land eller från en okänd enhet kan inloggningen anses vara riskabel. Användaren måste tillhandahålla extra autentisering (till exempel ett fingeravtryck eller en kod) för att bevisa sin identitet.

För närvarande innehåller baslinjeprinciperna följande principer:

- Konfigurera i administrationscentret för Microsoft 365:
  - **Kräv MFA för administratörer: Kräver** multifaktorautentisering för de mest privilegierade administratörsrollerna, inklusive global administratör.
  - **Slutanvändarskydd:** Kräver multifaktorautentisering för användare endast om en inloggning är riskabel. 
- Konfigurera i Azure Active Directory-portalen:
  - **Blockera äldre autentisering:** Äldre klientappar och vissa nya program använder inte nyare, säkrare och autentiseringsprotokoll. Dessa äldre appar kan kringgå villkorsstyrda åtkomstprinciper och få obehörig åtkomst till din miljö. Den här principen blockerar åtkomst från klienter som inte stöder villkorsstyrd åtkomst. 
  - **Kräv MFA för tjänsthantering:** Kräver multifaktorautentisering för åtkomst till hanteringsverktyg, inklusive Azure-portalen (där du konfigurerar baslinjeprinciper).

Vi rekommenderar att du aktiverar alla dessa baslinjeprinciper. När dessa principer har aktiverats uppmanas administratörer och användare att registrera sig för Azure AD-multifaktorautentisering.

Mer information om dessa principer finns i Vad [är grundläggande principer](/azure/active-directory/conditional-access/concept-baseline-protection)?

## <a name="require-mfa"></a>Kräv MFA

Så här kräver du att alla användare loggar in med en andra typ av ID:

1. Gå till administrationscentret och <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> välj **Inställningar.**

2. På sidan Inställningar väljer du **Visa** på **kortet Gör inloggningen säkrare.**

    ![Gör inloggningen säkrare.](../media/setupmfa.png)
3. På sidan Gör inloggningen säkrare väljer du **Komma igång.**

4. I fönstret Förstärka inloggningssäkerhet markerar du kryssrutorna bredvid Kräv multifaktorautentisering för administratörer och Kräv att användare registrerar sig för multifaktorautentisering och blockerar åtkomst om **risken identifieras**. 
    Se till att utesluta [nödsituations-](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) eller "break-glass"-administratörskontot från MFA-kravet i **rutan Hitta** användare.

    ![Förstärka säkerhetssidan.](../media/requiremfa.png)

5. Välj **Skapa** princip längst ned på sidan.

## <a name="set-up-baseline-policies"></a>Konfigurera baslinjeprinciper

1. Gå till [Azure-portalen och](https://portal.azure.com)gå sedan till Villkorsstyrd åtkomst till **Azure Active Directory-säkerhet** \>  \>  för att skapa en **ny princip.**

Se följande specifika instruktioner för varje princip: <br>
    - [Kräv MFA för administratörer](/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [Kräv MFA för användare](/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [Blockera äldre autentisering](/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [Kräv MFA för tjänsthantering](/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> Förhandsgranskningsprinciper finns inte längre och användarna måste skapa egna principer.

Du kan konfigurera extra principer, till exempel krav på godkända klientprogram. Mer information finns i dokumentationen [för villkorsstyrd åtkomst.](/azure/active-directory/conditional-access/)