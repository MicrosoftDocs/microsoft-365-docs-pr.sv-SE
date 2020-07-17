---
title: Registrera nya enheter själv
description: Registrera enheter själv så att de kan hanteras av Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 3c43c42ba2cb1feb339ad61b76d28fde4ed94298
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101665"
---
# <a name="register-new-devices-yourself"></a><span data-ttu-id="84bd0-103">Registrera nya enheter själv</span><span class="sxs-lookup"><span data-stu-id="84bd0-103">Register new devices yourself</span></span>

<span data-ttu-id="84bd0-104">Microsoft Managed Desktop kan fungera med helt nya enheter eller så kan du återanvända enheter som du kanske redan har (vilket kräver att du avbildar dem igen).</span><span class="sxs-lookup"><span data-stu-id="84bd0-104">Microsoft Managed Desktop can work with brand-new devices or you can re-use devices you might already have (which will require that you re-image them).</span></span> <span data-ttu-id="84bd0-105">Du kan registrera enheter med hjälp av Microsoft Managed Desktop Admin Portal.</span><span class="sxs-lookup"><span data-stu-id="84bd0-105">You can register devices by using the Microsoft Managed Desktop Admin Portal.</span></span>

> [!NOTE]
> <span data-ttu-id="84bd0-106">Arbeta med en partner för att få enheter?</span><span class="sxs-lookup"><span data-stu-id="84bd0-106">Working with a partner to obtain devices?</span></span> <span data-ttu-id="84bd0-107">Om så är fallet behöver du inte oroa dig för att få hårdvaran hashar; De tar hand om det åt dig.</span><span class="sxs-lookup"><span data-stu-id="84bd0-107">If so, you don't need to worry about getting the hardware hashes; they'll take care of that for you.</span></span> <span data-ttu-id="84bd0-108">Se till att din partner upprättar en relation med dig i [Partner center](https://partner.microsoft.com/dashboard).</span><span class="sxs-lookup"><span data-stu-id="84bd0-108">Make sure your partner establishes a relationship with you at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="84bd0-109">Din partner kan läsa mer på [Partner Center hjälp](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span><span class="sxs-lookup"><span data-stu-id="84bd0-109">Your partner can learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span> <span data-ttu-id="84bd0-110">När denna relation har upprättats registrerar din partner helt enkelt enheter för din räkning – inga ytterligare åtgärder krävs från dig.</span><span class="sxs-lookup"><span data-stu-id="84bd0-110">Once this relationship established, your partner will simply register devices on your behalf – no further action required from you.</span></span> <span data-ttu-id="84bd0-111">Om du vill se informationen eller om din partner har frågor läser du [Steg för partner för att registrera enheter](register-devices-partner.md).</span><span class="sxs-lookup"><span data-stu-id="84bd0-111">If you want to see the details, or your partner has questions, see [Steps for Partners to register devices](register-devices-partner.md).</span></span> <span data-ttu-id="84bd0-112">När enheterna har registrerats kan du fortsätta [med att kontrollera bilden](#check-the-image) och leverera [enheterna](#deliver-the-device) till användarna.</span><span class="sxs-lookup"><span data-stu-id="84bd0-112">Once the devices are registered, you can proceed with [checking the image](#check-the-image) and [delivering the devices](#deliver-the-device) to your users.</span></span>

## <a name="prepare-to-register-brand-new-devices"></a><span data-ttu-id="84bd0-113">Förbered att registrera helt nya enheter</span><span class="sxs-lookup"><span data-stu-id="84bd0-113">Prepare to register brand-new devices</span></span>


<span data-ttu-id="84bd0-114">När du har de nya enheterna i handen följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="84bd0-114">Once you have the new devices in hand, you'll follow these steps:</span></span>

1. [<span data-ttu-id="84bd0-115">Hämta maskinvaruhhhen för varje enhet.</span><span class="sxs-lookup"><span data-stu-id="84bd0-115">Obtain the hardware hash for each device.</span></span>](#obtain-the-hardware-hash)
2. [<span data-ttu-id="84bd0-116">Slå samman hash-data</span><span class="sxs-lookup"><span data-stu-id="84bd0-116">Merge the hash data</span></span>](#merge-hash-data)
3. <span data-ttu-id="84bd0-117">[Registrera enheterna i Microsoft Managed Desktop](#register-devices).</span><span class="sxs-lookup"><span data-stu-id="84bd0-117">[Register the devices in Microsoft Managed Desktop](#register-devices).</span></span>
4. [<span data-ttu-id="84bd0-118">Dubbelkolla att bilden är korrekt.</span><span class="sxs-lookup"><span data-stu-id="84bd0-118">Double-check that the image is correct.</span></span>](#check-the-image)
5. [<span data-ttu-id="84bd0-119">Leverera enheten</span><span class="sxs-lookup"><span data-stu-id="84bd0-119">Deliver the device</span></span>](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a><span data-ttu-id="84bd0-120">Skaffa maskinvaruhhh</span><span class="sxs-lookup"><span data-stu-id="84bd0-120">Obtain the hardware hash</span></span>

<span data-ttu-id="84bd0-121">Microsoft Managed Desktop identifierar varje enhet unikt genom att referera till dess maskinvaruhhh.</span><span class="sxs-lookup"><span data-stu-id="84bd0-121">Microsoft Managed Desktop identifies each device uniquely by referencing its hardware hash.</span></span> <span data-ttu-id="84bd0-122">Du har tre alternativ för att få den här informationen:</span><span class="sxs-lookup"><span data-stu-id="84bd0-122">You have three options for getting this information:</span></span>

- <span data-ttu-id="84bd0-123">Fråga oem-leverantören om registreringsfilen för Autopilot, som innehåller maskinvaruhännaren.</span><span class="sxs-lookup"><span data-stu-id="84bd0-123">Ask your OEM supplier for the AutoPilot registration file, which will include the hardware hashes.</span></span>
- <span data-ttu-id="84bd0-124">Kör ett [Windows PowerShell-skript](#powershell-script-method) på varje enhet och samla in resultaten i en fil.</span><span class="sxs-lookup"><span data-stu-id="84bd0-124">Run a [Windows PowerShell script](#powershell-script-method) on each device and collect the results in a file.</span></span>
- <span data-ttu-id="84bd0-125">Starta varje enhet – men slutför inte installationsupplevelsen för Windows – och [samla in hasharen på ett flyttbart flashminne](#flash-drive-method).</span><span class="sxs-lookup"><span data-stu-id="84bd0-125">Start each device--but don't complete the Windows setup experience--and [collect the hashes on a removable flash drive](#flash-drive-method).</span></span>

#### <a name="powershell-script-method"></a><span data-ttu-id="84bd0-126">PowerShell-skriptmetod</span><span class="sxs-lookup"><span data-stu-id="84bd0-126">PowerShell script method</span></span>

1.  <span data-ttu-id="84bd0-127">Öppna en PowerShell-prompt med administrativa rättigheter.</span><span class="sxs-lookup"><span data-stu-id="84bd0-127">Open a PowerShell prompt with administrative rights.</span></span>
2.  <span data-ttu-id="84bd0-128">Köra`Install-Script -Name Get-MMDRegistrationInfo`</span><span class="sxs-lookup"><span data-stu-id="84bd0-128">Run `Install-Script -Name Get-MMDRegistrationInfo`</span></span>
3.  <span data-ttu-id="84bd0-129">Köra`powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="84bd0-129">Run `powershell -ExecutionPolicy Unrestricted Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>

#### <a name="flash-drive-method"></a><span data-ttu-id="84bd0-130">Flash-enhet metod</span><span class="sxs-lookup"><span data-stu-id="84bd0-130">Flash drive method</span></span>

1. <span data-ttu-id="84bd0-131">På en annan enhet än den du registrerar sätter du i en USB-enhet.</span><span class="sxs-lookup"><span data-stu-id="84bd0-131">On a device other than the one you're registering, insert a USB drive.</span></span>
2. <span data-ttu-id="84bd0-132">Öppna en PowerShell-prompt med administrativa rättigheter.</span><span class="sxs-lookup"><span data-stu-id="84bd0-132">Open a PowerShell prompt with administrative rights.</span></span>
3. <span data-ttu-id="84bd0-133">Köra`Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span><span class="sxs-lookup"><span data-stu-id="84bd0-133">Run `Save-Script -Name Get-MMDRegistrationInfo -Path <pathToUsb>`</span></span>
4. <span data-ttu-id="84bd0-134">Slå på enheten du registrerar, men *starta inte installationsupplevelsen*.</span><span class="sxs-lookup"><span data-stu-id="84bd0-134">Turn on the device you are registering, but *do not start the setup experience*.</span></span> <span data-ttu-id="84bd0-135">Om du av misstag startar installationen måste du återställa eller konfigurera om enheten.</span><span class="sxs-lookup"><span data-stu-id="84bd0-135">If you accidentally start the setup experience, you'll have to reset or reimage the device.</span></span>
5. <span data-ttu-id="84bd0-136">Sätt i USB-enheten och tryck sedan på SKIFT + F10.</span><span class="sxs-lookup"><span data-stu-id="84bd0-136">Insert the USB drive, and then press SHIFT + F10.</span></span>
6. <span data-ttu-id="84bd0-137">Öppna en PowerShell-prompt med administrativa rättigheter och kör sedan `cd <pathToUsb>` .</span><span class="sxs-lookup"><span data-stu-id="84bd0-137">Open a PowerShell prompt with administrative rights, and then run `cd <pathToUsb>`.</span></span>
7. <span data-ttu-id="84bd0-138">Köra`Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span><span class="sxs-lookup"><span data-stu-id="84bd0-138">Run `Set-ExecutionPolicy -ExecutionPolicy Unrestricted`</span></span>
8. <span data-ttu-id="84bd0-139">Köra`.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span><span class="sxs-lookup"><span data-stu-id="84bd0-139">Run `.\Get-MMDRegistrationInfo -OutputFile <path>\hardwarehash.csv`</span></span>
9. <span data-ttu-id="84bd0-140">Ta bort USB-enheten och stäng sedan av enheten genom att köra`shutdown -s -t 0`</span><span class="sxs-lookup"><span data-stu-id="84bd0-140">Remove the USB drive, and then shut down the device by running `shutdown -s -t 0`</span></span>

>[!IMPORTANT]
><span data-ttu-id="84bd0-141">Slå inte på enheten du registrerar igen förrän du har registrerat dig för den.</span><span class="sxs-lookup"><span data-stu-id="84bd0-141">Do not power on the device you are registering again until you've completed registration for it.</span></span> 


### <a name="merge-hash-data"></a><span data-ttu-id="84bd0-142">Sammanfoga hash-data</span><span class="sxs-lookup"><span data-stu-id="84bd0-142">Merge hash data</span></span>

<span data-ttu-id="84bd0-143">Du måste ha data i CSV-filerna kombinerade till en enda fil för att slutföra registreringen.</span><span class="sxs-lookup"><span data-stu-id="84bd0-143">You'll need to have the data in the CSV files combined into a single file to complete registration.</span></span> <span data-ttu-id="84bd0-144">Här är ett exempel på PowerShell-skript för att göra det enkelt:</span><span class="sxs-lookup"><span data-stu-id="84bd0-144">Here's a sample PowerShell script to make this easy:</span></span>

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`
### <a name="register-devices"></a><span data-ttu-id="84bd0-145">Registrera enheter</span><span class="sxs-lookup"><span data-stu-id="84bd0-145">Register devices</span></span>

<span data-ttu-id="84bd0-146">CSV-filen måste vara i ett särskilt format för registrering.</span><span class="sxs-lookup"><span data-stu-id="84bd0-146">The CSV file must be in a particular format for registration.</span></span> <span data-ttu-id="84bd0-147">Om du själv har samlat in data i föregående steg bör filen redan vara i rätt format. Om du hämtar filen från en leverantör kan du behöva justera formatet.</span><span class="sxs-lookup"><span data-stu-id="84bd0-147">If you collected the data yourself in the previous steps, the file should already be in the right format; if you obtain the file from a supplier, you might need to adjust the format.</span></span>

>[!NOTE]
><span data-ttu-id="84bd0-148">För din bekvämlighet kan du ladda ner ett [exempel CSV fil](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv).</span><span class="sxs-lookup"><span data-stu-id="84bd0-148">For your convenience, you can download a [sample CSV file](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-self.csv).</span></span>

<span data-ttu-id="84bd0-149">Filen måste innehålla **exakt samma kolumnrubriker** som exemplet en (tillverkare, modell, etc.), men dina egna data för de andra raderna.</span><span class="sxs-lookup"><span data-stu-id="84bd0-149">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="84bd0-150">Om du använder mallen öppnar du den i ett textredigeringsverktyg som Anteckningar och överväg att lämna alla data enbart på rad 1, och ange bara data i raderna 2 och lägre.</span><span class="sxs-lookup"><span data-stu-id="84bd0-150">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number,Hardware Hash
  SpiralOrbit,ContosoABC,000000000000,dGhpc2RldmljZWlzYW5tbWRkZXZpY2U
  
  
  ```

>[!NOTE]
><span data-ttu-id="84bd0-151">Om du glömmer att ändra någon av exempeldata, kommer registreringen misslyckas.</span><span class="sxs-lookup"><span data-stu-id="84bd0-151">If you forget to change any of the sample data, registration will fail.</span></span>

#### <a name="register-devices-by-using-the-admin-portal"></a><span data-ttu-id="84bd0-152">Registrera enheter med hjälp av adminportalen</span><span class="sxs-lookup"><span data-stu-id="84bd0-152">Register devices by using the Admin Portal</span></span>

<span data-ttu-id="84bd0-153">Välj **Enheter** i det vänstra navigeringsfönstret i Microsoft Managed Desktop [Admin Portal.](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="84bd0-153">From the Microsoft Managed Desktop [Admin Portal](https://aka.ms/mmdportal), select **Devices** in the left navigation pane.</span></span> <span data-ttu-id="84bd0-154">Välj **+ Registrera enheter;** fly-in öppnar:</span><span class="sxs-lookup"><span data-stu-id="84bd0-154">Select **+ Register devices**; the fly-in opens:</span></span>

<span data-ttu-id="84bd0-155">[![Fly-in efter att ha valt Registrera enheter, lista enheter med kolumner för tilldelade användare, serienummer, status, senast sett datum och ålder](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span><span class="sxs-lookup"><span data-stu-id="84bd0-155">[![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/register-devices-flyin-sterile.png)](../../media/register-devices-flyin-sterile.png)</span></span>


[//]: # (Tyvärr är detta inte sant. Vi kan ta bort denna anmärkning - men lämnar det nu tills vi har en chans att prata om det.)

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


<span data-ttu-id="84bd0-157">Gör så här:</span><span class="sxs-lookup"><span data-stu-id="84bd0-157">Follow these steps:</span></span>

1. <span data-ttu-id="84bd0-158">I **Filöverföring**anger du en sökväg till CSV-filen som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="84bd0-158">In **File upload**, provide a path to the CSV file you created previously.</span></span>
2. <span data-ttu-id="84bd0-159">Du kan också lägga till ett **order-ID** eller **inköps-ID** för dina egna spårningsändamål.</span><span class="sxs-lookup"><span data-stu-id="84bd0-159">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="84bd0-160">Det finns inga formatkrav för dessa värden.</span><span class="sxs-lookup"><span data-stu-id="84bd0-160">There are no format requirements for these values.</span></span>
3. <span data-ttu-id="84bd0-161">Välj **Registrera enheter**.</span><span class="sxs-lookup"><span data-stu-id="84bd0-161">Select **Register devices**.</span></span> <span data-ttu-id="84bd0-162">Systemet lägger till enheterna i listan över enheter på **bladet Enheter**, markerade som **Registrering väntar**.</span><span class="sxs-lookup"><span data-stu-id="84bd0-162">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="84bd0-163">Registreringen tar vanligtvis mindre än 10 minuter, och när den lyckas visas enheten som **redo för användaren,** vilket innebär att den är klar och väntar på att en slutanvändare ska börja använda.</span><span class="sxs-lookup"><span data-stu-id="84bd0-163">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="84bd0-164">Du kan övervaka förloppet för enhetsregistrering på sidan **Microsoft Managed Desktop - Devices.**</span><span class="sxs-lookup"><span data-stu-id="84bd0-164">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="84bd0-165">Möjliga tillstånd som rapporteras där inkluderar:</span><span class="sxs-lookup"><span data-stu-id="84bd0-165">Possible states reported there include:</span></span>

| <span data-ttu-id="84bd0-166">Statligt</span><span class="sxs-lookup"><span data-stu-id="84bd0-166">State</span></span> | <span data-ttu-id="84bd0-167">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="84bd0-167">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="84bd0-168">Registrering väntar</span><span class="sxs-lookup"><span data-stu-id="84bd0-168">Registration pending</span></span> | <span data-ttu-id="84bd0-169">Registreringen är inte klar ännu.</span><span class="sxs-lookup"><span data-stu-id="84bd0-169">Registration is not done yet.</span></span> <span data-ttu-id="84bd0-170">Kom tillbaka senare.</span><span class="sxs-lookup"><span data-stu-id="84bd0-170">Check back later.</span></span> |
| <span data-ttu-id="84bd0-171">Registreringen misslyckades</span><span class="sxs-lookup"><span data-stu-id="84bd0-171">Registration failed</span></span> | <span data-ttu-id="84bd0-172">Det gick inte att slutföra registreringen.</span><span class="sxs-lookup"><span data-stu-id="84bd0-172">Registration could not be completed.</span></span> <span data-ttu-id="84bd0-173">Mer information finns i [Registrering av felsökning av enheten.](#troubleshooting-device-registration)</span><span class="sxs-lookup"><span data-stu-id="84bd0-173">Refer to [Troubleshooting device registration](#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="84bd0-174">Redo för användare</span><span class="sxs-lookup"><span data-stu-id="84bd0-174">Ready for user</span></span> | <span data-ttu-id="84bd0-175">Registreringen lyckades och enheten är nu klar att levereras till slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="84bd0-175">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="84bd0-176">Microsoft Managed Desktop guidar dem genom första gången set-up, så det finns ingen anledning för dig att göra några ytterligare förberedelser.</span><span class="sxs-lookup"><span data-stu-id="84bd0-176">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="84bd0-177">Aktiva</span><span class="sxs-lookup"><span data-stu-id="84bd0-177">Active</span></span> | <span data-ttu-id="84bd0-178">Enheten har levererats till slutanvändaren och de har registrerat sig hos din klient.</span><span class="sxs-lookup"><span data-stu-id="84bd0-178">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="84bd0-179">Detta indikerar också att de regelbundet använder enheten.</span><span class="sxs-lookup"><span data-stu-id="84bd0-179">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="84bd0-180">Inaktiva</span><span class="sxs-lookup"><span data-stu-id="84bd0-180">Inactive</span></span> | <span data-ttu-id="84bd0-181">Enheten har levererats till slutanvändaren och de har registrerat sig hos din klient.</span><span class="sxs-lookup"><span data-stu-id="84bd0-181">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="84bd0-182">De har dock inte använt enheten nyligen (under de senaste 7 dagarna).</span><span class="sxs-lookup"><span data-stu-id="84bd0-182">However, they have not used the device recently (in the last 7 days).</span></span>  | 

#### <a name="troubleshooting-device-registration"></a><span data-ttu-id="84bd0-183">Felsöka enhetsregistrering</span><span class="sxs-lookup"><span data-stu-id="84bd0-183">Troubleshooting device registration</span></span>

| <span data-ttu-id="84bd0-184">Felmeddelande</span><span class="sxs-lookup"><span data-stu-id="84bd0-184">Error message</span></span> | <span data-ttu-id="84bd0-185">Information</span><span class="sxs-lookup"><span data-stu-id="84bd0-185">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="84bd0-186">Enheten hittades inte</span><span class="sxs-lookup"><span data-stu-id="84bd0-186">Device not found</span></span> | <span data-ttu-id="84bd0-187">Vi kunde inte registrera den här enheten eftersom vi inte kunde hitta en matchning för den angivna tillverkaren, modellen eller serienumret.</span><span class="sxs-lookup"><span data-stu-id="84bd0-187">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="84bd0-188">Bekräfta dessa värden med din enhetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="84bd0-188">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="84bd0-189">Maskinvaruh hash är ogiltigt</span><span class="sxs-lookup"><span data-stu-id="84bd0-189">Hardware hash not valid</span></span> | <span data-ttu-id="84bd0-190">Maskinvaruhhingen som du angav för den här enheten har inte formaterats korrekt.</span><span class="sxs-lookup"><span data-stu-id="84bd0-190">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="84bd0-191">Dubbelkolla maskinvaruhhhen och skicka sedan in den igen.</span><span class="sxs-lookup"><span data-stu-id="84bd0-191">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="84bd0-192">Enheten har redan registrerats</span><span class="sxs-lookup"><span data-stu-id="84bd0-192">Device already registered</span></span> | <span data-ttu-id="84bd0-193">Den här enheten är redan registrerad i din organisation.</span><span class="sxs-lookup"><span data-stu-id="84bd0-193">This device is already registered to your organization.</span></span> <span data-ttu-id="84bd0-194">Inga ytterligare åtgärder krävs.</span><span class="sxs-lookup"><span data-stu-id="84bd0-194">No further action required.</span></span> |
| <span data-ttu-id="84bd0-195">Enhet som påstås av en annan organisation</span><span class="sxs-lookup"><span data-stu-id="84bd0-195">Device claimed by another organization</span></span> | <span data-ttu-id="84bd0-196">Den här enheten har redan hävdats av en annan organisation.</span><span class="sxs-lookup"><span data-stu-id="84bd0-196">This device has already been claimed by another organization.</span></span> <span data-ttu-id="84bd0-197">Kontrollera med din enhetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="84bd0-197">Check with your device supplier.</span></span> |
| <span data-ttu-id="84bd0-198">Oväntat fel</span><span class="sxs-lookup"><span data-stu-id="84bd0-198">Unexpected error</span></span> | <span data-ttu-id="84bd0-199">Det gick inte att bearbeta din begäran automatiskt.</span><span class="sxs-lookup"><span data-stu-id="84bd0-199">Your request could not be automatically processed.</span></span> <span data-ttu-id="84bd0-200">Kontakta supporten och ange ID:et för begäran:<requestId></span><span class="sxs-lookup"><span data-stu-id="84bd0-200">Contact Support and provide the Request ID: <requestId></span></span> |

### <a name="check-the-image"></a><span data-ttu-id="84bd0-201">Kontrollera bilden</span><span class="sxs-lookup"><span data-stu-id="84bd0-201">Check the image</span></span>

<span data-ttu-id="84bd0-202">Om enheten kommer från en Microsoft Managed Desktop-partnerleverantör ska avbildningen vara korrekt.</span><span class="sxs-lookup"><span data-stu-id="84bd0-202">If your device has come from a Microsoft Managed Desktop partner supplier, the image should be correct.</span></span>

<span data-ttu-id="84bd0-203">Du är också välkommen att använda bilden på egen hand om du föredrar.</span><span class="sxs-lookup"><span data-stu-id="84bd0-203">You’re also welcome to apply the image on your own if you prefer.</span></span> <span data-ttu-id="84bd0-204">För att komma igång kontaktar du den Microsoft-representant du arbetar med och de ger dig plats och steg för att tillämpa avbildningen.</span><span class="sxs-lookup"><span data-stu-id="84bd0-204">To get started, contact the Microsoft representative you’re working with and they will provide you the location and steps for applying the image.</span></span>

### <a name="deliver-the-device"></a><span data-ttu-id="84bd0-205">Leverera enheten</span><span class="sxs-lookup"><span data-stu-id="84bd0-205">Deliver the device</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84bd0-206">Innan du lämnar över enheten till användaren ska du se till att du har skaffat och tillämpat [lämpliga licenser](../get-ready/prerequisites.md) för den användaren.</span><span class="sxs-lookup"><span data-stu-id="84bd0-206">Before you hand off the device to your user, make sure you have obtained and applied the [appropriate licenses](../get-ready/prerequisites.md) for that user.</span></span>

<span data-ttu-id="84bd0-207">Om alla licenser tillämpas kan du [göra användarna redo att använda enheter](get-started-devices.md)och sedan kan användaren starta enheten och gå vidare genom installationen av Windows.</span><span class="sxs-lookup"><span data-stu-id="84bd0-207">If all the licenses are applied, you can [get your users ready to use devices](get-started-devices.md), and then your user can start up the device and proceed through the Windows setup experience.</span></span>






