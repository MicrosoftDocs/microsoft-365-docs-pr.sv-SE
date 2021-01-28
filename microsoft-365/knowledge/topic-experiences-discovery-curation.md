---
title: 'Avsnitts identifiering och granskning (för hands version) '
description: Översikt över hur ämnen identifieras.
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-topics
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 08860b32b6809f489a9c108dcfaed3f61fb2e306
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029644"
---
# <a name="topic-experiences-discovery-and-curation-preview"></a><span data-ttu-id="1888e-103">Ämnen Upptäck och granska (för hands version)</span><span class="sxs-lookup"><span data-stu-id="1888e-103">Topic Experiences discovery and curation (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="1888e-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="1888e-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="1888e-105">[Läs mer om Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="1888e-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="1888e-106">Avsnitts upplevelser konverterar kunskaps information till kunskap i din Microsoft 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="1888e-106">Topic Experiences converts knowledge information to knowledge in your Microsoft 365 environment.</span></span> <span data-ttu-id="1888e-107">Vi har allt Läs igenom dokument och webbplats sidor där vi inte känner till termer.</span><span class="sxs-lookup"><span data-stu-id="1888e-107">We've all experienced reading through documents and site pages where we encounter terms we are unfamiliar with.</span></span> <span data-ttu-id="1888e-108">Många gånger vi håller på att avbryta det vi gör för att göra en genom gång av mer information.</span><span class="sxs-lookup"><span data-stu-id="1888e-108">Many times we stop what we are doing to spend precious time searching for more information.</span></span>

<span data-ttu-id="1888e-109">Vilka ämnes upplevelser använder Microsoft Graph och AI för att identifiera **ämnen** i din organisation.</span><span class="sxs-lookup"><span data-stu-id="1888e-109">What Topic Experiences does is use Microsoft Graph and AI to identify **topics** in your organization.</span></span>  <span data-ttu-id="1888e-110">Ett ämne är en fras eller en term som har en specifik betydelse för en organisation, där användare skulle vilja ha nytta av att visa en wiki-sida om den.</span><span class="sxs-lookup"><span data-stu-id="1888e-110">A topic is a phrase or term that has a specific meaning to an organization, where users would benefit by being able to view a wiki page about it.</span></span> <span data-ttu-id="1888e-111">AI söker efter personer och innehåll som är anslutna till ämnet, och om det upptäcks blir det ett förslag till ämne.</span><span class="sxs-lookup"><span data-stu-id="1888e-111">AI searches for people and content connected to the topic, and if enough it discovered, it becomes a suggested topic.</span></span>

<span data-ttu-id="1888e-112">Informationen om det föreslagna ämnet för AI läggs till på en **ämnes sida**, som kan innehålla:</span><span class="sxs-lookup"><span data-stu-id="1888e-112">The AI suggested topic information is added to a **Topic page**, which can contain:</span></span>
- <span data-ttu-id="1888e-113">En kort beskrivning av ämnet.</span><span class="sxs-lookup"><span data-stu-id="1888e-113">A short description of the topic.</span></span>
- <span data-ttu-id="1888e-114">Alternativa namn för ämnet.</span><span class="sxs-lookup"><span data-stu-id="1888e-114">Alternate names for the topic.</span></span>
- <span data-ttu-id="1888e-115">Personer som kan veta mer om ämnet.</span><span class="sxs-lookup"><span data-stu-id="1888e-115">People who might know more about the topic.</span></span>
- <span data-ttu-id="1888e-116">Webbplatser, filer och sidor som kan vara relaterade till ämnet.</span><span class="sxs-lookup"><span data-stu-id="1888e-116">Sites, files, and pages that might be related to the topic.</span></span>

<span data-ttu-id="1888e-117">Avsnitts upplevelser när kontexten är lämplig, föreslår dessa ämnen att markeras på alla sidor i SharePoints moderna webbplatser i klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="1888e-117">Topic experiences then, when the context is appropriate, suggests these topics to be highlighted on all SharePoint modern site pages in your tenant.</span></span> <span data-ttu-id="1888e-118">När en användare är nyfiken på mer information om ett ämne kan de välja det markerade avsnittet för att visa ett **sammanfattnings** kort för ämne med en kort beskrivning.</span><span class="sxs-lookup"><span data-stu-id="1888e-118">When a user is curious to learn more about a topic, they can select the highlighted topic to view a **Topic summary** card that provides a short description.</span></span> <span data-ttu-id="1888e-119">Och om de vill lära sig mer kan de välja en länk för **ämnes information** i sammanfattningen för att öppna sidan detaljerad avsnitt.</span><span class="sxs-lookup"><span data-stu-id="1888e-119">And if they want to learn more, they can select a **Topic details** link in the summary to open the detailed topic page.</span></span>

