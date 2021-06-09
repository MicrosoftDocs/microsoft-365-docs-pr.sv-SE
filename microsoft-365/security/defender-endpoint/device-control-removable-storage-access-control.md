---
title: Microsoft Defender för endpoint-enhetskontroll, flyttbar Storage access-kontroll
description: En genomgång om Microsoft Defender för Endpoint
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
ms.openlocfilehash: fba74990d8e4465f957acda83e66e1dc43a317e8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841192"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="d3d00-104">Microsoft Defender för endpoint-enhetskontroll, flyttbar Storage access-kontroll</span><span class="sxs-lookup"><span data-stu-id="d3d00-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="d3d00-105">Med Microsoft Defender för Endpoint Device Control Storage och Access Control kan du göra följande:</span><span class="sxs-lookup"><span data-stu-id="d3d00-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>
- <span data-ttu-id="d3d00-106">granska, tillåta eller förhindra läsning, skriva eller köra åtkomst till flyttbara lagringsmedia med eller utan undantag</span><span class="sxs-lookup"><span data-stu-id="d3d00-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="d3d00-107">Behörighet</span><span class="sxs-lookup"><span data-stu-id="d3d00-107">Privilege</span></span> |<span data-ttu-id="d3d00-108">Behörighet</span><span class="sxs-lookup"><span data-stu-id="d3d00-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="d3d00-109">Åtkomst</span><span class="sxs-lookup"><span data-stu-id="d3d00-109">Access</span></span>    |  <span data-ttu-id="d3d00-110">Läsa, skriva, köra</span><span class="sxs-lookup"><span data-stu-id="d3d00-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="d3d00-111">Åtgärdsläge</span><span class="sxs-lookup"><span data-stu-id="d3d00-111">Action Mode</span></span>    |    <span data-ttu-id="d3d00-112">Granska, tillåt, förhindra</span><span class="sxs-lookup"><span data-stu-id="d3d00-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="d3d00-113">Stöd för CSP</span><span class="sxs-lookup"><span data-stu-id="d3d00-113">CSP Support</span></span>   |   <span data-ttu-id="d3d00-114">Ja</span><span class="sxs-lookup"><span data-stu-id="d3d00-114">Yes</span></span>      |
|<span data-ttu-id="d3d00-115">GPO-support</span><span class="sxs-lookup"><span data-stu-id="d3d00-115">GPO Support</span></span>    |   <span data-ttu-id="d3d00-116">Ja</span><span class="sxs-lookup"><span data-stu-id="d3d00-116">Yes</span></span>      |
|<span data-ttu-id="d3d00-117">Användarbaserad support</span><span class="sxs-lookup"><span data-stu-id="d3d00-117">User-based Support</span></span>     |   <span data-ttu-id="d3d00-118">Ja</span><span class="sxs-lookup"><span data-stu-id="d3d00-118">Yes</span></span>      |
|<span data-ttu-id="d3d00-119">Maskinbaserad support</span><span class="sxs-lookup"><span data-stu-id="d3d00-119">Machine-based Support</span></span>    |    <span data-ttu-id="d3d00-120">Ja</span><span class="sxs-lookup"><span data-stu-id="d3d00-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="d3d00-121">Förbered dina slutpunkter</span><span class="sxs-lookup"><span data-stu-id="d3d00-121">Prepare your endpoints</span></span>

<span data-ttu-id="d3d00-122">Distribuera Flyttbart Storage Access Control på Windows 10-enheter med klientversionen mot skadlig programvara **version 4.18.2103.3 eller senare.**</span><span class="sxs-lookup"><span data-stu-id="d3d00-122">Deploy Removable Storage Access Control on Windows 10 devices that have Anti-malware Client Version **4.18.2103.3 or later**.</span></span>
1. <span data-ttu-id="d3d00-123">**4.18.2104** eller senare: Add SerialNumberId, VID_PID, filepath-baserat GPO-stöd</span><span class="sxs-lookup"><span data-stu-id="d3d00-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support</span></span>

