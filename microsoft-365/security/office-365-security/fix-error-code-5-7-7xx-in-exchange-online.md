---
title: Åtgärda problem med e-postleverans för felkod 5.7.7xx i Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Läs om hur du åtgärdar e-postproblem för felkod 5.7.7xx i Exchange Online (klienten blockeras från att skicka e-post).
ms.openlocfilehash: e8e134793db946ddfc3ef09d0adc19b2a04df30b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810738"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a><span data-ttu-id="b98de-103">Åtgärda problem med e-postleverans för felkod 5.7.7xx i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b98de-103">Fix email delivery issues for error code 5.7.7xx in Exchange Online</span></span>

<span data-ttu-id="b98de-104">I det här avsnittet beskrivs vad du kan göra om du ser statuskoden 550 5.7.7xx i en rapport om utebliven leverans (kallas även NDR, avvisningsmeddelande, leveransstatusmeddelande eller DSN).</span><span class="sxs-lookup"><span data-stu-id="b98de-104">This topic describes what you can do if you see status code 550 5.7.7xx in a non-delivery report (also known as an NDR, bounce message, delivery status notification, or DSN).</span></span> <span data-ttu-id="b98de-105">Den här automatiska aviseringen visas när din klient är begränsad från att skicka e-post på ett eller annat sätt.</span><span class="sxs-lookup"><span data-stu-id="b98de-105">You'll see this automated notification when your tenant is restricted from sending email in one way or another.</span></span> <span data-ttu-id="b98de-106">Dessa felkoder kommer vanligtvis in som 705 eller 750.</span><span class="sxs-lookup"><span data-stu-id="b98de-106">These error codes will usually come in as 705 or 750.</span></span>

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a><span data-ttu-id="b98de-107">5.7.705: Hyresgästen har överskridit tröskelbegränsning: Vad du behöver veta</span><span class="sxs-lookup"><span data-stu-id="b98de-107">5.7.705: Tenant has exceeded threshold restriction: What you need to know</span></span>

<span data-ttu-id="b98de-108">När användarna (kollektivt, som organisation) skickar en viss mängd misstänkt e-post via tjänsten, kan alla användare hindras från att skicka e-post tills problemet är åtgärdat.</span><span class="sxs-lookup"><span data-stu-id="b98de-108">Once your users (collectively, as organization) send a certain amount of suspicious email through the service, all users can be prevented from sending any email until the problem is fixed.</span></span> <span data-ttu-id="b98de-109">Detta är vanligtvis resultatet av en kompromiss (vanligast) eller skicka för mycket massutskick.</span><span class="sxs-lookup"><span data-stu-id="b98de-109">This is usually the result of a compromise (most common) or sending too much bulk mail.</span></span> <span data-ttu-id="b98de-110">Användare får en NDR som anger:</span><span class="sxs-lookup"><span data-stu-id="b98de-110">Users will receive an NDR that states:</span></span>

`550 5.7.705 Access denied, tenant has exceeded threshold`

<span data-ttu-id="b98de-111">I sällsynta fall kan detta också inträffa om du förnyar prenumerationen när den redan har upphört att gälla.</span><span class="sxs-lookup"><span data-stu-id="b98de-111">In rare cases, this could also happen if you renew your subscription after it has already expired.</span></span> <span data-ttu-id="b98de-112">Det tar tid för tjänsten att synkronisera den nya prenumerationsinformationen (vanligtvis inte mer än en dag), men din organisation kan blockeras från att skicka e-post under tiden.</span><span class="sxs-lookup"><span data-stu-id="b98de-112">It takes time for the service to sync the new subscription information (typically, no more than one day), but your organization could be blocked from sending email in the meantime.</span></span> <span data-ttu-id="b98de-113">Det bästa sättet att förhindra detta är att se till att din prenumeration inte upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="b98de-113">The best way to prevent this is to make sure your subscription does not expire.</span></span>

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a><span data-ttu-id="b98de-114">5.7.750: Oregistrerad domän e-begränsning: Vad du behöver veta</span><span class="sxs-lookup"><span data-stu-id="b98de-114">5.7.750: Unregistered Domain Email restriction: What you need to know</span></span>

<span data-ttu-id="b98de-115">Med Office 365 kan klienter vidarebefordra vissa meddelanden via Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="b98de-115">Office 365 allows tenants to relay some messages through Exchange Online Protection (EOP).</span></span> <span data-ttu-id="b98de-116">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="b98de-116">For example:</span></span>

