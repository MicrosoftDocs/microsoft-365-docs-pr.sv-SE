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
description: Läs om hur du bevarar en medarbetares filer och e-postmeddelanden när personen lämnar organisationen.
ms.openlocfilehash: 2bf32aa9e7a3dcc76ae2114240bff07d697ce29d
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387207"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a><span data-ttu-id="53c33-103">Få åtkomst till och säkerhetskopiera en tidigare anställds användardata.</span><span class="sxs-lookup"><span data-stu-id="53c33-103">Get access to and back up a former user's data</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="53c33-104">Administrationscentret förändras.</span><span class="sxs-lookup"><span data-stu-id="53c33-104">The admin center is changing.</span></span> <span data-ttu-id="53c33-105">Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="53c33-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end


<span data-ttu-id="53c33-106">När en medarbetare lämnar organisationen vill du förmodligen komma åt deras data (dokument och e-postmeddelanden) och antingen granska dem, säkerhetskopiera den eller ge den till en ny medarbetare.</span><span class="sxs-lookup"><span data-stu-id="53c33-106">When an employee leaves your organization, you probably want to access their data (documents and emails) and either review it, back it up, or give it to a new employee.</span></span>
  
    
## <a name="access-a-former-users-onedrive-documents"></a><span data-ttu-id="53c33-107">Komma åt en tidigare användares OneDrive-dokument</span><span class="sxs-lookup"><span data-stu-id="53c33-107">Access a former user's OneDrive documents</span></span>

<span data-ttu-id="53c33-108">Om du tar bort en användares licens men inte tar bort kontot kan du ge dig själv åtkomst till innehållet på användarens OneDrive.</span><span class="sxs-lookup"><span data-stu-id="53c33-108">If you remove a user's license but don't delete the account, you can give yourself access to the content in the user's OneDrive.</span></span> <span data-ttu-id="53c33-109">Om du tar bort användarens konto har du som standard 30 dagar på dig att komma åt den tidigare användarens OneDrive-data.</span><span class="sxs-lookup"><span data-stu-id="53c33-109">If you delete the user's account, you have 30 days by default to access the former user's OneDrive data.</span></span> <span data-ttu-id="53c33-110">[Lär dig hur du ställer in OneDrive-kvarhållningen för borttagna användare](/onedrive/set-retention).</span><span class="sxs-lookup"><span data-stu-id="53c33-110">[Learn how to set the OneDrive retention for deleted users](/onedrive/set-retention).</span></span> <span data-ttu-id="53c33-111">Om du inte [återställer ett användarkonto](/office365/admin/add-users/restore-user) inom den här tiden tas deras OneDrive-innehåll bort.</span><span class="sxs-lookup"><span data-stu-id="53c33-111">If you don't [restore a user account](/office365/admin/add-users/restore-user) within this time, their OneDrive content is deleted.</span></span> 

<span data-ttu-id="53c33-112">Om du vill bevara en tidigare användares OneDrive-filer ger du dig först åtkomst till deras OneDrive och flyttar sedan de filer du vill behålla.</span><span class="sxs-lookup"><span data-stu-id="53c33-112">To preserve a former user's OneDrive files, first give yourself access to their OneDrive, and then move the files you want to keep.</span></span> 

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="53c33-113">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="53c33-113">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="53c33-114">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="53c33-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  
    
2. <span data-ttu-id="53c33-115">Välj en användare.</span><span class="sxs-lookup"><span data-stu-id="53c33-115">Select a user.</span></span>

3. <span data-ttu-id="53c33-116">Välj **OneDrive**i den högra rutan .</span><span class="sxs-lookup"><span data-stu-id="53c33-116">In the right pane, select **OneDrive**.</span></span> <span data-ttu-id="53c33-117">Under **Hämta åtkomst till filer**väljer du Skapa länk till **filer**.</span><span class="sxs-lookup"><span data-stu-id="53c33-117">Under **Get access to files**, select **Create link to files**.</span></span>

