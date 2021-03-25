---
title: Tabellen DeviceImageLoadEvents i det avancerade sökschemat
description: Läs mer om DLL-inläsningshändelser i tabellen DeviceImageLoadEvents i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, deviceimageloadevents, DLL-inläsning, bibliotek, filbild, ImageLoadEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: aad270a101e7052e04e4530e661e0e86c2db70d2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075106"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="1fd55-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="1fd55-104">DeviceImageLoadEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1fd55-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1fd55-105">**Applies to:**</span></span>
- [<span data-ttu-id="1fd55-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1fd55-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="1fd55-107">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="1fd55-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1fd55-108">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="1fd55-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="1fd55-109">Tabellen `DeviceImageLoadEvents` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller information om DLL-inläsningshändelser.</span><span class="sxs-lookup"><span data-stu-id="1fd55-109">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="1fd55-110">Använd den här referensen för att skapa frågor som returnerar information från tabellen.</span><span class="sxs-lookup"><span data-stu-id="1fd55-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="1fd55-111">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökningsschema.](advanced-hunting-schema-reference.md)</span><span class="sxs-lookup"><span data-stu-id="1fd55-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="1fd55-112">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="1fd55-112">Column name</span></span> | <span data-ttu-id="1fd55-113">Datatyp</span><span class="sxs-lookup"><span data-stu-id="1fd55-113">Data type</span></span> | <span data-ttu-id="1fd55-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1fd55-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="1fd55-115">datetime</span><span class="sxs-lookup"><span data-stu-id="1fd55-115">datetime</span></span> | <span data-ttu-id="1fd55-116">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="1fd55-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="1fd55-117">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-117">string</span></span> | <span data-ttu-id="1fd55-118">Unikt ID för enheten i tjänsten</span><span class="sxs-lookup"><span data-stu-id="1fd55-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="1fd55-119">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-119">string</span></span> | <span data-ttu-id="1fd55-120">Fullständigt kvalificerat domännamn (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="1fd55-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ActionType` | <span data-ttu-id="1fd55-121">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-121">string</span></span> | <span data-ttu-id="1fd55-122">Typ av aktivitet som utlöste händelsen</span><span class="sxs-lookup"><span data-stu-id="1fd55-122">Type of activity that triggered the event</span></span> |
| `FileName` | <span data-ttu-id="1fd55-123">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-123">string</span></span> | <span data-ttu-id="1fd55-124">Namnet på filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="1fd55-124">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="1fd55-125">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-125">string</span></span> | <span data-ttu-id="1fd55-126">Mapp som innehåller den fil som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="1fd55-126">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="1fd55-127">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-127">string</span></span> | <span data-ttu-id="1fd55-128">SHA-1 för filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="1fd55-128">SHA-1 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="1fd55-129">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-129">string</span></span> | <span data-ttu-id="1fd55-130">MD5-hash för filen som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="1fd55-130">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="1fd55-131">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-131">string</span></span> | <span data-ttu-id="1fd55-132">Domän för kontot som körde processen som ansvarar för händelsen</span><span class="sxs-lookup"><span data-stu-id="1fd55-132">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="1fd55-133">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-133">string</span></span> | <span data-ttu-id="1fd55-134">Användarnamn för det konto som körde processen som ansvarar för händelsen</span><span class="sxs-lookup"><span data-stu-id="1fd55-134">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="1fd55-135">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-135">string</span></span> | <span data-ttu-id="1fd55-136">Säkerhetsidentifierare (SID) för kontot som körde processen som ansvarar för händelsen</span><span class="sxs-lookup"><span data-stu-id="1fd55-136">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="1fd55-137">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-137">string</span></span> | <span data-ttu-id="1fd55-138">Integritetsnivån för processen som initierade händelsen.</span><span class="sxs-lookup"><span data-stu-id="1fd55-138">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="1fd55-139">I Windows tilldelar Windows integritetsnivåer till processer baserat på vissa egenskaper, till exempel om de startades från en Internetnedladdning.</span><span class="sxs-lookup"><span data-stu-id="1fd55-139">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="1fd55-140">De här integritetsnivåerna påverkar behörigheter till resurser</span><span class="sxs-lookup"><span data-stu-id="1fd55-140">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="1fd55-141">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-141">string</span></span> | <span data-ttu-id="1fd55-142">Tokentyp som anger närvaro eller frånvaro av UAC-behörighets ökning (User Access Control) som används för processen som initierade händelsen</span><span class="sxs-lookup"><span data-stu-id="1fd55-142">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="1fd55-143">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-143">string</span></span> | <span data-ttu-id="1fd55-144">SHA-1 för processen (bildfil) som initierade händelsen</span><span class="sxs-lookup"><span data-stu-id="1fd55-144">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="1fd55-145">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-145">string</span></span> | <span data-ttu-id="1fd55-146">MD5-hash för processen (bildfil) som initierade händelsen</span><span class="sxs-lookup"><span data-stu-id="1fd55-146">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="1fd55-147">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-147">string</span></span> | <span data-ttu-id="1fd55-148">Namn på processen som initierade händelsen</span><span class="sxs-lookup"><span data-stu-id="1fd55-148">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="1fd55-149">int</span><span class="sxs-lookup"><span data-stu-id="1fd55-149">int</span></span> | <span data-ttu-id="1fd55-150">Process-ID (PID) för processen som initierade händelsen</span><span class="sxs-lookup"><span data-stu-id="1fd55-150">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="1fd55-151">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-151">string</span></span> | <span data-ttu-id="1fd55-152">Kommandorad som används för att köra processen som initierade händelsen</span><span class="sxs-lookup"><span data-stu-id="1fd55-152">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="1fd55-153">datetime</span><span class="sxs-lookup"><span data-stu-id="1fd55-153">datetime</span></span> | <span data-ttu-id="1fd55-154">Datum och tid då processen som initierade händelsen startades</span><span class="sxs-lookup"><span data-stu-id="1fd55-154">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="1fd55-155">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-155">string</span></span> | <span data-ttu-id="1fd55-156">Mapp som innehåller den process (bildfil) som initierade händelsen</span><span class="sxs-lookup"><span data-stu-id="1fd55-156">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="1fd55-157">int</span><span class="sxs-lookup"><span data-stu-id="1fd55-157">int</span></span> | <span data-ttu-id="1fd55-158">Process-ID (PID) för den överordnade process som hanterade processen som ansvarar för händelsen</span><span class="sxs-lookup"><span data-stu-id="1fd55-158">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="1fd55-159">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-159">string</span></span> | <span data-ttu-id="1fd55-160">Namn på den överordnade process som gav upphov till processen som ansvarar för händelsen</span><span class="sxs-lookup"><span data-stu-id="1fd55-160">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="1fd55-161">datetime</span><span class="sxs-lookup"><span data-stu-id="1fd55-161">datetime</span></span> | <span data-ttu-id="1fd55-162">Datum och tid då föräldern till processen som ansvarar för händelsen startades</span><span class="sxs-lookup"><span data-stu-id="1fd55-162">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="1fd55-163">long</span><span class="sxs-lookup"><span data-stu-id="1fd55-163">long</span></span> | <span data-ttu-id="1fd55-164">Händelseidentifierare baserat på en räknare för upprepande händelser.</span><span class="sxs-lookup"><span data-stu-id="1fd55-164">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="1fd55-165">För att identifiera unika händelser måste den här kolumnen användas tillsammans med `DeviceName` `Timestamp` kolumnerna och</span><span class="sxs-lookup"><span data-stu-id="1fd55-165">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="1fd55-166">sträng</span><span class="sxs-lookup"><span data-stu-id="1fd55-166">string</span></span> | <span data-ttu-id="1fd55-167">Identifierare för den virtualiserade behållaren som används av Application Guard för att isolera webbläsaraktivitet</span><span class="sxs-lookup"><span data-stu-id="1fd55-167">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="1fd55-168">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="1fd55-168">Related topics</span></span>
- [<span data-ttu-id="1fd55-169">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="1fd55-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1fd55-170">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="1fd55-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1fd55-171">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="1fd55-171">Understand the schema</span></span>](advanced-hunting-schema-reference.md)