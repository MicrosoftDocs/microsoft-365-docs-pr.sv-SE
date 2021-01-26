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
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 'Administratörer kan läsa mer om hur du använder portalen för att skicka e-postmeddelanden, misstänkta nätfiske-meddelanden, skräp post och andra potentiellt skadligt meddelande, URL: er och filer till Microsoft för genomsökning i & den här gruppen.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 879a13e7c059495e653b79c424b227fe9f35a498
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976609"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="3e58e-103">Använd administratörs sändning för att skicka misstänkt skräp post, Phish, URL: er och filer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="3e58e-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3e58e-104">I Microsoft 365-organisationer med post lådor i Exchange Online kan administratörer använda & portalen för att skicka e-postmeddelanden, URL: er och bifogade filer till Microsoft för att söka.</span><span class="sxs-lookup"><span data-stu-id="3e58e-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="3e58e-105">När du skickar ett e-postmeddelande får du:</span><span class="sxs-lookup"><span data-stu-id="3e58e-105">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="3e58e-106">**Kontrol lera e-postauktorisering**: information om huruvida e-postauktoriseringen lyckades eller misslyckades när den levererades.</span><span class="sxs-lookup"><span data-stu-id="3e58e-106">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="3e58e-107">**Princip träffar**: information om eventuella principer som kan ha tillåtit eller blockera inkommande e-post till din klient organisation och Åsidosätt vårt service filter verdicts.</span><span class="sxs-lookup"><span data-stu-id="3e58e-107">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="3e58e-108">**Nytto lastens rykte/spränghet**: undersökning av URL-adresser och bilagor i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="3e58e-108">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="3e58e-109">**Kurs analys**: granska gjorda av de mänskliga betygen för att bekräfta att meddelanden är skadliga.</span><span class="sxs-lookup"><span data-stu-id="3e58e-109">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e58e-110">Nytto lastens rykte/Spräng och betygs analyser utförs inte hos alla klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="3e58e-110">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="3e58e-111">Informationen blockeras från att gå utanför organisationen när data inte förväntas lämna klient organisationens gräns för efterlevnad.</span><span class="sxs-lookup"><span data-stu-id="3e58e-111">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="3e58e-112">Andra sätt att skicka e-postmeddelanden, webb adresser och bilagor till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="3e58e-112">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3e58e-113">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="3e58e-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3e58e-114">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="3e58e-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3e58e-115">För att gå direkt till **sändnings** sidan, Använd <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="3e58e-115">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="3e58e-116">För att skicka meddelanden och filer till Microsoft måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="3e58e-116">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="3e58e-117">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3e58e-117">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="3e58e-118">**Organisations hantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="3e58e-118">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="3e58e-119">Observera att medlemskap i den här roll gruppen krävs för att [Visa användar överföringar till den anpassade post lådan](#view-user-submissions-to-the-custom-mailbox) enligt beskrivningen längre ned i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="3e58e-119">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="3e58e-120">Mer information om hur användarna kan skicka meddelanden och filer till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="3e58e-120">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="3e58e-121">Rapportera misstänkt innehåll till Microsoft</span><span class="sxs-lookup"><span data-stu-id="3e58e-121">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="3e58e-122">I säkerhets & Compliance Center går du till **Threat Management** -undersändningar \> , kontrollerar att du är på fliken **admin-överföring** och klickar sedan på **ny överföring**.</span><span class="sxs-lookup"><span data-stu-id="3e58e-122">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="3e58e-123">Använd  utfällbar text som visas för att skicka meddelandet, URL: en eller bifogad fil enligt beskrivningen i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="3e58e-123">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="3e58e-124">Skicka ett tveksamt e-postmeddelande till Microsoft</span><span class="sxs-lookup"><span data-stu-id="3e58e-124">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="3e58e-125">Välj **e-post** under **objekt typ** .</span><span class="sxs-lookup"><span data-stu-id="3e58e-125">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="3e58e-126">Använd något av följande alternativ i avsnittet **sändnings format** :</span><span class="sxs-lookup"><span data-stu-id="3e58e-126">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="3e58e-127">**ID för nätverks meddelande**: det här är ett GUID-värde som är tillgängligt i huvudet **x-MS-Exchange-Organization-Network-meddelande-ID** i meddelandet, eller i **X-MS-Office365**</span><span class="sxs-lookup"><span data-stu-id="3e58e-127">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="3e58e-128">**Fil**: Klicka på **Välj fil**.</span><span class="sxs-lookup"><span data-stu-id="3e58e-128">**File**: Click **Choose file**.</span></span> <span data-ttu-id="3e58e-129">I dialog rutan som öppnas letar du reda på och markerar EML-eller MSG-filen och klickar sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="3e58e-129">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3e58e-130">Administratörer med Defender för Office 365 abonnemang 1 eller abonnemang 2 kan skicka meddelanden som gamla 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="3e58e-130">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="3e58e-131">Andra administratörer kan bara gå tillbaka sju dagar.</span><span class="sxs-lookup"><span data-stu-id="3e58e-131">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="3e58e-132">Ange en eller flera mottagare som du vill köra en princip kontroll för i avsnittet **mottagare** .</span><span class="sxs-lookup"><span data-stu-id="3e58e-132">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="3e58e-133">Princip kontrollen avgör om genomsökning av e-postmeddelandet kringgås på grund av principer för användare eller organisation.</span><span class="sxs-lookup"><span data-stu-id="3e58e-133">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="3e58e-134">Välj något av följande alternativ i avsnittet **orsak för inlämning** :</span><span class="sxs-lookup"><span data-stu-id="3e58e-134">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="3e58e-135">**Ska inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="3e58e-135">**Should not have been blocked**</span></span>

   - <span data-ttu-id="3e58e-136">**Bör ha blockerats**: Välj **skräp post**, **nätfiske** eller **skadlig program vara**.</span><span class="sxs-lookup"><span data-stu-id="3e58e-136">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="3e58e-137">Om du är osäker kan du använda ditt bästa omdöme.</span><span class="sxs-lookup"><span data-stu-id="3e58e-137">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="3e58e-138">När du är klar klickar du på **Skicka** .</span><span class="sxs-lookup"><span data-stu-id="3e58e-138">When you're finished, click the **Submit** button.</span></span>

   ![Exempel på skicka URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="3e58e-140">Skicka en misstänkt URL till Microsoft</span><span class="sxs-lookup"><span data-stu-id="3e58e-140">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="3e58e-141">Välj **URL** under **objekt typ** .</span><span class="sxs-lookup"><span data-stu-id="3e58e-141">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="3e58e-142">I rutan som visas anger du den fullständiga URL: en (till exempel `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="3e58e-142">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="3e58e-143">Välj något av följande alternativ i avsnittet **orsak för inlämning** :</span><span class="sxs-lookup"><span data-stu-id="3e58e-143">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="3e58e-144">**Ska inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="3e58e-144">**Should not have been blocked**</span></span>

   - <span data-ttu-id="3e58e-145">**Borde ha blockerats**: Välj **nätfiske** eller **malware**.</span><span class="sxs-lookup"><span data-stu-id="3e58e-145">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="3e58e-146">När du är klar klickar du på **Skicka** .</span><span class="sxs-lookup"><span data-stu-id="3e58e-146">When you're finished, click the **Submit** button.</span></span>

   ![Exempel på Skicka e-post](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="3e58e-148">Skicka en misstänkt fil till Microsoft</span><span class="sxs-lookup"><span data-stu-id="3e58e-148">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="3e58e-149">Välj **bilaga** under **objekt typ** .</span><span class="sxs-lookup"><span data-stu-id="3e58e-149">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="3e58e-150">Klicka på **Välj fil**.</span><span class="sxs-lookup"><span data-stu-id="3e58e-150">Click **Choose File**.</span></span> <span data-ttu-id="3e58e-151">Leta upp och markera filen i dialog rutan som öppnas och klicka sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="3e58e-151">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="3e58e-152">Välj något av följande alternativ i avsnittet **orsak för inlämning** :</span><span class="sxs-lookup"><span data-stu-id="3e58e-152">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="3e58e-153">**Ska inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="3e58e-153">**Should not have been blocked**</span></span>

   - <span data-ttu-id="3e58e-154">**Bör ha blockerats**: **malware** är det enda alternativet och väljs automatiskt...</span><span class="sxs-lookup"><span data-stu-id="3e58e-154">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="3e58e-155">När du är klar klickar du på **Skicka** .</span><span class="sxs-lookup"><span data-stu-id="3e58e-155">When you're finished, click the **Submit** button.</span></span>

   ![Exempel på skicka bilagor](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="3e58e-157">Visa administratörs inlämningar</span><span class="sxs-lookup"><span data-stu-id="3e58e-157">View admin submissions</span></span>

<span data-ttu-id="3e58e-158">I säkerhets & Compliance Center går du till **Threat Management** -undersändningar \> , kontrollerar att du är på fliken **admin-överföring** och klickar sedan på **ny överföring**.</span><span class="sxs-lookup"><span data-stu-id="3e58e-158">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="3e58e-159">Högst upp på sidan kan du ange ett start datum, ett slutdatum och (som standard) som du kan filtrera efter **överförings-ID** (ett GUID-värde som är kopplat till varje överföring) genom att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="3e58e-159">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="3e58e-160">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="3e58e-160">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="3e58e-161">Om du vill ändra filter villkoren klickar du på knappen **Skicka ID** och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="3e58e-161">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="3e58e-162">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="3e58e-162">**Sender**</span></span>
- <span data-ttu-id="3e58e-163">**Ämne/URL/fil namn**</span><span class="sxs-lookup"><span data-stu-id="3e58e-163">**Subject/URL/File name**</span></span>
- <span data-ttu-id="3e58e-164">**Skickades av**</span><span class="sxs-lookup"><span data-stu-id="3e58e-164">**Submitted by**</span></span>
- <span data-ttu-id="3e58e-165">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="3e58e-165">**Submission type**</span></span>
- <span data-ttu-id="3e58e-166">**Status**</span><span class="sxs-lookup"><span data-stu-id="3e58e-166">**Status**</span></span>

![Filter alternativ för administratörs inlämning](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="3e58e-168">Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**.</span><span class="sxs-lookup"><span data-stu-id="3e58e-168">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="3e58e-169">Spara CSV-filen i dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="3e58e-169">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="3e58e-170">Under grafen finns det tre flikar: **e-post** (standard), **URL** och **bifogad fil**.</span><span class="sxs-lookup"><span data-stu-id="3e58e-170">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="3e58e-171">Visa e-postinlägg för administratörer</span><span class="sxs-lookup"><span data-stu-id="3e58e-171">View admin email submissions</span></span>

<span data-ttu-id="3e58e-172">Klicka på fliken **e-post** .</span><span class="sxs-lookup"><span data-stu-id="3e58e-172">Click the **Email** tab.</span></span>

<span data-ttu-id="3e58e-173">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="3e58e-173">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3e58e-174">**Datum**</span><span class="sxs-lookup"><span data-stu-id="3e58e-174">**Date**</span></span>
- <span data-ttu-id="3e58e-175">**Sändnings-ID**: ett GUID-värde som tilldelats varje överföring.</span><span class="sxs-lookup"><span data-stu-id="3e58e-175">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="3e58e-176">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e58e-176">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3e58e-177">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e58e-177">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="3e58e-178">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="3e58e-178">**Sender**</span></span>
- <span data-ttu-id="3e58e-179">**Avsändarens IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e58e-179">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="3e58e-180">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="3e58e-180">**Submission type**</span></span>
- <span data-ttu-id="3e58e-181">**Leverans orsak**</span><span class="sxs-lookup"><span data-stu-id="3e58e-181">**Delivery reason**</span></span>
- <span data-ttu-id="3e58e-182">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e58e-182">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="3e58e-183"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="3e58e-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="3e58e-184">Information om att söka efter administratörs uppgifter</span><span class="sxs-lookup"><span data-stu-id="3e58e-184">Admin submission rescan details</span></span>

<span data-ttu-id="3e58e-185">Meddelanden som skickas i administratörs inlämningar skannas in och visas i den utfällbara informationen:</span><span class="sxs-lookup"><span data-stu-id="3e58e-185">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="3e58e-186">Om det uppstod ett fel i avsändarens e-postautentisering vid leverans tillfället.</span><span class="sxs-lookup"><span data-stu-id="3e58e-186">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="3e58e-187">Information om eventuella policy träffar som kan ha påverkat eller åsidosatt Verdict av ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="3e58e-187">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="3e58e-188">Aktuella Spräng resultat för att se om URL-adresserna eller filerna i meddelandet är skadliga eller inte.</span><span class="sxs-lookup"><span data-stu-id="3e58e-188">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="3e58e-189">Feedback från betyg.</span><span class="sxs-lookup"><span data-stu-id="3e58e-189">Feedback from graders.</span></span>

<span data-ttu-id="3e58e-190">Om en åsidosättning hittas måste genomsökningen genomföras flera minuter.</span><span class="sxs-lookup"><span data-stu-id="3e58e-190">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="3e58e-191">Om det inte fanns något problem med e-postauktorisering eller leveransen påverkas inte av en åsidosättning och feedback från betyg kan ta upp till en dag.</span><span class="sxs-lookup"><span data-stu-id="3e58e-191">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="3e58e-192">Visa URL-överföringar för administratörer</span><span class="sxs-lookup"><span data-stu-id="3e58e-192">View admin URL submissions</span></span>

<span data-ttu-id="3e58e-193">Klicka på fliken **URL** .</span><span class="sxs-lookup"><span data-stu-id="3e58e-193">Click the **URL** tab.</span></span>

<span data-ttu-id="3e58e-194">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="3e58e-194">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3e58e-195">**Datum**</span><span class="sxs-lookup"><span data-stu-id="3e58e-195">**Date**</span></span>
- <span data-ttu-id="3e58e-196">**Sändnings-ID**</span><span class="sxs-lookup"><span data-stu-id="3e58e-196">**Submission ID**</span></span>
- <span data-ttu-id="3e58e-197">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e58e-197">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3e58e-198">**:**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e58e-198">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="3e58e-199">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="3e58e-199">**Submission type**</span></span>
- <span data-ttu-id="3e58e-200">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e58e-200">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="3e58e-201"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="3e58e-201"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="3e58e-202">Visa underlämning av administrativa bilagor</span><span class="sxs-lookup"><span data-stu-id="3e58e-202">View admin attachment submissions</span></span>

<span data-ttu-id="3e58e-203">Klicka på fliken **bifogade filer** .</span><span class="sxs-lookup"><span data-stu-id="3e58e-203">Click the **Attachments** tab.</span></span>

<span data-ttu-id="3e58e-204">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="3e58e-204">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3e58e-205">**Datum**</span><span class="sxs-lookup"><span data-stu-id="3e58e-205">**Date**</span></span>
- <span data-ttu-id="3e58e-206">**Sändnings-ID**</span><span class="sxs-lookup"><span data-stu-id="3e58e-206">**Submission ID**</span></span>
- <span data-ttu-id="3e58e-207">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e58e-207">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3e58e-208">**Fil namn**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e58e-208">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="3e58e-209">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="3e58e-209">**Submission type**</span></span>
- <span data-ttu-id="3e58e-210">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e58e-210">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="3e58e-211"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="3e58e-211"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="3e58e-212">Visa användar inlämningar till Microsoft</span><span class="sxs-lookup"><span data-stu-id="3e58e-212">View user submissions to Microsoft</span></span>

<span data-ttu-id="3e58e-213">Om du har distribuerat [tillägget rapportera](enable-the-report-message-add-in.md)tillägget rapport- [nätfiske](enable-the-report-phish-add-in.md)eller personer som använder den [inbyggda rapporteringen i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)kan du se vilka användare som rapporterar på fliken **användar överföringar** .</span><span class="sxs-lookup"><span data-stu-id="3e58e-213">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="3e58e-214">I säkerhets & Compliance Center går du till **Threat Management** - \> **inlämningar**.</span><span class="sxs-lookup"><span data-stu-id="3e58e-214">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="3e58e-215">Välj fliken **användar överföringar** och klicka sedan på **ny överföring**.</span><span class="sxs-lookup"><span data-stu-id="3e58e-215">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="3e58e-216">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="3e58e-216">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3e58e-217">**Skickades**</span><span class="sxs-lookup"><span data-stu-id="3e58e-217">**Submitted on**</span></span>
- <span data-ttu-id="3e58e-218">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e58e-218">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3e58e-219">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e58e-219">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="3e58e-220">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="3e58e-220">**Sender**</span></span>
- <span data-ttu-id="3e58e-221">**Avsändarens IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e58e-221">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="3e58e-222">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="3e58e-222">**Submission type**</span></span>

<span data-ttu-id="3e58e-223"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="3e58e-223"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="3e58e-224">Högst upp på sidan kan du ange ett start datum, ett slutdatum och (som standard) som du kan filtrera efter **avsändare** genom att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="3e58e-224">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="3e58e-225">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="3e58e-225">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="3e58e-226">Om du vill ändra filter villkoren klickar du på knappen **avsändare** och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="3e58e-226">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="3e58e-227">**Avsändningsdomän**</span><span class="sxs-lookup"><span data-stu-id="3e58e-227">**Sender domain**</span></span>
- <span data-ttu-id="3e58e-228">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="3e58e-228">**Subject**</span></span>
- <span data-ttu-id="3e58e-229">**Skickades av**</span><span class="sxs-lookup"><span data-stu-id="3e58e-229">**Submitted by**</span></span>
- <span data-ttu-id="3e58e-230">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="3e58e-230">**Submission type**</span></span>
- <span data-ttu-id="3e58e-231">**Avsändarens IP**</span><span class="sxs-lookup"><span data-stu-id="3e58e-231">**Sender IP**</span></span>

![Filter alternativ för användar inlämning](../../media/user-submissions-filter-options.png)

<span data-ttu-id="3e58e-233">Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**.</span><span class="sxs-lookup"><span data-stu-id="3e58e-233">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="3e58e-234">Spara CSV-filen i dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="3e58e-234">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="3e58e-235">Visa användar inlämningar till den anpassade post lådan</span><span class="sxs-lookup"><span data-stu-id="3e58e-235">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="3e58e-236">**Om** du har [konfigurerat en egen post låda](user-submission.md) för att få användardefinierade meddelanden kan du Visa och även skicka meddelanden som har levererats till rapporterings post lådan.</span><span class="sxs-lookup"><span data-stu-id="3e58e-236">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="3e58e-237">I säkerhets & Compliance Center går du till **Threat Management** - \> **inlämningar**.</span><span class="sxs-lookup"><span data-stu-id="3e58e-237">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="3e58e-238">Välj fliken **egen post låda** .</span><span class="sxs-lookup"><span data-stu-id="3e58e-238">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="3e58e-239">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="3e58e-239">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3e58e-240">**Skickades**</span><span class="sxs-lookup"><span data-stu-id="3e58e-240">**Submitted on**</span></span>
- <span data-ttu-id="3e58e-241">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e58e-241">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3e58e-242">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e58e-242">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="3e58e-243">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="3e58e-243">**Sender**</span></span>
- <span data-ttu-id="3e58e-244">**Avsändarens IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3e58e-244">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="3e58e-245">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="3e58e-245">**Submission type**</span></span>

<span data-ttu-id="3e58e-246">Högst upp på sidan kan du ange ett start datum, ett slutdatum och du kan **Filtrera efter genom** att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="3e58e-246">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="3e58e-247">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="3e58e-247">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="3e58e-248">Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**.</span><span class="sxs-lookup"><span data-stu-id="3e58e-248">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="3e58e-249">Spara CSV-filen i dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="3e58e-249">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="3e58e-250">Ångra användar inlägg</span><span class="sxs-lookup"><span data-stu-id="3e58e-250">Undo user submissions</span></span>

<span data-ttu-id="3e58e-251">När en användare skickar ett misstänkt e-postmeddelande till den anpassade post lådan har användaren och administratören inget alternativ för att ångra sändningen.</span><span class="sxs-lookup"><span data-stu-id="3e58e-251">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="3e58e-252">Om användaren vill återställa e-postmeddelandet kommer den att vara tillgänglig för återställning i mapparna Borttaget eller skräp post.</span><span class="sxs-lookup"><span data-stu-id="3e58e-252">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="3e58e-253">Skicka meddelanden till Microsoft från den anpassade post lådan</span><span class="sxs-lookup"><span data-stu-id="3e58e-253">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="3e58e-254">Om du har konfigurerat den anpassade post lådan för att avlyssna användardefinierade meddelanden utan att skicka meddelanden till Microsoft kan du söka efter och skicka specifika meddelanden till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="3e58e-254">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="3e58e-255">Detta flyttar en användares överföring till en administratör.</span><span class="sxs-lookup"><span data-stu-id="3e58e-255">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="3e58e-256">På fliken **egen post låda** väljer du ett meddelande i listan, klickar på knappen **åtgärd** och gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="3e58e-256">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="3e58e-257">**Rapport klar**</span><span class="sxs-lookup"><span data-stu-id="3e58e-257">**Report clean**</span></span>
- <span data-ttu-id="3e58e-258">**Rapportera nätfiske**</span><span class="sxs-lookup"><span data-stu-id="3e58e-258">**Report phishing**</span></span>
- <span data-ttu-id="3e58e-259">**Rapportera skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="3e58e-259">**Report malware**</span></span>
- <span data-ttu-id="3e58e-260">**Rapportera skräp post**</span><span class="sxs-lookup"><span data-stu-id="3e58e-260">**Report spam**</span></span>

![Alternativ på Åtgärds knappen](../../media/user-submission-custom-mailbox-action-button.png)
