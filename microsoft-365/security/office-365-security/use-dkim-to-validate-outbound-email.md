---
title: Använd DKIM för e-post i din anpassade domän i Office 365, 2048-bitars, 1024-bitars, steg, hur den fungerar, SPF, DMARC
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/8/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
description: 'Sammanfattning: i den här artikeln beskrivs hur du använder DomainKeys Identified Mail (DKIM) med Office 365 för att säkerställa att mål-e-postsystemen litar på meddelanden som skickas från din anpassade domän.'
ms.openlocfilehash: d76c31c6a3f0ce1550f0259ee40996189b60cb79
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42811473"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain-in-office-365"></a><span data-ttu-id="ee425-103">Använd DKIM för att validera utgående e-post som skickas från din egna domän i Office 365</span><span class="sxs-lookup"><span data-stu-id="ee425-103">Use DKIM to validate outbound email sent from your custom domain in Office 365</span></span>

 <span data-ttu-id="ee425-104">**Sammanfattning:** i den här artikeln beskrivs hur du använder DomainKeys Identified Mail (DKIM) med Office 365 för att säkerställa att mål-e-postsystemen litar på utgående meddelanden som skickas från din anpassade domän.</span><span class="sxs-lookup"><span data-stu-id="ee425-104">**Summary:** This article describes how you use DomainKeys Identified Mail (DKIM) with Office 365 to ensure that destination email systems trust messages sent outbound from your custom domain.</span></span>

<span data-ttu-id="ee425-105">Du bör använda DKIM tillsammans med SPF och DMARC för att förhindra att förfalskare skickar meddelanden som ser ut som att de kommer från din domän.</span><span class="sxs-lookup"><span data-stu-id="ee425-105">You should use DKIM in addition to SPF and DMARC to help prevent spoofers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="ee425-106">Med DKIM kan du lägga till en digital signatur i utgående e-postmeddelanden i meddelandehuvudet.</span><span class="sxs-lookup"><span data-stu-id="ee425-106">DKIM lets you add a digital signature to outbound email messages in the message header.</span></span> <span data-ttu-id="ee425-107">Det kan vara komplicerat, men det är det faktiskt inte.</span><span class="sxs-lookup"><span data-stu-id="ee425-107">It may sound complicated, but it's really not.</span></span> <span data-ttu-id="ee425-108">När du konfigurerar DKIM verifierar du att din domän ska kopplas till ett e-postmeddelande med hjälp av krypterad autentisering.</span><span class="sxs-lookup"><span data-stu-id="ee425-108">When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message by using cryptographic authentication.</span></span> <span data-ttu-id="ee425-109">E-postsystem som får e-post från din domän använder denna digitala signatur för att fastställa om inkommande e-post som tas emot är legitim.</span><span class="sxs-lookup"><span data-stu-id="ee425-109">Email systems that receive email from your domain can use this digital signature to help determine if incoming email that they receive is legitimate.</span></span>

<span data-ttu-id="ee425-110">I stort sett använder du en privat nyckel för att kryptera huvudet i domänens utgående e-post.</span><span class="sxs-lookup"><span data-stu-id="ee425-110">Basically, you use a private key to encrypt the header in your domain's outgoing email.</span></span> <span data-ttu-id="ee425-111">Du publicerar en offentlig nyckel i din domäns DNS-poster som tar emot servrar som sedan kan användas för att avkoda signaturen.</span><span class="sxs-lookup"><span data-stu-id="ee425-111">You publish a public key to your domain's DNS records that receiving servers can then use to decode the signature.</span></span> <span data-ttu-id="ee425-112">De använder en offentlig nyckel för att kontrollera att de verkligen kommer från dig och att de inte kommer från någon som *förfalskar* din domän.</span><span class="sxs-lookup"><span data-stu-id="ee425-112">They use the public key to verify that the messages are really coming from you and not coming from someone *spoofing* your domain.</span></span>

