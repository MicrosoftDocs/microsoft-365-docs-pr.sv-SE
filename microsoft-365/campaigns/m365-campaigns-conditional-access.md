---
title: Konfigurera regler för villkorsstyrd åtkomst
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
description: Lär dig hur du begär MFA och konfigurerar principer för villkorsstyrd åtkomst för Microsoft 365 för företag.
ms.openlocfilehash: 08a77615d6801eef52465c450c2559a9d786befb
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558280"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>Kräv multifaktorautentisering och konfigurera principer för villkorsstyrd åtkomst

Du skyddar åtkomsten till dina data med principer för multifaktorautentisering och villkorsstyrd åtkomst. Dessa tillägg till ökad säkerhet. Microsoft tillhandahåller en uppsättning principer för villkorsstyrd åtkomst enligt grundläggande som rekommenderas för alla kunder. Rikt linjer är en uppsättning fördefinierade principer som hjälper till att skydda organisationer mot många vanliga angrepp. Dessa vanliga angrepp kan inkludera lösen ord, Replay och nätfiske.

Dessa principer kräver att administratörer och användare anger en andra form av autentiseringsprocessen (kallas multifaktorautentisering) när vissa villkor uppfylls. Om en användare i din organisation till exempel försöker logga in på Microsoft 365 från ett annat land eller från en okänd enhet kan inloggningen betraktas som riskfylld. Användaren måste tillhandahålla en extra form av auktorisering (till exempel ett finger avtryck eller en kod) för att bevisa sin identitet. 

För närvarande inkluderar grundläggande principer följande:
- Konfigurera i Microsoft 365 Admin Center:
    - **KRÄV MFA för administratörer** – kräver multifaktorautentisering för de mest privilegierade administratörs rollerna, inklusive global administratör.
    - **Slutanvändarens skydd** – kräver multifaktorautentisering för användare endast när en inloggning är riskabel. 
- Konfigurera i Azure Active Directory-portalen:
    - **Blockera äldre verifierare** – äldre klient program och vissa nya appar använder inte nyare, säkrare autentiseringsprotokoll. Dessa äldre appar kan kringgå villkorsstyrda åtkomst principer och få obehörig åtkomst till din miljö. Denna princip blockerar åtkomst från klienter som inte stöder villkorlig åtkomst. 
    - **KRÄV MFA för tjänst hantering** – kräver multifaktorautentisering för åtkomst till hanterings verktyg, inklusive Azure Portal (där du konfigurerar rikt linjer för principer). 

Microsoft rekommenderar att du aktiverar alla dessa rikt linjer. När dessa principer är aktiverade uppmanas administratörer och användare att registrera dig för multifaktorautentisering med Azure AD.

Mer information om dessa principer finns i [Vad är rikt linjer](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?


## <a name="require-mfa"></a>Kräv MFA

Om du vill att alla användare ska logga in med en andra form av ID:

1. Gå till administrations centret på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> och välj **installation**.

2. På sidan Inställningar väljer du **Visa** i det **säkra kortet gör inloggning mer** .


    ![Logga in mer skyddat kort.](../media/setupmfa.png)
3. På sidan gör inloggning säkrare väljer du **Kom igång**.
 
4. Markera kryss rutorna bredvid **Kräv multifaktorautentisering för administratörer** i fönstret Förstärk inloggnings säkerhet och **Kräv att användare registrerar multifaktorautentisering och blockera åtkomst om risken upptäcks**.
    Se till att exkludera [katastrof](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) -eller "brytar glas"-kontot från MFA-kravet i rutan **Sök efter användare** .
    
    ![Förstärka sidan för att skydda dig.](../media/requiremfa.png)

5. Välj **Skapa princip** längst ned på sidan.

## <a name="set-up-baseline-policies"></a>Konfigurera rikt linjer

1. Gå till [Azure-portalen](https://portal.azure.com)och gå till villkorlig åtkomst för **Azure Active Directory** \> **Conditional Access** för att skapa en **ny princip**.

Se följande anvisningar för varje princip: <br>
    - [Kräv MFA för administratörer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [Kräv MFA för användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [Blockera äldre autentisering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [Kräv MFA för tjänst hantering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)
    
> [!NOTE]
> För hands versions principer finns inte längre och användarna måste skapa sina egna principer.


Du kan konfigurera ytterligare principer, till exempel för godkända klient program. Mer information finns i dokumentationen för [villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/).
