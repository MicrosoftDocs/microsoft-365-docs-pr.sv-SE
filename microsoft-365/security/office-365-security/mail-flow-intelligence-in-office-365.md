---
title: Information om e-postflöde
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Administratörer kan få mer information om de felkoder som associeras med meddelandeleverans med kopplingar (kallas även för e-postflödesinformation).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f9cd05664d055b1635583c24000ca4afa604b237
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926874"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="96d4c-103">E-postflödesinformation i EOP</span><span class="sxs-lookup"><span data-stu-id="96d4c-103">Mail flow intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="96d4c-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="96d4c-104">**Applies to**</span></span>
- [<span data-ttu-id="96d4c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="96d4c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="96d4c-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="96d4c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="96d4c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="96d4c-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="96d4c-108">I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor använder du vanligtvis en anslutare för att dirigera e-postmeddelanden från EOP till din lokala e-postmiljö.</span><span class="sxs-lookup"><span data-stu-id="96d4c-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="96d4c-109">Du kan också använda en koppling för att dirigera meddelanden från Microsoft 365 till en partnerorganisation.</span><span class="sxs-lookup"><span data-stu-id="96d4c-109">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="96d4c-110">När Microsoft 365 inte kan leverera dessa meddelanden via anslutningen är de i kö i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="96d4c-110">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="96d4c-111">Microsoft 365 fortsätter att försöka leverera för varje meddelande i 24 timmar.</span><span class="sxs-lookup"><span data-stu-id="96d4c-111">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="96d4c-112">Efter 24 timmar upphör det köade meddelandet att gälla och meddelandet returneras till den ursprungliga avsändaren i en rapport om utebliven leverans (kallas även för en NDR-rapport eller icke-leveranskavsändare).</span><span class="sxs-lookup"><span data-stu-id="96d4c-112">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="96d4c-113">Microsoft 365 genererar ett fel när ett meddelande inte kan levereras med hjälp av en koppling.</span><span class="sxs-lookup"><span data-stu-id="96d4c-113">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="96d4c-114">De vanligaste felen och deras lösningar beskrivs i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="96d4c-114">The most common errors and their solutions are described in this article.</span></span> <span data-ttu-id="96d4c-115">Köer och meddelandefel för meddelanden som inte kunde levereras via kopplingar kallas gemensamt för _e-postflödesinformation._</span><span class="sxs-lookup"><span data-stu-id="96d4c-115">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="96d4c-116">Felkod: DNS-frågan 450 4.4.312 misslyckades</span><span class="sxs-lookup"><span data-stu-id="96d4c-116">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="96d4c-117">Vanligtvis innebär det här felet att Microsoft 365 försökte ansluta till den smarta värden som anges i kopplingen, men DNS-frågan för att hitta den smarta värdens IP-adresser misslyckades.</span><span class="sxs-lookup"><span data-stu-id="96d4c-117">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="96d4c-118">Möjliga orsaker till det här felet är:</span><span class="sxs-lookup"><span data-stu-id="96d4c-118">The possible causes for this error are:</span></span>

- <span data-ttu-id="96d4c-119">Det är ett problem med domänens DNS-värdtjänst (den part som upprätthåller de auktoritativa namnservrarna för domänen).</span><span class="sxs-lookup"><span data-stu-id="96d4c-119">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="96d4c-120">Domänen har nyligen upphört att gälla, så MX-posten kan inte hämtas.</span><span class="sxs-lookup"><span data-stu-id="96d4c-120">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="96d4c-121">Domänens MX-post har nyligen ändrats och DNS-servrarna har fortfarande tidigare cachelagrad DNS-information för din domän.</span><span class="sxs-lookup"><span data-stu-id="96d4c-121">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="96d4c-122">Hur åtgärdar jag felkod 450 4.4.312?</span><span class="sxs-lookup"><span data-stu-id="96d4c-122">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="96d4c-123">Arbeta med DNS-värdtjänsten för att identifiera och åtgärda problemet med din domän.</span><span class="sxs-lookup"><span data-stu-id="96d4c-123">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="96d4c-124">Om felet kommer från din partnerorganisation (t.ex. en tredjepartsleverantör av molntjänster) kontaktar du din partner för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="96d4c-124">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="96d4c-125">Felkod: 450 4.4.315 Anslutningens timed out</span><span class="sxs-lookup"><span data-stu-id="96d4c-125">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="96d4c-126">Det innebär vanligtvis att Microsoft 365 inte kan ansluta till mål-e-postservern.</span><span class="sxs-lookup"><span data-stu-id="96d4c-126">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="96d4c-127">I felinformationen förklaras problemet.</span><span class="sxs-lookup"><span data-stu-id="96d4c-127">The error details will explain the problem.</span></span> <span data-ttu-id="96d4c-128">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="96d4c-128">For example:</span></span>

- <span data-ttu-id="96d4c-129">Din lokala e-postserver ligger nere.</span><span class="sxs-lookup"><span data-stu-id="96d4c-129">Your on-premises email server is down.</span></span>

- <span data-ttu-id="96d4c-130">Det finns ett fel i anslutningens inställningar för smart värd, så Microsoft 365 försöker ansluta till fel IP-adress.</span><span class="sxs-lookup"><span data-stu-id="96d4c-130">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="96d4c-131">Hur åtgärdar jag felkod 450 4.4.315?</span><span class="sxs-lookup"><span data-stu-id="96d4c-131">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="96d4c-132">Ta reda på vilket scenario som gäller för dig och gör nödvändiga korrigeringar.</span><span class="sxs-lookup"><span data-stu-id="96d4c-132">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="96d4c-133">Om e-postflödet till exempel har fungera korrekt och du inte har ändrat anslutningsinställningarna, måste du kontrollera din lokala e-postmiljö för att se om servern ligger nere, eller om det har gjorts några ändringar i nätverksinfrastrukturen (till exempel om du har ändrat internetleverantörer så att du nu har olika IP-adresser).</span><span class="sxs-lookup"><span data-stu-id="96d4c-133">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="96d4c-134">Om felet kommer från din partnerorganisation (t.ex. en tredjepartsleverantör av molntjänster) kontaktar du din partner för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="96d4c-134">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="96d4c-135">Felkod: 450 4.4.316 Anslutningen är inte säker</span><span class="sxs-lookup"><span data-stu-id="96d4c-135">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="96d4c-136">Vanligtvis innebär det här felet att Microsoft 365 stött på ett anslutningsfel när det försökt ansluta till mål-e-postservern.</span><span class="sxs-lookup"><span data-stu-id="96d4c-136">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="96d4c-137">En trolig orsak till det här felet är att din brandvägg blockerar anslutningar från Microsoft 365 IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="96d4c-137">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="96d4c-138">Eller så kan det här felet vara av design natur om du helt har migrerat ditt lokala e-postsystem till Microsoft 365 och stängt av din lokala e-postmiljö.</span><span class="sxs-lookup"><span data-stu-id="96d4c-138">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="96d4c-139">Hur åtgärdar jag felkod 450 4.4.316?</span><span class="sxs-lookup"><span data-stu-id="96d4c-139">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="96d4c-140">Om du har postlådor i din lokala miljö måste du ändra dina brandväggsinställningar för att tillåta anslutningar från Microsoft 365 IP-adresser på TCP-port 25 till dina lokala e-postservrar.</span><span class="sxs-lookup"><span data-stu-id="96d4c-140">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="96d4c-141">En lista över Microsoft 365 IP-adresser finns i URL-adresser och IP-adressintervall för [Microsoft 365.](../../enterprise/urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="96d4c-141">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](../../enterprise/urls-and-ip-address-ranges.md).</span></span>

- <span data-ttu-id="96d4c-142">Om inga fler meddelanden ska levereras till  din lokala miljö klickar du på Åtgärda nu i aviseringen så att Microsoft 365 omedelbart kan avvisa meddelanden med ogiltiga mottagare.</span><span class="sxs-lookup"><span data-stu-id="96d4c-142">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="96d4c-143">Det här minskar risken för att organisationens kvot för ogiltiga mottagare överskrids, vilket kan påverka normal meddelandeleverans.</span><span class="sxs-lookup"><span data-stu-id="96d4c-143">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="96d4c-144">Du kan även använda följande anvisningar för att åtgärda problemet manuellt:</span><span class="sxs-lookup"><span data-stu-id="96d4c-144">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="96d4c-145">I [administrationscentret för Exchange (EAC)](/Exchange/exchange-admin-center)inaktiverar eller tar du bort anslutningen som levererar e-post från Microsoft 365 till din lokala e-postmiljö:</span><span class="sxs-lookup"><span data-stu-id="96d4c-145">In the [Exchange admin center (EAC)](/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="96d4c-146">Gå till E-postflödeskopplingar  \> **i** EAC.</span><span class="sxs-lookup"><span data-stu-id="96d4c-146">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="96d4c-147">Välj kopplingen med **Från-värdet** **Office 365** och till-värdet  din organisations **e-postserver** och gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="96d4c-147">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="96d4c-148">Ta bort kopplingen genom att klicka på **ikonen Ta** ![ bort](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="96d4c-148">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="96d4c-149">Inaktivera kopplingen genom att klicka **på** ![ redigera-ikonen ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) och avmarkera **Aktivera.**</span><span class="sxs-lookup"><span data-stu-id="96d4c-149">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="96d4c-150">Ändra den godkända domänen i Microsoft 365 som är kopplad till din lokala e-postmiljö från Internt **relä** **till Auktoritativ.**</span><span class="sxs-lookup"><span data-stu-id="96d4c-150">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="96d4c-151">Anvisningar finns i Hantera [godkända domäner i Exchange Online.](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)</span><span class="sxs-lookup"><span data-stu-id="96d4c-151">For instructions, see [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="96d4c-152">**Obs!** Det brukar ta mellan 30 minuter och en timme innan ändringarna börjar gälla.</span><span class="sxs-lookup"><span data-stu-id="96d4c-152">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="96d4c-153">Efter en timme kontrollerar du att du inte längre får felmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="96d4c-153">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="96d4c-154">Om felet kommer från din partnerorganisation (t.ex. en tredjepartsleverantör av molntjänster) måste du kontakta din partner för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="96d4c-154">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="96d4c-155">Felkod: 450 4.4.317 Det går inte att ansluta till fjärrservern</span><span class="sxs-lookup"><span data-stu-id="96d4c-155">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="96d4c-156">Vanligtvis innebär det här felet att Microsoft 365 är ansluten till mål-e-postservern, men att servern har svarat med ett omedelbart fel eller inte uppfyller anslutningskraven.</span><span class="sxs-lookup"><span data-stu-id="96d4c-156">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="96d4c-157">I felinformationen förklaras problemet.</span><span class="sxs-lookup"><span data-stu-id="96d4c-157">The error details will explain the problem.</span></span> <span data-ttu-id="96d4c-158">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="96d4c-158">For example:</span></span>

- <span data-ttu-id="96d4c-159">Mål-e-postservern har svarat med felet "Tjänsten är inte tillgänglig", vilket indikerar att servern inte kan behålla kommunikationen med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="96d4c-159">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="96d4c-160">Anslutningen är konfigurerad så att den kräver TLS, men mål-e-postservern stöder inte TLS.</span><span class="sxs-lookup"><span data-stu-id="96d4c-160">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="96d4c-161">Hur åtgärdar jag felkod 450 4.4.317?</span><span class="sxs-lookup"><span data-stu-id="96d4c-161">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="96d4c-162">Verifiera TLS-inställningarna och certifikaten på de lokala e-postservrarna och TLS-inställningarna på kopplingen.</span><span class="sxs-lookup"><span data-stu-id="96d4c-162">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="96d4c-163">Om felet kommer från din partnerorganisation (t.ex. en tredjepartsleverantör av molntjänster) måste du kontakta din partner för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="96d4c-163">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="96d4c-164">Felkod: 450 4.4.318 Anslutningen var stängd</span><span class="sxs-lookup"><span data-stu-id="96d4c-164">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="96d4c-165">Vanligtvis innebär det här felet att Microsoft 365 har problem med att kommunicera med din lokala e-postmiljö, så anslutningen har släppts.</span><span class="sxs-lookup"><span data-stu-id="96d4c-165">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="96d4c-166">Möjliga orsaker till det här felet är:</span><span class="sxs-lookup"><span data-stu-id="96d4c-166">The possible causes for this error are:</span></span>

- <span data-ttu-id="96d4c-167">Din brandvägg använder regler för SMTP-paketundersökning och de reglerna fungerar inte korrekt.</span><span class="sxs-lookup"><span data-stu-id="96d4c-167">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="96d4c-168">Din lokala e-postserver fungerar inte korrekt (t.ex. hänger sig tjänsten, kraschar eller låg systemresurser), vilket gör att serverns time out och stänger anslutningen till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="96d4c-168">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="96d4c-169">Det finns nätverksproblem mellan din lokala miljö och Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="96d4c-169">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="96d4c-170">Hur åtgärdar jag felkod 450 4.4.318?</span><span class="sxs-lookup"><span data-stu-id="96d4c-170">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="96d4c-171">Ta reda på vilket scenario som gäller för dig och gör nödvändiga korrigeringar.</span><span class="sxs-lookup"><span data-stu-id="96d4c-171">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="96d4c-172">Om problemet orsakas av nätverksproblem mellan din lokala miljö och Microsoft 365 kontaktar du nätverksteamet för att felsöka problemet.</span><span class="sxs-lookup"><span data-stu-id="96d4c-172">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="96d4c-173">Om felet kommer från din partnerorganisation (t.ex. en tredjepartsleverantör av molntjänster) måste du kontakta din partner för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="96d4c-173">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="96d4c-174">Felkod: 450 4.7.320 Certifikatverifiering misslyckades</span><span class="sxs-lookup"><span data-stu-id="96d4c-174">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="96d4c-175">Vanligtvis innebär det här felet att Microsoft 365 stött på ett fel när certifikatet för mål-e-postservern ska verifieras.</span><span class="sxs-lookup"><span data-stu-id="96d4c-175">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="96d4c-176">I felinformationen förklaras felet.</span><span class="sxs-lookup"><span data-stu-id="96d4c-176">The error details will explain the error.</span></span> <span data-ttu-id="96d4c-177">Ett exempel:</span><span class="sxs-lookup"><span data-stu-id="96d4c-177">For example:</span></span>

- <span data-ttu-id="96d4c-178">Certifikatet har gått ut</span><span class="sxs-lookup"><span data-stu-id="96d4c-178">Certificate expired</span></span>

- <span data-ttu-id="96d4c-179">Felmatchning av certifikatsämne</span><span class="sxs-lookup"><span data-stu-id="96d4c-179">Certificate subject mismatch</span></span>

- <span data-ttu-id="96d4c-180">Certifikatet är inte längre giltigt</span><span class="sxs-lookup"><span data-stu-id="96d4c-180">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="96d4c-181">Hur åtgärdar jag felkod 450 4.7.320?</span><span class="sxs-lookup"><span data-stu-id="96d4c-181">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="96d4c-182">Åtgärda certifikatet eller inställningarna för anslutningen så att meddelanden i kö i Microsoft 365 kan levereras.</span><span class="sxs-lookup"><span data-stu-id="96d4c-182">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="96d4c-183">Om felet kommer från din partnerorganisation (t.ex. en tredjepartsleverantör av molntjänster) måste du kontakta din partner för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="96d4c-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="96d4c-184">Andra felkoder</span><span class="sxs-lookup"><span data-stu-id="96d4c-184">Other error codes</span></span>

<span data-ttu-id="96d4c-185">Microsoft 365 har problem med att leverera meddelanden till din lokala e-postserver eller partnerserver.</span><span class="sxs-lookup"><span data-stu-id="96d4c-185">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="96d4c-186">Använd **målserverinformationen** i felet om du vill undersöka problemet i miljön eller ändra kopplingen om det uppstår ett konfigurationsfel.</span><span class="sxs-lookup"><span data-stu-id="96d4c-186">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="96d4c-187">Om felet kommer från din partnerorganisation (t.ex. en tredjepartsleverantör av molntjänster) måste du kontakta din partner för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="96d4c-187">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>