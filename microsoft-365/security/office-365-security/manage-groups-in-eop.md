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
description: Administratörer i fristående EOP-organisationer (Exchange Online Protection) kan lära sig hur du skapar, ändrar och tar bort distributionsgrupper och e-postaktiverade säkerhetsgrupper i Exchange-administrationscentret (EAC) och i fristående EOP-powershell (Exchange Online Protection).
ms.openlocfilehash: 42086b67e22df4725bf07bf227853c070f936f24
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616508"
---
# <a name="manage-groups-in-eop"></a>Hantera grupper i EOP

I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kan du skapa, ändra och ta bort följande typer av grupper:

- **Distributionsgrupper**: En samling e-postanvändare eller andra distributionsgrupper. Till exempel team eller andra ad hoc-grupper som behöver ta emot eller skicka e-post inom ett gemensamt intresseområde. Distributionsgrupper är uteslutande avsedda för distribution av e-postmeddelanden och är inte säkerhetsobjekt (de kan inte ha behörigheter tilldelade till dem).

- **E-postaktiverade säkerhetsgrupper**: En samling e-postanvändare och andra säkerhetsgrupper som behöver åtkomstbehörigheter för administratörsroller. Du kanske till exempel vill ge specifika användaradministratörsbehörigheter så att de kan konfigurera inställningar för skräppost och skadlig kod.

    > [!NOTE]
    > <ul><li>Som standard avvisar nya e-postaktiverade säkerhetsgrupper meddelanden från externa (oautentiserade) avsändare.</li><li>Lägg inte till distributionsgrupper i e-postaktiverade säkerhetsgrupper.</li></ul>.

Du kan hantera grupper i Administrationscenter för Exchange (EAC) och i fristående EOP PowerShell.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Om du vill öppna administrationscentret för Exchange finns [i Administrationscenter för Exchange i fristående EOP](exchange-admin-center-in-exchange-online-protection-eop.md).

