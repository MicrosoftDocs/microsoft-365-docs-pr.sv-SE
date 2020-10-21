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
ms.openlocfilehash: 9f6fd61396d99245ffeabf757d3cb65c5d5cb85e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48646625"
---
# <a name="set-strong-password-requirement-for-users"></a><span data-ttu-id="07fe9-103">Ange krav för starkt lösen ord för användare</span><span class="sxs-lookup"><span data-stu-id="07fe9-103">Set strong password requirement for users</span></span>

<span data-ttu-id="07fe9-104">I den här artikeln förklaras hur du inaktiverar kraven på starka lösen ord för användarna.</span><span class="sxs-lookup"><span data-stu-id="07fe9-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="07fe9-105">Krav för starka lösen ord är aktiverade som standard i Microsoft 365 för företag-organisationen.</span><span class="sxs-lookup"><span data-stu-id="07fe9-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="07fe9-106">Din organisation kan ha behov att inaktivera starka lösen ord.</span><span class="sxs-lookup"><span data-stu-id="07fe9-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="07fe9-107">Följ stegen nedan om du vill inaktivera kraven för starka lösen ord.</span><span class="sxs-lookup"><span data-stu-id="07fe9-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="07fe9-108">Du måste utföra de här stegen med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07fe9-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="07fe9-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="07fe9-109">Before you begin</span></span>

<span data-ttu-id="07fe9-110">Den här artikeln är till för personer som hanterar lösen ords principer för ett företag, en skola eller en ideellt område.</span><span class="sxs-lookup"><span data-stu-id="07fe9-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="07fe9-111">Du måste logga in med ditt administratörskonto för Microsoft 365 för att slutföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="07fe9-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="07fe9-112">Vad är ett administratörs konto?</span><span class="sxs-lookup"><span data-stu-id="07fe9-112">What's an admin account?</span></span>](../admin-overview/admin-overview.md) <span data-ttu-id="07fe9-113">Du måste vara [Global administratör eller lösen ords administratör](about-admin-roles.md) för att utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="07fe9-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="07fe9-114">Du måste också ansluta till Microsoft 365 med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="07fe9-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="07fe9-115">Ange starka lösen ord</span><span class="sxs-lookup"><span data-stu-id="07fe9-115">Set strong passwords</span></span>

1. <span data-ttu-id="07fe9-116">[Anslut till Microsoft 365 med PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="07fe9-116">[Connect to Microsoft 365 with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="07fe9-117">Med PowerShell kan du stänga av kraven på starka lösen ord för alla användare med följande kommando:</span><span class="sxs-lookup"><span data-stu-id="07fe9-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="07fe9-118">UserPrincipalName måste finnas i Internet-stilens inloggnings format där användar namnet följs av snabel-a (@) och ett domän namn.</span><span class="sxs-lookup"><span data-stu-id="07fe9-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="07fe9-119">Till exempel: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="07fe9-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="07fe9-120">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="07fe9-120">Related content</span></span>

[<span data-ttu-id="07fe9-121">Så här ansluter du till Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="07fe9-121">How to connect to Microsoft 365 with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="07fe9-122">Mer information om PowerShell-kommandon för MsolUser</span><span class="sxs-lookup"><span data-stu-id="07fe9-122">More information on PowerShell MsolUser commands</span></span>](https://docs.microsoft.com/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="07fe9-123">Mer information om lösen ords princip</span><span class="sxs-lookup"><span data-stu-id="07fe9-123">More information on password policy</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)