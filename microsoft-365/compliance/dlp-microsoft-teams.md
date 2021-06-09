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
description: Microsoft Teams chattar och kanaler har stöd för DLP-principer (Data Loss Prevention).
ms.openlocfilehash: fa7e0967e24d8fa5e64b84fbccf54ff8cf45d1d6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843548"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="a797a-103">Skydd mot dataförlust och Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a797a-103">Data loss prevention and Microsoft Teams</span></span>

<span data-ttu-id="a797a-104">Om din organisation har skydd mot dataförlust (DLP) kan du definiera principer som hindrar personer från att dela känslig information i en Microsoft Teams kanal eller chattsession.</span><span class="sxs-lookup"><span data-stu-id="a797a-104">If your organization has data loss prevention (DLP), you can define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="a797a-105">Här är några exempel på hur skyddet fungerar:</span><span class="sxs-lookup"><span data-stu-id="a797a-105">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="a797a-106">**Exempel 1: Skydda känslig information i meddelanden**.</span><span class="sxs-lookup"><span data-stu-id="a797a-106">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="a797a-107">Anta att någon försöker dela känslig information i en Teams eller kanal med gäster (externa användare).</span><span class="sxs-lookup"><span data-stu-id="a797a-107">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="a797a-108">Om en DLP-princip har definierats för att förhindra detta, tas meddelanden med känslig information som skickas till externa användare bort.</span><span class="sxs-lookup"><span data-stu-id="a797a-108">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="a797a-109">Det sker automatiskt, och inom några sekunder, beroende på hur DLP-principen har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="a797a-109">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a797a-110">DLP för Microsoft Teams blockerar känsligt innehåll när det delas Microsoft Teams användare som har:</span><span class="sxs-lookup"><span data-stu-id="a797a-110">DLP for Microsoft Teams blocks sensitive content when shared with Microsoft Teams users who have:</span></span><br/><span data-ttu-id="a797a-111">- [gäståtkomst](/MicrosoftTeams/guest-access) i team och kanaler; eller</span><span class="sxs-lookup"><span data-stu-id="a797a-111">- [guest access](/MicrosoftTeams/guest-access) in teams and channels; or</span></span><br/><span data-ttu-id="a797a-112">- [extern åtkomst](/MicrosoftTeams/manage-external-access) i möten och chattsessioner.</span><span class="sxs-lookup"><span data-stu-id="a797a-112">- [external access](/MicrosoftTeams/manage-external-access) in meetings and chat sessions.</span></span> <p><span data-ttu-id="a797a-113">DLP för externa chattsessioner fungerar bara om både avsändaren och mottagaren är i Teams och använder [Microsoft Teams intern federation.](/microsoftteams/manage-external-access)</span><span class="sxs-lookup"><span data-stu-id="a797a-113">DLP for external chat sessions will only work if both the sender and the receiver are in Teams Only mode and using [Microsoft Teams native federation](/microsoftteams/manage-external-access).</span></span> <span data-ttu-id="a797a-114">DLP för Teams inte blockera meddelanden i [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) med Skype för företag eller icke-ursprungliga federerade chattsessioner.</span><span class="sxs-lookup"><span data-stu-id="a797a-114">DLP for Teams does not block messages in [interop](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) with Skype for Business or non-native federated chat sessions.</span></span>

