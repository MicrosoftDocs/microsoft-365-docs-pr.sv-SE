---
title: Få åtkomst till och säkerhetskopiera en tidigare anställds användardata.
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: Lär dig hur du bevarar en anställds filer och e-postmeddelanden när personen lämnar organisationen.
ms.openlocfilehash: 17911e4a4551bba07d2c2ad034941bba737dcc1d
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51755612"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="40628-103">Få åtkomst till och säkerhetskopiera en tidigare anställds användardata.</span><span class="sxs-lookup"><span data-stu-id="40628-103">Get access to and back up a former user's data</span></span>


<span data-ttu-id="40628-104">När en anställd lämnar organisationen vill du antagligen komma åt deras data (dokument och e-postmeddelanden) och antingen granska dem, backa upp dem eller ge dem till en ny anställd.</span><span class="sxs-lookup"><span data-stu-id="40628-104">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="40628-105">Komma åt en tidigare anställds OneDrive-dokument</span><span class="sxs-lookup"><span data-stu-id="40628-105">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="40628-106">Om du tar bort en användares licens men inte tar bort kontot kan du ge dig själv åtkomst till innehållet på användarens OneDrive.</span><span class="sxs-lookup"><span data-stu-id="40628-106">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="40628-107">Om du tar bort användarens konto har du som standard 30 dagar på dig att komma åt den tidigare användarens OneDrive-data.</span><span class="sxs-lookup"><span data-stu-id="40628-107">If you delete the user's account, you have 30 days by default to access the former user's OneDrive data.</span></span> <span data-ttu-id="40628-108">[Läs om hur du anger OneDrive-bevarande för borttagna användare.](/onedrive/set-retention)</span><span class="sxs-lookup"><span data-stu-id="40628-108">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="40628-109">Om du inte återställer [ett användarkonto under](/office365/admin/add-users/restore-user) denna tid tas deras OneDrive-innehåll bort.</span><span class="sxs-lookup"><span data-stu-id="40628-109">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="40628-110">Om du vill behålla en tidigare användares OneDrive-filer ger du först dig själv åtkomst till deras OneDrive och flyttar sedan de filer du vill behålla.</span><span class="sxs-lookup"><span data-stu-id="40628-110">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="40628-111">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="40628-111">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="40628-112">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="40628-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="40628-113">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="40628-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="40628-114">Välj en användare.</span><span class="sxs-lookup"><span data-stu-id="40628-114">Select a user.</span></span>

3. <span data-ttu-id="40628-115">Välj OneDrive i det **högra fönstret.**</span><span class="sxs-lookup"><span data-stu-id="40628-115">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="40628-116">Under **Få åtkomst till filer** väljer du Skapa länk till **filer**.</span><span class="sxs-lookup"><span data-stu-id="40628-116">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="40628-117">Klicka på länken för att öppna filens plats.</span><span class="sxs-lookup"><span data-stu-id="40628-117">Select the link to open the file location.</span></span> <span data-ttu-id="40628-118">Ladda ned filerna till datorn  eller  välj Flytta till eller Kopiera för att flytta eller kopiera dem till din egen OneDrive eller till ett delat bibliotek.</span><span class="sxs-lookup"><span data-stu-id="40628-118">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="40628-119">Du kan flytta eller kopiera upp till 500 MB filer och mappar i taget.</span><span class="sxs-lookup"><span data-stu-id="40628-119">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="40628-120">När du flyttar eller kopierar dokument som har versionshistorik flyttas bara den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="40628-120">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="40628-121">Återkalla administratörsåtkomst till en användares OneDrive</span><span class="sxs-lookup"><span data-stu-id="40628-121">Revoke admin access to a user's OneDrive</span></span>

<span data-ttu-id="40628-122">Som global administratör kan du ge dig själv åtkomst till innehållet på en användares OneDrive, men du kanske vill ta bort åtkomsten när du inte längre behöver den.</span><span class="sxs-lookup"><span data-stu-id="40628-122">As global admin, you can give yourself access to the content in a user's OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

 ::: moniker range="o365-worldwide"

1. <span data-ttu-id="40628-123">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="40628-123">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="40628-124">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span><span class="sxs-lookup"><span data-stu-id="40628-124">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="40628-125">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="40628-125">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end 

2. <span data-ttu-id="40628-126">I den vänstra rutan väljer du **Administrationscenter** \> **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="40628-126">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="40628-127">(Eventuellt måste du välja **Visa alla för** att listan över administrationscenter ska visas.)</span><span class="sxs-lookup"><span data-stu-id="40628-127">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="40628-128">Om det klassiska administrationscentret för SharePoint visas väljer du **Öppna nu** högst upp på sidan för att öppna administrationscentret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="40628-128">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the SharePoint admin center.</span></span>

