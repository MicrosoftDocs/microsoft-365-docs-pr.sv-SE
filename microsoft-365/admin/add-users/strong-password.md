---
title: Ange krav för starkt lösen ord för användare
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
description: Lär dig hur du ställer in kraven på starka lösen ord för användarna med Windows PowerShell.
ms.openlocfilehash: 1230ff4b4235ac5acbc28aa823506dfa5af26c2d
ms.sourcegitcommit: 3165329d1fb5a7fd866ff287bea3b6354ea2be18
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48581030"
---
# <a name="set-strong-password-requirement-for-users"></a>Ange krav för starkt lösen ord för användare

I den här artikeln förklaras hur du anger krav för starka lösen ord för användarna. Du måste utföra de här stegen med PowerShell.

## <a name="before-you-begin"></a>Innan du börjar

Den här artikeln är till för personer som hanterar lösen ords principer för ett företag, en skola eller en ideellt område. Du måste logga in med ditt administratörskonto för Microsoft 365 för att slutföra de här stegen. [Vad är ett administratörskonto?](../admin-overview/admin-overview.md). Du måste vara [Global administratör eller lösen ords administratör](about-admin-roles.md) för att utföra de här stegen.

Du måste också ansluta till Microsoft 365 med PowerShell.

## <a name="set-strong-passwords"></a>Ange starka lösen ord

1. [Anslut till Microsoft 365 med PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

2. Med PowerShell kan du inaktivera starka lösen ord för vissa användare med det här kommandot:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> UserPrincipalName måste finnas i Internet-stilens inloggnings format där användar namnet följs av snabel-a (@) och ett domän namn. Till exempel: user@contoso.com.

## <a name="related-content"></a>Relaterat innehåll

[Så här ansluter du till Microsoft 365 med PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[Mer information om PowerShell-kommandon för MsolUser](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[Mer information om lösen ords princip](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)