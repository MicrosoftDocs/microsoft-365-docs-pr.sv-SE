---
title: Granska händelser och fel med hjälp av Loggboken
description: Få beskrivningar och ytterligare felsökningssteg (om det behövs) för alla händelser som rapporterats av Microsoft Defender för slutpunktstjänsten.
keywords: felsökning, händelsevisningsprogram, loggsammanfattning, felkod, misslyckades, Microsoft Defender för slutpunktstjänsten, kan inte starta, brytas, kan inte starta
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
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: 1b8454107b6a2737f1236a066c3a24a2b9c776cb
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222663"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="e582e-104">Granska händelser och fel med hjälp av Loggboken</span><span class="sxs-lookup"><span data-stu-id="e582e-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e582e-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e582e-105">**Applies to:**</span></span>
- <span data-ttu-id="e582e-106">Loggboken</span><span class="sxs-lookup"><span data-stu-id="e582e-106">Event Viewer</span></span>
- [<span data-ttu-id="e582e-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="e582e-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="e582e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e582e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e582e-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="e582e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e582e-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="e582e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="e582e-111">Du kan granska händelse-IDt i [Loggboken](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) på enskilda enheter.</span><span class="sxs-lookup"><span data-stu-id="e582e-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="e582e-112">Om enheter inte visas i listan Enheter kan du till exempel behöva leta efter händelse-ID på enheterna.</span><span class="sxs-lookup"><span data-stu-id="e582e-112">For example, if devices aren't appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="e582e-113">Du kan sedan använda tabellen för att fastställa ytterligare felsökningssteg.</span><span class="sxs-lookup"><span data-stu-id="e582e-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="e582e-114">**Öppna Loggboken och hitta Microsoft Defender för slutpunktens händelselogg för tjänsten:**</span><span class="sxs-lookup"><span data-stu-id="e582e-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="e582e-115">Klicka **på Start** på Windows-menyn, skriv **Loggboken** och tryck på **Retur.**</span><span class="sxs-lookup"><span data-stu-id="e582e-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="e582e-116">Bläddra i logglistan under **Loggsammanfattning** tills du ser **Microsoft-Windows-SENSE/Operational**.</span><span class="sxs-lookup"><span data-stu-id="e582e-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="e582e-117">Dubbelklicka på objektet för att öppna loggen.</span><span class="sxs-lookup"><span data-stu-id="e582e-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="e582e-118">a.</span><span class="sxs-lookup"><span data-stu-id="e582e-118">a.</span></span>  <span data-ttu-id="e582e-119">Du kan också öppna loggen genom att expandera **Program och tjänstloggar**  >  **Microsoft**  >  **Windows**  >  **SENSE och** klicka på **Drift.**</span><span class="sxs-lookup"><span data-stu-id="e582e-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e582e-120">SENSE är det interna namn som används för att referera till den beteende sensor som driver Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="e582e-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="e582e-121">Händelser som registreras av tjänsten visas i loggen.</span><span class="sxs-lookup"><span data-stu-id="e582e-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="e582e-122">I följande tabell finns en lista över händelser som registrerats av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="e582e-123">Händelse-ID</span><span class="sxs-lookup"><span data-stu-id="e582e-123">Event ID</span></span></th>
<th><span data-ttu-id="e582e-124">Meddelande</span><span class="sxs-lookup"><span data-stu-id="e582e-124">Message</span></span></th>
<th><span data-ttu-id="e582e-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="e582e-125">Description</span></span></th>
<th><span data-ttu-id="e582e-126">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="e582e-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="e582e-127">1</span><span class="sxs-lookup"><span data-stu-id="e582e-127">1</span></span></td>
<td><span data-ttu-id="e582e-128">Microsoft Defender för slutpunktstjänsten startades (version <code>variable</code> ).</span><span class="sxs-lookup"><span data-stu-id="e582e-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="e582e-129">Inträffar vid start av system, stängs av och under registrering.</span><span class="sxs-lookup"><span data-stu-id="e582e-129">Occurs during system startup, shut down, and during onboarding.</span></span></td>
<td><span data-ttu-id="e582e-130">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-131">2</span><span class="sxs-lookup"><span data-stu-id="e582e-131">2</span></span></td>
<td><span data-ttu-id="e582e-132">Microsoft Defender för Endpoint-tjänsten stängs av.</span><span class="sxs-lookup"><span data-stu-id="e582e-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="e582e-133">Inträffar när enheten stängs av eller stängs av.</span><span class="sxs-lookup"><span data-stu-id="e582e-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="e582e-134">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-135">3</span><span class="sxs-lookup"><span data-stu-id="e582e-135">3</span></span></td>
<td><span data-ttu-id="e582e-136">Microsoft Defender för Slutpunkt-tjänsten kunde inte startas.</span><span class="sxs-lookup"><span data-stu-id="e582e-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="e582e-137">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-138">Tjänsten har inte startar.</span><span class="sxs-lookup"><span data-stu-id="e582e-138">Service didn't start.</span></span></td>
<td><span data-ttu-id="e582e-139">Granska andra meddelanden för att fastställa möjliga orsaker och felsökningssteg.</span><span class="sxs-lookup"><span data-stu-id="e582e-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-140">4</span><span class="sxs-lookup"><span data-stu-id="e582e-140">4</span></span></td>
<td><span data-ttu-id="e582e-141">Microsoft Defender för Slutpunkt-tjänsten kontaktade servern på <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-142">Variabel = URL för Defender för slutpunktsbearbetningsservrar.</span><span class="sxs-lookup"><span data-stu-id="e582e-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="e582e-143">Den här URL:en matchar den som visas i brandväggen eller nätverksaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="e582e-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="e582e-144">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-145">5</span><span class="sxs-lookup"><span data-stu-id="e582e-145">5</span></span></td>
<td><span data-ttu-id="e582e-146">Microsoft Defender för slutpunktstjänsten kunde inte ansluta till servern hos <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-147">Variabel = URL för Defender för slutpunktsbearbetningsservrar.</span><span class="sxs-lookup"><span data-stu-id="e582e-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="e582e-148">Det gick inte att kontakta den externa bearbetningsservrarna på den URL:en.</span><span class="sxs-lookup"><span data-stu-id="e582e-148">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="e582e-149">Kontrollera anslutningen till URL:en.</span><span class="sxs-lookup"><span data-stu-id="e582e-149">Check the connection to the URL.</span></span> <span data-ttu-id="e582e-150">Se <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Konfigurera proxy och Internetanslutning.</a></span><span class="sxs-lookup"><span data-stu-id="e582e-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-151">6</span><span class="sxs-lookup"><span data-stu-id="e582e-151">6</span></span></td>
<td><span data-ttu-id="e582e-152">Microsoft Defender för Slutpunkt-tjänsten är inte onboarded och inga onboarding-parametrar hittades.</span><span class="sxs-lookup"><span data-stu-id="e582e-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="e582e-153">Enheten fungerade inte korrekt och rapporterar inte till portalen.</span><span class="sxs-lookup"><span data-stu-id="e582e-153">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="e582e-154">Onboarding måste köras innan tjänsten startas.</span><span class="sxs-lookup"><span data-stu-id="e582e-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="e582e-155">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="e582e-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e582e-156">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="e582e-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e582e-157">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="e582e-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-158">7</span><span class="sxs-lookup"><span data-stu-id="e582e-158">7</span></span></td>
<td><span data-ttu-id="e582e-159">Microsoft Defender för slutpunktstjänsten kunde inte läsa onboarding-parametrarna.</span><span class="sxs-lookup"><span data-stu-id="e582e-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="e582e-160">Fel: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-161">Variabel = detaljerad felbeskrivning.</span><span class="sxs-lookup"><span data-stu-id="e582e-161">Variable = detailed error description.</span></span> <span data-ttu-id="e582e-162">Enheten fungerade inte korrekt och rapporterar inte till portalen.</span><span class="sxs-lookup"><span data-stu-id="e582e-162">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="e582e-163">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="e582e-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e582e-164">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="e582e-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e582e-165">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="e582e-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-166">8</span><span class="sxs-lookup"><span data-stu-id="e582e-166">8</span></span></td>
<td><span data-ttu-id="e582e-167">Microsoft Defender för slutpunktstjänsten kunde inte rensa konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="e582e-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="e582e-168">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-169"><b>Under introduktionen:</b> Det gick inte att rensa konfigurationen av tjänsten under onboarding.</span><span class="sxs-lookup"><span data-stu-id="e582e-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="e582e-170">Onboarding-processen fortsätter.</span><span class="sxs-lookup"><span data-stu-id="e582e-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="e582e-171"><b>Under offboarding:</b> Tjänsten kunde inte rensa konfigurationen under offboarding.</span><span class="sxs-lookup"><span data-stu-id="e582e-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="e582e-172">Offboarding-processen har slutförts men tjänsten fortsätter att köras.</span><span class="sxs-lookup"><span data-stu-id="e582e-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="e582e-173"><b>Introduktion:</b> Ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="e582e-174"><b>Offboarding:</b> Starta om systemet.</span><span class="sxs-lookup"><span data-stu-id="e582e-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="e582e-175">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="e582e-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-176">9</span><span class="sxs-lookup"><span data-stu-id="e582e-176">9</span></span></td>
<td><span data-ttu-id="e582e-177">Microsoft Defender för slutpunktstjänsten kunde inte ändra starttypen.</span><span class="sxs-lookup"><span data-stu-id="e582e-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="e582e-178">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-179"><b>Under introduktionen:</b> Enheten fungerade inte korrekt och rapporterar inte till portalen.</span><span class="sxs-lookup"><span data-stu-id="e582e-179"><b>During onboarding:</b> The device didn't onboard correctly and won't be reporting to the portal.</span></span> <br><br><span data-ttu-id="e582e-180"><b>Under offboarding:</b> Det gick inte att ändra tjänstens starttyp.</span><span class="sxs-lookup"><span data-stu-id="e582e-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="e582e-181">Offboarding-processen fortsätter.</span><span class="sxs-lookup"><span data-stu-id="e582e-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="e582e-182">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="e582e-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e582e-183">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="e582e-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e582e-184">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="e582e-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-185">10</span><span class="sxs-lookup"><span data-stu-id="e582e-185">10</span></span></td>
<td><span data-ttu-id="e582e-186">Microsoft Defender för slutpunktstjänsten kunde inte spara informationen om introduktionen.</span><span class="sxs-lookup"><span data-stu-id="e582e-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="e582e-187">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-188">Enheten fungerade inte korrekt och rapporterar inte till portalen.</span><span class="sxs-lookup"><span data-stu-id="e582e-188">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="e582e-189">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="e582e-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e582e-190">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="e582e-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e582e-191">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="e582e-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-192">11</span><span class="sxs-lookup"><span data-stu-id="e582e-192">11</span></span></td>
<td><span data-ttu-id="e582e-193">Registrering eller om onboarding av Defender för slutpunktstjänsten har slutförts.</span><span class="sxs-lookup"><span data-stu-id="e582e-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="e582e-194">Enheten var korrekt igång.</span><span class="sxs-lookup"><span data-stu-id="e582e-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="e582e-195">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="e582e-196">Det kan ta flera timmar innan enheten visas i portalen.</span><span class="sxs-lookup"><span data-stu-id="e582e-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-197">12</span><span class="sxs-lookup"><span data-stu-id="e582e-197">12</span></span></td>
<td><span data-ttu-id="e582e-198">Standardkonfigurationen kunde inte användas i Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="e582e-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="e582e-199">Det gick inte att använda standardkonfigurationen för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="e582e-200">Det här felet bör åtgärdas efter en kort tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="e582e-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-201">13</span><span class="sxs-lookup"><span data-stu-id="e582e-201">13</span></span></td>
<td><span data-ttu-id="e582e-202">Microsoft Defender för slutpunktens enhets-ID beräknat: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-203">Normal driftprocess.</span><span class="sxs-lookup"><span data-stu-id="e582e-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="e582e-204">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-205">15</span><span class="sxs-lookup"><span data-stu-id="e582e-205">15</span></span></td>
<td><span data-ttu-id="e582e-206">Microsoft Defender för Slutpunkt kan inte starta kommandokanalen med URL: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-207">Variabel = URL för Defender för slutpunktsbearbetningsservrar.</span><span class="sxs-lookup"><span data-stu-id="e582e-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="e582e-208">Det gick inte att kontakta den externa bearbetningsservrarna på den URL:en.</span><span class="sxs-lookup"><span data-stu-id="e582e-208">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="e582e-209">Kontrollera anslutningen till URL:en.</span><span class="sxs-lookup"><span data-stu-id="e582e-209">Check the connection to the URL.</span></span> <span data-ttu-id="e582e-210">Se <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Konfigurera proxy och Internetanslutning.</a></span><span class="sxs-lookup"><span data-stu-id="e582e-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-211">17</span><span class="sxs-lookup"><span data-stu-id="e582e-211">17</span></span></td>
<td><span data-ttu-id="e582e-212">Microsoft Defender för slutpunktstjänsten kunde inte ändra plats för anslutna användarupplevelser och telemetritjänster.</span><span class="sxs-lookup"><span data-stu-id="e582e-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="e582e-213">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-214">Ett fel uppstod med Windows-telemetritjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="e582e-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Kontrollera att diagnostikdatatjänsten är aktiverad.</a></span><span class="sxs-lookup"><span data-stu-id="e582e-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="e582e-216">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="e582e-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e582e-217">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="e582e-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e582e-218">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="e582e-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-219">18</span><span class="sxs-lookup"><span data-stu-id="e582e-219">18</span></span></td>
<td><span data-ttu-id="e582e-220">OOBE (Välkommen i Windows) har slutförts.</span><span class="sxs-lookup"><span data-stu-id="e582e-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="e582e-221">Tjänsten startar först när Windows-uppdateringarna har installerats.</span><span class="sxs-lookup"><span data-stu-id="e582e-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="e582e-222">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-223">19</span><span class="sxs-lookup"><span data-stu-id="e582e-223">19</span></span></td>
<td><span data-ttu-id="e582e-224">OOBE (Välkommen i Windows) har ännu inte slutförts.</span><span class="sxs-lookup"><span data-stu-id="e582e-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="e582e-225">Tjänsten startar först när Windows-uppdateringarna har installerats.</span><span class="sxs-lookup"><span data-stu-id="e582e-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="e582e-226">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="e582e-227">Om det här felet kvarstår efter en omstart av systemet bör du kontrollera att alla Windows-uppdateringar har installerats.</span><span class="sxs-lookup"><span data-stu-id="e582e-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-228">20</span><span class="sxs-lookup"><span data-stu-id="e582e-228">20</span></span></td>
<td><span data-ttu-id="e582e-229">Det går inte att vänta på att OOBE (Välkommen i Windows) ska slutföras.</span><span class="sxs-lookup"><span data-stu-id="e582e-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="e582e-230">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-231">Internt fel.</span><span class="sxs-lookup"><span data-stu-id="e582e-231">Internal error.</span></span></td>
<td><span data-ttu-id="e582e-232">Om det här felet kvarstår efter en omstart av systemet bör du kontrollera att alla Windows-uppdateringar har installerats.</span><span class="sxs-lookup"><span data-stu-id="e582e-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-233">25</span><span class="sxs-lookup"><span data-stu-id="e582e-233">25</span></span></td>
<td><span data-ttu-id="e582e-234">Microsoft Defender för Slutpunkt-tjänsten kunde inte återställa hälsostatus i registret.</span><span class="sxs-lookup"><span data-stu-id="e582e-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="e582e-235">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-236">Enheten fungerade inte korrekt.</span><span class="sxs-lookup"><span data-stu-id="e582e-236">The device didn't onboard correctly.</span></span>
<span data-ttu-id="e582e-237">Den rapporterar till portalen, men tjänsten kanske inte visas som registrerad i SCCM eller registret.</span><span class="sxs-lookup"><span data-stu-id="e582e-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="e582e-238">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="e582e-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e582e-239">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="e582e-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e582e-240">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="e582e-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-241">26</span><span class="sxs-lookup"><span data-stu-id="e582e-241">26</span></span></td>
<td><span data-ttu-id="e582e-242">Microsoft Defender för slutpunktstjänsten kunde inte ange registreringsstatus i registret.</span><span class="sxs-lookup"><span data-stu-id="e582e-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="e582e-243">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-244">Enheten fungerade inte korrekt.</span><span class="sxs-lookup"><span data-stu-id="e582e-244">The device didn't onboard correctly.</span></span><br>
<span data-ttu-id="e582e-245">Den rapporterar till portalen, men tjänsten kanske inte visas som registrerad i SCCM eller registret.</span><span class="sxs-lookup"><span data-stu-id="e582e-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="e582e-246">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="e582e-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e582e-247">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="e582e-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e582e-248">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="e582e-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-249">27</span><span class="sxs-lookup"><span data-stu-id="e582e-249">27</span></span></td>
<td><span data-ttu-id="e582e-250">Microsoft Defender för slutpunktstjänsten kunde inte aktivera SENSE-läge i Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="e582e-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="e582e-251">Onboarding-processen misslyckades.</span><span class="sxs-lookup"><span data-stu-id="e582e-251">Onboarding process failed.</span></span> <span data-ttu-id="e582e-252">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-253">Normalt inger Microsoft Defender Antivirus ett särskilt passivt läge om en annan antimalwareprodukt i realtid körs korrekt på enheten och enheten rapporterar till Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="e582e-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="e582e-254">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="e582e-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e582e-255">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="e582e-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e582e-256">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="e582e-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="e582e-257">Se till att skydd mot skadlig programvara i realtid fungerar som det ska.</span><span class="sxs-lookup"><span data-stu-id="e582e-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-258">28</span><span class="sxs-lookup"><span data-stu-id="e582e-258">28</span></span></td>
<td><span data-ttu-id="e582e-259">Microsoft Defender för slutpunktsanslutna användarupplevelser och registrering av telemetritjänster misslyckades.</span><span class="sxs-lookup"><span data-stu-id="e582e-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="e582e-260">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-261">Ett fel uppstod med Windows-telemetritjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="e582e-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Kontrollera att diagnostikdatatjänsten är aktiverad.</a></span><span class="sxs-lookup"><span data-stu-id="e582e-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="e582e-263">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="e582e-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e582e-264">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="e582e-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e582e-265">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="e582e-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-266">29</span><span class="sxs-lookup"><span data-stu-id="e582e-266">29</span></span></td>
<td><span data-ttu-id="e582e-267">Det gick inte att läsa parametrarna för offboarding.</span><span class="sxs-lookup"><span data-stu-id="e582e-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="e582e-268">Feltyp: %1, Felkod: %2, Beskrivning: %3</span><span class="sxs-lookup"><span data-stu-id="e582e-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="e582e-269">Händelsen inträffar när systemet inte&#39;av parametrarna för offboarding.</span><span class="sxs-lookup"><span data-stu-id="e582e-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="e582e-270">Kontrollera att enheten har internetanslutning och kör sedan hela offboardingprocessen igen.</span><span class="sxs-lookup"><span data-stu-id="e582e-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="e582e-271">Kontrollera att offboarding-paketet inte har gått ut.</span><span class="sxs-lookup"><span data-stu-id="e582e-271">Ensure the offboarding package hasn't expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-272">30</span><span class="sxs-lookup"><span data-stu-id="e582e-272">30</span></span></td>
<td><span data-ttu-id="e582e-273">Microsoft Defender för slutpunktstjänsten kunde inte inaktivera SENSE-läge i Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="e582e-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="e582e-274">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-275">Normalt inger Microsoft Defender Antivirus ett särskilt passivt läge om en annan antimalwareprodukt i realtid körs korrekt på enheten och enheten rapporterar till Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="e582e-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="e582e-276">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="e582e-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e582e-277">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="e582e-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e582e-278">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter</a></span><span class="sxs-lookup"><span data-stu-id="e582e-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="e582e-279">Se till att skydd mot skadlig programvara i realtid fungerar som det ska.</span><span class="sxs-lookup"><span data-stu-id="e582e-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-280">31</span><span class="sxs-lookup"><span data-stu-id="e582e-280">31</span></span></td>
<td><span data-ttu-id="e582e-281">Microsoft Defender för slutpunktsanslutna användarupplevelser och avregistrering av telemetritjänsten misslyckades.</span><span class="sxs-lookup"><span data-stu-id="e582e-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="e582e-282">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-283">Ett fel uppstod med Windows-telemetritjänsten under onboarding.</span><span class="sxs-lookup"><span data-stu-id="e582e-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="e582e-284">Offboarding-processen fortsätter.</span><span class="sxs-lookup"><span data-stu-id="e582e-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="e582e-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Sök efter fel med Windows-telemetritjänsten</a>.</span><span class="sxs-lookup"><span data-stu-id="e582e-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-286">32</span><span class="sxs-lookup"><span data-stu-id="e582e-286">32</span></span></td>
<td><span data-ttu-id="e582e-287">Microsoft Defender för slutpunktstjänsten kunde inte begära att stoppa sig själv efter offboardingprocessen.</span><span class="sxs-lookup"><span data-stu-id="e582e-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="e582e-288">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="e582e-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="e582e-289">Ett fel uppstod vid offboarding.</span><span class="sxs-lookup"><span data-stu-id="e582e-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="e582e-290">Starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="e582e-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-291">33</span><span class="sxs-lookup"><span data-stu-id="e582e-291">33</span></span></td>
<td><span data-ttu-id="e582e-292">Microsoft Defender för slutpunktstjänsten kunde inte spara SENSE GUID.</span><span class="sxs-lookup"><span data-stu-id="e582e-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="e582e-293">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-294">En unik identifierare används för att representera varje enhet som rapporterar till portalen.</span><span class="sxs-lookup"><span data-stu-id="e582e-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="e582e-295">Om identifieraren inte finns kvar kan samma enhet visas två gånger i portalen.</span><span class="sxs-lookup"><span data-stu-id="e582e-295">If the identifier doesn't persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="e582e-296">Kontrollera registerbehörigheter på enheten för att säkerställa att tjänsten kan uppdatera registret.</span><span class="sxs-lookup"><span data-stu-id="e582e-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-297">34</span><span class="sxs-lookup"><span data-stu-id="e582e-297">34</span></span></td>
<td><span data-ttu-id="e582e-298">Microsoft Defender för Slutpunkt-tjänsten kunde inte lägga till sig själv som ett beroende av den anslutna användarupplevelsen och telemetritjänsten, vilket ledde till att onboarding-processen misslyckades.</span><span class="sxs-lookup"><span data-stu-id="e582e-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="e582e-299">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-300">Ett fel uppstod med Windows-telemetritjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="e582e-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Kontrollera att diagnostikdatatjänsten är aktiverad.</a></span><span class="sxs-lookup"><span data-stu-id="e582e-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="e582e-302">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="e582e-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e582e-303">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="e582e-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e582e-304">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="e582e-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-305">35</span><span class="sxs-lookup"><span data-stu-id="e582e-305">35</span></span></td>
<td><span data-ttu-id="e582e-306">Microsoft Defender för slutpunktstjänsten kunde inte ta bort sig själv som ett beroende av den anslutna användarupplevelsen och telemetritjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="e582e-307">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-308">Ett fel uppstod med Windows-telemetritjänsten under offboarding.</span><span class="sxs-lookup"><span data-stu-id="e582e-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="e582e-309">Offboarding-processen fortsätter.</span><span class="sxs-lookup"><span data-stu-id="e582e-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="e582e-310">Sök efter fel med Windows-diagnostikdatatjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-311">36</span><span class="sxs-lookup"><span data-stu-id="e582e-311">36</span></span></td>
<td><span data-ttu-id="e582e-312">Microsoft Defender för slutpunktsanslutna användarupplevelser och telemetritjänstregistrering lyckades.</span><span class="sxs-lookup"><span data-stu-id="e582e-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="e582e-313">Slutförandekod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e582e-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e582e-314">Registrering av Defender för slutpunkt med den anslutna användarupplevelsen och telemetritjänsten har slutförts.</span><span class="sxs-lookup"><span data-stu-id="e582e-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="e582e-315">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-316">37</span><span class="sxs-lookup"><span data-stu-id="e582e-316">37</span></span></td>
<td><span data-ttu-id="e582e-317">Microsoft Defender för slutpunkt En modul kommer att överskrida sin kvot.</span><span class="sxs-lookup"><span data-stu-id="e582e-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="e582e-318">Modul: %1, Kvot: {%2} {%3}, Procentandel av kvotens användning: %4.</span><span class="sxs-lookup"><span data-stu-id="e582e-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="e582e-319">Enheten har nästan använt sin tilldelade kvot under det aktuella 24-timmarsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e582e-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="e582e-320">Den kommer att begränsas.</span><span class="sxs-lookup"><span data-stu-id="e582e-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="e582e-321">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-322">38</span><span class="sxs-lookup"><span data-stu-id="e582e-322">38</span></span></td>
<td><span data-ttu-id="e582e-323">Nätverksanslutningen identifieras som låg.</span><span class="sxs-lookup"><span data-stu-id="e582e-323">Network connection is identified as low.</span></span> <span data-ttu-id="e582e-324">Microsoft Defender för Endpoint kontaktar servern var %1:e minut.</span><span class="sxs-lookup"><span data-stu-id="e582e-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="e582e-325">Anslutning med datatrafik: %2, internet tillgängligt: %3, kostnadsfritt nätverk tillgängligt: %4.</span><span class="sxs-lookup"><span data-stu-id="e582e-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="e582e-326">Enheten använder ett nätverk med datatrafik/betalt nätverk och kontaktar servern mer sällan.</span><span class="sxs-lookup"><span data-stu-id="e582e-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="e582e-327">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-328">39</span><span class="sxs-lookup"><span data-stu-id="e582e-328">39</span></span></td>
<td><span data-ttu-id="e582e-329">Nätverksanslutningen identifieras som normal.</span><span class="sxs-lookup"><span data-stu-id="e582e-329">Network connection is identified as normal.</span></span> <span data-ttu-id="e582e-330">Microsoft Defender för Endpoint kontaktar servern var %1:e minut.</span><span class="sxs-lookup"><span data-stu-id="e582e-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="e582e-331">Anslutning med datatrafik: %2, internet tillgängligt: %3, kostnadsfritt nätverk tillgängligt: %4.</span><span class="sxs-lookup"><span data-stu-id="e582e-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="e582e-332">Enheten använder inte en anslutning med databetalda data och kontaktar servern som vanligt.</span><span class="sxs-lookup"><span data-stu-id="e582e-332">The device isn't using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="e582e-333">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-334">40</span><span class="sxs-lookup"><span data-stu-id="e582e-334">40</span></span></td>
<td><span data-ttu-id="e582e-335">Batteritillståndet identifieras som låg.</span><span class="sxs-lookup"><span data-stu-id="e582e-335">Battery state is identified as low.</span></span> <span data-ttu-id="e582e-336">Microsoft Defender för Endpoint kontaktar servern var %1:e minut.</span><span class="sxs-lookup"><span data-stu-id="e582e-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="e582e-337">Batteritillstånd: %2.</span><span class="sxs-lookup"><span data-stu-id="e582e-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="e582e-338">Enheten har låg batterinivå och kontaktar servern mindre ofta.</span><span class="sxs-lookup"><span data-stu-id="e582e-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="e582e-339">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-340">41</span><span class="sxs-lookup"><span data-stu-id="e582e-340">41</span></span></td>
<td><span data-ttu-id="e582e-341">Batteritillståndet identifieras som normalt.</span><span class="sxs-lookup"><span data-stu-id="e582e-341">Battery state is identified as normal.</span></span> <span data-ttu-id="e582e-342">Microsoft Defender för Endpoint kontaktar servern var %1:e minut.</span><span class="sxs-lookup"><span data-stu-id="e582e-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="e582e-343">Batteritillstånd: %2.</span><span class="sxs-lookup"><span data-stu-id="e582e-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="e582e-344">Enheten har inte låg batterinivå och kontaktar servern som vanligt.</span><span class="sxs-lookup"><span data-stu-id="e582e-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="e582e-345">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-346">42</span><span class="sxs-lookup"><span data-stu-id="e582e-346">42</span></span></td>
<td><span data-ttu-id="e582e-347">Microsoft Defender för Slutpunkt WDATP-komponent kunde inte utföra någon åtgärd.</span><span class="sxs-lookup"><span data-stu-id="e582e-347">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="e582e-348">Komponent: %1, Åtgärd: %2, Undantagstyp: %3, Undantagsmeddelande: %4</span><span class="sxs-lookup"><span data-stu-id="e582e-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="e582e-349">Internt fel.</span><span class="sxs-lookup"><span data-stu-id="e582e-349">Internal error.</span></span> <span data-ttu-id="e582e-350">Det gick inte att starta tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="e582e-351">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="e582e-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-352">43</span><span class="sxs-lookup"><span data-stu-id="e582e-352">43</span></span></td>
<td><span data-ttu-id="e582e-353">Microsoft Defender för Slutpunkt WDATP-komponent kunde inte utföra någon åtgärd.</span><span class="sxs-lookup"><span data-stu-id="e582e-353">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="e582e-354">Komponent: %1, Åtgärd: %2, Undantagstyp: %3, Undantagsfel: %4, Undantagsmeddelande: %5</span><span class="sxs-lookup"><span data-stu-id="e582e-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="e582e-355">Internt fel.</span><span class="sxs-lookup"><span data-stu-id="e582e-355">Internal error.</span></span> <span data-ttu-id="e582e-356">Det gick inte att starta tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="e582e-357">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="e582e-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-358">44</span><span class="sxs-lookup"><span data-stu-id="e582e-358">44</span></span></td>
<td><span data-ttu-id="e582e-359">Offboarding av Defender för slutpunktstjänsten har slutförts.</span><span class="sxs-lookup"><span data-stu-id="e582e-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="e582e-360">Tjänsten var offboarded.</span><span class="sxs-lookup"><span data-stu-id="e582e-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="e582e-361">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-362">45</span><span class="sxs-lookup"><span data-stu-id="e582e-362">45</span></span></td>
<td><span data-ttu-id="e582e-363">Det gick inte att registrera och starta händelsespårningssessionen [%1].</span><span class="sxs-lookup"><span data-stu-id="e582e-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="e582e-364">Felkod: %2</span><span class="sxs-lookup"><span data-stu-id="e582e-364">Error code: %2</span></span></td>
<td><span data-ttu-id="e582e-365">Ett fel uppstod vid start av tjänsten vid skapandet av ETW-session.</span><span class="sxs-lookup"><span data-stu-id="e582e-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="e582e-366">Detta orsakade startfel för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="e582e-367">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="e582e-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-368">46</span><span class="sxs-lookup"><span data-stu-id="e582e-368">46</span></span></td>
<td><span data-ttu-id="e582e-369">Det gick inte att registrera och starta händelsespårningssessionen [%1] på grund av brist på resurser.</span><span class="sxs-lookup"><span data-stu-id="e582e-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="e582e-370">Felkod: %2.</span><span class="sxs-lookup"><span data-stu-id="e582e-370">Error code: %2.</span></span> <span data-ttu-id="e582e-371">Det beror troligen på att det finns för många sessioner med aktiva händelsespårningar.</span><span class="sxs-lookup"><span data-stu-id="e582e-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="e582e-372">Tjänsten kommer att försöka igen om 1 minut.</span><span class="sxs-lookup"><span data-stu-id="e582e-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="e582e-373">Ett fel uppstod vid start av tjänsten när ETW-sessionen skulle skapas på grund av brist på resurser.</span><span class="sxs-lookup"><span data-stu-id="e582e-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="e582e-374">Tjänsten startades och körs, men rapporterar inte en sensorhändelse förrän ETW-sessionen startas.</span><span class="sxs-lookup"><span data-stu-id="e582e-374">The service started and is running, but won't report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="e582e-375">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="e582e-376">Tjänsten försöker starta sessionen varje minut.</span><span class="sxs-lookup"><span data-stu-id="e582e-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-377">47</span><span class="sxs-lookup"><span data-stu-id="e582e-377">47</span></span></td>
<td><span data-ttu-id="e582e-378">Registrerad och startade händelsespårningssessionen – återställdes efter tidigare misslyckade försök.</span><span class="sxs-lookup"><span data-stu-id="e582e-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="e582e-379">Händelsen följer den föregående händelsen efter att ETW-sessionen har startar.</span><span class="sxs-lookup"><span data-stu-id="e582e-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="e582e-380">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e582e-381">48</span><span class="sxs-lookup"><span data-stu-id="e582e-381">48</span></span></td>
<td><span data-ttu-id="e582e-382">Det gick inte att lägga till en provider [%1] i händelsespårningssession [%2].</span><span class="sxs-lookup"><span data-stu-id="e582e-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="e582e-383">Felkod: %3.</span><span class="sxs-lookup"><span data-stu-id="e582e-383">Error code: %3.</span></span> <span data-ttu-id="e582e-384">Det innebär att händelser från den här leverantören inte rapporteras.</span><span class="sxs-lookup"><span data-stu-id="e582e-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="e582e-385">Det gick inte att lägga till en leverantör i ETW-sessionen.</span><span class="sxs-lookup"><span data-stu-id="e582e-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="e582e-386">Därför rapporteras inte leverantörshändelserna.</span><span class="sxs-lookup"><span data-stu-id="e582e-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="e582e-387">Kontrollera felkoden.</span><span class="sxs-lookup"><span data-stu-id="e582e-387">Check the error code.</span></span> <span data-ttu-id="e582e-388">Kontakta support om felet kvarstår.</span><span class="sxs-lookup"><span data-stu-id="e582e-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
<tr>
   <td><span data-ttu-id="e582e-389">49</span><span class="sxs-lookup"><span data-stu-id="e582e-389">49</span></span></td>
   <td><span data-ttu-id="e582e-390">Kommandot ogiltig molnkonfiguration har tagits emot och ignorerats.</span><span class="sxs-lookup"><span data-stu-id="e582e-390">Invalid cloud configuration command received and ignored.</span></span> <span data-ttu-id="e582e-391">Version: %1, status: %2, felkod: %3, meddelande: %4</span><span class="sxs-lookup"><span data-stu-id="e582e-391">Version: %1, status: %2, error code: %3, message: %4</span></span></td>
   <td><span data-ttu-id="e582e-392">Fick en ogiltig konfigurationsfil från molntjänsten som ignorerades.</span><span class="sxs-lookup"><span data-stu-id="e582e-392">Received an invalid configuration file from the cloud service that was ignored.</span></span></td>
   <td><span data-ttu-id="e582e-393">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="e582e-393">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-394">50</span><span class="sxs-lookup"><span data-stu-id="e582e-394">50</span></span></td>
   <td><span data-ttu-id="e582e-395">Den nya molnkonfigurationen har använts.</span><span class="sxs-lookup"><span data-stu-id="e582e-395">New cloud configuration applied successfully.</span></span> <span data-ttu-id="e582e-396">Version: %1.</span><span class="sxs-lookup"><span data-stu-id="e582e-396">Version: %1.</span></span></td>
   <td><span data-ttu-id="e582e-397">En ny konfiguration från molntjänsten har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="e582e-397">Successfully applied a new configuration from the cloud service.</span></span></td>
   <td><span data-ttu-id="e582e-398">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-398">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-399">51</span><span class="sxs-lookup"><span data-stu-id="e582e-399">51</span></span></td>
   <td><span data-ttu-id="e582e-400">Ny molnkonfiguration kunde inte användas, version: %1.</span><span class="sxs-lookup"><span data-stu-id="e582e-400">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="e582e-401">Den senaste kända konfigurationen, version %2, har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="e582e-401">Successfully applied the last known good configuration, version %2.</span></span></td>
   <td><span data-ttu-id="e582e-402">Fick en felaktig konfigurationsfil från molntjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-402">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="e582e-403">Den senaste kända konfigurationen har använts.</span><span class="sxs-lookup"><span data-stu-id="e582e-403">Last known good configuration was applied successfully.</span></span></td>
   <td><span data-ttu-id="e582e-404">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="e582e-404">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-405">52</span><span class="sxs-lookup"><span data-stu-id="e582e-405">52</span></span></td>
   <td><span data-ttu-id="e582e-406">Ny molnkonfiguration kunde inte användas, version: %1.</span><span class="sxs-lookup"><span data-stu-id="e582e-406">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="e582e-407">Det gick inte heller att använda den senaste kända konfigurationen, version %2.</span><span class="sxs-lookup"><span data-stu-id="e582e-407">Also failed to apply last known good configuration, version %2.</span></span> <span data-ttu-id="e582e-408">Standardkonfigurationen har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="e582e-408">Successfully applied the default configuration.</span></span></td>
   <td><span data-ttu-id="e582e-409">Fick en felaktig konfigurationsfil från molntjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-409">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="e582e-410">Det gick inte att använda den senaste kända konfigurationen – och standardkonfigurationen tillämpades.</span><span class="sxs-lookup"><span data-stu-id="e582e-410">Failed to apply the last known good configuration - and the default configuration was applied.</span></span></td>
   <td><span data-ttu-id="e582e-411">Tjänsten försöker ladda ned en ny konfigurationsfil inom 5 minuter.</span><span class="sxs-lookup"><span data-stu-id="e582e-411">The service will attempt to download a new configuration file within 5 minutes.</span></span> <span data-ttu-id="e582e-412">Om du inte ser händelsen #50 kontakta support.</span><span class="sxs-lookup"><span data-stu-id="e582e-412">If you don't see event #50 - contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-413">53</span><span class="sxs-lookup"><span data-stu-id="e582e-413">53</span></span></td>
   <td><span data-ttu-id="e582e-414">Molnkonfiguration som lästs in från beständig lagring, version: %1.</span><span class="sxs-lookup"><span data-stu-id="e582e-414">Cloud configuration loaded from persistent storage, version: %1.</span></span></td>
   <td><span data-ttu-id="e582e-415">Konfigurationen startades från beständig lagring vid start av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-415">The configuration was loaded from persistent storage on service startup.</span></span></td>
   <td><span data-ttu-id="e582e-416">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-416">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-417">55</span><span class="sxs-lookup"><span data-stu-id="e582e-417">55</span></span></td>
   <td><span data-ttu-id="e582e-418">Det gick inte att skapa automatisk ETW-loggare för säker ETW.</span><span class="sxs-lookup"><span data-stu-id="e582e-418">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="e582e-419">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="e582e-419">Failure code: %1</span></span></td>
   <td><span data-ttu-id="e582e-420">Det gick inte att skapa den säkra ETW-loggern.</span><span class="sxs-lookup"><span data-stu-id="e582e-420">Failed to create the secure ETW logger.</span></span></td>
   <td><span data-ttu-id="e582e-421">Starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="e582e-421">Reboot the device.</span></span> <span data-ttu-id="e582e-422">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="e582e-422">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-423">56</span><span class="sxs-lookup"><span data-stu-id="e582e-423">56</span></span></td>
   <td><span data-ttu-id="e582e-424">Det gick inte att ta bort automatisk loggare för Secure ETW.</span><span class="sxs-lookup"><span data-stu-id="e582e-424">Failed to remove the Secure ETW autologger.</span></span> <span data-ttu-id="e582e-425">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="e582e-425">Failure code: %1</span></span></td>
   <td><span data-ttu-id="e582e-426">Det gick inte att ta bort den säkra ETW-sessionen på offboarding.</span><span class="sxs-lookup"><span data-stu-id="e582e-426">Failed to remove the secure ETW session on offboarding.</span></span></td>
   <td><span data-ttu-id="e582e-427">Kontakta support.</span><span class="sxs-lookup"><span data-stu-id="e582e-427">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-428">57</span><span class="sxs-lookup"><span data-stu-id="e582e-428">57</span></span></td>
   <td><span data-ttu-id="e582e-429">Fånga en ögonblicksbild av datorn i felsökningssyfte.</span><span class="sxs-lookup"><span data-stu-id="e582e-429">Capturing a snapshot of the machine for troubleshooting purposes.</span></span></td>
   <td><span data-ttu-id="e582e-430">Ett undersökningspaket, även kallat en forensisk paket, samlas in.</span><span class="sxs-lookup"><span data-stu-id="e582e-430">An investigation package, also known as forensics package, is being collected.</span></span></td>
   <td><span data-ttu-id="e582e-431">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-431">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-432">59</span><span class="sxs-lookup"><span data-stu-id="e582e-432">59</span></span></td>
   <td><span data-ttu-id="e582e-433">Startkommando: %1</span><span class="sxs-lookup"><span data-stu-id="e582e-433">Starting command: %1</span></span></td>
   <td><span data-ttu-id="e582e-434">Kommandot Startar svarskörning.</span><span class="sxs-lookup"><span data-stu-id="e582e-434">Starting response command execution.</span></span></td>
   <td><span data-ttu-id="e582e-435">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-435">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-436">60</span><span class="sxs-lookup"><span data-stu-id="e582e-436">60</span></span></td>
   <td><span data-ttu-id="e582e-437">Det gick inte att köra kommandot %1, fel: %2.</span><span class="sxs-lookup"><span data-stu-id="e582e-437">Failed to run command %1, error: %2.</span></span></td>
   <td><span data-ttu-id="e582e-438">Det gick inte att köra svarskommandot.</span><span class="sxs-lookup"><span data-stu-id="e582e-438">Failed to execute response command.</span></span></td>
   <td><span data-ttu-id="e582e-439">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="e582e-439">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-440">61</span><span class="sxs-lookup"><span data-stu-id="e582e-440">61</span></span></td>
   <td><span data-ttu-id="e582e-441">Parametrar för datainsamlingskommandon är ogiltiga: SasUri: %1, compressionLevel: %2.</span><span class="sxs-lookup"><span data-stu-id="e582e-441">Data collection command parameters are invalid: SasUri: %1, compressionLevel: %2.</span></span></td>
   <td><span data-ttu-id="e582e-442">Det gick inte att läsa eller tolka kommandoargumenten för datainsamling (ogiltiga argument).</span><span class="sxs-lookup"><span data-stu-id="e582e-442">Failed to read or parse the data collection command arguments (invalid arguments).</span></span></td>
   <td><span data-ttu-id="e582e-443">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="e582e-443">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-444">62</span><span class="sxs-lookup"><span data-stu-id="e582e-444">62</span></span></td>
   <td><span data-ttu-id="e582e-445">Det gick inte att starta den anslutna användarupplevelsen och telemetritjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-445">Failed to start Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="e582e-446">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="e582e-446">Failure code: %1</span></span></td>
   <td><span data-ttu-id="e582e-447">Anslutna användarupplevelser och den telemetriska tjänsten (diagtrack) kunde inte startas.</span><span class="sxs-lookup"><span data-stu-id="e582e-447">Connected User Experiences and Telemetry (diagtrack) service failed to start.</span></span> <span data-ttu-id="e582e-448">Telemetri med andra än Microsoft Defender för Slutpunkt-telemetri skickas inte från den här datorn.</span><span class="sxs-lookup"><span data-stu-id="e582e-448">Non-Microsoft Defender for Endpoint telemetry won't be sent from this machine.</span></span></td>
   <td><span data-ttu-id="e582e-449">Leta efter fler felsökningstips i händelseloggen: Microsoft-Windows-UniversalTelemetryClient/Operational.</span><span class="sxs-lookup"><span data-stu-id="e582e-449">Look for more troubleshooting hints in the event log: Microsoft-Windows-UniversalTelemetryClient/Operational.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-450">63</span><span class="sxs-lookup"><span data-stu-id="e582e-450">63</span></span></td>
   <td><span data-ttu-id="e582e-451">Uppdatera starttypen för extern tjänst.</span><span class="sxs-lookup"><span data-stu-id="e582e-451">Updating the start type of external service.</span></span> <span data-ttu-id="e582e-452">Namn: %1, verklig starttyp: %2, förväntad starttyp: %3, utgångskod: %4</span><span class="sxs-lookup"><span data-stu-id="e582e-452">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="e582e-453">Den externa tjänstens starttyp har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="e582e-453">Updated start type of the external service.</span></span></td>
   <td><span data-ttu-id="e582e-454">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-454">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-455">64</span><span class="sxs-lookup"><span data-stu-id="e582e-455">64</span></span></td>
   <td><span data-ttu-id="e582e-456">Starta den externa tjänsten som stoppas.</span><span class="sxs-lookup"><span data-stu-id="e582e-456">Starting stopped external service.</span></span> <span data-ttu-id="e582e-457">Namn: %1, utgångskod: %2</span><span class="sxs-lookup"><span data-stu-id="e582e-457">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="e582e-458">Starta en extern tjänst.</span><span class="sxs-lookup"><span data-stu-id="e582e-458">Starting an external service.</span></span></td>
   <td><span data-ttu-id="e582e-459">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-459">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-460">65</span><span class="sxs-lookup"><span data-stu-id="e582e-460">65</span></span></td>
   <td><span data-ttu-id="e582e-461">Det gick inte att läsa in minifilterdrivrutinen Microsoft Security Events Component.</span><span class="sxs-lookup"><span data-stu-id="e582e-461">Failed to load Microsoft Security Events Component Minifilter driver.</span></span> <span data-ttu-id="e582e-462">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="e582e-462">Failure code: %1</span></span></td>
   <td><span data-ttu-id="e582e-463">Det gick inte att MsSecFlt.sys av filsystems minifilter.</span><span class="sxs-lookup"><span data-stu-id="e582e-463">Failed to load MsSecFlt.sys filesystem minifilter.</span></span></td>
   <td><span data-ttu-id="e582e-464">Starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="e582e-464">Reboot the device.</span></span> <span data-ttu-id="e582e-465">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="e582e-465">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-466">66</span><span class="sxs-lookup"><span data-stu-id="e582e-466">66</span></span></td>
   <td><span data-ttu-id="e582e-467">Principuppdatering: Svarstidsläge – %1</span><span class="sxs-lookup"><span data-stu-id="e582e-467">Policy update: Latency mode - %1</span></span></td>
   <td><span data-ttu-id="e582e-468">Principen för&C-anslutningsfrekvensen uppdaterades.</span><span class="sxs-lookup"><span data-stu-id="e582e-468">The C&C connection frequency policy was updated.</span></span></td>
   <td><span data-ttu-id="e582e-469">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-469">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-470">68</span><span class="sxs-lookup"><span data-stu-id="e582e-470">68</span></span></td>
   <td><span data-ttu-id="e582e-471">Tjänstens starttyp är oväntad.</span><span class="sxs-lookup"><span data-stu-id="e582e-471">The start type of the service is unexpected.</span></span> <span data-ttu-id="e582e-472">Tjänstnamn: %1, verklig starttyp: %2, förväntad starttyp: %3</span><span class="sxs-lookup"><span data-stu-id="e582e-472">Service name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="e582e-473">Oväntad extern tjänststartstyp.</span><span class="sxs-lookup"><span data-stu-id="e582e-473">Unexpected external service start type.</span></span></td>
   <td><span data-ttu-id="e582e-474">Åtgärda den externa tjänstens starttyp.</span><span class="sxs-lookup"><span data-stu-id="e582e-474">Fix the external service start type.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-475">69</span><span class="sxs-lookup"><span data-stu-id="e582e-475">69</span></span></td>
   <td><span data-ttu-id="e582e-476">Tjänsten stoppas.</span><span class="sxs-lookup"><span data-stu-id="e582e-476">The service is stopped.</span></span> <span data-ttu-id="e582e-477">Tjänstnamn: %1</span><span class="sxs-lookup"><span data-stu-id="e582e-477">Service name: %1</span></span></td>
   <td><span data-ttu-id="e582e-478">Den externa tjänsten stoppas.</span><span class="sxs-lookup"><span data-stu-id="e582e-478">The external service is stopped.</span></span></td>
   <td><span data-ttu-id="e582e-479">Starta den externa tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-479">Start the external service.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-480">70</span><span class="sxs-lookup"><span data-stu-id="e582e-480">70</span></span></td>
   <td><span data-ttu-id="e582e-481">Principuppdatering: Tillåt exempelsamling – %1</span><span class="sxs-lookup"><span data-stu-id="e582e-481">Policy update: Allow sample collection - %1</span></span></td>
   <td><span data-ttu-id="e582e-482">Exempelprincipen för samling har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="e582e-482">The sample collection policy was updated.</span></span></td>
   <td><span data-ttu-id="e582e-483">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-483">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-484">71</span><span class="sxs-lookup"><span data-stu-id="e582e-484">71</span></span></td>
   <td><span data-ttu-id="e582e-485">Kommandot Lyckades köra: %1</span><span class="sxs-lookup"><span data-stu-id="e582e-485">Succeeded to run command: %1</span></span></td>
   <td><span data-ttu-id="e582e-486">Kommandot kördes korrekt.</span><span class="sxs-lookup"><span data-stu-id="e582e-486">The command was executed successfully.</span></span></td>
   <td><span data-ttu-id="e582e-487">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-487">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-488">72</span><span class="sxs-lookup"><span data-stu-id="e582e-488">72</span></span></td>
   <td><span data-ttu-id="e582e-489">Försökte skicka den första fullständiga datorprofilrapporten.</span><span class="sxs-lookup"><span data-stu-id="e582e-489">Tried to send first full machine profile report.</span></span> <span data-ttu-id="e582e-490">Resultatkod: %1</span><span class="sxs-lookup"><span data-stu-id="e582e-490">Result code: %1</span></span></td>
   <td><span data-ttu-id="e582e-491">Endast information.</span><span class="sxs-lookup"><span data-stu-id="e582e-491">Informational only.</span></span></td>
   <td><span data-ttu-id="e582e-492">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-492">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-493">73</span><span class="sxs-lookup"><span data-stu-id="e582e-493">73</span></span></td>
   <td><span data-ttu-id="e582e-494">Start för plattform: %1</span><span class="sxs-lookup"><span data-stu-id="e582e-494">Sense starting for platform: %1</span></span></td>
   <td><span data-ttu-id="e582e-495">Endast information.</span><span class="sxs-lookup"><span data-stu-id="e582e-495">Informational only.</span></span></td>
   <td><span data-ttu-id="e582e-496">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-496">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-497">74</span><span class="sxs-lookup"><span data-stu-id="e582e-497">74</span></span></td>
   <td><span data-ttu-id="e582e-498">Enhetstaggen i registret överskrider längdgränsen.</span><span class="sxs-lookup"><span data-stu-id="e582e-498">Device tag in registry exceeds length limit.</span></span> <span data-ttu-id="e582e-499">Taggnamn: %2.</span><span class="sxs-lookup"><span data-stu-id="e582e-499">Tag name: %2.</span></span> <span data-ttu-id="e582e-500">Längdbegränsning: %1.</span><span class="sxs-lookup"><span data-stu-id="e582e-500">Length limit: %1.</span></span></td>
   <td><span data-ttu-id="e582e-501">Enhetstaggen överskrider längdgränsen.</span><span class="sxs-lookup"><span data-stu-id="e582e-501">The device tag exceeds the length limit.</span></span></td>
   <td><span data-ttu-id="e582e-502">Använd en kortare enhetstagg.</span><span class="sxs-lookup"><span data-stu-id="e582e-502">Use a shorter device tag.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-503">81</span><span class="sxs-lookup"><span data-stu-id="e582e-503">81</span></span></td>
   <td><span data-ttu-id="e582e-504">Det gick inte att skapa Windows Defender Advanced Threat Protection ETW – automatisklogg.</span><span class="sxs-lookup"><span data-stu-id="e582e-504">Failed to create Windows Defender Advanced Threat Protection ETW autologger.</span></span> <span data-ttu-id="e582e-505">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="e582e-505">Failure code: %1</span></span></td>
   <td><span data-ttu-id="e582e-506">Det gick inte att skapa ETW-sessionen.</span><span class="sxs-lookup"><span data-stu-id="e582e-506">Failed to create the ETW session.</span></span></td>
   <td><span data-ttu-id="e582e-507">Starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="e582e-507">Reboot the device.</span></span> <span data-ttu-id="e582e-508">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="e582e-508">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-509">82</span><span class="sxs-lookup"><span data-stu-id="e582e-509">82</span></span></td>
   <td><span data-ttu-id="e582e-510">Det gick inte att ta bort Windows Defender Advanced Threat Protection ETW – automatisklogg.</span><span class="sxs-lookup"><span data-stu-id="e582e-510">Failed to remove Windows Defender Advanced Threat Protection ETW autologger.</span></span> <span data-ttu-id="e582e-511">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="e582e-511">Failure code: %1</span></span></td>
   <td><span data-ttu-id="e582e-512">Det gick inte att ta bort ETW-sessionen.</span><span class="sxs-lookup"><span data-stu-id="e582e-512">Failed to delete the ETW session.</span></span></td>
   <td><span data-ttu-id="e582e-513">Kontakta support.</span><span class="sxs-lookup"><span data-stu-id="e582e-513">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-514">84</span><span class="sxs-lookup"><span data-stu-id="e582e-514">84</span></span></td>
   <td><span data-ttu-id="e582e-515">Ange att Windows Defender Antivirus körs.</span><span class="sxs-lookup"><span data-stu-id="e582e-515">Set Windows Defender Antivirus running mode.</span></span> <span data-ttu-id="e582e-516">Tvinga passivt läge: %1, resultatkod: %2.</span><span class="sxs-lookup"><span data-stu-id="e582e-516">Force passive mode: %1, result code: %2.</span></span></td>
   <td><span data-ttu-id="e582e-517">Ställa in defender running mode (aktivt eller passivt).</span><span class="sxs-lookup"><span data-stu-id="e582e-517">Set defender running mode (active or passive).</span></span></td>
   <td><span data-ttu-id="e582e-518">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-518">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-519">85</span><span class="sxs-lookup"><span data-stu-id="e582e-519">85</span></span></td>
   <td><span data-ttu-id="e582e-520">Det gick inte att utlösa körbart windows Defender Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="e582e-520">Failed to trigger Windows Defender Advanced Threat Protection executable.</span></span> <span data-ttu-id="e582e-521">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="e582e-521">Failure code: %1</span></span></td>
   <td><span data-ttu-id="e582e-522">Körbar Stjärn senseIR misslyckades.</span><span class="sxs-lookup"><span data-stu-id="e582e-522">Starring SenseIR executable failed.</span></span></td>
   <td><span data-ttu-id="e582e-523">Starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="e582e-523">Reboot the device.</span></span> <span data-ttu-id="e582e-524">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="e582e-524">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-525">86</span><span class="sxs-lookup"><span data-stu-id="e582e-525">86</span></span></td>
   <td><span data-ttu-id="e582e-526">Starta igen, stoppad extern tjänst som ska vara upp.</span><span class="sxs-lookup"><span data-stu-id="e582e-526">Starting again stopped external service that should be up.</span></span> <span data-ttu-id="e582e-527">Namn: %1, utgångskod: %2</span><span class="sxs-lookup"><span data-stu-id="e582e-527">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="e582e-528">Starta den externa tjänsten igen.</span><span class="sxs-lookup"><span data-stu-id="e582e-528">Starting the external service again.</span></span></td>
   <td><span data-ttu-id="e582e-529">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-529">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-530">87</span><span class="sxs-lookup"><span data-stu-id="e582e-530">87</span></span></td>
   <td><span data-ttu-id="e582e-531">Det går inte att starta den externa tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-531">Cannot start the external service.</span></span> <span data-ttu-id="e582e-532">Namn: %1</span><span class="sxs-lookup"><span data-stu-id="e582e-532">Name: %1</span></span></td>
   <td><span data-ttu-id="e582e-533">Det gick inte att starta den externa tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-533">Failed to start the external service.</span></span></td>
   <td><span data-ttu-id="e582e-534">Kontakta support.</span><span class="sxs-lookup"><span data-stu-id="e582e-534">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-535">88</span><span class="sxs-lookup"><span data-stu-id="e582e-535">88</span></span></td>
   <td><span data-ttu-id="e582e-536">Uppdatera starttypen för den externa tjänsten igen.</span><span class="sxs-lookup"><span data-stu-id="e582e-536">Updating the start type of external service again.</span></span> <span data-ttu-id="e582e-537">Namn: %1, verklig starttyp: %2, förväntad starttyp: %3, utgångskod: %4</span><span class="sxs-lookup"><span data-stu-id="e582e-537">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="e582e-538">Uppdaterade starttypen för den externa tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-538">Updated the start type of the external service.</span></span></td>
   <td><span data-ttu-id="e582e-539">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-539">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-540">89</span><span class="sxs-lookup"><span data-stu-id="e582e-540">89</span></span></td>
   <td><span data-ttu-id="e582e-541">Det går inte att uppdatera starttypen för extern tjänst.</span><span class="sxs-lookup"><span data-stu-id="e582e-541">Cannot update the start type of external service.</span></span> <span data-ttu-id="e582e-542">Namn: %1, verklig starttyp: %2, förväntad starttyp: %3</span><span class="sxs-lookup"><span data-stu-id="e582e-542">Name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="e582e-543">Det går inte att uppdatera starttypen för den externa tjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-543">Can't update the start type of the external service.</span></span></td>
   <td><span data-ttu-id="e582e-544">Kontakta support.</span><span class="sxs-lookup"><span data-stu-id="e582e-544">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-545">90</span><span class="sxs-lookup"><span data-stu-id="e582e-545">90</span></span></td>
   <td><span data-ttu-id="e582e-546">Det gick inte att konfigurera System Guard Runtime Monitor för att ansluta till molntjänsten i geoområde %1.</span><span class="sxs-lookup"><span data-stu-id="e582e-546">Failed to configure System Guard Runtime Monitor to connect to cloud service in geo-region %1.</span></span> <span data-ttu-id="e582e-547">Felkod: %2</span><span class="sxs-lookup"><span data-stu-id="e582e-547">Failure code: %2</span></span></td>
   <td><span data-ttu-id="e582e-548">System Guard Runtime Monitor skickar inte attestationsdata till molntjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-548">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="e582e-549">Kontrollera behörigheterna för registersökvägen: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="e582e-549">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="e582e-550">Kontakta support om det inte är några problem.</span><span class="sxs-lookup"><span data-stu-id="e582e-550">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-551">91</span><span class="sxs-lookup"><span data-stu-id="e582e-551">91</span></span></td>
   <td><span data-ttu-id="e582e-552">Det gick inte att ta bort System Guard Runtime Monitor-information för geoområde.</span><span class="sxs-lookup"><span data-stu-id="e582e-552">Failed to remove System Guard Runtime Monitor geo-region information.</span></span> <span data-ttu-id="e582e-553">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="e582e-553">Failure code: %1</span></span></td>
   <td><span data-ttu-id="e582e-554">System Guard Runtime Monitor skickar inte attestationsdata till molntjänsten.</span><span class="sxs-lookup"><span data-stu-id="e582e-554">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="e582e-555">Kontrollera behörigheterna för registersökvägen: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="e582e-555">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="e582e-556">Kontakta support om det inte är några problem.</span><span class="sxs-lookup"><span data-stu-id="e582e-556">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-557">92</span><span class="sxs-lookup"><span data-stu-id="e582e-557">92</span></span></td>
   <td><span data-ttu-id="e582e-558">Stoppar sändning av sensordatakvot på cyber, eftersom datakvoten överskrids.</span><span class="sxs-lookup"><span data-stu-id="e582e-558">Stopping sending sensor cyber data quota because data quota is exceeded.</span></span> <span data-ttu-id="e582e-559">Återupptar sändningen när kvotperioden går ut.</span><span class="sxs-lookup"><span data-stu-id="e582e-559">Will resume sending once quota period passes.</span></span> <span data-ttu-id="e582e-560">Tillståndsmask: %1</span><span class="sxs-lookup"><span data-stu-id="e582e-560">State Mask: %1</span></span></td>
   <td><span data-ttu-id="e582e-561">Överskrid begränsningsgräns.</span><span class="sxs-lookup"><span data-stu-id="e582e-561">Exceed throttling limit.</span></span></td>
   <td><span data-ttu-id="e582e-562">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-562">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-563">93</span><span class="sxs-lookup"><span data-stu-id="e582e-563">93</span></span></td>
   <td><span data-ttu-id="e582e-564">Återupptar sändning av sensordata i cybern.</span><span class="sxs-lookup"><span data-stu-id="e582e-564">Resuming sending sensor cyber data.</span></span> <span data-ttu-id="e582e-565">Tillståndsmask: %1</span><span class="sxs-lookup"><span data-stu-id="e582e-565">State Mask: %1</span></span></td>
   <td><span data-ttu-id="e582e-566">Återuppta sändning av cyberdata.</span><span class="sxs-lookup"><span data-stu-id="e582e-566">Resume cyber data submission.</span></span></td>
   <td><span data-ttu-id="e582e-567">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-567">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-568">94</span><span class="sxs-lookup"><span data-stu-id="e582e-568">94</span></span></td>
   <td><span data-ttu-id="e582e-569">Körbar fil för Avancerat skydd för Windows Defender har startat</span><span class="sxs-lookup"><span data-stu-id="e582e-569">Windows Defender Advanced Threat Protection executable has started</span></span></td>
   <td><span data-ttu-id="e582e-570">Den körbara SenseCE-filen har startat.</span><span class="sxs-lookup"><span data-stu-id="e582e-570">The SenseCE executable has started.</span></span></td>
   <td><span data-ttu-id="e582e-571">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-571">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-572">95</span><span class="sxs-lookup"><span data-stu-id="e582e-572">95</span></span></td>
   <td><span data-ttu-id="e582e-573">Körbar fil för Windows Defender Advanced Threat Protection har avslutats</span><span class="sxs-lookup"><span data-stu-id="e582e-573">Windows Defender Advanced Threat Protection executable has ended</span></span></td>
   <td><span data-ttu-id="e582e-574">Den körbara SenseCE-filen har avslutats.</span><span class="sxs-lookup"><span data-stu-id="e582e-574">The SenseCE executable has ended.</span></span></td>
   <td><span data-ttu-id="e582e-575">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-575">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-576">96</span><span class="sxs-lookup"><span data-stu-id="e582e-576">96</span></span></td>
   <td><span data-ttu-id="e582e-577">Windows Defender Avancerat skydd Iit har anropats.</span><span class="sxs-lookup"><span data-stu-id="e582e-577">Windows Defender Advanced Threat Protection Init has called.</span></span> <span data-ttu-id="e582e-578">Resultatkod: %2</span><span class="sxs-lookup"><span data-stu-id="e582e-578">Result code: %2</span></span></td>
   <td><span data-ttu-id="e582e-579">Den körbara SenseCE-filen har kallat MCE-initiering.</span><span class="sxs-lookup"><span data-stu-id="e582e-579">The SenseCE executable has called MCE initialization.</span></span></td>
   <td><span data-ttu-id="e582e-580">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-580">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-581">97</span><span class="sxs-lookup"><span data-stu-id="e582e-581">97</span></span></td>
   <td><span data-ttu-id="e582e-582">Det finns anslutningsproblem till molnet för DLP-scenariot</span><span class="sxs-lookup"><span data-stu-id="e582e-582">There are connectivity issues to the Cloud for the DLP scenario</span></span></td>
   <td><span data-ttu-id="e582e-583">Det finns nätverksanslutningsproblem som påverkar DLP-klassificeringsflödet.</span><span class="sxs-lookup"><span data-stu-id="e582e-583">There are network connectivity issues that affect the DLP classification flow.</span></span></td>
   <td><span data-ttu-id="e582e-584">Kontrollera nätverksanslutningen.</span><span class="sxs-lookup"><span data-stu-id="e582e-584">Check the network connectivity.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-585">98</span><span class="sxs-lookup"><span data-stu-id="e582e-585">98</span></span></td>
   <td><span data-ttu-id="e582e-586">Anslutningen till molnet för DLP-scenariot har återställts</span><span class="sxs-lookup"><span data-stu-id="e582e-586">The connectivity to the Cloud for the DLP scenario has been restored</span></span></td>
   <td><span data-ttu-id="e582e-587">Anslutningen till nätverket återställdes och DLP-klassificeringsflödet kan fortsätta.</span><span class="sxs-lookup"><span data-stu-id="e582e-587">The connectivity to the network was restored and the DLP classification flow can continue.</span></span></td>
   <td><span data-ttu-id="e582e-588">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-588">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-589">99</span><span class="sxs-lookup"><span data-stu-id="e582e-589">99</span></span></td>
   <td><span data-ttu-id="e582e-590">Fel i Sense har uppstått när du kommunicerar med server: (%1).</span><span class="sxs-lookup"><span data-stu-id="e582e-590">Sense has encountered the following error while communicating with server: (%1).</span></span> <span data-ttu-id="e582e-591">Resultat: (%2)</span><span class="sxs-lookup"><span data-stu-id="e582e-591">Result: (%2)</span></span></td>
   <td><span data-ttu-id="e582e-592">Ett kommunikationsfel inträffade.</span><span class="sxs-lookup"><span data-stu-id="e582e-592">A communication error occurred.</span></span></td>
   <td><span data-ttu-id="e582e-593">Mer information finns i följande händelser i händelseloggen.</span><span class="sxs-lookup"><span data-stu-id="e582e-593">Check the following events in the event log for further details.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-594">100</span><span class="sxs-lookup"><span data-stu-id="e582e-594">100</span></span></td>
   <td><span data-ttu-id="e582e-595">Det gick inte att starta windows Defender Advanced Threat Protection (körbart skydd).</span><span class="sxs-lookup"><span data-stu-id="e582e-595">Windows Defender Advanced Threat Protection executable failed to start.</span></span> <span data-ttu-id="e582e-596">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="e582e-596">Failure code: %1</span></span></td>
   <td><span data-ttu-id="e582e-597">Det gick inte att starta SenseCE-körbara filer.</span><span class="sxs-lookup"><span data-stu-id="e582e-597">The SenseCE executable has failed to start.</span></span></td>
   <td><span data-ttu-id="e582e-598">Starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="e582e-598">Reboot the device.</span></span> <span data-ttu-id="e582e-599">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="e582e-599">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-600">102</span><span class="sxs-lookup"><span data-stu-id="e582e-600">102</span></span></td>
   <td><span data-ttu-id="e582e-601">Körbar nätverksidentifiering och svar i Windows Defender Advanced Threat Protection har startat</span><span class="sxs-lookup"><span data-stu-id="e582e-601">Windows Defender Advanced Threat Protection Network Detection and Response executable has started</span></span></td>
   <td><span data-ttu-id="e582e-602">Körbar SenseNdr har startat.</span><span class="sxs-lookup"><span data-stu-id="e582e-602">The SenseNdr executable has started.</span></span></td>
   <td><span data-ttu-id="e582e-603">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-603">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e582e-604">103</span><span class="sxs-lookup"><span data-stu-id="e582e-604">103</span></span></td>
   <td><span data-ttu-id="e582e-605">Körbar nätverksidentifiering och svar för Windows Defender Advanced Threat Protection har avslutats</span><span class="sxs-lookup"><span data-stu-id="e582e-605">Windows Defender Advanced Threat Protection Network Detection and Response executable has ended</span></span></td>
   <td><span data-ttu-id="e582e-606">Den körbara SenseNdr-filen har avslutats.</span><span class="sxs-lookup"><span data-stu-id="e582e-606">The SenseNdr executable has ended.</span></span></td>
   <td><span data-ttu-id="e582e-607">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="e582e-607">Normal operating notification; no action required.</span></span></td>
</tr>
</tbody>
</table>

><span data-ttu-id="e582e-608">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="e582e-608">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e582e-609">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="e582e-609">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="e582e-610">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e582e-610">Related topics</span></span>
- [<span data-ttu-id="e582e-611">Introducera Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="e582e-611">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="e582e-612">Konfigurera enhetsproxy och internetanslutningsinställningar</span><span class="sxs-lookup"><span data-stu-id="e582e-612">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="e582e-613">Felsöka Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="e582e-613">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
