---
title: Information om e-postflöde
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Administratörer kan läsa mer om fel koderna som är kopplade till meddelande leverans via kopplingar (kallas även för e-postflöde).
ms.openlocfilehash: e8427f3e0341ccb381121b6cdc83d20727713d4c
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307923"
---
# <a name="mail-flow-intelligence-in-eop"></a><span data-ttu-id="93385-103">E-postflödesinformation i EOP</span><span class="sxs-lookup"><span data-stu-id="93385-103">Mail flow intelligence in EOP</span></span>

<span data-ttu-id="93385-104">I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor använder du vanligt vis en koppling för att dirigera e-postmeddelanden från EOP till din lokala e-postmiljö.</span><span class="sxs-lookup"><span data-stu-id="93385-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, you typically use a connector to route email messages from EOP to your on-premises email environment.</span></span> <span data-ttu-id="93385-105">Du kan också använda en koppling för att dirigera meddelanden från Microsoft 365 till en partner organisation.</span><span class="sxs-lookup"><span data-stu-id="93385-105">You might also use a connector to route messages from Microsoft 365 to a partner organization.</span></span> <span data-ttu-id="93385-106">När Microsoft 365 inte kan leverera dessa meddelanden via kopplingen köas de i Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="93385-106">When Microsoft 365 can't deliver these messages via the connector, they're queued in Microsoft 365.</span></span> <span data-ttu-id="93385-107">Microsoft 365 fortsätter att försöka leverera för varje meddelande i 24 timmar.</span><span class="sxs-lookup"><span data-stu-id="93385-107">Microsoft 365 will continue to retry delivery for each message for 24 hours.</span></span> <span data-ttu-id="93385-108">Efter 24 timmar upphör det köade meddelandet att upphöra och meddelandet kommer att återföras till den ursprungliga avsändaren i en rapport om utebliven leverans (kallas även för en NDR eller ett studs meddelande).</span><span class="sxs-lookup"><span data-stu-id="93385-108">After 24 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="93385-109">Microsoft 365 skapar ett fel när ett meddelande inte kan levereras med en koppling.</span><span class="sxs-lookup"><span data-stu-id="93385-109">Microsoft 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="93385-110">De vanligaste felen och deras lösningar beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="93385-110">The most common errors and their solutions are described in this topic.</span></span> <span data-ttu-id="93385-111">Det är kollektivt, köer och aviserings fel för meddelanden som skickas via kopplingar kallas för _e-postflöde_.</span><span class="sxs-lookup"><span data-stu-id="93385-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="93385-112">Felkod: 450 4.4.312 DNS Query misslyckades</span><span class="sxs-lookup"><span data-stu-id="93385-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="93385-113">Det här felet innebär att Microsoft 365 försökte ansluta till den smarta värden som anges i kopplingen, men DNS-frågan för att hitta den smarta värdens IP-adresser misslyckades.</span><span class="sxs-lookup"><span data-stu-id="93385-113">Typically, this error means Microsoft 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="93385-114">Möjliga orsaker till det här felet är:</span><span class="sxs-lookup"><span data-stu-id="93385-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="93385-115">Det är problem med din domäns DNS-värd (den part som underhåller de auktoritära namnservrarna för din domän).</span><span class="sxs-lookup"><span data-stu-id="93385-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="93385-116">Din domän har nyligen upphört, så MX-posten kan inte hämtas.</span><span class="sxs-lookup"><span data-stu-id="93385-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="93385-117">Din domäns MX-post har nyligen ändrats och DNS-servrarna har fortfarande cachelagrat DNS-information för din domän.</span><span class="sxs-lookup"><span data-stu-id="93385-117">Your domain's MX record has recently changed, and the DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="93385-118">Hur åtgärdar jag felkod 450 4.4.312?</span><span class="sxs-lookup"><span data-stu-id="93385-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="93385-119">Arbeta med din DNS-värd för att identifiera och åtgärda problemet med din domän.</span><span class="sxs-lookup"><span data-stu-id="93385-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="93385-120">Om felet kommer från din partner organisation (till exempel en tredjeparts moln tjänst leverantör) kontaktar du din partner för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="93385-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="93385-121">Felkod: tids gränsen för 450 4.4.315-anslutningen uppnåddes</span><span class="sxs-lookup"><span data-stu-id="93385-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="93385-122">Det innebär vanligt vis att Microsoft 365 inte kan ansluta till mål-e-postservern.</span><span class="sxs-lookup"><span data-stu-id="93385-122">Typically, this means Microsoft 365 can't connect to the destination email server.</span></span> <span data-ttu-id="93385-123">Fel informationen förklarar problemet.</span><span class="sxs-lookup"><span data-stu-id="93385-123">The error details will explain the problem.</span></span> <span data-ttu-id="93385-124">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="93385-124">For example:</span></span>

