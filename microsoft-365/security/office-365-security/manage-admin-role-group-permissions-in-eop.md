---
title: Hantera rollgrupper i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 125834f4-1024-4325-ad5a-d2573cfb005e
description: Administratörer kan läsa om hur de tilldelar eller tar bort behörigheter i administrationscentret för Exchange (EAC) i Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ce272985f195f44c57848e6861cefb64431698b9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289931"
---
# <a name="manage-role-groups-in-standalone-eop"></a>Hantera rollgrupper i fristående EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
-  [Exchange Online Protection fristående](exchange-online-protection-overview.md)

I fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor kan du använda administrationscentret för Exchange (EAC) för att lägga till användare i rollgrupper. Om du lägger till en användare i en rollgrupp får användaren behörighet att utföra särskilda administrativa uppgifter. Du kan också ta bort användare från rollgrupper.

Mer information om roller och rollgrupper finns i [Behörigheter i fristående EOP.](feature-permissions-in-eop.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Om du vill öppna administrationscentret för Exchange (EAC) går du till [administrationscentret för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Information om hur du öppnar fristående EOP PowerShell [finns i Ansluta till Exchange Online Protection PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)

- Du måste ha tilldelats behörigheter i Exchange Online Protection innan du kan utföra procedurerna i den här artikeln. Specifikt behöver du **rollhanteringsrollen,** som är tilldelad **rollgruppen Organisationshantering** som standard. Mer information finns i [Behörigheter i fristående EOP](feature-permissions-in-eop.md) [och Använda EAC för att ändra listan över medlemmar i rollgrupper.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Mer information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i Kortkommandon för [administrationscentret för Exchange i Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Har du problem? Be om hjälp i [forumet för Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-eac-to-manage-role-groups"></a>Använda EAC för att hantera rollgrupper

### <a name="use-the-eac-to-view-role-groups"></a>Använda EAC för att visa rollgrupper

1. Gå till Behörighetsadministratörsroller **i** \> EAC. Här visas alla rollgrupper i din organisation.

2. Välj en rollgrupp. I informationsfönstret visas **rollgruppens** **namn,** beskrivning, **tilldelade** roller och hanteras av.  Du kan också visa den här informationen genom att klicka **på** ![ redigeringsikonen. ](../../media/ITPro-EAC-EditIcon.png)

### <a name="use-the-eac-to-create-role-groups"></a>Använda EAC för att skapa rollgrupper

När du skapar en ny rollgrupp kan du konfigurera alla inställningar själv (när gruppen eller efter den skapas). Du kan också kopiera en befintlig rollgrupp och ändra den.

1. Gå till Behörighetsadministratörsroller i EAC  \> och gör sedan något av följande:

   - **Skapa en ny rollgrupp manuellt: Klicka** på **ikonen Lägg** ![ ](../../media/ITPro-EAC-AddIcon.png) till.

   - **Kopiera en befintlig rollgrupp:** Markera den rollgrupp som du vill kopiera och klicka sedan på ikonen **Kopiera** ![ ](../../media/ITPro-EAC-CopyIcon.png) kopia.

2. I fönstret **Ny rollgrupp** som visas konfigurerar du följande inställningar:

    - **Namn:** Ange ett unikt namn för rollgruppen.

    - **Beskrivning:** Ange en valfri beskrivning för rollgruppen.

    - **Roller:** Klicka **på ikonen** Lägg till eller ta bort om du vill välja eller ändra ![ ](../../media/ITPro-EAC-AddIcon.png)  ![ ](../../media/ITPro-EAC-RemoveIcon.gif) rollerna som har tilldelats rollgruppen.

    - **Medlemmar:** Klicka på **ikonen Lägg** till eller ![ ta ](../../media/ITPro-EAC-AddIcon.png) **bort** om du vill ändra medlemskap ![ i ](../../media/ITPro-EAC-RemoveIcon.gif) rollgrupper.

3. När du är klar klickar du på **Spara** för att skapa rollgruppen.

### <a name="use-the-eac-to-modify-role-groups"></a>Använda EAC för att ändra rollgrupper

I EAC går  du till \> **Behörighetsadministratörsroller,** väljer den rollgrupp du vill ändra och klickar sedan på **ikonen** ![ Redigera ](../../media/ITPro-EAC-EditIcon.png) redigera.

Samma alternativ är tillgängliga när du ändrar rollgrupper som när du skapar rollgrupper. Du kan:

- Ändra namn och beskrivning.

- Lägga till och ta bort hanteringsroller (skapa eller ta bort rolltilldelningar).

- Lägga till och ta bort medlemmar.

**Obs!** Vissa rollgrupper (till exempel Organisationshantering) begränsar vilka roller du kan ta bort från gruppen.

#### <a name="use-the-eac-modify-the-list-of-members-in-role-groups"></a>Använd EAC för att ändra listan över medlemmar i rollgrupper

1. I EAC går du **till** \> **Behörighetsadministratörsroller,** väljer den rollgrupp som du vill ändra och klickar sedan på **ikonen** ![ Redigera ](../../media/ITPro-EAC-EditIcon.png) redigering.

2. Gör något av följande i avsnittet Medlemmar på sidan **med** rollgruppegenskaper som öppnas:

   - Klicka **på Lägg till** lägg ![ till-ikon. ](../../media/ITPro-EAC-AddIcon.png) Leta rätt på den användare som du vill lägga till på sidan som visas och klicka sedan på **lägg till ->.** Välj användare och klicka **på lägg >** gånger som behövs. Klicka på OK när du är **klar.**

   - Markera de användare du vill ta bort och klicka sedan på ikonen **Ta** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) bort.

3. Klicka på **Spara** när du är klar.

   > [!NOTE]
   > Användare kan behöva logga ut och logga in igen för att se ändringen av sina administrativa rättigheter när du har lagt till eller tagit bort medlemmar från rollgruppen.

### <a name="use-the-eac-to-remove-role-groups"></a>Använda EAC för att ta bort rollgrupper

Du kan inte ta bort inbyggda rollgrupper, men du kan ta bort anpassade rollgrupper som du har skapat.

1. Gå till Behörighetsadministratörsroller **i** \> EAC.

2. Markera den rollgrupp du vill ta bort och klicka sedan på ikonen **Ta** ![ ](../../media/ITPro-EAC-DeleteIcon.png) bort.

3. Klicka **på Ja** i bekräftelsefönstret som visas.

## <a name="use-powershell-to-manage-role-groups"></a>Använda PowerShell för att hantera rollgrupper

### <a name="use-standalone-eop-powershell-to-view-role-groups"></a>Använda fristående EOP PowerShell för att visa rollgrupper

Använd följande syntax för att visa en rollgrupp:

```PowerShell
Get-RoleGroup [-Identity "<Role Group Name>"] [-Filter <Filter>]
```

Det här exemplet returnerar en sammanfattningslista över alla rollgrupper.

```PowerShell
Get-RoleGroup
```

Det här exemplet returnerar detaljerad information för rollgruppen med namnet Mottagaradministratörer.

```PowerShell
Get-RoleGroup -Identity "Recipient Administrators" | Format-List
```

I det här exemplet returneras alla rollgrupper där användaren Julia är medlem. Du måste använda värdet DistinguishedName (DN) för Julia, som du hittar genom att köra kommandot: `Get-User -Identity Julia | Format-List DistinguishedName` .

```PowerShell
Get-RoleGroup -Filter "Members -eq 'CN=Julia,OU=contoso.onmicrosoft.com,OU=Microsoft Exchange Hosted Organizations,DC=NAMPR001,DC=PROD,DC=OUTLOOK,DC=COM'"
```

Detaljerad information om syntax och parametrar finns i [Get-RoleGroup.](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroup)

### <a name="use-standalone-eop-powershell-to-create-role-groups"></a>Använda fristående EOP PowerShell för att skapa rollgrupper

När du skapar en ny rollgrupp kan du konfigurera alla inställningar manuellt (när gruppen eller efter den skapas). Du kan också kopiera en befintlig rollgrupp och ändra den.

- Om du vill skapa en ny rollgrupp manuellt använder du följande syntax:

  ```PowerShell
  New-RoleGroup -Name "Unique Name" -Description "Descriptive text" -Roles <"Role1","Role2"...>
  ```

  - _Parametern_ Roles anger vilka hanteringsroller som ska tilldelas rollgruppen med hjälp av följande `"Role1","Role1",..."RoleN"` syntax. Du kan se tillgängliga roller med hjälp av **cmdleten Get-ManagementRole.**

  - _Parametern_ Members anger medlemmarna i rollgruppen genom att använda följande syntax: `"Member1","Member2",..."MemberN"` . Du kan ange användare, e-postaktiverade universal security groups (USGs) eller andra rollgrupper (säkerhetshuvudnamn).

  I det här exemplet skapas en ny rollgrupp med namnet "Hantering av begränsad mottagare" med följande inställningar:

  - Rollen E-postmottagare tilldelas till rollgruppen.

  - Användarna Kim och Martin läggs till som medlemmar.

  ```PowerShell
  New-RoleGroup -Name "Limited Recipient Management" -Roles "Mail Recipients" -Members "Kim","Martin"
  ```

- Så här kopierar du en befintlig rollgrupp:

  1. Lagra rollgruppen som du vill kopiera i en variabel med följande syntax:

     ```PowerShell
     $RoleGroup = Get-RoleGroup "<Existing Role Group Name>"
     ```

  2. Skapa den nya rollgruppen med följande syntax:

     ```PowerShell
     New-RoleGroup -Name "<Unique Name>" -Roles $RoleGroup.Roles [-Members <Members>]
     ```

     _Parametern_ Members anger medlemmarna i rollgruppen genom att använda följande syntax: `"Member1","Member2",..."MemberN"` . Du kan ange användare, e-postaktiverade universal security groups (USGs) eller andra rollgrupper (säkerhetshuvudnamn).

     I det här exemplet kopieras rollgruppen Organisationshantering till den nya rollgruppen "Begränsad organisationshantering". Rollgruppmedlemmarna är Isabelle, Bengt och Han.

     ```PowerShell
     $RoleGroup = Get-RoleGroup "Organization Management"
     New-RoleGroup "Limited Organization Management" -Roles $RoleGroup.Roles -Members "Isabelle","Carter","Lukas"
     ```

För detaljerad information om syntax och [parametrar, New-RoleGroup.](https://docs.microsoft.com/powershell/module/exchange/New-RoleGroup)

### <a name="use-standalone-eop-powershell-modify-the-list-of-members-in-role-groups"></a>Använda fristående EOP PowerShell för att ändra listan över medlemmar i rollgrupper

- **Cmdlet:arna Add-RoleGroupMember** och **Remove-RoleGroupMember** lägger till eller tar bort enskilda medlemmar en i taget. Cmdleten **Update-RoleGroupMember** kan ersätta eller ändra den befintliga listan över medlemmar.

- Medlemmar i en rollgrupp kan vara användare, e-postaktiverade universal security groups (USGs) eller andra rollgrupper (säkerhetshuvudnamn).

Använd följande syntax för att ändra medlemmar i en rollgrupp:

```PowerShell
Update-RoleGroupMember -Identity "<Role Group Name>" -Members <Members>
```

- Använd _följande_ syntax för att ersätta den befintliga listan med medlemmar med de värden du `"Member1","Member2",..."MemberN"` anger:

- Använd följande syntax _för_ att selektivt ändra den befintliga listan med medlemmar: `@{Add="Member1","Member2"...; Remove="Member3","Member4"...}` .

Det här exemplet ersätter alla aktuella medlemmar i rollgruppen supportavdelning med angivna användare.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members "Gabriela Laureano","Hyun-Ae Rim","Jacob Berger"
```

I det här exemplet läggs Daigoro Ario till och Valerie Barrio tas bort från listan över medlemmar i rollgruppen Supportavdelning.

```PowerShell
Update-RoleGroupMember -Identity "Help Desk" -Members @{Add="Daigoro Akai"; Remove="Valeria Barrios"}
```

Detaljerad information om syntax och parametrar finns i [Update-RoleGroupMember.](https://docs.microsoft.com/powershell/module/exchange/Update-RoleGroupMember)

### <a name="use-standalone-eop-powershell-to-remove-role-groups"></a>Använda fristående EOP PowerShell för att ta bort rollgrupper

Du kan inte ta bort inbyggda rollgrupper, men du kan ta bort anpassade rollgrupper som du har skapat.

Använd följande syntax för att ta bort en anpassad rollgrupp:

```PowerShell
Remove-RoleGroup -Identity "<Role Group Name>" [-BypassSecurityGroupManagerCheck]
```

I det här exemplet tas rollgruppen Utbildningsadministratörer bort.

```PowerShell
Remove-RoleGroup -Identity "Training Administrators"
```

Detaljerad information om syntax och parametrar finns i [Remove-RoleGroup.](https://docs.microsoft.com/powershell/module/exchange/Remove-RoleGroup)

### <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Kontrollera att du har kopierat en rollgrupp genom att göra något av följande:

- Gå till Behörighetsadministratörsroller i EAC och kontrollera  \> att rollgruppen visas (eller inte visas). Markera rollgruppen och kontrollera inställningarna i informationsfönstret eller klicka på **Redigera** ikon för ![ att verifiera ](../../media/ITPro-EAC-EditIcon.png) inställningarna.

- I Exchange Online PowerShell ersätter du med namnet på rollgruppen och kör följande kommando för att verifiera att rollgruppen finns (eller inte finns) och verifiera \<Role Group Name\> inställningarna:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
