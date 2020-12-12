---
title: Hantera roll grupper i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Administratörer kan läsa mer om hur du tilldelar eller tar bort behörigheter i administrations centret för Exchange (UK) i Exchange Online Protection.
ms.openlocfilehash: 4a1353963e5e3eadc1a07f8b4aa3a765b06c86ec
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659303"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Hantera rollgrupper i fristående EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor kan du använda administrations centret för Exchange (UK) för att lägga till användare i roll grupper. Om du lägger till en användare i en roll grupp får användaren behörighet att utföra särskilda administratörs uppgifter. Du kan också ta bort användare från roll grupper.

Mer information om roller och roll grupper finns i [behörigheter i fristående EOP](feature-permissions-in-eop.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Om du vill öppna administrations centret för Exchange (UK) läser du [administrations Center för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Information om hur du öppnar fristående EOP PowerShell finns i [ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Du måste ha behörighet i Exchange Online Protection innan du kan göra det i den här artikeln. Specifikt behöver du **roll hanterings** rollen, som tilldelats roll gruppen **organisations hantering** . Mer information finns i [behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd UK för att ändra listan över medlemmar i roll grupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i kortkommandon [för administrations centret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.

## <a name="use-the-eac-to-manage-role-groups"></a>Använda UK för att hantera roll grupper

### <a name="use-the-eac-to-view-role-groups"></a>Använda roll grupperna UK för att Visa

1. Gå till  \> **rollerna för administratörs** behörighet i UK. Alla roll grupper i din organisation visas här.

2. Välj en roll grupp. I informations fönstret visas **namnet**, **beskrivningen**, **tilldelade roller** och **som hanteras av** roll gruppen. Du kan också se informationen genom att klicka på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) .

### <a name="use-the-eac-to-create-role-groups"></a>Använda UK för att skapa roll grupper

När du skapar en ny roll grupp kan du konfigurera alla inställningar själv (när du skapar gruppen eller efter). Eller så kan du kopiera en befintlig roll grupp och ändra den.

1. Gå **till** \> **Administratörs roller** i UK och gör sedan något av följande:

   - **Skapa en ny roll grupp manuellt**: Klicka på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) .

   - **Kopiera en befintlig roll grupp**: Välj den roll grupp som du vill kopiera och klicka sedan på **Kopiera** ![ kopierings ikon ](../../media/ITPro-EAC-CopyIcon.png) .

2. I fönstret **ny roll grupp** som visas konfigurerar du följande inställningar:

    - **Namn**: Ange ett unikt namn för roll gruppen.

    - **Beskrivning**: Ange en valfri beskrivning för roll gruppen.

    - **Roller**: Klicka på **Lägg** till ![ Lägg till ](../../media/ITPro-EAC-AddIcon.png) eller **ta bort** ![ ikon ](../../media/ITPro-EAC-RemoveIcon.gif) för att välja eller ändra de roller som är tilldelade till roll gruppen.

    - **Medlemmar**: Klicka på **Lägg** till ![ Lägg till ](../../media/ITPro-EAC-AddIcon.png) eller **ta bort** ![ ikon ](../../media/ITPro-EAC-RemoveIcon.gif) för att ändra medlemskap i roll gruppen.

3. När du är klar klickar du på **Spara** för att skapa roll gruppen.

### <a name="use-the-eac-to-modify-role-groups"></a>Använda UK för att ändra roll grupper

I avsnittet UK går du till **behörigheter för behörighets** \> **Administration**, väljer den roll grupp som du vill ändra och klickar sedan på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) .

Samma alternativ är tillgängliga när du ändrar roll grupper som när du skapar roll grupper. Du kan:

- Ändra namn och beskrivning.

- Lägga till och ta bort hanterings roller (skapa eller ta bort roll tilldelningar).

- Lägga till och ta bort medlemmar.

**Obs!** vissa roll grupper (till exempel organisations hantering) begränsar vilka roller du kan ta bort från gruppen.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>Använda UK ändra listan över medlemmar i roll grupper

1. Gå **till** \> **Administratörs roller** i UK, Välj den roll grupp som du vill ändra och klicka sedan på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) .

2. Gör något av följande i avsnittet **medlemmar** på sidan roll grupp egenskaper som öppnas:

   - Klicka på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) . Leta reda på den användare som Wou vill lägga till på sidan som visas och klicka sedan på **Lägg till >**. Välj användare och klicka på **Lägg till >** många gånger efter behov. När du är klar klickar du på **OK**.

   - Markera de användare som du vill ta bort och klicka sedan på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-RemoveIcon.gif) .

3. Klicka på **Spara** när du är klar.

   > [!NOTE]
   > Användarna kan behöva logga ut och logga in igen för att se ändringarna i deras administrativa rättigheter efter att du har lagt till eller tagit bort medlemmar från roll gruppen.

### <a name="use-the-eac-to-remove-role-groups"></a>Använda UK för att ta bort roll grupper

