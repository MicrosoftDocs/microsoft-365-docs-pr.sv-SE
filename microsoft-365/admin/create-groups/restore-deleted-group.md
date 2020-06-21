---
title: Återställa en borttagen grupp
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Lär dig hur du återställer en borttagen Microsoft 365-grupp.
ms.openlocfilehash: d7cf548816af1661298458f27c704d654845075d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818513"
---
# <a name="restore-a-deleted-group"></a>Återställa en borttagen grupp

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Om du har tagit bort en grupp behålls den som standard i 30 dagar. Den här 30-dagarsperioden anses vara en "mjuk borttagning" eftersom du fortfarande kan återställa gruppen. Efter 30 dagar tas gruppen och dess associerade innehåll bort permanent och kan inte återställas.

När du återställer en grupp återställs följande innehåll:
  
- Azure Active Directory (AD) Microsoft 365 Grupper objekt, egenskaper och medlemmar.
    
- gruppens e-postadresser.
    
- Exchange Online delad inkorg och kalender.
    
- SharePoint Online-gruppwebbplats och -filer.
    
- OneNote-anteckningsbok
    
- Planner
    
- Teams

- Yammer-grupp- och gruppinnehåll (Om Microsoft 365-gruppen skapades från Yammer)

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a>Återställa en grupp som du äger med Outlook på webben

Om du äger en Microsoft 365-grupp kan du återställa gruppen själv i Outlook på webben genom att följa dessa steg:

1. På [sidan Borttagna grupper](https://outlook.office.com/people/group/deleted)väljer du alternativet **Hantera grupper** under noden **Grupper** och väljer sedan **Borttaget**.

2. Klicka på fliken **Återställ** bredvid den grupp som du vill återställa.

Om den borttagna gruppen inte visas här kontaktar du en administratör.

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a>Återställa en grupp i administrationscentret för Microsoft 365

Om du är global administratör eller gruppadministratör kan du återställa en borttagen grupp i microsoft 365-administrationscentret:

1. Gå till [administrationscentret](https://admin.microsoft.com).
2. Expandera **grupper**och klicka sedan på **Borttagna grupper**.
3. Markera den grupp som du vill återställa och klicka sedan på **Återställ grupp**.

> [!NOTE]
> I vissa fall kan det ta upp till 24 timmar innan gruppen och alla dess data återställs. 
  
## <a name="permanently-delete-a-microsoft-365-group"></a>Ta bort en Microsoft 365-grupp permanent

Ibland kanske du vill rensa en grupp permanent utan att vänta på att 30-dagarssperiod för mjuk borttagning ska löpa ut. Starta PowerShell och kör det här kommandot för att ta fram gruppens objekt-ID
  
```
Get-AzureADMSDeletedGroup
```

Ta del av objekt-ID för gruppen, eller grupperna, som du vill ta bort permanent.
  
> [!CAUTION]
> Borttagningen av gruppen raderar gruppen och allt innehåll för alltid. 
  
Om du vill ta bort gruppen kör du det här kommandot i PowerShell
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted. 
  
## <a name="got-questions-about-microsoft-365-groups"></a>Har du frågor om Microsoft 365 Groups?

Besök [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) för att ställa frågor och delta i konversationer om Microsoft 365-grupper. 
  
## <a name="related-articles"></a>Relaterade artiklar

[Hantera Microsoft 365-grupper med PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)
  
[Ta bort grupper med hjälp av cmdleten Remove-UnifiedGroup](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Hantera dina grupprelaterade gruppwebbplatsinställningar](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Ta bort en grupp i Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
