---
title: Så här verifierar EOP från-adressen för att förhindra nätfiske
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa om vilka typer av e-postadresser som accepteras eller nekas av Exchange Online Protection (EOP) och Outlook.com för att förhindra nätfiske.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 25fbca8fa5d264a212ac25e2035bffde0819383d
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659660"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="81a23-103">Så här verifierar EOP från-adressen för att förhindra nätfiske</span><span class="sxs-lookup"><span data-stu-id="81a23-103">How EOP validates the From address to prevent phishing</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="81a23-104">Nät fiske attacker är ett konstant hot mot alla e-postorganisationer.</span><span class="sxs-lookup"><span data-stu-id="81a23-104">Phishing attacks are a constant threat to any email organization.</span></span> <span data-ttu-id="81a23-105">Utöver [falska e-postadresser som inte är förfalskade](anti-spoofing-protection.md)använder angripare ofta värden i från-adressen som bryter mot Internet-standarden.</span><span class="sxs-lookup"><span data-stu-id="81a23-105">In addition to using [spoofed (forged) sender email addresses](anti-spoofing-protection.md), attackers often use values in the From address that violate internet standards.</span></span> <span data-ttu-id="81a23-106">För att förhindra den här typen av nätfiske måste du nu använda Exchange Online Protection (EOP) och Outlook.com inkommande meddelanden för att inkludera en RFC-kompatibel adress enligt beskrivningen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="81a23-106">To help prevent this type of phishing, Exchange Online Protection (EOP) and Outlook.com now require inbound messages to include an RFC-compliant From address as described in this article.</span></span> <span data-ttu-id="81a23-107">Denna tillämpning har Aktiver ATS i november 2017.</span><span class="sxs-lookup"><span data-stu-id="81a23-107">This enforcement was enabled in November 2017.</span></span>

<span data-ttu-id="81a23-108">**Anmärkningar**:</span><span class="sxs-lookup"><span data-stu-id="81a23-108">**Notes**:</span></span>

- <span data-ttu-id="81a23-109">Om du regelbundet får e-post från organisationer som har fel format från adresser enligt beskrivningen i den här artikeln bör du uppmuntra dessa organisationer att uppdatera sina e-postservrar för att uppfylla moderna säkerhets standarder.</span><span class="sxs-lookup"><span data-stu-id="81a23-109">If you regularly receive email from organizations that have malformed From addresses as described in this article, encourage these organizations to update their email servers to comply with modern security standards.</span></span>

- <span data-ttu-id="81a23-110">Motsvarande avsändare (används i skicka-och distributions listor) påverkas inte av de här kraven.</span><span class="sxs-lookup"><span data-stu-id="81a23-110">The related Sender field (used by Send on Behalf and mailing lists) isn't affected by these requirements.</span></span> <span data-ttu-id="81a23-111">Mer information finns i följande blogg inlägg: [Vad innebär det när vi hänvisar till "avsändaren" i ett e-postmeddelande?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span><span class="sxs-lookup"><span data-stu-id="81a23-111">For more information, see the following blog post: [What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).</span></span>

## <a name="an-overview-of-email-message-standards"></a><span data-ttu-id="81a23-112">En översikt över e-poststandarder</span><span class="sxs-lookup"><span data-stu-id="81a23-112">An overview of email message standards</span></span>

