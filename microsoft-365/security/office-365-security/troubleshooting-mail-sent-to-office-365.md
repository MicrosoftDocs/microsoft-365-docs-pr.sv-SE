---
title: Felsöka e-post som skickas till Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Den här artikeln innehåller felsöknings information för problem med att skicka e-post till Inkorgen i Microsoft 365 & metod tips för Mass utskick till Microsoft 365-kunder.
ms.openlocfilehash: 3504d7518073826f3979c3c837c58d4406886b41
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760488"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a><span data-ttu-id="c3622-103">Felsöka e-post som skickas till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3622-103">Troubleshooting mail sent to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c3622-104">Den här artikeln innehåller felsöknings information för avsändare som har problem med att skicka e-post till inkorgar i Microsoft 365 och metod tips för Mass utskick till kunder.</span><span class="sxs-lookup"><span data-stu-id="c3622-104">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Microsoft 365 and best practices for bulk mailing to customers.</span></span>

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="c3622-105">Hanterar du din IP-och domäns sändande rykte?</span><span class="sxs-lookup"><span data-stu-id="c3622-105">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="c3622-106">EOP filter Technologies är avsedda att tillhandahålla skydd mot skräp post för Microsoft 365 samt andra Microsoft-produkter som Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="c3622-106">EOP filtering technologies are designed to provide anti-spam protection for Microsoft 365 as well as other Microsoft products like Exchange Server.</span></span> <span data-ttu-id="c3622-107">Vi använder också SPF, DKIM och DMARC; tekniker för e-postverifiering som hjälper dig att lösa problemet med förfalskningar och nätfiske genom att verifiera att den domän som skickar e-postmeddelandet är behörig att göra det.</span><span class="sxs-lookup"><span data-stu-id="c3622-107">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="c3622-108">EOP-filtreringen påverkas av ett antal faktorer som är relaterade till sändnings-IP-, domän-, verifikations-, list precision, klagomåls taxa, innehåll och annat.</span><span class="sxs-lookup"><span data-stu-id="c3622-108">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="c3622-109">Av dessa är en av huvud faktorerna för att hålla ned avsändarens rykte och deras förmåga att skicka e-post till sin skräp post.</span><span class="sxs-lookup"><span data-stu-id="c3622-109">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

## <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="c3622-110">Skickar du e-post från nya IP-adresser?</span><span class="sxs-lookup"><span data-stu-id="c3622-110">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="c3622-111">IP-adresser som tidigare inte har använts för att skicka e-post har vanligt vis inget rykte inbyggt i våra system.</span><span class="sxs-lookup"><span data-stu-id="c3622-111">IP addresses not previously used to send email typically don't have any reputation built up in our systems.</span></span> <span data-ttu-id="c3622-112">Som ett resultat av detta är det mer sannolikt att skicka e-post från nya IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="c3622-112">As a result, emails from new IPs are more likely to experience delivery issues.</span></span> <span data-ttu-id="c3622-113">När undersöknings perioden har byggt ett rykte för att inte skicka skräp post, ger EOP vanligt vis bättre funktioner för e-postleverans.</span><span class="sxs-lookup"><span data-stu-id="c3622-113">Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="c3622-114">Nya IP-adresser som läggs till för domäner som är autentiserade under befintliga SPF-poster har vanligt vis utnyttjat fördelarna med att ärva en del av domänens avsändnings rykte.</span><span class="sxs-lookup"><span data-stu-id="c3622-114">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation.</span></span> <span data-ttu-id="c3622-115">Om din domän har ett bra avsändar rykte kan nya IP-adresser uppleva snabbare.</span><span class="sxs-lookup"><span data-stu-id="c3622-115">If your domain has a good sending reputation new IPs may experience a faster ramp up time.</span></span> <span data-ttu-id="c3622-116">En ny IP-adress kan förvänta sig att bli helt ramp inom några veckor eller snart beroende på volym, lista över riktighet och skräp post taxa.</span><span class="sxs-lookup"><span data-stu-id="c3622-116">A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

