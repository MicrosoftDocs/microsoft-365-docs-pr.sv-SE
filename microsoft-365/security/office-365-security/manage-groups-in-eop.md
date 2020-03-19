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
description: Du kan använda EOP (Exchange Online Protection) för att skapa e-postaktiverade grupper för en Exchange-organisation. Du kan också använda EOP för att definiera eller uppdatera gruppegenskaper som anger medlemskap, e-postadresser och andra aspekter av grupper.
ms.openlocfilehash: ad07066906f78703c568850afbfa5dfa8d8cc3c1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806471"
---
# <a name="manage-groups-in-eop"></a>Hantera grupper i EOP

 Du kan använda EOP (Exchange Online Protection) för att skapa e-postaktiverade grupper för en Exchange-organisation. Du kan också använda EOP för att definiera eller uppdatera gruppegenskaper som anger medlemskap, e-postadresser och andra aspekter av grupper. Du kan skapa distributionsgrupper och säkerhetsgrupper, beroende på dina behov. Dessa grupper kan skapas med hjälp av Exchange admin center (EAC) eller via fjärr-Windows PowerShell.

## <a name="types-of-mail-enabled-groups"></a>Typer av postaktiverade grupper

Du kan skapa två typer av grupper för exchange-organisationen:

- Distributionsgrupper är samlingar av e-postanvändare, till exempel ett team eller annan ad hoc-grupp, som behöver ta emot eller skicka e-post angående ett gemensamt intresseområde. Distributionsgrupper är endast för att distribuera e-postmeddelanden. I EOP refererar en distributionsgrupp till en postaktiverad grupp, oavsett om den har en säkerhetskontext eller inte.

- Säkerhetsgrupper är samlingar av e-postanvändare som behöver åtkomstbehörigheter för administratörsroller. Du kanske till exempel vill ge specifika behörigheter för användares administratörsroll så att de kan konfigurera inställningar för skräppost och skadlig kod.

    > [!NOTE]
    > Som standard kräver alla nya e-postaktiverade säkerhetsgrupper att alla avsändare autentiseras. Detta förhindrar att externa avsändare skickar meddelanden till e-postaktiverade säkerhetsgrupper.

## <a name="before-you-begin"></a>Innan du börjar

- Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Om du vill se vilka behörigheter du behöver läser du posten "Distributionsgrupper och säkerhetsgrupper" i [funktionsbehörigheterna i EOP-avsnittet.](feature-permissions-in-eop.md)

