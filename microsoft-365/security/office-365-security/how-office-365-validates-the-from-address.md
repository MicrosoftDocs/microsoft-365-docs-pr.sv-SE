---
title: Så här validerar Office 365 från-adressen för att förhindra nätfiske
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 10/11/2017
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
description: För att förhindra nätfiske kräver Office 365 och Outlook.com nu RFC-efterlevnad för Från:-adresser.
ms.openlocfilehash: 6459faa22f29017568747b84bbd2935aad6763d1
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812239"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a><span data-ttu-id="430f8-103">Så här validerar Office 365 från-adressen för att förhindra nätfiske</span><span class="sxs-lookup"><span data-stu-id="430f8-103">How Office 365 validates the From address to prevent phishing</span></span>

<span data-ttu-id="430f8-104">Office 365- och Outlook.com e-postkonton får allt fler nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="430f8-104">Office 365 and Outlook.com email accounts receive an increasingly large number of phishing attacks.</span></span> <span data-ttu-id="430f8-105">En teknik phishers användning är att skicka meddelanden som har värden för Från: adress som inte är kompatibla med [RFC 5322](https://tools.ietf.org/html/rfc5322).</span><span class="sxs-lookup"><span data-stu-id="430f8-105">One technique phishers use is to send messages that have values for the From: address that are not compliant with [RFC 5322](https://tools.ietf.org/html/rfc5322).</span></span> <span data-ttu-id="430f8-106">Från: adressen kallas också adressen 5322.From.</span><span class="sxs-lookup"><span data-stu-id="430f8-106">The From: address is also called the 5322.From address.</span></span> <span data-ttu-id="430f8-107">För att förhindra den här typen av nätfiske kräver Office 365 och Outlook.com meddelanden som tas emot av tjänsten för att inkludera en RFC-kompatibel Från:-adress enligt beskrivningen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="430f8-107">To help prevent this type of phishing, Office 365 and Outlook.com require messages received by the service to include an RFC-compliant From: address as described in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="430f8-108">Informationen i den här artikeln kräver att du har en grundläggande förståelse för det allmänna formatet för e-postadresser.</span><span class="sxs-lookup"><span data-stu-id="430f8-108">The information in this article requires you to have a basic understanding of the general format of email addresses.</span></span> <span data-ttu-id="430f8-109">Mer information finns i [RFC 5322](https://tools.ietf.org/html/rfc5322) (särskilt avsnitten 3.2.3, 3.4 och 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), samt [RFC 3696](https://tools.ietf.org/html/rfc3696).</span><span class="sxs-lookup"><span data-stu-id="430f8-109">For more information, see [RFC 5322](https://tools.ietf.org/html/rfc5322) (particularly sections 3.2.3, 3.4, and 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), as well as [RFC 3696](https://tools.ietf.org/html/rfc3696).</span></span> <span data-ttu-id="430f8-110">Den här artikeln handlar om policyverkställighet för adressen 5322.From.</span><span class="sxs-lookup"><span data-stu-id="430f8-110">This article is about policy enforcement for the 5322.From address.</span></span> <span data-ttu-id="430f8-111">Den här artikeln handlar inte om adressen 5321.MailFrom.</span><span class="sxs-lookup"><span data-stu-id="430f8-111">This article is not about the 5321.MailFrom address.</span></span>

<span data-ttu-id="430f8-112">Tyvärr finns det fortfarande några äldre e-postservrar på Internet som fortsätter att skicka "legitima" e-postmeddelanden som har en saknad eller felaktig från: adress.</span><span class="sxs-lookup"><span data-stu-id="430f8-112">Unfortunately, there are still some legacy email servers on the Internet that continue to send "legitimate" email messages that have a missing or malformed From: address.</span></span> <span data-ttu-id="430f8-113">Om du regelbundet får e-post från organisationer som använder dessa äldre system, uppmuntra dessa organisationer att uppdatera sina e-postservrar för att följa moderna säkerhetsstandarder.</span><span class="sxs-lookup"><span data-stu-id="430f8-113">If you regularly receive email from organizations that use these legacy systems, encourage those organizations to update their mail servers to comply with modern security standards.</span></span>

<span data-ttu-id="430f8-114">Microsoft kommer att börja rulla ut efterlevnaden av de principer som beskrivs i den här artikeln den 9 november 2017.</span><span class="sxs-lookup"><span data-stu-id="430f8-114">Microsoft will start rolling out enforcement of the policies described in this article on November 9, 2017.</span></span>

## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a><span data-ttu-id="430f8-115">Så här tillämpar Office 365 användningen av en giltig Från:-adress för att förhindra nätfiskeattacker</span><span class="sxs-lookup"><span data-stu-id="430f8-115">How Office 365 enforces the use of a valid From: address to prevent phishing attacks</span></span>

<span data-ttu-id="430f8-116">Office 365 gör ändringar i hur den tillämpar användningen av från:-adressen i meddelanden som den tar emot för att bättre skydda dig från nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="430f8-116">Office 365 is making changes to the way it enforces the use of the From: address in messages it receives in order to better protect you from phishing attacks.</span></span> <span data-ttu-id="430f8-117">I den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="430f8-117">In this article:</span></span>

- [<span data-ttu-id="430f8-118">Alla meddelanden måste innehålla en giltig Från:-adress</span><span class="sxs-lookup"><span data-stu-id="430f8-118">All messages must include a valid From: address</span></span>](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)

- [<span data-ttu-id="430f8-119">Format för från: adressen om du inte inkluderar ett visningsnamn</span><span class="sxs-lookup"><span data-stu-id="430f8-119">Format of the From: address if you don't include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatNoDisplayName)

- [<span data-ttu-id="430f8-120">Format för från: adressen om du inkluderar ett visningsnamn</span><span class="sxs-lookup"><span data-stu-id="430f8-120">Format of the From: address if you include a display name</span></span>](how-office-365-validates-the-from-address.md#FormatDisplayName)

- [<span data-ttu-id="430f8-121">Ytterligare exempel på giltiga och ogiltiga Från: adresser</span><span class="sxs-lookup"><span data-stu-id="430f8-121">Additional examples of valid and invalid From: addresses</span></span>](how-office-365-validates-the-from-address.md#Examples)

- [<span data-ttu-id="430f8-122">Undertryck automatiskt svar på din anpassade domän utan att bryta från: -principen</span><span class="sxs-lookup"><span data-stu-id="430f8-122">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>](how-office-365-validates-the-from-address.md#SuppressAutoReply)

- [<span data-ttu-id="430f8-123">Åsidosättoffice 365 från: ta itu med tvingande principer</span><span class="sxs-lookup"><span data-stu-id="430f8-123">Overriding the Office 365 From: address enforcement policy</span></span>](how-office-365-validates-the-from-address.md#Override)

- [<span data-ttu-id="430f8-124">Andra sätt att förebygga och skydda mot it-brott i Office 365</span><span class="sxs-lookup"><span data-stu-id="430f8-124">Other ways to prevent and protect against cybercrimes in Office 365</span></span>](how-office-365-validates-the-from-address.md#OtherProtection)

<span data-ttu-id="430f8-125">Skicka på uppdrag av en annan användare påverkas inte av denna förändring, för mer information, läs Terry Zink blogg "[Vad menar vi när vi hänvisar till "avsändare" av ett mail?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span><span class="sxs-lookup"><span data-stu-id="430f8-125">Sending on behalf of another user is not affected by this change, for more details, read Terry Zink's blog "[What do we mean when we refer to the 'sender' of an email?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".</span></span>

### <a name="all-messages-must-include-a-valid-from-address"></a><span data-ttu-id="430f8-126">Alla meddelanden måste innehålla en giltig Från:-adress</span><span class="sxs-lookup"><span data-stu-id="430f8-126">All messages must include a valid From: address</span></span>
<span data-ttu-id="430f8-127"><a name="MustIncludeFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="430f8-127"><a name="MustIncludeFromAddress"> </a></span></span>

<span data-ttu-id="430f8-128">Vissa automatiska meddelanden innehåller inte en från:-adress när de skickas.</span><span class="sxs-lookup"><span data-stu-id="430f8-128">Some automated messages don't include a From: address when they are sent.</span></span> <span data-ttu-id="430f8-129">Tidigare har tjänsten Outlook.com lagt till följande standardadress Från: adress till meddelandet för att göra det sluten:</span><span class="sxs-lookup"><span data-stu-id="430f8-129">In the past, when Office 365 or Outlook.com received a message without a From: address, the service added the following default From: address to the message in order to make it deliverable:</span></span>

```
From: <>
```

<span data-ttu-id="430f8-130">Från och med den 9 november 2017 kommer Office 365 att distribuera ändringar i sina datacenter och e-postservrar som kommer att tillämpa en ny regel där meddelanden utan från: adress inte längre accepteras av Office 365 eller Outlook.com.</span><span class="sxs-lookup"><span data-stu-id="430f8-130">Starting November 9, 2017, Office 365 will be rolling out changes to its datacenters and mail servers which will enforce a new rule where messages without a From: address will no longer be accepted by Office 365 or Outlook.com.</span></span> <span data-ttu-id="430f8-131">I stället måste alla meddelanden som tas emot av Office 365 redan innehålla en giltig Från:-adress.</span><span class="sxs-lookup"><span data-stu-id="430f8-131">Instead, all messages received by Office 365 must already contain a valid From: address.</span></span> <span data-ttu-id="430f8-132">Annars skickas meddelandet till mapparna Skräppost eller Borttaget i Outlook.com och Office 365.</span><span class="sxs-lookup"><span data-stu-id="430f8-132">Otherwise, the message will be sent to either the Junk Email or Deleted Items folders in Outlook.com and Office 365.</span></span>

### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a><span data-ttu-id="430f8-133">Syntaxöversikt: Giltigt format för adressen Från: för Office 365</span><span class="sxs-lookup"><span data-stu-id="430f8-133">Syntax overview: Valid format for the From: address for Office 365</span></span>
<span data-ttu-id="430f8-134"><a name="SyntaxOverviewFromAddress"> </a></span><span class="sxs-lookup"><span data-stu-id="430f8-134"><a name="SyntaxOverviewFromAddress"> </a></span></span>

<span data-ttu-id="430f8-135">Formatet för värdet för från:-adressen definieras i detalj över flera rFC:er.</span><span class="sxs-lookup"><span data-stu-id="430f8-135">The format for the value of the From: address is defined in detail across several RFCs.</span></span> <span data-ttu-id="430f8-136">Det finns många varianter på adressering och vad som kan anses giltigt eller ogiltigt.</span><span class="sxs-lookup"><span data-stu-id="430f8-136">There are many variations on addressing and what may be considered valid or invalid.</span></span> <span data-ttu-id="430f8-137">För att hålla det enkelt rekommenderar Microsoft att du använder följande format och definitioner:</span><span class="sxs-lookup"><span data-stu-id="430f8-137">To keep it simple, Microsoft recommends that you use the following format and definitions:</span></span>

```
From: "displayname " <emailaddress >
```

<span data-ttu-id="430f8-138">Där:</span><span class="sxs-lookup"><span data-stu-id="430f8-138">Where:</span></span>

- <span data-ttu-id="430f8-139">(Valfritt)  *visningsnamn* är en fras som beskriver ägaren till e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="430f8-139">(Optional)  *displayname*  is a phrase that describes the owner of the email address.</span></span> <span data-ttu-id="430f8-140">Detta kan till exempel vara ett mer användarvänligt namn för att beskriva avsändaren än namnet på postlådan.</span><span class="sxs-lookup"><span data-stu-id="430f8-140">For example, this might be a more user-friendly name to describe the sender than the name of the mailbox.</span></span> <span data-ttu-id="430f8-141">Det är valfritt att använda ett visningsnamn.</span><span class="sxs-lookup"><span data-stu-id="430f8-141">Using a display name is optional.</span></span> <span data-ttu-id="430f8-142">Om du väljer att använda ett visningsnamn rekommenderar Microsoft dock att du alltid omger det inom citattecken enligt bilden.</span><span class="sxs-lookup"><span data-stu-id="430f8-142">However, if you choose to use a display name, Microsoft recommends that you always enclose it within quotation marks as shown.</span></span>

- <span data-ttu-id="430f8-143">(Obligatoriskt)  *e-postadressen* består av:</span><span class="sxs-lookup"><span data-stu-id="430f8-143">(Required)  *emailaddress*  is made up of:</span></span>

  ```
  local-part @domain
  ```

    <span data-ttu-id="430f8-144">Där:</span><span class="sxs-lookup"><span data-stu-id="430f8-144">Where:</span></span>

  - <span data-ttu-id="430f8-145">(Obligatoriskt)  *lokal del* är en sträng som identifierar postlådan som är associerad med adressen.</span><span class="sxs-lookup"><span data-stu-id="430f8-145">(Required)  *local-part*  is a string that identifies the mailbox associated with the address.</span></span> <span data-ttu-id="430f8-146">Detta är unikt inom domänen.</span><span class="sxs-lookup"><span data-stu-id="430f8-146">This is unique within the domain.</span></span> <span data-ttu-id="430f8-147">Ofta används postlådans ägares användarnamn eller GUID som värde för den lokala delen.</span><span class="sxs-lookup"><span data-stu-id="430f8-147">Often, the mailbox owner's username or GUID is used as the value for the local-part.</span></span>

  - <span data-ttu-id="430f8-148">(Obligatoriskt)  *domänär* det fullständigt kvalificerade domännamnet (FQDN) för e-postservern som är värd för den postlåda som identifieras av den lokala delen av e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="430f8-148">(Required)  *domain*  is the fully-qualified domain name (FQDN) of the mail server that hosts the mailbox identified by the local-part of the email address.</span></span>

### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a><span data-ttu-id="430f8-149">Format för från: adressen om du inte inkluderar ett visningsnamn</span><span class="sxs-lookup"><span data-stu-id="430f8-149">Format of the From: address if you don't include a display name</span></span>
<span data-ttu-id="430f8-150"><a name="FormatNoDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="430f8-150"><a name="FormatNoDisplayName"> </a></span></span>

<span data-ttu-id="430f8-151">En korrekt formaterad från: adress som inte innehåller ett visningsnamn innehåller bara en enda e-postadress med eller utan vinkelfästen.</span><span class="sxs-lookup"><span data-stu-id="430f8-151">A properly formatted From: address that does not include a display name includes only a single email address with or without angle brackets.</span></span> <span data-ttu-id="430f8-152">Microsoft rekommenderar att du inte separerar vinkelfästena med blanksteg.</span><span class="sxs-lookup"><span data-stu-id="430f8-152">Microsoft recommends that you do not separate the angle brackets with spaces.</span></span> <span data-ttu-id="430f8-153">Dessutom ska du inte inkludera något efter e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="430f8-153">In addition, don't include anything after the email address.</span></span>

<span data-ttu-id="430f8-154">Följande exempel är giltiga:</span><span class="sxs-lookup"><span data-stu-id="430f8-154">The following examples are valid:</span></span>

```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

<span data-ttu-id="430f8-155">Följande exempel är giltigt men rekommenderas inte eftersom det innehåller blanksteg mellan vinkelfästena och e-postadressen:</span><span class="sxs-lookup"><span data-stu-id="430f8-155">The following example is valid but not recommended because it contains spaces between the angle brackets and the email address:</span></span>

```
From: < sender@contoso.com >
```

<span data-ttu-id="430f8-156">Följande exempel är ogiltigt eftersom det innehåller text efter e-postadressen:</span><span class="sxs-lookup"><span data-stu-id="430f8-156">The following example is invalid because it contains text after the email address:</span></span>

```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a><span data-ttu-id="430f8-157">Format för från: adressen om du inkluderar ett visningsnamn</span><span class="sxs-lookup"><span data-stu-id="430f8-157">Format of the From: address if you include a display name</span></span>
<span data-ttu-id="430f8-158"><a name="FormatDisplayName"> </a></span><span class="sxs-lookup"><span data-stu-id="430f8-158"><a name="FormatDisplayName"> </a></span></span>

<span data-ttu-id="430f8-159">För Från: adresser som innehåller ett värde för visningsnamnet gäller följande regler:</span><span class="sxs-lookup"><span data-stu-id="430f8-159">For From: addresses that include a value for the display name, the following rules apply:</span></span>

- <span data-ttu-id="430f8-160">Om avsändarens adress innehåller ett visningsnamn och visningsnamnet innehåller ett kommatecken måste visningsnamnet bifogas inom citattecken.</span><span class="sxs-lookup"><span data-stu-id="430f8-160">If the sender address includes a display name, and the display name includes a comma, then the display name must be enclosed within quotation marks.</span></span> <span data-ttu-id="430f8-161">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="430f8-161">For example:</span></span>

    <span data-ttu-id="430f8-162">Följande exempel är giltigt:</span><span class="sxs-lookup"><span data-stu-id="430f8-162">The following example is valid:</span></span>

  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    <span data-ttu-id="430f8-163">Följande exempel är ogiltigt:</span><span class="sxs-lookup"><span data-stu-id="430f8-163">The following example is not valid:</span></span>

  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    <span data-ttu-id="430f8-164">Om du inte omsluter visningsnamnet med citattecken om visningsnamnet innehåller ett kommatecken är ogiltigt enligt RFC 5322.</span><span class="sxs-lookup"><span data-stu-id="430f8-164">Not enclosing the display name in quotation marks if that display name includes a comma is invalid according to RFC 5322.</span></span>

    <span data-ttu-id="430f8-165">Som bästa praxis, sätta citattecken runt visningsnamnet oavsett om det finns ett kommatecken i visningsnamnet eller inte.</span><span class="sxs-lookup"><span data-stu-id="430f8-165">As a best practice, put quote marks around the display name regardless of whether or not there is a comma within the display name.</span></span>

- <span data-ttu-id="430f8-166">Om avsändarens adress innehåller ett visningsnamn måste e-postadressen bifogas inom vinkelparentes.</span><span class="sxs-lookup"><span data-stu-id="430f8-166">If the sender address includes a display name, then the email address must be enclosed within angle brackets.</span></span>

    <span data-ttu-id="430f8-167">Som bäst är att Microsoft rekommenderar att du infogar ett mellanslag mellan visningsnamnet och e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="430f8-167">As a best practice, Microsoft strongly recommends that you insert a space between the display name and the email address.</span></span>

### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a><span data-ttu-id="430f8-168">Ytterligare exempel på giltiga och ogiltiga Från: adresser</span><span class="sxs-lookup"><span data-stu-id="430f8-168">Additional examples of valid and invalid From: addresses</span></span>
<span data-ttu-id="430f8-169"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="430f8-169"><a name="Examples"> </a></span></span>

- <span data-ttu-id="430f8-170">Giltig:</span><span class="sxs-lookup"><span data-stu-id="430f8-170">Valid:</span></span>

  ```
  From: "Office 365" <sender@contoso.com>
  ```

- <span data-ttu-id="430f8-171">Ogiltig.</span><span class="sxs-lookup"><span data-stu-id="430f8-171">Invalid.</span></span> <span data-ttu-id="430f8-172">E-postadressen är inte innesluten med vinkelfästen:</span><span class="sxs-lookup"><span data-stu-id="430f8-172">The email address is not enclosed with angle brackets:</span></span>

  ```
  From: Office 365 sender@contoso.com
  ```

- <span data-ttu-id="430f8-173">Giltig, men rekommenderas inte.</span><span class="sxs-lookup"><span data-stu-id="430f8-173">Valid, but not recommended.</span></span> <span data-ttu-id="430f8-174">Visningsnamnet är inte citattecken.</span><span class="sxs-lookup"><span data-stu-id="430f8-174">The display name is not in quotes.</span></span> <span data-ttu-id="430f8-175">Som bästa praxis, alltid sätta citattecken runt visningsnamnet:</span><span class="sxs-lookup"><span data-stu-id="430f8-175">As a best practice, always put quotation marks around the display name:</span></span>

  ```
  From: Office 365 <sender@contoso.com>
  ```

- <span data-ttu-id="430f8-176">Ogiltig.</span><span class="sxs-lookup"><span data-stu-id="430f8-176">Invalid.</span></span> <span data-ttu-id="430f8-177">Allt omges inom citattecken, inte bara visningsnamnet:</span><span class="sxs-lookup"><span data-stu-id="430f8-177">Everything is enclosed within quotation marks, not just the display name:</span></span>

  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- <span data-ttu-id="430f8-178">Ogiltig.</span><span class="sxs-lookup"><span data-stu-id="430f8-178">Invalid.</span></span> <span data-ttu-id="430f8-179">Det finns inga vinkelfästen runt e-postadressen:</span><span class="sxs-lookup"><span data-stu-id="430f8-179">There are no angle brackets around the email address:</span></span>

  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- <span data-ttu-id="430f8-180">Ogiltig.</span><span class="sxs-lookup"><span data-stu-id="430f8-180">Invalid.</span></span> <span data-ttu-id="430f8-181">Det finns inget utrymme mellan visningsnamnet och vänster vinkelfäste:</span><span class="sxs-lookup"><span data-stu-id="430f8-181">There is no space between the display name and left angle bracket:</span></span>

  ```
  From: Office 365<sender@contoso.com>
  ```

- <span data-ttu-id="430f8-182">Ogiltig.</span><span class="sxs-lookup"><span data-stu-id="430f8-182">Invalid.</span></span> <span data-ttu-id="430f8-183">Det finns inget utrymme mellan det avslutande citattecknet runt visningsnamnet och den vänstra vinkelfästet.</span><span class="sxs-lookup"><span data-stu-id="430f8-183">There is no space between the closing quotation mark around the display name and the left angle bracket.</span></span>

  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a><span data-ttu-id="430f8-184">Undertryck automatiskt svar på din anpassade domän utan att bryta från: -principen</span><span class="sxs-lookup"><span data-stu-id="430f8-184">Suppress auto-replies to your custom domain without breaking the From: policy</span></span>
<span data-ttu-id="430f8-185"><a name="SuppressAutoReply"> </a></span><span class="sxs-lookup"><span data-stu-id="430f8-185"><a name="SuppressAutoReply"> </a></span></span>

<span data-ttu-id="430f8-186">Med den nya Från: principverkställighet, kan \< \> du inte längre använda Från: för att undertrycka auto-svar.</span><span class="sxs-lookup"><span data-stu-id="430f8-186">With the new From: policy enforcement, you can no longer use From: \<\> to suppress auto-replies.</span></span> <span data-ttu-id="430f8-187">I stället måste du ställa in en null MX-post för din anpassade domän.</span><span class="sxs-lookup"><span data-stu-id="430f8-187">Instead, you need to set up a null MX record for your custom domain.</span></span>

<span data-ttu-id="430f8-188">Posten e-postväxlare (MX) är en resurspost i DNS som identifierar e-postservern som tar emot e-post för domänen.</span><span class="sxs-lookup"><span data-stu-id="430f8-188">The mail exchanger (MX) record is a resource record in DNS that identifies the mail server that receives mail for your domain.</span></span> <span data-ttu-id="430f8-189">Autosvar (och alla svar) undertrycks naturligt eftersom det inte finns någon publicerad adress som svarsservern kan skicka meddelanden till.</span><span class="sxs-lookup"><span data-stu-id="430f8-189">Auto-replies (and all replies) are naturally suppressed because there is no published address to which the responding server can send messages.</span></span>

<span data-ttu-id="430f8-190">När du konfigurerar en null MX-post för din anpassade domän:</span><span class="sxs-lookup"><span data-stu-id="430f8-190">When you set up a null MX record for your custom domain:</span></span>

- <span data-ttu-id="430f8-191">Välj en domän som meddelanden ska skickas från och som inte accepterar (tar emot) e-post.</span><span class="sxs-lookup"><span data-stu-id="430f8-191">Choose a domain from which to send messages that doesn't accept (receive) email.</span></span> <span data-ttu-id="430f8-192">Om din primära domän till exempel är contoso.com kan du välja noreply.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="430f8-192">For example, if your primary domain is contoso.com, you might choose noreply.contoso.com.</span></span>

- <span data-ttu-id="430f8-193">Ställ in null MX-posten för domänen.</span><span class="sxs-lookup"><span data-stu-id="430f8-193">Set up the null MX record for your domain.</span></span> <span data-ttu-id="430f8-194">En null MX-post består till exempel av en enda punkt:</span><span class="sxs-lookup"><span data-stu-id="430f8-194">A null MX record consists of a single dot, for example:</span></span>

  ```
  noreply.contoso.com IN MX .
  ```

<span data-ttu-id="430f8-195">Mer information om hur du publicerar en null MX finns i [RFC 7505](https://tools.ietf.org/html/rfc7505).</span><span class="sxs-lookup"><span data-stu-id="430f8-195">For more information about publishing a null MX, see [RFC 7505](https://tools.ietf.org/html/rfc7505).</span></span>

### <a name="overriding-the-office-365-from-address-enforcement-policy"></a><span data-ttu-id="430f8-196">Åsidosättoffice 365 från: ta itu med tvingande principer</span><span class="sxs-lookup"><span data-stu-id="430f8-196">Overriding the Office 365 From: address enforcement policy</span></span>
<span data-ttu-id="430f8-197"><a name="Override"> </a></span><span class="sxs-lookup"><span data-stu-id="430f8-197"><a name="Override"> </a></span></span>

<span data-ttu-id="430f8-198">När lanseringen av den nya principen är klar kan du bara kringgå den här principen för inkommande e-post som du får från Office 365 med någon av följande metoder:</span><span class="sxs-lookup"><span data-stu-id="430f8-198">Once roll out of the new policy is complete, you can only bypass this policy for inbound mail you receive from Office 365 by using one of the following methods:</span></span>

- <span data-ttu-id="430f8-199">IP tillåter listor</span><span class="sxs-lookup"><span data-stu-id="430f8-199">IP allow lists</span></span>

- <span data-ttu-id="430f8-200">Regler för e-postflöde online</span><span class="sxs-lookup"><span data-stu-id="430f8-200">Exchange Online mail flow rules</span></span>

<span data-ttu-id="430f8-201">Microsoft rekommenderar starkt att man åsidosätter tillämpningen av från:-principen.</span><span class="sxs-lookup"><span data-stu-id="430f8-201">Microsoft strongly recommends against overriding the enforcement of the From: policy.</span></span> <span data-ttu-id="430f8-202">Genom att åsidosätta den här policyn kan din organisations risk för exponering för skräppost, nätfiske och andra it-brott ökas.</span><span class="sxs-lookup"><span data-stu-id="430f8-202">Overriding this policy can increase your organization's risk of exposure to spam, phishing, and other cybercrimes.</span></span>

<span data-ttu-id="430f8-203">Du kan inte åsidosätta den här principen för utgående e-post som du skickar i Office 365.</span><span class="sxs-lookup"><span data-stu-id="430f8-203">You cannot override this policy for outbound mail you send in Office 365.</span></span> <span data-ttu-id="430f8-204">Dessutom tillåter Outlook.com inte åsidosättningar av något slag, inte ens genom stöd.</span><span class="sxs-lookup"><span data-stu-id="430f8-204">In addition, Outlook.com will not allow overrides of any kind, even through support.</span></span>

### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a><span data-ttu-id="430f8-205">Andra sätt att förebygga och skydda mot it-brott i Office 365</span><span class="sxs-lookup"><span data-stu-id="430f8-205">Other ways to prevent and protect against cybercrimes in Office 365</span></span>
<span data-ttu-id="430f8-206"><a name="OtherProtection"> </a></span><span class="sxs-lookup"><span data-stu-id="430f8-206"><a name="OtherProtection"> </a></span></span>

<span data-ttu-id="430f8-207">Mer information om hur du kan stärka din organisation mot nätbrott som nätfiske, skräppost, dataintrång och andra hot finns i [Metodtips för säkerhet för Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data).</span><span class="sxs-lookup"><span data-stu-id="430f8-207">For more information on how you can strengthen your organization against cybercrimes like phishing, spamming, data breaches, and other threats, see [Security best practices for Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data).</span></span>

## <a name="related-topics"></a><span data-ttu-id="430f8-208">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="430f8-208">Related Topics</span></span>

[<span data-ttu-id="430f8-209">Meddelanden på grund av bakåtspridning och EOP</span><span class="sxs-lookup"><span data-stu-id="430f8-209">Backscatter messages and EOP</span></span>](backscatter-messages-and-eop.md)
