---
title: Skydd mot dataförlust och Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Nu kan du använda DLP-principer Microsoft Teams chattar och kanaler. Läs den här artikeln om du vill veta mer om hur det fungerar.
ms.openlocfilehash: ac4c326fccd6faccca92844a55c419faa61a8d4c
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52163004"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="a55a0-104">Skydd mot dataförlust och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a55a0-104">Data loss prevention and Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="a55a0-105">Funktioner för dataförlustskydd har nyligen lagts till i Microsoft Teams chatt- och kanalmeddelanden för användare som är licensierade för Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance eller Office 365 Advanced Compliance.</span><span class="sxs-lookup"><span data-stu-id="a55a0-105">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance or Office 365 Advanced Compliance.</span></span> <span data-ttu-id="a55a0-106">Office 365 och Microsoft 365 E3 DLP-skydd för SharePoint Online, OneDrive och Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a55a0-106">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="a55a0-107">Det omfattar även filer som delas via Teams eftersom Teams använder SharePoint Online och OneDrive för att dela filer.</span><span class="sxs-lookup"><span data-stu-id="a55a0-107">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>
<span data-ttu-id="a55a0-108">Stöd för DLP-skydd i Teams chatt kräver E5.</span><span class="sxs-lookup"><span data-stu-id="a55a0-108">Support for DLP protection in Teams Chat requires E5.</span></span>
<span data-ttu-id="a55a0-109">Mer information om licenskrav finns i [licensvägledning Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="a55a0-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="a55a0-110">Översikt över DLP för Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a55a0-110">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="a55a0-111">Nyligen [utökades funktioner för skydd](dlp-learn-about-dlp.md) mot dataförlust med funktioner för Microsoft Teams och kanalmeddelanden, **inklusive meddelanden i privata kanaler.**</span><span class="sxs-lookup"><span data-stu-id="a55a0-111">Recently, [data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages**.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="a55a0-112">DLP gäller för närvarande endast för de faktiska meddelandena i chatten eller kanaltråden.</span><span class="sxs-lookup"><span data-stu-id="a55a0-112">DLP currently applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="a55a0-113">Aktivitetsmeddelanden – som innehåller en kort förhandsgranskning av meddelanden och visas  baserat på en användares meddelandeinställningar – ingår inte i Teams DLP för stunden.</span><span class="sxs-lookup"><span data-stu-id="a55a0-113">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP at this time.</span></span> <span data-ttu-id="a55a0-114">Känslig information som finns i den del av meddelandet som visas i förhandsgranskningen fortsätter att visas i meddelandet även efter att DLP-principen har tillämpats och tagit bort känslig information i själva meddelandet.</span><span class="sxs-lookup"><span data-stu-id="a55a0-114">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

<span data-ttu-id="a55a0-115">Om din organisation har DLP kan du nu definiera principer som hindrar personer från att dela känslig information i en Microsoft Teams-kanal eller chattsession.</span><span class="sxs-lookup"><span data-stu-id="a55a0-115">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="a55a0-116">Här är några exempel på hur skyddet fungerar:</span><span class="sxs-lookup"><span data-stu-id="a55a0-116">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="a55a0-117">**Exempel 1: Skydda känslig information i meddelanden**.</span><span class="sxs-lookup"><span data-stu-id="a55a0-117">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="a55a0-118">Anta att någon försöker dela känslig information i en Teams eller kanal med gäster (externa användare).</span><span class="sxs-lookup"><span data-stu-id="a55a0-118">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="a55a0-119">Om en DLP-princip har definierats för att förhindra detta, tas meddelanden med känslig information som skickas till externa användare bort.</span><span class="sxs-lookup"><span data-stu-id="a55a0-119">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="a55a0-120">Det sker automatiskt, och inom några sekunder, beroende på hur DLP-principen har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="a55a0-120">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a55a0-121">DLP för Microsoft Teams blockerar känsligt innehåll när det delas Microsoft Teams användare som har:</span><span class="sxs-lookup"><span data-stu-id="a55a0-121">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="a55a0-122">- [gäståtkomst](/MicrosoftTeams/guest-access) i team och kanaler; eller</span><span class="sxs-lookup"><span data-stu-id="a55a0-122">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="a55a0-123">- [extern åtkomst](/MicrosoftTeams/manage-external-access) i möten och chattsessioner.</span><span class="sxs-lookup"><span data-stu-id="a55a0-123">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="a55a0-124">DLP för externa chattsessioner fungerar bara om både avsändaren och mottagaren är i Teams och använder [Microsoft Teams intern federation.](/microsoftteams/manage-external-access)</span><span class="sxs-lookup"><span data-stu-id="a55a0-124">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="a55a0-125">DLP för Teams inte blockera meddelanden i [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) med Skype för företag eller icke-ursprungliga federerade chattsessioner.</span><span class="sxs-lookup"><span data-stu-id="a55a0-125">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="a55a0-126">**Exempel 2: Skydda känslig information i dokument**.</span><span class="sxs-lookup"><span data-stu-id="a55a0-126">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="a55a0-127">Anta att någon försöker dela ett dokument med gäster i en Microsoft Teams kanal eller chatt, och att dokumentet innehåller känslig information.</span><span class="sxs-lookup"><span data-stu-id="a55a0-127">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="a55a0-128">Om en DLP-princip har definierats för att förhindra det öppnas inte dokumentet för dessa användare.</span><span class="sxs-lookup"><span data-stu-id="a55a0-128">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="a55a0-129">Observera att i det här fallet måste DLP-principen innehålla SharePoint och OneDrive för att skyddet ska vara på plats.</span><span class="sxs-lookup"><span data-stu-id="a55a0-129">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="a55a0-130">(Det här är ett exempel på DLP för SharePoint som visas i Microsoft Teams och kräver därför att användarna är licensierade för Office 365 DLP (ingår i Office 365 E3), men inte kräver att användarna är licensierade för Office 365 Advanced Compliance.)</span><span class="sxs-lookup"><span data-stu-id="a55a0-130">(This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="a55a0-131">Principtips hjälper till att utbilda användare</span><span class="sxs-lookup"><span data-stu-id="a55a0-131">Policy tips help educate users</span></span>

<span data-ttu-id="a55a0-132">På liknande sätt som DLP fungerar i [Exchange, Outlook, Outlook](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)på webben [, SharePoint Online, OneDrive för företag-webbplatser](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)och Office-skrivbordsklienter visas principtips när en åtgärd står i konflikt med en DLP-princip. [](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)</span><span class="sxs-lookup"><span data-stu-id="a55a0-132">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="a55a0-133">Här är ett exempel på ett principtips:</span><span class="sxs-lookup"><span data-stu-id="a55a0-133">Here's an example of a policy tip:</span></span>

![Meddelande om blockerat meddelande i Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="a55a0-135">I det här fallet försökte avsändaren dela ett personnummer i en Microsoft Teams kanal.</span><span class="sxs-lookup"><span data-stu-id="a55a0-135">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="a55a0-136">Länken **Vad kan jag göra?** öppnar en dialogruta med alternativ för att avsändaren ska kunna lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="a55a0-136">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="a55a0-137">Observera att i det här fallet kan avsändaren välja att åsidosätta principen eller meddela en administratör att granska och lösa den.</span><span class="sxs-lookup"><span data-stu-id="a55a0-137">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![Alternativ för att lösa blockerade meddelanden](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="a55a0-139">I din organisation kan du välja att tillåta användare att åsidosätta en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="a55a0-139">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="a55a0-140">När du konfigurerar DLP-principerna kan du använda standardprinciptipsen eller [anpassa principtipsen](#to-customize-policy-tips) för organisationen.</span><span class="sxs-lookup"><span data-stu-id="a55a0-140">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="a55a0-141">Gå tillbaka till vårt exempel, där en avsändare delade ett personnummer i en Teams-kanal, så här såg mottagaren:</span><span class="sxs-lookup"><span data-stu-id="a55a0-141">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a55a0-142">![Meddelandet är blockerat](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="a55a0-142">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="a55a0-143">Så här anpassar du principtips</span><span class="sxs-lookup"><span data-stu-id="a55a0-143">To customize policy tips</span></span>

<span data-ttu-id="a55a0-144">Du måste ha tilldelats en roll som har behörighet att redigera DLP-principer för att kunna utföra den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="a55a0-144">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="a55a0-145">Mer information finns i [Behörigheter.](data-loss-prevention-policies.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="a55a0-145">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="a55a0-146">Gå till Säkerhets- & [https://protection.office.com](https://protection.office.com) () och logga in.</span><span class="sxs-lookup"><span data-stu-id="a55a0-146">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="a55a0-147">Välj **Policy för skydd mot**  >  **dataförlust**.</span><span class="sxs-lookup"><span data-stu-id="a55a0-147">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="a55a0-148">Välj en princip och välj **Redigera bredvid** **Principinställningar.**</span><span class="sxs-lookup"><span data-stu-id="a55a0-148">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="a55a0-149">Skapa antingen en ny regel eller redigera en befintlig regel för principen.</span><span class="sxs-lookup"><span data-stu-id="a55a0-149">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a55a0-150">![Redigera en regel för en princip](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="a55a0-150">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="a55a0-151">På fliken **Användarmeddelanden** väljer du Anpassa **e-posttexten** och/eller **Anpassa textalternativen för principtips.**</span><span class="sxs-lookup"><span data-stu-id="a55a0-151">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a55a0-152">![Anpassa användarmeddelanden och principtips](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="a55a0-152">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="a55a0-153">Ange den text som du vill använda för e-postaviseringar och/eller principtips och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a55a0-153">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="a55a0-154">På fliken **Principinställningar** väljer du **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a55a0-154">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="a55a0-155">Det kan ta ungefär en timme innan ändringarna fungerar via datacentret och synkroniseras med användarkonton.</span><span class="sxs-lookup"><span data-stu-id="a55a0-155">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="a55a0-156">Lägga Microsoft Teams som plats i befintliga DLP-principer</span><span class="sxs-lookup"><span data-stu-id="a55a0-156">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="a55a0-157">Du måste ha tilldelats en roll som har behörighet att redigera DLP-principer för att kunna utföra den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="a55a0-157">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="a55a0-158">Mer information finns i [Behörigheter.](data-loss-prevention-policies.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="a55a0-158">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="a55a0-159">Gå till Säkerhets- & [https://protection.office.com](https://protection.office.com) () och logga in.</span><span class="sxs-lookup"><span data-stu-id="a55a0-159">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="a55a0-160">Välj **Policy för skydd mot**  >  **dataförlust**.</span><span class="sxs-lookup"><span data-stu-id="a55a0-160">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="a55a0-161">Välj en princip och titta på värdena under **Platser.**</span><span class="sxs-lookup"><span data-stu-id="a55a0-161">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="a55a0-162">Om du **ser Teams chatt- och kanalmeddelanden** är allt klart.</span><span class="sxs-lookup"><span data-stu-id="a55a0-162">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="a55a0-163">Om du inte har det klickar du på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="a55a0-163">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a55a0-164">![Platser för befintlig princip](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="a55a0-164">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="a55a0-165">I kolumnen **Status** aktiverar du principen för Teams **och kanalmeddelanden**.</span><span class="sxs-lookup"><span data-stu-id="a55a0-165">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a55a0-166">![DLP för Teams chattar och kanaler](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="a55a0-166">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="a55a0-167">Behåll **standardinställningen för** alla konton på fliken Välj **platser** eller välj Låt mig välja specifika platser .</span><span class="sxs-lookup"><span data-stu-id="a55a0-167">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="a55a0-168">Du kan ange:</span><span class="sxs-lookup"><span data-stu-id="a55a0-168">You can specify:</span></span>

    1. <span data-ttu-id="a55a0-169">upp till 1 000 enskilda konton att inkludera eller exkludera</span><span class="sxs-lookup"><span data-stu-id="a55a0-169">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="a55a0-170">distributionslistor och säkerhetsgrupper som ska inkluderas eller exkluderas.</span><span class="sxs-lookup"><span data-stu-id="a55a0-170">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="a55a0-171">Välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a55a0-171">Then choose **Next**.</span></span>

7. <span data-ttu-id="a55a0-172">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a55a0-172">Click **Save**.</span></span>

<span data-ttu-id="a55a0-173">Det kan ta ungefär en timme innan ändringarna fungerar via datacentret och synkroniseras med användarkonton.</span><span class="sxs-lookup"><span data-stu-id="a55a0-173">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="a55a0-174">Definiera en ny DLP-princip för Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a55a0-174">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="a55a0-175">Du måste ha tilldelats en roll som har behörighet att redigera DLP-principer för att kunna utföra den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="a55a0-175">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="a55a0-176">Mer information finns i [Behörigheter.](data-loss-prevention-policies.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="a55a0-176">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="a55a0-177">Gå till Säkerhets- & [https://protection.office.com](https://protection.office.com) () och logga in.</span><span class="sxs-lookup"><span data-stu-id="a55a0-177">Go to the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="a55a0-178">Välj **Policy för skydd mot**  >    >  **dataförlust + Skapa en princip.**</span><span class="sxs-lookup"><span data-stu-id="a55a0-178">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="a55a0-179">Välj en [mall](data-loss-prevention-policies.md#dlp-policy-templates)och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a55a0-179">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="a55a0-180">I vårt exempel har vi valt mallen U.S. Personally Identifiable Information Data.</span><span class="sxs-lookup"><span data-stu-id="a55a0-180">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a55a0-181">![Sekretessmall för DLP-princip](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="a55a0-181">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="a55a0-182">På fliken **Namnge principen** anger du ett namn och en beskrivning för principen och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="a55a0-182">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="a55a0-183">Behåll **standardinställningen för** alla konton på fliken Välj **platser** eller välj Låt mig välja specifika platser .</span><span class="sxs-lookup"><span data-stu-id="a55a0-183">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="a55a0-184">Du kan ange:</span><span class="sxs-lookup"><span data-stu-id="a55a0-184">You can specify:</span></span>

    1. <span data-ttu-id="a55a0-185">upp till 1 000 enskilda konton att inkludera eller exkludera</span><span class="sxs-lookup"><span data-stu-id="a55a0-185">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="a55a0-186">distributionslistor och säkerhetsgrupper som ska inkluderas eller exkluderas.</span><span class="sxs-lookup"><span data-stu-id="a55a0-186">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="a55a0-187">**Det här är en offentlig förhandsversionsfunktion.**</span><span class="sxs-lookup"><span data-stu-id="a55a0-187">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![DLP-principplatser](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="a55a0-189">Om du vill kontrollera att dokument som innehåller känslig information inte delas olämpligt i Teams kontrollerar du att **SharePoint-webbplatser** och **OneDrive-konton** är aktiverat tillsammans med Teams-chatt- och **kanalmeddelanden.**</span><span class="sxs-lookup"><span data-stu-id="a55a0-189">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="a55a0-190">På fliken **Principinställningar,** under **Anpassa** den typ av innehåll som du vill skydda, behåll de enkla standardinställningarna eller välj Använd avancerade inställningar och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="a55a0-190">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="a55a0-191">Om du väljer avancerade inställningar kan du skapa eller redigera regler för principen.</span><span class="sxs-lookup"><span data-stu-id="a55a0-191">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="a55a0-192">(Om du behöver hjälp med detta kan du [gå till Enkla inställningar och avancerade inställningar](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span><span class="sxs-lookup"><span data-stu-id="a55a0-192">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="a55a0-193">Granska **inställningarna under** Vad vill du göra om vi hittar känslig **information?** på fliken Principinställningar.</span><span class="sxs-lookup"><span data-stu-id="a55a0-193">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="a55a0-194">(Här kan du välja att behålla standardprinciptips [och e-postaviseringar](use-notifications-and-policy-tips.md)eller anpassa dem.)</span><span class="sxs-lookup"><span data-stu-id="a55a0-194">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a55a0-195">![DLP-principinställningar med tips och meddelanden](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="a55a0-195">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="a55a0-196">När du är klar med granskningen eller redigeringsinställningarna väljer du **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="a55a0-196">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="a55a0-197">På fliken **Principinställningar,** under Vill du aktivera principen eller testa saker **först?** väljer du om du vill aktivera [principen,](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)testar den först eller behåller den inaktiverad för tillfället och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="a55a0-197">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a55a0-198">![Ange om principen ska vara på](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="a55a0-198">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="a55a0-199">Granska **inställningarna för den nya** principen på fliken Granska dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="a55a0-199">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="a55a0-200">Välj **Redigera för** att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="a55a0-200">Choose **Edit** to make changes.</span></span> <span data-ttu-id="a55a0-201">När du är klar väljer du **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="a55a0-201">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="a55a0-202">Det kan ta ungefär en timme innan den nya principen fungerar via datacentret och synkroniseras med användarkonton.</span><span class="sxs-lookup"><span data-stu-id="a55a0-202">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="a55a0-203">Förhindra extern åtkomst till känsliga dokument</span><span class="sxs-lookup"><span data-stu-id="a55a0-203">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="a55a0-204">För att säkerställa SharePoint dokument som innehåller känslig information inte kan nås av externa gäster, antingen från SharePoint eller Teams, markerar du följande:</span><span class="sxs-lookup"><span data-stu-id="a55a0-204">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="a55a0-205">Du kan säkerställa att dokument skyddas tills DLP genomsöker och markerar dem som säkra att dela genom att markera [nya filer som känsliga som standard.](/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="a55a0-205">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="a55a0-206">Rekommenderad DLP-principstruktur</span><span class="sxs-lookup"><span data-stu-id="a55a0-206">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="a55a0-207">**Villkor**</span><span class="sxs-lookup"><span data-stu-id="a55a0-207">**Conditions**</span></span>
        - <span data-ttu-id="a55a0-208">Innehållet innehåller någon av följande typer av känslig information: [Markera alla som gäller]</span><span class="sxs-lookup"><span data-stu-id="a55a0-208">Content contains any of these sensitive information types: [Select all that applies]</span></span>
        
        - <span data-ttu-id="a55a0-209">Innehåll delas från Microsoft 365 med personer utanför organisationen</span><span class="sxs-lookup"><span data-stu-id="a55a0-209">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="a55a0-210">![DLP-villkor för identifiering av extern delning av känsligt innehåll](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="a55a0-210">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="a55a0-211">**Åtgärder**</span><span class="sxs-lookup"><span data-stu-id="a55a0-211">**Actions**</span></span>
        - <span data-ttu-id="a55a0-212">Begränsa åtkomst till innehållet för externa användare</span><span class="sxs-lookup"><span data-stu-id="a55a0-212">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="a55a0-213">Meddela användarna via e-post- och principtips</span><span class="sxs-lookup"><span data-stu-id="a55a0-213">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="a55a0-214">Skicka incidentrapporter till administratören</span><span class="sxs-lookup"><span data-stu-id="a55a0-214">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="a55a0-215">![DLP-åtgärd för att blockera extern delning av känsligt innehåll](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="a55a0-215">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="a55a0-216">DLP-princip används när du försöker dela ett dokument i ett SharePoint som innehåller känslig information med en extern gäst:</span><span class="sxs-lookup"><span data-stu-id="a55a0-216">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a55a0-217">![Extern delning blockerad](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="a55a0-217">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="a55a0-218">DLP-princip i praktiken när gäst försöker öppna ett dokument i Teams med extern blockering:</span><span class="sxs-lookup"><span data-stu-id="a55a0-218">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a55a0-219">![Extern åtkomst blockerad](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="a55a0-219">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="a55a0-220">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="a55a0-220">Related articles</span></span>

[<span data-ttu-id="a55a0-221">Skapa, testa och justera en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="a55a0-221">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="a55a0-222">Skicka e-postaviseringar och visa principtips för DLP-principer</span><span class="sxs-lookup"><span data-stu-id="a55a0-222">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
