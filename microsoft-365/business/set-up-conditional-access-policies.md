---
title: Ställ in principer för villkorlig åtkomst för Microsoft 365-kampanjer
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig hur du ställer in principer för villkorlig åtkomst för Microsoft 365-kampanjer.
ms.openlocfilehash: dbb5231032d2faef0a7ecb2734226b34290c70bf
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288624"
---
# <a name="set-up-conditional-access-policies"></a>Ställ in principer för villkorlig åtkomst

Principer för [villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) lägga till substancial ytterligare säkerhet. Microsoft tillhandahåller en uppsättning principer för villkorlig åtkomst Vidbaslinjen som rekommenderas för alla kunder. Baslinje principer är en uppsättning fördefinierade principer som hjälper till att skydda organisationer mot många vanliga attacker. Dessa vanliga attacker kan omfatta lösenord spray, Replay och phishing.

Dessa principer kräver administratörer och användare att ange en andra form av autentisering (kallas multifaktorautentisering eller MFA) när vissa villkor uppfylls. Till exempel om en användare loggar in från ett annat land, kan inloggningen anses vara riskabelt och användaren måste tillhandahålla ytterligare en form av autentisering. 

För närvarande omfattar baslinje principer följande:
- **KRÄV MFA för administratörer** – kräver multifaktorautentisering för de mest privilegierade administratörsrollerna, inklusive global administratör.
- **användarskydd** – kräver multifaktorautentisering för användare endast när en inloggning är riskabelt. 
- **Blockera äldre autentisering** – äldre klientappar och vissa nya appar använder inte nyare, säkrare autentiseringsprotokoll. Dessa äldre appar kan kringgå principer för villkorlig åtkomst och få obehörig åtkomst till din miljö. Den här principen blockerar åtkomsten från klienter som inte stöder villkorlig åtkomst. 
- **KRÄV MFA för service hantering** – kräver multifaktorautentisering för åtkomst till hanteringsverktyg, inklusive Azure Portal (där du konfigurerar principer för baslinje). 

Microsoft rekommenderar att du aktiverar alla dessa baslinje principer. När dessa principer har aktiverats uppmanas administratörer och användare att registrera för Azure Multii-Factor-autentisering.

Mer information om dessa principer finns i [Vad är baslinje principer](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?


## <a name="set-up-baseline-policies"></a>Ställ in principer för originalplan

1. Gå till [Azure-portalen](https://portal.azure.com), och sedan gå **till Azure Active Directory** \> **villkorlig åtkomst**.
    
    Baslinje principerna visas på sidan. <br/> <br/>
    ![Sida som listar baslinje principer för villkorlig åtkomst.](media/baslinepolicies.png)
1. Se följande specifika instruktioner för varje princip:

  - [Kräv MFA för administratörer](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [Kräv MFA för användare](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [Blockera äldre autentisering](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [Kräv MFA för servicehantering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

Du kan ställa in många ytterligare principer, till exempel kräver godkända klientappar. Mer information finns i [dokumentationen för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/) .