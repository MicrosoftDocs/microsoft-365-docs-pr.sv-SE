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
ms.openlocfilehash: 8fb2cb3afdf390efae7854a040bb56df731cceaf
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307193"
---
# <a name="restore-a-deleted-group"></a>Återställa en borttagen grupp

::: moniker range="o365-21vianet"

> [!NOTE]
> Administrationscentret förändras. Om dina erfarenheter inte överensstämmer med uppgifterna som visas här kan du läsa mer i [Om det nya administrationscentret för Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Om du har tagit bort en grupp sparas den i 30 dagar som standard. Denna 30-dagars period anses vara "mjuk borttagning" eftersom du fortfarande kan återställa gruppen. Efter 30 dagar tas gruppen och dess tillhör ande innehåll bort permanent och kan inte återställas.

När du återställer en grupp återställs följande innehåll:
  
- Azure Active Directory (AD) Microsoft 365 grupperar objekt, egenskaper och medlemmar.
    
- Gruppens e-postadresser.
    
- Delad inkorg och kalender för Exchange Online.
    
- SharePoint Online-gruppwebbplats och-filer.
    
- OneNote-anteckningsbok
    
- Planner
    
- Teams

- Grupp-och grupp innehåll i Yammer (om Microsoft 365-gruppen skapades från Yammer)

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a>Återställa en grupp som du äger med hjälp av Outlook på webben

Om du är ägare till en Microsoft 365-grupp kan du återställa gruppen själv i Outlook på webben genom att följa de här stegen:

1. Välj alternativet **hantera grupper** under noden **grupper** på [sidan borttagna grupper](https://outlook.office.com/people/group/deleted)och välj sedan **Borttaget**.

2. Klicka på fliken **Återställ** bredvid den grupp du vill återställa.

Om den borttagna gruppen inte visas här kan du kontakta en administratör.

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a>Återställa en grupp i administrations centret för Microsoft 365

Om du är global administratör eller administratör för administratörer kan du återställa en borttagen grupp i administrations centret för Microsoft 365:

1. Gå till [administrations centret](https://admin.microsoft.com).
2. Expandera **grupper**och klicka sedan på **borttagna grupper**.
3. Markera den grupp du vill återställa och klicka sedan på **Återställ grupp**.

> [!NOTE]
> I vissa fall kan det ta så lång tid som 24 timmar för gruppen och alla dess data att återställas. 
  
## <a name="permanently-delete-a-microsoft-365-group"></a>Ta bort en Microsoft 365-grupp permanent

Ibland kanske du vill ta bort en grupp permanent utan att vänta på att den 30 dagars borttagnings perioden upphör att gälla. Starta PowerShell och kör det här kommandot för att ta fram gruppens objekt-ID
  
```
Get-AzureADMSDeletedGroup
```

Anteckna objekt-ID: t för gruppen som du vill ta bort permanent.
  
> [!CAUTION]
> Borttagningen av gruppen raderar gruppen och allt innehåll för alltid. 
  
Om du vill ta bort gruppen kör du det här kommandot i PowerShell
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

För att kontrollera att gruppen har tagits bort kör du cmdleten  *Get- AzureADMSDeletedGroup*  en gång till för att bekräfta att gruppen inte längre visas i listan över mjukt borttagna grupper. I vissa fall kan det ta upp till ett dygn för gruppen och allt innehåll att tas bort permanent. 
  
## <a name="got-questions-about-microsoft-365-groups"></a>Har du frågor om Microsoft 365-grupper?

Besök [Microsofts Tech-community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) för att publicera frågor och delta i konversationer om Microsoft 365-grupper. 
  
## <a name="related-articles"></a>Relaterade artiklar

[Hantera Microsoft 365-grupper med PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[Ta bort grupper med hjälp av cmdleten Remove-UnifiedGroup](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Hantera dina grupprelaterade gruppwebbplatsinställningar](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Ta bort en grupp i Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
