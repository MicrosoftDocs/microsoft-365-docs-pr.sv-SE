---
title: Säkerhetsrekommendationer med hjälp av hantering av hot och hot
description: Få handlingsbara säkerhetsrekommendationer prioriterade efter hot, risk för intrång och värde, i hot och sårbarhetshantering.
keywords: Hantering av hot och sårbarhet, Microsoft Defender för Endpoint tvm-säkerhetsrekommendationer, rekommendation om cybersäkerhet, rekommendation om säkerhet på åtgärd
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
ms.openlocfilehash: af22bac911339de9c2e02df24a77c1889a33d43a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933739"
---
# <a name="security-recommendations---threat-and-vulnerability-management"></a><span data-ttu-id="17c63-104">Säkerhetsrekommendationer – hantering av hot och hot</span><span class="sxs-lookup"><span data-stu-id="17c63-104">Security recommendations - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="17c63-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="17c63-105">**Applies to:**</span></span>

- [<span data-ttu-id="17c63-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="17c63-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="17c63-107">Hantering av hot och sårbarhet</span><span class="sxs-lookup"><span data-stu-id="17c63-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="17c63-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="17c63-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="17c63-109">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="17c63-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="17c63-110">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="17c63-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="17c63-111">Cybersäkerhet som identifieras i organisationen mappas till rekommendationer om säkerhet som kan åtgärdas och prioriteras efter hur de påverkas.</span><span class="sxs-lookup"><span data-stu-id="17c63-111">Cybersecurity weaknesses identified in your organization are mapped to actionable security recommendations and prioritized by their impact.</span></span> <span data-ttu-id="17c63-112">Prioriterade rekommendationer hjälper till att förkorta tiden för att minimera eller åtgärda säkerhetsproblem och enhetsefterlevnad.</span><span class="sxs-lookup"><span data-stu-id="17c63-112">Prioritized recommendations help shorten the time to mitigate or remediate vulnerabilities and drive compliance.</span></span>

<span data-ttu-id="17c63-113">Varje säkerhetsrekommendationer innehåller åtgärdsåtgärdssteg.</span><span class="sxs-lookup"><span data-stu-id="17c63-113">Each security recommendation includes actionable remediation steps.</span></span> <span data-ttu-id="17c63-114">För att hjälpa till med uppgiftshantering kan rekommendationen också skickas med Hjälp av Microsoft Intune och Konfigurationshanteraren för Microsoft Endpoint.</span><span class="sxs-lookup"><span data-stu-id="17c63-114">To help with task management, the recommendation can also be sent using Microsoft Intune and Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="17c63-115">När hoten liggande ändras ändras även rekommendationen när den kontinuerligt samlar in information från din miljö.</span><span class="sxs-lookup"><span data-stu-id="17c63-115">When the threat landscape changes, the recommendation also changes as it continuously collects information from your environment.</span></span>

>[!TIP]
><span data-ttu-id="17c63-116">E-postmeddelanden om nya sårbarhetshändelser finns i [Konfigurera e-postaviseringar om säkerhetsrisk i Microsoft Defender för slutpunkt](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="17c63-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="how-it-works"></a><span data-ttu-id="17c63-117">Så här fungerar det</span><span class="sxs-lookup"><span data-stu-id="17c63-117">How it works</span></span>

<span data-ttu-id="17c63-118">Varje enhet i organisationen har tre viktiga faktorer som hjälper kunderna att fokusera på rätt saker vid rätt tidpunkt.</span><span class="sxs-lookup"><span data-stu-id="17c63-118">Each device in the organization is scored based on three important factors to help customers to focus on the right things at the right time.</span></span>

- <span data-ttu-id="17c63-119">**Hot** – Egenskaper för svagheter och sårbarheter i din organisations enheter och historik för intrång.</span><span class="sxs-lookup"><span data-stu-id="17c63-119">**Threat** - Characteristics of the vulnerabilities and exploits in your organizations' devices and breach history.</span></span> <span data-ttu-id="17c63-120">Baserat på dessa faktorer visar säkerhetsrekommendationerna motsvarande länkar till aktiva varningar, pågående hotkampanjer och deras motsvarande analysrapporter för hot.</span><span class="sxs-lookup"><span data-stu-id="17c63-120">Based on these factors, the security recommendations show the corresponding links to active alerts, ongoing threat campaigns, and their corresponding threat analytic reports.</span></span>

- <span data-ttu-id="17c63-121">**Risken för** intrång – din organisations säkerhetsstatus och motståndskraft mot hot</span><span class="sxs-lookup"><span data-stu-id="17c63-121">**Breach likelihood** - Your organization's security posture and resilience against threats</span></span>

- <span data-ttu-id="17c63-122">**Affärsvärde** – organisationens tillgångar, kritiska processer och immateriella egenskaper</span><span class="sxs-lookup"><span data-stu-id="17c63-122">**Business value** - Your organization's assets, critical processes, and intellectual properties</span></span>

## <a name="navigate-to-the-security-recommendations-page"></a><span data-ttu-id="17c63-123">Gå till sidan Säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="17c63-123">Navigate to the Security recommendations page</span></span>

<span data-ttu-id="17c63-124">Få åtkomst till sidan Rekommendationer om säkerhet på ett par olika sätt:</span><span class="sxs-lookup"><span data-stu-id="17c63-124">Access the Security recommendations page a few different ways:</span></span>

- <span data-ttu-id="17c63-125">Navigeringsmenyn för hantering av hot och sårbarhet i [Säkerhetscenter för Microsoft Defender](portal-overview.md)</span><span class="sxs-lookup"><span data-stu-id="17c63-125">Threat and vulnerability management navigation menu in the [Microsoft Defender Security Center](portal-overview.md)</span></span>
- <span data-ttu-id="17c63-126">De viktigaste säkerhetsrekommendationerna på [instrumentpanelen för hot och sårbarhetshantering](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="17c63-126">Top security recommendations in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md)</span></span>

<span data-ttu-id="17c63-127">Visa relaterade säkerhetsrekommendationer på följande platser:</span><span class="sxs-lookup"><span data-stu-id="17c63-127">View related security recommendations in the following places:</span></span>

- <span data-ttu-id="17c63-128">Sidan Programvara</span><span class="sxs-lookup"><span data-stu-id="17c63-128">Software page</span></span>
- <span data-ttu-id="17c63-129">Sidan Enhet</span><span class="sxs-lookup"><span data-stu-id="17c63-129">Device page</span></span>

### <a name="navigation-menu"></a><span data-ttu-id="17c63-130">Navigeringsmeny</span><span class="sxs-lookup"><span data-stu-id="17c63-130">Navigation menu</span></span>

<span data-ttu-id="17c63-131">Gå till navigeringsmenyn för hot och sårbarhetshantering och välj **Säkerhetsrekommendationer**.</span><span class="sxs-lookup"><span data-stu-id="17c63-131">Go to the threat and vulnerability management navigation menu and select **Security recommendations**.</span></span> <span data-ttu-id="17c63-132">Sidan innehåller en lista över säkerhetsrekommendationer för de hot och svagheter som finns i organisationen.</span><span class="sxs-lookup"><span data-stu-id="17c63-132">The page contains a list of security recommendations for the threats and vulnerabilities found in your organization.</span></span>

### <a name="top-security-recommendations-in-the-threat-and-vulnerability-management-dashboard"></a><span data-ttu-id="17c63-133">De viktigaste säkerhetsrekommendationerna på instrumentpanelen för hot och sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="17c63-133">Top security recommendations in the threat and vulnerability management dashboard</span></span>

<span data-ttu-id="17c63-134">Under en viss dag som säkerhetsadministratör kan du [](tvm-dashboard-insights.md) titta på instrumentpanelen [](tvm-exposure-score.md) för hantering av hot och risker för att se din exponeringsresultat sida vid sida med Microsoft [Secure Score för enheter.](tvm-microsoft-secure-score-devices.md)</span><span class="sxs-lookup"><span data-stu-id="17c63-134">In a given day as a Security Administrator, you can take a look at the [threat and vulnerability management dashboard](tvm-dashboard-insights.md) to see your [exposure score](tvm-exposure-score.md) side by side with your [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md).</span></span> <span data-ttu-id="17c63-135">Målet är att **minska organisationens** exponering mot  sårbarheter och att öka organisationens enhetssäkerhet för att bli mer flexibel mot attacker mot cybersäkerhetshot.</span><span class="sxs-lookup"><span data-stu-id="17c63-135">The goal is to **lower** your organization's exposure from vulnerabilities, and **increase** your organization's device security to be more resilient against cybersecurity threat attacks.</span></span> <span data-ttu-id="17c63-136">Den översta listan med säkerhetsrekommendationer hjälper dig att uppnå detta mål.</span><span class="sxs-lookup"><span data-stu-id="17c63-136">The top security recommendations list can help you achieve that goal.</span></span>

![Exempel på kortet med de viktigaste säkerhetsrekommendationerna, med fyra säkerhetsrekommendationer.](images/top-security-recommendations350.png)

<span data-ttu-id="17c63-138">De viktigaste säkerhetsrekommendationerna innehåller de förbättringsmöjligheter som prioriterats baserat på de viktiga faktorer som nämns i föregående avsnitt – hot, risk för intrång och värde.</span><span class="sxs-lookup"><span data-stu-id="17c63-138">The top security recommendations list the improvement opportunities prioritized based on the important factors mentioned in the previous section - threat, likelihood to be breached, and value.</span></span> <span data-ttu-id="17c63-139">Om du väljer en rekommendation kommer du till sidan med säkerhetsrekommendationer med mer information.</span><span class="sxs-lookup"><span data-stu-id="17c63-139">Selecting a recommendation will take you to the security recommendations page with more details.</span></span>

## <a name="security-recommendations-overview"></a><span data-ttu-id="17c63-140">Översikt över säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="17c63-140">Security recommendations overview</span></span>

<span data-ttu-id="17c63-141">Visa rekommendationer, antalet svagheter, relaterade komponenter, hotinsikter, antal exponerade enheter, status, åtgärdstyp, åtgärder, påverkan på exponeringsresultatet och Microsoft Secure Score för enheter samt tillhörande taggar.</span><span class="sxs-lookup"><span data-stu-id="17c63-141">View recommendations, the number of weaknesses found, related components, threat insights, number of exposed devices, status, remediation type, remediation activities, impact to your exposure score and Microsoft Secure Score for Devices, and associated tags.</span></span>

<span data-ttu-id="17c63-142">Färgen på diagrammet **Exponerade enheter** ändras när trenden ändras.</span><span class="sxs-lookup"><span data-stu-id="17c63-142">The color of the **Exposed devices** graph changes as the trend changes.</span></span> <span data-ttu-id="17c63-143">Om antalet exponerade enheter är på uppgång ändras färgen till röd.</span><span class="sxs-lookup"><span data-stu-id="17c63-143">If the number of exposed devices is on the rise, the color changes into red.</span></span> <span data-ttu-id="17c63-144">Om antalet exponerade enheter minskar kommer färgen på diagrammet att ändras till grön.</span><span class="sxs-lookup"><span data-stu-id="17c63-144">If there's a decrease in the number of exposed devices, the color of the graph will change into green.</span></span>

>[!NOTE]
><span data-ttu-id="17c63-145">Hantering av hot och sårbarhet visar enheter som används i upp till **30 dagar** sedan.</span><span class="sxs-lookup"><span data-stu-id="17c63-145">Threat and vulnerability management shows devices that were in use up to **30 days** ago.</span></span> <span data-ttu-id="17c63-146">Detta skiljer sig från resten av Microsoft Defender för Endpoint, där en enhet inte har använts på mer än 7 dagar och har statusen Inaktiv.</span><span class="sxs-lookup"><span data-stu-id="17c63-146">This is different from the rest of Microsoft Defender for Endpoint, where if a device has not been in use for more than 7 days it has in an ‘Inactive’ status.</span></span>

![Exempel på startsidan för säkerhetsrekommendationer.](images/tvmsecrec-updated.png)

### <a name="icons"></a><span data-ttu-id="17c63-148">Ikoner</span><span class="sxs-lookup"><span data-stu-id="17c63-148">Icons</span></span>

<span data-ttu-id="17c63-149">Användbara ikoner kan också snabbt uppmärksamma dig på:</span><span class="sxs-lookup"><span data-stu-id="17c63-149">Useful icons also quickly call your attention to:</span></span>
- ![pil som klickar på ett mål](images/tvm_alert_icon.png) <span data-ttu-id="17c63-151">möjliga aktiva aviseringar</span><span class="sxs-lookup"><span data-stu-id="17c63-151">possible active alerts</span></span>
- ![röd bugg](images/tvm_bug_icon.png) <span data-ttu-id="17c63-153">tillhörande offentliga sårbarheter</span><span class="sxs-lookup"><span data-stu-id="17c63-153">associated public exploits</span></span>
- ![glödlampa](images/tvm_insight_icon.png) <span data-ttu-id="17c63-155">rekommendationsinformation</span><span class="sxs-lookup"><span data-stu-id="17c63-155">recommendation insights</span></span>

### <a name="explore-security-recommendation-options"></a><span data-ttu-id="17c63-156">Utforska alternativ för säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="17c63-156">Explore security recommendation options</span></span>

<span data-ttu-id="17c63-157">Välj den säkerhetsrekommendationer som du vill undersöka eller bearbeta.</span><span class="sxs-lookup"><span data-stu-id="17c63-157">Select the security recommendation that you want to investigate or process.</span></span>

![Exempel på en utfällingssida med säkerhetsrekommendationer.](images/secrec-flyouteolsw.png)

<span data-ttu-id="17c63-159">Du kan välja något av följande alternativ i den utfällade den:</span><span class="sxs-lookup"><span data-stu-id="17c63-159">From the flyout, you can choose any of the following options:</span></span>

- <span data-ttu-id="17c63-160">**Öppna programvarusidan** – Öppna programvarusidan för att få mer kontext över programvaran och hur den distribueras.</span><span class="sxs-lookup"><span data-stu-id="17c63-160">**Open software page** - Open the software page to get more context on the software and how it's distributed.</span></span> <span data-ttu-id="17c63-161">Informationen kan omfatta hotsammanhang, associerade rekommendationer, identifierade svagheter, antal exponerade enheter, identifierade säkerhetsproblem, namn och detaljerad information om enheter med programvaran installerad samt versionsdistribution.</span><span class="sxs-lookup"><span data-stu-id="17c63-161">The information can include threat context, associated recommendations, weaknesses discovered, number of exposed devices, discovered vulnerabilities, names and detailed of devices with the software installed, and version distribution.</span></span>

- <span data-ttu-id="17c63-162">[**Åtgärdsalternativ –**](tvm-remediation.md) Skicka en begäran om åtgärd för att öppna ett ärende i Microsoft Intune, så att IT-administratören kan svara och ange adress.</span><span class="sxs-lookup"><span data-stu-id="17c63-162">[**Remediation options**](tvm-remediation.md) - Submit a remediation request to open a ticket in Microsoft Intune for your IT administrator to pick up and address.</span></span> <span data-ttu-id="17c63-163">Spåra åtgärdsaktiviteten på sidan Åtgärd.</span><span class="sxs-lookup"><span data-stu-id="17c63-163">Track the remediation activity in the Remediation page.</span></span>

- <span data-ttu-id="17c63-164">[**Undantagsalternativ**](tvm-exception.md) – Skicka ett undantag, ange justering och ange varaktighet för undantag om du inte kan åtgärda problemet ännu.</span><span class="sxs-lookup"><span data-stu-id="17c63-164">[**Exception options**](tvm-exception.md) - Submit an exception, provide justification, and set exception duration if you can't remediate the issue yet.</span></span>

>[!NOTE]
><span data-ttu-id="17c63-165">När en programvaruändring görs på en enhet tar det normalt 2 timmar innan data återspeglas i säkerhetsportalen.</span><span class="sxs-lookup"><span data-stu-id="17c63-165">When a software change is made on a device, it typically takes 2 hours for the data to be reflected in the security portal.</span></span> <span data-ttu-id="17c63-166">Ibland kan det dock ta längre tid.</span><span class="sxs-lookup"><span data-stu-id="17c63-166">However, it may sometimes take longer.</span></span> <span data-ttu-id="17c63-167">Det kan ta allt från 4 till 24 timmar att ändra konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="17c63-167">Configuration changes can take anywhere from 4 to 24 hours.</span></span>

### <a name="investigate-changes-in-device-exposure-or-impact"></a><span data-ttu-id="17c63-168">Undersöka ändringar av exponering av enhet eller påverkan</span><span class="sxs-lookup"><span data-stu-id="17c63-168">Investigate changes in device exposure or impact</span></span>

<span data-ttu-id="17c63-169">Om antalet exponerade enheter ökar stort, eller om det är en stark ökning av effekterna på exponeringsresultatet för organisationen och Microsoft Secure Score för enheter, bör säkerhetsrekommendationer undersökas.</span><span class="sxs-lookup"><span data-stu-id="17c63-169">If there is a large jump in the number of exposed devices, or a sharp increase in the impact on your organization exposure score and Microsoft Secure Score for Devices, then that security recommendation is worth investigating.</span></span>

1. <span data-ttu-id="17c63-170">Välj rekommendationen och **sidan Öppna programvara**</span><span class="sxs-lookup"><span data-stu-id="17c63-170">Select the recommendation and **Open software page**</span></span>
2. <span data-ttu-id="17c63-171">Välj **tidslinjefliken** Händelse för att visa alla effektfulla händelser relaterade till den programvaran, till exempel nya säkerhetsproblem eller nya offentliga sårbarheter.</span><span class="sxs-lookup"><span data-stu-id="17c63-171">Select the **Event timeline** tab to view all the impactful events related to that software, such as new vulnerabilities or new public exploits.</span></span> [<span data-ttu-id="17c63-172">Läs mer om tidslinjen för händelser</span><span class="sxs-lookup"><span data-stu-id="17c63-172">Learn more about event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
3. <span data-ttu-id="17c63-173">Bestäm hur du ska åtgärda den ökade eller organisationens exponering, t.ex. att skicka en begäran om åtgärd</span><span class="sxs-lookup"><span data-stu-id="17c63-173">Decide how to address the increase or your organization's exposure, such as submitting a remediation request</span></span>

## <a name="request-remediation"></a><span data-ttu-id="17c63-174">Begära åtgärd</span><span class="sxs-lookup"><span data-stu-id="17c63-174">Request remediation</span></span>

<span data-ttu-id="17c63-175">Funktionen för åtgärder för hantering av hot och sårbarhet överbrygger mellanrummet mellan säkerhet och IT-administratörer genom arbetsflödet för åtgärdsförfrågningar.</span><span class="sxs-lookup"><span data-stu-id="17c63-175">The threat and vulnerability management remediation capability bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="17c63-176">Som säkerhetsadministratörer kan du begära att IT-administratören åtgärdar ett problem från rekommendationssidan **för** säkerhet till Intune.</span><span class="sxs-lookup"><span data-stu-id="17c63-176">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** page to Intune.</span></span> [<span data-ttu-id="17c63-177">Läs mer om alternativ för åtgärder</span><span class="sxs-lookup"><span data-stu-id="17c63-177">Learn more about remediation options</span></span>](tvm-remediation.md)

### <a name="how-to-request-remediation"></a><span data-ttu-id="17c63-178">Så här begär du åtgärd</span><span class="sxs-lookup"><span data-stu-id="17c63-178">How to request remediation</span></span>

<span data-ttu-id="17c63-179">Välj en säkerhetsrekommendationer som du vill begära åtgärd för och välj sedan **Åtgärdsalternativ.**</span><span class="sxs-lookup"><span data-stu-id="17c63-179">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span> <span data-ttu-id="17c63-180">Fyll i formuläret och välj **Skicka begäran**.</span><span class="sxs-lookup"><span data-stu-id="17c63-180">Fill out the form and select **Submit request**.</span></span> <span data-ttu-id="17c63-181">Gå till [**sidan Åtgärd för**](tvm-remediation.md) att visa status för din begäran om åtgärd.</span><span class="sxs-lookup"><span data-stu-id="17c63-181">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span> [<span data-ttu-id="17c63-182">Läs mer om hur du begär åtgärd</span><span class="sxs-lookup"><span data-stu-id="17c63-182">Learn more about how to request remediation</span></span>](tvm-remediation.md#request-remediation)

## <a name="file-for-exception"></a><span data-ttu-id="17c63-183">Fil för undantag</span><span class="sxs-lookup"><span data-stu-id="17c63-183">File for exception</span></span>

<span data-ttu-id="17c63-184">Som ett alternativ till en begäran om åtgärd när en rekommendation inte är relevant för tillfället kan du skapa undantag för rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="17c63-184">As an alternative to a remediation request when a recommendation is not relevant at the moment, you can create exceptions for recommendations.</span></span> [<span data-ttu-id="17c63-185">Läs mer om undantag</span><span class="sxs-lookup"><span data-stu-id="17c63-185">Learn more about exceptions</span></span>](tvm-exception.md)

<span data-ttu-id="17c63-186">Endast användare med behörigheten "undantagshantering" kan lägga till undantag.</span><span class="sxs-lookup"><span data-stu-id="17c63-186">Only users with “exceptions handling” permissions can add exception.</span></span> <span data-ttu-id="17c63-187">[Läs mer om RBAC-roller.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="17c63-187">[Learn more about RBAC roles](user-roles.md).</span></span>

<span data-ttu-id="17c63-188">När ett undantag skapas för en rekommendation är rekommendationen inte längre aktiv.</span><span class="sxs-lookup"><span data-stu-id="17c63-188">When an exception is created for a recommendation, the recommendation is no longer active.</span></span> <span data-ttu-id="17c63-189">Rekommendationstillståndet ändras till **Fullständigt undantag eller** Delvis **undantag** (efter enhetsgrupp).</span><span class="sxs-lookup"><span data-stu-id="17c63-189">The recommendation state will change to **Full exception** or **Partial exception** (by device group).</span></span>

### <a name="how-to-create-an-exception"></a><span data-ttu-id="17c63-190">Så här skapar du ett undantag</span><span class="sxs-lookup"><span data-stu-id="17c63-190">How to create an exception</span></span>

<span data-ttu-id="17c63-191">Välj en säkerhetsrekommendationer som du vill skapa ett undantag för och välj sedan **Undantagsalternativ**.</span><span class="sxs-lookup"><span data-stu-id="17c63-191">Select a security recommendation you would like create an exception for, and then select **Exception options**.</span></span>  

![Visar var knappen för "undantagsalternativ" är platsen i en utfällsalternativ för säkerhetsrekommendationer.](images/tvm-exception-options.png)

<span data-ttu-id="17c63-193">Fyll i formuläret och skicka.</span><span class="sxs-lookup"><span data-stu-id="17c63-193">Fill out the form and submit.</span></span> <span data-ttu-id="17c63-194">Om du vill visa alla dina undantag [](tvm-remediation.md) (nuvarande och tidigare) går du till sidan Åtgärd under **menyn & Vulnerability Management** och väljer **fliken** Undantag. Läs mer om hur du skapar ett [undantag](tvm-exception.md#create-an-exception)</span><span class="sxs-lookup"><span data-stu-id="17c63-194">To view all your exceptions (current and past), navigate to the [Remediation](tvm-remediation.md) page under the **Threat & Vulnerability Management** menu and select the **Exceptions** tab. [Learn more about how to create an exception](tvm-exception.md#create-an-exception)</span></span>

## <a name="report-inaccuracy"></a><span data-ttu-id="17c63-195">Rapportera felaktigheter</span><span class="sxs-lookup"><span data-stu-id="17c63-195">Report inaccuracy</span></span>

<span data-ttu-id="17c63-196">Du kan rapportera en falsk positivhet när du ser någon vag, felaktig, ofullständig eller redan åtgärdad information om säkerhetsrekommendationer.</span><span class="sxs-lookup"><span data-stu-id="17c63-196">You can report a false positive when you see any vague, inaccurate, incomplete, or already remediated security recommendation information.</span></span>

1. <span data-ttu-id="17c63-197">Öppna rekommendationen Säkerhet.</span><span class="sxs-lookup"><span data-stu-id="17c63-197">Open the Security recommendation.</span></span>

2. <span data-ttu-id="17c63-198">Välj de tre punkterna bredvid den säkerhetsrekommendationer som du vill rapportera och välj **sedan Rapportinkurs.**</span><span class="sxs-lookup"><span data-stu-id="17c63-198">Select the three dots beside the security recommendation that you want to report,  then select **Report inaccuracy**.</span></span>

    ![Visar var knappen "Rapportinfall" finns i en utfällingsknapp för säkerhetsrekommendationer.](images/report-inaccuracy500.png)

3. <span data-ttu-id="17c63-200">I den utfällliga fönsterrutan väljer du kategorin felaktigheter i den nedrullningsmenyn, fyller i din e-postadress och information om felaktigheter.</span><span class="sxs-lookup"><span data-stu-id="17c63-200">From the flyout pane, select the inaccuracy category from the drop-down menu, fill in your email address, and details regarding the inaccuracy.</span></span>

4. <span data-ttu-id="17c63-201">Välj **Skicka**.</span><span class="sxs-lookup"><span data-stu-id="17c63-201">Select **Submit**.</span></span> <span data-ttu-id="17c63-202">Din feedback skickas omedelbart till experter på hot och sårbarhetshantering.</span><span class="sxs-lookup"><span data-stu-id="17c63-202">Your feedback is immediately sent to the threat and vulnerability management experts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="17c63-203">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="17c63-203">Related articles</span></span>

- [<span data-ttu-id="17c63-204">Översikt över hot- och sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="17c63-204">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="17c63-205">Instrumentpanelen</span><span class="sxs-lookup"><span data-stu-id="17c63-205">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="17c63-206">Exponeringsvärde</span><span class="sxs-lookup"><span data-stu-id="17c63-206">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="17c63-207">Microsoft Secure Score för enheter</span><span class="sxs-lookup"><span data-stu-id="17c63-207">Microsoft Secure Score for Devices</span></span>](tvm-microsoft-secure-score-devices.md)
- [<span data-ttu-id="17c63-208">Åtgärda säkerhetsproblem</span><span class="sxs-lookup"><span data-stu-id="17c63-208">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="17c63-209">Skapa och visa undantag för säkerhetsrekommendationer</span><span class="sxs-lookup"><span data-stu-id="17c63-209">Create and view exceptions for security recommendations</span></span>](tvm-exception.md)
- [<span data-ttu-id="17c63-210">Tidlinje för händelse</span><span class="sxs-lookup"><span data-stu-id="17c63-210">Event timeline</span></span>](threat-and-vuln-mgt-event-timeline.md)
