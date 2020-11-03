---
title: Migrera frågor om avancerade jakt från Microsoft Defender för slut punkt
description: Lär dig hur du justerar Microsoft Defender för slut punkts frågor så att du kan använda dem i Microsoft 365 Defender
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8b69dff94cc5d3ba3331fd6d13b1d7de1402ac47
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846862"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="7fa0f-104">Migrera frågor om avancerade jakt från Microsoft Defender för slut punkt</span><span class="sxs-lookup"><span data-stu-id="7fa0f-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7fa0f-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="7fa0f-105">**Applies to:**</span></span>
- <span data-ttu-id="7fa0f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7fa0f-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="7fa0f-107">Flytta dina avancerade jakt arbets flöden från Microsoft Defender för slut punkt för att proaktivt använda en bredare uppsättning data.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="7fa0f-108">I Microsoft 365 Defender får du till gång till data från andra säkerhetslösningar från Microsoft 365, till exempel:</span><span class="sxs-lookup"><span data-stu-id="7fa0f-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="7fa0f-109">Microsoft Defender för slut punkt</span><span class="sxs-lookup"><span data-stu-id="7fa0f-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="7fa0f-110">Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="7fa0f-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="7fa0f-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7fa0f-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="7fa0f-112">Microsoft Defender för identitet</span><span class="sxs-lookup"><span data-stu-id="7fa0f-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="7fa0f-113">De flesta Microsoft Defender för slut punkter kan [använda Microsoft 365 Defender utan ytterligare licenser](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="7fa0f-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="7fa0f-114">Om du vill börja överta dina avancerade arbets flöden från Defender för slut punkt [aktiverar du Microsoft 365 Defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="7fa0f-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="7fa0f-115">Du kan gå över utan att påverka dina befintliga Defender för slut arbets flöden.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="7fa0f-116">Sparade frågor är oförändrade och anpassade identifierings regler fortsätter att köra och generera aviseringar.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="7fa0f-117">De kommer att synas i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="7fa0f-118">Schema tabeller i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7fa0f-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="7fa0f-119">[Microsoft 365 Defender Advanced jakt-schemat](advanced-hunting-schema-tables.md) innehåller ytterligare tabeller med data från olika Microsoft 365-säkerhetslösningar.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="7fa0f-120">Följande tabeller är endast tillgängliga i Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="7fa0f-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="7fa0f-121">Tabellnamn</span><span class="sxs-lookup"><span data-stu-id="7fa0f-121">Table name</span></span> | <span data-ttu-id="7fa0f-122">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7fa0f-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="7fa0f-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="7fa0f-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="7fa0f-124">Filer, IP-adresser, URL: er, användare eller enheter associerade med aviseringar</span><span class="sxs-lookup"><span data-stu-id="7fa0f-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="7fa0f-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="7fa0f-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="7fa0f-126">Aviseringar från Microsoft Defender för slut punkt, Microsoft Defender för Office 365, Microsoft Cloud App Security och Microsoft Defender för identitet, inklusive allvarlighets GRADS information och hot kategorier</span><span class="sxs-lookup"><span data-stu-id="7fa0f-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="7fa0f-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="7fa0f-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="7fa0f-128">Filrelaterade aktiviteter i moln program och-tjänster</span><span class="sxs-lookup"><span data-stu-id="7fa0f-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="7fa0f-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="7fa0f-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="7fa0f-130">Information om bifogade filer i e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="7fa0f-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="7fa0f-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="7fa0f-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="7fa0f-132">Microsoft 365-e-posthändelser, inklusive händelser för e-postleverans och blockering</span><span class="sxs-lookup"><span data-stu-id="7fa0f-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="7fa0f-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="7fa0f-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="7fa0f-134">Säkerhets händelser som inträffar efter leverans efter att Microsoft 365 har levererat e-postmeddelandet till mottagar post lådan</span><span class="sxs-lookup"><span data-stu-id="7fa0f-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="7fa0f-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="7fa0f-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="7fa0f-136">Information om URL: er för e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="7fa0f-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="7fa0f-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="7fa0f-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="7fa0f-138">Händelser som berör en lokal domänkontrollant som kör Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="7fa0f-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="7fa0f-139">I den här tabellen beskrivs ett antal identitets relaterade händelser och system händelser på domänkontrollanten.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="7fa0f-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="7fa0f-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="7fa0f-141">Konto information från olika källor, inklusive Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7fa0f-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="7fa0f-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="7fa0f-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="7fa0f-143">Autentiseringsproblem för Active Directory och Microsoft Online-tjänster</span><span class="sxs-lookup"><span data-stu-id="7fa0f-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="7fa0f-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="7fa0f-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="7fa0f-145">Frågor för Active Directory-objekt, till exempel användare, grupper, enheter och domäner</span><span class="sxs-lookup"><span data-stu-id="7fa0f-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="7fa0f-146">Kart DeviceAlertEvents tabell</span><span class="sxs-lookup"><span data-stu-id="7fa0f-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="7fa0f-147">`AlertInfo`Tabellerna och `AlertEvidence` ersätter `DeviceAlertEvents` tabellen i Microsoft Defender för slut punkts schema.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="7fa0f-148">Utöver data om enhets aviseringar innehåller de här två tabellerna data om aviseringar för identiteter, appar och e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="7fa0f-149">Använd följande tabell för att kontrol lera hur `DeviceAlertEvents` kolumnerna mappas till kolumner i `AlertInfo` `AlertEvidence` tabellerna och.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="7fa0f-150">Förutom kolumnerna i följande tabell `AlertEvidence` innehåller tabellen många andra kolumner som ger en mer holistisk bild av notifieringar från olika källor.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="7fa0f-151">Se alla AlertEvidence-kolumner</span><span class="sxs-lookup"><span data-stu-id="7fa0f-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="7fa0f-152">Kolumnen DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="7fa0f-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="7fa0f-153">Här hittar du samma data i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7fa0f-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="7fa0f-154">`AlertInfo` och  `AlertEvidence` tabeller</span><span class="sxs-lookup"><span data-stu-id="7fa0f-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="7fa0f-155">`AlertInfo` och  `AlertEvidence` tabeller</span><span class="sxs-lookup"><span data-stu-id="7fa0f-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="7fa0f-156">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="7fa0f-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="7fa0f-157">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="7fa0f-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="7fa0f-158">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="7fa0f-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="7fa0f-159">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="7fa0f-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="7fa0f-160">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="7fa0f-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="7fa0f-161">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="7fa0f-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="7fa0f-162">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="7fa0f-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="7fa0f-163">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="7fa0f-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="7fa0f-164">`AlertEvidence` tabell</span><span class="sxs-lookup"><span data-stu-id="7fa0f-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="7fa0f-165">`AlertInfo` tabell</span><span class="sxs-lookup"><span data-stu-id="7fa0f-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="7fa0f-166">Den här kolumnen används vanligt vis i Microsoft Defender för slut punkter för att hitta relaterade poster i andra tabeller.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="7fa0f-167">I Microsoft 365 Defender kan du hämta relaterade data direkt från `AlertEvidence` tabellen.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="7fa0f-168">Den här kolumnen används vanligt vis i Microsoft Defender för att få ytterligare information i andra tabeller.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="7fa0f-169">I Microsoft 365 Defender kan du hämta relaterade data direkt från `AlertEvidence` tabellen.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="7fa0f-170">Justera befintliga Microsoft Defender för slut punkts frågor</span><span class="sxs-lookup"><span data-stu-id="7fa0f-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="7fa0f-171">Microsoft Defender för slut punkts frågor fungerar på samma sätt såvida den inte refererar till `DeviceAlertEvents` tabellen.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="7fa0f-172">Tillämpa dessa ändringar för att använda dessa frågor i Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="7fa0f-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="7fa0f-173">Ersätt `DeviceAlertEvents` med `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="7fa0f-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="7fa0f-174">Gå med i `AlertInfo` och till `AlertEvidence` tabellerna för `AlertId` att få motsvarande data.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="7fa0f-175">Ursprunglig fråga</span><span class="sxs-lookup"><span data-stu-id="7fa0f-175">Original query</span></span>
<span data-ttu-id="7fa0f-176">I följande fråga används `DeviceAlertEvents` Microsoft Defender för slut punkt för att få aviseringar som berör _powershell.exe_ :</span><span class="sxs-lookup"><span data-stu-id="7fa0f-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_ :</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="7fa0f-177">Ändrad fråga</span><span class="sxs-lookup"><span data-stu-id="7fa0f-177">Modified query</span></span>
<span data-ttu-id="7fa0f-178">Följande fråga har ställts in för användning i Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="7fa0f-179">I stället för att kontrol lera fil namnet direkt från `DeviceAlertEvents` går det `AlertEvidence` att kontrol lera fil namnet i tabellen.</span><span class="sxs-lookup"><span data-stu-id="7fa0f-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="7fa0f-180">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="7fa0f-180">Related topics</span></span>
- [<span data-ttu-id="7fa0f-181">Aktivera Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7fa0f-181">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="7fa0f-182">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="7fa0f-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="7fa0f-183">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="7fa0f-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="7fa0f-184">Avancerad jakt i Microsoft Defender för slut punkten</span><span class="sxs-lookup"><span data-stu-id="7fa0f-184">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)