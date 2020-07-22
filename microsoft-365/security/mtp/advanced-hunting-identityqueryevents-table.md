---
title: IdentityQueryEvents-tabellen i det avancerade jaktschemat
description: Lär dig mer om Active Directory-frågehändelser i tabellen IdentityQueryEvents i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, IdentityQueryEvents, Azure AD, Active Directory, Azure ATP, identiteter, LDAP-frågor
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 436c4d7306f9f5febd614489090a0a10929ba3c9
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204881"
---
# <a name="identityqueryevents"></a><span data-ttu-id="0745d-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="0745d-104">IdentityQueryEvents</span></span>

<span data-ttu-id="0745d-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="0745d-105">**Applies to:**</span></span>
- <span data-ttu-id="0745d-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="0745d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="0745d-107">`IdentityQueryEvents`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om frågor som utförs mot Active Directory-objekt, till exempel användare, grupper, enheter och domäner.</span><span class="sxs-lookup"><span data-stu-id="0745d-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="0745d-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="0745d-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="0745d-109">Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0745d-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0745d-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="0745d-110">Column name</span></span> | <span data-ttu-id="0745d-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="0745d-111">Data type</span></span> | <span data-ttu-id="0745d-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0745d-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0745d-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="0745d-113">datetime</span></span> | <span data-ttu-id="0745d-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="0745d-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="0745d-115">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-115">string</span></span> | <span data-ttu-id="0745d-116">Typ av aktivitet som utlöste händelsen</span><span class="sxs-lookup"><span data-stu-id="0745d-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="0745d-117">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-117">string</span></span> | <span data-ttu-id="0745d-118">Ansökan som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="0745d-118">Application that performed the recorded action</span></span> |
| `QueryType` | <span data-ttu-id="0745d-119">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-119">string</span></span> | <span data-ttu-id="0745d-120">Typ av fråga, till exempel QueryGroup, QueryUser eller UppräkningAnvändare</span><span class="sxs-lookup"><span data-stu-id="0745d-120">Type of query, such as QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryTarget` | <span data-ttu-id="0745d-121">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-121">string</span></span> | <span data-ttu-id="0745d-122">Namn på användare, grupp, enhet, domän eller någon annan entitetstyp som efterfrågas</span><span class="sxs-lookup"><span data-stu-id="0745d-122">Name of user, group, device, domain, or any other entity type being queried</span></span> |
| `Query` | <span data-ttu-id="0745d-123">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-123">string</span></span> | <span data-ttu-id="0745d-124">Sträng som används för att köra frågan</span><span class="sxs-lookup"><span data-stu-id="0745d-124">String used to run the query</span></span> |
| `Protocol` | <span data-ttu-id="0745d-125">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-125">string</span></span> | <span data-ttu-id="0745d-126">Protokoll som används under kommunikationen</span><span class="sxs-lookup"><span data-stu-id="0745d-126">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="0745d-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-127">string</span></span> | <span data-ttu-id="0745d-128">Kontots användarnamn</span><span class="sxs-lookup"><span data-stu-id="0745d-128">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="0745d-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-129">string</span></span> | <span data-ttu-id="0745d-130">Kontots domän</span><span class="sxs-lookup"><span data-stu-id="0745d-130">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="0745d-131">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-131">string</span></span> | <span data-ttu-id="0745d-132">Användarens huvudnamn (UPN) för kontot</span><span class="sxs-lookup"><span data-stu-id="0745d-132">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="0745d-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-133">string</span></span> | <span data-ttu-id="0745d-134">Säkerhetsidentifierare (SID) för kontot</span><span class="sxs-lookup"><span data-stu-id="0745d-134">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="0745d-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-135">string</span></span> | <span data-ttu-id="0745d-136">Unik identifierare för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="0745d-136">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="0745d-137">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-137">string</span></span> | <span data-ttu-id="0745d-138">Namn på den kontoanvändare som visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="0745d-138">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="0745d-139">Vanligtvis en kombination av ett givet eller förnamn, en mellaninitiering och ett efternamn eller efternamn.</span><span class="sxs-lookup"><span data-stu-id="0745d-139">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="0745d-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-140">string</span></span> | <span data-ttu-id="0745d-141">Fullständigt kvalificerat domännamn (FQDN) för slutpunkten</span><span class="sxs-lookup"><span data-stu-id="0745d-141">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="0745d-142">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-142">string</span></span> | <span data-ttu-id="0745d-143">IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="0745d-143">IP address assigned to the endpoint and used during related network communications</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="0745d-144">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-144">string</span></span> | <span data-ttu-id="0745d-145">Namn på den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="0745d-145">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="0745d-146">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-146">string</span></span> | <span data-ttu-id="0745d-147">IP-adressen för den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="0745d-147">IP address of the device running the server application that processed the recorded action</span></span> |
| `TargetDeviceName` | <span data-ttu-id="0745d-148">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-148">string</span></span> | <span data-ttu-id="0745d-149">Fullständigt kvalificerat domännamn (FQDN) för den enhet som den registrerade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="0745d-149">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="0745d-150">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-150">string</span></span> | <span data-ttu-id="0745d-151">Användarens huvudnamn (UPN) för det konto som den registrerade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="0745d-151">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="0745d-152">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-152">string</span></span> | <span data-ttu-id="0745d-153">Visa namnet på det konto som den registrerade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="0745d-153">Display name of the account that the recorded action was applied to</span></span> |
| `Location` | <span data-ttu-id="0745d-154">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-154">string</span></span> | <span data-ttu-id="0745d-155">Ort, land eller annan geografisk plats som är associerad med händelsen</span><span class="sxs-lookup"><span data-stu-id="0745d-155">City, country, or other geographic location associated with the event</span></span> |
| `ReportId` | <span data-ttu-id="0745d-156">Lång</span><span class="sxs-lookup"><span data-stu-id="0745d-156">long</span></span> | <span data-ttu-id="0745d-157">Unik identifierare för händelsen</span><span class="sxs-lookup"><span data-stu-id="0745d-157">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="0745d-158">Sträng</span><span class="sxs-lookup"><span data-stu-id="0745d-158">string</span></span> | <span data-ttu-id="0745d-159">Ytterligare information om entiteten eller händelsen</span><span class="sxs-lookup"><span data-stu-id="0745d-159">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0745d-160">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="0745d-160">Related topics</span></span>
- [<span data-ttu-id="0745d-161">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="0745d-161">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0745d-162">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="0745d-162">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0745d-163">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="0745d-163">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0745d-164">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="0745d-164">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0745d-165">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="0745d-165">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0745d-166">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="0745d-166">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
