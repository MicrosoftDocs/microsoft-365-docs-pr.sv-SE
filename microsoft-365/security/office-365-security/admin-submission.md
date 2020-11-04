---
title: Administratörs inlämningar
f1.keywords:
- NOCSH
ms.author: siosulli
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
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 'Administratörer kan läsa mer om hur du använder portalen för att skicka e-postmeddelanden, misstänkta nätfiske-meddelanden, skräp post och andra potentiellt skadligt meddelande, URL: er och filer till Microsoft för genomsökning i & den här gruppen.'
ms.openlocfilehash: be2fc8e41e3b53923b0297f30dfb102bbabd7489
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877273"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="c6e53-103">Använd administratörs sändning för att skicka misstänkt skräp post, Phish, URL: er och filer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="c6e53-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c6e53-104">I Microsoft 365-organisationer med post lådor i Exchange Online kan administratörer använda & portalen för att skicka e-postmeddelanden, URL: er och bifogade filer till Microsoft för att söka.</span><span class="sxs-lookup"><span data-stu-id="c6e53-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="c6e53-105">När du skickar ett e-postmeddelande får du information om eventuella principer som kan ha tillåtit inkommande e-post till din klient organisation samt granskning av URL: er och bilagor i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="c6e53-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="c6e53-106">Principer som kan ha tillåtelse till ett e-postmeddelande inkluderar en enskild användares lista över betrodda avsändare och policy principer för Exchange-flöden (kallas även transport regler).</span><span class="sxs-lookup"><span data-stu-id="c6e53-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="c6e53-107">Andra sätt att skicka e-postmeddelanden, webb adresser och bilagor till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="c6e53-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c6e53-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="c6e53-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c6e53-109">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c6e53-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c6e53-110">För att gå direkt till **sändnings** sidan, Använd <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="c6e53-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="c6e53-111">För att skicka meddelanden och filer till Microsoft måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="c6e53-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="c6e53-112">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c6e53-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="c6e53-113">**Organisations hantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="c6e53-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="c6e53-114">Observera att medlemskap i den här roll gruppen krävs för att [Visa användar överföringar till den anpassade post lådan](#view-user-submissions-to-the-custom-mailbox) enligt beskrivningen längre fram i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="c6e53-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="c6e53-115">Mer information om hur användarna kan skicka meddelanden och filer till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="c6e53-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="c6e53-116">Rapportera misstänkt innehåll till Microsoft</span><span class="sxs-lookup"><span data-stu-id="c6e53-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="c6e53-117">I säkerhets & Compliance Center går du till **Threat Management** -undersändningar \> **Submissions** , kontrollerar att du är på fliken **admin-överföring** och klickar sedan på **ny överföring**.</span><span class="sxs-lookup"><span data-stu-id="c6e53-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions** , verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="c6e53-118">Använd **New submission** utfällbar text som visas för att skicka meddelandet, URL: en eller bifogad fil enligt beskrivningen i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="c6e53-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="c6e53-119">Skicka ett tveksamt e-postmeddelande till Microsoft</span><span class="sxs-lookup"><span data-stu-id="c6e53-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="c6e53-120">Välj **e-post** under **objekt typ** .</span><span class="sxs-lookup"><span data-stu-id="c6e53-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="c6e53-121">Använd något av följande alternativ i avsnittet **sändnings format** :</span><span class="sxs-lookup"><span data-stu-id="c6e53-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="c6e53-122">**Nätverks meddelande-ID** : det här är ett GUID-värde som är tillgängligt i huvudet **X-MS-Exchange-Organization-Network-meddelande-ID** i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="c6e53-122">**Network Message ID** : This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="c6e53-123">**Fil** : Klicka på **Välj fil**.</span><span class="sxs-lookup"><span data-stu-id="c6e53-123">**File** : Click **Choose file**.</span></span> <span data-ttu-id="c6e53-124">I dialog rutan som öppnas letar du reda på och markerar EML-eller MSG-filen och klickar sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="c6e53-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="c6e53-125">Ange en eller flera mottagare som du vill köra en princip kontroll för i avsnittet **mottagare** .</span><span class="sxs-lookup"><span data-stu-id="c6e53-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="c6e53-126">Princip kontrollen avgör om genomsökning av e-postmeddelandet kringgås på grund av principer för användare eller organisation.</span><span class="sxs-lookup"><span data-stu-id="c6e53-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="c6e53-127">Välj något av följande alternativ i avsnittet **orsak för inlämning** :</span><span class="sxs-lookup"><span data-stu-id="c6e53-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="c6e53-128">**Ska inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="c6e53-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="c6e53-129">**Bör ha blockerats** : Välj **skräp post** , **nätfiske** eller **skadlig program vara**.</span><span class="sxs-lookup"><span data-stu-id="c6e53-129">**Should have been blocked** : Select **Spam** , **Phishing** , or **Malware**.</span></span> <span data-ttu-id="c6e53-130">Om du är osäker kan du använda ditt bästa omdöme.</span><span class="sxs-lookup"><span data-stu-id="c6e53-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="c6e53-131">Om filtret hoppades över på grund av principer vid överföring visas information om den policyn.</span><span class="sxs-lookup"><span data-stu-id="c6e53-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="c6e53-132">Om filtret inte har hoppats över på grund av en eller flera principer slutförs genomsökningen flera minuter.</span><span class="sxs-lookup"><span data-stu-id="c6e53-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="c6e53-133">Du får mer information om inlämningen genom att klicka på status länken.</span><span class="sxs-lookup"><span data-stu-id="c6e53-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="c6e53-134">Här ingår resultaten av princip kontrollen och omsökning Verdict.</span><span class="sxs-lookup"><span data-stu-id="c6e53-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="c6e53-135">OBS! detta kör inte e-postmeddelandet via Microsoft Defender för Office 365 full filtrerings stack igen men kör delvis omsökning baserat på vissa av attributen för e-post, URL eller fil.</span><span class="sxs-lookup"><span data-stu-id="c6e53-135">Note this does not run the email through the Microsoft Defender for Office 365 full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="c6e53-136">När du är klar klickar du på **Skicka** .</span><span class="sxs-lookup"><span data-stu-id="c6e53-136">When you're finished, click the **Submit** button.</span></span>

