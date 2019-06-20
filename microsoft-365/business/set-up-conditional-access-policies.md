---
title: Konfigurera principer för villkorlig åtkomst för Microsoft 365 kampanjer
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
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du konfigurerar principer för villkorlig åtkomst för Microsoft 365 kampanjer.
ms.openlocfilehash: 7d8e1f16019d151478aae57b1593b0e0758e5b19
ms.sourcegitcommit: 7e46db0b35c188ee6a7b40ab3eb2d76ff6c101c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2019
ms.locfileid: "35086405"
---
# <a name="set-up-conditional-access-policies"></a>Konfigurera principer för villkorad tillgång

Principer för [villkorad tillgång](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) lägga substancial ytterligare säkerhet. Microsoft tillhandahåller en uppsättning principer för villkorad tillgång originalplan som rekommenderas för alla kunder. Principer för originalplan är en uppsättning fördefinierade principer som skyddar organisationer mot många vanliga attacker. Vanliga angrepp kan innehålla lösenord spray, replay och nätfiske.

Dessa principer kräver att administratörer och användare att ange en andra form av autentisering (kallas flerfunktionsautentisering eller MFA) när vissa villkor uppfylls. Om en användare loggar in från ett annat land kan logga in kan betraktas som riskfyllda och användaren måste ange en ytterligare form av autentisering. 

Originalplan principer är för närvarande följande:
- **Kräver MFA för administratörer** , kräver autentisering på flera plan för de mest Privilegierade administratörsroller inklusive global administratör.
- **Skydd för slutanvändaren** – kräver autentisering på flera plan för användarna endast när en inloggning är riskabelt. 
- **Blockera äldre autentisering** – äldre klientprogram och vissa nya program som inte använder nyare, säkrare autentiseringsprotokoll. Dessa äldre apps kan kringgå principer för villkorad tillgång och få otillåten åtkomst till din miljö. Den här principen blockerar från klienter som inte stöder villkorlig åtkomst. 
- **Kräver MFA för servicehantering** , kräver autentisering på flera plan för tillgång till verktyg, inklusive Azure portal (där du konfigurerar principer för originalplanen). 

Microsoft rekommenderar att du aktiverar alla dessa principer för originalplan. När dessa principer är aktiverat kan uppmanas administratörer och användare att registrera för Azure Multii-faktor autentisering.

Mer information om dessa principer finns i [Vad är baslinjen principer](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?


## <a name="set-up-baseline-policies"></a>Ställ in policyer för baslinje

1. Gå till [Azure portal](https://portal.azure.com)och navigera sedan till **Azure Active Directory** \> **Villkorad tillgång**.
    
    Principer för originalplan visas på sidan. <br/> <br/>
    ![Sida med originalplan principer för villkorad tillgång.](media/baslinepolicies.png)
1. Följande specifika instruktioner för varje princip finns:

  - [Kräv MFA för administratörer](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [Reequire MFA för användare](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [Blockera äldre autentisering](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [Kräv MFA för servicehantering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

Du kan ställa in många ytterligare principer som kräver godkända klientprogram. Finns i [Dokumentationen för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/) för mer information.