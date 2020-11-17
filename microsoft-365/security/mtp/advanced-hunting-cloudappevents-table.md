---
title: CloudAppEvents-tabell i det avancerade jakt-schemat
description: Lär dig mer om händelser från moln program och-tjänster i CloudAppEvents-tabellen för avancerat jakt schema
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, CloudAppEvents, Cloud App-säkerhet, MCAS
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
ms.openlocfilehash: 3cb4498e5db6a7752e99b8c677bc8936d2c975ef
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087776"
---
# <a name="cloudappevents"></a><span data-ttu-id="18261-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="18261-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="18261-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="18261-105">**Applies to:**</span></span>
- <span data-ttu-id="18261-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="18261-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="18261-107">För närvarande tillgänglig i förhands granskningen `CloudAppEvents` innehåller tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat information om aktiviteter i olika moln program och-tjänster, särskilt Microsoft Teams och Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="18261-107">Currently available in preview, the `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services, specifically Microsoft Teams and Exchange Online.</span></span> <span data-ttu-id="18261-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="18261-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="18261-109">Denna tabell expanderar för att omfatta fler aktiviteter som övervakas av Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="18261-109">This table will expand to include more activities monitored by Microsoft Cloud App Security.</span></span> <span data-ttu-id="18261-110">Till sist kommer den här tabellen att innehålla fil aktivitet som lagras i tabellen [AppFileEvents](advanced-hunting-appfileevents-table.md) .</span><span class="sxs-lookup"><span data-stu-id="18261-110">Eventually, this table will include file activity currently stored in the [AppFileEvents](advanced-hunting-appfileevents-table.md) table.</span></span> <span data-ttu-id="18261-111">Microsoft tillhandahåller ytterligare vägledning när mer data flyttas till den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="18261-111">Microsoft will provide additional guidance as more data moves to this table.</span></span>

<span data-ttu-id="18261-112">Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="18261-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="18261-113">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="18261-113">Column name</span></span> | <span data-ttu-id="18261-114">Datatyp</span><span class="sxs-lookup"><span data-stu-id="18261-114">Data type</span></span> | <span data-ttu-id="18261-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="18261-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="18261-116">datetime</span><span class="sxs-lookup"><span data-stu-id="18261-116">datetime</span></span> | <span data-ttu-id="18261-117">Datum och tid när händelsen registrerades</span><span class="sxs-lookup"><span data-stu-id="18261-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="18261-118">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-118">string</span></span> | <span data-ttu-id="18261-119">Typ av aktivitet som utlöste händelsen</span><span class="sxs-lookup"><span data-stu-id="18261-119">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="18261-120">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-120">string</span></span> | <span data-ttu-id="18261-121">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="18261-121">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="18261-122">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-122">string</span></span> | <span data-ttu-id="18261-123">Unik identifierare för programmet</span><span class="sxs-lookup"><span data-stu-id="18261-123">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="18261-124">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-124">string</span></span> | <span data-ttu-id="18261-125">Unik identifierare för kontot i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="18261-125">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="18261-126">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-126">string</span></span> | <span data-ttu-id="18261-127">Namnet på kontot som visas i adress boken.</span><span class="sxs-lookup"><span data-stu-id="18261-127">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="18261-128">Vanligt vis en kombination av ett visst eller förnamn, en mellan initiering och ett efter namn eller från gång.</span><span class="sxs-lookup"><span data-stu-id="18261-128">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="18261-129">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-129">string</span></span> | <span data-ttu-id="18261-130">Anger om aktiviteten utfördes av en administratör</span><span class="sxs-lookup"><span data-stu-id="18261-130">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="18261-131">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-131">string</span></span> | <span data-ttu-id="18261-132">Typ av enhet baserat på syfte och funktioner, till exempel "nätverks enhet", "arbets Station", "Server", "mobil", "spel konsol" eller "skrivare"</span><span class="sxs-lookup"><span data-stu-id="18261-132">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="18261-133">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-133">string</span></span> | <span data-ttu-id="18261-134">Plattformen för det operativ system som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="18261-134">Platform of the operating system running on the device.</span></span> <span data-ttu-id="18261-135">I den här kolumnen anges specifika operativ system, inklusive varianter inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="18261-135">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="18261-136">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-136">string</span></span> | <span data-ttu-id="18261-137">IP-adress tilldelad till slut punkten och används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="18261-137">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="18261-138">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-138">string</span></span> | <span data-ttu-id="18261-139">Anger om IP-adressen tillhör en känd anonym proxyserver</span><span class="sxs-lookup"><span data-stu-id="18261-139">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="18261-140">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-140">string</span></span> | <span data-ttu-id="18261-141">Kod med två bokstäver som anger det land där klient-IP-adressen finns</span><span class="sxs-lookup"><span data-stu-id="18261-141">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="18261-142">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-142">string</span></span> | <span data-ttu-id="18261-143">Ort där klient-IP-adressen finns</span><span class="sxs-lookup"><span data-stu-id="18261-143">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="18261-144">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-144">string</span></span> | <span data-ttu-id="18261-145">Internet leverantör (ISP) associerad med IP-adressen</span><span class="sxs-lookup"><span data-stu-id="18261-145">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="18261-146">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-146">string</span></span> | <span data-ttu-id="18261-147">Information om användar agent från webbläsaren eller andra klient program</span><span class="sxs-lookup"><span data-stu-id="18261-147">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="18261-148">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-148">string</span></span> | <span data-ttu-id="18261-149">Typ av aktivitet som utlöste händelsen</span><span class="sxs-lookup"><span data-stu-id="18261-149">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="18261-150">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-150">string</span></span> | <span data-ttu-id="18261-151">Lista över objekt, till exempel filer och mappar, som ingick i den registrerade aktiviteten</span><span class="sxs-lookup"><span data-stu-id="18261-151">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="18261-152">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-152">string</span></span> | <span data-ttu-id="18261-153">Namnet på det objekt som den inspelade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="18261-153">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="18261-154">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-154">string</span></span> | <span data-ttu-id="18261-155">Typ av objekt, till exempel en fil eller en mapp, som den inspelade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="18261-155">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="18261-156">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-156">string</span></span> | <span data-ttu-id="18261-157">Unik identifierare för det objekt som den inspelade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="18261-157">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="18261-158">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-158">string</span></span> | <span data-ttu-id="18261-159">Unik identifierare för händelsen</span><span class="sxs-lookup"><span data-stu-id="18261-159">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="18261-160">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-160">string</span></span> | <span data-ttu-id="18261-161">Information om rå händelser från käll programmet eller tjänsten i JSON-format</span><span class="sxs-lookup"><span data-stu-id="18261-161">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="18261-162">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="18261-162">string</span></span> | <span data-ttu-id="18261-163">Ytterligare information om enheten eller händelsen</span><span class="sxs-lookup"><span data-stu-id="18261-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="18261-164">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="18261-164">Related topics</span></span>
- [<span data-ttu-id="18261-165">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="18261-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="18261-166">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="18261-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="18261-167">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="18261-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="18261-168">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="18261-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="18261-169">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="18261-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="18261-170">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="18261-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
