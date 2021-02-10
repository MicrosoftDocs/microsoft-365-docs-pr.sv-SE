---
title: Hantera grupper i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Administratörer i fristående Exchange Online Protection-organisationer (EOP) kan lära sig att skapa, ändra och ta bort distributionsgrupper och e-postaktiverade säkerhetsgrupper i administrationscentret för Exchange (EAC) och i fristående Exchange Online Protection (EOP) PowerShell.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01fe5c6ab1555749d38f9c092b05aca9befb67fe
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166969"
---
# <a name="manage-groups-in-eop"></a>Hantera grupper i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
-  [Exchange Online Protection fristående](https://go.microsoft.com/fwlink/?linkid=2148611)

I fristående Exchange Online Protection -organisationer (EOP) utan Exchange Online-postlådor kan du skapa, ändra och ta bort följande typer av grupper:

- **Distributionsgrupper:** En samling e-postanvändare eller andra distributionsgrupper. Till exempel grupper eller andra ad hoc-grupper som behöver ta emot eller skicka e-post i ett gemensamt intresse. Distributionsgrupper är enbart för distribution av e-postmeddelanden och är inte säkerhetsobjekt (de kan inte ha tilldelats behörighet).

- **E-postaktiverade säkerhetsgrupper:** En samling e-postanvändare och andra säkerhetsgrupper som behöver åtkomstbehörighet för administratörsroller. Du kanske till exempel vill ge vissa grupper av användare administratörsbehörigheter så att de kan konfigurera inställningarna för skydd mot skräppost och skadlig programvara.

    > [!NOTE]
    >
    > - Som standard avvisar nya e-postaktiverade säkerhetsgrupper meddelanden från externa (oauticerade) avsändare.
    >
    > - Lägg inte till distributionsgrupper i e-postaktiverade säkerhetsgrupper.

Du kan hantera grupper i administrationscentret för Exchange (EAC) och i fristående EOP PowerShell.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Information om hur du öppnar administrationscentret för Exchange finns [i administrationscentret för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- När du hanterar grupper i fristående EOP PowerShell kan det uppstå begränsningar. PowerShell-procedurerna i den här artikeln använder en batchbearbetningsmetod som resulterar i en överföringsfördröjning på några minuter innan resultatet av kommandona visas.

- Du måste ha tilldelats behörigheter i Exchange Online Protection innan du kan utföra procedurerna i den här artikeln. Specifikt behöver du rollen **Distributionsgrupper,** som är tilldelad **rollgrupperna Organisationshantering** **och Mottagarhantering** som standard. Mer information finns i [Behörigheter i fristående EOP](feature-permissions-in-eop.md) och Använda EAC för att [ändra listan över medlemmar i rollgrupper.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Mer information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i Kortkommandon för [administrationscentret för Exchange i Exchange Online.](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Har du problem? Be om hjälp i [forumet för Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Använda administrationscentret för Exchange för att hantera distributionsgrupper

### <a name="use-the-eac-to-create-groups"></a>Använda EAC för att skapa grupper

1. Öppna EAC och gå till **Mottagare** \> **Grupper**.

2. Klicka **på** ![ ikonen Nytt nytt och välj sedan något av följande ](../../media/ITPro-EAC-AddIcon.png) alternativ:

   - **Distributionsgrupp**

   - **E-postaktiverad säkerhetsgrupp**

3. På den nya gruppsidan som öppnas konfigurerar du följande inställningar. Inställningar som är markerade med <sup>\*</sup> ett måste.

   - <sup>\*</sup>**Visningsnamn:** Det här namnet visas i organisationens adressbok, på raden Till: när  e-post skickas till den här gruppen och i listan Grupper i EAC. Visningsnamnet är obligatoriskt, måste vara unikt och bör vara användarvänligt så att andra känner igen det.

   - <sup>\*</sup>**Alias:** Skriv namnet på gruppens alias i den här rutan. Alias får inte vara längre än 64 tecken och måste vara unika. När en användare skriver alias på raden Till i ett e-postmeddelande matchas det med gruppens visningsnamn.

   - <sup>\*</sup>**E-postadress:** E-postadressen består av alias till vänster om at-symbolen (@) och en domän på höger sida. Som standard används värdet för **Alias** för aliasvärdet, men du kan ändra det. För domänvärdet klickar du på listrutan och väljer och godkänner domänen i din organisation.

   - **Beskrivning:** Den här beskrivningen visas i adressboken och i informationsfönstret i EAC.

   - <sup>\*</sup>**Ägare:** En gruppägare kan hantera gruppmedlemskap. Som standard är den person som skapar en grupp ägaren. Alla grupper måste ha minst en ägare.

     Om du vill lägga till ägare klickar **du på ikonen** Lägg ![ ](../../media/ITPro-EAC-AddIcon.png) till. I dialogrutan som visas går du till och väljer en mottagare eller grupp och klickar sedan **på lägg till ->.** Upprepa det här steget så många gånger det behövs. Klicka på OK när du är **klar.**

     Om du vill ta bort en ägare markerar du ägaren och klickar sedan på **ikonen Ta** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) bort.

   - **Medlemmar:** Lägg till och ta bort gruppmedlemmar.

     Om du vill lägga till medlemmar klickar **du på ikonen** Lägg ![ ](../../media/ITPro-EAC-AddIcon.png) till. I dialogrutan som visas går du till och väljer en mottagare eller grupp och klickar sedan **på lägg till ->.** Upprepa det här steget så många gånger det behövs. Klicka på OK när du är **klar.**

     Om du vill ta bort en medlem markerar du medlemmen och klickar sedan på ikonen **Ta** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) bort.

4. När du är klar klickar du på **Spara** för att skapa distributionsgruppen.

### <a name="use-the-eac-to-modify-distribution-groups"></a>Använda EAC för att ändra distributionsgrupper

1. Öppna EAC och gå till **Mottagare** \> **Grupper**.

2. I listan över grupper väljer du den distributionsgrupp eller e-postaktiverade  säkerhetsgrupp som du vill ändra och klickar sedan på ![ redigeringsikonen. ](../../media/ITPro-EAC-AddIcon.png)

3. Klicka på någon av följande flikar på sidan med egenskaper för distributionsgruppen som öppnas om du vill visa eller ändra egenskaper.

   Klicka på **Spara** när du är klar.

#### <a name="general"></a>Allmänt

Använd den här fliken för att visa eller ändra grundläggande information om gruppen.

- **Visningsnamn:** Det här namnet visas i adressboken, på raden Till när e-post skickas till den här gruppen och i **listan Grupper.** Visningsnamnet är obligatoriskt och bör vara användarvänligt så att det är lätt att känna igen. Den måste också vara unik i din domän.

  Om du har implementerat en gruppnamnsprincip måste visningsnamnet följa namnformatet som definieras av principen.

- **Alias:** Det här är den del av e-postadressen som visas till vänster om at-symbolen (@). Om du ändrar alias ändras även gruppens primära SMTP-adress och innehåller det nya aliaset. Dessutom sparas e-postadressen med det tidigare aliaset som proxyadress för gruppen.

- **E-postadress:** E-postadressen består av alias till vänster om at-symbolen (@) och en domän på höger sida. Som standard används värdet för **Alias** för aliasvärdet, men du kan ändra det. För domänvärdet klickar du på listrutan och väljer och godkänner domänen i din organisation.

- **Beskrivning:** Den här beskrivningen visas i adressboken och i informationsfönstret i EAC.

#### <a name="ownership"></a>Ägarskap

Använd den här fliken för att tilldela gruppägare. En gruppägare kan hantera gruppmedlemskap. Som standard är den person som skapar en grupp ägaren. Alla grupper måste ha minst en ägare.

Om du vill lägga till ägare klickar **du på ikonen** Lägg ![ ](../../media/ITPro-EAC-AddIcon.png) till. I dialogrutan som visas går du till och väljer en mottagare och klickar sedan **på lägg till ->.** Upprepa det här steget så många gånger det behövs. Klicka på OK när du är **klar.**

Om du vill ta bort en ägare markerar du ägaren och klickar sedan på **ikonen Ta** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) bort.

#### <a name="membership"></a>Medlemskap

Använd den här fliken för att lägga till eller ta bort gruppmedlemmar. Gruppägare behöver inte vara medlemmar i gruppen.

Om du vill lägga till medlemmar klickar **du på ikonen** Lägg ![ ](../../media/ITPro-EAC-AddIcon.png) till. I dialogrutan som visas går du till och väljer en mottagare eller grupp och klickar sedan **på lägg till ->.** Upprepa det här steget så många gånger det behövs. Klicka på OK när du är **klar.**

Om du vill ta bort en medlem markerar du medlemmen och klickar sedan på ikonen **Ta** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) bort.

### <a name="use-the-eac-to-remove-groups"></a>Använda EAC för att ta bort grupper

1. Öppna EAC och gå till **Mottagare** \> **Grupper**.

2. Markera den distributionsgrupp som du vill ta bort i listan med grupper och klicka sedan på ikonen **Ta** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) bort.

