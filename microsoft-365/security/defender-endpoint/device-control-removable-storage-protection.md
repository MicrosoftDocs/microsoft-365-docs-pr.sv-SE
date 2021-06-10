---
title: Flyttbara enheter i Microsoft Defender för Endpoint Device Control Storage Protection
description: Förstå "funktioner som förhindrar användare eller dator eller både och från att använda obehöriga flyttbara lagringsmedia
keywords: flyttbart lagringsmedia
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-smandalika
author: v-smandalika
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 55171429d3ea447de32eb7e2ec12b8b2c3542e95
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861713"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-protection"></a><span data-ttu-id="b5073-104">Flyttbara enheter i Microsoft Defender för Endpoint Device Control Storage Protection</span><span class="sxs-lookup"><span data-stu-id="b5073-104">Microsoft Defender for Endpoint Device Control Removable Storage Protection</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="b5073-105">Microsoft Defender för Endpoint Device Control flyttbart Storage skydd förhindrar användare eller dator eller båda från att använda obehöriga flyttbara lagringsmedia.</span><span class="sxs-lookup"><span data-stu-id="b5073-105">Microsoft Defender for Endpoint Device Control Removable Storage Protection prevents user or machine or both from using unauthorized removable storage media.</span></span>

## <a name="protection-policies"></a><span data-ttu-id="b5073-106">Skyddsprinciper</span><span class="sxs-lookup"><span data-stu-id="b5073-106">Protection policies</span></span>

### <a name="device-installation"></a><span data-ttu-id="b5073-107">Enhetsinstallation</span><span class="sxs-lookup"><span data-stu-id="b5073-107">Device installation</span></span>

<span data-ttu-id="b5073-108">**Funktioner –** Förhindra installation med eller utan undantag baserat på olika enhetsegenskaper.</span><span class="sxs-lookup"><span data-stu-id="b5073-108">**Capabilities** - Prevent installation with or without exclusion based on various device properties.</span></span>

