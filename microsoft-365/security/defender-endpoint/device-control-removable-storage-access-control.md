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
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 8b32ab5162e0022d9500f7ddba2fe5bbca1017e7
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229581"
---
# <a name="microsoft-defender-for-endpoint-device-control-removable-storage-access-control"></a><span data-ttu-id="77689-104">Microsoft Defender för endpoint-enhetskontroll, flyttbar Storage access-kontroll</span><span class="sxs-lookup"><span data-stu-id="77689-104">Microsoft Defender for Endpoint Device Control Removable Storage Access Control</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="77689-105">Med Microsoft Defender för Endpoint Device Control Storage och Access Control kan du göra följande:</span><span class="sxs-lookup"><span data-stu-id="77689-105">Microsoft Defender for Endpoint Device Control Removable Storage Access Control enables you to do the following task:</span></span>
- <span data-ttu-id="77689-106">granska, tillåta eller förhindra läsning, skriva eller köra åtkomst till flyttbara lagringsmedia med eller utan undantag</span><span class="sxs-lookup"><span data-stu-id="77689-106">auditing, allowing or preventing the read, write or execute access to removable storage with or without exclusion</span></span>

|<span data-ttu-id="77689-107">Behörighet</span><span class="sxs-lookup"><span data-stu-id="77689-107">Privilege</span></span> |<span data-ttu-id="77689-108">Behörighet</span><span class="sxs-lookup"><span data-stu-id="77689-108">Permission</span></span>  |
|---------|---------|
|<span data-ttu-id="77689-109">Åtkomst</span><span class="sxs-lookup"><span data-stu-id="77689-109">Access</span></span>    |  <span data-ttu-id="77689-110">Läsa, skriva, köra</span><span class="sxs-lookup"><span data-stu-id="77689-110">Read, Write, Execute</span></span>       |
|<span data-ttu-id="77689-111">Åtgärdsläge</span><span class="sxs-lookup"><span data-stu-id="77689-111">Action Mode</span></span>    |    <span data-ttu-id="77689-112">Granska, tillåt, förhindra</span><span class="sxs-lookup"><span data-stu-id="77689-112">Audit, Allow, Prevent</span></span>     |
|<span data-ttu-id="77689-113">Stöd för CSP</span><span class="sxs-lookup"><span data-stu-id="77689-113">CSP Support</span></span>   |   <span data-ttu-id="77689-114">Ja</span><span class="sxs-lookup"><span data-stu-id="77689-114">Yes</span></span>      |
|<span data-ttu-id="77689-115">GPO-support</span><span class="sxs-lookup"><span data-stu-id="77689-115">GPO Support</span></span>    |   <span data-ttu-id="77689-116">Ja</span><span class="sxs-lookup"><span data-stu-id="77689-116">Yes</span></span>      |
|<span data-ttu-id="77689-117">Användarbaserad support</span><span class="sxs-lookup"><span data-stu-id="77689-117">User-based Support</span></span>     |   <span data-ttu-id="77689-118">Ja</span><span class="sxs-lookup"><span data-stu-id="77689-118">Yes</span></span>      |
|<span data-ttu-id="77689-119">Maskinbaserad support</span><span class="sxs-lookup"><span data-stu-id="77689-119">Machine-based Support</span></span>    |    <span data-ttu-id="77689-120">Ja</span><span class="sxs-lookup"><span data-stu-id="77689-120">Yes</span></span>     |

## <a name="prepare-your-endpoints"></a><span data-ttu-id="77689-121">Förbered dina slutpunkter</span><span class="sxs-lookup"><span data-stu-id="77689-121">Prepare your endpoints</span></span>

<span data-ttu-id="77689-122">Distribuera Flyttbara Storage Access Control på Windows 10-enheter som har version **4.18.2103.3 eller senare av** program mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="77689-122">Deploy Removable Storage Access Control on Windows 10 devices that have antimalware client version **4.18.2103.3 or later**.</span></span>

- <span data-ttu-id="77689-123">**4.18.2104** eller senare: Add SerialNumberId, VID_PID, filepath-baserat GPO-stöd, ComputerSid</span><span class="sxs-lookup"><span data-stu-id="77689-123">**4.18.2104 or later**: Add SerialNumberId, VID_PID, filepath-based GPO support, ComputerSid</span></span>

- <span data-ttu-id="77689-124">**4.18.2105** eller senare: Lägg till stöd för jokertecken för HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, kombinationen av en specifik användare på en specifik dator, removeable SSD (en SanDisk Extreme SSD)/USB Attached MORD (UAS) stöd</span><span class="sxs-lookup"><span data-stu-id="77689-124">**4.18.2105 or later**: Add Wildcard support for HardwareId/DeviceId/InstancePathId/FriendlyNameId/SerialNumberId, the combination of specific user on specific machine, removeable SSD (a SanDisk Extreme SSD)/USB Attached SCSI (UAS) support</span></span>

:::image type="content" source="images/powershell.png" alt-text="PowerShell-gränssnittet":::

> [!NOTE]
> <span data-ttu-id="77689-126">Ingen av Windows-säkerhet komponenter måste vara aktiva, du kan köra Flyttbara Storage Access Control oberoende av Windows-säkerhet status.</span><span class="sxs-lookup"><span data-stu-id="77689-126">None of Windows Security components need to be active, you can run Removable Storage Access Control independent of Windows Security status.</span></span>

## <a name="policy-properties"></a><span data-ttu-id="77689-127">Principegenskaper</span><span class="sxs-lookup"><span data-stu-id="77689-127">Policy properties</span></span>

<span data-ttu-id="77689-128">Du kan använda följande egenskaper till att skapa en flyttbar lagringsgrupp:</span><span class="sxs-lookup"><span data-stu-id="77689-128">You can use the following properties to create a removable storage group:</span></span>

<span data-ttu-id="77689-129">**Egenskapsnamn: Grupp-ID**</span><span class="sxs-lookup"><span data-stu-id="77689-129">**Property name: Group Id**</span></span>

