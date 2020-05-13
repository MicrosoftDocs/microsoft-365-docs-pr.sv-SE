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
description: Den här artikeln innehåller felsökningsinformation för problem med att skicka e-post till inkorgar i Microsoft 365 & metodtips för massutskick till Microsoft 365-kunder.
ms.openlocfilehash: 0d9c1646aa7491b3da458c7cb0ddeb908873153a
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208603"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a><span data-ttu-id="cd4a2-103">Felsöka e-post som skickas till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cd4a2-103">Troubleshooting mail sent to Microsoft 365</span></span>

<span data-ttu-id="cd4a2-104">Den här artikeln innehåller felsökningsinformation för avsändare som har problem när de försöker skicka e-post till inkorgar i Microsoft 365 och metodtips för massutskick till kunder.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-104">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Microsoft 365 and best practices for bulk mailing to customers.</span></span>

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="cd4a2-105">Hanterar du din IP och domänens skicka rykte?</span><span class="sxs-lookup"><span data-stu-id="cd4a2-105">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="cd4a2-106">EOP-filtreringstekniker är utformade för att ge skydd mot skräppost för Microsoft 365 och andra Microsoft-produkter som Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-106">EOP filtering technologies are designed to provide anti-spam protection for Microsoft 365 as well as other Microsoft products like Exchange Server.</span></span> <span data-ttu-id="cd4a2-107">Vi utnyttjar också SPF, DKIM och DMARC; e-postautentiseringstekniker som hjälper till att lösa problemet med förfalskning och nätfiske genom att verifiera att domänen som skickar e-postmeddelandet har behörighet att göra det.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-107">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="cd4a2-108">EOP-filtrering påverkas av ett antal faktorer relaterade till den sändande IP, domän, autentisering, lista noggrannhet, klagomål priser, innehåll och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-108">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="cd4a2-109">Av dessa, en av de viktigaste faktorerna för att köra ner en avsändare rykte och deras förmåga att leverera e-post är deras skräp e klagomål takt.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-109">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

## <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="cd4a2-110">Skickar du e-post från nya IP-adresser?</span><span class="sxs-lookup"><span data-stu-id="cd4a2-110">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="cd4a2-111">IP-adresser som inte tidigare använts för att skicka e-post har vanligtvis inget rykte byggt upp i våra system.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-111">IP addresses not previously used to send email typically don't have any reputation built up in our systems.</span></span> <span data-ttu-id="cd4a2-112">Som ett resultat, e-post från nya IPs är mer benägna att uppleva leveransproblem.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-112">As a result, emails from new IPs are more likely to experience delivery issues.</span></span> <span data-ttu-id="cd4a2-113">När IP har byggt upp ett rykte för att inte skicka skräppost, eop kommer vanligtvis att möjliggöra en bättre e-postleverans upplevelse.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-113">Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="cd4a2-114">Nya IPs som läggs till för domäner som autentiseras under befintliga SPF-poster får vanligtvis den extra fördelen att ärva en del av domänens sändningsrykte.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-114">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation.</span></span> <span data-ttu-id="cd4a2-115">Om din domän har ett gott sändningsrykt kan nya IPs uppleva en snabbare uppramptid.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-115">If your domain has a good sending reputation new IPs may experience a faster ramp up time.</span></span> <span data-ttu-id="cd4a2-116">En ny IP kan förvänta sig att vara helt ramped inom ett par veckor eller tidigare beroende på volym, lista noggrannhet och skräp e-post klagomål priser.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-116">A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

