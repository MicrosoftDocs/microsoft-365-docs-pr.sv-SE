---
title: Återställa en borttagna Microsoft 365 grupp
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: En borttagna grupp behålls i 30 dagar och du kan fortfarande återställa gruppen. Efter 30 dagar tas gruppen och dess innehåll bort permanent.
ms.openlocfilehash: 2c20c2bd3ce91331e7160132047dbf3ecd79c4b8
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635744"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>Återställa en borttagna Microsoft 365 grupp

Om du har tagit bort en grupp behålls den som standard i 30 dagar. Den här 30-dagarsperioden betraktas som en "mjuk borttagning" eftersom du fortfarande kan återställa gruppen. Efter 30 dagar tas gruppen och dess tillhörande innehåll bort permanent och kan inte återställas.

När du återställer en grupp återställs följande innehåll:
  
- Azure Active Directory (AD) Microsoft 365 Groups-objekt, egenskaper och medlemmar.
    
- Gruppens e-postadresser.
    
- Exchange Online delad inkorg och kalender.
    
- SharePoint Gruppwebbplats och filer online.
    
- OneNote-anteckningsbok
    
- Planner
    
- Teams

- Yammer gruppera och gruppera innehåll (om Microsoft 365 gruppen har skapats Yammer)

> [!NOTE]
> I den här artikeln beskrivs endast återställning Microsoft 365 grupper. Alla andra grupper kan inte återställas när de tagits bort.

## <a name="restore-a-group"></a>Återställa en grupp

# <a name="outlook"></a>[Outlook](#tab/outlook)

Om du är ägare till en Microsoft 365 grupp kan du återställa gruppen själv i Outlook på webben genom att följa de här stegen:

1. På sidan [Borttagna grupper](https://outlook.office.com/people/group/deleted)väljer du **alternativet Hantera grupper** under noden **Grupper** och väljer sedan **Borttagna**.

2. Klicka på **fliken** Återställ bredvid den grupp som du vill återställa.

Om den borttagna gruppen inte visas här kontaktar du administratören.

# <a name="admin-center"></a>[Administrationscenter](#tab/admin-center)

Om du är global administratör eller gruppadministratör kan du återställa en borttagna grupp Microsoft 365 administrationscentret:

1. Gå till [administrationscentret](https://admin.microsoft.com).
2. Expandera **Grupper** och klicka sedan på **Borttagna grupper.**
3. Markera den grupp som du vill återställa och klicka sedan på **Återställ grupp**.

> [!NOTE]
> I vissa fall kan det ta upp till ett dygn för gruppen och alla data att återställas. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>Har du frågor Microsoft 365 grupper?

Besök [Microsoft Tech Community om du](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) vill ställa frågor och delta i konversationer om Microsoft 365 grupper. 
  
## <a name="related-content"></a>Relaterat innehåll

[Hantera Microsoft 365-grupper med PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (artikel)\
[Ta bort grupper med Remove-UnifiedGroup cmdlet](/powershell/module/exchange/remove-unifiedgroup) (artikel)\
[Hantera dina gruppanslutna gruppwebbplatsinställningar](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (artikel)\
[Ta bort en grupp i Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (artikel)