---
title: Hantera ämnen i ämnescentret i Microsoft Viva-ämnen
description: Så här hanterar du ämnen i Ämnescenter.
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: e2cbf62339e2ade240474fed9db86e68dc0b3bb4
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760128"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a><span data-ttu-id="f0f58-103">Hantera ämnen i ämnescentret i Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="f0f58-103">Manage topics in the topic center in Microsoft Viva Topics</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>


<span data-ttu-id="f0f58-104">I ämnescentret viva ämnen kan en  knowledge manager visa sidan Hantera ämnen för att granska ämnen som har identifierats i SharePoint-källplatser som angetts av din kunskapsadministratör.</span><span class="sxs-lookup"><span data-stu-id="f0f58-104">In the Viva Topics topic center, a knowledge manager can view the **Manage topics** page to review topics that have been identified in SharePoint source locations as specified by your knowledge admin.</span></span>  

   ![Ämnescenter](../media/knowledge-management/topic-center.png) </br> 



<span data-ttu-id="f0f58-106">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span><span class="sxs-lookup"><span data-stu-id="f0f58-106">Knowledge managers help to guide discovered topics through the topic lifecycle in which topics are:</span></span>

- <span data-ttu-id="f0f58-107">**Förslag:** Ett ämne har identifierats med AI och har tillräckligt med stödresurser, anslutningar och egenskaper.</span><span class="sxs-lookup"><span data-stu-id="f0f58-107">**Suggested**: A topic has been identified by AI and has enough supporting resources, connections, and properties.</span></span>
- <span data-ttu-id="f0f58-108">**Bekräftad**: Ett ämne som har föreslagits av AI valideras.</span><span class="sxs-lookup"><span data-stu-id="f0f58-108">**Confirmed**: A topic that has been suggested by AI is validated.</span></span> <span data-ttu-id="f0f58-109">Valideringen utförs genom att en knowledge manager bekräftar detta.</span><span class="sxs-lookup"><span data-stu-id="f0f58-109">Validation is done by confirmation from a knowledge manager.</span></span> <span data-ttu-id="f0f58-110">Ett ämne kan också bekräftas om minst två användare ger positiv feedback via feedbackfrågan på ämneskortet.</span><span class="sxs-lookup"><span data-stu-id="f0f58-110">Additionally, a topic can be confirmed if at least two users give positive feedback through the feedback question on the topic card.</span></span>
- <span data-ttu-id="f0f58-111">**Publicerades**: Ett bekräftat ämne som har redigerats: manuell redigering har gjorts för att förbättra kvaliteten.</span><span class="sxs-lookup"><span data-stu-id="f0f58-111">**Published**: A confirmed topic that has been curated: manual edits have been made to improve its quality.</span></span>
- <span data-ttu-id="f0f58-112">**Tas** bort : Ett ämne avvisas av en kunskapshanterare och visas inte längre för tittare.</span><span class="sxs-lookup"><span data-stu-id="f0f58-112">**Removed**: A topic is rejected by a knowledge manager and will no longer be visible to viewers.</span></span> <span data-ttu-id="f0f58-113">Avsnittet kan vara i valgivet läge när det tas bort (förslag, bekräftar eller publiceras).</span><span class="sxs-lookup"><span data-stu-id="f0f58-113">The topic can be in any state when it is removed (suggested, confirmed, or published).</span></span> <span data-ttu-id="f0f58-114">När ett publicerat ämne tas bort måste sidan med den curated informationen tas bort manuellt via ämnescentrets sidbibliotek.</span><span class="sxs-lookup"><span data-stu-id="f0f58-114">When a published topic is removed, the page with the curated details will need to be deleted manually through the Pages Library of the topic center.</span></span>

   ![Diagram för livscykel för ämnen](../media/knowledge-management/topic-lifecycle.png) </br> 

> [!Note] 
> <span data-ttu-id="f0f58-116">På sidan Hantera ämnen kan varje kunskapshanterare bara se ämnen där de har åtkomst till filerna och sidorna i ämnet.</span><span class="sxs-lookup"><span data-stu-id="f0f58-116">On the Manage Topics page, each knowledge manager will only be able to see topics where they have access to the files and pages of the topic.</span></span> <span data-ttu-id="f0f58-117">Det kommer att återspeglas i avsnitten som visas under flikarna **Föreslagna**, **Bekräftade,** **Borttagna** **och Publicerade.**</span><span class="sxs-lookup"><span data-stu-id="f0f58-117">This will be reflected in the topics that are listed under the **Suggested**, **Confirmed**, **Removed**, and **Published** tabs.</span></span> <span data-ttu-id="f0f58-118">I avsnittet antal visas dock det totala antalet i organisationen.</span><span class="sxs-lookup"><span data-stu-id="f0f58-118">The topic counts, however, show the total counts in the organization.</span></span>

