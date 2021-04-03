---
title: Tabellen IdentityDirectoryEvents i det avancerade sökschemat
description: Läs mer om domänkontrollanter och Active Directory-händelser i tabellen IdentityDirectoryEvents i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, IdentityDirectoryEvents, domänkontrollant, Active Directory, Azure ATP, identiteter
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
ms.openlocfilehash: 73018bb65c011d10234ec9c02fc61bfb93fa125a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501133"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="429f0-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="429f0-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="429f0-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="429f0-105">**Applies to:**</span></span>
- <span data-ttu-id="429f0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="429f0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="429f0-107">Tabellen `IdentityDirectoryEvents` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller händelser som innefattar en lokal domänkontrollant som kör Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="429f0-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="429f0-108">I den här tabellen visas olika identitetsrelaterade händelser, som lösenordsändringar, giltighetstid för lösenord och ändringar av huvudnamn (UPN).</span><span class="sxs-lookup"><span data-stu-id="429f0-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="429f0-109">Den fångar även systemhändelser på domänkontrollanten, som schemaläggning av uppgifter och PowerShell-aktivitet.</span><span class="sxs-lookup"><span data-stu-id="429f0-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="429f0-110">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="429f0-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="429f0-111">Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` inbyggda schemareferensen som finns i säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="429f0-111">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="429f0-112">Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="429f0-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="429f0-113">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="429f0-113">Column name</span></span> | <span data-ttu-id="429f0-114">Datatyp</span><span class="sxs-lookup"><span data-stu-id="429f0-114">Data type</span></span> | <span data-ttu-id="429f0-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="429f0-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="429f0-116">datetime</span><span class="sxs-lookup"><span data-stu-id="429f0-116">datetime</span></span> | <span data-ttu-id="429f0-117">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="429f0-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="429f0-118">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-118">string</span></span> | <span data-ttu-id="429f0-119">Typ av aktivitet som utlöste händelsen.</span><span class="sxs-lookup"><span data-stu-id="429f0-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="429f0-120">Mer information [finns i schemareferensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i portalen</span><span class="sxs-lookup"><span data-stu-id="429f0-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="429f0-121">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-121">string</span></span> | <span data-ttu-id="429f0-122">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="429f0-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="429f0-123">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-123">string</span></span> | <span data-ttu-id="429f0-124">Användarens huvudnamn (UPN) för det konto som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="429f0-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="429f0-125">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-125">string</span></span> | <span data-ttu-id="429f0-126">Visningsnamn för det konto som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="429f0-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="429f0-127">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-127">string</span></span> | <span data-ttu-id="429f0-128">Fullständigt kvalificerat domännamn (FQDN) för enheten som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="429f0-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="429f0-129">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-129">string</span></span> | <span data-ttu-id="429f0-130">Namn på den enhet som kör serverprogrammet som bearbetat den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="429f0-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="429f0-131">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-131">string</span></span> | <span data-ttu-id="429f0-132">IP-adress för den enhet som kör serverprogrammet som bearbetat den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="429f0-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="429f0-133">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-133">string</span></span> | <span data-ttu-id="429f0-134">Målport för aktiviteten</span><span class="sxs-lookup"><span data-stu-id="429f0-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="429f0-135">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-135">string</span></span> | <span data-ttu-id="429f0-136">Protokoll som används under kommunikationen</span><span class="sxs-lookup"><span data-stu-id="429f0-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="429f0-137">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-137">string</span></span> | <span data-ttu-id="429f0-138">Användarnamn för kontot</span><span class="sxs-lookup"><span data-stu-id="429f0-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="429f0-139">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-139">string</span></span> | <span data-ttu-id="429f0-140">Domän för kontot</span><span class="sxs-lookup"><span data-stu-id="429f0-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="429f0-141">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-141">string</span></span> | <span data-ttu-id="429f0-142">Användarkontons huvudnamn (UPN)</span><span class="sxs-lookup"><span data-stu-id="429f0-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="429f0-143">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-143">string</span></span> | <span data-ttu-id="429f0-144">Säkerhetsidentifierare (SID) för kontot</span><span class="sxs-lookup"><span data-stu-id="429f0-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="429f0-145">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-145">string</span></span> | <span data-ttu-id="429f0-146">Unikt ID för kontot i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="429f0-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="429f0-147">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-147">string</span></span> | <span data-ttu-id="429f0-148">Namnet på kontoanvändaren som visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="429f0-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="429f0-149">Detta är en kombination av ett visst namn eller förnamn, en mellaninititiering och efternamn eller efternamn.</span><span class="sxs-lookup"><span data-stu-id="429f0-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="429f0-150">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-150">string</span></span> | <span data-ttu-id="429f0-151">Fullständigt kvalificerat domännamn (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="429f0-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="429f0-152">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-152">string</span></span> | <span data-ttu-id="429f0-153">IP-adress tilldelad till enheten under kommunikation</span><span class="sxs-lookup"><span data-stu-id="429f0-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="429f0-154">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-154">string</span></span> | <span data-ttu-id="429f0-155">TCP-port som används under kommunikation</span><span class="sxs-lookup"><span data-stu-id="429f0-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="429f0-156">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-156">string</span></span> | <span data-ttu-id="429f0-157">Stad, land eller annan geografisk plats som är kopplad till händelsen</span><span class="sxs-lookup"><span data-stu-id="429f0-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="429f0-158">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-158">string</span></span> | <span data-ttu-id="429f0-159">Internetleverantör som är kopplad till IP-adressen</span><span class="sxs-lookup"><span data-stu-id="429f0-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="429f0-160">long</span><span class="sxs-lookup"><span data-stu-id="429f0-160">long</span></span> | <span data-ttu-id="429f0-161">Unikt ID för händelsen</span><span class="sxs-lookup"><span data-stu-id="429f0-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="429f0-162">sträng</span><span class="sxs-lookup"><span data-stu-id="429f0-162">string</span></span> | <span data-ttu-id="429f0-163">Ytterligare information om entiteten eller händelsen</span><span class="sxs-lookup"><span data-stu-id="429f0-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="429f0-164">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="429f0-164">Related topics</span></span>
- [<span data-ttu-id="429f0-165">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="429f0-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="429f0-166">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="429f0-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="429f0-167">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="429f0-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="429f0-168">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="429f0-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="429f0-169">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="429f0-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="429f0-170">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="429f0-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
