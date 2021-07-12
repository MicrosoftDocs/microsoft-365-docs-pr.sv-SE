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
description: Använd ett PowerShell-skript som kör cmdleten Search-UnifiedAuditLog i Exchange Online för att söka i granskningsloggen. Det här skriptet är optimerat för att returnera en stor uppsättning (upp till 50 000) granskningsposter. Skriptet exporterar dessa poster till en CSV-fil som du kan visa eller transformera med Power Query i Excel.
ms.openlocfilehash: 8abea51bb1e7e1fa7bd513bea78708b06da62def
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341014"
---
# <a name="use-a-powershell-script-to-search-the-audit-log"></a>Använda ett PowerShell-skript för att söka i granskningsloggen

Säkerhet, efterlevnad och granskning har idag högsta prioritet för IT-administratörer. Microsoft 365 har flera inbyggda funktioner som organisationer kan använda för att enkelt hantera säkerhet, efterlevnad och granskning. Tack vare enhetlig granskningsloggning kan du undersöka säkerhetsincidenter och efterlevnadsproblem. Du kan hämta granskningsloggar med följande metoder:

- [Office 365 Management Activity-API:et](/office/office-365-management-api/office-365-management-activity-api-reference)

- [Verktyget för sökning i granskningslogg](search-the-audit-log-in-security-and-compliance.md) i Microsoft 365 Efterlevnadscenter

- Cmdleten [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog) i Exchange Online PowerShell

Om du regelbundet behöver hämta granskningsloggar bör du överväga en lösning som använder Office 365 Management Activity-API:et eftersom det ger stora organisationer skalbarhet och prestanda för att kontinuerligt hämta miljontals granskningsposter. Genom att använda verktyget för sökning i granskningslogg i Microsoft 365 Efterlevnadscenter kan du snabbt hitta granskningsposter för specifika åtgärder som inträffar under en kortare tidsperiod. Om du använder långa tidsintervall i verktyget för sökning i granskningslogg, särskilt om du har en stor organisation, kan så många poster returneras att de inte går att hantera eller exportera enkelt.

I situationer där du behöver hämta granskningsdata för en viss undersökning eller incident manuellt kan det bästa alternativet vara att använda cmdleten **Search-UnifiedAuditLog**, särskilt för längre datumintervall i större organisationer. Den här artikeln innehåller ett PowerShell-skript som använder cmdleten för att hämta upp till 50 000 granskningsposter och sedan exportera dem till en CSV-fil som du kan formatera med Power Query i Excel som stöd för din granskning. Med hjälp av skriptet i den här artikeln minimeras också risken för att stora sökningar i granskningsloggen uppnår tidsgränsen i tjänsten.

## <a name="before-you-run-the-script"></a>Innan du kör skriptet

- Granskningsloggning måste ha aktiverats för att organisationen ska kunna använda skriptet för att returnera granskningsposter. Granskningsloggning är som standard aktiverat för Microsoft 365 och Office 365 Enterprise-organisationer. Kontrollera att sökning i granskningslogg är aktiverat för din organisation genom att köra följande kommando i Exchange Online PowerShell:

  ```powershell
  Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
  ```

  Värdet `True` för egenskapen **UnifiedAuditLogIngestionEnabled** anger att sökning i granskningslogg är aktiverat.

