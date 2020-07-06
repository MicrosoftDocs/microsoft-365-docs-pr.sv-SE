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
description: Läs mer om kampanjvyer i det avancerade hotskyddet i Office 365.
ms.openlocfilehash: fe443c43fa5cea8ec6e3e1c0bc5ee5307b5c28f6
ms.sourcegitcommit: 9ee1261c405f82b49c62390a25dfdea23340d644
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2020
ms.locfileid: "45039484"
---
# <a name="campaign-views-in-atp"></a><span data-ttu-id="f308d-103">Kampanjvyer i ATP</span><span class="sxs-lookup"><span data-stu-id="f308d-103">Campaign Views in ATP</span></span>

<span data-ttu-id="f308d-104">Kampanjvyer är en funktion i Advanced Threat Protection (ATP) i Security & Compliance Center som identifierar och kategoriserar nätfiskeattacker i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f308d-104">Campaign Views is a feature in Advanced Threat Protection (ATP) in the Security & Compliance Center that identifies and categorizes phishing attacks in the service.</span></span> <span data-ttu-id="f308d-105">Kampanjvyer kan hjälpa dig att:</span><span class="sxs-lookup"><span data-stu-id="f308d-105">Campaign Views can help you to:</span></span>

- <span data-ttu-id="f308d-106">Effektivt undersöka och svara på phishing-attacker.</span><span class="sxs-lookup"><span data-stu-id="f308d-106">Efficiently investigate and respond to phishing attacks.</span></span>

- <span data-ttu-id="f308d-107">Bättre förstå omfattningen av attacken.</span><span class="sxs-lookup"><span data-stu-id="f308d-107">Better understand the scope of the attack.</span></span>

- <span data-ttu-id="f308d-108">Visa värde för beslutsfattare.</span><span class="sxs-lookup"><span data-stu-id="f308d-108">Show value to decision makers.</span></span>

<span data-ttu-id="f308d-109">Med kampanjvyer kan du se helheten av en attack snabbare och mer komplett än någon människa.</span><span class="sxs-lookup"><span data-stu-id="f308d-109">Campaign Views lets you see the big picture of an attack faster and more complete than any human.</span></span>

## <a name="what-is-a-campaign"></a><span data-ttu-id="f308d-110">Vad är en kampanj?</span><span class="sxs-lookup"><span data-stu-id="f308d-110">What is a campaign?</span></span>

<span data-ttu-id="f308d-111">En kampanj är en samordnad e-postattack mot en eller flera organisationer.</span><span class="sxs-lookup"><span data-stu-id="f308d-111">A campaign is a coordinated email attack against one or many organizations.</span></span> <span data-ttu-id="f308d-112">E-postattacker som stjäl referenser och företagsdata är en stor och lukrativ bransch.</span><span class="sxs-lookup"><span data-stu-id="f308d-112">Email attacks that steal credentials and company data are a big and lucrative industry.</span></span> <span data-ttu-id="f308d-113">I takt med att tekniken ökar i ett försök att stoppa attacker ändrar angripare sina metoder i ett försök att säkerställa fortsatt framgång.</span><span class="sxs-lookup"><span data-stu-id="f308d-113">As technologies increase in an effort to stop attacks, attackers modify their methods in an effort to ensure continued success.</span></span>

<span data-ttu-id="f308d-114">Microsoft utnyttjar de stora mängderna anti-phishing, anti-spam och anti-malware data över hela tjänsten för att identifiera kampanjer.</span><span class="sxs-lookup"><span data-stu-id="f308d-114">Microsoft leverages the vast amounts of anti-phishing, anti-spam, and anti-malware data across the entire service to help identify campaigns.</span></span> <span data-ttu-id="f308d-115">Vi analyserar och klassificerar attackinformationen enligt flera faktorer.</span><span class="sxs-lookup"><span data-stu-id="f308d-115">We analyze and classify the attack information according to several factors.</span></span> <span data-ttu-id="f308d-116">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="f308d-116">For example:</span></span>

- <span data-ttu-id="f308d-117">**Attack källa:** Källan IP-adresser och avsändare e-domäner.</span><span class="sxs-lookup"><span data-stu-id="f308d-117">**Attack source**: The source IP addresses and sender email domains.</span></span>

- <span data-ttu-id="f308d-118">**Attack meddelandeegenskaper:** Innehållet, stilen och tonen i meddelandena.</span><span class="sxs-lookup"><span data-stu-id="f308d-118">**Attack message properties**: The content, style, and tone of the messages.</span></span>

- <span data-ttu-id="f308d-119">**Attackmottagare:** Mottagare, mottagarjobbsfunktioner (administratörer, chefer osv.), företagstyper (stora, små, offentliga, privata osv.) och branscher.</span><span class="sxs-lookup"><span data-stu-id="f308d-119">**Attack recipients**: Recipient domains, recipient job functions (admins, executives, etc.), company types (large, small, public, private, etc.), and industries.</span></span>

- <span data-ttu-id="f308d-120">**Attack nyttolast:** Skadliga länkar, bilagor eller andra nyttolaster i meddelandena.</span><span class="sxs-lookup"><span data-stu-id="f308d-120">**Attack payload**: Malicious links, attachments, or other payloads in the messages.</span></span>

<span data-ttu-id="f308d-121">En kampanj kan vara kortlivad eller sträcka sig över flera dagar, veckor eller månader med aktiva och inaktiva perioder.</span><span class="sxs-lookup"><span data-stu-id="f308d-121">A campaign might be short-lived, or could span several days, weeks, or months with active and inactive periods.</span></span> <span data-ttu-id="f308d-122">En kampanj kan startas mot din specifika organisation, eller så kan din organisation vara en del av en större kampanj för flera företag.</span><span class="sxs-lookup"><span data-stu-id="f308d-122">A campaign might be launched against your specific organization, or your organization might be part of a larger campaign across multiple companies.</span></span>

## <a name="campaign-views-the-security--compliance-center"></a><span data-ttu-id="f308d-123">Kampanjvyer säkerhets- & compliance center</span><span class="sxs-lookup"><span data-stu-id="f308d-123">Campaign Views the Security & Compliance Center</span></span>

