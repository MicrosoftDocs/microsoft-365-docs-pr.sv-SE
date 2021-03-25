---
title: Tabellen EmailEvents i det avancerade sökschemat
description: Läs mer om händelser som är associerade med e-postmeddelanden från Microsoft 365 i tabellen EmailEvents i den avancerade tabellen för sökning
keywords: avancerad sökning, hotsökning, sökning efter cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, schemareferens, kusto, tabell, kolumn, datatyp, beskrivning, EmailEvents, nätverksmeddelande-ID, avsändare, mottagare, bifogad fil-ID, bifogade filer, skadlig kod, skadlig kod, nätfiske, antal bifogade filer, antal länkar, antal url
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 086d3ef8777685d17fdcdfdcd937cb120810c78a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073954"
---
# <a name="emailevents"></a><span data-ttu-id="6f258-104">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="6f258-104">EmailEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6f258-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6f258-105">**Applies to:**</span></span>

- <span data-ttu-id="6f258-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f258-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6f258-107">Tabellen i det avancerade schemat för sökning innehåller information om händelser som innefattar bearbetning `EmailEvents` av e-postmeddelanden på Microsoft Defender för Office 365. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6f258-107">The `EmailEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about events involving the processing of emails on Microsoft Defender for Office 365.</span></span> <span data-ttu-id="6f258-108">Använd den här referensen för att skapa frågor som returnerar information från den här tabellen.</span><span class="sxs-lookup"><span data-stu-id="6f258-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="6f258-109">Om du vill ha detaljerad information om de händelsetyper (värden) som stöds av en tabell kan du använda den `ActionType` inbyggda schemareferensen som finns i säkerhetscentret.</span><span class="sxs-lookup"><span data-stu-id="6f258-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="6f258-110">Information om andra tabeller i det avancerade sökschemat finns [i den avancerade referensen för sökning.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="6f258-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="6f258-111">Kolumnnamn</span><span class="sxs-lookup"><span data-stu-id="6f258-111">Column name</span></span> | <span data-ttu-id="6f258-112">Datatyp</span><span class="sxs-lookup"><span data-stu-id="6f258-112">Data type</span></span> | <span data-ttu-id="6f258-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6f258-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="6f258-114">datetime</span><span class="sxs-lookup"><span data-stu-id="6f258-114">datetime</span></span> | <span data-ttu-id="6f258-115">Datum och tid då händelsen spelades in</span><span class="sxs-lookup"><span data-stu-id="6f258-115">Date and time when the event was recorded</span></span> |
| `NetworkMessageId` | <span data-ttu-id="6f258-116">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-116">string</span></span> | <span data-ttu-id="6f258-117">Unikt ID för e-postmeddelandet som genereras av Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f258-117">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="6f258-118">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-118">string</span></span> | <span data-ttu-id="6f258-119">Offentlig identifierare för det e-postmeddelande som konfigureras av det avsändande e-postsystemet</span><span class="sxs-lookup"><span data-stu-id="6f258-119">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `SenderMailFromAddress` | <span data-ttu-id="6f258-120">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-120">string</span></span> | <span data-ttu-id="6f258-121">Avsändarens e-postadress i sidhuvudet E-POST FRÅN, som även kallas kuvertavsändaren eller Return-Path postadressen</span><span class="sxs-lookup"><span data-stu-id="6f258-121">Sender email address in the MAIL FROM header, also known as the envelope sender or the Return-Path address</span></span> |
| `SenderFromAddress` | <span data-ttu-id="6f258-122">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-122">string</span></span> | <span data-ttu-id="6f258-123">Avsändarens e-postadress i sidhuvudet FRÅN, som visas för e-postmottagare i deras e-postklienter</span><span class="sxs-lookup"><span data-stu-id="6f258-123">Sender email address in the FROM header, which is visible to email recipients on their email clients</span></span> |
| `SenderDisplayName` | <span data-ttu-id="6f258-124">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-124">string</span></span> | <span data-ttu-id="6f258-125">Namnet på avsändaren som visas i adressboken, vanligtvis en kombination av ett visst namn eller förnamn, en initial för mellannamn och efternamn eller efternamn</span><span class="sxs-lookup"><span data-stu-id="6f258-125">Name of the sender displayed in the address book, typically a combination of a given or first name, a middle initial, and a last name or surname</span></span> |
| `SenderObjectId` | <span data-ttu-id="6f258-126">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-126">string</span></span> |<span data-ttu-id="6f258-127">Unik identifierare för avsändarens konto i Azure AD</span><span class="sxs-lookup"><span data-stu-id="6f258-127">Unique identifier for the sender’s account in Azure AD</span></span> |
| `SenderMailFromDomain` | <span data-ttu-id="6f258-128">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-128">string</span></span> | <span data-ttu-id="6f258-129">Sender domain in the MAIL FROM header, also known as the envelope sender or the Return-Path address</span><span class="sxs-lookup"><span data-stu-id="6f258-129">Sender domain in the MAIL FROM header, also known as the envelope sender or the Return-Path address</span></span> |
| `SenderFromDomain` | <span data-ttu-id="6f258-130">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-130">string</span></span> | <span data-ttu-id="6f258-131">Sender domain in the FROM header, which is visible to email recipients on their email clients</span><span class="sxs-lookup"><span data-stu-id="6f258-131">Sender domain in the FROM header, which is visible to email recipients on their email clients</span></span> |
| `SenderIPv4` | <span data-ttu-id="6f258-132">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-132">string</span></span> | <span data-ttu-id="6f258-133">IPv4-adress till den senast identifierade e-postservern som vidarebefordrade meddelandet</span><span class="sxs-lookup"><span data-stu-id="6f258-133">IPv4 address of the last detected mail server that relayed the message</span></span> |
| `SenderIPv6` | <span data-ttu-id="6f258-134">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-134">string</span></span> | <span data-ttu-id="6f258-135">IPv6-adress till den senast identifierade e-postservern som vidarebefordrade meddelandet</span><span class="sxs-lookup"><span data-stu-id="6f258-135">IPv6 address of the last detected mail server that relayed the message</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="6f258-136">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-136">string</span></span> | <span data-ttu-id="6f258-137">Mottagarens e-postadress eller e-postadress efter att distributionslistan expanderat</span><span class="sxs-lookup"><span data-stu-id="6f258-137">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `RecipientObjectId` | <span data-ttu-id="6f258-138">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-138">string</span></span> | <span data-ttu-id="6f258-139">Unikt ID för e-postmottagaren i Azure AD</span><span class="sxs-lookup"><span data-stu-id="6f258-139">Unique identifier for the email recipient in Azure AD</span></span> |
| `Subject` | <span data-ttu-id="6f258-140">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-140">string</span></span> | <span data-ttu-id="6f258-141">E-postmeddelandets ämne</span><span class="sxs-lookup"><span data-stu-id="6f258-141">Subject of the email</span></span> |
| `EmailClusterId` | <span data-ttu-id="6f258-142">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-142">string</span></span> | <span data-ttu-id="6f258-143">Identifierare för gruppen av liknande e-postmeddelanden grupperade baserat på heuristisk analys av innehållet</span><span class="sxs-lookup"><span data-stu-id="6f258-143">Identifier for the group of similar emails clustered based on heuristic analysis of their contents</span></span> |
| `EmailDirection` | <span data-ttu-id="6f258-144">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-144">string</span></span> | <span data-ttu-id="6f258-145">E-postriktning i förhållande till ditt nätverk: Inkommande, utgående, årsorganisation</span><span class="sxs-lookup"><span data-stu-id="6f258-145">Direction of the email relative to your network:  Inbound, Outbound, Intra-org</span></span> |
| `DeliveryAction` | <span data-ttu-id="6f258-146">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-146">string</span></span> | <span data-ttu-id="6f258-147">Leveransåtgärd för e-postmeddelandet: Levererad, Skräppost, Blockerad eller Ersatt</span><span class="sxs-lookup"><span data-stu-id="6f258-147">Delivery action of the email: Delivered, Junked, Blocked, or Replaced</span></span> |
| `DeliveryLocation` | <span data-ttu-id="6f258-148">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-148">string</span></span> | <span data-ttu-id="6f258-149">Plats där e-postmeddelandet levererades: Inkorg/mapp, Lokal/Extern, Skräppost, Karantän, Misslyckades, Nedsl ett, Borttaget</span><span class="sxs-lookup"><span data-stu-id="6f258-149">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |
| `ThreatTypes` | <span data-ttu-id="6f258-150">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-150">string</span></span> | <span data-ttu-id="6f258-151">Bedömning av e-postfiltreringsstacken utifrån om e-postmeddelandet innehåller skadlig kod, nätfiske eller andra hot</span><span class="sxs-lookup"><span data-stu-id="6f258-151">Verdict from the email filtering stack on whether the email contains malware, phishing, or other threats</span></span> |
| `ThreatNames` | <span data-ttu-id="6f258-152">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-152">string</span></span> |<span data-ttu-id="6f258-153">Namn för identifiering av skadlig programvara eller andra hot som hittas</span><span class="sxs-lookup"><span data-stu-id="6f258-153">Detection name for malware or other threats found</span></span> |
| `DetectionMethods` | <span data-ttu-id="6f258-154">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-154">string</span></span> | <span data-ttu-id="6f258-155">Metoder som används för att identifiera skadlig kod, nätfiske eller andra hot som påträffas i e-postmeddelandet</span><span class="sxs-lookup"><span data-stu-id="6f258-155">Methods used to detect malware, phishing, or other threats found in the email</span></span> |
| `ConfidenceLevel` | <span data-ttu-id="6f258-156">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-156">string</span></span> | <span data-ttu-id="6f258-157">Lista över konfidensnivåer för skräppost- och nätfiskeförsök.</span><span class="sxs-lookup"><span data-stu-id="6f258-157">List of confidence levels of any spam or phishing verdicts.</span></span> <span data-ttu-id="6f258-158">För skräppost visar den här kolumnen konfidensnivån för skräppost (SCL), som anger om e-postmeddelandet hoppades över (-1), som hittades inte vara skräppost (0,1), som hittades som skräppost med måttligt förtroende (5,6) eller som hittades vara skräppost med hög konfidens (9).</span><span class="sxs-lookup"><span data-stu-id="6f258-158">For spam, this column shows the spam confidence level (SCL), indicating if the email was skipped (-1), found to be not spam (0,1), found to be spam with moderate confidence (5,6), or found to be spam with high confidence (9).</span></span> <span data-ttu-id="6f258-159">Vid nätfiske visas i den här kolumnen om konfidensnivån är "Hög" eller "Låg".</span><span class="sxs-lookup"><span data-stu-id="6f258-159">For phishing, this column displays whether the confidence level is "High" or "Low".</span></span> |
| `EmailAction` | <span data-ttu-id="6f258-160">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-160">string</span></span> | <span data-ttu-id="6f258-161">Slutåtgärd för e-postmeddelandet baserat på filterbekräftelse, principer och användaråtgärder: Flytta meddelandet till skräppostmappen, Lägg till X-sidhuvud, Ändra ämne, Omdirigera meddelande, Ta bort meddelande, skicka till karantän, Ingen åtgärd vidtas, Hemlig kopia</span><span class="sxs-lookup"><span data-stu-id="6f258-161">Final action taken on the email based on filter verdict, policies, and user actions:  Move message to junk mail folder, Add X-header, Modify subject, Redirect message, Delete message, send to quarantine, No action taken, Bcc message</span></span> |
| `EmailActionPolicy` | <span data-ttu-id="6f258-162">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-162">string</span></span> | <span data-ttu-id="6f258-163">Åtgärdspolicy som verkställde: Skräppostskydd med hög säkerhet, skräppostskydd, skräppostskydd, nätfiskeskydd, personifiering mot nätfiske, personifiering mot nätfiske, personifiering av användare mot nätfiske, förfalskning mot nätfiske, personifiering mot nätfiske, Program mot skadlig programvara, Säkra bifogade filer, ETR-regler (Enterprise Transport Rules)</span><span class="sxs-lookup"><span data-stu-id="6f258-163">Action policy that took effect: Antispam high-confidence, Antispam, Antispam bulk mail, Antispam phishing, Anti-phishing domain impersonation, Anti-phishing user impersonation, Anti-phishing spoof, Anti-phishing graph impersonation, Antimalware, Safe Attachments, Enterprise Transport Rules (ETR)</span></span> |
| `EmailActionPolicyGuid` | <span data-ttu-id="6f258-164">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-164">string</span></span> | <span data-ttu-id="6f258-165">Unikt ID för principen som avgör den slutliga e-poståtgärden</span><span class="sxs-lookup"><span data-stu-id="6f258-165">Unique identifier for the policy that determined the final mail action</span></span> |
| `AttachmentCount` | <span data-ttu-id="6f258-166">int</span><span class="sxs-lookup"><span data-stu-id="6f258-166">int</span></span> | <span data-ttu-id="6f258-167">Antal bifogade filer i e-postmeddelandet</span><span class="sxs-lookup"><span data-stu-id="6f258-167">Number of attachments in the email</span></span> |
| `UrlCount` | <span data-ttu-id="6f258-168">int</span><span class="sxs-lookup"><span data-stu-id="6f258-168">int</span></span> | <span data-ttu-id="6f258-169">Antal inbäddade URL:er i e-postmeddelandet</span><span class="sxs-lookup"><span data-stu-id="6f258-169">Number of embedded URLs in the email</span></span> |
| `EmailLanguage` | <span data-ttu-id="6f258-170">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-170">string</span></span> | <span data-ttu-id="6f258-171">Upptäckt språk för e-postinnehållet</span><span class="sxs-lookup"><span data-stu-id="6f258-171">Detected language of the email content</span></span> |
| `Connectors` | <span data-ttu-id="6f258-172">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-172">string</span></span> | <span data-ttu-id="6f258-173">Anpassade instruktioner som definierar organisationens e-postflöde och hur e-posten har dirigerats</span><span class="sxs-lookup"><span data-stu-id="6f258-173">Custom instructions that define organizational mail flow and how the email was routed</span></span> |
| `OrgLevelAction` | <span data-ttu-id="6f258-174">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-174">string</span></span> | <span data-ttu-id="6f258-175">Åtgärder som vidtas på e-postmeddelandet som svar på matchningar mot en princip som definierats på organisationsnivå</span><span class="sxs-lookup"><span data-stu-id="6f258-175">Action taken on the email in response to matches to a policy defined at the organizational level</span></span> |
| `OrgLevelPolicy` | <span data-ttu-id="6f258-176">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-176">string</span></span> | <span data-ttu-id="6f258-177">Organisationsprincip som utlöste e-postmeddelandets åtgärd</span><span class="sxs-lookup"><span data-stu-id="6f258-177">Organizational policy that triggered the action taken on the email</span></span> |
| `UserLevelAction` | <span data-ttu-id="6f258-178">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-178">string</span></span> | <span data-ttu-id="6f258-179">Åtgärd som vidtas på e-postmeddelandet som svar på matchningar mot en postlådeprincip som definieras av mottagaren</span><span class="sxs-lookup"><span data-stu-id="6f258-179">Action taken on the email in response to matches to a mailbox policy defined by the recipient</span></span> |
| `UserLevelPolicy` | <span data-ttu-id="6f258-180">sträng</span><span class="sxs-lookup"><span data-stu-id="6f258-180">string</span></span> | <span data-ttu-id="6f258-181">Postlådeprincip för slutanvändare som utlöste åtgärden för e-postmeddelandet</span><span class="sxs-lookup"><span data-stu-id="6f258-181">End-user mailbox policy that triggered the action taken on the email</span></span> |
| `ReportId` | <span data-ttu-id="6f258-182">long</span><span class="sxs-lookup"><span data-stu-id="6f258-182">long</span></span> | <span data-ttu-id="6f258-183">Händelseidentifierare baserat på en räknare för upprepande händelser.</span><span class="sxs-lookup"><span data-stu-id="6f258-183">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="6f258-184">För att identifiera unika händelser måste den här kolumnen användas tillsammans med kolumnerna DeviceName och Timestamp.</span><span class="sxs-lookup"><span data-stu-id="6f258-184">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="6f258-185">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6f258-185">Related topics</span></span>

- [<span data-ttu-id="6f258-186">Översikt över avancerad jakt</span><span class="sxs-lookup"><span data-stu-id="6f258-186">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6f258-187">Lär dig frågespråket</span><span class="sxs-lookup"><span data-stu-id="6f258-187">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6f258-188">Använda delade frågor</span><span class="sxs-lookup"><span data-stu-id="6f258-188">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="6f258-189">Jaga över olika enheter, e-postmeddelanden, appar och identiteter</span><span class="sxs-lookup"><span data-stu-id="6f258-189">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="6f258-190">Förstå schemat</span><span class="sxs-lookup"><span data-stu-id="6f258-190">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6f258-191">Använda metodtips för frågor</span><span class="sxs-lookup"><span data-stu-id="6f258-191">Apply query best practices</span></span>](advanced-hunting-best-practices.md)