- <span data-ttu-id="b98de-117">En Office 365-postlåda tar emot e-post från en extern avsändare.</span><span class="sxs-lookup"><span data-stu-id="b98de-117">An Office 365 mailbox receives email from an external sender.</span></span> <span data-ttu-id="b98de-118">Vidarebefordring av e-post är konfigurerad i Office 365-postlådan, så meddelandet skickas tillbaka till användarens externa e-postadress.</span><span class="sxs-lookup"><span data-stu-id="b98de-118">Mail forwarding is configured on the Office 365 mailbox, so the message goes back out to the user's external email address.</span></span> <span data-ttu-id="b98de-119">Det här scenariot är vanligast i utbildningsmiljöer där eleverna vill använda sina personliga e-postkonton för att visa skolrelaterade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="b98de-119">This scenario is most common in education environments where students want to use their personal email accounts to view school-related messages.</span></span>

- <span data-ttu-id="b98de-120">Hybridmiljöer som har lokala e-postservrar som skickar utgående e-post via EOP.</span><span class="sxs-lookup"><span data-stu-id="b98de-120">Hybrid environments that have on-premises email servers that send outgoing mail through EOP.</span></span>

### <a name="problems-with-unregistered-domains"></a><span data-ttu-id="b98de-121">Problem med oregistrerade domäner</span><span class="sxs-lookup"><span data-stu-id="b98de-121">Problems with unregistered domains</span></span>

<span data-ttu-id="b98de-122">Problemet är när äventyras lokala e-postservrar vidarebefordra en stor mängd spam via EOP.</span><span class="sxs-lookup"><span data-stu-id="b98de-122">The problem is when compromised on-premises email servers relay a large volume of spam through EOP.</span></span> <span data-ttu-id="b98de-123">I nästan alla fall är kopplingarna korrekt inställda, men e-post skickas från oregistrerade (kallas även oetablerade) domäner.</span><span class="sxs-lookup"><span data-stu-id="b98de-123">In almost all cases, the connectors are set up correctly, but email is being sent from unregistered (also known as unprovisioned) domains.</span></span> <span data-ttu-id="b98de-124">Office 365 tillåter en rimlig mängd e-post från oregistrerade domäner, men du bör konfigurera alla domäner som du använder för att skicka e-post som en accepterad domän.</span><span class="sxs-lookup"><span data-stu-id="b98de-124">Office 365 allows a reasonable amount of email from unregistered domains, but you should configure every domain that you use to send email as an accepted domain.</span></span>

<span data-ttu-id="b98de-125">När komprometteras förhindras klienter från att skicka utgående e-post för oregistrerade domäner.</span><span class="sxs-lookup"><span data-stu-id="b98de-125">Once compromised, tenants will be prevented from sending outbound email for unregistered domains.</span></span> <span data-ttu-id="b98de-126">Användare får en NDR som anger:</span><span class="sxs-lookup"><span data-stu-id="b98de-126">Users will receive an NDR that states:</span></span>

`550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains`

## <a name="unblocking-tenant-in-order-to-send-again"></a><span data-ttu-id="b98de-127">Avblockera klienten för att skicka igen</span><span class="sxs-lookup"><span data-stu-id="b98de-127">Unblocking tenant in order to send again</span></span>

<span data-ttu-id="b98de-128">Det finns flera saker du behöver göra om din klient är blockerad från att skicka e-post:</span><span class="sxs-lookup"><span data-stu-id="b98de-128">There are several things you need to do if your tenant is blocked from sending email:</span></span>

1. <span data-ttu-id="b98de-129">Ändra lösenordet för dina administratörskonton.</span><span class="sxs-lookup"><span data-stu-id="b98de-129">Change the password for your admin accounts.</span></span> <span data-ttu-id="b98de-130">Om en klient har blockerats från att skicka är det mest troligt att ett administratörskonto komprometterades.</span><span class="sxs-lookup"><span data-stu-id="b98de-130">If a tenant is blocked from sending, it's most likely that an admin account was compromised.</span></span> <span data-ttu-id="b98de-131">Att ändra lösenord är det första steget för att förhindra att angriparen gör mer skada.</span><span class="sxs-lookup"><span data-stu-id="b98de-131">Changing passwords is the first step to prevent the attacker from doing more harm.</span></span>

2. <span data-ttu-id="b98de-132">[Aktivera MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) för alla administratörer i office 365-organisationen.</span><span class="sxs-lookup"><span data-stu-id="b98de-132">[Enable MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) for all admins in your Office 365 organization.</span></span>

