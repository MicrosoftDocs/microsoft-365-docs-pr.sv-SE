---
title: Administrativa inlämningar
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
description: Administratörer kan lära sig hur du använder portalen Inlämningar i Security & Compliance Center för att skicka misstänkta e-postmeddelanden, misstänkta nätfiskemeddelanden, skräppost och andra potentiellt skadliga meddelanden, webbadresser och filer till Microsoft för skanning.
ms.openlocfilehash: 18941c1400917291f8924331fd19827e476db914
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726845"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="47eb9-103">Använd administratörsöverföring för att skicka misstänkt skräppost, phish, webbadresser och filer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="47eb9-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="47eb9-104">I Microsoft 365-organisationer med postlådor i Exchange Online kan administratörer använda portalen Inlämningar i Security & Compliance Center för att skicka e-postmeddelanden, webbadresser och bilagor till Microsoft för skanning.</span><span class="sxs-lookup"><span data-stu-id="47eb9-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="47eb9-105">När du skickar ett e-postmeddelande får du information om alla policyer som kan ha tillåtit inkommande e-post till din klientorganisation, samt granskning av webbadresser och bilagor med posten.</span><span class="sxs-lookup"><span data-stu-id="47eb9-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="47eb9-106">Principer som kan ha tillåtit ett e-postmeddelande inkluderar en enskild användares säkra avsänningslista samt principer för klientnivå, till exempel regler för Exchange-e-postflöde (kallas även transportregler).</span><span class="sxs-lookup"><span data-stu-id="47eb9-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="47eb9-107">Andra sätt att skicka e-postmeddelanden, webbadresser och bilagor till Microsoft finns i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="47eb9-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="47eb9-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="47eb9-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="47eb9-109">Öppna Säkerhets- och efterlevnadscentret på <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="47eb9-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="47eb9-110">Om du vill gå direkt till sidan **Inlämning** använder du <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="47eb9-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="47eb9-111">Du måste tilldelas behörigheter innan du kan göra procedurerna i det här avsnittet:</span><span class="sxs-lookup"><span data-stu-id="47eb9-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="47eb9-112">Om du vill skicka meddelanden och filer till Microsoft måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="47eb9-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="47eb9-113">**Organisationshantering** eller **säkerhetsadministratör** i [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="47eb9-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="47eb9-114">**Organisationshantering** eller **hygienhantering** i [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="47eb9-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="47eb9-115">För skrivskyddad åtkomst till portalen inlämningar måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="47eb9-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="47eb9-116">**Säkerhetsläsaren** i [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="47eb9-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="47eb9-117">**Endast visningsorganisation i** [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="47eb9-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="47eb9-118">Mer information om hur användare kan skicka meddelanden och filer till Microsoft finns i [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="47eb9-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="47eb9-119">Rapportera misstänkt innehåll till Microsoft</span><span class="sxs-lookup"><span data-stu-id="47eb9-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="47eb9-120">Gå till meddelanden om överföring av **Threat management** administratörer för & granskning \> **Review** \> **av**&.</span><span class="sxs-lookup"><span data-stu-id="47eb9-120">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="47eb9-121">Klicka på knappen **Ny inlämning** på sidan **Inlämningar** som visas.</span><span class="sxs-lookup"><span data-stu-id="47eb9-121">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="47eb9-122">Använd **Nytt överföringsutfällbart** överföringsutfällbart som visas för att skicka meddelandet, WEBBADRESSEN eller bilagan enligt beskrivningen i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="47eb9-122">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="47eb9-123">Skicka ett tvivelaktigt e-postmeddelande till Microsoft</span><span class="sxs-lookup"><span data-stu-id="47eb9-123">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="47eb9-124">Välj **E-post**i avsnittet **Objekttyp** .</span><span class="sxs-lookup"><span data-stu-id="47eb9-124">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="47eb9-125">I avsnittet **Inlämningsformat** använder du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="47eb9-125">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="47eb9-126">**Nätverksmeddelande-ID:** Det här är ett GUID-värde som är tillgängligt i **x-MS-Exchange-Organization-Network-Message-Id-huvudet** i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="47eb9-126">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="47eb9-127">**Arkiv**: Klicka på **Välj fil**.</span><span class="sxs-lookup"><span data-stu-id="47eb9-127">**File**: Click **Choose file**.</span></span> <span data-ttu-id="47eb9-128">Leta reda på och markera FILEN .eml eller .msg i dialogrutan som öppnas och klicka sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="47eb9-128">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="47eb9-129">I avsnittet **Mottagare** anger du en eller flera mottagare som du vill köra en principkontroll mot.</span><span class="sxs-lookup"><span data-stu-id="47eb9-129">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="47eb9-130">Principkontrollen avgör om e-postmeddelandet kringgås genomsökning på grund av användar- eller organisationsprinciper.</span><span class="sxs-lookup"><span data-stu-id="47eb9-130">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="47eb9-131">I avsnittet **Orsak till inlämning** väljer du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="47eb9-131">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="47eb9-132">**Borde inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="47eb9-132">**Should not have been blocked**</span></span>

   - <span data-ttu-id="47eb9-133">**Borde ha blockerats:** Välj **Skräppost,** **Nätfiske**eller **skadlig kod**.</span><span class="sxs-lookup"><span data-stu-id="47eb9-133">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="47eb9-134">Om du är osäker, använd ditt bästa omdöme.</span><span class="sxs-lookup"><span data-stu-id="47eb9-134">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="47eb9-135">Om filtret kringgådes på grund av principer vid inlämning visas information om den principen.</span><span class="sxs-lookup"><span data-stu-id="47eb9-135">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="47eb9-136">Om filtret inte kringgådes på grund av en eller flera principer slutförs genomsökningen på flera minuter.</span><span class="sxs-lookup"><span data-stu-id="47eb9-136">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="47eb9-137">Du ser ytterligare information om inlämningen genom att klicka på statuslänken.</span><span class="sxs-lookup"><span data-stu-id="47eb9-137">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="47eb9-138">Detta inkluderar resultaten av policykontrollen och återscan domen.</span><span class="sxs-lookup"><span data-stu-id="47eb9-138">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="47eb9-139">Observera att detta inte kör e-postmeddelandet via office 365 ATP full filtrering stack igen men kör en partiell omsökning baserat på vissa attribut för e-post, URL eller fil.</span><span class="sxs-lookup"><span data-stu-id="47eb9-139">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="47eb9-140">När du är klar klickar du på knappen **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="47eb9-140">When you're finished, click the **Submit** button.</span></span>

![Exempel på inskickad webbadress](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="47eb9-142">Skicka en misstänkt WEBBADRESS till Microsoft</span><span class="sxs-lookup"><span data-stu-id="47eb9-142">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="47eb9-143">Välj **URL**i avsnittet **Objekttyp** .</span><span class="sxs-lookup"><span data-stu-id="47eb9-143">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="47eb9-144">I rutan som visas anger du den fullständiga webbadressen (till exempel <https://www.fabrikam.com/marketing.html> ).</span><span class="sxs-lookup"><span data-stu-id="47eb9-144">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="47eb9-145">I avsnittet **Orsak till inlämning** väljer du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="47eb9-145">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="47eb9-146">**Borde inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="47eb9-146">**Should not have been blocked**</span></span>

   - <span data-ttu-id="47eb9-147">**Borde ha blockerats:** Välj **Nätfiske** eller **skadlig kod**.</span><span class="sxs-lookup"><span data-stu-id="47eb9-147">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="47eb9-148">När du är klar klickar du på knappen **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="47eb9-148">When you're finished, click the **Submit** button.</span></span>

![Exempel på inlämning av e-post](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="47eb9-150">Skicka en misstänkt fil till Microsoft</span><span class="sxs-lookup"><span data-stu-id="47eb9-150">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="47eb9-151">Välj **Bifogad fil**i avsnittet **Objekttyp** .</span><span class="sxs-lookup"><span data-stu-id="47eb9-151">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="47eb9-152">Klicka på **Välj fil**.</span><span class="sxs-lookup"><span data-stu-id="47eb9-152">Click **Choose File**.</span></span> <span data-ttu-id="47eb9-153">Leta reda på och markera filen i dialogrutan som öppnas och klicka sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="47eb9-153">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="47eb9-154">I avsnittet **Orsak till inlämning** väljer du något av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="47eb9-154">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="47eb9-155">**Borde inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="47eb9-155">**Should not have been blocked**</span></span>

   - <span data-ttu-id="47eb9-156">**Borde ha blockerats:** **Malware** är det enda valet, och väljs automatiskt..</span><span class="sxs-lookup"><span data-stu-id="47eb9-156">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="47eb9-157">När du är klar klickar du på knappen **Skicka.**</span><span class="sxs-lookup"><span data-stu-id="47eb9-157">When you're finished, click the **Submit** button.</span></span>

![Exempel på inlämning av bifogad fil](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="47eb9-159">Visa administratörsinlämningar</span><span class="sxs-lookup"><span data-stu-id="47eb9-159">View admin submissions</span></span>

1. <span data-ttu-id="47eb9-160">Gå till meddelanden om överföring av **Threat management** administratörer för & granskning \> **Review** \> **av**&.</span><span class="sxs-lookup"><span data-stu-id="47eb9-160">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="47eb9-161">Kontrollera att fliken **Administratörsöverföringar** är markerad på sidan **Inlämningar** som visas.</span><span class="sxs-lookup"><span data-stu-id="47eb9-161">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="47eb9-162">Högst upp på sidan kan du ange ett startdatum, ett slutdatum och (som standard) kan du filtrera efter **inlämnings-ID** genom att ange ett värde i rutan och klicka på Uppdatera.Up of the top of the page, you can enter a start date, an end date, and (by default) you can filter by Submission ID by entering a value in the box and ![ clicking Refresh button ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="47eb9-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="47eb9-163">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="47eb9-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="47eb9-164">Om du vill ändra filtervillkoren klickar du på knappen **Inlämnings-ID** och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="47eb9-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="47eb9-165">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="47eb9-165">**Sender**</span></span>
- <span data-ttu-id="47eb9-166">**Ämne/URL/Filnamn**</span><span class="sxs-lookup"><span data-stu-id="47eb9-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="47eb9-167">**Insänt av**</span><span class="sxs-lookup"><span data-stu-id="47eb9-167">**Submitted by**</span></span>
- <span data-ttu-id="47eb9-168">**Typ av inlämning**</span><span class="sxs-lookup"><span data-stu-id="47eb9-168">**Submission type**</span></span>
- <span data-ttu-id="47eb9-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="47eb9-169">**Status**</span></span>

![Filteralternativ för administratörsinlämningar](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="47eb9-171">Om du vill exportera resultaten klickar du på **Exportera** högst upp på sidan och väljer **Diagramdata** eller **Tabell**.</span><span class="sxs-lookup"><span data-stu-id="47eb9-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="47eb9-172">Spara CSV-filen i dialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="47eb9-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="47eb9-173">Under diagrammet finns tre flikar: **E-post** (standard), **URL**och **Bifogad fil**.</span><span class="sxs-lookup"><span data-stu-id="47eb9-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="47eb9-174">Visa e-postinlämningar för administratörer</span><span class="sxs-lookup"><span data-stu-id="47eb9-174">View admin email submissions</span></span>

<span data-ttu-id="47eb9-175">Klicka på fliken **E-post.**</span><span class="sxs-lookup"><span data-stu-id="47eb9-175">Click the **Email** tab.</span></span>

<span data-ttu-id="47eb9-176">Du kan klicka på knappen **Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner från vyn:</span><span class="sxs-lookup"><span data-stu-id="47eb9-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="47eb9-177">**Datum**</span><span class="sxs-lookup"><span data-stu-id="47eb9-177">**Date**</span></span>
- <span data-ttu-id="47eb9-178">**Inlämnings-ID**</span><span class="sxs-lookup"><span data-stu-id="47eb9-178">**Submission ID**</span></span>
- <span data-ttu-id="47eb9-179">**Insänt av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47eb9-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="47eb9-180">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47eb9-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="47eb9-181">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="47eb9-181">**Sender**</span></span>
- <span data-ttu-id="47eb9-182">**IP-adress för avsändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47eb9-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="47eb9-183">**Typ av inlämning**</span><span class="sxs-lookup"><span data-stu-id="47eb9-183">**Submission type**</span></span>
- <span data-ttu-id="47eb9-184">**Leveransorsak**</span><span class="sxs-lookup"><span data-stu-id="47eb9-184">**Delivery reason**</span></span>
- <span data-ttu-id="47eb9-185">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47eb9-185">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="47eb9-186">**Kontrolltyp**</span><span class="sxs-lookup"><span data-stu-id="47eb9-186">**Control type**</span></span>
- <span data-ttu-id="47eb9-187">**Kontrollkälla**</span><span class="sxs-lookup"><span data-stu-id="47eb9-187">**Control source**</span></span>

  <span data-ttu-id="47eb9-188"><sup>\*</sup>Om du klickar på det här värdet visas detaljerad information i ett utfällbart alternativ.</span><span class="sxs-lookup"><span data-stu-id="47eb9-188"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="47eb9-189">Visa inlämning av administratörs-URL</span><span class="sxs-lookup"><span data-stu-id="47eb9-189">View admin URL submissions</span></span>

<span data-ttu-id="47eb9-190">Klicka på fliken **URL.**</span><span class="sxs-lookup"><span data-stu-id="47eb9-190">Click the **URL** tab.</span></span>

<span data-ttu-id="47eb9-191">Du kan klicka på knappen **Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner från vyn:</span><span class="sxs-lookup"><span data-stu-id="47eb9-191">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="47eb9-192">**Datum**</span><span class="sxs-lookup"><span data-stu-id="47eb9-192">**Date**</span></span>
- <span data-ttu-id="47eb9-193">**Inlämnings-ID**</span><span class="sxs-lookup"><span data-stu-id="47eb9-193">**Submission ID**</span></span>
- <span data-ttu-id="47eb9-194">**Insänt av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47eb9-194">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="47eb9-195">**Url**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47eb9-195">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="47eb9-196">**Typ av inlämning**</span><span class="sxs-lookup"><span data-stu-id="47eb9-196">**Submission type**</span></span>
- <span data-ttu-id="47eb9-197">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47eb9-197">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="47eb9-198"><sup>\*</sup>Om du klickar på det här värdet visas detaljerad information i ett utfällbart alternativ.</span><span class="sxs-lookup"><span data-stu-id="47eb9-198"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="47eb9-199">Visa inlämningar av administratörsbelämning</span><span class="sxs-lookup"><span data-stu-id="47eb9-199">View admin attachment submissions</span></span>

<span data-ttu-id="47eb9-200">Klicka på fliken **Bifogade filer.**</span><span class="sxs-lookup"><span data-stu-id="47eb9-200">Click the **Attachments** tab.</span></span>

<span data-ttu-id="47eb9-201">Du kan klicka på knappen **Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner från vyn:</span><span class="sxs-lookup"><span data-stu-id="47eb9-201">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="47eb9-202">**Datum**</span><span class="sxs-lookup"><span data-stu-id="47eb9-202">**Date**</span></span>
- <span data-ttu-id="47eb9-203">**Inlämnings-ID**</span><span class="sxs-lookup"><span data-stu-id="47eb9-203">**Submission ID**</span></span>
- <span data-ttu-id="47eb9-204">**Insänt av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47eb9-204">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="47eb9-205">**Filnamn**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47eb9-205">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="47eb9-206">**Typ av inlämning**</span><span class="sxs-lookup"><span data-stu-id="47eb9-206">**Submission type**</span></span>
- <span data-ttu-id="47eb9-207">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47eb9-207">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="47eb9-208"><sup>\*</sup>Om du klickar på det här värdet visas detaljerad information i ett utfällbart alternativ.</span><span class="sxs-lookup"><span data-stu-id="47eb9-208"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="47eb9-209">Visa användarinlämningar till Microsoft</span><span class="sxs-lookup"><span data-stu-id="47eb9-209">View user submissions to Microsoft</span></span>

<span data-ttu-id="47eb9-210">Om du har distribuerat [tillägget Rapportmeddelande](enable-the-report-message-add-in.md)eller om personer använder den [inbyggda rapporteringen i Outlook på webben](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)kan du se vilka användare som rapporterar på fliken **Användares inlämningar.**</span><span class="sxs-lookup"><span data-stu-id="47eb9-210">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="47eb9-211">Gå till meddelanden om överföring av **Threat management** administratörer för & granskning \> **Review** \> **av**&.</span><span class="sxs-lookup"><span data-stu-id="47eb9-211">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="47eb9-212">Klicka på fliken **Användare inlämningar** på sidan **Inlämningar** som visas.</span><span class="sxs-lookup"><span data-stu-id="47eb9-212">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="47eb9-213">Du kan klicka på knappen **Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner från vyn:</span><span class="sxs-lookup"><span data-stu-id="47eb9-213">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="47eb9-214">**Insänt den**</span><span class="sxs-lookup"><span data-stu-id="47eb9-214">**Submitted on**</span></span>
- <span data-ttu-id="47eb9-215">**Insänt av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47eb9-215">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="47eb9-216">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47eb9-216">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="47eb9-217">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="47eb9-217">**Sender**</span></span>
- <span data-ttu-id="47eb9-218">**IP-adress för avsändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47eb9-218">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="47eb9-219">**Typ av inlämning**</span><span class="sxs-lookup"><span data-stu-id="47eb9-219">**Submission type**</span></span>

<span data-ttu-id="47eb9-220"><sup>\*</sup>Om du klickar på det här värdet visas detaljerad information i ett utfällbart alternativ.</span><span class="sxs-lookup"><span data-stu-id="47eb9-220"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="47eb9-221">Högst upp på sidan kan du ange ett startdatum, ett slutdatum och (som standard) som du kan filtrera efter **avsändare** genom att ange ett värde i rutan och klicka på Uppdatera.Up the top of the page, you can enter a start date, an end date, and (as default) you can filter by Sender by entering a value in the box and clicking ![ Refresh button ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="47eb9-221">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="47eb9-222">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="47eb9-222">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="47eb9-223">Om du vill ändra filtervillkoren klickar du på knappen **Avsändare** och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="47eb9-223">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="47eb9-224">**Avsändningsdomän**</span><span class="sxs-lookup"><span data-stu-id="47eb9-224">**Sender domain**</span></span>
- <span data-ttu-id="47eb9-225">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="47eb9-225">**Subject**</span></span>
- <span data-ttu-id="47eb9-226">**Insänt av**</span><span class="sxs-lookup"><span data-stu-id="47eb9-226">**Submitted by**</span></span>
- <span data-ttu-id="47eb9-227">**Typ av inlämning**</span><span class="sxs-lookup"><span data-stu-id="47eb9-227">**Submission type**</span></span>
- <span data-ttu-id="47eb9-228">**IP-adress för avsändare**</span><span class="sxs-lookup"><span data-stu-id="47eb9-228">**Sender IP**</span></span>

![Filteralternativ för användarinlämningar](../../media/user-submissions-filter-options.png)

<span data-ttu-id="47eb9-230">Om du vill exportera resultaten klickar du på **Exportera** högst upp på sidan och väljer **Diagramdata** eller **Tabell**.</span><span class="sxs-lookup"><span data-stu-id="47eb9-230">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="47eb9-231">Spara CSV-filen i dialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="47eb9-231">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="47eb9-232">Visa användaröverföringar till den anpassade postlådan</span><span class="sxs-lookup"><span data-stu-id="47eb9-232">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="47eb9-233">Om du har [konfigurerat en anpassad postlåda](user-submission.md) för att ta emot användarrapporterade meddelanden kan du visa och även skicka meddelanden som levererades till rapportpostlådan.</span><span class="sxs-lookup"><span data-stu-id="47eb9-233">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="47eb9-234">Gå till meddelanden om överföring av **Threat management** administratörer för & granskning \> **Review** \> **av**&.</span><span class="sxs-lookup"><span data-stu-id="47eb9-234">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="47eb9-235">Klicka på fliken **Anpassad postlåda** på sidan **Inlämningar** som visas.</span><span class="sxs-lookup"><span data-stu-id="47eb9-235">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="47eb9-236">Du kan klicka på knappen **Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner från vyn:</span><span class="sxs-lookup"><span data-stu-id="47eb9-236">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="47eb9-237">**Insänt den**</span><span class="sxs-lookup"><span data-stu-id="47eb9-237">**Submitted on**</span></span>
- <span data-ttu-id="47eb9-238">**Insänt av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47eb9-238">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="47eb9-239">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47eb9-239">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="47eb9-240">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="47eb9-240">**Sender**</span></span>
- <span data-ttu-id="47eb9-241">**IP-adress för avsändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="47eb9-241">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="47eb9-242">**Typ av inlämning**</span><span class="sxs-lookup"><span data-stu-id="47eb9-242">**Submission type**</span></span>

<span data-ttu-id="47eb9-243">Högst upp på sidan kan du ange ett startdatum, ett slutdatum och du kan filtrera efter **Skickad** genom att ange ett värde i rutan och klicka på ![ Uppdatera-knappen ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="47eb9-243">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="47eb9-244">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="47eb9-244">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="47eb9-245">Om du vill exportera resultaten klickar du på **Exportera** högst upp på sidan och väljer **Diagramdata** eller **Tabell**.</span><span class="sxs-lookup"><span data-stu-id="47eb9-245">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="47eb9-246">Spara CSV-filen i dialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="47eb9-246">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="47eb9-247">Skicka meddelanden till Microsoft från den anpassade postlådan</span><span class="sxs-lookup"><span data-stu-id="47eb9-247">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="47eb9-248">Om du har konfigurerat den anpassade postlådan för att avlyssna användarrapporterade meddelanden utan att skicka meddelandena till Microsoft kan du söka efter och skicka specifika meddelanden till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="47eb9-248">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="47eb9-249">Detta flyttar effektivt en användare inlämning till en administratör inlämning.</span><span class="sxs-lookup"><span data-stu-id="47eb9-249">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="47eb9-250">Markera ett meddelande i listan på fliken **Anpassad postlåda,** klicka på **knappen Åtgärd** och gör något av följande val:</span><span class="sxs-lookup"><span data-stu-id="47eb9-250">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="47eb9-251">**Rapporten är ren**</span><span class="sxs-lookup"><span data-stu-id="47eb9-251">**Report clean**</span></span>
- <span data-ttu-id="47eb9-252">**Rapportera nätfiske**</span><span class="sxs-lookup"><span data-stu-id="47eb9-252">**Report phishing**</span></span>
- <span data-ttu-id="47eb9-253">**Rapportera skadlig kod**</span><span class="sxs-lookup"><span data-stu-id="47eb9-253">**Report malware**</span></span>
- <span data-ttu-id="47eb9-254">**Rapportera skräppost**</span><span class="sxs-lookup"><span data-stu-id="47eb9-254">**Report spam**</span></span>

![Alternativ på knappen Åtgärd](../../media/user-submission-custom-mailbox-action-button.png)
