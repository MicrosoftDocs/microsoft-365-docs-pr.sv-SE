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
description: Administratörer i fristående EOP-organisationer (Exchange Online Protection) kan lära sig att skapa, ändra och ta bort distributionsgrupper och e-postaktiverade säkerhetsgrupper i administrationscentret för Exchange (EAC) och i fristående Exchange Online Protection (EOP) PowerShell.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3b97e3fac0840753edada964252875a6e3a4fa04
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207023"
---
# <a name="manage-groups-in-eop"></a>Hantera grupper i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
-  [Exchange Online Protection fristående](exchange-online-protection-overview.md)

I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kan du skapa, ändra och ta bort följande typer av grupper:

- **Distributionsgrupper:** En samling e-postanvändare eller andra distributionsgrupper. Det kan till exempel vara team eller andra ad hoc-grupper som behöver ta emot eller skicka e-post i ett gemensamt intresse. Distributionsgrupper är uteslutande för att distribuera e-postmeddelanden och är inte säkerhetsobjekt (de kan inte ha tilldelats behörigheter).

- **E-postaktiverade säkerhetsgrupper**: En samling e-postanvändare och andra säkerhetsgrupper som behöver åtkomstbehörighet för administratörsroller. Du kanske till exempel vill ge vissa grupper av användare administratörsbehörigheter så att de kan konfigurera inställningar för skydd mot skräppost och skadlig programvara.

    > [!NOTE]
    >
    > - Som standard avvisar nya e-postaktiverade säkerhetsgrupper meddelanden från externa avsändare (oautherade).
    >
    > - Lägg inte till distributionsgrupper till e-postaktiverade säkerhetsgrupper.

Du kan hantera grupper i administrationscentret för Exchange (EAC) och i fristående EOP PowerShell.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Information om hur du öppnar administrationscentret för Exchange finns [i Administrationscenter för Exchange i fristående EOP.](exchange-admin-center-in-exchange-online-protection-eop.md)

