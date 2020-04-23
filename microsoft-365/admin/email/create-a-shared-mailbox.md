---
title: Skapa en delad postlåda
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: När en delad postlåda har skapats kan flera personer i verksamheten dela på ansvaret att läsa och svara på e-postmeddelanden som skickas till en adress.
ms.openlocfilehash: 35711e1a17a244a9f68ac88daf665f0328b293b4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628909"
---
# <a name="create-a-shared-mailbox"></a><span data-ttu-id="ff239-103">Skapa en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="ff239-103">Create a shared mailbox</span></span> 

> [!NOTE]
> <span data-ttu-id="ff239-104">Om din organisation använder en Exchange-hybridmiljö, använder du det lokala administrationscentret för Exchange när du skapar och hanterar delade postlådor.</span><span class="sxs-lookup"><span data-stu-id="ff239-104">If your organization uses a hybrid Exchange environment, you should use the on-premises Exchange admin center (EAC) to create and manage shared mailboxes.</span></span> <span data-ttu-id="ff239-105">Se [Så här skapar du en delad postlåda i administrationscentret för Exchange](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)</span><span class="sxs-lookup"><span data-stu-id="ff239-105">See [Create shared mailboxes in the Exchange admin center](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)</span></span><br><br>
> <span data-ttu-id="ff239-106">Om du inte är säker på ifall du ska skapa en delad postlåda eller en Microsoft 365-grupp för Outlook, kan du läsa mer i [Jämföra grupper](../create-groups/compare-groups.md). </span><span class="sxs-lookup"><span data-stu-id="ff239-106">If you're not sure if you should create a shared mailbox or a Microsoft 365 group for Outlook, see [Compare groups](../create-groups/compare-groups.md) for some guidance.</span></span> <span data-ttu-id="ff239-107">Observera att det för närvarande inte är möjligt att migrera en delad postlåda till en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="ff239-107">Note that currently, it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="ff239-108">Om det är något som du vill kunna göra, kan du låta oss veta detta genom att [rösta här](https://go.microsoft.com/fwlink/?linkid=871518).</span><span class="sxs-lookup"><span data-stu-id="ff239-108">If this is something you want, let us know by [voting here](https://go.microsoft.com/fwlink/?linkid=871518).</span></span>

<span data-ttu-id="ff239-p103">Det är enkelt att skapa en delad postlåda så att en grupp användare kan övervaka och skicka e-post från en gemensam e-postadress, exempelvis info@contoso.com. När en person i gruppen svarar på ett meddelande till den delade postlådan ser svarsmeddelandet ut att komma från den delade postlådan, inte från den enskilda användaren.</span><span class="sxs-lookup"><span data-stu-id="ff239-p103">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span></span>

<span data-ttu-id="ff239-111">I delade postlådor finns det en delad kalender.</span><span class="sxs-lookup"><span data-stu-id="ff239-111">Shared mailboxes include a shared calendar.</span></span> <span data-ttu-id="ff239-112">Många små företag tycker att det är praktiskt att ha en delad kalender där alla lägger in sina avtalade tider.</span><span class="sxs-lookup"><span data-stu-id="ff239-112">A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments.</span></span> <span data-ttu-id="ff239-113">Om det till exempel finns tre personer som utför kundbesök kan de alla skriva in sina avtalade tider i kalendern.</span><span class="sxs-lookup"><span data-stu-id="ff239-113">For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments.</span></span> <span data-ttu-id="ff239-114">Det är ett bra sätt att hålla alla informerade om var alla befinner sig.</span><span class="sxs-lookup"><span data-stu-id="ff239-114">This is an easy way to keep everyone informed where people are.</span></span>

<span data-ttu-id="ff239-115">Innan du skapar en delad postlåda bör du läsa [Om delade postlådor](about-shared-mailboxes.md) för att få mer information.</span><span class="sxs-lookup"><span data-stu-id="ff239-115">Before creating a shared mailbox, be sure to read [About shared mailboxes](about-shared-mailboxes.md) for more information.</span></span>

## <a name="create-a-shared-mailbox-and-add-members"></a><span data-ttu-id="ff239-116">Skapa en delad postlåda och lägg till medlemmar</span><span class="sxs-lookup"><span data-stu-id="ff239-116">Create a shared mailbox and add members</span></span>
  
