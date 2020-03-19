---
title: Information om e-postflöde i Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Administratörer kan lära sig mer om de felkoder som är associerade med meddelandeleverans med kopplingar i Office 365 (kallas även information om e-postflöde).
ms.openlocfilehash: 849493cefecb3344eaf7b6db73be3930138c236c
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812236"
---
# <a name="mail-flow-intelligence-in-office-365"></a><span data-ttu-id="74ba7-103">Information om e-postflöde i Office 365</span><span class="sxs-lookup"><span data-stu-id="74ba7-103">Mail flow intelligence in Office 365</span></span>

<span data-ttu-id="74ba7-104">Vanligtvis använder du en anslutningsapp för att dirigera e-postmeddelanden från din Office 365-organisation till din lokala e-postmiljö.</span><span class="sxs-lookup"><span data-stu-id="74ba7-104">Typically, you use a connector to route email messages from your Office 365 organization to your on-premises email environment.</span></span> <span data-ttu-id="74ba7-105">Du kan också använda en anslutningsapp för att dirigera meddelanden från Office 365 till en partnerorganisation.</span><span class="sxs-lookup"><span data-stu-id="74ba7-105">You might also use a connector to route messages from Office 365 to a partner organization.</span></span> <span data-ttu-id="74ba7-106">När Office 365 inte kan leverera dessa meddelanden via anslutningsappen står de i kö i Office 365.</span><span class="sxs-lookup"><span data-stu-id="74ba7-106">When Office 365 can't deliver these messages via the connector, they're queued in Office 365.</span></span> <span data-ttu-id="74ba7-107">Office 365 fortsätter att försöka leverera för varje meddelande i 24 timmar.</span><span class="sxs-lookup"><span data-stu-id="74ba7-107">Office 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="74ba7-108">Efter 24 timmar upphör det köade meddelandet och meddelandet returneras till den ursprungliga avsändaren i en rapport om utebliven leverans (kallas även NDR eller avvisningsmeddelande).</span><span class="sxs-lookup"><span data-stu-id="74ba7-108">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="74ba7-109">Office 365 genererar ett fel när ett meddelande inte kan levereras med hjälp av en anslutningsapp.</span><span class="sxs-lookup"><span data-stu-id="74ba7-109">Office 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="74ba7-110">De vanligaste felen och deras lösningar beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="74ba7-110">The most common errors and their solutions are described in this topic.</span></span> <span data-ttu-id="74ba7-111">Kollektivt kallas kö- och meddelandefel för meddelanden som inte kan levereras via kopplingar som _e-postflödesinformation_.</span><span class="sxs-lookup"><span data-stu-id="74ba7-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="74ba7-112">Felkod: 450 4.4.312 DNS-frågan misslyckades</span><span class="sxs-lookup"><span data-stu-id="74ba7-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="74ba7-113">Det här felet innebär vanligtvis att Office 365 försökte ansluta till den smarta värden som anges i kopplingen, men DNS-frågan för att hitta den smarta värdens IP-adresser misslyckades.</span><span class="sxs-lookup"><span data-stu-id="74ba7-113">Typically, this error means Office 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="74ba7-114">De möjliga orsakerna till det här felet är:</span><span class="sxs-lookup"><span data-stu-id="74ba7-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="74ba7-115">Det finns ett problem med domänens DNS-värdtjänst (den part som underhåller de auktoritära namnservrarna för din domän).</span><span class="sxs-lookup"><span data-stu-id="74ba7-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="74ba7-116">Domänen har nyligen upphört att gälla, så MX-posten kan inte hämtas.</span><span class="sxs-lookup"><span data-stu-id="74ba7-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="74ba7-117">Domänens MX-post har nyligen ändrats och Office 365 DNS-servrarna har fortfarande tidigare cachelagrat DNS-information för domänen.</span><span class="sxs-lookup"><span data-stu-id="74ba7-117">Your domain's MX record has recently changed, and the Office 365 DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="74ba7-118">Hur åtgärdar jag felkod 450 4.4.312?</span><span class="sxs-lookup"><span data-stu-id="74ba7-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="74ba7-119">Arbeta med dns-värdtjänsten för att identifiera och åtgärda problemet med din domän.</span><span class="sxs-lookup"><span data-stu-id="74ba7-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="74ba7-120">Om felet kommer från din partnerorganisation (till exempel en molntjänstleverantör från tredje part) kontaktar du din partner för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="74ba7-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="74ba7-121">Felkod: 450 4.4.315 Anslutningstidsering</span><span class="sxs-lookup"><span data-stu-id="74ba7-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="74ba7-122">Det innebär vanligtvis att Office 365 inte kan ansluta till målmeddelandeservern.</span><span class="sxs-lookup"><span data-stu-id="74ba7-122">Typically, this means Office 365 can't connect to the destination email server.</span></span> <span data-ttu-id="74ba7-123">Felinformationen förklarar problemet.</span><span class="sxs-lookup"><span data-stu-id="74ba7-123">The error details will explain the problem.</span></span> <span data-ttu-id="74ba7-124">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="74ba7-124">For example:</span></span>