## <a name="use-powershell-to-manage-groups"></a>Använda PowerShell för att hantera grupper

### <a name="use-standalone-eop-powershell-to-view-groups"></a>Använda fristående EOP PowerShell för att visa grupper

Om du vill returnera en sammanfattningslista över alla distributionsgrupper och e-postaktiverade säkerhetsgrupper i fristående EOP PowerShell kör du följande kommando:

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

Om du vill returnera listan över gruppmedlemmar ersätter du med gruppens namn, alias eller e-postadress \<GroupIdentity\> och kör följande kommando:

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

Detaljerad information om syntax och parametrar finns i [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient) och [Get-DistributionGroupMember.](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember)

### <a name="use-standalone-eop-powershell-to-create-groups"></a>Använda fristående EOP PowerShell för att skapa grupper

Använd följande syntax för att skapa distributionsgrupper eller e-postaktiverade säkerhetsgrupper i fristående EOP PowerShell:

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**Anmärkningar**:

- _Namnparametern_ är obligatorisk, får innehålla högst 64 tecken och måste vara unik. Om du inte använder _displayName-parametern_ används värdet för _namnparametern_ för visningsnamnet.

- Om du inte använder _aliasparametern_ _används namnparametern_ för aliasvärdet. Blanksteg tas bort och tecken som inte stöds konverteras till frågetecken (?).

