---
title: Administratörs inlämningar
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 'Administratörer kan läsa mer om hur du använder portalen för att skicka e-postmeddelanden, misstänkta nätfiske-meddelanden, skräp post och andra potentiellt skadligt meddelande, URL: er och filer till Microsoft för genomsökning i & den här gruppen.'
ms.openlocfilehash: 4d0737d881334db9cc4aeda43037ab89d7444618
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577876"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="8122a-103">Använd administratörs sändning för att skicka misstänkt skräp post, Phish, URL: er och filer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="8122a-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="8122a-104">I Microsoft 365-organisationer med post lådor i Exchange Online kan administratörer använda & portalen för att skicka e-postmeddelanden, URL: er och bifogade filer till Microsoft för att söka.</span><span class="sxs-lookup"><span data-stu-id="8122a-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="8122a-105">När du skickar ett e-postmeddelande får du information om eventuella principer som kan ha tillåtit inkommande e-post till din klient organisation samt granskning av URL: er och bilagor i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="8122a-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="8122a-106">Principer som kan ha tillåtelse till ett e-postmeddelande inkluderar en enskild användares lista över betrodda avsändare och policy principer för Exchange-flöden (kallas även transport regler).</span><span class="sxs-lookup"><span data-stu-id="8122a-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="8122a-107">Andra sätt att skicka e-postmeddelanden, webb adresser och bilagor till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="8122a-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8122a-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="8122a-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8122a-109">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="8122a-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8122a-110">För att gå direkt till **sändnings** sidan, Använd <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="8122a-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="8122a-111">Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna för detta ämne:</span><span class="sxs-lookup"><span data-stu-id="8122a-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="8122a-112">För att skicka meddelanden och filer till Microsoft måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="8122a-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="8122a-113">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="8122a-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="8122a-114">**Organisationshantering** eller **Hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="8122a-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="8122a-115">Om du vill ha skrivskyddad åtkomst till portalen för att skicka objekt måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="8122a-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="8122a-116">**Säkerhetsläsare** i [Säkerhets- och efterlevnadscentret](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="8122a-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="8122a-117">**Skrivskyddad organisationshantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="8122a-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="8122a-118">Mer information om hur användarna kan skicka meddelanden och filer till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="8122a-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="8122a-119">Rapportera misstänkt innehåll till Microsoft</span><span class="sxs-lookup"><span data-stu-id="8122a-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="8122a-120">Gå till **Threat Management** på fliken säkerhet & efterlevnad \> **Review** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="8122a-120">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="8122a-121">Klicka på knappen **ny sändning** på sidan för **skickade inlägg** .</span><span class="sxs-lookup"><span data-stu-id="8122a-121">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="8122a-122">Använd **New submission** utfällbar text som visas för att skicka meddelandet, URL: en eller bifogad fil enligt beskrivningen i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="8122a-122">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="8122a-123">Skicka ett tveksamt e-postmeddelande till Microsoft</span><span class="sxs-lookup"><span data-stu-id="8122a-123">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="8122a-124">Välj **e-post**under **objekt typ** .</span><span class="sxs-lookup"><span data-stu-id="8122a-124">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="8122a-125">Använd något av följande alternativ i avsnittet **sändnings format** :</span><span class="sxs-lookup"><span data-stu-id="8122a-125">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="8122a-126">**Nätverks meddelande-ID**: det här är ett GUID-värde som är tillgängligt i huvudet **X-MS-Exchange-Organization-Network-meddelande-ID** i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="8122a-126">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="8122a-127">**Fil**: Klicka på **Välj fil**.</span><span class="sxs-lookup"><span data-stu-id="8122a-127">**File**: Click **Choose file**.</span></span> <span data-ttu-id="8122a-128">I dialog rutan som öppnas letar du reda på och markerar EML-eller MSG-filen och klickar sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="8122a-128">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="8122a-129">Ange en eller flera mottagare som du vill köra en princip kontroll för i avsnittet **mottagare** .</span><span class="sxs-lookup"><span data-stu-id="8122a-129">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="8122a-130">Princip kontrollen avgör om genomsökning av e-postmeddelandet kringgås på grund av principer för användare eller organisation.</span><span class="sxs-lookup"><span data-stu-id="8122a-130">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="8122a-131">Välj något av följande alternativ i avsnittet **orsak för inlämning** :</span><span class="sxs-lookup"><span data-stu-id="8122a-131">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="8122a-132">**Ska inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="8122a-132">**Should not have been blocked**</span></span>

   - <span data-ttu-id="8122a-133">**Bör ha blockerats**: Välj **skräp post**, **nätfiske**eller **skadlig program vara**.</span><span class="sxs-lookup"><span data-stu-id="8122a-133">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="8122a-134">Om du är osäker kan du använda ditt bästa omdöme.</span><span class="sxs-lookup"><span data-stu-id="8122a-134">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="8122a-135">Om filtret hoppades över på grund av principer vid överföring visas information om den policyn.</span><span class="sxs-lookup"><span data-stu-id="8122a-135">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="8122a-136">Om filtret inte har hoppats över på grund av en eller flera principer slutförs genomsökningen flera minuter.</span><span class="sxs-lookup"><span data-stu-id="8122a-136">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="8122a-137">Du får mer information om inlämningen genom att klicka på status länken.</span><span class="sxs-lookup"><span data-stu-id="8122a-137">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="8122a-138">Här ingår resultaten av princip kontrollen och omsökning Verdict.</span><span class="sxs-lookup"><span data-stu-id="8122a-138">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="8122a-139">OBS! detta kör inte e-postmeddelandet via Office 365 ATP-fullständig filtrerings stack igen men kör en delvis omsökning baserat på vissa av attributen för e-post, URL eller fil.</span><span class="sxs-lookup"><span data-stu-id="8122a-139">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="8122a-140">När du är klar klickar du på **Skicka** .</span><span class="sxs-lookup"><span data-stu-id="8122a-140">When you're finished, click the **Submit** button.</span></span>

![Exempel på skicka URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="8122a-142">Skicka en misstänkt URL till Microsoft</span><span class="sxs-lookup"><span data-stu-id="8122a-142">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="8122a-143">Välj **URL**under **objekt typ** .</span><span class="sxs-lookup"><span data-stu-id="8122a-143">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="8122a-144">I rutan som visas anger du den fullständiga URL: en (till exempel <https://www.fabrikam.com/marketing.html> ).</span><span class="sxs-lookup"><span data-stu-id="8122a-144">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="8122a-145">Välj något av följande alternativ i avsnittet **orsak för inlämning** :</span><span class="sxs-lookup"><span data-stu-id="8122a-145">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="8122a-146">**Ska inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="8122a-146">**Should not have been blocked**</span></span>

   - <span data-ttu-id="8122a-147">**Borde ha blockerats**: Välj **nätfiske** eller **malware**.</span><span class="sxs-lookup"><span data-stu-id="8122a-147">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="8122a-148">När du är klar klickar du på **Skicka** .</span><span class="sxs-lookup"><span data-stu-id="8122a-148">When you're finished, click the **Submit** button.</span></span>

![Exempel på Skicka e-post](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="8122a-150">Skicka en misstänkt fil till Microsoft</span><span class="sxs-lookup"><span data-stu-id="8122a-150">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="8122a-151">Välj **bilaga**under **objekt typ** .</span><span class="sxs-lookup"><span data-stu-id="8122a-151">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="8122a-152">Klicka på **Välj fil**.</span><span class="sxs-lookup"><span data-stu-id="8122a-152">Click **Choose File**.</span></span> <span data-ttu-id="8122a-153">Leta upp och markera filen i dialog rutan som öppnas och klicka sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="8122a-153">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="8122a-154">Välj något av följande alternativ i avsnittet **orsak för inlämning** :</span><span class="sxs-lookup"><span data-stu-id="8122a-154">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="8122a-155">**Ska inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="8122a-155">**Should not have been blocked**</span></span>

   - <span data-ttu-id="8122a-156">**Bör ha blockerats**: **malware** är det enda alternativet och väljs automatiskt...</span><span class="sxs-lookup"><span data-stu-id="8122a-156">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="8122a-157">När du är klar klickar du på **Skicka** .</span><span class="sxs-lookup"><span data-stu-id="8122a-157">When you're finished, click the **Submit** button.</span></span>

![Exempel på skicka bilagor](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="8122a-159">Visa administratörs inlämningar</span><span class="sxs-lookup"><span data-stu-id="8122a-159">View admin submissions</span></span>

1. <span data-ttu-id="8122a-160">Gå till **Threat Management** på fliken säkerhet & efterlevnad \> **Review** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="8122a-160">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="8122a-161">På sidan för att **Skicka** objekt som visas kontrollerar du att fliken **Administratörs överföringar** är markerad.</span><span class="sxs-lookup"><span data-stu-id="8122a-161">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="8122a-162">Högst upp på sidan kan du ange ett start datum, ett slutdatum och (som standard) som du kan filtrera efter **överförings-ID** (ett GUID-värde som är kopplat till varje överföring) genom att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="8122a-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="8122a-163">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="8122a-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="8122a-164">Om du vill ändra filter villkoren klickar du på knappen **Skicka ID** och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="8122a-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="8122a-165">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="8122a-165">**Sender**</span></span>
- <span data-ttu-id="8122a-166">**Ämne/URL/fil namn**</span><span class="sxs-lookup"><span data-stu-id="8122a-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="8122a-167">**Skickades av**</span><span class="sxs-lookup"><span data-stu-id="8122a-167">**Submitted by**</span></span>
- <span data-ttu-id="8122a-168">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="8122a-168">**Submission type**</span></span>
- <span data-ttu-id="8122a-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="8122a-169">**Status**</span></span>

![Filter alternativ för administratörs inlämning](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="8122a-171">Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**.</span><span class="sxs-lookup"><span data-stu-id="8122a-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="8122a-172">Spara CSV-filen i dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="8122a-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="8122a-173">Under grafen finns det tre flikar: **e-post** (standard), **URL**och **bifogad fil**.</span><span class="sxs-lookup"><span data-stu-id="8122a-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="8122a-174">Visa e-postinlägg för administratörer</span><span class="sxs-lookup"><span data-stu-id="8122a-174">View admin email submissions</span></span>

<span data-ttu-id="8122a-175">Klicka på fliken **e-post** .</span><span class="sxs-lookup"><span data-stu-id="8122a-175">Click the **Email** tab.</span></span>

<span data-ttu-id="8122a-176">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="8122a-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="8122a-177">**Datum**</span><span class="sxs-lookup"><span data-stu-id="8122a-177">**Date**</span></span>
- <span data-ttu-id="8122a-178">**Sändnings-ID**: ett GUID-värde som tilldelats varje överföring.</span><span class="sxs-lookup"><span data-stu-id="8122a-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="8122a-179">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8122a-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="8122a-180">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8122a-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="8122a-181">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="8122a-181">**Sender**</span></span>
- <span data-ttu-id="8122a-182">**Avsändarens IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8122a-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="8122a-183">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="8122a-183">**Submission type**</span></span>
- <span data-ttu-id="8122a-184">**Leverans orsak**</span><span class="sxs-lookup"><span data-stu-id="8122a-184">**Delivery reason**</span></span>
- <span data-ttu-id="8122a-185">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8122a-185">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="8122a-186">**Kontroll typ**</span><span class="sxs-lookup"><span data-stu-id="8122a-186">**Control type**</span></span>
- <span data-ttu-id="8122a-187">**Kontroll källa**</span><span class="sxs-lookup"><span data-stu-id="8122a-187">**Control source**</span></span>

  <span data-ttu-id="8122a-188"><sup>\*</sup>Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="8122a-188"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="8122a-189">Visa URL-överföringar för administratörer</span><span class="sxs-lookup"><span data-stu-id="8122a-189">View admin URL submissions</span></span>

<span data-ttu-id="8122a-190">Klicka på fliken **URL** .</span><span class="sxs-lookup"><span data-stu-id="8122a-190">Click the **URL** tab.</span></span>

<span data-ttu-id="8122a-191">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="8122a-191">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="8122a-192">**Datum**</span><span class="sxs-lookup"><span data-stu-id="8122a-192">**Date**</span></span>
- <span data-ttu-id="8122a-193">**Sändnings-ID**</span><span class="sxs-lookup"><span data-stu-id="8122a-193">**Submission ID**</span></span>
- <span data-ttu-id="8122a-194">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8122a-194">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="8122a-195">**:**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8122a-195">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="8122a-196">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="8122a-196">**Submission type**</span></span>
- <span data-ttu-id="8122a-197">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8122a-197">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="8122a-198"><sup>\*</sup>Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="8122a-198"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="8122a-199">Visa underlämning av administrativa bilagor</span><span class="sxs-lookup"><span data-stu-id="8122a-199">View admin attachment submissions</span></span>

<span data-ttu-id="8122a-200">Klicka på fliken **bifogade filer** .</span><span class="sxs-lookup"><span data-stu-id="8122a-200">Click the **Attachments** tab.</span></span>

<span data-ttu-id="8122a-201">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="8122a-201">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="8122a-202">**Datum**</span><span class="sxs-lookup"><span data-stu-id="8122a-202">**Date**</span></span>
- <span data-ttu-id="8122a-203">**Sändnings-ID**</span><span class="sxs-lookup"><span data-stu-id="8122a-203">**Submission ID**</span></span>
- <span data-ttu-id="8122a-204">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8122a-204">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="8122a-205">**Fil namn**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8122a-205">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="8122a-206">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="8122a-206">**Submission type**</span></span>
- <span data-ttu-id="8122a-207">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8122a-207">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="8122a-208"><sup>\*</sup>Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="8122a-208"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="8122a-209">Visa användar inlämningar till Microsoft</span><span class="sxs-lookup"><span data-stu-id="8122a-209">View user submissions to Microsoft</span></span>

<span data-ttu-id="8122a-210">Om du har distribuerat [tillägget för rapport meddelanden](enable-the-report-message-add-in.md), eller om personer använder den [inbyggda rapporteringen i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), kan du se vilka användare som rapporterar på fliken **användar överföringar** .</span><span class="sxs-lookup"><span data-stu-id="8122a-210">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="8122a-211">Gå till **Threat Management** på fliken säkerhet & efterlevnad \> **Review** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="8122a-211">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="8122a-212">På sidan för **skickade inlägg** klickar du på fliken **användar överföringar** .</span><span class="sxs-lookup"><span data-stu-id="8122a-212">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="8122a-213">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="8122a-213">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="8122a-214">**Skickades**</span><span class="sxs-lookup"><span data-stu-id="8122a-214">**Submitted on**</span></span>
- <span data-ttu-id="8122a-215">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8122a-215">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="8122a-216">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8122a-216">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="8122a-217">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="8122a-217">**Sender**</span></span>
- <span data-ttu-id="8122a-218">**Avsändarens IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8122a-218">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="8122a-219">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="8122a-219">**Submission type**</span></span>

<span data-ttu-id="8122a-220"><sup>\*</sup>Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="8122a-220"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="8122a-221">Högst upp på sidan kan du ange ett start datum, ett slutdatum och (som standard) som du kan filtrera efter **avsändare** genom att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="8122a-221">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="8122a-222">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="8122a-222">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="8122a-223">Om du vill ändra filter villkoren klickar du på knappen **avsändare** och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="8122a-223">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="8122a-224">**Avsändningsdomän**</span><span class="sxs-lookup"><span data-stu-id="8122a-224">**Sender domain**</span></span>
- <span data-ttu-id="8122a-225">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="8122a-225">**Subject**</span></span>
- <span data-ttu-id="8122a-226">**Skickades av**</span><span class="sxs-lookup"><span data-stu-id="8122a-226">**Submitted by**</span></span>
- <span data-ttu-id="8122a-227">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="8122a-227">**Submission type**</span></span>
- <span data-ttu-id="8122a-228">**Avsändarens IP**</span><span class="sxs-lookup"><span data-stu-id="8122a-228">**Sender IP**</span></span>

![Filter alternativ för användar inlämning](../../media/user-submissions-filter-options.png)

<span data-ttu-id="8122a-230">Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**.</span><span class="sxs-lookup"><span data-stu-id="8122a-230">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="8122a-231">Spara CSV-filen i dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="8122a-231">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="8122a-232">Visa användar inlämningar till den anpassade post lådan</span><span class="sxs-lookup"><span data-stu-id="8122a-232">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="8122a-233">Om du har [konfigurerat en egen post låda](user-submission.md) för att få användardefinierade meddelanden kan du Visa och även skicka meddelanden som har levererats till rapporterings post lådan.</span><span class="sxs-lookup"><span data-stu-id="8122a-233">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="8122a-234">Gå till **Threat Management** på fliken säkerhet & efterlevnad \> **Review** \> **Admin submission messages**.</span><span class="sxs-lookup"><span data-stu-id="8122a-234">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="8122a-235">På sidan för **skickade inlägg** klickar du på fliken **anpassad post låda** .</span><span class="sxs-lookup"><span data-stu-id="8122a-235">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="8122a-236">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="8122a-236">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="8122a-237">**Skickades**</span><span class="sxs-lookup"><span data-stu-id="8122a-237">**Submitted on**</span></span>
- <span data-ttu-id="8122a-238">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8122a-238">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="8122a-239">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8122a-239">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="8122a-240">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="8122a-240">**Sender**</span></span>
- <span data-ttu-id="8122a-241">**Avsändarens IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8122a-241">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="8122a-242">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="8122a-242">**Submission type**</span></span>

<span data-ttu-id="8122a-243">Högst upp på sidan kan du ange ett start datum, ett slutdatum och du kan **Filtrera efter genom** att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="8122a-243">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="8122a-244">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="8122a-244">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="8122a-245">Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**.</span><span class="sxs-lookup"><span data-stu-id="8122a-245">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="8122a-246">Spara CSV-filen i dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="8122a-246">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="8122a-247">Skicka meddelanden till Microsoft från den anpassade post lådan</span><span class="sxs-lookup"><span data-stu-id="8122a-247">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="8122a-248">Om du har konfigurerat den anpassade post lådan för att avlyssna användardefinierade meddelanden utan att skicka meddelanden till Microsoft kan du söka efter och skicka specifika meddelanden till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="8122a-248">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="8122a-249">Detta flyttar en användares överföring till en administratör.</span><span class="sxs-lookup"><span data-stu-id="8122a-249">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="8122a-250">På fliken **egen post låda** väljer du ett meddelande i listan, klickar på knappen **åtgärd** och gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="8122a-250">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="8122a-251">**Rapport klar**</span><span class="sxs-lookup"><span data-stu-id="8122a-251">**Report clean**</span></span>
- <span data-ttu-id="8122a-252">**Rapportera nätfiske**</span><span class="sxs-lookup"><span data-stu-id="8122a-252">**Report phishing**</span></span>
- <span data-ttu-id="8122a-253">**Rapportera skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="8122a-253">**Report malware**</span></span>
- <span data-ttu-id="8122a-254">**Rapportera skräp post**</span><span class="sxs-lookup"><span data-stu-id="8122a-254">**Report spam**</span></span>

![Alternativ på Åtgärds knappen](../../media/user-submission-custom-mailbox-action-button.png)
