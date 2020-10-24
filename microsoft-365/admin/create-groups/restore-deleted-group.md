---
title: Återställa en borttagen Microsoft 365-grupp
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
description: Lär dig hur du återställer en borttagen Microsoft 365-grupp.
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753249"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>Återställa en borttagen Microsoft 365-grupp

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

> [!NOTE]
> I den här artikeln beskrivs hur du återställer bara Microsoft 365-grupper. Alla andra grupper kan inte återställas när de har tagits bort.

## <a name="restore-a-group"></a>Återställa en grupp

# <a name="outlook"></a>[Outlook](#tab/outlook)

Om du är ägare till en Microsoft 365-grupp kan du återställa gruppen själv i Outlook på webben genom att följa de här stegen:

1. Välj alternativet **hantera grupper** under noden **grupper** på [sidan borttagna grupper](https://outlook.office.com/people/group/deleted)och välj sedan **Borttaget**.

2. Klicka på fliken **Återställ** bredvid den grupp du vill återställa.

Om den borttagna gruppen inte visas här kan du kontakta en administratör.

# <a name="admin-center"></a>[Administrations Center](#tab/admin-center)

Om du är global administratör eller administratör för administratörer kan du återställa en borttagen grupp i administrations centret för Microsoft 365:

1. Gå till [administrations centret](https://admin.microsoft.com).
2. Expandera **grupper**och klicka sedan på **borttagna grupper**.
3. Markera den grupp du vill återställa och klicka sedan på **Återställ grupp**.

> [!NOTE]
> I vissa fall kan det ta så lång tid som 24 timmar för gruppen och alla dess data att återställas. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>Har du frågor om Microsoft 365-grupper?

Besök [Microsofts Tech-community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) för att publicera frågor och delta i konversationer om Microsoft 365-grupper. 
  
## <a name="related-articles"></a>Relaterade artiklar

[Hantera Microsoft 365-grupper med PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[Ta bort grupper med hjälp av cmdleten Remove-UnifiedGroup](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Hantera dina grupprelaterade gruppwebbplatsinställningar](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Ta bort en grupp i Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
