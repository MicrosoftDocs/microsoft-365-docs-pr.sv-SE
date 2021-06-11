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
description: Administratörer kan ta reda på hur de använder portalen för sändning i säkerhetscentret i Microsoft 365 för att skicka misstänkta e-postmeddelanden, misstänkta nätfiskemeddelanden, skräppost och andra potentiellt skadliga meddelanden, URL:er och e-postbilagor till Microsoft för att återsöka.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6de6a018a96407a5690249bea15e90c2f5a0d1ed
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878694"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="2d914-103">Använd administrationsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="2d914-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2d914-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="2d914-104">**Applies to**</span></span>
- [<span data-ttu-id="2d914-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2d914-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2d914-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="2d914-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="2d914-107">I Microsoft 365 organisationer med postlådor i Exchange Online kan administratörer använda portalen för inskickade meddelanden i säkerhets- och efterlevnadscentret för & för att skicka e-postmeddelanden, URL:er och bifogade filer till Microsoft för genomsökning.</span><span class="sxs-lookup"><span data-stu-id="2d914-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="2d914-108">När du skickar ett e-postmeddelande får du:</span><span class="sxs-lookup"><span data-stu-id="2d914-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="2d914-109">**Kontroll av e-postautentisering:** Information om e-postautentisering har godkänts eller misslyckats när den levererades.</span><span class="sxs-lookup"><span data-stu-id="2d914-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="2d914-110">**Principträffar:** Information om principer som kan ha tillåtit eller blockerat inkommande e-post i klientorganisationen, åsidosätter våra tjänstfilters bedömningar.</span><span class="sxs-lookup"><span data-stu-id="2d914-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="2d914-111">**Payload reputation/detonation**: Eng över alla URL:er och bifogade filer i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="2d914-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="2d914-112">**Gradersanalys:** Granska utförts av grader för att bekräfta om meddelanden är skadliga.</span><span class="sxs-lookup"><span data-stu-id="2d914-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2d914-113">Analys av berytning och gradering av nyttolast görs inte i alla klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="2d914-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="2d914-114">Information blockeras från att gå utanför organisationen när data inte ska lämna klientorganisationsgränsen i efterlevnadssyfte.</span><span class="sxs-lookup"><span data-stu-id="2d914-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="2d914-115">Andra sätt att skicka e-postmeddelanden, URL:er och bifogade filer till Microsoft finns i [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="2d914-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2d914-116">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="2d914-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2d914-117">Du öppnar säkerhetscentret Microsoft 365 på <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="2d914-117">You open the Microsoft 365 security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="2d914-118">Använd för att gå **direkt till sidan** Inskickade <https://security.microsoft.com/reportsubmission> material.</span><span class="sxs-lookup"><span data-stu-id="2d914-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="2d914-119">För att skicka meddelanden och filer till Microsoft måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="2d914-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="2d914-120">**Organisationshantering** eller **Säkerhetsläsare** i [Microsoft 365 Säkerhetscenter](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="2d914-120">**Organization Management** or **Security Reader** in the [Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>

  - <span data-ttu-id="2d914-121">**Organisationshantering** i [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="2d914-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="2d914-122">Observera att medlemskap i den här rollgruppen krävs för att [visa användarinskick till den anpassade postlådan enligt](#view-user-submissions-to-the-custom-mailbox) beskrivningen längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="2d914-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="2d914-123">Mer information om hur användare kan skicka meddelanden och filer till Microsoft finns i [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="2d914-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="2d914-124">Rapportera misstänkt innehåll till Microsoft</span><span class="sxs-lookup"><span data-stu-id="2d914-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="2d914-125">Gå till Microsoft 365 [i](../defender/overview-security-center.md)säkerhetscentret  och kontrollera att du är  på fliken Skickat för analys och klicka sedan på Skicka till **Microsoft för granskning.**</span><span class="sxs-lookup"><span data-stu-id="2d914-125">In the [Microsoft 365 security center](../defender/overview-security-center.md), go to **Submissions** and verify that you're on the **Submitted for analysis** tab, and then click **Submit to Microsoft for review**.</span></span>

2. <span data-ttu-id="2d914-126">Använd den **utfäll plats för Skicka** till Microsoft för granskning som ser ut att skicka en bifogad fil med meddelande, URL eller e-post enligt beskrivningen i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="2d914-126">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="2d914-127">Skicka ett tveksamt e-postmeddelande till Microsoft</span><span class="sxs-lookup"><span data-stu-id="2d914-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="2d914-128">Välj **E-post i** avsnittet Välj **överföringstyp.**</span><span class="sxs-lookup"><span data-stu-id="2d914-128">In the **Select the submission type** section, select **Email**.</span></span> <span data-ttu-id="2d914-129">Använd **något av följande alternativ i avsnittet Lägg till** nätverksmeddelande-ID eller ladda upp e-postfilen:</span><span class="sxs-lookup"><span data-stu-id="2d914-129">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>

   - <span data-ttu-id="2d914-130">Lägg till **meddelande-ID** för e-postnätverket: Det här är ett GUID-värde som är tillgängligt i rubriken **X-MS-Exchange-Organization-Network-Message-Id** i meddelandet eller i rubriken **X-MS-Office365-Filtering-Correlation-Id** i meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="2d914-130">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="2d914-131">**Upload e-postfilen:** Klicka på **Bläddra bland filer**.</span><span class="sxs-lookup"><span data-stu-id="2d914-131">**Upload the email file**: Click **Browse files**.</span></span> <span data-ttu-id="2d914-132">Leta rätt på och välj .eml- eller .msg-filen i dialogrutan som öppnas och klicka sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="2d914-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2d914-133">Möjligheten att skicka meddelanden som gamla som 30 dagar har tillfälligt stängts av för Defender för Office 365 kunder.</span><span class="sxs-lookup"><span data-stu-id="2d914-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="2d914-134">Administratörer kan bara gå tillbaka 7 dagar.</span><span class="sxs-lookup"><span data-stu-id="2d914-134">Admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="2d914-135">I avsnittet **Välj en mottagare som har ett problem** anger du den mottagare som du vill köra en principkontroll mot.</span><span class="sxs-lookup"><span data-stu-id="2d914-135">In the **Choose a recipient who had an issue** section, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="2d914-136">Principkontrollen avgör om förbikoppling av e-post beror på användar- eller organisationsprinciper.</span><span class="sxs-lookup"><span data-stu-id="2d914-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="2d914-137">Välj **något av följande alternativ i avsnittet Välj** en orsak för att skicka till Microsoft:</span><span class="sxs-lookup"><span data-stu-id="2d914-137">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>

   - <span data-ttu-id="2d914-138">**Borde inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="2d914-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="2d914-139">**Ska ha blockerats:** Välj **Skräppost,** **Nätfiske** eller **Skadlig kod.**</span><span class="sxs-lookup"><span data-stu-id="2d914-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="2d914-140">Om du är osäker kan du använda ditt bästa omdöme.</span><span class="sxs-lookup"><span data-stu-id="2d914-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="2d914-141">När du är klar klickar du på **skicka-knappen.**</span><span class="sxs-lookup"><span data-stu-id="2d914-141">When you're finished, click the **Submit** button.</span></span>

   ![Exempel på ny URL-inskickning](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="2d914-143">Skicka en misstänkt URL till Microsoft</span><span class="sxs-lookup"><span data-stu-id="2d914-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="2d914-144">I avsnittet **Välj överföringstyp** väljer du **URL**.</span><span class="sxs-lookup"><span data-stu-id="2d914-144">In the **Select the submission type** section, select **URL**.</span></span> <span data-ttu-id="2d914-145">I rutan som visas anger du den fullständiga webbadressen (till exempel `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="2d914-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="2d914-146">Välj **något av följande** alternativ i avsnittet Orsak till inskickning:</span><span class="sxs-lookup"><span data-stu-id="2d914-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="2d914-147">**Borde inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="2d914-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="2d914-148">**Ska ha blockerats:** Välj **Nätfiske** eller **skadlig kod.**</span><span class="sxs-lookup"><span data-stu-id="2d914-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="2d914-149">När du är klar klickar du på **skicka-knappen.**</span><span class="sxs-lookup"><span data-stu-id="2d914-149">When you're finished, click the **Submit** button.</span></span>

   ![Exempel på ny e-postinskickning](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="2d914-151">Skicka en misstänkt e-postbilaga till Microsoft</span><span class="sxs-lookup"><span data-stu-id="2d914-151">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="2d914-152">I avsnittet **Välj typ av inskickning väljer** du Bifogad fil i **e-post**.</span><span class="sxs-lookup"><span data-stu-id="2d914-152">In the **Select the submission type** section, select **Email attachment**.</span></span>

2. <span data-ttu-id="2d914-153">Klicka **på Välj fil**.</span><span class="sxs-lookup"><span data-stu-id="2d914-153">Click **Choose File**.</span></span> <span data-ttu-id="2d914-154">Leta rätt på och markera filen i dialogrutan som öppnas och klicka sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="2d914-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="2d914-155">Välj **något av följande** alternativ i avsnittet Orsak till inskickning:</span><span class="sxs-lookup"><span data-stu-id="2d914-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="2d914-156">**Borde inte ha blockerats**</span><span class="sxs-lookup"><span data-stu-id="2d914-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="2d914-157">**Borde ha blockerats:** **Skadlig programvara** är det enda alternativet och väljs automatiskt.</span><span class="sxs-lookup"><span data-stu-id="2d914-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="2d914-158">När du är klar klickar du på **skicka-knappen.**</span><span class="sxs-lookup"><span data-stu-id="2d914-158">When you're finished, click the **Submit** button.</span></span>

   ![Exempel på ny inskickade bifogade filer](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a><span data-ttu-id="2d914-160">Visa objekt som skickats för analys</span><span class="sxs-lookup"><span data-stu-id="2d914-160">View items Submitted for analysis</span></span>

<span data-ttu-id="2d914-161">I säkerhetscentret Microsoft 365 du till **Inlämningar** och kontrollerar att du är på fliken **Skickat för** analys</span><span class="sxs-lookup"><span data-stu-id="2d914-161">In the Microsoft 365 security center, go to **Submissions**, and verify that you're on the **Submitted for analysis** tab</span></span>

<span data-ttu-id="2d914-162">I kommandofältet i mitten av sidan kan du ange ett startdatum, ett slutdatum och (som standard) kan du filtrera efter **Sändnings-ID** (ett GUID-värde som är kopplat till varje inskickat värde) genom att ange ett värde i rutan och klicka på ![ ](../../media/scc-quarantine-refresh.png) Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="2d914-162">In the command bar in the middle of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="2d914-163">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="2d914-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="2d914-164">Om du vill ändra filtervillkoren klickar **du på knappen** Filter och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="2d914-164">To change the filter criteria, click the **Filter** button and choose one of the following values:</span></span>

- <span data-ttu-id="2d914-165">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="2d914-165">**Sender**</span></span>
- <span data-ttu-id="2d914-166">**Ämne/URL/Filnamn**</span><span class="sxs-lookup"><span data-stu-id="2d914-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="2d914-167">**Skickat av**</span><span class="sxs-lookup"><span data-stu-id="2d914-167">**Submitted by**</span></span>
- <span data-ttu-id="2d914-168">**Typ av inskickat material**</span><span class="sxs-lookup"><span data-stu-id="2d914-168">**Submission type**</span></span>
- <span data-ttu-id="2d914-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="2d914-169">**Status**</span></span>

![Nya filteralternativ för administratörsinskick](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="2d914-171">Om du vill exportera resultaten klickar **du på** Exportera högst upp på sidan och väljer **Diagramdata** eller **Tabell.**</span><span class="sxs-lookup"><span data-stu-id="2d914-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="2d914-172">I dialogrutan som visas sparar du den .csv filen.</span><span class="sxs-lookup"><span data-stu-id="2d914-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="2d914-173">Under diagrammet finns tre flikar: **E-post** (standard), URL och E-postbilaga .  </span><span class="sxs-lookup"><span data-stu-id="2d914-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Email attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="2d914-174">Visa e-postinskick från administratör</span><span class="sxs-lookup"><span data-stu-id="2d914-174">View admin email submissions</span></span>

<span data-ttu-id="2d914-175">Du kan lägga till **eller ta bort** kolumner från vyn genom att klicka på knappen Anpassa kolumner nästan längst ned på sidan:</span><span class="sxs-lookup"><span data-stu-id="2d914-175">You can click the **Customize columns** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="2d914-176">**Datum**</span><span class="sxs-lookup"><span data-stu-id="2d914-176">**Date**</span></span>
- <span data-ttu-id="2d914-177">**Överförings-ID:** Ett GUID-värde som tilldelas till varje sändning.</span><span class="sxs-lookup"><span data-stu-id="2d914-177">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="2d914-178">**Skickat av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2d914-178">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="2d914-179">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2d914-179">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="2d914-180">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="2d914-180">**Sender**</span></span>
- <span data-ttu-id="2d914-181">**Sender IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2d914-181">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="2d914-182">**Typ av inskickat material**</span><span class="sxs-lookup"><span data-stu-id="2d914-182">**Submission type**</span></span>
- <span data-ttu-id="2d914-183">**Leveransorsak**</span><span class="sxs-lookup"><span data-stu-id="2d914-183">**Delivery reason**</span></span>
- <span data-ttu-id="2d914-184">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2d914-184">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="2d914-185"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfäll tillgänglig plats.</span><span class="sxs-lookup"><span data-stu-id="2d914-185"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="2d914-186">Information om administratörsinskickning igen</span><span class="sxs-lookup"><span data-stu-id="2d914-186">Admin submission rescan details</span></span>

<span data-ttu-id="2d914-187">Meddelanden som skickas i administrationsinskick genomsöks på annat sätt och resultaten visas i den utfällkommning som visas i inskickade uppgifter:</span><span class="sxs-lookup"><span data-stu-id="2d914-187">Messages that are submitted in admin submissions are rescanned and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="2d914-188">Om avsändarens e-postautentisering misslyckades vid leveransen.</span><span class="sxs-lookup"><span data-stu-id="2d914-188">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="2d914-189">Information om politiska träffar som kan ha påverkat eller åsidosatt bedömningen av ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="2d914-189">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="2d914-190">Aktuella detonationsresultat för att se om webbadresserna eller filerna i meddelandet var skadliga eller inte.</span><span class="sxs-lookup"><span data-stu-id="2d914-190">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="2d914-191">Feedback från grader.</span><span class="sxs-lookup"><span data-stu-id="2d914-191">Feedback from graders.</span></span>

<span data-ttu-id="2d914-192">Om en åsidosättning hittades bör omskanningen slutföras på några minuter.</span><span class="sxs-lookup"><span data-stu-id="2d914-192">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="2d914-193">Om det inte uppstod något problem i e-postautentisering eller -leverans påverkades inte av en åsidosättning, kan feedback från grader ta upp till en dag.</span><span class="sxs-lookup"><span data-stu-id="2d914-193">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="2d914-194">Visa url-inskickade administratörs-URL</span><span class="sxs-lookup"><span data-stu-id="2d914-194">View admin URL submissions</span></span>

<span data-ttu-id="2d914-195">Klicka på **fliken URL.**</span><span class="sxs-lookup"><span data-stu-id="2d914-195">Click the **URL** tab.</span></span>

<span data-ttu-id="2d914-196">Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="2d914-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="2d914-197">**Datum**</span><span class="sxs-lookup"><span data-stu-id="2d914-197">**Date**</span></span>
- <span data-ttu-id="2d914-198">**Sändnings-ID**</span><span class="sxs-lookup"><span data-stu-id="2d914-198">**Submission ID**</span></span>
- <span data-ttu-id="2d914-199">**Skickat av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2d914-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="2d914-200">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2d914-200">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="2d914-201">**Typ av inskickat material**</span><span class="sxs-lookup"><span data-stu-id="2d914-201">**Submission type**</span></span>
- <span data-ttu-id="2d914-202">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2d914-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="2d914-203"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfäll tillgänglig plats.</span><span class="sxs-lookup"><span data-stu-id="2d914-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-email-attachment-submissions"></a><span data-ttu-id="2d914-204">Visa inskickade e-postbilalar</span><span class="sxs-lookup"><span data-stu-id="2d914-204">View email attachment submissions</span></span>

<span data-ttu-id="2d914-205">Klicka på **fliken Bifogade** filer.</span><span class="sxs-lookup"><span data-stu-id="2d914-205">Click the **Attachments** tab.</span></span>

<span data-ttu-id="2d914-206">Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="2d914-206">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="2d914-207">**Datum**</span><span class="sxs-lookup"><span data-stu-id="2d914-207">**Date**</span></span>
- <span data-ttu-id="2d914-208">**Sändnings-ID**</span><span class="sxs-lookup"><span data-stu-id="2d914-208">**Submission ID**</span></span>
- <span data-ttu-id="2d914-209">**Skickat av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2d914-209">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="2d914-210">**Filnamn**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2d914-210">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="2d914-211">**Typ av inskickat material**</span><span class="sxs-lookup"><span data-stu-id="2d914-211">**Submission type**</span></span>
- <span data-ttu-id="2d914-212">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2d914-212">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="2d914-213"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfäll tillgänglig plats.</span><span class="sxs-lookup"><span data-stu-id="2d914-213"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="2d914-214">Visa användarinskick till Microsoft</span><span class="sxs-lookup"><span data-stu-id="2d914-214">View user submissions to Microsoft</span></span>

<span data-ttu-id="2d914-215">Om du har distribuerat tillägget Rapportmeddelande, [](enable-the-report-phish-add-in.md) [](enable-the-report-message-add-in.md)tillägget Rapportfiske eller om användarna använder den [inbyggda](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)rapporteringen i Outlook på webben kan  du se vad användarna rapporterar på fliken Användarinsändning.</span><span class="sxs-lookup"><span data-stu-id="2d914-215">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="2d914-216">I Säkerhets- & efterlevnadscenter går du till **Sändning av** \> **hothantering.**</span><span class="sxs-lookup"><span data-stu-id="2d914-216">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="2d914-217">Välj fliken **Användarinskickningar** och klicka sedan på **Ny inskicking.**</span><span class="sxs-lookup"><span data-stu-id="2d914-217">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="2d914-218">Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="2d914-218">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="2d914-219">**Skickat**</span><span class="sxs-lookup"><span data-stu-id="2d914-219">**Submitted on**</span></span>
- <span data-ttu-id="2d914-220">**Skickat av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2d914-220">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="2d914-221">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2d914-221">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="2d914-222">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="2d914-222">**Sender**</span></span>
- <span data-ttu-id="2d914-223">**Sender IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2d914-223">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="2d914-224">**Typ av inskickat material**</span><span class="sxs-lookup"><span data-stu-id="2d914-224">**Submission type**</span></span>

<span data-ttu-id="2d914-225"><sup>\*</sup> Om du klickar på det här värdet visas detaljerad information i en utfäll tillgänglig plats.</span><span class="sxs-lookup"><span data-stu-id="2d914-225"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="2d914-226">Högst upp på sidan kan du ange ett startdatum, ett slutdatum och (som  standard) kan du filtrera efter avsändare genom att ange ett värde i rutan och klicka på ![ Uppdatera ](../../media/scc-quarantine-refresh.png) knapp.</span><span class="sxs-lookup"><span data-stu-id="2d914-226">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="2d914-227">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="2d914-227">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="2d914-228">Om du vill ändra filtervillkor klickar du **på knappen** Avsändare och väljer något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="2d914-228">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="2d914-229">**Avsändningsdomän**</span><span class="sxs-lookup"><span data-stu-id="2d914-229">**Sender domain**</span></span>
- <span data-ttu-id="2d914-230">**Ämne**</span><span class="sxs-lookup"><span data-stu-id="2d914-230">**Subject**</span></span>
- <span data-ttu-id="2d914-231">**Skickat av**</span><span class="sxs-lookup"><span data-stu-id="2d914-231">**Submitted by**</span></span>
- <span data-ttu-id="2d914-232">**Typ av inskickat material**</span><span class="sxs-lookup"><span data-stu-id="2d914-232">**Submission type**</span></span>
- <span data-ttu-id="2d914-233">**Sender IP**</span><span class="sxs-lookup"><span data-stu-id="2d914-233">**Sender IP**</span></span>

![Nya filteralternativ för användarinskick](../../media/user-submissions-filter-options.png)

<span data-ttu-id="2d914-235">Om du vill exportera resultaten klickar **du på** Exportera högst upp på sidan och väljer **Diagramdata** eller **Tabell.**</span><span class="sxs-lookup"><span data-stu-id="2d914-235">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="2d914-236">I dialogrutan som visas sparar du den .csv filen.</span><span class="sxs-lookup"><span data-stu-id="2d914-236">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="2d914-237">Visa användarinskick till den anpassade postlådan</span><span class="sxs-lookup"><span data-stu-id="2d914-237">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="2d914-238">**Om** du har konfigurerat [en anpassad postlåda för](user-submission.md) att ta emot användarrapporterade meddelanden kan du visa och skicka meddelanden som har levererats till den rapportpostlådan.</span><span class="sxs-lookup"><span data-stu-id="2d914-238">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="2d914-239">I Säkerhets- & efterlevnadscenter går du till **Sändning av** \> **hothantering.**</span><span class="sxs-lookup"><span data-stu-id="2d914-239">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="2d914-240">Välj fliken **Anpassad** postlåda.</span><span class="sxs-lookup"><span data-stu-id="2d914-240">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="2d914-241">Du kan klicka på **knappen Kolumnalternativ** längst ned på sidan om du vill lägga till eller ta bort kolumner i vyn:</span><span class="sxs-lookup"><span data-stu-id="2d914-241">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="2d914-242">**Skickat**</span><span class="sxs-lookup"><span data-stu-id="2d914-242">**Submitted on**</span></span>
- <span data-ttu-id="2d914-243">**Skickat av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2d914-243">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="2d914-244">**Ämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2d914-244">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="2d914-245">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="2d914-245">**Sender**</span></span>
- <span data-ttu-id="2d914-246">**Sender IP**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2d914-246">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="2d914-247">**Typ av inskickat material**</span><span class="sxs-lookup"><span data-stu-id="2d914-247">**Submission type**</span></span>

<span data-ttu-id="2d914-248">Högst upp på sidan kan du ange ett startdatum, ett slutdatum och du kan filtrera efter **Skickat** genom att ange ett värde i rutan och klicka på ![ ](../../media/scc-quarantine-refresh.png) Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="2d914-248">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="2d914-249">Du kan ange flera värden avgränsade med kommatecken.</span><span class="sxs-lookup"><span data-stu-id="2d914-249">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="2d914-250">Om du vill exportera resultaten klickar **du på** Exportera högst upp på sidan och väljer **Diagramdata** eller **Tabell.**</span><span class="sxs-lookup"><span data-stu-id="2d914-250">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="2d914-251">I dialogrutan som visas sparar du den .csv filen.</span><span class="sxs-lookup"><span data-stu-id="2d914-251">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="2d914-252">Om organisationer är konfigurerade att endast skicka till en anpassad postlåda skickas inte rapporterade meddelanden för sökning och resultat i portalen för användarrapporter är alltid tomma.</span><span class="sxs-lookup"><span data-stu-id="2d914-252">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="2d914-253">Ångra användarinskick</span><span class="sxs-lookup"><span data-stu-id="2d914-253">Undo user submissions</span></span>

<span data-ttu-id="2d914-254">När en användare skickar ett misstänkt e-postmeddelande till den anpassade postlådan kan användaren och administratören inte ångra inskickat material.</span><span class="sxs-lookup"><span data-stu-id="2d914-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="2d914-255">Om användaren vill återställa e-posten kan den återställas i mapparna Borttagna objekt eller Skräppost.</span><span class="sxs-lookup"><span data-stu-id="2d914-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="2d914-256">Skicka meddelanden till Microsoft från den anpassade postlådan</span><span class="sxs-lookup"><span data-stu-id="2d914-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="2d914-257">Om du har konfigurerat den anpassade postlådan för att snappa upp användarrapporterade meddelanden utan att skicka meddelanden till Microsoft kan du hitta och skicka specifika meddelanden till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="2d914-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="2d914-258">Då flyttas en användarinskickning till en administratörsinskickning.</span><span class="sxs-lookup"><span data-stu-id="2d914-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="2d914-259">På fliken **Användarrapporterade** meddelanden väljer du ett  meddelande i listan, klickar på knappen Åtgärd och gör ett av följande val:</span><span class="sxs-lookup"><span data-stu-id="2d914-259">On the **User reported messages** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="2d914-260">**Rapportrensning**</span><span class="sxs-lookup"><span data-stu-id="2d914-260">**Report clean**</span></span>
- <span data-ttu-id="2d914-261">**Rapportera nätfiske**</span><span class="sxs-lookup"><span data-stu-id="2d914-261">**Report phishing**</span></span>
- <span data-ttu-id="2d914-262">**Rapportera skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="2d914-262">**Report malware**</span></span>
- <span data-ttu-id="2d914-263">**Rapportera skräppost**</span><span class="sxs-lookup"><span data-stu-id="2d914-263">**Report spam**</span></span>

![Nya alternativ på knappen Åtgärd](../../media/user-submission-custom-mailbox-action-button.png)
