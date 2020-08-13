---
title: Hantera grupper i EOP
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
ms.assetid: 212e68ac-6330-47e9-a169-6cf5e2f21e13
ms.custom:
- seo-marvel-apr2020
description: Administratörer i fristående Exchange Online Protection (EOP)-organisationer kan lära sig hur du skapar, ändrar och tar bort distributions grupper och e-postaktiverade säkerhets grupper i administrations centret för Exchange (UK) och i fristående Exchange Online Protection (EOP) PowerShell.
ms.openlocfilehash: 813735d4024c3b8424a6bbac51ebef7b4c53e590
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653659"
---
# <a name="manage-groups-in-eop"></a>Hantera grupper i EOP

I fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor kan du skapa, ändra och ta bort följande typer av grupper:

- **Distributions grupper**: en samling e-postanvändare eller andra distributions grupper. Teams eller andra ad hoc-grupper som behöver ta emot eller skicka e-post i ett gemensamt intresse område. Distributions grupper är exklusivt för att distribuera e-postmeddelanden och är inte säkerhets objekt (de kan inte ha tilldelade behörigheter).

- **E-postaktiverade säkerhets grupper**: en samling e-postanvändare och andra säkerhets grupper som behöver åtkomst behörigheter för administratörs roller. Du kanske till exempel vill ge specifika användar administratörs behörigheter så att de kan konfigurera skydd mot skräp post och inställningar mot skadlig program vara.

    > [!NOTE]
    >
    > - Som standard nekar nya e-postaktiverade säkerhets grupper meddelanden från externa (overifierade) avsändare.
    >
    > - Lägg inte till distributions grupper i e-postaktiverade säkerhets grupper.

Du kan hantera grupper i administrations centret för Exchange (UK) och i fristående EOP PowerShell.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Om du vill öppna administrations centret för Exchange går du till [administrations Center för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- När du hanterar grupper i fristående EOP PowerShell kan du stöta på begränsning. PowerShell-förfarandena i det här avsnittet använder en grupp bearbetnings metod som resulterar i en spridnings fördröjning på några minuter innan resultatet av kommandona visas.

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna. Specifikt behöver du rollen distributions grupper, som är tilldelad till roll grupperna i (global admins) och RecipientManagement som standard. Mer information finns i [behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd UK för att ändra listan över medlemmar i roll grupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Information om tangent bords gen vägar som kan gälla för procedurerna i det här avsnittet finns i kortkommandon [för administrations centret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Använda administrations centret för Exchange för att hantera distributions grupper

### <a name="use-the-eac-to-create-groups"></a>Använda UK för att skapa grupper

1. Öppna EAC och gå till **Mottagare** \> **Grupper**.

2. Klicka på **ny** ![ ny ikon ](../../media/ITPro-EAC-AddIcon.png) och välj något av följande alternativ:

   - **Distributions grupp**

   - **E-postaktiverad säkerhetsgrupp**

3. Konfigurera följande inställningar på sidan ny grupp som öppnas. Inställningar som är markerade med <sup>\*</sup> är obligatoriska.

   - <sup>\*</sup>**Visnings namn**: det här namnet visas i organisationens adress bok, på raden till: när e-post skickas till den här gruppen och i listan **grupper** i UK. Visnings namnet är obligatoriskt, måste vara unikt och bör vara användarvänligt så att folk förstår vad det är.

   - <sup>\*</sup>**Alias**: Använd den här rutan för att ange namnet på aliaset för gruppen. Aliaset får inte överstiga 64 tecken och måste vara unikt. När en användare skriver alias på raden till i ett e-postmeddelande matchas gruppens visnings namn.

   - <sup>\*</sup>**E-postadress**: e-postadressen består av aliaset på vänster sida av snabel-a (@) och en domän på höger sida. Som standard används värdet för **alias** för Ali Aset, men du kan ändra det. För domän värde klickar du på den nedrullningsbara List rutan och väljer och godkänner domänen i organisationen.

   - **Beskrivning**: beskrivningen visas i adress boken och i informations fönstret i UK.

   - <sup>\*</sup>**Ägare**: en grupp ägare kan hantera grupp medlemskap. Den person som skapar en grupp är som standard ägaren. Alla grupper måste ha minst en ägare.

     Om du vill lägga till ägare klickar du på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) . I dialog rutan som visas letar du reda på och väljer en mottagare eller grupp och klickar sedan på **Lägg till >**. Upprepa det här steget så många gånger det behövs. När du är klar klickar du på **OK**.

     Om du vill ta bort en ägare markerar du ägaren och klickar sedan på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-RemoveIcon.gif) .

   - **Medlemmar**: lägga till och ta bort grupp medlemmar.

     Om du vill lägga till medlemmar klickar du på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) . I dialog rutan som visas letar du reda på och väljer en mottagare eller grupp och klickar sedan på **Lägg till >**. Upprepa det här steget så många gånger det behövs. När du är klar klickar du på **OK**.

     Om du vill ta bort en medlem markerar du medlemmen och klickar sedan på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-RemoveIcon.gif) .