## <a name="requirements"></a><span data-ttu-id="f0f58-119">Krav</span><span class="sxs-lookup"><span data-stu-id="f0f58-119">Requirements</span></span>

<span data-ttu-id="f0f58-120">Om du vill hantera ämnen i ämnescentret måste du:</span><span class="sxs-lookup"><span data-stu-id="f0f58-120">To manage topics in the topic center, you need to:</span></span>
- <span data-ttu-id="f0f58-121">Ha en Viva Topics-licens.</span><span class="sxs-lookup"><span data-stu-id="f0f58-121">Have a Viva Topics license.</span></span>

- <span data-ttu-id="f0f58-122">Ha [**behörigheten Vem kan hantera**](./topic-experiences-user-permissions.md) ämnen.</span><span class="sxs-lookup"><span data-stu-id="f0f58-122">Have the [**Who can manage topics**](./topic-experiences-user-permissions.md) permission.</span></span> <span data-ttu-id="f0f58-123">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span><span class="sxs-lookup"><span data-stu-id="f0f58-123">Knowledge admins can give users this permission in the Viva Topics topic permissions settings.</span></span> 

<span data-ttu-id="f0f58-124">Du kan inte visa sidan Hantera ämnen i ämnescentret om du inte har behörigheten Vem **kan hantera** ämnen.</span><span class="sxs-lookup"><span data-stu-id="f0f58-124">You will not be able to view the Manage Topics page in the topic center unless you have the **Who can manage topics** permission.</span></span>

<span data-ttu-id="f0f58-125">I ämnescentret kan en knowledge manager granska ämnen som har identifierats på de SharePoint-källplatser du angett och antingen bekräfta eller avvisa dem.</span><span class="sxs-lookup"><span data-stu-id="f0f58-125">In the topic center, a knowledge manager can review topics that have been identified in the SharePoint source locations you specified, and can either confirm or reject them.</span></span> <span data-ttu-id="f0f58-126">En knowledge manager kan också skapa och publicera nya ämnessidor om en inte hittades i identifieringen av ämnen, eller redigera befintliga sidor om de behöver uppdateras.</span><span class="sxs-lookup"><span data-stu-id="f0f58-126">A knowledge manager can also create and publish new topic pages if one was not found in topic discovery, or edit existing ones if they need to be updated.</span></span>


## <a name="review-suggested-topics"></a><span data-ttu-id="f0f58-127">Granska föreslagna ämnen</span><span class="sxs-lookup"><span data-stu-id="f0f58-127">Review suggested topics</span></span>

<span data-ttu-id="f0f58-128">På sidan Ämnescenter Hantera ämnen visas ämnen som identifierats på dina angivna platser för SharePoint-källor på **fliken Förslag.** Vid behov kan en kunskapshanterare granska ämnen som inte har bekräftats och välja att bekräfta eller avvisa dem.</span><span class="sxs-lookup"><span data-stu-id="f0f58-128">On the topic center Manage Topics page, topics that were discovered in your specified SharePoint source locations will be listed in the **Suggested** tab. If needed, a knowledge manager can review unconfirmed topics and choose to confirm or reject them.</span></span>

   ![Föreslagna ämnen](../media/knowledge-management/quality-score.png) </br> 

<span data-ttu-id="f0f58-130">Så här granskar du ett föreslaget ämne:</span><span class="sxs-lookup"><span data-stu-id="f0f58-130">To review a suggested topic:</span></span>

1. <span data-ttu-id="f0f58-131">På sidan **Hantera ämnen** väljer du **fliken Förslag** och väljer ämnet för att öppna ämnessidan.</span><span class="sxs-lookup"><span data-stu-id="f0f58-131">On the **Manage topics** page, select the **Suggested** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="f0f58-132">På ämnessidan granskar du ämnessidan och väljer **Redigera** om du behöver göra ändringar på sidan.</span><span class="sxs-lookup"><span data-stu-id="f0f58-132">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span> <span data-ttu-id="f0f58-133">När du publicerar eventuella ändringar flyttas det här avsnittet till **fliken Publicerade.**</span><span class="sxs-lookup"><span data-stu-id="f0f58-133">Publishing any edits will move this topic to the **Published** tab.</span></span>

