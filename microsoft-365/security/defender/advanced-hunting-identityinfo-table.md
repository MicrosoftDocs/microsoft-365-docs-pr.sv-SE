---
title: IdentityInfo-tabell i det avancerade sökschemat
description: Mer information om användarkonton finns i tabellen IdentityInfo i det avancerade sökschemat
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, AccountInfo, IdentityInfo, account
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
ms.openlocfilehash: ce1a3d5153d324d008d2d46048838351eb7bc047
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935827"
---
# <a name="identityinfo"></a><span data-ttu-id="bb7cf-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="bb7cf-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bb7cf-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="bb7cf-105">**Applies to:**</span></span>
- <span data-ttu-id="bb7cf-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bb7cf-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bb7cf-107">Tabellen `IdentityInfo` i det avancerade [sökschemat](advanced-hunting-overview.md) innehåller information om användarkonton från olika tjänster, bland annat Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bb7cf-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="bb7cf-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="bb7cf-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="bb7cf-109">Den här tabellen har bytt namn från `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="bb7cf-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="bb7cf-110">Vid namnbyte uppdateras automatiskt alla frågor som sparas i portalen.</span><span class="sxs-lookup"><span data-stu-id="bb7cf-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="bb7cf-111">Kontrollera frågor som du har sparat någon annanstans.</span><span class="sxs-lookup"><span data-stu-id="bb7cf-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="bb7cf-112">Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="bb7cf-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="bb7cf-113">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="bb7cf-113">Column name</span></span> | <span data-ttu-id="bb7cf-114">Datatyp</span><span class="sxs-lookup"><span data-stu-id="bb7cf-114">Data type</span></span> | <span data-ttu-id="bb7cf-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="bb7cf-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="bb7cf-116">sträng</span><span class="sxs-lookup"><span data-stu-id="bb7cf-116">string</span></span> | <span data-ttu-id="bb7cf-117">Unikt ID för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="bb7cf-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="bb7cf-118">sträng</span><span class="sxs-lookup"><span data-stu-id="bb7cf-118">string</span></span> | <span data-ttu-id="bb7cf-119">Användarkontons huvudnamn (UPN)</span><span class="sxs-lookup"><span data-stu-id="bb7cf-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="bb7cf-120">sträng</span><span class="sxs-lookup"><span data-stu-id="bb7cf-120">string</span></span> | <span data-ttu-id="bb7cf-121">Sid för kontots lokala säkerhetsidentifierare</span><span class="sxs-lookup"><span data-stu-id="bb7cf-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="bb7cf-122">sträng</span><span class="sxs-lookup"><span data-stu-id="bb7cf-122">string</span></span> | <span data-ttu-id="bb7cf-123">Molnsäkerhetsidentifierare för kontot</span><span class="sxs-lookup"><span data-stu-id="bb7cf-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="bb7cf-124">sträng</span><span class="sxs-lookup"><span data-stu-id="bb7cf-124">string</span></span> | <span data-ttu-id="bb7cf-125">Användarens förnamn eller förnamn</span><span class="sxs-lookup"><span data-stu-id="bb7cf-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="bb7cf-126">sträng</span><span class="sxs-lookup"><span data-stu-id="bb7cf-126">string</span></span> | <span data-ttu-id="bb7cf-127">Efternamn, kontoanvändares efternamn eller efternamn</span><span class="sxs-lookup"><span data-stu-id="bb7cf-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="bb7cf-128">sträng</span><span class="sxs-lookup"><span data-stu-id="bb7cf-128">string</span></span> | <span data-ttu-id="bb7cf-129">Namnet på kontoanvändaren som visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="bb7cf-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="bb7cf-130">Detta är en kombination av ett visst namn eller förnamn, en mellaninititiering och efternamn eller efternamn.</span><span class="sxs-lookup"><span data-stu-id="bb7cf-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="bb7cf-131">sträng</span><span class="sxs-lookup"><span data-stu-id="bb7cf-131">string</span></span> | <span data-ttu-id="bb7cf-132">Namn på avdelningen som kontoanvändaren tillhör</span><span class="sxs-lookup"><span data-stu-id="bb7cf-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="bb7cf-133">sträng</span><span class="sxs-lookup"><span data-stu-id="bb7cf-133">string</span></span> | <span data-ttu-id="bb7cf-134">Befattning för kontoanvändaren</span><span class="sxs-lookup"><span data-stu-id="bb7cf-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="bb7cf-135">sträng</span><span class="sxs-lookup"><span data-stu-id="bb7cf-135">string</span></span> | <span data-ttu-id="bb7cf-136">Användarnamn för kontot</span><span class="sxs-lookup"><span data-stu-id="bb7cf-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="bb7cf-137">sträng</span><span class="sxs-lookup"><span data-stu-id="bb7cf-137">string</span></span> | <span data-ttu-id="bb7cf-138">Domän för kontot</span><span class="sxs-lookup"><span data-stu-id="bb7cf-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="bb7cf-139">sträng</span><span class="sxs-lookup"><span data-stu-id="bb7cf-139">string</span></span> | <span data-ttu-id="bb7cf-140">SMTP-adressen för kontot</span><span class="sxs-lookup"><span data-stu-id="bb7cf-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="bb7cf-141">sträng</span><span class="sxs-lookup"><span data-stu-id="bb7cf-141">string</span></span> | <span data-ttu-id="bb7cf-142">Kontots startprotokoll för Voice over IP (VOIP) session initiation protocol (SIP)</span><span class="sxs-lookup"><span data-stu-id="bb7cf-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="bb7cf-143">sträng</span><span class="sxs-lookup"><span data-stu-id="bb7cf-143">string</span></span> | <span data-ttu-id="bb7cf-144">Ort där kontoanvändaren finns</span><span class="sxs-lookup"><span data-stu-id="bb7cf-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="bb7cf-145">sträng</span><span class="sxs-lookup"><span data-stu-id="bb7cf-145">string</span></span> | <span data-ttu-id="bb7cf-146">Land/region där kontoanvändaren finns</span><span class="sxs-lookup"><span data-stu-id="bb7cf-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="bb7cf-147">boolesk</span><span class="sxs-lookup"><span data-stu-id="bb7cf-147">boolean</span></span> | <span data-ttu-id="bb7cf-148">Anger om kontot är aktiverat eller inte</span><span class="sxs-lookup"><span data-stu-id="bb7cf-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="bb7cf-149">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="bb7cf-149">Related topics</span></span>
- [<span data-ttu-id="bb7cf-150">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="bb7cf-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bb7cf-151">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="bb7cf-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="bb7cf-152">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="bb7cf-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="bb7cf-153">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="bb7cf-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="bb7cf-154">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="bb7cf-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="bb7cf-155">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="bb7cf-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