4. När du är klar klickar du på **Spara** för att skapa distributions gruppen.

### <a name="use-the-eac-to-modify-distribution-groups"></a>Använda UK för att ändra distributions grupper

1. Öppna EAC och gå till **Mottagare** \> **Grupper**.

2. I listan med grupper väljer du den distributions grupp eller e-postaktiverade säkerhets grupp som du vill ändra och klickar sedan på **Redigera** ![ redigerings ikon ](../../media/ITPro-EAC-AddIcon.png) .

3. På sidan Egenskaper för distributions grupp som öppnas klickar du på någon av följande flikar för att visa eller ändra egenskaper.

   Klicka på **Spara** när du är klar.

#### <a name="general"></a>Allmänt

Använd den här fliken för att visa eller ändra grundläggande information om gruppen.

- **Visnings namn**: det här namnet visas i adress boken, på raden till när e-post skickas till den här gruppen och i **listan grupper**. Visnings namnet är obligatoriskt och bör vara användarvänligt så att folk förstår vad det är. Det måste också vara unikt i din domän.

  Om du har implementerat en grupp namns princip måste visnings namnet följa det namngivnings format som definieras av principen.

- **Alias**: det här är den del av e-postadressen som visas till vänster om @-symbolen. Om du ändrar aliaset ändras även den primära SMTP-adressen för gruppen och innehåller det nya aliaset. Dessutom sparas e-postadressen med föregående alias som en proxyadress för gruppen.

- **E-postadress**: e-postadressen består av aliaset på vänster sida av snabel-a (@) och en domän på höger sida. Som standard används värdet för **alias** för Ali Aset, men du kan ändra det. För domän värde klickar du på den nedrullningsbara List rutan och väljer och godkänner domänen i organisationen.

- **Beskrivning**: beskrivningen visas i adress boken och i informations fönstret i UK.

#### <a name="ownership"></a>Egendom

Använd den här fliken för att tilldela grupp ägare. En grupp ägare kan hantera grupp medlemskap. Den person som skapar en grupp är som standard ägaren. Alla grupper måste ha minst en ägare.

Om du vill lägga till ägare klickar du på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) . Leta upp och välj en mottagare i dialog rutan som visas och klicka sedan på **Lägg till >**. Upprepa det här steget så många gånger det behövs. När du är klar klickar du på **OK**.

Om du vill ta bort en ägare markerar du ägaren och klickar sedan på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-RemoveIcon.gif) .

#### <a name="membership"></a>Ingå

Använd den här fliken för att lägga till eller ta bort grupp medlemmar. Grupp ägare behöver inte vara medlemmar i gruppen.

Om du vill lägga till medlemmar klickar du på **Lägg** till ![ ikonen Lägg till ](../../media/ITPro-EAC-AddIcon.png) . I dialog rutan som visas letar du reda på och väljer en mottagare eller grupp och klickar sedan på **Lägg till >**. Upprepa det här steget så många gånger det behövs. När du är klar klickar du på **OK**.