1. <span data-ttu-id="77689-130">Beskrivning: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), ett unikt ID, representerar gruppen och kommer att användas i principen.</span><span class="sxs-lookup"><span data-stu-id="77689-130">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the group and will be used in the policy.</span></span>

<span data-ttu-id="77689-131">**Egenskapsnamn: DescriptorIdList**</span><span class="sxs-lookup"><span data-stu-id="77689-131">**Property name: DescriptorIdList**</span></span>

1. <span data-ttu-id="77689-132">Beskrivning: Lista över de enhetsegenskaper du vill använda för gruppen.</span><span class="sxs-lookup"><span data-stu-id="77689-132">Description: List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="77689-133">Ange de enhetsegenskaper du vill använda i gruppen.</span><span class="sxs-lookup"><span data-stu-id="77689-133">List the device properties you want to use to cover in the group.</span></span>
<span data-ttu-id="77689-134">Mer information om varje **enhetsegenskap finns** i avsnittet Enhetsegenskaper ovan.</span><span class="sxs-lookup"><span data-stu-id="77689-134">For each device property, see **Device Properties** section above for more detail.</span></span>

1. <span data-ttu-id="77689-135">Alternativ:</span><span class="sxs-lookup"><span data-stu-id="77689-135">Options:</span></span>

    - <span data-ttu-id="77689-136">Primärt ID</span><span class="sxs-lookup"><span data-stu-id="77689-136">Primary ID</span></span>
        - <span data-ttu-id="77689-137">FlyttbaraMediaDevices</span><span class="sxs-lookup"><span data-stu-id="77689-137">RemovableMediaDevices</span></span>
        - <span data-ttu-id="77689-138">CdRomDevices</span><span class="sxs-lookup"><span data-stu-id="77689-138">CdRomDevices</span></span>
    - <span data-ttu-id="77689-139">DeviceId</span><span class="sxs-lookup"><span data-stu-id="77689-139">DeviceId</span></span>
    - <span data-ttu-id="77689-140">HardwareId</span><span class="sxs-lookup"><span data-stu-id="77689-140">HardwareId</span></span>
    - <span data-ttu-id="77689-141">InstancePathId: InstancePathId är en sträng som unikt identifierar enheten i systemet, till exempel USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span><span class="sxs-lookup"><span data-stu-id="77689-141">InstancePathId: InstancePathId is a string that uniquely identifies the device in the system, for example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611&0.</span></span> <span data-ttu-id="77689-142">Numret på slutet (till exempel&**0**) representerar den tillgängliga platsen och kan ändras från enhet till enhet.</span><span class="sxs-lookup"><span data-stu-id="77689-142">The number at the end (for example **&0**) represents the available slot and may change from device to device.</span></span> <span data-ttu-id="77689-143">För bästa resultat bör du använda ett jokertecken i slutet.</span><span class="sxs-lookup"><span data-stu-id="77689-143">For best results, use a wildcard at the end.</span></span> <span data-ttu-id="77689-144">Exempel: USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span><span class="sxs-lookup"><span data-stu-id="77689-144">For example, USBSTOR\DISK&VEN_GENERIC&PROD_FLASH_DISK&REV_8.07\8735B611\*</span></span>
    - <span data-ttu-id="77689-145">FriendlyNameId</span><span class="sxs-lookup"><span data-stu-id="77689-145">FriendlyNameId</span></span>
    - <span data-ttu-id="77689-146">SerialNumberId</span><span class="sxs-lookup"><span data-stu-id="77689-146">SerialNumberId</span></span>
    - <span data-ttu-id="77689-147">VID</span><span class="sxs-lookup"><span data-stu-id="77689-147">VID</span></span>
    - <span data-ttu-id="77689-148">PID</span><span class="sxs-lookup"><span data-stu-id="77689-148">PID</span></span>
    - <span data-ttu-id="77689-149">VID_PID</span><span class="sxs-lookup"><span data-stu-id="77689-149">VID_PID</span></span>
        - <span data-ttu-id="77689-150">0751_55E0: matcha exakt detta VID/PID-par</span><span class="sxs-lookup"><span data-stu-id="77689-150">0751_55E0: match this exact VID/PID pair</span></span>
        - <span data-ttu-id="77689-151">_55E0: matcha media med PID=55E0</span><span class="sxs-lookup"><span data-stu-id="77689-151">_55E0: match any media with PID=55E0</span></span>
        - <span data-ttu-id="77689-152">0751_: matcha media med VID=0751</span><span class="sxs-lookup"><span data-stu-id="77689-152">0751_: match any media with VID=0751</span></span>
        
<span data-ttu-id="77689-153">**Egenskapsnamn: MatchType**</span><span class="sxs-lookup"><span data-stu-id="77689-153">**Property name: MatchType**</span></span> 

1. <span data-ttu-id="77689-154">Beskrivning: När det finns flera enhetsegenskaper som används i DescriptorIDList definierar MatchType relationen.</span><span class="sxs-lookup"><span data-stu-id="77689-154">Description: When there are multiple device properties being used in the DescriptorIDList, MatchType defines the relationship.</span></span>

1. <span data-ttu-id="77689-155">Alternativ:</span><span class="sxs-lookup"><span data-stu-id="77689-155">Options:</span></span>

    - <span data-ttu-id="77689-156">MatchAll: Attributen under DescriptorIdList blir **och relationen;** Om administratören till exempel placerar DeviceID och InstancePathID för varje ansluten USB kontrollerar systemet om USB-minnet uppfyller båda värdena.</span><span class="sxs-lookup"><span data-stu-id="77689-156">MatchAll: Any attributes under the DescriptorIdList will be **And** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will check to see whether the USB meets both values.</span></span>
    - <span data-ttu-id="77689-157">MatchAny: Attributen under DescriptorIdList blir **Eller relationen;** Om administratören till exempel placerar DeviceID och InstancePathID, för varje anslutet USB-minne, kommer systemet att upprätthålla tillämpning så länge USB-minnet har antingen ett identiskt **DeviceID-** eller **InstanceID-värde.**</span><span class="sxs-lookup"><span data-stu-id="77689-157">MatchAny: The attributes under the DescriptorIdList will be **Or** relationship; for example, if administrator puts DeviceID and InstancePathID, for every connected USB, system will do the enforcement as long as the USB has either an identical **DeviceID** or **InstanceID** value.</span></span>

