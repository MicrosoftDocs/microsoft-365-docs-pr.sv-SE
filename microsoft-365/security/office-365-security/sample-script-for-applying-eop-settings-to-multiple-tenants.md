---
title: Exempel skript för att tillämpa EOP-inställningar på flera klienter
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
description: I följande exempelskript kan Microsoft Exchange Online Protection (EOP) -administratörer som hanterar flera klienter (företag) använda Windows PowerShell för att tillämpa konfigurationsinställningarna på sina klienter.
ms.openlocfilehash: 83199e809b6001b8b5b3b51d2cd15a6e44d83b03
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42809350"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="a47a8-103">Exempel skript för att tillämpa EOP-inställningar på flera klienter</span><span class="sxs-lookup"><span data-stu-id="a47a8-103">Sample script for applying EOP settings to multiple tenants</span></span>

<span data-ttu-id="a47a8-104">I följande exempelskript kan Microsoft Exchange Online Protection (EOP) -administratörer som hanterar flera klienter (företag) använda Windows PowerShell för att tillämpa konfigurationsinställningarna på sina klienter.</span><span class="sxs-lookup"><span data-stu-id="a47a8-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Windows PowerShell to apply configuration settings to their tenants.</span></span>

## <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="a47a8-105">Så här kör du ett skript eller cmdlet på flera klienter</span><span class="sxs-lookup"><span data-stu-id="a47a8-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="a47a8-106">Skapa en CSV-fil med ett program som Excel (till exempel c:\scripts\inputfile.csv):</span><span class="sxs-lookup"><span data-stu-id="a47a8-106">Using an application such as Excel, create a .csv file (for example, c:\scripts\inputfile.csv):</span></span>

2. <span data-ttu-id="a47a8-107">Ange två kolumnnamn: Användarnamn och Cmdlet i CSV-filen.</span><span class="sxs-lookup"><span data-stu-id="a47a8-107">In the .csv file, specify two column names: UserName and Cmdlet.</span></span>

3. <span data-ttu-id="a47a8-108">För varje rad i CSV-filen lägger du till klientens administratörsnamn i kolumnen Användarnamn och cmdleten som ska köras för den klienten i kolumnen Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a47a8-108">For each row in the .csv file, add the tenant's admin name in the UserName column and the cmdlet to run for that tenant in the Cmdlet column.</span></span> <span data-ttu-id="a47a8-109">Använd till exempel admin@contoso.com och Get-AcceptedDomain.</span><span class="sxs-lookup"><span data-stu-id="a47a8-109">For example, use admin@contoso.com and Get-AcceptedDomain.</span></span>

4. <span data-ttu-id="a47a8-110">Kopiera [Skriptet RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) till en redigerare som Anteckningar och spara sedan filen på en plats (till exempel c:\scripts) som gör PS1-filer enkla att hitta.</span><span class="sxs-lookup"><span data-stu-id="a47a8-110">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script to an editor like Notepad, and then save the file to a location (like c:\scripts) that makes .ps1 files easy to find.</span></span>

5. <span data-ttu-id="a47a8-111">Kör skriptet med hjälp av följande syntax:</span><span class="sxs-lookup"><span data-stu-id="a47a8-111">Run the script by using the following syntax:</span></span>

   ```Powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="a47a8-112">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="a47a8-112">Here's an example:</span></span>

   ```Powershell
   & "c:\scripts\RunCmdletOnMultipleTenanats.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="a47a8-113">Varje klient loggas in på och cmdleten kommer att köras.</span><span class="sxs-lookup"><span data-stu-id="a47a8-113">Each tenant will be logged on to, and the cmdlet will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="a47a8-114">RunCmdletPåFleraHyresgäster.ps1</span><span class="sxs-lookup"><span data-stu-id="a47a8-114">RunCmdletOnMultipleTenants.ps1</span></span>

```Powershell
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
