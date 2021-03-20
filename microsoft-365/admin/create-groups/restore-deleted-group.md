---
title: Återställa en borttagna Microsoft 365-grupp
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
description: Lär dig återställa en borttagna Microsoft 365-grupp.
ms.openlocfilehash: f3b6435d82d5beddf44f5920011b076b39c7dcd5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910552"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>Återställa en borttagna Microsoft 365-grupp

Om du har tagit bort en grupp behålls den som standard i 30 dagar. Den här 30-dagarsperioden betraktas som en "mjuk borttagning" eftersom du fortfarande kan återställa gruppen. Efter 30 dagar tas gruppen och dess tillhörande innehåll bort permanent och kan inte återställas.

När du återställer en grupp återställs följande innehåll:
  
- Azure Active Directory (AD) Microsoft 365 Groups-objekt, egenskaper och medlemmar.
    
- Gruppens e-postadresser.
    
- Delad inkorg och kalender i Exchange Online.
    
- SharePoint Online-gruppwebbplats och filer.
    
- OneNote-anteckningsbok
    
- Planner
    
- Teams

- Yammer-grupp- och gruppinnehåll (Om Microsoft 365-gruppen skapades från Yammer)

> [!NOTE]
> I den här artikeln beskrivs återställning av endast Microsoft 365-grupper. Alla andra grupper kan inte återställas när de tagits bort.

## <a name="restore-a-group"></a>Återställa en grupp

# <a name="outlook"></a>[Outlook](#tab/outlook)

Om du äger en Microsoft 365-grupp kan du återställa gruppen själv i Outlook på webben genom att följa de här stegen:

1. På sidan [Borttagna grupper](https://outlook.office.com/people/group/deleted)väljer du **alternativet Hantera grupper** under noden **Grupper** och väljer sedan **Borttagna**.

2. Klicka på **fliken** Återställ bredvid den grupp som du vill återställa.

Om den borttagna gruppen inte visas här kontaktar du administratören.

# <a name="admin-center"></a>[Administrationscenter](#tab/admin-center)

Om du är global administratör eller gruppadministratör kan du återställa en borttagna grupp i administrationscentret för Microsoft 365:

1. Gå till [administrationscentret](https://admin.microsoft.com).
2. Expandera **Grupper** och klicka sedan på **Borttagna grupper.**
3. Markera den grupp som du vill återställa och klicka sedan på **Återställ grupp**.

> [!NOTE]
> I vissa fall kan det ta upp till ett dygn för gruppen och alla data att återställas. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>Har du frågor om Microsoft 365-grupper?

Besök [Microsoft Tech Community om du](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) vill ställa frågor och delta i konversationer om Microsoft 365-grupper. 
  
## <a name="related-articles"></a>Relaterade artiklar

[Hantera Microsoft 365-grupper med PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
  
[Ta bort grupper med hjälp av cmdleten Remove-UnifiedGroup](/powershell/module/exchange/remove-unifiedgroup)
  
[Hantera dina grupprelaterade gruppwebbplatsinställningar](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Ta bort en grupp i Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)