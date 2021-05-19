---
title: Använda ett PowerShell-skript för att söka i granskningsloggen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Använd ett PowerShell-skript som kör cmdleten Search-UnifiedAuditLog i Exchange Online för att söka i granskningsloggen. Det här skriptet är optimerat för att returnera en stor uppsättning (upp till 50 000) granskningsposter. Skriptet exporterar dessa poster till en CSV-fil som du kan visa eller transformera med Power Query i Excel.
ms.openlocfilehash: df5e675e5e36603a73078bd5ecf5e64bc7a76f95
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "52162802"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a><span data-ttu-id="1a12a-105">Använda ett PowerShell-skript för att söka i granskningsloggen</span><span class="sxs-lookup"><span data-stu-id="1a12a-105">Use a PowerShell script to search the audit log</span></span>

<span data-ttu-id="1a12a-106">Säkerhet, efterlevnad och granskning har idag högsta prioritet för IT-administratörer.</span><span class="sxs-lookup"><span data-stu-id="1a12a-106">Security, compliance, and auditing have become a top priority for IT administrators in today’s world.</span></span> <span data-ttu-id="1a12a-107">Microsoft 365 har flera inbyggda funktioner som organisationer kan använda för att enkelt hantera säkerhet, efterlevnad och granskning.</span><span class="sxs-lookup"><span data-stu-id="1a12a-107">Microsoft 365 has several built-in capabilities to help organizations manage security, compliance, and auditing.</span></span> <span data-ttu-id="1a12a-108">Tack vare enhetlig granskningsloggning kan du undersöka säkerhetsincidenter och efterlevnadsproblem.</span><span class="sxs-lookup"><span data-stu-id="1a12a-108">In particular, unified audit logging can help you investigate security incidents and compliance issues.</span></span> <span data-ttu-id="1a12a-109">Du kan hämta granskningsloggar med följande metoder:</span><span class="sxs-lookup"><span data-stu-id="1a12a-109">You can retrieve audit logs by using the following methods:</span></span>

- [<span data-ttu-id="1a12a-110">Office 365 Management Activity-API:et</span><span class="sxs-lookup"><span data-stu-id="1a12a-110">The Office 365 Management Activity API</span></span>](/office/office-365-management-api/office-365-management-activity-api-reference)

- <span data-ttu-id="1a12a-111">[Verktyget för sökning i granskningslogg](search-the-audit-log-in-security-and-compliance.md) i Microsoft 365 Efterlevnadscenter</span><span class="sxs-lookup"><span data-stu-id="1a12a-111">The [audit log search tool](search-the-audit-log-in-security-and-compliance.md) in the Microsoft 365 compliance center</span></span>

- <span data-ttu-id="1a12a-112">Cmdleten [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) i Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a12a-112">The [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) cmdlet in Exchange Online PowerShell</span></span>

<span data-ttu-id="1a12a-113">Om du regelbundet behöver hämta granskningsloggar bör du överväga en lösning som använder Office 365 Management Activity-API:et eftersom det ger stora organisationer skalbarhet och prestanda för att kontinuerligt hämta miljontals granskningsposter.</span><span class="sxs-lookup"><span data-stu-id="1a12a-113">If you need to retrieve audit logs on a regular basis, you should consider a solution that uses the Office 365 Management Activity API because it that can provide large organizations with the scalability and performance to retrieve millions of audit records on an ongoing basis.</span></span> <span data-ttu-id="1a12a-114">Genom att använda verktyget för sökning i granskningslogg i Microsoft 365 Efterlevnadscenter kan du snabbt hitta granskningsposter för specifika åtgärder som inträffar under en kortare tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="1a12a-114">Using the audit log search tool in Microsoft 365 compliance center is a good way to quickly find audit records for specific operations that occur in shorter time range.</span></span> <span data-ttu-id="1a12a-115">Om du använder långa tidsintervall i verktyget för sökning i granskningslogg, särskilt om du har en stor organisation, kan så många poster returneras att de inte går att hantera eller exportera enkelt.</span><span class="sxs-lookup"><span data-stu-id="1a12a-115">Using longer time ranges in the audit log search tool, especially for large organizations, might return too many records to easily manage or export.</span></span>

