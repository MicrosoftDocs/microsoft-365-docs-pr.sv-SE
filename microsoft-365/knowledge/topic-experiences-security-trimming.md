---
title: Säkerhets trimning för Microsoft Viva Topics
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: None
description: Översikt över hur säkerhet används för att visa ämnen.
ms.openlocfilehash: 12a2ad34c55cd63468266abca1fa053048053dd2
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279338"
---
# <a name="microsoft-viva-topics-security-trimming"></a><span data-ttu-id="6f1b0-103">Säkerhets trimning för Microsoft Viva Topics</span><span class="sxs-lookup"><span data-stu-id="6f1b0-103">Microsoft Viva Topics security trimming</span></span> 

<span data-ttu-id="6f1b0-104">Viva Topics-användare kan inte visa information i ämnen som deras befintliga Office 365-behörigheter hindrar dem från att se.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-104">Viva Topics users can't view information in topics that their existing Office 365 permissions prevent them from seeing.</span></span> <span data-ttu-id="6f1b0-105">Allt som en användare ser på en ämnessida (till exempel SharePoint-webbplatser, dokument och filer) blir information som användaren redan har tillåtelse att se.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-105">Everything a user sees on a topic page (for example, SharePoint sites, documents, files) will be information they are already allowed to see.</span></span> <span data-ttu-id="6f1b0-106">Viva Topics gör inga ändringar av befintliga behörigheter.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-106">Viva Topics does not make changes to any existing permissions.</span></span>

## <a name="why-two-users-may-have-different-views-of-the-same-topic"></a><span data-ttu-id="6f1b0-107">Varför två användare kan ha olika vyer av samma ämne</span><span class="sxs-lookup"><span data-stu-id="6f1b0-107">Why two users may have different views of the same topic</span></span>

<span data-ttu-id="6f1b0-108">När ett ämne skapas med AI eller manuell läroplan kan det innehålla en beskrivning av ämnet, alternativa namn, personer kopplade till ämnet samt webbplatser, sidor och filer relaterade till ämnet.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-108">When a topic is created through AI or manual curation, it can contain a description of the topic, alternative names, people associated with the topic, as well as sites, pages, and files related to the topic.</span></span> <span data-ttu-id="6f1b0-109">När den här informationen visas på en ämnessida är det möjligt att två användare som visar samma ämne min inte ser samma information.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-109">When this information is viewed on a topic page, it is possible that two users who are viewing the same topic my not see the same information.</span></span>
  
<span data-ttu-id="6f1b0-110">När användare 1 till exempel visar ämnessidan för Neptune kan de se den här vyn av ämnessidan.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-110">For example, when User 1 views the Neptune topic page, they might see this view of the topic page.</span></span>

![Neptune-ämne för användare 1](../media/knowledge-management/user2-topic-view.png) </br> 

<span data-ttu-id="6f1b0-112">Men när Användare 2 tittar på samma ämnessida för Neptune skiljer sig deras vy från Användare 1.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-112">However, when User 2 looks at the same Neptune topic page, their view differs from User 1.</span></span>  <span data-ttu-id="6f1b0-113">Användare 2 kan se *FILEN DG-2000 Produktöversikt* i avsnittet Fästa filer och sidor på ämnessidan, som inte visas för Användare 1. </span><span class="sxs-lookup"><span data-stu-id="6f1b0-113">User 2 is able to see the *DG-2000 Product Overview* file in the **Pinned files and pages** section of the topic page, which does not appear for User 1.</span></span> 

![Neptune-ämne för användare 2](../media/knowledge-management/user1-topic-view.png) </br> 

<span data-ttu-id="6f1b0-115">Skillnaden i vad användarna kan se i samma ämne är att användarna kanske inte har Office 365-behörighet att visa en relaterad webbplats eller fil.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-115">The difference in what users may see on the same topic is because users may not have the Office 365 permissions to view a related site or file.</span></span>  <span data-ttu-id="6f1b0-116">Viva Topics respekterar behörigheterna som anges för objekt i ett ämne och kan inte ändra åtkomsten till dem.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-116">Viva Topics respects the permissions that are set on items in a topic, and cannot change access to them.</span></span> <span data-ttu-id="6f1b0-117">I vårt exempel kan användare 1 inte visa *filen DG-2000 Produktöversikt* på ämnessidan för Neptune eftersom Användare 1 inte har Office 365-behörigheter för att visa filen.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-117">In our example, User 1 is not able to view the *DG-2000 Product Overview* file in their topic page for Neptune because User 1 does not have Office 365 permissions to view the file.</span></span>

<span data-ttu-id="6f1b0-118">Om en användare inte kan se tillräckligt med information i ett ämne för att det ska vara användbart, är avsnittet inte tillgängligt för användaren.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-118">If a user is not able to see enough information in a topic for it to be useful, the topic will not be available to the user.</span></span> <span data-ttu-id="6f1b0-119">När det händer kan användaren inte se det markerade avsnittet.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-119">When this happens, the user will not see the highlighted topic.</span></span> <span data-ttu-id="6f1b0-120">En annan användare som har behörighet till mer information i avsnittet för att den ska vara användbar kommer att kunna se ämnet.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-120">A different user who has permissions to more information in the topic for it to be useful, will be able to see the topic.</span></span>


## <a name="topic-permissions-for-knowledge-managers-and-topic-contributors"></a><span data-ttu-id="6f1b0-121">Ämnesbehörigheter för knowledge managers och ämnesdeltagare</span><span class="sxs-lookup"><span data-stu-id="6f1b0-121">Topic permissions for knowledge managers and topic contributors</span></span>