<span data-ttu-id="ee425-113">I Office 365 konfigureras automatiskt DKIM för dess ursprungliga ”onmicrosoft.com”-domäner.</span><span class="sxs-lookup"><span data-stu-id="ee425-113">Office 365 automatically sets up DKIM for its initial 'onmicrosoft.com' domains.</span></span> <span data-ttu-id="ee425-114">Det innebär att du inte behöver göra något för att konfigurera DKIM för alla inledande domännamn (t. ex. litware.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="ee425-114">That means you don't need to do anything to set up DKIM for any initial domain names (for example, litware.onmicrosoft.com).</span></span> <span data-ttu-id="ee425-115">Mer information om domäner finns i [Vanliga frågor och svar om domäner](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="ee425-115">For more information about domains, see [Domains FAQ](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="ee425-116">Du kan också välja att inte göra något med DKIM för din anpassade domän.</span><span class="sxs-lookup"><span data-stu-id="ee425-116">You can choose to do nothing about DKIM for your custom domain too.</span></span> <span data-ttu-id="ee425-117">Om du inte konfigurerar DKIM för din anpassade domän skapar Office 365 ett privat och offentligt nyckelpar, aktiverar DKIM-signering och konfigurerar sedan standardprincipen för Office 365 för din anpassade domän.</span><span class="sxs-lookup"><span data-stu-id="ee425-117">If you don't set up DKIM for your custom domain, Office 365 creates a private and public key pair, enables DKIM signing, and then configures the Office 365 default policy for your custom domain.</span></span> <span data-ttu-id="ee425-118">Även om det är tillräcklig täckning för de flesta Office 365-kunder ska du manuellt konfigurera DKIM för din anpassade domän i följande fall:</span><span class="sxs-lookup"><span data-stu-id="ee425-118">While this is sufficient coverage for most Office 365 customers, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>

- <span data-ttu-id="ee425-119">Du har fler än en anpassad domän i Office 365</span><span class="sxs-lookup"><span data-stu-id="ee425-119">You have more than one custom domain in Office 365</span></span>

- <span data-ttu-id="ee425-120">Du ska även konfigurera DMARC (rekommenderas)</span><span class="sxs-lookup"><span data-stu-id="ee425-120">You're going to set up DMARC too (recommended)</span></span>

- <span data-ttu-id="ee425-121">Du vill ha kontroll över din privata nyckel</span><span class="sxs-lookup"><span data-stu-id="ee425-121">You want control over your private key</span></span>

- <span data-ttu-id="ee425-122">Du vill anpassa dina CNAME-poster</span><span class="sxs-lookup"><span data-stu-id="ee425-122">You want to customize your CNAME records</span></span>

- <span data-ttu-id="ee425-123">Du vill konfigurera DKIM-nycklar för e-post som kommer från en domän från tredje part, t. ex. om du använder ett massutskick från tredje part.</span><span class="sxs-lookup"><span data-stu-id="ee425-123">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>

<span data-ttu-id="ee425-124">I den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="ee425-124">In this article:</span></span>

- [<span data-ttu-id="ee425-125">Hur DKIM fungerar bättre än enbart SPF för att förhindra skadlig förfalskning i Office 365</span><span class="sxs-lookup"><span data-stu-id="ee425-125">How DKIM works better than SPF alone to prevent malicious spoofing in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [<span data-ttu-id="ee425-126">Uppgradera manuellt dina 1024-bitars nycklar till 2048-bitars DKIM-krypteringsnycklar</span><span class="sxs-lookup"><span data-stu-id="ee425-126">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [<span data-ttu-id="ee425-127">Steg du behöver göra för att konfigurera DKIM manuellt i Office 365</span><span class="sxs-lookup"><span data-stu-id="ee425-127">Steps you need to do to manually set up DKIM in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [<span data-ttu-id="ee425-128">Konfigurera fler än en anpassad domän i Office 365</span><span class="sxs-lookup"><span data-stu-id="ee425-128">To configure DKIM for more than one custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [<span data-ttu-id="ee425-129">Inaktivera DKIM-signeringsprincipen för en anpassad domän i Office 365</span><span class="sxs-lookup"><span data-stu-id="ee425-129">Disabling the DKIM signing policy for a custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [<span data-ttu-id="ee425-130">Standardbeteende för DKIM och Office 365</span><span class="sxs-lookup"><span data-stu-id="ee425-130">Default behavior for DKIM and Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [<span data-ttu-id="ee425-131">Konfigurera DKIM så att en tjänst från tredje part kan skicka, eller förfalska, e-postmeddelanden för din anpassade domän</span><span class="sxs-lookup"><span data-stu-id="ee425-131">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [<span data-ttu-id="ee425-132">Nästa steg: När du har konfigurerat DKIM för Office 365</span><span class="sxs-lookup"><span data-stu-id="ee425-132">Next steps: After you set up DKIM for Office 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing-in-office-365"></a><span data-ttu-id="ee425-133">Hur DKIM fungerar bättre än enbart SPF för att förhindra skadlig förfalskning i Office 365</span><span class="sxs-lookup"><span data-stu-id="ee425-133">How DKIM works better than SPF alone to prevent malicious spoofing in Office 365</span></span>
<span data-ttu-id="ee425-134"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="ee425-134"><a name="HowDKIMWorks"> </a></span></span>

<span data-ttu-id="ee425-135">SPF lägger till information i ett meddelandekuvert, men DKIM krypterar faktiskt en signatur i meddelandehuvudet.</span><span class="sxs-lookup"><span data-stu-id="ee425-135">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header.</span></span> <span data-ttu-id="ee425-136">När du vidarebefordrar ett meddelande kan delar av meddelandets kuvert vara rensade av vidarebefordringsservern.</span><span class="sxs-lookup"><span data-stu-id="ee425-136">When you forward a message, portions of that message's envelope can be stripped away by the forwarding server.</span></span> <span data-ttu-id="ee425-137">Eftersom den digitala signaturen ligger kvar i e-postmeddelandet eftersom den är en del av e-postmeddelandets huvud fungerar DKIM även när ett meddelande har vidarebefordrats enligt följande exempel.</span><span class="sxs-lookup"><span data-stu-id="ee425-137">Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>

![Diagram som visar ett vidarebefordrat meddelande som skickar DKIM-autentiseringen där SPF-kontrollen misslyckades](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

<span data-ttu-id="ee425-139">Om du bara hade publicerat en SPF TXT-post för domänen i det här exemplet skulle mottagarens e-postserver ha markerat e-postmeddelandet som skräppost och genererat ett falskt positivt resultat.</span><span class="sxs-lookup"><span data-stu-id="ee425-139">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result.</span></span> <span data-ttu-id="ee425-140">Om du lägger till DKIM i det här scenariot minskas falska positiva skräppostrapporter.</span><span class="sxs-lookup"><span data-stu-id="ee425-140">The addition of DKIM in this scenario reduces false positive spam reporting.</span></span> <span data-ttu-id="ee425-141">Eftersom DKIM använder offentlig nyckelkryptering för att autentisera och inte bara IP-adresser anses DKIM vara en mycket starkare autentiseringsmetod än SPF.</span><span class="sxs-lookup"><span data-stu-id="ee425-141">Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF.</span></span> <span data-ttu-id="ee425-142">Vi rekommenderar att du använder både SPF och DKIM, och även DMARC i din distribution.</span><span class="sxs-lookup"><span data-stu-id="ee425-142">We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>

<span data-ttu-id="ee425-143">Nitty Gritty: DKIM använder en privat nyckel för att infoga en krypterad signatur i meddelandehuvudena.</span><span class="sxs-lookup"><span data-stu-id="ee425-143">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers.</span></span> <span data-ttu-id="ee425-144">Signeringsdomänen, eller den utgående domänen, infogas som värdet för fältet **d =** i huvudet.</span><span class="sxs-lookup"><span data-stu-id="ee425-144">The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header.</span></span> <span data-ttu-id="ee425-145">Den verifierade domänen, eller mottagarens domän använder sedan fältet **d=** för att leta upp den offentliga nyckeln från DNS och autentisera meddelandet.</span><span class="sxs-lookup"><span data-stu-id="ee425-145">The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message.</span></span> <span data-ttu-id="ee425-146">Om meddelandet har bekräftats godkänns DKIM-kontrollen.</span><span class="sxs-lookup"><span data-stu-id="ee425-146">If the message is verified, the DKIM check passes.</span></span>

## <a name="manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a><span data-ttu-id="ee425-147">Uppgradera manuellt dina 1024-bitars nycklar till 2048-bitars DKIM-krypteringsnycklar</span><span class="sxs-lookup"><span data-stu-id="ee425-147">Manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>
<span data-ttu-id="ee425-148"><a name="1024to2048DKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="ee425-148"><a name="1024to2048DKIM"> </a></span></span>

<span data-ttu-id="ee425-149">Eftersom både 1024 och 2048 bitar stöds för DKIM-nycklar visar riktningarna hur du ska uppgradera din 1024-bitarsnyckel till 2048.</span><span class="sxs-lookup"><span data-stu-id="ee425-149">Since both 1024 and 2048 bitness are supported for DKIM keys, these directions will tell you how to upgrade your 1024-bit key to 2048.</span></span> <span data-ttu-id="ee425-150">Stegen nedan gäller för två användningsfall: Välj det som passar bäst för konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="ee425-150">The steps below are for two use-cases, please choose the one that best fits your configuration.</span></span>

1. <span data-ttu-id="ee425-151">När du **redan har konfigurerat DKIM** kan du rotera bitar enligt följande:</span><span class="sxs-lookup"><span data-stu-id="ee425-151">When you **already have DKIM configured**, you rotate bitness as follows:</span></span>
    1. <span data-ttu-id="ee425-152">[Ansluta till Office 365-arbetsbelastningar via PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="ee425-152">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="ee425-153">(Cmdleten kommer från Exchange Online.)</span><span class="sxs-lookup"><span data-stu-id="ee425-153">(The cmdlet comes from Exchange Online.)</span></span>
    1. <span data-ttu-id="ee425-154">Kör sedan följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ee425-154">And then execute the following cmdlet:</span></span>

<span data-ttu-id="ee425-155">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}`</span><span class="sxs-lookup"><span data-stu-id="ee425-155">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}`</span></span>

1. <span data-ttu-id="ee425-156">Eller för en **ny implementation av DKIM**:</span><span class="sxs-lookup"><span data-stu-id="ee425-156">Or for a **new implementation of DKIM**:</span></span>
    1. <span data-ttu-id="ee425-157">[Ansluta till Office 365-arbetsbelastningar via PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="ee425-157">[Connect to Office 365 workloads via PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span> <span data-ttu-id="ee425-158">(Det här är en Exchange Online-cmdlet.)</span><span class="sxs-lookup"><span data-stu-id="ee425-158">(This is an Exchange Online cmdlet.)</span></span>
    1. <span data-ttu-id="ee425-159">Kör följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ee425-159">Execute the following cmdlet:</span></span>

<span data-ttu-id="ee425-160">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True`</span><span class="sxs-lookup"><span data-stu-id="ee425-160">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `New-DkimSigningConfig -DomainName {Domain for which config is to be created} -KeySize 2048 -Enabled $True`</span></span>

<span data-ttu-id="ee425-161">Fortsätt att vara ansluten till Office 365 för att *verifiera* konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="ee425-161">Stay connected to Office 365 to *verify* the configuration.</span></span>

2. <span data-ttu-id="ee425-162">Kör cmdleten:</span><span class="sxs-lookup"><span data-stu-id="ee425-162">Execute the cmdlet:</span></span>

<span data-ttu-id="ee425-163">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `Get-DkimSigningConfig | fl`</span><span class="sxs-lookup"><span data-stu-id="ee425-163">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; `Get-DkimSigningConfig | fl`</span></span>

> [!TIP]
><span data-ttu-id="ee425-164">Den här nya 2048-bitarsnyckeln träder i kraft på RotateOnDate och skickar e-postmeddelanden med 1024-bitarsnyckeln i interimversionen.</span><span class="sxs-lookup"><span data-stu-id="ee425-164">This new 2048-bit key takes effect on the RotateOnDate, and will send emails with the 1024-bit key in the interim.</span></span> <span data-ttu-id="ee425-165">Efter fyra dagar kan du testa igen med 2048-bitarsnyckeln (det vill säga när rotationen träder i kraft i den andra väljaren).</span><span class="sxs-lookup"><span data-stu-id="ee425-165">After four days, you can test again with the 2048-bit key (that is, once the rotation takes effect to the second selector).</span></span>

<span data-ttu-id="ee425-166">Om du vill rotera till den andra väljaren är dina alternativ a) att låta Office 365-tjänsten rotera väljaren och uppgradera till 2048 bitar inom de kommande sex månaderna och b) att efter fyra dagar bekräfta att 2048-bitar används, manuellt rotera den andra väljarknappen med hjälp av lämplig cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ee425-166">If you want to rotate to the second selector, your options are a) let the Office 365 service rotate the selector and upgrade to 2048-bitness within the next 6 months, or b) after 4 days and confirming that 2048-bitness is in use, manually rotate the second selector key by using the appropriate cmdlet listed above.</span></span>

## <a name="steps-you-need-to-do-to-manually-set-up-dkim-in-office-365"></a><span data-ttu-id="ee425-167">Steg du behöver göra för att konfigurera DKIM manuellt i Office 365</span><span class="sxs-lookup"><span data-stu-id="ee425-167">Steps you need to do to manually set up DKIM in Office 365</span></span>
<span data-ttu-id="ee425-168"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="ee425-168"><a name="SetUpDKIMO365"> </a></span></span>

<span data-ttu-id="ee425-169">Om du vill konfigurera DKIM gör du så här:</span><span class="sxs-lookup"><span data-stu-id="ee425-169">To configure DKIM, you will complete these steps:</span></span>

- [<span data-ttu-id="ee425-170">Publicera två CNAME-poster för din anpassade domän i DNS</span><span class="sxs-lookup"><span data-stu-id="ee425-170">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [<span data-ttu-id="ee425-171">Aktivera DKIM-signering för din anpassade domän i Office 365</span><span class="sxs-lookup"><span data-stu-id="ee425-171">Enable DKIM signing for your custom domain in Office 365</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="ee425-172">Publicera två CNAME-poster för din anpassade domän i DNS</span><span class="sxs-lookup"><span data-stu-id="ee425-172">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="ee425-173"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="ee425-173"><a name="Publish2CNAME"> </a></span></span>

<span data-ttu-id="ee425-174">För varje domän som du vill lägga till en DKIM-signatur för måste du publicera två CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="ee425-174">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span>

<span data-ttu-id="ee425-175">Kör följande kommandon för att skapa väljarposterna:</span><span class="sxs-lookup"><span data-stu-id="ee425-175">Run the following commands to create the selector records:</span></span>

```powershell
    New-DkimSigningConfig -DomainName <domain> -Enabled $false
    Get-DkimSigningConfig -Identity <domain> | fl Selector1CNAME, Selector2CNAME
```

<span data-ttu-id="ee425-176">Skapa CNAME-referenser i Get-DkimSigningConfig-utdata</span><span class="sxs-lookup"><span data-stu-id="ee425-176">Create CNAMEs referenced in Get-DkimSigningConfig output</span></span>

```powershell
    Set-DkimSigningConfig -Identity <domain> -Enabled $true
```

<span data-ttu-id="ee425-177">I Office 365 utförs automatisk nyckelrotation med de två poster som du skapar.</span><span class="sxs-lookup"><span data-stu-id="ee425-177">Office 365 performs automatic key rotation using the two records that you establish.</span></span> <span data-ttu-id="ee425-178">Om du har etablerade egna domäner förutom den första domänen i Office 365 måste du publicera två CNAME-poster för varje ytterligare domän.</span><span class="sxs-lookup"><span data-stu-id="ee425-178">If you have provisioned custom domains in addition to the initial domain in Office 365, you must publish two CNAME records for each additional domain.</span></span> <span data-ttu-id="ee425-179">Om du har två domäner måste du publicera två ytterligare CNAME-poster och så vidare.</span><span class="sxs-lookup"><span data-stu-id="ee425-179">So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>

<span data-ttu-id="ee425-180">Använd följande format för CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="ee425-180">Use the following format for the CNAME records.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ee425-181">Om du är en av våra GCC High-kunder beräknar vi _domainGuid_ annorlunda!</span><span class="sxs-lookup"><span data-stu-id="ee425-181">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="ee425-182">I stället för att leta upp MX-posten för din _initialDomain_ för att beräkna _domainGuid_ beräknar vi det direkt från den anpassade domänen.</span><span class="sxs-lookup"><span data-stu-id="ee425-182">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="ee425-183">Om du till exempel har en anpassad domän som ”contoso.com” blir din domainGuid ”contoso-com”. Punkter ersätts med ett streck.</span><span class="sxs-lookup"><span data-stu-id="ee425-183">For example, if your customized domain is "contoso.com" your domainGuid becomes "contoso-com", any periods are replaced with a dash.</span></span> <span data-ttu-id="ee425-184">Oavsett vilken MX-post som initialDomain pekar på kommer du alltid att använda metoden ovan för att beräkna vilken domainGuid som ska användas i dina CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="ee425-184">So, regardless of what MX record your initialDomain points to, you'll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

```text
Host name:          selector1._domainkey
Points to address or value: selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

<span data-ttu-id="ee425-185">Var:</span><span class="sxs-lookup"><span data-stu-id="ee425-185">Where:</span></span>

- <span data-ttu-id="ee425-186">För Office 365 är väljarna alltid ”selector1” eller ”selector2”.</span><span class="sxs-lookup"><span data-stu-id="ee425-186">For Office 365, the selectors will always be "selector1" or "selector2".</span></span>

- <span data-ttu-id="ee425-187">_domainGUID_ är samma som _domainGUID_ i den anpassade MX-posten för din domän som visas före mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="ee425-187">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com.</span></span> <span data-ttu-id="ee425-188">Exempel: i följande MX-post för domänen contoso.com blir din _domainGUID_ contoso-com:</span><span class="sxs-lookup"><span data-stu-id="ee425-188">For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span>

    ```text
    contoso.com.  3600  IN  MX   5 contoso-com.mail.protection.outlook.com
    ```

- <span data-ttu-id="ee425-189">_initialDomain_ är den domän som du använde när du registrerade dig för Office 365.</span><span class="sxs-lookup"><span data-stu-id="ee425-189">_initialDomain_ is the domain that you used when you signed up for Office 365.</span></span> <span data-ttu-id="ee425-190">De första domänerna avslutas alltid i onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="ee425-190">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="ee425-191">Information om hur du fastställer din första domän finns i [Vanliga frågor och svar om domäner](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="ee425-191">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

<span data-ttu-id="ee425-192">Om du till exempel har en första domän med cohovineyardandwinery.onmicrosoft.com, och två egna domäner cohovineyard.com och cohowinery.co, behöver du skapa två CNAME-poster för varje ytterligare domän för att summera fyra CNAME-poster.</span><span class="sxs-lookup"><span data-stu-id="ee425-192">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>

```text
Host name:          selector1._domainkey
Points to address or value: selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector1._domainkey
Points to address or value: selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:          selector2._domainkey
Points to address or value: selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> <span data-ttu-id="ee425-193">Det är viktigt att skapa den andra posten, men bara en av dem kan vara tillgänglig när du skapar den.</span><span class="sxs-lookup"><span data-stu-id="ee425-193">It's important to create the second record, but only one of the selectors may be available at the time of creation.</span></span> <span data-ttu-id="ee425-194">I själva verket kan den andra väljarens peka på en adress som inte har skapats än.</span><span class="sxs-lookup"><span data-stu-id="ee425-194">In essence, the second selector might point to an address that hasn't been created yet.</span></span> <span data-ttu-id="ee425-195">Vi rekommenderar fortfarande att du skapar den andra CNAME-posten eftersom nyckelroteringen blir smidig och du inte behöver göra några manuella steg själv.</span><span class="sxs-lookup"><span data-stu-id="ee425-195">We still recommended that you create the second CNAME record, because your key rotation will be seamless and you won't need to do any manual steps yourself.</span></span>

### <a name="enable-dkim-signing-for-your-custom-domain-in-office-365"></a><span data-ttu-id="ee425-196">Aktivera DKIM-signering för din anpassade domän i Office 365</span><span class="sxs-lookup"><span data-stu-id="ee425-196">Enable DKIM signing for your custom domain in Office 365</span></span>
<span data-ttu-id="ee425-197"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="ee425-197"><a name="EnableDKIMinO365"> </a></span></span>

<span data-ttu-id="ee425-198">När du har publicerat CNAME-posterna i DNS är du redo att aktivera DKIM-signering via Office 365.</span><span class="sxs-lookup"><span data-stu-id="ee425-198">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Office 365.</span></span> <span data-ttu-id="ee425-199">Du kan göra det antingen via administrationscentret för Microsoft 365 eller med hjälp av PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee425-199">You can do this either through the Microsoft 365 admin center or by using PowerShell.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a><span data-ttu-id="ee425-200">Aktivera DKIM-signering för din anpassade domän via administrationscentret</span><span class="sxs-lookup"><span data-stu-id="ee425-200">To enable DKIM signing for your custom domain through the admin center</span></span>

1. <span data-ttu-id="ee425-201">[Logga in på Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) med ditt konto för arbetet eller skolan.</span><span class="sxs-lookup"><span data-stu-id="ee425-201">[Sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="ee425-202">Välj ikonen för startprogrammet i det övre vänstra hörnet, och välj sedan **Admin**.</span><span class="sxs-lookup"><span data-stu-id="ee425-202">Select the app launcher icon in the upper-left and choose **Admin**.</span></span>

3. <span data-ttu-id="ee425-203">I den nedre vänstra navigeringen expanderar du **Administratör** och väljer **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="ee425-203">In the lower-left navigation, expand **Admin** and choose **Exchange**.</span></span>

4. <span data-ttu-id="ee425-204">Gå till **Skydd** \> **DKIM**.</span><span class="sxs-lookup"><span data-stu-id="ee425-204">Go to **Protection** \> **dkim**.</span></span>

5. <span data-ttu-id="ee425-205">Välj domänen som du vill aktivera DKIM för och sedan går du till **Sign messages for this domain with DKIM signatures** (Signera meddelanden för domänen ed DKIM-signaturer) och väljer **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="ee425-205">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**.</span></span> <span data-ttu-id="ee425-206">Upprepa det här steget för varje anpassad domän.</span><span class="sxs-lookup"><span data-stu-id="ee425-206">Repeat this step for each custom domain.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="ee425-207">För att aktivera DKIM-signering för din anpassade domän med PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee425-207">To enable DKIM signing for your custom domain by using PowerShell</span></span>

1. <span data-ttu-id="ee425-208">[Ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ee425-208">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="ee425-209">Kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="ee425-209">Run the following command:</span></span>

    ```powershell
    Set-DkimSigningConfig -Identity <domain> -Enabled $true
    ```

   <span data-ttu-id="ee425-210">Här är _domänen_ namnet på den anpassade domän som du vill aktivera DKIM-signering för.</span><span class="sxs-lookup"><span data-stu-id="ee425-210">Where _domain_ is the name of the custom domain that you want to enable DKIM signing for.</span></span>

   <span data-ttu-id="ee425-211">Till exempel för domänen contoso.com:</span><span class="sxs-lookup"><span data-stu-id="ee425-211">For example, for the domain contoso.com:</span></span>

    ```powershell
    Set-DkimSigningConfig -Identity contoso.com -Enabled $true
    ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-office-365"></a><span data-ttu-id="ee425-212">Bekräfta att DKIM-signering är rätt konfigurerad för Office 365</span><span class="sxs-lookup"><span data-stu-id="ee425-212">To Confirm DKIM signing is configured properly for Office 365</span></span>

<span data-ttu-id="ee425-213">Vänta några minuter innan du följer de här anvisningarna för att kontrollera att du har konfigurerat DKIM.</span><span class="sxs-lookup"><span data-stu-id="ee425-213">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM.</span></span> <span data-ttu-id="ee425-214">Då får DKIM-informationen om domänen tid att spridas i hela nätverket.</span><span class="sxs-lookup"><span data-stu-id="ee425-214">This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>

- <span data-ttu-id="ee425-215">Skicka ett meddelande från ett konto i din Office 365-DKIM-aktiverade domän till ett annat e-postkonto, till exempel outlook.com eller Hotmail.com.</span><span class="sxs-lookup"><span data-stu-id="ee425-215">Send a message from an account within your Office 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>

- <span data-ttu-id="ee425-216">Använd inte ett aol.com-konto för testningsändamål.</span><span class="sxs-lookup"><span data-stu-id="ee425-216">Do not use an aol.com account for testing purposes.</span></span> <span data-ttu-id="ee425-217">AOL kan hoppa över DKIM för att kontrollera om SPF-kontrollen överförs.</span><span class="sxs-lookup"><span data-stu-id="ee425-217">AOL may skip the DKIM check if the SPF check passes.</span></span> <span data-ttu-id="ee425-218">Det här annullerar testet.</span><span class="sxs-lookup"><span data-stu-id="ee425-218">This will nullify your test.</span></span>

- <span data-ttu-id="ee425-219">Öppna meddelandet och titta på rubriken.</span><span class="sxs-lookup"><span data-stu-id="ee425-219">Open the message and look at the header.</span></span> <span data-ttu-id="ee425-220">Information om hur du visar rubriken för meddelandet beror på vilken meddelandeklient du har.</span><span class="sxs-lookup"><span data-stu-id="ee425-220">Instructions for viewing the header for the message will vary depending on your messaging client.</span></span> <span data-ttu-id="ee425-221">Information om hur du visar meddelanderubriker i Outlook finns i [Visa e-postmeddelandehuvud](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).</span><span class="sxs-lookup"><span data-stu-id="ee425-221">For instructions on viewing message headers in Outlook, see [View e-mail message headers](https://support.office.com/article/CD039382-DC6E-4264-AC74-C048563D212C).</span></span>

  <span data-ttu-id="ee425-222">Det DKIM-signerade meddelandet innehåller värdnamnet och domänen som du angav när du publicerade CNAME-posterna.</span><span class="sxs-lookup"><span data-stu-id="ee425-222">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries.</span></span> <span data-ttu-id="ee425-223">Meddelandet liknar nu följande exempel:</span><span class="sxs-lookup"><span data-stu-id="ee425-223">The message will look something like this example:</span></span>

  ```text
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- <span data-ttu-id="ee425-224">Håll utkik efter huvudet Authentication-Results.</span><span class="sxs-lookup"><span data-stu-id="ee425-224">Look for the Authentication-Results header.</span></span> <span data-ttu-id="ee425-225">Även om varje mottagande tjänst använder något annat format för att stämpla inkommande e-post ska resultatet innehålla något som liknar **DKIM=pass** eller **DKIM=OK**.</span><span class="sxs-lookup"><span data-stu-id="ee425-225">While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span>

## <a name="to-configure-dkim-for-more-than-one-custom-domain-in-office-365"></a><span data-ttu-id="ee425-226">Konfigurera fler än en anpassad domän i Office 365</span><span class="sxs-lookup"><span data-stu-id="ee425-226">To configure DKIM for more than one custom domain in Office 365</span></span>
<span data-ttu-id="ee425-227"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="ee425-227"><a name="DKIMMultiDomain"> </a></span></span>

<span data-ttu-id="ee425-228">Om du senare bestämmer dig för att lägga till en egen domän och vill aktivera DKIM för den nya domänen måste du utföra stegen i den här artikeln för varje domän.</span><span class="sxs-lookup"><span data-stu-id="ee425-228">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain.</span></span> <span data-ttu-id="ee425-229">Slutför först alla steg i [What you need to do to manually set up DKIM in Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365) (Vad du behöver göra för att konfigurera DKIM i Office 365).</span><span class="sxs-lookup"><span data-stu-id="ee425-229">Specifically, complete all steps in [What you need to do to manually set up DKIM in Office 365](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain-in-office-365"></a><span data-ttu-id="ee425-230">Inaktivera DKIM-signeringsprincipen för en anpassad domän i Office 365</span><span class="sxs-lookup"><span data-stu-id="ee425-230">Disabling the DKIM signing policy for a custom domain in Office 365</span></span>
<span data-ttu-id="ee425-231"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="ee425-231"><a name="DisableDKIMSigningPolicy"> </a></span></span>

<span data-ttu-id="ee425-232">När du inaktiverar signeringsprincipen inaktiveras inte DKIM fullständigt.</span><span class="sxs-lookup"><span data-stu-id="ee425-232">Disabling the signing policy does not completely disable DKIM.</span></span> <span data-ttu-id="ee425-233">Efter en tidsperiod används standardprincipen för Office 365 automatiskt för din domän i Office 365.</span><span class="sxs-lookup"><span data-stu-id="ee425-233">After a period of time, Office 365 will automatically apply the default Office 365 policy for your domain.</span></span> <span data-ttu-id="ee425-234">Mer information finns i [Standardbeteende för DKIM och Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span><span class="sxs-lookup"><span data-stu-id="ee425-234">For more information, see [Default behavior for DKIM and Office 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="ee425-235">Inaktivera DKIM-signeringsprincipen med Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee425-235">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="ee425-236">[Ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ee425-236">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="ee425-237">Kör något av följande kommandon för varje domän som du vill inaktivera DKIM-signering för.</span><span class="sxs-lookup"><span data-stu-id="ee425-237">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>

    ```powershell
    $p = Get-DkimSigningConfig -Identity <domain>
    $p[0] | Set-DkimSigningConfig -Enabled $false
    ```

   <span data-ttu-id="ee425-238">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="ee425-238">For example:</span></span>

    ```powershell
    $p = Get-DkimSigningConfig -Identity contoso.com
    $p[0] | Set-DkimSigningConfig -Enabled $false
    ```

   <span data-ttu-id="ee425-239">Eller</span><span class="sxs-lookup"><span data-stu-id="ee425-239">Or</span></span>

    ```powershell
    Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
    ```

    <span data-ttu-id="ee425-240">Där _number_ är indexet för principen.</span><span class="sxs-lookup"><span data-stu-id="ee425-240">Where _number_ is the index of the policy.</span></span> <span data-ttu-id="ee425-241">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="ee425-241">For example:</span></span>

    ```powershell
    Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
    ```

## <a name="default-behavior-for-dkim-and-office-365"></a><span data-ttu-id="ee425-242">Standardbeteende för DKIM och Office 365</span><span class="sxs-lookup"><span data-stu-id="ee425-242">Default behavior for DKIM and Office 365</span></span>
<span data-ttu-id="ee425-243"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="ee425-243"><a name="DefaultDKIMbehavior"> </a></span></span>

<span data-ttu-id="ee425-244">Om du inte aktiverar DKIM skapar Office 365 automatiskt en offentlig 1024-bitars DKIM-nyckel för din standarddomän och den tillhörande privata nyckeln som vi lagrar internt i vårt datacenter.</span><span class="sxs-lookup"><span data-stu-id="ee425-244">If you do not enable DKIM, Office 365 automatically creates a 1024-bit DKIM public key for your default domain and the associated private key which we store internally in our datacenter.</span></span> <span data-ttu-id="ee425-245">Som standard använder Office 365 en standardkonfiguration för signering för domäner som inte har någon princip.</span><span class="sxs-lookup"><span data-stu-id="ee425-245">By default, Office 365 uses a default signing configuration for domains that do not have a policy in place.</span></span> <span data-ttu-id="ee425-246">Det innebär att om du inte konfigurerar DKIM själv kommer Office 365 att använda sin standardprincip och de nycklar som skapas för att aktivera DKIM för din domän.</span><span class="sxs-lookup"><span data-stu-id="ee425-246">This means that if you do not set up DKIM yourself, Office 365 will use its default policy and keys it creates in order to enable DKIM for your domain.</span></span>

<span data-ttu-id="ee425-247">Om du inaktiverar DKIM-signering när du har aktiverat det kommer Office 365 att automatiskt använda standardprincipen för Office 365 för din domän.</span><span class="sxs-lookup"><span data-stu-id="ee425-247">Also, if you disable DKIM signing after enabling it, after a period of time, Office 365 will automatically apply the Office 365 default policy for your domain.</span></span>

<span data-ttu-id="ee425-248">I följande exempel antar vi att DKIM för fabrikam.com har aktiverats av Office 365, inte av domänens administratör.</span><span class="sxs-lookup"><span data-stu-id="ee425-248">In the following example, suppose that DKIM for fabrikam.com was enabled by Office 365, not by the administrator of the domain.</span></span> <span data-ttu-id="ee425-249">Det innebär att de nödvändiga CNAME-posterna inte finns i DNS.</span><span class="sxs-lookup"><span data-stu-id="ee425-249">This means that the required CNAMEs do not exist in DNS.</span></span> <span data-ttu-id="ee425-250">DKIM-signaturer för e-post från den här domänen ser ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="ee425-250">DKIM signatures for email from this domain will look something like this:</span></span>

```text
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

<span data-ttu-id="ee425-251">I det här exemplet innehåller värddatornamnet och domänen värdena som CNAME pekar på om DKIM-signering för fabrikam.com har aktiverats av domänadministratören.</span><span class="sxs-lookup"><span data-stu-id="ee425-251">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator.</span></span> <span data-ttu-id="ee425-252">Slutligen kommer alla meddelanden som skickats från Office 365 att DKIM-signeras.</span><span class="sxs-lookup"><span data-stu-id="ee425-252">Eventually, every single message sent from Office 365 will be DKIM-signed.</span></span> <span data-ttu-id="ee425-253">Om du aktiverar DKIM själv blir domänen samma som domänen i Från: adress, i det här fallet fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="ee425-253">If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com.</span></span> <span data-ttu-id="ee425-254">Om du inte gör det justeras det inte. I stället används din organisations första domän.</span><span class="sxs-lookup"><span data-stu-id="ee425-254">If you don't, it will not align and instead will use your organization's initial domain.</span></span> <span data-ttu-id="ee425-255">Information om hur du fastställer din första domän finns i [Vanliga frågor och svar om domäner](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span><span class="sxs-lookup"><span data-stu-id="ee425-255">For information about determining your initial domain, see [Domains FAQ](https://docs.microsoft.com/office365/admin/setup/domains-faq#why-do-i-have-an-onmicrosoftcom-domain).</span></span>

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="ee425-256">Konfigurera DKIM så att en tjänst från tredje part kan skicka, eller förfalska, e-postmeddelanden för din anpassade domän.</span><span class="sxs-lookup"><span data-stu-id="ee425-256">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="ee425-257"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="ee425-257"><a name="SetUp3rdPartyspoof"> </a></span></span>

<span data-ttu-id="ee425-258">Vissa leverantör av e-posttjänster, eller leverantörer av programvara som tjänst, kan konfigurera DKIM-nycklar för e-post som kommer från tjänsten.</span><span class="sxs-lookup"><span data-stu-id="ee425-258">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service.</span></span> <span data-ttu-id="ee425-259">Det kräver samordning mellan dig och tredje part för att du ska kunna skapa de DNS-poster som krävs.</span><span class="sxs-lookup"><span data-stu-id="ee425-259">This requires coordination between yourself and the third-party in order to set up the necessary DNS records.</span></span> <span data-ttu-id="ee425-260">Inga organisationer fungerar på exakt samma sätt.</span><span class="sxs-lookup"><span data-stu-id="ee425-260">No two organizations do it exactly the same way.</span></span> <span data-ttu-id="ee425-261">I stället beror processen helt på organisationen.</span><span class="sxs-lookup"><span data-stu-id="ee425-261">Instead, the process depends entirely on the organization.</span></span>

<span data-ttu-id="ee425-262">Ett exempelmeddelande som visar ett korrekt konfigurerat DKIM för contoso.com och bulkemailprovider.com kan se ut så här:</span><span class="sxs-lookup"><span data-stu-id="ee425-262">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>

```text
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="ee425-263">I det här exemplet för att uppnå följande resultat:</span><span class="sxs-lookup"><span data-stu-id="ee425-263">In this example, in order to achieve this result:</span></span>

1. <span data-ttu-id="ee425-264">E-postleverantören för massutskick gav Contoso en offentlig DKIM-nyckel.</span><span class="sxs-lookup"><span data-stu-id="ee425-264">Bulk Email Provider gave Contoso a public DKIM key.</span></span>

2. <span data-ttu-id="ee425-265">Contoso offentliggjorde nyckeln DKIM till dess DNS-post.</span><span class="sxs-lookup"><span data-stu-id="ee425-265">Contoso published the DKIM key to its DNS record.</span></span>

3. <span data-ttu-id="ee425-266">När du skickar e-post signerar e-postleverantören för massutskick nyckeln med motsvarande privata nyckel.</span><span class="sxs-lookup"><span data-stu-id="ee425-266">When sending email, Bulk Email Provider signs the key with the corresponding private key.</span></span> <span data-ttu-id="ee425-267">Det gör att e-postleverantören för massutskicket bifogar DKIM-signaturen i meddelandehuvudet.</span><span class="sxs-lookup"><span data-stu-id="ee425-267">By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>

4. <span data-ttu-id="ee425-268">Mottagande e-postsystem utför en DKIM-kontroll genom att autentisera värdet i DKIM-signaturen d=\<domän\> mot domänen i meddelandet Från: (5322.From) för meddelandet.</span><span class="sxs-lookup"><span data-stu-id="ee425-268">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message.</span></span> <span data-ttu-id="ee425-269">I det här exemplet överensstämmer värdena:</span><span class="sxs-lookup"><span data-stu-id="ee425-269">In this example, the values match:</span></span>

    <span data-ttu-id="ee425-270">sender@**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="ee425-270">sender@**contoso.com**</span></span>

    <span data-ttu-id="ee425-271">d=**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="ee425-271">d=**contoso.com**</span></span>

## <a name="next-steps-after-you-set-up-dkim-for-office-365"></a><span data-ttu-id="ee425-272">Nästa steg: När du har konfigurerat DKIM för Office 365</span><span class="sxs-lookup"><span data-stu-id="ee425-272">Next steps: After you set up DKIM for Office 365</span></span>
<span data-ttu-id="ee425-273"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="ee425-273"><a name="DKIMNextSteps"> </a></span></span>

<span data-ttu-id="ee425-274">Även om DKIM har utformats för att förhindra förfalskningar fungerar DKIM bättre med SPF och DMARC.</span><span class="sxs-lookup"><span data-stu-id="ee425-274">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="ee425-275">När du har konfigurerat DKIM kan du konfigurera SPF om du inte redan har gjort det.</span><span class="sxs-lookup"><span data-stu-id="ee425-275">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="ee425-276">En introduktion till SPF finns i [Konfigurera SPF i Office 365 för att förhindra förfalskning](set-up-spf-in-office-365-to-help-prevent-spoofing.md), där du även kan konfigurera det snabbt.</span><span class="sxs-lookup"><span data-stu-id="ee425-276">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="ee425-277">För att få en djupare förståelse av hur Office 365 använder SPF, eller om du vill veta hur du felsöker eller göra icke-standarddistributioner (t.ex. hybriddistributioner), kan du börja med att läsa [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing (Så här använder Office 365 SPF för att förhindra förfalskning)](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="ee425-277">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="ee425-278">Därefter läser du [Använd DMARC för att validera e-post i Office 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="ee425-278">Next, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="ee425-279">[Meddelandehuvuden för antiskräppost](anti-spam-message-headers.md) innehåller syntaxen och rubrikerna som används i Office 365 för DKIM-kontroller.</span><span class="sxs-lookup"><span data-stu-id="ee425-279">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Office 365 for DKIM checks.</span></span>