- Information om hur du ansluter till fristående EOP PowerShell finns i artikeln om att [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- När du hanterar grupper i fristående EOP PowerShell kan du stöta på begränsning. PowerShell-procedurerna i det här avsnittet använder en batchbearbetningsmetod som resulterar i en spridningsfördröjning på några minuter innan resultaten av kommandona visas.

- Du måste ha tilldelats behörigheter innan du kan genomföra de här procedurerna. Du behöver rollen Distributionsgrupper, som tilldelas rollgrupperna OrganizationManagement (global admins) och RecipientManagement som standard. Mer information finns [i Behörigheter i fristående EOP](feature-permissions-in-eop.md) och [Använd EAC ändra listan över medlemmar i rollgrupper](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns [i Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i Forumet för [Exchange Online Protection.](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="use-the-exchange-admin-center-to-manage-distribution-groups"></a>Använda administrationscentret för Exchange för att hantera distributionsgrupper

### <a name="use-the-eac-to-create-groups"></a>Använd EAC för att skapa grupper

1. Öppna EAC och gå till **Mottagare** \> **Grupper**.

2. Klicka på **Ny** ![ ny ikon och välj sedan något av ](../../media/ITPro-EAC-AddIcon.png) följande alternativ:

   - **Distributionsgrupp**

   - **E-postaktiverad säkerhetsgrupp**

3. Konfigurera följande inställningar på den nya gruppsidan som öppnas. Inställningar markerade med en <sup>\*</sup> krävs.

   - <sup>\*</sup>**Visningsnamn**: Det här namnet visas i organisationens adressbok, på raden Till: när e-post skickas till den här gruppen och i listan **Grupper** i EAC. Visningsnamnet krävs, måste vara unikt och ska vara användarvänligt så att folk känner igen vad det är.

   - <sup>\*</sup>**Alias**: Använd den här rutan om du vill skriva namnet på aliaset för gruppen. Aliaset får inte vara längre än 64 tecken och måste vara unikt. När en användare skriver aliaset på raden Till i ett e-postmeddelande matchas det till gruppens visningsnamn.

   - <sup>\*</sup>**E-postadress:** E-postadressen består av aliaset till vänster om at-symbolen (@) och en domän till höger. Som standard används värdet **för Alias** för aliasvärdet, men du kan ändra det. För domänvärdet klickar du på listrutan och väljer och accepterar domänen i organisationen.

   - **Beskrivning**: Den här beskrivningen visas i adressboken och i informationsfönstret i EAC.

   - <sup>\*</sup>**Ägare**: En gruppägare kan hantera gruppmedlemskap. Som standard är den person som skapar en grupp ägaren. Alla grupper måste ha minst en ägare.

     Om du vill lägga till ägare klickar du på **Lägg till** ikonen Lägg ![ till ](../../media/ITPro-EAC-AddIcon.png) . Leta reda på och markera en mottagare eller grupp i dialogrutan som visas och klicka sedan på **Lägg till ->**. Upprepa det här steget så många gånger det behövs. När du är klar klickar du på **OK**.

     Om du vill ta bort en ägare markerar du ägaren och klickar sedan på **Ikonen Ta bort** ta bort ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

   - **Medlemmar**: Lägg till och ta bort gruppmedlemmar.

     Om du vill lägga till medlemmar klickar du på **Lägg till** ikonen Lägg ![ till ](../../media/ITPro-EAC-AddIcon.png) . Leta reda på och markera en mottagare eller grupp i dialogrutan som visas och klicka sedan på **Lägg till ->**. Upprepa det här steget så många gånger det behövs. När du är klar klickar du på **OK**.

     Om du vill ta bort en medlem markerar du medlemmen och klickar sedan på **Ikonen Ta bort** ta bort ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

4. När du är klar klickar du på **Spara** för att skapa distributionsgruppen.

### <a name="use-the-eac-to-modify-distribution-groups"></a>Använda EAC för att ändra distributionsgrupper

1. Öppna EAC och gå till **Mottagare** \> **Grupper**.

2. Markera den distributionsgrupp eller den e-postaktiverade säkerhetsgrupp som du vill ändra i listan med grupper och klicka sedan på **Ikonen Redigera** ![ ](../../media/ITPro-EAC-AddIcon.png) redigera.

3. På sidan egenskaper för distributionsgrupp som öppnas klickar du på någon av följande flikar för att visa eller ändra egenskaper.

   Klicka på **Spara** när du är klar.

#### <a name="general"></a>Allmänt

Använd den här fliken om du vill visa eller ändra grundläggande information om gruppen.

- **Visningsnamn**: Det här namnet visas i adressboken, på raden Till när e-post skickas till den här gruppen och i **listan Grupper**. Visningsnamnet krävs och bör vara användarvänligt så att folk känner igen vad det är. Det måste också vara unikt i din domän.

  Om du har implementerat en gruppnamnprincip måste visningsnamnet överensstämma med det namngivningsformat som definieras av principen.

- **Alias**: Det här är den del av e-postadressen som visas till vänster om at-symbolen (@). Om du ändrar aliaset ändras även den primära SMTP-adressen för gruppen och det nya aliaset. Dessutom kommer e-postadressen med det tidigare aliaset att behållas som en proxyadress för gruppen.

- **E-postadress:** E-postadressen består av aliaset till vänster om at-symbolen (@) och en domän till höger. Som standard används värdet **för Alias** för aliasvärdet, men du kan ändra det. För domänvärdet klickar du på listrutan och väljer och accepterar domänen i organisationen.

- **Beskrivning**: Den här beskrivningen visas i adressboken och i informationsfönstret i EAC.

#### <a name="ownership"></a>Ägande

Använd den här fliken om du vill tilldela gruppägare. En gruppägare kan hantera gruppmedlemskap. Som standard är den person som skapar en grupp ägaren. Alla grupper måste ha minst en ägare.

Om du vill lägga till ägare klickar du på **Lägg till** ikonen Lägg ![ till ](../../media/ITPro-EAC-AddIcon.png) . Leta reda på och markera en mottagare i dialogrutan som visas och klicka sedan på **lägg till ->**. Upprepa det här steget så många gånger det behövs. När du är klar klickar du på **OK**.

Om du vill ta bort en ägare markerar du ägaren och klickar sedan på **Ikonen Ta bort** ta bort ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

#### <a name="membership"></a>Medlemskap

Använd den här fliken om du vill lägga till eller ta bort gruppmedlemmar. Gruppägare behöver inte vara medlemmar i gruppen.

Om du vill lägga till medlemmar klickar du på **Lägg till** ikonen Lägg ![ till ](../../media/ITPro-EAC-AddIcon.png) . Leta reda på och markera en mottagare eller grupp i dialogrutan som visas och klicka sedan på **Lägg till ->**. Upprepa det här steget så många gånger det behövs. När du är klar klickar du på **OK**.

Om du vill ta bort en medlem markerar du medlemmen och klickar sedan på **Ikonen Ta bort** ta bort ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

### <a name="use-the-eac-to-remove-groups"></a>Använd EAC för att ta bort grupper

1. Öppna EAC och gå till **Mottagare** \> **Grupper**.

2. Markera den distributionsgrupp som du vill ta bort i listan med grupper och klicka sedan på **Ikonen Ta bort** ta bort ![ ](../../media/ITPro-EAC-RemoveIcon.gif) .

## <a name="use-powershell-to-manage-groups"></a>Använda PowerShell för att hantera grupper

### <a name="use-standalone-eop-powershell-to-view-groups"></a>Använda fristående EOP PowerShell för att visa grupper

Om du vill returnera en sammanfattningslista över alla distributionsgrupper och e-postaktiverade säkerhetsgrupper i fristående EOP PowerShell kör du följande kommando:

```powershell
Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
```

Om du vill returnera listan över gruppmedlemmar ersätter du \<GroupIdentity\> med gruppens namn, alias eller e-postadress och kör följande kommando:

```powershell
Get-DistributionGroupMember -Identity <GroupIdentity>
```

Detaljerad syntax- och parameterinformation finns i [Hämta mottagare](https://docs.microsoft.com/powershell/module/exchange/get-recipient) och [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/get-distributiongroupmember).

### <a name="use-standalone-eop-powershell-to-create-groups"></a>Använda fristående EOP PowerShell för att skapa grupper

Om du vill skapa distributionsgrupper eller e-postaktiverade säkerhetsgrupper i fristående EOP PowerShell använder du följande syntax:

```PowerShell
New-EOPDistributionGroup -Name "<Unique Name>" -ManagedBy @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">) [-Alias <text>] [-DisplayName "<Descriptive Name>"] [-Members @("UserOrGroup1","UserOrGroup2",..."UserOrGroupN">)] [-Notes "<Optional Text>"] [-PrimarySmtpAddress <SmtpAddress>] [-Type <Distribution | Security>]
```

**Anmärkningar**:

- Parametern _Name_ krävs, har en maximal längd på 64 tecken och måste vara unik. Om du inte använder parametern _DisplayName_ används värdet för parametern _Name_ för visningsnamnet.

- Om du inte använder parametern _Alias_ används parametern _Name_ för aliasvärdet. Blanksteg tas bort och tecken som inte stöds konverteras till frågetecken (?).

- Om du inte använder parametern _PrimarySmtpAddress_ används aliasvärdet i parametern _PrimarySmtpAddress._

- Om du inte använder parametern _Typ_ är standardvärdet Distribution.

I det här exemplet skapas en distributionsgrupp med namnet IT-administratörer med de angivna egenskaperna.

```PowerShell
New-EOPDistributionGroup -Name "IT Administrators" -Alias itadmin -Members @("michelle@contoso.com","laura@contoso.com","julia@contoso.com") -ManagedBy "chris@contoso.com"
```

Detaljerad syntax- och parameterinformation finns i [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/New-EOPDistributionGroup).

### <a name="use-standalone-eop-powershell-to-modify-groups"></a>Använda fristående EOP PowerShell för att ändra grupper

Om du vill ändra grupper i fristående EOP PowerShell använder du följande syntax:

```powershell
Set-EOPDistributionGroup -Identity <GroupIdentity> [-Alias <Text>] [-DisplayName <Text>] [-ManagedBy @("User1","User2",..."UserN")] [-PrimarySmtpAddress <SmtpAddress>]

```powershell
Update-EOPDistributionGroupMember -Identity <GroupIdentity> -Members @("User1","User2",..."UserN")
```

I det här exemplet används ändringar av den primära SMTP-adressen (kallas även svarsadressen) för gruppen Seattle-anställda för att sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

Det här exemplet ersätter de nuvarande medlemmarna i gruppen Säkerhetsteam med Kitty Petersen och Tyson Fawcett.

```powershell
Update-EOPDistributionGroupMember -Identity "Security Team" -Members @("Kitty Petersen","Tyson Fawcett")
```

I det här exemplet läggs en ny användare till Tyson Fawcett i gruppen Security Team samtidigt som de aktuella medlemmarna i gruppen bevaras.

```powershell
$CurrentMemberObjects = Get-DistributionGroupMember "Security Team"
$CurrentMemberNames = $CurrentMemberObjects | % {$_.name}
$CurrentMemberNames += "Tyson Fawcett"
Update-EOPDistributionGroupMember -Identity "Security Team" -Members $CurrentMemberNames
```

Detaljerad syntax- och parameterinformation finns i [Ange-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/set-eopdistributiongroup) och [Update-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/update-eopdistributiongroupmember).

### <a name="remove-a-group-using-remote-windows-powershell"></a>Ta bort en grupp med fjärr-Windows PowerShell

I det här exemplet tas distributionsgruppen IT-administratörer bort.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Detaljerad syntax- och parameterinformation finns i [Ta bort EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/remove-eopdistributiongroup).

## <a name="how-do-you-know-these-procedures-worked"></a>Hur vet jag att de här procedurerna fungerade?

Så här kontrollerar du att du har skapat, ändrat eller tagit bort en distributionsgrupp eller en e-postaktiverad säkerhetsgrupp:

- Öppna EAC och gå till **Mottagare** \> **Grupper**. Kontrollera att gruppen visas (eller inte visas) och kontrollera värdet **för grupptypen.** Markera gruppen och visa informationen i informationsfönstret eller klicka på **Ikonen Redigera** ![ redigera för att visa ](../../media/ITPro-EAC-AddIcon.png) inställningarna.

- I fristående EOP PowerShell kör du följande kommando för att kontrollera att gruppen visas (eller inte finns med i listan):

  ```PowerShell
  Get-Recipient -RecipientType MailUniversalDistributionGroup,MailUniversalSecurityGroup -ResultSize unlimited
  ```

- Ersätt \<GroupIdentity\> med gruppens namn, alias eller e-postadress och kör följande kommando för att verifiera inställningarna:

  ```PowerShell
  Get-Recipient -Identity <GroupIdentity> | Format-List
  ```

- Om du vill visa gruppmedlemmarna ersätter du \<GroupIdentity\> med gruppens namn, alias eller e-postadress och kör följande kommando:

  ```PowerShell
  Get-DistributionGroupMember -Identity "<GroupIdentity>"
  ```
