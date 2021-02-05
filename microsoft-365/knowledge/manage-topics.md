---
title: Hantera ämnen i Ämnescenter i Microsoft Viva-ämnen
description: Så här hanterar du ämnen i Ämnescenter.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 45e8f26823998278f9a332d2ea1e362b77f2032b
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107200"
---
# <a name="manage-topics-in-the-topic-center"></a><span data-ttu-id="83adb-103">Hantera ämnen i Ämnescenter</span><span class="sxs-lookup"><span data-stu-id="83adb-103">Manage topics in the Topic center</span></span> 

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="83adb-104">I Ämnescenter för Viva kan en  knowledge manager visa sidan Hantera ämnen för att granska ämnen som har identifierats på SharePoint-källplatserna enligt givna av din kunskapsadministratör.</span><span class="sxs-lookup"><span data-stu-id="83adb-104">In the Viva Topics Topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![Ämnescenter](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="83adb-106">Knowledge Managers help to guide discovered topics through the topic lifecycle in which topics are:</span><span class="sxs-lookup"><span data-stu-id="83adb-106">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="83adb-107">Förslag: Ett ämne har identifierats av AI och har tillräckligt med stödresurser, anslutningar och egenskaper.</span><span class="sxs-lookup"><span data-stu-id="83adb-107">Suggested: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span>
- <span data-ttu-id="83adb-108">Bekräftad: Ett ämne som har föreslagits av AI har validerats.</span><span class="sxs-lookup"><span data-stu-id="83adb-108">Confirmed: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="83adb-109">Validering utförs genom bekräftelse från en kunskapshanterare.</span><span class="sxs-lookup"><span data-stu-id="83adb-109">Validation is done by confirmation from a knowledge manager.</span></span> <span data-ttu-id="83adb-110">Dessutom kan ett ämne bekräftas om minst två användare ger positiv feedback via feedbackfrågan på ämneskortet.</span><span class="sxs-lookup"><span data-stu-id="83adb-110">Additionally, a topic can be confirmed if at least two users give positive feedback through the feedback question on the topic card.</span></span>
- <span data-ttu-id="83adb-111">Publicerades: Ett bekräftat ämne som har gått ut: manuella redigeringar har gjorts för att förbättra kvaliteten.</span><span class="sxs-lookup"><span data-stu-id="83adb-111">Published: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>
- <span data-ttu-id="83adb-112">Borttaget: Ett ämne avvisas av en kunskapshanterare och visas inte längre för användare.</span><span class="sxs-lookup"><span data-stu-id="83adb-112">Removed: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="83adb-113">Ämnet kan vara i val annat läge när det tas bort (förslag, bekräftar eller publiceras).</span><span class="sxs-lookup"><span data-stu-id="83adb-113">The topic can be in any state when it is removed (suggested, confirmed or published).</span></span> <span data-ttu-id="83adb-114">När ett publicerat ämne tas bort måste sidan med den detaljerade informationen tas bort manuellt via ämnescentrets sidbibliotek.</span><span class="sxs-lookup"><span data-stu-id="83adb-114">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

   ![Livscykeldiagram för ämne](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> <span data-ttu-id="83adb-116">På sidan Hantera ämnen kan varje kunskapshanterare bara se ämnen där de har åtkomst till filer och sidor i ämnet.</span><span class="sxs-lookup"><span data-stu-id="83adb-116">In the Manage Topics page, each knowledge manager will only be able to see topics where they have access to the files and pages of the topic.</span></span> <span data-ttu-id="83adb-117">Det kommer att återspeglas i avsnitten som visas under flikarna Föreslagna, Bekräftade, Borttaget och Publicerade.</span><span class="sxs-lookup"><span data-stu-id="83adb-117">This will be reflected in the topics that are listed under the Suggested, Confirmed, Removed, and Published tabs.</span></span> <span data-ttu-id="83adb-118">I avsnittet antal visas dock det totala antalet i organisationen.</span><span class="sxs-lookup"><span data-stu-id="83adb-118">The topic counts, however, show the total counts in the organization.</span></span>

## <a name="requirements"></a><span data-ttu-id="83adb-119">Krav</span><span class="sxs-lookup"><span data-stu-id="83adb-119">Requirements</span></span>

<span data-ttu-id="83adb-120">Om du vill hantera ämnen i ämnescentret måste du:</span><span class="sxs-lookup"><span data-stu-id="83adb-120">To manage topics in the Topic center, you need to:</span></span>
- <span data-ttu-id="83adb-121">Ha en Viva Topics-licens.</span><span class="sxs-lookup"><span data-stu-id="83adb-121">Have a Viva Topics license.</span></span>

- <span data-ttu-id="83adb-122">Ha [**behörigheten Vem som kan hantera**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions) ämnen.</span><span class="sxs-lookup"><span data-stu-id="83adb-122">Have the [**Who can manage topics**](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-user-permissions) permission.</span></span> <span data-ttu-id="83adb-123">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span><span class="sxs-lookup"><span data-stu-id="83adb-123">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="83adb-124">Du kan inte visa sidan Hantera ämnen i Ämnescenter om du inte har behörigheten Vem **kan hantera** ämnen.</span><span class="sxs-lookup"><span data-stu-id="83adb-124">You will not be able to view the Manage Topics page in the Topic Center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="83adb-125">I ämnescentret kan en knowledge manager granska ämnen som har identifierats i de SharePoint-källplatser du angett och kan antingen bekräfta eller avvisa dem.</span><span class="sxs-lookup"><span data-stu-id="83adb-125">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="83adb-126">En kunskapshanterare kan också skapa och publicera nya ämnessidor om det inte finns någon som finns med i identifieringen av ämnen, eller redigera befintliga sidor om de behöver uppdateras.</span><span class="sxs-lookup"><span data-stu-id="83adb-126">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="83adb-127">Granska föreslagna ämnen</span><span class="sxs-lookup"><span data-stu-id="83adb-127">Review suggested topics</span></span>

<span data-ttu-id="83adb-128">På sidan Ämnescenter Hantera ämnen visas ämnen som identifierats på dina angivna SharePoint-källplatser på **fliken Förslag.** Vid behov kan en kunskapshanterare granska ämnen som inte har bekräftats och välja att bekräfta eller avvisa dem.</span><span class="sxs-lookup"><span data-stu-id="83adb-128">On the Topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

   ![Föreslagna ämnen](../media/knowledge-management/quality-score.png) </br> 

<span data-ttu-id="83adb-130">Så här granskar du ett ämne som föreslås:</span><span class="sxs-lookup"><span data-stu-id="83adb-130">To review a suggested topic:</span></span>

1. <span data-ttu-id="83adb-131">På sidan **Hantera ämnen** väljer du **fliken Förslag** och väljer sedan ämnet för att öppna ämnessidan.</span><span class="sxs-lookup"><span data-stu-id="83adb-131">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="83adb-132">På ämnessidan granskar du ämnessidan och väljer **Redigera** om du behöver göra några ändringar på sidan.</span><span class="sxs-lookup"><span data-stu-id="83adb-132">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="83adb-133">Om du publicerar några ändringar flyttas det här avsnittet till **fliken Publicerad.**</span><span class="sxs-lookup"><span data-stu-id="83adb-133">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="83adb-134">När du har granskat ämnet går du tillbaka till sidan Hantera ämnen.</span><span class="sxs-lookup"><span data-stu-id="83adb-134">After reviewing the topic, go back to the Manage topics page.</span></span> <span data-ttu-id="83adb-135">För det valda avsnittet kan du:</span><span class="sxs-lookup"><span data-stu-id="83adb-135">For the selected topic, you can:</span></span>

   - <span data-ttu-id="83adb-136">Markera bockmarkeringen för att bekräfta ämnet.</span><span class="sxs-lookup"><span data-stu-id="83adb-136">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="83adb-137">Markera **x om** du vill avvisa ämnet.</span><span class="sxs-lookup"><span data-stu-id="83adb-137">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="83adb-138">Bekräftade ämnen tas bort från listan **förslag** och visas nu i **den bekräftade** listan.</span><span class="sxs-lookup"><span data-stu-id="83adb-138">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="83adb-139">Avvisade ämnen tas bort från listan **förslag och** visas nu på fliken **Borttaget.**</span><span class="sxs-lookup"><span data-stu-id="83adb-139">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

### <a name="quality-score"></a><span data-ttu-id="83adb-140">Kvalitetsresultat</span><span class="sxs-lookup"><span data-stu-id="83adb-140">Quality score</span></span>

<span data-ttu-id="83adb-141">Varje ämne som visas på sidan Föreslagna ämnen har <b>tilldelats ett</b> kvalitetsresultat.</span><span class="sxs-lookup"><span data-stu-id="83adb-141">Each topic that appears in your Suggested Topics page has a <b>Quality</b> score assigned to it.</span></span> <span data-ttu-id="83adb-142">Kvalitetsresultatet är en reflektion av mängden information som en genomsnittlig användare ser för information om ämnet, med tanke på att varje användare kan se mer eller mindre information på grund av de behörigheter som de kanske inte har för information i ett ämne.</span><span class="sxs-lookup"><span data-stu-id="83adb-142">The Quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user may see more or less information because of the permissions they may or may not have on the information in a topic.</span></span> 

<span data-ttu-id="83adb-143">Kvalitetsresultatet kan bidra till att ge insyn i de ämnen som innehåller mest information och kan vara användbart för att hitta ämnen som kan behöva redigeras manuellt.</span><span class="sxs-lookup"><span data-stu-id="83adb-143">The Quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span>  <span data-ttu-id="83adb-144">Ett ämne med lägre kvalitet kan till exempel vara resultatet av att vissa användare inte har SharePoint-behörigheter till relevanta filer eller webbplatser som AI har tagit med i ämnet.</span><span class="sxs-lookup"><span data-stu-id="83adb-144">For example, a topic with a lower quality score may be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="83adb-145">En deltagare kan sedan redigera ämnet så att det innehåller information (vid behov), som sedan visas för alla användare som kan visa ämnet.</span><span class="sxs-lookup"><span data-stu-id="83adb-145">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

<span data-ttu-id="83adb-146">Kvalitetsresultatet kan variera mellan 1 och 100.</span><span class="sxs-lookup"><span data-stu-id="83adb-146">The Quality score could range from 1 to 100.</span></span> <span data-ttu-id="83adb-147">Ett nyligen upptäckt ämne får ett kvalitetsresultat på 0 tills två eller fler användare har visat det.</span><span class="sxs-lookup"><span data-stu-id="83adb-147">A newly discovered topic will have a quality score of 0 until two or more users have viewed it.</span></span> <span data-ttu-id="83adb-148">Varje användares kvalitetsresultat bestäms av ett antal faktorer, till exempel mängden innehåll som visas för en viss användare, som kontrolleras användarens behörigheter eftersom varje ämnessida har säkerhets trimning för AI-genererat innehåll.</span><span class="sxs-lookup"><span data-stu-id="83adb-148">Each users quality score is determined by a number of factors, such as the amount of content displayed for the specific user, which is controlled the user's permissions as each topic page has security trimming in place for AI-generated content.</span></span> <span data-ttu-id="83adb-149">Kvalitetsresultatet som visas på fliken Föreslagna ämnen är ett genomsnitt för varje användares enskilda poäng.</span><span class="sxs-lookup"><span data-stu-id="83adb-149">The Quality score shown on the Suggested topics tab is an average of each users individual score.</span></span>

### <a name="impressions"></a><span data-ttu-id="83adb-150">Intryck</span><span class="sxs-lookup"><span data-stu-id="83adb-150">Impressions</span></span>

<span data-ttu-id="83adb-151">I kolumnen Intryck visas hur många gånger ett ämne har <b>visats</b> för slutanvändare.</span><span class="sxs-lookup"><span data-stu-id="83adb-151">The <b>Impressions</b> column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="83adb-152">Det omfattar vyer via ämneskort i sökningar, genom viktiga ämnen och genom vyer i Ämnescenter.</span><span class="sxs-lookup"><span data-stu-id="83adb-152">This includes views through topic cards in search, through topic highlights, and through Topic center views.</span></span> <span data-ttu-id="83adb-153">Det speglar inte genomklickning för dessa ämnen, men det ämnet har visats.</span><span class="sxs-lookup"><span data-stu-id="83adb-153">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="83adb-154">Kolumnen Intryck visas för ämnen på flikarna Föreslagna, Bekräftade, Publicerade och Borttaget på sidan Hantera ämnen.</span><span class="sxs-lookup"><span data-stu-id="83adb-154">The Impressions column will show for topics in the Suggested, Confirmed, Published, and Removed tabs in the Manage Topics page.</span></span>


## <a name="confirmed-topics"></a><span data-ttu-id="83adb-155">Bekräftade ämnen</span><span class="sxs-lookup"><span data-stu-id="83adb-155">Confirmed topics</span></span>

<span data-ttu-id="83adb-156">På sidan Hantera ämnen visas ämnen som identifierats på dina angivna SharePoint-källplatser och har bekräftats av en knowledge manager eller "crowd-sourced" som bekräftats av två eller flera personer via feedbackmekanismen för kortet på fliken Bekräftad.  Om det behövs kan en användare med behörighet att hantera ämnen granska bekräftade ämnen och välja att avvisa dem.</span><span class="sxs-lookup"><span data-stu-id="83adb-156">On the Manage topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowd-sourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="83adb-157">Så här granskar du ett bekräftat ämne:</span><span class="sxs-lookup"><span data-stu-id="83adb-157">To review a confirmed topic:</span></span>

1. <span data-ttu-id="83adb-158">På fliken **Bekräftad** väljer du avsnittet för att öppna ämnessidan.</span><span class="sxs-lookup"><span data-stu-id="83adb-158">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="83adb-159">På ämnessidan granskar du ämnessidan och väljer **Redigera** om du behöver göra några ändringar på sidan.</span><span class="sxs-lookup"><span data-stu-id="83adb-159">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="83adb-160">Observera att du fortfarande kan välja att avvisa ett bekräftat ämne.</span><span class="sxs-lookup"><span data-stu-id="83adb-160">Note that you can still chose to reject a confirmed topic.</span></span>  <span data-ttu-id="83adb-161">Det gör du genom att gå till det valda avsnittet i listan Bekräftad och välja **x** om du vill avvisa ämnet.</span><span class="sxs-lookup"><span data-stu-id="83adb-161">To do this, go to the selected topic in the Confirmed list, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="83adb-162">Publicerade ämnen</span><span class="sxs-lookup"><span data-stu-id="83adb-162">Published topics</span></span>
<span data-ttu-id="83adb-163">Publicerade ämnen har redigerats så att specifik information alltid visas för dem som stöter på sidan.</span><span class="sxs-lookup"><span data-stu-id="83adb-163">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="83adb-164">Här listas även manuellt skapade ämnen.</span><span class="sxs-lookup"><span data-stu-id="83adb-164">Manually created topics are listed here as well.</span></span>

   ![Hantera ämnen](../media/knowledge-management/manage-topics-new.png) </br> 




