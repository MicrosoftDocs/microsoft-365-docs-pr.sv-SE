---
title: IdentityInfo-tabell i det avancerade jakt-schemat
description: Lär dig mer om användar konto information i tabellen IdentityInfo för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, AccountInfo, IdentityInfo, konto
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
ms.openlocfilehash: 38a7e6600c682b1edef5320ef4de296b5943952d
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430485"
---
# <a name="identityinfo"></a><span data-ttu-id="0f76a-104">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="0f76a-104">IdentityInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0f76a-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="0f76a-105">**Applies to:**</span></span>
- <span data-ttu-id="0f76a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0f76a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="0f76a-107">`IdentityInfo`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om användar konton som hämtas från olika tjänster, inklusive Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0f76a-107">The `IdentityInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about user accounts obtained from various services, including Azure Active Directory.</span></span> <span data-ttu-id="0f76a-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="0f76a-108">Use this reference to construct queries that return information from this table.</span></span>

>[!NOTE]
><span data-ttu-id="0f76a-109">Tabellen har bytt namn från `AccountInfo` .</span><span class="sxs-lookup"><span data-stu-id="0f76a-109">This table was renamed from `AccountInfo`.</span></span> <span data-ttu-id="0f76a-110">När du byter namn uppdateras alla frågor som sparats i portalen automatiskt.</span><span class="sxs-lookup"><span data-stu-id="0f76a-110">During renames, all queries saved in the portal are automatically updated.</span></span> <span data-ttu-id="0f76a-111">Kolla frågor som du har sparat någon annan stans.</span><span class="sxs-lookup"><span data-stu-id="0f76a-111">Check queries you have saved elsewhere.</span></span>

<span data-ttu-id="0f76a-112">Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="0f76a-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="0f76a-113">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="0f76a-113">Column name</span></span> | <span data-ttu-id="0f76a-114">Datatyp</span><span class="sxs-lookup"><span data-stu-id="0f76a-114">Data type</span></span> | <span data-ttu-id="0f76a-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="0f76a-115">Description</span></span> |
|-------------|-----------|-------------|
| `AccountObjectId` | <span data-ttu-id="0f76a-116">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0f76a-116">string</span></span> | <span data-ttu-id="0f76a-117">Unik identifierare för kontot i Azure AD</span><span class="sxs-lookup"><span data-stu-id="0f76a-117">Unique identifier for the account in Azure AD</span></span> |
| `AccountUpn` | <span data-ttu-id="0f76a-118">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0f76a-118">string</span></span> | <span data-ttu-id="0f76a-119">Kontots huvud namn (UPN)</span><span class="sxs-lookup"><span data-stu-id="0f76a-119">User principal name (UPN) of the account</span></span> |
| `OnPremSid` | <span data-ttu-id="0f76a-120">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0f76a-120">string</span></span> | <span data-ttu-id="0f76a-121">Lokal säkerhets identifierare (SID) för kontot</span><span class="sxs-lookup"><span data-stu-id="0f76a-121">On-premises security identifier (SID) of the account</span></span> |
| `CloudSid` | <span data-ttu-id="0f76a-122">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0f76a-122">string</span></span> | <span data-ttu-id="0f76a-123">Moln säkerhets identifierare för kontot</span><span class="sxs-lookup"><span data-stu-id="0f76a-123">Cloud security identifier of the account</span></span> |
| `GivenName` | <span data-ttu-id="0f76a-124">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0f76a-124">string</span></span> | <span data-ttu-id="0f76a-125">Tilldelat namn eller förnamn för konto användaren</span><span class="sxs-lookup"><span data-stu-id="0f76a-125">Given name or first name of the account user</span></span> |
| `Surname` | <span data-ttu-id="0f76a-126">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0f76a-126">string</span></span> | <span data-ttu-id="0f76a-127">Efter namn, familje namn eller efter namnet på konto användaren</span><span class="sxs-lookup"><span data-stu-id="0f76a-127">Surname, family name, or last name of the account user</span></span> |
| `AccountDisplayName` | <span data-ttu-id="0f76a-128">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0f76a-128">string</span></span> | <span data-ttu-id="0f76a-129">Namnet på kontot som visas i adress boken.</span><span class="sxs-lookup"><span data-stu-id="0f76a-129">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="0f76a-130">Vanligt vis en kombination av ett visst eller förnamn, en mellan initiering och ett efter namn eller från gång.</span><span class="sxs-lookup"><span data-stu-id="0f76a-130">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `Department` | <span data-ttu-id="0f76a-131">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0f76a-131">string</span></span> | <span data-ttu-id="0f76a-132">Namn på avdelningen som konto användaren tillhör</span><span class="sxs-lookup"><span data-stu-id="0f76a-132">Name of the department that the account user belongs to</span></span> |
| `JobTitle` | <span data-ttu-id="0f76a-133">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0f76a-133">string</span></span> | <span data-ttu-id="0f76a-134">Befattning för konto användaren</span><span class="sxs-lookup"><span data-stu-id="0f76a-134">Job title of the account user</span></span> |
| `AccountName` | <span data-ttu-id="0f76a-135">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0f76a-135">string</span></span> | <span data-ttu-id="0f76a-136">Kontots användar namn</span><span class="sxs-lookup"><span data-stu-id="0f76a-136">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="0f76a-137">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0f76a-137">string</span></span> | <span data-ttu-id="0f76a-138">Kontots domän</span><span class="sxs-lookup"><span data-stu-id="0f76a-138">Domain of the account</span></span> |
| `EmailAddress` | <span data-ttu-id="0f76a-139">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0f76a-139">string</span></span> | <span data-ttu-id="0f76a-140">SMTP-adressen för kontot</span><span class="sxs-lookup"><span data-stu-id="0f76a-140">SMTP address of the account</span></span> |
| `SipProxyAddress` | <span data-ttu-id="0f76a-141">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0f76a-141">string</span></span> | <span data-ttu-id="0f76a-142">Kontots SIP-adress (Voice over IP)</span><span class="sxs-lookup"><span data-stu-id="0f76a-142">Voice over IP (VOIP) session initiation protocol (SIP) address of the account</span></span> |
| `City` | <span data-ttu-id="0f76a-143">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0f76a-143">string</span></span> | <span data-ttu-id="0f76a-144">Ort där konto användaren finns</span><span class="sxs-lookup"><span data-stu-id="0f76a-144">City where the account user is located</span></span> |
| `Country` | <span data-ttu-id="0f76a-145">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="0f76a-145">string</span></span> | <span data-ttu-id="0f76a-146">Land/region där konto användaren finns</span><span class="sxs-lookup"><span data-stu-id="0f76a-146">Country/Region where the account user is located</span></span> |
| `IsAccountEnabled` | <span data-ttu-id="0f76a-147">returtyp</span><span class="sxs-lookup"><span data-stu-id="0f76a-147">boolean</span></span> | <span data-ttu-id="0f76a-148">Anger om kontot är aktiverat eller inte</span><span class="sxs-lookup"><span data-stu-id="0f76a-148">Indicates whether the account is enabled or not</span></span> |

## <a name="related-topics"></a><span data-ttu-id="0f76a-149">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="0f76a-149">Related topics</span></span>
- [<span data-ttu-id="0f76a-150">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="0f76a-150">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="0f76a-151">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="0f76a-151">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="0f76a-152">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="0f76a-152">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="0f76a-153">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="0f76a-153">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="0f76a-154">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="0f76a-154">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="0f76a-155">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="0f76a-155">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