- <span data-ttu-id="a797a-115">**Exempel 2: Skydda känslig information i dokument**.</span><span class="sxs-lookup"><span data-stu-id="a797a-115">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="a797a-116">Anta att någon försöker dela ett dokument med gäster i en Microsoft Teams kanal eller chatt, och att dokumentet innehåller känslig information.</span><span class="sxs-lookup"><span data-stu-id="a797a-116">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="a797a-117">Om en DLP-princip har definierats för att förhindra det öppnas inte dokumentet för dessa användare.</span><span class="sxs-lookup"><span data-stu-id="a797a-117">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="a797a-118">Din DLP-princip måste SharePoint och OneDrive för att skyddet ska vara på plats.</span><span class="sxs-lookup"><span data-stu-id="a797a-118">Your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span> <span data-ttu-id="a797a-119">Det här är ett exempel på DLP för SharePoint som visas i Microsoft Teams och kräver därför att användarna är licensierade för Office 365 DLP (ingår i Office 365 E3), men inte att användarna måste vara licensierade för Office 365 Advanced Compliance.)</span><span class="sxs-lookup"><span data-stu-id="a797a-119">This is an example of DLP for SharePoint that shows up in Microsoft Teams, and therefore requires that users are licensed for Office 365 DLP (included in Office 365 E3), but does not require users to be licensed for Office 365 Advanced Compliance.)</span></span>

## <a name="dlp-licensing-for-microsoft-teams"></a><span data-ttu-id="a797a-120">DLP-licensiering för Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a797a-120">DLP Licensing for Microsoft Teams</span></span>

<span data-ttu-id="a797a-121">[Funktionerna för skydd mot](dlp-learn-about-dlp.md) dataförlust har utökats så att de omfattar Microsoft Teams och kanalmeddelanden, **inklusive meddelanden i privata kanaler** för:</span><span class="sxs-lookup"><span data-stu-id="a797a-121">[Data loss prevention](dlp-learn-about-dlp.md) capabilities were extended to include Microsoft Teams chat and channel messages, **including private channel messages** for:</span></span>

- <span data-ttu-id="a797a-122">Office 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="a797a-122">Office 365 E5/A5</span></span>
- <span data-ttu-id="a797a-123">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="a797a-123">Microsoft 365 E5/A5</span></span>
- <span data-ttu-id="a797a-124">Microsoft 365 Informationsskydd och styrning</span><span class="sxs-lookup"><span data-stu-id="a797a-124">Microsoft 365 Information Protection and Governance</span></span>
- <span data-ttu-id="a797a-125">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="a797a-125">Office 365 Advanced Compliance</span></span>

<span data-ttu-id="a797a-126">Office 365 och Microsoft 365 E3 DLP-skydd för SharePoint Online, OneDrive och Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a797a-126">Office 365 and Microsoft 365 E3 include DLP protection for SharePoint Online, OneDrive, and Exchange Online.</span></span> <span data-ttu-id="a797a-127">Det omfattar även filer som delas via Teams eftersom Teams använder SharePoint Online och OneDrive för att dela filer.</span><span class="sxs-lookup"><span data-stu-id="a797a-127">This also includes files that are shared through Teams because Teams uses SharePoint Online and OneDrive to share files.</span></span>

<span data-ttu-id="a797a-128">Stöd för DLP-skydd i Teams chatt kräver E5.</span><span class="sxs-lookup"><span data-stu-id="a797a-128">Support for DLP protection in Teams Chat requires E5.</span></span>

