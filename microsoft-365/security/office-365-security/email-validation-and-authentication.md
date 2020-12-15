---
title: E-postautentisering i Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Administratörer kan lära sig hur EOP använder e-autentisering (SPF, DKIM och DMARC) för att förhindra förfalskning, phishing och skräppost.
ms.openlocfilehash: 7c196b68d88187da2890cc886f646c5416ef9a11
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131079"
---
# <a name="email-authentication-in-eop"></a><span data-ttu-id="df2db-103">E-postautentisering i EOP</span><span class="sxs-lookup"><span data-stu-id="df2db-103">Email authentication in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="df2db-104">E-postautentisering (kallas även för e-postverifiering) är en grupp standarder som försöker sluta förfalskning (e-postmeddelanden från falska avsändare).</span><span class="sxs-lookup"><span data-stu-id="df2db-104">Email authentication (also known as email validation) is a group of standards that tries to stop spoofing (email messages from forged senders).</span></span> <span data-ttu-id="df2db-105">I alla Microsoft 365-organisationer använder EOP dessa standarder för att verifiera inkommande e-post:</span><span class="sxs-lookup"><span data-stu-id="df2db-105">In all Microsoft 365 organizations, EOP uses these standards to verify inbound email:</span></span>

- [<span data-ttu-id="df2db-106">SPF</span><span class="sxs-lookup"><span data-stu-id="df2db-106">SPF</span></span>](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

- [<span data-ttu-id="df2db-107">DKIM</span><span class="sxs-lookup"><span data-stu-id="df2db-107">DKIM</span></span>](use-dkim-to-validate-outbound-email.md)

- [<span data-ttu-id="df2db-108">DMARC</span><span class="sxs-lookup"><span data-stu-id="df2db-108">DMARC</span></span>](use-dmarc-to-validate-email.md)

<span data-ttu-id="df2db-109">E-postautentisering verifierar att e-postmeddelanden från en avsändare (till exempel laura@contoso.com) är giltiga och kommer från förväntade källor för den e-postdomänen (till exempel contoso.com.)</span><span class="sxs-lookup"><span data-stu-id="df2db-109">Email authentication verifies that email messages from a sender (for example, laura@contoso.com) are legitimate and come from expected sources for that email domain (for example, contoso.com.)</span></span>

<span data-ttu-id="df2db-110">Resten av den här artikeln förklarar hur dessa tekniker fungerar och hur EOP använder dem för att kontrollera inkommande e-post.</span><span class="sxs-lookup"><span data-stu-id="df2db-110">The rest of this article explains how these technologies work, and how EOP uses them to check inbound email.</span></span>

## <a name="use-email-authentication-to-help-prevent-spoofing"></a><span data-ttu-id="df2db-111">Använda e-postautentisering för att förhindra förfalskning</span><span class="sxs-lookup"><span data-stu-id="df2db-111">Use email authentication to help prevent spoofing</span></span>

<span data-ttu-id="df2db-112">DMARC förhindrar förfalskning genom att granska **från** adress i meddelanden.</span><span class="sxs-lookup"><span data-stu-id="df2db-112">DMARC prevents spoofing by examining the **From** address in messages.</span></span> <span data-ttu-id="df2db-113">**Från** Adress är avsändarens e-postadress som användarna ser i sina e-postklienter.</span><span class="sxs-lookup"><span data-stu-id="df2db-113">The **From** address is the sender's email address that users see in their email client.</span></span> <span data-ttu-id="df2db-114">Destinationens e-postorganisationer kan också verifiera att e-postdomänen har passerat SPF eller DKIM.</span><span class="sxs-lookup"><span data-stu-id="df2db-114">Destination email organizations can also verify that the email domain has passed SPF or DKIM.</span></span> <span data-ttu-id="df2db-115">Med andra ord har domänen verifierats och därför skickas inte avsändarens e-postadress.</span><span class="sxs-lookup"><span data-stu-id="df2db-115">In other words, the domain has been authenticated and therefore the sender's email address is not spoofed.</span></span>

<span data-ttu-id="df2db-116">DNS-poster för SPF, DKIM och DMARC (gemensamt känd som e-autentiseringspolicy) är valfria.</span><span class="sxs-lookup"><span data-stu-id="df2db-116">However, DNS records for SPF, DKIM, and DMARC (collectively known as email authentication policies) are optional.</span></span> <span data-ttu-id="df2db-117">Domäner med starka e-autentiseringsprinciper som microsoft.com och skype.com är skyddade mot falskt fel.</span><span class="sxs-lookup"><span data-stu-id="df2db-117">Domains with strong email authentication policies like microsoft.com and skype.com are protected from spoofing.</span></span> <span data-ttu-id="df2db-118">Men domäner med svagare e-autentiseringspolicy, eller ingen politik alls, är främsta mål för att bli förfalskade.</span><span class="sxs-lookup"><span data-stu-id="df2db-118">But domains with weaker email authentication policies, or no policy at all, are prime targets for being spoofed.</span></span>

<span data-ttu-id="df2db-119">Till och med mars 2018 har endast 9 % av företag på Fortune 500-listan publicerat starka principer för e-postautentisering.</span><span class="sxs-lookup"><span data-stu-id="df2db-119">As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies.</span></span> <span data-ttu-id="df2db-120">De återstående 91% av företagen kan bli förfalskade av en angripare.</span><span class="sxs-lookup"><span data-stu-id="df2db-120">The remaining 91% of companies might be spoofed by an attacker.</span></span> <span data-ttu-id="df2db-121">Om du inte har en annan funktion för e-postfiltrering på plats kan e-post från falska avsändare i dessa domäner levereras till användare.</span><span class="sxs-lookup"><span data-stu-id="df2db-121">Unless some other email filtering mechanism is in-place, email from spoofed senders in these domains might be delivered to users.</span></span>

![DMARC-principer för Fortune 500-företag](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

<span data-ttu-id="df2db-123">Andelen små till medelstora företag som publicerar starka e-autentiseringsprinciper är mindre.</span><span class="sxs-lookup"><span data-stu-id="df2db-123">The proportion of small-to-medium sized companies that publish strong email authentication policies is smaller.</span></span> <span data-ttu-id="df2db-124">Och antalet är ännu mindre för e-postdomäner utanför Nordamerika och Västeuropa.</span><span class="sxs-lookup"><span data-stu-id="df2db-124">And the number is even smaller for email domains outside North America and western Europe.</span></span>

<span data-ttu-id="df2db-125">Brist på starka e-autentiseringsprinciper är ett stort problem.</span><span class="sxs-lookup"><span data-stu-id="df2db-125">Lack of strong email authentication policies is a large problem.</span></span> <span data-ttu-id="df2db-126">Medan organisationer kanske inte förstår hur e-autentisering fungerar, förstår angriparna fullt ut och de drar fördel.</span><span class="sxs-lookup"><span data-stu-id="df2db-126">W while organizations might not understand how email authentication works, attackers fully understand, and they take advantage.</span></span> <span data-ttu-id="df2db-127">På grund av phishing-problem och det begränsade införandet av principer för stark e-postautentisering använder Microsoft *implicit e-postautentisering* för att kontrollera inkommande e-post.</span><span class="sxs-lookup"><span data-stu-id="df2db-127">Because of phishing concerns and the limited adoption of strong email authentication policies, Microsoft uses *implicit email authentication* to check inbound email.</span></span>

<span data-ttu-id="df2db-128">Implicit e-autentisering är en förlängning av vanliga policyer för e-autentisering.</span><span class="sxs-lookup"><span data-stu-id="df2db-128">Implicit email authentication is an extension of regular email authentication policies.</span></span> <span data-ttu-id="df2db-129">Dessa tillägg inkluderar avsändarens rykte, avsändarhistorik, mottagarhistorik, beteendeanalys och annan avancerad teknik.</span><span class="sxs-lookup"><span data-stu-id="df2db-129">These extensions include: sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques.</span></span> <span data-ttu-id="df2db-130">I avsaknad av andra signaler från dessa tillägg markeras meddelanden som skickas från domäner som inte använder e-autentiseringspolicyer som falsk.</span><span class="sxs-lookup"><span data-stu-id="df2db-130">In the absence of other signals from these extensions, messages sent from domains that don't use email authentication policies will be marked as spoof.</span></span>

<span data-ttu-id="df2db-131">Du kan läsa Microsofts allmänna meddelande i [Ett hav av nätfiskare, del 2 – förbättrat skydd mot förfalskning i Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span><span class="sxs-lookup"><span data-stu-id="df2db-131">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>

## <a name="composite-authentication"></a><span data-ttu-id="df2db-132">Sammansatt autentisering</span><span class="sxs-lookup"><span data-stu-id="df2db-132">Composite authentication</span></span>

<span data-ttu-id="df2db-133">Om det inte finns traditionella SPF-, DKIM-och DMARC-poster i en domän, överförs inte tillräcklig information om autentiserings status vid de post kontrollerna.</span><span class="sxs-lookup"><span data-stu-id="df2db-133">If a domain doesn't have traditional SPF, DKIM, and DMARC records, those record checks don't communicate enough authentication status information.</span></span> <span data-ttu-id="df2db-134">Därför har Microsoft utvecklat en algoritm för implicit e-autentisering.</span><span class="sxs-lookup"><span data-stu-id="df2db-134">Therefore, Microsoft has developed an algorithm for implicit email authentication.</span></span> <span data-ttu-id="df2db-135">Med den här algoritmen kombineras flera signaler till ett enda värde som kallas _oseparerad autentisering_ eller `compauth` för kort.</span><span class="sxs-lookup"><span data-stu-id="df2db-135">This algorithm combines multiple signals into a single value called _composite authentication_, or `compauth` for short.</span></span> <span data-ttu-id="df2db-136">`compauth` värdet stämplas i **verifierings resultat** rubriken i meddelande rubrikerna.</span><span class="sxs-lookup"><span data-stu-id="df2db-136">The `compauth` value is stamped into the **Authentication-Results** header in the message headers.</span></span>

```text
Authentication-Results:
   compauth=<fail | pass | softpass | none> reason=<yyy>
```

<span data-ttu-id="df2db-137">Dessa värden förklaras i [Meddelanderubriken Authentication-results](anti-spam-message-headers.md#authentication-results-message-header).</span><span class="sxs-lookup"><span data-stu-id="df2db-137">These values are explained at [Authentication-results message header](anti-spam-message-headers.md#authentication-results-message-header).</span></span>

<span data-ttu-id="df2db-138">Genom att granska meddelandehuvudena kan administratörer eller slutanvändare fastställa hur Microsoft 365 upptäckte att avsändaren är falsk.</span><span class="sxs-lookup"><span data-stu-id="df2db-138">By examining the message headers, admins or even end users can determine how Microsoft 365 determined that the sender is spoofed.</span></span>

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="df2db-139">Varför e-postautentisering inte alltid är tillräckligt för att stoppa förfalskning</span><span class="sxs-lookup"><span data-stu-id="df2db-139">Why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="df2db-140">Att bara förlita sig på e-postautentisering för att avgöra om ett inkommande meddelande har manipulerats har följande begränsningar:</span><span class="sxs-lookup"><span data-stu-id="df2db-140">Relying only on email authentication records to determine if an incoming message is spoofed has the following limitations:</span></span>

- <span data-ttu-id="df2db-141">Den sändande domänen kanske saknar de nödvändiga DNS-posterna eller så är posterna felaktigt konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="df2db-141">The sending domain might lack the required DNS records, or the records are incorrectly configured.</span></span>

- <span data-ttu-id="df2db-142">Källdomänen har konfigurerat DNS-poster som har konfigurerats korrekt men domänen stämmer inte överens med domänen i från-adressen.</span><span class="sxs-lookup"><span data-stu-id="df2db-142">The source domain has correctly configured DNS records, but that domain doesn't match the domain in the From address.</span></span> <span data-ttu-id="df2db-143">SPF och DKIM kräver inte att domänen används i från-adressen.</span><span class="sxs-lookup"><span data-stu-id="df2db-143">SPF and DKIM don't require the domain to be used in the From address.</span></span> <span data-ttu-id="df2db-144">Angripare eller legitima tjänster kan registrera en domän, konfigurera SPF och DKIM för domänen och använda en helt annan domän i Från-adressen.</span><span class="sxs-lookup"><span data-stu-id="df2db-144">Attackers or legitimate services can register a domain, configure SPF and DKIM for the domain, and use a completely different domain in the From address.</span></span> <span data-ttu-id="df2db-145">Meddelanden från avsändare inom den här domänen kommer att skicka SPF och DKIM.</span><span class="sxs-lookup"><span data-stu-id="df2db-145">Messages from senders in this domain will pass SPF and DKIM.</span></span>

<span data-ttu-id="df2db-146">Sammansatt autentisering kan lösa de här begränsningarna genom att godkänna meddelanden som annars skulle ha misslyckat e-postverifiering.</span><span class="sxs-lookup"><span data-stu-id="df2db-146">Composite authentication can address these limitations by passing messages that would otherwise fail email authentication checks.</span></span>

<span data-ttu-id="df2db-147">För enkelhetens skull ska följande exempel koncentrera sig på resultat av e-postverifiering.</span><span class="sxs-lookup"><span data-stu-id="df2db-147">For simplicity, the following examples concentrate on email authentication results.</span></span> <span data-ttu-id="df2db-148">Andra intelligensfaktorer i backend kan identifiera meddelanden som klarar e-postautentisering som falska eller meddelanden som misslyckas e-postautentisering som legitima.</span><span class="sxs-lookup"><span data-stu-id="df2db-148">Other back-end intelligence factors could identify messages that pass email authentication as spoofed, or messages that fail email email authentication as legitimate.</span></span>

<span data-ttu-id="df2db-149">Exempel: fabrikam.com-domänen har inga SPF-, DKIM- eller DMARC-poster.</span><span class="sxs-lookup"><span data-stu-id="df2db-149">For example, the fabrikam.com domain has no SPF, DKIM, or DMARC records.</span></span> <span data-ttu-id="df2db-150">Meddelanden från avsändare i fabrikam.com-domänen kan misslyckas sammansatt autentisering (Observera `compauth` värde och anledning):</span><span class="sxs-lookup"><span data-stu-id="df2db-150">Messages from senders in the fabrikam.com domain can fail composite authentication (note the `compauth` value and reason):</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="df2db-151">Om fabrikam.com konfigurerar en SPF utan en DKIM-post, kan meddelandet passera sammansatt autentisering.</span><span class="sxs-lookup"><span data-stu-id="df2db-151">If fabrikam.com configures an SPF without a DKIM record, the message can pass composite authentication.</span></span> <span data-ttu-id="df2db-152">Domänen som passerade SPF-kontroller är i linje med domänen i Från-adressen:</span><span class="sxs-lookup"><span data-stu-id="df2db-152">The domain that passed SPF checks is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="df2db-153">Om fabrikam.com konfigurerar en DKIM-post utan SPF-post, kan meddelandet passera sammansatt autentisering.</span><span class="sxs-lookup"><span data-stu-id="df2db-153">If fabrikam.com configures a DKIM record without an SPF record, the message can pass composite authentication.</span></span> <span data-ttu-id="df2db-154">Domänen i DKIM-signaturen är i linje med domänen i från-adressen:</span><span class="sxs-lookup"><span data-stu-id="df2db-154">The domain in the DKIM signature is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="df2db-155">Om domänen i SPF eller DKIM-signaturen inte överensstämmer med domänen i från-adressen kan meddelandet misslyckas med sammansatt autentisering:</span><span class="sxs-lookup"><span data-stu-id="df2db-155">If the domain in SPF or the DKIM signature doesn't align with the domain in the From address, the message can fail composite authentication:</span></span>

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="df2db-156">Lösning för legitima avsändare som skickar icke-autentiserade e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="df2db-156">Solutions for legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="df2db-157">Microsoft 365 håller reda på vilka som skickar icke-autentiserad e-post till organisationen.</span><span class="sxs-lookup"><span data-stu-id="df2db-157">Microsoft 365 keeps track of who is sending unauthenticated email to your organization.</span></span> <span data-ttu-id="df2db-158">Om tjänsten tycker att avsändaren inte är legitim kommer den att markera meddelanden från den här avsändaren som ett sammansatt autentiseringsfel.</span><span class="sxs-lookup"><span data-stu-id="df2db-158">If the service thinks the sender is not legitimate, it will mark messages from this sender as a composite authentication failure.</span></span> <span data-ttu-id="df2db-159">För att undvika denna dom kan du använda rekommendationerna i detta avsnitt.</span><span class="sxs-lookup"><span data-stu-id="df2db-159">To avoid this verdict, you can use the recommendations in this section.</span></span>

### <a name="configure-email-authentication-for-domains-you-own"></a><span data-ttu-id="df2db-160">Konfigurera e-postautentisering för domäner som du äger</span><span class="sxs-lookup"><span data-stu-id="df2db-160">Configure email authentication for domains you own</span></span>

<span data-ttu-id="df2db-161">Du kan själv använda den här metoden till att lösa förfalskning inom organisationen och förfalskning mellan domäner i fall där du äger eller interagerar med flera klientorganisationer.</span><span class="sxs-lookup"><span data-stu-id="df2db-161">You can use this method to resolve intra-org spoofing and cross-domain spoofing in cases where you own or interact with multiple tenants.</span></span> <span data-ttu-id="df2db-162">Det hjälper också till att lösa förfalskning mellan domäner där du skickar till andra kunder inom Microsoft 365 och också tredje parter med andra värdar.</span><span class="sxs-lookup"><span data-stu-id="df2db-162">It also helps resolve cross-domain spoofing where you send to other customers within Microsoft 365 or third parties that are hosted by other providers.</span></span>

- <span data-ttu-id="df2db-163">[Konfigurerar SPF-poster](set-up-spf-in-office-365-to-help-prevent-spoofing.md) för dina domäner.</span><span class="sxs-lookup"><span data-stu-id="df2db-163">[Configure SPF records](set-up-spf-in-office-365-to-help-prevent-spoofing.md) for your domains.</span></span>

- <span data-ttu-id="df2db-164">[Konfigurera DKIM poster](use-dkim-to-validate-outbound-email.md) för dina primära domäner.</span><span class="sxs-lookup"><span data-stu-id="df2db-164">[Configure DKIM records](use-dkim-to-validate-outbound-email.md) for your primary domains.</span></span>

- <span data-ttu-id="df2db-165">[Överväg att konfigurera DMARC-poster](use-dmarc-to-validate-email.md) för att fastställa dina legitima avsändare.</span><span class="sxs-lookup"><span data-stu-id="df2db-165">[Consider setting up DMARC records](use-dmarc-to-validate-email.md) for your domain to determine your legitimate senders.</span></span>

<span data-ttu-id="df2db-166">Microsoft tillhandahåller inte detaljerade implementeringsriktlinjer för SPF, DKIM eller DMARC.</span><span class="sxs-lookup"><span data-stu-id="df2db-166">Microsoft doesn't provide detailed implementation guidelines for SPF, DKIM, and DMARC records.</span></span> <span data-ttu-id="df2db-167">Det finns dock många information online.</span><span class="sxs-lookup"><span data-stu-id="df2db-167">However, there's many information available online.</span></span> <span data-ttu-id="df2db-168">Det finns också tredjepartsföretag som är dedikerade till att hjälpa din organisation att ställa in autentiseringsposter via e-post.</span><span class="sxs-lookup"><span data-stu-id="df2db-168">There are also third party companies dedicated to helping your organization setup email authentication records.</span></span>

#### <a name="you-dont-know-all-sources-for-your-email"></a><span data-ttu-id="df2db-169">Du vet inte för alla källor för din e-post</span><span class="sxs-lookup"><span data-stu-id="df2db-169">You don't know all sources for your email</span></span>

<span data-ttu-id="df2db-170">Många domäner publicerar inte SPF-poster eftersom de inte vet alla e-postkällor för meddelanden i sina domäner.</span><span class="sxs-lookup"><span data-stu-id="df2db-170">Many domains don't publish SPF records because they don't know all of the email sources for messages in their domain.</span></span> <span data-ttu-id="df2db-171">Börja med att publicera en SPF-post som innehåller alla e-postkällor som du vet om (särskilt där din företagstrafik finns), och publicera den neutrala SPF-principen `?all`.</span><span class="sxs-lookup"><span data-stu-id="df2db-171">Start by publishing an SPF record that contains all of the email sources you know about (especially where your corporate traffic is located), and publish the neutral SPF policy `?all`.</span></span> <span data-ttu-id="df2db-172">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="df2db-172">For example:</span></span>

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

<span data-ttu-id="df2db-173">Det här exemplet innebär att e-post från din företagsinfrastruktur ska skicka e-postautentisering, men e-post från okända källor kommer att gå tillbaka till neutrala.</span><span class="sxs-lookup"><span data-stu-id="df2db-173">This example means that email from your corporate infrastructure will pass email authentication, but email from unknown sources will fall back to neutral.</span></span>

<span data-ttu-id="df2db-174">Microsoft 365 behandlar inkommande e-post från din företagsinfrastruktur som autentiserad.</span><span class="sxs-lookup"><span data-stu-id="df2db-174">Microsoft 365 will treat inbound email from your corporate infrastructure as authenticated.</span></span> <span data-ttu-id="df2db-175">E-post från oidentifierade källor kan fortfarande markeras som falsk om det misslyckas med implicit autentisering.</span><span class="sxs-lookup"><span data-stu-id="df2db-175">Email from unidentified sources might still be marked as spoof if it fails implicit authentication.</span></span> <span data-ttu-id="df2db-176">Men det här är ändå en förbättring jämfört med att all e-post markeras som falsk av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="df2db-176">However, this is still an improvement from all email being marked as spoof by Microsoft 365.</span></span>

<span data-ttu-id="df2db-177">När du har börjat med en SPF fallback-princip för `?all` kan du gradvis upptäcka och ta med fler e-postkällor för dina meddelanden och sedan uppdatera SPF-posten med en striktare policy.</span><span class="sxs-lookup"><span data-stu-id="df2db-177">Once you've gotten started with an SPF fallback policy of `?all`, you can gradually discover and include more email sources for your messages, and then update your SPF record with a stricter policy.</span></span>

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a><span data-ttu-id="df2db-178">Använd förfalskningsinformation för att konfigurera tillåtna avsändare av icke-autentiserad e-post</span><span class="sxs-lookup"><span data-stu-id="df2db-178">Use spoof intelligence to configure permitted senders of unauthenticated email</span></span>

<span data-ttu-id="df2db-179">Du kan också använda [förfalskningsinformation](learn-about-spoof-intelligence.md) för att tillåta avsändare att skicka icke-autentiserade meddelanden till din organisation.</span><span class="sxs-lookup"><span data-stu-id="df2db-179">You can also use [spoof intelligence](learn-about-spoof-intelligence.md) to permit senders to transmit unauthenticated messages to your organization.</span></span>

<span data-ttu-id="df2db-180">För externa domäner är den falska användaren domänen i från-adressen, medan den sändande infrastrukturen är antingen käll-IP-adressen (indelad i/24 CIDR-intervall), eller organisationsdomänen för PTR-posten.</span><span class="sxs-lookup"><span data-stu-id="df2db-180">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the source IP address (divided up into /24 CIDR ranges), or the organizational domain of the reverse DNS (PTR) record.</span></span>

<span data-ttu-id="df2db-181">I skärmbilden nedan kan käll-IP: 131.107.18.4 med PTR-posten outbound.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="df2db-181">In the screenshot below, the source IP might be 131.107.18.4 with the PTR record outbound.mail.protection.outlook.com.</span></span> <span data-ttu-id="df2db-182">Detta skulle visas som outlook.com för den sändande infrastrukturen.</span><span class="sxs-lookup"><span data-stu-id="df2db-182">This would show up as outlook.com for the sending infrastructure.</span></span>

<span data-ttu-id="df2db-183">För att tillåta den här avsändaren att skicka icke-autentiserad e-post ändrar du **Nej** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="df2db-183">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>

![Konfigurera tillåtna avsändare för förfalskning](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a><span data-ttu-id="df2db-185">Skapa en tillåta-post för avsändare/mottagare-paret</span><span class="sxs-lookup"><span data-stu-id="df2db-185">Create an allow entry for the sender/recipient pair</span></span>

<span data-ttu-id="df2db-186">I [Skapa listor över betrodda avsändare i Microsoft 365](create-safe-sender-lists-in-office-365.md) finns information om hur du kringgår skräppostfiltrering, t.ex. vissa delar av nätfiskefiltrering, men inte filter för skadlig kod för vissa avsändare.</span><span class="sxs-lookup"><span data-stu-id="df2db-186">To bypass spam filtering, some parts of filtering for phishing, but not malware filtering for specific senders, see [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a><span data-ttu-id="df2db-187">Be avsändaren att konfigurera e-postautentisering för domäner som du inte äger</span><span class="sxs-lookup"><span data-stu-id="df2db-187">Ask the sender to configure email authentication for domains you don't own</span></span>

<span data-ttu-id="df2db-188">På grund av problem med skräppost och nätfiske rekommenderar Microsoft att alla avsändare konfigurerar e-postautentisering.</span><span class="sxs-lookup"><span data-stu-id="df2db-188">Because of the problem of spam and phishing, Microsoft recommends email authentication for all email organizations.</span></span> <span data-ttu-id="df2db-189">I stället för att konfigurera manuella åsidosättningar i din organisation kan du be en administratör i den sändande domänen att konfigurera sina poster för e-postverifiering.</span><span class="sxs-lookup"><span data-stu-id="df2db-189">Instead of configuring manual overrides in your organization, you can ask an admin in the sending domain to configure their email authentication records.</span></span>

- <span data-ttu-id="df2db-190">Även om de inte har behövt publicera poster för e-postautentisering tidigare ska de göra det om de skickar e-post till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df2db-190">Even if they didn't need to publish email authentication records in the past, they should do so if they send email to Microsoft.</span></span>

- <span data-ttu-id="df2db-191">Du bör konfigurera SPF för att publicera din domäns avsändande IP-adresser och även konfigurera DKIM (om tillgängligt) för att signera meddelanden digitalt.</span><span class="sxs-lookup"><span data-stu-id="df2db-191">Set up SPF to publish the domain's sending IP addresses, and set up DKIM (if available) to digitally sign messages.</span></span> <span data-ttu-id="df2db-192">Du kan också konfigurera DMARC-poster.</span><span class="sxs-lookup"><span data-stu-id="df2db-192">They should also consider setting up DMARC records.</span></span>

- <span data-ttu-id="df2db-193">Om användarna massutskick för att skicka e-post åt dem, ska du kontrollera att domänen i från-adressen (om den tillhör dem) stämmer överens med den domän som beviljar SPF- eller DMARC.</span><span class="sxs-lookup"><span data-stu-id="df2db-193">If they use bulk senders to send email on their behalf, verify that the domain in the From address (if it belongs to them) aligns with the domain that passes SPF or DMARC.</span></span>

- <span data-ttu-id="df2db-194">Kontrollera att följande platser (om de använder dem) ingår i SPF-posten:</span><span class="sxs-lookup"><span data-stu-id="df2db-194">Verify the following locations (if they use them) are included in the SPF record:</span></span>

  - <span data-ttu-id="df2db-195">Lokala e-postservrar.</span><span class="sxs-lookup"><span data-stu-id="df2db-195">On-premises email servers.</span></span>
  - <span data-ttu-id="df2db-196">E-post som skickas från en SaaS-leverantör (Software as-as-service).</span><span class="sxs-lookup"><span data-stu-id="df2db-196">Email sent from a software-as-a-service (SaaS) provider.</span></span>
  - <span data-ttu-id="df2db-197">E-post som skickas från en molnvärdtjänst (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services osv.).</span><span class="sxs-lookup"><span data-stu-id="df2db-197">Email sent from a cloud-hosting service (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, etc.).</span></span>

- <span data-ttu-id="df2db-198">För små domäner som är värd för en ISP konfigurerar du SPF-posten enligt anvisningarna från leverantören.</span><span class="sxs-lookup"><span data-stu-id="df2db-198">For small domains that are hosted by an ISP, configure the SPF record according to the instructions from the ISP.</span></span>

<span data-ttu-id="df2db-199">Det kan till en början vara svårt att få avsändardomäner att autentisera men med tiden, när allt fler e-postfilter markerar deras e-post som skräppost eller till och med avvisar dem så kommer de att konfigurera korrekta poster för att säkerställa bättre leverans.</span><span class="sxs-lookup"><span data-stu-id="df2db-199">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span> <span data-ttu-id="df2db-200">Deltagande i kampen mot nätfiske, och det kan minska risken för nätfiske i organisationer och organisationer som de skickar e-post till.</span><span class="sxs-lookup"><span data-stu-id="df2db-200">Also, their participation can help in the fight against phishing, and can reduce the possibility of phishing in their organization or organizations that they send email to.</span></span>

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a><span data-ttu-id="df2db-201">Information för leverantörer av infrastruktur (ISP:er, ESP:er eller molnvärdtjänster)</span><span class="sxs-lookup"><span data-stu-id="df2db-201">Information for infrastructure providers (ISPs, ESPs, or cloud hosting services)</span></span>

<span data-ttu-id="df2db-202">Om du är värd för en domäns e-post eller tillhandahåller infrastruktur som kan skicka e-post, ska du göra följande steg:</span><span class="sxs-lookup"><span data-stu-id="df2db-202">If you host a domain's email or provide hosting infrastructure that can send email, you should do the following steps:</span></span>

- <span data-ttu-id="df2db-203">Se till att dina kunder har dokumentation som förklarar hur kunderna ska konfigurera sina SPF-poster</span><span class="sxs-lookup"><span data-stu-id="df2db-203">Ensure your customers have documentation that explains how your customers should configure their SPF records</span></span>

- <span data-ttu-id="df2db-204">Överväg att signera DKIM-signaturer på utgående e-post även om kunden inte uttryckligen konfigurerar det (signera med en standarddomän).</span><span class="sxs-lookup"><span data-stu-id="df2db-204">Consider signing DKIM-signatures on outbound email, even if the customer doesn't explicitly set it up (sign with a default domain).</span></span> <span data-ttu-id="df2db-205">Du kan till och med dubbelsignera e-postmeddelandet med DKIM-signaturer (en gång med kundens domän om det har konfigurerats och en andra gång med företagets DKIM-signatur)</span><span class="sxs-lookup"><span data-stu-id="df2db-205">You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>

<span data-ttu-id="df2db-206">Leveransen till Microsoft garanteras inte även om du autentiserar e-post som kommer från din plattform men det ser åtminstone till att Microsoft inte markerar din e-post som skräppost för att den inte autentiseras.</span><span class="sxs-lookup"><span data-stu-id="df2db-206">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it isn't authenticated.</span></span>

## <a name="related-links"></a><span data-ttu-id="df2db-207">Relaterade länkar</span><span class="sxs-lookup"><span data-stu-id="df2db-207">Related links</span></span>

<span data-ttu-id="df2db-208">Mer information om bästa praxis för tjänsteleverantörer finns i [M3AAWG Mobile Messaging Best Practices för tjänsteleverantörer](https://www.m3aawg.org/sites/default/files/m3aawg-mobile-messaging-best-practices-service-providers-2015-08_0.pdf).</span><span class="sxs-lookup"><span data-stu-id="df2db-208">For more information about service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/m3aawg-mobile-messaging-best-practices-service-providers-2015-08_0.pdf).</span></span>

<span data-ttu-id="df2db-209">Lär dig hur Office 365 använder SPF och stöder DKIM-validering:</span><span class="sxs-lookup"><span data-stu-id="df2db-209">Learn how Office 365 uses SPF and supports DKIM validation:</span></span>

- [<span data-ttu-id="df2db-210">Mer om SPF</span><span class="sxs-lookup"><span data-stu-id="df2db-210">More about SPF</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)

- [<span data-ttu-id="df2db-211">Mer om DKIM</span><span class="sxs-lookup"><span data-stu-id="df2db-211">More about DKIM</span></span>](support-for-validation-of-dkim-signed-messages.md)
