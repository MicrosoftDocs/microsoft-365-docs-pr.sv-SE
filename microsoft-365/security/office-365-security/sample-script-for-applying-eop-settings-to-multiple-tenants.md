---
title: Exempel skript för EOP-inställningar-flera innehavare
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
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln lär du dig hur du använder PowerShell för att tillämpa konfigurations inställningar för klient organisationer i Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: dbb4135c89ac8d351c40bd7d9ce5301500a9b81b
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376573"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Exempelskript för att tillämpa EOP-inställningar i flera klientorganisationer

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Med följande exempel skript kan du använda Exchange Online PowerShell för att visa och/eller tillämpa konfigurations inställningar för sina klient organisationer i Microsoft Exchange Online Protection (EOP)-administratörer som hanterar flera klient organisationer.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>Köra ett skript eller en cmdlet på flera klient organisationer

1. Om du inte redan har gjort [det installerar du Exchange Online v2-modulen](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

2. Använd ett kalkyl blads program (till exempel Excel) och skapa en CSV-fil med följande information:

   - Kolumnen UserName: det konto som du använder för att ansluta (till exempel `admin@contoso.onmicrosoft.com` ).
   - Cmdlet-kolumn: cmdleten eller kommandot som ska köras (till exempel `Get-AcceptedDomain` eller `Get-AcceptedDomain | FT Name` ).

   Filen ser ut så här:

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. Spara CSV-filen på en plats som är lätt att hitta (till exempel c:\scripts\inputfile.csv).

4. Kopiera [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) -skript till anteckningar och spara sedan filen på en plats som är lätt att hitta (till exempel c:\Scripts).

5. Kör skriptet genom att använda följande syntax:

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   Här är ett exempel:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. Varje klient organisation kommer att vara inloggad på och skriptet körs.

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

> [!NOTE]
> Du kan behöva ändra `Connect-IPPSSession` raden i skriptet för att passa din miljö. Office 365 Germany kräver till exempel ett annat _ConnectionUri_ -värde än det aktuella värdet i ett skript. Mer information finns i ansluta till [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
#
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
#
# UserName,Cmdlet
# admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
# admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name

# Get the .csv file name as an argument to this script.
$FilePath = $args[0]

# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath

# Load the EXO V2 module
Import-Module ExchangeOnlineManagement

# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
  
# Get the current entry's UserName.
$UserName = $Company.UserName

# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet

# Connect to EOP PowerShell by using the current entry's UserName. Prompt for the password.
Connect-IPPSSession -UserPrincipalName $UserName -ConnectionUri https://ps.protection.outlook.com/powershell-liveid/

# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet

# End the current PowerShell session.
Disconnect-ExchangeOnline -Confirm:$false
}
```