## <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="cd4a2-117">Bekräfta att DNS:en är korrekt konfigurerad</span><span class="sxs-lookup"><span data-stu-id="cd4a2-117">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="cd4a2-118">Om du vill ha instruktioner om hur du skapar och underhåller DNS-poster, inklusive MX-posten som krävs för e-postroutning, måste du kontakta din DNS-värd.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-118">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="cd4a2-119">Se till att du inte annonserar själv som en icke-dirigerbar IP</span><span class="sxs-lookup"><span data-stu-id="cd4a2-119">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="cd4a2-120">Vi kanske inte accepterar e-post från avsändare som misslyckas med en omvänd DNS-sökning.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-120">We may not accept email from senders who fail a reverse-DNS lookup.</span></span> <span data-ttu-id="cd4a2-121">I vissa fall annonserar legitima avsändare sig felaktigt som en icke-internetdigerbar IP när de försöker öppna en anslutning till EOP.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-121">In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP.</span></span> <span data-ttu-id="cd4a2-122">IP-adresser som är reserverade för privata (icke-dirigerbara) nätverk inkluderar:</span><span class="sxs-lookup"><span data-stu-id="cd4a2-122">IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="cd4a2-123">192.168.0.0/16 (eller 192.168.0.0 - 192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="cd4a2-123">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>

