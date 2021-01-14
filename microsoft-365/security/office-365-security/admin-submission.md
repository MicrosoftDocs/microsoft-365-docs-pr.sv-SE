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
ms.openlocfilehash: 432a245530d7906ae8babbc54176480d36315351
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864954"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="ecac0-103">Använd administratörs sändning för att skicka misstänkt skräp post, Phish, URL: er och filer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="ecac0-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ecac0-104">I Microsoft 365-organisationer med post lådor i Exchange Online kan administratörer använda & portalen för att skicka e-postmeddelanden, URL: er och bifogade filer till Microsoft för att söka.</span><span class="sxs-lookup"><span data-stu-id="ecac0-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="ecac0-105">När du skickar ett e-postmeddelande får du information om eventuella principer som kan ha tillåtit inkommande e-post till din klient organisation samt granskning av URL: er och bilagor i e-postmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="ecac0-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="ecac0-106">Principer som kan ha tillåtelse till ett e-postmeddelande inkluderar en enskild användares lista över betrodda avsändare och policy principer för Exchange-flöden (kallas även transport regler).</span><span class="sxs-lookup"><span data-stu-id="ecac0-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="ecac0-107">Andra sätt att skicka e-postmeddelanden, webb adresser och bilagor till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="ecac0-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ecac0-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="ecac0-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ecac0-109">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ecac0-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="ecac0-110">För att gå direkt till **sändnings** sidan, Använd <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="ecac0-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="ecac0-111">För att skicka meddelanden och filer till Microsoft måste du vara medlem i någon av följande roll grupper:</span><span class="sxs-lookup"><span data-stu-id="ecac0-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="ecac0-112">**Organisationshantering** eller **Säkerhetsadministratör** i [Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ecac0-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="ecac0-113">**Organisations hantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="ecac0-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="ecac0-114">Observera att medlemskap i den här roll gruppen krävs för att [Visa användar överföringar till den anpassade post lådan](#view-user-submissions-to-the-custom-mailbox) enligt beskrivningen längre ned i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="ecac0-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="ecac0-115">Mer information om hur användarna kan skicka meddelanden och filer till Microsoft finns i [rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="ecac0-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="ecac0-116">Rapportera misstänkt innehåll till Microsoft</span><span class="sxs-lookup"><span data-stu-id="ecac0-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="ecac0-117">I säkerhets & Compliance Center går du till **Threat Management** -undersändningar \> , kontrollerar att du är på fliken **admin-överföring** och klickar sedan på **ny överföring**.</span><span class="sxs-lookup"><span data-stu-id="ecac0-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="ecac0-118">Använd  utfällbar text som visas för att skicka meddelandet, URL: en eller bifogad fil enligt beskrivningen i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="ecac0-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="ecac0-119">Skicka ett tveksamt e-postmeddelande till Microsoft</span><span class="sxs-lookup"><span data-stu-id="ecac0-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="ecac0-120">Välj **e-post** under **objekt typ** .</span><span class="sxs-lookup"><span data-stu-id="ecac0-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="ecac0-121">Använd något av följande alternativ i avsnittet **sändnings format** :</span><span class="sxs-lookup"><span data-stu-id="ecac0-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="ecac0-122">**ID för nätverks meddelande**: det här är ett GUID-värde som är tillgängligt i huvudet **x-MS-Exchange-Organization-Network-meddelande-ID** i meddelandet, eller i **X-MS-Office365**</span><span class="sxs-lookup"><span data-stu-id="ecac0-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="ecac0-123">**Fil**: Klicka på **Välj fil**.</span><span class="sxs-lookup"><span data-stu-id="ecac0-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="ecac0-124">I dialog rutan som öppnas letar du reda på och markerar EML-eller MSG-filen och klickar sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="ecac0-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ecac0-125">Administratörer med Defender för Office 365 abonnemang 1 eller abonnemang 2 kan skicka meddelanden som gamla 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="ecac0-125">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="ecac0-126">Andra administratörer kan bara gå tillbaka sju dagar.</span><span class="sxs-lookup"><span data-stu-id="ecac0-126">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="ecac0-127">Ange en eller flera mottagare som du vill köra en princip kontroll för i avsnittet **mottagare** .</span><span class="sxs-lookup"><span data-stu-id="ecac0-127">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="ecac0-128">Princip kontrollen avgör om genomsökning av e-postmeddelandet kringgås på grund av principer för användare eller organisation.</span><span class="sxs-lookup"><span data-stu-id="ecac0-128">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="ecac0-129">Välj något av följande alternativ i avsnittet **orsak för inlämning** :</span><span class="sxs-lookup"><span data-stu-id="ecac0-129">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="ecac0-130">**Ska inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="ecac0-130">**Should not have been blocked**</span></span>

   - <span data-ttu-id="ecac0-131">**Bör ha blockerats**: Välj **skräp post**, **nätfiske** eller **skadlig program vara**.</span><span class="sxs-lookup"><span data-stu-id="ecac0-131">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="ecac0-132">Om du är osäker kan du använda ditt bästa omdöme.</span><span class="sxs-lookup"><span data-stu-id="ecac0-132">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="ecac0-133">När du är klar klickar du på **Skicka** .</span><span class="sxs-lookup"><span data-stu-id="ecac0-133">When you're finished, click the **Submit** button.</span></span>

![Exempel på skicka URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="ecac0-135">Skicka en misstänkt URL till Microsoft</span><span class="sxs-lookup"><span data-stu-id="ecac0-135">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="ecac0-136">Välj **URL** under **objekt typ** .</span><span class="sxs-lookup"><span data-stu-id="ecac0-136">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="ecac0-137">I rutan som visas anger du den fullständiga URL: en (till exempel `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="ecac0-137">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="ecac0-138">Välj något av följande alternativ i avsnittet **orsak för inlämning** :</span><span class="sxs-lookup"><span data-stu-id="ecac0-138">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="ecac0-139">**Ska inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="ecac0-139">**Should not have been blocked**</span></span>

   - <span data-ttu-id="ecac0-140">**Borde ha blockerats**: Välj **nätfiske** eller **malware**.</span><span class="sxs-lookup"><span data-stu-id="ecac0-140">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="ecac0-141">När du är klar klickar du på **Skicka** .</span><span class="sxs-lookup"><span data-stu-id="ecac0-141">When you're finished, click the **Submit** button.</span></span>

![Exempel på Skicka e-post](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="ecac0-143">Skicka en misstänkt fil till Microsoft</span><span class="sxs-lookup"><span data-stu-id="ecac0-143">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="ecac0-144">Välj **bilaga** under **objekt typ** .</span><span class="sxs-lookup"><span data-stu-id="ecac0-144">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="ecac0-145">Klicka på **Välj fil**.</span><span class="sxs-lookup"><span data-stu-id="ecac0-145">Click **Choose File**.</span></span> <span data-ttu-id="ecac0-146">Leta upp och markera filen i dialog rutan som öppnas och klicka sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="ecac0-146">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="ecac0-147">Välj något av följande alternativ i avsnittet **orsak för inlämning** :</span><span class="sxs-lookup"><span data-stu-id="ecac0-147">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="ecac0-148">**Ska inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="ecac0-148">**Should not have been blocked**</span></span>

   - <span data-ttu-id="ecac0-149">**Bör ha blockerats**: **malware** är det enda alternativet och väljs automatiskt...</span><span class="sxs-lookup"><span data-stu-id="ecac0-149">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="ecac0-150">När du är klar klickar du på **Skicka** .</span><span class="sxs-lookup"><span data-stu-id="ecac0-150">When you're finished, click the **Submit** button.</span></span>

![Exempel på skicka bilagor](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="ecac0-152">Visa administratörs inlämningar</span><span class="sxs-lookup"><span data-stu-id="ecac0-152">View admin submissions</span></span>

<span data-ttu-id="ecac0-153">I säkerhets & Compliance Center går du till **Threat Management** -undersändningar \> , kontrollerar att du är på fliken **admin-överföring** och klickar sedan på **ny överföring**.</span><span class="sxs-lookup"><span data-stu-id="ecac0-153">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="ecac0-154">Högst upp på sidan kan du ange ett start datum, ett slutdatum och (som standard) som du kan filtrera efter **överförings-ID** (ett GUID-värde som är kopplat till varje överföring) genom att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="ecac0-154">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="ecac0-155">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="ecac0-155">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="ecac0-156">Om du vill ändra filter villkoren klickar du på knappen **Skicka ID** och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="ecac0-156">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="ecac0-157">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="ecac0-157">**Sender**</span></span>
- <span data-ttu-id="ecac0-158">**Ämne/URL/fil namn**</span><span class="sxs-lookup"><span data-stu-id="ecac0-158">**Subject/URL/File name**</span></span>
- <span data-ttu-id="ecac0-159">**Skickades av**</span><span class="sxs-lookup"><span data-stu-id="ecac0-159">**Submitted by**</span></span>
- <span data-ttu-id="ecac0-160">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="ecac0-160">**Submission type**</span></span>
- <span data-ttu-id="ecac0-161">**Status**</span><span class="sxs-lookup"><span data-stu-id="ecac0-161">**Status**</span></span>

![Filter alternativ för administratörs inlämning](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="ecac0-163">Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**.</span><span class="sxs-lookup"><span data-stu-id="ecac0-163">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="ecac0-164">Spara CSV-filen i dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="ecac0-164">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="ecac0-165">Under grafen finns det tre flikar: **e-post** (standard), **URL** och **bifogad fil**.</span><span class="sxs-lookup"><span data-stu-id="ecac0-165">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="ecac0-166">Visa e-postinlägg för administratörer</span><span class="sxs-lookup"><span data-stu-id="ecac0-166">View admin email submissions</span></span>

<span data-ttu-id="ecac0-167">Klicka på fliken **e-post** .</span><span class="sxs-lookup"><span data-stu-id="ecac0-167">Click the **Email** tab.</span></span>

<span data-ttu-id="ecac0-168">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="ecac0-168">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ecac0-169">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ecac0-169">**Date**</span></span>
- <span data-ttu-id="ecac0-170">**Sändnings-ID**: ett GUID-värde som tilldelats varje överföring.</span><span class="sxs-lookup"><span data-stu-id="ecac0-170">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="ecac0-171">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ecac0-171">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ecac0-172">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ecac0-172">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="ecac0-173">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="ecac0-173">**Sender**</span></span>
- <span data-ttu-id="ecac0-174">**Avsändarens IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ecac0-174">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="ecac0-175">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="ecac0-175">**Submission type**</span></span>
- <span data-ttu-id="ecac0-176">**Leverans orsak**</span><span class="sxs-lookup"><span data-stu-id="ecac0-176">**Delivery reason**</span></span>
- <span data-ttu-id="ecac0-177">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ecac0-177">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="ecac0-178"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="ecac0-178"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="ecac0-179">Information om att söka efter administratörs uppgifter</span><span class="sxs-lookup"><span data-stu-id="ecac0-179">Admin submission rescan details</span></span>

<span data-ttu-id="ecac0-180">Meddelanden som skickas i administratörs inlämningar skannas in och visas i den utfällbara informationen:</span><span class="sxs-lookup"><span data-stu-id="ecac0-180">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="ecac0-181">Om det uppstod ett fel i avsändarens e-postautentisering vid leverans tillfället.</span><span class="sxs-lookup"><span data-stu-id="ecac0-181">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="ecac0-182">Information om eventuella policy träffar som kan ha påverkat eller åsidosatt Verdict av ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="ecac0-182">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="ecac0-183">Aktuella Spräng resultat för att se om URL-adresserna eller filerna i meddelandet är skadliga eller inte.</span><span class="sxs-lookup"><span data-stu-id="ecac0-183">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="ecac0-184">Feedback från betyg.</span><span class="sxs-lookup"><span data-stu-id="ecac0-184">Feedback from graders.</span></span>

<span data-ttu-id="ecac0-185">Om en åsidosättning hittas måste genomsökningen genomföras flera minuter.</span><span class="sxs-lookup"><span data-stu-id="ecac0-185">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="ecac0-186">Om det inte fanns något problem med e-postauktorisering eller leveransen påverkas inte av en åsidosättning och feedback från betyg kan ta upp till en dag.</span><span class="sxs-lookup"><span data-stu-id="ecac0-186">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="ecac0-187">Visa URL-överföringar för administratörer</span><span class="sxs-lookup"><span data-stu-id="ecac0-187">View admin URL submissions</span></span>

<span data-ttu-id="ecac0-188">Klicka på fliken **URL** .</span><span class="sxs-lookup"><span data-stu-id="ecac0-188">Click the **URL** tab.</span></span>

<span data-ttu-id="ecac0-189">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="ecac0-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ecac0-190">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ecac0-190">**Date**</span></span>
- <span data-ttu-id="ecac0-191">**Sändnings-ID**</span><span class="sxs-lookup"><span data-stu-id="ecac0-191">**Submission ID**</span></span>
- <span data-ttu-id="ecac0-192">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ecac0-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ecac0-193">**:**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ecac0-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="ecac0-194">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="ecac0-194">**Submission type**</span></span>
- <span data-ttu-id="ecac0-195">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ecac0-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="ecac0-196"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="ecac0-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="ecac0-197">Visa underlämning av administrativa bilagor</span><span class="sxs-lookup"><span data-stu-id="ecac0-197">View admin attachment submissions</span></span>

<span data-ttu-id="ecac0-198">Klicka på fliken **bifogade filer** .</span><span class="sxs-lookup"><span data-stu-id="ecac0-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="ecac0-199">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="ecac0-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ecac0-200">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ecac0-200">**Date**</span></span>
- <span data-ttu-id="ecac0-201">**Sändnings-ID**</span><span class="sxs-lookup"><span data-stu-id="ecac0-201">**Submission ID**</span></span>
- <span data-ttu-id="ecac0-202">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ecac0-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ecac0-203">**Fil namn**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ecac0-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="ecac0-204">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="ecac0-204">**Submission type**</span></span>
- <span data-ttu-id="ecac0-205">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ecac0-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="ecac0-206"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="ecac0-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="ecac0-207">Visa användar inlämningar till Microsoft</span><span class="sxs-lookup"><span data-stu-id="ecac0-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="ecac0-208">Om du har distribuerat [tillägget rapportera](enable-the-report-message-add-in.md)tillägget rapport- [nätfiske](enable-the-report-phish-add-in.md)eller personer som använder den [inbyggda rapporteringen i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)kan du se vilka användare som rapporterar på fliken **användar överföringar** .</span><span class="sxs-lookup"><span data-stu-id="ecac0-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="ecac0-209">I säkerhets & Compliance Center går du till **Threat Management** - \> **inlämningar**.</span><span class="sxs-lookup"><span data-stu-id="ecac0-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="ecac0-210">Välj fliken **användar överföringar** och klicka sedan på **ny överföring**.</span><span class="sxs-lookup"><span data-stu-id="ecac0-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="ecac0-211">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="ecac0-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ecac0-212">**Skickades**</span><span class="sxs-lookup"><span data-stu-id="ecac0-212">**Submitted on**</span></span>
- <span data-ttu-id="ecac0-213">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ecac0-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ecac0-214">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ecac0-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="ecac0-215">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="ecac0-215">**Sender**</span></span>
- <span data-ttu-id="ecac0-216">**Avsändarens IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ecac0-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="ecac0-217">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="ecac0-217">**Submission type**</span></span>

<span data-ttu-id="ecac0-218"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i utfällbar skick.</span><span class="sxs-lookup"><span data-stu-id="ecac0-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="ecac0-219">Högst upp på sidan kan du ange ett start datum, ett slutdatum och (som standard) som du kan filtrera efter **avsändare** genom att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="ecac0-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="ecac0-220">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="ecac0-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="ecac0-221">Om du vill ändra filter villkoren klickar du på knappen **avsändare** och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="ecac0-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="ecac0-222">**Avsändningsdomän**</span><span class="sxs-lookup"><span data-stu-id="ecac0-222">**Sender domain**</span></span>
- <span data-ttu-id="ecac0-223">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="ecac0-223">**Subject**</span></span>
- <span data-ttu-id="ecac0-224">**Skickades av**</span><span class="sxs-lookup"><span data-stu-id="ecac0-224">**Submitted by**</span></span>
- <span data-ttu-id="ecac0-225">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="ecac0-225">**Submission type**</span></span>
- <span data-ttu-id="ecac0-226">**Avsändarens IP**</span><span class="sxs-lookup"><span data-stu-id="ecac0-226">**Sender IP**</span></span>

![Filter alternativ för användar inlämning](../../media/user-submissions-filter-options.png)

<span data-ttu-id="ecac0-228">Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**.</span><span class="sxs-lookup"><span data-stu-id="ecac0-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="ecac0-229">Spara CSV-filen i dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="ecac0-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="ecac0-230">Visa användar inlämningar till den anpassade post lådan</span><span class="sxs-lookup"><span data-stu-id="ecac0-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="ecac0-231">**Om** du har [konfigurerat en egen post låda](user-submission.md) för att få användardefinierade meddelanden kan du Visa och även skicka meddelanden som har levererats till rapporterings post lådan.</span><span class="sxs-lookup"><span data-stu-id="ecac0-231">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="ecac0-232">I säkerhets & Compliance Center går du till **Threat Management** - \> **inlämningar**.</span><span class="sxs-lookup"><span data-stu-id="ecac0-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="ecac0-233">Välj fliken **egen post låda** .</span><span class="sxs-lookup"><span data-stu-id="ecac0-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="ecac0-234">Du kan klicka på knappen **kolumn alternativ** nära längst ned på sidan för att lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="ecac0-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="ecac0-235">**Skickades**</span><span class="sxs-lookup"><span data-stu-id="ecac0-235">**Submitted on**</span></span>
- <span data-ttu-id="ecac0-236">**Skickades av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ecac0-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="ecac0-237">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ecac0-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="ecac0-238">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="ecac0-238">**Sender**</span></span>
- <span data-ttu-id="ecac0-239">**Avsändarens IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ecac0-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="ecac0-240">**Sändnings typ**</span><span class="sxs-lookup"><span data-stu-id="ecac0-240">**Submission type**</span></span>

<span data-ttu-id="ecac0-241">Högst upp på sidan kan du ange ett start datum, ett slutdatum och du kan **Filtrera efter genom** att ange ett värde i rutan och klicka på ![ knappen uppdatera ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="ecac0-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="ecac0-242">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="ecac0-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="ecac0-243">Exportera resultatet genom att klicka på **Exportera** överst på sidan och välja **diagram data** eller **tabell**.</span><span class="sxs-lookup"><span data-stu-id="ecac0-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="ecac0-244">Spara CSV-filen i dialog rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="ecac0-244">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="ecac0-245">Ångra användar inlägg</span><span class="sxs-lookup"><span data-stu-id="ecac0-245">Undo user submissions</span></span>

<span data-ttu-id="ecac0-246">När en användare skickar ett misstänkt e-postmeddelande till den anpassade post lådan har användaren och administratören inget alternativ för att ångra sändningen.</span><span class="sxs-lookup"><span data-stu-id="ecac0-246">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="ecac0-247">Om användaren vill återställa e-postmeddelandet kommer den att vara tillgänglig för återställning i mapparna Borttaget eller skräp post.</span><span class="sxs-lookup"><span data-stu-id="ecac0-247">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="ecac0-248">Skicka meddelanden till Microsoft från den anpassade post lådan</span><span class="sxs-lookup"><span data-stu-id="ecac0-248">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="ecac0-249">Om du har konfigurerat den anpassade post lådan för att avlyssna användardefinierade meddelanden utan att skicka meddelanden till Microsoft kan du söka efter och skicka specifika meddelanden till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="ecac0-249">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="ecac0-250">Detta flyttar en användares överföring till en administratör.</span><span class="sxs-lookup"><span data-stu-id="ecac0-250">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="ecac0-251">På fliken **egen post låda** väljer du ett meddelande i listan, klickar på knappen **åtgärd** och gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="ecac0-251">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="ecac0-252">**Rapport klar**</span><span class="sxs-lookup"><span data-stu-id="ecac0-252">**Report clean**</span></span>
- <span data-ttu-id="ecac0-253">**Rapportera nätfiske**</span><span class="sxs-lookup"><span data-stu-id="ecac0-253">**Report phishing**</span></span>
- <span data-ttu-id="ecac0-254">**Rapportera skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="ecac0-254">**Report malware**</span></span>
- <span data-ttu-id="ecac0-255">**Rapportera skräp post**</span><span class="sxs-lookup"><span data-stu-id="ecac0-255">**Report spam**</span></span>

![Alternativ på Åtgärds knappen](../../media/user-submission-custom-mailbox-action-button.png)
