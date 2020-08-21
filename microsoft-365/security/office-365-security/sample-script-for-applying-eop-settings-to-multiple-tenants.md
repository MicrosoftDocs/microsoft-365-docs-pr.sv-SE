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
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="94aad-103">Exempelskript för att tillämpa EOP-inställningar i flera klientorganisationer</span><span class="sxs-lookup"><span data-stu-id="94aad-103">Sample script for applying EOP settings to multiple tenants</span></span>

<span data-ttu-id="94aad-104">Med följande exempel skript kan EOP-administratörer (Microsoft Exchange Online Protection) som hanterar flera klient organisationer (företag) använda Windows PowerShell för att tillämpa konfigurations inställningar på sina klient organisationer.</span><span class="sxs-lookup"><span data-stu-id="94aad-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Windows PowerShell to apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="94aad-105">Köra ett skript eller en cmdlet på flera klient organisationer</span><span class="sxs-lookup"><span data-stu-id="94aad-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="94aad-106">Skapa en CSV-fil med hjälp av ett program som Excel, till exempel c:\scripts\inputfile.csv):</span><span class="sxs-lookup"><span data-stu-id="94aad-106">Using an application such as Excel, create a .csv file (for example, c:\scripts\inputfile.csv):</span></span>

2. <span data-ttu-id="94aad-107">Ange två kolumn namn i CSV-filen: UserName och cmdlet.</span><span class="sxs-lookup"><span data-stu-id="94aad-107">In the .csv file, specify two column names: UserName and Cmdlet.</span></span>

3. <span data-ttu-id="94aad-108">För varje rad i CSV-filen lägger du till innehavarens administratörs namn i kolumnen UserName och cmdleten som ska köras för den klient organisationen i kolumnen cmdlet.</span><span class="sxs-lookup"><span data-stu-id="94aad-108">For each row in the .csv file, add the tenant's admin name in the UserName column and the cmdlet to run for that tenant in the Cmdlet column.</span></span> <span data-ttu-id="94aad-109">Använd till exempel admin@contoso.com och get-AcceptedDomain.</span><span class="sxs-lookup"><span data-stu-id="94aad-109">For example, use admin@contoso.com and Get-AcceptedDomain.</span></span>

4. <span data-ttu-id="94aad-110">Kopiera [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) -skript till anteckningar och spara sedan filen på en plats som är lätt att hitta (till exempel c:\Scripts).</span><span class="sxs-lookup"><span data-stu-id="94aad-110">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script into Notepad, and then save the file to a location that's easy to find  (for example, c:\scripts).</span></span>

5. <span data-ttu-id="94aad-111">Kör skriptet genom att använda följande syntax:</span><span class="sxs-lookup"><span data-stu-id="94aad-111">Run the script by using the following syntax:</span></span>

   ```powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="94aad-112">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="94aad-112">Here's an example:</span></span>

   ```powershell
   & "c:\scripts\RunCmdletOnMultipleTenants.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="94aad-113">Varje klient organisation kommer att vara inloggad på och skriptet körs.</span><span class="sxs-lookup"><span data-stu-id="94aad-113">Each tenant will be logged on to, and the script will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="94aad-114">RunCmdletOnMultipleTenants.ps1</span><span class="sxs-lookup"><span data-stu-id="94aad-114">RunCmdletOnMultipleTenants.ps1</span></span>

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