Om du vill ta bort en medlem markerar du medlemmen och klickar sedan på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-RemoveIcon.gif) .

### <a name="use-the-eac-to-remove-groups"></a>Använda UK för att ta bort grupper

1. Öppna EAC och gå till **Mottagare** \> **Grupper**.

2. I listan med grupper väljer du den distributions grupp som du vill ta bort och klickar sedan på **ta bort** ![ ikonen Ta bort ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-groups"></a>Använda PowerShell för att hantera grupper

### <a name="use-standalone-eop-powershell-to-view-groups"></a>Använd fristående EOP PowerShell för att Visa grupper

Kör följande kommando om du vill returnera en sammanfattnings lista över alla distributions grupper och e-postaktiverade säkerhets grupper i fristående EOP PowerShell:

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

Om du vill returnera listan över grupp medlemmar ersätter du \<GroupIdentity\> med gruppens namn, alias eller e-postadress och kör följande kommando:

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

Detaljerad information om syntax och parametrar finns i [Get-mottagare](https://docs.microsoft.com/powershell/module/exchange/get-recipient) och [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).

### <a name="use-standalone-eop-powershell-to-create-groups"></a>Använda fristående EOP PowerShell för att skapa grupper

Använd följande syntax för att skapa distributions grupper eller e-postaktiverade säkerhets grupper i fristående EOP PowerShell:

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**Anmärkningar**:

- Parametern _namn_ är obligatorisk, har en maximal längd på 64 tecken och måste vara unik. Om du inte använder parametern _DisplayName_ används värdet för _namn_ parametern som visnings namn.

- Om du inte använder _Ali Aset_ används parametern _Name_ för värdet alias. Blank steg tas bort och tecken som inte stöds konverteras till frågetecken (?).

- Om du inte använder parametern _PrimarySMTPAddress_ används värdet alias i parametern _PrimarySMTPAddress_ .

- Om du inte använder parametern _Type_ är standardvärdet distribution.

I det här exemplet skapas en distributions grupp som heter IT-administratörer med angivna egenskaper.

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

Detaljerad information om syntax och parametrar finns i [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>Använda fristående EOP PowerShell för att ändra grupper

Om du vill ändra grupper i fristående EOP PowerShell använder du följande syntax:

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

I det här exemplet används ändringar av den primära SMTP-adressen (kallas även för svars adress) för anställda i Stockholm till sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

Det här exemplet ersätter de aktuella medlemmarna i gruppen säkerhets team med söta Petersen och Tyson Fawcett.

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

I det här exemplet läggs en ny användare till som heter Tyson Fawcett till i gruppen säkerhets team samtidigt som de nuvarande medlemmarna i gruppen bevaras.

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

Detaljerad information om syntax och parametrar finns i [set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) and [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).

### <a name="remove-a-group-using-remote-windows-powershell"></a>Ta bort en grupp med Windows PowerShell

I det här exemplet används borttagning av distributions gruppen IT-administratörer.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Detaljerad information om syntax och parametrar finns i [Remove-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Gör något av följande om du vill kontrol lera att du har skapat, ändrat eller tagit bort en distributions grupp eller en e-postaktive rad säkerhets grupp:

- Öppna EAC och gå till **Mottagare** \> **Grupper**. Kontrol lera att gruppen är listad (eller inte listad) och kontrol lera värdet för **grupp typ** . Markera gruppen och Visa informationen i informations fönstret, eller klicka på **Redigera** ![ redigerings ikonen ](../../media/ITPro-EAC-AddIcon.png) om du vill visa inställningarna.

- I fristående EOP PowerShell kör du följande kommando för att kontrol lera att gruppen är listad (eller inte listad):

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- Ersätt \<GroupIdentity\> med namn, alias eller e-postadress för gruppen och kör följande kommando för att kontrol lera inställningarna:

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- Om du vill visa grupp medlemmarna ersätter du \<GroupIdentity\> gruppen med namn, alias eller e-postadress och kör följande kommando:

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
