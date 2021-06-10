---
title: Inventering av programvara i Hantering av hot och säkerhetsrisker
description: Sidan för programvaruinventering för Microsoft Defender för Endpoints Hantering av hot och säkerhetsrisker visar hur många svagheter som har upptäckts i programvaran.
keywords: Hantering av hot och säkerhetsrisker, Microsoft Defender för slutpunkt, Microsoft Defender för programvaruinventering av slutpunkt, Microsoft Defender för slutpunktshot & hantering av säkerhetsrisker, Microsoft Defender för slutpunktshot & hantering av säkerhetsrisker programvarulager, Microsoft Defender för endpoint tvm-programinventering, tvm-programinventering
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0d270760cfed965c8190668afcdb1cc25223d2b1
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933727"
---
# <a name="software-inventory---threat-and-vulnerability-management"></a><span data-ttu-id="33269-104">Inventering av programvara – Hantering av hot och säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="33269-104">Software inventory - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="33269-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="33269-105">**Applies to:**</span></span>
- [<span data-ttu-id="33269-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="33269-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="33269-107">Hot och hantering av säkerhetsrisker</span><span class="sxs-lookup"><span data-stu-id="33269-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="33269-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33269-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="33269-109">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="33269-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="33269-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="33269-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="33269-111">Software inventory in Hantering av hot och säkerhetsrisker is a list of known software in your organization with [official Common Platform Enumerations (CPE)](https://nvd.nist.gov/products/cpe).</span><span class="sxs-lookup"><span data-stu-id="33269-111">The software inventory in threat and vulnerability management is a list of known software in your organization with official [Common Platform Enumerations (CPE)](https://nvd.nist.gov/products/cpe).</span></span> <span data-ttu-id="33269-112">Eventuella svagheter publiceras inte för programvaruprodukter utan ett officiellt CPE.</span><span class="sxs-lookup"><span data-stu-id="33269-112">Software products without an official CPE don’t have vulnerabilities published.</span></span> <span data-ttu-id="33269-113">Den innehåller även information som namn på leverantören, antal svagheter, hot och antal exponerade enheter.</span><span class="sxs-lookup"><span data-stu-id="33269-113">It also includes details such as the name of the vendor, number of weaknesses, threats, and number of exposed devices.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="33269-114">Så här fungerar det</span><span class="sxs-lookup"><span data-stu-id="33269-114">How it works</span></span>

<span data-ttu-id="33269-115">När det gäller identifiering utnyttjar vi samma uppsättning signaler som ansvarar för identifierings- och sårbarhetsbedömning i Microsoft Defender för funktioner för identifiering och [svar av slutpunkter.](overview-endpoint-detection-response.md)</span><span class="sxs-lookup"><span data-stu-id="33269-115">In the field of discovery, we're leveraging the same set of signals that is responsible for detection and vulnerability assessment in [Microsoft Defender for Endpoint detection and response capabilities](overview-endpoint-detection-response.md).</span></span>

<span data-ttu-id="33269-116">Eftersom det är i realtid kommer du att se sårbarhetsinformation när de upptäcks.</span><span class="sxs-lookup"><span data-stu-id="33269-116">Since it's real time, in a matter of minutes, you'll see vulnerability information as they get discovered.</span></span> <span data-ttu-id="33269-117">Motorn hämtar automatiskt information från flera säkerhetsfeeds.</span><span class="sxs-lookup"><span data-stu-id="33269-117">The engine automatically grabs information from multiple security feeds.</span></span> <span data-ttu-id="33269-118">Faktum är att du ser om en viss programvara är ansluten till en kampanj med verkliga hot.</span><span class="sxs-lookup"><span data-stu-id="33269-118">In fact, you'll see if a particular software is connected to a live threat campaign.</span></span> <span data-ttu-id="33269-119">Den innehåller även en länk till en rapport om hotanalys så snart den blir tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="33269-119">It also provides a link to a Threat Analytics report soon as it's available.</span></span>

## <a name="navigate-to-the-software-inventory-page"></a><span data-ttu-id="33269-120">Gå till sidan för programvaruinventering</span><span class="sxs-lookup"><span data-stu-id="33269-120">Navigate to the Software inventory page</span></span>

<span data-ttu-id="33269-121">Öppna sidan Software inventory genom att välja **Software inventory** Hantering av hot och säkerhetsrisker navigationsmenyn i [Microsoft Defender Säkerhetscenter](portal-overview.md).</span><span class="sxs-lookup"><span data-stu-id="33269-121">Access the Software inventory page by selecting **Software inventory** from the threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md).</span></span>

