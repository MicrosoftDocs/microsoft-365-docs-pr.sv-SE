---
title: Exempel på skript för EOP-inställningar – flera klienter
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
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig hur du använder PowerShell för att tillämpa konfigurationsinställningar för dina klienter i Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: c25bafe9ece71264931d8f059dd726147a6d28a4
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209145"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>Exempelskript för att tillämpa EOP-inställningar i flera klientorganisationer

Med följande exempelskript kan Microsoft Exchange Online Protection (EOP) administratörer som hanterar flera klienter (företag) använda Windows PowerShell för att tillämpa konfigurationsinställningar för sina klienter.

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>Så här kör du ett skript eller en cmdlet på flera klienter

1. Skapa en CSV-fil med hjälp av ett program som Excel (till exempel c:\scripts\inputfile.csv):

2. I CSV-filen anger du två kolumnnamn: Användarnamn och Cmdlet.

3. För varje rad i CSV-filen lägger du till klientens administratörsnamn i kolumnen Användarnamn och den cmdlet som ska köras för klienten i kolumnen Cmdlet. Använd till exempel admin@contoso.com och Get-AcceptedDomain.

4. Kopiera skriptet [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) till Anteckningar och spara sedan filen på en plats som är lätt att hitta (till exempel c:\scripts).

5. Kör skriptet med hjälp av följande syntax:

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   Här är ett exempel:

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenanats.ps1" "c:\scripts\inputfile.csv"
   ```

6. Varje klient loggas in på och skriptet körs.

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
