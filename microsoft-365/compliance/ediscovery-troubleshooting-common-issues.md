---
title: Felsöka vanliga eDiscovery-problem
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Läs mer om grundläggande felsökningssteg du kan vidta för att lösa vanliga problem Office 365 eDiscovery.
siblings_only: true
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 28c092cefbdd8add46d3f36aa118e230d16a918a
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822244"
---
# <a name="investigate-troubleshoot-and-resolve-common-ediscovery-issues"></a>Undersöka, felsöka och lösa vanliga eDiscovery-problem

Det här avsnittet beskriver grundläggande felsökningssteg du kan vidta för att identifiera och lösa problem som kan uppstå under en eDiscovery-sökning eller någon annanstans i eDiscovery-processen. För att du ska kunna lösa vissa av de här scenarierna behöver du hjälp från Microsoft Support. Information om när du kontaktar Microsoft Support ingår i lösningsstegen.

## <a name="errorissue-ambiguous-location"></a>Fel/problem: Tvetydig plats

Om du försöker lägga till användarens postlådas plats för sökning och det finns dubbletter eller objekt i konflikt med samma användar-ID i Exchange Online Protection-katalogen (EOP) visas följande felmeddelande: `The compliance search contains the following invalid location(s):useralias@contoso.com. The location "useralias@contoso.com" is ambiguous` .

### <a name="resolution"></a>Lösning

Sök efter dubbletter av användare eller distributionslistor med samma användar-ID.

1. Anslut till [Säkerhets- & Efterlevnadscenter PowerShell.](/powershell/exchange/connect-to-scc-powershell)

2. Kör följande kommando för att hämta alla förekomster av användarnamnet:

    ```powershell
    Get-Recipient <username>
    ```

   Utdata för "useralias@contoso.com" skulle se ut ungefär så här:

   > 
   > |Namn|RecipientType|
   > |---|---|
   > |Alias, användare|MailUser|
   > |Alias, användare|Användare|

3. Om flera användare returneras letar du reda på och åtgärdar det objekt som ligger i konflikt.

## <a name="errorissue-search-fails-on-specific-locations"></a>Fel/problem: Sökningen misslyckas på specifika platser

En e-dataidentifiering eller innehållssökning kan ge följande fel: `This search completed with (#) errors.  Would you like to retry the search on the failed locations?`

![Skärmbild på ett fel om att en sökspecifik plats misslyckas](../media/edisc-tshoot-specific-location-search-fails.png)

### <a name="resolution"></a>Lösning

Om du får det här felet rekommenderar vi att du verifierar de platser som misslyckades i sökningen och sedan kör sökningen på de misslyckade platserna igen.

1. Anslut [säkerhets- & Säkerhets- och efterlevnadscenter PowerShell](/powershell/exchange/connect-to-scc-powershell) och kör sedan följande kommando:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. I PowerShell-utdata kan du visa de misslyckade platserna i felfältet eller i statusinformationen i felmeddelandet från sökresultatet.

3. Försök bara att söka efter eDiscovery på de misslyckade platserna.

4. Om du fortsätter att få de här felen kan du [läsa mer om felsökningssteg i](/Office365/SecurityCompliance/retry-failed-content-search) Försök igen med misslyckade platser.

## <a name="errorissue-file-not-found"></a>Fel/problem: Filen hittades inte

När du kör en eDiscovery-sökning som innehåller SharePoint Online och One Drive för företag-platser, kan du få felmeddelandet trots att filen finns `File Not Found` på webbplatsen. Det här felet visas i exportvarningarna och errors.csv hoppas över items.csv. Detta kan inträffa om filen inte kan hittas på webbplatsen eller om indexet är in datera. Här är texten för ett faktiskt fel (med betoning).

> 28.06.2019 10:02:19_FailedToExportItem_Failed för att ladda ned innehåll. Ytterligare diagnostikinformation: Microsoft. Office. Compliance.EDiscovery.ExportWorker.Exceptions.ContentDownloadTemporaryFailure: Det gick inte att ladda ned från innehåll 6ea52149-91cd-4965-b5bb-82ca6a3ec9be av typen Dokument. Korrelations-ID: 3bd84722-937b-4c23-b61b-08d6fba9ec32. ServerErrorCode: -2147024894 ---> Microsoft. SharePoint. Client.ServerException: ***File Not Found***. på Microsoft. SharePoint. Client.ClientRequest.ProcessResponseStream(Stream responseStream) på Microsoft. SharePoint. Client.ClientRequest.ProcessResponse() --- i slutet av den inre undantagsstapelspårningen ---

