---
title: Multi-Geo Capabilities i OneDrive och SharePoint Online
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: Utöka din Microsoft 365 närvaro till flera geografiska områden med flera geofunktioner i OneDrive Online.
ms.openlocfilehash: 8f42b071abef0602304f1a468190c33700fe3e82
ms.sourcegitcommit: 321610fd312e5c54ae8a757a71ab0c9fd2f1ac03
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2020
ms.locfileid: "48995915"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a><span data-ttu-id="f69c2-103">Multi-Geo Capabilities i OneDrive och SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="f69c2-103">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>

<span data-ttu-id="f69c2-104">Multi-Geo capabilities in OneDrive and SharePoint Online enables control of shared resources like SharePoint team sites and Microsoft 365 Group mailboxes stored at rest in a country or region.</span><span class="sxs-lookup"><span data-stu-id="f69c2-104">Multi-Geo capabilities in OneDrive and SharePoint Online enables control of shared resources like SharePoint team sites and Microsoft 365 Group mailboxes stored at rest in a country or region.</span></span>

<span data-ttu-id="f69c2-105">Varje användare, grupppostlåda och SharePoint-webbplats har en PDL-plats (Preferred Data Location) som betecknar den geografiska plats där relaterade data ska lagras.</span><span class="sxs-lookup"><span data-stu-id="f69c2-105">Each user, Group mailbox, and SharePoint site has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="f69c2-106">Användarnas personliga data (Exchange-postlådan och OneDrive) tillsammans med eventuella Microsoft 365-grupper eller SharePoint-webbplatser som de skapar kan lagras på den angivna geoplatsen för att uppfylla krav på datalagring.</span><span class="sxs-lookup"><span data-stu-id="f69c2-106">Users' personal data (Exchange mailbox and OneDrive) along with any Microsoft 365 Groups or SharePoint sites that they create can be stored in the specified geo location to meet data residency requirements.</span></span> <span data-ttu-id="f69c2-107">Du kan [ange olika administratörer för varje geoplats.](add-a-sharepoint-geo-admin.md)</span><span class="sxs-lookup"><span data-stu-id="f69c2-107">You can [specify different administrators for each geo location](add-a-sharepoint-geo-admin.md).</span></span>

<span data-ttu-id="f69c2-108">Användarna får en smidig upplevelse när de Microsoft 365-tjänster, Office program, OneDrive och sökning.</span><span class="sxs-lookup"><span data-stu-id="f69c2-108">Users get a seamless experience when using Microsoft 365 services, including Office applications, OneDrive, and Search.</span></span> <span data-ttu-id="f69c2-109">Mer [information finns i Användarupplevelse i en geomiljö](multi-geo-user-experience.md) med flera miljön.</span><span class="sxs-lookup"><span data-stu-id="f69c2-109">See [User experience in a multi-geo environment](multi-geo-user-experience.md) for details.</span></span>

## <a name="onedrive"></a><span data-ttu-id="f69c2-110">OneDrive</span><span class="sxs-lookup"><span data-stu-id="f69c2-110">OneDrive</span></span>

<span data-ttu-id="f69c2-111">Varje användares OneDrive kan etableras i eller flyttas av en [administratör](move-onedrive-between-geo-locations.md) till en satellitplats i enlighet med användarens PDL.</span><span class="sxs-lookup"><span data-stu-id="f69c2-111">Each user's OneDrive can be provisioned in or [moved by an administrator](move-onedrive-between-geo-locations.md) to a satellite location in accordance with the user's PDL.</span></span> <span data-ttu-id="f69c2-112">Personliga filer sparas sedan på den geoplatsen, men de kan delas med användare på andra geoplatser.</span><span class="sxs-lookup"><span data-stu-id="f69c2-112">Personal files are then kept in that geo location, though they can be shared with users in other geo locations.</span></span>

## <a name="sharepoint-sites-and-groups"></a><span data-ttu-id="f69c2-113">SharePoint Webbplatser och grupper</span><span class="sxs-lookup"><span data-stu-id="f69c2-113">SharePoint Sites and Groups</span></span>