3. <span data-ttu-id="b98de-133">Kontrollera att alla dina e-postdomäner är registrerade.</span><span class="sxs-lookup"><span data-stu-id="b98de-133">Verify that all of your email domains are registered.</span></span> <span data-ttu-id="b98de-134">Mer information finns i [Lägga till en domän i Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain) och Hantera godkända [domäner i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="b98de-134">For more information, see [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain) and [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

4. <span data-ttu-id="b98de-135">Leta efter ovanliga [kontakter](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="b98de-135">Look for unusual [connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> <span data-ttu-id="b98de-136">Skadliga aktörer skapar ofta nya inkommande kopplingar i Office 365-organisationen för att skicka skräppost.</span><span class="sxs-lookup"><span data-stu-id="b98de-136">Malicious actors will often create new inbound connectors in your Office 365 organization to send spam.</span></span> <span data-ttu-id="b98de-137">Information om hur du visar befintliga kopplingar finns [i Validera kopplingar i Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors).</span><span class="sxs-lookup"><span data-stu-id="b98de-137">To view your existing connectors, see [Validate connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors).</span></span>

5. <span data-ttu-id="b98de-138">Sök efter komprometterade användare enligt beskrivningen i [Svara på ett komprometterat e-postkonto i Office 365](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="b98de-138">Check for compromised users as described in [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

6. <span data-ttu-id="b98de-139">Lås dina lokala e-postservrar och kontrollera att de inte äventyras.</span><span class="sxs-lookup"><span data-stu-id="b98de-139">Lock down your on-premises email servers and verify that they are not compromised.</span></span>

   > [!TIP]
   > <span data-ttu-id="b98de-140">Det finns många faktorer här, särskilt om du använder servrar från tredje part.</span><span class="sxs-lookup"><span data-stu-id="b98de-140">There are many factors here, especially if you're using third-party servers.</span></span> <span data-ttu-id="b98de-141">Oavsett måste du kontrollera att din utgående e-post inte innehåller skräppost.</span><span class="sxs-lookup"><span data-stu-id="b98de-141">Regardless, you'll need to verify that your outgoing mail does not include spam.</span></span>

7. <span data-ttu-id="b98de-142">Ring Microsoft Support och be att få din klient avblockerad för att skicka e-post igen.</span><span class="sxs-lookup"><span data-stu-id="b98de-142">Call Microsoft Support and ask to get your tenant unblocked to send email again.</span></span> <span data-ttu-id="b98de-143">Felkoden är användbar, men du måste bevisa att din miljö har säkrats och är oförmögen att skicka skräppost.</span><span class="sxs-lookup"><span data-stu-id="b98de-143">The error code is helpful, but you'll need to prove that your environment has been secured and is incapable of sending spam.</span></span> <span data-ttu-id="b98de-144">Information om hur du öppnar ett supportärende finns i [Kontakta support för företagsprodukter - Hjälp om administratörer](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="b98de-144">To open a support case, see [Contact support for business products - Admin Help](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>

## <a name="for-more-information"></a><span data-ttu-id="b98de-145">Mer information</span><span class="sxs-lookup"><span data-stu-id="b98de-145">For more information</span></span>

[<span data-ttu-id="b98de-146">Office 365 email anti-spam protection</span><span class="sxs-lookup"><span data-stu-id="b98de-146">Office 365 email anti-spam protection</span></span>](anti-spam-protection.md)

[<span data-ttu-id="b98de-147">Massutskicksvägledning i avsnittet Sändningsgränser i exchange online-tjänstens beskrivning</span><span class="sxs-lookup"><span data-stu-id="b98de-147">Bulk Mail guidance in the sending limits section of the Exchange Online service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)

[<span data-ttu-id="b98de-148">NDR-rapporter via e-post i Office 365</span><span class="sxs-lookup"><span data-stu-id="b98de-148">Email non-delivery reports in Office 365</span></span>](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

[<span data-ttu-id="b98de-149">Konfigurera vidarebefordran av e-post för en postlåda</span><span class="sxs-lookup"><span data-stu-id="b98de-149">Configure email forwarding for a mailbox</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[<span data-ttu-id="b98de-150">Konfigurera en multifunktionsenhet eller ett multifunktionsprogram för att skicka e-post med hjälp av Office 365</span><span class="sxs-lookup"><span data-stu-id="b98de-150">How to set up a multifunction device or application to send email using Office 365</span></span>](https://docs.microsoft.com/Exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-office-3)

<span data-ttu-id="b98de-151">[Hantera godkända domäner i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="b98de-151">[Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>
