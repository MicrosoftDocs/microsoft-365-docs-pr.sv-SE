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
ms.openlocfilehash: a8b7268e89470a85a34015967b69abb1818fe64f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933847"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="9b340-104">Granska händelser och fel med hjälp av Loggboken</span><span class="sxs-lookup"><span data-stu-id="9b340-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9b340-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="9b340-105">**Applies to:**</span></span>
- <span data-ttu-id="9b340-106">Loggboken</span><span class="sxs-lookup"><span data-stu-id="9b340-106">Event Viewer</span></span>
- [<span data-ttu-id="9b340-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="9b340-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="9b340-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9b340-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="9b340-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="9b340-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9b340-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="9b340-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="9b340-111">Du kan granska händelse-IDt i [Loggboken](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) på enskilda enheter.</span><span class="sxs-lookup"><span data-stu-id="9b340-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="9b340-112">Om enheter inte visas i listan Enheter kan du till exempel behöva leta efter händelse-ID på enheterna.</span><span class="sxs-lookup"><span data-stu-id="9b340-112">For example, if devices aren't appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="9b340-113">Du kan sedan använda tabellen för att fastställa ytterligare felsökningssteg.</span><span class="sxs-lookup"><span data-stu-id="9b340-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="9b340-114">**Öppna Loggboken och hitta Microsoft Defender för slutpunktens händelselogg för tjänsten:**</span><span class="sxs-lookup"><span data-stu-id="9b340-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="9b340-115">Klicka **på Start** på Windows-menyn, skriv **Loggboken** och tryck på **Retur.**</span><span class="sxs-lookup"><span data-stu-id="9b340-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="9b340-116">Bläddra i logglistan under **Loggsammanfattning** tills du ser **Microsoft-Windows-SENSE/Operational**.</span><span class="sxs-lookup"><span data-stu-id="9b340-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="9b340-117">Dubbelklicka på objektet för att öppna loggen.</span><span class="sxs-lookup"><span data-stu-id="9b340-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="9b340-118">a.</span><span class="sxs-lookup"><span data-stu-id="9b340-118">a.</span></span>  <span data-ttu-id="9b340-119">Du kan också öppna loggen genom att expandera **Program och tjänstloggar**  >  **Microsoft**  >  **Windows**  >  **SENSE och** klicka på **Drift.**</span><span class="sxs-lookup"><span data-stu-id="9b340-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9b340-120">SENSE är det interna namn som används för att referera till den beteende sensor som driver Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9b340-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="9b340-121">Händelser som registreras av tjänsten visas i loggen.</span><span class="sxs-lookup"><span data-stu-id="9b340-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="9b340-122">I följande tabell finns en lista över händelser som registrerats av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="9b340-123">Händelse-ID</span><span class="sxs-lookup"><span data-stu-id="9b340-123">Event ID</span></span></th>
<th><span data-ttu-id="9b340-124">Meddelande</span><span class="sxs-lookup"><span data-stu-id="9b340-124">Message</span></span></th>
<th><span data-ttu-id="9b340-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9b340-125">Description</span></span></th>
<th><span data-ttu-id="9b340-126">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="9b340-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="9b340-127">1</span><span class="sxs-lookup"><span data-stu-id="9b340-127">1</span></span></td>
<td><span data-ttu-id="9b340-128">Microsoft Defender för slutpunktstjänsten startades (version <code>variable</code> ).</span><span class="sxs-lookup"><span data-stu-id="9b340-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="9b340-129">Inträffar vid start av system, stängs av och under registrering.</span><span class="sxs-lookup"><span data-stu-id="9b340-129">Occurs during system startup, shut down, and during onboarding.</span></span></td>
<td><span data-ttu-id="9b340-130">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-131">2</span><span class="sxs-lookup"><span data-stu-id="9b340-131">2</span></span></td>
<td><span data-ttu-id="9b340-132">Microsoft Defender för Endpoint-tjänsten stängs av.</span><span class="sxs-lookup"><span data-stu-id="9b340-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="9b340-133">Inträffar när enheten stängs av eller stängs av.</span><span class="sxs-lookup"><span data-stu-id="9b340-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="9b340-134">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-135">3</span><span class="sxs-lookup"><span data-stu-id="9b340-135">3</span></span></td>
<td><span data-ttu-id="9b340-136">Microsoft Defender för Slutpunkt-tjänsten kunde inte startas.</span><span class="sxs-lookup"><span data-stu-id="9b340-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="9b340-137">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-138">Tjänsten har inte startar.</span><span class="sxs-lookup"><span data-stu-id="9b340-138">Service didn't start.</span></span></td>
<td><span data-ttu-id="9b340-139">Granska andra meddelanden för att fastställa möjliga orsaker och felsökningssteg.</span><span class="sxs-lookup"><span data-stu-id="9b340-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-140">4</span><span class="sxs-lookup"><span data-stu-id="9b340-140">4</span></span></td>
<td><span data-ttu-id="9b340-141">Microsoft Defender för Slutpunkt-tjänsten kontaktade servern på <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-142">Variabel = URL för Defender för slutpunktsbearbetningsservrar.</span><span class="sxs-lookup"><span data-stu-id="9b340-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="9b340-143">Den här URL:en matchar den som visas i brandväggen eller nätverksaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="9b340-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="9b340-144">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-145">5</span><span class="sxs-lookup"><span data-stu-id="9b340-145">5</span></span></td>
<td><span data-ttu-id="9b340-146">Microsoft Defender för slutpunktstjänsten kunde inte ansluta till servern hos <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-147">Variabel = URL för Defender för slutpunktsbearbetningsservrar.</span><span class="sxs-lookup"><span data-stu-id="9b340-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="9b340-148">Det gick inte att kontakta den externa bearbetningsservrarna på den URL:en.</span><span class="sxs-lookup"><span data-stu-id="9b340-148">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="9b340-149">Kontrollera anslutningen till URL:en.</span><span class="sxs-lookup"><span data-stu-id="9b340-149">Check the connection to the URL.</span></span> <span data-ttu-id="9b340-150">Se <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Konfigurera proxy och Internetanslutning.</a></span><span class="sxs-lookup"><span data-stu-id="9b340-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-151">6</span><span class="sxs-lookup"><span data-stu-id="9b340-151">6</span></span></td>
<td><span data-ttu-id="9b340-152">Microsoft Defender för Slutpunkt-tjänsten är inte onboarded och inga onboarding-parametrar hittades.</span><span class="sxs-lookup"><span data-stu-id="9b340-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="9b340-153">Enheten fungerade inte korrekt och rapporterar inte till portalen.</span><span class="sxs-lookup"><span data-stu-id="9b340-153">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="9b340-154">Onboarding måste köras innan tjänsten startas.</span><span class="sxs-lookup"><span data-stu-id="9b340-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="9b340-155">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="9b340-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="9b340-156">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="9b340-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="9b340-157">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="9b340-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-158">7</span><span class="sxs-lookup"><span data-stu-id="9b340-158">7</span></span></td>
<td><span data-ttu-id="9b340-159">Microsoft Defender för slutpunktstjänsten kunde inte läsa onboarding-parametrarna.</span><span class="sxs-lookup"><span data-stu-id="9b340-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="9b340-160">Fel: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-161">Variabel = detaljerad felbeskrivning.</span><span class="sxs-lookup"><span data-stu-id="9b340-161">Variable = detailed error description.</span></span> <span data-ttu-id="9b340-162">Enheten fungerade inte korrekt och rapporterar inte till portalen.</span><span class="sxs-lookup"><span data-stu-id="9b340-162">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="9b340-163">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="9b340-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="9b340-164">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="9b340-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="9b340-165">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="9b340-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-166">8</span><span class="sxs-lookup"><span data-stu-id="9b340-166">8</span></span></td>
<td><span data-ttu-id="9b340-167">Microsoft Defender för slutpunktstjänsten kunde inte rensa konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="9b340-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="9b340-168">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-169"><b>Under introduktionen:</b> Det gick inte att rensa konfigurationen av tjänsten under onboarding.</span><span class="sxs-lookup"><span data-stu-id="9b340-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="9b340-170">Onboarding-processen fortsätter.</span><span class="sxs-lookup"><span data-stu-id="9b340-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="9b340-171"><b>Under offboarding:</b> Tjänsten kunde inte rensa konfigurationen under offboarding.</span><span class="sxs-lookup"><span data-stu-id="9b340-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="9b340-172">Offboarding-processen har slutförts men tjänsten fortsätter att köras.</span><span class="sxs-lookup"><span data-stu-id="9b340-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="9b340-173"><b>Introduktion:</b> Ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="9b340-174"><b>Offboarding:</b> Starta om systemet.</span><span class="sxs-lookup"><span data-stu-id="9b340-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="9b340-175">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="9b340-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-176">9</span><span class="sxs-lookup"><span data-stu-id="9b340-176">9</span></span></td>
<td><span data-ttu-id="9b340-177">Microsoft Defender för slutpunktstjänsten kunde inte ändra starttypen.</span><span class="sxs-lookup"><span data-stu-id="9b340-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="9b340-178">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-179"><b>Under introduktionen:</b> Enheten fungerade inte korrekt och rapporterar inte till portalen.</span><span class="sxs-lookup"><span data-stu-id="9b340-179"><b>During onboarding:</b> The device didn't onboard correctly and won't be reporting to the portal.</span></span> <br><br><span data-ttu-id="9b340-180"><b>Under offboarding:</b> Det gick inte att ändra tjänstens starttyp.</span><span class="sxs-lookup"><span data-stu-id="9b340-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="9b340-181">Offboarding-processen fortsätter.</span><span class="sxs-lookup"><span data-stu-id="9b340-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="9b340-182">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="9b340-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="9b340-183">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="9b340-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="9b340-184">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="9b340-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-185">10</span><span class="sxs-lookup"><span data-stu-id="9b340-185">10</span></span></td>
<td><span data-ttu-id="9b340-186">Microsoft Defender för slutpunktstjänsten kunde inte spara informationen om introduktionen.</span><span class="sxs-lookup"><span data-stu-id="9b340-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="9b340-187">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-188">Enheten fungerade inte korrekt och rapporterar inte till portalen.</span><span class="sxs-lookup"><span data-stu-id="9b340-188">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="9b340-189">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="9b340-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="9b340-190">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="9b340-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="9b340-191">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="9b340-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-192">11</span><span class="sxs-lookup"><span data-stu-id="9b340-192">11</span></span></td>
<td><span data-ttu-id="9b340-193">Registrering eller om onboarding av Defender för slutpunktstjänsten har slutförts.</span><span class="sxs-lookup"><span data-stu-id="9b340-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="9b340-194">Enheten var korrekt igång.</span><span class="sxs-lookup"><span data-stu-id="9b340-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="9b340-195">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="9b340-196">Det kan ta flera timmar innan enheten visas i portalen.</span><span class="sxs-lookup"><span data-stu-id="9b340-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-197">12</span><span class="sxs-lookup"><span data-stu-id="9b340-197">12</span></span></td>
<td><span data-ttu-id="9b340-198">Standardkonfigurationen kunde inte användas i Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9b340-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="9b340-199">Det gick inte att använda standardkonfigurationen för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="9b340-200">Det här felet bör åtgärdas efter en kort tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="9b340-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-201">13</span><span class="sxs-lookup"><span data-stu-id="9b340-201">13</span></span></td>
<td><span data-ttu-id="9b340-202">Microsoft Defender för slutpunktens enhets-ID beräknat: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-203">Normal driftprocess.</span><span class="sxs-lookup"><span data-stu-id="9b340-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="9b340-204">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-205">15</span><span class="sxs-lookup"><span data-stu-id="9b340-205">15</span></span></td>
<td><span data-ttu-id="9b340-206">Microsoft Defender för Slutpunkt kan inte starta kommandokanalen med URL: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-207">Variabel = URL för Defender för slutpunktsbearbetningsservrar.</span><span class="sxs-lookup"><span data-stu-id="9b340-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="9b340-208">Det gick inte att kontakta den externa bearbetningsservrarna på den URL:en.</span><span class="sxs-lookup"><span data-stu-id="9b340-208">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="9b340-209">Kontrollera anslutningen till URL:en.</span><span class="sxs-lookup"><span data-stu-id="9b340-209">Check the connection to the URL.</span></span> <span data-ttu-id="9b340-210">Se <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Konfigurera proxy och Internetanslutning.</a></span><span class="sxs-lookup"><span data-stu-id="9b340-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-211">17</span><span class="sxs-lookup"><span data-stu-id="9b340-211">17</span></span></td>
<td><span data-ttu-id="9b340-212">Microsoft Defender för slutpunktstjänsten kunde inte ändra plats för anslutna användarupplevelser och telemetritjänster.</span><span class="sxs-lookup"><span data-stu-id="9b340-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="9b340-213">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-214">Ett fel uppstod med Windows-telemetritjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="9b340-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Kontrollera att diagnostikdatatjänsten är aktiverad.</a></span><span class="sxs-lookup"><span data-stu-id="9b340-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="9b340-216">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="9b340-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="9b340-217">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="9b340-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="9b340-218">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="9b340-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-219">18</span><span class="sxs-lookup"><span data-stu-id="9b340-219">18</span></span></td>
<td><span data-ttu-id="9b340-220">OOBE (Välkommen i Windows) har slutförts.</span><span class="sxs-lookup"><span data-stu-id="9b340-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="9b340-221">Tjänsten startar först när Windows-uppdateringarna har installerats.</span><span class="sxs-lookup"><span data-stu-id="9b340-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="9b340-222">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-223">19</span><span class="sxs-lookup"><span data-stu-id="9b340-223">19</span></span></td>
<td><span data-ttu-id="9b340-224">OOBE (Välkommen i Windows) har ännu inte slutförts.</span><span class="sxs-lookup"><span data-stu-id="9b340-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="9b340-225">Tjänsten startar först när Windows-uppdateringarna har installerats.</span><span class="sxs-lookup"><span data-stu-id="9b340-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="9b340-226">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="9b340-227">Om det här felet kvarstår efter en omstart av systemet bör du kontrollera att alla Windows-uppdateringar har installerats.</span><span class="sxs-lookup"><span data-stu-id="9b340-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-228">20</span><span class="sxs-lookup"><span data-stu-id="9b340-228">20</span></span></td>
<td><span data-ttu-id="9b340-229">Det går inte att vänta på att OOBE (Välkommen i Windows) ska slutföras.</span><span class="sxs-lookup"><span data-stu-id="9b340-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="9b340-230">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-231">Internt fel.</span><span class="sxs-lookup"><span data-stu-id="9b340-231">Internal error.</span></span></td>
<td><span data-ttu-id="9b340-232">Om det här felet kvarstår efter en omstart av systemet bör du kontrollera att alla Windows-uppdateringar har installerats.</span><span class="sxs-lookup"><span data-stu-id="9b340-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-233">25</span><span class="sxs-lookup"><span data-stu-id="9b340-233">25</span></span></td>
<td><span data-ttu-id="9b340-234">Microsoft Defender för Slutpunkt-tjänsten kunde inte återställa hälsostatus i registret.</span><span class="sxs-lookup"><span data-stu-id="9b340-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="9b340-235">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-236">Enheten fungerade inte korrekt.</span><span class="sxs-lookup"><span data-stu-id="9b340-236">The device didn't onboard correctly.</span></span>
<span data-ttu-id="9b340-237">Den rapporterar till portalen, men tjänsten kanske inte visas som registrerad i SCCM eller registret.</span><span class="sxs-lookup"><span data-stu-id="9b340-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="9b340-238">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="9b340-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="9b340-239">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="9b340-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="9b340-240">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="9b340-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-241">26</span><span class="sxs-lookup"><span data-stu-id="9b340-241">26</span></span></td>
<td><span data-ttu-id="9b340-242">Microsoft Defender för slutpunktstjänsten kunde inte ange registreringsstatus i registret.</span><span class="sxs-lookup"><span data-stu-id="9b340-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="9b340-243">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-244">Enheten fungerade inte korrekt.</span><span class="sxs-lookup"><span data-stu-id="9b340-244">The device didn't onboard correctly.</span></span><br>
<span data-ttu-id="9b340-245">Den rapporterar till portalen, men tjänsten kanske inte visas som registrerad i SCCM eller registret.</span><span class="sxs-lookup"><span data-stu-id="9b340-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="9b340-246">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="9b340-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="9b340-247">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="9b340-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="9b340-248">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="9b340-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-249">27</span><span class="sxs-lookup"><span data-stu-id="9b340-249">27</span></span></td>
<td><span data-ttu-id="9b340-250">Microsoft Defender för slutpunktstjänsten kunde inte aktivera SENSE-läge i Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="9b340-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="9b340-251">Onboarding-processen misslyckades.</span><span class="sxs-lookup"><span data-stu-id="9b340-251">Onboarding process failed.</span></span> <span data-ttu-id="9b340-252">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-253">Normalt inger Microsoft Defender Antivirus ett särskilt passivt läge om en annan antimalwareprodukt i realtid körs korrekt på enheten och enheten rapporterar till Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9b340-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="9b340-254">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="9b340-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="9b340-255">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="9b340-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="9b340-256">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="9b340-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="9b340-257">Se till att skydd mot skadlig programvara i realtid fungerar som det ska.</span><span class="sxs-lookup"><span data-stu-id="9b340-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-258">28</span><span class="sxs-lookup"><span data-stu-id="9b340-258">28</span></span></td>
<td><span data-ttu-id="9b340-259">Microsoft Defender för slutpunktsanslutna användarupplevelser och registrering av telemetritjänster misslyckades.</span><span class="sxs-lookup"><span data-stu-id="9b340-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="9b340-260">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-261">Ett fel uppstod med Windows-telemetritjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="9b340-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Kontrollera att diagnostikdatatjänsten är aktiverad.</a></span><span class="sxs-lookup"><span data-stu-id="9b340-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="9b340-263">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="9b340-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="9b340-264">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="9b340-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="9b340-265">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="9b340-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-266">29</span><span class="sxs-lookup"><span data-stu-id="9b340-266">29</span></span></td>
<td><span data-ttu-id="9b340-267">Det gick inte att läsa parametrarna för offboarding.</span><span class="sxs-lookup"><span data-stu-id="9b340-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="9b340-268">Feltyp: %1, Felkod: %2, Beskrivning: %3</span><span class="sxs-lookup"><span data-stu-id="9b340-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="9b340-269">Händelsen inträffar när systemet inte&#39;av parametrarna för offboarding.</span><span class="sxs-lookup"><span data-stu-id="9b340-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="9b340-270">Kontrollera att enheten har internetanslutning och kör sedan hela offboardingprocessen igen.</span><span class="sxs-lookup"><span data-stu-id="9b340-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="9b340-271">Kontrollera att offboarding-paketet inte har gått ut.</span><span class="sxs-lookup"><span data-stu-id="9b340-271">Ensure the offboarding package hasn't expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-272">30</span><span class="sxs-lookup"><span data-stu-id="9b340-272">30</span></span></td>
<td><span data-ttu-id="9b340-273">Microsoft Defender för slutpunktstjänsten kunde inte inaktivera SENSE-läge i Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="9b340-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="9b340-274">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-275">Normalt inger Microsoft Defender Antivirus ett särskilt passivt läge om en annan antimalwareprodukt i realtid körs korrekt på enheten och enheten rapporterar till Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="9b340-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="9b340-276">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="9b340-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="9b340-277">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="9b340-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="9b340-278">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter</a></span><span class="sxs-lookup"><span data-stu-id="9b340-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="9b340-279">Se till att skydd mot skadlig programvara i realtid fungerar som det ska.</span><span class="sxs-lookup"><span data-stu-id="9b340-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-280">31</span><span class="sxs-lookup"><span data-stu-id="9b340-280">31</span></span></td>
<td><span data-ttu-id="9b340-281">Microsoft Defender för slutpunktsanslutna användarupplevelser och avregistrering av telemetritjänsten misslyckades.</span><span class="sxs-lookup"><span data-stu-id="9b340-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="9b340-282">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-283">Ett fel uppstod med Windows-telemetritjänsten under onboarding.</span><span class="sxs-lookup"><span data-stu-id="9b340-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="9b340-284">Offboarding-processen fortsätter.</span><span class="sxs-lookup"><span data-stu-id="9b340-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="9b340-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Sök efter fel med Windows-telemetritjänsten</a>.</span><span class="sxs-lookup"><span data-stu-id="9b340-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-286">32</span><span class="sxs-lookup"><span data-stu-id="9b340-286">32</span></span></td>
<td><span data-ttu-id="9b340-287">Microsoft Defender för slutpunktstjänsten kunde inte begära att stoppa sig själv efter offboardingprocessen.</span><span class="sxs-lookup"><span data-stu-id="9b340-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="9b340-288">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="9b340-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="9b340-289">Ett fel uppstod vid offboarding.</span><span class="sxs-lookup"><span data-stu-id="9b340-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="9b340-290">Starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="9b340-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-291">33</span><span class="sxs-lookup"><span data-stu-id="9b340-291">33</span></span></td>
<td><span data-ttu-id="9b340-292">Microsoft Defender för slutpunktstjänsten kunde inte spara SENSE GUID.</span><span class="sxs-lookup"><span data-stu-id="9b340-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="9b340-293">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-294">En unik identifierare används för att representera varje enhet som rapporterar till portalen.</span><span class="sxs-lookup"><span data-stu-id="9b340-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="9b340-295">Om identifieraren inte finns kvar kan samma enhet visas två gånger i portalen.</span><span class="sxs-lookup"><span data-stu-id="9b340-295">If the identifier doesn't persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="9b340-296">Kontrollera registerbehörigheter på enheten för att säkerställa att tjänsten kan uppdatera registret.</span><span class="sxs-lookup"><span data-stu-id="9b340-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-297">34</span><span class="sxs-lookup"><span data-stu-id="9b340-297">34</span></span></td>
<td><span data-ttu-id="9b340-298">Microsoft Defender för Slutpunkt-tjänsten kunde inte lägga till sig själv som ett beroende av den anslutna användarupplevelsen och telemetritjänsten, vilket ledde till att onboarding-processen misslyckades.</span><span class="sxs-lookup"><span data-stu-id="9b340-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="9b340-299">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-300">Ett fel uppstod med Windows-telemetritjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="9b340-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Kontrollera att diagnostikdatatjänsten är aktiverad.</a></span><span class="sxs-lookup"><span data-stu-id="9b340-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="9b340-302">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="9b340-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="9b340-303">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="9b340-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="9b340-304">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="9b340-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-305">35</span><span class="sxs-lookup"><span data-stu-id="9b340-305">35</span></span></td>
<td><span data-ttu-id="9b340-306">Microsoft Defender för slutpunktstjänsten kunde inte ta bort sig själv som ett beroende av den anslutna användarupplevelsen och telemetritjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="9b340-307">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-308">Ett fel uppstod med Windows-telemetritjänsten under offboarding.</span><span class="sxs-lookup"><span data-stu-id="9b340-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="9b340-309">Offboarding-processen fortsätter.</span><span class="sxs-lookup"><span data-stu-id="9b340-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="9b340-310">Sök efter fel med Windows-diagnostikdatatjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-311">36</span><span class="sxs-lookup"><span data-stu-id="9b340-311">36</span></span></td>
<td><span data-ttu-id="9b340-312">Microsoft Defender för slutpunktsanslutna användarupplevelser och telemetritjänstregistrering lyckades.</span><span class="sxs-lookup"><span data-stu-id="9b340-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="9b340-313">Slutförandekod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="9b340-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="9b340-314">Registrering av Defender för slutpunkt med den anslutna användarupplevelsen och telemetritjänsten har slutförts.</span><span class="sxs-lookup"><span data-stu-id="9b340-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="9b340-315">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-316">37</span><span class="sxs-lookup"><span data-stu-id="9b340-316">37</span></span></td>
<td><span data-ttu-id="9b340-317">Microsoft Defender för slutpunkt En modul kommer att överskrida sin kvot.</span><span class="sxs-lookup"><span data-stu-id="9b340-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="9b340-318">Modul: %1, Kvot: {%2} {%3}, Procentandel av kvotens användning: %4.</span><span class="sxs-lookup"><span data-stu-id="9b340-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="9b340-319">Enheten har nästan använt sin tilldelade kvot under det aktuella 24-timmarsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9b340-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="9b340-320">Den kommer att begränsas.</span><span class="sxs-lookup"><span data-stu-id="9b340-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="9b340-321">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-322">38</span><span class="sxs-lookup"><span data-stu-id="9b340-322">38</span></span></td>
<td><span data-ttu-id="9b340-323">Nätverksanslutningen identifieras som låg.</span><span class="sxs-lookup"><span data-stu-id="9b340-323">Network connection is identified as low.</span></span> <span data-ttu-id="9b340-324">Microsoft Defender för Endpoint kontaktar servern var %1:e minut.</span><span class="sxs-lookup"><span data-stu-id="9b340-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="9b340-325">Anslutning med datatrafik: %2, internet tillgängligt: %3, kostnadsfritt nätverk tillgängligt: %4.</span><span class="sxs-lookup"><span data-stu-id="9b340-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="9b340-326">Enheten använder ett nätverk med datatrafik/betalt nätverk och kontaktar servern mer sällan.</span><span class="sxs-lookup"><span data-stu-id="9b340-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="9b340-327">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-328">39</span><span class="sxs-lookup"><span data-stu-id="9b340-328">39</span></span></td>
<td><span data-ttu-id="9b340-329">Nätverksanslutningen identifieras som normal.</span><span class="sxs-lookup"><span data-stu-id="9b340-329">Network connection is identified as normal.</span></span> <span data-ttu-id="9b340-330">Microsoft Defender för Endpoint kontaktar servern var %1:e minut.</span><span class="sxs-lookup"><span data-stu-id="9b340-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="9b340-331">Anslutning med datatrafik: %2, internet tillgängligt: %3, kostnadsfritt nätverk tillgängligt: %4.</span><span class="sxs-lookup"><span data-stu-id="9b340-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="9b340-332">Enheten använder inte en anslutning med databetalda data och kontaktar servern som vanligt.</span><span class="sxs-lookup"><span data-stu-id="9b340-332">The device isn't using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="9b340-333">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-334">40</span><span class="sxs-lookup"><span data-stu-id="9b340-334">40</span></span></td>
<td><span data-ttu-id="9b340-335">Batteritillståndet identifieras som låg.</span><span class="sxs-lookup"><span data-stu-id="9b340-335">Battery state is identified as low.</span></span> <span data-ttu-id="9b340-336">Microsoft Defender för Endpoint kontaktar servern var %1:e minut.</span><span class="sxs-lookup"><span data-stu-id="9b340-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="9b340-337">Batteritillstånd: %2.</span><span class="sxs-lookup"><span data-stu-id="9b340-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="9b340-338">Enheten har låg batterinivå och kontaktar servern mindre ofta.</span><span class="sxs-lookup"><span data-stu-id="9b340-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="9b340-339">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-340">41</span><span class="sxs-lookup"><span data-stu-id="9b340-340">41</span></span></td>
<td><span data-ttu-id="9b340-341">Batteritillståndet identifieras som normalt.</span><span class="sxs-lookup"><span data-stu-id="9b340-341">Battery state is identified as normal.</span></span> <span data-ttu-id="9b340-342">Microsoft Defender för Endpoint kontaktar servern var %1:e minut.</span><span class="sxs-lookup"><span data-stu-id="9b340-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="9b340-343">Batteritillstånd: %2.</span><span class="sxs-lookup"><span data-stu-id="9b340-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="9b340-344">Enheten har inte låg batterinivå och kontaktar servern som vanligt.</span><span class="sxs-lookup"><span data-stu-id="9b340-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="9b340-345">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-346">42</span><span class="sxs-lookup"><span data-stu-id="9b340-346">42</span></span></td>
<td><span data-ttu-id="9b340-347">Microsoft Defender för slutpunktskomponenten kunde inte utföra någon åtgärd.</span><span class="sxs-lookup"><span data-stu-id="9b340-347">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="9b340-348">Komponent: %1, Åtgärd: %2, Undantagstyp: %3, Undantagsmeddelande: %4</span><span class="sxs-lookup"><span data-stu-id="9b340-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="9b340-349">Internt fel.</span><span class="sxs-lookup"><span data-stu-id="9b340-349">Internal error.</span></span> <span data-ttu-id="9b340-350">Det gick inte att starta tjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="9b340-351">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="9b340-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-352">43</span><span class="sxs-lookup"><span data-stu-id="9b340-352">43</span></span></td>
<td><span data-ttu-id="9b340-353">Microsoft Defender för slutpunktskomponenten kunde inte utföra någon åtgärd.</span><span class="sxs-lookup"><span data-stu-id="9b340-353">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="9b340-354">Komponent: %1, Åtgärd: %2, Undantagstyp: %3, Undantagsfel: %4, Undantagsmeddelande: %5</span><span class="sxs-lookup"><span data-stu-id="9b340-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="9b340-355">Internt fel.</span><span class="sxs-lookup"><span data-stu-id="9b340-355">Internal error.</span></span> <span data-ttu-id="9b340-356">Det gick inte att starta tjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="9b340-357">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="9b340-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-358">44</span><span class="sxs-lookup"><span data-stu-id="9b340-358">44</span></span></td>
<td><span data-ttu-id="9b340-359">Offboarding av Defender för slutpunktstjänsten har slutförts.</span><span class="sxs-lookup"><span data-stu-id="9b340-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="9b340-360">Tjänsten var offboarded.</span><span class="sxs-lookup"><span data-stu-id="9b340-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="9b340-361">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-362">45</span><span class="sxs-lookup"><span data-stu-id="9b340-362">45</span></span></td>
<td><span data-ttu-id="9b340-363">Det gick inte att registrera och starta händelsespårningssessionen [%1].</span><span class="sxs-lookup"><span data-stu-id="9b340-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="9b340-364">Felkod: %2</span><span class="sxs-lookup"><span data-stu-id="9b340-364">Error code: %2</span></span></td>
<td><span data-ttu-id="9b340-365">Ett fel uppstod vid start av tjänsten vid skapandet av ETW-session.</span><span class="sxs-lookup"><span data-stu-id="9b340-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="9b340-366">Detta orsakade startfel för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="9b340-367">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="9b340-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-368">46</span><span class="sxs-lookup"><span data-stu-id="9b340-368">46</span></span></td>
<td><span data-ttu-id="9b340-369">Det gick inte att registrera och starta händelsespårningssessionen [%1] på grund av brist på resurser.</span><span class="sxs-lookup"><span data-stu-id="9b340-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="9b340-370">Felkod: %2.</span><span class="sxs-lookup"><span data-stu-id="9b340-370">Error code: %2.</span></span> <span data-ttu-id="9b340-371">Det beror troligen på att det finns för många sessioner med aktiva händelsespårningar.</span><span class="sxs-lookup"><span data-stu-id="9b340-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="9b340-372">Tjänsten kommer att försöka igen om 1 minut.</span><span class="sxs-lookup"><span data-stu-id="9b340-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="9b340-373">Ett fel uppstod vid start av tjänsten när ETW-sessionen skulle skapas på grund av brist på resurser.</span><span class="sxs-lookup"><span data-stu-id="9b340-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="9b340-374">Tjänsten startades och körs, men rapporterar inte en sensorhändelse förrän ETW-sessionen startas.</span><span class="sxs-lookup"><span data-stu-id="9b340-374">The service started and is running, but won't report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="9b340-375">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="9b340-376">Tjänsten försöker starta sessionen varje minut.</span><span class="sxs-lookup"><span data-stu-id="9b340-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-377">47</span><span class="sxs-lookup"><span data-stu-id="9b340-377">47</span></span></td>
<td><span data-ttu-id="9b340-378">Registrerad och startade händelsespårningssessionen – återställdes efter tidigare misslyckade försök.</span><span class="sxs-lookup"><span data-stu-id="9b340-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="9b340-379">Händelsen följer den föregående händelsen efter att ETW-sessionen har startar.</span><span class="sxs-lookup"><span data-stu-id="9b340-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="9b340-380">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="9b340-381">48</span><span class="sxs-lookup"><span data-stu-id="9b340-381">48</span></span></td>
<td><span data-ttu-id="9b340-382">Det gick inte att lägga till en provider [%1] i händelsespårningssession [%2].</span><span class="sxs-lookup"><span data-stu-id="9b340-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="9b340-383">Felkod: %3.</span><span class="sxs-lookup"><span data-stu-id="9b340-383">Error code: %3.</span></span> <span data-ttu-id="9b340-384">Det innebär att händelser från den här leverantören inte rapporteras.</span><span class="sxs-lookup"><span data-stu-id="9b340-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="9b340-385">Det gick inte att lägga till en leverantör i ETW-sessionen.</span><span class="sxs-lookup"><span data-stu-id="9b340-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="9b340-386">Därför rapporteras inte leverantörshändelserna.</span><span class="sxs-lookup"><span data-stu-id="9b340-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="9b340-387">Kontrollera felkoden.</span><span class="sxs-lookup"><span data-stu-id="9b340-387">Check the error code.</span></span> <span data-ttu-id="9b340-388">Kontakta support om felet kvarstår.</span><span class="sxs-lookup"><span data-stu-id="9b340-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
<tr>
   <td><span data-ttu-id="9b340-389">49</span><span class="sxs-lookup"><span data-stu-id="9b340-389">49</span></span></td>
   <td><span data-ttu-id="9b340-390">Kommandot ogiltig molnkonfiguration har tagits emot och ignorerats.</span><span class="sxs-lookup"><span data-stu-id="9b340-390">Invalid cloud configuration command received and ignored.</span></span> <span data-ttu-id="9b340-391">Version: %1, status: %2, felkod: %3, meddelande: %4</span><span class="sxs-lookup"><span data-stu-id="9b340-391">Version: %1, status: %2, error code: %3, message: %4</span></span></td>
   <td><span data-ttu-id="9b340-392">Fick en ogiltig konfigurationsfil från molntjänsten som ignorerades.</span><span class="sxs-lookup"><span data-stu-id="9b340-392">Received an invalid configuration file from the cloud service that was ignored.</span></span></td>
   <td><span data-ttu-id="9b340-393">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="9b340-393">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-394">50</span><span class="sxs-lookup"><span data-stu-id="9b340-394">50</span></span></td>
   <td><span data-ttu-id="9b340-395">Den nya molnkonfigurationen har använts.</span><span class="sxs-lookup"><span data-stu-id="9b340-395">New cloud configuration applied successfully.</span></span> <span data-ttu-id="9b340-396">Version: %1.</span><span class="sxs-lookup"><span data-stu-id="9b340-396">Version: %1.</span></span></td>
   <td><span data-ttu-id="9b340-397">En ny konfiguration från molntjänsten har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="9b340-397">Successfully applied a new configuration from the cloud service.</span></span></td>
   <td><span data-ttu-id="9b340-398">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-398">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-399">51</span><span class="sxs-lookup"><span data-stu-id="9b340-399">51</span></span></td>
   <td><span data-ttu-id="9b340-400">Ny molnkonfiguration kunde inte användas, version: %1.</span><span class="sxs-lookup"><span data-stu-id="9b340-400">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="9b340-401">Den senaste kända konfigurationen, version %2, har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="9b340-401">Successfully applied the last known good configuration, version %2.</span></span></td>
   <td><span data-ttu-id="9b340-402">Fick en felaktig konfigurationsfil från molntjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-402">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="9b340-403">Den senaste kända konfigurationen har använts.</span><span class="sxs-lookup"><span data-stu-id="9b340-403">Last known good configuration was applied successfully.</span></span></td>
   <td><span data-ttu-id="9b340-404">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="9b340-404">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-405">52</span><span class="sxs-lookup"><span data-stu-id="9b340-405">52</span></span></td>
   <td><span data-ttu-id="9b340-406">Ny molnkonfiguration kunde inte användas, version: %1.</span><span class="sxs-lookup"><span data-stu-id="9b340-406">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="9b340-407">Det gick inte heller att använda den senaste kända konfigurationen, version %2.</span><span class="sxs-lookup"><span data-stu-id="9b340-407">Also failed to apply last known good configuration, version %2.</span></span> <span data-ttu-id="9b340-408">Standardkonfigurationen har tillämpats.</span><span class="sxs-lookup"><span data-stu-id="9b340-408">Successfully applied the default configuration.</span></span></td>
   <td><span data-ttu-id="9b340-409">Fick en felaktig konfigurationsfil från molntjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-409">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="9b340-410">Det gick inte att använda den senaste kända konfigurationen – och standardkonfigurationen tillämpades.</span><span class="sxs-lookup"><span data-stu-id="9b340-410">Failed to apply the last known good configuration - and the default configuration was applied.</span></span></td>
   <td><span data-ttu-id="9b340-411">Tjänsten försöker ladda ned en ny konfigurationsfil inom 5 minuter.</span><span class="sxs-lookup"><span data-stu-id="9b340-411">The service will attempt to download a new configuration file within 5 minutes.</span></span> <span data-ttu-id="9b340-412">Om du inte ser händelsen #50 kontakta support.</span><span class="sxs-lookup"><span data-stu-id="9b340-412">If you don't see event #50 - contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-413">53</span><span class="sxs-lookup"><span data-stu-id="9b340-413">53</span></span></td>
   <td><span data-ttu-id="9b340-414">Molnkonfiguration som lästs in från beständig lagring, version: %1.</span><span class="sxs-lookup"><span data-stu-id="9b340-414">Cloud configuration loaded from persistent storage, version: %1.</span></span></td>
   <td><span data-ttu-id="9b340-415">Konfigurationen startades från beständig lagring vid start av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-415">The configuration was loaded from persistent storage on service startup.</span></span></td>
   <td><span data-ttu-id="9b340-416">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-416">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-417">55</span><span class="sxs-lookup"><span data-stu-id="9b340-417">55</span></span></td>
   <td><span data-ttu-id="9b340-418">Det gick inte att skapa automatisk ETW-loggare för säker ETW.</span><span class="sxs-lookup"><span data-stu-id="9b340-418">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="9b340-419">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="9b340-419">Failure code: %1</span></span></td>
   <td><span data-ttu-id="9b340-420">Det gick inte att skapa den säkra ETW-loggern.</span><span class="sxs-lookup"><span data-stu-id="9b340-420">Failed to create the secure ETW logger.</span></span></td>
   <td><span data-ttu-id="9b340-421">Starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="9b340-421">Reboot the device.</span></span> <span data-ttu-id="9b340-422">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="9b340-422">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-423">56</span><span class="sxs-lookup"><span data-stu-id="9b340-423">56</span></span></td>
   <td><span data-ttu-id="9b340-424">Det gick inte att ta bort automatisk loggare för Secure ETW.</span><span class="sxs-lookup"><span data-stu-id="9b340-424">Failed to remove the Secure ETW autologger.</span></span> <span data-ttu-id="9b340-425">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="9b340-425">Failure code: %1</span></span></td>
   <td><span data-ttu-id="9b340-426">Det gick inte att ta bort den säkra ETW-sessionen på offboarding.</span><span class="sxs-lookup"><span data-stu-id="9b340-426">Failed to remove the secure ETW session on offboarding.</span></span></td>
   <td><span data-ttu-id="9b340-427">Kontakta support.</span><span class="sxs-lookup"><span data-stu-id="9b340-427">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-428">57</span><span class="sxs-lookup"><span data-stu-id="9b340-428">57</span></span></td>
   <td><span data-ttu-id="9b340-429">Fånga en ögonblicksbild av datorn i felsökningssyfte.</span><span class="sxs-lookup"><span data-stu-id="9b340-429">Capturing a snapshot of the machine for troubleshooting purposes.</span></span></td>
   <td><span data-ttu-id="9b340-430">Ett undersökningspaket, även kallat en forensisk paket, samlas in.</span><span class="sxs-lookup"><span data-stu-id="9b340-430">An investigation package, also known as forensics package, is being collected.</span></span></td>
   <td><span data-ttu-id="9b340-431">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-431">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-432">59</span><span class="sxs-lookup"><span data-stu-id="9b340-432">59</span></span></td>
   <td><span data-ttu-id="9b340-433">Startkommando: %1</span><span class="sxs-lookup"><span data-stu-id="9b340-433">Starting command: %1</span></span></td>
   <td><span data-ttu-id="9b340-434">Kommandot Startar svarskörning.</span><span class="sxs-lookup"><span data-stu-id="9b340-434">Starting response command execution.</span></span></td>
   <td><span data-ttu-id="9b340-435">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-435">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-436">60</span><span class="sxs-lookup"><span data-stu-id="9b340-436">60</span></span></td>
   <td><span data-ttu-id="9b340-437">Det gick inte att köra kommandot %1, fel: %2.</span><span class="sxs-lookup"><span data-stu-id="9b340-437">Failed to run command %1, error: %2.</span></span></td>
   <td><span data-ttu-id="9b340-438">Det gick inte att köra svarskommandot.</span><span class="sxs-lookup"><span data-stu-id="9b340-438">Failed to execute response command.</span></span></td>
   <td><span data-ttu-id="9b340-439">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="9b340-439">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-440">61</span><span class="sxs-lookup"><span data-stu-id="9b340-440">61</span></span></td>
   <td><span data-ttu-id="9b340-441">Parametrar för datainsamlingskommandon är ogiltiga: SasUri: %1, compressionLevel: %2.</span><span class="sxs-lookup"><span data-stu-id="9b340-441">Data collection command parameters are invalid: SasUri: %1, compressionLevel: %2.</span></span></td>
   <td><span data-ttu-id="9b340-442">Det gick inte att läsa eller tolka kommandoargumenten för datainsamling (ogiltiga argument).</span><span class="sxs-lookup"><span data-stu-id="9b340-442">Failed to read or parse the data collection command arguments (invalid arguments).</span></span></td>
   <td><span data-ttu-id="9b340-443">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="9b340-443">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-444">62</span><span class="sxs-lookup"><span data-stu-id="9b340-444">62</span></span></td>
   <td><span data-ttu-id="9b340-445">Det gick inte att starta den anslutna användarupplevelsen och telemetritjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-445">Failed to start Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="9b340-446">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="9b340-446">Failure code: %1</span></span></td>
   <td><span data-ttu-id="9b340-447">Anslutna användarupplevelser och den telemetriska tjänsten (diagtrack) kunde inte startas.</span><span class="sxs-lookup"><span data-stu-id="9b340-447">Connected User Experiences and Telemetry (diagtrack) service failed to start.</span></span> <span data-ttu-id="9b340-448">Telemetri med andra än Microsoft Defender för Slutpunkt-telemetri skickas inte från den här datorn.</span><span class="sxs-lookup"><span data-stu-id="9b340-448">Non-Microsoft Defender for Endpoint telemetry won't be sent from this machine.</span></span></td>
   <td><span data-ttu-id="9b340-449">Leta efter fler felsökningstips i händelseloggen: Microsoft-Windows-UniversalTelemetryClient/Operational.</span><span class="sxs-lookup"><span data-stu-id="9b340-449">Look for more troubleshooting hints in the event log: Microsoft-Windows-UniversalTelemetryClient/Operational.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-450">63</span><span class="sxs-lookup"><span data-stu-id="9b340-450">63</span></span></td>
   <td><span data-ttu-id="9b340-451">Uppdatera starttypen för extern tjänst.</span><span class="sxs-lookup"><span data-stu-id="9b340-451">Updating the start type of external service.</span></span> <span data-ttu-id="9b340-452">Namn: %1, verklig starttyp: %2, förväntad starttyp: %3, utgångskod: %4</span><span class="sxs-lookup"><span data-stu-id="9b340-452">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="9b340-453">Den externa tjänstens starttyp har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="9b340-453">Updated start type of the external service.</span></span></td>
   <td><span data-ttu-id="9b340-454">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-454">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-455">64</span><span class="sxs-lookup"><span data-stu-id="9b340-455">64</span></span></td>
   <td><span data-ttu-id="9b340-456">Starta den externa tjänsten som stoppas.</span><span class="sxs-lookup"><span data-stu-id="9b340-456">Starting stopped external service.</span></span> <span data-ttu-id="9b340-457">Namn: %1, utgångskod: %2</span><span class="sxs-lookup"><span data-stu-id="9b340-457">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="9b340-458">Starta en extern tjänst.</span><span class="sxs-lookup"><span data-stu-id="9b340-458">Starting an external service.</span></span></td>
   <td><span data-ttu-id="9b340-459">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-459">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-460">65</span><span class="sxs-lookup"><span data-stu-id="9b340-460">65</span></span></td>
   <td><span data-ttu-id="9b340-461">Det gick inte att läsa in minifilterdrivrutinen Microsoft Security Events Component.</span><span class="sxs-lookup"><span data-stu-id="9b340-461">Failed to load Microsoft Security Events Component Minifilter driver.</span></span> <span data-ttu-id="9b340-462">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="9b340-462">Failure code: %1</span></span></td>
   <td><span data-ttu-id="9b340-463">Det gick inte att MsSecFlt.sys av filsystems minifilter.</span><span class="sxs-lookup"><span data-stu-id="9b340-463">Failed to load MsSecFlt.sys filesystem minifilter.</span></span></td>
   <td><span data-ttu-id="9b340-464">Starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="9b340-464">Reboot the device.</span></span> <span data-ttu-id="9b340-465">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="9b340-465">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-466">66</span><span class="sxs-lookup"><span data-stu-id="9b340-466">66</span></span></td>
   <td><span data-ttu-id="9b340-467">Principuppdatering: Svarstidsläge – %1</span><span class="sxs-lookup"><span data-stu-id="9b340-467">Policy update: Latency mode - %1</span></span></td>
   <td><span data-ttu-id="9b340-468">Principen för&C-anslutningsfrekvensen uppdaterades.</span><span class="sxs-lookup"><span data-stu-id="9b340-468">The C&C connection frequency policy was updated.</span></span></td>
   <td><span data-ttu-id="9b340-469">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-469">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-470">68</span><span class="sxs-lookup"><span data-stu-id="9b340-470">68</span></span></td>
   <td><span data-ttu-id="9b340-471">Tjänstens starttyp är oväntad.</span><span class="sxs-lookup"><span data-stu-id="9b340-471">The start type of the service is unexpected.</span></span> <span data-ttu-id="9b340-472">Tjänstnamn: %1, verklig starttyp: %2, förväntad starttyp: %3</span><span class="sxs-lookup"><span data-stu-id="9b340-472">Service name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="9b340-473">Oväntad extern tjänststartstyp.</span><span class="sxs-lookup"><span data-stu-id="9b340-473">Unexpected external service start type.</span></span></td>
   <td><span data-ttu-id="9b340-474">Åtgärda den externa tjänstens starttyp.</span><span class="sxs-lookup"><span data-stu-id="9b340-474">Fix the external service start type.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-475">69</span><span class="sxs-lookup"><span data-stu-id="9b340-475">69</span></span></td>
   <td><span data-ttu-id="9b340-476">Tjänsten stoppas.</span><span class="sxs-lookup"><span data-stu-id="9b340-476">The service is stopped.</span></span> <span data-ttu-id="9b340-477">Tjänstnamn: %1</span><span class="sxs-lookup"><span data-stu-id="9b340-477">Service name: %1</span></span></td>
   <td><span data-ttu-id="9b340-478">Den externa tjänsten stoppas.</span><span class="sxs-lookup"><span data-stu-id="9b340-478">The external service is stopped.</span></span></td>
   <td><span data-ttu-id="9b340-479">Starta den externa tjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-479">Start the external service.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-480">70</span><span class="sxs-lookup"><span data-stu-id="9b340-480">70</span></span></td>
   <td><span data-ttu-id="9b340-481">Principuppdatering: Tillåt exempelsamling – %1</span><span class="sxs-lookup"><span data-stu-id="9b340-481">Policy update: Allow sample collection - %1</span></span></td>
   <td><span data-ttu-id="9b340-482">Exempelprincipen för samling har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="9b340-482">The sample collection policy was updated.</span></span></td>
   <td><span data-ttu-id="9b340-483">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-483">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-484">71</span><span class="sxs-lookup"><span data-stu-id="9b340-484">71</span></span></td>
   <td><span data-ttu-id="9b340-485">Kommandot Lyckades köra: %1</span><span class="sxs-lookup"><span data-stu-id="9b340-485">Succeeded to run command: %1</span></span></td>
   <td><span data-ttu-id="9b340-486">Kommandot kördes korrekt.</span><span class="sxs-lookup"><span data-stu-id="9b340-486">The command was executed successfully.</span></span></td>
   <td><span data-ttu-id="9b340-487">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-487">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-488">72</span><span class="sxs-lookup"><span data-stu-id="9b340-488">72</span></span></td>
   <td><span data-ttu-id="9b340-489">Försökte skicka den första fullständiga datorprofilrapporten.</span><span class="sxs-lookup"><span data-stu-id="9b340-489">Tried to send first full machine profile report.</span></span> <span data-ttu-id="9b340-490">Resultatkod: %1</span><span class="sxs-lookup"><span data-stu-id="9b340-490">Result code: %1</span></span></td>
   <td><span data-ttu-id="9b340-491">Endast information.</span><span class="sxs-lookup"><span data-stu-id="9b340-491">Informational only.</span></span></td>
   <td><span data-ttu-id="9b340-492">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-492">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-493">73</span><span class="sxs-lookup"><span data-stu-id="9b340-493">73</span></span></td>
   <td><span data-ttu-id="9b340-494">Start för plattform: %1</span><span class="sxs-lookup"><span data-stu-id="9b340-494">Sense starting for platform: %1</span></span></td>
   <td><span data-ttu-id="9b340-495">Endast information.</span><span class="sxs-lookup"><span data-stu-id="9b340-495">Informational only.</span></span></td>
   <td><span data-ttu-id="9b340-496">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-496">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-497">74</span><span class="sxs-lookup"><span data-stu-id="9b340-497">74</span></span></td>
   <td><span data-ttu-id="9b340-498">Enhetstaggen i registret överskrider längdgränsen.</span><span class="sxs-lookup"><span data-stu-id="9b340-498">Device tag in registry exceeds length limit.</span></span> <span data-ttu-id="9b340-499">Taggnamn: %2.</span><span class="sxs-lookup"><span data-stu-id="9b340-499">Tag name: %2.</span></span> <span data-ttu-id="9b340-500">Längdbegränsning: %1.</span><span class="sxs-lookup"><span data-stu-id="9b340-500">Length limit: %1.</span></span></td>
   <td><span data-ttu-id="9b340-501">Enhetstaggen överskrider längdgränsen.</span><span class="sxs-lookup"><span data-stu-id="9b340-501">The device tag exceeds the length limit.</span></span></td>
   <td><span data-ttu-id="9b340-502">Använd en kortare enhetstagg.</span><span class="sxs-lookup"><span data-stu-id="9b340-502">Use a shorter device tag.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-503">81</span><span class="sxs-lookup"><span data-stu-id="9b340-503">81</span></span></td>
   <td><span data-ttu-id="9b340-504">Det gick inte att skapa Microsoft Defender för slutpunkt ETW – automatisklogg.</span><span class="sxs-lookup"><span data-stu-id="9b340-504">Failed to create Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="9b340-505">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="9b340-505">Failure code: %1</span></span></td>
   <td><span data-ttu-id="9b340-506">Det gick inte att skapa ETW-sessionen.</span><span class="sxs-lookup"><span data-stu-id="9b340-506">Failed to create the ETW session.</span></span></td>
   <td><span data-ttu-id="9b340-507">Starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="9b340-507">Reboot the device.</span></span> <span data-ttu-id="9b340-508">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="9b340-508">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-509">82</span><span class="sxs-lookup"><span data-stu-id="9b340-509">82</span></span></td>
   <td><span data-ttu-id="9b340-510">Det gick inte att ta bort Microsoft Defender för endpoint ETW autologger.</span><span class="sxs-lookup"><span data-stu-id="9b340-510">Failed to remove Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="9b340-511">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="9b340-511">Failure code: %1</span></span></td>
   <td><span data-ttu-id="9b340-512">Det gick inte att ta bort ETW-sessionen.</span><span class="sxs-lookup"><span data-stu-id="9b340-512">Failed to delete the ETW session.</span></span></td>
   <td><span data-ttu-id="9b340-513">Kontakta support.</span><span class="sxs-lookup"><span data-stu-id="9b340-513">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-514">84</span><span class="sxs-lookup"><span data-stu-id="9b340-514">84</span></span></td>
   <td><span data-ttu-id="9b340-515">Ange att Windows Defender Antivirus körs.</span><span class="sxs-lookup"><span data-stu-id="9b340-515">Set Windows Defender Antivirus running mode.</span></span> <span data-ttu-id="9b340-516">Tvinga passivt läge: %1, resultatkod: %2.</span><span class="sxs-lookup"><span data-stu-id="9b340-516">Force passive mode: %1, result code: %2.</span></span></td>
   <td><span data-ttu-id="9b340-517">Ställa in defender running mode (aktivt eller passivt).</span><span class="sxs-lookup"><span data-stu-id="9b340-517">Set defender running mode (active or passive).</span></span></td>
   <td><span data-ttu-id="9b340-518">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-518">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-519">85</span><span class="sxs-lookup"><span data-stu-id="9b340-519">85</span></span></td>
   <td><span data-ttu-id="9b340-520">Det gick inte att utlösa Microsoft Defender för körbar slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="9b340-520">Failed to trigger Microsoft Defender for Endpoint executable.</span></span> <span data-ttu-id="9b340-521">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="9b340-521">Failure code: %1</span></span></td>
   <td><span data-ttu-id="9b340-522">Körbar Stjärn senseIR misslyckades.</span><span class="sxs-lookup"><span data-stu-id="9b340-522">Starring SenseIR executable failed.</span></span></td>
   <td><span data-ttu-id="9b340-523">Starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="9b340-523">Reboot the device.</span></span> <span data-ttu-id="9b340-524">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="9b340-524">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-525">86</span><span class="sxs-lookup"><span data-stu-id="9b340-525">86</span></span></td>
   <td><span data-ttu-id="9b340-526">Starta igen, stoppad extern tjänst som ska vara upp.</span><span class="sxs-lookup"><span data-stu-id="9b340-526">Starting again stopped external service that should be up.</span></span> <span data-ttu-id="9b340-527">Namn: %1, utgångskod: %2</span><span class="sxs-lookup"><span data-stu-id="9b340-527">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="9b340-528">Starta den externa tjänsten igen.</span><span class="sxs-lookup"><span data-stu-id="9b340-528">Starting the external service again.</span></span></td>
   <td><span data-ttu-id="9b340-529">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-529">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-530">87</span><span class="sxs-lookup"><span data-stu-id="9b340-530">87</span></span></td>
   <td><span data-ttu-id="9b340-531">Det går inte att starta den externa tjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-531">Cannot start the external service.</span></span> <span data-ttu-id="9b340-532">Namn: %1</span><span class="sxs-lookup"><span data-stu-id="9b340-532">Name: %1</span></span></td>
   <td><span data-ttu-id="9b340-533">Det gick inte att starta den externa tjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-533">Failed to start the external service.</span></span></td>
   <td><span data-ttu-id="9b340-534">Kontakta support.</span><span class="sxs-lookup"><span data-stu-id="9b340-534">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-535">88</span><span class="sxs-lookup"><span data-stu-id="9b340-535">88</span></span></td>
   <td><span data-ttu-id="9b340-536">Uppdatera starttypen för den externa tjänsten igen.</span><span class="sxs-lookup"><span data-stu-id="9b340-536">Updating the start type of external service again.</span></span> <span data-ttu-id="9b340-537">Namn: %1, verklig starttyp: %2, förväntad starttyp: %3, utgångskod: %4</span><span class="sxs-lookup"><span data-stu-id="9b340-537">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="9b340-538">Uppdaterade starttypen för den externa tjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-538">Updated the start type of the external service.</span></span></td>
   <td><span data-ttu-id="9b340-539">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-539">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-540">89</span><span class="sxs-lookup"><span data-stu-id="9b340-540">89</span></span></td>
   <td><span data-ttu-id="9b340-541">Det går inte att uppdatera starttypen för extern tjänst.</span><span class="sxs-lookup"><span data-stu-id="9b340-541">Cannot update the start type of external service.</span></span> <span data-ttu-id="9b340-542">Namn: %1, verklig starttyp: %2, förväntad starttyp: %3</span><span class="sxs-lookup"><span data-stu-id="9b340-542">Name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="9b340-543">Det går inte att uppdatera starttypen för den externa tjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-543">Can't update the start type of the external service.</span></span></td>
   <td><span data-ttu-id="9b340-544">Kontakta support.</span><span class="sxs-lookup"><span data-stu-id="9b340-544">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-545">90</span><span class="sxs-lookup"><span data-stu-id="9b340-545">90</span></span></td>
   <td><span data-ttu-id="9b340-546">Det gick inte att konfigurera System Guard Runtime Monitor för att ansluta till molntjänsten i geoområde %1.</span><span class="sxs-lookup"><span data-stu-id="9b340-546">Failed to configure System Guard Runtime Monitor to connect to cloud service in geo-region %1.</span></span> <span data-ttu-id="9b340-547">Felkod: %2</span><span class="sxs-lookup"><span data-stu-id="9b340-547">Failure code: %2</span></span></td>
   <td><span data-ttu-id="9b340-548">System Guard Runtime Monitor skickar inte attestationsdata till molntjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-548">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="9b340-549">Kontrollera behörigheterna för registersökvägen: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="9b340-549">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="9b340-550">Kontakta support om det inte är några problem.</span><span class="sxs-lookup"><span data-stu-id="9b340-550">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-551">91</span><span class="sxs-lookup"><span data-stu-id="9b340-551">91</span></span></td>
   <td><span data-ttu-id="9b340-552">Det gick inte att ta bort System Guard Runtime Monitor-information för geoområde.</span><span class="sxs-lookup"><span data-stu-id="9b340-552">Failed to remove System Guard Runtime Monitor geo-region information.</span></span> <span data-ttu-id="9b340-553">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="9b340-553">Failure code: %1</span></span></td>
   <td><span data-ttu-id="9b340-554">System Guard Runtime Monitor skickar inte attestationsdata till molntjänsten.</span><span class="sxs-lookup"><span data-stu-id="9b340-554">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="9b340-555">Kontrollera behörigheterna för registersökvägen: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="9b340-555">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="9b340-556">Kontakta support om det inte är några problem.</span><span class="sxs-lookup"><span data-stu-id="9b340-556">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-557">92</span><span class="sxs-lookup"><span data-stu-id="9b340-557">92</span></span></td>
   <td><span data-ttu-id="9b340-558">Stoppar sändning av sensordatakvot på cyber, eftersom datakvoten överskrids.</span><span class="sxs-lookup"><span data-stu-id="9b340-558">Stopping sending sensor cyber data quota because data quota is exceeded.</span></span> <span data-ttu-id="9b340-559">Återupptar sändningen när kvotperioden går ut.</span><span class="sxs-lookup"><span data-stu-id="9b340-559">Will resume sending once quota period passes.</span></span> <span data-ttu-id="9b340-560">Tillståndsmask: %1</span><span class="sxs-lookup"><span data-stu-id="9b340-560">State Mask: %1</span></span></td>
   <td><span data-ttu-id="9b340-561">Överskrid begränsningsgräns.</span><span class="sxs-lookup"><span data-stu-id="9b340-561">Exceed throttling limit.</span></span></td>
   <td><span data-ttu-id="9b340-562">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-562">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-563">93</span><span class="sxs-lookup"><span data-stu-id="9b340-563">93</span></span></td>
   <td><span data-ttu-id="9b340-564">Återupptar sändning av sensordata i cybern.</span><span class="sxs-lookup"><span data-stu-id="9b340-564">Resuming sending sensor cyber data.</span></span> <span data-ttu-id="9b340-565">Tillståndsmask: %1</span><span class="sxs-lookup"><span data-stu-id="9b340-565">State Mask: %1</span></span></td>
   <td><span data-ttu-id="9b340-566">Återuppta sändning av cyberdata.</span><span class="sxs-lookup"><span data-stu-id="9b340-566">Resume cyber data submission.</span></span></td>
   <td><span data-ttu-id="9b340-567">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-567">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-568">94</span><span class="sxs-lookup"><span data-stu-id="9b340-568">94</span></span></td>
   <td><span data-ttu-id="9b340-569">Körbar Microsoft Defender för slutpunkt har startat</span><span class="sxs-lookup"><span data-stu-id="9b340-569">Microsoft Defender for Endpoint executable has started</span></span></td>
   <td><span data-ttu-id="9b340-570">Den körbara SenseCE-filen har startat.</span><span class="sxs-lookup"><span data-stu-id="9b340-570">The SenseCE executable has started.</span></span></td>
   <td><span data-ttu-id="9b340-571">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-571">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-572">95</span><span class="sxs-lookup"><span data-stu-id="9b340-572">95</span></span></td>
   <td><span data-ttu-id="9b340-573">Körbar Microsoft Defender för slutpunkt har avslutats</span><span class="sxs-lookup"><span data-stu-id="9b340-573">Microsoft Defender for Endpoint executable has ended</span></span></td>
   <td><span data-ttu-id="9b340-574">Den körbara SenseCE-filen har avslutats.</span><span class="sxs-lookup"><span data-stu-id="9b340-574">The SenseCE executable has ended.</span></span></td>
   <td><span data-ttu-id="9b340-575">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-575">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-576">96</span><span class="sxs-lookup"><span data-stu-id="9b340-576">96</span></span></td>
   <td><span data-ttu-id="9b340-577">Microsoft Defender för Slutpunkt Init har anropats.</span><span class="sxs-lookup"><span data-stu-id="9b340-577">Microsoft Defender for Endpoint Init has called.</span></span> <span data-ttu-id="9b340-578">Resultatkod: %2</span><span class="sxs-lookup"><span data-stu-id="9b340-578">Result code: %2</span></span></td>
   <td><span data-ttu-id="9b340-579">Den körbara SenseCE-filen har kallat MCE-initiering.</span><span class="sxs-lookup"><span data-stu-id="9b340-579">The SenseCE executable has called MCE initialization.</span></span></td>
   <td><span data-ttu-id="9b340-580">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-580">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-581">97</span><span class="sxs-lookup"><span data-stu-id="9b340-581">97</span></span></td>
   <td><span data-ttu-id="9b340-582">Det finns anslutningsproblem till molnet för DLP-scenariot</span><span class="sxs-lookup"><span data-stu-id="9b340-582">There are connectivity issues to the Cloud for the DLP scenario</span></span></td>
   <td><span data-ttu-id="9b340-583">Det finns nätverksanslutningsproblem som påverkar DLP-klassificeringsflödet.</span><span class="sxs-lookup"><span data-stu-id="9b340-583">There are network connectivity issues that affect the DLP classification flow.</span></span></td>
   <td><span data-ttu-id="9b340-584">Kontrollera nätverksanslutningen.</span><span class="sxs-lookup"><span data-stu-id="9b340-584">Check the network connectivity.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-585">98</span><span class="sxs-lookup"><span data-stu-id="9b340-585">98</span></span></td>
   <td><span data-ttu-id="9b340-586">Anslutningen till molnet för DLP-scenariot har återställts</span><span class="sxs-lookup"><span data-stu-id="9b340-586">The connectivity to the Cloud for the DLP scenario has been restored</span></span></td>
   <td><span data-ttu-id="9b340-587">Anslutningen till nätverket återställdes och DLP-klassificeringsflödet kan fortsätta.</span><span class="sxs-lookup"><span data-stu-id="9b340-587">The connectivity to the network was restored and the DLP classification flow can continue.</span></span></td>
   <td><span data-ttu-id="9b340-588">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-588">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-589">99</span><span class="sxs-lookup"><span data-stu-id="9b340-589">99</span></span></td>
   <td><span data-ttu-id="9b340-590">Fel i Sense har uppstått när du kommunicerar med server: (%1).</span><span class="sxs-lookup"><span data-stu-id="9b340-590">Sense has encountered the following error while communicating with server: (%1).</span></span> <span data-ttu-id="9b340-591">Resultat: (%2)</span><span class="sxs-lookup"><span data-stu-id="9b340-591">Result: (%2)</span></span></td>
   <td><span data-ttu-id="9b340-592">Ett kommunikationsfel inträffade.</span><span class="sxs-lookup"><span data-stu-id="9b340-592">A communication error occurred.</span></span></td>
   <td><span data-ttu-id="9b340-593">Mer information finns i följande händelser i händelseloggen.</span><span class="sxs-lookup"><span data-stu-id="9b340-593">Check the following events in the event log for further details.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-594">100</span><span class="sxs-lookup"><span data-stu-id="9b340-594">100</span></span></td>
   <td><span data-ttu-id="9b340-595">Körbar Microsoft Defender för slutpunkt kunde inte starta.</span><span class="sxs-lookup"><span data-stu-id="9b340-595">Microsoft Defender for Endpoint executable failed to start.</span></span> <span data-ttu-id="9b340-596">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="9b340-596">Failure code: %1</span></span></td>
   <td><span data-ttu-id="9b340-597">Det gick inte att starta SenseCE-körbara filer.</span><span class="sxs-lookup"><span data-stu-id="9b340-597">The SenseCE executable has failed to start.</span></span></td>
   <td><span data-ttu-id="9b340-598">Starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="9b340-598">Reboot the device.</span></span> <span data-ttu-id="9b340-599">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="9b340-599">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-600">102</span><span class="sxs-lookup"><span data-stu-id="9b340-600">102</span></span></td>
   <td><span data-ttu-id="9b340-601">Körbar microsoft Defender för slutpunktsnätverksidentifiering och svar har startat</span><span class="sxs-lookup"><span data-stu-id="9b340-601">Microsoft Defender for Endpoint Network Detection and Response executable has started</span></span></td>
   <td><span data-ttu-id="9b340-602">Körbar SenseNdr har startat.</span><span class="sxs-lookup"><span data-stu-id="9b340-602">The SenseNdr executable has started.</span></span></td>
   <td><span data-ttu-id="9b340-603">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-603">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="9b340-604">103</span><span class="sxs-lookup"><span data-stu-id="9b340-604">103</span></span></td>
   <td><span data-ttu-id="9b340-605">Microsoft Defender för slutpunkt nätverksidentifiering och svar körbar fil har avslutats</span><span class="sxs-lookup"><span data-stu-id="9b340-605">Microsoft Defender for Endpoint Network Detection and Response executable has ended</span></span></td>
   <td><span data-ttu-id="9b340-606">Den körbara SenseNdr-filen har avslutats.</span><span class="sxs-lookup"><span data-stu-id="9b340-606">The SenseNdr executable has ended.</span></span></td>
   <td><span data-ttu-id="9b340-607">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="9b340-607">Normal operating notification; no action required.</span></span></td>
</tr>
</tbody>
</table>

><span data-ttu-id="9b340-608">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="9b340-608">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9b340-609">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="9b340-609">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="9b340-610">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="9b340-610">Related topics</span></span>
- [<span data-ttu-id="9b340-611">Registrera Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="9b340-611">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="9b340-612">Konfigurera enhetsproxy och internetanslutningsinställningar</span><span class="sxs-lookup"><span data-stu-id="9b340-612">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="9b340-613">Felsöka Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="9b340-613">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
