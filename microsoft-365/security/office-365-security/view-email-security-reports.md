---
title: Visa e-postsäkerhetsrapporter i Microsoft 365 Defender-portalen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Lär dig hur du hittar och använder e-postsäkerhetsrapporter för din organisation. Säkerhetsrapporter för e-post finns tillgängliga Microsoft 365 Defender-portalen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bb7570722fcc957ca86d68f6b42ef254578d7bd7
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930331"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="84aaa-104">Visa e-postsäkerhetsrapporter i Microsoft 365 Defender-portalen</span><span class="sxs-lookup"><span data-stu-id="84aaa-104">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="84aaa-105">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="84aaa-105">**Applies to**</span></span>
- [<span data-ttu-id="84aaa-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="84aaa-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="84aaa-107">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="84aaa-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="84aaa-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84aaa-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="84aaa-109">Det finns en mängd olika rapporter på [Microsoft 365 Defender-portalen](https://security.microsoft.com) som hjälper dig se hur e-postsäkerhetsfunktioner, till exempel funktioner för skydd mot skräppost, skadlig programvara och kryptering i Microsoft 365 skyddar organisationen.</span><span class="sxs-lookup"><span data-stu-id="84aaa-109">A variety of reports are available in the [Microsoft 365 Defender portal](https://security.microsoft.com) to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="84aaa-110">Om du har [nödvändiga](#what-permissions-are-needed-to-view-these-reports)behörigheter kan du visa de här rapporterna  i Microsoft 365 Defender-portalen genom att gå till Rapporterar e-& för samarbete \>  \> **E& och samarbetsrapporter**.</span><span class="sxs-lookup"><span data-stu-id="84aaa-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="84aaa-111">Gå direkt till instrumentpanelen Rapporter genom att öppna <https://security.microsoft.com/emailandcollabreport> .</span><span class="sxs-lookup"><span data-stu-id="84aaa-111">To go directly to the Reports dashboard, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Instrumentpanelen Rapporter i Microsoft 365 Defender-portalen](../../media/email-collaboration-reports.png)

## <a name="compromised-users-report"></a><span data-ttu-id="84aaa-113">Rapport om komprometterade användare</span><span class="sxs-lookup"><span data-stu-id="84aaa-113">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="84aaa-114">Den här rapporten är tillgänglig i Microsoft 365 organisationer med Exchange Online postlådor.</span><span class="sxs-lookup"><span data-stu-id="84aaa-114">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="84aaa-115">Det är inte tillgängligt i fristående EOP Exchange Online Protection(EOP).</span><span class="sxs-lookup"><span data-stu-id="84aaa-115">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="84aaa-116">I **rapporten Komprometterade** användare visas antalet användarkonton som har markerats **som misstänkta eller** begränsade **under** de senaste 7 dagarna.</span><span class="sxs-lookup"><span data-stu-id="84aaa-116">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="84aaa-117">Konton i något av dessa tillstånd är problematiska eller till och med komprometterade.</span><span class="sxs-lookup"><span data-stu-id="84aaa-117">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="84aaa-118">Med regelbunden användning kan du använda rapporten för att upptäcka ökningar och även trender i misstänkta eller begränsade konton.</span><span class="sxs-lookup"><span data-stu-id="84aaa-118">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="84aaa-119">Mer information om komprometterade användare finns i [Svara på ett komprometterat e-postkonto.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="84aaa-119">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![Widget för komprometterade användare i instrumentpanelen Rapporter](../../media/compromised-users-report-widget.png)

<span data-ttu-id="84aaa-121">I mängdvyn visas data för de senaste 90 dagarna och i detaljvyn visas data för de senaste 30 dagarna.</span><span class="sxs-lookup"><span data-stu-id="84aaa-121">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="84aaa-122">Om du vill visa rapporten öppnar du Microsoft 365  [Defender-portalen](https://security.microsoft.com), går till E& och samarbete via e& och klickar på Visa \>  \>  **information** under **Komprometterade användare.**</span><span class="sxs-lookup"><span data-stu-id="84aaa-122">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Compromised users**.</span></span> <span data-ttu-id="84aaa-123">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/CompromisedUsers> .</span><span class="sxs-lookup"><span data-stu-id="84aaa-123">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="84aaa-124">Du kan filtrera både diagrammet och informationstabellen genom att klicka **på Filter** och välja ett eller flera av följande värden:</span><span class="sxs-lookup"><span data-stu-id="84aaa-124">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="84aaa-125">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-125">**Start date** and **End date**</span></span>

- <span data-ttu-id="84aaa-126">**Misstänkt:** Användarkontot har skickat misstänkt e-postmeddelande och riskerar att bli begränsat från att skicka e-post.</span><span class="sxs-lookup"><span data-stu-id="84aaa-126">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>

- <span data-ttu-id="84aaa-127">**Begränsad:** Användarkontot har begränsats från att skicka e-post på grund av mycket misstänkta mönster.</span><span class="sxs-lookup"><span data-stu-id="84aaa-127">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

![Rapportvyn i rapporten Komprometterade användare](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="84aaa-129">Om du **klickar på Visa informationstabell** visas följande information:</span><span class="sxs-lookup"><span data-stu-id="84aaa-129">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="84aaa-130">**Tid då det skapades**</span><span class="sxs-lookup"><span data-stu-id="84aaa-130">**Creation time**</span></span>
- <span data-ttu-id="84aaa-131">**Användar-ID**</span><span class="sxs-lookup"><span data-stu-id="84aaa-131">**User ID**</span></span>
- <span data-ttu-id="84aaa-132">**Åtgärd**</span><span class="sxs-lookup"><span data-stu-id="84aaa-132">**Action**</span></span>

<span data-ttu-id="84aaa-133">Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**</span><span class="sxs-lookup"><span data-stu-id="84aaa-133">To go back to the report view, click **View report**.</span></span>

## <a name="encryption-report"></a><span data-ttu-id="84aaa-134">Krypteringsrapport</span><span class="sxs-lookup"><span data-stu-id="84aaa-134">Encryption report</span></span>

<span data-ttu-id="84aaa-135">Krypteringsrapporten **är** tillgänglig i EOP (prenumerationer med postlådor i Exchange Online eller fristående EOP utan Exchange Online postlådor).</span><span class="sxs-lookup"><span data-stu-id="84aaa-135">The **Encryption report** is available in EOP (subscriptions with mailboxes in Exchange Online or standalone EOP without Exchange Online mailboxes).</span></span> <span data-ttu-id="84aaa-136">Organisationens säkerhetsteam kan använda informationen i den här rapporten för att identifiera mönster och proaktivt tillämpa eller justera principer för känsliga e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="84aaa-136">Your organization's security team can use information in this report to identify patterns and proactively apply or adjust policies for sensitive email messages.</span></span> <span data-ttu-id="84aaa-137">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="84aaa-137">For example:</span></span>

- <span data-ttu-id="84aaa-138">Om du ser ett stort antal e-postmeddelanden som krypteras av användare kanske du vill lägga till en krypteringsprincip för att automatisera kryptering för vissa användningsfall.</span><span class="sxs-lookup"><span data-stu-id="84aaa-138">If you see a high number of email messages encrypted by users, you might want to add an encryption policy to automate encryption for certain use cases.</span></span> <span data-ttu-id="84aaa-139">Mer information finns i Definiera [e-postflödesregler för att kryptera e-postmeddelanden i Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="84aaa-139">For more information, see [Define mail flow rules to encrypt email messages in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).</span></span>

- <span data-ttu-id="84aaa-140">Om du har ett antal krypteringsmallar tillgängliga men ingen använder dem kan du undersöka om användarna behöver utbildningar i funktioner.</span><span class="sxs-lookup"><span data-stu-id="84aaa-140">If you have a number of encryption templates available but no one is using them, you might explore whether users need feature training.</span></span>

<span data-ttu-id="84aaa-141">I mängdvyn kan du filtrera de senaste 90 dagarna, medan detaljvyn tillåter filtrering i 10 dagar.</span><span class="sxs-lookup"><span data-stu-id="84aaa-141">The aggregate view allows filtering for the last 90 days, while the detail view allows filtering for 10 days.</span></span>

<span data-ttu-id="84aaa-142">Om du vill visa rapporten öppnar du Microsoft 365  [Defender-portalen](https://security.microsoft.com), går till Rapporterar e-& samarbete E& och samarbetsrapporter och klickar på Visa \>  \>  **information** under **Krypteringsrapport.**</span><span class="sxs-lookup"><span data-stu-id="84aaa-142">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Encryption report**.</span></span> <span data-ttu-id="84aaa-143">Gå direkt till rapporten genom att öppna <https://protection.office.com/reportv2?id=EncryptionReport> .</span><span class="sxs-lookup"><span data-stu-id="84aaa-143">To go directly to the report, open <https://protection.office.com/reportv2?id=EncryptionReport>.</span></span>

<span data-ttu-id="84aaa-144">Mer information om kryptering finns i [E-postkryptering i Microsoft 365](../../compliance/email-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="84aaa-144">To learn more about encryption, see [Email encryption in Microsoft 365](../../compliance/email-encryption.md).</span></span>

### <a name="report-view-for-the-encryption-report"></a><span data-ttu-id="84aaa-145">Rapportvy för rapporten Kryptering</span><span class="sxs-lookup"><span data-stu-id="84aaa-145">Report view for the Encryption report</span></span>

<span data-ttu-id="84aaa-146">Du kan använda följande filter i diagrammet:</span><span class="sxs-lookup"><span data-stu-id="84aaa-146">You can use the following filters on the chart:</span></span>

- <span data-ttu-id="84aaa-147">**Visa data efter: Meddelandekrypteringsrapport** **och Dela upp efter: Krypteringsmetod:** Följande krypteringsmetoder är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="84aaa-147">**View data by: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="84aaa-148">**Kryptering efter användare**</span><span class="sxs-lookup"><span data-stu-id="84aaa-148">**Encryption by user**</span></span>
  - <span data-ttu-id="84aaa-149">**Kryptering efter princip**</span><span class="sxs-lookup"><span data-stu-id="84aaa-149">**Encryption by policy**</span></span>

  <span data-ttu-id="84aaa-150">Om du **klickar på** Filter kan du ändra diagrammet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="84aaa-150">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="84aaa-151">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-151">**Start date** and **End date**</span></span>
  - <span data-ttu-id="84aaa-152">Krypteringsmetod.</span><span class="sxs-lookup"><span data-stu-id="84aaa-152">Encryption method.</span></span>
  - <span data-ttu-id="84aaa-153">Krypteringsmall.</span><span class="sxs-lookup"><span data-stu-id="84aaa-153">Encryption template.</span></span>

- <span data-ttu-id="84aaa-154">**Visa data efter: Meddelandekrypteringsrapport** **och Dela upp efter: Krypteringsmall:** Följande krypteringsmetoder är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="84aaa-154">**View data by: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:</span></span>

  - <span data-ttu-id="84aaa-155">**Vidarebefordra inte**</span><span class="sxs-lookup"><span data-stu-id="84aaa-155">**Do not forward**</span></span>
  - <span data-ttu-id="84aaa-156">**Kryptera endast**</span><span class="sxs-lookup"><span data-stu-id="84aaa-156">**Encrypt only**</span></span>
  - <span data-ttu-id="84aaa-157">**OME föregående**</span><span class="sxs-lookup"><span data-stu-id="84aaa-157">**OME previous**</span></span>
  - <span data-ttu-id="84aaa-158">**Anpassad**</span><span class="sxs-lookup"><span data-stu-id="84aaa-158">**Custom**</span></span>

  <span data-ttu-id="84aaa-159">Om du **klickar på** Filter kan du ändra diagrammet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="84aaa-159">If you click **Filters**, you can modify the chart with the following filters:</span></span>

  - <span data-ttu-id="84aaa-160">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-160">**Start date** and **End date**</span></span>
  - <span data-ttu-id="84aaa-161">Krypteringsmetod</span><span class="sxs-lookup"><span data-stu-id="84aaa-161">Encryption method</span></span>
  - <span data-ttu-id="84aaa-162">Krypteringsmall</span><span class="sxs-lookup"><span data-stu-id="84aaa-162">Encryption template</span></span>

- <span data-ttu-id="84aaa-163">**Visa data efter: De 5 främsta** mottagardomänerna: I den här vyn visas ett cirkeldiagram med antal skickade meddelanden för de 5 översta mottagardomänerna.</span><span class="sxs-lookup"><span data-stu-id="84aaa-163">**View data by: Top 5 recipient domains**: This view shows a pie chart with sent message counts for the top 5 recipient domains.</span></span>

  <span data-ttu-id="84aaa-164">Om du klickar **på** Filter kan du välja **startdatum** och **slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="84aaa-164">If you click **Filters**, you can select a **Start date** and **End date**.</span></span>

### <a name="details-table-view-for-the-encryption-report"></a><span data-ttu-id="84aaa-165">Detaljtabellvyn för krypteringsrapporten</span><span class="sxs-lookup"><span data-stu-id="84aaa-165">Details table view for the Encryption report</span></span>

<span data-ttu-id="84aaa-166">Om du **klickar på Visa** informationstabell beror den information som visas på det diagram som du tittar på:</span><span class="sxs-lookup"><span data-stu-id="84aaa-166">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="84aaa-167">**Dela upp dig efter: Krypteringsmetod** **eller Dela upp efter: Krypteringsmall:** Följande information visas:</span><span class="sxs-lookup"><span data-stu-id="84aaa-167">**Break down by: Encryption method** or **Break down by: Encryption template**: The following information is shown:</span></span>

  - <span data-ttu-id="84aaa-168">**Datum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-168">**Date**</span></span>
  - <span data-ttu-id="84aaa-169">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="84aaa-169">**Sender address**</span></span>
  - <span data-ttu-id="84aaa-170">**Krypteringsmall**</span><span class="sxs-lookup"><span data-stu-id="84aaa-170">**Encryption template**</span></span>
  - <span data-ttu-id="84aaa-171">**Krypteringsmetod**</span><span class="sxs-lookup"><span data-stu-id="84aaa-171">**Encryption method**</span></span>
  - <span data-ttu-id="84aaa-172">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="84aaa-172">**Recipient address**</span></span>
  - <span data-ttu-id="84aaa-173">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="84aaa-173">**Subject**</span></span>

- <span data-ttu-id="84aaa-174">**Visa data efter: De 5 främsta mottagardomänerna**:</span><span class="sxs-lookup"><span data-stu-id="84aaa-174">**View data by: Top 5 recipient domains**:</span></span>

  - <span data-ttu-id="84aaa-175">**Datum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-175">**Date**</span></span>
  - <span data-ttu-id="84aaa-176">**Mottagardomän**</span><span class="sxs-lookup"><span data-stu-id="84aaa-176">**Recipient domain**</span></span>
  - <span data-ttu-id="84aaa-177">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="84aaa-177">**Message count**</span></span>

<span data-ttu-id="84aaa-178">Om du klickar **på** Filter i en detaljtabellvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="84aaa-178">If you click **Filters** in a details table view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="84aaa-179">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-179">**Start date** and **End date**</span></span>
- <span data-ttu-id="84aaa-180">Krypteringsmetod</span><span class="sxs-lookup"><span data-stu-id="84aaa-180">Encryption method</span></span>
- <span data-ttu-id="84aaa-181">Krypteringsmall</span><span class="sxs-lookup"><span data-stu-id="84aaa-181">Encryption template</span></span>

<span data-ttu-id="84aaa-182">Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**</span><span class="sxs-lookup"><span data-stu-id="84aaa-182">To go back to the report view, click **View report**.</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="84aaa-183">Statusrapport för e-postflöde</span><span class="sxs-lookup"><span data-stu-id="84aaa-183">Mailflow status report</span></span>

<span data-ttu-id="84aaa-184">Statusrapporten **E-postflöde** innehåller information om blockerade meddelanden som skadlig kod, skräppost, nätfiske och edge.</span><span class="sxs-lookup"><span data-stu-id="84aaa-184">The **Mailflow status report** contains information about malware, spam, phishing and edge blocked messages.</span></span> <span data-ttu-id="84aaa-185">Mer information finns i [Statusrapport för e-postflöde](view-mail-flow-reports.md#mailflow-status-report).</span><span class="sxs-lookup"><span data-stu-id="84aaa-185">For more details, see [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).</span></span>

## <a name="malware-detections-in-email-report"></a><span data-ttu-id="84aaa-186">Identifieringar av skadlig programvara i en e-postrapport</span><span class="sxs-lookup"><span data-stu-id="84aaa-186">Malware detections in email report</span></span>

<span data-ttu-id="84aaa-187">I **rapporten om identifiering av skadlig programvara i** e-postmeddelanden visas information om identifiering av skadlig programvara i inkommande och utgående e-postmeddelanden (skadlig kod som Exchange Online Protection eller EOP).</span><span class="sxs-lookup"><span data-stu-id="84aaa-187">The **Malware detections in email** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="84aaa-188">Mer information om skydd mot skadlig programvara i EOP finns [i Skydd mot skadlig programvara i EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="84aaa-188">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

 <span data-ttu-id="84aaa-189">Mängdvyfiltret tillåter 90 dagar, medan filtret i detaljtabellen bara tillåter 10 dagar.</span><span class="sxs-lookup"><span data-stu-id="84aaa-189">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="84aaa-190">Om du vill visa rapporten öppnar du [Microsoft 365 Defender-portalen](https://security.microsoft.com), går till E-& rapporter för samarbete & skicka  \>  \> **e& samarbetsrapporter**  och klickar på Visa information under Skadlig programvara som upptäckts via e-post. </span><span class="sxs-lookup"><span data-stu-id="84aaa-190">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Malware detected in email**.</span></span> <span data-ttu-id="84aaa-191">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/MalwareDetections> .</span><span class="sxs-lookup"><span data-stu-id="84aaa-191">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![Widget för identifiering av skadlig programvara i e-postwidgeten i instrumentpanelen Rapporter](../../media/malware-detections-widget.png)

<span data-ttu-id="84aaa-193">Du kan filtrera både diagrammet och detaljtabellen genom att klicka **på Filter** och välja:</span><span class="sxs-lookup"><span data-stu-id="84aaa-193">You can filter both the chart and the details table by clicking **Filters** and selecting:</span></span>

- <span data-ttu-id="84aaa-194">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-194">**Start date** and **End date**</span></span>
- <span data-ttu-id="84aaa-195">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="84aaa-195">**Inbound**</span></span>
- <span data-ttu-id="84aaa-196">**Utgående**</span><span class="sxs-lookup"><span data-stu-id="84aaa-196">**Outbound**</span></span>

![Rapportvyn i rapporten om identifiering av skadlig programvara i e-post](../../media/malware-detections-report-view.png)

<span data-ttu-id="84aaa-198">Om du **klickar på Visa informationstabell** visas följande information:</span><span class="sxs-lookup"><span data-stu-id="84aaa-198">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="84aaa-199">**Datum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-199">**Date**</span></span>
- <span data-ttu-id="84aaa-200">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="84aaa-200">**Sender address**</span></span>
- <span data-ttu-id="84aaa-201">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="84aaa-201">**Recipient address**</span></span>
- <span data-ttu-id="84aaa-202">**Meddelande-ID:** Tillgängligt i **sidhuvudet för meddelande-ID** i meddelandehuvudet och ska vara unikt.</span><span class="sxs-lookup"><span data-stu-id="84aaa-202">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="84aaa-203">Ett exempelvärde är `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (observera vinkelparenteserna).</span><span class="sxs-lookup"><span data-stu-id="84aaa-203">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="84aaa-204">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="84aaa-204">**Subject**</span></span>
- <span data-ttu-id="84aaa-205">**Filnamn**</span><span class="sxs-lookup"><span data-stu-id="84aaa-205">**Filename**</span></span>
- <span data-ttu-id="84aaa-206">**Namn på skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="84aaa-206">**Malware name**</span></span>

<span data-ttu-id="84aaa-207">Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**</span><span class="sxs-lookup"><span data-stu-id="84aaa-207">To go back to the report view, click **View report**.</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="84aaa-208">E-postsvarstid – rapport</span><span class="sxs-lookup"><span data-stu-id="84aaa-208">Mail latency report</span></span>

<span data-ttu-id="84aaa-209">Svarstiden **för E-post** innehåller information om den svarstid för e-postleverans och detonation som har upplevts inom organisationen.</span><span class="sxs-lookup"><span data-stu-id="84aaa-209">The **Mail latency report** contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="84aaa-210">Mer information finns i [E-postsvarstidsrapport](view-reports-for-mdo.md#mail-latency-report).</span><span class="sxs-lookup"><span data-stu-id="84aaa-210">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="sent-and-received-email-report"></a><span data-ttu-id="84aaa-211">Rapport om skickad och mottagen e-post</span><span class="sxs-lookup"><span data-stu-id="84aaa-211">Sent and received email report</span></span>

<span data-ttu-id="84aaa-212">Rapporten **Skickad och mottagen** e-post innehåller information om skadlig programvara, skräppost, e-postflödesregler (kallas även transportregler) och avancerad identifiering av skadlig programvara efter att e-post har kommit in i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="84aaa-212">The **Sent and received email** report contains information about malware, spam, mail flow rules (also known as transport rules), and advanced malware detections after email enters the service.</span></span> <span data-ttu-id="84aaa-213">Mer information finns i Rapporten [skickad och mottagen e-post](view-mail-flow-reports.md#sent-and-received-email-report).</span><span class="sxs-lookup"><span data-stu-id="84aaa-213">For more information, see [Sent and received email report](view-mail-flow-reports.md#sent-and-received-email-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="84aaa-214">Rapport om identifiering av skräppost</span><span class="sxs-lookup"><span data-stu-id="84aaa-214">Spam detections report</span></span>

<span data-ttu-id="84aaa-215">Rapporten **Om identifiering av** skräppost visar e-postmeddelanden som har blockerats av EOP.</span><span class="sxs-lookup"><span data-stu-id="84aaa-215">The **Spam detections** report shows spam email messages that were blocked by EOP.</span></span> <span data-ttu-id="84aaa-216">Meddelanden räknas individuellt, inte per mottagare.</span><span class="sxs-lookup"><span data-stu-id="84aaa-216">Messages are counted individually, not per recipient.</span></span> <span data-ttu-id="84aaa-217">Om till exempel samma skräppostmeddelande har skickats till 100 mottagare i organisationen räknas det som ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="84aaa-217">For example, if the same spam message was sent to 100 recipients in your organization, it counts as one message.</span></span>

<span data-ttu-id="84aaa-218">I mängdvyn kan du filtrera i 90 dagar, medan detaljtabellen tillåter 10 dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="84aaa-218">The aggregate view allows for 90 days filtering, while the details table allows for 10 days filtering.</span></span>

<span data-ttu-id="84aaa-219">Om du vill visa rapporten öppnar du Microsoft 365  [Defender-portalen](https://security.microsoft.com), går till Rapporterar e-& samarbete E& och samarbetsrapporter och klickar på Visa information under Identifiering av \>  \>  **skräppost.** </span><span class="sxs-lookup"><span data-stu-id="84aaa-219">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click click **View details** under **Spam detections**.</span></span> <span data-ttu-id="84aaa-220">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/SpamDetections> .</span><span class="sxs-lookup"><span data-stu-id="84aaa-220">To go directly to the report, open <https://security.microsoft.com/reports/SpamDetections>.</span></span>

![Widget för identifiering av skräppost på instrumentpanelen Rapporter](../../media/spam-detections-report-widget.png)

<span data-ttu-id="84aaa-222">Mer information om skydd mot skräppost finns i [Skydd mot skräppost i EOP.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="84aaa-222">For more information about anti-spam protection, see [Anti-spam protection in EOP](anti-spam-protection.md).</span></span>

### <a name="report-view-for-the-spam-detections-report"></a><span data-ttu-id="84aaa-223">Rapportvy för rapporten om identifiering av skräppost</span><span class="sxs-lookup"><span data-stu-id="84aaa-223">Report view for the Spam detections report</span></span>

<span data-ttu-id="84aaa-224">Följande diagram är tillgängliga i rapportvyn:</span><span class="sxs-lookup"><span data-stu-id="84aaa-224">The following charts are available in the report view:</span></span>

- <span data-ttu-id="84aaa-225">**Dela upp efter: Åtgärd:** Följande händelsetyper visas:</span><span class="sxs-lookup"><span data-stu-id="84aaa-225">**Break down by: Action**: The following event types are shown:</span></span>

  - <span data-ttu-id="84aaa-226">**Skräppostinnehåll filtrerat**</span><span class="sxs-lookup"><span data-stu-id="84aaa-226">**Spam content filtered**</span></span>
  - <span data-ttu-id="84aaa-227">**IP-block för skräppost**</span><span class="sxs-lookup"><span data-stu-id="84aaa-227">**Spam IP block**</span></span>
  - <span data-ttu-id="84aaa-228">**Skräppostkuvertblock**</span><span class="sxs-lookup"><span data-stu-id="84aaa-228">**Spam envelope block**</span></span>
  - <span data-ttu-id="84aaa-229">**DBEB-skräppostfilter:** Katalogbaserad kantblockering (DBEB)</span><span class="sxs-lookup"><span data-stu-id="84aaa-229">**Spam DBEB filter**: Directory based edge blocking (DBEB)</span></span>

  <span data-ttu-id="84aaa-230">När du hovrar över en dag (datapunkt) i diagrammet kan du se hur många objekt som blockerades den dagen och hur de objekten kategoriserats.</span><span class="sxs-lookup"><span data-stu-id="84aaa-230">When you hover over a day (data point) in the chart, you can see how many items were blocked that day, as well as how those items are categorized.</span></span>

  ![Åtgärdsvyn i rapporten om identifiering av skräppost](../../media/spam-detections-report-action-view.png)

- <span data-ttu-id="84aaa-232">**Dela upp i: Riktning**: Följande anvisningar visas:</span><span class="sxs-lookup"><span data-stu-id="84aaa-232">**Break down by: Direction**: The following directions are shown:</span></span>

  - <span data-ttu-id="84aaa-233">**Inkommande**</span><span class="sxs-lookup"><span data-stu-id="84aaa-233">**Inbound**</span></span>
  - <span data-ttu-id="84aaa-234">**Utgående**</span><span class="sxs-lookup"><span data-stu-id="84aaa-234">**Outbound**</span></span>

  ![Vy för riktning i rapporten om identifiering av skräppost](../../media/spam-detections-report-direction-view.png)

<span data-ttu-id="84aaa-236">Om du klickar **på** Filter i en rapportvy kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="84aaa-236">If you click **Filters** in a report view, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="84aaa-237">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-237">**Start date** and **End date**</span></span>
- <span data-ttu-id="84aaa-238">Riktningsvärden</span><span class="sxs-lookup"><span data-stu-id="84aaa-238">Direction values</span></span>
- <span data-ttu-id="84aaa-239">Händelsetypsvärden</span><span class="sxs-lookup"><span data-stu-id="84aaa-239">Event type values</span></span>

### <a name="details-table-view-for-the-spam-detections-report"></a><span data-ttu-id="84aaa-240">Detaljtabellvyn för rapporten om identifiering av skräppost</span><span class="sxs-lookup"><span data-stu-id="84aaa-240">Details table view for the Spam detections report</span></span>

<span data-ttu-id="84aaa-241">Om du **klickar på Visa informationstabell** i en rapportvy visas följande information:</span><span class="sxs-lookup"><span data-stu-id="84aaa-241">If you click **View details table** in any report view, the following information is shown:</span></span>

- <span data-ttu-id="84aaa-242">**Datum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-242">**Date**</span></span>
- <span data-ttu-id="84aaa-243">**Avsändarens adress**</span><span class="sxs-lookup"><span data-stu-id="84aaa-243">**Sender address**</span></span>
- <span data-ttu-id="84aaa-244">**Mottagaradress**</span><span class="sxs-lookup"><span data-stu-id="84aaa-244">**Recipient address**</span></span>
- <span data-ttu-id="84aaa-245">**Händelsetyp**</span><span class="sxs-lookup"><span data-stu-id="84aaa-245">**Event type**</span></span>
- <span data-ttu-id="84aaa-246">**Åtgärd**</span><span class="sxs-lookup"><span data-stu-id="84aaa-246">**Action**</span></span>
- <span data-ttu-id="84aaa-247">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="84aaa-247">**Subject**</span></span>

<span data-ttu-id="84aaa-248">Om du klickar **på** Filter i en informationstabell kan du ändra resultatet med följande filter:</span><span class="sxs-lookup"><span data-stu-id="84aaa-248">If you click **Filters** in a details table, you can modify the results with the following filters:</span></span>

- <span data-ttu-id="84aaa-249">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-249">**Start date** and **End date**</span></span>
- <span data-ttu-id="84aaa-250">Riktningsvärden</span><span class="sxs-lookup"><span data-stu-id="84aaa-250">Direction values</span></span>
- <span data-ttu-id="84aaa-251">Händelsetypsvärden</span><span class="sxs-lookup"><span data-stu-id="84aaa-251">Event type values</span></span>

<span data-ttu-id="84aaa-252">Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**</span><span class="sxs-lookup"><span data-stu-id="84aaa-252">To go back to the report view, click **View report**.</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="84aaa-253">Rapport om identifieringar av förfalskning</span><span class="sxs-lookup"><span data-stu-id="84aaa-253">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="84aaa-254">Rapporten om förbättrade identifieringar av förfalskning som beskrivs i den här artikeln är en förhandsversion, kan komma att ändras och är inte tillgänglig i alla organisationer.</span><span class="sxs-lookup"><span data-stu-id="84aaa-254">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="84aaa-255">I den äldre versionen av rapporten visades endast **Bra e-post** **och Fångad som skräppost.**</span><span class="sxs-lookup"><span data-stu-id="84aaa-255">The older version of the report showed only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="84aaa-256">I **rapporten Identifieringar av förfalskning** visas information om meddelanden som har blockerats eller tillåts på grund av förfalskning.</span><span class="sxs-lookup"><span data-stu-id="84aaa-256">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="84aaa-257">Mer information om förfalskning finns i [Skydd mot förfalskning i EOP.](anti-spoofing-protection.md)</span><span class="sxs-lookup"><span data-stu-id="84aaa-257">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="84aaa-258">I den samlade vyn för rapporten kan du filtrera i 45 dagar, medan <sup>\*</sup> detaljvyn bara tillåter tio dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="84aaa-258">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="84aaa-259"><sup>\*</sup> Till slut kan du använda upp till 90 dagars filtrering.</span><span class="sxs-lookup"><span data-stu-id="84aaa-259"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="84aaa-260">Om du vill visa rapporten öppnar du Microsoft 365  [Defender-portalen](https://security.microsoft.com), går till E-& rapporter för samarbete E& & och samarbetsrapporter och klickar på Visa information \>  \>  under **förfalskning.** </span><span class="sxs-lookup"><span data-stu-id="84aaa-260">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Spoof detections**.</span></span> <span data-ttu-id="84aaa-261">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/SpoofMailReport> .</span><span class="sxs-lookup"><span data-stu-id="84aaa-261">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReport>.</span></span>

![Widget för identifiering av förfalskning på instrumentpanelen Rapporter](../../media/spoof-detections-widget.png)

<span data-ttu-id="84aaa-263">När du hovrar över en dag (datapunkt) i diagrammet kan du se hur många falska meddelanden som påträffades och varför.</span><span class="sxs-lookup"><span data-stu-id="84aaa-263">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="84aaa-264">Du kan filtrera både diagrammet och informationstabellen genom att klicka **på Filter** och välja ett eller flera av följande värden:</span><span class="sxs-lookup"><span data-stu-id="84aaa-264">You can filter both the chart and the details table by clicking **Filters** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="84aaa-265">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-265">**Start date** and **End date**</span></span>

- <span data-ttu-id="84aaa-266">**Result**</span><span class="sxs-lookup"><span data-stu-id="84aaa-266">**Result**</span></span>
  - <span data-ttu-id="84aaa-267">**Godkänd**</span><span class="sxs-lookup"><span data-stu-id="84aaa-267">**Pass**</span></span>
  - <span data-ttu-id="84aaa-268">**Fel**</span><span class="sxs-lookup"><span data-stu-id="84aaa-268">**Fail**</span></span>
  - <span data-ttu-id="84aaa-269">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="84aaa-269">**SoftPass**</span></span>
  - <span data-ttu-id="84aaa-270">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="84aaa-270">**None**</span></span>
  - <span data-ttu-id="84aaa-271">**Annat**</span><span class="sxs-lookup"><span data-stu-id="84aaa-271">**Other**</span></span>

- <span data-ttu-id="84aaa-272">**Förfalskningstyp:** **Intern** och **Extern**</span><span class="sxs-lookup"><span data-stu-id="84aaa-272">**Spoof type**: **Internal** and **External**</span></span>

![Rapportvyn i rapporten Identifiering av förfalskning](../../media/spoof-detections-report-view.png)

<span data-ttu-id="84aaa-274">Om du **klickar på Visa informationstabell** visas följande information:</span><span class="sxs-lookup"><span data-stu-id="84aaa-274">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="84aaa-275">**Datum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-275">**Date**</span></span>
- <span data-ttu-id="84aaa-276">**Spoofed användare**</span><span class="sxs-lookup"><span data-stu-id="84aaa-276">**Spoofed user**</span></span>
- <span data-ttu-id="84aaa-277">**Skicka infrastruktur**</span><span class="sxs-lookup"><span data-stu-id="84aaa-277">**Sending infrastructure**</span></span>
- <span data-ttu-id="84aaa-278">**Förfalskningstyp**</span><span class="sxs-lookup"><span data-stu-id="84aaa-278">**Spoof type**</span></span>
- <span data-ttu-id="84aaa-279">**Result**</span><span class="sxs-lookup"><span data-stu-id="84aaa-279">**Result**</span></span>
- <span data-ttu-id="84aaa-280">**Resultatkod**</span><span class="sxs-lookup"><span data-stu-id="84aaa-280">**Result code**</span></span>
- <span data-ttu-id="84aaa-281">**SPF**</span><span class="sxs-lookup"><span data-stu-id="84aaa-281">**SPF**</span></span>
- <span data-ttu-id="84aaa-282">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="84aaa-282">**DKIM**</span></span>
- <span data-ttu-id="84aaa-283">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="84aaa-283">**DMARC**</span></span>
- <span data-ttu-id="84aaa-284">**Antal meddelanden**</span><span class="sxs-lookup"><span data-stu-id="84aaa-284">**Message count**</span></span>

<span data-ttu-id="84aaa-285">Om du vill gå tillbaka till rapportvyn klickar du **på Visa rapport.**</span><span class="sxs-lookup"><span data-stu-id="84aaa-285">To go back to the report view, click **View report**.</span></span>

<span data-ttu-id="84aaa-286">Mer information om sammansatta resultatkoder för autentisering finns i Rubriker mot skräppost [i Microsoft 365.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="84aaa-286">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="84aaa-287">Statusrapport för hotskydd</span><span class="sxs-lookup"><span data-stu-id="84aaa-287">Threat protection status report</span></span>

<span data-ttu-id="84aaa-288">Statusrapporten **för skydd** mot hot är tillgänglig i både EOP och Microsoft Defender för Office 365. Rapporterna innehåller däremot olika data.</span><span class="sxs-lookup"><span data-stu-id="84aaa-288">The **Threat protection status** report is available in both EOP and Microsoft Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="84aaa-289">Till exempel kan EOP-kunder visa information om skadlig programvara som upptäckts i e-post, men inte information om skadliga filer som upptäckts av [Valv-bifogade](mdo-for-spo-odb-and-teams.md)filer för SharePoint, OneDrive och Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="84aaa-289">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="84aaa-290">Rapporten innehåller antalet e-postmeddelanden med skadligt innehåll, till exempel filer eller webbadresser (URL:er) som har blockerats av skadlig programvara, ZAP [(Zero-hour Auto Purge)](zero-hour-auto-purge.md)och Defender för Office 365-funktioner som [Valv-länkar,](safe-links.md) [Valv-bilagor](safe-attachments.md)och [nätfiske](set-up-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="84aaa-290">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [Anti-phishing](set-up-anti-phishing-policies.md).</span></span> <span data-ttu-id="84aaa-291">Du kan använda den här informationen för att identifiera trender eller avgöra om organisationens principer behöver justeras.</span><span class="sxs-lookup"><span data-stu-id="84aaa-291">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="84aaa-292">**Obs!** Det är viktigt att förstå att om ett meddelande skickas till fem mottagare räknas det som fem olika meddelanden och inte ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="84aaa-292">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="84aaa-293">Om du vill visa rapporten öppnar du Microsoft 365  [Defender-portalen](https://security.microsoft.com), går till Rapporterar e-& samarbete E& och klickar på Visa information under Status för skydd mot \>  \>  **hot.** </span><span class="sxs-lookup"><span data-stu-id="84aaa-293">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Threat protection status**.</span></span> <span data-ttu-id="84aaa-294">Öppna någon av följande URL:er för att gå direkt till rapporten:</span><span class="sxs-lookup"><span data-stu-id="84aaa-294">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="84aaa-295">Microsoft Defender för Office 365:<https://protection.office.com/reportv2?id=TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="84aaa-295">Microsoft Defender for Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP></span></span>
- <span data-ttu-id="84aaa-296">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="84aaa-296">EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport></span></span>

![Widget för hotskyddsstatus på instrumentpanelen Rapporter](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="84aaa-298">Som standard visas data för de senaste 7 dagarna i diagrammet.</span><span class="sxs-lookup"><span data-stu-id="84aaa-298">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="84aaa-299">Om du klickar **på Filter** kan du välja ett datumintervall på 90 dagar (utvärderingsprenumerationer kan vara begränsat till 30 dagar).</span><span class="sxs-lookup"><span data-stu-id="84aaa-299">If you click **Filters**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="84aaa-300">I detaljtabellvyn kan du filtrera i 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="84aaa-300">The details table view allows filtering for 30 days.</span></span>

### <a name="report-view-for-the-threat-protection-status-report"></a><span data-ttu-id="84aaa-301">Rapportvy för statusrapporten för skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="84aaa-301">Report view for the Threat protection status report</span></span>

<span data-ttu-id="84aaa-302">Följande vyer är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="84aaa-302">The following views are available:</span></span>

- <span data-ttu-id="84aaa-303">**Visa data efter: Översikt:** Följande identifieringsinformation visas:</span><span class="sxs-lookup"><span data-stu-id="84aaa-303">**View data by: Overview**: The following detection information is shown:</span></span>

  - <span data-ttu-id="84aaa-304">**Skadlig programvara för e-post**</span><span class="sxs-lookup"><span data-stu-id="84aaa-304">**Email malware**</span></span>
  - <span data-ttu-id="84aaa-305">**E-post phish**</span><span class="sxs-lookup"><span data-stu-id="84aaa-305">**Email phish**</span></span>
  - <span data-ttu-id="84aaa-306">**Skadlig programvara för innehåll**</span><span class="sxs-lookup"><span data-stu-id="84aaa-306">**Content malware**</span></span>

  ![Översiktsvy i rapporten om skydd mot hot](../../media/threat-protection-status-report-overview-view.png)

- <span data-ttu-id="84aaa-308">**Visa data efter: Innehåll \> Skadlig**<sup>programvara 1:</sup>Följande information visas för Microsoft Defender för Office 365 organisationer:</span><span class="sxs-lookup"><span data-stu-id="84aaa-308">**View data by: Content \> Malware**<sup>1</sup>: The following information is shown for Microsoft Defender for Office 365 organizations:</span></span>

  - <span data-ttu-id="84aaa-309">**Motor mot skadlig programvara:** Skadliga filer som upptäckts i Sharepoint, OneDrive och Microsoft Teams av den [inbyggda virusidentifieringen i Microsoft 365.](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="84aaa-309">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
  - <span data-ttu-id="84aaa-310">**Fildeonation:** Skadliga filer som upptäckts [Valv bifogade filer för SharePoint, OneDrive och Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="84aaa-310">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

  ![Vyn För skadlig programvara för innehåll i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-content-malware-view.png)

- <span data-ttu-id="84aaa-312">**Visa data efter: Åsidosättning av** meddelande: Följande orsak till åsidosättning visas:</span><span class="sxs-lookup"><span data-stu-id="84aaa-312">**View data by: Message Override**: The following override reason information is shown:</span></span>

  - <span data-ttu-id="84aaa-313">**Lokal hoppa över**</span><span class="sxs-lookup"><span data-stu-id="84aaa-313">**On-premises skip**</span></span>
  - <span data-ttu-id="84aaa-314">**IP Allow**</span><span class="sxs-lookup"><span data-stu-id="84aaa-314">**IP Allow**</span></span>
  - <span data-ttu-id="84aaa-315">**E-postflödesregel**</span><span class="sxs-lookup"><span data-stu-id="84aaa-315">**Mail flow rule**</span></span>
  - <span data-ttu-id="84aaa-316">**Sender allow**</span><span class="sxs-lookup"><span data-stu-id="84aaa-316">**Sender allow**</span></span>
  - <span data-ttu-id="84aaa-317">**Tillåt domän**</span><span class="sxs-lookup"><span data-stu-id="84aaa-317">**Domain allow**</span></span>
  - <span data-ttu-id="84aaa-318">**ZAP inte aktiverat**</span><span class="sxs-lookup"><span data-stu-id="84aaa-318">**ZAP not enabled**</span></span>
  - <span data-ttu-id="84aaa-319">**Mappen Skräppost är inte aktiverad**</span><span class="sxs-lookup"><span data-stu-id="84aaa-319">**Junk Mail folder not enabled**</span></span>
  - <span data-ttu-id="84aaa-320">**Användare Valv avsändare**</span><span class="sxs-lookup"><span data-stu-id="84aaa-320">**User Safe Sender**</span></span>
  - <span data-ttu-id="84aaa-321">**User Valv Domain**</span><span class="sxs-lookup"><span data-stu-id="84aaa-321">**User Safe Domain**</span></span>

  ![Vy för åsidosättning av meddelande i rapporten om skydd mot hot](../../media/threat-protection-status-report-message-override-view.png)

- <span data-ttu-id="84aaa-323">**Dela upp dig med: Identifieringsteknik** **och Visa data efter: E-postfras \>**: Följande information visas:</span><span class="sxs-lookup"><span data-stu-id="84aaa-323">**Break down by: Detection technology** and **View data by: Email \> Phish**: The following information is shown:</span></span>

  - <span data-ttu-id="84aaa-324">**ATP-genererat URL-rykte**<sup>1</sup>: Skadligt URL-rykte genererat av Defender för Office 365 detonationer i andra Microsoft 365 kunder.</span><span class="sxs-lookup"><span data-stu-id="84aaa-324">**ATP-generated URL reputation**<sup>1</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
  - <span data-ttu-id="84aaa-325">**Avancerat nätfiskefilter:** Nätfiskesignaler baserade på maskininlärning.</span><span class="sxs-lookup"><span data-stu-id="84aaa-325">**Advanced phish filter**: Phishing signals based on machine learning.</span></span>
  - <span data-ttu-id="84aaa-326">**Anti-spoof – DMARC-fel:** DMARC-autentiseringsfel i meddelanden.</span><span class="sxs-lookup"><span data-stu-id="84aaa-326">**Anti-spoof - DMARC failure**: DMARC authentication failure on messages.</span></span>
  - <span data-ttu-id="84aaa-327">**Anti-förfalskning – årsorganisation:** Avsändaren försöker kapa mottagardomänen.</span><span class="sxs-lookup"><span data-stu-id="84aaa-327">**Anti-spoof - intra-org**: Sender is trying to spoof the recipient domain.</span></span>
  - <span data-ttu-id="84aaa-328">**Skydd mot förfalskning – extern domän:** Avsändaren försöker kapa en annan domän.</span><span class="sxs-lookup"><span data-stu-id="84aaa-328">**Anti-spoof - external domain**: Sender is trying to spoof some other domain.</span></span>
  - <span data-ttu-id="84aaa-329">**Personifiering av märke**: Personifiering av välkända varumärken baserat på avsändare.</span><span class="sxs-lookup"><span data-stu-id="84aaa-329">**Brand impersonation**: Impersonation of well-known brands based on senders.</span></span>
  - <span data-ttu-id="84aaa-330">**Domänpersonifiering**<sup>1</sup>: Personifiering av domäner som kunden äger eller definierar.</span><span class="sxs-lookup"><span data-stu-id="84aaa-330">**Domain impersonation**<sup>1</sup>: Impersonation of domains that the customer owns or defines.</span></span>
  - <span data-ttu-id="84aaa-331">**Ryktet EOP URL**: Skadligt URL-rykte.</span><span class="sxs-lookup"><span data-stu-id="84aaa-331">**EOP URL reputation**: Malicious URL reputation.</span></span>
  - <span data-ttu-id="84aaa-332">**Allmänt nätfiskefilter:** Nätfiskesignaler baserade på analytiker.</span><span class="sxs-lookup"><span data-stu-id="84aaa-332">**General phish filter**: Phishing signals based on analyst rules.</span></span>
  - <span data-ttu-id="84aaa-333">**Andra**</span><span class="sxs-lookup"><span data-stu-id="84aaa-333">**Others**</span></span>
  - <span data-ttu-id="84aaa-334">**Phish ZAP**<sup>2</sup>: Automatisk rensning av nätfiskemeddelanden i noll timme.</span><span class="sxs-lookup"><span data-stu-id="84aaa-334">**Phish ZAP**<sup>2</sup>: Zero hour auto purge of phishing messages.</span></span>
  - <span data-ttu-id="84aaa-335">**URL-detonation**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="84aaa-335">**URL detonation**<sup>1</sup></span></span>
  - <span data-ttu-id="84aaa-336">**Användarpersonifiering**<sup>1</sup>: Personifiering av användare som definierats av administratör eller som har lärt sig postlådeintelligens.</span><span class="sxs-lookup"><span data-stu-id="84aaa-336">**User impersonation**<sup>1</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>

  ![Vy för identifieringsteknik för nätfiske i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- <span data-ttu-id="84aaa-338">**Dela upp dig med: Identifieringsteknik** **och Visa data efter: Skadlig e-post: \>** Följande information visas:</span><span class="sxs-lookup"><span data-stu-id="84aaa-338">**Break down by: Detection technology** and **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="84aaa-339">**ATP-genererat rykte**<sup>1</sup>: Alla ryktet för skadlig fil som genererats av Defender Office 365 detonationer.</span><span class="sxs-lookup"><span data-stu-id="84aaa-339">**ATP-generated file reputation**<sup>1</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
  - <span data-ttu-id="84aaa-340">**Motor mot skadlig programvara**<sup>1:</sup>Identifiering från sökmotorer mot skadlig programvara.</span><span class="sxs-lookup"><span data-stu-id="84aaa-340">**Anti-malware engine**<sup>1</sup>: Detection from anti-malware engines.</span></span>
  - <span data-ttu-id="84aaa-341">**Filtypsblockering mot skadlig programvara:** Det här är e-postmeddelanden som filtrerats bort på grund av vilken typ av skadlig fil som identifieras i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="84aaa-341">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
  - <span data-ttu-id="84aaa-342">**Fildeonation**<sup>1</sup>: Identifiering av e Valv bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="84aaa-342">**File detonation**<sup>1</sup>: Detection by Safe Attachments.</span></span>
  - <span data-ttu-id="84aaa-343">**Skadligt filrynde**</span><span class="sxs-lookup"><span data-stu-id="84aaa-343">**Malicious file reputation**</span></span>
  - <span data-ttu-id="84aaa-344">**Malware ZAP**<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="84aaa-344">**Malware ZAP**<sup>2</sup></span></span>
  - <span data-ttu-id="84aaa-345">**Andra**</span><span class="sxs-lookup"><span data-stu-id="84aaa-345">**Others**</span></span>

  ![Vy för identifieringsteknik för skadlig programvara i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- <span data-ttu-id="84aaa-347">**Dela upp efter: Principtyp och** Visa data efter: E-postfras eller Visa data efter: Skadlig e-post: Följande information visas: **\>** **\>**</span><span class="sxs-lookup"><span data-stu-id="84aaa-347">**Break down by: Policy type** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="84aaa-348">**Skydd mot skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="84aaa-348">**Anti-malware**</span></span>
  - <span data-ttu-id="84aaa-349">**Valv 1**<sup></sup></span><span class="sxs-lookup"><span data-stu-id="84aaa-349">**Safe Attachments**<sup>1</sup></span></span>
  - <span data-ttu-id="84aaa-350">**Anti-phish**</span><span class="sxs-lookup"><span data-stu-id="84aaa-350">**Anti-phish**</span></span>
  - <span data-ttu-id="84aaa-351">**Skräppostskydd**</span><span class="sxs-lookup"><span data-stu-id="84aaa-351">**Anti-spam**</span></span>
  - <span data-ttu-id="84aaa-352">**E-postflödesregel** (kallas även transportregel)</span><span class="sxs-lookup"><span data-stu-id="84aaa-352">**Mail flow rule** (also known as a transport rule)</span></span>
  - <span data-ttu-id="84aaa-353">**Andra**</span><span class="sxs-lookup"><span data-stu-id="84aaa-353">**Others**</span></span>

  ![Vy av principtyp för nätfiske i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- <span data-ttu-id="84aaa-355">**Dela upp efter: Leveransstatus** och **Visa data efter: E-postfras \>** eller Visa data efter: Skadlig e-post: Följande information visas: **\>**</span><span class="sxs-lookup"><span data-stu-id="84aaa-355">**Break down by: Delivery status** and **View data by: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:</span></span>

  - <span data-ttu-id="84aaa-356">**Leveransen misslyckades**</span><span class="sxs-lookup"><span data-stu-id="84aaa-356">**Delivery failed**</span></span>
  - <span data-ttu-id="84aaa-357">**Nedsnad**</span><span class="sxs-lookup"><span data-stu-id="84aaa-357">**Dropped**</span></span>
  - <span data-ttu-id="84aaa-358">**Vidarebefordrad**</span><span class="sxs-lookup"><span data-stu-id="84aaa-358">**Forwarded**</span></span>
  - <span data-ttu-id="84aaa-359">**Värdpostlåda: Anpassad mapp**</span><span class="sxs-lookup"><span data-stu-id="84aaa-359">**Hosted mailbox: Custom folder**</span></span>
  - <span data-ttu-id="84aaa-360">**Värdpostlåda: Borttagna objekt**</span><span class="sxs-lookup"><span data-stu-id="84aaa-360">**Hosted mailbox: Deleted items**</span></span>
  - <span data-ttu-id="84aaa-361">**Värdpostlåda: Inkorgen**</span><span class="sxs-lookup"><span data-stu-id="84aaa-361">**Hosted mailbox: Inbox**</span></span>
  - <span data-ttu-id="84aaa-362">**Värdpostlåda: Skräppost**</span><span class="sxs-lookup"><span data-stu-id="84aaa-362">**Hosted mailbox: Junk**</span></span>
  - <span data-ttu-id="84aaa-363">**Lokal server: Levererad**</span><span class="sxs-lookup"><span data-stu-id="84aaa-363">**On-premises server: Delivered**</span></span>
  - <span data-ttu-id="84aaa-364">**Karantän**</span><span class="sxs-lookup"><span data-stu-id="84aaa-364">**Quarantine**</span></span>

  ![Vyn Leveransstatus för nätfiskemeddelande i statusrapporten för skydd mot hot](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="84aaa-366"><sup>1</sup> Defender för Office 365 endast</span><span class="sxs-lookup"><span data-stu-id="84aaa-366"><sup>1</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="84aaa-367"><sup>ZAP</sup> (Zero-hour auto purge) är inte tillgängligt i fristående EOP (det fungerar bara i Exchange Online postlådor).</span><span class="sxs-lookup"><span data-stu-id="84aaa-367"><sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).</span></span>

<span data-ttu-id="84aaa-368">Om du klickar **på** Filter beror de tillgängliga filtren på det diagram du tittar på:</span><span class="sxs-lookup"><span data-stu-id="84aaa-368">If you click **Filters**, the filters available depends on the chart you were looking at:</span></span>

- <span data-ttu-id="84aaa-369">För **Visa data efter: Skadlig \>** programvara för  innehåll kan du ändra rapporten efter startdatum **och** slutdatum samt värdet **för Identifiering.**</span><span class="sxs-lookup"><span data-stu-id="84aaa-369">For **View data by: Content \> Malware**, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="84aaa-370">För **Visa data efter: Åsidosättning av** meddelande , kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="84aaa-370">For **View data by: Message Override**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="84aaa-371">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-371">**Start date** and **End date**</span></span>
  - <span data-ttu-id="84aaa-372">**Åsidosätt orsak**</span><span class="sxs-lookup"><span data-stu-id="84aaa-372">**Override Reason**</span></span>
  - <span data-ttu-id="84aaa-373">**Tagg:** Filtrera resultatet efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton).</span><span class="sxs-lookup"><span data-stu-id="84aaa-373">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="84aaa-374">Mer information om användartaggar finns i [Användartaggar.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="84aaa-374">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="84aaa-375">**Domän**</span><span class="sxs-lookup"><span data-stu-id="84aaa-375">**Domain**</span></span>

- <span data-ttu-id="84aaa-376">För alla andra vyer kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="84aaa-376">For all other views, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="84aaa-377">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-377">**Start date** and **End date**</span></span>
  - <span data-ttu-id="84aaa-378">**Identifiering**</span><span class="sxs-lookup"><span data-stu-id="84aaa-378">**Detection**</span></span>
  - <span data-ttu-id="84aaa-379">**Skyddad av**: **ATP** eller **EOP**</span><span class="sxs-lookup"><span data-stu-id="84aaa-379">**Protected by**: **ATP** or **EOP**</span></span>
  - <span data-ttu-id="84aaa-380">**Tagg:** Filtrera resultatet efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton).</span><span class="sxs-lookup"><span data-stu-id="84aaa-380">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="84aaa-381">Mer information om användartaggar finns i [Användartaggar.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="84aaa-381">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="84aaa-382">**Domän**</span><span class="sxs-lookup"><span data-stu-id="84aaa-382">**Domain**</span></span>

### <a name="details-table-view-for-the-threat-protection-status-report"></a><span data-ttu-id="84aaa-383">Detaljtabellvy för rapporten om skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="84aaa-383">Details table view for the Threat protection status report</span></span>

<span data-ttu-id="84aaa-384">Om du **klickar på Visa** informationstabell beror den information som visas på det diagram som du tittar på:</span><span class="sxs-lookup"><span data-stu-id="84aaa-384">If you click **View details table**, the information that's shown depends on the chart you were looking at:</span></span>

- <span data-ttu-id="84aaa-385">**Visa data efter: Översikt:** **Tabellknappen Ingen tabellvyinformation** är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="84aaa-385">**View data by: Overview**: No **View details table** button is available.</span></span>

- <span data-ttu-id="84aaa-386">**Visa data efter: Innehåll \> Skadlig programvara:**</span><span class="sxs-lookup"><span data-stu-id="84aaa-386">**View data by: Content \> Malware**:</span></span>

  - <span data-ttu-id="84aaa-387">**Datum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-387">**Date**</span></span>
  - <span data-ttu-id="84aaa-388">**Plats**</span><span class="sxs-lookup"><span data-stu-id="84aaa-388">**Location**</span></span>
  - <span data-ttu-id="84aaa-389">**Riktad av**</span><span class="sxs-lookup"><span data-stu-id="84aaa-389">**Directed by**</span></span>
  - <span data-ttu-id="84aaa-390">**Namn på skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="84aaa-390">**Malware name**</span></span>

  <span data-ttu-id="84aaa-391">Om du klickar **på** Filter i den här vyn kan du ändra rapporten **efter Startdatum** **och Slutdatum** och värdet **Identifiering.**</span><span class="sxs-lookup"><span data-stu-id="84aaa-391">If you click **Filters** in this view, you can modify the report by **Start date** and **End date**, and the **Detection** value.</span></span>

- <span data-ttu-id="84aaa-392">**Visa data efter: Åsidosättning av meddelande:**</span><span class="sxs-lookup"><span data-stu-id="84aaa-392">**View data by: Message Override**:</span></span>

  - <span data-ttu-id="84aaa-393">**Datum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-393">**Date**</span></span>
  - <span data-ttu-id="84aaa-394">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="84aaa-394">**Subject**</span></span>
  - <span data-ttu-id="84aaa-395">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="84aaa-395">**Sender**</span></span>
  - <span data-ttu-id="84aaa-396">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="84aaa-396">**Recipients**</span></span>
  - <span data-ttu-id="84aaa-397">**Upptäckt av**</span><span class="sxs-lookup"><span data-stu-id="84aaa-397">**Detected by**</span></span>
  - <span data-ttu-id="84aaa-398">**Åsidosätt orsak**</span><span class="sxs-lookup"><span data-stu-id="84aaa-398">**Override Reason**</span></span>
  - <span data-ttu-id="84aaa-399">**Källan till en kompromett**</span><span class="sxs-lookup"><span data-stu-id="84aaa-399">**Source of Compromise**</span></span>
  - <span data-ttu-id="84aaa-400">**Taggar**</span><span class="sxs-lookup"><span data-stu-id="84aaa-400">**Tags**</span></span>

  <span data-ttu-id="84aaa-401">Om du **klickar på** Filter i den här vyn kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="84aaa-401">If you click **Filters** in this view, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="84aaa-402">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-402">**Start date** and **End date**</span></span>
  - <span data-ttu-id="84aaa-403">**Åsidosätt orsak**</span><span class="sxs-lookup"><span data-stu-id="84aaa-403">**Override Reason**</span></span>
  - <span data-ttu-id="84aaa-404">**Tagg:** Filtrera resultatet efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton).</span><span class="sxs-lookup"><span data-stu-id="84aaa-404">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="84aaa-405">Mer information om användartaggar finns i [Användartaggar.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="84aaa-405">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="84aaa-406">**Domän**</span><span class="sxs-lookup"><span data-stu-id="84aaa-406">**Domain**</span></span>
  - <span data-ttu-id="84aaa-407">**Mottagare** (observera att den här filtrerbara egenskapen endast är tillgänglig i detaljtabellvyn)</span><span class="sxs-lookup"><span data-stu-id="84aaa-407">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

- <span data-ttu-id="84aaa-408">Alla andra diagram:</span><span class="sxs-lookup"><span data-stu-id="84aaa-408">All other charts:</span></span>

  - <span data-ttu-id="84aaa-409">**Datum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-409">**Date**</span></span>
  - <span data-ttu-id="84aaa-410">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="84aaa-410">**Subject**</span></span>
  - <span data-ttu-id="84aaa-411">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="84aaa-411">**Sender**</span></span>
  - <span data-ttu-id="84aaa-412">**Mottagare**</span><span class="sxs-lookup"><span data-stu-id="84aaa-412">**Recipients**</span></span>
  - <span data-ttu-id="84aaa-413">**Upptäckt av**</span><span class="sxs-lookup"><span data-stu-id="84aaa-413">**Detected by**</span></span>
  - <span data-ttu-id="84aaa-414">**Leveransstatus**</span><span class="sxs-lookup"><span data-stu-id="84aaa-414">**Delivery Status**</span></span>
  - <span data-ttu-id="84aaa-415">**Källan till en kompromett**</span><span class="sxs-lookup"><span data-stu-id="84aaa-415">**Source of Compromise**</span></span>
  - <span data-ttu-id="84aaa-416">**Taggar**</span><span class="sxs-lookup"><span data-stu-id="84aaa-416">**Tags**</span></span>

  <span data-ttu-id="84aaa-417">Om du **klickar på** Filter kan du ändra rapporten med följande filter:</span><span class="sxs-lookup"><span data-stu-id="84aaa-417">If you click **Filters**, you can modify the report with the following filters:</span></span>

  - <span data-ttu-id="84aaa-418">**Startdatum och** **slutdatum**</span><span class="sxs-lookup"><span data-stu-id="84aaa-418">**Start date** and **End date**</span></span>
  - <span data-ttu-id="84aaa-419">**Identifiering**</span><span class="sxs-lookup"><span data-stu-id="84aaa-419">**Detection**</span></span>
  - <span data-ttu-id="84aaa-420">**Skyddad av**: **Defender för Office 365** eller **EOP**</span><span class="sxs-lookup"><span data-stu-id="84aaa-420">**Protected by**: **Defender for Office 365** or **EOP**</span></span>
  - <span data-ttu-id="84aaa-421">**Tagg:** Filtrera resultatet efter användare eller grupper som har tillämpat den angivna användartaggen (inklusive prioritetskonton).</span><span class="sxs-lookup"><span data-stu-id="84aaa-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="84aaa-422">Mer information om användartaggar finns i [Användartaggar.](user-tags.md)</span><span class="sxs-lookup"><span data-stu-id="84aaa-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
  - <span data-ttu-id="84aaa-423">**Domän**</span><span class="sxs-lookup"><span data-stu-id="84aaa-423">**Domain**</span></span>
  - <span data-ttu-id="84aaa-424">**Mottagare** (observera att den här filtrerbara egenskapen endast är tillgänglig i detaljtabellvyn)</span><span class="sxs-lookup"><span data-stu-id="84aaa-424">**Recipients** (Note that this filterable property is only available in the details table view)</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="84aaa-425">Den viktigaste rapporten om skadlig programvara</span><span class="sxs-lookup"><span data-stu-id="84aaa-425">Top malware report</span></span>

<span data-ttu-id="84aaa-426">Den **viktigaste rapporten om** skadlig programvara visar de olika typer av skadlig programvara som identifierats av skydd mot skadlig programvara i [EOP.](anti-malware-protection.md)</span><span class="sxs-lookup"><span data-stu-id="84aaa-426">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="84aaa-427">Om du vill visa rapporten öppnar du [Microsoft 365 Defender-portalen](https://security.microsoft.com), går till Rapporterar e-& samarbete  \> **E&** och klickar på Visa information under Mest \>  skadlig  **programvara.**</span><span class="sxs-lookup"><span data-stu-id="84aaa-427">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** and click **View details** under **Top malware**.</span></span> <span data-ttu-id="84aaa-428">Gå direkt till rapporten genom att öppna <https://security.microsoft.com/reports/TopMalware> .</span><span class="sxs-lookup"><span data-stu-id="84aaa-428">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![Populära widget för skadlig programvara på instrumentpanelen Rapporter](../../media/top-malware-report-widget.png)

<span data-ttu-id="84aaa-430">När du hovrar över en kil i cirkeldiagrammet kan du se namnet på en typ av skadlig programvara och hur många meddelanden som identifierats som har den skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="84aaa-430">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

![Den övre vyn för skadlig programvara](../../media/top-malware-report-view.png)

<span data-ttu-id="84aaa-432">Om du **klickar på Visa informationstabell** visas följande information:</span><span class="sxs-lookup"><span data-stu-id="84aaa-432">If you click **View details table**, you can see the following details:</span></span>

- <span data-ttu-id="84aaa-433">**Populära skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="84aaa-433">**Top malware**</span></span>
- <span data-ttu-id="84aaa-434">**Antal**</span><span class="sxs-lookup"><span data-stu-id="84aaa-434">**Count**</span></span>

<span data-ttu-id="84aaa-435">Om du klickar **på** Filter i rapportvyn eller i detaljtabellvyn kan du ange ett datumintervall **med Startdatum** **och Slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="84aaa-435">If you click **Filters** in the report view or details table view, you can specify a date range with **Start date** and **End date**.</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="84aaa-436">Rapport om skydd mot URL-hot</span><span class="sxs-lookup"><span data-stu-id="84aaa-436">URL threat protection report</span></span>

<span data-ttu-id="84aaa-437">Rapporten **om skydd mot URL-hot** är tillgänglig i Microsoft Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="84aaa-437">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="84aaa-438">Mer information finns i Rapporten [om url-skydd mot hot.](view-reports-for-mdo.md#url-threat-protection-report)</span><span class="sxs-lookup"><span data-stu-id="84aaa-438">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="84aaa-439">Rapport över användarrapporterade meddelanden</span><span class="sxs-lookup"><span data-stu-id="84aaa-439">User reported messages report</span></span>

<span data-ttu-id="84aaa-440">Rapporten **Om användarrapporter** visar information om e-postmeddelanden som användare har rapporterat som skräppost, nätfiskeförsök eller bra [e-post](enable-the-report-message-add-in.md) med hjälp av tilläggen Rapportmeddelande eller [Rapport nätfiske.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="84aaa-440">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or [The Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="84aaa-441">Information är tillgänglig för varje meddelande, inklusive leveransorsaken, ett sådant undantag från skräppostprincipen eller en e-postflödesregel som konfigurerats för din organisation.</span><span class="sxs-lookup"><span data-stu-id="84aaa-441">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization.</span></span> <span data-ttu-id="84aaa-442">Om du vill visa information markerar du ett objekt i listan med användarrapporter och visar informationen på **flikarna Sammanfattning** **och** Information.</span><span class="sxs-lookup"><span data-stu-id="84aaa-442">To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span>

![Rapporten Över rapporterade meddelanden visar meddelanden som användare märkt som skräppost, inte skräppost eller nätfiskeförsök.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

<span data-ttu-id="84aaa-444">Du visar rapporten genom att gå [till Microsoft 365 Defender-portalen](https://security.microsoft.com)på & e-post och samarbete  \> **e&** \> **och samarbetsrapporter Användaren** har rapporterat \> **meddelanden.**</span><span class="sxs-lookup"><span data-stu-id="84aaa-444">To view this report, in the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \>**Email & collaboration reports** \> **User reported messages**.</span></span>

- <span data-ttu-id="84aaa-445">Gå  till Rapporterar \> **e-& för samarbete** \> **E& och samarbetsrapporter** \> **Användarrapporterade meddelanden.**</span><span class="sxs-lookup"><span data-stu-id="84aaa-445">Go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports** \> **User reported messages**.</span></span>

![I Den Microsoft 365 Defender-portalen väljer du Rapporterar \> e-& samarbete \> E& om \> samarbetsrapporter, användarrapporter](../../media/user-reported-messages.png)

> [!IMPORTANT]
> <span data-ttu-id="84aaa-447">För att rapporten över användarrapporter ska fungera korrekt måste granskningsloggning vara **aktiverad** i din Office 365 miljö.</span><span class="sxs-lookup"><span data-stu-id="84aaa-447">In order for the User reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment.</span></span> <span data-ttu-id="84aaa-448">Det görs vanligtvis av någon som har rollen Granskningsloggar tilldelad i Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="84aaa-448">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="84aaa-449">Mer information finns i aktivera [Microsoft 365 eller inaktivera granskningsloggsökning.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="84aaa-449">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="84aaa-450">Vilka behörigheter krävs för att visa rapporterna?</span><span class="sxs-lookup"><span data-stu-id="84aaa-450">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="84aaa-451">För att kunna visa och använda rapporterna som beskrivs i den här artikeln måste du vara medlem i någon av följande rollgrupper i Microsoft 365 Defender-portalen:</span><span class="sxs-lookup"><span data-stu-id="84aaa-451">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="84aaa-452">**Organisationshantering**</span><span class="sxs-lookup"><span data-stu-id="84aaa-452">**Organization Management**</span></span>
- <span data-ttu-id="84aaa-453">**Säkerhetsadministratör**</span><span class="sxs-lookup"><span data-stu-id="84aaa-453">**Security Administrator**</span></span>
- <span data-ttu-id="84aaa-454">**Säkerhetsläsare**</span><span class="sxs-lookup"><span data-stu-id="84aaa-454">**Security Reader**</span></span>
- <span data-ttu-id="84aaa-455">**Global Reader**</span><span class="sxs-lookup"><span data-stu-id="84aaa-455">**Global Reader**</span></span>

<span data-ttu-id="84aaa-456">Mer information finns i [Behörigheter i Microsoft 365 Defender-portalen.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="84aaa-456">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="84aaa-457">**Obs!** Om du lägger till användare i motsvarande Azure Active Directory-roll i administrationscentret för Microsoft 365 får användarna  de behörigheter som krävs i Microsoft 365 Defender-portalen samt behörigheter för andra funktioner Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="84aaa-457">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="84aaa-458">Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="84aaa-458">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="84aaa-459">Vad händer om rapporterna inte visar data?</span><span class="sxs-lookup"><span data-stu-id="84aaa-459">What if the reports aren't showing data?</span></span>

<span data-ttu-id="84aaa-460">Om du inte ser data i rapporterna kan du kontrollera att dina principer är korrekt konfigurerade.</span><span class="sxs-lookup"><span data-stu-id="84aaa-460">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="84aaa-461">Mer information finns i [Skydda mot hot.](protect-against-threats.md)</span><span class="sxs-lookup"><span data-stu-id="84aaa-461">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="84aaa-462">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="84aaa-462">Related topics</span></span>

[<span data-ttu-id="84aaa-463">Skydd mot skräppost och skadlig programvara i EOP</span><span class="sxs-lookup"><span data-stu-id="84aaa-463">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="84aaa-464">Smarta rapporter och insikter i Microsoft 365 Defender-portalen</span><span class="sxs-lookup"><span data-stu-id="84aaa-464">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="84aaa-465">Visa e-postflödesrapporter i Microsoft 365 Defender-portalen</span><span class="sxs-lookup"><span data-stu-id="84aaa-465">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="84aaa-466">Visa rapporter för Defender för Office 365</span><span class="sxs-lookup"><span data-stu-id="84aaa-466">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
