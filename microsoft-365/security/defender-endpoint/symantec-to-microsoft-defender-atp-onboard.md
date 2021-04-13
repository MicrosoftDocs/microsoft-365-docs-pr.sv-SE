---
title: Symantec för Microsoft Defender för Endpoint – fas 3, onboarding
description: Det här är fas 3, introduktion, av migreringen från Symantec till Microsoft Defender för Slutpunkt
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: b42a33d975e1368ad25d4a7102ef44bf8b9824a8
ms.sourcegitcommit: 72ae1b49e7a3d3199272fcb4c39f5daec0d66f1a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51698286"
---
# <a name="migrate-from-symantec---phase-3-onboard-to-microsoft-defender-for-endpoint"></a>Migrera från Symantec – fas 3: Introduktion till Microsoft Defender för Slutpunkt

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|[![Fas 1: Förbereda](images/phase-diagrams/prepare.png)](symantec-to-microsoft-defender-atp-prepare.md)<br/>[Fas 1: Förbereda](symantec-to-microsoft-defender-atp-prepare.md) |[![Fas 2: Konfigurera](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Fas 2: Konfigurera](symantec-to-microsoft-defender-atp-setup.md) |![Fas 3: Introduktion](images/phase-diagrams/onboard.png)<br/>Fas 3: Introduktion |
|--|--|--|
|| |*Du är här!* |


**Välkommen till fas 3 av [migreringen från Symantec till Microsoft Defender för Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)**. Den här migreringsfasen omfattar följande steg:

1. [Onboard-enheter till Microsoft Defender för Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).
2. [Kör ett identifieringstest](#run-a-detection-test).
3. [Avinstallera Symantec](#uninstall-symantec).
4. [Kontrollera att Microsoft Defender för Slutpunkt är i aktivt läge](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode).

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Registrera enheter till Microsoft Defender för Endpoint

1. Gå till Microsoft Defender Säkerhetscenter ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) och logga in.
2. Välj **Inställningar Registrering** av  >    >  **enhetshantering**. 
3. Välj **ett operativsystem i listan Välj** operativsystem för att starta registreringsprocessen. 
4. Välj **ett alternativ** under Distributionsmetod. Följ länkarna och instruktionerna för att registrera organisationens enheter. Behöver du hjälp? Se [Onboarding-metoder](#onboarding-methods) (i den här artikeln).

### <a name="onboarding-methods"></a>Onboarding-metoder
 
Distributionsmetoderna varierar beroende på vilket operativsystem som väljs. Se resurserna i tabellen nedan för att få hjälp med introduktion.

|Operativsystem  |Metod  |
|---------|---------|
|Windows 10     |- [Grupprincip](configure-endpoints-gp.md)<br/>- [Konfigurationshanteraren](configure-endpoints-sccm.md)<br/>- [Hantering av mobila enheter (Intune)](configure-endpoints-mdm.md)<br/>- [Lokalt skript](configure-endpoints-script.md) <br/><br/>**Obs!** Ett lokalt skript är lämpligt för ett konceptbevis men bör inte användas för produktionsdistribution. För produktionsdistribution rekommenderar vi att du använder Grupprincip, Microsoft Endpoint Configuration Manager eller Intune.         |
|- Windows 8.1 Enterprise <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1 Enterprise <br/>- Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint)<br/><br/>**OBS!** Microsoft Monitoring Agent är nu Azure Log Analytics-agent. Mer information finns i Översikt [över logganalysagenter.](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)        |
|- Windows Server 2019 och senare <br/>- Kärnversionen av Windows Server 2019 <br/>- Windows Server version 1803 och senare |- [Lokalt skript](configure-endpoints-script.md) <br/>- [Grupprincip](configure-endpoints-gp.md) <br/>- [Konfigurationshanteraren](/configure-endpoints-sccm.md) <br/>- [System Center Configuration Manager](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)<br/>- [VDI-onboardingskript för icke-beständiga enheter](configure-endpoints-vdi.md) <br/><br/>**Obs!** Ett lokalt skript är lämpligt för ett konceptbevis men bör inte användas för produktionsdistribution. För produktionsdistribution rekommenderar vi att du använder Grupprincip, Microsoft Endpoint Configuration Manager eller Intune.    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Microsoft Defender Säkerhetscenter](configure-server-endpoints.md)<br/>- [Azure Säkerhetscenter](https://docs.microsoft.com/azure/security-center/security-center-wdatp) |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10.13 (High Sierra)<br/><br/>iOS<br/><br/>Linux:<br/>- RHEL 7,2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS, eller senare LTS<br/>- SLES 12+<br/>- Till och med 9+<br/>- Oracle Linux 7.2 |[Registrera icke-Windows-enheter](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Köra ett identifieringstest

Om du vill kontrollera att dina onboarded-enheter är korrekt anslutna till Microsoft Defender för Endpoint kan du köra ett identifieringstest.

|Operativsystem  |Vägledning  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server, version 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |Se [Köra ett identifieringstest](run-detection-test.md). <br/><br/>Besök webbplatsen microsoft Defender för slutpunktsdemonstration [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) och prova en eller flera av scenarierna. Prova till exempel **demoscenariot Moln levererat skydd.**         |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10.13 (High Sierra)     |Ladda ned och använd APPEN GÖR-själv-programmet på [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <br/><br/>Mer information finns i [Microsoft Defender för Slutpunkt på macOS.](microsoft-defender-endpoint-mac.md)        |
|Linux:<br/>- RHEL 7,2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS, eller senare LTS<br/>- SLES 12+<br/>- Till och med 9+<br/>- Oracle Linux 7.2 |1. Kör följande kommando och leta efter resultatet **1:** <br/>`mdatp health --field real_time_protection_enabled`. <br/><br/>2. Öppna ett terminalfönster och kör följande kommando: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <br/><br/>3. Kör följande kommando för att lista identifierade hot: <br/>`mdatp threat list`. <br/><br/>Mer information finns i [Microsoft Defender för Slutpunkt i Linux.](microsoft-defender-endpoint-linux.md) |

## <a name="uninstall-symantec"></a>Avinstallera Symantec

Nu när du har introducerat din organisations enheter i Microsoft Defender för Endpoint är nästa steg att avinstallera Symantec.

1. [Inaktivera skydd mot manipulering](https://knowledge.broadcom.com/external/article?legacyId=tech192023) i Symantec.
2. Ta bort avinstallationslösenordet för Symantec:<br/>
   1. Öppna Registereditorn som administratör på dina Windows-enheter.
   2. Gå till `HKEY_LOCAL_MACHINE\SOFTWARE\Symantec\Symantec Endpoint Protection\SMC`.
   3. Leta efter en post med **namnet SmcInstData**. 
   4. Högerklicka på objektet och välj sedan Ta **bort**. 
3. Ta bort Symantec från dina enheter. Om du behöver hjälp med detta kan du läsa Broadcoms dokumentation. Här är några Broadcom-resurser: 
   - [Avinstallera Symantec Endpoint Protection](https://knowledge.broadcom.com/external/article/156148/uninstall-symantec-endpoint-protection.html)
   - Windows-enheter: [Avinstallera Endpoint Protection 14-klienter manuellt i Windows](https://knowledge.broadcom.com/external/article?articleId=170040)
   - macOS-datorer: [Ta bort Symantec-programvaran för Mac med RemoveSymantecMacFiles](https://knowledge.broadcom.com/external/article?articleId=151387)
   - Linux-enheter: [Vanliga frågor och svar om Endpoint Protection på Linux](https://knowledge.broadcom.com/external/article?articleId=162054)

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Kontrollera att Microsoft Defender för Slutpunkt är i aktivt läge

Nu när du har avinstallerat Symantec är nästa steg att se till att Microsoft Defender Antivirus och Microsoft Defender för Slutpunkt är aktiverade och i aktivt läge.

Om du vill göra detta går du till webbplatsen för microsoft Defender för endpoint-demoscenarier ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Prova en eller flera demoscenarier på den sidan, inklusive minst följande:
- Moln levererat skydd
- Potentiellt oönskade program (PUA)
- Network Protection (NP)

> [!IMPORTANT]
> Om du använder Windows Server 2016 kan du behöva starta Microsoft Defender Antivirus manuellt. Det kan du göra med hjälp av PowerShell-cmdleten `mpcmdrun.exe -wdenable` på enheten.

## <a name="next-steps"></a>Nästa steg

**Grattis!** Du har slutfört [migreringen från Symantec till Microsoft Defender för Endpoint](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)! 
- [Besök instrumentpanelen för säkerhetsåtgärder](security-operations-dashboard.md) i Microsoft Defender Säkerhetscenter ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Hantera Microsoft Defender för Slutpunkt efter migreringen.](manage-atp-post-migration.md)
