---
title: Skapa och hantera enhetstaggar
description: Använd enhetstaggar för att gruppera enheter för att samla kontext och möjliggöra dynamiskt listskapande som en del av ett incident
keywords: taggar, enhetstaggar, enhetsgrupper, grupper, åtgärd, nivå, regler, aad-grupp, roll, tilldela, rangordna
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ffe7d13ca0943e8927d0d9ce663527fedf880e48
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187595"
---
# <a name="create-and-manage-device-tags"></a><span data-ttu-id="41be3-104">Skapa och hantera enhetstaggar</span><span class="sxs-lookup"><span data-stu-id="41be3-104">Create and manage device tags</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="41be3-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="41be3-105">**Applies to:**</span></span>
- [<span data-ttu-id="41be3-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="41be3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="41be3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41be3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="41be3-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="41be3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="41be3-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="41be3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="41be3-110">Lägg till taggar på enheter för att skapa logiskt grupp samarbete.</span><span class="sxs-lookup"><span data-stu-id="41be3-110">Add tags on devices to create a logical group affiliation.</span></span> <span data-ttu-id="41be3-111">Enhetstaggar stöder korrekt mappning av nätverket, så att du kan bifoga olika taggar för att fånga sammanhang och möjliggöra skapande av dynamiska listor som en del av ett problem.</span><span class="sxs-lookup"><span data-stu-id="41be3-111">Device tags support proper mapping of the network, enabling you to attach different tags to capture context and to enable dynamic list creation as part of an incident.</span></span> <span data-ttu-id="41be3-112">Taggar kan användas som ett filter i **listvyn Enheter** eller för att gruppera enheter.</span><span class="sxs-lookup"><span data-stu-id="41be3-112">Tags can be used as a filter in **Devices list** view, or to group devices.</span></span> <span data-ttu-id="41be3-113">Mer information om enhetsgruppering finns i [Skapa och hantera enhetsgrupper.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="41be3-113">For more information on device grouping, see [Create and manage device groups](machine-groups.md).</span></span>

<span data-ttu-id="41be3-114">Du kan lägga till taggar på enheter på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="41be3-114">You can add tags on devices using the following ways:</span></span>

- <span data-ttu-id="41be3-115">Med hjälp av portalen</span><span class="sxs-lookup"><span data-stu-id="41be3-115">Using the portal</span></span>
- <span data-ttu-id="41be3-116">Ange ett registernyckelvärde</span><span class="sxs-lookup"><span data-stu-id="41be3-116">Setting a registry key value</span></span>

> [!NOTE]
> <span data-ttu-id="41be3-117">Det kan finnas viss svarstid mellan det att en tagg läggs till på en enhet och dess tillgänglighet i listan enheter och på sidan enhet.</span><span class="sxs-lookup"><span data-stu-id="41be3-117">There may be some latency between the time a tag is added to a device and its availability in the devices list and device page.</span></span>  

<span data-ttu-id="41be3-118">Information om hur du lägger till enhetstaggar med API finns [i Lägga till eller ta bort API för enhetstaggar.](add-or-remove-machine-tags.md)</span><span class="sxs-lookup"><span data-stu-id="41be3-118">To add device tags using API, see [Add or remove device tags API](add-or-remove-machine-tags.md).</span></span>

## <a name="add-and-manage-device-tags-using-the-portal"></a><span data-ttu-id="41be3-119">Lägga till och hantera enhetstaggar via portalen</span><span class="sxs-lookup"><span data-stu-id="41be3-119">Add and manage device tags using the portal</span></span>

1. <span data-ttu-id="41be3-120">Välj den enhet där du vill hantera taggar.</span><span class="sxs-lookup"><span data-stu-id="41be3-120">Select the device that you want to manage tags on.</span></span> <span data-ttu-id="41be3-121">Du kan välja eller söka efter en enhet i någon av följande vyer:</span><span class="sxs-lookup"><span data-stu-id="41be3-121">You can select or search for a device from any of the following views:</span></span>

   - <span data-ttu-id="41be3-122">**Instrumentpanel för** säkerhetsåtgärder – Välj enhetens namn i avsnittet Populära enheter med aktiva aviseringar.</span><span class="sxs-lookup"><span data-stu-id="41be3-122">**Security operations dashboard** - Select the device name from the Top devices with active alerts section.</span></span>
   - <span data-ttu-id="41be3-123">**Telefonaviseringar** – Välj enhetsnamnet bredvid enhetsikonen från aviseringskön.</span><span class="sxs-lookup"><span data-stu-id="41be3-123">**Alerts queue** - Select the device name beside the device icon from the alerts queue.</span></span>
   - <span data-ttu-id="41be3-124">**Listan Enheter** – Välj enhetsnamnet i listan över enheter.</span><span class="sxs-lookup"><span data-stu-id="41be3-124">**Devices list** - Select the device name from the list of devices.</span></span>
   - <span data-ttu-id="41be3-125">**Sökruta** – Välj enhet i listrutan och ange enhetens namn.</span><span class="sxs-lookup"><span data-stu-id="41be3-125">**Search box** - Select Device from the drop-down menu and enter the device name.</span></span>

     <span data-ttu-id="41be3-126">Du kan också gå till aviseringssidan via filen och IP-vyerna.</span><span class="sxs-lookup"><span data-stu-id="41be3-126">You can also get to the alert page through the file and IP views.</span></span>

2. <span data-ttu-id="41be3-127">Välj **Hantera taggar** i raden med svarsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="41be3-127">Select **Manage Tags** from the row of Response actions.</span></span>

    ![Bild på knappen Hantera taggar](images/manage-tags.png)

3. <span data-ttu-id="41be3-129">Skriv för att hitta eller skapa taggar</span><span class="sxs-lookup"><span data-stu-id="41be3-129">Type to find or create tags</span></span>

    ![Bild av att lägga till taggar på en enhet1](images/new-tags.png)

<span data-ttu-id="41be3-131">Taggar läggs till i enhetsvyn och visas även i **listvyn** Enheter.</span><span class="sxs-lookup"><span data-stu-id="41be3-131">Tags are added to the device view and will also be reflected on the **Devices list** view.</span></span> <span data-ttu-id="41be3-132">Sedan kan du använda **filtret Taggar** för att se den relevanta listan över enheter.</span><span class="sxs-lookup"><span data-stu-id="41be3-132">You can then use the **Tags** filter to see the relevant list of devices.</span></span>

>[!NOTE]
> <span data-ttu-id="41be3-133">Filtrering kanske inte fungerar på taggnamn som innehåller parenteser.</span><span class="sxs-lookup"><span data-stu-id="41be3-133">Filtering might not work on tag names that contain parenthesis.</span></span><br>
> <span data-ttu-id="41be3-134">När du skapar en ny tagg visas en lista med befintliga taggar.</span><span class="sxs-lookup"><span data-stu-id="41be3-134">When you create a new tag, a list of existing tags are displayed.</span></span> <span data-ttu-id="41be3-135">I listan visas bara taggar som skapats via portalen.</span><span class="sxs-lookup"><span data-stu-id="41be3-135">The list only shows tags created through the portal.</span></span> <span data-ttu-id="41be3-136">Befintliga taggar som skapats från klientenheter visas inte.</span><span class="sxs-lookup"><span data-stu-id="41be3-136">Existing tags created from client devices will not be displayed.</span></span>

<span data-ttu-id="41be3-137">Du kan också ta bort taggar från den här vyn.</span><span class="sxs-lookup"><span data-stu-id="41be3-137">You can also delete tags from this view.</span></span>

![Bild av att lägga till taggar på en enhet2](images/more-manage-tags.png)

## <a name="add-device-tags-by-setting-a-registry-key-value"></a><span data-ttu-id="41be3-139">Lägga till enhetstaggar genom att ange ett registernyckelvärde</span><span class="sxs-lookup"><span data-stu-id="41be3-139">Add device tags by setting a registry key value</span></span>

>[!NOTE]
> <span data-ttu-id="41be3-140">Endast tillämpligt på följande enheter:</span><span class="sxs-lookup"><span data-stu-id="41be3-140">Applicable only on the following devices:</span></span>
>- <span data-ttu-id="41be3-141">Windows 10, version 1709 eller senare</span><span class="sxs-lookup"><span data-stu-id="41be3-141">Windows 10, version 1709 or later</span></span>
>- <span data-ttu-id="41be3-142">Windows Server, version 1803 eller senare</span><span class="sxs-lookup"><span data-stu-id="41be3-142">Windows Server, version 1803 or later</span></span>
>- <span data-ttu-id="41be3-143">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="41be3-143">Windows Server 2016</span></span>
>- <span data-ttu-id="41be3-144">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="41be3-144">Windows Server 2012 R2</span></span>
>- <span data-ttu-id="41be3-145">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="41be3-145">Windows Server 2008 R2 SP1</span></span>
>- <span data-ttu-id="41be3-146">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="41be3-146">Windows 8.1</span></span>
>- <span data-ttu-id="41be3-147">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="41be3-147">Windows 7 SP1</span></span>

> [!NOTE] 
> <span data-ttu-id="41be3-148">Det maximala antalet tecken som kan anges i en tagg är 200.</span><span class="sxs-lookup"><span data-stu-id="41be3-148">The maximum number of characters that can be set in a tag is 200.</span></span>

<span data-ttu-id="41be3-149">Enheter med liknande taggar kan vara praktiska när du behöver tillämpa sammanhangsberoende åtgärder på en viss lista med enheter.</span><span class="sxs-lookup"><span data-stu-id="41be3-149">Devices with similar tags can be handy when you need to apply contextual action on a specific list of devices.</span></span>

<span data-ttu-id="41be3-150">Använd följande registernyckelpost för att lägga till en tagg på en enhet:</span><span class="sxs-lookup"><span data-stu-id="41be3-150">Use the following registry key entry to add a tag on a device:</span></span>

- <span data-ttu-id="41be3-151">Registernyckel: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span><span class="sxs-lookup"><span data-stu-id="41be3-151">Registry key: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`</span></span>
- <span data-ttu-id="41be3-152">Registernyckelvärde (REG_SZ): `Group`</span><span class="sxs-lookup"><span data-stu-id="41be3-152">Registry key value (REG_SZ): `Group`</span></span>
- <span data-ttu-id="41be3-153">Registernyckeldata: `Name of the tag you want to set`</span><span class="sxs-lookup"><span data-stu-id="41be3-153">Registry key data: `Name of the tag you want to set`</span></span>

>[!NOTE]
><span data-ttu-id="41be3-154">Enhetstaggen är en del av enhetsinformationsrapporten som genereras en gång om dagen.</span><span class="sxs-lookup"><span data-stu-id="41be3-154">The device tag is part of the device information report that's generated once a day.</span></span> <span data-ttu-id="41be3-155">Alternativt kan du välja att starta om slutpunkten som överför en ny enhetsinformationsrapport.</span><span class="sxs-lookup"><span data-stu-id="41be3-155">As an alternative, you may choose to restart the endpoint that would transfer a new device information report.</span></span>
> 
> <span data-ttu-id="41be3-156">Om du behöver ta bort en tagg som lagts till med ovanstående registernyckel rensar du innehållet i registernyckeldata i stället för att ta bort gruppnyckeln.</span><span class="sxs-lookup"><span data-stu-id="41be3-156">If you need to remove a tag that was added using the above Registry key, clear the contents of the Registry key data instead of removing the 'Group' key.</span></span>
