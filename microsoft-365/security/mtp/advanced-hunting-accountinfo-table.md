---
title: AccountInfo-tabellen i det avancerade jaktschemat
description: Läs mer om användarkontoinformation i tabellen AccountInfo i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, AlertInfo, alert, enheter, bevis, fil, IP-adress, enhet, maskin, användare, konto
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
ms.openlocfilehash: 9e4503ab297c7a584a548faa36ca6102c1b8dda6
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929534"
---
# <a name="accountinfo"></a><span data-ttu-id="a5010-104">KontoInfo</span><span class="sxs-lookup"><span data-stu-id="a5010-104">AccountInfo</span></span>

<span data-ttu-id="a5010-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="a5010-105">**Applies to:**</span></span>
- <span data-ttu-id="a5010-106">Microsofts hotskydd</span><span class="sxs-lookup"><span data-stu-id="a5010-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="a5010-107">Tabellen `AccountInfo` i det [avancerade jaktschemat](advanced-hunting-overview.md) innehåller information om användarkonton som hämtats från olika tjänster, inklusive Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a5010-107">The `AccountInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="a5010-108">Använd den här referensen om du vill skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="a5010-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="a5010-109">Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="a5010-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="a5010-110">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="a5010-110">Column name</span></span> | <span data-ttu-id="a5010-111">Datatyp</span><span class="sxs-lookup"><span data-stu-id="a5010-111">Data type</span></span> | <span data-ttu-id="a5010-112">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="a5010-112">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="a5010-113">Sträng</span><span class="sxs-lookup"><span data-stu-id="a5010-113">string</span></span> | <span data-ttu-id="a5010-114">Unik identifierare för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="a5010-114">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="a5010-115">Sträng</span><span class="sxs-lookup"><span data-stu-id="a5010-115">string</span></span> | <span data-ttu-id="a5010-116">Kontots användarnamn (UPN)</span><span class="sxs-lookup"><span data-stu-id="a5010-116">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="a5010-117">Sträng</span><span class="sxs-lookup"><span data-stu-id="a5010-117">string</span></span> | <span data-ttu-id="a5010-118">Sid-säkerhetsidentifierare (On-premises security identifier) för kontot</span><span class="sxs-lookup"><span data-stu-id="a5010-118">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="a5010-119">Sträng</span><span class="sxs-lookup"><span data-stu-id="a5010-119">string</span></span> | <span data-ttu-id="a5010-120">Molnsäkerhetsidentifierare för kontot</span><span class="sxs-lookup"><span data-stu-id="a5010-120">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="a5010-121">Sträng</span><span class="sxs-lookup"><span data-stu-id="a5010-121">string</span></span> | <span data-ttu-id="a5010-122">Kontoanvändarens förnamn eller förnamn</span><span class="sxs-lookup"><span data-stu-id="a5010-122">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="a5010-123">Sträng</span><span class="sxs-lookup"><span data-stu-id="a5010-123">string</span></span> | <span data-ttu-id="a5010-124">Kontoanvändarens efternamn, efternamn eller efternamn</span><span class="sxs-lookup"><span data-stu-id="a5010-124">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="a5010-125">Sträng</span><span class="sxs-lookup"><span data-stu-id="a5010-125">string</span></span> | <span data-ttu-id="a5010-126">Namn på den kontoanvändare som visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="a5010-126">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="a5010-127">Vanligtvis en kombination av ett givet eller förnamn, en mellaninitiering och ett efternamn eller efternamn.</span><span class="sxs-lookup"><span data-stu-id="a5010-127">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="a5010-128">Sträng</span><span class="sxs-lookup"><span data-stu-id="a5010-128">string</span></span> | <span data-ttu-id="a5010-129">Namn på den avdelning som kontoanvändaren tillhör</span><span class="sxs-lookup"><span data-stu-id="a5010-129">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="a5010-130">Sträng</span><span class="sxs-lookup"><span data-stu-id="a5010-130">string</span></span> | <span data-ttu-id="a5010-131">Befattning för kontoanvändaren</span><span class="sxs-lookup"><span data-stu-id="a5010-131">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="a5010-132">Sträng</span><span class="sxs-lookup"><span data-stu-id="a5010-132">string</span></span> | <span data-ttu-id="a5010-133">Kontots användarnamn</span><span class="sxs-lookup"><span data-stu-id="a5010-133">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="a5010-134">Sträng</span><span class="sxs-lookup"><span data-stu-id="a5010-134">string</span></span> | <span data-ttu-id="a5010-135">Kontots domän</span><span class="sxs-lookup"><span data-stu-id="a5010-135">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="a5010-136">Sträng</span><span class="sxs-lookup"><span data-stu-id="a5010-136">string</span></span> | <span data-ttu-id="a5010-137">SMTP-adressen för kontot</span><span class="sxs-lookup"><span data-stu-id="a5010-137">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="a5010-138">Sträng</span><span class="sxs-lookup"><span data-stu-id="a5010-138">string</span></span> | <span data-ttu-id="a5010-139">Röst för kontots ip-sessionsinitieringsprotokoll (VOIP) för kontot</span><span class="sxs-lookup"><span data-stu-id="a5010-139">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="a5010-140">Sträng</span><span class="sxs-lookup"><span data-stu-id="a5010-140">string</span></span> | <span data-ttu-id="a5010-141">Stad där kontoanvändaren finns</span><span class="sxs-lookup"><span data-stu-id="a5010-141">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="a5010-142">Sträng</span><span class="sxs-lookup"><span data-stu-id="a5010-142">string</span></span> | <span data-ttu-id="a5010-143">Land/region där kontoanvändaren finns</span><span class="sxs-lookup"><span data-stu-id="a5010-143">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="a5010-144">Boolean</span><span class="sxs-lookup"><span data-stu-id="a5010-144">boolean</span></span> | <span data-ttu-id="a5010-145">Anger om kontot är aktiverat eller inte</span><span class="sxs-lookup"><span data-stu-id="a5010-145">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="a5010-146">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="a5010-146">Related topics</span></span>
- [<span data-ttu-id="a5010-147">Proaktivt jakt efter hot</span><span class="sxs-lookup"><span data-stu-id="a5010-147">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="a5010-148">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="a5010-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="a5010-149">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="a5010-149">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="a5010-150">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="a5010-150">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="a5010-151">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="a5010-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="a5010-152">Tillämpa metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="a5010-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
