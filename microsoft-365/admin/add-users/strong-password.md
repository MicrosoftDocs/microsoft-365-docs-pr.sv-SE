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
description: Läs om hur du ställer in starka lösenordskrav för användarna med Windows PowerShell.
ms.openlocfilehash: e2300e3c94de53cd04d0c1726538fdb8a86a1ccf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903542"
---
# <a name="turn-off-strong-password-requirements-for-users"></a><span data-ttu-id="924eb-103">Inaktivera starka lösenordskrav för användare</span><span class="sxs-lookup"><span data-stu-id="924eb-103">Turn off strong password requirements for users</span></span>

<span data-ttu-id="924eb-104">I den här artikeln förklarar vi hur du inaktiverar starka lösenordskrav för användarna.</span><span class="sxs-lookup"><span data-stu-id="924eb-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="924eb-105">Starka lösenordskrav är aktiverat som standard i din organisation för Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="924eb-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="924eb-106">Din organisation kan behöva inaktivera starka lösenord.</span><span class="sxs-lookup"><span data-stu-id="924eb-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="924eb-107">Följ stegen nedan för att inaktivera starka lösenordskrav.</span><span class="sxs-lookup"><span data-stu-id="924eb-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="924eb-108">Du måste utföra de här stegen med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="924eb-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="924eb-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="924eb-109">Before you begin</span></span>

<span data-ttu-id="924eb-110">Den här artikeln är för personer som hanterar lösenordspolicyn för ett företag, en skola eller en ideell förening.</span><span class="sxs-lookup"><span data-stu-id="924eb-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="924eb-111">Du måste logga in med ditt administratörskonto för Microsoft 365 för att slutföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="924eb-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="924eb-112">Vad är ett administratörskonto?</span><span class="sxs-lookup"><span data-stu-id="924eb-112">What's an admin account?</span></span>](../admin-overview/admin-overview.md) <span data-ttu-id="924eb-113">Du måste vara global [administratör eller lösenordsadministratör för att](about-admin-roles.md) utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="924eb-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="924eb-114">Du måste också ansluta till Microsoft 365 med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="924eb-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="924eb-115">Ange starka lösenord</span><span class="sxs-lookup"><span data-stu-id="924eb-115">Set strong passwords</span></span>

1. <span data-ttu-id="924eb-116">[Anslut till Microsoft 365 med PowerShell.](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="924eb-116">[Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="924eb-117">Med PowerShell kan du inaktivera starka lösenordskrav för alla användare med följande kommando:</span><span class="sxs-lookup"><span data-stu-id="924eb-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="924eb-118">UserPrincipalName måste ha ett inloggningsformat som är internetformat där användarnamnet följs av at-tecknet (@) och ett domännamn.</span><span class="sxs-lookup"><span data-stu-id="924eb-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="924eb-119">Till exempel: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="924eb-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="924eb-120">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="924eb-120">Related content</span></span>

[<span data-ttu-id="924eb-121">Ansluta till Microsoft 365 med PowerShell</span><span class="sxs-lookup"><span data-stu-id="924eb-121">How to connect to Microsoft 365 with PowerShell</span></span>](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="924eb-122">Mer information om PowerShell MsolUser-kommandon</span><span class="sxs-lookup"><span data-stu-id="924eb-122">More information on PowerShell MsolUser commands</span></span>](/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="924eb-123">Mer information om lösenordsprincip</span><span class="sxs-lookup"><span data-stu-id="924eb-123">More information on password policy</span></span>](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)