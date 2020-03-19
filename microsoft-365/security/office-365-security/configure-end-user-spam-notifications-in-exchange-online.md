---
title: Konfigurera skräppostmeddelanden för slutanvändare i Exchange Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: Du kan konfigurera skräppostmeddelanden för slutanvändare för standardprincipen för skräppostfilter för hela företaget eller för anpassade principer för skräppostfilter som tillämpas på domäner.
ms.openlocfilehash: c8690a64e222bca2bbdc6be62d1077a9d361ae85
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/29/2020
ms.locfileid: "42811123"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="b74d4-103">Konfigurera skräppostmeddelanden för slutanvändare i Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b74d4-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b74d4-104">Det här avsnittet är till Exchange Online-kunder som skyddar molnbaserade postlådor.</span><span class="sxs-lookup"><span data-stu-id="b74d4-104">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes.</span></span> <span data-ttu-id="b74d4-105">Fristående exchange online protection (EOP) som skyddar lokala postlådor bör läsa följande ämne i stället: [Konfigurera skräppostmeddelanden för slutanvändare i EOP](configure-end-user-spam-notifications-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="b74d4-105">Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="b74d4-106">Du kan konfigurera skräppostmeddelanden för slutanvändare för standardprincipen för skräppostfilter för hela företaget eller för anpassade principer för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="b74d4-106">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies.</span></span> <span data-ttu-id="b74d4-107">Genom att aktivera skräppostmeddelanden för slutanvändare kan användarna hantera sina egna skräppost-, mass- och nätfiskemeddelanden i karantän.</span><span class="sxs-lookup"><span data-stu-id="b74d4-107">Enabling end-user spam notification messages lets your users manage their own quarantined spam, bulk, and phishing messages.</span></span>   
  
<span data-ttu-id="b74d4-108">Skräppostmeddelanden för slutanvändare innehåller en lista över alla meddelanden som användaren har fått i skräppost i karantän under en tidsperiod som du konfigurerar (du kan ange ett värde mellan 1 och 15 dagar).</span><span class="sxs-lookup"><span data-stu-id="b74d4-108">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days).</span></span> <span data-ttu-id="b74d4-109">Du kan också konfigurera det språk som meddelandet skrivs på.</span><span class="sxs-lookup"><span data-stu-id="b74d4-109">You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="b74d4-110">När slutanvändarna har fått ett meddelande kan de välja mellan följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="b74d4-110">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="b74d4-111">**Blockera avsändare** om du vill att Office 365 ska lägga till avsändaren i listan blockerade avsändare.</span><span class="sxs-lookup"><span data-stu-id="b74d4-111">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="b74d4-112">**Släpp** om meddelandet inte är skräppost och du vill att Office 365 ska skicka meddelandet till postlådan.</span><span class="sxs-lookup"><span data-stu-id="b74d4-112">**Release** if the message isn't spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="b74d4-113">**Granska** om du vill navigera till karantänportalen i Security & Compliance Center om du vill vidta andra åtgärder, till exempel Förhandsgranska eller Släpp.</span><span class="sxs-lookup"><span data-stu-id="b74d4-113">**Review** to navigate to the Quarantine Portal within the Security & Compliance Center if you want to take other actions, such as Preview or Release.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b74d4-114">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="b74d4-114">What do you need to know before you begin?</span></span>

<span data-ttu-id="b74d4-115">Beräknad tid att slutföra: 2 minuter</span><span class="sxs-lookup"><span data-stu-id="b74d4-115">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="b74d4-116">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="b74d4-116">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="b74d4-117">Information om vilka behörigheter du behöver finns i posten "Anti-spam" i [avsnittet Funktionsbehörigheter i Exchange Online.](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)</span><span class="sxs-lookup"><span data-stu-id="b74d4-117">To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) topic.</span></span> 
  
