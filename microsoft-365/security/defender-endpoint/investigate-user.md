---
title: Undersöka ett användarkonto i Microsoft Defender för Endpoint
description: Undersök ett användarkonto för möjliga komprometterade autentiseringsuppgifter eller pivotera på det associerade användarkontot under en undersökning.
keywords: undersöker, konto, användare, användar entitet, avisering, Microsoft Defender för slutpunkt
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
ms.openlocfilehash: e98142e4076c5e695f16eb06c062bc69d3d7dd55
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935071"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="3c1ad-104">Undersöka ett användarkonto i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="3c1ad-104">Investigate a user account in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3c1ad-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3c1ad-105">**Applies to:**</span></span>
- [<span data-ttu-id="3c1ad-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="3c1ad-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3c1ad-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c1ad-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="3c1ad-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="3c1ad-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3c1ad-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a><span data-ttu-id="3c1ad-110">Undersöka enheter för användarkonton</span><span class="sxs-lookup"><span data-stu-id="3c1ad-110">Investigate user account entities</span></span>

<span data-ttu-id="3c1ad-111">Identifiera användarkonton med de mest aktiva aviseringarna (visas på instrumentpanelen som "Användare på risk") och undersöker fall av potentiella komprometterade autentiseringsuppgifter, eller pivotera på det associerade användarkontot när du undersöker en avisering eller enhet för att identifiera möjlig mobil rörelse mellan enheter med det användarkontot.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-111">Identify user accounts with the most active alerts (displayed on dashboard as "Users at risk") and investigate cases of potential compromised credentials, or pivot on the associated user account when investigating an alert or device to identify possible lateral movement between devices with that user account.</span></span>

<span data-ttu-id="3c1ad-112">Användarkontoinformationen finns i följande vyer:</span><span class="sxs-lookup"><span data-stu-id="3c1ad-112">You can find user account information in the following views:</span></span>

- <span data-ttu-id="3c1ad-113">Instrumentpanelen</span><span class="sxs-lookup"><span data-stu-id="3c1ad-113">Dashboard</span></span>
- <span data-ttu-id="3c1ad-114">Aviseringskö</span><span class="sxs-lookup"><span data-stu-id="3c1ad-114">Alert queue</span></span>
- <span data-ttu-id="3c1ad-115">Sidan Enhetsinformation</span><span class="sxs-lookup"><span data-stu-id="3c1ad-115">Device details page</span></span>

<span data-ttu-id="3c1ad-116">I de här vyerna finns det en klickbar länk till användarkontots informationssida där mer information om användarkontot visas.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-116">A clickable user account link is available in these views, that will take you to the user account details page where more details about the user account are shown.</span></span>

<span data-ttu-id="3c1ad-117">När du undersöker en användarkontotitet visas:</span><span class="sxs-lookup"><span data-stu-id="3c1ad-117">When you investigate a user account entity, you'll see:</span></span>

- <span data-ttu-id="3c1ad-118">Användarkontoinformation, Microsoft Defender för identitetsaviseringar och inloggad på enheter, roll, inloggningstyp och annan information</span><span class="sxs-lookup"><span data-stu-id="3c1ad-118">User account details, Microsoft Defender for Identity alerts, and logged on devices, role, logon type, and other details</span></span>
- <span data-ttu-id="3c1ad-119">Översikt över incidenter och användarens enheter</span><span class="sxs-lookup"><span data-stu-id="3c1ad-119">Overview of the incidents and user's devices</span></span>
- <span data-ttu-id="3c1ad-120">Aviseringar relaterade till den här användaren</span><span class="sxs-lookup"><span data-stu-id="3c1ad-120">Alerts related to this user</span></span>
- <span data-ttu-id="3c1ad-121">Observerad i organisationen (enheter som är inloggade)</span><span class="sxs-lookup"><span data-stu-id="3c1ad-121">Observed in organization (devices logged on to)</span></span>

![Bild på informationssidan för användarkontot](images/atp-user-details-view.png)

### <a name="user-details"></a><span data-ttu-id="3c1ad-123">Användarinformation</span><span class="sxs-lookup"><span data-stu-id="3c1ad-123">User details</span></span>

<span data-ttu-id="3c1ad-124">I  fönstret Användarinformation till vänster finns information om användaren, till exempel relaterade öppna incidenter, aktiva aviseringar, SAM-namn, SID, Microsoft Defender för identitetsaviseringar, antalet enheter som användaren är inloggad på, när användaren sågs för första och sista gången, roll och inloggning.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-124">The **User details** pane on left provides information about the user, such as related open incidents, active alerts, SAM name, SID, Microsoft Defender for Identity alerts, number of devices the user is logged on to, when the user was first and last seen, role, and logon types.</span></span> <span data-ttu-id="3c1ad-125">Beroende på vilka integrationsfunktioner du har aktiverat visas annan information.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-125">Depending on the integration features you've enabled, you'll see other details.</span></span> <span data-ttu-id="3c1ad-126">Om du till exempel aktiverar Skype för företag-integrering kommer du att kunna kontakta användaren från portalen.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-126">For example, if you enable the Skype for business integration, you'll be able to contact the user from the portal.</span></span> <span data-ttu-id="3c1ad-127">Avsnittet **Azure ATP-aviseringar** innehåller en länk som tar dig till sidan Microsoft Defender för identitet om du har aktiverat Microsoft Defender för identitetsfunktionen och det finns aviseringar relaterade till användaren.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-127">The **Azure ATP alerts** section contains a link that will take you to the Microsoft Defender for Identity page, if you have enabled the Microsoft Defender for Identity feature, and there are alerts related to the user.</span></span> <span data-ttu-id="3c1ad-128">På sidan Microsoft Defender för identitet hittar du mer information om aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-128">The Microsoft Defender for Identity page will provide more information about the alerts.</span></span>

>[!NOTE]
><span data-ttu-id="3c1ad-129">Du måste aktivera integreringen på både Microsoft Defender för identitet och Defender för Endpoint om du vill använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-129">You'll need to enable the integration on both Microsoft Defender for Identity and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="3c1ad-130">I Defender för Slutpunkt kan du aktivera den här funktionen i avancerade funktioner.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-130">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="3c1ad-131">Mer information om hur du aktiverar avancerade funktioner finns i [Aktivera avancerade funktioner.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="3c1ad-131">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

<span data-ttu-id="3c1ad-132">Översikt, aviseringar och observerade i organisationen är olika flikar som visar olika attribut om användarkontot.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-132">The Overview, Alerts, and Observed in organization are different tabs that display various attributes about the user account.</span></span>

### <a name="overview"></a><span data-ttu-id="3c1ad-133">Översikt</span><span class="sxs-lookup"><span data-stu-id="3c1ad-133">Overview</span></span>

<span data-ttu-id="3c1ad-134">På **fliken** Översikt visas incidentinformation och en lista med de enheter som användaren har loggat in på.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-134">The **Overview** tab shows the incidents details and a list of the devices that the user has logged on to.</span></span> <span data-ttu-id="3c1ad-135">Du kan expandera dessa om du vill se information om inloggningshändelserna för varje enhet.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-135">You can expand these to see details of the log-on events for each device.</span></span>

### <a name="alerts"></a><span data-ttu-id="3c1ad-136">Varningar</span><span class="sxs-lookup"><span data-stu-id="3c1ad-136">Alerts</span></span>

<span data-ttu-id="3c1ad-137">På **fliken** Aviseringar finns en lista med aviseringar som är kopplade till användarkontot.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-137">The **Alerts** tab provides a list of alerts that are associated with the user account.</span></span> <span data-ttu-id="3c1ad-138">Den här listan är en [](alerts-queue.md)filtrerad vy av aviseringskön och visar aviseringar där användarkontexten är det valda användarkontot, datumet när den senaste aktiviteten upptäcktes, en kort beskrivning av aviseringen, enheten som är kopplad till aviseringen, aviseringens allvarlighetsgrad, aviseringens status i kön och vem som har tilldelats aviseringen.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-138">This list is a filtered view of the [Alert queue](alerts-queue.md), and shows alerts where the user context is the selected user account, the date when the last activity was detected, a short description of the alert, the device associated with the alert, the alert's severity, the alert's status in the queue, and who is assigned the alert.</span></span>

### <a name="observed-in-organization"></a><span data-ttu-id="3c1ad-139">Observerad i organisationen</span><span class="sxs-lookup"><span data-stu-id="3c1ad-139">Observed in organization</span></span>

<span data-ttu-id="3c1ad-140">På  fliken Observerad på organisation kan du ange ett datumintervall för att visa en lista över enheter där användaren har varit inloggad, det vanligaste och minst frekventa inloggade användarkontot för var och en av dessa enheter samt totalt antal observerade användare på varje enhet.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-140">The **Observed in organization** tab allows you to specify a date range to see a list of devices where this user was observed logged on to, the most frequent and least frequent logged on user account for each of these devices, and total observed users on each device.</span></span>

<span data-ttu-id="3c1ad-141">Om du markerar ett objekt i organisationstabellen Observerat utökas objektet och mer information om enheten visas.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-141">Selecting an item on the Observed in organization table will expand the item, revealing more details about the device.</span></span> <span data-ttu-id="3c1ad-142">Om du direkt markerar en länk i ett objekt skickas du till motsvarande sida.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-142">Directly selecting a link within an item will send you to the corresponding page.</span></span>

## <a name="search-for-specific-user-accounts"></a><span data-ttu-id="3c1ad-143">Söka efter specifika användarkonton</span><span class="sxs-lookup"><span data-stu-id="3c1ad-143">Search for specific user accounts</span></span>

1. <span data-ttu-id="3c1ad-144">Välj **Användare** i **sökfältets** nedrullningsbar meny.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-144">Select **User** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="3c1ad-145">Ange användarkontot i **sökfältet.**</span><span class="sxs-lookup"><span data-stu-id="3c1ad-145">Enter the user account in the **Search** field.</span></span>
3. <span data-ttu-id="3c1ad-146">Klicka på sökikonen eller tryck på **Retur.**</span><span class="sxs-lookup"><span data-stu-id="3c1ad-146">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="3c1ad-147">En lista med användare som matchar frågetexten visas.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-147">A list of users matching the query text is displayed.</span></span> <span data-ttu-id="3c1ad-148">Du ser användarkontots domän och namn, när användarkontot senast sågs och det totala antalet enheter som det observerades loggade in på under de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="3c1ad-148">You'll see the user account's domain and name, when the user account was last seen, and the total number of devices it was observed logged on to in the last 30 days.</span></span>

<span data-ttu-id="3c1ad-149">Du kan filtrera resultatet efter följande tidsperioder:</span><span class="sxs-lookup"><span data-stu-id="3c1ad-149">You can filter the results by the following time periods:</span></span>

- <span data-ttu-id="3c1ad-150">1 dag</span><span class="sxs-lookup"><span data-stu-id="3c1ad-150">1 day</span></span>
- <span data-ttu-id="3c1ad-151">3 dagar</span><span class="sxs-lookup"><span data-stu-id="3c1ad-151">3 days</span></span>
- <span data-ttu-id="3c1ad-152">7 dagar</span><span class="sxs-lookup"><span data-stu-id="3c1ad-152">7 days</span></span>
- <span data-ttu-id="3c1ad-153">30 dagar</span><span class="sxs-lookup"><span data-stu-id="3c1ad-153">30 days</span></span>
- <span data-ttu-id="3c1ad-154">6 månader</span><span class="sxs-lookup"><span data-stu-id="3c1ad-154">6 months</span></span>

## <a name="related-topics"></a><span data-ttu-id="3c1ad-155">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="3c1ad-155">Related topics</span></span>

- [<span data-ttu-id="3c1ad-156">Visa och ordna kön Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="3c1ad-156">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="3c1ad-157">Hantera Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="3c1ad-157">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="3c1ad-158">Undersöka Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="3c1ad-158">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="3c1ad-159">Undersöka en fil som är kopplad till en Defender för slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="3c1ad-159">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="3c1ad-160">Undersök enheter i listan Defender för slutpunktsenheter</span><span class="sxs-lookup"><span data-stu-id="3c1ad-160">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="3c1ad-161">Undersöka en IP-adress som är kopplad till en Defender för Slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="3c1ad-161">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="3c1ad-162">Undersöka en domän som är kopplad till en Defender för slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="3c1ad-162">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
