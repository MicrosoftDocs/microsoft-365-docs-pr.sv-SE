---
title: Skapa en rapport om spärrade eDiscovery-ärenden
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
ms.custom:
- seo-marvel-apr2020
description: Lär dig hur du skapar en rapport som innehåller information om alla innehåll som är kopplade till eDiscovery-ärenden.
ms.openlocfilehash: 04282f6f2481d892fa16d685936efeec55feae77
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161947"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases"></a><span data-ttu-id="aba14-103">Skapa en rapport om spärrade eDiscovery-ärenden</span><span class="sxs-lookup"><span data-stu-id="aba14-103">Create a report on holds in eDiscovery cases</span></span>

<span data-ttu-id="aba14-104">Skriptet i den här artikeln gör att eDiscovery-administratörer och eDiscovery-hanterare kan generera en rapport som innehåller information om alla innehåll som är kopplade till eDiscovery-ärenden i efterlevnadscentret i Office 365 eller Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aba14-104">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the the compliance center in Office 365 or Microsoft 365.</span></span> <span data-ttu-id="aba14-105">Rapporten innehåller information som namnet på det ärende som ett ärende som ett ärende är kopplat till, vilka innehållsplatser som är placerade som väntande och om fältet är frågebaserat.</span><span class="sxs-lookup"><span data-stu-id="aba14-105">The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based.</span></span> <span data-ttu-id="aba14-106">Om det finns fall som inte har något som kan spärras skapas en rapport med en lista över ärenden utan rymmer.</span><span class="sxs-lookup"><span data-stu-id="aba14-106">If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="aba14-107">I avsnittet [Mer information](#more-information) finns en detaljerad beskrivning av informationen i rapporten.</span><span class="sxs-lookup"><span data-stu-id="aba14-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span>

## <a name="admin-requirements-and-script-information"></a><span data-ttu-id="aba14-108">Administratörskrav och skriptinformation</span><span class="sxs-lookup"><span data-stu-id="aba14-108">Admin requirements and script information</span></span>

