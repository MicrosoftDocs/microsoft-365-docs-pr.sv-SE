---
title: Hantera ämnen i ämnescentret i Microsoft Viva-ämnen
description: Så här hanterar du ämnen i ämnescentret.
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: ergradel
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: 59581dce3701e622a1e2d7ed264370c9d92b3211
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327286"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="792be-103">Hantera ämnen i ämnescentret i Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="792be-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>

<span data-ttu-id="792be-104">I ämnescentret viva ämnen kan en  knowledge manager visa sidan Hantera ämnen för att granska ämnen som har identifierats på de källplatser som angetts av din kunskapsadministratör.</span><span class="sxs-lookup"><span data-stu-id="792be-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in the source locations as specified by your knowledge admin.</span></span>  

   ![Ämnescenter](../media/knowledge-management/topic-center.png)  

## <a name="topic-stages"></a><span data-ttu-id="792be-106">Ämnesfaser</span><span class="sxs-lookup"><span data-stu-id="792be-106">Topic stages</span></span>

<span data-ttu-id="792be-107">Knowledge managers help to guide discovered topics through the various topic lifecycle stages: **Suggested**, **Confirmed**, **Published**, and **Removed**.</span><span class="sxs-lookup"><span data-stu-id="792be-107">Knowledge managers help to guide discovered topics through the various topic lifecycle stages: **Suggested**, **Confirmed**, **Published**, and **Removed**.</span></span>

   ![Diagram för livscykel för ämnen](../media/knowledge-management/topic-lifecycle.png) 

- <span data-ttu-id="792be-109">**Förslag:** Ett ämne har identifierats med AI och har tillräckligt med stödresurser, anslutningar och egenskaper.</span><span class="sxs-lookup"><span data-stu-id="792be-109">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span> <span data-ttu-id="792be-110">(De är markerade som ett **föreslaget ämne** i användargränssnittet.)</span><span class="sxs-lookup"><span data-stu-id="792be-110">(These are marked as a **Suggested Topic** in the UI.)</span></span>

- <span data-ttu-id="792be-111">**Bekräftad**: Ett ämne som har föreslagits av AI valideras.</span><span class="sxs-lookup"><span data-stu-id="792be-111">**Confirmed**: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="792be-112">Validering av ämne måste bekräftas av en knowledge manager.</span><span class="sxs-lookup"><span data-stu-id="792be-112">Topic validation must be confirmed by a knowledge manager.</span></span> <span data-ttu-id="792be-113">För att man ska kunna bekräfta ett ämne måste två positiva röster tas emot från användare som har röstat med hjälp av feedbackmekanismen på ämneskortet.</span><span class="sxs-lookup"><span data-stu-id="792be-113">For a topic to be confirmed, there must be a net of two positive votes received from users who voted using the feedback mechanism on the topic card.</span></span> <span data-ttu-id="792be-114">Om en användare till exempel har röstat på positivt och en användare har röstat nej till ett visst ämne, skulle du fortfarande behöva två positiva röster för att ämnet ska bekräftas.</span><span class="sxs-lookup"><span data-stu-id="792be-114">For example, if one user voted positive and one user voted negative for a particular topic, you would still need two more positive votes for the topic to be confirmed.</span></span>
 
- <span data-ttu-id="792be-115">**Publicerades**: Ett bekräftat ämne som har redigerats: manuell redigering har gjorts för att förbättra kvaliteten.</span><span class="sxs-lookup"><span data-stu-id="792be-115">**Published**: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>