<span data-ttu-id="b74d4-118">Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="b74d4-118">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="b74d4-119">Använda EAC för att konfigurera skräppostmeddelanden för slutanvändare</span><span class="sxs-lookup"><span data-stu-id="b74d4-119">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="b74d4-120">I Administrationscentret för Exchange (EAC) navigerar du till **filtret Skydds** \> **skräppost**.</span><span class="sxs-lookup"><span data-stu-id="b74d4-120">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="b74d4-121">Välj den policy för skräppostfilter som du vill aktivera skräppostmeddelanden för slutanvändare (de är inaktiverade som standard).</span><span class="sxs-lookup"><span data-stu-id="b74d4-121">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="b74d4-122">Klicka på länken **Konfigurera skräppostmeddelanden** i den högra rutan där sammanfattningsinformationen om din princip visas.</span><span class="sxs-lookup"><span data-stu-id="b74d4-122">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="b74d4-123">I den efterföljande dialogrutan kan du konfigurera följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="b74d4-123">In the subsequent dialog box, you can configure the following options:</span></span>
    
   - <span data-ttu-id="b74d4-124">**Aktivera skräppostmeddelanden för slutanvändare** Markera den här kryssrutan för att aktivera skräppostmeddelanden för slutanvändare för den här principen.</span><span class="sxs-lookup"><span data-stu-id="b74d4-124">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy.</span></span> <span data-ttu-id="b74d4-125">(Om den här principen är aktiverad kan du däremot avmarkera den här kryssrutan för att inaktivera skräppostmeddelanden för slutanvändare för den här principen.)</span><span class="sxs-lookup"><span data-stu-id="b74d4-125">(Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
   - <span data-ttu-id="b74d4-126">**Skicka skräppostmeddelanden för slutanvändare varje (dagar)** Ange hur ofta slutanvändarnas skräppostmeddelanden ska skickas.</span><span class="sxs-lookup"><span data-stu-id="b74d4-126">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications.</span></span> <span data-ttu-id="b74d4-127">Standardvärdet är 3 dagar.</span><span class="sxs-lookup"><span data-stu-id="b74d4-127">The default is 3 days.</span></span> <span data-ttu-id="b74d4-128">Du kan ange mellan 1 och 15 dagar.</span><span class="sxs-lookup"><span data-stu-id="b74d4-128">You can specify between 1 and 15 days.</span></span> <span data-ttu-id="b74d4-129">Om du till exempel anger 7 dagar innehåller meddelandet en lista över alla meddelanden som är avsedda för användaren under de senaste 7 dagarna som har skickats till skräppostkarantänen i stället.</span><span class="sxs-lookup"><span data-stu-id="b74d4-129">If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
   - <span data-ttu-id="b74d4-130">**Meddelandespråk** Med listrutan väljer du det språk på vilket du vill skriva skräppostmeddelanden för slutanvändare för den här principen.</span><span class="sxs-lookup"><span data-stu-id="b74d4-130">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
   - <span data-ttu-id="b74d4-131">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b74d4-131">Click **Save**.</span></span> <span data-ttu-id="b74d4-132">En sammanfattning av dina principinställningar för skräppostfilter, inklusive inställningarna för skräppostmeddelanden för slutanvändare, visas i den högra rutan.</span><span class="sxs-lookup"><span data-stu-id="b74d4-132">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="b74d4-133">Skräppostmeddelanden för slutanvändare fungerar bara för principer för skräppostfilter som är aktiverade.</span><span class="sxs-lookup"><span data-stu-id="b74d4-133">End-user spam notifications will only be functional for spam filter policies that are enabled.</span></span> <span data-ttu-id="b74d4-134">> Skräppostmeddelanden för slutanvändare skickas bara en gång per dag.</span><span class="sxs-lookup"><span data-stu-id="b74d4-134">>  End-user spam notifications are only sent once per day.</span></span> <span data-ttu-id="b74d4-135">Leveranstiden för meddelandet kan inte garanteras för en viss kund och kan inte konfigureras.</span><span class="sxs-lookup"><span data-stu-id="b74d4-135">The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="b74d4-136">**Tips:** Om du vill testa skräppostmeddelanden för slutanvändare genom att skicka dem till en begränsad uppsättning användare innan du implementerar dem helt, skapar du en anpassad policy för skräppost för slutanvändare för de domäner där användarna finns.</span><span class="sxs-lookup"><span data-stu-id="b74d4-136">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="b74d4-137">Skapa sedan en regel \*\* \> \*\*för e-postflöde (kallas även transportregel) i EAC-reglerna för att blockera meddelanden från quarantine@messaging.microsoft.com (e-postadressen som skickar meddelanden) med undantag för de användare som du vill ta emot meddelandena.</span><span class="sxs-lookup"><span data-stu-id="b74d4-137">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="b74d4-138">Följande bild är ett exempel på att skapa ett undantag för två användare (SaraD och AlexD) från domänen Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="b74d4-138">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Transportregel för att testa skräppostmeddelanden för slutanvändare](../../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="use-the-scc-to-configure-end-user-spam-notifications"></a><span data-ttu-id="b74d4-140">Använda SCC för att konfigurera skräppostmeddelanden för slutanvändare</span><span class="sxs-lookup"><span data-stu-id="b74d4-140">Use the SCC to configure end-user spam notifications</span></span>

<span data-ttu-id="b74d4-141">Du kan också använda Security and Compliance Center (SCC) för att konfigurera skräppostmeddelanden för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="b74d4-141">You can also use the Security and Compliance Center (SCC) to configure end-user spam notifications.</span></span> <span data-ttu-id="b74d4-142">Följ anvisningarna nedan:</span><span class="sxs-lookup"><span data-stu-id="b74d4-142">Follow these steps:</span></span>

1. <span data-ttu-id="b74d4-143">Öppna Säkerhets- och efterlevnadscenter, navigera till policy **Policy** \> **mot** https://protection.office.com/antispamskräppost **för hothantering** \> eller använd direktlänken .</span><span class="sxs-lookup"><span data-stu-id="b74d4-143">Open the Security and Compliance Center, navigate to **Threat management** \> **Policy** \> **Anti-spam** or use the direct link https://protection.office.com/antispam.</span></span>

2. <span data-ttu-id="b74d4-144">Klicka på nedpilen bredvid den skräppostfilterprincip som du vill aktivera skräppostmeddelanden för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="b74d4-144">Click the down arrow next to the spam filter policy for which you want to enable end-user spam notifications.</span></span>

3. <span data-ttu-id="b74d4-145">Klicka på länken **Konfigurera skräppostmeddelanden** för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="b74d4-145">Click on the **Configure End-user spam notifications** link.</span></span>

4. <span data-ttu-id="b74d4-146">I den efterföljande dialogrutan kan du konfigurera följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="b74d4-146">In the subsequent dialog box, you can configure the following options:</span></span>
    
   - <span data-ttu-id="b74d4-147">**Aktivera skräppostmeddelanden för slutanvändare** Markera den här kryssrutan för att aktivera skräppostmeddelanden för slutanvändare för den här principen.</span><span class="sxs-lookup"><span data-stu-id="b74d4-147">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy.</span></span> <span data-ttu-id="b74d4-148">(Om den här principen är aktiverad kan du däremot avmarkera den här kryssrutan för att inaktivera skräppostmeddelanden för slutanvändare för den här principen.)</span><span class="sxs-lookup"><span data-stu-id="b74d4-148">(Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
   - <span data-ttu-id="b74d4-149">**Skicka skräppostmeddelanden för slutanvändare varje (dagar)** Ange hur ofta slutanvändarnas skräppostmeddelanden ska skickas.</span><span class="sxs-lookup"><span data-stu-id="b74d4-149">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications.</span></span> <span data-ttu-id="b74d4-150">Standardvärdet är 3 dagar.</span><span class="sxs-lookup"><span data-stu-id="b74d4-150">The default is 3 days.</span></span> <span data-ttu-id="b74d4-151">Du kan ange mellan 1 och 15 dagar.</span><span class="sxs-lookup"><span data-stu-id="b74d4-151">You can specify between 1 and 15 days.</span></span> <span data-ttu-id="b74d4-152">Om du till exempel anger 7 dagar innehåller meddelandet en lista över alla meddelanden som är avsedda för användaren under de senaste 7 dagarna som har skickats till skräppostkarantänen i stället.</span><span class="sxs-lookup"><span data-stu-id="b74d4-152">If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
   - <span data-ttu-id="b74d4-153">**Meddelandespråk** Med listrutan väljer du det språk på vilket du vill skriva skräppostmeddelanden för slutanvändare för den här principen.</span><span class="sxs-lookup"><span data-stu-id="b74d4-153">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
   - <span data-ttu-id="b74d4-154">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b74d4-154">Click **Save**.</span></span> <span data-ttu-id="b74d4-155">En sammanfattning av dina principinställningar för skräppostfilter, inklusive inställningarna för skräppostmeddelanden för slutanvändare, visas i fönstret.</span><span class="sxs-lookup"><span data-stu-id="b74d4-155">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the pane.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="b74d4-156">Mer information</span><span class="sxs-lookup"><span data-stu-id="b74d4-156">For more information</span></span>

[<span data-ttu-id="b74d4-157">Konfigurera principer för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="b74d4-157">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="b74d4-158">Set-hostedContentFilterPolicy</span><span class="sxs-lookup"><span data-stu-id="b74d4-158">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)
  
