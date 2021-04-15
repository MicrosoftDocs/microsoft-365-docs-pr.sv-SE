---
title: Distributionsguide för den virtuella skrivbordsinfrastrukturen för Microsoft Defender Antivirus
description: Lär dig hur du distribuerar Microsoft Defender Antivirus i en virtuell skrivbordsmiljö för bästa balans mellan skydd och prestanda.
keywords: vdi, hyper-v, VM, virtuell dator, windows defender, antivirus, av, virtuellt skrivbord, rds, fjärrskrivbord
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.openlocfilehash: fed66586dc0607989e407ecd790d2af8c40e2939
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765737"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Distributionsguide för Microsoft Defender Antivirus i en VDI-miljö (Virtual Desktop Infrastructure)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Förutom standardkonfigurationer för lokal dator eller maskinvara kan du också använda Microsoft Defender Antivirus i en fjärrskrivbordsmiljö (RDS) eller i en VDI-miljö (Virtual Desktop Infrastructure).

Mer [information om Microsoft Fjärrskrivbordstjänster](/azure/virtual-desktop) och VDI-support finns i Dokumentationen för Virtuellt skrivbord för Windows.

För Azure-baserade virtuella datorer, se [Installera Endpoint Protection i Azure Defender](/azure/security-center/security-center-install-endpoint-protection).

Med möjlighet att enkelt distribuera uppdateringar till virtuella maskiner som körs i VDE:er har vi förkortat den här guiden för att fokusera på hur du kan få uppdateringar på dina maskiner snabbt och enkelt. Du behöver inte längre regelbundet skapa och försegla gyllene bilder eftersom uppdateringarna utökas till sina beståndsdelar på värdservern och sedan hämtas direkt till den virtuella maskinerna när den är påslagen.

I den här guiden beskrivs hur du konfigurerar virtuella maskiner för optimala skydd och prestanda, inklusive hur du:

