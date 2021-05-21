---
title: Växla till Microsoft Defender för Slutpunkt – onboard
description: Det här är steg 3, Onboard, för migrering från en lösning som inte är en Microsoft-lösning till Microsoft Defender för Endpoint.
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
ms.custom: migrationguides
ms.topic: article
ms.date: 05/20/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 939fea5b815827f5afbe6cdf78fd9335da6337e8
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594067"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Växla till Microsoft Defender för Slutpunkt – fas 3: Onboard

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![Fas 1: Förbereda3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Fas 1: Förbereda](switch-to-microsoft-defender-prepare.md) | [![Fas 2: Konfigurera](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Fas 2: Konfigurera](switch-to-microsoft-defender-setup.md) | ![Fas 3: Introduktion](images/phase-diagrams/onboard.png)<br/>Fas 3: Introduktion |
|--|--|--|
|| |*Du är här!* |


**Välkommen till Fas 3 om [att byta till Defender för Slutpunkt.](switch-to-microsoft-defender-migration.md#the-migration-process)** Den här migreringsfasen omfattar följande steg:

1. [Introducera enheter till Defender för Slutpunkt](#onboard-devices-to-microsoft-defender-for-endpoint).
2. [Kör ett identifieringstest](#run-a-detection-test).
3. [Kontrollera att Microsoft Defender Antivirus är i passivt läge på dina slutpunkter](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints).
4. [Hämta uppdateringar för Microsoft Defender Antivirus](#get-updates-for-microsoft-defender-antivirus).
5. [Avinstallera din lösning som inte är en Microsoft-lösning.](#uninstall-your-non-microsoft-solution) 
6. [Kontrollera att Defender för Slutpunkt fungerar som det ska.](#make-sure-defender-for-endpoint-is-working-correctly)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Registrera enheter till Microsoft Defender för Endpoint

1. Gå till Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) och logga in.

2. Välj **Inställningar**  >  **Registrering av**  >  **enhetshantering**. 

3. Välj **ett operativsystem i listan Välj** operativsystem för att starta registreringsprocessen. 

4. Välj **ett alternativ** under Distributionsmetod. Följ länkarna och instruktionerna för att registrera organisationens enheter. Behöver du hjälp? Se [Onboarding-metoder](#onboarding-methods) (i den här artikeln).

### <a name="onboarding-methods"></a>Onboarding-metoder
 
Distributionsmetoderna varierar beroende på operativsystem och rekommenderade metoder. I följande tabell finns resurser som hjälper dig att komma igång med Defender för Slutpunkt:

|Operativsystem  |Metoder  |
|---------|---------|
| Windows 10     | [Grupprincip](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[Hantering av mobila enheter (Intune)](configure-endpoints-mdm.md)<p>[Lokalt skript](configure-endpoints-script.md) <p>**Obs!** Ett lokalt skript är lämpligt för ett konceptbevis men bör inte användas för produktionsdistribution. För produktionsdistribution rekommenderar vi att du använder Grupprincip, Microsoft Endpoint Configuration Manager eller Intune.         |
| Windows 8.1 Enterprise <p>Windows 8.1 Pro <p>Windows 7 SP1 Enterprise <p>Windows 7 SP1-Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md)<p>**OBS!** Microsoft Monitoring Agent är nu Azure Log Analytics-agent. Mer information finns i Översikt [över logganalysagenter.](/azure/azure-monitor/platform/log-analytics-agent)        |
| Windows Server 2019 och senare <p>Windows Basversionen av Server 2019 <p>Windows Serverversion 1803 och senare | [Lokalt skript](configure-endpoints-script.md) <p>[Grupprincip](configure-endpoints-gp.md) <p>[Configuration Manager](configure-endpoints-sccm.md) <p>[System Center Configuration Manager](configure-endpoints-sccm.md) <p>[VDI-onboardingskript för icke-beständiga enheter](configure-endpoints-vdi.md) <p>**Obs!** Ett lokalt skript är lämpligt för ett konceptbevis men bör inte användas för produktionsdistribution. För produktionsdistribution rekommenderar vi att du använder Grupprincip, Microsoft Endpoint Configuration Manager eller Intune.    |
| Windows Server 2016 <p>Windows Server 2012 R2 <p>Windows Server 2008 R2 SP1  | [Microsoft Defender Säkerhetscenter](configure-server-endpoints.md)<p>[Azure Defender](/azure/security-center/security-center-wdatp) |
| macOS:<p>11.3.1 (Big Sur) <p>10.15 (Catalina)<p>10.14 (Mojave) | [Introducera icke-Windows-enheter](configure-endpoints-non-windows.md)  |
| iOS | [Introducera icke-Windows-enheter](configure-endpoints-non-windows.md)  |
| Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS eller senare LTS<p>SLES 12+<p>9+<p>Oracle Linux 7.2 | [Introducera icke-Windows-enheter](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Köra ett identifieringstest

Om du vill kontrollera att dina onboarded-enheter är korrekt anslutna till Defender för Endpoint kan du köra ett identifieringstest.

|Operativsystem  |Vägledning  |
|---------|---------|
| Windows 10 <p>Windows Server 2019 <p>Windows Server, version 1803 <p>Windows Server 2016 <p>Windows Server 2012 R2     | Se [Köra ett identifieringstest](run-detection-test.md). <p>Besök webbplatsen för Demoscenarier i Defender för slutpunkt [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) () och prova en eller flera av scenarierna. Prova till exempel **demoscenariot Moln levererat skydd.**    |
| macOS:<p>11.3.1 (Big Sur) <p>10.15 (Catalina)<p>10.14 (Mojave)    | Ladda ned och använd APPEN GÖR-själv-programmet på [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <p>Mer information finns i [Defender för Slutpunkt på macOS.](microsoft-defender-endpoint-mac.md)        |
| Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS eller senare LTS<p>SLES 12+<p>9+<p>Oracle Linux 7.2 | 1. Kör följande kommando och leta efter resultatet **1:** <br/>`mdatp health --field real_time_protection_enabled`. <p>2. Öppna ett terminalfönster och kör följande kommando: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. Kör följande kommando för att lista identifierade hot: <br/>`mdatp threat list`. <p>Mer information finns i [Defender för Slutpunkt på Linux.](microsoft-defender-endpoint-linux.md) |

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode-on-your-endpoints"></a>Kontrollera att Microsoft Defender Antivirus är i passivt läge på dina slutpunkter

Nu när dina slutpunkter har introducerats till Defender för Endpoint är nästa steg att se till att Microsoft Defender Antivirus körs i passiv form. Du kan använda kommandotolken eller PowerShell för att utföra den här uppgiften enligt följande tabell:

| Metod  | Lämplig åtgärd  |
|:-------|:-------|
|Kommandotolken     | 1. På en Windows enhet öppnar du Kommandotolken som administratör.<p>2. Skriv `sc query windefend` och tryck sedan på Retur.<p>3. Granska resultaten för att bekräfta att Microsoft Defender Antivirus i passiv form.         |
| PowerShell     | 1. På en Windows enhet öppnar du Windows PowerShell som administratör.<p>2. Kör [cmdleten Get-MpComputerStatus.](/powershell/module/defender/Get-MpComputerStatus) <p>3. I resultatlistan letar du efter antingen **AMRunningMode: Passivt läge** eller **AMRunningMode: SxS-passivt läge.**    |

> [!NOTE]
> I vissa *versioner Windows Defender Antivirus* inte *Microsoft Defender Antivirus* visas i Windows.

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>Ställ Microsoft Defender Antivirus på Windows server till passivt läge manuellt

Om du Microsoft Defender Antivirus till passivt läge på Windows Server, version 1803 eller senare eller Windows Server 2019 gör du så här:

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

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>Starta Microsoft Defender Antivirus på Windows Server 2016

Om du använder Windows Server 2016 kan du behöva börja Microsoft Defender Antivirus manuellt. Det kan du göra med hjälp av PowerShell-cmdleten `mpcmdrun.exe -wdenable` på enheten.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Hämta uppdateringar för Microsoft Defender Antivirus

Att hålla Microsoft Defender Antivirus uppdaterat är viktigt för att säkerställa att dina enheter har den senaste tekniken och funktionerna som behövs för att skydda mot nya tekniker för skadlig programvara och attack, även om Microsoft Defender Antivirus körs i passiv form. (Se [Microsoft Defender Antivirus kompatibilitet](microsoft-defender-antivirus-compatibility.md).)

Det finns två typer av uppdateringar som är relaterade till Microsoft Defender Antivirus uppdateringar:

- Säkerhetsintelligensuppdateringar
- Produktuppdateringar

Följ linjerna i Hantera uppdateringar i Microsoft Defender Antivirus [och tillämpa baslinjer](manage-updates-baselines-microsoft-defender-antivirus.md)för att få uppdateringarna.

## <a name="uninstall-your-non-microsoft-solution"></a>Avinstallera din lösning som inte är en Microsoft-lösning

Om du vid det här läget har:

- Din organisations enheter onboardeds till Defender för Endpoint och 
- Microsoft Defender Antivirus är installerat och aktiverat 

Nästa steg är att avinstallera en lösning som inte är en Microsoft-slutpunktsskyddslösning. 

Om du behöver hjälp med den här uppgiften kan du kontakta lösningsleverantörens tekniska supportteam.

## <a name="make-sure-defender-for-endpoint-is-working-correctly"></a>Kontrollera att Defender för Slutpunkt fungerar korrekt

Nu när du har gått över till Defender för Endpoint och du har avinstallerat din tidigare lösning utanför Microsoft är nästa steg att se till att Defender för Slutpunkt fungerar korrekt. Ett bra sätt att göra detta är att besöka webbplatsen för Defender för Endpoint-demoscenarier ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Prova en eller flera demoscenarier på den sidan, inklusive minst följande:

- Molnbaserat skydd
- Potentiellt oönskade program (PUA)
- Network Protection (NP)

## <a name="next-steps"></a>Nästa steg

**Grattis!** Du har slutfört [migreringen till Defender för slutpunkt](switch-to-microsoft-defender-migration.md#the-migration-process)! 

- [Besök instrumentpanelen för säkerhetsåtgärder](security-operations-dashboard.md) i Microsoft Defender Säkerhetscenter ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ). 
- [Hantera Defender för Slutpunkt efter migreringen.](manage-atp-post-migration.md)