2. <span data-ttu-id="d3d00-124">**4.18.2105** eller senare: Lägg till stöd för jokertecken för HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, kombinationen av en specifik användare på en specifik dator, removeable SSD (en SanDisk Extreme SSD)/USB Attached MORD (UAS) stöd</span><span class="sxs-lookup"><span data-stu-id="d3d00-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

:::image type="content" source="images/powershell.png" alt-text="PowerShell-gränssnittet":::

## <a name="policy-properties"></a><span data-ttu-id="d3d00-126">Principegenskaper</span><span class="sxs-lookup"><span data-stu-id="d3d00-126">Policy properties</span></span>

<span data-ttu-id="d3d00-127">Du kan använda följande egenskaper till att skapa en flyttbar lagringsgrupp:</span><span class="sxs-lookup"><span data-stu-id="d3d00-127">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="d3d00-128">**Egenskapsnamn: Grupp-ID**</span><span class="sxs-lookup"><span data-stu-id="d3d00-128">**Property name: Group ID**</span></span>

1. <span data-ttu-id="d3d00-129">Beskrivning: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), ett unikt ID, representerar gruppen och kommer att användas i principen.</span><span class="sxs-lookup"><span data-stu-id="d3d00-129">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="d3d00-130">**Egenskapsnamn: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="d3d00-130">**Property name: DescriptorIdList**</span></span>

1. <span data-ttu-id="d3d00-131">Beskrivning: Lista över de enhetsegenskaper du vill använda för gruppen.</span><span class="sxs-lookup"><span data-stu-id="d3d00-131">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="d3d00-132">Ange de enhetsegenskaper du vill använda i gruppen.</span><span class="sxs-lookup"><span data-stu-id="d3d00-132">List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="d3d00-133">Mer information om varje **enhetsegenskap finns** i avsnittet Enhetsegenskaper ovan.</span><span class="sxs-lookup"><span data-stu-id="d3d00-133">For each device property, see **Device Properties** section above for more detail.</span></span>

1. <span data-ttu-id="d3d00-134">Alternativ:</span><span class="sxs-lookup"><span data-stu-id="d3d00-134">Options:</span></span>
    - <span data-ttu-id="d3d00-135">Primärt ID</span><span class="sxs-lookup"><span data-stu-id="d3d00-135">Primary ID</span></span>
        - <span data-ttu-id="d3d00-136">FlyttbaraMediaDevices</span><span class="sxs-lookup"><span data-stu-id="d3d00-136">RemovableMediaDevices</span></span>
        - <span data-ttu-id="d3d00-137">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="d3d00-137">CdRomDevices</span></span>
    - <span data-ttu-id="d3d00-138">DeviceId</span><span class="sxs-lookup"><span data-stu-id="d3d00-138">DeviceId</span></span>
    - <span data-ttu-id="d3d00-139">HardwareId</span><span class="sxs-lookup"><span data-stu-id="d3d00-139">HardwareId</span></span>
    - <span data-ttu-id="d3d00-140">InstancePathId: InstancePathId är en sträng som unikt identifierar enheten i systemet, till exempel USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span><span class="sxs-lookup"><span data-stu-id="d3d00-140">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="d3d00-141">Numret på slutet (till exempel&**0**) representerar den tillgängliga platsen och kan ändras från enhet till enhet.</span><span class="sxs-lookup"><span data-stu-id="d3d00-141">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="d3d00-142">För bästa resultat bör du använda ett jokertecken i slutet.</span><span class="sxs-lookup"><span data-stu-id="d3d00-142">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="d3d00-143">Exempel: USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="d3d00-143">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="d3d00-144">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="d3d00-144">FriendlyNameId</span></span>
    - <span data-ttu-id="d3d00-145">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="d3d00-145">SerialNumberId</span></span>
    - <span data-ttu-id="d3d00-146">VID</span><span class="sxs-lookup"><span data-stu-id="d3d00-146">VID</span></span>
    - <span data-ttu-id="d3d00-147">PID</span><span class="sxs-lookup"><span data-stu-id="d3d00-147">PID</span></span>
    - <span data-ttu-id="d3d00-148">VID_PID</span><span class="sxs-lookup"><span data-stu-id="d3d00-148">VID_PID</span></span>
        - <span data-ttu-id="d3d00-149">0751_55E0: matcha exakt detta VID/PID-par</span><span class="sxs-lookup"><span data-stu-id="d3d00-149">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="d3d00-150">_55E0: matcha media med PID=55E0</span><span class="sxs-lookup"><span data-stu-id="d3d00-150">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="d3d00-151">0751_: matcha media med VID=0751</span><span class="sxs-lookup"><span data-stu-id="d3d00-151">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="d3d00-152">**Egenskapsnamn: MatchType**</span><span class="sxs-lookup"><span data-stu-id="d3d00-152">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="d3d00-153">Beskrivning: När det finns flera enhetsegenskaper som används i DescriptorIDList definierar MatchType relationen.</span><span class="sxs-lookup"><span data-stu-id="d3d00-153">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

