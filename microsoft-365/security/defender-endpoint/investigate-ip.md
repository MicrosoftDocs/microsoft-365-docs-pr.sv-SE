---
title: Undersöka en IP-adress som associeras med en avisering
description: Använd undersökningsalternativen för att undersöka möjlig kommunikation mellan enheter och externa IP-adresser.
keywords: undersöker, undersökning, IP-adress, avisering, microsoft defender atp, extern IP
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: ca7f5e9126ffd57f7e858210e006bc05459d567b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070642"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="bdf82-104">Undersöka en IP-adress som är kopplad till en Microsoft Defender för Slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="bdf82-104">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bdf82-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="bdf82-105">**Applies to:**</span></span>
- [<span data-ttu-id="bdf82-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="bdf82-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="bdf82-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bdf82-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="bdf82-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="bdf82-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bdf82-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="bdf82-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="bdf82-110">Undersök eventuell kommunikation mellan dina enheter och IP-adresser (External Internet Protocol).</span><span class="sxs-lookup"><span data-stu-id="bdf82-110">Examine possible communication between your devices and external internet protocol (IP) addresses.</span></span>

<span data-ttu-id="bdf82-111">Identifiera alla enheter i organisationen som kommunicerat med en misstänkt eller känd skadlig IP-adress, till exempel kommando- och kontrollservrar (C2), för att fastställa möjlig omfattning för intrång, associerade filer och smittade enheter.</span><span class="sxs-lookup"><span data-stu-id="bdf82-111">Identifying all devices in the organization that communicated with a suspected or known malicious IP address, such as Command and Control (C2) servers, helps determine the potential scope of breach, associated files, and infected devices.</span></span>

<span data-ttu-id="bdf82-112">Du hittar information i följande avsnitt i IP-adressvyn:</span><span class="sxs-lookup"><span data-stu-id="bdf82-112">You can find information from the following sections in the IP address view:</span></span>

- <span data-ttu-id="bdf82-113">IP globalt</span><span class="sxs-lookup"><span data-stu-id="bdf82-113">IP worldwide</span></span>
- <span data-ttu-id="bdf82-114">Spegelvända DNS-namn</span><span class="sxs-lookup"><span data-stu-id="bdf82-114">Reverse DNS names</span></span>
- <span data-ttu-id="bdf82-115">Aviseringar relaterade till denna IP</span><span class="sxs-lookup"><span data-stu-id="bdf82-115">Alerts related to this IP</span></span>
- <span data-ttu-id="bdf82-116">IP i organisation</span><span class="sxs-lookup"><span data-stu-id="bdf82-116">IP in organization</span></span>
- <span data-ttu-id="bdf82-117">Endeprenad</span><span class="sxs-lookup"><span data-stu-id="bdf82-117">Prevalence</span></span>

## <a name="ip-worldwide-and-reverse-dns-names"></a><span data-ttu-id="bdf82-118">IP Worldwide and Reverse DNS names</span><span class="sxs-lookup"><span data-stu-id="bdf82-118">IP Worldwide and Reverse DNS names</span></span>

<span data-ttu-id="bdf82-119">I avsnittet för IP-adressinformation visas attribut för IP-adressen, till exempel dess ASN och de omvända DNS-namnen.</span><span class="sxs-lookup"><span data-stu-id="bdf82-119">The IP address details section shows attributes of the IP address such as its ASN and its Reverse DNS names.</span></span>

## <a name="alerts-related-to-this-ip"></a><span data-ttu-id="bdf82-120">Aviseringar relaterade till denna IP</span><span class="sxs-lookup"><span data-stu-id="bdf82-120">Alerts related to this IP</span></span>

<span data-ttu-id="bdf82-121">Aviseringar **relaterade till den här IP-adressen** innehåller en lista med aviseringar som associeras med IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="bdf82-121">The **Alerts related to this IP** section provides a list of alerts that are associated with the IP.</span></span>

## <a name="ip-in-organization"></a><span data-ttu-id="bdf82-122">IP i organisation</span><span class="sxs-lookup"><span data-stu-id="bdf82-122">IP in organization</span></span>

<span data-ttu-id="bdf82-123">I **avsnittet IP i** organisationen finns information om hur IP-adressen i organisationen utser.</span><span class="sxs-lookup"><span data-stu-id="bdf82-123">The **IP in organization** section provides details on the prevalence of the IP address in the organization.</span></span>

## <a name="prevalence"></a><span data-ttu-id="bdf82-124">Endeprenad</span><span class="sxs-lookup"><span data-stu-id="bdf82-124">Prevalence</span></span>

<span data-ttu-id="bdf82-125">I **avsnittet Föregående** visas hur många enheter som har anslutit till den här IP-adressen och när IP-adressen sågs för första och sista gången.</span><span class="sxs-lookup"><span data-stu-id="bdf82-125">The **Prevalence** section displays how many devices have connected to this IP address, and when the IP was first and last seen.</span></span> <span data-ttu-id="bdf82-126">Du kan filtrera resultatet av det här avsnittet efter tidsperiod. standardtiden är 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="bdf82-126">You can filter the results of this section by time period; the default period is 30 days.</span></span>

## <a name="most-recent-observed-devices-with-ip"></a><span data-ttu-id="bdf82-127">Senaste observerade enheter med IP</span><span class="sxs-lookup"><span data-stu-id="bdf82-127">Most recent observed devices with IP</span></span>

<span data-ttu-id="bdf82-128">De **senaste observerade enheterna med** IP-avsnitt ger en kronologisk vy över händelser och tillhörande aviseringar som observerats på IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="bdf82-128">The **Most recent observed devices** with IP section provides a chronological view on the events and associated alerts that were observed on the IP address.</span></span>

<span data-ttu-id="bdf82-129">**Undersök en extern IP:**</span><span class="sxs-lookup"><span data-stu-id="bdf82-129">**Investigate an external IP:**</span></span>

1. <span data-ttu-id="bdf82-130">Välj **IP** i **sökfältets** nedrullningsbar meny.</span><span class="sxs-lookup"><span data-stu-id="bdf82-130">Select **IP** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="bdf82-131">Ange IP-adressen i **sökfältet.**</span><span class="sxs-lookup"><span data-stu-id="bdf82-131">Enter the IP address in the **Search** field.</span></span>
3. <span data-ttu-id="bdf82-132">Klicka på sökikonen eller tryck på **Retur.**</span><span class="sxs-lookup"><span data-stu-id="bdf82-132">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="bdf82-133">Information om IP-adressen visas, bland annat: registreringsinformation (om tillgänglig), omvända IP-adresser (t.ex. domäner), från enheter i organisationen som kommunicerar med denna IP-adress (under valbar tidsperiod) och vilka enheter i organisationen som har observerats kommunicerar med den här IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="bdf82-133">Details about the IP address are displayed, including: registration details (if available), reverse IPs (for example, domains), prevalence of devices in the organization that communicated with this IP Address (during selectable time period), and the devices in the organization that were observed communicating with this IP address.</span></span>

> [!NOTE]
> <span data-ttu-id="bdf82-134">Sökresultat returneras endast för IP-adresser som observerats under kommunikation med enheter i organisationen.</span><span class="sxs-lookup"><span data-stu-id="bdf82-134">Search results will only be returned for IP addresses observed in communication with devices in the organization.</span></span>

<span data-ttu-id="bdf82-135">Använd sökfiltren för att definiera sökvillkoren.</span><span class="sxs-lookup"><span data-stu-id="bdf82-135">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="bdf82-136">Du kan också använda sökrutan för tidslinjen för att filtrera de resultat som visas på alla enheter i organisationen som observerats kommunicerar med IP-adressen, filen som är kopplad till kommunikationen och det senaste observerade datumet.</span><span class="sxs-lookup"><span data-stu-id="bdf82-136">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the IP address, the file associated with the communication and the last date observed.</span></span>

<span data-ttu-id="bdf82-137">Om du klickar på något av enhetsnamnen visas enhetens vy, där du kan fortsätta undersöka rapporterade aviseringar, beteenden och händelser.</span><span class="sxs-lookup"><span data-stu-id="bdf82-137">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bdf82-138">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="bdf82-138">Related topics</span></span>

- [<span data-ttu-id="bdf82-139">Visa och ordna kön Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="bdf82-139">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="bdf82-140">Hantera Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="bdf82-140">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="bdf82-141">Undersöka Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="bdf82-141">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="bdf82-142">Undersöka en fil som är kopplad till en Microsoft Defender för slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="bdf82-142">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="bdf82-143">Undersöka enheter i listan Microsoft Defender för slutpunktsenheter</span><span class="sxs-lookup"><span data-stu-id="bdf82-143">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="bdf82-144">Undersöka en domän som är kopplad till en Microsoft Defender för slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="bdf82-144">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="bdf82-145">Undersöka ett användarkonto i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="bdf82-145">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