<span data-ttu-id="f69c2-114">Hantering av Multi-Geo-funktionen är tillgänglig via SharePoint administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="f69c2-114">Management of the Multi-Geo feature is available through the SharePoint admin center.</span></span> <span data-ttu-id="f69c2-115">Detaljerad information finns i [motsvarande blogginlägg.](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)</span><span class="sxs-lookup"><span data-stu-id="f69c2-115">Detailed information can be found in the [corresponding blog post](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).</span></span>

<span data-ttu-id="f69c2-116">När en användare skapar en SharePoint gruppansluten webbplats i en geomiljö används deras PDL för att fastställa den geografiska plats där webbplatsen och dess tillhörande grupppostlåda skapas.</span><span class="sxs-lookup"><span data-stu-id="f69c2-116">When a user creates a SharePoint group-connected site in a multi-geo environment, their PDL is used to determine the geo location where the site and its associated Group mailbox is created.</span></span> <span data-ttu-id="f69c2-117">(Om användarens PDL-värde inte har angetts, eller har angetts till en geoplats som inte har konfigurerats som en satellitplats, skapas webbplatsen och postlådan på den centrala platsen.)</span><span class="sxs-lookup"><span data-stu-id="f69c2-117">(If the user's PDL value hasn't been set, or has been set to geo location that hasn't been configured as a satellite location, then the site and mailbox are created in the central location.)</span></span>

<span data-ttu-id="f69c2-118">Microsoft 365 andra tjänster än Exchange, OneDrive och SharePoint inte är Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="f69c2-118">Microsoft 365 services other than Exchange, OneDrive, and SharePoint are not Multi-Geo.</span></span> <span data-ttu-id="f69c2-119">Men Microsoft 365 Grupper som skapas av dessa tjänster stämplas med PDL för skaparen och deras Exchange-grupppostlåda och SharePoint O365-gruppwebbplats etableras i motsvarande geo.</span><span class="sxs-lookup"><span data-stu-id="f69c2-119">However, Microsoft 365 Groups that are created by these services will be stamped with the PDL of the creator and their Exchange Group mailbox and SharePoint O365 Group Site provisioned in the corresponding geo.</span></span> 

## <a name="managing-the-multi-geo-environment"></a><span data-ttu-id="f69c2-120">Hantera multigeobaserade miljöer</span><span class="sxs-lookup"><span data-stu-id="f69c2-120">Managing the multi-geo environment</span></span>

<span data-ttu-id="f69c2-121">Du kan konfigurera och hantera din multigeobaserade miljö via SharePoint administrationscenter.</span><span class="sxs-lookup"><span data-stu-id="f69c2-121">Setting up and managing your multi-geo environment is done through the SharePoint admin center.</span></span> 

![Skärmbild av sidan geoplatser i SharePoint administrationscenter](../media/sharepoint-multi-geo-admin-center.png)

<span data-ttu-id="f69c2-123">(Vissa åtgärder, till exempel för att flytta SharePoint webbplats eller en OneDrive-webbplats, kräver Microsoft PowerShell.)</span><span class="sxs-lookup"><span data-stu-id="f69c2-123">(Some actions, such as moving a SharePoint site or a OneDrive site require Microsoft PowerShell.)</span></span>

## <a name="see-also"></a><span data-ttu-id="f69c2-124">Se även</span><span class="sxs-lookup"><span data-stu-id="f69c2-124">See also</span></span>

[<span data-ttu-id="f69c2-125">Multi-Geo i SharePoint och Microsoft 365 Grupper</span><span class="sxs-lookup"><span data-stu-id="f69c2-125">Multi-Geo in SharePoint and Microsoft 365 Groups</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[<span data-ttu-id="f69c2-126">Administrera en Multi-Geo-Miljö</span><span class="sxs-lookup"><span data-stu-id="f69c2-126">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="f69c2-127">SharePoint för flera geografiska miljöer</span><span class="sxs-lookup"><span data-stu-id="f69c2-127">SharePoint storage quotas in multi-geo environments</span></span>](sharepoint-multi-geo-storage-quota.md)

[<span data-ttu-id="f69c2-128">Administrera Exchange Online postlådor i en miljö med flera geografiska miljöer</span><span class="sxs-lookup"><span data-stu-id="f69c2-128">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
