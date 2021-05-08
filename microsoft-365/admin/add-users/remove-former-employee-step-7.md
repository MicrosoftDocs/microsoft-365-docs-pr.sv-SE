---
title: Steg 7 – Ta bort en tidigare anställds användarkonto
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Följ de här stegen om du vill ta bort en tidigare anställds användarkonto.
ms.openlocfilehash: 0afa9b112919d2668d7553ac5bcf08e664bc1749
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244293"
---
# <a name="step-7---delete-a-former-employees-user-account"></a><span data-ttu-id="4bcd1-103">Steg 7 – Ta bort en tidigare anställds användarkonto</span><span class="sxs-lookup"><span data-stu-id="4bcd1-103">Step 7 - Delete a former employee's user account</span></span>

<span data-ttu-id="4bcd1-104">När du har sparat och kommit åt den tidigare anställdes alla användardata kan du ta bort den tidigare anställdes konto.</span><span class="sxs-lookup"><span data-stu-id="4bcd1-104">After you've saved and accessed all the former employee's user data, you can delete the former employee's account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4bcd1-p101">Ta inte bort kontot om du har konfigurerat vidarebefordran av e-post eller konverterat postlådan till en delad postlåda. Kontot krävs för att kunna använda vidarebefordran av e-post eller den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="4bcd1-p101">Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.</span></span>

1. <span data-ttu-id="4bcd1-107">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="4bcd1-107">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="4bcd1-108">Markera namnet på den anställda som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="4bcd1-108">Select the name of the employee that you want to delete.</span></span>
3. <span data-ttu-id="4bcd1-109">Under användarens namn väljer du Ta **bort användare.**</span><span class="sxs-lookup"><span data-stu-id="4bcd1-109">Under the user's name, select **Delete user**.</span></span> <span data-ttu-id="4bcd1-110">Välj de alternativ du vill använda för användaren och välj sedan Ta **bort användare.**</span><span class="sxs-lookup"><span data-stu-id="4bcd1-110">Choose the options you want for this user, and then select **Delete user**.</span></span> <span data-ttu-id="4bcd1-111">Om du redan har gett en annan användare åtkomst till den här användarens e-OneDrive behöver du inte göra det igen här.</span><span class="sxs-lookup"><span data-stu-id="4bcd1-111">If you've already given another user access to this user's email and OneDrive, you don't have to do it again here.</span></span>

<span data-ttu-id="4bcd1-p103">När du tar bort en användare blir dennes konto inaktivt i ca 30 dagar. Du har tills dess på dig att återställa kontot innan det tas bort permanent.</span><span class="sxs-lookup"><span data-stu-id="4bcd1-p103">When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.</span></span>
  
## <a name="does-your-organization-use-active-directory"></a><span data-ttu-id="4bcd1-114">Använder ni Active Directory i organisationen?</span><span class="sxs-lookup"><span data-stu-id="4bcd1-114">Does your organization use Active Directory?</span></span>

<span data-ttu-id="4bcd1-115">Om din organisation synkroniserar användarkonton till Microsoft 365 från en lokal Active Directory-miljö måste du ta bort och återställa dessa användarkonton i den lokala Active Directory-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="4bcd1-115">If your organization synchronizes user accounts to Microsoft 365 from a local Active Directory environment, you must delete and restore those user accounts in your local Active Directory service.</span></span> <span data-ttu-id="4bcd1-116">Du kan inte ta bort eller återställa dem i Office 365.</span><span class="sxs-lookup"><span data-stu-id="4bcd1-116">You can't delete or restore them in Office 365.</span></span>

