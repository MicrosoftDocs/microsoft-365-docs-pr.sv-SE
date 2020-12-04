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
ms.openlocfilehash: 6f5ebd0fd42d17354eeb1e03c946ac5446c3667c
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572747"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a><span data-ttu-id="e8e79-104">Genom gång-inblick i Microsoft Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="e8e79-104">Walkthrough - Spoof intelligence insight in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e8e79-105">I Microsoft 365-organisationer med Defender för Office 365 kan du använda falsk IT-insyn för att snabbt avgöra vilka avsändare som skickar e-postautentisering på ett legitimt sätt.</span><span class="sxs-lookup"><span data-stu-id="e8e79-105">In Microsoft 365 organizations with Defender for Office 365, you can use the Spoof intelligence insight to quickly determine which senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="e8e79-106">Genom att tillåta att kända avsändare skickar falska meddelanden från kända platser kan du minska falska positiva (god e-post som är markerad som dålig).</span><span class="sxs-lookup"><span data-stu-id="e8e79-106">By allowing known senders to send spoofed messages from known locations, you can reduce false positives (good email marked as bad).</span></span> <span data-ttu-id="e8e79-107">Genom att övervaka tillåtna avsändare tillhandahåller du ett ytterligare säkerhets skikt för att förhindra att osäkra meddelanden kommer in i organisationen.</span><span class="sxs-lookup"><span data-stu-id="e8e79-107">By monitoring the allowed spoofed senders, you provide an additional layer of security to prevent unsafe messages from arriving in your organization.</span></span>

