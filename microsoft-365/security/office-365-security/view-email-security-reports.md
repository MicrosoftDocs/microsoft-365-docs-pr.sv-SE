---
title: Visa rapporter om e-postsäkerhet i Säkerhets- och efterlevnadscenter
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Lär dig hur du hittar och använder e-postsäkerhets rapporter för organisationen. Säkerhets rapporter för e-post finns i säkerhets & Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7e594f758e0fb08b0b8718248466ecbc46903b82
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327015"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a><span data-ttu-id="7a236-104">Visa rapporter om e-postsäkerhet i Säkerhets- och efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="7a236-104">View email security reports in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7a236-105">Det finns en mängd olika rapporter i [säkerhets & Compliance Center](https://protection.office.com) som hjälper dig att se hur säkerhetsfunktionerna för e-post, till exempel skydd mot skräp post, mot skadlig program vara och krypterings funktioner i Microsoft 365 som skyddar din organisation.</span><span class="sxs-lookup"><span data-stu-id="7a236-105">A variety of reports are available in the [Security & Compliance Center](https://protection.office.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="7a236-106">Om du har [nödvändig behörighet](#what-permissions-are-needed-to-view-these-reports)kan du visa dessa rapporter i säkerhets & Compliance Center genom att gå till **Reports** \> **instrument panelen**för rapporter.</span><span class="sxs-lookup"><span data-stu-id="7a236-106">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security & Compliance Center by going to **Reports** \> **Dashboard**.</span></span> <span data-ttu-id="7a236-107">Öppna för att gå direkt till instrument panelen rapporter <https://protection.office.com/insightdashboard> .</span><span class="sxs-lookup"><span data-stu-id="7a236-107">To go directly to the Reports dashboard, open <https://protection.office.com/insightdashboard>.</span></span>

![Instrument panel för rapporter i centret för säkerhets &](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a><span data-ttu-id="7a236-109">Rapport om komprometterade användare</span><span class="sxs-lookup"><span data-stu-id="7a236-109">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="7a236-110">Den här rapporten är tillgänglig i Microsoft 365-organisationer med Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="7a236-110">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="7a236-111">Den är inte tillgänglig i fristående Exchange Online Protection-organisationer (EOP).</span><span class="sxs-lookup"><span data-stu-id="7a236-111">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="7a236-112">Rapporten **äventyrade användare** visar antalet användar konton som marker ATS som **misstänkta** eller **begränsade** under de senaste 7 dagarna.</span><span class="sxs-lookup"><span data-stu-id="7a236-112">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="7a236-113">Konton i något av dessa tillstånd är problematiska eller till och med kompromissade.</span><span class="sxs-lookup"><span data-stu-id="7a236-113">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="7a236-114">Med en ofta förekommande användning kan du använda rapporten för att upptäcka mellanliggande och till och med trender i misstänkta eller begränsade konton.</span><span class="sxs-lookup"><span data-stu-id="7a236-114">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="7a236-115">Mer information om komprometterade användare finns i [svara på ett komprometterat e-postkonto](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="7a236-115">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widgeten användare med sekretess i rapport instrument panelen](../../media/compromised-users-report-widget.png)

<span data-ttu-id="7a236-117">I vyn mängd visas data för de senaste 90 dagarna och detaljvyn visar data för de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="7a236-117">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="7a236-118">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **användare med kompromissade**.</span><span class="sxs-lookup"><span data-stu-id="7a236-118">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Compromised users**.</span></span> <span data-ttu-id="7a236-119">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="7a236-119">To go directly to the report, open <https://protection.office.com/reportv2?id=CompromisedUsers>.</span></span>

<span data-ttu-id="7a236-120">Du kan filtrera både diagrammet och informations tabellen genom att klicka på **filter** och välja ett eller flera av följande värden:</span><span class="sxs-lookup"><span data-stu-id="7a236-120">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="7a236-121">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="7a236-121">**Start date** and **End date**</span></span>

- <span data-ttu-id="7a236-122">**Misstänkt**: användar kontot har skickat misstänkt e-post och riskerar att begränsas från att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="7a236-122">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="7a236-123">**Begränsat**: användar kontot har begränsats från att skicka e-post på grund av starkt misstänkta mönster.</span><span class="sxs-lookup"><span data-stu-id="7a236-123">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![Rapportvyn i rapporten användare med kompromissad](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="7a236-125">Om du klickar på **Visa informations tabell**kan du se följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="7a236-125">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="7a236-126">**Skapelse tid**</span><span class="sxs-lookup"><span data-stu-id="7a236-126">**Creation time**</span></span>
- <span data-ttu-id="7a236-127">**Användar-ID**</span><span class="sxs-lookup"><span data-stu-id="7a236-127">**User ID**</span></span>
- <span data-ttu-id="7a236-128">**Fattning**</span><span class="sxs-lookup"><span data-stu-id="7a236-128">**Action**</span></span>

<span data-ttu-id="7a236-129">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="7a236-129">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="7a236-130">Krypterings rapport</span><span class="sxs-lookup"><span data-stu-id="7a236-130">Encryption report</span></span>

<span data-ttu-id="7a236-131">**Krypterings rapporten** är tillgänglig i EOP (abonnemang med post lådor i Exchange Online eller fristående EOP utan Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="7a236-131">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="7a236-132">Din organisations säkerhets team kan använda informationen i den här rapporten för att identifiera mönster och proaktivt tillämpa eller justera principer för känsliga e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="7a236-132">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="7a236-133">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="7a236-133">For example:</span></span>

- <span data-ttu-id="7a236-134">Om du ser ett stort antal e-postmeddelanden som har krypterats av användarna kanske du vill lägga till en krypterings princip för att automatisera kryptering för vissa användnings fall.</span><span class="sxs-lookup"><span data-stu-id="7a236-134">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="7a236-135">Mer information finns i [definiera regler för e-postflöde för att kryptera e-postmeddelanden i Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="7a236-135">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="7a236-136">Om du har ett antal krypteringsalgoritmer tillgängliga men ingen använder dem kan du undersöka om användarna behöver funktions träning.</span><span class="sxs-lookup"><span data-stu-id="7a236-136">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="7a236-137">Med mängd läget kan du filtrera under de senaste 90 dagarna, medan vyn detaljerad kan filtreras i 10 dagar.</span><span class="sxs-lookup"><span data-stu-id="7a236-137">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="7a236-138">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **krypterings rapport**.</span><span class="sxs-lookup"><span data-stu-id="7a236-138">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Encryption report**.</span></span> <span data-ttu-id="7a236-139">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="7a236-139">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="7a236-140">Mer information om kryptering finns i [kryptering med e-post i Microsoft 365](../../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="7a236-140">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="7a236-141">Rapportvy för krypterings rapporten</span><span class="sxs-lookup"><span data-stu-id="7a236-141">Report view for the Encryption report</span></span>

<span data-ttu-id="7a236-142">Du kan använda följande filter i diagrammet:</span><span class="sxs-lookup"><span data-stu-id="7a236-142">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="7a236-143">**Visa data via: meddelande krypterings rapport** och **bryta ned efter: krypterings metod**: följande krypterings metoder är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="7a236-143">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="7a236-144">**Kryptering efter användare**</span><span class="sxs-lookup"><span data-stu-id="7a236-144">**Encryption by user**</span></span>
  - <span data-ttu-id="7a236-145">**Kryptering per princip**</span><span class="sxs-lookup"><span data-stu-id="7a236-145">**Encryption by policy**</span></span>

  <span data-ttu-id="7a236-146">Om du klickar på **filter**kan du ändra diagrammet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="7a236-146">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="7a236-147">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="7a236-147">**Start date** and **End date**</span></span>
  - <span data-ttu-id="7a236-148">Krypterings metod.</span><span class="sxs-lookup"><span data-stu-id="7a236-148">Encryption method.</span></span>
  - <span data-ttu-id="7a236-149">Krypterings mal len.</span><span class="sxs-lookup"><span data-stu-id="7a236-149">Encryption template.</span></span>

- <span data-ttu-id="7a236-150">**Visa data via: meddelande krypterings rapport** och **bryta ned efter: krypterings mal len**: följande krypterings metoder är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="7a236-150">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="7a236-151">**Vidarekoppla inte**</span><span class="sxs-lookup"><span data-stu-id="7a236-151">**Do not forward**</span></span>
  - <span data-ttu-id="7a236-152">**Endast kryptering**</span><span class="sxs-lookup"><span data-stu-id="7a236-152">**Encrypt only**</span></span>
  - <span data-ttu-id="7a236-153">**OME föregående**</span><span class="sxs-lookup"><span data-stu-id="7a236-153">**OME previous**</span></span>
  - <span data-ttu-id="7a236-154">**Företagsanpassade**</span><span class="sxs-lookup"><span data-stu-id="7a236-154">**Custom**</span></span>

  <span data-ttu-id="7a236-155">Om du klickar på **filter**kan du ändra diagrammet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="7a236-155">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="7a236-156">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="7a236-156">**Start date** and **End date**</span></span>
  - <span data-ttu-id="7a236-157">Krypteringsmetod</span><span class="sxs-lookup"><span data-stu-id="7a236-157">Encryption method</span></span>
  - <span data-ttu-id="7a236-158">Krypterings mal len</span><span class="sxs-lookup"><span data-stu-id="7a236-158">Encryption template</span></span>

- <span data-ttu-id="7a236-159">**Visa data efter: de fem främsta mottagar domänerna**: i den här vyn visas ett cirkel diagram med antal skickade meddelanden för de fem främsta domänerna.</span><span class="sxs-lookup"><span data-stu-id="7a236-159">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="7a236-160">Om du klickar på **filter**kan du välja ett **start datum** och ett **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="7a236-160">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="7a236-161">Vyn detaljerad tabell för krypterings rapporten</span><span class="sxs-lookup"><span data-stu-id="7a236-161">Details table view for the Encryption report</span></span>

<span data-ttu-id="7a236-162">Om du klickar på **Visa informations tabell**beror informationen som visas på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="7a236-162">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="7a236-163">**Bryt ner med: krypterings metod** eller **Bryt ner med: krypterings mal len**: följande information visas:</span><span class="sxs-lookup"><span data-stu-id="7a236-163">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="7a236-164">**Datum**</span><span class="sxs-lookup"><span data-stu-id="7a236-164">**Date**</span></span>
  - <span data-ttu-id="7a236-165">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="7a236-165">**Sender address**</span></span>
  - <span data-ttu-id="7a236-166">**Krypterings mal len**</span><span class="sxs-lookup"><span data-stu-id="7a236-166">**Encryption template**</span></span>
  - <span data-ttu-id="7a236-167">**Krypteringsmetod**</span><span class="sxs-lookup"><span data-stu-id="7a236-167">**Encryption method**</span></span>
  - <span data-ttu-id="7a236-168">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="7a236-168">**Recipient address**</span></span>
  - <span data-ttu-id="7a236-169">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="7a236-169">**Subject**</span></span>

- <span data-ttu-id="7a236-170">**Visa data enligt: de 5 främsta mottagar domänerna**:</span><span class="sxs-lookup"><span data-stu-id="7a236-170">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="7a236-171">**Datum**</span><span class="sxs-lookup"><span data-stu-id="7a236-171">**Date**</span></span>
  - <span data-ttu-id="7a236-172">**Mottagar domän**</span><span class="sxs-lookup"><span data-stu-id="7a236-172">**Recipient domain**</span></span>
  - <span data-ttu-id="7a236-173">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="7a236-173">**Message count**</span></span>
  
<span data-ttu-id="7a236-174">Om du klickar på **filter** i en detaljerad tabellvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="7a236-174">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="7a236-175">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="7a236-175">**Start date** and **End date**</span></span>
- <span data-ttu-id="7a236-176">Krypteringsmetod</span><span class="sxs-lookup"><span data-stu-id="7a236-176">Encryption method</span></span>
- <span data-ttu-id="7a236-177">Krypterings mal len</span><span class="sxs-lookup"><span data-stu-id="7a236-177">Encryption template</span></span>

<span data-ttu-id="7a236-178">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="7a236-178">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="7a236-179">Flödes status rapport</span><span class="sxs-lookup"><span data-stu-id="7a236-179">Mailflow status report</span></span>

<span data-ttu-id="7a236-180">I **rapporten flödes** schema visas information om skadlig program vara, skräp post, nätfiske och Edge-blockerade meddelanden.</span><span class="sxs-lookup"><span data-stu-id="7a236-180">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="7a236-181">Mer information finns i [flödes status rapport](view-mail-flow-reports.md#mailflow-status-report).</span><span class="sxs-lookup"><span data-stu-id="7a236-181">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="7a236-182">Identifiering av skadlig program vara i e-postrapport</span><span class="sxs-lookup"><span data-stu-id="7a236-182">Malware detections in email report</span></span>

<span data-ttu-id="7a236-183">**Identifiering av skadlig program vara i e-** postrapporten visar information om identifiering av skadlig program vara i inkommande och utgående e-postmeddelanden (malware identifieras av Exchange Online Protection eller EOP).</span><span class="sxs-lookup"><span data-stu-id="7a236-183">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="7a236-184">Mer information om skydd mot skadlig program vara i EOP finns i [skydda mot skadlig program vara i EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="7a236-184">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="7a236-185">Med filtret mängd filter kan du använda 90 dagar, men det går bara att filtrera tabellen med information i 10 dagar.</span><span class="sxs-lookup"><span data-stu-id="7a236-185">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="7a236-186">Om du vill visa rapporten öppnar du [säkerhets & efterlevnad](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **identifiering av skadlig kod i e-post**.</span><span class="sxs-lookup"><span data-stu-id="7a236-186">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Malware detections in email**.</span></span> <span data-ttu-id="7a236-187">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="7a236-187">To go directly to the report, open <https://protection.office.com/reportv2?id=MalwareDetections>.</span></span>

![Identifiering av skadlig program vara i e-postwidget på rapport instrument panelen](../../media/malware-detections-widget.png)

<span data-ttu-id="7a236-189">Du kan filtrera både diagrammet och informations tabellen genom att klicka på **filter** och välja:</span><span class="sxs-lookup"><span data-stu-id="7a236-189">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="7a236-190">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="7a236-190">**Start date** and **End date**</span></span>
- <span data-ttu-id="7a236-191">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="7a236-191">**Inbound**</span></span>
- <span data-ttu-id="7a236-192">**Gående**</span><span class="sxs-lookup"><span data-stu-id="7a236-192">**Outbound**</span></span>

![Rapportvy i rapporten om skadlig program vara i e-postrapporten](../../media/malware-detections-report-view.png)

<span data-ttu-id="7a236-194">Om du klickar på **Visa informations tabell**kan du se följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="7a236-194">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="7a236-195">**Datum**</span><span class="sxs-lookup"><span data-stu-id="7a236-195">**Date**</span></span>
- <span data-ttu-id="7a236-196">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="7a236-196">**Sender address**</span></span>
- <span data-ttu-id="7a236-197">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="7a236-197">**Recipient address**</span></span>
- <span data-ttu-id="7a236-198">**Meddelande-ID**: tillgängligt i fältet **meddelande-ID** i meddelande huvudet och ska vara unikt.</span><span class="sxs-lookup"><span data-stu-id="7a236-198">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="7a236-199">Ett exempel värde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Observera vinkelparenteser).</span><span class="sxs-lookup"><span data-stu-id="7a236-199">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="7a236-200">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="7a236-200">**Subject**</span></span>
- <span data-ttu-id="7a236-201">**Datafil**</span><span class="sxs-lookup"><span data-stu-id="7a236-201">**Filename**</span></span>
- <span data-ttu-id="7a236-202">**Namn på skadlig kod**</span><span class="sxs-lookup"><span data-stu-id="7a236-202">**Malware name**</span></span>

<span data-ttu-id="7a236-203">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="7a236-203">To go back to the report view, click **View report**.</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="7a236-204">Skicka och ta emot e-postrapport</span><span class="sxs-lookup"><span data-stu-id="7a236-204">Sent and received email report</span></span>

<span data-ttu-id="7a236-205">Den **skickade och mottagna e-** postrapporten innehåller information om skadlig kod, skräp post, regler för e-postflöde (kallas även transport regler) och avancerade identifieringar av skadlig kod efter e-post till tjänsten.</span><span class="sxs-lookup"><span data-stu-id="7a236-205">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="7a236-206">Mer information finns i [skicka och ta emot e-postrapport](view-mail-flow-reports.md#sent-and-received-email-report).</span><span class="sxs-lookup"><span data-stu-id="7a236-206">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="7a236-207">Rapport om skräp identifiering</span><span class="sxs-lookup"><span data-stu-id="7a236-207">Spam detections report</span></span>

<span data-ttu-id="7a236-208">I rapporten **skräp identifiering** visas skräp post meddelanden som blockeras av EOP.</span><span class="sxs-lookup"><span data-stu-id="7a236-208">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="7a236-209">Meddelanden räknas individuellt, inte per mottagare.</span><span class="sxs-lookup"><span data-stu-id="7a236-209">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="7a236-210">Om till exempel samma skräp post skickades till 100 mottagare i din organisation räknas det som ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="7a236-210">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="7a236-211">I den sammanslagna vyn kan du filtrera 90 dagar medan tabellen information tillåter filtrering i tio dagar.</span><span class="sxs-lookup"><span data-stu-id="7a236-211">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="7a236-212">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **skräp identifiering**.</span><span class="sxs-lookup"><span data-stu-id="7a236-212">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spam detections**.</span></span> <span data-ttu-id="7a236-213">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="7a236-213">To go directly to the report, open <https://protection.office.com/reportv2?id=SpamDetections>.</span></span>

![Widget för skräp post identifiering i instrument panelen rapporter](../../media/spam-detections-report-widget.png)

<span data-ttu-id="7a236-215">Mer information om skydd mot skräp post finns i [skydd mot skräp post i EOP](anti-spam-protection.md).</span><span class="sxs-lookup"><span data-stu-id="7a236-215">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="7a236-216">Rapportvy för rapporten skräp identifiering</span><span class="sxs-lookup"><span data-stu-id="7a236-216">Report view for the Spam detections report</span></span>

<span data-ttu-id="7a236-217">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="7a236-217">The following charts are available in the report view:</span></span>

- <span data-ttu-id="7a236-218">**Bryt ned genom: åtgärd**: följande händelse typer visas:</span><span class="sxs-lookup"><span data-stu-id="7a236-218">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="7a236-219">**Skräp post filtrerat**</span><span class="sxs-lookup"><span data-stu-id="7a236-219">**Spam content filtered**</span></span>
  - <span data-ttu-id="7a236-220">**Skräp post IP-block**</span><span class="sxs-lookup"><span data-stu-id="7a236-220">**Spam IP block**</span></span>
  - <span data-ttu-id="7a236-221">**Skräp post omslag**</span><span class="sxs-lookup"><span data-stu-id="7a236-221">**Spam envelope block**</span></span>
  - <span data-ttu-id="7a236-222">**Spam DBEB filter**: mappad Edge-blockering (DBEB)</span><span class="sxs-lookup"><span data-stu-id="7a236-222">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="7a236-223">När du hovrar över en dag (data punkt) i diagrammet kan du se hur många objekt som har blockerats den dagen samt hur objekten kategoriseras.</span><span class="sxs-lookup"><span data-stu-id="7a236-223">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![Aktivitetsvy i rapporten om skräp identifiering](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="7a236-225">**Bryt ned efter: riktning**: följande vägvisningar visas:</span><span class="sxs-lookup"><span data-stu-id="7a236-225">**Break down by:Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="7a236-226">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="7a236-226">**Inbound**</span></span>
  - <span data-ttu-id="7a236-227">**Gående**</span><span class="sxs-lookup"><span data-stu-id="7a236-227">**Outbound**</span></span>

  ![Vyn riktning i rapporten skräp identifiering](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="7a236-229">Om du klickar på **filter** i en rapportvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="7a236-229">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="7a236-230">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="7a236-230">**Start date** and **End date**</span></span>
- <span data-ttu-id="7a236-231">Riktnings värden</span><span class="sxs-lookup"><span data-stu-id="7a236-231">Direction values</span></span>
- <span data-ttu-id="7a236-232">Händelse typ värden</span><span class="sxs-lookup"><span data-stu-id="7a236-232">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="7a236-233">Vyn detaljerad tabell för rapporten skräp identifiering</span><span class="sxs-lookup"><span data-stu-id="7a236-233">Details table view for the Spam detections report</span></span>

<span data-ttu-id="7a236-234">Om du klickar på **Visa informations tabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="7a236-234">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="7a236-235">**Datum**</span><span class="sxs-lookup"><span data-stu-id="7a236-235">**Date**</span></span>
- <span data-ttu-id="7a236-236">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="7a236-236">**Sender address**</span></span>
- <span data-ttu-id="7a236-237">**Mottagarens adress**</span><span class="sxs-lookup"><span data-stu-id="7a236-237">**Recipient address**</span></span>
- <span data-ttu-id="7a236-238">**Händelse typ**</span><span class="sxs-lookup"><span data-stu-id="7a236-238">**Event type**</span></span>
- <span data-ttu-id="7a236-239">**Fattning**</span><span class="sxs-lookup"><span data-stu-id="7a236-239">**Action**</span></span>
- <span data-ttu-id="7a236-240">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="7a236-240">**Subject**</span></span>

<span data-ttu-id="7a236-241">Om du klickar på **filter** i en informations tabell kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="7a236-241">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="7a236-242">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="7a236-242">**Start date** and **End date**</span></span>
- <span data-ttu-id="7a236-243">Riktnings värden</span><span class="sxs-lookup"><span data-stu-id="7a236-243">Direction values</span></span>
- <span data-ttu-id="7a236-244">Händelse typ värden</span><span class="sxs-lookup"><span data-stu-id="7a236-244">Event type values</span></span>

<span data-ttu-id="7a236-245">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="7a236-245">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="7a236-246">Rapport om falska identifieringar</span><span class="sxs-lookup"><span data-stu-id="7a236-246">Spoof detections report</span></span>

<span data-ttu-id="7a236-247">Rapporten **Spoof identifieringar** visar hur många e-postmeddelanden som har identifierats och vilka som ansågs "goda" (falsk e-post gjorda för legitima affärs skäl).</span><span class="sxs-lookup"><span data-stu-id="7a236-247">The **Spoof detections** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> <span data-ttu-id="7a236-248">Mer information om förfalskning finns i [skydd mot förfalskning i EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="7a236-248">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="7a236-249">Med den sammanslagna rapporten kan du använda 90 dagar på filtreringen, men i detaljvyn kan endast tio dagar av filtrering tillåtas.</span><span class="sxs-lookup"><span data-stu-id="7a236-249">The aggregate view of the report allows for 90 days of filtering, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="7a236-250">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **rapport** \> **instrument panelen** och väljer **falska identifierings**regler.</span><span class="sxs-lookup"><span data-stu-id="7a236-250">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Spoof detections**.</span></span> <span data-ttu-id="7a236-251">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="7a236-251">To go directly to the report, open <https://protection.office.com/reportv2?id=SpoofMailReport>.</span></span>

![Widgeten för förfalskningar i rapport instrument panelen](../../media/spoof-detections-widget.png)

<span data-ttu-id="7a236-253">När du håller mus pekaren över en dag (data punkt) i diagrammet kan du se hur många e-postmeddelanden som är falska.</span><span class="sxs-lookup"><span data-stu-id="7a236-253">When you hover over a day (data point) in the chart, you can see how many spoof mail messages came through.</span></span>

<span data-ttu-id="7a236-254">Du kan filtrera både diagrammet och informations tabellen genom att klicka på **filter** och välja ett eller flera av följande värden:</span><span class="sxs-lookup"><span data-stu-id="7a236-254">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="7a236-255">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="7a236-255">**Start date** and **End date**</span></span>

- <span data-ttu-id="7a236-256">**Bra e-post**</span><span class="sxs-lookup"><span data-stu-id="7a236-256">**Good mail**</span></span>

- <span data-ttu-id="7a236-257">**Fångade som skräp post**</span><span class="sxs-lookup"><span data-stu-id="7a236-257">**Caught as spam**</span></span>

![Rapportvy i rapporten för falska identifieringar](../../media/spoof-detections-report-view.png)

<span data-ttu-id="7a236-259">Om du klickar på **Visa informations tabell**kan du se följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="7a236-259">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="7a236-260">**Datum**</span><span class="sxs-lookup"><span data-stu-id="7a236-260">**Date**</span></span>
- <span data-ttu-id="7a236-261">**Falsk avsändare**</span><span class="sxs-lookup"><span data-stu-id="7a236-261">**Spoofed sender**</span></span>
- <span data-ttu-id="7a236-262">**Sant avsändare**</span><span class="sxs-lookup"><span data-stu-id="7a236-262">**True sender**</span></span>
- <span data-ttu-id="7a236-263">**Avsändarens IP**</span><span class="sxs-lookup"><span data-stu-id="7a236-263">**Sender IP**</span></span>
- <span data-ttu-id="7a236-264">**Fattning**</span><span class="sxs-lookup"><span data-stu-id="7a236-264">**Action**</span></span>
- <span data-ttu-id="7a236-265">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="7a236-265">**Message count**</span></span>

<span data-ttu-id="7a236-266">Om du vill gå tillbaka till rapportvyn klickar du på **Visa rapport**.</span><span class="sxs-lookup"><span data-stu-id="7a236-266">To go back to the report view, click **View report**.</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="7a236-267">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="7a236-267">Threat protection status report</span></span>

<span data-ttu-id="7a236-268">Status rapporten för **hotets skydd** är tillgänglig i både EOP och Office 365 ATP; rapporterna innehåller emellertid olika data.</span><span class="sxs-lookup"><span data-stu-id="7a236-268">The **Threat protection status** report is available in both EOP and Office 365 ATP; however, the reports contain different data.</span></span> <span data-ttu-id="7a236-269">EOP kunder kan till exempel Visa information om skadlig kod som upptäckts i e-post, men inte information om [skadliga filer som identifieras av ATP för SharePoint, OneDrive eller Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7a236-269">For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected by ATP for SharePoint, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="7a236-270">I rapporten får du räknat antalet e-postmeddelanden med skadligt innehåll, till exempel filer eller webbplats adresser (URL: er) som blockerades av motorn mot skadlig program vara, [nollställning (Zap)](zero-hour-auto-purge.md)och ATP-funktioner som [säkra länkar](atp-safe-links.md), [säkra bilagor](atp-safe-attachments.md)och [ATP-nätfiske](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7a236-270">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [Safe Links](atp-safe-links.md), [Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="7a236-271">Du kan använda den här informationen för att identifiera trender eller för att avgöra om organisations principer behöver justeras.</span><span class="sxs-lookup"><span data-stu-id="7a236-271">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span> <span data-ttu-id="7a236-272">Det är viktigt att förstå att om ett meddelande skickas till fem mottagare räknas det som fem olika meddelanden och inte ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="7a236-272">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="7a236-273">Om du vill visa rapporten öppnar du [säkerhets & efterlevnad](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **skydds status**.</span><span class="sxs-lookup"><span data-stu-id="7a236-273">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Threat protection status**.</span></span> <span data-ttu-id="7a236-274">Om du vill gå direkt till rapporten öppnar du en av följande webb adresser:</span><span class="sxs-lookup"><span data-stu-id="7a236-274">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="7a236-275">Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport> .</span><span class="sxs-lookup"><span data-stu-id="7a236-275">Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport>.</span></span>
- <span data-ttu-id="7a236-276">EOP <https://protection.office.com/reportv2?id=ATPAggregateLightReport></span><span class="sxs-lookup"><span data-stu-id="7a236-276">EOP: <https://protection.office.com/reportv2?id=ATPAggregateLightReport></span></span>

![Widgeten skydds status i rapport instrument panelen](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="7a236-278">Som standard visar diagrammet data för de senaste sju dagarna.</span><span class="sxs-lookup"><span data-stu-id="7a236-278">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="7a236-279">Om du klickar på **filter**kan du välja ett datum intervall för 90 dagar (prov abonnemang kan vara begränsat till 30 dagar).</span><span class="sxs-lookup"><span data-stu-id="7a236-279">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="7a236-280">Med vyn detaljerad tabell kan du filtrera i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="7a236-280">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="7a236-281">Rapportvy för status rapport för hotet skydd</span><span class="sxs-lookup"><span data-stu-id="7a236-281">Report view for the Threat protection status report</span></span>

<span data-ttu-id="7a236-282">Följande vyer är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="7a236-282">The following views are available:</span></span>

- <span data-ttu-id="7a236-283">**Visa data via: översikt**: följande identifierings information visas:</span><span class="sxs-lookup"><span data-stu-id="7a236-283">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="7a236-284">**Skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="7a236-284">**Email malware**</span></span>
  - <span data-ttu-id="7a236-285">**E-Phish**</span><span class="sxs-lookup"><span data-stu-id="7a236-285">**Email phish**</span></span>
  - <span data-ttu-id="7a236-286">**Skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="7a236-286">**Content malware**</span></span>

  ![Vyn Översikt i status rapport för hotet skydd](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="7a236-288">**Visa data efter: innehåll \> Malware**<sup>1</sup>: följande information visas för Office 365 ATP-organisationer:</span><span class="sxs-lookup"><span data-stu-id="7a236-288">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Office 365 ATP organizations:</span></span>

  - <span data-ttu-id="7a236-289">**Skydd mot skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="7a236-289">**Anti-malware engine**</span></span>
  - <span data-ttu-id="7a236-290">**Fil sprängning**</span><span class="sxs-lookup"><span data-stu-id="7a236-290">**File detonation**</span></span>

  ![Vyn skadlig program vara i rapporten skydds status](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="7a236-292">**Bryta ned efter: identifierings teknologi** och **Visa data via: e- \> Phish**: följande information visas:</span><span class="sxs-lookup"><span data-stu-id="7a236-292">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="7a236-293">**ATP – genererad URL-rykte**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7a236-293">**ATP-generated URL reputation**<sup>1</sup></span></span>
  - <span data-ttu-id="7a236-294">**Avancerat Phish-filter**</span><span class="sxs-lookup"><span data-stu-id="7a236-294">**Advanced phish filter**</span></span>
  - <span data-ttu-id="7a236-295">**Anti-förfalskningar: DMARC-fel**</span><span class="sxs-lookup"><span data-stu-id="7a236-295">**Anti-spoof: DMARC failure**</span></span>
  - <span data-ttu-id="7a236-296">**Anti-förfalskningar: inom organisationen**</span><span class="sxs-lookup"><span data-stu-id="7a236-296">**Anti-spoof: Intra-org**</span></span>
  - <span data-ttu-id="7a236-297">**Skydd mot förfalskning: extern domän**</span><span class="sxs-lookup"><span data-stu-id="7a236-297">**Anti-spoof: external domain**</span></span>
  - <span data-ttu-id="7a236-298">**Varumärkes-personifiering**</span><span class="sxs-lookup"><span data-stu-id="7a236-298">**Brand impersonation**</span></span>
  - <span data-ttu-id="7a236-299">**Domän person**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7a236-299">**Domain impersonation**<sup>1</sup></span></span>
  - <span data-ttu-id="7a236-300">**EOP URL-rykte**</span><span class="sxs-lookup"><span data-stu-id="7a236-300">**EOP URL reputation**</span></span>
  - <span data-ttu-id="7a236-301">**Allmänt Phish-filter**</span><span class="sxs-lookup"><span data-stu-id="7a236-301">**General phish filter**</span></span>
  - <span data-ttu-id="7a236-302">**Gemensamma**</span><span class="sxs-lookup"><span data-stu-id="7a236-302">**Others**</span></span>
  - <span data-ttu-id="7a236-303">**PHISH ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7a236-303">**Phish ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="7a236-304">**URL-sprängare**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7a236-304">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="7a236-305">**Användarens personifiering**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7a236-305">**User impersonation**<sup>1</sup></span></span>

  ![Identifierings teknologi vy för nät fiske-e-post i status rapport för hotet skydd](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="7a236-307">**Bryta ned efter: identifierings teknologi** och **Visa data via: e- \> postskadlig program vara**: följande information visas:</span><span class="sxs-lookup"><span data-stu-id="7a236-307">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="7a236-308">**ATP – genererad fil rykte**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7a236-308">**ATP-generated file reputation**<sup>1</sup></span></span>
  - <span data-ttu-id="7a236-309">**Skydd mot skadlig program vara**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7a236-309">**Anti-malware engine**<sup>1</sup></span></span>
  - <span data-ttu-id="7a236-310">**Fil typs block för principer mot skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="7a236-310">**Anti-malware policy file type block**</span></span>
  - <span data-ttu-id="7a236-311">**Fil Spräng**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7a236-311">**File detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="7a236-312">**Fil rykte**</span><span class="sxs-lookup"><span data-stu-id="7a236-312">**Malicious file reputation**</span></span>
  - <span data-ttu-id="7a236-313">**Malware, ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="7a236-313">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="7a236-314">**Gemensamma**</span><span class="sxs-lookup"><span data-stu-id="7a236-314">**Others**</span></span>

  ![Identifierings teknologi vy för malware i status rapport för hotet skydd](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="7a236-316">**Bryt ned med: princip typ** och **Visa data via: e- \> Phish** eller **Visa data via: e-post för \> skadlig kod**: följande information visas:</span><span class="sxs-lookup"><span data-stu-id="7a236-316">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="7a236-317">**Skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="7a236-317">**Anti-malware**</span></span>
  - <span data-ttu-id="7a236-318">**Säker bilaga**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7a236-318">**Safe Attachment**<sup>1</sup></span></span>
  - <span data-ttu-id="7a236-319">**Anti-Phish**</span><span class="sxs-lookup"><span data-stu-id="7a236-319">**Anti-phish**</span></span>
  - <span data-ttu-id="7a236-320">**Skydd mot skräp post**</span><span class="sxs-lookup"><span data-stu-id="7a236-320">**Anti-spam**</span></span>
  - <span data-ttu-id="7a236-321">**Regel för e-postflöde** (kallas även transport regel)</span><span class="sxs-lookup"><span data-stu-id="7a236-321">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="7a236-322">**Gemensamma**</span><span class="sxs-lookup"><span data-stu-id="7a236-322">**Others**</span></span>

  ![Vy för princip typ för nät fiske meddelanden i status rapport för hotet skydd](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="7a236-324">**Bryt ner med: leverans status** och **Visa data via: e- \> Phish** eller **Visa data via: e-post för \> skadlig kod**: följande information visas:</span><span class="sxs-lookup"><span data-stu-id="7a236-324">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="7a236-325">**Leveransen misslyckades**</span><span class="sxs-lookup"><span data-stu-id="7a236-325">**Delivery failed**</span></span>
  - <span data-ttu-id="7a236-326">**Avbröts**</span><span class="sxs-lookup"><span data-stu-id="7a236-326">**Dropped**</span></span>
  - <span data-ttu-id="7a236-327">**Vidarekopplas**</span><span class="sxs-lookup"><span data-stu-id="7a236-327">**Forwarded**</span></span>
  - <span data-ttu-id="7a236-328">**Den värdbaserade post lådan: anpassad mapp**</span><span class="sxs-lookup"><span data-stu-id="7a236-328">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="7a236-329">**Den värdbaserade post lådan: borttagna objekt**</span><span class="sxs-lookup"><span data-stu-id="7a236-329">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="7a236-330">**Den värdbaserade post lådan: Inkorgen**</span><span class="sxs-lookup"><span data-stu-id="7a236-330">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="7a236-331">**Post låda: skräp post**</span><span class="sxs-lookup"><span data-stu-id="7a236-331">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="7a236-332">**Lokal server: levereras**</span><span class="sxs-lookup"><span data-stu-id="7a236-332">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="7a236-333">**Karantän**</span><span class="sxs-lookup"><span data-stu-id="7a236-333">**Quarantine**</span></span>

  ![Vyn leverans status för phishing-e-post i status rapport för hotet skydd](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="7a236-335"><sup>1</sup> Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="7a236-335"><sup>1</sup> Office 365 ATP only</span></span>

<span data-ttu-id="7a236-336"><sup>2</sup> noll-timmars autorensning (Zap) är inte tillgängligt i fristående EOP (den fungerar bara i Exchange Online-postlådor).</span><span class="sxs-lookup"><span data-stu-id="7a236-336"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="7a236-337">Om du klickar på **filter**kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="7a236-337">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="7a236-338">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="7a236-338">**Start date** and **End date**</span></span>
- <span data-ttu-id="7a236-339">**Proxyidentifiering**</span><span class="sxs-lookup"><span data-stu-id="7a236-339">**Detection**</span></span>
- <span data-ttu-id="7a236-340">**Skyddas av**: **ATP** eller **EOP**</span><span class="sxs-lookup"><span data-stu-id="7a236-340">**Protected by**: **ATP** or **EOP**</span></span>
- <span data-ttu-id="7a236-341">**Tagg**: Filtrera efter tagg för att returnera användare eller grupper som har en viss tagg.</span><span class="sxs-lookup"><span data-stu-id="7a236-341">**Tag**: filter by tag to return users or groups that have had a specific tag applied.</span></span> <span data-ttu-id="7a236-342">Mer information om användar flaggor finns i [User Tags](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="7a236-342">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="7a236-343">**Domain**</span><span class="sxs-lookup"><span data-stu-id="7a236-343">**Domain**</span></span>

> [!NOTE]
> <span data-ttu-id="7a236-344">**Skyddas av**, **tagg** och **Domain** är endast Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="7a236-344">**Protected by**, **Tag** and **Domain** are Office 365 ATP only.</span></span> <span data-ttu-id="7a236-345">De här filter bara egenskaperna är inte tillgängliga i **Visa data genom: \> skadlig program vara**.</span><span class="sxs-lookup"><span data-stu-id="7a236-345">These filterable properties are not available in **View data by: Content \> Malware**.</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="7a236-346">Vyn detaljerad tabell för status rapport för hotet skydd</span><span class="sxs-lookup"><span data-stu-id="7a236-346">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="7a236-347">Om du klickar på **Visa informations tabell**beror informationen som visas på diagrammet du tittade på:</span><span class="sxs-lookup"><span data-stu-id="7a236-347">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="7a236-348">**Visa data efter: innehåll \> Skadlig kod**:</span><span class="sxs-lookup"><span data-stu-id="7a236-348">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="7a236-349">**Datum**</span><span class="sxs-lookup"><span data-stu-id="7a236-349">**Date**</span></span>
  - <span data-ttu-id="7a236-350">**Plats**</span><span class="sxs-lookup"><span data-stu-id="7a236-350">**Location**</span></span>
  - <span data-ttu-id="7a236-351">**Omkopplad av**</span><span class="sxs-lookup"><span data-stu-id="7a236-351">**Directed by**</span></span>
  - <span data-ttu-id="7a236-352">**Namn på skadlig kod**</span><span class="sxs-lookup"><span data-stu-id="7a236-352">**Malware name**</span></span>

<span data-ttu-id="7a236-353">Om du klickar på **filter** i den här vyn kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="7a236-353">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="7a236-354">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="7a236-354">**Start date** and **End date**</span></span>
- <span data-ttu-id="7a236-355">**Proxyidentifiering**</span><span class="sxs-lookup"><span data-stu-id="7a236-355">**Detection**</span></span>

<span data-ttu-id="7a236-356">**Visa data efter: översikt**: knappen för **tabell information** är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="7a236-356">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="7a236-357">Alla andra diagram:</span><span class="sxs-lookup"><span data-stu-id="7a236-357">All other charts:</span></span>

  - <span data-ttu-id="7a236-358">**Datum**</span><span class="sxs-lookup"><span data-stu-id="7a236-358">**Date**</span></span>
  - <span data-ttu-id="7a236-359">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="7a236-359">**Subject**</span></span>
  - <span data-ttu-id="7a236-360">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="7a236-360">**Sender**</span></span>
  - <span data-ttu-id="7a236-361">**Mottagarna**</span><span class="sxs-lookup"><span data-stu-id="7a236-361">**Recipients**</span></span>
  - <span data-ttu-id="7a236-362">**Identifieras av**</span><span class="sxs-lookup"><span data-stu-id="7a236-362">**Detected by**</span></span>
  - <span data-ttu-id="7a236-363">**Leverans status**</span><span class="sxs-lookup"><span data-stu-id="7a236-363">**Delivery status**</span></span>
  - <span data-ttu-id="7a236-364">**Kompromiss källa**</span><span class="sxs-lookup"><span data-stu-id="7a236-364">**Source of compromise**</span></span>
  - <span data-ttu-id="7a236-365">**Taggen**</span><span class="sxs-lookup"><span data-stu-id="7a236-365">**Tags**</span></span>

<span data-ttu-id="7a236-366">Om du klickar på **filter**kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="7a236-366">If you click **Filters**, you can modify the report with the following filters:</span></span>

- <span data-ttu-id="7a236-367">**Start datum** och **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="7a236-367">**Start date** and **End date**</span></span>
- <span data-ttu-id="7a236-368">**Proxyidentifiering**</span><span class="sxs-lookup"><span data-stu-id="7a236-368">**Detection**</span></span>
- <span data-ttu-id="7a236-369">**Skyddas av** (endast Office 365 ATP): **ATP** eller **EOP**</span><span class="sxs-lookup"><span data-stu-id="7a236-369">**Protected by** (Office 365 ATP only): **ATP** or **EOP**</span></span>
- <span data-ttu-id="7a236-370">**Tagg**: Filtrera efter tagg för att returnera användare eller grupper som har en viss tagg.</span><span class="sxs-lookup"><span data-stu-id="7a236-370">**Tag**: filter by tag to return users or groups that have had a specific tag applied.</span></span> <span data-ttu-id="7a236-371">Mer information om användar flaggor finns i [User Tags](user-tags.md).</span><span class="sxs-lookup"><span data-stu-id="7a236-371">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="7a236-372">**Domain**</span><span class="sxs-lookup"><span data-stu-id="7a236-372">**Domain**</span></span>
- <span data-ttu-id="7a236-373">**Mottagare** (Observera att den här filter bara egenskapen är endast tillgänglig i vyn detaljerad tabell)</span><span class="sxs-lookup"><span data-stu-id="7a236-373">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="7a236-374">Top skadlig kod-rapport</span><span class="sxs-lookup"><span data-stu-id="7a236-374">Top malware report</span></span>

<span data-ttu-id="7a236-375">Den **översta program varan** rapporterar visar de olika typer av skadlig kod som identifieras av [skydd mot skadlig program vara i EOP](anti-malware-protection.md).</span><span class="sxs-lookup"><span data-stu-id="7a236-375">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="7a236-376">Om du vill visa rapporten öppnar du [säkerhets & Compliance Center](https://protection.office.com), går till **Reports** \> **instrument paneler** för rapporter och väljer **högsta skadliga program vara**.</span><span class="sxs-lookup"><span data-stu-id="7a236-376">To view the report, open the [Security & Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** and select **Top malware**.</span></span> <span data-ttu-id="7a236-377">Om du vill gå direkt till rapporten öppnar du <https://protection.office.com/reportv2?id=TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="7a236-377">To go directly to the report, open <https://protection.office.com/reportv2?id=TopMalware>.</span></span>

![Widgeten Top skadlig kod på instrument panelen rapporter](../../media/top-malware-report-widget.png)

<span data-ttu-id="7a236-379">När du hovrar över en sektor i cirkel diagrammet kan du se namnet på en typ av skadlig kod och hur många meddelanden som har identifierats.</span><span class="sxs-lookup"><span data-stu-id="7a236-379">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![Övre rapport över skadlig program vara](../../media/top-malware-report-view.png)

<span data-ttu-id="7a236-381">Om du klickar på **Visa informations tabell**kan du se följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="7a236-381">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="7a236-382">**Övre skadliga program**</span><span class="sxs-lookup"><span data-stu-id="7a236-382">**Top malware**</span></span>
- <span data-ttu-id="7a236-383">**Öka**</span><span class="sxs-lookup"><span data-stu-id="7a236-383">**Count**</span></span>

<span data-ttu-id="7a236-384">Om du klickar på **filter** i vyn rapport eller detaljerad tabell kan du ange ett datum intervall med **start datum** och **slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="7a236-384">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="7a236-385">Rapport om skydd mot URL-hotet</span><span class="sxs-lookup"><span data-stu-id="7a236-385">URL threat protection report</span></span>

<span data-ttu-id="7a236-386">**Rapporten för skydd mot URL-hotet** är tillgänglig i Office 365 Avancerat skydd (ATP).</span><span class="sxs-lookup"><span data-stu-id="7a236-386">The **URL threat protection report** is available in Office 365 Advanced Threat Protection (ATP).</span></span> <span data-ttu-id="7a236-387">Mer information finns i [rapporten om skydd mot URL-hotet](view-reports-for-atp.md#url-threat-protection-report).</span><span class="sxs-lookup"><span data-stu-id="7a236-387">For more information, see [URL threat protection report](view-reports-for-atp.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="7a236-388">Rapport med rapporterat meddelande</span><span class="sxs-lookup"><span data-stu-id="7a236-388">User-reported messages report</span></span>

<span data-ttu-id="7a236-389">I rapporten **rapporterad meddelanden** visas information om e-postmeddelanden som användare har rapporterat som skräp post, nät fiske försök eller god e-post med hjälp av [rapport tillägget](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span><span class="sxs-lookup"><span data-stu-id="7a236-389">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).</span></span>

<span data-ttu-id="7a236-390">Information är tillgänglig för varje meddelande, inklusive leverans orsaken, sådant undantag för skräp post eller regel för e-postflöde som har kon figurer ATS för din organisation.</span><span class="sxs-lookup"><span data-stu-id="7a236-390">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="7a236-391">Om du vill visa information väljer du ett objekt i listan med användar rapporter och visar sedan informationen på flikarna **Sammanfattning** och **information** .</span><span class="sxs-lookup"><span data-stu-id="7a236-391">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![I rapporten rapporterade meddelanden visas meddelanden som användare märkt som skräp post, inte skräp post eller nätfiske-försök.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="7a236-393">Om du vill visa den här rapporten gör du något av följande i avsnittet [säkerhet & regelefterlevnad](https://protection.office.com):</span><span class="sxs-lookup"><span data-stu-id="7a236-393">To view this report, in the [Security & Compliance Center](https://protection.office.com), do one of the following:</span></span>

- <span data-ttu-id="7a236-394">Gå till instrument panel för **Threat Management** \> **Dashboard** \> **-rapporter**.</span><span class="sxs-lookup"><span data-stu-id="7a236-394">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>

- <span data-ttu-id="7a236-395">Gå till **Threat Management** \> **Granska** \> **användardefinierade meddelanden**.</span><span class="sxs-lookup"><span data-stu-id="7a236-395">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>

![Välj Threat Management \> Granska \> användarnas rapporterade meddelanden i säkerhets & efterlevnad](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> <span data-ttu-id="7a236-397">För att det rapporterade meddelandet ska fungera korrekt **måste gransknings loggning vara aktiverat** för din Office 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="7a236-397">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="7a236-398">Det gör du vanligt vis av någon som har rollen gransknings loggar som tilldelats i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7a236-398">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="7a236-399">Mer information finns i [Aktivera eller inaktivera Gransknings logg för Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span><span class="sxs-lookup"><span data-stu-id="7a236-399">For more information, see [Turn Microsoft 365 audit log search on or off](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="7a236-400">Vilka behörigheter behövs för att visa rapporterna?</span><span class="sxs-lookup"><span data-stu-id="7a236-400">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="7a236-401">Om du vill visa och använda rapporterna måste du vara medlem i den angivna roll gruppen i säkerhets & efterföljandekrav **och** i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7a236-401">To view and use the reports, you need to be a member of the specified role group in the Security & Compliance Center **and** in Exchange Online.</span></span>

- <span data-ttu-id="7a236-402">I säkerhets & Compliance Center måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="7a236-402">In the Security & Compliance Center, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="7a236-403">-Organisations hantering-säkerhets administratör (du kan också göra det i [Azure Active Directory Admin Center](https://aad.portal.azure.com) -säkerhets läsare</span><span class="sxs-lookup"><span data-stu-id="7a236-403">-Organization Management -Security Administrator (you can also do this in the [Azure Active Directory admin center](https://aad.portal.azure.com) -Security Reader</span></span>

  <span data-ttu-id="7a236-404">Mer information finns i [Behörigheter i Säkerhets- och efterlevnadscentret](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span><span class="sxs-lookup"><span data-stu-id="7a236-404">For more information, see [Permissions in the Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).</span></span>

- <span data-ttu-id="7a236-405">I Exchange Online måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="7a236-405">In Exchange Online, you need to be a member of one of the following role groups:</span></span>

  <span data-ttu-id="7a236-406">-Organisations hantering-Visa endast organisations hantering-endast Visa-mottagare-kompatibilitetskontrollen</span><span class="sxs-lookup"><span data-stu-id="7a236-406">-Organization Management -View-only Organization Management -View-Only Recipients -Compliance Management</span></span>

<span data-ttu-id="7a236-407">Mer information finns i [behörigheter i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) och [Hantera roll grupper i Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="7a236-407">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) and [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="7a236-408">Vad händer om rapporterna inte visar data?</span><span class="sxs-lookup"><span data-stu-id="7a236-408">What if the reports aren't showing data?</span></span>

<span data-ttu-id="7a236-409">Om du inte ser data i rapporterna kontrollerar du att dina principer är korrekt konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="7a236-409">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="7a236-410">Mer information finns i [skydda mot hot](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="7a236-410">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7a236-411">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="7a236-411">Related topics</span></span>

[<span data-ttu-id="7a236-412">Skydd mot skräp post och skyddet mot skadlig program vara i EOP</span><span class="sxs-lookup"><span data-stu-id="7a236-412">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="7a236-413">Smarta rapporter och insikter i säkerhets & efterlevnad</span><span class="sxs-lookup"><span data-stu-id="7a236-413">Smart reports and insights in the Security & Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="7a236-414">Visa rapporter om e-postflöden i säkerhets & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="7a236-414">View mail flow reports in the Security & Compliance Center</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="7a236-415">Visa rapporter för Office 365 Avancerat skydd</span><span class="sxs-lookup"><span data-stu-id="7a236-415">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
