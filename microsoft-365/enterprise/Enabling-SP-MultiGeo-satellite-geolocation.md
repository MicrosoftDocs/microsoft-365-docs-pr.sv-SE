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
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a>Aktivera SharePoint Multi-Geo på din satelits geo-plats

Den här artikeln är till för globala administratörer eller SharePoint-administratörer som har skapat en fler geo satellitplats innan **SharePoint Multi-Geo-funktioner** blev allmänt tillgängliga den 27 mars 2019 och som inte har aktiverat SharePoint Multi-Geo på sina satellitgeoplatser. 

>[!Note]
>Om du har lagt till en ny geoplats efter **den 27** mars behöver du inte utföra de här instruktionerna eftersom din nya geoplats redan är aktiverad för OneDrive och SharePoint Multi-Geo.

Med de här instruktionerna kan du aktivera SharePoint på din satellitplats, så att dina användare av flera satellitanvändare kan dra nytta av både OneDrive- och SharePoint Multi-Geo-funktionerna i O365. 

>[!IMPORTANT]
>Observera att det här är ett sätt att aktivera. När du har angett SPO-läge kan du inte återställa klientorganisationen till OneDrive Multi-Geo-läge utan eskalering med support. 

## <a name="to-set-a-geo-location-into-spo-mode"></a>Så här ställer du in en geoplats i SPO-läge

Om du vill ange en geoplats i SPO-läge ansluter du till den geoplats du vill ställa in i SPO-läge:

1.    Öppna SharePoint Online Management Shell 
2.    Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential
3.    Set-SPOMultiGeoExperience</br></br>
![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)
4.    Den här åtgärden tar vanligtvis ungefär en timme medan vi utför olika publiceringar i tjänsten och stämpla klientorganisationen igen. Efter minst 1 timme bör du utföra en Get-SPOMultiGeoExperience.  Det visar om den här geoplatsen är i SPO-läge.</br></br>
![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)

 
 
 
>[!Note]
>Vissa cacheminnen i tjänsten uppdateras en gång per dygn, så det är möjligt att din satellit geo ibland fungerar som om den fortfarande var i ODB-läge under en period på upp till 24 timmar. Det här orsakar inga tekniska problem. 
 
Mer information om SharePoint Multi-Geo finns i [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)


