---
title: Migrera avancerade frågor om sökning från Microsoft Defender för Endpoint
description: Läs om hur du justerar dina Frågor om Microsoft Defender för slutpunkt så att du kan använda dem i Microsoft 365 Defender
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, Microsoft Defender for Endpoint, search, query, telemetry, custom detections, schema, kusto, mapping
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ba6f84f9f08d0635dab6ac65eaa697b8e0e73df7
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470694"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="48d16-104">Migrera avancerade frågor om sökning från Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="48d16-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="48d16-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="48d16-105">**Applies to:**</span></span>
- <span data-ttu-id="48d16-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48d16-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="48d16-107">Flytta dina avancerade arbetsflöden för sökning från Microsoft Defender för Endpoint till att proaktivt leta efter hot med en bredare uppsättning data.</span><span class="sxs-lookup"><span data-stu-id="48d16-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="48d16-108">I Microsoft 365 Defender får du åtkomst till data från andra Microsoft 365 säkerhetslösningar, bland annat:</span><span class="sxs-lookup"><span data-stu-id="48d16-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="48d16-109">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="48d16-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="48d16-110">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="48d16-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="48d16-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="48d16-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="48d16-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="48d16-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="48d16-113">De flesta Microsoft Defender för slutpunktskunder [kan använda Microsoft 365 Defender utan ytterligare licenser.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="48d16-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="48d16-114">Om du vill börja gå över dina avancerade arbetsflöden för sökning från Defender för Slutpunkt [aktiverar du Microsoft 365 Defender.](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="48d16-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

<span data-ttu-id="48d16-115">Du kan gå över utan att påverka dina befintliga Defender för slutpunktsarbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="48d16-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="48d16-116">Sparade frågor förblir intakta, och anpassade identifieringsregler fortsätter att köras och generera aviseringar.</span><span class="sxs-lookup"><span data-stu-id="48d16-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="48d16-117">De kommer dock att visas i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="48d16-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="48d16-118">Schematabeller i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48d16-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="48d16-119">I [Microsoft 365 defender avancerade sökschema finns](advanced-hunting-schema-tables.md) ytterligare tabeller som innehåller data från olika Microsoft 365 säkerhetslösningar.</span><span class="sxs-lookup"><span data-stu-id="48d16-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="48d16-120">Följande tabeller är endast tillgängliga i Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="48d16-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="48d16-121">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="48d16-121">Table name</span></span> | <span data-ttu-id="48d16-122">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="48d16-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="48d16-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="48d16-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="48d16-124">Filer, IP-adresser, URL:er, användare eller enheter som associeras med aviseringar</span><span class="sxs-lookup"><span data-stu-id="48d16-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="48d16-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="48d16-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="48d16-126">Varningar från Microsoft Defender för Slutpunkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet, inklusive information om allvarlighetsgrad och hotkategorier</span><span class="sxs-lookup"><span data-stu-id="48d16-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="48d16-127">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="48d16-127">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="48d16-128">Information om bifogade filer i e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="48d16-128">Information about files attached to emails</span></span> |
| [<span data-ttu-id="48d16-129">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="48d16-129">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="48d16-130">Microsoft 365 e-posthändelser, inklusive e-postleverans och blockeringshändelser</span><span class="sxs-lookup"><span data-stu-id="48d16-130">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="48d16-131">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="48d16-131">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="48d16-132">Säkerhetshändelser som inträffar efter leveransen, Microsoft 365 e-postmeddelanden har levererats till mottagarens postlåda</span><span class="sxs-lookup"><span data-stu-id="48d16-132">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="48d16-133">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="48d16-133">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="48d16-134">Information om URL:er för e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="48d16-134">Information about URLs on emails</span></span> |
| [<span data-ttu-id="48d16-135">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="48d16-135">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="48d16-136">Händelser som innefattar en lokal domänkontrollant som kör Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="48d16-136">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="48d16-137">Den här tabellen omfattar ett antal identitetsrelaterade händelser och systemhändelser på domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="48d16-137">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="48d16-138">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="48d16-138">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="48d16-139">Kontoinformation från olika källor, bland annat Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="48d16-139">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="48d16-140">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="48d16-140">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="48d16-141">Autentiseringshändelser i Active Directory och Microsoft-onlinetjänster</span><span class="sxs-lookup"><span data-stu-id="48d16-141">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="48d16-142">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="48d16-142">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="48d16-143">Frågor för Active Directory-objekt, till exempel användare, grupper, enheter och domäner</span><span class="sxs-lookup"><span data-stu-id="48d16-143">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

>[!IMPORTANT]
> <span data-ttu-id="48d16-144">Frågor och anpassade identifieringar som använder schematabeller som bara är tillgängliga i Microsoft 365 Defender kan endast visas i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="48d16-144">Queries and custom detections which use schema tables that are only available in Microsoft 365 Defender can only be viewed in Microsoft 365 Defender.</span></span>

## <a name="map-devicealertevents-table"></a><span data-ttu-id="48d16-145">Karta DeviceAlertEvents-tabell</span><span class="sxs-lookup"><span data-stu-id="48d16-145">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="48d16-146">Tabellerna `AlertInfo` `AlertEvidence` och ersätter tabellen i Microsoft Defender `DeviceAlertEvents` för Endpoint-schemat.</span><span class="sxs-lookup"><span data-stu-id="48d16-146">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="48d16-147">Utöver data om enhetsaviseringar innehåller de här två tabellerna data om aviseringar om identiteter, appar och e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="48d16-147">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="48d16-148">Använd följande tabell för att kontrollera hur `DeviceAlertEvents` kolumner mapps till kolumner i `AlertInfo` `AlertEvidence` tabellerna.</span><span class="sxs-lookup"><span data-stu-id="48d16-148">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="48d16-149">Utöver kolumnerna i tabellen nedan innehåller tabellen många andra kolumner som ger en mer holistisk bild `AlertEvidence` av aviseringar från olika källor.</span><span class="sxs-lookup"><span data-stu-id="48d16-149">In addition to the columns in the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="48d16-150">Visa alla kolumner för AviseringVidens</span><span class="sxs-lookup"><span data-stu-id="48d16-150">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="48d16-151">DeviceAlertEvents-kolumn</span><span class="sxs-lookup"><span data-stu-id="48d16-151">DeviceAlertEvents column</span></span> | <span data-ttu-id="48d16-152">Här hittar du samma data i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48d16-152">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="48d16-153">`AlertInfo` och  `AlertEvidence` tabeller</span><span class="sxs-lookup"><span data-stu-id="48d16-153">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="48d16-154">`AlertInfo` och  `AlertEvidence` tabeller</span><span class="sxs-lookup"><span data-stu-id="48d16-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="48d16-155">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="48d16-155">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="48d16-156">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="48d16-156">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="48d16-157">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="48d16-157">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="48d16-158">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="48d16-158">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="48d16-159">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="48d16-159">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="48d16-160">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="48d16-160">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="48d16-161">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="48d16-161">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="48d16-162">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="48d16-162">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="48d16-163">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="48d16-163">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="48d16-164">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="48d16-164">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="48d16-165">Den här kolumnen används vanligtvis i Microsoft Defender för Slutpunkt för att hitta relaterade poster i andra tabeller.</span><span class="sxs-lookup"><span data-stu-id="48d16-165">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="48d16-166">I Microsoft 365 Defender kan du hämta relaterade data direkt från `AlertEvidence` tabellen.</span><span class="sxs-lookup"><span data-stu-id="48d16-166">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="48d16-167">Den här kolumnen används vanligtvis i Microsoft Defender för Slutpunkt för ytterligare händelseinformation i andra tabeller.</span><span class="sxs-lookup"><span data-stu-id="48d16-167">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="48d16-168">I Microsoft 365 Defender kan du hämta relaterade data direkt från `AlertEvidence` tabellen.</span><span class="sxs-lookup"><span data-stu-id="48d16-168">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="48d16-169">Justera befintliga Microsoft Defender för slutpunktsfrågor</span><span class="sxs-lookup"><span data-stu-id="48d16-169">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="48d16-170">Microsoft Defender för slutpunktsfrågor fungerar som de är såvida de inte refererar till `DeviceAlertEvents` tabellen.</span><span class="sxs-lookup"><span data-stu-id="48d16-170">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="48d16-171">Om du vill använda dessa frågor i Microsoft 365 Defender gör du följande ändringar:</span><span class="sxs-lookup"><span data-stu-id="48d16-171">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="48d16-172">Ersätt `DeviceAlertEvents` med `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="48d16-172">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="48d16-173">Sammanfoga och `AlertInfo` `AlertEvidence` tabellerna för att `AlertId` få motsvarande data.</span><span class="sxs-lookup"><span data-stu-id="48d16-173">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="48d16-174">Ursprunglig fråga</span><span class="sxs-lookup"><span data-stu-id="48d16-174">Original query</span></span>
<span data-ttu-id="48d16-175">Följande fråga använder i `DeviceAlertEvents` Microsoft Defender för Slutpunkt för att få aviseringar som involverar _powershell.exe:_</span><span class="sxs-lookup"><span data-stu-id="48d16-175">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="48d16-176">Ändrad fråga</span><span class="sxs-lookup"><span data-stu-id="48d16-176">Modified query</span></span>
<span data-ttu-id="48d16-177">Följande fråga har justerats för användning i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="48d16-177">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="48d16-178">I stället för att kontrollera filnamnet direkt `DeviceAlertEvents` från , ansluts `AlertEvidence` filen och söker efter filnamnet i tabellen.</span><span class="sxs-lookup"><span data-stu-id="48d16-178">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="48d16-179">Migrera anpassade identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="48d16-179">Migrate custom detection rules</span></span>

<span data-ttu-id="48d16-180">När Microsoft Defender för slutpunktsregler redigeras i Microsoft 365 Defender fortsätter de att fungera som förut om den resulterande frågan endast tittar på enhetstabeller.</span><span class="sxs-lookup"><span data-stu-id="48d16-180">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> 

<span data-ttu-id="48d16-181">Till exempel kommer aviseringar som genereras av anpassade identifieringsregler som endast gäller enhetstabeller att fortsätta levereras till SIEM och generera e-postaviseringar, beroende på hur du har konfigurerat dessa i Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="48d16-181">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="48d16-182">Befintliga regelregler i Defender för Endpoint fortsätter också att gälla.</span><span class="sxs-lookup"><span data-stu-id="48d16-182">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="48d16-183">När du redigerar en Defender för slutpunktsregel så att den frågar om identitets- och e-posttabeller, som bara är tillgängliga i Microsoft 365 Defender, flyttas regeln automatiskt till Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="48d16-183">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="48d16-184">Varningar som genereras av den migrerade regeln:</span><span class="sxs-lookup"><span data-stu-id="48d16-184">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="48d16-185">Visas inte längre i Defender för Slutpunktsportalen (Microsoft Defender Säkerhetscenter)</span><span class="sxs-lookup"><span data-stu-id="48d16-185">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="48d16-186">Sluta levereras till din SIEM eller generera e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="48d16-186">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="48d16-187">Du kan komma runt den här ändringen genom att konfigurera Microsoft 365 Defender för att få aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="48d16-187">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="48d16-188">Du kan använda Defender [API Microsoft 365 få](api-incident.md) aviseringar om aviseringar för identifiering av kunder eller relaterade incidenter.</span><span class="sxs-lookup"><span data-stu-id="48d16-188">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="48d16-189">Kommer inte att döljas av Microsoft Defender för slutpunktsreglerna.</span><span class="sxs-lookup"><span data-stu-id="48d16-189">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="48d16-190">För att förhindra att aviseringar skapas för vissa användare, enheter eller postlådor ändrar du motsvarande frågor för att uttryckligen utesluta dessa enheter.</span><span class="sxs-lookup"><span data-stu-id="48d16-190">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="48d16-191">Om du redigerar en regel på det här sättet uppmanas du att bekräfta ändringarna innan de tillämpas.</span><span class="sxs-lookup"><span data-stu-id="48d16-191">If you edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="48d16-192">Nya aviseringar som genereras av anpassade identifieringsregler i Microsoft 365 Defender-portalen visas på en aviseringssida med följande information:</span><span class="sxs-lookup"><span data-stu-id="48d16-192">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="48d16-193">Aviseringstitel och beskrivning</span><span class="sxs-lookup"><span data-stu-id="48d16-193">Alert title and description</span></span> 
- <span data-ttu-id="48d16-194">Påverkade tillgångar</span><span class="sxs-lookup"><span data-stu-id="48d16-194">Impacted assets</span></span>
- <span data-ttu-id="48d16-195">Åtgärder som vidtas som svar på aviseringen</span><span class="sxs-lookup"><span data-stu-id="48d16-195">Actions taken in response to the alert</span></span>
- <span data-ttu-id="48d16-196">Frågeresultat som utlöste aviseringen</span><span class="sxs-lookup"><span data-stu-id="48d16-196">Query results that triggered the alert</span></span> 
- <span data-ttu-id="48d16-197">Information om den anpassade identifieringsregeln</span><span class="sxs-lookup"><span data-stu-id="48d16-197">Information on the custom detection rule</span></span> 
 
> [!div class="mx-imgBorder"]
> <span data-ttu-id="48d16-198">![Bild på ny aviseringssida](../../media/new-alert-page.png)</span><span class="sxs-lookup"><span data-stu-id="48d16-198">![Image of new alert page](../../media/new-alert-page.png)</span></span>

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="48d16-199">Skriv frågor utan DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="48d16-199">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="48d16-200">I Microsoft 365 Defender-schemat finns tabeller och den diverse uppsättningen information som medföljer `AlertInfo` `AlertEvidence` aviseringar från olika källor.</span><span class="sxs-lookup"><span data-stu-id="48d16-200">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="48d16-201">Om du vill ha samma aviseringsinformation som du fick från tabellen i Microsoft Defender för Endpoint-schemat filtrerar du tabellen efter och sammanar sedan varje unikt ID med tabellen, som ger detaljerad information om händelser och `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` enheter.</span><span class="sxs-lookup"><span data-stu-id="48d16-201">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="48d16-202">Se exempelfrågan nedan:</span><span class="sxs-lookup"><span data-stu-id="48d16-202">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="48d16-203">Den här frågan ger många fler kolumner än `DeviceAlertEvents` i Microsoft Defender för Endpoint-schemat.</span><span class="sxs-lookup"><span data-stu-id="48d16-203">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="48d16-204">Använd bara kolumnerna du är `project` intresserad av för att hålla resultaten hanterbara.</span><span class="sxs-lookup"><span data-stu-id="48d16-204">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="48d16-205">I exemplet nedan visas kolumner för projekt som du kan vara intresserad av när undersökningen upptäckte PowerShell-aktivitet:</span><span class="sxs-lookup"><span data-stu-id="48d16-205">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="48d16-206">Om du vill filtrera efter specifika enheter som är inblandade i aviseringarna kan du göra det genom att ange enhetstypen i och det värde du vill `EntityType` filtrera efter.</span><span class="sxs-lookup"><span data-stu-id="48d16-206">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="48d16-207">Följande exempel söker efter en specifik IP-adress:</span><span class="sxs-lookup"><span data-stu-id="48d16-207">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="48d16-208">Se även</span><span class="sxs-lookup"><span data-stu-id="48d16-208">See also</span></span>
- [<span data-ttu-id="48d16-209">Aktivera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48d16-209">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="48d16-210">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="48d16-210">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="48d16-211">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="48d16-211">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="48d16-212">Avancerad sökning i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="48d16-212">Advanced hunting in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)