- Du måste ha tilldelats rollen för endast visning av granskningsloggar eller rollen för granskningsloggar i Exchange Online för att kunna köra skriptet. Som standard tilldelas de här rollerna till rollgrupperna Efterlevnadshantering och Organisationshantering på sidan Behörigheter i administrationscentret för Exchange. Mer information finns i avsnittet ”Krav för att söka i granskningsloggen” i [Söka i granskningsloggen i Efterlevnadscenter](search-the-audit-log-in-security-and-compliance.md#before-you-search-the-audit-log).

- Det kan ta lång tid för skriptet att slutföras. Hur lång tid det tar att köra beror på datumintervallet och storleken på det intervall som du konfigurerar att skriptet ska hämta granskningsposter för. Större datumintervall och mindre intervall ger långa körningstider. Se tabellen i steg 2 för mer information om datumintervall och intervall.

- Exempelskriptet i den här artikeln har ingen support enligt något standardsupportprogram eller någon standardsupporttjänst från Microsoft. Exempelskriptet ges i befintligt skick utan garantier av något slag. Vidare frånsäger sig Microsoft alla underförstådda garantier, inklusive, men inte begränsat till, underförstådda garantier om säljbarhet eller lämplighet för ett visst ändamål. Hela risken i samband med användningen av eller prestandan hos exempelskriptet och dokumentationen vilar på dig. Under inga omständigheter ska Microsoft, dess upphovspersoner eller någon annan som är involverad i skapandet, produktionen eller leveransen av skriptet hållas ansvariga för någon som helst skada (inklusive, men inte begränsat till, skador avseende utebliven vinst, driftavbrott, förlust av affärsinformation eller annan ekonomisk skada) som uppstår till följd av användning eller svårighet eller omöjlighet att använda exempelskriptet eller dokumentationen, även om Microsoft har fått information om att sådana skador kan uppstå.

## <a name="step-1-connect-to-exchange-online-powershell"></a>Steg 1: Ansluta till Exchange Online PowerShell

Det första steget är att ansluta till Exchange Online PowerShell. Du kan ansluta med modern autentisering eller multifaktorautentisering (MFA). Stegvisa anvisningar finns i [Ansluta till Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

## <a name="step-2-modify-and-run-the-script-to-retrieve-audit-records"></a>Steg 2: Ändra och köra skriptet för att hämta granskningsposter

När du har anslutit till Exchange Online PowerShell är nästa steg att skapa, ändra och köra skriptet för att hämta granskningsdata. De första sju raderna i skriptet för sökning i granskningslogg innehåller följande variabler som du kan ändra om du vill konfigurera sökningen. I tabellen i steg 2 finns en beskrivning av dessa variabler.

1. Spara följande text i ett Windows PowerShell-skript med filnamnssuffixet .ps1. Till exempel SearchAuditLog.ps1.

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

2. Ändra de variabler som listas i följande tabell om du vill konfigurera sökvillkoren. Skriptet innehåller exempelvärden för de här variablerna, men du bör ändra dem (om inget annat anges) så att de uppfyller dina specifika krav.

   <br>

   ****

   |Variabel|Exempelvärde|Beskrivning|
   |---|---|---|
   |`$logFile`|"d:\temp\AuditSearchLog.txt"|Anger namn och plats för loggfilen som innehåller information om förloppet för sökningen i granskningsloggen som utförs av skriptet. Skriptet skriver UTC-tidsstämplar till loggfilen.|
   |`$outputFile`|"d:\temp\AuditRecords.csv"|Anger namn och plats för CSV-filen som innehåller granskningsposterna som returneras av skriptet.|
   |`[DateTime]$start` och `[DateTime]$end`|[DateTime]::UtcNow.AddDays(-1) <br/>[DateTime]::UtcNow|Anger datumintervallet för sökningen i granskningsloggen. Skriptet returnerar poster för granskningsaktiviteter som inträffat inom det angivna datumintervallet. Om du till exempel vill returnera aktiviteter som har utförts i januari 2021 kan du använda startdatumet `"2021-01-01"` och slutdatumet `"2021-01-31"` (se till att omge värdena med dubbla citattecken). Exempelvärdet i skriptet returnerar poster för aktiviteter som utförts under de föregående 24 timmarna. Om du inte tar med en tidsstämpel i värdet är standardtidsstämpeln 00:00 (midnatt) på det angivna datumet.|
   |`$record`|"AzureActiveDirectory"|Anger posttypen för granskningsaktiviteterna (kallas även för *åtgärder*) som du vill söka efter. Den här egenskapen anger tjänsten eller funktionen som en aktivitet utlöstes i. En lista över posttyper som du kan använda för den här variabeln finns i [Posttyper i granskningsloggen](/office/office-365-management-api/office-365-management-activity-api-schema#auditlogrecordtype). Du kan använda posttypsnamnet eller ENUM-värdet. <br/><br/>**Tips!** Om du vill returnera granskningsposter för alla posttyper använder du värdet `$null` (utan dubbla citattecken).|
   |`$resultSize`|5000|Anger antalet resultat som returneras varje gång cmdleten **Search-UnifiedAuditLog** anropas av skriptet (kallas för *resultatuppsättning*). Värdet på 5 000 är det största värde som stöds av cmdleten. Lämna det här värdet som det är.|
   |`$intervalMinutes`|60|För att kringgå returneringsgränsen på 5 000 poster tar den här variabeln det dataintervall du har angett och delar upp det i mindre tidsintervall. Nu omfattas varje tidsintervall, inte hela datumintervallet, av kommandots utdatagräns på 5 000 poster. Standardvärdet på 5 000 poster per 60 minuters intervall inom datumintervallet borde vara tillräckligt för de flesta organisationer. Men om skriptet returnerar ett felmeddelande som säger `maximum results limitation reached` (gränsen för högsta antal resultat har nåtts), minskar du tidsintervallet (till exempel till 30 minuter eller 15 minuter) och kör sedan skriptet igen.|
   ||||

   De flesta variablerna som anges i den föregående tabellen har motsvarande parametrar för cmdleten **Search-UnifiedAuditLog**. Mer information om de här parametrarna finns i [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog).

3. Öppna Windows PowerShell på den lokala datorn och gå till mappen där du har sparat det ändrade skriptet.

4. Kör skriptet i Exchange Online PowerShell, till exempel:

   ```powershell
   .\SearchAuditLog.ps1
   ```

Skriptet visar meddelanden om förloppet medan det körs. När skriptet har slutförts skapas loggfilen och CSV-filen som innehåller granskningsposterna. De sparas i de mappar som definieras av variablerna `$logFile` och `$outputFile`.

> [!IMPORTANT]
> Det finns en gräns på 50 000 för det maximala antalet granskningsposter som kan returneras varje gång du kör det här skriptet. Om du kör det här skriptet och det returnerar 50 000 resultat är det troligt att det finns granskningsposter för aktiviteter som inträffat inom datumintervallet som inte har tagits med. Om det här händer rekommenderar vi att du delar upp datumintervallet i kortare tidsperioder och sedan kör skriptet igen för varje datumintervall. Om till exempel ett datumintervall på 90 dagar returnerar 50 000 resultat kan du köra skriptet igen två gånger, en gång för de första 45 dagarna i datumintervallet och sedan en gång till för de följande 45 dagarna.

## <a name="step-3-format-and-view-the-audit-records"></a>Steg 3: Formatera och visa granskningsposterna

När du har kört skriptet och exporterat granskningsposterna till en CSV-fil kan det vara bra att formatera CSV-filen för att göra det lättare att granska och analysera granskningsposterna. Ett sätt att göra det här är att använda Power Query-funktionen för JSON-transformering i Excel för att dela upp varje egenskap i JSON-objektet i kolumnen **AuditData** i en egen kolumn. Stegvisa instruktioner finns i ”Steg 2: Formatera den exporterade granskningsloggen med Power Query-redigeraren” i [Exportera, konfigurera och visa granskningsloggposter](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).
