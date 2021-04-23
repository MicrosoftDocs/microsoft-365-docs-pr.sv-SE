---
title: Skapa och hantera regler för anpassad identifiering i Microsoft 365 Defender
description: Lär dig hur du skapar och hanterar anpassade identifieringsregler baserat på avancerade sökfrågor
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, custom detections, rules, schema, kusto, RBAC, permissions, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: f37cc63c958331f7c03e09689de92c73fd06b4d4
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952566"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="681e7-104">Skapa och hantera anpassade identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="681e7-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="681e7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="681e7-105">**Applies to:**</span></span>
- <span data-ttu-id="681e7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="681e7-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="681e7-107">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="681e7-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="681e7-108">Anpassade identifieringsregler är regler som du kan utforma och modifiera [med hjälp av avancerade sökfrågor.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="681e7-108">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="681e7-109">Med dessa regler kan du proaktivt övervaka olika händelser och systemhändelser, inklusive misstänkt intrång och felkonfigurerade slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="681e7-109">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="681e7-110">Du kan ange att de ska köras med jämna mellanrum, generera aviseringar och vidta svarsåtgärder när det finns matchningar.</span><span class="sxs-lookup"><span data-stu-id="681e7-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="681e7-111">Behörighet som krävs för att hantera anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="681e7-111">Required permissions for managing custom detections</span></span>

