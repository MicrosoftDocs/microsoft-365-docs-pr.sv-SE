---
title: CloudAppEvents-tabellen i det avancerade sökschemat
description: Läs mer om händelser från molnappar och -tjänster i tabellen CloudAppEvents i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, CloudAppEvents, Cloud App Security, MCAS
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
ms.technology: m365d
ms.openlocfilehash: 021a8210bbe5886021e980b33ade0b9e2ded7b5b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928459"
---
# <a name="cloudappevents"></a><span data-ttu-id="58411-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="58411-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="58411-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="58411-105">**Applies to:**</span></span>
- <span data-ttu-id="58411-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="58411-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="58411-107">Tabellen i det avancerade sökschemat, som för närvarande finns i förhandsversion, innehåller information om aktiviteter i olika molnappar och -tjänster, särskilt `CloudAppEvents` Microsoft Teams och Exchange Online. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="58411-107">Currently available in preview, the `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services, specifically Microsoft Teams and Exchange Online.</span></span> <span data-ttu-id="58411-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="58411-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="58411-109">Den här tabellen utökas med fler aktiviteter som övervakas av Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="58411-109">This table will expand to include more activities monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="58411-110">Så småningom kommer den här tabellen att innehålla filaktivitet som för närvarande lagras i [tabellen AppFileEvents.](advanced-hunting-appfileevents-table.md)</span><span class="sxs-lookup"><span data-stu-id="58411-110">Eventually, this table will include file activity currently stored in the [AppFileEvents](advanced-hunting-appfileevents-table.md) table.</span></span> <span data-ttu-id="58411-111">Microsoft ger ytterligare vägledning när mer information flyttas till den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="58411-111">Microsoft will provide additional guidance as more data moves to this table.</span></span>

<span data-ttu-id="58411-112">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="58411-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="58411-113">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="58411-113">Column name</span></span> | <span data-ttu-id="58411-114">Datatyp</span><span class="sxs-lookup"><span data-stu-id="58411-114">Data type</span></span> | <span data-ttu-id="58411-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="58411-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="58411-116">datetime</span><span class="sxs-lookup"><span data-stu-id="58411-116">datetime</span></span> | <span data-ttu-id="58411-117">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="58411-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="58411-118">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-118">string</span></span> | <span data-ttu-id="58411-119">Typ av aktivitet som utlöste händelsen</span><span class="sxs-lookup"><span data-stu-id="58411-119">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="58411-120">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-120">string</span></span> | <span data-ttu-id="58411-121">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="58411-121">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="58411-122">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-122">string</span></span> | <span data-ttu-id="58411-123">Unikt ID för programmet</span><span class="sxs-lookup"><span data-stu-id="58411-123">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="58411-124">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-124">string</span></span> | <span data-ttu-id="58411-125">Unikt ID för kontot i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="58411-125">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="58411-126">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-126">string</span></span> | <span data-ttu-id="58411-127">Namnet på kontoanvändaren som visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="58411-127">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="58411-128">Vanligtvis en kombination av ett visst namn eller förnamn, en mellaninititiering och ett efternamn eller efternamn.</span><span class="sxs-lookup"><span data-stu-id="58411-128">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="58411-129">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-129">string</span></span> | <span data-ttu-id="58411-130">Anger om aktiviteten utfördes av en administratör</span><span class="sxs-lookup"><span data-stu-id="58411-130">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="58411-131">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-131">string</span></span> | <span data-ttu-id="58411-132">Typ av enhet baserat på syfte och funktionalitet, till exempel "Nätverksenhet", "Arbetsstation", "Server", "Mobil", "Spelkonsol" eller "Skrivare"</span><span class="sxs-lookup"><span data-stu-id="58411-132">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="58411-133">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-133">string</span></span> | <span data-ttu-id="58411-134">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="58411-134">Platform of the operating system running on the device.</span></span> <span data-ttu-id="58411-135">Den här kolumnen anger specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="58411-135">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="58411-136">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-136">string</span></span> | <span data-ttu-id="58411-137">IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="58411-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="58411-138">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-138">string</span></span> | <span data-ttu-id="58411-139">Anger om IP-adressen tillhör en känd anonym proxy</span><span class="sxs-lookup"><span data-stu-id="58411-139">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="58411-140">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-140">string</span></span> | <span data-ttu-id="58411-141">Kod med två bokstäver som anger landet där klient-IP-adressen är geolokal</span><span class="sxs-lookup"><span data-stu-id="58411-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="58411-142">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-142">string</span></span> | <span data-ttu-id="58411-143">Ort där klient-IP-adressen är geolokal</span><span class="sxs-lookup"><span data-stu-id="58411-143">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="58411-144">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-144">string</span></span> | <span data-ttu-id="58411-145">Internet tjänstprovider (ISP) som är kopplat till IP-adressen</span><span class="sxs-lookup"><span data-stu-id="58411-145">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="58411-146">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-146">string</span></span> | <span data-ttu-id="58411-147">Information om användaragenter från webbläsaren eller ett annat klientprogram</span><span class="sxs-lookup"><span data-stu-id="58411-147">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="58411-148">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-148">string</span></span> | <span data-ttu-id="58411-149">Typ av aktivitet som utlöste händelsen</span><span class="sxs-lookup"><span data-stu-id="58411-149">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="58411-150">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-150">string</span></span> | <span data-ttu-id="58411-151">Lista över objekt, till exempel filer eller mappar, som var inblandade i den inspelade aktiviteten</span><span class="sxs-lookup"><span data-stu-id="58411-151">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="58411-152">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-152">string</span></span> | <span data-ttu-id="58411-153">Namnet på det objekt som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="58411-153">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="58411-154">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-154">string</span></span> | <span data-ttu-id="58411-155">Typ av objekt, till exempel en fil eller en mapp, som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="58411-155">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="58411-156">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-156">string</span></span> | <span data-ttu-id="58411-157">Unikt ID för det objekt som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="58411-157">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="58411-158">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-158">string</span></span> | <span data-ttu-id="58411-159">Unikt ID för händelsen</span><span class="sxs-lookup"><span data-stu-id="58411-159">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="58411-160">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-160">string</span></span> | <span data-ttu-id="58411-161">Obearbetad händelseinformation från källprogrammet eller källtjänsten i JSON-format</span><span class="sxs-lookup"><span data-stu-id="58411-161">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="58411-162">sträng</span><span class="sxs-lookup"><span data-stu-id="58411-162">string</span></span> | <span data-ttu-id="58411-163">Ytterligare information om entiteten eller händelsen</span><span class="sxs-lookup"><span data-stu-id="58411-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="58411-164">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="58411-164">Related topics</span></span>
- [<span data-ttu-id="58411-165">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="58411-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="58411-166">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="58411-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="58411-167">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="58411-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="58411-168">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="58411-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="58411-169">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="58411-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="58411-170">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="58411-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