<span data-ttu-id="a797a-129">Mer information om licenskrav finns i [licensvägledning Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="a797a-129">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a797a-130">DLP gäller endast för de faktiska meddelandena i chatten eller kanaltråden.</span><span class="sxs-lookup"><span data-stu-id="a797a-130">DLP applies only to the actual messages in the chat or channel thread.</span></span> <span data-ttu-id="a797a-131">Aktivitetsmeddelanden – som innehåller en kort förhandsgranskning och visas utifrån en  användares meddelandeinställningar – tas inte med i Teams DLP.</span><span class="sxs-lookup"><span data-stu-id="a797a-131">Activity notifications -- which include a short message preview and appear based on a user's notification settings -- are **not** included in Teams DLP.</span></span> <span data-ttu-id="a797a-132">Känslig information som finns i den del av meddelandet som visas i förhandsgranskningen fortsätter att visas i meddelandet även efter att DLP-principen har tillämpats och tagit bort känslig information i själva meddelandet.</span><span class="sxs-lookup"><span data-stu-id="a797a-132">Any sensitive information present in the part of the message that appears in the preview will remain visible in the notification even after the DLP policy has been applied and removed sensitive information the message itself.</span></span>

## <a name="scope-of-dlp-protection"></a><span data-ttu-id="a797a-133">DLP-skyddets omfattning</span><span class="sxs-lookup"><span data-stu-id="a797a-133">Scope of DLP protection</span></span>

<span data-ttu-id="a797a-134">DLP-skydd tillämpas olika på Teams enheter.</span><span class="sxs-lookup"><span data-stu-id="a797a-134">DLP protection are applied differently to Teams entities.</span></span>

|<span data-ttu-id="a797a-135">Användarkonton/grupper/lista</span><span class="sxs-lookup"><span data-stu-id="a797a-135">User Accounts/Groups/List</span></span>  |<span data-ttu-id="a797a-136">Teams Entitet</span><span class="sxs-lookup"><span data-stu-id="a797a-136">Teams Entity</span></span> |<span data-ttu-id="a797a-137">DLP-skydd tillgängligt</span><span class="sxs-lookup"><span data-stu-id="a797a-137">DLP protection available</span></span>|
|---------|---------|---------|
|<span data-ttu-id="a797a-138">enskilda användarkonton</span><span class="sxs-lookup"><span data-stu-id="a797a-138">individual user accounts</span></span>     |<span data-ttu-id="a797a-139">1:1/n chattar</span><span class="sxs-lookup"><span data-stu-id="a797a-139">1:1/n chats</span></span>         |<span data-ttu-id="a797a-140">ja</span><span class="sxs-lookup"><span data-stu-id="a797a-140">yes</span></span>         |
|     |<span data-ttu-id="a797a-141">allmänna chattar</span><span class="sxs-lookup"><span data-stu-id="a797a-141">general chats</span></span>         |<span data-ttu-id="a797a-142">nej</span><span class="sxs-lookup"><span data-stu-id="a797a-142">no</span></span>         |
|     |<span data-ttu-id="a797a-143">privata kanaler</span><span class="sxs-lookup"><span data-stu-id="a797a-143">private channels</span></span>         |<span data-ttu-id="a797a-144">ja</span><span class="sxs-lookup"><span data-stu-id="a797a-144">yes</span></span>         |
|<span data-ttu-id="a797a-145">säkerhetsgrupper/distributionslistor</span><span class="sxs-lookup"><span data-stu-id="a797a-145">security groups/distribution lists</span></span>  | <span data-ttu-id="a797a-146">1:1/n chattar</span><span class="sxs-lookup"><span data-stu-id="a797a-146">1:1/n chats</span></span>         |<span data-ttu-id="a797a-147">ja</span><span class="sxs-lookup"><span data-stu-id="a797a-147">yes</span></span>         |
|     |<span data-ttu-id="a797a-148">allmänna chattar</span><span class="sxs-lookup"><span data-stu-id="a797a-148">general chats</span></span>         |<span data-ttu-id="a797a-149">nej</span><span class="sxs-lookup"><span data-stu-id="a797a-149">no</span></span>         |
|     |<span data-ttu-id="a797a-150">privata kanaler</span><span class="sxs-lookup"><span data-stu-id="a797a-150">private channels</span></span>         |<span data-ttu-id="a797a-151">ja</span><span class="sxs-lookup"><span data-stu-id="a797a-151">yes</span></span>        |
|<span data-ttu-id="a797a-152">Microsoft 365 grupp</span><span class="sxs-lookup"><span data-stu-id="a797a-152">Microsoft 365 group</span></span>    |<span data-ttu-id="a797a-153">1:1/n chattar</span><span class="sxs-lookup"><span data-stu-id="a797a-153">1:1/n chats</span></span>          |<span data-ttu-id="a797a-154">nej</span><span class="sxs-lookup"><span data-stu-id="a797a-154">no</span></span>         |
|     |<span data-ttu-id="a797a-155">allmänna chattar</span><span class="sxs-lookup"><span data-stu-id="a797a-155">general chats</span></span>          |<span data-ttu-id="a797a-156">ja</span><span class="sxs-lookup"><span data-stu-id="a797a-156">yes</span></span>        |
|     |<span data-ttu-id="a797a-157">privata kanaler</span><span class="sxs-lookup"><span data-stu-id="a797a-157">private channels</span></span>|<span data-ttu-id="a797a-158">nej</span><span class="sxs-lookup"><span data-stu-id="a797a-158">no</span></span>| 


## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="a797a-159">Principtips hjälper till att utbilda användare</span><span class="sxs-lookup"><span data-stu-id="a797a-159">Policy tips help educate users</span></span>

<span data-ttu-id="a797a-160">På liknande sätt som DLP fungerar i [Exchange, Outlook, Outlook](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)på webben [, SharePoint Online, OneDrive för företag-webbplatser](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)och Office-skrivbordsklienter visas principtips när en åtgärd utlöses med en DLP-princip. [](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)</span><span class="sxs-lookup"><span data-stu-id="a797a-160">Similar to how DLP works in [Exchange, Outlook, Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action triggers with a DLP policy.</span></span> <span data-ttu-id="a797a-161">Här är ett exempel på ett principtips:</span><span class="sxs-lookup"><span data-stu-id="a797a-161">Here's an example of a policy tip:</span></span>

![Meddelande om blockerat meddelande i Teams](../media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="a797a-163">Här försökte avsändaren dela ett personnummer i en Microsoft Teams kanal.</span><span class="sxs-lookup"><span data-stu-id="a797a-163">Here, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="a797a-164">Länken **Vad kan jag göra?** öppnar en dialogruta med alternativ för att avsändaren ska kunna lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="a797a-164">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="a797a-165">Observera att avsändaren kan välja att åsidosätta principen eller meddela en administratör att granska och lösa den.</span><span class="sxs-lookup"><span data-stu-id="a797a-165">Notice that, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![Alternativ för att lösa blockerade meddelanden](../media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="a797a-167">I din organisation kan du välja att tillåta användare att åsidosätta en DLP-princip.</span><span class="sxs-lookup"><span data-stu-id="a797a-167">In your organization, you can choose to allow users to override a DLP policy.</span></span> <span data-ttu-id="a797a-168">När du konfigurerar DLP-principerna kan du använda standardprinciptipsen eller [anpassa principtipsen](#to-customize-policy-tips) för organisationen.</span><span class="sxs-lookup"><span data-stu-id="a797a-168">When you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span>

<span data-ttu-id="a797a-169">Gå tillbaka till vårt exempel, där en avsändare delade ett personnummer i en Teams-kanal, så här såg mottagaren:</span><span class="sxs-lookup"><span data-stu-id="a797a-169">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a797a-170">![Meddelandet är blockerat](../media/dlp-teams-blockedmessage-notification-to-user.png)</span><span class="sxs-lookup"><span data-stu-id="a797a-170">![Message blocked](../media/dlp-teams-blockedmessage-notification-to-user.png)</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="a797a-171">Så här anpassar du principtips</span><span class="sxs-lookup"><span data-stu-id="a797a-171">To customize policy tips</span></span>

<span data-ttu-id="a797a-172">Du måste ha tilldelats en roll som har behörighet att redigera DLP-principer för att kunna utföra den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="a797a-172">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="a797a-173">Mer information finns i [Behörigheter.](data-loss-prevention-policies.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="a797a-173">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="a797a-174">Gå till efterlevnadscentret [https://compliance.microsoft.com](https://compliance.microsoft.com) () och logga in.</span><span class="sxs-lookup"><span data-stu-id="a797a-174">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="a797a-175">Välj **Policy för skydd mot**  >  **dataförlust**.</span><span class="sxs-lookup"><span data-stu-id="a797a-175">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="a797a-176">Välj en princip och välj **Redigera bredvid** **Principinställningar.**</span><span class="sxs-lookup"><span data-stu-id="a797a-176">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="a797a-177">Skapa antingen en ny regel eller redigera en befintlig regel för principen.</span><span class="sxs-lookup"><span data-stu-id="a797a-177">Either create a new rule, or edit an existing rule for the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a797a-178">![Redigera en regel för en princip](../media/dlp-teams-editrule.png)</span><span class="sxs-lookup"><span data-stu-id="a797a-178">![Editing a rule for a policy](../media/dlp-teams-editrule.png)</span></span>

5. <span data-ttu-id="a797a-179">På fliken **Användarmeddelanden** väljer du Anpassa **e-posttexten** och/eller **Anpassa textalternativen för principtips.**</span><span class="sxs-lookup"><span data-stu-id="a797a-179">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a797a-180">![Anpassa användarmeddelanden och principtips](../media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="a797a-180">![Customize user notifications and policy tips](../media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="a797a-181">Ange den text som du vill använda för e-postaviseringar och/eller principtips och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a797a-181">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span>

7. <span data-ttu-id="a797a-182">På fliken **Principinställningar** väljer du **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a797a-182">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="a797a-183">Det kan ta ungefär en timme innan ändringarna fungerar via datacentret och synkroniseras med användarkonton.</span><span class="sxs-lookup"><span data-stu-id="a797a-183">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="a797a-184">Lägga Microsoft Teams som plats i befintliga DLP-principer</span><span class="sxs-lookup"><span data-stu-id="a797a-184">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="a797a-185">Du måste ha tilldelats en roll som har behörighet att redigera DLP-principer för att kunna utföra den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="a797a-185">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="a797a-186">Mer information finns i [Behörigheter.](data-loss-prevention-policies.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="a797a-186">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="a797a-187">Gå till efterlevnadscentret [https://compliance.microsoft.com](https://compliance.microsoft.com) () och logga in.</span><span class="sxs-lookup"><span data-stu-id="a797a-187">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="a797a-188">Välj **Policy för skydd mot**  >  **dataförlust**.</span><span class="sxs-lookup"><span data-stu-id="a797a-188">Choose **Data loss prevention** > **Policy**.</span></span>

3. <span data-ttu-id="a797a-189">Välj en princip och titta på värdena under **Platser.**</span><span class="sxs-lookup"><span data-stu-id="a797a-189">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="a797a-190">Om du **ser Teams chatt- och kanalmeddelanden** är allt klart.</span><span class="sxs-lookup"><span data-stu-id="a797a-190">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="a797a-191">Om du inte har det klickar du på **Redigera.**</span><span class="sxs-lookup"><span data-stu-id="a797a-191">If you don't, click **Edit**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a797a-192">![Platser för befintlig princip](../media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="a797a-192">![Locations for existing policy](../media/dlp-teams-editexistingpolicy.png)</span></span>

4. <span data-ttu-id="a797a-193">I kolumnen **Status** aktiverar du principen för Teams **och kanalmeddelanden**.</span><span class="sxs-lookup"><span data-stu-id="a797a-193">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a797a-194">![DLP för Teams chattar och kanaler](../media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="a797a-194">![DLP for Teams chats and channels](../media/dlp-teams-addteamschatschannels.png)</span></span>

5. <span data-ttu-id="a797a-195">Behåll **standardinställningen för** alla konton på fliken Välj **platser** eller välj Låt mig välja specifika platser .</span><span class="sxs-lookup"><span data-stu-id="a797a-195">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="a797a-196">Du kan ange:</span><span class="sxs-lookup"><span data-stu-id="a797a-196">You can specify:</span></span>

    1. <span data-ttu-id="a797a-197">upp till 1 000 enskilda konton att inkludera eller exkludera</span><span class="sxs-lookup"><span data-stu-id="a797a-197">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="a797a-198">distributionslistor och säkerhetsgrupper som ska inkluderas eller exkluderas.</span><span class="sxs-lookup"><span data-stu-id="a797a-198">distribution lists and security groups to include or exclude.</span></span> 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. <span data-ttu-id="a797a-199">Välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a797a-199">Then choose **Next**.</span></span>

7. <span data-ttu-id="a797a-200">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a797a-200">Click **Save**.</span></span>

<span data-ttu-id="a797a-201">Det kan ta ungefär en timme innan ändringarna fungerar via datacentret och synkroniseras med användarkonton.</span><span class="sxs-lookup"><span data-stu-id="a797a-201">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="a797a-202">Definiera en ny DLP-princip för Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a797a-202">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="a797a-203">Du måste ha tilldelats en roll som har behörighet att redigera DLP-principer för att kunna utföra den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="a797a-203">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="a797a-204">Mer information finns i [Behörigheter.](data-loss-prevention-policies.md#permissions)</span><span class="sxs-lookup"><span data-stu-id="a797a-204">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="a797a-205">Gå till efterlevnadscentret [https://compliance.microsoft.com](https://compliance.microsoft.com) () och logga in.</span><span class="sxs-lookup"><span data-stu-id="a797a-205">Go to the Compliance Center ([https://compliance.microsoft.com](https://compliance.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="a797a-206">Välj **Policy för skydd mot**  >    >  **dataförlust + Skapa en princip.**</span><span class="sxs-lookup"><span data-stu-id="a797a-206">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span>

3. <span data-ttu-id="a797a-207">Välj en [mall](data-loss-prevention-policies.md#dlp-policy-templates)och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="a797a-207">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span>

    <span data-ttu-id="a797a-208">I vårt exempel har vi valt mallen U.S. Personally Identifiable Information Data.</span><span class="sxs-lookup"><span data-stu-id="a797a-208">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a797a-209">![Sekretessmall för DLP-princip](../media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="a797a-209">![Privacy template for DLP policy](../media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="a797a-210">På fliken **Namnge principen** anger du ett namn och en beskrivning för principen och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="a797a-210">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span>

5. <span data-ttu-id="a797a-211">Behåll **standardinställningen för** alla konton på fliken Välj **platser** eller välj Låt mig välja specifika platser .</span><span class="sxs-lookup"><span data-stu-id="a797a-211">On the **Choose locations** tab, keep the default setting of all accounts, or select **Let me choose specific locations**.</span></span> <span data-ttu-id="a797a-212">Du kan ange:</span><span class="sxs-lookup"><span data-stu-id="a797a-212">You can specify:</span></span>

    1. <span data-ttu-id="a797a-213">upp till 1 000 enskilda konton att inkludera eller exkludera</span><span class="sxs-lookup"><span data-stu-id="a797a-213">up to 1000 individual accounts to include or exclude</span></span>
    1. <span data-ttu-id="a797a-214">distributionslistor och säkerhetsgrupper som ska inkluderas eller exkluderas.</span><span class="sxs-lookup"><span data-stu-id="a797a-214">distribution lists and security groups to include or exclude.</span></span> <span data-ttu-id="a797a-215">**Det här är en offentlig förhandsversionsfunktion.**</span><span class="sxs-lookup"><span data-stu-id="a797a-215">**This is a public preview feature.**</span></span>
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![DLP-principplatser](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > <span data-ttu-id="a797a-217">Om du vill kontrollera att dokument som innehåller känslig information inte delas olämpligt i Teams kontrollerar du att **SharePoint-webbplatser** och **OneDrive-konton** är aktiverat tillsammans med Teams-chatt- och **kanalmeddelanden.**</span><span class="sxs-lookup"><span data-stu-id="a797a-217">If you want to make sure documents that contain sensitive information are not shared inappropriately in Teams, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>

6. <span data-ttu-id="a797a-218">På fliken **Principinställningar,** under **Anpassa** den typ av innehåll som du vill skydda, behåll de enkla standardinställningarna eller välj Använd avancerade inställningar och välj sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="a797a-218">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="a797a-219">Om du väljer avancerade inställningar kan du skapa eller redigera regler för principen.</span><span class="sxs-lookup"><span data-stu-id="a797a-219">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="a797a-220">Om du behöver hjälp med detta kan du [gå till Enkla inställningar jämfört med avancerade inställningar.](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)</span><span class="sxs-lookup"><span data-stu-id="a797a-220">To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).</span></span>

7.  <span data-ttu-id="a797a-221">Granska **inställningarna under** Vad vill du göra om vi hittar känslig **information?** på fliken Principinställningar.</span><span class="sxs-lookup"><span data-stu-id="a797a-221">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="a797a-222">Här kan du välja att behålla standardprinciptips [och e-postaviseringar](use-notifications-and-policy-tips.md)eller anpassa dem.</span><span class="sxs-lookup"><span data-stu-id="a797a-222">Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a797a-223">![DLP-principinställningar med tips och meddelanden](../media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="a797a-223">![DLP policy settings with tips and notifications](../media/dlp-teams-policysettings-tipsemails.png)</span></span>

    <span data-ttu-id="a797a-224">När du är klar med granskningen eller redigeringsinställningarna väljer du **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="a797a-224">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="a797a-225">På fliken **Principinställningar,** under Vill du aktivera principen eller testa saker **först?** väljer du om du vill aktivera [principen,](dlp-overview-plan-for-dlp.md#policy-deployment)testar den först eller behåller den inaktiverad för tillfället och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="a797a-225">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](dlp-overview-plan-for-dlp.md#policy-deployment), or keep it turned off for now, and then choose **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a797a-226">![Ange om principen ska vara på](../media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="a797a-226">![Specify whether to turn the policy on](../media/dlp-teams-policysettings-turnonnow.png)</span></span>

9. <span data-ttu-id="a797a-227">Granska **inställningarna för den nya** principen på fliken Granska dina inställningar.</span><span class="sxs-lookup"><span data-stu-id="a797a-227">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="a797a-228">Välj **Redigera för** att göra ändringar.</span><span class="sxs-lookup"><span data-stu-id="a797a-228">Choose **Edit** to make changes.</span></span> <span data-ttu-id="a797a-229">När du är klar väljer du **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="a797a-229">When you're finished, choose **Create**.</span></span>

<span data-ttu-id="a797a-230">Det kan ta ungefär en timme innan den nya principen fungerar via datacentret och synkroniseras med användarkonton.</span><span class="sxs-lookup"><span data-stu-id="a797a-230">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="prevent-external-access-to-sensitive-documents"></a><span data-ttu-id="a797a-231">Förhindra extern åtkomst till känsliga dokument</span><span class="sxs-lookup"><span data-stu-id="a797a-231">Prevent external access to sensitive documents</span></span>

<span data-ttu-id="a797a-232">För att säkerställa SharePoint dokument som innehåller känslig information inte kan nås av externa gäster, antingen från SharePoint eller Teams, markerar du följande:</span><span class="sxs-lookup"><span data-stu-id="a797a-232">To ensure that SharePoint documents that contain sensitive information cannot be accessed by external guests either from SharePoint or Teams by default, select the following:</span></span>

- <span data-ttu-id="a797a-233">Du kan säkerställa att dokument skyddas tills DLP genomsöker och markerar dem som säkra att dela genom att markera [nya filer som känsliga som standard.](/sharepoint/sensitive-by-default)</span><span class="sxs-lookup"><span data-stu-id="a797a-233">You can ensure that documents are protected until DLP scans and marks them as safe to share by [marking new files as sensitive by default](/sharepoint/sensitive-by-default).</span></span>

- <span data-ttu-id="a797a-234">Rekommenderad DLP-principstruktur</span><span class="sxs-lookup"><span data-stu-id="a797a-234">Recommended DLP policy structure</span></span>

    - <span data-ttu-id="a797a-235">**Villkor**</span><span class="sxs-lookup"><span data-stu-id="a797a-235">**Conditions**</span></span>
        - <span data-ttu-id="a797a-236">Innehållet innehåller någon av följande typer av känslig information: [Markera alla som gäller]</span><span class="sxs-lookup"><span data-stu-id="a797a-236">Content contains any of these sensitive information types: [Select all that apply]</span></span>
        
        - <span data-ttu-id="a797a-237">Innehåll delas från Microsoft 365 med personer utanför organisationen</span><span class="sxs-lookup"><span data-stu-id="a797a-237">Content is shared from Microsoft 365 with people outside my organization</span></span>
        
          > [!div class="mx-imgBorder"]
          > <span data-ttu-id="a797a-238">![DLP-villkor för identifiering av extern delning av känsligt innehåll](../media/dlp-teams-external-sharing/external-condition.png)</span><span class="sxs-lookup"><span data-stu-id="a797a-238">![DLP conditions to detect external sharing of sensitive content](../media/dlp-teams-external-sharing/external-condition.png)</span></span>

    - <span data-ttu-id="a797a-239">**Åtgärder**</span><span class="sxs-lookup"><span data-stu-id="a797a-239">**Actions**</span></span>
        - <span data-ttu-id="a797a-240">Begränsa åtkomst till innehållet för externa användare</span><span class="sxs-lookup"><span data-stu-id="a797a-240">Restrict access to the content for external users</span></span>
        
        - <span data-ttu-id="a797a-241">Meddela användarna via e-post- och principtips</span><span class="sxs-lookup"><span data-stu-id="a797a-241">Notify users with email and policy tips</span></span>
        
        - <span data-ttu-id="a797a-242">Skicka incidentrapporter till administratören</span><span class="sxs-lookup"><span data-stu-id="a797a-242">Send incident reports to the Administrator</span></span>
        
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="a797a-243">![DLP-åtgärd för att blockera extern delning av känsligt innehåll](../media/dlp-teams-external-sharing/external-action.png)</span><span class="sxs-lookup"><span data-stu-id="a797a-243">![DLP action to block external sharing of sensitive content](../media/dlp-teams-external-sharing/external-action.png)</span></span>

<span data-ttu-id="a797a-244">DLP-princip används när du försöker dela ett dokument i ett SharePoint som innehåller känslig information med en extern gäst:</span><span class="sxs-lookup"><span data-stu-id="a797a-244">DLP policy in action when attempting to share a document in SharePoint that contains sensitive information with an external guest:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a797a-245">![Extern delning blockerad](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="a797a-245">![External sharing blocked](../media/dlp-teams-external-sharing/external-sharing-blocked.png)</span></span>


<span data-ttu-id="a797a-246">DLP-princip i praktiken när gäst försöker öppna ett dokument i Teams med extern blockering:</span><span class="sxs-lookup"><span data-stu-id="a797a-246">DLP policy in action when guest attempts to open a document in Teams with block external:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a797a-247">![Extern åtkomst blockerad](../media/dlp-teams-external-sharing/external-access-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="a797a-247">![External access blocked](../media/dlp-teams-external-sharing/external-access-blocked.png)</span></span>

## <a name="related-articles"></a><span data-ttu-id="a797a-248">Relaterade artiklar</span><span class="sxs-lookup"><span data-stu-id="a797a-248">Related articles</span></span>

- [<span data-ttu-id="a797a-249">Skapa, testa och justera en DLP-princip</span><span class="sxs-lookup"><span data-stu-id="a797a-249">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="a797a-250">Skicka e-postaviseringar och visa principtips för DLP-principer</span><span class="sxs-lookup"><span data-stu-id="a797a-250">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
