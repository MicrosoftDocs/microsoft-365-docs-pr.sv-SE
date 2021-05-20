---
title: Växla till Microsoft Defender för slutpunkt – konfigurera
description: Fas 2, installationsprocessen, när du växlar till Microsoft Defender för Endpoint.
keywords: migrering, Microsoft Defender för Slutpunkt, edr, Windows Defender
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
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: e8abf10bd036b5e6e76d08e86ab4963629d2f994
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537997"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-2-setup"></a>Växla till Microsoft Defender för slutpunkt – fas 2: Installation

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fas 1: Förbereda](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Fas 1: Förbereda](switch-to-microsoft-defender-prepare.md) |![Fas 2: Konfigurera](images/phase-diagrams/setup.png)<br/>Fas 2: Konfigurera |[![Fas 3: Onboard3](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[Fas 3: Introduktion](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
||*Du är här!* | |

**Välkommen till konfigurationsfasen av [bytet till Defender för Slutpunkt.](switch-to-microsoft-defender-migration.md#the-migration-process)** Den här fasen omfattar följande steg:

1. [Installera om/Microsoft Defender Antivirus dina slutpunkter](#reinstallenable-microsoft-defender-antivirus-on-your-endpoints).

2. [Konfigurera Defender för Slutpunkt](#configure-defender-for-endpoint).

3. [Lägg till Defender för slutpunkt i undantagslistan för din befintliga lösning](#add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution).

4. [Lägg till din befintliga lösning i undantagslistan för Microsoft Defender Antivirus](#add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus).

5. [Konfigurera enhetsgrupper, enhetssamlingar och organisationsenheter.](#set-up-your-device-groups-device-collections-and-organizational-units)

6. [Konfigurera program mot skadlig programvara och realtidsskydd](#configure-antimalware-policies-and-real-time-protection).


## <a name="reinstallenable-microsoft-defender-antivirus-on-your-endpoints"></a>Installera om/Microsoft Defender Antivirus på slutpunkterna

På vissa versioner av Windows har Microsoft Defender Antivirus troligen avinstallerats eller inaktiverats när lösningen som inte är en Microsoft antivirus/antimalware-lösning har installerats. Mer information finns i [Microsoft Defender Antivirus kompatibilitet](microsoft-defender-antivirus-compatibility.md).

På Windows-klienter inaktiveras Microsoft Defender Antivirus automatiskt när en antivirus-/antimalware-lösning som inte är en Microsoft-lösning har installerats till Defender för slutpunkt. När klientslutpunkterna introduceras till Defender för Slutpunkt hamnar Microsoft Defender Antivirus i passiv form tills antiviruslösningen som inte är microsoft avinstalleras. Microsoft Defender Antivirus vara installerat, men är sannolikt inaktiverat vid det här läget av migreringen. Om Microsoft Defender Antivirus inte har avinstallerats behöver du inte vidta någon åtgärd för dina Windows klienter.

När Windows ett icke-Microsoft-antivirusprogram/-Microsoft Defender Antivirus program mot skadlig programvara på Windows av manuellt (om det inte avinstalleras). Följande uppgifter säkerställer att Microsoft Defender Antivirus installeras och ställs in som passivt läge på Windows Server.

- [Ställ in DisableAntiSpyware på False på Windows Server](#set-disableantispyware-to-false-on-windows-server) (endast om det behövs)

- [Installera Microsoft Defender Antivirus på Windows Server](#reinstall-microsoft-defender-antivirus-on-windows-server) 

- [Ställ Microsoft Defender Antivirus till passivt läge på Windows Server](#set-microsoft-defender-antivirus-to-passive-mode-on-windows-server)

### <a name="set-disableantispyware-to-false-on-windows-server"></a>Ställ in DisableAntiSpyware på False på Windows Server

Registernyckeln [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) användes tidigare för att inaktivera Microsoft Defender Antivirus och distribuera ett annat antivirusprogram, till exempel McAfee, Symantec eller andra. I allmänhet bör du inte ha den här registernyckeln på dina Windows och slutpunkter. Men om du har `DisableAntiSpyware` konfigurerat så här anger du värdet falskt:

1. Öppna Registereditorn på Windows Server-enhet.

2. Gå till `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` .

3. Leta där efter en DWORD-post med namnet **DisableAntiSpyware.**
   - Om du inte ser den posten är allt klart.
   - Om du ser **DisableAntiSpyware går** du vidare till steg 4.

4. Högerklicka på DisableAntiSpyware DWORD och välj sedan **Ändra**.

5. Ställ in värdet på `0` . (Den här åtgärden anger värdet för registernyckeln till *falskt*.)

> [!TIP]
> Mer information om den här registernyckeln finns [i DisableAntiSpyware.](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)

### <a name="reinstall-microsoft-defender-antivirus-on-windows-server"></a>Installera Microsoft Defender Antivirus på Windows Server

> [!IMPORTANT]
> Följande procedur gäller endast för slutpunkter eller enheter som kör följande versioner av Windows:
> - Windows Server 2019
> - Windows Server, version 1803 (endast kärnläge)
> - Windows Server 2016 (se följande avsnitt: [Använder du Windows Server 2016?](#are-you-using-windows-server-2016))

1. Som lokal administratör på slutpunkten eller enheten öppnar du Windows PowerShell.

2. Kör följande PowerShell-cmdlets: <br/>   
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features` <p>
   `Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender` <br/>
 
    > [!NOTE]
    > När du använder DISM-kommandot i en aktivitetssekvens som kör PS krävs cmd.exe sökväg.
    > Exempel:<br/>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender-Features`<p>
    > `c:\windows\sysnative\cmd.exe /c Dism /online /Get-FeatureInfo /FeatureName:Windows-Defender`<br/>

3. Kontrollera att Microsoft Defender Antivirus är igång med följande PowerShell-cmdlet: <br/>
   `Get-Service -Name windefend`

   Leta efter statusen *Körs*.

### <a name="set-microsoft-defender-antivirus-to-passive-mode-on-windows-server"></a>Ställ Microsoft Defender Antivirus till passivt läge på Windows Server

1. Öppna Registereditorn och gå till <br/>
   `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.

2. Redigera (eller skapa) en DWORD-post **som heter ForcePassiveMode** och ange följande inställningar:
   - Ställ in DWORD-värdet på **1.**
   - Under **Bas** väljer du **Hexadecimal**.

> [!NOTE]
> Efter introduktionen till Defender för Slutpunkt kan du behöva Microsoft Defender Antivirus passivt läge på Windows Server.

### <a name="are-you-using-windows-server-2016"></a>Använder du Windows Server 2016?

Om du har slutpunkter som kör Windows Server 2016 kan du inte köra Microsoft Defender Antivirus tillsammans med en lösning som inte är en Antivirus-/antimalware-lösning från Microsoft. Microsoft Defender Antivirus kan inte köras i passiv form på Windows Server 2016. I så fall måste du avinstallera lösningen som inte är en Microsoft-antivirus-/antimalware-lösning och installera/aktivera Microsoft Defender Antivirus stället. Mer information finns i [Kompatibilitet för antiviruslösningar med Defender för slutpunkt.](microsoft-defender-antivirus-compatibility.md)

Om du använder en Windows Server 2016 och har problem med att Microsoft Defender Antivirus kan du använda följande PowerShell-cmdlet:

`mpcmdrun -wdenable`

Mer information finns i [Microsoft Defender Antivirus på Windows Server](microsoft-defender-antivirus-on-windows-server.md).

## <a name="configure-defender-for-endpoint"></a>Konfigurera Defender för slutpunkt

Det här steget i migreringsprocessen omfattar att konfigurera Microsoft Defender Antivirus för slutpunkterna. Vi rekommenderar att du använder Intune. du kan däremot välja någon av de metoder som listas i följande tabell:

|Metod  |Lämplig åtgärd  |
|---------|---------|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**OBS!** Intune är nu en del av Microsoft Endpoint Manager. | 1. Gå till [Microsoft Endpoint Manager och](https://go.microsoft.com/fwlink/?linkid=2109431) logga in.<p> 2. Välj  >  **Konfigurationsprofiler för** enheter och välj sedan den profiltyp du vill konfigurera. Om du ännu inte  har skapat en profiltyp för enhetsbegränsningar, eller om du vill skapa en ny, går du till Konfigurera inställningar för enhetsbegränsning [i Microsoft Intune](/intune/device-restrictions-configure).<p> 3. Välj **Egenskaper** och välj sedan **Konfigurationsinställningar: Redigera**.<p> 4. Utöka **Microsoft Defender Antivirus**. <p> 5. Aktivera **moln levererat skydd.**<p> 6. I **listrutan Fråga användarna innan exempel skickas** väljer du Skicka alla exempel **automatiskt.**<p> 7. I **listrutan Identifiera potentiellt oönskade program** väljer du **Aktivera** eller **Granska**.<p> 8. Välj **Granska + spara** och välj sedan **Spara.**<p>**TIPS:** Mer information om Intune-enhetsprofiler, bland annat hur du skapar och konfigurerar deras inställningar finns i Vad är [Microsoft Intune enhetsprofiler?](/intune/device-profiles).|
|Kontrollpanelen i Windows     |Följ instruktionerna här: [Aktivera Microsoft Defender Antivirus](/mem/intune/user-help/turn-on-defender-windows). <p>**OBS!** I vissa versioner *Windows Defender Antivirus* inte *Microsoft Defender Antivirus* visas i Windows.        |
|[Avancerad grupprinciphantering](/microsoft-desktop-optimization-pack/agpm/) <br/>eller<br/>[Konsolen grupprinciphantering](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus)  | 1. Gå till **Administrativa mallar för**  >  **datorkonfiguration Windows**  >  **komponenter**  >  **Microsoft Defender Antivirus**. <p> 2. Leta efter en princip med **namnet Inaktivera Microsoft Defender Antivirus**.<p> 3. Välj **Redigera principinställning** och kontrollera att principen är inaktiverad. Med den här åtgärden Microsoft Defender Antivirus. <p>**OBS!** I vissa versioner *Windows Defender Antivirus* inte *Microsoft Defender Antivirus* visas i Windows. |

## <a name="add-microsoft-defender-for-endpoint-to-the-exclusion-list-for-your-existing-solution"></a>Lägga till Microsoft Defender för slutpunkt i undantagslistan för din befintliga lösning

Det här steget i konfigurationsprocessen omfattar att lägga till Defender för Endpoint i undantagslistan för din befintliga lösning för slutpunktsskydd och andra säkerhetsprodukter som din organisation använder. 

> [!TIP]
> Hjälp med att konfigurera undantag finns i lösningsleverantörens dokumentation.

Specifika undantag att konfigurera beror på vilken version av Windows dina slutpunkter eller enheter körs och visas i följande tabell:

|OS |Undantag |
|--|--|
|Windows 10 version [1803 eller](/windows/release-health/status-windows-10-1803) senare (se Windows 10 [versionsinformation)](/windows/release-health/release-information)<p>Windows 10, version 1703 eller 1709 med [KB4493441](https://support.microsoft.com/help/4493441) installerat <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Server, version 1803](/windows-server/get-started/whats-new-in-windows-server-1803) |`C:\Program Files\Windows Defender Advanced Threat Protection\MsSense.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseCncProxy.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseSampleUploader.exe`<p>`C:\Program Files\Windows Defender Advanced Threat Protection\SenseIR.exe`<p>  |
|[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2) <p>[Windows 7](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016)<p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |`C:\Program Files\Microsoft Monitoring Agent\Agent\Health Service State\Monitoring Host Temporary Files 6\45\MsSenseS.exe`<p>**Obs!** Tillfälliga filer 6\45 som övervakas av värden kan vara olika numrerade undermappar. <p>`C:\Program Files\Microsoft Monitoring Agent\Agent\AgentControlPanel.exe`<br/>`C:\Program Files\Microsoft Monitoring Agent\Agent\HealthService.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\HSLockdown.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MOMPerfSnapshotHelper.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe`<p>`C:\Program Files\Microsoft Monitoring Agent\Agent\TestCloudConnection.exe` |

## <a name="add-your-existing-solution-to-the-exclusion-list-for-microsoft-defender-antivirus"></a>Lägg till din befintliga lösning i undantagslistan för Microsoft Defender Antivirus

I det här steget i installationsprocessen lägger du till din befintliga lösning i Microsoft Defender Antivirus för uteslutning. Du kan välja mellan flera metoder för att lägga till Microsoft Defender Antivirus undantag, som anges i följande tabell:

|Metod | Lämplig åtgärd|
|--|--|
|[Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) <br/>**OBS!** Intune är nu en del av Microsoft Endpoint Manager. | 1. Gå till [Microsoft Endpoint Manager och](https://go.microsoft.com/fwlink/?linkid=2109431) logga in.<p> 2. Välj  >  **Konfigurationsprofiler för** enheter och välj sedan den profil som du vill konfigurera.<p> 3. Under **Hantera** väljer du **Egenskaper**.<p> 4. Välj **Konfigurationsinställningar: Redigera**.<p> 5. Visa **Microsoft Defender Antivirus** och expandera **Microsoft Defender Antivirus Undantag**.<p> 6. Ange de filer och mappar, tillägg och processer som ska undantas från Microsoft Defender Antivirus genomsökningar. Information finns i [Microsoft Defender Antivirus undantag](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions).<p> 7. Välj **Granska + Spara** och välj sedan **Spara**.  |
|[Microsoft Endpoint Configuration Manager](/mem/configmgr/) | 1. Med hjälp av [konfigurationshanterarens](/mem/configmgr/core/servers/manage/admin-console)konsol går du till Tillgångar och efterlevnad Endpoint Protection Principer för program mot skadlig programvara och väljer sedan den princip som du vill  >    >  ändra. <p> 2. Ange undantagsinställningar för filer och mappar, tillägg och processer som ska undantas från Microsoft Defender Antivirus genomsökningar. |
|[Grupprincipobjekt](/previous-versions/windows/desktop/Policy/group-policy-objects) | 1. Öppna konsolen Grupprinciphantering på [](https://technet.microsoft.com/library/cc731212.aspx)datorn för grupprinciphantering, högerklicka på det grupprincipobjekt som du vill konfigurera och välj sedan **Redigera.**<p> 2. I **redigeraren för grupprinciphantering** går du till **Datorkonfiguration** och väljer **Administrativa mallar**.<p> 3. Expandera trädet för **att Windows komponenter > Microsoft Defender Antivirus > Undantag**.<br/>**OBS!** I vissa versioner *Windows Defender Antivirus* inte *Microsoft Defender Antivirus* visas i Windows.<p> 4. Dubbelklicka på inställningen **Undantag för sökväg** och lägg till undantagen.<br/>- Ställ in alternativet som **Aktiverat.**<br/>- Under **avsnittet Alternativ** väljer du **Visa...**.<br/>- Ange varje mapp på en egen rad under **kolumnen Värdenamn.**<br/>– Om du anger en fil anger du en fullständigt kvalificerad sökväg till filen, inklusive enhetsbeteckningen, mappsökvägen, filnamn och filnamnstillägg. Ange **0** i **kolumnen** Värde.<p> 5. Välj **OK.**<p> 6. Dubbelklicka på inställningen **undantag för filnamnstillägg** och lägg till undantagen.<br/>- Ställ in alternativet som **Aktiverat.**<br/>- Under **avsnittet Alternativ** väljer du **Visa...**.<br/>– Ange varje filnamnstillägg på en egen rad under **kolumnen Värdenamn.**  Ange **0** i **kolumnen** Värde.<p> 7. Välj **OK.** |
|Lokalt grupprincipobjekt |1. Öppna redigeraren för lokala grupprinciper på slutpunkten eller enheten. <p>2. Gå till **Administrativa mallar**  >  **för**  >  **datorkonfiguration Windows komponenter**  >  **Microsoft Defender Antivirus**  >  **Undantag**.<p>**OBS!** I vissa versioner *Windows Defender Antivirus* inte *Microsoft Defender Antivirus* visas i Windows.<p>3. Ange undantag för sökväg och process. |
|Registernyckel |1. Exportera följande registernyckel: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\exclusions` .<p>2. Importera registernyckeln. Här är två exempel:<br/>- Lokal sökväg: `regedit.exe /s c:\temp\ MDAV_Exclusion.reg` <br/>- Nätverksresurs: `regedit.exe /s \\FileServer\ShareName\MDAV_Exclusion.reg` |

### <a name="keep-the-following-points-about-exclusions-in-mind"></a>Tänk på följande om undantag

När du lägger [till undantag Microsoft Defender Antivirus genomsökningar](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)bör du lägga till undantag för sökvägar och processer. Tänk på följande:

- *Undantag från sökvägar* exkluderar specifika filer och all åtkomst till dessa filer.

- *Processkludering* exkluderar det som händer i en process, men exkluderar inte själva processen.

- Lista undantag från processen med hjälp av deras fullständiga sökväg och inte efter namn. (Metoden med endast namn är mindre säker.)

- Om du visar varje körbar (.exe) som både ett sökvägs- och ett processkludering utesluts processen och det som berörs.


## <a name="set-up-your-device-groups-device-collections-and-organizational-units"></a>Konfigurera enhetsgrupper, enhetssamlingar och organisationsenheter

Enhetsgrupper, enhetssamlingar och organisationsenheter gör det möjligt för säkerhetsteamet att hantera och tilldela säkerhetsprinciper effektivt och effektivt. I följande tabell beskrivs var och en av dessa grupper och hur du konfigurerar dem. Din organisation kanske inte använder alla tre samlingstyperna.

| Samlingstyp | Lämplig åtgärd |
|--|--|
|[Enhetsgrupper](/microsoft-365/security/defender-endpoint/machine-groups) (kallades *tidigare datorgrupper)* gör det möjligt för teamet med säkerhetsåtgärder att konfigurera säkerhetsfunktioner, till exempel automatisk undersökning och åtgärd.<p>Enhetsgrupper är också användbara för att tilldela åtkomst till dessa enheter så att ditt säkerhetsteam kan vidta åtgärder om det behövs. <p>Enhetsgrupper skapas i [Microsoft Defender Säkerhetscenter](microsoft-defender-security-center.md). |1. Gå till Microsoft Defender Säkerhetscenter ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ).<p>2. I navigeringsfönstret till vänster väljer du **välj** Inställningar  >  **i Grupper för**  >  **enheter med behörigheter.**  <p>3. Välj **+ Lägg till enhetsgrupp**.<p>4. Ange ett namn och en beskrivning för enhetsgruppen.<p>5. Välj **ett alternativ i** listan Automatiseringsnivå. (Vi rekommenderar **Fullständigt – åtgärda hot automatiskt**.) Mer information om de olika automationsnivåerna finns [i Hur hot åtgärdas.](/microsoft-365/security/defender-endpoint/automated-investigations#how-threats-are-remediated)<p>6. Ange villkor för en matchande regel för att avgöra vilka enheter som tillhör enhetsgruppen. Du kan till exempel välja en domän, OS-versioner eller till och med använda [enhetstaggar.](/microsoft-365/security/defender-endpoint/machine-tags)<p>7. På **fliken Användaråtkomst** anger du roller som ska ha åtkomst till de enheter som ingår i enhetsgruppen. <p>8. Välj **Klar**. |
|[Med hjälp av](/mem/configmgr/core/clients/manage/collections/introduction-to-collections) enhetssamlingar kan ditt säkerhetsteam hantera program, distribuera efterlevnadsinställningar eller installera programvaruuppdateringar på enheterna i organisationen.<p>Enhetssamlingar skapas med [konfigurationshanteraren.](/mem/configmgr/) |Följ stegen i [Skapa en samling.](/mem/configmgr/core/clients/manage/collections/create-collections#bkmk_create) |
|[Med organisationsenheter](/azure/active-directory-domain-services/create-ou) kan du logiskt gruppera objekt som användarkonton, tjänstkonton eller datorkonton. Du kan sedan tilldela administratörer till specifika organisationsenheter och tillämpa grupprinciper för att tillämpa riktade konfigurationsinställningar.<p> Organisationsenheter definieras i [Azure Active Directory Domain Services.](/azure/active-directory-domain-services) | Följ stegen i Skapa [en organisationsenhet i en domän som hanteras Azure Active Directory Domain Services.](/azure/active-directory-domain-services/create-ou) |

## <a name="configure-antimalware-policies-and-real-time-protection"></a>Konfigurera skydd mot skadlig programvara och realtidsskydd

Med Hjälp av Konfigurationshanteraren och din enhetssamling konfigurerar du principer för program mot skadlig programvara.

- Se [Skapa och distribuera program mot skadlig programvara för Endpoint Protection i Configuration Manager.](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies)

- När du skapar och konfigurerar principer för program [](/mem/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) mot skadlig programvara bör du granska skyddsinställningarna i realtid och aktivera [blockering vid första synen.](configure-block-at-first-sight-microsoft-defender-antivirus.md)

> [!TIP]
> Du kan distribuera principerna innan organisationens enheter börjar.

## <a name="next-step"></a>Nästa steg

**Grattis!** Du har slutfört konfigurationsfasen av att [växla till Defender för slutpunkt!](switch-to-microsoft-defender-migration.md#the-migration-process)

- [Gå vidare till fas 3: Onboard to Defender för Endpoint](switch-to-microsoft-defender-onboard.md)