- <span data-ttu-id="792be-116">**Tas** bort : Ett ämne avvisas av en kunskapshanterare och visas inte längre för tittare.</span><span class="sxs-lookup"><span data-stu-id="792be-116">**Removed**: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="792be-117">Ett ämne kan tas bort i valfri stat (förslag, bekräftade eller publicerade).</span><span class="sxs-lookup"><span data-stu-id="792be-117">A topic can be removed in any state (suggested, confirmed, or published).</span></span> <span data-ttu-id="792be-118">För att ett ämne ska kunna tas bort måste två negativa röster tas emot från användare som har röstat med hjälp av feedbackmekanismen på ämneskortet.</span><span class="sxs-lookup"><span data-stu-id="792be-118">For a topic to be removed, there must be a net of two negative votes received from users who voted using the feedback mechanisms on the topic card.</span></span> <span data-ttu-id="792be-119">Om en användare till exempel har röstat nej och en användare har röstat positivt på ett visst ämne, skulle du ändå behöva två fler negativa röster för att ämnet ska tas bort.</span><span class="sxs-lookup"><span data-stu-id="792be-119">For example, if one user voted negative and one user voted positive for a particular topic, you would still need two more negative votes for the topic to be removed.</span></span> <span data-ttu-id="792be-120">När ett publicerat ämne tas bort måste sidan med den curated informationen tas bort manuellt via ämnescentrets sidbibliotek.</span><span class="sxs-lookup"><span data-stu-id="792be-120">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

<span data-ttu-id="792be-121">På sidan **Hantera ämnen** kan en kunskapshanterare se om ett ämne har bekräftats eller tagits bort av användarens röster eller av en viss person.</span><span class="sxs-lookup"><span data-stu-id="792be-121">On the **Manage topics** page, a knowledge manager can see whether a topic was confirmed or removed by user votes or by a specific person.</span></span> <span data-ttu-id="792be-122">För ämnen som tagits bort på grund av  användarens röster  visas orsaken i kolumnen Borttaget av som Användarröster i stället för en persons namn.</span><span class="sxs-lookup"><span data-stu-id="792be-122">For example, for topics removed by user votes, the reason is shown in the **Removed by** column as **User votes** rather than a person's name.</span></span> 

   ![Skärmbild av sidan Hantera ämnen med listan borttagna ämnen med Användarens röster markerade.](../media/knowledge-management/removed-topics-user-votes.png) 

> [!Note] 
> <span data-ttu-id="792be-124">På **sidan Hantera ämnen** kan varje kunskapshanterare bara se ämnen där de har åtkomst till underliggande filer och sidor som är kopplade till avsnittet.</span><span class="sxs-lookup"><span data-stu-id="792be-124">On the **Manage topics** page, each knowledge manager will only be able to see topics where they have access to the underlying files and pages connected to the topic.</span></span> <span data-ttu-id="792be-125">Den här behörighets trimningen visas i listan med ämnen på flikarna **Föreslagna,** **Bekräftade,** **Publicerade** **och Borttagna.**</span><span class="sxs-lookup"><span data-stu-id="792be-125">This permission trimming will be reflected in the list of topics that appear in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs.</span></span> <span data-ttu-id="792be-126">I avsnittet antal visas dock det totala antalet i organisationen, oavsett behörighet.</span><span class="sxs-lookup"><span data-stu-id="792be-126">The topic counts, however, show the total counts in the organization regardless of permissions.</span></span>

## <a name="requirements"></a><span data-ttu-id="792be-127">Krav</span><span class="sxs-lookup"><span data-stu-id="792be-127">Requirements</span></span>

<span data-ttu-id="792be-128">Om du vill hantera ämnen i ämnescentret måste du:</span><span class="sxs-lookup"><span data-stu-id="792be-128">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="792be-129">Ha en Viva Topics-licens.</span><span class="sxs-lookup"><span data-stu-id="792be-129">Have a Viva Topics license.</span></span>

- <span data-ttu-id="792be-130">Ha [**behörigheten Vem kan hantera**](./topic-experiences-user-permissions.md) ämnen.</span><span class="sxs-lookup"><span data-stu-id="792be-130">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="792be-131">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span><span class="sxs-lookup"><span data-stu-id="792be-131">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="792be-132">Du kan inte visa sidan Hantera **ämnen i ämnescentret** om du inte har behörigheten Vem **kan hantera** ämnen.</span><span class="sxs-lookup"><span data-stu-id="792be-132">You will not be able to view the **Manage topics** page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="792be-133">I ämnescentret kan en knowledge manager granska ämnen som har identifierats på de källplatser du angett och bekräfta eller ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="792be-133">In the topic center, a knowledge manager can review topics that have been identified in the source locations you specified, and can either confirm or remove them.</span></span> <span data-ttu-id="792be-134">En knowledge manager kan också skapa och publicera nya ämnessidor om en inte hittades i identifieringen av ämnen, eller redigera befintliga sidor om de behöver uppdateras.</span><span class="sxs-lookup"><span data-stu-id="792be-134">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>

