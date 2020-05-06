---
title: Konfigurera EOP till skräppost i hybridmiljöer
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
description: Administratörer kan lära sig hur du dirigerar skräppost till mappar för skräppost från användare i hybridmiljö för Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 14193fecf90a6f2ddde05fbfdaded0ff2bcb5875
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036578"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="d14df-103">Konfigurera fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljöer</span><span class="sxs-lookup"><span data-stu-id="d14df-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d14df-104">Det här avsnittet är endast för fristående EOP-kunder i hybridmiljöer.</span><span class="sxs-lookup"><span data-stu-id="d14df-104">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="d14df-105">Det här avsnittet gäller inte Microsoft 365-kunder med Exchange Online-postlådor.</span><span class="sxs-lookup"><span data-stu-id="d14df-105">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="d14df-106">Om du är en fristående Exchange Online Protection (EOP) kund i en hybridmiljö, måste du konfigurera din lokala Exchange-organisation för att känna igen och översätta spam filtrering domar av EOP, så att skräppost regeln i den lokala postlådan kan flytta meddelanden till skräppostmappen.</span><span class="sxs-lookup"><span data-stu-id="d14df-106">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="d14df-107">Specifikt måste du skapa regler för e-postflöde (kallas även transportregler) i din lokala Exchange-organisation med villkor som hittar meddelanden med någon av följande EOP-rubriker och värden mot skräppost och åtgärder som anger att skräppostförtroendenivån (SCL) för dessa meddelanden ska vara 6:</span><span class="sxs-lookup"><span data-stu-id="d14df-107">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="d14df-108">`X-Forefront-Antispam-Report: SFV:SPM`(meddelande markerat som skräppost genom skräppostfiltrering)</span><span class="sxs-lookup"><span data-stu-id="d14df-108">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="d14df-109">`X-Forefront-Antispam-Report: SFV:SKS`(meddelande markerat som skräppost via regler för e-postflöde i EOP före skräppostfiltrering)</span><span class="sxs-lookup"><span data-stu-id="d14df-109">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="d14df-110">`X-Forefront-Antispam-Report: SFV:SKB`(meddelande markerat som skräppost genom skräppostfiltrering på grund av att avsändarens e-postadress eller e-postdomän finns i listan över blockerade avsändare eller den blockerade domänlistan i EOP)</span><span class="sxs-lookup"><span data-stu-id="d14df-110">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="d14df-111">Mer information om dessa rubrikvärden finns i [Rubriker för skräppostmeddelanden](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="d14df-111">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="d14df-112">I det här avsnittet beskrivs hur du skapar dessa regler för e-postflöde (EAC) och Exchange Management Shell (Exchange PowerShell) i den lokala Exchange-organisationen.</span><span class="sxs-lookup"><span data-stu-id="d14df-112">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="d14df-113">I stället för att leverera meddelandena till den lokala användarens skräppostmapp kan du konfigurera anti-spam-principer i EOP för att sätta skräppostmeddelanden i karantän i EOP.</span><span class="sxs-lookup"><span data-stu-id="d14df-113">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="d14df-114">Mer information finns i [Konfigurera principer för skräppostskydd i Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d14df-114">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d14df-115">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="d14df-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d14df-116">Du måste tilldelas behörigheter i den lokala Exchange-miljön innan du kan göra dessa procedurer.</span><span class="sxs-lookup"><span data-stu-id="d14df-116">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="d14df-117">Du måste ha tilldelats rollen **Transportregler,** som tilldelas rollerna **Organisationshantering,** **Efterlevnadshantering**och **Arkivhandling** som standard.</span><span class="sxs-lookup"><span data-stu-id="d14df-117">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="d14df-118">Mer information finns i [Lägga till medlemmar i en rollgrupp](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).</span><span class="sxs-lookup"><span data-stu-id="d14df-118">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="d14df-119">Om och när ett meddelande levereras till mappen Skräppost i en lokal Exchange-organisation styrs av en kombination av följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="d14df-119">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="d14df-120">Parametervärdet _SCLJunkThreshold_ på [cmdlet Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) i Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d14df-120">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="d14df-121">Standardvärdet är 4, vilket innebär att en SCL på 5 eller högre bör leverera meddelandet till användarens skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="d14df-121">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="d14df-122">Parametervärdet _SCLJunkThreshold_ på cmdlet [set-postlådan](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) i Exchange Management Shell.</span><span class="sxs-lookup"><span data-stu-id="d14df-122">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="d14df-123">Standardvärdet är tomt ($null), vilket innebär att organisationsinställningen används.</span><span class="sxs-lookup"><span data-stu-id="d14df-123">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="d14df-124">Mer information finns i [SCL-tröskelvärden (Exchange spam Confidence Level).](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl)</span><span class="sxs-lookup"><span data-stu-id="d14df-124">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="d14df-125">Om skräppostregeln är aktiverad på postlådan (parametervärdet _Aktiverad_ $true på cmdleten [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) i Exchange Management Shell).</span><span class="sxs-lookup"><span data-stu-id="d14df-125">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="d14df-126">Det är skräppostregeln som faktiskt flyttar meddelandet till mappen Skräppost efter leverans.</span><span class="sxs-lookup"><span data-stu-id="d14df-126">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="d14df-127">Som standard är skräppostregeln aktiverad på postlådor.</span><span class="sxs-lookup"><span data-stu-id="d14df-127">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="d14df-128">Mer information finns i [Konfigurera inställningar för antispam för Exchange på postlådor](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span><span class="sxs-lookup"><span data-stu-id="d14df-128">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>
  
- <span data-ttu-id="d14df-129">Om du vill öppna EAC på en Exchange Server finns [i Administrationscenter för Exchange i Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="d14df-129">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="d14df-130">Om du vill öppna [https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell)Exchange Management Shell finns i .</span><span class="sxs-lookup"><span data-stu-id="d14df-130">To open the Exchange Management Shell, see [https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="d14df-131">Mer information om regler för e-postflöde i lokalt Exchange finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="d14df-131">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="d14df-132">Regler för e-postflöde i Exchange Server</span><span class="sxs-lookup"><span data-stu-id="d14df-132">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="d14df-133">Villkor och undantag för e-postflödesregel (predikat) i Exchange Server</span><span class="sxs-lookup"><span data-stu-id="d14df-133">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="d14df-134">Regelåtgärder för e-postflöde i Exchange Server</span><span class="sxs-lookup"><span data-stu-id="d14df-134">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="d14df-135">Använd EAC för att skapa regler för e-postflöde som anger SCL för EOP-skräppostmeddelanden</span><span class="sxs-lookup"><span data-stu-id="d14df-135">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="d14df-136">Gå till **Regler för** **e-postflöde** \> i EAC .</span><span class="sxs-lookup"><span data-stu-id="d14df-136">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="d14df-137">Klicka på](../../media/ITPro-EAC-AddIcon.png) **Lägg till-ikonen** ![och välj **Skapa en ny regel** i listrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="d14df-137">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="d14df-138">Konfigurera följande inställningar på sidan **Ny regel** som öppnas:</span><span class="sxs-lookup"><span data-stu-id="d14df-138">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="d14df-139">**Namn**: Ange ett unikt, beskrivande namn för regeln.</span><span class="sxs-lookup"><span data-stu-id="d14df-139">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="d14df-140">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="d14df-140">For example:</span></span>

     - <span data-ttu-id="d14df-141">EOP SFV:SPM till SCL 6</span><span class="sxs-lookup"><span data-stu-id="d14df-141">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="d14df-142">EOP SFV:SKS till SCL 6</span><span class="sxs-lookup"><span data-stu-id="d14df-142">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="d14df-143">EOP SFV:SKB till SCL 6</span><span class="sxs-lookup"><span data-stu-id="d14df-143">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="d14df-144">Klicka på **Fler alternativ**.</span><span class="sxs-lookup"><span data-stu-id="d14df-144">Click **More Options**.</span></span>

   - <span data-ttu-id="d14df-145">**Använd den här regeln om**: Välj ett **meddelandehuvud** \> **innehåller något av dessa ord**.</span><span class="sxs-lookup"><span data-stu-id="d14df-145">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="d14df-146">I **textrubriken Retur finns Ange ord** mening som visas, gör följande steg:</span><span class="sxs-lookup"><span data-stu-id="d14df-146">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="d14df-147">Klicka på **Ange text**.</span><span class="sxs-lookup"><span data-stu-id="d14df-147">Click **Enter text**.</span></span> <span data-ttu-id="d14df-148">I dialogrutan **Ange rubriknamn** som visas anger du **X-Forefront-Antispam-Report** och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="d14df-148">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="d14df-149">Klicka på **Ange ord**.</span><span class="sxs-lookup"><span data-stu-id="d14df-149">Click  **Enter words**.</span></span> <span data-ttu-id="d14df-150">I dialogrutan **Ange ord eller fraser** som visas anger du ett av EOP:s värden för skräpposthuvudet **(SFV:SPM,** **SFV:SKS**eller **SFV:SKB**), klicka på **Ikonen Lägg till** ![](../../media/ITPro-EAC-AddIcon.png)lägg till och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="d14df-150">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="d14df-151">**Gör så här:** Välj **Ändra meddelandeegenskaper** \> **Ange scl (Spam Confidence Level)**.</span><span class="sxs-lookup"><span data-stu-id="d14df-151">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="d14df-152">I dialogrutan **Ange SCL** som visas väljer du **6** (standardvärdet är **5**).</span><span class="sxs-lookup"><span data-stu-id="d14df-152">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="d14df-153">När du är klar klickar du på **Spara**</span><span class="sxs-lookup"><span data-stu-id="d14df-153">When you're finished, click **Save**</span></span>

<span data-ttu-id="d14df-154">Upprepa dessa steg för de återstående EOP spam dom värden **(SFV: SPM,** **SFV:SKS**, eller **SFV:SKB**).</span><span class="sxs-lookup"><span data-stu-id="d14df-154">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="d14df-155">Använd Exchange Management Shell för att skapa regler för e-postflöde som anger SCL för EOP-skräppostmeddelanden</span><span class="sxs-lookup"><span data-stu-id="d14df-155">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="d14df-156">Använd följande syntax för att skapa de tre reglerna för e-postflöde:</span><span class="sxs-lookup"><span data-stu-id="d14df-156">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="d14df-157">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="d14df-157">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="d14df-158">Detaljerad information om syntax och parametrar finns i [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="d14df-158">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="d14df-159">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="d14df-159">How do you know this worked?</span></span>

<span data-ttu-id="d14df-160">Så här kontrollerar du att du har konfigurerat fristående EOP för att leverera skräppost till mappen Skräppost i hybridmiljö:</span><span class="sxs-lookup"><span data-stu-id="d14df-160">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="d14df-161">Gå till Regler **för** **e-postflöde** \> i EAC, välj](../../media/ITPro-EAC-EditIcon.png) regeln och klicka sedan på **Ikonen Redigera** ![redigering för att verifiera inställningarna.</span><span class="sxs-lookup"><span data-stu-id="d14df-161">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="d14df-162">I Exchange Management Shell \<ersätter du RuleName\> med namnet på e-postflödesregeln och rul följande kommando för att verifiera inställningarna:</span><span class="sxs-lookup"><span data-stu-id="d14df-162">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="d14df-163">I ett externt e-postsystem **som inte skannar utgående meddelanden efter skräppost**skickar du ett allmänt test för oönskat massmeddelande (GTUBE) till en berörd mottagare och bekräftar att det levereras till mappen Skräppost.</span><span class="sxs-lookup"><span data-stu-id="d14df-163">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="d14df-164">Ett GTUBE-meddelande liknar EICAR-textfilen (European Institute for Computer Antivirus Research) för att testa inställningar för skadlig kod.</span><span class="sxs-lookup"><span data-stu-id="d14df-164">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="d14df-165">Om du vill skicka ett GTUBE-meddelande tar du med följande text i brödtexten i ett e-postmeddelande på en enda rad, utan blanksteg eller radbrytningar:</span><span class="sxs-lookup"><span data-stu-id="d14df-165">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
