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
ms.openlocfilehash: ea0bbc1f7d34ff01fcf446bfa4bbd0b95f310c4c
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976173"
---
# <a name="topic-experiences-discovery-and-curation-preview"></a><span data-ttu-id="91bdf-103">Ämnen Upptäck och granska (för hands version)</span><span class="sxs-lookup"><span data-stu-id="91bdf-103">Topic Experiences discovery and curation (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="91bdf-104">Innehållet i den här artikeln gäller för projekt cortex privat för hands version.</span><span class="sxs-lookup"><span data-stu-id="91bdf-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="91bdf-105">[Läs mer om Project Cortex](https://aka.ms/projectcortex).</span><span class="sxs-lookup"><span data-stu-id="91bdf-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="91bdf-106">Avsnitts upplevelser konverterar kunskaps information till kunskap i din Microsoft 365-miljö.</span><span class="sxs-lookup"><span data-stu-id="91bdf-106">Topic Experiences converts knowledge information to knowledge in your Microsoft 365 environment.</span></span> <span data-ttu-id="91bdf-107">Vi har allt Läs igenom dokument och webbplats sidor där vi inte känner till termer.</span><span class="sxs-lookup"><span data-stu-id="91bdf-107">We've all experienced reading through documents and site pages where we encounter terms we are unfamiliar with.</span></span> <span data-ttu-id="91bdf-108">Många gånger vi håller på att avbryta det vi gör för att göra en genom gång av mer information.</span><span class="sxs-lookup"><span data-stu-id="91bdf-108">Many times we stop what we are doing to spend precious time searching for more information.</span></span>

<span data-ttu-id="91bdf-109">Vilka ämnes upplevelser använder Microsoft Graph och AI för att identifiera **ämnen** i din organisation.</span><span class="sxs-lookup"><span data-stu-id="91bdf-109">What Topic Experiences does is use Microsoft Graph and AI to identify **topics** in your organization.</span></span>  <span data-ttu-id="91bdf-110">Ett ämne är en fras eller en term som har en specifik betydelse för en organisation, där användare skulle vilja ha nytta av att visa en wiki-sida om den.</span><span class="sxs-lookup"><span data-stu-id="91bdf-110">A topic is a phrase or term that has a specific meaning to an organization, where users would benefit by being able to view a wiki page about it.</span></span> <span data-ttu-id="91bdf-111">AI söker efter personer och innehåll som är anslutna till ämnet, och om det upptäcks blir det ett förslag till ämne.</span><span class="sxs-lookup"><span data-stu-id="91bdf-111">AI searches for people and content connected to the topic, and if enough it discovered, it becomes a suggested topic.</span></span>

<span data-ttu-id="91bdf-112">Informationen om AI-genererat ämne läggs till på en **ämnes sida**, som kan innehålla:</span><span class="sxs-lookup"><span data-stu-id="91bdf-112">The AI generated topic information is added to a **Topic page**, which can contain:</span></span>
- <span data-ttu-id="91bdf-113">En kort beskrivning av ämnet.</span><span class="sxs-lookup"><span data-stu-id="91bdf-113">A short description of the topic.</span></span>
- <span data-ttu-id="91bdf-114">Alternativa namn för ämnet.</span><span class="sxs-lookup"><span data-stu-id="91bdf-114">Alternate names for the topic.</span></span>
- <span data-ttu-id="91bdf-115">Personer som kan veta mer om ämnet.</span><span class="sxs-lookup"><span data-stu-id="91bdf-115">People who might know more about the topic.</span></span>
- <span data-ttu-id="91bdf-116">Webbplatser, filer och sidor som kan vara relaterade till ämnet.</span><span class="sxs-lookup"><span data-stu-id="91bdf-116">Sites, files, and pages that might be related to the topic.</span></span>

