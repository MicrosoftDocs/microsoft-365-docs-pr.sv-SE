---
title: Skapa och hantera regler för anpassad identifiering i Microsoft 365 Defender
description: Lär dig hur du skapar och hanterar anpassade identifieringsregler baserat på avancerade sökfrågor
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, custom detections, rules, schema, kusto, microsoft 365, Microsoft Threat Protection, RBAC, permissions, Microsoft Defender ATP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9699b5e2bc2e33b94795b7c23bd3f34f0383a8cc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068982"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="f8ca5-104">Skapa och hantera anpassade identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="f8ca5-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f8ca5-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f8ca5-105">**Applies to:**</span></span>
- <span data-ttu-id="f8ca5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8ca5-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f8ca5-107">Anpassade identifieringsregler är regler som du kan utforma och modifiera [med hjälp av avancerade sökfrågor.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f8ca5-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="f8ca5-108">Med dessa regler kan du proaktivt övervaka olika händelser och systemhändelser, inklusive misstänkt intrång och felkonfigurerade slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="f8ca5-109">Du kan ange att de ska köras med jämna mellanrum, generera aviseringar och vidta svarsåtgärder när det finns matchningar.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="f8ca5-110">Behörighet som krävs för att hantera anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="f8ca5-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="f8ca5-111">För att kunna hantera anpassade identifieringar måste du tilldelas en av följande roller:</span><span class="sxs-lookup"><span data-stu-id="f8ca5-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="f8ca5-112">**Säkerhetsadministratör**– Användare med denna [Azure Active Directory-roll](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) kan hantera säkerhetsinställningar i Microsoft 365 säkerhetscenter och andra portaler och tjänster.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-112">**Security administrator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="f8ca5-113">**Säkerhetsoperator**– Användare med denna [Azure Active Directory-roll](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) kan hantera aviseringar och ha global skrivskyddsåtkomst till säkerhetsrelaterade funktioner, inklusive all information i Säkerhetscenter för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-113">**Security operator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="f8ca5-114">Den här rollen är tillräcklig för att hantera anpassade identifieringar endast om rollbaserad åtkomstkontroll (RBAC) är inaktiverad i Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="f8ca5-115">Om RBAC har konfigurerats behöver du också behörigheten hantera **säkerhetsinställningar** för Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-115">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="f8ca5-116">En global administratör kan hantera nödvändiga **behörigheter genom att:**</span><span class="sxs-lookup"><span data-stu-id="f8ca5-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="f8ca5-117">Tilldela rollen **som säkerhetsadministratör** **eller säkerhetsoperator** i administrationscentret för [Microsoft 365](https://admin.microsoft.com/) under **Roller –**  >  **säkerhetsadministratör.**</span><span class="sxs-lookup"><span data-stu-id="f8ca5-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="f8ca5-118">Kontrollera RBAC-inställningarna för Microsoft Defender för Slutpunkt i [Microsoft Defender Säkerhetscenter](https://securitycenter.windows.com/) under **Roller för**  >  **inställningar.**  >  </span><span class="sxs-lookup"><span data-stu-id="f8ca5-118">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="f8ca5-119">Välj motsvarande roll för att tilldela **behörigheten hantera säkerhetsinställningar.**</span><span class="sxs-lookup"><span data-stu-id="f8ca5-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="f8ca5-120">Om du vill hantera anpassade identifieringar **behöver** säkerhetsoperatorerna behörigheten hantera säkerhetsinställningar i Microsoft Defender för Endpoint om RBAC är aktiverat. </span><span class="sxs-lookup"><span data-stu-id="f8ca5-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="f8ca5-121">Skapa en anpassad identifieringsregel</span><span class="sxs-lookup"><span data-stu-id="f8ca5-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="f8ca5-122">1. Förbereda frågan.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-122">1. Prepare the query.</span></span>

<span data-ttu-id="f8ca5-123">I Microsoft 365 säkerhetscenter går du till **Avancerad sökning** och väljer en befintlig fråga eller skapar en ny fråga.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="f8ca5-124">När du använder en ny fråga kör du frågan för att identifiera fel och förstå möjliga resultat.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="f8ca5-125">För att förhindra att tjänsten returnerar för många aviseringar är varje regel begränsad till att generera endast 100 aviseringar när den körs.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="f8ca5-126">Innan du skapar en regel bör du justera frågan för att undvika aviseringar om normal aktivitet.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="f8ca5-127">Obligatoriska kolumner i frågeresultatet</span><span class="sxs-lookup"><span data-stu-id="f8ca5-127">Required columns in the query results</span></span>
<span data-ttu-id="f8ca5-128">Om du vill skapa en anpassad identifieringsregel måste frågan returnera följande kolumner:</span><span class="sxs-lookup"><span data-stu-id="f8ca5-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="f8ca5-129">`Timestamp`– används för att ange tidsstämpeln för genererade aviseringar</span><span class="sxs-lookup"><span data-stu-id="f8ca5-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="f8ca5-130">`ReportId`– aktiverar uppslag för de ursprungliga posterna</span><span class="sxs-lookup"><span data-stu-id="f8ca5-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="f8ca5-131">En av följande kolumner som identifierar specifika enheter, användare eller postlådor:</span><span class="sxs-lookup"><span data-stu-id="f8ca5-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="f8ca5-132">`SenderFromAddress` (kuvertavsändare Return-Path adress)</span><span class="sxs-lookup"><span data-stu-id="f8ca5-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="f8ca5-133">`SenderMailFromAddress` (avsändaradressen visas i e-postklienten)</span><span class="sxs-lookup"><span data-stu-id="f8ca5-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="f8ca5-134">Stöd för ytterligare enheter läggs till när nya tabeller läggs till i det [avancerade sökschemat.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="f8ca5-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="f8ca5-135">Enkla frågor, till exempel de som inte använder operatorn eller för att anpassa eller sammanställa resultat, returnerar `project` `summarize` vanligtvis dessa gemensamma kolumner.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="f8ca5-136">Det finns olika sätt att säkerställa att mer komplexa frågor returnerar dessa kolumner.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="f8ca5-137">Om du till exempel föredrar att aggregera och räkna efter entitet under en kolumn som , kan du fortfarande returnera och genom att hämta den från den senaste händelsen som innefattar `DeviceId` `Timestamp` varje unik `ReportId` `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="f8ca5-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="f8ca5-138">I exempelfrågan nedan räknas antalet unika enheter () med antivirusidentifiering och antalet används för att endast hitta enheter med `DeviceId` fler än fem identifieringar.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="f8ca5-139">För att returnera det `Timestamp` senaste och motsvarande används `ReportId` `summarize` operatorn med `arg_max` funktionen.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="f8ca5-140">För att få bättre frågeprestanda kan du ange ett tidsfilter som matchar den avsedda körningsfrekvensen för regeln.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="f8ca5-141">Eftersom det minsta antalet körningar är en gång _per dygn_ omfattar filtreringen för den senaste dagen alla nya data.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="f8ca5-142">2. Skapa en ny regel och ange aviseringsinformation.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="f8ca5-143">Med frågan i frågeredigeraren väljer du **Skapa identifieringsregel** och anger följande aviseringsinformation:</span><span class="sxs-lookup"><span data-stu-id="f8ca5-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="f8ca5-144">**Identifieringsnamn**– namnet på identifieringsregeln</span><span class="sxs-lookup"><span data-stu-id="f8ca5-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="f8ca5-145">**Frekvens**– intervall för att köra frågan och vidta åtgärder.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="f8ca5-146">Mer information finns nedan</span><span class="sxs-lookup"><span data-stu-id="f8ca5-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="f8ca5-147">**Aviseringsrubrik**– rubrik som visas med aviseringar som utlöses av regeln</span><span class="sxs-lookup"><span data-stu-id="f8ca5-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="f8ca5-148">**Allvarlighetsgrad**– potentiell risk för komponenten eller aktiviteten som identifieras av regeln</span><span class="sxs-lookup"><span data-stu-id="f8ca5-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="f8ca5-149">**Kategori**– hotkomponent eller aktivitet som identifieras av regeln</span><span class="sxs-lookup"><span data-stu-id="f8ca5-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="f8ca5-150">**MITRE ATT&CK-tekniker**– en eller flera attacktekniker som identifieras av regeln enligt reglerna som beskrivs i [MITRE ATT&CK-ramverket.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="f8ca5-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="f8ca5-151">Det här avsnittet är dolt för vissa aviseringskategorier, till exempel skadlig kod, utpressningstrojaner, misstänkt aktivitet och oönskad programvara</span><span class="sxs-lookup"><span data-stu-id="f8ca5-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="f8ca5-152">**Beskrivning**– mer information om komponenten eller aktiviteten som identifieras av regeln</span><span class="sxs-lookup"><span data-stu-id="f8ca5-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="f8ca5-153">**Rekommenderade åtgärder**– ytterligare åtgärder som svarare kan vidta för en avisering</span><span class="sxs-lookup"><span data-stu-id="f8ca5-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="f8ca5-154">Regelfrekvens</span><span class="sxs-lookup"><span data-stu-id="f8ca5-154">Rule frequency</span></span>
<span data-ttu-id="f8ca5-155">När du sparar eller redigerar en ny regel körs den och söker efter matchningar från de senaste 30 dagarnas data.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="f8ca5-156">Regeln körs sedan igen med fasta intervall, och en motslagsvaraktighet tillämpas baserat på den frekvens du väljer:</span><span class="sxs-lookup"><span data-stu-id="f8ca5-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="f8ca5-157">**Körs en gång per dygn** och kontrollerar data från de senaste 30 dagarna</span><span class="sxs-lookup"><span data-stu-id="f8ca5-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="f8ca5-158">**Körs var 12:e** timme per dygn och kontrollerar data från de senaste 24 timmarna</span><span class="sxs-lookup"><span data-stu-id="f8ca5-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="f8ca5-159">**Körs var tredje timme** och kontrollerar data från de senaste 6 timmarna</span><span class="sxs-lookup"><span data-stu-id="f8ca5-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="f8ca5-160">**Varje timme** körs varje timme och du kontrollerar data från de senaste två timmarna</span><span class="sxs-lookup"><span data-stu-id="f8ca5-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="f8ca5-161">Matcha tidsfiltren i frågan med tillbakaslagslängden.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="f8ca5-162">Resultat utanför återställningsvaraktigheten ignoreras.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="f8ca5-163">Välj den frekvens som matchar hur nära du vill övervaka identifieringar.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="f8ca5-164">Ta hänsyn till organisationens kapacitet att svara på aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="f8ca5-165">3. Välj de berörda enheterna.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="f8ca5-166">Identifiera kolumnerna i frågeresultatet där du förväntar dig att hitta den viktigaste påverkade eller påverkade enheten.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="f8ca5-167">En fråga kan till exempel returnera avsändarens ( `SenderFromAddress` eller `SenderMailFromAddress` ) och mottagarens ( ) `RecipientEmailAddress` adresser.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="f8ca5-168">Genom att identifiera vilka av dessa kolumner som representerar den viktigaste påverkade enheten bidrar tjänsten till att slå samman relevanta aviseringar, korrelera incidenter och målsvarsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="f8ca5-169">Du kan bara välja en kolumn för varje entitetstyp (postlåda, användare eller enhet).</span><span class="sxs-lookup"><span data-stu-id="f8ca5-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="f8ca5-170">Kolumner som inte returneras av frågan kan inte markeras.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="f8ca5-171">4. Ange åtgärder.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-171">4. Specify actions.</span></span>
<span data-ttu-id="f8ca5-172">Den anpassade identifieringsregeln kan automatiskt vidta åtgärder på enheter, filer eller användare som returneras av frågan.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="f8ca5-173">Åtgärder på enheter</span><span class="sxs-lookup"><span data-stu-id="f8ca5-173">Actions on devices</span></span>
<span data-ttu-id="f8ca5-174">Dessa åtgärder tillämpas på enheter i `DeviceId` kolumnen med frågeresultat:</span><span class="sxs-lookup"><span data-stu-id="f8ca5-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="f8ca5-175">**Isolera enhet**– använder Microsoft Defender för Endpoint för att tillämpa fullständig nätverksisolering, vilket hindrar enheten från att ansluta till något program eller en tjänst.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-175">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="f8ca5-176">Läs mer om Microsoft Defender för Endpoint-datorisolering</span><span class="sxs-lookup"><span data-stu-id="f8ca5-176">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="f8ca5-177">Samla in **undersökningspaket**– samlar in enhetsinformation i en ZIP-fil.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-177">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="f8ca5-178">Läs mer om Microsoft Defender för undersökningspaketet för slutpunkt</span><span class="sxs-lookup"><span data-stu-id="f8ca5-178">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="f8ca5-179">**Kör antivirussökning**– utför en fullständig Windows Defender Antivirus-sökning på enheten</span><span class="sxs-lookup"><span data-stu-id="f8ca5-179">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="f8ca5-180">**Initiera undersökning**– initierar en [automatiserad undersökning](m365d-autoir.md) på enheten</span><span class="sxs-lookup"><span data-stu-id="f8ca5-180">**Initiate investigation**—initiates an [automated investigation](m365d-autoir.md) on the device</span></span>
- <span data-ttu-id="f8ca5-181">**Begränsa programkörning**– anger begränsningar på enheten så att endast filer som har signerats med ett Certifikat utfärdat av Microsoft kan köras.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-181">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="f8ca5-182">Läs mer om appbegränsningar med Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="f8ca5-182">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="f8ca5-183">Åtgärder för filer</span><span class="sxs-lookup"><span data-stu-id="f8ca5-183">Actions on files</span></span>
<span data-ttu-id="f8ca5-184">Med det här alternativet kan du välja att **tillämpa filåtgärden** Karantän för filer i `SHA1` , , eller kolumnen i `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` frågeresultatet.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="f8ca5-185">Den här åtgärden tar bort filen från dess aktuella plats och placerar en kopia i karantän.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="f8ca5-186">Åtgärder för användare</span><span class="sxs-lookup"><span data-stu-id="f8ca5-186">Actions on users</span></span>
<span data-ttu-id="f8ca5-187">Med det här alternativet **vidtas åtgärden Markera** användare som komprometterad på användare i , eller i kolumnen för `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` frågeresultatet.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="f8ca5-188">Med den här åtgärden ställs användarnas risknivå in på "hög" i Azure Active Directory, vilket utlöser motsvarande [identitetsskyddsprinciper.](/azure/active-directory/identity-protection/overview-identity-protection)</span><span class="sxs-lookup"><span data-stu-id="f8ca5-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="f8ca5-189">Åtgärden tillåt eller blockera för anpassade identifieringsregler stöds för närvarande inte i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-189">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="f8ca5-190">5. Ange regelns omfattning.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-190">5. Set the rule scope.</span></span>
<span data-ttu-id="f8ca5-191">Ange omfattningen för att ange vilka enheter som omfattas av regeln.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="f8ca5-192">Omfattningen påverkar regler som kontrollerar enheter och påverkar inte regler som bara kontrollerar postlådor och användarkonton eller identiteter.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="f8ca5-193">När du anger omfattningen kan du välja:</span><span class="sxs-lookup"><span data-stu-id="f8ca5-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="f8ca5-194">Alla enheter</span><span class="sxs-lookup"><span data-stu-id="f8ca5-194">All devices</span></span>
- <span data-ttu-id="f8ca5-195">Specifika enhetsgrupper</span><span class="sxs-lookup"><span data-stu-id="f8ca5-195">Specific device groups</span></span>

<span data-ttu-id="f8ca5-196">Endast data från enheter i omfattningen kommer att tillfrågas.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="f8ca5-197">Dessutom kommer åtgärder endast att vidtas på de enheterna.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="f8ca5-198">6. Granska och aktivera regeln.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="f8ca5-199">När du har granskat regeln väljer du **Skapa för** att spara den.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="f8ca5-200">Regeln för anpassad identifiering körs direkt.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="f8ca5-201">Den körs igen baserat på konfigurerad frekvens för att söka efter matchningar, generera aviseringar och vidta svarsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>


>[!Important] 
><span data-ttu-id="f8ca5-202">Anpassade identifieringar bör regelbundet granskas av effektivitet och effektivitet.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-202">Custom detections should be regularly reviewed for efficiency and effectiveness.</span></span> <span data-ttu-id="f8ca5-203">Om du vill vara säker på att du skapar identifieringar som utlöser sanna aviseringar tar det tid att granska dina befintliga anpassade identifieringar genom att följa stegen i Hantera [befintliga anpassade identifieringsregler.](#manage-existing-custom-detection-rules)</span><span class="sxs-lookup"><span data-stu-id="f8ca5-203">To make sure you are creating detections that trigger true alerts, take time to review your existing custom detections by following the steps in [Manage existing custom detection rules](#manage-existing-custom-detection-rules).</span></span> <br>  
<span data-ttu-id="f8ca5-204">Du behåller kontrollen över hur omfattande eller specifika dina anpassade identifieringar är, så falska varningar som genereras av anpassade identifieringar kan ange ett behov av att ändra vissa parametrar för reglerna.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-204">You maintain control over the broadness or specificity of your custom detections so any false alerts generated by custom detections might indicate a need to modify certain parameters of the rules.</span></span>


## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="f8ca5-205">Hantera befintliga anpassade identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="f8ca5-205">Manage existing custom detection rules</span></span>
<span data-ttu-id="f8ca5-206">Du kan visa listan över befintliga anpassade identifieringsregler, kontrollera deras tidigare körningar och granska de aviseringar som de har utlöst.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-206">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="f8ca5-207">Du kan även köra en regel på begäran och ändra den.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-207">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="f8ca5-208">Visa befintliga regler</span><span class="sxs-lookup"><span data-stu-id="f8ca5-208">View existing rules</span></span>

<span data-ttu-id="f8ca5-209">Om du vill visa alla befintliga anpassade identifieringsregler går du **till Söka** efter  >  **anpassade identifieringar.**</span><span class="sxs-lookup"><span data-stu-id="f8ca5-209">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="f8ca5-210">På sidan visas alla regler med följande körningsinformation:</span><span class="sxs-lookup"><span data-stu-id="f8ca5-210">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="f8ca5-211">**Senaste körningen**– när en regel senast körts för att söka efter frågematchningar och generera aviseringar</span><span class="sxs-lookup"><span data-stu-id="f8ca5-211">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="f8ca5-212">**Status för senaste körningen**– om en regel kördes som den ska</span><span class="sxs-lookup"><span data-stu-id="f8ca5-212">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="f8ca5-213">**Nästa körning**– nästa schemalagda körning</span><span class="sxs-lookup"><span data-stu-id="f8ca5-213">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="f8ca5-214">**Status**– om en regel har aktiverats eller inaktiverats</span><span class="sxs-lookup"><span data-stu-id="f8ca5-214">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="f8ca5-215">Visa regeldetaljer, ändra regel och köra regel</span><span class="sxs-lookup"><span data-stu-id="f8ca5-215">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="f8ca5-216">Om du vill visa omfattande information om en anpassad identifieringsregel **går** du till  >  Anpassade identifieringar av **visning** och väljer namnet på regeln.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-216">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="f8ca5-217">Du kan sedan visa allmän information om regeln, inklusive information om dess körningsstatus och omfattning.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-217">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="f8ca5-218">Sidan innehåller också en lista över utlösande aviseringar och åtgärder.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-218">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="f8ca5-219">![Sidan Information om anpassade identifieringsregel](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="f8ca5-219">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="f8ca5-220">*Information om anpassade identifieringsregel*</span><span class="sxs-lookup"><span data-stu-id="f8ca5-220">*Custom detection rule details*</span></span>

<span data-ttu-id="f8ca5-221">Du kan också utföra följande åtgärder på regeln från den här sidan:</span><span class="sxs-lookup"><span data-stu-id="f8ca5-221">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="f8ca5-222">**Kör**– kör regeln direkt.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-222">**Run**—run the rule immediately.</span></span> <span data-ttu-id="f8ca5-223">Då återställs också intervallet för nästa körning.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-223">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="f8ca5-224">**Redigera**– ändra regeln utan att ändra frågan</span><span class="sxs-lookup"><span data-stu-id="f8ca5-224">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="f8ca5-225">**Ändra fråga**– redigera frågan under avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="f8ca5-225">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="f8ca5-226">**Aktivera**  /  **Inaktivera –** aktivera regeln eller hindra den från att köras</span><span class="sxs-lookup"><span data-stu-id="f8ca5-226">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="f8ca5-227">**Ta** bort – inaktivera regeln och ta bort den</span><span class="sxs-lookup"><span data-stu-id="f8ca5-227">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="f8ca5-228">Visa och hantera utlösande aviseringar</span><span class="sxs-lookup"><span data-stu-id="f8ca5-228">View and manage triggered alerts</span></span>

<span data-ttu-id="f8ca5-229">På skärmen med regeldetaljer (**Anpassad** identifiering av uppgifter  >    >  **[Regelnamn]**) går du till Utlösade aviseringar, som visar de aviseringar som genererats av matchningar mot regeln.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-229">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="f8ca5-230">Välj en avisering om du vill visa detaljerad information om den och utföra följande åtgärder:</span><span class="sxs-lookup"><span data-stu-id="f8ca5-230">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="f8ca5-231">Hantera aviseringen genom att ange dess status och klassificering (sant eller falskt meddelande)</span><span class="sxs-lookup"><span data-stu-id="f8ca5-231">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="f8ca5-232">Länka aviseringen till en händelse</span><span class="sxs-lookup"><span data-stu-id="f8ca5-232">Link the alert to an incident</span></span>
- <span data-ttu-id="f8ca5-233">Kör frågan som utlöste varningen vid avancerad sökning</span><span class="sxs-lookup"><span data-stu-id="f8ca5-233">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="f8ca5-234">Granska åtgärder</span><span class="sxs-lookup"><span data-stu-id="f8ca5-234">Review actions</span></span>
<span data-ttu-id="f8ca5-235">På skärmen med regeldetaljer **(** Anpassade identifieringar av uppgifter  >    >  **[Regelnamn] )** går du till Utlösade åtgärder, där de åtgärder som vidtas baserat på matchningar mot regeln visas.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-235">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="f8ca5-236">Om du snabbt vill visa information och vidta åtgärder för ett objekt i en tabell använder du urvalskolumnen [&#10003;] till vänster om tabellen.</span><span class="sxs-lookup"><span data-stu-id="f8ca5-236">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8ca5-237">Se även</span><span class="sxs-lookup"><span data-stu-id="f8ca5-237">See also</span></span>
- [<span data-ttu-id="f8ca5-238">Översikt över anpassade identifieringar</span><span class="sxs-lookup"><span data-stu-id="f8ca5-238">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="f8ca5-239">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="f8ca5-239">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f8ca5-240">Lär dig språket för avancerad fråga om sökning</span><span class="sxs-lookup"><span data-stu-id="f8ca5-240">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f8ca5-241">Migrera avancerade frågor om sökning från Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f8ca5-241">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
