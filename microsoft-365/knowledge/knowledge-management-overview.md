---
title: Översikt över kunskaps hantering (för hands version)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Översikt över Knowledge Management i Project cortex.
ms.openlocfilehash: c4f7ff7d65ec08740dc14f717712731d839bd903
ms.sourcegitcommit: d648356b27842e779921859480b1b405a1804c7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361957"
---
# <a name="knowledge-management-overview-preview"></a><span data-ttu-id="41abc-103">Översikt över kunskaps hantering (för hands version)</span><span class="sxs-lookup"><span data-stu-id="41abc-103">Knowledge management Overview (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="41abc-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="41abc-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="41abc-105">[Läs mer om Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="41abc-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="41abc-106">Kunskaps hantering använder Microsoft AI-teknologi, Microsoft 365, Delve, sökning och andra komponenter och tjänster för att bygga ett kunskaps nätverk i din Microsoft 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="41abc-106">Knowledge management uses Microsoft AI technology, Microsoft 365, Delve, Search, and other components and services to build a knowledge network in your Microsoft 365 environment.</span></span> 

   ![Kunskaps hanterings flöde](../media/content-understanding/knowledge-management-flowchart.png) </br> 

<span data-ttu-id="41abc-108">Målet är att leverera information till användare i program som de använder varje dag, till exempel Outlook, teams och SharePoint.</span><span class="sxs-lookup"><span data-stu-id="41abc-108">It's goal is to deliver information to you users in apps they use everyday, such as Outlook, Teams, and SharePoint.</span></span>

<span data-ttu-id="41abc-109">Användarna kan till exempel se okända villkor i deras e-post, SharePoint-webbplatser eller i team-konversationer, som de vill veta mer om.</span><span class="sxs-lookup"><span data-stu-id="41abc-109">For example, users see unfamiliar terms in their emails, SharePoint sites, or in Teams conversations, that they want to know more about.</span></span> <span data-ttu-id="41abc-110">Kunskaps hantering använder AI för att automatiskt söka efter och identifiera dessa **ämnen**och sammanfattar information om dem, till exempel en kort beskrivning, ämnes experter på ämnet och webbplatser, filer och sidor som är relaterade till det.</span><span class="sxs-lookup"><span data-stu-id="41abc-110">Knowledge management uses AI to automatically searches for and identifies these **topics**, and compiles information about them, such as a short description, subject matter experts on the topic, and sites, files, and pages that are related to it.</span></span> <span data-ttu-id="41abc-111">Du kan välja att uppdatera ämnes informationen efter behov.</span><span class="sxs-lookup"><span data-stu-id="41abc-111">You can choose to update the topic information as needed.</span></span> <span data-ttu-id="41abc-112">Du kan sedan göra de avsnitt tillgängliga för användarna, vilket innebär att för varje förekomst av avsnittet som visas i program som Outlook, grupper och SharePoint markeras texten.</span><span class="sxs-lookup"><span data-stu-id="41abc-112">You can then make the topics available to your users, which means that for every instance of the topic that appears in apps such as Outlook, Teams, and SharePoint, the text will be highlighted.</span></span> <span data-ttu-id="41abc-113">Användare kan välja att välja ämne för att lära dig mer om det i avsnitts informationen.</span><span class="sxs-lookup"><span data-stu-id="41abc-113">Users can choose to select the topic to learn more about it through the topic details.</span></span>


## <a name="topic-discovery"></a><span data-ttu-id="41abc-114">Avsnitts identifiering</span><span class="sxs-lookup"><span data-stu-id="41abc-114">Topic discovery</span></span>

<span data-ttu-id="41abc-115">Kunskaps hantering använder Microsoft AI-teknologi till att söka efter **ämnen** i din Office 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="41abc-115">Knowledge Management uses Microsoft AI technology to search for **topics** in your Office 365 environment.</span></span>

<span data-ttu-id="41abc-116">Ett ämne är en fras eller en term som är organiserad eller viktig.</span><span class="sxs-lookup"><span data-stu-id="41abc-116">A topic is a phrase or term that is organizationally significant or important.</span></span> <span data-ttu-id="41abc-117">Den har en specifik innebörd för organisationen och har resurser relaterade till det som kan hjälpa folk förstå vad det är och få mer information om den.</span><span class="sxs-lookup"><span data-stu-id="41abc-117">It has a specific meaning to the organization, and has resources related to it that can help people understand what it is and find more information about it.</span></span>