## <a name="review-suggested-topics"></a><span data-ttu-id="792be-135">Granska föreslagna ämnen</span><span class="sxs-lookup"><span data-stu-id="792be-135">Review suggested topics</span></span>

<span data-ttu-id="792be-136">På sidan **Hantera ämnen** visas ämnen som identifierats på dina angivna platser för SharePoint-källor på **fliken** Förslag. Vid behov kan en kunskapshanterare granska ämnen som inte har bekräftats och välja att bekräfta eller ta bort dem.</span><span class="sxs-lookup"><span data-stu-id="792be-136">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations will be listed on the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or remove them.</span></span>

   ![Föreslagna ämnen](../media/knowledge-management/quality-score.png) 

<span data-ttu-id="792be-138">Så här granskar du ett föreslaget ämne:</span><span class="sxs-lookup"><span data-stu-id="792be-138">To review a suggested topic:</span></span>

1. <span data-ttu-id="792be-139">På sidan **Hantera ämnen** väljer du **fliken Förslag** och väljer sedan ämnet för att öppna ämnessidan.</span><span class="sxs-lookup"><span data-stu-id="792be-139">On the **Manage topics** page, select the **Suggested** tab, and then select the topic to open the topic page.</span></span>

2. <span data-ttu-id="792be-140">På ämnessidan granskar du ämnessidan och väljer **Redigera** om du behöver göra ändringar på sidan.</span><span class="sxs-lookup"><span data-stu-id="792be-140">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="792be-141">När du publicerar eventuella ändringar flyttas det här avsnittet till **fliken Publicerade.**</span><span class="sxs-lookup"><span data-stu-id="792be-141">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="792be-142">När du har granskat ämnet går du tillbaka till **sidan Hantera** ämnen.</span><span class="sxs-lookup"><span data-stu-id="792be-142">After reviewing the topic, go back to the **Manage topics** page.</span></span> <span data-ttu-id="792be-143">För det valda avsnittet kan du:</span><span class="sxs-lookup"><span data-stu-id="792be-143">For the selected topic, you can:</span></span>

   - <span data-ttu-id="792be-144">Välj bockmarkeringen för att bekräfta ämnet.</span><span class="sxs-lookup"><span data-stu-id="792be-144">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="792be-145">Välj **x om** du vill ta bort ämnet.</span><span class="sxs-lookup"><span data-stu-id="792be-145">Select the **x** if you want to remove the topic.</span></span>

    <span data-ttu-id="792be-146">Bekräftade ämnen tas bort från listan **Förslag** och visas nu i **den bekräftade** listan.</span><span class="sxs-lookup"><span data-stu-id="792be-146">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="792be-147">Borttagna ämnen tas bort från **listan Förslag** och visas nu på fliken **Borttaget.**</span><span class="sxs-lookup"><span data-stu-id="792be-147">Removed topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

### <a name="quality-score"></a><span data-ttu-id="792be-148">Kvalitetsresultat</span><span class="sxs-lookup"><span data-stu-id="792be-148">Quality score</span></span>

<span data-ttu-id="792be-149">Varje ämne som visas på **sidan Föreslagna** ämnen har tilldelats ett kvalitetsresultat.</span><span class="sxs-lookup"><span data-stu-id="792be-149">Each topic that appears on the **Suggested** topics page has a quality score assigned to it.</span></span> <span data-ttu-id="792be-150">Kvalitetsresultatet är en reflektion av mängden information som medelvärdet ser för information om ämnet, med tanke på att varje användare kan se mer eller mindre information på grund av de behörigheter som de kan ha eller kanske inte har på informationen i ett ämne.</span><span class="sxs-lookup"><span data-stu-id="792be-150">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="792be-151">Kvalitetsresultatet kan bidra till att ge insyn i de ämnen som innehåller mest information och kan vara användbart för att hitta ämnen som kan behöva redigeras manuellt.</span><span class="sxs-lookup"><span data-stu-id="792be-151">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="792be-152">Ett ämne med lägre kvalitet kan till exempel vara ett resultat av att vissa användare inte har SharePoint-behörigheter till relevanta filer eller webbplatser som AI har inkluderat i ämnet.</span><span class="sxs-lookup"><span data-stu-id="792be-152">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="792be-153">En deltagare kan sedan redigera ämnet så att det innehåller informationen (vid behov), som sedan kan visas för alla användare som kan visa ämnet.</span><span class="sxs-lookup"><span data-stu-id="792be-153">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