<span data-ttu-id="4bcd1-117">Mer information om hur du tar bort och återställer användarkonton i Active Directory finns [i Ta bort ett användarkonto.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="4bcd1-117">To learn how to delete and restore user account in Active Directory, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>
  
<span data-ttu-id="4bcd1-118">Om du använder en Azure Active Directory, se [PowerShell-cmdleten Remove-MsolUser.](https://go.microsoft.com/fwlink/?linkid=842230)</span><span class="sxs-lookup"><span data-stu-id="4bcd1-118">If you're using Azure Active Directory, see the [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell cmdlet.</span></span>
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a><span data-ttu-id="4bcd1-119">Vad du behöver veta om att avsluta en anställds e-postsession</span><span class="sxs-lookup"><span data-stu-id="4bcd1-119">What you need to know about terminating an employee's email session</span></span>

<span data-ttu-id="4bcd1-120">Här finns information om hur du avslutar en anställds e-post (Exchange).</span><span class="sxs-lookup"><span data-stu-id="4bcd1-120">Here's information about how to get an employee out of email (Exchange).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4bcd1-121">**Vad du kan göra**</span><span class="sxs-lookup"><span data-stu-id="4bcd1-121">**What you can do**</span></span> <br/> |<span data-ttu-id="4bcd1-122">**Hur gör du det?**</span><span class="sxs-lookup"><span data-stu-id="4bcd1-122">**How you do it**</span></span> <br/> |
|<span data-ttu-id="4bcd1-123">Avsluta en session (till exempel Outlook på webben, Outlook, Exchange ActiveSync, etc.) och framtvinga en ny session</span><span class="sxs-lookup"><span data-stu-id="4bcd1-123">Terminate a session (such as Outlook on the web, Outlook, Exchange active sync, etc.) and force to open a new session</span></span>  <br/> |<span data-ttu-id="4bcd1-124">Återställa lösenord</span><span class="sxs-lookup"><span data-stu-id="4bcd1-124">Reset password</span></span>  <br/> |
|<span data-ttu-id="4bcd1-125">Avsluta en session och blockera åtkomst till framtida sessioner (för alla protokoll)</span><span class="sxs-lookup"><span data-stu-id="4bcd1-125">Terminate a session and block access to future sessions (for all protocols)</span></span>  <br/> |<span data-ttu-id="4bcd1-126">Inaktivera kontot.</span><span class="sxs-lookup"><span data-stu-id="4bcd1-126">Disable the account.</span></span> <span data-ttu-id="4bcd1-127">Till exempel (i Exchange eller med PowerShell):</span><span class="sxs-lookup"><span data-stu-id="4bcd1-127">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|<span data-ttu-id="4bcd1-128">Avbryt sessionen för ett visst protokoll (till exempel ActiveSync)</span><span class="sxs-lookup"><span data-stu-id="4bcd1-128">Terminate the session for a particular protocol (such as ActiveSync)</span></span>  <br/> |<span data-ttu-id="4bcd1-129">Inaktivera protokollet.</span><span class="sxs-lookup"><span data-stu-id="4bcd1-129">Disable the protocol.</span></span> <span data-ttu-id="4bcd1-130">Till exempel (i Exchange eller med PowerShell):</span><span class="sxs-lookup"><span data-stu-id="4bcd1-130">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

<span data-ttu-id="4bcd1-131">Åtgärderna ovan kan utföras på tre platser:</span><span class="sxs-lookup"><span data-stu-id="4bcd1-131">The above operations can be done in three places:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4bcd1-132">**Om du avslutar sessionen här**</span><span class="sxs-lookup"><span data-stu-id="4bcd1-132">**If you terminate the session here**</span></span> <br/> |<span data-ttu-id="4bcd1-133">**Hur lång tid det tar**</span><span class="sxs-lookup"><span data-stu-id="4bcd1-133">**How long it takes**</span></span> <br/> |
|<span data-ttu-id="4bcd1-134">I administrationscentret för Exchange eller med PowerShell</span><span class="sxs-lookup"><span data-stu-id="4bcd1-134">In the Exchange admin center or using PowerShell</span></span>  <br/> |<span data-ttu-id="4bcd1-135">Förväntad fördröjning mindre än 30 minuter</span><span class="sxs-lookup"><span data-stu-id="4bcd1-135">Expected delay is within 30 min</span></span>  <br/> |
|<span data-ttu-id="4bcd1-136">I Azure Active Directory-administratörcenter</span><span class="sxs-lookup"><span data-stu-id="4bcd1-136">In the Azure Active Directory admin center</span></span>  <br/> |<span data-ttu-id="4bcd1-137">Förväntad fördröjning mindre än 60 minuter</span><span class="sxs-lookup"><span data-stu-id="4bcd1-137">Expected delay is 60 min</span></span>  <br/> |
|<span data-ttu-id="4bcd1-138">I en lokal miljö</span><span class="sxs-lookup"><span data-stu-id="4bcd1-138">In an on-premises environment</span></span>  <br/> |<span data-ttu-id="4bcd1-139">Förväntad fördröjning 3 timmar eller mer</span><span class="sxs-lookup"><span data-stu-id="4bcd1-139">Expected delay is 3 hours or more</span></span>  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a><span data-ttu-id="4bcd1-140">Så här får du snabbast svar vid kontouppsägning</span><span class="sxs-lookup"><span data-stu-id="4bcd1-140">How to get fastest response for account termination</span></span>

 <span data-ttu-id="4bcd1-p107">**Snabbast**: Använd administrationscentret för Exchange (använd PowerShell) eller administrationscentret för Azure Active Directory. Det kan ta flera timmar att synkronisera ändringar genom DirSync i en lokal miljö.</span><span class="sxs-lookup"><span data-stu-id="4bcd1-p107">**Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync.</span></span>
  
 <span data-ttu-id="4bcd1-p108">**Snabbast för en användare med närvaro lokalt och i Exchange-datacentret**: Avbryt sessionen med administrationscentret för Azure Active Directory/administrationscentret för Exchange OCH gör även ändringen i den lokala miljön. Ändringen i administrationscentret för Azure Active Directory/administrationscentret för Exchange kommer annars att skrivas över av DirSync.</span><span class="sxs-lookup"><span data-stu-id="4bcd1-p108">**Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="4bcd1-145">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="4bcd1-145">Related articles</span></span>

[<span data-ttu-id="4bcd1-146">Återställa en användare</span><span class="sxs-lookup"><span data-stu-id="4bcd1-146">Restore a user</span></span>](restore-user.md)
