---
title: IdentityQueryEvents-tabell i det avancerade jakt-schemat
description: Lär dig mer om Active Directory-frågegrupper i tabellen IdentityQueryEvents för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identiteter, LDAP-frågor
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
ms.openlocfilehash: 2b163dc39e56c82ef177b71d197c431c744b12d7
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847410"
---
# <a name="identityqueryevents"></a><span data-ttu-id="3f1b7-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="3f1b7-104">IdentityQueryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3f1b7-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="3f1b7-105">**Applies to:**</span></span>
- <span data-ttu-id="3f1b7-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3f1b7-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3f1b7-107">`IdentityQueryEvents`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om frågor som gjorts mot Active Directory-objekt, till exempel användare, grupper, enheter och domäner.</span><span class="sxs-lookup"><span data-stu-id="3f1b7-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="3f1b7-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="3f1b7-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="3f1b7-109">Detaljerad information om de händelse typer ( `ActionType` värden) som stöds av en tabell finns i den [inbyggda schema referensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="3f1b7-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="3f1b7-110">Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="3f1b7-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3f1b7-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="3f1b7-111">Column name</span></span> | <span data-ttu-id="3f1b7-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="3f1b7-112">Data type</span></span> | <span data-ttu-id="3f1b7-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3f1b7-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="3f1b7-114">datetime</span><span class="sxs-lookup"><span data-stu-id="3f1b7-114">datetime</span></span> | <span data-ttu-id="3f1b7-115">Datum och tid när händelsen registrerades</span><span class="sxs-lookup"><span data-stu-id="3f1b7-115">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="3f1b7-116">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-116">string</span></span> | <span data-ttu-id="3f1b7-117">Typ av aktivitet som utlöste händelsen.</span><span class="sxs-lookup"><span data-stu-id="3f1b7-117">Type of activity that triggered the event.</span></span> <span data-ttu-id="3f1b7-118">Mer information finns [i referens för in-Portal schema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="3f1b7-118">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="3f1b7-119">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-119">string</span></span> | <span data-ttu-id="3f1b7-120">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="3f1b7-120">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="3f1b7-121">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-121">string</span></span> | <span data-ttu-id="3f1b7-122">Typ av fråga, till exempel QueryGroup, QueryUser eller EnumerateUsers</span><span class="sxs-lookup"><span data-stu-id="3f1b7-122">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="3f1b7-123">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-123">string</span></span> | <span data-ttu-id="3f1b7-124">Namn på användare, grupp, enhet, domän eller annan entitetstyp som frågas</span><span class="sxs-lookup"><span data-stu-id="3f1b7-124">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="3f1b7-125">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-125">string</span></span> | <span data-ttu-id="3f1b7-126">Sträng som används för att köra frågan</span><span class="sxs-lookup"><span data-stu-id="3f1b7-126">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="3f1b7-127">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-127">string</span></span> | <span data-ttu-id="3f1b7-128">Protokoll som används under kommunikationen</span><span class="sxs-lookup"><span data-stu-id="3f1b7-128">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="3f1b7-129">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-129">string</span></span> | <span data-ttu-id="3f1b7-130">Kontots användar namn</span><span class="sxs-lookup"><span data-stu-id="3f1b7-130">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="3f1b7-131">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-131">string</span></span> | <span data-ttu-id="3f1b7-132">Kontots domän</span><span class="sxs-lookup"><span data-stu-id="3f1b7-132">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="3f1b7-133">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-133">string</span></span> | <span data-ttu-id="3f1b7-134">Kontots huvud namn (UPN)</span><span class="sxs-lookup"><span data-stu-id="3f1b7-134">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="3f1b7-135">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-135">string</span></span> | <span data-ttu-id="3f1b7-136">Kontots säkerhets identifierare (SID)</span><span class="sxs-lookup"><span data-stu-id="3f1b7-136">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="3f1b7-137">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-137">string</span></span> | <span data-ttu-id="3f1b7-138">Unik identifierare för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="3f1b7-138">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="3f1b7-139">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-139">string</span></span> | <span data-ttu-id="3f1b7-140">Namnet på kontot som visas i adress boken.</span><span class="sxs-lookup"><span data-stu-id="3f1b7-140">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="3f1b7-141">Vanligt vis en kombination av ett visst eller förnamn, en mellan initiering och ett efter namn eller från gång.</span><span class="sxs-lookup"><span data-stu-id="3f1b7-141">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="3f1b7-142">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-142">string</span></span> | <span data-ttu-id="3f1b7-143">Slut punktens fullständiga domän namn (FQDN)</span><span class="sxs-lookup"><span data-stu-id="3f1b7-143">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="3f1b7-144">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-144">string</span></span> | <span data-ttu-id="3f1b7-145">IP-adress tilldelad till slut punkten och används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="3f1b7-145">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="3f1b7-146">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-146">string</span></span> | <span data-ttu-id="3f1b7-147">Namn på den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="3f1b7-147">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="3f1b7-148">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-148">string</span></span> | <span data-ttu-id="3f1b7-149">IP-adress för enheten som kör serverprogrammet som bearbetade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="3f1b7-149">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="3f1b7-150">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-150">string</span></span> | <span data-ttu-id="3f1b7-151">Det fullständigt kvalificerade domän namnet (FQDN) för enheten som den inspelade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="3f1b7-151">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="3f1b7-152">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-152">string</span></span> | <span data-ttu-id="3f1b7-153">Användarens huvud namn (UPN) för det konto som den inspelade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="3f1b7-153">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="3f1b7-154">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-154">string</span></span> | <span data-ttu-id="3f1b7-155">Visnings namn för det konto som den inspelade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="3f1b7-155">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="3f1b7-156">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-156">string</span></span> | <span data-ttu-id="3f1b7-157">Ort, land eller annan geografisk plats som är kopplad till evenemanget</span><span class="sxs-lookup"><span data-stu-id="3f1b7-157">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="3f1b7-158">tids</span><span class="sxs-lookup"><span data-stu-id="3f1b7-158">long</span></span> | <span data-ttu-id="3f1b7-159">Unik identifierare för händelsen</span><span class="sxs-lookup"><span data-stu-id="3f1b7-159">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="3f1b7-160">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="3f1b7-160">string</span></span> | <span data-ttu-id="3f1b7-161">Ytterligare information om enheten eller händelsen</span><span class="sxs-lookup"><span data-stu-id="3f1b7-161">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="3f1b7-162">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="3f1b7-162">Related topics</span></span>
- [<span data-ttu-id="3f1b7-163">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="3f1b7-163">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3f1b7-164">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="3f1b7-164">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3f1b7-165">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="3f1b7-165">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3f1b7-166">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="3f1b7-166">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3f1b7-167">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="3f1b7-167">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3f1b7-168">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="3f1b7-168">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