1. <span data-ttu-id="ff239-117">Logga in med ett globalt administratörskonto eller Exchange-administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="ff239-117">Sign in with a global admin account or Exchange admin account.</span></span> <span data-ttu-id="ff239-118">Om du får meddelandet ”**Du har inte behörighet att komma åt den här sidan eller utföra den här åtgärden**”, är du inte någon administratör.</span><span class="sxs-lookup"><span data-stu-id="ff239-118">If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin.</span></span> 

::: moniker range="o365-worldwide"

2. <span data-ttu-id="ff239-119">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="ff239-119">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

2. <span data-ttu-id="ff239-120">I [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=848041) går du till sidan **Grupper** \> **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="ff239-120">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

2. <span data-ttu-id="ff239-121">I [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=850627) går du till sidan **Grupper** \> **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="ff239-121">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end
    
3. <span data-ttu-id="ff239-122">På sidan **Delade postlådor** väljer du **+ Lägg till en postlåda**.</span><span class="sxs-lookup"><span data-stu-id="ff239-122">On the **Shared mailboxes** page, select **+ Add a mailbox**.</span></span> <span data-ttu-id="ff239-123">Ange ett namn på den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ff239-123">Enter a name for the shared mailbox.</span></span> <span data-ttu-id="ff239-124">Guiden väljer sedan e-postadress, men du kan redigera den.</span><span class="sxs-lookup"><span data-stu-id="ff239-124">Then the wizard chooses the email address, but you can edit it.</span></span>
    
    ![Namnge den delade postlådan.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. <span data-ttu-id="ff239-126">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="ff239-126">Select **Add**.</span></span> <span data-ttu-id="ff239-127">Det kan ta några minuter innan du kan lägga till medlemmar.</span><span class="sxs-lookup"><span data-stu-id="ff239-127">It may take a few minutes before you can add members.</span></span>

5. <span data-ttu-id="ff239-128">Under **Nästa steg** väljer du **Lägg till medlemmar i den här postlådan**.</span><span class="sxs-lookup"><span data-stu-id="ff239-128">Under **Next steps**, select **Add members to this mailbox**.</span></span> <span data-ttu-id="ff239-129">Medlemmarna är de personer som kan se inkommande e-post till den delade postlådan och utgående svar.</span><span class="sxs-lookup"><span data-stu-id="ff239-129">Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.</span></span>

   ![Välj Lägg till medlemmar](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. <span data-ttu-id="ff239-131">Välj knappen **+Lägg till medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="ff239-131">Select the **+Add members** button.</span></span> <span data-ttu-id="ff239-132">Markera de personer som ska använda den delade postlådan och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ff239-132">Put a check mark next to the people who you want to use this shared mailbox, and select **Save**.</span></span>

   ![Tilldela medlemmar till den delade postlådan](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. <span data-ttu-id="ff239-134">Välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="ff239-134">Select **Close**.</span></span>

<span data-ttu-id="ff239-135">Du har en delad postlåda och den innehåller en delad kalender.</span><span class="sxs-lookup"><span data-stu-id="ff239-135">You have a shared mailbox and it includes a shared calendar.</span></span> <span data-ttu-id="ff239-136">Gå vidare till nästa steg: Blockera inloggning för den delade postlådans konto.</span><span class="sxs-lookup"><span data-stu-id="ff239-136">Now go on to the next step: block sign-in for the shared mailbox account.</span></span>

## <a name="block-sign-in-for-the-shared-mailbox-account"></a><span data-ttu-id="ff239-137">Blockera inloggning för den delade postlådans konto</span><span class="sxs-lookup"><span data-stu-id="ff239-137">Block sign-in for the shared mailbox account</span></span>

<span data-ttu-id="ff239-138">Alla delade postlådor har ett motsvarande användarkonto.</span><span class="sxs-lookup"><span data-stu-id="ff239-138">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="ff239-139">Lade du märke till att du inte behövde ange något lösenord när du skapade den delade postlådan?</span><span class="sxs-lookup"><span data-stu-id="ff239-139">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="ff239-140">Kontot har ett lösenord, men det genereras av systemet (okänt).</span><span class="sxs-lookup"><span data-stu-id="ff239-140">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="ff239-141">Du ska inte använda kontot för att logga in på den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ff239-141">You aren't supposed to use the account to log in to the shared mailbox.</span></span>

<span data-ttu-id="ff239-142">Men vad händer om en administratör återställer lösenordet för den delade postlådans användarkonto?</span><span class="sxs-lookup"><span data-stu-id="ff239-142">But what if an admin simply resets the password of the shared mailbox user account?</span></span> <span data-ttu-id="ff239-143">Eller om en angripare får åtkomst till kontoautentiseringsuppgifterna för den delade postlådan?</span><span class="sxs-lookup"><span data-stu-id="ff239-143">Or what if an attacker gains access to the shared mailbox account credentials?</span></span> <span data-ttu-id="ff239-144">Det skulle innebära att användarkontot kan logga in på den delade postlådan och skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="ff239-144">This would allow the user account to log in to the shared mailbox and send email.</span></span> <span data-ttu-id="ff239-145">För att förhindra detta måste du blockera inloggningen för det konto som är kopplat till den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ff239-145">To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="ff239-146">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="ff239-146">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="ff239-147">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ff239-147">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="ff239-148">Leta reda på kontot för den delade postlådan i listan med användarkonton (ändra t.ex. filtret till **Användare utan licens**).</span><span class="sxs-lookup"><span data-stu-id="ff239-148">In the list of user accounts, find the account for the shared mailbox (for example, change the filter to **Unlicensed users**).</span></span>

3. <span data-ttu-id="ff239-149">Välj användaren för att öppna fönstret Egenskaper och välj sedan ikonen **Blockera den här användaren** ![Skärmbild av ikonen Blockera den här användaren](../../media/block-user-icon.png).</span><span class="sxs-lookup"><span data-stu-id="ff239-149">Select the user to open their properties pane, and then select the **Block this user** icon ![Screen shot of the Block this user icon](../../media/block-user-icon.png).</span></span>

   <span data-ttu-id="ff239-150">**Obs**! Om kontot redan är blockerat visas **Inloggning blockerad** längst upp och ikonen är **Avblockera den här användaren**.</span><span class="sxs-lookup"><span data-stu-id="ff239-150">**Note**: If the account is already blocked, **Sign in blocked** will appear at the top and the icon will read **Unblock this user**.</span></span>

4. <span data-ttu-id="ff239-151">I fönstret **Blockera den här användaren?** väljer du **Blockera användaren från att logga in** och sedan **Spara ändringarna**.</span><span class="sxs-lookup"><span data-stu-id="ff239-151">In the **Block this user?** pane, select **Block the user from signing in**, and then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ff239-152">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ff239-152">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="ff239-153">Leta reda på kontot för den delade postlådan i listan med användarkonton (ändra t.ex. vyn till **Användare utan licens**) och markera sedan kontot.</span><span class="sxs-lookup"><span data-stu-id="ff239-153">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="ff239-154">Välj **Blockera inloggning** i den utfällbara menyn för egenskaper.</span><span class="sxs-lookup"><span data-stu-id="ff239-154">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="ff239-155">**Obs!** Om kontot redan har blockerats visar knappen **Tillåt inloggning**.</span><span class="sxs-lookup"><span data-stu-id="ff239-155">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="ff239-156">Kontrollera att Blockera användaren från att logga in är markerad i den utfällbara menyn **Redigera inloggningsstatus**. Välj **Spara** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="ff239-156">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ff239-157">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ff239-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="ff239-158">Leta reda på kontot för den delade postlådan i listan med användarkonton (ändra t.ex. vyn till **Användare utan licens**) och markera sedan kontot.</span><span class="sxs-lookup"><span data-stu-id="ff239-158">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="ff239-159">Välj **Blockera inloggning** i den utfällbara menyn för egenskaper.</span><span class="sxs-lookup"><span data-stu-id="ff239-159">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="ff239-160">**Obs!** Om kontot redan har blockerats visar knappen **Tillåt inloggning**.</span><span class="sxs-lookup"><span data-stu-id="ff239-160">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="ff239-161">Kontrollera att Blockera användaren från att logga in är markerad i den utfällbara menyn **Redigera inloggningsstatus**. Välj **Spara** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="ff239-161">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>
::: moniker-end

<span data-ttu-id="ff239-162">Om du vill ha anvisningar om hur du blockerar inloggning för konton som använder Azure AD PowerShell (med flera konton samtidigt), kan du läsa [Blockera användarkonton med Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="ff239-162">For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).</span></span>

## <a name="add-the-shared-mailbox-to-outlook"></a><span data-ttu-id="ff239-163">Lägga till den delade postlådan i Outlook</span><span class="sxs-lookup"><span data-stu-id="ff239-163">Add the shared mailbox to Outlook</span></span>

<span data-ttu-id="ff239-164">Om ditt företag har aktiverat automatisk mappning (det har de flesta som standard), visas den delade postlådan i användarnas Outlook-app automatiskt när de har stängt och startat om Outlook.</span><span class="sxs-lookup"><span data-stu-id="ff239-164">If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.</span></span> 

<span data-ttu-id="ff239-165">Automatisk mappning är inställt på användarens postlåda, inte på den delade postlådan.  </span><span class="sxs-lookup"><span data-stu-id="ff239-165">Automapping is set on the user's mailbox, not the shared mailbox.</span></span> <span data-ttu-id="ff239-166">Det här innebär att automatisk mappning inte fungerar om du försöker använda säkerhetsgruppen för att hantera vem som har åtkomst till den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ff239-166">This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work.</span></span> <span data-ttu-id="ff239-167">Om du vill använda automatisk mappning måste du uttryckligen tilldela behörigheter.</span><span class="sxs-lookup"><span data-stu-id="ff239-167">So, if you want automapping, you have to assign permissions explicitly.</span></span> <span data-ttu-id="ff239-168">Automatisk mappning är aktiverat som standard.</span><span class="sxs-lookup"><span data-stu-id="ff239-168">Automapping is on by default.</span></span> <span data-ttu-id="ff239-169">Mer information om hur du inaktiverar funktionen finns i [Ta bort automatisk mappning för en delad postlåda](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="ff239-169">To learn how to turn it off, see [Remove automapping for a shared mailbox](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="ff239-170">Mer information om delade postlådor i Outlook finns i:</span><span class="sxs-lookup"><span data-stu-id="ff239-170">To learn more about shared mailboxes in Outlook, see:</span></span>

- <span data-ttu-id="ff239-171"><a href="https://support.office.com/article/d94a8e9e-21f1-4240-808b-de9c9c088afd.aspx" target="_blank">Öppna och använda en delad postlåda i Outlook</a></span><span class="sxs-lookup"><span data-stu-id="ff239-171"><a href="https://support.office.com/article/d94a8e9e-21f1-4240-808b-de9c9c088afd.aspx" target="_blank">Open and use a shared mailbox in Outlook</a></span></span>

- <span data-ttu-id="ff239-172"><a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Lägga till en delad postlåda i Outlook på webben</a></span><span class="sxs-lookup"><span data-stu-id="ff239-172"><a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Add a shared mailbox to Outlook on the web</a></span></span>

- <span data-ttu-id="ff239-173"><a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Lägga till en delad postlåda i Outlook Mobile</a></span><span class="sxs-lookup"><span data-stu-id="ff239-173"><a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a></span></span>

- <span data-ttu-id="ff239-174"><a href="https://support.office.com/article/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2.aspx" target="_blank">Öppna en delad mapp eller postlåda i Outlook för Mac</a></span><span class="sxs-lookup"><span data-stu-id="ff239-174"><a href="https://support.office.com/article/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2.aspx" target="_blank">Open a shared folder or mailbox in Outlook for Mac</a></span></span>

- <span data-ttu-id="ff239-175"><a href="https://support.office.com/article/b0963400-2a51-4c64-afc7-b816d737d164.aspx" target="_blank">Lägga till regler i en delad postlåda</a></span><span class="sxs-lookup"><span data-stu-id="ff239-175"><a href="https://support.office.com/article/b0963400-2a51-4c64-afc7-b816d737d164.aspx" target="_blank">Add rules to a shared mailbox</a></span></span>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a><span data-ttu-id="ff239-176">Använda en delad postlåda på en mobil enhet (mobiltelefon eller surfplatta)</span><span class="sxs-lookup"><span data-stu-id="ff239-176">Use a shared mailbox on a mobile device (phone or tablet)</span></span>

<span data-ttu-id="ff239-177">Du kan komma åt en delad postlåda på en mobil enhet på två sätt:</span><span class="sxs-lookup"><span data-stu-id="ff239-177">You can access a shared mailbox on a mobile device in two ways:</span></span>
- <span data-ttu-id="ff239-178">Lägg till den delade postlådan i <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook för iOS-appen</a> eller <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook för Android-mobilappen</a>.</span><span class="sxs-lookup"><span data-stu-id="ff239-178">Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>.</span></span> 
    
    <span data-ttu-id="ff239-179">Anvisningar finns i <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Lägga till en delad postlåda i Outlook Mobile</a>.</span><span class="sxs-lookup"><span data-stu-id="ff239-179">For instructions, see <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span>

- <span data-ttu-id="ff239-180">Öppna webbläsaren, logga in och gå sedan till Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="ff239-180">Open your browser, sign in, and then go to Outlook on the web.</span></span> <span data-ttu-id="ff239-181">Från Outlook på webben har du tillgång till den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ff239-181">From Outlook on the web you'll be able to access the shared mailbox.</span></span>

    <span data-ttu-id="ff239-182">Anvisningar finns i <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Lägga till en delad postlåda i Outlook på webben</a>.</span><span class="sxs-lookup"><span data-stu-id="ff239-182">For instructions, see <a href="https://support.office.com/article/98b5a90d-4e38-415d-a030-f09a4cd28207.aspx" target="_blank">Add a shared mailbox to Outlook on the web</a>.</span></span>

## <a name="use-the-shared-calendar"></a><span data-ttu-id="ff239-183">Använda den delade kalendern</span><span class="sxs-lookup"><span data-stu-id="ff239-183">Use the shared calendar</span></span>

<span data-ttu-id="ff239-184">När du skapade den delade postlådan, skapade du automatiskt en delad kalender.</span><span class="sxs-lookup"><span data-stu-id="ff239-184">When you created the shared mailbox, you automatically created a shared calendar.</span></span> <span data-ttu-id="ff239-185">Vi föredrar den delade postlådekalendern framför en SharePoint-kalender när det handlar om att hålla koll på avtalade tider och var personer befinner sig.</span><span class="sxs-lookup"><span data-stu-id="ff239-185">We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are.</span></span> <span data-ttu-id="ff239-186">En delad kalender är integrerad med Outlook och är mycket enklare att använda än en SharePoint-kalender.</span><span class="sxs-lookup"><span data-stu-id="ff239-186">A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.</span></span>

1. <span data-ttu-id="ff239-187">Öppna kalendervyn i Outlook-appen och välj den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ff239-187">In the Outlook app, go to calendar view, and select the shared mailbox.</span></span>

2. <span data-ttu-id="ff239-188">Alla medlemmar i den delade postlådan ser avtalade tider som du lägger in. </span><span class="sxs-lookup"><span data-stu-id="ff239-188">When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.</span></span>

3. <span data-ttu-id="ff239-189">Alla medlemmar i den delade postlådan kan skapa, visa och hantera avtalade tider i kalendern på samma sätt som med privata avtalade tider.</span><span class="sxs-lookup"><span data-stu-id="ff239-189">Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments.</span></span> <span data-ttu-id="ff239-190">Alla som är medlemmar i en delad postlåda kan se sina ändringar i den delade kalendern.</span><span class="sxs-lookup"><span data-stu-id="ff239-190">Everyone who is a member of shared mailbox can see their changes to the shared calendar.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ff239-191">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="ff239-191">Related articles</span></span>

[<span data-ttu-id="ff239-192">Om delade postlådor</span><span class="sxs-lookup"><span data-stu-id="ff239-192">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="ff239-193">Konfigurera en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="ff239-193">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="ff239-194">Konvertera en användarpostlåda till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="ff239-194">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="ff239-195">Ta bort en licens från en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="ff239-195">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="ff239-196">Lösa problem med delade postlådor</span><span class="sxs-lookup"><span data-stu-id="ff239-196">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)





