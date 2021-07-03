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
ms.openlocfilehash: e2e1b234eaee3818321761af8f737bad8d131b62
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286329"
---
# <a name="step-7---delete-a-former-employees-user-account"></a><span data-ttu-id="033a4-103">Steg 7 – Ta bort en tidigare anställds användarkonto</span><span class="sxs-lookup"><span data-stu-id="033a4-103">Step 7 - Delete a former employee's user account</span></span>

<span data-ttu-id="033a4-104">När du har sparat och kommit åt den tidigare anställdes alla användardata kan du ta bort den tidigare anställdes konto.</span><span class="sxs-lookup"><span data-stu-id="033a4-104">After you've saved and accessed all the former employee's user data, you can delete the former employee's account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="033a4-p101">Ta inte bort kontot om du har konfigurerat vidarebefordran av e-post eller konverterat postlådan till en delad postlåda. Kontot krävs för att kunna använda vidarebefordran av e-post eller den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="033a4-p101">Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.</span></span>

1. <span data-ttu-id="033a4-107">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="033a4-107">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="033a4-108">Markera namnet på den anställda som du vill ta bort.</span><span class="sxs-lookup"><span data-stu-id="033a4-108">Select the name of the employee that you want to delete.</span></span>
3. <span data-ttu-id="033a4-109">Under användarens namn väljer du Ta **bort användare.**</span><span class="sxs-lookup"><span data-stu-id="033a4-109">Under the user's name, select **Delete user**.</span></span> <span data-ttu-id="033a4-110">Välj de alternativ du vill använda för användaren och välj sedan Ta **bort användare.**</span><span class="sxs-lookup"><span data-stu-id="033a4-110">Choose the options you want for this user, and then select **Delete user**.</span></span> <span data-ttu-id="033a4-111">Om du redan har gett en annan användare åtkomst till den här användarens e-OneDrive behöver du inte göra det igen här.</span><span class="sxs-lookup"><span data-stu-id="033a4-111">If you've already given another user access to this user's email and OneDrive, you don't have to do it again here.</span></span>

<span data-ttu-id="033a4-p103">När du tar bort en användare blir dennes konto inaktivt i ca 30 dagar. Du har tills dess på dig att återställa kontot innan det tas bort permanent.</span><span class="sxs-lookup"><span data-stu-id="033a4-p103">When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.</span></span>

## <a name="watch-delete-a-former-employees-user-account"></a><span data-ttu-id="033a4-114">Titta: Ta bort en tidigare anställds användarkonto</span><span class="sxs-lookup"><span data-stu-id="033a4-114">Watch: Delete a former employee's user account</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR]

