---
title: Exportera resultat för innehållssökning
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ed48d448-3714-4c42-85f5-10f75f6a4278
description: Exportera sökresultatet från en innehållssökning i säkerhets- Microsoft 365 till en lokal dator. E-postresultat exporteras som PST-filer. Innehåll från SharePoint och OneDrive för företag exporteras som ursprungliga dokument Office dokument.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3bb46966ddd8d4b2ae61091b126daea1413039ac
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/24/2021
ms.locfileid: "52162813"
---
# <a name="export-content-search-results"></a>Exportera resultat för innehållssökning

När du har kört en innehållssökning kan du exportera sökresultatet till en lokal dator. När du exporterar e-postresultat laddas de ned till datorn som PST-filer. När du exporterar innehåll SharePoint och OneDrive för företag webbplatser exporteras kopior av Office dokument. Det finns andra dokument och rapporter som ingår i de exporterade sökresultaten.
  
Om du exporterar resultaten av en innehållssökning förbereds resultaten och hämtas sedan till en lokal dator.
  
## <a name="before-you-export-content-search-results"></a>Innan du exporterar sökresultat för innehåll

- Om du vill exportera sökresultat måste du ha rollen Exporthantering i Säkerhets- & Efterlevnadscenter. Den här rollen tilldelas till den inbyggda rollgruppen för eDiscovery-hanteraren. Den är som standard inte tilldelad rollgruppen Organisationshantering. Mer information finns i Tilldela [eDiscovery-behörigheter.](assign-ediscovery-permissions.md)

- Datorn du använder för att exportera sökresultaten måste uppfylla följande systemkrav:
  
  - Senaste versionen av Windows (32-bitars eller 64-bitars)
  
  - Microsoft .NET Framework 4.7
  
- Du måste använda någon av följande webbläsare som stöds för att köra eDiscovery Export Tool<sup>1:</sup>

  - Microsoft Edge <sup>2</sup>
  
    ELLER

  - Microsoft Internet Explorer 10 och senare versioner
  
  > [!NOTE]
  > <sup>1</sup> Microsoft tillverkar inte tillägg eller tillägg från tredje part för ClickOnce tilläggsprogram. Export av sökresultat med en webbläsare som inte stöds med tillägg eller tillägg från tredje part stöds inte.<br/>
  > <sup>2</sup> På grund av de senaste ändringarna Microsoft Edge är ClickOnce inte längre aktiverat som standard. Anvisningar om hur du aktiverar ClickOnce i Edge finns i [Använda verktyget för eDiscovery-export i Microsoft Edge.](configure-edge-to-export-search-results.md)
  
