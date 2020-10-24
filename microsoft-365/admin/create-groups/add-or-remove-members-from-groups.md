---
title: Lägga till eller ta bort medlemmar från Microsoft 365-grupper
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
- BCS160
- MET150
- MOE150
- BSA160
ms.assetid: e186d224-a324-4afa-8300-0e4fc0c3000a
description: Lär dig hur du lägger till en medlem i en grupp, tar bort medlem från grupp och hanterar grupp ägar status i administrations centret för Microsoft 365.
ms.openlocfilehash: a8739b6cd2005598acbfccbaff6131235ec480ee
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753319"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a>Lägga till eller ta bort medlemmar från Microsoft 365-grupper med administrations centret

I Microsoft 365 skapar grupp medlemmar normalt deras egna grupper, lägger till sig själva i grupper som de vill delta i, eller är inbjudna efter grupp ägare. Om grupp ägandet ändras, eller om du fastställer att en medlem ska läggas till eller tas bort, som administratör kan du även göra den ändringen. Endast globala administratörer, Exchange-administratörer, grupp administratörer och användar administratörer kan göra dessa ändringar. [Vad är en Microsoft 365-grupp?](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

> [!TIP]
> Om du inte är administratör kan du [lägga till eller ta bort medlemmar med hjälp av Outlook](https://support.microsoft.com/office/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de).
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a>Lägga till en medlem i en grupp i administrations centret

1. Gå till sidan grupper i administrations centret **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .  

2. Välj ett grupp namn.

3. Välj **Visa alla och hantera medlemmar**på fliken **medlemmar** i informations fönstret och välj sedan **Lägg till medlemmar**.

4. Sök efter eller välj namnet på den person som du vill lägga till.

5. Välj **Spara**.

## <a name="add-a-group-to-a-member-in-the-admin-center"></a>Lägga till en grupp till en medlem i administrations centret

1. I administrationscentret går du till sidan **Användare** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktiva användare</a>.  

2. Välj en användare.

3. Välj **hantera grupper**på fliken **konto** i informations fönstret.

4. Sök efter eller välj namnet på den grupp du vill lägga till.

5. Välj **Spara**.

## <a name="remove-a-member-from-a-group-in-the-admin-center"></a>Ta bort en medlem från en grupp i administrations centret

> [!NOTE]
> När du tar bort en medlem från en privat grupp tar det 5 minuter innan personen blockeras från gruppen (sedan medlemskapsändringar har replikerats fullständigt bland domänkontrollanter).

1. Gå till sidan grupper i administrations centret **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .

2. Välj ett grupp namn.

3. Välj **Visa alla och hantera medlemmar**på fliken **medlemmar** i informations fönstret.

4. Markera kryss rutan X bredvid medlemmen du vill ta bort.

5. Klicka på **Spara** för att ta bort medlemmen.

## <a name="manage-group-owner-status"></a>Hantera grupp ägar status

Personen som skapade gruppen är som standard gruppägare. Grupper har ofta flera ägare för stöd av säkerhetskopiering eller av andra orsaker. Medlemmar kan flyttas upp till ägarstatus och ägare kan flyttas ned till medlemsstatus.
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a>Befordra en medlem till ägar status i Admin Center

1. Gå till sidan grupper i administrations centret **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .

2. Välj ett grupp namn.

3. Välj **Visa alla och hantera ägare**på fliken **medlemmar** i informations fönstret.

4. Sök efter en medlem eller Välj **Lägg till ägare**.

5. Markera kryss rutan bredvid namnet på den medlem som du vill lägga till.

6. Välj **Spara**och sedan **Stäng**.

### <a name="remove-owner-status-in-the-admin-center"></a>Ta bort ägar status i administrations centret

1. Gå till sidan grupper i administrations centret **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> .

2. Välj ett grupp namn.

3. Välj **Visa alla och hantera ägare**på fliken **medlemmar** i informations fönstret.

4. Välj X bredvid ägarens namn.

5. Välj **Spara**.

## <a name="more-on-managing-membership"></a>Mer om att hantera medlemskap

- [Hantera grupper dynamiskt i Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=847632): mer information finns i avsnittet "Hur kan jag hantera medlemskapet för en grupp dynamiskt?"

- Om du vill lägga till hundratals eller tusentals användare i grupper använder du [unifiedgrouplinkshttps](https://go.microsoft.com/fwlink/p/?LinkId=616191).

- [Tilldela en ny ägare till en överbliven grupp](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

## <a name="articles-about-managing-groups"></a>Artiklar om att hantera grupper

- [Uppgradera distributions listor till Microsoft 365-grupper i Outlook](../manage/upgrade-distribution-lists.md)

- [Varför du bör uppgradera dina distributionslistor till grupper i Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

- [Hantera gäst åtkomst i Microsoft 365-grupper](manage-guest-access-in-groups.md)

- [Hantera Microsoft 365-grupper med PowerShell: i](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)den här artikeln får du en introduktion till viktiga cmdlets och ger exempel

- [Microsoft 365 grupper namn princip](groups-naming-policy.md)