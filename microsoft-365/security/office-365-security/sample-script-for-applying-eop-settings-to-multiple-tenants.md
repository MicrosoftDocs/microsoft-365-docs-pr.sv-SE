---
title: Exempelskript för EOP-inställningar – flera klientorganisationar
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig hur du använder PowerShell för att använda konfigurationsinställningar för klientorganisationen i Microsoft Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4823ed09cd8a9d72aef21df3d51213cb4512b4f9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288543"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Exempelskript för att tillämpa EOP-inställningar i flera klientorganisationer

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
-  [Exchange Online Protection fristående](exchange-online-protection-overview.md)

Med följande exempelskript kan Microsoft Exchange Online Protection-administratörer (EOP) som hanterar flera innehavare (företag) använda Exchange Online PowerShell för att visa och/eller använda konfigurationsinställningar för sina klientorganisationar.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>Köra ett skript eller en cmdlet på flera klientorganisationar

1. Om du inte redan har gjort det [installerar du Exchange Online V2-modulen.](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)

2. Skapa en CSV-fil med följande information med hjälp av ett kalkylblad (till exempel Excel):

   - Kolumnen Användarnamn: Det konto som du kommer att använda för att ansluta (till `admin@contoso.onmicrosoft.com` exempel).
   - Kolumnen Cmdlet: Cmdleten eller kommandot som ska köras (till exempel `Get-AcceptedDomain` eller `Get-AcceptedDomain | FT Name` ).

   Filen ser ut så här:

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. Spara CSV-filen på en plats som är lätt att hitta (till exempel c:\scripts\inputfile.csv).

4. Kopiera skriptet [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) Anteckningar och spara sedan filen på en plats som är lätt att hitta (till exempel c:\skript).

5. Kör skriptet med följande syntax:

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   Här är ett exempel:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. Varje klientorganisation loggas in på och skriptet körs.

## <a name="runcmdletonmultipletenantsps1"></a>RunCmdletOnMultipleTenants.ps1

> [!NOTE]
> Du kan behöva ändra raden `Connect-IPPSSession` i skriptet så att den matchar din miljö. Office 365 Germany kräver till exempel ett annat _ConnectionUri-värde_ än det aktuella värdet i ett skript. Mer information finns i Ansluta till [Exchange Online Powershell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)

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
