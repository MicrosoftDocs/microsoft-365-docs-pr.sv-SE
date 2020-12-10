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
ms.openlocfilehash: b18fc71171a93e2a2f415800bcf2b5abd5c5a526
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615870"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="6076e-103">Exempelskript för att tillämpa EOP-inställningar i flera klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="6076e-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="6076e-104">Med följande exempel skript kan du använda Exchange Online PowerShell för att visa och/eller tillämpa konfigurations inställningar för sina klient organisationer i Microsoft Exchange Online Protection (EOP)-administratörer som hanterar flera klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="6076e-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="6076e-105">Köra ett skript eller en cmdlet på flera klient organisationer</span><span class="sxs-lookup"><span data-stu-id="6076e-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="6076e-106">Om du inte redan har gjort [det installerar du Exchange Online v2-modulen](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span><span class="sxs-lookup"><span data-stu-id="6076e-106">If you haven't already, [install the Exchange Online V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="6076e-107">Använd ett kalkyl blads program (till exempel Excel) och skapa en CSV-fil med följande information:</span><span class="sxs-lookup"><span data-stu-id="6076e-107">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="6076e-108">Kolumnen UserName: det konto som du använder för att ansluta (till exempel `admin@contoso.onmicrosoft.com` ).</span><span class="sxs-lookup"><span data-stu-id="6076e-108">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="6076e-109">Cmdlet-kolumn: cmdleten eller kommandot som ska köras (till exempel `Get-AcceptedDomain` eller `Get-AcceptedDomain | FT Name` ).</span><span class="sxs-lookup"><span data-stu-id="6076e-109">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="6076e-110">Filen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="6076e-110">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="6076e-111">Spara CSV-filen på en plats som är lätt att hitta (till exempel c:\scripts\inputfile.csv).</span><span class="sxs-lookup"><span data-stu-id="6076e-111">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="6076e-112">Kopiera [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) -skript till anteckningar och spara sedan filen på en plats som är lätt att hitta (till exempel c:\Scripts).</span><span class="sxs-lookup"><span data-stu-id="6076e-112">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="6076e-113">Kör skriptet genom att använda följande syntax:</span><span class="sxs-lookup"><span data-stu-id="6076e-113">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="6076e-114">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="6076e-114">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="6076e-115">Varje klient organisation kommer att vara inloggad på och skriptet körs.</span><span class="sxs-lookup"><span data-stu-id="6076e-115">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="6076e-116">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="6076e-116">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="6076e-117">Du kan behöva ändra `Connect-IPPSSession` raden i skriptet för att passa din miljö.</span><span class="sxs-lookup"><span data-stu-id="6076e-117">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="6076e-118">Office 365 Germany kräver till exempel ett annat _ConnectionUri_ -värde än det aktuella värdet i ett skript.</span><span class="sxs-lookup"><span data-stu-id="6076e-118">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="6076e-119">Mer information finns i ansluta till [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="6076e-119">For details, see Connect to [Exchange Online Powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

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
