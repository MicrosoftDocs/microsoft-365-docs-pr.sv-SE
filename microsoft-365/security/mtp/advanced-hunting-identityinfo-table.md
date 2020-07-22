---
title: IdentityInfo-tabellen i det avancerade jaktschemat
description: Läs mer om användarkontoinformation i tabellen IdentityInfo i det avancerade jaktschemat
keywords: avancerad jakt, hotjakt, cyberhotjakt, microsoft threat protection, microsoft 365, mtp, m365, sök, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, AccountInfo, IdentityInfo, konto
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
ms.openlocfilehash: e922fc7930d645a7024a0ffc73359277c4b637e4
ms.sourcegitcommit: b4119682bd3c036289e851fff56fde869c816479
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/22/2020
ms.locfileid: "45204929"
---
# <a name="identityinfo"></a><span data-ttu-id="0ad9d-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="0ad9d-104">IdentityInfo</span></span>

<span data-ttu-id="0ad9d-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="0ad9d-105">**Applies to:**</span></span>
- <span data-ttu-id="0ad9d-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="0ad9d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="0ad9d-107">`IdentityInfo`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om användarkonton som hämtats från olika tjänster, inklusive Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="0ad9d-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="0ad9d-109">Den här tabellen har bytt namn från `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="0ad9d-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="0ad9d-110">Under namnbyten uppdateras alla frågor som sparats i portalen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="0ad9d-111">Kontrollera frågor som du har sparat någon annanstans.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="0ad9d-112">Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0ad9d-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0ad9d-113">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="0ad9d-113">Column name</span></span> | <span data-ttu-id="0ad9d-114">Datatyp</span><span class="sxs-lookup"><span data-stu-id="0ad9d-114">Data type</span></span> | <span data-ttu-id="0ad9d-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0ad9d-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="0ad9d-116">Sträng</span><span class="sxs-lookup"><span data-stu-id="0ad9d-116">string</span></span> | <span data-ttu-id="0ad9d-117">Unik identifierare för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="0ad9d-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="0ad9d-118">Sträng</span><span class="sxs-lookup"><span data-stu-id="0ad9d-118">string</span></span> | <span data-ttu-id="0ad9d-119">Användarens huvudnamn (UPN) för kontot</span><span class="sxs-lookup"><span data-stu-id="0ad9d-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="0ad9d-120">Sträng</span><span class="sxs-lookup"><span data-stu-id="0ad9d-120">string</span></span> | <span data-ttu-id="0ad9d-121">Sid-säkerhetsidentifierare (On-premises security identifier) för kontot</span><span class="sxs-lookup"><span data-stu-id="0ad9d-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="0ad9d-122">Sträng</span><span class="sxs-lookup"><span data-stu-id="0ad9d-122">string</span></span> | <span data-ttu-id="0ad9d-123">Molnsäkerhetsidentifierare för kontot</span><span class="sxs-lookup"><span data-stu-id="0ad9d-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="0ad9d-124">Sträng</span><span class="sxs-lookup"><span data-stu-id="0ad9d-124">string</span></span> | <span data-ttu-id="0ad9d-125">Kontoanvändarens förnamn eller förnamn</span><span class="sxs-lookup"><span data-stu-id="0ad9d-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="0ad9d-126">Sträng</span><span class="sxs-lookup"><span data-stu-id="0ad9d-126">string</span></span> | <span data-ttu-id="0ad9d-127">Kontoanvändarens efternamn, efternamn eller efternamn</span><span class="sxs-lookup"><span data-stu-id="0ad9d-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="0ad9d-128">Sträng</span><span class="sxs-lookup"><span data-stu-id="0ad9d-128">string</span></span> | <span data-ttu-id="0ad9d-129">Namn på den kontoanvändare som visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="0ad9d-130">Vanligtvis en kombination av ett givet eller förnamn, en mellaninitiering och ett efternamn eller efternamn.</span><span class="sxs-lookup"><span data-stu-id="0ad9d-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="0ad9d-131">Sträng</span><span class="sxs-lookup"><span data-stu-id="0ad9d-131">string</span></span> | <span data-ttu-id="0ad9d-132">Namn på den avdelning som kontoanvändaren tillhör</span><span class="sxs-lookup"><span data-stu-id="0ad9d-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="0ad9d-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="0ad9d-133">string</span></span> | <span data-ttu-id="0ad9d-134">Befattning för kontoanvändaren</span><span class="sxs-lookup"><span data-stu-id="0ad9d-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="0ad9d-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="0ad9d-135">string</span></span> | <span data-ttu-id="0ad9d-136">Kontots användarnamn</span><span class="sxs-lookup"><span data-stu-id="0ad9d-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="0ad9d-137">Sträng</span><span class="sxs-lookup"><span data-stu-id="0ad9d-137">string</span></span> | <span data-ttu-id="0ad9d-138">Kontots domän</span><span class="sxs-lookup"><span data-stu-id="0ad9d-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="0ad9d-139">Sträng</span><span class="sxs-lookup"><span data-stu-id="0ad9d-139">string</span></span> | <span data-ttu-id="0ad9d-140">SMTP-adressen för kontot</span><span class="sxs-lookup"><span data-stu-id="0ad9d-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="0ad9d-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="0ad9d-141">string</span></span> | <span data-ttu-id="0ad9d-142">SIP-adressen (Voice over IP) session initiation protocol (SIP) för kontot</span><span class="sxs-lookup"><span data-stu-id="0ad9d-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="0ad9d-143">Sträng</span><span class="sxs-lookup"><span data-stu-id="0ad9d-143">string</span></span> | <span data-ttu-id="0ad9d-144">Stad där kontoanvändaren finns</span><span class="sxs-lookup"><span data-stu-id="0ad9d-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="0ad9d-145">Sträng</span><span class="sxs-lookup"><span data-stu-id="0ad9d-145">string</span></span> | <span data-ttu-id="0ad9d-146">Land/region där kontoanvändaren finns</span><span class="sxs-lookup"><span data-stu-id="0ad9d-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="0ad9d-147">Boolean</span><span class="sxs-lookup"><span data-stu-id="0ad9d-147">boolean</span></span> | <span data-ttu-id="0ad9d-148">Anger om kontot är aktiverat eller inte</span><span class="sxs-lookup"><span data-stu-id="0ad9d-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0ad9d-149">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="0ad9d-149">Related topics</span></span>
- [<span data-ttu-id="0ad9d-150">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="0ad9d-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0ad9d-151">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="0ad9d-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0ad9d-152">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="0ad9d-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0ad9d-153">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="0ad9d-153">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0ad9d-154">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="0ad9d-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0ad9d-155">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="0ad9d-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
