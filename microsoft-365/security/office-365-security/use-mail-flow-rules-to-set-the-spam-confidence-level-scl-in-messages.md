---
title: Använda e-postflödesregler till SCL i meddelanden
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Lär dig hur du skapar e-postflödesregler (transportregler) för att identifiera meddelanden och ställa in SCL (Spam Confidence Level) för meddelanden i Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d7d1de194d8529fd3cf3e2d1da68c1f928ffcfa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921138"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="a3756-103">Använda e-postflödesregler för att ange konfidensnivån för skräppost (SCL) i meddelanden i EOP</span><span class="sxs-lookup"><span data-stu-id="a3756-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a3756-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="a3756-104">**Applies to**</span></span>
- [<span data-ttu-id="a3756-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="a3756-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a3756-106">Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2</span><span class="sxs-lookup"><span data-stu-id="a3756-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="a3756-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a3756-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="a3756-108">I Microsoft 365-organisationer som har postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor använder EOP principer för skräppostskydd (kallas även principer för skräppostfilter eller principer för innehållsfilter) för att söka efter skräppost i inkommande meddelanden.</span><span class="sxs-lookup"><span data-stu-id="a3756-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="a3756-109">Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a3756-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="a3756-110">Om du vill markera vissa meddelanden som skräppost innan de ens har genomsökts genom skräppostfiltrering, eller markera meddelanden så att de hoppar över skräppostfiltrering, kan du skapa e-postflödesregler (kallas även transportregler) för att identifiera meddelandena och ange SCL (Spam Confidence Level).</span><span class="sxs-lookup"><span data-stu-id="a3756-110">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="a3756-111">Mer information om SCL finns i [SCL (Spam Confidence Level) i EOP.](spam-confidence-levels.md)</span><span class="sxs-lookup"><span data-stu-id="a3756-111">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a3756-112">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="a3756-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a3756-113">Du måste ha tilldelats behörigheter i Exchange Online eller Exchange Online Protection innan du kan utföra procedurerna i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="a3756-113">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="a3756-114">Specifikt behöver du rollen **Transportregler,** som är tilldelad rollgrupperna **Organisationshantering,**  Efterlevnadshantering (globala administratörer) och **Hantering** av arkivhandlingar som standard.</span><span class="sxs-lookup"><span data-stu-id="a3756-114">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="a3756-115">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="a3756-115">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="a3756-116">Behörigheter i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a3756-116">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="a3756-117">Behörigheter i fristående EOP</span><span class="sxs-lookup"><span data-stu-id="a3756-117">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="a3756-118">Använd EAC för att ändra listan över medlemmar i rollgrupper</span><span class="sxs-lookup"><span data-stu-id="a3756-118">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="a3756-119">Information om hur du öppnar EAC i Exchange Online finns i [Administrationscenter för Exchange i Exchange Online.](/Exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="a3756-119">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="a3756-120">Information om hur du öppnar EAC i fristående EOP finns i [Administrationscenter för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)</span><span class="sxs-lookup"><span data-stu-id="a3756-120">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="a3756-121">Information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i artikeln om att [ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a3756-121">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a3756-122">Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="a3756-122">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a3756-123">Mer information om e-postflödesregler i Exchange Online och Exchange Online Protection finns i [E-postflödesregler (transportregler) i Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="a3756-123">For more information about mail flow rules in Exchange Online and Exchange Online Protection, see [Mail flow rules (transport rules) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="a3756-124">Använda EAC för att skapa en e-postflödesregel som anger SCL för ett meddelande</span><span class="sxs-lookup"><span data-stu-id="a3756-124">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="a3756-125">Gå till E-postflödesregler **i** \> EAC.</span><span class="sxs-lookup"><span data-stu-id="a3756-125">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="a3756-126">Klicka **på ikonen** Lägg till lägg till och välj sedan Skapa en ny ![ ](../../media/ITPro-EAC-AddIcon.png) **regel.**</span><span class="sxs-lookup"><span data-stu-id="a3756-126">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="a3756-127">På sidan **Ny regel** som öppnas konfigurerar du följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="a3756-127">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="a3756-128">**Namn**: Ange ett unikt, beskrivande namn för regeln.</span><span class="sxs-lookup"><span data-stu-id="a3756-128">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="a3756-129">Klicka **på Fler alternativ.**</span><span class="sxs-lookup"><span data-stu-id="a3756-129">Click **More Options**.</span></span>

   - <span data-ttu-id="a3756-130">**Använd den här regeln om:** Välj ett eller flera villkor för att identifiera meddelanden.</span><span class="sxs-lookup"><span data-stu-id="a3756-130">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="a3756-131">Mer information finns i Villkor [för e-postflödesregel och undantag (predikat) i Exchange Online.](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</span><span class="sxs-lookup"><span data-stu-id="a3756-131">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="a3756-132">**Gör följande:** Välj **Ändra meddelandeegenskaperna** \> **för att ange SCL (Spam Confidence Level).**</span><span class="sxs-lookup"><span data-stu-id="a3756-132">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="a3756-133">I dialogrutan **Ange SCL** konfigurerar du något av följande värden:</span><span class="sxs-lookup"><span data-stu-id="a3756-133">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="a3756-134">**Kringgå skräppostfiltrering:** Meddelandena hoppar över skräppostfiltrering.</span><span class="sxs-lookup"><span data-stu-id="a3756-134">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="a3756-135">Var mycket noga med att tillåta meddelanden att hoppa över skräppostfiltrering.</span><span class="sxs-lookup"><span data-stu-id="a3756-135">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="a3756-136">Attacker kan använda det här problemet för att skicka nätfiske och andra skadliga meddelanden till organisationen.</span><span class="sxs-lookup"><span data-stu-id="a3756-136">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="a3756-137">E-postflödesreglerna kräver mer än bara avsändarens e-postadress eller domän.</span><span class="sxs-lookup"><span data-stu-id="a3756-137">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="a3756-138">Mer information finns i Skapa [listor över betrodda avsändare i EOP.](create-safe-sender-lists-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="a3756-138">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="a3756-139">**0 till 4:** Meddelandet skickas via skräppostfiltrering för ytterligare bearbetning.</span><span class="sxs-lookup"><span data-stu-id="a3756-139">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="a3756-140">**5 eller 6:** Meddelandet markeras som **skräppost.**</span><span class="sxs-lookup"><span data-stu-id="a3756-140">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="a3756-141">Åtgärden som du har konfigurerat  för skräppostfiltreringsval i dina principer mot skräppost tillämpas på meddelandet (standardvärdet är Flytta meddelandet till mappen **Skräppost).**</span><span class="sxs-lookup"><span data-stu-id="a3756-141">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="a3756-142">**7–9:** Meddelandet markeras som Skräppost **med hög konfidens.**</span><span class="sxs-lookup"><span data-stu-id="a3756-142">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="a3756-143">Åtgärden som du har konfigurerat  för skräppostfiltrering av hög kvalitet i skräppostprinciperna tillämpas på meddelandet (standardvärdet är Flytta meddelandet till mappen **Skräppost).**</span><span class="sxs-lookup"><span data-stu-id="a3756-143">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="a3756-144">Ange ytterligare egenskaper som du vill använda för regeln.</span><span class="sxs-lookup"><span data-stu-id="a3756-144">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="a3756-145">Klicka på **Spara** när du är klar.</span><span class="sxs-lookup"><span data-stu-id="a3756-145">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a3756-146">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="a3756-146">How do you know this worked?</span></span>

<span data-ttu-id="a3756-147">Kontrollera att den här proceduren fungerar korrekt genom att skicka ett e-postmeddelande till någon i organisationen och kontrollera att åtgärden som utförts för meddelandet är som förväntat.</span><span class="sxs-lookup"><span data-stu-id="a3756-147">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="a3756-148">Om du till exempel anger **SCL (Spam Confidence Level)** som Förbikoppling av **skräppostfiltrering** ska meddelandet skickas till den angivna mottagarens inkorg.</span><span class="sxs-lookup"><span data-stu-id="a3756-148">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="a3756-149">Men om du ställer in konfidensnivån för skräppost **(SCL)** på **9** och åtgärden Hög förtroende för skräppostprinciperna för skräppost är att flytta meddelandet till mappen Skräppost ska meddelandet skickas till den angivna mottagarens skräppostmapp. </span><span class="sxs-lookup"><span data-stu-id="a3756-149">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>