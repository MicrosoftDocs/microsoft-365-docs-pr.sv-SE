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
ms.openlocfilehash: bec7f13d49e2ccf4e3a9121d5e5a2fecd1b10aa2
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899119"
---
# <a name="identityqueryevents"></a><span data-ttu-id="0fe5e-104">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="0fe5e-104">IdentityQueryEvents</span></span>

<span data-ttu-id="0fe5e-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="0fe5e-105">**Applies to:**</span></span>
- <span data-ttu-id="0fe5e-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="0fe5e-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="0fe5e-107">`IdentityQueryEvents`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om frågor som utförs mot Active Directory-objekt, till exempel användare, grupper, enheter och domäner.</span><span class="sxs-lookup"><span data-stu-id="0fe5e-107">The `IdentityQueryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about queries performed against Active Directory objects, such as users, groups, devices, and domains.</span></span> <span data-ttu-id="0fe5e-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="0fe5e-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="0fe5e-109">Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0fe5e-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0fe5e-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="0fe5e-110">Column name</span></span> | <span data-ttu-id="0fe5e-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="0fe5e-111">Data type</span></span> | <span data-ttu-id="0fe5e-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0fe5e-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="0fe5e-113">Datetime</span><span class="sxs-lookup"><span data-stu-id="0fe5e-113">datetime</span></span> | <span data-ttu-id="0fe5e-114">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="0fe5e-114">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="0fe5e-115">Sträng</span><span class="sxs-lookup"><span data-stu-id="0fe5e-115">string</span></span> | <span data-ttu-id="0fe5e-116">Typ av aktivitet som utlöste händelsen</span><span class="sxs-lookup"><span data-stu-id="0fe5e-116">Type of activity that triggered the event</span></span> |
| `Application` | <span data-ttu-id="0fe5e-117">Sträng</span><span class="sxs-lookup"><span data-stu-id="0fe5e-117">string</span></span> | <span data-ttu-id="0fe5e-118">Ansökan som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="0fe5e-118">Application that performed the recorded action</span></span> |
| `Query` | <span data-ttu-id="0fe5e-119">Sträng</span><span class="sxs-lookup"><span data-stu-id="0fe5e-119">string</span></span> | <span data-ttu-id="0fe5e-120">Typ av fråga: QueryGroup, QueryUser eller UppräkningAnvändare</span><span class="sxs-lookup"><span data-stu-id="0fe5e-120">Type of query: QueryGroup, QueryUser, or EnumerateUsers</span></span> |
| `QueryObject` | <span data-ttu-id="0fe5e-121">Sträng</span><span class="sxs-lookup"><span data-stu-id="0fe5e-121">string</span></span> | <span data-ttu-id="0fe5e-122">Namn på den användare, grupp, enhet, domän eller någon annan entitetstyp som efterfrågas</span><span class="sxs-lookup"><span data-stu-id="0fe5e-122">Name of the user, group, device, domain, or any other entity type being queried</span></span> |
| `Protocol` | <span data-ttu-id="0fe5e-123">Sträng</span><span class="sxs-lookup"><span data-stu-id="0fe5e-123">string</span></span> | <span data-ttu-id="0fe5e-124">Protokoll som används under kommunikationen</span><span class="sxs-lookup"><span data-stu-id="0fe5e-124">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="0fe5e-125">Sträng</span><span class="sxs-lookup"><span data-stu-id="0fe5e-125">string</span></span> | <span data-ttu-id="0fe5e-126">Kontots användarnamn</span><span class="sxs-lookup"><span data-stu-id="0fe5e-126">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="0fe5e-127">Sträng</span><span class="sxs-lookup"><span data-stu-id="0fe5e-127">string</span></span> | <span data-ttu-id="0fe5e-128">Kontots domän</span><span class="sxs-lookup"><span data-stu-id="0fe5e-128">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="0fe5e-129">Sträng</span><span class="sxs-lookup"><span data-stu-id="0fe5e-129">string</span></span> | <span data-ttu-id="0fe5e-130">Användarens huvudnamn (UPN) för kontot</span><span class="sxs-lookup"><span data-stu-id="0fe5e-130">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="0fe5e-131">Sträng</span><span class="sxs-lookup"><span data-stu-id="0fe5e-131">string</span></span> | <span data-ttu-id="0fe5e-132">Säkerhetsidentifierare (SID) för kontot</span><span class="sxs-lookup"><span data-stu-id="0fe5e-132">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="0fe5e-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="0fe5e-133">string</span></span> | <span data-ttu-id="0fe5e-134">Unik identifierare för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="0fe5e-134">Unique identifier for the account in Azure AD</span></span> |
| `AccountDisplayName` | <span data-ttu-id="0fe5e-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="0fe5e-135">string</span></span> | <span data-ttu-id="0fe5e-136">Namn på den kontoanvändare som visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="0fe5e-136">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="0fe5e-137">Vanligtvis en kombination av ett givet eller förnamn, en mellaninitiering och ett efternamn eller efternamn.</span><span class="sxs-lookup"><span data-stu-id="0fe5e-137">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="0fe5e-138">Sträng</span><span class="sxs-lookup"><span data-stu-id="0fe5e-138">string</span></span> | <span data-ttu-id="0fe5e-139">Fullständigt kvalificerat domännamn (FQDN) för slutpunkten</span><span class="sxs-lookup"><span data-stu-id="0fe5e-139">Fully qualified domain name (FQDN) of the endpoint</span></span> |
| `IPAddress` | <span data-ttu-id="0fe5e-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="0fe5e-140">string</span></span> | <span data-ttu-id="0fe5e-141">IP-adress som tilldelats slutpunkten och som används under relaterad nätverkskommunikation</span><span class="sxs-lookup"><span data-stu-id="0fe5e-141">IP address assigned to the endpoint and used during related network communications</span></span> |
| `Location` | <span data-ttu-id="0fe5e-142">Sträng</span><span class="sxs-lookup"><span data-stu-id="0fe5e-142">string</span></span> | <span data-ttu-id="0fe5e-143">Ort, land eller annan geografisk plats som är associerad med händelsen</span><span class="sxs-lookup"><span data-stu-id="0fe5e-143">City, country, or other geographic location associated with the event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0fe5e-144">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="0fe5e-144">Related topics</span></span>
- [<span data-ttu-id="0fe5e-145">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="0fe5e-145">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0fe5e-146">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="0fe5e-146">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0fe5e-147">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="0fe5e-147">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0fe5e-148">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="0fe5e-148">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0fe5e-149">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="0fe5e-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0fe5e-150">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="0fe5e-150">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
