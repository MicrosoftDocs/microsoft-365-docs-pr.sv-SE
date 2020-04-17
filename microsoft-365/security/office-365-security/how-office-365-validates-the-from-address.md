---
title: Så här validerar Office 365 Från-adressen för att förhindra nätfiske
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Lear om kraven på Från e-postadresser för inkommande meddelanden i Office 365. Från och med november 2017 kräver tjänsten nu RFC-kompatibla Från-adresser för att förhindra förfalskning.
ms.openlocfilehash: 4df073cfff3c36f60a013237d95548cb48fa7b5f
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43529007"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="6e68f-104">Så här validerar Office 365 Från-adressen för att förhindra nätfiske</span><span class="sxs-lookup"><span data-stu-id="6e68f-104">How Office 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="6e68f-105">Office 365-e-postkonton får ett allt större antal nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="6e68f-105">Office 365 email accounts receive an increasingly large number of phishing attacks.</span></span> <span data-ttu-id="6e68f-106">Förutom att använda [falska (förfalskade) avsändar-e-postadresser](anti-spoofing-protection.md)använder angripare ofta värden i den Från-adress som bryter mot internetstandarder.</span><span class="sxs-lookup"><span data-stu-id="6e68f-106">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="6e68f-107">För att förhindra den här typen av nätfiske kräver Office 365 och Outlook.com nu inkommande meddelanden för att inkludera en RFC-kompatibel Från-adress enligt beskrivningen i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="6e68f-107">To help prevent this type of phishing, Office 365 and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this topic.</span></span> <span data-ttu-id="6e68f-108">Denna verkställighet aktiverades i november 2017.</span><span class="sxs-lookup"><span data-stu-id="6e68f-108">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="6e68f-109">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="6e68f-109">**Notes**:</span></span>