- <span data-ttu-id="aba14-109">Om du vill skapa en rapport över alla eDiscovery-ärenden i organisationen måste du vara eDiscovery-administratör i organisationen.</span><span class="sxs-lookup"><span data-stu-id="aba14-109">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization.</span></span> <span data-ttu-id="aba14-110">Om du är en eDiscovery-hanterare innehåller rapporten endast information om de fall som du kan komma åt.</span><span class="sxs-lookup"><span data-stu-id="aba14-110">If you are an eDiscovery Manager, the report will only include information about the cases that you can access.</span></span> <span data-ttu-id="aba14-111">Mer information om eDiscovery-behörigheter finns i [Tilldela eDiscovery-behörigheter.](assign-ediscovery-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="aba14-111">For more information about eDiscovery permissions, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="aba14-112">Skriptet i den här artikeln har minimal felhantering.</span><span class="sxs-lookup"><span data-stu-id="aba14-112">The script in this article has minimal error handling.</span></span> <span data-ttu-id="aba14-113">Det primära syftet är att snabbt skapa en rapport om de kvarhåller information som är kopplade till eDiscovery-ärenden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="aba14-113">The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>

- <span data-ttu-id="aba14-114">Exempelskripten som tillhandahålls i det här avsnittet stöds inte under något standardsupportprogram eller någon standardsupporttjänst från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="aba14-114">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="aba14-115">Exempelskripten ges i befintligt skick utan garantier av något slag.</span><span class="sxs-lookup"><span data-stu-id="aba14-115">The sample scripts are provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="aba14-116">Vidare frånsäger sig Microsoft alla underförstådda garantier, inklusive, utan begränsning, underförstådda garantier om säljbarhet eller lämplighet för ett visst ändamål.</span><span class="sxs-lookup"><span data-stu-id="aba14-116">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="aba14-117">Hela risken i samband med användningen av eller prestandan hos exempelskripten och dokumentationen vilar på dig.</span><span class="sxs-lookup"><span data-stu-id="aba14-117">The entire risk arising out of the use or performance of the sample scripts and documentation remains with you.</span></span> <span data-ttu-id="aba14-118">Under inga omständigheter ska Microsoft, dess upphovspersoner eller någon annan som är involverad i skapandet, produktionen eller leveransen av skripten hållas ansvariga för någon som helst skada (inklusive, men inte begränsat till, skador avseende utebliven vinst, driftavbrott, förlust av affärsinformation eller annan ekonomisk skada) som uppstår till följd av användning eller svårighet eller omöjlighet att använda exempelskripten eller dokumentationen, även om Microsoft har fått information om att sådana skador kan uppstå.</span><span class="sxs-lookup"><span data-stu-id="aba14-118">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-connect-to-the-security--compliance-center-powershell"></a><span data-ttu-id="aba14-119">Steg 1: Anslut säkerhets- och & Säkerhets- och efterlevnadscenter PowerShell</span><span class="sxs-lookup"><span data-stu-id="aba14-119">Step 1: Connect to the Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="aba14-120">Det första steget är att ansluta till PowerShell för Säkerhets- och efterlevnadscenter för din organisation.</span><span class="sxs-lookup"><span data-stu-id="aba14-120">The first step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="aba14-121">Stegvisa anvisningar finns i [Ansluta till PowerShell för Säkerhets- och efterlevnadscenter](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="aba14-121">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="aba14-122">Steg 2: Kör skriptet för att rapportera om eDiscovery-ärenden</span><span class="sxs-lookup"><span data-stu-id="aba14-122">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="aba14-123">När du har anslutit till Security & Compliance Center PowerShell är nästa steg att skapa och köra skriptet som samlar in information om eDiscovery-ärenden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="aba14-123">After you've connected to Security & Compliance Center PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span>

1. <span data-ttu-id="aba14-124">Spara följande text i en Windows PowerShell skriptfil med hjälp av ett filnamnssuffix .ps1; till exempel CaseHoldsReport.ps1.</span><span class="sxs-lookup"><span data-stu-id="aba14-124">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span>

   ```powershell
   #script begin
   " "
   write-host "***********************************************"
   write-host "   Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "        eDiscovery cases - Holds report         " -foregroundColor yellow -backgroundcolor darkgreen
   write-host "***********************************************"
   " "
   #prompt users to specify a path to store the output files
   $time=get-date
   $Path = Read-Host 'Enter a file path to save the report to a .csv file'
   $outputpath=$Path+'\'+'CaseHoldsReport'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
   $noholdsfilepath=$Path+'\'+'CaseswithNoHolds'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
   #add case details to the csv file
   function add-tocasereport{
   Param([string]$casename,
   [String]$casestatus,
   [datetime]$casecreatedtime,
   [string]$casemembers,
   [datetime]$caseClosedDateTime,
   [string]$caseclosedby,
   [string]$holdname,
   [String]$Holdenabled,
   [string]$holdcreatedby,
   [string]$holdlastmodifiedby,
   [string]$ExchangeLocation,
   [string]$sharePointlocation,
   [string]$ContentMatchQuery,
   [datetime]$holdcreatedtime,
   [datetime]$holdchangedtime
   )
   $addRow = New-Object PSObject
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case name" -Value $casename
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case status" -Value $casestatus
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case members" -Value $casemembers
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case created time" -Value $casecreatedtime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed time" -Value $caseClosedDateTime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed by" -Value $caseclosedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold name" -Value $holdname
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold enabled" -Value $Holdenabled
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created by" -Value $holdcreatedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold last changed by" -Value $holdlastmodifiedby
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Exchange locations" -Value  $ExchangeLocation
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "SharePoint locations" -Value $sharePointlocation
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold query" -Value $ContentMatchQuery
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created time (UTC)" -Value $holdcreatedtime
   Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold changed time (UTC)" -Value $holdchangedtime
   $allholdreport = $addRow | Select-Object "Case name","Case status","Hold name","Hold enabled","Case members", "Case created time","Case closed time","Case closed by","Exchange locations","SharePoint locations","Hold query","Hold created by","Hold created time (UTC)","Hold last changed by","Hold changed time (UTC)"
   $allholdreport | export-csv -path $outputPath -notypeinfo -append -Encoding ascii
   }
   #get information on the cases and pass values to the case report function
   " "
   write-host "Gathering a list of cases and holds..."
   " "
   $edc =Get-ComplianceCase -ErrorAction SilentlyContinue
   foreach($cc in $edc)
   {
   write-host "Working on case :" $cc.name
   if($cc.status -eq 'Closed')
   {
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   add-tocasereport -casename $cc.name -casestatus $cc.Status -caseclosedby $cc.closedby -caseClosedDateTime $cc.ClosedDateTime -casemembers $cmembers
   }
   else{
   $cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
   $policies = Get-CaseHoldPolicy -Case $cc.Name | %{ Get-CaseHoldPolicy $_.Name -Case $_.CaseId -DistributionDetail}
   if ($policies -ne $NULL)
   {
   foreach ($policy in $policies)
   {
   $rule=Get-CaseHoldRule -Policy $policy.name
   add-tocasereport -casename $cc.name -casemembers $cmembers -casestatus $cc.Status -casecreatedtime $cc.CreatedDateTime -holdname $policy.name -holdenabled $policy.enabled -holdcreatedby $policy.CreatedBy -holdlastmodifiedby $policy.LastModifiedBy -ExchangeLocation (($policy.exchangelocation.name)-join ';') -SharePointLocation (($policy.sharePointlocation.name)-join ';') -ContentMatchQuery $rule.ContentMatchQuery -holdcreatedtime $policy.WhenCreatedUTC -holdchangedtime $policy.WhenChangedUTC
   }
   }
   else{
   write-host "No hold policies found in case:" $cc.name -foregroundColor 'Yellow'
   " "
   [string]$cc.name | out-file -filepath $noholdsfilepath -append
   }
   }
   }

   " "
   Write-host "Script complete! Report files saved to this folder: '$Path'"
   " "
   #script end
   ```

2. <span data-ttu-id="aba14-125">I den Windows PowerShell som öppnades i steg 1 går du till mappen där du sparade skriptet.</span><span class="sxs-lookup"><span data-stu-id="aba14-125">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="aba14-126">Kör skriptet. till exempel:</span><span class="sxs-lookup"><span data-stu-id="aba14-126">Run the script; for example:</span></span>

   ```powershell
   .\CaseHoldsReport.ps1
   ```

   <span data-ttu-id="aba14-127">Skriptet uppmanar dig att ange en målmapp där rapporten ska sparas.</span><span class="sxs-lookup"><span data-stu-id="aba14-127">The script will prompt for a target folder to save the report to.</span></span>

4. <span data-ttu-id="aba14-128">Skriv den fullständiga sökvägen till den mapp du vill spara rapporten till och tryck sedan på **Retur.**</span><span class="sxs-lookup"><span data-stu-id="aba14-128">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>

   > [!TIP]
   > <span data-ttu-id="aba14-129">Om du vill spara rapporten i samma mapp som skriptet finns i skriver du en punkt (".") när du uppmanas att ange en målmapp.</span><span class="sxs-lookup"><span data-stu-id="aba14-129">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder.</span></span> <span data-ttu-id="aba14-130">Om du vill spara rapporten i en undermapp i mappen där skriptet finns skriver du bara namnet på undermappen.</span><span class="sxs-lookup"><span data-stu-id="aba14-130">To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span>

   <span data-ttu-id="aba14-131">Skriptet börjar samla in information om alla eDiscovery-ärenden i organisationen.</span><span class="sxs-lookup"><span data-stu-id="aba14-131">The script starts to collect information about all the eDiscovery cases in your organization.</span></span> <span data-ttu-id="aba14-132">Kom inte åt rapportfilen medan skriptet körs.</span><span class="sxs-lookup"><span data-stu-id="aba14-132">Don't access the report file while the script is running.</span></span> <span data-ttu-id="aba14-133">När skriptet är klart visas ett bekräftelsemeddelande under Windows PowerShell session.</span><span class="sxs-lookup"><span data-stu-id="aba14-133">After the script is complete, a confirmation message is displayed in the Windows PowerShell session.</span></span> <span data-ttu-id="aba14-134">När det här meddelandet visas kan du komma åt rapporten i den mapp som du angav i steg 4.</span><span class="sxs-lookup"><span data-stu-id="aba14-134">After this message is displayed, you can access the report in the folder that you specified in Step 4.</span></span> <span data-ttu-id="aba14-135">Filnamnet för rapporten är `CaseHoldsReport<DateTimeStamp>.csv` .</span><span class="sxs-lookup"><span data-stu-id="aba14-135">The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

   <span data-ttu-id="aba14-136">Skriptet skapar även en rapport med en lista med ärenden som inte innehåller några mål.</span><span class="sxs-lookup"><span data-stu-id="aba14-136">Addtionally, the script also creates a report with a list of cases that don't have any holds.</span></span> <span data-ttu-id="aba14-137">Filnamnet för den här rapporten är `CaseswithNoHolds<DateTimeStamp>.csv` .</span><span class="sxs-lookup"><span data-stu-id="aba14-137">The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>

   <span data-ttu-id="aba14-138">Här är ett exempel på hur skriptet CaseHoldsReport.ps1 körs.</span><span class="sxs-lookup"><span data-stu-id="aba14-138">Here's an example of running the CaseHoldsReport.ps1 script.</span></span>

   ![Utdata efter att ha kört CaseHoldsReport.ps1 skriptet](../media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)

## <a name="more-information"></a><span data-ttu-id="aba14-140">Mer information</span><span class="sxs-lookup"><span data-stu-id="aba14-140">More information</span></span>

<span data-ttu-id="aba14-141">Rapporten om ärende som skapas när du kör skriptet i den här artikeln innehåller följande information om varje enskilt ärende.</span><span class="sxs-lookup"><span data-stu-id="aba14-141">The case holds report that's created when you run the script in this article contains the following information about each hold.</span></span> <span data-ttu-id="aba14-142">Som tidigare förklarats måste du vara eDiscovery-administratör för att returnera information för alla som finns i organisationen.</span><span class="sxs-lookup"><span data-stu-id="aba14-142">As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization.</span></span> <span data-ttu-id="aba14-143">Mer information om fall som kan spärras finns i [eDiscovery-ärenden.](./get-started-core-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="aba14-143">For more information about case holds, see [eDiscovery cases](./get-started-core-ediscovery.md).</span></span>

- <span data-ttu-id="aba14-144">Namnet på kvarten och namnet på det eDiscovery-ärende som är kopplat till det.</span><span class="sxs-lookup"><span data-stu-id="aba14-144">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>

- <span data-ttu-id="aba14-145">Om eDiscovery-ärendet är aktivt eller stängt eller inte.</span><span class="sxs-lookup"><span data-stu-id="aba14-145">Whether or not the eDiscovery case is active or closed.</span></span>

- <span data-ttu-id="aba14-146">Om alternativet för att hålla på en enhet är aktiverat eller inte.</span><span class="sxs-lookup"><span data-stu-id="aba14-146">Whether or not the hold is enabled or disabled.</span></span>

- <span data-ttu-id="aba14-147">Medlemmarna i eDiscovery-ärendet som är kopplat till det.</span><span class="sxs-lookup"><span data-stu-id="aba14-147">The members of the eDiscovery case that the hold is associated with.</span></span> <span data-ttu-id="aba14-148">Ärendemedlemmar kan visa eller hantera ett ärende beroende på vilka eDiscovery-behörigheter de har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="aba14-148">Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>

- <span data-ttu-id="aba14-149">Den tid och det datum då ärendet skapades.</span><span class="sxs-lookup"><span data-stu-id="aba14-149">The time and date the case was created.</span></span>

- <span data-ttu-id="aba14-150">Om ett ärende är stängt stänger personen som stängde det samt tiden och datumet då det stängdes.</span><span class="sxs-lookup"><span data-stu-id="aba14-150">If a case is closed, the person who closed it and the time and date it was closed.</span></span>

- <span data-ttu-id="aba14-151">Den Exchange postlådor SharePoint har platser som är väntande.</span><span class="sxs-lookup"><span data-stu-id="aba14-151">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>

- <span data-ttu-id="aba14-152">Om hold är frågebaserad, ska frågans syntax vara.</span><span class="sxs-lookup"><span data-stu-id="aba14-152">If the hold is query-based, the query syntax.</span></span>

- <span data-ttu-id="aba14-153">Den tid och det datum då det skapades och den person som skapade det.</span><span class="sxs-lookup"><span data-stu-id="aba14-153">The time and date the hold was created and the person who created it.</span></span>

- <span data-ttu-id="aba14-154">Den tid och det datum då lasten ändrades och den person som ändrade det.</span><span class="sxs-lookup"><span data-stu-id="aba14-154">The time and date the hold was last changed and the person who changed it.</span></span>