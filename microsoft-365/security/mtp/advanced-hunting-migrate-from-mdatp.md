---
title: Migrera avancerade sökfrågor från Microsoft Defender för Slutpunkt
description: Läs om hur du justerar frågor för Microsoft Defender för slutpunkt så att du kan använda dem i Microsoft 365 Defender
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, microsoft threat protection, microsoft 365, mtp, m365, microsoft defender atp, mdatp, sökning, fråga, telemetri, anpassade identifieringar, schema, kusto, microsoft 365, mappning
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 521b5fc2a8efee83b6a2931e7dbc1c713bd63cd2
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094813"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="8d58d-104">Migrera avancerade sökfrågor från Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="8d58d-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8d58d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="8d58d-105">**Applies to:**</span></span>
- <span data-ttu-id="8d58d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d58d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8d58d-107">Flytta dina avancerade arbetsflöden för sökning från Microsoft Defender för Endpoint till att proaktivt leta efter hot med en bredare uppsättning data.</span><span class="sxs-lookup"><span data-stu-id="8d58d-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="8d58d-108">I Microsoft 365 Defender får du åtkomst till data från andra säkerhetslösningar för Microsoft 365, bland annat:</span><span class="sxs-lookup"><span data-stu-id="8d58d-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="8d58d-109">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="8d58d-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="8d58d-110">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="8d58d-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="8d58d-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8d58d-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="8d58d-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="8d58d-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="8d58d-113">De flesta Microsoft Defender för slutpunktskunder [kan använda Microsoft 365 Defender utan ytterligare licenser.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="8d58d-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="8d58d-114">Om du vill börja gå över dina avancerade arbetsflöden för sökning från Defender för Endpoint aktiverar du [Microsoft 365 Defender.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="8d58d-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="8d58d-115">Du kan gå över utan att påverka dina befintliga Defender för slutpunktsarbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="8d58d-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="8d58d-116">Sparade frågor förblir intakta, och anpassade identifieringsregler fortsätter att köra och generera aviseringar.</span><span class="sxs-lookup"><span data-stu-id="8d58d-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="8d58d-117">De visas däremot i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8d58d-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="8d58d-118">Schematabeller endast i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d58d-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="8d58d-119">I [det avancerade sökschemat i Microsoft 365 Defender finns](advanced-hunting-schema-tables.md) fler tabeller som innehåller data från olika säkerhetslösningar från Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8d58d-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="8d58d-120">Följande tabeller är endast tillgängliga i Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="8d58d-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="8d58d-121">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="8d58d-121">Table name</span></span> | <span data-ttu-id="8d58d-122">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="8d58d-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="8d58d-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="8d58d-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="8d58d-124">Filer, IP-adresser, URL:er, användare eller enheter som är associerade med aviseringar</span><span class="sxs-lookup"><span data-stu-id="8d58d-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="8d58d-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="8d58d-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="8d58d-126">Varningar från Microsoft Defender för Slutpunkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet, inklusive information om allvarlighetsgrad och hotkategorier</span><span class="sxs-lookup"><span data-stu-id="8d58d-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="8d58d-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="8d58d-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="8d58d-128">Filrelaterade aktiviteter i molnappar och -tjänster</span><span class="sxs-lookup"><span data-stu-id="8d58d-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="8d58d-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="8d58d-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="8d58d-130">Information om bifogade filer i e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="8d58d-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="8d58d-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="8d58d-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="8d58d-132">E-posthändelser i Microsoft 365, inklusive e-postleverans och blockeringshändelser</span><span class="sxs-lookup"><span data-stu-id="8d58d-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="8d58d-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="8d58d-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="8d58d-134">Säkerhetshändelser som inträffar efter leverans, när Microsoft 365 har levererat e-postmeddelandena till mottagarens postlåda</span><span class="sxs-lookup"><span data-stu-id="8d58d-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="8d58d-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="8d58d-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="8d58d-136">Information om URL:er för e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="8d58d-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="8d58d-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="8d58d-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="8d58d-138">Händelser som innefattar en lokal domänkontrollant som kör Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="8d58d-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="8d58d-139">Den här tabellen omfattar ett antal identitetsrelaterade händelser och systemhändelser på domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="8d58d-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="8d58d-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="8d58d-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="8d58d-141">Kontoinformation från olika källor, bland annat Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="8d58d-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="8d58d-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="8d58d-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="8d58d-143">Autentiseringshändelser i Active Directory och Microsofts onlinetjänster</span><span class="sxs-lookup"><span data-stu-id="8d58d-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="8d58d-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="8d58d-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="8d58d-145">Frågor för Active Directory-objekt, till exempel användare, grupper, enheter och domäner</span><span class="sxs-lookup"><span data-stu-id="8d58d-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="8d58d-146">Map DeviceAlertEvents-tabell</span><span class="sxs-lookup"><span data-stu-id="8d58d-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="8d58d-147">Tabellerna `AlertInfo` `AlertEvidence` ersätter tabellen `DeviceAlertEvents` i Microsoft Defender för Endpoint-schemat.</span><span class="sxs-lookup"><span data-stu-id="8d58d-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="8d58d-148">Utöver data om enhetsaviseringar innehåller dessa två tabeller data om aviseringar om identiteter, appar och e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="8d58d-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="8d58d-149">Använd följande tabell för att kontrollera hur `DeviceAlertEvents` kolumner mappar till kolumner i `AlertInfo` och `AlertEvidence` tabeller.</span><span class="sxs-lookup"><span data-stu-id="8d58d-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="8d58d-150">Utöver kolumnerna i tabellen nedan innehåller tabellen många andra kolumner som ger en mer övergripande bild `AlertEvidence` av aviseringar från olika källor.</span><span class="sxs-lookup"><span data-stu-id="8d58d-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="8d58d-151">Visa alla kolumner med Aviseringsvidens</span><span class="sxs-lookup"><span data-stu-id="8d58d-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="8d58d-152">DeviceAlertEvents-kolumn</span><span class="sxs-lookup"><span data-stu-id="8d58d-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="8d58d-153">Så här hittar du samma data i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d58d-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="8d58d-154">`AlertInfo` och  `AlertEvidence` tabeller</span><span class="sxs-lookup"><span data-stu-id="8d58d-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="8d58d-155">`AlertInfo` och  `AlertEvidence` tabeller</span><span class="sxs-lookup"><span data-stu-id="8d58d-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="8d58d-156">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="8d58d-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="8d58d-157">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="8d58d-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="8d58d-158">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="8d58d-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="8d58d-159">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="8d58d-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="8d58d-160">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="8d58d-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="8d58d-161">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="8d58d-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="8d58d-162">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="8d58d-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="8d58d-163">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="8d58d-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="8d58d-164">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="8d58d-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="8d58d-165">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="8d58d-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="8d58d-166">Den här kolumnen används vanligtvis i Microsoft Defender för Slutpunkt för att hitta relaterade poster i andra tabeller.</span><span class="sxs-lookup"><span data-stu-id="8d58d-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="8d58d-167">I Microsoft 365 Defender kan du hämta relaterade data direkt från `AlertEvidence` tabellen.</span><span class="sxs-lookup"><span data-stu-id="8d58d-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="8d58d-168">Den här kolumnen används vanligtvis i Microsoft Defender för Slutpunkt för ytterligare händelseinformation i andra tabeller.</span><span class="sxs-lookup"><span data-stu-id="8d58d-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="8d58d-169">I Microsoft 365 Defender kan du hämta relaterade data direkt från `AlertEvidence` tabellen.</span><span class="sxs-lookup"><span data-stu-id="8d58d-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="8d58d-170">Justera befintliga Microsoft Defender för slutpunktsfrågor</span><span class="sxs-lookup"><span data-stu-id="8d58d-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="8d58d-171">Microsoft Defender för slutpunktsfrågor fungerar som de är om de inte refererar till `DeviceAlertEvents` tabellen.</span><span class="sxs-lookup"><span data-stu-id="8d58d-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="8d58d-172">Använd de här ändringarna om du vill använda dessa frågor i Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="8d58d-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="8d58d-173">Ersätt `DeviceAlertEvents` med `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="8d58d-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="8d58d-174">Sammanfoga `AlertInfo` tabellerna och `AlertEvidence` koppla dem för att få motsvarande `AlertId` data.</span><span class="sxs-lookup"><span data-stu-id="8d58d-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="8d58d-175">Ursprunglig fråga</span><span class="sxs-lookup"><span data-stu-id="8d58d-175">Original query</span></span>
<span data-ttu-id="8d58d-176">Följande fråga använder i `DeviceAlertEvents` Microsoft Defender för Slutpunkt för att få aviseringar som innebär att _powershell.exe:_</span><span class="sxs-lookup"><span data-stu-id="8d58d-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="8d58d-177">Ändrad fråga</span><span class="sxs-lookup"><span data-stu-id="8d58d-177">Modified query</span></span>
<span data-ttu-id="8d58d-178">Följande fråga har justerats för användning i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8d58d-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="8d58d-179">I stället för att kontrollera filnamnet `DeviceAlertEvents` direkt från, sammanfogas `AlertEvidence` det och söker efter filnamnet i tabellen.</span><span class="sxs-lookup"><span data-stu-id="8d58d-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```



## <a name="see-also"></a><span data-ttu-id="8d58d-180">Se även</span><span class="sxs-lookup"><span data-stu-id="8d58d-180">See also</span></span>
- [<span data-ttu-id="8d58d-181">Aktivera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8d58d-181">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="8d58d-182">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="8d58d-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="8d58d-183">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="8d58d-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="8d58d-184">Avancerad sökning i Microsoft Defender för Slutpunkt</span><span class="sxs-lookup"><span data-stu-id="8d58d-184">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)