- Information om hur du öppnar administrationscentret för Exchange finns [i Administrationscenter för Exchange i Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Tänk på att när du skapar och hanterar grupper med Exchange Online Protection PowerShell cmdlets kan du stöta på begränsning.

- PowerShell-procedurerna i det här avsnittet använder en batchbearbetningsmetod som resulterar i en förökningsfördröjning på några minuter innan kommandonas resultat visas.

- Mer information om hur du använder Windows PowerShell för att ansluta till Exchange Online Protection finns i [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Information om kortkommandon som kan gälla för procedurerna i det här avsnittet finns i [Kortkommandon för administrationscentret för Exchange i Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Har du problem? Be om hjälp i [exchange onlineskydd](https://go.microsoft.com/fwlink/p/?linkId=285351) forum.

## <a name="create-a-group-in-the-eac"></a>Skapa en grupp i EAC

1. Öppna EAC och gå till **Mottagare** \> **Grupper**.

2. Klicka **New** ![på](../../media/ITPro-EAC-AddIcon.gif)Ny lägg till ikon och sedan på **Distributionsgrupp** eller **säkerhetsgrupp**, beroende på dina behov.

3. Konfigurera följande inställningar på sidan **Ny distributionsgrupp** eller **Ny säkerhetsgrupp:**

   - **Visningsnamn:** Skriv ett visningsnamn som är unikt för din organisation och meningsfullt för EOP-användare. Visningsnamnet krävs.

   - **Alias**: Skriv ett gruppalias på upp till 64 tecken som är unikt för din organisation. EOP-användare skriver aliaset i raden Till: e-postmeddelanden och aliaset matchar gruppens visningsnamn. Om du ändrar aliasändras även den primära SMTP-adressen för gruppen och innehåller det nya aliaset. Aliaset krävs.

   - **Beskrivning**: Skriv en beskrivning av gruppen så att användarna känner till syftet med gruppen.

   - **Ägare:** Som standard är den person som skapar gruppen ägare. Du kan lägga till en](../../media/ITPro-EAC-AddIcon.gif)ägare genom att välja Lägg **till** ![lägg till ikon . Alla grupper måste ha minst en ägare.

     > [!NOTE]
     > Ägare behöver inte vara medlemmar i gruppen.

   - **Medlemmar**: Använd det här avsnittet för att lägga till gruppmedlemmar och ange om godkännande krävs för att personer ska kunna gå med i eller lämna gruppen. Om du vill lägga till medlemmar](../../media/ITPro-EAC-AddIcon.gif)i gruppen klickar du på Lägg **till** ![lägg till ikon .

4. Klicka på **OK** om du vill gå tillbaka till den ursprungliga sidan.

5. När du är klar klickar du på **Spara** för att skapa gruppen. Den nya gruppen ska visas i listan över grupper.

## <a name="edit-or-remove-a-group-in-the-eac"></a>Redigera eller ta bort en grupp i EAC

1. Navigera till \> **mottagargrupper** **Recipients** i EAC.

2. Gör något av följande:

   - Så här redigerar du en grupp: I listan med grupper klickar du på den grupp](../../media/ITPro-EAC-EditIcon.gif)som du vill visa eller ändra och klickar sedan på **Redigera** ![redigera ikon . Du kan uppdatera allmänna inställningar, lägga till eller ta bort gruppägare och lägga till eller ta bort gruppmedlemmar efter behov.

   - Om du vill ta bort en grupp: Markera gruppen och klicka på **Ta bort** ![ikonen](../../media/ITPro-EAC-RemoveIcon.gif).

3. När du är klar med ändringarna klickar du på **Spara**.

## <a name="create-edit-or-remove-a-group-using-remote-windows-powershell"></a>Skapa, redigera eller ta bort en grupp med fjärranslutna Windows PowerShell

Det här avsnittet innehåller information om hur du skapar grupper och ändrar deras egenskaper i Exchange Online Protection PowerShell. Den visar också hur du tar bort en befintlig grupp.

### <a name="create-a-group-using-remote-windows-powershell"></a>Skapa en grupp med fjärranslutna Windows PowerShell

I det här exemplet används cmdleten [New-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/New-EOPDistributionGroup) för att skapa en distributionsgrupp med ett alias för itadmin och namnet IT-administratörer. Det lägger också till användare som medlemmar i gruppen.

```PowerShell
New-EOPDistributionGroup -Type Distribution -Name "IT Administrators" -Alias itadmin -Members @("Member1","Member2","Member3") -ManagedBy Member1
```

**Om**du vill skapa en säkerhetsgrupp i stället `Security` för en distributionsgrupp använder du värdet för parametern *Typ.*

Om du vill kontrollera att du har skapat GRUPPEN IT-administratörer kör du följande kommando för att visa information om den nya gruppen:

```PowerShell
Get-Recipient "IT Administrators" | Format-List
```

Detaljerad syntax och parameterinformation finns i [Hämta mottagare](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/Get-Recipient).

Om du vill hämta en lista över medlemmar i gruppen kör du följande kommando:

```PowerShell
Get-DistributionGroupMember "IT Administrators"
```

Detaljerad syntax- och parameterinformation finns i [Get-DistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-distributiongroupmember).

Om du vill få en fullständig lista över alla dina grupper kör du följande kommando:

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup" | Format-Table | more
```

### <a name="change-the-properties-of-a-group-using-remote-windows-powershell"></a>Ändra egenskaperna för en grupp med fjärranslutna Windows PowerShell

En fördel med att använda PowerShell i stället för EAC är möjligheten att ändra egenskaper för flera grupper.

Här är några exempel på hur du använder PowerShell för Exchange Online Protection för att ändra gruppegenskaper.

I det här exemplet används ändringar av den primära SMTP-adressen (kallas även svarsadressen) för gruppen Seattle-anställda för att sea.employees@contoso.com.

```PowerShell
Set-EOPDistributionGroup "Seattle Employees" -PrimarysmptAddress "sea.employees@contoso.com"
```

Detaljerad syntax- och parameterinformation finns i [Set-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-eopdistributiongroup).

Om du vill kontrollera att du har ändrat egenskaperna för gruppen kör du följande kommando för att verifiera det nya värdet:

```PowerShell
Get-Recipient "Seattle Employees" | Format-List "PrimarySmtpAddress"
```

I det här exemplet uppdateras alla medlemmar i gruppen Seattle Anställda. Använd ett kommatecken för att skilja alla medlemmar åt.

```PowerShell
Update-EOPDistributionGroupMember -Identity "Seattle Employees" -Members @("Member1","Member2","Member3","Member4","Member5")
```

Detaljerad syntax- och parameterinformation finns i [Uppdatera-EOPDistributionGroupMember](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/update-eopdistributiongroupmember).

Om du vill hämta listan över alla medlemmar i gruppen Seattle-anställda kör du följande kommando:

```PowerShell
Get-DistributionGroupMember "Seattle Employees"
```

### <a name="remove-a-group-using-remote-windows-powershell"></a>Ta bort en grupp med fjärranslutna Windows PowerShell

I det här exemplet används distributionsgruppen IT-administratörer.

```PowerShell
Remove-EOPDistributionGroup -Identity "IT Administrators"
```

Detaljerad syntax- och parameterinformation finns i [Ta bort-EOPDistributionGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/remove-eopdistributiongroup).

Om du vill kontrollera att gruppen har tagits bort kör du följande kommando och bekräftar att gruppen (i det här fallet "It-administratörer") har tagits bort.

```PowerShell
Get-Recipient -RecipientType "MailUniversalDistributionGroup"
```
