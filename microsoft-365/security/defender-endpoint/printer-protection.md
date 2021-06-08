---
title: Microsoft Defender för Endpoint Device Control Printer Protection
description: Microsoft Defender för Endpoint Device Control Printer Protection blockerar personer från att skriva ut via icke-företagsskrivare eller icke-godkänd USB-skrivare.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: v-lsaldanha
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 431497ded684543c33d91c49a0da47e92297321f
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809325"
---
# <a name="device-control-printer-protection"></a><span data-ttu-id="69fd6-103">Skrivarskydd för enhetskontroll</span><span class="sxs-lookup"><span data-stu-id="69fd6-103">Device Control Printer Protection</span></span> 

<span data-ttu-id="69fd6-104">Microsoft Defender för Endpoint Device Control Printer Protection blockerar personer från att skriva ut via icke-företagsskrivare eller icke-godkänd USB-skrivare.</span><span class="sxs-lookup"><span data-stu-id="69fd6-104">Microsoft Defender for Endpoint Device Control Printer Protection blocks people from printing via non-corporate printers or non-approved USB printer.</span></span>

## <a name="licensing"></a><span data-ttu-id="69fd6-105">Licensiering</span><span class="sxs-lookup"><span data-stu-id="69fd6-105">Licensing</span></span> 

