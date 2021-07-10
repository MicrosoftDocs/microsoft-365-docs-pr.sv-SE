---
title: Multi-Geo Capabilities i Microsoft Teams
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
description: Läs mer om Teams fungerar med Microsoft 365 Multi-Geo.
ms.openlocfilehash: 9fe9b289b0ffbef12327c4232b9deb6727b6d718
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362672"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a><span data-ttu-id="b44bc-103">Multi-Geo capabilities in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b44bc-103">Multi-Geo capabilities in Microsoft Teams</span></span>

<span data-ttu-id="b44bc-104">Med multi geofunktioner i Teams kan Teams lagras i vila på en viss geoplats.</span><span class="sxs-lookup"><span data-stu-id="b44bc-104">Multi-Geo capabilities in Teams enables Teams chat data to be stored at rest in a specified geo location.</span></span> <span data-ttu-id="b44bc-105">Chattdata består av chattmeddelanden, inklusive privata meddelanden, kanalmeddelanden och bilder som används i chattar.</span><span class="sxs-lookup"><span data-stu-id="b44bc-105">Chat data consists of chat messages, including private messages, channel messages, and images used in chats.</span></span>

<span data-ttu-id="b44bc-106">Teams använder den önskade dataplatsen (PDL) för användare och grupper för att avgöra var data ska lagras.</span><span class="sxs-lookup"><span data-stu-id="b44bc-106">Teams uses the Preferred Data Location (PDL) for users and groups to determine where to store data.</span></span> <span data-ttu-id="b44bc-107">Om PDL-data inte anges eller är ogiltiga lagras data på klientorganisationens centrala plats.</span><span class="sxs-lookup"><span data-stu-id="b44bc-107">If the PDL is not set or is invalid, data is stored in the tenant's central location.</span></span>

## <a name="user-chat"></a><span data-ttu-id="b44bc-108">Användarchatt</span><span class="sxs-lookup"><span data-stu-id="b44bc-108">User chat</span></span>

<span data-ttu-id="b44bc-109">Användarchatt innehåller 1:1-meddelanden, 1:många och privata mötesmeddelanden.</span><span class="sxs-lookup"><span data-stu-id="b44bc-109">User chat includes one-to-one, one-to-many, and private meeting messages.</span></span>

<span data-ttu-id="b44bc-110">När en ny användare skapas Teams användarens PDL och lagrar alla chattdata på den geoplatsen.</span><span class="sxs-lookup"><span data-stu-id="b44bc-110">When a new user is created, Teams reads the user's PDL and stores all their chat data in that geo location.</span></span>

<span data-ttu-id="b44bc-111">Om en administratör lägger till eller ändrar PDL för en användare läggs användarens chattdata till i en migreringskö för att flyttas till den angivna geoplatsen för befintliga användare.</span><span class="sxs-lookup"><span data-stu-id="b44bc-111">For existing users, if an administrator adds or modifies the PDL for a user, that user's chat data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="b44bc-112">Lagringsplatsen för en 1:1- eller en-till-många-chatt baseras på PDL för den person som skapade chatten.</span><span class="sxs-lookup"><span data-stu-id="b44bc-112">The storage location for a one-to-one or one-to-many chat is based on the PDL of the person who created the chat.</span></span> <span data-ttu-id="b44bc-113">Om användarens PDL ändras migreras chatten till den nya geoplatsen.</span><span class="sxs-lookup"><span data-stu-id="b44bc-113">If that user's PDL is changed, the chat will be migrated to the new geo location.</span></span> <span data-ttu-id="b44bc-114">Lagringsplatsen för en möteschatt baseras på mötesorganisatörens PDL.</span><span class="sxs-lookup"><span data-stu-id="b44bc-114">The storage location for a meeting chat is based on the PDL of the meeting organizer.</span></span>

<span data-ttu-id="b44bc-115">Du hittar den aktuella platsen för en användares Teams genom att [ansluta Teams PowerShell](/powershell/module/teams/connect-microsoftteams) och köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b44bc-115">To find the current location of a user's Teams data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a><span data-ttu-id="b44bc-116">Kanalmeddelanden</span><span class="sxs-lookup"><span data-stu-id="b44bc-116">Channel messages</span></span>

<span data-ttu-id="b44bc-117">Varje Microsoft 365 har en PDL (Preferred Data Location) som betecknar den geoplats där relaterade data ska lagras.</span><span class="sxs-lookup"><span data-stu-id="b44bc-117">Each Microsoft 365 group has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="b44bc-118">Teams använder PDL för gruppen som är kopplad till varje team för att avgöra var kanalmeddelandedata för teamet ska lagras.</span><span class="sxs-lookup"><span data-stu-id="b44bc-118">Teams uses the PDL for the group associated with each team to determine where to store channel messaging data for that team.</span></span> <span data-ttu-id="b44bc-119">Det omfattar chatt som sker i ett kanalmöte.</span><span class="sxs-lookup"><span data-stu-id="b44bc-119">This includes chat that occurs within a channel meeting.</span></span>

