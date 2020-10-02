---
title: Migrera avancerade frågor från Microsoft Defender ATP
description: Lär dig hur du justerar dina Microsoft Defender ATP-frågor så att du kan använda dem i Microsoft Threat Protection
keywords: Avancerad jakt, Hot jakt, cyberterrorism Threat stöldskydd, Microsoft Threat Protection, Microsoft 365, MTP, m365, Microsoft Defender ATP, mdatp, Sök, fråga, telemetri, anpassade identifieringar, schema, kusto, Microsoft 365, mappning
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: daa89ebf39f8fc6d2110720f61b8d02c074fb484
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338752"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a><span data-ttu-id="65c22-104">Migrera avancerade frågor från Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="65c22-104">Migrate advanced hunting queries from Microsoft Defender ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="65c22-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="65c22-105">**Applies to:**</span></span>
- <span data-ttu-id="65c22-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="65c22-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="65c22-107">Flytta dina avancerade arbets flöden från Microsoft Defender ATP för att proaktivt använda en bredare uppsättning data.</span><span class="sxs-lookup"><span data-stu-id="65c22-107">Move your advanced hunting workflows from Microsoft Defender ATP to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="65c22-108">I Microsoft Threat Protection får du till gång till data från andra Microsoft 365-säkerhetslösningar, bland annat:</span><span class="sxs-lookup"><span data-stu-id="65c22-108">In Microsoft Threat Protection, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="65c22-109">Microsoft Defender Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="65c22-109">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="65c22-110">Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="65c22-110">Office 365 Advanced Threat Protection</span></span>
- <span data-ttu-id="65c22-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="65c22-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="65c22-112">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="65c22-112">Azure Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="65c22-113">De flesta Microsoft Defender ATP-kunder kan [använda Microsoft Threat Protection utan ytterligare licenser](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="65c22-113">Most Microsoft Defender ATP customers can [use Microsoft Threat Protection without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="65c22-114">Om du vill börja överföra dina avancerade arbets flöden från Microsoft Defender ATP [aktiverar du skydd mot Microsoft Threat](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="65c22-114">To start transitioning your advanced hunting workflows from Microsoft Defender ATP, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

<span data-ttu-id="65c22-115">Du kan gå över utan att påverka dina befintliga Microsoft Defender ATP-arbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="65c22-115">You can transition without affecting your existing Microsoft Defender ATP workflows.</span></span> <span data-ttu-id="65c22-116">Sparade frågor är oförändrade och anpassade identifierings regler fortsätter att köra och generera aviseringar.</span><span class="sxs-lookup"><span data-stu-id="65c22-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="65c22-117">De kommer att synas i skydd mot Microsoft Threat.</span><span class="sxs-lookup"><span data-stu-id="65c22-117">They will, however, be visible in Microsoft Threat Protection.</span></span> 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a><span data-ttu-id="65c22-118">Endast schema tabeller i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="65c22-118">Schema tables in Microsoft Threat Protection only</span></span>
<span data-ttu-id="65c22-119">Ett [Avancerat Antivirus schema för Microsoft Threat Protection](advanced-hunting-schema-tables.md) ger ytterligare tabeller med data från olika Microsoft 365-säkerhetslösningar.</span><span class="sxs-lookup"><span data-stu-id="65c22-119">The [Microsoft Threat Protection advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="65c22-120">Följande tabeller är endast tillgängliga i Microsoft Threat Protection:</span><span class="sxs-lookup"><span data-stu-id="65c22-120">The following tables are available only in Microsoft Threat Protection:</span></span>

| <span data-ttu-id="65c22-121">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="65c22-121">Table name</span></span> | <span data-ttu-id="65c22-122">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="65c22-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="65c22-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="65c22-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="65c22-124">Filer, IP-adresser, URL: er, användare eller enheter associerade med aviseringar</span><span class="sxs-lookup"><span data-stu-id="65c22-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="65c22-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="65c22-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="65c22-126">Aviseringar från Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security och Azure ATP, inklusive allvarlighets GRADS information och hot kategorier</span><span class="sxs-lookup"><span data-stu-id="65c22-126">Alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="65c22-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="65c22-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="65c22-128">Filrelaterade aktiviteter i moln program och-tjänster</span><span class="sxs-lookup"><span data-stu-id="65c22-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="65c22-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="65c22-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="65c22-130">Information om bifogade filer i e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="65c22-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="65c22-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="65c22-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="65c22-132">Microsoft 365-e-posthändelser, inklusive händelser för e-postleverans och blockering</span><span class="sxs-lookup"><span data-stu-id="65c22-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="65c22-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="65c22-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="65c22-134">Säkerhets händelser som inträffar efter leverans efter att Microsoft 365 har levererat e-postmeddelandet till mottagar post lådan</span><span class="sxs-lookup"><span data-stu-id="65c22-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="65c22-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="65c22-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="65c22-136">Information om URL: er för e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="65c22-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="65c22-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="65c22-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="65c22-138">Händelser som berör en lokal domänkontrollant som kör Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="65c22-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="65c22-139">I den här tabellen beskrivs ett antal identitets relaterade händelser och system händelser på domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="65c22-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="65c22-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="65c22-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="65c22-141">Konto information från olika källor, inklusive Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="65c22-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="65c22-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="65c22-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="65c22-143">Autentiseringsproblem för Active Directory och Microsoft Online-tjänster</span><span class="sxs-lookup"><span data-stu-id="65c22-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="65c22-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="65c22-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="65c22-145">Frågor för Active Directory-objekt, till exempel användare, grupper, enheter och domäner</span><span class="sxs-lookup"><span data-stu-id="65c22-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="65c22-146">Kart DeviceAlertEvents tabell</span><span class="sxs-lookup"><span data-stu-id="65c22-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="65c22-147">`AlertInfo`Tabellerna och `AlertEvidence` ersätter `DeviceAlertEvents` tabellen i Microsoft Defender ATP-schemat.</span><span class="sxs-lookup"><span data-stu-id="65c22-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender ATP schema.</span></span> <span data-ttu-id="65c22-148">Utöver data om enhets aviseringar innehåller de här två tabellerna data om aviseringar för identiteter, appar och e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="65c22-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="65c22-149">Använd följande tabell för att kontrol lera hur `DeviceAlertEvents` kolumnerna mappas till kolumner i `AlertInfo` `AlertEvidence` tabellerna och.</span><span class="sxs-lookup"><span data-stu-id="65c22-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="65c22-150">Förutom kolumnerna i följande tabell `AlertEvidence` innehåller tabellen många andra kolumner som ger en mer holistisk bild av notifieringar från olika källor.</span><span class="sxs-lookup"><span data-stu-id="65c22-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="65c22-151">Se alla AlertEvidence-kolumner</span><span class="sxs-lookup"><span data-stu-id="65c22-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="65c22-152">Kolumnen DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="65c22-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="65c22-153">Här hittar du samma data i Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="65c22-153">Where to find the same data in Microsoft Threat Protection</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="65c22-154">`AlertInfo` och  `AlertEvidence` tabeller</span><span class="sxs-lookup"><span data-stu-id="65c22-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="65c22-155">`AlertInfo` och  `AlertEvidence` tabeller</span><span class="sxs-lookup"><span data-stu-id="65c22-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="65c22-156">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="65c22-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="65c22-157">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="65c22-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="65c22-158">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="65c22-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="65c22-159">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="65c22-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="65c22-160">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="65c22-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="65c22-161">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="65c22-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="65c22-162">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="65c22-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="65c22-163">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="65c22-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="65c22-164">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="65c22-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="65c22-165">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="65c22-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="65c22-166">Den här kolumnen används vanligt vis i Microsoft Defender ATP för att hitta relaterade poster i andra tabeller.</span><span class="sxs-lookup"><span data-stu-id="65c22-166">This column is typically used in Microsoft Defender ATP to locate related records in other tables.</span></span> <span data-ttu-id="65c22-167">I Microsoft Threat Protection kan du hämta relaterade data direkt från `AlertEvidence` tabellen.</span><span class="sxs-lookup"><span data-stu-id="65c22-167">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="65c22-168">Den här kolumnen används vanligt vis i Microsoft Defender ATP för ytterligare information i andra tabeller.</span><span class="sxs-lookup"><span data-stu-id="65c22-168">This column is typically used in Microsoft Defender ATP for additional event information in other tables.</span></span> <span data-ttu-id="65c22-169">I Microsoft Threat Protection kan du hämta relaterade data direkt från `AlertEvidence` tabellen.</span><span class="sxs-lookup"><span data-stu-id="65c22-169">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a><span data-ttu-id="65c22-170">Justera befintliga Microsoft Defender ATP-frågor</span><span class="sxs-lookup"><span data-stu-id="65c22-170">Adjust existing Microsoft Defender ATP queries</span></span>
<span data-ttu-id="65c22-171">Microsoft Defender ATP-frågor fungerar på samma sätt såvida de inte refererar till `DeviceAlertEvents` tabellen.</span><span class="sxs-lookup"><span data-stu-id="65c22-171">Microsoft Defender ATP queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="65c22-172">Tillämpa dessa ändringar för att använda dessa frågor i skydd mot Microsoft Threats:</span><span class="sxs-lookup"><span data-stu-id="65c22-172">To use these queries in Microsoft Threat Protection, apply these changes:</span></span>

- <span data-ttu-id="65c22-173">Ersätt `DeviceAlertEvents` med `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="65c22-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="65c22-174">Gå med i `AlertInfo` och till `AlertEvidence` tabellerna för `AlertId` att få motsvarande data.</span><span class="sxs-lookup"><span data-stu-id="65c22-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="65c22-175">Ursprunglig fråga</span><span class="sxs-lookup"><span data-stu-id="65c22-175">Original query</span></span>
<span data-ttu-id="65c22-176">I följande fråga används `DeviceAlertEvents` Microsoft Defender ATP för att få de meddelanden som berör _powershell.exe_:</span><span class="sxs-lookup"><span data-stu-id="65c22-176">The following query uses `DeviceAlertEvents` in Microsoft Defender ATP to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="65c22-177">Ändrad fråga</span><span class="sxs-lookup"><span data-stu-id="65c22-177">Modified query</span></span>
<span data-ttu-id="65c22-178">Följande fråga har ställts in för användning i Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="65c22-178">The following query has been adjusted for use in Microsoft Threat Protection.</span></span> <span data-ttu-id="65c22-179">I stället för att kontrol lera fil namnet direkt från `DeviceAlertEvents` går det `AlertEvidence` att kontrol lera fil namnet i tabellen.</span><span class="sxs-lookup"><span data-stu-id="65c22-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="65c22-180">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="65c22-180">Related topics</span></span>
- [<span data-ttu-id="65c22-181">Aktivera Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="65c22-181">Turn on Microsoft Threat Protection</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="65c22-182">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="65c22-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="65c22-183">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="65c22-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="65c22-184">Avancerad jakt i Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="65c22-184">Advanced hunting in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)