<span data-ttu-id="033a4-115">Om den här videon har hjälp dig kan du ta en titt på den[fullständiga utbildningsserien för småföretag och de som är nya för Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="033a4-115">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

## <a name="does-your-organization-use-active-directory"></a><span data-ttu-id="033a4-116">Använder ni Active Directory i organisationen?</span><span class="sxs-lookup"><span data-stu-id="033a4-116">Does your organization use Active Directory?</span></span>

<span data-ttu-id="033a4-117">Om din organisation synkroniserar användarkonton till Microsoft 365 från en lokal Active Directory-miljö måste du ta bort och återställa dessa användarkonton i den lokala Active Directory-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="033a4-117">If your organization synchronizes user accounts to Microsoft 365 from a local Active Directory environment, you must delete and restore those user accounts in your local Active Directory service.</span></span> <span data-ttu-id="033a4-118">Du kan inte ta bort eller återställa dem i Office 365.</span><span class="sxs-lookup"><span data-stu-id="033a4-118">You can't delete or restore them in Office 365.</span></span>

<span data-ttu-id="033a4-119">Mer information om hur du tar bort och återställer användarkonton i Active Directory finns [i Ta bort ett användarkonto.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="033a4-119">To learn how to delete and restore user account in Active Directory, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>
  
<span data-ttu-id="033a4-120">Om du använder en Azure Active Directory, se [PowerShell-cmdleten Remove-MsolUser.](/powershell/module/msonline/remove-msoluser)</span><span class="sxs-lookup"><span data-stu-id="033a4-120">If you're using Azure Active Directory, see the [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet.</span></span>
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a><span data-ttu-id="033a4-121">Vad du behöver veta om att avsluta en anställds e-postsession</span><span class="sxs-lookup"><span data-stu-id="033a4-121">What you need to know about terminating an employee's email session</span></span>

<span data-ttu-id="033a4-122">Här finns information om hur du avslutar en anställds e-post (Exchange).</span><span class="sxs-lookup"><span data-stu-id="033a4-122">Here's information about how to get an employee out of email (Exchange).</span></span>

<br>

****

|<span data-ttu-id="033a4-123">Vad du kan göra</span><span class="sxs-lookup"><span data-stu-id="033a4-123">What you can do</span></span>|<span data-ttu-id="033a4-124">Hur gör du det?</span><span class="sxs-lookup"><span data-stu-id="033a4-124">How you do it</span></span>|
|:-----|:-----|
|<span data-ttu-id="033a4-125">Avsluta en session (till exempel Outlook på webben, Outlook, Exchange ActiveSync, etc.) och framtvinga en ny session</span><span class="sxs-lookup"><span data-stu-id="033a4-125">Terminate a session (such as Outlook on the web, Outlook, Exchange active sync, etc.) and force to open a new session</span></span>|<span data-ttu-id="033a4-126">Återställa lösenord</span><span class="sxs-lookup"><span data-stu-id="033a4-126">Reset password</span></span>|
|<span data-ttu-id="033a4-127">Avsluta en session och blockera åtkomst till framtida sessioner (för alla protokoll)</span><span class="sxs-lookup"><span data-stu-id="033a4-127">Terminate a session and block access to future sessions (for all protocols)</span></span>|<span data-ttu-id="033a4-128">Inaktivera kontot.</span><span class="sxs-lookup"><span data-stu-id="033a4-128">Disable the account.</span></span> <span data-ttu-id="033a4-129">Till exempel (i Exchange eller med PowerShell):</span><span class="sxs-lookup"><span data-stu-id="033a4-129">For example, (in the Exchange admin center or using PowerShell):</span></span> <p>  `Set-Mailbox user@contoso.com -AccountDisabled:$true`|
|<span data-ttu-id="033a4-130">Avbryt sessionen för ett visst protokoll (till exempel ActiveSync)</span><span class="sxs-lookup"><span data-stu-id="033a4-130">Terminate the session for a particular protocol (such as ActiveSync)</span></span>|<span data-ttu-id="033a4-131">Inaktivera protokollet.</span><span class="sxs-lookup"><span data-stu-id="033a4-131">Disable the protocol.</span></span> <span data-ttu-id="033a4-132">Till exempel (i Exchange eller med PowerShell):</span><span class="sxs-lookup"><span data-stu-id="033a4-132">For example, (in the Exchange admin center or using PowerShell):</span></span> <p>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false`|
|

<span data-ttu-id="033a4-133">Åtgärderna ovan kan utföras på tre platser:</span><span class="sxs-lookup"><span data-stu-id="033a4-133">The above operations can be done in three places:</span></span>
  
<br>

****

|<span data-ttu-id="033a4-134">Om du avslutar sessionen här</span><span class="sxs-lookup"><span data-stu-id="033a4-134">If you terminate the session here</span></span>|<span data-ttu-id="033a4-135">Hur lång tid det tar</span><span class="sxs-lookup"><span data-stu-id="033a4-135">How long it takes</span></span>|
|---|---|
|<span data-ttu-id="033a4-136">I administrationscentret för Exchange eller med PowerShell</span><span class="sxs-lookup"><span data-stu-id="033a4-136">In the Exchange admin center or using PowerShell</span></span>|<span data-ttu-id="033a4-137">Förväntad fördröjning mindre än 30 minuter</span><span class="sxs-lookup"><span data-stu-id="033a4-137">Expected delay is within 30 min</span></span>|
|<span data-ttu-id="033a4-138">I Azure Active Directory-administratörcenter</span><span class="sxs-lookup"><span data-stu-id="033a4-138">In the Azure Active Directory admin center</span></span>|<span data-ttu-id="033a4-139">Förväntad fördröjning mindre än 60 minuter</span><span class="sxs-lookup"><span data-stu-id="033a4-139">Expected delay is 60 min</span></span>|
|<span data-ttu-id="033a4-140">I en lokal miljö</span><span class="sxs-lookup"><span data-stu-id="033a4-140">In an on-premises environment</span></span>|<span data-ttu-id="033a4-141">Förväntad fördröjning 3 timmar eller mer</span><span class="sxs-lookup"><span data-stu-id="033a4-141">Expected delay is 3 hours or more</span></span>|
|

### <a name="how-to-get-fastest-response-for-account-termination"></a><span data-ttu-id="033a4-142">Så här får du snabbast svar vid kontouppsägning</span><span class="sxs-lookup"><span data-stu-id="033a4-142">How to get fastest response for account termination</span></span>

<span data-ttu-id="033a4-p107">**Snabbast**: Använd administrationscentret för Exchange (använd PowerShell) eller administrationscentret för Azure Active Directory. Det kan ta flera timmar att synkronisera ändringar genom DirSync i en lokal miljö.</span><span class="sxs-lookup"><span data-stu-id="033a4-p107">**Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync.</span></span>
  
<span data-ttu-id="033a4-p108">**Snabbast för en användare med närvaro lokalt och i Exchange-datacentret**: Avbryt sessionen med administrationscentret för Azure Active Directory/administrationscentret för Exchange OCH gör även ändringen i den lokala miljön. Ändringen i administrationscentret för Azure Active Directory/administrationscentret för Exchange kommer annars att skrivas över av DirSync.</span><span class="sxs-lookup"><span data-stu-id="033a4-p108">**Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="033a4-147">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="033a4-147">Related content</span></span>

<span data-ttu-id="033a4-148">[Återställa en användare](restore-user.md) (artikel)/ [Återställa lösenord](reset-passwords.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="033a4-148">[Restore a user](restore-user.md) (article)/ [Reset passwords](reset-passwords.md) (article)</span></span>