<span data-ttu-id="b44bc-120">När en användare skapar ett nytt team avgör den användarens PDL vilken PDL som ska Microsoft 365 gruppen.</span><span class="sxs-lookup"><span data-stu-id="b44bc-120">When a user creates a new team, that user's PDL determines what PDL is assigned to the Microsoft 365 group.</span></span> <span data-ttu-id="b44bc-121">Grupp-PDL avgör var gruppens data lagras.</span><span class="sxs-lookup"><span data-stu-id="b44bc-121">The group PDL determines where that team's data is stored.</span></span> <span data-ttu-id="b44bc-122">Om användarens PDL ändras senare ändras inte gruppens PDL.</span><span class="sxs-lookup"><span data-stu-id="b44bc-122">If that user's PDL later changes, the group's PDL is not changed.</span></span>

<span data-ttu-id="b44bc-123">Om en administratör lägger till eller ändrar PDL för den Microsoft 365-grupp som har stöd för ett team, läggs teamets kanalmeddelandedata till i en migreringskö som ska flyttas till den angivna geoplatsen.</span><span class="sxs-lookup"><span data-stu-id="b44bc-123">For existing teams, if an administrator adds or modifies the PDL for the Microsoft 365 group that backs a team, that team's channel messaging data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="b44bc-124">Om du ändrar PDF-Microsoft 365 för gruppen köar Teams data som ska migreras till den valda platsen.</span><span class="sxs-lookup"><span data-stu-id="b44bc-124">Changing the PDL of the Microsoft 365 group queues the Teams data to migrate to the chosen location.</span></span> <span data-ttu-id="b44bc-125">Men det migrerar inte automatiskt den SharePoint eller de filer som är associerade med gruppen.</span><span class="sxs-lookup"><span data-stu-id="b44bc-125">However, this does not migrate the SharePoint site or files associated with the Group automatically.</span></span> <span data-ttu-id="b44bc-126">Du måste flytta webbplatsen separat genom att följa procedurerna i Flytta [en SharePoint till en annan geoplats.](/microsoft-365/enterprise/move-sharepoint-between-geo-locations)</span><span class="sxs-lookup"><span data-stu-id="b44bc-126">You must move the site separately by following the procedures in [Move a SharePoint site to a different geo location](/microsoft-365/enterprise/move-sharepoint-between-geo-locations).</span></span> <span data-ttu-id="b44bc-127">Se till att göra båda stegen för att Teams data och SharePoint för en grupp på olika platser.</span><span class="sxs-lookup"><span data-stu-id="b44bc-127">Be sure to do both steps to avoid Teams data and SharePoint data for one group in different locations.</span></span>

<span data-ttu-id="b44bc-128">För att hitta den aktuella platsen för ett teams data [ansluter du till Teams PowerShell](/powershell/module/teams/connect-microsoftteams) och kör följande kommando:</span><span class="sxs-lookup"><span data-stu-id="b44bc-128">To find the current location of a team's data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a><span data-ttu-id="b44bc-129">Användarupplevelse</span><span class="sxs-lookup"><span data-stu-id="b44bc-129">User Experience</span></span>

<span data-ttu-id="b44bc-130">Teams Multi-Geo är sömlös för slutanvändaren.</span><span class="sxs-lookup"><span data-stu-id="b44bc-130">Teams Multi-Geo is seamless to the end user.</span></span> <span data-ttu-id="b44bc-131">När du ändrar PDL för en användare eller grupp köas respektive data för migreringen och migreringen sker automatiskt utan att påverka användaren eller deras Teams-klient även om de är aktiva medan migreringen sker.</span><span class="sxs-lookup"><span data-stu-id="b44bc-131">Once you change the PDL of a user or a group, the respective data will queue for migration and the migration will occur automatically with no impact to the user or their Teams client even if they are active while the migration occurs.</span></span>

## <a name="see-also"></a><span data-ttu-id="b44bc-132">Mer information finns även i</span><span class="sxs-lookup"><span data-stu-id="b44bc-132">See also</span></span>

[<span data-ttu-id="b44bc-133">Microsoft 365 Konfiguration för flera geoklienter</span><span class="sxs-lookup"><span data-stu-id="b44bc-133">Microsoft 365 Multi-Geo tenant configuration</span></span>](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[<span data-ttu-id="b44bc-134">Administrera en Multi-Geo-Miljö</span><span class="sxs-lookup"><span data-stu-id="b44bc-134">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="b44bc-135">Administrera Exchange Online postlådor i en miljö med flera geografiska miljöer</span><span class="sxs-lookup"><span data-stu-id="b44bc-135">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
