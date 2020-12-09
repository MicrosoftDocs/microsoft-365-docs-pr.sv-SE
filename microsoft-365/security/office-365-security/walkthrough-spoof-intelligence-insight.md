---
title: Genom gång – Insight-inblick
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur inblicken med förfalsknings information fungerar. De kan snabbt avgöra vilka avsändare som skickar e-post till sina organisationer från domäner som inte klarar e-postauktorisering (SPF, DKIM eller DMARC).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9139a2b4c3c7ed8262f3d75b445defb869371d07
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602113"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="744d2-104">Genom gång-inblick i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="744d2-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="744d2-105">I Microsoft 365-organisationer med Defender för Office 365 kan du använda falsk IT-insyn för att snabbt avgöra vilka externa avsändare som skickar e-postautentisering på ett legitimt sätt.</span><span class="sxs-lookup"><span data-stu-id="744d2-105">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which external senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="744d2-106">Genom att tillåta kända externa avsändare att skicka falska meddelanden från kända platser kan du minska falska positiva (bra e-postmeddelanden).</span><span class="sxs-lookup"><span data-stu-id="744d2-106">By allowing known external senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="744d2-107">Genom att övervaka tillåtna avsändare tillhandahåller du ett ytterligare säkerhets skikt för att förhindra att osäkra meddelanden kommer in i organisationen.</span><span class="sxs-lookup"><span data-stu-id="744d2-107">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="744d2-108">Mer information om rapporter och insikter finns i [rapporter och insikter i avsnittet om säkerhets & efterlevnad](reports-and-insights-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="744d2-108">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="744d2-109">Den här genom gången är en av flera för säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="744d2-109">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="744d2-110">Information om hur du navigerar i rapporter och insikter finns i avsnittet [Närliggande information](#related-topics) .</span><span class="sxs-lookup"><span data-stu-id="744d2-110">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="744d2-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="744d2-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="744d2-112">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="744d2-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="744d2-113">För att gå direkt till sidan **säkerhets instrument panel** <https://protection.office.com/searchandinvestigation/dashboard> .</span><span class="sxs-lookup"><span data-stu-id="744d2-113">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="744d2-114">Du kan visa inblick från fler än en instrument panel i säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="744d2-114">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="744d2-115">Oavsett vilken instrument panel du tittar på, ger inblicken samma uppgifter och gör att du snabbt kan utföra samma uppgifter.</span><span class="sxs-lookup"><span data-stu-id="744d2-115">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="744d2-116">Du måste ha tilldelats behörigheter i Säkerhets- och efterlevnadscentret innan du kan genomföra procedurerna i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="744d2-116">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="744d2-117">**Organisationshantering**</span><span class="sxs-lookup"><span data-stu-id="744d2-117">**Organization Management**</span></span>
  - <span data-ttu-id="744d2-118">**Säkerhets administratör**</span><span class="sxs-lookup"><span data-stu-id="744d2-118">**Security Administrator**</span></span>
  - <span data-ttu-id="744d2-119">**Säkerhets läsare**</span><span class="sxs-lookup"><span data-stu-id="744d2-119">**Security Reader**</span></span>
  - <span data-ttu-id="744d2-120">**Global läsare**</span><span class="sxs-lookup"><span data-stu-id="744d2-120">**Global Reader**</span></span>

  <span data-ttu-id="744d2-121">**Obs!** när du lägger till användare i motsvarande Azure Active Directory-roll i Microsoft 365 Admin Center får användarna den behörighet som krävs för säkerhets & efterlevnad Center _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="744d2-121">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="744d2-122">Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="744d2-122">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="744d2-123">Du aktiverar och inaktiverar förfalsknings intelligens i policy mot nätfiske i Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="744d2-123">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="744d2-124">Förfalsknings intelligens är aktiverat som standard.</span><span class="sxs-lookup"><span data-stu-id="744d2-124">Spoof intelligence is enabled by default.</span></span> <span data-ttu-id="744d2-125">Mer information finns i [Konfigurera anti-nätfiske-principer i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="744d2-125">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="744d2-126">Information om hur du använder falsk intelligens för att övervaka och hantera avsändare som skickar dig overifierade meddelanden finns i [Konfigurera förfalsknings intelligens i Microsoft 365](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="744d2-126">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="744d2-127">Öppna inblicken för falsk identitet i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="744d2-127">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="744d2-128">Gå till instrument panelen **Threat Management** i säkerhets & efterlevnad \> **.**</span><span class="sxs-lookup"><span data-stu-id="744d2-128">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="744d2-129">Leta efter något av följande i raden **insikter** :</span><span class="sxs-lookup"><span data-stu-id="744d2-129">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="744d2-130">**Sannolika spoofade domäner under de senaste sju dagarna**: denna inblick visar att förfalsknings intelligens är aktiverat (det är aktiverat som standard).</span><span class="sxs-lookup"><span data-stu-id="744d2-130">**Likely spoofed domains over the past seven days**: This insight indicates that spoof intelligence is enabled (it's enabled by default).</span></span>
   - <span data-ttu-id="744d2-131">**Aktivera förfalsknings skydd**: denna inblick visar att förfalsknings intelligens är inaktiverat och att du kan aktivera förfalsknings intelligens genom att klicka på inblicken.</span><span class="sxs-lookup"><span data-stu-id="744d2-131">**Enable Spoof Protection**: This insight indicates that spoof intelligence is disabled, and clicking on the insight allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="744d2-132">Inblicken på instrument panelen visar information så här:</span><span class="sxs-lookup"><span data-stu-id="744d2-132">The insight on the dashboard shows you information like this:</span></span>

   ![Skärm bild av inblick i Spoof intelligens](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="744d2-134">Denna inblick har två lägen:</span><span class="sxs-lookup"><span data-stu-id="744d2-134">This insight has two modes:</span></span>

   - <span data-ttu-id="744d2-135">**Insight-läge**: om förfalsknings intelligens är aktiverat visar insikt dig hur många meddelanden som har påverkats av våra förfalsknings funktioner under de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="744d2-135">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past seven days.</span></span>
   - <span data-ttu-id="744d2-136">**Vad händer om-läge**: om förfalsknings intelligens är inaktiverat visar insikten dig hur *många meddelanden som* har påverkats av våra förfalsknings uppgifter under de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="744d2-136">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past seven days.</span></span>

   <span data-ttu-id="744d2-137">Oavsett vilket är de falska domänerna som visas i inblicken indelade i två kategorier: **misstänkta domäner** och **icke misstänkt domän**.</span><span class="sxs-lookup"><span data-stu-id="744d2-137">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domains** and **Non-suspicious domains**.</span></span>

   - <span data-ttu-id="744d2-138">**Misstänkta domäner** inkluderar:</span><span class="sxs-lookup"><span data-stu-id="744d2-138">**Suspicious domains** include:</span></span>

     - <span data-ttu-id="744d2-139">Falska användare med hög exakthet: baserat på de historiska sändnings-och ryktes poängen för domänerna, är det mycket säkert att domänerna är falska och att meddelanden från dessa domäner är mer troligt att de är skadliga.</span><span class="sxs-lookup"><span data-stu-id="744d2-139">High-confidence spoof: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

     - <span data-ttu-id="744d2-140">Falska säkerhets problem: baserat på historiska sändnings mönster och ryktes poängen för domänerna, är det ganska säkert att domänerna är falska och att meddelanden som skickas från dessa domäner är giltiga.</span><span class="sxs-lookup"><span data-stu-id="744d2-140">Moderate confidence spoof: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="744d2-141">Falsk positiv identitet är mer sannolik i den här kategorin än högkonfidens.</span><span class="sxs-lookup"><span data-stu-id="744d2-141">False positives are more likely in this category than high-confidence spoof.</span></span>

   <span data-ttu-id="744d2-142">**Icke misstänkt domän**: domänen kunde inte explicit e-postverifierare kontrol lera [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)och [DMARC](use-dmarc-to-validate-email.md)).</span><span class="sxs-lookup"><span data-stu-id="744d2-142">**Non-suspicious domains**: The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="744d2-143">Domänen godkände emellertid vår implicita kontroll för e-postverifikationer ([sammansatt verifikation](email-validation-and-authentication.md#composite-authentication)).</span><span class="sxs-lookup"><span data-stu-id="744d2-143">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="744d2-144">Därför har ingen åtgärd mot förfalskning gjorts för meddelandet.</span><span class="sxs-lookup"><span data-stu-id="744d2-144">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a><span data-ttu-id="744d2-145">Visa detaljerad information om misstänkta domäner från informationen om förfalsknings intelligens</span><span class="sxs-lookup"><span data-stu-id="744d2-145">View detailed information about suspicious domains from the Spoof intelligence insight</span></span>

1. <span data-ttu-id="744d2-146">Klicka på **misstänkta domäner** eller **icke misstänkt domän** för att gå till Insight-sidan för **falsk underrättelse** .</span><span class="sxs-lookup"><span data-stu-id="744d2-146">On the Spoof intelligence insight, click **Suspicious domains** or **Non-suspicious domains** to go to the **Spoof intelligence insight** page.</span></span> <span data-ttu-id="744d2-147">Informations sidan om **falska** uppgifter innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="744d2-147">The **Spoof Intelligence insight** page contains the following information:</span></span>

   - <span data-ttu-id="744d2-148">**Falsk domän**: domänen för den falska användare som visas i rutan **från** i e-postklienter.</span><span class="sxs-lookup"><span data-stu-id="744d2-148">**Spoofed domain**: The domain of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="744d2-149">Denna adress kallas också `5322.From` adress.</span><span class="sxs-lookup"><span data-stu-id="744d2-149">This address is also known as the `5322.From` address.</span></span>
   - <span data-ttu-id="744d2-150">**Infrastruktur**: kallas även för att _Skicka infrastrukturen_.</span><span class="sxs-lookup"><span data-stu-id="744d2-150">**Infrastructure**: Also known as the _sending infrastructure_.</span></span> <span data-ttu-id="744d2-151">Domänen hittades i en omvänd DNS-sökning (PTR-post) för käll-e-postserverns IP-adress.</span><span class="sxs-lookup"><span data-stu-id="744d2-151">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="744d2-152">Om käll-IP-adressen inte har någon PTR-post identifieras den sändande infrastrukturen som \<source IP\> /24 (till exempel 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="744d2-152">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>
   - <span data-ttu-id="744d2-153">**Antal** meddelanden: meddelande från infrastrukturen för att skicka till din organisation som innehåller den angivna domänen under de senaste 7 dagarna.</span><span class="sxs-lookup"><span data-stu-id="744d2-153">**Message count**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed domain within the last 7 days.</span></span>
   - <span data-ttu-id="744d2-154">**Senast sedd**: det sista datum då ett meddelande togs emot från den sändande infrastrukturen som innehåller den falska domänen.</span><span class="sxs-lookup"><span data-stu-id="744d2-154">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span></span>
   - <span data-ttu-id="744d2-155">**Falsk skrivning**: det här värdet är **externt**.</span><span class="sxs-lookup"><span data-stu-id="744d2-155">**Spoof type**: This value is **External**.</span></span>
   - <span data-ttu-id="744d2-156">Har du **tillstånd för falska identiteter?**: de värden som visas här är:</span><span class="sxs-lookup"><span data-stu-id="744d2-156">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="744d2-157">**Ja**: meddelanden från en kombination av falsk användares domän och överföring av infrastrukturen tillåts och behandlas inte som falsk e-post.</span><span class="sxs-lookup"><span data-stu-id="744d2-157">**Yes**: Messages from the combination of spoofed user's domain and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="744d2-158">**Nej**: meddelanden från en kombination av användarens domän och sändande infrastruktur markeras som falska.</span><span class="sxs-lookup"><span data-stu-id="744d2-158">**No**: Messages from the combination of spoofed user's domain and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="744d2-159">Åtgärden styrs av standard policyn för skydd mot nätfiske eller anpassade anti-phishing-principer (Standardvärdet är **Flytta meddelandet till mappen skräp post**).</span><span class="sxs-lookup"><span data-stu-id="744d2-159">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span>

     <span data-ttu-id="744d2-160">Mer information finns i [Konfigurera anti-nätfiske-principer i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="744d2-160">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

2. <span data-ttu-id="744d2-161">Välj ett objekt i listan om du vill visa information om den domän/sändande infrastruktur paret i en utfällbar metod.</span><span class="sxs-lookup"><span data-stu-id="744d2-161">Select an item in the list to view details about the domain/sending infrastructure pair in a flyout.</span></span> <span data-ttu-id="744d2-162">Informationen inkluderar:</span><span class="sxs-lookup"><span data-stu-id="744d2-162">The information includes:</span></span>
   - <span data-ttu-id="744d2-163">Varför vi fångade det här.</span><span class="sxs-lookup"><span data-stu-id="744d2-163">Why we caught this.</span></span>
   - <span data-ttu-id="744d2-164">Det här behöver du göra.</span><span class="sxs-lookup"><span data-stu-id="744d2-164">What you need to do.</span></span>
   - <span data-ttu-id="744d2-165">En domän Sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="744d2-165">A domain summary.</span></span>
   - <span data-ttu-id="744d2-166">WhoIs data om avsändaren.</span><span class="sxs-lookup"><span data-stu-id="744d2-166">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="744d2-167">Liknande meddelanden som vi har sett i klient organisationen från samma avsändare.</span><span class="sxs-lookup"><span data-stu-id="744d2-167">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="744d2-168">Härifrån kan du också välja att lägga till eller ta bort infrastrukturen för domän/skicka från listan Tillåt nekade **avsändare** .</span><span class="sxs-lookup"><span data-stu-id="744d2-168">From here, you can also choose to add or remove the domain/sending infrastructure pair from the **Allowed to spoof** sender allow list.</span></span> <span data-ttu-id="744d2-169">Ställ in växlings knappen på motsvarande sätt.</span><span class="sxs-lookup"><span data-stu-id="744d2-169">Simply set the toggle accordingly.</span></span>

   ![Skärm bild av en domän i informations fönstret för förfalsknings information](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a><span data-ttu-id="744d2-171">Lägga till en domän i listan över bevarade</span><span class="sxs-lookup"><span data-stu-id="744d2-171">Adding a domain to the Allowed to spoof list</span></span>

<span data-ttu-id="744d2-172">Genom att lägga till en domän i listan över tillåtna programlistor från all inblick med falsk intelligens kan bara en kombination av den falska domänen *och* den sändande infrastrukturen skickas.</span><span class="sxs-lookup"><span data-stu-id="744d2-172">Adding a domain to the Allowed to spoof list from the spoof intelligence insight only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="744d2-173">Den tillåter inte e-post från den nekade domänen från någon källa eller tillåter inte e-post från den sändande infrastrukturen för någon domän.</span><span class="sxs-lookup"><span data-stu-id="744d2-173">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="744d2-174">Du tillåter till exempel följande domän till listan med falska identiteter:</span><span class="sxs-lookup"><span data-stu-id="744d2-174">For example, you allow the following domain to the Allowed to spoof list:</span></span>

- <span data-ttu-id="744d2-175">**Domän**: Gmail.com</span><span class="sxs-lookup"><span data-stu-id="744d2-175">**Domain**: gmail.com</span></span>
- <span data-ttu-id="744d2-176">**Infrastruktur**: TMS.MX.com</span><span class="sxs-lookup"><span data-stu-id="744d2-176">**Infrastructure**: tms.mx.com</span></span>

<span data-ttu-id="744d2-177">Endast e-post från den domänen/sändande infrastruktur paret kommer att få åtkomst till förfalskningar.</span><span class="sxs-lookup"><span data-stu-id="744d2-177">Only email from that domain/sending infrastructure pair will be allowed to spoof.</span></span> <span data-ttu-id="744d2-178">Andra avsändare som försöker falska gmail.com är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="744d2-178">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="744d2-179">Meddelanden i andra domäner från tms.mx.com kontrol leras av förfalsknings intelligens.</span><span class="sxs-lookup"><span data-stu-id="744d2-179">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="744d2-180">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="744d2-180">Related topics</span></span>

[<span data-ttu-id="744d2-181">Skydd mot förfalskning i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="744d2-181">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)
