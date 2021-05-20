---
title: Steg 4 – Ge en annan anställd tillgång OneDrive och Outlook data
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
description: Följ stegen i den här artikeln för att ge en annan anställd åtkomst till den tidigare anställdes OneDrive och Outlook data.
ms.openlocfilehash: cb5c27cbc7f1c184af8f0d1ad32b822660e93791
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582698"
---
# <a name="step-4---give-another-employee-access-to-onedrive-and-outlook-data"></a><span data-ttu-id="745a9-103">Steg 4 – Ge en annan anställd tillgång OneDrive och Outlook data</span><span class="sxs-lookup"><span data-stu-id="745a9-103">Step 4 - Give another employee access to OneDrive and Outlook data</span></span>

<span data-ttu-id="745a9-104">När en anställd lämnar organisationen ska du komma åt deras OneDrive och Outlook-data, backa dem och välja om du vill ge dem till en annan anställd.</span><span class="sxs-lookup"><span data-stu-id="745a9-104">When an employee leaves your organization, you'll want to access their OneDrive and Outlook data, back it up, and choose whether to give it to another employee.</span></span>
  
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="745a9-105">Komma åt en tidigare anställds OneDrive dokument</span><span class="sxs-lookup"><span data-stu-id="745a9-105">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="745a9-106">Om du tar bort en användares licens men inte tar bort kontot kan du ge dig själv åtkomst till innehållet i användarens OneDrive.</span><span class="sxs-lookup"><span data-stu-id="745a9-106">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="745a9-107">Om du tar bort användarens konto har du som standard 30 dagar på dig att få åtkomst till den tidigare användarens OneDrive data.</span><span class="sxs-lookup"><span data-stu-id="745a9-107">If you delete the user's account, you have 30 days by default to access the former user's OneDrive data.</span></span> <span data-ttu-id="745a9-108">[Lär dig hur du OneDrive bevarande för borttagna användare.](/onedrive/set-retention)</span><span class="sxs-lookup"><span data-stu-id="745a9-108">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="745a9-109">Om du inte återställer [ett användarkonto inom den](/office365/admin/add-users/restore-user) tiden tas OneDrive bort användarens innehåll.</span><span class="sxs-lookup"><span data-stu-id="745a9-109">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span>

<span data-ttu-id="745a9-110">Om du vill bevara en tidigare OneDrive måste du först ge dig själv åtkomst till deras OneDrive och sedan flytta de filer du vill behålla.</span><span class="sxs-lookup"><span data-stu-id="745a9-110">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span>

1. <span data-ttu-id="745a9-111">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="745a9-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="745a9-112">Välj en användare.</span><span class="sxs-lookup"><span data-stu-id="745a9-112">Select a user.</span></span>

3. <span data-ttu-id="745a9-113">I det högra fönstret väljer **du OneDrive**.</span><span class="sxs-lookup"><span data-stu-id="745a9-113">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="745a9-114">Under **Få åtkomst till filer** väljer du Skapa länk till **filer**.</span><span class="sxs-lookup"><span data-stu-id="745a9-114">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="745a9-115">Klicka på länken för att öppna filens plats.</span><span class="sxs-lookup"><span data-stu-id="745a9-115">Select the link to open the file location.</span></span> <span data-ttu-id="745a9-116">Ladda ned filerna till datorn  eller  välj Flytta till eller Kopiera för att flytta eller kopiera dem till din egen OneDrive eller till ett delat bibliotek.</span><span class="sxs-lookup"><span data-stu-id="745a9-116">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span>

> [!NOTE]
> <span data-ttu-id="745a9-117">Du kan flytta eller kopiera upp till 500 MB filer och mappar i taget.</span><span class="sxs-lookup"><span data-stu-id="745a9-117">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="745a9-118">När du flyttar eller kopierar dokument som har versionshistorik flyttas bara den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="745a9-118">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

### <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="745a9-119">Återkalla administratörsåtkomst till en användares OneDrive</span><span class="sxs-lookup"><span data-stu-id="745a9-119">Revoke admin access to a user's OneDrive</span></span>

