---
title: Konfigurera enhetsidentifiering
description: Lär dig hur du konfigurerar enhetsidentifiering i Microsoft 365 Defender med grundläggande identifiering eller standardidentifiering
keywords: grundläggande, standard, konfigurera identifiering av slutpunkt, enhetsidentifiering
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 0d722b4f4bef5b4d178edc5f2142c887690d4c63
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765257"
---
# <a name="configure-device-discovery"></a><span data-ttu-id="8e326-104">Konfigurera enhetsidentifiering</span><span class="sxs-lookup"><span data-stu-id="8e326-104">Configure device discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8e326-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8e326-105">**Applies to:**</span></span>
- [<span data-ttu-id="8e326-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="8e326-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="8e326-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8e326-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="8e326-108">Identifiering kan konfigureras att ske i standard- eller standardläge.</span><span class="sxs-lookup"><span data-stu-id="8e326-108">Discovery can be configured to be on standard or basic mode.</span></span> <span data-ttu-id="8e326-109">Använd standardalternativet för att aktivt hitta enheter i nätverket, vilket bättre garanterar att slutpunkter upptäcks och ger bättre enhetsklassificering.</span><span class="sxs-lookup"><span data-stu-id="8e326-109">Use the standard option to actively find devices in your network, which will better guarantee the discovery of endpoints and provide richer device classification.</span></span> 

<span data-ttu-id="8e326-110">Du kan anpassa listan med enheter som används för standardidentifiering.</span><span class="sxs-lookup"><span data-stu-id="8e326-110">You can customize the list of devices that are used to perform standard discovery.</span></span> <span data-ttu-id="8e326-111">Du kan antingen aktivera standardidentifiering för alla enheter som har stöd för den här funktionen (för närvarande endast Windows 10-enheter) eller välja en delmängd eller delmängder av dina enheter genom att ange deras enhetstaggar.</span><span class="sxs-lookup"><span data-stu-id="8e326-111">You can either enable standard discovery on all the onboarded devices that also support this capability (currently - Windows 10 devices only) or select a subset or subsets of your devices by specifying their device tags.</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="8e326-112">För förhandsgranskning måste du först aktivera förhandsgranskningsfunktionerna i Microsoft Defender Säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="8e326-112">For preview, you'll first need to turn on the Preview features in Microsoft Defender Security Center.</span></span>
> <span data-ttu-id="8e326-113">Du kan sedan komma åt konfigurationen för enhetsidentifiering Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="8e326-113">You can then access the device discovery configuration in Microsoft 365 security center.</span></span> <span data-ttu-id="8e326-114">Listan över ohanterade enheter och säkerhetsrekommendationer blir tillgänglig i både säkerhetscentret i Microsoft Defender Säkerhetscenter och Microsoft 365, medan panelerna på instrumentpanelen bara är tillgängliga i Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="8e326-114">The list of unmanaged devices and security recommendations will be available in both Microsoft Defender Security Center and Microsoft 365 security center, while the dashboard tiles will only be available in Microsoft 365 security center.</span></span>


<span data-ttu-id="8e326-115">Gör följande i Microsoft 365 säkerhetscenter:</span><span class="sxs-lookup"><span data-stu-id="8e326-115">Take the following configuration steps in Microsoft 365 security center:</span></span>

1.  <span data-ttu-id="8e326-116">Gå till Inställningar > **enhetsidentifiering**.</span><span class="sxs-lookup"><span data-stu-id="8e326-116">Navigate to **Settings > Device discovery**.</span></span>
2.  <span data-ttu-id="8e326-117">Välj det identifieringsläge du vill använda på dina onboarded-enheter.</span><span class="sxs-lookup"><span data-stu-id="8e326-117">Select the discovery mode to use on your onboarded devices.</span></span> 
3.  <span data-ttu-id="8e326-118">Om du har valt att använda standardidentifiering väljer du vilka enheter som ska användas för aktiv sannolikhet: alla enheter eller en delmängd genom att ange deras enhetstaggar.</span><span class="sxs-lookup"><span data-stu-id="8e326-118">If you've selected to use standard discovery, select which devices to use for active probing: all devices or on a subset by specifying their device tags.</span></span>
4. <span data-ttu-id="8e326-119">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="8e326-119">Click **Save**.</span></span>


## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a><span data-ttu-id="8e326-120">Undanta enheter från aktivt sök efter standardidentifiering</span><span class="sxs-lookup"><span data-stu-id="8e326-120">Exclude devices from being actively probed in standard discovery</span></span>
<span data-ttu-id="8e326-121">Om det finns enheter i nätverket som inte ska sökas igenom aktivt (till exempel enheter som används som Honey honeytek för ett annat säkerhetsverktyg) kan du också definiera en lista med undantag så att de inte genomsöks.</span><span class="sxs-lookup"><span data-stu-id="8e326-121">If there are devices on your network which should not be actively scanned (for example, devices used as honeypots for another security tool), you can also define a list of exclusions to prevent them from being scanned.</span></span> <span data-ttu-id="8e326-122">Observera att enheter fortfarande kan upptäckas med hjälp av Grundläggande identifieringsläge.</span><span class="sxs-lookup"><span data-stu-id="8e326-122">Note that devices can still be discovered using Basic discovery mode.</span></span> <span data-ttu-id="8e326-123">Dessa enheter kommer att upptäckas passivt men kommer inte att sökas aktivt.</span><span class="sxs-lookup"><span data-stu-id="8e326-123">Those devices will be passively discovered but won't be actively probed.</span></span> 

## <a name="select-networks-to-monitor"></a><span data-ttu-id="8e326-124">Välja nätverk att övervaka</span><span class="sxs-lookup"><span data-stu-id="8e326-124">Select networks to monitor</span></span>
 <span data-ttu-id="8e326-125">Microsoft Defender för Endpoint analyserar ett nätverk och fastställer om det är ett företagsnätverk som måste övervakas eller ett icke-företagsnätverk som kan ignoreras.</span><span class="sxs-lookup"><span data-stu-id="8e326-125">Microsoft Defender for Endpoint analyzes a network and determines if it is a corporate network that needs to be monitored or a non-corporate network that can be ignored.</span></span> <span data-ttu-id="8e326-126">Företagsnätverk övervakas vanligtvis.</span><span class="sxs-lookup"><span data-stu-id="8e326-126">Corporate networks are typically chosen to be monitored.</span></span> <span data-ttu-id="8e326-127">Du kan dock åsidosätta det här beslutet genom att välja att övervaka icke-företagsnätverk där enheter med registrering finns.</span><span class="sxs-lookup"><span data-stu-id="8e326-127">However, you can override this decision by choosing to monitor non-corporate networks where onboarded devices are found.</span></span> 

<span data-ttu-id="8e326-128">Du kan konfigurera var enhetsidentifiering kan utföras genom att ange vilka nätverk som ska övervakas.</span><span class="sxs-lookup"><span data-stu-id="8e326-128">You can configure where device discovery can be performed by specifying which networks to monitor.</span></span> <span data-ttu-id="8e326-129">När ett nätverk övervakas kan enhetsidentifieringen utföras på det.</span><span class="sxs-lookup"><span data-stu-id="8e326-129">When a network is monitored, device discovery can be performed on it.</span></span> 

<span data-ttu-id="8e326-130">En lista över nätverk där enhetsidentifiering kan utföras visas på sidan **Övervakade** nätverk.</span><span class="sxs-lookup"><span data-stu-id="8e326-130">A list of networks where device discovery can be performed is shown in the **Monitored networks** page.</span></span> 


>[!NOTE]
> <span data-ttu-id="8e326-131">Endast de 50 främsta nätverken (enligt antalet associerade enheter) kommer att vara tillgängliga i nätverkslistan.</span><span class="sxs-lookup"><span data-stu-id="8e326-131">Only top 50 networks (according to the number of associated devices) will be available in the network list.</span></span> 


<span data-ttu-id="8e326-132">Listan över övervakade nätverk sorteras baserat på det totala antalet enheter som har setts på nätverket under de senaste 7 dagarna.</span><span class="sxs-lookup"><span data-stu-id="8e326-132">The list of monitored networks is sorted based upon the total number of devices seen on the network in the last 7 days.</span></span>


<span data-ttu-id="8e326-133">Du kan använda ett filter för att visa följande nätverksidentifierings tillstånd:</span><span class="sxs-lookup"><span data-stu-id="8e326-133">You can apply a filter to view any of the following network discovery states:</span></span>

- <span data-ttu-id="8e326-134">**Övervakade nätverk** – nätverk där enhetsidentifieringen utförs.</span><span class="sxs-lookup"><span data-stu-id="8e326-134">**Monitored networks** - Networks where device discovery is performed.</span></span>
- <span data-ttu-id="8e326-135">**Ignorerade nätverk** – Det här nätverket ignoreras och enhetsidentifieringen utförs inte på det.</span><span class="sxs-lookup"><span data-stu-id="8e326-135">**Ignored networks** - This network will be ignored and device discovery will not be performed on it.</span></span>
- <span data-ttu-id="8e326-136">**Alla** – Både övervakade och ignorerade nätverk visas.</span><span class="sxs-lookup"><span data-stu-id="8e326-136">**All** - Both monitored and ignored networks will be displayed.</span></span> 


### <a name="configure-the-network-monitor-state"></a><span data-ttu-id="8e326-137">Konfigurera nätverksövervakningstillståndet</span><span class="sxs-lookup"><span data-stu-id="8e326-137">Configure the network monitor state</span></span>
<span data-ttu-id="8e326-138">Du styr var enhetsidentifiering sker.</span><span class="sxs-lookup"><span data-stu-id="8e326-138">You control where device discovery takes place.</span></span> <span data-ttu-id="8e326-139">Övervakade nätverk är den plats där enhetsidentifiering utförs och vanligtvis är företagsnätverk.</span><span class="sxs-lookup"><span data-stu-id="8e326-139">Monitored networks is where device discovery will be performed and are typically corporate networks.</span></span> <span data-ttu-id="8e326-140">Du kan också välja att ignorera nätverk eller välja den första identifieringsklassificeringsklassificeringen när du har modifierat ett tillstånd.</span><span class="sxs-lookup"><span data-stu-id="8e326-140">You can also choose to ignore networks or select the initial discovery classification after modifying a state.</span></span> 

<span data-ttu-id="8e326-141">När du väljer den första identifieringsklassificeringen innebär det att standardsystemets nätverksövervakningstillstånd tillämpas.</span><span class="sxs-lookup"><span data-stu-id="8e326-141">Choosing the initial discovery classification means applying the default system-made network monitor state.</span></span> <span data-ttu-id="8e326-142">Om du väljer standardsystemövervakningstillståndet övervakas nätverk som har identifierats som företagsbaserade och sådana som identifieras som icke-företagsbaserade ignoreras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="8e326-142">Selecting the default system-made network monitor state means that networks that were identified to be corporate, will be monitored, and ones identified as non-corporate, will be ignored automatically.</span></span>
 
1. <span data-ttu-id="8e326-143">Välj **Inställningar > enhetsidentifiering**.</span><span class="sxs-lookup"><span data-stu-id="8e326-143">Select **Settings > Device discovery**.</span></span>
2. <span data-ttu-id="8e326-144">Välj **Övervakade nätverk**.</span><span class="sxs-lookup"><span data-stu-id="8e326-144">Select **Monitored networks**.</span></span> 
3. <span data-ttu-id="8e326-145">Visa listan över nätverk.</span><span class="sxs-lookup"><span data-stu-id="8e326-145">View the list of networks.</span></span> 
4. <span data-ttu-id="8e326-146">Välj de tre punkterna bredvid nätverksnamnet.</span><span class="sxs-lookup"><span data-stu-id="8e326-146">Select the three dots next to the network name.</span></span> 
5. <span data-ttu-id="8e326-147">Välj om du vill övervaka, ignorera eller använda den första identifieringsklassificeringsklassificeringen.</span><span class="sxs-lookup"><span data-stu-id="8e326-147">Choose whether you want to monitor, ignore, or use the initial discovery classification.</span></span> 
    
    > [!WARNING]
    >- <span data-ttu-id="8e326-148">Om du väljer att övervaka ett nätverk som inte identifierats av Microsoft Defender för Endpoint som ett företagsnätverk kan det orsaka enhetsidentifiering utanför företagsnätverket och kan därför identifiera hemenheter eller andra enheter som inte är företagsbaserade.</span><span class="sxs-lookup"><span data-stu-id="8e326-148">Choosing to monitor a network that was not identified by Microsoft Defender for Endpoint as a corporate network can cause device discovery outside of your corporate network, and may therefore detect home or other non-corporate devices.</span></span> 
    > - <span data-ttu-id="8e326-149">Om du väljer att ignorera ett nätverk avbryts övervakning och identifiering av enheter i nätverket.</span><span class="sxs-lookup"><span data-stu-id="8e326-149">Choosing to ignore a network will stop monitoring and discovering devices in that network.</span></span> <span data-ttu-id="8e326-150">Enheter som redan identifierats tas inte bort från inventeringen, men uppdateras inte längre, och informationen behålls tills Defender för Slutpunktens datalagringsperiod upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="8e326-150">Devices that were already discovered will not be removed from the inventory, but will no longer be updated, and details will be retained until the data retention period of the Defender for Endpoint expires.</span></span>
    > - <span data-ttu-id="8e326-151">Innan du väljer att övervaka nätverk utanför företaget måste du ha behörighet att göra det.</span><span class="sxs-lookup"><span data-stu-id="8e326-151">Before choosing to monitor non-corporate networks, you must ensure you have permission to do so.</span></span> <br>


6. <span data-ttu-id="8e326-152">Bekräfta att du vill göra ändringen.</span><span class="sxs-lookup"><span data-stu-id="8e326-152">Confirm that you want to make the change.</span></span> 




## <a name="see-also"></a><span data-ttu-id="8e326-153">Se även</span><span class="sxs-lookup"><span data-stu-id="8e326-153">See also</span></span>
- [<span data-ttu-id="8e326-154">Översikt över enhetsidentifiering</span><span class="sxs-lookup"><span data-stu-id="8e326-154">Device discovery overview</span></span>](device-discovery.md)
- [<span data-ttu-id="8e326-155">Vanliga frågor och svar om enhetsupptäckt</span><span class="sxs-lookup"><span data-stu-id="8e326-155">Device discovery FAQs</span></span>](device-discovery-faq.md)