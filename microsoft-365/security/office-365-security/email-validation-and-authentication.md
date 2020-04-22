---
title: E-postautentisering i Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- Strat_O365_IP
ms.custom: TopSMBIssues
localization_priority: Priority
description: Lär dig mer om hur Exchange Online och Exchange Online Protection (EOP) i Microsoft 365 använder e-postautentisering (SPF, DKIM och DMARC) för att förhindra förfalskning, nätfiske och skräppost.
ms.openlocfilehash: f3a3ea902cb0c4fede4fcfd919f0969765bc4a96
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637562"
---
# <a name="email-authentication-in-microsoft-365"></a><span data-ttu-id="a4ebb-103">E-postautentisering i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a4ebb-103">Email authentication in Microsoft 365</span></span>

<span data-ttu-id="a4ebb-104">E-postautentisering (kallas även för e-postverifiering) är en grupp standarder som försöker sluta förfalskning (e-postmeddelanden från falska avsändare).</span><span class="sxs-lookup"><span data-stu-id="a4ebb-104">Email authentication (also known as email validation) is a group of standards that tries to stop spoofing (email messages from forged senders).</span></span> <span data-ttu-id="a4ebb-105">I Microsoft 365-organisationer med Exchange Online-postlådor och fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor används standarderna för att verifiera inkommande e-post:</span><span class="sxs-lookup"><span data-stu-id="a4ebb-105">In Microsoft 365 organizations with Exchange Online mailboxes and standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP useses the standards to verify inbound email:</span></span>

- [<span data-ttu-id="a4ebb-106">SPF</span><span class="sxs-lookup"><span data-stu-id="a4ebb-106">SPF</span></span>](how-office-365-uses-spf-to-prevent-spoofing.md)

- [<span data-ttu-id="a4ebb-107">DKIM</span><span class="sxs-lookup"><span data-stu-id="a4ebb-107">DKIM</span></span>](support-for-validation-of-dkim-signed-messages.md)

- [<span data-ttu-id="a4ebb-108">DMARC</span><span class="sxs-lookup"><span data-stu-id="a4ebb-108">DMARC</span></span>](use-dmarc-to-validate-email.md)

<span data-ttu-id="a4ebb-109">E-postautentisering verifierar att e-postmeddelanden från en avsändare (till exempel laura@contoso.com) är giltiga och kommer från förväntade källor för den e-postdomänen (till exempel contoso.com.)</span><span class="sxs-lookup"><span data-stu-id="a4ebb-109">Email authentication verifies that email messages from a sender (for example, laura@contoso.com) are legitimate and come from expected sources for that email domain (for example, contoso.com.)</span></span>

<span data-ttu-id="a4ebb-110">I resten av det här avsnittet förklaras hur dessa tekniker fungerar och hur EOP använder dem för att kontrollera inkommande e-post.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-110">The rest of this topic explains how these technologies work, and how EOP uses them to check inbound email.</span></span>

## <a name="use-email-authentication-to-help-prevent-spoofing"></a><span data-ttu-id="a4ebb-111">Använda e-postautentisering för att förhindra förfalskning</span><span class="sxs-lookup"><span data-stu-id="a4ebb-111">Use email authentication to help prevent spoofing</span></span>

<span data-ttu-id="a4ebb-112">DMARC förhindrar förfalskning genom att granska **från** adress i meddelanden (den avsändar-e-postadress som användarna ser i sina e-postklienter).</span><span class="sxs-lookup"><span data-stu-id="a4ebb-112">DMARC prevents spoofing by examining the **From** address in messages (the sender email address that users see in their email client).</span></span> <span data-ttu-id="a4ebb-113">Mottagande e-postorganisationer kan också verifiera att e-postdomänen har godkänts i SPF- eller DKIM-kontrollen, vilket betyder att domänen har autentiserats och är därför ingen förfalskning.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-113">Destination email organizations can also verify that the email domain has passed SPF or DKIM, which means that the domain has been authenticated and is therefore not spoofed.</span></span> 

