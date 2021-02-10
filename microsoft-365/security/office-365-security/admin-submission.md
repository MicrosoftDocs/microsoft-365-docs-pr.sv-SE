---
title: Administratörsinskickningar
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan ta reda på hur de använder portalen inskickade innehåll i Säkerhets- & och efterlevnadscenter för att skicka misstänkta e-postmeddelanden, misstänkta nätfiskemeddelanden, skräppost och andra potentiellt skadliga meddelanden, URL:er och filer till Microsoft för genomsökning.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7a822909c318cb336c179b299aa64cd71dcca4d8
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175877"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="ca61f-103">Använd admininskickning för att skicka misstänkt skräppost, nätt phish, URL:er och filer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="ca61f-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ca61f-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="ca61f-104">**Applies to**</span></span>
- [<span data-ttu-id="ca61f-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ca61f-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="ca61f-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="ca61f-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)


<span data-ttu-id="ca61f-107">I Microsoft 365-organisationer med postlådor i Exchange Online kan administratörer använda portalen Inskickade i säkerhets- och efterlevnadscentret för & för att skicka e-postmeddelanden, URL:er och bifogade filer till Microsoft för genomsökning.</span><span class="sxs-lookup"><span data-stu-id="ca61f-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="ca61f-108">När du skickar ett e-postmeddelande får du:</span><span class="sxs-lookup"><span data-stu-id="ca61f-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="ca61f-109">**Kontroll av e-postautentisering:** Information om huruvida e-postautentisering har godkänts eller misslyckats när den levererades.</span><span class="sxs-lookup"><span data-stu-id="ca61f-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="ca61f-110">**Principträffar:** Information om principer som kan ha tillåtit eller blockerat inkommande e-post i klientorganisationen åsidosätter våra tjänstefilterprinciper.</span><span class="sxs-lookup"><span data-stu-id="ca61f-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="ca61f-111">**Payload reputation/detonation**: En undersökning av url:er och bifogade filer i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="ca61f-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="ca61f-112">**Analys av** grader: Granska gjort av mänskliga graders för att bekräfta om meddelanden är skadliga.</span><span class="sxs-lookup"><span data-stu-id="ca61f-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca61f-113">Analys av nyttolast och detonation och grader görs inte i alla klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="ca61f-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="ca61f-114">Information blockeras från att gå utanför organisationen när data inte ska lämna klientorganisationens gräns i efterlevnadssyfte.</span><span class="sxs-lookup"><span data-stu-id="ca61f-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="ca61f-115">Andra sätt att skicka e-postmeddelanden, URL:er och bifogade filer till Microsoft finns i [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="ca61f-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ca61f-116">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="ca61f-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ca61f-117">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ca61f-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ca61f-118">Om du vill gå direkt **till sidan** För inskicking använder du <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="ca61f-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="ca61f-119">Om du vill skicka meddelanden och filer till Microsoft måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="ca61f-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="ca61f-120">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ca61f-120">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="ca61f-121">**Organisationshantering** i [Exchange Online.](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="ca61f-121">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="ca61f-122">Observera att medlemskap i den här rollgruppen krävs för att visa användarinskickningar till den anpassade [postlådan enligt](#view-user-submissions-to-the-custom-mailbox) beskrivningen längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="ca61f-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="ca61f-123">Mer information om hur användare kan skicka meddelanden och filer till Microsoft finns i [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="ca61f-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="ca61f-124">Rapportera misstänkt innehåll till Microsoft</span><span class="sxs-lookup"><span data-stu-id="ca61f-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="ca61f-125">I Säkerhets- & Efterlevnadscenter går  du till Sändning av hothantering, kontrollerar att du är på fliken Administratörsinskickningar och klickar sedan på \>  **Ny inskickad inskicking.** </span><span class="sxs-lookup"><span data-stu-id="ca61f-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="ca61f-126">Använd **den utfälltext** för ny inskickning som ser ut att skicka meddelandet, URL:en eller den bifogade filen enligt beskrivningen i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="ca61f-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="ca61f-127">Skicka ett tveksamt e-postmeddelande till Microsoft</span><span class="sxs-lookup"><span data-stu-id="ca61f-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="ca61f-128">Välj **E-post i** avsnittet **Objekttyp.**</span><span class="sxs-lookup"><span data-stu-id="ca61f-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="ca61f-129">Använd **något av följande alternativ** i avsnittet Överföringsformat:</span><span class="sxs-lookup"><span data-stu-id="ca61f-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="ca61f-130">**Nätverksmeddelande-ID:** Det här är ett GUID-värde som är tillgängligt i rubriken **X-MS-Exchange-Organization-Network-Message-Id** i meddelandet eller i rubriken **X-MS-Office365-Filtering-Correlation-Id** i meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="ca61f-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="ca61f-131">**Arkiv:** Klicka **på Välj fil.**</span><span class="sxs-lookup"><span data-stu-id="ca61f-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="ca61f-132">Leta upp och markera .eml- eller .msg-filen i dialogrutan som öppnas och klicka sedan på **Öppna.**</span><span class="sxs-lookup"><span data-stu-id="ca61f-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ca61f-133">Administratörer med Defender för Office 365 abonnemang 1 eller abonnemang 2 kan skicka meddelanden som är så gamla som 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="ca61f-133">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="ca61f-134">Andra administratörer kan bara gå tillbaka 7 dagar.</span><span class="sxs-lookup"><span data-stu-id="ca61f-134">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="ca61f-135">I avsnittet **Mottagare** anger du en eller flera mottagare som du vill köra en principkontroll mot.</span><span class="sxs-lookup"><span data-stu-id="ca61f-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="ca61f-136">Principkontrollen avgör om genomsökning av e-post har kringgåts på grund av principer för användare eller organisation.</span><span class="sxs-lookup"><span data-stu-id="ca61f-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="ca61f-137">Välj **något av följande** alternativ i avsnittet Orsak till inskickning:</span><span class="sxs-lookup"><span data-stu-id="ca61f-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="ca61f-138">**Borde inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="ca61f-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="ca61f-139">**Ska ha blockerats:** Välj **Skräppost,** **nätfiske** eller **skadlig kod.**</span><span class="sxs-lookup"><span data-stu-id="ca61f-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="ca61f-140">Om du är osäker kan du använda ditt bästa omdöme.</span><span class="sxs-lookup"><span data-stu-id="ca61f-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="ca61f-141">Klicka på knappen Skicka när du **är** klar.</span><span class="sxs-lookup"><span data-stu-id="ca61f-141">When you're finished, click the **Submit** button.</span></span>

   ![Exempel på URL-inskickning](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="ca61f-143">Skicka en misstänkt URL till Microsoft</span><span class="sxs-lookup"><span data-stu-id="ca61f-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="ca61f-144">Välj URL i avsnittet **Objekttyp.** </span><span class="sxs-lookup"><span data-stu-id="ca61f-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="ca61f-145">I rutan som visas anger du den fullständiga WEBBADRESSen (till `https://www.fabrikam.com/marketing.html` exempel).</span><span class="sxs-lookup"><span data-stu-id="ca61f-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="ca61f-146">Välj **något av följande** alternativ i avsnittet Orsak till inskickning:</span><span class="sxs-lookup"><span data-stu-id="ca61f-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="ca61f-147">**Borde inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="ca61f-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="ca61f-148">**Bör ha blockerats:** Välj **nätfiske eller** **skadlig kod.**</span><span class="sxs-lookup"><span data-stu-id="ca61f-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="ca61f-149">Klicka på knappen Skicka när du **är** klar.</span><span class="sxs-lookup"><span data-stu-id="ca61f-149">When you're finished, click the **Submit** button.</span></span>

   ![Exempel på e-postinskickning](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="ca61f-151">Skicka en misstänkt fil till Microsoft</span><span class="sxs-lookup"><span data-stu-id="ca61f-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="ca61f-152">Välj **Bifogad fil i** avsnittet **Objekttyp.**</span><span class="sxs-lookup"><span data-stu-id="ca61f-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="ca61f-153">Klicka **på Välj fil.**</span><span class="sxs-lookup"><span data-stu-id="ca61f-153">Click **Choose File**.</span></span> <span data-ttu-id="ca61f-154">Leta upp och markera filen i dialogrutan som öppnas och klicka sedan på **Öppna.**</span><span class="sxs-lookup"><span data-stu-id="ca61f-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="ca61f-155">Välj **något av följande** alternativ i avsnittet Orsak till inskickning:</span><span class="sxs-lookup"><span data-stu-id="ca61f-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="ca61f-156">**Borde inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="ca61f-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="ca61f-157">**Bör ha blockerats:** **Skadlig programvara** är det enda alternativet och väljs automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ca61f-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="ca61f-158">Klicka på knappen Skicka när du **är** klar.</span><span class="sxs-lookup"><span data-stu-id="ca61f-158">When you're finished, click the **Submit** button.</span></span>

   ![Exempel på inskickade bifogade filer](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="ca61f-160">Visa administratörsinskickningar</span><span class="sxs-lookup"><span data-stu-id="ca61f-160">View admin submissions</span></span>

<span data-ttu-id="ca61f-161">I Säkerhets- & Efterlevnadscenter går  du till Sändning av hothantering, kontrollerar att du är på fliken Administratörsinskickningar och klickar sedan på \>  **Ny inskickad inskicking.** </span><span class="sxs-lookup"><span data-stu-id="ca61f-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="ca61f-162">Högst upp på sidan kan du ange ett startdatum, ett slutdatum och (som  standard) kan du filtrera efter inskicknings-ID (ett GUID-värde som tilldelas till varje inskickat värde) genom att ange ett värde i rutan och klicka på ![ ](../../media/scc-quarantine-refresh.png) Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="ca61f-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="ca61f-163">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="ca61f-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="ca61f-164">Om du vill ändra filtervillkor klickar du **på knappen** Submission ID och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="ca61f-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="ca61f-165">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="ca61f-165">**Sender**</span></span>
- <span data-ttu-id="ca61f-166">**Ämne/URL/Filnamn**</span><span class="sxs-lookup"><span data-stu-id="ca61f-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="ca61f-167">**Skickat av**</span><span class="sxs-lookup"><span data-stu-id="ca61f-167">**Submitted by**</span></span>
- <span data-ttu-id="ca61f-168">**Typ av inskicking**</span><span class="sxs-lookup"><span data-stu-id="ca61f-168">**Submission type**</span></span>
- <span data-ttu-id="ca61f-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="ca61f-169">**Status**</span></span>

![Filteralternativ för administratörsinskickningar](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="ca61f-171">Om du vill exportera resultaten **klickar du på Exportera** nästan högst upp på sidan och väljer **Diagramdata** eller **Tabell.**</span><span class="sxs-lookup"><span data-stu-id="ca61f-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="ca61f-172">Spara CSV-filen i dialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="ca61f-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="ca61f-173">Under diagrammet finns det tre flikar: **E-post** (standard), **URL och** **bifogad fil.**</span><span class="sxs-lookup"><span data-stu-id="ca61f-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="ca61f-174">Visa inskickade e-postinskick för administratörer</span><span class="sxs-lookup"><span data-stu-id="ca61f-174">View admin email submissions</span></span>

<span data-ttu-id="ca61f-175">Klicka på **fliken E-post.**</span><span class="sxs-lookup"><span data-stu-id="ca61f-175">Click the **Email** tab.</span></span>

<span data-ttu-id="ca61f-176">Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="ca61f-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ca61f-177">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ca61f-177">**Date**</span></span>
- <span data-ttu-id="ca61f-178">**Inskickings-ID:** Ett GUID-värde som tilldelas till varje sändning.</span><span class="sxs-lookup"><span data-stu-id="ca61f-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="ca61f-179">**Skickat av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ca61f-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ca61f-180">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ca61f-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="ca61f-181">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="ca61f-181">**Sender**</span></span>
- <span data-ttu-id="ca61f-182">**Sender IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ca61f-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="ca61f-183">**Typ av inskicking**</span><span class="sxs-lookup"><span data-stu-id="ca61f-183">**Submission type**</span></span>
- <span data-ttu-id="ca61f-184">**Leveransorsak**</span><span class="sxs-lookup"><span data-stu-id="ca61f-184">**Delivery reason**</span></span>
- <span data-ttu-id="ca61f-185">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ca61f-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="ca61f-186"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfällplan.</span><span class="sxs-lookup"><span data-stu-id="ca61f-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="ca61f-187">Information om administratörsinskickning</span><span class="sxs-lookup"><span data-stu-id="ca61f-187">Admin submission rescan details</span></span>

<span data-ttu-id="ca61f-188">Meddelanden som skickas som inskickade administratörer skannas på ny sida och resultaten visas i den utfällna informationen:</span><span class="sxs-lookup"><span data-stu-id="ca61f-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="ca61f-189">Om det var fel i avsändarens e-postautentisering vid leverans.</span><span class="sxs-lookup"><span data-stu-id="ca61f-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="ca61f-190">Information om principträffar som kan ha påverkat eller åsidosättt ett meddelandes bedömning.</span><span class="sxs-lookup"><span data-stu-id="ca61f-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="ca61f-191">Aktuella detonationsresultat för att se om URL:erna eller filerna som finns i meddelandet är skadliga eller inte.</span><span class="sxs-lookup"><span data-stu-id="ca61f-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="ca61f-192">Feedback från graders.</span><span class="sxs-lookup"><span data-stu-id="ca61f-192">Feedback from graders.</span></span>

<span data-ttu-id="ca61f-193">Om en åsidosättning hittades ska reningen slutföras inom några minuter.</span><span class="sxs-lookup"><span data-stu-id="ca61f-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="ca61f-194">Om det inte uppstod något problem med e-postautentisering eller e-postleverans påverkades inte av en åsidosättning, kan det ta upp till en dag för feedback från grader.</span><span class="sxs-lookup"><span data-stu-id="ca61f-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="ca61f-195">Visa url-inskickade administratörs-URL</span><span class="sxs-lookup"><span data-stu-id="ca61f-195">View admin URL submissions</span></span>

<span data-ttu-id="ca61f-196">Klicka på **fliken URL.**</span><span class="sxs-lookup"><span data-stu-id="ca61f-196">Click the **URL** tab.</span></span>

<span data-ttu-id="ca61f-197">Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="ca61f-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ca61f-198">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ca61f-198">**Date**</span></span>
- <span data-ttu-id="ca61f-199">**Inskickings-ID**</span><span class="sxs-lookup"><span data-stu-id="ca61f-199">**Submission ID**</span></span>
- <span data-ttu-id="ca61f-200">**Skickat av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ca61f-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ca61f-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ca61f-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="ca61f-202">**Typ av inskicking**</span><span class="sxs-lookup"><span data-stu-id="ca61f-202">**Submission type**</span></span>
- <span data-ttu-id="ca61f-203">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ca61f-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="ca61f-204"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfällplan.</span><span class="sxs-lookup"><span data-stu-id="ca61f-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="ca61f-205">Visa inskickade bifogade filer från administratörer</span><span class="sxs-lookup"><span data-stu-id="ca61f-205">View admin attachment submissions</span></span>

<span data-ttu-id="ca61f-206">Klicka på **fliken Bifogade** filer.</span><span class="sxs-lookup"><span data-stu-id="ca61f-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="ca61f-207">Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="ca61f-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ca61f-208">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ca61f-208">**Date**</span></span>
- <span data-ttu-id="ca61f-209">**Inskickings-ID**</span><span class="sxs-lookup"><span data-stu-id="ca61f-209">**Submission ID**</span></span>
- <span data-ttu-id="ca61f-210">**Skickat av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ca61f-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ca61f-211">**Filnamn**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ca61f-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="ca61f-212">**Typ av inskicking**</span><span class="sxs-lookup"><span data-stu-id="ca61f-212">**Submission type**</span></span>
- <span data-ttu-id="ca61f-213">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ca61f-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="ca61f-214"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfällplan.</span><span class="sxs-lookup"><span data-stu-id="ca61f-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="ca61f-215">Visa användarinskick till Microsoft</span><span class="sxs-lookup"><span data-stu-id="ca61f-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="ca61f-216">Om du har distribuerat tillägget Rapportmeddelande, [](enable-the-report-phish-add-in.md) [](enable-the-report-message-add-in.md)tillägget Rapport nätfiske eller personer använder den [inbyggda](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)rapporteringen i Outlook på webben  kan du se vad användarna rapporterar på fliken Användarinsändning.</span><span class="sxs-lookup"><span data-stu-id="ca61f-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="ca61f-217">Gå till & för hantering av  hothantering i Säkerhets- \> **och efterlevnadscentret.**</span><span class="sxs-lookup"><span data-stu-id="ca61f-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="ca61f-218">Välj fliken **Användarinskickningar** och klicka sedan på **Ny inskickning.**</span><span class="sxs-lookup"><span data-stu-id="ca61f-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="ca61f-219">Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="ca61f-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ca61f-220">**Skickat**</span><span class="sxs-lookup"><span data-stu-id="ca61f-220">**Submitted on**</span></span>
- <span data-ttu-id="ca61f-221">**Skickat av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ca61f-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ca61f-222">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ca61f-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="ca61f-223">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="ca61f-223">**Sender**</span></span>
- <span data-ttu-id="ca61f-224">**Sender IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ca61f-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="ca61f-225">**Typ av inskicking**</span><span class="sxs-lookup"><span data-stu-id="ca61f-225">**Submission type**</span></span>

<span data-ttu-id="ca61f-226"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfällplan.</span><span class="sxs-lookup"><span data-stu-id="ca61f-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="ca61f-227">Högst upp på sidan kan du ange ett startdatum, ett slutdatum och (som  standard) kan du filtrera efter avsändare genom att ange ett värde i rutan och klicka på ![ ](../../media/scc-quarantine-refresh.png) Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="ca61f-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="ca61f-228">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="ca61f-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="ca61f-229">Om du vill ändra filtervillkor klickar du **på knappen** Avsändare och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="ca61f-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="ca61f-230">**Avsändningsdomän**</span><span class="sxs-lookup"><span data-stu-id="ca61f-230">**Sender domain**</span></span>
- <span data-ttu-id="ca61f-231">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="ca61f-231">**Subject**</span></span>
- <span data-ttu-id="ca61f-232">**Skickat av**</span><span class="sxs-lookup"><span data-stu-id="ca61f-232">**Submitted by**</span></span>
- <span data-ttu-id="ca61f-233">**Typ av inskicking**</span><span class="sxs-lookup"><span data-stu-id="ca61f-233">**Submission type**</span></span>
- <span data-ttu-id="ca61f-234">**Sender IP**</span><span class="sxs-lookup"><span data-stu-id="ca61f-234">**Sender IP**</span></span>

![Filteralternativ för användarinskickningar](../../media/user-submissions-filter-options.png)

<span data-ttu-id="ca61f-236">Om du vill exportera resultaten **klickar du på Exportera** nästan högst upp på sidan och väljer **Diagramdata** eller **Tabell.**</span><span class="sxs-lookup"><span data-stu-id="ca61f-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="ca61f-237">Spara CSV-filen i dialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="ca61f-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="ca61f-238">Visa användarinskickningar till den anpassade postlådan</span><span class="sxs-lookup"><span data-stu-id="ca61f-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="ca61f-239">**Om** du har konfigurerat [en anpassad](user-submission.md) postlåda för att ta emot användarrapporterade meddelanden kan du visa och även skicka meddelanden som har levererats till den rapportpostlådan.</span><span class="sxs-lookup"><span data-stu-id="ca61f-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="ca61f-240">Gå till & för hantering av  hothantering i Säkerhets- \> **och efterlevnadscentret.**</span><span class="sxs-lookup"><span data-stu-id="ca61f-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="ca61f-241">Välj fliken **Anpassad** postlåda.</span><span class="sxs-lookup"><span data-stu-id="ca61f-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="ca61f-242">Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="ca61f-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ca61f-243">**Skickat**</span><span class="sxs-lookup"><span data-stu-id="ca61f-243">**Submitted on**</span></span>
- <span data-ttu-id="ca61f-244">**Skickat av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ca61f-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ca61f-245">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ca61f-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="ca61f-246">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="ca61f-246">**Sender**</span></span>
- <span data-ttu-id="ca61f-247">**Sender IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ca61f-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="ca61f-248">**Typ av inskicking**</span><span class="sxs-lookup"><span data-stu-id="ca61f-248">**Submission type**</span></span>

<span data-ttu-id="ca61f-249">Högst upp på sidan kan du ange ett startdatum, ett slutdatum  och filtrera efter Skickat genom att ange ett värde i rutan och klicka på ![ ](../../media/scc-quarantine-refresh.png) Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="ca61f-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="ca61f-250">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="ca61f-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="ca61f-251">Om du vill exportera resultaten **klickar du på Exportera** nästan högst upp på sidan och väljer **Diagramdata** eller **Tabell.**</span><span class="sxs-lookup"><span data-stu-id="ca61f-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="ca61f-252">Spara CSV-filen i dialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="ca61f-252">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="ca61f-253">Ångra användarinskickningar</span><span class="sxs-lookup"><span data-stu-id="ca61f-253">Undo user submissions</span></span>

<span data-ttu-id="ca61f-254">När en användare skickar ett misstänkt e-postmeddelande till den anpassade postlådan kan användaren och administratören inte ångra inskickat material.</span><span class="sxs-lookup"><span data-stu-id="ca61f-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="ca61f-255">Om användaren vill återställa e-post är den tillgänglig för återställning i mapparna Borttagna objekt eller Skräppost.</span><span class="sxs-lookup"><span data-stu-id="ca61f-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="ca61f-256">Skicka meddelanden till Microsoft från den anpassade postlådan</span><span class="sxs-lookup"><span data-stu-id="ca61f-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="ca61f-257">Om du har konfigurerat den anpassade postlådan för att snappa upp användarrapporterade meddelanden utan att skicka meddelanden till Microsoft kan du hitta och skicka specifika meddelanden till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="ca61f-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="ca61f-258">Då flyttas en användarinskickning till en administratörsinskickning.</span><span class="sxs-lookup"><span data-stu-id="ca61f-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="ca61f-259">Markera ett **meddelande i** listan på fliken Anpassad  postlåda, klicka på åtgärdsknappen och gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="ca61f-259">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="ca61f-260">**Rapportrensning**</span><span class="sxs-lookup"><span data-stu-id="ca61f-260">**Report clean**</span></span>
- <span data-ttu-id="ca61f-261">**Rapportera nätfiske**</span><span class="sxs-lookup"><span data-stu-id="ca61f-261">**Report phishing**</span></span>
- <span data-ttu-id="ca61f-262">**Rapportera skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="ca61f-262">**Report malware**</span></span>
- <span data-ttu-id="ca61f-263">**Rapportera skräppost**</span><span class="sxs-lookup"><span data-stu-id="ca61f-263">**Report spam**</span></span>

![Alternativ på knappen Åtgärd](../../media/user-submission-custom-mailbox-action-button.png)
