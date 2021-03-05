---
title: Konfigurera villkorsstyrda åtkomstprinciper
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
description: Lär dig hur du kräver MFA och konfigurera villkorsstyrda åtkomstprinciper för Microsoft 365 för företag.
ms.openlocfilehash: e16b7f4ff7d215ee749435806be214a807cc60a4
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453675"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>Kräv multifaktorautentisering och konfigurera villkorsstyrda åtkomstprinciper

Du skyddar åtkomsten till dina data med principer för multifaktorautentisering och villkorsstyrd åtkomst. Dessa ger betydande ytterligare säkerhet. Microsoft tillhandahåller en uppsättning grundläggande villkorsstyrda åtkomstprinciper som rekommenderas för alla kunder. Baslinjeprinciper är en uppsättning fördefinierade principer som hjälper till att skydda organisationer mot många vanliga attacker. Dessa vanliga attacker kan vara lösenordsattacker, uppspelning och nätfiske.

Dessa principer kräver att administratörer och användare anger en andra form av autentisering (kallas multifaktorautentisering eller MFA) under vissa förhållanden. Om en användare i organisationen till exempel försöker logga in på Microsoft 365 från ett annat land eller från en okänd enhet kan inloggningen vara riskabel. Användaren måste tillhandahålla en extra autentiseringsform (t.ex. fingeravtryck eller kod) för att bevisa sin identitet.

För närvarande innehåller baslinjeprinciperna följande principer:

- Konfigurera i administrationscentret för Microsoft 365:
  - **Kräv MFA för administratörer: Kräver** multifaktorautentisering för de mest behöriga administratörsrollerna, inklusive global administratör.
  - **Slutanvändarskydd:** Kräver multifaktorautentisering för användarna endast när en inloggning är riskabel. 
- Konfigurera i Azure Active Directory-portalen:
  - **Blockera äldre autentisering:** Äldre klientappar och vissa nya program använder inte nyare, säkrare autentiseringsprotokoll. Dessa äldre appar kan kringgå villkorsstyrda åtkomstprinciper och få obehörig åtkomst till din miljö. Den här principen blockerar åtkomst från klienter som inte stöder villkorsstyrd åtkomst. 
  - **Kräv MFA för tjänsthantering:** Kräver multifaktorautentisering för åtkomst till hanteringsverktyg, inklusive Azure-portalen (där du konfigurerar baslinjeprinciper).

Vi rekommenderar att du aktiverar alla dessa baslinjeprinciper. När dessa principer har aktiverats uppmanas administratörer och användare att registrera sig för Azure AD Multifaktorautentisering.

Mer information om dessa principer finns i Vad [är baslinjeprinciper?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)

## <a name="require-mfa"></a>Kräv MFA

Så här kräver du att alla användare loggar in med en andra form av ID:

1. Gå till administrationscentret och <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> välj **Installation.**

2. Välj Visa i **inloggningskortet** för **att göra inloggningen** säkrare på sidan Inställningar.

    ![Gör inloggningskortet säkrare.](../media/setupmfa.png)
3. Välj Kom igång på sidan Gör **inloggningen säkrare.**

4. I fönstret Förstärka **inloggningssäkerhet** markerar du kryssrutorna bredvid Kräv multifaktorautentisering för administratörer och Kräv att användare registrerar sig för multifaktorautentisering och blockera åtkomst om **risker identifieras.**
    Se till att utesluta det [akuta](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) administratörskontot eller "break-glass"-administratörskontot från MFA-kravet i **rutan Hitta** användare.

    ![Förstärka säkerhetssidan.](../media/requiremfa.png)

5. Välj **Skapa princip** längst ned på sidan.

## <a name="set-up-baseline-policies"></a>Konfigurera baslinjeprinciper

1. Gå till [Azure-portalen och](https://portal.azure.com)gå sedan till villkorsstyrd åtkomst för **Azure Active** \>  \> **Directory-säkerhet** för att skapa **en ny princip.**

Se följande specifika anvisningar för varje princip: <br>
    - [Kräv MFA för administratörer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [Kräv MFA för användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [Blockera äldre autentisering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [Kräv MFA för tjänsthantering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> Förhandsgranskningsprinciperna finns inte längre och användarna måste skapa sina egna principer.

Du kan konfigurera extra principer, till exempel krav på godkända klientprogram. Mer information finns i dokumentationen för [villkorsstyrd åtkomst.](https://docs.microsoft.com/azure/active-directory/conditional-access/)