4. <span data-ttu-id="53c33-118">Välj länken för att öppna filplatsen.</span><span class="sxs-lookup"><span data-stu-id="53c33-118">Select the link to open the file location.</span></span> <span data-ttu-id="53c33-119">Ladda ned filerna till datorn eller välj **Flytta till** eller Kopiera **för att** flytta eller kopiera dem till din egen OneDrive eller till ett delat bibliotek.</span><span class="sxs-lookup"><span data-stu-id="53c33-119">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="53c33-120">Du kan flytta eller kopiera upp till 500 MB filer och mappar åt gången.</span><span class="sxs-lookup"><span data-stu-id="53c33-120">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="53c33-121">När du flyttar eller kopierar dokument med versionshistorik flyttas bara den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="53c33-121">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="53c33-122">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="53c33-122">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="53c33-123">Välj en användare.</span><span class="sxs-lookup"><span data-stu-id="53c33-123">Select a user.</span></span>

3. <span data-ttu-id="53c33-124">Expandera **OneDrive-inställningar i**den högra rutan och välj sedan **Access-filer bredvid** **Access**.</span><span class="sxs-lookup"><span data-stu-id="53c33-124">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="53c33-125">Välj länken för att öppna filplatsen.</span><span class="sxs-lookup"><span data-stu-id="53c33-125">Select the link to open the file location.</span></span> <span data-ttu-id="53c33-126">Ladda ned filerna till datorn eller välj **Flytta till** eller Kopiera **för att** flytta eller kopiera dem till din egen OneDrive eller till ett delat bibliotek.</span><span class="sxs-lookup"><span data-stu-id="53c33-126">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span> 

> [!NOTE]
> <span data-ttu-id="53c33-127">Du kan flytta eller kopiera upp till 500 MB filer och mappar åt gången.</span><span class="sxs-lookup"><span data-stu-id="53c33-127">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="53c33-128">När du flyttar eller kopierar dokument med versionshistorik flyttas bara den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="53c33-128">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="53c33-129">I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktiva användare</a>.</span><span class="sxs-lookup"><span data-stu-id="53c33-129">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="53c33-130">Välj en användare.</span><span class="sxs-lookup"><span data-stu-id="53c33-130">Select a user.</span></span>

3. <span data-ttu-id="53c33-131">Expandera **OneDrive-inställningar i**den högra rutan och välj sedan **Access-filer bredvid** **Access**.</span><span class="sxs-lookup"><span data-stu-id="53c33-131">In the right pane, expand **OneDrive Settings**, and then next to **Access**, select **Access files**.</span></span>

4. <span data-ttu-id="53c33-132">Välj länken för att öppna filplatsen.</span><span class="sxs-lookup"><span data-stu-id="53c33-132">Select the link to open the file location.</span></span> <span data-ttu-id="53c33-133">Ladda ned filerna till datorn eller välj **Flytta till** eller Kopiera **för att** flytta eller kopiera dem till din egen OneDrive eller till ett delat bibliotek.</span><span class="sxs-lookup"><span data-stu-id="53c33-133">Download the files to your computer, or select **Move to** or **Copy to** to move or copy them to your own OneDrive or to a shared library.</span></span>  

> [!NOTE]
> <span data-ttu-id="53c33-134">Du kan flytta eller kopiera upp till 500 MB filer och mappar åt gången.</span><span class="sxs-lookup"><span data-stu-id="53c33-134">You can move or copy up to 500 MB of files and folders at a time.</span></span><br/>
> <span data-ttu-id="53c33-135">När du flyttar eller kopierar dokument med versionshistorik flyttas bara den senaste versionen.</span><span class="sxs-lookup"><span data-stu-id="53c33-135">When you move or copy documents that have version history, only the latest version is moved.</span></span>  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a><span data-ttu-id="53c33-136">Återkalla administratörsåtkomst till en användares OneDrive</span><span class="sxs-lookup"><span data-stu-id="53c33-136">Revoke admin access to a user's OneDrive</span></span>

