---
title: Ta bort en användare från organisationen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Lär hur du tar bort ett användarkonto. Bestäm vad du ska göra med användarens e-postadress, OneDrive-innehåll och om du vill behålla produktlicensen eller sluta betala för den.
ms.openlocfilehash: a179915ae92def2a967dc86378346bb905c923e4
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049465"
---
# <a name="delete-a-user-from-your-organization"></a><span data-ttu-id="70f4b-104">Ta bort en användare från organisationen</span><span class="sxs-lookup"><span data-stu-id="70f4b-104">Delete a user from your organization</span></span>
  
||
|:-----|
|<span data-ttu-id="70f4b-105">**Letar du efter hur du tar bort ditt *eget* Microsoft 365-användarkonto som du använder på jobbet eller i skolan? Kontakta den tekniska supporten på ditt arbete eller på universitetet för att göra dessa steg åt dig.**</span><span class="sxs-lookup"><span data-stu-id="70f4b-105">**Looking for how to delete your *own* Microsoft 365 user account that you use at work or school? Contact the technical support at your work or university to do these steps for you.**</span></span>|
   
## <a name="what-you-need-to-know-about-deleting-users"></a><span data-ttu-id="70f4b-106">Allt du behöver veta om att ta bort användare</span><span class="sxs-lookup"><span data-stu-id="70f4b-106">What you need to know about deleting users</span></span>

- <span data-ttu-id="70f4b-107">Endast personer som har [microsoft 365 globala administratörs-](about-admin-roles.md) eller användarhanteringsbehörigheter för företaget eller skolan kan ta bort användarkonton.</span><span class="sxs-lookup"><span data-stu-id="70f4b-107">Only people who have [Microsoft 365 global admin](about-admin-roles.md) or User management permissions for the business or school can delete user accounts.</span></span> 
    
- <span data-ttu-id="70f4b-108">Du har 30 dagar på dig att [återställa](restore-user.md) kontot innan användarens data tas bort permanent.</span><span class="sxs-lookup"><span data-stu-id="70f4b-108">You have 30 days to [restore](restore-user.md) the account before the user's data is permanently deleted.</span></span> 
    
- <span data-ttu-id="70f4b-p102">Om du vill behålla användarens OneDrive-information flyttar du den till en annan plats. Du kan göra det upp till 30 dagar efter du tagit bort kontot. Se [Få åtkomst till och säkerhetskopiera en tidigare anställds användardata](get-access-to-and-back-up-a-former-user-s-data.md). Du har fortfarande åtkomst till användarens SharePoint-filer och behöver inte flytta dem.</span><span class="sxs-lookup"><span data-stu-id="70f4b-p102">If you want to keep the user's OneDrive data, move it to a different location. You can even do this up to 30 days after deleting the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md). You don't need to move their SharePoint files; you'll still have access to them.</span></span>
    
- <span data-ttu-id="70f4b-p103">Om du vill behålla användarens e-post flyttar du den till en annan plats **INNAN** du tar bort kontot. Om du redan har tagit bort kontot kan du återställa det inom 30 dagar. Flytta sedan e-postdata och ta bort kontot. Se [Få åtkomst till och säkerhetskopiera en tidigare anställds användardata](get-access-to-and-back-up-a-former-user-s-data.md).</span><span class="sxs-lookup"><span data-stu-id="70f4b-p103">If you want to keep the user's email, **BEFORE** you delete the account, move the email to a different location. If you've already deleted the account: if it's been less than 30 days you can restore it, then move the email data, then delete the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span>
    
