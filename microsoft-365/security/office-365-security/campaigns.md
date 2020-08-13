---
title: Kampanjmallar i ATP
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
description: Lär dig mer om kampanjmallar i Office 365 Avancerat skydd.
ms.openlocfilehash: b7078188d8e01f27e6941c3f61f4ef20a004606c
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653239"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="7dcbd-103">Kampanjmallar i ATP</span><span class="sxs-lookup"><span data-stu-id="7dcbd-103">Campaign Views in ATP</span></span>

<span data-ttu-id="7dcbd-104">Kampanjmallar är en funktion i avancerat skydd (ATP) i säkerhets & efterlevnad som identifierar och kategoriserar nät fiske attacker i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="7dcbd-105">Med hjälp av kampanjmallar kan du:</span><span class="sxs-lookup"><span data-stu-id="7dcbd-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="7dcbd-106">Undersök och svara på nät fiske attacker effektivt.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="7dcbd-107">Bättre förståelse för attackens omfattning.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="7dcbd-108">Visa värde för besluts fattare.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-108">Show value to decision makers.</span></span>

<span data-ttu-id="7dcbd-109">Med kampanjmallar kan du se en stor bild av en attack snabbare och mer komplett än de som är på människa.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="7dcbd-110">Vad är en kampanj?</span><span class="sxs-lookup"><span data-stu-id="7dcbd-110">What is a campaign?</span></span>

<span data-ttu-id="7dcbd-111">En kampanj är en koordinerad e-postattack mot en eller flera organisationer.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="7dcbd-112">E-postattacker som stjälar uppgifter och företags data är en stor och Lucrative bransch.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="7dcbd-113">Eftersom teknikerna ökar för att förhindra attacker, ändrar angripare sina metoder för att säkerställa fortsatt framgång.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="7dcbd-114">Microsoft utnyttjar de stora mängderna nätfiske, anti-spam och data mot skadlig program vara via hela tjänsten för att identifiera kampanjer.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="7dcbd-115">Vi analyserar och klassificerar angrepps informationen enligt flera faktorer.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="7dcbd-116">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="7dcbd-116">For example:</span></span>

- <span data-ttu-id="7dcbd-117">**Attack källa**: käll-IP-adresser och e-postdomäner.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-117">**Attack source**: The source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="7dcbd-118">**Egenskaper för attack meddelande**: innehåll, format och ton för meddelanden.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-118">**Attack message properties**: The content, style, and tone of the messages.</span></span>