### <a name="resolution"></a>Lösning

1. Kontrollera platsen som identifieras i sökningen för att säkerställa att filens plats är korrekt och läggs till på sökplatserna.

2. Använd procedurerna i Manuellt begära crawlning och [omindexering](/sharepoint/crawl-site-content) av en webbplats, ett bibliotek eller en lista för att indexera om webbplatsen.

## <a name="errorissue-this-file-wasnt-exported-because-it-doesnt-exist-anymore-the-file-was-included-in-the-count-of-estimated-search-results-because-its-still-listed-in-the-index-the-file-will-eventually-be-removed-from-the-index-and-wont-cause-an-error-in-the-future"></a>Fel/problem: Filen exporterades inte eftersom den inte längre finns. Filen inkluderades i antalet uppskattade sökresultat eftersom den fortfarande finns med i indexet. Filen tas så småningom bort från indexet och orsakar inte något fel i framtiden.

Det felmeddelandet kan visas när du kör en eDiscovery-sökning som innehåller SharePoint Online- och One Drive för företag-platser. eDiscovery använder SPO-indexet för att identifiera filplatserna. Om filen togs bort men SPO-indexet inte uppdaterades än kan det här felet uppstå.

### <a name="resolution"></a>Lösning 
Öppna SPO-platsen och kontrollera att filen verkligen inte finns där.
Den föreslagna lösningen är att indexera om webbplatsen manuellt eller vänta tills webbplatsen indexeras om av den automatiska bakgrundsprocessen.


## <a name="errorissue-this-search-result-was-not-downloaded-as-it-is-a-folder-or-other-artefact-that-cant-be-downloaded-by-itself-any-items-inside-the-folder-or-library-will-be-downloaded"></a>Fel/problem: Sökresultatet har inte laddats ned eftersom det är en mapp eller andra objekt som inte kan laddas ned själv, och objekt i mappen eller biblioteket laddas ned.

Det felmeddelandet kan visas när du kör en eDiscovery-sökning som innehåller SharePoint Online- och One Drive för företag-platser. Det innebär att vi skulle försöka exportera objektet som rapporterats i indexet, men det visades vara en mapp så vi exporterade det inte. Som nämns i felet exporterar vi inte mappobjekt men vi exporterar innehållet.


## <a name="errorissue-search-fails-because-recipient-is-not-found"></a>Fel/problem: Sökningen misslyckas eftersom mottagaren inte hittas

En eDiscovery-sökning misslyckas och felmeddelandet `recipient not found` . Det här felet kan uppstå om användarobjektet inte kan hittas i Exchange Online Protection (EOP) eftersom objektet inte har synkroniserats.

### <a name="resolution"></a>Lösning

