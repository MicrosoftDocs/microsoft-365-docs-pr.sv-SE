---
title: Granska händelser och fel med hjälp av Loggboken
description: Få beskrivningar och ytterligare felsökningssteg (om det behövs) för alla händelser som rapporterats av Microsoft Defender för slutpunktstjänsten.
keywords: felsökning, händelsevisningsprogram, loggsammanfattning, felkod, misslyckades, Microsoft Defender för slutpunktstjänsten, kan inte starta, brutna, kan inte starta
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
ms.openlocfilehash: 98c0f790c228989b261b95f3b87cdc9d18e4fa76
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076618"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="1476d-104">Granska händelser och fel med hjälp av Loggboken</span><span class="sxs-lookup"><span data-stu-id="1476d-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1476d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1476d-105">**Applies to:**</span></span>
- <span data-ttu-id="1476d-106">Loggboken</span><span class="sxs-lookup"><span data-stu-id="1476d-106">Event Viewer</span></span>
- [<span data-ttu-id="1476d-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1476d-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="1476d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1476d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1476d-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1476d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1476d-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="1476d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="1476d-111">Du kan granska händelse-IDt i [Loggboken](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) på enskilda enheter.</span><span class="sxs-lookup"><span data-stu-id="1476d-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="1476d-112">Om enheter inte visas i listan Enheter kan du till exempel behöva leta efter händelse-ID på enheterna.</span><span class="sxs-lookup"><span data-stu-id="1476d-112">For example, if devices are not appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="1476d-113">Du kan sedan använda tabellen för att fastställa ytterligare felsökningssteg.</span><span class="sxs-lookup"><span data-stu-id="1476d-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="1476d-114">**Öppna Loggboken och hitta Microsoft Defender för slutpunktens händelselogg för tjänsten:**</span><span class="sxs-lookup"><span data-stu-id="1476d-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="1476d-115">Klicka **på Start** på Windows-menyn, skriv **Loggboken** och tryck på **Retur.**</span><span class="sxs-lookup"><span data-stu-id="1476d-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="1476d-116">Bläddra i logglistan under **Loggsammanfattning** tills du ser **Microsoft-Windows-SENSE/Operational**.</span><span class="sxs-lookup"><span data-stu-id="1476d-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="1476d-117">Dubbelklicka på objektet för att öppna loggen.</span><span class="sxs-lookup"><span data-stu-id="1476d-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="1476d-118">a.</span><span class="sxs-lookup"><span data-stu-id="1476d-118">a.</span></span>  <span data-ttu-id="1476d-119">Du kan också öppna loggen genom att expandera **Program och tjänstloggar**  >  **Microsoft**  >  **Windows**  >  **SENSE och** klicka på **Drift.**</span><span class="sxs-lookup"><span data-stu-id="1476d-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1476d-120">SENSE är det interna namn som används för att referera till den beteende sensor som driver Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1476d-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="1476d-121">Händelser som registreras av tjänsten visas i loggen.</span><span class="sxs-lookup"><span data-stu-id="1476d-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="1476d-122">I följande tabell finns en lista över händelser som registrerats av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="1476d-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="1476d-123">Händelse-ID</span><span class="sxs-lookup"><span data-stu-id="1476d-123">Event ID</span></span></th>
<th><span data-ttu-id="1476d-124">Meddelande</span><span class="sxs-lookup"><span data-stu-id="1476d-124">Message</span></span></th>
<th><span data-ttu-id="1476d-125">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1476d-125">Description</span></span></th>
<th><span data-ttu-id="1476d-126">Åtgärd</span><span class="sxs-lookup"><span data-stu-id="1476d-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="1476d-127">1</span><span class="sxs-lookup"><span data-stu-id="1476d-127">1</span></span></td>
<td><span data-ttu-id="1476d-128">Microsoft Defender för slutpunktstjänsten startades (version <code>variable</code> ).</span><span class="sxs-lookup"><span data-stu-id="1476d-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="1476d-129">Inträffar under systemstart, avstängning och vid start av tavlor.</span><span class="sxs-lookup"><span data-stu-id="1476d-129">Occurs during system start up, shut down, and during onbboarding.</span></span></td>
<td><span data-ttu-id="1476d-130">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="1476d-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-131">2</span><span class="sxs-lookup"><span data-stu-id="1476d-131">2</span></span></td>
<td><span data-ttu-id="1476d-132">Microsoft Defender för Endpoint-tjänsten stängs av.</span><span class="sxs-lookup"><span data-stu-id="1476d-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="1476d-133">Inträffar när enheten stängs av eller stängs av.</span><span class="sxs-lookup"><span data-stu-id="1476d-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="1476d-134">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="1476d-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-135">3</span><span class="sxs-lookup"><span data-stu-id="1476d-135">3</span></span></td>
<td><span data-ttu-id="1476d-136">Microsoft Defender för Slutpunkt-tjänsten kunde inte startas.</span><span class="sxs-lookup"><span data-stu-id="1476d-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="1476d-137">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-138">Tjänsten har inte startar.</span><span class="sxs-lookup"><span data-stu-id="1476d-138">Service did not start.</span></span></td>
<td><span data-ttu-id="1476d-139">Granska andra meddelanden för att fastställa möjliga orsaker och felsökningssteg.</span><span class="sxs-lookup"><span data-stu-id="1476d-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-140">4</span><span class="sxs-lookup"><span data-stu-id="1476d-140">4</span></span></td>
<td><span data-ttu-id="1476d-141">Microsoft Defender för Slutpunkt-tjänsten kontaktade servern på <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-142">Variabel = URL för Defender för slutpunktsbearbetningsservrar.</span><span class="sxs-lookup"><span data-stu-id="1476d-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="1476d-143">Den här URL:en matchar den som visas i brandväggen eller nätverksaktiviteten.</span><span class="sxs-lookup"><span data-stu-id="1476d-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="1476d-144">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="1476d-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-145">5</span><span class="sxs-lookup"><span data-stu-id="1476d-145">5</span></span></td>
<td><span data-ttu-id="1476d-146">Microsoft Defender för slutpunktstjänsten kunde inte ansluta till servern hos <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-147">Variabel = URL för Defender för slutpunktsbearbetningsservrar.</span><span class="sxs-lookup"><span data-stu-id="1476d-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="1476d-148">Det gick inte att kontakta den externa bearbetningsservrarna på den URL:en.</span><span class="sxs-lookup"><span data-stu-id="1476d-148">The service could not contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="1476d-149">Kontrollera anslutningen till URL:en.</span><span class="sxs-lookup"><span data-stu-id="1476d-149">Check the connection to the URL.</span></span> <span data-ttu-id="1476d-150">Se <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Konfigurera proxy och Internetanslutning.</a></span><span class="sxs-lookup"><span data-stu-id="1476d-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-151">6</span><span class="sxs-lookup"><span data-stu-id="1476d-151">6</span></span></td>
<td><span data-ttu-id="1476d-152">Microsoft Defender för Slutpunkt-tjänsten är inte onboarded och inga onboarding-parametrar hittades.</span><span class="sxs-lookup"><span data-stu-id="1476d-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="1476d-153">Enheten onboardly inte korrekt och kommer inte att rapportera till portalen.</span><span class="sxs-lookup"><span data-stu-id="1476d-153">The device did not onboard correctly and will not be reporting to the portal.</span></span></td>
<td><span data-ttu-id="1476d-154">Onboarding måste köras innan tjänsten startas.</span><span class="sxs-lookup"><span data-stu-id="1476d-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="1476d-155">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="1476d-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="1476d-156">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="1476d-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="1476d-157">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="1476d-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-158">7</span><span class="sxs-lookup"><span data-stu-id="1476d-158">7</span></span></td>
<td><span data-ttu-id="1476d-159">Microsoft Defender för slutpunktstjänsten kunde inte läsa onboarding-parametrarna.</span><span class="sxs-lookup"><span data-stu-id="1476d-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="1476d-160">Fel: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-161">Variabel = detaljerad felbeskrivning.</span><span class="sxs-lookup"><span data-stu-id="1476d-161">Variable = detailed error description.</span></span> <span data-ttu-id="1476d-162">Enheten onboardly inte korrekt och kommer inte att rapportera till portalen.</span><span class="sxs-lookup"><span data-stu-id="1476d-162">The device did not onboard correctly and will not be reporting to the portal.</span></span></td>
<td><span data-ttu-id="1476d-163">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="1476d-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="1476d-164">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="1476d-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="1476d-165">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="1476d-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-166">8</span><span class="sxs-lookup"><span data-stu-id="1476d-166">8</span></span></td>
<td><span data-ttu-id="1476d-167">Microsoft Defender för slutpunktstjänsten kunde inte rensa konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="1476d-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="1476d-168">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-169"><b>Under introduktionen:</b> Det gick inte att rensa konfigurationen av tjänsten under onboarding.</span><span class="sxs-lookup"><span data-stu-id="1476d-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="1476d-170">Onboarding-processen fortsätter.</span><span class="sxs-lookup"><span data-stu-id="1476d-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="1476d-171"><b>Under offboarding:</b> Tjänsten kunde inte rensa konfigurationen under offboarding.</span><span class="sxs-lookup"><span data-stu-id="1476d-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="1476d-172">Offboarding-processen har slutförts men tjänsten fortsätter att köras.</span><span class="sxs-lookup"><span data-stu-id="1476d-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="1476d-173"><b>Introduktion:</b> Ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="1476d-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="1476d-174"><b>Offboarding:</b> Starta om systemet.</span><span class="sxs-lookup"><span data-stu-id="1476d-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="1476d-175">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="1476d-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-176">9</span><span class="sxs-lookup"><span data-stu-id="1476d-176">9</span></span></td>
<td><span data-ttu-id="1476d-177">Microsoft Defender för slutpunktstjänsten kunde inte ändra starttypen.</span><span class="sxs-lookup"><span data-stu-id="1476d-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="1476d-178">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-179"><b>Under introduktionen:</b> Enheten onboardly inte korrekt och kommer inte att rapportera till portalen.</span><span class="sxs-lookup"><span data-stu-id="1476d-179"><b>During onboarding:</b> The device did not onboard correctly and will not be reporting to the portal.</span></span> <br><br><span data-ttu-id="1476d-180"><b>Under offboarding:</b> Det gick inte att ändra tjänstens starttyp.</span><span class="sxs-lookup"><span data-stu-id="1476d-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="1476d-181">Offboarding-processen fortsätter.</span><span class="sxs-lookup"><span data-stu-id="1476d-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="1476d-182">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="1476d-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="1476d-183">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="1476d-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="1476d-184">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="1476d-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-185">10</span><span class="sxs-lookup"><span data-stu-id="1476d-185">10</span></span></td>
<td><span data-ttu-id="1476d-186">Microsoft Defender för slutpunktstjänsten kunde inte spara informationen om introduktionen.</span><span class="sxs-lookup"><span data-stu-id="1476d-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="1476d-187">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-188">Enheten onboardly inte korrekt och kommer inte att rapportera till portalen.</span><span class="sxs-lookup"><span data-stu-id="1476d-188">The device did not onboard correctly and will not be reporting to the portal.</span></span></td>
<td><span data-ttu-id="1476d-189">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="1476d-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="1476d-190">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="1476d-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="1476d-191">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="1476d-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-192">11</span><span class="sxs-lookup"><span data-stu-id="1476d-192">11</span></span></td>
<td><span data-ttu-id="1476d-193">Registrering eller om onboarding av Defender för slutpunktstjänsten har slutförts.</span><span class="sxs-lookup"><span data-stu-id="1476d-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="1476d-194">Enheten var korrekt igång.</span><span class="sxs-lookup"><span data-stu-id="1476d-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="1476d-195">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="1476d-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="1476d-196">Det kan ta flera timmar innan enheten visas i portalen.</span><span class="sxs-lookup"><span data-stu-id="1476d-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-197">12</span><span class="sxs-lookup"><span data-stu-id="1476d-197">12</span></span></td>
<td><span data-ttu-id="1476d-198">Standardkonfigurationen kunde inte användas i Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1476d-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="1476d-199">Det gick inte att använda standardkonfigurationen för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="1476d-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="1476d-200">Det här felet bör åtgärdas efter en kort tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="1476d-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-201">13</span><span class="sxs-lookup"><span data-stu-id="1476d-201">13</span></span></td>
<td><span data-ttu-id="1476d-202">Microsoft Defender för slutpunktens enhets-ID beräknat: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-203">Normal driftprocess.</span><span class="sxs-lookup"><span data-stu-id="1476d-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="1476d-204">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="1476d-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-205">15</span><span class="sxs-lookup"><span data-stu-id="1476d-205">15</span></span></td>
<td><span data-ttu-id="1476d-206">Microsoft Defender för Slutpunkt kan inte starta kommandokanalen med URL: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-207">Variabel = URL för Defender för slutpunktsbearbetningsservrar.</span><span class="sxs-lookup"><span data-stu-id="1476d-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="1476d-208">Det gick inte att kontakta den externa bearbetningsservrarna på den URL:en.</span><span class="sxs-lookup"><span data-stu-id="1476d-208">The service could not contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="1476d-209">Kontrollera anslutningen till URL:en.</span><span class="sxs-lookup"><span data-stu-id="1476d-209">Check the connection to the URL.</span></span> <span data-ttu-id="1476d-210">Se <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Konfigurera proxy och Internetanslutning.</a></span><span class="sxs-lookup"><span data-stu-id="1476d-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-211">17</span><span class="sxs-lookup"><span data-stu-id="1476d-211">17</span></span></td>
<td><span data-ttu-id="1476d-212">Microsoft Defender för slutpunktstjänsten kunde inte ändra plats för anslutna användarupplevelser och telemetritjänster.</span><span class="sxs-lookup"><span data-stu-id="1476d-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="1476d-213">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-214">Ett fel uppstod med Windows-telemetritjänsten.</span><span class="sxs-lookup"><span data-stu-id="1476d-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="1476d-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Kontrollera att diagnostikdatatjänsten är aktiverad.</a></span><span class="sxs-lookup"><span data-stu-id="1476d-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="1476d-216">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="1476d-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="1476d-217">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="1476d-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="1476d-218">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="1476d-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-219">18</span><span class="sxs-lookup"><span data-stu-id="1476d-219">18</span></span></td>
<td><span data-ttu-id="1476d-220">OOBE (Välkommen i Windows) har slutförts.</span><span class="sxs-lookup"><span data-stu-id="1476d-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="1476d-221">Tjänsten startar först när Windows-uppdateringarna har installerats.</span><span class="sxs-lookup"><span data-stu-id="1476d-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="1476d-222">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="1476d-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-223">19</span><span class="sxs-lookup"><span data-stu-id="1476d-223">19</span></span></td>
<td><span data-ttu-id="1476d-224">OOBE (Välkommen i Windows) har ännu inte slutförts.</span><span class="sxs-lookup"><span data-stu-id="1476d-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="1476d-225">Tjänsten startar först när Windows-uppdateringarna har installerats.</span><span class="sxs-lookup"><span data-stu-id="1476d-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="1476d-226">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="1476d-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="1476d-227">Om det här felet kvarstår efter en omstart av systemet bör du kontrollera att alla Windows-uppdateringar har installerats.</span><span class="sxs-lookup"><span data-stu-id="1476d-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-228">20</span><span class="sxs-lookup"><span data-stu-id="1476d-228">20</span></span></td>
<td><span data-ttu-id="1476d-229">Det går inte att vänta på att OOBE (Välkommen i Windows) ska slutföras.</span><span class="sxs-lookup"><span data-stu-id="1476d-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="1476d-230">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-231">Internt fel.</span><span class="sxs-lookup"><span data-stu-id="1476d-231">Internal error.</span></span></td>
<td><span data-ttu-id="1476d-232">Om det här felet kvarstår efter en omstart av systemet bör du kontrollera att alla Windows-uppdateringar har installerats.</span><span class="sxs-lookup"><span data-stu-id="1476d-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-233">25</span><span class="sxs-lookup"><span data-stu-id="1476d-233">25</span></span></td>
<td><span data-ttu-id="1476d-234">Microsoft Defender för Slutpunkt-tjänsten kunde inte återställa hälsostatus i registret.</span><span class="sxs-lookup"><span data-stu-id="1476d-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="1476d-235">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-236">Enheten kunde inte introduceras på rätt sätt.</span><span class="sxs-lookup"><span data-stu-id="1476d-236">The device did not onboard correctly.</span></span>
<span data-ttu-id="1476d-237">Den rapporterar till portalen, men tjänsten kanske inte visas som registrerad i SCCM eller registret.</span><span class="sxs-lookup"><span data-stu-id="1476d-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="1476d-238">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="1476d-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="1476d-239">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="1476d-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="1476d-240">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="1476d-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-241">26</span><span class="sxs-lookup"><span data-stu-id="1476d-241">26</span></span></td>
<td><span data-ttu-id="1476d-242">Microsoft Defender för slutpunktstjänsten kunde inte ange registreringsstatus i registret.</span><span class="sxs-lookup"><span data-stu-id="1476d-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="1476d-243">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-244">Enheten kunde inte introduceras på rätt sätt.</span><span class="sxs-lookup"><span data-stu-id="1476d-244">The device did not onboard correctly.</span></span><br>
<span data-ttu-id="1476d-245">Den rapporterar till portalen, men tjänsten kanske inte visas som registrerad i SCCM eller registret.</span><span class="sxs-lookup"><span data-stu-id="1476d-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="1476d-246">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="1476d-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="1476d-247">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="1476d-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="1476d-248">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="1476d-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-249">27</span><span class="sxs-lookup"><span data-stu-id="1476d-249">27</span></span></td>
<td><span data-ttu-id="1476d-250">Microsoft Defender för slutpunktstjänsten kunde inte aktivera SENSE-läge i Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="1476d-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="1476d-251">Onboarding-processen misslyckades.</span><span class="sxs-lookup"><span data-stu-id="1476d-251">Onboarding process failed.</span></span> <span data-ttu-id="1476d-252">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-253">Normalt inger Microsoft Defender Antivirus ett särskilt passivt läge om en annan antimalwareprodukt i realtid körs korrekt på enheten och enheten rapporterar till Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1476d-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="1476d-254">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="1476d-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="1476d-255">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="1476d-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="1476d-256">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="1476d-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="1476d-257">Se till att skydd mot skadlig programvara i realtid fungerar som det ska.</span><span class="sxs-lookup"><span data-stu-id="1476d-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-258">28</span><span class="sxs-lookup"><span data-stu-id="1476d-258">28</span></span></td>
<td><span data-ttu-id="1476d-259">Microsoft Defender för slutpunktsanslutna användarupplevelser och registrering av telemetritjänster misslyckades.</span><span class="sxs-lookup"><span data-stu-id="1476d-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="1476d-260">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-261">Ett fel uppstod med Windows-telemetritjänsten.</span><span class="sxs-lookup"><span data-stu-id="1476d-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="1476d-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Kontrollera att diagnostikdatatjänsten är aktiverad.</a></span><span class="sxs-lookup"><span data-stu-id="1476d-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="1476d-263">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="1476d-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="1476d-264">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="1476d-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="1476d-265">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="1476d-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-266">29</span><span class="sxs-lookup"><span data-stu-id="1476d-266">29</span></span></td>
<td><span data-ttu-id="1476d-267">Det gick inte att läsa parametrarna för offboarding.</span><span class="sxs-lookup"><span data-stu-id="1476d-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="1476d-268">Feltyp: %1, Felkod: %2, Beskrivning: %3</span><span class="sxs-lookup"><span data-stu-id="1476d-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="1476d-269">Händelsen inträffar när systemet inte&#39;av parametrarna för offboarding.</span><span class="sxs-lookup"><span data-stu-id="1476d-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="1476d-270">Kontrollera att enheten har internetanslutning och kör sedan hela offboardingprocessen igen.</span><span class="sxs-lookup"><span data-stu-id="1476d-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="1476d-271">Kontrollera att offboarding-paketet inte har upphört att gälla.</span><span class="sxs-lookup"><span data-stu-id="1476d-271">Ensure the offboarding package has not expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-272">30</span><span class="sxs-lookup"><span data-stu-id="1476d-272">30</span></span></td>
<td><span data-ttu-id="1476d-273">Microsoft Defender för slutpunktstjänsten kunde inte inaktivera SENSE-läge i Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="1476d-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="1476d-274">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-275">Normalt inger Microsoft Defender Antivirus ett särskilt passivt läge om en annan antimalwareprodukt i realtid körs korrekt på enheten och enheten rapporterar till Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="1476d-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="1476d-276">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="1476d-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="1476d-277">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="1476d-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="1476d-278">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter</a></span><span class="sxs-lookup"><span data-stu-id="1476d-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="1476d-279">Se till att skydd mot skadlig programvara i realtid fungerar som det ska.</span><span class="sxs-lookup"><span data-stu-id="1476d-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-280">31</span><span class="sxs-lookup"><span data-stu-id="1476d-280">31</span></span></td>
<td><span data-ttu-id="1476d-281">Microsoft Defender för slutpunktsanslutna användarupplevelser och avregistrering av telemetritjänsten misslyckades.</span><span class="sxs-lookup"><span data-stu-id="1476d-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="1476d-282">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-283">Ett fel uppstod med Windows-telemetritjänsten under onboarding.</span><span class="sxs-lookup"><span data-stu-id="1476d-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="1476d-284">Offboarding-processen fortsätter.</span><span class="sxs-lookup"><span data-stu-id="1476d-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="1476d-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Sök efter fel med Windows-telemetritjänsten</a>.</span><span class="sxs-lookup"><span data-stu-id="1476d-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-286">32</span><span class="sxs-lookup"><span data-stu-id="1476d-286">32</span></span></td>
<td><span data-ttu-id="1476d-287">Microsoft Defender för slutpunktstjänsten kunde inte begära att stoppa sig själv efter offboardingprocessen.</span><span class="sxs-lookup"><span data-stu-id="1476d-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="1476d-288">Felkod: %1</span><span class="sxs-lookup"><span data-stu-id="1476d-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="1476d-289">Ett fel uppstod vid offboarding.</span><span class="sxs-lookup"><span data-stu-id="1476d-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="1476d-290">Starta om enheten.</span><span class="sxs-lookup"><span data-stu-id="1476d-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-291">33</span><span class="sxs-lookup"><span data-stu-id="1476d-291">33</span></span></td>
<td><span data-ttu-id="1476d-292">Microsoft Defender för slutpunktstjänsten kunde inte spara SENSE GUID.</span><span class="sxs-lookup"><span data-stu-id="1476d-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="1476d-293">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-294">En unik identifierare används för att representera varje enhet som rapporterar till portalen.</span><span class="sxs-lookup"><span data-stu-id="1476d-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="1476d-295">Om identifieraren inte finns kvar kan samma enhet visas två gånger i portalen.</span><span class="sxs-lookup"><span data-stu-id="1476d-295">If the identifier does not persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="1476d-296">Kontrollera registerbehörigheter på enheten för att säkerställa att tjänsten kan uppdatera registret.</span><span class="sxs-lookup"><span data-stu-id="1476d-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-297">34</span><span class="sxs-lookup"><span data-stu-id="1476d-297">34</span></span></td>
<td><span data-ttu-id="1476d-298">Microsoft Defender för Slutpunkt-tjänsten kunde inte lägga till sig själv som ett beroende av den anslutna användarupplevelsen och telemetritjänsten, vilket ledde till att onboarding-processen misslyckades.</span><span class="sxs-lookup"><span data-stu-id="1476d-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="1476d-299">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-300">Ett fel uppstod med Windows-telemetritjänsten.</span><span class="sxs-lookup"><span data-stu-id="1476d-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="1476d-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Kontrollera att diagnostikdatatjänsten är aktiverad.</a></span><span class="sxs-lookup"><span data-stu-id="1476d-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="1476d-302">Kontrollera att onboarding-inställningarna och skripten har distribuerats korrekt.</span><span class="sxs-lookup"><span data-stu-id="1476d-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="1476d-303">Försök distribuera konfigurationspaketen igen.</span><span class="sxs-lookup"><span data-stu-id="1476d-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="1476d-304">Se <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Introduktion till Windows 10-enheter.</a></span><span class="sxs-lookup"><span data-stu-id="1476d-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-305">35</span><span class="sxs-lookup"><span data-stu-id="1476d-305">35</span></span></td>
<td><span data-ttu-id="1476d-306">Microsoft Defender för slutpunktstjänsten kunde inte ta bort sig själv som ett beroende av den anslutna användarupplevelsen och telemetritjänsten.</span><span class="sxs-lookup"><span data-stu-id="1476d-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="1476d-307">Felkod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-308">Ett fel uppstod med Windows-telemetritjänsten under offboarding.</span><span class="sxs-lookup"><span data-stu-id="1476d-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="1476d-309">Offboarding-processen fortsätter.</span><span class="sxs-lookup"><span data-stu-id="1476d-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="1476d-310">Sök efter fel med Windows-diagnostikdatatjänsten.</span><span class="sxs-lookup"><span data-stu-id="1476d-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-311">36</span><span class="sxs-lookup"><span data-stu-id="1476d-311">36</span></span></td>
<td><span data-ttu-id="1476d-312">Microsoft Defender för slutpunktsanslutna användarupplevelser och telemetritjänstregistrering lyckades.</span><span class="sxs-lookup"><span data-stu-id="1476d-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="1476d-313">Slutförandekod: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="1476d-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="1476d-314">Registrering av Defender för slutpunkt med den anslutna användarupplevelsen och telemetritjänsten har slutförts.</span><span class="sxs-lookup"><span data-stu-id="1476d-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="1476d-315">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="1476d-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-316">37</span><span class="sxs-lookup"><span data-stu-id="1476d-316">37</span></span></td>
<td><span data-ttu-id="1476d-317">Microsoft Defender för slutpunkt En modul kommer att överskrida sin kvot.</span><span class="sxs-lookup"><span data-stu-id="1476d-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="1476d-318">Modul: %1, Kvot: {%2} {%3}, Procentandel av kvotens användning: %4.</span><span class="sxs-lookup"><span data-stu-id="1476d-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="1476d-319">Enheten har nästan använt sin tilldelade kvot under det aktuella 24-timmarsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1476d-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="1476d-320">Den kommer att begränsas.</span><span class="sxs-lookup"><span data-stu-id="1476d-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="1476d-321">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="1476d-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-322">38</span><span class="sxs-lookup"><span data-stu-id="1476d-322">38</span></span></td>
<td><span data-ttu-id="1476d-323">Nätverksanslutningen identifieras som låg.</span><span class="sxs-lookup"><span data-stu-id="1476d-323">Network connection is identified as low.</span></span> <span data-ttu-id="1476d-324">Microsoft Defender för Endpoint kontaktar servern var %1:e minut.</span><span class="sxs-lookup"><span data-stu-id="1476d-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="1476d-325">Anslutning med datatrafik: %2, internet tillgängligt: %3, kostnadsfritt nätverk tillgängligt: %4.</span><span class="sxs-lookup"><span data-stu-id="1476d-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="1476d-326">Enheten använder ett nätverk med datatrafik/betalt nätverk och kontaktar servern mer sällan.</span><span class="sxs-lookup"><span data-stu-id="1476d-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="1476d-327">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="1476d-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-328">39</span><span class="sxs-lookup"><span data-stu-id="1476d-328">39</span></span></td>
<td><span data-ttu-id="1476d-329">Nätverksanslutningen identifieras som normal.</span><span class="sxs-lookup"><span data-stu-id="1476d-329">Network connection is identified as normal.</span></span> <span data-ttu-id="1476d-330">Microsoft Defender för Endpoint kontaktar servern var %1:e minut.</span><span class="sxs-lookup"><span data-stu-id="1476d-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="1476d-331">Anslutning med datatrafik: %2, internet tillgängligt: %3, kostnadsfritt nätverk tillgängligt: %4.</span><span class="sxs-lookup"><span data-stu-id="1476d-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="1476d-332">Enheten använder inte en anslutning med databetalda data och kontaktar servern som vanligt.</span><span class="sxs-lookup"><span data-stu-id="1476d-332">The device is not using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="1476d-333">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="1476d-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-334">40</span><span class="sxs-lookup"><span data-stu-id="1476d-334">40</span></span></td>
<td><span data-ttu-id="1476d-335">Batteritillståndet identifieras som låg.</span><span class="sxs-lookup"><span data-stu-id="1476d-335">Battery state is identified as low.</span></span> <span data-ttu-id="1476d-336">Microsoft Defender för Endpoint kontaktar servern var %1:e minut.</span><span class="sxs-lookup"><span data-stu-id="1476d-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="1476d-337">Batteritillstånd: %2.</span><span class="sxs-lookup"><span data-stu-id="1476d-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="1476d-338">Enheten har låg batterinivå och kontaktar servern mindre ofta.</span><span class="sxs-lookup"><span data-stu-id="1476d-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="1476d-339">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="1476d-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-340">41</span><span class="sxs-lookup"><span data-stu-id="1476d-340">41</span></span></td>
<td><span data-ttu-id="1476d-341">Batteritillståndet identifieras som normalt.</span><span class="sxs-lookup"><span data-stu-id="1476d-341">Battery state is identified as normal.</span></span> <span data-ttu-id="1476d-342">Microsoft Defender för Endpoint kontaktar servern var %1:e minut.</span><span class="sxs-lookup"><span data-stu-id="1476d-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="1476d-343">Batteritillstånd: %2.</span><span class="sxs-lookup"><span data-stu-id="1476d-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="1476d-344">Enheten har inte låg batterinivå och kontaktar servern som vanligt.</span><span class="sxs-lookup"><span data-stu-id="1476d-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="1476d-345">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="1476d-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-346">42</span><span class="sxs-lookup"><span data-stu-id="1476d-346">42</span></span></td>
<td><span data-ttu-id="1476d-347">Microsoft Defender för Slutpunkt WDATP-komponent kunde inte utföra någon åtgärd.</span><span class="sxs-lookup"><span data-stu-id="1476d-347">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="1476d-348">Komponent: %1, Åtgärd: %2, Undantagstyp: %3, Undantagsmeddelande: %4</span><span class="sxs-lookup"><span data-stu-id="1476d-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="1476d-349">Internt fel.</span><span class="sxs-lookup"><span data-stu-id="1476d-349">Internal error.</span></span> <span data-ttu-id="1476d-350">Det gick inte att starta tjänsten.</span><span class="sxs-lookup"><span data-stu-id="1476d-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="1476d-351">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="1476d-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-352">43</span><span class="sxs-lookup"><span data-stu-id="1476d-352">43</span></span></td>
<td><span data-ttu-id="1476d-353">Microsoft Defender för Slutpunkt WDATP-komponent kunde inte utföra någon åtgärd.</span><span class="sxs-lookup"><span data-stu-id="1476d-353">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="1476d-354">Komponent: %1, Åtgärd: %2, Undantagstyp: %3, Undantagsfel: %4, Undantagsmeddelande: %5</span><span class="sxs-lookup"><span data-stu-id="1476d-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="1476d-355">Internt fel.</span><span class="sxs-lookup"><span data-stu-id="1476d-355">Internal error.</span></span> <span data-ttu-id="1476d-356">Det gick inte att starta tjänsten.</span><span class="sxs-lookup"><span data-stu-id="1476d-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="1476d-357">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="1476d-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-358">44</span><span class="sxs-lookup"><span data-stu-id="1476d-358">44</span></span></td>
<td><span data-ttu-id="1476d-359">Offboarding av Defender för slutpunktstjänsten har slutförts.</span><span class="sxs-lookup"><span data-stu-id="1476d-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="1476d-360">Tjänsten var offboarded.</span><span class="sxs-lookup"><span data-stu-id="1476d-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="1476d-361">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="1476d-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-362">45</span><span class="sxs-lookup"><span data-stu-id="1476d-362">45</span></span></td>
<td><span data-ttu-id="1476d-363">Det gick inte att registrera och starta händelsespårningssessionen [%1].</span><span class="sxs-lookup"><span data-stu-id="1476d-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="1476d-364">Felkod: %2</span><span class="sxs-lookup"><span data-stu-id="1476d-364">Error code: %2</span></span></td>
<td><span data-ttu-id="1476d-365">Ett fel uppstod vid start av tjänsten vid skapandet av ETW-session.</span><span class="sxs-lookup"><span data-stu-id="1476d-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="1476d-366">Detta orsakade startfel för tjänsten.</span><span class="sxs-lookup"><span data-stu-id="1476d-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="1476d-367">Om det här felet kvarstår kontaktar du supporten.</span><span class="sxs-lookup"><span data-stu-id="1476d-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-368">46</span><span class="sxs-lookup"><span data-stu-id="1476d-368">46</span></span></td>
<td><span data-ttu-id="1476d-369">Det gick inte att registrera och starta händelsespårningssessionen [%1] på grund av brist på resurser.</span><span class="sxs-lookup"><span data-stu-id="1476d-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="1476d-370">Felkod: %2.</span><span class="sxs-lookup"><span data-stu-id="1476d-370">Error code: %2.</span></span> <span data-ttu-id="1476d-371">Det beror troligen på att det finns för många sessioner med aktiva händelsespårningar.</span><span class="sxs-lookup"><span data-stu-id="1476d-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="1476d-372">Tjänsten kommer att försöka igen om 1 minut.</span><span class="sxs-lookup"><span data-stu-id="1476d-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="1476d-373">Ett fel uppstod vid start av tjänsten när ETW-sessionen skulle skapas på grund av brist på resurser.</span><span class="sxs-lookup"><span data-stu-id="1476d-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="1476d-374">Tjänsten startades och körs, men rapporterar inte någon sensorhändelse förrän ETW-sessionen startas.</span><span class="sxs-lookup"><span data-stu-id="1476d-374">The service started and is running, but will not report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="1476d-375">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="1476d-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="1476d-376">Tjänsten försöker starta sessionen varje minut.</span><span class="sxs-lookup"><span data-stu-id="1476d-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-377">47</span><span class="sxs-lookup"><span data-stu-id="1476d-377">47</span></span></td>
<td><span data-ttu-id="1476d-378">Registrerad och startade händelsespårningssessionen – återställdes efter tidigare misslyckade försök.</span><span class="sxs-lookup"><span data-stu-id="1476d-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="1476d-379">Händelsen följer den föregående händelsen efter att ETW-sessionen har startar.</span><span class="sxs-lookup"><span data-stu-id="1476d-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="1476d-380">Meddelande om normal användning. ingen åtgärd krävs.</span><span class="sxs-lookup"><span data-stu-id="1476d-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="1476d-381">48</span><span class="sxs-lookup"><span data-stu-id="1476d-381">48</span></span></td>
<td><span data-ttu-id="1476d-382">Det gick inte att lägga till en provider [%1] i händelsespårningssession [%2].</span><span class="sxs-lookup"><span data-stu-id="1476d-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="1476d-383">Felkod: %3.</span><span class="sxs-lookup"><span data-stu-id="1476d-383">Error code: %3.</span></span> <span data-ttu-id="1476d-384">Det innebär att händelser från den här leverantören inte rapporteras.</span><span class="sxs-lookup"><span data-stu-id="1476d-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="1476d-385">Det gick inte att lägga till en leverantör i ETW-sessionen.</span><span class="sxs-lookup"><span data-stu-id="1476d-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="1476d-386">Därför rapporteras inte leverantörshändelserna.</span><span class="sxs-lookup"><span data-stu-id="1476d-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="1476d-387">Kontrollera felkoden.</span><span class="sxs-lookup"><span data-stu-id="1476d-387">Check the error code.</span></span> <span data-ttu-id="1476d-388">Kontakta support om felet kvarstår.</span><span class="sxs-lookup"><span data-stu-id="1476d-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
</tbody>
</table>

><span data-ttu-id="1476d-389">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1476d-389">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1476d-390">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="1476d-390">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="1476d-391">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1476d-391">Related topics</span></span>
- [<span data-ttu-id="1476d-392">Introducera Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="1476d-392">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="1476d-393">Konfigurera enhetsproxy och internetanslutningsinställningar</span><span class="sxs-lookup"><span data-stu-id="1476d-393">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="1476d-394">Felsöka Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="1476d-394">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
