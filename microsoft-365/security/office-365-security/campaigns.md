---
title: Kampanjmallar i Office 365 ATP-abonnemang
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Lär dig mer om kampanjmallar i Office 365 Avancerat skydd.
ms.openlocfilehash: df3b3c7a0e8d8f614e5f743b445af07916f1dfd5
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326597"
---
# <a name="campaign-views-in-office-365-atp"></a><span data-ttu-id="aaadb-103">Analysvyer i Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="aaadb-103">Campaign Views in Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="aaadb-104">Kampanjmallar är en funktion i abonnemanget Avancerat skydd (ATP) (till exempel Microsoft 365 E5 eller organisationer med ett ATP-abonnemang 2-tillägg).</span><span class="sxs-lookup"><span data-stu-id="aaadb-104">Campaign Views is a feature in Advanced Threat Protection (ATP) Plan 2 (for example Microsoft 365 E5 or organizations with an ATP Plan 2 add-on).</span></span> <span data-ttu-id="aaadb-105">I vyn kampanjer i säkerhets & identifieras och kategoriseras nätfiske-attacker i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="aaadb-105">Campaign Views in the Security & Compliance Center identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="aaadb-106">Med hjälp av kampanjmallar kan du:</span><span class="sxs-lookup"><span data-stu-id="aaadb-106">Campaign Views can help you to:</span></span>

- <span data-ttu-id="aaadb-107">Undersök och svara på nät fiske attacker effektivt.</span><span class="sxs-lookup"><span data-stu-id="aaadb-107">Efficiently investigate and respond to phishing attacks.</span></span>
- <span data-ttu-id="aaadb-108">Bättre förståelse för attackens omfattning.</span><span class="sxs-lookup"><span data-stu-id="aaadb-108">Better understand the scope of the attack.</span></span>
- <span data-ttu-id="aaadb-109">Visa värde för besluts fattare.</span><span class="sxs-lookup"><span data-stu-id="aaadb-109">Show value to decision makers.</span></span>

<span data-ttu-id="aaadb-110">Med kampanjmallar kan du se en stor bild av en attack snabbare och mer komplett än de som är på människa.</span><span class="sxs-lookup"><span data-stu-id="aaadb-110">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="aaadb-111">Vad är en kampanj?</span><span class="sxs-lookup"><span data-stu-id="aaadb-111">What is a campaign?</span></span>

<span data-ttu-id="aaadb-112">En kampanj är en koordinerad e-postattack mot en eller flera organisationer.</span><span class="sxs-lookup"><span data-stu-id="aaadb-112">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="aaadb-113">E-postattacker som stjälar uppgifter och företags data är en stor och Lucrative bransch.</span><span class="sxs-lookup"><span data-stu-id="aaadb-113">Email attacks that steal credentials and company data are a large and lucrative industry.</span></span> <span data-ttu-id="aaadb-114">Eftersom teknikerna ökar för att förhindra attacker, ändrar angripare sina metoder för att säkerställa fortsatt framgång.</span><span class="sxs-lookup"><span data-stu-id="aaadb-114">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="aaadb-115">Microsoft utnyttjar de stora mängderna nätfiske, anti-spam och data mot skadlig program vara via hela tjänsten för att identifiera kampanjer.</span><span class="sxs-lookup"><span data-stu-id="aaadb-115">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="aaadb-116">Vi analyserar och klassificerar angrepps informationen enligt flera faktorer.</span><span class="sxs-lookup"><span data-stu-id="aaadb-116">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="aaadb-117">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="aaadb-117">For example:</span></span>

- <span data-ttu-id="aaadb-118">**Attack källa**: käll-IP-adresser och e-postdomäner.</span><span class="sxs-lookup"><span data-stu-id="aaadb-118">**Attack source**: The source IP addresses and sender email domains.</span></span>
- <span data-ttu-id="aaadb-119">**Meddelande egenskaper**: innehåll, format och ton för meddelanden.</span><span class="sxs-lookup"><span data-stu-id="aaadb-119">**Message properties**: The content, style, and tone of the messages.</span></span>
- <span data-ttu-id="aaadb-120">**Mottagare**: hur mottagarna är relaterade.</span><span class="sxs-lookup"><span data-stu-id="aaadb-120">**Message recipients**: How recipients are related.</span></span> <span data-ttu-id="aaadb-121">Till exempel mottagare och mottagare, arbets uppgifter (administratörer, chefer etc.), företags typer (stor, liten, offentlig, privat etc.) och branscher.</span><span class="sxs-lookup"><span data-stu-id="aaadb-121">For example, recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>
- <span data-ttu-id="aaadb-122">**Attack-nyttolast**: illasinnade länkar, bifogade filer eller andra nytto laster i meddelanden.</span><span class="sxs-lookup"><span data-stu-id="aaadb-122">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="aaadb-123">En kampanj kan vara kort livs längd eller kunna omfatta flera dagar, veckor eller månader med aktiva och inaktiva perioder.</span><span class="sxs-lookup"><span data-stu-id="aaadb-123">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="aaadb-124">En kampanj kan startas mot din specifika organisation, eller så kan din organisation vara en del av en större kampanj i flera företag.</span><span class="sxs-lookup"><span data-stu-id="aaadb-124">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-in-the-security--compliance-center"></a><span data-ttu-id="aaadb-125">Kampanjmallar i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="aaadb-125">Campaign Views in the Security & Compliance Center</span></span>

