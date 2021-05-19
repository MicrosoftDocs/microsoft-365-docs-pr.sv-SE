---
title: Skapa och publicera kvarhållningsetiketter med PowerShell
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du använder PowerShell för att skapa och publicera kvarhållningsetiketter från kommandoraden, separat från Microsoft 365 Efterlevnadscenter.
ms.openlocfilehash: 1c3a1e1b9e363659b276d2f11a929308f43737b3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162022"
---
# <a name="create-and-publish-retention-labels-by-using-powershell"></a><span data-ttu-id="b7b22-103">Skapa och publicera kvarhållningsetiketter med PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7b22-103">Create and publish retention labels by using PowerShell</span></span>

><span data-ttu-id="b7b22-104">*[Licensieringsvägledning för Microsoft 365 för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="b7b22-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="b7b22-105">När du bestämde dig för att använda [kvarhållningsetiketter](retention.md) som metod för att bevara eller ta bort dokument och e-postmeddelanden i Microsoft 365 kanske du insåg att du har många, eventuellt hundratals, kvarhållningsetiketter att skapa och publicera.</span><span class="sxs-lookup"><span data-stu-id="b7b22-105">After you've decided to use [retention labels](retention.md) to help you keep or delete documents and emails in Microsoft 365, you might have realized that you have many and possibly hundreds of retention labels to create and publish.</span></span> <span data-ttu-id="b7b22-106">Den rekommenderade metoden för att skapa kvarhållningsetiketter i stor skala är att använda [filplanen](file-plan-manager.md) från Microsoft 365 Efterlevnadscenter.</span><span class="sxs-lookup"><span data-stu-id="b7b22-106">The recommended method to create retention labels at scale is by using [file plan](file-plan-manager.md) from the Microsoft 365 compliance center.</span></span> <span data-ttu-id="b7b22-107">Men du kan också använda [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="b7b22-107">However, you can also use [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels).</span></span>
  
<span data-ttu-id="b7b22-108">Använd informationen, mallfilerna och exemplen samt skripten i den här artikeln som hjälp för att skapa många kvarhållningsetiketter på en gång och publicera dem i principer för kvarhållningsetiketter.</span><span class="sxs-lookup"><span data-stu-id="b7b22-108">Use the information, template files and examples, and script in this article to help you bulk-create retention labels and publish them in retention label policies.</span></span> <span data-ttu-id="b7b22-109">Kvarhållningsetiketterna kan sedan [användas av administratörer och användare](create-apply-retention-labels.md#how-to-apply-published-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="b7b22-109">Then, the retention labels can be [applied by administrators and users](create-apply-retention-labels.md#how-to-apply-published-retention-labels).</span></span>

<span data-ttu-id="b7b22-110">De angivna instruktionerna stöder inte kvarhållningsetiketter som används automatiskt.</span><span class="sxs-lookup"><span data-stu-id="b7b22-110">The supplied instructions don't support retention labels that are auto-applied.</span></span>

<span data-ttu-id="b7b22-111">Översikt:</span><span class="sxs-lookup"><span data-stu-id="b7b22-111">Overview:</span></span> 

1. <span data-ttu-id="b7b22-112">Skapa en lista med dina kvarhållningsetiketter och en lista över deras kvarhållningsetikettprinciper i Excel.</span><span class="sxs-lookup"><span data-stu-id="b7b22-112">In Excel, create a list of your retention labels and a list of their retention label policies.</span></span>

2. <span data-ttu-id="b7b22-113">Använd PowerShell för att skapa kvarhållningsetiketter och principer för kvarhållningsetiketter i dessa listor.</span><span class="sxs-lookup"><span data-stu-id="b7b22-113">Use PowerShell to create the retention labels and retention label policies in those lists.</span></span>
  
## <a name="disclaimer"></a><span data-ttu-id="b7b22-114">Ansvarsfriskrivning</span><span class="sxs-lookup"><span data-stu-id="b7b22-114">Disclaimer</span></span>

<span data-ttu-id="b7b22-115">Exempelskripten i den här artikeln har ingen support enligt något standardsupportprogram eller någon standardsupporttjänst från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b7b22-115">The sample scripts provided in this article aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="b7b22-116">Exempelskripten ges i befintligt skick utan garantier av något slag.</span><span class="sxs-lookup"><span data-stu-id="b7b22-116">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="b7b22-117">Vidare frånsäger sig Microsoft alla underförstådda garantier, inklusive, utan begränsning, underförstådda garantier om säljbarhet eller lämplighet för ett visst ändamål.</span><span class="sxs-lookup"><span data-stu-id="b7b22-117">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="b7b22-118">Hela risken i samband med användningen av eller prestandan hos exempelskripten och dokumentationen vilar på dig.</span><span class="sxs-lookup"><span data-stu-id="b7b22-118">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="b7b22-119">Under inga omständigheter ska Microsoft, dess upphovspersoner eller någon annan som är involverad i skapandet, produktionen eller leveransen av skripten hållas ansvariga för någon som helst skada (inklusive, men inte begränsat till, skador avseende utebliven vinst, driftavbrott, förlust av affärsinformation eller annan ekonomisk skada) som uppstår till följd av användning eller svårighet eller omöjlighet att använda exempelskripten eller dokumentationen, även om Microsoft har fått information om att sådana skador kan uppstå.</span><span class="sxs-lookup"><span data-stu-id="b7b22-119">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-create-a-csv-file-for-the-retention-labels"></a><span data-ttu-id="b7b22-120">Steg 1: Skapa en .csv-fil för kvarhållningsetiketterna</span><span class="sxs-lookup"><span data-stu-id="b7b22-120">Step 1: Create a .csv file for the retention labels</span></span>

1. <span data-ttu-id="b7b22-121">Kopiera följande .csv-exempelfil med en mall och exempelposter för fyra olika kvarhållningsetiketter, och klistra in dem i Excel.</span><span class="sxs-lookup"><span data-stu-id="b7b22-121">Copy the following sample .csv file for a template and example entries for four different retention labels, and paste them into Excel.</span></span> 

2. <span data-ttu-id="b7b22-122">Konvertera texten till kolumner: fliken **Data** \> **Text till kolumner** \> **Avgränsade fält** \> **Komma** \> **Allmänt**</span><span class="sxs-lookup"><span data-stu-id="b7b22-122">Convert the text to columns: **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**</span></span>

2. <span data-ttu-id="b7b22-123">Ersätt exemplen med poster för dina egna kvarhållningsetiketter och inställningar.</span><span class="sxs-lookup"><span data-stu-id="b7b22-123">Replace the examples with entries for your own retention labels and settings.</span></span> <span data-ttu-id="b7b22-124">Mer information om parametervärdena finns i [New-ComplianceTag](/powershell/module/exchange/new-compliancetag).</span><span class="sxs-lookup"><span data-stu-id="b7b22-124">For more information about the parameter values, see [New-ComplianceTag](/powershell/module/exchange/new-compliancetag).</span></span>

3. <span data-ttu-id="b7b22-125">Spara kalkylbladet som en .csv-fil på en plats som är lätt att hitta i ett senare steg.</span><span class="sxs-lookup"><span data-stu-id="b7b22-125">Save the worksheet as a .csv file in a location that's easy to find for a later step.</span></span> <span data-ttu-id="b7b22-126">Till exempel: C:\>Scripts\Labels.csv</span><span class="sxs-lookup"><span data-stu-id="b7b22-126">For example: C:\>Scripts\Labels.csv</span></span>

  
<span data-ttu-id="b7b22-127">Kommentarer:</span><span class="sxs-lookup"><span data-stu-id="b7b22-127">Notes:</span></span>

- <span data-ttu-id="b7b22-128">Om .csv-filen innehåller en kvarhållningsetikett med samma namn som en som redan finns hoppar skriptet över att skapa den kvarhållningsetiketten.</span><span class="sxs-lookup"><span data-stu-id="b7b22-128">If the .csv file contains a retention label with the same name as one that already exists, the script skips creating that retention label.</span></span> <span data-ttu-id="b7b22-129">Inga dubbletter av kvarhållningsetiketter skapas.</span><span class="sxs-lookup"><span data-stu-id="b7b22-129">No duplicate retention labels are created.</span></span>
    
- <span data-ttu-id="b7b22-130">Ändra inte och byt inte namn på kolumnrubrikerna från .csv-exempelfilen eftersom skriptet då misslyckas.</span><span class="sxs-lookup"><span data-stu-id="b7b22-130">Don't change or rename the column headers from the sample .csv file provided, or the script will fail.</span></span>
    
### <a name="sample-csv-file-for-retention-labels"></a><span data-ttu-id="b7b22-131">.csv-exempelfil för kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="b7b22-131">Sample .csv file for retention labels</span></span>

```
Name (Required),Comment (Optional),IsRecordLabel (Required),RetentionAction (Optional),RetentionDuration (Optional),RetentionType (Optional),ReviewerEmail (Optional)
LabelName_t_1,Record - keep and delete - 2 years,$true,KeepAndDelete,730,CreationAgeInDays,
LabelName_t_2,Keep and delete tag - 7 years,$false,KeepAndDelete,2555,ModificationAgeInDays,
LabelName_t_3,5 year delete,$false,Delete,1825,TaggedAgeInDays,
LabelName_t_4,Record label tag - financial,$true,Keep,730,CreationAgeInDays,
```

## <a name="step-2-create-a-csv-file-for-the-retention-label-policies"></a><span data-ttu-id="b7b22-132">Steg 2: Skapa en .csv-fil för principerna för kvarhållningsetiketterna</span><span class="sxs-lookup"><span data-stu-id="b7b22-132">Step 2: Create a .csv file for the retention label policies</span></span>

1. <span data-ttu-id="b7b22-133">Kopiera följande .csv-exempelfil med en mall och exempelposter för tre olika principer för kvarhållningsetiketter, och klistra in dem i Excel.</span><span class="sxs-lookup"><span data-stu-id="b7b22-133">Copy the following sample .csv file for a template and example entries for three different retention label policies, and paste them into Excel.</span></span> 

2. <span data-ttu-id="b7b22-134">Konvertera texten till kolumner: fliken **Data** \> **Text till kolumner** \> **Avgränsade fält** \> **Komma** \> **Allmänt**</span><span class="sxs-lookup"><span data-stu-id="b7b22-134">Convert the text to columns: **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**</span></span>

2. <span data-ttu-id="b7b22-135">Ersätt exemplen med poster för dina egna principer för kvarhållningsetiketter och deras inställningar.</span><span class="sxs-lookup"><span data-stu-id="b7b22-135">Replace the examples with entries for your own retention label policies and their settings.</span></span> <span data-ttu-id="b7b22-136">Mer information om parametervärdena för den här cmdleten finns i [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy).</span><span class="sxs-lookup"><span data-stu-id="b7b22-136">For more information about the parameter values for this cmdlet, see [New-RetentionCompliancePolicy](/powershell/module/exchange/new-retentioncompliancepolicy).</span></span>

3. <span data-ttu-id="b7b22-137">Spara kalkylbladet som en .csv-fil på en plats som är lätt att hitta i ett senare steg.</span><span class="sxs-lookup"><span data-stu-id="b7b22-137">Save the worksheet as a .csv file in a location that's easy to find for a later step.</span></span> <span data-ttu-id="b7b22-138">Till exempel: `<path>Policies.csv`</span><span class="sxs-lookup"><span data-stu-id="b7b22-138">For example: `<path>Policies.csv`</span></span>


<span data-ttu-id="b7b22-139">Kommentarer:</span><span class="sxs-lookup"><span data-stu-id="b7b22-139">Notes:</span></span>
  
- <span data-ttu-id="b7b22-140">Om .csv-filen innehåller en princip för kvarhållningsetiketter med samma namn som en som redan finns hoppar skriptet över att skapa den principen för kvarhållningsetiketter.</span><span class="sxs-lookup"><span data-stu-id="b7b22-140">If the .csv file contains a retention label policy with the same name as one that already exists, the script skips creating that retention label policy.</span></span> <span data-ttu-id="b7b22-141">Inga dubbletter av principer för kvarhållningsetiketter skapas.</span><span class="sxs-lookup"><span data-stu-id="b7b22-141">No duplicate retention label policies are created.</span></span>
    
- <span data-ttu-id="b7b22-142">Ändra inte och byt inte namn på kolumnrubrikerna från .csv-exempelfilen eftersom skriptet då misslyckas.</span><span class="sxs-lookup"><span data-stu-id="b7b22-142">Don't change or rename the column headers from the sample .csv file provided, or the script will fail.</span></span>
    
### <a name="sample-csv-file-for-retention-policies"></a><span data-ttu-id="b7b22-143">.csv-exempelfil för principer för kvarhållningsetiketter</span><span class="sxs-lookup"><span data-stu-id="b7b22-143">Sample .csv file for retention policies</span></span>

```
Policy Name (Required),PublishComplianceTag (Required),Comment (Optional),Enabled (Required),ExchangeLocation (Optional),ExchangeLocationException (Optional),ModernGroupLocation (Optional),ModernGroupLocationException (Optional),OneDriveLocation (Optional),OneDriveLocationException (Optional),PublicFolderLocation (Optional),SharePointLocation (Optional),SharePointLocationException (Optional),SkypeLocation (Optional),SkypeLocationException (Optional)
Publishing Policy Red1,"LabelName_t_1, LabelName_t_2, LabelName_t_3, LabelName_t_4",N/A,$true,All,,All,,All,,,All,,,
Publishing Policy Orange1,"LabelName_t_1, LabelName_t_2",N/A,$true,All,,,,,,,,,,
Publishing Policy Yellow1,"LabelName_t_3, LabelName_t_4",N/A,$false,All,,,,,,,,,,
```

## <a name="step-3-create-the-powershell-script"></a><span data-ttu-id="b7b22-144">Steg 3: Skapa PowerShell-skriptet</span><span class="sxs-lookup"><span data-stu-id="b7b22-144">Step 3: Create the PowerShell script</span></span>

1. <span data-ttu-id="b7b22-145">Kopiera och klistra in följande PowerShell-skript i Anteckningar.</span><span class="sxs-lookup"><span data-stu-id="b7b22-145">Copy and paste the following PowerShell script into Notepad.</span></span>

2. <span data-ttu-id="b7b22-146">Spara filen med filnamnstillägget **.ps1** på en plats som är lätt att hitta.</span><span class="sxs-lookup"><span data-stu-id="b7b22-146">Save the file by using a file name extension of **.ps1** in a location that's easy to find.</span></span> <span data-ttu-id="b7b22-147">Till exempel: `<path>CreateRetentionSchedule.ps1`</span><span class="sxs-lookup"><span data-stu-id="b7b22-147">For example: `<path>CreateRetentionSchedule.ps1`</span></span>

<span data-ttu-id="b7b22-148">Kommentarer:</span><span class="sxs-lookup"><span data-stu-id="b7b22-148">Notes:</span></span>

- <span data-ttu-id="b7b22-149">Skriptet uppmanar dig att ange de två källfiler du skapade i de två föregående stegen:</span><span class="sxs-lookup"><span data-stu-id="b7b22-149">The script prompts you to provide the two source files that you created in the previous two steps:</span></span>
    - <span data-ttu-id="b7b22-150">Om du inte anger källfilen för att skapa kvarhållningsetiketterna går skriptet vidare till att skapa principerna för kvarhållningsetiketterna.</span><span class="sxs-lookup"><span data-stu-id="b7b22-150">If you don't specify the source file to create the retention labels, the script moves on to create the retention label policies.</span></span> 
    - <span data-ttu-id="b7b22-151">Om du inte anger källfilen för att skapa principerna för kvarhållningsetiketterna skapar skriptet endast kvarhållningsetiketterna.</span><span class="sxs-lookup"><span data-stu-id="b7b22-151">If you don't specify the source file to create the retention label policies, the script creates the retention labels only.</span></span>

- <span data-ttu-id="b7b22-152">Skriptet genererar en loggfil som registrerar varje åtgärd som vidtas och om åtgärden lyckades eller misslyckades.</span><span class="sxs-lookup"><span data-stu-id="b7b22-152">The script generates a log file that records each action it took and whether the action succeeded or failed.</span></span> <span data-ttu-id="b7b22-153">Det finns anvisningar för hur du hittar loggfilen i det sista steget.</span><span class="sxs-lookup"><span data-stu-id="b7b22-153">See the final step for instructions how to locate this log file.</span></span>

### <a name="powershell-script"></a><span data-ttu-id="b7b22-154">PowerShell-skript</span><span class="sxs-lookup"><span data-stu-id="b7b22-154">PowerShell script</span></span>

```Powershell
<#
. Steps: Import and publish retention labels
    ○ Load retention labels csv file 
    ○ Validate csv file input
    ○ Create retention labels
    ○ Create retention policies
    ○ Publish retention labels for the policies
    ○ Generate the log for retention labels and policies creation
    ○ Generate the csv result for the labels and policies created
. Syntax
    .\Publish-ComplianceTag.ps1 [-LabelListCSV <string>] [-PolicyListCSV <string>] 
. Detailed Description
    1) [-LabelListCSV <string>]
    -LabelListCSV ".\SampleInputFile_LabelList.csv"
    Load compliance tag for creation.
    2) [-PolicyListCSV <string>]
    -PolicyListCSV ".\SampleInputFile_PolicyList.csv"
    Load compliance tag for creation.
#>
param (
    [Parameter(Mandatory = $true)]
    [string]$LabelListCSV = "",
    [Parameter(Mandatory = $true)]
    [string]$PolicyListCSV = "",
    [Switch]$ResultCSV
)
# -------------------
# File operation
# -------------------
Function FileExist
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath,
        [Switch]$Warning
    )
    $inputFileExist = Test-Path $FilePath
    if (!$inputFileExist)
    {
        if ($Warning -eq $false) 
        { 
            WriteToLog -Type "Failed" -Message "[File: $FilePath] The file doesn't exist"
            throw 
        }
        else 
        { 
            WriteToLog -Type "Warning" -Message "[File: $FilePath] The file doesn't exist"
        }
    }
    else
    {
        WriteToLog -Type "Succeed" -Message "[File: $FilePath] The file is found"
    }
}
# -------------------
# Log operation
# -------------------
Function WriteToLog
{
    Param(
        # Message want to write to log file
        [Parameter(Mandatory = $true)]
        [String]$Message,
        # "Succeed" or "Faild"
        [String]$Type = "Message"
    )
    $date = Get-Date -Format 'HH:mm:ss'
    $logInfo = $date + " - [$Type] " + $Message
    $logInfo | Out-File -FilePath $logfilePath -Append
    if ($Type -eq "Succeed") { Write-Host $logInfo -ForegroundColor Green }
    elseif ($Type -eq "Failed") { Write-Host $logInfo -ForegroundColor Red }
    elseif ($Type -eq "Warning") { Write-Host $logInfo -ForegroundColor Yellow }
    elseif ($Type -eq "Start") { Write-Host $logInfo -ForegroundColor Cyan }
    else { Write-Verbose $logInfo }
}
Function Create-Log
{
    Param(
        # Log folder Root
        [Parameter(Mandatory = $true)]
        [String]$LogFolderRoot,
        # The function Log file for
        [Parameter(Mandatory = $true)]
        [String]$LogFunction
    )
    $logFolderPath = "$LogFolderRoot\logfiles"
    $folderExist = Test-Path "$logFolderPath"
    if (!$folderExist)
    {
        $folder = New-Item "$logFolderPath" -type directory
    }
    $date = Get-Date -Format 'MMddyyyy_HHmmss'
    $logfilePath = "$logFolderPath\Log_{0}_{1}.txt" -f $LogFunction, $date
    Write-Verbose "Log file is written to: $logfilePath"
    $logfile = New-Item $logfilePath  -type file
    return $logfilePath
}
Function Create-ResultCSV
{
    Param(
        # Result folder Root
        [Parameter(Mandatory = $true)]
        [String]$ResultFolderRoot,
        # The function Result file for
        [Parameter(Mandatory = $true)]
        [String]$ResultFunction
    )
    $retFolderPath = "$ResultFolderRoot\logfiles"
    $folderExist = Test-Path "$retFolderPath"
    if (!$folderExist)
    {
        $folder = New-Item "$retFolderPath" -type directory
    }
    $date = Get-Date -Format 'MMddyyyy_HHmmss'
    $retfilePath = "$retFolderPath\Result_{0}_{1}.csv" -f $ResultFunction, $date
    Write-Verbose "Result file is written to: $retfilePath"
    $retfile = New-Item $retfilePath  -type file
    return $retfilePath
}
# -------------------
# Prepare Log File
# -------------------
$scriptPath = '.\'
$logfilePath = Create-Log -LogFolderRoot $scriptPath -LogFunction "Publish_Compliance_Tag"
if ($ResultCSV)
{
    $tagRetFile = Create-ResultCSV -ResultFolderRoot $scriptPath -ResultFunction "Tag_Creation"
    $tagPubRetFile = Create-ResultCSV -ResultFolderRoot $scriptPath -ResultFunction "Tag_Publish"
}
# -------------------
# Invoke Powershell cmdlet
# -------------------
Function InvokePowerShellCmdlet
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$CmdLet
    )
    try
    {
        WriteToLog -Type "Start" -Message "Execute Cmdlet : '$CmdLet'" 
        return Invoke-Expression $CmdLet -ErrorAction SilentlyContinue
    }
    catch
    {
        WriteToLog -Type "Failed" "Failed to execute cmdlet!"
        WriteToLog -Type "Failed" $error[0]
        return $null
    }
}
# -------------------
# Create Compliance Tag
# -------------------
Function CreateComplianceTag
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath
    )
    
    WriteToLog -Type "Start" "Start to create Compliance Tag"
    FileExist $FilePath
    
    # TODO Validate CSV file for the Header
    try
    {
        # Import csv
        $labels = Import-Csv $FilePath
        # Retrieve existing compliance tags
        $tags = InvokePowerShellCmdlet "Get-ComplianceTag"
        foreach($lab in $labels)
        {
            # Cmdlet parameters
            $para = [String]::Empty;
            $name = [String]::Empty;
            $cmdlet = 'New-ComplianceTag'
            if ([String]::IsNullOrEmpty($lab.'Name (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
                $name = $lab.'Name (Required)'
                $cmdlet += " -Name '" + $name + "'"
            }
            if (![String]::IsNullOrEmpty($lab.'Comment (Optional)'))
            {
                $para = $lab.'Comment (Optional)'
                $cmdlet += " -Comment '" + $para + "'"
            }
            if (![String]::IsNullOrEmpty($lab.'IsRecordLabel (Required)'))
            {
                $para = $lab.'IsRecordLabel (Required)'
                $cmdlet += " -IsRecordLabel " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionAction (Optional)'))
            {
                $para = $lab.'RetentionAction (Optional)'
                $cmdlet += " -RetentionAction " + $para 
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionDuration (Optional)'))
            {
                $para = $lab.'RetentionDuration (Optional)'
                $cmdlet += " -RetentionDuration " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionType (Optional)'))
            {
                $para = $lab.'RetentionType (Optional)'
                $cmdlet += " -RetentionType " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'ReviewerEmail (Optional)'))
            {
                $emails = $lab.'ReviewerEmail (Optional)'.Split(",") | ForEach-Object { $_.Trim() }
                if (($emails -ne $null) -and ($emails.Count -ne 0))
                {
                    $eml = '@('
                    foreach($email in $emails)
                    {
                        $eml += "'{0}'," -f $email
                    }
                    $eml = $eml.Substring(0, $eml.Length - 1) + ')'
                    
                    $cmdlet += " -ReviewerEmail " + $eml
                }
            }
            # If the tag already exists, skip for creation
            if (($tags -eq $null) -or ($tags | ? { $_.Name.ToLower() -eq $name.ToLower() }) -eq $null)
            {
                # Create compliance tag
                $msg = "Execute Cmdlet : {0}" -f $cmdlet
                
                $ret = InvokePowerShellCmdlet $cmdlet
            
                if ($ret -eq $null)
                {
                    WriteToLog -Type "Failed" $error[0]
                    break;
                }
            }
            else
            {
                WriteToLog -Type "Warning" -Message "The tag '$name' already exists! Skip for creation!"
            }
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Create Retention Compliance Policy
# -------------------
Function CreateRetentionCompliancePolicy
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath
    )
    
    WriteToLog -Type "Start" "Start to Create Retention Policy"
    FileExist $FilePath
    try
    {
        # Import csv
        $list = Import-Csv -Path $FilePath
        # Retrieve existing retention compliance policy
        $policies = InvokePowerShellCmdlet "Get-RetentionCompliancePolicy"
        foreach($rp in $list)
        {
            # Cmdlet parameters
            $para = [String]::Empty;
            $name = [String]::Empty;
            $rpid = [String]::Empty;
            $cmdlet = 'New-RetentionCompliancePolicy'
            if ([String]::IsNullOrEmpty($rp.'Policy Name (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
               $name = $rp.'Policy Name (Required)'
               $cmdlet += " -Name '" + $name + "'"
            }
            if ([String]::IsNullOrEmpty($rp.'Enabled (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
                $enabled = $rp.'Enabled (Required)'
                $cmdlet += " -Enabled " + $enabled
            }
            if (![String]::IsNullOrEmpty($rp.'ExchangeLocation (Optional)'))
            {
                $para = $rp.'ExchangeLocation (Optional)'
                $cmdlet += " -ExchangeLocation " + $para
            }
         
            if (![String]::IsNullOrEmpty($rp.'ExchangeLocationException (Optional)'))
            {
                $para = $rp.'ExchangeLocationException (Optional)'
                $cmdlet += " -ExchangeLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'ModernGroupLocation (Optional)'))
            {
                $para = $rp.'ModernGroupLocation (Optional)'
                $cmdlet += " -ModernGroupLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'ModernGroupLocationException (Optional)'))
            {
                $para = $rp.'ModernGroupLocationException (Optional)'
                $cmdlet += " -ModernGroupLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'OneDriveLocation (Optional)'))
            {
                $para = $rp.'OneDriveLocation (Optional)'
                $cmdlet += " -OneDriveLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'OneDriveLocationException (Optional)'))
            {
                $para = $rp.'OneDriveLocationException (Optional)'
                $cmdlet += " -OneDriveLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SharePointLocation (Optional)'))
            {
                $para = $rp.'SharePointLocation (Optional)'
                $cmdlet += " -SharePointLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SharePointLocationException (Optional)'))
            {
                $para = $rp.'SharePointLocationException (Optional)'
                $cmdlet += " -SharePointLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'PublicFolderLocation (Optional)'))
            {
                $para = $rp.'PublicFolderLocation (Optional)'
                $cmdlet += " -PublicFolderLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SkypeLocation (Optional)'))
            {
                $para = $rp.'SkypeLocation (Optional)'
                $cmdlet += " -SkypeLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SkypeLocationException (Optional)'))
            {
                $para = $rp.'SkypeLocationException (Optional)'
                $cmdlet += " -SkypeLocationException " + $para
            }
            # If the policy already exists, skip for creation
            if (($policies -eq $null) -or ($policies | ? { $_.Name.ToLower() -eq $name.ToLower() }) -eq $null)
            {
                # Create retention compliance policy
                $msg = "Execute Cmdlet : {0}" -f $cmdlet
            
                $ret = invokepowershellcmdlet $cmdlet
            
                if ($ret -eq $null)
                {
                    WriteToLog -Type "Failed" $error[0]
                    break;
                }
                $rpid = $ret.Guid
            }
            else
            {
                WriteToLog -Type "Warning" -Message "The policy '$name' already exists! Skip for creation!"
                $rpid = ($policies | ? { $_.Name.ToLower() -eq $name.ToLower() }).Guid
            }
                        
            # Retrieve tag name for publishing
            $ts = $rp.'PublishComplianceTag (Required)'
            $tagList = $ts.Split(",") | ForEach-Object { $_.Trim() }
            
            WriteToLog -Type "Message" -Message "Publish Tags : '$ts'" 
            
            PublishComplianceTag -PolicyGuid $rpid -TagName $tagList
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Publish Compliance Tag
# -------------------
Function PublishComplianceTag
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$PolicyGuid,
        [Parameter(Mandatory = $true)]
        [String[]]$TagNames
    )
    
    WriteToLog -Type "Start" "Start to Publish Compliance Tag"
    try
    {
        # Retrieve existing rule related to the given compliance policy
        $rule = InvokePowerShellCmdlet ("Get-RetentionComplianceRule -Policy {0}" -f $PolicyGuid)
        $tagGuids = New-Object System.Collections.ArrayList
        
        foreach ($tn in $TagNames)
        {
            $t = InvokePowerShellCmdlet ("Get-ComplianceTag {0}" -f $tn)
            $tagGuids.Add($t.Guid) | Out-Null
        }
        if ($rule -ne $null)
        {
            foreach ($r in $rule)
            {
                if ([String]::IsNullOrEmpty($r.PublishComplianceTag))
                {
                    continue;
                }
                else
                {
                    $tl = $r.PublishComplianceTag.Split(",")
                    if ($tagGuids.Contains([GUID]$tl[0]))
                    {
                        $tagGuids.Remove([GUID]$tl[0]);
                    }
                }
            }
        }
        
        foreach($t in $tagGuids)
        {
            # Publish compliance tag
            $cmdlet = "New-RetentionComplianceRule -Policy {0} -PublishComplianceTag {1}" -f $PolicyGuid, $t
            $ret = InvokePowerShellCmdlet $cmdlet
            
            if ($ret -eq $null)
            {
                WriteToLog -Type "Failed" $error[0]
                break;
            }
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Export All Labels Created in The Process
# -------------------
Function ExportCreatedComplianceTag
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$LabelFilePath
    )
    
    WriteToLog -Type "Start" "Start to Export Compliance Tag Created"
    try
    {
        # Import input csv
        $labels = Import-Csv $LabelFilePath
        # Create result table
        $tabName = "ResultTable"
        $table = New-Object system.Data.DataTable "$tabName"
        $col1 = New-Object system.Data.DataColumn Name,([string])
        $col2 = New-Object system.Data.DataColumn Comment,([string])
        $col3 = New-Object system.Data.DataColumn IsRecordLabel,([string])
        $col4 = New-Object system.Data.DataColumn RetentionAction,([string])
        $col5 = New-Object system.Data.DataColumn RetentionDuration,([string])
        $col6 = New-Object system.Data.DataColumn RetentionType,([string])
        $col7 = New-Object system.Data.DataColumn ReviewerEmail,([string])
        
        # Add the Columns
        $table.columns.add($col1)
        $table.columns.add($col2)
        $table.columns.add($col3)
        $table.columns.add($col4)
        $table.columns.add($col5)
        $table.columns.add($col6)
        $table.columns.add($col7)
        foreach($lab in $labels)
        {
            $t = InvokePowerShellCmdlet ("Get-ComplianceTag '{0}' " -f $lab.'Name (Required)')
            
            # Create a result row
            $row = $table.NewRow()
            $row['Name'] = $t.Name
            $row['Comment'] = $t.Comment
            $row['IsRecordLabel'] = $t.IsRecordLabel
            $row['RetentionAction'] = $t.RetentionAction
            $row['RetentionDuration'] = $t.RetentionDuration
            $row['RetentionType'] = $t.RetentionType
            $row['ReviewerEmail'] = $t.ReviewerEmail
            
            # Add the row to the table
            $table.Rows.Add($row)
        }
        $table | Export-Csv $tagRetFile -NoTypeInformation
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in exporting results."
    }
}
# -------------------
# Export All Published Labels and Policies in The Process
# -------------------
Function ExportPublishedComplianceTagAndPolicy
{
    Param(
        [Parameter(Mandatory = $true)]
        [String[]]$PolicyFilePath
    )
    
    WriteToLog -Type "Start" "Start to Export Published Compliance Tag and Policy"
    try
    {
        # Import input csv
        $policies = Import-Csv $PolicyFilePath
        # Create result table
        $tabName = "ResultTable"
        $table = New-Object system.Data.DataTable "$tabName"
        $col1 = New-Object system.Data.DataColumn 'Policy Name',([string])
        $col2 = New-Object system.Data.DataColumn PublishComplianceTag,([string])
        $col3 = New-Object system.Data.DataColumn Comment,([string])
        $col4 = New-Object system.Data.DataColumn Enabled,([string])
        $col5 = New-Object system.Data.DataColumn ExchangeLocation,([string])
        $col6 = New-Object system.Data.DataColumn ExchangeLocationException,([string])
        $col7 = New-Object system.Data.DataColumn ModernGroupLocation,([string])
        $col8 = New-Object system.Data.DataColumn ModernGroupLocationException,([string])
        $col9 = New-Object system.Data.DataColumn OneDriveLocation,([string])
        $col10 = New-Object system.Data.DataColumn OneDriveLocationException,([string])
        $col11 = New-Object system.Data.DataColumn PublicFolderLocation,([string])
        $col12 = New-Object system.Data.DataColumn SharePointLocation,([string])
        $col13 = New-Object system.Data.DataColumn SharePointLocationException,([string])
        $col14 = New-Object system.Data.DataColumn SkypeLocation,([string])
        $col15 = New-Object system.Data.DataColumn SkypeLocationException,([string])
        
        # Add the Columns
        $table.columns.add($col1)
        $table.columns.add($col2)
        $table.columns.add($col3)
        $table.columns.add($col4)
        $table.columns.add($col5)
        $table.columns.add($col6)
        $table.columns.add($col7)
        $table.columns.add($col8)
        $table.columns.add($col9)
        $table.columns.add($col10)
        $table.columns.add($col11)
        $table.columns.add($col12)
        $table.columns.add($col13)
        $table.columns.add($col14)
        $table.columns.add($col15)
        foreach($policy in $policies)
        {
            $t = InvokePowerShellCmdlet ("Get-RetentionCompliancePolicy '{0}' -DistributionDetail" -f $policy.'Policy Name (Required)')
            
            # Create a result row
            $row = $table.NewRow()
            $row['Policy Name'] = $t.Name
            
            $rules = InvokePowerShellCmdlet ("Get-RetentionComplianceRule -Policy {0}" -f $t.Guid)
            $tagList = [String]::Empty
            foreach($rule in $rules)
            {
                if ([String]::IsNullOrEmpty($rule.PublishComplianceTag) -eq $False)
                {
                    $tName = $rule.PublishComplianceTag.Split(',')[1]
                    $tagList = [String]::Concat($tagList, $tName, ",")
                }
            }
            if (![String]::IsNullOrEmpty($tagList))
            {
                $tagList = $tagList.Substring(0, $tagList.LastIndexOf(','))
            }
            $row['PublishComplianceTag'] = $tagList
            $row['Comment'] = $t.Comment
            $row['Enabled'] = $t.Enabled
            $row['ExchangeLocation'] = $t.ExchangeLocation
            $row['ExchangeLocationException'] = $t.ExchangeLocationException
            $row['ModernGroupLocation'] = $t.ModernGroupLocation
            $row['ModernGroupLocationException'] = $t.ModernGroupLocationException
            $row['OneDriveLocation'] = $t.OneDriveLocation
            $row['OneDriveLocationException'] = $t.OneDriveLocationException
            $row['PublicFolderLocation'] = $t.PublicFolderLocation
            $row['SharePointLocation'] = $t.SharePointLocation
            $row['SharePointLocationException'] = $t.SharePointLocationException
            $row['SkypeLocation'] = $t.SkypeLocation
            $row['SkypeLocationException'] = $t.SkypeLocationException
            
            # Add the row to the table
            $table.Rows.Add($row)
        }
        $table | Export-Csv $tagPubRetFile -NoTypeInformation
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in exporting results."
    }
}
# Create compliance tag
CreateComplianceTag -FilePath $LabelListCSV
# Create retention policy and publish compliance tag with the policy
CreateRetentionCompliancePolicy -FilePath $PolicyListCSV
# Export to result csv
if ($ResultCSV)
{
    ExportCreatedComplianceTag -LabelFilePath $LabelListCSV
    ExportPublishedComplianceTagAndPolicy -PolicyFilePath $PolicyListCSV 
}

```

## <a name="step-4-run-the-powershell-script"></a><span data-ttu-id="b7b22-155">Steg 4: Köra PowerShell-skriptet</span><span class="sxs-lookup"><span data-stu-id="b7b22-155">Step 4: Run the PowerShell script</span></span>

<span data-ttu-id="b7b22-156">Börja med att [Ansluta till Säkerhets- och efterlevnadscentret i PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="b7b22-156">First, [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

<span data-ttu-id="b7b22-157">Kör sedan skriptet som skapar och publicerar kvarhållningsetiketterna:</span><span class="sxs-lookup"><span data-stu-id="b7b22-157">Then, run the script that creates and publishes the retention labels:</span></span>
  
1. <span data-ttu-id="b7b22-158">I PowerShell-sessionen för Säkerhets- och efterlevnadscenter anger du sökvägen, följt av tecknen `.\` och skriptets filnamn. Tryck sedan på RETUR, så körs skriptet.</span><span class="sxs-lookup"><span data-stu-id="b7b22-158">In your Security & Compliance Center PowerShell session, enter the path, followed by the characters `.\` and the file name of the script, and then press ENTER to run the script.</span></span> <span data-ttu-id="b7b22-159">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="b7b22-159">For example:</span></span>
    
    ```powershell
    <path>.\CreateRetentionSchedule.ps1
    ```

2. <span data-ttu-id="b7b22-160">Skriptet uppmanar dig att ange platserna för de .csv-filer du skapade i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="b7b22-160">The script prompts you for the locations of the .csv files that you created in the previous steps.</span></span> <span data-ttu-id="b7b22-161">Ange sökvägen, följt av tecknen `.\` och filnamnet på .csv-filen, och tryck sedan på RETUR.</span><span class="sxs-lookup"><span data-stu-id="b7b22-161">Enter the path, followed by the characters `.\` and file name of the .csv file, and then press ENTER.</span></span> <span data-ttu-id="b7b22-162">För den första frågan anger du till exempel:</span><span class="sxs-lookup"><span data-stu-id="b7b22-162">For example, for the first prompt:</span></span>
    
    ```powershell
    <path>.\Labels.csv
    ```

## <a name="step-5-view-the-log-file-with-the-results"></a><span data-ttu-id="b7b22-163">Steg 5: Visa loggfilen med resultatet</span><span class="sxs-lookup"><span data-stu-id="b7b22-163">Step 5: View the log file with the results</span></span>

<span data-ttu-id="b7b22-164">Använd loggfilen som skriptet skapade för att kontrollera resultatet och hitta eventuella fel som behöver åtgärdas.</span><span class="sxs-lookup"><span data-stu-id="b7b22-164">Use the log file that the script created to check the results and identify any failures that need resolving.</span></span>

<span data-ttu-id="b7b22-165">Loggfilen finns på följande plats, även om siffrorna i exemplets filnamn varierar.</span><span class="sxs-lookup"><span data-stu-id="b7b22-165">You can find the log file at the following location, although the digits in the example file name vary.</span></span>
  
```
<path>.\Log_Publish_Compliance_Tag_01112018_151239.txt
```