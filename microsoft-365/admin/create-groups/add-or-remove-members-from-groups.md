---
title: Lägga till eller ta bort medlemmar Microsoft 365 grupper
ms.reviewer: arvaradh
f1.keywords: NOCSH
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
- MET150
ms.assetid: e186d224-a324-4afa-8300-0e4fc0c3000a
description: Lär dig hur du lägger till en medlem i en grupp, tar bort medlemmar från gruppen och hanterar gruppägares status i Microsoft 365 administrationscenter.
ms.openlocfilehash: b5b0a398a5ebb47a5f27066f1daea1a822adbff2
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635612"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a>Lägga till eller ta bort medlemmar Microsoft 365 grupper i administrationscentret

I Microsoft 365 skapar gruppmedlemmarna vanligtvis sina egna grupper, lägger till sig själva i grupper som de vill gå med i eller bjuds in av gruppägare. Om gruppägandet ändras eller om du anser att en medlem ska läggas till eller tas bort kan du som administratör även göra den ändringen. Endast en global administratör, Exchange, gruppadministratör eller användaradministratör kan göra dessa ändringar. [Vad är en Microsoft 365 grupp?](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

> [!TIP]
> Om du inte är administratör kan du [lägga till eller ta bort medlemmar med hjälp av Outlook](https://support.microsoft.com/office/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de).
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a>Lägga till en medlem i en grupp i administrationscentret

1. Gå till sidan Aktiva grupper [**i administrationscentret.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Klicka på ett gruppnamn.

3. På fliken Medlemmar i informationsfönstret **väljer** du Visa **alla och hantera medlemmar och** sedan Lägg till **medlemmar.**

4. Sök efter eller välj namnet på den person som du vill lägga till.

5. Välj **Spara**.

## <a name="add-a-group-to-a-member-in-the-admin-center"></a>Lägga till en grupp till en medlem i administrationscentret

1. I administrationscentret går du till [**sidan Aktiva**](https://admin.microsoft.com/Adminportal/Home?#/users) användare.  

2. Klicka på en användare.

3. På fliken Konto i **informationsfönstret väljer** du **Hantera grupper.**

4. Sök efter eller välj namnet på gruppen som du vill lägga till.

5. Välj **Spara**.

## <a name="remove-a-member-from-a-group-in-the-admin-center"></a>Ta bort en medlem från en grupp i administrationscentret

> [!NOTE]
> När du tar bort en medlem från en privat grupp tar det 5 minuter innan personen blockeras från gruppen.

1. Gå till sidan Aktiva grupper [**i administrationscentret.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Klicka på ett gruppnamn.

3. På fliken Medlemmar i **informationsfönstret väljer** du **Visa alla och hanterar medlemmar**.

4. Välj X bredvid den medlem du vill ta bort.

5. Välj **Spara** för att ta bort medlemmen.

## <a name="manage-group-owner-status"></a>Hantera gruppägares status

Personen som skapade gruppen är som standard gruppägare. Grupper har ofta flera ägare för stöd av säkerhetskopiering eller av andra orsaker. Medlemmar kan flyttas upp till ägarstatus och ägare kan flyttas ned till medlemsstatus.
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a>Höja en medlem till ägarstatus i administrationscentret

1. Gå till sidan Aktiva grupper [**i administrationscentret.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Klicka på ett gruppnamn.

3. På fliken Medlemmar i **informationsfönstret väljer** du Visa **alla och hantera ägare.**

4. Välj **Lägg till ägare.**

5. Markera kryssrutan bredvid namnet på den medlem som du vill lägga till.

6. Välj **Spara** och sedan **Stäng.**

### <a name="remove-owner-status-in-the-admin-center"></a>Ta bort ägarstatus i administrationscentret

1. Gå till sidan Aktiva grupper [**i administrationscentret.**](https://admin.microsoft.com/Adminportal/Home?#/groups)  

2. Klicka på ett gruppnamn.

3. På fliken Medlemmar i **informationsfönstret väljer** du Visa **alla och hantera ägare.**

4. Välj X bredvid ägarens namn.

5. Välj **Spara**.

## <a name="next-steps"></a>Nästa steg

- [Hantera grupper dynamiskt i Azure Active Directory](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal): mer information finns i avsnittet "Hur kan jag hantera medlemskapet för en grupp dynamiskt?"

- Om du vill lägga till tusentals användare i grupper använder [du Add-UnifiedGroupLinks.](/powershell/module/exchange/add-unifiedgrouplinks)

- [Tilldela en ny ägare till en överbliven grupp](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

## <a name="related-content"></a>Relaterat innehåll

[Uppgradera distributionslistor till Microsoft 365 grupper i Outlook](../manage/upgrade-distribution-lists.md) (artikel)\
[Varför du bör uppgradera dina distributionslistor till grupper i Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188) (artikel)\
[Hantera gäståtkomst i Microsoft 365 grupper](manage-guest-access-in-groups.md) (artikel)\
[Hantera Microsoft 365 grupper med PowerShell: i](../../enterprise/manage-microsoft-365-groups-with-powershell.md)den här artikeln ges en artikel om viktiga cmdlets och exempel (artikel)\
[Microsoft 365 gruppnamnprincip](../../solutions/groups-naming-policy.md) (artikel)