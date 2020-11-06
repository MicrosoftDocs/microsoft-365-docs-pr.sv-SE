---
title: Multi-geo-funktioner i OneDrive och SharePoint Online
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
description: Utöka din Microsoft 365-närvaro till flera geografiska regioner med flera geo-funktioner i OneDrive online.
ms.openlocfilehash: 84abfc01d5073889e998347f58d4a3e8bb29ea33
ms.sourcegitcommit: 5a355bde865369f64ea1788a378da23c65b1d249
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2020
ms.locfileid: "48930183"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a><span data-ttu-id="9ccbf-103">Multi-geo-funktioner i OneDrive och SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="9ccbf-103">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>

<span data-ttu-id="9ccbf-104">Multi-geo-funktioner i OneDrive och SharePoint Online möjliggör kontroll över det land eller den region där delade resurser som SharePoint-gruppwebbplatser och Microsoft 365-grupppost lådor lagras på resten.</span><span class="sxs-lookup"><span data-stu-id="9ccbf-104">Multi-Geo capabilities in OneDrive and SharePoint Online enables control of the country or region where shared resources like SharePoint team sites and Microsoft 365 Group mailboxes are stored at rest.</span></span>

<span data-ttu-id="9ccbf-105">Varje användare, grupp post låda och SharePoint-webbplats har en önskad data plats (PDL) som anger den Geo-plats där relaterade data ska lagras.</span><span class="sxs-lookup"><span data-stu-id="9ccbf-105">Each user, Group mailbox, and SharePoint site has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="9ccbf-106">Användares person uppgifter (Exchange-postlåda och OneDrive) tillsammans med alla Microsoft 365-grupper eller SharePoint-webbplatser som de skapar kan lagras på angiven Geo-plats för att uppfylla data de kraven.</span><span class="sxs-lookup"><span data-stu-id="9ccbf-106">Users' personal data (Exchange mailbox and OneDrive) along with any Microsoft 365 Groups or SharePoint sites that they create can be stored in the specified geo location to meet data residency requirements.</span></span> <span data-ttu-id="9ccbf-107">Du kan [ange olika administratörer för varje Geo-plats](add-a-sharepoint-geo-admin.md).</span><span class="sxs-lookup"><span data-stu-id="9ccbf-107">You can [specify different administrators for each geo location](add-a-sharepoint-geo-admin.md).</span></span>

<span data-ttu-id="9ccbf-108">Användarna får en sömlös upplevelse när de använder Microsoft 365-tjänster, inklusive Office-program, OneDrive och sökning.</span><span class="sxs-lookup"><span data-stu-id="9ccbf-108">Users get a seamless experience when using Microsoft 365 services, including Office applications, OneDrive, and Search.</span></span> <span data-ttu-id="9ccbf-109">Mer information finns [i användar miljön i en multi-geo-miljö](multi-geo-user-experience.md) .</span><span class="sxs-lookup"><span data-stu-id="9ccbf-109">See [User experience in a multi-geo environment](multi-geo-user-experience.md) for details.</span></span>

## <a name="onedrive"></a><span data-ttu-id="9ccbf-110">OneDrive</span><span class="sxs-lookup"><span data-stu-id="9ccbf-110">OneDrive</span></span>

<span data-ttu-id="9ccbf-111">Varje användares OneDrive kan etableras i eller [flyttas av en administratör](move-onedrive-between-geo-locations.md) till en satellit plats i enlighet med användarens PDL.</span><span class="sxs-lookup"><span data-stu-id="9ccbf-111">Each user's OneDrive can be provisioned in or [moved by an administrator](move-onedrive-between-geo-locations.md) to a satellite location in accordance with the user's PDL.</span></span> <span data-ttu-id="9ccbf-112">Personliga filer behålls i den geo platsen, även om de kan delas med användarna på andra geo platser.</span><span class="sxs-lookup"><span data-stu-id="9ccbf-112">Personal files are then kept in that geo location, though they can be shared with users in other geo locations.</span></span>

## <a name="sharepoint-sites-and-groups"></a><span data-ttu-id="9ccbf-113">SharePoint-webbplatser och-grupper</span><span class="sxs-lookup"><span data-stu-id="9ccbf-113">SharePoint Sites and Groups</span></span>