1. <span data-ttu-id="d3d00-154">Alternativ:</span><span class="sxs-lookup"><span data-stu-id="d3d00-154">Options:</span></span>
    - <span data-ttu-id="d3d00-155">MatchAll: Attributen under DescriptorIdList blir **och relationen;** Om administratören till exempel placerar DeviceID och InstancePathID för varje ansluten USB kontrollerar systemet om USB-minnet uppfyller båda värdena.</span><span class="sxs-lookup"><span data-stu-id="d3d00-155">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>

    - <span data-ttu-id="d3d00-156">MatchAny: Attributen under DescriptorIdList blir **Eller relationen;** Om administratören till exempel placerar DeviceID och InstancePathID, för varje anslutet USB-minne, kommer systemet att upprätthålla tillämpning så länge USB-minnet har antingen ett identiskt **DeviceID-** eller **InstanceID-värde.**</span><span class="sxs-lookup"><span data-stu-id="d3d00-156">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="d3d00-157">Här är egenskaperna för principegenskaper för åtkomstkontroll:</span><span class="sxs-lookup"><span data-stu-id="d3d00-157">Following are the access control policy properties:</span></span>

<span data-ttu-id="d3d00-158">**Egenskapsnamn: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="d3d00-158">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="d3d00-159">Beskrivning: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), ett unikt ID, representerar principen och kommer att användas i rapportering och felsökning.</span><span class="sxs-lookup"><span data-stu-id="d3d00-159">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="d3d00-160">**Egenskapsnamn: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="d3d00-160">**Property name: IncludedIdList**</span></span>

1. <span data-ttu-id="d3d00-161">Beskrivning: De grupper som principen ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="d3d00-161">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="d3d00-162">Om flera grupper läggs till tillämpas principen på alla media i alla grupperna.</span><span class="sxs-lookup"><span data-stu-id="d3d00-162">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

1. <span data-ttu-id="d3d00-163">Alternativ: Grupp-ID/GUID måste användas i den här instansen.</span><span class="sxs-lookup"><span data-stu-id="d3d00-163">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="d3d00-164">I följande exempel visas användningen av GroupID:</span><span class="sxs-lookup"><span data-stu-id="d3d00-164">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="d3d00-165">**Egenskapsnamn: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="d3d00-165">**Property name: ExcludedIDList**</span></span>

1. <span data-ttu-id="d3d00-166">Beskrivning: De grupper som principen inte ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="d3d00-166">Description: The group(s) that the policy will not be applied to.</span></span>
1. <span data-ttu-id="d3d00-167">Alternativ: Grupp-ID/GUID måste användas i den här instansen.</span><span class="sxs-lookup"><span data-stu-id="d3d00-167">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="d3d00-168">**Egenskapsnamn: Post-ID**</span><span class="sxs-lookup"><span data-stu-id="d3d00-168">**Property name: Entry ID**</span></span>

1. <span data-ttu-id="d3d00-169">Beskrivning: En principregel kan ha flera poster. varje post med ett unikt GUID anger enhetskontroll en begränsning.</span><span class="sxs-lookup"><span data-stu-id="d3d00-169">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="d3d00-170">**Egenskapsnamn: Typ**</span><span class="sxs-lookup"><span data-stu-id="d3d00-170">**Property name: Type**</span></span>

