---
title: Aktivera SharePoint multi-geo på din satellit geografiska plats
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
description: I den här artikeln finns information för globala eller SharePoint-administratörer om aktivering av SharePoint multi-geo på Geo-platser med satellit.
ms.openlocfilehash: 78f0e925a333dd48a6016bc749459b13e1ac21c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694890"
---
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a><span data-ttu-id="17b44-103">Aktivera SharePoint multi-geo på din satellit geografiska plats</span><span class="sxs-lookup"><span data-stu-id="17b44-103">Enabling SharePoint Multi-Geo in your satellite geo location</span></span>

<span data-ttu-id="17b44-104">Den här artikeln gäller för globala eller SharePoint-administratörer som har skapat en plats med flera geobaserade satelliter **innan** SharePoint multi-geo-funktioner blev allmänt tillgängliga den 27 mars 2019 och som inte har aktiverat SharePoint multi-geo på sina satellit geo-platser.</span><span class="sxs-lookup"><span data-stu-id="17b44-104">This article is for Global or SharePoint administrators who have created a Multi-Geo satellite location **before** SharePoint Multi-Geo capabilities became generally available on March 27, 2019, and who have not enabled SharePoint Multi-Geo in their satellite geo location(s).</span></span> 

>[!Note]
><span data-ttu-id="17b44-105">Om du har lagt till en ny Geo-plats **efter mars 27**behöver du inte utföra de här instruktionerna eftersom den nya geo-platsen redan är aktive rad för OneDrive och SharePoint multi-geo.</span><span class="sxs-lookup"><span data-stu-id="17b44-105">If you have added a new geo location **after March 27th**, you do not need to perform these instructions, as your new geo location will already be enabled for OneDrive and SharePoint Multi-Geo.</span></span>

<span data-ttu-id="17b44-106">Med hjälp av de här anvisningarna kan du aktivera SharePoint på din satellit plats, så att dina användare med flera geo-satelliter utnyttjar både OneDrive och SharePoint multi-geo-funktioner i O365.</span><span class="sxs-lookup"><span data-stu-id="17b44-106">These instructions will allow you to enable SharePoint in your satellite location, so your Multi-Geo satellite users can take advantage of both OneDrive and SharePoint Multi-Geo capabilities in O365.</span></span> 

>[!IMPORTANT]
><span data-ttu-id="17b44-107">Observera att detta är ett enkelriktat sätt.</span><span class="sxs-lookup"><span data-stu-id="17b44-107">Please note that this is a one way enablement.</span></span> <span data-ttu-id="17b44-108">När du har angett SPO-läget kan du inte återställa din klient organisation till OneDrive i bara flera lägen utan att det finns stöd för det.</span><span class="sxs-lookup"><span data-stu-id="17b44-108">Once you set SPO mode, you will not be able to revert your tenant to OneDrive only Multi-Geo mode without an escalation with support.</span></span> 

## <a name="to-set-a-geo-location-into-spo-mode"></a><span data-ttu-id="17b44-109">Ange en Geo-plats i SPO-läge</span><span class="sxs-lookup"><span data-stu-id="17b44-109">To set a geo location into SPO Mode</span></span>

<span data-ttu-id="17b44-110">Om du vill ange en Geo-plats i SPO-läge ansluter du till den Geo-plats som du vill ange i SPO-läge:</span><span class="sxs-lookup"><span data-stu-id="17b44-110">To set a geo location into SPO mode, connect to the geo location you want to set in SPO Mode:</span></span>

1.    <span data-ttu-id="17b44-111">Öppna SharePoint Online Management Shell</span><span class="sxs-lookup"><span data-stu-id="17b44-111">Open your SharePoint Online Management Shell</span></span> 
2.    <span data-ttu-id="17b44-112">Connect-SPOService-URL "https://$tenantGeo-admin.sharepoint.com"-Credential $credential</span><span class="sxs-lookup"><span data-stu-id="17b44-112">Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential</span></span>
3.    <span data-ttu-id="17b44-113">Set-SPOMultiGeoExperience</span><span class="sxs-lookup"><span data-stu-id="17b44-113">Set-SPOMultiGeoExperience</span></span></br></br>
<span data-ttu-id="17b44-114">![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)</span><span class="sxs-lookup"><span data-stu-id="17b44-114">![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)</span></span>
4.    <span data-ttu-id="17b44-115">Det tar vanligt vis ungefär en timme innan vi utför olika publiceringar av den här tjänsten och omstämpla din klient organisation.</span><span class="sxs-lookup"><span data-stu-id="17b44-115">This operation usually takes about an hour while we perform various publish backs in the service and re-stamp your tenant.</span></span> <span data-ttu-id="17b44-116">Efter minst 1 timme utför du en get-SPOMultiGeoExperience.</span><span class="sxs-lookup"><span data-stu-id="17b44-116">After at least 1 hour, please perform a Get-SPOMultiGeoExperience.</span></span>  <span data-ttu-id="17b44-117">Då visas om den här geo-platsen är i SPO-läge.</span><span class="sxs-lookup"><span data-stu-id="17b44-117">This will show you whether this geo location is in SPO mode.</span></span></br></br>
<span data-ttu-id="17b44-118">![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)</span><span class="sxs-lookup"><span data-stu-id="17b44-118">![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)</span></span>

 
 
 
>[!Note]
><span data-ttu-id="17b44-119">Vissa cacheminnen i tjänst uppdateringen var 24: e timme, så det kan hända att din satellit med upp till 24 timmar fungerar som om den fortfarande är i SYNKRONISERINGSREPARATION-läge.</span><span class="sxs-lookup"><span data-stu-id="17b44-119">Certain caches in the service update every 24 hours, so it is possible that for a period of up to 24 hours, your satellite geo may intermittently behave as if it was still in ODB mode.</span></span> <span data-ttu-id="17b44-120">Detta orsakar inga tekniska problem.</span><span class="sxs-lookup"><span data-stu-id="17b44-120">This does not cause any technical issues.</span></span> 
 
<span data-ttu-id="17b44-121">Mer information om SharePoint multi-geo finns i [aka.MS/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="17b44-121">For additional information regarding SharePoint Multi-Geo, please refer to [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)</span></span>


