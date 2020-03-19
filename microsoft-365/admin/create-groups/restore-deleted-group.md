---
title: Återställa en borttagen Office 365-grupp
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
description: Läs om hur du återställer en borttagen Office 365-grupp.
ms.openlocfilehash: 31d6481f87d7da219e042eefa8f004425caee133
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2020
ms.locfileid: "42808006"
---
# <a name="restore-a-deleted-office-365-group"></a>Återställa en borttagen Office 365-grupp

Om du har tagit bort en grupp behålls den i 30 dagar som standard. Denna 30-dagarsperiod anses vara en "soft-delete" eftersom du fortfarande kan återställa gruppen. Efter 30 dagar tas gruppen och dess associerade innehåll bort permanent och kan inte återställas.

När du återställer en grupp återställs följande innehåll:
  
- Azure Active Directory (AD) Office 365-grupper objekt, egenskaper och medlemmar.
    
- gruppens e-postadresser.
    
- Exchange Online delad inkorg och kalender.
    
- SharePoint Online-gruppwebbplats och -filer.
    
- OneNote-anteckningsbok
    
- Planner
    
- Lag

- Yammer-grupp- och gruppinnehåll (Om Office 365-gruppen skapades från Yammer)

## <a name="restore-a-group-that-you-own-by-using-outlook"></a>Återställa en grupp som du äger med Outlook

Om du äger en Office 365-grupp kan du återställa gruppen själv i Outlook genom att följa följande steg:

1. På [sidan Borttagna grupper](https://outlook.office.com/people/group/deleted)väljer du alternativet **Hantera grupper** under noden **Grupper** och väljer sedan **Borttaget**.
2. Klicka på fliken **Återställ** bredvid den grupp som du vill återställa.

Om den borttagna gruppen inte visas här kontaktar du en administratör.

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a>Återställa en grupp i administrationscentret för Microsoft 365

Om du är global administratör eller gruppadministratör kan du återställa en borttagen grupp i administrationscentret för Microsoft 365:

1. Gå till administrationscentret på [https://admin.microsoft.com](Go to the admin center at https://admin.microsoft.com).
2. Expandera **grupper**och klicka sedan på **Borttagna grupper**.
3. Markera den grupp som du vill återställa och klicka sedan på **Återställ grupp**.
  
## <a name="permanently-delete-an-office-365-group"></a>Ta bort en Office 365-grupp permanent

Ibland kanske du vill rensa en grupp permanent utan att vänta på att perioden för mjukborttagning på 30 dagar upphör att gälla. Starta PowerShell och kör det här kommandot för att ta fram gruppens objekt-ID
  
```
Get-AzureADMSDeletedGroup
```

Ta del av objekt-ID:t för gruppen eller grupperna som du vill ta bort permanent.
  
> [!CAUTION]
> Borttagningen av gruppen raderar gruppen och allt innehåll för alltid. 
  
Om du vill ta bort gruppen kör du det här kommandot i PowerShell
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

För att kontrollera att gruppen har tagits bort kör du cmdleten  *Get- AzureADMSDeletedGroup*  en gång till för att bekräfta att gruppen inte längre visas i listan över mjukt borttagna grupper. I vissa fall kan det ta upp till ett dygn för gruppen och allt innehåll att tas bort permanent. 
  
## <a name="got-questions-about-office-365-groups"></a>Har du frågor om Office 365-grupper?

Besök [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) för att ställa frågor och delta i konversationer om Office 365-grupper. 
  
## <a name="related-articles"></a>Relaterade artiklar

[Manage Office 365 Groups with PowerShell](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[Ta bort grupper med hjälp av cmdleten Remove-UnifiedGroup](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Hantera dina grupprelaterade gruppwebbplatsinställningar](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[Ta bort en grupp i Outlook](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