## <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="c3622-117">Kontrol lera att din DNS är korrekt konfigurerad</span><span class="sxs-lookup"><span data-stu-id="c3622-117">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="c3622-118">Instruktioner om hur du skapar och hanterar DNS-poster, inklusive MX-posten som krävs för e-postdirigering, måste du kontakta din DNS-värd.</span><span class="sxs-lookup"><span data-stu-id="c3622-118">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="c3622-119">Se till att du inte annonserar dig själv som en icke-Routing-IP</span><span class="sxs-lookup"><span data-stu-id="c3622-119">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="c3622-120">Vi kanske inte accepterar e-post från avsändare som inte har en omvänd DNS-sökning.</span><span class="sxs-lookup"><span data-stu-id="c3622-120">We may not accept email from senders who fail a reverse-DNS lookup.</span></span> <span data-ttu-id="c3622-121">I vissa fall annonseras legitima avsändare felaktigt som icke-Internetbaserad IP-adress när du försöker öppna en anslutning till EOP.</span><span class="sxs-lookup"><span data-stu-id="c3622-121">In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP.</span></span> <span data-ttu-id="c3622-122">IP-adresser som reserveras för privata (icke-dirigerbart) nätverk inkluderar:</span><span class="sxs-lookup"><span data-stu-id="c3622-122">IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="c3622-123">192.168.0.0/16 (eller 192.168.0.0 – 192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="c3622-123">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>
- <span data-ttu-id="c3622-124">10.0.0.0/8 (eller 10.0.0.0-10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="c3622-124">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>
- <span data-ttu-id="c3622-125">172.16.0.0/11 (eller 172.16.0.0 – 172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="c3622-125">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="c3622-126">Du fick en rapport om utebliven leverans (NDR) när du skickar e-post till en användare i Office 365</span><span class="sxs-lookup"><span data-stu-id="c3622-126">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="c3622-127">Vissa leverans problem är resultatet av avsändarens IP-adress som blockeras av Microsoft eller på grund av att användar kontot identifieras som blockerad avsändare på grund av tidigare spam.</span><span class="sxs-lookup"><span data-stu-id="c3622-127">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity.</span></span> <span data-ttu-id="c3622-128">Om du tror att du har fått fel meddelandet om MISSLYCKAd leverans problem, följer du först anvisningarna i NDR för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="c3622-128">If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="c3622-129">Om du vill ha mer information om det fel du fick kan du läsa listan med felkoder i [rapportera inte meddelanden om e-post i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="c3622-129">For more information about the error you received, see the list of error codes in [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

 <span data-ttu-id="c3622-130">Om du till exempel tar emot följande NDR anger det att den sändande IP-adressen blockerades av Microsoft:</span><span class="sxs-lookup"><span data-stu-id="c3622-130">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft:</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="c3622-131">För att begära borttagning från den här listan kan du [ta bort dig själv från listan Spärrade avsändare](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)genom att använda List portalen.</span><span class="sxs-lookup"><span data-stu-id="c3622-131">To request removal from this list, you can [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a><span data-ttu-id="c3622-132">Mitt e-postmeddelande landats i mottagarens mapp för skräp post</span><span class="sxs-lookup"><span data-stu-id="c3622-132">My email landed in the recipient's Junk Email folder</span></span>

<span data-ttu-id="c3622-133">Om ett meddelande felaktigt har identifierats som skräp post av EOP kan du arbeta med mottagaren för att skicka detta falska positiva meddelande till Microsoft spam-gruppen, som kommer att utvärdera och analysera meddelandet.</span><span class="sxs-lookup"><span data-stu-id="c3622-133">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="c3622-134">Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="c3622-134">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="c3622-135">Trafik från min IP-adress begränsas av EOP</span><span class="sxs-lookup"><span data-stu-id="c3622-135">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="c3622-136">Om du får en NDR från EOP att din IP-adress begränsas av EOP, till exempel:</span><span class="sxs-lookup"><span data-stu-id="c3622-136">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="c3622-137">Du fick meddelandet NDR eftersom misstänkt aktivitet har upptäckts från IP-adressen och den har tillfälligt begränsats medan den utvärderas vidare.</span><span class="sxs-lookup"><span data-stu-id="c3622-137">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated.</span></span> <span data-ttu-id="c3622-138">Om misstanken är klar genom utvärdering kommer denna begränsning att hävas snart.</span><span class="sxs-lookup"><span data-stu-id="c3622-138">If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a><span data-ttu-id="c3622-139">Jag kan inte ta emot e-post från avsändare i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3622-139">I can't receive email from senders in Microsoft 365</span></span>

 <span data-ttu-id="c3622-140">För att ta emot meddelanden från våra användare ska du kontrol lera att nätverket tillåter anslutningar från IP-adresserna som EOP använder i våra data Center.</span><span class="sxs-lookup"><span data-stu-id="c3622-140">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="c3622-141">Mer information finns i [Exchange Online Protection IP-adresser](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="c3622-141">For more information, see [Exchange Online Protection IP addresses](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span>

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a><span data-ttu-id="c3622-142">Metod tips för Mass utskick via e-post till Microsoft 365-användare</span><span class="sxs-lookup"><span data-stu-id="c3622-142">Best practices for bulk emailing to Microsoft 365 users</span></span>

<span data-ttu-id="c3622-143">Om du ofta utför Mass utskick av e-post till Microsoft 365-användare och vill försäkra dig om att dina e-postmeddelanden kommer till ett säkert och tidseffektivt sätt, följer du tipsen i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="c3622-143">If you often conduct bulk email campaigns to Microsoft 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="c3622-144">Kontrol lera att från-namnet återspeglar vem som skickar meddelandet</span><span class="sxs-lookup"><span data-stu-id="c3622-144">Ensure that the From name reflects who is sending the message</span></span>

<span data-ttu-id="c3622-145">Ämnet bör vara en kort sammanfattning av vad meddelandet rör sig om och meddelandets brödtext bör tydligt och succinctly Visa vad erbjudandet, tjänsten eller produkten är till för.</span><span class="sxs-lookup"><span data-stu-id="c3622-145">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about.</span></span> <span data-ttu-id="c3622-146">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="c3622-146">For example:</span></span>

<span data-ttu-id="c3622-147">Rätt:</span><span class="sxs-lookup"><span data-stu-id="c3622-147">Correct:</span></span>

> <span data-ttu-id="c3622-148">Från: marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="c3622-148">From: marketing@shoppershandbag.com</span></span> <br> <span data-ttu-id="c3622-149">Ämne: Uppdaterad katalog för jul säsongen!</span><span class="sxs-lookup"><span data-stu-id="c3622-149">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="c3622-150">Fel:</span><span class="sxs-lookup"><span data-stu-id="c3622-150">Incorrect:</span></span>

> <span data-ttu-id="c3622-151">Från: someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="c3622-151">From: someone@outlook.com</span></span> <br> <span data-ttu-id="c3622-152">Ämne: kataloger</span><span class="sxs-lookup"><span data-stu-id="c3622-152">Subject: Catalogs</span></span>

<span data-ttu-id="c3622-153">Ju lättare du gör det för folk att veta vem du är och vad du gör är det mindre svårt att få fram de flesta spam.</span><span class="sxs-lookup"><span data-stu-id="c3622-153">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="c3622-154">Inkludera alltid alternativet för att avbryta prenumerationer i e-post för kampanjer</span><span class="sxs-lookup"><span data-stu-id="c3622-154">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="c3622-155">Marknadsförings-e-postmeddelanden, särskilt nyhets brev, bör alltid innehålla ett sätt att avsluta en framtida e-post.</span><span class="sxs-lookup"><span data-stu-id="c3622-155">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails.</span></span> <span data-ttu-id="c3622-156">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="c3622-156">For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

<span data-ttu-id="c3622-157">Vissa avsändare inkluderar det här alternativet genom att kräva att mottagarna skickar ett e-postmeddelande till ett visst alias med "avabonnera" i ämnes raden.</span><span class="sxs-lookup"><span data-stu-id="c3622-157">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject.</span></span> <span data-ttu-id="c3622-158">Det är inte lämpligt att använda ett av exemplen ovan.</span><span class="sxs-lookup"><span data-stu-id="c3622-158">This is not preferable to the one-click example above.</span></span> <span data-ttu-id="c3622-159">Om du väljer att kräva att mottagarna skickar ett e-postmeddelande, se till att när de klickar på länken är alla obligatoriska fält ifyllda.</span><span class="sxs-lookup"><span data-stu-id="c3622-159">If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="c3622-160">Använd alternativet dubbelt opt-in för marknadsföring via e-post eller nyhets brev</span><span class="sxs-lookup"><span data-stu-id="c3622-160">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="c3622-161">Vi rekommenderar att du använder denna bransch metod om företaget kräver eller uppmuntrar användare att registrera sin kontakt information för att få åtkomst till din produkt eller tjänst.</span><span class="sxs-lookup"><span data-stu-id="c3622-161">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services.</span></span> <span data-ttu-id="c3622-162">Vissa företag gör det för att automatiskt registrera sina användare för marknadsförings-e-post eller e-postnyhetsbrev under registrerings processen, men det anses vara en tveksam marknadsförings övning i världen med e-postfiltrering.</span><span class="sxs-lookup"><span data-stu-id="c3622-162">Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="c3622-163">Under registrerings processen, om kryss rutan "Ja, skicka mig ett nyhets brev" eller "Ja, skicka mig med Special erbjudanden" är markerat som standard kan användare som inte betalar nära uppmärksamheten registrera sig för marknadsföring via e-post eller nyhets brev som de inte vill ta emot.</span><span class="sxs-lookup"><span data-stu-id="c3622-163">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="c3622-164">Vi rekommenderar alternativet dubbel opt-in i stället, vilket betyder att kryss rutan för marknadsförings-e-post eller nyhets brev inte är markerad som standard.</span><span class="sxs-lookup"><span data-stu-id="c3622-164">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default.</span></span> <span data-ttu-id="c3622-165">När registrerings formuläret har skickats skickas dessutom en bekräftelse via e-post till användaren med en URL som gör att de kan bekräfta marknadsförings-e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="c3622-165">Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="c3622-166">Då ser du till att bara de användare som vill få marknadsförings-e-post är registrerade för e-postmeddelandena och sedan Rensa det sändande företaget av en tveksam e-postmarknadsförings praxis.</span><span class="sxs-lookup"><span data-stu-id="c3622-166">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="c3622-167">Kontrol lera att e-postmeddelandets innehåll är transparent och kan spåras</span><span class="sxs-lookup"><span data-stu-id="c3622-167">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="c3622-168">Precis så viktigt som att e-postmeddelandena skickas är innehållet de innehåller.</span><span class="sxs-lookup"><span data-stu-id="c3622-168">Just as important as the way the emails are sent is the content they contain.</span></span> <span data-ttu-id="c3622-169">När du skapar e-post kan du använda följande metod tips för att se till att dina e-postmeddelanden inte flaggas via e-post filter tjänster:</span><span class="sxs-lookup"><span data-stu-id="c3622-169">When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="c3622-170">När e-postmeddelandet begär att mottagarna lägger till avsändaren i adress boken bör det tydligt uppges att sådan åtgärd inte är en garanti för leverans.</span><span class="sxs-lookup"><span data-stu-id="c3622-170">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="c3622-171">Omdirigeringar som ingår i meddelandets brödtext ska vara liknande och enhetliga och inte multipla och varierande.</span><span class="sxs-lookup"><span data-stu-id="c3622-171">Redirects included in the body of the message should be similar and consistent, and not multiple and varied.</span></span> <span data-ttu-id="c3622-172">Det är bara att omdirigera från meddelandet, till exempel länkar och dokument.</span><span class="sxs-lookup"><span data-stu-id="c3622-172">A redirect in this context is anything that points away from the message, such as links and documents.</span></span> <span data-ttu-id="c3622-173">Om du har många annonserings-eller avprenumerations länkar eller uppdaterar profil länkarna måste de peka på samma domän.</span><span class="sxs-lookup"><span data-stu-id="c3622-173">If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain.</span></span> <span data-ttu-id="c3622-174">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="c3622-174">For example:</span></span>

  <span data-ttu-id="c3622-175">Korrekt (alla domäner är desamma):</span><span class="sxs-lookup"><span data-stu-id="c3622-175">Correct (all domains are the same):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="c3622-176">Fel (alla domäner är olika):</span><span class="sxs-lookup"><span data-stu-id="c3622-176">Incorrect (all domains are different):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="c3622-177">Undvik innehåll med stora bilder och bifogade filer eller meddelanden som bara består av en bild.</span><span class="sxs-lookup"><span data-stu-id="c3622-177">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="c3622-178">Dina offentliga integritets-eller P3P-inställningar bör tydligt ange närvaron av spårnings pixlar (webb programs och beacons).</span><span class="sxs-lookup"><span data-stu-id="c3622-178">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="c3622-179">Ta bort felaktiga e-postalias från dina databaser</span><span class="sxs-lookup"><span data-stu-id="c3622-179">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="c3622-180">Alla e-postalias i databasen som skapar en återuppringning är onödigt och gör dina utgående e-postmeddelanden till risk för ytterligare granskning via e-post filter tjänster.</span><span class="sxs-lookup"><span data-stu-id="c3622-180">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services.</span></span> <span data-ttu-id="c3622-181">Kontrol lera att din e-postdatabas är uppdaterad.</span><span class="sxs-lookup"><span data-stu-id="c3622-181">Ensure that your email database is up-to-date.</span></span>