### <a name="impressions"></a><span data-ttu-id="792be-154">Intryck</span><span class="sxs-lookup"><span data-stu-id="792be-154">Impressions</span></span>

<span data-ttu-id="792be-155">I kolumnen Intryck visas hur många gånger ett ämne har **visats** för slutanvändarna.</span><span class="sxs-lookup"><span data-stu-id="792be-155">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="792be-156">Det omfattar vyer via ämnessvarskort i sökningar och genom viktiga ämnen.</span><span class="sxs-lookup"><span data-stu-id="792be-156">This includes views through topic answer cards in search and through topic highlights.</span></span> <span data-ttu-id="792be-157">Den återspeglar inte genomklickning på dessa ämnen, men att ämnet har visats.</span><span class="sxs-lookup"><span data-stu-id="792be-157">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="792be-158">Kolumnen **Intryck visas** för ämnen på flikarna **Föreslagna**, **Bekräftade,** **Publicerade** och **Borttagna** på **sidan Hantera** ämnen.</span><span class="sxs-lookup"><span data-stu-id="792be-158">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the **Manage topics** page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="792be-159">Bekräftade ämnen</span><span class="sxs-lookup"><span data-stu-id="792be-159">Confirmed topics</span></span>

<span data-ttu-id="792be-160">På sidan **Hantera** ämnen visas ämnen som identifierats på dina angivna platser för SharePoint-källor och har bekräftats av en knowledge manager eller "crowdsourced" som bekräftas av ett nettot två eller fler personer (balansera negativa användarröster mot positiva användarröster) via systemet för kortfeedback på fliken **Bekräftad.** Om det behövs kan en användare med behörighet att hantera ämnen granska bekräftade ämnen och välja att avvisa dem.</span><span class="sxs-lookup"><span data-stu-id="792be-160">On the **Manage topics** page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by a net two or more people (balancing negative user votes against positive user votes) through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="792be-161">Granska ett bekräftat ämne:</span><span class="sxs-lookup"><span data-stu-id="792be-161">To review a confirmed topic:</span></span>

1. <span data-ttu-id="792be-162">På fliken **Bekräftad** väljer du ämnet för att öppna ämnessidan.</span><span class="sxs-lookup"><span data-stu-id="792be-162">On the **Confirmed** tab, select the topic to open the topic page.</span></span>

2. <span data-ttu-id="792be-163">På ämnessidan granskar du ämnessidan och väljer **Redigera** om du behöver göra ändringar på sidan.</span><span class="sxs-lookup"><span data-stu-id="792be-163">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="792be-164">Observera att du fortfarande kan välja att avvisa ett bekräftat avsnitt.</span><span class="sxs-lookup"><span data-stu-id="792be-164">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="792be-165">Det gör du genom att gå  till det valda avsnittet på fliken Bekräftad och välja **x** om du vill avvisa ämnet.</span><span class="sxs-lookup"><span data-stu-id="792be-165">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="792be-166">Publicerade ämnen</span><span class="sxs-lookup"><span data-stu-id="792be-166">Published topics</span></span>

<span data-ttu-id="792be-167">Publicerade ämnen har redigerats så att specifik information alltid visas för dem som stöter på sidan.</span><span class="sxs-lookup"><span data-stu-id="792be-167">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="792be-168">Här listas även manuellt skapade ämnen.</span><span class="sxs-lookup"><span data-stu-id="792be-168">Manually created topics are listed here as well.</span></span>

   ![Hantera ämnen](../media/knowledge-management/manage-topics-new.png)
