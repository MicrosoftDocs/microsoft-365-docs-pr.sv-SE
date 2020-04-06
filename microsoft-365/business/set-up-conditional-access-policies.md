---
title: Konfigurera principer för villkorlig åtkomst för Microsoft 365-kampanjer
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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du ställer in principer för villkorlig åtkomst för Microsoft 365-kampanjer för att lägga till betydande ytterligare säkerhet.
ms.openlocfilehash: 26fadecc69486d7931dac069d8f53061592f397f
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153775"
---
# <a name="set-up-conditional-access-policies"></a>Ställ in principer för villkorlig åtkomst

[Principer för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) ger betydande ytterligare säkerhet. Microsoft tillhandahåller en uppsättning grundläggande principer för villkorlig åtkomst som rekommenderas för alla kunder. Baslinjeprinciper är en uppsättning fördefinierade principer som hjälper till att skydda organisationer mot många vanliga attacker. Dessa vanliga attacker kan omfatta lösenordsspray, uppspelning och nätfiske.

Dessa principer kräver att administratörer och användare anger en andra form av autentisering (kallas multifaktorautentisering eller MFA) när vissa villkor är uppfyllda. Om en användare till exempel loggar in från ett annat land kan inloggningen anses vara riskabel och användaren måste tillhandahålla ytterligare en form av autentisering. 

För närvarande omfattar baslinjeprinciper följande:
- **Kräv MFA för administratörer** &ndash; Kräver multifaktorautentisering för de mest privilegierade administratörsrollerna, inklusive global administratör.
- **Skydd för slutanvändare** &ndash; kräver multifaktorautentisering endast för användare när en inloggning är riskabel. 
- **Blockera äldre autentisering** &ndash; Äldre klientappar och vissa nya appar använder inte nyare, säkrare autentiseringsprotokoll. Dessa äldre appar kan kringgå principer för villkorlig åtkomst och få obehörig åtkomst till din miljö. Den här principen blockerar åtkomst från klienter som inte stöder villkorlig åtkomst. 
- **Kräv MFA för tjänsthantering** &ndash; Kräver multifaktorautentisering för åtkomst till hanteringsverktyg, inklusive Azure-portal (där du konfigurerar originalprinciper). 

Microsoft rekommenderar att du aktiverar alla dessa grundläggande principer. När dessa principer har aktiverats uppmanas administratörer och användare att registrera sig för Azure Multii-Factor-autentisering.

Mer information om dessa principer finns i [Vad är baslinjeprinciper?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)


## <a name="set-up-baseline-policies"></a>Ställ in originalprinciper

1. Gå till [Azure-portalen](https://portal.azure.com)och navigera sedan till **Azure Active Directory** \> **Villkorlig åtkomst**.
    
    Originalprinciperna visas på sidan. <br/> <br/>
    ![Sida som visar originalprinciper för villkorlig åtkomst.](../media/baslinepolicies.png)
1. Se följande specifika instruktioner för varje policy:

  - [Kräv MFA för administratörer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [Kräv MFA för användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [Blockera äldre autentisering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [Kräv MFA för tjänsthantering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

Du kan ställa in många ytterligare principer, till exempel kräver godkända klientappar. Mer information finns i [dokumentationen för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/).
