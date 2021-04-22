---
title: Åtgärda säkerhetsproblem med hantering av hot och risker
description: Åtgärda säkerhetsbrister som upptäcks genom säkerhetsrekommendationer och skapa undantag vid behov, i hantering av hot och sårbarhet.
keywords: Microsoft Defender för Endpoint-tvm-åtgärd, Microsoft Defender för Slutpunkt-tvm, hantering av hot och sårbarhet, & sårbarhetshantering, & sårbarhetshantering, åtgärd för tvm-åtgärd intune, tvm remediation sccm
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
ms.openlocfilehash: 56b6c809e31285bbfae47a5fdcc0446890919e8b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934075"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a><span data-ttu-id="24ea7-104">Åtgärda säkerhetsproblem med hantering av hot och risker</span><span class="sxs-lookup"><span data-stu-id="24ea7-104">Remediate vulnerabilities with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="24ea7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="24ea7-105">**Applies to:**</span></span>
- [<span data-ttu-id="24ea7-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="24ea7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="24ea7-107">Hantering av hot och sårbarhet</span><span class="sxs-lookup"><span data-stu-id="24ea7-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="24ea7-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24ea7-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="24ea7-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="24ea7-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="24ea7-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="24ea7-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a><span data-ttu-id="24ea7-111">Begära åtgärd</span><span class="sxs-lookup"><span data-stu-id="24ea7-111">Request remediation</span></span>

<span data-ttu-id="24ea7-112">Funktionen för hantering av hot och sårbarhet i Microsoft Defender för Endpoint överbrygger mellanrummet mellan säkerhet och IT-administratörer genom arbetsflödet för åtgärdsförfrågningar.</span><span class="sxs-lookup"><span data-stu-id="24ea7-112">The threat and vulnerability management capability in Microsoft Defender for Endpoint bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="24ea7-113">Som säkerhetsadministratörer kan du begära att IT-administratören åtgärdar problemet från sidorna med säkerhetsrekommendationer till Intune. </span><span class="sxs-lookup"><span data-stu-id="24ea7-113">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** pages to Intune.</span></span>

### <a name="enable-microsoft-intune-connection"></a><span data-ttu-id="24ea7-114">Aktivera Microsoft Intune-anslutning</span><span class="sxs-lookup"><span data-stu-id="24ea7-114">Enable Microsoft Intune connection</span></span>

<span data-ttu-id="24ea7-115">Aktivera dina Microsoft Intune-anslutningar om du vill använda den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="24ea7-115">To use this capability, enable your Microsoft Intune connections.</span></span> <span data-ttu-id="24ea7-116">I Microsoft Defender Säkerhetscenter går du till **Inställningar**  >  **Allmänna**  >  **avancerade funktioner.**</span><span class="sxs-lookup"><span data-stu-id="24ea7-116">In the Microsoft Defender Security Center, navigate to **Settings** > **General** > **Advanced features**.</span></span> <span data-ttu-id="24ea7-117">Rulla nedåt och leta efter **Microsoft Intune-anslutning**.</span><span class="sxs-lookup"><span data-stu-id="24ea7-117">Scroll down and look for **Microsoft Intune connection**.</span></span> <span data-ttu-id="24ea7-118">Växlingsknappen är inaktiverad som standard.</span><span class="sxs-lookup"><span data-stu-id="24ea7-118">By default, the toggle is turned off.</span></span> <span data-ttu-id="24ea7-119">Aktivera Microsoft **Intune-anslutningen.** </span><span class="sxs-lookup"><span data-stu-id="24ea7-119">Turn your **Microsoft Intune connection** toggle **On**.</span></span>

<span data-ttu-id="24ea7-120">**Obs!** Om Intune-anslutningen är aktiverad får du ett alternativ för att skapa en Intune-säkerhetsaktivitet när du skapar en åtgärdsbegäran.</span><span class="sxs-lookup"><span data-stu-id="24ea7-120">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="24ea7-121">Det här alternativet visas inte om anslutningen inte har angetts.</span><span class="sxs-lookup"><span data-stu-id="24ea7-121">This option does not appear if the connection is not set.</span></span>

<span data-ttu-id="24ea7-122">Mer [information finns i Använda Intune för att](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) åtgärda säkerhetsproblem som identifieras av Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="24ea7-122">See [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) for details.</span></span>

### <a name="remediation-request-steps"></a><span data-ttu-id="24ea7-123">Steg för åtgärdsförfrågan</span><span class="sxs-lookup"><span data-stu-id="24ea7-123">Remediation request steps</span></span>

1. <span data-ttu-id="24ea7-124">Gå till navigeringsmenyn för hantering av hot och sårbarhet i Microsoft Defender Säkerhetscenter och välj [**Säkerhetsrekommendationer**](tvm-security-recommendation.md).</span><span class="sxs-lookup"><span data-stu-id="24ea7-124">Go to the threat and vulnerability management navigation menu in the Microsoft Defender Security Center, and select [**Security recommendations**](tvm-security-recommendation.md).</span></span>

2. <span data-ttu-id="24ea7-125">Välj en säkerhetsrekommendationer som du vill begära åtgärd för och välj sedan **Åtgärdsalternativ.**</span><span class="sxs-lookup"><span data-stu-id="24ea7-125">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span>

3. <span data-ttu-id="24ea7-126">Fyll i formuläret, inklusive vad du begär åtgärd för, tillämpliga enhetsgrupper, prioritet, förfallodatum och valfria anteckningar.</span><span class="sxs-lookup"><span data-stu-id="24ea7-126">Fill out the form, including what you are requesting remediation for, applicable device groups, priority, due date, and optional notes.</span></span>
    1. <span data-ttu-id="24ea7-127">Om du väljer åtgärdsalternativet "åtgärd krävs" är det inte tillgängligt att välja ett förfallodatum eftersom det inte finns någon särskild åtgärd.</span><span class="sxs-lookup"><span data-stu-id="24ea7-127">If you choose the "attention required" remediation option, selecting a due date will not be available since there is no specific action.</span></span>

4. <span data-ttu-id="24ea7-128">Välj **Skicka begäran**.</span><span class="sxs-lookup"><span data-stu-id="24ea7-128">Select **Submit request**.</span></span> <span data-ttu-id="24ea7-129">Om du skickar en begäran om åtgärd skapas ett åtgärdsaktivitetsobjekt inom hantering av hot och sårbarhet, som kan användas för att övervaka åtgärdsförloppet för den här rekommendationen.</span><span class="sxs-lookup"><span data-stu-id="24ea7-129">Submitting a remediation request creates a remediation activity item within threat and vulnerability management, which can be used for monitoring the remediation progress for this recommendation.</span></span> <span data-ttu-id="24ea7-130">Det här utlöser inte någon åtgärd eller tillämpar ändringar på enheter.</span><span class="sxs-lookup"><span data-stu-id="24ea7-130">This will not trigger a remediation or apply any changes to devices.</span></span>

5. <span data-ttu-id="24ea7-131">Meddela IT-administratören om den nya begäran och be dem logga in i Intune för att godkänna eller avvisa begäran och starta en paketdistribution.</span><span class="sxs-lookup"><span data-stu-id="24ea7-131">Notify your IT Administrator about the new request and have them log into Intune to approve or reject the request and start a package deployment.</span></span>

6. <span data-ttu-id="24ea7-132">Gå till [**sidan Åtgärd för**](tvm-remediation.md) att visa status för din begäran om åtgärd.</span><span class="sxs-lookup"><span data-stu-id="24ea7-132">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span>

<span data-ttu-id="24ea7-133">Om du vill kontrollera hur biljetten visas i Intune hittar du mer information i Använd [Intune](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) för att åtgärda säkerhetsproblem som identifieras av Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="24ea7-133">If you want to check how the ticket shows up in Intune, see [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) for details.</span></span>

>[!NOTE]
><span data-ttu-id="24ea7-134">Om din begäran kräver åtgärd av fler än 10 000 enheter kan vi bara skicka 10 000 enheter för åtgärd till Intune.</span><span class="sxs-lookup"><span data-stu-id="24ea7-134">If your request involves remediating more than 10,000 devices, we can only send 10,000 devices for remediation to Intune.</span></span>

<span data-ttu-id="24ea7-135">När du har identifierat och mappat organisationens cybersäkerhet till åtgärdsbara [säkerhetsrekommendationer börjar](tvm-security-recommendation.md)du med att skapa säkerhetsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="24ea7-135">After your organization's cybersecurity weaknesses are identified and mapped to actionable [security recommendations](tvm-security-recommendation.md), start creating security tasks.</span></span> <span data-ttu-id="24ea7-136">Du kan skapa uppgifter genom integreringen med Microsoft Intune där åtgärder skapas.</span><span class="sxs-lookup"><span data-stu-id="24ea7-136">You can create tasks through the integration with Microsoft Intune where remediation tickets are created.</span></span>

<span data-ttu-id="24ea7-137">Minska exponeringen från svagheter i organisationen och öka säkerhetskonfigurationen genom att åtgärda säkerhetsrekommendationerna.</span><span class="sxs-lookup"><span data-stu-id="24ea7-137">Lower your organization's exposure from vulnerabilities and increase your security configuration by remediating the security recommendations.</span></span>

## <a name="view-your-remediation-activities"></a><span data-ttu-id="24ea7-138">Visa åtgärder</span><span class="sxs-lookup"><span data-stu-id="24ea7-138">View your remediation activities</span></span>

<span data-ttu-id="24ea7-139">När du skickar en begäran om åtgärd från sidan Säkerhetsrekommendationer startar den en åtgärdsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="24ea7-139">When you submit a remediation request from the Security recommendations page, it kicks-off a remediation activity.</span></span> <span data-ttu-id="24ea7-140">En säkerhetsuppgift skapas som kan spåras på  sidan för åtgärder för hot och sårbarhetshantering, och en åtgärdsuppgift skapas i Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="24ea7-140">A security task is created that can be tracked in the threat and vulnerability management **Remediation** page, and a remediation ticket is created in Microsoft Intune.</span></span>

<span data-ttu-id="24ea7-141">Om du väljer åtgärdsalternativet "åtgärd krävs" finns det ingen förloppsstapel, status för biljett eller förfallodatum eftersom det inte finns någon verklig åtgärd vi kan övervaka.</span><span class="sxs-lookup"><span data-stu-id="24ea7-141">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there is no actual action we can monitor.</span></span>

<span data-ttu-id="24ea7-142">När du är på sidan Åtgärd väljer du den åtgärdsaktivitet som du vill visa.</span><span class="sxs-lookup"><span data-stu-id="24ea7-142">Once you are in the Remediation page, select the remediation activity that you want to view.</span></span> <span data-ttu-id="24ea7-143">Du kan följa åtgärdsstegen, spåra förloppet, visa relaterad rekommendation, exportera till CSV eller markera som slutförd.</span><span class="sxs-lookup"><span data-stu-id="24ea7-143">You can follow the remediation steps, track progress, view the related recommendation, export to CSV, or mark as complete.</span></span>
<span data-ttu-id="24ea7-144">![Exempel på sidan Åtgärd, med en vald åtgärdsaktivitet, och den aktivitetens utfällsida med en lista över beskrivningen, IT-tjänster och verktyg för enhetshantering samt status för enhetsreparation.](images/remediation_flyouteolsw.png)</span><span class="sxs-lookup"><span data-stu-id="24ea7-144">![Example of the Remediation page, with a selected remediation activity, and that activity's flyout listing the description, IT service and device management tools, and device remediation progress.](images/remediation_flyouteolsw.png)</span></span>

>[!NOTE]
> <span data-ttu-id="24ea7-145">Det finns en 180-dagars kvarhållningstid för slutförda åtgärder.</span><span class="sxs-lookup"><span data-stu-id="24ea7-145">There is a 180 day retention period for completed remediation activities.</span></span> <span data-ttu-id="24ea7-146">För att åtgärdssidan ska fungera optimalt tas åtgärdsaktiviteten bort 6 månader efter att den har slutförts.</span><span class="sxs-lookup"><span data-stu-id="24ea7-146">To keep the Remediation page performing optimally, the remediation activity will be removed 6 months after its completion.</span></span>

### <a name="completed-by-column"></a><span data-ttu-id="24ea7-147">Kolumnen Slutförd efter</span><span class="sxs-lookup"><span data-stu-id="24ea7-147">Completed by column</span></span>

<span data-ttu-id="24ea7-148">Spåra vem som har stängt åtgärdsaktiviteten med kolumnen "Slutförd av" på sidan Åtgärd.</span><span class="sxs-lookup"><span data-stu-id="24ea7-148">Track who closed the remediation activity with the "Completed by" column on the Remediation page.</span></span>

- <span data-ttu-id="24ea7-149">**E-postadress:** E-postadressen till den person som slutförde uppgiften manuellt</span><span class="sxs-lookup"><span data-stu-id="24ea7-149">**Email address**: The email of the person who manually completed the task</span></span>
- <span data-ttu-id="24ea7-150">**Systembekräftelse:** Uppgiften slutfördes automatiskt (alla enheter har åtgärdats)</span><span class="sxs-lookup"><span data-stu-id="24ea7-150">**System confirmation**: The task was automatically completed (all devices remediated)</span></span>
- <span data-ttu-id="24ea7-151">**Ej tillgänglig:** Informationen är inte tillgänglig eftersom vi inte vet hur den äldre uppgiften slutfördes</span><span class="sxs-lookup"><span data-stu-id="24ea7-151">**N/A**: Information is not available because we don't know how this older task was completed</span></span>

![Skapad av och slutförd av kolumner med två rader.](images/tvm-completed-by.png)

### <a name="top-remediation-activities-in-the-dashboard"></a><span data-ttu-id="24ea7-154">De viktigaste åtgärdsaktiviteterna på instrumentpanelen</span><span class="sxs-lookup"><span data-stu-id="24ea7-154">Top remediation activities in the dashboard</span></span>

<span data-ttu-id="24ea7-155">Visa **de viktigaste åtgärdsaktiviteterna på instrumentpanelen** [för hantering av hot och sårbarhet.](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="24ea7-155">View **Top remediation activities** in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span> <span data-ttu-id="24ea7-156">Markera någon av posterna för att gå **till sidan** Åtgärd.</span><span class="sxs-lookup"><span data-stu-id="24ea7-156">Select any of the entries to go to the **Remediation** page.</span></span> <span data-ttu-id="24ea7-157">Du kan markera åtgärdsaktiviteten som slutförd när IT-administratörteamet har åtgärdat uppgiften.</span><span class="sxs-lookup"><span data-stu-id="24ea7-157">You can mark the remediation activity as completed after the IT admin team remediates the task.</span></span>

![Exempel på kortet Toppåtgärder-aktiviteter med en tabell som visar de aktiviteter som har genererats från säkerhetsrekommendationer.](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a><span data-ttu-id="24ea7-159">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="24ea7-159">Related articles</span></span>

- [<span data-ttu-id="24ea7-160">Översikt över hot- och sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="24ea7-160">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="24ea7-161">Instrumentpanelen</span><span class="sxs-lookup"><span data-stu-id="24ea7-161">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="24ea7-162">Säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="24ea7-162">Security recommendations</span></span>](tvm-security-recommendation.md)