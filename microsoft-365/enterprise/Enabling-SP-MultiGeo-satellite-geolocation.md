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
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a>Aktivera SharePoint multi-geo på din satellit geografiska plats

Den här artikeln gäller för globala eller SharePoint-administratörer som har skapat en plats med flera geobaserade satelliter **innan** SharePoint multi-geo-funktioner blev allmänt tillgängliga den 27 mars 2019 och som inte har aktiverat SharePoint multi-geo på sina satellit geo-platser. 

>[!Note]
>Om du har lagt till en ny Geo-plats **efter mars 27**behöver du inte utföra de här instruktionerna eftersom den nya geo-platsen redan är aktive rad för OneDrive och SharePoint multi-geo.

Med hjälp av de här anvisningarna kan du aktivera SharePoint på din satellit plats, så att dina användare med flera geo-satelliter utnyttjar både OneDrive och SharePoint multi-geo-funktioner i O365. 

>[!IMPORTANT]
>Observera att detta är ett enkelriktat sätt. När du har angett SPO-läget kan du inte återställa din klient organisation till OneDrive i bara flera lägen utan att det finns stöd för det. 

## <a name="to-set-a-geo-location-into-spo-mode"></a>Ange en Geo-plats i SPO-läge

Om du vill ange en Geo-plats i SPO-läge ansluter du till den Geo-plats som du vill ange i SPO-läge:

1.    Öppna SharePoint Online Management Shell 
2.    Connect-SPOService-URL "https://$tenantGeo-admin.sharepoint.com"-Credential $credential
3.    Set-SPOMultiGeoExperience</br></br>
![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)
4.    Det tar vanligt vis ungefär en timme innan vi utför olika publiceringar av den här tjänsten och omstämpla din klient organisation. Efter minst 1 timme utför du en get-SPOMultiGeoExperience.  Då visas om den här geo-platsen är i SPO-läge.</br></br>
![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)

 
 
 
>[!Note]
>Vissa cacheminnen i tjänst uppdateringen var 24: e timme, så det kan hända att din satellit med upp till 24 timmar fungerar som om den fortfarande är i SYNKRONISERINGSREPARATION-läge. Detta orsakar inga tekniska problem. 
 
Mer information om SharePoint multi-geo finns i [aka.MS/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)


