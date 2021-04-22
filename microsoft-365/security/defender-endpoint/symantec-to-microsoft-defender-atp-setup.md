---
title: Symantec för Microsoft Defender för Endpoint – fas 2, inställning
description: Det här är fas 2, konfiguration, av migrering från Symantec till Microsoft Defender för Slutpunkt
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: 755eb54f848e0cc5da3ca1b7b613a951c77d0b4c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935239"
---
# <a name="migrate-from-symantec---phase-2-set-up-microsoft-defender-for-endpoint"></a>Migrera från Symantec – fas 2: Konfigurera Microsoft Defender för Endpoint

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fas 1: Förbereda](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[Fas 1: Förbereda](symantec-to-microsoft-defender-atp-prepare.md) |![Fas 2: Konfigurera](images/phase-diagrams/setup.png)<br/>Fas 2: Konfigurera |[![Fas 3: Introduktion](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[Fas 3: Introduktion](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
||*Du är här!* | |


**Välkommen till konfigurationsfasen av [migreringen från Symantec till Microsoft Defender för Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)**. Den här fasen omfattar följande steg:
1. [Aktivera eller installera om Microsoft Defender Antivirus (för vissa versioner av Windows).](#enable-or-reinstall-microsoft-defender-antivirus-for-certain-versions-of-windows)
2. [Aktivera Microsoft Defender Antivirus.](#enable-microsoft-defender-antivirus)
3. [Hämta uppdateringar för Microsoft Defender Antivirus.](#get-updates-for-microsoft-defender-antivirus)
4. [Lägg till Microsoft Defender för Endpoint i undantagslistan för Symantec.](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec)
5. [Lägg till Symantec i undantagslistan för Microsoft Defender Antivirus.](#add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus)
6. [Lägg till Symantec i undantagslistan för Microsoft Defender för Endpoint](#add-symantec-to-the-exclusion-list-for-microsoft-defender-for-endpoint).
7. [Konfigurera enhetsgrupper, enhetssamlingar och organisationsenheter.](#set-up-your-device-groups-device-collections-and-organizational-units)
8. [Konfigurera program mot skadlig programvara och realtidsskydd](#configure-antimalware-policies-and-real-time-protection).

## <a name="enable-or-reinstall-microsoft-defender-antivirus-for-certain-versions-of-windows"></a>Aktivera eller installera om Microsoft Defender Antivirus (för vissa versioner av Windows)

> [!TIP]
> Om du kör Windows 10 behöver du inte utföra den här uppgiften. Gå vidare **[till Aktivera Microsoft Defender Antivirus.](#enable-microsoft-defender-antivirus)**

I vissa versioner av Windows kan Microsoft Defender Antivirus ha avinstallerats eller inaktiverats. Det beror på att Microsoft Defender Antivirus inte förs in i passiv form eller inaktiverat läge när du installerar ett antivirusprogram från en tredje part, till exempel Symantec. Mer information finns i Kompatibilitet [för Microsoft Defender Antivirus.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility) 

Nu när du flyttar från Symantec till Microsoft Defender för Endpoint måste du aktivera eller installera om Microsoft Defender Antivirus och ställa in det på passivt läge. 

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Installera om Microsoft Defender Antivirus på Windows Server

> [!NOTE]
> Följande procedur gäller endast för slutpunkter eller enheter som kör följande versioner av Windows:
> - Windows Server 2019
> - Windows Server, version 1803 (endast kärnläge)
> - Windows Server 2016
> 
> Microsoft Defender Antivirus är inbyggt i Windows 10, men det kan vara inaktiverat. I så fall fortsätter du till [Aktivera Microsoft Defender Antivirus.](#enable-microsoft-defender-antivirus)

1. Öppna Windows PowerShell som lokal administratör på slutpunkten eller enheten.
2. Kör följande PowerShell-cmdlets: `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <br/>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`

   > [!NOTE]
   > När du använder DISM-kommandot i en aktivitetssekvens som kör PS krävs cmd.exe sökväg.
   > Exempel:<br/>
   > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<br/>
   > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>
3. Kontrollera att Microsoft Defender Antivirus körs med hjälp av följande PowerShell-cmdlet: <br/>
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>Använder du Windows Server 2016?

Om du använder Windows Server 2016 och har problem med att aktivera Microsoft Defender Antivirus kan du använda följande PowerShell-cmdlet:

`mpcmdrun -wdenable`

> [!TIP]
> Behöver du fortfarande hjälp? Se [Microsoft Defender Antivirus i Windows Server 2016 och 2019.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-on-windows-server-2016)

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Ställ in Microsoft Defender Antivirus på passivt läge på Windows Server

Eftersom din organisation fortfarande använder Symantec måste du ställa in Microsoft Defender Antivirus på passivt läge. På så sätt kan Symantec och Microsoft Defender Antivirus köras sida vid sida tills du har avslutat introduktionen till Microsoft Defender för Endpoint.

1. Öppna Registereditorn och gå till <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.
2. Redigera (eller skapa) en DWORD-post som heter **ForceDefenderPassiveMode** och ange följande inställningar:
   - Ställ in DWORD-värdet på **1.**
   - Under **Bas** väljer du **Hexadecimal**.

> [!NOTE]
> Du kan använda andra metoder för att ange registernyckeln, till exempel följande:
>- [Grupprincipinställning](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Verktyget Lokalt grupprincipobjekt](https://docs.microsoft.com/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Ett paket i Konfigurationshanteraren](https://docs.microsoft.com/mem/configmgr/apps/deploy-use/packages-and-programs)

## <a name="enable-microsoft-defender-antivirus"></a>Aktivera Microsoft Defender Antivirus

Eftersom din organisation har använt Symantec som primär antiviruslösning är troligen Microsoft Defender Antivirus inaktiverat på din organisations Windows-enheter. Det här steget i migreringsprocessen omfattar att aktivera Microsoft Defender Antivirus. 

Om du vill aktivera Microsoft Defender Antivirus rekommenderar vi att du använder Intune. Du kan däremot välja någon av de metoder som listas i följande tabell:

|Metod  |Vad kan jag göra?  |
|---------|---------|
|[Intune](https://docs.microsoft.com/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**Obs!** Intune är nu Microsoft Endpoint Manager. |1. Gå till [administrationscentret för Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) och logga in.<br/>2. Välj  >  **Konfigurationsprofiler för** enheter och välj sedan den profiltyp du vill konfigurera. Om du ännu inte  har skapat en profiltyp för enhetsbegränsningar, eller om du vill skapa en ny, går du till Konfigurera inställningar för enhetsbegränsning [i Microsoft Intune.](https://docs.microsoft.com/intune/device-restrictions-configure)<br/>3. Välj **Egenskaper** och välj sedan **Konfigurationsinställningar: Redigera**.<br/>4. Expandera **Microsoft Defender Antivirus**. <br/>5. Aktivera **moln levererat skydd.**<br/>6. I **listrutan Fråga användarna innan exempel skickas** väljer du Skicka alla exempel **automatiskt.**<br/>7. I **listrutan Identifiera potentiellt oönskade program** väljer du **Aktivera** eller **Granska**.<br/>8. Välj **Granska + spara** och välj sedan **Spara.**<br/>Mer information om Intune-enhetsprofiler, bland annat hur du skapar och konfigurerar deras inställningar finns i Vad [är Enhetsprofiler i Microsoft Intune?](https://docs.microsoft.com/intune/device-profiles).|
|Kontrollpanelen i Windows     |Följ vägledning här: [Aktivera Microsoft Defender Antivirus.](https://docs.microsoft.com/mem/intune/user-help/turn-on-defender-windows) <br/>**Obs!** I vissa versioner av Windows kan du se *Windows Defender* Antivirus i stället för Microsoft Defender *Antivirus.*        |
|[Avancerad grupprinciphantering](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) <br/>eller<br/>[Konsolen grupprinciphantering](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  |1. Gå till `Computer configuration > Administrative templates > Windows components > Microsoft Defender Antivirus` . <br/>2. Leta efter en princip som **heter Inaktivera Microsoft Defender Antivirus.**<br/>3. Välj **Redigera principinställning** och kontrollera att principen är inaktiverad. Detta aktiverar Microsoft Defender Antivirus. <br/>**Obs!** I vissa versioner av Windows kan du se *Windows Defender* Antivirus i stället för Microsoft Defender *Antivirus.* |

### <a name="verify-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Kontrollera att Microsoft Defender Antivirus är i passiv form

Microsoft Defender Antivirus kan köras tillsammans med Symantec om du ställer in Microsoft Defender Antivirus på passivt läge. Du kan använda kommandotolken eller PowerShell för att utföra den här uppgiften enligt följande tabell:

|Metod  |Vad kan jag göra?  |
|---------|---------|
|Kommandotolken     |1. Öppna Kommandotolken som administratör på en Windows-enhet. <br/>2. Skriv `sc query windefend` och tryck sedan på Retur.<br/>3. Granska resultaten för att bekräfta att Microsoft Defender Antivirus körs i passiv form.         |
|PowerShell     |1. Öppna Windows PowerShell som administratör på en Windows-enhet.<br/>2. Kör [cmdleten Get-MpComputerStatus.](https://docs.microsoft.com/powershell/module/defender/Get-MpComputerStatus) <br/>3. I resultatlistan letar du efter antingen **AMRunningMode: Passivt läge** eller **AMRunningMode: SxS-passivt läge.**|

> [!NOTE]
> Du kanske ser *Windows Defender Antivirus i* stället för Microsoft Defender *Antivirus* i vissa versioner av Windows.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Hämta uppdateringar för Microsoft Defender Antivirus

Att hålla Microsoft Defender Antivirus uppdaterat är viktigt för att säkerställa att dina enheter har den senaste tekniken och funktionerna som behövs för att skydda mot nya tekniker för skadlig programvara och attack, även om Microsoft Defender Antivirus körs i [passivt läge.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

Det finns två typer av uppdateringar som är relaterade till att hålla Microsoft Defender Antivirus uppdaterat:
- Säkerhetsintelligensuppdateringar
- Produktuppdateringar

Följ linjerna i Hantera antivirusuppdateringar för Microsoft Defender och tillämpa baslinjer om du vill [ha dina uppdateringar.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-symantec"></a>Lägga till Microsoft Defender för Slutpunkt i undantagslistan för Symantec

Det här steget i installationen omfattar att lägga till Microsoft Defender för Endpoint i undantagslistan för Symantec och andra säkerhetsprodukter som din organisation använder. Specifika undantag att konfigurera beror på vilken version av Windows dina slutpunkter eller enheter körs och visas i följande tabell:

|OS |Undantag |
|--|--|
|– Windows 10, [version 1803](https://docs.microsoft.com/windows/release-health/status-windows-10-1803) eller senare (se versionsinformation [för Windows 10)](https://docs.microsoft.com/windows/release-health/release-information)<br/>- Windows 10, version 1703 eller [1709](https://docs.microsoft.com/windows/release-health/status-windows-10-1709) med [KB4493441](https://support.microsoft.com/help/4493441) installerat <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server, version 1803](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<br/>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<br/>  |
|- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/>- [Windows 7](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/>**Obs!** Där övervakningsvärden för tillfälliga filer 6\45 kan vara olika numrerade undermappar.<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-symantec-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Lägga till Symantec i undantagslistan för Microsoft Defender Antivirus

I det här steget i installationen lägger du till Symantec och dina andra säkerhetslösningar i undantagslistan för Microsoft Defender Antivirus. 

> [!NOTE]
> Information om vilka processer och tjänster som ska uteslutas finns i Broadcoms processer och tjänster som [används av Endpoint Protection 14.](https://knowledge.broadcom.com/external/article/170706/processes-and-services-used-by-endpoint.html)

När du lägger [till undantag i Genomsökningar för Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)bör du lägga till undantag för sökvägar och processer. Tänk på följande:
- Undantag från sökvägar exkluderar specifika filer och all åtkomst till dessa filer.
- Processkludering exkluderar det som händer i en process, men exkluderar inte själva processen.
- Om du visar varje körbar (.exe) som både sökvägs- och processkludering utesluts processen och det som berörs.
- Lista undantag från processen med hjälp av deras fullständiga sökväg och inte efter namn. (Metoden med endast namn är mindre säker.)

Du kan välja mellan flera olika metoder för att lägga till dina undantag i Microsoft Defender Antivirus, som visas i följande tabell:

|Metod | Vad kan jag göra?|
|--|--|
|[Intune](https://docs.microsoft.com/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**Obs!** Intune är nu Microsoft Endpoint Manager. |1. Gå till [administrationscentret för Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) och logga in.<br/>2. Välj  >  **Konfigurationsprofiler för** enheter och välj sedan den profil som du vill konfigurera.<br/>3. Under **Hantera** väljer du **Egenskaper**. <br/>4. Välj **Konfigurationsinställningar: Redigera**.<br/>5. Expandera **Microsoft Defender Antivirus** och expandera sedan undantag för Microsoft Defender **Antivirus**.<br/>6. Ange de filer och mappar, tillägg och processer som ska undantas från Genomsökningar av Microsoft Defender Antivirus. Mer information finns i [undantag för Microsoft Defender Antivirus.](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)<br/>7. Välj **Granska + Spara** och välj sedan **Spara**.  |
|[Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/) |1. Med hjälp av [konfigurationshanterarens](https://docs.microsoft.com/mem/configmgr/core/servers/manage/admin-console)konsol går du till Principer för skydd mot skadlig programvara för tillgångar och efterlevnadsslutpunkter och väljer sedan den   >    >  princip som du vill ändra. <br/>2. Ange undantagsinställningar för filer och mappar, tillägg och processer som ska undantas från Genomsökningar för Microsoft Defender Antivirus. |
|[Grupprincipobjekt](https://docs.microsoft.com/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. Öppna konsolen Grupprinciphantering på [](https://technet.microsoft.com/library/cc731212.aspx)datorn för grupprinciphantering, högerklicka på det grupprincipobjekt du vill konfigurera och klicka på **Redigera.**<br/>2. I **redigeraren för grupprinciphantering går** du till **Datorkonfiguration och** klickar på Administrativa **mallar**.<br/>3. Visa trädet till **Windows-komponenter > Microsoft Defender Antivirus > Undantag**.<br/>**Obs!** I vissa versioner av Windows kan du se *Windows Defender* Antivirus i stället för Microsoft Defender *Antivirus.*<br/>4. Dubbelklicka på inställningen **Undantag för sökväg** och lägg till undantagen.<br/>- Ställ in alternativet som **Aktiverat.**<br/>- Under avsnittet **Alternativ** klickar du på **Visa...**.<br/>- Ange varje mapp på en egen rad under **kolumnen Värdenamn.**<br/>– Om du anger en fil anger du en fullständigt kvalificerad sökväg till filen, inklusive enhetsbeteckningen, mappsökvägen, filnamn och filnamnstillägg. Ange **0** i **kolumnen** Värde.<br/>5. Klicka på **OK.**<br/>6. Dubbelklicka på inställningen **undantag för filnamnstillägg** och lägg till undantagen.<br/>- Ställ in alternativet som **Aktiverat.**<br/>- Under avsnittet **Alternativ** klickar du på **Visa...**.<br/>– Ange varje filnamnstillägg på en egen rad under **kolumnen Värdenamn.**  Ange **0** i **kolumnen** Värde.<br/>7. Klicka på **OK.** |
|Lokalt grupprincipobjekt |1. Öppna redigeraren för lokala grupprinciper på slutpunkten eller enheten. <br/>2. Gå till Administrativa **mallar**  >  **för datorkonfiguration**  >  **Windows-komponenter** Microsoft Defender  >    >  **Antivirus-undantag**. <br/>**Obs!** I vissa versioner av Windows kan du se *Windows Defender* Antivirus i stället för Microsoft Defender *Antivirus.*<br/>3. Ange undantag för sökväg och process. |
|Registernyckel |1. Exportera följande registernyckel: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<br/>2. Importera registernyckeln. Här är två exempel:<br/>- Lokal sökväg: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Nätverksresurs: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

## <a name="add-symantec-to-the-exclusion-list-for-microsoft-defender-for-endpoint"></a>Lägga till Symantec i undantagslistan för Microsoft Defender för Endpoint

Om du vill lägga till undantag i Microsoft Defender för Endpoint skapar du [indikatorer](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators#create-indicators-for-files).

1. Gå till Microsoft Defender Säkerhetscenter ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) och logga in.
2. Välj Inställningar Regelindikatorer i  >    >  **navigeringsfönstret.**
3.  På fliken **Filhashar** väljer du **Lägg till indikator**.
4. Ange **följande** inställningar på fliken Indikator:
   - Filhash (Behöver du hjälp? Se [Hitta en filhash med CMPivot](#find-a-file-hash-using-cmpivot) i den här artikeln.)
   - Under **Går ut på (UTC)** väljer du **Aldrig.**
5. På **fliken Åtgärd** anger du följande inställningar:
   - **Svarsåtgärd:** **Tillåt**
   - Titel och beskrivning
6. På fliken **Omfattning,** under **Enhetsgrupper,** väljer du antingen **Alla enheter i min omfattning** eller Välj från **listan**.
7. Granska **inställningarna på** fliken Sammanfattning och klicka sedan på **Spara**.

### <a name="find-a-file-hash-using-cmpivot"></a>Hitta en filhash med CMPivot

CMPivot är ett konsolverktyg för Konfigurationshanteraren. CMPivot ger åtkomst till realtidstillståndet för enheter i din miljö. En fråga körs direkt på alla anslutna enheter i målsamlingen och resultatet returneras. Mer information finns i [CMPivotöversikt](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot-overview).

Följ de här stegen om du vill använda CMPivot för att få din filhash:

1. Granska [förutsättningarna](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot#prerequisites).
2. [Starta CMPivot](https://docs.microsoft.com/mem/configmgr/core/servers/manage/cmpivot#start-cmpivot). 
3. Ansluta till Konfigurationshanteraren ( `SCCM_ServerName.DomainName.com` ).
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
|[Enhetsgrupper](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) (kallades tidigare datorgrupper) gör det möjligt för säkerhetsgruppen att konfigurera säkerhetsfunktioner, till exempel automatisk undersökning och åtgärd.<br/> Enhetsgrupper är också användbara för att tilldela åtkomst till dessa enheter så att ditt säkerhetsteam kan vidta åtgärder om det behövs. <br/>Enhetsgrupper skapas i Microsoft Defender Säkerhetscenter. |1. Gå till Microsoft Defender Säkerhetscenter ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<br/>2. I navigeringsfönstret till vänster väljer du Inställningar **Behörigheter**  >    >  **Enhetsgrupper**.  <br/>3. Välj **+ Lägg till enhetsgrupp**.<br/>4. Ange ett namn och en beskrivning för enhetsgruppen.<br/>5. Välj **ett alternativ i** listan Automatiseringsnivå. (Vi rekommenderar **Fullständigt – åtgärda hot automatiskt**.) Mer information om de olika automationsnivåerna finns [i Hur hot åtgärdas.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<br/>6. Ange villkor för en matchande regel för att avgöra vilka enheter som tillhör enhetsgruppen. Du kan till exempel välja en domän, OS-versioner eller till och med använda [enhetstaggar.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags) <br/>7. På **fliken Användaråtkomst** anger du roller som ska ha åtkomst till de enheter som ingår i enhetsgruppen. <br/>8. Välj **Klar**. |
|[Med hjälp av](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/introduction-to-collections) enhetssamlingar kan ditt säkerhetsteam hantera program, distribuera efterlevnadsinställningar eller installera programvaruuppdateringar på enheterna i organisationen. <br/>Enhetssamlingar skapas med [konfigurationshanteraren.](https://docs.microsoft.com/mem/configmgr/) |Följ stegen i [Skapa en samling.](https://docs.microsoft.com/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create) |
|[Med organisationsenheter](https://docs.microsoft.com/azure/active-directory-domain-services/create-ou) kan du logiskt gruppera objekt som användarkonton, tjänstkonton eller datorkonton. Du kan sedan tilldela administratörer till specifika organisationsenheter och tillämpa grupprinciper för att tillämpa riktade konfigurationsinställningar.<br/> Organisationsenheter definieras i [Azure Active Directory Domain Services.](https://docs.microsoft.com/azure/active-directory-domain-services) | Följ stegen i Skapa [en organisationsenhet i en hanterad azure Active Directory Domain Services-domän.](https://docs.microsoft.com/azure/active-directory-domain-services/create-ou) |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Konfigurera skydd mot skadlig programvara och realtidsskydd

Med Hjälp av Konfigurationshanteraren och din enhetssamling konfigurerar du principer för program mot skadlig programvara.

- Se [Skapa och distribuera program mot skadlig programvara för Endpoint Protection i Konfigurationshanteraren.](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- När du skapar och konfigurerar principer för program [](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) mot skadlig programvara bör du granska skyddsinställningarna i realtid och aktivera [blockering vid första synen.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

> [!TIP]
> Du kan distribuera principerna innan organisationens enheter börjar.

## <a name="next-step"></a>Nästa steg

**Grattis!** Du har slutfört konfigurationsfasen av [migreringen från Symantec till Microsoft Defender för Slutpunkt](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)!
- [Gå till fas 3: Gå in i Microsoft Defender för Slutpunkt](symantec-to-microsoft-defender-atp-onboard.md)
