---
title: Hantera en grupp i administrationscentret
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
description: Lär dig att hantera Microsoft 365-grupper, inklusive att lägga till ta bort gruppmedlemmar, redigera e-postadressen, gruppnamnet eller beskrivningen och anpassa hur gruppen fungerar.
ms.openlocfilehash: 3ba3dd36ed3929e956ce6359e678d6b684f64bb9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908716"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>Hantera en grupp i administrationscentret för Microsoft 365

När du har [skapat en Microsoft 365-grupp](create-groups.md) och lagt till gruppmedlemmar kan du konfigurera gruppen. Du kan redigera gruppens namn eller beskrivning, hantera ägare eller medlemmar och ange om externa avsändare kan skicka e-post till gruppen och om kopior av gruppkonversationer ska skickas till medlemmar.

Gå till administrationscentret för Microsoft 365 på [https://admin.microsoft.com](https://admin.microsoft.com) .

## <a name="edit-the-group-name-or-description"></a>Redigera gruppens namn eller beskrivning

1. I administrationscentret expanderar du **Grupper** och klickar sedan på **Grupper.**

2. Markera den grupp som du vill redigera och klicka sedan på **Redigera namn och beskrivning**.

3. Uppdatera namn och beskrivning och välj sedan **Spara**.

## <a name="manage-group-owners-and-members"></a>Hantera gruppägare och medlemmar

1. I administrationscentret expanderar du **Grupper** och klickar sedan på **Grupper.**

2. Klicka på namnet på den grupp du vill hantera för att öppna inställningsfönstret.

3. På fliken **Medlemmar** väljer du om du vill hantera ägare eller medlemmar.

4. Välj **Lägg till om** du vill lägga till någon eller klicka på X **om** du vill ta bort någon.

5. Klicka på **Stäng**.

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>Skicka kopior av konversationer till gruppmedlemmars inkorgar
  
När du använder administrationscentret för att skapa en grupp får användarna som standard inte kopior av gruppmeddelanden och mötesinbjudningar som skickas till deras inkorgar. De måste gå till gruppen för att se konversationer och möten. Du kan ändra den här inställningen i administrationscentret.

När du aktiverar den här inställningen får gruppmedlemmarna en kopia av gruppmeddelanden och mötesinbjudningar som skickas till deras inkorg i Outlook. De kan läsa och ta bort kopian utan att någon annan påverkas. En kopia av e-postmeddelandet finns kvar i gruppens inkorg.

Gruppmedlemmar kan avanmäla sig från dessa e-postmeddelanden genom att välja att sluta följa gruppen i Outlook.

1. I administrationscentret expanderar du **Grupper** och klickar sedan på **Grupper.**

2. Klicka på namnet på den grupp du vill hantera för att öppna inställningsfönstret.

3. På fliken **Inställningar** väljer du Skicka **kopior** av gruppkonversationer och händelser till gruppmedlemmar om du vill att medlemmarna ska få kopior av gruppmeddelanden och kalenderobjekt i sin egen inkorg.

4. Välj **Spara**.

## <a name="let-people-outside-the-organization-email-the-group"></a>Låta personer utanför organisationen skicka e-post till gruppen

Det här alternativet är bra om du vill ha en företags-e-postadress som info@contoso.com.
 
1. I administrationscentret expanderar du **Grupper** och klickar sedan på **Grupper.**

2. Klicka på namnet på den grupp du vill hantera för att öppna inställningsfönstret.

3. I listan över grupper i administrationscentret väljer du namnet på den  grupp som du vill ändra och går sedan till fliken Inställningar och väljer Tillåt externa avsändare att skicka e-post till den **här gruppen.**
    
4. Välj **Spara**.

## <a name="permanently-delete-a-microsoft-365-group"></a>Ta bort en Microsoft 365-grupp permanent

Ibland vill du kanske ta bort en grupp permanent utan att behöva vänta på att den mjuka borttagningsperioden på 30 dagar ska upphöra att gälla. Starta PowerShell och kör det här kommandot för att ta fram gruppens objekt-ID
 
 ```powershell
`Get-AzureADMSDeletedGroup`
```

Notera objekt-ID för gruppen eller grupperna som du vill ta bort permanent.
  
> [!CAUTION]
> Borttagningen av gruppen raderar gruppen och allt innehåll för alltid. 
  
Om du vill ta bort gruppen kör du det här kommandot i PowerShell

```powershell
`Remove-AzureADMSDeletedDirectoryObject -Id <objectId>`
```

För att kontrollera att gruppen har tagits bort kör du cmdleten  *Get- AzureADMSDeletedGroup*  en gång till för att bekräfta att gruppen inte längre visas i listan över mjukt borttagna grupper. I vissa fall kan det ta upp till ett dygn för gruppen och allt innehåll att tas bort permanent. 
  
## <a name="related-articles"></a>Relaterade artiklar

[Skapa en Microsoft 365-grupp](create-groups.md)

[Hantera gäståtkomst till Microsoft 365-grupper](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Välj den domän som ska användas när du skapar Microsoft 365-grupper](../../solutions/choose-domain-to-create-groups.md)

[Tillåta medlemmar att skicka som eller skicka för en Microsoft 365-grupp](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[Uppgradera distributionslistor till Microsoft 365-grupper](../manage/upgrade-distribution-lists.md)

[Hantera Microsoft 365-grupper med PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md)