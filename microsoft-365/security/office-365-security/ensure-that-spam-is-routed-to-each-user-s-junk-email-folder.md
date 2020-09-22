---
title: Konfigurera EOP till skräp post i hybrid miljöer
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om hur du dirigerar skräp post till e-postmappar för användare i Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4c01ad0e8efa4d28e1b5d1e72b3daa87bb01b619
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196599"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="f7f83-103">Konfigurera fristående EOP för att skicka skräp post till skräppostmappen i hybrid miljöer</span><span class="sxs-lookup"><span data-stu-id="f7f83-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> <span data-ttu-id="f7f83-104">Det här avsnittet gäller endast för fristående EOP-kunder i hybrid miljöer.</span><span class="sxs-lookup"><span data-stu-id="f7f83-104">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="f7f83-105">Det här avsnittet gäller inte för Microsoft 365-kunder med Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="f7f83-105">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="f7f83-106">Om du är en fristående Exchange Online Protection-kund (EOP) i en hybrid miljö måste du konfigurera den lokala Exchange-organisationen för att känna igen och översätta skräp post filtrerings verdicts för EOP, så att skräp post regeln i den lokala post lådan kan flytta meddelanden till mappen skräp post.</span><span class="sxs-lookup"><span data-stu-id="f7f83-106">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="f7f83-107">Specifikt måste du skapa regler för e-postflöden (kallas även transport regler) i din lokala Exchange-organisation med villkor som returnerar meddelanden med något av följande EOP skydd mot skräp post och värden, och åtgärder som ställer in den SCL (spam) för dessa meddelanden till 6:</span><span class="sxs-lookup"><span data-stu-id="f7f83-107">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="f7f83-108">`X-Forefront-Antispam-Report: SFV:SPM` (meddelande som marker ATS som skräp post vid filtrering av skräp post)</span><span class="sxs-lookup"><span data-stu-id="f7f83-108">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="f7f83-109">`X-Forefront-Antispam-Report: SFV:SKS` (meddelande som marker ATS som skräp post av regler för e-postflöde i EOP före skräp post filtrering)</span><span class="sxs-lookup"><span data-stu-id="f7f83-109">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="f7f83-110">`X-Forefront-Antispam-Report: SFV:SKB` (meddelande som marker ATS som skräp post genom filtrering av skräp post på grund av avsändarens e-postadress eller e-postdomän i listan Blockerade avsändare eller listan blockerade domäner i EOP)</span><span class="sxs-lookup"><span data-stu-id="f7f83-110">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="f7f83-111">Mer information om dessa rubrik värden finns i [meddelande rubriker med skräp post](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="f7f83-111">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="f7f83-112">I det här avsnittet beskrivs hur du skapar de här e-postflödena för Exchange Admin Center (UK) och i Exchange Management Shell (Exchange PowerShell) i den lokala Exchange-organisationen.</span><span class="sxs-lookup"><span data-stu-id="f7f83-112">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="f7f83-113">I stället för att skicka meddelanden till den lokala användarens skräppost-mapp kan du konfigurera principer för skräp post i EOP till skräp post meddelanden i EOP.</span><span class="sxs-lookup"><span data-stu-id="f7f83-113">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="f7f83-114">Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f7f83-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f7f83-115">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="f7f83-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f7f83-116">Du måste ha behörighet i den lokala Exchange-miljön innan du kan utföra dessa procedurer.</span><span class="sxs-lookup"><span data-stu-id="f7f83-116">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="f7f83-117">Specifikt måste du ha tilldelats rollen **transport regler** , som tilldelats rollerna **organisations hantering**, **regelefterlevnad**och hantering av **Arkiv handlingar** .</span><span class="sxs-lookup"><span data-stu-id="f7f83-117">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="f7f83-118">Mer information finns i [lägga till medlemmar i en roll grupp](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).</span><span class="sxs-lookup"><span data-stu-id="f7f83-118">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="f7f83-119">Om och när ett meddelande skickas till mappen skräp post i en lokal Exchange-organisation styrs av en kombination av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f7f83-119">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="f7f83-120">Parametern _SCLJunkThreshold_ i cmdleten [set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) i Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f7f83-120">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="f7f83-121">Standardvärdet är 4, vilket innebär att en SCL på 5 eller högre ska skicka meddelandet till användarens mapp för skräp post.</span><span class="sxs-lookup"><span data-stu-id="f7f83-121">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="f7f83-122">Värdet på parametern _SCLJunkThreshold_ i cmdleten [set-post låda](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) i Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f7f83-122">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="f7f83-123">Standardvärdet är blank ($null), vilket innebär att organisations inställningen används.</span><span class="sxs-lookup"><span data-stu-id="f7f83-123">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="f7f83-124">Mer information finns i [tröskelvärden för skydd mot skräp post (SCL)](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span><span class="sxs-lookup"><span data-stu-id="f7f83-124">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="f7f83-125">Om regeln för skräp post är aktive rad på post lådan (det _aktiverade_ parametervärdet är $true i cmdleten [set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) i Exchange Management Shell).</span><span class="sxs-lookup"><span data-stu-id="f7f83-125">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="f7f83-126">Det är skräp post regeln som faktiskt flyttar meddelandet till mappen skräp post efter leverans.</span><span class="sxs-lookup"><span data-stu-id="f7f83-126">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="f7f83-127">Regeln för skräp post är aktive rad som standard för post lådor.</span><span class="sxs-lookup"><span data-stu-id="f7f83-127">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="f7f83-128">Mer information finns i [Konfigurera inställningar för Exchange-antispam i post lådor](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span><span class="sxs-lookup"><span data-stu-id="f7f83-128">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>

- <span data-ttu-id="f7f83-129">Information om hur du öppnar UK på en Exchange-Server finns i [administrations Center för Exchange i Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="f7f83-129">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="f7f83-130">Information om hur du öppnar Exchange Management Shell finns i [Öppna Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span><span class="sxs-lookup"><span data-stu-id="f7f83-130">To open the Exchange Management Shell, see [Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="f7f83-131">Mer information om regler för e-postflöden finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="f7f83-131">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="f7f83-132">Regler för e-postflöde i Exchange Server</span><span class="sxs-lookup"><span data-stu-id="f7f83-132">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="f7f83-133">Villkor och undantag (predikat) i Exchange Server för regel för e-postflöde</span><span class="sxs-lookup"><span data-stu-id="f7f83-133">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="f7f83-134">Åtgärder för e-postflödes regel i Exchange Server</span><span class="sxs-lookup"><span data-stu-id="f7f83-134">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="f7f83-135">Använd UK för att skapa regler för e-postflöden som anger SCL för EOP spam-meddelanden</span><span class="sxs-lookup"><span data-stu-id="f7f83-135">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="f7f83-136">Gå till regler för **e-postflöde** i UK \> **Rules**.</span><span class="sxs-lookup"><span data-stu-id="f7f83-136">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="f7f83-137">Klicka på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) och välj **skapa en ny regel** i list rutan som visas.</span><span class="sxs-lookup"><span data-stu-id="f7f83-137">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="f7f83-138">På sidan **ny regel** som öppnas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="f7f83-138">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="f7f83-139">**Namn**: Ange ett unikt, beskrivande namn för regeln.</span><span class="sxs-lookup"><span data-stu-id="f7f83-139">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="f7f83-140">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="f7f83-140">For example:</span></span>

     - <span data-ttu-id="f7f83-141">EOP SFV: SPM till SCL 6</span><span class="sxs-lookup"><span data-stu-id="f7f83-141">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="f7f83-142">EOP SFV: SKS till SCL 6</span><span class="sxs-lookup"><span data-stu-id="f7f83-142">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="f7f83-143">EOP SFV: SKB till SCL 6</span><span class="sxs-lookup"><span data-stu-id="f7f83-143">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="f7f83-144">Klicka på **fler alternativ**.</span><span class="sxs-lookup"><span data-stu-id="f7f83-144">Click **More Options**.</span></span>

   - <span data-ttu-id="f7f83-145">**Använd den här regeln om**: Välj **en meddelande rubrik** \> **innehåller något av dessa ord**.</span><span class="sxs-lookup"><span data-stu-id="f7f83-145">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="f7f83-146">I **text rubriken ange ord** mening som visas gör du följande:</span><span class="sxs-lookup"><span data-stu-id="f7f83-146">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="f7f83-147">Klicka på **Ange text**.</span><span class="sxs-lookup"><span data-stu-id="f7f83-147">Click **Enter text**.</span></span> <span data-ttu-id="f7f83-148">I dialog rutan **Ange rubrik namn** anger du **X-Forefront-antispam-Report** och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7f83-148">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="f7f83-149">Klicka på  **Ange ord**.</span><span class="sxs-lookup"><span data-stu-id="f7f83-149">Click  **Enter words**.</span></span> <span data-ttu-id="f7f83-150">I dialog rutan **Ange ord eller fraser** som visas anger du ett av värdena för EOP spam (**SFV: SPM**, **SFV: SKS**eller **SFV: SKB**), klickar på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) och sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7f83-150">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="f7f83-151">**Gör följande**: Välj **ändra meddelande egenskaper** \> **ange nivån för skräp post (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="f7f83-151">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="f7f83-152">I dialog rutan **Ange SCL** väljer du **6** (Standardvärdet är **5**).</span><span class="sxs-lookup"><span data-stu-id="f7f83-152">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="f7f83-153">När du är klar klickar du på **Spara**</span><span class="sxs-lookup"><span data-stu-id="f7f83-153">When you're finished, click **Save**</span></span>

<span data-ttu-id="f7f83-154">Upprepa de här stegen för återstående EOP spam Verdict värden (**SFV: SPM**, **SFV: SKS**eller **SFV: SKB**).</span><span class="sxs-lookup"><span data-stu-id="f7f83-154">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="f7f83-155">Använd Exchange Management Shell för att skapa regler för e-postflöden som anger SCL för EOP spam-meddelanden</span><span class="sxs-lookup"><span data-stu-id="f7f83-155">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="f7f83-156">Använd följande syntax för att skapa de tre reglerna för e-postflöden:</span><span class="sxs-lookup"><span data-stu-id="f7f83-156">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="f7f83-157">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="f7f83-157">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="f7f83-158">Detaljerad information om syntax och parametrar finns i [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="f7f83-158">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f7f83-159">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="f7f83-159">How do you know this worked?</span></span>

<span data-ttu-id="f7f83-160">Gör något av följande om du vill kontrol lera att fristående EOP har kon figurer ATS för att skicka skräp post till skräppost-mappen i hybrid miljö:</span><span class="sxs-lookup"><span data-stu-id="f7f83-160">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="f7f83-161">Gå till regler för **e-postflöde** i UK, \> **Rules**Välj regeln och klicka sedan på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) för att bekräfta inställningarna.</span><span class="sxs-lookup"><span data-stu-id="f7f83-161">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="f7f83-162">I Exchange Management Shell ersätter du \<RuleName\> med namnet på regeln för e-postflöde och RUL följande kommando för att verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="f7f83-162">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="f7f83-163">I ett externt e-postsystem **som inte skannar utgående meddelanden för skräp post**kan du skicka ett allmänt test till en mottagare och bekräfta att det levereras till mappen skräp post.</span><span class="sxs-lookup"><span data-stu-id="f7f83-163">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="f7f83-164">Ett GTUBE-meddelande liknar EICAR-textfilen (European Institute for Computer Antivirus Research) för att testa inställningar för skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="f7f83-164">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="f7f83-165">Skicka ett GTUBE meddelande genom att lägga till följande text i bröd texten i ett e-postmeddelande på en enda rad, utan blank steg eller rad brytningar:</span><span class="sxs-lookup"><span data-stu-id="f7f83-165">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
