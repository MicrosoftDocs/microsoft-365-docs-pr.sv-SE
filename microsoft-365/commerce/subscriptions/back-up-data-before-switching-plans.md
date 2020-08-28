---
title: Säkerhetskopiera data innan du ändrar abonnemang
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: a1da52c9-2167-4973-9e6d-492314a79b87
description: Säkerhetskopiera Outlook, OneDrive, Yammer och SharePoint-innehåll innan du ändrar Microsoft 365-abonnemang.
ms.openlocfilehash: 1158a98fc35c586ae900ef64579b52b9d64a85e6
ms.sourcegitcommit: 89b2ad0793c68415f178b8792a9757b9448345a6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/28/2020
ms.locfileid: "47294723"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Säkerhetskopiera data innan du byter Microsoft 365 för företag-abonnemang

Om en användare byter till ett annat abonnemang med färre datarelaterade tjänster eller om en användare lämnar organisationen, kan en kopia av sina data som lagras i Microsoft 365 hämtas innan de flyttas till det nya abonnemanget.

Om du flyttar en användare till en prenumeration som har samma eller fler tjänster behöver du inte säkerhetskopiera användar data. Se [flytta användare till ett annat abonnemang](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/move-users-different-subscription).
  
## <a name="save-a-copy-of-outlook-information"></a>Spara en kopia av Outlook-information

Om användarna har Outlook kan de [Exportera eller säkerhetskopiera e-post, kontakter och kalender till en Outlook. PST-fil](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) innan deras abonnemang sätts.
  
När du har växlat till det nya abonnemanget kan användarna [Importera e-post, kontakter och kalender från en Outlook. PST-fil](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac).
  
## <a name="save-files-stored-in-onedrive-for-business"></a>Spara filer som lagras i OneDrive för företag

Innan användare byter till ett annat abonnemang kan de [Ladda ned filer och mappar från OneDrive eller SharePoint](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) till en annan plats, till exempel en mapp på datorns hård disk eller en fil resurs i organisationens nätverk.
  
## <a name="save-yammer-information"></a>Spara Yammer-information

Administratörer kan exportera alla meddelanden, anteckningar, filer, ämnen, användare och grupper till en .zip-fil. Mer information finns i [Exportera data från Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data). Utvecklare kan även använda [Yammer API](https://go.microsoft.com/fwlink/p/?linkid=842495) för att göra detta.
  
## <a name="how-to-save-sharepoint-information"></a>Spara SharePoint-information

Om en användare byter från en prenumeration som har SharePoint Online till ett som inte har den visas inte **SharePoint** -panelen i Microsoft 365-menyn.
  
Så länge den nya prenumerationen är inom samma organisation som de har bytt från kan användaren fortfarande se SharePoint-gruppwebbplatsen. De kan visa och uppdatera anteckningsböcker, dokument, uppgifter och kalendrar med hjälp av direktlänkarna på gruppwebbplatsen.
  
> [!TIP]
> Vi rekommenderar att sådana användare går till gruppwebbplatsen innan prenumerationen byts ut och sparar webbadressen som en favorit eller ett bokmärke i webbläsaren.
  
Som standard har webbadressen till gruppwebbplatser följande format:
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

var  _\<orgDomain\>_ finns organisationens URL-adress.
  
Om domänen för organisationen till exempel är contoso.onmicrosoft.com så skulle direktadressen till gruppwebbplatsen vara https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx.
  
Användare kan förstås också ladda ned SharePoint Online-dokument från SharePoint-gruppwebbplatsen till en lokal dator eller annan plats när som helst.