- <span data-ttu-id="74ba7-125">Din lokala e-postserver är nere.</span><span class="sxs-lookup"><span data-stu-id="74ba7-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="74ba7-126">Det finns ett fel i kopplingens smarta värdinställningar, så Office 365 försöker ansluta till fel IP-adress.</span><span class="sxs-lookup"><span data-stu-id="74ba7-126">There's an error in the connector's smart host settings, so Office 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="74ba7-127">Hur åtgärdar jag felkod 450 4.4.315?</span><span class="sxs-lookup"><span data-stu-id="74ba7-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="74ba7-128">Ta reda på vilket scenario som gäller för dig och gör nödvändiga korrigeringar.</span><span class="sxs-lookup"><span data-stu-id="74ba7-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="74ba7-129">Om e-postflödet till exempel har fungerat korrekt och du inte har ändrat anslutningsinställningarna måste du kontrollera din lokala e-postmiljö för att se om servern är nere eller om det har skett några ändringar i nätverksinfrastrukturen (till exempel du har ändrat internetleverantörer, så du har nu olika IP-adresser).</span><span class="sxs-lookup"><span data-stu-id="74ba7-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="74ba7-130">Om felet kommer från din partnerorganisation (till exempel en molntjänstleverantör från tredje part) kontaktar du din partner för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="74ba7-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="74ba7-131">Felkod: 450 4.4.316 Anslutning nekad</span><span class="sxs-lookup"><span data-stu-id="74ba7-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="74ba7-132">Det här felet innebär vanligtvis att Office 365 påträffade ett anslutningsfel när det försökte ansluta till målmeddelandeservern.</span><span class="sxs-lookup"><span data-stu-id="74ba7-132">Typically, this error means Office 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="74ba7-133">En trolig orsak till det här felet är att brandväggen blockerar anslutningar från Office 365 IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="74ba7-133">A likely cause for this error is your firewall is blocking connections from Office 365 IP addresses.</span></span> <span data-ttu-id="74ba7-134">Det här felet kan också vara avsiktligt om du helt har migrerat ditt lokala e-postsystem till Office 365 och stängt av din lokala e-postmiljö.</span><span class="sxs-lookup"><span data-stu-id="74ba7-134">Or, this error might be by design if you've completely migrated your on-premises email system to Office 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="74ba7-135">Hur åtgärdar jag felkod 450 4.4.316?</span><span class="sxs-lookup"><span data-stu-id="74ba7-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="74ba7-136">Om du har postlådor i din lokala miljö måste du ändra brandväggsinställningarna så att anslutningar från Office 365 IP-adresser på TCP-port 25 till dina lokala e-postservrar tillåts.</span><span class="sxs-lookup"><span data-stu-id="74ba7-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Office 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="74ba7-137">En lista över IP-adresserna för Office 365 finns i [Url:er och IP-adressintervall för Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="74ba7-137">For a list of the Office 365 IP addresses, see [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span>

