---
title: Administratörs inlämningar
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 'Administratörer kan läsa mer om hur du använder portalen för att skicka e-postmeddelanden, misstänkta nätfiske-meddelanden, skräp post och andra potentiellt skadligt meddelande, URL: er och filer till Microsoft för genomsökning i & den här gruppen.'
ms.openlocfilehash: 1b3715e3ed6f0472d9202573ff0cab92f7240ffa
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845972"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="2a859-103">Använd administratörs sändning för att skicka misstänkt skräp post, Phish, URL: er och filer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="2a859-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="2a859-104">I Microsoft 365-organisationer med post lådor i Exchange Online kan administratörer använda & portalen för att skicka e-postmeddelanden, URL: er och bifogade filer till Microsoft för att söka.</span><span class="sxs-lookup"><span data-stu-id="2a859-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="2a859-105">När du skickar ett e-postmeddelande får du information om eventuella principer som kan ha tillåtit inkommande e-post till din klient organisation samt granskning av URL: er och bilagor i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="2a859-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="2a859-106">Principer som kan ha tillåtelse till ett e-postmeddelande inkluderar en enskild användares lista över betrodda avsändare och policy principer för Exchange-flöden (kallas även transport regler).</span><span class="sxs-lookup"><span data-stu-id="2a859-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="2a859-107">Andra sätt att skicka e-postmeddelanden, webb adresser och bilagor till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="2a859-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2a859-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="2a859-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2a859-109">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="2a859-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="2a859-110">För att gå direkt till **sändnings** sidan, Använd <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="2a859-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="2a859-111">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:</span><span class="sxs-lookup"><span data-stu-id="2a859-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="2a859-112">För att skicka meddelanden och filer till Microsoft måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="2a859-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="2a859-113">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="2a859-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="2a859-114">**Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="2a859-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="2a859-115">Om du vill ha skrivskyddad åtkomst till portalen för att skicka objekt måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="2a859-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="2a859-116">**Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="2a859-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="2a859-117">**Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="2a859-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="2a859-118">Mer information om hur användarna kan skicka meddelanden och filer till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="2a859-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="2a859-119">Rapportera misstänkt innehåll till Microsoft</span><span class="sxs-lookup"><span data-stu-id="2a859-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="2a859-120">I säkerhets & Compliance Center går du till **Threat Management** -undersändningar \> **Submissions**, kontrollerar att du är på fliken **admin-överföring** och klickar sedan på **ny överföring**.</span><span class="sxs-lookup"><span data-stu-id="2a859-120">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="2a859-121">Använd **New submission** utfällbar text som visas för att skicka meddelandet, URL: en eller bifogad fil enligt beskrivningen i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="2a859-121">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="2a859-122">Skicka ett tveksamt e-postmeddelande till Microsoft</span><span class="sxs-lookup"><span data-stu-id="2a859-122">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="2a859-123">Välj **e-post**under **objekt typ** .</span><span class="sxs-lookup"><span data-stu-id="2a859-123">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="2a859-124">Använd något av följande alternativ i avsnittet **sändnings format** :</span><span class="sxs-lookup"><span data-stu-id="2a859-124">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="2a859-125">**Nätverks meddelande-ID**: det här är ett GUID-värde som är tillgängligt i huvudet **X-MS-Exchange-Organization-Network-meddelande-ID** i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="2a859-125">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="2a859-126">**Fil**: Klicka på **Välj fil**.</span><span class="sxs-lookup"><span data-stu-id="2a859-126">**File**: Click **Choose file**.</span></span> <span data-ttu-id="2a859-127">I dialog rutan som öppnas letar du reda på och markerar EML-eller MSG-filen och klickar sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="2a859-127">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="2a859-128">Ange en eller flera mottagare som du vill köra en princip kontroll för i avsnittet **mottagare** .</span><span class="sxs-lookup"><span data-stu-id="2a859-128">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="2a859-129">Princip kontrollen avgör om genomsökning av e-postmeddelandet kringgås på grund av principer för användare eller organisation.</span><span class="sxs-lookup"><span data-stu-id="2a859-129">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="2a859-130">Välj något av följande alternativ i avsnittet **orsak för inlämning** :</span><span class="sxs-lookup"><span data-stu-id="2a859-130">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="2a859-131">**Ska inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="2a859-131">**Should not have been blocked**</span></span>

   - <span data-ttu-id="2a859-132">**Bör ha blockerats**: Välj **skräp post**, **nätfiske**eller **skadlig program vara**.</span><span class="sxs-lookup"><span data-stu-id="2a859-132">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="2a859-133">Om du är osäker kan du använda ditt bästa omdöme.</span><span class="sxs-lookup"><span data-stu-id="2a859-133">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="2a859-134">Om filtret hoppades över på grund av principer vid överföring visas information om den policyn.</span><span class="sxs-lookup"><span data-stu-id="2a859-134">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="2a859-135">Om filtret inte har hoppats över på grund av en eller flera principer slutförs genomsökningen flera minuter.</span><span class="sxs-lookup"><span data-stu-id="2a859-135">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="2a859-136">Du får mer information om inlämningen genom att klicka på status länken.</span><span class="sxs-lookup"><span data-stu-id="2a859-136">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="2a859-137">Här ingår resultaten av princip kontrollen och omsökning Verdict.</span><span class="sxs-lookup"><span data-stu-id="2a859-137">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="2a859-138">OBS! detta kör inte e-postmeddelandet via Office 365 ATP-fullständig filtrerings stack igen men kör en delvis omsökning baserat på vissa av attributen för e-post, URL eller fil.</span><span class="sxs-lookup"><span data-stu-id="2a859-138">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="2a859-139">När du är klar klickar du på **Skicka** .</span><span class="sxs-lookup"><span data-stu-id="2a859-139">When you're finished, click the **Submit** button.</span></span>

