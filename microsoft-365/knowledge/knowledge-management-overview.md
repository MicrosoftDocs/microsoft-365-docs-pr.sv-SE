---
title: Översikt över kunskapshantering (förhandsgranskning)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Översikt över kunskapshanteringen i Project Cortex.
ms.openlocfilehash: 99b0d0ece9ef8271666b1978db7947f3e3f2a4e8
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540086"
---
# <a name="knowledge-management-0verview-preview"></a><span data-ttu-id="a8580-103">Kunskapshantering 0verview (Förhandsgranska)</span><span class="sxs-lookup"><span data-stu-id="a8580-103">Knowledge management 0verview (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="a8580-104">Innehållet i den här artikeln är för Project Cortex Private Preview.</span><span class="sxs-lookup"><span data-stu-id="a8580-104">The content in this article is for Project Cortex Private Preview.</span></span> [<span data-ttu-id="a8580-105">Läs mer om Project Cortex</span><span class="sxs-lookup"><span data-stu-id="a8580-105">Find out more about Project Cortex</span></span>](https://aka.ms/projectcortex) 

<span data-ttu-id="a8580-106">Kunskapshantering använder Microsoft AI-teknik, Microsoft 365, Delve, Sök och andra komponenter och tjänster för att skapa ett kunskapsnätverk i din Microsoft 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="a8580-106">Knowledge management uses Microsoft AI technology, Microsoft 365, Delve, Search, and other components and services to build a knowledge network in your Microsoft 365 environment.</span></span> 

   ![Flöde av kunskapshantering](../media/content-understanding/knowledge-management-flowchart.png) </br> 

<span data-ttu-id="a8580-108">Målet är att leverera information till användarna i appar som de använder varje dag, till exempel Outlook, Teams och SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a8580-108">It's goal is to deliver information to you users in apps they use everyday, such as Outlook, Teams, and SharePoint.</span></span>

<span data-ttu-id="a8580-109">Användarna ser till exempel okända termer i sina e-postmeddelanden, SharePoint-webbplatser eller i Teams-konversationer som de vill veta mer om.</span><span class="sxs-lookup"><span data-stu-id="a8580-109">For example, users see unfamiliar terms in their emails, SharePoint sites, or in Teams conversations, that they want to know more about.</span></span> <span data-ttu-id="a8580-110">Kunskapshantering använder AI för att automatiskt söka efter och identifiera dessa **ämnen**och sammanställer information om dem, till exempel en kort beskrivning, ämnesexperter i ämnet och webbplatser, filer och sidor som är relaterade till det.</span><span class="sxs-lookup"><span data-stu-id="a8580-110">Knowledge management uses AI to automatically searches for and identifies these **topics**, and compiles information about them, such as a short description, subject matter experts on the topic, and sites, files, and pages that are related to it.</span></span> <span data-ttu-id="a8580-111">Du kan välja att uppdatera ämnesinformationen efter behov.</span><span class="sxs-lookup"><span data-stu-id="a8580-111">You can choose to update the topic information as needed.</span></span> <span data-ttu-id="a8580-112">Du kan sedan göra ämnena tillgängliga för användarna, vilket innebär att texten markeras för varje förekomst av ämnet som visas i appar som Outlook, Teams och SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a8580-112">You can then make the topics available to your users, which means that for every instance of the topic that appears in apps such as Outlook, Teams, and SharePoint, the text will be highlighted.</span></span> <span data-ttu-id="a8580-113">Användare kan välja att välja ämne för att lära sig mer om det genom ämnesinformationen.</span><span class="sxs-lookup"><span data-stu-id="a8580-113">Users can choose to select the topic to learn more about it through the topic details.</span></span>


## <a name="topic-discovery"></a><span data-ttu-id="a8580-114">Upptäckt av ämne</span><span class="sxs-lookup"><span data-stu-id="a8580-114">Topic discovery</span></span>

<span data-ttu-id="a8580-115">Knowledge Management använder Microsoft AI-teknik för att söka efter **ämnen** i din Office 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="a8580-115">Knowledge Management uses Microsoft AI technology to search for **topics** in your Office 365 environment.</span></span>

