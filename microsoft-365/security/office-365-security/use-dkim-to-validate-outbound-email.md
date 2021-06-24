---
title: Använda DKIM för e-post i en egen domän
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
audience: ITPro
ms.topic: article
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du använder DomainKeys identifierad e-post (DKIM) med Microsoft 365 för att säkerställa att meddelanden som skickas från din anpassade domän är betrodda av mål-e-postsystemet.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e9aa3a72a36a146d121c9302a4b6cb126e765671
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082786"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a><span data-ttu-id="0dc76-103">Använda DKIM för att validera utgående e-post som skickas från din anpassade domän</span><span class="sxs-lookup"><span data-stu-id="0dc76-103">Use DKIM to validate outbound email sent from your custom domain</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0dc76-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="0dc76-104">**Applies to**</span></span>
- [<span data-ttu-id="0dc76-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0dc76-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0dc76-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="0dc76-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0dc76-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0dc76-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

 <span data-ttu-id="0dc76-108">Den här artikeln innehåller steg för att använda DomainKeys Identified Mail (DKIM) med Microsoft 365 för att säkerställa att mål-e-postsystemen litar på utgående meddelanden som skickas från din anpassade domän.</span><span class="sxs-lookup"><span data-stu-id="0dc76-108">This article lists the steps to use DomainKeys Identified Mail (DKIM) with Microsoft 365 to ensure that destination email systems trust messages sent outbound from your custom domain.</span></span>

<span data-ttu-id="0dc76-109">I den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="0dc76-109">In this article:</span></span>

- [<span data-ttu-id="0dc76-110">Hur DKIM fungerar bättre än enbart SPF för att förhindra skadlig förfalskning</span><span class="sxs-lookup"><span data-stu-id="0dc76-110">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>](#how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing)
- [<span data-ttu-id="0dc76-111">Steg för att manuellt uppgradera dina 1024-bitars nycklar till 2048-bitars DKIM-krypteringsnycklar</span><span class="sxs-lookup"><span data-stu-id="0dc76-111">Steps to manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>](#steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys)
- [<span data-ttu-id="0dc76-112">Steg för att konfigurera DKIM manuellt</span><span class="sxs-lookup"><span data-stu-id="0dc76-112">Steps to manually set up DKIM</span></span>](#steps-to-manually-set-up-dkim)
- [<span data-ttu-id="0dc76-113">Steg för att konfigurera DKIM för fler än en anpassad domän</span><span class="sxs-lookup"><span data-stu-id="0dc76-113">Steps to configure DKIM for more than one custom domain</span></span>](#to-configure-dkim-for-more-than-one-custom-domain)
- [<span data-ttu-id="0dc76-114">Inaktivera DKIM-signeringsprincipen för en anpassad domän</span><span class="sxs-lookup"><span data-stu-id="0dc76-114">Disabling the DKIM signing policy for a custom domain</span></span>](#disabling-the-dkim-signing-policy-for-a-custom-domain)
- [<span data-ttu-id="0dc76-115">Standardbeteende för DKIM och Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0dc76-115">Default behavior for DKIM and Microsoft 365</span></span>](#default-behavior-for-dkim-and-microsoft-365)
- [<span data-ttu-id="0dc76-116">Konfigurera DKIM så att en tjänst från tredje part kan skicka, eller förfalska, e-postmeddelanden för din anpassade domän</span><span class="sxs-lookup"><span data-stu-id="0dc76-116">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](#set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain)
- [<span data-ttu-id="0dc76-117">Nästa steg: När du har konfigurerat DKIM för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0dc76-117">Next steps: After you set up DKIM for Microsoft 365</span></span>](#next-steps-after-you-set-up-dkim-for-microsoft-365)

> [!NOTE]
> <span data-ttu-id="0dc76-118">Microsoft 365 konfigurerar automatiskt DKIM för dess ursprungliga ”onmicrosoft.com”-domäner.</span><span class="sxs-lookup"><span data-stu-id="0dc76-118">Microsoft 365 automatically sets up DKIM for its initial 'onmicrosoft.com' domains.</span></span> <span data-ttu-id="0dc76-119">Det innebär att du inte behöver göra något för att konfigurera DKIM för alla inledande domännamn (t. ex. litware.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="0dc76-119">That means you don't need to do anything to set up DKIM for any initial domain names (for example, litware.onmicrosoft.com).</span></span> <span data-ttu-id="0dc76-120">Mer information om domäner finns i [Vanliga frågor och svar om domäner](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span><span class="sxs-lookup"><span data-stu-id="0dc76-120">For more information about domains, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

<span data-ttu-id="0dc76-121">DKIM är en av tre autentiseringsmetoder (SPF, DKIM och DMARC) som hjälper till att förhindra angripare att skicka meddelanden som ser ut som att de kommer från din domän.</span><span class="sxs-lookup"><span data-stu-id="0dc76-121">DKIM is one of the trio of Authentication methods (SPF, DKIM and DMARC) that help prevent attackers from sending messages that look like they come from your domain.</span></span>

<span data-ttu-id="0dc76-122">Med DKIM kan du lägga till en digital signatur i utgående e-postmeddelanden i meddelanderubriken.</span><span class="sxs-lookup"><span data-stu-id="0dc76-122">DKIM lets you add a digital signature to outbound email messages in the message header.</span></span> <span data-ttu-id="0dc76-123">När du konfigurerar DKIM auktoriserar du domänen att associera, eller signera, dess namn till ett e-postmeddelande med hjälp av krypterad autentisering.</span><span class="sxs-lookup"><span data-stu-id="0dc76-123">When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message using cryptographic authentication.</span></span> <span data-ttu-id="0dc76-124">E-postsystem som får e-post från din domän kan använda denna digitala signatur för att fastställe om inkommande e-post är legitim.</span><span class="sxs-lookup"><span data-stu-id="0dc76-124">Email systems that get email from your domain can use this digital signature to help verify whether incoming email is legitimate.</span></span>

<span data-ttu-id="0dc76-125">Enkelt sagt krypterar en privat nyckel rubriken i utgående e-postmeddelanden från en domän.</span><span class="sxs-lookup"><span data-stu-id="0dc76-125">In basic, a private key encrypts the header in a domain's outgoing email.</span></span> <span data-ttu-id="0dc76-126">Den offentliga nyckeln publiceras i domänens DNS-poster och mottagande servrar kan använda den nyckeln för att avkoda signaturen.</span><span class="sxs-lookup"><span data-stu-id="0dc76-126">The public key is published in the domain's DNS records, and receiving servers can use that key to decode the signature.</span></span> <span data-ttu-id="0dc76-127">DKIM-verifiering hjälper de mottagande servrarna att bekräfta att e-posten verkligen kommer från din domän och inte från någon som *förfalskar* din domän.</span><span class="sxs-lookup"><span data-stu-id="0dc76-127">DKIM verification helps the receiving servers confirm the mail is really coming from your domain and not someone *spoofing* your domain.</span></span>

> [!TIP]
><span data-ttu-id="0dc76-p104">Du kan även välja att inte göra någonting med DKIM för din anpassade domän. Om du inte konfigurerar DKIM för din anpassade domän skapar Microsoft 365 ett privat och offentligt nyckelpar, aktiverar DKIM-signering och konfigurerar sedan standardprincipen för Microsoft 365 för din anpassade domän.</span><span class="sxs-lookup"><span data-stu-id="0dc76-p104">You can choose to do nothing about DKIM for your custom domain too. If you don't set up DKIM for your custom domain, Microsoft 365 creates a private and public key pair, enables DKIM signing, and then configures the Microsoft 365 default policy for your custom domain.</span></span>

 <span data-ttu-id="0dc76-p105">Den inbyggda DKIM-konfigurationen för Microsoft 365 är tillräcklig täckning för de flesta kunder. Men du bör manuellt konfigurera DKIM för din anpassade domän i följande fall:</span><span class="sxs-lookup"><span data-stu-id="0dc76-p105">Microsoft-365's built-in DKIM configuration is sufficient coverage for most customers. However, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>

- <span data-ttu-id="0dc76-132">Du har fler än en anpassad domän i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0dc76-132">You have more than one custom domain in Microsoft 365</span></span>
- <span data-ttu-id="0dc76-133">Du ska även konfigurera DMARC (**rekommenderas**)</span><span class="sxs-lookup"><span data-stu-id="0dc76-133">You're going to set up DMARC too (**recommended**)</span></span>
- <span data-ttu-id="0dc76-134">Du vill ha kontroll över din privata nyckel</span><span class="sxs-lookup"><span data-stu-id="0dc76-134">You want control over your private key</span></span>
- <span data-ttu-id="0dc76-135">Du vill anpassa dina CNAME-poster</span><span class="sxs-lookup"><span data-stu-id="0dc76-135">You want to customize your CNAME records</span></span>
- <span data-ttu-id="0dc76-136">Du vill konfigurera DKIM-nycklar för e-post som kommer från en domän från tredje part, t. ex. om du använder ett massutskick från tredje part.</span><span class="sxs-lookup"><span data-stu-id="0dc76-136">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a><span data-ttu-id="0dc76-137">Hur DKIM fungerar bättre än enbart SPF för att förhindra skadlig förfalskning</span><span class="sxs-lookup"><span data-stu-id="0dc76-137">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>
<span data-ttu-id="0dc76-138"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="0dc76-138"><a name="HowDKIMWorks"> </a></span></span>

<span data-ttu-id="0dc76-139">SPF lägger till information till ett meddelandekuvert, men DKIM *krypterar* en signatur i meddelanderubriken.</span><span class="sxs-lookup"><span data-stu-id="0dc76-139">SPF adds information to a message envelope but DKIM *encrypts* a signature within the message header.</span></span> <span data-ttu-id="0dc76-140">När du vidarebefordrar ett meddelande kan delar av meddelandets kuvert vara rensade av vidarebefordringsservern.</span><span class="sxs-lookup"><span data-stu-id="0dc76-140">When you forward a message, portions of that message's envelope can be stripped away by the forwarding server.</span></span> <span data-ttu-id="0dc76-141">Eftersom den digitala signaturen ligger kvar i e-postmeddelandet eftersom den är en del av e-postmeddelandets huvud fungerar DKIM även när ett meddelande har vidarebefordrats enligt följande exempel.</span><span class="sxs-lookup"><span data-stu-id="0dc76-141">Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>

![Diagram som visar ett vidarebefordrat meddelande som skickar DKIM-autentiseringen där SPF-kontrollen misslyckades](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

<span data-ttu-id="0dc76-143">Om du bara hade publicerat en SPF TXT-post för domänen i det här exemplet skulle mottagarens e-postserver ha markerat e-postmeddelandet som skräppost och genererat ett falskt positivt resultat.</span><span class="sxs-lookup"><span data-stu-id="0dc76-143">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result.</span></span> <span data-ttu-id="0dc76-144">**Tillägget av DKIM i det här scenariot minskar *falska positiva* rapporteringar av skräppost.**</span><span class="sxs-lookup"><span data-stu-id="0dc76-144">**The addition of DKIM in this scenario reduces *false positive* spam reporting.**</span></span> <span data-ttu-id="0dc76-145">Eftersom DKIM använder offentlig nyckelkryptering för att autentisera och inte bara IP-adresser anses DKIM vara en mycket starkare autentiseringsmetod än SPF.</span><span class="sxs-lookup"><span data-stu-id="0dc76-145">Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF.</span></span> <span data-ttu-id="0dc76-146">Vi rekommenderar att du använder både SPF och DKIM, och även DMARC i din distribution.</span><span class="sxs-lookup"><span data-stu-id="0dc76-146">We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>

> [!TIP]
> <span data-ttu-id="0dc76-147">DKIM använder en privat nyckel för att infoga en krypterad signatur i meddelanderubrikerna.</span><span class="sxs-lookup"><span data-stu-id="0dc76-147">DKIM uses a private key to insert an encrypted signature into the message headers.</span></span> <span data-ttu-id="0dc76-148">Signeringsdomänen, eller den utgående domänen, infogas som värdet för fältet **d =** i rubriken.</span><span class="sxs-lookup"><span data-stu-id="0dc76-148">The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header.</span></span> <span data-ttu-id="0dc76-149">Den verifierande domänen, eller mottagarens domän, använder sedan fältet **d=** för att leta upp den offentliga nyckeln från DNS och autentisera meddelandet.</span><span class="sxs-lookup"><span data-stu-id="0dc76-149">The verifying domain, or recipient's domain, then uses the **d=** field to look up the public key from DNS, and authenticate the message.</span></span> <span data-ttu-id="0dc76-150">Om meddelandet har bekräftats godkänns DKIM-kontrollen.</span><span class="sxs-lookup"><span data-stu-id="0dc76-150">If the message is verified, the DKIM check passes.</span></span>


## <a name="steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a><span data-ttu-id="0dc76-151">Uppgradera manuellt dina 1024-bitars nycklar till 2048-bitars DKIM-krypteringsnycklar</span><span class="sxs-lookup"><span data-stu-id="0dc76-151">Steps to manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>
<span data-ttu-id="0dc76-152"><a name="1024to2048DKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="0dc76-152"><a name="1024to2048DKIM"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="0dc76-153">Microsoft 365 konfigurerar automatiskt DKIM för domäner med *onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="0dc76-153">Microsoft 365 automatically sets up DKIM for *onmicrosoft.com* domains.</span></span> <span data-ttu-id="0dc76-154">Inga steg krävs för att använda DKIM för inledande domännamn (t.ex. litware.*onmicrosoft.com*).</span><span class="sxs-lookup"><span data-stu-id="0dc76-154">No steps are needed to use DKIM for any initial domain names (like litware.*onmicrosoft.com*).</span></span> <span data-ttu-id="0dc76-155">Mer information om domäner finns i [Vanliga frågor och svar om domäner](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span><span class="sxs-lookup"><span data-stu-id="0dc76-155">For more information about domains, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

<span data-ttu-id="0dc76-156">Eftersom både 1024 och 2048 bitar stöds för DKIM-nycklar visar dessa instruktioner hur du uppgraderar din 1024-bitarsnyckel till 2048 i [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0dc76-156">Since both 1024 and 2048 bitness are supported for DKIM keys, these directions will tell you how to upgrade your 1024-bit key to 2048 in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0dc76-157">Stegen nedan gäller för två användningsfall: Välj det som passar bäst för konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="0dc76-157">The steps below are for two use-cases, please choose the one that best fits your configuration.</span></span>

- <span data-ttu-id="0dc76-158">När du **redan har konfigurerat DKIM** kan du rotera bitar genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="0dc76-158">When you **already have DKIM configured**, you rotate bitness by running the following command:</span></span>

  ```powershell
  Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
  ```

  <span data-ttu-id="0dc76-159">**eller**</span><span class="sxs-lookup"><span data-stu-id="0dc76-159">**or**</span></span>

- <span data-ttu-id="0dc76-160">För en **ny implementering av DKIM**, kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="0dc76-160">For a **new implementation of DKIM**, run the following command:</span></span>

  ```powershell
  New-DkimSigningConfig -DomainName <Domain for which config is to be created> -KeySize 2048 -Enabled $true
  ```

<span data-ttu-id="0dc76-161">Håll dig ansluten till Exchange Online PowerShell för att *verifiera* konfigurationen genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="0dc76-161">Stay connected to Exchange Online PowerShell to *verify* the configuration by running the following command:</span></span>

```powershell
Get-DkimSigningConfig -Identity <Domain for which the configuration was set> | Format-List
```

> [!TIP]
> <span data-ttu-id="0dc76-162">Den här nya 2048-bitarsnyckeln träder i kraft på RotateOnDate och skickar e-postmeddelanden med 1024-bitarsnyckeln i interimversionen.</span><span class="sxs-lookup"><span data-stu-id="0dc76-162">This new 2048-bit key takes effect on the RotateOnDate, and will send emails with the 1024-bit key in the interim.</span></span> <span data-ttu-id="0dc76-163">Efter fyra dagar kan du testa igen med 2048-bitarsnyckeln (det vill säga när rotationen träder i kraft i den andra väljaren).</span><span class="sxs-lookup"><span data-stu-id="0dc76-163">After four days, you can test again with the 2048-bit key (that is, once the rotation takes effect to the second selector).</span></span>

<span data-ttu-id="0dc76-164">Om du vill rotera till den andra väljaren är dina alternativ a) att låta Microsoft 365-tjänsten rotera väljaren och uppgradera till 2048 bitar inom de kommande sex månaderna eller b) att efter fyra dagar bekräfta att 2048 bitar används och manuellt rotera den andra väljarknappen med hjälp av lämplig cmdlet ovan.</span><span class="sxs-lookup"><span data-stu-id="0dc76-164">If you want to rotate to the second selector, your options are a) let the Microsoft 365 service rotate the selector and upgrade to 2048-bitness within the next 6 months, or b) after 4 days and confirming that 2048-bitness is in use, manually rotate the second selector key by using the appropriate cmdlet listed above.</span></span>

<span data-ttu-id="0dc76-165">För detaljerad information om syntax och parametrar, se följande artiklar: [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig), [New-DkimSigningConfig](/powershell/module/exchange/new-dkimsigningconfig)och [Get-DkimSigningConfig](/powershell/module/exchange/get-dkimsigningconfig).</span><span class="sxs-lookup"><span data-stu-id="0dc76-165">For detailed syntax and parameter information, see the following articles: [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig), [New-DkimSigningConfig](/powershell/module/exchange/new-dkimsigningconfig), and [Get-DkimSigningConfig](/powershell/module/exchange/get-dkimsigningconfig).</span></span>

## <a name="steps-to-manually-set-up-dkim"></a><span data-ttu-id="0dc76-166">Steg för att konfigurera DKIM manuellt</span><span class="sxs-lookup"><span data-stu-id="0dc76-166">Steps to manually set up DKIM</span></span>
<span data-ttu-id="0dc76-167"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="0dc76-167"><a name="SetUpDKIMO365"> </a></span></span>

<span data-ttu-id="0dc76-168">Om du vill konfigurera DKIM gör du så här:</span><span class="sxs-lookup"><span data-stu-id="0dc76-168">To configure DKIM, you will complete these steps:</span></span>

- [<span data-ttu-id="0dc76-169">Publicera två CNAME-poster för din anpassade domän i DNS</span><span class="sxs-lookup"><span data-stu-id="0dc76-169">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)
- [<span data-ttu-id="0dc76-170">Aktivera DKIM-signering för din anpassade domän</span><span class="sxs-lookup"><span data-stu-id="0dc76-170">Enable DKIM signing for your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="0dc76-171">Publicera två CNAME-poster för din anpassade domän i DNS</span><span class="sxs-lookup"><span data-stu-id="0dc76-171">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="0dc76-172"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="0dc76-172"><a name="Publish2CNAME"> </a></span></span>

<span data-ttu-id="0dc76-173">För varje domän som du vill lägga till en DKIM-signatur för måste du publicera två CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="0dc76-173">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span>

> [!NOTE]
> <span data-ttu-id="0dc76-174">Har du inte läst hela artikeln kan du ha missat den här tidsbesparande PowerShell-anslutningsinformationen: [Anslut till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0dc76-174">If you haven't read the full article, you may have missed this time-saving PowerShell connection information: [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="0dc76-175">Kör följande kommandon i Exchange Online PowerShell för att skapa väljararkiv:</span><span class="sxs-lookup"><span data-stu-id="0dc76-175">Run the following commands in Exchange Online PowerShell to create the selector records:</span></span>

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

<span data-ttu-id="0dc76-176">Om du har etablerat anpassade domäner utöver den första domänen i Microsoft 365 måste du publicera två CNAME-poster för varje ytterligare domän.</span><span class="sxs-lookup"><span data-stu-id="0dc76-176">If you have provisioned custom domains in addition to the initial domain in Microsoft 365, you must publish two CNAME records for each additional domain.</span></span> <span data-ttu-id="0dc76-177">Om du har två domäner måste du publicera två ytterligare CNAME-poster och så vidare.</span><span class="sxs-lookup"><span data-stu-id="0dc76-177">So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>

<span data-ttu-id="0dc76-178">Använd följande format för CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="0dc76-178">Use the following format for the CNAME records.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0dc76-179">Om du är en av våra GCC High-kunder beräknar vi _domainGuid_ annorlunda!</span><span class="sxs-lookup"><span data-stu-id="0dc76-179">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="0dc76-180">I stället för att leta upp MX-posten för din _initialDomain_ för att beräkna _domainGuid_ beräknar vi det direkt från den anpassade domänen.</span><span class="sxs-lookup"><span data-stu-id="0dc76-180">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="0dc76-181">Om du till exempel har en anpassad domän som ”contoso.com” blir din domainGuid ”contoso-com”. Punkter ersätts med ett streck.</span><span class="sxs-lookup"><span data-stu-id="0dc76-181">For example, if your customized domain is "contoso.com" your domainGuid becomes "contoso-com", any periods are replaced with a dash.</span></span> <span data-ttu-id="0dc76-182">Oavsett vilken MX-post som initialDomain pekar på kommer du alltid att använda metoden ovan för att beräkna vilken domainGuid som ska användas i dina CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="0dc76-182">So, regardless of what MX record your initialDomain points to, you'll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

<span data-ttu-id="0dc76-183">Var:</span><span class="sxs-lookup"><span data-stu-id="0dc76-183">Where:</span></span>

- <span data-ttu-id="0dc76-184">För Microsoft 365 är väljarna alltid ”selector1” eller ”selector2”.</span><span class="sxs-lookup"><span data-stu-id="0dc76-184">For Microsoft 365, the selectors will always be "selector1" or "selector2".</span></span>
- <span data-ttu-id="0dc76-185">_domainGUID_ är samma som _domainGUID_ i den anpassade MX-posten för din domän som visas före mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="0dc76-185">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com.</span></span> <span data-ttu-id="0dc76-186">Exempel: i följande MX-post för domänen contoso.com blir din _domainGUID_ contoso-com:</span><span class="sxs-lookup"><span data-stu-id="0dc76-186">For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span>

  > <span data-ttu-id="0dc76-p115">contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0dc76-p115">contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span></span>

- <span data-ttu-id="0dc76-189">_initialDomain_ är den domän som du använde när du registrerade dig för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0dc76-189">_initialDomain_ is the domain that you used when you signed up for Microsoft 365.</span></span> <span data-ttu-id="0dc76-190">De första domänerna avslutas alltid i onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="0dc76-190">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="0dc76-191">Information om hur du fastställer din första domän finns i [Vanliga frågor och svar om domäner](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span><span class="sxs-lookup"><span data-stu-id="0dc76-191">For information about determining your initial domain, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

<span data-ttu-id="0dc76-192">Om du till exempel har en första domän med cohovineyardandwinery.onmicrosoft.com, och två egna domäner cohovineyard.com och cohowinery.co, behöver du skapa två CNAME-poster för varje ytterligare domän för att summera fyra CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="0dc76-192">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector1._domainkey
Points to address or value:    selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> <span data-ttu-id="0dc76-193">Det är viktigt att skapa den andra posten, men bara en av dem kan vara tillgänglig när du skapar den.</span><span class="sxs-lookup"><span data-stu-id="0dc76-193">It's important to create the second record, but only one of the selectors may be available at the time of creation.</span></span> <span data-ttu-id="0dc76-194">I själva verket kan den andra väljarens peka på en adress som inte har skapats än.</span><span class="sxs-lookup"><span data-stu-id="0dc76-194">In essence, the second selector might point to an address that hasn't been created yet.</span></span> <span data-ttu-id="0dc76-195">Vi rekommenderar fortfarande att du skapar den andra CNAME-posten eftersom nyckelroteringen blir smidig.</span><span class="sxs-lookup"><span data-stu-id="0dc76-195">We still recommended that you create the second CNAME record, because your key rotation will be seamless.</span></span>

### <a name="steps-to-enable-dkim-signing-for-your-custom-domain"></a><span data-ttu-id="0dc76-196">Steg för att aktivera DKIM-signering för din anpassade domän</span><span class="sxs-lookup"><span data-stu-id="0dc76-196">Steps to enable DKIM signing for your custom domain</span></span>
<span data-ttu-id="0dc76-197"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="0dc76-197"><a name="EnableDKIMinO365"> </a></span></span>

<span data-ttu-id="0dc76-198">När du har publicerat CNAME-posterna i DNS är du redo att aktivera DKIM-signering via Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0dc76-198">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Microsoft 365.</span></span> <span data-ttu-id="0dc76-199">Du kan göra det antingen via administrationscentret för Microsoft 365 eller med hjälp av PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0dc76-199">You can do this either through the Microsoft 365 admin center or by using PowerShell.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="0dc76-200">Så här aktiverar du DKIM-signering för din anpassade domän i Microsoft 365 Defender-portalen</span><span class="sxs-lookup"><span data-stu-id="0dc76-200">To enable DKIM signing for your custom domain in the Microsoft 365 Defender portal</span></span>

1. <span data-ttu-id="0dc76-201">Öppna Microsoft 365 Defender-portalen [med ditt arbets- eller skolkonto](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span><span class="sxs-lookup"><span data-stu-id="0dc76-201">Open the Microsoft 365 Defender portal [using your work or school account](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="0dc76-202">Gå till **E-post och samarbete** \> **Principer och regler** \> **Hotprinciper** \> **Regler** avsnitt \> **DKIM**.</span><span class="sxs-lookup"><span data-stu-id="0dc76-202">Go to **Email & Collaboration** \> **Policies & rules** \> **Threat policies** \> **Rules** section \> **DKIM**.</span></span> <span data-ttu-id="0dc76-203">Om du vill gå direkt till DKIM-sidan använder du <https://security.microsoft.com/dkimv2>.</span><span class="sxs-lookup"><span data-stu-id="0dc76-203">Or, to go directly to the DKIM page, use <https://security.microsoft.com/dkimv2>.</span></span>

3. <span data-ttu-id="0dc76-204">På sidan **DKIM** markerar du domänen genom att klicka på namnet.</span><span class="sxs-lookup"><span data-stu-id="0dc76-204">On the **DKIM** page, select the domain by clicking on the name.</span></span>

4. <span data-ttu-id="0dc76-205">I den utfällbara menyn med information ändrar du inställningen **Signera meddelanden för den här domänen med DKIM-signaturer** till **Aktiverad** (![Växlingsknapp på](../../media/scc-toggle-on.png))</span><span class="sxs-lookup"><span data-stu-id="0dc76-205">In the details flyout that appears, chang the **Sign messages for this domain with DKIM signatures** setting to **Enabled** (![Toggle on](../../media/scc-toggle-on.png))</span></span>

   <span data-ttu-id="0dc76-206">Klicka på **Rotera DKIM-nycklar** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="0dc76-206">When you're finished, click **Rotate DKIM keys**.</span></span>

5. <span data-ttu-id="0dc76-207">Upprepa det här steget för varje anpassad domän.</span><span class="sxs-lookup"><span data-stu-id="0dc76-207">Repeat these step for each custom domain.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="0dc76-208">För att aktivera DKIM-signering för din anpassade domän med PowerShell</span><span class="sxs-lookup"><span data-stu-id="0dc76-208">To enable DKIM signing for your custom domain by using PowerShell</span></span>

> [!IMPORTANT]
> :::image type="content" source="../../media/dkim.png" alt-text="Felet &quot;Inga DKIM-nycklar sparade för den här domänen.&quot;":::
> <span data-ttu-id="0dc76-210">Om du konfigurerar DKIM för första gången och ser felet "Inga DKIM-nycklar har sparats för den här domänen" slutför du kommandot i steg 2 nedan (till exempel `Set-DkimSigningConfig -Identity contoso.com -Enabled $true`) för att se nyckeln.</span><span class="sxs-lookup"><span data-stu-id="0dc76-210">If you are configuring DKIM for the first time and see the error 'No DKIM keys saved for this domain' complete the command in step 2 below (for example, `Set-DkimSigningConfig -Identity contoso.com -Enabled $true`) to see the key.</span></span>

1. <span data-ttu-id="0dc76-211">[Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0dc76-211">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="0dc76-212">Använd följande syntax:</span><span class="sxs-lookup"><span data-stu-id="0dc76-212">Use the following syntax:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity <Domain> -Enabled $true
   ```

   <span data-ttu-id="0dc76-213">\<Domain\> är namnet på den anpassade domän som du vill aktivera DKIM-signering för.</span><span class="sxs-lookup"><span data-stu-id="0dc76-213">\<Domain\> is the name of the custom domain that you want to enable DKIM signing for.</span></span>

   <span data-ttu-id="0dc76-214">Det här exemplet aktiverar DKIM-signering för domänen contoso.com:</span><span class="sxs-lookup"><span data-stu-id="0dc76-214">This example enables DKIM signing for the domain contoso.com:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a><span data-ttu-id="0dc76-215">Bekräfta att DKIM-signering är rätt konfigurerad för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0dc76-215">To Confirm DKIM signing is configured properly for Microsoft 365</span></span>

<span data-ttu-id="0dc76-216">Vänta några minuter innan du följer de här anvisningarna för att kontrollera att du har konfigurerat DKIM.</span><span class="sxs-lookup"><span data-stu-id="0dc76-216">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM.</span></span> <span data-ttu-id="0dc76-217">Då får DKIM-informationen om domänen tid att spridas i hela nätverket.</span><span class="sxs-lookup"><span data-stu-id="0dc76-217">This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>

- <span data-ttu-id="0dc76-218">Skicka ett meddelande från ett konto i din DKIM-aktiverade Microsoft 365-domän till ett annat e-postkonto, till exempel outlook.com eller Hotmail.com.</span><span class="sxs-lookup"><span data-stu-id="0dc76-218">Send a message from an account within your Microsoft 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>
- <span data-ttu-id="0dc76-219">Använd inte ett aol.com-konto för testningsändamål.</span><span class="sxs-lookup"><span data-stu-id="0dc76-219">Do not use an aol.com account for testing purposes.</span></span> <span data-ttu-id="0dc76-220">AOL kan hoppa över DKIM för att kontrollera om SPF-kontrollen överförs.</span><span class="sxs-lookup"><span data-stu-id="0dc76-220">AOL may skip the DKIM check if the SPF check passes.</span></span> <span data-ttu-id="0dc76-221">Det här annullerar testet.</span><span class="sxs-lookup"><span data-stu-id="0dc76-221">This will nullify your test.</span></span>
- <span data-ttu-id="0dc76-222">Öppna meddelandet och titta på rubriken.</span><span class="sxs-lookup"><span data-stu-id="0dc76-222">Open the message and look at the header.</span></span> <span data-ttu-id="0dc76-223">Information om hur du visar rubriken för meddelandet beror på vilken meddelandeklient du har.</span><span class="sxs-lookup"><span data-stu-id="0dc76-223">Instructions for viewing the header for the message will vary depending on your messaging client.</span></span> <span data-ttu-id="0dc76-224">Information om hur du visar meddelanderubriker i Outlook finns i [Visa internetmeddelandehuvud i Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span><span class="sxs-lookup"><span data-stu-id="0dc76-224">For instructions on viewing message headers in Outlook, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

  <span data-ttu-id="0dc76-p123">Det DKIM-signerade meddelandet innehåller värdnamnet och domänen som du angav när du publicerade CNAME-posterna. Meddelandet ser ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="0dc76-p123">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries. The message will look something like this example:</span></span>

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- <span data-ttu-id="0dc76-227">Håll utkik efter huvudet Authentication-Results.</span><span class="sxs-lookup"><span data-stu-id="0dc76-227">Look for the Authentication-Results header.</span></span> <span data-ttu-id="0dc76-228">Även om varje mottagande tjänst använder något annat format för att stämpla inkommande e-post ska resultatet innehålla något som liknar **DKIM=pass** eller **DKIM=OK**.</span><span class="sxs-lookup"><span data-stu-id="0dc76-228">While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span>

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a><span data-ttu-id="0dc76-229">Konfigurera DKIM för fler än en anpassad domän</span><span class="sxs-lookup"><span data-stu-id="0dc76-229">To configure DKIM for more than one custom domain</span></span>
<span data-ttu-id="0dc76-230"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="0dc76-230"><a name="DKIMMultiDomain"> </a></span></span>

<span data-ttu-id="0dc76-231">Om du senare bestämmer dig för att lägga till en egen domän och vill aktivera DKIM för den nya domänen måste du utföra stegen i den här artikeln för varje domän.</span><span class="sxs-lookup"><span data-stu-id="0dc76-231">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain.</span></span> <span data-ttu-id="0dc76-232">Slutför först alla [steg du behöver göra för att konfigurera DKIM manuellt](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span><span class="sxs-lookup"><span data-stu-id="0dc76-232">Specifically, complete all steps in [What you need to do to manually set up DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a><span data-ttu-id="0dc76-233">Inaktivera DKIM-signeringsprincipen för en anpassad domän</span><span class="sxs-lookup"><span data-stu-id="0dc76-233">Disabling the DKIM signing policy for a custom domain</span></span>
<span data-ttu-id="0dc76-234"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="0dc76-234"><a name="DisableDKIMSigningPolicy"> </a></span></span>

<span data-ttu-id="0dc76-235">När du inaktiverar signeringsprincipen inaktiveras inte DKIM fullständigt.</span><span class="sxs-lookup"><span data-stu-id="0dc76-235">Disabling the signing policy does not completely disable DKIM.</span></span> <span data-ttu-id="0dc76-236">Efter en viss tid används standardprincipen automatiskt för din domän i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0dc76-236">After a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span> <span data-ttu-id="0dc76-237">Mer information finns i [Standardbeteende för DKIM och Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span><span class="sxs-lookup"><span data-stu-id="0dc76-237">For more information, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="0dc76-238">Inaktivera DKIM-signeringsprincipen med Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0dc76-238">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="0dc76-239">[Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0dc76-239">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="0dc76-240">Kör något av följande kommandon för varje domän som du vill inaktivera DKIM-signering för.</span><span class="sxs-lookup"><span data-stu-id="0dc76-240">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity <Domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="0dc76-241">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="0dc76-241">For example:</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="0dc76-242">Eller</span><span class="sxs-lookup"><span data-stu-id="0dc76-242">Or</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   <span data-ttu-id="0dc76-243">Där _number_ är indexet för principen.</span><span class="sxs-lookup"><span data-stu-id="0dc76-243">Where _number_ is the index of the policy.</span></span> <span data-ttu-id="0dc76-244">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="0dc76-244">For example:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a><span data-ttu-id="0dc76-245">Standardbeteende för DKIM och Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0dc76-245">Default behavior for DKIM and Microsoft 365</span></span>
<span data-ttu-id="0dc76-246"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="0dc76-246"><a name="DefaultDKIMbehavior"> </a></span></span>

<span data-ttu-id="0dc76-247">Om du inte aktiverar DKIM skapar Microsoft 365 automatiskt en offentlig 1024-bitars DKIM-nyckel för din standarddomän och den tillhörande privata nyckeln som vi lagrar internt i vårt datacenter.</span><span class="sxs-lookup"><span data-stu-id="0dc76-247">If you do not enable DKIM, Microsoft 365 automatically creates a 1024-bit DKIM public key for your default domain and the associated private key which we store internally in our datacenter.</span></span> <span data-ttu-id="0dc76-248">Som standard använder Microsoft 365 en standardkonfiguration för signering för domäner som inte har någon princip.</span><span class="sxs-lookup"><span data-stu-id="0dc76-248">By default, Microsoft 365 uses a default signing configuration for domains that do not have a policy in place.</span></span> <span data-ttu-id="0dc76-249">Det innebär att om du inte konfigurerar DKIM själv kommer Microsoft 365 att använda sin standardprincip och de nycklar som skapas för att aktivera DKIM för din domän.</span><span class="sxs-lookup"><span data-stu-id="0dc76-249">This means that if you do not set up DKIM yourself, Microsoft 365 will use its default policy and keys it creates to enable DKIM for your domain.</span></span>

<span data-ttu-id="0dc76-250">Om du inaktiverar DKIM-signering efter att du har aktiverat det kommer Microsoft 365 efter en viss tid att automatiskt använda standardprincipen för din domän.</span><span class="sxs-lookup"><span data-stu-id="0dc76-250">Also, if you disable DKIM signing after enabling it, after a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span>

<span data-ttu-id="0dc76-251">I följande exempel antar vi att DKIM för fabrikam.com har aktiverats av Microsoft 365, inte av domänens administratör.</span><span class="sxs-lookup"><span data-stu-id="0dc76-251">In the following example, suppose that DKIM for fabrikam.com was enabled by Microsoft 365, not by the administrator of the domain.</span></span> <span data-ttu-id="0dc76-252">Det innebär att de nödvändiga CNAME-posterna inte finns i DNS.</span><span class="sxs-lookup"><span data-stu-id="0dc76-252">This means that the required CNAMEs do not exist in DNS.</span></span> <span data-ttu-id="0dc76-253">DKIM-signaturer för e-post från den här domänen ser ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="0dc76-253">DKIM signatures for email from this domain will look something like this:</span></span>

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

<span data-ttu-id="0dc76-254">I det här exemplet innehåller värddatornamnet och domänen värdena som CNAME pekar på om DKIM-signering för fabrikam.com har aktiverats av domänadministratören.</span><span class="sxs-lookup"><span data-stu-id="0dc76-254">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator.</span></span> <span data-ttu-id="0dc76-255">Till slut kommer alla meddelanden som skickats från Microsoft 365 att DKIM-signeras.</span><span class="sxs-lookup"><span data-stu-id="0dc76-255">Eventually, every single message sent from Microsoft 365 will be DKIM-signed.</span></span> <span data-ttu-id="0dc76-256">Om du aktiverar DKIM själv blir domänen samma som domänen i Från: adress, i det här fallet fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="0dc76-256">If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com.</span></span> <span data-ttu-id="0dc76-257">Om du inte gör det justeras det inte. I stället används din organisations första domän.</span><span class="sxs-lookup"><span data-stu-id="0dc76-257">If you don't, it will not align and instead will use your organization's initial domain.</span></span> <span data-ttu-id="0dc76-258">Information om hur du fastställer din första domän finns i [Vanliga frågor och svar om domäner](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span><span class="sxs-lookup"><span data-stu-id="0dc76-258">For information about determining your initial domain, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="0dc76-259">Konfigurera DKIM så att en tjänst från tredje part kan skicka, eller förfalska, e-postmeddelanden för din anpassade domän.</span><span class="sxs-lookup"><span data-stu-id="0dc76-259">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="0dc76-260"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="0dc76-260"><a name="SetUp3rdPartyspoof"> </a></span></span>

<span data-ttu-id="0dc76-261">Vissa leverantör av e-posttjänster, eller leverantörer av programvara som tjänst, kan konfigurera DKIM-nycklar för e-post som kommer från tjänsten.</span><span class="sxs-lookup"><span data-stu-id="0dc76-261">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service.</span></span> <span data-ttu-id="0dc76-262">Det kräver samordning mellan dig och tredje part för att du ska kunna skapa de DNS-poster som krävs.</span><span class="sxs-lookup"><span data-stu-id="0dc76-262">This requires coordination between yourself and the third-party in order to set up the necessary DNS records.</span></span> <span data-ttu-id="0dc76-263">Vissa servrar från tredje part kan ha egna CNAME-poster med olika väljare.</span><span class="sxs-lookup"><span data-stu-id="0dc76-263">Some third-party servers can have their own CNAME records with different selectors.</span></span> <span data-ttu-id="0dc76-264">Inga organisationer fungerar på exakt samma sätt.</span><span class="sxs-lookup"><span data-stu-id="0dc76-264">No two organizations do it exactly the same way.</span></span> <span data-ttu-id="0dc76-265">I stället beror processen helt på organisationen.</span><span class="sxs-lookup"><span data-stu-id="0dc76-265">Instead, the process depends entirely on the organization.</span></span>

<span data-ttu-id="0dc76-266">Ett exempelmeddelande som visar ett korrekt konfigurerat DKIM för contoso.com och bulkemailprovider.com kan se ut så här:</span><span class="sxs-lookup"><span data-stu-id="0dc76-266">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="0dc76-267">I det här exemplet för att uppnå följande resultat:</span><span class="sxs-lookup"><span data-stu-id="0dc76-267">In this example, in order to achieve this result:</span></span>

1. <span data-ttu-id="0dc76-268">E-postleverantören för massutskick gav Contoso en offentlig DKIM-nyckel.</span><span class="sxs-lookup"><span data-stu-id="0dc76-268">Bulk Email Provider gave Contoso a public DKIM key.</span></span>

2. <span data-ttu-id="0dc76-269">Contoso offentliggjorde nyckeln DKIM till dess DNS-post.</span><span class="sxs-lookup"><span data-stu-id="0dc76-269">Contoso published the DKIM key to its DNS record.</span></span>

3. <span data-ttu-id="0dc76-270">När du skickar e-post signerar e-postleverantören för massutskick nyckeln med motsvarande privata nyckel.</span><span class="sxs-lookup"><span data-stu-id="0dc76-270">When sending email, Bulk Email Provider signs the key with the corresponding private key.</span></span> <span data-ttu-id="0dc76-271">Det gör att e-postleverantören för massutskicket bifogar DKIM-signaturen i meddelandehuvudet.</span><span class="sxs-lookup"><span data-stu-id="0dc76-271">By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>

4. <span data-ttu-id="0dc76-272">Mottagande e-postsystem utför en DKIM-kontroll genom att autentisera värdet i DKIM-signaturen d=\<domain\> mot domänen i meddelandet Från: (5322.From) för meddelandet.</span><span class="sxs-lookup"><span data-stu-id="0dc76-272">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message.</span></span> <span data-ttu-id="0dc76-273">I det här exemplet överensstämmer värdena:</span><span class="sxs-lookup"><span data-stu-id="0dc76-273">In this example, the values match:</span></span>

   > <span data-ttu-id="0dc76-274">sender@**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="0dc76-274">sender@**contoso.com**</span></span>

   > <span data-ttu-id="0dc76-275">d=**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="0dc76-275">d=**contoso.com**</span></span>

## <a name="identify-domains-that-do-not-send-email"></a><span data-ttu-id="0dc76-276">Identifiera domäner som inte skickar e-post</span><span class="sxs-lookup"><span data-stu-id="0dc76-276">Identify domains that do not send email</span></span>

<span data-ttu-id="0dc76-277">Organisationer ska uttryckligen ange om en domän inte skickar e-post genom att ange `v=DKIM1; p=` i DKIM-posten för dessa domäner.</span><span class="sxs-lookup"><span data-stu-id="0dc76-277">Organizations should explicitly state if a domain does not send email by specifying `v=DKIM1; p=` in the DKIM record for those domains.</span></span> <span data-ttu-id="0dc76-278">Detta informerar om att ta emot e-postservrar att det inte finns några giltiga offentliga nycklar för domänen och att e-postmeddelanden som påstår sig komma från den domänen bör avvisas.</span><span class="sxs-lookup"><span data-stu-id="0dc76-278">This advises receiving email servers that there are no valid public keys for the domain, and any email claiming to be from that domain should be rejected.</span></span> <span data-ttu-id="0dc76-279">Du bör göra detta för varje domän och under domän med en jokertecken DKIM.</span><span class="sxs-lookup"><span data-stu-id="0dc76-279">You should do this for each domain and subdomain using a wildcard DKIM.</span></span>

<span data-ttu-id="0dc76-280">Till exempel skulle DKIM-posten se ut så här:</span><span class="sxs-lookup"><span data-stu-id="0dc76-280">For example, the DKIM record would look like this:</span></span>

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a><span data-ttu-id="0dc76-281">Nästa steg: När du har konfigurerat DKIM för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0dc76-281">Next steps: After you set up DKIM for Microsoft 365</span></span>
<span data-ttu-id="0dc76-282"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="0dc76-282"><a name="DKIMNextSteps"> </a></span></span>

<span data-ttu-id="0dc76-283">Även om DKIM har utformats för att förhindra förfalskningar fungerar DKIM bättre med SPF och DMARC.</span><span class="sxs-lookup"><span data-stu-id="0dc76-283">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="0dc76-284">När du har konfigurerat DKIM kan du konfigurera SPF om du inte redan har gjort det.</span><span class="sxs-lookup"><span data-stu-id="0dc76-284">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="0dc76-285">En introduktion till SPF finns i [Konfigurera SPF i Microsoft 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md), där du även kan konfigurera det snabbt.</span><span class="sxs-lookup"><span data-stu-id="0dc76-285">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="0dc76-286">För att få en djupare förståelse av hur Microsoft 365 använder SPF, eller om du vill felsöka eller göra icke-standarddistributioner (t.ex. hybriddistributioner), kan du börja med att läsa artikeln om [hur Microsoft 365 använder SPF (Sender Policy Framework) för att förhindra förfalskning](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="0dc76-286">For a more in-depth understanding of how Microsoft 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="0dc76-287">Därefter läser du [Använda DMARC för att validera e-post](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="0dc76-287">Next, see [Use DMARC to validate email](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="0dc76-288">[Meddelandehuvuden för antiskräppost](anti-spam-message-headers.md) innehåller syntaxen och rubrikerna som används i Microsoft 365 för DKIM-kontroller.</span><span class="sxs-lookup"><span data-stu-id="0dc76-288">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for DKIM checks.</span></span>

## <a name="more-information"></a><span data-ttu-id="0dc76-289">Mer information</span><span class="sxs-lookup"><span data-stu-id="0dc76-289">More information</span></span>

<span data-ttu-id="0dc76-290">Nyckelrotation via PowerShell [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig)</span><span class="sxs-lookup"><span data-stu-id="0dc76-290">Key rotation via PowerShell [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig)</span></span>
