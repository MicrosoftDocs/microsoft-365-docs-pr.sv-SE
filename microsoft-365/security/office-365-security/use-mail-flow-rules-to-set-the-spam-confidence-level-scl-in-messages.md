---
title: Använd regler för e-postflöde för att ställa in scl (Spam Confidence Level) i meddelanden
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig hur du ställer in SCL för meddelanden i Exchange Online Protection.
ms.openlocfilehash: 10440d5ac8cd57388f4550f21ca72ce7aa1a2745
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806467"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a><span data-ttu-id="49e63-103">Använd regler för e-postflöde för att ställa in scl (Spam Confidence Level) i meddelanden</span><span class="sxs-lookup"><span data-stu-id="49e63-103">Use mail flow rules to set the spam confidence level (SCL) in messages</span></span>

<span data-ttu-id="49e63-104">Du kan skapa en regel för e-postflöde (kallas även en transportregel) som anger åtkomstnivån för skräppost (SCL) för ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="49e63-104">You can create a mail flow rule (also known as a transport rule) that sets the spam confidence level (SCL) of an email message.</span></span> <span data-ttu-id="49e63-105">SCL är ett mått på hur sannolikt ett meddelande är att vara spam.</span><span class="sxs-lookup"><span data-stu-id="49e63-105">The SCL is a measure of how likely a message is to be spam.</span></span> <span data-ttu-id="49e63-106">Skräppost är oönskade (och vanligtvis oönskade) e-postmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="49e63-106">Spam is unsolicited (and typically unwanted) email messages.</span></span> <span data-ttu-id="49e63-107">Tjänsten vidtar olika åtgärder på ett meddelande beroende på dess SCL-klassificering.</span><span class="sxs-lookup"><span data-stu-id="49e63-107">The service takes different action on a message depending on its SCL rating.</span></span> <span data-ttu-id="49e63-108">Du kanske till exempel vill kringgå filtrering av skräppostinnehåll för meddelanden som skickas från personer i organisationen eftersom du litar på att ett meddelande som skickas internt från en kollega inte är skräppost.</span><span class="sxs-lookup"><span data-stu-id="49e63-108">For example, you might want to bypass spam content filtering for messages that are sent from people inside your organization because you trust that a message sent internally from a colleague isn't spam.</span></span> <span data-ttu-id="49e63-109">Genom att använda regler för e-postflöde för att ange SCL-värdet för ett meddelande får du ökad kontroll över hanteringen av skräppost.</span><span class="sxs-lookup"><span data-stu-id="49e63-109">Using mail flow rules to set the SCL value of a message gives you increased control in handling spam.</span></span>

 <span data-ttu-id="49e63-110">**Vad behöver du veta innan du börjar?**</span><span class="sxs-lookup"><span data-stu-id="49e63-110">**What do you need to know before you begin?**</span></span>

- <span data-ttu-id="49e63-111">Beräknad tid för att slutföra denna procedur: 10 minuter.</span><span class="sxs-lookup"><span data-stu-id="49e63-111">Estimated time to complete this procedure: 10 minutes.</span></span>

