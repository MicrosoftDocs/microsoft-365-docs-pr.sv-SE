---
title: Använda e-postflödes regler i SCL i meddelanden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Lär dig hur du skapar e-postflödes regler (transport regler) för att identifiera meddelanden och ange SCL (skräp säkerhets nivå) för meddelanden i Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 447333eb968ba7d91a1673c57b11afdb16b90469
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659843"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="2330a-103">Använda regler för e-postflöde för att ange säkerhets nivån för skräp post (SCL) i meddelanden i EOP</span><span class="sxs-lookup"><span data-stu-id="2330a-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2330a-104">I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor används principer för skräp post (kallas även för principer för skräp post filter eller principer för innehålls filter) för att söka igenom inkommande meddelanden.</span><span class="sxs-lookup"><span data-stu-id="2330a-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="2330a-105">Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2330a-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="2330a-106">Om du vill markera specifika meddelanden som skräp post innan de är inaktiverade med skräp post filtrering, eller markera meddelanden så att de hoppar över skräp post filtrering, kan du skapa regler för e-postflöde (kallas även transport regler) för att identifiera meddelandena och ställa in säkerhets nivån för skräp post.</span><span class="sxs-lookup"><span data-stu-id="2330a-106">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="2330a-107">Mer information om SCL finns i [säkerhets nivå för skräp post (SCL) i EOP](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2330a-107">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2330a-108">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="2330a-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2330a-109">Du måste tilldelas behörigheter i Exchange Online eller Exchange Online Protection innan du kan göra det i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="2330a-109">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="2330a-110">För det specifika måste du ha rollen **Transport regel** , som är tilldelad till **organisations hantering**, **hantering av efterlevnad** (globala administratörer) och roll grupperna **Arkiv handlings hantering** som standard.</span><span class="sxs-lookup"><span data-stu-id="2330a-110">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="2330a-111">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="2330a-111">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="2330a-112">Behörigheter i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2330a-112">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="2330a-113">Behörigheter i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="2330a-113">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="2330a-114">Använda UK ändra listan över medlemmar i roll grupper</span><span class="sxs-lookup"><span data-stu-id="2330a-114">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="2330a-115">Om du vill öppna UK i Exchange Online läser du [administrations Center för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="2330a-115">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="2330a-116">Information om hur du öppnar UK i fristående EOP finns i [administrations Center för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="2330a-116">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="2330a-117">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2330a-117">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2330a-118">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="2330a-118">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2330a-119">Mer information om regler för e-postflöden i Exchange Online och Exchange Online Protection finns i [regler för e-postflöde (transport regler) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="2330a-119">For more information about mail flow rules in Exchange Online and Exchange Online Protection, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="2330a-120">Använd UK för att skapa en regel för e-postflöde som anger SCL för ett meddelande</span><span class="sxs-lookup"><span data-stu-id="2330a-120">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="2330a-121">Gå till regler för **e-postflöde** i UK \> .</span><span class="sxs-lookup"><span data-stu-id="2330a-121">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="2330a-122">Klicka på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) och välj sedan **skapa en ny regel**.</span><span class="sxs-lookup"><span data-stu-id="2330a-122">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="2330a-123">På sidan **ny regel** som öppnas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="2330a-123">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="2330a-124">**Namn**: Ange ett unikt, beskrivande namn för regeln.</span><span class="sxs-lookup"><span data-stu-id="2330a-124">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="2330a-125">Klicka på **fler alternativ**.</span><span class="sxs-lookup"><span data-stu-id="2330a-125">Click **More Options**.</span></span>

   - <span data-ttu-id="2330a-126">**Använd den här regeln om**: Välj ett eller flera villkor för att identifiera meddelanden.</span><span class="sxs-lookup"><span data-stu-id="2330a-126">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="2330a-127">Mer information finns i [villkor och undantag för e-postflödes regler (predikat) i Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="2330a-127">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="2330a-128">**Gör följande**: Välj **ändra meddelande egenskaper** \> **ange nivån för skräp post (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="2330a-128">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="2330a-129">I dialog rutan **Ange SCL** väljer du något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="2330a-129">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="2330a-130">**Kringgå skräp post filtrering**: meddelanden åsidosätter inte skräp post filtrering.</span><span class="sxs-lookup"><span data-stu-id="2330a-130">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="2330a-131">Var försiktig om att låta meddelanden hoppa över skräp post filtrering.</span><span class="sxs-lookup"><span data-stu-id="2330a-131">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="2330a-132">Angripare kan använda detta problem för att skicka nätfiske och andra skadliga meddelanden till din organisation.</span><span class="sxs-lookup"><span data-stu-id="2330a-132">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="2330a-133">Reglerna för e-postflöden kräver mer än avsändarens e-postadress eller domän.</span><span class="sxs-lookup"><span data-stu-id="2330a-133">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="2330a-134">Mer information finns i [skapa säkra avsändare i EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="2330a-134">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="2330a-135">**0 till 4**: meddelandet skickas via spam för ytterligare bearbetning.</span><span class="sxs-lookup"><span data-stu-id="2330a-135">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="2330a-136">**5 eller 6**: meddelandet är markerat som **skräp post**.</span><span class="sxs-lookup"><span data-stu-id="2330a-136">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="2330a-137">Den åtgärd som du har konfigurerat för **skräp post** filtrering verdicts i dina meddelanden (standardvärdet **flyttas till mappen skräp post**).</span><span class="sxs-lookup"><span data-stu-id="2330a-137">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="2330a-138">**7 till 9**: meddelandet har marker ATS som **skräp post**.</span><span class="sxs-lookup"><span data-stu-id="2330a-138">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="2330a-139">Den åtgärd som du har konfigurerat för filtrering av skräp post med **hög exakthet** verdicts i meddelandet (standardvärdet **flyttas till mappen skräp post**).</span><span class="sxs-lookup"><span data-stu-id="2330a-139">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="2330a-140">Ange ytterligare egenskaper för regeln.</span><span class="sxs-lookup"><span data-stu-id="2330a-140">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="2330a-141">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="2330a-141">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2330a-142">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="2330a-142">How do you know this worked?</span></span>

<span data-ttu-id="2330a-143">Verifiera att den här proceduren fungerar som den ska genom att skicka ett e-postmeddelande till någon inom organisationen och kontrol lera att åtgärden som utförs på meddelandet är som förväntat.</span><span class="sxs-lookup"><span data-stu-id="2330a-143">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="2330a-144">Om du till exempel **ställer in säkerhets nivån för skräp post (SCL)** för att **kringgå skräp post** ska meddelandet skickas till den angivna mottagarens inkorg.</span><span class="sxs-lookup"><span data-stu-id="2330a-144">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="2330a-145">Men om du **har angett säkerhets nivån för skräp post (SCL)** till **9** och åtgärden att ta bort **hög säkerhet** för dina tillämpliga skydd mot skräp post är att meddelandet ska flyttas till mappen skräp post.</span><span class="sxs-lookup"><span data-stu-id="2330a-145">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
