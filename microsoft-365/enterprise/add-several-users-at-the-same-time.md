---
title: Lägga till flera användare samtidigt i Microsoft 365 – hjälp för administratörer
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_AddUsersCSV
- O365M_AddUsersCSV
- O365E_AddUsersCSV
search.appverid:
- MET150
- MOP150
- MOE150
- MED150
- GMA150
- MBS150
- GEA150
- BCS160
description: 'Lär dig hur du lägger till flera användare i Microsoft 365 för företag från en lista i ett kalkylblad eller en annan CSV-formaterad fil. Här finns en video på YouTube som visar hur du lägger till konton i Microsoft 365. När det är gjort har varje användare som har ett konto fått en Microsoft 365-postlåda. '
ms.openlocfilehash: 6b3e8d885466e44a4aa23427a54cfc98b2eebdf3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905626"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a><span data-ttu-id="0052f-105">Lägga till flera användare samtidigt i Microsoft 365 – hjälp för administratörer</span><span class="sxs-lookup"><span data-stu-id="0052f-105">Add several users at the same time to Microsoft 365 - Admin Help</span></span>

<span data-ttu-id="0052f-106">Alla i din grupp behöver ett användarkonto innan de kan logga in och komma åt Microsoft 365-tjänsterna, till exempel e-post och Office.</span><span class="sxs-lookup"><span data-stu-id="0052f-106">Each person on your team needs a user account before they can sign in and access Microsoft 365 services, such as email and Office.</span></span> <span data-ttu-id="0052f-107">Om du har många personer kan du lägga till deras konton samtidigt från ett Excel-kalkylblad eller en annan fil som sparats i CSV-format.</span><span class="sxs-lookup"><span data-stu-id="0052f-107">If you have a lot of people, you can add their accounts all at once from an Excel spreadsheet or other file saved in CSV format.</span></span> <span data-ttu-id="0052f-108">[Vet du inte vad CSV-formatet är?](add-several-users-at-the-same-time.md#not-sure-what-csv-format-is)</span><span class="sxs-lookup"><span data-stu-id="0052f-108">[Not sure what CSV format is](add-several-users-at-the-same-time.md#not-sure-what-csv-format-is)?</span></span>
  
> [!NOTE]
> <span data-ttu-id="0052f-109">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="0052f-109">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a><span data-ttu-id="0052f-110">Lägga till flera användare i administrationscentret för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0052f-110">Add multiple users in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="0052f-111">Logga in på Microsoft 365 med ditt arbets- eller skolkonto.</span><span class="sxs-lookup"><span data-stu-id="0052f-111">Sign in to Microsoft 365 with your work or school account.</span></span>

2. <span data-ttu-id="0052f-112">I administrationscentret väljer du **Användare** \> **aktiva användare.**</span><span class="sxs-lookup"><span data-stu-id="0052f-112">In the admin center, choose **Users** \> **Active users**.</span></span>

3. <span data-ttu-id="0052f-113">Välj **Lägg till flera användare.**</span><span class="sxs-lookup"><span data-stu-id="0052f-113">Select **Add multiple users**.</span></span>

4. <span data-ttu-id="0052f-114">På panelen **Importera flera användare** kan du ladda ned en CSV-exempelfil med eller utan ifyllda exempeldata.</span><span class="sxs-lookup"><span data-stu-id="0052f-114">On the **Import multiple users** panel, you can optionally download a sample CSV file with or without sample data filled in.</span></span>

    <span data-ttu-id="0052f-115">Kalkylbladet måste innehålla exakt **samma kolumnrubriker** som exempelrubriken (Användarnamn, Förnamn och så vidare).</span><span class="sxs-lookup"><span data-stu-id="0052f-115">Your spreadsheet needs to include the **exact same column headings** as the sample one (User Name, First Name, and so on).</span></span> <span data-ttu-id="0052f-116">Om du använder mallen kan du öppna den i ett textredigeringsverktyg, till exempel Anteckningar, och låta alla data på rad 1 vara och bara ange data i rad 2 och nedanför.</span><span class="sxs-lookup"><span data-stu-id="0052f-116">If you use the template, open it in a text editing tool, like Notepad, and consider leaving all the data in row 1 alone, and only entering data in rows 2 and below.</span></span>

    <span data-ttu-id="0052f-117">Kalkylbladet måste också innehålla värden för användarnamn (t.ex. jens@contoso.com) och ett visningsnamn (t.ex. Jens Persson) för varje användare.</span><span class="sxs-lookup"><span data-stu-id="0052f-117">Your spreadsheet also needs to include values for the user name (like bob@contoso.com) and a display name (like Bob Kelly) for each user.</span></span>

  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Fax,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. <span data-ttu-id="0052f-118">Ange en filsökväg i rutan eller välj **Bläddra** för att bläddra till CSV-filens plats. Välj sedan **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="0052f-118">Enter a file path into the box, or choose **Browse** to browse to the CSV file location, then choose **Verify**.</span></span>
  
    <span data-ttu-id="0052f-p104">Om det finns problem med filen visas de problemen i panelen. Du kan också ladda ned en loggfil.</span><span class="sxs-lookup"><span data-stu-id="0052f-p104">If there are problems with the file, the problem is displayed in the panel. You can also download a log file.</span></span>

6. <span data-ttu-id="0052f-121">I dialogrutan **Ange användaralternativ** kan du ange inloggningsstatus och välja den produktlicens som tilldelas till alla användare.</span><span class="sxs-lookup"><span data-stu-id="0052f-121">On the **Set user options** dialog you can set the sign-in status and choose the product license that will be assigned to all users.</span></span>

7. <span data-ttu-id="0052f-122">I dialogrutan **Visa resultat** kan du välja att skicka resultaten till dig själv eller till andra användare (lösenord anges i oformaterad text) och du kan se hur många användare som har skapats och om du måste köpa fler licenser att tilldela till några av de nya användarna.</span><span class="sxs-lookup"><span data-stu-id="0052f-122">On the **View your result** dialog you can choose to send the results to either yourself or other users (passwords will be in plain text) and you can see how many users were created, and if you need to purchase more licenses to assign to some of the new users.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0052f-123">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="0052f-123">Next steps</span></span>

- <span data-ttu-id="0052f-124">Nu när de här personerna har konton måste de ladda ned och installera eller ominstallera [Microsoft 365 eller Office 2016 på en PC eller Mac.](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658)</span><span class="sxs-lookup"><span data-stu-id="0052f-124">Now that these people have accounts, they need to [Download and install or reinstall Microsoft 365 or Office 2016 on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> <span data-ttu-id="0052f-125">Varje person i din grupp kan installera Microsoft 365 på upp till fem PC- eller Mac-datorer.</span><span class="sxs-lookup"><span data-stu-id="0052f-125">Each person on your team can install Microsoft 365 on up to 5 PCs or Macs.</span></span>

- <span data-ttu-id="0052f-126">Varje person kan också konfigurera [Office-program](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) och e-post på en mobil enhet på upp till fem surfplattor och fem telefoner, till exempel iPhone, iPad och telefoner och surfplattor med Android.</span><span class="sxs-lookup"><span data-stu-id="0052f-126">Each person can also [Set up Office apps and email on a mobile device](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) on up to 5 tablets and 5 phones, such as iPhones, iPads, and Android phones and tablets.</span></span> <span data-ttu-id="0052f-127">Tack vare det här kan de redigera Office-filer var de än befinner sig.</span><span class="sxs-lookup"><span data-stu-id="0052f-127">This way they can edit Office files from anywhere.</span></span>

    <span data-ttu-id="0052f-128">Se [Konfigurera Microsoft 365 för företag](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) för en fullständig lista över konfigurationsstegen.</span><span class="sxs-lookup"><span data-stu-id="0052f-128">See [Set up Microsoft 365 for business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) for an end-to-end list of the setup steps.</span></span>

## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a><span data-ttu-id="0052f-129">Mer information om hur du lägger till användare i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0052f-129">More information about how to add users to Microsoft 365</span></span>

### <a name="not-sure-what-csv-format-is"></a><span data-ttu-id="0052f-130">Är du osäker på vad CSV-formatet är?</span><span class="sxs-lookup"><span data-stu-id="0052f-130">Not sure what CSV format is?</span></span>

<span data-ttu-id="0052f-p107">En CSV-fil är en fil med kommaavgränsade värden. Du kan skapa eller redigera en sådan fil med en textredigerare eller med ett kalkylprogram, t.ex. Excel.</span><span class="sxs-lookup"><span data-stu-id="0052f-p107">A CSV file is a file with comma separated values. You can create or edit a file like this with any text editor or spreadsheet program, such as Excel.</span></span>
  
<span data-ttu-id="0052f-133">Du kan ladda ned [det här exempelkalkylbladet](https://www.microsoft.com/download/details.aspx?id=45485) som en startpunkt.</span><span class="sxs-lookup"><span data-stu-id="0052f-133">You can download [this sample spreadsheet](https://www.microsoft.com/download/details.aspx?id=45485) as a starting point.</span></span> <span data-ttu-id="0052f-134">Kom ihåg att det krävs kolumnrubriker på första raden i Microsoft 365 så att du inte ersätter dem med något annat.</span><span class="sxs-lookup"><span data-stu-id="0052f-134">Remember that Microsoft 365 requires column headings in the first row so don't replace them with something else.</span></span> 
  
<span data-ttu-id="0052f-135">Spara filen med ett nytt namn och ange CSV-format.</span><span class="sxs-lookup"><span data-stu-id="0052f-135">Save the file with a new name, and specify CSV format.</span></span>
  
![En bild om hur du sparar en fil i Excel i CSV-format](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
<span data-ttu-id="0052f-p109">När du sparar filen visas antagligen ett meddelande om att vissa funktioner i arbetsboken kan gå förlorade om du sparar filen i CSV-format. Det är OK. Klicka på **Ja** för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="0052f-p109">When you save the file, you'll probably get a prompt that some features in your workbook will be lost if you save the file in CSV format. This is okay. Click **Yes** to continue.</span></span>
  
![En bild av frågan som du eventuellt får i Excel och som frågar om du verkligen vill spara filen i CSV-format](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a><span data-ttu-id="0052f-141">Tips på hur du formaterar kalkylbladet</span><span class="sxs-lookup"><span data-stu-id="0052f-141">Tips for formatting your spreadsheet</span></span>

- <span data-ttu-id="0052f-142">**Behöver jag samma kolumnrubriker som i exempelkalkylbladet?**</span><span class="sxs-lookup"><span data-stu-id="0052f-142">**Do I need the same column headings as in the sample spreadsheet?**</span></span> <span data-ttu-id="0052f-143">Ja.</span><span class="sxs-lookup"><span data-stu-id="0052f-143">Yes.</span></span> <span data-ttu-id="0052f-144">Exempelkalkylbladet innehåller kolumnrubriker på första raden.</span><span class="sxs-lookup"><span data-stu-id="0052f-144">The sample spreadsheet contains column headings in the first row.</span></span> <span data-ttu-id="0052f-145">De här rubrikerna är obligatoriska.</span><span class="sxs-lookup"><span data-stu-id="0052f-145">These headings are required.</span></span> <span data-ttu-id="0052f-146">För varje användare som du vill lägga till i Microsoft 365 skapar du en rad under rubriken.</span><span class="sxs-lookup"><span data-stu-id="0052f-146">For each user you want to add to Microsoft 365, create a row under the heading.</span></span> <span data-ttu-id="0052f-147">Om du lägger till, ändrar eller tar bort någon kolumnrubrik kanske Microsoft 365 inte kan skapa användare utifrån informationen i filen.</span><span class="sxs-lookup"><span data-stu-id="0052f-147">If you add, change, or delete any of the column headings, Microsoft 365 might not be able to create users from the information in the file.</span></span>

- <span data-ttu-id="0052f-p111">**Vad gör jag om jag inte har all information som behövs om en användare?** Fälten Användarnamn och Visningsnamn är obligatoriska, och du kan inte lägga till en ny användare om du inte har de uppgifterna. Om du saknar någon annan uppgift, till exempel faxnummer, kan du lägga in ett blanksteg och ett kommatecken för att visa att fältet ska vara tomt.</span><span class="sxs-lookup"><span data-stu-id="0052f-p111">**What if I don't have all the information required for each user?** The user name and display name are required, and you cannot add a new user without this information. If you don't have some of the other information, such as the fax, you can use a space plus a comma to indicate that the field should remain blank.</span></span>

- <span data-ttu-id="0052f-151">**Hur litet eller stort får kalkylbladet vara?**</span><span class="sxs-lookup"><span data-stu-id="0052f-151">**How small or large can the spreadsheet be?**</span></span> <span data-ttu-id="0052f-152">Kalkylbladet måste innehålla minst två rader.</span><span class="sxs-lookup"><span data-stu-id="0052f-152">The spreadsheet must have at least two rows.</span></span> <span data-ttu-id="0052f-153">One is for the column headings (the user data column label) and one for the user.</span><span class="sxs-lookup"><span data-stu-id="0052f-153">One is for the column headings (the user data column label) and one for the user.</span></span> <span data-ttu-id="0052f-154">You cannot have more than 251 rows.</span><span class="sxs-lookup"><span data-stu-id="0052f-154">You cannot have more than 251 rows.</span></span> <span data-ttu-id="0052f-155">If you need to import more than 250 users, you can create more than one spreadsheet.</span><span class="sxs-lookup"><span data-stu-id="0052f-155">If you need to import more than 250 users, you can create more than one spreadsheet.</span></span>

- <span data-ttu-id="0052f-156">**Vilka språk kan jag använda?**</span><span class="sxs-lookup"><span data-stu-id="0052f-156">**What languages can I use?**</span></span> <span data-ttu-id="0052f-157">När du skapar kalkylbladet kan du ange kolumnetiketter för användardata på alla språk och tecken, men du får inte ändra ordningen på etiketterna, som visas i exemplet.</span><span class="sxs-lookup"><span data-stu-id="0052f-157">When you create your spreadsheet, you can enter user data column labels in any language or characters, but you must not change the order of the labels, as shown in the sample.</span></span> <span data-ttu-id="0052f-158">Sedan kan du lägga in data i fälten, på vilket språk och med vilka tecken som helst, och spara filen i Unicode- eller UTF-8-format.</span><span class="sxs-lookup"><span data-stu-id="0052f-158">You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.</span></span>

- <span data-ttu-id="0052f-p114">**Vad gäller om jag lägger till användare från andra länder och regioner?** Skapa ett separat kalkylblad för varje område. Du måste gå igenom guiden Lägg till användare i grupp för varje kalkylblad, och då ange en enda plats för alla användare som ingår i den fil du arbetar med.</span><span class="sxs-lookup"><span data-stu-id="0052f-p114">**What if I'm adding users from different countries or regions?** Create a separate spreadsheet for each area. You'll need to step through the Bulk add users wizard which each spreadsheet, giving a single location of all users included in the file that you're working with.</span></span>

- <span data-ttu-id="0052f-p115">**Finns det någon begränsning för hur många tecken jag kan använda?** I följande tabell visas kolumnetiketter för användardata med motsvarande maximalt antal tecken i exempelkalkylbladet.</span><span class="sxs-lookup"><span data-stu-id="0052f-p115">**Is there a limit to the number of characters I can use?** The following table shows the user data column labels and the maximum character length for each in the sample spreadsheet.</span></span>

|<span data-ttu-id="0052f-164">**Kolumnetikett med användardata**</span><span class="sxs-lookup"><span data-stu-id="0052f-164">**User data column label**</span></span>|<span data-ttu-id="0052f-165">**Maximalt antal tecken**</span><span class="sxs-lookup"><span data-stu-id="0052f-165">**Maximum character length**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0052f-166">Användarnamn (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="0052f-166">User Name (Required)</span></span>  <br/> |<span data-ttu-id="0052f-167">79 inklusive at-tecknet (@), i det format som name@domain. \<extension\> .</span><span class="sxs-lookup"><span data-stu-id="0052f-167">79 including the at sign (@), in the format name@domain.\<extension\>.</span></span> <span data-ttu-id="0052f-168">Användarens alias får inte vara längre än 50 tecken och domännamn får inte vara längre än 48 tecken.</span><span class="sxs-lookup"><span data-stu-id="0052f-168">The user's alias cannot exceed 50 characters, and the domain name cannot exceed 48 characters.</span></span>  <br/> |
|<span data-ttu-id="0052f-169">Förnamn</span><span class="sxs-lookup"><span data-stu-id="0052f-169">First Name</span></span>  <br/> |<span data-ttu-id="0052f-170">64</span><span class="sxs-lookup"><span data-stu-id="0052f-170">64</span></span>  <br/> |
|<span data-ttu-id="0052f-171">Efternamn</span><span class="sxs-lookup"><span data-stu-id="0052f-171">Last Name</span></span>  <br/> |<span data-ttu-id="0052f-172">64</span><span class="sxs-lookup"><span data-stu-id="0052f-172">64</span></span>  <br/> |
|<span data-ttu-id="0052f-173">Visningsnamn (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="0052f-173">Display Name (required)</span></span>  <br/> |<span data-ttu-id="0052f-174">256</span><span class="sxs-lookup"><span data-stu-id="0052f-174">256</span></span>  <br/> |
|<span data-ttu-id="0052f-175">Befattning</span><span class="sxs-lookup"><span data-stu-id="0052f-175">Job Title</span></span>  <br/> |<span data-ttu-id="0052f-176">64</span><span class="sxs-lookup"><span data-stu-id="0052f-176">64</span></span>  <br/> |
|<span data-ttu-id="0052f-177">Avdelning</span><span class="sxs-lookup"><span data-stu-id="0052f-177">Department</span></span>  <br/> |<span data-ttu-id="0052f-178">64</span><span class="sxs-lookup"><span data-stu-id="0052f-178">64</span></span>  <br/> |
|<span data-ttu-id="0052f-179">Kontorsnummer</span><span class="sxs-lookup"><span data-stu-id="0052f-179">Office Number</span></span>  <br/> |<span data-ttu-id="0052f-180">128</span><span class="sxs-lookup"><span data-stu-id="0052f-180">128</span></span>  <br/> |
|<span data-ttu-id="0052f-181">Telefonnr till arbetet</span><span class="sxs-lookup"><span data-stu-id="0052f-181">Office Phone</span></span>  <br/> |<span data-ttu-id="0052f-182">64</span><span class="sxs-lookup"><span data-stu-id="0052f-182">64</span></span>  <br/> |
|<span data-ttu-id="0052f-183">Mobiltelefon</span><span class="sxs-lookup"><span data-stu-id="0052f-183">Mobile Phone</span></span>  <br/> |<span data-ttu-id="0052f-184">64</span><span class="sxs-lookup"><span data-stu-id="0052f-184">64</span></span>  <br/> |
|<span data-ttu-id="0052f-185">Fax</span><span class="sxs-lookup"><span data-stu-id="0052f-185">Fax</span></span>  <br/> |<span data-ttu-id="0052f-186">64</span><span class="sxs-lookup"><span data-stu-id="0052f-186">64</span></span>  <br/> |
|<span data-ttu-id="0052f-187">Adress</span><span class="sxs-lookup"><span data-stu-id="0052f-187">Address</span></span>  <br/> |<span data-ttu-id="0052f-188">1023</span><span class="sxs-lookup"><span data-stu-id="0052f-188">1023</span></span>  <br/> |
|<span data-ttu-id="0052f-189">Ort</span><span class="sxs-lookup"><span data-stu-id="0052f-189">City</span></span>  <br/> |<span data-ttu-id="0052f-190">128</span><span class="sxs-lookup"><span data-stu-id="0052f-190">128</span></span>  <br/> |
|<span data-ttu-id="0052f-191">Region</span><span class="sxs-lookup"><span data-stu-id="0052f-191">State or Province</span></span>  <br/> |<span data-ttu-id="0052f-192">128</span><span class="sxs-lookup"><span data-stu-id="0052f-192">128</span></span>  <br/> |
|<span data-ttu-id="0052f-193">Postnummer</span><span class="sxs-lookup"><span data-stu-id="0052f-193">ZIP or Postal Code</span></span>  <br/> |<span data-ttu-id="0052f-194">40</span><span class="sxs-lookup"><span data-stu-id="0052f-194">40</span></span>  <br/> |
|<span data-ttu-id="0052f-195">Land eller region</span><span class="sxs-lookup"><span data-stu-id="0052f-195">Country or Region</span></span>  <br/> |<span data-ttu-id="0052f-196">128</span><span class="sxs-lookup"><span data-stu-id="0052f-196">128</span></span>  <br/> |

### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a><span data-ttu-id="0052f-197">Har du fortfarande problem med att lägga till användare i Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="0052f-197">Still having problems when adding users to Microsoft 365?</span></span>

- <span data-ttu-id="0052f-p117">**Kontrollera en extra gång att kalkylbladet är rätt formaterat.** Kontrollera kolumnrubrikerna och se till att de överensstämmer med rubrikerna i exempelfilen. Se till att du följer reglerna om maximalt antal tecken och att varje fält avgränsas med ett komma.</span><span class="sxs-lookup"><span data-stu-id="0052f-p117">**Double-check that the spreadsheet is formatted correctly.** Check the column headings to make sure they match the headings in the sample file. Make sure you're following the rules for character lengths and that each field is separated by a comma.</span></span>

- <span data-ttu-id="0052f-201">**Vänta några minuter om du inte ser de nya användarna i Microsoft 365 på en gång.**</span><span class="sxs-lookup"><span data-stu-id="0052f-201">**If you don't see the new users in Microsoft 365 right away, wait a few minutes.**</span></span> <span data-ttu-id="0052f-202">Det kan ta en stund innan ändringarna har gjorts i alla tjänster i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0052f-202">It can take a little while for changes to go across all the services in Microsoft 365.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="0052f-203">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="0052f-203">Related articles</span></span>

[<span data-ttu-id="0052f-204">Lägga till användare individuellt eller flera samtidigt i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0052f-204">Add users individually or in bulk to Microsoft 365</span></span>](/office365/admin/add-users/add-users)