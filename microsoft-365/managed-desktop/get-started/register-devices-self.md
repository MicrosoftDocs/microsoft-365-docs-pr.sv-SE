---
title: Registrera nya enheter själv
description: Registrera enheter själv så att de kan hanteras av Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 1d4ca01e7b791dafc952b62a5f5dd59263b31546
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42806794"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="917e8-103">Registrera nya enheter själv</span><span class="sxs-lookup"><span data-stu-id="917e8-103">Register new devices yourself</span></span>

<span data-ttu-id="917e8-104">Microsoft Managed Desktop kan arbeta med helt nya enheter eller så kan du återanvända enheter som du kanske redan har (vilket kräver att du avbildar dem igen).</span><span class="sxs-lookup"><span data-stu-id="917e8-104">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="917e8-105">Du kan registrera enheter med Hjälp av Microsoft Managed Desktop på Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="917e8-105">You can register devices by using Microsoft Managed Desktop on the Azure Portal.</span></span>

> [!NOTE]
> <span data-ttu-id="917e8-106">Arbetar du med en partner för att hämta enheter?</span><span class="sxs-lookup"><span data-stu-id="917e8-106">Working with a partner to obtain devices?</span></span> <span data-ttu-id="917e8-107">Om så är fallet behöver du inte oroa dig för att få hårdvarahashes; De tar hand om det åt dig.</span><span class="sxs-lookup"><span data-stu-id="917e8-107">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="917e8-108">Kontrollera att din partner upprättar en relation med dig i [Partnercenter](https://partner.microsoft.com/dashboard) och att de innehåller delegerade administrationsprivilegier för Azure Active Directory och Office 365.</span><span class="sxs-lookup"><span data-stu-id="917e8-108">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard) and that they include delegated administration privileges for Azure Active Directory and Office 365.</span></span> <span data-ttu-id="917e8-109">Din partner kan läsa mer på [Hjälp i PartnerCenter.](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)</span><span class="sxs-lookup"><span data-stu-id="917e8-109">Your partner can learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="917e8-110">När denna relation har upprättats registrerar din partner helt enkelt enheter för din räkning – inga ytterligare åtgärder krävs från dig.</span><span class="sxs-lookup"><span data-stu-id="917e8-110">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="917e8-111">Om du vill se informationen, eller om din partner har frågor, se [Steg för partners för att registrera enheter](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="917e8-111">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="917e8-112">När enheterna har registrerats kan du fortsätta [med att kontrollera avbildningen](#check-the-image) och [leverera enheterna](#deliver-the-device) till användarna.</span><span class="sxs-lookup"><span data-stu-id="917e8-112">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>

## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="917e8-113">Förbered dig på att registrera helt nya enheter</span><span class="sxs-lookup"><span data-stu-id="917e8-113">Prepare to register brand-new devices</span></span>


<span data-ttu-id="917e8-114">När du har de nya enheterna i handen följer du följande steg:</span><span class="sxs-lookup"><span data-stu-id="917e8-114">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="917e8-115">Skaffa maskinvaruhash för varje enhet.</span><span class="sxs-lookup"><span data-stu-id="917e8-115">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="917e8-116">Sammanfoga hash-data</span><span class="sxs-lookup"><span data-stu-id="917e8-116">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="917e8-117">[Registrera enheterna i Microsoft Managed Desktop](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="917e8-117">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="917e8-118">Dubbelkolla att bilden är korrekt.</span><span class="sxs-lookup"><span data-stu-id="917e8-118">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="917e8-119">Leverera enheten</span><span class="sxs-lookup"><span data-stu-id="917e8-119">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="917e8-120">Skaffa maskinvaruhash</span><span class="sxs-lookup"><span data-stu-id="917e8-120">Obtain the hardware hash</span></span>

<span data-ttu-id="917e8-121">Microsoft Managed Desktop identifierar varje enhet unikt genom att referera till dess maskinvaruhash.</span><span class="sxs-lookup"><span data-stu-id="917e8-121">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="917e8-122">Du har tre alternativ för att få den här informationen:</span><span class="sxs-lookup"><span data-stu-id="917e8-122">You have three options for getting this information:</span></span>

- <span data-ttu-id="917e8-123">Fråga oem-leverantören om AutoPilot-registreringsfilen, som inkluderar maskinvaruhashar.</span><span class="sxs-lookup"><span data-stu-id="917e8-123">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="917e8-124">Kör ett [Windows PowerShell-skript](#powershell-script-method) på varje enhet och samla in resultaten i en fil.</span><span class="sxs-lookup"><span data-stu-id="917e8-124">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="917e8-125">Starta varje enhet – men slutför inte Windows-installationsupplevelsen – och [samla in hasharna på ett flyttbart flashminne](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="917e8-125">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="917e8-126">PowerShell-skriptmetod</span><span class="sxs-lookup"><span data-stu-id="917e8-126">PowerShell script method</span></span>

1.  <span data-ttu-id="917e8-127">Öppna en PowerShell-prompt med administrativa rättigheter.</span><span class="sxs-lookup"><span data-stu-id="917e8-127">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="917e8-128">Köra`Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="917e8-128">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="917e8-129">Köra`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="917e8-129">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>

#### <a name="flash-drive-method"></a><span data-ttu-id="917e8-130">Flash-enhet metod</span><span class="sxs-lookup"><span data-stu-id="917e8-130">Flash drive method</span></span>

1. <span data-ttu-id="917e8-131">Sätt i en USB-enhet på en annan enhet än den du registrerar.</span><span class="sxs-lookup"><span data-stu-id="917e8-131">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="917e8-132">Öppna en PowerShell-prompt med administrativa rättigheter.</span><span class="sxs-lookup"><span data-stu-id="917e8-132">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="917e8-133">Köra`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="917e8-133">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="917e8-134">Slå på enheten som du registrerar, men *starta inte installationsupplevelsen*.</span><span class="sxs-lookup"><span data-stu-id="917e8-134">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="917e8-135">Om du av misstag startar installationsupplevelsen måste du återställa eller avbilda enheten igen.</span><span class="sxs-lookup"><span data-stu-id="917e8-135">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="917e8-136">Sätt i USB-enheten och tryck sedan på SKIFT + F10.</span><span class="sxs-lookup"><span data-stu-id="917e8-136">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="917e8-137">Öppna en PowerShell-prompt med administrativa `cd <pathToUsb>`rättigheter och kör sedan .</span><span class="sxs-lookup"><span data-stu-id="917e8-137">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="917e8-138">Köra`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="917e8-138">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="917e8-139">Köra`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="917e8-139">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="917e8-140">Ta bort USB-enheten och stäng sedan av enheten genom att köra`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="917e8-140">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="917e8-141">Slå inte på enheten som du registrerar igen förrän du har slutfört registreringen för den.</span><span class="sxs-lookup"><span data-stu-id="917e8-141">Do not power on the device you are registering again until you've completed registration for it.</span></span> 


### <a name="merge-hash-data"></a><span data-ttu-id="917e8-142">Sammanfoga hash-data</span><span class="sxs-lookup"><span data-stu-id="917e8-142">Merge hash data</span></span>

<span data-ttu-id="917e8-143">Du måste ha data i CSV-filerna kombinerade till en enda fil för att slutföra registreringen.</span><span class="sxs-lookup"><span data-stu-id="917e8-143">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="917e8-144">Här är ett exempel powershell-skript för att göra detta enkelt:</span><span class="sxs-lookup"><span data-stu-id="917e8-144">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`
### <a name="register-devices"></a><span data-ttu-id="917e8-145">Registrera enheter</span><span class="sxs-lookup"><span data-stu-id="917e8-145">Register devices</span></span>

<span data-ttu-id="917e8-146">CSV-filen måste vara i ett visst format för registrering.</span><span class="sxs-lookup"><span data-stu-id="917e8-146">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="917e8-147">Om du har samlat in data själv i föregående steg ska filen redan vara i rätt format. Om du hämtar filen från en leverantör kan du behöva justera formatet.</span><span class="sxs-lookup"><span data-stu-id="917e8-147">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="917e8-148">För din bekvämlighet kan du ladda ner ett [exempel CSV-fil](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv).</span><span class="sxs-lookup"><span data-stu-id="917e8-148">For your convenience, you can download a [sample CSV file](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv).</span></span>

<span data-ttu-id="917e8-149">Filen måste innehålla **exakt samma kolumnrubriker** som exempelrubriken (tillverkare, modell osv.), men dina egna data för de andra raderna.</span><span class="sxs-lookup"><span data-stu-id="917e8-149">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="917e8-150">Om du använder mallen öppnar du den i ett textredigeringsverktyg som Anteckningar och överväg att lämna alla data på rad 1 ensam, och ange bara data i rad 2 och nedan.</span><span class="sxs-lookup"><span data-stu-id="917e8-150">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="917e8-151">Om du glömmer att ändra någon av exempeldata misslyckas registreringen.</span><span class="sxs-lookup"><span data-stu-id="917e8-151">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="917e8-152">Registrera enheter med hjälp av Azure Portal</span><span class="sxs-lookup"><span data-stu-id="917e8-152">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="917e8-153">Välj **Enheter** i den vänstra navigeringsfönstret i Microsoft Managed Desktop [Azure Portal.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="917e8-153">From the Microsoft Managed Desktop [Azure Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="917e8-154">Välj **+ Registrera enheter**; inflygningen öppnas:</span><span class="sxs-lookup"><span data-stu-id="917e8-154">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="917e8-155">[![Inflygning efter att ha valt Registrera enheter, lista enheter med kolumner för tilldelade användare, serienummer, status, senast sett datum och ålder](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="917e8-155">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span></span>


[//]: # (Tyvärr är detta inte sant. Vi kan ta bort denna anmärkning - men lämnar den nu tills vi har en chans att prata om det.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="917e8-157">Följ anvisningarna nedan:</span><span class="sxs-lookup"><span data-stu-id="917e8-157">Follow these steps:</span></span>

1. <span data-ttu-id="917e8-158">Ange en sökväg till den CSV-fil som du skapade tidigare i **Filuppladdning.**</span><span class="sxs-lookup"><span data-stu-id="917e8-158">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="917e8-159">Du kan också lägga till ett **order-ID** eller **inköps-ID** för dina egna spårningsändamål.</span><span class="sxs-lookup"><span data-stu-id="917e8-159">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="917e8-160">Det finns inga formatkrav för dessa värden.</span><span class="sxs-lookup"><span data-stu-id="917e8-160">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="917e8-161">Välj **Registrera enheter**.</span><span class="sxs-lookup"><span data-stu-id="917e8-161">Select **Register devices**.</span></span> <span data-ttu-id="917e8-162">Systemet lägger till enheterna i listan över enheter på **bladet Enheter**, markerat som **Registreringsväntande**.</span><span class="sxs-lookup"><span data-stu-id="917e8-162">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="917e8-163">Registreringen tar vanligtvis mindre än 10 minuter, och när enheten lyckas visas som **klar för användaren,** vilket innebär att den är klar och väntar på att en slutanvändare ska börja använda.</span><span class="sxs-lookup"><span data-stu-id="917e8-163">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="917e8-164">Du kan övervaka förloppet för enhetsregistrering på sidan **Microsoft Managed Desktop – Enheter.**</span><span class="sxs-lookup"><span data-stu-id="917e8-164">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="917e8-165">Möjliga tillstånd som rapporteras där inkluderar:</span><span class="sxs-lookup"><span data-stu-id="917e8-165">Possible states reported there include:</span></span>

| <span data-ttu-id="917e8-166">Statligt</span><span class="sxs-lookup"><span data-stu-id="917e8-166">State</span></span> | <span data-ttu-id="917e8-167">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="917e8-167">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="917e8-168">Väntande registrering</span><span class="sxs-lookup"><span data-stu-id="917e8-168">Registration pending</span></span> | <span data-ttu-id="917e8-169">Registreringen är inte klar än.</span><span class="sxs-lookup"><span data-stu-id="917e8-169">Registration is not done yet.</span></span> <span data-ttu-id="917e8-170">Kom tillbaka senare.</span><span class="sxs-lookup"><span data-stu-id="917e8-170">Check back later.</span></span> |
| <span data-ttu-id="917e8-171">Registreringen misslyckades</span><span class="sxs-lookup"><span data-stu-id="917e8-171">Registration failed</span></span> | <span data-ttu-id="917e8-172">Det gick inte att slutföra registreringen.</span><span class="sxs-lookup"><span data-stu-id="917e8-172">Registration could not be completed.</span></span> <span data-ttu-id="917e8-173">Mer information finns i [Felsöka enhetsregistrering.](#troubleshooting-device-registration)</span><span class="sxs-lookup"><span data-stu-id="917e8-173">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="917e8-174">Redo för användare</span><span class="sxs-lookup"><span data-stu-id="917e8-174">Ready for user</span></span> | <span data-ttu-id="917e8-175">Registreringen lyckades och enheten är nu redo att levereras till slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="917e8-175">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="917e8-176">Microsoft Managed Desktop guidar dem genom första gången set-up, så det finns ingen anledning för dig att göra några ytterligare förberedelser.</span><span class="sxs-lookup"><span data-stu-id="917e8-176">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="917e8-177">Aktiva</span><span class="sxs-lookup"><span data-stu-id="917e8-177">Active</span></span> | <span data-ttu-id="917e8-178">Enheten har levererats till slutanvändaren och de har registrerat sig hos din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="917e8-178">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="917e8-179">Detta indikerar också att de regelbundet använder enheten.</span><span class="sxs-lookup"><span data-stu-id="917e8-179">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="917e8-180">Inaktiva</span><span class="sxs-lookup"><span data-stu-id="917e8-180">Inactive</span></span> | <span data-ttu-id="917e8-181">Enheten har levererats till slutanvändaren och de har registrerat sig hos din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="917e8-181">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="917e8-182">De har dock inte använt enheten nyligen (under de senaste 7 dagarna).</span><span class="sxs-lookup"><span data-stu-id="917e8-182">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="917e8-183">Felsöka enhetsregistrering</span><span class="sxs-lookup"><span data-stu-id="917e8-183">Troubleshooting device registration</span></span>

| <span data-ttu-id="917e8-184">Felmeddelande</span><span class="sxs-lookup"><span data-stu-id="917e8-184">Error message</span></span> | <span data-ttu-id="917e8-185">Information</span><span class="sxs-lookup"><span data-stu-id="917e8-185">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="917e8-186">Enheten hittades inte</span><span class="sxs-lookup"><span data-stu-id="917e8-186">Device not found</span></span> | <span data-ttu-id="917e8-187">Vi kunde inte registrera den här enheten eftersom vi inte kunde hitta en matchning för den medföljande tillverkaren, modellen eller serienumret.</span><span class="sxs-lookup"><span data-stu-id="917e8-187">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="917e8-188">Bekräfta dessa värden med din enhetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="917e8-188">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="917e8-189">Maskinvaruhash är ogiltigt</span><span class="sxs-lookup"><span data-stu-id="917e8-189">Hardware hash not valid</span></span> | <span data-ttu-id="917e8-190">Maskinvaruhash som du angav för den här enheten har inte formaterats korrekt.</span><span class="sxs-lookup"><span data-stu-id="917e8-190">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="917e8-191">Dubbelkolla maskinvaruhash och skicka sedan in igen.</span><span class="sxs-lookup"><span data-stu-id="917e8-191">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="917e8-192">Enheten har redan registrerats</span><span class="sxs-lookup"><span data-stu-id="917e8-192">Device already registered</span></span> | <span data-ttu-id="917e8-193">Den här enheten är redan registrerad i din organisation.</span><span class="sxs-lookup"><span data-stu-id="917e8-193">This device is already registered to your organization.</span></span> <span data-ttu-id="917e8-194">Inga ytterligare åtgärder krävs.</span><span class="sxs-lookup"><span data-stu-id="917e8-194">No further action required.</span></span> |
| <span data-ttu-id="917e8-195">Enhet som en annan organisation har gjort anspråk på</span><span class="sxs-lookup"><span data-stu-id="917e8-195">Device claimed by another organization</span></span> | <span data-ttu-id="917e8-196">Den här enheten har redan hävdats av en annan organisation.</span><span class="sxs-lookup"><span data-stu-id="917e8-196">This device has already been claimed by another organization.</span></span> <span data-ttu-id="917e8-197">Kontrollera med din enhetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="917e8-197">Check with your device supplier.</span></span> |
| <span data-ttu-id="917e8-198">Oväntat fel</span><span class="sxs-lookup"><span data-stu-id="917e8-198">Unexpected error</span></span> | <span data-ttu-id="917e8-199">Det gick inte att behandla din begäran automatiskt.</span><span class="sxs-lookup"><span data-stu-id="917e8-199">Your request could not be automatically processed.</span></span> <span data-ttu-id="917e8-200">Kontakta supporten och ange begärande-ID:<requestId></span><span class="sxs-lookup"><span data-stu-id="917e8-200">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="917e8-201">Kontrollera bilden</span><span class="sxs-lookup"><span data-stu-id="917e8-201">Check the image</span></span>

<span data-ttu-id="917e8-202">Om enheten har hämtats från en Microsoft Managed Desktop-partnerleverantör bör avbildningen vara korrekt.</span><span class="sxs-lookup"><span data-stu-id="917e8-202">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="917e8-203">Du är också välkommen att använda bilden på egen hand om du vill.</span><span class="sxs-lookup"><span data-stu-id="917e8-203">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="917e8-204">För att komma igång kontaktar du den Microsoft-representant som du arbetar med och de ger dig plats och steg för att använda avbildningen.</span><span class="sxs-lookup"><span data-stu-id="917e8-204">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="917e8-205">Leverera enheten</span><span class="sxs-lookup"><span data-stu-id="917e8-205">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="917e8-206">Innan du lämnar ut enheten till användaren kontrollerar du att du har fått och tillämpat [lämpliga licenser](../get-ready/prerequisites.md) för den användaren.</span><span class="sxs-lookup"><span data-stu-id="917e8-206">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="917e8-207">Om alla licenser tillämpas kan du [förbereda användarna för att använda enheter](get-started-devices.md)och sedan kan användaren starta enheten och gå igenom installationsprogrammet för Windows.</span><span class="sxs-lookup"><span data-stu-id="917e8-207">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>