- <span data-ttu-id="49e63-112">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="49e63-112">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="49e63-113">Information om vilka behörigheter du behöver finns i posten "E-postflödesregler" i [Funktionsbehörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) eller [Funktionsbehörigheter i EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="49e63-113">To see what permissions you need, see the "Mail flow rules" entry in [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) or [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span>

- <span data-ttu-id="49e63-114">Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="49e63-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

### <a name="to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="49e63-115">Så här skapar du en regel för e-postflöde som anger SCL för ett meddelande</span><span class="sxs-lookup"><span data-stu-id="49e63-115">To create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="49e63-116">Välj Regler för **e-postflöde** \> i Administrationscentret för Exchange **.**</span><span class="sxs-lookup"><span data-stu-id="49e63-116">In the Exchange admin center (EAC), choose **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="49e63-117">Välj **Ny**![](../../media/ITPro-EAC-AddIcon.gif)lägg till ikon och välj sedan **Skapa en ny regel**.</span><span class="sxs-lookup"><span data-stu-id="49e63-117">Choose **New**![Add Icon](../../media/ITPro-EAC-AddIcon.gif), and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="49e63-118">Ange ett namn för regeln.</span><span class="sxs-lookup"><span data-stu-id="49e63-118">Specify a name for the rule.</span></span>

4. <span data-ttu-id="49e63-119">Välj **Fler alternativ**och ange sedan ett villkor som utlöser åtgärden som du ska ange för den här regeln (som ska anges i SCL-värdet) under Använd den här **regeln**om du anger ett villkor som utlöser den åtgärd som ska utlösas för den här regeln (som ska anges i SCL-värdet).</span><span class="sxs-lookup"><span data-stu-id="49e63-119">Choose **More options**, and then under **Apply this rule if**, specify a condition that will trigger the action you'll be setting for this rule (which is to set the SCL value).</span></span>

   <span data-ttu-id="49e63-120">Du kan till exempel ange **att avsändaren** \> **är intern/extern**och sedan väljer **du Inuti organisationen**i dialogrutan Välj **avsänaresplats** och väljer **ok**.</span><span class="sxs-lookup"><span data-stu-id="49e63-120">For example, you can set **The sender** \> **is internal/external**, and then in the **select sender location** dialog box, select **Inside the organization**, and choose **ok**.</span></span><br/>
   <span data-ttu-id="49e63-121">![Välj avsändningsplats](../../media/EOP-ETR-SetSCL-1.jpg)</span><span class="sxs-lookup"><span data-stu-id="49e63-121">![Select sender location](../../media/EOP-ETR-SetSCL-1.jpg)</span></span>

5. <span data-ttu-id="49e63-122">Under **Gör följande**väljer du Ändra **meddelandeegenskaperna** \> som **säkerhetsnivå för skräppost (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="49e63-122">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>

6. <span data-ttu-id="49e63-123">Markera ett av följande värden i rutan **Ange SCL** och välj **OK:**</span><span class="sxs-lookup"><span data-stu-id="49e63-123">In the **Specify SCL** box, select one of the following values, and choose **OK**:</span></span>

   - <span data-ttu-id="49e63-124">**Bypass spam filtrering:** Detta ställer in SCL till -1, vilket innebär att innehållsfiltrering inte kommer att utföras.</span><span class="sxs-lookup"><span data-stu-id="49e63-124">**Bypass spam filtering**: This sets the SCL to -1, which means that content filtering won't be performed.</span></span>

   - <span data-ttu-id="49e63-125">**0-4**: Meddelandet skickas vidare till innehållsfiltret för ytterligare bearbetning.</span><span class="sxs-lookup"><span data-stu-id="49e63-125">**0-4**: The message will be passed along to the content filter for additional processing.</span></span>

   - <span data-ttu-id="49e63-126">**5-6**: Åtgärden som anges för **skräppost** i tillämpliga innehållsfilterpolicyer kommer att tillämpas.</span><span class="sxs-lookup"><span data-stu-id="49e63-126">**5-6**: The action specified for **Spam** in the applicable content filter policies will be applied.</span></span> <span data-ttu-id="49e63-127">Som standard är åtgärden att skicka meddelandet till mottagarens skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="49e63-127">By default, the action is to send the message to the recipient's Junk Email folder.</span></span>

   - <span data-ttu-id="49e63-128">**7-9**: Åtgärden som anges för **Skräppost med högt förtroende** i tillämpliga innehållsfilterpolicyer kommer att tillämpas.</span><span class="sxs-lookup"><span data-stu-id="49e63-128">**7-9**: The action specified for **High confidence spam** in the applicable content filter policies will be applied.</span></span> <span data-ttu-id="49e63-129">Som standard är åtgärden att skicka meddelandet till mottagarens skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="49e63-129">By default, the action is to send the message to the recipient's Junk Email folder.</span></span>

   <span data-ttu-id="49e63-130">Mer information om hur du konfigurerar innehållsfilterprinciper finns i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="49e63-130">For more information about configuring your content filter policies, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="49e63-131">Mer information om SCL-värden i tjänsten finns i [Säkerhetsnivåer för skräppost](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="49e63-131">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

7. <span data-ttu-id="49e63-132">Ange ytterligare egenskaper för regeln och välj **spara**.</span><span class="sxs-lookup"><span data-stu-id="49e63-132">Specify additional properties for the rule, and choose **save**.</span></span>

   > [!TIP]
   > <span data-ttu-id="49e63-133">Mer information om de ytterligare egenskaper som du kan välja eller ange för den här regeln finns i [Använda EAC för att skapa regler för e-postflöde](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="49e63-133">For more information about the additional properties you can select or specify for this rule, see [Use the EAC to create mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="49e63-134">Hur vet du att det fungerade?</span><span class="sxs-lookup"><span data-stu-id="49e63-134">How do you know this worked?</span></span>

<span data-ttu-id="49e63-135">Om du vill kontrollera att den här proceduren fungerar korrekt skickar du ett e-postmeddelande till någon i organisationen och kontrollerar att åtgärden som utförs i meddelandet är som förväntat.</span><span class="sxs-lookup"><span data-stu-id="49e63-135">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="49e63-136">Om du till exempel **ställer in scl (Spam Confidence Level)** på **Kringgå skräppostfiltrering**ska meddelandet skickas till den angivna mottagarens inkorg.</span><span class="sxs-lookup"><span data-stu-id="49e63-136">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="49e63-137">Men om du **ställer in spam förtroendenivå (SCL)** till **9**, och **hög förtroende spam** åtgärder för din tillämpliga innehåll filter politik är att flytta meddelandet till mappen Skräppost, då meddelandet ska skickas till den angivna mottagarens skräppostmapp.</span><span class="sxs-lookup"><span data-stu-id="49e63-137">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable content filter policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