3. <span data-ttu-id="f0f58-134">När du har granskat ämnet går du tillbaka till sidan Hantera ämnen.</span><span class="sxs-lookup"><span data-stu-id="f0f58-134">After reviewing the topic, go back to the Manage Topics page.</span></span> <span data-ttu-id="f0f58-135">För det valda avsnittet kan du:</span><span class="sxs-lookup"><span data-stu-id="f0f58-135">For the selected topic, you can:</span></span>

   - <span data-ttu-id="f0f58-136">Välj bockmarkeringen för att bekräfta ämnet.</span><span class="sxs-lookup"><span data-stu-id="f0f58-136">Select the check mark to confirm the topic.</span></span>
    
   - <span data-ttu-id="f0f58-137">Markera **x om** du vill avvisa ämnet.</span><span class="sxs-lookup"><span data-stu-id="f0f58-137">Select the **x** if you want to reject the topic.</span></span>

    <span data-ttu-id="f0f58-138">Bekräftade ämnen tas bort från listan **Förslag** och visas nu i **den bekräftade** listan.</span><span class="sxs-lookup"><span data-stu-id="f0f58-138">Confirmed topics will be removed from the **Suggested** list and will now display in the **Confirmed** list.</span></span>

    <span data-ttu-id="f0f58-139">Avvisade ämnen tas bort från listan **Förslag** och visas nu på fliken **Borttaget.**</span><span class="sxs-lookup"><span data-stu-id="f0f58-139">Rejected topics will be removed from the **Suggested** list and will now display in the **Removed** tab.</span></span>

   </br> 

### <a name="quality-score"></a><span data-ttu-id="f0f58-140">Kvalitetsresultat</span><span class="sxs-lookup"><span data-stu-id="f0f58-140">Quality score</span></span>

<span data-ttu-id="f0f58-141">Varje ämne som visas på sidan Föreslagna ämnen har tilldelats ett kvalitetsresultat.</span><span class="sxs-lookup"><span data-stu-id="f0f58-141">Each topic that appears on your Suggested Topics page has a quality score assigned to it.</span></span> <span data-ttu-id="f0f58-142">Kvalitetsresultatet är en reflektion av mängden information som medelvärdet ser för information om ämnet, med tanke på att varje användare kan se mer eller mindre information på grund av de behörigheter som de kan ha eller kanske inte har på informationen i ett ämne.</span><span class="sxs-lookup"><span data-stu-id="f0f58-142">The quality score is a reflection of the amount of information that the average user will see for the information on the topic, keeping in mind that each user might see more or less information because of the permissions they might or might not have on the information in a topic.</span></span> 

<span data-ttu-id="f0f58-143">Kvalitetsresultatet kan bidra till att ge insyn i de ämnen som innehåller mest information och kan vara användbart för att hitta ämnen som kan behöva redigeras manuellt.</span><span class="sxs-lookup"><span data-stu-id="f0f58-143">The quality score can help give insight to the topics with the most information and can be useful for finding topics that may need to be manually edited.</span></span> <span data-ttu-id="f0f58-144">Ett ämne med lägre kvalitet kan till exempel vara ett resultat av att vissa användare inte har SharePoint-behörigheter till relevanta filer eller webbplatser som AI har inkluderat i ämnet.</span><span class="sxs-lookup"><span data-stu-id="f0f58-144">For example, a topic with a lower quality score might be the result of some users not having SharePoint permissions to pertinent files or sites that AI has included in the topic.</span></span> <span data-ttu-id="f0f58-145">En deltagare kan sedan redigera ämnet så att det innehåller informationen (vid behov), som sedan kan visas för alla användare som kan visa ämnet.</span><span class="sxs-lookup"><span data-stu-id="f0f58-145">A contributor could then edit the topic to include the information (when appropriate), which will then be viewable to all users who can view the topic.</span></span>

<span data-ttu-id="f0f58-146">Kvalitetsresultatet kan variera mellan 1 och 100.</span><span class="sxs-lookup"><span data-stu-id="f0f58-146">The quality score could range from 1 to 100.</span></span> <span data-ttu-id="f0f58-147">Ett nyligen upptäckt ämne får ett kvalitetsresultat på 0 tills två eller fler användare har visat det.</span><span class="sxs-lookup"><span data-stu-id="f0f58-147">A newly discovered topic will have a quality score of 0 until two or more users have viewed it.</span></span> <span data-ttu-id="f0f58-148">Varje användares kvalitetsresultat bestäms av ett antal faktorer, till exempel mängden innehåll som visas för den specifika användaren, som styrs av användarens behörigheter eftersom varje ämnessida har säkerhets trimning för AI-genererat innehåll.</span><span class="sxs-lookup"><span data-stu-id="f0f58-148">Each user's quality score is determined by a number of factors, such as the amount of content displayed for the specific user, which is controlled the user's permissions as each topic page has security trimming in place for AI-generated content.</span></span> <span data-ttu-id="f0f58-149">Kvalitetsresultatet som visas på fliken **Föreslagna** ämnen är det genomsnittliga resultatet för varje användares poäng.</span><span class="sxs-lookup"><span data-stu-id="f0f58-149">The quality score shown on the **Suggested** topics tab is an average of each users individual score.</span></span>