1. <span data-ttu-id="d3d00-171">Beskrivning: Definierar åtgärden för de flyttbara lagringsgrupperna i IncludedIDList.</span><span class="sxs-lookup"><span data-stu-id="d3d00-171">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="d3d00-172">Tillämpning: Tillåt eller Neka</span><span class="sxs-lookup"><span data-stu-id="d3d00-172">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="d3d00-173">Granskning: GranskningSalla eller GranskaDenied</span><span class="sxs-lookup"><span data-stu-id="d3d00-173">Audit: AuditAllowed or AuditDenied</span></span> 
1. <span data-ttu-id="d3d00-174">Alternativ:</span><span class="sxs-lookup"><span data-stu-id="d3d00-174">Options:</span></span>
    - <span data-ttu-id="d3d00-175">Tillåt</span><span class="sxs-lookup"><span data-stu-id="d3d00-175">Allow</span></span>
    - <span data-ttu-id="d3d00-176">Neka</span><span class="sxs-lookup"><span data-stu-id="d3d00-176">Deny</span></span>
    - <span data-ttu-id="d3d00-177">AuditAllowed: Definierar meddelande och händelse när åtkomst är tillåten</span><span class="sxs-lookup"><span data-stu-id="d3d00-177">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="d3d00-178">AuditDenied: Definierar meddelande och händelse när åtkomst nekas. måste arbeta tillsammans med **den nekade** posten.</span><span class="sxs-lookup"><span data-stu-id="d3d00-178">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="d3d00-179">När det finns konflikttyper för samma media används den första i principen i systemet.</span><span class="sxs-lookup"><span data-stu-id="d3d00-179">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="d3d00-180">Ett exempel på en konflikt är **Tillåt** **och Neka.**</span><span class="sxs-lookup"><span data-stu-id="d3d00-180">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="d3d00-181">**Egenskapsnamn: Alternativ**</span><span class="sxs-lookup"><span data-stu-id="d3d00-181">**Property name: Options**</span></span>

1. <span data-ttu-id="d3d00-182">Beskrivning: Definierar om meddelandet ska visas eller inte.</span><span class="sxs-lookup"><span data-stu-id="d3d00-182">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="Skärmen där enhetens status visas":::

1. <span data-ttu-id="d3d00-184">Alternativ: 0–4.</span><span class="sxs-lookup"><span data-stu-id="d3d00-184">Options: 0-4.</span></span> <span data-ttu-id="d3d00-185">När Tillåt eller Neka är markerat:</span><span class="sxs-lookup"><span data-stu-id="d3d00-185">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="d3d00-186">0: ingenting</span><span class="sxs-lookup"><span data-stu-id="d3d00-186">0: nothing</span></span>
   - <span data-ttu-id="d3d00-187">4: Inaktivera **AuditAllowed** **och AuditDenied för** den här posten.</span><span class="sxs-lookup"><span data-stu-id="d3d00-187">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="d3d00-188">Även om **Blockera** inträffar **och AuditDenied-inställningen** har konfigurerats visas inget meddelande i systemet.</span><span class="sxs-lookup"><span data-stu-id="d3d00-188">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="d3d00-189">När Type **AuditAllowed** **eller AuditDenied** är markerat:</span><span class="sxs-lookup"><span data-stu-id="d3d00-189">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="d3d00-190">0: ingenting</span><span class="sxs-lookup"><span data-stu-id="d3d00-190">0: nothing</span></span>
   - <span data-ttu-id="d3d00-191">1: visa meddelande</span><span class="sxs-lookup"><span data-stu-id="d3d00-191">1: show notification</span></span>
   - <span data-ttu-id="d3d00-192">2: skicka händelse</span><span class="sxs-lookup"><span data-stu-id="d3d00-192">2: send event</span></span>
   - <span data-ttu-id="d3d00-193">3: visa meddelande och skicka händelse</span><span class="sxs-lookup"><span data-stu-id="d3d00-193">3: show notification and send event</span></span>

<span data-ttu-id="d3d00-194">**Egenskapsnamn: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="d3d00-194">**Property name: AccessMask**</span></span>