<span data-ttu-id="81a23-113">Ett SMTP-standard-e-postmeddelande består av ett *meddelandes kuvert* och meddelande innehåll.</span><span class="sxs-lookup"><span data-stu-id="81a23-113">A standard SMTP email message consists of a *message envelope* and message content.</span></span> <span data-ttu-id="81a23-114">Meddelandets kuvert innehåller information som krävs för överföring och leverans av meddelandet mellan SMTP-servrar.</span><span class="sxs-lookup"><span data-stu-id="81a23-114">The message envelope contains information that's required for transmitting and delivering the message between SMTP servers.</span></span> <span data-ttu-id="81a23-115">Meddelandets innehåll innehåller fält för meddelande rubrik (gemensamt kallat *meddelande huvudet*) och meddelande texten.</span><span class="sxs-lookup"><span data-stu-id="81a23-115">The message content contains message header fields (collectively called the *message header*) and the message body.</span></span> <span data-ttu-id="81a23-116">Meddelandets kuvert beskrivs i [rfc 5321](https://tools.ietf.org/html/rfc5321)och meddelande huvudet beskrivs i [RFC 5322](https://tools.ietf.org/html/rfc5322).</span><span class="sxs-lookup"><span data-stu-id="81a23-116">The message envelope is described in [RFC 5321](https://tools.ietf.org/html/rfc5321), and the message header is described in [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="81a23-117">Mottagarna kan aldrig se det faktiska meddelandets kuvert eftersom det är genererat av meddelande överföringen och egentligen inte ingår i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="81a23-117">Recipients never see the actual message envelope because it's generated by the message transmission process, and it isn't actually part of the message.</span></span>

- <span data-ttu-id="81a23-118">`5321.MailFrom`Adressen (kallas även för **e-post från** adress, P1 avsändare eller kuvert avsändare) är den e-postadress som används i SMTP-överföringen av meddelandet.</span><span class="sxs-lookup"><span data-stu-id="81a23-118">The `5321.MailFrom` address (also known as the **MAIL FROM** address, P1 sender, or envelope sender) is the email address that's used in the SMTP transmission of the message.</span></span> <span data-ttu-id="81a23-119">Den här e-postadressen lagras normalt i huvud fältet för **RETUR-sökväg** i meddelande huvudet (även om det är möjligt för avsändaren att ange en annan e-postadress för **RETUR-sökvägen** ).</span><span class="sxs-lookup"><span data-stu-id="81a23-119">This email address is typically recorded in the **Return-Path** header field in the message header (although it's possible for the sender to designate a different **Return-Path** email address).</span></span>

- <span data-ttu-id="81a23-120">`5322.From`(Kallas även från-adressen eller P2-avsändaren) är e-postadressen i fältet **från** huvud och är avsändarens e-postadress som visas i e-postklienter.</span><span class="sxs-lookup"><span data-stu-id="81a23-120">The `5322.From` (also known as the From address or P2 sender) is the email address in the **From** header field, and is the sender's email address that's displayed in email clients.</span></span> <span data-ttu-id="81a23-121">Från-adressen är fokus på kraven i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="81a23-121">The From address is the focus of the requirements in this article.</span></span>

