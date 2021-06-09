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
ms.openlocfilehash: 898eaf30d813e883e88c3ccc8ff500d72ae72854
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840664"
---
# <a name="turn-off-strong-password-requirements-for-users"></a><span data-ttu-id="6e65f-103">Inaktivera starka lösenordskrav för användare</span><span class="sxs-lookup"><span data-stu-id="6e65f-103">Turn off strong password requirements for users</span></span>

<span data-ttu-id="6e65f-104">I den här artikeln förklarar vi hur du inaktiverar starka lösenordskrav för användarna.</span><span class="sxs-lookup"><span data-stu-id="6e65f-104">This article explains how to turn off strong password requirements for your users.</span></span> <span data-ttu-id="6e65f-105">Starka lösenordskrav är aktiverat som standard i din organisation Microsoft 365 för företag.</span><span class="sxs-lookup"><span data-stu-id="6e65f-105">Strong password requirements are turned on by default in your Microsoft 365 for business organization.</span></span> <span data-ttu-id="6e65f-106">Din organisation kan behöva inaktivera starka lösenord.</span><span class="sxs-lookup"><span data-stu-id="6e65f-106">Your organization might have requirements to disable strong passwords.</span></span> <span data-ttu-id="6e65f-107">Följ stegen nedan för att inaktivera starka lösenordskrav.</span><span class="sxs-lookup"><span data-stu-id="6e65f-107">Follow the steps below to turn off strong password requirements.</span></span> <span data-ttu-id="6e65f-108">Du måste utföra de här stegen med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e65f-108">You have to complete these steps using PowerShell.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6e65f-109">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="6e65f-109">Before you begin</span></span>

<span data-ttu-id="6e65f-110">Den här artikeln är för personer som hanterar lösenordspolicyn för ett företag, en skola eller en ideell förening.</span><span class="sxs-lookup"><span data-stu-id="6e65f-110">This article is for people who manage password policy for a business, school, or nonprofit.</span></span> <span data-ttu-id="6e65f-111">Du måste logga in med ditt administratörskonto för Microsoft 365 för att slutföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="6e65f-111">To complete these steps, you need to sign in with your Microsoft 365 admin account.</span></span> [<span data-ttu-id="6e65f-112">Vad är ett administratörskonto?</span><span class="sxs-lookup"><span data-stu-id="6e65f-112">What's an admin account?</span></span>](/microsoft-365/business-video/admin-center-overview) <span data-ttu-id="6e65f-113">Du måste vara global [administratör eller lösenordsadministratör för att](about-admin-roles.md) utföra de här stegen.</span><span class="sxs-lookup"><span data-stu-id="6e65f-113">You must be an [global admin or password administrator](about-admin-roles.md) to perform these steps.</span></span>

<span data-ttu-id="6e65f-114">Du måste också ansluta till Microsoft 365 med PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6e65f-114">You must also connect to Microsoft 365 with PowerShell.</span></span>

## <a name="set-strong-passwords"></a><span data-ttu-id="6e65f-115">Ange starka lösenord</span><span class="sxs-lookup"><span data-stu-id="6e65f-115">Set strong passwords</span></span>

1. <span data-ttu-id="6e65f-116">[Anslut att Microsoft 365 med PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="6e65f-116">[Connect to Microsoft 365 with PowerShell](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

2. <span data-ttu-id="6e65f-117">Med PowerShell kan du inaktivera starka lösenordskrav för alla användare med följande kommando:</span><span class="sxs-lookup"><span data-stu-id="6e65f-117">Using PowerShell, you can turn off strong password requirements for all users with the following command:</span></span>

    ```powershell
    Get-MsolUser | Set-MsolUser -StrongPasswordRequired $false

3. You can turn of strong password requirements for specific users with this command:

    ```powershell
    Set-MsolUser –UserPrincipalName –StrongPasswordRequired  $false
    ```

> [!NOTE]
> <span data-ttu-id="6e65f-118">UserPrincipalName måste ha ett inloggningsformat som är internetformat där användarnamnet följs av at-tecknet (@) och ett domännamn.</span><span class="sxs-lookup"><span data-stu-id="6e65f-118">The userPrincipalName must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name.</span></span> <span data-ttu-id="6e65f-119">Till exempel: user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6e65f-119">For example: user@contoso.com.</span></span>

## <a name="related-content"></a><span data-ttu-id="6e65f-120">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="6e65f-120">Related content</span></span>

[<span data-ttu-id="6e65f-121">Ansluta till Microsoft 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e65f-121">How to connect to Microsoft 365 with PowerShell</span></span>](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

[<span data-ttu-id="6e65f-122">Mer information om PowerShell MsolUser-kommandon</span><span class="sxs-lookup"><span data-stu-id="6e65f-122">More information on PowerShell MsolUser commands</span></span>](/powershell/module/msonline/set-msoluser?view=azureadps-1.0)

[<span data-ttu-id="6e65f-123">Mer information om lösenordsprincip</span><span class="sxs-lookup"><span data-stu-id="6e65f-123">More information on password policy</span></span>](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)