1. <span data-ttu-id="d3d00-195">Beskrivning: Definierar åtkomsten.</span><span class="sxs-lookup"><span data-stu-id="d3d00-195">Description: Defines the access.</span></span>

1. <span data-ttu-id="d3d00-196">Alternativ: 1–7:</span><span class="sxs-lookup"><span data-stu-id="d3d00-196">Options: 1-7:</span></span>
    - <span data-ttu-id="d3d00-197">1: Läsa</span><span class="sxs-lookup"><span data-stu-id="d3d00-197">1: Read</span></span>
    - <span data-ttu-id="d3d00-198">2: Skriva</span><span class="sxs-lookup"><span data-stu-id="d3d00-198">2: Write</span></span>
    - <span data-ttu-id="d3d00-199">3: Läsa och skriva</span><span class="sxs-lookup"><span data-stu-id="d3d00-199">3: Read and Write</span></span>
    - <span data-ttu-id="d3d00-200">4: Utför</span><span class="sxs-lookup"><span data-stu-id="d3d00-200">4: Execute</span></span>
    - <span data-ttu-id="d3d00-201">5: Läsa och utföra</span><span class="sxs-lookup"><span data-stu-id="d3d00-201">5: Read and Execute</span></span>
    - <span data-ttu-id="d3d00-202">6: Skriva och utföra</span><span class="sxs-lookup"><span data-stu-id="d3d00-202">6: Write and Execute</span></span>
    - <span data-ttu-id="d3d00-203">7: Läsa och skriva och utföra</span><span class="sxs-lookup"><span data-stu-id="d3d00-203">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="d3d00-204">Vanliga scenarier för Storage och Access-kontroll</span><span class="sxs-lookup"><span data-stu-id="d3d00-204">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="d3d00-205">Vi har satt ihop några vanliga scenarier som du kan följa för att bekanta dig med Microsoft Defender för slutpunkten flyttbara Storage Access Control.</span><span class="sxs-lookup"><span data-stu-id="d3d00-205">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="d3d00-206">Scenario 1: Förhindra skrivning och körning av åtkomst till alla men tillåta specifika godkända USBs</span><span class="sxs-lookup"><span data-stu-id="d3d00-206">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="d3d00-207">Skapa grupper</span><span class="sxs-lookup"><span data-stu-id="d3d00-207">Create groups</span></span>
    1. <span data-ttu-id="d3d00-208">Grupp 1: Alla flyttbara lagringsmedia och CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="d3d00-208">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="d3d00-209">Ett exempel på flyttbart lagringsutrymme och cd/dvd är: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** i exemplet Any [Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="d3d00-209">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="d3d00-210">Grupp 2: Godkända usa baserat på enhetsegenskaper.</span><span class="sxs-lookup"><span data-stu-id="d3d00-210">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="d3d00-211">Ett exempel för det här användningsfall är: Instans-ID – Grupp **65fa649a-a111-4912-9294-fb6337a25038** i exemplet Godkända [amerikanska Group.xml-filer.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="d3d00-211">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d3d00-212">Du måste ersätta `&` med `&amp;` i värdet.</span><span class="sxs-lookup"><span data-stu-id="d3d00-212">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="d3d00-213">Skapa princip</span><span class="sxs-lookup"><span data-stu-id="d3d00-213">Create policy</span></span>
    1. <span data-ttu-id="d3d00-214">Princip 1: Blockera skrivning och körning av Access men tillåt godkända amerikanskabs.</span><span class="sxs-lookup"><span data-stu-id="d3d00-214">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="d3d00-215">Ett exempel för det här användningsfall är: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** i exemplet [Scenario 1 Blockera skrivning](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) och kör Access men tillåt godkända USBs .xml-fil.</span><span class="sxs-lookup"><span data-stu-id="d3d00-215">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs .xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="d3d00-216">Princip 2: Granska skrivning och kör åtkomst till tillåtna USB.</span><span class="sxs-lookup"><span data-stu-id="d3d00-216">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="d3d00-217">Ett exempel för det här användningsfall är: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** i exemplet Scenario 1 Granskningsskrivning och Kör åtkomst till [godkänd USBs.xml-fil.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="d3d00-217">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="d3d00-218">Scenario 2: Granska skrivning och kör åtkomst till alla utom blockera specifika usbs som inte godkänts</span><span class="sxs-lookup"><span data-stu-id="d3d00-218">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="d3d00-219">Skapa grupper</span><span class="sxs-lookup"><span data-stu-id="d3d00-219">Create groups</span></span>
    1. <span data-ttu-id="d3d00-220">Grupp 1: Alla flyttbara lagringsmedia och CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="d3d00-220">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="d3d00-221">Ett exempel för det här användningsfall är: Grupp **9b28fae8-72f7-4267-a1a5-685f747a7146** i exemplet [Flyttbara Storage- och CD-DVD-Group.xmlfiler.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="d3d00-221">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="d3d00-222">Grupp 2: Ej godkända amerikanska sampel baserat på enhetsegenskaper, exempelvis leverantörs-ID/produkt-ID, eget namn – grupp **65fa649a-a111-4912-9294-fb6337a25038** i [exempelfilen Group.xmlusbs som](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) inte godkänts.</span><span class="sxs-lookup"><span data-stu-id="d3d00-222">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="d3d00-223">Du måste ersätta `&` med `&amp;` i värdet.</span><span class="sxs-lookup"><span data-stu-id="d3d00-223">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="d3d00-224">Skapa princip</span><span class="sxs-lookup"><span data-stu-id="d3d00-224">Create policy</span></span>
    1. <span data-ttu-id="d3d00-225">Princip 1: Blockera skrivning och körning av åtkomst till alla utom blockera specifika usBs som inte godkänts.</span><span class="sxs-lookup"><span data-stu-id="d3d00-225">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="d3d00-226">Ett exempel på det här användningsfall är: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** i exempelscenario 2 Granskningsskrivning och Kör åtkomst till alla men blockerar en viss ej USBs.xml [fil.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="d3d00-226">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="d3d00-227">Princip 2: Granska skrivning och utför åtkomst till andra.</span><span class="sxs-lookup"><span data-stu-id="d3d00-227">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="d3d00-228">Ett exempel på det här användningsfall är: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** i exemplet [Scenario 2](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Granskningsskrivning och Kör åtkomst till others.xmlfil.</span><span class="sxs-lookup"><span data-stu-id="d3d00-228">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="d3d00-229">Distribuera och hantera princip via grupprincip</span><span class="sxs-lookup"><span data-stu-id="d3d00-229">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="d3d00-230">Med funktionen Storage och Access Control kan du tillämpa en princip via grupprincip på antingen en användare eller enhet eller både och.</span><span class="sxs-lookup"><span data-stu-id="d3d00-230">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="d3d00-231">Licensiering</span><span class="sxs-lookup"><span data-stu-id="d3d00-231">Licensing</span></span>

<span data-ttu-id="d3d00-232">Innan du kommer igång med Flyttbara Storage Access Control måste du bekräfta din [Microsoft 365-prenumeration.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="d3d00-232">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="d3d00-233">För att komma åt och använda Storage Access Control måste du ha Microsoft 365 E3 eller Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="d3d00-233">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="d3d00-234">Distribuera princip via grupprincip</span><span class="sxs-lookup"><span data-stu-id="d3d00-234">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="d3d00-235">Kombinera alla grupper i `<Groups>` `</Groups>` en XML-fil.</span><span class="sxs-lookup"><span data-stu-id="d3d00-235">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="d3d00-236">Följande bild illustrerar exemplet på [Scenario 1: Förhindra skrivning](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)och kör åtkomst till alla men tillåta specifika godkända amerikanskabs .</span><span class="sxs-lookup"><span data-stu-id="d3d00-236">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Skärmen som visar konfigurationsinställningar som tillåter specifika godkända usbs på enheter":::
    
2. <span data-ttu-id="d3d00-238">Kombinera alla regler i `<PolicyRules>` `</PolicyRules>` en XML-fil.</span><span class="sxs-lookup"><span data-stu-id="d3d00-238">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="d3d00-239">Om du vill begränsa en viss användare använder du SID-egenskapen i Posten.</span><span class="sxs-lookup"><span data-stu-id="d3d00-239">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="d3d00-240">Om det inte finns någon SID i principposten kommer posten att tillämpas på alla inloggningsinstans för datorn.</span><span class="sxs-lookup"><span data-stu-id="d3d00-240">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="d3d00-241">Följande bild visar användningen av SID-egenskapen och ett exempel på [Scenario 1: Förhindra skrivning](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)och kör åtkomst till alla men tillåta specifika godkända USBs.</span><span class="sxs-lookup"><span data-stu-id="d3d00-241">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Skärmen som visar en kod som anger användningen av sidegenskapsattributet":::

3. <span data-ttu-id="d3d00-243">Spara både regel- och grupp-XML-filer i mappen för nätverksresurs och placera sökvägen till mappen för nätverksresurs i grupprincipinställningen: Datorkonfiguration -> Administrativa mallar **-> Windows-komponenter -> Microsoft Defender Antivirus -> Enhetskontroll: Definiera** grupper för enhetskontrollprinciper och Definiera regler för enhetskontrollprinciper.</span><span class="sxs-lookup"><span data-stu-id="d3d00-243">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="d3d00-244">Måldatorn måste kunna komma åt nätverksresursen för att principen ska vara på.</span><span class="sxs-lookup"><span data-stu-id="d3d00-244">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="d3d00-245">När principen har lästs behövs dock inte längre nätverksanslutningen för nätverksresursen, även efter att datorn startats om.</span><span class="sxs-lookup"><span data-stu-id="d3d00-245">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="Skärmen Enhetskontroll":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="d3d00-247">Distribuera och hantera princip via Intune OMA-URI</span><span class="sxs-lookup"><span data-stu-id="d3d00-247">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="d3d00-248">Med funktionen flyttbara Storage Access Control kan du tillämpa principen via OMA-URI på antingen användare eller enhet, eller båda.</span><span class="sxs-lookup"><span data-stu-id="d3d00-248">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="d3d00-249">Licensiering</span><span class="sxs-lookup"><span data-stu-id="d3d00-249">Licensing</span></span>

<span data-ttu-id="d3d00-250">Innan du kommer igång med Flyttbara Storage Access Control måste du bekräfta din [Microsoft 365-prenumeration.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="d3d00-250">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="d3d00-251">För att komma åt och använda Storage Access Control måste du ha Microsoft 365 E3 eller Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="d3d00-251">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="d3d00-252">Behörighet</span><span class="sxs-lookup"><span data-stu-id="d3d00-252">Permission</span></span>

<span data-ttu-id="d3d00-253">För principdistribution i Intune måste kontot ha behörighet att skapa, redigera, uppdatera eller ta bort profiler för enhetskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="d3d00-253">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="d3d00-254">Du kan skapa anpassade roller eller använda någon av de inbyggda rollerna med dessa behörigheter.</span><span class="sxs-lookup"><span data-stu-id="d3d00-254">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="d3d00-255">Rollen Princip- och profilhanterare</span><span class="sxs-lookup"><span data-stu-id="d3d00-255">Policy and profile Manager role</span></span>
- <span data-ttu-id="d3d00-256">Anpassad roll med behörigheten Skapa/Redigera/Uppdatera/Läsa/Ta bort/Visa rapporter aktiverad för enhetskonfigurationsprofiler</span><span class="sxs-lookup"><span data-stu-id="d3d00-256">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="d3d00-257">Global administratör</span><span class="sxs-lookup"><span data-stu-id="d3d00-257">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="d3d00-258">Distribuera princip via OMA-URI</span><span class="sxs-lookup"><span data-stu-id="d3d00-258">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="d3d00-259">**Microsoft Endpoint Manager administrationscenter ( https://endpoint.microsoft.com/) -> -> Konfigurationsprofiler -> Skapa profil ->-plattform: Windows 10 och senare & Profil: Anpassad**</span><span class="sxs-lookup"><span data-stu-id="d3d00-259">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="d3d00-260">Skapa en OMA-URI-regel för varje grupp:</span><span class="sxs-lookup"><span data-stu-id="d3d00-260">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="d3d00-261">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="d3d00-261">OMA-URI:</span></span>

      <span data-ttu-id="d3d00-262">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="d3d00-262">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="d3d00-263">För flyttbara **lagrings- och CD-/DVD-grupper** i samplet måste länken till exempel vara:</span><span class="sxs-lookup"><span data-stu-id="d3d00-263">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="d3d00-264">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="d3d00-264">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="d3d00-265">Datatyp: Sträng (XML-fil)</span><span class="sxs-lookup"><span data-stu-id="d3d00-265">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="XML-filen för datatypen STRING":::

2. <span data-ttu-id="d3d00-267">För varje princip skapar du även en OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="d3d00-267">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="d3d00-268">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="d3d00-268">OMA-URI:</span></span>

      <span data-ttu-id="d3d00-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="d3d00-269">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="d3d00-270">För till exempel regeln **Blockera skrivning och körning av Access men** tillåt godkända amerikanskabs i exemplet måste länken vara:</span><span class="sxs-lookup"><span data-stu-id="d3d00-270">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="d3d00-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="d3d00-271">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="d3d00-272">Datatyp: Sträng (XML-fil)</span><span class="sxs-lookup"><span data-stu-id="d3d00-272">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Visning av XML-fil för datatypen STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="d3d00-274">Distribuera och hantera princip med hjälp av användargränssnittet i Intune</span><span class="sxs-lookup"><span data-stu-id="d3d00-274">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="d3d00-275">Den här funktionen (i Microsoft Endpoint Manager admincenter (>-enheter > konfigurationsprofiler > Skapa profil >-plattform: Windows 10 och senare & Profil: Enhetskontroll) är ännu inte https://endpoint.microsoft.com/) tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="d3d00-275">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="d3d00-276">Visa flyttbara enheter med enhetskontroll Storage Access Control-data i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="d3d00-276">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="d3d00-277">I Microsoft 365 säkerhetsportalen visas flyttbart lagringsutrymme som blockeras av den flyttbara enhetskontrollen Storage Access Control.</span><span class="sxs-lookup"><span data-stu-id="d3d00-277">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="d3d00-278">För att komma Microsoft 365 säkerhet måste du ha följande prenumeration:</span><span class="sxs-lookup"><span data-stu-id="d3d00-278">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="d3d00-279">Microsoft 365 för E5-rapportering</span><span class="sxs-lookup"><span data-stu-id="d3d00-279">Microsoft 365 for E5 reporting</span></span>

```kusto
//events triggered by RemovableStoragePolicyTriggered
DeviceEvents
| where ActionType == &quot;RemovableStoragePolicyTriggered&quot; 
| extend parsed=parse_json(AdditionalFields) 
| extend RemovableStorageAccess = tostring(parsed.RemovableStorageAccess)  
| extend RemovableStoragePolicyVerdict = tostring(parsed.RemovableStoragePolicyVerdict)  
| extend MediaBusType = tostring(parsed.BusType)  
| extend MediaClassGuid = tostring(parsed.ClassGuid)
| extend MediaClassName = tostring(parsed.ClassName)
| extend MediaDeviceId = tostring(parsed.DeviceId) 
| extend MediaInstanceId = tostring(parsed.DeviceInstanceId) 
| extend MediaName = tostring(parsed.MediaName) 
| extend RemovableStoragePolicy = tostring(parsed.RemovableStoragePolicy)  
| extend MediaProductId = tostring(parsed.ProductId)  
| extend MediaVendorId = tostring(parsed.VendorId)  
| extend MediaSerialNumber = tostring(parsed.SerialNumber)  
| extend MediaVolume = tostring(parsed.Volume)  
| project Timestamp, DeviceId, DeviceName, ActionType, RemovableStorageAccess, RemovableStoragePolicyVerdict, MediaBusType, MediaClassGuid, MediaClassName, MediaDeviceId, MediaInstanceId, MediaName, RemovableStoragePolicy, MediaProductId, MediaVendorId, MediaSerialNumber, MediaVolume 
| order by Timestamp desc
```

:::image type="content" source="images/block-removable-storage.png" alt-text="Skärmen visar hur det flyttbara lagringsutrymmet blockeras":::
