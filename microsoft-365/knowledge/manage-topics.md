---
title: 'Hantera ämnen i ämnes centret i avsnitts erfarenhet (för hands version) '
description: Hantera ämnen i ämnes centret.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 92cf9c860ddbf199c70a7c2d89a7daba3dfe0fe7
ms.sourcegitcommit: 18f95c4b7f74881b4a6ce71ad2ffa78a6ead5584
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731337"
---
# <a name="manage-topics-in-the-topic-center-preview"></a><span data-ttu-id="b84e7-103">Hantera ämnen i ämnes centret (för hands version)</span><span class="sxs-lookup"><span data-stu-id="b84e7-103">Manage topics in the Topic center (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="b84e7-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="b84e7-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="b84e7-105">[Läs mer om Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="b84e7-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="b84e7-106">I ämnes Center kan en kunskaps chef Visa sidan **hantera ämnen** för att granska ämnen som har identifierats på SharePoint source locations, enligt vad som anges av din kunskaps administratör.</span><span class="sxs-lookup"><span data-stu-id="b84e7-106">In the Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![Ämnes Center](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="b84e7-108">Kunskaps cheferna hjälper till att hitta upptäckta ämnen via ämnes livs cykeln i vilka ämnen är:</span><span class="sxs-lookup"><span data-stu-id="b84e7-108">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="b84e7-109">Föreslagna: ett ämne identifieras av AI och har tillräckligt med stöd resurser, anslutningar och egenskaper för att uppfylla ämnets tröskel.</span><span class="sxs-lookup"><span data-stu-id="b84e7-109">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties to meet the topic threshold.</span></span>
- <span data-ttu-id="b84e7-110">Bekräftat: ett ämne som föreslås av AI är validerat.</span><span class="sxs-lookup"><span data-stu-id="b84e7-110">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="b84e7-111">Validering sker genom bekräftelse från en kunskaps administratör. Ett ämne kan dessutom bekräftas om minst två användare ger positiv feedback genom feedback om ämnen som är giltigt.</span><span class="sxs-lookup"><span data-stu-id="b84e7-111">Validation is done by confirmation from a knowledge admin. Additionally, a topic can be confirmed if at least two users give positive feedback through topic feedback that the topic is valid.</span></span>
- <span data-ttu-id="b84e7-112">Borttaget: ett ämne nekas av en kunskaps administratör och kommer inte längre att synas för tittarna.</span><span class="sxs-lookup"><span data-stu-id="b84e7-112">Removed: A topic is rejected by a knowledge admin and will no longer be visible to viewers.</span></span> <span data-ttu-id="b84e7-113">Ämnet kan vara i vilket tillstånd som helst när det tas bort (föreslås eller bekräftas).</span><span class="sxs-lookup"><span data-stu-id="b84e7-113">The topic can be in any state when it is removed (suggested or confirmed).</span></span> 
- <span data-ttu-id="b84e7-114">Publicerat: ett bekräftat ämne som har uppdaterats manuellt.</span><span class="sxs-lookup"><span data-stu-id="b84e7-114">Published: A confirmed topic that has been manually updated.</span></span>

   ![Ämnes livscykel diagram](../media/knowledge-management/topic-lifecycle.png) </br> 

## <a name="requirements"></a><span data-ttu-id="b84e7-116">Krav</span><span class="sxs-lookup"><span data-stu-id="b84e7-116">Requirements</span></span>