<span data-ttu-id="81a23-122">Från-adressen definieras i detalj bland flera RFC: er (till exempel RFC 5322 Section 3.2.3, 3,4 och 3.4.1 och [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span><span class="sxs-lookup"><span data-stu-id="81a23-122">The From address is defined in detail across several RFCs (for example, RFC 5322 sections 3.2.3, 3.4, and 3.4.1, and [RFC 3696](https://tools.ietf.org/html/rfc3696)).</span></span> <span data-ttu-id="81a23-123">Det finns många variationer för adressering och vad som anses vara giltigt eller ogiltigt.</span><span class="sxs-lookup"><span data-stu-id="81a23-123">There are many variations on addressing and what's considered valid or invalid.</span></span> <span data-ttu-id="81a23-124">För att det ska vara enkelt rekommenderar vi följande format och definitioner:</span><span class="sxs-lookup"><span data-stu-id="81a23-124">To keep it simple, we recommend the following format and definitions:</span></span>

`From: "Display Name" <EmailAddress>`

- <span data-ttu-id="81a23-125">**Visnings namn**: en valfri fras som beskriver ägaren till e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="81a23-125">**Display Name**: An optional phrase that describes the owner of the email address.</span></span>

  - <span data-ttu-id="81a23-126">Vi rekommenderar att du alltid omger visnings namnet med citat tecken (") som visas.</span><span class="sxs-lookup"><span data-stu-id="81a23-126">We recommend that you always enclose the display name in double quotation marks (") as shown.</span></span> <span data-ttu-id="81a23-127">Om visnings namnet innehåller ett kommatecken _måste_ du omge strängen med dubbla citat tecken enligt RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="81a23-127">If the display name contains a comma, you _must_ enclose the string in double quotation marks per RFC 5322.</span></span>
  - <span data-ttu-id="81a23-128">Om from-adressen innehåller ett visnings namn måste EmailAddress-värdet omges av vinkelparenteser (< >) som visas.</span><span class="sxs-lookup"><span data-stu-id="81a23-128">If the From address includes a display name, the EmailAddress value must be enclosed in angle brackets (< >) as shown.</span></span>
  - <span data-ttu-id="81a23-129">Microsoft rekommenderar att du infogar ett blank steg mellan visnings namnet och e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="81a23-129">Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

- <span data-ttu-id="81a23-130">**EmailAddress**: en e-postadress använder formatet `local-part@domain` :</span><span class="sxs-lookup"><span data-stu-id="81a23-130">**EmailAddress**: An email address uses the format `local-part@domain`:</span></span>

  - <span data-ttu-id="81a23-131">**Local-part**: en sträng som identifierar post lådan som är kopplad till adressen.</span><span class="sxs-lookup"><span data-stu-id="81a23-131">**local-part**: A string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="81a23-132">Det här värdet är unikt i domänen.</span><span class="sxs-lookup"><span data-stu-id="81a23-132">This value is unique within the domain.</span></span> <span data-ttu-id="81a23-133">Post lådans användar namn eller GUID används ofta.</span><span class="sxs-lookup"><span data-stu-id="81a23-133">Often, the mailbox owner's username or GUID is used.</span></span>
  - <span data-ttu-id="81a23-134">**domän**: det fullständigt kvalificerade domän namnet (FQDN) för e-postservern som är värd för post lådan som identifieras av den lokala delen av e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="81a23-134">**domain**: The fully qualified domain name (FQDN) of the email server that hosts the mailbox identified by the local-part of the email address.</span></span>

  <span data-ttu-id="81a23-135">Det här är några ytterligare överväganden för värdet EmailAddress:</span><span class="sxs-lookup"><span data-stu-id="81a23-135">These are some additional considerations for the EmailAddress value:</span></span>

  - <span data-ttu-id="81a23-136">Endast en e-postadress.</span><span class="sxs-lookup"><span data-stu-id="81a23-136">Only one email address.</span></span>
  - <span data-ttu-id="81a23-137">Vi rekommenderar att du inte avgränsar vinkelparenteser med blank steg.</span><span class="sxs-lookup"><span data-stu-id="81a23-137">We recommend that you do not separate the angle brackets with spaces.</span></span>
  - <span data-ttu-id="81a23-138">Ta inte med ytterligare text efter e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="81a23-138">Don't include additional text after the email address.</span></span>

## <a name="examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="81a23-139">Exempel på giltiga och ogiltiga från adresser</span><span class="sxs-lookup"><span data-stu-id="81a23-139">Examples of valid and invalid From addresses</span></span>

<span data-ttu-id="81a23-140">Följande från e-post adresser är giltiga:</span><span class="sxs-lookup"><span data-stu-id="81a23-140">The following From email addresses are valid:</span></span>

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- <span data-ttu-id="81a23-141">`From: < sender@contoso.com >` (Rekommenderas inte eftersom det finns blank steg mellan vinkelparenteser och e-postadressen.)</span><span class="sxs-lookup"><span data-stu-id="81a23-141">`From: < sender@contoso.com >` (Not recommended because there are spaces between the angle brackets and the email address.)</span></span>

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- <span data-ttu-id="81a23-142">`From: Microsoft 365 <sender@contoso.com>` (Rekommenderas inte eftersom visnings namnet inte omges av dubbla citat tecken.)</span><span class="sxs-lookup"><span data-stu-id="81a23-142">`From: Microsoft 365 <sender@contoso.com>` (Not recommended because the display name is not enclosed in double quotation marks.)</span></span>

<span data-ttu-id="81a23-143">Följande från e-postadresser är ogiltiga:</span><span class="sxs-lookup"><span data-stu-id="81a23-143">The following From email addresses are invalid:</span></span>

- <span data-ttu-id="81a23-144">**Nej från adress**: vissa automatiska meddelanden innehåller inte en adress från.</span><span class="sxs-lookup"><span data-stu-id="81a23-144">**No From address**: Some automated messages don't include a From address.</span></span> <span data-ttu-id="81a23-145">Tidigare, när Microsoft 365 eller Outlook.com tog emot ett meddelande utan en from-adress, lades tjänsten till följande standard från: adress för att göra meddelandets slut produkt:</span><span class="sxs-lookup"><span data-stu-id="81a23-145">In the past, when Microsoft 365 or Outlook.com received a message without a From address, the service added the following default From: address to make the message deliverable:</span></span>

  `From: <>`

  <span data-ttu-id="81a23-146">Meddelanden med en tom adress är nu inte längre godkända.</span><span class="sxs-lookup"><span data-stu-id="81a23-146">Now, messages with a blank From address are no longer accepted.</span></span>

- <span data-ttu-id="81a23-147">`From: Microsoft 365 sender@contoso.com` (Visnings namnet visas, men e-postadressen är inte omgiven av vinkelparenteser.)</span><span class="sxs-lookup"><span data-stu-id="81a23-147">`From: Microsoft 365 sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="81a23-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text efter e-postadressen.)</span><span class="sxs-lookup"><span data-stu-id="81a23-148">`From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text after the email address.)</span></span>

- <span data-ttu-id="81a23-149">`From: Sender, Example <sender.example@contoso.com>` (Visnings namnet innehåller ett kommatecken, men omges inte av dubbla citat tecken.)</span><span class="sxs-lookup"><span data-stu-id="81a23-149">`From: Sender, Example <sender.example@contoso.com>` (The display name contains a comma, but is not enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="81a23-150">`From: "Microsoft 365 <sender@contoso.com>"` (Hela värdet är felaktigt omslutet med dubbla citat tecken.)</span><span class="sxs-lookup"><span data-stu-id="81a23-150">`From: "Microsoft 365 <sender@contoso.com>"` (The whole value is incorrectly enclosed in double quotation marks.)</span></span>

- <span data-ttu-id="81a23-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (Visnings namnet visas, men e-postadressen är inte omgiven av vinkelparenteser.)</span><span class="sxs-lookup"><span data-stu-id="81a23-151">`From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (The display name is present, but the email address is not enclosed in angle brackets.)</span></span>

- <span data-ttu-id="81a23-152">`From: Microsoft 365<sender@contoso.com>` (Inget blank steg mellan visnings namnet och vänster vinkel paren tes.)</span><span class="sxs-lookup"><span data-stu-id="81a23-152">`From: Microsoft 365<sender@contoso.com>` (No space between the display name and the left angle bracket.)</span></span>

- <span data-ttu-id="81a23-153">`From: "Microsoft 365"<sender@contoso.com>` (Inget blank steg mellan det avslutande dubbla citat tecknet och vänster vinkel paren tes.)</span><span class="sxs-lookup"><span data-stu-id="81a23-153">`From: "Microsoft 365"<sender@contoso.com>` (No space between the closing double quotation mark and the left angle bracket.)</span></span>

## <a name="suppress-auto-replies-to-your-custom-domain"></a><span data-ttu-id="81a23-154">Förhindra autosvar till din egen domän</span><span class="sxs-lookup"><span data-stu-id="81a23-154">Suppress auto-replies to your custom domain</span></span>

<span data-ttu-id="81a23-155">Du kan inte använda värdet `From: <>` för att dölja autosvar.</span><span class="sxs-lookup"><span data-stu-id="81a23-155">You can't use the value `From: <>` to suppress auto-replies.</span></span> <span data-ttu-id="81a23-156">Istället måste du skapa en null MX-post för din egen domän.</span><span class="sxs-lookup"><span data-stu-id="81a23-156">Instead, you need to set up a null MX record for your custom domain.</span></span> <span data-ttu-id="81a23-157">Autosvar (och alla svar) är naturligt undertryckta eftersom det inte finns någon publicerad adress som den svarande servern kan skicka meddelanden till.</span><span class="sxs-lookup"><span data-stu-id="81a23-157">Auto-replies (and all replies) are naturally suppressed because there is no published address that the responding server can send messages to.</span></span>

- <span data-ttu-id="81a23-158">Välj en e-postdomän som inte kan ta emot e-post.</span><span class="sxs-lookup"><span data-stu-id="81a23-158">Choose an email domain that can't receive email.</span></span> <span data-ttu-id="81a23-159">Om din primära domän är contoso.com kan du till exempel välja noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="81a23-159">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="81a23-160">Null MX-posten för den här domänen består av en enda period.</span><span class="sxs-lookup"><span data-stu-id="81a23-160">The null MX record for this domain consists of a single period.</span></span>

<span data-ttu-id="81a23-161">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="81a23-161">For example:</span></span>

```text
noreply.contoso.com IN MX .
```

<span data-ttu-id="81a23-162">Mer information om hur du konfigurerar MX-poster finns i [Skapa DNS-poster hos en DNS-värd för Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="81a23-162">For more information about setting up MX records, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="81a23-163">Mer information om hur du publicerar ett null MX finns i [RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="81a23-163">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

## <a name="override-from-address-enforcement"></a><span data-ttu-id="81a23-164">Åsidosätt från tvingande adress</span><span class="sxs-lookup"><span data-stu-id="81a23-164">Override From address enforcement</span></span>

<span data-ttu-id="81a23-165">Om du vill hoppa över från adress kraven för inkommande e-post kan du använda listan IP-tillåtelse (filtrering) eller regler för e-postflöde (kallas även transport regler) enligt beskrivningen i [skapa säkra avsändare i Microsoft 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="81a23-165">To bypass the From address requirements for inbound email, you can use the IP Allow List (connection filtering) or mail flow rules (also known as transport rules) as described in [Create safe sender lists in Microsoft 365](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="81a23-166">Du kan inte åsidosätta adress kraven från Microsoft 365 för utgående e-post.</span><span class="sxs-lookup"><span data-stu-id="81a23-166">You can't override the From address requirements for outbound email that you send from Microsoft 365.</span></span> <span data-ttu-id="81a23-167">Dessutom tillåter inte Outlook.com åsidosättning av något slag, till och med support.</span><span class="sxs-lookup"><span data-stu-id="81a23-167">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a><span data-ttu-id="81a23-168">Andra sätt att förhindra och skydda mot cybercrimes i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="81a23-168">Other ways to prevent and protect against cybercrimes in Microsoft 365</span></span>

<span data-ttu-id="81a23-169">Mer information om hur du kan förstärka din organisation mot nätfiske, skräp post, data brott och andra hot finns i [de 10 viktigaste sätten att skydda Microsoft 365 för företag-abonnemang](../../admin/security-and-compliance/secure-your-business-data.md).</span><span class="sxs-lookup"><span data-stu-id="81a23-169">For more information on how you can strengthen your organization against phishing, spam, data breaches, and other threats, see [Top 10 ways to secure Microsoft 365 for business plans](../../admin/security-and-compliance/secure-your-business-data.md).</span></span>