<span data-ttu-id="f308d-124">Kampanjvyer är tillgängliga i [Security & Compliance Center](https://protection.office.com) vid **hothanteringskampanjer** \> **Campaigns**eller direkt på <https://protection.office.com/campaigns> .</span><span class="sxs-lookup"><span data-stu-id="f308d-124">Campaign Views is available in the [Security & Compliance Center](https://protection.office.com) at **Threat management** \> **Campaigns**, or directly at <https://protection.office.com/campaigns>.</span></span>

![Översikt över kampanjer i Security & Compliance Center](../../media/campaigns-overview.png)

<span data-ttu-id="f308d-126">Du kan också komma åt kampanjvyer från:</span><span class="sxs-lookup"><span data-stu-id="f308d-126">You can also get to Campaign Views from:</span></span>

- <span data-ttu-id="f308d-127">**Hantering av** \> hot **Explorer** \> **Visa** \> **Kampanjer**</span><span class="sxs-lookup"><span data-stu-id="f308d-127">**Threat management** \> **Explorer** \> **View** \> **Campaigns**</span></span>

- <span data-ttu-id="f308d-128">**Hantering av** \> hot **Explorer** \> **Visa** \> **Alla e-postmeddelanden** \> **Fliken Kampanj**</span><span class="sxs-lookup"><span data-stu-id="f308d-128">**Threat management** \> **Explorer** \> **View** \> **All email** \> **Campaign** tab</span></span>

- <span data-ttu-id="f308d-129">**Hantering av** \> hot **Explorer** \> **Visa** \> **Phish (phish)** \> **Fliken Kampanj**</span><span class="sxs-lookup"><span data-stu-id="f308d-129">**Threat management** \> **Explorer** \> **View** \> **Phish** \> **Campaign** tab</span></span>

- <span data-ttu-id="f308d-130">**Hantering av** \> hot **Explorer** \> **Visa** \> **Skadlig kod** \> **Fliken Kampanj**</span><span class="sxs-lookup"><span data-stu-id="f308d-130">**Threat management** \> **Explorer** \> **View** \> **Malware** \> **Campaign** tab</span></span>

<span data-ttu-id="f308d-131">För att komma åt kampanjvyer måste du vara medlem i rollgrupperna **Organisationshantering,** **Säkerhetsadministratör**eller **Säkerhetsläsare** i säkerhets- & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="f308d-131">To access Campaign Views, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="f308d-132">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f308d-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="campaigns-overview"></a><span data-ttu-id="f308d-133">Översikt över kampanjer</span><span class="sxs-lookup"><span data-stu-id="f308d-133">Campaigns overview</span></span>

<span data-ttu-id="f308d-134">Översiktssidan visar information om alla kampanjer.</span><span class="sxs-lookup"><span data-stu-id="f308d-134">The overview page shows information about all campaigns.</span></span>

<span data-ttu-id="f308d-135">På fliken **Kampanj** visar området **Kampanjtyp** ett stapeldiagram som visar antalet mottagare per dag.</span><span class="sxs-lookup"><span data-stu-id="f308d-135">On the default **Campaign** tab, the **Campaign type** area shows a bar graph that shows the number of recipients per day.</span></span> <span data-ttu-id="f308d-136">Som standard visar diagrammet både **Phish-** och **Malware-data.**</span><span class="sxs-lookup"><span data-stu-id="f308d-136">By default, the graph shows both **Phish** and **Malware** data.</span></span>

> [!TIP]
> <span data-ttu-id="f308d-137">Om du inte ser några kampanjdata kan du prova att ändra datumintervallet eller [filtren](#filters-and-settings).</span><span class="sxs-lookup"><span data-stu-id="f308d-137">If you don't see any campaign data, try changing the date range or [filters](#filters-and-settings).</span></span>

<span data-ttu-id="f308d-138">På sidan Översikt visas följande information på fliken **Kampanj:**</span><span class="sxs-lookup"><span data-stu-id="f308d-138">The rest of the overview page shows the following information on the **Campaign** tab:</span></span>

- <span data-ttu-id="f308d-139">**Namn**</span><span class="sxs-lookup"><span data-stu-id="f308d-139">**Name**</span></span>

- <span data-ttu-id="f308d-140">**Exempelämne**: Ämnesraden för ett av meddelandena i kampanjen.</span><span class="sxs-lookup"><span data-stu-id="f308d-140">**Sample subject**: The subject line of one of the messages in the campaign.</span></span> <span data-ttu-id="f308d-141">Observera att alla meddelanden i kampanjen inte nödvändigtvis har samma ämne.</span><span class="sxs-lookup"><span data-stu-id="f308d-141">Note that all messages in the campaign will not necessarily have the same subject.</span></span>

- <span data-ttu-id="f308d-142">**Riktad**: Procentsatsen som beräknat med: (antalet kampanjmottagare i organisationen) / (det totala antalet mottagare i kampanjen i alla organisationer i tjänsten).</span><span class="sxs-lookup"><span data-stu-id="f308d-142">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="f308d-143">Det här värdet anger i vilken utsträckning kampanjen är specifikt riktad till din organisation (ett högre värde) jämfört med andra organisationer i tjänsten (ett lägre värde).</span><span class="sxs-lookup"><span data-stu-id="f308d-143">This value indicates the degree to which the campaign is specifically directed at your organization (a higher value) vs. directed at other organizations in the service (a lower value).</span></span>

- <span data-ttu-id="f308d-144">**Typ:** Detta värde är antingen **Phish** eller **Malware**.</span><span class="sxs-lookup"><span data-stu-id="f308d-144">**Type**: This value is either **Phish** or **Malware**.</span></span>

- <span data-ttu-id="f308d-145">**Undertyp**: Det här värdet innehåller mer information om kampanjen.</span><span class="sxs-lookup"><span data-stu-id="f308d-145">**Subtype**: This value contains more details about the campaign.</span></span> <span data-ttu-id="f308d-146">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="f308d-146">For example:</span></span>

  - <span data-ttu-id="f308d-147">**Phish**: Om tillgängligt, det varumärke som phished av denna kampanj.</span><span class="sxs-lookup"><span data-stu-id="f308d-147">**Phish**: Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="f308d-148">Till exempel `Microsoft` `365` , , , eller `Unknown` `Outlook` `DocuSign` .</span><span class="sxs-lookup"><span data-stu-id="f308d-148">For example, `Microsoft`, `365`, `Unknown`, `Outlook`, or `DocuSign`.</span></span>

  - <span data-ttu-id="f308d-149">**Skadlig kod:** Till exempel, `HTML/PHISH` eller `HTML/<MalwareFamilyName>` .</span><span class="sxs-lookup"><span data-stu-id="f308d-149">**Malware**: For example, `HTML/PHISH` or `HTML/<MalwareFamilyName>`.</span></span>

<span data-ttu-id="f308d-150">Om det finns, det varumärke som phished av denna kampanj.</span><span class="sxs-lookup"><span data-stu-id="f308d-150">Where available, the brand that is being phished by this campaign.</span></span> <span data-ttu-id="f308d-151">När identifieringen drivs av **ATP-teknik** läggs prefixet ATP till undertypsvärdet.</span><span class="sxs-lookup"><span data-stu-id="f308d-151">When the detection is driven by ATP technology, the prefix **ATP-** is added to the subtype value.</span></span>

- <span data-ttu-id="f308d-152">**Mottagare**: Antalet användare som har riktats mot kampanjen.</span><span class="sxs-lookup"><span data-stu-id="f308d-152">**Recipients**: The number of users that were targeted by this campaign.</span></span>

- <span data-ttu-id="f308d-153">**Inkorg**: Antalet användare som har fått meddelanden från den här kampanjen i inkorgen (inte levererat till mappen Skräppost).</span><span class="sxs-lookup"><span data-stu-id="f308d-153">**Inboxed**: The number of users that received messages from this campaign in their Inbox (not delivered to their Junk Email folder).</span></span>

- <span data-ttu-id="f308d-154">**Klickade på**: Antalet användare som klickade på webbadressen eller öppnade den bifogade filen i nätfiskemeddelandet.</span><span class="sxs-lookup"><span data-stu-id="f308d-154">**Clicked**: The number of users that clicked on the URL or opened the attachment in the phishing message.</span></span>

- <span data-ttu-id="f308d-155">**Klickfrekvens**: Procentsatsen som beräknas av "**Klickad**  /  **inkorg**".</span><span class="sxs-lookup"><span data-stu-id="f308d-155">**Click rate**: The percentage as calculated by "**Clicked** / **Inboxed**".</span></span> <span data-ttu-id="f308d-156">Det här värdet är en indikator på kampanjens effektivitet och om mottagarna kunde identifiera meddelandet som nätfiske och undvika att klicka på nyttolast-url:en.</span><span class="sxs-lookup"><span data-stu-id="f308d-156">This value is an indicator of the effectiveness of the campaign, and whether the recipients were able to identify the message as phishing and avoid clicking on the payload URL.</span></span>

  <span data-ttu-id="f308d-157">Observera att det här värdet inte används i kampanjer för skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="f308d-157">Note that this value isn't used in malware campaigns.</span></span>

- <span data-ttu-id="f308d-158">**Besökt:** Hur många användare som faktiskt gjorde det genom att nyttolasten webbplats.</span><span class="sxs-lookup"><span data-stu-id="f308d-158">**Visited**: How many users actually made it through to the payload website.</span></span> <span data-ttu-id="f308d-159">Om det finns klickade värden, men säkra länkar **blockeras** åtkomst till webbplatsen, kommer detta värde att vara noll.</span><span class="sxs-lookup"><span data-stu-id="f308d-159">If there are **Clicked** values, but Safe Links blocked access to the website, this value will be zero.</span></span>

<span data-ttu-id="f308d-160">På fliken **Kampanjursprung** visas meddelandekällorna på en världskarta.</span><span class="sxs-lookup"><span data-stu-id="f308d-160">The **Campaign origin** tab shows the message sources on a map of the world.</span></span>

### <a name="filters-and-settings"></a><span data-ttu-id="f308d-161">Filter och inställningar</span><span class="sxs-lookup"><span data-stu-id="f308d-161">Filters and settings</span></span>

<span data-ttu-id="f308d-162">Högst upp på sidan Kampanjvyer finns det flera filter- och frågeinställningar som hjälper dig att hitta och isolera specifika kampanjer.</span><span class="sxs-lookup"><span data-stu-id="f308d-162">At the top of the Campaign Views page, there are several filter and query settings to help you find and isolate specific campaigns.</span></span>

![Kampanjfilter](../../media/campaign-filters-and-settings.png)

<span data-ttu-id="f308d-164">Den mest grundläggande filtrering som du kan göra är startdatum/tid och slutdatum/-tid.</span><span class="sxs-lookup"><span data-stu-id="f308d-164">The most basic filtering that you can do is the start date/time and the end date/time.</span></span>

<span data-ttu-id="f308d-165">Om du vill filtrera vyn ytterligare kan du göra en enda egenskap med flera värden som filtrerar genom att klicka på knappen **Kampanjtyp,** göra ditt val och sedan klicka på **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="f308d-165">To further filter the view, you can do single property with multiple values filtering by clicking the **Campaign type** button, making your selection, and then clicking **Refresh**.</span></span>

<span data-ttu-id="f308d-166">De tillgängliga kampanjegenskaperna beskrivs i följande lista:</span><span class="sxs-lookup"><span data-stu-id="f308d-166">The available campaign properties are described in the following list:</span></span>

- <span data-ttu-id="f308d-167">Grundläggande</span><span class="sxs-lookup"><span data-stu-id="f308d-167">Basic</span></span>

  - <span data-ttu-id="f308d-168">**Kampanjtyp:** Välj **Skadlig kod** eller **Phish**.</span><span class="sxs-lookup"><span data-stu-id="f308d-168">**Campaign type**: Select **Malware** or **Phish**.</span></span> <span data-ttu-id="f308d-169">När du rensar markeringarna får du samma resultat som att välja båda.</span><span class="sxs-lookup"><span data-stu-id="f308d-169">Clearing the selections has the same result as selecting both.</span></span>
  - <span data-ttu-id="f308d-170">**Kampanjnamn**</span><span class="sxs-lookup"><span data-stu-id="f308d-170">**Campaign name**</span></span>
  - <span data-ttu-id="f308d-171">**Undertyp för kampanj**</span><span class="sxs-lookup"><span data-stu-id="f308d-171">**Campaign subtype**</span></span>
  - <span data-ttu-id="f308d-172">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="f308d-172">**Sender**</span></span>
  - <span data-ttu-id="f308d-173">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="f308d-173">**Recipients**</span></span>
  - <span data-ttu-id="f308d-174">**Avsändningsdomän**</span><span class="sxs-lookup"><span data-stu-id="f308d-174">**Sender domain**</span></span>
  - <span data-ttu-id="f308d-175">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="f308d-175">**Subject**</span></span>
  - <span data-ttu-id="f308d-176">**Filnamn för bifogad fil**</span><span class="sxs-lookup"><span data-stu-id="f308d-176">**Attachment filename**</span></span>
  - <span data-ttu-id="f308d-177">**Malware familj**</span><span class="sxs-lookup"><span data-stu-id="f308d-177">**Malware family**</span></span>
  - <span data-ttu-id="f308d-178">**Leveransåtgärd**</span><span class="sxs-lookup"><span data-stu-id="f308d-178">**Delivery action**</span></span>
  - <span data-ttu-id="f308d-179">**Detektionsteknik**</span><span class="sxs-lookup"><span data-stu-id="f308d-179">**Detection technology**</span></span>
  - <span data-ttu-id="f308d-180">**Taggar**</span><span class="sxs-lookup"><span data-stu-id="f308d-180">**Tags**</span></span>
  - <span data-ttu-id="f308d-181">**System åsidosättningar**</span><span class="sxs-lookup"><span data-stu-id="f308d-181">**System overrides**</span></span>

- <span data-ttu-id="f308d-182">Avancerade</span><span class="sxs-lookup"><span data-stu-id="f308d-182">Advanced</span></span>

  - <span data-ttu-id="f308d-183">**Internet-meddelande-ID:** Tillgängligt i fältet **Meddelande-ID-huvud** i meddelandehuvudet.</span><span class="sxs-lookup"><span data-stu-id="f308d-183">**Internet message ID**: Available in the **Message-ID** header field in the message header.</span></span> <span data-ttu-id="f308d-184">Ett exempelvärde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (notera vinkelparenteserna).</span><span class="sxs-lookup"><span data-stu-id="f308d-184">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
  
  - <span data-ttu-id="f308d-185">**Nätverksmeddelande-ID:** Ett GUID-värde som är tillgängligt i huvudfältet **X-MS-Exchange-Organization-Network-Message-Id** i meddelandehuvudet.</span><span class="sxs-lookup"><span data-stu-id="f308d-185">**Network message ID**: A GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header field in the message header.</span></span>
  
  - <span data-ttu-id="f308d-186">**IP-adress för avsändare**</span><span class="sxs-lookup"><span data-stu-id="f308d-186">**Sender IP**</span></span>
  
  - <span data-ttu-id="f308d-187">**BIFOGAD FIL SHA256**: Om du vill hitta SHA256-hash-värdet för en fil i Windows kör du följande kommando i en kommandotolk: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .</span><span class="sxs-lookup"><span data-stu-id="f308d-187">**Attachment SHA256**: To find the SHA256 hash value of a file in Windows, run the following command in a Command Prompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`.</span></span>
  
  - <span data-ttu-id="f308d-188">**Kluster-ID**</span><span class="sxs-lookup"><span data-stu-id="f308d-188">**Cluster ID**</span></span>
  
  - <span data-ttu-id="f308d-189">**Princip-ID för aviseringar**</span><span class="sxs-lookup"><span data-stu-id="f308d-189">**Alert Policy ID**</span></span>

- <span data-ttu-id="f308d-190">Webbadresser</span><span class="sxs-lookup"><span data-stu-id="f308d-190">URLs</span></span>

  - <span data-ttu-id="f308d-191">**URL-domän**</span><span class="sxs-lookup"><span data-stu-id="f308d-191">**URL domain**</span></span>
  - <span data-ttu-id="f308d-192">**URL-domän och url-sökväg**</span><span class="sxs-lookup"><span data-stu-id="f308d-192">**URL domain and path**</span></span>
  - <span data-ttu-id="f308d-193">**Url**</span><span class="sxs-lookup"><span data-stu-id="f308d-193">**URL**</span></span>
  - <span data-ttu-id="f308d-194">**URL-sökväg**</span><span class="sxs-lookup"><span data-stu-id="f308d-194">**URL path**</span></span>
  - <span data-ttu-id="f308d-195">**Klicka dom**</span><span class="sxs-lookup"><span data-stu-id="f308d-195">**Click verdict**</span></span>

<span data-ttu-id="f308d-196">Om du vill ha mer avancerad filtrering, inklusive filtrering efter flera egenskaper, kan du klicka på knappen **Avancerat filter** för att skapa en fråga.</span><span class="sxs-lookup"><span data-stu-id="f308d-196">For more advanced filtering, including filtering by multiple properties, you can click the **Advanced filter** button to build a query.</span></span> <span data-ttu-id="f308d-197">Samma kampanjegenskaper är tillgängliga, men med följande förbättringar:</span><span class="sxs-lookup"><span data-stu-id="f308d-197">The same campaign properties are available, but with the following enhancements:</span></span>

- <span data-ttu-id="f308d-198">Du kan klicka på **Lägg till ett villkor** för att välja flera villkor.</span><span class="sxs-lookup"><span data-stu-id="f308d-198">You can click **Add a condition** to select multiple conditions.</span></span>
- <span data-ttu-id="f308d-199">Du kan välja operatorn **Och** **eller Eller** mellan villkoren.</span><span class="sxs-lookup"><span data-stu-id="f308d-199">You can choose the **And** or **Or** operator between conditions.</span></span>
- <span data-ttu-id="f308d-200">Du kan välja objektet **Villkorsgrupp** längst ned i villkorslistan för att skapa komplexa sammansatta villkor.</span><span class="sxs-lookup"><span data-stu-id="f308d-200">You can select the **Condition group** item at the bottom of the conditions list to form complex compound conditions.</span></span>

<span data-ttu-id="f308d-201">När du är klar klickar du på knappen **Fråga.**</span><span class="sxs-lookup"><span data-stu-id="f308d-201">When you're finished, click the **Query** button.</span></span>

<span data-ttu-id="f308d-202">När du har skapat ett grundläggande eller avancerat filter kan du spara det med hjälp av **Spara fråga** eller **Spara fråga som**.</span><span class="sxs-lookup"><span data-stu-id="f308d-202">After you create a basic or advanced filter, you can save it by using **Save query** or **Save query as**.</span></span> <span data-ttu-id="f308d-203">När du senare går tillbaka till kampanjvyer kan du läsa in ett sparat filter genom att klicka på **Sparade frågeinställningar**.</span><span class="sxs-lookup"><span data-stu-id="f308d-203">Later, when you return to Campaign Views, you can load a saved filter by clicking **Saved query settings**.</span></span>

<span data-ttu-id="f308d-204">Om du vill exportera diagrammet eller listan över kampanjer klickar du på **Exportera** och väljer **Exportera diagramdata** eller **Exportkampanjlista**.</span><span class="sxs-lookup"><span data-stu-id="f308d-204">To export the graph or the list of campaigns, click **Export** and select **Export chart data** or **Export campaign list**.</span></span>

<span data-ttu-id="f308d-205">Om du har en Microsoft Defender ATP-prenumeration kan du klicka på **WDATP** för att ansluta eller koppla från kampanjinformationen med Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="f308d-205">If you have a Microsoft Defender ATP subscription, you can click **WDATP** to connect or disconnect the campaigns information with Microsoft Defender ATP.</span></span> <span data-ttu-id="f308d-206">Mer information finns i [Integrera Office 365 ATP med Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span><span class="sxs-lookup"><span data-stu-id="f308d-206">For more information, see [Integrate Office 365 ATP with Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).</span></span>

## <a name="campaign-details"></a><span data-ttu-id="f308d-207">Information om kampanj</span><span class="sxs-lookup"><span data-stu-id="f308d-207">Campaign details</span></span>

<span data-ttu-id="f308d-208">När du klickar på namnet på en kampanj visas kampanjinformationen i ett utfällbart utfällbart.</span><span class="sxs-lookup"><span data-stu-id="f308d-208">When you click on the name of a campaign, the campaign details appear in a flyout.</span></span>

### <a name="campaign-information"></a><span data-ttu-id="f308d-209">Kampanjinformation</span><span class="sxs-lookup"><span data-stu-id="f308d-209">Campaign information</span></span>

<span data-ttu-id="f308d-210">Högst upp i kampanjinformationsvyn finns följande kampanjinformation tillgänglig:</span><span class="sxs-lookup"><span data-stu-id="f308d-210">At the top of the campaign details view, the following campaign information is available:</span></span>

- <span data-ttu-id="f308d-211">**ID**: Den unika kampanjidentifieraren.</span><span class="sxs-lookup"><span data-stu-id="f308d-211">**ID**: The unique campaign identifier.</span></span>

- <span data-ttu-id="f308d-212">**Startad** och **avslutad:** Kampanjens startdatum och slutdatum.</span><span class="sxs-lookup"><span data-stu-id="f308d-212">**Started** and **Ended**: The start date and end date of the campaign.</span></span> <span data-ttu-id="f308d-213">Observera att dessa datum kan sträcka sig längre än dina filterdatum som du har valt på översiktssidan.</span><span class="sxs-lookup"><span data-stu-id="f308d-213">Note that these dates might extend further than your filter dates that you selected on the overview page.</span></span>

- <span data-ttu-id="f308d-214">**Effekt**: Det här avsnittet innehåller följande data för det datumintervallfilter du valt (eller som du väljer på tidslinjen):</span><span class="sxs-lookup"><span data-stu-id="f308d-214">**Impact**: This section contains the following data for the date range filter you selected (or that you select in the timeline):</span></span>
  
  - <span data-ttu-id="f308d-215">Det totala antalet mottagare.</span><span class="sxs-lookup"><span data-stu-id="f308d-215">The total number of recipients.</span></span>
  - <span data-ttu-id="f308d-216">Antalet meddelanden som var "Inkorged" (det vill än levereras till Inkorgen, inte till mappen Skräppost).</span><span class="sxs-lookup"><span data-stu-id="f308d-216">The number of messages that were "Inboxed" (that is, delivered to the Inbox, not to the Junk Email folder).</span></span>
  - <span data-ttu-id="f308d-217">Hur många användare klickade på webbadressens nyttolast i nätfiskemeddelandet.</span><span class="sxs-lookup"><span data-stu-id="f308d-217">How many users clicked on the URL payload in the phishing message.</span></span>
  - <span data-ttu-id="f308d-218">Howe många användare besökte webbadressen.</span><span class="sxs-lookup"><span data-stu-id="f308d-218">Howe many users visited the URL.</span></span>

- <span data-ttu-id="f308d-219">**Riktad**: Procentsatsen som beräknat med: (antalet kampanjmottagare i organisationen) / (det totala antalet mottagare i kampanjen i alla organisationer i tjänsten).</span><span class="sxs-lookup"><span data-stu-id="f308d-219">**Targeted**: The percentage as calculated by: (the number of campaign recipients in your organization) / (the total number of recipients in the campaign across all organizations in the service).</span></span> <span data-ttu-id="f308d-220">Observera att det här värdet beräknas under kampanjens hela livstid och inte ändrar filterdatumen.</span><span class="sxs-lookup"><span data-stu-id="f308d-220">Note that this value is calculated over the entire lifetime of the campaign, and doesn't change the filter dates.</span></span>

- <span data-ttu-id="f308d-221">En interaktiv tidslinje för kampanjaktivitet: Tidslinjen visar aktivitet under kampanjens hela livstid.</span><span class="sxs-lookup"><span data-stu-id="f308d-221">An interactive timeline of campaign activity: The timeline shows activity over the entire lifetime of the campaign.</span></span> <span data-ttu-id="f308d-222">Som standard innehåller det skuggade området det datumintervallfilter som du valde i översikten.</span><span class="sxs-lookup"><span data-stu-id="f308d-222">By default, the shaded area includes the date range filter that you selected in the overview.</span></span> <span data-ttu-id="f308d-223">Du kan klicka och dra för att välja en viss startpunkt och slutpunkt, <u>som ändrar de data som visas i **Impact-området** och på resten av sidan enligt beskrivningen i nästa avsnitt</u>.</span><span class="sxs-lookup"><span data-stu-id="f308d-223">You can click and drag to select a specific start point and end point, <u>which will change the data that's displayed in **Impact** area, and on the rest of the page as described in the next sections</u>.</span></span>

<span data-ttu-id="f308d-224">I namnlisten kan du klicka på knappen Hämta **kampanjbildning** Av att ladda ![ ned ](../../media/download-campaign-write-up-button.png) kampanjskrivningen för att hämta kampanjinformationen till ett Word-dokument (som standard med namnet CampaignReport.docx).</span><span class="sxs-lookup"><span data-stu-id="f308d-224">In the title bar, you can click the **Download campaign write-up** button ![Download campaign write-up icon](../../media/download-campaign-write-up-button.png) to download the campaign details to a Word document (by default, named CampaignReport.docx).</span></span> <span data-ttu-id="f308d-225">Observera att det här dokumentet innehåller information under kampanjens hela livstid (inte bara de filterdatum du har valt).</span><span class="sxs-lookup"><span data-stu-id="f308d-225">Note that this document contains details over the entire lifetime of the campaign (not just the filter dates you selected).</span></span>

![Kampanjinformation](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a><span data-ttu-id="f308d-227">Kampanjflöde</span><span class="sxs-lookup"><span data-stu-id="f308d-227">Campaign flow</span></span>

<span data-ttu-id="f308d-228">I mitten av vyn kampanjinformation presenteras viktiga detaljer om kampanjen i avsnittet **Flöde** i ett vågrätt flödesdiagram (ett så kallat _Sankey-diagram)._</span><span class="sxs-lookup"><span data-stu-id="f308d-228">In the middle of the campaign details view, important details about the campaign are presented in the **Flow** section in a horizontal flow diagram (known as a _Sankey_ diagram).</span></span> <span data-ttu-id="f308d-229">Dessa uppgifter hjälper dig att förstå delarna av kampanjen och den potentiella effekten i din organisation.</span><span class="sxs-lookup"><span data-stu-id="f308d-229">These details will help you to understand the elements of the campaign and the potential impact in your organization.</span></span>

> [!TIP]
> <span data-ttu-id="f308d-230">Informationen som visas i **flödesdiagrammet** styrs av det skuggade datumintervallet i tidslinjen enligt beskrivningen i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="f308d-230">The information that's displayed in the **Flow** diagram is controlled by the shaded date range in the timeline as described in the previous section.</span></span>

![Kampanjinformation som inte innehåller klick på användarens WEBBADRESS](../../media/campaign-details-no-recipient-actions.png)

<span data-ttu-id="f308d-232">Om du hovrar över ett vågrätt band i diagrammet visas antalet relaterade meddelanden (till exempel meddelanden från en viss käll-IP, meddelanden från käll-IP med den angivna avsändarendomänen osv.).</span><span class="sxs-lookup"><span data-stu-id="f308d-232">If you hover over a horizontal band in the diagram, you'll see the number of related messages (for example, messages from a particular source IP, messages from the source IP using the specified sender domain, etc.).</span></span>

<span data-ttu-id="f308d-233">Diagrammet innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="f308d-233">The diagram contains the following information:</span></span>

- <span data-ttu-id="f308d-234">**Avsändare-IPs**</span><span class="sxs-lookup"><span data-stu-id="f308d-234">**Sender IPs**</span></span>

- <span data-ttu-id="f308d-235">**Avsändaredomäner**</span><span class="sxs-lookup"><span data-stu-id="f308d-235">**Sender domains**</span></span>

- <span data-ttu-id="f308d-236">**Filtrera domar:** Dessa värden är relaterade till tillgängliga phishing och spam filtrering domar som beskrivs i [Anti-spam meddelande rubriker](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="f308d-236">**Filter verdicts**: These values are related to the available phishing and spam filtering verdicts as described in [Anti-spam message headers](anti-spam-message-headers.md).</span></span> <span data-ttu-id="f308d-237">De tillgängliga värdena beskrivs i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="f308d-237">The available values are described in the following table:</span></span>

  ||||
  |---|---|---|
  |<span data-ttu-id="f308d-238">**Värde**</span><span class="sxs-lookup"><span data-stu-id="f308d-238">**Value**</span></span>|<span data-ttu-id="f308d-239">**Spam filter dom**</span><span class="sxs-lookup"><span data-stu-id="f308d-239">**Spam filter verdict**</span></span>|<span data-ttu-id="f308d-240">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="f308d-240">**Description**</span></span>|
  |<span data-ttu-id="f308d-241">**Tillåtet**</span><span class="sxs-lookup"><span data-stu-id="f308d-241">**Allowed**</span></span>|`SFV:SKN` <br/><br/> `SFV:SKI`|<span data-ttu-id="f308d-242">Meddelandet markerades som inte skräppost och/eller överhoppade filtrering innan det utvärderades av skräppostfiltrering (till exempel av en regel för e-postflöde, även känd som en transportregel).</span><span class="sxs-lookup"><span data-stu-id="f308d-242">The message was marked as not spam and/or skipped filtering before being evaluated by spam filtering (for example, by a mail flow rule, also known as a transport rule).</span></span><br/><br/><span data-ttu-id="f308d-243">Meddelandet hoppade över skräppostfiltrering av andra skäl (till exempel verkar avsändaren och mottagaren vara i samma organisation).</span><span class="sxs-lookup"><span data-stu-id="f308d-243">The message skipped spam filtering for other reasons (for example, the sender and recipient appear to be in the same organization).</span></span>|
  |<span data-ttu-id="f308d-244">**Blockerade**</span><span class="sxs-lookup"><span data-stu-id="f308d-244">**Blocked**</span></span>|`SFV:SKS`|<span data-ttu-id="f308d-245">Meddelandet markerades som skräppost innan det utvärderades av skräppostfiltrering (till exempel av en regel för e-postflöde).</span><span class="sxs-lookup"><span data-stu-id="f308d-245">The message was marked as spam before being evaluated by spam filtering (for example, by a mail flow rule).</span></span>|
  |<span data-ttu-id="f308d-246">**Upptäckt**</span><span class="sxs-lookup"><span data-stu-id="f308d-246">**Detected**</span></span>|`SFV:SPM`|<span data-ttu-id="f308d-247">Meddelandet markerades som skräppost av skräppostfiltret.</span><span class="sxs-lookup"><span data-stu-id="f308d-247">The message was marked as spam by spam filtering.</span></span>|
  |<span data-ttu-id="f308d-248">**Har inte identifierats**</span><span class="sxs-lookup"><span data-stu-id="f308d-248">**Not Detected**</span></span>|`SFV:NSPM`|<span data-ttu-id="f308d-249">Meddelandet markerades som inte skräppost genom skräppostfiltrering.</span><span class="sxs-lookup"><span data-stu-id="f308d-249">The message was marked as not spam by spam filtering.</span></span>|
  |<span data-ttu-id="f308d-250">**Släppt**</span><span class="sxs-lookup"><span data-stu-id="f308d-250">**Released**</span></span>|`SFV:SKQ`|<span data-ttu-id="f308d-251">Meddelandet hoppade över skräppostfiltrering eftersom det släpptes från karantänen.</span><span class="sxs-lookup"><span data-stu-id="f308d-251">The message skipped spam filtering because it was released from quarantine.</span></span>|
  |<span data-ttu-id="f308d-252">**Klient tillåt**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f308d-252">**Tenant Allow**<sup>\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="f308d-253">Meddelandet hoppade över skräppostfiltrering på grund av policyinställningar mot skräppost (till exempel var avsändaren med i listan över tillåtna avsändare eller tillåtna domänlistan).</span><span class="sxs-lookup"><span data-stu-id="f308d-253">The message skipped spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="f308d-254">**Hyresgästblock**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="f308d-254">**Tenant Block**<sup>\*\*</sup></span></span>|`SFV:SKA`|<span data-ttu-id="f308d-255">Meddelandet blockerades av skräppostfiltrering på grund av policyinställningar mot skräppost (till exempel var avsändaren i listan över tillåtna avsändare eller tillåtna domänlistan).</span><span class="sxs-lookup"><span data-stu-id="f308d-255">The message was blocked by spam filtering due to anti-spam policy settings (for example, the sender was in the allowed sender list or allowed domain list).</span></span>|
  |<span data-ttu-id="f308d-256">**Tillåt användare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f308d-256">**User Allow**<sup>\*</sup></span></span>|`SFV:SFE`|<span data-ttu-id="f308d-257">Meddelandet hoppade över skräppostfiltrering eftersom avsändaren fanns i en användares lista över betrodda avsändare i Outlook.</span><span class="sxs-lookup"><span data-stu-id="f308d-257">The message skipped spam filtering because the sender was in a user's Safe Senders list in Outlook.</span></span>|
  |<span data-ttu-id="f308d-258">**Användarblock**<sup>\*\*</sup></span><span class="sxs-lookup"><span data-stu-id="f308d-258">**User Block**<sup>\*\*</sup></span></span>|`SFV:BLK`|<span data-ttu-id="f308d-259">Meddelandet blockerades av skräppostfiltrering eftersom avsändaren fanns i en användares lista blockerade avsändare i Outlook.</span><span class="sxs-lookup"><span data-stu-id="f308d-259">The message was blocked by spam filtering because the sender was in a user's Blocked Senders list in Outlook.</span></span>|
  |<span data-ttu-id="f308d-260">**Zap**</span><span class="sxs-lookup"><span data-stu-id="f308d-260">**ZAP**</span></span>|<span data-ttu-id="f308d-261">ej</span><span class="sxs-lookup"><span data-stu-id="f308d-261">n/a</span></span>|<span data-ttu-id="f308d-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) vidtog åtgärder på det levererade meddelandet enligt dina anti-spam-principinställningar (flyttade till mappen Skräppost eller karantän).</span><span class="sxs-lookup"><span data-stu-id="f308d-262">[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) took action on the delivered message according to your anti-spam policy settings (moved to the Junk Email folder or Quarantined).</span></span>|
  |

  <span data-ttu-id="f308d-263"><sup>\*</sup>Granska dina policyer mot skräppost, eftersom det tillåtna meddelandet sannolikt skulle ha blockerats av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f308d-263"><sup>\*</sup> Review your anti-spam policies, because the allowed message would have likely been blocked by the service.</span></span>

  <span data-ttu-id="f308d-264"><sup>\*\*</sup>Granska dina policyer mot skräppost, eftersom dessa meddelanden ska sättas i karantän, inte levereras.</span><span class="sxs-lookup"><span data-stu-id="f308d-264"><sup>\*\*</sup> Review your anti-spam policies, because these messages should be quarantined, not delivered.</span></span>

- <span data-ttu-id="f308d-265">**Leveransplatser**: Du vill förmodligen undersöka meddelanden som faktiskt levererades till mottagarna (antingen till inkorgen eller mappen Skräppost), även om användarna inte klickade på nyttolast-URL:en i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="f308d-265">**Delivery locations**: You'll likely want to investigate messages that were actually delivered to recipients (either to the Inbox or the Junk Email folder), even if users didn't click on the payload URL in the message.</span></span> <span data-ttu-id="f308d-266">Du kan också ta bort meddelandena i karantän från karantänen.</span><span class="sxs-lookup"><span data-stu-id="f308d-266">You can also remove the quarantined messages from quarantine.</span></span> <span data-ttu-id="f308d-267">Mer information finns [i EOP i karantän](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="f308d-267">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

  - <span data-ttu-id="f308d-268">**Borttagen mapp**</span><span class="sxs-lookup"><span data-stu-id="f308d-268">**Deleted folder**</span></span>
  - <span data-ttu-id="f308d-269">**Tappade**</span><span class="sxs-lookup"><span data-stu-id="f308d-269">**Dropped**</span></span>
  - <span data-ttu-id="f308d-270">**Externt**: Mottagaren finns i din lokala e-postorganisation i hybridmiljöer.</span><span class="sxs-lookup"><span data-stu-id="f308d-270">**External**: The recipient is located in your on-premises email organization in hybrid environments.</span></span>
  - <span data-ttu-id="f308d-271">**Misslyckades**</span><span class="sxs-lookup"><span data-stu-id="f308d-271">**Failed**</span></span>
  - <span data-ttu-id="f308d-272">**Vidarebefordras**</span><span class="sxs-lookup"><span data-stu-id="f308d-272">**Forwarded**</span></span>
  - <span data-ttu-id="f308d-273">**Inkorg**</span><span class="sxs-lookup"><span data-stu-id="f308d-273">**Inbox**</span></span>
  - <span data-ttu-id="f308d-274">**Skräppostmapp**</span><span class="sxs-lookup"><span data-stu-id="f308d-274">**Junk folder**</span></span>
  - <span data-ttu-id="f308d-275">**Karantän**</span><span class="sxs-lookup"><span data-stu-id="f308d-275">**Quarantine**</span></span>
  - <span data-ttu-id="f308d-276">**Okänd**</span><span class="sxs-lookup"><span data-stu-id="f308d-276">**Unknown**</span></span>

- <span data-ttu-id="f308d-277">**URL-klick**: Dessa beskrivs i nästa avsnitt.</span><span class="sxs-lookup"><span data-stu-id="f308d-277">**URL clicks**: These are described in the next section.</span></span>

> [!NOTE]
> <span data-ttu-id="f308d-278">I alla lager som innehåller fler än 10 objekt visas de 10 översta objekten, medan resten buntas ihop i **Andra**.</span><span class="sxs-lookup"><span data-stu-id="f308d-278">In all layers that contain more than 10 items, the top 10 items are shown, while the rest are bundled together in **Others**.</span></span>

#### <a name="url-clicks"></a><span data-ttu-id="f308d-279">URL-klick</span><span class="sxs-lookup"><span data-stu-id="f308d-279">URL clicks</span></span>

<span data-ttu-id="f308d-280">När ett nätfiskemeddelande levereras till en mottagare (till inkorgen eller mappen Skräppost) finns det alltid en chans att användaren klickar på nyttolastadressen.</span><span class="sxs-lookup"><span data-stu-id="f308d-280">When a phishing message is delivered to a recipient (to the Inbox or the Junk Email folder), there's always a chance that the user will click on the payload URL.</span></span> <span data-ttu-id="f308d-281">Att inte klicka på webbadressen i ett levererat meddelande är ett litet mått på framgång, men du måste ta reda på varför nätfiskemeddelandet levererades till deras postlåda från början.</span><span class="sxs-lookup"><span data-stu-id="f308d-281">Not clicking on the URL in a delivered message is a small measure of success, but you need to determine why the phishing message was delivered to their mailbox in the first place.</span></span>

<span data-ttu-id="f308d-282">Om en användare klickade på nyttolast-URL:en i nätfiskemeddelandet visas åtgärderna i området **URL-klick** i diagrammet i kampanjinformationsvyn.</span><span class="sxs-lookup"><span data-stu-id="f308d-282">If a user clicked on the payload URL in the phishing message, the actions are displayed in the **URL clicks** area of the diagram in the campaign details view.</span></span>

- <span data-ttu-id="f308d-283">**Tillåtet**</span><span class="sxs-lookup"><span data-stu-id="f308d-283">**Allowed**</span></span>

- <span data-ttu-id="f308d-284">**BlockPage**: Mottagaren klickade på nyttolastens URL, men deras åtkomst till den skadliga webbplatsen blockerades av [ATP Safe Links-principerna](atp-safe-links.md) i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f308d-284">**BlockPage**: The recipient clicked on the payload URL, but their access to the malicious website was blocked by the [ATP Safe Links](atp-safe-links.md) policies in your organization.</span></span>

- <span data-ttu-id="f308d-285">**BlockPageOverride**: Mottagaren klickade på nyttolastens URL i meddelandet, ATP Safe Links försökte stoppa dem, men de fick åsidosätta blocket.</span><span class="sxs-lookup"><span data-stu-id="f308d-285">**BlockPageOverride**: The recipient clicked on the payload URL in the message, ATP Safe Links tried to stop them, but they were allowed to override the block.</span></span> <span data-ttu-id="f308d-286">Du måste undersöka dina principer för [säkra länkar](set-up-atp-safe-links-policies.md) för att se varför användare tillåts åsidosätta domen om säkra länkar och fortsätta till den skadliga webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="f308d-286">You need to investigate your [Safe Links policies](set-up-atp-safe-links-policies.md) to see why users are allowed to override the Safe Links verdict and continue to the malicious website.</span></span>

- <span data-ttu-id="f308d-287">**PendingDetonationPage**: ATP Säkra bilagor håller på att öppna nyttolast-URL:en i en virtuell datormiljö och se vad som händer.</span><span class="sxs-lookup"><span data-stu-id="f308d-287">**PendingDetonationPage**: ATP Safe Attachments is in the process of opening the payload URL in a virtual computer environment, and seeing what happens.</span></span>

- <span data-ttu-id="f308d-288">**PendingDetonationPageOverride**: Mottagaren tilläts åsidosätta detonationsprocessen för nyttolasten och öppna URL:en utan att vänta på resultatet.</span><span class="sxs-lookup"><span data-stu-id="f308d-288">**PendingDetonationPageOverride**: The recipient was allowed to override the payload detonation process and open the URL without waiting for the results.</span></span>

### <a name="tabs"></a><span data-ttu-id="f308d-289">Flikar</span><span class="sxs-lookup"><span data-stu-id="f308d-289">Tabs</span></span>

<span data-ttu-id="f308d-290">Med flikarna i vyn kampanjinformation kan du undersöka kampanjen ytterligare.</span><span class="sxs-lookup"><span data-stu-id="f308d-290">The tabs in the campaign details view allow you to further investigate the campaign.</span></span>

> [!TIP]
> <span data-ttu-id="f308d-291">Informationen som visas på flikarna styrs av det skuggade datumintervallet i tidslinjen enligt beskrivningen i avsnittet [Kampanjinformation.](#campaign-information)</span><span class="sxs-lookup"><span data-stu-id="f308d-291">The information that's displayed on the tabs is controlled by the shaded date range in the timeline as described in [Campaign information](#campaign-information) section.</span></span>

- <span data-ttu-id="f308d-292">**URL-klick**: Om användarna inte klickade på nyttolastadressen i nätfiskemeddelandet är det här avsnittet tomt.</span><span class="sxs-lookup"><span data-stu-id="f308d-292">**URL clicks**: If users didn't click on the payload URL in the phishing message, this section will be blank.</span></span> <span data-ttu-id="f308d-293">Om en användare kunde klicka på webbadressen fylls följande värden i:</span><span class="sxs-lookup"><span data-stu-id="f308d-293">If a user was able to click on the URL, the following values will be populated:</span></span>

  - <span data-ttu-id="f308d-294">**Användaren**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f308d-294">**User**<sup>\*</sup></span></span>
  - <span data-ttu-id="f308d-295">**Url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f308d-295">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="f308d-296">**Klicka på tid**</span><span class="sxs-lookup"><span data-stu-id="f308d-296">**Click time**</span></span>
  - <span data-ttu-id="f308d-297">**Klicka dom**</span><span class="sxs-lookup"><span data-stu-id="f308d-297">**Click verdict**</span></span>

- <span data-ttu-id="f308d-298">**Avsändare-IPs**</span><span class="sxs-lookup"><span data-stu-id="f308d-298">**Sender IPs**</span></span>

  - <span data-ttu-id="f308d-299">**IP-adress för avsändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f308d-299">**Sender IP**<sup>\*</sup></span></span>
  - <span data-ttu-id="f308d-300">**Totalt antal**</span><span class="sxs-lookup"><span data-stu-id="f308d-300">**Total count**</span></span>
  - <span data-ttu-id="f308d-301">**Inkorg**</span><span class="sxs-lookup"><span data-stu-id="f308d-301">**Inboxed**</span></span>
  - <span data-ttu-id="f308d-302">**Inte inkorg**</span><span class="sxs-lookup"><span data-stu-id="f308d-302">**Not Inboxed**</span></span>
  - <span data-ttu-id="f308d-303">**SPF passerade:** Avsändaren autentiserades av [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="f308d-303">**SPF passed**: The sender was authenticated by the [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="f308d-304">En avsändare som inte skickar SPF-validering anger att avsändaren inte autentiseras eller att meddelandet förfalskar en legitim avsändare.</span><span class="sxs-lookup"><span data-stu-id="f308d-304">A sender that does not pass SPF validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="f308d-305">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="f308d-305">**Senders**</span></span>

  - <span data-ttu-id="f308d-306">**Avsändare**: Det här är den faktiska avsändaradressen i kommandot SMTP MAIL FROM, vilket inte nödvändigtvis är den Från: e-postadress som användarna ser i sina e-postklienter.</span><span class="sxs-lookup"><span data-stu-id="f308d-306">**Sender**: This is the actual sender address in the SMTP MAIL FROM command, which is not necessarily the From: email address that users see in their email clients.</span></span>
  - <span data-ttu-id="f308d-307">**Totalt antal**</span><span class="sxs-lookup"><span data-stu-id="f308d-307">**Total count**</span></span>
  - <span data-ttu-id="f308d-308">**Inkorg**</span><span class="sxs-lookup"><span data-stu-id="f308d-308">**Inboxed**</span></span>
  - <span data-ttu-id="f308d-309">**Inte inkorg**</span><span class="sxs-lookup"><span data-stu-id="f308d-309">**Not Inboxed**</span></span>
  - <span data-ttu-id="f308d-310">**DKIM-skickaded:** Avsändaren autentiserades av [DKIM (Domain Keys Identified Mail).](support-for-validation-of-dkim-signed-messages.md)</span><span class="sxs-lookup"><span data-stu-id="f308d-310">**DKIM passed**: The sender was authenticated by [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md).</span></span> <span data-ttu-id="f308d-311">En avsändare som inte klarar DKIM-validering anger att avsändaren inte autentiseras eller att meddelandet förfalskar en legitim avsändare.</span><span class="sxs-lookup"><span data-stu-id="f308d-311">A sender that does not pass DKIM validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>
  - <span data-ttu-id="f308d-312">**DMARC-godkänd:** Avsändaren autentiserades av [Domänbaserad meddelandeautentisering, rapportering och konformance (DMARC)](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="f308d-312">**DMARC passed**: The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="f308d-313">En avsändare som inte klarar DMARC-validering anger att avsändaren inte autentiseras eller att meddelandet förfalskar en legitim avsändare.</span><span class="sxs-lookup"><span data-stu-id="f308d-313">A sender that does not pass DMARC validation indicates the sender isn't authenticated, or the message is spoofing a legitimate sender.</span></span>

- <span data-ttu-id="f308d-314">**Bilagor**</span><span class="sxs-lookup"><span data-stu-id="f308d-314">**Attachments**</span></span>

  - <span data-ttu-id="f308d-315">**Filnamn**</span><span class="sxs-lookup"><span data-stu-id="f308d-315">**Filename**</span></span>
  - <span data-ttu-id="f308d-316">**SHA256 (SHA256)**</span><span class="sxs-lookup"><span data-stu-id="f308d-316">**SHA256**</span></span>
  - <span data-ttu-id="f308d-317">**Malware familj**</span><span class="sxs-lookup"><span data-stu-id="f308d-317">**Malware family**</span></span>
  - <span data-ttu-id="f308d-318">**Totalt antal**</span><span class="sxs-lookup"><span data-stu-id="f308d-318">**Total count**</span></span>

- <span data-ttu-id="f308d-319">**Url**</span><span class="sxs-lookup"><span data-stu-id="f308d-319">**URL**</span></span>

  - <span data-ttu-id="f308d-320">**Url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f308d-320">**URL**<sup>\*</sup></span></span>
  - <span data-ttu-id="f308d-321">**Totalt antal**</span><span class="sxs-lookup"><span data-stu-id="f308d-321">**Total Count**</span></span>

<span data-ttu-id="f308d-322"><sup>\*</sup>Om du klickar på det här värdet öppnas ett nytt utfällbart objekt som innehåller mer information om det angivna objektet (användare, URL osv.) ovanpå kampanjinformationsvyn.</span><span class="sxs-lookup"><span data-stu-id="f308d-322"><sup>\*</sup> Clicking on this value opens a new flyout that contains more details about the specified item (user, URL, etc.) on top of the campaign details view.</span></span> <span data-ttu-id="f308d-323">Om du vill återgå till kampanjinformationsvyn klickar du på **Klar** i det nya utfällbara resultatet.</span><span class="sxs-lookup"><span data-stu-id="f308d-323">To return to the campaign details view, click **Done** in the new flyout.</span></span>

### <a name="buttons"></a><span data-ttu-id="f308d-324">Knappar</span><span class="sxs-lookup"><span data-stu-id="f308d-324">Buttons</span></span>

<span data-ttu-id="f308d-325">Med knapparna i vyn kampanjinformation kan du använda kraften i Threat Explorer för att undersöka kampanjen ytterligare.</span><span class="sxs-lookup"><span data-stu-id="f308d-325">The buttons in the campaign details view allow you to use the power of Threat Explorer to further investigate the campaign.</span></span>

- <span data-ttu-id="f308d-326">**Utforska kampanj**: Öppnar en ny sökflik för Threat Explorer med värdet **Kampanj-ID** som sökfilter.</span><span class="sxs-lookup"><span data-stu-id="f308d-326">**Explore campaign**: Opens a new Threat Explorer search tab using the **Campaign ID** value as the search filter.</span></span>

- <span data-ttu-id="f308d-327">**Utforska inkorgsmeddelanden:** Öppnar en ny sökflik för Hot Explorer med **kampanj-ID** och **leveransplats: Inkorgen** som sökfilter.</span><span class="sxs-lookup"><span data-stu-id="f308d-327">**Explore Inboxed messages**: Opens a new Threat Explorer search tab using the **Campaign ID** and **Delivery location: Inbox** as the search filter.</span></span>
