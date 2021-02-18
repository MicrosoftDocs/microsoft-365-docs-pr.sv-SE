---
title: Konfigurera EOP för skräppost i hybridmiljöer
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig att dirigera skräppost till användarens skräppostmappar i en Exchange Online Protection-hybridmiljö.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b8fbc1b065e348f759806d80fd85421eb9d66098
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288879"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="6090d-103">Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer</span><span class="sxs-lookup"><span data-stu-id="6090d-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6090d-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="6090d-104">**Applies to**</span></span>
-  [<span data-ttu-id="6090d-105">Exchange Online Protection fristående</span><span class="sxs-lookup"><span data-stu-id="6090d-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

> [!IMPORTANT]
> <span data-ttu-id="6090d-106">Det här avsnittet gäller endast fristående EOP-kunder i hybridmiljöer.</span><span class="sxs-lookup"><span data-stu-id="6090d-106">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="6090d-107">Det här avsnittet gäller inte för Microsoft 365-kunder med Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="6090d-107">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="6090d-108">Om du är en fristående Exchange Online Protection-kund (EOP) i en hybridmiljö måste du konfigurera den lokala Exchange-organisationen så att den identifierar och översätter skräppostfiltreringsregel för EOP, så att skräppostregeln i den lokala postlådan kan flytta meddelanden till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="6090d-108">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="6090d-109">Specifikt måste du skapa e-postflödesregler (kallas även transportregler) i din lokala Exchange-organisation med villkor som hittar meddelanden med något av följande EOP-värden för skydd mot skräppost, och åtgärder som anger SCL (Spam Confidence Level) för dessa meddelanden till 6:</span><span class="sxs-lookup"><span data-stu-id="6090d-109">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="6090d-110">`X-Forefront-Antispam-Report: SFV:SPM` (meddelande som markerats som skräppost med skräppostfiltrering)</span><span class="sxs-lookup"><span data-stu-id="6090d-110">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="6090d-111">`X-Forefront-Antispam-Report: SFV:SKS` (Meddelande som har markerats som skräppost av e-postflödesregler i EOP före skräppostfiltrering)</span><span class="sxs-lookup"><span data-stu-id="6090d-111">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="6090d-112">`X-Forefront-Antispam-Report: SFV:SKB` (Meddelande som har markerats som skräppost med hjälp av skräppostfiltrering på grund av att avsändarens e-postadress eller e-postdomän finns med i listan över spärrade avsändare eller listan över blockerade domäner i EOP)</span><span class="sxs-lookup"><span data-stu-id="6090d-112">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="6090d-113">Mer information om dessa rubrikvärden finns i [Rubriken mot skräppost.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="6090d-113">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="6090d-114">I det här avsnittet beskrivs hur du skapar de här e-postflödesreglerna i administrationscentret för Exchange (EAC) och i Exchange Management Shell (Exchange PowerShell) i den lokala Exchange-organisationen.</span><span class="sxs-lookup"><span data-stu-id="6090d-114">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="6090d-115">I stället för att leverera meddelanden till den lokala användarens skräppostmapp kan du konfigurera principer för skydd mot skräppost i EOP för att sätta skräppostmeddelanden i karantän i EOP.</span><span class="sxs-lookup"><span data-stu-id="6090d-115">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="6090d-116">Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6090d-116">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6090d-117">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="6090d-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6090d-118">Du måste ha tilldelats behörigheter i den lokala Exchange-miljön innan du kan utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="6090d-118">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="6090d-119">Specifikt måste du tilldelas rollen **Transportregler,** som tilldelas rollerna **Organisationshantering,** **Efterlevnadshantering** och **Hantering** av arkivhandlingar som standard.</span><span class="sxs-lookup"><span data-stu-id="6090d-119">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="6090d-120">Mer information finns i Lägga [till medlemmar i en rollgrupp.](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group)</span><span class="sxs-lookup"><span data-stu-id="6090d-120">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="6090d-121">Om och när ett meddelande levereras till mappen Skräppost i en lokal Exchange-organisation styrs av en kombination av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="6090d-121">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="6090d-122">Parametervärdet _SCLJunkThreshold_ i [cmdleten Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) i Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6090d-122">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="6090d-123">Standardvärdet är 4, vilket innebär att en SCL med 5 eller högre ska leverera meddelandet till användarens skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="6090d-123">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="6090d-124">Parametervärdet _SCLJunkThreshold_ för cmdleten [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) i Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6090d-124">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="6090d-125">Standardvärdet är tomt ($null), vilket betyder att organisationsinställningen används.</span><span class="sxs-lookup"><span data-stu-id="6090d-125">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="6090d-126">Mer information finns i [SCL-tröskelvärden (Exchange Spam Confidence Level).](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)</span><span class="sxs-lookup"><span data-stu-id="6090d-126">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="6090d-127">Om skräppostregeln är aktiverad för postlådan (det aktiverade _parametervärdet_ $true på cmdleten [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) i Exchange Management Shell).</span><span class="sxs-lookup"><span data-stu-id="6090d-127">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="6090d-128">Det är skräppostregeln som faktiskt flyttar meddelandet till mappen Skräppost efter leverans.</span><span class="sxs-lookup"><span data-stu-id="6090d-128">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="6090d-129">Som standard är skräppostregeln aktiverad för postlådor.</span><span class="sxs-lookup"><span data-stu-id="6090d-129">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="6090d-130">Mer information finns i Konfigurera [inställningar för nätverksskydd för Exchange för postlådor.](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings)</span><span class="sxs-lookup"><span data-stu-id="6090d-130">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>

- <span data-ttu-id="6090d-131">Information om hur du öppnar EAC på Exchange Server finns i [administrationscentret för Exchange i Exchange Server.](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="6090d-131">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="6090d-132">Information om hur du öppnar Exchange Management Shell [finns i Öppna Exchange Management Shell.](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell)</span><span class="sxs-lookup"><span data-stu-id="6090d-132">To open the Exchange Management Shell, see [Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="6090d-133">Mer information om e-postflödesregler i lokal Exchange finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="6090d-133">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="6090d-134">E-postflödesregler i Exchange Server</span><span class="sxs-lookup"><span data-stu-id="6090d-134">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="6090d-135">Villkor för e-postflödesregel och undantag (predikat) i Exchange Server</span><span class="sxs-lookup"><span data-stu-id="6090d-135">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="6090d-136">Åtgärder för e-postflödesregel i Exchange Server</span><span class="sxs-lookup"><span data-stu-id="6090d-136">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="6090d-137">Använda EAC för att skapa e-postflödesregler som anger SCL för EOP-skräppostmeddelanden</span><span class="sxs-lookup"><span data-stu-id="6090d-137">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="6090d-138">Gå till E-postflödesregler **i** \> EAC.</span><span class="sxs-lookup"><span data-stu-id="6090d-138">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="6090d-139">Klicka **på** ![ ikonen Lägg till och välj Skapa en ](../../media/ITPro-EAC-AddIcon.png) **ny** regel i listrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="6090d-139">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="6090d-140">Konfigurera **följande inställningar** på sidan Ny regel som öppnas:</span><span class="sxs-lookup"><span data-stu-id="6090d-140">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="6090d-141">**Namn:** Ange ett unikt, beskrivande namn för regeln.</span><span class="sxs-lookup"><span data-stu-id="6090d-141">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="6090d-142">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="6090d-142">For example:</span></span>

     - <span data-ttu-id="6090d-143">EOP SFV:SPM till SCL 6</span><span class="sxs-lookup"><span data-stu-id="6090d-143">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="6090d-144">EOP SFV:SKS till SCL 6</span><span class="sxs-lookup"><span data-stu-id="6090d-144">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="6090d-145">EOP SFV:SKB till SCL 6</span><span class="sxs-lookup"><span data-stu-id="6090d-145">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="6090d-146">Klicka **på Fler alternativ.**</span><span class="sxs-lookup"><span data-stu-id="6090d-146">Click **More Options**.</span></span>

   - <span data-ttu-id="6090d-147">**Använd den här regeln om:** **Välj ett** \> **meddelandehuvud som innehåller något av dessa ord.**</span><span class="sxs-lookup"><span data-stu-id="6090d-147">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="6090d-148">Gör så **här i textrubriken Ange** ord som visas:</span><span class="sxs-lookup"><span data-stu-id="6090d-148">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="6090d-149">Klicka **på Retur-text.**</span><span class="sxs-lookup"><span data-stu-id="6090d-149">Click **Enter text**.</span></span> <span data-ttu-id="6090d-150">I dialogrutan **Ange rubriknamn** som visas anger du **X-Forefront-Antispam-Report** och klickar sedan på **OK.**</span><span class="sxs-lookup"><span data-stu-id="6090d-150">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="6090d-151">Klicka **på Retur-ord.**</span><span class="sxs-lookup"><span data-stu-id="6090d-151">Click  **Enter words**.</span></span> <span data-ttu-id="6090d-152">I  dialogrutan Ange ord eller fraser som visas anger du ett av EOP:s rubrikvärden för skräppost **(SFV:SPM,** **SFV:SKS** eller **SFV:SKB),** klickar på Lägg till ikon och klickar sedan på  ![ ](../../media/ITPro-EAC-AddIcon.png) **OK.**</span><span class="sxs-lookup"><span data-stu-id="6090d-152">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="6090d-153">**Gör följande:** Välj **Ändra meddelandeegenskaperna** \> **Ange skräppostförtroendenivån (SCL).**</span><span class="sxs-lookup"><span data-stu-id="6090d-153">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="6090d-154">I dialogrutan **Ange SCL** som visas väljer du **6** (standardvärdet är **5**).</span><span class="sxs-lookup"><span data-stu-id="6090d-154">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="6090d-155">Klicka på Spara när du är **klar**</span><span class="sxs-lookup"><span data-stu-id="6090d-155">When you're finished, click **Save**</span></span>

<span data-ttu-id="6090d-156">Upprepa de här stegen för de återstående värdena för skräppost i EOP **(SFV:SPM,** **SFV:SKS** eller **SFV:SKB).**</span><span class="sxs-lookup"><span data-stu-id="6090d-156">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="6090d-157">Använda Exchange Management Shell för att skapa e-postflödesregler som anger SCL för EOP-skräppostmeddelanden</span><span class="sxs-lookup"><span data-stu-id="6090d-157">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="6090d-158">Använd följande syntax för att skapa de tre e-postflödesreglerna:</span><span class="sxs-lookup"><span data-stu-id="6090d-158">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="6090d-159">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="6090d-159">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="6090d-160">Detaljerad information om syntax och parametrar finns i [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="6090d-160">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="6090d-161">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="6090d-161">How do you know this worked?</span></span>

<span data-ttu-id="6090d-162">Kontrollera att du har konfigurerat fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljön genom att göra något av följande:</span><span class="sxs-lookup"><span data-stu-id="6090d-162">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="6090d-163">I EAC går du till **E-postflödesregler,** markerar regeln och klickar sedan på \>   ![ ](../../media/ITPro-EAC-EditIcon.png) redigera-ikonen för att kontrollera inställningarna.</span><span class="sxs-lookup"><span data-stu-id="6090d-163">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="6090d-164">Ersätt med namnet på e-postflödesregeln i Exchange Management Shell och \<RuleName\> skapa följande kommando för att verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="6090d-164">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="6090d-165">I ett externt e-postsystem som inte söker igenom utgående meddelanden efter **skräppost** skickar du ett allmänt test för oombedd GTUBE-meddelande (Massutskick) till en mottagare och bekräftar att det har levererats till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="6090d-165">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="6090d-166">Ett GTUBE-meddelande liknar EICAR-textfilen (European Institute for Computer Antivirus Research) för att testa inställningar för skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="6090d-166">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="6090d-167">Om du vill skicka ett GTUBE-meddelande ska du ta med följande text i brödtexten i ett e-postmeddelande på en enda rad, utan blanksteg eller radbrytningar:</span><span class="sxs-lookup"><span data-stu-id="6090d-167">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
