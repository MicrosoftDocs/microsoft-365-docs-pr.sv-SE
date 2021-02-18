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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Den här artikeln innehåller felsökningsinformation för problem med att skicka e-post till inkorgar i Microsoft 365 & metodtips för massutskick till Microsoft 365-kunder.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1e4a91f70b59debc770a5811638bd64a1eef36dd
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286387"
---
# <a name="troubleshooting-mail-sent-to-microsoft-365"></a><span data-ttu-id="9b2c3-103">Felsöka e-post som skickas till Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9b2c3-103">Troubleshooting mail sent to Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9b2c3-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="9b2c3-104">**Applies to**</span></span>
- [<span data-ttu-id="9b2c3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9b2c3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9b2c3-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="9b2c3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

<span data-ttu-id="9b2c3-107">Den här artikeln innehåller felsökningsinformation för avsändare som har problem med att skicka e-post till inkorgar i Microsoft 365 och rekommendationer för massutskick till kunder.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-107">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Microsoft 365 and best practices for bulk mailing to customers.</span></span>

## <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="9b2c3-108">Hanterar du ditt IP- och domäns rykte?</span><span class="sxs-lookup"><span data-stu-id="9b2c3-108">Are you managing your IP and domain's sending reputation?</span></span>

<span data-ttu-id="9b2c3-109">EOP-filtreringstekniken är utformad för att skydda mot skräppost för Microsoft 365 och andra Microsoft-produkter som Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-109">EOP filtering technologies are designed to provide anti-spam protection for Microsoft 365 as well as other Microsoft products like Exchange Server.</span></span> <span data-ttu-id="9b2c3-110">Vi använder även SPF, DKIM och DMARC. E-postautentiseringsteknik som hjälper dig att lösa problemet med förfalskning och nätfiske genom att verifiera att den domän som skickar e-postmeddelandet har behörighet att göra det.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-110">We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so.</span></span> <span data-ttu-id="9b2c3-111">EOP-filtrering påverkas av ett antal faktorer relaterade till avsändande IP, domän, autentisering, korrekt lista, klagomålshastigheter, innehåll med mera.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-111">EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more.</span></span> <span data-ttu-id="9b2c3-112">Av dessa är en av de viktigaste faktorerna för att skada avsändarens rykte och möjligheten att leverera e-post är klagomålsfrekvensen för skräppost.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-112">Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span>

## <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="9b2c3-113">Skickar du e-post från nya IP-adresser?</span><span class="sxs-lookup"><span data-stu-id="9b2c3-113">Are you sending email from new IP addresses?</span></span>

<span data-ttu-id="9b2c3-114">IP-adresser som inte tidigare använts för att skicka e-post har vanligtvis inte något rykte uppbyggt i våra system.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-114">IP addresses not previously used to send email typically don't have any reputation built up in our systems.</span></span> <span data-ttu-id="9b2c3-115">Därför är det troligare att e-postmeddelanden från nya IP-adresser upplever leveransproblem.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-115">As a result, emails from new IPs are more likely to experience delivery issues.</span></span> <span data-ttu-id="9b2c3-116">När IP-adressen har skapat ett rykte för att inte skicka skräppost ger EOP vanligtvis bättre upplevelse för e-postleverans.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-116">Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>

<span data-ttu-id="9b2c3-117">Nya IP-adresser som läggs till för domäner som autentiseras under befintliga SPF-poster har vanligtvis den extra fördelen att ärva en del av domänens sändande rykte.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-117">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation.</span></span> <span data-ttu-id="9b2c3-118">Om din domän har goda möjligheter att skicka ryktet för nya IP-adresser kan det gå snabbare.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-118">If your domain has a good sending reputation new IPs may experience a faster ramp up time.</span></span> <span data-ttu-id="9b2c3-119">En ny IP-adress kan förväntas bli helt nyare inom några veckor eller tidigare beroende på volym, listprecision och klagomålsfrekvens för skräppost.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-119">A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>

## <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="9b2c3-120">Bekräfta att DNS-posterna är korrekt konfigurerade</span><span class="sxs-lookup"><span data-stu-id="9b2c3-120">Confirm that your DNS is set up correctly</span></span>

<span data-ttu-id="9b2c3-121">Om du vill ha anvisningar om hur du skapar och underhåller DNS-poster, inklusive den MX-post som krävs för e-postdirigering, måste du kontakta din DNS-värd.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-121">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>

## <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="9b2c3-122">Se till att du inte annonserar dig själv som icke-dirigerbar IP</span><span class="sxs-lookup"><span data-stu-id="9b2c3-122">Ensure that you do not advertise yourself as a non-routable IP</span></span>

<span data-ttu-id="9b2c3-123">Vi kanske inte accepterar e-post från avsändare som misslyckas med en omvänd DNS-sökning.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-123">We may not accept email from senders who fail a reverse-DNS lookup.</span></span> <span data-ttu-id="9b2c3-124">I vissa fall annonserar legitima avsändare sig själva felaktigt som en icke-dirigerbar IP när de försöker öppna en anslutning till EOP.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-124">In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP.</span></span> <span data-ttu-id="9b2c3-125">IP-adresser som är reserverade för privata (icke-dirigerbara) nätverk:</span><span class="sxs-lookup"><span data-stu-id="9b2c3-125">IP addresses that are reserved for private (non-routable) networking include:</span></span>

- <span data-ttu-id="9b2c3-126">192.168.0.0/16 (eller 192.168.0.0 - 192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="9b2c3-126">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>
- <span data-ttu-id="9b2c3-127">10.0.0.0/8 (eller 10.0.0.0 - 10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="9b2c3-127">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>
- <span data-ttu-id="9b2c3-128">172.16.0.0/11 (eller 172.16.0.0 - 172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="9b2c3-128">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>

## <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="9b2c3-129">Du har fått en rapport om utebliven leverans (NDR) när du skickar e-post till en användare i Office 365</span><span class="sxs-lookup"><span data-stu-id="9b2c3-129">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>

<span data-ttu-id="9b2c3-130">Vissa leveransproblem beror på att avsändarens IP-adress blockeras av Microsoft eller att användarkontot identifieras som spärrad avsändare på grund av tidigare skräppostaktivitet.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-130">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity.</span></span> <span data-ttu-id="9b2c3-131">Om du anser att du fått NDR-meddelandet av misstag ska du först följa instruktionerna i NDR-meddelandet för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-131">If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span>

<span data-ttu-id="9b2c3-132">Mer information om felet du fick finns i listan över felkoder i rapporter om utebliven leverans via [e-post i Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)</span><span class="sxs-lookup"><span data-stu-id="9b2c3-132">For more information about the error you received, see the list of error codes in [Email non-delivery reports in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).</span></span>

 <span data-ttu-id="9b2c3-133">Om du till exempel får följande NDR visar det att den avsändande IP-adressen har blockerats av Microsoft:</span><span class="sxs-lookup"><span data-stu-id="9b2c3-133">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft:</span></span>

 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`

<span data-ttu-id="9b2c3-134">Om du vill begära borttagning från listan kan du använda [delist-portalen](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)för att ta bort dig själv från listan med spärrade avsändare.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-134">To request removal from this list, you can [Use the delist portal to remove yourself from the blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>

## <a name="my-email-landed-in-the-recipients-junk-email-folder"></a><span data-ttu-id="9b2c3-135">Mitt e-postmeddelande hamnar i mottagarens skräppostmapp</span><span class="sxs-lookup"><span data-stu-id="9b2c3-135">My email landed in the recipient's Junk Email folder</span></span>

<span data-ttu-id="9b2c3-136">Om ett meddelande felaktigt identifierats som skräppost av EOP kan du samarbeta med mottagaren för att skicka det här falska positiva meddelandet till Microsofts team för skräppostanalys, som ska utvärdera och analysera meddelandet.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-136">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message.</span></span> <span data-ttu-id="9b2c3-137">Mer informations finns i [Anmäla meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="9b2c3-137">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="9b2c3-138">Trafiken från min IP-adress begränsas av EOP</span><span class="sxs-lookup"><span data-stu-id="9b2c3-138">Traffic from my IP address is throttled by EOP</span></span>

<span data-ttu-id="9b2c3-139">Om du får en NDR från EOP som anger att din IP-adress begränsas av EOP, till exempel:</span><span class="sxs-lookup"><span data-stu-id="9b2c3-139">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>

 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`

<span data-ttu-id="9b2c3-140">Du har fått NDR eftersom misstänkt aktivitet har upptäckts från IP-adressen och den har tillfälligt begränsats medan den utvärderas ytterligare.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-140">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated.</span></span> <span data-ttu-id="9b2c3-141">Om det finns en bedömning av vad som kan göras tas begränsningen bort inom kort.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-141">If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>

## <a name="i-cant-receive-email-from-senders-in-microsoft-365"></a><span data-ttu-id="9b2c3-142">Jag kan inte ta emot e-post från avsändare i Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9b2c3-142">I can't receive email from senders in Microsoft 365</span></span>

 <span data-ttu-id="9b2c3-143">För att kunna ta emot meddelanden från våra användare ska du se till att nätverket tillåter anslutningar från IP-adresserna som EOP använder i våra datacenter.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-143">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="9b2c3-144">Mer information finns i [IP-adresser för Exchange Online Protection.](../../enterprise/urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="9b2c3-144">For more information, see [Exchange Online Protection IP addresses](../../enterprise/urls-and-ip-address-ranges.md).</span></span>

## <a name="best-practices-for-bulk-emailing-to-microsoft-365-users"></a><span data-ttu-id="9b2c3-145">Metodtips för massutskick till Microsoft 365-användare</span><span class="sxs-lookup"><span data-stu-id="9b2c3-145">Best practices for bulk emailing to Microsoft 365 users</span></span>

<span data-ttu-id="9b2c3-146">Om du ofta gör massutskick av e-postkampanjer till Microsoft 365-användare och vill se till att dina e-postmeddelanden kommer in på ett säkert sätt i rätt tid följer du tipsen i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-146">If you often conduct bulk email campaigns to Microsoft 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>

### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="9b2c3-147">Kontrollera att från-namnet motsvarar vem som skickar meddelandet</span><span class="sxs-lookup"><span data-stu-id="9b2c3-147">Ensure that the From name reflects who is sending the message</span></span>

<span data-ttu-id="9b2c3-148">Ämnet ska vara en kort sammanfattning av vad meddelandet handlar om, och meddelandets brödtext ska tydligt och tydligt ange vad erbjudandet, tjänsten eller produkten handlar om.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-148">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about.</span></span> <span data-ttu-id="9b2c3-149">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="9b2c3-149">For example:</span></span>

<span data-ttu-id="9b2c3-150">Rätt:</span><span class="sxs-lookup"><span data-stu-id="9b2c3-150">Correct:</span></span>

> <span data-ttu-id="9b2c3-151">Från: marketing@shoppershandbag.com</span><span class="sxs-lookup"><span data-stu-id="9b2c3-151">From: marketing@shoppershandbag.com</span></span> <br> <span data-ttu-id="9b2c3-152">Ämne: Uppdaterad katalog för julafton!</span><span class="sxs-lookup"><span data-stu-id="9b2c3-152">Subject: Updated catalog for the Christmas season!</span></span>

<span data-ttu-id="9b2c3-153">Fel:</span><span class="sxs-lookup"><span data-stu-id="9b2c3-153">Incorrect:</span></span>

> <span data-ttu-id="9b2c3-154">Från: someone@outlook.com</span><span class="sxs-lookup"><span data-stu-id="9b2c3-154">From: someone@outlook.com</span></span> <br> <span data-ttu-id="9b2c3-155">Ämne: Kataloger</span><span class="sxs-lookup"><span data-stu-id="9b2c3-155">Subject: Catalogs</span></span>

<span data-ttu-id="9b2c3-156">Ju enklare du gör det för andra att veta vem du är och vad du gör, desto mindre svårt är det att leverera via de flesta skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-156">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>

### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="9b2c3-157">Inkludera alltid ett alternativ för att avsluta prenumerationen i kampanjmeddelanden</span><span class="sxs-lookup"><span data-stu-id="9b2c3-157">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="9b2c3-158">Marknadsföringsmeddelanden, särskilt nyhetsbrev, bör alltid innehålla ett sätt att avsluta prenumerationen från framtida e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-158">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails.</span></span> <span data-ttu-id="9b2c3-159">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="9b2c3-159">For example:</span></span>

 `This email was sent to example@contoso.com by sender@fabrikam.com.`

 `Update Profile/Email Address | Instant removal with SafeUnsubscribe&trade; | Privacy Policy`

<span data-ttu-id="9b2c3-160">Vissa avsändare inkluderar det här alternativet genom att kräva att mottagarna skickar ett e-postmeddelande till ett visst alias med "Avbryt prenumeration" i ämnesämnet.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-160">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject.</span></span> <span data-ttu-id="9b2c3-161">Detta är inte bättre än exemplet med ett klick ovan.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-161">This is not preferable to the one-click example above.</span></span> <span data-ttu-id="9b2c3-162">Om du väljer att kräva att mottagarna skickar e-post ska du se till att alla obligatoriska fält är ifyllda när de klickar på länken.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-162">If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>

### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="9b2c3-163">Använd alternativet för dubbel registrering av e-post eller nyhetsbrev</span><span class="sxs-lookup"><span data-stu-id="9b2c3-163">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="9b2c3-164">Den här metoden rekommenderas om företaget kräver eller uppmuntrar användarna att registrera sin kontaktinformation för att få åtkomst till din produkt eller dina tjänster.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-164">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services.</span></span> <span data-ttu-id="9b2c3-165">Vissa företag gör det till en metod att automatiskt registrera sina användare för marknadsföringsmeddelanden eller e-nyhetsbrev under registreringen, men det här är en tveksam marknadsföringsmetod inom e-postfiltrering.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-165">Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>

<span data-ttu-id="9b2c3-166">Om kryssrutan "Ja, skicka mig ditt nyhetsbrev" eller "Ja, skicka specialerbjudanden" är markerad som standard under registreringen, kan användare som inte är extra noga registrera sig för reklamutskick eller nyhetsbrev som de inte vill få.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-166">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>

 <span data-ttu-id="9b2c3-167">Vi rekommenderar dubbelval i stället, vilket innebär att kryssrutan för marknadsföringsmeddelanden eller nyhetsbrev är avmarkerad som standard.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-167">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default.</span></span> <span data-ttu-id="9b2c3-168">När registreringsformuläret har skickats skickas dessutom ett e-postmeddelande med en URL till användaren för att bekräfta att han eller hon vill ta emot marknadsföringsmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-168">Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span>

 <span data-ttu-id="9b2c3-169">På så sätt kan du se till att bara de användare som vill ta emot marknadsföringsmeddelanden har registrerat sig för e-postmeddelandena, och därefter rensar företaget för alla tveksamma marknadsföringsmetoder för e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-169">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span>

### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="9b2c3-170">Kontrollera att e-postmeddelandets innehåll är transparent och kan spåras</span><span class="sxs-lookup"><span data-stu-id="9b2c3-170">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="9b2c3-171">Lika viktigt som hur e-postmeddelanden skickas är innehållet de innehåller.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-171">Just as important as the way the emails are sent is the content they contain.</span></span> <span data-ttu-id="9b2c3-172">När du skapar e-postinnehåll ska du använda följande metodtips för att säkerställa att dina e-postmeddelanden inte flaggas med e-postfiltreringstjänster:</span><span class="sxs-lookup"><span data-stu-id="9b2c3-172">When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>

- <span data-ttu-id="9b2c3-173">När e-postmeddelandet begär att mottagarna ska lägga till avsändaren i adressboken bör det tydligt anges att en sådan åtgärd inte är en leveransgaranti.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-173">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>

- <span data-ttu-id="9b2c3-174">Omdirigeringar som ingår i brödtexten i meddelandet bör vara lika och konsekventa, och inte flera och varierade.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-174">Redirects included in the body of the message should be similar and consistent, and not multiple and varied.</span></span> <span data-ttu-id="9b2c3-175">En omdirigering i det här sammanhanget är någonting som pekar bort från meddelandet, till exempel länkar och dokument.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-175">A redirect in this context is anything that points away from the message, such as links and documents.</span></span> <span data-ttu-id="9b2c3-176">Om du har många annonser eller länkar för att avsluta prenumerationen eller uppdatera profillänkarna, bör de alla peka på samma domän.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-176">If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain.</span></span> <span data-ttu-id="9b2c3-177">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="9b2c3-177">For example:</span></span>

  <span data-ttu-id="9b2c3-178">Rätt (alla domäner är desamma):</span><span class="sxs-lookup"><span data-stu-id="9b2c3-178">Correct (all domains are the same):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.bulkmailer.com`

  `options.bulkmailer.com`

  <span data-ttu-id="9b2c3-179">Fel (alla domäner är olika):</span><span class="sxs-lookup"><span data-stu-id="9b2c3-179">Incorrect (all domains are different):</span></span>

  `unsubscribe.bulkmailer.com`

  `profile.excite.com`

  `options.yahoo.com`

- <span data-ttu-id="9b2c3-180">Undvik innehåll med stora bilder och bifogade filer eller meddelanden som endast består av en bild.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-180">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>

- <span data-ttu-id="9b2c3-181">Din offentliga integritet eller P3P-inställningar bör tydligt ange förekomsten av spårningspunkter (webbbuggar eller beacons).</span><span class="sxs-lookup"><span data-stu-id="9b2c3-181">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>

### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="9b2c3-182">Ta bort felaktiga e-postalias från dina databaser</span><span class="sxs-lookup"><span data-stu-id="9b2c3-182">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="9b2c3-183">Alla e-postalias i databasen som skapar en icke-återstudsning är onödiga och innebär att dina utgående e-postmeddelanden riskerar att granskas ytterligare genom e-postfiltreringstjänster.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-183">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services.</span></span> <span data-ttu-id="9b2c3-184">Kontrollera att din e-postdatabas är uppdaterad.</span><span class="sxs-lookup"><span data-stu-id="9b2c3-184">Ensure that your email database is up-to-date.</span></span>