### <a name="impressions"></a><span data-ttu-id="f0f58-150">Intryck</span><span class="sxs-lookup"><span data-stu-id="f0f58-150">Impressions</span></span>

<span data-ttu-id="f0f58-151">I kolumnen Intryck visas hur många gånger ett ämne har **visats** för slutanvändarna.</span><span class="sxs-lookup"><span data-stu-id="f0f58-151">The **Impressions** column displays the number of times a topic has been shown to end users.</span></span> <span data-ttu-id="f0f58-152">Det omfattar vyer via ämneskort i sökning, genom viktiga ämnen och genom vyer i ämnescenter.</span><span class="sxs-lookup"><span data-stu-id="f0f58-152">This includes views through topic cards in search, through topic highlights, and through topic center views.</span></span> <span data-ttu-id="f0f58-153">Den återspeglar inte genomklickning på dessa ämnen, men att ämnet har visats.</span><span class="sxs-lookup"><span data-stu-id="f0f58-153">It does not reflect the click-through on these topics, but that the topic has been displayed.</span></span> <span data-ttu-id="f0f58-154">Kolumnen **Intryck visas** för ämnen på flikarna **Föreslagna**, **Bekräftade,** **Publicerade** och **Borttagna** på sidan Hantera ämnen.</span><span class="sxs-lookup"><span data-stu-id="f0f58-154">The **Impressions** column will show for topics in the **Suggested**, **Confirmed**, **Published**, and **Removed** tabs on the Manage Topics page.</span></span>

## <a name="confirmed-topics"></a><span data-ttu-id="f0f58-155">Bekräftade ämnen</span><span class="sxs-lookup"><span data-stu-id="f0f58-155">Confirmed topics</span></span>

<span data-ttu-id="f0f58-156">På sidan Hantera ämnen visas ämnen som identifierats på dina angivna platser för SharePoint-källor och har bekräftats av en knowledge manager eller "crowdsourced" som bekräftats av två eller fler personer via feedbackmekanismen för kortet på fliken Bekräftad.  Om det behövs kan en användare med behörighet att hantera ämnen granska bekräftade ämnen och välja att avvisa dem.</span><span class="sxs-lookup"><span data-stu-id="f0f58-156">On the Manage Topics page, topics that were discovered in your specified SharePoint source locations and have been confirmed by a knowledge manager or "crowdsourced" confirmed by two or more people through the card feedback mechanism will be listed in the **Confirmed** tab. If needed, a user with permissions to manage topics can review confirmed topics and choose to reject them.</span></span>

<span data-ttu-id="f0f58-157">Granska ett bekräftat ämne:</span><span class="sxs-lookup"><span data-stu-id="f0f58-157">To review a confirmed topic:</span></span>

1. <span data-ttu-id="f0f58-158">På fliken **Bekräftad** väljer du ämnet för att öppna ämnessidan.</span><span class="sxs-lookup"><span data-stu-id="f0f58-158">On the **Confirmed** tab, select the topic to open the topic page.</span></span></br>

2. <span data-ttu-id="f0f58-159">På ämnessidan granskar du ämnessidan och väljer **Redigera** om du behöver göra ändringar på sidan.</span><span class="sxs-lookup"><span data-stu-id="f0f58-159">On the topic page, review the topic page, and select **Edit** if you need to make any changes to the page.</span></span>

<span data-ttu-id="f0f58-160">Observera att du fortfarande kan välja att avvisa ett bekräftat avsnitt.</span><span class="sxs-lookup"><span data-stu-id="f0f58-160">Note that you can still choose to reject a confirmed topic.</span></span> <span data-ttu-id="f0f58-161">Det gör du genom att gå  till det valda avsnittet på fliken Bekräftad och välja **x** om du vill avvisa ämnet.</span><span class="sxs-lookup"><span data-stu-id="f0f58-161">To do this, go to the selected topic on the **Confirmed** tab, and select the **x** if you want to reject the topic.</span></span>

## <a name="published-topics"></a><span data-ttu-id="f0f58-162">Publicerade ämnen</span><span class="sxs-lookup"><span data-stu-id="f0f58-162">Published topics</span></span>
<span data-ttu-id="f0f58-163">Publicerade ämnen har redigerats så att specifik information alltid visas för dem som stöter på sidan.</span><span class="sxs-lookup"><span data-stu-id="f0f58-163">Published topics have been edited so that specific information will always appear to whoever encounters the page.</span></span> <span data-ttu-id="f0f58-164">Här listas även manuellt skapade ämnen.</span><span class="sxs-lookup"><span data-stu-id="f0f58-164">Manually created topics are listed here as well.</span></span>

   ![Hantera ämnen](../media/knowledge-management/manage-topics-new.png) </br>