<span data-ttu-id="aaadb-126">Kampanjmallar är tillgängligt i [säkerhets & Compliance Center](https://protection.office.com) med kampanjer för **Threat Management** \> **Campaigns**eller direkt vid <https://protection.office.com/campaigns> .</span><span class="sxs-lookup"><span data-stu-id="aaadb-126">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![Översikt över kampanjer i säkerhets & Compliance Center](../../media/campaigns-overview.png)

<span data-ttu-id="aaadb-128">Du kan också komma åt kampanjmallar från:</span><span class="sxs-lookup"><span data-stu-id="aaadb-128">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="aaadb-129">**Threat Management** \> **Utforskaren** \> **Visa** \> **Kampanjer**</span><span class="sxs-lookup"><span data-stu-id="aaadb-129">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="aaadb-130">**Threat Management** \> **Utforskaren** \> **Visa** \> **All e-post** \> Fliken **kampanj**</span><span class="sxs-lookup"><span data-stu-id="aaadb-130">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="aaadb-131">**Threat Management** \> **Utforskaren** \> **Visa** \> **Phish** \> Fliken **kampanj**</span><span class="sxs-lookup"><span data-stu-id="aaadb-131">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="aaadb-132">**Threat Management** \> **Utforskaren** \> **Visa** \> **Malware** \> Fliken **kampanj**</span><span class="sxs-lookup"><span data-stu-id="aaadb-132">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="aaadb-133">För att få åtkomst till kampanjmallar måste du vara medlem i roll grupperna **organisations hantering**, **säkerhets administratör**eller **säkerhets läsare** i säkerhets & efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="aaadb-133">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="aaadb-134">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="aaadb-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="aaadb-135">Översikt över kampanjer</span><span class="sxs-lookup"><span data-stu-id="aaadb-135">Campaigns overview</span></span>

<span data-ttu-id="aaadb-136">Sidan översikt visar information om alla kampanjer.</span><span class="sxs-lookup"><span data-stu-id="aaadb-136">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="aaadb-137">På fliken standard **kampanj** visas ett stapeldiagram som visar antalet mottagare per dag i området **kampanj typ** .</span><span class="sxs-lookup"><span data-stu-id="aaadb-137">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="aaadb-138">Som standard visar diagrammet både **Phish** och **malware** data.</span><span class="sxs-lookup"><span data-stu-id="aaadb-138">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="aaadb-139">Om du inte ser några kampanj data kan du försöka ändra datum intervallet eller [filtren](#filters-and-settings).</span><span class="sxs-lookup"><span data-stu-id="aaadb-139">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="aaadb-140">På resten av översikts sidan visas följande information på fliken **kampanj** :</span><span class="sxs-lookup"><span data-stu-id="aaadb-140">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="aaadb-141">**Namn**</span><span class="sxs-lookup"><span data-stu-id="aaadb-141">**Name**</span></span>

- <span data-ttu-id="aaadb-142">**Exempel ämne**: ämnes raden för ett av meddelandena i kampanjen.</span><span class="sxs-lookup"><span data-stu-id="aaadb-142">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="aaadb-143">Observera att alla meddelanden i kampanjen inte nödvändigt vis har samma ämne.</span><span class="sxs-lookup"><span data-stu-id="aaadb-143">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="aaadb-144">**Riktad**: den procents ATS som beräknas av: (antalet mottagare av kampanjen i organisationen)/(det totala antalet mottagare i kampanjen i alla organisationer i tjänsten).</span><span class="sxs-lookup"><span data-stu-id="aaadb-144">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="aaadb-145">Det här värdet anger i vilken utsträckning kampanjen bara riktas in på din organisation (ett högre värde) kontra riktas till andra organisationer i tjänsten (ett lägre värde).</span><span class="sxs-lookup"><span data-stu-id="aaadb-145">This value indicates the degree to which the campaign is directed only at your organization (a higher value) vs. also directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="aaadb-146">**Typ**: det här värdet är antingen **Phish** eller **skadlig program vara**.</span><span class="sxs-lookup"><span data-stu-id="aaadb-146">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="aaadb-147">**Undertyp**: det här värdet innehåller mer information om kampanjen.</span><span class="sxs-lookup"><span data-stu-id="aaadb-147">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="aaadb-148">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="aaadb-148">For example:</span></span>

  - <span data-ttu-id="aaadb-149">**Phish**: där det är tillgängligt, det märke som phished av kampanjen.</span><span class="sxs-lookup"><span data-stu-id="aaadb-149">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="aaadb-150">Till exempel, `Microsoft` ,,, `365` `Unknown` `Outlook` eller `DocuSign` .</span><span class="sxs-lookup"><span data-stu-id="aaadb-150">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="aaadb-151">**Skadlig kod**: till exempel `HTML/PHISH` eller `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="aaadb-151">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="aaadb-152">Där det är tillgängligt, det märke som phished av kampanjen.</span><span class="sxs-lookup"><span data-stu-id="aaadb-152">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="aaadb-153">När identifieringen drivs av ATP-teknologin används prefixet **ATP-** och värdet för undertyp.</span><span class="sxs-lookup"><span data-stu-id="aaadb-153">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="aaadb-154">**Mottagare**: antalet användare som är riktade till den här kampanjen.</span><span class="sxs-lookup"><span data-stu-id="aaadb-154">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="aaadb-155">**Inkorgen**: antalet användare som fick meddelanden från den här kampanjen i sin inkorg (levereras inte till mappen skräp post).</span><span class="sxs-lookup"><span data-stu-id="aaadb-155">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="aaadb-156">**Klickar**du på: antalet användare som klickade på URL-adressen eller öppnade den bifogade filen i nät fiske meddelandet.</span><span class="sxs-lookup"><span data-stu-id="aaadb-156">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="aaadb-157">**Klicka på ränta**: procent satsen beräknat av "**klickade**på  /  **Inkorgen**".</span><span class="sxs-lookup"><span data-stu-id="aaadb-157">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="aaadb-158">Detta värde är en indikator för kampanjens effektivitet.</span><span class="sxs-lookup"><span data-stu-id="aaadb-158">This value is an indicator of the effectiveness of the campaign.</span></span> <span data-ttu-id="aaadb-159">Med andra ord, om mottagarna kunde identifiera meddelandet som nätfiske, och om de inte klickade på nytto lastens URL.</span><span class="sxs-lookup"><span data-stu-id="aaadb-159">In other words, if the recipients were able to identify the message as phishing, and if they didn't click on the payload URL.</span></span>

  <span data-ttu-id="aaadb-160">Observera att **Klicka på ränta** inte används i kampanjer med skadlig program vara.</span><span class="sxs-lookup"><span data-stu-id="aaadb-160">Note that **Click rate** isn't used in malware campaigns.</span></span>

- <span data-ttu-id="aaadb-161">**Besökt**: hur många användare faktiskt gjorde det till nytto Last webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="aaadb-161">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="aaadb-162">Om du **klickade på** värden, men säkra länkar blockerade åtkomst till webbplatsen, är det här värdet noll.</span><span class="sxs-lookup"><span data-stu-id="aaadb-162">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="aaadb-163">På fliken **kampanj källa** visas meddelande källorna på en karta över hela världen.</span><span class="sxs-lookup"><span data-stu-id="aaadb-163">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="aaadb-164">Filter och inställningar</span><span class="sxs-lookup"><span data-stu-id="aaadb-164">Filters and settings</span></span>

<span data-ttu-id="aaadb-165">Högst upp på sidan kampanjmallar finns det flera filter-och frågeinställningar som hjälper dig att hitta och isolera specifika kampanjer.</span><span class="sxs-lookup"><span data-stu-id="aaadb-165">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![Kampanj filter](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="aaadb-167">Den mest grundläggande filtreringen du kan göra är start datum och slut tid.</span><span class="sxs-lookup"><span data-stu-id="aaadb-167">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="aaadb-168">Om du vill filtrera vyn ytterligare kan du utföra en enskild egenskap med filtrering av flera värden genom att klicka på knappen **kampanj typ** , välja och sedan klicka på **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="aaadb-168">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="aaadb-169">De tillgängliga kampanj egenskaperna beskrivs i följande lista:</span><span class="sxs-lookup"><span data-stu-id="aaadb-169">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="aaadb-170">Basic</span><span class="sxs-lookup"><span data-stu-id="aaadb-170">Basic</span></span>

  - <span data-ttu-id="aaadb-171">**Kampanj typ**: Välj **skadlig** eller **Phish**.</span><span class="sxs-lookup"><span data-stu-id="aaadb-171">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="aaadb-172">Om du avmarkerar valen är det samma resultat som att markera båda.</span><span class="sxs-lookup"><span data-stu-id="aaadb-172">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="aaadb-173">**Kampanj namn**</span><span class="sxs-lookup"><span data-stu-id="aaadb-173">**Campaign name**</span></span>
  - <span data-ttu-id="aaadb-174">**Kampanj under typ**</span><span class="sxs-lookup"><span data-stu-id="aaadb-174">**Campaign subtype**</span></span>
  - <span data-ttu-id="aaadb-175">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="aaadb-175">**Sender**</span></span>
  - <span data-ttu-id="aaadb-176">**Mottagarna**</span><span class="sxs-lookup"><span data-stu-id="aaadb-176">**Recipients**</span></span>
  - <span data-ttu-id="aaadb-177">**Avsändningsdomän**</span><span class="sxs-lookup"><span data-stu-id="aaadb-177">**Sender domain**</span></span>
  - <span data-ttu-id="aaadb-178">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="aaadb-178">**Subject**</span></span>
  - <span data-ttu-id="aaadb-179">**Namn på bifogad fil**</span><span class="sxs-lookup"><span data-stu-id="aaadb-179">**Attachment filename**</span></span>
  - <span data-ttu-id="aaadb-180">**Familjen skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="aaadb-180">**Malware family**</span></span>
  - <span data-ttu-id="aaadb-181">**Leverans åtgärd**</span><span class="sxs-lookup"><span data-stu-id="aaadb-181">**Delivery action**</span></span>
  - <span data-ttu-id="aaadb-182">**Detekterings teknologi**</span><span class="sxs-lookup"><span data-stu-id="aaadb-182">**Detection technology**</span></span>
  - <span data-ttu-id="aaadb-183">**Taggen**</span><span class="sxs-lookup"><span data-stu-id="aaadb-183">**Tags**</span></span>
  - <span data-ttu-id="aaadb-184">**Systemåsidosättningar**</span><span class="sxs-lookup"><span data-stu-id="aaadb-184">**System overrides**</span></span>

- <span data-ttu-id="aaadb-185">Avancerat</span><span class="sxs-lookup"><span data-stu-id="aaadb-185">Advanced</span></span>

  - <span data-ttu-id="aaadb-186">**Internet meddelande-ID**: tillgängligt i fältet **meddelande-ID** i meddelande huvudet.</span><span class="sxs-lookup"><span data-stu-id="aaadb-186">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="aaadb-187">Ett exempel värde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Observera vinkelparenteser).</span><span class="sxs-lookup"><span data-stu-id="aaadb-187">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="aaadb-188">**ID för nätverks meddelande**: ett GUID-värde som är tillgängligt i huvudet **X-MS-Exchange-Organization-Network-meddelande-ID** i meddelande huvudet.</span><span class="sxs-lookup"><span data-stu-id="aaadb-188">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="aaadb-189">**Avsändarens IP**</span><span class="sxs-lookup"><span data-stu-id="aaadb-189">**Sender IP**</span></span>
  
  - <span data-ttu-id="aaadb-190">**Bilaga SHA256**: om du vill hitta SHA256-hash-värdet för en fil i Windows kör du följande kommando i kommando tolken: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .</span><span class="sxs-lookup"><span data-stu-id="aaadb-190">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="aaadb-191">**Kluster-ID**</span><span class="sxs-lookup"><span data-stu-id="aaadb-191">**Cluster ID**</span></span>
  
  - <span data-ttu-id="aaadb-192">**ID för aviserings policy**</span><span class="sxs-lookup"><span data-stu-id="aaadb-192">**Alert Policy ID**</span></span>

- <span data-ttu-id="aaadb-193">Garanteras</span><span class="sxs-lookup"><span data-stu-id="aaadb-193">URLs</span></span>

  - <span data-ttu-id="aaadb-194">**URL-domän**</span><span class="sxs-lookup"><span data-stu-id="aaadb-194">**URL domain**</span></span>
  - <span data-ttu-id="aaadb-195">**URL-domän och sökväg**</span><span class="sxs-lookup"><span data-stu-id="aaadb-195">**URL domain and path**</span></span>
  - <span data-ttu-id="aaadb-196">**:**</span><span class="sxs-lookup"><span data-stu-id="aaadb-196">**URL**</span></span>
  - <span data-ttu-id="aaadb-197">**URL-sökväg**</span><span class="sxs-lookup"><span data-stu-id="aaadb-197">**URL path**</span></span>
  - <span data-ttu-id="aaadb-198">**Klicka på Verdict**</span><span class="sxs-lookup"><span data-stu-id="aaadb-198">**Click verdict**</span></span>

<span data-ttu-id="aaadb-199">För mer avancerad filtrering, inklusive filtrering efter flera egenskaper, kan du klicka på knappen **Avancerat filter** för att skapa en fråga.</span><span class="sxs-lookup"><span data-stu-id="aaadb-199">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="aaadb-200">Samma kampanj egenskaper är tillgängliga, men med följande förbättringar:</span><span class="sxs-lookup"><span data-stu-id="aaadb-200">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="aaadb-201">Du kan klicka på **Lägg till ett villkor** för att välja flera villkor.</span><span class="sxs-lookup"><span data-stu-id="aaadb-201">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="aaadb-202">Du kan välja operatorerna **och** eller **eller** mellan villkoren.</span><span class="sxs-lookup"><span data-stu-id="aaadb-202">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="aaadb-203">Du kan markera **villkors gruppen** längst ned i listan villkor för att bilda komplexa sammansatta förhållanden.</span><span class="sxs-lookup"><span data-stu-id="aaadb-203">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="aaadb-204">När du är klar klickar du på knappen **fråga** .</span><span class="sxs-lookup"><span data-stu-id="aaadb-204">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="aaadb-205">När du har skapat ett grundläggande eller Avancerat filter kan du spara det genom att använda **Spara fråga** eller **Spara fråga som**.</span><span class="sxs-lookup"><span data-stu-id="aaadb-205">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="aaadb-206">Senare när du återvänder till kampanjmallar kan du läsa in ett sparat filter genom att klicka på **Inställningar för sparade frågor**.</span><span class="sxs-lookup"><span data-stu-id="aaadb-206">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="aaadb-207">Om du vill exportera diagrammet eller listan med kampanjer klickar du på **Exportera** och väljer **Exportera diagram data** eller **Exportera kampanj lista**.</span><span class="sxs-lookup"><span data-stu-id="aaadb-207">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="aaadb-208">Om du har en Microsoft Defender ATP-prenumeration kan du klicka på **WDATP** för att koppla eller koppla bort kampanj informationen med Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="aaadb-208">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="aaadb-209">Mer information finns i [integrera Office 365 ATP med Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span><span class="sxs-lookup"><span data-stu-id="aaadb-209">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="aaadb-210">Kampanj uppgifter</span><span class="sxs-lookup"><span data-stu-id="aaadb-210">Campaign details</span></span>

<span data-ttu-id="aaadb-211">När du klickar på namnet på en kampanj visas kampanj informationen i en utfällbar lista.</span><span class="sxs-lookup"><span data-stu-id="aaadb-211">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="aaadb-212">Kampanj information</span><span class="sxs-lookup"><span data-stu-id="aaadb-212">Campaign information</span></span>

<span data-ttu-id="aaadb-213">Högst upp i vyn kampanj information är följande kampanj information tillgänglig:</span><span class="sxs-lookup"><span data-stu-id="aaadb-213">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="aaadb-214">**ID**: unika kampanj-ID.</span><span class="sxs-lookup"><span data-stu-id="aaadb-214">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="aaadb-215">**Startat** och **avslutat**: start datum och slutdatum för kampanjen.</span><span class="sxs-lookup"><span data-stu-id="aaadb-215">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="aaadb-216">Observera att dessa datum kanske sträcker sig längre än de filter datum som du valde på översikts sidan.</span><span class="sxs-lookup"><span data-stu-id="aaadb-216">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="aaadb-217">**Effekt**: det här avsnittet innehåller följande data för det datum intervall som du valde (eller som du väljer i tids linjen):</span><span class="sxs-lookup"><span data-stu-id="aaadb-217">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="aaadb-218">Totalt antal mottagare.</span><span class="sxs-lookup"><span data-stu-id="aaadb-218">The total number of recipients.</span></span>
  - <span data-ttu-id="aaadb-219">Antalet meddelanden som "Inkorg" (det vill säga levereras till Inkorgen, inte till mappen skräp post).</span><span class="sxs-lookup"><span data-stu-id="aaadb-219">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="aaadb-220">Hur många användare klickar på URL-nyttolasten i nät fiske meddelandet.</span><span class="sxs-lookup"><span data-stu-id="aaadb-220">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="aaadb-221">Howe många användare besöker URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="aaadb-221">Howe many users visited the URL.</span></span>

- <span data-ttu-id="aaadb-222">**Riktad**: den procents ATS som beräknas av: (antalet mottagare av kampanjen i organisationen)/(det totala antalet mottagare i kampanjen i alla organisationer i tjänsten).</span><span class="sxs-lookup"><span data-stu-id="aaadb-222">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="aaadb-223">Observera att det här värdet beräknas under hela kampanjens livstid och inte ändras utifrån datum filter.</span><span class="sxs-lookup"><span data-stu-id="aaadb-223">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change based on date filters.</span></span>

- <span data-ttu-id="aaadb-224">En interaktiv tids linje med kampanj aktivitet: tids linjen visar aktivitet under hela kampanjens livstid.</span><span class="sxs-lookup"><span data-stu-id="aaadb-224">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="aaadb-225">Som standard innehåller det skuggade området det datum intervall som du valde i översikten.</span><span class="sxs-lookup"><span data-stu-id="aaadb-225">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="aaadb-226">Du kan klicka och dra för att välja en specifik start punkt och slut punkt, <u>som ändrar informationen som visas i området **påverkan** och på resten av sidan enligt beskrivningen i nästa avsnitt</u>.</span><span class="sxs-lookup"><span data-stu-id="aaadb-226">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="aaadb-227">I namn listen kan du klicka på knappen **Hämta kampanjens uppskrivnings** ![ ikon för att hämta kampanj ](../../media/download-campaign-write-up-button.png) informationen till ett Word-dokument (som standard heter CampaignReport.docx).</span><span class="sxs-lookup"><span data-stu-id="aaadb-227">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="aaadb-228">Observera att nedladdningen innehåller information under hela kampanjens livstid (inte bara valda filter datum).</span><span class="sxs-lookup"><span data-stu-id="aaadb-228">Note that the download contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![Kampanj information](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="aaadb-230">Kampanj flöde</span><span class="sxs-lookup"><span data-stu-id="aaadb-230">Campaign flow</span></span>

<span data-ttu-id="aaadb-231">I vyn kampanj information visas viktig information om kampanjen i **flödet** i ett vågrätt flödes diagram (kallas ett _Sankey_ -diagram).</span><span class="sxs-lookup"><span data-stu-id="aaadb-231">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="aaadb-232">Dessa uppgifter hjälper dig att förstå vad som händer med kampanjen och hur de kan påverka din organisation.</span><span class="sxs-lookup"><span data-stu-id="aaadb-232">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="aaadb-233">Informationen som visas i **flödes** diagrammet styrs av det skuggade datum intervallet på tids linjen enligt beskrivningen i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="aaadb-233">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![Kampanj uppgifter som inte innehåller användar-URL-musklick](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="aaadb-235">Om du hovrar över ett vågrätt band i diagrammet visas antalet relaterade meddelanden (till exempel meddelanden från en viss käll-IP, meddelanden från käll-IP med den angivna avsändarens domän osv.).</span><span class="sxs-lookup"><span data-stu-id="aaadb-235">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="aaadb-236">Diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="aaadb-236">The diagram contains the following information:</span></span>

- <span data-ttu-id="aaadb-237">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="aaadb-237">**Sender IPs**</span></span>

- <span data-ttu-id="aaadb-238">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="aaadb-238">**Sender domains**</span></span>

- <span data-ttu-id="aaadb-239">**Filter verdicts**: Verdict-värden är relaterade till de tillgängliga phishing-och skräp post filtrerings verdicts som beskrivs i [meddelandehuvuden](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="aaadb-239">**Filter verdicts**: Verdict values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="aaadb-240">De tillgängliga värdena beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="aaadb-240">The available values are described in the following table:</span></span>

  ****

  |<span data-ttu-id="aaadb-241">Value</span><span class="sxs-lookup"><span data-stu-id="aaadb-241">Value</span></span>|<span data-ttu-id="aaadb-242">Skräp post filter Verdict</span><span class="sxs-lookup"><span data-stu-id="aaadb-242">Spam filter verdict</span></span>|<span data-ttu-id="aaadb-243">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="aaadb-243">Description</span></span>|
  |---|---|---|
  |<span data-ttu-id="aaadb-244">**Möjlighet**</span><span class="sxs-lookup"><span data-stu-id="aaadb-244">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="aaadb-245">Meddelandet har marker ATS som icke skräp post och/eller ignorerade filtrering innan skräp post filtrering.</span><span class="sxs-lookup"><span data-stu-id="aaadb-245">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering.</span></span> <span data-ttu-id="aaadb-246">Meddelandet markerades till exempel som inte skräp post av en regel för e-postflöde (kallas även transport regel).</span><span class="sxs-lookup"><span data-stu-id="aaadb-246">For example, the message was marked as not spam by a mail flow rule (also known as a transport rule).</span></span><br/><br/><span data-ttu-id="aaadb-247">Meddelandet ignorerade spam av andra orsaker.</span><span class="sxs-lookup"><span data-stu-id="aaadb-247">The message skipped spam filtering for other reasons.</span></span> <span data-ttu-id="aaadb-248">Avsändaren och mottagaren ser till exempel ut i samma organisation.</span><span class="sxs-lookup"><span data-stu-id="aaadb-248">For example, the sender and recipient appear to be in the same organization.</span></span>|
  |<span data-ttu-id="aaadb-249">**Blockering**</span><span class="sxs-lookup"><span data-stu-id="aaadb-249">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="aaadb-250">Meddelandet har marker ATS som skräp post innan det utvärderas av skräp post filtrering.</span><span class="sxs-lookup"><span data-stu-id="aaadb-250">The message was marked as spam before being evaluated by spam filtering.</span></span> <span data-ttu-id="aaadb-251">Till exempel med en regel för e-postflöde.</span><span class="sxs-lookup"><span data-stu-id="aaadb-251">For example, by a mail flow rule.</span></span>|
  |<span data-ttu-id="aaadb-252">**Upptäckte**</span><span class="sxs-lookup"><span data-stu-id="aaadb-252">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="aaadb-253">Meddelandet markerades som skräppost av skräppostfiltret.</span><span class="sxs-lookup"><span data-stu-id="aaadb-253">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="aaadb-254">**Identifieras inte**</span><span class="sxs-lookup"><span data-stu-id="aaadb-254">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="aaadb-255">Meddelandet har marker ATS som inte skräp post av filtrering av skräp post.</span><span class="sxs-lookup"><span data-stu-id="aaadb-255">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="aaadb-256">**Levereras**</span><span class="sxs-lookup"><span data-stu-id="aaadb-256">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="aaadb-257">Meddelandet hoppade över skräp post filtrering eftersom det släpptes från karantän.</span><span class="sxs-lookup"><span data-stu-id="aaadb-257">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="aaadb-258">**Tillåt klient organisation**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="aaadb-258">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="aaadb-259">Meddelandet hoppade över skräp post filtrering på grund av inställningarna i en policy för skräp post.</span><span class="sxs-lookup"><span data-stu-id="aaadb-259">The message skipped spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="aaadb-260">Avsändaren fanns till exempel i listan över tillåtna avsändare eller tillåtna domäner.</span><span class="sxs-lookup"><span data-stu-id="aaadb-260">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="aaadb-261">**Klient blockering**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="aaadb-261">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="aaadb-262">Meddelandet blockerades av filtrering av skräp post på grund av inställningarna i en policy för skräp post.</span><span class="sxs-lookup"><span data-stu-id="aaadb-262">The message was blocked by spam filtering because of the settings in an anti-spam policy.</span></span> <span data-ttu-id="aaadb-263">Avsändaren fanns till exempel i listan över tillåtna avsändare eller tillåtna domäner.</span><span class="sxs-lookup"><span data-stu-id="aaadb-263">For example, the sender was in the allowed sender list or allowed domain list.</span></span>|
  |<span data-ttu-id="aaadb-264">**Tillåt användare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="aaadb-264">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="aaadb-265">Meddelandet hoppade över skräp post filtrering eftersom avsändaren fanns i en användares lista med betrodda avsändare.</span><span class="sxs-lookup"><span data-stu-id="aaadb-265">The message skipped spam filtering because the sender was in a user's Safe Senders list.</span></span>|
  |<span data-ttu-id="aaadb-266">**User block**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="aaadb-266">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="aaadb-267">Meddelandet blockerades av skräp post filtrering eftersom avsändaren fanns i en användares lista över spärrade avsändare.</span><span class="sxs-lookup"><span data-stu-id="aaadb-267">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list.</span></span>|
  |<span data-ttu-id="aaadb-268">**ZAP**</span><span class="sxs-lookup"><span data-stu-id="aaadb-268">**ZAP**</span></span>|<span data-ttu-id="aaadb-269">ej tillämpligt</span><span class="sxs-lookup"><span data-stu-id="aaadb-269">n/a</span></span>|<span data-ttu-id="aaadb-270">[Automatisk rensning av Tom timme (Zap)](zero-hour-auto-purge.md) flyttade det levererade meddelandet till mappen skräp post eller karantän.</span><span class="sxs-lookup"><span data-stu-id="aaadb-270">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) moved the delivered message to the Junk Email folder or quarantine.</span></span> <span data-ttu-id="aaadb-271">Du konfigurerar åtgärden i policyn för skydd mot skräp post.</span><span class="sxs-lookup"><span data-stu-id="aaadb-271">You configure the action in your anti-spam policy.</span></span>|
  |

  <span data-ttu-id="aaadb-272"><sup>\*</sup> Granska dina skydd mot skräp post eftersom det tillåtna meddelandet förmodligen har blockerats av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="aaadb-272"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="aaadb-273"><sup>\*\*</sup> Granska dina principer för skräp post, eftersom dessa meddelanden bör vara i karantän, inte levereras.</span><span class="sxs-lookup"><span data-stu-id="aaadb-273"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="aaadb-274">**Leverans ställen**: du kommer troligen att behöva undersöka meddelanden som har levererats till mottagarna (antingen till Inkorgen eller mappen skräp post), även om användarna inte klickar på nytto lastens URL i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="aaadb-274">**Delivery locations**: You'll likely want to investigate messages that were delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="aaadb-275">Du kan också ta bort meddelanden i karantänen från karantänen.</span><span class="sxs-lookup"><span data-stu-id="aaadb-275">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="aaadb-276">Mer information finns i [e-postmeddelanden i karantän i EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="aaadb-276">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="aaadb-277">**Borttagen mapp**</span><span class="sxs-lookup"><span data-stu-id="aaadb-277">**Deleted folder**</span></span>
  - <span data-ttu-id="aaadb-278">**Avbröts**</span><span class="sxs-lookup"><span data-stu-id="aaadb-278">**Dropped**</span></span>
  - <span data-ttu-id="aaadb-279">**Externt**: mottagaren finns i din lokala e-postorganisation i hybrid miljöer.</span><span class="sxs-lookup"><span data-stu-id="aaadb-279">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="aaadb-280">**Misslyckades**</span><span class="sxs-lookup"><span data-stu-id="aaadb-280">**Failed**</span></span>
  - <span data-ttu-id="aaadb-281">**Vidarekopplas**</span><span class="sxs-lookup"><span data-stu-id="aaadb-281">**Forwarded**</span></span>
  - <span data-ttu-id="aaadb-282">**Brevlåda**</span><span class="sxs-lookup"><span data-stu-id="aaadb-282">**Inbox**</span></span>
  - <span data-ttu-id="aaadb-283">**Skräppostmappen**</span><span class="sxs-lookup"><span data-stu-id="aaadb-283">**Junk folder**</span></span>
  - <span data-ttu-id="aaadb-284">**Karantän**</span><span class="sxs-lookup"><span data-stu-id="aaadb-284">**Quarantine**</span></span>
  - <span data-ttu-id="aaadb-285">**Okänd**</span><span class="sxs-lookup"><span data-stu-id="aaadb-285">**Unknown**</span></span>

- <span data-ttu-id="aaadb-286">**URL-musklick**: de här värdena beskrivs i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="aaadb-286">**URL clicks**: These values are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="aaadb-287">I alla lager som innehåller fler än 10 objekt visas de 10 översta objekten, medan resten samlas samman i **andra**.</span><span class="sxs-lookup"><span data-stu-id="aaadb-287">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="aaadb-288">URL-klickningar</span><span class="sxs-lookup"><span data-stu-id="aaadb-288">URL clicks</span></span>

<span data-ttu-id="aaadb-289">När ett nät fiske meddelande levereras till en mottagares inkorg eller mapp för skräp post kan användaren klicka på nytto lastens URL-adress.</span><span class="sxs-lookup"><span data-stu-id="aaadb-289">When a phishing message is delivered to a recipient's Inbox or Junk Email folder, there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="aaadb-290">Att klicka på URL-adressen är en liten mått på framgång, men du måste fastställa varför nät fiske meddelandet levererades till post lådan.</span><span class="sxs-lookup"><span data-stu-id="aaadb-290">Not clicking on the URL is a small measure of success, but you need to determine why the phishing message was even delivered to the mailbox.</span></span>

<span data-ttu-id="aaadb-291">Om en användare klickar på nytto lastens URL i nät fiske meddelandet visas åtgärderna i området URL- **klickning** i diagrammet i vyn kampanj information.</span><span class="sxs-lookup"><span data-stu-id="aaadb-291">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="aaadb-292">**Möjlighet**</span><span class="sxs-lookup"><span data-stu-id="aaadb-292">**Allowed**</span></span>

- <span data-ttu-id="aaadb-293">**BlockPage**: mottagaren klickade på nytto lastens URL, men deras åtkomst till den illasinnade webbplatsen blockerades av en princip för [säkra länkar](atp-safe-links.md) i organisationen.</span><span class="sxs-lookup"><span data-stu-id="aaadb-293">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by a [Safe Links](atp-safe-links.md) policy in your organization.</span></span>

- <span data-ttu-id="aaadb-294">**BlockPageOverride**: mottagaren klickade på nytto lastens URL i meddelandet, men säkra länkar försökte stoppa dem, men de har kunnat åsidosätta blocket.</span><span class="sxs-lookup"><span data-stu-id="aaadb-294">**BlockPageOverride**: The recipient clicked on the payload URL in the message, Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="aaadb-295">Undersök dina [principer för säkra länkar](set-up-atp-safe-links-policies.md) för att se varför användare tillåts att åsidosätta Safe Links-Verdict och fortsätta till den illasinnade webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="aaadb-295">Inspect your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="aaadb-296">**PendingDetonationPage**: säkra bilagor i Office 365 ATP är att öppna och undersöka nytto lastens URL i en virtuell dator miljö.</span><span class="sxs-lookup"><span data-stu-id="aaadb-296">**PendingDetonationPage**: Safe Attachments in Office 365 ATP is in the process of opening and investigating the payload URL in a virtual computer environment.</span></span>

- <span data-ttu-id="aaadb-297">**PendingDetonationPageOverride**: mottagaren har fått tillåtelse att åsidosätta nytto toner processen och öppna URL: en utan att vänta på resultaten.</span><span class="sxs-lookup"><span data-stu-id="aaadb-297">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="aaadb-298">TABB</span><span class="sxs-lookup"><span data-stu-id="aaadb-298">Tabs</span></span>

<span data-ttu-id="aaadb-299">Flikarna i vyn kampanj information gör att du kan undersöka kampanjen ytterligare.</span><span class="sxs-lookup"><span data-stu-id="aaadb-299">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="aaadb-300">Informationen som visas på flikarna styrs av det skuggade datum intervallet i tids linjen enligt beskrivningen i avsnittet [kampanj information](#campaign-information) .</span><span class="sxs-lookup"><span data-stu-id="aaadb-300">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="aaadb-301">**URL klickar**på: om användare inte klickar på nytto lastens URL i meddelandet är det här avsnittet tomt.</span><span class="sxs-lookup"><span data-stu-id="aaadb-301">**URL clicks**: If users didn't click on the payload URL in the message, this section will be blank.</span></span> <span data-ttu-id="aaadb-302">Om en användare kunde klicka på URL-adressen fylls följande värden i:</span><span class="sxs-lookup"><span data-stu-id="aaadb-302">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="aaadb-303">**Användarläge**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="aaadb-303">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="aaadb-304">**:**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="aaadb-304">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="aaadb-305">**Klicka på tid**</span><span class="sxs-lookup"><span data-stu-id="aaadb-305">**Click time**</span></span>
  - <span data-ttu-id="aaadb-306">**Klicka på Verdict**</span><span class="sxs-lookup"><span data-stu-id="aaadb-306">**Click verdict**</span></span>

- <span data-ttu-id="aaadb-307">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="aaadb-307">**Sender IPs**</span></span>

  - <span data-ttu-id="aaadb-308">**Avsändarens IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="aaadb-308">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="aaadb-309">**Totalt antal**</span><span class="sxs-lookup"><span data-stu-id="aaadb-309">**Total count**</span></span>
  - <span data-ttu-id="aaadb-310">**Inkorgen**</span><span class="sxs-lookup"><span data-stu-id="aaadb-310">**Inboxed**</span></span>
  - <span data-ttu-id="aaadb-311">**Inte i Inkorgen**</span><span class="sxs-lookup"><span data-stu-id="aaadb-311">**Not Inboxed**</span></span>
  - <span data-ttu-id="aaadb-312">**SPF skickades**: avsändaren autentiserades av [SPF (avsändare Policy Framework)](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="aaadb-312">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="aaadb-313">En avsändare som inte skickar SPF-verifiering indikerar en oautentiserad avsändare eller meddelandet har falskats för en legitim avsändare.</span><span class="sxs-lookup"><span data-stu-id="aaadb-313">A sender that doesn't pass SPF validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="aaadb-314">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="aaadb-314">**Senders**</span></span>

  - <span data-ttu-id="aaadb-315">**Avsändare**: det här är den faktiska avsändar adressen i SMTP e-postmeddelandet, som inte nödvändigt vis är den e-postadress som användarna ser i sina e-postklienter.</span><span class="sxs-lookup"><span data-stu-id="aaadb-315">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="aaadb-316">**Totalt antal**</span><span class="sxs-lookup"><span data-stu-id="aaadb-316">**Total count**</span></span>
  - <span data-ttu-id="aaadb-317">**Inkorgen**</span><span class="sxs-lookup"><span data-stu-id="aaadb-317">**Inboxed**</span></span>
  - <span data-ttu-id="aaadb-318">**Inte i Inkorgen**</span><span class="sxs-lookup"><span data-stu-id="aaadb-318">**Not Inboxed**</span></span>
  - <span data-ttu-id="aaadb-319">**DKIM lyckades**: avsändaren autentiserades av [domän nycklar som identifieras via e-post (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span><span class="sxs-lookup"><span data-stu-id="aaadb-319">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="aaadb-320">En avsändare som inte skickar DKIM verifiering indikerar en overifierad avsändare eller meddelandet har falskats för en legitim avsändare.</span><span class="sxs-lookup"><span data-stu-id="aaadb-320">A sender that doesn't pass DKIM validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="aaadb-321">**DMARC skickades**: avsändaren autentiserades av [domänbaserad autentisering, rapportering och omslutande (DMARC)](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="aaadb-321">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="aaadb-322">En avsändare som inte skickar DMARC verifiering indikerar en overifierad avsändare eller meddelandet har falskats för en legitim avsändare.</span><span class="sxs-lookup"><span data-stu-id="aaadb-322">A sender that doesn't pass DMARC validation indicates an unauthenticated sender, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="aaadb-323">**Bifogade filer**</span><span class="sxs-lookup"><span data-stu-id="aaadb-323">**Attachments**</span></span>

  - <span data-ttu-id="aaadb-324">**Datafil**</span><span class="sxs-lookup"><span data-stu-id="aaadb-324">**Filename**</span></span>
  - <span data-ttu-id="aaadb-325">**SHA256**</span><span class="sxs-lookup"><span data-stu-id="aaadb-325">**SHA256**</span></span>
  - <span data-ttu-id="aaadb-326">**Familjen skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="aaadb-326">**Malware family**</span></span>
  - <span data-ttu-id="aaadb-327">**Totalt antal**</span><span class="sxs-lookup"><span data-stu-id="aaadb-327">**Total count**</span></span>

- <span data-ttu-id="aaadb-328">**:**</span><span class="sxs-lookup"><span data-stu-id="aaadb-328">**URL**</span></span>

  - <span data-ttu-id="aaadb-329">**:**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="aaadb-329">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="aaadb-330">**Totalt antal**</span><span class="sxs-lookup"><span data-stu-id="aaadb-330">**Total Count**</span></span>

<span data-ttu-id="aaadb-331"><sup>\*</sup> Om du klickar på det här värdet öppnas en ny utfällare som innehåller mer information om det angivna objektet (användare, URL: er osv.).</span><span class="sxs-lookup"><span data-stu-id="aaadb-331"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="aaadb-332">Om du vill gå tillbaka till vyn kampanj Detaljer klickar du på **klar** i den nya utfällbara menyn.</span><span class="sxs-lookup"><span data-stu-id="aaadb-332">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="aaadb-333">Pilknapp</span><span class="sxs-lookup"><span data-stu-id="aaadb-333">Buttons</span></span>

<span data-ttu-id="aaadb-334">Med knapparna i vyn kampanj information kan du använda privilegiet mot hot Explorer för att undersöka kampanjen.</span><span class="sxs-lookup"><span data-stu-id="aaadb-334">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="aaadb-335">**Utforska kampanjen**: öppna en ny Threat Explorer-fliken Sök med hjälp av värdet för **kampanj-ID** som Sök filter.</span><span class="sxs-lookup"><span data-stu-id="aaadb-335">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="aaadb-336">**Utforska meddelanden i Inkorgen**: öppnar en ny webbplats Sök-flik med **kampanj-ID** och **leverans plats: Inkorgen** som Sök filter.</span><span class="sxs-lookup"><span data-stu-id="aaadb-336">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