4. <span data-ttu-id="40628-129">I det vänstra fönstret väljer du **Fler funktioner.**</span><span class="sxs-lookup"><span data-stu-id="40628-129">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="40628-130">Under **Användarprofiler** väljer du **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="40628-130">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="40628-131">Under **Personer** väljer du **Hantera användarprofiler.**</span><span class="sxs-lookup"><span data-stu-id="40628-131">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="40628-132">Ange användarens namn och välj **Sök**.</span><span class="sxs-lookup"><span data-stu-id="40628-132">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="40628-133">Högerklicka på användaren och välj sedan Hantera **webbplatssamlingens ägare.**</span><span class="sxs-lookup"><span data-stu-id="40628-133">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="40628-134">Ta bort den person som inte längre behöver åtkomst till användarens data och välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="40628-134">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="40628-135">Komma åt Outlook-data för en tidigare användare</span><span class="sxs-lookup"><span data-stu-id="40628-135">Access the Outlook data of a former user</span></span>

<span data-ttu-id="40628-136">Om du vill spara e-postmeddelanden, kalender, uppgifter och kontakter från den tidigare anställda exporterar du informationen till en Outlook-datafil (.pst).</span><span class="sxs-lookup"><span data-stu-id="40628-136">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="40628-137">[Lägg till den tidigare anställdas e-postadress](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) i ditt Outlook (Om du återställer användarens lösenord kan du ange att det bara ska vara något du känner till.) [](reset-passwords.md)</span><span class="sxs-lookup"><span data-stu-id="40628-137">[Add the former employee's email](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="40628-138">Välj Arkiv **i** Outlook.</span><span class="sxs-lookup"><span data-stu-id="40628-138">In Outlook, select **File**.</span></span>
    
    ![Så här ser menyfliksområdet ut i Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="40628-140">Välj **Öppna &amp;** \> **export/import/export.**</span><span class="sxs-lookup"><span data-stu-id="40628-140">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Kommandot Importera/Exportera i Backstage-vyn](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="40628-142">Välj **Exportera till en fil** och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="40628-142">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![Alternativet Exportera till en fil i Importera-/exporteraguiden](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="40628-144">Välj **Outlook-datafil (.pst)** och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="40628-144">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="40628-145">Välj det konto som du vill exportera genom att välja namn eller e-postadress, till exempel Postlåda – Anna Weiler eller anne@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="40628-145">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="40628-146">Om du vill exportera allt på ditt konto, inklusive e-post, kalender, kontakter, uppgifter och anteckningar markerar du kryssrutan Inkludera undermappar. </span><span class="sxs-lookup"><span data-stu-id="40628-146">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="40628-147">Du kan exportera ett konto i taget.</span><span class="sxs-lookup"><span data-stu-id="40628-147">You can export one account at a time.</span></span> <span data-ttu-id="40628-148">Om du vill exportera flera konton upprepar du stegen efter att ett konto exporterats.</span><span class="sxs-lookup"><span data-stu-id="40628-148">If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![Dialogrutan Exportera Outlook-datafil med den översta mappen markerad och Inkludera undermappar markerad](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="40628-150">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="40628-150">Select **Next**.</span></span>
    
8. <span data-ttu-id="40628-151">Välj **Bläddra** och välj var du vill spara Outlook-datafilen (.pst).</span><span class="sxs-lookup"><span data-stu-id="40628-151">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="40628-152">Skriv ett  *filnamn och* välj sedan **OK för** att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="40628-152">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="40628-153">Om du har exporterat tidigare visas den förra mappsökvägen och filnamnet.</span><span class="sxs-lookup"><span data-stu-id="40628-153">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="40628-154">Skriv in *ett annat filnamn innan* du väljer **OK.**</span><span class="sxs-lookup"><span data-stu-id="40628-154">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="40628-155">Om du exporterar till en befintlig Outlook-datafil (.pst) anger du vad du vill göra under **Alternativ** när du exporterar objekt som redan finns i filen.</span><span class="sxs-lookup"><span data-stu-id="40628-155">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="40628-156">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="40628-156">Select **Finish**.</span></span>
    
<span data-ttu-id="40628-157">Outlook påbörjar exporten direkt om du inte skapar en ny Outlook-datafil (.pst) eller använder en lösenordskyddad fil.</span><span class="sxs-lookup"><span data-stu-id="40628-157">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="40628-158">Om du skapar en Outlook-datafil (.pst) kan du skydda filen med ett lösenord.</span><span class="sxs-lookup"><span data-stu-id="40628-158">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="40628-159">När dialogrutan **Skapa Outlook-datafil** visas anger du lösenordet *i* **rutorna Lösenord** och **Bekräfta** lösenord och väljer sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="40628-159">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="40628-160">Skriv **lösenordet i dialogrutan** Lösenord för Outlook-datafil *och* välj sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="40628-160">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="40628-161">Om du exporterar till en befintlig Outlook-datafil (.pst) som är lösenordsskyddad skriver du lösenordet i dialogrutan Lösenord för **Outlook-datafil** och väljer sedan **OK.**</span><span class="sxs-lookup"><span data-stu-id="40628-161">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="40628-162">Se hur du [exporterar eller säkerhetskopierar e-post, kontakter och kalender till en Outlook-fil (.pst)](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) i Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="40628-162">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="40628-163">Som standard är din e-post tillgänglig offline under en period på 12 månader.</span><span class="sxs-lookup"><span data-stu-id="40628-163">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="40628-164">Om det behövs kan du se hur [du kan öka de data som är tillgängliga offline](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span><span class="sxs-lookup"><span data-stu-id="40628-164">If required, see how to [increase the data available offline](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="40628-165">Ge en annan användare åtkomst till en tidigare anställds e-post</span><span class="sxs-lookup"><span data-stu-id="40628-165">Give another user access to a former user's email</span></span> 

<span data-ttu-id="40628-166">Om du vill ge åtkomst till e-postmeddelanden, kalender, uppgifter och kontakter hos den tidigare anställde till en annan anställd importerar du informationen till en annan anställds Outlook-inkorg.</span><span class="sxs-lookup"><span data-stu-id="40628-166">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="40628-167">Du kan också [konvertera den tidigare användarens postlåda till en](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) delad postlåda eller vidarebefordra en tidigare [anställds e-post till en annan anställd.](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)</span><span class="sxs-lookup"><span data-stu-id="40628-167">You can also [convert the former user's mailbox to a shared mailbox](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="40628-168">Gå till Öppna **export/import/export** \> **&amp; i** \> **Outlook.**</span><span class="sxs-lookup"><span data-stu-id="40628-168">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="40628-169">När du gör det startas Import-/exportguiden.</span><span class="sxs-lookup"><span data-stu-id="40628-169">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="40628-170">Välj **Importera från ett annat program eller en** fil och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="40628-170">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![Import-/exportguiden](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="40628-172">Välj **Outlook-datafil (.pst)** och sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="40628-172">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="40628-173">Bläddra till .pst-filen som du vill importera.</span><span class="sxs-lookup"><span data-stu-id="40628-173">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="40628-174">Välj **hur** dubbletter ska hanteras under Alternativ</span><span class="sxs-lookup"><span data-stu-id="40628-174">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="40628-175">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="40628-175">Select **Next**.</span></span>
    
7. <span data-ttu-id="40628-176">Om Outlook-datafilen (.pst) har tilldelats ett lösenord anger du lösenordet och väljer **sedan OK.**</span><span class="sxs-lookup"><span data-stu-id="40628-176">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="40628-177">Ange alternativen för importen av objekten.</span><span class="sxs-lookup"><span data-stu-id="40628-177">Set the options for importing items.</span></span> <span data-ttu-id="40628-178">Vanligtvis behöver du inte ändra standardinställningarna.</span><span class="sxs-lookup"><span data-stu-id="40628-178">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="40628-179">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="40628-179">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="40628-180">Stegen förblir desamma för åtkomst till en befintlig användares OneDrive och e-postdata.</span><span class="sxs-lookup"><span data-stu-id="40628-180">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="40628-181">Om du bara vill importera eller återställa ett fåtal objekt från en Outlook-datafil (.pst) kan du öppna Outlook-datafilen.</span><span class="sxs-lookup"><span data-stu-id="40628-181">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="40628-182">Dra sedan objekten från mapparna med Outlook-datafiler till de befintliga Outlook-mapparna i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="40628-182">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="40628-183">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="40628-183">Related articles</span></span>
[<span data-ttu-id="40628-184">Ta bort en tidigare anställd från Office 365</span><span class="sxs-lookup"><span data-stu-id="40628-184">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="40628-185">Lägga till och ta bort administratörer för ett OneDrive-konto</span><span class="sxs-lookup"><span data-stu-id="40628-185">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="40628-186">Återställa en borttagna OneDrive</span><span class="sxs-lookup"><span data-stu-id="40628-186">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="40628-187">OneDrive-bevarande och borttagning</span><span class="sxs-lookup"><span data-stu-id="40628-187">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