<span data-ttu-id="33269-122">Visa programvara på specifika enheter på sidorna för enskilda enheter i [listan över enheter](machines-view-overview.md).</span><span class="sxs-lookup"><span data-stu-id="33269-122">View software on specific devices in the individual devices pages from the [devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="33269-123">Om du söker efter programvara med hjälp av den globala sökningen i Microsoft Defender för Endpoint ska du se till att lägga till ett understreck i stället för ett blanksteg.</span><span class="sxs-lookup"><span data-stu-id="33269-123">If you search for software using the Microsoft Defender for Endpoint global search, make sure to put an underscore instead of a space.</span></span> <span data-ttu-id="33269-124">För bästa sökresultat skriver du exempelvis "windows_10" i stället för "Windows 10".</span><span class="sxs-lookup"><span data-stu-id="33269-124">For example, for the best search results you'd write "windows_10" instead of "Windows 10".</span></span>

## <a name="software-inventory-overview"></a><span data-ttu-id="33269-125">Översikt över programvaruinventering</span><span class="sxs-lookup"><span data-stu-id="33269-125">Software inventory overview</span></span>

<span data-ttu-id="33269-126">Sidan **För inventering** av programvara öppnas med en lista över programvara som installerats i nätverket, inklusive leverantörsnamn, svagheter, hot associerade med dem, exponerade enheter, påverkan på exponeringsresultat och taggar.</span><span class="sxs-lookup"><span data-stu-id="33269-126">The **Software inventory** page opens with a list of software installed in your network, including the vendor name, weaknesses found, threats associated with them, exposed devices, impact to exposure score, and tags.</span></span>

<span data-ttu-id="33269-127">Du kan filtrera listvyn baserat på var programvaran finns, hot som är associerade med dem och taggar som om supporten för programvaran har uppnåtts.</span><span class="sxs-lookup"><span data-stu-id="33269-127">You can filter the list view based on weaknesses found in the software, threats associated with them, and tags like whether the software has reached end-of-support.</span></span>

![Exempel på startsidan för programvaruinventering.](images/tvm-software-inventory.png)

<span data-ttu-id="33269-129">Välj den programvara du vill undersöka.</span><span class="sxs-lookup"><span data-stu-id="33269-129">Select the software that you want to investigate.</span></span> <span data-ttu-id="33269-130">En utfällningspanel öppnas med en mer komprimerad vy av informationen på sidan.</span><span class="sxs-lookup"><span data-stu-id="33269-130">A flyout panel will open with a more compact view of the information on the page.</span></span> <span data-ttu-id="33269-131">Du kan antingen dyka ned djupare i undersökningen och välja Öppna programvarusida **eller** flagga tekniska inkonsekvenser genom att välja **Rapportinsekvens.**</span><span class="sxs-lookup"><span data-stu-id="33269-131">You can either dive deeper into the investigation and select **Open software page**, or flag any technical inconsistencies by selecting **Report inaccuracy**.</span></span>

### <a name="software-that-isnt-supported"></a><span data-ttu-id="33269-132">Programvara som inte stöds</span><span class="sxs-lookup"><span data-stu-id="33269-132">Software that isn't supported</span></span>

<span data-ttu-id="33269-133">Programvara som för närvarande inte stöds av hot & hantering av säkerhetsrisker finns på sidan för programvaruinventering.</span><span class="sxs-lookup"><span data-stu-id="33269-133">Software that isn't currently supported by threat & vulnerability management may be present in the Software inventory page.</span></span> <span data-ttu-id="33269-134">Eftersom det inte stöds är endast begränsade data tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="33269-134">Because it is not supported, only limited data will be available.</span></span> <span data-ttu-id="33269-135">Filtrera efter programvara som inte stöds med alternativet "Inte tillgängligt" i avsnittet "Bra att"</span><span class="sxs-lookup"><span data-stu-id="33269-135">Filter by unsupported software with the "Not available" option in the "Weakness" section.</span></span>

![Programvarufilter som inte stöds.](images/tvm-unsupported-software-filter.png)

<span data-ttu-id="33269-137">Följande anger att en programvara inte stöds:</span><span class="sxs-lookup"><span data-stu-id="33269-137">The following indicates that a software is not supported:</span></span>

- <span data-ttu-id="33269-138">Fältet Svagheter visar "Inte tillgängligt"</span><span class="sxs-lookup"><span data-stu-id="33269-138">Weaknesses field shows "Not available"</span></span>
- <span data-ttu-id="33269-139">Fältet Exponerade enheter visar ett streck</span><span class="sxs-lookup"><span data-stu-id="33269-139">Exposed devices field shows a dash</span></span>
- <span data-ttu-id="33269-140">Informationstext på sidopanelen och på programvarusidan</span><span class="sxs-lookup"><span data-stu-id="33269-140">Informational text added in side panel and in software page</span></span>
- <span data-ttu-id="33269-141">Programsidan kommer inte att ha säkerhetsrekommendationer, identifierade säkerhetsproblem eller avsnitt om händelsetidslinje</span><span class="sxs-lookup"><span data-stu-id="33269-141">The software page won't have the security recommendations, discovered vulnerabilities, or event timeline sections</span></span>

<span data-ttu-id="33269-142">För närvarande visas inte produkter utan CPE på sidan för programvaruinventering, utan endast i inventeringen av programvara på enhetsnivå.</span><span class="sxs-lookup"><span data-stu-id="33269-142">Currently, products without a CPE are not shown in the software inventory page, only in the device level software inventory.</span></span>

## <a name="software-inventory-on-devices"></a><span data-ttu-id="33269-143">Inventering av programvara på enheter</span><span class="sxs-lookup"><span data-stu-id="33269-143">Software inventory on devices</span></span>

<span data-ttu-id="33269-144">Från Microsoft Defender Säkerhetscenter navigeringspanelen går du till **[listan Enheter](machines-view-overview.md)**.</span><span class="sxs-lookup"><span data-stu-id="33269-144">From the Microsoft Defender Security Center navigation panel, go to the **[Devices list](machines-view-overview.md)**.</span></span> <span data-ttu-id="33269-145">Välj namnet på en enhet för att öppna enhetssidan  (t.ex. Dator1). Välj sedan fliken Programvaruinventering för att se en lista över alla kända program som finns på enheten.</span><span class="sxs-lookup"><span data-stu-id="33269-145">Select the name of a device to open the device page (like Computer1), then select the **Software inventory** tab to see a list of all the known software present on the device.</span></span> <span data-ttu-id="33269-146">Välj en specifik programvarupost för att öppna den utfällade listan med mer information.</span><span class="sxs-lookup"><span data-stu-id="33269-146">Select a specific software entry to open the flyout with more information.</span></span>

<span data-ttu-id="33269-147">Programvaran kan visas på enhetsnivå även om den för närvarande inte stöds av Hantering av hot och säkerhetsrisker.</span><span class="sxs-lookup"><span data-stu-id="33269-147">Software may be visible at the device level even if it is currently not supported by threat and vulnerability management.</span></span> <span data-ttu-id="33269-148">Men endast begränsade data kommer att vara tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="33269-148">However, only limited data will be available.</span></span> <span data-ttu-id="33269-149">Du vet om programvaran inte stöds eftersom det står "Inte tillgänglig" i kolumnen "Det här är en bra dag".</span><span class="sxs-lookup"><span data-stu-id="33269-149">You'll know if software is unsupported because it will say "Not available" in the "Weakness" column.</span></span>

<span data-ttu-id="33269-150">Programvara utan CPE kan också visas under denna enhetsspecifika inventering av programvara.</span><span class="sxs-lookup"><span data-stu-id="33269-150">Software with no CPE can also show up under this device specific software inventory.</span></span>

### <a name="software-evidence"></a><span data-ttu-id="33269-151">Programvarubevis</span><span class="sxs-lookup"><span data-stu-id="33269-151">Software evidence</span></span>

<span data-ttu-id="33269-152">Se bevis för var vi upptäckte en specifik programvara på en enhet från registret, hårddisken eller båda. Du hittar den på alla enheter i inventeringen av enhetsprogramvaran.</span><span class="sxs-lookup"><span data-stu-id="33269-152">See evidence of where we detected a specific software on a device from the registry, disk, or both.You can find it on any device in the device software inventory.</span></span>

<span data-ttu-id="33269-153">Välj ett programvarunamn för att öppna den utfällna sidan och leta efter avsnittet "Programvarubevis".</span><span class="sxs-lookup"><span data-stu-id="33269-153">Select a software name to open the flyout, and look for the section called "Software Evidence."</span></span>

![Exempel på programvaru bevis Windows 10 i listan över enheter, med registersökväg för programvaru bevis.](images/tvm-software-evidence.png)

## <a name="software-pages"></a><span data-ttu-id="33269-155">Programvarusidor</span><span class="sxs-lookup"><span data-stu-id="33269-155">Software pages</span></span>

<span data-ttu-id="33269-156">Du kan visa programvarusidor på några olika sätt:</span><span class="sxs-lookup"><span data-stu-id="33269-156">You can view software pages a few different ways:</span></span>

- <span data-ttu-id="33269-157">Sidan För programvaruinventering > Välj ett programvarunamn > **Välj Sidan Öppna programvara i** den utfäll plats</span><span class="sxs-lookup"><span data-stu-id="33269-157">Software inventory page > Select a software name > Select **Open software page** in the flyout</span></span>
- <span data-ttu-id="33269-158">[Sidan Rekommendationer](tvm-security-recommendation.md) för > Välj en rekommendation > Välj **sidan Öppna programvara i** den utfällda sidan</span><span class="sxs-lookup"><span data-stu-id="33269-158">[Security recommendations page](tvm-security-recommendation.md) > Select a recommendation > Select **Open software page** in the flyout</span></span>
- <span data-ttu-id="33269-159">[](threat-and-vuln-mgt-event-timeline.md) Sidan Händelsetidslinje > Välj en händelse > Välj namnet på den hyperlänkade programvaran (till exempel Visual Studio 2017) i avsnittet "Relaterad komponent" i den utfällbar menyn</span><span class="sxs-lookup"><span data-stu-id="33269-159">[Event timeline page](threat-and-vuln-mgt-event-timeline.md) > Select an event > Select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout</span></span>

 <span data-ttu-id="33269-160">En hel sida visas med all information om en viss programvara och följande information:</span><span class="sxs-lookup"><span data-stu-id="33269-160">A full page will appear with all the details of a specific software and the following information:</span></span>

- <span data-ttu-id="33269-161">Sidopanel med leverantörsinformation, av programvaran i organisationen (inklusive antal enheter som den är installerad på och exponerade enheter som inte har korrigerats), om och sårbarhet är tillgänglig och påverkan på exponeringsresultatet.</span><span class="sxs-lookup"><span data-stu-id="33269-161">Side panel with vendor information, prevalence of the software in the organization (including number of devices it's installed on, and exposed devices that aren't patched), whether and exploit is available, and impact to your exposure score.</span></span>
- <span data-ttu-id="33269-162">Datavisualiseringar som visar antalet säkerhetsproblem och felkonfigurering, samt deras allvarlighetsgrad.</span><span class="sxs-lookup"><span data-stu-id="33269-162">Data visualizations showing the number of, and severity of, vulnerabilities and misconfigurations.</span></span> <span data-ttu-id="33269-163">Dessutom diagram med antalet exponerade enheter.</span><span class="sxs-lookup"><span data-stu-id="33269-163">Also, graphs with the number of exposed devices.</span></span>
- <span data-ttu-id="33269-164">Flikar som visar information som:</span><span class="sxs-lookup"><span data-stu-id="33269-164">Tabs showing information such as:</span></span>
    - <span data-ttu-id="33269-165">Motsvarande säkerhetsrekommendationer för svagheter och svagheter som identifieras.</span><span class="sxs-lookup"><span data-stu-id="33269-165">Corresponding security recommendations for the weaknesses and vulnerabilities identified.</span></span>
    - <span data-ttu-id="33269-166">Namngivna CV:n för identifierade säkerhetsproblem.</span><span class="sxs-lookup"><span data-stu-id="33269-166">Named CVEs of discovered vulnerabilities.</span></span>
    - <span data-ttu-id="33269-167">Enheter som har programvaran installerad (tillsammans med enhetsnamn, domän, operativsystem med mera).</span><span class="sxs-lookup"><span data-stu-id="33269-167">Devices that have the software installed (along with device name, domain, OS, and more).</span></span>
    - <span data-ttu-id="33269-168">Lista över programvaruversion (inklusive antalet enheter som versionen är installerad på, antalet identifierade säkerhetsproblem och namnen på de installerade enheterna).</span><span class="sxs-lookup"><span data-stu-id="33269-168">Software version list (including number of devices the version is installed on, the number of discovered vulnerabilities, and the names of the installed devices).</span></span>

    ![Exempelsida för programvara Visual Studio 2017 med information om programvaran, svagheter, exponerade enheter med mera.](images/tvm-software-page-example.png)

## <a name="report-inaccuracy"></a><span data-ttu-id="33269-170">Rapportera felaktigheter</span><span class="sxs-lookup"><span data-stu-id="33269-170">Report inaccuracy</span></span>

<span data-ttu-id="33269-171">Rapportera en falsk positiv när du ser någon vag, felaktig eller ofullständig information.</span><span class="sxs-lookup"><span data-stu-id="33269-171">Report a false positive when you see any vague, inaccurate, or incomplete information.</span></span> <span data-ttu-id="33269-172">Du kan också rapportera säkerhetsrekommendationer som redan har åtgärdats.</span><span class="sxs-lookup"><span data-stu-id="33269-172">You can also report on security recommendations that have already been remediated.</span></span>

1. <span data-ttu-id="33269-173">Öppna programvarans utfällutrymme på sidan För programvaruinventering.</span><span class="sxs-lookup"><span data-stu-id="33269-173">Open the software flyout on the Software inventory page.</span></span>
2. <span data-ttu-id="33269-174">Välj **Rapportens felaktigheter.**</span><span class="sxs-lookup"><span data-stu-id="33269-174">Select **Report inaccuracy**.</span></span>
3. <span data-ttu-id="33269-175">I den utfällliga fönsterrutan väljer du kategorin felaktigheter i den nedrullningsmenyn, fyller i din e-postadress och information om felaktigheter.</span><span class="sxs-lookup"><span data-stu-id="33269-175">From the flyout pane, select the inaccuracy category from the drop-down menu, fill in your email address, and details about the inaccuracy.</span></span>
4. <span data-ttu-id="33269-176">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="33269-176">Select **Submit**.</span></span> <span data-ttu-id="33269-177">Din feedback skickas omedelbart till Hantering av hot och säkerhetsrisker experter.</span><span class="sxs-lookup"><span data-stu-id="33269-177">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="33269-178">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="33269-178">Related articles</span></span>

- [<span data-ttu-id="33269-179">Översikt över hantering av säkerhetsrisker hot och hot</span><span class="sxs-lookup"><span data-stu-id="33269-179">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="33269-180">Säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="33269-180">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="33269-181">Tidlinje för händelse</span><span class="sxs-lookup"><span data-stu-id="33269-181">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
- [<span data-ttu-id="33269-182">Visa och ordna listan Microsoft Defender för slutpunktsenheter</span><span class="sxs-lookup"><span data-stu-id="33269-182">View and organize the Microsoft Defender for Endpoint Devices list</span></span>](machines-view-overview.md)
