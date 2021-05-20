---
title: Vidta svarsåtgärder på en enhet i Microsoft Defender för slutpunkt
description: Vidta svarsåtgärder på en enhet som att isolera enheter, samla in ett undersökningspaket, hantera taggar, köra avsökning och begränsa appkörningen.
keywords: svara, isolera, isolera enhet, samla in undersökningspaket, åtgärdscenter, begränsa, hantera taggar, av skanna, begränsa appen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ae8b08ce3d5bcc34e91f031223108fca053348ce
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572399"
---
# <a name="take-response-actions-on-a-device"></a>Vidta svarsåtgärder på en enhet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Vill du uppleva Defender for Endpoint? [Registrera dig för en gratis provperiod.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-respondmachine-abovefoldlink) 

Svara snabbt på upptäckta attacker genom att isolera enheter eller samla in ett undersökningspaket. När du har tagit åtgärder på enheter kan du kontrollera aktivitetsinformationen i åtgärdscentret.

Svarsåtgärder körs högst upp på en viss enhetssida och inkluderar:

- Hantera taggar
- Initiera automatiserad undersökning
- Starta livesvarssession
- Samla in undersökningspaket
- Kör antivirusgenomsökning
- Begränsa körning av program
- Isolera enhet
- Konsultera en hotexpert
- Åtgärdscenter

