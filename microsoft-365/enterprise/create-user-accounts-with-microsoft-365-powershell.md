---
title: Skapa Microsoft 365-användarkonton med PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- O365ITProTrain
- seo-marvel-apr2020
ms.assetid: 6770c5fa-b886-4512-8c67-ffd53226589e
description: Så här använder du PowerShell för att skapa enskilda eller flera Microsoft 365-användarkonton.
ms.openlocfilehash: c3676acdec3bbba328809ee1528206bbc44f94f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907570"
---
# <a name="create-microsoft-365-user-accounts-with-powershell"></a>Skapa Microsoft 365-användarkonton med PowerShell

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Du kan använda PowerShell för Microsoft 365 för att effektivt skapa användarkonton, inklusive flera konton.

När du skapar användarkonton i PowerShell krävs alltid vissa kontoegenskaper. Andra egenskaper krävs inte men är viktiga. Se följande tabell.
  
|**Egenskapsnamn**|**Obligatorisk**|**Beskrivning**|
|:-----|:-----|:-----|
|**DisplayName** <br/> |Ja  <br/> |Det här är visningsnamnet som används i Microsoft 365-tjänster. Till exempel *Caleb Några*. <br/> |
|**UserPrincipalName** <br/> |Ja  <br/> |Det här är kontonamnet som används för att logga in på Microsoft 365-tjänster. Till exempel *kan CalebS \@ contoso.onmicrosoft.com*.  <br/> |
|**Förnamn** <br/> |Nej  <br/> ||
|**LastName** <br/> |Nej  <br/> ||
|**LicenseAssignment** <br/> |Nej  <br/> |Det här är licensplanen (kallas även licensplanen eller SKU:n) som en tillgänglig licens tilldelas till användarkontot från. Licensen definierar de Microsoft 365-tjänster som är tillgängliga för kontot. Du behöver inte tilldela en licens till en användare när du skapar kontot, men kontot måste ha en licens för att få åtkomst till Microsoft 365-tjänster. Du har 30 dagar på dig att licensiera användarkontot när du har skapat det. |
|**Lösenord** <br/> |Nej  <br/> | Om du inte anger ett lösenord tilldelas ett slumpmässigt lösenord till användarkontot och lösenordet visas i resultatet av kommandot. Om du anger ett lösenord måste det innehålla 8 till 16 ASCII-texttecken av följande typer: gemener, versaler, siffror och symboler.<br/> |
|**Användningsbeläggning** <br/> |Nej  <br/> |Det här är en giltig landskod enligt ISO 3166-1 alfa-2. Till exempel *USA* för USA och *FR* för Frankrike. Det är viktigt att tillhandahålla detta värde eftersom vissa Microsoft 365-tjänster inte är tillgängliga i vissa länder. Du kan inte tilldela en licens till ett användarkonto om inte kontot har det här värdet konfigurerat. Mer information finns i [Om licensbegränsningar](https://go.microsoft.com/fwlink/p/?LinkId=691730).<br/> |

>[!Note]
>[Lär dig hur du skapar användarkonton](../admin/add-users/add-users.md) med hjälp av administrationscentret för Microsoft 365.
> 
> En lista över ytterligare resurser finns i [Hantera användare och grupper.](../admin/add-users/index.yml)
>   

## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Använda Azure Active Directory PowerShell för Graph-modulen

Börja med [att ansluta till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)

När du har anslutt använder du följande syntax för att skapa ett enskilt konto:
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="<user account password>"
New-AzureADUser -DisplayName "<display name>" -GivenName "<first name>" -SurName "<last name>" -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -MailNickName <mailbox name> -PasswordProfile $PasswordProfile -AccountEnabled $true
```

I det här exemplet skapas ett konto för den amerikanska *användaren Caleb Beskrivning:*
  
```powershell
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password="3Rv0y1q39/chsy"
New-AzureADUser -DisplayName "Caleb Sills" -GivenName "Caleb" -SurName "Sills" -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -MailNickName calebs -PasswordProfile $PasswordProfile -AccountEnabled $true
```

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Använda Microsoft Azure Active Directory-modulen för Windows PowerShell

Börja med [att ansluta till din Microsoft 365-klientorganisation.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

### <a name="create-an-individual-user-account"></a>Skapa ett enskilt användarkonto

Om du vill skapa ett enskilt konto ska du använda följande syntax:
  
```powershell
New-MsolUser -DisplayName <display name> -FirstName <first name> -LastName <last name> -UserPrincipalName <sign-in name> -UsageLocation <ISO 3166-1 alpha-2 country code> -LicenseAssignment <licensing plan name> [-Password <Password>]
```

>[!Note]
>PowerShell Core stöder inte Microsoft Azure Active Directory-modulen för Windows PowerShell-modulen och cmdlets som har *Msol* i sitt namn. Kör dessa cmdlets från Windows PowerShell.
>

Använd det här kommandot om du vill visa en lista över tillgängliga namn på licensplanen:

````powershell
Get-MsolAccountSku
````

Det här exemplet skapar ett konto för den amerikanska användaren *Caleb Planers* och tilldelar en licens från `contoso:ENTERPRISEPACK` licensplanen (Office 365 Enterprise E3).
  
```powershell
New-MsolUser -DisplayName "Caleb Sills" -FirstName Caleb -LastName Sills -UserPrincipalName calebs@contoso.onmicrosoft.com -UsageLocation US -LicenseAssignment contoso:ENTERPRISEPACK
```

### <a name="create-multiple-user-accounts"></a>Skapa flera användarkonton

1. Skapa en fil med kommaavgränsade värden (CSV) som innehåller den användarkontoinformation som krävs. Ett exempel:

     ```powershell
     UserPrincipalName,FirstName,LastName,DisplayName,UsageLocation,AccountSkuId
     ClaudeL@contoso.onmicrosoft.com,Claude,Loiselle,Claude Loiselle,US,contoso:ENTERPRISEPACK
     LynneB@contoso.onmicrosoft.com,Lynne,Baxter,Lynne Baxter,US,contoso:ENTERPRISEPACK
     ShawnM@contoso.onmicrosoft.com,Shawn,Melendez,Shawn Melendez,US,contoso:ENTERPRISEPACK
     ```

   >[!NOTE]
   >Kolumnnamnen och deras ordning i den första raden i CSV-filen är godtyckliga. Men se till att ordningen på data i resten av filen matchar ordningsföljden för kolumnnamnen. Och använd kolumnnamnen för parametervärdena i PowerShell för Microsoft 365-kommandot.
    
2. Använd följande syntax:
    
    ```powershell
     Import-Csv -Path <Input CSV File Path and Name> | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId [-Password $_.Password]} | Export-Csv -Path <Output CSV File Path and Name>
    ```

   I det här exemplet skapas användarkonton från filen *C:\My Documents\NewAccounts.csv* och resultatet loggas i en fil med namnet *C:\My Documents\NewAccountResults.csv*.
    
    ```powershell
    Import-Csv -Path "C:\My Documents\NewAccounts.csv" | foreach {New-MsolUser -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -UserPrincipalName $_.UserPrincipalName -UsageLocation $_.UsageLocation -LicenseAssignment $_.AccountSkuId} | Export-Csv -Path "C:\My Documents\NewAccountResults.csv"
    ```

3. Granska utdatafilen för att se resultatet. Vi har inte angett lösenord, så de slumpmässiga lösenord som Microsoft 365 skapade visas i utdatafilen.
    
## <a name="see-also"></a>Se även

[Hantera Microsoft 365-användarkonton,-licenser och-grupper med PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Hantera Microsoft 365 med PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Börja använda PowerShell för Microsoft 365](getting-started-with-microsoft-365-powershell.md)