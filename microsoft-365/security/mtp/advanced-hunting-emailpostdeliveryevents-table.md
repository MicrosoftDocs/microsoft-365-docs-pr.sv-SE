---
title: Tabellen EmailPostDeliveryEvents i det avancerade sökschemat
description: Läs mer om åtgärder efter leverans som har vidtagits i e-postmeddelanden från Microsoft 365 i tabellen EmailPostDeliveryEvents i det avancerade sökschemat
keywords: avancerad sökning, hotsökning, sökning på cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, E-postPostDeliveryEvents, nätverksmeddelande-ID, avsändare, mottagare, bifogad fil-ID, namn på bifogad fil, skadlig kod
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 6e12ddfc402f1bd420f57369cc6d54f2e670d710
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712384"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="24212-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="24212-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="24212-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="24212-105">**Applies to:**</span></span>
- <span data-ttu-id="24212-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24212-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="24212-107">Tabellen i det avancerade utbildningsschemat innehåller information om åtgärder efter leverans av `EmailPostDeliveryEvents` e-postmeddelanden [](advanced-hunting-overview.md) som bearbetats av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24212-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="24212-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="24212-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="24212-109">Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` inbyggda schemareferensen som finns i säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="24212-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="24212-110">Du kan också använda tabellerna och om du vill ha mer information om [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) enskilda [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="24212-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="24212-111">Information om andra tabeller i det avancerade sökschemat finns i [den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="24212-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="24212-112">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="24212-112">Column name</span></span> | <span data-ttu-id="24212-113">Datatyp</span><span class="sxs-lookup"><span data-stu-id="24212-113">Data type</span></span> | <span data-ttu-id="24212-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="24212-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="24212-115">datetime</span><span class="sxs-lookup"><span data-stu-id="24212-115">datetime</span></span> | <span data-ttu-id="24212-116">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="24212-116">Date and time when the event was recorded</span></span> |
| `NetworkMessageId` | <span data-ttu-id="24212-117">sträng</span><span class="sxs-lookup"><span data-stu-id="24212-117">string</span></span> | <span data-ttu-id="24212-118">Unikt ID för e-postmeddelandet som genereras av Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="24212-118">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="24212-119">sträng</span><span class="sxs-lookup"><span data-stu-id="24212-119">string</span></span> | <span data-ttu-id="24212-120">Offentlig identifierare för e-postmeddelandet som anges av det avsändande e-postsystemet</span><span class="sxs-lookup"><span data-stu-id="24212-120">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="24212-121">sträng</span><span class="sxs-lookup"><span data-stu-id="24212-121">string</span></span> | <span data-ttu-id="24212-122">Åtgärd som vidtas på entiteten</span><span class="sxs-lookup"><span data-stu-id="24212-122">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="24212-123">sträng</span><span class="sxs-lookup"><span data-stu-id="24212-123">string</span></span> | <span data-ttu-id="24212-124">Typ av aktivitet som utlöste händelsen: Manuell åtgärd, Phish ZAP, Malware ZAP</span><span class="sxs-lookup"><span data-stu-id="24212-124">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="24212-125">sträng</span><span class="sxs-lookup"><span data-stu-id="24212-125">string</span></span> | <span data-ttu-id="24212-126">Anger om en åtgärd utlöstes av en administratör (manuellt eller genom godkännande av en väntande automatiserad åtgärd) eller av någon särskild mekanism, till exempel en ZAP eller dynamisk leverans</span><span class="sxs-lookup"><span data-stu-id="24212-126">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="24212-127">sträng</span><span class="sxs-lookup"><span data-stu-id="24212-127">string</span></span> | <span data-ttu-id="24212-128">Åtgärdens resultat</span><span class="sxs-lookup"><span data-stu-id="24212-128">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="24212-129">sträng</span><span class="sxs-lookup"><span data-stu-id="24212-129">string</span></span> | <span data-ttu-id="24212-130">Mottagarens e-postadress eller e-postadress för mottagaren efter distributionslistans expansion</span><span class="sxs-lookup"><span data-stu-id="24212-130">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="24212-131">sträng</span><span class="sxs-lookup"><span data-stu-id="24212-131">string</span></span> | <span data-ttu-id="24212-132">Plats där e-postmeddelandet levererades: Inkorg/Mapp, Lokal/Extern, Skräppost, Karantän, Misslyckades, Släppt, Borttaget</span><span class="sxs-lookup"><span data-stu-id="24212-132">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |
| `ReportId` | <span data-ttu-id="24212-133">long</span><span class="sxs-lookup"><span data-stu-id="24212-133">long</span></span> | <span data-ttu-id="24212-134">Händelseidentifierare baserade på en återkommande räknare.</span><span class="sxs-lookup"><span data-stu-id="24212-134">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="24212-135">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp.</span><span class="sxs-lookup"><span data-stu-id="24212-135">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="24212-136">Händelsetyper som stöds</span><span class="sxs-lookup"><span data-stu-id="24212-136">Supported event types</span></span>
<span data-ttu-id="24212-137">I den här tabellen visas händelser med följande `ActionType` värden:</span><span class="sxs-lookup"><span data-stu-id="24212-137">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="24212-138">**Manuell åtgärd – en** administratör har manuellt åtgärdat ett e-postmeddelande efter att det levererades till användarens postlåda.</span><span class="sxs-lookup"><span data-stu-id="24212-138">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="24212-139">Det omfattar åtgärder som vidtas manuellt via [Threat Explorer](../office-365-security/threat-explorer.md) eller godkännanden av automatisk undersökning [och svarsåtgärder (AIR).](mtp-autoir-actions.md)</span><span class="sxs-lookup"><span data-stu-id="24212-139">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="24212-140">**Phish ZAP** – [zap (Zero-hour auto purge)](../office-365-security/zero-hour-auto-purge.md) har vidta åtgärder för nätfiske efter leverans.</span><span class="sxs-lookup"><span data-stu-id="24212-140">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="24212-141">**Malware ZAP** – ZAP (Zero-hour auto purge) vidtog åtgärder på ett e-postmeddelande som innehöll skadlig kod efter leverans.</span><span class="sxs-lookup"><span data-stu-id="24212-141">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="24212-142">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="24212-142">Related topics</span></span>
- [<span data-ttu-id="24212-143">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="24212-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="24212-144">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="24212-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="24212-145">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="24212-145">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="24212-146">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="24212-146">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="24212-147">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="24212-147">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="24212-148">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="24212-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