![Exempel på skicka URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="2a859-141">Skicka en misstänkt URL till Microsoft</span><span class="sxs-lookup"><span data-stu-id="2a859-141">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="2a859-142">Välj **URL**under **objekt typ** .</span><span class="sxs-lookup"><span data-stu-id="2a859-142">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="2a859-143">I rutan som visas anger du den fullständiga URL: en (till exempel <https://www.fabrikam.com/marketing.html> ).</span><span class="sxs-lookup"><span data-stu-id="2a859-143">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="2a859-144">Välj något av följande alternativ i avsnittet **orsak för inlämning** :</span><span class="sxs-lookup"><span data-stu-id="2a859-144">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="2a859-145">**Ska inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="2a859-145">**Should not have been blocked**</span></span>

   - <span data-ttu-id="2a859-146">**Borde ha blockerats**: Välj **nätfiske** eller **malware**.</span><span class="sxs-lookup"><span data-stu-id="2a859-146">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="2a859-147">När du är klar klickar du på **Skicka** .</span><span class="sxs-lookup"><span data-stu-id="2a859-147">When you're finished, click the **Submit** button.</span></span>

![Exempel på Skicka e-post](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="2a859-149">Skicka en misstänkt fil till Microsoft</span><span class="sxs-lookup"><span data-stu-id="2a859-149">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="2a859-150">Välj **bilaga**under **objekt typ** .</span><span class="sxs-lookup"><span data-stu-id="2a859-150">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="2a859-151">Klicka på **Välj fil**.</span><span class="sxs-lookup"><span data-stu-id="2a859-151">Click **Choose File**.</span></span> <span data-ttu-id="2a859-152">Leta upp och markera filen i dialog rutan som öppnas och klicka sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="2a859-152">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="2a859-153">Välj något av följande alternativ i avsnittet **orsak för inlämning** :</span><span class="sxs-lookup"><span data-stu-id="2a859-153">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="2a859-154">**Ska inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="2a859-154">**Should not have been blocked**</span></span>

   - <span data-ttu-id="2a859-155">**Bör ha blockerats**: **malware** är det enda alternativet och väljs automatiskt...</span><span class="sxs-lookup"><span data-stu-id="2a859-155">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="2a859-156">När du är klar klickar du på **Skicka** .</span><span class="sxs-lookup"><span data-stu-id="2a859-156">When you're finished, click the **Submit** button.</span></span>

![Exempel på skicka bilagor](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="2a859-158">Visa administratörs inlämningar</span><span class="sxs-lookup"><span data-stu-id="2a859-158">View admin submissions</span></span>

<span data-ttu-id="2a859-159">I säkerhets & Compliance Center går du till **Threat Management** -undersändningar \> **Submissions**, kontrollerar att du är på fliken **admin-överföring** och klickar sedan på **ny överföring**.</span><span class="sxs-lookup"><span data-stu-id="2a859-159">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="2a859-160">Högst upp på sidan kan du ange ett start datum, ett slutdatum och (som standard) som du kan filtrera efter **överförings-ID** (ett GUID-värde som är kopplat till varje överföring) genom att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="2a859-160">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="2a859-161">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="2a859-161">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="2a859-162">Om du vill ändra filter villkoren klickar du på knappen **Skicka ID** och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="2a859-162">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="2a859-163">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="2a859-163">**Sender**</span></span>
- <span data-ttu-id="2a859-164">**Ämne/URL/fil namn**</span><span class="sxs-lookup"><span data-stu-id="2a859-164">**Subject/URL/File name**</span></span>
- <span data-ttu-id="2a859-165">**Skickades av**</span><span class="sxs-lookup"><span data-stu-id="2a859-165">**Submitted by**</span></span>
- <span data-ttu-id="2a859-166">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="2a859-166">**Submission type**</span></span>
- <span data-ttu-id="2a859-167">**Status**</span><span class="sxs-lookup"><span data-stu-id="2a859-167">**Status**</span></span>

![Filter alternativ för administratörs inlämning](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="2a859-169">Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**.</span><span class="sxs-lookup"><span data-stu-id="2a859-169">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="2a859-170">Spara CSV-filen i dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="2a859-170">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="2a859-171">Under grafen finns det tre flikar: **e-post** (standard), **URL**och **bifogad fil**.</span><span class="sxs-lookup"><span data-stu-id="2a859-171">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="2a859-172">Visa e-postinlägg för administratörer</span><span class="sxs-lookup"><span data-stu-id="2a859-172">View admin email submissions</span></span>

<span data-ttu-id="2a859-173">Klicka på fliken **e-post** .</span><span class="sxs-lookup"><span data-stu-id="2a859-173">Click the **Email** tab.</span></span>

<span data-ttu-id="2a859-174">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="2a859-174">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="2a859-175">**Datum**</span><span class="sxs-lookup"><span data-stu-id="2a859-175">**Date**</span></span>
- <span data-ttu-id="2a859-176">**Sändnings-ID**: ett GUID-värde som tilldelats varje överföring.</span><span class="sxs-lookup"><span data-stu-id="2a859-176">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="2a859-177">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a859-177">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="2a859-178">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a859-178">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="2a859-179">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="2a859-179">**Sender**</span></span>
- <span data-ttu-id="2a859-180">**Avsändarens IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a859-180">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="2a859-181">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="2a859-181">**Submission type**</span></span>
- <span data-ttu-id="2a859-182">**Leverans orsak**</span><span class="sxs-lookup"><span data-stu-id="2a859-182">**Delivery reason**</span></span>
- <span data-ttu-id="2a859-183">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a859-183">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="2a859-184">**Kontroll typ**</span><span class="sxs-lookup"><span data-stu-id="2a859-184">**Control type**</span></span>
- <span data-ttu-id="2a859-185">**Kontroll källa**</span><span class="sxs-lookup"><span data-stu-id="2a859-185">**Control source**</span></span>

  <span data-ttu-id="2a859-186"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="2a859-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="2a859-187">Visa URL-överföringar för administratörer</span><span class="sxs-lookup"><span data-stu-id="2a859-187">View admin URL submissions</span></span>

<span data-ttu-id="2a859-188">Klicka på fliken **URL** .</span><span class="sxs-lookup"><span data-stu-id="2a859-188">Click the **URL** tab.</span></span>

<span data-ttu-id="2a859-189">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="2a859-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="2a859-190">**Datum**</span><span class="sxs-lookup"><span data-stu-id="2a859-190">**Date**</span></span>
- <span data-ttu-id="2a859-191">**Sändnings-ID**</span><span class="sxs-lookup"><span data-stu-id="2a859-191">**Submission ID**</span></span>
- <span data-ttu-id="2a859-192">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a859-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="2a859-193">**:**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a859-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="2a859-194">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="2a859-194">**Submission type**</span></span>
- <span data-ttu-id="2a859-195">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a859-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="2a859-196"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="2a859-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="2a859-197">Visa underlämning av administrativa bilagor</span><span class="sxs-lookup"><span data-stu-id="2a859-197">View admin attachment submissions</span></span>

<span data-ttu-id="2a859-198">Klicka på fliken **bifogade filer** .</span><span class="sxs-lookup"><span data-stu-id="2a859-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="2a859-199">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="2a859-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="2a859-200">**Datum**</span><span class="sxs-lookup"><span data-stu-id="2a859-200">**Date**</span></span>
- <span data-ttu-id="2a859-201">**Sändnings-ID**</span><span class="sxs-lookup"><span data-stu-id="2a859-201">**Submission ID**</span></span>
- <span data-ttu-id="2a859-202">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a859-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="2a859-203">**Fil namn**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a859-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="2a859-204">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="2a859-204">**Submission type**</span></span>
- <span data-ttu-id="2a859-205">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a859-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="2a859-206"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="2a859-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="2a859-207">Visa användar inlämningar till Microsoft</span><span class="sxs-lookup"><span data-stu-id="2a859-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="2a859-208">Om du har distribuerat [tillägget för rapport meddelanden](enable-the-report-message-add-in.md), eller om personer använder den [inbyggda rapporteringen i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), kan du se vilka användare som rapporterar på fliken **användar överföringar** .</span><span class="sxs-lookup"><span data-stu-id="2a859-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="2a859-209">I säkerhets & Compliance Center går du till **Threat Management** - \> **inlämningar**.</span><span class="sxs-lookup"><span data-stu-id="2a859-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="2a859-210">Välj fliken **användar överföringar** och klicka sedan på **ny överföring**.</span><span class="sxs-lookup"><span data-stu-id="2a859-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="2a859-211">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="2a859-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="2a859-212">**Skickades**</span><span class="sxs-lookup"><span data-stu-id="2a859-212">**Submitted on**</span></span>
- <span data-ttu-id="2a859-213">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a859-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="2a859-214">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a859-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="2a859-215">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="2a859-215">**Sender**</span></span>
- <span data-ttu-id="2a859-216">**Avsändarens IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a859-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="2a859-217">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="2a859-217">**Submission type**</span></span>

<span data-ttu-id="2a859-218"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="2a859-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="2a859-219">Högst upp på sidan kan du ange ett start datum, ett slutdatum och (som standard) som du kan filtrera efter **avsändare** genom att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="2a859-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="2a859-220">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="2a859-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="2a859-221">Om du vill ändra filter villkoren klickar du på knappen **avsändare** och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="2a859-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="2a859-222">**Avsändningsdomän**</span><span class="sxs-lookup"><span data-stu-id="2a859-222">**Sender domain**</span></span>
- <span data-ttu-id="2a859-223">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="2a859-223">**Subject**</span></span>
- <span data-ttu-id="2a859-224">**Skickades av**</span><span class="sxs-lookup"><span data-stu-id="2a859-224">**Submitted by**</span></span>
- <span data-ttu-id="2a859-225">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="2a859-225">**Submission type**</span></span>
- <span data-ttu-id="2a859-226">**Avsändarens IP**</span><span class="sxs-lookup"><span data-stu-id="2a859-226">**Sender IP**</span></span>

![Filter alternativ för användar inlämning](../../media/user-submissions-filter-options.png)

<span data-ttu-id="2a859-228">Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**.</span><span class="sxs-lookup"><span data-stu-id="2a859-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="2a859-229">Spara CSV-filen i dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="2a859-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="2a859-230">Visa användar inlämningar till den anpassade post lådan</span><span class="sxs-lookup"><span data-stu-id="2a859-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="2a859-231">Om du har [konfigurerat en egen post låda](user-submission.md) för att få användardefinierade meddelanden kan du Visa och även skicka meddelanden som har levererats till rapporterings post lådan.</span><span class="sxs-lookup"><span data-stu-id="2a859-231">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="2a859-232">I säkerhets & Compliance Center går du till **Threat Management** - \> **inlämningar**.</span><span class="sxs-lookup"><span data-stu-id="2a859-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="2a859-233">Välj fliken **egen post låda** .</span><span class="sxs-lookup"><span data-stu-id="2a859-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="2a859-234">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="2a859-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="2a859-235">**Skickades**</span><span class="sxs-lookup"><span data-stu-id="2a859-235">**Submitted on**</span></span>
- <span data-ttu-id="2a859-236">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a859-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="2a859-237">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a859-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="2a859-238">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="2a859-238">**Sender**</span></span>
- <span data-ttu-id="2a859-239">**Avsändarens IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2a859-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="2a859-240">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="2a859-240">**Submission type**</span></span>

<span data-ttu-id="2a859-241">Högst upp på sidan kan du ange ett start datum, ett slutdatum och du kan **Filtrera efter genom** att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="2a859-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="2a859-242">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="2a859-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="2a859-243">Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**.</span><span class="sxs-lookup"><span data-stu-id="2a859-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="2a859-244">Spara CSV-filen i dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="2a859-244">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="2a859-245">Skicka meddelanden till Microsoft från den anpassade post lådan</span><span class="sxs-lookup"><span data-stu-id="2a859-245">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="2a859-246">Om du har konfigurerat den anpassade post lådan för att avlyssna användardefinierade meddelanden utan att skicka meddelanden till Microsoft kan du söka efter och skicka specifika meddelanden till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="2a859-246">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="2a859-247">Detta flyttar en användares överföring till en administratör.</span><span class="sxs-lookup"><span data-stu-id="2a859-247">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="2a859-248">På fliken **egen post låda** väljer du ett meddelande i listan, klickar på knappen **åtgärd** och gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="2a859-248">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="2a859-249">**Rapport klar**</span><span class="sxs-lookup"><span data-stu-id="2a859-249">**Report clean**</span></span>
- <span data-ttu-id="2a859-250">**Rapportera nätfiske**</span><span class="sxs-lookup"><span data-stu-id="2a859-250">**Report phishing**</span></span>
- <span data-ttu-id="2a859-251">**Rapportera skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="2a859-251">**Report malware**</span></span>
- <span data-ttu-id="2a859-252">**Rapportera skräp post**</span><span class="sxs-lookup"><span data-stu-id="2a859-252">**Report spam**</span></span>

![Alternativ på Åtgärds knappen](../../media/user-submission-custom-mailbox-action-button.png)
