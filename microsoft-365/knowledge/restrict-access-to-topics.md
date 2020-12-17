---
title: Begränsa åtkomst till ämnen
description: Så här utesluter du ämnen som hindrar dem från att upptäckas.
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
ms.openlocfilehash: b23d01585d9282132d9e55c74bb22bcdc6ca314a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699068"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a><span data-ttu-id="d4ecc-103">Begränsa åtkomsten till ämnen i ämnen</span><span class="sxs-lookup"><span data-stu-id="d4ecc-103">Restrict access to topics in Topic Experiences</span></span>

<span data-ttu-id="d4ecc-104">I ämnes erfarenheter kanske intressenterna i organisationen vill se till att specifika ämnen inte identifieras och exponeras för dina licensierade användare.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-104">In Topic Experiences, stakeholders in your organization may want to make sure that specific topics are not discovered and exposed to your licensed users.</span></span> <span data-ttu-id="d4ecc-105">Du kan till exempel arbeta med ett projekt som du inte vill visa information om ännu.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="d4ecc-106">Office 365-behörigheter på webbplatser, filer och andra resurser gör att användarna inte kan visa känslig information i ämnen, men det finns ytterligare säkerhets åtgärder för att förhindra att vissa ämnen identifieras.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="d4ecc-107">När kunskaps administratörer styr inställningar för kunskaps nätverk för att förhindra att ämnen upptäcks måste kunskaps cheferna och andra intressenter känna till hur det görs, så att de kan samar beta på detta.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to be know how this is done so that they can work collaboratively on this.</span></span>

> [!Important] 
> <span data-ttu-id="d4ecc-108">I den här artikeln beskrivs olika sätt att förhindra att ämnen identifieras via AI eller visas i din miljö som ytterligare säkerhetsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="d4ecc-109">Det är viktigt att tänka på att användare inte har tillstånd att visa något i ett ämne som de inte har behörighet att komma åt via Office 365-behörigheter.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-109">It is important to note that in Topic Experiences, users are not allowed to view anything in a topic that they are not allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="d4ecc-110">Även om en användare kan visa ett ämne kan dess filer, webbplatser och sidor som inte har Office 365-behörigheter att Visa inte visas för dem.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="d4ecc-111">Att se till att behörigheterna för känsliga filer är korrekta bör vara din primära säkerhets kontroll.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="d4ecc-112">Förhindra att ämnen identifieras</span><span class="sxs-lookup"><span data-stu-id="d4ecc-112">Prevent topics from being identified</span></span>

<span data-ttu-id="d4ecc-113">Kunskaps administratören kan begränsa åtkomsten till specifika ämnen genom att hindra dem från att hittas vid inledande indexering.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="d4ecc-114">Det finns två sätt att göra detta i administratörs inställningarna för kunskaps nätverk i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-114">There are two ways to do this in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="d4ecc-115">[Välj SharePoint-webbplatser som ska undantas från avsnitts identifiering](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): du kan använda den här inställningen för att förhindra att vissa SharePoint-webbplatser crawlas för avsnitt.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-115">[Select SharePoint sites to exclude from topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="d4ecc-116">[Utelämna ämnen efter namn](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): administratörer kan använda den här inställningen för att förhindra att vissa ämnen identifieras med namn.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-116">[Exclude topics by name](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="d4ecc-117">I kunskaps nätverkets administratörs inställningar kan en administratör överföra en lista med ämnen som ska uteslutas i en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="d4ecc-118">Du kan utesluta ämnen med exakt eller delvis matchning av ett avsnitts namn.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="d4ecc-119">Förhindra att ämnen visas av specifika användare</span><span class="sxs-lookup"><span data-stu-id="d4ecc-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="d4ecc-120">Kunskaps administratörer kan också [välja vem som kan visa ämnen i din organisation](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span><span class="sxs-lookup"><span data-stu-id="d4ecc-120">Knowledge admins can also [select who can view topics in your organization](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span></span> <span data-ttu-id="d4ecc-121">Med den här inställningen kan du välja vilka licensierade användare som ska kunna visa alla ämnen.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="d4ecc-122">I en pilot miljö kanske du till exempel vill tillåta att en liten grupp användare inte kan se ämnen.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="d4ecc-123">Ta bort ämnen som visas</span><span class="sxs-lookup"><span data-stu-id="d4ecc-123">Remove topics from being viewed</span></span>

<span data-ttu-id="d4ecc-124">Kunskaps chefer kan välja att [ta bort ämnen](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) så att användare inte längre kan se dem.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-124">Knowledge managers can choose to [remove topics](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) so that users can no longer see them.</span></span> <span data-ttu-id="d4ecc-125">På sidan **hantera ämnen** i **ämnes Center** kan kunskaps ansvariga välja att avvisa vissa ämnen för att förhindra att de visas.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="d4ecc-126">Ämnen kan tas bort oavsett om de är i ett föreslaget eller bekräftat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="d4ecc-127">Borttagna ämnen kan senare läggas tillbaka som visnings bara avsnitt om det behövs.</span><span class="sxs-lookup"><span data-stu-id="d4ecc-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="d4ecc-128">Se även</span><span class="sxs-lookup"><span data-stu-id="d4ecc-128">See also</span></span>



  