![Ämnes markeringar](../media/knowledge-management/saturn.png) </br>

<span data-ttu-id="1888e-121">Dessutom kan användarna Hitta ämnen via Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="1888e-121">Additionally, users will also be able to find topics through Microsoft Search.</span></span>


## <a name="topic-curation"></a><span data-ttu-id="1888e-122">Ämnes underavsnitt</span><span class="sxs-lookup"><span data-stu-id="1888e-122">Topic curation</span></span>

<span data-ttu-id="1888e-123">Ämnen som får bidrag från människa kan bidra till bättre kvalitet på dina ämnen.</span><span class="sxs-lookup"><span data-stu-id="1888e-123">Topic Experiences welcomes human contribution to improve the quality of your topics.</span></span> <span data-ttu-id="1888e-124">Även om AI från början identifierar och föreslår ämnen, manuellt gjorda redigeringar till innehåll från deltagare, bekräftelse från användare för AI-genererat innehåll och feedback om användbarheten av ämnena är allt nödvändigt.</span><span class="sxs-lookup"><span data-stu-id="1888e-124">While AI initially identifies and suggests topics, manually made edits to content from contributors, confirmation from users for AI generated content, and feedback on the usefulness of topics are all essential.</span></span>

- <span data-ttu-id="1888e-125">AI-genererade ämnen ("föreslagna ämnen") kan granskas av **kunskaps cheferna** i din organisation.</span><span class="sxs-lookup"><span data-stu-id="1888e-125">AI generated topics ("suggested topics") can be reviewed by **knowledge managers** in your organization.</span></span> <span data-ttu-id="1888e-126">På sidan Hantera ämnen i ämnes Center kan de välja att bekräfta att de är giltiga eller avvisa dem för att förhindra att de visas.</span><span class="sxs-lookup"><span data-stu-id="1888e-126">In the Manage Topics page in the Topic Center, they can choose to confirm them as valid, or reject them to prevent them from being viewed.</span></span>

- <span data-ttu-id="1888e-127">Du kan tilldela behörigheter för att *skapa och redigera ämnen* till alla dina licensierade användare så att de kan göra ändringar i befintliga ämnen eller skapa nya ämnen när de behövs.</span><span class="sxs-lookup"><span data-stu-id="1888e-127">You can assign *Create and edit topics* permissions to any of your licensed users so that they can make changes to existing topics or create new topics when needed.</span></span> 

- <span data-ttu-id="1888e-128">Även användare som bara har Läs åtkomst till ämne (ämnes visnings program) ombeds att bekräfta att vissa ämnen är användbara.</span><span class="sxs-lookup"><span data-stu-id="1888e-128">Even users who only have read access to topic (topic viewers) will be asked to verify the usefulness of specific topics.</span></span> <span data-ttu-id="1888e-129">Deras feedback görs också för att bekräfta eller avvisa ett föreslaget ämne.</span><span class="sxs-lookup"><span data-stu-id="1888e-129">Their feedback is also taken to confirm or reject a suggested topic.</span></span>

<span data-ttu-id="1888e-130">Även med mänsklig redigering letar AI kontinuerligt efter mer information om ämnen och söker efter mänsklig verifiering.</span><span class="sxs-lookup"><span data-stu-id="1888e-130">Even with human edits, AI will continually look for more information about topics, and will look for human verification.</span></span> <span data-ttu-id="1888e-131">Om t ex AI tror att du är en person som ska vara en expert på ett ämne ber vi dig bekräfta detta.</span><span class="sxs-lookup"><span data-stu-id="1888e-131">For example, if AI thinks you are a person that should be listed as an expert on a topic, it will ask you to confirm this.</span></span> 



## <a name="see-also"></a><span data-ttu-id="1888e-132">Se även</span><span class="sxs-lookup"><span data-stu-id="1888e-132">See also</span></span>
