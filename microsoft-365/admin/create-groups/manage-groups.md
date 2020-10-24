---
title: Hantera en grupp i administrations centret
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 74a1ef8b-3844-4d08-9980-9f8f7a36000f
description: Lär dig att hantera Microsoft 365-grupper, inklusive att lägga till, ta bort grupp medlemmar, redigera e-postadress, grupp namn eller beskrivning och anpassa hur gruppen fungerar.
ms.openlocfilehash: 8216b80ba6cd6bffe470f4fe4ace43307afba5f2
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753307"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>Hantera en grupp i administrations centret för Microsoft 365

När du har [skapat en Microsoft 365-grupp](create-groups.md) och lagt till grupp medlemmar kan du konfigurera gruppen. Du kan redigera grupp namnet eller beskrivningen, hantera ägare eller medlemmar och ange om externa avsändare ska kunna skicka e-post till medlemmarna.

Gå till administrations centret för Microsoft 365 på [https://admin.microsoft.com](https://admin.microsoft.com) .

## <a name="edit-the-group-name-or-description"></a>Redigera gruppens namn eller beskrivning

1. I Admin Center expanderar du **grupper**och klickar sedan på **grupper**.

2. Välj den grupp du vill redigera och klicka sedan på **Redigera namn och beskrivning**.

3. Uppdatera namn och beskrivning och välj sedan **Spara**.

## <a name="manage-group-owners-and-members"></a>Hantera grupp ägare och medlemmar

1. I Admin Center expanderar du **grupper**och klickar sedan på **grupper**.

2. Klicka på namnet på den grupp du vill hantera för att öppna fönstret inställningar.

3. Välj om du vill hantera ägare eller medlemmar på fliken **medlemmar** .

4. Välj **Lägg** till för att lägga till någon eller klicka på **X** för att ta bort någon.

5. Klicka på **Stäng**.

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>Skicka kopior av konversationer till grupp medlemmarnas inkorgar
  
När du använder administrations centret för att skapa en grupp får användarna inte kopior av grupp-e-post och mötes inbjudningar till sina inkorgar. De måste gå till gruppen för att se konversationer och möten. Du kan ändra den här inställningen i administrations centret.

När du aktiverar den här inställningen kommer grupp medlemmar att få en kopia av grupp-e-postmeddelanden och mötes inbjudningar som skickas till Inkorgen i Outlook. De kan läsa och ta bort kopian utan att någon annan påverkas. En kopia av e-postmeddelandet finns kvar i gruppens inkorg.

Grupp medlemmar kan välja att inte ta emot dessa e-postmeddelanden genom att välja att sluta följa gruppen i Outlook.

1. I Admin Center expanderar du **grupper**och klickar sedan på **grupper**.

2. Klicka på namnet på den grupp du vill hantera för att öppna fönstret inställningar.

3. På fliken **Inställningar** väljer du **skicka kopior av gruppkonversationer och händelser till grupp medlemmar** om du vill att medlemmarna ska få kopior av grupp meddelanden och Kalender objekt i sin egen inkorg.

4. Välj **Spara**.

## <a name="let-people-outside-the-organization-email-the-group"></a>Låt personer utanför organisationen skicka e-post till gruppen

Det här alternativet är bra om du vill ha en e-postadress till företaget, till exempel info@contoso.com.
 
1. I Admin Center expanderar du **grupper**och klickar sedan på **grupper**.

2. Klicka på namnet på den grupp du vill hantera för att öppna fönstret inställningar.

3. I listan administrations Center grupper väljer du namnet på den grupp du vill ändra och väljer **Tillåt externa avsändare att skicka e-post till den här gruppen**på fliken **Inställningar** .
    
4. Välj **Spara**.

## <a name="permanently-delete-a-microsoft-365-group"></a>Ta bort en Microsoft 365-grupp permanent

Ibland kanske du vill ta bort en grupp permanent utan att vänta på att den 30 dagars borttagnings perioden upphör att gälla. Starta PowerShell och kör det här kommandot för att ta fram gruppens objekt-ID
 
 ```powershell
`Get-AzureADMSDeletedGroup`
```

Anteckna objekt-ID: t för gruppen som du vill ta bort permanent.
  
> [!CAUTION]
> Borttagningen av gruppen raderar gruppen och allt innehåll för alltid. 
  
Om du vill ta bort gruppen kör du det här kommandot i PowerShell

```powershell
`Remove-AzureADMSDeletedDirectoryObject -Id <objectId>`
```

För att kontrollera att gruppen har tagits bort kör du cmdleten  *Get- AzureADMSDeletedGroup*  en gång till för att bekräfta att gruppen inte längre visas i listan över mjukt borttagna grupper. I vissa fall kan det ta upp till ett dygn för gruppen och allt innehåll att tas bort permanent. 
  
## <a name="related-articles"></a>Relaterade artiklar

[Skapa en Microsoft 365-grupp](create-groups.md)

[Hantera gäst åtkomst till Microsoft 365-grupper](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Välj den domän som ska användas när du skapar Microsoft 365-grupper](../../solutions/choose-domain-to-create-groups.md)

[Tillåta medlemmar att skicka som eller skicka för en Microsoft 365-grupp](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[Uppgradera distributions listor till Microsoft 365-grupper](../manage/upgrade-distribution-lists.md)

[Hantera Microsoft 365-grupper med PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
