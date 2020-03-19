---
title: Steg för partners att registrera enheter
description: Hur partner kan registrera enheter så att de kan hanteras av Microsoft Managed Desktop
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: dc446281e8a791b59a9ac97592ff6a53dcde310c
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42805441"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="e18c0-103">Steg för partners att registrera enheter</span><span class="sxs-lookup"><span data-stu-id="e18c0-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="e18c0-104">I det här avsnittet beskrivs stegen för partners att följa för att registrera enheter.</span><span class="sxs-lookup"><span data-stu-id="e18c0-104">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="e18c0-105">Processen för att registrera enheter själv dokumenteras själv i [Registrera enheter i Microsoft Managed Desktop själv](register-devices-self.md).</span><span class="sxs-lookup"><span data-stu-id="e18c0-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="e18c0-106">Förbered för registrering</span><span class="sxs-lookup"><span data-stu-id="e18c0-106">Prepare for registration</span></span> 
<span data-ttu-id="e18c0-107">Innan du slutför registreringen för en kund måste du först upprätta en relation med dem på [Partnercenter.](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="e18c0-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="e18c0-108">Var noga med att välja **Inkludera delegerade administrationsbehörigheter för Azure Active Directory och Office 365**.</span><span class="sxs-lookup"><span data-stu-id="e18c0-108">Be sure to select **Include delegated administration privileges for Azure Active Directory and Office 365**.</span></span> <span data-ttu-id="e18c0-109">Läs mer på [Hjälp till PartnerCenter](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span><span class="sxs-lookup"><span data-stu-id="e18c0-109">Learn more at [Partner Center help](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer).</span></span>

<span data-ttu-id="e18c0-110">Om du vill slutföra registreringen för kunden skapar du först en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="e18c0-110">To complete registration for your customer, first create a CSV file.</span></span>

>[!NOTE]
><span data-ttu-id="e18c0-111">För din bekvämlighet kan du ladda ner en [exempel CSV-fil](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.csv) för den här *partnerversionen*.</span><span class="sxs-lookup"><span data-stu-id="e18c0-111">For your convenience, you can download a [sample CSV file](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-started/downloads/device-registration-sample-partner.csv) for this *Partner version*.</span></span>

<span data-ttu-id="e18c0-112">Filen måste innehålla **exakt samma kolumnrubriker** som exempelrubriken (tillverkare, modell osv.), men dina egna data för de andra raderna.</span><span class="sxs-lookup"><span data-stu-id="e18c0-112">Your file needs to include the **exact same column headings** as the sample one (Manufacturer, Model, etc.), but your own data for the other rows.</span></span> <span data-ttu-id="e18c0-113">Om du använder mallen öppnar du den i ett textredigeringsverktyg som Anteckningar och överväg att lämna alla data på rad 1 ensam, och ange bara data i rad 2 och nedan.</span><span class="sxs-lookup"><span data-stu-id="e18c0-113">If you use the template, open it in a text editing tool such as Notepad, and consider leaving all the data in row 1 alone, only entering data in rows 2 and below.</span></span> 
    
  ```
 Manufacturer,Model,Serial Number
  SpiralOrbit,ContosoABC,000000000000
  
  
  ```




>[!NOTE]
><span data-ttu-id="e18c0-114">Det här formatet är bara för partnerprocessen.</span><span class="sxs-lookup"><span data-stu-id="e18c0-114">This format is only for the Partner process.</span></span> <span data-ttu-id="e18c0-115">Processen för självregistrering dokumenteras själv i [Registrera enheter i Microsoft Managed Desktop själv](register-devices-self.md).</span><span class="sxs-lookup"><span data-stu-id="e18c0-115">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="e18c0-116">Dessa värden måste matcha tillverkarens värden från SMBIOS exakt, inklusive versaler och specialtecken.</span><span class="sxs-lookup"><span data-stu-id="e18c0-116">These values must match the manufacturer values from SMBIOS exactly, including capitalization and special characters.</span></span> 

- <span data-ttu-id="e18c0-117">Enhetstillverkare (exempel: SpiralOrbit)</span><span class="sxs-lookup"><span data-stu-id="e18c0-117">Device manufacturer (example: SpiralOrbit)</span></span> 
- <span data-ttu-id="e18c0-118">Enhetsmodell (exempel: ContosoABC)</span><span class="sxs-lookup"><span data-stu-id="e18c0-118">Device model (example: ContosoABC)</span></span>
- <span data-ttu-id="e18c0-119">Serienummer för enhet</span><span class="sxs-lookup"><span data-stu-id="e18c0-119">Device serial number</span></span>

## <a name="register-devices-by-using-the-azure-portal"></a><span data-ttu-id="e18c0-120">Registrera enheter med hjälp av Azure Portal</span><span class="sxs-lookup"><span data-stu-id="e18c0-120">Register devices by using the Azure Portal</span></span>

<span data-ttu-id="e18c0-121">Registrering med hjälp av Azure Portal är samma som för självbetjäning, förutom att du kommer åt portalen på olika sätt.</span><span class="sxs-lookup"><span data-stu-id="e18c0-121">Registering by using the Azure Portal is the same as for self-service, except you access the portal differently.</span></span> <span data-ttu-id="e18c0-122">Följ anvisningarna nedan:</span><span class="sxs-lookup"><span data-stu-id="e18c0-122">Follow these steps:</span></span>

1. <span data-ttu-id="e18c0-123">Navigera till [Partnercenter](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="e18c0-123">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="e18c0-124">Välj **kunder**.</span><span class="sxs-lookup"><span data-stu-id="e18c0-124">Select **Customers**.</span></span>
3. <span data-ttu-id="e18c0-125">Välj den kund som du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="e18c0-125">Select the customer you want to manage.</span></span>
4. <span data-ttu-id="e18c0-126">Välj **Serviceadministration**.</span><span class="sxs-lookup"><span data-stu-id="e18c0-126">Select **Service Administration**.</span></span>
5. <span data-ttu-id="e18c0-127">Välj **Intune**.</span><span class="sxs-lookup"><span data-stu-id="e18c0-127">Select **Intune**.</span></span>
6. <span data-ttu-id="e18c0-128">Sök efter "mmd" i den övre sökrutan på Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="e18c0-128">Search for "mmd" in the top search box of the Azure portal.</span></span>
7. <span data-ttu-id="e18c0-129">Välj **enheter**.</span><span class="sxs-lookup"><span data-stu-id="e18c0-129">Select **Devices**.</span></span>
8. <span data-ttu-id="e18c0-130">Ange en sökväg till den CSV-fil som du skapade tidigare i **Filuppladdning.**</span><span class="sxs-lookup"><span data-stu-id="e18c0-130">In **File upload**, provide a path to the CSV file you created previously.</span></span>
9. <span data-ttu-id="e18c0-131">Du kan också lägga till ett **order-ID** eller **inköps-ID** för dina egna spårningsändamål.</span><span class="sxs-lookup"><span data-stu-id="e18c0-131">Optionally, you can add an **Order ID** or **Purchase ID** for your own tracking purposes.</span></span> <span data-ttu-id="e18c0-132">Det finns inga formatkrav för dessa värden.</span><span class="sxs-lookup"><span data-stu-id="e18c0-132">There are no format requirements for these values.</span></span>
10. <span data-ttu-id="e18c0-133">Välj **Registrera enheter**.</span><span class="sxs-lookup"><span data-stu-id="e18c0-133">Select **Register devices**.</span></span> <span data-ttu-id="e18c0-134">Systemet lägger till enheterna i listan över enheter på **bladet Enheter**, markerat som **Registreringsväntande**.</span><span class="sxs-lookup"><span data-stu-id="e18c0-134">The system will add the devices to your list of devices on the **Devices blade**, marked as **Registration Pending**.</span></span> <span data-ttu-id="e18c0-135">Registreringen tar vanligtvis mindre än 10 minuter, och när enheten lyckas visas som **klar för användaren,** vilket innebär att den är klar och väntar på att en slutanvändare ska börja använda.</span><span class="sxs-lookup"><span data-stu-id="e18c0-135">Registration typically takes less than 10 minutes, and when successful the device will show as **Ready for user** meaning it's ready and waiting for an end-user to start using.</span></span>


<span data-ttu-id="e18c0-136">Du kan övervaka förloppet för enhetsregistrering på sidan **Microsoft Managed Desktop – Enheter.**</span><span class="sxs-lookup"><span data-stu-id="e18c0-136">You can monitor the progress of device registration on the main **Microsoft Managed Desktop - Devices** page.</span></span> <span data-ttu-id="e18c0-137">Möjliga tillstånd som rapporteras där inkluderar:</span><span class="sxs-lookup"><span data-stu-id="e18c0-137">Possible states reported there include:</span></span>

| <span data-ttu-id="e18c0-138">Statligt</span><span class="sxs-lookup"><span data-stu-id="e18c0-138">State</span></span> | <span data-ttu-id="e18c0-139">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e18c0-139">Description</span></span> |
|---------------|-------------|
| <span data-ttu-id="e18c0-140">Väntande registrering</span><span class="sxs-lookup"><span data-stu-id="e18c0-140">Registration pending</span></span> | <span data-ttu-id="e18c0-141">Registreringen är inte klar än.</span><span class="sxs-lookup"><span data-stu-id="e18c0-141">Registration is not done yet.</span></span> <span data-ttu-id="e18c0-142">Kom tillbaka senare.</span><span class="sxs-lookup"><span data-stu-id="e18c0-142">Check back later.</span></span> |
| <span data-ttu-id="e18c0-143">Registreringen misslyckades</span><span class="sxs-lookup"><span data-stu-id="e18c0-143">Registration failed</span></span> | <span data-ttu-id="e18c0-144">Det gick inte att slutföra registreringen.</span><span class="sxs-lookup"><span data-stu-id="e18c0-144">Registration could not be completed.</span></span> <span data-ttu-id="e18c0-145">Mer information finns i [Felsöka enhetsregistrering.](register-devices-self.md#troubleshooting-device-registration)</span><span class="sxs-lookup"><span data-stu-id="e18c0-145">Refer to [Troubleshooting device registration](register-devices-self.md#troubleshooting-device-registration) for more information.</span></span> |
| <span data-ttu-id="e18c0-146">Redo för användare</span><span class="sxs-lookup"><span data-stu-id="e18c0-146">Ready for user</span></span> | <span data-ttu-id="e18c0-147">Registreringen lyckades och enheten är nu redo att levereras till slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="e18c0-147">Registration succeeded and the device is now ready to be delivered to the end user.</span></span> <span data-ttu-id="e18c0-148">Microsoft Managed Desktop guidar dem genom första gången set-up, så det finns ingen anledning för dig att göra några ytterligare förberedelser.</span><span class="sxs-lookup"><span data-stu-id="e18c0-148">Microsoft Managed Desktop will guide them through first time set-up, so there’s no need for you to do any further preparations.</span></span> |
| <span data-ttu-id="e18c0-149">Aktiva</span><span class="sxs-lookup"><span data-stu-id="e18c0-149">Active</span></span> | <span data-ttu-id="e18c0-150">Enheten har levererats till slutanvändaren och de har registrerat sig hos din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="e18c0-150">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="e18c0-151">Detta indikerar också att de regelbundet använder enheten.</span><span class="sxs-lookup"><span data-stu-id="e18c0-151">This also indicates that they are regularly using the device.</span></span> |
| <span data-ttu-id="e18c0-152">Inaktiva</span><span class="sxs-lookup"><span data-stu-id="e18c0-152">Inactive</span></span> | <span data-ttu-id="e18c0-153">Enheten har levererats till slutanvändaren och de har registrerat sig hos din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="e18c0-153">The device has been delivered to the end user and they have registered with your tenant.</span></span> <span data-ttu-id="e18c0-154">De har dock inte använt enheten nyligen (under de senaste 7 dagarna).</span><span class="sxs-lookup"><span data-stu-id="e18c0-154">However, they have not used the device recently (in the last 7 days).</span></span>  |



## <a name="troubleshooting"></a><span data-ttu-id="e18c0-155">Felsökning</span><span class="sxs-lookup"><span data-stu-id="e18c0-155">Troubleshooting</span></span>

| <span data-ttu-id="e18c0-156">Felmeddelande</span><span class="sxs-lookup"><span data-stu-id="e18c0-156">Error message</span></span> | <span data-ttu-id="e18c0-157">Information</span><span class="sxs-lookup"><span data-stu-id="e18c0-157">Details</span></span> |
|---------------|-------------|
| <span data-ttu-id="e18c0-158">Enheten hittades inte</span><span class="sxs-lookup"><span data-stu-id="e18c0-158">Device not found</span></span> | <span data-ttu-id="e18c0-159">Vi kunde inte registrera den här enheten eftersom vi inte kunde hitta en matchning för den medföljande tillverkaren, modellen eller serienumret.</span><span class="sxs-lookup"><span data-stu-id="e18c0-159">We couldn’t register this device because we could not find a match for the provided manufacturer, model, or serial number.</span></span> <span data-ttu-id="e18c0-160">Bekräfta dessa värden med din enhetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="e18c0-160">Confirm these values with your device supplier.</span></span> |
| <span data-ttu-id="e18c0-161">Maskinvaruhash är ogiltigt</span><span class="sxs-lookup"><span data-stu-id="e18c0-161">Hardware hash not valid</span></span> | <span data-ttu-id="e18c0-162">Maskinvaruhash som du angav för den här enheten har inte formaterats korrekt.</span><span class="sxs-lookup"><span data-stu-id="e18c0-162">The hardware hash you provided for this device was not formatted correctly.</span></span> <span data-ttu-id="e18c0-163">Dubbelkolla maskinvaruhash och skicka sedan in igen.</span><span class="sxs-lookup"><span data-stu-id="e18c0-163">Double-check the hardware hash and then resubmit.</span></span> |
| <span data-ttu-id="e18c0-164">Enheten har redan registrerats</span><span class="sxs-lookup"><span data-stu-id="e18c0-164">Device already registered</span></span> | <span data-ttu-id="e18c0-165">Den här enheten är redan registrerad i din organisation.</span><span class="sxs-lookup"><span data-stu-id="e18c0-165">This device is already registered to your organization.</span></span> <span data-ttu-id="e18c0-166">Inga ytterligare åtgärder krävs.</span><span class="sxs-lookup"><span data-stu-id="e18c0-166">No further action required.</span></span> |
| <span data-ttu-id="e18c0-167">Enhet som en annan organisation har gjort anspråk på</span><span class="sxs-lookup"><span data-stu-id="e18c0-167">Device claimed by another organization</span></span> | <span data-ttu-id="e18c0-168">Den här enheten har redan hävdats av en annan organisation.</span><span class="sxs-lookup"><span data-stu-id="e18c0-168">This device has already been claimed by another organization.</span></span> <span data-ttu-id="e18c0-169">Kontrollera med din enhetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="e18c0-169">Check with your device supplier.</span></span> |
| <span data-ttu-id="e18c0-170">Oväntat fel</span><span class="sxs-lookup"><span data-stu-id="e18c0-170">Unexpected error</span></span> | <span data-ttu-id="e18c0-171">Det gick inte att behandla din begäran automatiskt.</span><span class="sxs-lookup"><span data-stu-id="e18c0-171">Your request could not be automatically processed.</span></span> <span data-ttu-id="e18c0-172">Kontakta supporten (<support link>) och ange begärande-ID:<requestId></span><span class="sxs-lookup"><span data-stu-id="e18c0-172">Contact Support (<support link>) and provide the Request ID: <requestId></span></span> |