![Exempel på skicka URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="c6e53-138">Skicka en misstänkt URL till Microsoft</span><span class="sxs-lookup"><span data-stu-id="c6e53-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="c6e53-139">Välj **URL** under **objekt typ** .</span><span class="sxs-lookup"><span data-stu-id="c6e53-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="c6e53-140">I rutan som visas anger du den fullständiga URL: en (till exempel `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="c6e53-140">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="c6e53-141">Välj något av följande alternativ i avsnittet **orsak för inlämning** :</span><span class="sxs-lookup"><span data-stu-id="c6e53-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="c6e53-142">**Ska inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="c6e53-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="c6e53-143">**Borde ha blockerats** : Välj **nätfiske** eller **malware**.</span><span class="sxs-lookup"><span data-stu-id="c6e53-143">**Should have been blocked** : Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="c6e53-144">När du är klar klickar du på **Skicka** .</span><span class="sxs-lookup"><span data-stu-id="c6e53-144">When you're finished, click the **Submit** button.</span></span>

![Exempel på Skicka e-post](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="c6e53-146">Skicka en misstänkt fil till Microsoft</span><span class="sxs-lookup"><span data-stu-id="c6e53-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="c6e53-147">Välj **bilaga** under **objekt typ** .</span><span class="sxs-lookup"><span data-stu-id="c6e53-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="c6e53-148">Klicka på **Välj fil**.</span><span class="sxs-lookup"><span data-stu-id="c6e53-148">Click **Choose File**.</span></span> <span data-ttu-id="c6e53-149">Leta upp och markera filen i dialog rutan som öppnas och klicka sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="c6e53-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="c6e53-150">Välj något av följande alternativ i avsnittet **orsak för inlämning** :</span><span class="sxs-lookup"><span data-stu-id="c6e53-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="c6e53-151">**Ska inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="c6e53-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="c6e53-152">**Bör ha blockerats** : **malware** är det enda alternativet och väljs automatiskt...</span><span class="sxs-lookup"><span data-stu-id="c6e53-152">**Should have been blocked** : **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="c6e53-153">När du är klar klickar du på **Skicka** .</span><span class="sxs-lookup"><span data-stu-id="c6e53-153">When you're finished, click the **Submit** button.</span></span>

![Exempel på skicka bilagor](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="c6e53-155">Visa administratörs inlämningar</span><span class="sxs-lookup"><span data-stu-id="c6e53-155">View admin submissions</span></span>

<span data-ttu-id="c6e53-156">I säkerhets & Compliance Center går du till **Threat Management** -undersändningar \> **Submissions** , kontrollerar att du är på fliken **admin-överföring** och klickar sedan på **ny överföring**.</span><span class="sxs-lookup"><span data-stu-id="c6e53-156">In the Security & Compliance Center, go to **Threat management** \> **Submissions** , verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="c6e53-157">Högst upp på sidan kan du ange ett start datum, ett slutdatum och (som standard) som du kan filtrera efter **överförings-ID** (ett GUID-värde som är kopplat till varje överföring) genom att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="c6e53-157">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="c6e53-158">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="c6e53-158">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="c6e53-159">Om du vill ändra filter villkoren klickar du på knappen **Skicka ID** och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="c6e53-159">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="c6e53-160">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="c6e53-160">**Sender**</span></span>
- <span data-ttu-id="c6e53-161">**Ämne/URL/fil namn**</span><span class="sxs-lookup"><span data-stu-id="c6e53-161">**Subject/URL/File name**</span></span>
- <span data-ttu-id="c6e53-162">**Skickades av**</span><span class="sxs-lookup"><span data-stu-id="c6e53-162">**Submitted by**</span></span>
- <span data-ttu-id="c6e53-163">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="c6e53-163">**Submission type**</span></span>
- <span data-ttu-id="c6e53-164">**Status**</span><span class="sxs-lookup"><span data-stu-id="c6e53-164">**Status**</span></span>

![Filter alternativ för administratörs inlämning](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="c6e53-166">Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**.</span><span class="sxs-lookup"><span data-stu-id="c6e53-166">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="c6e53-167">Spara CSV-filen i dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="c6e53-167">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="c6e53-168">Under grafen finns det tre flikar: **e-post** (standard), **URL** och **bifogad fil**.</span><span class="sxs-lookup"><span data-stu-id="c6e53-168">Below the graph, there are three tabs: **Email** (default), **URL** , and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="c6e53-169">Visa e-postinlägg för administratörer</span><span class="sxs-lookup"><span data-stu-id="c6e53-169">View admin email submissions</span></span>

<span data-ttu-id="c6e53-170">Klicka på fliken **e-post** .</span><span class="sxs-lookup"><span data-stu-id="c6e53-170">Click the **Email** tab.</span></span>

<span data-ttu-id="c6e53-171">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="c6e53-171">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c6e53-172">**Datum**</span><span class="sxs-lookup"><span data-stu-id="c6e53-172">**Date**</span></span>
- <span data-ttu-id="c6e53-173">**Sändnings-ID** : ett GUID-värde som tilldelats varje överföring.</span><span class="sxs-lookup"><span data-stu-id="c6e53-173">**Submission ID** : A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="c6e53-174">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c6e53-174">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c6e53-175">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c6e53-175">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="c6e53-176">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="c6e53-176">**Sender**</span></span>
- <span data-ttu-id="c6e53-177">**Avsändarens IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c6e53-177">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="c6e53-178">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="c6e53-178">**Submission type**</span></span>
- <span data-ttu-id="c6e53-179">**Leverans orsak**</span><span class="sxs-lookup"><span data-stu-id="c6e53-179">**Delivery reason**</span></span>
- <span data-ttu-id="c6e53-180">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c6e53-180">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="c6e53-181">**Kontroll typ**</span><span class="sxs-lookup"><span data-stu-id="c6e53-181">**Control type**</span></span>
- <span data-ttu-id="c6e53-182">**Kontroll källa**</span><span class="sxs-lookup"><span data-stu-id="c6e53-182">**Control source**</span></span>

  <span data-ttu-id="c6e53-183"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="c6e53-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="c6e53-184">Visa URL-överföringar för administratörer</span><span class="sxs-lookup"><span data-stu-id="c6e53-184">View admin URL submissions</span></span>

<span data-ttu-id="c6e53-185">Klicka på fliken **URL** .</span><span class="sxs-lookup"><span data-stu-id="c6e53-185">Click the **URL** tab.</span></span>

<span data-ttu-id="c6e53-186">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="c6e53-186">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c6e53-187">**Datum**</span><span class="sxs-lookup"><span data-stu-id="c6e53-187">**Date**</span></span>
- <span data-ttu-id="c6e53-188">**Sändnings-ID**</span><span class="sxs-lookup"><span data-stu-id="c6e53-188">**Submission ID**</span></span>
- <span data-ttu-id="c6e53-189">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c6e53-189">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c6e53-190">**:**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c6e53-190">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="c6e53-191">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="c6e53-191">**Submission type**</span></span>
- <span data-ttu-id="c6e53-192">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c6e53-192">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="c6e53-193"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="c6e53-193"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="c6e53-194">Visa underlämning av administrativa bilagor</span><span class="sxs-lookup"><span data-stu-id="c6e53-194">View admin attachment submissions</span></span>

<span data-ttu-id="c6e53-195">Klicka på fliken **bifogade filer** .</span><span class="sxs-lookup"><span data-stu-id="c6e53-195">Click the **Attachments** tab.</span></span>

<span data-ttu-id="c6e53-196">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="c6e53-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c6e53-197">**Datum**</span><span class="sxs-lookup"><span data-stu-id="c6e53-197">**Date**</span></span>
- <span data-ttu-id="c6e53-198">**Sändnings-ID**</span><span class="sxs-lookup"><span data-stu-id="c6e53-198">**Submission ID**</span></span>
- <span data-ttu-id="c6e53-199">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c6e53-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c6e53-200">**Fil namn**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c6e53-200">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="c6e53-201">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="c6e53-201">**Submission type**</span></span>
- <span data-ttu-id="c6e53-202">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c6e53-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="c6e53-203"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="c6e53-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="c6e53-204">Visa användar inlämningar till Microsoft</span><span class="sxs-lookup"><span data-stu-id="c6e53-204">View user submissions to Microsoft</span></span>

<span data-ttu-id="c6e53-205">Om du har distribuerat [tillägget för rapport meddelanden](enable-the-report-message-add-in.md), eller om personer använder den [inbyggda rapporteringen i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), kan du se vilka användare som rapporterar på fliken **användar överföringar** .</span><span class="sxs-lookup"><span data-stu-id="c6e53-205">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="c6e53-206">I säkerhets & Compliance Center går du till **Threat Management** - \> **inlämningar**.</span><span class="sxs-lookup"><span data-stu-id="c6e53-206">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="c6e53-207">Välj fliken **användar överföringar** och klicka sedan på **ny överföring**.</span><span class="sxs-lookup"><span data-stu-id="c6e53-207">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="c6e53-208">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="c6e53-208">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c6e53-209">**Skickades**</span><span class="sxs-lookup"><span data-stu-id="c6e53-209">**Submitted on**</span></span>
- <span data-ttu-id="c6e53-210">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c6e53-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c6e53-211">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c6e53-211">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="c6e53-212">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="c6e53-212">**Sender**</span></span>
- <span data-ttu-id="c6e53-213">**Avsändarens IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c6e53-213">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="c6e53-214">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="c6e53-214">**Submission type**</span></span>

<span data-ttu-id="c6e53-215"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="c6e53-215"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="c6e53-216">Högst upp på sidan kan du ange ett start datum, ett slutdatum och (som standard) som du kan filtrera efter **avsändare** genom att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="c6e53-216">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="c6e53-217">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="c6e53-217">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="c6e53-218">Om du vill ändra filter villkoren klickar du på knappen **avsändare** och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="c6e53-218">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="c6e53-219">**Avsändningsdomän**</span><span class="sxs-lookup"><span data-stu-id="c6e53-219">**Sender domain**</span></span>
- <span data-ttu-id="c6e53-220">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="c6e53-220">**Subject**</span></span>
- <span data-ttu-id="c6e53-221">**Skickades av**</span><span class="sxs-lookup"><span data-stu-id="c6e53-221">**Submitted by**</span></span>
- <span data-ttu-id="c6e53-222">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="c6e53-222">**Submission type**</span></span>
- <span data-ttu-id="c6e53-223">**Avsändarens IP**</span><span class="sxs-lookup"><span data-stu-id="c6e53-223">**Sender IP**</span></span>

![Filter alternativ för användar inlämning](../../media/user-submissions-filter-options.png)

<span data-ttu-id="c6e53-225">Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**.</span><span class="sxs-lookup"><span data-stu-id="c6e53-225">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="c6e53-226">Spara CSV-filen i dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="c6e53-226">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="c6e53-227">Visa användar inlämningar till den anpassade post lådan</span><span class="sxs-lookup"><span data-stu-id="c6e53-227">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="c6e53-228">**Om** du har [konfigurerat en egen post låda](user-submission.md) för att få användardefinierade meddelanden kan du Visa och även skicka meddelanden som har levererats till rapporterings post lådan.</span><span class="sxs-lookup"><span data-stu-id="c6e53-228">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="c6e53-229">I säkerhets & Compliance Center går du till **Threat Management** - \> **inlämningar**.</span><span class="sxs-lookup"><span data-stu-id="c6e53-229">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="c6e53-230">Välj fliken **egen post låda** .</span><span class="sxs-lookup"><span data-stu-id="c6e53-230">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="c6e53-231">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="c6e53-231">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="c6e53-232">**Skickades**</span><span class="sxs-lookup"><span data-stu-id="c6e53-232">**Submitted on**</span></span>
- <span data-ttu-id="c6e53-233">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c6e53-233">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="c6e53-234">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c6e53-234">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="c6e53-235">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="c6e53-235">**Sender**</span></span>
- <span data-ttu-id="c6e53-236">**Avsändarens IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c6e53-236">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="c6e53-237">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="c6e53-237">**Submission type**</span></span>

<span data-ttu-id="c6e53-238">Högst upp på sidan kan du ange ett start datum, ett slutdatum och du kan **Filtrera efter genom** att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="c6e53-238">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="c6e53-239">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="c6e53-239">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="c6e53-240">Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**.</span><span class="sxs-lookup"><span data-stu-id="c6e53-240">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="c6e53-241">Spara CSV-filen i dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="c6e53-241">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="c6e53-242">Ångra användar inlägg</span><span class="sxs-lookup"><span data-stu-id="c6e53-242">Undo user submissions</span></span>

<span data-ttu-id="c6e53-243">När en användare skickar ett misstänkt e-postmeddelande till den anpassade post lådan har användaren och administratören inget alternativ för att ångra sändningen.</span><span class="sxs-lookup"><span data-stu-id="c6e53-243">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="c6e53-244">Om användaren vill återställa e-postmeddelandet kommer den att vara tillgänglig för återställning i mapparna Borttaget eller skräp post.</span><span class="sxs-lookup"><span data-stu-id="c6e53-244">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span> 

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="c6e53-245">Skicka meddelanden till Microsoft från den anpassade post lådan</span><span class="sxs-lookup"><span data-stu-id="c6e53-245">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="c6e53-246">Om du har konfigurerat den anpassade post lådan för att avlyssna användardefinierade meddelanden utan att skicka meddelanden till Microsoft kan du söka efter och skicka specifika meddelanden till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="c6e53-246">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="c6e53-247">Detta flyttar en användares överföring till en administratör.</span><span class="sxs-lookup"><span data-stu-id="c6e53-247">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="c6e53-248">På fliken **egen post låda** väljer du ett meddelande i listan, klickar på knappen **åtgärd** och gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="c6e53-248">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="c6e53-249">**Rapport klar**</span><span class="sxs-lookup"><span data-stu-id="c6e53-249">**Report clean**</span></span>
- <span data-ttu-id="c6e53-250">**Rapportera nätfiske**</span><span class="sxs-lookup"><span data-stu-id="c6e53-250">**Report phishing**</span></span>
- <span data-ttu-id="c6e53-251">**Rapportera skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="c6e53-251">**Report malware**</span></span>
- <span data-ttu-id="c6e53-252">**Rapportera skräp post**</span><span class="sxs-lookup"><span data-stu-id="c6e53-252">**Report spam**</span></span>

![Alternativ på Åtgärds knappen](../../media/user-submission-custom-mailbox-action-button.png)