- Vi rekommenderar att du laddar ned sökresultat till en lokal dator. Men om du vill eliminera företagets brandvägg eller proxyinfrastruktur från att orsaka problem när du laddar ned sökresultat kan du överväga att ladda ned sökresultat till ett virtuellt skrivbord utanför nätverket. Det kan minska tidsgränserna för export av Azure-dataanslutningar vid export av ett stort antal filer. Mer information om virtuella skrivbord finns i Windows [Virtual Desktop](https://azure.microsoft.com/services/virtual-desktop). 

- För att förbättra prestandan när du laddar ned sökresultat kan du dela upp sökningar som returnerar en stor uppsättning resultat i mindre sökningar. Du kan till exempel använda datumintervall i sökfrågor för att returnera ett mindre antal resultat som kan laddas ned snabbare.
  
- När du exporterar sökresultat lagras data tillfälligt på en microsoft-tillhandahålls Azure Storage plats i Microsoft Cloud innan de laddas ned till din lokala dator. Se till att din organisation kan ansluta till slutpunkten i Azure, som är **\* .blob.core.windows.net** (jokertecknet representerar en unik identifierare för exporten). Sökresultatdata tas bort från e-Azure Storage två veckor efter att den har skapats. 
  
- Om organisationen använder en proxyserver för att kommunicera med Internet måste du definiera proxyserverinställningarna på datorn som du använder för att exportera sökresultaten (så att exportverktyget kan autentiseras av din proxyserver). Det gör du genom att *machine.config* filen på den plats som överensstämmer med din version Windows. 
  
  - **32-bitars:**`%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`
  
  - **64-bitars:**`%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`
  
    Lägg till följande rader i  *machine.config*  filen någonstans mellan  `<configuration>`  `</configuration>` taggarna och. Se till att  `ProxyServer` ersätta och med rätt värden för din  `Port` organisation, till exempel `proxy01.contoso.com:80` . 
  
    ```xml
    <system.net>
       <defaultProxy enabled="true" useDefaultCredentials="true">
         <proxy proxyaddress="https://ProxyServer :Port " 
                usesystemdefault="False" 
                bypassonlocal="True" 
                autoDetect="False" />
       </defaultProxy>
    </system.net>
    ```

## <a name="step-1-prepare-search-results-for-export"></a>Steg 1: Förbereda sökresultat för export

Det första steget är att förbereda sökresultatet för export. När du förbereder resultat överförs de till en plats i Microsoft som Azure Storage i Microsoft-molnet. Innehåll från postlådor och webbplatser laddas upp med en maxhastighet på 2 GB per timme.
  
1. Gå till [https://protection.office.com](https://protection.office.com).
  
2. Logga in med ditt arbets- eller skolkonto.
  
3. I den vänstra rutan i säkerhets- & Säkerhets- och efterlevnadscenter klickar du **på Sök** \> **efter innehållsökning**.
  
4. Välj **en sökning på** sidan Innehållssökning. 
  
5. Klicka på Starta export under **Exportera resultat till en dator** i **informationsfönstret.**
  
    > [!NOTE]
    > Om resultatet för en sökning är äldre än 7 dagar uppmanas du att uppdatera sökresultatet. Om det händer avbryter du  exporten, klickar på Uppdatera sökresultat i informationsfönstret för den valda sökningen och startar exporten igen när resultatet har uppdaterats. 
  
6. Välj **något av följande alternativ** under **Utdataalternativ** på sidan Exportera sökresultat:
  
    - Alla objekt, förutom sådana som har okänt format, krypteras eller inte indexeras av andra orsaker
  
    - Alla objekt, även sådana som har okänt format, krypteras eller inte indexeras av andra orsaker
  
    - Endast objekt som har ett okänt format, är krypterade eller inte indexeras av andra orsaker
  
    I avsnittet [Mer information](#more-information) finns en beskrivning av hur delvis indexerade objekt exporteras. Mer information om delvis indexerade objekt finns i [Delvis indexerade objekt i Innehållssökning.](partially-indexed-items-in-content-search.md)
  
7. Under **Exportera Exchange innehåll som** väljer du något av följande alternativ:
  
    - **En PST-fil för varje postlåda:** Exporterar en PST-fil för varje användarpostlåda som innehåller sökresultat. Resultat från användarens arkivpostlåda inkluderas i samma PST-fil. Det här alternativet återskapar postlådemappstrukturen från källpostlådan.
  
    - **En PST-fil som innehåller alla meddelanden:** Exporterar en enskild PST-fil *(Exchange.pst)* som innehåller sökresultaten från alla källpostlådor som ingår i sökningen. Det här alternativet återskapar postlådemappstrukturen för varje meddelande.
  
    - **En PST-fil som innehåller alla meddelanden i en enda mapp:** Exporterar sökresultat till en enda PST-fil där alla meddelanden finns i en mapp på översta nivån. Med det här alternativet kan granskare granska objekt i kronologisk ordning (objekt sorteras efter skickat datum) utan att behöva navigera i den ursprungliga postlådemappstrukturen för varje objekt.
  
    - **Enskilda meddelanden:** Exporterar sökresultat som enskilda e-postmeddelanden med formatet .msg. Om du väljer det här alternativet exporteras sökresultat för e-post till en mapp i filsystemet. Mappsökvägen för enskilda meddelanden är densamma som den som användes när du exporterade resultatet till PST-filer.
  
      > [!IMPORTANT]
      > Om du vill dekryptera RMS-skyddade meddelanden när de exporteras måste du exportera e-postsökresultat som enskilda meddelanden. Krypterade meddelanden förblir krypterade om du exporterar sökresultatet som en PST-fil. Mer information finns i [Dekryptera RMS-skyddade e-postmeddelanden och krypterade bifogade filer i](#decrypting-rms-protected-email-messages-and-encrypted-file-attachments) den här artikeln.
  
8. Klicka på **kryssrutan Aktivera avduplicering** om du vill utesluta dubblettmeddelanden. Det här alternativet visas bara om innehållskällorna för sökningen omfattar Exchange postlådor eller gemensamma mappar. 
  
    Om du väljer det här alternativet exporteras bara en kopia av ett meddelande även om flera kopior av samma meddelande hittas i postlådorna som genomsöktes. Exportresultatrapporten (Results.csv) innehåller en rad för varje kopia av ett duplicerat meddelande så att du kan identifiera postlådorna (eller de gemensamma mapparna) som innehåller en kopia av dubblettmeddelandet. Mer information om avduplicering och hur dubbletter identifieras finns i [Avduplicering i eDiscovery-sökresultat.](de-duplication-in-ediscovery-search-results.md)
  
9. Klicka på **kryssrutan Inkludera versioner SharePoint dokument om** du vill exportera alla versioner SharePoint dokument. Det här alternativet visas bara om innehållskällorna för sökningen omfattar SharePoint eller OneDrive för företag webbplatser. 
  
10. Klicka på **kryssrutan Exportera filer i en komprimerad mapp om** du vill exportera sökresultatet till komprimerade mappar. Det här alternativet är bara tillgängligt när du väljer att exportera Exchange objekt som enskilda meddelanden och när sökresultatet innehåller SharePoint eller OneDrive dokument. Det här alternativet används främst för att komma runt gränsen på 260 Windows i sökvägsnamnen när objekt exporteras. Se "Filnamn på exporterade objekt" i avsnittet [Mer information.](#more-information) 
  
11. Klicka **på Starta export.** Sökresultaten förbereds för nedladdning, vilket innebär att de laddas upp till en Azure Storage plats i Microsoft-molnet. Det kan ta flera minuter.

Instruktioner för hur du laddar ned exporterade sökresultat finns i nästa avsnitt.
  
## <a name="step-2-download-the-search-results"></a>Steg 2: Ladda ned sökresultatet

Nästa steg är att ladda ned sökresultatet från den Azure Storage platsen till din lokala dator.
  
1. Klicka på **fliken Exporter** på **sidan Innehållssökning.** 
  
   Du kanske måste klicka på **Uppdatera** för att uppdatera listan med exportjobb så att den visar det exportjobb du har skapat. Exportjobb har samma namn som motsvarande sökning **_Export** lagts till i söknamnet.
  
2. Välj det exportjobb som du skapade i steg 1.

3. På den utfällna sidan under **Exportera-tangenten** klickar **du på Kopiera till Urklipp.** Du använder den här nyckeln i steg 6 för att ladda ned sökresultaten.
  
4. Klicka **på Ladda ned resultat.**

5. Om du uppmanas att installera **eDiscovery-exportverktyget klickar** du på **Installera**.

6. I **eDiscovery-exportverktyget** gör du följande:

   ![eDiscovery-exportverktyget](../media/eDiscoveryExportTool.png)

   1. Klistra in exportnyckeln som du kopierade i steg 3 i lämplig ruta.
  
   2. Klicka **på** Bläddra för att ange den plats där du vill ladda ned sökresultatfilerna.
  
      > [!IMPORTANT]
      >  På grund av hög nätverksaktivitet vid nedladdning bör du bara ladda ned sökresultatet till en plats på en intern enhet på den lokala datorn. Följ de här riktlinjerna för att få den bästa nedladdningsupplevelsen: <br/>
      >- Ladda inte ned sökresultat till en UNC-sökväg, en mappad nätverksenhet, en extern USB-enhet eller ett synkroniserat OneDrive för företag konto.<br/>
      >- Inaktivera antivirusskanning för mappen som du laddar ned sökresultatet till.<br/>
      >- Ladda ned sökresultat till olika mappar för samtidiga nedladdningsjobb.

6. Klicka **på Start** för att ladda ned sökresultatet till datorn.
  
    I **verktyget eDiscovery Export** visas statusinformation om exporten, inklusive en uppskattning av antalet (och storleken) av de återstående objekten som ska laddas ned. När exporten är klar kan du komma åt filerna på den plats där de laddades ned.

## <a name="more-information"></a>Mer information

Här finns mer information om hur du exporterar sökresultat.
  
[Exportgränser](#export-limits)
  
[Exportera rapporter](#export-reports)
  
[Exportera delvis indexerade objekt](#exporting-partially-indexed-items)

[Exportera enskilda meddelanden eller PST-filer](#exporting-individual-messages-or-pst-files)

[Dekryptera RMS-skyddade e-postmeddelanden och krypterade bifogade filer](#decrypting-rms-protected-email-messages-and-encrypted-file-attachments)

[Filnamn på exporterade objekt](#filenames-of-exported-items)  
  
[Diverse](#miscellaneous)
  
### <a name="export-limits"></a>Exportgränser

Information om begränsningar när du exporterar innehållssökningsresultat finns i avsnittet "Exportera begränsningar" i [Begränsningar för innehållssökning](limits-for-content-search.md#export-limits).

### <a name="export-reports"></a>Exportera rapporter
  
- När du exporterar sökresultaten ingår följande rapporter utöver sökresultaten.
  
  - **Sammanfattning av export** Ett Excel som innehåller en sammanfattning av exporten. Det omfattar information som antal innehållskällor som har sökts, den uppskattade och hämtade storleken på sökresultatet och det uppskattade och nedladdade antalet objekt som exporterades.
  
  - **Manifest** En manifestfil (i XML-format) som innehåller information om varje objekt som ingår i sökresultatet.
  
  - **Resultat** Ett Excel som innehåller information om varje objekt som hämtas som sökresultat. För e-post innehåller resultatloggen information om varje meddelande, inklusive:
  
    - Platsen för meddelandet i källpostlådan (inklusive om meddelandet finns i den primära postlådan eller arkivpostlådan).
  
    - Datumet då meddelandet skickades eller togs emot.

    - Ämnesraden från meddelandet.

    - Meddelandets avsändare och mottagare.

    - Om meddelandet är ett duplicerat meddelande om du har aktiverat avdupliceringsalternativet när du exporterar sökresultatet. Dubblettmeddelanden har ett värde i **kolumnen Duplicera till** objekt som identifierar meddelandet som en dubblett. Värdet i kolumnen **Duplicera till** objekt innehåller objektidentiteten för meddelandet som exporterades. Mer information finns i [Avduplicering i eDiscovery-sökresultat.](de-duplication-in-ediscovery-search-results.md)

      För dokument SharePoint och OneDrive för företag innehåller resultatloggen information om varje dokument, inklusive:

      - URL-adressen för dokumentet.

      - URL-adressen för webbplatssamlingen där dokumentet finns.

      - Datumet då dokumentet senast ändrades.

      - Namnet på dokumentet (som finns i kolumnen Ämne i resultatloggen).

  - **Icke indexerade objekt** Ett Excel som innehåller information om delvis indexerade objekt som skulle ingå i sökresultatet. Om du inte tar med delvis indexerade objekt när du skapar sökresultatrapporten kommer den här rapporten fortfarande att laddas ned, men den är tom.

  - **Fel och varningar** Innehåller fel och varningar för filer som påträffades under exporten. I kolumnen Felinformation finns information som är specifik för varje enskilt fel eller varning.

  - **Objekt som hoppats över** När du exporterar sökresultat från SharePoint och OneDrive för företag-webbplatser innehåller exporten vanligtvis en rapport över överhoppade objekt (SkippedItems.csv). Citerade objekt i den här rapporten är vanligtvis objekt som inte laddas ned, till exempel en mapp eller en dokumentuppsättning. Att inte exportera den här typen av objekt är enligt design. För andra objekt som hoppades över visar fältet "Feltyp" och "Felinformation" i rapporten överhoppade objekt orsaken till att objektet hoppades över och inte laddades ned med de andra sökresultaten.

  - **Spåra logg** Innehåller detaljerad loggningsinformation om exporten och kan hjälpa dig att upptäcka problem under exporten.
  
    > [!NOTE]
    > Du kan bara exportera dessa dokument utan att behöva exportera de faktiska sökresultaten. Se [Exportera en rapport för innehållssökning](export-a-content-search-report.md). 
  
### <a name="exporting-partially-indexed-items"></a>Exportera delvis indexerade objekt
  
- Om du exporterar postlådeobjekt från en innehållssökning som returnerar alla postlådeobjekt i sökresultatet (eftersom inga nyckelord anges i sökfrågan) kopieras inte delvis indexerade objekt till PST-filen som innehåller icke indexerade objekt. Det beror på att alla objekt, inklusive delvis indexerade objekt, automatiskt inkluderas i de vanliga sökresultaten. Det innebär att delvis indexerade objekt inkluderas i en PST-fil (eller som enskilda meddelanden) som innehåller andra indexerade objekt.

    Om du exporterar både indexerade och delvis indexerade objekt eller om du bara exporterar indexerade objekt från en innehållssökning som returnerar alla objekt laddas samma antal objekt ned. Detta inträffar även om det uppskattade sökresultatet för innehållssökningen (visas i sökstatistiken i säkerhets- och efterlevnadscentret för &) fortfarande innehåller en separat uppskattning av antalet delvis indexerade objekt. Anta till exempel att uppskattningen av en sökning som innehåller alla objekt (inga nyckelord i sökfrågan) visar att 1 000 objekt hittades och att 200 delvis indexerade objekt också hittades. I det här fallet innehåller 1 000 objekt delvis indexerade objekt eftersom sökningen returnerar alla objekt. Med andra ord, det finns totalt 1 000 objekt som returneras av sökningen och inte 1 200 objekt (som du kan förvänta dig). Om du exporterar sökresultatet av den här sökningen och väljer att exportera indexerade och delvis indexerade objekt (eller bara delvis indexerat objekt) laddas 1 000 objekt ned. Det beror även på att delvis indexerade objekt inkluderas i de vanliga (indexerade) resultaten när du använder en tom sökfråga för att returnera alla objekt. I samma exempel, om du väljer att exportera endast delvis indexerade objekt, hämtas endast de 200 icke indexerade objekten.

    Observera även att i föregående exempel (när du exporterar indexerade och delvis  indexerade objekt eller bara exporterar indexerade objekt) visades en lista med 1 000 uppskattade objekt och 1 000 nedladdade objekt av samma orsaker som beskrivits tidigare. 

- Om sökningen du exporterar resultat från var en sökning på specifika innehållsplatser eller alla innehållsplatser i organisationen exporteras bara delar av objekt från innehållsplatser som innehåller objekt som matchar sökvillkoren. Med andra ord, om inga sökresultat hittas i en postlåda eller på en webbplats, exporteras inte delvis indexerade objekt i den postlådan eller webbplatsen. Anledningen är att export av delvis indexerade objekt från många platser i organisationen kan öka sannolikheten för exportfel och öka tiden det tar att exportera och ladda ned sökresultaten.

    Om du vill exportera delvis indexerade objekt från alla innehållsplatser för en sökning konfigurerar du sökningen så att alla objekt returneras (genom att nyckelord tas bort från sökfrågan) och sedan exporteras endast delvis indexerade objekt när du exporterar sökresultatet.

    ![Använd det tredje exportalternativet för att exportera endast icke indexerade objekt](../media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- När du exporterar sökresultat från SharePoint eller OneDrive för företag-webbplatser beror möjligheten att exportera icke indexerade objekt också på vilket exportalternativ du väljer och om en webbplats som genomsökts innehåller ett indexerat objekt som matchar sökvillkoren. Om du till exempel söker på specifika SharePoint- eller OneDrive för företag-webbplatser och inga sökresultat hittas exporteras inga icke indexerade objekt från de webbplatserna om du väljer det andra exportalternativet för att exportera både indexerade och icke indexerade objekt. Om ett indexerat objekt från en webbplats matchar sökvillkoren exporteras alla icke indexerade objekt från webbplatsen vid export av både indexerade och icke indexerade objekt. Följande bild beskriver exportalternativen baserat på om en webbplats innehåller ett indexerat objekt som matchar sökvillkoren.

    ![Välj exportalternativ baserat på om en webbplats innehåller ett indexerat objekt som matchar sökvillkoren](../media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    a. Endast indexerade objekt som matchar sökvillkoren exporteras. Inga delvis indexerade objekt exporteras.

    b. Om inga indexerade objekt från en webbplats matchar sökvillkoren exporteras inte delvis indexerade objekt från samma webbplats. Om indexerade objekt från en webbplats returneras i sökresultaten exporteras delvis indexerade objekt från den webbplatsen. Med andra ord exporteras bara delvis indexerade objekt från webbplatser som innehåller objekt som matchar sökvillkoren.

    c. Alla delvis indexerade objekt från alla webbplatser i sökningen exporteras, oavsett om en webbplats innehåller objekt som matchar sökvillkoren.

    Om du väljer att exportera delvis indexerade objekt exporteras delvis indexerade postlådeobjekt i en separat PST-fil oavsett vilket alternativ du väljer under **Exportera Exchange innehåll som**.

- Om delvis indexerade objekt returneras i sökresultatet (eftersom andra egenskaper för delvis indexerade objekt matchade sökvillkoren), exporteras de delvis indexerade med de vanliga sökresultaten. Om du väljer att exportera både indexerade och delvis indexerade objekt (genom att markera alternativet Alla objekt, även sådana som har okänt **format,** krypteras eller inte indexeras av andra orsaker), visas därför delvis indexerade objekt som exporterats med de vanliga resultaten i Results.csv-rapporten. De visas inte i rapporten icke indexerade items.csv indexerade.
  
### <a name="exporting-individual-messages-or-pst-files"></a>Exportera enskilda meddelanden eller PST-filer
  
- Om filnamnet i ett meddelande överskrider gränsen för maximalt Windows trunkeras filnamnet. Men det ursprungliga filnamnet visas i manifestet och resultatloggen.
  
- Som tidigare förklarats exporteras sökresultat för e-post till en mapp i filsystemet. Mappsökvägen för enskilda meddelanden replikerar mappsökvägen i användarens postlåda. Till exempel finns en sökning med namnet "ContosoCase101" i en användares inkorg i mappsökvägen  `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox` .

- Om du väljer att exportera e-postmeddelanden i en PST-fil som innehåller  alla meddelanden i en enda mapp, inkluderas mappen Borttaget och mappen Sökmappar i den översta nivån i PST-mappen.  Mapparna är tomma.

- Som tidigare nämnts måste du exportera sökresultaten som enskilda meddelanden för att dekryptera RMS-skyddade meddelanden när de exporteras. Krypterade meddelanden förblir krypterade om du exporterar e-postsökresultat som en PST-fil.
  
### <a name="decrypting-rms-protected-email-messages-and-encrypted-file-attachments"></a>Dekryptera RMS-skyddade e-postmeddelanden och krypterade bifogade filer

Rättighetsskyddade (RMS-skyddade) e-postmeddelanden som ingår i resultatet av en innehållssökning dekrypteras när du exporterar dem. Alla filer som är krypterade med [](encryption.md) Microsoft-krypteringsteknik och bifogas i ett e-postmeddelande som ingår i sökresultaten dekrypteras också när de exporteras. Den här dekrypteringsfunktionerna är aktiverade som standard för medlemmar i rollgruppen för eDiscovery Manager. Det beror på att rollgruppen tilldelas rollen RMS-dekrypthantering. Tänk på följande när du exporterar krypterade e-postmeddelanden och bifogade filer:
  
- Om du vill dekryptera RMS-skyddade meddelanden när du exporterar dem måste du, som tidigare förklarats, exportera sökresultatet som enskilda meddelanden. Om du exporterar sökresultat till en PST-fil förblir RMS-skyddade meddelanden krypterade.

- Meddelanden som dekrypteras identifieras i **ResultsLog-rapporten.** Den här rapporten innehåller en kolumn med namnet Avkoda **status** och värdet **Avkoda** i den här kolumnen identifierar de meddelanden som har dekrypterats.

- Förutom att dekryptera bifogade filer när du exporterar sökresultat kan du också förhandsgranska den dekrypterade filen när du förhandsgranskar sökresultat. Du kan bara visa det rättighetsskyddade e-postmeddelandet när du exporterat det.

- För stunden innehåller dekrypteringsfunktionerna inte krypterat innehåll från SharePoint och OneDrive för företag webbplatser. Support kommer dock snart för dokument som krypteras med microsoft-krypteringstekniker och som lagras i SharePoint Online och OneDrive för företag.

- Om du behöver förhindra att någon dekrypterar RMS-skydda meddelanden och krypterade bifogade filer måste du skapa en anpassad rollgrupp (genom att kopiera den inbyggda rollgruppen för eDiscovery-hanteraren) och sedan ta bort RMS-rollen Dekryptera hantering från den anpassade rollgruppen. Lägg sedan till den person som du inte vill dekryptera meddelanden till som medlem i den anpassade rollgruppen.
  
### <a name="filenames-of-exported-items"></a>Filnamn på exporterade objekt
  
- Det finns en begränsning på 260 tecken (som införs i operativsystemet) för det fullständiga sökvägsnamnet för e-postmeddelanden och webbplatsdokument som exporteras till den lokala datorn. Den fullständiga sökvägen för exporterade objekt innehåller objektets ursprungliga plats och mappplatsen på den lokala datorn dit sökresultaten hämtas. Om du till exempel anger att sökresultatet ska hämtas till verktyget eDiscovery Export blir den fullständiga sökvägen för ett  `C:\Users\Admin\Desktop\SearchResults` nedladdat e-postobjekt  `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg` .

- Om gränsen på 260 tecken överskrids trunkeras det fullständiga sökvägsnamnet för ett objekt, baserat på följande:

  - Om det fullständiga sökvägsnamnet är längre än 260 tecken förkortas filnamnet så att det ligger under gränsen. Observera att det trunkerade filnamnet (exklusive filnamnstillägget) inte är färre än åtta tecken.

  - Om den fullständiga sökvägen är för lång efter att filnamnet förkortats flyttas objektet från dess aktuella plats till den överordnade mappen. Om sökvägen fortfarande är för lång upprepas processen: förkorta filnamnet och om det behövs flytta igen till den överordnade mappen. Den här processen upprepas tills den fullständiga sökvägen är under gränsen på 260 tecken.

  - Om det redan finns ett trunkerat fullständigt sökvägsnamn läggs ett versionsnummer till i slutet av filnamnet. till exempel `statusmessage(2).msg` .

    Överväg att ladda ned sökresultaten till en plats med ett kort sökvägsnamn för att minimera problemet. Att ladda ned sökresultat till en mapp med namnet skulle till exempel lägga till färre tecken i sökvägen för exporterade objekt än att ladda ned dem till  `C:\Results` en mapp med namnet  `C:\Users\Admin\Desktop\Results` .

- När du exporterar webbplatsdokument är det också möjligt att det ursprungliga filnamnet på ett dokument ändras. Detta inträffar specifikt för dokument som har tagits bort från en SharePoint eller OneDrive för företag-webbplats som har satts på en plats. När ett dokument som finns på en webbplats som är på en bevarande webbplats tas bort flyttas det borttagna dokumentet automatiskt till biblioteket för bevarande av dokument för webbplatsen (som skapades när webbplatsen skapades som bevarande). När det borttagna dokumentet flyttas till biblioteket för bevarande av dokument läggs ett slumpmässigt genererat och unikt ID till i det ursprungliga filnamnet för dokumentet. Om filnamnet för ett dokument till exempel tas bort och det senare tas bort och flyttas till biblioteket För bevarande av dokument ändras filnamnet på dokumentet som flyttas till biblioteket för bevarande av dokument till något i liknande  `FY2017Budget.xlsx`  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` skick. Om ett dokument i biblioteket för bevarande av dokument matchar frågan för en innehållssökning och du exporterar resultatet av sökningen får den exporterade filen det ändrade filnamnet. I det här exemplet skulle filnamnet på det exporterade dokumentet vara  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` .

    När ett dokument på en webbplats som är på plats ändras (och versionshantering för dokumentbiblioteket på webbplatsen har aktiverats) skapas en kopia av filen automatiskt i biblioteket för bevarande av dokument. I det här fallet läggs även ett slumpmässigt genererat och unikt ID till i filnamnet för det dokument som kopieras till biblioteket Bevarande av dokument.

    Anledningen till att filnamnen på dokument som flyttas eller kopieras till biblioteket för bevarande av dokument är att de inte innehåller filnamn i konflikt. Mer information om hur du placerar ett bevarande på webbplatser och biblioteket för bevarande av dokument finns i Översikt över förvaring i [SharePoint Server 2016.](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95)

### <a name="miscellaneous"></a>Diverse
  
- När du laddar ned sökresultat med eDiscovery-exportverktyget kan följande felmeddelande visas: Det här är tillfälligt fel, som vanligtvis förekommer `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` i Azure Storage plats. Du kan lösa problemet genom att försöka [ladda ned sökresultaten igen,](#step-2-download-the-search-results)som startar om eDiscovery-exportverktyget.

- Alla sökresultat och exportrapporterna ingår i en mapp som har samma namn som Innehållssökning. De e-postmeddelanden som exporterades finns i en mapp med namnet **Exchange**. Dokument finns i en mapp med namnet **SharePoint**.

- Filsystemmetadata för dokument på SharePoint och OneDrive för företag underhålls när dokument exporteras till den lokala datorn. Det innebär att dokumentegenskaper som datum som skapats och senast ändrades inte ändras när dokument exporteras.

- Om sökresultatet innehåller ett listobjekt från SharePoint som matchar sökfrågan exporteras alla rader i listan förutom det objekt som matchar sökfrågan och eventuella bifogade filer i listan. Orsaken till det här beteendet är att skapa ett sammanhang för listobjekt som returneras i sökresultatet. De ytterligare listobjekten och de bifogade filerna kan orsaka att antalet exporterade objekt skiljer sig från den ursprungliga uppskattningen av sökresultaten.
