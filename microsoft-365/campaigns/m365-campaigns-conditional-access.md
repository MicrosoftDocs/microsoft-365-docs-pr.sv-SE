---
title: Konfigurera principer för villkorlig åtkomst
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
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Läs om hur du kräver MFA och konfigurerar principer för villkorlig åtkomst för Microsoft 365 Business.
ms.openlocfilehash: 7898ded24bb66545b903ab98f3c7aa78d95860f1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811470"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>Kräv multifaktorautentisering och konfigurera principer för villkorlig åtkomst

Du skyddar åtkomsten till dina data med principer för multifaktorautentisering och villkorlig åtkomst. Dessa ger betydande ytterligare säkerhet. Microsoft tillhandahåller en uppsättning principer för villkorlig åtkomst vid originalplan som rekommenderas för alla kunder. Originalprinciper är en uppsättning fördefinierade principer som hjälper till att skydda organisationer mot många vanliga attacker. Dessa vanliga attacker kan omfatta lösenordsspray, repris och nätfiske.

Dessa principer kräver att administratörer och användare anger en andra form av autentisering (kallas multifaktorautentisering eller MFA) när vissa villkor är uppfyllda. Om en användare i organisationen till exempel försöker logga in på Microsoft 365 från ett annat land eller från en okänd enhet kan inloggningen anses riskabel. Användaren måste tillhandahålla en extra form av autentisering (t.ex. ett fingeravtryck eller en kod) för att bevisa sin identitet. 

För närvarande innehåller baslinjeprinciper följande:
- Konfigurera i Microsoft 365 administrationscenter:
    - **Kräv MFA för administratörer** – Kräver multifaktorautentisering för de mest privilegierade administratörsrollerna, inklusive global administratör.
    - **Skydd för slutanvändare** – Kräver multifaktorautentisering endast för användare när en inloggning är riskabel. 
- Konfigurera i Azure Active Directory-portal:
    - **Blockera äldre autentisering** – Äldre klientappar och vissa nya appar använder inte nyare, säkrare autentiseringsprotokoll. Dessa äldre appar kan kringgå principer för villkorlig åtkomst och få obehörig åtkomst till din miljö. Den här principen blockerar åtkomst från klienter som inte stöder villkorlig åtkomst. 
    - **Kräv MFA för servicehantering** – Kräver multifaktorautentisering för åtkomst till hanteringsverktyg, inklusive Azure-portal (där du konfigurerar baslinjeprinciper). 

Microsoft rekommenderar att du aktiverar alla dessa baslinjeprinciper. När dessa principer är aktiverade uppmanas administratörer och användare att registrera sig för Azure Multi-Factor-autentisering.

Mer information om dessa principer finns i [Vad är originalprinciper?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)


## <a name="require-mfa"></a>Kräv MFA

Så här kräver du att alla användare loggar in med en andra form av ID:

1. Gå till administrationscentret och <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> välj **Installationsprogram**.

2. På sidan Inställningar väljer du **Visa** på det **säkrare kortet Gör inloggning.**


    ![Gör inloggning säkrare kort.](../media/setupmfa.png)
3. På sidan Gör inloggning säkrare väljer du **Kom igång**.
 
4. Markera kryssrutorna bredvid **Kräv multifaktorautentisering för administratörer** i säkerhetsfönstret Stärka inloggning **och blockera åtkomst om risken upptäcks**.
    Var noga med att utesluta [administrationskontot](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) för nödsituationer eller "break-glass" från MFA-kravet i rutan **Hitta användare.**
    
    ![Stärka sing-in säkerhetssida.](../media/requiremfa.png)

5. Välj **Skapa princip** längst ned på sidan.

## <a name="set-up-baseline-policies"></a>Ställ in baslinjeprinciper

1. Gå till [Azure-portalen](https://portal.azure.com)och navigera sedan till **Azure Active Directory** \> **Villkorlig åtkomst**.
    
    Baslinjeprinciperna visas på sidan och du kan se att **Kräv MFA för administratörer** och **skydd för slutanvändare** redan är aktiverade när du har slutfört stegen i [kräver MFA](#require-mfa).

    ![Sida som visar originalprinciper för villkorlig åtkomst.](../media/casettings.png)
2. Se följande specifika instruktioner för varje princip:

    - [Kräv MFA för administratörer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
    - [Kräv MFA för användare](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [Blockera äldre autentisering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
    - [Kräv MFA för servicehantering](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

Du kan ställa in extra principer, till exempel kräva godkända klientappar. Mer information finns i [dokumentationen för villkorlig åtkomst](https://docs.microsoft.com/azure/active-directory/conditional-access/).
