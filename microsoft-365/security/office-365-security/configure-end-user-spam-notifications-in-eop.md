---
title: Konfigurera skräppostmeddelanden från slutanvändare i EOP
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
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
ms.collection:
- M365-security-compliance
description: Du kan konfigurera skräppostmeddelanden för slutanvändare för standardprincipen för företagsomfattande innehållsfilter eller för anpassade innehållsfilterprinciper som tillämpas på domäner.
ms.openlocfilehash: 6ac43ee3419e7b768312b6826994a5b8f5e4a231
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808622"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a><span data-ttu-id="f71f6-103">Konfigurera skräppostmeddelanden från slutanvändare i EOP</span><span class="sxs-lookup"><span data-stu-id="f71f6-103">Configure end-user spam notifications in EOP</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f71f6-104">Det här avsnittet gäller fristående Exchange Online Protection (EOP) som skyddar lokala postlådor.</span><span class="sxs-lookup"><span data-stu-id="f71f6-104">This topic is for Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes.</span></span> <span data-ttu-id="f71f6-105">Exchange Online-kunder som skyddar molnbaserade postlådor bör läsa följande ämne i stället: [Konfigurera skräppostmeddelanden för slutanvändare i Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="f71f6-105">Exchange Online customers who are protecting cloud-hosted mailboxes should read the following topic instead: [Configure end-user spam notifications in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span></span> 
  
<span data-ttu-id="f71f6-106">Du kan konfigurera skräppostmeddelanden för slutanvändare för standardprincipen för skräppostfilter för hela företaget eller för anpassade principer för skräppostfilter.</span><span class="sxs-lookup"><span data-stu-id="f71f6-106">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies.</span></span> <span data-ttu-id="f71f6-107">Genom att aktivera meddelanden om skräppost från slutanvändaren kan användarna hantera sina egna meddelanden om skräppost, bulk och nätfiske i karantän.</span><span class="sxs-lookup"><span data-stu-id="f71f6-107">Enabling end-user spam notification messages lets your users manage their own quarantined spam, bulk, and phishing messages.</span></span> 
  
<span data-ttu-id="f71f6-108">Skräppostmeddelanden från slutanvändare innehåller en lista över alla meddelanden om skräppost i karantän som slutanvändaren har fått under en tidsperiod som du konfigurerar (du kan ange ett värde mellan 1 och 15 dagar).</span><span class="sxs-lookup"><span data-stu-id="f71f6-108">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days).</span></span> <span data-ttu-id="f71f6-109">Du kan också konfigurera det språk på vilket meddelandet skrivs.</span><span class="sxs-lookup"><span data-stu-id="f71f6-109">You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="f71f6-110">När slutanvändarna har fått ett meddelande kan de välja mellan följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="f71f6-110">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="f71f6-111">**Blockera avsändare** om du vill att Office 365 ska lägga till avsändaren i listan över blockerade avsändare.</span><span class="sxs-lookup"><span data-stu-id="f71f6-111">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="f71f6-112">**Släpp** om meddelandet inte är skräppost och du vill att Office 365 ska skicka meddelandet till postlådan.</span><span class="sxs-lookup"><span data-stu-id="f71f6-112">**Release** if the message isn't spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="f71f6-113">**Granska** för att navigera till karantänportalen i Säkerhets- och efterlevnadscenter om du vill vidta andra åtgärder, till exempel Förhandsgranska eller Släpp.</span><span class="sxs-lookup"><span data-stu-id="f71f6-113">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f71f6-114">Vad behöver jag veta innan jag börjar?</span><span class="sxs-lookup"><span data-stu-id="f71f6-114">What do you need to know before you begin?</span></span>
<span data-ttu-id="f71f6-115"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="f71f6-115"><a name="sectionSection0"> </a></span></span>

<span data-ttu-id="f71f6-116">Beräknad tid att slutföra: 5 minuter</span><span class="sxs-lookup"><span data-stu-id="f71f6-116">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="f71f6-117">Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna.</span><span class="sxs-lookup"><span data-stu-id="f71f6-117">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="f71f6-118">Om du vill se vilka behörigheter du behöver läser du posten "Anti-spam" i [funktionsbehörigheterna i EOP-avsnittet.](feature-permissions-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="f71f6-118">To see what permissions you need, see the "Anti-spam" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
  
<span data-ttu-id="f71f6-119">Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns i [Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="f71f6-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="f71f6-120">Använd EAC för att konfigurera skräppostmeddelanden från slutanvändare</span><span class="sxs-lookup"><span data-stu-id="f71f6-120">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="f71f6-121">I Exchange Admin Center (EAC) navigerar du till > **skräppostfiltret**. **Protection**</span><span class="sxs-lookup"><span data-stu-id="f71f6-121">In the Exchange Admin Center (EAC), navigate to **Protection** > **Spam filter**.</span></span>
    
2. <span data-ttu-id="f71f6-122">Välj den innehållsfilterprincip som du vill aktivera skräppostmeddelanden från slutanvändare (de inaktiveras som standard).</span><span class="sxs-lookup"><span data-stu-id="f71f6-122">Select the content filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="f71f6-123">Klicka på länken **Konfigurera skräppostmeddelanden** för slutanvändare i det högra fönstret, där sammanfattningsinformationen om din policy visas.</span><span class="sxs-lookup"><span data-stu-id="f71f6-123">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="f71f6-124">I den efterföljande dialogrutan kan du konfigurera följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="f71f6-124">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="f71f6-125">**Aktivera skräppostmeddelanden från slutanvändare** Markera den här kryssrutan för att aktivera skräppostmeddelanden från slutanvändaren för den här principen.</span><span class="sxs-lookup"><span data-stu-id="f71f6-125">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy.</span></span> <span data-ttu-id="f71f6-126">(Omvänt, om den här principen är aktiverad, kan du avmarkera den här kryssrutan för att inaktivera skräppostmeddelanden för slutanvändare för den här principen.)</span><span class="sxs-lookup"><span data-stu-id="f71f6-126">(Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="f71f6-127">**Skicka skräppostmeddelanden för slutanvändare varje (dagar)** Ange hur ofta skräppostmeddelanden ska skickas.</span><span class="sxs-lookup"><span data-stu-id="f71f6-127">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications.</span></span> <span data-ttu-id="f71f6-128">Standardär 3 dagar.</span><span class="sxs-lookup"><span data-stu-id="f71f6-128">The default is 3 days.</span></span> <span data-ttu-id="f71f6-129">Du kan ange mellan 1 och 15 dagar.</span><span class="sxs-lookup"><span data-stu-id="f71f6-129">You can specify between 1 and 15 days.</span></span> <span data-ttu-id="f71f6-130">Om du till exempel anger 7 dagar innehåller meddelandet en lista över alla meddelanden som är avsedda för användaren under de senaste 7 dagarna som skickades till skräppostkarantänen i stället.</span><span class="sxs-lookup"><span data-stu-id="f71f6-130">If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="f71f6-131">**Meddelandespråk** Med hjälp av listrutan väljer du det språk på vilket du vill skriva skräppostmeddelanden för slutanvändaren för den här principen.</span><span class="sxs-lookup"><span data-stu-id="f71f6-131">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="f71f6-132">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f71f6-132">Click **save**.</span></span> <span data-ttu-id="f71f6-133">En sammanfattning av inställningarna för innehållsfilter, inklusive inställningarna för skräppostmeddelanden från slutanvändaren, visas i den högra rutan.</span><span class="sxs-lookup"><span data-stu-id="f71f6-133">A summary of your content filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="f71f6-134">Skräppostmeddelanden från slutanvändare fungerar bara för innehållsfilterprinciper som är aktiverade.</span><span class="sxs-lookup"><span data-stu-id="f71f6-134">End-user spam notifications will only be functional for content filter policies that are enabled.</span></span> <span data-ttu-id="f71f6-135">> slutanvändare sa skräppostmeddelanden endast en gång per dag.</span><span class="sxs-lookup"><span data-stu-id="f71f6-135">>  End-user spam notifications are only sent once per day.</span></span> <span data-ttu-id="f71f6-136">Leveranstiden för meddelandet kan inte garanteras för någon specifik kund och kan inte konfigureras.</span><span class="sxs-lookup"><span data-stu-id="f71f6-136">The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="f71f6-137">**Tips:** Om du vill testa skräppostmeddelanden från slutanvändare genom att skicka dem till en begränsad uppsättning användare innan de implementeras fullt ut skapar du en policy för anpassat innehållsfilter som gör det möjligt för skräppostmeddelanden från slutanvändaren för de domäner där användarna finns.</span><span class="sxs-lookup"><span data-stu-id="f71f6-137">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom content filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="f71f6-138">Skapa sedan en regel \*\* \> \*\*för e-postflöde (kallas även en transportregel) i EAC-flödesreglerna för att blockera meddelanden från quarantine@messaging.microsoft.com (e-postadressen som skickar meddelanden) med undantag för de användare som du vill ta emot meddelandena.</span><span class="sxs-lookup"><span data-stu-id="f71f6-138">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="f71f6-139">Följande bild är ett exempel på att skapa ett undantag för två användare (SaraD och AlexD) från domän Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="f71f6-139">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Transportregel för att testa skräppostmeddelanden för slutanvändare](../../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="f71f6-141">Mer information</span><span class="sxs-lookup"><span data-stu-id="f71f6-141">For more information</span></span>

[<span data-ttu-id="f71f6-142">Konfigurera principer för skräppostfilter</span><span class="sxs-lookup"><span data-stu-id="f71f6-142">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