<span data-ttu-id="41abc-118">När ett ämne identifieras skapas en **ämnes sida** för den som innehåller information som samlats in genom identifiering av ämnen, till exempel:</span><span class="sxs-lookup"><span data-stu-id="41abc-118">When a topic is discovered, a **topic page** is created for it that contains information that was gathered through topic discovery, such as:</span></span>

- <span data-ttu-id="41abc-119">En kort beskrivning av ämnet.</span><span class="sxs-lookup"><span data-stu-id="41abc-119">A short description of the topic.</span></span>
- <span data-ttu-id="41abc-120">Användare som kan vara kunskapsbaserade i avsnittet.</span><span class="sxs-lookup"><span data-stu-id="41abc-120">Users who might be knowledgeable about the topic.</span></span>
- <span data-ttu-id="41abc-121">Filer, sidor och webbplatser som är relaterade till avsnittet.</span><span class="sxs-lookup"><span data-stu-id="41abc-121">Files, pages, and sites that are related to the topic.</span></span>


## <a name="topic-management"></a><span data-ttu-id="41abc-122">Hantering av ämnen</span><span class="sxs-lookup"><span data-stu-id="41abc-122">Topic management</span></span>

<span data-ttu-id="41abc-123">Hantering av ämnen finns i organisationens **ämnes Center**.</span><span class="sxs-lookup"><span data-stu-id="41abc-123">Topic management is done in your organization's **topic center**.</span></span> <span data-ttu-id="41abc-124">Webbplatsen för ämnes Center skapas under installationen och fungerar som din grupp kunskap för organisationen.</span><span class="sxs-lookup"><span data-stu-id="41abc-124">The topic center site is created during setup and serves as your center of knowledge for your organization.</span></span> <span data-ttu-id="41abc-125">Den innehåller en lista över alla ämnen som upptäckts i din miljö, samt alla sidor som skapats för dessa ämnen.</span><span class="sxs-lookup"><span data-stu-id="41abc-125">It will contain a list of all topics that were discovered in your environment, as well as all topic pages that were created for these topics.</span></span> 

<span data-ttu-id="41abc-126">Användare som har rätt behörighet kan göra följande i ämnes centret:</span><span class="sxs-lookup"><span data-stu-id="41abc-126">Users who are provided the correct permissions will be able to do the following in the topic center:</span></span>

- <span data-ttu-id="41abc-127">Bekräfta eller avvisa ämnen som upptäckts i klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="41abc-127">Confirm or reject topics that were discovered in your tenant.</span></span>
- <span data-ttu-id="41abc-128">Skapa nya ämnen manuellt efter behov (till exempel om det inte finns tillräckligt med information för att det ska identifieras via AI).</span><span class="sxs-lookup"><span data-stu-id="41abc-128">Create new topics manually as needed (for example, if not enough information was provided for it to be discovered through AI).</span></span>
- <span data-ttu-id="41abc-129">Redigera befintliga avsnitts sidor.</span><span class="sxs-lookup"><span data-stu-id="41abc-129">Edit existing topic pages.</span></span></br>

<span data-ttu-id="41abc-130">Mer information finns i [arbeta med ämne i ämnes centret](work-with-topics.md) .</span><span class="sxs-lookup"><span data-stu-id="41abc-130">See [Work with topic in the topic center](work-with-topics.md) for more information.</span></span>  


## <a name="admin-controls"></a><span data-ttu-id="41abc-131">Administratörs kontroller</span><span class="sxs-lookup"><span data-stu-id="41abc-131">Admin controls</span></span>

<span data-ttu-id="41abc-132">Med administratörs kontroller i Microsoft 365 Admin Center kan du hantera kunskaps nätverk.</span><span class="sxs-lookup"><span data-stu-id="41abc-132">Admin controls in the Microsoft 365 admin center  allow you to manage your knowledge network.</span></span> <span data-ttu-id="41abc-133">De tillåter en Microsoft 365 global-eller SharePoint-administratör att:</span><span class="sxs-lookup"><span data-stu-id="41abc-133">They allow a Microsoft 365 global or SharePoint admin to:</span></span>