<span data-ttu-id="1a12a-116">I situationer där du behöver hämta granskningsdata för en viss undersökning eller incident manuellt kan det bästa alternativet vara att använda cmdleten **Search-UnifiedAuditLog**, särskilt för längre datumintervall i större organisationer.</span><span class="sxs-lookup"><span data-stu-id="1a12a-116">When there are situations where you need to manually retrieve auditing data for a specific investigation or incident, particularly for longer date ranges in larger organizations, using the **Search-UnifiedAuditLog** cmdlet may be the best option.</span></span> <span data-ttu-id="1a12a-117">Den här artikeln innehåller ett PowerShell-skript som använder cmdleten för att hämta upp till 50 000 granskningsposter och sedan exportera dem till en CSV-fil som du kan formatera med Power Query i Excel som stöd för din granskning.</span><span class="sxs-lookup"><span data-stu-id="1a12a-117">This article includes a PowerShell script that uses the cmdlet to retrieve up to 50,000 audit records and then export them to a CSV file that you can format using Power Query in Excel to help with your review.</span></span> <span data-ttu-id="1a12a-118">Med hjälp av skriptet i den här artikeln minimeras också risken för att stora sökningar i granskningsloggen uppnår tidsgränsen i tjänsten.</span><span class="sxs-lookup"><span data-stu-id="1a12a-118">Using the script in this article also minimizes the chance that large audit log searches will time out in the service.</span></span>

## <a name="before-you-run-the-script"></a><span data-ttu-id="1a12a-119">Innan du kör skriptet</span><span class="sxs-lookup"><span data-stu-id="1a12a-119">Before you run the script</span></span>