- <span data-ttu-id="70f4b-116">Om du har en Enterprise-prenumeration som Office 365 Enterprise E3 kan du bevara postlådedata för ett borttaget användarkonto genom att omvandla dem till en *inaktiv postlåda*.</span><span class="sxs-lookup"><span data-stu-id="70f4b-116">If you have an Enterprise subscription like Office 365 Enterprise E3, you can preserve the mailbox data of a deleted user account by turning it into an *inactive mailbox*.</span></span> <span data-ttu-id="70f4b-117">Lär dig mer i [Hantera inaktiva postlådor i Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="70f4b-117">To learn more, see [Manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span>


## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a><span data-ttu-id="70f4b-118">Global administratör: Ta bort medarbetare, sluta betala för deras licens och välj vad du vill göra med deras e-postadress och OneDrive-innehåll</span><span class="sxs-lookup"><span data-stu-id="70f4b-118">Global admin: Delete a user, stop paying for their license, and choose what to do with their email and OneDrive content</span></span>

<span data-ttu-id="70f4b-119">Om du är global administratör och tar bort en användare kan du ge andra användare tillgång till användarens e-post. Du kan också välja vad du vill göra med OneDrive-innehållet.</span><span class="sxs-lookup"><span data-stu-id="70f4b-119">If you are a global administrator, when you delete a user you can also give another user access to their email, and choose what to do with their OneDrive content.</span></span> 

  
### <a name="things-to-consider"></a><span data-ttu-id="70f4b-120">Saker att tänka på ...</span><span class="sxs-lookup"><span data-stu-id="70f4b-120">Things to consider...</span></span>

<span data-ttu-id="70f4b-121">Innan du börjar ska du bestämma dig för vad du vill göra med användarens e-post och OneDrive-innehåll, och om du vill behålla licensen eller sluta betala för den.</span><span class="sxs-lookup"><span data-stu-id="70f4b-121">Before you begin, think about what you want to do with the user's email and OneDrive content, and whether you want to keep the license or stop paying for it.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="70f4b-122">Produktlicenser</span><span class="sxs-lookup"><span data-stu-id="70f4b-122">Product licenses</span></span>  <br/> |<span data-ttu-id="70f4b-p105">Du kan ta bort licensen från användaren och ta bort den från dina prenumerationer om du vill sluta betala för den licensen. Om du väljer det här alternativet kommer licensen att tas bort automatiskt från dina prenumerationer.  </span><span class="sxs-lookup"><span data-stu-id="70f4b-p105">You can remove the license from the user and remove it from your subscriptions to stop paying for that license. If you select this option, the license will be removed automatically from your subscriptions.  </span></span><br/><br/> <span data-ttu-id="70f4b-p106">**Du kan inte ta bort licensen** om du har köpt den via en partner eller via volymlicensiering. Om du betalar för ett årsabonnemang eller om du är mitt i en faktureringsperiod kan du inte ta bort licensen från din prenumeration förrän abonnemanget har gått ut.  </span><span class="sxs-lookup"><span data-stu-id="70f4b-p106">**You can't remove the license** if you bought it through a Partner or volume licensing. If you are paying for an annual plan or if you are in the middle of a billing cycle, you won't be able to remove the license from your subscription until your commitment is completed.  </span></span><br/> |
|<span data-ttu-id="70f4b-127">OneDrive-innehåll</span><span class="sxs-lookup"><span data-stu-id="70f4b-127">OneDrive content</span></span>  <br/> |<span data-ttu-id="70f4b-128">Om användaren har sparat sina filer i OneDrive kan du ge en annan användare tillgång till filerna.</span><span class="sxs-lookup"><span data-stu-id="70f4b-128">If the user saved their files to OneDrive, you can give another user access to these files.</span></span>  <br/><br/> <span data-ttu-id="70f4b-p107">Du måste flytta filerna som du vill behålla inom den kvarhållningstid som har angetts för OneDrive-filer. **Kvarhållningstiden är som standard 30 dagar.** Om du inte flyttar filerna inom kvarhållningstiden efter att du har tagit bort användaren tas OneDrive-innehållet bort permanent. Om du vill öka antalet dagar som du kvarhåller OneDrive-filer för borttagna konton kan du läsa mer i [Ange OneDrive-kvarhållning för borttagna användare](https://docs.microsoft.com/onedrive/set-retention).  </span><span class="sxs-lookup"><span data-stu-id="70f4b-p107">You'll need to move the files you want to keep within the retention period that is set for OneDrive files. **By default, the retention period is 30 days.** If you don't move the files within the retention period after deleting the user, the OneDrive content will be permanently deleted. To increase the number of days that you retain OneDrive files for deleted accounts, see [Set the OneDrive retention for deleted users](https://docs.microsoft.com/onedrive/set-retention).  </span></span><br/><br/> <span data-ttu-id="70f4b-133">**Viktigt!**</span><span class="sxs-lookup"><span data-stu-id="70f4b-133">**Important!**</span></span> <span data-ttu-id="70f4b-134">Om den borttagna användaren använde en personlig dator när denna ladda ned filer från SharePoint och OneDrive är det omöjligt för dig att rensa filerna som de har lagrat på datorn.</span><span class="sxs-lookup"><span data-stu-id="70f4b-134">If the deleted user used a personal computer to download files from SharePoint and OneDrive, there's no way for you to wipe those files they stored on their computer.</span></span> <span data-ttu-id="70f4b-135">Användaren har fortfarande åtkomst till alla filer som har synkroniserats från OneDrive.</span><span class="sxs-lookup"><span data-stu-id="70f4b-135">They will continue to have access to any files that were synced from OneDrive.</span></span>           |
|<span data-ttu-id="70f4b-136">E-post</span><span class="sxs-lookup"><span data-stu-id="70f4b-136">Email</span></span>  <br/> | <span data-ttu-id="70f4b-p109">Om du ger en annan användare tillgång till den borttagna användarens e-post konverteras den borttagna användarens postlåda till en delad postlåda. Då har den nya ägaren till postlådan tillgång till den och kan kontrollera nya e-postmeddelanden. Du har även följande alternativ:  </span><span class="sxs-lookup"><span data-stu-id="70f4b-p109">Giving another user access to the deleted user's email will convert the deleted user's mailbox to a shared mailbox. The new mailbox owner can then access the mailbox and monitor for new email. You'll also have the following options:  </span></span><br/>  <br/><span data-ttu-id="70f4b-140">Ändra visningsnamnet – Vi rekommenderar att du ändrar visningsnamnet så att det blir enklare att identifiera den delade postlådan i listan över aktiva användare.</span><span class="sxs-lookup"><span data-stu-id="70f4b-140">Change the display name - We recommend changing the display name so that it will be easy to identify the shared mailbox in the Active users list.</span></span>  <br/>  <span data-ttu-id="70f4b-p110">Aktivera automatiska svar – Det finns redan ett färdigt, artigt automatiskt svar skrivet. Du kan skicka olika automatiska svar till personer inom organisationen och till personer utanför organisationen.  </span><span class="sxs-lookup"><span data-stu-id="70f4b-p110">Turn on automatic replies - We've already written a polite automatic reply for you. You can send a different automatic replies to people within your organization and people from outside your organization.  </span></span><br/> <br/> <span data-ttu-id="70f4b-143">Rensa alias-adresser – Ytterligare e-postadresser för användare kallas alias.</span><span class="sxs-lookup"><span data-stu-id="70f4b-143">Clean up aliases - Aliases are additional email addresses for users.</span></span> <span data-ttu-id="70f4b-144">De används inte i en del organisationer, så om du inte har några behöver du inte göra något mera här.</span><span class="sxs-lookup"><span data-stu-id="70f4b-144">Some organizations don't use them, so if you don't have any you don't need to do anything else here.</span></span> <span data-ttu-id="70f4b-145">Om användaren har ett eller flera alias rekommenderar vi att du tar bort dem så att du kan använda de e-postadresserna igen.</span><span class="sxs-lookup"><span data-stu-id="70f4b-145">If the user does have aliases, we recommend removing them so that you can re-use those email addresses.</span></span> <span data-ttu-id="70f4b-146">Annars kan du inte återanvända dessa e-postadresser förrän kvarhållningsperioden för borttagna postlådor har passerats.</span><span class="sxs-lookup"><span data-stu-id="70f4b-146">Otherwise, you can't re-use those email addresses until the retention period for deleted mailboxes has passed.</span></span> <span data-ttu-id="70f4b-147">Som standard är en borttagen postlåda möjlig att återskapa i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="70f4b-147">By default, a deleted mailbox is recoverable for 30 days.</span></span> <span data-ttu-id="70f4b-148">Mer information finns i [ta bort eller återställa användarpostlådor i Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span><span class="sxs-lookup"><span data-stu-id="70f4b-148">For more information, see  [Delete or restore user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span></span> <br/> |
|<span data-ttu-id="70f4b-149">Active Directory</span><span class="sxs-lookup"><span data-stu-id="70f4b-149">Active Directory</span></span>  <br/> |<span data-ttu-id="70f4b-150">Om ditt företag använder **Active Directory** som synkroniseras med Azure AD måste du ta bort användarkontot från Active Directory.</span><span class="sxs-lookup"><span data-stu-id="70f4b-150">If your business uses **Active Directory** that is synchronizing with Azure AD, you need to delete the user account from Active Directory.</span></span> <span data-ttu-id="70f4b-151">Du kan inte göra det via Office 365.</span><span class="sxs-lookup"><span data-stu-id="70f4b-151">You can't do it through Office 365.</span></span> <span data-ttu-id="70f4b-152">Anvisningar finns i[Ta bort ett användarkonto](https://go.microsoft.com/fwlink/p/?linkid=841808).</span><span class="sxs-lookup"><span data-stu-id="70f4b-152">For instructions, see [Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808).</span></span>  <br/> |
   
### <a name="get-started"></a><span data-ttu-id="70f4b-153">Komma igång</span><span class="sxs-lookup"><span data-stu-id="70f4b-153">Get started</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="70f4b-154">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="70f4b-154">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

<span data-ttu-id="70f4b-155">Du blir guidad genom processen för att ta bort en användare. Så här kommer du igång.</span><span class="sxs-lookup"><span data-stu-id="70f4b-155">Since the guided experience walks through the steps to delete a user, here's how to get started.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="70f4b-156">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="70f4b-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="70f4b-157">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="70f4b-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="70f4b-158">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="70f4b-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="70f4b-159">Markera användaren som du vill ta bort och välj sedan **Ta bort användare**.</span><span class="sxs-lookup"><span data-stu-id="70f4b-159">Select the user you want to delete, and then select **Delete user**.</span></span>

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a><span data-ttu-id="70f4b-160">Användarhanteringsadministratör: Ta bort en eller flera användare från Office 365</span><span class="sxs-lookup"><span data-stu-id="70f4b-160">User management admin: Delete one or more users from Office 365</span></span>


> [!IMPORTANT]
> <span data-ttu-id="70f4b-p113">Ta inte bort en användares konto om du har [konverterat det till en delad postlåda](../email/convert-user-mailbox-to-shared-mailbox.md) eller om du har konfigurerat vidarebefordran av e-post på kontot. Dessa funktioner behöver fortfarande kontot. En delad postlåda kräver ingen licens. Om du har konverterat kontot till en delad postlåda kan du [sluta betala för licensen](#stop-paying-for-the-license). Om du har konfigurerat vidarebefordran av e-post på kontot kan du inte ta bort licensen. Om du gör det stoppas vidarebefordran av e-post och inaktiverar postlådan.</span><span class="sxs-lookup"><span data-stu-id="70f4b-p113">Don't delete a user's account if you've [converted it to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md) or if you've set up email forwarding on the account. Those functions still need the account. A shared mailbox doesn't require a license. If you've converted the account to a shared mailbox you can [Stop paying for the license](#stop-paying-for-the-license). If you've set up email forwarding on the account, you can't remove the license. Doing so will stop email forwarding and deactivate the mailbox.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="70f4b-167">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="70f4b-167">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="70f4b-168">Markera namnen på de användare som du vill ta bort, välj **Fler alternativ** (**...**) och sedan **Ta bort användare**. </span><span class="sxs-lookup"><span data-stu-id="70f4b-168">Select the names of the users that you want to delete, select **More options** (**...**), and then choose  **Delete user**.</span></span>

   <span data-ttu-id="70f4b-169">**Du betalar fortfarande för licensen** även om du har tagit bort användarens konto.</span><span class="sxs-lookup"><span data-stu-id="70f4b-169">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="70f4b-170">Se nästa procedur om du vill sluta betala för licensen.</span><span class="sxs-lookup"><span data-stu-id="70f4b-170">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="70f4b-171">Du kan sedan tilldela licensen till en annan användare.</span><span class="sxs-lookup"><span data-stu-id="70f4b-171">Or, you can assign the license to another user.</span></span> <span data-ttu-id="70f4b-172">Den kommer inte automatiskt att tilldelas till någon.</span><span class="sxs-lookup"><span data-stu-id="70f4b-172">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="70f4b-173">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="70f4b-173">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="70f4b-174">Markera namnen på de användare som du vill ta bort och välj **Ta bort användare** i rutan **Massåtgärder**. </span><span class="sxs-lookup"><span data-stu-id="70f4b-174">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="70f4b-175">**Du betalar fortfarande för licensen** även om du har tagit bort användarens konto.</span><span class="sxs-lookup"><span data-stu-id="70f4b-175">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="70f4b-176">Se nästa procedur om du vill sluta betala för licensen.</span><span class="sxs-lookup"><span data-stu-id="70f4b-176">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="70f4b-177">Du kan sedan tilldela licensen till en annan användare.</span><span class="sxs-lookup"><span data-stu-id="70f4b-177">Or, you can assign the license to another user.</span></span> <span data-ttu-id="70f4b-178">Den kommer inte automatiskt att tilldelas till någon.</span><span class="sxs-lookup"><span data-stu-id="70f4b-178">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="70f4b-179">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="70f4b-179">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="70f4b-180">Markera namnen på de användare som du vill ta bort och välj **Ta bort användare** i rutan **Massåtgärder**. </span><span class="sxs-lookup"><span data-stu-id="70f4b-180">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="70f4b-181">**Du betalar fortfarande för licensen** även om du har tagit bort användarens konto.</span><span class="sxs-lookup"><span data-stu-id="70f4b-181">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="70f4b-182">Se nästa procedur om du vill sluta betala för licensen.</span><span class="sxs-lookup"><span data-stu-id="70f4b-182">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="70f4b-183">Du kan sedan tilldela licensen till en annan användare.</span><span class="sxs-lookup"><span data-stu-id="70f4b-183">Or, you can assign the license to another user.</span></span> <span data-ttu-id="70f4b-184">Den kommer inte automatiskt att tilldelas till någon.</span><span class="sxs-lookup"><span data-stu-id="70f4b-184">It won't be assigned to someone automatically.</span></span>

::: moniker-end

### <a name="stop-paying-for-the-license"></a><span data-ttu-id="70f4b-185">Sluta betala för licensen</span><span class="sxs-lookup"><span data-stu-id="70f4b-185">Stop paying for the license</span></span>

<span data-ttu-id="70f4b-186">Att minska antalet licenser är ett separat steg som endast kan utföras av den globala administratören eller faktureringsadministratören.</span><span class="sxs-lookup"><span data-stu-id="70f4b-186">Reducing the number of licenses is a separate step that can only be performed by the global admin or billing admin.</span></span> 
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="70f4b-187">Gå till sidan \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Faktureringsprodukter</a> i administrationscentret. **Billing**</span><span class="sxs-lookup"><span data-stu-id="70f4b-187">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span> <span data-ttu-id="70f4b-188">Om du inte ser det här alternativet är du inte en global administratör eller faktureringsadministratör och kan inte genomföra detta steg.</span><span class="sxs-lookup"><span data-stu-id="70f4b-188">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="70f4b-189">Markera prenumerationen (om du har fler än en) och välj sedan **Lägg till/ta bort licenser** för att ta bort licensen så att du inte betalar för den förrän du anställer en ny person.</span><span class="sxs-lookup"><span data-stu-id="70f4b-189">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="70f4b-190">När du sedan följer anvisningarna och lägger till en annan person i verksamheten uppmanas du samtidigt att köpa en licens.</span><span class="sxs-lookup"><span data-stu-id="70f4b-190">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="70f4b-191">Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Prenumerationer</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="70f4b-191">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="70f4b-192">Om du inte ser det här alternativet är du inte en global administratör eller faktureringsadministratör och kan inte genomföra detta steg.</span><span class="sxs-lookup"><span data-stu-id="70f4b-192">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="70f4b-193">Markera prenumerationen (om du har fler än en) och välj sedan **Lägg till/ta bort licenser** för att ta bort licensen så att du inte betalar för den förrän du anställer en ny person.</span><span class="sxs-lookup"><span data-stu-id="70f4b-193">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="70f4b-194">När du sedan följer anvisningarna och lägger till en annan person i verksamheten uppmanas du samtidigt att köpa en licens.</span><span class="sxs-lookup"><span data-stu-id="70f4b-194">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="70f4b-195">Gå till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Prenumerationer</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="70f4b-195">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="70f4b-196">Om du inte ser det här alternativet är du inte en global administratör eller faktureringsadministratör och kan inte genomföra detta steg.</span><span class="sxs-lookup"><span data-stu-id="70f4b-196">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="70f4b-197">Markera prenumerationen (om du har fler än en) och välj sedan **Lägg till/ta bort licenser** för att ta bort licensen så att du inte betalar för den förrän du anställer en ny person.</span><span class="sxs-lookup"><span data-stu-id="70f4b-197">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="70f4b-198">När du sedan följer anvisningarna och lägger till en annan person i verksamheten uppmanas du samtidigt att köpa en licens.</span><span class="sxs-lookup"><span data-stu-id="70f4b-198">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end 

## <a name="delete-many-users-at-the-same-time"></a><span data-ttu-id="70f4b-199">Ta bort flera användare samtidigt</span><span class="sxs-lookup"><span data-stu-id="70f4b-199">Delete many users at the same time</span></span>

<span data-ttu-id="70f4b-200">Läs mer om PowerShell-cmdleten [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230).</span><span class="sxs-lookup"><span data-stu-id="70f4b-200">See the [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet.</span></span>

## <a name="fix-issues-with-deleting-a-user"></a><span data-ttu-id="70f4b-201">Åtgärda problem med att ta bort en användare</span><span class="sxs-lookup"><span data-stu-id="70f4b-201">Fix issues with deleting a user</span></span>

<span data-ttu-id="70f4b-202">Här är de vanligaste problemen som uppstår när du tar bort en användare:</span><span class="sxs-lookup"><span data-stu-id="70f4b-202">Here are the most common issues people encounter when deleting a user:</span></span>
  
- <span data-ttu-id="70f4b-p120">**Du får ett felmeddelande i stil med "Användare kan inte tas bort. Försök igen senare."** Kontrollera om kontot är inställt att vidarebefordra e-post eller om det har konverterats till en delad postlåda. Båda dessa kan orsaka felet. Ta inte bort ett konto som vidarebefordrar e-postmeddelanden eller har konverterats till en delad postlåda.</span><span class="sxs-lookup"><span data-stu-id="70f4b-p120">**You get an error message along the lines of "User cannot be deleted. Please try again later."** Doublecheck whether the account has email forwarding set up on it, or it's been converted to a shared mailbox. Both of these will cause that error. Don't delete the account if it has email forwarding or it's been converted to a shared mailbox.</span></span>

- <span data-ttu-id="70f4b-207">**Du har inte tillräckliga behörigheter för att ta bort en användare**.</span><span class="sxs-lookup"><span data-stu-id="70f4b-207">**You don't have the appropriate permissions to delete a user**.</span></span> <span data-ttu-id="70f4b-208">Endast personer som är [globala administratörer för Microsoft 365 eller användarhanteringsadministratörer](about-admin-roles.md) kan ta bort användare.</span><span class="sxs-lookup"><span data-stu-id="70f4b-208">Only people who are [Microsoft 365 global admins or user management admins](about-admin-roles.md) can delete users.</span></span> <span data-ttu-id="70f4b-209">Det är i regel skolans eller företagets tekniska support.</span><span class="sxs-lookup"><span data-stu-id="70f4b-209">Usually this is the technical support in your school or business.</span></span>

- <span data-ttu-id="70f4b-p122">**Du kan ta bort användaren, men hans eller hennes namn fortsätter visas i den globala adressboken**. Detta inträffar när ett företag använder Active Directory. Du måste ta bort användarkontot från Active Directory. Anvisningar finns i den här TechNet-artikeln: [Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808) (Ta bort ett användarkonto).</span><span class="sxs-lookup"><span data-stu-id="70f4b-p122">**You delete the user but their name continues appear in your global address book**. This happens when a business is using Active Directory. You have to delete the users account from Active Directory. For instructions, see this TechNet article: [Delete a User Account.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span></span>

||
|:-----|
|<span data-ttu-id="70f4b-214">**Vill du ta bort Microsoft 365 från datorn? Gå till [Avsluta prenumerationen](../../commerce/subscriptions/cancel-your-subscription.md).**</span><span class="sxs-lookup"><span data-stu-id="70f4b-214">**Do you want to delete Microsoft 365 from your computer? Go to [Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).**</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="70f4b-215">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="70f4b-215">Related articles</span></span>

[<span data-ttu-id="70f4b-216">Återställa en användare</span><span class="sxs-lookup"><span data-stu-id="70f4b-216">Restore a user</span></span>](restore-user.md)
  
[<span data-ttu-id="70f4b-217">Ta bort meddelande permanent</span><span class="sxs-lookup"><span data-stu-id="70f4b-217">Permanently delete a mailbox</span></span>](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[<span data-ttu-id="70f4b-218">Ta bort en tidigare anställd från Office 365</span><span class="sxs-lookup"><span data-stu-id="70f4b-218">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="70f4b-219">Lägga till en ny anställd i Office 365</span><span class="sxs-lookup"><span data-stu-id="70f4b-219">Add a new employee to Office 365</span></span>](add-new-employee.md)

<span data-ttu-id="70f4b-220">[Ta bort ett användarkonto](https://go.microsoft.com/fwlink/p/?linkid=841808): Gör följande om ditt företag använder **Active Directory** som synkroniseras med Azure AD.</span><span class="sxs-lookup"><span data-stu-id="70f4b-220">[Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808): Use these instructions if your business uses **Active Directory** that is synchronizing with Azure AD.</span></span> <span data-ttu-id="70f4b-221">Du kan inte göra det via Office 365.</span><span class="sxs-lookup"><span data-stu-id="70f4b-221">You can't do it through Office 365.</span></span>