---
title: Mer information om dataförlustskydd för slutpunkter i Microsoft 365
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'Dataförlustskyddet för slutpunkter i Microsoft 365 utökar övervakningen av filaktiviteter och skyddsåtgärder för dessa filer till slutpunkter. Filerna visas i lösningarna för Microsoft 365 Efterlevnadscenter '
ms.openlocfilehash: b5aa6c737bc54129ce49378a7dcaf81e9d5c612f
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162990"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="512bb-104">Mer information om dataförlustskydd för slutpunkter i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="512bb-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="512bb-105">Du kan använda dataförlustskyddet (DLP) i Microsoft 365 till att övervaka åtgärder som vidtas för objekt som du har fastställt vara känsliga och för att förhindra oavsiktlig delning av dessa objekt.</span><span class="sxs-lookup"><span data-stu-id="512bb-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="512bb-106">Mer information om DLP finns i [Mer information om dataförlustskydd](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="512bb-106">For more information on DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="512bb-107">**Dataförlustskyddet för slutpunkter** (slutpunkts-DLP) utökar funktionerna för aktivitetsövervakning och säkerhet i DLP till känsliga objekt som finns på Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="512bb-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="512bb-108">När enheter har registrerats i efterlevnadslösningarna för Microsoft 365 blir informationen om vad användare gör med känsliga objekt synlig i [aktivitetsutforskaren](data-classification-activity-explorer.md) och du kan vidta skyddsåtgärder för dessa objekt via [DLP-principer](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="512bb-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="512bb-109">Slutpunktsaktiviteter som du kan övervaka och vidta åtgärder för</span><span class="sxs-lookup"><span data-stu-id="512bb-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="512bb-110">Med Microsofts slutpunkts-DLP kan du granska och hantera följande typer av aktiviteter som användare utför på känsliga objekt som finns på Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="512bb-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> 

|<span data-ttu-id="512bb-111">Aktivitet</span><span class="sxs-lookup"><span data-stu-id="512bb-111">Activity</span></span> |<span data-ttu-id="512bb-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="512bb-112">Description</span></span>  | <span data-ttu-id="512bb-113">Granskningsbar/begränsningsbar</span><span class="sxs-lookup"><span data-stu-id="512bb-113">Auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="512bb-114">ladda upp till molntjänst, eller ge åtkomst till otillåtna webbläsare</span><span class="sxs-lookup"><span data-stu-id="512bb-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="512bb-115">Upptäcker när en användare försöker ladda upp ett objekt till en begränsad tjänstdomän eller öppna ett objekt via en webbläsare.</span><span class="sxs-lookup"><span data-stu-id="512bb-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="512bb-116">Om en webbläsare används som anges i DLP som en otillåten webbläsare, blockeras uppladdningen och användaren omdirigeras till Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="512bb-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="512bb-117">Edge Chromium tillåter eller blockerar sedan uppladdningen eller åtkomsten baserat på DLP-principkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="512bb-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="512bb-118">granskningsbart och begränsningsbart</span><span class="sxs-lookup"><span data-stu-id="512bb-118">auditable and restrictable</span></span>|
|<span data-ttu-id="512bb-119">kopiera till en annan app</span><span class="sxs-lookup"><span data-stu-id="512bb-119">copy to other app</span></span>    |<span data-ttu-id="512bb-120">Upptäcker när en användare försöker kopiera information från ett skyddat objekt och sedan klistra in den i en annan app, en annan process eller ett annat objekt.</span><span class="sxs-lookup"><span data-stu-id="512bb-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="512bb-121">Att kopiera och klistra in information i samma app, process eller objekt identifieras inte av den här aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="512bb-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="512bb-122">granskningsbart och begränsningsbart</span><span class="sxs-lookup"><span data-stu-id="512bb-122">auditable and restrictable</span></span>|
|<span data-ttu-id="512bb-123">kopiera till USB-flyttbart medium</span><span class="sxs-lookup"><span data-stu-id="512bb-123">copy to USB removable media</span></span> |<span data-ttu-id="512bb-124">Upptäcker när en användare försöker kopiera ett objekt eller information till ett flyttbart medium eller en USB-enhet.</span><span class="sxs-lookup"><span data-stu-id="512bb-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="512bb-125">granskningsbart och begränsningsbart</span><span class="sxs-lookup"><span data-stu-id="512bb-125">auditable and restrictable</span></span>|
|<span data-ttu-id="512bb-126">kopiera till en nätverksresurs</span><span class="sxs-lookup"><span data-stu-id="512bb-126">copy to a network share</span></span>    |<span data-ttu-id="512bb-127">Upptäcker när en användare försöker kopiera ett objekt till en nätverksresurs eller en mappad nätverksenhet</span><span class="sxs-lookup"><span data-stu-id="512bb-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="512bb-128">granskningsbart och begränsningsbart</span><span class="sxs-lookup"><span data-stu-id="512bb-128">auditable and restrictable</span></span>|
|<span data-ttu-id="512bb-129">skriva ut ett dokument</span><span class="sxs-lookup"><span data-stu-id="512bb-129">print a document</span></span>    |<span data-ttu-id="512bb-130">Upptäcker när en användare försöker skriva ut ett skyddat objekt till en lokal skrivare eller en nätverksskrivare.</span><span class="sxs-lookup"><span data-stu-id="512bb-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="512bb-131">granskningsbart och begränsningsbart</span><span class="sxs-lookup"><span data-stu-id="512bb-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="512bb-132">kopiera till en fjärrsession</span><span class="sxs-lookup"><span data-stu-id="512bb-132">copy to a remote session</span></span>|<span data-ttu-id="512bb-133">Upptäcker när en användare försöker kopiera ett objekt till en session för fjärrdatorer</span><span class="sxs-lookup"><span data-stu-id="512bb-133">Detects when a user attempts to copy an item to a remote desktop session</span></span> |  <span data-ttu-id="512bb-134">granskningsbart och begränsningsbart</span><span class="sxs-lookup"><span data-stu-id="512bb-134">auditable and restrictable</span></span>|
|<span data-ttu-id="512bb-135">kopiera till en Bluetooth-enhet</span><span class="sxs-lookup"><span data-stu-id="512bb-135">copy to a Bluetooth device</span></span>|<span data-ttu-id="512bb-136">Upptäcker när en användare försöker kopiera ett objekt till en otillåten Bluetooth-app (enligt definitionen i listan med otillåtna Bluetooth-appar i inställningarna för slutpunkts-DLP:n).</span><span class="sxs-lookup"><span data-stu-id="512bb-136">Detects when a user attempts to copy an item to an unallowed Bluetooth app (as defined in the list of unallowed Bluetooth aps in Endpoint DLP settings).</span></span>| <span data-ttu-id="512bb-137">granskningsbart och begränsningsbart</span><span class="sxs-lookup"><span data-stu-id="512bb-137">auditable and restrictable</span></span>|
|<span data-ttu-id="512bb-138">skapa ett objekt.</span><span class="sxs-lookup"><span data-stu-id="512bb-138">create an item</span></span>|<span data-ttu-id="512bb-139">Upptäcker när en användare skapar ett objekt</span><span class="sxs-lookup"><span data-stu-id="512bb-139">Detects when a user creates an item</span></span>| <span data-ttu-id="512bb-140">granskningsbart</span><span class="sxs-lookup"><span data-stu-id="512bb-140">auditable</span></span>|
|<span data-ttu-id="512bb-141">byta namn på ett objekt</span><span class="sxs-lookup"><span data-stu-id="512bb-141">rename an item</span></span>|<span data-ttu-id="512bb-142">Upptäcker när en användare byter namn på ett objekt</span><span class="sxs-lookup"><span data-stu-id="512bb-142">Detects when a user renames an item</span></span>| <span data-ttu-id="512bb-143">granskningsbart</span><span class="sxs-lookup"><span data-stu-id="512bb-143">auditable</span></span>|

 ## <a name="monitored-files"></a><span data-ttu-id="512bb-144">Övervakade filer</span><span class="sxs-lookup"><span data-stu-id="512bb-144">Monitored files</span></span>

<span data-ttu-id="512bb-145">Slutpunkts-DLP:n stöder övervakning av följande filtyper:</span><span class="sxs-lookup"><span data-stu-id="512bb-145">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="512bb-146">Word-filer</span><span class="sxs-lookup"><span data-stu-id="512bb-146">Word files</span></span>
- <span data-ttu-id="512bb-147">PowerPoint-filer</span><span class="sxs-lookup"><span data-stu-id="512bb-147">PowerPoint files</span></span>
- <span data-ttu-id="512bb-148">Excel-filer</span><span class="sxs-lookup"><span data-stu-id="512bb-148">Excel files</span></span>
- <span data-ttu-id="512bb-149">PDF-filer</span><span class="sxs-lookup"><span data-stu-id="512bb-149">PDF files</span></span>
- <span data-ttu-id="512bb-150">.csv-filer</span><span class="sxs-lookup"><span data-stu-id="512bb-150">.csv files</span></span>
- <span data-ttu-id="512bb-151">.tsv-filer</span><span class="sxs-lookup"><span data-stu-id="512bb-151">.tsv files</span></span>
- <span data-ttu-id="512bb-152">.txt-filer</span><span class="sxs-lookup"><span data-stu-id="512bb-152">.txt files</span></span>
- <span data-ttu-id="512bb-153">.rtf-filer</span><span class="sxs-lookup"><span data-stu-id="512bb-153">.rtf files</span></span>
- <span data-ttu-id="512bb-154">.c-filer</span><span class="sxs-lookup"><span data-stu-id="512bb-154">.c files</span></span>
- <span data-ttu-id="512bb-155">.class-filer</span><span class="sxs-lookup"><span data-stu-id="512bb-155">.class files</span></span>
- <span data-ttu-id="512bb-156">.cpp-filer</span><span class="sxs-lookup"><span data-stu-id="512bb-156">.cpp files</span></span>
- <span data-ttu-id="512bb-157">.cs-filer</span><span class="sxs-lookup"><span data-stu-id="512bb-157">.cs files</span></span>
- <span data-ttu-id="512bb-158">.h-filer</span><span class="sxs-lookup"><span data-stu-id="512bb-158">.h files</span></span>
- <span data-ttu-id="512bb-159">.java-filer</span><span class="sxs-lookup"><span data-stu-id="512bb-159">.java files</span></span>
 
<span data-ttu-id="512bb-160">Som standard granskar slutpunkts-DLP:n aktiviteterna för dessa filtyper, även om det inte finns någon principmatchning.</span><span class="sxs-lookup"><span data-stu-id="512bb-160">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="512bb-161">Om du bara vill övervaka data från principmatchningar kan du stänga av **Granska alltid filaktivitet för enheter** i de globala inställningarna för slutpunkts-DLP:n.</span><span class="sxs-lookup"><span data-stu-id="512bb-161">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="512bb-162">Om inställningen är på granskas alltid aktiviteter i Word-, PowerPoint-, Excel-, PDF- och .csv-filer, även om enheten inte omfattas av någon princip.</span><span class="sxs-lookup"><span data-stu-id="512bb-162">If this setting is on, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited even if the device is not targeted by any policy.</span></span>

<span data-ttu-id="512bb-163">Slutpunkts-DLP:n övervakar aktivitet baserat på MIME-typ, så aktiviteterna samlas in även om filtillägget ändras.</span><span class="sxs-lookup"><span data-stu-id="512bb-163">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> 

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="512bb-164">Vad är annorlunda i slutpunkts-DLP?</span><span class="sxs-lookup"><span data-stu-id="512bb-164">What's different in Endpoint DLP</span></span>

<span data-ttu-id="512bb-165">Det finns några fler begrepp som du behöver känna till innan du fördjupar dig i slutpunkts-DLP:n.</span><span class="sxs-lookup"><span data-stu-id="512bb-165">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="512bb-166">Aktivera enhetshantering</span><span class="sxs-lookup"><span data-stu-id="512bb-166">Enabling Device management</span></span>

<span data-ttu-id="512bb-167">Enhetshantering är den funktion som samlar in telemetri från enheter och matar in den i Microsoft 365-efterlevnadslösningar som slutpunkts-DLP och [hantering av interna risker](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="512bb-167">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="512bb-168">Du måste registrera alla enheter som ska användas som platser i DLP-principerna.</span><span class="sxs-lookup"><span data-stu-id="512bb-168">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="512bb-169">![aktivera enhetshantering](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="512bb-169">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="512bb-170">Registrering och avregistrering hanteras via skript som du hämtar från Enhetshanteringscenter.</span><span class="sxs-lookup"><span data-stu-id="512bb-170">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="512bb-171">Centret har anpassade skript för var och en av dessa distributionsmetoder:</span><span class="sxs-lookup"><span data-stu-id="512bb-171">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="512bb-172">lokalt skript (upp till 10 datorer)</span><span class="sxs-lookup"><span data-stu-id="512bb-172">local script (up to 10 machines)</span></span>
- <span data-ttu-id="512bb-173">Grupprincip</span><span class="sxs-lookup"><span data-stu-id="512bb-173">Group policy</span></span>
- <span data-ttu-id="512bb-174">System Center Configuration Manager (version 1610 eller senare)</span><span class="sxs-lookup"><span data-stu-id="512bb-174">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="512bb-175">Hantering av mobila enheter/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="512bb-175">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="512bb-176">VDI-registreringsskript för icke-beständiga datorer</span><span class="sxs-lookup"><span data-stu-id="512bb-176">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="512bb-177">![enhetsregistreringssida](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="512bb-177">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="512bb-178">Använd procedurerna i [Komma igång med slutpunkts-DLP i Microsoft 365](endpoint-dlp-getting-started.md) för att registrera enheter.</span><span class="sxs-lookup"><span data-stu-id="512bb-178">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="512bb-179">Om du har registrerat enheter via [Microsoft Defender för Endpoint](/windows/security/threat-protection/) visas de enheterna automatiskt i listan med enheter.</span><span class="sxs-lookup"><span data-stu-id="512bb-179">If you have onboarded devices through [Microsoft Defender for Endpoint](/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="512bb-180">![lista med hanterade enheter](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="512bb-180">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="512bb-181">Visa data för slutpunkts-DLP</span><span class="sxs-lookup"><span data-stu-id="512bb-181">Viewing Endpoint DLP data</span></span>

<span data-ttu-id="512bb-182">Du kan se aviseringar om DLP-principer som tillämpas på slutpunktsenheter genom att gå till [instrumentpanelen för hantering av DLP-aviseringar](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="512bb-182">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="512bb-183">![Aviseringsinformation](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="512bb-183">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="512bb-184">Du kan också se information om den associerade händelsen med omfattande metadata i samma instrumentpanel</span><span class="sxs-lookup"><span data-stu-id="512bb-184">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="512bb-185">![händelseinformation](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="512bb-185">![event info](../media/Event-info-1.png)</span></span>

<span data-ttu-id="512bb-186">När en enhet har registrerats flödar information om granskade aktiviteter till aktivitetsutforskaren redan innan du har konfigurerat och distribuerat DLP-principer som har enheter som en plats.</span><span class="sxs-lookup"><span data-stu-id="512bb-186">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="512bb-187">![händelser för slutpunkts-DLP i aktivitetsutforskaren](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="512bb-187">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="512bb-188">Slutpunkts-DLP:n samlar in omfattande information om den granskade aktiviteten.</span><span class="sxs-lookup"><span data-stu-id="512bb-188">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="512bb-189">Om en fil till exempel kopieras till ett flyttbart USB-medium visas följande attribut i aktivitetsinformationen:</span><span class="sxs-lookup"><span data-stu-id="512bb-189">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="512bb-190">aktivitetstyp</span><span class="sxs-lookup"><span data-stu-id="512bb-190">activity type</span></span>
- <span data-ttu-id="512bb-191">klient-IP</span><span class="sxs-lookup"><span data-stu-id="512bb-191">client IP</span></span>
- <span data-ttu-id="512bb-192">sökväg till målfil</span><span class="sxs-lookup"><span data-stu-id="512bb-192">target file path</span></span>
- <span data-ttu-id="512bb-193">tidsstämpel</span><span class="sxs-lookup"><span data-stu-id="512bb-193">happened timestamp</span></span>
- <span data-ttu-id="512bb-194">filnamn</span><span class="sxs-lookup"><span data-stu-id="512bb-194">file name</span></span>
- <span data-ttu-id="512bb-195">användare</span><span class="sxs-lookup"><span data-stu-id="512bb-195">user</span></span>
- <span data-ttu-id="512bb-196">filtillägg</span><span class="sxs-lookup"><span data-stu-id="512bb-196">file extension</span></span>
- <span data-ttu-id="512bb-197">filstorlek</span><span class="sxs-lookup"><span data-stu-id="512bb-197">file size</span></span>
- <span data-ttu-id="512bb-198">typ av känslig information (om tillämpligt)</span><span class="sxs-lookup"><span data-stu-id="512bb-198">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="512bb-199">sha1-värde</span><span class="sxs-lookup"><span data-stu-id="512bb-199">sha1 value</span></span>
- <span data-ttu-id="512bb-200">sha256-värde</span><span class="sxs-lookup"><span data-stu-id="512bb-200">sha256 value</span></span>
- <span data-ttu-id="512bb-201">tidigare filnamn</span><span class="sxs-lookup"><span data-stu-id="512bb-201">previous file name</span></span>
- <span data-ttu-id="512bb-202">plats</span><span class="sxs-lookup"><span data-stu-id="512bb-202">location</span></span>
- <span data-ttu-id="512bb-203">överordnad</span><span class="sxs-lookup"><span data-stu-id="512bb-203">parent</span></span>
- <span data-ttu-id="512bb-204">filsökväg</span><span class="sxs-lookup"><span data-stu-id="512bb-204">filepath</span></span>
- <span data-ttu-id="512bb-205">källplatstyp</span><span class="sxs-lookup"><span data-stu-id="512bb-205">source location type</span></span>
- <span data-ttu-id="512bb-206">plattform</span><span class="sxs-lookup"><span data-stu-id="512bb-206">platform</span></span>
- <span data-ttu-id="512bb-207">enhetsnamn</span><span class="sxs-lookup"><span data-stu-id="512bb-207">device name</span></span>
- <span data-ttu-id="512bb-208">målplatstyp</span><span class="sxs-lookup"><span data-stu-id="512bb-208">destination location type</span></span>
- <span data-ttu-id="512bb-209">program som utförde kopian</span><span class="sxs-lookup"><span data-stu-id="512bb-209">application that performed the copy</span></span>
- <span data-ttu-id="512bb-210">Enhets-ID till Microsoft Defender för Endpoint (om tillämpligt)</span><span class="sxs-lookup"><span data-stu-id="512bb-210">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="512bb-211">tillverkare av flyttbar medieenhet</span><span class="sxs-lookup"><span data-stu-id="512bb-211">removable media device manufacturer</span></span>
- <span data-ttu-id="512bb-212">modell för flyttbar medieenhet</span><span class="sxs-lookup"><span data-stu-id="512bb-212">removable media device model</span></span>
- <span data-ttu-id="512bb-213">serienummer för flyttbar medieenhet</span><span class="sxs-lookup"><span data-stu-id="512bb-213">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="512bb-214">![kopiera till USB-aktivitetsattribut](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="512bb-214">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="512bb-215">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="512bb-215">Next steps</span></span>

<span data-ttu-id="512bb-216">Nu när du har lärt dig mer om slutpunkts-DLP är nästa steg:</span><span class="sxs-lookup"><span data-stu-id="512bb-216">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="512bb-217">Komma igång med Microsofts dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="512bb-217">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="512bb-218">Använda Microsofts dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="512bb-218">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="512bb-219">Se även</span><span class="sxs-lookup"><span data-stu-id="512bb-219">See also</span></span>

- [<span data-ttu-id="512bb-220">Komma igång med Microsofts dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="512bb-220">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="512bb-221">Använda Microsofts dataförlustskydd för slutpunkter</span><span class="sxs-lookup"><span data-stu-id="512bb-221">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="512bb-222">Mer information om dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="512bb-222">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="512bb-223">Skapa, testa och justera en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="512bb-223">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="512bb-224">Kom igång med aktivitetsutforskaren</span><span class="sxs-lookup"><span data-stu-id="512bb-224">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="512bb-225">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="512bb-225">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="512bb-226">Hantering av interna risker</span><span class="sxs-lookup"><span data-stu-id="512bb-226">Insider Risk management</span></span>](insider-risk-management.md)