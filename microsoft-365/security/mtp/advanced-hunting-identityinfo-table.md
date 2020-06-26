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
ms.openlocfilehash: b384e76439ae706520725e7193fa64224b724be0
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898963"
---
# <a name="identityinfo"></a><span data-ttu-id="baeee-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="baeee-104">IdentityInfo</span></span>

<span data-ttu-id="baeee-105">**Gäller:**</span><span class="sxs-lookup"><span data-stu-id="baeee-105">**Applies to:**</span></span>
- <span data-ttu-id="baeee-106">Microsoft Hotskydd</span><span class="sxs-lookup"><span data-stu-id="baeee-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="baeee-107">`IdentityInfo`Tabellen i det avancerade [jaktschemat](advanced-hunting-overview.md) innehåller information om användarkonton som hämtats från olika tjänster, inklusive Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="baeee-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="baeee-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="baeee-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="baeee-109">Den här tabellen har bytt namn från `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="baeee-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="baeee-110">Under namnbyten uppdateras alla frågor som sparats i portalen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="baeee-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="baeee-111">Kontrollera frågor som du har sparat någon annanstans.</span><span class="sxs-lookup"><span data-stu-id="baeee-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="baeee-112">Information om andra tabeller i det avancerade jaktschemat [finns i den avancerade jaktreferensen](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="baeee-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="baeee-113">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="baeee-113">Column name</span></span> | <span data-ttu-id="baeee-114">Datatyp</span><span class="sxs-lookup"><span data-stu-id="baeee-114">Data type</span></span> | <span data-ttu-id="baeee-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="baeee-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="baeee-116">Sträng</span><span class="sxs-lookup"><span data-stu-id="baeee-116">string</span></span> | <span data-ttu-id="baeee-117">Unik identifierare för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="baeee-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="baeee-118">Sträng</span><span class="sxs-lookup"><span data-stu-id="baeee-118">string</span></span> | <span data-ttu-id="baeee-119">Användarens huvudnamn (UPN) för kontot</span><span class="sxs-lookup"><span data-stu-id="baeee-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="baeee-120">Sträng</span><span class="sxs-lookup"><span data-stu-id="baeee-120">string</span></span> | <span data-ttu-id="baeee-121">Sid-säkerhetsidentifierare (On-premises security identifier) för kontot</span><span class="sxs-lookup"><span data-stu-id="baeee-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="baeee-122">Sträng</span><span class="sxs-lookup"><span data-stu-id="baeee-122">string</span></span> | <span data-ttu-id="baeee-123">Molnsäkerhetsidentifierare för kontot</span><span class="sxs-lookup"><span data-stu-id="baeee-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="baeee-124">Sträng</span><span class="sxs-lookup"><span data-stu-id="baeee-124">string</span></span> | <span data-ttu-id="baeee-125">Kontoanvändarens förnamn eller förnamn</span><span class="sxs-lookup"><span data-stu-id="baeee-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="baeee-126">Sträng</span><span class="sxs-lookup"><span data-stu-id="baeee-126">string</span></span> | <span data-ttu-id="baeee-127">Kontoanvändarens efternamn, efternamn eller efternamn</span><span class="sxs-lookup"><span data-stu-id="baeee-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="baeee-128">Sträng</span><span class="sxs-lookup"><span data-stu-id="baeee-128">string</span></span> | <span data-ttu-id="baeee-129">Namn på den kontoanvändare som visas i adressboken.</span><span class="sxs-lookup"><span data-stu-id="baeee-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="baeee-130">Vanligtvis en kombination av ett givet eller förnamn, en mellaninitiering och ett efternamn eller efternamn.</span><span class="sxs-lookup"><span data-stu-id="baeee-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="baeee-131">Sträng</span><span class="sxs-lookup"><span data-stu-id="baeee-131">string</span></span> | <span data-ttu-id="baeee-132">Namn på den avdelning som kontoanvändaren tillhör</span><span class="sxs-lookup"><span data-stu-id="baeee-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="baeee-133">Sträng</span><span class="sxs-lookup"><span data-stu-id="baeee-133">string</span></span> | <span data-ttu-id="baeee-134">Befattning för kontoanvändaren</span><span class="sxs-lookup"><span data-stu-id="baeee-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="baeee-135">Sträng</span><span class="sxs-lookup"><span data-stu-id="baeee-135">string</span></span> | <span data-ttu-id="baeee-136">Kontots användarnamn</span><span class="sxs-lookup"><span data-stu-id="baeee-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="baeee-137">Sträng</span><span class="sxs-lookup"><span data-stu-id="baeee-137">string</span></span> | <span data-ttu-id="baeee-138">Kontots domän</span><span class="sxs-lookup"><span data-stu-id="baeee-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="baeee-139">Sträng</span><span class="sxs-lookup"><span data-stu-id="baeee-139">string</span></span> | <span data-ttu-id="baeee-140">SMTP-adressen för kontot</span><span class="sxs-lookup"><span data-stu-id="baeee-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="baeee-141">Sträng</span><span class="sxs-lookup"><span data-stu-id="baeee-141">string</span></span> | <span data-ttu-id="baeee-142">Röst för kontots ip-sessionsinitieringsprotokoll (VOIP) för kontot</span><span class="sxs-lookup"><span data-stu-id="baeee-142">Voice of over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="baeee-143">Sträng</span><span class="sxs-lookup"><span data-stu-id="baeee-143">string</span></span> | <span data-ttu-id="baeee-144">Stad där kontoanvändaren finns</span><span class="sxs-lookup"><span data-stu-id="baeee-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="baeee-145">Sträng</span><span class="sxs-lookup"><span data-stu-id="baeee-145">string</span></span> | <span data-ttu-id="baeee-146">Land/region där kontoanvändaren finns</span><span class="sxs-lookup"><span data-stu-id="baeee-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="baeee-147">Boolean</span><span class="sxs-lookup"><span data-stu-id="baeee-147">boolean</span></span> | <span data-ttu-id="baeee-148">Anger om kontot är aktiverat eller inte</span><span class="sxs-lookup"><span data-stu-id="baeee-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="baeee-149">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="baeee-149">Related topics</span></span>
- [<span data-ttu-id="baeee-150">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="baeee-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="baeee-151">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="baeee-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="baeee-152">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="baeee-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="baeee-153">Jakten på hot på olika enheter och e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="baeee-153">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="baeee-154">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="baeee-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="baeee-155">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="baeee-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
