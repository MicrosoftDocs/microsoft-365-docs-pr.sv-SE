---
title: Kampanjvyer i ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Läs mer om kampanjvyer i det avancerade skydd mot office 365-hotet.
ms.openlocfilehash: 5441c877dac70330bf1e5653983494be5b1b3293
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209601"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="9e31e-103">Kampanjvyer i ATP</span><span class="sxs-lookup"><span data-stu-id="9e31e-103">Campaign Views in ATP</span></span>

<span data-ttu-id="9e31e-104">Kampanjvyer är en funktion i Advanced Threat Protection (ATP) i Security & Compliance Center som identifierar och kategoriserar nätfiskeattacker i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="9e31e-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="9e31e-105">Kampanjvyer kan hjälpa dig att:</span><span class="sxs-lookup"><span data-stu-id="9e31e-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="9e31e-106">Undersök och reagera effektivt på nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="9e31e-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="9e31e-107">Bättre förstå omfattningen av attacken.</span><span class="sxs-lookup"><span data-stu-id="9e31e-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="9e31e-108">Visa värde för beslutsfattare.</span><span class="sxs-lookup"><span data-stu-id="9e31e-108">Show value to decision makers.</span></span>

<span data-ttu-id="9e31e-109">Med kampanjvyer kan du se helheten av en attack snabbare och mer komplett än någon människa.</span><span class="sxs-lookup"><span data-stu-id="9e31e-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="9e31e-110">Vad är en kampanj?</span><span class="sxs-lookup"><span data-stu-id="9e31e-110">What is a campaign?</span></span>

<span data-ttu-id="9e31e-111">En kampanj är en samordnad e-postattack mot en eller flera organisationer.</span><span class="sxs-lookup"><span data-stu-id="9e31e-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="9e31e-112">E-postattacker som stjäl referenser och företagsdata är en stor och lukrativ bransch.</span><span class="sxs-lookup"><span data-stu-id="9e31e-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="9e31e-113">I takt med att tekniken ökar i ett försök att stoppa attacker ändrar angripare sina metoder i ett försök att säkerställa fortsatt framgång.</span><span class="sxs-lookup"><span data-stu-id="9e31e-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="9e31e-114">Microsoft utnyttjar de stora mängderna anti-phishing, anti-spam och anti-malware data över hela tjänsten för att identifiera kampanjer.</span><span class="sxs-lookup"><span data-stu-id="9e31e-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="9e31e-115">Vi analyserar och klassificerar attackinformationen enligt flera faktorer.</span><span class="sxs-lookup"><span data-stu-id="9e31e-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="9e31e-116">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="9e31e-116">For example:</span></span>

- <span data-ttu-id="9e31e-117">**Attack källa:** Källa IP-adresser och avsändare e-domäner.</span><span class="sxs-lookup"><span data-stu-id="9e31e-117">**Attack source**: Source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="9e31e-118">**Attack meddelandeegenskaper:** Innehållet, stil och ton i attackmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="9e31e-118">**Attack message properties**: The content, style, and tone of the attack messages.</span></span>

- <span data-ttu-id="9e31e-119">**Attackmottagare:** Mottagardomäner, mottagarjobbsfunktioner (administratörer, chefer osv.), företagstyper (stora, små, offentliga, privata osv.) och branscher.</span><span class="sxs-lookup"><span data-stu-id="9e31e-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="9e31e-120">**Attack nyttolast:** Skadliga länkar, bilagor eller andra nyttolaster i attackmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="9e31e-120">**Attack payload**: Malicious links, attachments, or other payloads in the attack messages.</span></span>

<span data-ttu-id="9e31e-121">En kampanj kan vara kortlivad eller sträcka sig över flera dagar, veckor eller månader med aktiva och inaktiva perioder.</span><span class="sxs-lookup"><span data-stu-id="9e31e-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="9e31e-122">En kampanj kan startas mot din specifika organisation, eller så kan din organisation vara en del av en större kampanj för flera företag.</span><span class="sxs-lookup"><span data-stu-id="9e31e-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="9e31e-123">Kampanjvyer security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="9e31e-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="9e31e-124">Kampanjvyer är tillgängliga i [Security & Compliance Center](https://protection.office.com) vid **Threat management** \> **hothanteringskampanjer**.</span><span class="sxs-lookup"><span data-stu-id="9e31e-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**.</span></span>