Det går inte att ta bort inbyggda roll grupper, men du kan ta bort anpassade roll grupper som du har skapat.

1. Gå till  \> **rollerna för administratörs** behörighet i UK.

2. Välj den roll grupp du vill ta bort och klicka sedan på **ta bort** ![ ikon för borttagning ](../../media/ITPro-EAC-DeleteIcon.png) .

3. Klicka på **Ja** i bekräftelse fönstret som visas.

## <a name="use-powershell-to-manage-role-groups"></a>Använda PowerShell för att hantera roll grupper

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Använd fristående EOP PowerShell för att Visa roll grupper

Använd följande syntax för att visa en roll grupp:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

I det här exemplet returneras en sammanfattnings lista över alla roll grupper.

```PowerShell
Get-RoleGroup
```

Det här exemplet returnerar detaljerad information för roll gruppen som heter mottagare.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

I det här exemplet returneras alla roll grupper där användaren Julia är medlem. Du måste använda värdet för DistinguishedName (DN) för Julia, som du kan söka efter genom att köra kommandot: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Detaljerad information om syntax och parametrar finns i [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Använda fristående EOP PowerShell för att skapa roll grupper

När du skapar en ny roll grupp kan du konfigurera alla inställningar manuellt (när du skapar gruppen eller efter). Eller så kan du kopiera en befintlig roll grupp och ändra den.

- Använd följande syntax för att manuellt skapa en ny roll grupp:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - Parametern _roles_ anger de hanterings roller som ska tilldelas roll gruppen genom att använda följande syntax `"Role1","Role1",..."RoleN"` . Du kan se tillgängliga roller med cmdleten **Get-ManagementRole** .

  - Parametern _members_ anger medlemmar i roll gruppen genom att använda följande syntax: `"Member1","Member2",..."MemberN"` . Du kan ange användare, e-postaktiverade universella säkerhets grupper (USGs) eller andra roll grupper (säkerhets objekt).

  I det här exemplet skapas en ny roll grupp med namnet "begränsad mottagar hantering" med följande inställningar:

  - Rollen e-postmottagare är tilldelad roll gruppen.

  - Användare Kim och Martin läggs till som medlemmar.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Gör så här om du vill kopiera en befintlig roll grupp:

  1. Lagra den roll grupp som du vill kopiera med hjälp av följande syntax:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Skapa den nya roll gruppen med följande syntax:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     Parametern _members_ anger medlemmar i roll gruppen genom att använda följande syntax: `"Member1","Member2",..."MemberN"` . Du kan ange användare, e-postaktiverade universella säkerhets grupper (USGs) eller andra roll grupper (säkerhets objekt).

     I det här exemplet kopieras roll gruppen organisations hantering till den nya roll gruppen "begränsad organisations hantering". Medlemmar i roll gruppen är Isabelle, Cartere och Lukas.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Detaljerad information om syntax och parametrar finns i [New-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Använda fristående EOP PowerShell ändra listan över medlemmar i roll grupper

- Cmdletarna **Add-RoleGroupMember** och **Remove-RoleGroupMember** lägger till eller tar bort enskilda medlemmar ett i taget. Cmdleten **Update-RoleGroupMember** kan ersätta eller ändra befintlig lista över medlemmar.

- Medlemmar i en roll grupp kan vara användare, e-postaktiverade universella säkerhets grupper (USGs) eller andra roll grupper (säkerhets objekt).

Använd följande syntax för att ändra medlemmar i en roll grupp:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Använd följande syntax för att _ersätta_ den befintliga listan över medlemmar med de värden du anger: `"Member1","Member2",..."MemberN"` .

- Om du vill _ändra_ den befintliga listan med medlemmar kan du använda följande syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

I det här exemplet ersätts alla aktuella medlemmar i roll gruppen supportavdelning med de angivna användarna.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

I det här exemplet läggs Daigoro Akai och tas bort från listan med medlemmar i roll gruppen supportavdelning.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Detaljerad information om syntax och parametrar finns i [Update-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Använd fristående EOP-PowerShell för att ta bort roll grupper

Det går inte att ta bort inbyggda roll grupper, men du kan ta bort anpassade roll grupper som du har skapat.

Använd följande syntax för att ta bort en anpassad roll grupp:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

I det här exemplet tas roll gruppen utbildnings administratörer bort.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Detaljerad information om syntax och parametrar finns i [Remove-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).

### <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Om du vill kontrol lera att du har kopierat en roll grupp gör du något av följande:

- Gå **till** \> **Administratörs rollerna** i UK och kontrol lera att roll gruppen är listad (eller inte listad). Välj roll gruppen och kontrol lera inställningarna i informations fönstret eller klicka på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-EditIcon.png) för att bekräfta inställningarna.

- I Exchange Online PowerShell ersätter du \<Role Group Name\> namnet på roll gruppen och kör följande kommando för att kontrol lera att roll gruppen finns (eller inte existerar) och verifierar inställningarna:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
