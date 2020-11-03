---
title: Skapa och hantera anpassade identifierings regler i Microsoft 365 Defender
description: Lär dig hur du skapar och hanterar anpassade identifierings regler baserat på avancerade jakt frågor
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, anpassade identifieringar, regler, schema, kusto, Microsoft 365, Microsoft Threat Protection, RBAC, behörigheter, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 5de4532a1bba809cde16ba6033ab30773a832176
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846778"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="ef65f-104">Skapa och hantera regler för anpassat identifiering</span><span class="sxs-lookup"><span data-stu-id="ef65f-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ef65f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="ef65f-105">**Applies to:**</span></span>
- <span data-ttu-id="ef65f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef65f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ef65f-107">Anpassade identifierings regler är regler som du kan utforma och anpassa med hjälp av [avancerade](advanced-hunting-overview.md) frågor.</span><span class="sxs-lookup"><span data-stu-id="ef65f-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="ef65f-108">Med dessa regler kan du proaktivt övervaka olika händelser och system tillstånd, inklusive misstänkt överträdelse och felkonfigurerade slut punkter.</span><span class="sxs-lookup"><span data-stu-id="ef65f-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="ef65f-109">Du kan ange att de ska köras med jämna mellanrum, skapa aviseringar och vidta åtgärder när det finns träffar.</span><span class="sxs-lookup"><span data-stu-id="ef65f-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="ef65f-110">Nödvändiga behörigheter för att hantera anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="ef65f-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="ef65f-111">För att hantera anpassade identifieringar måste du tilldela en av följande roller:</span><span class="sxs-lookup"><span data-stu-id="ef65f-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="ef65f-112">**Säkerhets administratören** – användare med den här [Azure Active Directory-rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) kan hantera säkerhets inställningar i Microsoft 365 säkerhets Center och andra portaler och tjänster.</span><span class="sxs-lookup"><span data-stu-id="ef65f-112">**Security administrator** —Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="ef65f-113">**Säkerhets ansvarig** – användare med den här [Azure Active Directory-rollen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) kan hantera aviseringar och ha global åtkomst till säkerhetsrelaterade funktioner, inklusive all information i Microsoft 365 säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="ef65f-113">**Security operator** —Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="ef65f-114">Den här rollen räcker bara till för att hantera anpassade identifieringar om RBAC (rollbaserad åtkomst kontroll) är inaktiverat i Microsoft Defender för slut punkten.</span><span class="sxs-lookup"><span data-stu-id="ef65f-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="ef65f-115">Om du har en RBAC-konfiguration behöver du även behörigheten **hantera säkerhets inställningar** för Defender för slut punkt.</span><span class="sxs-lookup"><span data-stu-id="ef65f-115">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="ef65f-116">För att hantera nödvändiga behörigheter kan en **Global administratör** :</span><span class="sxs-lookup"><span data-stu-id="ef65f-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="ef65f-117">Koppla rollen som **säkerhets administratör** eller **säkerhets ansvarig** i [administrations centret för Microsoft 365](https://admin.microsoft.com/) under **roll**  >  **säkerhets administratör**.</span><span class="sxs-lookup"><span data-stu-id="ef65f-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="ef65f-118">Kontrol lera inställningar för RBAC för Microsoft Defender för slut punkten i [Microsoft Defender säkerhets Center](https://securitycenter.windows.com/) under **Inställningar** för  >  **behörighets**  >  **roller**.</span><span class="sxs-lookup"><span data-stu-id="ef65f-118">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="ef65f-119">Välj motsvarande roll för att tilldela behörigheten **hantera säkerhets inställningar** .</span><span class="sxs-lookup"><span data-stu-id="ef65f-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="ef65f-120">För att hantera anpassade identifieringar måste **säkerhets operatörerna** **hantera säkerhets inställningar** i Microsoft Defender för slut punkt om RBAC är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="ef65f-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="ef65f-121">Skapa en anpassad detektions regel</span><span class="sxs-lookup"><span data-stu-id="ef65f-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="ef65f-122">1. förbereda frågan.</span><span class="sxs-lookup"><span data-stu-id="ef65f-122">1. Prepare the query.</span></span>

<span data-ttu-id="ef65f-123">I Microsoft 365 säkerhets Center går du till **Avancerad jakt** och väljer en befintlig fråga eller skapar en ny fråga.</span><span class="sxs-lookup"><span data-stu-id="ef65f-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="ef65f-124">Kör frågan för att identifiera fel och förstå möjliga resultat när du använder en ny fråga.</span><span class="sxs-lookup"><span data-stu-id="ef65f-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="ef65f-125">För att förhindra att tjänsten returnerar för många aviseringar begränsas varje regel för att bara generera 100-varningar när den körs.</span><span class="sxs-lookup"><span data-stu-id="ef65f-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="ef65f-126">Innan du skapar en regel kan du ställa in din fråga för att undvika att aviseringar visas för normal, daglig aktivitet.</span><span class="sxs-lookup"><span data-stu-id="ef65f-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="ef65f-127">Kolumner som krävs i frågeresultatet</span><span class="sxs-lookup"><span data-stu-id="ef65f-127">Required columns in the query results</span></span>
<span data-ttu-id="ef65f-128">Om du vill skapa en anpassad detektions regel måste frågan returnera följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="ef65f-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="ef65f-129">`Timestamp`— används för att ställa in tidsstämpeln för genererade aviseringar</span><span class="sxs-lookup"><span data-stu-id="ef65f-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="ef65f-130">`ReportId`– aktiverar uppslag för de ursprungliga posterna</span><span class="sxs-lookup"><span data-stu-id="ef65f-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="ef65f-131">En av följande kolumner som identifierar specifika enheter, användare eller post lådor:</span><span class="sxs-lookup"><span data-stu-id="ef65f-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="ef65f-132">`SenderFromAddress` (kuvert avsändare eller Return-Path adress)</span><span class="sxs-lookup"><span data-stu-id="ef65f-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="ef65f-133">`SenderMailFromAddress` (avsändar adress som visas i e-postklienten)</span><span class="sxs-lookup"><span data-stu-id="ef65f-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="ef65f-134">Stöd för ytterligare enheter läggs till när nya tabeller läggs till i det [avancerade jakt schemat](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ef65f-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="ef65f-135">Enkla frågor, till exempel dem som inte använder `project` `summarize` operatorn eller för att anpassa resultat, returnerar normalt dessa vanliga kolumner.</span><span class="sxs-lookup"><span data-stu-id="ef65f-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="ef65f-136">Det finns olika sätt att se till att komplexa frågor returnerar de här kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="ef65f-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="ef65f-137">Om du till exempel föredrar att aggregera och inventera efter entitet under en kolumn, `DeviceId` kan du ändå återgå till `Timestamp` och `ReportId` genom att hämta den från den senaste händelsen som rör varje unikt `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="ef65f-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="ef65f-138">I exempel frågan nedan räknas antalet unika enheter ( `DeviceId` ) med Antivirus identifieringar och använder det här antalet för att endast hitta enheter med fler än fem identifieringar.</span><span class="sxs-lookup"><span data-stu-id="ef65f-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="ef65f-139">Om du vill returnera det senaste `Timestamp` och det motsvarande `ReportId` används `summarize` operatorn med `arg_max` funktionen.</span><span class="sxs-lookup"><span data-stu-id="ef65f-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="ef65f-140">För bättre prestanda för frågor kan du ange ett tids filter som matchar den avsedda användnings frekvensen för regeln.</span><span class="sxs-lookup"><span data-stu-id="ef65f-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="ef65f-141">Eftersom den minst oftare är i _24 timmar_ täcker filtreringen för den förflutna dagen alla nya data.</span><span class="sxs-lookup"><span data-stu-id="ef65f-141">Since the least frequent run is _every 24 hours_ , filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="ef65f-142">2. skapa en ny regel och ange aviserings information.</span><span class="sxs-lookup"><span data-stu-id="ef65f-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="ef65f-143">Med frågan i Frågeredigeraren väljer du **skapa detektions regel** och anger följande aviserings information:</span><span class="sxs-lookup"><span data-stu-id="ef65f-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="ef65f-144">**Identifierings namn** – namnet på identifierings regeln</span><span class="sxs-lookup"><span data-stu-id="ef65f-144">**Detection name** —name of the detection rule</span></span>
- <span data-ttu-id="ef65f-145">**Frekvens** – ett tidsintervall som används för att köra frågan och vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="ef65f-145">**Frequency** —interval for running the query and taking action.</span></span> [<span data-ttu-id="ef65f-146">Se ytterligare vägledning nedan</span><span class="sxs-lookup"><span data-stu-id="ef65f-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="ef65f-147">**Aviserings rubrik** – titeln visas med notifieringar utlöst av regeln</span><span class="sxs-lookup"><span data-stu-id="ef65f-147">**Alert title** —title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="ef65f-148">**Allvarlighets grad** — den komponent eller aktivitet som identifieras av regeln</span><span class="sxs-lookup"><span data-stu-id="ef65f-148">**Severity** —potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="ef65f-149">**Kategori** – hot komponent eller aktivitet som identifieras av regeln</span><span class="sxs-lookup"><span data-stu-id="ef65f-149">**Category** —threat component or activity identified by the rule</span></span>
- <span data-ttu-id="ef65f-150">**Mitre to&CK-teknik** – en eller flera angrepp som identifieras av regeln enligt anvisningarna i [&MITREs ramverk](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="ef65f-150">**MITRE ATT&CK techniques** —one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="ef65f-151">Det här avsnittet är dolt för vissa aviserings kategorier, inklusive skadlig program vara</span><span class="sxs-lookup"><span data-stu-id="ef65f-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="ef65f-152">**Beskrivning** – mer information om komponenten eller aktiviteten som identifieras av regeln</span><span class="sxs-lookup"><span data-stu-id="ef65f-152">**Description** —more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="ef65f-153">**Rekommenderade åtgärder** – ytterligare åtgärder som svars handlingar kan ta emot när det gäller en avisering</span><span class="sxs-lookup"><span data-stu-id="ef65f-153">**Recommended actions** —additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="ef65f-154">Regel frekvens</span><span class="sxs-lookup"><span data-stu-id="ef65f-154">Rule frequency</span></span>
<span data-ttu-id="ef65f-155">När du sparar eller redigerar en ny regel körs den och söker efter matchningar från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="ef65f-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="ef65f-156">Regeln körs sedan igen med fasta tidsintervall, med en lookback längd utifrån den frekvens du väljer:</span><span class="sxs-lookup"><span data-stu-id="ef65f-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="ef65f-157">Med ett **dygn** – löper ett dygn runt data från de senaste 30 dagarna</span><span class="sxs-lookup"><span data-stu-id="ef65f-157">**Every 24 hours** —runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="ef65f-158">**Var 12: e** timme – kör var tolfte timme och kontrol lera data från de senaste 24 timmarna</span><span class="sxs-lookup"><span data-stu-id="ef65f-158">**Every 12 hours** —runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="ef65f-159">**Var tredje timme** – kör var tredje timme, kontrol lera data från de senaste 6 timmarna</span><span class="sxs-lookup"><span data-stu-id="ef65f-159">**Every 3 hours** —runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="ef65f-160">**Varje timme** – kör per timme för att kontrol lera data från de senaste 2 timmarna</span><span class="sxs-lookup"><span data-stu-id="ef65f-160">**Every hour** —runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="ef65f-161">Matcha tids filtren i frågan med lookback längd.</span><span class="sxs-lookup"><span data-stu-id="ef65f-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="ef65f-162">Resultat utanför lookback varaktighet ignoreras.</span><span class="sxs-lookup"><span data-stu-id="ef65f-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="ef65f-163">Välj den frekvens som motsvarar hur nära du vill övervaka identifieringarna.</span><span class="sxs-lookup"><span data-stu-id="ef65f-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="ef65f-164">Överväg organisationens kapacitet för att svara på aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="ef65f-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="ef65f-165">3. Välj de enheter som påverkas.</span><span class="sxs-lookup"><span data-stu-id="ef65f-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="ef65f-166">Identifiera kolumnerna i frågeresultatet där du förväntar dig att hitta den huvud enhet som påverkas eller påverkas.</span><span class="sxs-lookup"><span data-stu-id="ef65f-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="ef65f-167">En fråga kan till exempel returnera avsändare ( `SenderFromAddress` eller `SenderMailFromAddress` )-och mottagar `RecipientEmailAddress` adresser.</span><span class="sxs-lookup"><span data-stu-id="ef65f-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="ef65f-168">Att identifiera vilka av de här kolumnerna som representerar huvud enheten som påverkas hjälper tjänsten att aggregera relevanta aviseringar, korrelera problem och åtgärder för mål svar.</span><span class="sxs-lookup"><span data-stu-id="ef65f-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="ef65f-169">Du kan bara välja en kolumn för varje entitetstyp (post låda, användare eller enhet).</span><span class="sxs-lookup"><span data-stu-id="ef65f-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="ef65f-170">Kolumner som inte returneras av frågan kan inte markeras.</span><span class="sxs-lookup"><span data-stu-id="ef65f-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="ef65f-171">4. ange åtgärder.</span><span class="sxs-lookup"><span data-stu-id="ef65f-171">4. Specify actions.</span></span>
<span data-ttu-id="ef65f-172">Din regel för anpassad avkänning kan automatiskt utföra åtgärder på enheter, filer eller användare som returneras av frågan.</span><span class="sxs-lookup"><span data-stu-id="ef65f-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="ef65f-173">Åtgärder på enheter</span><span class="sxs-lookup"><span data-stu-id="ef65f-173">Actions on devices</span></span>
<span data-ttu-id="ef65f-174">De här åtgärderna tillämpas på enheter i `DeviceId` kolumnen i frågeresultatet:</span><span class="sxs-lookup"><span data-stu-id="ef65f-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="ef65f-175">**Isolera enhet** — använder Microsoft Defender för slut punkt för att tillämpa fullständig nätverks isolering och förhindra att enheten ansluter till något program eller en tjänst.</span><span class="sxs-lookup"><span data-stu-id="ef65f-175">**Isolate device** —uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="ef65f-176">Läs mer om Microsoft Defender för slut punkts dator isolering</span><span class="sxs-lookup"><span data-stu-id="ef65f-176">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="ef65f-177">**Samla in undersöknings paket** – samlar in enhets information i en zip-fil.</span><span class="sxs-lookup"><span data-stu-id="ef65f-177">**Collect investigation package** —collects device information in a ZIP file.</span></span> [<span data-ttu-id="ef65f-178">Läs mer om Microsoft Defender för slut punkts gransknings paketet</span><span class="sxs-lookup"><span data-stu-id="ef65f-178">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="ef65f-179">**Kör antivirus-genomsökning** – utför en fullständig Windows Defender Antivirus-genomsökning på enheten</span><span class="sxs-lookup"><span data-stu-id="ef65f-179">**Run antivirus scan** —performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="ef65f-180">**Inleda undersökning** – initierar en [Automatisk undersökning](mtp-autoir.md) på enheten</span><span class="sxs-lookup"><span data-stu-id="ef65f-180">**Initiate investigation** —initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="ef65f-181">**Begränsa program körning** – anger begränsningar för enheter för att endast tillåta att filer som är signerade med ett Microsoft-utfärdat certifikat körs.</span><span class="sxs-lookup"><span data-stu-id="ef65f-181">**Restrict app execution** —sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="ef65f-182">Lär dig mer om program begränsningar med Microsoft Defender för slut punkten</span><span class="sxs-lookup"><span data-stu-id="ef65f-182">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="ef65f-183">Åtgärder på filer</span><span class="sxs-lookup"><span data-stu-id="ef65f-183">Actions on files</span></span>
<span data-ttu-id="ef65f-184">När du väljer det här alternativet kan du välja att använda **karantän fil** åtgärden för filer `SHA1` i `InitiatingProcessSHA1` `SHA256` kolumnerna,, eller i `InitiatingProcessSHA256` frågeresultatet.</span><span class="sxs-lookup"><span data-stu-id="ef65f-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="ef65f-185">Den här åtgärden tar bort filen från dess nuvarande plats och placerar en kopia i karantän.</span><span class="sxs-lookup"><span data-stu-id="ef65f-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="ef65f-186">Åtgärder för användare</span><span class="sxs-lookup"><span data-stu-id="ef65f-186">Actions on users</span></span>
<span data-ttu-id="ef65f-187">När **det här** alternativet är markerat vidtas användare i `AccountObjectId` `InitiatingProcessAccountObjectId` kolumnen, eller, eller i `RecipientObjectId` frågeresultatet.</span><span class="sxs-lookup"><span data-stu-id="ef65f-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="ef65f-188">Den här åtgärden anger risk nivån för användare till "hög" i Azure Active Directory och utlöser motsvarande [identitets skydds principer](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="ef65f-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="ef65f-189">Åtgärden för att tillåta eller blockera för anpassade identifierings regler stöds för närvarande inte i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ef65f-189">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="ef65f-190">5. Ange regel omfånget.</span><span class="sxs-lookup"><span data-stu-id="ef65f-190">5. Set the rule scope.</span></span>
<span data-ttu-id="ef65f-191">Ange omfattningen för att ange vilka enheter som omfattas av regeln.</span><span class="sxs-lookup"><span data-stu-id="ef65f-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="ef65f-192">Omfattningen påverkar regler som kontrollerar enheter och påverkar inte regler som bara kontrollerar post lådor och användar konton eller identiteter.</span><span class="sxs-lookup"><span data-stu-id="ef65f-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="ef65f-193">När du ställer in omfattningen kan du välja:</span><span class="sxs-lookup"><span data-stu-id="ef65f-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="ef65f-194">Alla enheter</span><span class="sxs-lookup"><span data-stu-id="ef65f-194">All devices</span></span>
- <span data-ttu-id="ef65f-195">Specifika enhets grupper</span><span class="sxs-lookup"><span data-stu-id="ef65f-195">Specific device groups</span></span>

<span data-ttu-id="ef65f-196">Endast data från enheter i omfattning kommer att frågas.</span><span class="sxs-lookup"><span data-stu-id="ef65f-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="ef65f-197">Åtgärder kommer också att vidtas för dessa enheter.</span><span class="sxs-lookup"><span data-stu-id="ef65f-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="ef65f-198">6. granska och aktivera regeln.</span><span class="sxs-lookup"><span data-stu-id="ef65f-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="ef65f-199">När du har granskat regeln väljer du **skapa** för att spara den.</span><span class="sxs-lookup"><span data-stu-id="ef65f-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="ef65f-200">Den anpassade detektions regeln körs omedelbart.</span><span class="sxs-lookup"><span data-stu-id="ef65f-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="ef65f-201">Det körs igen baserat på konfigurerat frekvens för att kontrol lera träffar, generera aviseringar och vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="ef65f-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="ef65f-202">Hantera befintliga regler för anpassat identifiering</span><span class="sxs-lookup"><span data-stu-id="ef65f-202">Manage existing custom detection rules</span></span>
<span data-ttu-id="ef65f-203">Du kan visa en lista med befintliga regler för anpassad avkänning, kontrol lera deras tidigare körningar och granska de notifieringar de har utlöst.</span><span class="sxs-lookup"><span data-stu-id="ef65f-203">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="ef65f-204">Du kan också köra en regel på begäran och ändra den.</span><span class="sxs-lookup"><span data-stu-id="ef65f-204">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="ef65f-205">Visa befintliga regler</span><span class="sxs-lookup"><span data-stu-id="ef65f-205">View existing rules</span></span>

<span data-ttu-id="ef65f-206">Om du vill visa alla befintliga regler för anpassat identifiering navigerar du till **jakt** i  >  **anpassat** läge.</span><span class="sxs-lookup"><span data-stu-id="ef65f-206">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="ef65f-207">På sidan visas alla regler med följande kör information:</span><span class="sxs-lookup"><span data-stu-id="ef65f-207">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="ef65f-208">**Senaste körning** – när en regel senast kördes för att kontrol lera frågan och generera aviseringar</span><span class="sxs-lookup"><span data-stu-id="ef65f-208">**Last run** —when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="ef65f-209">**Senaste körnings status** – oavsett om en regel kördes</span><span class="sxs-lookup"><span data-stu-id="ef65f-209">**Last run status** —whether a rule ran successfully</span></span>
- <span data-ttu-id="ef65f-210">**Nästa kör** -nästa schemalagda körning</span><span class="sxs-lookup"><span data-stu-id="ef65f-210">**Next run** —the next scheduled run</span></span>
- <span data-ttu-id="ef65f-211">**Status** – om en regel har Aktiver ATS eller inaktiverats</span><span class="sxs-lookup"><span data-stu-id="ef65f-211">**Status** —whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="ef65f-212">Visa regel detaljer, ändra regel och kör regel</span><span class="sxs-lookup"><span data-stu-id="ef65f-212">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="ef65f-213">Om du vill visa omfattande information om en anpassad detektions regel går **du till**  >  **anpassade identifierings** regler och väljer sedan namnet på regeln.</span><span class="sxs-lookup"><span data-stu-id="ef65f-213">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="ef65f-214">Du kan sedan Visa allmän information om regeln, inklusive information om programmets kör status och omfattning.</span><span class="sxs-lookup"><span data-stu-id="ef65f-214">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="ef65f-215">Sidan innehåller också en lista över utlösta varningar och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="ef65f-215">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="ef65f-216">![Sidan information om anpassad identifierings regel](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="ef65f-216">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="ef65f-217">*Information om anpassade identifierings regler*</span><span class="sxs-lookup"><span data-stu-id="ef65f-217">*Custom detection rule details*</span></span>

<span data-ttu-id="ef65f-218">Du kan också vidta följande åtgärder på regeln från den här sidan:</span><span class="sxs-lookup"><span data-stu-id="ef65f-218">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="ef65f-219">**Kör** – kör regeln omedelbart.</span><span class="sxs-lookup"><span data-stu-id="ef65f-219">**Run** —run the rule immediately.</span></span> <span data-ttu-id="ef65f-220">Detta återställer också intervallet för nästa körning.</span><span class="sxs-lookup"><span data-stu-id="ef65f-220">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="ef65f-221">**Redigera** – ändra regeln utan att ändra frågan</span><span class="sxs-lookup"><span data-stu-id="ef65f-221">**Edit** —modify the rule without changing the query</span></span>
- <span data-ttu-id="ef65f-222">**Ändra fråga** – redigera frågan i avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="ef65f-222">**Modify query** —edit the query in advanced hunting</span></span>
- <span data-ttu-id="ef65f-223">**Aktivera**  /  **Inaktivera** – aktivera regeln eller förhindra att den körs</span><span class="sxs-lookup"><span data-stu-id="ef65f-223">**Turn on** / **Turn off** —enable the rule or stop it from running</span></span>
- <span data-ttu-id="ef65f-224">**Ta bort** – inaktivera regeln och ta bort den</span><span class="sxs-lookup"><span data-stu-id="ef65f-224">**Delete** —turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="ef65f-225">Visa och hantera utlösta aviseringar</span><span class="sxs-lookup"><span data-stu-id="ef65f-225">View and manage triggered alerts</span></span>

<span data-ttu-id="ef65f-226">I fönstret med regel information ( **jakt** efter  >  **anpassade identifieringar**  >  **[regel namn]** ) går du till **utlösnings bara aviseringar** som visar de varningar som genererats av matchningar till regeln.</span><span class="sxs-lookup"><span data-stu-id="ef65f-226">In the rule details screen ( **Hunting** > **Custom detections** > **[Rule name]** ), go to  **Triggered alerts** , which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="ef65f-227">Välj en avisering om du vill visa detaljerad information om den och vidta följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="ef65f-227">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="ef65f-228">Hantera varningen genom att ange dess status och klassificering (sant eller falsk)</span><span class="sxs-lookup"><span data-stu-id="ef65f-228">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="ef65f-229">Länka aviseringen till en olycka</span><span class="sxs-lookup"><span data-stu-id="ef65f-229">Link the alert to an incident</span></span>
- <span data-ttu-id="ef65f-230">Kör frågan som utlöste aviseringen om avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="ef65f-230">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="ef65f-231">Gransknings åtgärder</span><span class="sxs-lookup"><span data-stu-id="ef65f-231">Review actions</span></span>
<span data-ttu-id="ef65f-232">I fönstret med regel detaljer ( **jakt** på  >  **anpassade identifieringar**  >  **[regel namn]** ) går du till **utlösta åtgärder** som visar vilka åtgärder som utförs baserat på matchningar till regeln.</span><span class="sxs-lookup"><span data-stu-id="ef65f-232">In the rule details screen ( **Hunting** > **Custom detections** > **[Rule name]** ), go to **Triggered actions** , which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="ef65f-233">Om du snabbt vill visa information och vidta åtgärder för ett objekt i en tabell använder du kolumn kolumnen [&#10003;] till vänster i tabellen.</span><span class="sxs-lookup"><span data-stu-id="ef65f-233">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topic"></a><span data-ttu-id="ef65f-234">Närliggande ämne</span><span class="sxs-lookup"><span data-stu-id="ef65f-234">Related topic</span></span>
- [<span data-ttu-id="ef65f-235">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="ef65f-235">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="ef65f-236">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="ef65f-236">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ef65f-237">Lär dig mer om det avancerade frågespråket</span><span class="sxs-lookup"><span data-stu-id="ef65f-237">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