- <span data-ttu-id="1a12a-120">Granskningsloggning måste ha aktiverats för att organisationen ska kunna använda skriptet för att returnera granskningsposter.</span><span class="sxs-lookup"><span data-stu-id="1a12a-120">Audit logging has to be enabled for your organization to successfully use the script to return audit records.</span></span> <span data-ttu-id="1a12a-121">Granskningsloggning är som standard aktiverat för Microsoft 365 och Office 365 Enterprise-organisationer.</span><span class="sxs-lookup"><span data-stu-id="1a12a-121">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="1a12a-122">Kontrollera att sökning i granskningslogg är aktiverat för din organisation genom att köra följande kommando i Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1a12a-122">To verify that audit log search is turned on for your organization, you can run the following command in Exchange Online PowerShell:</span></span>

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```

  <span data-ttu-id="1a12a-123">Värdet `True` för egenskapen **UnifiedAuditLogIngestionEnabled** anger att sökning i granskningslogg är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="1a12a-123">The value of `True` for the **UnifiedAuditLogIngestionEnabled** property indicates that audit log search is turned on.</span></span>

- <span data-ttu-id="1a12a-124">Du måste ha tilldelats rollen för endast visning av granskningsloggar eller rollen för granskningsloggar i Exchange Online för att kunna köra skriptet.</span><span class="sxs-lookup"><span data-stu-id="1a12a-124">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to run successfully the script.</span></span> <span data-ttu-id="1a12a-125">Som standard tilldelas de här rollerna till rollgrupperna Efterlevnadshantering och Organisationshantering på sidan Behörigheter i administrationscentret för Exchange.</span><span class="sxs-lookup"><span data-stu-id="1a12a-125">By default, these roles are assigned to the Compliance Management and Organization Management role groups on the Permissions page in the Exchange admin center.</span></span> <span data-ttu-id="1a12a-126">Mer information finns i avsnittet ”Krav för att söka i granskningsloggen” i [Söka i granskningsloggen i Efterlevnadscenter](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span><span class="sxs-lookup"><span data-stu-id="1a12a-126">For more information, see the "Requirements to search the audit log" section in [Search the audit log in the compliance center](search-the-audit-log-in-security-and-compliance.md#requirements-to-search-the-audit-log).</span></span>

- <span data-ttu-id="1a12a-127">Det kan ta lång tid för skriptet att slutföras.</span><span class="sxs-lookup"><span data-stu-id="1a12a-127">It may take a long time for the script to complete.</span></span> <span data-ttu-id="1a12a-128">Hur lång tid det tar att köra beror på datumintervallet och storleken på det intervall som du konfigurerar att skriptet ska hämta granskningsposter för.</span><span class="sxs-lookup"><span data-stu-id="1a12a-128">How long it takes to run depends on the date range and the size of the interval that you configure the script to retrieve audit records for.</span></span> <span data-ttu-id="1a12a-129">Större datumintervall och mindre intervall ger långa körningstider.</span><span class="sxs-lookup"><span data-stu-id="1a12a-129">Larger date ranges and smaller intervals will result in a long running time.</span></span> <span data-ttu-id="1a12a-130">Se tabellen i steg 2 för mer information om datumintervall och intervall.</span><span class="sxs-lookup"><span data-stu-id="1a12a-130">See the table in Step 2 for more information about the date range and intervals.</span></span>

- <span data-ttu-id="1a12a-131">Exempelskriptet i den här artikeln har ingen support enligt något standardsupportprogram eller någon standardsupporttjänst från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1a12a-131">The sample script provided in this article isn't supported under any Microsoft standard support program or service.</span></span> <span data-ttu-id="1a12a-132">Exempelskriptet ges i befintligt skick utan garantier av något slag.</span><span class="sxs-lookup"><span data-stu-id="1a12a-132">The sample script is provided AS IS without warranty of any kind.</span></span> <span data-ttu-id="1a12a-133">Vidare frånsäger sig Microsoft alla underförstådda garantier, inklusive, men inte begränsat till, underförstådda garantier om säljbarhet eller lämplighet för ett visst ändamål.</span><span class="sxs-lookup"><span data-stu-id="1a12a-133">Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose.</span></span> <span data-ttu-id="1a12a-134">Hela risken i samband med användningen av eller prestandan hos exempelskriptet och dokumentationen vilar på dig.</span><span class="sxs-lookup"><span data-stu-id="1a12a-134">The entire risk arising out of the use or performance of the sample script and documentation remains with you.</span></span> <span data-ttu-id="1a12a-135">Under inga omständigheter ska Microsoft, dess upphovspersoner eller någon annan som är involverad i skapandet, produktionen eller leveransen av skriptet hållas ansvariga för någon som helst skada (inklusive, men inte begränsat till, skador avseende utebliven vinst, driftavbrott, förlust av affärsinformation eller annan ekonomisk skada) som uppstår till följd av användning eller svårighet eller omöjlighet att använda exempelskriptet eller dokumentationen, även om Microsoft har fått information om att sådana skador kan uppstå.</span><span class="sxs-lookup"><span data-stu-id="1a12a-135">In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the script be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample script or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-connect-to-exchange-online-powershell"></a><span data-ttu-id="1a12a-136">Steg 1: Ansluta till Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="1a12a-136">Step 1: Connect to Exchange Online PowerShell</span></span>

<span data-ttu-id="1a12a-137">Det första steget är att ansluta till Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a12a-137">The first step is to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="1a12a-138">Du kan ansluta med modern autentisering eller multifaktorautentisering (MFA).</span><span class="sxs-lookup"><span data-stu-id="1a12a-138">You can connect using modern authentication or with multi-factor authentication (MFA).</span></span> <span data-ttu-id="1a12a-139">Stegvisa anvisningar finns i [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="1a12a-139">For step-by-step instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a><span data-ttu-id="1a12a-140">Steg 2: Ändra och köra skriptet för att hämta granskningsposter</span><span class="sxs-lookup"><span data-stu-id="1a12a-140">Step 2: Modify and run the script to retrieve audit records</span></span>

<span data-ttu-id="1a12a-141">När du har anslutit till Exchange Online PowerShell är nästa steg att skapa, ändra och köra skriptet för att hämta granskningsdata.</span><span class="sxs-lookup"><span data-stu-id="1a12a-141">After you've connected to Exchange Online PowerShell, the next step is to create, modify, and run the script to retrieve the auditing data.</span></span> <span data-ttu-id="1a12a-142">De första sju raderna i skriptet för sökning i granskningslogg innehåller följande variabler som du kan ändra om du vill konfigurera sökningen.</span><span class="sxs-lookup"><span data-stu-id="1a12a-142">The first seven lines in the audit log search script contain the following variables that you can modify to configure your search.</span></span> <span data-ttu-id="1a12a-143">I tabellen i steg 2 finns en beskrivning av dessa variabler.</span><span class="sxs-lookup"><span data-stu-id="1a12a-143">See the table in step 2 for a description of these variables.</span></span>

1. <span data-ttu-id="1a12a-144">Spara följande text i ett Windows PowerShell-skript med filnamnssuffixet .ps1.</span><span class="sxs-lookup"><span data-stu-id="1a12a-144">Save the following text to a Windows PowerShell script by using a filename suffix of .ps1.</span></span> <span data-ttu-id="1a12a-145">Till exempel SearchAuditLog.ps1.</span><span class="sxs-lookup"><span data-stu-id="1a12a-145">For example, SearchAuditLog.ps1.</span></span>

   ```powershell
   #Modify the values for the following variables to configure the audit log search.
   $logFile = "d:\AuditLogSearch\AuditLogSearchLog.txt"
   $outputFile = "d:\AuditLogSearch\AuditLogRecords.csv"
   [DateTime]$start = [DateTime]::UtcNow.AddDays(-1)
   [DateTime]$end = [DateTime]::UtcNow
   $record = "AzureActiveDirectory"
   $resultSize = 5000
   $intervalMinutes = 60
   
   #Start script
   [DateTime]$currentStart = $start
   [DateTime]$currentEnd = $start
   
   Function Write-LogFile ([String]$Message)
   {
       $final = [DateTime]::Now.ToUniversalTime().ToString("s") + ":" + $Message
       $final | Out-File $logFile -Append
   }
   
   Write-LogFile "BEGIN: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize."
   Write-Host "Retrieving audit records for the date range between $($start) and $($end), RecordType=$record, ResultsSize=$resultSize"
   
   $totalCount = 0
   while ($true)
   {
       $currentEnd = $currentStart.AddMinutes($intervalMinutes)
       if ($currentEnd -gt $end)
       {
           $currentEnd = $end
       }
   
       if ($currentStart -eq $currentEnd)
       {
           break
       }
   
       $sessionID = [Guid]::NewGuid().ToString() + "_" +  "ExtractLogs" + (Get-Date).ToString("yyyyMMddHHmmssfff")
       Write-LogFile "INFO: Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
       Write-Host "Retrieving audit records for activities performed between $($currentStart) and $($currentEnd)"
       $currentCount = 0
   
       $sw = [Diagnostics.StopWatch]::StartNew()
       do
       {
           $results = Search-UnifiedAuditLog -StartDate $currentStart -EndDate $currentEnd -RecordType $record -SessionId $sessionID -SessionCommand ReturnLargeSet -ResultSize $resultSize
   
           if (($results | Measure-Object).Count -ne 0)
           {
               $results | export-csv -Path $outputFile -Append -NoTypeInformation
   
               $currentTotal = $results[0].ResultCount
               $totalCount += $results.Count
               $currentCount += $results.Count
               Write-LogFile "INFO: Retrieved $($currentCount) audit records out of the total $($currentTotal)"
   
               if ($currentTotal -eq $results[$results.Count - 1].ResultIndex)
               {
                   $message = "INFO: Successfully retrieved $($currentTotal) audit records for the current time range. Moving on!"
                   Write-LogFile $message
                   Write-Host "Successfully retrieved $($currentTotal) audit records for the current time range. Moving on to the next interval." -foregroundColor Yellow
                   ""
                   break
               }
           }
       }
       while (($results | Measure-Object).Count -ne 0)
   
       $currentStart = $currentEnd
   }
   
   Write-LogFile "END: Retrieving audit records between $($start) and $($end), RecordType=$record, PageSize=$resultSize, total count: $totalCount."
   Write-Host "Script complete! Finished retrieving audit records for the date range between $($start) and $($end). Total count: $totalCount" -foregroundColor Green
   ```

2. <span data-ttu-id="1a12a-146">Ändra de variabler som listas i följande tabell om du vill konfigurera sökvillkoren.</span><span class="sxs-lookup"><span data-stu-id="1a12a-146">Modify the variables listed in the following table to configure the search criteria.</span></span> <span data-ttu-id="1a12a-147">Skriptet innehåller exempelvärden för de här variablerna, men du bör ändra dem (om inget annat anges) så att de uppfyller dina specifika krav.</span><span class="sxs-lookup"><span data-stu-id="1a12a-147">The script includes sample values for these variables, but you should change them (unless stated otherwise) to meet your specific requirements.</span></span>

   <br>

   ****

   |<span data-ttu-id="1a12a-148">Variabel</span><span class="sxs-lookup"><span data-stu-id="1a12a-148">Variable</span></span>|<span data-ttu-id="1a12a-149">Exempelvärde</span><span class="sxs-lookup"><span data-stu-id="1a12a-149">Sample value</span></span>|<span data-ttu-id="1a12a-150">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="1a12a-150">Description</span></span>|
   |---|---|---|
   |`$logFile`|<span data-ttu-id="1a12a-151">"d:\temp\AuditSearchLog.txt"</span><span class="sxs-lookup"><span data-stu-id="1a12a-151">"d:\temp\AuditSearchLog.txt"</span></span>|<span data-ttu-id="1a12a-152">Anger namn och plats för loggfilen som innehåller information om förloppet för sökningen i granskningsloggen som utförs av skriptet.</span><span class="sxs-lookup"><span data-stu-id="1a12a-152">Specifies the name and location for the log file that contains information about the progress of the audit log search performed by the script.</span></span> <span data-ttu-id="1a12a-153">Skriptet skriver UTC-tidsstämplar till loggfilen.</span><span class="sxs-lookup"><span data-stu-id="1a12a-153">The script writes UTC timestamps to the log file.</span></span>|
   |`$outputFile`|<span data-ttu-id="1a12a-154">"d:\temp\AuditRecords.csv"</span><span class="sxs-lookup"><span data-stu-id="1a12a-154">"d:\temp\AuditRecords.csv"</span></span>|<span data-ttu-id="1a12a-155">Anger namn och plats för CSV-filen som innehåller granskningsposterna som returneras av skriptet.</span><span class="sxs-lookup"><span data-stu-id="1a12a-155">Specifies the name and location of the CSV file that contains the audit records returned by the script.</span></span>|
   |<span data-ttu-id="1a12a-156">`[DateTime]$start` och `[DateTime]$end`</span><span class="sxs-lookup"><span data-stu-id="1a12a-156">`[DateTime]$start` and `[DateTime]$end`</span></span>|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|<span data-ttu-id="1a12a-159">Anger datumintervallet för sökningen i granskningsloggen.</span><span class="sxs-lookup"><span data-stu-id="1a12a-159">Specifies the date range for the audit log search.</span></span> <span data-ttu-id="1a12a-160">Skriptet returnerar poster för granskningsaktiviteter som inträffat inom det angivna datumintervallet.</span><span class="sxs-lookup"><span data-stu-id="1a12a-160">The script will return records for audit activities that occurred within the specified date range.</span></span> <span data-ttu-id="1a12a-161">Om du till exempel vill returnera aktiviteter som har utförts i januari 2021 kan du använda startdatumet `"2021-01-01"` och slutdatumet `"2021-01-31"` (se till att omge värdena med dubbla citattecken). Exempelvärdet i skriptet returnerar poster för aktiviteter som utförts under de föregående 24 timmarna.</span><span class="sxs-lookup"><span data-stu-id="1a12a-161">For example, to return activities performed in January 2021, you can use a start date of `"2021-01-01"` and an end date of `"2021-01-31"` (be sure to surround the values in double-quotation marks) The sample value in the script returns records for activities performed in the previous 24 hours.</span></span> <span data-ttu-id="1a12a-162">Om du inte tar med en tidsstämpel i värdet är standardtidsstämpeln 00:00 (midnatt) på det angivna datumet.</span><span class="sxs-lookup"><span data-stu-id="1a12a-162">If you don't include a timestamp in the value, the default timestamp is 12:00 AM (midnight) on the specified date.</span></span>|
   |`$record`|<span data-ttu-id="1a12a-163">"AzureActiveDirectory"</span><span class="sxs-lookup"><span data-stu-id="1a12a-163">"AzureActiveDirectory"</span></span>|<span data-ttu-id="1a12a-164">Anger posttypen för granskningsaktiviteterna (kallas även för *åtgärder*) som du vill söka efter.</span><span class="sxs-lookup"><span data-stu-id="1a12a-164">Specifies the record type of the audit activities (also called *operations*) to search for.</span></span> <span data-ttu-id="1a12a-165">Den här egenskapen anger tjänsten eller funktionen som en aktivitet utlöstes i.</span><span class="sxs-lookup"><span data-stu-id="1a12a-165">This property indicates the service or feature that an activity was triggered in.</span></span> <span data-ttu-id="1a12a-166">En lista över posttyper som du kan använda för den här variabeln finns i [Posttyper i granskningsloggen](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span><span class="sxs-lookup"><span data-stu-id="1a12a-166">For a list of record types that you can use for this variable, see [Audit log record type](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype).</span></span> <span data-ttu-id="1a12a-167">Du kan använda posttypsnamnet eller ENUM-värdet.</span><span class="sxs-lookup"><span data-stu-id="1a12a-167">You can use the record type name or ENUM value.</span></span> <br/><br/><span data-ttu-id="1a12a-168">**Tips!** Om du vill returnera granskningsposter för alla posttyper använder du värdet `$null` (utan dubbla citattecken).</span><span class="sxs-lookup"><span data-stu-id="1a12a-168">**Tip:** To return audit records for all record types, use the value `$null` (without double-quotations marks).</span></span>|
   |`$resultSize`|<span data-ttu-id="1a12a-169">5000</span><span class="sxs-lookup"><span data-stu-id="1a12a-169">5000</span></span>|<span data-ttu-id="1a12a-170">Anger antalet resultat som returneras varje gång cmdleten **Search-UnifiedAuditLog** anropas av skriptet (kallas för *resultatuppsättning*).</span><span class="sxs-lookup"><span data-stu-id="1a12a-170">Specifies the number of results returned each time the **Search-UnifiedAuditLog** cmdlet is called by the script (called a *result set*).</span></span> <span data-ttu-id="1a12a-171">Värdet på 5 000 är det största värde som stöds av cmdleten.</span><span class="sxs-lookup"><span data-stu-id="1a12a-171">The value of 5,000 is the maximum value supported by the cmdlet.</span></span> <span data-ttu-id="1a12a-172">Lämna det här värdet som det är.</span><span class="sxs-lookup"><span data-stu-id="1a12a-172">Leave this value as-is.</span></span>|
   |`$intervalMinutes`|<span data-ttu-id="1a12a-173">60</span><span class="sxs-lookup"><span data-stu-id="1a12a-173">60</span></span>|<span data-ttu-id="1a12a-174">För att kringgå returneringsgränsen på 5 000 poster tar den här variabeln det dataintervall du har angett och delar upp det i mindre tidsintervall.</span><span class="sxs-lookup"><span data-stu-id="1a12a-174">To help overcome the limit of 5000 records returned, this variable takes the data range you specified and slices it up into smaller time intervals.</span></span> <span data-ttu-id="1a12a-175">Nu omfattas varje tidsintervall, inte hela datumintervallet, av kommandots utdatagräns på 5 000 poster.</span><span class="sxs-lookup"><span data-stu-id="1a12a-175">Now each interval, not the entire date range, is subject to the 5000 record output limit of the command.</span></span> <span data-ttu-id="1a12a-176">Standardvärdet på 5 000 poster per 60 minuters intervall inom datumintervallet borde vara tillräckligt för de flesta organisationer.</span><span class="sxs-lookup"><span data-stu-id="1a12a-176">The default value of 5000 records per 60-minute interval within the date range should be sufficient for most organizations.</span></span> <span data-ttu-id="1a12a-177">Men om skriptet returnerar ett felmeddelande som säger `maximum results limitation reached` (gränsen för högsta antal resultat har nåtts), minskar du tidsintervallet (till exempel till 30 minuter eller 15 minuter) och kör sedan skriptet igen.</span><span class="sxs-lookup"><span data-stu-id="1a12a-177">But, if the script returns an error that says, `maximum results limitation reached`, decrease the time interval (for example, to 30 minutes or even 15 minutes) and rerun the script.</span></span>|
   ||||

   <span data-ttu-id="1a12a-178">De flesta variablerna som anges i den föregående tabellen har motsvarande parametrar för cmdleten **Search-UnifiedAuditLog**.</span><span class="sxs-lookup"><span data-stu-id="1a12a-178">Most of the variables listed in the previous table correspond to parameters for the **Search-UnifiedAuditLog** cmdlet.</span></span> <span data-ttu-id="1a12a-179">Mer information om de här parametrarna finns i [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog).</span><span class="sxs-lookup"><span data-stu-id="1a12a-179">For more information about these parameters, see [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog).</span></span>

3. <span data-ttu-id="1a12a-180">Öppna Windows PowerShell på den lokala datorn och gå till mappen där du har sparat det ändrade skriptet.</span><span class="sxs-lookup"><span data-stu-id="1a12a-180">On your local computer, open Windows PowerShell and go to the folder where you saved the modified script.</span></span>

4. <span data-ttu-id="1a12a-181">Kör skriptet i Exchange Online PowerShell, till exempel:</span><span class="sxs-lookup"><span data-stu-id="1a12a-181">Run the script in Exchange Online PowerShell; for example:</span></span>

   ```powershell
   .\SearchAuditLog.ps1
   ```

<span data-ttu-id="1a12a-182">Skriptet visar meddelanden om förloppet medan det körs.</span><span class="sxs-lookup"><span data-stu-id="1a12a-182">The script displays progress messages while it's running.</span></span> <span data-ttu-id="1a12a-183">När skriptet har slutförts skapas loggfilen och CSV-filen som innehåller granskningsposterna. De sparas i de mappar som definieras av variablerna `$logFile` och `$outputFile`.</span><span class="sxs-lookup"><span data-stu-id="1a12a-183">After the script is finished running, it creates the log file and the CSV file that contains the audit records and saves them to the folders defined by the `$logFile` and `$outputFile` variables.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1a12a-184">Det finns en gräns på 50 000 för det maximala antalet granskningsposter som kan returneras varje gång du kör det här skriptet.</span><span class="sxs-lookup"><span data-stu-id="1a12a-184">There is a 50,000 limit for the maximum number of audit records returned each time you run this script.</span></span> <span data-ttu-id="1a12a-185">Om du kör det här skriptet och det returnerar 50 000 resultat är det troligt att det finns granskningsposter för aktiviteter som inträffat inom datumintervallet som inte har tagits med.</span><span class="sxs-lookup"><span data-stu-id="1a12a-185">If you run this script and it returns 50,000 results, then it's likely that audit records for activities that occurred within the date range weren't included.</span></span> <span data-ttu-id="1a12a-186">Om det här händer rekommenderar vi att du delar upp datumintervallet i kortare tidsperioder och sedan kör skriptet igen för varje datumintervall.</span><span class="sxs-lookup"><span data-stu-id="1a12a-186">If this happens, we recommend that you divide the date range into smaller durations and then rerun the script for each date range.</span></span> <span data-ttu-id="1a12a-187">Om till exempel ett datumintervall på 90 dagar returnerar 50 000 resultat kan du köra skriptet igen två gånger, en gång för de första 45 dagarna i datumintervallet och sedan en gång till för de följande 45 dagarna.</span><span class="sxs-lookup"><span data-stu-id="1a12a-187">For example, if a date range of 90 days returns 50,000 results then you can rerun the script twice, once for the first 45 days in the date range and then again for the next 45 days.</span></span>

## <a name="step-3-format-and-view-the-audit-records"></a><span data-ttu-id="1a12a-188">Steg 3: Formatera och visa granskningsposterna</span><span class="sxs-lookup"><span data-stu-id="1a12a-188">Step 3: Format and view the audit records</span></span>

<span data-ttu-id="1a12a-189">När du har kört skriptet och exporterat granskningsposterna till en CSV-fil kan det vara bra att formatera CSV-filen för att göra det lättare att granska och analysera granskningsposterna.</span><span class="sxs-lookup"><span data-stu-id="1a12a-189">After you've run the script and exported the audit records to a CSV file, you may want to format the CSV to make easier to review and analyze the audit records.</span></span> <span data-ttu-id="1a12a-190">Ett sätt att göra det här är att använda Power Query-funktionen för JSON-transformering i Excel för att dela upp varje egenskap i JSON-objektet i kolumnen **AuditData** i en egen kolumn.</span><span class="sxs-lookup"><span data-stu-id="1a12a-190">One way to do this is to the Power Query JSON transform feature in Excel to split each property in the JSON object in the **AuditData** column into its own column.</span></span> <span data-ttu-id="1a12a-191">Stegvisa instruktioner finns i ”Steg 2: Formatera den exporterade granskningsloggen med Power Query-redigeraren” i [Exportera, konfigurera och visa granskningsloggposter](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span><span class="sxs-lookup"><span data-stu-id="1a12a-191">For step-by-step instructions, see "Step 2: Format the exported audit log using the Power Query Editor" in [Export, configure, and view audit log records](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).</span></span>