- <span data-ttu-id="74ba7-138">Om inga fler meddelanden ska levereras till din lokala miljö klickar du på **Åtgärda nu** i aviseringen så att Office 365 omedelbart kan avvisa meddelandena med ogiltiga mottagare.</span><span class="sxs-lookup"><span data-stu-id="74ba7-138">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Office 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="74ba7-139">Detta minskar risken för att din organisations kvot överskrids för ogiltiga mottagare, vilket kan påverka normal meddelandeleverans.</span><span class="sxs-lookup"><span data-stu-id="74ba7-139">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="74ba7-140">Du kan också använda följande instruktioner för att åtgärda problemet manuellt:</span><span class="sxs-lookup"><span data-stu-id="74ba7-140">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="74ba7-141">I [Administrationscentret för Exchange (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) i Office 365 inaktiverar eller tar du bort den anslutningsapp som levererar e-post från Office 365 till din lokala e-postmiljö:</span><span class="sxs-lookup"><span data-stu-id="74ba7-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365, disable or delete the connector that delivers email from Office 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="74ba7-142">Gå till **EAC i EAC-kopplingarna för e-postflöde** \> **Connectors**.</span><span class="sxs-lookup"><span data-stu-id="74ba7-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="74ba7-143">Välj anslutningsappen med **värdet Från** **Office 365** och **Värdet Till** **Organisationens e-postserver** och gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="74ba7-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="74ba7-144">Ta bort kopplingen genom att klicka på Ikonen **Ta bort** ![ta bort](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="74ba7-144">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="74ba7-145">Inaktivera kopplingen genom **Edit** ![att klicka](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) på Ikonen Redigera redigera och avmarkera **Aktivera den**.</span><span class="sxs-lookup"><span data-stu-id="74ba7-145">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and unchecking **Turn it on**.</span></span>

  - <span data-ttu-id="74ba7-146">Ändra den accepterade domänen i Office 365 som är associerad med din lokala e-postmiljö från **Intern relay** till **auktoritär .**</span><span class="sxs-lookup"><span data-stu-id="74ba7-146">Change the accepted domain in Office 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="74ba7-147">Instruktioner finns [i Hantera accepterade domäner i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="74ba7-147">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="74ba7-148">**Obs:** Vanligtvis tar dessa ändringar mellan 30 minuter och en timme att börja gälla.</span><span class="sxs-lookup"><span data-stu-id="74ba7-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="74ba7-149">Efter en timme kontrollerar du att felet inte längre visas.</span><span class="sxs-lookup"><span data-stu-id="74ba7-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="74ba7-150">Om felet kommer från din partnerorganisation (till exempel en molntjänstleverantör från tredje part) måste du kontakta din partner för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="74ba7-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="74ba7-151">Felkod: 450 4.4.317 Det går inte att ansluta till fjärrservern</span><span class="sxs-lookup"><span data-stu-id="74ba7-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="74ba7-152">Det här felet innebär vanligtvis att Office 365 är anslutet till målmeddelandeservern, men servern svarade med ett omedelbart fel eller inte uppfyller anslutningskraven.</span><span class="sxs-lookup"><span data-stu-id="74ba7-152">Typically, this error means Office 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="74ba7-153">Felinformationen förklarar problemet.</span><span class="sxs-lookup"><span data-stu-id="74ba7-153">The error details will explain the problem.</span></span> <span data-ttu-id="74ba7-154">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="74ba7-154">For example:</span></span>

- <span data-ttu-id="74ba7-155">Målmeddelandeservern svarade med ett felmeddelande om tjänsten som inte är tillgänglig, vilket indikerar att servern inte kan upprätthålla kommunikationen med Office 365.</span><span class="sxs-lookup"><span data-stu-id="74ba7-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Office 365.</span></span>

- <span data-ttu-id="74ba7-156">Anslutningen är konfigurerad för att kräva TLS, men målmeddelandeservern stöder inte TLS.</span><span class="sxs-lookup"><span data-stu-id="74ba7-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="74ba7-157">Hur åtgärdar jag felkod 450 4.4.317?</span><span class="sxs-lookup"><span data-stu-id="74ba7-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="74ba7-158">Verifiera TLS-inställningarna och certifikaten på dina lokala e-postservrar och TLS-inställningarna på anslutningen.</span><span class="sxs-lookup"><span data-stu-id="74ba7-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="74ba7-159">Om felet kommer från din partnerorganisation (till exempel en molntjänstleverantör från tredje part) måste du kontakta din partner för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="74ba7-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="74ba7-160">Felkod: 450 4.4.318 Anslutningen stängdes plötsligt</span><span class="sxs-lookup"><span data-stu-id="74ba7-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="74ba7-161">Det här felet innebär vanligtvis att Office 365 har svårt att kommunicera med din lokala e-postmiljö, så anslutningen avbröts.</span><span class="sxs-lookup"><span data-stu-id="74ba7-161">Typically, this error means Office 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="74ba7-162">De möjliga orsakerna till det här felet är:</span><span class="sxs-lookup"><span data-stu-id="74ba7-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="74ba7-163">Brandväggen använder SMTP-paketgranskningsregler och dessa regler fungerar inte korrekt.</span><span class="sxs-lookup"><span data-stu-id="74ba7-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="74ba7-164">Din lokala e-postserver fungerar inte korrekt (till exempel låser sig tjänsten, kraschar eller har låga systemresurser), vilket gör att servern tar timeout och stänger anslutningen till Office 365.</span><span class="sxs-lookup"><span data-stu-id="74ba7-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Office 365.</span></span>

- <span data-ttu-id="74ba7-165">Det finns nätverksproblem mellan den lokala miljön och Office 365.</span><span class="sxs-lookup"><span data-stu-id="74ba7-165">There are network issues between your on-premises environment and Office 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="74ba7-166">Hur åtgärdar jag felkod 450 4.4.318?</span><span class="sxs-lookup"><span data-stu-id="74ba7-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="74ba7-167">Ta reda på vilket scenario som gäller för dig och gör nödvändiga korrigeringar.</span><span class="sxs-lookup"><span data-stu-id="74ba7-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="74ba7-168">Om problemet beror på nätverksproblem mellan den lokala miljön och Office 365 kontaktar du nätverksteamet för att felsöka problemet.</span><span class="sxs-lookup"><span data-stu-id="74ba7-168">If the problem is caused by network issues between your on-premises environment and Office 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="74ba7-169">Om felet kommer från din partnerorganisation (till exempel en molntjänstleverantör från tredje part) måste du kontakta din partner för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="74ba7-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="74ba7-170">Felkod: 450 4.7.320 Certifikatvalidering misslyckades</span><span class="sxs-lookup"><span data-stu-id="74ba7-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="74ba7-171">Det här felet innebär vanligtvis att Office 365 påträffade ett fel när certifikatet för målmeddelandeservern skulle valideras.</span><span class="sxs-lookup"><span data-stu-id="74ba7-171">Typically, this error means Office 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="74ba7-172">Felinformationen förklarar felet.</span><span class="sxs-lookup"><span data-stu-id="74ba7-172">The error details will explain the error.</span></span> <span data-ttu-id="74ba7-173">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="74ba7-173">For example:</span></span>

- <span data-ttu-id="74ba7-174">Certifikatet har upphört att gälla</span><span class="sxs-lookup"><span data-stu-id="74ba7-174">Certificate expired</span></span>

- <span data-ttu-id="74ba7-175">Felmatchning av certifikatämne</span><span class="sxs-lookup"><span data-stu-id="74ba7-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="74ba7-176">Certifikatet är inte längre giltigt</span><span class="sxs-lookup"><span data-stu-id="74ba7-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="74ba7-177">Hur åtgärdar jag felkod 450 4.7.320?</span><span class="sxs-lookup"><span data-stu-id="74ba7-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="74ba7-178">Åtgärda certifikatet eller inställningarna på kopplingen så att köade meddelanden i Office 365 kan levereras.</span><span class="sxs-lookup"><span data-stu-id="74ba7-178">Fix the certificate or the settings on the connector so that queued messages in Office 365 can be delivered.</span></span>

- <span data-ttu-id="74ba7-179">Om felet kommer från din partnerorganisation (till exempel en molntjänstleverantör från tredje part) måste du kontakta din partner för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="74ba7-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="74ba7-180">Andra felkoder</span><span class="sxs-lookup"><span data-stu-id="74ba7-180">Other error codes</span></span>

<span data-ttu-id="74ba7-181">Office 365 har svårt att leverera meddelanden till din lokala e-postserver eller partnerserver.</span><span class="sxs-lookup"><span data-stu-id="74ba7-181">Office 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="74ba7-182">Använd **målserverinformationen** i felet för att undersöka problemet i din miljö eller ändra kopplingen om det finns ett konfigurationsfel.</span><span class="sxs-lookup"><span data-stu-id="74ba7-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="74ba7-183">Om felet kommer från din partnerorganisation (till exempel en molntjänstleverantör från tredje part) måste du kontakta din partner för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="74ba7-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
