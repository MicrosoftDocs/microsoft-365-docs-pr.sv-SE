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
ms.openlocfilehash: 1634e2f0de2cdd2cac5e1928adbef54457e50716
ms.sourcegitcommit: e17fd18b01d70e6428263c20cbce4b92e2a97765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/20/2020
ms.locfileid: "48626149"
---
# <a name="set-strong-password-requirement-for-users"></a><span data-ttu-id="b5a1d-103">Ange krav för starkt lösen ord för användare</span><span class="sxs-lookup"><span data-stu-id="b5a1d-103">Set strong password requirement for users</span></span>

<span data-ttu-id="b5a1d-104">I den här artikeln förklaras hur du anger krav för starka lösen ord för användarna.</span><span class="sxs-lookup"><span data-stu-id="b5a1d-104">This article explains how to set strong password requirements for your users.</span></span> <span data-ttu-id="b5a1d-105">Du måste utföra de här stegen med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b5a1d-105">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="b5a1d-106">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="b5a1d-106">Before you begin</span></span>

<span data-ttu-id="b5a1d-107">Den här artikeln är till för personer som hanterar lösen ords principer för ett företag, en skola eller en ideellt område.</span><span class="sxs-lookup"><span data-stu-id="b5a1d-107">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="b5a1d-108">Du måste logga in med ditt administratörskonto för Microsoft 365 för att slutföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="b5a1d-108">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> <span data-ttu-id="b5a1d-109">[Vad är ett administratörskonto?](../admin-overview/admin-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b5a1d-109">[What's an admin account?](../admin-overview/admin-overview.md).</span></span> <span data-ttu-id="b5a1d-110">Du måste vara [Global administratör eller lösen ords administratör](about-admin-roles.md) för att utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="b5a1d-110">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="b5a1d-111">Du måste också ansluta till Microsoft 365 med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b5a1d-111">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="b5a1d-112">Ange starka lösen ord</span><span class="sxs-lookup"><span data-stu-id="b5a1d-112">Set strong passwords</span></span>

1. <span data-ttu-id="b5a1d-113">[Anslut till Microsoft 365 med PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="b5a1d-113">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="b5a1d-114">Med PowerShell kan du aktivera krav för starka lösen ord för alla användare med följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b5a1d-114">Using PowerShell, you can turn on strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $true

3. You can turn on strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $true
    ```

> [!NOTE]
> <span data-ttu-id="b5a1d-115">UserPrincipalName måste finnas i Internet-stilens inloggnings format där användar namnet följs av snabel-a (@) och ett domän namn.</span><span class="sxs-lookup"><span data-stu-id="b5a1d-115">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="b5a1d-116">Till exempel: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b5a1d-116">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="b5a1d-117">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="b5a1d-117">Related content</span></span>

[<span data-ttu-id="b5a1d-118">Så här ansluter du till Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="b5a1d-118">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="b5a1d-119">Mer information om PowerShell-kommandon för MsolUser</span><span class="sxs-lookup"><span data-stu-id="b5a1d-119">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="b5a1d-120">Mer information om lösen ords princip</span><span class="sxs-lookup"><span data-stu-id="b5a1d-120">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)