<span data-ttu-id="745a9-120">Du kan ge dig själv åtkomst till innehållet i en användares OneDrive, men du kanske vill ta bort åtkomsten när du inte längre behöver den.</span><span class="sxs-lookup"><span data-stu-id="745a9-120">You can give yourself access to the content in a user's OneDrive, but you may want to remove your access when you no longer need it.</span></span>

1. <span data-ttu-id="745a9-121">Logga in i <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret som</a> global administratör eller SharePoint administratör.</span><span class="sxs-lookup"><span data-stu-id="745a9-121">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="745a9-122">Om du får ett meddelande om att du inte har behörighet att komma åt administrationscentret har du inte administratörsbehörighet i din organisation.</span><span class="sxs-lookup"><span data-stu-id="745a9-122">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

2. <span data-ttu-id="745a9-123">I den vänstra rutan väljer du **Administrationscenter** \> **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="745a9-123">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="745a9-124">(Eventuellt måste du välja **Visa alla för** att listan över administrationscenter ska visas.)</span><span class="sxs-lookup"><span data-stu-id="745a9-124">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="745a9-125">Om det klassiska SharePoint administrationscentret visas väljer du **Öppna nu** högst upp på sidan för att SharePoint administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="745a9-125">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the SharePoint admin center.</span></span>

4. <span data-ttu-id="745a9-126">I det vänstra fönstret väljer du **Fler funktioner.**</span><span class="sxs-lookup"><span data-stu-id="745a9-126">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="745a9-127">Under **Användarprofiler** väljer du **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="745a9-127">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="745a9-128">Under **Personer** väljer du **Hantera användarprofiler.**</span><span class="sxs-lookup"><span data-stu-id="745a9-128">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="745a9-129">Ange användarens namn och välj **Sök**.</span><span class="sxs-lookup"><span data-stu-id="745a9-129">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="745a9-130">Högerklicka på användaren och välj sedan Hantera **webbplatssamlingens ägare.**</span><span class="sxs-lookup"><span data-stu-id="745a9-130">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="745a9-131">Ta bort den person som inte längre behöver åtkomst till användarens data och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="745a9-131">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="745a9-132">Komma åt Outlook för en tidigare användare</span><span class="sxs-lookup"><span data-stu-id="745a9-132">Access the Outlook data of a former user</span></span>