1. Anslut till [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Kör följande kommando för att kontrollera om användaren är synkroniserad till Exchange Online Protection:

   ```powershell
   Get-Recipient <userId> | FL
   ```

3. Det bör finnas ett användarobjekt för e-post för användarfrågan. Om ingenting returneras undersöker du användarobjektet. Kontakta Microsoft Support om objektet inte kan synkroniseras.

## <a name="errorissue-exporting-search-results-is-slow"></a>Fel/problem: Det går långsamt att exportera sökresultat

När du exporterar sökresultat från eDiscovery eller innehållssökning i säkerhets- och efterlevnadscentret tar nedladdningen längre tid än väntat.  Du kan kontrollera hur mycket data som ska laddas ned och eventuellt öka exporthastigheten.

### <a name="resolution"></a>Lösning

1. Anslut [säkerhets- & Säkerhets- och efterlevnadscenter PowerShell](/powershell/exchange/connect-to-scc-powershell) och kör sedan följande kommando:

   ```powershell
   Get-ComplianceSearch <searchname> | FL
   ```

2. Hitta mängden data som ska laddas ned i parametrarna SearchResults och SearchStatistics.

3. Kör följande kommando:

   ```powershell
   Get-ComplianceSearchAction | FL
   ```

4. I resultatfältet hittar du de data som har exporterats och visar eventuella fel som uppstått.

5. Leta efter eventuella fel i filen trace.log i katalogen som du exporterade innehållet till.

6. Om du fortfarande har problem kan du dela upp sökningar som returnerar en stor uppsättning resultat i mindre sökningar. Du kan till exempel använda datumintervall i sökfrågor för att returnera ett mindre antal resultat som kan laddas ned snabbare.

## <a name="errorissue-internal-server-error-500-occurred"></a>Fel/problem: "Internt serverfel (500) uppstod"

Om sökningen kontinuerligt misslyckas med fel som liknar "Internt serverfel (500) inträffade" när du kör en eDiscovery-sökning kan du behöva köra sökningen igen endast på specifika postlådeplatser.

![Internt serverfel 500 skärmbild](../media/edisc-tshoot-error-500.png)

### <a name="resolution"></a>Lösning

1. Dela upp sökningen i mindre sökningar och kör sökningen igen.  Prova att använda ett mindre datumintervall eller begränsa antalet platser som genomsöks.

2. Anslut [säkerhets- & Säkerhets- och efterlevnadscenter PowerShell](/powershell/exchange/connect-to-scc-powershell) och kör sedan följande kommando:

   ```powershell Set-CaseHoldPolicy <policyname> -RetryDistribution
   Get-ComplianceSearch <searchname> | FL
   ```

3. Undersök resultatet för resultat och fel.

4. Undersök filen trace.log. Den finns i samma mapp som du exporterade sökresultatet till.

5. Kontakta Microsoft Support.

## <a name="errorissue-holds-dont-sync"></a>Fel/problem: Det går inte att synkronisera spärrar

EDiscovery Case Hold Policy Sync Distribution Error. Följande felmeddelande visas:

> "Resurser: Det tar längre tid än förväntat att distribuera principen. Det kan ta ytterligare 2 timmar att uppdatera den slutliga distributionsstatusen, så titta igen om några timmar."

### <a name="resolution"></a>Lösning

1. Anslut [säkerhets- & Säkerhets- och](/powershell/exchange/connect-to-scc-powershell) efterlevnadscenter PowerShell och kör sedan följande kommando för att hålla ett eDiscovery-ärende:

   ```powershell
   Get-CaseHoldPolicy <policyname> - DistributionDetail | FL
   ```

    Kör följande kommando för en bevarandeprincip:

   ```powershell
   Get-RetentionCompliancePolicy <policyname> - DistributionDetail | FL
   ```

2. Undersök värdet i parametern DistributionDetaljer för fel som följande:

   > Fel: Resurser: Det tar längre tid än förväntat att distribuera principen. Det kan ta ytterligare 2 timmar att uppdatera den slutliga distributionsstatusen, så titta igen om några timmar."

3. Prova att köra parametern RetryDistribution för principen i fråga:

   För eDiscovery-ärende:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

   För bevarandeprinciper:

   ```powershell
   Set-RetentionCompliancePolicy <policyname> -RetryDistribution
   ```

4. Kontakta Microsoft Support.

## <a name="error-the-condition-specified-using-http-conditional-headers-is-not-met"></a>Fel: "Villkoret som anges med HTTP-villkorsrubriker inte uppfylls"

När du laddar ned sökresultat med eDiscovery-exportverktyget kan följande felmeddelande visas: Det här är tillfälligt fel, som vanligtvis förekommer `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` i Azure Storage plats.

### <a name="resolution"></a>Lösning

Du kan lösa problemet genom att försöka [ladda ned sökresultaten igen,](export-search-results.md#step-2-download-the-search-results)som startar om eDiscovery-exportverktyget.

## <a name="errorissue-downloaded-export-shows-no-results"></a>Fel/problem: Nedladdad export visar inga resultat

När exporten har slutförts visas noll filer i resultatet när nedladdningen slutförts via exportverktyget.

### <a name="resolution"></a>Lösning

Det här är ett klientproblem och försök med följande steg för att åtgärda det:

1. Prova att använda en annan klient/dator för att ladda ned.

2. Ta bort gamla sökningar som inte längre behövs med [cmdleten Remove-ComplianceSearch.](/powershell/module/exchange/remove-compliancesearch)

3. Se till att ladda ned till en lokal enhet.

4. Kontrollera att det virusskannern inte körs.

5. Kontrollera att ingen annan export laddas ned till samma mapp eller någon överordnad mapp.

6. Om de föregående stegen inte fungerar inaktiverar du zipping och avduplicering.

7. Om det fungerar beror problemet på en lokal virusskanner eller ett diskproblem.
