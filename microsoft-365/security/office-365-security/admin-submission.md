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
description: Administratörer kan ta reda på hur de använder portalen för inskickade innehåll i Microsoft 365 Defender-portalen för att skicka misstänkta e-postmeddelanden, misstänkta nätfiskemeddelanden, skräppost och andra potentiellt skadliga meddelanden, URL-adresser och e-postbilagor till Microsoft för att återsöka.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eecb635972be85e1a1a4f95c2786f209ee249745
ms.sourcegitcommit: 99e67bfe1d677c2f51712b05dcc54908b343cf6f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53203286"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="19f68-103">Använd administrationsinskick för att skicka misstänkt skräppost, nättr ut, URL:er och filer till Microsoft</span><span class="sxs-lookup"><span data-stu-id="19f68-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="19f68-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="19f68-104">**Applies to**</span></span>
- [<span data-ttu-id="19f68-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="19f68-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="19f68-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="19f68-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="19f68-107">I Microsoft 365 organisationer med Exchange Online postlådor kan administratörer använda portalen för inskickade material i Microsoft 365 Defender-portalen för att skicka e-postmeddelanden, URL-adresser och bifogade filer till Microsoft för genomsökning.</span><span class="sxs-lookup"><span data-stu-id="19f68-107">In Microsoft 365 organizations with Exchange Online mailboxes, admins can use the Submissions portal in the Microsoft 365 Defender portal to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="19f68-108">När du skickar ett e-postmeddelande får du:</span><span class="sxs-lookup"><span data-stu-id="19f68-108">When you submit an email message, you will get:</span></span>

- <span data-ttu-id="19f68-109">**Kontroll av e-postautentisering:** Information om e-postautentisering har godkänts eller misslyckats när den levererades.</span><span class="sxs-lookup"><span data-stu-id="19f68-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
- <span data-ttu-id="19f68-110">**Principträffar:** Information om principer som kan ha tillåtit eller blockerat inkommande e-post i klientorganisationen, åsidosätter våra tjänstfilters bedömningar.</span><span class="sxs-lookup"><span data-stu-id="19f68-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
- <span data-ttu-id="19f68-111">**Payload reputation/detonation**: Eng över alla URL:er och bifogade filer i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="19f68-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
- <span data-ttu-id="19f68-112">**Gradersanalys:** Granska utförts av grader för att bekräfta om meddelanden är skadliga.</span><span class="sxs-lookup"><span data-stu-id="19f68-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="19f68-113">Analys av berytning och gradering av nyttolast görs inte i alla klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="19f68-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="19f68-114">Information blockeras från att gå utanför organisationen när data inte ska lämna klientorganisationsgränsen i efterlevnadssyfte.</span><span class="sxs-lookup"><span data-stu-id="19f68-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="19f68-115">Andra sätt att skicka e-postmeddelanden, URL:er och bifogade filer till Microsoft finns i [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="19f68-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="19f68-116">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="19f68-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="19f68-117">Du kan öppna Microsoft 365 Defender-portalen genom att gå till <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="19f68-117">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="19f68-118">Använd för att gå **direkt till sidan** Inskickade <https://security.microsoft.com/reportsubmission> material.</span><span class="sxs-lookup"><span data-stu-id="19f68-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="19f68-119">För att skicka meddelanden och filer till Microsoft måste du vara medlem i någon av följande rollgrupper:</span><span class="sxs-lookup"><span data-stu-id="19f68-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="19f68-120">**Organisationshantering** eller **säkerhetsläsare** i [Microsoft 365 Defender .](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="19f68-120">**Organization Management** or **Security Reader** in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  
    <span data-ttu-id="19f68-121">Observera att medlemskap i den här rollgruppen krävs för att [visa användarinskick till den anpassade postlådan enligt](#view-user-submissions-to-microsoft) beskrivningen längre fram i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="19f68-121">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-microsoft) as described later in this article.</span></span>

- <span data-ttu-id="19f68-122">Mer information om hur användare kan skicka meddelanden och filer till Microsoft finns i [Rapportera meddelanden och filer till Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="19f68-122">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="19f68-123">Rapportera misstänkt innehåll till Microsoft</span><span class="sxs-lookup"><span data-stu-id="19f68-123">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="19f68-124">I Microsoft 365 Defender går du till Skicka **e-& och** \> **samarbetsinskick.**</span><span class="sxs-lookup"><span data-stu-id="19f68-124">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="19f68-125">På sidan **Inskickade** kontrollerar du att fliken **Skickat** för analys är markerad och klickar sedan på Annonsikon ![ skicka till Microsoft för ](../../media/m365-cc-sc-create-icon.png) **analys.**</span><span class="sxs-lookup"><span data-stu-id="19f68-125">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected, and then click ![Ad icon](../../media/m365-cc-sc-create-icon.png) **Submit to Microsoft for analysis**.</span></span>

3. <span data-ttu-id="19f68-126">Använd den **utfäll plats för Skicka** till Microsoft för granskning som ser ut att skicka en bifogad fil med meddelande, URL eller e-post enligt beskrivningen i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="19f68-126">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="19f68-127">Skicka ett tveksamt e-postmeddelande till Microsoft</span><span class="sxs-lookup"><span data-stu-id="19f68-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="19f68-128">I rutan **Välj typ av inskickning** kontrollerar du att **E-post** är valt i listrutan.</span><span class="sxs-lookup"><span data-stu-id="19f68-128">In the **Select the submission type** box, verify that **Email** is selected in the drop down list.</span></span>

2. <span data-ttu-id="19f68-129">Använd **något av följande alternativ i avsnittet Lägg till** nätverksmeddelande-ID eller ladda upp e-postfilen:</span><span class="sxs-lookup"><span data-stu-id="19f68-129">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>
   - <span data-ttu-id="19f68-130">Lägg till **meddelande-ID** för e-postnätverket: Det här är ett GUID-värde som är tillgängligt i rubriken **X-MS-Exchange-Organization-Network-Message-Id** i meddelandet eller i rubriken **X-MS-Office365-Filtering-Correlation-Id** i meddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="19f68-130">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>
   - <span data-ttu-id="19f68-131">**Upload e-postfilen (.msg eller .eml)**: Klicka på **Bläddra bland filer.**</span><span class="sxs-lookup"><span data-stu-id="19f68-131">**Upload the email file (.msg or .eml)**: Click **Browse files**.</span></span> <span data-ttu-id="19f68-132">Leta rätt på och välj .eml- eller .msg-filen i dialogrutan som öppnas och klicka sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="19f68-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="19f68-133">Möjligheten att skicka meddelanden som gamla som 30 dagar har tillfälligt stängts av för Defender för Office 365 kunder.</span><span class="sxs-lookup"><span data-stu-id="19f68-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="19f68-134">Administratörer kan bara gå tillbaka 7 dagar.</span><span class="sxs-lookup"><span data-stu-id="19f68-134">Admins will only be able to go back 7 days.</span></span>

3. <span data-ttu-id="19f68-135">I rutan **Välj en mottagare som har ett problem** anger du den mottagare som du vill köra en principkontroll mot.</span><span class="sxs-lookup"><span data-stu-id="19f68-135">In the **Choose a recipient who had an issue** box, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="19f68-136">Principkontrollen avgör om förbikoppling av e-post beror på användar- eller organisationsprinciper.</span><span class="sxs-lookup"><span data-stu-id="19f68-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

4. <span data-ttu-id="19f68-137">Välj **något av följande alternativ i avsnittet Välj** en orsak för att skicka till Microsoft:</span><span class="sxs-lookup"><span data-stu-id="19f68-137">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="19f68-138">**Bör inte ha blockerats (falskt positivt resultat)**</span><span class="sxs-lookup"><span data-stu-id="19f68-138">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="19f68-139">**Borde ha blockerats:**  I e-postmeddelandet ska ha kategoriserats som avsnitt som visas väljer du ett av följande värden (om du är osäker kan du använda bästa möjliga metod):</span><span class="sxs-lookup"><span data-stu-id="19f68-139">**Should have been blocked**: In the **The email should have been categorized as** section that appears, select one of the following values (if you're not sure, use your best judgement):</span></span>
     - <span data-ttu-id="19f68-140">**Nätfiske**</span><span class="sxs-lookup"><span data-stu-id="19f68-140">**Phish**</span></span>
     - <span data-ttu-id="19f68-141">**Skräppost**</span><span class="sxs-lookup"><span data-stu-id="19f68-141">**Spam**</span></span>
     - <span data-ttu-id="19f68-142">**Skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="19f68-142">**Malware**</span></span>

5. <span data-ttu-id="19f68-143">När du är klar klickar du på **skicka-knappen.**</span><span class="sxs-lookup"><span data-stu-id="19f68-143">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="19f68-144">![Exempel på ny URL-inskickning](../../media/submission-flyout-email.png)</span><span class="sxs-lookup"><span data-stu-id="19f68-144">![New URL submission example](../../media/submission-flyout-email.png)</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="19f68-145">Skicka en misstänkt URL till Microsoft</span><span class="sxs-lookup"><span data-stu-id="19f68-145">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="19f68-146">I rutan **Välj överföringstyp** väljer du **URL** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="19f68-146">In the **Select the submission type** box, select **URL** from the drop down list.</span></span>

2. <span data-ttu-id="19f68-147">I rutan **URL** som visas anger du den fullständiga webbadressen (till exempel `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="19f68-147">In the **URL** box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

3. <span data-ttu-id="19f68-148">Välj **något av följande alternativ i avsnittet Välj** en orsak för att skicka till Microsoft:</span><span class="sxs-lookup"><span data-stu-id="19f68-148">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="19f68-149">**Bör inte ha blockerats (falskt positivt resultat)**</span><span class="sxs-lookup"><span data-stu-id="19f68-149">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="19f68-150">**Borde ha blockerats:** I avsnittet Den **här url:en** borde ha kategoriserats som ett avsnitt som visas väljer du **Phish eller** **Malware**.</span><span class="sxs-lookup"><span data-stu-id="19f68-150">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, select **Phish** or **Malware**.</span></span>

4. <span data-ttu-id="19f68-151">När du är klar klickar du på **skicka-knappen.**</span><span class="sxs-lookup"><span data-stu-id="19f68-151">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="19f68-152">![Exempel på ny e-postinskickning](../../media/submission-url-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="19f68-152">![New Email submission example](../../media/submission-url-flyout.png)</span></span>

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="19f68-153">Skicka en misstänkt e-postbilaga till Microsoft</span><span class="sxs-lookup"><span data-stu-id="19f68-153">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="19f68-154">I rutan **Välj typ av inskickning** väljer **du Arkiv** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="19f68-154">In the **Select the submission type** box, select **File** from the drop down list.</span></span>

2. <span data-ttu-id="19f68-155">I avsnittet **Arkiv** som visas klickar du på **Bläddra bland filer**.</span><span class="sxs-lookup"><span data-stu-id="19f68-155">In the **File** section that appears, click **Browse files**.</span></span> <span data-ttu-id="19f68-156">Leta rätt på och markera filen i dialogrutan som öppnas och klicka sedan på **Öppna**.</span><span class="sxs-lookup"><span data-stu-id="19f68-156">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="19f68-157">Välj **något av följande alternativ i avsnittet Välj** en orsak för att skicka till Microsoft:</span><span class="sxs-lookup"><span data-stu-id="19f68-157">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="19f68-158">**Bör inte ha blockerats (falskt positivt resultat)**</span><span class="sxs-lookup"><span data-stu-id="19f68-158">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="19f68-159">**Borde ha blockerats:** I avsnittet Den här **webbadressen** borde  ha kategoriserats som visas är Skadlig programvara det enda alternativet och väljs automatiskt.</span><span class="sxs-lookup"><span data-stu-id="19f68-159">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="19f68-160">När du är klar klickar du på **skicka-knappen.**</span><span class="sxs-lookup"><span data-stu-id="19f68-160">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="19f68-161">![Exempel på ny inskickade bifogade filer](../../media/submission-file-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="19f68-161">![New Attachment submission example](../../media/submission-file-flyout.png)</span></span>

## <a name="view-admin-submissions-to-microsoft"></a><span data-ttu-id="19f68-162">Visa administrationsinskick till Microsoft</span><span class="sxs-lookup"><span data-stu-id="19f68-162">View admin submissions to Microsoft</span></span>

1. <span data-ttu-id="19f68-163">I Microsoft 365 Defender går du till Skicka **e-& och** \> **samarbetsinskick.**</span><span class="sxs-lookup"><span data-stu-id="19f68-163">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="19f68-164">På sidan **Inlämnade uppgifter** kontrollerar du att fliken **Skickat för** analys är markerad.</span><span class="sxs-lookup"><span data-stu-id="19f68-164">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected.</span></span>

   - <span data-ttu-id="19f68-165">Du kan sortera posterna genom att klicka på en tillgänglig kolumnrubrik.</span><span class="sxs-lookup"><span data-stu-id="19f68-165">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="19f68-166">Klicka **på Anpassa** kolumner för att visa maximalt sju kolumner.</span><span class="sxs-lookup"><span data-stu-id="19f68-166">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="19f68-167">Standardvärdena är markerade med en asterisk (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="19f68-167">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>
     - <span data-ttu-id="19f68-168">**Namn på inskickat material**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19f68-168">**Submission name**<sup>\*</sup></span></span>
     - <span data-ttu-id="19f68-169">**Avsändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19f68-169">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="19f68-170">**Skickat**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19f68-170">**Date submitted**<sup>\*</sup></span></span>
     - <span data-ttu-id="19f68-171">**Typ av inskickat material**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19f68-171">**Submission type**<sup>\*</sup></span></span>
     - <span data-ttu-id="19f68-172">**Orsak till att skicka in**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19f68-172">**Reason for submitting**<sup>\*</sup></span></span>
     - <span data-ttu-id="19f68-173">**Rescan-status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19f68-173">**Rescan status**<sup>\*</sup></span></span>
     - <span data-ttu-id="19f68-174">**Rescan-resultat**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19f68-174">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="19f68-175">**Filtrera bedömning**</span><span class="sxs-lookup"><span data-stu-id="19f68-175">**Filter verdict**</span></span>
     - <span data-ttu-id="19f68-176">**Leverans-/blockeringsorsak**</span><span class="sxs-lookup"><span data-stu-id="19f68-176">**Delivery/Block reason**</span></span>
     - <span data-ttu-id="19f68-177">**Sändnings-ID**</span><span class="sxs-lookup"><span data-stu-id="19f68-177">**Submission ID**</span></span>
     - <span data-ttu-id="19f68-178">**Id för nätverksmeddelande/objekt-ID**</span><span class="sxs-lookup"><span data-stu-id="19f68-178">**Network Message ID/Object ID**</span></span>
     - <span data-ttu-id="19f68-179">**Riktning**</span><span class="sxs-lookup"><span data-stu-id="19f68-179">**Direction**</span></span>
     - <span data-ttu-id="19f68-180">**Sender IP**</span><span class="sxs-lookup"><span data-stu-id="19f68-180">**Sender IP**</span></span>
     - <span data-ttu-id="19f68-181">**BCL (Bulk compliant level)**</span><span class="sxs-lookup"><span data-stu-id="19f68-181">**Bulk compliant level (BCL)**</span></span>
     - <span data-ttu-id="19f68-182">**Destination**</span><span class="sxs-lookup"><span data-stu-id="19f68-182">**Destination**</span></span>
     - <span data-ttu-id="19f68-183">**Principåtgärd**</span><span class="sxs-lookup"><span data-stu-id="19f68-183">**Policy action**</span></span>
     - <span data-ttu-id="19f68-184">**Skickat av**</span><span class="sxs-lookup"><span data-stu-id="19f68-184">**Submitted by**</span></span>

     <span data-ttu-id="19f68-185">När du är klar klickar du på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="19f68-185">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="19f68-186">Om du vill filtrera posterna klickar du **på Filtrera**.</span><span class="sxs-lookup"><span data-stu-id="19f68-186">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="19f68-187">Följande filter är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="19f68-187">The available filters are:</span></span>
     - <span data-ttu-id="19f68-188">**Skickat:** **Startdatum** **och Slutdatum**.</span><span class="sxs-lookup"><span data-stu-id="19f68-188">**Date submitted**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="19f68-189">**Inskickingstyp:** **E-post, URL** eller **fil**. </span><span class="sxs-lookup"><span data-stu-id="19f68-189">**Submission type**: **Email**, **URL**, or **File**.</span></span>
     - <span data-ttu-id="19f68-190">**Överförings-ID:** Ett GUID-värde som tilldelas till varje sändning.</span><span class="sxs-lookup"><span data-stu-id="19f68-190">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
     - <span data-ttu-id="19f68-191">**Id för nätverksmeddelande**</span><span class="sxs-lookup"><span data-stu-id="19f68-191">**Network Message ID**</span></span>
     - <span data-ttu-id="19f68-192">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="19f68-192">**Sender**</span></span>

     <span data-ttu-id="19f68-193">När du är klar klickar du på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="19f68-193">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="19f68-194">![Nya filteralternativ för administratörsinskick](../../media/admin-submission-filters.png)</span><span class="sxs-lookup"><span data-stu-id="19f68-194">![New Filter options for admin submissions](../../media/admin-submission-filters.png)</span></span>

   - <span data-ttu-id="19f68-195">Om du vill gruppera posterna **klickar du** på Gruppera och väljer något av följande värden i listrutan:</span><span class="sxs-lookup"><span data-stu-id="19f68-195">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="19f68-196">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="19f68-196">**None**</span></span>
     - <span data-ttu-id="19f68-197">**Typ**</span><span class="sxs-lookup"><span data-stu-id="19f68-197">**Type**</span></span>
     - <span data-ttu-id="19f68-198">**Orsak**</span><span class="sxs-lookup"><span data-stu-id="19f68-198">**Reason**</span></span>
     - <span data-ttu-id="19f68-199">**Status**</span><span class="sxs-lookup"><span data-stu-id="19f68-199">**Status**</span></span>
     - <span data-ttu-id="19f68-200">**Rescan-resultat**</span><span class="sxs-lookup"><span data-stu-id="19f68-200">**Rescan result**</span></span>

   - <span data-ttu-id="19f68-201">Om du vill exportera posterna klickar du **på Exportera.**</span><span class="sxs-lookup"><span data-stu-id="19f68-201">To export the entries, click **Export**.</span></span> <span data-ttu-id="19f68-202">I dialogrutan som visas sparar du den .csv filen.</span><span class="sxs-lookup"><span data-stu-id="19f68-202">In the dialog that appears, save the .csv file.</span></span>

### <a name="admin-submission-rescan-details"></a><span data-ttu-id="19f68-203">Information om administratörsinskickning igen</span><span class="sxs-lookup"><span data-stu-id="19f68-203">Admin submission rescan details</span></span>

<span data-ttu-id="19f68-204">Meddelanden som skickas i administratörsinskick granskas och resultaten visas i den utfällda utfällningen med information om inskickade inskickade meddelanden:</span><span class="sxs-lookup"><span data-stu-id="19f68-204">Messages that are submitted in admin submissions are reviewed and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="19f68-205">Om avsändarens e-postautentisering misslyckades vid leveransen.</span><span class="sxs-lookup"><span data-stu-id="19f68-205">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="19f68-206">Information om politiska träffar som kan ha påverkat eller åsidosatt bedömningen av ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="19f68-206">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="19f68-207">Aktuella detonationsresultat för att se om webbadresserna eller filerna i meddelandet var skadliga eller inte.</span><span class="sxs-lookup"><span data-stu-id="19f68-207">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="19f68-208">Feedback från grader.</span><span class="sxs-lookup"><span data-stu-id="19f68-208">Feedback from graders.</span></span>

<span data-ttu-id="19f68-209">Om en åsidosättning hittades bör omskanningen slutföras på några minuter.</span><span class="sxs-lookup"><span data-stu-id="19f68-209">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="19f68-210">Om det inte uppstod något problem i e-postautentisering eller -leverans påverkades inte av en åsidosättning, kan feedback från grader ta upp till en dag.</span><span class="sxs-lookup"><span data-stu-id="19f68-210">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="19f68-211">Visa användarinskick till Microsoft</span><span class="sxs-lookup"><span data-stu-id="19f68-211">View user submissions to Microsoft</span></span>

<span data-ttu-id="19f68-212">Om du har distribuerat tillägget Rapportmeddelande, [](enable-the-report-phish-add-in.md) [](enable-the-report-message-add-in.md)tillägget Rapportfiske eller om användarna använder den [inbyggda](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)rapporteringen i Outlook på webben kan du se vad användarna rapporterar på meddelandefliken **Rapporterad** användare.</span><span class="sxs-lookup"><span data-stu-id="19f68-212">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User reported message** tab.</span></span>

1. <span data-ttu-id="19f68-213">I Microsoft 365 Defender går du till Skicka **e-& och** \> **samarbetsinskick.**</span><span class="sxs-lookup"><span data-stu-id="19f68-213">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="19f68-214">På sidan **Inskickade** meddelanden väljer du **fliken Användarrapporterade** meddelanden.</span><span class="sxs-lookup"><span data-stu-id="19f68-214">On the **Submissions** page, select the **User reported messages** tab.</span></span>

   - <span data-ttu-id="19f68-215">Du kan sortera posterna genom att klicka på en tillgänglig kolumnrubrik.</span><span class="sxs-lookup"><span data-stu-id="19f68-215">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="19f68-216">Klicka **på Anpassa** kolumner för att visa maximalt sju kolumner.</span><span class="sxs-lookup"><span data-stu-id="19f68-216">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="19f68-217">Standardvärdena är markerade med en asterisk (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="19f68-217">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

     - <span data-ttu-id="19f68-218">**E-postämne**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19f68-218">**Email subject**<sup>\*</sup></span></span>
     - <span data-ttu-id="19f68-219">**Rapporterad av**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19f68-219">**Reported by**<sup>\*</sup></span></span>
     - <span data-ttu-id="19f68-220">**Rapporterad**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19f68-220">**Date reported**<sup>\*</sup></span></span>
     - <span data-ttu-id="19f68-221">**Avsändare**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19f68-221">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="19f68-222">**Rapporterad orsak**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19f68-222">**Reported reason**<sup>\*</sup></span></span>
     - <span data-ttu-id="19f68-223">**Rescan-resultat**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="19f68-223">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="19f68-224">**Rapporterat ID för meddelande**</span><span class="sxs-lookup"><span data-stu-id="19f68-224">**Message reported ID**</span></span>
     - <span data-ttu-id="19f68-225">**Id för nätverksmeddelande**</span><span class="sxs-lookup"><span data-stu-id="19f68-225">**Network Message ID**</span></span>
     - <span data-ttu-id="19f68-226">**Sender IP**</span><span class="sxs-lookup"><span data-stu-id="19f68-226">**Sender IP**</span></span>
     - <span data-ttu-id="19f68-227">**Phish-simulering**</span><span class="sxs-lookup"><span data-stu-id="19f68-227">**Phish simulation**</span></span>

     <span data-ttu-id="19f68-228">När du är klar klickar du på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="19f68-228">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="19f68-229">Om du vill filtrera posterna klickar du **på Filtrera**.</span><span class="sxs-lookup"><span data-stu-id="19f68-229">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="19f68-230">Följande filter är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="19f68-230">The available filters are:</span></span>
     - <span data-ttu-id="19f68-231">**Rapporterat datum:** **Startdatum** **och slutdatum.**</span><span class="sxs-lookup"><span data-stu-id="19f68-231">**Date reported**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="19f68-232">**Rapporterad av**</span><span class="sxs-lookup"><span data-stu-id="19f68-232">**Reported by**</span></span>
     - <span data-ttu-id="19f68-233">**Ämne för e-post**</span><span class="sxs-lookup"><span data-stu-id="19f68-233">**Email subject**</span></span>
     - <span data-ttu-id="19f68-234">**Rapporterat ID för meddelande**</span><span class="sxs-lookup"><span data-stu-id="19f68-234">**Message reported ID**</span></span>
     - <span data-ttu-id="19f68-235">**Id för nätverksmeddelande**</span><span class="sxs-lookup"><span data-stu-id="19f68-235">**Network Message ID**</span></span>
     - <span data-ttu-id="19f68-236">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="19f68-236">**Sender**</span></span>
     - <span data-ttu-id="19f68-237">**Rapporterad** orsak : **Inte skräppost,** **Phish** eller **Skräppost**.</span><span class="sxs-lookup"><span data-stu-id="19f68-237">**Reported reason**: **Not junk**, **Phish**, or **Spam**.</span></span>
     - <span data-ttu-id="19f68-238">**Phish simulering**: **Ja** eller **Nej**</span><span class="sxs-lookup"><span data-stu-id="19f68-238">**Phish simulation**: **Yes** or **No**</span></span>

     <span data-ttu-id="19f68-239">När du är klar klickar du på **Använd**.</span><span class="sxs-lookup"><span data-stu-id="19f68-239">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="19f68-240">![Nya filteralternativ för användarinskick](../../media/admin-submission-reported-messages.png)</span><span class="sxs-lookup"><span data-stu-id="19f68-240">![New Filter options for user submissions](../../media/admin-submission-reported-messages.png)</span></span>

   - <span data-ttu-id="19f68-241">Om du vill gruppera posterna **klickar du** på Gruppera och väljer något av följande värden i listrutan:</span><span class="sxs-lookup"><span data-stu-id="19f68-241">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="19f68-242">**Ingen**</span><span class="sxs-lookup"><span data-stu-id="19f68-242">**None**</span></span>
     - <span data-ttu-id="19f68-243">**Orsak**</span><span class="sxs-lookup"><span data-stu-id="19f68-243">**Reason**</span></span>
     - <span data-ttu-id="19f68-244">**Avsändare**</span><span class="sxs-lookup"><span data-stu-id="19f68-244">**Sender**</span></span>
     - <span data-ttu-id="19f68-245">**Rapporterad av**</span><span class="sxs-lookup"><span data-stu-id="19f68-245">**Reported by**</span></span>
     - <span data-ttu-id="19f68-246">**Rescan-resultat**</span><span class="sxs-lookup"><span data-stu-id="19f68-246">**Rescan result**</span></span>
     - <span data-ttu-id="19f68-247">**Phish-simulering**</span><span class="sxs-lookup"><span data-stu-id="19f68-247">**Phish simulation**</span></span>

   - <span data-ttu-id="19f68-248">Om du vill exportera posterna klickar du **på Exportera.**</span><span class="sxs-lookup"><span data-stu-id="19f68-248">To export the entries, click **Export**.</span></span> <span data-ttu-id="19f68-249">I dialogrutan som visas sparar du den .csv filen.</span><span class="sxs-lookup"><span data-stu-id="19f68-249">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="19f68-250">Om organisationer är konfigurerade att skicka endast användarrapporterade meddelanden till den anpassade postlådan  skickas inte rapporterade meddelanden för ny sökning och resultaten i Användarrapporterade meddelanden är alltid tomma.</span><span class="sxs-lookup"><span data-stu-id="19f68-250">If organizations are configured to send user reported messages to the custom mailbox only, reported messages will not be sent for rescan and the results in **User reported messages** will always be empty.</span></span>

### <a name="undo-user-submissions"></a><span data-ttu-id="19f68-251">Ångra användarinskick</span><span class="sxs-lookup"><span data-stu-id="19f68-251">Undo user submissions</span></span>

<span data-ttu-id="19f68-252">När en användare skickar ett misstänkt e-postmeddelande till den anpassade postlådan kan användaren och administratören inte ångra inskickat material.</span><span class="sxs-lookup"><span data-stu-id="19f68-252">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="19f68-253">Om användaren vill återställa e-posten kan den återställas i mapparna Borttagna objekt eller Skräppost.</span><span class="sxs-lookup"><span data-stu-id="19f68-253">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="19f68-254">Skicka meddelanden till Microsoft från den anpassade postlådan</span><span class="sxs-lookup"><span data-stu-id="19f68-254">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="19f68-255">Om du har konfigurerat den anpassade postlådan för att snappa upp användarrapporterade meddelanden utan att skicka meddelanden till Microsoft kan du hitta och skicka specifika meddelanden till Microsoft för analys.</span><span class="sxs-lookup"><span data-stu-id="19f68-255">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="19f68-256">Då flyttas en användarinskickning till en administratörsinskickning.</span><span class="sxs-lookup"><span data-stu-id="19f68-256">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="19f68-257">På fliken **Användarrapporterade** meddelanden väljer du ett meddelande i listan, klickar på Skicka till **Microsoft** för analys och väljer sedan ett av följande värden i listrutan:</span><span class="sxs-lookup"><span data-stu-id="19f68-257">On the **User reported messages** tab, select a message in the list, click **Submit to Microsoft for analysis**, and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="19f68-258">**Rapportrensning**</span><span class="sxs-lookup"><span data-stu-id="19f68-258">**Report clean**</span></span>
- <span data-ttu-id="19f68-259">**Rapportera nätfiske**</span><span class="sxs-lookup"><span data-stu-id="19f68-259">**Report phishing**</span></span>
- <span data-ttu-id="19f68-260">**Rapportera skadlig programvara**</span><span class="sxs-lookup"><span data-stu-id="19f68-260">**Report malware**</span></span>
- <span data-ttu-id="19f68-261">**Rapportera skräppost**</span><span class="sxs-lookup"><span data-stu-id="19f68-261">**Report spam**</span></span>
- <span data-ttu-id="19f68-262">**Undersökning av utlösare**</span><span class="sxs-lookup"><span data-stu-id="19f68-262">**Trigger investigation**</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="19f68-263">![Nya alternativ på knappen Åtgärd](../../media/admin-submission-main-action-button.png)</span><span class="sxs-lookup"><span data-stu-id="19f68-263">![New Options on the Action button](../../media/admin-submission-main-action-button.png)</span></span>