<span data-ttu-id="745a9-133">Om du vill spara den tidigare anställdas e-postmeddelanden, kalender, uppgifter och kontakter exporterar du informationen till en Outlook (.pst).</span><span class="sxs-lookup"><span data-stu-id="745a9-133">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="745a9-134">[Lägg till den tidigare anställdas](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) e-postadress i [](reset-passwords.md)ditt Outlook (Om du återställer användarens lösenord kan du ställa in det på något som bara du känner till.)</span><span class="sxs-lookup"><span data-stu-id="745a9-134">[Add the former employee's email](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>

2. <span data-ttu-id="745a9-135">I Outlook väljer du **Arkiv**.</span><span class="sxs-lookup"><span data-stu-id="745a9-135">In Outlook, select **File**.</span></span>

    ![Så här ser menyfliksområdet ut i Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="745a9-137">Välj **Öppna &amp; export** \> **Import/Export**.</span><span class="sxs-lookup"><span data-stu-id="745a9-137">Select **Open &amp; Export** \> **Import/Export**.</span></span>

    ![Kommandot Importera/Exportera i Backstage-vyn](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="745a9-139">Välj **Exportera till en fil** och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="745a9-139">Select **Export to a file**, and then select **Next**.</span></span>

    ![Alternativet Exportera till en fil i Importera-/exporteraguiden](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="745a9-141">Välj **Outlook (.pst) och** välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="745a9-141">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>

6. <span data-ttu-id="745a9-142">Välj det konto som du vill exportera genom att välja namn eller e-postadress, till exempel Postlåda – Anna Weiler eller anne@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="745a9-142">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="745a9-143">Om du vill exportera allt på ditt konto, inklusive e-post, kalender, kontakter, uppgifter och anteckningar markerar du kryssrutan Inkludera undermappar. </span><span class="sxs-lookup"><span data-stu-id="745a9-143">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="745a9-144">Du kan exportera ett konto i taget.</span><span class="sxs-lookup"><span data-stu-id="745a9-144">You can export one account at a time.</span></span> <span data-ttu-id="745a9-145">Om du vill exportera flera konton upprepar du stegen efter att ett konto exporterats.</span><span class="sxs-lookup"><span data-stu-id="745a9-145">If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span>
  
    ![Dialogrutan Exportera Outlook-datafil med den översta mappen markerad och Inkludera undermappar markerad](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="745a9-147">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="745a9-147">Select **Next**.</span></span>

8. <span data-ttu-id="745a9-148">Välj **Bläddra** och välj var du vill spara Outlook datafilen (.pst).</span><span class="sxs-lookup"><span data-stu-id="745a9-148">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="745a9-149">Skriv ett  *filnamn och* välj sedan **OK för** att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="745a9-149">Type a  *file name*, and then select **OK** to continue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="745a9-150">Om du har exporterat tidigare visas den förra mappsökvägen och filnamnet.</span><span class="sxs-lookup"><span data-stu-id="745a9-150">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="745a9-151">Skriv in *ett annat filnamn innan* du väljer **OK.**</span><span class="sxs-lookup"><span data-stu-id="745a9-151">Type a  *different file name*  before selecting **OK**.</span></span>
  
9. <span data-ttu-id="745a9-152">Om du exporterar till en befintlig Outlook-datafil (.pst) anger du vad du vill göra under **Alternativ** när du exporterar objekt som redan finns i filen.</span><span class="sxs-lookup"><span data-stu-id="745a9-152">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>

10. <span data-ttu-id="745a9-153">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="745a9-153">Select **Finish**.</span></span>

<span data-ttu-id="745a9-154">Outlook påbörjar exporten direkt om du inte skapar en ny Outlook-datafil (.pst) eller använder en lösenordskyddad fil.</span><span class="sxs-lookup"><span data-stu-id="745a9-154">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
- <span data-ttu-id="745a9-155">Om du skapar en Outlook-datafil (.pst) kan du skydda filen med ett lösenord.</span><span class="sxs-lookup"><span data-stu-id="745a9-155">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="745a9-156">När dialogrutan **Outlook datafil** visas anger du  lösenordet i  rutorna Lösenord och Bekräfta lösenord och väljer sedan  **OK.**</span><span class="sxs-lookup"><span data-stu-id="745a9-156">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="745a9-157">Skriv **lösenordet Outlook i dialogrutan** Ändra datafilslösenord *och* välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="745a9-157">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>

- <span data-ttu-id="745a9-158">Om du exporterar till en befintlig Outlook-datafil (.pst) som är lösenordsskyddad skriver du lösenordet i dialogrutan lösenord för **Outlook-datafil** och väljer sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="745a9-158">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>

<span data-ttu-id="745a9-159">Se hur du [exporterar eller säkerhetskopierar e-post,](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) kontakter och kalender till Outlook .pst-fil i Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="745a9-159">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) in Outlook 2010.</span></span>

  > [!NOTE]
  > <span data-ttu-id="745a9-160">Som standard är din e-post tillgänglig offline under en period på 12 månader.</span><span class="sxs-lookup"><span data-stu-id="745a9-160">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="745a9-161">Om det behövs kan du se hur [du kan öka de data som är tillgängliga offline](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span><span class="sxs-lookup"><span data-stu-id="745a9-161">If required, see how to [increase the data available offline](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>

### <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="745a9-162">Ge en annan användare åtkomst till en tidigare anställds e-post</span><span class="sxs-lookup"><span data-stu-id="745a9-162">Give another user access to a former user's email</span></span>

<span data-ttu-id="745a9-163">Om du vill ge åtkomst till e-postmeddelanden, kalender, uppgifter och kontakter hos den tidigare anställde till en annan anställd importerar du informationen till en annan anställds e-Outlook inkorg.</span><span class="sxs-lookup"><span data-stu-id="745a9-163">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="745a9-164">Du kan också [konvertera den tidigare användarens postlåda till en](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) delad postlåda eller vidarebefordra en tidigare [anställds e-post till en annan anställd.](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)</span><span class="sxs-lookup"><span data-stu-id="745a9-164">You can also [convert the former user's mailbox to a shared mailbox](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

1. <span data-ttu-id="745a9-165">Gå Outlook öppna Öppna **export i** \> **&amp; Import/Export** \> .</span><span class="sxs-lookup"><span data-stu-id="745a9-165">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>

    <span data-ttu-id="745a9-166">När du gör det startas Import-/exportguiden.</span><span class="sxs-lookup"><span data-stu-id="745a9-166">This starts the Import and Export Wizard.</span></span>

2. <span data-ttu-id="745a9-167">Välj **Importera från ett annat program eller en** fil och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="745a9-167">Select **Import from another program or file**, and then select **Next**.</span></span>

    ![Import-/exportguiden](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="745a9-169">Välj **Outlook (.pst) och** välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="745a9-169">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>

4. <span data-ttu-id="745a9-170">Bläddra till .pst-filen som du vill importera.</span><span class="sxs-lookup"><span data-stu-id="745a9-170">Browse to the .pst file you want to import.</span></span>

5. <span data-ttu-id="745a9-171">Välj **hur** dubbletter ska hanteras under Alternativ</span><span class="sxs-lookup"><span data-stu-id="745a9-171">Under **Options**, choose how you want to deal with duplicates</span></span>

6. <span data-ttu-id="745a9-172">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="745a9-172">Select **Next**.</span></span>

7. <span data-ttu-id="745a9-173">Om datafilen (.pst) har tilldelats Outlook ett lösenord anger du lösenordet och väljer **sedan OK.**</span><span class="sxs-lookup"><span data-stu-id="745a9-173">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>

8. <span data-ttu-id="745a9-p111">Ange alternativen för importen av objekten. Vanligtvis behöver du inte ändra standardinställningarna.</span><span class="sxs-lookup"><span data-stu-id="745a9-p111">Set the options for importing items. The default settings usually don't need to be changed.</span></span>

9. <span data-ttu-id="745a9-176">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="745a9-176">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="745a9-177">Stegen förblir desamma för åtkomst till en befintlig användares e-OneDrive och e-postdata.</span><span class="sxs-lookup"><span data-stu-id="745a9-177">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>

> [!TIP]
> <span data-ttu-id="745a9-178">Om du bara vill importera eller återställa ett fåtal objekt från en Outlook-datafil (.pst) kan du öppna den Outlook datafilen.</span><span class="sxs-lookup"><span data-stu-id="745a9-178">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="745a9-179">I navigeringsfönstret drar du sedan objekten från mapparna Outlook datafil till dina befintliga Outlook mappar.</span><span class="sxs-lookup"><span data-stu-id="745a9-179">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 

## <a name="related-content"></a><span data-ttu-id="745a9-180">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="745a9-180">Related content</span></span>

<span data-ttu-id="745a9-181">[Lägga till och ta bort administratörer i OneDrive-konto](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive) (artikel)</span><span class="sxs-lookup"><span data-stu-id="745a9-181">[Add and remove admins on a OneDrive account](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive) (article)</span></span>

<span data-ttu-id="745a9-182">[Återställa en borttagna OneDrive](/onedrive/restore-deleted-onedrive) (artikel)</span><span class="sxs-lookup"><span data-stu-id="745a9-182">[Restore a deleted OneDrive](/onedrive/restore-deleted-onedrive) (article)</span></span>
  
<span data-ttu-id="745a9-183">[OneDrive och borttagning](/onedrive/retention-and-deletion) (artikel)</span><span class="sxs-lookup"><span data-stu-id="745a9-183">[OneDrive retention and deletion](/onedrive/retention-and-deletion) (article)</span></span>
