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
ms.openlocfilehash: 46b7c756171da7687568e5135974841d828f45bd
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827463"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Exempelskript för att tillämpa EOP-inställningar i flera klientorganisationer

Med följande exempel skript kan EOP-administratörer (Microsoft Exchange Online Protection) som hanterar flera klient organisationer (företag) använda Windows PowerShell för att tillämpa konfigurations inställningar på sina klient organisationer.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>Köra ett skript eller en cmdlet på flera klient organisationer

1. Skapa en CSV-fil med hjälp av ett program som Excel, till exempel c:\scripts\inputfile.csv):

2. Ange två kolumn namn i CSV-filen: UserName och cmdlet.

3. För varje rad i CSV-filen lägger du till innehavarens administratörs namn i kolumnen UserName och cmdleten som ska köras för den klient organisationen i kolumnen cmdlet. Använd till exempel admin@contoso.com och get-AcceptedDomain.

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

```powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#
# .csv input file sample:
# UserName,Cmdlet
# admin@contoso.com,Get-AcceptedDomain | ft Name
# URI for connecting to remote Windows PowerShell
$URI = "https://ps.protection.outlook.com/powershell-liveid/"
# Get the .csv file name as an argument to this script.
$FilePath = $args[0]
# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath
# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
# Get the current entry's UserName.
$UserName = $Company.UserName
# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet
# Create a PowerShell credential object by using the current entry's UserName. Prompt for the password.
$UserCredential = Get-Credential -username $UserName
# Log on to a new Windows PowerShell session.
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri $URI -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session
# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet
# End the current PowerShell session.
Remove-PsSession -Session $Session
}
```
