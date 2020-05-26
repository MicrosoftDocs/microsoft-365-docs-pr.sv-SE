---
title: Hantera rollgrupper i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Administratörer kan lära sig att tilldela eller ta bort behörigheter i Administrationscenter för Exchange (EAC) i Exchange Online Protection.
ms.openlocfilehash: ba2d053e1e75bd8867ebb9eb7f426cde92abd3e8
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352341"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Hantera rollgrupper i fristående EOP

I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kan du använda Administrationscenter för Exchange (EAC) för att lägga till användare i rollgrupper. Genom att lägga till en användare i en rollgrupp får användaren behörighet att utföra specifika administratörsuppgifter. Du kan också ta bort användare från rollgrupper.

Mer information om roller och rollgrupper finns [i Behörigheter i fristående EOP](feature-permissions-in-eop.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Om du vill öppna Administrationscenter för Exchange (EAC) finns [i Administrationscenter för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Information om hur du öppnar fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna. Du behöver rollrollen Rollhantering, som som tilldelas rollgruppen OrganizationManagement (global admins) som standard. Mer information finns [i Behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd EAC ändra listan över medlemmar i rollgrupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i Forumet för [Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-eac-to-manage-role-groups"></a>Använd EAC för att hantera rollgrupper

### <a name="use-the-eac-to-view-role-groups"></a>Använda EAC för att visa rollgrupper

1. Gå till **Behörighetsadministratörsroller** \> **Admin roles**i EAC. Alla rollgrupper i organisationen visas här.

2. Välj en rollgrupp. I fönstret Information visas **rollgruppens namn,** **beskrivning,** **tilldelade roller**och **Hanterad** av. Du kan också se den **Edit** här informationen genom att klicka på ![ Ikonen Redigera redigera ](../../media/ITPro-EAC-EditIcon.png) .

### <a name="use-the-eac-to-create-role-groups"></a>Använd EAC för att skapa rollgrupper

När du skapar en ny rollgrupp kan du konfigurera alla inställningar själv (under skapandet av gruppen eller efter). Du kan också kopiera en befintlig rollgrupp och ändra den.

1. Gå till **Behörighetsadministratörsroller** i EAC \> **Admin roles**och gör sedan något av följande:

   - **Skapa en ny rollgrupp manuellt:** Klicka på **Ikonen Lägg till** lägg till ![ ](../../media/ITPro-EAC-AddIcon.png) .

   - **Kopiera en befintlig rollgrupp**: Markera den rollgrupp som du vill kopiera och klicka sedan på **Ikonen Kopiera** ![ kopia ](../../media/ITPro-EAC-CopyIcon.png) .

2. Konfigurera följande inställningar i fönstret **Ny rollgrupp** som visas:

    - **Namn**: Ange ett unikt namn för rollgruppen.

    - **Beskrivning**: Ange en valfri beskrivning för rollgruppen.

    - **Roller**: Klicka på **Ikonen Lägg** till eller ![ Ta ](../../media/ITPro-EAC-AddIcon.png) **bort** ![ ITPro-EAC-RemoveIcon.gif ](../../media/ITPro-EAC-RemoveIcon.gif) för att markera eller ändra de roller som har tilldelats rollgruppen.

    - **Medlemmar**: Klicka på **Lägg till** ikonen Lägg till eller ![ Ta ](../../media/ITPro-EAC-AddIcon.png) **bort** ![ ITPro-EAC-RemoveIcon.gif ](../../media/ITPro-EAC-RemoveIcon.gif) om du vill ändra rollgruppens medlemskap.

3. När du är klar klickar du på **Spara** för att skapa rollgruppen.

### <a name="use-the-eac-to-modify-role-groups"></a>Använda EAC för att ändra rollgrupper

Gå till **Behörighetsadministratörsroller** i EAC, \> **Admin roles**välj den rollgrupp som du vill ändra och klicka sedan på Ikonen **Redigera** ![ ](../../media/ITPro-EAC-EditIcon.png) redigera.

Samma alternativ är tillgängliga när du ändrar rollgrupper som när du skapar rollgrupper. Du kan:

- Ändra namn och beskrivning.

- Lägga till och ta bort hanteringsroller (skapa eller ta bort rolltilldelningar).

- Lägg till och ta bort medlemmar.

**Vissa**rollgrupper (till exempel Organisationshantering) begränsar de roller som du kan ta bort från gruppen.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>Använda EAC ändra listan över medlemmar i rollgrupper

1. Gå till **Behörighetsadministratörsroller** i \> **Admin roles**EAC, välj den rollgrupp som du vill ändra och klicka sedan på **Ikonen Redigera** ![ ](../../media/ITPro-EAC-EditIcon.png) redigera.

2. Gör något av följande i avsnittet **Memebers** i egenskapssidan för rollgrupp som öppnas:

   - Klicka på **Lägg till** ikonen För lägg ![ till ](../../media/ITPro-EAC-AddIcon.png) . På sidan som visas hittar du den användare som wou vill lägga till och klickar sedan på **lägg till ->**. Markera användare och klicka på **Lägg till ->** många gånger om det behövs. När du är klar klickar du på **OK**.

   - Markera de användare som du vill ta bort och klicka sedan på **Ikonen Ta bort** ta bort ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

3. Klicka på **Spara** när du är klar.

   > [!NOTE]
   > Användare kan behöva logga ut och logga in igen för att se ändringen av sina administrativa rättigheter när du har lagt till eller tagit bort medlemmar från rollgruppen.

### <a name="use-the-eac-to-remove-role-groups"></a>Använd EAC för att ta bort rollgrupper

Du kan inte ta bort inbyggda rollgrupper, men du kan ta bort anpassade rollgrupper som du har skapat.

1. Gå till **Behörighetsadministratörsroller** \> **Admin roles**i EAC.

2. Markera den rollgrupp som du vill ta bort och klicka sedan på **Ikonen Ta bort borttagning** ![ ](../../media/ITPro-EAC-DeleteIcon.png) .

3. Klicka på **Ja** i bekräftelsefönstret som visas.

## <a name="use-powershell-to-manage-role-groups"></a>Använda PowerShell för att hantera rollgrupper

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Använda fristående EOP PowerShell för att visa rollgrupper

Om du vill visa en rollgrupp använder du följande syntax:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

I det här exemplet returneras en sammanfattningslista över alla rollgrupper.

```PowerShell
Get-RoleGroup
```

I det här exemplet returneras detaljerad information för rollgruppen Med namnet Mottagaradministratörer.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

I det här exemplet returneras alla rollgrupper där användaren Julia är medlem. Du måste använda värdet DistinguishedName (DN) för Julia, som du kan hitta genom att köra kommandot: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Detaljerad syntax- och parameterinformation finns i [Get-RoleGroup](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup).

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Använda fristående EOP PowerShell för att skapa rollgrupper

När du skapar en ny rollgrupp kan du konfigurera alla inställningar manuellt (under skapandet av gruppen eller efter). Du kan också kopiera en befintlig rollgrupp och ändra den.

- Om du vill skapa en ny rollgrupp manuellt använder du följande syntax:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - Parametern _Roller_ anger vilka hanteringsroller som ska tilldelas rollgruppen med hjälp av följande syntax `"Role1","Role1",..."RoleN"` . Du kan se tillgängliga roller med hjälp av **Cmdlet Get-ManagementRole.**

  - Parametern _Medlemmar_ anger medlemmarna i rollgruppen med hjälp av följande syntax: `"Member1","Member2",..."MemberN"` . Du kan ange användare, e-postaktiverade universella säkerhetsgrupper (USGs) eller andra rollgrupper (säkerhetsobjekt).

  I det här exemplet skapas en ny rollgrupp med namnet "Begränsad mottagarehantering" med följande inställningar:

  - Rollen Mottagare av e-post tilldelas rollgruppen.

  - Användarna Kim och Martin läggs till som medlemmar.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Så här kopierar du en befintlig rollgrupp:

  1. Lagra den rollgrupp som du vill kopiera i en variabel med följande syntax:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Skapa den nya rollgruppen med följande syntax:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     Parametern _Medlemmar_ anger medlemmarna i rollgruppen med hjälp av följande syntax: `"Member1","Member2",..."MemberN"` . Du kan ange användare, e-postaktiverade universella säkerhetsgrupper (USGs) eller andra rollgrupper (säkerhetsobjekt).

     I det här exemplet kopieras rollgruppen Organisationshantering till den nya rollgruppen "Begränsad organisationshantering". Rollgruppmedlemmarna är Isabelle, Carter och Lukas.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

Detaljerad syntax- och parameterinformation, [Nyrollgrupp](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup).

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Använda fristående EOP PowerShell ändra listan över medlemmar i rollgrupper

- Cmdlets **för Add-RoleGroupMember** och **Remove-RoleGroupMember** lägger till eller tar bort enskilda medlemmar en i taget. **Cmdlet för Update-RoleGroupMember** kan ersätta eller ändra den befintliga medlemslistan.

- Medlemmarna i en rollgrupp kan vara användare, e-postaktiverade universella säkerhetsgrupper (USGs) eller andra rollgrupper (säkerhetsobjekt).

Om du vill ändra medlemmarna i en rollgrupp använder du följande syntax:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Om du vill _ersätta_ den befintliga medlemslistan med de värden du anger använder du följande syntax: `"Member1","Member2",..."MemberN"` .

- Om du vill ändra den befintliga medlemslistan _selektivt_ använder du följande syntax: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

Det här exemplet ersätter alla aktuella medlemmar i rollgruppen Help Desk med de angivna användarna.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

I det här exemplet läggs Daigoro Akai till och Valeria Barrio tas bort från listan över medlemmar i rollgruppen Help Desk.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Detaljerad syntax- och parameterinformation finns i [Uppdatera rollgruppmedlem](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember).

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Använd fristående EOP PowerShell för att ta bort rollgrupper

Du kan inte ta bort inbyggda rollgrupper, men du kan ta bort anpassade rollgrupper som du har skapat.

Om du vill ta bort en anpassad rollgrupp använder du följande syntax:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

I det här exemplet tas rollgruppen Utbildningsadministratörer bort.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Detaljerad syntax- och parameterinformation finns i [Ta bort rollgrupp](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup).

### <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Så här kontrollerar du att du har kopierat en rollgrupp:

- Gå till **Behörighetsadministratörsroller** i EAC och kontrollera att \> **Admin roles**rollgruppen visas (eller inte visas). Markera rollgruppen och kontrollera inställningarna i informationsfönstret eller klicka på **Redigera** ![ redigera ikon för att verifiera ](../../media/ITPro-EAC-EditIcon.png) inställningarna.

- I Exchange Online PowerShell ersätter du \< Rollgruppsnamnet \> med namnet på rollgruppen och kör följande kommando för att verifiera att rollgruppen finns (eller inte finns) och verifiera inställningarna:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
