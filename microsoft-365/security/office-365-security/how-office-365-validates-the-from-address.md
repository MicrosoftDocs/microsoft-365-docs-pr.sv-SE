---
title: Hur EOP verifierar från-adressen för att förhindra nätfiske
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om vilka typer av e-postadresser som godkänns eller avvisas av Exchange Online Protection (EOP) och Outlook.com för att förhindra nätfiske.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a02313bf8c36fe0be91340e421c69a8dc5c0842
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207087"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="fbc9d-103">Hur EOP verifierar från-adressen för att förhindra nätfiske</span><span class="sxs-lookup"><span data-stu-id="fbc9d-103">How EOP validates the From address to prevent phishing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fbc9d-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="fbc9d-104">**Applies to**</span></span>
- [<span data-ttu-id="fbc9d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fbc9d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="fbc9d-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="fbc9d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="fbc9d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fbc9d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="fbc9d-108">Nätfiskeattacker är ett konstant hot mot e-postorganisation.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-108">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="fbc9d-109">Förutom att använda [förfalskade (förfalskade)](anti-spoofing-protection.md)avsändares e-postadresser använder attacker ofta värden i från-adressen som bryter mot Internetstandarder.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-109">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="fbc9d-110">För att förhindra den här typen av nätfiske kräver nu Exchange Online Protection (EOP) och Outlook.com inkommande meddelanden en RFC-kompatibel från-adress enligt beskrivningen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-110">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this article.</span></span> <span data-ttu-id="fbc9d-111">Tillämpning av den här funktionen aktiverades i november 2017.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-111">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="fbc9d-112">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="fbc9d-112">**Notes**:</span></span>

- <span data-ttu-id="fbc9d-113">Om du regelbundet får e-post från organisationer som har felaktigt använda från-adresser enligt beskrivningen i den här artikeln bör du uppmuntra dessa organisationer att uppdatera sina e-postservrar så att de uppfyller moderna säkerhetsstandarder.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-113">If you regularly receive email from organizations that have malformed From addresses as described in this article, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="fbc9d-114">Det relaterade avsändarfältet (som används av Skicka för och distributionslistor) påverkas inte av dessa krav.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-114">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="fbc9d-115">Mer information finns i följande blogginlägg: Vad betyder vi när vi refererar till avsändaren av ett [e-postmeddelande?](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email).</span><span class="sxs-lookup"><span data-stu-id="fbc9d-115">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="fbc9d-116">En översikt över standarder för e-postmeddelanden</span><span class="sxs-lookup"><span data-stu-id="fbc9d-116">An overview of email message standards</span></span>

<span data-ttu-id="fbc9d-117">Ett vanligt SMTP-e-postmeddelande består av ett *meddelandekuvert* och meddelandeinnehåll.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-117">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="fbc9d-118">Meddelandekuvertet innehåller information som behövs för att överföra och leverera meddelandet mellan SMTP-servrarna.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-118">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="fbc9d-119">Meddelandeinnehållet innehåller fält för meddelanderubriker (kallas gemensamt *för meddelanderubriken)* och meddelandets brödtext.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-119">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="fbc9d-120">Meddelandekuvertet beskrivs i [RFC 5321](https://tools.ietf.org/html/rfc5321)och meddelanderubriken beskrivs i [RFC 5322.](https://tools.ietf.org/html/rfc5322)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-120">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="fbc9d-121">Mottagarna ser aldrig det faktiska meddelandekuvertet eftersom det genereras vid meddelandeöverföringen och det är faktiskt inte en del av meddelandet.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-121">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="fbc9d-122">Adressen (kallas även MAIL FROM address, P1 sender, or envelope sender) är den e-postadress som används vid `5321.MailFrom` SMTP-överföringen  av meddelandet.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-122">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="fbc9d-123">Den här **e-postadressen** registreras vanligtvis i huvudfältet Retursökväg i meddelandehuvudet (även om det är möjligt för avsändaren att ange en annan **e-postadress** för retursökväg).</span><span class="sxs-lookup"><span data-stu-id="fbc9d-123">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="fbc9d-124">(Kallas även från-adressen eller P2-avsändaren) är e-postadressen i fältet Från rubrik och är avsändarens e-postadress som visas i `5322.From` e-postklienter. </span><span class="sxs-lookup"><span data-stu-id="fbc9d-124">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="fbc9d-125">Från-adressen är fokus på kraven i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-125">The From address is the focus of the requirements in this article.</span></span>

<span data-ttu-id="fbc9d-126">Från-adressen definieras i detalj på flera offertförfrågningar (till exempel avsnitten 3.2.3, 3.4, 3.4 och 3.4.1 och [RFC 3696)](https://tools.ietf.org/html/rfc3696)i från.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-126">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="fbc9d-127">Det finns många varianter på adressering och vad som anses vara giltigt eller ogiltigt.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-127">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="fbc9d-128">För att göra det enkelt rekommenderar vi följande format och definitioner:</span><span class="sxs-lookup"><span data-stu-id="fbc9d-128">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="fbc9d-129">**Visningsnamn:** En valfri fras som beskriver e-postadressens ägare.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-129">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="fbc9d-130">Vi rekommenderar att du alltid omsluter visningsnamnet med dubbla citattecken (") enligt bilden.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-130">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="fbc9d-131">Om visningsnamnet innehåller ett kommatecken måste du _omge_ strängen med dubbla citattecken per RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-131">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="fbc9d-132">Om från-adressen innehåller ett visningsnamn måste värdet e-postadress omges av vinkelparenteser (< >) på det sätt som visas.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-132">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="fbc9d-133">Microsoft rekommenderar starkt att du infogar ett blanksteg mellan visningsnamnet och e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-133">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="fbc9d-134">**EmailAddress:** En e-postadress har följande `local-part@domain` format:</span><span class="sxs-lookup"><span data-stu-id="fbc9d-134">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="fbc9d-135">**lokaldel:** En sträng som identifierar postlådan som är kopplad till adressen.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-135">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="fbc9d-136">Det här värdet är unikt inom domänen.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-136">This value is unique within the domain.</span></span> <span data-ttu-id="fbc9d-137">Ofta används postlådans ägares användarnamn eller GUID.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-137">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="fbc9d-138">**domän:** Det fullständigt kvalificerade domännamnet (FQDN) för e-postservern som är värd för postlådan som identifieras av den lokala delen av e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-138">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="fbc9d-139">Det här är ytterligare saker att tänka på när det gäller värdet för EmailAddress:</span><span class="sxs-lookup"><span data-stu-id="fbc9d-139">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="fbc9d-140">Endast en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-140">Only one email address.</span></span>
  - <span data-ttu-id="fbc9d-141">Vi rekommenderar att du inte avgränsar vinkelparenteserna med blanksteg.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-141">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="fbc9d-142">Inkludera inte ytterligare text efter e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-142">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="fbc9d-143">Exempel på giltiga och ogiltiga från adresser</span><span class="sxs-lookup"><span data-stu-id="fbc9d-143">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="fbc9d-144">Följande Från e-postadresser är giltiga:</span><span class="sxs-lookup"><span data-stu-id="fbc9d-144">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="fbc9d-145">`From: < sender@contoso.com >` (Rekommenderas inte eftersom det finns blanksteg mellan vinkelparenteserna och e-postadressen.)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-145">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="fbc9d-146">`From: Microsoft 365 <sender@contoso.com>` (Rekommenderas inte eftersom visningsnamnet inte omges av dubbla citattecken.)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-146">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="fbc9d-147">Följande Från e-postadresser är ogiltiga:</span><span class="sxs-lookup"><span data-stu-id="fbc9d-147">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="fbc9d-148">**Ingen av från-adress:** Vissa automatiska meddelanden innehåller inte en Från-adress.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-148">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="fbc9d-149">Tidigare när Microsoft 365 eller Outlook.com fick ett meddelande utan en Från-adress lade tjänsten till följande standardadress från: så att meddelandet kan levereras:</span><span class="sxs-lookup"><span data-stu-id="fbc9d-149">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="fbc9d-150">Nu accepteras inte längre meddelanden med en tom Från-adress.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-150">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="fbc9d-151">`From: Microsoft 365 sender@contoso.com` (Visningsnamnet finns, men e-postadressen omges inte av vinkelparenteser.)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-151">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="fbc9d-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text efter e-postadressen.)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-152">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="fbc9d-153">`From: Sender, Example <sender.example@contoso.com>` (Visningsnamnet innehåller ett kommatecken, men omges inte av dubbla citattecken.)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-153">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="fbc9d-154">`From: "Microsoft 365 <sender@contoso.com>"` (Hela värdet omges felaktigt av dubbla citattecken.)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-154">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="fbc9d-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (Visningsnamnet finns, men e-postadressen omges inte av vinkelparenteser.)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-155">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="fbc9d-156">`From: Microsoft 365<sender@contoso.com>` (Inget blanksteg mellan visningsnamnet och den vänstra vinkelparentesen.)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-156">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="fbc9d-157">`From: "Microsoft 365"<sender@contoso.com>` (Inget blanksteg mellan det avslutande dubbla citattecknet och den vänstra vinkelparentesen.)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-157">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="fbc9d-158">Ignorera autosvar i din egen domän</span><span class="sxs-lookup"><span data-stu-id="fbc9d-158">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="fbc9d-159">Du kan inte använda värdet för `From: <>` att ignorera autosvar.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-159">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="fbc9d-160">I stället måste du konfigurera en null MX-post för din anpassade domän.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-160">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="fbc9d-161">Autosvar (och alla svar) utelämnas naturligt eftersom det inte finns någon publicerad adress som svarsservern kan skicka meddelanden till.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-161">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="fbc9d-162">Välj en e-postdomän som inte kan ta emot e-post.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-162">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="fbc9d-163">Om din primära domän till exempel är contoso.com kan du välja noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-163">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="fbc9d-164">MX-posten för den här domänen består av en enda punkt.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-164">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="fbc9d-165">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="fbc9d-165">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="fbc9d-166">Mer information om hur du konfigurerar MX-poster finns i [Skapa DNS-poster på vilken DNS-värd som helst för Microsoft 365.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-166">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="fbc9d-167">Mer information om hur du publicerar en null MX finns [i RFC 7505.](https://tools.ietf.org/html/rfc7505)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-167">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="fbc9d-168">Åsidosätt från tillämpning av adress</span><span class="sxs-lookup"><span data-stu-id="fbc9d-168">Override From address enforcement</span></span>

<span data-ttu-id="fbc9d-169">Om du vill åsidosätta kraven för från-adress för inkommande e-post kan du använda listan över tillåtna IP-adresser (anslutningsfiltrering) eller e-postflödesregler (kallas även transportregler) enligt beskrivningen i Skapa listor över betrodda avsändare i [Microsoft 365.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-169">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="fbc9d-170">Du kan inte åsidosätta kraven för Från-adress för utgående e-post som du skickar från Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-170">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="fbc9d-171">Dessutom kan Outlook.com åsidosättningar av något slag, även via support.</span><span class="sxs-lookup"><span data-stu-id="fbc9d-171">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="fbc9d-172">Andra sätt att förhindra och skydda mot cyberbrott i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fbc9d-172">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="fbc9d-173">Mer information om hur du kan stärka organisationen mot nätfiske, skräppost, databrott och andra hot finns i De 10 bästa sätten att skydda [Microsoft 365 för företag-abonnemang.](../../admin/security-and-compliance/secure-your-business-data.md)</span><span class="sxs-lookup"><span data-stu-id="fbc9d-173">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>