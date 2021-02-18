---
title: Skapa en delad postlåda
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: När en delad postlåda har skapats kan flera personer i verksamheten dela på ansvaret att läsa och svara på e-postmeddelanden som skickas till en adress.
ms.openlocfilehash: d71e33aa0a04bd52f707038ac31e98bef68f27b0
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287239"
---
# <a name="create-a-shared-mailbox"></a><span data-ttu-id="ffd46-103">Skapa en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="ffd46-103">Create a shared mailbox</span></span> 

> [!NOTE]
> <span data-ttu-id="ffd46-104">Om din organisation använder en Exchange-hybridmiljö, använder du det lokala administrationscentret för Exchange när du skapar och hanterar delade postlådor.</span><span class="sxs-lookup"><span data-stu-id="ffd46-104">If your organization uses a hybrid Exchange environment, you should use the on-premises Exchange admin center (EAC) to create and manage shared mailboxes.</span></span> <span data-ttu-id="ffd46-105">Se [Så här skapar du en delad postlåda i administrationscentret för Exchange](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019&preserve-view=true.)</span><span class="sxs-lookup"><span data-stu-id="ffd46-105">See [Create shared mailboxes in the Exchange admin center](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019&preserve-view=true.)</span></span><br><br>
> <span data-ttu-id="ffd46-106">Om du inte är säker på ifall du ska skapa en delad postlåda eller en Microsoft 365-grupp för Outlook, kan du läsa mer i [Jämföra grupper](../create-groups/compare-groups.md). </span><span class="sxs-lookup"><span data-stu-id="ffd46-106">If you're not sure if you should create a shared mailbox or a Microsoft 365 group for Outlook, see [Compare groups](../create-groups/compare-groups.md) for some guidance.</span></span> <span data-ttu-id="ffd46-107">Observera att det för närvarande inte är möjligt att migrera en delad postlåda till en Microsoft 365-grupp.</span><span class="sxs-lookup"><span data-stu-id="ffd46-107">Note that currently, it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="ffd46-108">Om det är något som du vill kunna göra, kan du låta oss veta detta genom att [rösta här](https://go.microsoft.com/fwlink/?linkid=871518).</span><span class="sxs-lookup"><span data-stu-id="ffd46-108">If this is something you want, let us know by [voting here](https://go.microsoft.com/fwlink/?linkid=871518).</span></span>

<span data-ttu-id="ffd46-p103">Det är enkelt att skapa en delad postlåda så att en grupp användare kan övervaka och skicka e-post från en gemensam e-postadress, exempelvis info@contoso.com. När en person i gruppen svarar på ett meddelande till den delade postlådan ser svarsmeddelandet ut att komma från den delade postlådan, inte från den enskilda användaren.</span><span class="sxs-lookup"><span data-stu-id="ffd46-p103">It's easy to create shared mailboxes so a group of people can monitor and send email from a common email addresses, like info@contoso.com. When a person in the group replies to a message sent to the shared mailbox, the email appears to be from the shared mailbox, not from the individual user.</span></span>

<span data-ttu-id="ffd46-111">I delade postlådor finns det en delad kalender.</span><span class="sxs-lookup"><span data-stu-id="ffd46-111">Shared mailboxes include a shared calendar.</span></span> <span data-ttu-id="ffd46-112">Många små företag tycker att det är praktiskt att ha en delad kalender där alla lägger in sina avtalade tider.</span><span class="sxs-lookup"><span data-stu-id="ffd46-112">A lot of small businesses like to use the shared calendar as a place for everyone to enter their appointments.</span></span> <span data-ttu-id="ffd46-113">Om det till exempel finns tre personer som utför kundbesök kan de alla skriva in sina avtalade tider i kalendern.</span><span class="sxs-lookup"><span data-stu-id="ffd46-113">For example, if you have 3 people who do customer visits, all can use the shared calendar to enter the appointments.</span></span> <span data-ttu-id="ffd46-114">Det är ett bra sätt att hålla alla informerade om var alla befinner sig.</span><span class="sxs-lookup"><span data-stu-id="ffd46-114">This is an easy way to keep everyone informed where people are.</span></span>

