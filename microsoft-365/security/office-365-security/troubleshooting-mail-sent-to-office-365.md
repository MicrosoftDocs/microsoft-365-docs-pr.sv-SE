---
title: Felsöka e-post som skickas till Office 365
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
description: Den här artikeln innehåller felsökningsinformation för avsändare som har problem när de försöker skicka e-post till inkorgar i Office 365 och metodtips för massutskick till Office 365-kunder.
ms.openlocfilehash: 7c5d355f1037df94d856ffff7080d4a12d22f709
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211913"
---
# <a name="troubleshooting-mail-sent-to-office-365"></a><span data-ttu-id="46e5c-103">Felsöka e-post som skickas till Office 365</span><span class="sxs-lookup"><span data-stu-id="46e5c-103">Troubleshooting mail sent to Office 365</span></span>

<span data-ttu-id="46e5c-104">Den här artikeln innehåller felsökningsinformation för avsändare som har problem när de försöker skicka e-post till inkorgar i Office 365 och metodtips för massutskick till Office 365-kunder.</span><span class="sxs-lookup"><span data-stu-id="46e5c-104">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Office 365 and best practices for bulk mailing to Office 365 customers.</span></span>

## <a name="troubleshooting-common-problems-with-mail-delivery-to-office-365"></a><span data-ttu-id="46e5c-105">Felsöka vanliga problem med e-postleverans till Office 365</span><span class="sxs-lookup"><span data-stu-id="46e5c-105">Troubleshooting common problems with mail delivery to Office 365</span></span>

<span data-ttu-id="46e5c-106">Välj bland ett av dessa vanliga problem.</span><span class="sxs-lookup"><span data-stu-id="46e5c-106">Choose from one of these commonly encountered issues.</span></span>