<span data-ttu-id="6f1b0-122">Användare som har tilldelats behörighet att hantera ämnen – knowledge managers – kommer bara att kunna visa information som de har behörighet att se i ämnen.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-122">Users that are assigned permissions to manage topics - knowledge managers - will only be able to view information they have permissions to see within topics.</span></span>

<span data-ttu-id="6f1b0-123">På samma sätt kan användare som har behörighet att skapa och redigera ämnesbehörigheter – ämnesdeltagare – bara visa information som de har behörighet att se i ämnen.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-123">Similarly, users who have create and edit topic permissions - topic contributors - will only be able to view information they have permissions to see within topics.</span></span> 


## <a name="ai-versus-manually-curated-topic-information"></a><span data-ttu-id="6f1b0-124">AI kontra manuellt curated topic information</span><span class="sxs-lookup"><span data-stu-id="6f1b0-124">AI versus manually curated topic information</span></span>

<span data-ttu-id="6f1b0-125">Ämnen kan innehålla information som genereras av AI och information som lagts till eller redigerats av ämnesdeltagare eller kunskapshanterare.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-125">Topics can contain information generated by AI and information added or edited by topic contributors or knowledge managers.</span></span>

 - <span data-ttu-id="6f1b0-126">Information i ett ämne som lagts till av AI visas bara för personer som har åtkomst till källinnehållet.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-126">Information in a topic that was added by AI is only visible to people who have access to the source content.</span></span>
 - <span data-ttu-id="6f1b0-127">Information om ämnen och personer som manuellt har lagts till eller redigerats av en ämnesdeltagare eller knowledge manager är synliga för alla som kan se ämnet.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-127">Topic description and people information that has been manually added or edited by a topic contributor or knowledge manager is visible to everyone who can see the topic.</span></span>
 - <span data-ttu-id="6f1b0-128">Filer, sidor och webbplatser visas bara för användare som har behörighet till källinnehållet, oavsett om de har lagts till manuellt eller lagts till av AI.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-128">Files, pages, and sites are only visible to users who have permissions to the source content, whether manually added or added by AI.</span></span>

<span data-ttu-id="6f1b0-129">I följande tabell beskrivs vad användare – ämnesanvändare, deltagare och kunskapshanterare – kan se i ett visst ämne baserat på deras behörigheter.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-129">The following table describes what users - topic viewers, contributors, and knowledge managers - can see in a given topic based on their permissions.</span></span>

|<span data-ttu-id="6f1b0-130">Ämnesobjekt</span><span class="sxs-lookup"><span data-stu-id="6f1b0-130">Topic item</span></span>|<span data-ttu-id="6f1b0-131">Vad användarna kan se</span><span class="sxs-lookup"><span data-stu-id="6f1b0-131">What users can see</span></span>|
|:---------|:------------------|
|<span data-ttu-id="6f1b0-132">Ämnesnamn</span><span class="sxs-lookup"><span data-stu-id="6f1b0-132">Topic name</span></span>|<span data-ttu-id="6f1b0-133">Användarna kan se ämnesnamnet för alla ämnen i ämnescentret.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-133">Users can see the topic name of all topics in the topic center.</span></span> <span data-ttu-id="6f1b0-134">Vissa ämnen kanske inte visas om de har en låg relevans för användaren.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-134">Some topics may not be visible if they have a low relevancy to the user.</span></span>|
|<span data-ttu-id="6f1b0-135">Ämnesbeskrivning</span><span class="sxs-lookup"><span data-stu-id="6f1b0-135">Topic description</span></span>|<span data-ttu-id="6f1b0-136">AI-genererade beskrivningar visas endast för användare som har behörighet till källinnehållet.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-136">AI-generated descriptions are visible only to users who have permissions to the source content.</span></span> <span data-ttu-id="6f1b0-137">Manuellt angivna eller redigerade beskrivningar visas för alla användare.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-137">Manually entered or edited descriptions are visible to all users.</span></span>|
|<span data-ttu-id="6f1b0-138">Kontakter</span><span class="sxs-lookup"><span data-stu-id="6f1b0-138">People</span></span>|<span data-ttu-id="6f1b0-139">Fästa personer visas för alla användare.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-139">Pinned people are visible to all users.</span></span> <span data-ttu-id="6f1b0-140">Föreslagna personer visas bara för användare som har behörighet till källinnehållet.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-140">Suggested people are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="6f1b0-141">Filer</span><span class="sxs-lookup"><span data-stu-id="6f1b0-141">Files</span></span>|<span data-ttu-id="6f1b0-142">Filer visas bara för användare som har behörighet till källinnehållet.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-142">Files are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="6f1b0-143">Sidor</span><span class="sxs-lookup"><span data-stu-id="6f1b0-143">Pages</span></span>|<span data-ttu-id="6f1b0-144">Sidor visas bara för användare som har behörighet till källinnehållet.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-144">Pages are only visible to users who have permissions to the source content.</span></span>|
|<span data-ttu-id="6f1b0-145">Webbplatser</span><span class="sxs-lookup"><span data-stu-id="6f1b0-145">Sites</span></span>|<span data-ttu-id="6f1b0-146">Webbplatser visas bara för användare som har behörighet till källinnehållet.</span><span class="sxs-lookup"><span data-stu-id="6f1b0-146">Sites are only visible to users who have permissions to the source content.</span></span>|




## <a name="see-also"></a><span data-ttu-id="6f1b0-147">Se även</span><span class="sxs-lookup"><span data-stu-id="6f1b0-147">See also</span></span>