<span data-ttu-id="69fd6-106">Innan du börjar med skrivarskyddet bör du bekräfta din [prenumeration Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="69fd6-106">Before you get started with Printer Protection, you should [confirm your Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1).</span></span> <span data-ttu-id="69fd6-107">För att komma åt och använda skrivarskydd måste du ha följande:</span><span class="sxs-lookup"><span data-stu-id="69fd6-107">To access and use Printer Protection, you must have the following:</span></span>

- <span data-ttu-id="69fd6-108">Microsoft 365 E3 för funktionalitet/principdistribution</span><span class="sxs-lookup"><span data-stu-id="69fd6-108">Microsoft 365 E3 for functionality/policy deployment</span></span> 
- <span data-ttu-id="69fd6-109">Microsoft 365 E5 för rapportering</span><span class="sxs-lookup"><span data-stu-id="69fd6-109">Microsoft 365 E5 for reporting</span></span> 

## <a name="permission"></a><span data-ttu-id="69fd6-110">Behörighet</span><span class="sxs-lookup"><span data-stu-id="69fd6-110">Permission</span></span> 

<span data-ttu-id="69fd6-111">För principdistribution i Intune måste kontot ha behörighet att skapa, redigera, uppdatera eller ta bort enhetskonfigurationsprofiler för att distribuera principen via OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="69fd6-111">For Policy deployment in Intune, to deploy policy via OMA-URI, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="69fd6-112">Du kan skapa anpassade roller eller använda någon av de inbyggda rollerna med följande behörigheter:</span><span class="sxs-lookup"><span data-stu-id="69fd6-112">You can create custom roles or use any of the built-in roles with these permissions:</span></span>  

- <span data-ttu-id="69fd6-113">Rollen Princip och profilhanterare.</span><span class="sxs-lookup"><span data-stu-id="69fd6-113">Policy and profile Manager role.</span></span> 
- <span data-ttu-id="69fd6-114">Eller en anpassad roll med behörigheten Skapa/redigera/uppdatera/Läsa/Ta bort/Visa rapporter aktiverad för enhetskonfigurationsprofiler</span><span class="sxs-lookup"><span data-stu-id="69fd6-114">Or custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>  
- <span data-ttu-id="69fd6-115">Eller global administratör</span><span class="sxs-lookup"><span data-stu-id="69fd6-115">Or Global admin</span></span>

<span data-ttu-id="69fd6-116">För att kunna se enhetkonfigurationsrapporter måste kontot ha behörighet att visa rapporter.</span><span class="sxs-lookup"><span data-stu-id="69fd6-116">To see device configuration reports, the account must have view reports permissions.</span></span> <span data-ttu-id="69fd6-117">Du kan skapa anpassade roller eller använda de inbyggda rollerna med följande behörigheter:</span><span class="sxs-lookup"><span data-stu-id="69fd6-117">You can create custom roles or use the built-in roles with these permissions:</span></span>  

- <span data-ttu-id="69fd6-118">Global säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="69fd6-118">Global security admin</span></span>
- <span data-ttu-id="69fd6-119">Säkerhetsadministratör</span><span class="sxs-lookup"><span data-stu-id="69fd6-119">Security admin</span></span>
- <span data-ttu-id="69fd6-120">Säkerhetsläsare</span><span class="sxs-lookup"><span data-stu-id="69fd6-120">Security Reader</span></span> 

## <a name="prepare-your-endpoints"></a><span data-ttu-id="69fd6-121">Förbered dina slutpunkter</span><span class="sxs-lookup"><span data-stu-id="69fd6-121">Prepare your endpoints</span></span>

<span data-ttu-id="69fd6-122">Kontrollera att de Windows 10 som du planerar att distribuera skrivarskydd för att uppfylla dessa krav.</span><span class="sxs-lookup"><span data-stu-id="69fd6-122">Make sure that the Windows 10 devices that you plan on deploying Printer Protection to meet these requirements.</span></span>

1. <span data-ttu-id="69fd6-123">Gå med i Insider Program.</span><span class="sxs-lookup"><span data-stu-id="69fd6-123">Join the Insider Program.</span></span>

1. <span data-ttu-id="69fd6-124">Följande Windows-uppdateringar installeras.</span><span class="sxs-lookup"><span data-stu-id="69fd6-124">The following Windows Updates are installed.</span></span> 

    - <span data-ttu-id="69fd6-125">För Windows 1809: installera Windows [KB5003217](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span><span class="sxs-lookup"><span data-stu-id="69fd6-125">For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)</span></span> 
    - <span data-ttu-id="69fd6-126">För Windows 1909: installera Windows [KB5003212](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span><span class="sxs-lookup"><span data-stu-id="69fd6-126">For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/en-us/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)</span></span>
    - <span data-ttu-id="69fd6-127">För Windows 2004 eller senare</span><span class="sxs-lookup"><span data-stu-id="69fd6-127">For Windows 2004 or later</span></span> 
    
1. <span data-ttu-id="69fd6-128">Om du planerar att distribuera principen via Grupprincip måste enheten vara ansluten MDATP. Om du planerar att distribuera principen via MEM måste enheten vara intune ansluten.</span><span class="sxs-lookup"><span data-stu-id="69fd6-128">If you're planning to deploy policy via Group Policy, the device must be MDATP joined; if you're planning to deploy policy via MEM, the device must be Intune joined.</span></span>

## <a name="deploy-device-control-printer-protection-policy"></a><span data-ttu-id="69fd6-129">Princip för skrivarskydd för enhetskontroll</span><span class="sxs-lookup"><span data-stu-id="69fd6-129">Deploy Device Control Printer Protection policy</span></span>

<span data-ttu-id="69fd6-130">Du kan distribuera principen via Grupprincip eller Intune.</span><span class="sxs-lookup"><span data-stu-id="69fd6-130">You can deploy the policy via Group Policy or Intune.</span></span>

| <span data-ttu-id="69fd6-131">Title</span><span class="sxs-lookup"><span data-stu-id="69fd6-131">Title</span></span> | <span data-ttu-id="69fd6-132">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="69fd6-132">Description</span></span> | <span data-ttu-id="69fd6-133">Stöd för CSP</span><span class="sxs-lookup"><span data-stu-id="69fd6-133">CSP Support</span></span> | <span data-ttu-id="69fd6-134">GPO-support</span><span class="sxs-lookup"><span data-stu-id="69fd6-134">GPO Support</span></span> | <span data-ttu-id="69fd6-135">Användarbaserad support</span><span class="sxs-lookup"><span data-stu-id="69fd6-135">User-based Support</span></span> | <span data-ttu-id="69fd6-136">Maskinbaserad support</span><span class="sxs-lookup"><span data-stu-id="69fd6-136">Machine-based Support</span></span> |
|:--|:--|:--|:--|:--|:--|
|<span data-ttu-id="69fd6-137">**Aktivera enhetskontrollens utskriftsbegränsningar**</span><span class="sxs-lookup"><span data-stu-id="69fd6-137">**Enable Device control Printing Restrictions**</span></span>|<span data-ttu-id="69fd6-138">Blockera personer från att skriva ut via skrivare som inte finns i företaget</span><span class="sxs-lookup"><span data-stu-id="69fd6-138">Block people from printing via non-corporate printer</span></span>|<span data-ttu-id="69fd6-139">Ja</span><span class="sxs-lookup"><span data-stu-id="69fd6-139">Yes</span></span>|<span data-ttu-id="69fd6-140">Ja</span><span class="sxs-lookup"><span data-stu-id="69fd6-140">Yes</span></span>|<span data-ttu-id="69fd6-141">Ja</span><span class="sxs-lookup"><span data-stu-id="69fd6-141">Yes</span></span>|<span data-ttu-id="69fd6-142">Ja</span><span class="sxs-lookup"><span data-stu-id="69fd6-142">Yes</span></span>|
|<span data-ttu-id="69fd6-143">**Lista över godkända USB-anslutna utskriftsenheter**\*</span><span class="sxs-lookup"><span data-stu-id="69fd6-143">**List of Approved USB-connected print devices** \*</span></span>|<span data-ttu-id="69fd6-144">Tillåt specifik USB-skrivare</span><span class="sxs-lookup"><span data-stu-id="69fd6-144">Allow specific USB printer</span></span>|<span data-ttu-id="69fd6-145">Ja</span><span class="sxs-lookup"><span data-stu-id="69fd6-145">Yes</span></span>|<span data-ttu-id="69fd6-146">Ja</span><span class="sxs-lookup"><span data-stu-id="69fd6-146">Yes</span></span>|<span data-ttu-id="69fd6-147">Ja</span><span class="sxs-lookup"><span data-stu-id="69fd6-147">Yes</span></span>|<span data-ttu-id="69fd6-148">Ja</span><span class="sxs-lookup"><span data-stu-id="69fd6-148">Yes</span></span>|
|||||||

<span data-ttu-id="69fd6-149">\* Den här principen måste användas tillsammans med **Aktivera utskriftsbegränsningar för enhetskontroller**</span><span class="sxs-lookup"><span data-stu-id="69fd6-149">\* This policy must be used together with **Enable Device control Printing Restrictions**</span></span>
## <a name="deploy-policy-via-intune"></a><span data-ttu-id="69fd6-150">Distribuera princip via Intune</span><span class="sxs-lookup"><span data-stu-id="69fd6-150">Deploy policy via Intune</span></span> 

<span data-ttu-id="69fd6-151">För Intune stöder för närvarande Device Control Printer Protection ENDAST OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="69fd6-151">For Intune, currently Device Control Printer Protection supports OMA-URI only.</span></span>

<span data-ttu-id="69fd6-152">**Scenario 1: Blockera personer från att skriva ut via en skrivare som inte finns i företaget**</span><span class="sxs-lookup"><span data-stu-id="69fd6-152">**Scenario 1: Block people from printing via any non-corporate printer**</span></span> 

 - <span data-ttu-id="69fd6-153">Tillämpa principen på datorn:</span><span class="sxs-lookup"><span data-stu-id="69fd6-153">Apply policy over machine:</span></span> 

    - <span data-ttu-id="69fd6-154">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl</span><span class="sxs-lookup"><span data-stu-id="69fd6-154">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl</span></span> 

- <span data-ttu-id="69fd6-155">Tillämpa princip över användare:</span><span class="sxs-lookup"><span data-stu-id="69fd6-155">Apply policy over user:</span></span> 

    - <span data-ttu-id="69fd6-156">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser</span><span class="sxs-lookup"><span data-stu-id="69fd6-156">./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser</span></span> 

<span data-ttu-id="69fd6-157">CSP-supportsträngen `` <enabled/>`` med:</span><span class="sxs-lookup"><span data-stu-id="69fd6-157">The CSP support string with `` <enabled/>``:</span></span> 

:::image type="content" source="../../media/customeditrow.png" alt-text="anpassad redigeringsrad":::

<span data-ttu-id="69fd6-159">**Scenario 2: Tillåta specifika godkända USB-skrivare**</span><span class="sxs-lookup"><span data-stu-id="69fd6-159">**Scenario 2: Allow specific approved USB printers**</span></span>

- <span data-ttu-id="69fd6-160">Tillämpa principen på datorn:</span><span class="sxs-lookup"><span data-stu-id="69fd6-160">Apply policy over machine:</span></span> 

    - <span data-ttu-id="69fd6-161">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices</span><span class="sxs-lookup"><span data-stu-id="69fd6-161">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices</span></span> 

- <span data-ttu-id="69fd6-162">Tillämpa princip över användare:</span><span class="sxs-lookup"><span data-stu-id="69fd6-162">Apply policy over user:</span></span> 

    - <span data-ttu-id="69fd6-163">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser</span><span class="sxs-lookup"><span data-stu-id="69fd6-163">./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser</span></span>  

<span data-ttu-id="69fd6-164">CSP-supportsträngen med godkända USB-skrivare via egenskapen ApprovedUsbPrintDevices, till `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>`` exempel:</span><span class="sxs-lookup"><span data-stu-id="69fd6-164">The CSP support string with approved USB printers via ‘ApprovedUsbPrintDevices’ property, example `` <enabled/><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872"/>``:</span></span> 

:::image type="content" source="../../media/editrow.png" alt-text="redigera rad":::

## <a name="deploy-policy-via-group-policy"></a><span data-ttu-id="69fd6-166">Distribuera princip via grupprincip</span><span class="sxs-lookup"><span data-stu-id="69fd6-166">Deploy policy via Group Policy</span></span> 

<span data-ttu-id="69fd6-167">Om enheten inte är Intune ansluten kan du även distribuera principen via Grupprincip.</span><span class="sxs-lookup"><span data-stu-id="69fd6-167">If the device isn't Intune joined, you can also deploy the policy via Group Policy.</span></span> 

<span data-ttu-id="69fd6-168">**Scenario 1: Blockera personer från att skriva ut via en skrivare som inte finns i företaget**</span><span class="sxs-lookup"><span data-stu-id="69fd6-168">**Scenario 1: Block people from printing via any non-corporate printer**</span></span> 

- <span data-ttu-id="69fd6-169">Tillämpa principen på datorn:</span><span class="sxs-lookup"><span data-stu-id="69fd6-169">Apply policy over machine:</span></span> 

    - <span data-ttu-id="69fd6-170">Datorkonfiguration > administrativa mallar > skrivare: Aktivera begränsningar för enhetsstyrning vid utskrift</span><span class="sxs-lookup"><span data-stu-id="69fd6-170">Computer Configuration > Administrative Templates > Printer: Enable Device control Printing Restrictions</span></span> 

- <span data-ttu-id="69fd6-171">Tillämpa princip över användare:</span><span class="sxs-lookup"><span data-stu-id="69fd6-171">Apply policy over user:</span></span> 

    - <span data-ttu-id="69fd6-172">Användarkonfiguration > Administrativa mallar > På Kontrollpanelen > Skrivare: Aktivera utskriftsbegränsningar för enhetskontroller</span><span class="sxs-lookup"><span data-stu-id="69fd6-172">User Configuration > Administrative Templates > Control Panel > Printers: Enable Device control Printing Restrictions</span></span> 

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="aktivera begränsningar för utskrift av enheter":::
 

<span data-ttu-id="69fd6-174">**Scenario 2: Tillåta specifika godkända USB-skrivare**</span><span class="sxs-lookup"><span data-stu-id="69fd6-174">**Scenario 2: Allow specific approved USB printers**</span></span>

- <span data-ttu-id="69fd6-175">Tillämpa principen på datorn:</span><span class="sxs-lookup"><span data-stu-id="69fd6-175">Apply policy over machine:</span></span> 

    - <span data-ttu-id="69fd6-176">Datorkonfiguration > administrationsmallar > skrivare: Lista över godkända USB-anslutna utskriftsenheter</span><span class="sxs-lookup"><span data-stu-id="69fd6-176">Computer Configuration > Administrative Templates > Printer:  List of Approved USB-connected print devices</span></span> 

- <span data-ttu-id="69fd6-177">Tillämpa princip över användare:</span><span class="sxs-lookup"><span data-stu-id="69fd6-177">Apply policy over user:</span></span>  

    - <span data-ttu-id="69fd6-178">Användarkonfiguration > Administrationsmallar > Kontrollpanelen > Skrivare: Lista över godkända USB-anslutna utskriftsenheter</span><span class="sxs-lookup"><span data-stu-id="69fd6-178">User Configuration > Administrative Templates > Control Panel > Printers: List of Approved USB-connected print devices</span></span> 
 
 :::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="lista över godkända USB-anslutna utskriftsenheter":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a><span data-ttu-id="69fd6-180">Visa data om skrivarskydd för enhetskontroll i Microsoft Defender för Endpoint-portalen</span><span class="sxs-lookup"><span data-stu-id="69fd6-180">View Device Control Printer Protection data in Microsoft Defender for Endpoint portal</span></span> 

<span data-ttu-id="69fd6-181">På [Microsoft 365 säkerhetscenter visas](https://security.microsoft.com) utskrift som blockerats av principen för skrivarskydd för enhetskontroll ovan.</span><span class="sxs-lookup"><span data-stu-id="69fd6-181">The [Microsoft 365 security center](https://security.microsoft.com) shows printing blocked by the Device Control Printer Protection policy above.</span></span>
 
```sql
DeviceEvents 

|where ActionType == 'PrintJobBlocked' 

| extend parsed=parse_json(AdditionalFields) 

| extend PrintedFile=tostring(parsed.JobOrDocumentName) 

| extend PrintPortName=tostring(parsed.PortName) 

| extend PrinterName=tostring(parsed.PrinterName) 

| extend Policy=tostring(parsed.RestrictionReason)  

| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName,Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields 

| order by Timestamp desc 
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="avancerad sökning":::