<span data-ttu-id="9ccbf-114">Hanteringen av multi-geo-funktionen är tillgänglig via administrations centret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9ccbf-114">Management of the Multi-Geo feature is available through the SharePoint admin center.</span></span> <span data-ttu-id="9ccbf-115">Detaljerad information finns i [motsvarande blogg inlägg](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).</span><span class="sxs-lookup"><span data-stu-id="9ccbf-115">Detailed information can be found in the [corresponding blog post](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302).</span></span>

<span data-ttu-id="9ccbf-116">När en användare skapar en SharePoint-gruppansluten webbplats i en multi-geo-miljö används deras PDL för att bestämma den Geo-plats där webbplatsen och dess tillhör ande grupp post låda skapas.</span><span class="sxs-lookup"><span data-stu-id="9ccbf-116">When a user creates a SharePoint group-connected site in a multi-geo environment, their PDL is used to determine the geo location where the site and its associated Group mailbox is created.</span></span> <span data-ttu-id="9ccbf-117">(Om användarens PDL-värde inte har ställts in, eller har ställts in på Geo-platsen som inte har kon figurer ATS som en satellit plats, skapas webbplatsen och post lådan på den centrala platsen.)</span><span class="sxs-lookup"><span data-stu-id="9ccbf-117">(If the user's PDL value hasn't been set, or has been set to geo location that hasn't been configured as a satellite location, then the site and mailbox are created in the central location.)</span></span>

<span data-ttu-id="9ccbf-118">Microsoft 365-tjänster som inte är Exchange, OneDrive och SharePoint är inte Multi-geo.</span><span class="sxs-lookup"><span data-stu-id="9ccbf-118">Microsoft 365 services other than Exchange, OneDrive, and SharePoint are not Multi-Geo.</span></span> <span data-ttu-id="9ccbf-119">Men Microsoft 365-grupper som skapas av de här tjänsterna stämplas med den som har skapat den och Exchange-gruppwebbplatsen och SharePoint O365-grupp webbplatsen som tillhandahålls i motsvarande geo.</span><span class="sxs-lookup"><span data-stu-id="9ccbf-119">However, Microsoft 365 Groups that are created by these services will be stamped with the PDL of the creator and their Exchange Group mailbox and SharePoint O365 Group Site provisioned in the corresponding geo.</span></span> 

## <a name="managing-the-multi-geo-environment"></a><span data-ttu-id="9ccbf-120">Hantera multi-geo-miljön</span><span class="sxs-lookup"><span data-stu-id="9ccbf-120">Managing the multi-geo environment</span></span>

<span data-ttu-id="9ccbf-121">Konfigurering och hantering av multi-geo-miljön sker via administrations centret för SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9ccbf-121">Setting up and managing your multi-geo environment is done through the SharePoint admin center.</span></span> 

![Skärm bild av sidan geo locations i administrations centret för SharePoint](../media/sharepoint-multi-geo-admin-center.png)

<span data-ttu-id="9ccbf-123">(Vissa åtgärder, till exempel att flytta en SharePoint-webbplats eller en OneDrive-webbplats, kräver Microsoft PowerShell.)</span><span class="sxs-lookup"><span data-stu-id="9ccbf-123">(Some actions, such as moving a SharePoint site or a OneDrive site require Microsoft PowerShell.)</span></span>

## <a name="see-also"></a><span data-ttu-id="9ccbf-124">Se även</span><span class="sxs-lookup"><span data-stu-id="9ccbf-124">See also</span></span>

[<span data-ttu-id="9ccbf-125">Multi-geo i SharePoint-och Microsoft 365-grupper</span><span class="sxs-lookup"><span data-stu-id="9ccbf-125">Multi-Geo in SharePoint and Microsoft 365 Groups</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[<span data-ttu-id="9ccbf-126">Administrera en Multi-Geo-Miljö</span><span class="sxs-lookup"><span data-stu-id="9ccbf-126">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="9ccbf-127">SharePoint-lagringslösningar i multi-geo-miljöer</span><span class="sxs-lookup"><span data-stu-id="9ccbf-127">SharePoint storage quotas in multi-geo environments</span></span>](sharepoint-multi-geo-storage-quota.md)

[<span data-ttu-id="9ccbf-128">Administrera Exchange Online-postlådor i en multi-geo-miljö</span><span class="sxs-lookup"><span data-stu-id="9ccbf-128">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