- <span data-ttu-id="7dcbd-119">**Attack mottagare**: mottagar domäner, funktioner för mottagaren (administratörer, chefer etc.), företags typer (stort, litet, offentligt, privat etc.) och branscher.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="7dcbd-120">**Attack-nyttolast**: illasinnade länkar, bifogade filer eller andra nytto laster i meddelanden.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-120">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="7dcbd-121">En kampanj kan vara kort livs längd eller kunna omfatta flera dagar, veckor eller månader med aktiva och inaktiva perioder.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="7dcbd-122">En kampanj kan startas mot din specifika organisation, eller så kan din organisation vara en del av en större kampanj i flera företag.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="7dcbd-123">Kampanjmallar säkerhets &</span><span class="sxs-lookup"><span data-stu-id="7dcbd-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="7dcbd-124">Kampanjmallar är tillgängligt i [säkerhets & Compliance Center](https://protection.office.com) med kampanjer för **Threat Management** \> **Campaigns**eller direkt vid <https://protection.office.com/campaigns> .</span><span class="sxs-lookup"><span data-stu-id="7dcbd-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![Översikt över kampanjer i säkerhets & Compliance Center](../../media/campaigns-overview.png)

<span data-ttu-id="7dcbd-126">Du kan också komma åt kampanjmallar från:</span><span class="sxs-lookup"><span data-stu-id="7dcbd-126">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="7dcbd-127">**Threat Management** \> **Utforskaren** \> **Visa** \> **Kampanjer**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="7dcbd-128">**Threat Management** \> **Utforskaren** \> **Visa** \> **All e-post** \> Fliken **kampanj**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="7dcbd-129">**Threat Management** \> **Utforskaren** \> **Visa** \> **Phish** \> Fliken **kampanj**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-129">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="7dcbd-130">**Threat Management** \> **Utforskaren** \> **Visa** \> **Malware** \> Fliken **kampanj**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-130">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="7dcbd-131">För att få åtkomst till kampanjmallar måste du vara medlem i roll grupperna **organisations hantering**, **säkerhets administratör**eller **säkerhets läsare** i säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-131">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="7dcbd-132">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="7dcbd-133">Översikt över kampanjer</span><span class="sxs-lookup"><span data-stu-id="7dcbd-133">Campaigns overview</span></span>

<span data-ttu-id="7dcbd-134">Sidan översikt visar information om alla kampanjer.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-134">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="7dcbd-135">På fliken standard **kampanj** visas ett stapeldiagram som visar antalet mottagare per dag i området **kampanj typ** .</span><span class="sxs-lookup"><span data-stu-id="7dcbd-135">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="7dcbd-136">Som standard visar diagrammet både **Phish** och **malware** data.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-136">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="7dcbd-137">Om du inte ser några kampanj data kan du försöka ändra datum intervallet eller [filtren](#filters-and-settings).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-137">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="7dcbd-138">På resten av översikts sidan visas följande information på fliken **kampanj** :</span><span class="sxs-lookup"><span data-stu-id="7dcbd-138">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="7dcbd-139">**Namn**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-139">**Name**</span></span>

- <span data-ttu-id="7dcbd-140">**Exempel ämne**: ämnes raden för ett av meddelandena i kampanjen.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-140">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="7dcbd-141">Observera att alla meddelanden i kampanjen inte nödvändigt vis har samma ämne.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-141">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="7dcbd-142">**Riktad**: den procents ATS som beräknas av: (antalet mottagare av kampanjen i organisationen)/(det totala antalet mottagare i kampanjen i alla organisationer i tjänsten).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-142">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="7dcbd-143">Det här värdet anger i vilken grad kampanjen specifikt riktas till din organisation (ett högre värde) kontra direkt till andra organisationer i tjänsten (ett lägre värde).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-143">This value indicates the degree to which the campaign is specifically directed at your organization (a higher value) vs. directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="7dcbd-144">**Typ**: det här värdet är antingen **Phish** eller **skadlig program vara**.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-144">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="7dcbd-145">**Undertyp**: det här värdet innehåller mer information om kampanjen.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-145">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="7dcbd-146">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="7dcbd-146">For example:</span></span>

  - <span data-ttu-id="7dcbd-147">**Phish**: där det är tillgängligt, det märke som phished av kampanjen.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-147">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="7dcbd-148">Till exempel, `Microsoft` ,,, `365` `Unknown` `Outlook` eller `DocuSign` .</span><span class="sxs-lookup"><span data-stu-id="7dcbd-148">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="7dcbd-149">**Skadlig kod**: till exempel `HTML/PHISH` eller `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="7dcbd-149">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="7dcbd-150">Där det är tillgängligt, det märke som phished av kampanjen.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-150">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="7dcbd-151">När identifieringen drivs av ATP-teknologin används prefixet **ATP-** och värdet för undertyp.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-151">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="7dcbd-152">**Mottagare**: antalet användare som är riktade till den här kampanjen.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-152">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="7dcbd-153">**Inkorgen**: antalet användare som fick meddelanden från den här kampanjen i sin inkorg (levereras inte till mappen skräp post).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-153">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="7dcbd-154">**Klickar**du på: antalet användare som klickade på URL-adressen eller öppnade den bifogade filen i nät fiske meddelandet.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-154">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="7dcbd-155">**Klicka på ränta**: procent satsen beräknat av "**klickade**på  /  **Inkorgen**".</span><span class="sxs-lookup"><span data-stu-id="7dcbd-155">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="7dcbd-156">Det här värdet är en indikator på kampanjens effektivitet och om mottagarna kan identifiera meddelandet som nätfiske och undvika att klicka på URL: en för nytto lasten.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-156">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

  <span data-ttu-id="7dcbd-157">Observera att det här värdet inte används för kampanjer med skadlig program vara.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-157">Note that this value isn't used in malware campaigns.</span></span>

- <span data-ttu-id="7dcbd-158">**Besökt**: hur många användare faktiskt gjorde det till nytto Last webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-158">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="7dcbd-159">Om du **klickade på** värden, men säkra länkar blockerade åtkomst till webbplatsen, är det här värdet noll.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-159">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="7dcbd-160">På fliken **kampanj källa** visas meddelande källorna på en karta över hela världen.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-160">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="7dcbd-161">Filter och inställningar</span><span class="sxs-lookup"><span data-stu-id="7dcbd-161">Filters and settings</span></span>

<span data-ttu-id="7dcbd-162">Högst upp på sidan kampanjmallar finns det flera filter-och frågeinställningar som hjälper dig att hitta och isolera specifika kampanjer.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-162">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![Kampanj filter](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="7dcbd-164">Den mest grundläggande filtreringen du kan göra är start datum och slut tid.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-164">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="7dcbd-165">Om du vill filtrera vyn ytterligare kan du utföra en enskild egenskap med filtrering av flera värden genom att klicka på knappen **kampanj typ** , välja och sedan klicka på **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-165">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="7dcbd-166">De tillgängliga kampanj egenskaperna beskrivs i följande lista:</span><span class="sxs-lookup"><span data-stu-id="7dcbd-166">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="7dcbd-167">Basisk</span><span class="sxs-lookup"><span data-stu-id="7dcbd-167">Basic</span></span>

  - <span data-ttu-id="7dcbd-168">**Kampanj typ**: Välj **skadlig** eller **Phish**.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-168">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="7dcbd-169">Om du avmarkerar valen är det samma resultat som att markera båda.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-169">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="7dcbd-170">**Kampanj namn**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-170">**Campaign name**</span></span>
  - <span data-ttu-id="7dcbd-171">**Kampanj under typ**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-171">**Campaign subtype**</span></span>
  - <span data-ttu-id="7dcbd-172">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-172">**Sender**</span></span>
  - <span data-ttu-id="7dcbd-173">**Mottagarna**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-173">**Recipients**</span></span>
  - <span data-ttu-id="7dcbd-174">**Avsändningsdomän**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-174">**Sender domain**</span></span>
  - <span data-ttu-id="7dcbd-175">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-175">**Subject**</span></span>
  - <span data-ttu-id="7dcbd-176">**Namn på bifogad fil**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-176">**Attachment filename**</span></span>
  - <span data-ttu-id="7dcbd-177">**Familjen skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-177">**Malware family**</span></span>
  - <span data-ttu-id="7dcbd-178">**Leverans åtgärd**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-178">**Delivery action**</span></span>
  - <span data-ttu-id="7dcbd-179">**Detekterings teknologi**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-179">**Detection technology**</span></span>
  - <span data-ttu-id="7dcbd-180">**Taggen**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-180">**Tags**</span></span>
  - <span data-ttu-id="7dcbd-181">**Systemåsidosättningar**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-181">**System overrides**</span></span>

- <span data-ttu-id="7dcbd-182">Tidigareläggas</span><span class="sxs-lookup"><span data-stu-id="7dcbd-182">Advanced</span></span>

  - <span data-ttu-id="7dcbd-183">**Internet meddelande-ID**: tillgängligt i fältet **meddelande-ID** i meddelande huvudet.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-183">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="7dcbd-184">Ett exempel värde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Observera vinkelparenteser).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-184">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="7dcbd-185">**ID för nätverks meddelande**: ett GUID-värde som är tillgängligt i huvudet **X-MS-Exchange-Organization-Network-meddelande-ID** i meddelande huvudet.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-185">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="7dcbd-186">**Avsändarens IP**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-186">**Sender IP**</span></span>
  
  - <span data-ttu-id="7dcbd-187">**Bilaga SHA256**: om du vill hitta SHA256-hash-värdet för en fil i Windows kör du följande kommando i kommando tolken: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .</span><span class="sxs-lookup"><span data-stu-id="7dcbd-187">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="7dcbd-188">**Kluster-ID**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-188">**Cluster ID**</span></span>
  
  - <span data-ttu-id="7dcbd-189">**ID för aviserings policy**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-189">**Alert Policy ID**</span></span>

- <span data-ttu-id="7dcbd-190">Garanteras</span><span class="sxs-lookup"><span data-stu-id="7dcbd-190">URLs</span></span>

  - <span data-ttu-id="7dcbd-191">**URL-domän**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-191">**URL domain**</span></span>
  - <span data-ttu-id="7dcbd-192">**URL-domän och sökväg**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-192">**URL domain and path**</span></span>
  - <span data-ttu-id="7dcbd-193">**:**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-193">**URL**</span></span>
  - <span data-ttu-id="7dcbd-194">**URL-sökväg**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-194">**URL path**</span></span>
  - <span data-ttu-id="7dcbd-195">**Klicka på Verdict**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-195">**Click verdict**</span></span>

<span data-ttu-id="7dcbd-196">För mer avancerad filtrering, inklusive filtrering efter flera egenskaper, kan du klicka på knappen **Avancerat filter** för att skapa en fråga.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-196">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="7dcbd-197">Samma kampanj egenskaper är tillgängliga, men med följande förbättringar:</span><span class="sxs-lookup"><span data-stu-id="7dcbd-197">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="7dcbd-198">Du kan klicka på **Lägg till ett villkor** för att välja flera villkor.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-198">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="7dcbd-199">Du kan välja operatorerna **och** eller **eller** mellan villkoren.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-199">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="7dcbd-200">Du kan markera **villkors gruppen** längst ned i listan villkor för att bilda komplexa sammansatta förhållanden.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-200">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="7dcbd-201">När du är klar klickar du på knappen **fråga** .</span><span class="sxs-lookup"><span data-stu-id="7dcbd-201">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="7dcbd-202">När du har skapat ett grundläggande eller Avancerat filter kan du spara det genom att använda **Spara fråga** eller **Spara fråga som**.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-202">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="7dcbd-203">Senare när du återvänder till kampanjmallar kan du läsa in ett sparat filter genom att klicka på **Inställningar för sparade frågor**.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-203">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="7dcbd-204">Om du vill exportera diagrammet eller listan med kampanjer klickar du på **Exportera** och väljer **Exportera diagram data** eller **Exportera kampanj lista**.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-204">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="7dcbd-205">Om du har en Microsoft Defender ATP-prenumeration kan du klicka på **WDATP** för att koppla eller koppla bort kampanj informationen med Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-205">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="7dcbd-206">Mer information finns i [integrera Office 365 ATP med Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-206">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="7dcbd-207">Kampanj uppgifter</span><span class="sxs-lookup"><span data-stu-id="7dcbd-207">Campaign details</span></span>

<span data-ttu-id="7dcbd-208">När du klickar på namnet på en kampanj visas kampanj informationen i en utfällbar lista.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-208">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="7dcbd-209">Kampanj information</span><span class="sxs-lookup"><span data-stu-id="7dcbd-209">Campaign information</span></span>

<span data-ttu-id="7dcbd-210">Högst upp i vyn kampanj information är följande kampanj information tillgänglig:</span><span class="sxs-lookup"><span data-stu-id="7dcbd-210">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="7dcbd-211">**ID**: unika kampanj-ID.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-211">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="7dcbd-212">**Startat** och **avslutat**: start datum och slutdatum för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-212">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="7dcbd-213">Observera att dessa datum kanske sträcker sig längre än de filter datum som du valde på översikts sidan.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-213">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="7dcbd-214">**Effekt**: det här avsnittet innehåller följande data för det datum intervall som du valde (eller som du väljer i tids linjen):</span><span class="sxs-lookup"><span data-stu-id="7dcbd-214">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="7dcbd-215">Totalt antal mottagare.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-215">The total number of recipients.</span></span>
  - <span data-ttu-id="7dcbd-216">Antalet meddelanden som "Inkorg" (det vill säga levereras till Inkorgen, inte till mappen skräp post).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-216">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="7dcbd-217">Hur många användare klickar på URL-nyttolasten i nät fiske meddelandet.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-217">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="7dcbd-218">Howe många användare besöker URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-218">Howe many users visited the URL.</span></span>

- <span data-ttu-id="7dcbd-219">**Riktad**: den procents ATS som beräknas av: (antalet mottagare av kampanjen i organisationen)/(det totala antalet mottagare i kampanjen i alla organisationer i tjänsten).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-219">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="7dcbd-220">Observera att det här värdet beräknas under hela kampanjens livstid och ändrar inte filter datumen.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-220">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change the filter dates.</span></span>

- <span data-ttu-id="7dcbd-221">En interaktiv tids linje med kampanj aktivitet: tids linjen visar aktivitet under hela kampanjens livstid.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-221">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="7dcbd-222">Som standard innehåller det skuggade området det datum intervall som du valde i översikten.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-222">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="7dcbd-223">Du kan klicka och dra för att välja en specifik start punkt och slut punkt, <u>som ändrar informationen som visas i området **påverkan** och på resten av sidan enligt beskrivningen i nästa avsnitt</u>.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-223">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="7dcbd-224">I namn listen kan du klicka på knappen **Hämta kampanjens uppskrivnings** ![ ikon för att hämta kampanj ](../../media/download-campaign-write-up-button.png) informationen till ett Word-dokument (som standard heter CampaignReport.docx).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-224">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="7dcbd-225">Observera att det här dokumentet innehåller information över hela kampanjens livstid (inte bara valda filter datum).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-225">Note that this document contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![Kampanj information](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="7dcbd-227">Kampanj flöde</span><span class="sxs-lookup"><span data-stu-id="7dcbd-227">Campaign flow</span></span>

<span data-ttu-id="7dcbd-228">I vyn kampanj information visas viktig information om kampanjen i **flödet** i ett vågrätt flödes diagram (kallas ett _Sankey_ -diagram).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-228">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="7dcbd-229">Dessa uppgifter hjälper dig att förstå vad som händer med kampanjen och hur de kan påverka din organisation.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-229">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="7dcbd-230">Informationen som visas i **flödes** diagrammet styrs av det skuggade datum intervallet på tids linjen enligt beskrivningen i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-230">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![Kampanj uppgifter som inte innehåller användar-URL-musklick](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="7dcbd-232">Om du hovrar över ett vågrätt band i diagrammet visas antalet relaterade meddelanden (till exempel meddelanden från en viss käll-IP, meddelanden från käll-IP med den angivna avsändarens domän osv.).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-232">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="7dcbd-233">Diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="7dcbd-233">The diagram contains the following information:</span></span>

- <span data-ttu-id="7dcbd-234">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-234">**Sender IPs**</span></span>

- <span data-ttu-id="7dcbd-235">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-235">**Sender domains**</span></span>

- <span data-ttu-id="7dcbd-236">**Filtrera verdicts**: de här värdena är relaterade till de tillgängliga phishing-och skräp post filtrerings verdicts enligt beskrivningen i [meddelandehuvuden](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-236">**Filter verdicts**: These values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="7dcbd-237">De tillgängliga värdena beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="7dcbd-237">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="7dcbd-238">Value</span><span class="sxs-lookup"><span data-stu-id="7dcbd-238">Value</span></span>|<span data-ttu-id="7dcbd-239">Skräp post filter Verdict</span><span class="sxs-lookup"><span data-stu-id="7dcbd-239">Spam filter verdict</span></span>|<span data-ttu-id="7dcbd-240">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7dcbd-240">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="7dcbd-241">**Möjlighet**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-241">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="7dcbd-242">Meddelandet har marker ATS som inte skräp post och/eller ignorerade filtrering innan den utvärderas av skräp post filtreringen (till exempel i en regel för e-postflöde).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-242">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="7dcbd-243">Meddelandet ignorerade spam av andra orsaker (till exempel att avsändaren och mottagaren ser ut att vara i samma organisation).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-243">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="7dcbd-244">**Blockering**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-244">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="7dcbd-245">Meddelandet har marker ATS som skräp post innan det utvärderas av skräp post filtreringen (till exempel i en regel för e-postflöde).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-245">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="7dcbd-246">**Upptäckte**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-246">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="7dcbd-247">Meddelandet markerades som skräppost av skräppostfiltret.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-247">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="7dcbd-248">**Identifieras inte**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-248">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="7dcbd-249">Meddelandet har marker ATS som inte skräp post av filtrering av skräp post.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-249">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="7dcbd-250">**Levereras**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-250">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="7dcbd-251">Meddelandet hoppade över skräp post filtrering eftersom det släpptes från karantän.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-251">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="7dcbd-252">**Tillåt klient organisation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7dcbd-252">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="7dcbd-253">Meddelandet hoppade över skräp post filtrering på grund av princip inställningar för skräp post (till exempel att avsändaren var i listan över tillåtna avsändare eller listan över tillåtna domäner).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-253">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="7dcbd-254">**Klient blockering**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="7dcbd-254">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="7dcbd-255">Meddelandet blockerades av skräp post filtrering på grund av princip inställningar för skräp post (till exempel att avsändaren fanns i listan över tillåtna avsändare eller listan över tillåtna domäner).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-255">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="7dcbd-256">**Tillåt användare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7dcbd-256">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="7dcbd-257">Meddelandet hoppade över skräp post filtrering eftersom avsändaren fanns i en användares lista med betrodda avsändare i Outlook.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-257">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="7dcbd-258">**User block**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="7dcbd-258">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="7dcbd-259">Meddelandet blockerades av filtrering av skräp post eftersom avsändaren fanns i en användares lista över spärrade avsändare i Outlook.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-259">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="7dcbd-260">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-260">**ZAP**</span></span>|<span data-ttu-id="7dcbd-261">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="7dcbd-261">n/a</span></span>|<span data-ttu-id="7dcbd-262">[Automatisk rensning för en hel timme (Zap)](zero-hour-auto-purge.md) vidtog en åtgärd på det levererade meddelandet enligt inställningarna för skydd mot skräp post (flyttad till mappen Skräppost eller karantän).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|
  |

  <span data-ttu-id="7dcbd-263"><sup>\*</sup>Granska dina skydd mot skräp post eftersom det tillåtna meddelandet förmodligen har blockerats av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-263"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="7dcbd-264"><sup>\*\*</sup>Granska dina principer för skräp post, eftersom dessa meddelanden bör vara i karantän, inte levereras.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-264"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="7dcbd-265">**Leverans ställen**: du kommer troligen att behöva undersöka meddelanden som faktiskt har levererats till mottagarna (antingen till Inkorgen eller mappen skräp post), även om användarna inte klickat på URL: en för nytto lasten i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-265">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="7dcbd-266">Du kan också ta bort meddelanden i karantänen från karantänen.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-266">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="7dcbd-267">Mer information finns i [e-postmeddelanden i karantän i EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-267">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="7dcbd-268">**Borttagen mapp**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-268">**Deleted folder**</span></span>
  - <span data-ttu-id="7dcbd-269">**Avbröts**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-269">**Dropped**</span></span>
  - <span data-ttu-id="7dcbd-270">**Externt**: mottagaren finns i din lokala e-postorganisation i hybrid miljöer.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-270">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="7dcbd-271">**Misslyckades**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-271">**Failed**</span></span>
  - <span data-ttu-id="7dcbd-272">**Vidarekopplas**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-272">**Forwarded**</span></span>
  - <span data-ttu-id="7dcbd-273">**Brevlåda**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-273">**Inbox**</span></span>
  - <span data-ttu-id="7dcbd-274">**Skräppostmappen**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-274">**Junk folder**</span></span>
  - <span data-ttu-id="7dcbd-275">**Karantän**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-275">**Quarantine**</span></span>
  - <span data-ttu-id="7dcbd-276">**Okänd**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-276">**Unknown**</span></span>

- <span data-ttu-id="7dcbd-277">**URL-musklick**: de här beskrivs i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-277">**URL clicks**: These are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="7dcbd-278">I alla lager som innehåller fler än 10 objekt visas de 10 översta objekten, medan resten samlas samman i **andra**.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-278">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="7dcbd-279">URL-klickningar</span><span class="sxs-lookup"><span data-stu-id="7dcbd-279">URL clicks</span></span>

<span data-ttu-id="7dcbd-280">När ett nät fiske meddelande levereras till en mottagare (till Inkorgen eller mappen skräp post) finns det en chans att användaren klickar på nytto lastens URL-adress.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-280">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="7dcbd-281">Det går inte att klicka på URL-adressen i ett levererat meddelande, men du måste fastställa varför nät fiske meddelandet levererades till post lådan.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-281">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="7dcbd-282">Om en användare klickar på nytto lastens URL i nät fiske meddelandet visas åtgärderna i området URL- **klickning** i diagrammet i vyn kampanj information.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-282">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="7dcbd-283">**Möjlighet**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-283">**Allowed**</span></span>

- <span data-ttu-id="7dcbd-284">**BlockPage**: mottagaren klickade på nytto lastens URL, men deras åtkomst till den illasinnade webbplatsen blockerades av principerna för [Safe Links för ATP](atp-safe-links.md) i din organisation.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-284">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="7dcbd-285">**BlockPageOverride**: mottagaren klickade på nytto lastens URL-adress i meddelandet, men de har kunnat åsidosätta det.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-285">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="7dcbd-286">Du måste undersöka dina [principer för säkra länkar](set-up-atp-safe-links-policies.md) för att se varför användare har tillåtelse att åsidosätta Safe Links-Verdict och fortsätta till den illasinnade webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-286">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="7dcbd-287">**PendingDetonationPage**: säkra bifogade filer med ATP är att öppna nytto lastens URL i en virtuell dator miljö och se vad som händer.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-287">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="7dcbd-288">**PendingDetonationPageOverride**: mottagaren har fått tillåtelse att åsidosätta nytto toner processen och öppna URL: en utan att vänta på resultaten.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-288">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="7dcbd-289">TABB</span><span class="sxs-lookup"><span data-stu-id="7dcbd-289">Tabs</span></span>

<span data-ttu-id="7dcbd-290">Flikarna i vyn kampanj information gör att du kan undersöka kampanjen ytterligare.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-290">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="7dcbd-291">Informationen som visas på flikarna styrs av det skuggade datum intervallet i tids linjen enligt beskrivningen i avsnittet [kampanj information](#campaign-information) .</span><span class="sxs-lookup"><span data-stu-id="7dcbd-291">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="7dcbd-292">**URL klickar**på: om användare inte klickar på nytto lastens URL i nät fiske meddelandet är det här avsnittet tomt.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-292">**URL clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="7dcbd-293">Om en användare kunde klicka på URL-adressen fylls följande värden i:</span><span class="sxs-lookup"><span data-stu-id="7dcbd-293">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="7dcbd-294">**Användarläge**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7dcbd-294">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="7dcbd-295">**:**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7dcbd-295">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="7dcbd-296">**Klicka på tid**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-296">**Click time**</span></span>
  - <span data-ttu-id="7dcbd-297">**Klicka på Verdict**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-297">**Click verdict**</span></span>

- <span data-ttu-id="7dcbd-298">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-298">**Sender IPs**</span></span>

  - <span data-ttu-id="7dcbd-299">**Avsändarens IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7dcbd-299">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="7dcbd-300">**Totalt antal**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-300">**Total count**</span></span>
  - <span data-ttu-id="7dcbd-301">**Inkorgen**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-301">**Inboxed**</span></span>
  - <span data-ttu-id="7dcbd-302">**Inte i Inkorgen**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-302">**Not Inboxed**</span></span>
  - <span data-ttu-id="7dcbd-303">**SPF skickades**: avsändaren autentiserades av [SPF (avsändare Policy Framework)](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-303">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="7dcbd-304">En avsändare som inte skickar SPF-verifiering indikerar att avsändaren inte är autentiserad eller att meddelandet har falskats för en legitim avsändare.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-304">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="7dcbd-305">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-305">**Senders**</span></span>

  - <span data-ttu-id="7dcbd-306">**Avsändare**: det här är den faktiska avsändar adressen i SMTP e-postmeddelandet, som inte nödvändigt vis är den e-postadress som användarna ser i sina e-postklienter.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-306">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="7dcbd-307">**Totalt antal**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-307">**Total count**</span></span>
  - <span data-ttu-id="7dcbd-308">**Inkorgen**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-308">**Inboxed**</span></span>
  - <span data-ttu-id="7dcbd-309">**Inte i Inkorgen**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-309">**Not Inboxed**</span></span>
  - <span data-ttu-id="7dcbd-310">**DKIM lyckades**: avsändaren autentiserades av [domän nycklar som identifieras via e-post (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-310">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="7dcbd-311">En avsändare som inte klarar DKIM-verifiering anger att avsändaren inte är autentiserad eller att meddelandet har falskats för en legitim avsändare.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-311">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="7dcbd-312">**DMARC skickades**: avsändaren autentiserades av [domänbaserad autentisering, rapportering och omslutande (DMARC)](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-312">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="7dcbd-313">En avsändare som inte klarar DMARC-verifiering anger att avsändaren inte är autentiserad eller att meddelandet har falskats för en legitim avsändare.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-313">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="7dcbd-314">**Bifogade filer**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-314">**Attachments**</span></span>

  - <span data-ttu-id="7dcbd-315">**Datafil**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-315">**Filename**</span></span>
  - <span data-ttu-id="7dcbd-316">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-316">**SHA256**</span></span>
  - <span data-ttu-id="7dcbd-317">**Familjen skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-317">**Malware family**</span></span>
  - <span data-ttu-id="7dcbd-318">**Totalt antal**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-318">**Total count**</span></span>

- <span data-ttu-id="7dcbd-319">**:**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-319">**URL**</span></span>

  - <span data-ttu-id="7dcbd-320">**:**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7dcbd-320">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="7dcbd-321">**Totalt antal**</span><span class="sxs-lookup"><span data-stu-id="7dcbd-321">**Total Count**</span></span>

<span data-ttu-id="7dcbd-322"><sup>\*</sup>Om du klickar på det här värdet öppnas en ny utfällare som innehåller mer information om det angivna objektet (användare, URL: er osv.).</span><span class="sxs-lookup"><span data-stu-id="7dcbd-322"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="7dcbd-323">Om du vill gå tillbaka till vyn kampanj Detaljer klickar du på **klar** i den nya utfällbara menyn.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-323">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="7dcbd-324">Pilknapp</span><span class="sxs-lookup"><span data-stu-id="7dcbd-324">Buttons</span></span>

<span data-ttu-id="7dcbd-325">Med knapparna i vyn kampanj information kan du använda privilegiet mot hot Explorer för att undersöka kampanjen.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-325">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="7dcbd-326">**Utforska kampanjen**: öppna en ny Threat Explorer-fliken Sök med hjälp av värdet för **kampanj-ID** som Sök filter.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-326">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="7dcbd-327">**Utforska meddelanden i Inkorgen**: öppnar en ny webbplats Sök-flik med **kampanj-ID** och **leverans plats: Inkorgen** som Sök filter.</span><span class="sxs-lookup"><span data-stu-id="7dcbd-327">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