<span data-ttu-id="a8580-116">Ett ämne är en fras eller term som är organisatoriskt betydelsefull eller viktig.</span><span class="sxs-lookup"><span data-stu-id="a8580-116">A topic is a phrase or term that is organizationally significant or important.</span></span> <span data-ttu-id="a8580-117">Den har en specifik betydelse för organisationen, och har resurser relaterade till den som kan hjälpa människor att förstå vad det är och hitta mer information om det.</span><span class="sxs-lookup"><span data-stu-id="a8580-117">It has a specific meaning to the organization, and has resources related to it that can help people understand what it is and find more information about it.</span></span>

<span data-ttu-id="a8580-118">När ett ämne upptäcks skapas en **ämnessida** som innehåller information som har samlats in genom ämnesidentifiering, till exempel:</span><span class="sxs-lookup"><span data-stu-id="a8580-118">When a topic is discovered, a **topic page** is created for it that contains information that was gathered through topic discovery, such as:</span></span>

- <span data-ttu-id="a8580-119">En kort beskrivning av ämnet.</span><span class="sxs-lookup"><span data-stu-id="a8580-119">A short description of the topic.</span></span>
- <span data-ttu-id="a8580-120">Användare som kan vara kunniga om ämnet.</span><span class="sxs-lookup"><span data-stu-id="a8580-120">Users who might be knowledgeable about the topic.</span></span>
- <span data-ttu-id="a8580-121">Filer, sidor och webbplatser som är relaterade till ämnet.</span><span class="sxs-lookup"><span data-stu-id="a8580-121">Files, pages, and sites that are related to the topic.</span></span>


## <a name="topic-management"></a><span data-ttu-id="a8580-122">Ämneshantering</span><span class="sxs-lookup"><span data-stu-id="a8580-122">Topic management</span></span>

<span data-ttu-id="a8580-123">Ämneshantering görs i organisationens **ämnescenter**.</span><span class="sxs-lookup"><span data-stu-id="a8580-123">Topic management is done in your organization's **topic center**.</span></span> <span data-ttu-id="a8580-124">Ämnescentrets webbplats skapas under installationen och fungerar som ditt kunskapscentrum för din organisation.</span><span class="sxs-lookup"><span data-stu-id="a8580-124">The topic center site is created during setup and serves as your center of knowledge for your organization.</span></span> <span data-ttu-id="a8580-125">Den innehåller en lista över alla ämnen som upptäcktes i din miljö, liksom alla ämnessidor som har skapats för dessa ämnen.</span><span class="sxs-lookup"><span data-stu-id="a8580-125">It will contain a list of all topics that were discovered in your environment, as well as all topic pages that were created for these topics.</span></span> 

<span data-ttu-id="a8580-126">Användare som får rätt behörighet kan göra följande i ämnescentret:</span><span class="sxs-lookup"><span data-stu-id="a8580-126">Users who are provided the correct permissions will be able to do the following in the topic center:</span></span>

- <span data-ttu-id="a8580-127">Bekräfta eller avvisa ämnen som upptäcktes i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="a8580-127">Confirm or reject topics that were discovered in your tenant.</span></span>
- <span data-ttu-id="a8580-128">Skapa nya ämnen manuellt efter behov (till exempel om det inte fanns tillräckligt med information för att det ska upptäckas via AI).</span><span class="sxs-lookup"><span data-stu-id="a8580-128">Create new topics manually as needed (for example, if not enough information was provided for it to be discovered through AI).</span></span>
- <span data-ttu-id="a8580-129">Redigera befintliga ämnessidor.</span><span class="sxs-lookup"><span data-stu-id="a8580-129">Edit existing topic pages.</span></span></br>

<span data-ttu-id="a8580-130">Mer information [finns i Arbeta med ämne i ämnescentret.](work-with-topics.md)</span><span class="sxs-lookup"><span data-stu-id="a8580-130">See [Work with topic in the topic center](work-with-topics.md) for more information.</span></span>  


## <a name="admin-controls"></a><span data-ttu-id="a8580-131">Administratörskontroller</span><span class="sxs-lookup"><span data-stu-id="a8580-131">Admin controls</span></span>