<span data-ttu-id="91bdf-117">Avsnitts upplevelser ser då till att alla förekomster av ett avsnitt är markerade på alla SharePoint-moderna webbplats sidor i klient organisationen.</span><span class="sxs-lookup"><span data-stu-id="91bdf-117">Topic experiences then makes sure that every instance of a topic is highlighted on all SharePoint modern site pages in your tenant.</span></span> <span data-ttu-id="91bdf-118">När en användare är nyfiken på mer information om ett ämne kan de välja det markerade avsnittet för att visa ett **sammanfattnings** kort för ämne med en kort beskrivning.</span><span class="sxs-lookup"><span data-stu-id="91bdf-118">When a user is curious to learn more about a topic, they can select the highlighted topic to view a **Topic summary** card that provides a short description.</span></span> <span data-ttu-id="91bdf-119">Och om de vill lära sig mer kan de välja en länk för **ämnes information** i sammanfattningen för att öppna sidan detaljerad avsnitt.</span><span class="sxs-lookup"><span data-stu-id="91bdf-119">And if they want to learn more, they can select a **Topic details** link in the summary to open the detailed topic page.</span></span>

![Ämnes markeringar](../media/knowledge-management/saturn.png) </br>

<span data-ttu-id="91bdf-121">Dessutom kan användarna Hitta ämnen via Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="91bdf-121">Additionally, users will also be able to find topics through Microsoft Search.</span></span>


## <a name="topic-curation"></a><span data-ttu-id="91bdf-122">Ämnes underavsnitt</span><span class="sxs-lookup"><span data-stu-id="91bdf-122">Topic curation</span></span>

<span data-ttu-id="91bdf-123">Ämnen som går vidare med "beslagning" för att förbättra kvaliteten på dina ämnen.</span><span class="sxs-lookup"><span data-stu-id="91bdf-123">Topic Experiences welcomes human "curation" to improve the quality of your topics.</span></span> <span data-ttu-id="91bdf-124">Även om AI från början identifierar och föreslår ämnen, manuellt gjorda uppdateringar av innehåll från deltagare, bekräftelse från användare för AI-genererat innehåll och feedback om användbarheten av ämnena är allt som behövs.</span><span class="sxs-lookup"><span data-stu-id="91bdf-124">While AI initially identifies and suggests topics, manually made updates to content from contributors, confirmation from users for AI generated content, and feedback on the usefulness of topics are all essential.</span></span>

- <span data-ttu-id="91bdf-125">AI-genererade ämnen ("föreslagna ämnen") kan granskas av **kunskaps cheferna** i din organisation.</span><span class="sxs-lookup"><span data-stu-id="91bdf-125">AI generated topics ("suggested topics") can be reviewed by **knowledge managers** in your organization.</span></span> <span data-ttu-id="91bdf-126">På sidan Hantera ämnen i ämnes Center kan de välja att bekräfta att de är giltiga eller avvisa dem för att förhindra att de visas.</span><span class="sxs-lookup"><span data-stu-id="91bdf-126">In the Manage Topics page in the Topic Center, they can choose to confirm them as valid, or reject them to prevent them from being viewed.</span></span>

- <span data-ttu-id="91bdf-127">Du kan tilldela behörigheter för att *skapa och redigera ämnen* till alla dina licensierade användare så att de kan göra ändringar i befintliga ämnen eller skapa nya ämnen när de behövs.</span><span class="sxs-lookup"><span data-stu-id="91bdf-127">You can assign *Create and edit topics* permissions to any of your licensed users so that they can make changes to existing topics or create new topics when needed.</span></span> 

- <span data-ttu-id="91bdf-128">Även användare som bara har Läs åtkomst till ämne (ämnes visnings program) ombeds att bekräfta att vissa ämnen är användbara.</span><span class="sxs-lookup"><span data-stu-id="91bdf-128">Even users who only have read access to topic (topic viewers) will be asked to verify the usefulness of specific topics.</span></span>

<span data-ttu-id="91bdf-129">Även med mänsklig granskning letar AI efter mer information om ämnen och söker efter mänsklig verifiering.</span><span class="sxs-lookup"><span data-stu-id="91bdf-129">Even with human curation, AI will continually look for more information about topics, and will look for human verification.</span></span> <span data-ttu-id="91bdf-130">Om t ex AI tror att du är en person som ska fästas som expert på ett ämne ber vi dig bekräfta detta.</span><span class="sxs-lookup"><span data-stu-id="91bdf-130">For example, if AI thinks you are a person that should be pinned as an expert on a topic, it will ask you to confirm this.</span></span> 

















## <a name="see-also"></a><span data-ttu-id="91bdf-131">Se även</span><span class="sxs-lookup"><span data-stu-id="91bdf-131">See also</span></span>



  