![Översikt över kampanjer i Security & Compliance Center](../../media/campaigns-overview.png)

<span data-ttu-id="9e31e-126">Du kan också komma åt kampanjvyn från:</span><span class="sxs-lookup"><span data-stu-id="9e31e-126">You can also get to Campaigns View from:</span></span>

- <span data-ttu-id="9e31e-127">**Hantering av** \> hot **Explorer** \> **Visa** \> **Kampanjer**</span><span class="sxs-lookup"><span data-stu-id="9e31e-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="9e31e-128">**Hantering av** \> hot **Explorer** \> **Visa** \> **Alla e-postmeddelanden** \> **Kampanj**</span><span class="sxs-lookup"><span data-stu-id="9e31e-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign**</span></span>

> [!TIP]
> <span data-ttu-id="9e31e-129">Om du inte ser några kampanjdata kan du prova att ändra datumintervallet.</span><span class="sxs-lookup"><span data-stu-id="9e31e-129">If you don't see any campaign data, try changing the date range.</span></span>

<span data-ttu-id="9e31e-130">Översiktssidan visar följande information om kampanjen:</span><span class="sxs-lookup"><span data-stu-id="9e31e-130">The overview page shows the following information about the campaign:</span></span>

- <span data-ttu-id="9e31e-131">**Namn**</span><span class="sxs-lookup"><span data-stu-id="9e31e-131">**Name**</span></span>

- <span data-ttu-id="9e31e-132">**Exempelämne**: Ämnesraden för ett av meddelandena i kampanjen.</span><span class="sxs-lookup"><span data-stu-id="9e31e-132">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="9e31e-133">Observera att alla meddelanden i kampanjen inte nödvändigtvis har samma ämne.</span><span class="sxs-lookup"><span data-stu-id="9e31e-133">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="9e31e-134">**Typ:** För närvarande är detta värde alltid **Phish**.</span><span class="sxs-lookup"><span data-stu-id="9e31e-134">**Type**: Currently, this value is always **Phish**.</span></span>

- <span data-ttu-id="9e31e-135">**Undertyp:** Om tillgängligt, det varumärke som phished av denna kampanj.</span><span class="sxs-lookup"><span data-stu-id="9e31e-135">**Subtype**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="9e31e-136">När identifieringen drivs av **ATP-teknik** läggs prefixet ATP till undertypsvärdet.</span><span class="sxs-lookup"><span data-stu-id="9e31e-136">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="9e31e-137">**Mottagare**: Antalet användare som har utsatts för den här kampanjen.</span><span class="sxs-lookup"><span data-stu-id="9e31e-137">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="9e31e-138">**Inkorg**: Antalet användare som har fått meddelanden från den här kampanjen i inkorgen (inte levererat till Skräppost).</span><span class="sxs-lookup"><span data-stu-id="9e31e-138">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to Junk).</span></span>

- <span data-ttu-id="9e31e-139">**Klickad :** Antalet användare som klickade på webbadressen i nätfiskemeddelandet.</span><span class="sxs-lookup"><span data-stu-id="9e31e-139">**Clicked**: The number of users that clicked on the URL in the phishing message.</span></span>

- <span data-ttu-id="9e31e-140">**Klicka på Betyg:** Procentsatsen som beräknas av "**Klickad**  /  **inkorg**".</span><span class="sxs-lookup"><span data-stu-id="9e31e-140">**Click Rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="9e31e-141">Det här värdet är en indikator på kampanjens effektivitet och om mottagarna kunde identifiera meddelandet som nätfiske och undvika att klicka på nyttolast-url:en.</span><span class="sxs-lookup"><span data-stu-id="9e31e-141">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

- <span data-ttu-id="9e31e-142">**Besökt:** Hur många användare som faktiskt gjorde det genom att nyttolasten webbplats.</span><span class="sxs-lookup"><span data-stu-id="9e31e-142">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="9e31e-143">Om det finns klickade värden, men säkra länkar **blockeras** åtkomst till webbplatsen, kommer detta värde att vara noll.</span><span class="sxs-lookup"><span data-stu-id="9e31e-143">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="9e31e-144">När du klickar på namnet på en kampanj visas kampanjinformationen i ett utfällbart utfällbart.</span><span class="sxs-lookup"><span data-stu-id="9e31e-144">When you click on the name of a campaign, the campaign details appears in a flyout.</span></span>