- [<span data-ttu-id="46e5c-107">Hanterar du din IP och domänens skicka rykte?</span><span class="sxs-lookup"><span data-stu-id="46e5c-107">Are you managing your IP and domain's sending reputation?</span></span>](#are-you-managing-your-ip-and-domains-sending-reputation)

- [<span data-ttu-id="46e5c-108">Skickar du e-post från nya IP-adresser?</span><span class="sxs-lookup"><span data-stu-id="46e5c-108">Are you sending email from new IP addresses?</span></span>](#are-you-sending-email-from-new-ip-addresses)

- [<span data-ttu-id="46e5c-109">Bekräfta att DNS:en är korrekt konfigurerad</span><span class="sxs-lookup"><span data-stu-id="46e5c-109">Confirm that your DNS is set up correctly</span></span>](#confirm-that-your-dns-is-set-up-correctly)

- [<span data-ttu-id="46e5c-110">Se till att du inte annonserar själv som en icke-dirigerbar IP</span><span class="sxs-lookup"><span data-stu-id="46e5c-110">Ensure that you do not advertise yourself as a non-routable IP</span></span>](#ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip)

- [<span data-ttu-id="46e5c-111">Du har fått en rapport om utebliven leverans (NDR) när du skickade e-post till en användare i Office 365</span><span class="sxs-lookup"><span data-stu-id="46e5c-111">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>](#you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365)

- [<span data-ttu-id="46e5c-112">Min e-post landade i mottagarens skräppostmapp i EOP</span><span class="sxs-lookup"><span data-stu-id="46e5c-112">My email landed in the recipient's junk folder in EOP</span></span>](#my-email-landed-in-the-recipients-junk-folder-in-eop)

- [<span data-ttu-id="46e5c-113">Trafiken från min IP-adress begränsas av EOP</span><span class="sxs-lookup"><span data-stu-id="46e5c-113">Traffic from my IP address is throttled by EOP</span></span>](#traffic-from-my-ip-address-is-throttled-by-eop)

### <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="46e5c-114">Hanterar du din IP och domänens skicka rykte?</span><span class="sxs-lookup"><span data-stu-id="46e5c-114">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="46e5c-115">EOP-filtreringstekniker är utformade för att ge skydd mot skräppost för Microsoft Office 365 och andra Microsoft-produkter som Exchange Server, Microsoft Office Outlook och Windows Live Mail.</span><span class="sxs-lookup"><span data-stu-id="46e5c-115">EOP filtering technologies are designed to provide anti-spam protections for Microsoft Office 365 as well as other Microsoft products like Exchange Server, Microsoft Office Outlook, and Windows Live Mail.</span></span> <span data-ttu-id="46e5c-116">Vi utnyttjar också SPF, DKIM och DMARC; e-postautentiseringstekniker som hjälper till att lösa problemet med förfalskning och nätfiske genom att verifiera att domänen som skickar e-postmeddelandet har behörighet att göra det.</span><span class="sxs-lookup"><span data-stu-id="46e5c-116">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="46e5c-117">EOP-filtrering påverkas av ett antal faktorer relaterade till den sändande IP, domän, autentisering, lista noggrannhet, klagomål priser, innehåll och mycket mer.</span><span class="sxs-lookup"><span data-stu-id="46e5c-117">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="46e5c-118">Av dessa, en av de viktigaste faktorerna för att köra ner en avsändare rykte och deras förmåga att leverera e-post är deras skräp e klagomål takt.</span><span class="sxs-lookup"><span data-stu-id="46e5c-118">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

### <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="46e5c-119">Skickar du e-post från nya IP-adresser?</span><span class="sxs-lookup"><span data-stu-id="46e5c-119">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="46e5c-120">IP-adresser som inte tidigare använts för att skicka e-post har vanligtvis inget rykte byggt upp i våra system.</span><span class="sxs-lookup"><span data-stu-id="46e5c-120">IP addresses not previously used to send email typically don't have any reputation built up in our systems.</span></span> <span data-ttu-id="46e5c-121">Som ett resultat, e-post från nya IPs är mer benägna att uppleva leveransproblem.</span><span class="sxs-lookup"><span data-stu-id="46e5c-121">As a result, emails from new IPs are more likely to experience delivery issues.</span></span> <span data-ttu-id="46e5c-122">När IP har byggt upp ett rykte för att inte skicka skräppost, eop kommer vanligtvis att möjliggöra en bättre e-postleverans upplevelse.</span><span class="sxs-lookup"><span data-stu-id="46e5c-122">Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="46e5c-123">Nya IPs som läggs till för domäner som autentiseras under befintliga SPF-poster får vanligtvis den extra fördelen att ärva en del av domänens sändningsrykte.</span><span class="sxs-lookup"><span data-stu-id="46e5c-123">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation.</span></span> <span data-ttu-id="46e5c-124">Om din domän har ett gott sändningsrykt kan nya IPs uppleva en snabbare uppramptid.</span><span class="sxs-lookup"><span data-stu-id="46e5c-124">If your domain has a good sending reputation new IPs may experience a faster ramp up time.</span></span> <span data-ttu-id="46e5c-125">En ny IP kan förvänta sig att vara helt ramped inom ett par veckor eller tidigare beroende på volym, lista noggrannhet och skräp e-post klagomål priser.</span><span class="sxs-lookup"><span data-stu-id="46e5c-125">A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

### <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="46e5c-126">Bekräfta att DNS:en är korrekt konfigurerad</span><span class="sxs-lookup"><span data-stu-id="46e5c-126">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="46e5c-127">Om du vill ha instruktioner om hur du skapar och underhåller DNS-poster, inklusive MX-posten som krävs för e-postroutning, måste du kontakta din DNS-värd.</span><span class="sxs-lookup"><span data-stu-id="46e5c-127">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

### <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="46e5c-128">Se till att du inte annonserar själv som en icke-dirigerbar IP</span><span class="sxs-lookup"><span data-stu-id="46e5c-128">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="46e5c-129">Vi kanske inte accepterar e-post från avsändare som misslyckas med en omvänd DNS-sökning.</span><span class="sxs-lookup"><span data-stu-id="46e5c-129">We may not accept email from senders who fail a reverse-DNS lookup.</span></span> <span data-ttu-id="46e5c-130">I vissa fall annonserar legitima avsändare sig felaktigt som en icke-internetdigerbar IP när de försöker öppna en anslutning till EOP.</span><span class="sxs-lookup"><span data-stu-id="46e5c-130">In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP.</span></span> <span data-ttu-id="46e5c-131">IP-adresser som är reserverade för privata (icke-dirigerbara) nätverk inkluderar:</span><span class="sxs-lookup"><span data-stu-id="46e5c-131">IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="46e5c-132">192.168.0.0/16 (eller 192.168.0.0 - 192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="46e5c-132">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>

- <span data-ttu-id="46e5c-133">10.0.0.0/8 (eller 10.0.0.0 - 10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="46e5c-133">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>

- <span data-ttu-id="46e5c-134">172.16.0.0/11 (eller 172.16.0.0 - 172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="46e5c-134">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

### <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="46e5c-135">Du har fått en rapport om utebliven leverans (NDR) när du skickade e-post till en användare i Office 365</span><span class="sxs-lookup"><span data-stu-id="46e5c-135">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="46e5c-136">Vissa leveransproblem är resultatet av att avsändarens IP-adress blockeras av Microsoft eller på att användarkontot identifieras som förbjudna avsändare på grund av tidigare skräppostaktivitet.</span><span class="sxs-lookup"><span data-stu-id="46e5c-136">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity.</span></span> <span data-ttu-id="46e5c-137">Om du tror att du har fått NDR av misstag, följ först eventuella instruktioner i NDR-meddelandet för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="46e5c-137">If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="46e5c-138">Mer information om felet du fick finns i listan över felkoder i [rapporter om utebliven leverans via e-post i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="46e5c-138">For more information about the error you received, see the list of error codes in [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

 <span data-ttu-id="46e5c-139">Om du till exempel får följande NDR anger den att den sändande IP-adressen har blockerats av Microsoft.</span><span class="sxs-lookup"><span data-stu-id="46e5c-139">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft.</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="46e5c-140">Om du vill begära borttagning från den här listan kan du [använda avlistningsportalen för att ta bort dig själv från listan Blockerade avsändare i Office 365](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span><span class="sxs-lookup"><span data-stu-id="46e5c-140">To request removal from this list, you can [Use the delist portal to remove yourself from the Office 365 blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

### <a name="my-email-landed-in-the-recipients-junk-folder-in-eop"></a><span data-ttu-id="46e5c-141">Min e-post landade i mottagarens skräppostmapp i EOP</span><span class="sxs-lookup"><span data-stu-id="46e5c-141">My email landed in the recipient's junk folder in EOP</span></span>

<span data-ttu-id="46e5c-142">Om ett meddelande felaktigt har identifierats som skräppost av EOP kan du arbeta med mottagaren för att skicka det här falska positiva meddelandet till Microsoft Spam Analysis Team, som utvärderar och analyserar meddelandet.</span><span class="sxs-lookup"><span data-stu-id="46e5c-142">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="46e5c-143">Beroende på resultatet av analysen kan reglerna för skräppostinnehållsfilter justeras så att meddelandet kan skickas igenom.</span><span class="sxs-lookup"><span data-stu-id="46e5c-143">Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span> <span data-ttu-id="46e5c-144">Du använder e-post för att skicka meddelanden till Microsoft som inte bör klassificeras som skräppost.</span><span class="sxs-lookup"><span data-stu-id="46e5c-144">You use email to submit messages to Microsoft that should not be classified as spam.</span></span> <span data-ttu-id="46e5c-145">När du gör det, se till att använda stegen i följande procedur.</span><span class="sxs-lookup"><span data-stu-id="46e5c-145">When doing so, be sure to use the steps in the following procedure.</span></span>

### <a name="to-use-email-to-submit-false-positive-messages-to-the-microsoft-spam-analysis-team"></a><span data-ttu-id="46e5c-146">Så här använder du e-post för att skicka falska positiva meddelanden till Microsoft Spam Analysis Team</span><span class="sxs-lookup"><span data-stu-id="46e5c-146">To use email to submit false positive messages to the Microsoft Spam Analysis Team</span></span>

1. <span data-ttu-id="46e5c-147">Spara meddelandet som du vill skicka som icke-skräppost.</span><span class="sxs-lookup"><span data-stu-id="46e5c-147">Save the message you want to submit as non-spam.</span></span>

2. <span data-ttu-id="46e5c-148">Skapa ett nytt, tomt meddelande och bifoga meddelandet om icke-skräppost till det.</span><span class="sxs-lookup"><span data-stu-id="46e5c-148">Create a new, blank message and attach the non-spam message to it.</span></span>

    <span data-ttu-id="46e5c-149">Du kan bifoga flera meddelanden som inte är skräppost om det behövs.</span><span class="sxs-lookup"><span data-stu-id="46e5c-149">You can attach multiple non-spam messages if needed.</span></span>

3. <span data-ttu-id="46e5c-150">Kopiera och klistra in den ursprungliga meddelandeämnesraden i den nya ämnesraden för meddelande.</span><span class="sxs-lookup"><span data-stu-id="46e5c-150">Copy and paste the original message subject line into the new message subject line.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="46e5c-151">Lämna brödtexten i det nya meddelandet tom.</span><span class="sxs-lookup"><span data-stu-id="46e5c-151">Leave the body of the new message empty.</span></span>

4. <span data-ttu-id="46e5c-152">Skicka det nya meddelandet till [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="46e5c-152">Send your new message to [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).</span></span>

### <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="46e5c-153">Trafiken från min IP-adress begränsas av EOP</span><span class="sxs-lookup"><span data-stu-id="46e5c-153">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="46e5c-154">Om du får en NDR från EOP som anger att din IP-adress begränsas av EOP, till exempel:</span><span class="sxs-lookup"><span data-stu-id="46e5c-154">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="46e5c-155">Du har fått NDR eftersom misstänkt aktivitet har upptäckts från IP-adressen och den har begränsats tillfälligt medan den utvärderas ytterligare.</span><span class="sxs-lookup"><span data-stu-id="46e5c-155">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated.</span></span> <span data-ttu-id="46e5c-156">Om misstanken undanröjs genom utvärdering kommer denna begränsning att hävas inom kort.</span><span class="sxs-lookup"><span data-stu-id="46e5c-156">If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

### <a name="i-cant-receive-email-from-senders-in-office-365"></a><span data-ttu-id="46e5c-157">Jag kan inte ta emot e-post från avsändare i Office 365</span><span class="sxs-lookup"><span data-stu-id="46e5c-157">I can't receive email from senders in Office 365</span></span>

 <span data-ttu-id="46e5c-158">För att ta emot meddelanden från våra användare, se till att ditt nätverk tillåter anslutningar från IP-adresser som EOP använder i våra datacenter.</span><span class="sxs-lookup"><span data-stu-id="46e5c-158">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="46e5c-159">Mer information finns i [Exchange Online Protection IP-adresser](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="46e5c-159">For more information, see [Exchange Online Protection IP addresses](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

## <a name="best-practices-for-bulk-emailing-to-office-365-users"></a><span data-ttu-id="46e5c-160">Metodtips för massutskick av e-post till Office 365-användare</span><span class="sxs-lookup"><span data-stu-id="46e5c-160">Best practices for bulk emailing to Office 365 users</span></span>

<span data-ttu-id="46e5c-161">Om du ofta genomför massutskick av e-post till Office 365-användare och vill se till att dina e-postmeddelanden kommer fram på ett säkert och snabbt sätt följer du tipsen i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="46e5c-161">If you often conduct bulk email campaigns to Office 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="46e5c-162">Se till att namnet Från: återspeglar vem som skickar meddelandet</span><span class="sxs-lookup"><span data-stu-id="46e5c-162">Ensure that the From: name reflects who is sending the message</span></span>

<span data-ttu-id="46e5c-163">Ämnet bör vara en kort sammanfattning av vad meddelandet handlar om, och meddelandetexten bör tydligt och kortfattat ange vad erbjudandet, tjänsten eller produkten handlar om.</span><span class="sxs-lookup"><span data-stu-id="46e5c-163">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about.</span></span> <span data-ttu-id="46e5c-164">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="46e5c-164">For example:</span></span>

<span data-ttu-id="46e5c-165">Korrekt:</span><span class="sxs-lookup"><span data-stu-id="46e5c-165">Correct:</span></span>

> <span data-ttu-id="46e5c-166">Från: marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="46e5c-166">From: marketing@shoppershandbag.com</span></span> <br/> <span data-ttu-id="46e5c-167">Ämne: Uppdaterad katalog för julen!</span><span class="sxs-lookup"><span data-stu-id="46e5c-167">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="46e5c-168">Felaktig:</span><span class="sxs-lookup"><span data-stu-id="46e5c-168">Incorrect:</span></span>

> <span data-ttu-id="46e5c-169">Från: someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="46e5c-169">From: someone@outlook.com</span></span> <br/> <span data-ttu-id="46e5c-170">Ämne: Kataloger</span><span class="sxs-lookup"><span data-stu-id="46e5c-170">Subject: Catalogs</span></span>

<span data-ttu-id="46e5c-171">Ju lättare du gör det för människor att veta vem du är och vad du gör, desto mindre svårigheter kommer du att ha leverera genom de flesta spamfilter.</span><span class="sxs-lookup"><span data-stu-id="46e5c-171">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="46e5c-172">Inkludera alltid ett alternativ för att avsluta prenumerationen i kampanjmeddelanden</span><span class="sxs-lookup"><span data-stu-id="46e5c-172">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="46e5c-173">Marknadsföring e-post, särskilt nyhetsbrev, bör alltid innehålla ett sätt att avregistrera sig från framtida e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="46e5c-173">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails.</span></span> <span data-ttu-id="46e5c-174">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="46e5c-174">For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

<span data-ttu-id="46e5c-175">Vissa avsändare inkluderar det här alternativet genom att kräva att mottagarna skickar ett e-postmeddelande till ett visst alias med "Avsluta prenumeration" i ämnet.</span><span class="sxs-lookup"><span data-stu-id="46e5c-175">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject.</span></span> <span data-ttu-id="46e5c-176">Detta är inte att föredra framför ett klick exempel ovan.</span><span class="sxs-lookup"><span data-stu-id="46e5c-176">This is not preferable to the one-click example above.</span></span> <span data-ttu-id="46e5c-177">Om du väljer att kräva att mottagarna skickar ett e-postmeddelande kontrollerar du att alla obligatoriska fält är förifyllda när de klickar på länken.</span><span class="sxs-lookup"><span data-stu-id="46e5c-177">If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="46e5c-178">Använd alternativet dubbel opt-in för marknadsföring e-post eller nyhetsbrev registrering</span><span class="sxs-lookup"><span data-stu-id="46e5c-178">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="46e5c-179">Den här bästa branschen rekommenderas om ditt företag kräver eller uppmuntrar användare att registrera sina kontaktuppgifter för att få tillgång till din produkt eller dina tjänster.</span><span class="sxs-lookup"><span data-stu-id="46e5c-179">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services.</span></span> <span data-ttu-id="46e5c-180">Vissa företag gör det till en praxis att automatiskt registrera sina användare för marknadsföring e-post eller e-nyhetsbrev under registreringsprocessen, men detta anses vara en tvivelaktig marknadsföring praxis i en värld av e-filtrering.</span><span class="sxs-lookup"><span data-stu-id="46e5c-180">Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="46e5c-181">Under registreringsprocessen, om "Ja, skicka mig ditt nyhetsbrev" eller "Ja, skicka mig specialerbjudanden" kryssrutan väljs som standard, användare som inte betalar stor uppmärksamhet kan oavsiktligt registrera dig för marknadsföring e-post eller nyhetsbrev som de inte vill få.</span><span class="sxs-lookup"><span data-stu-id="46e5c-181">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="46e5c-182">Vi rekommenderar alternativet dubbel opt-in i stället, vilket innebär att kryssrutan för marknadsföring av e-postmeddelanden eller nyhetsbrev är avmarkerad som standard.</span><span class="sxs-lookup"><span data-stu-id="46e5c-182">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default.</span></span> <span data-ttu-id="46e5c-183">Dessutom, när registreringsformuläret har skickats, en verifiering e-post skickas till användaren med en webbadress som tillåter dem att bekräfta sitt beslut att ta emot marknadsföring e-post.</span><span class="sxs-lookup"><span data-stu-id="46e5c-183">Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="46e5c-184">Detta bidrar till att säkerställa att endast de användare som vill få marknadsföring e-post är registrerade för e-post, därefter rensa det sändande företaget av tvivelaktiga e-postmarknadsföring praxis.</span><span class="sxs-lookup"><span data-stu-id="46e5c-184">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="46e5c-185">Se till att e-postmeddelandets innehåll är genomskinligt och spårbart</span><span class="sxs-lookup"><span data-stu-id="46e5c-185">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="46e5c-186">Lika viktigt som hur e-postmeddelandena skickas är innehållet de innehåller.</span><span class="sxs-lookup"><span data-stu-id="46e5c-186">Just as important as the way the emails are sent is the content they contain.</span></span> <span data-ttu-id="46e5c-187">När du skapar e-postinnehåll använder du följande metodtips för att se till att dina e-postmeddelanden inte flaggas av e-postfiltreringstjänster:</span><span class="sxs-lookup"><span data-stu-id="46e5c-187">When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="46e5c-188">När e-postmeddelandet begär att mottagarna lägger till avsändaren i adressboken, bör det tydligt anges att en sådan åtgärd inte är en garanti för leverans.</span><span class="sxs-lookup"><span data-stu-id="46e5c-188">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="46e5c-189">Omdirigeringar som ingår i meddelandets brödtext ska vara lika och konsekventa och inte flera och varierande.</span><span class="sxs-lookup"><span data-stu-id="46e5c-189">Redirects included in the body of the message should be similar and consistent, and not multiple and varied.</span></span> <span data-ttu-id="46e5c-190">En omdirigering i det här sammanhanget är allt som pekar bort från meddelandet, till exempel länkar och dokument.</span><span class="sxs-lookup"><span data-stu-id="46e5c-190">A redirect in this context is anything that points away from the message, such as links and documents.</span></span> <span data-ttu-id="46e5c-191">Om du har många annonserings- eller unsubscribe-länkar eller uppdatera profillänkarna bör de alla peka på samma domän.</span><span class="sxs-lookup"><span data-stu-id="46e5c-191">If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain.</span></span> <span data-ttu-id="46e5c-192">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="46e5c-192">For example:</span></span>

  <span data-ttu-id="46e5c-193">Korrekt:</span><span class="sxs-lookup"><span data-stu-id="46e5c-193">Correct:</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="46e5c-194">Felaktig:</span><span class="sxs-lookup"><span data-stu-id="46e5c-194">Incorrect:</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="46e5c-195">Undvik innehåll med stora bilder och bifogade filer eller meddelanden som enbart består av en bild.</span><span class="sxs-lookup"><span data-stu-id="46e5c-195">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="46e5c-196">Din offentliga integritet eller P3P-inställningar bör tydligt ange förekomsten av spårningspixlar (webbbuggar eller beacons).</span><span class="sxs-lookup"><span data-stu-id="46e5c-196">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="46e5c-197">Ta bort felaktiga e-postalias från databaserna</span><span class="sxs-lookup"><span data-stu-id="46e5c-197">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="46e5c-198">Alla e-postalias i databasen som skapar en studsa tillbaka är onödigt och sätter dina utgående e-postmeddelanden i riskzonen för ytterligare granskning av e-filtreringstjänster.</span><span class="sxs-lookup"><span data-stu-id="46e5c-198">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services.</span></span> <span data-ttu-id="46e5c-199">Se till att din e-postdatabas är uppdaterad.</span><span class="sxs-lookup"><span data-stu-id="46e5c-199">Ensure that your email database is up-to-date.</span></span>
