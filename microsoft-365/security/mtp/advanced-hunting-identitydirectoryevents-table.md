---
title: IdentityDirectoryEvents-tabell i det avancerade jakt-schemat
description: Lär dig mer om domän kontrol Lanterna och Active Directory-händelser i tabellen IdentityDirectoryEvents för Advanced jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, IdentityDirectoryEvents, domänkontrollant, Active Directory, Azure ATP, identiteter
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
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 9113d12face141b5e8005340af25061c98d5dfe3
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412856"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="6c378-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="6c378-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6c378-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6c378-105">**Applies to:**</span></span>
- <span data-ttu-id="6c378-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6c378-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="6c378-107">`IdentityDirectoryEvents`Tabellen i det [avancerade](advanced-hunting-overview.md) antivirus programmet innehåller händelser som berör en lokal domänkontrollant som kör Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="6c378-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="6c378-108">Den här tabellen innehåller olika identitets relaterade händelser, till exempel lösen ords ändringar, lösen ords giltighet och UPN-ändringar.</span><span class="sxs-lookup"><span data-stu-id="6c378-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="6c378-109">Den fångar också system händelser på domänkontrollanten, som schemaläggning av uppgifter och PowerShell-aktivitet.</span><span class="sxs-lookup"><span data-stu-id="6c378-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="6c378-110">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="6c378-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="6c378-111">Detaljerad information om de händelse typer ( `ActionType` värden) som stöds av en tabell finns i den [inbyggda schema referensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="6c378-111">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="6c378-112">Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="6c378-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6c378-113">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="6c378-113">Column name</span></span> | <span data-ttu-id="6c378-114">Datatyp</span><span class="sxs-lookup"><span data-stu-id="6c378-114">Data type</span></span> | <span data-ttu-id="6c378-115">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6c378-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6c378-116">datetime</span><span class="sxs-lookup"><span data-stu-id="6c378-116">datetime</span></span> | <span data-ttu-id="6c378-117">Datum och tid när händelsen registrerades</span><span class="sxs-lookup"><span data-stu-id="6c378-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="6c378-118">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-118">string</span></span> | <span data-ttu-id="6c378-119">Typ av aktivitet som utlöste händelsen.</span><span class="sxs-lookup"><span data-stu-id="6c378-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="6c378-120">Mer information finns [i referens för in-Portal schema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="6c378-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="6c378-121">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-121">string</span></span> | <span data-ttu-id="6c378-122">Program som utförde den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="6c378-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="6c378-123">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-123">string</span></span> | <span data-ttu-id="6c378-124">Användarens huvud namn (UPN) för det konto som den inspelade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="6c378-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="6c378-125">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-125">string</span></span> | <span data-ttu-id="6c378-126">Visnings namn för det konto som den inspelade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="6c378-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="6c378-127">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-127">string</span></span> | <span data-ttu-id="6c378-128">Det fullständigt kvalificerade domän namnet (FQDN) för enheten som den inspelade åtgärden tillämpades på</span><span class="sxs-lookup"><span data-stu-id="6c378-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="6c378-129">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-129">string</span></span> | <span data-ttu-id="6c378-130">Namn på den enhet som kör serverprogrammet som bearbetade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="6c378-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="6c378-131">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-131">string</span></span> | <span data-ttu-id="6c378-132">IP-adress för enheten som kör serverprogrammet som bearbetade den inspelade åtgärden</span><span class="sxs-lookup"><span data-stu-id="6c378-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="6c378-133">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-133">string</span></span> | <span data-ttu-id="6c378-134">Mål Port för aktiviteten</span><span class="sxs-lookup"><span data-stu-id="6c378-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="6c378-135">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-135">string</span></span> | <span data-ttu-id="6c378-136">Protokoll som används under kommunikationen</span><span class="sxs-lookup"><span data-stu-id="6c378-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="6c378-137">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-137">string</span></span> | <span data-ttu-id="6c378-138">Kontots användar namn</span><span class="sxs-lookup"><span data-stu-id="6c378-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="6c378-139">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-139">string</span></span> | <span data-ttu-id="6c378-140">Kontots domän</span><span class="sxs-lookup"><span data-stu-id="6c378-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="6c378-141">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-141">string</span></span> | <span data-ttu-id="6c378-142">Kontots huvud namn (UPN)</span><span class="sxs-lookup"><span data-stu-id="6c378-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="6c378-143">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-143">string</span></span> | <span data-ttu-id="6c378-144">Kontots säkerhets identifierare (SID)</span><span class="sxs-lookup"><span data-stu-id="6c378-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="6c378-145">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-145">string</span></span> | <span data-ttu-id="6c378-146">Unik identifierare för kontot i Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6c378-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="6c378-147">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-147">string</span></span> | <span data-ttu-id="6c378-148">Namnet på kontot som visas i adress boken.</span><span class="sxs-lookup"><span data-stu-id="6c378-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="6c378-149">Vanligt vis en kombination av ett visst eller förnamn, en mellan initiering och ett efter namn eller från gång.</span><span class="sxs-lookup"><span data-stu-id="6c378-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="6c378-150">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-150">string</span></span> | <span data-ttu-id="6c378-151">Det fullständigt kvalificerade domän namnet (FQDN) för enheten</span><span class="sxs-lookup"><span data-stu-id="6c378-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="6c378-152">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-152">string</span></span> | <span data-ttu-id="6c378-153">Den IP-adress som tilldelats enheten under kommunikationen</span><span class="sxs-lookup"><span data-stu-id="6c378-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="6c378-154">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-154">string</span></span> | <span data-ttu-id="6c378-155">TCP-port som används under kommunikation</span><span class="sxs-lookup"><span data-stu-id="6c378-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="6c378-156">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-156">string</span></span> | <span data-ttu-id="6c378-157">Ort, land eller annan geografisk plats som är kopplad till evenemanget</span><span class="sxs-lookup"><span data-stu-id="6c378-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="6c378-158">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-158">string</span></span> | <span data-ttu-id="6c378-159">Internet leverantör associerad med IP-adressen</span><span class="sxs-lookup"><span data-stu-id="6c378-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="6c378-160">tids</span><span class="sxs-lookup"><span data-stu-id="6c378-160">long</span></span> | <span data-ttu-id="6c378-161">Unik identifierare för händelsen</span><span class="sxs-lookup"><span data-stu-id="6c378-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="6c378-162">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="6c378-162">string</span></span> | <span data-ttu-id="6c378-163">Ytterligare information om enheten eller händelsen</span><span class="sxs-lookup"><span data-stu-id="6c378-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6c378-164">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6c378-164">Related topics</span></span>
- [<span data-ttu-id="6c378-165">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="6c378-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6c378-166">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="6c378-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6c378-167">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="6c378-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6c378-168">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="6c378-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6c378-169">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="6c378-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6c378-170">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="6c378-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