- [Konfigurera en dedikerad VDI-filresurs för säkerhetsintelligensuppdateringar](#set-up-a-dedicated-vdi-file-share)
- [Slumpmässiga schemalagda genomsökningar](#randomize-scheduled-scans)
- [Använda snabbsökningar](#use-quick-scans)
- [Förhindra meddelanden](#prevent-notifications)
- [Inaktivera genomsökningar från att inträffa efter varje uppdatering](#disable-scans-after-an-update)
- [Skanna in-datera datorer eller datorer som har varit offline ett tag](#scan-vms-that-have-been-offline)
- [Använda undantag](#exclusions)

Du kan också ladda ned informationsbladet [Microsoft Defender Antivirus](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf)på Virtual Desktop Infrastructure som tittar på den nya delade säkerhetsintelligensuppdateringsfunktionen, tillsammans med prestandatestning och vägledning om hur du kan testa antivirusprestanda på din egen VDI.

> [!IMPORTANT]
> Även om VDI kan lagras på Windows Server 2012 eller Windows Server 2016 bör virtuella maskinerna (VMs) åtminstone köra Windows 10, 1607, på grund av ökade skyddsteknik och funktioner som inte är tillgängliga i tidigare versioner av Windows.<br/>Det finns prestanda- och funktionsförbättringar för hur Microsoft Defender AV fungerar på virtuella datorer i Windows 10 Insider Preview, version 18323 (och senare). Vi identifierar dig i den här guiden om du behöver använda en Insider Preview-version. Om den inte anges är Windows 10 1607 den lägsta versionen som krävs för bästa skydd och prestanda.

## <a name="set-up-a-dedicated-vdi-file-share"></a>Konfigurera en dedikerad VDI-filresurs

I Windows 10, version 1903, introducerade vi den delade säkerhetsintelligensfunktionen, som förser packa upp paketering av hämtade säkerhetsintelligensuppdateringar på en värddator – vilket sparar tidigare processor-, disk- och minnesresurser på enskilda datorer. Den här funktionen har bakåtporterats och fungerar nu i Windows 10 version 1703 och senare. Du kan ställa in den här funktionen med en grupprincip eller PowerShell.

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a>Använd Grupprincip för att aktivera den delade säkerhetsintelligensfunktionen:

1. Öppna grupprinciphanteringskonsolen på datorn för grupprinciphantering, högerklicka på det grupprincipobjekt som du vill konfigurera och klicka sedan på **Redigera.**

2. Gå till **Datorkonfiguration i redigeraren** för **grupprinciphantering.**

3. Klicka **på Administrativa mallar**.

4. Expandera trädet till **Windows-komponenterna**  >  **Microsoft Defender Antivirus** Security  >  **Intelligence-uppdateringar.**

5. Dubbelklicka på Definiera **säkerhetsintelligens för VDI-klienter** och ange sedan alternativet **Aktiverad.** Ett fält visas automatiskt.

6. Ange `\\<sharedlocation\>\wdav-update` (om du behöver hjälp med det här värdet går [du till Ladda ned och packa upp](#download-and-unpackage-the-latest-updates)).

7. Klicka på **OK**.

8. Distribuera GPO:t till de virtuella maskinerna som du vill testa.

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a>Använda PowerShell för att aktivera den delade säkerhetsintelligensfunktionen

Använd följande cmdlet för att aktivera funktionen. Du måste sedan pusha det här eftersom du normalt skulle pusha PowerShell-baserade konfigurationsprinciper till virtuella maskiner:

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

Se [avsnittet Ladda ned och packa upp](#download-and-unpackage-the-latest-updates) för information om vad som kommer att \<shared location\> ske.

## <a name="download-and-unpackage-the-latest-updates"></a>Ladda ned och packa upp de senaste uppdateringarna

Nu kan du komma igång med att ladda ned och installera nya uppdateringar. Vi har skapat ett PowerShell-exempelskript nedan. Det här skriptet är det enklaste sättet att ladda ned nya uppdateringar och förbereda dem för dina virtuella maskiner. Du bör sedan ange att skriptet ska köras vid en viss tidpunkt på hanteringsdatorn genom att använda en schemalagd aktivitet (eller om du är van vid att använda PowerShell-skript i Azure, Intune eller SCCM kan du också använda de skripten).

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

Du kan ange att en schemalagd aktivitet ska köras en gång om dagen, så att de virtuella maskinerna får den nya uppdateringen varje gång paketet laddas ned och packas upp. Vi föreslår att du börjar med en gång om dagen, men du bör experimentera med att öka eller minska frekvensen för att förstå effekten. 

Säkerhetsintelligenspaket publiceras vanligtvis en gång var tredje till fyra:e timme. Vi avråder dig från att ställa in en frekvens som är kortare än fyra timmar eftersom det ökar nätverkskostnaderna på hanteringsdatorn utan någon förmån.

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a>Ange en schemalagd aktivitet för att köra PowerShell-skriptet

1. Öppna Start-menyn på hanteringsdatorn och skriv **Schemaläggaren.** Öppna den och välj **Skapa uppgift...** i sidopanelen.

2. Ange namnet som **"Security intelligence" för att packa upp**. Gå till **fliken Utlösare.** Välj **Nytt...** > **Varje** dag och välj **OK.**

3. Gå till **fliken** Åtgärder. Välj **Nytt...** Ange **PowerShell** i **fältet Program/skript.** Ange `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` i fältet Lägg **till** argument. Välj **OK**.

4. Du kan välja att konfigurera ytterligare inställningar om du vill.

5. Spara **den schemalagda** aktiviteten genom att välja OK.
 
Du kan starta uppdateringen manuellt genom att högerklicka på uppgiften och klicka på **Kör**.

### <a name="download-and-unpackage-manually"></a>Ladda ned och packa upp manuellt

Om du föredrar att göra allt manuellt gör du så här för att replikera skriptets beteende:

1. Skapa en ny mapp i systemroten som `wdav_update` anropas för att lagra informationsuppdateringar, till exempel skapa mappen `c:\wdav_update` .

2. Skapa en undermapp under *wdav_update* med ett GUID-namn, till exempel `{00000000-0000-0000-0000-000000000000}`

Här är ett exempel: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`

   > [!NOTE]
   > I skriptet vi anger det så de sista 12 siffrorna i GUID är år, månad, dag och tid när filen laddades ned så att en ny mapp skapas varje gång. Du kan ändra detta så att filen laddas ned till samma mapp varje gång.

3. Hämta ett säkerhetsintelligenspaket [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  från mappen GUID. Filen ska heta `mpam-fe.exe` .

4. Öppna ett cmd-meddelandefönster och gå till GUID-mappen som du har skapat. Använd **extraheringskommandot /X** för att extrahera filerna, till exempel `mpam-fe.exe /X` .

   > [!NOTE]
   > Virtuella maskiner hämtar det uppdaterade paketet när en ny GUID-mapp skapas med ett extraherat uppdateringspaket eller när en befintlig mapp uppdateras med ett nytt extraherat paket.

## <a name="randomize-scheduled-scans"></a>Slumpmässiga schemalagda genomsökningar

Schemalagda skanningar körs utöver [realtidsskydd och skanning.](configure-real-time-protection-microsoft-defender-antivirus.md)

Starttiden för själva genomsökningen baseras fortfarande på principen för schemalagd sökning **(ScheduleDay,** **ScheduleTime** och **ScheduleQuickScanTime).** Slumpvisisering gör att Microsoft Defender Antivirus startar en genomsökning på varje dator inom 4 timmar från den tid som angetts för den schemalagda genomsökningen.

Se [Schemalägga genomsökningar för](scheduled-catch-up-scans-microsoft-defender-antivirus.md) andra konfigurationsalternativ som är tillgängliga för schemalagda genomsökningar.

## <a name="use-quick-scans"></a>Använda snabbsökningar

Du kan ange vilken typ av genomsökning som ska utföras vid en schemalagd genomsökning. Snabbsökningar är den rekommenderade metoden eftersom de är utformade för att leta på alla platser där skadlig programvara måste vara aktiv. Här beskrivs hur du ställer in snabba genomsökningar med grupprinciper.

1. I grupprincipredigeraren går du till Administrativa **mallar**  >  **Windows-komponenter**  >  **Microsoft Defender Antivirus**  >  **Scan.**

2. Välj **Ange vilken genomsökningstyp som ska användas för en schemalagd** sökning och redigera sedan principinställningen.

3. Ställ in principen på **Aktiverad** och välj sedan **Snabbsökning** under **Alternativ.**

4. Välj **OK**. 

5. Distribuera grupprincipobjektet som vanligt.

## <a name="prevent-notifications"></a>Förhindra meddelanden

Ibland kan antivirusmeddelanden från Microsoft Defender skickas till eller finns kvar i flera sessioner. Om du vill minimera det här problemet kan du låsa användargränssnittet i Microsoft Defender Antivirus. Här beskrivs hur du förhindrar aviseringar med grupprinciper.

1. Gå till Windows-komponenter Microsoft Defender Antivirus Client Interface i  >    >  **grupprincipredigeraren.**

2. Markera **Ignorera alla meddelanden** och redigera sedan principinställningarna. 

3. Ställ in principen **på Aktiverad** och välj sedan **OK.**

4. Distribuera grupprincipobjektet som vanligt.

Om du ignorerar meddelanden förhindrar du att meddelanden från Microsoft Defender Antivirus visas i Åtgärdscenter på Windows 10 när genomsökningar görs eller åtgärder vidtas. Men teamet för säkerhetsåtgärder ser resultatet av genomsökningen i Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

> [!TIP]
> Öppna Åtgärdscenter i Windows 10 genom att göra något av följande:
> - Välj ikonen för Åtgärdscenter till höger i aktivitetsfältet.
> - Tryck på Windows-tangenten + A.
> - På en enhet med pekskärm sveper du från skärmens högra kant.

## <a name="disable-scans-after-an-update"></a>Inaktivera genomsökningar efter en uppdatering

Om du inaktiverar en genomsökning efter en uppdatering förhindras en genomsökning efter att en uppdatering har mottagits. Du kan använda den här inställningen när du skapar basbilden om du också har gjort en snabbsökning. På så sätt kan du förhindra att den nyligen uppdaterade virtuella maskinerna utför en genomsökning igen (eftersom du redan har skannat den när du skapade basbilden).

> [!IMPORTANT]
> Genom att köra genomsökningar efter en uppdatering kan du säkerställa att dina virtuella maskiner skyddas med de senaste säkerhetsintelligensuppdateringarna. Om du inaktiverar det här alternativet minskas skyddsnivån för virtuella maskiner och bör endast användas när du skapar eller distribuerar basbilden.

1. Gå till Windows-komponenterna Microsoft  >  **Defender Antivirus**  >  **Security Intelligence-uppdateringar i grupprincipredigeraren.**

2. Välj **Aktivera genomsökning efter säkerhetsintelligensuppdatering** och redigera sedan principinställningen.

3. Ställ in principen på **Inaktiverad**.

4. Välj **OK**.

5. Distribuera grupprincipobjektet som vanligt.

Den här principen förhindrar att en genomsökning körs direkt efter en uppdatering.

## <a name="scan-vms-that-have-been-offline"></a>Skanna virtuella maskiner som har varit offline

1. Gå till Windows-komponenterna Microsoft Defender Antivirus Scan i  >  **grupprincipredigeraren.**  >  

2. Välj **Aktivera snabbsökning och redigera** sedan principinställningen.

3. Ställ in principen på **Aktiverad.**

4. Välj **OK**.

5. Distribuera grupprincipobjektet som vanligt.

Den här principen tvingar fram en genomsökning om den virtuella maskinerna har missat två eller fler schemalagda genomsökningar i följd.

## <a name="enable-headless-ui-mode"></a>Aktivera huvudlöst gränssnittsläge

1. Gå till Windows-komponenter Microsoft Defender Antivirus Client Interface i  >    >  **grupprincipredigeraren.**

2. Välj **Aktivera huvudlöst gränssnittsläge** och redigera principen.

3. Ställ in principen på **Aktiverad.**

4. Klicka på **OK**.

5. Distribuera grupprincipobjektet som vanligt.
 
Den här principen döljer hela Microsoft Defender Antivirus-användargränssnittet från slutanvändarna i organisationen.

## <a name="exclusions"></a>Undantag

Undantag kan läggas till, tas bort eller anpassas så att de passar dina behov.

Mer information finns i Konfigurera [undantag för Microsoft Defender Antivirus på Windows Server.](configure-exclusions-microsoft-defender-antivirus.md)

## <a name="additional-resources"></a>Ytterligare resurser

- [Tech Community-blogg: Konfigurera Microsoft Defender Antivirus för icke-beständiga VDI-datorer](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [TechNet-forum på Fjärrskrivbordstjänster och VDI](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [PowerShell-skript för SignatureDownloadCustomTask](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)