---
title: Massimport av externa kontakter till Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: Lär dig hur administratörer kan använda Exchange Online PowerShell och en CSV-fil för att massimporter av externa kontakter till den globala adresslistan.
ms.openlocfilehash: 178e3676f8dc5fb59cdad9cc46d7ecbd9dddb90e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162020"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a><span data-ttu-id="52732-103">Massimport av externa kontakter till Exchange Online</span><span class="sxs-lookup"><span data-stu-id="52732-103">Bulk import external contacts to Exchange Online</span></span>

<span data-ttu-id="52732-104">**Den här artikeln är för administratörer. Försöker du importera kontakter till din egen postlåda? Läs [Importera kontakter till Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span><span class="sxs-lookup"><span data-stu-id="52732-104">**This article is for administrators. Are you trying to import contacts to your own mailbox? See [Import contacts to Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**</span></span>
   
<span data-ttu-id="52732-105">Har ditt företag många befintliga affärskontakter som du vill ta med i den delade adressboken (kallas även global adresslista) i Exchange Online?</span><span class="sxs-lookup"><span data-stu-id="52732-105">Does your company have lots of existing business contacts that you want to include in the shared address book (also called the global address list) in Exchange Online?</span></span> <span data-ttu-id="52732-106">Vill du lägga till externa kontakter som medlemmar i distributionsgrupper, precis som med användare inom företaget?</span><span class="sxs-lookup"><span data-stu-id="52732-106">Do you want to add external contacts as members of distribution groups, just like you can with users inside your company?</span></span> <span data-ttu-id="52732-107">I så fall kan du använda Exchange Online PowerShell och en CSV-fil (kommaavgränsade värden) för att massimporta externa kontakter till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="52732-107">If so, you can use Exchange Online PowerShell and a CSV (comma-separated value) file to bulk import external contacts into Exchange Online.</span></span> <span data-ttu-id="52732-108">Processen i tre steg:</span><span class="sxs-lookup"><span data-stu-id="52732-108">It's a three-step process:</span></span>
  
[<span data-ttu-id="52732-109">Steg 1: Skapa en CSV-fil som innehåller information om de externa kontakterna</span><span class="sxs-lookup"><span data-stu-id="52732-109">Step 1: Create a CSV file that contains information about the external contacts</span></span>](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[<span data-ttu-id="52732-110">Steg 2: Skapa de externa kontakterna med PowerShell</span><span class="sxs-lookup"><span data-stu-id="52732-110">Step 2: Create the external contacts with PowerShell</span></span>](#step-2-create-the-external-contacts-with-powershell) 

[<span data-ttu-id="52732-111">Steg 3: Lägg till information i egenskaperna för de externa kontakterna</span><span class="sxs-lookup"><span data-stu-id="52732-111">Step 3: Add information to the properties of the external contacts</span></span>](#step-3-add-information-to-the-properties-of-the-external-contacts)

<span data-ttu-id="52732-112">När du har slutfört de här stegen för att importera kontakter kan du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="52732-112">After you complete these steps to import contacts, you can perform these additional tasks:</span></span>
  
- [<span data-ttu-id="52732-113">Lägga till fler externa kontakter</span><span class="sxs-lookup"><span data-stu-id="52732-113">Add more external contacts</span></span>](#add-more-external-contacts)
  
- [<span data-ttu-id="52732-114">Dölja externa kontakter från den delade adressboken</span><span class="sxs-lookup"><span data-stu-id="52732-114">Hide external contacts from the shared address book</span></span>](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a><span data-ttu-id="52732-115">Steg 1: Skapa en CSV-fil som innehåller information om de externa kontakterna</span><span class="sxs-lookup"><span data-stu-id="52732-115">Step 1: Create a CSV file that contains information about the external contacts</span></span>

<span data-ttu-id="52732-116">Det första steget är att skapa en CSV-fil som innehåller information om varje extern kontakt som du vill importera till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="52732-116">The first step is to create a CSV file that contains information about each external contact that you want to import to Exchange Online.</span></span> 
  
1. <span data-ttu-id="52732-117">Kopiera följande text till en textfil i Anteckningar och spara den på skrivbordet som en CSV-fil med hjälp av ett filnamnssuffix .csv. till exempel ExternalContacts.csv.</span><span class="sxs-lookup"><span data-stu-id="52732-117">Copy the following text to a text file in NotePad, and save it on your desktop as a CSV file by using a filename suffix of .csv; for example, ExternalContacts.csv.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="52732-118">Om språket innehåller specialtecken (till exempel **å,** **ä** och **ö** på svenska) sparar du CSV-filen med UTF-8-kodning eller annan Unicode-kodning när du sparar filen i Anteckningar.</span><span class="sxs-lookup"><span data-stu-id="52732-118">If your language contains special characters (such as **å**, **ä**, and **ö** in Swedish) save the CSV file with UTF-8 or other Unicode encoding when you save the file in NotePad.</span></span> 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    <span data-ttu-id="52732-119">Den första raden, eller rubrikraden, i CSV-filen innehåller egenskaper för kontakter som kan användas när du importerar dem till Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="52732-119">The first row, or header row, of the CSV file lists the properties of contacts that can be used when you import them to Exchange Online.</span></span> <span data-ttu-id="52732-120">Varje egenskapsnamn avgränsas med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="52732-120">Each property name is separated by a comma.</span></span> <span data-ttu-id="52732-121">Varje rad under rubrikraden representerar egenskapsvärdena för att importera en enskild extern kontakt.</span><span class="sxs-lookup"><span data-stu-id="52732-121">Each row under the header row represents the property values for importing a single external contact.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="52732-122">Den här texten innehåller exempeldata som du kan ta bort.</span><span class="sxs-lookup"><span data-stu-id="52732-122">This text includes sample data, which you can delete.</span></span> <span data-ttu-id="52732-123">Men ta inte bort eller ändra den första raden (rubrikraden).</span><span class="sxs-lookup"><span data-stu-id="52732-123">But don't delete or change the first (header) row.</span></span> <span data-ttu-id="52732-124">Den innehåller alla egenskaper för de externa kontakterna.</span><span class="sxs-lookup"><span data-stu-id="52732-124">It contains all of the properties for the external contacts.</span></span> 
  
2. <span data-ttu-id="52732-125">Öppna CSV-filen i Microsoft Excel redigera CSV-filen eftersom det är mycket enklare att använda Excel redigera CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="52732-125">Open the CSV file in Microsoft Excel to edit the CSV file because it's much easier to use Excel to edit the CSV file.</span></span>
    
3. <span data-ttu-id="52732-126">Skapa en rad för varje kontakt som du vill importera för att Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="52732-126">Create a row for each contact that you want to import to Exchange Online.</span></span> <span data-ttu-id="52732-127">Fyll i så många celler som möjligt.</span><span class="sxs-lookup"><span data-stu-id="52732-127">Populate as many of the cells as possible.</span></span> <span data-ttu-id="52732-128">Den här informationen visas i den delade adressboken för varje kontakt.</span><span class="sxs-lookup"><span data-stu-id="52732-128">This information will be displayed in the shared address book for each contact.</span></span> 
    
    > [!IMPORTANT]
    >  <span data-ttu-id="52732-129">Följande egenskaper (som är de fyra första objekten på rubrikraden) krävs för att skapa en extern kontakt och måste vara ifyllda i CSV-filen: **ExternalEmailAddress,** **Name**, **FirstName,** **LastName**.</span><span class="sxs-lookup"><span data-stu-id="52732-129">The following properties (which are the first four items in the header row) are required to create an external contact and must be populated in the CSV file: **ExternalEmailAddress**, **Name**, **FirstName**, **LastName**.</span></span> <span data-ttu-id="52732-130">PowerShell-kommandot som du kör i Steg 2 använder värdena för dessa egenskaper för att skapa kontakterna.</span><span class="sxs-lookup"><span data-stu-id="52732-130">The PowerShell command that you run in Step 2 will use the values for these properties to create the contacts.</span></span> 

## <a name="step-2-create-the-external-contacts-with-powershell"></a><span data-ttu-id="52732-131">Steg 2: Skapa de externa kontakterna med PowerShell</span><span class="sxs-lookup"><span data-stu-id="52732-131">Step 2: Create the external contacts with PowerShell</span></span>

<span data-ttu-id="52732-132">Nästa steg är att använda CSV-filen som du skapade i Steg 1 och PowerShell för att massimporter av externa kontakter som visas i CSV-filen Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="52732-132">The next step is to use the CSV file that you created in Step 1 and PowerShell to bulk import the external contacts listed in the CSV file to Exchange Online.</span></span> 
  
1.  <span data-ttu-id="52732-133">Anslut PowerShell till din Exchange Online organisation.</span><span class="sxs-lookup"><span data-stu-id="52732-133">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="52732-134">Stegvisa instruktioner finns i Skapa [Anslut-Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="52732-134">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="52732-135">Se till att använda användarnamnet och lösenordet för ditt globala administratörskonto när du ansluter till Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="52732-135">Be sure to use the user name and password for your global administrator account when you connect to Exchange Online PowerShell.</span></span> 
    
2. <span data-ttu-id="52732-136">När du har anslutt PowerShell Exchange Online går du till skrivbordsmappen där du sparade CSV-filen i steg 1. till exempel `C:\Users\Administrator\desktop` .</span><span class="sxs-lookup"><span data-stu-id="52732-136">After you connect PowerShell to Exchange Online, go to the desktop folder where you saved the CSV file in Step 1; for example `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="52732-137">Kör följande kommando för att skapa de externa kontakterna:</span><span class="sxs-lookup"><span data-stu-id="52732-137">Run the following command to create the external contacts:</span></span>

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    <span data-ttu-id="52732-138">Det kan ta en stund att skapa de nya kontakterna, beroende på hur många du importerar.</span><span class="sxs-lookup"><span data-stu-id="52732-138">It might take a while to create the new contacts, depending on how many you're importing.</span></span> <span data-ttu-id="52732-139">När kommandot har körts klart visas en lista i PowerShell över de nya kontakter som har skapats.</span><span class="sxs-lookup"><span data-stu-id="52732-139">When the command is finished running, PowerShell displays a list of the new contacts that were created.</span></span> 
    
4. <span data-ttu-id="52732-140">Om du vill visa de nya externa kontakterna går du till Exchange (EAC) och klickar sedan **på Mottagare** \> **kontakter**.</span><span class="sxs-lookup"><span data-stu-id="52732-140">To view the new external contacts, go to the Exchange admin center (EAC), and then click **Recipients** \> **Contacts**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="52732-141">Anvisningar för hur du ansluter till EAC finns Exchange [administrationscenter i Exchange Online](/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="52732-141">For instructions for connecting to the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span> 
  
5. <span data-ttu-id="52732-142">Om det behövs klickar **du på** Uppdatera för att uppdatera listan och se de externa kontakter som har importerats.</span><span class="sxs-lookup"><span data-stu-id="52732-142">If necessary, click **Refresh** to update the list and see the external contacts that were imported.</span></span> 
    
    <span data-ttu-id="52732-143">De importerade kontakterna visas i den delade adressboken i Outlook och Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="52732-143">The imported contacts will appear in the shared address book in Outlook and Outlook on the web.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="52732-144">Du kan också visa kontakterna i Microsoft 365 administrationscenter  genom att gå till \> **Användarkontakter.**</span><span class="sxs-lookup"><span data-stu-id="52732-144">You can also view the contacts in the Microsoft 365 admin center by going to **Users** \> **Contacts**.</span></span> 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a><span data-ttu-id="52732-145">Steg 3: Lägg till information i egenskaperna för de externa kontakterna</span><span class="sxs-lookup"><span data-stu-id="52732-145">Step 3: Add information to the properties of the external contacts</span></span>

<span data-ttu-id="52732-146">När du har kört kommandot i steg 2 skapas de externa kontakterna, men de innehåller ingen kontakt- eller organisationsinformation, det vill säga informationen från de flesta celler i CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="52732-146">After you run the command in Step 2, the external contacts are created, but they don't contain any of the contact or organization information, which is the information from most of the cells in the CSV file.</span></span> <span data-ttu-id="52732-147">Det beror på att när du skapar nya externa kontakter fylls bara de obligatoriska egenskaperna i.</span><span class="sxs-lookup"><span data-stu-id="52732-147">This is because when you create new external contacts, only the required properties are populated.</span></span> <span data-ttu-id="52732-148">Oroa dig inte om du inte har all information ifylld i CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="52732-148">Don't worry if you don't have all the information populated in the CSV file.</span></span> <span data-ttu-id="52732-149">Om den inte finns där läggs den inte till.</span><span class="sxs-lookup"><span data-stu-id="52732-149">If it's not there, it won't be added.</span></span>
  
1.  <span data-ttu-id="52732-150">Anslut PowerShell till din Exchange Online organisation.</span><span class="sxs-lookup"><span data-stu-id="52732-150">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="52732-151">Stegvisa instruktioner finns i Skapa [Anslut-Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="52732-151">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="52732-152">Gå till skrivbordsmappen där du sparade CSV-filen i steg 1. till exempel `C:\Users\Administrator\desktop` .</span><span class="sxs-lookup"><span data-stu-id="52732-152">Go to the desktop folder where you saved the CSV file in Step 1; for example, `C:\Users\Administrator\desktop`.</span></span>
    
3. <span data-ttu-id="52732-153">Kör följande två kommandon för att lägga till de andra egenskaperna från CSV-filen i de externa kontakter som du skapade i steg 2.</span><span class="sxs-lookup"><span data-stu-id="52732-153">Run the following two commands to add the other properties from the CSV file to the external contacts that you created in Step 2.</span></span>
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > <span data-ttu-id="52732-154">Parametern  _Manager_ kan vara problematiskt.</span><span class="sxs-lookup"><span data-stu-id="52732-154">The  _Manager_ parameter might be problematic.</span></span> <span data-ttu-id="52732-155">Om cellen är tom i CSV-filen får du ett felmeddelande och ingen egenskapsinformation läggs till för kontakten.</span><span class="sxs-lookup"><span data-stu-id="52732-155">If the cell is blank in the CSV file, you will get an error and none of the property information will be added to the contact.</span></span> <span data-ttu-id="52732-156">Om du inte behöver ange en chef tar du bara bort från  ` -Manager $_.Manager ` det tidigare PowerShell-kommandot.</span><span class="sxs-lookup"><span data-stu-id="52732-156">If you don't need to specify a manager, then just delete  ` -Manager $_.Manager ` from the previous PowerShell command.</span></span> 
  
    <span data-ttu-id="52732-157">Det kan ta en stund att uppdatera kontakterna, beroende på hur många du importerade i steg 1.</span><span class="sxs-lookup"><span data-stu-id="52732-157">Again, it might take a while to update the contacts, depending on how many you imported in Step 1.</span></span> 
    
4. <span data-ttu-id="52732-158">Så här kontrollerar du att egenskaperna har lagts till i kontakterna:</span><span class="sxs-lookup"><span data-stu-id="52732-158">To verify that the properties were added to the contacts:</span></span> 
    
1. <span data-ttu-id="52732-159">Gå till Mottagare i **EAC.** \> </span><span class="sxs-lookup"><span data-stu-id="52732-159">In the EAC, go to **Recipients** \> **Contacts**.</span></span>
    
2. <span data-ttu-id="52732-160">Klicka på en kontakt och **klicka sedan** på ![ Redigera ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) redigera-ikonen för att visa kontaktens egenskaper.</span><span class="sxs-lookup"><span data-stu-id="52732-160">Click a contact and then click **Edit** ![Edit icon](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) to display the contact's properties.</span></span> 
    
<span data-ttu-id="52732-161">Nu är det allt!</span><span class="sxs-lookup"><span data-stu-id="52732-161">That's it!</span></span> <span data-ttu-id="52732-162">Användarna kan se kontakterna och den ytterligare informationen i adressboken när Outlook och Outlook på webben.</span><span class="sxs-lookup"><span data-stu-id="52732-162">Users can see the contacts and the additional information in the address book Outlook and Outlook on the web.</span></span>
  
## <a name="add-more-external-contacts"></a><span data-ttu-id="52732-163">Lägga till fler externa kontakter</span><span class="sxs-lookup"><span data-stu-id="52732-163">Add more external contacts</span></span>

<span data-ttu-id="52732-164">Du kan upprepa steg 1 till steg 3 för att lägga till nya externa kontakter i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="52732-164">You can repeat Steps 1 through Step 3 to add new external contacts in Exchange Online.</span></span> <span data-ttu-id="52732-165">Du eller användarna i företaget kan helt enkelt lägga till en ny rad i CSV-filen för den nya kontakten.</span><span class="sxs-lookup"><span data-stu-id="52732-165">You or users in your company can just add a new row in the CSV file for the new contact.</span></span> <span data-ttu-id="52732-166">Sedan kan du köra PowerShell-kommandona från steg 2 och steg 3 för att skapa och lägga till information i de nya kontakterna.</span><span class="sxs-lookup"><span data-stu-id="52732-166">Then you can run the PowerShell commands from Step 2 and Step 3 to create and add information to the new contacts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="52732-167">När du kör kommandot för att skapa nya kontakter kan du få ett felmeddelande om att de kontakter som skapades tidigare redan finns.</span><span class="sxs-lookup"><span data-stu-id="52732-167">When you run the command to create new contacts, you might get an error saying that the contacts that were created earlier already exist.</span></span> <span data-ttu-id="52732-168">Men alla nya kontakter som läggs till i CSV-filen skapas.</span><span class="sxs-lookup"><span data-stu-id="52732-168">But any new contact added to the CSV file is created.</span></span> 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a><span data-ttu-id="52732-169">Dölja externa kontakter från den delade adressboken></span><span class="sxs-lookup"><span data-stu-id="52732-169">Hide external contacts from the shared address book></span></span>

<span data-ttu-id="52732-170">Vissa företag kanske bara använder externa kontakter så att de kan läggas till som medlemmar i distributionsgrupper.</span><span class="sxs-lookup"><span data-stu-id="52732-170">Some companies may use external contacts only so they can be added as members of distribution groups.</span></span> <span data-ttu-id="52732-171">I det här scenariot vill de kanske dölja externa kontakter i den delade adressboken.</span><span class="sxs-lookup"><span data-stu-id="52732-171">In this scenario, they may want to hide external contacts from the shared address book.</span></span> <span data-ttu-id="52732-172">Så här gör du:</span><span class="sxs-lookup"><span data-stu-id="52732-172">Here's how:</span></span>
  
1.  <span data-ttu-id="52732-173">Anslut PowerShell till din Exchange Online organisation.</span><span class="sxs-lookup"><span data-stu-id="52732-173">Connect PowerShell to your Exchange Online organization.</span></span> <span data-ttu-id="52732-174">Stegvisa instruktioner finns i Skapa [Anslut-Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="52732-174">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="52732-175">Om du vill dölja en enskild extern kontakt kör du följande kommando.</span><span class="sxs-lookup"><span data-stu-id="52732-175">To hide a single external contact, run the following command.</span></span>
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    <span data-ttu-id="52732-176">Om du till exempel vill dölja Pilar Pinilla från den delade adressboken kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="52732-176">For example, to hide Pilar Pinilla from the shared address book, run this command:</span></span>

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. <span data-ttu-id="52732-177">Om du vill dölja alla externa kontakter från den delade adressboken kör du det här kommandot:</span><span class="sxs-lookup"><span data-stu-id="52732-177">To hide all external contacts from the shared address book, run this command:</span></span>

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

<span data-ttu-id="52732-178">När du har döljt dem visas inte externa kontakter i den delade adressboken, men du kan fortfarande lägga till dem som medlemmar i en distributionsgrupp.</span><span class="sxs-lookup"><span data-stu-id="52732-178">After you hide them, external contacts aren't displayed in the shared address book, but you can still add them as members of a distribution group.</span></span>