<span data-ttu-id="77689-158">Här är egenskaperna för principegenskaper för åtkomstkontroll:</span><span class="sxs-lookup"><span data-stu-id="77689-158">Following are the access control policy properties:</span></span>

<span data-ttu-id="77689-159">**Egenskapsnamn: PolicyRuleId**</span><span class="sxs-lookup"><span data-stu-id="77689-159">**Property name: PolicyRuleId**</span></span>

1. <span data-ttu-id="77689-160">Beskrivning: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), ett unikt ID, representerar principen och kommer att användas i rapportering och felsökning.</span><span class="sxs-lookup"><span data-stu-id="77689-160">Description: [GUID](https://en.wikipedia.org/wiki/Universally_unique_identifier), a unique ID, represents the policy and will be used in the reporting and troubleshooting.</span></span>

<span data-ttu-id="77689-161">**Egenskapsnamn: IncludedIdList**</span><span class="sxs-lookup"><span data-stu-id="77689-161">**Property name: IncludedIdList**</span></span>

2. <span data-ttu-id="77689-162">Beskrivning: De grupper som principen ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="77689-162">Description: The group(s) that the policy will be applied to.</span></span> <span data-ttu-id="77689-163">Om flera grupper läggs till tillämpas principen på alla media i alla grupperna.</span><span class="sxs-lookup"><span data-stu-id="77689-163">If multiple groups are added, the policy will be applied to any media in all those groups.</span></span>

3. <span data-ttu-id="77689-164">Alternativ: Grupp-ID/GUID måste användas i den här instansen.</span><span class="sxs-lookup"><span data-stu-id="77689-164">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="77689-165">I följande exempel visas användningen av GroupID:</span><span class="sxs-lookup"><span data-stu-id="77689-165">The following example shows the usage of GroupID:</span></span>

`<IncludedIdList> <GroupId>{EAA4CCE5-F6C9-4760-8BAD-FDCC76A2ACA1}</GroupId> </IncludedIdList>`

<span data-ttu-id="77689-166">**Egenskapsnamn: ExcludedIDList**</span><span class="sxs-lookup"><span data-stu-id="77689-166">**Property name: ExcludedIDList**</span></span>

<span data-ttu-id="77689-167">Beskrivning: De grupper som principen inte ska tillämpas på.</span><span class="sxs-lookup"><span data-stu-id="77689-167">Description: The group(s) that the policy will not be applied to.</span></span>

<span data-ttu-id="77689-168">Alternativ: Grupp-ID/GUID måste användas i den här instansen.</span><span class="sxs-lookup"><span data-stu-id="77689-168">Options: The Group ID/GUID must be used at this instance.</span></span>

<span data-ttu-id="77689-169">**Egenskapsnamn: Post-ID**</span><span class="sxs-lookup"><span data-stu-id="77689-169">**Property name: Entry Id**</span></span>

1. <span data-ttu-id="77689-170">Beskrivning: En principregel kan ha flera poster. varje post med ett unikt GUID anger enhetskontroll en begränsning.</span><span class="sxs-lookup"><span data-stu-id="77689-170">Description: One PolicyRule can have multiple entries; each entry with a unique GUID tells Device Control one restriction.</span></span>

<span data-ttu-id="77689-171">**Egenskapsnamn: Typ**</span><span class="sxs-lookup"><span data-stu-id="77689-171">**Property name: Type**</span></span>

1. <span data-ttu-id="77689-172">Beskrivning: Definierar åtgärden för de flyttbara lagringsgrupperna i IncludedIDList.</span><span class="sxs-lookup"><span data-stu-id="77689-172">Description: Defines the action for the removable storage groups in IncludedIDList.</span></span>
    - <span data-ttu-id="77689-173">Tillämpning: Tillåt eller Neka</span><span class="sxs-lookup"><span data-stu-id="77689-173">Enforcement: Allow or Deny</span></span>
    - <span data-ttu-id="77689-174">Granskning: GranskningSalla eller GranskaDenied</span><span class="sxs-lookup"><span data-stu-id="77689-174">Audit: AuditAllowed or AuditDenied</span></span> 

2. <span data-ttu-id="77689-175">Alternativ:</span><span class="sxs-lookup"><span data-stu-id="77689-175">Options:</span></span>

    - <span data-ttu-id="77689-176">Tillåt</span><span class="sxs-lookup"><span data-stu-id="77689-176">Allow</span></span>
    - <span data-ttu-id="77689-177">Neka</span><span class="sxs-lookup"><span data-stu-id="77689-177">Deny</span></span>
    - <span data-ttu-id="77689-178">AuditAllowed: Definierar meddelande och händelse när åtkomst är tillåten</span><span class="sxs-lookup"><span data-stu-id="77689-178">AuditAllowed: Defines notification and event when access is allowed</span></span>
    - <span data-ttu-id="77689-179">AuditDenied: Definierar meddelande och händelse när åtkomst nekas. måste arbeta tillsammans med **den nekade** posten.</span><span class="sxs-lookup"><span data-stu-id="77689-179">AuditDenied: Defines notification and event when access is denied; has to work together with **Deny** entry.</span></span>

<span data-ttu-id="77689-180">När det finns konflikttyper för samma media används den första i principen i systemet.</span><span class="sxs-lookup"><span data-stu-id="77689-180">When there are conflict types for the same media, the system will apply the first one in the policy.</span></span> <span data-ttu-id="77689-181">Ett exempel på en konflikt är **Tillåt** **och Neka.**</span><span class="sxs-lookup"><span data-stu-id="77689-181">An example of a conflict type is **Allow** and **Deny**.</span></span>

<span data-ttu-id="77689-182">**Egenskapsnamn: Sid**</span><span class="sxs-lookup"><span data-stu-id="77689-182">**Property name: Sid**</span></span>

<span data-ttu-id="77689-183">Beskrivning: Definierar om den här principen ska användas i en viss användare eller användargrupp. en post kan ha maximalt en Sid och en post utan sid innebär att principen tillämpas på datorn.</span><span class="sxs-lookup"><span data-stu-id="77689-183">Description: Defines whether apply this policy over specific user or user group; one entry can have maximum one Sid and an entry without any Sid means applying the policy over the machine.</span></span>

<span data-ttu-id="77689-184">**Egenskapsnamn: DatorSid**</span><span class="sxs-lookup"><span data-stu-id="77689-184">**Property name: ComputerSid**</span></span>

<span data-ttu-id="77689-185">Beskrivning: Definierar om den här principen ska användas i en viss dator eller datorgrupp. En post kan ha maximalt en ComputerSid och en post utan ComputerSid innebär att principen tillämpas på datorn.</span><span class="sxs-lookup"><span data-stu-id="77689-185">Description: Defines whether apply this policy over specific machine or machine group; one entry can have maximum one ComputerSid and an entry without any ComputerSid means applying the policy over the machine.</span></span> <span data-ttu-id="77689-186">Om du vill använda en Post för en viss användare och en viss dator lägger du till både Sid och DatorSid i samma Post.</span><span class="sxs-lookup"><span data-stu-id="77689-186">If you want to apply an Entry to a specific user and specific machine, add both Sid and ComputerSid into the same Entry.</span></span>

<span data-ttu-id="77689-187">**Egenskapsnamn: Alternativ**</span><span class="sxs-lookup"><span data-stu-id="77689-187">**Property name: Options**</span></span>

<span data-ttu-id="77689-188">Beskrivning: Definierar om meddelandet ska visas eller inte.</span><span class="sxs-lookup"><span data-stu-id="77689-188">Description: Defines whether to display notification or not.</span></span>

   :::image type="content" source="images/device-status.png" alt-text="Skärmen där enhetens status visas":::

<span data-ttu-id="77689-190">Alternativ: 0–4.</span><span class="sxs-lookup"><span data-stu-id="77689-190">Options: 0-4.</span></span> <span data-ttu-id="77689-191">När Tillåt eller Neka är markerat:</span><span class="sxs-lookup"><span data-stu-id="77689-191">When Type Allow or Deny is selected:</span></span>

   - <span data-ttu-id="77689-192">0: ingenting</span><span class="sxs-lookup"><span data-stu-id="77689-192">0: nothing</span></span>
   - <span data-ttu-id="77689-193">4: Inaktivera **AuditAllowed** **och AuditDenied för** den här posten.</span><span class="sxs-lookup"><span data-stu-id="77689-193">4: disable **AuditAllowed** and **AuditDenied** for this Entry.</span></span> <span data-ttu-id="77689-194">Även om **Blockera** inträffar **och AuditDenied-inställningen** har konfigurerats visas inget meddelande i systemet.</span><span class="sxs-lookup"><span data-stu-id="77689-194">Even if **Block** happens and the **AuditDenied** is setting configured, the system will not show notification.</span></span>

   <span data-ttu-id="77689-195">När Type **AuditAllowed** **eller AuditDenied** är markerat:</span><span class="sxs-lookup"><span data-stu-id="77689-195">When Type **AuditAllowed** or **AuditDenied** is selected:</span></span>

   - <span data-ttu-id="77689-196">0: ingenting</span><span class="sxs-lookup"><span data-stu-id="77689-196">0: nothing</span></span>
   - <span data-ttu-id="77689-197">1: visa meddelande</span><span class="sxs-lookup"><span data-stu-id="77689-197">1: show notification</span></span>
   - <span data-ttu-id="77689-198">2: skicka händelse</span><span class="sxs-lookup"><span data-stu-id="77689-198">2: send event</span></span>
   - <span data-ttu-id="77689-199">3: visa meddelande och skicka händelse</span><span class="sxs-lookup"><span data-stu-id="77689-199">3: show notification and send event</span></span>

<span data-ttu-id="77689-200">**Egenskapsnamn: AccessMask**</span><span class="sxs-lookup"><span data-stu-id="77689-200">**Property name: AccessMask**</span></span>

<span data-ttu-id="77689-201">Beskrivning: Definierar åtkomsten.</span><span class="sxs-lookup"><span data-stu-id="77689-201">Description: Defines the access.</span></span>

<span data-ttu-id="77689-202">Alternativ 1–7:</span><span class="sxs-lookup"><span data-stu-id="77689-202">Options 1-7:</span></span>
  - <span data-ttu-id="77689-203">1: Läsa</span><span class="sxs-lookup"><span data-stu-id="77689-203">1: Read</span></span>
  - <span data-ttu-id="77689-204">2: Skriva</span><span class="sxs-lookup"><span data-stu-id="77689-204">2: Write</span></span>
  - <span data-ttu-id="77689-205">3: Läsa och skriva</span><span class="sxs-lookup"><span data-stu-id="77689-205">3: Read and Write</span></span>
  - <span data-ttu-id="77689-206">4: Utför</span><span class="sxs-lookup"><span data-stu-id="77689-206">4: Execute</span></span>
  - <span data-ttu-id="77689-207">5: Läsa och utföra</span><span class="sxs-lookup"><span data-stu-id="77689-207">5: Read and Execute</span></span>
  - <span data-ttu-id="77689-208">6: Skriva och utföra</span><span class="sxs-lookup"><span data-stu-id="77689-208">6: Write and Execute</span></span>
  - <span data-ttu-id="77689-209">7: Läsa och skriva och utföra</span><span class="sxs-lookup"><span data-stu-id="77689-209">7: Read and Write and Execute</span></span>

## <a name="common-removable-storage-access-control-scenarios"></a><span data-ttu-id="77689-210">Vanliga scenarier för Storage och Access-kontroll</span><span class="sxs-lookup"><span data-stu-id="77689-210">Common Removable Storage Access Control scenarios</span></span>

<span data-ttu-id="77689-211">Vi har satt ihop några vanliga scenarier som du kan följa för att bekanta dig med Microsoft Defender för slutpunkten flyttbara Storage Access Control.</span><span class="sxs-lookup"><span data-stu-id="77689-211">To help familiarize you with Microsoft Defender for Endpoint Removable Storage Access Control, we have put together some common scenarios for you to follow.</span></span>

### <a name="scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs"></a><span data-ttu-id="77689-212">Scenario 1: Förhindra skrivning och körning av åtkomst till alla men tillåta specifika godkända USBs</span><span class="sxs-lookup"><span data-stu-id="77689-212">Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs</span></span>

1. <span data-ttu-id="77689-213">Skapa grupper</span><span class="sxs-lookup"><span data-stu-id="77689-213">Create groups</span></span>

    1. <span data-ttu-id="77689-214">Grupp 1: Alla flyttbara lagringsmedia och CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="77689-214">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="77689-215">Ett exempel på flyttbart lagringsutrymme och cd/dvd är: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** i exemplet Any [Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span><span class="sxs-lookup"><span data-stu-id="77689-215">An example of a removable storage and CD/DVD is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="77689-216">Grupp 2: Godkända usa baserat på enhetsegenskaper.</span><span class="sxs-lookup"><span data-stu-id="77689-216">Group 2: Approved USBs based on device properties.</span></span> <span data-ttu-id="77689-217">Ett exempel för det här användningsfall är: Instans-ID – Grupp **65fa649a-a111-4912-9294-fb6337a25038** i exemplet Godkända [amerikanska Group.xml-filer.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="77689-217">An example for this use case is: Instance ID – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Approved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="77689-218">Du måste ersätta `&` med `&amp;` i värdet.</span><span class="sxs-lookup"><span data-stu-id="77689-218">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="77689-219">Skapa princip</span><span class="sxs-lookup"><span data-stu-id="77689-219">Create policy</span></span>

    1. <span data-ttu-id="77689-220">Princip 1: Blockera skrivning och körning av Access men tillåt godkända amerikanskabs.</span><span class="sxs-lookup"><span data-stu-id="77689-220">Policy 1: Block Write and Execute Access but allow approved USBs.</span></span> <span data-ttu-id="77689-221">Ett exempel för det här användningsfall är: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** i exemplet [Scenario 1 Blockera skrivning](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) och kör Access men tillåt godkänd USBs.xmlfil.</span><span class="sxs-lookup"><span data-stu-id="77689-221">An example for this use case is: PolicyRule **c544a991-5786-4402-949e-a032cb790d0e** in the sample [Scenario 1 Block Write and Execute Access but allow approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="77689-222">Princip 2: Granska skrivning och kör åtkomst till tillåtna USB.</span><span class="sxs-lookup"><span data-stu-id="77689-222">Policy 2: Audit Write and Execute access to allowed USBs.</span></span> <span data-ttu-id="77689-223">Ett exempel för det här användningsfall är: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** i exemplet Scenario 1 Granskningsskrivning och Kör åtkomst till [godkänd USBs.xml-fil.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="77689-223">An example for this use case is: PolicyRule **36ae1037-a639-4cff-946b-b36c53089a4c** in the sample [Scenario 1 Audit Write and Execute access to approved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

### <a name="scenario-2-audit-write-and-execute-access-to-all-but-block-specific-unapproved-usbs"></a><span data-ttu-id="77689-224">Scenario 2: Granska skrivning och kör åtkomst till alla utom blockera specifika usbs som inte godkänts</span><span class="sxs-lookup"><span data-stu-id="77689-224">Scenario 2: Audit Write and Execute access to all but block specific unapproved USBs</span></span>

1. <span data-ttu-id="77689-225">Skapa grupper</span><span class="sxs-lookup"><span data-stu-id="77689-225">Create groups</span></span>

    1. <span data-ttu-id="77689-226">Grupp 1: Alla flyttbara lagringsmedia och CD/DVD.</span><span class="sxs-lookup"><span data-stu-id="77689-226">Group 1: Any removable storage and CD/DVD.</span></span> <span data-ttu-id="77689-227">Ett exempel för det här användningsfall är: Grupp **9b28fae8-72f7-4267-a1a5-685f747a7146** i exemplet [Flyttbara Storage- och CD-DVD-Group.xmlfiler.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="77689-227">An example for this use case is: Group **9b28fae8-72f7-4267-a1a5-685f747a7146** in the sample [Any Removable Storage and CD-DVD Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="77689-228">Grupp 2: Ej godkända amerikanska sampel baserat på enhetsegenskaper, exempelvis leverantörs-ID/produkt-ID, eget namn – grupp **65fa649a-a111-4912-9294-fb6337a25038** i [exempelfilen Group.xmlusbs som](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) inte godkänts.</span><span class="sxs-lookup"><span data-stu-id="77689-228">Group 2: Unapproved USBs based on device properties, for example, Vendor ID / Product ID, Friendly Name – Group **65fa649a-a111-4912-9294-fb6337a25038** in the sample [Unapproved USBs Group.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="77689-229">Du måste ersätta `&` med `&amp;` i värdet.</span><span class="sxs-lookup"><span data-stu-id="77689-229">You have to replace `&` with `&amp;` in the value.</span></span>

2. <span data-ttu-id="77689-230">Skapa princip</span><span class="sxs-lookup"><span data-stu-id="77689-230">Create policy</span></span>

    1. <span data-ttu-id="77689-231">Princip 1: Blockera skrivning och körning av åtkomst till alla utom blockera specifika usBs som inte godkänts.</span><span class="sxs-lookup"><span data-stu-id="77689-231">Policy 1: Block Write and Execute access to all but block specific unapproved USBs.</span></span> <span data-ttu-id="77689-232">Ett exempel på det här användningsfall är: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** i exempelscenario 2 Granskningsskrivning och Kör åtkomst till alla men blockerar en viss ej USBs.xml [fil.](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples)</span><span class="sxs-lookup"><span data-stu-id="77689-232">An example of this use case is: PolicyRule **23b8e437-66ac-4b32-b3d7-24044637fc98** in the sample [Scenario 2 Audit Write and Execute access to all but block specific unapproved USBs.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>
    
    2. <span data-ttu-id="77689-233">Princip 2: Granska skrivning och utför åtkomst till andra.</span><span class="sxs-lookup"><span data-stu-id="77689-233">Policy 2: Audit Write and Execute access to others.</span></span> <span data-ttu-id="77689-234">Ett exempel på det här användningsfall är: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** i exemplet [Scenario 2](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) Granskningsskrivning och Kör åtkomst till others.xmlfil.</span><span class="sxs-lookup"><span data-stu-id="77689-234">An example of this use case is: PolicyRule **b58ab853-9a6f-405c-a194-740e69422b48** in the sample [Scenario 2 Audit Write and Execute access to others.xml](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) file.</span></span>

## <a name="deploying-and-managing-policy-via-group-policy"></a><span data-ttu-id="77689-235">Distribuera och hantera princip via grupprincip</span><span class="sxs-lookup"><span data-stu-id="77689-235">Deploying and managing policy via Group Policy</span></span>

<span data-ttu-id="77689-236">Med funktionen Storage och Access Control kan du tillämpa en princip via grupprincip på antingen en användare eller enhet eller både och.</span><span class="sxs-lookup"><span data-stu-id="77689-236">The Removable Storage Access Control feature enables you to apply policy via Group Policy to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="77689-237">Licensiering</span><span class="sxs-lookup"><span data-stu-id="77689-237">Licensing</span></span>

<span data-ttu-id="77689-238">Innan du kommer igång med Flyttbara Storage Access Control måste du bekräfta din [Microsoft 365-prenumeration.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="77689-238">Before you get started with Removable Storage Access Control, you must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="77689-239">För att komma åt och använda Storage Access Control måste du ha Microsoft 365 E3 eller Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="77689-239">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="deploying-policy-via-group-policy"></a><span data-ttu-id="77689-240">Distribuera princip via grupprincip</span><span class="sxs-lookup"><span data-stu-id="77689-240">Deploying policy via Group Policy</span></span>

1. <span data-ttu-id="77689-241">Kombinera alla grupper i `<Groups>` `</Groups>` en XML-fil.</span><span class="sxs-lookup"><span data-stu-id="77689-241">Combine all groups within `<Groups>` `</Groups>` into one xml file.</span></span> 

    <span data-ttu-id="77689-242">Följande bild illustrerar exemplet på [Scenario 1: Förhindra skrivning](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)och kör åtkomst till alla men tillåta specifika godkända amerikanskabs .</span><span class="sxs-lookup"><span data-stu-id="77689-242">The following image illustrates the example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/prevent-write-access-allow-usb.png" alt-text="Skärmen som visar konfigurationsinställningar som tillåter specifika godkända usbs på enheter":::
    
2. <span data-ttu-id="77689-244">Kombinera alla regler i `<PolicyRules>` `</PolicyRules>` en XML-fil.</span><span class="sxs-lookup"><span data-stu-id="77689-244">Combine all rules within `<PolicyRules>` `</PolicyRules>` into one xml file.</span></span> 

    <span data-ttu-id="77689-245">Om du vill begränsa en viss användare använder du SID-egenskapen i Posten.</span><span class="sxs-lookup"><span data-stu-id="77689-245">If you want to restrict a specific user, then use SID property into the Entry.</span></span> <span data-ttu-id="77689-246">Om det inte finns någon SID i principposten kommer posten att tillämpas på alla inloggningsinstans för datorn.</span><span class="sxs-lookup"><span data-stu-id="77689-246">If there is no SID in the policy Entry, the Entry will be applied to everyone login instance for the machine.</span></span>
    
    <span data-ttu-id="77689-247">Följande bild visar användningen av SID-egenskapen och ett exempel på [Scenario 1: Förhindra skrivning](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs)och kör åtkomst till alla men tillåta specifika godkända USBs.</span><span class="sxs-lookup"><span data-stu-id="77689-247">The following image illustrates the usage of SID property, and an example of [Scenario 1: Prevent Write and Execute access to all but allow specific approved USBs](#scenario-1-prevent-write-and-execute-access-to-all-but-allow-specific-approved-usbs).</span></span>
    
    :::image type="content" source="images/usage-sid-property.png" alt-text="Skärmen som visar en kod som anger användningen av sidegenskapsattributet":::

3. <span data-ttu-id="77689-249">Spara både regel- och grupp-XML-filer i mappen för nätverksresurs och placera sökvägen till mappen för nätverksresurs i grupprincipinställningen: Datorkonfiguration -> Administrativa mallar **-> Windows-komponenter -> Microsoft Defender Antivirus -> Enhetskontroll: Definiera** grupper för enhetskontrollprinciper och Definiera regler för enhetskontrollprinciper.</span><span class="sxs-lookup"><span data-stu-id="77689-249">Save both rule and group XML files on network share folder and put network share folder path into the Group Policy setting: **Computer Configuration -> Administrative Templates -> Windows Components -> Microsoft Defender Antivirus -> Device Control: ‘Define device control policy groups’ and ‘Define device control policy rules’**.</span></span>

    - <span data-ttu-id="77689-250">Måldatorn måste kunna komma åt nätverksresursen för att principen ska vara på.</span><span class="sxs-lookup"><span data-stu-id="77689-250">The target machine must be able to access the network share to have the policy.</span></span> <span data-ttu-id="77689-251">När principen har lästs behövs dock inte längre nätverksanslutningen för nätverksresursen, även efter att datorn startats om.</span><span class="sxs-lookup"><span data-stu-id="77689-251">However, once the policy is read, the network share connection is no longer required, even after machine reboot.</span></span>

    :::image type="content" source="images/device-control.png" alt-text="Skärmen Enhetskontroll":::

## <a name="deploying-and-managing-policy-via-intune-oma-uri"></a><span data-ttu-id="77689-253">Distribuera och hantera princip via Intune OMA-URI</span><span class="sxs-lookup"><span data-stu-id="77689-253">Deploying and managing policy via Intune OMA-URI</span></span>

<span data-ttu-id="77689-254">Med funktionen flyttbara Storage Access Control kan du tillämpa principen via OMA-URI på antingen användare eller enhet, eller båda.</span><span class="sxs-lookup"><span data-stu-id="77689-254">The Removable Storage Access Control feature enables you to apply policy via OMA-URI to either user or device, or both.</span></span>

### <a name="licensing"></a><span data-ttu-id="77689-255">Licensiering</span><span class="sxs-lookup"><span data-stu-id="77689-255">Licensing</span></span>

<span data-ttu-id="77689-256">Innan du kommer igång med Flyttbara Storage Access Control måste du bekräfta din [Microsoft 365-prenumeration.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2)</span><span class="sxs-lookup"><span data-stu-id="77689-256">Before you get started with Removable Storage Access Control, you  must confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=2).</span></span> <span data-ttu-id="77689-257">För att komma åt och använda Storage Access Control måste du ha Microsoft 365 E3 eller Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="77689-257">To access and use Removable Storage Access Control, you must have Microsoft 365 E3 or Microsoft 365 E5.</span></span>

### <a name="permission"></a><span data-ttu-id="77689-258">Behörighet</span><span class="sxs-lookup"><span data-stu-id="77689-258">Permission</span></span>

<span data-ttu-id="77689-259">För principdistribution i Intune måste kontot ha behörighet att skapa, redigera, uppdatera eller ta bort profiler för enhetskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="77689-259">For policy deployment in Intune, the account must have permissions to create, edit, update, or delete device configuration profiles.</span></span> <span data-ttu-id="77689-260">Du kan skapa anpassade roller eller använda någon av de inbyggda rollerna med dessa behörigheter.</span><span class="sxs-lookup"><span data-stu-id="77689-260">You can create custom roles or use any of the built-in roles with these permissions.</span></span>

- <span data-ttu-id="77689-261">Rollen Princip- och profilhanterare</span><span class="sxs-lookup"><span data-stu-id="77689-261">Policy and profile Manager role</span></span>
- <span data-ttu-id="77689-262">Anpassad roll med behörigheten Skapa/Redigera/Uppdatera/Läsa/Ta bort/Visa rapporter aktiverad för enhetskonfigurationsprofiler</span><span class="sxs-lookup"><span data-stu-id="77689-262">Custom role with Create/Edit/Update/Read/Delete/View Reports permissions turned on for Device Configuration profiles</span></span>
- <span data-ttu-id="77689-263">Global administratör</span><span class="sxs-lookup"><span data-stu-id="77689-263">Global administrator</span></span>

### <a name="deploying-policy-via-oma-uri"></a><span data-ttu-id="77689-264">Distribuera princip via OMA-URI</span><span class="sxs-lookup"><span data-stu-id="77689-264">Deploying policy via OMA-URI</span></span>

<span data-ttu-id="77689-265">**Microsoft Endpoint Manager administrationscenter ( https://endpoint.microsoft.com/) -> -> Konfigurationsprofiler -> Skapa profil ->-plattform: Windows 10 och senare & Profil: Anpassad**</span><span class="sxs-lookup"><span data-stu-id="77689-265">**Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) -> Devices -> Configuration profiles -> Create profile -> Platform: Windows 10 and later & Profile: Custom**</span></span>

1. <span data-ttu-id="77689-266">Skapa en OMA-URI-regel för varje grupp:</span><span class="sxs-lookup"><span data-stu-id="77689-266">For each Group, create an OMA-URI rule:</span></span>
    - <span data-ttu-id="77689-267">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="77689-267">OMA-URI:</span></span>

      <span data-ttu-id="77689-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="77689-268">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b **GroupGUID**%7d/GroupData</span></span>

      <span data-ttu-id="77689-269">För flyttbara **lagrings- och CD-/DVD-grupper** i samplet måste länken till exempel vara:</span><span class="sxs-lookup"><span data-stu-id="77689-269">For example, for **any removable storage and CD/DVD** group in the sample, the link must be:</span></span>

      <span data-ttu-id="77689-270">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span><span class="sxs-lookup"><span data-stu-id="77689-270">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyGroups/%7b9b28fae8-72f7-4267-a1a5-685f747a7146%7d/GroupData</span></span>

    - <span data-ttu-id="77689-271">Datatyp: Sträng (XML-fil)</span><span class="sxs-lookup"><span data-stu-id="77689-271">Data Type: String (XML file)</span></span>
    
      :::image type="content" source="images/xml-data-type-string.png" alt-text="XML-filen för datatypen STRING":::

2. <span data-ttu-id="77689-273">För varje princip skapar du även en OMA-URI:</span><span class="sxs-lookup"><span data-stu-id="77689-273">For each policy, also create an OMA-URI:</span></span>

    - <span data-ttu-id="77689-274">OMA-URI: </span><span class="sxs-lookup"><span data-stu-id="77689-274">OMA-URI:</span></span>

      <span data-ttu-id="77689-275">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span><span class="sxs-lookup"><span data-stu-id="77689-275">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bFA6BE102-0784-4A2A-B010-A0BEBEBF68E1%7d/RuleData</span></span>

      <span data-ttu-id="77689-276">För till exempel regeln **Blockera skrivning och körning av Access men** tillåt godkända amerikanskabs i exemplet måste länken vara:</span><span class="sxs-lookup"><span data-stu-id="77689-276">For example, for the **Block Write and Execute Access but allow approved USBs** rule in the sample, the link must be:</span></span> 

      <span data-ttu-id="77689-277">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span><span class="sxs-lookup"><span data-stu-id="77689-277">./Vendor/MSFT/Defender/Configuration/DeviceControl/PolicyRules/%7bc544a991-5786-4402-949e-a032cb790d0e%7d/RuleData.</span></span>

    - <span data-ttu-id="77689-278">Datatyp: Sträng (XML-fil)</span><span class="sxs-lookup"><span data-stu-id="77689-278">Data Type: String (XML file)</span></span>

      :::image type="content" source="images/xml-data-type-string-2.png" lightbox="images/xml-data-type-string-2.png" alt-text="Visning av XML-fil för datatypen STRING":::

## <a name="deploying-and-managing-policy-by-using-intune-user-interface"></a><span data-ttu-id="77689-280">Distribuera och hantera princip med hjälp av användargränssnittet i Intune</span><span class="sxs-lookup"><span data-stu-id="77689-280">Deploying and managing policy by using Intune user interface</span></span>

<span data-ttu-id="77689-281">Den här funktionen (i Microsoft Endpoint Manager admincenter (>-enheter > konfigurationsprofiler > Skapa profil >-plattform: Windows 10 och senare & Profil: Enhetskontroll) är ännu inte https://endpoint.microsoft.com/) tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="77689-281">This capability (in Microsoft Endpoint Manager admin center (https://endpoint.microsoft.com/) > Devices > Configuration profiles > Create profile > Platform: Windows 10 and later & Profile: Device Control) is not yet available.</span></span> 

## <a name="view-device-control-removable-storage-access-control-data-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="77689-282">Visa flyttbara enheter med enhetskontroll Storage Access Control-data i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="77689-282">View Device Control Removable Storage Access Control data in Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="77689-283">I Microsoft 365 säkerhetsportalen visas flyttbart lagringsutrymme som blockeras av den flyttbara enhetskontrollen Storage Access Control.</span><span class="sxs-lookup"><span data-stu-id="77689-283">The Microsoft 365 security portal shows removable storage blocked by the Device Control Removable Storage Access Control.</span></span> <span data-ttu-id="77689-284">För att komma Microsoft 365 säkerhet måste du ha följande prenumeration:</span><span class="sxs-lookup"><span data-stu-id="77689-284">To access the Microsoft 365 security, you must have the following subscription:</span></span>

- <span data-ttu-id="77689-285">Microsoft 365 för E5-rapportering</span><span class="sxs-lookup"><span data-stu-id="77689-285">Microsoft 365 for E5 reporting</span></span>

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

## <a name="frequently-asked-questions"></a><span data-ttu-id="77689-287">Vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="77689-287">Frequently asked questions</span></span>
<span data-ttu-id="77689-288">**Vad är begränsningen för flyttbara lagringsmedia för det maximala antalet AMERIKANSKABB?**</span><span class="sxs-lookup"><span data-stu-id="77689-288">**What is the removable storage media limitation for the maximum number of USBs?**</span></span>

<span data-ttu-id="77689-289">Vi har validerat en USB-grupp med 100 000 media – upp till 7 MB i storlek.</span><span class="sxs-lookup"><span data-stu-id="77689-289">We have validated one USB group with 100,000 media - up to 7 MB in size.</span></span> <span data-ttu-id="77689-290">Principen fungerar i både Intune och GPO utan prestandaproblem.</span><span class="sxs-lookup"><span data-stu-id="77689-290">The policy works in both Intune and GPO without performance issues.</span></span>

<span data-ttu-id="77689-291">**Varför fungerar inte principen?**</span><span class="sxs-lookup"><span data-stu-id="77689-291">**Why does the policy not work?**</span></span>

<span data-ttu-id="77689-292">Den vanligaste orsaken är att det inte finns någon [obligatorisk version av program mot skadlig programvara.](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints)</span><span class="sxs-lookup"><span data-stu-id="77689-292">The most common reason is there is no required [antimalware client version](/microsoft-365/security/defender-endpoint/device-control-removable-storage-access-control#prepare-your-endpoints).</span></span>

<span data-ttu-id="77689-293">En annan orsak kan vara att XML-filen inte är korrekt formaterad, t.ex. att rätt formatering för tecknet "&" i XML-filen inte används, eller att textredigeraren lägger till en XML-0xEF 0xBB 0xBF (Byte Order Mark) i början av filerna, vilket gör att XML-tolkningarna inte fungerar.</span><span class="sxs-lookup"><span data-stu-id="77689-293">Another reason could be that the XML file is not correctly formatted, for example, not using the correct markdown formatting for the "&" character in the XML file, or the text editor might add a byte order mark (BOM) 0xEF 0xBB 0xBF at the beginning of the files which causes the XML parsing not to work.</span></span> <span data-ttu-id="77689-294">En enkel lösning är att ladda ned [exempelfilen](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (välj **Raw** och **sedan Spara som**) och sedan uppdatera.</span><span class="sxs-lookup"><span data-stu-id="77689-294">One simple solution is to download the [sample file](https://github.com/microsoft/mdatp-devicecontrol/tree/main/Removable%20Storage%20Access%20Control%20Samples) (select **Raw** and then **Save as**) and then update.</span></span>

<span data-ttu-id="77689-295">Om det finns ett värde och principen hanteras via grupprincip kontrollerar du om klientenheten kan komma åt XML-sökvägen.</span><span class="sxs-lookup"><span data-stu-id="77689-295">If there is a value and the policy is managed via Group Policy, check whether the client device can access the policy XML path.</span></span>

<span data-ttu-id="77689-296">**Hur vet jag vilken dator som använder en inversion av den senaste klientversionen av program mot skadlig programvara i organisationen?**</span><span class="sxs-lookup"><span data-stu-id="77689-296">**How can I know which machine is using out of date antimalware client version in the organization?**</span></span>

<span data-ttu-id="77689-297">Du kan använda följande fråga för att få klientversionen av program mot skadlig programvara på Microsoft 365-säkerhetsportalen:</span><span class="sxs-lookup"><span data-stu-id="77689-297">You can use following query to get antimalware client version on the Microsoft 365 security portal:</span></span>
```kusto
//check the antimalware client version
DeviceFileEvents
| where FileName == "MsMpEng.exe"
| where FolderPath contains @"C:\ProgramData\Microsoft\Windows Defender\Platform\"
| extend PlatformVersion=tostring(split(FolderPath, "\\", 5))
//| project DeviceName, PlatformVersion // check which machine is using legacy platformVersion
| summarize dcount(DeviceName) by PlatformVersion // check how many machines are using which platformVersion
| order by PlatformVersion desc
```

