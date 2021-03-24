---
title: Tabellen CloudAppEvents i det avancerade sökschemat
description: Läs mer om händelser från molnappar och -tjänster i tabellen CloudAppEvents i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, datatyp, description, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: e9e9cc78289136e22da1871d68a384eac2a901ef
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071593"
---
# <a name="cloudappevents"></a><span data-ttu-id="df491-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="df491-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="df491-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="df491-105">**Applies to:**</span></span>
- <span data-ttu-id="df491-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df491-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="df491-107">Tabellen i det avancerade sökschemat innehåller information om aktiviteter i olika molnappar och tjänster som omfattas av Microsoft Cloud App Security, särskilt `CloudAppEvents` Dropbox, Exchange Online, [](advanced-hunting-overview.md) OneDrive, Microsoft Teams och SharePoint.</span><span class="sxs-lookup"><span data-stu-id="df491-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security, specifically Dropbox, Exchange Online, OneDrive, Microsoft Teams, and SharePoint.</span></span> <span data-ttu-id="df491-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="df491-108">Use this reference to construct queries that return information from this table.</span></span>

>[!IMPORTANT]
><span data-ttu-id="df491-109">Den här tabellen innehåller information som brukade vara tillgänglig i `AppFileEvents` tabellen.</span><span class="sxs-lookup"><span data-stu-id="df491-109">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="df491-110">Från och med den 7 mars 2021 bör användare som vill gå igenom filrelaterade aktiviteter i molntjänster på och efter detta datum använda `CloudAppEvents` tabellen i stället.</span><span class="sxs-lookup"><span data-stu-id="df491-110">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="df491-111">Se till att söka efter frågor och anpassade identifieringsregler som fortfarande använder `AppFileEvents` tabellen och redigera dem för att använda `CloudAppEvents` tabellen.</span><span class="sxs-lookup"><span data-stu-id="df491-111">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="df491-112">Mer information om hur du konverterar påverkade frågor finns i Sök efter [molnappaktiviteter med avancerad sökning i Microsoft 365 Defender.](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)</span><span class="sxs-lookup"><span data-stu-id="df491-112">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="df491-113">Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="df491-113">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="df491-114">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="df491-114">Column name</span></span> | <span data-ttu-id="df491-115">Datatyp</span><span class="sxs-lookup"><span data-stu-id="df491-115">Data type</span></span> | <span data-ttu-id="df491-116">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="df491-116">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="df491-117">datetime</span><span class="sxs-lookup"><span data-stu-id="df491-117">datetime</span></span> | <span data-ttu-id="df491-118">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="df491-118">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="df491-119">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-119">string</span></span> | <span data-ttu-id="df491-120">Typ av aktivitet som utlöste händelsen</span><span class="sxs-lookup"><span data-stu-id="df491-120">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="df491-121">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-121">string</span></span> | <span data-ttu-id="df491-122">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="df491-122">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="df491-123">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-123">string</span></span> | <span data-ttu-id="df491-124">Unikt ID för programmet</span><span class="sxs-lookup"><span data-stu-id="df491-124">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="df491-125">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-125">string</span></span> | <span data-ttu-id="df491-126">Unikt ID för kontot i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="df491-126">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="df491-127">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-127">string</span></span> | <span data-ttu-id="df491-128">Namnet på kontoanvändaren som visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="df491-128">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="df491-129">Detta är en kombination av ett visst namn eller förnamn, en mellaninititiering och efternamn eller efternamn.</span><span class="sxs-lookup"><span data-stu-id="df491-129">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="df491-130">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-130">string</span></span> | <span data-ttu-id="df491-131">Anger om aktiviteten utfördes av en administratör</span><span class="sxs-lookup"><span data-stu-id="df491-131">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="df491-132">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-132">string</span></span> | <span data-ttu-id="df491-133">Typ av enhet baserat på syfte och funktionalitet, till exempel "Nätverksenhet", "Arbetsstation", "Server", "Mobil", "Spelkonsol" eller "Skrivare"</span><span class="sxs-lookup"><span data-stu-id="df491-133">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="df491-134">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-134">string</span></span> | <span data-ttu-id="df491-135">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="df491-135">Platform of the operating system running on the device.</span></span> <span data-ttu-id="df491-136">Den här kolumnen visar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="df491-136">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="df491-137">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-137">string</span></span> | <span data-ttu-id="df491-138">IP-adress tilldelad till slutpunkten och används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="df491-138">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="df491-139">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-139">string</span></span> | <span data-ttu-id="df491-140">Anger om IP-adressen tillhör en känd anonym proxy</span><span class="sxs-lookup"><span data-stu-id="df491-140">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="df491-141">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-141">string</span></span> | <span data-ttu-id="df491-142">Kod med två bokstäver som anger landet där klientens IP-adress är geolocerad</span><span class="sxs-lookup"><span data-stu-id="df491-142">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="df491-143">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-143">string</span></span> | <span data-ttu-id="df491-144">Ort där klientens IP-adress är geolocerad</span><span class="sxs-lookup"><span data-stu-id="df491-144">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="df491-145">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-145">string</span></span> | <span data-ttu-id="df491-146">Internetleverantör (ISP) som är kopplad till IP-adressen</span><span class="sxs-lookup"><span data-stu-id="df491-146">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="df491-147">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-147">string</span></span> | <span data-ttu-id="df491-148">Information om användaragenter från webbläsaren eller ett annat klientprogram</span><span class="sxs-lookup"><span data-stu-id="df491-148">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="df491-149">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-149">string</span></span> | <span data-ttu-id="df491-150">Typ av aktivitet som utlöste händelsen</span><span class="sxs-lookup"><span data-stu-id="df491-150">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="df491-151">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-151">string</span></span> | <span data-ttu-id="df491-152">Lista över objekt, till exempel filer eller mappar, som var inblandade i den inspelade aktiviteten</span><span class="sxs-lookup"><span data-stu-id="df491-152">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="df491-153">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-153">string</span></span> | <span data-ttu-id="df491-154">Namnet på det objekt som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="df491-154">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="df491-155">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-155">string</span></span> | <span data-ttu-id="df491-156">Typ av objekt, till exempel en fil eller en mapp, som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="df491-156">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="df491-157">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-157">string</span></span> | <span data-ttu-id="df491-158">Unik identifierare för det objekt som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="df491-158">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="df491-159">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-159">string</span></span> | <span data-ttu-id="df491-160">Unikt ID för händelsen</span><span class="sxs-lookup"><span data-stu-id="df491-160">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="df491-161">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-161">string</span></span> | <span data-ttu-id="df491-162">Obearbetad händelseinformation från källprogrammet eller källtjänsten i JSON-format</span><span class="sxs-lookup"><span data-stu-id="df491-162">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="df491-163">sträng</span><span class="sxs-lookup"><span data-stu-id="df491-163">string</span></span> | <span data-ttu-id="df491-164">Ytterligare information om entiteten eller händelsen</span><span class="sxs-lookup"><span data-stu-id="df491-164">Additional information about the entity or event</span></span> |


## <a name="related-topics"></a><span data-ttu-id="df491-165">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="df491-165">Related topics</span></span>
- [<span data-ttu-id="df491-166">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="df491-166">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="df491-167">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="df491-167">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="df491-168">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="df491-168">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="df491-169">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="df491-169">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="df491-170">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="df491-170">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="df491-171">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="df491-171">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