- Om du inte använder _parametern PrimarySmtpAddress_ används aliasvärdet i _parametern PrimarySmtpAddress._

- Om du inte använder _parametern Typ_ är standardvärdet Fördelning.

I det här exemplet skapas en distributionsgrupp med namnet IT-administratörer med angivna egenskaper.

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

Detaljerad information om syntax och parametrar finns i [New-EOPDistributionGroup.](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup)

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>Använda fristående EOP PowerShell för att ändra grupper

Om du vill ändra grupper i fristående EOP PowerShell använder du följande syntax:

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

I det här exemplet används ändringar av den primära SMTP-adressen (kallas även svarsadressen) för gruppen Anställda i Seattle till sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

Det här exemplet ersätter de aktuella medlemmarna i gruppen Säkerhetsgrupp med Peter Petersen och Tyson Fawcett.

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

I det här exemplet läggs en ny användare med namnet Tyson Fawcett till i gruppen Säkerhetsgrupp, samtidigt som de aktuella medlemmarna i gruppen bevaras.

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

Detaljerad information om syntax och parametrar finns [i Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) och [Update-EOPDistributionGroupMember.](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)

### <a name="remove-a-group-using-remote-windows-powershell"></a>Ta bort en grupp med fjärr-Windows PowerShell

I det här exemplet tas distributionsgruppen MED namnet IT-administratörer bort.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Detaljerad information om syntax och parametrar finns i [Remove-EOPDistributionGroup.](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Kontrollera att du har skapat, ändrat eller tagit bort en distributionsgrupp eller e-postaktiverad säkerhetsgrupp genom att göra något av följande:

- Öppna EAC och gå till **Mottagare** \> **Grupper**. Kontrollera att gruppen finns med i listan (eller inte visas) och verifiera **värdet grupptyp.** Markera gruppen och visa informationen i informationsfönstret, eller klicka på **redigeringsikonen** ![ för att visa ](../../media/ITPro-EAC-AddIcon.png) inställningarna.

- Kör följande kommando i fristående EOP PowerShell för att verifiera att gruppen listas (eller inte visas):

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- Ersätt \<GroupIdentity\> med namn, alias eller e-postadress för gruppen och kör följande kommando för att verifiera inställningarna:

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- Om du vill visa gruppmedlemmarna ersätter du med gruppens namn, alias eller \<GroupIdentity\> e-postadress och kör följande kommando:

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