- Information om hur du ansluter till fristående EOP PowerShell finns i [Anslut till Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- När du hanterar grupper i fristående EOP PowerShell kan det uppstå begränsningar. PowerShell-procedurerna i den här artikeln använder en batchbearbetningsmetod som resulterar i en överföringsfördröjning på några minuter innan resultatet av kommandona visas.

- Du måste ha tilldelats behörigheter i Exchange Online Protection innan du kan utföra procedurerna i den här artikeln. Specifikt behöver du rollen **Distributionsgrupper,** som är tilldelad **rollgrupperna Organisationshantering** och **Mottagarhantering** som standard. Mer information finns i [Behörigheter i fristående EOP](feature-permissions-in-eop.md) och Använda EAC för att [ändra listan över medlemmar i rollgrupper.](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- Mer information om kortkommandon som kan gälla för procedurerna i den här artikeln finns i Kortkommandon för [Administrationscenter för Exchange i Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Har du problem? Be om hjälp i [Forumet för Exchange Online Protection.](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE)

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Använda Exchange admin center för att hantera distributionsgrupper

### <a name="use-the-eac-to-create-groups"></a>Använda EAC för att skapa grupper

1. Öppna EAC och gå till **Mottagare** \> **Grupper**.

2. Klicka **på** ![ Ny ny ikon och välj sedan något av följande ](../../media/ITPro-EAC-AddIcon.png) alternativ:

   - **Distributionsgrupp**

   - **E-postaktiverad säkerhetsgrupp**

3. På den nya gruppsidan som öppnas konfigurerar du följande inställningar. Inställningar som är markerade med <sup>\*</sup> ett är obligatoriska.

   - <sup>\*</sup>**Visningsnamn:** Det här namnet visas i organisationens adressbok, på raden Till: när  e-post skickas till den här gruppen och i listan Grupper i EAC. Visningsnamnet är obligatoriskt, måste vara unikt och bör vara användarvänligt så att det är lätt att känna igen.

   - <sup>\*</sup>**Alias**: Använd den här rutan för att skriva namnet på gruppens alias. Aliaset får högst innehålla 64 tecken och måste vara unikt. När en användare skriver alias på raden Till i ett e-postmeddelande matchas det med gruppens visningsnamn.

   - <sup>\*</sup>**E-postadress:** E-postadressen består av alias på vänster sida av at-symbolen (@) och en domän på höger sida. Som standard används värdet för **Alias** för aliasvärdet, men du kan ändra det. För domänvärdet klickar du på listrutan och väljer och accepterar domänen i din organisation.

   - **Beskrivning**: Den här beskrivningen visas i adressboken och i informationsfönstret i EAC.

   - <sup>\*</sup>**Ägare**: En gruppägare kan hantera gruppmedlemskap. Som standard är den person som skapar en grupp ägaren. Alla grupper måste ha minst en ägare.

     Om du vill lägga till ägare klickar du **på Lägg till** lägg ![ till-ikon. ](../../media/ITPro-EAC-AddIcon.png) I dialogrutan som visas går du till och väljer en mottagare eller grupp och klickar sedan på **lägg till ->**. Upprepa det här steget så många gånger det behövs. När du är klar klickar du på **OK.**

     Om du vill ta bort en ägare markerar du ägaren och klickar sedan på ta **bort-ikonen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

   - **Medlemmar**: Lägga till och ta bort gruppmedlemmar.

     Om du vill lägga till medlemmar klickar du **på Lägg till** lägg ![ till-ikon ](../../media/ITPro-EAC-AddIcon.png) . I dialogrutan som visas går du till och väljer en mottagare eller grupp och klickar sedan på **lägg till ->**. Upprepa det här steget så många gånger det behövs. När du är klar klickar du på **OK.**

     Om du vill ta bort en medlem markerar du medlemmen och klickar sedan på ta **bort-ikonen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

4. När du är klar klickar du på **Spara** för att skapa distributionsgruppen.

### <a name="use-the-eac-to-modify-distribution-groups"></a>Använda EAC för att ändra distributionsgrupper

1. Öppna EAC och gå till **Mottagare** \> **Grupper**.

2. I listan över grupper markerar du den distributionsgrupp eller e-postaktiverade säkerhetsgrupp som du vill ändra och klickar sedan på **Redigera** ![ redigera-ikonen ](../../media/ITPro-EAC-AddIcon.png) .

3. På sidan med egenskaper för distributionsgruppen som öppnas klickar du på någon av följande flikar för att visa eller ändra egenskaper.

   Klicka på **Spara** när du är klar.

#### <a name="general"></a>Allmänt

Använd den här fliken för att visa eller ändra grundläggande information om gruppen.

- **Visningsnamn:** Det här namnet visas i adressboken, på raden Till när e-post skickas till den här gruppen och i **listan Grupper.** Visningsnamnet är obligatoriskt och bör vara användarvänligt så att det är lätt att känna igen. Den måste också vara unik i din domän.

  Om du har implementerat en gruppnamnprincip måste visningsnamnet följa namnformatet som definieras av principen.

- **Alias:** Det här är den del av e-postadressen som visas till vänster om at-symbolen (@). Om du ändrar alias ändras även gruppens primära SMTP-adress och innehåller det nya aliaset. Dessutom sparas e-postadressen med det tidigare aliaset som en proxyadress för gruppen.

- **E-postadress:** E-postadressen består av alias på vänster sida av at-symbolen (@) och en domän på höger sida. Som standard används värdet för **Alias** för aliasvärdet, men du kan ändra det. För domänvärdet klickar du på listrutan och väljer och accepterar domänen i din organisation.

- **Beskrivning**: Den här beskrivningen visas i adressboken och i informationsfönstret i EAC.

#### <a name="ownership"></a>Ägarskap

Använd den här fliken för att tilldela gruppägare. En gruppägare kan hantera gruppmedlemskap. Som standard är den person som skapar en grupp ägaren. Alla grupper måste ha minst en ägare.

Om du vill lägga till ägare klickar du **på Lägg till** lägg ![ till-ikon. ](../../media/ITPro-EAC-AddIcon.png) I dialogrutan som visas går du till och väljer en mottagare och klickar sedan på **lägg till ->**. Upprepa det här steget så många gånger det behövs. När du är klar klickar du på **OK.**

Om du vill ta bort en ägare markerar du ägaren och klickar sedan på ta **bort-ikonen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

#### <a name="membership"></a>Medlemskap

Använd den här fliken för att lägga till eller ta bort gruppmedlemmar. Gruppägare behöver inte vara medlemmar i gruppen.

Om du vill lägga till medlemmar klickar du **på Lägg till** lägg ![ till-ikon ](../../media/ITPro-EAC-AddIcon.png) . I dialogrutan som visas går du till och väljer en mottagare eller grupp och klickar sedan på **lägg till ->**. Upprepa det här steget så många gånger det behövs. När du är klar klickar du på **OK.**

Om du vill ta bort en medlem markerar du medlemmen och klickar sedan på ta **bort-ikonen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

### <a name="use-the-eac-to-remove-groups"></a>Använda EAC för att ta bort grupper

1. Öppna EAC och gå till **Mottagare** \> **Grupper**.

2. I listan över grupper markerar du distributionsgruppen som du vill ta bort och klickar sedan på ta **bort-ikonen** ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-groups"></a>Använda PowerShell för att hantera grupper

### <a name="use-standalone-eop-powershell-to-view-groups"></a>Använda fristående EOP PowerShell för att visa grupper

Om du vill returnera en sammanfattningslista över alla distributionsgrupper och e-postaktiverade säkerhetsgrupper i fristående EOP PowerShell kör du följande kommando:

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

Om du vill returnera listan över gruppmedlemmar ersätter du den med gruppens namn, alias eller \<GroupIdentity\> e-postadress och kör följande kommando:

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

Detaljerad information om syntax och parametrar finns i [Get-Recipient](/powershell/module/exchange/get-recipient) och [Get-DistributionGroupMember.](/powershell/module/exchange/get-distributiongroupmember)

### <a name="use-standalone-eop-powershell-to-create-groups"></a>Använda fristående EOP PowerShell för att skapa grupper

Om du vill skapa distributionsgrupper eller e-postaktiverade säkerhetsgrupper i fristående EOP PowerShell använder du följande syntax:

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**Anmärkningar**:

- Parametern _Name_ är obligatorisk, har en maxlängd på 64 tecken och måste vara unik. Om du inte använder _parametern DisplayName_ används värdet för _parametern Name_ för visningsnamnet.

- Om du inte använder _parametern Alias_ används _parametern Name_ för aliasvärdet. Blanksteg tas bort och tecken som inte stöds konverteras till frågetecken (?).

- Om du inte använder _parametern PrimarySmtpAddress_ används aliasvärdet i _parametern PrimarySmtpAddress._

- Om du inte använder _parametern Typ_ är standardvärdet Fördelning.

I det här exemplet skapas en distributionsgrupp med namnet IT-administratörer med de angivna egenskaperna.

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

Detaljerad information om syntax och parametrar finns i [New-EOPDistributionGroup](/powershell/module/exchange/New-EOPDistributionGroup).

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>Använda fristående EOP PowerShell för att ändra grupper

Om du vill ändra grupper i fristående EOP PowerShell använder du följande syntax:

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

I det här exemplet används ändringar av den primära SMTP-adressen (kallas även svarsadressen) för gruppen Seattle Employees för att sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarySmtpAddress "sea.employees@contoso.com"
```

Det här exemplet ersätter de aktuella medlemmarna i gruppen Säkerhetsgrupp med Peter Petersen och Tyson Fawcett.

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

I det här exemplet läggs en ny användare med namnet Tyson Fawcett till i gruppen Säkerhetsteam samtidigt som de aktuella medlemmarna i gruppen bevaras.

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

Detaljerad information om syntax och parametrar finns i [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) och [Update-EOPDistributionGroupMember.](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember)

### <a name="remove-a-group-using-remote-windows-powershell"></a>Ta bort en grupp med Windows PowerShell på distans

I det här exemplet tas distributionsgruppen IT-administratörer bort.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Detaljerad information om syntax och parametrar finns i [Remove-EOPDistributionGroup.](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup)

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Kontrollera att du har skapat, ändrat eller tagit bort en distributionsgrupp eller en e-postaktiverad säkerhetsgrupp genom att göra något av följande:

- Öppna EAC och gå till **Mottagare** \> **Grupper**. Kontrollera att gruppen visas (eller inte visas) och kontrollera **värdet för Grupptyp.** Markera gruppen och visa informationen i fönstret Information, eller klicka på **Redigera** ![ redigera-ikonen ](../../media/ITPro-EAC-AddIcon.png) om du vill visa inställningarna.

- I fristående EOP PowerShell kör du följande kommando för att verifiera att gruppen visas (eller inte finns med):

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- Ersätt \<GroupIdentity\> med gruppens namn, alias eller e-postadress och kör följande kommando för att verifiera inställningarna:

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- Om du vill visa gruppens medlemmar \<GroupIdentity\> ersätter du den med gruppens namn, alias eller e-postadress och kör följande kommando:

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```