---
title: Migrera avancerade frågor om sökning från Microsoft Defender för Endpoint
description: Läs om hur du justerar dina Frågor om Microsoft Defender för slutpunkt så att du kan använda dem i Microsoft 365 Defender
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, microsoft defender atp, mdatp, search, query, telemetry, custom detections, schema, kusto, microsoft 365, mapping
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: c0575b5eaf5a4683f86d4a48dd1076fa2c423acf
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076353"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="f88ab-104">Migrera avancerade frågor om sökning från Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f88ab-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f88ab-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f88ab-105">**Applies to:**</span></span>
- <span data-ttu-id="f88ab-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f88ab-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f88ab-107">Flytta dina avancerade arbetsflöden för sökning från Microsoft Defender för Endpoint till att proaktivt leta efter hot med en bredare uppsättning data.</span><span class="sxs-lookup"><span data-stu-id="f88ab-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="f88ab-108">I Microsoft 365 Defender får du åtkomst till data från andra Microsoft 365-säkerhetslösningar, bland annat:</span><span class="sxs-lookup"><span data-stu-id="f88ab-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="f88ab-109">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f88ab-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="f88ab-110">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="f88ab-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="f88ab-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f88ab-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="f88ab-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="f88ab-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="f88ab-113">De flesta Microsoft Defender för slutpunktskunder [kan använda Microsoft 365 Defender utan ytterligare licenser.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="f88ab-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="f88ab-114">Om du vill börja gå över dina avancerade arbetsflöden för sökning från Defender för Endpoint [aktiverar du Microsoft 365 Defender.](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="f88ab-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

<span data-ttu-id="f88ab-115">Du kan gå över utan att påverka dina befintliga Defender för slutpunktsarbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="f88ab-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="f88ab-116">Sparade frågor förblir intakta, och anpassade identifieringsregler fortsätter att köras och generera aviseringar.</span><span class="sxs-lookup"><span data-stu-id="f88ab-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="f88ab-117">De kommer dock att visas i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f88ab-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="f88ab-118">Schematabeller endast i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f88ab-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="f88ab-119">I [det avancerade sökschemat för Microsoft 365 Defender](advanced-hunting-schema-tables.md) finns ytterligare tabeller som innehåller data från olika säkerhetslösningar för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f88ab-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="f88ab-120">Följande tabeller är endast tillgängliga i Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="f88ab-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="f88ab-121">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="f88ab-121">Table name</span></span> | <span data-ttu-id="f88ab-122">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f88ab-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="f88ab-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="f88ab-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="f88ab-124">Filer, IP-adresser, URL:er, användare eller enheter som associeras med aviseringar</span><span class="sxs-lookup"><span data-stu-id="f88ab-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="f88ab-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="f88ab-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="f88ab-126">Varningar från Microsoft Defender för Slutpunkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet, inklusive information om allvarlighetsgrad och hotkategorier</span><span class="sxs-lookup"><span data-stu-id="f88ab-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="f88ab-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="f88ab-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="f88ab-128">Filrelaterade aktiviteter i molnappar och -tjänster</span><span class="sxs-lookup"><span data-stu-id="f88ab-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="f88ab-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="f88ab-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="f88ab-130">Information om bifogade filer i e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="f88ab-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="f88ab-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="f88ab-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="f88ab-132">E-posthändelser i Microsoft 365, inklusive e-postleverans och blockeringshändelser</span><span class="sxs-lookup"><span data-stu-id="f88ab-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="f88ab-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="f88ab-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="f88ab-134">Säkerhetshändelser som inträffar efter leverans, när Microsoft 365 har levererat e-postmeddelanden till mottagarens postlåda</span><span class="sxs-lookup"><span data-stu-id="f88ab-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="f88ab-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="f88ab-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="f88ab-136">Information om URL:er för e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="f88ab-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="f88ab-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="f88ab-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="f88ab-138">Händelser som innefattar en lokal domänkontrollant som kör Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="f88ab-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="f88ab-139">Den här tabellen omfattar ett antal identitetsrelaterade händelser och systemhändelser på domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="f88ab-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="f88ab-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="f88ab-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="f88ab-141">Kontoinformation från olika källor, inklusive Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f88ab-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="f88ab-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="f88ab-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="f88ab-143">Autentiseringshändelser i Active Directory och Microsoft-onlinetjänster</span><span class="sxs-lookup"><span data-stu-id="f88ab-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="f88ab-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="f88ab-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="f88ab-145">Frågor för Active Directory-objekt, till exempel användare, grupper, enheter och domäner</span><span class="sxs-lookup"><span data-stu-id="f88ab-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

>[!IMPORTANT]
> <span data-ttu-id="f88ab-146">Frågor och anpassade identifieringar som använder schematabeller som bara är tillgängliga i Microsoft 365 Defender kan endast visas i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f88ab-146">Queries and custom detections which use schema tables that are only available in Microsoft 365 Defender can only be viewed in Microsoft 365 Defender.</span></span>

## <a name="map-devicealertevents-table"></a><span data-ttu-id="f88ab-147">Karta DeviceAlertEvents-tabell</span><span class="sxs-lookup"><span data-stu-id="f88ab-147">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="f88ab-148">Tabellerna `AlertInfo` `AlertEvidence` och ersätter tabellen i Microsoft Defender `DeviceAlertEvents` för Endpoint-schemat.</span><span class="sxs-lookup"><span data-stu-id="f88ab-148">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="f88ab-149">Utöver data om enhetsaviseringar innehåller de här två tabellerna data om aviseringar om identiteter, appar och e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="f88ab-149">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="f88ab-150">Använd följande tabell för att kontrollera hur `DeviceAlertEvents` kolumner mapps till kolumner i `AlertInfo` `AlertEvidence` tabellerna.</span><span class="sxs-lookup"><span data-stu-id="f88ab-150">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="f88ab-151">Utöver kolumnerna i tabellen nedan innehåller tabellen många andra kolumner som ger en mer holistisk bild `AlertEvidence` av aviseringar från olika källor.</span><span class="sxs-lookup"><span data-stu-id="f88ab-151">In addition to the columns in the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="f88ab-152">Visa alla kolumner för AviseringVidens</span><span class="sxs-lookup"><span data-stu-id="f88ab-152">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="f88ab-153">DeviceAlertEvents-kolumn</span><span class="sxs-lookup"><span data-stu-id="f88ab-153">DeviceAlertEvents column</span></span> | <span data-ttu-id="f88ab-154">Här hittar du samma data i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f88ab-154">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="f88ab-155">`AlertInfo` och  `AlertEvidence` tabeller</span><span class="sxs-lookup"><span data-stu-id="f88ab-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="f88ab-156">`AlertInfo` och  `AlertEvidence` tabeller</span><span class="sxs-lookup"><span data-stu-id="f88ab-156">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="f88ab-157">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="f88ab-157">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="f88ab-158">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="f88ab-158">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="f88ab-159">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="f88ab-159">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="f88ab-160">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="f88ab-160">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="f88ab-161">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="f88ab-161">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="f88ab-162">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="f88ab-162">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="f88ab-163">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="f88ab-163">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="f88ab-164">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="f88ab-164">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="f88ab-165">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="f88ab-165">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="f88ab-166">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="f88ab-166">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="f88ab-167">Den här kolumnen används vanligtvis i Microsoft Defender för Slutpunkt för att hitta relaterade poster i andra tabeller.</span><span class="sxs-lookup"><span data-stu-id="f88ab-167">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="f88ab-168">I Microsoft 365 Defender kan du hämta relaterade data direkt från `AlertEvidence` tabellen.</span><span class="sxs-lookup"><span data-stu-id="f88ab-168">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="f88ab-169">Den här kolumnen används vanligtvis i Microsoft Defender för Slutpunkt för ytterligare händelseinformation i andra tabeller.</span><span class="sxs-lookup"><span data-stu-id="f88ab-169">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="f88ab-170">I Microsoft 365 Defender kan du hämta relaterade data direkt från `AlertEvidence` tabellen.</span><span class="sxs-lookup"><span data-stu-id="f88ab-170">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="f88ab-171">Justera befintliga Microsoft Defender för slutpunktsfrågor</span><span class="sxs-lookup"><span data-stu-id="f88ab-171">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="f88ab-172">Microsoft Defender för slutpunktsfrågor fungerar som de är såvida de inte refererar till `DeviceAlertEvents` tabellen.</span><span class="sxs-lookup"><span data-stu-id="f88ab-172">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="f88ab-173">Använd de här ändringarna om du vill använda dessa frågor i Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="f88ab-173">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="f88ab-174">Ersätt `DeviceAlertEvents` med `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="f88ab-174">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="f88ab-175">Sammanfoga och `AlertInfo` `AlertEvidence` tabellerna för att `AlertId` få motsvarande data.</span><span class="sxs-lookup"><span data-stu-id="f88ab-175">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="f88ab-176">Ursprunglig fråga</span><span class="sxs-lookup"><span data-stu-id="f88ab-176">Original query</span></span>
<span data-ttu-id="f88ab-177">Följande fråga använder i `DeviceAlertEvents` Microsoft Defender för Slutpunkt för att få aviseringar som involverar _powershell.exe:_</span><span class="sxs-lookup"><span data-stu-id="f88ab-177">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="f88ab-178">Ändrad fråga</span><span class="sxs-lookup"><span data-stu-id="f88ab-178">Modified query</span></span>
<span data-ttu-id="f88ab-179">Följande fråga har justerats för användning i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f88ab-179">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="f88ab-180">I stället för att kontrollera filnamnet direkt `DeviceAlertEvents` från , ansluts `AlertEvidence` filen och söker efter filnamnet i tabellen.</span><span class="sxs-lookup"><span data-stu-id="f88ab-180">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="f88ab-181">Migrera anpassade identifieringsregler</span><span class="sxs-lookup"><span data-stu-id="f88ab-181">Migrate custom detection rules</span></span>

<span data-ttu-id="f88ab-182">När Microsoft Defender för slutpunktsregler redigeras på Microsoft 365 Defender fortsätter de att fungera som förut om den resulterande frågan bara tittar på enhetstabeller.</span><span class="sxs-lookup"><span data-stu-id="f88ab-182">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> 

<span data-ttu-id="f88ab-183">Till exempel kommer aviseringar som genereras av anpassade identifieringsregler som endast gäller enhetstabeller att fortsätta levereras till SIEM och generera e-postaviseringar, beroende på hur du har konfigurerat dessa i Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="f88ab-183">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="f88ab-184">Befintliga regelregler i Defender för Endpoint fortsätter också att gälla.</span><span class="sxs-lookup"><span data-stu-id="f88ab-184">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="f88ab-185">När du redigerar en Defender för slutpunktsregel så att den frågar om identitets- och e-posttabeller, som bara är tillgängliga i Microsoft 365 Defender, flyttas regeln automatiskt till Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f88ab-185">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="f88ab-186">Varningar som genereras av den migrerade regeln:</span><span class="sxs-lookup"><span data-stu-id="f88ab-186">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="f88ab-187">Visas inte längre i Defender för Slutpunktsportalen (Microsoft Defender Säkerhetscenter)</span><span class="sxs-lookup"><span data-stu-id="f88ab-187">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="f88ab-188">Sluta levereras till din SIEM eller generera e-postaviseringar.</span><span class="sxs-lookup"><span data-stu-id="f88ab-188">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="f88ab-189">Du kan komma runt den här ändringen genom att konfigurera aviseringarna via Microsoft 365 Defender för att få aviseringarna.</span><span class="sxs-lookup"><span data-stu-id="f88ab-189">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="f88ab-190">Du kan använda [Microsoft 365 Defender API för](api-incident.md) att få aviseringar om aviseringar för identifiering av kunder eller relaterade incidenter.</span><span class="sxs-lookup"><span data-stu-id="f88ab-190">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="f88ab-191">Kommer inte att döljas av Microsoft Defender för slutpunktsreglerna.</span><span class="sxs-lookup"><span data-stu-id="f88ab-191">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="f88ab-192">För att förhindra att aviseringar skapas för vissa användare, enheter eller postlådor ändrar du motsvarande frågor för att uttryckligen utesluta dessa enheter.</span><span class="sxs-lookup"><span data-stu-id="f88ab-192">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="f88ab-193">Om du redigerar en regel på det här sättet uppmanas du att bekräfta ändringarna innan de tillämpas.</span><span class="sxs-lookup"><span data-stu-id="f88ab-193">If you edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="f88ab-194">Nya aviseringar som genereras av anpassade identifieringsregler i Microsoft 365 Defender-portalen visas på en aviseringssida med följande information:</span><span class="sxs-lookup"><span data-stu-id="f88ab-194">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="f88ab-195">Aviseringstitel och beskrivning</span><span class="sxs-lookup"><span data-stu-id="f88ab-195">Alert title and description</span></span> 
- <span data-ttu-id="f88ab-196">Påverkade tillgångar</span><span class="sxs-lookup"><span data-stu-id="f88ab-196">Impacted assets</span></span>
- <span data-ttu-id="f88ab-197">Åtgärder som vidtas som svar på aviseringen</span><span class="sxs-lookup"><span data-stu-id="f88ab-197">Actions taken in response to the alert</span></span>
- <span data-ttu-id="f88ab-198">Frågeresultat som utlöste aviseringen</span><span class="sxs-lookup"><span data-stu-id="f88ab-198">Query results that triggered the alert</span></span> 
- <span data-ttu-id="f88ab-199">Information om den anpassade identifieringsregeln</span><span class="sxs-lookup"><span data-stu-id="f88ab-199">Information on the custom detection rule</span></span> 
 
![Bild på ny aviseringssida](../../media/new-alert-page.png)

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="f88ab-201">Skriv frågor utan DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="f88ab-201">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="f88ab-202">I Microsoft 365 Defender-schemat finns tabellerna och dem för den diverse uppsättningen information som medföljer aviseringar `AlertInfo` `AlertEvidence` från olika källor.</span><span class="sxs-lookup"><span data-stu-id="f88ab-202">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="f88ab-203">Om du vill ha samma aviseringsinformation som du fick från tabellen i Microsoft Defender för Endpoint-schemat filtrerar du tabellen efter och sammanar sedan varje unikt ID med tabellen, som ger detaljerad information om händelser och `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` enheter.</span><span class="sxs-lookup"><span data-stu-id="f88ab-203">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="f88ab-204">Se exempelfrågan nedan:</span><span class="sxs-lookup"><span data-stu-id="f88ab-204">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="f88ab-205">Den här frågan ger många fler kolumner än `DeviceAlertEvents` i Microsoft Defender för Endpoint-schemat.</span><span class="sxs-lookup"><span data-stu-id="f88ab-205">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="f88ab-206">Använd bara kolumnerna du är `project` intresserad av för att hålla resultaten hanterbara.</span><span class="sxs-lookup"><span data-stu-id="f88ab-206">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="f88ab-207">I exemplet nedan visas kolumner för projekt som du kan vara intresserad av när undersökningen upptäckte PowerShell-aktivitet:</span><span class="sxs-lookup"><span data-stu-id="f88ab-207">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="f88ab-208">Om du vill filtrera efter specifika enheter som är inblandade i aviseringarna kan du göra det genom att ange enhetstypen i och det värde du vill `EntityType` filtrera efter.</span><span class="sxs-lookup"><span data-stu-id="f88ab-208">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="f88ab-209">Följande exempel söker efter en specifik IP-adress:</span><span class="sxs-lookup"><span data-stu-id="f88ab-209">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="f88ab-210">Se även</span><span class="sxs-lookup"><span data-stu-id="f88ab-210">See also</span></span>
- [<span data-ttu-id="f88ab-211">Aktivera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f88ab-211">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f88ab-212">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="f88ab-212">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f88ab-213">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="f88ab-213">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f88ab-214">Avancerad sökning i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="f88ab-214">Advanced hunting in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)