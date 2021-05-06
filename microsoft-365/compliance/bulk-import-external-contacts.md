---
title: Massimport av externa kontakter till Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: Lär dig hur administratörer kan använda Exchange Online PowerShell och en CSV-fil för att massimporter av externa kontakter till den globala adresslistan.
ms.openlocfilehash: 178e3676f8dc5fb59cdad9cc46d7ecbd9dddb90e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162020"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>Massimport av externa kontakter till Exchange Online

**Den här artikeln är för administratörer. Försöker du importera kontakter till din egen postlåda? Läs [Importera kontakter till Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
Har ditt företag många befintliga affärskontakter som du vill ta med i den delade adressboken (kallas även global adresslista) i Exchange Online? Vill du lägga till externa kontakter som medlemmar i distributionsgrupper, precis som med användare inom företaget? I så fall kan du använda Exchange Online PowerShell och en CSV-fil (kommaavgränsade värden) för att massimporta externa kontakter till Exchange Online. Processen i tre steg:
  
[Steg 1: Skapa en CSV-fil som innehåller information om de externa kontakterna](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[Steg 2: Skapa de externa kontakterna med PowerShell](#step-2-create-the-external-contacts-with-powershell) 

[Steg 3: Lägg till information i egenskaperna för de externa kontakterna](#step-3-add-information-to-the-properties-of-the-external-contacts)

När du har slutfört de här stegen för att importera kontakter kan du utföra följande uppgifter:
  
- [Lägga till fler externa kontakter](#add-more-external-contacts)
  
- [Dölja externa kontakter från den delade adressboken](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>Steg 1: Skapa en CSV-fil som innehåller information om de externa kontakterna

Det första steget är att skapa en CSV-fil som innehåller information om varje extern kontakt som du vill importera till Exchange Online. 
  
1. Kopiera följande text till en textfil i Anteckningar och spara den på skrivbordet som en CSV-fil med hjälp av ett filnamnssuffix .csv. till exempel ExternalContacts.csv.
    
    > [!TIP]
    > Om språket innehåller specialtecken (till exempel **å,** **ä** och **ö** på svenska) sparar du CSV-filen med UTF-8-kodning eller annan Unicode-kodning när du sparar filen i Anteckningar. 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    Den första raden, eller rubrikraden, i CSV-filen innehåller egenskaper för kontakter som kan användas när du importerar dem till Exchange Online. Varje egenskapsnamn avgränsas med kommatecken. Varje rad under rubrikraden representerar egenskapsvärdena för att importera en enskild extern kontakt. 
    
    > [!NOTE]
    > Den här texten innehåller exempeldata som du kan ta bort. Men ta inte bort eller ändra den första raden (rubrikraden). Den innehåller alla egenskaper för de externa kontakterna. 
  
2. Öppna CSV-filen i Microsoft Excel redigera CSV-filen eftersom det är mycket enklare att använda Excel redigera CSV-filen.
    
3. Skapa en rad för varje kontakt som du vill importera för att Exchange Online. Fyll i så många celler som möjligt. Den här informationen visas i den delade adressboken för varje kontakt. 
    
    > [!IMPORTANT]
    >  Följande egenskaper (som är de fyra första objekten på rubrikraden) krävs för att skapa en extern kontakt och måste vara ifyllda i CSV-filen: **ExternalEmailAddress,** **Name**, **FirstName,** **LastName**. PowerShell-kommandot som du kör i Steg 2 använder värdena för dessa egenskaper för att skapa kontakterna. 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>Steg 2: Skapa de externa kontakterna med PowerShell

Nästa steg är att använda CSV-filen som du skapade i Steg 1 och PowerShell för att massimporter av externa kontakter som visas i CSV-filen Exchange Online. 
  
1.  Anslut PowerShell till din Exchange Online organisation. Stegvisa instruktioner finns i Skapa [Anslut-Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell) Se till att använda användarnamnet och lösenordet för ditt globala administratörskonto när du ansluter till Exchange Online PowerShell. 
    
2. När du har anslutt PowerShell Exchange Online går du till skrivbordsmappen där du sparade CSV-filen i steg 1. till exempel `C:\Users\Administrator\desktop` .
    
3. Kör följande kommando för att skapa de externa kontakterna:

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    Det kan ta en stund att skapa de nya kontakterna, beroende på hur många du importerar. När kommandot har körts klart visas en lista i PowerShell över de nya kontakter som har skapats. 
    
4. Om du vill visa de nya externa kontakterna går du till Exchange (EAC) och klickar sedan **på Mottagare** \> **kontakter**. 
    
    > [!TIP]
    > Anvisningar för hur du ansluter till EAC finns Exchange [administrationscenter i Exchange Online](/exchange/exchange-admin-center). 
  
5. Om det behövs klickar **du på** Uppdatera för att uppdatera listan och se de externa kontakter som har importerats. 
    
    De importerade kontakterna visas i den delade adressboken i Outlook och Outlook på webben.
    
    > [!NOTE]
    > Du kan också visa kontakterna i Microsoft 365 administrationscenter  genom att gå till \> **Användarkontakter.** 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>Steg 3: Lägg till information i egenskaperna för de externa kontakterna

När du har kört kommandot i steg 2 skapas de externa kontakterna, men de innehåller ingen kontakt- eller organisationsinformation, det vill säga informationen från de flesta celler i CSV-filen. Det beror på att när du skapar nya externa kontakter fylls bara de obligatoriska egenskaperna i. Oroa dig inte om du inte har all information ifylld i CSV-filen. Om den inte finns där läggs den inte till.
  
1.  Anslut PowerShell till din Exchange Online organisation. Stegvisa instruktioner finns i Skapa [Anslut-Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)
    
2. Gå till skrivbordsmappen där du sparade CSV-filen i steg 1. till exempel `C:\Users\Administrator\desktop` .
    
3. Kör följande två kommandon för att lägga till de andra egenskaperna från CSV-filen i de externa kontakter som du skapade i steg 2.
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > Parametern  _Manager_ kan vara problematiskt. Om cellen är tom i CSV-filen får du ett felmeddelande och ingen egenskapsinformation läggs till för kontakten. Om du inte behöver ange en chef tar du bara bort från  ` -Manager $_.Manager ` det tidigare PowerShell-kommandot. 
  
    Det kan ta en stund att uppdatera kontakterna, beroende på hur många du importerade i steg 1. 
    
4. Så här kontrollerar du att egenskaperna har lagts till i kontakterna: 
    
1. Gå till Mottagare i **EAC.** \> 
    
2. Klicka på en kontakt och **klicka sedan** på ![ Redigera ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) redigera-ikonen för att visa kontaktens egenskaper. 
    
Nu är det allt! Användarna kan se kontakterna och den ytterligare informationen i adressboken när Outlook och Outlook på webben.
  
## <a name="add-more-external-contacts"></a>Lägga till fler externa kontakter

Du kan upprepa steg 1 till steg 3 för att lägga till nya externa kontakter i Exchange Online. Du eller användarna i företaget kan helt enkelt lägga till en ny rad i CSV-filen för den nya kontakten. Sedan kan du köra PowerShell-kommandona från steg 2 och steg 3 för att skapa och lägga till information i de nya kontakterna.
  
> [!NOTE]
> När du kör kommandot för att skapa nya kontakter kan du få ett felmeddelande om att de kontakter som skapades tidigare redan finns. Men alla nya kontakter som läggs till i CSV-filen skapas. 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>Dölja externa kontakter från den delade adressboken>

Vissa företag kanske bara använder externa kontakter så att de kan läggas till som medlemmar i distributionsgrupper. I det här scenariot vill de kanske dölja externa kontakter i den delade adressboken. Så här gör du:
  
1.  Anslut PowerShell till din Exchange Online organisation. Stegvisa instruktioner finns i Skapa [Anslut-Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)
    
2. Om du vill dölja en enskild extern kontakt kör du följande kommando.
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    Om du till exempel vill dölja Pilar Pinilla från den delade adressboken kör du det här kommandot:

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. Om du vill dölja alla externa kontakter från den delade adressboken kör du det här kommandot:

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

När du har döljt dem visas inte externa kontakter i den delade adressboken, men du kan fortfarande lägga till dem som medlemmar i en distributionsgrupp.