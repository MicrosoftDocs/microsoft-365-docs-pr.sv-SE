---
title: Microsoft Defender för slutpunkt i Säkerhetscenter för Microsoft 365
description: Läs mer om ändringar från Microsoft Defender Säkerhetscenter till Microsoft 365 Säkerhetscenter
keywords: Komma igång med Microsoft 365 säkerhetscenter, OATP, MDATP, MDO, MDE, en fönsterruta, konvergerad portal, säkerhetsportal, defender säkerhetsportal
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 03b73901512522edec7fdbc579eaf4073eed5d48
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167473"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a><span data-ttu-id="ac9c6-104">Microsoft Defender för slutpunkt i Säkerhetscenter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac9c6-104">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="ac9c6-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ac9c6-105">**Applies to:**</span></span>

- [<span data-ttu-id="ac9c6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ac9c6-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="ac9c6-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="ac9c6-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="ac9c6-108">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="ac9c6-108">Microsoft Defender for Office 365</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)

<span data-ttu-id="ac9c6-109">Det förbättrade [säkerhetscentret i Microsoft 365](overview-security-center.md) kombinerar säkerhetsfunktioner som skyddar, identifierar, undersöker och svarar på e-post, samarbete, identitet [https://security.microsoft.com](https://security.microsoft.com) och enhetshot.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-109">The improved [Microsoft 365 security center](overview-security-center.md) at [https://security.microsoft.com](https://security.microsoft.com) combines security capabilities that protect, detect, investigate, and respond to email, collaboration, identity, and device threats.</span></span> <span data-ttu-id="ac9c6-110">I det här säkerhetscentret samlas funktioner från befintliga Microsoft-säkerhetsportaler, bland annat Microsoft Defender Säkerhetscenter och Office 365 Säkerhets- & Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-110">This security center brings together functionality from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span>

<span data-ttu-id="ac9c6-111">Om du är bekant med Microsoft Defender Säkerhetscenter beskriver den här artikeln några av de ändringar och förbättringar som har gjorts i det förbättrade säkerhetscentret i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-111">If you're familiar with the Microsoft Defender Security Center, this article helps describe some of the changes and improvements in the improved Microsoft 365 security center.</span></span> <span data-ttu-id="ac9c6-112">Det finns dock några nya och uppdaterade element som du bör känna till.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-112">However there are some new and updated elements to be aware of.</span></span>

<span data-ttu-id="ac9c6-113">Microsoft Defender [Säkerhetscenter har historiskt varit](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) ett hem för Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-113">Historically, the [Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/portal-overview) has been the home for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="ac9c6-114">Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-114">Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> <span data-ttu-id="ac9c6-115">För att minska antalet portaler är Microsoft 365 säkerhetscenter ett hem för övervakning och hantering av säkerhet i dina Microsoft-identiteter, data, enheter, appar och infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-115">To help reduce the number of portals, the Microsoft 365 security center will be the home for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac9c6-116">Vad du ser i Microsoft 365 säkerhetscenter beror på dina aktuella prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-116">What you see in the Microsoft 365 security center depends on your current subscriptions.</span></span> <span data-ttu-id="ac9c6-117">Om du till exempel inte har en licens för Microsoft Defender för Office 365 visas inte avsnittet & e-postsamarbete.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-117">For example, if you don't have a license for Microsoft Defender for Office 365, then the Email & Collaboration section will not be shown.</span></span>

<span data-ttu-id="ac9c6-118">Ta en titt på det förbättrade säkerhetscentret i Microsoft 365: [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="ac9c6-118">Take a look at the improved Microsoft 365 security center: [https://security.microsoft.com](https://security.microsoft.com).</span></span>

<span data-ttu-id="ac9c6-119">Läs mer om fördelarna: [Översikt över Säkerhetscenter i Microsoft 365](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="ac9c6-119">Learn more about the benefits: [Overview of the Microsoft 365 security center](overview-security-center.md)</span></span>

## <a name="whats-changed"></a><span data-ttu-id="ac9c6-120">Vad har ändrats</span><span class="sxs-lookup"><span data-stu-id="ac9c6-120">What's changed</span></span>

<span data-ttu-id="ac9c6-121">Den här tabellen är en snabbreferens över ändringarna mellan Microsoft Defender Säkerhetscenter och Microsoft 365 säkerhetscenter.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-121">This table is a quick reference of the changes between the Microsoft Defender Security Center and the Microsoft 365 security center.</span></span>

### <a name="alerts-and-actions"></a><span data-ttu-id="ac9c6-122">Varningar och åtgärder</span><span class="sxs-lookup"><span data-stu-id="ac9c6-122">Alerts and actions</span></span>

|<span data-ttu-id="ac9c6-123">**Område**</span><span class="sxs-lookup"><span data-stu-id="ac9c6-123">**Area**</span></span>  |<span data-ttu-id="ac9c6-124">**Beskrivning av ändring**</span><span class="sxs-lookup"><span data-stu-id="ac9c6-124">**Description of change**</span></span>  |
|---------|---------|
| [<span data-ttu-id="ac9c6-125">Incidenter & aviseringar</span><span class="sxs-lookup"><span data-stu-id="ac9c6-125">Incidents & alerts</span></span>](incidents-overview.md)  | <span data-ttu-id="ac9c6-126">I Säkerhetscenter för Microsoft 365 kan du hantera incidenter och aviseringar för alla slutpunkter, e-post och identiteter.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-126">In the Microsoft 365 security center, you can manage incidents and alerts across all of your endpoints, email, and identities.</span></span> <span data-ttu-id="ac9c6-127">Vi har konvergerat upplevelsen för att lättare hitta relaterade händelser.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-127">We've converged the experience to help you find related events more easily.</span></span> <span data-ttu-id="ac9c6-128">Mer information finns i [Incidentöversikt.](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ac9c6-128">For more information, see [Incidents Overview](incidents-overview.md).</span></span>   |
| [<span data-ttu-id="ac9c6-129">Jägning</span><span class="sxs-lookup"><span data-stu-id="ac9c6-129">Hunting</span></span>](advanced-hunting-overview.md)  |  <span data-ttu-id="ac9c6-130">Om du ändrar anpassade identifieringsregler som skapats i Microsoft Defender för Endpoint för att inkludera identitets- och e-posttabeller flyttas de automatiskt till Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-130">Modifying custom detection rules created in Microsoft Defender for Endpoint to include identity and email tables automatically moves them to Microsoft 365 Defender.</span></span> <span data-ttu-id="ac9c6-131">Motsvarande aviseringar visas också i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-131">Their corresponding alerts will also appear in Microsoft 365 Defender.</span></span> <span data-ttu-id="ac9c6-132">Mer information om dessa ändringar finns i [Migrera regler för anpassad identifiering.](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules)</span><span class="sxs-lookup"><span data-stu-id="ac9c6-132">For more details about these changes, read [Migrate custom detection rules](advanced-hunting-migrate-from-mdatp.md#migrate-custom-detection-rules).</span></span> <span data-ttu-id="ac9c6-133">Tabellen `DeviceAlertEvents` för avancerad sökning finns inte i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-133">The `DeviceAlertEvents` table for advanced hunting isn't available in Microsoft 365 Defender.</span></span> <span data-ttu-id="ac9c6-134">Om du vill fråga om enhetsspecifik aviseringsinformation i Microsoft 365 Defender kan du använda tabellerna och tabellerna för att få plats med ännu mer information från `AlertInfo` `AlertEvidence` en rad olika källor.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-134">To query device-specific alert information in Microsoft 365 Defender, you can use the `AlertInfo` and `AlertEvidence` tables to accommodate even more information from a diverse set of sources.</span></span> <span data-ttu-id="ac9c6-135">Skapa nästa enhetsrelaterade fråga genom att följa [skrivfrågor utan DeviceAlertEvents.](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents)</span><span class="sxs-lookup"><span data-stu-id="ac9c6-135">Craft your next device-related query by following [Write queries without DeviceAlertEvents](advanced-hunting-migrate-from-mdatp.md#write-queries-without-devicealertevents).</span></span>|
|[<span data-ttu-id="ac9c6-136">Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="ac9c6-136">Action center</span></span>](mtp-action-center.md)    | <span data-ttu-id="ac9c6-137">Listor med väntande och slutförda åtgärder som utförts efter automatiserade undersökningar och åtgärdsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-137">Lists pending and completed actions that were taken following automated investigations and remediation actions.</span></span> <span data-ttu-id="ac9c6-138">Åtgärdscenter i Microsoft Defender Säkerhetscenter listade väntande och slutförda åtgärder för åtgärder som vidtas endast på enheter, medan automatiserade undersökningar listade varningar och status.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-138">Formerly, the Action center in the Microsoft Defender Security Center listed pending and completed actions for remediation actions taken on devices only, while Automated investigations listed alerts and status.</span></span> <span data-ttu-id="ac9c6-139">I det förbättrade säkerhetscentret i Microsoft 365 sammanför åtgärdscenter åtgärder och undersökningar för e-post, enheter och användare – allt på en plats.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-139">In the  improved Microsoft 365 security center, the Action center brings together remediation actions and investigations across email, devices, and users—all in one location.</span></span>  |
| [<span data-ttu-id="ac9c6-140">Analys av hot</span><span class="sxs-lookup"><span data-stu-id="ac9c6-140">Threat analytics</span></span>](threat-analytics.md) |  <span data-ttu-id="ac9c6-141">Flyttades högst upp i navigeringsfältet för enklare identifiering och användning.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-141">Moved to the top of the navigation bar for easier discovery and use.</span></span> <span data-ttu-id="ac9c6-142">Innehåller nu information om hot för både slutpunkter och e-post och samarbete.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-142">Now includes threat information for both endpoints and email and collaboration.</span></span>    |

### <a name="endpoints"></a><span data-ttu-id="ac9c6-143">Slutpunkter</span><span class="sxs-lookup"><span data-stu-id="ac9c6-143">Endpoints</span></span>

|<span data-ttu-id="ac9c6-144">**Område**</span><span class="sxs-lookup"><span data-stu-id="ac9c6-144">**Area**</span></span>  |<span data-ttu-id="ac9c6-145">**Beskrivning av ändring**</span><span class="sxs-lookup"><span data-stu-id="ac9c6-145">**Description of change**</span></span>  |
|---------|---------|
|<span data-ttu-id="ac9c6-146">Sök</span><span class="sxs-lookup"><span data-stu-id="ac9c6-146">Search</span></span>   |  <span data-ttu-id="ac9c6-147">I stället för att vara i rubriken flyttas microsoft Defender för slutpunktssökfältet under avsnittet Slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-147">Instead of being in the heading, Microsoft Defender for Endpoint search bar is moving under the Endpoints section.</span></span> <span data-ttu-id="ac9c6-148">Du kan fortsätta att söka efter enheter, filer, användare, URL:er, IP-adresser, svagheter, programvara och rekommendationer.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-148">You can continue to search for devices, files, users, URLs, IPs, vulnerabilities, software, and recommendations.</span></span>  |
|[<span data-ttu-id="ac9c6-149">Instrumentpanelen</span><span class="sxs-lookup"><span data-stu-id="ac9c6-149">Dashboard</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  <span data-ttu-id="ac9c6-150">Det här är instrumentpanelen för säkerhetsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-150">This is your security operations dashboard.</span></span> <span data-ttu-id="ac9c6-151">Se en översikt över hur många aktiva aviseringar som utlöstes, vilka enheter som är i riskzonen, vilka användare som är på risknivå och allvarlighetsnivå för aviseringar, enheter och användare.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-151">See an overview of how many active alerts were triggered, which devices are at risk, which users are at risk, and severity level for alerts, devices, and users.</span></span> <span data-ttu-id="ac9c6-152">Du kan också se om några enheter har sensorproblem, din allmänna tjänsthälsa och hur omatchade aviseringar har upptäckts.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-152">You can also see if any devices have sensor issues, your overall service health, and how any unresolved alerts were detected.</span></span> |
|<span data-ttu-id="ac9c6-153">Enhetsinventering</span><span class="sxs-lookup"><span data-stu-id="ac9c6-153">Device inventory</span></span> | <span data-ttu-id="ac9c6-154">Inga ändringar.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-154">No changes.</span></span> |
|[<span data-ttu-id="ac9c6-155">Sårbarhetshantering</span><span class="sxs-lookup"><span data-stu-id="ac9c6-155">Vulnerability management</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    <span data-ttu-id="ac9c6-156">Namnet förkortades så att det passar i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-156">Name was shortened to fit in the navigation pane.</span></span> <span data-ttu-id="ac9c6-157">Det är samma som avsnittet om hantering av hot och sårbarhet, med alla sidor undertill.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-157">It's the same as the threat and vulnerability management section, with all the pages underneath.</span></span>     |
| <span data-ttu-id="ac9c6-158">Partner och API:er</span><span class="sxs-lookup"><span data-stu-id="ac9c6-158">Partners and APIs</span></span> | <span data-ttu-id="ac9c6-159">Inga ändringar.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-159">No changes.</span></span> |
| <span data-ttu-id="ac9c6-160">Utvärderingar & självstudiekurser</span><span class="sxs-lookup"><span data-stu-id="ac9c6-160">Evaluations & tutorials</span></span>    |     <span data-ttu-id="ac9c6-161">Nya test- och inlärningsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-161">New testing and learning capabilities.</span></span>     |
| <span data-ttu-id="ac9c6-162">Konfigurationshantering</span><span class="sxs-lookup"><span data-stu-id="ac9c6-162">Configuration management</span></span>   |  <span data-ttu-id="ac9c6-163">Inga ändringar.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-163">No changes.</span></span>  |

> [!NOTE]
> <span data-ttu-id="ac9c6-164">**Automatisk undersökning och åtgärd är** nu en del av incidenter.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-164">**Automatic investigation and remediation** is now a part of  incidents.</span></span> <span data-ttu-id="ac9c6-165">Du kan se händelser för automatisk undersökning och åtgärd på fliken **> Incidentundersökning.**</span><span class="sxs-lookup"><span data-stu-id="ac9c6-165">You can see Automated  investigation and remediation events in the **Incident > Investigation** tab.</span></span>

### <a name="access-and-reporting"></a><span data-ttu-id="ac9c6-166">Access och rapportering</span><span class="sxs-lookup"><span data-stu-id="ac9c6-166">Access and reporting</span></span>

|<span data-ttu-id="ac9c6-167">**Område**</span><span class="sxs-lookup"><span data-stu-id="ac9c6-167">**Area**</span></span>  |<span data-ttu-id="ac9c6-168">**Beskrivning av ändring**</span><span class="sxs-lookup"><span data-stu-id="ac9c6-168">**Description of change**</span></span>  |
|---------|---------|
| <span data-ttu-id="ac9c6-169">Rapporter</span><span class="sxs-lookup"><span data-stu-id="ac9c6-169">Reports</span></span>  | <span data-ttu-id="ac9c6-170">Se rapporter för slutpunkter och e-& samarbete, inklusive skydd mot hot, enhetens hälsa och efterlevnad och sårbara enheter.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-170">See reports for endpoints and email & collaboration, including Threat protection, Device health and compliance, and Vulnerable devices.</span></span> |
| <span data-ttu-id="ac9c6-171">Hälsa</span><span class="sxs-lookup"><span data-stu-id="ac9c6-171">Health</span></span>  |  <span data-ttu-id="ac9c6-172">Länkar för närvarande ut till sidan Tjänstens hälsa i administrationscentret för [Microsoft 365.](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="ac9c6-172">Currently links out to the "Service health" page in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> |
| <span data-ttu-id="ac9c6-173">Inställningar</span><span class="sxs-lookup"><span data-stu-id="ac9c6-173">Settings</span></span> |  <span data-ttu-id="ac9c6-174">Hantera dina inställningar för Microsoft 365 säkerhetscenter, Microsoft 365 Defender, slutpunkter, e-& samarbete, identiteter och enhetsidentifiering.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-174">Manage your settings for the Microsoft 365 security center, Microsoft 365 Defender, Endpoints, Email & collaboration, Identities, and Device discovery.</span></span>   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a><span data-ttu-id="ac9c6-175">Säkerhetsnavigering och funktioner i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac9c6-175">Microsoft 365 security navigation and capabilities</span></span>

<span data-ttu-id="ac9c6-176">Det vänstra navigeringsfältet, eller snabbstartfältet, ser bekant ut.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-176">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="ac9c6-177">Det finns dock några nya och uppdaterade element i det här säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-177">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="ac9c6-178">Incidenter och aviseringar</span><span class="sxs-lookup"><span data-stu-id="ac9c6-178">Incidents and alerts</span></span>

<span data-ttu-id="ac9c6-179">Sammanför incidenter och aviseringshantering i din e-post, dina enheter och identiteter.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-179">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="ac9c6-180">På aviseringssidan får du fullständig kontext till aviseringen genom att kombinera attacksignaler för att skapa en detaljerad berättelse.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-180">The alert page provides full context to the alert by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="ac9c6-181">En ny enhetlig upplevelse sammanför nu en enhetlig vy av aviseringar för alla arbetsbelastningar.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-181">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="ac9c6-182">Du kan snabbt ändra, undersöka och vidta effektiva åtgärder.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-182">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="ac9c6-183">Läs mer om incidenter</span><span class="sxs-lookup"><span data-stu-id="ac9c6-183">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="ac9c6-184">Läs mer om att hantera aviseringar</span><span class="sxs-lookup"><span data-stu-id="ac9c6-184">Learn more about managing alerts</span></span>](investigate-alerts.md)

![Snabbstartsfältet Aviseringar och åtgärder](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a><span data-ttu-id="ac9c6-186">Jägning</span><span class="sxs-lookup"><span data-stu-id="ac9c6-186">Hunting</span></span>

<span data-ttu-id="ac9c6-187">Proaktivt söka efter hot, skadlig programvara och skadlig aktivitet i slutpunkter, Office 365-postlådor och mycket mer med hjälp av avancerade [sökningsfrågor.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ac9c6-187">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="ac9c6-188">Dessa kraftfulla frågor kan användas för att hitta och granska hotindikatorer och -enheter för både kända och potentiella hot.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-188">These powerful queries can be used to locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="ac9c6-189">[Anpassade identifieringsregler kan](custom-detection-rules.md) byggas från avancerade sökfrågor för att hjälpa dig att proaktivt hålla utkik efter händelser som kan vara misslyckad av intrångsaktivitet och felkonfigurerade enheter.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-189">[Custom detection rules](custom-detection-rules.md) can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>


### <a name="action-center"></a><span data-ttu-id="ac9c6-190">Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="ac9c6-190">Action center</span></span>

<span data-ttu-id="ac9c6-191">I åtgärdscenter visas undersökningar som skapats med automatisk undersökning och svarsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-191">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="ac9c6-192">Den här automatiska självbetjäningsprocessen i Microsoft 365 Defender kan hjälpa säkerhetsteam genom att automatiskt svara på specifika händelser.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-192">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

[<span data-ttu-id="ac9c6-193">Läs mer om Åtgärdscenter</span><span class="sxs-lookup"><span data-stu-id="ac9c6-193">Learn more about the Action center</span></span>](mtp-action-center.md)

### <a name="threat-analytics"></a><span data-ttu-id="ac9c6-194">Hotanalys</span><span class="sxs-lookup"><span data-stu-id="ac9c6-194">Threat Analytics</span></span>

<span data-ttu-id="ac9c6-195">Få information om hot från en expert på Microsoft-säkerhet.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-195">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="ac9c6-196">Hotanalys hjälper säkerhetsteam att bli effektivare när de står inför nya hot.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-196">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="ac9c6-197">Hotanalys omfattar:</span><span class="sxs-lookup"><span data-stu-id="ac9c6-197">Threat Analytics includes:</span></span>

- <span data-ttu-id="ac9c6-198">E-postrelaterade identifieringar och åtgärder från Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-198">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="ac9c6-199">Detta är utöver de slutpunktsdata som redan är tillgängliga från Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-199">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="ac9c6-200">Vyn Incidenter som är relaterad till hoten.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-200">Incidents view related to the threats.</span></span>
- <span data-ttu-id="ac9c6-201">Förbättrad upplevelse för att snabbt identifiera och använda användbar information i rapporterna.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-201">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span>

<span data-ttu-id="ac9c6-202">Du kan komma åt hotanalyser antingen från det övre vänstra navigeringsfältet i Säkerhetscenter för Microsoft 365 eller från ett dedikerat instrumentpanelskort som visar de viktigaste hoten för din organisation.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-202">You can access threat analytics either from the upper left navigation bar in the Microsoft 365 security center, or from a dedicated dashboard card that shows the top threats for your organization.</span></span>

<span data-ttu-id="ac9c6-203">Läs mer om hur du [spårar och svarar på nya hot med hotanalyser](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)</span><span class="sxs-lookup"><span data-stu-id="ac9c6-203">Learn more about how to [track and respond to emerging threats with threat analytics](https://docs.microsoft.com/microsoft-365/security/mtp/threat-analytics)</span></span>

### <a name="endpoints-section"></a><span data-ttu-id="ac9c6-204">Avsnittet Slutpunkter</span><span class="sxs-lookup"><span data-stu-id="ac9c6-204">Endpoints section</span></span>

<span data-ttu-id="ac9c6-205">Visa och hantera säkerheten för slutpunkter i din organisation.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-205">View and manage the security of endpoints in your organization.</span></span> <span data-ttu-id="ac9c6-206">Om du har använt Microsoft Defender Säkerhetscenter ser det bekant ut.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-206">If you've used the Microsoft Defender Security Center, it will look familiar.</span></span>

![Snabbstartfältet för slutpunkter](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a><span data-ttu-id="ac9c6-208">Access och rapporter</span><span class="sxs-lookup"><span data-stu-id="ac9c6-208">Access and reports</span></span>

<span data-ttu-id="ac9c6-209">Visa rapporter, ändra dina inställningar och ändra användarroller.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-209">View reports, change your settings, and modify user roles.</span></span>

![Snabbstartfältet för Access och rapportering](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a><span data-ttu-id="ac9c6-211">SIEM API-anslutningar</span><span class="sxs-lookup"><span data-stu-id="ac9c6-211">SIEM API connections</span></span>

<span data-ttu-id="ac9c6-212">Om du använder [Defender för Slutpunkt SIEM API](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md)kan du fortsätta att göra det.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-212">If you use the [Defender for Endpoint SIEM API](/windows/security/threat-protection/microsoft-defender-atp/enable-siem-integration.md), you can continue to do so.</span></span> <span data-ttu-id="ac9c6-213">Vi har lagt till nya länkar i API-nyttolasten som pekar på aviseringssidan eller incidentsidan i Microsoft 365-säkerhetsportalen.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-213">We’ve added new links on the API payload that point to the alert page or the incident page in the Microsoft 365 security portal.</span></span> <span data-ttu-id="ac9c6-214">Nya API-fält innehåller LinkToMTP och IncidentLinkToMTP.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-214">New API fields include LinkToMTP and IncidentLinkToMTP.</span></span> <span data-ttu-id="ac9c6-215">Mer information finns i Omdirigera [konton från Microsoft Defender för Slutpunkt till Säkerhetscenter för Microsoft 365.](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)</span><span class="sxs-lookup"><span data-stu-id="ac9c6-215">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md).</span></span>

### <a name="email-alerts"></a><span data-ttu-id="ac9c6-216">E-postaviseringar</span><span class="sxs-lookup"><span data-stu-id="ac9c6-216">Email alerts</span></span>

<span data-ttu-id="ac9c6-217">Du kan fortsätta att använda e-postaviseringar för Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-217">You can continue to use email alerts for Defender for Endpoint.</span></span> <span data-ttu-id="ac9c6-218">Vi har lagt till nya länkar i e-postmeddelanden som pekar på aviseringssidan eller incidentsidan i Säkerhetscenter i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ac9c6-218">We've added new links in the emails that point to the alert page or the incident page in the Microsoft 365 security center.</span></span> <span data-ttu-id="ac9c6-219">Mer information finns i Omdirigera [konton från Microsoft Defender för Slutpunkt till Säkerhetscenter för Microsoft 365.](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md)</span><span class="sxs-lookup"><span data-stu-id="ac9c6-219">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](/microsoft-365/security/mtp/microsoft-365-security-mde-redirection.md).</span></span>

## <a name="related-information"></a><span data-ttu-id="ac9c6-220">Relaterad information</span><span class="sxs-lookup"><span data-stu-id="ac9c6-220">Related information</span></span>

- [<span data-ttu-id="ac9c6-221">Microsoft 365 Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="ac9c6-221">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="ac9c6-222">Microsoft Defender för slutpunkt i Säkerhetscenter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac9c6-222">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="ac9c6-223">Omdirigera konton från Microsoft Defender för Slutpunkt till Säkerhetscenter för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ac9c6-223">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)