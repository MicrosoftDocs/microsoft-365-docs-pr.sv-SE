---
title: Växla till Microsoft Defender för slutpunkt – konfigurera
description: Det här är fas 2, installationsprogrammet, för att växla till Microsoft Defender för Endpoint.
keywords: migrering, Microsoft Defender för Slutpunkt, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 21a3ee2f40667e31c6eb9b1cf80a30997f167b82
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245750"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>Växla till Microsoft Defender för slutpunkt – fas 2: Installation

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fas 1: Förbereda](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Fas 1: Förbereda](switch-to-microsoft-defender-prepare.md) |![Fas 2: Konfigurera](images/phase-diagrams/setup.png)<br/>Fas 2: Konfigurera |[![Fas 3: Onboard3](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[Fas 3: Introduktion](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
||*Du är här!* | |

**Välkommen till konfigurationsfasen av [bytet till Microsoft Defender för Slutpunkt.](switch-to-microsoft-defender-migration.md#the-migration-process)** Den här fasen omfattar följande steg:
1. [Aktivera Microsoft Defender Antivirus och bekräfta att det är i passivt läge](#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode).
2. [Hämta uppdateringar för Microsoft Defender Antivirus](#get-updates-for-microsoft-defender-antivirus).
3. [Lägg till Microsoft Defender för Slutpunkt i undantagslistan för din befintliga slutpunktslösning](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution).
4. [Lägg till din befintliga lösning i undantagslistan för Microsoft Defender Antivirus](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus).
5. [Lägg till din befintliga lösning i undantagslistan för Microsoft Defender för Slutpunkt.](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-for-endpoint)
6. [Konfigurera enhetsgrupper, enhetssamlingar och organisationsenheter.](#set-up-your-device-groups-device-collections-and-organizational-units)
7. [Konfigurera program mot skadlig programvara och realtidsskydd](#configure-antimalware-policies-and-real-time-protection).

## <a name="enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode"></a>Aktivera Microsoft Defender Antivirus och bekräfta att det är i passivt läge

I vissa versioner Windows, till exempel Windows Server, kan Microsoft Defender Antivirus avinstalleras eller inaktiverats när McAfee-lösningen installerades. Det beror på Microsoft Defender Antivirus inte inaktivt eller passivt läge när du installerar en antivirusprodukt från tredje part, till exempel McAfee. (Mer information om detta finns [i Microsoft Defender Antivirus kompatibilitet](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).)

Det här steget i migreringsprocessen omfattar följande uppgifter:
- [Ange DisableAntiSpyware till False på Windows Server](#set-disableantispyware-to-false-on-windows-server)
- [Ominstallera Microsoft Defender Antivirus på Windows Server ;](#reinstall-microsoft-defender-antivirus-on-windows-server)
- [Inställning Microsoft Defender Antivirus till passivt läge på Windows Server](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)
- [Aktivera Microsoft Defender Antivirus på din Windows klientenheter](#enable-microsoft-defender-antivirus-on-your-windows-client-devices); och
- [Bekräftar att Microsoft Defender Antivirus är inställt på passivt läge](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode).  

### <a name="set-disableantispyware-to-false-on-windows-server"></a>Ställ in DisableAntiSpyware på False på Windows Server

Registernyckeln [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) användes tidigare för att inaktivera Microsoft Defender Antivirus och distribuera ett annat antivirusprogram, till exempel McAfee. I allmänhet bör du inte ha den här registernyckeln på dina Windows och slutpunkter. Men om du har `DisableAntiSpyware` konfigurerat så här anger du värdet falskt:

1. Öppna Registereditorn på Windows Server-enhet.

1. Gå till `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` .

1. Leta där efter en DWORD-post med namnet **DisableAntiSpyware.**
   - Om du inte ser den posten är allt klart.
   - Om du ser **DisableAntiSpyware går** du vidare till steg 4.

1. Högerklicka på DisableAntiSpyware DWORD och välj sedan **Ändra**.

1. Ställ in värdet på `0` . (Detta anger värdet för registernyckeln till *falskt*.)

> [!TIP]
> Mer information om den här registernyckeln finns [i DisableAntiSpyware.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Installera Microsoft Defender Antivirus på Windows Server

> [!NOTE]
> Följande procedur gäller endast för slutpunkter eller enheter som kör följande versioner av Windows:
> - Windows Server 2019
> - Windows Server, version 1803 (endast kärnläge)
> - Windows Server 2016

1. Som lokal administratör på slutpunkten eller enheten öppnar du Windows PowerShell.
2. Kör följande PowerShell-cmdlets: <br/>   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/><br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>
 
    > [!NOTE]
    > När du använder DISM-kommandot i en aktivitetssekvens som kör PS krävs cmd.exe sökväg.
    > Exempel:<br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/><br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. Kontrollera att Microsoft Defender Antivirus är igång med följande PowerShell-cmdlet: <br/>
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>Använder du Windows Server 2016?

Om du använder en Windows Server 2016 och har problem med att Microsoft Defender Antivirus kan du använda följande PowerShell-cmdlet:

`mpcmdrun -wdenable`

> [!TIP]
> Behöver du fortfarande hjälp? Se [Microsoft Defender Antivirus på Windows Server](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-on-windows-server-2016).

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Ställ Microsoft Defender Antivirus till passivt läge på Windows Server

Eftersom din organisation fortfarande använder din befintliga lösning för slutpunktsskydd måste du Microsoft Defender Antivirus passivt läge. På så sätt kan din befintliga lösning och Microsoft Defender Antivirus köras sida vid sida tills du är klar med introduktionen till Microsoft Defender för Endpoint.

1. Öppna Registereditorn och gå till <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Redigera (eller skapa) en DWORD-post som heter **ForceDefenderPassiveMode** och ange följande inställningar:
   - Ställ in DWORD-värdet på **1.**
   - Under **Bas** väljer du **Hexadecimal**.

> [!NOTE]
> Du kan använda andra metoder för att ange registernyckeln, till exempel följande:
>- [Grupprincipinställning](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Verktyget Lokalt grupprincipobjekt](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Ett paket i Konfigurationshanteraren](/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="enable-microsoft-defender-antivirus-on-your-windows-client-devices"></a>Aktivera Microsoft Defender Antivirus på dina Windows klientenheter

Eftersom din organisation har använt en antiviruslösning som inte är en Microsoft Microsoft Defender Antivirus är troligen inaktiverad på din organisations Windows enheter. Det här steget i migreringsprocessen omfattar att aktivera Microsoft Defender Antivirus. 

Om du Microsoft Defender Antivirus en app rekommenderar vi att du använder Intune. Du kan däremot välja någon av de metoder som listas i följande tabell:

|Metod  |Vad kan jag göra?  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**OBS!** Intune är nu Microsoft Endpoint Manager. |1. Gå till [Microsoft Endpoint Manager och](https://go.microsoft.com/fwlink/?linkid=2109431) logga in.<br/><br/>2. Välj  >  **Konfigurationsprofiler för** enheter och välj sedan den profiltyp du vill konfigurera. Om du ännu inte  har skapat en profiltyp för enhetsbegränsningar, eller om du vill skapa en ny, går du till Konfigurera inställningar för enhetsbegränsning [i Microsoft Intune](/intune/device-restrictions-configure).<br/><br/>3. Välj **Egenskaper** och välj sedan **Konfigurationsinställningar: Redigera**.<br/><br/>4. Utöka **Microsoft Defender Antivirus**. <br/><br/>5. Aktivera **moln levererat skydd.**<br/><br/>6. I **listrutan Fråga användarna innan exempel skickas** väljer du Skicka alla exempel **automatiskt.**<br/><br/>7. I **listrutan Identifiera potentiellt oönskade program** väljer du **Aktivera** eller **Granska**.<br/><br/>8. Välj **Granska + spara** och välj sedan **Spara.**<br/>**TIPS:** Mer information om Intune-enhetsprofiler, bland annat hur du skapar och konfigurerar deras inställningar finns i Vad är [Microsoft Intune enhetsprofiler?](/intune/device-profiles).|
|Kontrollpanelen i Windows     |Följ instruktionerna här: [Aktivera Microsoft Defender Antivirus](/mem/intune/user-help/turn-on-defender-windows). <br/>**OBS!** I vissa versioner *Windows Defender Antivirus* inte *Microsoft Defender Antivirus* visas i Windows.        |
|[Avancerad grupprinciphantering](/microsoft-desktop-optimization-pack/agpm/) <br/>eller<br/>[Konsolen grupprinciphantering](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  |1. Gå till `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` . <br/><br/>2. Leta efter en princip med **namnet Inaktivera Microsoft Defender Antivirus**.<br/><br/>3. Välj **Redigera principinställning** och kontrollera att principen är inaktiverad. Det här gör att Microsoft Defender Antivirus. <br/><br/>**OBS!** I vissa versioner *Windows Defender Antivirus* inte *Microsoft Defender Antivirus* visas i Windows. |


### <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Kontrollera att Microsoft Defender Antivirus är i passiv form

Microsoft Defender Antivirus kan köras tillsammans med din befintliga lösning för slutpunktsskydd om du ställer Microsoft Defender Antivirus på passivt läge. Du kan använda kommandotolken eller PowerShell för att utföra den här uppgiften enligt följande tabell:

|Metod  |Vad kan jag göra?  |
|---------|---------|
|Kommandotolken     |1. På en Windows enhet öppnar du Kommandotolken som administratör. <br/><br/>2. Skriv `sc query windefend` och tryck sedan på Retur.<br/><br/>3. Granska resultaten för att bekräfta att Microsoft Defender Antivirus i passiv form.         |
|PowerShell     |1. På en Windows enhet öppnar du Windows PowerShell som administratör.<br/><br/>2. Kör [cmdleten Get-MpComputerStatus.](/powershell/module/defender/Get-MpComputerStatus) <br/><br/>3. I resultatlistan letar du efter antingen **AMRunningMode: Passivt läge** eller **AMRunningMode: SxS-passivt läge.**          |

> [!NOTE]
> I vissa *versioner Windows Defender Antivirus* inte *Microsoft Defender Antivirus* visas i Windows.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Hämta uppdateringar för Microsoft Defender Antivirus

Att hålla Microsoft Defender Antivirus uppdaterad är viktigt för att säkerställa att dina enheter har den senaste tekniken och funktionerna som behövs för att skydda mot nya tekniker för skadlig programvara och attack, även om Microsoft Defender Antivirus körs i [passiv form.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

Det finns två typer av uppdateringar som är relaterade till Microsoft Defender Antivirus uppdateringar:
- Säkerhetsintelligensuppdateringar
- Produktuppdateringar

Följ linjerna i Hantera uppdateringar i Microsoft Defender Antivirus [och tillämpa baslinjer](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)för att få uppdateringarna.

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>Lägga till Microsoft Defender för slutpunkt i undantagslistan för din befintliga lösning

Det här steget i konfigurationen innebär att du lägger till Microsoft Defender för Endpoint i undantagslistan för din befintliga lösning för slutpunktsskydd och andra säkerhetsprodukter som din organisation använder. 

> [!TIP]
> Hjälp med att konfigurera undantag finns i lösningsleverantörens dokumentation.

Specifika undantag att konfigurera beror på vilken version av Windows dina slutpunkter eller enheter körs och visas i följande tabell:

|OS |Undantag |
|--|--|
|- Windows 10 version [1803 eller senare](/windows/release-health/status-windows-10-1803) (se Windows 10 [versionsinformation](/windows/release-health/release-information))<br/>- Windows 10, version 1703 eller 1709 med [KB4493441](https://support.microsoft.com/help/4493441) installerat <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server, version 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/><br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/><br/>  |
|- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/>- [Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/>- [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/>**Obs!** Där övervakningsvärden för tillfälliga filer 6\45 kan vara olika numrerade undermappar.<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/><br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Lägg till din befintliga lösning i undantagslistan för Microsoft Defender Antivirus

I det här steget i installationsprocessen lägger du till din befintliga lösning i Microsoft Defender Antivirus för uteslutning. 

När du lägger [till undantag Microsoft Defender Antivirus genomsökningar](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)bör du lägga till undantag för sökvägar och processer. Tänk på följande:
- Undantag från sökvägar exkluderar specifika filer och all åtkomst till dessa filer.
- Processkludering exkluderar det som händer i en process, men exkluderar inte själva processen.
- Om du visar varje körbar (.exe) som både ett sökvägs- och ett processkludering utesluts processen och det som berörs.
- Lista undantag från processen med hjälp av deras fullständiga sökväg och inte efter namn. (Metoden med endast namn är mindre säker.)

Du kan välja mellan flera metoder för att lägga till Microsoft Defender Antivirus undantag, som anges i följande tabell:


|Metod | Vad kan jag göra?|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**OBS!** Intune är nu Microsoft Endpoint Manager. |1. Gå till [Microsoft Endpoint Manager och](https://go.microsoft.com/fwlink/?linkid=2109431) logga in.<br/><br/>2. Välj  >  **Konfigurationsprofiler för** enheter och välj sedan den profil som du vill konfigurera.<br/><br/>3. Under **Hantera** väljer du **Egenskaper**.<br/> <br/>4. Välj **Konfigurationsinställningar: Redigera**.<br/><br/>5. Visa **Microsoft Defender Antivirus** och expandera **Microsoft Defender Antivirus Undantag**.<br/><br/>6. Ange de filer och mappar, tillägg och processer som ska undantas från Microsoft Defender Antivirus genomsökningar. Information finns i [Microsoft Defender Antivirus undantag](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions).<br/><br/>7. Välj **Granska + Spara** och välj sedan **Spara**.  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) |1. Med hjälp av [konfigurationshanterarens](/mem/configmgr/core/servers/manage/admin-console)konsol går du till Tillgångar och efterlevnad Endpoint Protection Principer för program mot skadlig programvara och väljer sedan den princip som du vill  >    >  ändra. <br/><br/>2. Ange undantagsinställningar för filer och mappar, tillägg och processer som ska undantas från Microsoft Defender Antivirus genomsökningar. |
|[Grupprincipobjekt](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. Öppna konsolen Grupprinciphantering på [](https://technet.microsoft.com/library/cc731212.aspx)datorn för grupprinciphantering, högerklicka på det grupprincipobjekt du vill konfigurera och klicka på **Redigera.**<br/><br/>2. I **redigeraren för grupprinciphantering går** du till **Datorkonfiguration och** klickar på Administrativa **mallar**.<br/><br/>3. Expandera trädet för **att Windows komponenter > Microsoft Defender Antivirus > Undantag**.<br/>**OBS!** I vissa versioner *Windows Defender Antivirus* inte *Microsoft Defender Antivirus* visas i Windows.<br/><br/>4. Dubbelklicka på inställningen **Undantag för sökväg** och lägg till undantagen.<br/>- Ställ in alternativet som **Aktiverat.**<br/>- Under avsnittet **Alternativ** klickar du på **Visa...**.<br/>- Ange varje mapp på en egen rad under **kolumnen Värdenamn.**<br/>– Om du anger en fil anger du en fullständigt kvalificerad sökväg till filen, inklusive enhetsbeteckningen, mappsökvägen, filnamn och filnamnstillägg. Ange **0** i **kolumnen** Värde.<br/><br/>5. Klicka på **OK.**<br/><br/>6. Dubbelklicka på inställningen **undantag för filnamnstillägg** och lägg till undantagen.<br/>- Ställ in alternativet som **Aktiverat.**<br/>- Under avsnittet **Alternativ** klickar du på **Visa...**.<br/>– Ange varje filnamnstillägg på en egen rad under **kolumnen Värdenamn.**  Ange **0** i **kolumnen** Värde.<br/><br/>7. Klicka på **OK.** |
|Lokalt grupprincipobjekt |1. Öppna redigeraren för lokala grupprinciper på slutpunkten eller enheten. <br/><br/>2. Gå till **Administrativa mallar**  >  **för**  >  **datorkonfiguration Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Undantag**.<br/><br/>**OBS!** I vissa versioner *Windows Defender Antivirus* inte *Microsoft Defender Antivirus* visas i Windows.<br/><br/>3. Ange undantag för sökväg och process. |
|Registernyckel |1. Exportera följande registernyckel: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<br/><br/>2. Importera registernyckeln. Här är två exempel:<br/>- Lokal sökväg: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Nätverksresurs: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |
|||


## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-for-endpoint"></a>Lägg till din befintliga lösning i undantagslistan för Microsoft Defender för Slutpunkt

Om du vill lägga till undantag i Microsoft Defender för Endpoint skapar du [indikatorer](/microsoft-365/security/defender-endpoint/manage-indicators#create-indicators-for-files).

1. Gå till Microsoft Defender Säkerhetscenter ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) och logga in.<br/>

1. Välj Ange regelindikatorer **Inställningar**  >    >  **navigeringsfönstret.**<br/>

1. På fliken **Filhashar** väljer du **Lägg till indikator**.<br/>

1. Ange **följande** inställningar på fliken Indikator:
   - Filhash (Behöver du hjälp? Se [Hitta en filhash med CMPivot](#find-a-file-hash-using-cmpivot) i den här artikeln.)
   - Under **Går ut på (UTC)** väljer du **Aldrig.**<br/>
   
1. På **fliken Åtgärd** anger du följande inställningar:
   - **Svarsåtgärd:** **Tillåt**
   - Titel och beskrivning<br/>
   
1. På fliken **Omfattning,** under **Enhetsgrupper,** väljer du antingen **Alla enheter i min omfattning** eller Välj från **listan**.<br/>

1. Granska **inställningarna på** fliken Sammanfattning och klicka sedan på **Spara**.

### <a name="find-a-file-hash-using-cmpivot"></a>Hitta en filhash med CMPivot

CMPivot är ett konsolverktyg för Konfigurationshanteraren. CMPivot ger åtkomst till realtidstillståndet för enheter i din miljö. En fråga körs direkt på alla anslutna enheter i målsamlingen och resultatet returneras. Mer information finns i [CMPivotöversikt](/mem/configmgr/core/servers/manage/cmpivot-overview).

Följ de här stegen om du vill använda CMPivot för att få din filhash:

1. Granska [förutsättningarna](/mem/configmgr/core/servers/manage/cmpivot#prerequisites).
2. [Starta CMPivot](/mem/configmgr/core/servers/manage/cmpivot#start-cmpivot). 
3. Anslut till Konfigurationshanteraren ( `SCCM_ServerName.DomainName.com` ).
4. Välj **fliken** Fråga.
5. Välj **Alla system** **(standard) i listan Enhetssamling.**
6. Skriv följande fråga i frågerutan:<br/>

   ```kusto
   File(c:\\windows\\notepad.exe)
   | project Hash
   ```
   
   > [!NOTE]
   > I frågan ovan ersätter *dunotepad.exe* namnet på din säkerhetsprodukt från tredje part. 

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Konfigurera enhetsgrupper, enhetssamlingar och organisationsenheter

| Samlingstyp | Vad kan jag göra? |
|--|--|
|[Enhetsgrupper](/microsoft-365/security/defender-endpoint/machine-groups) (kallades tidigare datorgrupper) gör det möjligt för säkerhetsgruppen att konfigurera säkerhetsfunktioner, till exempel automatisk undersökning och åtgärd.<br/> Enhetsgrupper är också användbara för att tilldela åtkomst till dessa enheter så att ditt säkerhetsteam kan vidta åtgärder om det behövs. <br/>Enhetsgrupper skapas i Microsoft Defender Säkerhetscenter. |1. Gå till Microsoft Defender Säkerhetscenter ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<br/><br/>2. I navigeringsfönstret till vänster väljer du **välj** Inställningar  >  **i Grupper för**  >  **enheter med behörigheter.**  <br/><br/>3. Välj **+ Lägg till enhetsgrupp**.<br/><br/>4. Ange ett namn och en beskrivning för enhetsgruppen.<br/><br/>5. Välj **ett alternativ i** listan Automatiseringsnivå. (Vi rekommenderar **Fullständigt – åtgärda hot automatiskt**.) Mer information om de olika automationsnivåerna finns [i Hur hot åtgärdas.](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<br/><br/>6. Ange villkor för en matchande regel för att avgöra vilka enheter som tillhör enhetsgruppen. Du kan till exempel välja en domän, OS-versioner eller till och med använda [enhetstaggar.](/microsoft-365/security/defender-endpoint/machine-tags)<br/><br/>7. På **fliken Användaråtkomst** anger du roller som ska ha åtkomst till de enheter som ingår i enhetsgruppen. <br/><br/>8. Välj **Klar**. |
|[Med hjälp av](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) enhetssamlingar kan ditt säkerhetsteam hantera program, distribuera efterlevnadsinställningar eller installera programvaruuppdateringar på enheterna i organisationen.<br/>Enhetssamlingar skapas med [konfigurationshanteraren.](/mem/configmgr/) |Följ stegen i [Skapa en samling.](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create) |
|[Med organisationsenheter](/azure/active-directory-domain-services/create-ou) kan du logiskt gruppera objekt som användarkonton, tjänstkonton eller datorkonton. Du kan sedan tilldela administratörer till specifika organisationsenheter och tillämpa grupprinciper för att tillämpa riktade konfigurationsinställningar.<br/> Organisationsenheter definieras i [Azure Active Directory Domain Services.](/azure/active-directory-domain-services) | Följ stegen i Skapa [en organisationsenhet i en domän som hanteras Azure Active Directory Domain Services.](/azure/active-directory-domain-services/create-ou) |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Konfigurera skydd mot skadlig programvara och realtidsskydd

Med Hjälp av Konfigurationshanteraren och din enhetssamling konfigurerar du principer för program mot skadlig programvara.
- Se [Skapa och distribuera program mot skadlig programvara för Endpoint Protection i Configuration Manager.](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- När du skapar och konfigurerar principer för program [](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) mot skadlig programvara bör du granska skyddsinställningarna i realtid och aktivera [blockering vid första synen.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

> [!TIP]
> Du kan distribuera principerna innan organisationens enheter börjar.

## <a name="next-step"></a>Nästa steg

**Grattis!** Du har slutfört konfigurationsfasen av att [byta till Microsoft Defender för slutpunkt!](switch-to-microsoft-defender-migration.md#the-migration-process)

- [Gå till fas 3: Gå in i Microsoft Defender för Slutpunkt](switch-to-microsoft-defender-onboard.md)