- <span data-ttu-id="93385-125">Din lokala e-postserver är nere.</span><span class="sxs-lookup"><span data-stu-id="93385-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="93385-126">Det finns ett fel i kopplingens inställningar för smart värd, så Microsoft 365 försöker ansluta till fel IP-adress.</span><span class="sxs-lookup"><span data-stu-id="93385-126">There's an error in the connector's smart host settings, so Microsoft 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="93385-127">Hur åtgärdar jag felkod 450 4.4.315?</span><span class="sxs-lookup"><span data-stu-id="93385-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="93385-128">Ta reda på vilket scenario som gäller för dig och gör nödvändiga ändringar.</span><span class="sxs-lookup"><span data-stu-id="93385-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="93385-129">Om e-postflödet fungerar som det ska och du inte har ändrat kopplings inställningarna måste du kontrol lera din lokala e-postmiljö för att se om servern är nere, eller om det har gjorts ändringar i nätverks infrastrukturen (till exempel har du ändrat Internet leverantörens IP-adresser).</span><span class="sxs-lookup"><span data-stu-id="93385-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="93385-130">Om felet kommer från din partner organisation (till exempel en tredjeparts moln tjänst leverantör) kontaktar du din partner för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="93385-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="93385-131">Felkod: 450 4.4.316 anslutningen nekades</span><span class="sxs-lookup"><span data-stu-id="93385-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="93385-132">Vanligt vis betyder det att Microsoft 365 stötte på ett anslutnings fel när det försökte ansluta till mål-e-postservern.</span><span class="sxs-lookup"><span data-stu-id="93385-132">Typically, this error means Microsoft 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="93385-133">Den sannolika orsaken till felet är att brand väggen blockerar anslutningar från Microsoft 365-IP-adresser.</span><span class="sxs-lookup"><span data-stu-id="93385-133">A likely cause for this error is your firewall is blocking connections from Microsoft 365 IP addresses.</span></span> <span data-ttu-id="93385-134">Eller så kan det bero på att du har migrerat det lokala e-postsystemet fullständigt till Microsoft 365 och stängt din lokala e-postmiljö.</span><span class="sxs-lookup"><span data-stu-id="93385-134">Or, this error might be by design if you've completely migrated your on-premises email system to Microsoft 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="93385-135">Hur åtgärdar jag felkod 450 4.4.316?</span><span class="sxs-lookup"><span data-stu-id="93385-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="93385-136">Om du har post lådor i den lokala miljön måste du ändra brand Väggs inställningarna för att tillåta anslutningar från Microsoft 365-IP-adresser på TCP port 25 till lokala e-postservrar.</span><span class="sxs-lookup"><span data-stu-id="93385-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Microsoft 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="93385-137">En lista med IP-adresser för Microsoft 365 finns i [microsoft 365 URL: er och IP-adressintervall](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="93385-137">For a list of the Microsoft 365 IP addresses, see [Microsoft 365 URLs and IP address ranges](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span>

