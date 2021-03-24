---
title: Administratörs inskickade material
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
description: Administratörer kan ta reda på hur de använder portalen för inskickade innehåll i Säkerhets- och efterlevnadscenter för & för att skicka misstänkta e-postmeddelanden, misstänkta nätfiskemeddelanden, skräppost och andra potentiellt skadliga meddelanden, URL:er och filer till Microsoft för genomsökning.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3dd566de3ba4b4281b19c423b8623f081c378bca
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073689"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="6fc4d-103">Använd administrationsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="6fc4d-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6fc4d-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-104">**Applies to**</span></span>
- [<span data-ttu-id="6fc4d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6fc4d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6fc4d-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="6fc4d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="6fc4d-107">I Microsoft 365-organisationer med postlådor i Exchange Online kan administratörer använda portalen för inskickade meddelanden i säkerhets- och efterlevnadscentret för & för att skicka e-postmeddelanden, URL:er och bifogade filer till Microsoft för genomsökning.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="6fc4d-108">När du skickar ett e-postmeddelande får du:</span><span class="sxs-lookup"><span data-stu-id="6fc4d-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="6fc4d-109">**Kontroll av e-postautentisering:** Information om e-postautentisering har godkänts eller misslyckats när den levererades.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="6fc4d-110">**Principträffar:** Information om principer som kan ha tillåtit eller blockerat inkommande e-post i klientorganisationen, åsidosätter våra tjänstfilters bedömningar.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="6fc4d-111">**Payload reputation/detonation**: Eng över alla URL:er och bifogade filer i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="6fc4d-112">**Gradersanalys:** Granska utförts av grader för att bekräfta om meddelanden är skadliga.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fc4d-113">Analys av berytning och gradering av nyttolast görs inte i alla klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="6fc4d-114">Information blockeras från att gå utanför organisationen när data inte ska lämna klientorganisationsgränsen i efterlevnadssyfte.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="6fc4d-115">Andra sätt att skicka e-postmeddelanden, URL:er och bifogade filer till Microsoft finns i [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="6fc4d-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6fc4d-116">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="6fc4d-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6fc4d-117">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="6fc4d-118">Använd för att gå direkt **till sidan** Inskickat. <https://protection.office.com/reportsubmission></span><span class="sxs-lookup"><span data-stu-id="6fc4d-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="6fc4d-119">För att skicka meddelanden och filer till Microsoft måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="6fc4d-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="6fc4d-120">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6fc4d-120">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="6fc4d-121">**Organisationshantering** i [Exchange Online.](/Exchange/permissions-exo/permissions-exo#role-groups)</span><span class="sxs-lookup"><span data-stu-id="6fc4d-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="6fc4d-122">Observera att medlemskap i den här rollgruppen krävs för att [visa användarinskick till den anpassade postlådan enligt](#view-user-submissions-to-the-custom-mailbox) beskrivningen längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="6fc4d-123">Mer information om hur användare kan skicka meddelanden och filer till Microsoft finns i [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="6fc4d-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="6fc4d-124">Rapportera misstänkt innehåll till Microsoft</span><span class="sxs-lookup"><span data-stu-id="6fc4d-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="6fc4d-125">I Säkerhets- & efterlevnadscenter går  du till Inskickade hothantering , kontrollerar att du är på fliken Administratörsinskickningar och klickar sedan \> på **Ny inskickad inskickad information.** </span><span class="sxs-lookup"><span data-stu-id="6fc4d-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="6fc4d-126">Använd den utfällingstext för ny inskickning som ser ut att skicka meddelandet, **URL:en** eller den bifogade filen enligt beskrivningen i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="6fc4d-127">Skicka ett tveksamt e-postmeddelande till Microsoft</span><span class="sxs-lookup"><span data-stu-id="6fc4d-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="6fc4d-128">Välj **E-post** i avsnittet **Objekttyp.**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="6fc4d-129">Använd **något av följande** alternativ i avsnittet Överföringsformat:</span><span class="sxs-lookup"><span data-stu-id="6fc4d-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="6fc4d-130">**Nätverksmeddelande-ID:** Det här är ett GUID-värde som är tillgängligt i rubriken **X-MS-Exchange-Organization-Network-Message-Id** i meddelandet eller i **rubriken X-MS-Office365-Filtering-Correlation-Id** i meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="6fc4d-131">**Fil:** Klicka på **Välj fil**.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="6fc4d-132">Leta rätt på och välj .eml- eller .msg-filen i dialogrutan som öppnas och klicka sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6fc4d-133">Administratörer med Defender för Office 365 abonnemang 1 eller abonnemang 2 kan skicka meddelanden så gamla som 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-133">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="6fc4d-134">Andra administratörer kan bara gå tillbaka 7 dagar.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-134">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="6fc4d-135">I avsnittet **Mottagare** anger du en eller flera mottagare som du vill köra en principkontroll mot.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="6fc4d-136">Principkontrollen avgör om förbikoppling av e-post beror på användar- eller organisationsprinciper.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="6fc4d-137">Välj **något av följande** alternativ i avsnittet Orsak till inskickning:</span><span class="sxs-lookup"><span data-stu-id="6fc4d-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="6fc4d-138">**Borde inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="6fc4d-139">**Ska ha blockerats:** Välj **Skräppost,** **Nätfiske** eller **Skadlig kod.**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="6fc4d-140">Om du är osäker kan du använda ditt bästa omdöme.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="6fc4d-141">När du är klar klickar du på **skicka-knappen.**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-141">When you're finished, click the **Submit** button.</span></span>

   ![Exempel på URL-inskickning](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="6fc4d-143">Skicka en misstänkt URL till Microsoft</span><span class="sxs-lookup"><span data-stu-id="6fc4d-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="6fc4d-144">Välj URL **i avsnittet** **Objekttyp.**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="6fc4d-145">I rutan som visas anger du den fullständiga webbadressen (till exempel `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="6fc4d-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="6fc4d-146">Välj **något av följande** alternativ i avsnittet Orsak till inskickning:</span><span class="sxs-lookup"><span data-stu-id="6fc4d-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="6fc4d-147">**Borde inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="6fc4d-148">**Ska ha blockerats:** Välj **Nätfiske** eller **skadlig kod.**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="6fc4d-149">När du är klar klickar du på **skicka-knappen.**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-149">When you're finished, click the **Submit** button.</span></span>

   ![Exempel på e-postinskickning](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="6fc4d-151">Skicka en misstänkt fil till Microsoft</span><span class="sxs-lookup"><span data-stu-id="6fc4d-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="6fc4d-152">Välj **Bifogad fil** i avsnittet **Objekttyp.**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="6fc4d-153">Klicka **på Välj fil**.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-153">Click **Choose File**.</span></span> <span data-ttu-id="6fc4d-154">Leta rätt på och markera filen i dialogrutan som öppnas och klicka sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="6fc4d-155">Välj **något av följande** alternativ i avsnittet Orsak till inskickning:</span><span class="sxs-lookup"><span data-stu-id="6fc4d-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="6fc4d-156">**Borde inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="6fc4d-157">**Borde ha blockerats:** **Skadlig programvara** är det enda alternativet, och väljs automatiskt.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="6fc4d-158">När du är klar klickar du på **skicka-knappen.**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-158">When you're finished, click the **Submit** button.</span></span>

   ![Exempel på inskickade bifogade filer](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="6fc4d-160">Visa administrationsinskick</span><span class="sxs-lookup"><span data-stu-id="6fc4d-160">View admin submissions</span></span>

<span data-ttu-id="6fc4d-161">I Säkerhets- & efterlevnadscenter går  du till Inskickade hothantering , kontrollerar att du är på fliken Administratörsinskickningar och klickar sedan \> på **Ny inskickad inskickad information.** </span><span class="sxs-lookup"><span data-stu-id="6fc4d-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="6fc4d-162">Högst upp på sidan kan du ange ett startdatum, ett slutdatum och (som  standard) kan du filtrera efter sändnings-ID (ett GUID-värde som är tilldelat till varje inskickat värde) genom att ange ett värde i rutan och klicka på Uppdatera knapp ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="6fc4d-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="6fc4d-163">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="6fc4d-164">Om du vill ändra filtervillkor klickar du på knappen Inskickat **ID** och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="6fc4d-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="6fc4d-165">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-165">**Sender**</span></span>
- <span data-ttu-id="6fc4d-166">**Ämne/URL/Filnamn**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="6fc4d-167">**Skickat av**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-167">**Submitted by**</span></span>
- <span data-ttu-id="6fc4d-168">**Typ av inskickat material**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-168">**Submission type**</span></span>
- <span data-ttu-id="6fc4d-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-169">**Status**</span></span>

![Filteralternativ för administratörsinskick](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="6fc4d-171">Om du vill exportera resultaten klickar **du på** Exportera högst upp på sidan och väljer **Diagramdata** eller **Tabell.**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="6fc4d-172">Spara CSV-filen i dialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="6fc4d-173">Under diagrammet finns tre **flikar:** E-post (standard), **URL och** **Bifogad fil**.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="6fc4d-174">Visa e-postinskick från administratör</span><span class="sxs-lookup"><span data-stu-id="6fc4d-174">View admin email submissions</span></span>

<span data-ttu-id="6fc4d-175">Klicka på fliken **E-post.**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-175">Click the **Email** tab.</span></span>

<span data-ttu-id="6fc4d-176">Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="6fc4d-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6fc4d-177">**Datum**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-177">**Date**</span></span>
- <span data-ttu-id="6fc4d-178">**Överförings-ID:** Ett GUID-värde som tilldelas till varje sändning.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="6fc4d-179">**Skickat av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6fc4d-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6fc4d-180">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6fc4d-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="6fc4d-181">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-181">**Sender**</span></span>
- <span data-ttu-id="6fc4d-182">**Sender IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6fc4d-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="6fc4d-183">**Typ av inskickat material**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-183">**Submission type**</span></span>
- <span data-ttu-id="6fc4d-184">**Leveransorsak**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-184">**Delivery reason**</span></span>
- <span data-ttu-id="6fc4d-185">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6fc4d-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="6fc4d-186"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfäll tillgänglig plats.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="6fc4d-187">Information om administratörsinskickning igen</span><span class="sxs-lookup"><span data-stu-id="6fc4d-187">Admin submission rescan details</span></span>

<span data-ttu-id="6fc4d-188">Meddelanden som skickas i administratörsinskick genomsöks på ny plats och resultaten visas i den utfällade informationen:</span><span class="sxs-lookup"><span data-stu-id="6fc4d-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="6fc4d-189">Om avsändarens e-postautentisering misslyckades vid leveransen.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="6fc4d-190">Information om politiska träffar som kan ha påverkat eller åsidosatt bedömningen av ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="6fc4d-191">Aktuella detonationsresultat för att se om webbadresserna eller filerna i meddelandet var skadliga eller inte.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="6fc4d-192">Feedback från grader.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-192">Feedback from graders.</span></span>

<span data-ttu-id="6fc4d-193">Om en åsidosättning hittades bör omskanningen slutföras på några minuter.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="6fc4d-194">Om det inte uppstod något problem i e-postautentisering eller -leverans påverkades inte av en åsidosättning, kan feedback från grader ta upp till en dag.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="6fc4d-195">Visa url-inskickade administratörs-URL</span><span class="sxs-lookup"><span data-stu-id="6fc4d-195">View admin URL submissions</span></span>

<span data-ttu-id="6fc4d-196">Klicka på **fliken URL.**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-196">Click the **URL** tab.</span></span>

<span data-ttu-id="6fc4d-197">Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="6fc4d-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6fc4d-198">**Datum**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-198">**Date**</span></span>
- <span data-ttu-id="6fc4d-199">**Sändnings-ID**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-199">**Submission ID**</span></span>
- <span data-ttu-id="6fc4d-200">**Skickat av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6fc4d-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6fc4d-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6fc4d-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="6fc4d-202">**Typ av inskickat material**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-202">**Submission type**</span></span>
- <span data-ttu-id="6fc4d-203">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6fc4d-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="6fc4d-204"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfäll tillgänglig plats.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="6fc4d-205">Visa inskickade bifogade filer från administratörer</span><span class="sxs-lookup"><span data-stu-id="6fc4d-205">View admin attachment submissions</span></span>

<span data-ttu-id="6fc4d-206">Klicka på **fliken Bifogade** filer.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="6fc4d-207">Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="6fc4d-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6fc4d-208">**Datum**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-208">**Date**</span></span>
- <span data-ttu-id="6fc4d-209">**Sändnings-ID**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-209">**Submission ID**</span></span>
- <span data-ttu-id="6fc4d-210">**Skickat av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6fc4d-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6fc4d-211">**Filnamn**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6fc4d-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="6fc4d-212">**Typ av inskickat material**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-212">**Submission type**</span></span>
- <span data-ttu-id="6fc4d-213">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6fc4d-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="6fc4d-214"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfäll tillgänglig plats.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="6fc4d-215">Visa användarinskick till Microsoft</span><span class="sxs-lookup"><span data-stu-id="6fc4d-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="6fc4d-216">Om du har distribuerat tillägget Rapportmeddelande, [](enable-the-report-phish-add-in.md) [](enable-the-report-message-add-in.md)tillägget Rapportfiske eller om användarna använder den [inbyggda](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)rapporteringen i Outlook på webben, kan du se vad användarna rapporterar på fliken Användarinsändning. </span><span class="sxs-lookup"><span data-stu-id="6fc4d-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="6fc4d-217">I Säkerhets- & efterlevnadscenter går du till **Sändning av** \> **hothantering.**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="6fc4d-218">Välj fliken **Användarinskickningar** och klicka sedan på **Ny inskicking.**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="6fc4d-219">Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="6fc4d-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6fc4d-220">**Skickat**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-220">**Submitted on**</span></span>
- <span data-ttu-id="6fc4d-221">**Skickat av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6fc4d-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6fc4d-222">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6fc4d-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="6fc4d-223">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-223">**Sender**</span></span>
- <span data-ttu-id="6fc4d-224">**Sender IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6fc4d-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="6fc4d-225">**Typ av inskickat material**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-225">**Submission type**</span></span>

<span data-ttu-id="6fc4d-226"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfäll tillgänglig plats.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="6fc4d-227">Högst upp på sidan kan du ange ett startdatum, ett slutdatum och (som  standard) kan du filtrera efter avsändare genom att ange ett värde i rutan och klicka på ![ Uppdatera ](../../media/scc-quarantine-refresh.png) knapp.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="6fc4d-228">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="6fc4d-229">Om du vill ändra filtervillkor klickar du **på knappen** Avsändare och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="6fc4d-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="6fc4d-230">**Avsändningsdomän**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-230">**Sender domain**</span></span>
- <span data-ttu-id="6fc4d-231">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-231">**Subject**</span></span>
- <span data-ttu-id="6fc4d-232">**Skickat av**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-232">**Submitted by**</span></span>
- <span data-ttu-id="6fc4d-233">**Typ av inskickat material**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-233">**Submission type**</span></span>
- <span data-ttu-id="6fc4d-234">**Sender IP**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-234">**Sender IP**</span></span>

![Filteralternativ för användarinskick](../../media/user-submissions-filter-options.png)

<span data-ttu-id="6fc4d-236">Om du vill exportera resultaten klickar **du på** Exportera högst upp på sidan och väljer **Diagramdata** eller **Tabell.**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="6fc4d-237">Spara CSV-filen i dialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="6fc4d-238">Visa användarinskick till den anpassade postlådan</span><span class="sxs-lookup"><span data-stu-id="6fc4d-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="6fc4d-239">**Om** du har konfigurerat [en anpassad postlåda för](user-submission.md) att ta emot användarrapporterade meddelanden kan du visa och skicka meddelanden som har levererats till den rapportpostlådan.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="6fc4d-240">I Säkerhets- & efterlevnadscenter går du till **Sändning av** \> **hothantering.**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="6fc4d-241">Välj fliken **Anpassad** postlåda.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="6fc4d-242">Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="6fc4d-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6fc4d-243">**Skickat**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-243">**Submitted on**</span></span>
- <span data-ttu-id="6fc4d-244">**Skickat av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6fc4d-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6fc4d-245">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6fc4d-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="6fc4d-246">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-246">**Sender**</span></span>
- <span data-ttu-id="6fc4d-247">**Sender IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6fc4d-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="6fc4d-248">**Typ av inskickat material**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-248">**Submission type**</span></span>

<span data-ttu-id="6fc4d-249">Högst upp på sidan kan du ange ett startdatum, ett slutdatum och du kan filtrera efter **Skickat** genom att ange ett värde i rutan och klicka på ![ ](../../media/scc-quarantine-refresh.png) Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="6fc4d-250">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="6fc4d-251">Om du vill exportera resultaten klickar **du på** Exportera högst upp på sidan och väljer **Diagramdata** eller **Tabell.**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="6fc4d-252">Spara CSV-filen i dialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-252">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="6fc4d-253">Ångra användarinskick</span><span class="sxs-lookup"><span data-stu-id="6fc4d-253">Undo user submissions</span></span>

<span data-ttu-id="6fc4d-254">När en användare skickar ett misstänkt e-postmeddelande till den anpassade postlådan kan användaren och administratören inte ångra inskickat material.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="6fc4d-255">Om användaren vill återställa e-posten kan den återställas i mapparna Borttagna objekt eller Skräppost.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="6fc4d-256">Skicka meddelanden till Microsoft från den anpassade postlådan</span><span class="sxs-lookup"><span data-stu-id="6fc4d-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="6fc4d-257">Om du har konfigurerat den anpassade postlådan för att snappa upp användarrapporterade meddelanden utan att skicka meddelanden till Microsoft kan du hitta och skicka specifika meddelanden till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="6fc4d-258">Då flyttas en användarinskickning till en administratörsinskickning.</span><span class="sxs-lookup"><span data-stu-id="6fc4d-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="6fc4d-259">Markera **ett meddelande i** listan på fliken Anpassad postlåda, klicka **på** knappen Åtgärd och gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="6fc4d-259">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="6fc4d-260">**Rapportrensning**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-260">**Report clean**</span></span>
- <span data-ttu-id="6fc4d-261">**Rapportera nätfiske**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-261">**Report phishing**</span></span>
- <span data-ttu-id="6fc4d-262">**Rapportera skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-262">**Report malware**</span></span>
- <span data-ttu-id="6fc4d-263">**Rapportera skräppost**</span><span class="sxs-lookup"><span data-stu-id="6fc4d-263">**Report spam**</span></span>

![Alternativ på knappen Åtgärd](../../media/user-submission-custom-mailbox-action-button.png)