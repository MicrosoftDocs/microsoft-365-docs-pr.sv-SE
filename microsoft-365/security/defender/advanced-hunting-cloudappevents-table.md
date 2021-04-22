---
title: Tabellen CloudAppEvents i det avancerade sökschemat
description: Läs mer om händelser från molnappar och -tjänster i tabellen CloudAppEvents i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, Microsoft 365 Defender, microsoft 365, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, CloudAppEvents, Cloud App Security, MCAS
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
ms.openlocfilehash: 17f424d368c0df2f07cda41917f005e4163e5750
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935875"
---
# <a name="cloudappevents"></a><span data-ttu-id="20f64-104">CloudAppEvents</span><span class="sxs-lookup"><span data-stu-id="20f64-104">CloudAppEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="20f64-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="20f64-105">**Applies to:**</span></span>
- <span data-ttu-id="20f64-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="20f64-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="20f64-107">Tabellen `CloudAppEvents` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller information om aktiviteter i olika molnappar och tjänster som omfattas av Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="20f64-107">The `CloudAppEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about activities in various cloud apps and services covered by Microsoft Cloud App Security.</span></span> <span data-ttu-id="20f64-108">Gå till Appar och tjänster som omfattas för [en fullständig lista.](#apps-and-services-covered)</span><span class="sxs-lookup"><span data-stu-id="20f64-108">For a complete list, jump to [Apps and services covered](#apps-and-services-covered).</span></span> <span data-ttu-id="20f64-109">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="20f64-109">Use this reference to construct queries that return information from this table.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="20f64-110">Den här tabellen innehåller information som brukade vara tillgänglig i `AppFileEvents` tabellen.</span><span class="sxs-lookup"><span data-stu-id="20f64-110">This table includes information that used to be available in the `AppFileEvents` table.</span></span> <span data-ttu-id="20f64-111">Från och med den 7 mars 2021 bör användare som vill gå igenom filrelaterade aktiviteter i molntjänster på och efter detta datum använda `CloudAppEvents` tabellen i stället.</span><span class="sxs-lookup"><span data-stu-id="20f64-111">Starting March 7, 2021, users hunting through file-related activities in cloud services on and beyond this date should use the `CloudAppEvents` table instead.</span></span> <br><br><span data-ttu-id="20f64-112">Se till att söka efter frågor och anpassade identifieringsregler som fortfarande använder `AppFileEvents` tabellen och redigera dem för att använda `CloudAppEvents` tabellen.</span><span class="sxs-lookup"><span data-stu-id="20f64-112">Make sure to search for queries and custom detection rules that still use the `AppFileEvents` table and edit them to use the `CloudAppEvents` table.</span></span> <span data-ttu-id="20f64-113">Mer information om hur du konverterar påverkade frågor finns i Sök efter [molnappaktiviteter med avancerad sökning i Microsoft 365 Defender.](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857)</span><span class="sxs-lookup"><span data-stu-id="20f64-113">More guidance about converting affected queries can be found in [Hunt across cloud app activities with Microsoft 365 Defender advanced hunting](https://techcommunity.microsoft.com/t5/microsoft-365-defender/hunt-across-cloud-app-activities-with-microsoft-365-defender/ba-p/1893857).</span></span>


<span data-ttu-id="20f64-114">Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="20f64-114">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="20f64-115">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="20f64-115">Column name</span></span> | <span data-ttu-id="20f64-116">Datatyp</span><span class="sxs-lookup"><span data-stu-id="20f64-116">Data type</span></span> | <span data-ttu-id="20f64-117">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="20f64-117">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="20f64-118">datetime</span><span class="sxs-lookup"><span data-stu-id="20f64-118">datetime</span></span> | <span data-ttu-id="20f64-119">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="20f64-119">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="20f64-120">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-120">string</span></span> | <span data-ttu-id="20f64-121">Typ av aktivitet som utlöste händelsen</span><span class="sxs-lookup"><span data-stu-id="20f64-121">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="20f64-122">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-122">string</span></span> | <span data-ttu-id="20f64-123">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="20f64-123">Application that performed the recorded action</span></span> |
| `ApplicationId` | <span data-ttu-id="20f64-124">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-124">string</span></span> | <span data-ttu-id="20f64-125">Unikt ID för programmet</span><span class="sxs-lookup"><span data-stu-id="20f64-125">Unique identifier for the application</span></span> |
| `AccountObjectId` | <span data-ttu-id="20f64-126">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-126">string</span></span> | <span data-ttu-id="20f64-127">Unikt ID för kontot i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="20f64-127">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="20f64-128">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-128">string</span></span> | <span data-ttu-id="20f64-129">Namnet på kontoanvändaren som visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="20f64-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="20f64-130">Detta är en kombination av ett visst namn eller förnamn, en mellaninititiering och efternamn eller efternamn.</span><span class="sxs-lookup"><span data-stu-id="20f64-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `IsAdminOperation` | <span data-ttu-id="20f64-131">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-131">string</span></span> | <span data-ttu-id="20f64-132">Anger om aktiviteten utfördes av en administratör</span><span class="sxs-lookup"><span data-stu-id="20f64-132">Indicates whether the activity was performed by an administrator</span></span> |
| `DeviceType` | <span data-ttu-id="20f64-133">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-133">string</span></span> | <span data-ttu-id="20f64-134">Typ av enhet baserat på syfte och funktionalitet, till exempel "Nätverksenhet", "Arbetsstation", "Server", "Mobil", "Spelkonsol" eller "Skrivare"</span><span class="sxs-lookup"><span data-stu-id="20f64-134">Type of device based on purpose and functionality, such as "Network device", "Workstation", "Server", "Mobile", "Gaming console", or "Printer"</span></span> | 
| `OSPlatform` | <span data-ttu-id="20f64-135">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-135">string</span></span> | <span data-ttu-id="20f64-136">Operativsystemets plattform som körs på enheten.</span><span class="sxs-lookup"><span data-stu-id="20f64-136">Platform of the operating system running on the device.</span></span> <span data-ttu-id="20f64-137">Den här kolumnen visar specifika operativsystem, inklusive variationer inom samma familj, till exempel Windows 10 och Windows 7.</span><span class="sxs-lookup"><span data-stu-id="20f64-137">This column indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> |
| `IPAddress` | <span data-ttu-id="20f64-138">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-138">string</span></span> | <span data-ttu-id="20f64-139">IP-adress tilldelad till slutpunkten och används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="20f64-139">IP address assigned to the endpoint and used during related network communications</span></span> |
| `IsAnonymousProxy` | <span data-ttu-id="20f64-140">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-140">string</span></span> | <span data-ttu-id="20f64-141">Anger om IP-adressen tillhör en känd anonym proxy</span><span class="sxs-lookup"><span data-stu-id="20f64-141">Indicates whether the IP address belongs to a known anonymous proxy</span></span> |
| `CountryCode` | <span data-ttu-id="20f64-142">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-142">string</span></span> | <span data-ttu-id="20f64-143">Kod med två bokstäver som anger landet där klientens IP-adress är geolocerad</span><span class="sxs-lookup"><span data-stu-id="20f64-143">Two-letter code indicating the country where the client IP address is geolocated</span></span> |
| `City` | <span data-ttu-id="20f64-144">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-144">string</span></span> | <span data-ttu-id="20f64-145">Ort där klientens IP-adress är geolocerad</span><span class="sxs-lookup"><span data-stu-id="20f64-145">City where the client IP address is geolocated</span></span> |
| `Isp` | <span data-ttu-id="20f64-146">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-146">string</span></span> | <span data-ttu-id="20f64-147">Internetleverantör (ISP) som är kopplad till IP-adressen</span><span class="sxs-lookup"><span data-stu-id="20f64-147">Internet service provider (ISP) associated with the IP address</span></span> |
| `UserAgent` | <span data-ttu-id="20f64-148">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-148">string</span></span> | <span data-ttu-id="20f64-149">Information om användaragenter från webbläsaren eller ett annat klientprogram</span><span class="sxs-lookup"><span data-stu-id="20f64-149">User agent information from the web browser or other client application</span></span> |
| `ActivityType` | <span data-ttu-id="20f64-150">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-150">string</span></span> | <span data-ttu-id="20f64-151">Typ av aktivitet som utlöste händelsen</span><span class="sxs-lookup"><span data-stu-id="20f64-151">Type of activity that triggered the event</span></span> |
| `ActivityObjects` | <span data-ttu-id="20f64-152">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-152">string</span></span> | <span data-ttu-id="20f64-153">Lista över objekt, till exempel filer eller mappar, som var inblandade i den inspelade aktiviteten</span><span class="sxs-lookup"><span data-stu-id="20f64-153">List of objects, such as files or folders, that were involved in the recorded activity</span></span> |
| `ObjectName` | <span data-ttu-id="20f64-154">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-154">string</span></span> | <span data-ttu-id="20f64-155">Namnet på det objekt som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="20f64-155">Name of the object that the recorded action was applied to</span></span> |
| `ObjectType` | <span data-ttu-id="20f64-156">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-156">string</span></span> | <span data-ttu-id="20f64-157">Typ av objekt, till exempel en fil eller en mapp, som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="20f64-157">Type of object, such as a file or a folder, that the recorded action was applied to</span></span> |
| `ObjectId` | <span data-ttu-id="20f64-158">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-158">string</span></span> | <span data-ttu-id="20f64-159">Unik identifierare för det objekt som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="20f64-159">Unique identifier of the object that the recorded action was applied to</span></span> |
| `ReportId` | <span data-ttu-id="20f64-160">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-160">string</span></span> | <span data-ttu-id="20f64-161">Unikt ID för händelsen</span><span class="sxs-lookup"><span data-stu-id="20f64-161">Unique identifier for the event</span></span> |
| `RawEventData` | <span data-ttu-id="20f64-162">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-162">string</span></span> | <span data-ttu-id="20f64-163">Obearbetad händelseinformation från källprogrammet eller källtjänsten i JSON-format</span><span class="sxs-lookup"><span data-stu-id="20f64-163">Raw event information from the source application or service in JSON format</span></span> |
| `AdditionalFields` | <span data-ttu-id="20f64-164">sträng</span><span class="sxs-lookup"><span data-stu-id="20f64-164">string</span></span> | <span data-ttu-id="20f64-165">Ytterligare information om entiteten eller händelsen</span><span class="sxs-lookup"><span data-stu-id="20f64-165">Additional information about the entity or event</span></span> |

## <a name="apps-and-services-covered"></a><span data-ttu-id="20f64-166">Program och tjänster som omfattas</span><span class="sxs-lookup"><span data-stu-id="20f64-166">Apps and services covered</span></span>

- <span data-ttu-id="20f64-167">Dropbox</span><span class="sxs-lookup"><span data-stu-id="20f64-167">Dropbox</span></span>
- <span data-ttu-id="20f64-168">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="20f64-168">Dynamics 365</span></span>
- <span data-ttu-id="20f64-169">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="20f64-169">Exchange Online</span></span>
- <span data-ttu-id="20f64-170">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="20f64-170">Microsoft Teams</span></span>
- <span data-ttu-id="20f64-171">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="20f64-171">OneDrive for Business</span></span>
- <span data-ttu-id="20f64-172">Power Automate</span><span class="sxs-lookup"><span data-stu-id="20f64-172">Power Automate</span></span>
- <span data-ttu-id="20f64-173">Power BI</span><span class="sxs-lookup"><span data-stu-id="20f64-173">Power BI</span></span>
- <span data-ttu-id="20f64-174">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="20f64-174">SharePoint Online</span></span>
- <span data-ttu-id="20f64-175">Skype för företag</span><span class="sxs-lookup"><span data-stu-id="20f64-175">Skype for Business</span></span>
- <span data-ttu-id="20f64-176">Office 365</span><span class="sxs-lookup"><span data-stu-id="20f64-176">Office 365</span></span>
- <span data-ttu-id="20f64-177">Yammer</span><span class="sxs-lookup"><span data-stu-id="20f64-177">Yammer</span></span> 

## <a name="related-topics"></a><span data-ttu-id="20f64-178">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="20f64-178">Related topics</span></span>
- [<span data-ttu-id="20f64-179">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="20f64-179">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="20f64-180">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="20f64-180">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="20f64-181">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="20f64-181">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="20f64-182">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="20f64-182">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="20f64-183">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="20f64-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="20f64-184">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="20f64-184">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