<span data-ttu-id="e8e79-108">Mer information om rapporter och insikter finns i [rapporter och insikter i avsnittet om säkerhets & efterlevnad](reports-and-insights-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="e8e79-108">For more information about reports and insights, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

<span data-ttu-id="e8e79-109">Den här genom gången är en av flera för säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="e8e79-109">This walkthrough is one of several for the Security & Compliance Center.</span></span> <span data-ttu-id="e8e79-110">Information om hur du navigerar i rapporter och insikter finns i avsnittet [Närliggande information](#related-topics) .</span><span class="sxs-lookup"><span data-stu-id="e8e79-110">To about navigating reports and insights, see the walkthroughs in the [Related topics](#related-topics) section.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e8e79-111">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="e8e79-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e8e79-112">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="e8e79-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e8e79-113">För att gå direkt till sidan **säkerhets instrument panel** <https://protection.office.com/searchandinvestigation/dashboard> .</span><span class="sxs-lookup"><span data-stu-id="e8e79-113">To go directly to the **Security dashboard** page, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

  <span data-ttu-id="e8e79-114">Du kan visa inblick från fler än en instrument panel i säkerhets & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="e8e79-114">You can view the Spoof intelligence insight from more than one dashboard in the Security & Compliance Center.</span></span> <span data-ttu-id="e8e79-115">Oavsett vilken instrument panel du tittar på, ger inblicken samma uppgifter och gör att du snabbt kan utföra samma uppgifter.</span><span class="sxs-lookup"><span data-stu-id="e8e79-115">Regardless of which dashboard you're looking at, the insight provides the same details and allows you to quickly perform the same tasks.</span></span>

- <span data-ttu-id="e8e79-116">Du måste tilldelas behörigheter i säkerhets & Compliance Center innan du kan göra det i den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="e8e79-116">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e8e79-117">**Organisationshantering**</span><span class="sxs-lookup"><span data-stu-id="e8e79-117">**Organization Management**</span></span>
  - <span data-ttu-id="e8e79-118">**Säkerhets administratör**</span><span class="sxs-lookup"><span data-stu-id="e8e79-118">**Security Administrator**</span></span>
  - <span data-ttu-id="e8e79-119">**Säkerhets läsare**</span><span class="sxs-lookup"><span data-stu-id="e8e79-119">**Security Reader**</span></span>
  - <span data-ttu-id="e8e79-120">**Global läsare**</span><span class="sxs-lookup"><span data-stu-id="e8e79-120">**Global Reader**</span></span>

  <span data-ttu-id="e8e79-121">**Obs!** när du lägger till användare i motsvarande Azure Active Directory-roll i Microsoft 365 Admin Center får användarna den behörighet som krävs för säkerhets & efterlevnad Center _och_ behörigheter för andra funktioner i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e8e79-121">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e8e79-122">Mer information finns i [Om administratörsroller](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="e8e79-122">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="e8e79-123">Du aktiverar och inaktiverar förfalsknings intelligens i policy mot nätfiske i Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="e8e79-123">You enable and disable spoof intelligence in anti-phishing policies in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="e8e79-124">Mer information finns i [Konfigurera anti-nätfiske-principer i Microsoft Defender för Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e8e79-124">For more information, see [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="e8e79-125">Information om hur du använder falsk intelligens för att övervaka och hantera avsändare som skickar dig overifierade meddelanden finns i [Konfigurera förfalsknings intelligens i Microsoft 365](learn-about-spoof-intelligence.md).</span><span class="sxs-lookup"><span data-stu-id="e8e79-125">To use spoof intelligence to monitor and manage senders who are sending you unauthenticated messages, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a><span data-ttu-id="e8e79-126">Öppna inblicken för falsk identitet i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="e8e79-126">Open the spoof intelligence insight in the Security & Compliance Center</span></span>

1. <span data-ttu-id="e8e79-127">Gå till instrument panelen **Threat Management** i säkerhets & efterlevnad \> **.**</span><span class="sxs-lookup"><span data-stu-id="e8e79-127">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard.**</span></span>

2. <span data-ttu-id="e8e79-128">Leta efter något av följande i raden **insikter** :</span><span class="sxs-lookup"><span data-stu-id="e8e79-128">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="e8e79-129">**Förfalsknings intelligens är aktiverat**: inblicken heter **falska domäner som inte kunde verifieras av de senaste 30 dagarna**.</span><span class="sxs-lookup"><span data-stu-id="e8e79-129">**Spoof intelligence is enabled**: The insight is named **Spoofed domains that failed authentication of the past 30 days**.</span></span> <span data-ttu-id="e8e79-130">Det här är standardinställningen.</span><span class="sxs-lookup"><span data-stu-id="e8e79-130">This is the default.</span></span>
   - <span data-ttu-id="e8e79-131">**Förfalsknings intelligens är inaktiverat**: inblicken i namngivna **Aktivera förfalsknings skydd** och när du klickar på den kan du aktivera förfalsknings intelligens.</span><span class="sxs-lookup"><span data-stu-id="e8e79-131">**Spoof intelligence is disabled**: The insight in named **Enable Spoof Protection**, and clicking on it allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="e8e79-132">Inblicken på instrument panelen visar information så här:</span><span class="sxs-lookup"><span data-stu-id="e8e79-132">The insight on the dashboard shows you information like this:</span></span>

   ![Skärm bild av inblick i Spoof intelligens](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="e8e79-134">Denna inblick har två lägen:</span><span class="sxs-lookup"><span data-stu-id="e8e79-134">This insight has two modes:</span></span>

   - <span data-ttu-id="e8e79-135">**Insight-läge**: om förfalsknings intelligens är aktiverat visar insikt dig hur många meddelanden som har påverkats av våra förfalsknings funktioner under de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="e8e79-135">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   - <span data-ttu-id="e8e79-136">**Vad händer om-läge**: om förfalsknings intelligens är inaktiverat visar insikten dig hur *många meddelanden som* har påverkats av våra förfalsknings uppgifter under de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="e8e79-136">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past 30 days.</span></span>

   <span data-ttu-id="e8e79-137">Oavsett vilket är de falska domänerna som visas i inblicken indelade i två kategorier: **misstänkta domän par** och **icke misstänkt domän par**.</span><span class="sxs-lookup"><span data-stu-id="e8e79-137">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domain pairs** and **Non-suspicious domain pairs**.</span></span> <span data-ttu-id="e8e79-138">Dessa kategorier är indelade i tre olika buckets för att du ska kunna granska.</span><span class="sxs-lookup"><span data-stu-id="e8e79-138">These categories are further subdivided into three different buckets for you to review.</span></span>

   <span data-ttu-id="e8e79-139">Ett **domän par** är en kombination av från-adressen och den sändande infrastrukturen:</span><span class="sxs-lookup"><span data-stu-id="e8e79-139">A **domain pair** is a combination of the From address and the sending infrastructure:</span></span>

   - <span data-ttu-id="e8e79-140">Från-adressen är avsändarens e-postadress som visas i rutan från i e-postklienter.</span><span class="sxs-lookup"><span data-stu-id="e8e79-140">The From address is the sender's email address that's displayed in the From box in email clients.</span></span> <span data-ttu-id="e8e79-141">Denna adress kallas också `5322.From` adress.</span><span class="sxs-lookup"><span data-stu-id="e8e79-141">This address is also known as the `5322.From` address.</span></span>

   - <span data-ttu-id="e8e79-142">Den sändande infrastrukturen, eller avsändaren, är domän domänen för omvänd DNS-sökning (PTR-post) för den sändande IP-adressen.</span><span class="sxs-lookup"><span data-stu-id="e8e79-142">The sending infrastructure, or sender, is the organizational domain of the reverse DNS lookup (PTR record) of the sending IP address.</span></span> <span data-ttu-id="e8e79-143">Om den sändande IP-adressen inte har någon PTR-post identifieras avsändaren av den sändande undernätet med den 255.255.255.0 nät masken i CIDR-notation (/24).</span><span class="sxs-lookup"><span data-stu-id="e8e79-143">If the sending IP address has no PTR record, then the sender is identified by the sending IP with the 255.255.255.0 subnet mask in CIDR notation (/24).</span></span> <span data-ttu-id="e8e79-144">Om IP-adressen till exempel är 192.168.100.100 är avsändarens fullständiga IP-adress 192.168.100.100/24.</span><span class="sxs-lookup"><span data-stu-id="e8e79-144">For example, if the IP address is 192.168.100.100 then the complete IP address of the sender is 192.168.100.100/24.</span></span>

   <span data-ttu-id="e8e79-145">**Misstänkta domän par** är:</span><span class="sxs-lookup"><span data-stu-id="e8e79-145">**Suspicious domain pairs** include:</span></span>

   - <span data-ttu-id="e8e79-146">**Falska användare med hög exakthet**: baserat på de historiska sändnings-och ryktes poängen för domänerna, är det mycket säkert att domänerna är falska och att meddelanden från dessa domäner är mer troligt att de är skadliga.</span><span class="sxs-lookup"><span data-stu-id="e8e79-146">**High-confidence spoof**: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>

   - <span data-ttu-id="e8e79-147">**Falska säkerhets** problem: baserat på historiska sändnings mönster och ryktes poängen för domänerna, är det ganska säkert att domänerna är falska och att meddelanden som skickas från dessa domäner är giltiga.</span><span class="sxs-lookup"><span data-stu-id="e8e79-147">**Moderate confidence spoof**: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="e8e79-148">Falsk positiv identitet är mer sannolik i den här kategorin än högkonfidens.</span><span class="sxs-lookup"><span data-stu-id="e8e79-148">False positives are more likely in this category than high-confidence spoof.</span></span>

   - <span data-ttu-id="e8e79-149">**Icke misstänkt domän par** (inklusive **räddad förfalskning**): domänen misslyckades explicit kontroller för e-postauktorisering [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md)och [DMARC](use-dmarc-to-validate-email.md)).</span><span class="sxs-lookup"><span data-stu-id="e8e79-149">**Non-suspicious domain pairs** (includes **rescued spoof**): The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="e8e79-150">Domänen godkände emellertid vår implicita kontroll för e-postverifikationer ([sammansatt verifikation](email-validation-and-authentication.md#composite-authentication)).</span><span class="sxs-lookup"><span data-stu-id="e8e79-150">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="e8e79-151">Därför har ingen åtgärd mot förfalskning gjorts för meddelandet.</span><span class="sxs-lookup"><span data-stu-id="e8e79-151">As a result, no anti-spoofing action was taken on the message.</span></span>

### <a name="view-detailed-information-about-suspicious-domain-pairs-from-the-spoof-intelligence-insight"></a><span data-ttu-id="e8e79-152">Visa detaljerad information om misstänkta domän par från inblicken för falska uppgifter</span><span class="sxs-lookup"><span data-stu-id="e8e79-152">View detailed information about suspicious domain pairs from the spoof intelligence insight</span></span>

1. <span data-ttu-id="e8e79-153">Klicka på något av de här domän paren (High, måttlig eller räddat) i den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="e8e79-153">On the Spoof intelligence insight, click any of the domain pairs (high, moderate, or rescued).</span></span>

   <span data-ttu-id="e8e79-154">Sidan för att **Insight-information** visas.</span><span class="sxs-lookup"><span data-stu-id="e8e79-154">The **Spoof Intelligence insight** page appears.</span></span> <span data-ttu-id="e8e79-155">På sidan visas en lista med avsändare som skickar overifierad e-post till din organisation.</span><span class="sxs-lookup"><span data-stu-id="e8e79-155">The page shows you a list of senders who are sending unauthenticated email into your organization.</span></span>

   <span data-ttu-id="e8e79-156">Med den här informationen kan du avgöra om falska meddelanden är godkända eller om du behöver vidta ytterligare åtgärder.</span><span class="sxs-lookup"><span data-stu-id="e8e79-156">This information helps you determine whether spoofed messages are authorized, or if you need to take further action.</span></span>

   <span data-ttu-id="e8e79-157">Du kan sortera informationen efter antal meddelanden, det datum då datafilen senast upptäcktes och mer.</span><span class="sxs-lookup"><span data-stu-id="e8e79-157">You can sort the information by message count, the date the spoof was last detected, and more.</span></span>

2. <span data-ttu-id="e8e79-158">Välj ett objekt i tabellen för att öppna en informations ruta som innehåller information om domän paret.</span><span class="sxs-lookup"><span data-stu-id="e8e79-158">Select an item in the table to open a details pane that contains rich information about the domain pair.</span></span> <span data-ttu-id="e8e79-159">Informationen inkluderar:</span><span class="sxs-lookup"><span data-stu-id="e8e79-159">The information includes:</span></span>
   - <span data-ttu-id="e8e79-160">Varför vi fångade det här.</span><span class="sxs-lookup"><span data-stu-id="e8e79-160">Why we caught this.</span></span>
   - <span data-ttu-id="e8e79-161">Det här behöver du göra.</span><span class="sxs-lookup"><span data-stu-id="e8e79-161">What you need to do.</span></span>
   - <span data-ttu-id="e8e79-162">En domän Sammanfattning.</span><span class="sxs-lookup"><span data-stu-id="e8e79-162">A domain summary.</span></span>
   - <span data-ttu-id="e8e79-163">WhoIs data om avsändaren.</span><span class="sxs-lookup"><span data-stu-id="e8e79-163">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="e8e79-164">Liknande meddelanden som vi har sett i klient organisationen från samma avsändare.</span><span class="sxs-lookup"><span data-stu-id="e8e79-164">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="e8e79-165">Härifrån kan du också välja att lägga till eller ta bort domän paret från **AllowedToSpoof** Safe delistion.</span><span class="sxs-lookup"><span data-stu-id="e8e79-165">From here, you can also choose to add or remove the domain pair from the **AllowedToSpoof** safe sender list.</span></span>

   ![Skärm bild av en domän i informations fönstret för förfalsknings information](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="add-or-remove-a-domain-from-the-allowedtospoof-list"></a><span data-ttu-id="e8e79-167">Lägga till eller ta bort en domän från AllowedToSpoof-listan</span><span class="sxs-lookup"><span data-stu-id="e8e79-167">Add or remove a domain from the AllowedToSpoof list</span></span>

<span data-ttu-id="e8e79-168">Du lägger till eller tar bort en domän från listan AllowedToSpoof (Safe-avsändare) i informations fönstret i den falska informationen om ett domän par.</span><span class="sxs-lookup"><span data-stu-id="e8e79-168">You add or remove a domain from the AllowedToSpoof (safe sender) list in the details pane of the spoof intelligence insight for the domain pair.</span></span> <span data-ttu-id="e8e79-169">Ställ in växlings knappen på motsvarande sätt.</span><span class="sxs-lookup"><span data-stu-id="e8e79-169">Simply set the toggle accordingly.</span></span>

<span data-ttu-id="e8e79-170">Om du bara tillåter ett domän par kan kombinationen av den nekade domänen *och* den sändande infrastrukturen.</span><span class="sxs-lookup"><span data-stu-id="e8e79-170">Allowing a domain pair only allows the combination of the spoofed domain *and* the sending infrastructure.</span></span> <span data-ttu-id="e8e79-171">Den tillåter inte e-post från den nekade domänen från någon källa eller tillåter inte e-post från den sändande infrastrukturen för någon domän.</span><span class="sxs-lookup"><span data-stu-id="e8e79-171">It does not allow email from the spoofed domain from any source, nor does it allow email from the sending infrastructure for any domain.</span></span>

<span data-ttu-id="e8e79-172">Du tillåter till exempel följande domän par för att skicka falska meddelanden till din organisation:</span><span class="sxs-lookup"><span data-stu-id="e8e79-172">For example, you allow the following domain pair to send spoofed messages into your organization:</span></span>

- <span data-ttu-id="e8e79-173">*Falsk domän*: Gmail.com "</span><span class="sxs-lookup"><span data-stu-id="e8e79-173">*Spoofed Domain*: gmail.com"</span></span>
- <span data-ttu-id="e8e79-174">*Skickar infrastruktur* `tms.mx.com` :</span><span class="sxs-lookup"><span data-stu-id="e8e79-174">*Sending Infrastructure* `tms.mx.com`:</span></span>

<span data-ttu-id="e8e79-175">Endast e-post från det domän paret kommer att tillåtas för falska identiteter.</span><span class="sxs-lookup"><span data-stu-id="e8e79-175">Only email from that domain pair will be allowed to spoof.</span></span> <span data-ttu-id="e8e79-176">Andra avsändare som försöker falska gmail.com är inte tillåtna.</span><span class="sxs-lookup"><span data-stu-id="e8e79-176">Other senders attempting to spoof gmail.com aren't allowed.</span></span> <span data-ttu-id="e8e79-177">Meddelanden i andra domäner från tms.mx.com kontrol leras av förfalsknings intelligens.</span><span class="sxs-lookup"><span data-stu-id="e8e79-177">Messages in other domains from tms.mx.com are checked by spoof intelligence.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e8e79-178">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="e8e79-178">Related topics</span></span>

[<span data-ttu-id="e8e79-179">Skydd mot förfalskning i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e8e79-179">Anti-spoofing protection in Microsoft 365</span></span>](anti-spoofing-protection.md)