<span data-ttu-id="ffd46-115">Innan du skapar en delad postlåda bör du läsa [Om delade postlådor](about-shared-mailboxes.md) för att få mer information.</span><span class="sxs-lookup"><span data-stu-id="ffd46-115">Before creating a shared mailbox, be sure to read [About shared mailboxes](about-shared-mailboxes.md) for more information.</span></span>

## <a name="create-a-shared-mailbox-and-add-members"></a><span data-ttu-id="ffd46-116">Skapa en delad postlåda och lägg till medlemmar</span><span class="sxs-lookup"><span data-stu-id="ffd46-116">Create a shared mailbox and add members</span></span>
  
1. <span data-ttu-id="ffd46-117">Logga in med ett globalt administratörskonto eller Exchange-administratörskonto.</span><span class="sxs-lookup"><span data-stu-id="ffd46-117">Sign in with a global admin account or Exchange admin account.</span></span> <span data-ttu-id="ffd46-118">Om du får meddelandet ”**Du har inte behörighet att komma åt den här sidan eller utföra den här åtgärden**”, är du inte någon administratör.</span><span class="sxs-lookup"><span data-stu-id="ffd46-118">If you get the message "**You don't have permission to access this page or perform this action**," then you aren't an admin.</span></span> 

::: moniker range="o365-worldwide"

2. <span data-ttu-id="ffd46-119">Gå till sidan **Grupper** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Delade postlådor</a> i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="ffd46-119">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Shared mailboxes</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

2. <span data-ttu-id="ffd46-120">I [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=848041) går du till sidan **Grupper** \> **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="ffd46-120">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

