---
title: Lägga till flera användare samtidigt i Microsoft 365 – administratörshjälp
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
description: 'Lär dig hur du lägger till flera användare i Microsoft 365 för företag med hjälp av en lista i ett kalkylblad eller en annan CSV-formaterad fil. Här finns en video på YouTube som visar hur du lägger till konton Microsoft 365. I slutet av den här processen kommer varje användare med ett konto att ha en Microsoft 365 postlåda. '
ms.openlocfilehash: 6b3e8d885466e44a4aa23427a54cfc98b2eebdf3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905626"
---
# <a name="add-several-users-at-the-same-time-to-microsoft-365---admin-help"></a><span data-ttu-id="ae85e-105">Lägga till flera användare samtidigt i Microsoft 365 – administratörshjälp</span><span class="sxs-lookup"><span data-stu-id="ae85e-105">Add several users at the same time to Microsoft 365 - Admin Help</span></span>

<span data-ttu-id="ae85e-106">Alla i din grupp behöver ett användarkonto innan de kan logga in och komma åt Microsoft 365 tjänster, till exempel e-Office.</span><span class="sxs-lookup"><span data-stu-id="ae85e-106">Each person on your team needs a user account before they can sign in and access Microsoft 365 services, such as email and Office.</span></span> <span data-ttu-id="ae85e-107">Om du har många personer kan du lägga till deras konton samtidigt från ett kalkylblad Excel någon annan fil som sparats i CSV-format.</span><span class="sxs-lookup"><span data-stu-id="ae85e-107">If you have a lot of people, you can add their accounts all at once from an Excel spreadsheet or other file saved in CSV format.</span></span> <span data-ttu-id="ae85e-108">[Vet du inte vad CSV-formatet är?](add-several-users-at-the-same-time.md#not-sure-what-csv-format-is)</span><span class="sxs-lookup"><span data-stu-id="ae85e-108">[Not sure what CSV format is](add-several-users-at-the-same-time.md#not-sure-what-csv-format-is)?</span></span>
  
> [!NOTE]
> <span data-ttu-id="ae85e-109">Om du inte använder det nya administrationscentret för Microsoft 365 kan du aktivera det genom att välja **Prova det nya administrationscentret** längst upp på startsidan.</span><span class="sxs-lookup"><span data-stu-id="ae85e-109">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="add-multiple-users-in-the-microsoft-365-admin-center"></a><span data-ttu-id="ae85e-110">Lägga till flera användare Microsoft 365 administrationscentret</span><span class="sxs-lookup"><span data-stu-id="ae85e-110">Add multiple users in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="ae85e-111">Logga in på Microsoft 365 med ditt arbets- eller skolkonto.</span><span class="sxs-lookup"><span data-stu-id="ae85e-111">Sign in to Microsoft 365 with your work or school account.</span></span>

2. <span data-ttu-id="ae85e-112">I administrationscentret väljer du **Användare** \> **aktiva användare.**</span><span class="sxs-lookup"><span data-stu-id="ae85e-112">In the admin center, choose **Users** \> **Active users**.</span></span>

3. <span data-ttu-id="ae85e-113">Välj **Lägg till flera användare.**</span><span class="sxs-lookup"><span data-stu-id="ae85e-113">Select **Add multiple users**.</span></span>

4. <span data-ttu-id="ae85e-114">På panelen **Importera flera användare** kan du ladda ned en CSV-exempelfil med eller utan ifyllda exempeldata.</span><span class="sxs-lookup"><span data-stu-id="ae85e-114">On the **Import multiple users** panel, you can optionally download a sample CSV file with or without sample data filled in.</span></span>

    <span data-ttu-id="ae85e-115">Kalkylbladet måste innehålla exakt **samma kolumnrubriker** som exempelrubriken (Användarnamn, Förnamn och så vidare).</span><span class="sxs-lookup"><span data-stu-id="ae85e-115">Your spreadsheet needs to include the **exact same column headings** as the sample one (User Name, First Name, and so on).</span></span> <span data-ttu-id="ae85e-116">Om du använder mallen öppnar du den i ett textredigeringsverktyg, till exempel Anteckningar, och överväg att låta alla data på rad 1 vara och bara ange data i rad 2 och nedan.</span><span class="sxs-lookup"><span data-stu-id="ae85e-116">If you use the template, open it in a text editing tool, like Notepad, and consider leaving all the data in row 1 alone, and only entering data in rows 2 and below.</span></span>

    <span data-ttu-id="ae85e-117">Kalkylbladet måste också innehålla värden för användarnamn (t.ex. jens@contoso.com) och ett visningsnamn (t.ex. Jens Persson) för varje användare.</span><span class="sxs-lookup"><span data-stu-id="ae85e-117">Your spreadsheet also needs to include values for the user name (like bob@contoso.com) and a display name (like Bob Kelly) for each user.</span></span>

  ```
  User Name,First Name,Last Name,Display Name,Job Title,Department,Office Number,Office Phone,Mobile Phone,Fax,Address,City,State or Province,ZIP or Postal Code,Country or Region
  chris@contoso.com,Chris,Green,Chris Green,IT Manager,Information Technology,123451,123-555-1211,123-555-6641,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  ben@contoso.com,Ben,Andrews,Ben Andrews,IT Manager,Information Technology,123452,123-555-1212,123-555-6642,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  david@contoso.com,David,Longmuir,David Longmuir,IT Manager,Information Technology,123453,123-555-1213,123-555-6643,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  cynthia@contoso.com,Cynthia,Carey,Cynthia Carey,IT Manager,Information Technology,123454,123-555-1214,123-555-6644,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  melissa@contoso.com,Melissa,MacBeth,Melissa MacBeth,IT Manager,Information Technology,123455,123-555-1215,123-555-6645,123-555-6700,1 Microsoft way,Redmond,Wa,98052,United States
  
  ```

5. <span data-ttu-id="ae85e-118">Ange en filsökväg i rutan eller välj **Bläddra** för att bläddra till CSV-filens plats. Välj sedan **Verifiera**.</span><span class="sxs-lookup"><span data-stu-id="ae85e-118">Enter a file path into the box, or choose **Browse** to browse to the CSV file location, then choose **Verify**.</span></span>
  
    <span data-ttu-id="ae85e-p104">Om det finns problem med filen visas de problemen i panelen. Du kan också ladda ned en loggfil.</span><span class="sxs-lookup"><span data-stu-id="ae85e-p104">If there are problems with the file, the problem is displayed in the panel. You can also download a log file.</span></span>

6. <span data-ttu-id="ae85e-121">I dialogrutan **Ange användaralternativ** kan du ange inloggningsstatus och välja den produktlicens som tilldelas till alla användare.</span><span class="sxs-lookup"><span data-stu-id="ae85e-121">On the **Set user options** dialog you can set the sign-in status and choose the product license that will be assigned to all users.</span></span>

7. <span data-ttu-id="ae85e-122">I dialogrutan **Visa resultat** kan du välja att skicka resultaten till dig själv eller till andra användare (lösenord anges i oformaterad text) och du kan se hur många användare som har skapats och om du måste köpa fler licenser att tilldela till några av de nya användarna.</span><span class="sxs-lookup"><span data-stu-id="ae85e-122">On the **View your result** dialog you can choose to send the results to either yourself or other users (passwords will be in plain text) and you can see how many users were created, and if you need to purchase more licenses to assign to some of the new users.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ae85e-123">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="ae85e-123">Next steps</span></span>

- <span data-ttu-id="ae85e-124">Nu när de här personerna har konton måste de ladda ned och installera eller installera om [Microsoft 365 eller Office 2016 på en PC eller Mac.](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658)</span><span class="sxs-lookup"><span data-stu-id="ae85e-124">Now that these people have accounts, they need to [Download and install or reinstall Microsoft 365 or Office 2016 on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658).</span></span> <span data-ttu-id="ae85e-125">Varje person i din grupp kan installera Microsoft 365 på upp till fem PC- eller Mac-datorer.</span><span class="sxs-lookup"><span data-stu-id="ae85e-125">Each person on your team can install Microsoft 365 on up to 5 PCs or Macs.</span></span>

- <span data-ttu-id="ae85e-126">Varje person kan också konfigurera [Office-appar](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) och e-post på en mobil enhet på upp till fem surfplattor och fem telefoner, till exempel iPhone, iPad och telefoner och surfplattor med Android.</span><span class="sxs-lookup"><span data-stu-id="ae85e-126">Each person can also [Set up Office apps and email on a mobile device](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f) on up to 5 tablets and 5 phones, such as iPhones, iPads, and Android phones and tablets.</span></span> <span data-ttu-id="ae85e-127">Tack vare det här kan de redigera Office-filer var de än befinner sig.</span><span class="sxs-lookup"><span data-stu-id="ae85e-127">This way they can edit Office files from anywhere.</span></span>

    <span data-ttu-id="ae85e-128">Se [Konfigurera Microsoft 365 för företag](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) för en fullständig lista över konfigurationsstegen.</span><span class="sxs-lookup"><span data-stu-id="ae85e-128">See [Set up Microsoft 365 for business](https://support.office.com/article/6a3a29a0-e616-4713-99d1-15eda62d04fa) for an end-to-end list of the setup steps.</span></span>

## <a name="more-information-about-how-to-add-users-to-microsoft-365"></a><span data-ttu-id="ae85e-129">Mer information om hur du lägger till användare i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ae85e-129">More information about how to add users to Microsoft 365</span></span>

### <a name="not-sure-what-csv-format-is"></a><span data-ttu-id="ae85e-130">Är du osäker på vad CSV-formatet är?</span><span class="sxs-lookup"><span data-stu-id="ae85e-130">Not sure what CSV format is?</span></span>

<span data-ttu-id="ae85e-p107">En CSV-fil är en fil med kommaavgränsade värden. Du kan skapa eller redigera en sådan fil med en textredigerare eller med ett kalkylprogram, t.ex. Excel.</span><span class="sxs-lookup"><span data-stu-id="ae85e-p107">A CSV file is a file with comma separated values. You can create or edit a file like this with any text editor or spreadsheet program, such as Excel.</span></span>
  
<span data-ttu-id="ae85e-133">Du kan ladda ned [det här exempelkalkylbladet](https://www.microsoft.com/download/details.aspx?id=45485) som en startpunkt.</span><span class="sxs-lookup"><span data-stu-id="ae85e-133">You can download [this sample spreadsheet](https://www.microsoft.com/download/details.aspx?id=45485) as a starting point.</span></span> <span data-ttu-id="ae85e-134">Kom ihåg Microsoft 365 behöver kolumnrubriker på den första raden så att du inte ersätter dem med något annat.</span><span class="sxs-lookup"><span data-stu-id="ae85e-134">Remember that Microsoft 365 requires column headings in the first row so don't replace them with something else.</span></span> 
  
<span data-ttu-id="ae85e-135">Spara filen med ett nytt namn och ange CSV-format.</span><span class="sxs-lookup"><span data-stu-id="ae85e-135">Save the file with a new name, and specify CSV format.</span></span>
  
![En bild om hur du sparar en fil i Excel i CSV-format](../media/35a86ebe-63ab-4b4d-9a92-e177de33ebae.png)
  
<span data-ttu-id="ae85e-p109">När du sparar filen visas antagligen ett meddelande om att vissa funktioner i arbetsboken kan gå förlorade om du sparar filen i CSV-format. Det är OK. Klicka på **Ja** för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="ae85e-p109">When you save the file, you'll probably get a prompt that some features in your workbook will be lost if you save the file in CSV format. This is okay. Click **Yes** to continue.</span></span>
  
![En bild av frågan som du eventuellt får i Excel och som frågar om du verkligen vill spara filen i CSV-format](../media/51032a81-690c-45ef-bfc5-09ea7f790e98.png)
  
### <a name="tips-for-formatting-your-spreadsheet"></a><span data-ttu-id="ae85e-141">Tips på hur du formaterar kalkylbladet</span><span class="sxs-lookup"><span data-stu-id="ae85e-141">Tips for formatting your spreadsheet</span></span>

- <span data-ttu-id="ae85e-142">**Behöver jag samma kolumnrubriker som i exempelkalkylbladet?**</span><span class="sxs-lookup"><span data-stu-id="ae85e-142">**Do I need the same column headings as in the sample spreadsheet?**</span></span> <span data-ttu-id="ae85e-143">Ja.</span><span class="sxs-lookup"><span data-stu-id="ae85e-143">Yes.</span></span> <span data-ttu-id="ae85e-144">Exempelkalkylbladet innehåller kolumnrubriker på första raden.</span><span class="sxs-lookup"><span data-stu-id="ae85e-144">The sample spreadsheet contains column headings in the first row.</span></span> <span data-ttu-id="ae85e-145">De här rubrikerna är obligatoriska.</span><span class="sxs-lookup"><span data-stu-id="ae85e-145">These headings are required.</span></span> <span data-ttu-id="ae85e-146">För varje användare som du vill lägga till Microsoft 365 skapar du en rad under rubriken.</span><span class="sxs-lookup"><span data-stu-id="ae85e-146">For each user you want to add to Microsoft 365, create a row under the heading.</span></span> <span data-ttu-id="ae85e-147">Om du lägger till, ändrar eller tar bort någon kolumnrubrik kanske Microsoft 365 inte kan skapa användare från informationen i filen.</span><span class="sxs-lookup"><span data-stu-id="ae85e-147">If you add, change, or delete any of the column headings, Microsoft 365 might not be able to create users from the information in the file.</span></span>

- <span data-ttu-id="ae85e-p111">**Vad gör jag om jag inte har all information som behövs om en användare?** Fälten Användarnamn och Visningsnamn är obligatoriska, och du kan inte lägga till en ny användare om du inte har de uppgifterna. Om du saknar någon annan uppgift, till exempel faxnummer, kan du lägga in ett blanksteg och ett kommatecken för att visa att fältet ska vara tomt.</span><span class="sxs-lookup"><span data-stu-id="ae85e-p111">**What if I don't have all the information required for each user?** The user name and display name are required, and you cannot add a new user without this information. If you don't have some of the other information, such as the fax, you can use a space plus a comma to indicate that the field should remain blank.</span></span>

- <span data-ttu-id="ae85e-151">**Hur litet eller stort får kalkylbladet vara?**</span><span class="sxs-lookup"><span data-stu-id="ae85e-151">**How small or large can the spreadsheet be?**</span></span> <span data-ttu-id="ae85e-152">Kalkylbladet måste innehålla minst två rader.</span><span class="sxs-lookup"><span data-stu-id="ae85e-152">The spreadsheet must have at least two rows.</span></span> <span data-ttu-id="ae85e-153">One is for the column headings (the user data column label) and one for the user.</span><span class="sxs-lookup"><span data-stu-id="ae85e-153">One is for the column headings (the user data column label) and one for the user.</span></span> <span data-ttu-id="ae85e-154">You cannot have more than 251 rows.</span><span class="sxs-lookup"><span data-stu-id="ae85e-154">You cannot have more than 251 rows.</span></span> <span data-ttu-id="ae85e-155">If you need to import more than 250 users, you can create more than one spreadsheet.</span><span class="sxs-lookup"><span data-stu-id="ae85e-155">If you need to import more than 250 users, you can create more than one spreadsheet.</span></span>

- <span data-ttu-id="ae85e-156">**Vilka språk kan jag använda?**</span><span class="sxs-lookup"><span data-stu-id="ae85e-156">**What languages can I use?**</span></span> <span data-ttu-id="ae85e-157">När du skapar kalkylbladet kan du ange kolumnetiketter för användardata på alla språk och tecken, men du får inte ändra ordningen på etiketterna, som visas i exemplet.</span><span class="sxs-lookup"><span data-stu-id="ae85e-157">When you create your spreadsheet, you can enter user data column labels in any language or characters, but you must not change the order of the labels, as shown in the sample.</span></span> <span data-ttu-id="ae85e-158">Sedan kan du lägga in data i fälten, på vilket språk och med vilka tecken som helst, och spara filen i Unicode- eller UTF-8-format.</span><span class="sxs-lookup"><span data-stu-id="ae85e-158">You can then make entries into the fields, using any language or characters, and save your file in a Unicode or UTF-8 format.</span></span>

- <span data-ttu-id="ae85e-p114">**Vad gäller om jag lägger till användare från andra länder och regioner?** Skapa ett separat kalkylblad för varje område. Du måste gå igenom guiden Lägg till användare i grupp för varje kalkylblad, och då ange en enda plats för alla användare som ingår i den fil du arbetar med.</span><span class="sxs-lookup"><span data-stu-id="ae85e-p114">**What if I'm adding users from different countries or regions?** Create a separate spreadsheet for each area. You'll need to step through the Bulk add users wizard which each spreadsheet, giving a single location of all users included in the file that you're working with.</span></span>

- <span data-ttu-id="ae85e-p115">**Finns det någon begränsning för hur många tecken jag kan använda?** I följande tabell visas kolumnetiketter för användardata med motsvarande maximalt antal tecken i exempelkalkylbladet.</span><span class="sxs-lookup"><span data-stu-id="ae85e-p115">**Is there a limit to the number of characters I can use?** The following table shows the user data column labels and the maximum character length for each in the sample spreadsheet.</span></span>

|<span data-ttu-id="ae85e-164">**Kolumnetikett med användardata**</span><span class="sxs-lookup"><span data-stu-id="ae85e-164">**User data column label**</span></span>|<span data-ttu-id="ae85e-165">**Maximalt antal tecken**</span><span class="sxs-lookup"><span data-stu-id="ae85e-165">**Maximum character length**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ae85e-166">Användarnamn (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="ae85e-166">User Name (Required)</span></span>  <br/> |<span data-ttu-id="ae85e-167">79 inklusive at-tecknet (@), i det format som name@domain. \<extension\> .</span><span class="sxs-lookup"><span data-stu-id="ae85e-167">79 including the at sign (@), in the format name@domain.\<extension\>.</span></span> <span data-ttu-id="ae85e-168">Användarens alias får inte vara längre än 50 tecken och domännamn får inte vara längre än 48 tecken.</span><span class="sxs-lookup"><span data-stu-id="ae85e-168">The user's alias cannot exceed 50 characters, and the domain name cannot exceed 48 characters.</span></span>  <br/> |
|<span data-ttu-id="ae85e-169">Förnamn</span><span class="sxs-lookup"><span data-stu-id="ae85e-169">First Name</span></span>  <br/> |<span data-ttu-id="ae85e-170">64</span><span class="sxs-lookup"><span data-stu-id="ae85e-170">64</span></span>  <br/> |
|<span data-ttu-id="ae85e-171">Efternamn</span><span class="sxs-lookup"><span data-stu-id="ae85e-171">Last Name</span></span>  <br/> |<span data-ttu-id="ae85e-172">64</span><span class="sxs-lookup"><span data-stu-id="ae85e-172">64</span></span>  <br/> |
|<span data-ttu-id="ae85e-173">Visningsnamn (obligatoriskt)</span><span class="sxs-lookup"><span data-stu-id="ae85e-173">Display Name (required)</span></span>  <br/> |<span data-ttu-id="ae85e-174">256</span><span class="sxs-lookup"><span data-stu-id="ae85e-174">256</span></span>  <br/> |
|<span data-ttu-id="ae85e-175">Befattning</span><span class="sxs-lookup"><span data-stu-id="ae85e-175">Job Title</span></span>  <br/> |<span data-ttu-id="ae85e-176">64</span><span class="sxs-lookup"><span data-stu-id="ae85e-176">64</span></span>  <br/> |
|<span data-ttu-id="ae85e-177">Avdelning</span><span class="sxs-lookup"><span data-stu-id="ae85e-177">Department</span></span>  <br/> |<span data-ttu-id="ae85e-178">64</span><span class="sxs-lookup"><span data-stu-id="ae85e-178">64</span></span>  <br/> |
|<span data-ttu-id="ae85e-179">Kontorsnummer</span><span class="sxs-lookup"><span data-stu-id="ae85e-179">Office Number</span></span>  <br/> |<span data-ttu-id="ae85e-180">128</span><span class="sxs-lookup"><span data-stu-id="ae85e-180">128</span></span>  <br/> |
|<span data-ttu-id="ae85e-181">Telefonnr till arbetet</span><span class="sxs-lookup"><span data-stu-id="ae85e-181">Office Phone</span></span>  <br/> |<span data-ttu-id="ae85e-182">64</span><span class="sxs-lookup"><span data-stu-id="ae85e-182">64</span></span>  <br/> |
|<span data-ttu-id="ae85e-183">Mobiltelefon</span><span class="sxs-lookup"><span data-stu-id="ae85e-183">Mobile Phone</span></span>  <br/> |<span data-ttu-id="ae85e-184">64</span><span class="sxs-lookup"><span data-stu-id="ae85e-184">64</span></span>  <br/> |
|<span data-ttu-id="ae85e-185">Fax</span><span class="sxs-lookup"><span data-stu-id="ae85e-185">Fax</span></span>  <br/> |<span data-ttu-id="ae85e-186">64</span><span class="sxs-lookup"><span data-stu-id="ae85e-186">64</span></span>  <br/> |
|<span data-ttu-id="ae85e-187">Adress</span><span class="sxs-lookup"><span data-stu-id="ae85e-187">Address</span></span>  <br/> |<span data-ttu-id="ae85e-188">1023</span><span class="sxs-lookup"><span data-stu-id="ae85e-188">1023</span></span>  <br/> |
|<span data-ttu-id="ae85e-189">Ort</span><span class="sxs-lookup"><span data-stu-id="ae85e-189">City</span></span>  <br/> |<span data-ttu-id="ae85e-190">128</span><span class="sxs-lookup"><span data-stu-id="ae85e-190">128</span></span>  <br/> |
|<span data-ttu-id="ae85e-191">Region</span><span class="sxs-lookup"><span data-stu-id="ae85e-191">State or Province</span></span>  <br/> |<span data-ttu-id="ae85e-192">128</span><span class="sxs-lookup"><span data-stu-id="ae85e-192">128</span></span>  <br/> |
|<span data-ttu-id="ae85e-193">Postnummer</span><span class="sxs-lookup"><span data-stu-id="ae85e-193">ZIP or Postal Code</span></span>  <br/> |<span data-ttu-id="ae85e-194">40</span><span class="sxs-lookup"><span data-stu-id="ae85e-194">40</span></span>  <br/> |
|<span data-ttu-id="ae85e-195">Land eller region</span><span class="sxs-lookup"><span data-stu-id="ae85e-195">Country or Region</span></span>  <br/> |<span data-ttu-id="ae85e-196">128</span><span class="sxs-lookup"><span data-stu-id="ae85e-196">128</span></span>  <br/> |

### <a name="still-having-problems-when-adding-users-to-microsoft-365"></a><span data-ttu-id="ae85e-197">Har du fortfarande problem med att lägga till användare i Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="ae85e-197">Still having problems when adding users to Microsoft 365?</span></span>

- <span data-ttu-id="ae85e-p117">**Kontrollera en extra gång att kalkylbladet är rätt formaterat.** Kontrollera kolumnrubrikerna och se till att de överensstämmer med rubrikerna i exempelfilen. Se till att du följer reglerna om maximalt antal tecken och att varje fält avgränsas med ett komma.</span><span class="sxs-lookup"><span data-stu-id="ae85e-p117">**Double-check that the spreadsheet is formatted correctly.** Check the column headings to make sure they match the headings in the sample file. Make sure you're following the rules for character lengths and that each field is separated by a comma.</span></span>

- <span data-ttu-id="ae85e-201">**Vänta några minuter om du inte ser de nya Microsoft 365 på en gång.**</span><span class="sxs-lookup"><span data-stu-id="ae85e-201">**If you don't see the new users in Microsoft 365 right away, wait a few minutes.**</span></span> <span data-ttu-id="ae85e-202">Det kan ta en stund innan ändringarna har gjorts i alla tjänster i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae85e-202">It can take a little while for changes to go across all the services in Microsoft 365.</span></span> 

## <a name="related-articles"></a><span data-ttu-id="ae85e-203">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="ae85e-203">Related articles</span></span>

[<span data-ttu-id="ae85e-204">Lägga till användare individuellt eller flera samtidigt i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ae85e-204">Add users individually or in bulk to Microsoft 365</span></span>](/office365/admin/add-users/add-users)