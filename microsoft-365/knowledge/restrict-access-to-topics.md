---
title: Begränsa åtkomst till ämnen i Microsoft Viva-ämnen
description: Hur du utesluter ämnen för att förhindra att de upptäcks.
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
ms.openlocfilehash: 6b3d2a4b6cbfc67623cea58b73681b7af7cc4889
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107164"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a><span data-ttu-id="55514-103">Begränsa åtkomst till ämnen i Microsoft Viva-ämnen</span><span class="sxs-lookup"><span data-stu-id="55514-103">Restrict access to topics in Microsoft Viva Topics</span></span>

<span data-ttu-id="55514-104">I Microsoft Viva kanske intressenter i organisationen vill se till att specifika ämnen inte upptäcks och exponeras för dina licensierade användare.</span><span class="sxs-lookup"><span data-stu-id="55514-104">In Microsoft Viva, stakeholders in your organization may want to make sure that specific topics aren't discovered and exposed to your licensed users.</span></span> <span data-ttu-id="55514-105">Du kanske arbetar på ett projekt som du inte vill visa information om ännu.</span><span class="sxs-lookup"><span data-stu-id="55514-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="55514-106">Office 365-behörigheter på webbplatser, filer och andra resurser hindrar användare av ämneserfarenheter från att visa känslig information i ämnen, men det finns ytterligare säkerhetsåtgärder för att förhindra att särskilda ämnen upptäcks.</span><span class="sxs-lookup"><span data-stu-id="55514-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="55514-107">Medan knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to know how it is done so that they can work collaboratively.</span><span class="sxs-lookup"><span data-stu-id="55514-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to know how it is done so that they can work collaboratively.</span></span>

> [!Important] 
> <span data-ttu-id="55514-108">I den här artikeln beskrivs olika sätt att förhindra att ämnen identifieras genom AI eller visas i din miljö som ett ytterligare säkerhetsskydd.</span><span class="sxs-lookup"><span data-stu-id="55514-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="55514-109">Det är viktigt att observera att användare i Viva Topics inte har behörighet att visa något i ett ämne som de inte har åtkomst till via Office 365-behörigheter.</span><span class="sxs-lookup"><span data-stu-id="55514-109">It is important to note that in Viva Topics, users aren't allowed to view anything in a topic that they aren't allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="55514-110">Även om en användare kan visa ett ämne kommer dess filer, webbplatser och sidor som de inte har Office 365-behörighet att visa inte att visas för dem.</span><span class="sxs-lookup"><span data-stu-id="55514-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="55514-111">Att se till att behörigheter för känsliga filer ställs in korrekt bör vara det primära säkerhetsåtgärden.</span><span class="sxs-lookup"><span data-stu-id="55514-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="55514-112">Förhindra att ämnen identifieras</span><span class="sxs-lookup"><span data-stu-id="55514-112">Prevent topics from being identified</span></span>

<span data-ttu-id="55514-113">Knowledge admin can restrict access to specific topics by preventing them from found in initial indexing.</span><span class="sxs-lookup"><span data-stu-id="55514-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="55514-114">Det finns två sätt att utföra den här uppgiften i administrationsinställningarna för Knowledge Network i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="55514-114">There are two ways to do this task in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="55514-115">[Välj SharePoint-webbplatser som ska undantas](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)från ämnesidentifiering: Du kan använda den här inställningen för att förhindra att vissa SharePoint-webbplatser crawlas för ämnen.</span><span class="sxs-lookup"><span data-stu-id="55514-115">[Select SharePoint sites to exclude from topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="55514-116">[Undanta avsnitt efter namn:](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)Administratörer kan använda den här inställningen för att förhindra att vissa ämnen upptäcks med namn.</span><span class="sxs-lookup"><span data-stu-id="55514-116">[Exclude topics by name](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="55514-117">I administratörsinställningarna för Knowledge Network kan en administratör ladda upp en lista med ämnen som ska undantas i en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="55514-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="55514-118">Du kan utesluta avsnitt som innehåller exakta eller partiella träffar i ett ämnesnamn.</span><span class="sxs-lookup"><span data-stu-id="55514-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="55514-119">Förhindra att avsnitt visas för specifika användare</span><span class="sxs-lookup"><span data-stu-id="55514-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="55514-120">Kunskapsadministratörer kan också [välja vilka som kan visa ämnen i organisationen.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)</span><span class="sxs-lookup"><span data-stu-id="55514-120">Knowledge admins can also [select who can view topics in your organization](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span></span> <span data-ttu-id="55514-121">Med den här inställningen kan du välja vilka licensierade användare som kan visa alla ämnen.</span><span class="sxs-lookup"><span data-stu-id="55514-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="55514-122">I en pilotmiljö kanske du till exempel bara vill tillåta att en liten grupp användare kan visa ämnen.</span><span class="sxs-lookup"><span data-stu-id="55514-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="55514-123">Ta bort ämnen från att visas</span><span class="sxs-lookup"><span data-stu-id="55514-123">Remove topics from being viewed</span></span>

<span data-ttu-id="55514-124">Kunskapshanterare kan välja att [ta bort ämnen](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) så att användarna inte längre kan se dem.</span><span class="sxs-lookup"><span data-stu-id="55514-124">Knowledge managers can choose to [remove topics](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) so that users can no longer see them.</span></span> <span data-ttu-id="55514-125">På sidan **Hantera ämnen** i Ämnescenter **kan knowledge** managers välja att avvisa vissa ämnen för att förhindra att de visas.</span><span class="sxs-lookup"><span data-stu-id="55514-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="55514-126">Ämnen kan tas bort oavsett om de är i föreslaget eller bekräftat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="55514-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="55514-127">Borttagna ämnen kan senare läggas till som visningsbara ämnen vid behov.</span><span class="sxs-lookup"><span data-stu-id="55514-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="55514-128">Se även</span><span class="sxs-lookup"><span data-stu-id="55514-128">See also</span></span>



  