- <span data-ttu-id="cd4a2-124">10.0.0.0/8 (eller 10.0.0.0 - 10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="cd4a2-124">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>

- <span data-ttu-id="cd4a2-125">172.16.0.0/11 (eller 172.16.0.0 - 172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="cd4a2-125">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="cd4a2-126">Du har fått en rapport om utebliven leverans (NDR) när du skickade e-post till en användare i Office 365</span><span class="sxs-lookup"><span data-stu-id="cd4a2-126">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="cd4a2-127">Vissa leveransproblem är resultatet av att avsändarens IP-adress blockeras av Microsoft eller på att användarkontot identifieras som förbjudna avsändare på grund av tidigare skräppostaktivitet.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-127">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity.</span></span> <span data-ttu-id="cd4a2-128">Om du tror att du har fått NDR av misstag, följ först eventuella instruktioner i NDR-meddelandet för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-128">If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="cd4a2-129">Mer information om felet du fick finns i listan över felkoder i [rapporter om utebliven leverans via e-post i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="cd4a2-129">For more information about the error you received, see the list of error codes in [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

 <span data-ttu-id="cd4a2-130">Om du till exempel får följande NDR anger den att den sändande IP-adressen har blockerats av Microsoft:</span><span class="sxs-lookup"><span data-stu-id="cd4a2-130">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft:</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="cd4a2-131">Om du vill begära borttagning från den här listan kan du [använda avlistningsportalen för att ta bort dig själv från listan blockerade avsändare](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="cd4a2-131">To request removal from this list, you can [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a><span data-ttu-id="cd4a2-132">Min e-post landade i mottagarens skräppostmapp</span><span class="sxs-lookup"><span data-stu-id="cd4a2-132">My email landed in the recipient's Junk Email folder</span></span>

<span data-ttu-id="cd4a2-133">Om ett meddelande felaktigt har identifierats som skräppost av EOP kan du arbeta med mottagaren för att skicka det här falska positiva meddelandet till Microsoft Spam Analysis Team, som utvärderar och analyserar meddelandet.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-133">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="cd4a2-134">Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="cd4a2-134">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="cd4a2-135">Trafiken från min IP-adress begränsas av EOP</span><span class="sxs-lookup"><span data-stu-id="cd4a2-135">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="cd4a2-136">Om du får en NDR från EOP som anger att din IP-adress begränsas av EOP, till exempel:</span><span class="sxs-lookup"><span data-stu-id="cd4a2-136">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="cd4a2-137">Du har fått NDR eftersom misstänkt aktivitet har upptäckts från IP-adressen och den har begränsats tillfälligt medan den utvärderas ytterligare.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-137">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated.</span></span> <span data-ttu-id="cd4a2-138">Om misstanken undanröjs genom utvärdering kommer denna begränsning att hävas inom kort.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-138">If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a><span data-ttu-id="cd4a2-139">Jag kan inte ta emot e-post från avsändare i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cd4a2-139">I can't receive email from senders in Microsoft 365</span></span>

 <span data-ttu-id="cd4a2-140">För att ta emot meddelanden från våra användare, se till att ditt nätverk tillåter anslutningar från IP-adresser som EOP använder i våra datacenter.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-140">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="cd4a2-141">Mer information finns i [Exchange Online Protection IP-adresser](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="cd4a2-141">For more information, see [Exchange Online Protection IP addresses](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a><span data-ttu-id="cd4a2-142">Metodtips för massutskick av e-post till Microsoft 365-användare</span><span class="sxs-lookup"><span data-stu-id="cd4a2-142">Best practices for bulk emailing to Microsoft 365 users</span></span>

<span data-ttu-id="cd4a2-143">Om du ofta genomför massutskick av e-post till Microsoft 365-användare och vill se till att dina e-postmeddelanden kommer fram på ett säkert och snabbt sätt följer du tipsen i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-143">If you often conduct bulk email campaigns to Microsoft 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="cd4a2-144">Se till att namnet Från visar vem som skickar meddelandet</span><span class="sxs-lookup"><span data-stu-id="cd4a2-144">Ensure that the From name reflects who is sending the message</span></span>

<span data-ttu-id="cd4a2-145">Ämnet bör vara en kort sammanfattning av vad meddelandet handlar om, och meddelandetexten bör tydligt och kortfattat ange vad erbjudandet, tjänsten eller produkten handlar om.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-145">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about.</span></span> <span data-ttu-id="cd4a2-146">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="cd4a2-146">For example:</span></span>

<span data-ttu-id="cd4a2-147">Korrekt:</span><span class="sxs-lookup"><span data-stu-id="cd4a2-147">Correct:</span></span>

> <span data-ttu-id="cd4a2-148">Från: marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="cd4a2-148">From: marketing@shoppershandbag.com</span></span> <br/> <span data-ttu-id="cd4a2-149">Ämne: Uppdaterad katalog för julen!</span><span class="sxs-lookup"><span data-stu-id="cd4a2-149">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="cd4a2-150">Felaktig:</span><span class="sxs-lookup"><span data-stu-id="cd4a2-150">Incorrect:</span></span>

> <span data-ttu-id="cd4a2-151">Från: someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="cd4a2-151">From: someone@outlook.com</span></span> <br/> <span data-ttu-id="cd4a2-152">Ämne: Kataloger</span><span class="sxs-lookup"><span data-stu-id="cd4a2-152">Subject: Catalogs</span></span>

<span data-ttu-id="cd4a2-153">Ju lättare du gör det för människor att veta vem du är och vad du gör, desto mindre svårigheter kommer du att ha leverera genom de flesta spamfilter.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-153">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="cd4a2-154">Inkludera alltid ett alternativ för att avsluta prenumerationen i kampanjmeddelanden</span><span class="sxs-lookup"><span data-stu-id="cd4a2-154">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="cd4a2-155">Marknadsföring e-post, särskilt nyhetsbrev, bör alltid innehålla ett sätt att avregistrera sig från framtida e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-155">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails.</span></span> <span data-ttu-id="cd4a2-156">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="cd4a2-156">For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

<span data-ttu-id="cd4a2-157">Vissa avsändare inkluderar det här alternativet genom att kräva att mottagarna skickar ett e-postmeddelande till ett visst alias med "Avsluta prenumeration" i ämnet.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-157">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject.</span></span> <span data-ttu-id="cd4a2-158">Detta är inte att föredra framför ett klick exempel ovan.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-158">This is not preferable to the one-click example above.</span></span> <span data-ttu-id="cd4a2-159">Om du väljer att kräva att mottagarna skickar ett e-postmeddelande kontrollerar du att alla obligatoriska fält är förifyllda när de klickar på länken.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-159">If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="cd4a2-160">Använd alternativet dubbel opt-in för marknadsföring e-post eller nyhetsbrev registrering</span><span class="sxs-lookup"><span data-stu-id="cd4a2-160">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="cd4a2-161">Den här bästa branschen rekommenderas om ditt företag kräver eller uppmuntrar användare att registrera sina kontaktuppgifter för att få tillgång till din produkt eller dina tjänster.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-161">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services.</span></span> <span data-ttu-id="cd4a2-162">Vissa företag gör det till en praxis att automatiskt registrera sina användare för marknadsföring e-post eller e-nyhetsbrev under registreringsprocessen, men detta anses vara en tvivelaktig marknadsföring praxis i en värld av e-filtrering.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-162">Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="cd4a2-163">Under registreringsprocessen, om "Ja, skicka mig ditt nyhetsbrev" eller "Ja, skicka mig specialerbjudanden" kryssrutan väljs som standard, användare som inte betalar stor uppmärksamhet kan oavsiktligt registrera dig för marknadsföring e-post eller nyhetsbrev som de inte vill få.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-163">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="cd4a2-164">Vi rekommenderar alternativet dubbel opt-in i stället, vilket innebär att kryssrutan för marknadsföring av e-postmeddelanden eller nyhetsbrev är avmarkerad som standard.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-164">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default.</span></span> <span data-ttu-id="cd4a2-165">Dessutom, när registreringsformuläret har skickats, en verifiering e-post skickas till användaren med en webbadress som tillåter dem att bekräfta sitt beslut att ta emot marknadsföring e-post.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-165">Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="cd4a2-166">Detta bidrar till att säkerställa att endast de användare som vill få marknadsföring e-post är registrerade för e-post, därefter rensa det sändande företaget av tvivelaktiga e-postmarknadsföring praxis.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-166">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="cd4a2-167">Se till att e-postmeddelandets innehåll är genomskinligt och spårbart</span><span class="sxs-lookup"><span data-stu-id="cd4a2-167">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="cd4a2-168">Lika viktigt som hur e-postmeddelandena skickas är innehållet de innehåller.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-168">Just as important as the way the emails are sent is the content they contain.</span></span> <span data-ttu-id="cd4a2-169">När du skapar e-postinnehåll använder du följande metodtips för att se till att dina e-postmeddelanden inte flaggas av e-postfiltreringstjänster:</span><span class="sxs-lookup"><span data-stu-id="cd4a2-169">When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="cd4a2-170">När e-postmeddelandet begär att mottagarna lägger till avsändaren i adressboken, bör det tydligt anges att en sådan åtgärd inte är en garanti för leverans.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-170">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="cd4a2-171">Omdirigeringar som ingår i meddelandets brödtext ska vara lika och konsekventa och inte flera och varierande.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-171">Redirects included in the body of the message should be similar and consistent, and not multiple and varied.</span></span> <span data-ttu-id="cd4a2-172">En omdirigering i det här sammanhanget är allt som pekar bort från meddelandet, till exempel länkar och dokument.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-172">A redirect in this context is anything that points away from the message, such as links and documents.</span></span> <span data-ttu-id="cd4a2-173">Om du har många annonserings- eller unsubscribe-länkar eller uppdatera profillänkarna bör de alla peka på samma domän.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-173">If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain.</span></span> <span data-ttu-id="cd4a2-174">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="cd4a2-174">For example:</span></span>

  <span data-ttu-id="cd4a2-175">Korrekt:</span><span class="sxs-lookup"><span data-stu-id="cd4a2-175">Correct:</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="cd4a2-176">Felaktig:</span><span class="sxs-lookup"><span data-stu-id="cd4a2-176">Incorrect:</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="cd4a2-177">Undvik innehåll med stora bilder och bifogade filer eller meddelanden som enbart består av en bild.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-177">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="cd4a2-178">Din offentliga integritet eller P3P-inställningar bör tydligt ange förekomsten av spårningspixlar (webbbuggar eller beacons).</span><span class="sxs-lookup"><span data-stu-id="cd4a2-178">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="cd4a2-179">Ta bort felaktiga e-postalias från databaserna</span><span class="sxs-lookup"><span data-stu-id="cd4a2-179">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="cd4a2-180">Alla e-postalias i databasen som skapar en studsa tillbaka är onödigt och sätter dina utgående e-postmeddelanden i riskzonen för ytterligare granskning av e-filtreringstjänster.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-180">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services.</span></span> <span data-ttu-id="cd4a2-181">Se till att din e-postdatabas är uppdaterad.</span><span class="sxs-lookup"><span data-stu-id="cd4a2-181">Ensure that your email database is up-to-date.</span></span>