<span data-ttu-id="b5073-109">**Windows 10 supportinformation**</span><span class="sxs-lookup"><span data-stu-id="b5073-109">**Windows 10 support details**</span></span>
- <span data-ttu-id="b5073-110">Används på maskinnivå: samma princip gäller för alla inloggade användare.</span><span class="sxs-lookup"><span data-stu-id="b5073-110">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="b5073-111">Stöd för MEM och GPO.</span><span class="sxs-lookup"><span data-stu-id="b5073-111">Supports MEM and GPO.</span></span>
- <span data-ttu-id="b5073-112">' Device[Properties '](#device-properties)as listed.</span><span class="sxs-lookup"><span data-stu-id="b5073-112">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="b5073-113">Mer information om hur Windows finns i Styra USB-enheter och andra [flyttbara medium med hjälp av Microsoft Defender för slutpunkt.](control-usb-devices-using-intune.md)</span><span class="sxs-lookup"><span data-stu-id="b5073-113">For more information on Windows, see [How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md).</span></span>

<span data-ttu-id="b5073-114">**Plattform som stöds** – Windows 10</span><span class="sxs-lookup"><span data-stu-id="b5073-114">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="b5073-115">**supportinformation för macOS**</span><span class="sxs-lookup"><span data-stu-id="b5073-115">**macOS support details**</span></span>
- <span data-ttu-id="b5073-116">Används på maskinnivå: samma princip gäller för alla inloggade användare</span><span class="sxs-lookup"><span data-stu-id="b5073-116">Applied at machine level: the same policy applies for any logged on user</span></span>
- <span data-ttu-id="b5073-117">Specifik information för macOS finns i [Enhetskontroll för macOS.](mac-device-control-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b5073-117">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="b5073-118">**Plattform som** stöds – macOS Catalina 10.15.4+ (med systemtillägg aktiverade)</span><span class="sxs-lookup"><span data-stu-id="b5073-118">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="removable-storage-access-control"></a><span data-ttu-id="b5073-119">Åtkomstkontroll för flyttbara lagringsmedia</span><span class="sxs-lookup"><span data-stu-id="b5073-119">Removable storage Access Control</span></span>

<span data-ttu-id="b5073-120">**Kapaciteter**</span><span class="sxs-lookup"><span data-stu-id="b5073-120">**Capabilities**</span></span>
- <span data-ttu-id="b5073-121">*Granskning* Läsa eller skriva eller köra åtkomst till flyttbart lagringsutrymme baserat på olika enhetsegenskaper, med eller utan undantag.</span><span class="sxs-lookup"><span data-stu-id="b5073-121">*Audit* Read or Write or Execute access to removable storage based on various device properties, with or without an exclusion.</span></span>
- <span data-ttu-id="b5073-122">*Förhindra* Läsa eller skriva eller köra åtkomst med eller utan undantag – Tillåt specifik enhet baserat på olika enhetsegenskaper.</span><span class="sxs-lookup"><span data-stu-id="b5073-122">*Prevent* Read or Write or Execute access with or without an exclusion - Allow specific device based on various device properties.</span></span>

<span data-ttu-id="b5073-123">**Windows 10 supportinformation**</span><span class="sxs-lookup"><span data-stu-id="b5073-123">**Windows 10 support details**</span></span>
- <span data-ttu-id="b5073-124">Används på antingen datorn eller användaren eller både och – tillåt endast vissa personer som utför läs-/skriv-/kör åtkomst till specifik flyttbar lagring på en viss dator.</span><span class="sxs-lookup"><span data-stu-id="b5073-124">Applied at either machine or user or both – only allow specific people performing Read/Write/Execute access to specific removable storage on specific machine.</span></span>
- <span data-ttu-id="b5073-125">Stöd för MEM OMA-URI och GPO.</span><span class="sxs-lookup"><span data-stu-id="b5073-125">Support MEM OMA-URI and GPO.</span></span>
- <span data-ttu-id="b5073-126">' Device[Properties '](#device-properties)as listed.</span><span class="sxs-lookup"><span data-stu-id="b5073-126">Supported  ‘[Device Properties](#device-properties)’ as listed.</span></span>
- <span data-ttu-id="b5073-127">Information om funktionen Windows finns i [Ta bort åtkomstkontroll för flyttbara lagringsmedia.](device-control-removable-storage-access-control.md)</span><span class="sxs-lookup"><span data-stu-id="b5073-127">For feature in Windows, see [Removable storage Access Control](device-control-removable-storage-access-control.md).</span></span>

<span data-ttu-id="b5073-128">**Plattform som stöds** – Windows 10</span><span class="sxs-lookup"><span data-stu-id="b5073-128">**Supported Platform** - Windows 10</span></span>

<span data-ttu-id="b5073-129">**supportinformation för macOS**</span><span class="sxs-lookup"><span data-stu-id="b5073-129">**macOS support details**</span></span>
- <span data-ttu-id="b5073-130">Används på maskinnivå: samma princip gäller för alla inloggade användare.</span><span class="sxs-lookup"><span data-stu-id="b5073-130">Applied at machine level: the same policy applies for any logged on user.</span></span>
- <span data-ttu-id="b5073-131">Specifik information för macOS finns i [Enhetskontroll för macOS.](mac-device-control-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b5073-131">For macOS specific information, see [Device control for macOS](mac-device-control-overview.md).</span></span>
 
<span data-ttu-id="b5073-132">**Plattform som** stöds – macOS Catalina 10.15.4+ (med systemtillägg aktiverade)</span><span class="sxs-lookup"><span data-stu-id="b5073-132">**Supported platform** - macOS Catalina 10.15.4+ (with system extensions enabled)</span></span>

### <a name="windows-portable-device-access-control"></a><span data-ttu-id="b5073-133">Windows Åtkomstkontroll för bärbar enhet</span><span class="sxs-lookup"><span data-stu-id="b5073-133">Windows Portable Device Access Control</span></span>

<span data-ttu-id="b5073-134">**Funktioner –** Neka läs- eller skrivåtkomst till valfri [bärbar Windows,](/windows-hardware/drivers/portable/)till exempel: surfplatta, iPhone.</span><span class="sxs-lookup"><span data-stu-id="b5073-134">**Capabilities** - Deny Read or Write access to any [Windows Portable Device](/windows-hardware/drivers/portable/), for example: Tablet, iPhone.</span></span>

<span data-ttu-id="b5073-135">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="b5073-135">**Description**</span></span>
- <span data-ttu-id="b5073-136">Används på antingen datorn eller användaren eller båda.</span><span class="sxs-lookup"><span data-stu-id="b5073-136">Applied at either machine or user or both.</span></span>
- <span data-ttu-id="b5073-137">Stöd för MEM OMA-URI och GPO.</span><span class="sxs-lookup"><span data-stu-id="b5073-137">Support MEM OMA-URI and GPO.</span></span>

<span data-ttu-id="b5073-138">**Plattform som stöds** – Windows 10</span><span class="sxs-lookup"><span data-stu-id="b5073-138">**Supported Platform** - Windows 10</span></span>

### <a name="endpoint-dlp-removable-storage"></a><span data-ttu-id="b5073-139">Slutpunkt DLP, flyttbar lagring</span><span class="sxs-lookup"><span data-stu-id="b5073-139">Endpoint DLP Removable storage</span></span>

<span data-ttu-id="b5073-140">**Funktioner –** Granska eller Varna eller Förhindra en användare från att kopiera ett objekt eller information till ett flyttbart medium eller EN USB-enhet.</span><span class="sxs-lookup"><span data-stu-id="b5073-140">**Capabilities** - Audit or Warn or Prevent a user from copying an item or information to removable media or USB device.</span></span>

<span data-ttu-id="b5073-141">**Beskrivning** – Mer information om Windows finns i Läs [mer Microsoft 365 skydd mot dataförlust i Slutpunkt](../../compliance/endpoint-dlp-learn-about.md).</span><span class="sxs-lookup"><span data-stu-id="b5073-141">**Description** - For more information on Windows, see [Learn about Microsoft 365 Endpoint data loss prevention](../../compliance/endpoint-dlp-learn-about.md).</span></span>

<span data-ttu-id="b5073-142">**Plattform som stöds** – Windows 10</span><span class="sxs-lookup"><span data-stu-id="b5073-142">**Supported Platform** - Windows 10</span></span>

### <a name="bitlocker"></a><span data-ttu-id="b5073-143">BitLocker</span><span class="sxs-lookup"><span data-stu-id="b5073-143">BitLocker</span></span> 

<span data-ttu-id="b5073-144">**Kapaciteter**</span><span class="sxs-lookup"><span data-stu-id="b5073-144">**Capabilities**</span></span>
- <span data-ttu-id="b5073-145">Blockera data som ska skrivas till flyttbara enheter som inte BitLocker skyddade.</span><span class="sxs-lookup"><span data-stu-id="b5073-145">Block data to be written to removable drives that aren't BitLocker protected.</span></span>
- <span data-ttu-id="b5073-146">Blockera åtkomst till flyttbara enheter såvida de inte krypterats på en dator som ägs av din organisation</span><span class="sxs-lookup"><span data-stu-id="b5073-146">Block access to removable drives unless they were encrypted on a computer owned by your organization</span></span>
 
<span data-ttu-id="b5073-147">**Beskrivning** – Mer information om hur du Windows finns i [BitLocker – Flyttbar enhet Inställningar](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).</span><span class="sxs-lookup"><span data-stu-id="b5073-147">**Description** - For more information on Windows, see [BitLocker – Removable Drive Settings](/mem/intune/protect/endpoint-security-disk-encryption-profile-settings).</span></span>

<span data-ttu-id="b5073-148">**Plattform som stöds** – Windows 10</span><span class="sxs-lookup"><span data-stu-id="b5073-148">**Supported Platform** - Windows 10</span></span>

## <a name="device-properties"></a><span data-ttu-id="b5073-149">Enhetsegenskaper</span><span class="sxs-lookup"><span data-stu-id="b5073-149">Device properties</span></span>

<span data-ttu-id="b5073-150">Med Microsoft Defender för Endpoint Device Control flyttbart Storage Protection kan du begränsa åtkomsten till det flyttbara lagringsutrymmet baserat på de egenskaper som beskrivs i tabellen nedan:</span><span class="sxs-lookup"><span data-stu-id="b5073-150">Microsoft Defender for Endpoint Device Control Removable Storage Protection allows you to restrict the removable storage access based on the properties described in the table below:</span></span>


|<span data-ttu-id="b5073-151">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="b5073-151">Property Name</span></span>  |<span data-ttu-id="b5073-152">Tillämpliga principer</span><span class="sxs-lookup"><span data-stu-id="b5073-152">Applicable Policies</span></span>  |<span data-ttu-id="b5073-153">Gäller för operativsystem</span><span class="sxs-lookup"><span data-stu-id="b5073-153">Applies to Operating Systems</span></span>  |<span data-ttu-id="b5073-154">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="b5073-154">Description</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="b5073-155">Enhetsklass</span><span class="sxs-lookup"><span data-stu-id="b5073-155">Device Class</span></span>    |     [<span data-ttu-id="b5073-156">Styra USB-enheter och andra flyttbara medium med Hjälp av Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b5073-156">How to control USB devices and other removable media using Microsoft Defender for Endpoint</span></span>](control-usb-devices-using-intune.md)     |   <span data-ttu-id="b5073-157">Windows</span><span class="sxs-lookup"><span data-stu-id="b5073-157">Windows</span></span>      |  <span data-ttu-id="b5073-158">Mer information om enhets-ID-format finns i [enhetskonfigurationsklassen](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).</span><span class="sxs-lookup"><span data-stu-id="b5073-158">For information about Device ID formats, see [device setup class](/windows-hardware/drivers/install/system-defined-device-setup-classes-available-to-vendors).</span></span> <span data-ttu-id="b5073-159">**Obs!** Enhetsinstallation kan tillämpas på alla enheter, inte bara på flyttbart lagringsutrymme.</span><span class="sxs-lookup"><span data-stu-id="b5073-159">**Note**: Device Installation can be applied to any devices, not only Removable storage.</span></span>       |
|<span data-ttu-id="b5073-160">Primärt ID</span><span class="sxs-lookup"><span data-stu-id="b5073-160">Primary ID</span></span>   |     <span data-ttu-id="b5073-161">Åtkomstkontroll för flyttbara lagringsmedia</span><span class="sxs-lookup"><span data-stu-id="b5073-161">Removable storage Access Control</span></span>    |   <span data-ttu-id="b5073-162">Windows</span><span class="sxs-lookup"><span data-stu-id="b5073-162">Windows</span></span>      |      <span data-ttu-id="b5073-163">Det primära ID:t omfattar flyttbart lagringsutrymme och CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="b5073-163">The Primary ID includes removable storage and CD/DVD.</span></span>   |
|<span data-ttu-id="b5073-164">Enhets-ID</span><span class="sxs-lookup"><span data-stu-id="b5073-164">Device ID</span></span>     |  <span data-ttu-id="b5073-165">[Styra USB-enheter och andra flyttbara medium med Hjälp av Microsoft Defender för Slutpunkt](control-usb-devices-using-intune.md); Åtkomstkontroll för flyttbara lagringsmedia</span><span class="sxs-lookup"><span data-stu-id="b5073-165">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>       |      <span data-ttu-id="b5073-166">Windows</span><span class="sxs-lookup"><span data-stu-id="b5073-166">Windows</span></span>   |    <span data-ttu-id="b5073-167">Mer information om enhets-ID-format finns [i Standard-USB-identifierare,](/windows-hardware/drivers/install/standard-usb-identifiers)till exempel USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span><span class="sxs-lookup"><span data-stu-id="b5073-167">For information about Device ID formats, see [Standard USB Identifiers](/windows-hardware/drivers/install/standard-usb-identifiers), for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07</span></span>      |
|<span data-ttu-id="b5073-168">Maskinvaru-ID</span><span class="sxs-lookup"><span data-stu-id="b5073-168">Hardware ID</span></span>     |     <span data-ttu-id="b5073-169">[Styra USB-enheter och andra flyttbara medium med Hjälp av Microsoft Defender för Slutpunkt](control-usb-devices-using-intune.md); Åtkomstkontroll för flyttbara lagringsmedia</span><span class="sxs-lookup"><span data-stu-id="b5073-169">[How to control USB devices and other removable media using Microsoft Defender for Endpoint](control-usb-devices-using-intune.md); Removable storage Access Control</span></span>    |     <span data-ttu-id="b5073-170">Windows</span><span class="sxs-lookup"><span data-stu-id="b5073-170">Windows</span></span>    |    <span data-ttu-id="b5073-171">En sträng som identifieras av enheten i systemet, till exempel USBSTOR\DiskGeneric_Flash_Disk______8.07; **Obs!** Maskinvaru-ID är inte unikt. olika enheter kan ha samma värde.</span><span class="sxs-lookup"><span data-stu-id="b5073-171">A string identified the device in the system, for example, USBSTOR\DiskGeneric_Flash_Disk______8.07; **Note**: Hardware ID is not unique; different devices may share same value.</span></span>|
|<span data-ttu-id="b5073-172">Instans-ID</span><span class="sxs-lookup"><span data-stu-id="b5073-172">Instance ID</span></span>    | <span data-ttu-id="b5073-173">Enhetsinstallation; Åtkomstkontroll för flyttbara lagringsmedia</span><span class="sxs-lookup"><span data-stu-id="b5073-173">Device Installation; Removable storage Access Control</span></span>     |     <span data-ttu-id="b5073-174">Windows</span><span class="sxs-lookup"><span data-stu-id="b5073-174">Windows</span></span>    |   <span data-ttu-id="b5073-175">En sträng identifierar unikt enheten i systemet, till exempel USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span><span class="sxs-lookup"><span data-stu-id="b5073-175">A string uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0</span></span>      |
|<span data-ttu-id="b5073-176">Eget namn</span><span class="sxs-lookup"><span data-stu-id="b5073-176">Friendly Name</span></span>     |     <span data-ttu-id="b5073-177">Åtkomstkontroll för flyttbara lagringsmedia</span><span class="sxs-lookup"><span data-stu-id="b5073-177">Removable storage Access Control</span></span>    |   <span data-ttu-id="b5073-178">Windows</span><span class="sxs-lookup"><span data-stu-id="b5073-178">Windows</span></span>      |    <span data-ttu-id="b5073-179">En sträng ansluten till enheten, till exempel allmän FLASH USB-enhet</span><span class="sxs-lookup"><span data-stu-id="b5073-179">A string attached to the device, for example, Generic Flash Disk USB Device</span></span>     |
|<span data-ttu-id="b5073-180">Leverantörs-ID/produkt-ID</span><span class="sxs-lookup"><span data-stu-id="b5073-180">Vendor ID / Product ID</span></span>     |  <span data-ttu-id="b5073-181">Åtkomstkontroll för flyttbara lagringsmedia</span><span class="sxs-lookup"><span data-stu-id="b5073-181">Removable storage Access Control</span></span>       |   <span data-ttu-id="b5073-182">Windows Mac</span><span class="sxs-lookup"><span data-stu-id="b5073-182">Windows Mac</span></span>      |     <span data-ttu-id="b5073-183">Leverantörs-ID är den fyrsiffriga leverantörskod som USB-kommittéen tilldelar leverantören.</span><span class="sxs-lookup"><span data-stu-id="b5073-183">Vendor ID is the four-digit vendor code that the USB committee assigns to the vendor.</span></span> <span data-ttu-id="b5073-184">Produkt-ID är den fyrsiffriga produktkod som leverantören tilldelar till enheten. Stöd för jokertecken.</span><span class="sxs-lookup"><span data-stu-id="b5073-184">Product ID is the four-digit product code that the vendor assigns to the device; Support wildcard.</span></span>    |
|<span data-ttu-id="b5073-185">Serienummer</span><span class="sxs-lookup"><span data-stu-id="b5073-185">Serial NumberId</span></span>     |     <span data-ttu-id="b5073-186">Åtkomstkontroll för flyttbara lagringsmedia</span><span class="sxs-lookup"><span data-stu-id="b5073-186">Removable storage Access Control</span></span>    |      <span data-ttu-id="b5073-187">Windows Mac</span><span class="sxs-lookup"><span data-stu-id="b5073-187">Windows Mac</span></span>   |     <span data-ttu-id="b5073-188">Exempel: <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span><span class="sxs-lookup"><span data-stu-id="b5073-188">For example, <SerialNumberId>002324B534BCB431B000058A</SerialNumberId></span></span>    |

## <a name="related-topic"></a><span data-ttu-id="b5073-189">Relaterat ämne</span><span class="sxs-lookup"><span data-stu-id="b5073-189">Related topic</span></span>

- [<span data-ttu-id="b5073-190">Microsoft Defender för endpoint-enhetskontroll, flyttbar Storage access-kontroll</span><span class="sxs-lookup"><span data-stu-id="b5073-190">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>](device-control-removable-storage-access-control.md)

