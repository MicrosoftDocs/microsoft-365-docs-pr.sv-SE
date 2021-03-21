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
description: I den här artikeln får du lära dig hur du använder PowerShell för att tillämpa konfigurationsinställningar för klientorganisationen i Microsoft Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77a1dce25901845628f8148c44a0d0783088255e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928514"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="4e336-103">Exempelskript för att tillämpa EOP-inställningar i flera klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="4e336-103">Sample script for applying EOP settings to multiple tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4e336-104">**Gäller för**</span><span class="sxs-lookup"><span data-stu-id="4e336-104">**Applies to**</span></span>
-  [<span data-ttu-id="4e336-105">Exchange Online Protection fristående</span><span class="sxs-lookup"><span data-stu-id="4e336-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="4e336-106">Med följande exempelskript kan Administratörer för Microsoft Exchange Online Protection (EOP) som hanterar flera klientorganisationen (företag) använda Exchange Online PowerShell för att visa och/eller använda konfigurationsinställningar för sina klientorganisationar.</span><span class="sxs-lookup"><span data-stu-id="4e336-106">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Exchange Online PowerShell to view and/or apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="4e336-107">Köra ett skript eller en cmdlet på flera klientorganisationar</span><span class="sxs-lookup"><span data-stu-id="4e336-107">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="4e336-108">Om du inte redan har gjort det [installerar du modulen Exchange Online V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span><span class="sxs-lookup"><span data-stu-id="4e336-108">If you haven't already, [install the Exchange Online V2 module](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

2. <span data-ttu-id="4e336-109">Med ett kalkylbladsprogram (till exempel Excel) skapar du en CSV-fil med följande information:</span><span class="sxs-lookup"><span data-stu-id="4e336-109">Using an spreadsheet app (for example, Excel), create a .csv file with the following details:</span></span>

   - <span data-ttu-id="4e336-110">Kolumnen UserName: Det konto som du kommer att använda för att ansluta (till exempel `admin@contoso.onmicrosoft.com` ).</span><span class="sxs-lookup"><span data-stu-id="4e336-110">UserName column: The account that you'll use to connect (for example, `admin@contoso.onmicrosoft.com`).</span></span>
   - <span data-ttu-id="4e336-111">Kolumnen Cmdlet: Cmdleten eller kommandot som ska köras (till exempel `Get-AcceptedDomain` eller `Get-AcceptedDomain | FT Name` ).</span><span class="sxs-lookup"><span data-stu-id="4e336-111">Cmdlet column: The cmdlet or command to run (for example, `Get-AcceptedDomain` or `Get-AcceptedDomain | FT Name`).</span></span>

   <span data-ttu-id="4e336-112">Filen ser ut så här:</span><span class="sxs-lookup"><span data-stu-id="4e336-112">The file will look like this:</span></span>

   ```text
   UserName,Cmdlet
   admin@contoso.onmicrosoft.com,Get-AcceptedDomain | FT Name
   admin@fabrikam.onmicrosoft.com,Get-AcceptedDomain | FT Name
   ```

3. <span data-ttu-id="4e336-113">Spara CSV-filen på en plats som är lätt att hitta (till exempel på c:\scripts\inputfile.csv).</span><span class="sxs-lookup"><span data-stu-id="4e336-113">Save the .csv file in a location that's easy to find (for example, c:\scripts\inputfile.csv).</span></span>

4. <span data-ttu-id="4e336-114">Kopiera [ skriptetRunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) Anteckningar och spara sedan filen på en plats som är lätt att hitta (till exempel c:\skript).</span><span class="sxs-lookup"><span data-stu-id="4e336-114">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find (for example, c:\scripts).</span></span>

5. <span data-ttu-id="4e336-115">Kör skriptet med följande syntax:</span><span class="sxs-lookup"><span data-stu-id="4e336-115">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="4e336-116">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="4e336-116">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="4e336-117">Varje klientorganisation loggas in på och skriptet körs.</span><span class="sxs-lookup"><span data-stu-id="4e336-117">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="4e336-118">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="4e336-118">RunCmdletOnMultipleTenants.ps1</span></span>

> [!NOTE]
> <span data-ttu-id="4e336-119">Du kan behöva ändra raden `Connect-IPPSSession` i skriptet så att den matchar din miljö.</span><span class="sxs-lookup"><span data-stu-id="4e336-119">You might need to modify the `Connect-IPPSSession` line in the script to match your environment.</span></span> <span data-ttu-id="4e336-120">Till exempel kräver Office 365 Germany ett annat _ConnectionUri-värde_ än det aktuella värdet i ett skript.</span><span class="sxs-lookup"><span data-stu-id="4e336-120">For example, Office 365 Germany requires a different _ConnectionUri_ value than the current value in a script.</span></span> <span data-ttu-id="4e336-121">Mer information finns i Ansluta till [Exchange Online Powershell.](/powershell/exchange/connect-to-exchange-online-protection-powershell)</span><span class="sxs-lookup"><span data-stu-id="4e336-121">For details, see Connect to [Exchange Online Powershell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

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