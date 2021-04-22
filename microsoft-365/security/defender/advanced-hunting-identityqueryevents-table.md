---
title: Tabellen IdentityQueryEvents i det avancerade sökschemat
description: Läs mer om Active Directory-frågehändelser i tabellen IdentityQueryEvents i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, Microsoft 365 Defender, microsoft 365, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, IdentityQueryEvents, Azure AD, Active Directory, Microsoft Defender för identitet, identiteter, LDAP-frågor
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
ms.openlocfilehash: 89f6f83112bc6bea57a3b5f7703353adb9d87a30
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935803"
---
# <a name="identityqueryevents"></a><span data-ttu-id="65594-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="65594-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="65594-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="65594-105">**Applies to:**</span></span>
- <span data-ttu-id="65594-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65594-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="65594-107">Tabellen i det avancerade sökschemat innehåller information om frågor som utförs mot Active Directory-objekt, till exempel `IdentityQueryEvents` användare, grupper, enheter [](advanced-hunting-overview.md) och domäner.</span><span class="sxs-lookup"><span data-stu-id="65594-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="65594-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="65594-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="65594-109">Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` inbyggda schemareferensen som finns i säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="65594-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="65594-110">Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="65594-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="65594-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="65594-111">Column name</span></span> | <span data-ttu-id="65594-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="65594-112">Data type</span></span> | <span data-ttu-id="65594-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="65594-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="65594-114">datetime</span><span class="sxs-lookup"><span data-stu-id="65594-114">datetime</span></span> | <span data-ttu-id="65594-115">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="65594-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="65594-116">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-116">string</span></span> | <span data-ttu-id="65594-117">Typ av aktivitet som utlöste händelsen.</span><span class="sxs-lookup"><span data-stu-id="65594-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="65594-118">Mer information [finns i schemareferensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i portalen</span><span class="sxs-lookup"><span data-stu-id="65594-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="65594-119">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-119">string</span></span> | <span data-ttu-id="65594-120">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="65594-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="65594-121">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-121">string</span></span> | <span data-ttu-id="65594-122">Typ av fråga, till exempel QueryGroup, QueryUser eller EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="65594-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="65594-123">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-123">string</span></span> | <span data-ttu-id="65594-124">Namnet på användaren, gruppen, enheten, domänen eller någon annan enhetstyp som blir frågad</span><span class="sxs-lookup"><span data-stu-id="65594-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="65594-125">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-125">string</span></span> | <span data-ttu-id="65594-126">Sträng som används för att köra frågan</span><span class="sxs-lookup"><span data-stu-id="65594-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="65594-127">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-127">string</span></span> | <span data-ttu-id="65594-128">Protokoll som används under kommunikationen</span><span class="sxs-lookup"><span data-stu-id="65594-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="65594-129">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-129">string</span></span> | <span data-ttu-id="65594-130">Användarnamn för kontot</span><span class="sxs-lookup"><span data-stu-id="65594-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="65594-131">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-131">string</span></span> | <span data-ttu-id="65594-132">Domän för kontot</span><span class="sxs-lookup"><span data-stu-id="65594-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="65594-133">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-133">string</span></span> | <span data-ttu-id="65594-134">Användarkontons huvudnamn (UPN)</span><span class="sxs-lookup"><span data-stu-id="65594-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="65594-135">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-135">string</span></span> | <span data-ttu-id="65594-136">Säkerhetsidentifierare (SID) för kontot</span><span class="sxs-lookup"><span data-stu-id="65594-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="65594-137">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-137">string</span></span> | <span data-ttu-id="65594-138">Unikt ID för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="65594-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="65594-139">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-139">string</span></span> | <span data-ttu-id="65594-140">Namnet på kontoanvändaren som visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="65594-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="65594-141">Detta är en kombination av ett visst namn eller förnamn, en mellaninititiering och efternamn eller efternamn.</span><span class="sxs-lookup"><span data-stu-id="65594-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="65594-142">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-142">string</span></span> | <span data-ttu-id="65594-143">Fullständigt kvalificerat domännamn (FQDN) för slutpunkten</span><span class="sxs-lookup"><span data-stu-id="65594-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="65594-144">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-144">string</span></span> | <span data-ttu-id="65594-145">IP-adress tilldelad till slutpunkten och används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="65594-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Port` | <span data-ttu-id="65594-146">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-146">string</span></span> | <span data-ttu-id="65594-147">TCP-port som används under kommunikation</span><span class="sxs-lookup"><span data-stu-id="65594-147">TCP port used during communication</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="65594-148">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-148">string</span></span> | <span data-ttu-id="65594-149">Namn på den enhet som kör serverprogrammet som bearbetat den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="65594-149">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="65594-150">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-150">string</span></span> | <span data-ttu-id="65594-151">IP-adress för den enhet som kör serverprogrammet som bearbetat den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="65594-151">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="65594-152">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-152">string</span></span> | <span data-ttu-id="65594-153">Målport för relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="65594-153">Destination port of related network communications</span></span> |
| `TargetDeviceName` | <span data-ttu-id="65594-154">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-154">string</span></span> | <span data-ttu-id="65594-155">Fullständigt kvalificerat domännamn (FQDN) för enheten som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="65594-155">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="65594-156">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-156">string</span></span> | <span data-ttu-id="65594-157">Användarens huvudnamn (UPN) för det konto som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="65594-157">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="65594-158">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-158">string</span></span> | <span data-ttu-id="65594-159">Visningsnamn för det konto som den inspelade åtgärden tillämpats på</span><span class="sxs-lookup"><span data-stu-id="65594-159">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="65594-160">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-160">string</span></span> | <span data-ttu-id="65594-161">Stad, land eller annan geografisk plats som är kopplad till händelsen</span><span class="sxs-lookup"><span data-stu-id="65594-161">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="65594-162">long</span><span class="sxs-lookup"><span data-stu-id="65594-162">long</span></span> | <span data-ttu-id="65594-163">Unikt ID för händelsen</span><span class="sxs-lookup"><span data-stu-id="65594-163">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="65594-164">sträng</span><span class="sxs-lookup"><span data-stu-id="65594-164">string</span></span> | <span data-ttu-id="65594-165">Ytterligare information om entiteten eller händelsen</span><span class="sxs-lookup"><span data-stu-id="65594-165">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="65594-166">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="65594-166">Related topics</span></span>
- [<span data-ttu-id="65594-167">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="65594-167">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="65594-168">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="65594-168">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="65594-169">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="65594-169">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="65594-170">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="65594-170">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="65594-171">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="65594-171">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="65594-172">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="65594-172">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