## <a name="campaign-details"></a><span data-ttu-id="9e31e-145">Information om kampanj</span><span class="sxs-lookup"><span data-stu-id="9e31e-145">Campaign details</span></span>

<span data-ttu-id="9e31e-146">I vyn Kampanjinformation finns mycket information om kampanjen:</span><span class="sxs-lookup"><span data-stu-id="9e31e-146">In the campaign details view, a lot of information is available about the campaign:</span></span>

- <span data-ttu-id="9e31e-147">Kampanjinformation:</span><span class="sxs-lookup"><span data-stu-id="9e31e-147">Campaign information:</span></span>

  - <span data-ttu-id="9e31e-148">**ID**: Den unika kampanjidentifieraren.</span><span class="sxs-lookup"><span data-stu-id="9e31e-148">**ID**: The unique campaign identifier.</span></span>

  - <span data-ttu-id="9e31e-149">**Startad** och **avslutad:** det datumintervallfilter som du har valt.</span><span class="sxs-lookup"><span data-stu-id="9e31e-149">**Started** and **Ended**: the date range filter you selected.</span></span>

  - <span data-ttu-id="9e31e-150">**Effekt**: Följande data för det datumintervallfilter du valde:</span><span class="sxs-lookup"><span data-stu-id="9e31e-150">**Impact**: The following data for the date range filter you selected:</span></span>
  
    - <span data-ttu-id="9e31e-151">Det totala antalet mottagare.</span><span class="sxs-lookup"><span data-stu-id="9e31e-151">The total number of recipients.</span></span>

    - <span data-ttu-id="9e31e-152">Antalet meddelanden som var "Inkorgade" (det vill än levereras till Inkorgen, inte till Skräppost).</span><span class="sxs-lookup"><span data-stu-id="9e31e-152">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to Junk).</span></span>

    - <span data-ttu-id="9e31e-153">Hur många användare klickade på webbadressens nyttolast i nätfiskemeddelandet.</span><span class="sxs-lookup"><span data-stu-id="9e31e-153">How many users clicked on the URL payload in the phishing message.</span></span>

    - <span data-ttu-id="9e31e-154">Howe många användare besökte webbadressen.</span><span class="sxs-lookup"><span data-stu-id="9e31e-154">Howe many users visited the URL.</span></span>

  - <span data-ttu-id="9e31e-155">En tidslinje för kampanjaktivitet: När kampanjen startades och avslutades och volymen av meddelanden över tid.</span><span class="sxs-lookup"><span data-stu-id="9e31e-155">A timeline of campaign activity: When the campaign started and ended, and the volume of messages over time.</span></span>

### <a name="campaign-flow"></a><span data-ttu-id="9e31e-156">Kampanjflöde</span><span class="sxs-lookup"><span data-stu-id="9e31e-156">Campaign flow</span></span>

<span data-ttu-id="9e31e-157">Viktiga detaljer om kampanjen presenteras i ett horisontellt flödesdiagram (ett _sankey-diagram)_ i avsnittet **Flöde.**</span><span class="sxs-lookup"><span data-stu-id="9e31e-157">Important details about the campaign are presented in a horizontal flow diagram (known as a _Sankey_ diagram) in the **Flow** section.</span></span> <span data-ttu-id="9e31e-158">Dessa uppgifter hjälper dig att förstå delarna av kampanjen och den potentiella effekten i din organisation.</span><span class="sxs-lookup"><span data-stu-id="9e31e-158">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

