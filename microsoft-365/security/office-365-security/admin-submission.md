---
title: Admin inlagor, inlagor, spam problem, falskt negativt, skicka phish, skicka e-post för skanning, misstänkt e-post i Office 365, skanna ett mail, har Microsoft söka efter phish, har Microsoft söka efter spam, skicka e-post, skicka e-post, skumma e-post, dålig skådespelare post, misstänkt, opålitlig e-post, rapportera phish e-post till Microsoft, rapportera phish e-post till Microsoft, rapportera skadlig e-post till Microsoft, rapportera bluff e-post till Microsoft , rapportera skadlig kod i e-post till Microsoft, skräppost i inkorgen, virus i e-post
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
description: Läs om hur du skickar misstänkta e-postmeddelanden, misstänkta nätfiskemeddelanden, skräppost och andra potentiellt skadliga meddelanden, webbadresser och filer från företaget till Microsoft för skanning.
ms.openlocfilehash: 73c33ba1218a710c33f8b2675bc65c0a7486efda
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2020
ms.locfileid: "43921534"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="edb66-103">Använd administratörsöverföring för att skicka misstänkt skräppost, phish, webbadresser och filer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="edb66-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="edb66-104">Om du är administratör i en Microsoft 365-organisation med postlådor i Exchange Online kan du använda portalen Inlämningar i Security & Compliance Center för att skicka e-postmeddelanden, webbadresser och bilagor till Microsoft för skanning.</span><span class="sxs-lookup"><span data-stu-id="edb66-104">If you're an admin in a Microsoft 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="edb66-105">När du skickar ett e-postmeddelande får du information om alla policyer som kan ha tillåtit inkommande e-post till din klientorganisation, samt granskning av eventuella webbadresser och bilagor med posten.</span><span class="sxs-lookup"><span data-stu-id="edb66-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="edb66-106">Principer som kan ha tillåtit ett e-postmeddelande inkluderar en enskild användares säkra avsänningslista samt principer på klientnivå, till exempel regler för Exchange-e-postflöde (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="edb66-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="edb66-107">Andra sätt att skicka e-postmeddelanden, webbadresser och bilagor till Microsoft finns i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="edb66-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="edb66-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="edb66-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="edb66-109">Öppna säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="edb66-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="edb66-110">Om du vill **Submission** gå direkt <https://protection.office.com/reportsubmission>till sidan Inlämning använder du .</span><span class="sxs-lookup"><span data-stu-id="edb66-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="edb66-111">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="edb66-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="edb66-112">Om du vill lägga till, ändra och ta bort principer för skräppost måste du vara medlem i rollgrupperna **Organisationshantering,** **Säkerhetsadministratör**eller **Säkerhetsläsare.**</span><span class="sxs-lookup"><span data-stu-id="edb66-112">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="edb66-113">Mer information om rollgrupper i säkerhets- och efterlevnadscentret finns i [Behörigheter i Säkerhets- och efterlevnadscenter](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="edb66-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="edb66-114">Mer information om hur användare kan skicka meddelanden och filer till Microsoft finns i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="edb66-114">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="edb66-115">Rapportera misstänkt innehåll till Microsoft</span><span class="sxs-lookup"><span data-stu-id="edb66-115">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="edb66-116">Gå till meddelanden om överföring av **Review** \> **administratörer**för hantering av & för **&.** \></span><span class="sxs-lookup"><span data-stu-id="edb66-116">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="edb66-117">Klicka på knappen **Ny inlämning** på sidan **Inlämningar** som visas.</span><span class="sxs-lookup"><span data-stu-id="edb66-117">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="edb66-118">Använd **Nytt överföringsutfällbart** överföringsavsnitt som visas för att skicka meddelandet, WEBBADRESSEN eller bilagan enligt beskrivningen i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="edb66-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="edb66-119">Skicka ett tvivelaktigt e-postmeddelande till Microsoft</span><span class="sxs-lookup"><span data-stu-id="edb66-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="edb66-120">Välj **E-post**i avsnittet **Objekttyp** .</span><span class="sxs-lookup"><span data-stu-id="edb66-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="edb66-121">I avsnittet **Inlämningsformat** använder du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="edb66-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="edb66-122">**Nätverksmeddelande-ID:** Det här är ett GUID-värde som är tillgängligt i **X-MS-Exchange-Organization-Network-Message-Id-huvudet** i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="edb66-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="edb66-123">**Arkiv**: Klicka på **Välj fil**.</span><span class="sxs-lookup"><span data-stu-id="edb66-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="edb66-124">Leta reda på och markera FILEN .eml eller .msg i dialogrutan som öppnas och klicka sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="edb66-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="edb66-125">I avsnittet **Mottagare** anger du en eller flera mottagare som du vill köra en principkontroll mot.</span><span class="sxs-lookup"><span data-stu-id="edb66-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="edb66-126">Principkontrollen avgör om e-postmeddelandet kringgås genomsökning på grund av användar- eller organisationsprinciper.</span><span class="sxs-lookup"><span data-stu-id="edb66-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="edb66-127">I avsnittet **Orsak till inlämning** väljer du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="edb66-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="edb66-128">**Borde inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="edb66-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="edb66-129">**Borde ha blockerats:** Välj **Skräppost,** **Nätfiske**eller **skadlig kod**.</span><span class="sxs-lookup"><span data-stu-id="edb66-129">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="edb66-130">Om du är osäker, använd ditt bästa omdöme.</span><span class="sxs-lookup"><span data-stu-id="edb66-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="edb66-131">Om filtret kringgådes på grund av principer vid inlämning visas information om den principen.</span><span class="sxs-lookup"><span data-stu-id="edb66-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="edb66-132">Om filtret inte kringgådes på grund av en eller flera principer slutförs genomsökningen på flera minuter.</span><span class="sxs-lookup"><span data-stu-id="edb66-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="edb66-133">Du ser ytterligare information om inlämningen genom att klicka på statuslänken.</span><span class="sxs-lookup"><span data-stu-id="edb66-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="edb66-134">Detta inkluderar resultaten av policykontrollen och återscan dom.</span><span class="sxs-lookup"><span data-stu-id="edb66-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="edb66-135">Observera att detta inte kör e-postmeddelandet via office 365 ATP full filtrering stack igen men kör en partiell rescan baserat på vissa attribut för e-post, URL eller fil.</span><span class="sxs-lookup"><span data-stu-id="edb66-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="edb66-136">När du är klar klickar du på knappen **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="edb66-136">When you're finished, click the **Submit** button.</span></span>

![Exempel på lämning av URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="edb66-138">Skicka en misstänkt WEBBADRESS till Microsoft</span><span class="sxs-lookup"><span data-stu-id="edb66-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="edb66-139">Välj **URL**i avsnittet **Objekttyp** .</span><span class="sxs-lookup"><span data-stu-id="edb66-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="edb66-140">I rutan som visas anger du den <https://www.fabrikam.com/marketing.html>fullständiga webbadressen (till exempel ).</span><span class="sxs-lookup"><span data-stu-id="edb66-140">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="edb66-141">I avsnittet **Orsak till inlämning** väljer du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="edb66-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="edb66-142">**Borde inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="edb66-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="edb66-143">**Borde ha blockerats:** Välj **Nätfiske** eller **malware**.</span><span class="sxs-lookup"><span data-stu-id="edb66-143">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="edb66-144">När du är klar klickar du på knappen **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="edb66-144">When you're finished, click the **Submit** button.</span></span>

![Exempel på skicka e-post](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="edb66-146">Skicka en misstänkt fil till Microsoft</span><span class="sxs-lookup"><span data-stu-id="edb66-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="edb66-147">Välj **Bifogad fil**i avsnittet **Objekttyp** .</span><span class="sxs-lookup"><span data-stu-id="edb66-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="edb66-148">Klicka på **Välj fil**.</span><span class="sxs-lookup"><span data-stu-id="edb66-148">Click **Choose File**.</span></span> <span data-ttu-id="edb66-149">Leta reda på och markera filen i dialogrutan som öppnas och klicka sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="edb66-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="edb66-150">I avsnittet **Orsak till inlämning** väljer du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="edb66-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="edb66-151">**Borde inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="edb66-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="edb66-152">**Borde ha blockerats:** **Malware** är det enda valet, och väljs automatiskt..</span><span class="sxs-lookup"><span data-stu-id="edb66-152">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="edb66-153">När du är klar klickar du på knappen **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="edb66-153">When you're finished, click the **Submit** button.</span></span>

![Exempel på inlämning av bifogad fil](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="edb66-155">Visa administratörsinlämningar</span><span class="sxs-lookup"><span data-stu-id="edb66-155">View admin submissions</span></span>

1. <span data-ttu-id="edb66-156">Gå till meddelanden om överföring av **Review** \> **administratörer**för hantering av & för **&.** \></span><span class="sxs-lookup"><span data-stu-id="edb66-156">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="edb66-157">Kontrollera att fliken **Administratörsöverföringar** är markerad på sidan **Inlämningar.**</span><span class="sxs-lookup"><span data-stu-id="edb66-157">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="edb66-158">Högst upp på sidan kan du ange ett startdatum, ett slutdatum och (som standard) kan du filtrera efter ![ **inlämnings-ID** genom att ange ett värde i rutan och klicka på Uppdatera.Up of the top of the page, you can enter a start date, an end date, and (by default) you can filter by Submission ID by entering a value in the box and clicking Refresh button](../../media/scc-quarantine-refresh.png).</span><span class="sxs-lookup"><span data-stu-id="edb66-158">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="edb66-159">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="edb66-159">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="edb66-160">Om du vill ändra filtervillkoren klickar du på knappen **Inlämnings-ID** och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="edb66-160">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="edb66-161">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="edb66-161">**Sender**</span></span>
- <span data-ttu-id="edb66-162">**Ämne/URL/Filnamn**</span><span class="sxs-lookup"><span data-stu-id="edb66-162">**Subject/URL/File name**</span></span>
- <span data-ttu-id="edb66-163">**Insänt av**</span><span class="sxs-lookup"><span data-stu-id="edb66-163">**Submitted by**</span></span>
- <span data-ttu-id="edb66-164">**Typ av inlämning**</span><span class="sxs-lookup"><span data-stu-id="edb66-164">**Submission type**</span></span>
- <span data-ttu-id="edb66-165">**Status**</span><span class="sxs-lookup"><span data-stu-id="edb66-165">**Status**</span></span>

![Filteralternativ för administratörsinlämningar](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="edb66-167">Om du vill exportera resultaten klickar du på **Exportera** högst upp på sidan och väljer **Diagramdata** eller **Tabell**.</span><span class="sxs-lookup"><span data-stu-id="edb66-167">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="edb66-168">Spara CSV-filen i dialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="edb66-168">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="edb66-169">Under diagrammet finns tre flikar: **E-post** (standard), **URL**och **Bifogad fil**.</span><span class="sxs-lookup"><span data-stu-id="edb66-169">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="edb66-170">Visa e-postinlämningar för administratörer</span><span class="sxs-lookup"><span data-stu-id="edb66-170">View admin email submissions</span></span>

<span data-ttu-id="edb66-171">Klicka på fliken **E-post.**</span><span class="sxs-lookup"><span data-stu-id="edb66-171">Click the **Email** tab.</span></span>

<span data-ttu-id="edb66-172">Du kan klicka på knappen **Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner från vyn:</span><span class="sxs-lookup"><span data-stu-id="edb66-172">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="edb66-173">**Datum**</span><span class="sxs-lookup"><span data-stu-id="edb66-173">**Date**</span></span>
- <span data-ttu-id="edb66-174">**Inlämnings-ID**</span><span class="sxs-lookup"><span data-stu-id="edb66-174">**Submission ID**</span></span>
- <span data-ttu-id="edb66-175">**Insänt av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="edb66-175">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="edb66-176">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="edb66-176">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="edb66-177">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="edb66-177">**Sender**</span></span>
- <span data-ttu-id="edb66-178">**IP-adress för avsändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="edb66-178">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="edb66-179">**Typ av inlämning**</span><span class="sxs-lookup"><span data-stu-id="edb66-179">**Submission type**</span></span>
- <span data-ttu-id="edb66-180">**Leveransorsak**</span><span class="sxs-lookup"><span data-stu-id="edb66-180">**Delivery reason**</span></span>
- <span data-ttu-id="edb66-181">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="edb66-181">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="edb66-182">**Kontrolltyp**</span><span class="sxs-lookup"><span data-stu-id="edb66-182">**Control type**</span></span>
- <span data-ttu-id="edb66-183">**Kontrollkälla**</span><span class="sxs-lookup"><span data-stu-id="edb66-183">**Control source**</span></span>

  <span data-ttu-id="edb66-184"><sup>\*</sup>Om du klickar på det här värdet visas detaljerad information i ett utfällbart alternativ.</span><span class="sxs-lookup"><span data-stu-id="edb66-184"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="edb66-185">Visa inlämning av administratörs-URL</span><span class="sxs-lookup"><span data-stu-id="edb66-185">View admin URL submissions</span></span>

<span data-ttu-id="edb66-186">Klicka på fliken **URL.**</span><span class="sxs-lookup"><span data-stu-id="edb66-186">Click the **URL** tab.</span></span>

<span data-ttu-id="edb66-187">Du kan klicka på knappen **Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner från vyn:</span><span class="sxs-lookup"><span data-stu-id="edb66-187">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="edb66-188">**Datum**</span><span class="sxs-lookup"><span data-stu-id="edb66-188">**Date**</span></span>
- <span data-ttu-id="edb66-189">**Inlämnings-ID**</span><span class="sxs-lookup"><span data-stu-id="edb66-189">**Submission ID**</span></span>
- <span data-ttu-id="edb66-190">**Insänt av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="edb66-190">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="edb66-191">**Url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="edb66-191">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="edb66-192">**Typ av inlämning**</span><span class="sxs-lookup"><span data-stu-id="edb66-192">**Submission type**</span></span>
- <span data-ttu-id="edb66-193">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="edb66-193">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="edb66-194"><sup>\*</sup>Om du klickar på det här värdet visas detaljerad information i ett utfällbart alternativ.</span><span class="sxs-lookup"><span data-stu-id="edb66-194"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="edb66-195">Visa inlämningar av administratörstillbehör</span><span class="sxs-lookup"><span data-stu-id="edb66-195">View admin attachment submissions</span></span>

<span data-ttu-id="edb66-196">Klicka på fliken **Bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="edb66-196">Click the **Attachments** tab.</span></span>

<span data-ttu-id="edb66-197">Du kan klicka på knappen **Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner från vyn:</span><span class="sxs-lookup"><span data-stu-id="edb66-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="edb66-198">**Datum**</span><span class="sxs-lookup"><span data-stu-id="edb66-198">**Date**</span></span>
- <span data-ttu-id="edb66-199">**Inlämnings-ID**</span><span class="sxs-lookup"><span data-stu-id="edb66-199">**Submission ID**</span></span>
- <span data-ttu-id="edb66-200">**Insänt av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="edb66-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="edb66-201">**Filnamn**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="edb66-201">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="edb66-202">**Typ av inlämning**</span><span class="sxs-lookup"><span data-stu-id="edb66-202">**Submission type**</span></span>
- <span data-ttu-id="edb66-203">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="edb66-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="edb66-204"><sup>\*</sup>Om du klickar på det här värdet visas detaljerad information i ett utfällbart alternativ.</span><span class="sxs-lookup"><span data-stu-id="edb66-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="edb66-205">Visa användarinlämningar till Microsoft</span><span class="sxs-lookup"><span data-stu-id="edb66-205">View user submissions to Microsoft</span></span>

<span data-ttu-id="edb66-206">Om du har distribuerat [tillägget Report Message eller](enable-the-report-message-add-in.md)om personer använder den [inbyggda rapporteringen i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)kan du se vilka användare som rapporterar på fliken **Användares inlämningar.**</span><span class="sxs-lookup"><span data-stu-id="edb66-206">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="edb66-207">Gå till meddelanden om överföring av **Review** \> **administratörer**för hantering av & för **&.** \></span><span class="sxs-lookup"><span data-stu-id="edb66-207">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="edb66-208">Klicka på fliken **Användare inlämningar** på sidan **Inlämningar** som visas.</span><span class="sxs-lookup"><span data-stu-id="edb66-208">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="edb66-209">Du kan klicka på knappen **Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner från vyn:</span><span class="sxs-lookup"><span data-stu-id="edb66-209">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="edb66-210">**Insänt den**</span><span class="sxs-lookup"><span data-stu-id="edb66-210">**Submitted on**</span></span>
- <span data-ttu-id="edb66-211">**Insänt av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="edb66-211">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="edb66-212">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="edb66-212">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="edb66-213">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="edb66-213">**Sender**</span></span>
- <span data-ttu-id="edb66-214">**IP-adress för avsändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="edb66-214">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="edb66-215">**Typ av inlämning**</span><span class="sxs-lookup"><span data-stu-id="edb66-215">**Submission type**</span></span>

<span data-ttu-id="edb66-216"><sup>\*</sup>Om du klickar på det här värdet visas detaljerad information i ett utfällbart alternativ.</span><span class="sxs-lookup"><span data-stu-id="edb66-216"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="edb66-217">Högst upp på sidan kan du ange ett startdatum, ett slutdatum och (som standard) som du kan filtrera ![efter](../../media/scc-quarantine-refresh.png)avsändare genom att ange ett värde i rutan och klicka på Uppdatera.Up of the page, you can enter a start date, a end date, and (as default) you can filter by **Sender** by entering a value in the box and clicking Refresh button .</span><span class="sxs-lookup"><span data-stu-id="edb66-217">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="edb66-218">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="edb66-218">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="edb66-219">Om du vill ändra filtervillkoren klickar du på knappen **Avsändare** och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="edb66-219">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="edb66-220">**Domän för avsändare**</span><span class="sxs-lookup"><span data-stu-id="edb66-220">**Sender domain**</span></span>
- <span data-ttu-id="edb66-221">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="edb66-221">**Subject**</span></span>
- <span data-ttu-id="edb66-222">**Insänt av**</span><span class="sxs-lookup"><span data-stu-id="edb66-222">**Submitted by**</span></span>
- <span data-ttu-id="edb66-223">**Typ av inlämning**</span><span class="sxs-lookup"><span data-stu-id="edb66-223">**Submission type**</span></span>
- <span data-ttu-id="edb66-224">**IP-adress för avsändare**</span><span class="sxs-lookup"><span data-stu-id="edb66-224">**Sender IP**</span></span>

![Filteralternativ för användarinlämningar](../../media/user-submissions-filter-options.png)

<span data-ttu-id="edb66-226">Om du vill exportera resultaten klickar du på **Exportera** högst upp på sidan och väljer **Diagramdata** eller **Tabell**.</span><span class="sxs-lookup"><span data-stu-id="edb66-226">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="edb66-227">Spara CSV-filen i dialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="edb66-227">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="edb66-228">Visa användaröverföringar till den anpassade postlådan</span><span class="sxs-lookup"><span data-stu-id="edb66-228">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="edb66-229">Om du har [konfigurerat en anpassad postlåda](user-submission.md) för att ta emot användarrapporterade meddelanden kan du visa och även skicka meddelanden som levererades till rapportpostlådan.</span><span class="sxs-lookup"><span data-stu-id="edb66-229">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="edb66-230">Gå till meddelanden om överföring av **Review** \> **administratörer**för hantering av & för **&.** \></span><span class="sxs-lookup"><span data-stu-id="edb66-230">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="edb66-231">Klicka på fliken **Anpassad postlåda** på sidan **Inlämningar** som visas.</span><span class="sxs-lookup"><span data-stu-id="edb66-231">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="edb66-232">Du kan klicka på knappen **Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner från vyn:</span><span class="sxs-lookup"><span data-stu-id="edb66-232">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="edb66-233">**Insänt den**</span><span class="sxs-lookup"><span data-stu-id="edb66-233">**Submitted on**</span></span>
- <span data-ttu-id="edb66-234">**Insänt av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="edb66-234">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="edb66-235">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="edb66-235">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="edb66-236">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="edb66-236">**Sender**</span></span>
- <span data-ttu-id="edb66-237">**IP-adress för avsändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="edb66-237">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="edb66-238">**Typ av inlämning**</span><span class="sxs-lookup"><span data-stu-id="edb66-238">**Submission type**</span></span>

<span data-ttu-id="edb66-239">Högst upp på sidan kan du ange ett startdatum, ett slutdatum och du kan filtrera efter Skickad](../../media/scc-quarantine-refresh.png)genom att ange ett värde i rutan och klicka på Uppdatera.Up the top of the page, you can enter a start date, an end date, and you can filter by Submitted by **entering** a value in the box and clicking ![Refresh button .</span><span class="sxs-lookup"><span data-stu-id="edb66-239">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="edb66-240">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="edb66-240">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="edb66-241">Om du vill exportera resultaten klickar du på **Exportera** högst upp på sidan och väljer **Diagramdata** eller **Tabell**.</span><span class="sxs-lookup"><span data-stu-id="edb66-241">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="edb66-242">Spara CSV-filen i dialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="edb66-242">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="edb66-243">Skicka meddelanden till Microsoft från den anpassade postlådan</span><span class="sxs-lookup"><span data-stu-id="edb66-243">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="edb66-244">Om du har konfigurerat den anpassade postlådan för att avlyssna användarrapporterade meddelanden utan att skicka meddelandena till Microsoft kan du söka efter och skicka specifika meddelanden till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="edb66-244">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="edb66-245">Detta flyttar effektivt en användare inlämning till en administratör inlämning.</span><span class="sxs-lookup"><span data-stu-id="edb66-245">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="edb66-246">Markera ett meddelande i listan på fliken **Anpassad postlåda,** klicka på knappen **Åtgärd** och gör något av följande val:</span><span class="sxs-lookup"><span data-stu-id="edb66-246">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="edb66-247">**Rapporten är ren**</span><span class="sxs-lookup"><span data-stu-id="edb66-247">**Report clean**</span></span>
- <span data-ttu-id="edb66-248">**Rapportera nätfiske**</span><span class="sxs-lookup"><span data-stu-id="edb66-248">**Report phishing**</span></span>
- <span data-ttu-id="edb66-249">**Rapportera skadlig kod**</span><span class="sxs-lookup"><span data-stu-id="edb66-249">**Report malware**</span></span>
- <span data-ttu-id="edb66-250">**Rapportera skräppost**</span><span class="sxs-lookup"><span data-stu-id="edb66-250">**Report spam**</span></span>

![Alternativ på knappen Åtgärd](../../media/user-submission-custom-mailbox-action-button.png)