[![Bild av svarsåtgärder ](images/response-actions.png)](images/response-actions.png#lightbox)

 Du hittar enhetssidor från någon av följande vyer:

- **Instrumentpanel för säkerhetsåtgärder** – Välj ett enhetsnamn på kortet Enheter i riskzonen.
- **Kö för aviseringar** – Välj enhetsnamnet bredvid enhetsikonen i varningskön.
- **Enhetslista** - Välj rubriken på enhetsnamnet i enhetslistan.
- **Sökruta** – Välj Enhet på den nedrullningsbara menyn och ange enhetens namn.

>[!IMPORTANT]
> - Dessa svarsåtgärder är endast tillgängliga för enheter på Windows 10, version 1703 eller senare. 
> - För icke-Windows-plattformar är svarsfunktioner (till exempel enhets isolering) beroende av funktionerna från tredje part.

## <a name="manage-tags"></a>Hantera taggar

Lägga till eller hantera taggar för att skapa en logisk grupptillhörighet. Enhetstaggar stöder korrekt mappning av nätverket, så att du kan bifoga olika taggar för att fånga kontext och aktivera dynamisk listskapande som en del av en incident.

Mer information om enhetstaggning finns i [Skapa och hantera enhetstaggar](machine-tags.md).

## <a name="initiate-automated-investigation"></a>Initiera automatiserad undersökning

Du kan starta en ny automatiserad undersökning för allmänt syfte på enheten om det behövs. Medan en undersökning körs kommer alla andra aviseringar som genereras från enheten att läggas till i en pågående automatiserad undersökning tills den undersökningen är klar. Dessutom, om samma hot ses på andra enheter, läggs dessa enheter till i undersökningen.

Mer information om automatiserade utredningar finns i [Översikt över automatiserade undersökningar](automated-investigations.md).

## <a name="initiate-live-response-session"></a>Starta livesvarssession

Live-svar är en funktion som ger dig omedelbar åtkomst till en enhet med hjälp av en fjärrskalanslutning. Detta ger dig befogenhet att göra ett fördjupat utredningsarbete och vidta omedelbara åtgärder för att snabbt begränsa identifierade hot – i realtid.

Live-svar är utformat för att förbättra undersökningar genom att du kan samla in kriminaltekniska data, köra skript, skicka misstänkta entiteter för analys, åtgärda hot och proaktivt jaga efter nya hot.

Mer information om livesvar finns i Undersöka [entiteter på enheter som använder livesvar](live-response.md).

## <a name="collect-investigation-package-from-devices"></a>Samla in undersökningspaket från enheter

Som en del av undersöknings- eller svarsprocessen kan du samla in ett undersökningspaket från en enhet. Genom att samla in undersökningspaketet kan du identifiera enhetens aktuella tillstånd och ytterligare förstå de verktyg och tekniker som används av angriparen.

Så här laddar du ned paketet (Zip-filen) och undersöker händelserna som inträffade på en enhet

1. Välj **Samla in undersökningspaket** från raden med svarsåtgärder högst upp på enhetssidan.
2. Ange i textrutan varför du vill utföra den här åtgärden. Välj **Bekräfta**.
3. Zip-filen laddas ner

Alternativt sätt:

1. Välj **Åtgärdscenter** i avsnittet svarsåtgärder på enhetssidan.

    ![Bild av knappen Åtgärdscenter](images/action-center-package-collection.png)

3. I utfällbara åtgärdscenter väljer du **Paketsamlingspaket som är tillgängligt för** att hämta zip-filen.
  
    ![Bild av knappen ladda ner paket](images/collect-package.png)

Paketet innehåller följande mappar:

| mapp | Beskrivning |
|:---|:---------|
|Kör automatiskt | Innehåller en uppsättning filer som var och en representerar innehållet i registret i en känd automatisk start start punkt (ASEP) för att identifiera angriparens beständighet på enheten. </br></br> <div class="alert"><b>OBS:</b> Om registernyckeln inte hittas innehåller filen följande meddelande: "FEL: Systemet kunde inte hitta den angivna registernyckeln eller det angivna registervärdet."</div>                                                                                                                                |
|Installerade program | Den .CSV filen innehåller listan över installerade program som kan hjälpa till att identifiera vad som för närvarande är installerat på enheten. Mer information finns i [Win32_Product klass](https://go.microsoft.com/fwlink/?linkid=841509).                                                                                  |
|Nätverksanslutningar | Den här mappen innehåller en uppsättning datapunkter relaterade till anslutningsinformationen som kan hjälpa till att identifiera anslutning till misstänkta webbadresser, angriparens C&C-infrastruktur (Command and Control), eventuella laterala rörelser eller fjärranslutningar.</br></br> - ActiveNetConnections.txt – Visar protokollstatistik och aktuella TCP/IP-nätverksanslutningar. Ger möjlighet att leta efter misstänkt anslutning som görs av en process. </br></br> - Arp.txt – Visar ARP-cachetabeller (Current Address Resolution Protocol) för alla gränssnitt. </br></br> ARP-cache kan avslöja ytterligare värdar i ett nätverk som har komprometterats eller misstänkta system i nätverket som kan ha använts för att köra en intern attack.</br></br> - DnsCache.txt - Visar innehållet i DNS-klientens matchningscachen, som innehåller båda posterna förinlästa från den lokala Hosts-filen och eventuella nyligen erhållna resursposter för namnfrågor som lösts av datorn. Detta kan hjälpa till att identifiera misstänkta anslutningar. </br></br> - IpConfig.txt – Visar den fullständiga TCP/IP-konfigurationen för alla adaptrar. Kort kan representera fysiska gränssnitt, till exempel installerade nätverkskort eller logiska gränssnitt, till exempel fjärranslutningar. </br></br> - FirewallExecutionLog.txt och pfirewall.log                                                                                  |
| Förfetch filer| Windows Prefetch-filer är utformade för att påskynda programstartprocessen. Det kan användas för att spåra alla filer som nyligen använts i systemet och hitta spår för program som kan ha tagits bort men som fortfarande finns i förhämtningsfillistan. </br></br> - Prefetch mapp – innehåller en kopia av prefetch filer från `%SystemRoot%\Prefetch` . Obs: Det föreslås att ladda ner en prefetch filvisare för att visa prefetch-filerna. </br></br> - PrefetchFilesList.txt – Innehåller listan över alla kopierade filer som kan användas för att spåra om det fanns några kopieringsfel i förhämtningsmappen.                                                                                                      |
| Processer| Innehåller en .CSV fil som listar de processer som körs, vilket ger möjlighet att identifiera aktuella processer som körs på enheten. Detta kan vara användbart när du identifierar en misstänkt process och dess tillstånd.                                                                                                                                                                                                       |
| Schemalagda aktiviteter| Innehåller en .CSV fil som listar de schemalagda aktiviteterna, som kan användas för att identifiera rutiner som utförs automatiskt på en vald enhet för att leta efter misstänkt kod som har ställts in för att köras automatiskt.                                                                                                                                                                                                      |
| Händelselogg för säkerhet| Innehåller säkerhetshändelseloggen, som innehåller poster för inloggnings- eller utloggningsaktivitet, eller andra säkerhetsrelaterade händelser som anges i systemets granskningsprincip. </br></br><div class="alert"><b>OBS:</b> Öppna händelseloggfilen med Loggboken.</div>                                                                                    |
| Tjänster| Innehåller en .CSV fil som listar tjänster och deras tillstånd.                                                                                      |
| Windows SMB-sessioner (Server Message Block) | Visar en lista över delad åtkomst till filer, skrivare och seriella portar och diverse kommunikation mellan noder i ett nätverk. Detta kan hjälpa till att identifiera dataexfiltrering eller sidoförflyttning. </br></br> Innehåller filer för SMBInboundSessions och SMBOutboundSession. </br></br> <div class="alert"><b>OBS:</b> Om det inte finns några sessioner (inkommande eller utgående) får du en textfil som talar om för dig att det inte finns några SMB-sessioner hittade.</div>                                                                                                                          |
| Systeminformation| Innehåller en SystemInformation.txt fil som listar systeminformation som OS-version och nätverkskort.                                                                                     |
| Temp kataloger| Innehåller en uppsättning textfiler som visar filerna i %Temp% för alla användare i systemet. </br></br> Detta kan hjälpa till att spåra misstänkta filer som en angripare kan ha släppt på systemet. </br></br> <div class="alert"><b>OBS:</b> Om filen innehåller följande meddelande: "Systemet kan inte hitta den angivna sökvägen", betyder det att det inte finns någon temporär katalog för den här användaren och kan bero på att användaren inte loggade in på systemet.</div>                                                                                                                                         |
| Användare och grupper| Innehåller en lista över filer som var och en representerar en grupp och dess medlemmar.                                                                                                                   |
|WdSupportLogs (på logg)| Ger MpCmdRunLog.txt och MPSupportFiles.cab  </br></br> <div class="alert"><b>OBS:</b> Den här mappen skapas bara på Windows 10, version 1709 eller senare med den samlade uppdateringen från februari 2020 eller senare installerat:</br> Win10 1709 (RS3) Bygg 16299.1717 : [KB4537816](https://support.microsoft.com/en-us/help/4537816/windows-10-update-kb4537816) </br> Win10 1803 (RS4) Bygg 17134.1345 : [KB4537795](https://support.microsoft.com/en-us/help/4537795/windows-10-update-kb4537795) </br> Win10 1809 (RS5) Bygg 17763.1075 : [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818) </br> Win10 1903/1909 (19h1/19h2) Bygger 18362.693 och 18363.693 : [KB4535996](https://support.microsoft.com/en-us/help/4535996/windows-10-update-kb4535996) </div>                                                                                                                    |
| CollectionSummaryReport.xls| Den här filen är en sammanfattning av undersökningspaketsamlingen, den innehåller listan över datapunkter, kommandot som används för att extrahera data, körningsstatusen och felkoden i händelse av fel. Du kan använda den här rapporten för att spåra om paketet innehåller alla förväntade data och identifiera om det fanns några fel. |

## <a name="run-microsoft-defender-antivirus-scan-on-devices"></a>Kör Microsoft Defender Antivirus skanna på enheter

Som en del av undersökningen eller svarsprocessen kan du fjärrinitiera en antivirussökning för att identifiera och åtgärda skadlig kod som kan finnas på en komprometterad enhet.

>[!IMPORTANT]
>- Den här åtgärden är tillgänglig för enheter Windows 10, version 1709 eller senare.
>- En Microsoft Defender Antivirus (Microsoft Defender AV) kan köras tillsammans med andra antiviruslösningar, oavsett om Microsoft Defender AV är den aktiva antiviruslösningen eller inte. Microsoft Defender AV kan vara i passivt läge. Mer information finns i [Microsoft Defender Antivirus kompatibilitet](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility.md).

En som du har valt **Kör antivirussökning**, välj den skanningstyp som du vill köra (snabb eller fullständig) och lägg till en kommentar innan du bekräftar skanningen.

![Bild av meddelande för att välja snabbsökning eller fullständig skanning och lägga till kommentar](images/run-antivirus.png)

Åtgärdscentret visar skanningsinformationen och enhetens tidslinje innehåller en ny händelse, vilket återspeglar att en genomsökningsåtgärd har skickats på enheten. Microsoft Defender AV-aviseringar återspeglar alla identifieringar som visades under genomsökningen.

>[!NOTE]
>När du utlöser en genomsökning med defender for endpoint-svarsåtgärd gäller fortfarande värdet ScanAvgCPULoadFactor för Antivirus "ScanAvgCPULoadFactor" och begränsar CPU-effekten av genomsökningen.<br> Om ScanAvgCPULoadFactor inte är konfigurerat är standardvärdet en gräns på 50 % maximal CPU-belastning under en genomsökning.<br>
>Mer information finns i [konfigurera avancerade skanningstyper-microsoft-defender-antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-advanced-scan-types-microsoft-defender-antivirus).

## <a name="restrict-app-execution"></a>Begränsa körning av program

Förutom att begränsa en attack genom att stoppa skadliga processer kan du också låsa en enhet och förhindra att efterföljande försök med potentiellt skadliga program körs.

>[!IMPORTANT]
> - Den här åtgärden är tillgänglig för enheter Windows 10, version 1709 eller senare.
> - Den här funktionen är tillgänglig om din organisation använder Microsoft Defender Antivirus.
> - Den här åtgärden måste uppfylla Windows Defender programkontrollkodintegritetsprincipformat och signeringskrav. Mer information finns i [Policyformat för kodintegritet och signering](https://docs.microsoft.com/windows/device-security/device-guard/requirements-and-deployment-planning-guidelines-for-device-guard#code-integrity-policy-formats-and-signing).

För att begränsa ett program från att köras tillämpas en kodintegritetsprincip som bara tillåter filer att köras om de är signerade av ett Microsoft-utfärdat certifikat. Den här begränsningsmetoden kan hjälpa till att förhindra att en angripare kontrollerar komprometterade enheter och utför ytterligare skadliga aktiviteter.

>[!NOTE]
>Du kan när som helst ändra begränsningen av program från att köras. Knappen på enhetssidan ändras för att säga Ta **bort appbegränsningar**, och sedan vidtar du samma steg som att begränsa appkörningen.

När du har valt Begränsa **appkörning** på enhetssidan skriver du en kommentar och väljer **Bekräfta**. Åtgärdscentret visar skanningsinformationen och enhetens tidslinje innehåller en ny händelse.

![Bild av meddelande om appbegränsning](images/restrict-app-execution.png)

**Meddelande om enhetsanvändare:**</br>
När en app är begränsad visas följande meddelande för att informera användaren om att en app begränsas från att köras:

![Bild av appbegränsning](images/atp-app-restriction.png)

## <a name="isolate-devices-from-the-network"></a>Isolera enheter från nätverket

Beroende på attackens allvarlighetsgrad och enhetens känslighet kanske du vill isolera enheten från nätverket. Den här åtgärden kan hjälpa till att förhindra att angriparen kontrollerar den komprometterade enheten och utför ytterligare aktiviteter som dataexfiltrering och sidoförflyttning.

>[!IMPORTANT]
>- Fullständig isolering är tillgänglig för enheter på Windows 10, version 1703.
>- Selektiv isolering är tillgänglig för enheter på Windows 10, version 1709 eller senare.
>- När du isolerar en enhet är endast vissa processer och destinationer tillåtna. Därför kan enheter som ligger bakom en fullständig VPN-tunnel inte nå molntjänsten Microsoft Defender för Slutpunkt när enheten har isolerats. Vi rekommenderar att du använder en VPN med delad tunnel för Microsoft Defender för slutpunkt och Microsoft Defender Antivirus med molnbaserad skyddsrelaterad trafik.

Den här enhets isolerings funktionen kopplar från den komprometterade enheten från nätverket samtidigt som anslutningen till tjänsten Defender för punkt, som fortsätter att övervaka enheten, bibehålls.

I Windows 10, version 1709 eller senare, har du ytterligare kontroll över nätverksisoleringsnivån. Du kan också välja att aktivera Outlook, Microsoft Teams och Skype för företag anslutning (även skrivet selektiv isolering).

>[!NOTE]
>Du kan när som helst återansluta enheten till nätverket. Knappen på enhetssidan ändras för att säga **Släpp från isolering**, och sedan vidtar du samma steg som att isolera enheten.

När du har valt **Isolera enhet på** enhetssidan skriver du en kommentar och väljer **Bekräfta**. Åtgärdscentret visar skanningsinformationen och enhetens tidslinje innehåller en ny händelse.

![Bild av isolatanordning](images/isolate-device.png)

>[!NOTE]
>Enheten förblir ansluten till tjänsten Defender for Endpoint även om den är isolerad från nätverket. Om du har valt att aktivera Outlook Skype för företag kommunikation kan du kommunicera med användaren medan enheten är isolerad.

**Meddelande om enhetsanvändare:**</br>
När en enhet isoleras visas följande meddelande för att informera användaren om att enheten isoleras från nätverket:

![Bild av ingen nätverksanslutning](images/atp-notification-isolate.png)

## <a name="consult-a-threat-expert"></a>Konsultera en hotexpert

Du kan konsultera en Microsoft-hotexpert för mer information om en potentiellt komprometterad enhet eller redan komprometterade. Microsoft Hotexperter kan aktiveras direkt inifrån Microsoft Defender Säkerhetscenter för snabb och korrekt respons. Experter ger insikter inte bara om en potentiellt komprometterad enhet, utan också för att bättre förstå komplexa hot, riktade attackmeddelanden som du får eller om du behöver mer information om aviseringarna eller en hotinformationskontext som du ser på portalpanelen.

Mer [information finns i Kontakta en Microsoft Threat Expert.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization)


## <a name="check-activity-details-in-action-center"></a>Kontrollera aktivitetsinformation i Åtgärdscenter

**Åtgärdscentret** innehåller information om åtgärder som har vidtagits på en enhet eller fil. Du kan se följande information:

- Insamling av utredningspaket
- Antivirussökning
- Begränsning av appar
- Isolering av enhet

Alla andra relaterade uppgifter visas också, till exempel inlämningsdatum/-tid, skickande användare och om åtgärden lyckades eller misslyckades.

![Bild av åtgärdscenter med information](images/action-center-details.png)

## <a name="related-topic"></a>Relaterat ämne
- [Vidta svarsåtgärder för en fil](respond-file-alerts.md)
- [Rapportera felaktigheter](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-security-recommendation#report-inaccuracy)