- <span data-ttu-id="41abc-134">Kontrol lera vilka användare i organisationen som har tillstånd att se ämnen i sina klient program eller i Sök resultat i SharePoint.</span><span class="sxs-lookup"><span data-stu-id="41abc-134">Control which users in your organization are allowed to see topics in their client apps or in SharePoint search results.</span></span>
- <span data-ttu-id="41abc-135">Kontrol lera vilka SharePoint-webbplatser som ska crawlas för att söka efter avsnitt.</span><span class="sxs-lookup"><span data-stu-id="41abc-135">Control which SharePoint sites will be crawled to search for topics.</span></span>
- <span data-ttu-id="41abc-136">Konfigurera avsnitts identifiering för att exkludera specifika termer som du inte vill ska vara ett ämne.</span><span class="sxs-lookup"><span data-stu-id="41abc-136">Configure topic discovery to exclude specific terms that you don't want to be a topic.</span></span>
- <span data-ttu-id="41abc-137">Kontrol lera vilka användare som kan bekräfta eller avvisa ämnen i ämnes centret.</span><span class="sxs-lookup"><span data-stu-id="41abc-137">Control which users can to confirm or reject topics in the topic center.</span></span>
- <span data-ttu-id="41abc-138">Kontrol lera vilka användare som kan skapa och redigera ämnen i ämnes centret.</span><span class="sxs-lookup"><span data-stu-id="41abc-138">Control which users can create and edit topics in the topic center.</span></span>

<span data-ttu-id="41abc-139">Mer information finns i [Hantera kunskaps nätverk](manage-knowledge-network.md) .</span><span class="sxs-lookup"><span data-stu-id="41abc-139">See [Manage your knowledge network](manage-knowledge-network.md) for more information.</span></span> 

## <a name="topic-curation"></a><span data-ttu-id="41abc-140">Ämnes underavsnitt</span><span class="sxs-lookup"><span data-stu-id="41abc-140">Topic curation</span></span>

<span data-ttu-id="41abc-141">AI fungerar fort löp ande för att ge förslag på att förbättra dina ämnen när ändringar sker i miljön.</span><span class="sxs-lookup"><span data-stu-id="41abc-141">AI will continually work to provide you suggestions to improve your topics as changes occur in your environment.</span></span>

<span data-ttu-id="41abc-142">Användare som du tillåter åtkomst till för att se ämnen i deras dagliga arbete får göra förslag för att förbättra dem.</span><span class="sxs-lookup"><span data-stu-id="41abc-142">Users who you allow access to see topics in their daily work are allowed to make suggestions to improve them.</span></span> <span data-ttu-id="41abc-143">Om en användare till exempel visar ämnes sidan och ser information som är felaktig eller måste läggas till kan en länk på ämnes sidan skicka en förfrågan om att uppdatera informationen.</span><span class="sxs-lookup"><span data-stu-id="41abc-143">For example, if a user views the topic page and sees information that is incorrect or needs to be added, a link on the topic page allows them to submit a request to update the information.</span></span>

<span data-ttu-id="41abc-144">Dessutom kan användare med rätt behörighet tagga objekt som en Teams-konversation som är relevant för ett ämne och lägga till dem i ett visst ämne.</span><span class="sxs-lookup"><span data-stu-id="41abc-144">Additionally, users with proper permissions can tag items such as Teams conversation that are relevant to a topic, and add them to a specific topic.</span></span>




## <a name="see-also"></a><span data-ttu-id="41abc-145">Se även</span><span class="sxs-lookup"><span data-stu-id="41abc-145">See also</span></span>
[<span data-ttu-id="41abc-146">Konfigurera kunskaps hantering</span><span class="sxs-lookup"><span data-stu-id="41abc-146">Set up knowledge management</span></span>](set-up-knowledge-network.md)</br>
[<span data-ttu-id="41abc-147">Översikt över ämnes Center</span><span class="sxs-lookup"><span data-stu-id="41abc-147">Topic center overview</span></span>](topic-center-overview.md)