- <span data-ttu-id="93385-138">Om du inte vill skicka fler meddelanden till den lokala miljön klickar du på **åtgärda nu** i aviseringen så att Microsoft 365 omedelbart neka meddelanden med ogiltiga mottagare.</span><span class="sxs-lookup"><span data-stu-id="93385-138">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Microsoft 365 can immediately reject the messages with invalid recipients.</span></span> <span data-ttu-id="93385-139">Detta minskar risken för att organisationens kvot överskrids för ogiltiga mottagare, vilket kan påverka normal meddelande leverans.</span><span class="sxs-lookup"><span data-stu-id="93385-139">This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery.</span></span> <span data-ttu-id="93385-140">Eller så kan du använda följande anvisningar för att lösa problemet manuellt:</span><span class="sxs-lookup"><span data-stu-id="93385-140">Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="93385-141">I [administrations centret för Exchange (UK)](https://docs.microsoft.com/Exchange/exchange-admin-center)inaktiverar eller tar du bort kopplingen som skickar e-post från Microsoft 365 till din lokala e-post miljö:</span><span class="sxs-lookup"><span data-stu-id="93385-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center), disable or delete the connector that delivers email from Microsoft 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="93385-142">Gå till **e-postflödes** \> **kopplingar**i UK.</span><span class="sxs-lookup"><span data-stu-id="93385-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="93385-143">Välj kopplingen med värdet **från** **Office 365** och värdet **till för** **din organisations e-postserver** och gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="93385-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="93385-144">Ta bort kopplingen genom att klicka på **ta bort** ![ ta bort ikon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="93385-144">Delete the connector by clicking **Delete** ![Remove icon](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="93385-145">Inaktivera kopplingen genom att klicka på **Redigera** ![ redigerings ikon ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) och sedan Rensa **på Aktivera den**.</span><span class="sxs-lookup"><span data-stu-id="93385-145">Disable the connector by clicking **Edit** ![Edit icon](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and clearing **Turn it on**.</span></span>

  - <span data-ttu-id="93385-146">Ändra den godkända domänen i Microsoft 365 som är kopplad till den lokala e-postmiljön från **intern relä** till **auktoritär**.</span><span class="sxs-lookup"><span data-stu-id="93385-146">Change the accepted domain in Microsoft 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="93385-147">Anvisningar finns i [Hantera godkända domäner i Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span><span class="sxs-lookup"><span data-stu-id="93385-147">For instructions, see [Manage accepted domains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).</span></span>

  <span data-ttu-id="93385-148">**Obs!** normalt tar de här ändringarna mellan 30 minuter och 1 timme att börja gälla.</span><span class="sxs-lookup"><span data-stu-id="93385-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="93385-149">Efter en timme kontrollerar du att du inte längre får felet.</span><span class="sxs-lookup"><span data-stu-id="93385-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="93385-150">Om felet kommer från din partner organisation (till exempel en tredjeparts moln tjänst leverantör) måste du kontakta din partner för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="93385-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="93385-151">Felkod: 450 4.4.317 går inte att ansluta till fjärrservern</span><span class="sxs-lookup"><span data-stu-id="93385-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="93385-152">Det här felet innebär vanligt vis att Microsoft 365 är uppkopplat till mål-e-postservern, men servern svarade med ett omedelbara fel eller inte uppfyller anslutnings kraven.</span><span class="sxs-lookup"><span data-stu-id="93385-152">Typically, this error means Microsoft 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="93385-153">Fel informationen förklarar problemet.</span><span class="sxs-lookup"><span data-stu-id="93385-153">The error details will explain the problem.</span></span> <span data-ttu-id="93385-154">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="93385-154">For example:</span></span>

- <span data-ttu-id="93385-155">Mål-e-postservern svarade med fel meddelandet "tjänsten är inte tillgänglig", vilket betyder att servern inte kan hantera kommunikationen med Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="93385-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Microsoft 365.</span></span>

- <span data-ttu-id="93385-156">Anslutningen är konfigurerad för att kräva TLS men mål-e-postservern stöder inte TLS.</span><span class="sxs-lookup"><span data-stu-id="93385-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="93385-157">Hur åtgärdar jag felkod 450 4.4.317?</span><span class="sxs-lookup"><span data-stu-id="93385-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="93385-158">Kontrol lera TLS-inställningar och certifikat på lokala e-postservrar och TLS-inställningar på kopplingen.</span><span class="sxs-lookup"><span data-stu-id="93385-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="93385-159">Om felet kommer från din partner organisation (till exempel en tredjeparts moln tjänst leverantör) måste du kontakta din partner för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="93385-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="93385-160">Felkod: 450 4.4.318 anslutningen avbröts plötsligt</span><span class="sxs-lookup"><span data-stu-id="93385-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="93385-161">Vanligt vis betyder det att Microsoft 365 har problem med kommunikationen med din lokala e-postmiljö, så anslutningen avbröts.</span><span class="sxs-lookup"><span data-stu-id="93385-161">Typically, this error means Microsoft 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="93385-162">Möjliga orsaker till det här felet är:</span><span class="sxs-lookup"><span data-stu-id="93385-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="93385-163">Brand väggen använder regler för SMTP-paketfiltrering och reglerna fungerar inte som de ska.</span><span class="sxs-lookup"><span data-stu-id="93385-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="93385-164">Den lokala e-postservern fungerar inte som den ska (till exempel att tjänsten hänger sig, kraschar eller låg system resurser), vilket gör att servern tar slut på timeout och stänger anslutningen till Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="93385-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Microsoft 365.</span></span>

- <span data-ttu-id="93385-165">Det finns nätverks problem mellan den lokala miljön och Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="93385-165">There are network issues between your on-premises environment and Microsoft 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="93385-166">Hur åtgärdar jag felkod 450 4.4.318?</span><span class="sxs-lookup"><span data-stu-id="93385-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="93385-167">Ta reda på vilket scenario som gäller för dig och gör nödvändiga ändringar.</span><span class="sxs-lookup"><span data-stu-id="93385-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="93385-168">Om problemet orsakas av nätverks problem mellan den lokala miljön och Microsoft 365 kontaktar du nätverks gruppen för att felsöka problemet.</span><span class="sxs-lookup"><span data-stu-id="93385-168">If the problem is caused by network issues between your on-premises environment and Microsoft 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="93385-169">Om felet kommer från din partner organisation (till exempel en tredjeparts moln tjänst leverantör) måste du kontakta din partner för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="93385-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="93385-170">Felkod: det gick inte att verifiera 450-4.7.320</span><span class="sxs-lookup"><span data-stu-id="93385-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="93385-171">Det här felet innebär vanligt vis att Microsoft 365 påträffade ett fel när du försöker verifiera mål-e-postserverns certifikat.</span><span class="sxs-lookup"><span data-stu-id="93385-171">Typically, this error means Microsoft 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="93385-172">Fel informationen förklarar felet.</span><span class="sxs-lookup"><span data-stu-id="93385-172">The error details will explain the error.</span></span> <span data-ttu-id="93385-173">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="93385-173">For example:</span></span>

- <span data-ttu-id="93385-174">Certifikatet har upphört</span><span class="sxs-lookup"><span data-stu-id="93385-174">Certificate expired</span></span>

- <span data-ttu-id="93385-175">Subjekt brist</span><span class="sxs-lookup"><span data-stu-id="93385-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="93385-176">Certifikatet är inte längre giltigt</span><span class="sxs-lookup"><span data-stu-id="93385-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="93385-177">Hur åtgärdar jag felkod 450 4.7.320?</span><span class="sxs-lookup"><span data-stu-id="93385-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="93385-178">Åtgärda certifikatet eller inställningarna för anslutningen så att köade meddelanden i Microsoft 365 kan levereras.</span><span class="sxs-lookup"><span data-stu-id="93385-178">Fix the certificate or the settings on the connector so that queued messages in Microsoft 365 can be delivered.</span></span>

- <span data-ttu-id="93385-179">Om felet kommer från din partner organisation (till exempel en tredjeparts moln tjänst leverantör) måste du kontakta din partner för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="93385-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="93385-180">Andra felkoder</span><span class="sxs-lookup"><span data-stu-id="93385-180">Other error codes</span></span>

<span data-ttu-id="93385-181">Microsoft 365 har svårt att leverera meddelanden till din lokala eller partner e-postserver.</span><span class="sxs-lookup"><span data-stu-id="93385-181">Microsoft 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="93385-182">Använd informationen om **mål servern** för att undersöka problemet i miljön eller ändra anslutningen om det finns ett konfigurations fel.</span><span class="sxs-lookup"><span data-stu-id="93385-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span>

<span data-ttu-id="93385-183">Om felet kommer från din partner organisation (till exempel en tredjeparts moln tjänst leverantör) måste du kontakta din partner för att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="93385-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