<span data-ttu-id="a4ebb-114">Men problemet är att SPF-, DKIM- och DMARC-poster i DNS för e-postautentisering (kollektivt kallat principer för e-postautentisering) är helt valfria.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-114">However, the problem is that SPF, DKIM, and DMARC records in DNS for email authentication (collectively known as email authentication policies) are completely optional.</span></span> <span data-ttu-id="a4ebb-115">Det innebär att domäner med kraftfulla autentiseringsprinciper som microsoft.com och skype.com skyddas från förfalskning medan domäner som publicerar svagare autentiseringsprinciper eller ingen princip alls, är mål för att bli förfalskade.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-115">Therefore, while domains with strong email authentication policies like microsoft.com and skype.com are protected from spoofing, domains that publish weaker email authentication policies, or no policy at all, are prime targets for being spoofed.</span></span>

<span data-ttu-id="a4ebb-116">Till och med mars 2018 har endast 9 % av företag på Fortune 500-listan publicerat starka principer för e-postautentisering.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-116">As of March 2018, only 9% of domains of companies in the Fortune 500 publish strong email authentication policies.</span></span> <span data-ttu-id="a4ebb-117">Återstående 91% av företagen kan ha manipulerats av en inkräktare.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-117">The remaining 91% of companies might be spoofed by a attacker.</span></span> <span data-ttu-id="a4ebb-118">Om du inte har en annan funktion för e-postfiltrering på plats kan e-post från falska avsändare i dessa domäner levereras till användare.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-118">Unless some other email filtering mechanism is in-place, email from spoofed senders in these domains might be delivered to users.</span></span>

![DMARC-principer för Fortune 500-företag](../../media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)

<span data-ttu-id="a4ebb-120">Antalet små och medelstora företag som inte finns i Fortune 500-listan som publicerar starka principer för e-postautentisering är mindre, och ännu mindre för domäner som är utanför Nordamerika och Västeuropa.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-120">The proportion of small-to-medium sized companies that are not in the Fortune 500 that publish strong email authentication policies is smaller, and smaller still for email domains that are outside of North America and western Europe.</span></span>

<span data-ttu-id="a4ebb-121">Det här är ett stort problem, för att även om företagen kanske inte känner till hur e-postautentisering fungerar så vet nätfiskare det och utnyttjar den här bristen.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-121">This is a big problem because while enterprises may not be aware of how email authentication works, attackers fully understand and take advantage it.</span></span> <span data-ttu-id="a4ebb-122">Eftersom nätfiske är ett sådant problem och på grund av det begränsade införandet av principer för stark e-postautentisering, använder Microsoft *implicit e-postautentisering* för att kontrollera inkommande e-post.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-122">Because phishing is such a problem, and because of the limited adoption of strong email authentication policies, Microsoft uses *implicit email authentication* to check inbound email.</span></span>

<span data-ttu-id="a4ebb-123">Implicit e-postautentisering bygger på flera tillägg till vanliga principer för e-postautentisering.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-123">Implicit email authentication is built on numerous extensions to regular email authentication policies.</span></span> <span data-ttu-id="a4ebb-124">De här tilläggen är bland annat avsändarens rykte, avsändarhistorik, mottagarens historia, beteendeanalys och annan avancerad teknik.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-124">These extensions include sender reputation, sender history, recipient history, behavioral analysis, and other advanced techniques.</span></span> <span data-ttu-id="a4ebb-125">Ett meddelande som skickats från en domän som inte publicerar e-postautentisering markeras som förfalskning om det inte innehåller andra signaler som indikerar att det är äkta.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-125">A message sent from a domain that doesn't use email authentication policies will be marked as spoof unless it contains other signals to indicate that it's legitimate.</span></span>