<span data-ttu-id="b84e7-117">Om du vill hantera ämnen i ämnes centret måste du:</span><span class="sxs-lookup"><span data-stu-id="b84e7-117">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="b84e7-118">Har en licens för ämne.</span><span class="sxs-lookup"><span data-stu-id="b84e7-118">Have a Topic Experiences license.</span></span>
- <span data-ttu-id="b84e7-119">Har behörighet till [**vem som kan hantera ämnen**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span><span class="sxs-lookup"><span data-stu-id="b84e7-119">Have permissions to [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions).</span></span> <span data-ttu-id="b84e7-120">Kunskaps administratörer kan ge användarna den här behörigheten i avsnittet behörigheter för kunskaps nätverk.</span><span class="sxs-lookup"><span data-stu-id="b84e7-120">Knowledge admins can give users this permission in the Knowledge Network topic permissions settings.</span></span> 

<span data-ttu-id="b84e7-121">Du kommer inte att kunna se sidan Hantera ämnen i ämnes centret om du inte har behörigheten **vem kan hantera ämnen** .</span><span class="sxs-lookup"><span data-stu-id="b84e7-121">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="b84e7-122">I ämnes Center kan en kunskaps chef granska ämnen som har identifierats i de SharePoint source locations som du har angett och kan antingen bekräfta eller avvisa dem.</span><span class="sxs-lookup"><span data-stu-id="b84e7-122">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="b84e7-123">En kunskaps chef kan också skapa och publicera nya avsnitts sidor om en sådan inte fanns i ämnes identifieringen eller redigera befintliga om de måste uppdateras.</span><span class="sxs-lookup"><span data-stu-id="b84e7-123">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="b84e7-124">Granska förslag till ämnen</span><span class="sxs-lookup"><span data-stu-id="b84e7-124">Review suggested topics</span></span>

<span data-ttu-id="b84e7-125">På sidan avsnitt Center hantera ämnen visas de avsnitt som upptäckts på dina angivna SharePoint source locations på fliken **föreslagen** . En kunskaps chef kan granska obekräftade ämnen och välja att bekräfta eller avvisa dem.</span><span class="sxs-lookup"><span data-stu-id="b84e7-125">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. A knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

<span data-ttu-id="b84e7-126">Så här granskar du ett föreslaget ämne:</span><span class="sxs-lookup"><span data-stu-id="b84e7-126">To review a suggested topic:</span></span>

1. <span data-ttu-id="b84e7-127">På sidan **hantera ämnen** väljer du fliken **föreslag** , markerar avsnittet för att öppna sidan ämne.</span><span class="sxs-lookup"><span data-stu-id="b84e7-127">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="b84e7-128">På sidan ämne granskar du sidan ämne och väljer **Redigera** om du behöver göra några ändringar på sidan.</span><span class="sxs-lookup"><span data-stu-id="b84e7-128">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

3. <span data-ttu-id="b84e7-129">När du har granskat avsnittet går du tillbaka till sidan Hantera ämnen.</span><span class="sxs-lookup"><span data-stu-id="b84e7-129">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="b84e7-130">För det markerade ämnet kan du:</span><span class="sxs-lookup"><span data-stu-id="b84e7-130">For the selected topic, you can:</span></span>

   - <span data-ttu-id="b84e7-131">Markera kryss rutan för att bekräfta ämnet.</span><span class="sxs-lookup"><span data-stu-id="b84e7-131">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="b84e7-132">Välj **x** om du vill avvisa avsnittet.</span><span class="sxs-lookup"><span data-stu-id="b84e7-132">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="b84e7-133">Bekräftade ämnen kommer att tas bort från den **föreslagna** listan och visas nu i listan **bekräftat** .</span><span class="sxs-lookup"><span data-stu-id="b84e7-133">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="b84e7-134">Avvisade ämnen tas bort från den **föreslagna** listan och visas nu på fliken **Borttaget** .</span><span class="sxs-lookup"><span data-stu-id="b84e7-134">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

## <a name="confirmed-topics"></a><span data-ttu-id="b84e7-135">Bekräftade ämnen</span><span class="sxs-lookup"><span data-stu-id="b84e7-135">Confirmed topics</span></span>

<span data-ttu-id="b84e7-136">På sidan Hantera ämnen visas ämnen som upptäckts på dina angivna SharePoint-källor och har bekräftats av en kunskaps chef eller "Fully source" som bekräftats av två eller fler personer via kort återkopplings funktionen på fliken **bekräftad** . Om det behövs kan en användare som har behörighet att hantera ämnen granska bekräftade ämnen och välja att avvisa dem.</span><span class="sxs-lookup"><span data-stu-id="b84e7-136">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="b84e7-137">Så här granskar du ett bekräftat ämne:</span><span class="sxs-lookup"><span data-stu-id="b84e7-137">To review a confirmed topic:</span></span>

1. <span data-ttu-id="b84e7-138">På fliken **bekräftat** markerar du avsnittet för att öppna sidan ämne.</span><span class="sxs-lookup"><span data-stu-id="b84e7-138">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="b84e7-139">På sidan ämne granskar du sidan ämne och väljer **Redigera** om du behöver göra några ändringar på sidan.</span><span class="sxs-lookup"><span data-stu-id="b84e7-139">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="b84e7-140">Observera att du fortfarande kan välja att avvisa ett bekräftat ämne.</span><span class="sxs-lookup"><span data-stu-id="b84e7-140">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="b84e7-141">Det gör du genom att gå till det markerade avsnittet i listan bekräftat och välja **x** om du vill avvisa avsnittet.</span><span class="sxs-lookup"><span data-stu-id="b84e7-141">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="b84e7-142">Publicerade ämnen</span><span class="sxs-lookup"><span data-stu-id="b84e7-142">Published topics</span></span>
<span data-ttu-id="b84e7-143">Publicerade ämnen har redigerats så att viss information alltid visas för alla som stöter på sidan.</span><span class="sxs-lookup"><span data-stu-id="b84e7-143">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="b84e7-144">Manuellt skapade avsnitt finns här.</span><span class="sxs-lookup"><span data-stu-id="b84e7-144">Manually created topics are listed here.</span></span>