<span data-ttu-id="681e7-112">För att kunna hantera anpassade identifieringar måste du tilldelas en av följande roller:</span><span class="sxs-lookup"><span data-stu-id="681e7-112">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="681e7-113">**Säkerhetsadministratör**– Användare med denna [Azure Active Directory-roll](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) kan hantera säkerhetsinställningar i Microsoft 365 säkerhetscenter och andra portaler och tjänster.</span><span class="sxs-lookup"><span data-stu-id="681e7-113">**Security administrator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="681e7-114">**Säkerhetsoperator**– Användare med denna [Azure Active Directory-roll](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) kan hantera aviseringar och ha global skrivskyddsåtkomst till säkerhetsrelaterade funktioner, inklusive all information i Säkerhetscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="681e7-114">**Security operator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="681e7-115">Den här rollen är tillräcklig för att hantera anpassade identifieringar endast om rollbaserad åtkomstkontroll (RBAC) är inaktiverad i Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="681e7-115">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="681e7-116">Om RBAC har konfigurerats behöver du också behörigheten hantera **säkerhetsinställningar** för Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="681e7-116">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="681e7-117">En global administratör kan hantera nödvändiga **behörigheter genom att:**</span><span class="sxs-lookup"><span data-stu-id="681e7-117">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="681e7-118">Tilldela rollen **som säkerhetsadministratör** **eller säkerhetsoperator** i administrationscentret för [Microsoft 365](https://admin.microsoft.com/) under **Roller –**  >  **säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="681e7-118">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="681e7-119">Kontrollera RBAC-inställningarna för Microsoft Defender för Slutpunkt i [Microsoft Defender Säkerhetscenter](https://securitycenter.windows.com/) under **Roller för**  >  **inställningar.**  >  </span><span class="sxs-lookup"><span data-stu-id="681e7-119">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="681e7-120">Välj motsvarande roll för att tilldela **behörigheten hantera säkerhetsinställningar.**</span><span class="sxs-lookup"><span data-stu-id="681e7-120">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="681e7-121">Om du vill hantera anpassade identifieringar **behöver** säkerhetsoperatorerna behörigheten hantera säkerhetsinställningar i Microsoft Defender för Endpoint om RBAC är aktiverat. </span><span class="sxs-lookup"><span data-stu-id="681e7-121">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="681e7-122">Skapa en anpassad identifieringsregel</span><span class="sxs-lookup"><span data-stu-id="681e7-122">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="681e7-123">1. Förbereda frågan.</span><span class="sxs-lookup"><span data-stu-id="681e7-123">1. Prepare the query.</span></span>

<span data-ttu-id="681e7-124">I Microsoft 365 säkerhetscenter går du till **Avancerad sökning** och väljer en befintlig fråga eller skapar en ny fråga.</span><span class="sxs-lookup"><span data-stu-id="681e7-124">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="681e7-125">När du använder en ny fråga kör du frågan för att identifiera fel och förstå möjliga resultat.</span><span class="sxs-lookup"><span data-stu-id="681e7-125">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="681e7-126">För att förhindra att tjänsten returnerar för många aviseringar är varje regel begränsad till att generera endast 100 aviseringar när den körs.</span><span class="sxs-lookup"><span data-stu-id="681e7-126">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="681e7-127">Innan du skapar en regel bör du justera frågan för att undvika aviseringar om normal aktivitet.</span><span class="sxs-lookup"><span data-stu-id="681e7-127">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="681e7-128">Obligatoriska kolumner i frågeresultatet</span><span class="sxs-lookup"><span data-stu-id="681e7-128">Required columns in the query results</span></span>
<span data-ttu-id="681e7-129">Om du vill skapa en anpassad identifieringsregel måste frågan returnera följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="681e7-129">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="681e7-130">`Timestamp`– används för att ange tidsstämpeln för genererade aviseringar</span><span class="sxs-lookup"><span data-stu-id="681e7-130">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="681e7-131">`ReportId`– aktiverar uppslag för de ursprungliga posterna</span><span class="sxs-lookup"><span data-stu-id="681e7-131">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="681e7-132">En av följande kolumner som identifierar specifika enheter, användare eller postlådor:</span><span class="sxs-lookup"><span data-stu-id="681e7-132">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="681e7-133">`SenderFromAddress` (kuvertavsändare Return-Path adress)</span><span class="sxs-lookup"><span data-stu-id="681e7-133">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="681e7-134">`SenderMailFromAddress` (avsändaradressen visas i e-postklienten)</span><span class="sxs-lookup"><span data-stu-id="681e7-134">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="681e7-135">Stöd för ytterligare enheter läggs till när nya tabeller läggs till i det [avancerade sökschemat.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="681e7-135">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="681e7-136">Enkla frågor, till exempel de som inte använder operatorn eller för att anpassa eller sammanställa resultat, returnerar `project` `summarize` vanligtvis dessa gemensamma kolumner.</span><span class="sxs-lookup"><span data-stu-id="681e7-136">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="681e7-137">Det finns olika sätt att säkerställa att mer komplexa frågor returnerar dessa kolumner.</span><span class="sxs-lookup"><span data-stu-id="681e7-137">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="681e7-138">Om du till exempel föredrar att aggregera och räkna efter entitet under en kolumn som , kan du fortfarande returnera och genom att hämta den från den senaste händelsen som innefattar `DeviceId` `Timestamp` varje unik `ReportId` `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="681e7-138">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="681e7-139">I exempelfrågan nedan räknas antalet unika enheter () med antivirusidentifiering och antalet används för att endast hitta enheter med `DeviceId` fler än fem identifieringar.</span><span class="sxs-lookup"><span data-stu-id="681e7-139">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="681e7-140">För att returnera det `Timestamp` senaste och motsvarande används `ReportId` `summarize` operatorn med `arg_max` funktionen.</span><span class="sxs-lookup"><span data-stu-id="681e7-140">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="681e7-141">För att få bättre frågeprestanda kan du ange ett tidsfilter som matchar den avsedda körningsfrekvensen för regeln.</span><span class="sxs-lookup"><span data-stu-id="681e7-141">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="681e7-142">Eftersom det minsta antalet körningar är en gång _per dygn_ omfattar filtreringen för den senaste dagen alla nya data.</span><span class="sxs-lookup"><span data-stu-id="681e7-142">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="681e7-143">2. Skapa en ny regel och ange aviseringsinformation.</span><span class="sxs-lookup"><span data-stu-id="681e7-143">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="681e7-144">Med frågan i frågeredigeraren väljer du **Skapa identifieringsregel** och anger följande aviseringsinformation:</span><span class="sxs-lookup"><span data-stu-id="681e7-144">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="681e7-145">**Identifieringsnamn**– namnet på identifieringsregeln</span><span class="sxs-lookup"><span data-stu-id="681e7-145">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="681e7-146">**Frekvens**– intervall för att köra frågan och vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="681e7-146">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="681e7-147">Mer information finns nedan</span><span class="sxs-lookup"><span data-stu-id="681e7-147">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="681e7-148">**Aviseringsrubrik**– rubrik som visas med aviseringar som utlöses av regeln</span><span class="sxs-lookup"><span data-stu-id="681e7-148">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="681e7-149">**Allvarlighetsgrad**– potentiell risk för komponenten eller aktiviteten som identifieras av regeln</span><span class="sxs-lookup"><span data-stu-id="681e7-149">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="681e7-150">**Kategori**– hotkomponent eller aktivitet som identifieras av regeln</span><span class="sxs-lookup"><span data-stu-id="681e7-150">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="681e7-151">**MITRE ATT&CK-tekniker**– en eller flera attacktekniker som identifieras av regeln enligt reglerna som beskrivs i [MITRE ATT&CK-ramverket.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="681e7-151">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="681e7-152">Det här avsnittet är dolt för vissa aviseringskategorier, till exempel skadlig kod, utpressningstrojaner, misstänkt aktivitet och oönskad programvara</span><span class="sxs-lookup"><span data-stu-id="681e7-152">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="681e7-153">**Beskrivning**– mer information om komponenten eller aktiviteten som identifieras av regeln</span><span class="sxs-lookup"><span data-stu-id="681e7-153">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="681e7-154">**Rekommenderade åtgärder**– ytterligare åtgärder som svarare kan vidta för en avisering</span><span class="sxs-lookup"><span data-stu-id="681e7-154">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="681e7-155">Regelfrekvens</span><span class="sxs-lookup"><span data-stu-id="681e7-155">Rule frequency</span></span>
<span data-ttu-id="681e7-156">När du sparar en ny regel körs den och söker efter matchningar från de senaste 30 dagarnas data.</span><span class="sxs-lookup"><span data-stu-id="681e7-156">When you save a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="681e7-157">Regeln körs sedan igen med fasta intervall, och en motslagsvaraktighet tillämpas baserat på den frekvens du väljer:</span><span class="sxs-lookup"><span data-stu-id="681e7-157">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="681e7-158">**Körs en gång per dygn** och kontrollerar data från de senaste 30 dagarna</span><span class="sxs-lookup"><span data-stu-id="681e7-158">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="681e7-159">**Körs var 12:e** timme per dygn och kontrollerar data från de senaste 24 timmarna</span><span class="sxs-lookup"><span data-stu-id="681e7-159">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="681e7-160">**Körs var tredje timme** och kontrollerar data från de senaste 6 timmarna</span><span class="sxs-lookup"><span data-stu-id="681e7-160">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="681e7-161">**Varje timme** körs varje timme och du kontrollerar data från de senaste två timmarna</span><span class="sxs-lookup"><span data-stu-id="681e7-161">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="681e7-162">När du redigerar en regel körs den med tillämpade ändringar under nästa körning enligt den frekvens du har angett.</span><span class="sxs-lookup"><span data-stu-id="681e7-162">When you edit a rule, it will run with the applied changes in the next run time scheduled according to the frequency you set.</span></span>



>[!TIP]
> <span data-ttu-id="681e7-163">Matcha tidsfiltren i frågan med tillbakaslagslängden.</span><span class="sxs-lookup"><span data-stu-id="681e7-163">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="681e7-164">Resultat utanför återställningsvaraktigheten ignoreras.</span><span class="sxs-lookup"><span data-stu-id="681e7-164">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="681e7-165">Välj den frekvens som matchar hur nära du vill övervaka identifieringar.</span><span class="sxs-lookup"><span data-stu-id="681e7-165">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="681e7-166">Ta hänsyn till organisationens kapacitet att svara på aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="681e7-166">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="681e7-167">3. Välj de berörda enheterna.</span><span class="sxs-lookup"><span data-stu-id="681e7-167">3. Choose the impacted entities.</span></span>
<span data-ttu-id="681e7-168">Identifiera kolumnerna i frågeresultatet där du förväntar dig att hitta den viktigaste påverkade eller påverkade enheten.</span><span class="sxs-lookup"><span data-stu-id="681e7-168">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="681e7-169">En fråga kan till exempel returnera avsändarens ( `SenderFromAddress` eller `SenderMailFromAddress` ) och mottagarens ( ) `RecipientEmailAddress` adresser.</span><span class="sxs-lookup"><span data-stu-id="681e7-169">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="681e7-170">Genom att identifiera vilka av dessa kolumner som representerar den viktigaste påverkade enheten bidrar tjänsten till att slå samman relevanta aviseringar, korrelera incidenter och målsvarsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="681e7-170">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="681e7-171">Du kan bara välja en kolumn för varje entitetstyp (postlåda, användare eller enhet).</span><span class="sxs-lookup"><span data-stu-id="681e7-171">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="681e7-172">Kolumner som inte returneras av frågan kan inte markeras.</span><span class="sxs-lookup"><span data-stu-id="681e7-172">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="681e7-173">4. Ange åtgärder.</span><span class="sxs-lookup"><span data-stu-id="681e7-173">4. Specify actions.</span></span>
<span data-ttu-id="681e7-174">Den anpassade identifieringsregeln kan automatiskt vidta åtgärder på enheter, filer eller användare som returneras av frågan.</span><span class="sxs-lookup"><span data-stu-id="681e7-174">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="681e7-175">Åtgärder på enheter</span><span class="sxs-lookup"><span data-stu-id="681e7-175">Actions on devices</span></span>
<span data-ttu-id="681e7-176">Dessa åtgärder tillämpas på enheter i `DeviceId` kolumnen med frågeresultat:</span><span class="sxs-lookup"><span data-stu-id="681e7-176">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="681e7-177">**Isolera enhet**– använder Microsoft Defender för Endpoint för att tillämpa fullständig nätverksisolering, vilket hindrar enheten från att ansluta till något program eller en tjänst.</span><span class="sxs-lookup"><span data-stu-id="681e7-177">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="681e7-178">Läs mer om Microsoft Defender för Endpoint-datorisolering</span><span class="sxs-lookup"><span data-stu-id="681e7-178">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="681e7-179">Samla in **undersökningspaket**– samlar in enhetsinformation i en ZIP-fil.</span><span class="sxs-lookup"><span data-stu-id="681e7-179">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="681e7-180">Läs mer om Microsoft Defender för undersökningspaketet för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="681e7-180">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="681e7-181">**Kör antivirussökning**– utför en fullständig Windows Defender Antivirus-sökning på enheten</span><span class="sxs-lookup"><span data-stu-id="681e7-181">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="681e7-182">**Initiera undersökning**– initierar en [automatiserad undersökning](m365d-autoir.md) på enheten</span><span class="sxs-lookup"><span data-stu-id="681e7-182">**Initiate investigation**—initiates an [automated investigation](m365d-autoir.md) on the device</span></span>
- <span data-ttu-id="681e7-183">**Begränsa programkörning**– anger begränsningar på enheten så att endast filer som har signerats med ett Certifikat utfärdat av Microsoft kan köras.</span><span class="sxs-lookup"><span data-stu-id="681e7-183">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="681e7-184">Läs mer om appbegränsningar med Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="681e7-184">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="681e7-185">Åtgärder för filer</span><span class="sxs-lookup"><span data-stu-id="681e7-185">Actions on files</span></span>
<span data-ttu-id="681e7-186">Med det här alternativet kan du välja att **tillämpa filåtgärden** Karantän för filer i `SHA1` , , eller kolumnen i `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` frågeresultatet.</span><span class="sxs-lookup"><span data-stu-id="681e7-186">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="681e7-187">Den här åtgärden tar bort filen från dess aktuella plats och placerar en kopia i karantän.</span><span class="sxs-lookup"><span data-stu-id="681e7-187">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="681e7-188">Åtgärder för användare</span><span class="sxs-lookup"><span data-stu-id="681e7-188">Actions on users</span></span>
<span data-ttu-id="681e7-189">Med det här alternativet **vidtas åtgärden Markera** användare som komprometterad på användare i , eller i kolumnen för `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` frågeresultatet.</span><span class="sxs-lookup"><span data-stu-id="681e7-189">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="681e7-190">Med den här åtgärden ställs användarnas risknivå in på "hög" i Azure Active Directory, vilket utlöser motsvarande [identitetsskyddsprinciper.](/azure/active-directory/identity-protection/overview-identity-protection)</span><span class="sxs-lookup"><span data-stu-id="681e7-190">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="681e7-191">Åtgärden tillåt eller blockera för anpassade identifieringsregler stöds för närvarande inte i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="681e7-191">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="681e7-192">5. Ange regelns omfattning.</span><span class="sxs-lookup"><span data-stu-id="681e7-192">5. Set the rule scope.</span></span>
<span data-ttu-id="681e7-193">Ange omfattningen för att ange vilka enheter som omfattas av regeln.</span><span class="sxs-lookup"><span data-stu-id="681e7-193">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="681e7-194">Omfattningen påverkar regler som kontrollerar enheter och påverkar inte regler som bara kontrollerar postlådor och användarkonton eller identiteter.</span><span class="sxs-lookup"><span data-stu-id="681e7-194">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="681e7-195">När du anger omfattningen kan du välja:</span><span class="sxs-lookup"><span data-stu-id="681e7-195">When setting the scope, you can select:</span></span>

- <span data-ttu-id="681e7-196">Alla enheter</span><span class="sxs-lookup"><span data-stu-id="681e7-196">All devices</span></span>
- <span data-ttu-id="681e7-197">Specifika enhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="681e7-197">Specific device groups</span></span>

<span data-ttu-id="681e7-198">Endast data från enheter i omfattningen kommer att tillfrågas.</span><span class="sxs-lookup"><span data-stu-id="681e7-198">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="681e7-199">Dessutom kommer åtgärder endast att vidtas på de enheterna.</span><span class="sxs-lookup"><span data-stu-id="681e7-199">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="681e7-200">6. Granska och aktivera regeln.</span><span class="sxs-lookup"><span data-stu-id="681e7-200">6. Review and turn on the rule.</span></span>
<span data-ttu-id="681e7-201">När du har granskat regeln väljer du **Skapa för** att spara den.</span><span class="sxs-lookup"><span data-stu-id="681e7-201">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="681e7-202">Regeln för anpassad identifiering körs direkt.</span><span class="sxs-lookup"><span data-stu-id="681e7-202">The custom detection rule immediately runs.</span></span> <span data-ttu-id="681e7-203">Den körs igen baserat på konfigurerad frekvens för att söka efter matchningar, generera aviseringar och vidta svarsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="681e7-203">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>


>[!Important] 
><span data-ttu-id="681e7-204">Anpassade identifieringar bör regelbundet granskas av effektivitet och effektivitet.</span><span class="sxs-lookup"><span data-stu-id="681e7-204">Custom detections should be regularly reviewed for efficiency and effectiveness.</span></span> <span data-ttu-id="681e7-205">Om du vill vara säker på att du skapar identifieringar som utlöser sanna aviseringar tar det tid att granska dina befintliga anpassade identifieringar genom att följa stegen i Hantera [befintliga anpassade identifieringsregler.](#manage-existing-custom-detection-rules)</span><span class="sxs-lookup"><span data-stu-id="681e7-205">To make sure you are creating detections that trigger true alerts, take time to review your existing custom detections by following the steps in [Manage existing custom detection rules](#manage-existing-custom-detection-rules).</span></span> <br>  
<span data-ttu-id="681e7-206">Du behåller kontrollen över hur omfattande eller specifika dina anpassade identifieringar är, så falska varningar som genereras av anpassade identifieringar kan ange ett behov av att ändra vissa parametrar för reglerna.</span><span class="sxs-lookup"><span data-stu-id="681e7-206">You maintain control over the broadness or specificity of your custom detections so any false alerts generated by custom detections might indicate a need to modify certain parameters of the rules.</span></span>


## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="681e7-207">Hantera befintliga anpassade identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="681e7-207">Manage existing custom detection rules</span></span>
<span data-ttu-id="681e7-208">Du kan visa listan över befintliga anpassade identifieringsregler, kontrollera deras tidigare körningar och granska de aviseringar som de har utlöst.</span><span class="sxs-lookup"><span data-stu-id="681e7-208">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="681e7-209">Du kan även köra en regel på begäran och ändra den.</span><span class="sxs-lookup"><span data-stu-id="681e7-209">You can also run a rule on demand and modify it.</span></span>

>[!TIP]
> <span data-ttu-id="681e7-210">Aviseringar som upphöjs med anpassade identifieringar är tillgängliga via API:er för aviseringar och incidenter.</span><span class="sxs-lookup"><span data-stu-id="681e7-210">Alerts raised by custom detections are available over alerts and incident APIs.</span></span> <span data-ttu-id="681e7-211">Mer information finns i Microsoft [365 Defender-API:er som stöds.](api-supported.md)</span><span class="sxs-lookup"><span data-stu-id="681e7-211">For more information, see [Supported Microsoft 365 Defender APIs](api-supported.md).</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="681e7-212">Visa befintliga regler</span><span class="sxs-lookup"><span data-stu-id="681e7-212">View existing rules</span></span>

<span data-ttu-id="681e7-213">Om du vill visa alla befintliga anpassade identifieringsregler går du **till Söka** efter  >  **anpassade identifieringar.**</span><span class="sxs-lookup"><span data-stu-id="681e7-213">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="681e7-214">På sidan visas alla regler med följande körningsinformation:</span><span class="sxs-lookup"><span data-stu-id="681e7-214">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="681e7-215">**Senaste körningen**– när en regel senast körts för att söka efter frågematchningar och generera aviseringar</span><span class="sxs-lookup"><span data-stu-id="681e7-215">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="681e7-216">**Status för senaste körningen**– om en regel kördes som den ska</span><span class="sxs-lookup"><span data-stu-id="681e7-216">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="681e7-217">**Nästa körning**– nästa schemalagda körning</span><span class="sxs-lookup"><span data-stu-id="681e7-217">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="681e7-218">**Status**– om en regel har aktiverats eller inaktiverats</span><span class="sxs-lookup"><span data-stu-id="681e7-218">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="681e7-219">Visa regeldetaljer, ändra regel och köra regel</span><span class="sxs-lookup"><span data-stu-id="681e7-219">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="681e7-220">Om du vill visa omfattande information om en anpassad identifieringsregel **går** du till  >  Anpassade identifieringar av **visning** och väljer namnet på regeln.</span><span class="sxs-lookup"><span data-stu-id="681e7-220">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="681e7-221">Du kan sedan visa allmän information om regeln, inklusive information om dess körningsstatus och omfattning.</span><span class="sxs-lookup"><span data-stu-id="681e7-221">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="681e7-222">Sidan innehåller också en lista över utlösande aviseringar och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="681e7-222">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="681e7-223">![Sidan Information om anpassade identifieringsregel](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="681e7-223">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="681e7-224">*Information om anpassade identifieringsregel*</span><span class="sxs-lookup"><span data-stu-id="681e7-224">*Custom detection rule details*</span></span>

<span data-ttu-id="681e7-225">Du kan också utföra följande åtgärder på regeln från den här sidan:</span><span class="sxs-lookup"><span data-stu-id="681e7-225">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="681e7-226">**Kör**– kör regeln direkt.</span><span class="sxs-lookup"><span data-stu-id="681e7-226">**Run**—run the rule immediately.</span></span> <span data-ttu-id="681e7-227">Då återställs också intervallet för nästa körning.</span><span class="sxs-lookup"><span data-stu-id="681e7-227">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="681e7-228">**Redigera**– ändra regeln utan att ändra frågan</span><span class="sxs-lookup"><span data-stu-id="681e7-228">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="681e7-229">**Ändra fråga**– redigera frågan under avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="681e7-229">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="681e7-230">**Aktivera**  /  **Inaktivera –** aktivera regeln eller hindra den från att köras</span><span class="sxs-lookup"><span data-stu-id="681e7-230">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="681e7-231">**Ta** bort – inaktivera regeln och ta bort den</span><span class="sxs-lookup"><span data-stu-id="681e7-231">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="681e7-232">Visa och hantera utlösande aviseringar</span><span class="sxs-lookup"><span data-stu-id="681e7-232">View and manage triggered alerts</span></span>

<span data-ttu-id="681e7-233">På skärmen med regeldetaljer (**Anpassad** identifiering av uppgifter  >    >  **[Regelnamn]**) går du till Utlösade aviseringar, som visar de aviseringar som genererats av matchningar mot regeln.</span><span class="sxs-lookup"><span data-stu-id="681e7-233">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="681e7-234">Välj en avisering om du vill visa detaljerad information om den och utföra följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="681e7-234">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="681e7-235">Hantera aviseringen genom att ange dess status och klassificering (sant eller falskt meddelande)</span><span class="sxs-lookup"><span data-stu-id="681e7-235">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="681e7-236">Länka aviseringen till en händelse</span><span class="sxs-lookup"><span data-stu-id="681e7-236">Link the alert to an incident</span></span>
- <span data-ttu-id="681e7-237">Kör frågan som utlöste varningen vid avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="681e7-237">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="681e7-238">Granska åtgärder</span><span class="sxs-lookup"><span data-stu-id="681e7-238">Review actions</span></span>
<span data-ttu-id="681e7-239">På skärmen med regeldetaljer **(** Anpassade identifieringar av uppgifter  >    >  **[Regelnamn] )** går du till Utlösade åtgärder, där de åtgärder som vidtas baserat på matchningar mot regeln visas.</span><span class="sxs-lookup"><span data-stu-id="681e7-239">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="681e7-240">Om du snabbt vill visa information och vidta åtgärder för ett objekt i en tabell använder du urvalskolumnen [&#10003;] till vänster om tabellen.</span><span class="sxs-lookup"><span data-stu-id="681e7-240">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

>[!NOTE]
><span data-ttu-id="681e7-241">Vissa kolumner i den här artikeln kanske inte är tillgängliga i Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="681e7-241">Some columns in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="681e7-242">[Aktivera Microsoft 365 Defender för](m365d-enable.md) att leta efter hot med hjälp av fler datakällor.</span><span class="sxs-lookup"><span data-stu-id="681e7-242">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="681e7-243">Du kan flytta dina avancerade arbetsflöden för sökning från Microsoft Defender för Slutpunkt till Microsoft 365 Defender genom att följa stegen i Migrera avancerade sökfrågor från [Microsoft Defender för Slutpunkt.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="681e7-243">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="681e7-244">Se även</span><span class="sxs-lookup"><span data-stu-id="681e7-244">See also</span></span>
- [<span data-ttu-id="681e7-245">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="681e7-245">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="681e7-246">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="681e7-246">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="681e7-247">Lär dig språket för avancerad fråga om sökning</span><span class="sxs-lookup"><span data-stu-id="681e7-247">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="681e7-248">Migrera avancerade frågor om sökning från Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="681e7-248">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