2. <span data-ttu-id="ffd46-121">I [administrationscentret](https://go.microsoft.com/fwlink/p/?linkid=850627) går du till sidan **Grupper** \> **Delade postlådor**.</span><span class="sxs-lookup"><span data-stu-id="ffd46-121">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=850627), go to the **Groups** \> **Shared mailboxes** page.</span></span>

::: moniker-end
    
3. <span data-ttu-id="ffd46-122">På sidan **Delade postlådor** väljer du **+ Lägg till en postlåda**.</span><span class="sxs-lookup"><span data-stu-id="ffd46-122">On the **Shared mailboxes** page, select **+ Add a mailbox**.</span></span> <span data-ttu-id="ffd46-123">Ange ett namn på den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ffd46-123">Enter a name for the shared mailbox.</span></span> <span data-ttu-id="ffd46-124">Guiden väljer sedan e-postadress, men du kan redigera den.</span><span class="sxs-lookup"><span data-stu-id="ffd46-124">Then the wizard chooses the email address, but you can edit it.</span></span>
    
    ![Namnge den delade postlådan.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. <span data-ttu-id="ffd46-126">Välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="ffd46-126">Select **Add**.</span></span> <span data-ttu-id="ffd46-127">Det kan ta några minuter innan du kan lägga till medlemmar.</span><span class="sxs-lookup"><span data-stu-id="ffd46-127">It may take a few minutes before you can add members.</span></span>

5. <span data-ttu-id="ffd46-128">Under **Nästa steg** väljer du **Lägg till medlemmar i den här postlådan**.</span><span class="sxs-lookup"><span data-stu-id="ffd46-128">Under **Next steps**, select **Add members to this mailbox**.</span></span> <span data-ttu-id="ffd46-129">Medlemmarna är de personer som kan se inkommande e-post till den delade postlådan och utgående svar.</span><span class="sxs-lookup"><span data-stu-id="ffd46-129">Members are the people who will be able to view the incoming mail to this shared mailbox, and the outgoing replies.</span></span>

   ![Välj Lägg till medlemmar](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. <span data-ttu-id="ffd46-131">Välj knappen **+Lägg till medlemmar**.</span><span class="sxs-lookup"><span data-stu-id="ffd46-131">Select the **+Add members** button.</span></span> <span data-ttu-id="ffd46-132">Markera de personer som ska använda den delade postlådan och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ffd46-132">Put a check mark next to the people who you want to use this shared mailbox, and select **Save**.</span></span>

   ![Tilldela medlemmar till den delade postlådan](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. <span data-ttu-id="ffd46-134">Välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="ffd46-134">Select **Close**.</span></span>

<span data-ttu-id="ffd46-135">Du har en delad postlåda och den innehåller en delad kalender.</span><span class="sxs-lookup"><span data-stu-id="ffd46-135">You have a shared mailbox and it includes a shared calendar.</span></span> <span data-ttu-id="ffd46-136">Gå vidare till nästa steg: Blockera inloggning för den delade postlådans konto.</span><span class="sxs-lookup"><span data-stu-id="ffd46-136">Now go on to the next step: block sign-in for the shared mailbox account.</span></span>

## <a name="which-permissions-should-you-use"></a><span data-ttu-id="ffd46-137">Vilken behörighet ska du välja?</span><span class="sxs-lookup"><span data-stu-id="ffd46-137">Which permissions should you use?</span></span>

<span data-ttu-id="ffd46-138">Du kan använda följande behörigheter med en delad postlåda:</span><span class="sxs-lookup"><span data-stu-id="ffd46-138">You can use the following permissions with a shared mailbox:</span></span>

- <span data-ttu-id="ffd46-139">**Fullständig åtkomst**: Med behörigheten Fullständig åtkomst kan användaren logga in till den delade postlådan och agera som ägare av postlådan.</span><span class="sxs-lookup"><span data-stu-id="ffd46-139">**Full Access**: The Full Access permission lets a user open the shared mailbox and act as the owner of that mailbox.</span></span> <span data-ttu-id="ffd46-140">Efter åtkomst till den delade postlådan kan en användare skapa kalenderobjekt, läsa, visa, radera och ändra e-postmeddelanden och skapa uppgifter och kalenderkontakter.</span><span class="sxs-lookup"><span data-stu-id="ffd46-140">After accessing the shared mailbox, a user can create calendar items, read, view, delete, and change email messages, and create tasks and calendar contacts.</span></span> <span data-ttu-id="ffd46-141">Men användare med behörigheten Fullständig åtkomst kan inte skicka e-post från den delade postlådan om de inte också har behörigheten Skicka som eller Skicka för.</span><span class="sxs-lookup"><span data-stu-id="ffd46-141">However, a user with Full Access permission can't send email from the shared mailbox unless they also have Send As or Send on Behalf permission.</span></span>

- <span data-ttu-id="ffd46-142">**Skicka som** Med behörigheten Skicka som kan användaren skicka e-post för den delade postlådans räkning.</span><span class="sxs-lookup"><span data-stu-id="ffd46-142">**Send As**: The Send As permission lets a user impersonate the shared mailbox when sending mail.</span></span> <span data-ttu-id="ffd46-143">Till exempel, om Katerina loggar in på den delade postlådans marknadsavdelning och skickar ett e-postmeddelande, ser det ut som att marknadsavdelningen skickade e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="ffd46-143">For example, if Katerina logs into the shared mailbox Marketing Department and sends an email, it will look like the Marketing Department sent the email.</span></span>

- <span data-ttu-id="ffd46-144">**Skicka för**: Med behörigheten Skicka för kan användaren skicka e-post för den delade postlådans räkning.</span><span class="sxs-lookup"><span data-stu-id="ffd46-144">**Send on Behalf**: The Send on Behalf permission lets a user send email on behalf of the shared mailbox.</span></span> <span data-ttu-id="ffd46-145">Till exempel, om John loggar in till den delade postlådan Reception byggnad 32 och skickar ett e-postmeddelande, kommer det att se ut som att e-postmeddelandet skickades av "John för Reception byggnad 32".</span><span class="sxs-lookup"><span data-stu-id="ffd46-145">For example, if John logs into the shared mailbox Reception Building 32 and sends an email, it will look like the mail was sent by "John on behalf of Reception Building 32".</span></span> <span data-ttu-id="ffd46-146">Du kan inte använda EAC för att bevilja behörigheter för skicka på väg, du måste använda cmdlet **Set-Mailbox** med parametern _GrantSendonBehalf_.</span><span class="sxs-lookup"><span data-stu-id="ffd46-146">You can't use the EAC to grant Send on Behalf permissions, you must use the **Set-Mailbox** cmdlet with the _GrantSendonBehalf_ parameter.</span></span>

### <a name="use-the-eac-to-edit-shared-mailbox-delegation"></a><span data-ttu-id="ffd46-147">Använda EAC för att redigera delegering för delad postlåda</span><span class="sxs-lookup"><span data-stu-id="ffd46-147">Use the EAC to edit shared mailbox delegation</span></span>

1. <span data-ttu-id="ffd46-148">Öppna EAC och gå till **Mottagare** \> **Grupper**.</span><span class="sxs-lookup"><span data-stu-id="ffd46-148">In the EAC, go to **Recipients** \> **Shared**.</span></span> <span data-ttu-id="ffd46-149">Välj den delade postlådan och välj sedan **Redigera** ![redigeringsikon](../../media/ITPro-EAC-EditIcon.png).</span><span class="sxs-lookup"><span data-stu-id="ffd46-149">Select the shared mailbox, and then select **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>

2. <span data-ttu-id="ffd46-150">Välj **delegering av postlåda**.</span><span class="sxs-lookup"><span data-stu-id="ffd46-150">Select **Mailbox delegation**.</span></span>

3. <span data-ttu-id="ffd46-151">Om du vill bevilja eller ta bort full åtkomst och skicka som behörighet, välj **Lägg till** ![lägg till ikonen](../../media/ITPro-EAC-AddIcon.png) eller **ta bort** ![ta bort ikonen](../../media/ITPro-EAC-RemoveIcon.gif) och välj sedan de användare du vill ge behörighet till.</span><span class="sxs-lookup"><span data-stu-id="ffd46-151">To grant or remove Full Access and Send As permissions, select **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png) or **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif) and then select the users you want to grant permissions to.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ffd46-p115">Med behörigheten Fullständig åtkomst kan användaren öppna postlådan samt skapa och ändra objekt i den. Med behörigheten Skicka som kan alla utöver postlådans ägare skicka e-post från den delade postlådan. Båda behörigheterna krävs för att den delade postlådan ska kunna hanteras.</span><span class="sxs-lookup"><span data-stu-id="ffd46-p115">The Full Access permission allows a user to open the mailbox as well as create and modify items in it. The Send As permission allows anyone other than the mailbox owner to send email from this shared mailbox. Both permissions are required for successful shared mailbox operation.</span></span>

4. <span data-ttu-id="ffd46-155">Välj **Spara** för att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="ffd46-155">Select **Save** to save your changes.</span></span>


## <a name="block-sign-in-for-the-shared-mailbox-account"></a><span data-ttu-id="ffd46-156">Blockera inloggning för den delade postlådans konto</span><span class="sxs-lookup"><span data-stu-id="ffd46-156">Block sign-in for the shared mailbox account</span></span>

<span data-ttu-id="ffd46-157">Alla delade postlådor har ett motsvarande användarkonto.</span><span class="sxs-lookup"><span data-stu-id="ffd46-157">Every shared mailbox has a corresponding user account.</span></span> <span data-ttu-id="ffd46-158">Lade du märke till att du inte behövde ange något lösenord när du skapade den delade postlådan?</span><span class="sxs-lookup"><span data-stu-id="ffd46-158">Notice how you weren't asked to provide a password when you created the shared mailbox?</span></span> <span data-ttu-id="ffd46-159">Kontot har ett lösenord, men det genereras av systemet (okänt).</span><span class="sxs-lookup"><span data-stu-id="ffd46-159">The account has a password, but it's system-generated (unknown).</span></span> <span data-ttu-id="ffd46-160">Du ska inte använda kontot för att logga in på den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ffd46-160">You aren't supposed to use the account to log in to the shared mailbox.</span></span>

<span data-ttu-id="ffd46-161">Men vad händer om en administratör återställer lösenordet för den delade postlådans användarkonto?</span><span class="sxs-lookup"><span data-stu-id="ffd46-161">But what if an admin simply resets the password of the shared mailbox user account?</span></span> <span data-ttu-id="ffd46-162">Eller om en angripare får åtkomst till kontoautentiseringsuppgifterna för den delade postlådan?</span><span class="sxs-lookup"><span data-stu-id="ffd46-162">Or what if an attacker gains access to the shared mailbox account credentials?</span></span> <span data-ttu-id="ffd46-163">Det skulle innebära att användarkontot kan logga in på den delade postlådan och skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="ffd46-163">This would allow the user account to log in to the shared mailbox and send email.</span></span> <span data-ttu-id="ffd46-164">För att förhindra detta måste du blockera inloggningen för det konto som är kopplat till den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ffd46-164">To prevent this, you need to block sign-in for the account that's associated with the shared mailbox.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ffd46-165">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ffd46-165">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="ffd46-166">Leta reda på kontot för den delade postlådan i listan med användarkonton (ändra t.ex. filtret till **Användare utan licens**).</span><span class="sxs-lookup"><span data-stu-id="ffd46-166">In the list of user accounts, find the account for the shared mailbox (for example, change the filter to **Unlicensed users**).</span></span>

3. <span data-ttu-id="ffd46-167">Välj användaren för att öppna fönstret Egenskaper och välj sedan ikonen **Blockera den här användaren** ![Skärmbild av ikonen Blockera den här användaren](../../media/block-user-icon.png).</span><span class="sxs-lookup"><span data-stu-id="ffd46-167">Select the user to open their properties pane, and then select the **Block this user** icon ![Screen shot of the Block this user icon](../../media/block-user-icon.png).</span></span>

   <span data-ttu-id="ffd46-168">**Obs**! Om kontot redan är blockerat visas **Inloggning blockerad** längst upp och ikonen är **Avblockera den här användaren**.</span><span class="sxs-lookup"><span data-stu-id="ffd46-168">**Note**: If the account is already blocked, **Sign in blocked** will appear at the top and the icon will read **Unblock this user**.</span></span>

4. <span data-ttu-id="ffd46-169">I fönstret **Blockera den här användaren?** väljer du **Blockera användaren från att logga in** och sedan **Spara ändringarna**.</span><span class="sxs-lookup"><span data-stu-id="ffd46-169">In the **Block this user?** pane, select **Block the user from signing in**, and then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ffd46-170">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ffd46-170">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="ffd46-171">Leta reda på kontot för den delade postlådan i listan med användarkonton (ändra t.ex. vyn till **Användare utan licens**) och markera sedan kontot.</span><span class="sxs-lookup"><span data-stu-id="ffd46-171">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="ffd46-172">Välj **Blockera inloggning** i den utfällbara menyn för egenskaper.</span><span class="sxs-lookup"><span data-stu-id="ffd46-172">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="ffd46-173">**Obs!** Om kontot redan har blockerats visar knappen **Tillåt inloggning**.</span><span class="sxs-lookup"><span data-stu-id="ffd46-173">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="ffd46-174">Kontrollera att Blockera användaren från att logga in är markerad i den utfällbara menyn **Redigera inloggningsstatus**. Välj **Spara** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="ffd46-174">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ffd46-175">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="ffd46-175">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="ffd46-176">Leta reda på kontot för den delade postlådan i listan med användarkonton (ändra t.ex. vyn till **Användare utan licens**) och markera sedan kontot.</span><span class="sxs-lookup"><span data-stu-id="ffd46-176">In the list of user accounts, find the account for the shared mailbox (for example, change the view to **Unlicensed users**) and then select the account.</span></span>

3. <span data-ttu-id="ffd46-177">Välj **Blockera inloggning** i den utfällbara menyn för egenskaper.</span><span class="sxs-lookup"><span data-stu-id="ffd46-177">In the properties flyout, select **Block sign-in**.</span></span>

    <span data-ttu-id="ffd46-178">**Obs!** Om kontot redan har blockerats visar knappen **Tillåt inloggning**.</span><span class="sxs-lookup"><span data-stu-id="ffd46-178">**Note:** If the account was already blocked, the button would say **Unblock sign-in**.</span></span>

4. <span data-ttu-id="ffd46-179">Kontrollera att Blockera användaren från att logga in är markerad i den utfällbara menyn **Redigera inloggningsstatus**. Välj **Spara** och sedan **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="ffd46-179">In the **Edit sign-in status** flyout, verify that Block the user from signing in is selected, select **Save** and then **Close**.</span></span>
::: moniker-end

<span data-ttu-id="ffd46-180">Om du vill ha anvisningar om hur du blockerar inloggning för konton som använder Azure AD PowerShell (med flera konton samtidigt), kan du läsa [Blockera användarkonton med Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/block-user-accounts-with-microsoft-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="ffd46-180">For instructions on how to block sign-in for accounts using Azure AD PowerShell (including many accounts at the same time), see [Block user accounts with Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/block-user-accounts-with-microsoft-365-powershell).</span></span>

## <a name="add-the-shared-mailbox-to-outlook"></a><span data-ttu-id="ffd46-181">Lägga till den delade postlådan i Outlook</span><span class="sxs-lookup"><span data-stu-id="ffd46-181">Add the shared mailbox to Outlook</span></span>

<span data-ttu-id="ffd46-182">Om ditt företag har aktiverat automatisk mappning (det har de flesta som standard), visas den delade postlådan i användarnas Outlook-app automatiskt när de har stängt och startat om Outlook.</span><span class="sxs-lookup"><span data-stu-id="ffd46-182">If you have automapping enabled in your business (by default, most people do), the shared mailbox will appear in your user's Outlook app automatically after they close and restart Outlook.</span></span> 

<span data-ttu-id="ffd46-183">Automatisk mappning är inställt på användarens postlåda, inte på den delade postlådan.  </span><span class="sxs-lookup"><span data-stu-id="ffd46-183">Automapping is set on the user's mailbox, not the shared mailbox.</span></span> <span data-ttu-id="ffd46-184">Det här innebär att automatisk mappning inte fungerar om du försöker använda säkerhetsgruppen för att hantera vem som har åtkomst till den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ffd46-184">This means if you try to use a security group to manage who has access to the shared mailbox, automapping won't work.</span></span> <span data-ttu-id="ffd46-185">Om du vill använda automatisk mappning måste du uttryckligen tilldela behörigheter.</span><span class="sxs-lookup"><span data-stu-id="ffd46-185">So, if you want automapping, you have to assign permissions explicitly.</span></span> <span data-ttu-id="ffd46-186">Automatisk mappning är aktiverat som standard.</span><span class="sxs-lookup"><span data-stu-id="ffd46-186">Automapping is on by default.</span></span> <span data-ttu-id="ffd46-187">Mer information om hur du inaktiverar funktionen finns i [Ta bort automatisk mappning för en delad postlåda](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="ffd46-187">To learn how to turn it off, see [Remove automapping for a shared mailbox](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).</span></span>

<span data-ttu-id="ffd46-188">Mer information om delade postlådor i Outlook finns i:</span><span class="sxs-lookup"><span data-stu-id="ffd46-188">To learn more about shared mailboxes in Outlook, see:</span></span>

- <span data-ttu-id="ffd46-189"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Öppna och använda en delad postlåda i Outlook</a></span><span class="sxs-lookup"><span data-stu-id="ffd46-189"><a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Open and use a shared mailbox in Outlook</a></span></span>

- <span data-ttu-id="ffd46-190"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Lägga till en delad postlåda i Outlook på webben</a></span><span class="sxs-lookup"><span data-stu-id="ffd46-190"><a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a></span></span>

- <span data-ttu-id="ffd46-191"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Lägga till en delad postlåda i Outlook Mobile</a></span><span class="sxs-lookup"><span data-stu-id="ffd46-191"><a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a></span></span>

- <span data-ttu-id="ffd46-192"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Öppna en delad mapp eller postlåda i Outlook för Mac</a></span><span class="sxs-lookup"><span data-stu-id="ffd46-192"><a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Open a shared folder or mailbox in Outlook for Mac</a></span></span>

- <span data-ttu-id="ffd46-193"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Lägga till regler i en delad postlåda</a></span><span class="sxs-lookup"><span data-stu-id="ffd46-193"><a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Add rules to a shared mailbox</a></span></span>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a><span data-ttu-id="ffd46-194">Använda en delad postlåda på en mobil enhet (mobiltelefon eller surfplatta)</span><span class="sxs-lookup"><span data-stu-id="ffd46-194">Use a shared mailbox on a mobile device (phone or tablet)</span></span>

<span data-ttu-id="ffd46-195">Du kan komma åt en delad postlåda på en mobil enhet på två sätt:</span><span class="sxs-lookup"><span data-stu-id="ffd46-195">You can access a shared mailbox on a mobile device in two ways:</span></span>
- <span data-ttu-id="ffd46-196">Lägg till den delade postlådan i <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook för iOS-appen</a> eller <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook för Android-mobilappen</a>.</span><span class="sxs-lookup"><span data-stu-id="ffd46-196">Add the shared mailbox in the <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook for iOS app</a> or the <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android mobile app</a>.</span></span> 
    
    <span data-ttu-id="ffd46-197">Anvisningar finns i <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Lägga till en delad postlåda i Outlook Mobile</a>.</span><span class="sxs-lookup"><span data-stu-id="ffd46-197">For instructions, see <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Add a shared mailbox to Outlook mobile</a>.</span></span>

- <span data-ttu-id="ffd46-198">Öppna webbläsaren, logga in och gå sedan till Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="ffd46-198">Open your browser, sign in, and then go to Outlook on the web.</span></span> <span data-ttu-id="ffd46-199">Från Outlook på webben har du tillgång till den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ffd46-199">From Outlook on the web you'll be able to access the shared mailbox.</span></span>

    <span data-ttu-id="ffd46-200">Anvisningar finns i <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Lägga till en delad postlåda i Outlook på webben</a>.</span><span class="sxs-lookup"><span data-stu-id="ffd46-200">For instructions, see <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Add a shared mailbox to Outlook on the web</a>.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ffd46-201">Delad postlåda kan bara läggas till i Outlook för iOS-appen eller Outlook för Android-mobilappen</span><span class="sxs-lookup"><span data-stu-id="ffd46-201">Shared mailbox can only be added to Outlook for iOS app or the Outlook for Android mobile app</span></span>

## <a name="use-the-shared-calendar"></a><span data-ttu-id="ffd46-202">Använda den delade kalendern</span><span class="sxs-lookup"><span data-stu-id="ffd46-202">Use the shared calendar</span></span>

<span data-ttu-id="ffd46-203">När du skapade den delade postlådan, skapade du automatiskt en delad kalender.</span><span class="sxs-lookup"><span data-stu-id="ffd46-203">When you created the shared mailbox, you automatically created a shared calendar.</span></span> <span data-ttu-id="ffd46-204">Vi föredrar den delade postlådekalendern framför en SharePoint-kalender när det handlar om att hålla koll på avtalade tider och var personer befinner sig.</span><span class="sxs-lookup"><span data-stu-id="ffd46-204">We like the shared mailbox calendar rather than a SharePoint calendar for keeping track of appointments and where people are.</span></span> <span data-ttu-id="ffd46-205">En delad kalender är integrerad med Outlook och är mycket enklare att använda än en SharePoint-kalender.</span><span class="sxs-lookup"><span data-stu-id="ffd46-205">A shared calendar is integrated with Outlook and it's much easier to use than a SharePoint calendar.</span></span>

1. <span data-ttu-id="ffd46-206">Öppna kalendervyn i Outlook-appen och välj den delade postlådan.</span><span class="sxs-lookup"><span data-stu-id="ffd46-206">In the Outlook app, go to calendar view, and select the shared mailbox.</span></span>

2. <span data-ttu-id="ffd46-207">Alla medlemmar i den delade postlådan ser avtalade tider som du lägger in. </span><span class="sxs-lookup"><span data-stu-id="ffd46-207">When you enter appointments, everyone who is a member of the shared mailbox will be able to see them.</span></span>

3. <span data-ttu-id="ffd46-208">Alla medlemmar i den delade postlådan kan skapa, visa och hantera avtalade tider i kalendern på samma sätt som med privata avtalade tider.</span><span class="sxs-lookup"><span data-stu-id="ffd46-208">Any member of the shared mailbox can create, view, and manage appointments on the calendar, just like they would their personal appointments.</span></span> <span data-ttu-id="ffd46-209">Alla som är medlemmar i en delad postlåda kan se sina ändringar i den delade kalendern.</span><span class="sxs-lookup"><span data-stu-id="ffd46-209">Everyone who is a member of shared mailbox can see their changes to the shared calendar.</span></span>

## <a name="related-articles"></a><span data-ttu-id="ffd46-210">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="ffd46-210">Related articles</span></span>

[<span data-ttu-id="ffd46-211">Om delade postlådor</span><span class="sxs-lookup"><span data-stu-id="ffd46-211">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="ffd46-212">Konfigurera en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="ffd46-212">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="ffd46-213">Konvertera en användarpostlåda till en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="ffd46-213">Convert a user mailbox to a shared mailbox</span></span>](convert-user-mailbox-to-shared-mailbox.md)

[<span data-ttu-id="ffd46-214">Ta bort en licens från en delad postlåda</span><span class="sxs-lookup"><span data-stu-id="ffd46-214">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="ffd46-215">Lösa problem med delade postlådor</span><span class="sxs-lookup"><span data-stu-id="ffd46-215">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)


