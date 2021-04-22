---
title: Enhetskontroll för macOS
description: Läs om hur du konfigurerar Microsoft Defender för slutpunkt på Mac för att minska hoten från flyttbara lagringsmedia, till exempel USB-enheter.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, mac, enhet, kontroll, usb, flyttbart, media
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 39f8367c34e98c5e9dd11e9716f08e6c9e7fd9c0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935131"
---
# <a name="device-control-for-macos"></a><span data-ttu-id="9a035-104">Enhetskontroll för macOS</span><span class="sxs-lookup"><span data-stu-id="9a035-104">Device control for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9a035-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9a035-105">**Applies to:**</span></span>
- [<span data-ttu-id="9a035-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="9a035-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9a035-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9a035-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9a035-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="9a035-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9a035-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="9a035-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="requirements"></a><span data-ttu-id="9a035-110">Krav</span><span class="sxs-lookup"><span data-stu-id="9a035-110">Requirements</span></span>

<span data-ttu-id="9a035-111">Enhetskontroll för macOS har följande krav:</span><span class="sxs-lookup"><span data-stu-id="9a035-111">Device control for macOS has the following prerequisites:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="9a035-112">Microsoft Defender för slutpunktsberättigande (kan vara utvärderingsversion)</span><span class="sxs-lookup"><span data-stu-id="9a035-112">Microsoft Defender for Endpoint entitlement (can be trial)</span></span>
> - <span data-ttu-id="9a035-113">Lägsta OS-version: macOS 10.15.4 eller senare</span><span class="sxs-lookup"><span data-stu-id="9a035-113">Minimum OS version: macOS 10.15.4 or higher</span></span>
> - <span data-ttu-id="9a035-114">Lägsta produktversion: 101.24.59</span><span class="sxs-lookup"><span data-stu-id="9a035-114">Minimum product version: 101.24.59</span></span>
> - <span data-ttu-id="9a035-115">Enheten måste köras med systemtillägg (det här är standardinställningen i macOS 11 Big Sur).</span><span class="sxs-lookup"><span data-stu-id="9a035-115">Your device must be running with system extensions (this is the default on macOS 11 Big Sur).</span></span> 
> 
>   <span data-ttu-id="9a035-116">Du kan kontrollera om enheten körs på systemtillägg genom att köra följande kommando och kontrollera att den skrivs ut `endpoint_security_extension` till konsolen:</span><span class="sxs-lookup"><span data-stu-id="9a035-116">You can check if your device is running on system extensions by running the following command and verify that it is printing `endpoint_security_extension` to the console:</span></span> 
> 
>   ```bash
>   mdatp health --field real_time_protection_subsystem 
>   ```
> - <span data-ttu-id="9a035-117">Enheten måste finnas i `Beta` (kallades tidigare `InsiderFast` ) Uppdateringskanal för Microsoft AutoUpdate.</span><span class="sxs-lookup"><span data-stu-id="9a035-117">Your device must be in `Beta` (previously called `InsiderFast`) Microsoft AutoUpdate update channel.</span></span> <span data-ttu-id="9a035-118">Mer information finns i [Distribuera uppdateringar för Microsoft Defender för Slutpunkt på Mac.](mac-updates.md)</span><span class="sxs-lookup"><span data-stu-id="9a035-118">For more information, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span>
> 
>   <span data-ttu-id="9a035-119">Du kan kontrollera uppdateringskanalen med hjälp av följande kommando:</span><span class="sxs-lookup"><span data-stu-id="9a035-119">You can check the update channel using the following command:</span></span> 
> 
>    ```bash
>    mdatp health --field release_ring 
>    ```
>
>    <span data-ttu-id="9a035-120">Om kommandot ovan inte skriver ut något `Beta` av eller kör du följande kommando från `InsiderFast` terminalen.</span><span class="sxs-lookup"><span data-stu-id="9a035-120">If the above command does not print either `Beta` or `InsiderFast`, execute the following command from the Terminal.</span></span> <span data-ttu-id="9a035-121">Kanaluppdateringen börjar gälla nästa gång produkten startar (när nästa produktuppdatering installeras eller när enheten startas om).</span><span class="sxs-lookup"><span data-stu-id="9a035-121">The channel update takes effect next time the product starts (when the next product update is installed or when the device is rebooted).</span></span> 
> 
>    ```bash
>    defaults write com.microsoft.autoupdate2 ChannelName -string Beta
>    ```
>
>    <span data-ttu-id="9a035-122">Om du befinner dig i en hanterad miljö (JAMF eller Intune) kan du även fjärrkonfigurera uppdateringskanalen.</span><span class="sxs-lookup"><span data-stu-id="9a035-122">Alternatively, if you are in a managed environment (JAMF or Intune), you can configure the update channel remotely.</span></span> <span data-ttu-id="9a035-123">Mer information finns i [Distribuera uppdateringar för Microsoft Defender för Slutpunkt på Mac.](mac-updates.md)</span><span class="sxs-lookup"><span data-stu-id="9a035-123">For more information, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span> 

## <a name="device-control-policy"></a><span data-ttu-id="9a035-124">Princip för enhetskontroll</span><span class="sxs-lookup"><span data-stu-id="9a035-124">Device control policy</span></span>

<span data-ttu-id="9a035-125">Om du vill konfigurera enhetskontroll för macOS måste du skapa en princip som beskriver de begränsningar du vill införa i organisationen.</span><span class="sxs-lookup"><span data-stu-id="9a035-125">To configure device control for macOS, you must create a policy that describes the restrictions you want to put in place within your organization.</span></span>

<span data-ttu-id="9a035-126">Principen för enhetskontroll ingår i konfigurationsprofilen som används för att konfigurera alla andra produktinställningar.</span><span class="sxs-lookup"><span data-stu-id="9a035-126">The device control policy is included in the configuration profile used to configure all other product settings.</span></span> <span data-ttu-id="9a035-127">Mer information finns i [Konfigurationsprofilens struktur.](mac-preferences.md#configuration-profile-structure)</span><span class="sxs-lookup"><span data-stu-id="9a035-127">For more information, see [Configuration profile structure](mac-preferences.md#configuration-profile-structure).</span></span>

<span data-ttu-id="9a035-128">I konfigurationsprofilen definieras enhetens kontrollprincip i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="9a035-128">Within the configuration profile, the device control policy is defined in the following section:</span></span>

|<span data-ttu-id="9a035-129">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="9a035-129">Section</span></span>|<span data-ttu-id="9a035-130">Värde</span><span class="sxs-lookup"><span data-stu-id="9a035-130">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9a035-131">**Domän**</span><span class="sxs-lookup"><span data-stu-id="9a035-131">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9a035-132">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="9a035-132">**Key**</span></span> | <span data-ttu-id="9a035-133">deviceControl</span><span class="sxs-lookup"><span data-stu-id="9a035-133">deviceControl</span></span> |
| <span data-ttu-id="9a035-134">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="9a035-134">**Data type**</span></span> | <span data-ttu-id="9a035-135">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="9a035-135">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9a035-136">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="9a035-136">**Comments**</span></span> | <span data-ttu-id="9a035-137">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="9a035-137">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="9a035-138">Principen för enhetskontroll kan användas för att:</span><span class="sxs-lookup"><span data-stu-id="9a035-138">The device control policy can be used to:</span></span>

- [<span data-ttu-id="9a035-139">Anpassa URL-målet för meddelanden upphöjt av enhetskontroll</span><span class="sxs-lookup"><span data-stu-id="9a035-139">Customize the URL target for notifications raised by device control</span></span>](#customize-url-target-for-notifications-raised-by-device-control)
- [<span data-ttu-id="9a035-140">Tillåt eller blockera flyttbara enheter</span><span class="sxs-lookup"><span data-stu-id="9a035-140">Allow or block removable devices</span></span>](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a><span data-ttu-id="9a035-141">Anpassa URL-målet för meddelanden upphöjt av enhetskontroll</span><span class="sxs-lookup"><span data-stu-id="9a035-141">Customize URL target for notifications raised by device control</span></span>

<span data-ttu-id="9a035-142">När den princip för enhetskontroll som du har tillämpat tillämpas på en enhet (till exempel åtkomsten till en flyttbar medieenhet är begränsad) visas ett meddelande för användaren.</span><span class="sxs-lookup"><span data-stu-id="9a035-142">When the device control policy that you have put in place is enforced on a device (for example, access to a removable media device is restricted), a notification is displayed to the user.</span></span>

![Meddelande om enhetskontroll](images/mac-device-control-notification.png)

<span data-ttu-id="9a035-144">När slutanvändare klickar på det här meddelandet öppnas en webbsida i standardwebbläsaren.</span><span class="sxs-lookup"><span data-stu-id="9a035-144">When end users click this notification, a web page is opened in the default browser.</span></span> <span data-ttu-id="9a035-145">Du kan konfigurera URL-adressen som öppnas när slutanvändare klickar på meddelandet.</span><span class="sxs-lookup"><span data-stu-id="9a035-145">You can configure the URL that is opened when end users click the notification.</span></span>

|<span data-ttu-id="9a035-146">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="9a035-146">Section</span></span>|<span data-ttu-id="9a035-147">Värde</span><span class="sxs-lookup"><span data-stu-id="9a035-147">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9a035-148">**Domän**</span><span class="sxs-lookup"><span data-stu-id="9a035-148">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9a035-149">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="9a035-149">**Key**</span></span> | <span data-ttu-id="9a035-150">navigationTarget</span><span class="sxs-lookup"><span data-stu-id="9a035-150">navigationTarget</span></span> |
| <span data-ttu-id="9a035-151">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="9a035-151">**Data type**</span></span> | <span data-ttu-id="9a035-152">Sträng</span><span class="sxs-lookup"><span data-stu-id="9a035-152">String</span></span> |
| <span data-ttu-id="9a035-153">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="9a035-153">**Comments**</span></span> | <span data-ttu-id="9a035-154">Om den inte är definierad använder produkten en standard-URL som pekar till en allmän sida som förklarar produktens åtgärder.</span><span class="sxs-lookup"><span data-stu-id="9a035-154">If not defined, the product uses a default URL pointing to a generic page explaining the action taken by the product.</span></span> |

### <a name="allow-or-block-removable-devices"></a><span data-ttu-id="9a035-155">Tillåt eller blockera flyttbara enheter</span><span class="sxs-lookup"><span data-stu-id="9a035-155">Allow or block removable devices</span></span>

<span data-ttu-id="9a035-156">Avsnittet för flyttbara mediefiler i enhetens kontrollprincip används för att begränsa åtkomsten till flyttbara medium.</span><span class="sxs-lookup"><span data-stu-id="9a035-156">The removable media section of the device control policy is used to restrict access to removable media.</span></span> 

> [!NOTE]
> <span data-ttu-id="9a035-157">Följande typer av flyttbara media stöds för närvarande och kan ingå i principen: USB-lagringsenheter.</span><span class="sxs-lookup"><span data-stu-id="9a035-157">The following types of removable media are currently supported and can be included in the policy: USB storage devices.</span></span>

|<span data-ttu-id="9a035-158">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="9a035-158">Section</span></span>|<span data-ttu-id="9a035-159">Värde</span><span class="sxs-lookup"><span data-stu-id="9a035-159">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9a035-160">**Domän**</span><span class="sxs-lookup"><span data-stu-id="9a035-160">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9a035-161">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="9a035-161">**Key**</span></span> | <span data-ttu-id="9a035-162">removableMediaPolicy</span><span class="sxs-lookup"><span data-stu-id="9a035-162">removableMediaPolicy</span></span> |
| <span data-ttu-id="9a035-163">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="9a035-163">**Data type**</span></span> | <span data-ttu-id="9a035-164">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="9a035-164">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="9a035-165">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="9a035-165">**Comments**</span></span> | <span data-ttu-id="9a035-166">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="9a035-166">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="9a035-167">Det här avsnittet i principen är hierarkiskt, vilket ger maximal flexibilitet och omfattar ett brett utbud av användningsfall.</span><span class="sxs-lookup"><span data-stu-id="9a035-167">This section of the policy is hierarchical, allowing for maximum flexibility and covering a wide range of use cases.</span></span> <span data-ttu-id="9a035-168">På den högsta nivån finns leverantörer som har ett leverantörs-ID.</span><span class="sxs-lookup"><span data-stu-id="9a035-168">At the top level are vendors, identified by a vendor ID.</span></span> <span data-ttu-id="9a035-169">För varje leverantör finns det produkter som identifieras med ett produkt-ID.</span><span class="sxs-lookup"><span data-stu-id="9a035-169">For each vendor, there are products, identified by a product ID.</span></span> <span data-ttu-id="9a035-170">För varje produkt finns slutligen serienummer som anger specifika enheter.</span><span class="sxs-lookup"><span data-stu-id="9a035-170">Finally, for each product there are serial numbers denoting specific devices.</span></span>

```
|-- policy top level 
    |-- vendor 1 
        |-- product 1 
            |-- serial number 1 
            ...
            |-- serial number N 
        ...
        |-- product N 
    ...
    |-- vendor N
```

<span data-ttu-id="9a035-171">Mer information om hur du hittar enhetsidentifierare finns i [Slå upp enhetsidentifierare](#look-up-device-identifiers).</span><span class="sxs-lookup"><span data-stu-id="9a035-171">For information on how to find the device identifiers, see [Look up device identifiers](#look-up-device-identifiers).</span></span>

<span data-ttu-id="9a035-172">Principen utvärderas från det mest specifika inmatnings området till det mest allmänna.</span><span class="sxs-lookup"><span data-stu-id="9a035-172">The policy is evaluated from the most specific entry to the most general one.</span></span> <span data-ttu-id="9a035-173">När en enhet är ansluten försöker produkten alltså hitta den mest specifika matchningen i principen för varje flyttbar medieenhet och tillämpa behörigheterna på den nivån.</span><span class="sxs-lookup"><span data-stu-id="9a035-173">Meaning, when a device is plugged in, the product tries to find the most specific match in the policy for each removable media device and apply the permissions at that level.</span></span> <span data-ttu-id="9a035-174">Om det inte finns någon matchning tillämpas nästa bästa matchning, hela vägen till den behörighet som anges på den högsta nivån, vilket är standard när en enhet inte matchar någon annan post i principen.</span><span class="sxs-lookup"><span data-stu-id="9a035-174">If there is no match, then the next best match is applied, all the way to the permission specified at the top level, which is the default when a device does not match any other entry in the policy.</span></span>

#### <a name="policy-enforcement-level"></a><span data-ttu-id="9a035-175">Tillämpningsnivå för policy</span><span class="sxs-lookup"><span data-stu-id="9a035-175">Policy enforcement level</span></span>

<span data-ttu-id="9a035-176">Under avsnittet flyttbara media finns ett alternativ för att ställa in tillämpningsnivån, som kan ha något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="9a035-176">Under the removable media section, there is an option to set the enforcement level, which can take one of the following values:</span></span>

- <span data-ttu-id="9a035-177">`audit` – Om åtkomsten till en enhet är begränsad visas ett meddelande för användaren under den här tillämpningsnivån, men enheten kan fortfarande användas.</span><span class="sxs-lookup"><span data-stu-id="9a035-177">`audit` - Under this enforcement level, if access to a device is restricted, a notification is displayed to the user, however the device can still be used.</span></span> <span data-ttu-id="9a035-178">Den här tillämpningsnivån kan vara användbar för att utvärdera en princips effektivitet.</span><span class="sxs-lookup"><span data-stu-id="9a035-178">This enforcement level can be useful to evaluate the effectiveness of a policy.</span></span>
- <span data-ttu-id="9a035-179">`block` – Under den här tillämpningsnivån är åtgärderna som användaren kan utföra på enheten begränsade till vad som har definierats i principen.</span><span class="sxs-lookup"><span data-stu-id="9a035-179">`block` - Under this enforcement level, the operations that the user can perform on the device are limited to what is defined in the policy.</span></span> <span data-ttu-id="9a035-180">Dessutom skickas ett meddelande till användaren.</span><span class="sxs-lookup"><span data-stu-id="9a035-180">Furthermore, a notification is raised to the user.</span></span> 

|<span data-ttu-id="9a035-181">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="9a035-181">Section</span></span>|<span data-ttu-id="9a035-182">Värde</span><span class="sxs-lookup"><span data-stu-id="9a035-182">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9a035-183">**Domän**</span><span class="sxs-lookup"><span data-stu-id="9a035-183">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9a035-184">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="9a035-184">**Key**</span></span> | <span data-ttu-id="9a035-185">enforcementLevel</span><span class="sxs-lookup"><span data-stu-id="9a035-185">enforcementLevel</span></span> |
| <span data-ttu-id="9a035-186">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="9a035-186">**Data type**</span></span> | <span data-ttu-id="9a035-187">Sträng</span><span class="sxs-lookup"><span data-stu-id="9a035-187">String</span></span> |
| <span data-ttu-id="9a035-188">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="9a035-188">**Possible values**</span></span> | <span data-ttu-id="9a035-189">granskning (standard)</span><span class="sxs-lookup"><span data-stu-id="9a035-189">audit (default)</span></span> <br/> <span data-ttu-id="9a035-190">blockera</span><span class="sxs-lookup"><span data-stu-id="9a035-190">block</span></span> |

#### <a name="default-permission-level"></a><span data-ttu-id="9a035-191">Standardbehörighetsnivå</span><span class="sxs-lookup"><span data-stu-id="9a035-191">Default permission level</span></span>

<span data-ttu-id="9a035-192">På den översta nivån i avsnittet flyttbara media kan du konfigurera standardbehörighetsnivån för enheter som inte matchar något annat i principen.</span><span class="sxs-lookup"><span data-stu-id="9a035-192">At the top level of the removable media section, you can configure the default permission level for devices that do not match anything else in the policy.</span></span>

<span data-ttu-id="9a035-193">Den här inställningen kan ställas in på:</span><span class="sxs-lookup"><span data-stu-id="9a035-193">This setting can be set to:</span></span>

- <span data-ttu-id="9a035-194">`none` - Inga åtgärder kan utföras på enheten</span><span class="sxs-lookup"><span data-stu-id="9a035-194">`none` - No operations can be performed on the device</span></span>
- <span data-ttu-id="9a035-195">En kombination av följande värden:</span><span class="sxs-lookup"><span data-stu-id="9a035-195">A combination of the following values:</span></span>
    - <span data-ttu-id="9a035-196">`read` - Läsåtgärder tillåts på enheten</span><span class="sxs-lookup"><span data-stu-id="9a035-196">`read` - Read operations are permitted on the device</span></span>
    - <span data-ttu-id="9a035-197">`write` - Skrivåtgärder tillåts på enheten</span><span class="sxs-lookup"><span data-stu-id="9a035-197">`write` - Write operations are permitted on the device</span></span>
    - <span data-ttu-id="9a035-198">`execute` - Utföra åtgärder tillåts på enheten</span><span class="sxs-lookup"><span data-stu-id="9a035-198">`execute` - Execute operations are permitted on the device</span></span>

> [!NOTE]
> <span data-ttu-id="9a035-199">Om `none` finns i behörighetsnivån ignoreras alla andra behörigheter ( `read` , eller `write` `execute` ).</span><span class="sxs-lookup"><span data-stu-id="9a035-199">If `none` is present in the permission level, any other permissions (`read`, `write`, or `execute`) will be ignored.</span></span>

> [!NOTE]
> <span data-ttu-id="9a035-200">Behörigheten `execute` refererar bara till körning av Binärfilerna i Så här många binärfiler.</span><span class="sxs-lookup"><span data-stu-id="9a035-200">The `execute` permission only refers to execution of Mach-O binaries.</span></span> <span data-ttu-id="9a035-201">Den innehåller inte körning av skript eller andra typer av nyttolaster.</span><span class="sxs-lookup"><span data-stu-id="9a035-201">It does not include execution of scripts or other types of payloads.</span></span>

|<span data-ttu-id="9a035-202">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="9a035-202">Section</span></span>|<span data-ttu-id="9a035-203">Värde</span><span class="sxs-lookup"><span data-stu-id="9a035-203">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9a035-204">**Domän**</span><span class="sxs-lookup"><span data-stu-id="9a035-204">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9a035-205">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="9a035-205">**Key**</span></span> | <span data-ttu-id="9a035-206">behörighet</span><span class="sxs-lookup"><span data-stu-id="9a035-206">permission</span></span> |
| <span data-ttu-id="9a035-207">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="9a035-207">**Data type**</span></span> | <span data-ttu-id="9a035-208">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="9a035-208">Array of strings</span></span> |
| <span data-ttu-id="9a035-209">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="9a035-209">**Possible values**</span></span> | <span data-ttu-id="9a035-210">none (ingen)</span><span class="sxs-lookup"><span data-stu-id="9a035-210">none</span></span> <br/> <span data-ttu-id="9a035-211">läsa</span><span class="sxs-lookup"><span data-stu-id="9a035-211">read</span></span> <br/> <span data-ttu-id="9a035-212">skriva</span><span class="sxs-lookup"><span data-stu-id="9a035-212">write</span></span> <br/> <span data-ttu-id="9a035-213">utföra</span><span class="sxs-lookup"><span data-stu-id="9a035-213">execute</span></span> |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a><span data-ttu-id="9a035-214">Begränsa flyttbara medium efter leverantör, produkt och serienummer</span><span class="sxs-lookup"><span data-stu-id="9a035-214">Restrict removable media by vendor, product, and serial number</span></span>

<span data-ttu-id="9a035-215">Enligt beskrivningen [i Tillåt eller blockera](#allow-or-block-removable-devices)flyttbara enheter kan flyttbara medium, t.ex. USB-enheter, identifieras med leverantörs-ID, produkt-ID och serienummer.</span><span class="sxs-lookup"><span data-stu-id="9a035-215">As described in [Allow or block removable devices](#allow-or-block-removable-devices), removable media such as USB devices can be identified by the vendor ID, product ID, and serial number.</span></span>

<span data-ttu-id="9a035-216">På den högsta nivån i principen för flyttbara media kan du definiera mer detaljerade begränsningar på leverantörsnivå.</span><span class="sxs-lookup"><span data-stu-id="9a035-216">At the top level of the removable media policy, you can optionally define more granular restrictions at the vendor level.</span></span> 

<span data-ttu-id="9a035-217">Ordlistan `vendors` innehåller en eller flera poster där varje post identifieras med leverantörs-ID.</span><span class="sxs-lookup"><span data-stu-id="9a035-217">The `vendors` dictionary contains one or more entries, with each entry being identified by the vendor ID.</span></span>

|<span data-ttu-id="9a035-218">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="9a035-218">Section</span></span>|<span data-ttu-id="9a035-219">Värde</span><span class="sxs-lookup"><span data-stu-id="9a035-219">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9a035-220">**Domän**</span><span class="sxs-lookup"><span data-stu-id="9a035-220">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9a035-221">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="9a035-221">**Key**</span></span> | <span data-ttu-id="9a035-222">leverantörer</span><span class="sxs-lookup"><span data-stu-id="9a035-222">vendors</span></span> |
| <span data-ttu-id="9a035-223">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="9a035-223">**Data type**</span></span> | <span data-ttu-id="9a035-224">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="9a035-224">Dictionary (nested preference)</span></span> |

<span data-ttu-id="9a035-225">Du kan ange önskad behörighetsnivå för enheter från den leverantören för varje leverantör.</span><span class="sxs-lookup"><span data-stu-id="9a035-225">For each vendor, you can specify the desired permission level for devices from that vendor.</span></span>

|<span data-ttu-id="9a035-226">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="9a035-226">Section</span></span>|<span data-ttu-id="9a035-227">Värde</span><span class="sxs-lookup"><span data-stu-id="9a035-227">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9a035-228">**Domän**</span><span class="sxs-lookup"><span data-stu-id="9a035-228">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9a035-229">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="9a035-229">**Key**</span></span> | <span data-ttu-id="9a035-230">behörighet</span><span class="sxs-lookup"><span data-stu-id="9a035-230">permission</span></span> |
| <span data-ttu-id="9a035-231">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="9a035-231">**Data type**</span></span> | <span data-ttu-id="9a035-232">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="9a035-232">Array of strings</span></span> |
| <span data-ttu-id="9a035-233">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="9a035-233">**Possible values**</span></span> | <span data-ttu-id="9a035-234">Samma som [standardbehörighetsnivå](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="9a035-234">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="9a035-235">Alternativt kan du ange en uppsättning produkter som tillhör den leverantören och vilka mer detaljerade behörigheter definieras för.</span><span class="sxs-lookup"><span data-stu-id="9a035-235">Furthermore, you can optionally specify the set of products belonging to that vendor for which more granular permissions are defined.</span></span> <span data-ttu-id="9a035-236">Ordlistan `products` innehåller en eller flera poster där varje post identifieras med produkt-ID: t.</span><span class="sxs-lookup"><span data-stu-id="9a035-236">The `products` dictionary contains one or more entries, with each entry being identified by the product ID.</span></span> 

|<span data-ttu-id="9a035-237">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="9a035-237">Section</span></span>|<span data-ttu-id="9a035-238">Värde</span><span class="sxs-lookup"><span data-stu-id="9a035-238">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9a035-239">**Domän**</span><span class="sxs-lookup"><span data-stu-id="9a035-239">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9a035-240">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="9a035-240">**Key**</span></span> | <span data-ttu-id="9a035-241">produkter</span><span class="sxs-lookup"><span data-stu-id="9a035-241">products</span></span> |
| <span data-ttu-id="9a035-242">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="9a035-242">**Data type**</span></span> | <span data-ttu-id="9a035-243">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="9a035-243">Dictionary (nested preference)</span></span> |

<span data-ttu-id="9a035-244">Du kan ange önskad behörighetsnivå för varje produkt.</span><span class="sxs-lookup"><span data-stu-id="9a035-244">For each product, you can specify the desired permission level for that product.</span></span>

|<span data-ttu-id="9a035-245">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="9a035-245">Section</span></span>|<span data-ttu-id="9a035-246">Värde</span><span class="sxs-lookup"><span data-stu-id="9a035-246">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9a035-247">**Domän**</span><span class="sxs-lookup"><span data-stu-id="9a035-247">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9a035-248">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="9a035-248">**Key**</span></span> | <span data-ttu-id="9a035-249">behörighet</span><span class="sxs-lookup"><span data-stu-id="9a035-249">permission</span></span> |
| <span data-ttu-id="9a035-250">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="9a035-250">**Data type**</span></span> | <span data-ttu-id="9a035-251">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="9a035-251">Array of strings</span></span> |
| <span data-ttu-id="9a035-252">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="9a035-252">**Possible values**</span></span> | <span data-ttu-id="9a035-253">Samma som [standardbehörighetsnivå](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="9a035-253">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="9a035-254">Du kan dessutom ange en valfri uppsättning serienummer som mer detaljerade behörigheter definieras för.</span><span class="sxs-lookup"><span data-stu-id="9a035-254">Furthermore, you can specify an optional set of serial numbers for which more granular permissions are defined.</span></span>

<span data-ttu-id="9a035-255">Ordlistan `serialNumbers` innehåller en eller flera poster där varje post identifieras med serienumret.</span><span class="sxs-lookup"><span data-stu-id="9a035-255">The `serialNumbers` dictionary contains one or more entries, with each entry being identified by the serial number.</span></span>

|<span data-ttu-id="9a035-256">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="9a035-256">Section</span></span>|<span data-ttu-id="9a035-257">Värde</span><span class="sxs-lookup"><span data-stu-id="9a035-257">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9a035-258">**Domän**</span><span class="sxs-lookup"><span data-stu-id="9a035-258">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9a035-259">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="9a035-259">**Key**</span></span> | <span data-ttu-id="9a035-260">serialNumbers</span><span class="sxs-lookup"><span data-stu-id="9a035-260">serialNumbers</span></span> |
| <span data-ttu-id="9a035-261">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="9a035-261">**Data type**</span></span> | <span data-ttu-id="9a035-262">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="9a035-262">Dictionary (nested preference)</span></span> |

<span data-ttu-id="9a035-263">Du kan ange önskad behörighetsnivå för varje serienummer.</span><span class="sxs-lookup"><span data-stu-id="9a035-263">For each serial number, you can specify the desired permission level.</span></span>

|<span data-ttu-id="9a035-264">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="9a035-264">Section</span></span>|<span data-ttu-id="9a035-265">Värde</span><span class="sxs-lookup"><span data-stu-id="9a035-265">Value</span></span>|
|:---|:---|
| <span data-ttu-id="9a035-266">**Domän**</span><span class="sxs-lookup"><span data-stu-id="9a035-266">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="9a035-267">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="9a035-267">**Key**</span></span> | <span data-ttu-id="9a035-268">behörighet</span><span class="sxs-lookup"><span data-stu-id="9a035-268">permission</span></span> |
| <span data-ttu-id="9a035-269">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="9a035-269">**Data type**</span></span> | <span data-ttu-id="9a035-270">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="9a035-270">Array of strings</span></span> |
| <span data-ttu-id="9a035-271">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="9a035-271">**Possible values**</span></span> | <span data-ttu-id="9a035-272">Samma som [standardbehörighetsnivå](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="9a035-272">Same as [Default permission level](#default-permission-level)</span></span> |

#### <a name="example-device-control-policy"></a><span data-ttu-id="9a035-273">Exempel på princip för enhetskontroll</span><span class="sxs-lookup"><span data-stu-id="9a035-273">Example device control policy</span></span>

<span data-ttu-id="9a035-274">Följande exempel visar hur alla ovanstående begrepp kan kombineras i en enhetskontrollprincip.</span><span class="sxs-lookup"><span data-stu-id="9a035-274">The following example shows how all of the above concepts can be combined into a device control policy.</span></span> <span data-ttu-id="9a035-275">Observera i exemplet nedan hur hierarkiskt principen för flyttbara media är.</span><span class="sxs-lookup"><span data-stu-id="9a035-275">In the following example, note the hierarchical nature of the removable media policy.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>navigationTarget</key> 
        <string>[custom URL for notifications]</string> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>[enforcement level]</string> <!-- audit / block --> 
            <key>permission</key> 
            <array> 
                <string>[permission]</string> <!-- none / read / write / execute --> 
                <!-- other permissions -->
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>[vendor id]</key> 
                <dict>
                    <key>permission</key> 
                    <array> 
                        <string>[permission]</string> <!-- none / read / write / execute --> 
                        <!-- other permissions -->
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>[product id]</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>[permission]</string> <!-- none / read / write / execute --> 
                                <!-- other permissions -->
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>[serial-number]</key> 
                                <array> 
                                    <string>[permission]</string> <!-- none / read / write / execute --> 
                                    <!-- other permissions -->
                                </array> 
                                <!-- other serial numbers --> 
                            </dict> 
                        </dict> 
                        <!-- other products --> 
                    </dict> 
                </dict> 
                <!-- other vendors --> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

<span data-ttu-id="9a035-276">Vi har tagit med fler exempel på principer för enhetskontroll i följande dokument:</span><span class="sxs-lookup"><span data-stu-id="9a035-276">We have included more examples of device control policies in the following documents:</span></span>

- [<span data-ttu-id="9a035-277">Exempel på principer för enhetskontroll för Intune</span><span class="sxs-lookup"><span data-stu-id="9a035-277">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="9a035-278">Exempel på principer för enhetskontroll för JAMF</span><span class="sxs-lookup"><span data-stu-id="9a035-278">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a><span data-ttu-id="9a035-279">Slå upp enhetsidentifierare</span><span class="sxs-lookup"><span data-stu-id="9a035-279">Look up device identifiers</span></span>

<span data-ttu-id="9a035-280">Så här hittar du leverantörs-ID, produkt-ID och serienummer för en USB-enhet:</span><span class="sxs-lookup"><span data-stu-id="9a035-280">To find the vendor ID, product ID, and serial number of a USB device:</span></span>

1. <span data-ttu-id="9a035-281">Logga in på en Mac-enhet.</span><span class="sxs-lookup"><span data-stu-id="9a035-281">Log into a Mac device.</span></span>
1. <span data-ttu-id="9a035-282">Anslut den USB-enhet där du vill slå upp identifierarna.</span><span class="sxs-lookup"><span data-stu-id="9a035-282">Plug in the USB device for which you want to look up the identifiers.</span></span>
1. <span data-ttu-id="9a035-283">På menyn på översta nivån i macOS väljer du **Om den här mac-datorn.**</span><span class="sxs-lookup"><span data-stu-id="9a035-283">In the top-level menu of macOS, select **About This Mac**.</span></span>

    ![Om den här Mac-datorn](images/mac-device-control-lookup-1.png)

1. <span data-ttu-id="9a035-285">Välj **Systemrapport**.</span><span class="sxs-lookup"><span data-stu-id="9a035-285">Select **System Report**.</span></span>

    ![Systemrapport](images/mac-device-control-lookup-2.png)

1. <span data-ttu-id="9a035-287">Välj USB i den vänstra **kolumnen.**</span><span class="sxs-lookup"><span data-stu-id="9a035-287">From the left column, select **USB**.</span></span>

    ![Vy över alla USB-enheter](images/mac-device-control-lookup-3.png)

1. <span data-ttu-id="9a035-289">Under **USB-enhetsträd** navigerar du till den USB-enhet som du har anslutit.</span><span class="sxs-lookup"><span data-stu-id="9a035-289">Under **USB Device Tree**, navigate to the USB device that you plugged in.</span></span>

    ![Information om en USB-enhet](images/mac-device-control-lookup-4.png)

1. <span data-ttu-id="9a035-291">Leverantörs-ID, produkt-ID och serienummer visas.</span><span class="sxs-lookup"><span data-stu-id="9a035-291">The vendor ID, product ID, and serial number are displayed.</span></span> <span data-ttu-id="9a035-292">När du lägger till leverantörs-ID och produkt-ID i principen för flyttbara media får du bara lägga till delen efter `0x` .</span><span class="sxs-lookup"><span data-stu-id="9a035-292">When adding the vendor ID and product ID to the removable media policy, you must only add the part after `0x`.</span></span> <span data-ttu-id="9a035-293">I bilden nedan är leverantörs-ID och `1000` `090c` produkt-ID.</span><span class="sxs-lookup"><span data-stu-id="9a035-293">For example, in the below image, vendor ID is `1000` and product ID is `090c`.</span></span>

#### <a name="discover-usb-devices-in-your-organization"></a><span data-ttu-id="9a035-294">Upptäck USB-enheter i din organisation</span><span class="sxs-lookup"><span data-stu-id="9a035-294">Discover USB devices in your organization</span></span>

<span data-ttu-id="9a035-295">Du kan visa monterings-, avsluts- och volymändringshändelser som kommer från USB-enheter i Microsoft Defender för avancerad sökning för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="9a035-295">You can view mount, unmount, and volume change events originating from USB devices in Microsoft Defender for Endpoint advanced hunting.</span></span> <span data-ttu-id="9a035-296">Dessa händelser kan vara användbara för att identifiera misstänkt användningsaktivitet eller utföra interna undersökningar.</span><span class="sxs-lookup"><span data-stu-id="9a035-296">These events can be helpful to identify suspicious usage activity or perform internal investigations.</span></span>

```
DeviceEvents 
    | where ActionType == "UsbDriveMount" or ActionType == "UsbDriveUnmount" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a><span data-ttu-id="9a035-297">Distribution av princip för enhetskontroll</span><span class="sxs-lookup"><span data-stu-id="9a035-297">Device control policy deployment</span></span>

<span data-ttu-id="9a035-298">Principen för enhetskontroll måste finnas bredvid de andra produktinställningarna, enligt beskrivningen i Ange inställningar för [Microsoft Defender för Slutpunkt på macOS.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="9a035-298">The device control policy must be included next to the other product settings, as described in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>

<span data-ttu-id="9a035-299">Den här profilen kan distribueras med hjälp av anvisningarna i [Distribution av konfigurationsprofil.](mac-preferences.md#configuration-profile-deployment)</span><span class="sxs-lookup"><span data-stu-id="9a035-299">This profile can be deployed using the instructions listed in [Configuration profile deployment](mac-preferences.md#configuration-profile-deployment).</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="9a035-300">Felsökningstips</span><span class="sxs-lookup"><span data-stu-id="9a035-300">Troubleshooting tips</span></span>

<span data-ttu-id="9a035-301">När konfigurationsprofilen har installerats via Intune eller JAMF kan du kontrollera om den hämtats av produkten genom att köra följande kommando från terminalen:</span><span class="sxs-lookup"><span data-stu-id="9a035-301">After pushing the configuration profile through Intune or JAMF, you can check if it was successfully picked up by the product by running the following command from the Terminal:</span></span>

```bash
mdatp device-control removable-media policy list
```

<span data-ttu-id="9a035-302">Det här kommandot skriver ut enligt standardprincipen för enhetskontroll som produkten använder.</span><span class="sxs-lookup"><span data-stu-id="9a035-302">This command will print to standard output the device control policy that the product is using.</span></span> <span data-ttu-id="9a035-303">Om det här skrivs ut ser du till att (a) konfigurationsprofilen verkligen har tryckts ned till din enhet från hanteringskonsolen och (b) det är en giltig princip för enhetskontroll, enligt beskrivningen i det här `Policy is empty` dokumentet.</span><span class="sxs-lookup"><span data-stu-id="9a035-303">In case this prints `Policy is empty`, make sure that (a) the configuration profile has indeed been pushed to your device from the management console, and (b) it is a valid device control policy, as described in this document.</span></span>

<span data-ttu-id="9a035-304">På en enhet där principen har levererats och där det finns en eller flera enheter som är inkopplade kan du köra följande kommando för att visa alla enheter och de gällande behörigheterna som tillämpas på dem.</span><span class="sxs-lookup"><span data-stu-id="9a035-304">On a device where the policy has been delivered successfully and where there are one or more devices plugged in, you can run the following command to list all devices and the effective permissions applied to them.</span></span>

```bash
mdatp device-control removable-media devices list
```

<span data-ttu-id="9a035-305">Exempel på utdata:</span><span class="sxs-lookup"><span data-stu-id="9a035-305">Example of output:</span></span>

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

<span data-ttu-id="9a035-306">I exemplet ovan finns det bara en flyttbar medieenhet som är ansluten och den har och behörigheter, enligt principen för enhetskontroll som `read` `execute` levererades till enheten.</span><span class="sxs-lookup"><span data-stu-id="9a035-306">In the above example, there is only one removable media device plugged in and it has `read` and `execute` permissions, according to the device control policy that was delivered to the device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9a035-307">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="9a035-307">Related topics</span></span>

- [<span data-ttu-id="9a035-308">Exempel på principer för enhetskontroll för Intune</span><span class="sxs-lookup"><span data-stu-id="9a035-308">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="9a035-309">Exempel på principer för enhetskontroll för JAMF</span><span class="sxs-lookup"><span data-stu-id="9a035-309">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)