<span data-ttu-id="53c33-137">Som global administratör kan du ge dig själv tillgång till innehållet på en användares OneDrive, men du kanske vill ta bort din åtkomst när du inte längre behöver det.</span><span class="sxs-lookup"><span data-stu-id="53c33-137">As global admin, you can give yourself access to the content in a user's OneDrive, but you may want to remove your access when you no longer need it.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="53c33-138">Logga in på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">administrationscentret</a> som global administratör eller SharePoint-administratör.</span><span class="sxs-lookup"><span data-stu-id="53c33-138">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span> 

    <span data-ttu-id="53c33-139">Om du får ett meddelande om att du inte har behörighet att komma åt administrationscentret har du inte administratörsbehörighet i organisationen.</span><span class="sxs-lookup"><span data-stu-id="53c33-139">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="53c33-140">Logga in på <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">administrationscentret</a> som global administratör eller SharePoint-administratör.</span><span class="sxs-lookup"><span data-stu-id="53c33-140">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="53c33-141">Om du får ett meddelande om att du inte har behörighet att komma åt administrationscentret har du inte administratörsbehörighet i organisationen.</span><span class="sxs-lookup"><span data-stu-id="53c33-141">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="53c33-142">Logga in på <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">administrationscentret</a> som global administratör eller SharePoint-administratör.</span><span class="sxs-lookup"><span data-stu-id="53c33-142">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a> as a global admin or SharePoint admin.</span></span>

    <span data-ttu-id="53c33-143">Om du får ett meddelande om att du inte har behörighet att komma åt administrationscentret har du inte administratörsbehörighet i organisationen.</span><span class="sxs-lookup"><span data-stu-id="53c33-143">If you get a message that you don't have permission to access the admin center, then you don't have administrator permissions in your organization.</span></span>

::: moniker-end

2. <span data-ttu-id="53c33-144">Välj **Administrationscenter** \> **SharePoint**i den vänstra rutan .</span><span class="sxs-lookup"><span data-stu-id="53c33-144">In the left pane, select **Admin centers** \> **SharePoint**.</span></span> <span data-ttu-id="53c33-145">(Du kan behöva välja **Visa alla** för att se listan över administrationscenter.)</span><span class="sxs-lookup"><span data-stu-id="53c33-145">(You might need to select **Show all** to see the list of admin centers.)</span></span>

3. <span data-ttu-id="53c33-146">Om det klassiska Administrationscentret för SharePoint visas väljer du **Öppna det nu** högst upp på sidan för att öppna det nya Administrationscentret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="53c33-146">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

4. <span data-ttu-id="53c33-147">Välj **Fler funktioner**i den vänstra rutan .</span><span class="sxs-lookup"><span data-stu-id="53c33-147">In the left pane, select **More features**.</span></span>

5. <span data-ttu-id="53c33-148">Under **Användarprofiler**väljer du **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="53c33-148">Under **User profiles**, select **Open**.</span></span>

6. <span data-ttu-id="53c33-149">Under **Kontakter**väljer du **Hantera användarprofiler**.</span><span class="sxs-lookup"><span data-stu-id="53c33-149">Under **People**, select **Manage User Profiles**.</span></span>

7. <span data-ttu-id="53c33-150">Ange användarens namn och välj **Sök**.</span><span class="sxs-lookup"><span data-stu-id="53c33-150">Enter the user's name and select **Find**.</span></span>

8. <span data-ttu-id="53c33-151">Högerklicka på användaren och välj sedan **Hantera webbplatssamlingsägare**.</span><span class="sxs-lookup"><span data-stu-id="53c33-151">Right-click the user, and then choose **Manage site collection owners**.</span></span>

9. <span data-ttu-id="53c33-152">Ta bort personen som inte längre behöver åtkomst till användarens data och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="53c33-152">Remove the person who no longer needs access to the user's data, and then select **OK**.</span></span>

    
## <a name="access-the-outlook-data-of-a-former-user"></a><span data-ttu-id="53c33-153">Komma åt Outlook-data för en tidigare användare</span><span class="sxs-lookup"><span data-stu-id="53c33-153">Access the Outlook data of a former user</span></span>

<span data-ttu-id="53c33-154">Om du vill spara e-postmeddelanden, kalender, uppgifter och kontakter för den tidigare medarbetaren exporterar du informationen till en Outlook-datafil (.pst).</span><span class="sxs-lookup"><span data-stu-id="53c33-154">To save the email messages, calendar, tasks, and contacts of the former employee, export the information to an Outlook Data File (.pst).</span></span>
  
