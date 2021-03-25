---
title: Skapa anpassade identifieringsregler i Microsoft Defender ATP
ms.reviewer: ''
description: Lär dig hur du skapar anpassade identifieringsregler som baseras på avancerade sökfrågor
keywords: anpassade identifieringar, skapa, hantera, aviseringar, redigera, köra på begäran, frekvens, intervall, identifieringsregler, avancerad sökning, sökning, fråga, svarsåtgärder, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: fc4c15d2e391176ed0b4420c13fb865674da0361
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163593"
---
# <a name="create-custom-detection-rules"></a><span data-ttu-id="1a365-104">Skapa anpassade identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="1a365-104">Create custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1a365-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1a365-105">**Applies to:**</span></span>
- [<span data-ttu-id="1a365-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1a365-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1a365-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1a365-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="1a365-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1a365-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1a365-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="1a365-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="1a365-110">Anpassade identifieringsregler skapade av [avancerade](advanced-hunting-overview.md) sökfrågor gör att du proaktivt kan övervaka olika händelser och systemhändelser, inklusive misstänkt intrång och felkonfigurerade enheter.</span><span class="sxs-lookup"><span data-stu-id="1a365-110">Custom detection rules built from [advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="1a365-111">Du kan ange att de ska köras med jämna mellanrum, generera aviseringar och vidta svarsåtgärder när det finns matchningar.</span><span class="sxs-lookup"><span data-stu-id="1a365-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="1a365-112">I den här artikeln får du lära dig hur du skapar nya anpassade identifieringsregler.</span><span class="sxs-lookup"><span data-stu-id="1a365-112">Read this article to learn how to create new custom detection rules.</span></span> <span data-ttu-id="1a365-113">Du [kan också visa och hantera befintliga regler.](custom-detections-manage.md)</span><span class="sxs-lookup"><span data-stu-id="1a365-113">Or [see viewing and managing existing rules](custom-detections-manage.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1a365-114">För att skapa eller hantera anpassade identifieringar [måste din roll](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) ha behörighet att hantera **säkerhetsinställningar.**</span><span class="sxs-lookup"><span data-stu-id="1a365-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="1-prepare-the-query"></a><span data-ttu-id="1a365-115">1. Förbereda frågan.</span><span class="sxs-lookup"><span data-stu-id="1a365-115">1. Prepare the query.</span></span>

<span data-ttu-id="1a365-116">I Microsoft Defender Säkerhetscenter går du till **Avancerad sökning** och väljer en befintlig fråga eller skapar en ny fråga.</span><span class="sxs-lookup"><span data-stu-id="1a365-116">In Microsoft Defender Security Center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="1a365-117">När du använder en ny fråga kör du frågan för att identifiera fel och förstå möjliga resultat.</span><span class="sxs-lookup"><span data-stu-id="1a365-117">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="1a365-118">För att förhindra att tjänsten returnerar för många aviseringar är varje regel begränsad till att generera endast 100 aviseringar när den körs.</span><span class="sxs-lookup"><span data-stu-id="1a365-118">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="1a365-119">Innan du skapar en regel bör du justera frågan för att undvika aviseringar om normal aktivitet.</span><span class="sxs-lookup"><span data-stu-id="1a365-119">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>

### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="1a365-120">Obligatoriska kolumner i frågeresultatet</span><span class="sxs-lookup"><span data-stu-id="1a365-120">Required columns in the query results</span></span>

<span data-ttu-id="1a365-121">Om du vill använda en fråga för en anpassad identifieringsregel måste frågan returnera följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="1a365-121">To use a query for a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- `DeviceId`
- `ReportId`

<span data-ttu-id="1a365-122">Enkla frågor, till exempel de som inte använder operatorn eller för att anpassa eller sammanställa resultat, returnerar `project` `summarize` vanligtvis dessa gemensamma kolumner.</span><span class="sxs-lookup"><span data-stu-id="1a365-122">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="1a365-123">Det finns olika sätt att säkerställa att mer komplexa frågor returnerar dessa kolumner.</span><span class="sxs-lookup"><span data-stu-id="1a365-123">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="1a365-124">Om du till exempel föredrar att aggregera och räkna efter kan du fortfarande returnera och genom att hämta dem från den senaste händelsen `DeviceId` `Timestamp` som innefattar varje `ReportId` enhet.</span><span class="sxs-lookup"><span data-stu-id="1a365-124">For example, if you prefer to aggregate and count by `DeviceId`, you can still return `Timestamp` and `ReportId` by getting them from the most recent event involving each device.</span></span>

<span data-ttu-id="1a365-125">I exempelfrågan nedan räknas antalet unika enheter () med antivirusidentifiering och används för att endast hitta de enheter som har `DeviceId` fler än fem identifieringar.</span><span class="sxs-lookup"><span data-stu-id="1a365-125">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this to find only those devices with more than five detections.</span></span> <span data-ttu-id="1a365-126">För att returnera det `Timestamp` senaste och motsvarande används `ReportId` `summarize` operatorn med `arg_max` funktionen.</span><span class="sxs-lookup"><span data-stu-id="1a365-126">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="1a365-127">För att få bättre frågeprestanda kan du ange ett tidsfilter som matchar den avsedda körningsfrekvensen för regeln.</span><span class="sxs-lookup"><span data-stu-id="1a365-127">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="1a365-128">Eftersom det minsta antalet körningar är en gång per dygn omfattar filtreringen för den senaste dagen alla nya data.</span><span class="sxs-lookup"><span data-stu-id="1a365-128">Since the least frequent run is every 24 hours, filtering for the past day will cover all new data.</span></span>

## <a name="2-create-a-new-rule-and-provide-alert-details"></a><span data-ttu-id="1a365-129">2. Skapa en ny regel och ange aviseringsinformation.</span><span class="sxs-lookup"><span data-stu-id="1a365-129">2. Create a new rule and provide alert details.</span></span>

<span data-ttu-id="1a365-130">Med frågan i frågeredigeraren väljer du **Skapa identifieringsregel** och anger följande aviseringsinformation:</span><span class="sxs-lookup"><span data-stu-id="1a365-130">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="1a365-131">**Identifieringsnamn**– namnet på identifieringsregeln</span><span class="sxs-lookup"><span data-stu-id="1a365-131">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="1a365-132">**Frekvens**– intervall för att köra frågan och vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="1a365-132">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="1a365-133">Mer information finns nedan</span><span class="sxs-lookup"><span data-stu-id="1a365-133">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="1a365-134">**Aviseringsrubrik**– rubrik som visas med aviseringar som utlöses av regeln</span><span class="sxs-lookup"><span data-stu-id="1a365-134">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="1a365-135">**Allvarlighetsgrad**– potentiell risk för den komponent eller aktivitet som identifieras av regeln.</span><span class="sxs-lookup"><span data-stu-id="1a365-135">**Severity**—potential risk of the component or activity identified by the rule.</span></span> [<span data-ttu-id="1a365-136">Läs mer om allvarlighetsgraderna för aviseringar</span><span class="sxs-lookup"><span data-stu-id="1a365-136">Read about alert severities</span></span>](alerts-queue.md#severity)
- <span data-ttu-id="1a365-137">**Kategori**– typ av hotkomponent eller aktivitet, om det finns någon.</span><span class="sxs-lookup"><span data-stu-id="1a365-137">**Category**—type of threat component or activity, if any.</span></span> [<span data-ttu-id="1a365-138">Läs mer om aviseringskategorier</span><span class="sxs-lookup"><span data-stu-id="1a365-138">Read about alert categories</span></span>](alerts-queue.md#understanding-alert-categories)
- <span data-ttu-id="1a365-139">**MITRE ATT&CK-tekniker**– en eller flera attacktekniker som identifieras av regeln enligt finns i MITRE ATT&CK-ramverket.</span><span class="sxs-lookup"><span data-stu-id="1a365-139">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the MITRE ATT&CK framework.</span></span> <span data-ttu-id="1a365-140">Det här avsnittet är inte tillgängligt för vissa aviseringskategorier, till exempel skadlig kod, utpressningstrojaner, misstänkt aktivitet och oönskad programvara</span><span class="sxs-lookup"><span data-stu-id="1a365-140">This section is not available with certain alert categories, such as malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="1a365-141">**Beskrivning**– mer information om komponenten eller aktiviteten som identifieras av regeln</span><span class="sxs-lookup"><span data-stu-id="1a365-141">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="1a365-142">**Rekommenderade åtgärder**– ytterligare åtgärder som svarare kan vidta för en avisering</span><span class="sxs-lookup"><span data-stu-id="1a365-142">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

<span data-ttu-id="1a365-143">Mer information om hur aviseringsinformation visas finns [i om aviseringskön](alerts-queue.md).</span><span class="sxs-lookup"><span data-stu-id="1a365-143">For more information about how alert details are displayed, [read about the alert queue](alerts-queue.md).</span></span>

### <a name="rule-frequency"></a><span data-ttu-id="1a365-144">Regelfrekvens</span><span class="sxs-lookup"><span data-stu-id="1a365-144">Rule frequency</span></span>

<span data-ttu-id="1a365-145">När den sparas körs en ny anpassad identifieringsregel direkt och söker efter matchningar från de senaste 30 dagarnas data.</span><span class="sxs-lookup"><span data-stu-id="1a365-145">When saved, a new custom detection rule immediately runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="1a365-146">Regeln körs sedan igen med fasta intervall och söklängder baserat på den frekvens du väljer:</span><span class="sxs-lookup"><span data-stu-id="1a365-146">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="1a365-147">**Körs en gång per dygn** och kontrollerar data från de senaste 30 dagarna</span><span class="sxs-lookup"><span data-stu-id="1a365-147">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="1a365-148">**Körs var 12:e** timme per dygn och kontrollerar data från de senaste 24 timmarna</span><span class="sxs-lookup"><span data-stu-id="1a365-148">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="1a365-149">**Körs var tredje timme** och kontrollerar data från de senaste 6 timmarna</span><span class="sxs-lookup"><span data-stu-id="1a365-149">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="1a365-150">**Varje timme** körs varje timme och du kontrollerar data från de senaste två timmarna</span><span class="sxs-lookup"><span data-stu-id="1a365-150">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a365-151">När du ändrar en fråga som redan schemalagts som en anpassad identifiering kommer nästa omedelbart körning att ha ett uppslagsfönster på 30 dagar, exakt som om en ny fråga skapades.</span><span class="sxs-lookup"><span data-stu-id="1a365-151">When changing a query that is already scheduled as a Custom Detection, it's next immediate execution will have a lookback window of 30 days, exactly as if a new query was being created.</span></span> <span data-ttu-id="1a365-152">Ändringar av ett stort antal frågor, och med tidsfilter som är högre än standardvaraktigheten för den valda frekvensen, kan påverka den totala kvoten för Avancerad sökning och resultera i att den dagliga kvoten förbrukas.</span><span class="sxs-lookup"><span data-stu-id="1a365-152">Changes to a large number of queries, and with time filters higher than the default lookback duration for the selected frequency, might have an impact in the overall quota consumption of Advanced Hunting and resulting in exhausting the daily quota.</span></span>

> [!TIP]
> <span data-ttu-id="1a365-153">Matcha tidsfiltren i frågan med tillbakaslagslängden.</span><span class="sxs-lookup"><span data-stu-id="1a365-153">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="1a365-154">Resultat utanför återställningsvaraktigheten ignoreras.</span><span class="sxs-lookup"><span data-stu-id="1a365-154">Results outside of the lookback duration are ignored.</span></span>

<span data-ttu-id="1a365-155">Välj den frekvens som matchar hur nära du vill övervaka identifieringar och ta hänsyn till organisationens kapacitet att svara på aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="1a365-155">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

## <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="1a365-156">3. Välj de berörda enheterna.</span><span class="sxs-lookup"><span data-stu-id="1a365-156">3. Choose the impacted entities.</span></span>

<span data-ttu-id="1a365-157">Identifiera kolumnerna i frågeresultatet där du förväntar dig att hitta den viktigaste påverkade eller påverkade enheten.</span><span class="sxs-lookup"><span data-stu-id="1a365-157">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="1a365-158">En fråga kan till exempel returnera både enhets- och användar-ID.</span><span class="sxs-lookup"><span data-stu-id="1a365-158">For example, a query might return both device and user IDs.</span></span> <span data-ttu-id="1a365-159">Genom att identifiera vilka av dessa kolumner som representerar den viktigaste påverkade enheten bidrar tjänsten till att slå samman relevanta aviseringar, korrelera incidenter och målsvarsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="1a365-159">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="1a365-160">Du kan bara välja en kolumn för varje entitetstyp.</span><span class="sxs-lookup"><span data-stu-id="1a365-160">You can select only one column for each entity type.</span></span> <span data-ttu-id="1a365-161">Kolumner som inte returneras av frågan kan inte markeras.</span><span class="sxs-lookup"><span data-stu-id="1a365-161">Columns that are not returned by your query can't be selected.</span></span>

## <a name="4-specify-actions"></a><span data-ttu-id="1a365-162">4. Ange åtgärder.</span><span class="sxs-lookup"><span data-stu-id="1a365-162">4. Specify actions.</span></span>

<span data-ttu-id="1a365-163">Den anpassade identifieringsregeln kan automatiskt utföra åtgärder på filer eller enheter som returneras av frågan.</span><span class="sxs-lookup"><span data-stu-id="1a365-163">Your custom detection rule can automatically take actions on files or devices that are returned by the query.</span></span>

### <a name="actions-on-devices"></a><span data-ttu-id="1a365-164">Åtgärder på enheter</span><span class="sxs-lookup"><span data-stu-id="1a365-164">Actions on devices</span></span>

<span data-ttu-id="1a365-165">Dessa åtgärder tillämpas på enheter i `DeviceId` kolumnen med frågeresultat:</span><span class="sxs-lookup"><span data-stu-id="1a365-165">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>

- <span data-ttu-id="1a365-166">**Isolera enhet**– tillämpar fullständig nätverksisolering, vilket hindrar enheten från att ansluta till något program eller en tjänst, förutom Defender för Slutpunkt-tjänsten.</span><span class="sxs-lookup"><span data-stu-id="1a365-166">**Isolate device**—applies full network isolation, preventing the device from connecting to any application or service, except for the Defender for Endpoint service.</span></span> [<span data-ttu-id="1a365-167">Läs mer om enhetsisolering</span><span class="sxs-lookup"><span data-stu-id="1a365-167">Learn more about device isolation</span></span>](respond-machine-alerts.md#isolate-devices-from-the-network)
- <span data-ttu-id="1a365-168">Samla in **undersökningspaket**– samlar in enhetsinformation i en ZIP-fil.</span><span class="sxs-lookup"><span data-stu-id="1a365-168">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="1a365-169">Läs mer om undersökningspaketet</span><span class="sxs-lookup"><span data-stu-id="1a365-169">Learn more about the investigation package</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- <span data-ttu-id="1a365-170">**Kör en antivirussökning**– utför en fullständig sökning i Microsoft Defender Antivirus på enheten</span><span class="sxs-lookup"><span data-stu-id="1a365-170">**Run antivirus scan**—performs a full Microsoft Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="1a365-171">**Initiera undersökning**– startar [en automatiserad undersökning](automated-investigations.md) på enheten</span><span class="sxs-lookup"><span data-stu-id="1a365-171">**Initiate investigation**—starts an [automated investigation](automated-investigations.md) on the device</span></span>
- <span data-ttu-id="1a365-172">**Begränsa programkörning**– anger begränsningar på enheten så att endast filer som är signerade med ett certifikat utfärdat av Microsoft kan köras.</span><span class="sxs-lookup"><span data-stu-id="1a365-172">**Restrict app execution**—sets restrictions on the device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="1a365-173">Läs mer om att begränsa programkörning</span><span class="sxs-lookup"><span data-stu-id="1a365-173">Learn more about restricting app execution</span></span>](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a><span data-ttu-id="1a365-174">Åtgärder för filer</span><span class="sxs-lookup"><span data-stu-id="1a365-174">Actions on files</span></span>

<span data-ttu-id="1a365-175">Dessa åtgärder tillämpas på filer i `SHA1` eller `InitiatingProcessSHA1` kolumnen i frågeresultatet:</span><span class="sxs-lookup"><span data-stu-id="1a365-175">These actions are applied to files in the `SHA1` or the `InitiatingProcessSHA1` column of the query results:</span></span>

- <span data-ttu-id="1a365-176">**Tillåt/blockera**– lägger automatiskt till filen i din [anpassade indikatorlista](manage-indicators.md) så att den alltid kan köras eller blockeras.</span><span class="sxs-lookup"><span data-stu-id="1a365-176">**Allow/Block**—automatically adds the file to your [custom indicator list](manage-indicators.md) so that it is always allowed to run or blocked from running.</span></span> <span data-ttu-id="1a365-177">Du kan ange omfattningen av den här åtgärden så att den endast vidtas på valda enhetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="1a365-177">You can set the scope of this action so that it is taken only on selected device groups.</span></span> <span data-ttu-id="1a365-178">Den här omfattningen är oberoende av regelns omfattning.</span><span class="sxs-lookup"><span data-stu-id="1a365-178">This scope is independent of the scope of the rule.</span></span>
- <span data-ttu-id="1a365-179">**Karantänfil**– tar bort filen från dess aktuella plats och placerar en kopia i karantän</span><span class="sxs-lookup"><span data-stu-id="1a365-179">**Quarantine file**—deletes the file from its current location and places a copy in quarantine</span></span>

### <a name="actions-on-users"></a><span data-ttu-id="1a365-180">Åtgärder för användare</span><span class="sxs-lookup"><span data-stu-id="1a365-180">Actions on users</span></span>

- <span data-ttu-id="1a365-181">**Markera användare som komprometterade**– anger att användarens risknivå är "hög" i Azure Active Directory, vilket utlöser motsvarande [principer för identitetsskydd.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)</span><span class="sxs-lookup"><span data-stu-id="1a365-181">**Mark user as compromised**—sets the user's risk level to "high" in Azure Active Directory, triggering the corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels).</span></span>

## <a name="5-set-the-rule-scope"></a><span data-ttu-id="1a365-182">5. Ange regelns omfattning.</span><span class="sxs-lookup"><span data-stu-id="1a365-182">5. Set the rule scope.</span></span>

<span data-ttu-id="1a365-183">Ange omfattningen för att ange vilka enheter som omfattas av regeln:</span><span class="sxs-lookup"><span data-stu-id="1a365-183">Set the scope to specify which devices are covered by the rule:</span></span>

- <span data-ttu-id="1a365-184">Alla enheter</span><span class="sxs-lookup"><span data-stu-id="1a365-184">All devices</span></span>
- <span data-ttu-id="1a365-185">Specifika enhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="1a365-185">Specific device groups</span></span>

<span data-ttu-id="1a365-186">Endast data från enheter i omfattningen kommer att tillfrågas.</span><span class="sxs-lookup"><span data-stu-id="1a365-186">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="1a365-187">Dessutom kommer åtgärder endast att vidtas på de enheterna.</span><span class="sxs-lookup"><span data-stu-id="1a365-187">Also, actions will be taken only on those devices.</span></span>

## <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="1a365-188">6. Granska och aktivera regeln.</span><span class="sxs-lookup"><span data-stu-id="1a365-188">6. Review and turn on the rule.</span></span>

<span data-ttu-id="1a365-189">När du har granskat regeln väljer du **Skapa för** att spara den.</span><span class="sxs-lookup"><span data-stu-id="1a365-189">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="1a365-190">Regeln för anpassad identifiering körs direkt.</span><span class="sxs-lookup"><span data-stu-id="1a365-190">The custom detection rule immediately runs.</span></span> <span data-ttu-id="1a365-191">Den körs igen baserat på konfigurerad frekvens för att söka efter matchningar, generera aviseringar och vidta svarsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="1a365-191">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

<span data-ttu-id="1a365-192">Du kan [visa och hantera anpassade identifieringsregler](custom-detections-manage.md), kontrollera deras tidigare körningar och granska aviseringarna som de har utlöst.</span><span class="sxs-lookup"><span data-stu-id="1a365-192">You can [view and manage custom detection rules](custom-detections-manage.md), check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="1a365-193">Du kan även köra en regel på begäran och ändra den.</span><span class="sxs-lookup"><span data-stu-id="1a365-193">You can also run a rule on demand and modify it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1a365-194">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1a365-194">Related topics</span></span>

- [<span data-ttu-id="1a365-195">Visa och hantera anpassade identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="1a365-195">View and manage custom detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="1a365-196">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="1a365-196">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="1a365-197">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="1a365-197">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1a365-198">Lär dig språket för avancerad fråga om sökning</span><span class="sxs-lookup"><span data-stu-id="1a365-198">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1a365-199">Visa och ordna aviseringar</span><span class="sxs-lookup"><span data-stu-id="1a365-199">View and organize alerts</span></span>](alerts-queue.md)
