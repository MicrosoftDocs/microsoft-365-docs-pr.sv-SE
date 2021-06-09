---
title: Aktivera SharePoint Multi-Geo på din satelits geo-plats
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Den här artikeln innehåller information för globala SharePoint administratörer om hur du aktiverar SharePoint Multi-Geo i satellitgeoplatser.
ms.openlocfilehash: 78f0e925a333dd48a6016bc749459b13e1ac21c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694890"
---
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a><span data-ttu-id="84a59-103">Aktivera SharePoint Multi-Geo på din satelits geo-plats</span><span class="sxs-lookup"><span data-stu-id="84a59-103">Enabling SharePoint Multi-Geo in your satellite geo location</span></span>

<span data-ttu-id="84a59-104">Den här artikeln är till för globala administratörer eller SharePoint-administratörer som har skapat en fler geo satellitplats innan **SharePoint Multi-Geo-funktioner** blev allmänt tillgängliga den 27 mars 2019 och som inte har aktiverat SharePoint Multi-Geo på sina satellitgeoplatser.</span><span class="sxs-lookup"><span data-stu-id="84a59-104">This article is for Global or SharePoint administrators who have created a Multi-Geo satellite location **before** SharePoint Multi-Geo capabilities became generally available on March 27, 2019, and who have not enabled SharePoint Multi-Geo in their satellite geo location(s).</span></span> 

>[!Note]
><span data-ttu-id="84a59-105">Om du har lagt till en ny geoplats efter **den 27** mars behöver du inte utföra de här instruktionerna eftersom din nya geoplats redan är aktiverad för OneDrive och SharePoint Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="84a59-105">If you have added a new geo location **after March 27th**, you do not need to perform these instructions, as your new geo location will already be enabled for OneDrive and SharePoint Multi-Geo.</span></span>

<span data-ttu-id="84a59-106">Med de här instruktionerna kan du aktivera SharePoint på din satellitplats, så att dina användare av flera satellitanvändare kan dra nytta av både OneDrive- och SharePoint Multi-Geo-funktionerna i O365.</span><span class="sxs-lookup"><span data-stu-id="84a59-106">These instructions will allow you to enable SharePoint in your satellite location, so your Multi-Geo satellite users can take advantage of both OneDrive and SharePoint Multi-Geo capabilities in O365.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="84a59-107">Observera att det här är ett sätt att aktivera.</span><span class="sxs-lookup"><span data-stu-id="84a59-107">Please note that this is a one way enablement.</span></span> <span data-ttu-id="84a59-108">När du har angett SPO-läge kan du inte återställa klientorganisationen till OneDrive Multi-Geo-läge utan eskalering med support.</span><span class="sxs-lookup"><span data-stu-id="84a59-108">Once you set SPO mode, you will not be able to revert your tenant to OneDrive only Multi-Geo mode without an escalation with support.</span></span> 

## <a name="to-set-a-geo-location-into-spo-mode"></a><span data-ttu-id="84a59-109">Så här ställer du in en geoplats i SPO-läge</span><span class="sxs-lookup"><span data-stu-id="84a59-109">To set a geo location into SPO Mode</span></span>

<span data-ttu-id="84a59-110">Om du vill ange en geoplats i SPO-läge ansluter du till den geoplats du vill ställa in i SPO-läge:</span><span class="sxs-lookup"><span data-stu-id="84a59-110">To set a geo location into SPO mode, connect to the geo location you want to set in SPO Mode:</span></span>

1.    <span data-ttu-id="84a59-111">Öppna SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="84a59-111">Open your SharePoint Online Management Shell</span></span> 
2.    <span data-ttu-id="84a59-112">Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential</span><span class="sxs-lookup"><span data-stu-id="84a59-112">Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential</span></span>
3.    <span data-ttu-id="84a59-113">Set-SPOMultiGeoExperience</span><span class="sxs-lookup"><span data-stu-id="84a59-113">Set-SPOMultiGeoExperience</span></span></br></br>
<span data-ttu-id="84a59-114">![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)</span><span class="sxs-lookup"><span data-stu-id="84a59-114">![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)</span></span>
4.    <span data-ttu-id="84a59-115">Den här åtgärden tar vanligtvis ungefär en timme medan vi utför olika publiceringar i tjänsten och stämpla klientorganisationen igen.</span><span class="sxs-lookup"><span data-stu-id="84a59-115">This operation usually takes about an hour while we perform various publish backs in the service and re-stamp your tenant.</span></span> <span data-ttu-id="84a59-116">Efter minst 1 timme bör du utföra en Get-SPOMultiGeoExperience.</span><span class="sxs-lookup"><span data-stu-id="84a59-116">After at least 1 hour, please perform a Get-SPOMultiGeoExperience.</span></span>  <span data-ttu-id="84a59-117">Det visar om den här geoplatsen är i SPO-läge.</span><span class="sxs-lookup"><span data-stu-id="84a59-117">This will show you whether this geo location is in SPO mode.</span></span></br></br>
<span data-ttu-id="84a59-118">![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)</span><span class="sxs-lookup"><span data-stu-id="84a59-118">![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)</span></span>

 
 
 
>[!Note]
><span data-ttu-id="84a59-119">Vissa cacheminnen i tjänsten uppdateras en gång per dygn, så det är möjligt att din satellit geo ibland fungerar som om den fortfarande var i ODB-läge under en period på upp till 24 timmar.</span><span class="sxs-lookup"><span data-stu-id="84a59-119">Certain caches in the service update every 24 hours, so it is possible that for a period of up to 24 hours, your satellite geo may intermittently behave as if it was still in ODB mode.</span></span> <span data-ttu-id="84a59-120">Det här orsakar inga tekniska problem.</span><span class="sxs-lookup"><span data-stu-id="84a59-120">This does not cause any technical issues.</span></span> 
 
<span data-ttu-id="84a59-121">Mer information om SharePoint Multi-Geo finns i [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="84a59-121">For additional information regarding SharePoint Multi-Geo, please refer to [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)</span></span>


