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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
description: Läs om hur du ställer in principer för villkorlig åtkomst för Microsoft 365-kampanjer för att lägga till ytterligare säkerhet.
ms.openlocfilehash: be3ca0da3d27e3ec49f1227e4482cfd7fcaae8cb
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/06/2020
ms.locfileid: "42550086"
---
# <a name="set-up-conditional-access-policies"></a>Konfigurera principer för villkorlig åtkomst

[Principer](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) för villkorlig åtkomst ger betydande ytterligare säkerhet. Microsoft tillhandahåller en uppsättning principer för villkorlig åtkomst vid originalplan som rekommenderas för alla kunder. Originalprinciper är en uppsättning fördefinierade principer som hjälper till att skydda organisationer mot många vanliga attacker. Dessa vanliga attacker kan omfatta lösenordsspray, repris och nätfiske.

Dessa principer kräver att administratörer och användare anger en andra form av autentisering (kallas multifaktorautentisering eller MFA) när vissa villkor är uppfyllda. Om en användare till exempel loggar in från ett annat land kan inloggning betraktas som riskabel och användaren måste tillhandahålla ytterligare en form av autentisering. 

För närvarande innehåller baslinjeprinciper följande:
- **Kräv MFA för administratörer** &ndash; Kräver multifaktorautentisering för de mest privilegierade administratörsrollerna, inklusive global administratör.
- **Slutanvändarskydd** &ndash; Kräver multifaktorautentisering endast för användare när en inloggning är riskabel. 
- **Blockera äldre autentisering** &ndash; Äldre klientappar och vissa nya appar använder inte nyare, säkrare autentiseringsprotokoll. Dessa äldre appar kan kringgå principer för villkorlig åtkomst och få obehörig åtkomst till din miljö. Den här principen blockerar åtkomst från klienter som inte stöder villkorlig åtkomst. 
- **Kräv MFA för servicehantering** &ndash; Kräver multifaktorautentisering för åtkomst till hanteringsverktyg, inklusive Azure-portal (där du konfigurerar baslinjeprinciper). 

Microsoft rekommenderar att du aktiverar alla dessa baslinjeprinciper. När dessa principer är aktiverade uppmanas administratörer och användare att registrera sig för Azure Multii-Factor-autentisering.

Mer information om dessa principer finns i [Vad är originalprinciper?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)


## <a name="set-up-baseline-policies"></a>Ställ in baslinjeprinciper

1. Gå till [Azure-portalen](https://portal.azure.com)och navigera sedan till **Azure Active Directory** \> **Villkorlig åtkomst**.
    
    Originalplansprinciperna visas på sidan. <br/> <br/>
    ![Sida som visar originalprinciper för villkorlig åtkomst.](../media/baslinepolicies.png)
1. Se följande specifika instruktioner för varje princip:

  - [Kräv MFA för administratörer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
- [Kräv MFA för användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
 - [Blockera äldre autentisering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
  - [Kräv MFA för servicehantering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

Du kan ställa in många ytterligare principer, till exempel kräva godkända klientappar. Mer information finns i [dokumentationen för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/).