<span data-ttu-id="a4ebb-126">Du kan läsa Microsofts allmänna meddelande i [Ett hav av nätfiskare, del 2 – förbättrat skydd mot förfalskning i Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span><span class="sxs-lookup"><span data-stu-id="a4ebb-126">To see Microsoft's general announcement, see [A Sea of Phish Part 2 - Enhanced Anti-spoofing in Microsoft 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209).</span></span>

## <a name="composite-authentication"></a><span data-ttu-id="a4ebb-127">Sammansatt autentisering</span><span class="sxs-lookup"><span data-stu-id="a4ebb-127">Composite authentication</span></span>

<span data-ttu-id="a4ebb-128">SPF, DKIM och DMARC är alla användbara men de kommunicerar inte tillräckligt om autentiseringsstatus om ett meddelande inte har explicita autentiseringsposter.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-128">While SPF, DKIM, and DMARC are all useful by themselves, they don't communicate enough authentication status in the event a message has no explicit authentication records.</span></span> <span data-ttu-id="a4ebb-129">Därför har Microsoft utvecklat en algoritm för implicit e-postautentisering som kombinerar flera signaler till ett enda värde som kallas _sammansatt autentisering_ – eller förkortat till compauth.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-129">Therefore, Microsoft has developed an algorithm for implicit email authentication that combines multiple signals into a single value called _composite authentication_, or compauth for short.</span></span> <span data-ttu-id="a4ebb-130">Compauth-värden är stämplade i **Autentiseringsresult**-huvudet i meddelandehuvudena.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-130">The compauth value is stamped into the **Authentication-Results** header in the message headers.</span></span>

> <span data-ttu-id="a4ebb-131">Autentiseringsresultat:</span><span class="sxs-lookup"><span data-stu-id="a4ebb-131">Authentication-Results:</span></span><br/><span data-ttu-id="a4ebb-132">&nbsp;&nbsp;&nbsp;compauth =\<misslyckat| godkänt | softpass | ingen\> anledning =\<yyy\></span><span class="sxs-lookup"><span data-stu-id="a4ebb-132">&nbsp;&nbsp;&nbsp;compauth=\<fail | pass | softpass | none\> reason=\<yyy\></span></span>

<span data-ttu-id="a4ebb-133">Dessa värden förklaras i [Meddelanderubriken Authentication-results](anti-spam-message-headers.md#authentication-results-message-header).</span><span class="sxs-lookup"><span data-stu-id="a4ebb-133">These values are explained at [Authentication-results message header](anti-spam-message-headers.md#authentication-results-message-header).</span></span>

<span data-ttu-id="a4ebb-134">Genom att granska meddelandehuvudena kan administratörer eller slutanvändare fastställa hur Microsoft 365 upptäckte att avsändaren är falsk.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-134">By examining the message headers, admins or even end users can determine how Microsoft 365 determined that the sender is spoofed.</span></span>

## <a name="why-email-authentication-is-not-always-enough-to-stop-spoofing"></a><span data-ttu-id="a4ebb-135">Varför e-postautentisering inte alltid är tillräckligt för att stoppa förfalskning</span><span class="sxs-lookup"><span data-stu-id="a4ebb-135">Why email authentication is not always enough to stop spoofing</span></span>

<span data-ttu-id="a4ebb-136">Att bara förlita sig på e-postautentisering för att avgöra om ett inkommande meddelande har manipulerats har följande begränsningar:</span><span class="sxs-lookup"><span data-stu-id="a4ebb-136">Relying only on email authentication records to determine if an incoming message is spoofed has the following limitations:</span></span>

- <span data-ttu-id="a4ebb-137">Den sändande domänen kanske saknar de nödvändiga DNS-posterna eller så är posterna felaktigt konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-137">The sending domain might lack the required DNS records, or the records are incorrectly configured.</span></span>

- <span data-ttu-id="a4ebb-138">Källdomänen har konfigurerat DNS-poster som har konfigurerats korrekt men domänen stämmer inte överens med domänen i från-adressen.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-138">The source domain has correctly configured DNS records, but that domain doesn't match the domain in the From address.</span></span> <span data-ttu-id="a4ebb-139">SPF och DKIM kräver inte att domänen används i från-adressen.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-139">SPF and DKIM don't require the domain to be used in the From address.</span></span> <span data-ttu-id="a4ebb-140">Angripare och legitima tjänster kan registrera en domän, konfigurera SPF och DKIM för domänen, använda en helt annan domän i från-adressen och meddelandet klarar SPF och DKIM.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-140">Attackers or legitimate services can register a domain, configure SPF and DKIM for the domain, use a completely different domain in the From address, and that message will pass SPF and DKIM.</span></span>

<span data-ttu-id="a4ebb-141">Sammansatt autentisering kan lösa de här begränsningarna genom att godkänna meddelanden som annars skulle ha misslyckat e-postverifiering.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-141">Composite authentication can address these limitations by passing messages that would otherwise fail email authentication checks.</span></span>

> [!NOTE]
> <span data-ttu-id="a4ebb-142">Som tidigare beskrivits används flera signaler för implicit e-postautentisering för att avgöra om ett meddelande är legitimt.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-142">As described earlier, implicit email authentication uses multiple signals to determine if a message is legitimate.</span></span> <span data-ttu-id="a4ebb-143">För enkelhetens skull ska följande exempel koncentrera sig på resultat av e-postverifiering.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-143">For simplicity, the following examples concentrate on email authentication results.</span></span> <span data-ttu-id="a4ebb-144">Andra intelligensfaktorer i backend kan identifiera meddelanden som klarar e-postautentisering som falska eller meddelanden som misslyckas e-postautentisering som legitima.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-144">Other back-end intelligence factors could identify messages that pass email authentication as spoofed, or messages that fail email email authentication as legitimate.</span></span>

<span data-ttu-id="a4ebb-145">Exempel: fabrikam.com-domänen har inga SPF-, DKIM- eller DMARC-poster.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-145">For example, the fabrikam.com domain has no SPF, DKIM, or DMARC records.</span></span> <span data-ttu-id="a4ebb-146">Meddelanden från avsändare i fabrikam.com-domänen kan misslyckas sammansatt autentisering (Observera `compauth` värde och anledning):</span><span class="sxs-lookup"><span data-stu-id="a4ebb-146">Messages from senders in the fabrikam.com domain can fail composite authentication (note the `compauth` value and reason):</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=fabrikam.com; compauth=fail reason=001
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="a4ebb-147">Om fabrikam.com konfigurerar en SPF utan en DKIM-post kan meddelandet klara sammansatt autentisering eftersom domänen som passerade SPF justeras mot domänen i från-adressen:</span><span class="sxs-lookup"><span data-stu-id="a4ebb-147">If fabrikam.com configures an SPF without a DKIM record, the message can pass composite authentication, because the domain that passed SPF is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=pass (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="a4ebb-148">Om fabrikam.com konfigurerar en DKIM-post utan en SPF-post kan meddelandet klara sammansatt autentisering eftersom domänen i den överförda DKIM-signaturen justeras mot domänen i från-adressen:</span><span class="sxs-lookup"><span data-stu-id="a4ebb-148">If fabrikam.com configures a DKIM record without an SPF record, the message can pass composite authentication, because the domain in the passed DKIM signature is aligned with the domain in the From address:</span></span>

```text
Authentication-Results: spf=none (sender IP is 10.2.3.4)
  smtp.mailfrom=fabrikam.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.fabrikam.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=fabrikam.com; compauth=pass reason=109
From: chris@fabrikam.com
To: michelle@contoso.com
```

<span data-ttu-id="a4ebb-149">Om domänen i SPF eller DKIM-signaturen inte överensstämmer med domänen i från-adressen kan meddelandet misslyckas med sammansatt autentisering:</span><span class="sxs-lookup"><span data-stu-id="a4ebb-149">If the domain in SPF or the DKIM signature don't align with the domain in the From address, the message can fail composite authentication:</span></span>

```text
Authentication-Results: spf=none (sender IP is 192.168.1.8)
  smtp.mailfrom=maliciousdomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousdomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: chris@contoso.com
To: michelle@fabrikam.com
```

## <a name="solutions-for-legitimate-senders-who-are-sending-unauthenticated-email"></a><span data-ttu-id="a4ebb-150">Lösning för legitima avsändare som skickar icke-autentiserade e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="a4ebb-150">Solutions for legitimate senders who are sending unauthenticated email</span></span>

<span data-ttu-id="a4ebb-151">Microsoft 365 håller reda på vilka som skickar icke-autentiserad e-post till organisationen.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-151">Microsoft 365 keeps track of who is sending unauthenticated email to your organization.</span></span> <span data-ttu-id="a4ebb-152">Om tjänsten inte bedömer avsändaren som legitim markeras e-posten med ett compauth-fel.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-152">If the service thinks the sender is not legitimate, it will mark it as a composite authentication failure.</span></span> <span data-ttu-id="a4ebb-153">Du kan undvika det här genom att använda rekommendationerna i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-153">To avoid this, you can use the recommendations in this section.</span></span>

### <a name="configure-email-authentication-for-domains-you-own"></a><span data-ttu-id="a4ebb-154">Konfigurera e-postautentisering för domäner som du äger</span><span class="sxs-lookup"><span data-stu-id="a4ebb-154">Configure email authentication for domains you own</span></span>

<span data-ttu-id="a4ebb-155">Du kan själv använda den här metoden till att lösa förfalskning inom organisationen och förfalskning mellan domäner i fall där du äger eller interagerar med flera klientorganisationer.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-155">You can use this method to resolve intra-org spoofing and cross-domain spoofing in cases where you own or interact with multiple tenants.</span></span> <span data-ttu-id="a4ebb-156">Det hjälper också till att lösa förfalskning mellan domäner där du skickar till andra kunder inom Microsoft 365 och också tredje parter med andra värdar.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-156">It also helps resolve cross-domain spoofing where you send to other customers within Microsoft 365 or third parties that are hosted by other providers.</span></span>

- <span data-ttu-id="a4ebb-157">[Konfigurerar SPF-poster](set-up-spf-in-office-365-to-help-prevent-spoofing.md) för dina domäner.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-157">[Configure SPF records](set-up-spf-in-office-365-to-help-prevent-spoofing.md) for your domains.</span></span>

- <span data-ttu-id="a4ebb-158">[Konfigurera DKIM poster](use-dkim-to-validate-outbound-email.md) för dina primära domäner.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-158">[Configure DKIM records](use-dkim-to-validate-outbound-email.md) for your primary domains.</span></span>

- <span data-ttu-id="a4ebb-159">[Överväg att konfigurera DMARC-poster](use-dmarc-to-validate-email.md) för att fastställa dina legitima avsändare.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-159">[Consider setting up DMARC records](use-dmarc-to-validate-email.md) for your domain to determine your legitimate senders.</span></span>

<span data-ttu-id="a4ebb-160">Microsoft tillhandahåller inte detaljerade implementeringsriktlinjer för SPF, DKIM eller DMARC.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-160">Microsoft doesn't provide detailed implementation guidelines for SPF, DKIM, and DMARC records.</span></span> <span data-ttu-id="a4ebb-161">Det finns emellertid mycket information tillgänglig online.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-161">However, there's a lot of information available online.</span></span> <span data-ttu-id="a4ebb-162">Det finns även tredjepartsföretag specialiserade på att hjälpa din organisation att konfigurera poster för e-postautentisering.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-162">There are also 3rd party companies dedicated to helping your organization set up email authentication records.</span></span>

#### <a name="you-dont-know-all-sources-for-your-email"></a><span data-ttu-id="a4ebb-163">Du vet inte för alla källor för din e-post</span><span class="sxs-lookup"><span data-stu-id="a4ebb-163">You don't know all sources for your email</span></span>

<span data-ttu-id="a4ebb-164">Många domäner publicerar inte SPF-poster eftersom de inte vet alla e-postkällor för meddelanden i sina domäner.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-164">Many domains don't publish SPF records because they don't know all of the email sources for messages in their domain.</span></span> <span data-ttu-id="a4ebb-165">Börja med att publicera en SPF-post som innehåller alla e-postkällor som du vet om (särskilt där din företagstrafik finns), och publicera den neutrala SPF-principen `?all`.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-165">Start by publishing an SPF record that contains all of the email sources you know about (especially where your corporate traffic is located), and publish the neutral SPF policy `?all`.</span></span> <span data-ttu-id="a4ebb-166">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="a4ebb-166">For example:</span></span>

```text
fabrikam.com IN TXT "v=spf1 include:spf.fabrikam.com ?all"
```

<span data-ttu-id="a4ebb-167">Det här exemplet innebär att e-post från din företagsinfrastruktur ska skicka e-postautentisering, men e-post från okända källor kommer att gå tillbaka till neutrala.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-167">This example means that email from your corporate infrastructure will pass email authentication, but email from unknown sources will fall back to neutral.</span></span>

<span data-ttu-id="a4ebb-168">Microsoft 365 behandlar inkommande e-post från företagets infrastruktur som autentiserad, men e-post från oidentifierade källor kan fortfarande vara markerade som falska (beroende på om Microsoft 365 kan verifiera det implicit).</span><span class="sxs-lookup"><span data-stu-id="a4ebb-168">Microsoft 365 will treat inbound email from your corporate infrastructure as authenticated, but email from unidentified sources might still be marked as spoof (depending upon whether Microsoft 365 can implicitly authenticate it).</span></span> <span data-ttu-id="a4ebb-169">Men det här är ändå en förbättring jämfört med att all e-post markeras som falsk av Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-169">However, this is still an improvement from all email being marked as spoof by Microsoft 365.</span></span>

<span data-ttu-id="a4ebb-170">När du har börjat med en SPF fallback-princip för `?all` kan du gradvis upptäcka och ta med fler e-postkällor för dina meddelanden och sedan uppdatera SPF-posten med en striktare policy.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-170">Once you've gotten started with an SPF fallback policy of `?all`, you can gradually discover and include more email sources for your messages, and then update your SPF record with a stricter policy.</span></span>

### <a name="use-spoof-intelligence-to-configure-permitted-senders-of-unauthenticated-email"></a><span data-ttu-id="a4ebb-171">Använd förfalskningsinformation för att konfigurera tillåtna avsändare av icke-autentiserad e-post</span><span class="sxs-lookup"><span data-stu-id="a4ebb-171">Use spoof intelligence to configure permitted senders of unauthenticated email</span></span>

<span data-ttu-id="a4ebb-172">Du kan också använda [förfalskningsinformation](learn-about-spoof-intelligence.md) för att tillåta avsändare att skicka icke-autentiserade meddelanden till din organisation.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-172">You can also use [spoof intelligence](learn-about-spoof-intelligence.md) to permit senders to transmit unauthenticated messages to your organization.</span></span>

<span data-ttu-id="a4ebb-173">För externa domäner är den falska användaren domänen i från-adressen, medan den sändande infrastrukturen är antingen käll-IP-adressen (indelad i/24 CIDR-intervall), eller organisationsdomänen för PTR-posten.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-173">For external domains, the spoofed user is the domain in the From address, while the sending infrastructure is either the source IP address (divided up into /24 CIDR ranges), or the organizational domain of the reverse DNS (PTR) record.</span></span>

<span data-ttu-id="a4ebb-174">I skärmbilden nedan kan käll-IP: 131.107.18.4 med PTR-posten outbound.mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-174">In the screenshot below, the source IP might be 131.107.18.4 with the PTR record outbound.mail.protection.outlook.com.</span></span> <span data-ttu-id="a4ebb-175">Detta skulle visas som outlook.com för den sändande infrastrukturen.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-175">This would show up as outlook.com for the sending infrastructure.</span></span>

<span data-ttu-id="a4ebb-176">För att tillåta den här avsändaren att skicka icke-autentiserad e-post ändrar du **Nej** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-176">To permit this sender to send unauthenticated email, change the **No** to a **Yes**.</span></span>

![Konfigurera tillåtna avsändare för förfalskning](../../media/d4334921-d820-4334-8217-788279701e94.jpg)

### <a name="create-an-allow-entry-for-the-senderrecipient-pair"></a><span data-ttu-id="a4ebb-178">Skapa en tillåta-post för avsändare/mottagare-paret</span><span class="sxs-lookup"><span data-stu-id="a4ebb-178">Create an allow entry for the sender/recipient pair</span></span>

<span data-ttu-id="a4ebb-179">I [Skapa listor över betrodda avsändare i Microsoft 365](create-safe-sender-lists-in-office-365.md) finns information om hur du kringgår skräppostfiltrering, t.ex. vissa delar av nätfiskefiltrering, men inte filter för skadlig kod för vissa avsändare.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-179">To bypass spam filtering, some parts of phish filtering, but not malware filtering for specific senders, see [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

### <a name="ask-the-sender-to-configure-email-authentication-for-domains-you-dont-own"></a><span data-ttu-id="a4ebb-180">Be avsändaren att konfigurera e-postautentisering för domäner som du inte äger</span><span class="sxs-lookup"><span data-stu-id="a4ebb-180">Ask the sender to configure email authentication for domains you don't own</span></span>

<span data-ttu-id="a4ebb-181">På grund av problem med skräppost och nätfiske rekommenderar Microsoft att alla avsändare konfigurerar e-postautentisering.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-181">Because of the problem of spam and phishing, Microsoft recommends email authentication for all email organizations.</span></span> <span data-ttu-id="a4ebb-182">I stället för att konfigurera manuella åsidosättningar i din organisation kan du be en administratör i den sändande domänen att konfigurera sina poster för e-postverifiering.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-182">Instead of configuring manual overrides in your organization, you can ask an admin in the sending domain to configure their email authentication records.</span></span>

- <span data-ttu-id="a4ebb-183">Även om de inte har behövt publicera poster för e-postautentisering tidigare ska de göra det om de skickar e-post till Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-183">Even if they didn't need to publish email authentication records in the past, they should do so if they send email to Microsoft.</span></span>

- <span data-ttu-id="a4ebb-184">Du bör konfigurera SPF för att publicera din domäns avsändande IP-adresser och även konfigurera DKIM (om tillgängligt) för att signera meddelanden digitalt.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-184">Set up SPF to publish the domain's sending IP addresses, and set up DKIM (if available) to digitally sign messages.</span></span> <span data-ttu-id="a4ebb-185">Du kan också konfigurera DMARC-poster.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-185">They should also consider setting up DMARC records.</span></span>

- <span data-ttu-id="a4ebb-186">Om användarna massutskick för att skicka e-post åt dem, ska du kontrollera att domänen i från-adressen (om den tillhör dem) stämmer överens med den domän som beviljar SPF- eller DMARC.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-186">If they use bulk senders to send email on their behalf, verify that the domain in the From address (if it belongs to them) aligns with the domain that passes SPF or DMARC.</span></span>

- <span data-ttu-id="a4ebb-187">Kontrollera att följande platser (om de använder dem) ingår i SPF-posten:</span><span class="sxs-lookup"><span data-stu-id="a4ebb-187">Verify the following locations (if they use them) are included in the SPF record:</span></span>
  
  - <span data-ttu-id="a4ebb-188">Lokala e-postservrar.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-188">On-premises email servers.</span></span>
  - <span data-ttu-id="a4ebb-189">E-post som skickas från en SaaS-leverantör (Software as-as-service).</span><span class="sxs-lookup"><span data-stu-id="a4ebb-189">Email sent from a software-as-a-service (SaaS) provider.</span></span>
  - <span data-ttu-id="a4ebb-190">E-post som skickas från en molnvärdtjänst (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services osv.).</span><span class="sxs-lookup"><span data-stu-id="a4ebb-190">Email sent from a cloud-hosting service (Microsoft Azure, GoDaddy, Rackspace, Amazon Web Services, etc.).</span></span>

- <span data-ttu-id="a4ebb-191">För små domäner som är värd för en ISP konfigurerar du SPF-posten enligt anvisningarna från leverantören.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-191">For small domains that are hosted by an ISP, configure the SPF record according to the instructions from the ISP.</span></span>

<span data-ttu-id="a4ebb-192">Det kan till en början vara svårt att få avsändardomäner att autentisera men med tiden, när allt fler e-postfilter markerar deras e-post som skräppost eller till och med avvisar dem så kommer de att konfigurera korrekta poster för att säkerställa bättre leverans.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-192">While it may be difficult at first to get sending domains to authenticate, over time, as more and more email filters start junking or even rejecting their email, it will cause them to set up the proper records to ensure better delivery.</span></span> <span data-ttu-id="a4ebb-193">Deltagande i kampen mot nätfiske, och det kan minska risken för nätfiske i organisationer och organisationer som de skickar e-post till.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-193">Also, their participation can help in the fight against phishing, and can reduce the possibility of phishing in their organization or organizations that they send email to.</span></span>

#### <a name="information-for-infrastructure-providers-isps-esps-or-cloud-hosting-services"></a><span data-ttu-id="a4ebb-194">Information för leverantörer av infrastruktur (ISP:er, ESP:er eller molnvärdtjänster)</span><span class="sxs-lookup"><span data-stu-id="a4ebb-194">Information for infrastructure providers (ISPs, ESPs, or cloud hosting services)</span></span>

<span data-ttu-id="a4ebb-195">Om du är värd för en domäns e-post eller tillhandahåller infrastruktur som kan skicka e-post, ska du göra följande steg:</span><span class="sxs-lookup"><span data-stu-id="a4ebb-195">If you host a domain's email or provide hosting infrastructure that can send email, you should do the following steps:</span></span>

- <span data-ttu-id="a4ebb-196">Se till att dina kunder har dokumentation som förklarar hur kunderna ska konfigurera sina SPF-poster</span><span class="sxs-lookup"><span data-stu-id="a4ebb-196">Ensure your customers have documentation that explains how your customers should configure their SPF records</span></span>

- <span data-ttu-id="a4ebb-197">Överväg att signera DKIM-signaturer på utgående e-post även om kunden inte uttryckligen konfigurerar det (signera med en standarddomän).</span><span class="sxs-lookup"><span data-stu-id="a4ebb-197">Consider signing DKIM-signatures on outbound email, even if the customer doesn't explicitly set it up (sign with a default domain).</span></span> <span data-ttu-id="a4ebb-198">Du kan till och med dubbelsignera e-postmeddelandet med DKIM-signaturer (en gång med kundens domän om det har konfigurerats och en andra gång med företagets DKIM-signatur)</span><span class="sxs-lookup"><span data-stu-id="a4ebb-198">You can even double-sign the email with DKIM signatures (once with the customer's domain if they have set it up, and a second time with your company's DKIM signature)</span></span>

<span data-ttu-id="a4ebb-199">Leveransen till Microsoft garanteras inte även om du autentiserar e-post som kommer från din plattform men det ser åtminstone till att Microsoft inte markerar din e-post som skräppost för att den inte autentiseras.</span><span class="sxs-lookup"><span data-stu-id="a4ebb-199">Deliverability to Microsoft is not guaranteed even if you authenticate email originating from your platform, but at least it ensures that Microsoft does not junk your email because it isn't authenticated.</span></span>

<span data-ttu-id="a4ebb-200">Mer information om metodtips för tjänstleverantörer finns i [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf) (M3AAWG:s metodtips för mobila meddelanden för tjänstleverantörer).</span><span class="sxs-lookup"><span data-stu-id="a4ebb-200">For more details on service providers best practices, see [M3AAWG Mobile Messaging Best Practices for Service Providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf).</span></span>