<span data-ttu-id="a8580-132">Med administratörskontroller i administrationscentret för Microsoft 365 kan du hantera kunskapsnätverket.</span><span class="sxs-lookup"><span data-stu-id="a8580-132">Admin controls in the Microsoft 365 admin center  allow you to manage your knowledge network.</span></span> <span data-ttu-id="a8580-133">De gör det möjligt för en Microsoft 365 global eller SharePoint-administratör att:</span><span class="sxs-lookup"><span data-stu-id="a8580-133">They allow a Microsoft 365 global or SharePoint admin to:</span></span>

- <span data-ttu-id="a8580-134">Kontrollera vilka användare i organisationen som får se ämnen i sina klientappar eller i SharePoint-sökresultat.</span><span class="sxs-lookup"><span data-stu-id="a8580-134">Control which users in your organization are allowed to see topics in their client apps or in SharePoint search results.</span></span>
- <span data-ttu-id="a8580-135">Kontrollera vilka SharePoint-webbplatser som ska genomsökas för att söka efter ämnen.</span><span class="sxs-lookup"><span data-stu-id="a8580-135">Control which SharePoint sites will be crawled to search for topics.</span></span>
- <span data-ttu-id="a8580-136">Konfigurera ämnesidentifiering för att utesluta specifika termer som du inte vill ska vara ett ämne.</span><span class="sxs-lookup"><span data-stu-id="a8580-136">Configure topic discovery to exclude specific terms that you don't want to be a topic.</span></span>
- <span data-ttu-id="a8580-137">Styr vilka användare som kan bekräfta eller avvisa ämnen i ämnescentret.</span><span class="sxs-lookup"><span data-stu-id="a8580-137">Control which users can to confirm or reject topics in the topic center.</span></span>
- <span data-ttu-id="a8580-138">Styr vilka användare som kan skapa och redigera ämnen i ämnescentret.</span><span class="sxs-lookup"><span data-stu-id="a8580-138">Control which users can create and edit topics in the topic center.</span></span>

<span data-ttu-id="a8580-139">Mer information [finns i Hantera kunskapsnätverket.](manage-knowledge-network.md)</span><span class="sxs-lookup"><span data-stu-id="a8580-139">See [Manage your knowledge network](manage-knowledge-network.md) for more information.</span></span> 

## <a name="topic-curation"></a><span data-ttu-id="a8580-140">Ämneshärdning</span><span class="sxs-lookup"><span data-stu-id="a8580-140">Topic curation</span></span>

<span data-ttu-id="a8580-141">AI kommer kontinuerligt att arbeta för att ge dig förslag för att förbättra dina ämnen när förändringar sker i din miljö.</span><span class="sxs-lookup"><span data-stu-id="a8580-141">AI will continually work to provide you suggestions to improve your topics as changes occur in your environment.</span></span>

<span data-ttu-id="a8580-142">Användare som du tillåter åtkomst till att se ämnen i sitt dagliga arbete får komma med förslag för att förbättra dem.</span><span class="sxs-lookup"><span data-stu-id="a8580-142">Users who you allow access to see topics in their daily work are allowed to make suggestions to improve them.</span></span> <span data-ttu-id="a8580-143">Om en användare till exempel visar ämnessidan och ser information som är felaktig eller behöver läggas till, kan de med en länk på ämnessidan skicka en begäran om att uppdatera informationen.</span><span class="sxs-lookup"><span data-stu-id="a8580-143">For example, if a user views the topic page and sees information that is incorrect or needs to be added, a link on the topic page allows them to submit a request to update the information.</span></span>

<span data-ttu-id="a8580-144">Dessutom kan användare med rätt behörighet tagga objekt som Teams-konversation som är relevanta för ett ämne och lägga till dem i ett visst ämne.</span><span class="sxs-lookup"><span data-stu-id="a8580-144">Additionally, users with proper permissions can tag items such as Teams conversation that are relevant to a topic, and add them to a specific topic.</span></span>




## <a name="see-also"></a><span data-ttu-id="a8580-145">Se även</span><span class="sxs-lookup"><span data-stu-id="a8580-145">See also</span></span>
[<span data-ttu-id="a8580-146">Ställ in kunskapshantering</span><span class="sxs-lookup"><span data-stu-id="a8580-146">Set up knowledge management</span></span>](set-up-knowledge-network.md)</br>
[<span data-ttu-id="a8580-147">Översikt över ämnescenter</span><span class="sxs-lookup"><span data-stu-id="a8580-147">Topic center overview</span></span>](topic-center-overview.md)