---
title: EmailPostDeliveryEvents-tabell i det avancerade jakt-schemat
description: Lär dig mer om åtgärder efter leverans på Microsoft 365-e-postmeddelanden i EmailPostDeliveryEvents-tabellen i det avancerade jakt-schemat
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, schema referens, kusto, tabell, kolumn, datatyp, beskrivning, EmailPostDeliveryEvents, nätverks meddelande-ID, avsändare, mottagare, bifogade filer
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
ms.openlocfilehash: ea54f6b312c473240dba07eae95733d2ea610fe5
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430555"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="c38ab-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="c38ab-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c38ab-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c38ab-105">**Applies to:**</span></span>
- <span data-ttu-id="c38ab-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c38ab-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c38ab-107">`EmailPostDeliveryEvents`Tabellen i det [avancerade jakt](advanced-hunting-overview.md) -schemat innehåller information om åtgärder efter leverans på de e-postmeddelanden som hanteras av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c38ab-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="c38ab-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="c38ab-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="c38ab-109">Detaljerad information om de händelse typer ( `ActionType` värden) som stöds av en tabell finns i den [inbyggda schema referensen](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) i säkerhets Center.</span><span class="sxs-lookup"><span data-stu-id="c38ab-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="c38ab-110">Om du vill ha mer information om enskilda e-postmeddelanden kan du även [`EmailEvents`](advanced-hunting-emailevents-table.md) använda [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) tabellerna, och [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) .</span><span class="sxs-lookup"><span data-stu-id="c38ab-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="c38ab-111">Information om andra tabeller i det avancerade jakt schema [finns i referens för avancerad jakt](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c38ab-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c38ab-112">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="c38ab-112">Column name</span></span> | <span data-ttu-id="c38ab-113">Datatyp</span><span class="sxs-lookup"><span data-stu-id="c38ab-113">Data type</span></span> | <span data-ttu-id="c38ab-114">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="c38ab-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c38ab-115">datetime</span><span class="sxs-lookup"><span data-stu-id="c38ab-115">datetime</span></span> | <span data-ttu-id="c38ab-116">Datum och tid när händelsen registrerades</span><span class="sxs-lookup"><span data-stu-id="c38ab-116">Date and time when the event was recorded</span></span> |
| `EventId` | <span data-ttu-id="c38ab-117">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="c38ab-117">string</span></span> | <span data-ttu-id="c38ab-118">Unik identifierare för händelsen</span><span class="sxs-lookup"><span data-stu-id="c38ab-118">Unique identifier for the event</span></span> |
| `NetworkMessageId` | <span data-ttu-id="c38ab-119">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="c38ab-119">string</span></span> | <span data-ttu-id="c38ab-120">Unik identifierare för e-postmeddelandet, genererat av Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c38ab-120">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="c38ab-121">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="c38ab-121">string</span></span> | <span data-ttu-id="c38ab-122">Public-Facing ID för e-postmeddelandet som anges i det sändande e-postsystemet</span><span class="sxs-lookup"><span data-stu-id="c38ab-122">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="c38ab-123">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="c38ab-123">string</span></span> | <span data-ttu-id="c38ab-124">Åtgärd som utförs på enheten</span><span class="sxs-lookup"><span data-stu-id="c38ab-124">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="c38ab-125">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="c38ab-125">string</span></span> | <span data-ttu-id="c38ab-126">Typ av aktivitet som utlöste händelsen: manuell reparation, Phish, ZAP</span><span class="sxs-lookup"><span data-stu-id="c38ab-126">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="c38ab-127">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="c38ab-127">string</span></span> | <span data-ttu-id="c38ab-128">Anger om en åtgärd som utlöstes av en administratör (manuellt eller genom godkännande av en väntande automatiserad åtgärd) eller någon särskild mekanism, till exempel en ZAP eller dynamisk leverans</span><span class="sxs-lookup"><span data-stu-id="c38ab-128">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="c38ab-129">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="c38ab-129">string</span></span> | <span data-ttu-id="c38ab-130">Resultat av åtgärden</span><span class="sxs-lookup"><span data-stu-id="c38ab-130">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="c38ab-131">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="c38ab-131">string</span></span> | <span data-ttu-id="c38ab-132">E-postadress till mottagaren eller e-postadressen till mottagaren efter expansion av distributions lista</span><span class="sxs-lookup"><span data-stu-id="c38ab-132">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="c38ab-133">strängvärdet</span><span class="sxs-lookup"><span data-stu-id="c38ab-133">string</span></span> | <span data-ttu-id="c38ab-134">Plats där e-postmeddelandet levererades: Inkorgen/mapp, lokal/extern, skräp, karantän, misslyckad, avbruten, borttaget</span><span class="sxs-lookup"><span data-stu-id="c38ab-134">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="c38ab-135">Händelse typer som stöds</span><span class="sxs-lookup"><span data-stu-id="c38ab-135">Supported event types</span></span>
<span data-ttu-id="c38ab-136">Den här tabellen registrerar händelser med följande `ActionType` värden:</span><span class="sxs-lookup"><span data-stu-id="c38ab-136">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="c38ab-137">**Manuell reparation** – en administratör vidtog en åtgärd manuellt i ett e-postmeddelande efter att det har skickats till användarens post låda.</span><span class="sxs-lookup"><span data-stu-id="c38ab-137">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="c38ab-138">Detta inkluderar åtgärder som utförs manuellt via [Threat Explorer](../office-365-security/threat-explorer.md) eller godkännanden av [automatiserade undersökningar och svar (Air)](mtp-autoir-actions.md).</span><span class="sxs-lookup"><span data-stu-id="c38ab-138">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="c38ab-139">**PHISH ZAP** – [Automatisk rensning av Tom timme (Zap)](../office-365-security/zero-hour-auto-purge.md) vidtog en åtgärd på en nätfiske-e-postadress efter leverans.</span><span class="sxs-lookup"><span data-stu-id="c38ab-139">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="c38ab-140">**Malware-ZAP** – automatisk rensning för en timme (Zap) vidtog en åtgärd i ett e-postmeddelande som innehöll skadlig kod efter leverans.</span><span class="sxs-lookup"><span data-stu-id="c38ab-140">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c38ab-141">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="c38ab-141">Related topics</span></span>
- [<span data-ttu-id="c38ab-142">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="c38ab-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c38ab-143">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="c38ab-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c38ab-144">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="c38ab-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c38ab-145">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="c38ab-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c38ab-146">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="c38ab-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c38ab-147">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="c38ab-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
