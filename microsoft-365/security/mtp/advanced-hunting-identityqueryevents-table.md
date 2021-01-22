---
title: Tabellen IdentityQueryEvents i det avancerade sökschemat
description: Läs mer om Active Directory-frågehändelser i tabellen IdentityQueryEvents i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identiteter, LDAP-frågor
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
ms.openlocfilehash: 7016127a75bca48103f5325ce169faa3d7c31c85
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929820"
---
# <a name="identityqueryevents"></a><span data-ttu-id="06493-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="06493-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="06493-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="06493-105">**Applies to:**</span></span>
- <span data-ttu-id="06493-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="06493-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="06493-107">Tabellen i det avancerade sökschemat innehåller information om frågor som utförs mot Active Directory-objekt, till exempel `IdentityQueryEvents` användare, grupper, enheter [](advanced-hunting-overview.md) och domäner.</span><span class="sxs-lookup"><span data-stu-id="06493-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="06493-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="06493-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="06493-109">Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` [inbyggda schemareferensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) som finns i säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="06493-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="06493-110">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="06493-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="06493-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="06493-111">Column name</span></span> | <span data-ttu-id="06493-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="06493-112">Data type</span></span> | <span data-ttu-id="06493-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="06493-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="06493-114">datetime</span><span class="sxs-lookup"><span data-stu-id="06493-114">datetime</span></span> | <span data-ttu-id="06493-115">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="06493-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="06493-116">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-116">string</span></span> | <span data-ttu-id="06493-117">Typ av aktivitet som utlöste händelsen.</span><span class="sxs-lookup"><span data-stu-id="06493-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="06493-118">Mer information [finns i referensen till portalschemat](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="06493-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="06493-119">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-119">string</span></span> | <span data-ttu-id="06493-120">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="06493-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="06493-121">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-121">string</span></span> | <span data-ttu-id="06493-122">Typ av fråga, till exempel QueryGroup, QueryUser eller EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="06493-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="06493-123">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-123">string</span></span> | <span data-ttu-id="06493-124">Namn på användare, grupp, enhet, domän eller någon annan entitetstyp som blir tillfrågad</span><span class="sxs-lookup"><span data-stu-id="06493-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="06493-125">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-125">string</span></span> | <span data-ttu-id="06493-126">Sträng som används för att köra frågan</span><span class="sxs-lookup"><span data-stu-id="06493-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="06493-127">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-127">string</span></span> | <span data-ttu-id="06493-128">Protokoll som används under kommunikationen</span><span class="sxs-lookup"><span data-stu-id="06493-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="06493-129">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-129">string</span></span> | <span data-ttu-id="06493-130">Användarnamn för kontot</span><span class="sxs-lookup"><span data-stu-id="06493-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="06493-131">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-131">string</span></span> | <span data-ttu-id="06493-132">Domänen för kontot</span><span class="sxs-lookup"><span data-stu-id="06493-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="06493-133">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-133">string</span></span> | <span data-ttu-id="06493-134">Kontots huvudnamn (UPN)</span><span class="sxs-lookup"><span data-stu-id="06493-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="06493-135">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-135">string</span></span> | <span data-ttu-id="06493-136">Säkerhetsidentifierare (SID) för kontot</span><span class="sxs-lookup"><span data-stu-id="06493-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="06493-137">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-137">string</span></span> | <span data-ttu-id="06493-138">Unikt ID för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="06493-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="06493-139">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-139">string</span></span> | <span data-ttu-id="06493-140">Namnet på kontoanvändaren som visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="06493-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="06493-141">Vanligtvis en kombination av ett visst namn eller förnamn, en mellaninititiering och ett efternamn eller efternamn.</span><span class="sxs-lookup"><span data-stu-id="06493-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="06493-142">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-142">string</span></span> | <span data-ttu-id="06493-143">Fullständigt kvalificerat domännamn (FQDN) för slutpunkten</span><span class="sxs-lookup"><span data-stu-id="06493-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="06493-144">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-144">string</span></span> | <span data-ttu-id="06493-145">IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="06493-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="06493-146">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-146">string</span></span> | <span data-ttu-id="06493-147">Namn på den enhet som kör serverprogrammet som hanterade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="06493-147">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="06493-148">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-148">string</span></span> | <span data-ttu-id="06493-149">IP-adressen för den enhet som kör serverprogrammet som hanterade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="06493-149">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="06493-150">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-150">string</span></span> | <span data-ttu-id="06493-151">Fullständigt kvalificerat domännamn (FQDN) för enheten som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="06493-151">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="06493-152">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-152">string</span></span> | <span data-ttu-id="06493-153">Användarens huvudnamn (UPN) för kontot som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="06493-153">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="06493-154">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-154">string</span></span> | <span data-ttu-id="06493-155">Visningsnamn för det konto som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="06493-155">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="06493-156">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-156">string</span></span> | <span data-ttu-id="06493-157">Stad, land eller annan geografisk plats som är kopplad till händelsen</span><span class="sxs-lookup"><span data-stu-id="06493-157">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="06493-158">long</span><span class="sxs-lookup"><span data-stu-id="06493-158">long</span></span> | <span data-ttu-id="06493-159">Unikt ID för händelsen</span><span class="sxs-lookup"><span data-stu-id="06493-159">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="06493-160">sträng</span><span class="sxs-lookup"><span data-stu-id="06493-160">string</span></span> | <span data-ttu-id="06493-161">Ytterligare information om entiteten eller händelsen</span><span class="sxs-lookup"><span data-stu-id="06493-161">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="06493-162">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="06493-162">Related topics</span></span>
- [<span data-ttu-id="06493-163">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="06493-163">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="06493-164">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="06493-164">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="06493-165">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="06493-165">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="06493-166">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="06493-166">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="06493-167">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="06493-167">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="06493-168">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="06493-168">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