- <span data-ttu-id="6e68f-110">Om du regelbundet får e-post från organisationer som har felformaterat från-adresser enligt beskrivningen i det här avsnittet uppmuntrar du dessa organisationer att uppdatera sina e-postservrar så att de uppfyller moderna säkerhetsstandarder.</span><span class="sxs-lookup"><span data-stu-id="6e68f-110">If you regularly receive email from organizations that have malformed From addresses as described in this topic, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="6e68f-111">Det relaterade fältet Avsändare (som används av Skicka för räkning och e-postlistor) påverkas inte av dessa krav.</span><span class="sxs-lookup"><span data-stu-id="6e68f-111">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="6e68f-112">För mer information, se följande blogginlägg: [Vad menar vi när vi hänvisar till "avsändaren" av ett e-postmeddelande?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span><span class="sxs-lookup"><span data-stu-id="6e68f-112">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="6e68f-113">En översikt över e-postmeddelanden standarder</span><span class="sxs-lookup"><span data-stu-id="6e68f-113">An overview of email message standards</span></span>

<span data-ttu-id="6e68f-114">Ett standardmeddelande för SMTP-meddelanden består av ett *meddelandekuvert* och meddelandeinnehåll.</span><span class="sxs-lookup"><span data-stu-id="6e68f-114">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="6e68f-115">Meddelandekuvertet innehåller information som krävs för att överföra och leverera meddelandet mellan SMTP-servrar.</span><span class="sxs-lookup"><span data-stu-id="6e68f-115">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="6e68f-116">Meddelandeinnehållet innehåller fält för meddelandehuvud (kallas gemensamt *meddelandehuvudet)* och meddelandetexten.</span><span class="sxs-lookup"><span data-stu-id="6e68f-116">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="6e68f-117">Meddelandekuvertet beskrivs i [RFC 5321](https://tools.ietf.org/html/rfc5321)och meddelandehuvudet beskrivs i [RFC 5322](https://tools.ietf.org/html/rfc5322).</span><span class="sxs-lookup"><span data-stu-id="6e68f-117">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="6e68f-118">Mottagarna ser aldrig det faktiska meddelandekuvertet eftersom det genereras av meddelandeöverföringsprocessen och det är faktiskt inte en del av meddelandet.</span><span class="sxs-lookup"><span data-stu-id="6e68f-118">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="6e68f-119">Adressen `5321.MailFrom` (kallas även **MAIL FROM-adressen,** P1-avsändaren eller kuvertavsändaren) är den e-postadress som används i SMTP-överföringen av meddelandet.</span><span class="sxs-lookup"><span data-stu-id="6e68f-119">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="6e68f-120">Den här e-postadressen registreras vanligtvis i fältet **Retursökväg** i meddelandehuvudet (även om avsändaren kan ange en annan **e-postadress för retursökväg).**</span><span class="sxs-lookup"><span data-stu-id="6e68f-120">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="6e68f-121">(även `5322.From` känd som Från-adressen eller P2-avsändaren) är e-postadressen i fältet **Från-huvud** och är avsändarens e-postadress som visas i e-postklienter.</span><span class="sxs-lookup"><span data-stu-id="6e68f-121">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="6e68f-122">Från-adressen är i fokus för kraven i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="6e68f-122">The From address is the focus of the requirements in this topic.</span></span>

<span data-ttu-id="6e68f-123">Från-adressen definieras i detalj i flera RFC (till exempel RFC 5322-avsnitten 3.2.3, 3.4 och 3.4.1 och [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span><span class="sxs-lookup"><span data-stu-id="6e68f-123">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="6e68f-124">Det finns många varianter på adressering och vad som anses giltigt eller ogiltigt.</span><span class="sxs-lookup"><span data-stu-id="6e68f-124">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="6e68f-125">För att hålla det enkelt rekommenderar vi följande format och definitioner:</span><span class="sxs-lookup"><span data-stu-id="6e68f-125">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="6e68f-126">**Visningsnamn**: En valfri fras som beskriver e-postadressens ägare.</span><span class="sxs-lookup"><span data-stu-id="6e68f-126">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="6e68f-127">Vi rekommenderar att du alltid omsluter visningsnamnet med dubbla citattecken (") som visas.</span><span class="sxs-lookup"><span data-stu-id="6e68f-127">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="6e68f-128">Om visningsnamnet innehåller ett kommatecken _måste_ du omge strängen med dubbla citattecken per RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="6e68f-128">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="6e68f-129">Om från-adressen innehåller ett visningsnamn måste värdet e-postadress omges av vinkelparenteser (< >) enligt bilden.</span><span class="sxs-lookup"><span data-stu-id="6e68f-129">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="6e68f-130">Microsoft rekommenderar starkt att du infogar ett mellanslag mellan visningsnamnet och e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="6e68f-130">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="6e68f-131">**EmailAddress**: En e-postadress använder formatet: `local-part@domain`</span><span class="sxs-lookup"><span data-stu-id="6e68f-131">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="6e68f-132">**lokal del**: En sträng som identifierar postlådan som är associerad med adressen.</span><span class="sxs-lookup"><span data-stu-id="6e68f-132">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="6e68f-133">Det här värdet är unikt inom domänen.</span><span class="sxs-lookup"><span data-stu-id="6e68f-133">This value is unique within the domain.</span></span> <span data-ttu-id="6e68f-134">Ofta används postlådeägarens användarnamn eller GUID.</span><span class="sxs-lookup"><span data-stu-id="6e68f-134">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="6e68f-135">**domän:** Det fullständigt kvalificerade domännamnet (FQDN) för e-postservern som är värd för postlådan som identifieras av den lokala delen av e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="6e68f-135">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="6e68f-136">Dessa är några ytterligare överväganden för emailAddress värde:</span><span class="sxs-lookup"><span data-stu-id="6e68f-136">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="6e68f-137">Endast en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="6e68f-137">Only one email address.</span></span>
  - <span data-ttu-id="6e68f-138">Vi rekommenderar att du inte separerar vinkelfästena med mellanslag.</span><span class="sxs-lookup"><span data-stu-id="6e68f-138">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="6e68f-139">Ta inte med ytterligare text efter e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="6e68f-139">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="6e68f-140">Exempel på giltiga och ogiltiga Från-adresser</span><span class="sxs-lookup"><span data-stu-id="6e68f-140">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="6e68f-141">Följande Från e-postadresser är giltiga:</span><span class="sxs-lookup"><span data-stu-id="6e68f-141">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="6e68f-142">`From: < sender@contoso.com >`(Rekommenderas inte eftersom det finns mellanrum mellan vinkelparenteserna och e-postadressen.)</span><span class="sxs-lookup"><span data-stu-id="6e68f-142">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Office 365" <sender@contoso.com>`

- <span data-ttu-id="6e68f-143">`From: Office 365 <sender@contoso.com>`(Rekommenderas inte eftersom visningsnamnet inte omges av dubbla citattecken.)</span><span class="sxs-lookup"><span data-stu-id="6e68f-143">`From: Office 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="6e68f-144">Följande Från-e-postadresser är ogiltiga:</span><span class="sxs-lookup"><span data-stu-id="6e68f-144">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="6e68f-145">**Nej från-adress**: Vissa automatiska meddelanden innehåller inte en Från-adress.</span><span class="sxs-lookup"><span data-stu-id="6e68f-145">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="6e68f-146">Tidigare, när Office 365 eller Outlook.com tog emot ett meddelande utan från-adress, lade tjänsten till följande standard Från:-adress för att göra meddelandet slutprodukt:</span><span class="sxs-lookup"><span data-stu-id="6e68f-146">In the past, when Office 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="6e68f-147">Meddelanden med en tom Från-adress accepteras inte längre.</span><span class="sxs-lookup"><span data-stu-id="6e68f-147">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="6e68f-148">`From: Office 365 sender@contoso.com`(Visningsnamnet finns, men e-postadressen omges inte av vinkelparenteser.)</span><span class="sxs-lookup"><span data-stu-id="6e68f-148">`From: Office 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="6e68f-149">`From: "Office 365" <sender@contoso.com> (Sent by a process)`(Text efter e-postadressen.)</span><span class="sxs-lookup"><span data-stu-id="6e68f-149">`From: "Office 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="6e68f-150">`From: Sender, Example <sender.example@contoso.com>`(Visningsnamnet innehåller ett kommatecken, men omges inte av dubbla citattecken.)</span><span class="sxs-lookup"><span data-stu-id="6e68f-150">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="6e68f-151">`From: "Office 365 <sender@contoso.com>"`(Hela värdet omges felaktigt av dubbla citattecken.)</span><span class="sxs-lookup"><span data-stu-id="6e68f-151">`From: "Office 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="6e68f-152">`From: "Office 365 <sender@contoso.com>" sender@contoso.com`(Visningsnamnet finns, men e-postadressen omges inte av vinkelparenteser.)</span><span class="sxs-lookup"><span data-stu-id="6e68f-152">`From: "Office 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="6e68f-153">`From: Office 365<sender@contoso.com>`(Inget blanksteg mellan visningsnamnet och det vänstra vinkelfästet.)</span><span class="sxs-lookup"><span data-stu-id="6e68f-153">`From: Office 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="6e68f-154">`From: "Office 365"<sender@contoso.com>`(Inget blanksteg mellan det avslutande dubbla citattecknet och det vänstra vinkelfästet.)</span><span class="sxs-lookup"><span data-stu-id="6e68f-154">`From: "Office 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="6e68f-155">Undertrycka autosvar på din anpassade domän</span><span class="sxs-lookup"><span data-stu-id="6e68f-155">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="6e68f-156">Du kan inte använda `From: <>` värdet för att undertrycka autosvar.</span><span class="sxs-lookup"><span data-stu-id="6e68f-156">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="6e68f-157">I stället måste du ställa in en null MX-post för din anpassade domän.</span><span class="sxs-lookup"><span data-stu-id="6e68f-157">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="6e68f-158">Autosvar (och alla svar) undertrycks naturligtvis eftersom det inte finns någon publicerad adress som den svarande servern kan skicka meddelanden till.</span><span class="sxs-lookup"><span data-stu-id="6e68f-158">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="6e68f-159">Välj en e-postdomän som inte kan ta emot e-post.</span><span class="sxs-lookup"><span data-stu-id="6e68f-159">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="6e68f-160">Om din primära domän till exempel är contoso.com kan du välja noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6e68f-160">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="6e68f-161">Null MX-posten för den här domänen består av en enda period.</span><span class="sxs-lookup"><span data-stu-id="6e68f-161">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="6e68f-162">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="6e68f-162">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="6e68f-163">Mer information om hur du konfigurerar MX-poster finns i [Skapa DNS-poster hos alla DNS-värdar för Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="6e68f-163">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="6e68f-164">Mer information om hur du publicerar ett null MX finns i [RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="6e68f-164">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="6e68f-165">Åsidosätt från adresskontroll</span><span class="sxs-lookup"><span data-stu-id="6e68f-165">Override From address enforcement</span></span>

<span data-ttu-id="6e68f-166">Om du vill kringgå kraven på från-adress för inkommande e-post kan du använda IP Allow List (anslutningsfiltrering) eller regler för e-postflöde (kallas även transportregler) enligt beskrivningen i [Skapa listor över betrodda avsändare i Office 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="6e68f-166">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="6e68f-167">Du kan inte åsidosätta kraven för Från-adresser för utgående e-post som du skickar från Office 365.</span><span class="sxs-lookup"><span data-stu-id="6e68f-167">You can't override the From address requirements for outbound email that you send from Office 365.</span></span> <span data-ttu-id="6e68f-168">Dessutom kommer Outlook.com inte tillåta åsidosättningar av något slag, även genom stöd.</span><span class="sxs-lookup"><span data-stu-id="6e68f-168">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a><span data-ttu-id="6e68f-169">Andra sätt att förebygga och skydda mot it-brott i Office 365</span><span class="sxs-lookup"><span data-stu-id="6e68f-169">Other ways to prevent and protect against cybercrimes in Office 365</span></span>

<span data-ttu-id="6e68f-170">Mer information om hur du kan stärka din organisation mot nätfiske, skräppost, dataintrång och andra hot finns på [de 10 bästa sätten att skydda Office 365- och Microsoft 365 Business-abonnemang](../../admin/security-and-compliance/secure-your-business-data.md).</span><span class="sxs-lookup"><span data-stu-id="6e68f-170">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Office 365 and Microsoft 365 Business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>