![Kampanjinformation som inte innehåller klick på användarens webbadress](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="9e31e-160">Om du hovrar över ett vågrätt band i diagrammet visas antalet relaterade meddelanden (till exempel meddelanden från en viss käll-IP, meddelanden från käll-IP med den angivna avsändardomänen osv.).</span><span class="sxs-lookup"><span data-stu-id="9e31e-160">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="9e31e-161">Diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="9e31e-161">The diagram contains the following information:</span></span>

- <span data-ttu-id="9e31e-162">**Avsändare-IPs**</span><span class="sxs-lookup"><span data-stu-id="9e31e-162">**Sender IPs**</span></span>

- <span data-ttu-id="9e31e-163">**Avsändaredomäner**</span><span class="sxs-lookup"><span data-stu-id="9e31e-163">**Sender domains**</span></span>

- <span data-ttu-id="9e31e-164">**Filtrera domar:** Värdena här är relaterade till tillgängliga phishing och spam filtrering domar som beskrivs i [Anti-spam meddelande rubriker](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="9e31e-164">**Filter verdicts**: The values here are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="9e31e-165">De tillgängliga värdena beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="9e31e-165">The available values are described in the following table:</span></span>

  |<span data-ttu-id="9e31e-166">Value</span><span class="sxs-lookup"><span data-stu-id="9e31e-166">Value</span></span>|<span data-ttu-id="9e31e-167">Spam filter dom</span><span class="sxs-lookup"><span data-stu-id="9e31e-167">Spam filter verdict</span></span>|<span data-ttu-id="9e31e-168">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="9e31e-168">Description</span></span>|
  |:-----|:-----|:-----|
  | <span data-ttu-id="9e31e-169">**Tillåtet**</span><span class="sxs-lookup"><span data-stu-id="9e31e-169">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="9e31e-170">Meddelandet markerades som inte skräppost och/eller överhoppade filtrering innan det utvärderades av skräppostfiltrering (till exempel av en regel för e-postflöde, även känd som en transportregel).</span><span class="sxs-lookup"><span data-stu-id="9e31e-170">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="9e31e-171">Meddelandet hoppade över skräppostfiltrering av andra skäl (till exempel verkar avsändaren och mottagaren befinna sig i samma organisation).</span><span class="sxs-lookup"><span data-stu-id="9e31e-171">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="9e31e-172">**Blockerade**</span><span class="sxs-lookup"><span data-stu-id="9e31e-172">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="9e31e-173">Meddelandet markerades som skräppost innan det utvärderades av skräppostfiltrering (till exempel av en regel för e-postflöde).</span><span class="sxs-lookup"><span data-stu-id="9e31e-173">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="9e31e-174">**Upptäckt**</span><span class="sxs-lookup"><span data-stu-id="9e31e-174">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="9e31e-175">Meddelandet markerades som skräppost av skräppostfiltret.</span><span class="sxs-lookup"><span data-stu-id="9e31e-175">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="9e31e-176">**Har inte identifierats**</span><span class="sxs-lookup"><span data-stu-id="9e31e-176">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="9e31e-177">Meddelandet markerades som inte skräppost genom skräppostfiltrering.</span><span class="sxs-lookup"><span data-stu-id="9e31e-177">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="9e31e-178">**Släppt**</span><span class="sxs-lookup"><span data-stu-id="9e31e-178">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="9e31e-179">Meddelandet hoppade över skräppostfiltrering eftersom det släpptes från karantänen.</span><span class="sxs-lookup"><span data-stu-id="9e31e-179">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="9e31e-180">**Klient tillåt**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9e31e-180">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="9e31e-181">Meddelandet hoppade över skräppostfiltrering på grund av policyinställningar för skräppost (till exempel var avsändaren med i listan över tillåtna avsändare eller tillåtna domänlistan).</span><span class="sxs-lookup"><span data-stu-id="9e31e-181">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="9e31e-182">**Hyresgästblock**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="9e31e-182">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="9e31e-183">Meddelandet blockerades av skräppostfiltrering på grund av policyinställningar mot skräppost (till exempel var avsändaren i listan över tillåtna avsändare eller tillåtna domänlistan).</span><span class="sxs-lookup"><span data-stu-id="9e31e-183">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="9e31e-184">**Tillåt användare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9e31e-184">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="9e31e-185">Meddelandet hoppade över skräppostfiltrering eftersom avsändaren fanns i en användares lista över betrodda avsändare i Outlook.</span><span class="sxs-lookup"><span data-stu-id="9e31e-185">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="9e31e-186">**Användarblock**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="9e31e-186">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="9e31e-187">Meddelandet blockerades av skräppostfiltrering eftersom avsändaren fanns i en användares lista blockerade avsändare i Outlook.</span><span class="sxs-lookup"><span data-stu-id="9e31e-187">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="9e31e-188">**Zap**</span><span class="sxs-lookup"><span data-stu-id="9e31e-188">**ZAP**</span></span>|<span data-ttu-id="9e31e-189">n/a</span><span class="sxs-lookup"><span data-stu-id="9e31e-189">n/a</span></span>|<span data-ttu-id="9e31e-190">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) vidtog åtgärder på det levererade meddelandet enligt dina anti-spam-principinställningar (flyttade till mappen Skräppost eller karantän).</span><span class="sxs-lookup"><span data-stu-id="9e31e-190">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|

  <span data-ttu-id="9e31e-191"><sup>\*</sup>Granska dina policyer mot skräppost, eftersom det tillåtna meddelandet sannolikt skulle ha blockerats av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="9e31e-191"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="9e31e-192"><sup>\*\*</sup>Granska dina policyer mot skräppost, eftersom dessa meddelanden ska sättas i karantän, inte levereras.</span><span class="sxs-lookup"><span data-stu-id="9e31e-192"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="9e31e-193">**Leveransplatser**: Du vill förmodligen undersöka meddelanden som faktiskt levererades till mottagare (antingen till inkorgen eller mappen Skräppost), även om användarna inte klickade på nyttolast-URL:en i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="9e31e-193">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="9e31e-194">Du kan också ta bort meddelandena i karantän från karantänen.</span><span class="sxs-lookup"><span data-stu-id="9e31e-194">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="9e31e-195">Mer information finns i [EOP i karantän](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="9e31e-195">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="9e31e-196">**Borttagen mapp**</span><span class="sxs-lookup"><span data-stu-id="9e31e-196">**Deleted folder**</span></span>

  - <span data-ttu-id="9e31e-197">**Tappade**</span><span class="sxs-lookup"><span data-stu-id="9e31e-197">**Dropped**</span></span>

  - <span data-ttu-id="9e31e-198">**Externt**: Mottagaren finns i din lokala e-postorganisation.</span><span class="sxs-lookup"><span data-stu-id="9e31e-198">**External**: The recipient is located in your on-premises email organization.</span></span>

  - <span data-ttu-id="9e31e-199">**Misslyckades**</span><span class="sxs-lookup"><span data-stu-id="9e31e-199">**Failed**</span></span>

  - <span data-ttu-id="9e31e-200">**Vidarebefordras**</span><span class="sxs-lookup"><span data-stu-id="9e31e-200">**Forwarded**</span></span>

  - <span data-ttu-id="9e31e-201">**Inkorg**</span><span class="sxs-lookup"><span data-stu-id="9e31e-201">**Inbox**</span></span>

  - <span data-ttu-id="9e31e-202">**Skräppostmapp**</span><span class="sxs-lookup"><span data-stu-id="9e31e-202">**Junk folder**</span></span>

  - <span data-ttu-id="9e31e-203">**Karantän**</span><span class="sxs-lookup"><span data-stu-id="9e31e-203">**Quarantine**</span></span>

  - <span data-ttu-id="9e31e-204">**Okänd**</span><span class="sxs-lookup"><span data-stu-id="9e31e-204">**Unknown**</span></span>

> [!NOTE]
> <span data-ttu-id="9e31e-205">I alla lager som innehåller fler än 10 objekt visas de 10 översta objekten, medan resten buntas ihop i **Andra**.</span><span class="sxs-lookup"><span data-stu-id="9e31e-205">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="9e31e-206">URL-klick</span><span class="sxs-lookup"><span data-stu-id="9e31e-206">URL clicks</span></span>

<span data-ttu-id="9e31e-207">När ett nätfiskemeddelande levereras till en mottagare (till inkorgen eller mappen Skräppost) finns det alltid en chans att användaren klickar på nyttolastadressen.</span><span class="sxs-lookup"><span data-stu-id="9e31e-207">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="9e31e-208">Att inte klicka på webbadressen i ett levererat meddelande är ett litet mått på framgång, men du måste ta reda på varför nätfiskemeddelandet levererades till deras postlåda från början.</span><span class="sxs-lookup"><span data-stu-id="9e31e-208">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="9e31e-209">Om en användare klickade på nyttolast-URL:en i nätfiskemeddelandet visas åtgärderna i området **URL-klick** i diagrammet i kampanjinformationsvyn.</span><span class="sxs-lookup"><span data-stu-id="9e31e-209">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="9e31e-210">**Tillåtet**</span><span class="sxs-lookup"><span data-stu-id="9e31e-210">**Allowed**</span></span>

- <span data-ttu-id="9e31e-211">**BlockPage**: Mottagaren klickade på nyttolast-URL:en, men deras åtkomst till den skadliga webbplatsen blockerades av [ATP Safe Links-principerna](atp-safe-links.md) i organisationen.</span><span class="sxs-lookup"><span data-stu-id="9e31e-211">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="9e31e-212">**BlockPageOverride**: Mottagaren klickade på nyttolastens URL i meddelandet, ATP Safe Links försökte stoppa dem, men de fick åsidosätta blocket.</span><span class="sxs-lookup"><span data-stu-id="9e31e-212">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="9e31e-213">Du måste undersöka dina principer för [säkra länkar](set-up-atp-safe-links-policies.md) för att se varför användare tillåts åsidosätta domen om säkra länkar och fortsätta till den skadliga webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="9e31e-213">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="9e31e-214">**PendingDetonationPage**: ATP Säkra bilagor håller på att öppna nyttolast-URL:en i en virtuell datormiljö och se vad som händer.</span><span class="sxs-lookup"><span data-stu-id="9e31e-214">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="9e31e-215">**VäntandeDetonationPageOverride**: Mottagaren tilläts åsidosätta detonationsprocessen för nyttolasten och öppna URL:en utan att vänta på resultatet.</span><span class="sxs-lookup"><span data-stu-id="9e31e-215">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="9e31e-216">Flikar</span><span class="sxs-lookup"><span data-stu-id="9e31e-216">Tabs</span></span>

<span data-ttu-id="9e31e-217">Det finns flera flikar i vyn kampanjinformation som gör att du kan undersöka kampanjen ytterligare.</span><span class="sxs-lookup"><span data-stu-id="9e31e-217">There are several tabs in the campaign details view that allow you to further investigate the campaign.</span></span>

- <span data-ttu-id="9e31e-218">**URL-klick**: Om användarna inte klickade på nyttolastadressen i nätfiskemeddelandet är det här avsnittet tomt.</span><span class="sxs-lookup"><span data-stu-id="9e31e-218">**URL Clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="9e31e-219">Om en användare kunde klicka på webbadressen fylls följande värden i:</span><span class="sxs-lookup"><span data-stu-id="9e31e-219">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="9e31e-220">**Användaren**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9e31e-220">**User**<sup>\*</sup></span></span>

  - <span data-ttu-id="9e31e-221">**Url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9e31e-221">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="9e31e-222">**Klicka på Tid**</span><span class="sxs-lookup"><span data-stu-id="9e31e-222">**Click Time**</span></span>

  - <span data-ttu-id="9e31e-223">**Klicka på Åtgärd**</span><span class="sxs-lookup"><span data-stu-id="9e31e-223">**Click Action**</span></span>

- <span data-ttu-id="9e31e-224">**Avsändare-IPs**</span><span class="sxs-lookup"><span data-stu-id="9e31e-224">**Sender IPs**</span></span>

  - <span data-ttu-id="9e31e-225">**IP-adress för avsändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9e31e-225">**Sender IP**<sup>\*</sup></span></span>

  - <span data-ttu-id="9e31e-226">**Totalt antal**</span><span class="sxs-lookup"><span data-stu-id="9e31e-226">**Total Count**</span></span>

  - <span data-ttu-id="9e31e-227">**Antal inkorgar**</span><span class="sxs-lookup"><span data-stu-id="9e31e-227">**Inboxed Count**</span></span>

  - <span data-ttu-id="9e31e-228">**Blockerat antal**</span><span class="sxs-lookup"><span data-stu-id="9e31e-228">**Blocked Count**</span></span>

  - <span data-ttu-id="9e31e-229">**SPF Godkänd:** Avsändaren autentiserades av [Avsändarens policyram (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="9e31e-229">**SPF Passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="9e31e-230">En avsändare som inte skickar SPF-validering anger att avsändaren inte autentiseras eller att meddelandet förfalskar en legitim avsändare.</span><span class="sxs-lookup"><span data-stu-id="9e31e-230">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="9e31e-231">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="9e31e-231">**Senders**</span></span>

  - <span data-ttu-id="9e31e-232">**Avsändare**: Det här är den faktiska avsändaradressen i kommandot SMTP MAIL FROM, vilket inte nödvändigtvis är den Från: e-postadress som användarna ser i sina e-postklienter.</span><span class="sxs-lookup"><span data-stu-id="9e31e-232">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>

  - <span data-ttu-id="9e31e-233">**Totalt antal**</span><span class="sxs-lookup"><span data-stu-id="9e31e-233">**Total Count**</span></span>

  - <span data-ttu-id="9e31e-234">**Inkorg**</span><span class="sxs-lookup"><span data-stu-id="9e31e-234">**Inboxed**</span></span>

  - <span data-ttu-id="9e31e-235">**Inte inkorg**</span><span class="sxs-lookup"><span data-stu-id="9e31e-235">**Not Inboxed**</span></span>

  - <span data-ttu-id="9e31e-236">**DKIM-godkänd:** Avsändaren autentiserades av [DKIM (Domain Keys Identified Mail).](support-for-validation-of-dkim-signed-messages.md)</span><span class="sxs-lookup"><span data-stu-id="9e31e-236">**DKIM Passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="9e31e-237">En avsändare som inte klarar DKIM-validering anger att avsändaren inte autentiseras eller att meddelandet förfalskar en legitim avsändare.</span><span class="sxs-lookup"><span data-stu-id="9e31e-237">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

  - <span data-ttu-id="9e31e-238">**DMARC Godkänd:** Avsändaren autentiserades av [domänbaserad meddelandeautentisering, rapportering och konformance (DMARC)](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="9e31e-238">**DMARC Passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="9e31e-239">En avsändare som inte klarar DMARC-validering anger att avsändaren inte autentiseras eller att meddelandet förfalskar en legitim avsändare.</span><span class="sxs-lookup"><span data-stu-id="9e31e-239">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="9e31e-240">**Nyttolaster**</span><span class="sxs-lookup"><span data-stu-id="9e31e-240">**Payloads**</span></span>

  - <span data-ttu-id="9e31e-241">**Url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9e31e-241">**URL**<sup>\*</sup></span></span>

  - <span data-ttu-id="9e31e-242">**Totalt antal**</span><span class="sxs-lookup"><span data-stu-id="9e31e-242">**Total Count**</span></span>

<span data-ttu-id="9e31e-243"><sup>\*</sup>Om du klickar på det här värdet öppnas ett nytt utfällbart objekt som innehåller mer information om det angivna objektet (användare, URL osv.) ovanpå kampanjinformationsvyn.</span><span class="sxs-lookup"><span data-stu-id="9e31e-243"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="9e31e-244">Om du vill återgå till kampanjinformationsvyn klickar du på **Klar** i det nya utfällbara resultatet.</span><span class="sxs-lookup"><span data-stu-id="9e31e-244">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="9e31e-245">Knappar</span><span class="sxs-lookup"><span data-stu-id="9e31e-245">Buttons</span></span>

<span data-ttu-id="9e31e-246">Med knapparna i vyn kampanjinformation kan du använda kraften i Threat Explorer för att undersöka kampanjen ytterligare.</span><span class="sxs-lookup"><span data-stu-id="9e31e-246">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="9e31e-247">**Utforska kampanj**: Öppnar en ny sökflik för Threat Explorer med värdet **Kampanj-ID** som sökfilter.</span><span class="sxs-lookup"><span data-stu-id="9e31e-247">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="9e31e-248">**Utforska inkorgsmeddelanden:** Öppnar en ny sökflik för Hot Explorer med **kampanj-ID** och **leveransplats: Inkorgen** som sökfilter.</span><span class="sxs-lookup"><span data-stu-id="9e31e-248">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
