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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Lär dig hur du återställer en borttagen Microsoft 365-grupp.
ms.openlocfilehash: 9d432d6ddb7e41b6560329b562c24f392a424412
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140530"
---
# <a name="restore-a-deleted-group"></a>Återställa en borttagen grupp

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om din upplevelse inte stämmer överens med informationen som presenteras här läser du [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Om du har tagit bort en grupp behålls den som standard i 30 dagar. Denna 30-dagarsperiod anses vara en "mjuk borttagning" eftersom du fortfarande kan återställa gruppen. Efter 30 dagar tas gruppen och dess associerade innehåll bort permanent och kan inte återställas.

När du återställer en grupp återställs följande innehåll:
  
- Azure Active Directory (AD) Microsoft 365 Groups-objekt, egenskaper och medlemmar.
    
- gruppens e-postadresser.
    
- Exchange Online delad inkorg och kalender.
    
- SharePoint Online-gruppwebbplats och -filer.
    
- OneNote-anteckningsbok
    
- Planner
    
- Teams

- Yammer-grupp- och gruppinnehåll (Om Microsoft 365-gruppen skapades från Yammer)

## <a name="restore-a-group-that-you-own-by-using-outlook"></a>Återställa en grupp som du äger med Outlook

Om du äger en Microsoft 365-grupp kan du återställa gruppen själv i Outlook genom att följa följande:

1. På [sidan Borttagna grupper](https://outlook.office.com/people/group/deleted)väljer du alternativet **Hantera grupper** under noden **Grupper** och väljer sedan **Borttaget**.

2. Klicka på fliken **Återställ** bredvid den grupp som du vill återställa.

Om den borttagna gruppen inte visas här kontaktar du en administratör.

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a>Återställa en grupp i administrationscentret för Microsoft 365

Om du är global administratör eller gruppadministratör kan du återställa en borttagen grupp i microsoft 365-administrationscentret:

1. Gå till [administrationscentret](https://admin.microsoft.com).
2. Expandera **grupper**och klicka sedan på **Borttagna grupper**.
3. Markera den grupp som du vill återställa och klicka sedan på **Återställ grupp**.
  
## <a name="permanently-delete-a-microsoft-365-group"></a>Ta bort en Microsoft 365-grupp permanent

Ibland kanske du vill rensa en grupp permanent utan att vänta på att 30-dagars perioden för mjuk borttagning ska löpa ut. Starta PowerShell och kör det här kommandot för att ta fram gruppens objekt-ID
  
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

För att kontrollera att gruppen har tagits bort kör du cmdleten  *Get- AzureADMSDeletedGroup*  en gång till för att bekräfta att gruppen inte längre visas i listan över mjukt borttagna grupper. I vissa fall kan det ta upp till ett dygn för gruppen och allt innehåll att tas bort permanent. 
  
## <a name="got-questions-about-microsoft-365-groups"></a>Har du frågor om Microsoft 365 Groups?

Besök [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) för att ställa frågor och delta i konversationer om Microsoft 365-grupper. 
  
## <a name="related-articles"></a>Relaterade artiklar

[Hantera Microsoft 365-grupper med PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)
  
[Ta bort grupper med hjälp av cmdleten Remove-UnifiedGroup](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Hantera dina grupprelaterade gruppwebbplatsinställningar](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[Ta bort en grupp i Outlook](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
