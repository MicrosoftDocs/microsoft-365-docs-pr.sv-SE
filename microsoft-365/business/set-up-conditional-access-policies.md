---
title: Ställ in principer för villkorlig åtkomst för Microsoft 365-kampanjer
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
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du ställer in principer för villkorlig åtkomst för Microsoft 365-kampanjer.
ms.openlocfilehash: 335fbd7e771b1595e1846529daed76e5ddd3a8f5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593394"
---
# <a name="set-up-conditional-access-policies"></a>Ställ in principer för villkorlig åtkomst

[Principer för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) lägger till betydande ytterligare säkerhet. Microsoft tillhandahåller en uppsättning principer för villkorlig åtkomst vid baslinjen som rekommenderas för alla kunder. Baslinjeprinciper är en uppsättning fördefinierade principer som skyddar organisationer mot många vanliga attacker. Dessa vanliga attacker kan omfatta lösenordspray, repris och nätfiske.

Dessa principer kräver administratörer och användare att ange en andra form av autentisering (kallas multifaktorautentisering, eller MFA) när vissa villkor är uppfyllda. Om en användare till exempel loggar in från ett annat land kan inloggningen betraktas som riskabel och användaren måste tillhandahålla ytterligare en form av autentisering. 

För närvarande omfattar baslinjeprinciper följande:
- **Kräv MFA för administratörer** &ndash; kräver multifaktorautentisering för de mest privilegierade administratörsroller, inklusive global administratör.
- **Slutanvändarskydd** &ndash; Kräver multifaktorautentisering endast för användare när en inloggning är riskabel. 
- **Blockera äldre autentisering** &ndash; Äldre klientappar och vissa nya appar använder inte nyare, säkrare autentiseringsprotokoll. Dessa äldre appar kan kringgå principer för villkorlig åtkomst och få obehörig åtkomst till din miljö. Den här principen blockerar åtkomst från klienter som inte stöder villkorlig åtkomst. 
- **Kräv MFA för Service Management** &ndash; kräver multifaktorautentisering för åtkomst till hanteringsverktyg, inklusive Azure-portalen (där du konfigurerar baslinjeprinciper). 

Microsoft rekommenderar att du aktiverar alla dessa baslinjeprinciper. När dessa principer har aktiverats uppmanas administratörer och användare att registrera sig för Azure Multii-Factor-autentisering.After these policies are enabled, admins and users will be prompted to register for Azure Multii-Factor authentication.

Mer information om dessa principer finns i [Vad är baslinjeprinciper?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)


## <a name="set-up-baseline-policies"></a>Ställ in baslinjeprinciper

1. Gå till [Azure-portalen](https://portal.azure.com)och navigera sedan till **Azure Active Directory** \> villkorlig åtkomst .Go to Azure portal **conditional access**.
    
    Baslinjeprinciperna visas på sidan. <br/> <br/>
    ![Sida som visar originalprinciper för villkorlig åtkomst.](media/baslinepolicies.png)
1. Se följande specifika instruktioner för varje princip:

  - [Kräv MFA för administratörerRequire MFA for admins](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [Kräv MFA för användareRequire MFA for users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [Blockera äldre autentisering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [Kräv MFA för servicehantering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

Du kan ställa in många ytterligare principer, till exempel kräver godkända klientappar. Mer information finns i [dokumentationen för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/).
