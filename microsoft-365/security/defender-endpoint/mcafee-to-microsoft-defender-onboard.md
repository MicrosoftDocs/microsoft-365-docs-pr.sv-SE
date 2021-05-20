---
title: McAfee till Microsoft Defender för Slutpunkt – onboard
description: Det här är fas 3, Onboard, för migrering från McAfee till Microsoft Defender för Endpoint.
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
- m365solution-McAfeemigrate
- m365solution-scenario
ms.custom: migrationguides
ms.topic: article
ms.date: 05/14/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 8a9d1ea36ae0778892768e3b39f4ffbed2a8d732
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538033"
---
# <a name="migrate-from-mcafee---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>Migrera från McAfee – fas 3: Gå över till Microsoft Defender för Endpoint

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


|[![Fas 1: Förbereda](images/phase-diagrams/prepare.png)](mcafee-to-microsoft-defender-prepare.md)<br/>[Fas 1: Förbereda](mcafee-to-microsoft-defender-prepare.md) |[![Fas 2: Konfigurera](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)<br/>[Fas 2: Konfigurera](mcafee-to-microsoft-defender-setup.md) |![Fas 3: Introduktion](images/phase-diagrams/onboard.png)<br/>Fas 3: Introduktion |
|--|--|--|
|| |*Du är här!* |

**Välkommen till fas 3 av [migreringen från McAfee Endpoint Security (McAfee) till Microsoft Defender för Slutpunkt](mcafee-to-microsoft-defender-migration.md#the-migration-process)**. Den här migreringsfasen omfattar följande steg:

1. [Onboard-enheter till Microsoft Defender för Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).

2. [Kör ett identifieringstest](#run-a-detection-test).

3. [Kontrollera att Microsoft Defender Antivirus är i passivt läge](#confirm-that-microsoft-defender-antivirus-is-in-passive-mode).

4. [Hämta uppdateringar för Microsoft Defender Antivirus](#get-updates-for-microsoft-defender-antivirus).

5. [Avinstallera McAfee](#uninstall-mcafee).

6. [Kontrollera att Defender för Slutpunkt fungerar som det ska.](#make-sure-defender-for-endpoint-is-working-correctly)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Registrera enheter till Microsoft Defender för Endpoint

1. Gå till Microsoft Defender Säkerhetscenter ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) och logga in.

2. Välj **Inställningar**  >  **Registrering av**  >  **enhetshantering**. 

3. Välj **ett operativsystem i listan Välj** operativsystem för att starta registreringsprocessen. 

4. Välj **ett alternativ** under Distributionsmetod. Följ länkarna och instruktionerna för att registrera organisationens enheter. Behöver du hjälp? Se [Onboarding-metoder](#onboarding-methods) (i den här artikeln).

### <a name="onboarding-methods"></a>Onboarding-metoder
 
Distributionsmetoderna varierar beroende på vilket operativsystem som väljs. Se resurserna i tabellen nedan för att få hjälp med introduktion.

| Operativsystem  |Metod  |
|---------|---------|
| Windows 10     | [Grupprincip](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[Hantering av mobila enheter (Intune)](configure-endpoints-mdm.md)<p>[Lokalt skript](configure-endpoints-script.md) <br/>**Obs!** Ett lokalt skript är lämpligt för ett konceptbevis men bör inte användas för produktionsdistribution. För produktionsdistribution rekommenderar vi att du använder Grupprincip, Microsoft Endpoint Configuration Manager eller Intune.         |
| Windows 8.1 Enterprise <p>Windows 8.1 Pro <p>Windows 7 SP1 Enterprise<p>Windows 7 SP1-Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md)<br/>**OBS!** Microsoft Monitoring Agent är nu Azure Log Analytics-agent. Mer information finns i Översikt [över logganalysagenter.](/azure/azure-monitor/platform/log-analytics-agent)        |
| Windows Server 2019 och senare<p>Windows Basversionen av Server 2019<p>Windows Serverversion 1803 och senare | [Lokalt skript](configure-endpoints-script.md)<p>[Grupprincip](configure-endpoints-gp.md)<p>[Configuration Manager](configure-endpoints-sccm.md)<p>[System Center Configuration Manager](configure-endpoints-sccm.md)<p>[VDI-onboardingskript för icke-beständiga enheter](configure-endpoints-vdi.md) <br/>**Obs!** Ett lokalt skript är lämpligt för ett konceptbevis men bör inte användas för produktionsdistribution. För produktionsdistribution rekommenderar vi att du använder Grupprincip, Microsoft Endpoint Configuration Manager eller Intune.    |
| Windows Server 2016 <p>Windows Server 2012 R2<p>Windows Server 2008 R2 SP1  | [Microsoft Defender Säkerhetscenter](configure-server-endpoints.md)<p>[Azure Defender](/azure/security-center/security-center-wdatp) |
|macOS:<p>11.3.1 (Big Sur)<p>10.15 (Catalina)<p>10.14 (Mojave) |[Introducera icke-Windows-enheter](configure-endpoints-non-windows.md)  |
|iOS |[Introducera icke-Windows-enheter](configure-endpoints-non-windows.md)  |
|Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS eller senare LTS<p>SLES 12+<p>9+<p>Oracle Linux 7.2 |[Introducera icke-Windows-enheter](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Köra ett identifieringstest

Om du vill kontrollera att dina onboarded-enheter är korrekt anslutna till Microsoft Defender för Endpoint kan du köra ett identifieringstest.

|Operativsystem  |Vägledning  |
|---------|---------|
| Windows 10<p>Windows Server 2019 <p>Windows Server, version 1803 <p>Windows Server 2016 <p>Windows Server 2012 R2     |Se [Köra ett identifieringstest](run-detection-test.md). <p>Besök webbplatsen microsoft Defender för slutpunktsdemonstration [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) och prova en eller flera av scenarierna. Prova till exempel **demoscenariot Moln levererat skydd.**         |
|macOS<p>11.3.1 (Big Sur)<p>10.15 (Catalina)<p>10.14 (Mojave)     |Ladda ned och använd APPEN GÖR-själv-programmet på [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <p>Mer information finns i [Microsoft Defender för slutpunkt på Mac.](microsoft-defender-endpoint-mac.md)        |
|Linux:<p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS eller senare LTS<p>SLES 12+<p>9+<p>Oracle Linux 7.2 |1. Kör följande kommando och leta efter resultatet **1:** <br/>`mdatp health --field real_time_protection_enabled`. <p>2. Öppna ett terminalfönster och kör följande kommando: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. Kör följande kommando för att lista identifierade hot: <br/>`mdatp threat list`. <p>Mer information finns i [Microsoft Defender för Slutpunkt i Linux.](microsoft-defender-endpoint-linux.md) |

## <a name="confirm-that-microsoft-defender-antivirus-is-in-passive-mode"></a>Kontrollera att Microsoft Defender Antivirus är i passiv form

Nu när dina slutpunkter har introducerats till Defender för Endpoint är nästa steg att se till att Microsoft Defender Antivirus körs i passiv form. Du kan använda kommandotolken eller PowerShell för att utföra den här uppgiften enligt följande tabell:

|Metod  |Lämplig åtgärd  |
|---------|---------|
|Kommandotolken     |1. På en Windows enhet öppnar du Kommandotolken som administratör.<p> 2. Skriv `sc query windefend` och tryck sedan på Retur.<p> 3. Granska resultaten för att bekräfta att Microsoft Defender Antivirus i passiv form.         |
|PowerShell     |1. På en Windows enhet öppnar du Windows PowerShell som administratör.<p> 2. Kör [cmdleten Get-MpComputerStatus.](/powershell/module/defender/Get-MpComputerStatus) <p> 3. I resultatlistan letar du efter antingen **AMRunningMode: Passivt läge** eller **AMRunningMode: SxS-passivt läge.**|

> [!NOTE]
> I vissa *versioner Windows Defender Antivirus* inte *Microsoft Defender Antivirus* visas i Windows.

### <a name="set-microsoft-defender-antivirus-on-windows-server-to-passive-mode-manually"></a>Ställ Microsoft Defender Antivirus på Windows server till passivt läge manuellt

Om du Microsoft Defender Antivirus till passivt läge på Windows Server, version 1803 eller senare eller Windows Server 2019 gör du så här:

1. Öppna Registereditorn och gå till `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection` .

2. Redigera (eller skapa) en DWORD-post **som heter ForcePassiveMode** och ange följande inställningar:

   - Ställ in DWORD-värdet på `1` .
   - Under **Bas** väljer du **Hexadecimal**.
 
   > [!NOTE]
   > Du kan använda andra metoder för att ange registernyckeln, till exempel följande:
   > - Grupprincipinställning
   > - Verktyget Lokalt grupprincipobjekt
   > - Ett paket i Konfigurationshanteraren

### <a name="start-microsoft-defender-antivirus-on-windows-server-2016"></a>Starta Microsoft Defender Antivirus på Windows Server 2016

Om du använder Windows Server 2016 kan du behöva börja Microsoft Defender Antivirus manuellt. Det kan du göra med hjälp av PowerShell-cmdleten `mpcmdrun.exe -wdenable` på enheten.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Hämta uppdateringar för Microsoft Defender Antivirus

Att hålla Microsoft Defender Antivirus uppdaterat är viktigt för att säkerställa att dina enheter har den senaste tekniken och funktionerna som behövs för att skydda mot nya tekniker för skadlig programvara och attack, även om Microsoft Defender Antivirus körs i passiv form.

Det finns två typer av uppdateringar som är relaterade till Microsoft Defender Antivirus uppdateringar:
- Säkerhetsintelligensuppdateringar
- Produktuppdateringar

Följ linjerna i Hantera uppdateringar i Microsoft Defender Antivirus [och tillämpa baslinjer](manage-updates-baselines-microsoft-defender-antivirus.md)för att få uppdateringarna.


## <a name="uninstall-mcafee"></a>Avinstallera McAfee

Nu när du har introducerat din organisations enheter i Microsoft Defender för Endpoint är nästa steg att avinstallera McAfee. Om du vill ha hjälp med det här steget går du till din McAfee ServicePortal ( [http://mysupport.mcafee.com](http://mysupport.mcafee.com) ).

## <a name="make-sure-defender-for-endpoint-is-working-correctly"></a>Kontrollera att Defender för Slutpunkt fungerar korrekt

Nu när du har avinstallerat McAfee är nästa steg att se till att Microsoft Defender Antivirus och identifiering och åtgärd på slutpunkt är aktiverade och i aktivt läge.

Om du vill göra detta går du till webbplatsen för microsoft Defender för endpoint-demoscenarier ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Prova en eller flera demoscenarier på den sidan, inklusive minst följande:
- Molnbaserat skydd
- Potentiellt oönskade program (PUA)
- Network Protection (NP)

> [!IMPORTANT]
> Om du använder Windows Server 2016 kan du behöva börja Microsoft Defender Antivirus manuellt. Det kan du göra med hjälp av PowerShell-cmdleten `mpcmdrun.exe -wdenable` på enheten.

## <a name="next-steps"></a>Nästa steg

**Grattis!** Du har slutfört [migreringen från McAfee till Microsoft Defender för Slutpunkt](mcafee-to-microsoft-defender-migration.md#the-migration-process)! 

- [Besök instrumentpanelen för säkerhetsåtgärder](security-operations-dashboard.md) i Microsoft Defender Säkerhetscenter ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Hantera Microsoft Defender för Slutpunkt efter migreringen.](manage-atp-post-migration.md)
