---
title: Skapa och hantera anpassade identifierings regler i Microsoft Threat Protection
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: cea4dbcb42833a14980d092bd0ff168ca97e5934
ms.sourcegitcommit: 9489aaf255f8bf165e6debc574e20548ad82e882
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/11/2020
ms.locfileid: "46632157"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="80388-104">Skapa och hantera regler för anpassat identifiering</span><span class="sxs-lookup"><span data-stu-id="80388-104">Create and manage custom detections rules</span></span>

<span data-ttu-id="80388-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="80388-105">**Applies to:**</span></span>
- <span data-ttu-id="80388-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="80388-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="80388-107">Anpassade identifierings regler som bygger på [avancerade jakt](advanced-hunting-overview.md) frågor gör att du kan övervaka olika händelser och system tillstånd, inklusive misstänkta överträdelser och felkonfigurerade slut punkter.</span><span class="sxs-lookup"><span data-stu-id="80388-107">Custom detection rules built from [Advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="80388-108">Du kan ange att de ska köras med jämna mellanrum, skapa aviseringar och vidta åtgärder när det finns träffar.</span><span class="sxs-lookup"><span data-stu-id="80388-108">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="80388-109">Nödvändiga behörigheter för att hantera anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="80388-109">Required permissions for managing custom detections</span></span>

<span data-ttu-id="80388-110">För att hantera anpassade identifieringar måste du tilldela en av följande roller:</span><span class="sxs-lookup"><span data-stu-id="80388-110">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="80388-111">**Säkerhets administratören** – rollen säkerhets administratör eller säkerhets administratör är en [Azure Active Directory-roll](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) för att hantera olika säkerhets inställningar i Microsoft 365 säkerhets Center och olika portaler och tjänster.</span><span class="sxs-lookup"><span data-stu-id="80388-111">**Security administrator** — the security administrator or security admin role is an [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) for managing various security settings in Microsoft 365 security center and various portals and services.</span></span>

- <span data-ttu-id="80388-112">**Säkerhets ansvarig** – rollen säkerhets ansvarig är en [Azure Active Directory-roll](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) för att hantera aviseringar och har globalt skrivskyddad åtkomst till säkerhetsrelaterade funktioner, inklusive all information i Microsoft 365 säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="80388-112">**Security operator** —  the security operator role is an [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) for managing alerts and has global read-only access on security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="80388-113">Den här rollen räcker bara till för att hantera anpassade identifieringar om RBAC (rollbaserad åtkomst kontroll) är inaktiverat i Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="80388-113">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender ATP.</span></span> <span data-ttu-id="80388-114">Om du har en RBAC-konfiguration behöver du även behörigheten **hantera säkerhets inställningar** för Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="80388-114">If you have RBAC configured, you also need the **manage security settings** permission for Microsoft Defender ATP.</span></span>

<span data-ttu-id="80388-115">För att hantera nödvändiga behörigheter kan en **Global administratör** göra följande:</span><span class="sxs-lookup"><span data-stu-id="80388-115">To manage required permissions, a **global administrator** can do the following:</span></span>

- <span data-ttu-id="80388-116">Koppla rollen som **säkerhets administratör** eller **säkerhets ansvarig** i [administrations centret för Microsoft 365](https://admin.microsoft.com/) under **roll**  >  **säkerhets administratör**.</span><span class="sxs-lookup"><span data-stu-id="80388-116">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="80388-117">Kontrol lera inställningar för RBAC för Microsoft Defender ATP i [Microsoft Defender säkerhets Center](https://securitycenter.windows.com/) under **Inställningar**för  >  **behörighets**  >  **roller**.</span><span class="sxs-lookup"><span data-stu-id="80388-117">Check RBAC settings for Microsoft Defender ATP in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="80388-118">Välj motsvarande roll för att tilldela behörigheten **hantera säkerhets inställningar** .</span><span class="sxs-lookup"><span data-stu-id="80388-118">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="80388-119">För att hantera anpassade identifieringar måste **säkerhets operatörerna** **hantera säkerhets inställningar** i Microsoft Defender ATP om RBAC är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="80388-119">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender ATP if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="80388-120">Skapa en anpassad detektions regel</span><span class="sxs-lookup"><span data-stu-id="80388-120">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="80388-121">1. förbereda frågan.</span><span class="sxs-lookup"><span data-stu-id="80388-121">1. Prepare the query.</span></span>

<span data-ttu-id="80388-122">I Microsoft 365 säkerhets Center går du till **Avancerad jakt** och väljer en befintlig fråga eller skapar en ny fråga.</span><span class="sxs-lookup"><span data-stu-id="80388-122">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="80388-123">Kör frågan för att identifiera fel och förstå möjliga resultat när du använder en ny fråga.</span><span class="sxs-lookup"><span data-stu-id="80388-123">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="80388-124">För att förhindra att tjänsten returnerar för många aviseringar begränsas varje regel för att bara generera 100-varningar när den körs.</span><span class="sxs-lookup"><span data-stu-id="80388-124">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="80388-125">Innan du skapar en regel kan du ställa in din fråga för att undvika att aviseringar visas för normal, daglig aktivitet.</span><span class="sxs-lookup"><span data-stu-id="80388-125">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="80388-126">Kolumner som krävs i frågeresultatet</span><span class="sxs-lookup"><span data-stu-id="80388-126">Required columns in the query results</span></span>
<span data-ttu-id="80388-127">Om du vill skapa en anpassad detektions regel måste frågan returnera följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="80388-127">To create a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- <span data-ttu-id="80388-128">En av följande kolumner för enhet, användare eller post lådor:</span><span class="sxs-lookup"><span data-stu-id="80388-128">One of the following device, user, or mailbox columns:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="80388-129">`SenderFromAddress`(kuvert avsändare eller RETUR adress)</span><span class="sxs-lookup"><span data-stu-id="80388-129">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="80388-130">`SenderMailFromAddress`(avsändar adress som visas i e-postklienten)</span><span class="sxs-lookup"><span data-stu-id="80388-130">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`
>[!NOTE]
><span data-ttu-id="80388-131">Stöd för ytterligare enheter läggs till när nya tabeller läggs till i det [avancerade jakt schemat](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="80388-131">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="80388-132">Enkla frågor, till exempel dem som inte använder `project` `summarize` operatorn eller för att anpassa resultat, returnerar normalt dessa vanliga kolumner.</span><span class="sxs-lookup"><span data-stu-id="80388-132">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="80388-133">Det finns olika sätt att se till att komplexa frågor returnerar de här kolumnerna.</span><span class="sxs-lookup"><span data-stu-id="80388-133">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="80388-134">Om du till exempel föredrar att aggregera och inventera efter entitet under en kolumn, `DeviceId` kan du ändå återgå till `Timestamp` genom att hämta den från den senaste händelsen som berör varje unikt `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="80388-134">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="80388-135">I exempel frågan nedan räknas antalet unika enheter ( `DeviceId` ) med Antivirus identifieringar och använder det här antalet för att endast hitta enheter med fler än fem identifieringar.</span><span class="sxs-lookup"><span data-stu-id="80388-135">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="80388-136">För att returnera det senaste `Timestamp` använder den `summarize` operatorn med `arg_max` funktionen.</span><span class="sxs-lookup"><span data-stu-id="80388-136">To return the latest `Timestamp`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where ActionType == "AntivirusDetection"
| summarize Timestamp = max(Timestamp), count() by DeviceId, SHA1, InitiatingProcessAccountObjectId 
| where count_ > 5
```

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="80388-137">2. skapa en ny regel och ange aviserings information.</span><span class="sxs-lookup"><span data-stu-id="80388-137">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="80388-138">Med frågan i Frågeredigeraren väljer du **skapa detektions regel** och anger följande aviserings information:</span><span class="sxs-lookup"><span data-stu-id="80388-138">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="80388-139">**Identifierings namn** – namnet på identifierings regeln</span><span class="sxs-lookup"><span data-stu-id="80388-139">**Detection name** — name of the detection rule</span></span>
- <span data-ttu-id="80388-140">**Frekvens** – ett tidsintervall som används för att köra frågan och vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="80388-140">**Frequency** — interval for running the query and taking action.</span></span> [<span data-ttu-id="80388-141">Se ytterligare vägledning nedan</span><span class="sxs-lookup"><span data-stu-id="80388-141">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="80388-142">**Aviserings rubrik** – titeln visas med notifieringar utlöst av regeln</span><span class="sxs-lookup"><span data-stu-id="80388-142">**Alert title** — title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="80388-143">**Allvarlighets grad** — den komponent eller aktivitet som identifieras av regeln</span><span class="sxs-lookup"><span data-stu-id="80388-143">**Severity** — potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="80388-144">**Kategori** – hot komponent eller aktivitet som identifieras av regeln</span><span class="sxs-lookup"><span data-stu-id="80388-144">**Category** — threat component or activity identified by the rule</span></span>
- <span data-ttu-id="80388-145">**Mitre to&CK-teknik** – en eller flera angrepp som identifieras av regeln enligt anvisningarna i [&MITREs ramverk](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="80388-145">**MITRE ATT&CK techniques** — one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="80388-146">Det här avsnittet gäller inte och är dolt för vissa varnings kategorier, inklusive skadlig program vara, utpressnings tro Jan, misstänkt aktivitet och oönskad tillämpning</span><span class="sxs-lookup"><span data-stu-id="80388-146">This section does not apply and is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="80388-147">**Beskrivning** – mer information om komponenten eller aktiviteten som identifieras av regeln</span><span class="sxs-lookup"><span data-stu-id="80388-147">**Description** — more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="80388-148">**Rekommenderade åtgärder** – ytterligare åtgärder som svars handlingar kan ta emot när det gäller en avisering</span><span class="sxs-lookup"><span data-stu-id="80388-148">**Recommended actions** — additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="80388-149">Regel frekvens</span><span class="sxs-lookup"><span data-stu-id="80388-149">Rule frequency</span></span>
<span data-ttu-id="80388-150">När den sparas körs en ny eller redige rad anpassad detektion direkt och söker efter träffar från de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="80388-150">When saved, a new or edited custom detection rule immediately runs and checks for matches from  the past 30 days of data.</span></span> <span data-ttu-id="80388-151">Regeln körs sedan igen med fasta tidsintervall och lookback varaktighet baserat på den frekvens du väljer:</span><span class="sxs-lookup"><span data-stu-id="80388-151">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="80388-152">Med ett **dygn** – löper ett dygn runt data från de senaste 30 dagarna</span><span class="sxs-lookup"><span data-stu-id="80388-152">**Every 24 hours** — runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="80388-153">**Var 12: e** timme – kör var tolfte timme och kontrol lera data från de senaste 24 timmarna</span><span class="sxs-lookup"><span data-stu-id="80388-153">**Every 12 hours** — runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="80388-154">**Var tredje timme** – kör var tredje timme, kontrol lera data från de senaste 6 timmarna</span><span class="sxs-lookup"><span data-stu-id="80388-154">**Every 3 hours** — runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="80388-155">**Varje timme** – kör per timme för att kontrol lera data från de senaste 2 timmarna</span><span class="sxs-lookup"><span data-stu-id="80388-155">**Every hour** — runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="80388-156">Välj den frekvens som motsvarar hur nära du vill övervaka identifieringarna och Överväg organisationens kapacitet för att svara på aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="80388-156">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="80388-157">3. Välj de enheter som påverkas.</span><span class="sxs-lookup"><span data-stu-id="80388-157">3. Choose the impacted entities.</span></span>
<span data-ttu-id="80388-158">Identifiera kolumnerna i frågeresultatet där du förväntar dig att hitta den huvud enhet som påverkas eller påverkas.</span><span class="sxs-lookup"><span data-stu-id="80388-158">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="80388-159">En fråga kan till exempel returnera avsändare ( `SenderFromAddress` eller `SenderMailFromAddress` )-och mottagar `RecipientEmailAddress` adresser.</span><span class="sxs-lookup"><span data-stu-id="80388-159">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="80388-160">Att identifiera vilka av de här kolumnerna som representerar huvud enheten som påverkas hjälper tjänsten att aggregera relevanta aviseringar, korrelera problem och åtgärder för mål svar.</span><span class="sxs-lookup"><span data-stu-id="80388-160">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="80388-161">Du kan bara välja en kolumn för varje entitetstyp (post låda, användare eller enhet).</span><span class="sxs-lookup"><span data-stu-id="80388-161">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="80388-162">Kolumner som inte returneras av frågan kan inte markeras.</span><span class="sxs-lookup"><span data-stu-id="80388-162">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="80388-163">4. ange åtgärder.</span><span class="sxs-lookup"><span data-stu-id="80388-163">4. Specify actions.</span></span>
<span data-ttu-id="80388-164">Din regel för anpassad avkänning kan automatiskt utföra åtgärder på enheter, filer eller användare som returneras av frågan.</span><span class="sxs-lookup"><span data-stu-id="80388-164">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="80388-165">Åtgärder på enheter</span><span class="sxs-lookup"><span data-stu-id="80388-165">Actions on devices</span></span>
<span data-ttu-id="80388-166">De här åtgärderna tillämpas på enheter i `DeviceId` kolumnen i frågeresultatet:</span><span class="sxs-lookup"><span data-stu-id="80388-166">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="80388-167">**Isolera enhet** – använder Microsoft Defender ATP för att tillämpa fullständig nätverks isolering, så att enheten inte kan ansluta till något program eller någon tjänst.</span><span class="sxs-lookup"><span data-stu-id="80388-167">**Isolate device** — uses Microsoft Defender ATP to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="80388-168">Läs mer om dator isolering för Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="80388-168">Learn more about Microsoft Defender ATP machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="80388-169">**Samla in undersöknings paket** – samlar in enhets information i en zip-fil.</span><span class="sxs-lookup"><span data-stu-id="80388-169">**Collect investigation package** — collects device information in a ZIP file.</span></span> [<span data-ttu-id="80388-170">Läs mer om Microsoft Defender-gransknings paketet för ATP</span><span class="sxs-lookup"><span data-stu-id="80388-170">Learn more about the Microsoft Defender ATP investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="80388-171">**Kör antivirus-genomsökning** – utför en fullständig Windows Defender Antivirus-genomsökning på enheten</span><span class="sxs-lookup"><span data-stu-id="80388-171">**Run antivirus scan** — performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="80388-172">**Inleda undersökning** – initierar en [Automatisk undersökning](mtp-autoir.md) på enheten</span><span class="sxs-lookup"><span data-stu-id="80388-172">**Initiate investigation** — initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="80388-173">**Begränsa program körning** – anger begränsningar för enheter för att endast tillåta att filer som är signerade med ett Microsoft-utfärdat certifikat körs.</span><span class="sxs-lookup"><span data-stu-id="80388-173">**Restrict app execution** — sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="80388-174">Läs mer om program begränsningar med Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="80388-174">Learn more about app restrictions with Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="80388-175">Åtgärder på filer</span><span class="sxs-lookup"><span data-stu-id="80388-175">Actions on files</span></span>
<span data-ttu-id="80388-176">När du väljer det här alternativet kan du välja att använda **karantän fil** åtgärden för filer `SHA1` i `InitiatingProcessSHA1` `SHA256` kolumnerna,, eller i `InitiatingProcessSHA256` frågeresultatet.</span><span class="sxs-lookup"><span data-stu-id="80388-176">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="80388-177">Den här åtgärden tar bort filen från dess nuvarande plats och placerar en kopia i karantän.</span><span class="sxs-lookup"><span data-stu-id="80388-177">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="80388-178">Åtgärder för användare</span><span class="sxs-lookup"><span data-stu-id="80388-178">Actions on users</span></span>
<span data-ttu-id="80388-179">När **det här** alternativet är markerat vidtas användare i `AccountObjectId` `InitiatingProcessAccountObjectId` kolumnen, eller, eller i `RecipientObjectId` frågeresultatet.</span><span class="sxs-lookup"><span data-stu-id="80388-179">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="80388-180">Den här åtgärden anger risk nivån för användare till "hög" i Azure Active Directory och utlöser motsvarande [identitets skydds principer](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span><span class="sxs-lookup"><span data-stu-id="80388-180">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="80388-181">Åtgärden tillåta eller blockera för anpassade identifierings regler stöds för närvarande inte för skydd mot Microsoft-hotet.</span><span class="sxs-lookup"><span data-stu-id="80388-181">The allow or block action for custom detection rules is currently not supported on Microsoft Threat Protection.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="80388-182">5. Ange regel omfånget.</span><span class="sxs-lookup"><span data-stu-id="80388-182">5. Set the rule scope.</span></span>
<span data-ttu-id="80388-183">Ange omfattningen för att ange vilka enheter som omfattas av regeln.</span><span class="sxs-lookup"><span data-stu-id="80388-183">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="80388-184">Omfattningen påverkar regler som kontrollerar enheter och påverkar inte regler som bara kontrollerar post lådor och användar konton eller identiteter.</span><span class="sxs-lookup"><span data-stu-id="80388-184">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="80388-185">När du ställer in omfattningen kan du välja:</span><span class="sxs-lookup"><span data-stu-id="80388-185">When setting the scope, you can select:</span></span>

- <span data-ttu-id="80388-186">Alla enheter</span><span class="sxs-lookup"><span data-stu-id="80388-186">All devices</span></span>
- <span data-ttu-id="80388-187">Specifika enhets grupper</span><span class="sxs-lookup"><span data-stu-id="80388-187">Specific device groups</span></span>

<span data-ttu-id="80388-188">Endast data från enheter i omfattning kommer att frågas.</span><span class="sxs-lookup"><span data-stu-id="80388-188">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="80388-189">Åtgärder kommer också att vidtas för dessa enheter.</span><span class="sxs-lookup"><span data-stu-id="80388-189">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="80388-190">6. granska och aktivera regeln.</span><span class="sxs-lookup"><span data-stu-id="80388-190">6. Review and turn on the rule.</span></span>
<span data-ttu-id="80388-191">När du har granskat regeln klickar du på **skapa** för att spara den.</span><span class="sxs-lookup"><span data-stu-id="80388-191">After reviewing the rule, click **Create** to save it.</span></span> <span data-ttu-id="80388-192">Den anpassade detektions regeln körs omedelbart.</span><span class="sxs-lookup"><span data-stu-id="80388-192">The custom detection rule immediately runs.</span></span> <span data-ttu-id="80388-193">Det körs igen baserat på konfigurerat frekvens för att kontrol lera träffar, generera aviseringar och vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="80388-193">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="80388-194">Hantera befintliga regler för anpassat identifiering</span><span class="sxs-lookup"><span data-stu-id="80388-194">Manage existing custom detection rules</span></span>
<span data-ttu-id="80388-195">Du kan visa en lista med befintliga regler för anpassad avkänning, kontrol lera deras tidigare körningar och granska de notifieringar de har utlöst.</span><span class="sxs-lookup"><span data-stu-id="80388-195">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="80388-196">Du kan också köra en regel på begäran och ändra den.</span><span class="sxs-lookup"><span data-stu-id="80388-196">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="80388-197">Visa befintliga regler</span><span class="sxs-lookup"><span data-stu-id="80388-197">View existing rules</span></span>

<span data-ttu-id="80388-198">Om du vill visa alla befintliga regler för anpassat identifiering navigerar du till **jakt**i  >  **anpassat**läge.</span><span class="sxs-lookup"><span data-stu-id="80388-198">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="80388-199">På sidan visas alla regler med följande kör information:</span><span class="sxs-lookup"><span data-stu-id="80388-199">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="80388-200">**Senaste körning** – när en regel senast kördes för att kontrol lera frågan och generera aviseringar</span><span class="sxs-lookup"><span data-stu-id="80388-200">**Last run** — when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="80388-201">**Senaste körnings status** – oavsett om en regel kördes</span><span class="sxs-lookup"><span data-stu-id="80388-201">**Last run status** — whether a rule ran successfully</span></span>
- <span data-ttu-id="80388-202">**Nästa kör** -nästa schemalagda körning</span><span class="sxs-lookup"><span data-stu-id="80388-202">**Next run** — the next scheduled run</span></span>
- <span data-ttu-id="80388-203">**Status** – om en regel har Aktiver ATS eller inaktiverats</span><span class="sxs-lookup"><span data-stu-id="80388-203">**Status** — whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="80388-204">Visa regel detaljer, ändra regel och kör regel</span><span class="sxs-lookup"><span data-stu-id="80388-204">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="80388-205">Om du vill visa omfattande information om en anpassad detektions regel väljer du namnet på regeln i listan med regler i **jaktens**  >  **anpassade identifieringar**.</span><span class="sxs-lookup"><span data-stu-id="80388-205">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="80388-206">Då öppnas en sida om den anpassade identifierings regeln med allmän information om regeln, inklusive information om varningen, kör status och omfattning.</span><span class="sxs-lookup"><span data-stu-id="80388-206">This opens a page about the custom detection rule with general information about the rule, including the details of the alert, run status, and scope.</span></span> <span data-ttu-id="80388-207">Den innehåller också en lista över utlösta varningar och utlösta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="80388-207">It also provides the list of triggered alerts and triggered actions.</span></span>

<span data-ttu-id="80388-208">![Sidan information om anpassad identifierings regel](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="80388-208">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="80388-209">*Information om anpassade identifierings regler*</span><span class="sxs-lookup"><span data-stu-id="80388-209">*Custom detection rule details*</span></span>

<span data-ttu-id="80388-210">Du kan också vidta följande åtgärder på regeln från den här sidan:</span><span class="sxs-lookup"><span data-stu-id="80388-210">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="80388-211">**Kör** – kör regeln omedelbart.</span><span class="sxs-lookup"><span data-stu-id="80388-211">**Run** — run the rule immediately.</span></span> <span data-ttu-id="80388-212">Detta återställer också intervallet för nästa körning.</span><span class="sxs-lookup"><span data-stu-id="80388-212">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="80388-213">**Redigera** – ändra regeln utan att ändra frågan</span><span class="sxs-lookup"><span data-stu-id="80388-213">**Edit** — modify the rule without changing the query</span></span>
- <span data-ttu-id="80388-214">**Ändra fråga** – redigera frågan i avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="80388-214">**Modify query** — edit the query in advanced hunting</span></span>
- <span data-ttu-id="80388-215">**Aktivera**  /  **Inaktivera** – aktivera regeln eller förhindra att den körs</span><span class="sxs-lookup"><span data-stu-id="80388-215">**Turn on** / **Turn off** — enable the rule or stop it from running</span></span>
- <span data-ttu-id="80388-216">**Ta bort** – inaktivera regeln och ta bort den</span><span class="sxs-lookup"><span data-stu-id="80388-216">**Delete** — turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="80388-217">Visa och hantera utlösta aviseringar</span><span class="sxs-lookup"><span data-stu-id="80388-217">View and manage triggered alerts</span></span>

<span data-ttu-id="80388-218">I fönstret med regel information (**jakt**  >  efter**anpassade identifieringar**  >  **[regel namn]**) går du till **utlösta varningar** för att visa listan med aviseringar som genererats av matchningar till regeln.</span><span class="sxs-lookup"><span data-stu-id="80388-218">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered alerts** to view the list of alerts generated by matches to the rule.</span></span> <span data-ttu-id="80388-219">Välj en avisering om du vill visa detaljerad information om den här aviseringen och vidta följande åtgärder för aviseringen:</span><span class="sxs-lookup"><span data-stu-id="80388-219">Select an alert to view detailed information about that alert and take the following actions on that alert:</span></span>

- <span data-ttu-id="80388-220">Hantera varningen genom att ange dess status och klassificering (sant eller falsk)</span><span class="sxs-lookup"><span data-stu-id="80388-220">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="80388-221">Länka aviseringen till en olycka</span><span class="sxs-lookup"><span data-stu-id="80388-221">Link the alert to an incident</span></span>
- <span data-ttu-id="80388-222">Kör frågan som utlöste aviseringen om avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="80388-222">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="80388-223">Gransknings åtgärder</span><span class="sxs-lookup"><span data-stu-id="80388-223">Review actions</span></span>
<span data-ttu-id="80388-224">I fönstret med regel detaljer (**jakt**på  >  **anpassade identifieringar**  >  **[regel namn]**) går du till **utlösta åtgärder** för att visa listan med åtgärder som utförs baserat på matchningar till regeln.</span><span class="sxs-lookup"><span data-stu-id="80388-224">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions** to view the list of actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="80388-225">Om du snabbt vill visa information och vidta åtgärder för ett objekt i en tabell använder du kolumn kolumnen [&#10003;] till vänster i tabellen.</span><span class="sxs-lookup"><span data-stu-id="80388-225">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topic"></a><span data-ttu-id="80388-226">Närliggande ämne</span><span class="sxs-lookup"><span data-stu-id="80388-226">Related topic</span></span>
- [<span data-ttu-id="80388-227">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="80388-227">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="80388-228">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="80388-228">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="80388-229">Lär dig mer om det avancerade frågespråket</span><span class="sxs-lookup"><span data-stu-id="80388-229">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)