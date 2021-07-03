---
title: Inaktivera starka lösenordskrav för användare
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Lär dig ställa in starka lösenordskrav för användarna med hjälp av Windows PowerShell.
ms.openlocfilehash: 87ba9e0323c379d8c2589dbb82c38c531dd9d047
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286273"
---
# <a name="turn-off-strong-password-requirements-for-users"></a>Inaktivera starka lösenordskrav för användare

I den här artikeln förklarar vi hur du inaktiverar starka lösenordskrav för användarna. Starka lösenordskrav är aktiverat som standard i din organisation Microsoft 365 för företag. Din organisation kan behöva inaktivera starka lösenord. Följ stegen nedan för att inaktivera starka lösenordskrav. Du måste utföra de här stegen med PowerShell.

## <a name="before-you-begin"></a>Innan du börjar

Den här artikeln är för personer som hanterar lösenordspolicyn för ett företag, en skola eller en ideell förening. Du måste logga in med ditt administratörskonto för Microsoft 365 för att slutföra de här stegen. [Vad är ett administratörskonto?](/microsoft-365/business-video/admin-center-overview) Du måste vara global [administratör eller lösenordsadministratör för att](about-admin-roles.md) utföra de här stegen.

Du måste också ansluta till Microsoft 365 med PowerShell.

## <a name="set-strong-passwords"></a>Ange starka lösenord

1. [Anslut att Microsoft 365 med PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. Med PowerShell kan du inaktivera starka lösenordskrav för alla användare med följande kommando:

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> UserPrincipalName måste ha ett inloggningsformat som är internetformat där användarnamnet följs av at-tecknet (@) och ett domännamn. Till exempel: user@contoso.com.

## <a name="related-content"></a>Relaterat innehåll

[Ansluta till Microsoft 365 PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Mer information om PowerShell MsolUser-kommandon](/powershell/azure/active-directory/install-adv2)

[Mer information om lösenordsprincip](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)
