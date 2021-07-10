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
ms.openlocfilehash: 5cb819daa11a50ef54c758a6aa696a5fc645029c
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363985"
---
# <a name="device-control-for-macos"></a><span data-ttu-id="5a9cc-104">Enhetskontroll för macOS</span><span class="sxs-lookup"><span data-stu-id="5a9cc-104">Device control for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5a9cc-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-105">**Applies to:**</span></span>
- [<span data-ttu-id="5a9cc-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="5a9cc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5a9cc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5a9cc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5a9cc-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="5a9cc-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5a9cc-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="requirements"></a><span data-ttu-id="5a9cc-110">Krav</span><span class="sxs-lookup"><span data-stu-id="5a9cc-110">Requirements</span></span>

<span data-ttu-id="5a9cc-111">Enhetskontroll för macOS har följande krav:</span><span class="sxs-lookup"><span data-stu-id="5a9cc-111">Device control for macOS has the following prerequisites:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="5a9cc-112">Microsoft Defender för slutpunktsberättigande (kan vara utvärderingsversion)</span><span class="sxs-lookup"><span data-stu-id="5a9cc-112">Microsoft Defender for Endpoint entitlement (can be trial)</span></span>
> - <span data-ttu-id="5a9cc-113">Lägsta OS-version: macOS 11 eller senare</span><span class="sxs-lookup"><span data-stu-id="5a9cc-113">Minimum OS version: macOS 11 or higher</span></span>
> - <span data-ttu-id="5a9cc-114">Lägsta produktversion: 101.34.20</span><span class="sxs-lookup"><span data-stu-id="5a9cc-114">Minimum product version: 101.34.20</span></span>

## <a name="device-control-policy"></a><span data-ttu-id="5a9cc-115">Princip för enhetskontroll</span><span class="sxs-lookup"><span data-stu-id="5a9cc-115">Device control policy</span></span>

<span data-ttu-id="5a9cc-116">Om du vill konfigurera enhetskontroll för macOS måste du skapa en princip som beskriver de begränsningar du vill införa i organisationen.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-116">To configure device control for macOS, you must create a policy that describes the restrictions you want to put in place within your organization.</span></span>

<span data-ttu-id="5a9cc-117">Principen för enhetskontroll ingår i konfigurationsprofilen som används för att konfigurera alla andra produktinställningar.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-117">The device control policy is included in the configuration profile used to configure all other product settings.</span></span> <span data-ttu-id="5a9cc-118">Mer information finns i [Konfigurationsprofilens struktur.](mac-preferences.md#configuration-profile-structure)</span><span class="sxs-lookup"><span data-stu-id="5a9cc-118">For more information, see [Configuration profile structure](mac-preferences.md#configuration-profile-structure).</span></span>

<span data-ttu-id="5a9cc-119">I konfigurationsprofilen definieras enhetens kontrollprincip i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="5a9cc-119">Within the configuration profile, the device control policy is defined in the following section:</span></span>

|<span data-ttu-id="5a9cc-120">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="5a9cc-120">Section</span></span>|<span data-ttu-id="5a9cc-121">Värde</span><span class="sxs-lookup"><span data-stu-id="5a9cc-121">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5a9cc-122">**Domän**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-122">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5a9cc-123">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-123">**Key**</span></span> | <span data-ttu-id="5a9cc-124">deviceControl</span><span class="sxs-lookup"><span data-stu-id="5a9cc-124">deviceControl</span></span> |
| <span data-ttu-id="5a9cc-125">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-125">**Data type**</span></span> | <span data-ttu-id="5a9cc-126">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="5a9cc-126">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5a9cc-127">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-127">**Comments**</span></span> | <span data-ttu-id="5a9cc-128">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-128">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="5a9cc-129">Principen för enhetskontroll kan användas för att:</span><span class="sxs-lookup"><span data-stu-id="5a9cc-129">The device control policy can be used to:</span></span>

- [<span data-ttu-id="5a9cc-130">Anpassa URL-målet för meddelanden upphöjt av enhetskontroll</span><span class="sxs-lookup"><span data-stu-id="5a9cc-130">Customize the URL target for notifications raised by device control</span></span>](#customize-url-target-for-notifications-raised-by-device-control)
- [<span data-ttu-id="5a9cc-131">Tillåt eller blockera flyttbara enheter</span><span class="sxs-lookup"><span data-stu-id="5a9cc-131">Allow or block removable devices</span></span>](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a><span data-ttu-id="5a9cc-132">Anpassa URL-målet för meddelanden upphöjt av enhetskontroll</span><span class="sxs-lookup"><span data-stu-id="5a9cc-132">Customize URL target for notifications raised by device control</span></span>

<span data-ttu-id="5a9cc-133">När den princip för enhetskontroll som du har tillämpat tillämpas på en enhet (till exempel åtkomsten till en flyttbar medieenhet är begränsad) visas ett meddelande för användaren.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-133">When the device control policy that you have put in place is enforced on a device (for example, access to a removable media device is restricted), a notification is displayed to the user.</span></span>

![Meddelande om enhetskontroll](images/mac-device-control-notification.png)

<span data-ttu-id="5a9cc-135">När slutanvändare klickar på det här meddelandet öppnas en webbsida i standardwebbläsaren.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-135">When end users click this notification, a web page is opened in the default browser.</span></span> <span data-ttu-id="5a9cc-136">Du kan konfigurera URL-adressen som öppnas när slutanvändare klickar på meddelandet.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-136">You can configure the URL that is opened when end users click the notification.</span></span>

|<span data-ttu-id="5a9cc-137">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="5a9cc-137">Section</span></span>|<span data-ttu-id="5a9cc-138">Värde</span><span class="sxs-lookup"><span data-stu-id="5a9cc-138">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5a9cc-139">**Domän**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-139">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5a9cc-140">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-140">**Key**</span></span> | <span data-ttu-id="5a9cc-141">navigationTarget</span><span class="sxs-lookup"><span data-stu-id="5a9cc-141">navigationTarget</span></span> |
| <span data-ttu-id="5a9cc-142">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-142">**Data type**</span></span> | <span data-ttu-id="5a9cc-143">Sträng</span><span class="sxs-lookup"><span data-stu-id="5a9cc-143">String</span></span> |
| <span data-ttu-id="5a9cc-144">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-144">**Comments**</span></span> | <span data-ttu-id="5a9cc-145">Om den inte är definierad använder produkten en standard-URL som pekar till en allmän sida som förklarar produktens åtgärder.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-145">If not defined, the product uses a default URL pointing to a generic page explaining the action taken by the product.</span></span> |

### <a name="allow-or-block-removable-devices"></a><span data-ttu-id="5a9cc-146">Tillåt eller blockera flyttbara enheter</span><span class="sxs-lookup"><span data-stu-id="5a9cc-146">Allow or block removable devices</span></span>

<span data-ttu-id="5a9cc-147">Avsnittet för flyttbara mediefiler i enhetens kontrollprincip används för att begränsa åtkomsten till flyttbara medium.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-147">The removable media section of the device control policy is used to restrict access to removable media.</span></span> 

> [!NOTE]
> <span data-ttu-id="5a9cc-148">Följande typer av flyttbara media stöds för närvarande och kan ingå i principen: USB-lagringsenheter.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-148">The following types of removable media are currently supported and can be included in the policy: USB storage devices.</span></span>

|<span data-ttu-id="5a9cc-149">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="5a9cc-149">Section</span></span>|<span data-ttu-id="5a9cc-150">Värde</span><span class="sxs-lookup"><span data-stu-id="5a9cc-150">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5a9cc-151">**Domän**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-151">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5a9cc-152">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-152">**Key**</span></span> | <span data-ttu-id="5a9cc-153">removableMediaPolicy</span><span class="sxs-lookup"><span data-stu-id="5a9cc-153">removableMediaPolicy</span></span> |
| <span data-ttu-id="5a9cc-154">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-154">**Data type**</span></span> | <span data-ttu-id="5a9cc-155">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="5a9cc-155">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="5a9cc-156">**Kommentarer**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-156">**Comments**</span></span> | <span data-ttu-id="5a9cc-157">I följande avsnitt finns en beskrivning av innehållet i ordlistan.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-157">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="5a9cc-158">Det här avsnittet i principen är hierarkiskt, vilket ger maximal flexibilitet och omfattar ett brett utbud av användningsfall.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-158">This section of the policy is hierarchical, allowing for maximum flexibility and covering a wide range of use cases.</span></span> <span data-ttu-id="5a9cc-159">På den högsta nivån finns leverantörer som har ett leverantörs-ID.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-159">At the top level are vendors, identified by a vendor ID.</span></span> <span data-ttu-id="5a9cc-160">För varje leverantör finns det produkter som identifieras med ett produkt-ID.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-160">For each vendor, there are products, identified by a product ID.</span></span> <span data-ttu-id="5a9cc-161">För varje produkt finns slutligen serienummer som anger specifika enheter.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-161">Finally, for each product there are serial numbers denoting specific devices.</span></span>

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

<span data-ttu-id="5a9cc-162">Mer information om hur du hittar enhetsidentifierare finns i [Slå upp enhetsidentifierare](#look-up-device-identifiers).</span><span class="sxs-lookup"><span data-stu-id="5a9cc-162">For information on how to find the device identifiers, see [Look up device identifiers](#look-up-device-identifiers).</span></span>

<span data-ttu-id="5a9cc-163">Principen utvärderas från det mest specifika inmatnings området till det mest allmänna.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-163">The policy is evaluated from the most specific entry to the most general one.</span></span> <span data-ttu-id="5a9cc-164">När en enhet är ansluten försöker produkten alltså hitta den mest specifika matchningen i principen för varje flyttbar medieenhet och tillämpa behörigheterna på den nivån.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-164">Meaning, when a device is plugged in, the product tries to find the most specific match in the policy for each removable media device and apply the permissions at that level.</span></span> <span data-ttu-id="5a9cc-165">Om det inte finns någon matchning tillämpas nästa bästa matchning, hela vägen till den behörighet som anges på den högsta nivån, vilket är standard när en enhet inte matchar någon annan post i principen.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-165">If there is no match, then the next best match is applied, all the way to the permission specified at the top level, which is the default when a device does not match any other entry in the policy.</span></span>

#### <a name="policy-enforcement-level"></a><span data-ttu-id="5a9cc-166">Tillämpningsnivå för policy</span><span class="sxs-lookup"><span data-stu-id="5a9cc-166">Policy enforcement level</span></span>

<span data-ttu-id="5a9cc-167">Under avsnittet flyttbara media finns ett alternativ för att ställa in tillämpningsnivån, som kan ha något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="5a9cc-167">Under the removable media section, there is an option to set the enforcement level, which can take one of the following values:</span></span>

- <span data-ttu-id="5a9cc-168">`audit` – Om åtkomsten till en enhet är begränsad visas ett meddelande för användaren under den här tillämpningsnivån, men enheten kan fortfarande användas.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-168">`audit` - Under this enforcement level, if access to a device is restricted, a notification is displayed to the user, however the device can still be used.</span></span> <span data-ttu-id="5a9cc-169">Den här tillämpningsnivån kan vara användbar för att utvärdera en princips effektivitet.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-169">This enforcement level can be useful to evaluate the effectiveness of a policy.</span></span>
- <span data-ttu-id="5a9cc-170">`block` – Under den här tillämpningsnivån är åtgärderna som användaren kan utföra på enheten begränsade till vad som har definierats i principen.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-170">`block` - Under this enforcement level, the operations that the user can perform on the device are limited to what is defined in the policy.</span></span> <span data-ttu-id="5a9cc-171">Dessutom skickas ett meddelande till användaren.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-171">Furthermore, a notification is raised to the user.</span></span> 

> [!NOTE] 
> <span data-ttu-id="5a9cc-172">Som standard har tillämpningsnivån `audit` .</span><span class="sxs-lookup"><span data-stu-id="5a9cc-172">By default, the enforcement level is set to `audit`.</span></span> 

|<span data-ttu-id="5a9cc-173">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="5a9cc-173">Section</span></span>|<span data-ttu-id="5a9cc-174">Värde</span><span class="sxs-lookup"><span data-stu-id="5a9cc-174">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5a9cc-175">**Domän**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-175">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5a9cc-176">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-176">**Key**</span></span> | <span data-ttu-id="5a9cc-177">enforcementLevel</span><span class="sxs-lookup"><span data-stu-id="5a9cc-177">enforcementLevel</span></span> |
| <span data-ttu-id="5a9cc-178">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-178">**Data type**</span></span> | <span data-ttu-id="5a9cc-179">Sträng</span><span class="sxs-lookup"><span data-stu-id="5a9cc-179">String</span></span> |
| <span data-ttu-id="5a9cc-180">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-180">**Possible values**</span></span> | <span data-ttu-id="5a9cc-181">granskning (standard)</span><span class="sxs-lookup"><span data-stu-id="5a9cc-181">audit (default)</span></span> <br/> <span data-ttu-id="5a9cc-182">blockera</span><span class="sxs-lookup"><span data-stu-id="5a9cc-182">block</span></span> |

#### <a name="default-permission-level"></a><span data-ttu-id="5a9cc-183">Standardbehörighetsnivå</span><span class="sxs-lookup"><span data-stu-id="5a9cc-183">Default permission level</span></span>

<span data-ttu-id="5a9cc-184">På den översta nivån i avsnittet flyttbara media kan du konfigurera standardbehörighetsnivån för enheter som inte matchar något annat i principen.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-184">At the top level of the removable media section, you can configure the default permission level for devices that do not match anything else in the policy.</span></span>

<span data-ttu-id="5a9cc-185">Den här inställningen kan ställas in på:</span><span class="sxs-lookup"><span data-stu-id="5a9cc-185">This setting can be set to:</span></span>

- <span data-ttu-id="5a9cc-186">`none` - Inga åtgärder kan utföras på enheten</span><span class="sxs-lookup"><span data-stu-id="5a9cc-186">`none` - No operations can be performed on the device</span></span>
- <span data-ttu-id="5a9cc-187">En kombination av följande värden:</span><span class="sxs-lookup"><span data-stu-id="5a9cc-187">A combination of the following values:</span></span>
    - <span data-ttu-id="5a9cc-188">`read` - Läsåtgärder tillåts på enheten</span><span class="sxs-lookup"><span data-stu-id="5a9cc-188">`read` - Read operations are permitted on the device</span></span>
    - <span data-ttu-id="5a9cc-189">`write` - Skrivåtgärder tillåts på enheten</span><span class="sxs-lookup"><span data-stu-id="5a9cc-189">`write` - Write operations are permitted on the device</span></span>
    - <span data-ttu-id="5a9cc-190">`execute` - Utföra åtgärder tillåts på enheten</span><span class="sxs-lookup"><span data-stu-id="5a9cc-190">`execute` - Execute operations are permitted on the device</span></span>

> [!NOTE]
> <span data-ttu-id="5a9cc-191">Om `none` finns i behörighetsnivån ignoreras alla andra behörigheter ( `read` , eller `write` `execute` ).</span><span class="sxs-lookup"><span data-stu-id="5a9cc-191">If `none` is present in the permission level, any other permissions (`read`, `write`, or `execute`) will be ignored.</span></span>

> [!NOTE]
> <span data-ttu-id="5a9cc-192">Behörigheten `execute` refererar bara till körning av Binärfilerna i Så här många binärfiler.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-192">The `execute` permission only refers to execution of Mach-O binaries.</span></span> <span data-ttu-id="5a9cc-193">Den innehåller inte körning av skript eller andra typer av nyttolaster.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-193">It does not include execution of scripts or other types of payloads.</span></span>

|<span data-ttu-id="5a9cc-194">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="5a9cc-194">Section</span></span>|<span data-ttu-id="5a9cc-195">Värde</span><span class="sxs-lookup"><span data-stu-id="5a9cc-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5a9cc-196">**Domän**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5a9cc-197">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-197">**Key**</span></span> | <span data-ttu-id="5a9cc-198">behörighet</span><span class="sxs-lookup"><span data-stu-id="5a9cc-198">permission</span></span> |
| <span data-ttu-id="5a9cc-199">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-199">**Data type**</span></span> | <span data-ttu-id="5a9cc-200">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="5a9cc-200">Array of strings</span></span> |
| <span data-ttu-id="5a9cc-201">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-201">**Possible values**</span></span> | <span data-ttu-id="5a9cc-202">none (ingen)</span><span class="sxs-lookup"><span data-stu-id="5a9cc-202">none</span></span> <br/> <span data-ttu-id="5a9cc-203">läsa</span><span class="sxs-lookup"><span data-stu-id="5a9cc-203">read</span></span> <br/> <span data-ttu-id="5a9cc-204">skriva</span><span class="sxs-lookup"><span data-stu-id="5a9cc-204">write</span></span> <br/> <span data-ttu-id="5a9cc-205">utföra</span><span class="sxs-lookup"><span data-stu-id="5a9cc-205">execute</span></span> |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a><span data-ttu-id="5a9cc-206">Begränsa flyttbara medium efter leverantör, produkt och serienummer</span><span class="sxs-lookup"><span data-stu-id="5a9cc-206">Restrict removable media by vendor, product, and serial number</span></span>

<span data-ttu-id="5a9cc-207">Enligt beskrivningen [i Tillåt eller blockera](#allow-or-block-removable-devices)flyttbara enheter kan flyttbara medium, t.ex. USB-enheter, identifieras med leverantörs-ID, produkt-ID och serienummer.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-207">As described in [Allow or block removable devices](#allow-or-block-removable-devices), removable media such as USB devices can be identified by the vendor ID, product ID, and serial number.</span></span>

<span data-ttu-id="5a9cc-208">På den högsta nivån i principen för flyttbara media kan du definiera mer detaljerade begränsningar på leverantörsnivå.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-208">At the top level of the removable media policy, you can optionally define more granular restrictions at the vendor level.</span></span> 

<span data-ttu-id="5a9cc-209">Ordlistan `vendors` innehåller en eller flera poster där varje post identifieras med leverantörs-ID.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-209">The `vendors` dictionary contains one or more entries, with each entry being identified by the vendor ID.</span></span>

|<span data-ttu-id="5a9cc-210">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="5a9cc-210">Section</span></span>|<span data-ttu-id="5a9cc-211">Värde</span><span class="sxs-lookup"><span data-stu-id="5a9cc-211">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5a9cc-212">**Domän**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-212">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5a9cc-213">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-213">**Key**</span></span> | <span data-ttu-id="5a9cc-214">leverantörer</span><span class="sxs-lookup"><span data-stu-id="5a9cc-214">vendors</span></span> |
| <span data-ttu-id="5a9cc-215">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-215">**Data type**</span></span> | <span data-ttu-id="5a9cc-216">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="5a9cc-216">Dictionary (nested preference)</span></span> |

<span data-ttu-id="5a9cc-217">Du kan ange önskad behörighetsnivå för enheter från den leverantören för varje leverantör.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-217">For each vendor, you can specify the desired permission level for devices from that vendor.</span></span>

|<span data-ttu-id="5a9cc-218">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="5a9cc-218">Section</span></span>|<span data-ttu-id="5a9cc-219">Värde</span><span class="sxs-lookup"><span data-stu-id="5a9cc-219">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5a9cc-220">**Domän**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-220">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5a9cc-221">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-221">**Key**</span></span> | <span data-ttu-id="5a9cc-222">behörighet</span><span class="sxs-lookup"><span data-stu-id="5a9cc-222">permission</span></span> |
| <span data-ttu-id="5a9cc-223">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-223">**Data type**</span></span> | <span data-ttu-id="5a9cc-224">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="5a9cc-224">Array of strings</span></span> |
| <span data-ttu-id="5a9cc-225">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-225">**Possible values**</span></span> | <span data-ttu-id="5a9cc-226">Samma som [standardbehörighetsnivå](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="5a9cc-226">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="5a9cc-227">Alternativt kan du ange en uppsättning produkter som tillhör den leverantören och vilka mer detaljerade behörigheter definieras för.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-227">Furthermore, you can optionally specify the set of products belonging to that vendor for which more granular permissions are defined.</span></span> <span data-ttu-id="5a9cc-228">Ordlistan `products` innehåller en eller flera poster där varje post identifieras med produkt-ID: t.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-228">The `products` dictionary contains one or more entries, with each entry being identified by the product ID.</span></span> 

|<span data-ttu-id="5a9cc-229">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="5a9cc-229">Section</span></span>|<span data-ttu-id="5a9cc-230">Värde</span><span class="sxs-lookup"><span data-stu-id="5a9cc-230">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5a9cc-231">**Domän**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-231">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5a9cc-232">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-232">**Key**</span></span> | <span data-ttu-id="5a9cc-233">produkter</span><span class="sxs-lookup"><span data-stu-id="5a9cc-233">products</span></span> |
| <span data-ttu-id="5a9cc-234">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-234">**Data type**</span></span> | <span data-ttu-id="5a9cc-235">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="5a9cc-235">Dictionary (nested preference)</span></span> |

<span data-ttu-id="5a9cc-236">Du kan ange önskad behörighetsnivå för varje produkt.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-236">For each product, you can specify the desired permission level for that product.</span></span>

|<span data-ttu-id="5a9cc-237">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="5a9cc-237">Section</span></span>|<span data-ttu-id="5a9cc-238">Värde</span><span class="sxs-lookup"><span data-stu-id="5a9cc-238">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5a9cc-239">**Domän**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-239">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5a9cc-240">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-240">**Key**</span></span> | <span data-ttu-id="5a9cc-241">behörighet</span><span class="sxs-lookup"><span data-stu-id="5a9cc-241">permission</span></span> |
| <span data-ttu-id="5a9cc-242">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-242">**Data type**</span></span> | <span data-ttu-id="5a9cc-243">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="5a9cc-243">Array of strings</span></span> |
| <span data-ttu-id="5a9cc-244">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-244">**Possible values**</span></span> | <span data-ttu-id="5a9cc-245">Samma som [standardbehörighetsnivå](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="5a9cc-245">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="5a9cc-246">Du kan dessutom ange en valfri uppsättning serienummer som mer detaljerade behörigheter definieras för.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-246">Furthermore, you can specify an optional set of serial numbers for which more granular permissions are defined.</span></span>

<span data-ttu-id="5a9cc-247">Ordlistan `serialNumbers` innehåller en eller flera poster där varje post identifieras med serienumret.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-247">The `serialNumbers` dictionary contains one or more entries, with each entry being identified by the serial number.</span></span>

|<span data-ttu-id="5a9cc-248">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="5a9cc-248">Section</span></span>|<span data-ttu-id="5a9cc-249">Värde</span><span class="sxs-lookup"><span data-stu-id="5a9cc-249">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5a9cc-250">**Domän**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-250">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5a9cc-251">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-251">**Key**</span></span> | <span data-ttu-id="5a9cc-252">serialNumbers</span><span class="sxs-lookup"><span data-stu-id="5a9cc-252">serialNumbers</span></span> |
| <span data-ttu-id="5a9cc-253">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-253">**Data type**</span></span> | <span data-ttu-id="5a9cc-254">Ordlista (kapslad inställning)</span><span class="sxs-lookup"><span data-stu-id="5a9cc-254">Dictionary (nested preference)</span></span> |

<span data-ttu-id="5a9cc-255">Du kan ange önskad behörighetsnivå för varje serienummer.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-255">For each serial number, you can specify the desired permission level.</span></span>

|<span data-ttu-id="5a9cc-256">Avsnitt</span><span class="sxs-lookup"><span data-stu-id="5a9cc-256">Section</span></span>|<span data-ttu-id="5a9cc-257">Värde</span><span class="sxs-lookup"><span data-stu-id="5a9cc-257">Value</span></span>|
|:---|:---|
| <span data-ttu-id="5a9cc-258">**Domän**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-258">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="5a9cc-259">**Nyckel**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-259">**Key**</span></span> | <span data-ttu-id="5a9cc-260">behörighet</span><span class="sxs-lookup"><span data-stu-id="5a9cc-260">permission</span></span> |
| <span data-ttu-id="5a9cc-261">**Datatyp**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-261">**Data type**</span></span> | <span data-ttu-id="5a9cc-262">Matris med strängar</span><span class="sxs-lookup"><span data-stu-id="5a9cc-262">Array of strings</span></span> |
| <span data-ttu-id="5a9cc-263">**Möjliga värden**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-263">**Possible values**</span></span> | <span data-ttu-id="5a9cc-264">Samma som [standardbehörighetsnivå](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="5a9cc-264">Same as [Default permission level](#default-permission-level)</span></span> |

#### <a name="example-device-control-policy"></a><span data-ttu-id="5a9cc-265">Exempel på princip för enhetskontroll</span><span class="sxs-lookup"><span data-stu-id="5a9cc-265">Example device control policy</span></span>

<span data-ttu-id="5a9cc-266">Följande exempel visar hur alla ovanstående begrepp kan kombineras i en enhetskontrollprincip.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-266">The following example shows how all of the above concepts can be combined into a device control policy.</span></span> <span data-ttu-id="5a9cc-267">Observera i exemplet nedan hur hierarkiskt principen för flyttbara media är.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-267">In the following example, note the hierarchical nature of the removable media policy.</span></span>

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

<span data-ttu-id="5a9cc-268">Vi har tagit med fler exempel på principer för enhetskontroll i följande dokument:</span><span class="sxs-lookup"><span data-stu-id="5a9cc-268">We have included more examples of device control policies in the following documents:</span></span>

- [<span data-ttu-id="5a9cc-269">Exempel på principer för enhetskontroll för Intune</span><span class="sxs-lookup"><span data-stu-id="5a9cc-269">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="5a9cc-270">Exempel på principer för enhetskontroll för JAMF</span><span class="sxs-lookup"><span data-stu-id="5a9cc-270">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a><span data-ttu-id="5a9cc-271">Slå upp enhetsidentifierare</span><span class="sxs-lookup"><span data-stu-id="5a9cc-271">Look up device identifiers</span></span>

<span data-ttu-id="5a9cc-272">Så här hittar du leverantörs-ID, produkt-ID och serienummer för en USB-enhet:</span><span class="sxs-lookup"><span data-stu-id="5a9cc-272">To find the vendor ID, product ID, and serial number of a USB device:</span></span>

1. <span data-ttu-id="5a9cc-273">Logga in på en Mac-enhet.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-273">Log into a Mac device.</span></span>
1. <span data-ttu-id="5a9cc-274">Anslut den USB-enhet där du vill slå upp identifierarna.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-274">Plug in the USB device for which you want to look up the identifiers.</span></span>
1. <span data-ttu-id="5a9cc-275">På menyn på översta nivån i macOS väljer du **Om den här mac-datorn.**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-275">In the top-level menu of macOS, select **About This Mac**.</span></span>

    ![Om den här Mac-datorn](images/mac-device-control-lookup-1.png)

1. <span data-ttu-id="5a9cc-277">Välj **Systemrapport**.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-277">Select **System Report**.</span></span>

    ![Systemrapport](images/mac-device-control-lookup-2.png)

1. <span data-ttu-id="5a9cc-279">Välj USB i den vänstra **kolumnen.**</span><span class="sxs-lookup"><span data-stu-id="5a9cc-279">From the left column, select **USB**.</span></span>

    ![Vy över alla USB-enheter](images/mac-device-control-lookup-3.png)

1. <span data-ttu-id="5a9cc-281">Under **USB-enhetsträd** navigerar du till den USB-enhet som du har anslutit.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-281">Under **USB Device Tree**, navigate to the USB device that you plugged in.</span></span>

    ![Information om en USB-enhet](images/mac-device-control-lookup-4.png)

1. <span data-ttu-id="5a9cc-283">Leverantörs-ID, produkt-ID och serienummer visas.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-283">The vendor ID, product ID, and serial number are displayed.</span></span> <span data-ttu-id="5a9cc-284">När du lägger till leverantörs-ID och produkt-ID i principen för flyttbara media får du bara lägga till delen efter `0x` .</span><span class="sxs-lookup"><span data-stu-id="5a9cc-284">When adding the vendor ID and product ID to the removable media policy, you must only add the part after `0x`.</span></span> <span data-ttu-id="5a9cc-285">I bilden nedan är leverantörs-ID och `1000` `090c` produkt-ID.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-285">For example, in the below image, vendor ID is `1000` and product ID is `090c`.</span></span>

#### <a name="discover-usb-devices-in-your-organization"></a><span data-ttu-id="5a9cc-286">Upptäck USB-enheter i din organisation</span><span class="sxs-lookup"><span data-stu-id="5a9cc-286">Discover USB devices in your organization</span></span>

<span data-ttu-id="5a9cc-287">Du kan visa monterings-, avsluts- och volymändringshändelser som kommer från USB-enheter i Microsoft Defender för avancerad sökning för slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-287">You can view mount, unmount, and volume change events originating from USB devices in Microsoft Defender for Endpoint advanced hunting.</span></span> <span data-ttu-id="5a9cc-288">Dessa händelser kan vara användbara för att identifiera misstänkt användningsaktivitet eller utföra interna undersökningar.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-288">These events can be helpful to identify suspicious usage activity or perform internal investigations.</span></span>

```
DeviceEvents 
    | where ActionType == "UsbDriveMounted" or ActionType == "UsbDriveUnmounted" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a><span data-ttu-id="5a9cc-289">Distribution av princip för enhetskontroll</span><span class="sxs-lookup"><span data-stu-id="5a9cc-289">Device control policy deployment</span></span>

<span data-ttu-id="5a9cc-290">Principen för enhetskontroll måste finnas bredvid de andra produktinställningarna, enligt beskrivningen i Ange inställningar för [Microsoft Defender för Slutpunkt på macOS.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="5a9cc-290">The device control policy must be included next to the other product settings, as described in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>

<span data-ttu-id="5a9cc-291">Den här profilen kan distribueras med hjälp av anvisningarna i [Distribution av konfigurationsprofil.](mac-preferences.md#configuration-profile-deployment)</span><span class="sxs-lookup"><span data-stu-id="5a9cc-291">This profile can be deployed using the instructions listed in [Configuration profile deployment](mac-preferences.md#configuration-profile-deployment).</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="5a9cc-292">Felsökningstips</span><span class="sxs-lookup"><span data-stu-id="5a9cc-292">Troubleshooting tips</span></span>

<span data-ttu-id="5a9cc-293">När konfigurationsprofilen har installerats via Intune eller JAMF kan du kontrollera om den hämtats av produkten genom att köra följande kommando från terminalen:</span><span class="sxs-lookup"><span data-stu-id="5a9cc-293">After pushing the configuration profile through Intune or JAMF, you can check if it was successfully picked up by the product by running the following command from the Terminal:</span></span>

```bash
mdatp device-control removable-media policy list
```

<span data-ttu-id="5a9cc-294">Det här kommandot skriver ut enligt standardprincipen för enhetskontroll som produkten använder.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-294">This command will print to standard output the device control policy that the product is using.</span></span> <span data-ttu-id="5a9cc-295">Om det här skrivs ut ser du till att (a) konfigurationsprofilen verkligen har tryckts ned till din enhet från hanteringskonsolen och (b) det är en giltig princip för enhetskontroll, enligt beskrivningen i det här `Policy is empty` dokumentet.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-295">In case this prints `Policy is empty`, make sure that (a) the configuration profile has indeed been pushed to your device from the management console, and (b) it is a valid device control policy, as described in this document.</span></span>

<span data-ttu-id="5a9cc-296">På en enhet där principen har levererats och där det finns en eller flera enheter som är inkopplade kan du köra följande kommando för att visa alla enheter och de gällande behörigheterna som tillämpas på dem.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-296">On a device where the policy has been delivered successfully and where there are one or more devices plugged in, you can run the following command to list all devices and the effective permissions applied to them.</span></span>

```bash
mdatp device-control removable-media devices list
```

<span data-ttu-id="5a9cc-297">Exempel på utdata:</span><span class="sxs-lookup"><span data-stu-id="5a9cc-297">Example of output:</span></span>

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

<span data-ttu-id="5a9cc-298">I exemplet ovan finns det bara en flyttbar medieenhet som är ansluten och den har och behörigheter, enligt principen för enhetskontroll som `read` `execute` levererades till enheten.</span><span class="sxs-lookup"><span data-stu-id="5a9cc-298">In the above example, there is only one removable media device plugged in and it has `read` and `execute` permissions, according to the device control policy that was delivered to the device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5a9cc-299">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="5a9cc-299">Related topics</span></span>

- [<span data-ttu-id="5a9cc-300">Exempel på principer för enhetskontroll för Intune</span><span class="sxs-lookup"><span data-stu-id="5a9cc-300">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="5a9cc-301">Exempel på principer för enhetskontroll för JAMF</span><span class="sxs-lookup"><span data-stu-id="5a9cc-301">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)
