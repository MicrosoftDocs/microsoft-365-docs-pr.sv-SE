---
title: Växla till Microsoft Defender för Slutpunkt – onboard
description: Det här är steg 3, Onboard, för migrering från en lösning som inte är en Microsoft-lösning till Microsoft Defender för Endpoint.
keywords: migrering, windows defender avancerat skydd, atp, edr
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
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: afc3590bb3ad57a63868bb8218612ae69956186c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185545"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Växla till Microsoft Defender för Slutpunkt – fas 3: Onboard

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![Fas 1: Förbereda3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Fas 1: Förbereda](switch-to-microsoft-defender-prepare.md) | [![Fas 2: Konfigurera](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Fas 2: Konfigurera](switch-to-microsoft-defender-setup.md) | ![Fas 3: Introduktion](images/phase-diagrams/onboard.png)<br/>Fas 3: Introduktion |
|--|--|--|
|| |*Du är här!* |


**Välkommen till Fas 3 för [att byta till Microsoft Defender för Slutpunkt.](switch-to-microsoft-defender-migration.md#the-migration-process)** Den här migreringsfasen omfattar följande steg:

1. [Onboard-enheter till Microsoft Defender för Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).
2. [Kör ett identifieringstest](#run-a-detection-test).
3. [Avinstallera din lösning som inte är en Microsoft-lösning.](#uninstall-your-non-microsoft-solution)
4. [Kontrollera att Microsoft Defender för Slutpunkt är i aktivt läge](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode).

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Onboard devices to Microsoft Defender for Endpoint

1. Gå till Microsoft Defender Säkerhetscenter ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) och logga in.
2. Välj **Inställningar Registrering** av  >    >  **enhetshantering**. 
3. Välj **ett operativsystem i listan Välj** operativsystem för att starta registreringsprocessen. 
4. Välj **ett alternativ** under Distributionsmetod. Följ länkarna och instruktionerna för att registrera organisationens enheter. Behöver du hjälp? Se [Onboarding-metoder](#onboarding-methods) (i den här artikeln).

### <a name="onboarding-methods"></a>Onboarding-metoder
 
Distributionsmetoderna varierar beroende på vilket operativsystem som väljs. Se resurserna i tabellen nedan för att få hjälp med introduktion.

|Operativsystem  |Metod  |
|---------|---------|
|Windows 10     |- [Grupprincip](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp)<br/>- [Konfigurationshanteraren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)<br/>- [Hantering av mobila enheter (Intune)](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-mdm)<br/>- [Lokalt skript](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/><br/>**Obs!** Ett lokalt skript är lämpligt för ett konceptbevis men bör inte användas för produktionsdistribution. För produktionsdistribution rekommenderar vi att du använder Grupprincip, Microsoft Endpoint Configuration Manager eller Intune.         |
|- Windows 8.1 Enterprise <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1 Enterprise <br/>- Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-atp)<br/><br/>**OBS!** Microsoft Monitoring Agent är nu Azure Log Analytics-agent. Mer information finns i Översikt [över logganalysagenter.](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)        |
|- Windows Server 2019 och senare <br/>- Kärnversionen av Windows Server 2019 <br/>- Windows Server version 1803 och senare |- [Lokalt skript](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/>- [Grupprincip](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp) <br/>- [Konfigurationshanteraren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm) <br/>- [System Center Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm#onboard-windows-10-devices-using-earlier-versions-of-system-center-configuration-manager) <br/>- [VDI-onboardingskript för icke-beständiga enheter](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi) <br/><br/>**Obs!** Ett lokalt skript är lämpligt för ett konceptbevis men bör inte användas för produktionsdistribution. För produktionsdistribution rekommenderar vi att du använder Grupprincip, Microsoft Endpoint Configuration Manager eller Intune.    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Microsoft Defender Säkerhetscenter](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#option-1-onboard-servers-through-microsoft-defender-security-center)<br/>- [Azure Säkerhetscenter](https://docs.microsoft.com/azure/security-center/security-center-wdatp) |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10.13 (High Sierra)<br/><br/>iOS<br/><br/>Linux:<br/>- RHEL 7,2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS, eller senare LTS<br/>- SLES 12+<br/>- Till och med 9+<br/>- Oracle Linux 7.2 |[Introducera enheter som inte är Windows-enheter](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-non-windows)  |

## <a name="run-a-detection-test"></a>Köra ett identifieringstest

Om du vill kontrollera att dina onboarded-enheter är korrekt anslutna till Microsoft Defender för Endpoint kan du köra ett identifieringstest.

|Operativsystem  |Vägledning  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server, version 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |Se [Köra ett identifieringstest](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test). <br/><br/>Besök webbplatsen microsoft Defender för slutpunktsdemonstration [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) och prova en eller flera av scenarierna. Prova till exempel **demoscenariot Moln levererat skydd.**         |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10.13 (High Sierra)     |Ladda ned och använd APPEN GÖR-själv-programmet på [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <br/><br/>Mer information finns i [Microsoft Defender för Slutpunkt för Mac.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac)        |
|Linux:<br/>- RHEL 7,2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS, eller senare LTS<br/>- SLES 12+<br/>- Till och med 9+<br/>- Oracle Linux 7.2 |1. Kör följande kommando och leta efter resultatet **1:** <br/>`mdatp health --field real_time_protection_enabled`. <br/><br/>2. Öppna ett terminalfönster och kör följande kommando: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <br/><br/>3. Kör följande kommando för att lista identifierade hot: <br/>`mdatp threat list`. <br/><br/>Mer information finns i [Microsoft Defender ATP för Linux.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux) |

## <a name="uninstall-your-non-microsoft-solution"></a>Avinstallera din lösning som inte är en Microsoft-lösning

Nu när du har introducerat din organisations enheter i Microsoft Defender för Endpoint är nästa steg att avinstallera en lösning som inte är en Microsoft-slutpunktsskyddslösning.

Om du behöver hjälp med det här steget kan du kontakta lösningsleverantörens tekniska supportteam.

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Kontrollera att Microsoft Defender för Slutpunkt är i aktivt läge

Nu när du har avinstallerat din lösning som inte är en Microsoft-slutpunktsskyddslösning är nästa steg att se till att Microsoft Defender Antivirus och Microsoft Defender för Slutpunkt är aktiverade och i aktivt läge.

Om du vill göra detta går du till webbplatsen för microsoft Defender för endpoint-demoscenarier ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Prova en eller flera demoscenarier på den sidan, inklusive minst följande:
- Moln levererat skydd
- Potentiellt oönskade program (PUA)
- Network Protection (NP)

> [!IMPORTANT]
> Om du använder Windows Server 2016 kan du behöva starta Microsoft Defender Antivirus manuellt. Det kan du göra med hjälp av PowerShell-cmdleten `mpcmdrun.exe -wdenable` på enheten.

## <a name="next-steps"></a>Nästa steg

**Grattis!** Du har slutfört [migreringen till Microsoft Defender för Slutpunkt](switch-to-microsoft-defender-migration.md#the-migration-process)! 

- [Besök instrumentpanelen för säkerhetsåtgärder](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard) i Microsoft Defender Säkerhetscenter ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Hantera Microsoft Defender för Slutpunkt efter migreringen.](manage-atp-post-migration.md)
