---
title: Undersöka ett användarkonto i Microsoft Defender ATP
description: Undersök ett användarkonto för möjliga komprometterade autentiseringsuppgifter eller pivotera på det associerade användarkontot under en undersökning.
keywords: undersöker, konto, användare, användar entitet, avisering, microsoft defender atp
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
ms.openlocfilehash: e994069220d8f88f1b8910413ad86da399c4a8f3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072330"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="58bff-104">Undersöka ett användarkonto i Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="58bff-104">Investigate a user account in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="58bff-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="58bff-105">**Applies to:**</span></span>
- [<span data-ttu-id="58bff-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="58bff-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="58bff-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="58bff-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="58bff-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="58bff-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="58bff-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="58bff-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a><span data-ttu-id="58bff-110">Undersöka enheter för användarkonton</span><span class="sxs-lookup"><span data-stu-id="58bff-110">Investigate user account entities</span></span>

<span data-ttu-id="58bff-111">Identifiera användarkonton med de mest aktiva aviseringarna (visas på instrumentpanelen som "Användare på risk") och undersöker fall av potentiella komprometterade autentiseringsuppgifter, eller pivotera på det associerade användarkontot när du undersöker en avisering eller enhet för att identifiera möjlig mobil rörelse mellan enheter med det användarkontot.</span><span class="sxs-lookup"><span data-stu-id="58bff-111">Identify user accounts with the most active alerts (displayed on dashboard as "Users at risk") and investigate cases of potential compromised credentials, or pivot on the associated user account when investigating an alert or device to identify possible lateral movement between devices with that user account.</span></span>

<span data-ttu-id="58bff-112">Användarkontoinformationen finns i följande vyer:</span><span class="sxs-lookup"><span data-stu-id="58bff-112">You can find user account information in the following views:</span></span>

- <span data-ttu-id="58bff-113">Instrumentpanelen</span><span class="sxs-lookup"><span data-stu-id="58bff-113">Dashboard</span></span>
- <span data-ttu-id="58bff-114">Aviseringskö</span><span class="sxs-lookup"><span data-stu-id="58bff-114">Alert queue</span></span>
- <span data-ttu-id="58bff-115">Sidan Enhetsinformation</span><span class="sxs-lookup"><span data-stu-id="58bff-115">Device details page</span></span>

<span data-ttu-id="58bff-116">I de här vyerna finns det en klickbar länk till användarkontots informationssida där mer information om användarkontot visas.</span><span class="sxs-lookup"><span data-stu-id="58bff-116">A clickable user account link is available in these views, that will take you to the user account details page where more details about the user account are shown.</span></span>

<span data-ttu-id="58bff-117">När du undersöker en användarkontotitet visas:</span><span class="sxs-lookup"><span data-stu-id="58bff-117">When you investigate a user account entity, you'll see:</span></span>

- <span data-ttu-id="58bff-118">Användarkontoinformation, Azure Advanced Threat Protection-aviseringar (Azure ATP) och inloggade på enheter, roll, inloggningstyp och annan information</span><span class="sxs-lookup"><span data-stu-id="58bff-118">User account details, Azure Advanced Threat Protection (Azure ATP) alerts, and logged on devices, role, logon type, and other details</span></span>
- <span data-ttu-id="58bff-119">Översikt över incidenter och användarens enheter</span><span class="sxs-lookup"><span data-stu-id="58bff-119">Overview of the incidents and user's devices</span></span>
- <span data-ttu-id="58bff-120">Aviseringar relaterade till den här användaren</span><span class="sxs-lookup"><span data-stu-id="58bff-120">Alerts related to this user</span></span>
- <span data-ttu-id="58bff-121">Observerad i organisationen (enheter som är inloggade)</span><span class="sxs-lookup"><span data-stu-id="58bff-121">Observed in organization (devices logged on to)</span></span>

![Bild på informationssidan för användarkontot](images/atp-user-details-view.png)

### <a name="user-details"></a><span data-ttu-id="58bff-123">Användarinformation</span><span class="sxs-lookup"><span data-stu-id="58bff-123">User details</span></span>

<span data-ttu-id="58bff-124">I  fönstret Användarinformation till vänster finns information om användaren, till exempel relaterade öppna incidenter, aktiva aviseringar, SAM-namn, SID, Azure ATP-aviseringar, antal enheter som användaren är inloggad på, när användaren sågs för första och sista gången, roll- och inloggningstyper.</span><span class="sxs-lookup"><span data-stu-id="58bff-124">The **User details** pane on left provides information about the user, such as related open incidents, active alerts, SAM name, SID, Azure ATP alerts, number of devices the user is logged on to, when the user was first and last seen, role, and logon types.</span></span> <span data-ttu-id="58bff-125">Beroende på vilka integrationsfunktioner du har aktiverat visas annan information.</span><span class="sxs-lookup"><span data-stu-id="58bff-125">Depending on the integration features you've enabled, you'll see other details.</span></span> <span data-ttu-id="58bff-126">Om du till exempel aktiverar Skype för företag-integreringen kan du kontakta användaren från portalen.</span><span class="sxs-lookup"><span data-stu-id="58bff-126">For example, if you enable the Skype for business integration, you'll be able to contact the user from the portal.</span></span> <span data-ttu-id="58bff-127">Avsnittet **Azure ATP-aviseringar** innehåller en länk som tar dig till Azure ATP-sidan, om du har aktiverat Azure ATP-funktionen och det finns aviseringar relaterade till användaren.</span><span class="sxs-lookup"><span data-stu-id="58bff-127">The **Azure ATP alerts** section contains a link that will take you to the Azure ATP page, if you have enabled the Azure ATP feature, and there are alerts related to the user.</span></span> <span data-ttu-id="58bff-128">På Azure ATP-sidan finns mer information om aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="58bff-128">The Azure ATP page will provide more information about the alerts.</span></span>

>[!NOTE]
><span data-ttu-id="58bff-129">Du måste aktivera integreringen på både Azure ATP och Defender för Endpoint om du vill använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="58bff-129">You'll need to enable the integration on both Azure ATP and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="58bff-130">I Defender för Slutpunkt kan du aktivera den här funktionen i avancerade funktioner.</span><span class="sxs-lookup"><span data-stu-id="58bff-130">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="58bff-131">Mer information om hur du aktiverar avancerade funktioner finns i [Aktivera avancerade funktioner.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="58bff-131">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

<span data-ttu-id="58bff-132">Översikt, aviseringar och observerade i organisationen är olika flikar som visar olika attribut om användarkontot.</span><span class="sxs-lookup"><span data-stu-id="58bff-132">The Overview, Alerts, and Observed in organization are different tabs that display various attributes about the user account.</span></span>

### <a name="overview"></a><span data-ttu-id="58bff-133">Översikt</span><span class="sxs-lookup"><span data-stu-id="58bff-133">Overview</span></span>

<span data-ttu-id="58bff-134">På **fliken** Översikt visas incidentinformation och en lista med de enheter som användaren har loggat in på.</span><span class="sxs-lookup"><span data-stu-id="58bff-134">The **Overview** tab shows the incidents details and a list of the devices that the user has logged on to.</span></span> <span data-ttu-id="58bff-135">Du kan expandera dessa om du vill se information om inloggningshändelserna för varje enhet.</span><span class="sxs-lookup"><span data-stu-id="58bff-135">You can expand these to see details of the log-on events for each device.</span></span>

### <a name="alerts"></a><span data-ttu-id="58bff-136">Varningar</span><span class="sxs-lookup"><span data-stu-id="58bff-136">Alerts</span></span>

<span data-ttu-id="58bff-137">På **fliken** Aviseringar finns en lista med aviseringar som är kopplade till användarkontot.</span><span class="sxs-lookup"><span data-stu-id="58bff-137">The **Alerts** tab provides a list of alerts that are associated with the user account.</span></span> <span data-ttu-id="58bff-138">Den här listan är en [](alerts-queue.md)filtrerad vy av aviseringskön och visar aviseringar där användarkontexten är det valda användarkontot, datumet när den senaste aktiviteten upptäcktes, en kort beskrivning av aviseringen, enheten som är kopplad till aviseringen, aviseringens allvarlighetsgrad, aviseringens status i kön och vem som har tilldelats aviseringen.</span><span class="sxs-lookup"><span data-stu-id="58bff-138">This list is a filtered view of the [Alert queue](alerts-queue.md), and shows alerts where the user context is the selected user account, the date when the last activity was detected, a short description of the alert, the device associated with the alert, the alert's severity, the alert's status in the queue, and who is assigned the alert.</span></span>

### <a name="observed-in-organization"></a><span data-ttu-id="58bff-139">Observerad i organisationen</span><span class="sxs-lookup"><span data-stu-id="58bff-139">Observed in organization</span></span>

<span data-ttu-id="58bff-140">På  fliken Observerad på organisation kan du ange ett datumintervall för att visa en lista över enheter där användaren har varit inloggad, det vanligaste och minst frekventa inloggade användarkontot för var och en av dessa enheter samt totalt antal observerade användare på varje enhet.</span><span class="sxs-lookup"><span data-stu-id="58bff-140">The **Observed in organization** tab allows you to specify a date range to see a list of devices where this user was observed logged on to, the most frequent and least frequent logged on user account for each of these devices, and total observed users on each device.</span></span>

<span data-ttu-id="58bff-141">Om du markerar ett objekt i organisationstabellen Observerat utökas objektet och mer information om enheten visas.</span><span class="sxs-lookup"><span data-stu-id="58bff-141">Selecting an item on the Observed in organization table will expand the item, revealing more details about the device.</span></span> <span data-ttu-id="58bff-142">Om du direkt markerar en länk i ett objekt skickas du till motsvarande sida.</span><span class="sxs-lookup"><span data-stu-id="58bff-142">Directly selecting a link within an item will send you to the corresponding page.</span></span>

## <a name="search-for-specific-user-accounts"></a><span data-ttu-id="58bff-143">Söka efter specifika användarkonton</span><span class="sxs-lookup"><span data-stu-id="58bff-143">Search for specific user accounts</span></span>

1. <span data-ttu-id="58bff-144">Välj **Användare** i **sökfältets** nedrullningsbar meny.</span><span class="sxs-lookup"><span data-stu-id="58bff-144">Select **User** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="58bff-145">Ange användarkontot i **sökfältet.**</span><span class="sxs-lookup"><span data-stu-id="58bff-145">Enter the user account in the **Search** field.</span></span>
3. <span data-ttu-id="58bff-146">Klicka på sökikonen eller tryck på **Retur.**</span><span class="sxs-lookup"><span data-stu-id="58bff-146">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="58bff-147">En lista med användare som matchar frågetexten visas.</span><span class="sxs-lookup"><span data-stu-id="58bff-147">A list of users matching the query text is displayed.</span></span> <span data-ttu-id="58bff-148">Du ser användarkontots domän och namn, när användarkontot senast sågs och det totala antalet enheter som det observerades loggade in på under de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="58bff-148">You'll see the user account's domain and name, when the user account was last seen, and the total number of devices it was observed logged on to in the last 30 days.</span></span>

<span data-ttu-id="58bff-149">Du kan filtrera resultatet efter följande tidsperioder:</span><span class="sxs-lookup"><span data-stu-id="58bff-149">You can filter the results by the following time periods:</span></span>

- <span data-ttu-id="58bff-150">1 dag</span><span class="sxs-lookup"><span data-stu-id="58bff-150">1 day</span></span>
- <span data-ttu-id="58bff-151">3 dagar</span><span class="sxs-lookup"><span data-stu-id="58bff-151">3 days</span></span>
- <span data-ttu-id="58bff-152">7 dagar</span><span class="sxs-lookup"><span data-stu-id="58bff-152">7 days</span></span>
- <span data-ttu-id="58bff-153">30 dagar</span><span class="sxs-lookup"><span data-stu-id="58bff-153">30 days</span></span>
- <span data-ttu-id="58bff-154">6 månader</span><span class="sxs-lookup"><span data-stu-id="58bff-154">6 months</span></span>

## <a name="related-topics"></a><span data-ttu-id="58bff-155">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="58bff-155">Related topics</span></span>

- [<span data-ttu-id="58bff-156">Visa och ordna kön Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="58bff-156">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="58bff-157">Hantera Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="58bff-157">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="58bff-158">Undersöka Microsoft Defender för slutpunktsaviseringar</span><span class="sxs-lookup"><span data-stu-id="58bff-158">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="58bff-159">Undersöka en fil som är kopplad till en Defender för slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="58bff-159">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="58bff-160">Undersök enheter i listan Defender för slutpunktsenheter</span><span class="sxs-lookup"><span data-stu-id="58bff-160">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="58bff-161">Undersöka en IP-adress som är kopplad till en Defender för Slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="58bff-161">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="58bff-162">Undersöka en domän som är kopplad till en Defender för slutpunktsavisering</span><span class="sxs-lookup"><span data-stu-id="58bff-162">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
