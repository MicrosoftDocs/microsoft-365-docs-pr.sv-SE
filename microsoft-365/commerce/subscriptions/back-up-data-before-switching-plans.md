---
title: Lagra data innan du ändrar abonnemang
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
description: Säkerhetskopiera Outlook-, OneDrive-, Yammer- och SharePoint-innehåll innan du ändrar Microsoft 365-abonnemang.
ms.openlocfilehash: d29d4e739a9328a63a491696ba26bee5b1947f0a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924066"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Backa data innan du byter abonnemang för Microsoft 365 för företag

Om en användare byter till en annan prenumeration som har färre datarelaterade tjänster eller lämnar organisationen kan en kopia av de data som lagras i Microsoft 365 laddas ned innan de byter till den nya prenumerationen.

Om du flyttar en användare till en prenumeration som har samma eller flera tjänster behöver du inte backa upp användardata. Se [Flytta användare till en annan prenumeration](./move-users-different-subscription.md).
  
## <a name="save-a-copy-of-outlook-information"></a>Spara en kopia av Outlook-information

Om användarna har Outlook kan de exportera eller säkerhetskopiera e-post, kontakter och kalender till [en Outlook-fil (.pst)](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) innan de byter abonnemang.
  
När bytet till det nya abonnemanget är klart kan användarna [Importera e-post, kontakter och kalender från en PST-fil för Outlook.](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)
  
## <a name="save-files-stored-in-onedrive-for-business"></a>Spara filer som lagrats i OneDrive för företag

Innan användare byter till en annan prenumeration kan de ladda ned filer och mappar från OneDrive eller [SharePoint](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) till en annan plats, till exempel en mapp på datorns hårddisk eller en filresurs i organisationens nätverk.
  
## <a name="save-yammer-information"></a>Spara Yammer-information

Administratörer kan exportera alla meddelanden, anteckningar, filer, ämnen, användare och grupper till en .zip-fil. Mer information finns i [Exportera data från Yammer Enterprise.](/yammer/manage-security-and-compliance/export-yammer-enterprise-data) Utvecklare kan också använda [Yammer API](https://go.microsoft.com/fwlink/p/?linkid=842495) för att göra detta.
  
## <a name="how-to-save-sharepoint-information"></a>Spara SharePoint-information

Om en användare byter från en prenumeration som har SharePoint Online till en prenumeration som inte har det visas inte längre **SharePoint-panelen** i deras Microsoft 365-meny.
  
Så länge den nya prenumerationen är inom samma organisation som de har bytt från kan användaren fortfarande se SharePoint-gruppwebbplatsen. De kan visa och uppdatera anteckningsböcker, dokument, uppgifter och kalendrar med hjälp av direktlänkarna på gruppwebbplatsen.
  
> [!TIP]
> Vi rekommenderar att sådana användare går till gruppwebbplatsen innan prenumerationen byts ut och sparar webbadressen som en favorit eller ett bokmärke i webbläsaren.
  
Som standard har webbadressen till gruppwebbplatser följande format:
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

var  _\<orgDomain\>_ finns organisationens URL.
  
Om domänen för organisationen till exempel är contoso.onmicrosoft.com så skulle direktadressen till gruppwebbplatsen vara https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx.
  
Användare kan förstås också ladda ned SharePoint Online-dokument från SharePoint-gruppwebbplatsen till en lokal dator eller annan plats när som helst.