1. <span data-ttu-id="53c33-155">[Lägg till den tidigare anställdes e-post](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) i Outlook (Om du [återställer användarens lösenord](reset-passwords.md)kan du ställa in det till något som bara du vet.)</span><span class="sxs-lookup"><span data-stu-id="53c33-155">[Add the former employee's email](https://support.office.com/article/6e27792a-9267-4aa4-8bb6-c84ef146101b.aspx) to your Outlook (If you [reset the user's password](reset-passwords.md), you can set it to something only you know.)</span></span>
    
2. <span data-ttu-id="53c33-156">Välj **Arkiv**i Outlook .</span><span class="sxs-lookup"><span data-stu-id="53c33-156">In Outlook, select **File**.</span></span>
    
    ![Så här ser menyfliksområdet ut i Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. <span data-ttu-id="53c33-158">Välj **Öppna &amp; Exportera** \> **import/export**.</span><span class="sxs-lookup"><span data-stu-id="53c33-158">Select **Open &amp; Export** \> **Import/Export**.</span></span>
    
    ![Kommandot Importera/Exportera i Backstage-vyn](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. <span data-ttu-id="53c33-160">Välj **Exportera till en fil**och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="53c33-160">Select **Export to a file**, and then select **Next**.</span></span>
    
    ![Alternativet Exportera till en fil i Importera-/exporteraguiden](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. <span data-ttu-id="53c33-162">Välj **Outlook-datafil (.pst)** och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="53c33-162">Select **Outlook Data File (.pst)**, and then select **Next**.</span></span>
    
6. <span data-ttu-id="53c33-163">Välj det konto som du vill exportera genom att välja namn eller e-postadress, till exempel Postlåda - Anne Weiler eller anne@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="53c33-163">Select the account you want to export by selecting the name or email address, such as Mailbox - Anne Weiler or anne@contoso.com.</span></span> <span data-ttu-id="53c33-164">Om du vill exportera allt i ditt konto, inklusive e-post, kalender, kontakter, uppgifter och anteckningar, kontrollerar du att kryssrutan **Inkludera undermappar** är markerad.</span><span class="sxs-lookup"><span data-stu-id="53c33-164">If you want to export everything in your account, including mail, calendar, contacts, tasks, and notes, make sure the **Include subfolders** check box is selected.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="53c33-165">Du kan exportera ett konto i taget.</span><span class="sxs-lookup"><span data-stu-id="53c33-165">You can export one account at a time.</span></span> <span data-ttu-id="53c33-166">Om du vill exportera flera konton upprepar du dessa steg när ett konto har exporterats.</span><span class="sxs-lookup"><span data-stu-id="53c33-166">If you want to export multiple accounts, after one account is exported, repeat these steps.</span></span> 
  
    ![Dialogrutan Exportera Outlook-datafil med den översta mappen markerad och Inkludera undermappar markerad](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. <span data-ttu-id="53c33-168">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="53c33-168">Select **Next**.</span></span>
    
8. <span data-ttu-id="53c33-169">Välj **Bläddra** för att välja var Outlook-datafilen (.pst) ska sparas.</span><span class="sxs-lookup"><span data-stu-id="53c33-169">Select **Browse** to select where to save the Outlook Data File (.pst).</span></span> <span data-ttu-id="53c33-170">Skriv ett *filnamn*och välj sedan **OK** för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="53c33-170">Type a  *file name*, and then select **OK** to continue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="53c33-171">Om du har exporterat tidigare visas den förra mappsökvägen och filnamnet.</span><span class="sxs-lookup"><span data-stu-id="53c33-171">If you've used export before, the previous folder location and file name appear.</span></span> <span data-ttu-id="53c33-172">Skriv ett *annat filnamn* innan du väljer **OK**.</span><span class="sxs-lookup"><span data-stu-id="53c33-172">Type a  *different file name*  before selecting **OK**.</span></span> 
  
9. <span data-ttu-id="53c33-173">Om du exporterar till en befintlig Outlook-datafil (.pst) anger du vad du vill göra under **Alternativ** när du exporterar objekt som redan finns i filen.</span><span class="sxs-lookup"><span data-stu-id="53c33-173">If you are exporting to an existing Outlook Data File (.pst), under **Options**, specify what to do when exporting items that already exist in the file.</span></span>
    
10. <span data-ttu-id="53c33-174">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="53c33-174">Select **Finish**.</span></span>
    
<span data-ttu-id="53c33-175">Outlook påbörjar exporten direkt om du inte skapar en ny Outlook-datafil (.pst) eller använder en lösenordskyddad fil.</span><span class="sxs-lookup"><span data-stu-id="53c33-175">Outlook begins the export immediately unless a new Outlook Data File (.pst) is created or a password-protected file is used.</span></span>
  
   - <span data-ttu-id="53c33-176">Om du skapar en Outlook-datafil (.pst) kan du skydda filen med ett lösenord.</span><span class="sxs-lookup"><span data-stu-id="53c33-176">If you're creating an Outlook Data File (.pst), an optional password can help protect the file.</span></span> <span data-ttu-id="53c33-177">När dialogrutan **Skapa Outlook-datafil** visas skriver du *lösenordet* i rutorna **Lösenord** och **Verifiera lösenord** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="53c33-177">When the **Create Outlook Data File** dialog box appears, type the  *password*  in the **Password** and **Verify Password** boxes, and then select **OK**.</span></span> <span data-ttu-id="53c33-178">Skriv *lösenordet*i dialogrutan **Lösenord för Outlook-datafil** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="53c33-178">In the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
  - <span data-ttu-id="53c33-179">Om du exporterar till en befintlig Outlook-datafil (.pst) som är lösenordsskyddad skriver du *lösenordet*i dialogrutan **Lösenord för Outlook-datafil** och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="53c33-179">If you're exporting to an existing Outlook Data File (.pst) that is password protected, in the **Outlook Data File Password** dialog box, type the  *password*, and then select **OK**.</span></span>
    
<span data-ttu-id="53c33-180">Lär dig hur du [exporterar eller säkerhetskopierar e-post, kontakter och kalender till en PST-fil](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) i Outlook 2010.</span><span class="sxs-lookup"><span data-stu-id="53c33-180">See how to [Export or backup email, contacts, and calendar to an Outlook .pst file](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx) in Outlook 2010.</span></span> 
  
  
  > [!NOTE]
  > <span data-ttu-id="53c33-181">Som standard är din e-post tillgänglig offline under en period av 12 månader.</span><span class="sxs-lookup"><span data-stu-id="53c33-181">By default, your email is available offline for a period of 12 months.</span></span> <span data-ttu-id="53c33-182">Om det behövs kan du se hur du [ökar tillgängliga data offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span><span class="sxs-lookup"><span data-stu-id="53c33-182">If required, see how to [increase the data available offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).</span></span>
 
## <a name="give-another-user-access-to-a-former-users-email"></a><span data-ttu-id="53c33-183">Ge en annan användare åtkomst till en tidigare användares e-post</span><span class="sxs-lookup"><span data-stu-id="53c33-183">Give another user access to a former user's email</span></span> 

<span data-ttu-id="53c33-184">Om du vill ge åtkomst till den tidigare medarbetarens e-postmeddelanden, kalender, uppgifter och kontakter till en annan anställd importerar du informationen till en annan medarbetares Outlook-inkorg.</span><span class="sxs-lookup"><span data-stu-id="53c33-184">To give access to the email messages, calendar, tasks, and contacts of the former employee to another employee, import the information to another employee's Outlook inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="53c33-185">Du kan också [konvertera den tidigare användarens postlåda till en delad postlåda](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) eller [vidarebefordra en tidigare anställds e-post till en annan anställd](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span><span class="sxs-lookup"><span data-stu-id="53c33-185">You can also [convert the former user's mailbox to a shared mailbox](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) or [forward a former employee's email to another employee](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).</span></span>

  
1. <span data-ttu-id="53c33-186">Gå till **File** \> \*\* &amp; Filöppnad\*\* \> **exportimport/export**i Outlook .</span><span class="sxs-lookup"><span data-stu-id="53c33-186">In Outlook, go to **File** \> **Open &amp; Export** \> **Import/Export**.</span></span>
    
    <span data-ttu-id="53c33-187">När du gör det startas Import-/exportguiden.</span><span class="sxs-lookup"><span data-stu-id="53c33-187">This starts the Import and Export Wizard.</span></span>
    
2. <span data-ttu-id="53c33-188">Välj **Importera från ett annat program eller en annan fil**och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="53c33-188">Select **Import from another program or file**, and then select **Next**.</span></span>
    
    ![Import-/exportguiden](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. <span data-ttu-id="53c33-190">Välj **Outlook-datafil (.pst)** och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="53c33-190">Select **Outlook Data File (.pst)**, and select **Next**.</span></span>
    
4. <span data-ttu-id="53c33-191">Bläddra till .pst-filen som du vill importera.</span><span class="sxs-lookup"><span data-stu-id="53c33-191">Browse to the .pst file you want to import.</span></span>
    
5. <span data-ttu-id="53c33-192">Under **Alternativ**väljer du hur du vill hantera dubbletter</span><span class="sxs-lookup"><span data-stu-id="53c33-192">Under **Options**, choose how you want to deal with duplicates</span></span>
    
6. <span data-ttu-id="53c33-193">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="53c33-193">Select **Next**.</span></span>
    
7. <span data-ttu-id="53c33-194">Om ett lösenord har tilldelats Outlook-datafilen (.pst) anger du lösenordet och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="53c33-194">If a password was assigned to the Outlook Data File (.pst), enter the password, and then select **OK**.</span></span>
    
8. <span data-ttu-id="53c33-195">Ange alternativen för importen av objekten.</span><span class="sxs-lookup"><span data-stu-id="53c33-195">Set the options for importing items.</span></span> <span data-ttu-id="53c33-196">Vanligtvis behöver du inte ändra standardinställningarna.</span><span class="sxs-lookup"><span data-stu-id="53c33-196">The default settings usually don't need to be changed.</span></span>
    
9. <span data-ttu-id="53c33-197">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="53c33-197">Select **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="53c33-198">Stegen förblir desamma för åtkomst till en befintlig användares OneDrive- och e-postdata.</span><span class="sxs-lookup"><span data-stu-id="53c33-198">The steps remain the same for accessing an existing user's OneDrive and email data.</span></span>
    
> [!TIP]
> <span data-ttu-id="53c33-199">Om du bara vill importera eller återställa ett fåtal objekt från en Outlook-datafil (.pst) kan du öppna Outlook-datafilen.</span><span class="sxs-lookup"><span data-stu-id="53c33-199">If you want to import or restore only a few items from an Outlook Data File (.pst), you can open the Outlook Data File.</span></span> <span data-ttu-id="53c33-200">Dra sedan objekten från Outlook-datafilsmappar till befintliga Outlook-mappar i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="53c33-200">Then, in the navigation pane, drag the items from Outlook Data File folders to your existing Outlook folders.</span></span> 
  
  
## <a name="related-articles"></a><span data-ttu-id="53c33-201">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="53c33-201">Related articles</span></span>
[<span data-ttu-id="53c33-202">Ta bort en tidigare anställd från Office 365</span><span class="sxs-lookup"><span data-stu-id="53c33-202">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="53c33-203">Lägga till och ta bort administratörer på ett OneDrive-konto</span><span class="sxs-lookup"><span data-stu-id="53c33-203">Add and remove admins on a OneDrive account</span></span>](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[<span data-ttu-id="53c33-204">Återställa en borttagen OneDrive</span><span class="sxs-lookup"><span data-stu-id="53c33-204">Restore a deleted OneDrive</span></span>](/onedrive/restore-deleted-onedrive)
  
[<span data-ttu-id="53c33-205">Bevarande och borttagning av OneDrive</span><span class="sxs-lookup"><span data-stu-id="53c33-205">OneDrive retention and deletion</span></span>](/onedrive/retention-and-deletion)
  
