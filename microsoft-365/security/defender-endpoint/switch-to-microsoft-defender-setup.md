---
title: Växla till Microsoft Defender för slutpunkt – konfigurera
description: Fas 2, installationsprocessen, när du växlar till Microsoft Defender för Endpoint.
keywords: migrering, Microsoft Defender för slutpunkt, edr, Windows Defender
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
ms.date: 05/10/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 1047d39c70e230e2765f82da4d687b36c4719b3e
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327470"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>Växla till Microsoft Defender för slutpunkt – fas 2: Installation

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fas 1: Förbereda](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Fas 1: Förbereda](switch-to-microsoft-defender-prepare.md) |![Fas 2: Konfigurera](images/phase-diagrams/setup.png)<br/>Fas 2: Konfigurera |[![Fas 3: Onboard3](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[Fas 3: Introduktion](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
||*Du är här!* | |

**Välkommen till konfigurationsfasen av [bytet till Microsoft Defender för Slutpunkt.](switch-to-microsoft-defender-migration.md#the-migration-process)** Den här fasen omfattar följande steg:
1. [Aktivera Microsoft Defender Antivirus och bekräfta att det är i passivt läge.](#enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode)
2. [Hämta uppdateringar för Microsoft Defender Antivirus.](#get-updates-for-microsoft-defender-antivirus)
3. [Lägg till Microsoft Defender för Slutpunkt i undantagslistan för din befintliga slutpunktslösning](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution).
4. [Lägg till din befintliga lösning i undantagslistan för Microsoft Defender Antivirus.](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus)
5. [Konfigurera enhetsgrupper, enhetssamlingar och organisationsenheter.](#set-up-your-device-groups-device-collections-and-organizational-units)
6. [Konfigurera program mot skadlig programvara och realtidsskydd](#configure-antimalware-policies-and-real-time-protection).

## <a name="enable-microsoft-defender-antivirus-and-confirm-its-in-passive-mode"></a>Aktivera Microsoft Defender Antivirus och bekräfta att det är i passivt läge

I vissa versioner av Windows, till exempel Windows Server, kan Microsoft Defender Antivirus ha avinstallerats eller inaktiverats när McAfee-lösningen installerades. När du vill registrera slutpunkterna i Defender för Slutpunkt, för att inte Microsoft Defender Antivirus automatiskt gå in i passiv form eller inaktiverat läge. På Windows Server kan du heller inte ha Microsoft Defender Antivirus i aktivt läge tillsammans med en lösning som inte är en Antivirus-/antimalwarelösning från Microsoft, till exempel McAfee, Symantec eller andra. Mer information om vad som händer med Defender för Endpoint och antivirusprogram finns i [Kompatibilitet för Microsoft Defender Antivirus.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

För att säkerställa att Microsoft Defender Antivirus är aktiverat och i passivt läge slutför du följande uppgifter som beskrivs i den här artikeln:
- [Ange DisableAntiSpyware till false på Windows Server](#set-disableantispyware-to-false-on-windows-server)
- [Ominstallera Microsoft Defender Antivirus på Windows Server](#reinstall-microsoft-defender-antivirus-on-windows-server);
- [Ställa in Microsoft Defender Antivirus på passiv form på Windows Server](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)
- [Aktivera Microsoft Defender Antivirus på dina Windows-klientenheter](#enable-microsoft-defender-antivirus-on-your-windows-client-devices). och
- [Bekräfta att Microsoft Defender Antivirus är inställt på passivt läge](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode).  

### <a name="set-disableantispyware-to-false-on-windows-server"></a>Ställ in DisableAntiSpyware på False på Windows Server

Registernyckeln [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) användes tidigare för att inaktivera Microsoft Defender Antivirus och distribuera ett annat antivirusprogram, till exempel McAfee. I allmänhet bör du inte ha den här registernyckeln på dina Windows-enheter och slutpunkter. Men om du har `DisableAntiSpyware` konfigurerat så här anger du värdet falskt:

1. Öppna Registereditorn på Windows Server-enheten.

2. Gå till `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` .

3. Leta där efter en DWORD-post med namnet **DisableAntiSpyware.**
   - Om du inte ser den posten är allt klart.
   - Om du ser **DisableAntiSpyware går** du vidare till steg 4.

4. Högerklicka på DisableAntiSpyware DWORD och välj sedan **Ändra**.

5. Ställ in värdet på `0` . (Den här åtgärden anger värdet för registernyckeln till *falskt*.)

> [!TIP]
> Mer information om den här registernyckeln finns [i DisableAntiSpyware.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Installera om Microsoft Defender Antivirus på Windows Server

> [!NOTE]
> Följande procedur gäller endast för slutpunkter eller enheter som kör följande versioner av Windows:
> - Windows Server 2019
> - Windows Server, version 1803 (endast kärnläge)
> - Windows Server 2016 (se viktig information i [Använder du Windows Server 2016?](#are-you-using-windows-server-2016))

1. Öppna Windows PowerShell som lokal administratör på slutpunkten eller enheten.

2. Kör följande PowerShell-cmdlets: <br/>   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <p>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>
 
    > [!NOTE]
    > När du använder DISM-kommandot i en aktivitetssekvens som kör PS krävs cmd.exe sökväg.
    > Exempel:<br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<p>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. Kontrollera att Microsoft Defender Antivirus körs med hjälp av följande PowerShell-cmdlet: <br/>
   `Get-Service -Name windefend`

#### <a name="are-you-using-windows-server-2016"></a>Använder du Windows Server 2016?

Om du har slutpunkter som kör Windows Server 2016 kan du inte köra Microsoft Defender Antivirus tillsammans med en lösning som inte är en Microsoft antivirus/antimalware-lösning. Microsoft Defender Antivirus kan inte köras i passiv form på Windows Server 2016. I så fall måste du avinstallera lösningen som inte är en Microsoft-antivirus-/antimalware-lösning och installera/aktivera Microsoft Defender Antivirus i stället. Mer information finns i [Kompatibilitet för antiviruslösningar med Defender för slutpunkt.](microsoft-defender-antivirus-compatibility.md)

Om du använder Windows Server 2016 och har problem med att aktivera Microsoft Defender Antivirus kan du använda följande PowerShell-cmdlet:

`mpcmdrun -wdenable`

> [!TIP]
> Behöver du fortfarande hjälp? Se [Microsoft Defender Antivirus på Windows Server](microsoft-defender-antivirus-on-windows-server.md).

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Ställ in Microsoft Defender Antivirus på passivt läge på Windows Server

> [!IMPORTANT]
> Du kan ställa in Microsoft Defender Antivirus på passiv form på Windows Server, version 1803 eller senare eller Windows Server 2019. Men passivt läge stöds inte i Windows Server 2016. Mer information finns i [Kompatibilitet för antiviruslösningar med Microsoft Defender för Slutpunkt.](defender-compatibility.md)

Eftersom din organisation fortfarande använder din befintliga lösning för slutpunktsskydd måste du ställa in Microsoft Defender Antivirus på passivt läge. På så sätt kan din befintliga lösning och Microsoft Defender Antivirus köras sida vid sida tills du är klar med introduktionen till Microsoft Defender för Endpoint.

1. Öppna Registereditorn och gå till <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Redigera (eller skapa) en DWORD-post **som heter ForcePassiveMode** och ange följande inställningar:
   - Ställ in DWORD-värdet på **1.**
   - Under **Bas** väljer du **Hexadecimal**.

> [!NOTE]
> Du kan använda andra metoder för att ange registernyckeln, till exempel följande:
>- [Grupprincipinställning](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn581922(v=ws.11))
>- [Verktyget Lokalt grupprincipobjekt](/windows/security/threat-protection/security-compliance-toolkit-10#what-is-the-local-group-policy-object-lgpo-tool)
>- [Ett paket i Konfigurationshanteraren](/mem/configmgr/apps/deploy-use/packages-and-programs)

### <a name="enable-microsoft-defender-antivirus-on-your-windows-client-devices"></a>Aktivera Microsoft Defender Antivirus på dina Windows-klientenheter

Eftersom din organisation har använt en antiviruslösning som inte är en Microsoft Defender Antivirus är troligen inaktiverad på din organisations Windows-enheter. Det här steget i migreringsprocessen omfattar att aktivera Microsoft Defender Antivirus. 

Om du vill aktivera Microsoft Defender Antivirus rekommenderar vi att du använder Intune. Du kan däremot välja någon av de metoder som listas i följande tabell:

|Metod  |Vad kan jag göra?  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**Obs!** Intune är nu Microsoft Endpoint Manager. | 1. Gå till [administrationscentret för Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) och logga in.<p> 2. Välj  >  **Konfigurationsprofiler för** enheter och välj sedan den profiltyp du vill konfigurera. Om du ännu inte  har skapat en profiltyp för enhetsbegränsningar, eller om du vill skapa en ny, går du till Konfigurera inställningar för enhetsbegränsning [i Microsoft Intune.](/intune/device-restrictions-configure)<p> 3. Välj **Egenskaper** och välj sedan **Konfigurationsinställningar: Redigera**.<p> 4. Expandera **Microsoft Defender Antivirus**. <p> 5. Aktivera **moln levererat skydd.**<p> 6. I **listrutan Fråga användarna innan exempel skickas** väljer du Skicka alla exempel **automatiskt.**<p> 7. I **listrutan Identifiera potentiellt oönskade program** väljer du **Aktivera** eller **Granska**.<p> 8. Välj **Granska + spara** och välj sedan **Spara.**<p>**TIPS:** Mer information om Intune-enhetsprofiler, bland annat hur du skapar och konfigurerar deras inställningar finns i Vad är enhetsprofiler i [Microsoft Intune?](/intune/device-profiles).|
|Kontrollpanelen i Windows     |Följ vägledning här: [Aktivera Microsoft Defender Antivirus.](/mem/intune/user-help/turn-on-defender-windows) <p>**Obs!** I vissa versioner av Windows kan du se *Windows Defender* Antivirus i stället för Microsoft Defender *Antivirus.*        |
|[Avancerad grupprinciphantering](/microsoft-desktop-optimization-pack/agpm/) <br/>eller<br/>[Konsolen grupprinciphantering](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  | 1. Gå till Administrativa **mallar för**  >  **datorkonfiguration**  >  **Windows-komponenter**  >  **Microsoft Defender Antivirus.** <p> 2. Leta efter en princip som **heter Inaktivera Microsoft Defender Antivirus.**<p> 3. Välj **Redigera principinställning** och kontrollera att principen är inaktiverad. Den här åtgärden aktiverar Microsoft Defender Antivirus. <p>**Obs!** I vissa versioner av Windows kan du se *Windows Defender* Antivirus i stället för Microsoft Defender *Antivirus.* |


### <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Bekräfta att Microsoft Defender Antivirus är i passiv form

Microsoft Defender Antivirus kan köras tillsammans med din befintliga lösning för slutpunktsskydd om du ställer in Microsoft Defender Antivirus på passivt läge. Du kan använda kommandotolken eller PowerShell för att utföra den här uppgiften enligt följande tabell:

|Metod  |Vad kan jag göra?  |
|---------|---------|
|Kommandotolken     | 1. Öppna Kommandotolken som administratör på en Windows-enhet. <p> 2. Skriv `sc query windefend` och tryck sedan på Retur.<p> 3. Granska resultaten för att bekräfta att Microsoft Defender Antivirus körs i passiv form.         |
|PowerShell     | 1. Öppna Windows PowerShell som administratör på en Windows-enhet.<p> 2. Kör [cmdleten Get-MpComputerStatus.](/powershell/module/defender/Get-MpComputerStatus) <p> 3. I resultatlistan letar du efter antingen **AMRunningMode: Passivt läge** eller **AMRunningMode: SxS-passivt läge.**          |

> [!NOTE]
> Du kanske ser *Windows Defender Antivirus i* stället för Microsoft Defender *Antivirus* i vissa versioner av Windows.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Hämta uppdateringar för Microsoft Defender Antivirus

Att hålla Microsoft Defender Antivirus uppdaterat är viktigt för att säkerställa att dina enheter har den senaste tekniken och funktionerna som behövs för att skydda mot nya tekniker för skadlig programvara och attack, även om Microsoft Defender Antivirus körs i [passivt läge.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)

Det finns två typer av uppdateringar som är relaterade till att hålla Microsoft Defender Antivirus uppdaterat:
- Säkerhetsintelligensuppdateringar
- Produktuppdateringar

Följ linjerna i Hantera antivirusuppdateringar för Microsoft Defender och tillämpa baslinjer om du vill [ha dina uppdateringar.](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>Lägga till Microsoft Defender för slutpunkt i undantagslistan för din befintliga lösning

Det här steget i konfigurationen innebär att du lägger till Microsoft Defender för Endpoint i undantagslistan för din befintliga lösning för slutpunktsskydd och andra säkerhetsprodukter som din organisation använder. 

> [!TIP]
> Hjälp med att konfigurera undantag finns i lösningsleverantörens dokumentation.

Specifika undantag att konfigurera beror på vilken version av Windows dina slutpunkter eller enheter körs och listas i följande tabell:

|OS |Undantag |
|--|--|
|– Windows 10, [version 1803](/windows/release-health/status-windows-10-1803) eller senare (se versionsinformation [för Windows 10)](/windows/release-health/release-information)<br/>- Windows 10, version 1703 eller 1709 med [KB4493441](https://support.microsoft.com/help/4493441) installerat <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server, version 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<p>  |
|- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <br/>- [Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<br/>- [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<br/>**Obs!** Där övervakningsvärden för tillfälliga filer 6\45 kan vara olika numrerade undermappar. <br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Lägg till din befintliga lösning i undantagslistan för Microsoft Defender Antivirus

I det här steget i installationen lägger du till din befintliga lösning i undantagslistan för Microsoft Defender Antivirus. 

När du lägger [till undantag i Genomsökningar för Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)bör du lägga till undantag för sökvägar och processer. Tänk på följande:
- Undantag från sökvägar exkluderar specifika filer och all åtkomst till dessa filer.
- Processkludering exkluderar det som händer i en process, men exkluderar inte själva processen.
- Om du visar varje körbar (.exe) som både ett sökvägs- och ett processkludering utesluts processen och det som berörs.
- Lista undantag från processen med hjälp av deras fullständiga sökväg och inte efter namn. (Metoden med endast namn är mindre säker.)

Du kan välja mellan flera olika metoder för att lägga till dina undantag i Microsoft Defender Antivirus, som visas i följande tabell:

|Metod | Vad kan jag göra?|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**Obs!** Intune är nu Microsoft Endpoint Manager. | 1. Gå till [administrationscentret för Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) och logga in.<p> 2. Välj  >  **Konfigurationsprofiler för** enheter och välj sedan den profil som du vill konfigurera.<p> 3. Under **Hantera** väljer du **Egenskaper**.<p> 4. Välj **Konfigurationsinställningar: Redigera**.<p> 5. Expandera **Microsoft Defender Antivirus** och expandera sedan undantag för Microsoft Defender **Antivirus**.<p> 6. Ange de filer och mappar, tillägg och processer som ska undantas från Genomsökningar av Microsoft Defender Antivirus. Mer information finns i [undantag för Microsoft Defender Antivirus.](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions)<p> 7. Välj **Granska + Spara** och välj sedan **Spara**.  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) | 1. Med hjälp av [konfigurationshanterarens](/mem/configmgr/core/servers/manage/admin-console)konsol går du till Principer för skydd mot skadlig programvara för tillgångar och efterlevnadsslutpunkter och väljer sedan den   >    >  princip som du vill ändra. <p> 2. Ange undantagsinställningar för filer och mappar, tillägg och processer som ska undantas från Genomsökningar för Microsoft Defender Antivirus. |
|[Grupprincipobjekt](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. Öppna konsolen Grupprinciphantering på [](https://technet.microsoft.com/library/cc731212.aspx)datorn för grupprinciphantering, högerklicka på det grupprincipobjekt som du vill konfigurera och välj sedan **Redigera.**<p> 2. I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.<p> 3. Visa trädet till **Windows-komponenter > Microsoft Defender Antivirus > Undantag**.<br/>**Obs!** I vissa versioner av Windows kan du se *Windows Defender* Antivirus i stället för Microsoft Defender *Antivirus.*<p> 4. Dubbelklicka på inställningen **Undantag för sökväg** och lägg till undantagen.<br/>- Ställ in alternativet som **Aktiverat.**<br/>- Under **avsnittet Alternativ** väljer du **Visa...**.<br/>- Ange varje mapp på en egen rad under **kolumnen Värdenamn.**<br/>– Om du anger en fil anger du en fullständigt kvalificerad sökväg till filen, inklusive enhetsbeteckningen, mappsökvägen, filnamn och filnamnstillägg. Ange **0** i **kolumnen** Värde.<p> 5. Välj **OK.**<p> 6. Dubbelklicka på inställningen **undantag för filnamnstillägg** och lägg till undantagen.<br/>- Ställ in alternativet som **Aktiverat.**<br/>- Under **avsnittet Alternativ** väljer du **Visa...**.<br/>– Ange varje filnamnstillägg på en egen rad under **kolumnen Värdenamn.**  Ange **0** i **kolumnen** Värde.<p> 7. Välj **OK.** |
|Lokalt grupprincipobjekt |1. Öppna redigeraren för lokala grupprinciper på slutpunkten eller enheten. <p>2. Gå till Administrativa **mallar**  >  **för datorkonfiguration**  >  **Windows-komponenter** Microsoft Defender  >    >  **Antivirus-undantag**.<p>**Obs!** I vissa versioner av Windows kan du se *Windows Defender* Antivirus i stället för Microsoft Defender *Antivirus.*<p>3. Ange undantag för sökväg och process. |
|Registernyckel |1. Exportera följande registernyckel: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<p>2. Importera registernyckeln. Här är två exempel:<br/>- Lokal sökväg: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Nätverksresurs: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Konfigurera enhetsgrupper, enhetssamlingar och organisationsenheter

| Samlingstyp | Vad kan jag göra? |
|--|--|
|[Enhetsgrupper](/microsoft-365/security/defender-endpoint/machine-groups) (kallades tidigare datorgrupper) gör det möjligt för säkerhetsgruppen att konfigurera säkerhetsfunktioner, till exempel automatisk undersökning och åtgärd.<br/> Enhetsgrupper är också användbara för att tilldela åtkomst till dessa enheter så att ditt säkerhetsteam kan vidta åtgärder om det behövs. <br/>Enhetsgrupper skapas i Microsoft Defender Säkerhetscenter. |1. Gå till Microsoft Defender Säkerhetscenter ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<p>2. I navigeringsfönstret till vänster väljer du Inställningar **Behörigheter**  >    >  **Enhetsgrupper**.  <p>3. Välj **+ Lägg till enhetsgrupp**.<p>4. Ange ett namn och en beskrivning för enhetsgruppen.<p>5. Välj **ett alternativ i** listan Automatiseringsnivå. (Vi rekommenderar **Fullständigt – åtgärda hot automatiskt**.) Mer information om de olika automationsnivåerna finns [i Hur hot åtgärdas.](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<p>6. Ange villkor för en matchande regel för att avgöra vilka enheter som tillhör enhetsgruppen. Du kan till exempel välja en domän, OS-versioner eller till och med använda [enhetstaggar.](/microsoft-365/security/defender-endpoint/machine-tags)<p>7. På **fliken Användaråtkomst** anger du roller som ska ha åtkomst till de enheter som ingår i enhetsgruppen. <p>8. Välj **Klar**. |
|[Med hjälp av](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) enhetssamlingar kan ditt säkerhetsteam hantera program, distribuera efterlevnadsinställningar eller installera programvaruuppdateringar på enheterna i organisationen.<br/>Enhetssamlingar skapas med [konfigurationshanteraren.](/mem/configmgr/) |Följ stegen i [Skapa en samling.](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create) |
|[Med organisationsenheter](/azure/active-directory-domain-services/create-ou) kan du logiskt gruppera objekt som användarkonton, tjänstkonton eller datorkonton. Du kan sedan tilldela administratörer till specifika organisationsenheter och tillämpa grupprinciper för att tillämpa riktade konfigurationsinställningar.<br/> Organisationsenheter definieras i [Azure Active Directory Domain Services.](/azure/active-directory-domain-services) | Följ stegen i Skapa [en organisationsenhet i en hanterad azure Active Directory Domain Services-domän.](/azure/active-directory-domain-services/create-ou) |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Konfigurera skydd mot skadlig programvara och realtidsskydd

Med Hjälp av Konfigurationshanteraren och din enhetssamling konfigurerar du principer för program mot skadlig programvara.
- Se [Skapa och distribuera program mot skadlig programvara för Endpoint Protection i Konfigurationshanteraren.](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- När du skapar och konfigurerar principer för program [](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) mot skadlig programvara bör du granska skyddsinställningarna i realtid och aktivera [blockering vid första synen.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)

> [!TIP]
> Du kan distribuera principerna innan organisationens enheter börjar.

## <a name="next-step"></a>Nästa steg

**Grattis!** Du har slutfört konfigurationsfasen av att [byta till Microsoft Defender för slutpunkt!](switch-to-microsoft-defender-migration.md#the-migration-process)

- [Gå till fas 3: Gå in i Microsoft Defender för Slutpunkt](switch-to-microsoft-defender-onboard.md)
