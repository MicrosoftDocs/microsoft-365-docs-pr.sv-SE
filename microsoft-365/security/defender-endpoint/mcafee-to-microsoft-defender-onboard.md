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
ms.date: 05/10/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 00f96234fd92a70b4d2a2c1dba2862a6ee3404f4
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327384"
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
3. [Avinstallera McAfee](#uninstall-mcafee).
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
|Windows 10     |- [Grupprincip](configure-endpoints-gp.md)<br/>- [Konfigurationshanteraren](configure-endpoints-sccm.md)<br/>- [Hantering av mobila enheter (Intune)](configure-endpoints-mdm.md)<br/>- [Lokalt skript](configure-endpoints-script.md) <p>**Obs!** Ett lokalt skript är lämpligt för ett konceptbevis men bör inte användas för produktionsdistribution. För produktionsdistribution rekommenderar vi att du använder Grupprincip, Microsoft Endpoint Configuration Manager eller Intune.         |
|- Windows 8.1 Enterprise <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1 Enterprise <br/>- Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](onboard-downlevel.md)<p>**OBS!** Microsoft Monitoring Agent är nu Azure Log Analytics-agent. Mer information finns i Översikt [över logganalysagenter.](/azure/azure-monitor/platform/log-analytics-agent)        |
|- Windows Server 2019 och senare <br/>- Kärnversionen av Windows Server 2019 <br/>- Windows Server version 1803 och senare |- [Lokalt skript](configure-endpoints-script.md) <br/>- [Grupprincip](configure-endpoints-gp.md) <br/>- [Konfigurationshanteraren](configure-endpoints-sccm.md) <br/>- [System Center Configuration Manager](configure-endpoints-sccm.md) <br/>- [VDI-onboardingskript för icke-beständiga enheter](configure-endpoints-vdi.md) <p>**Obs!** Ett lokalt skript är lämpligt för ett konceptbevis men bör inte användas för produktionsdistribution. För produktionsdistribution rekommenderar vi att du använder Grupprincip, Microsoft Endpoint Configuration Manager eller Intune.    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Microsoft Defender Säkerhetscenter](configure-server-endpoints.md)<br/>- [Azure Defender](/azure/security-center/security-center-wdatp) |
|macOS<br/>- 11.3.1 (Big Sur)<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<p>iOS<p>Linux:<br/>- RHEL 7,2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS, eller senare LTS<br/>- SLES 12+<br/>- Till och med 9+<br/>- Oracle Linux 7.2 |[Introducera icke-Windows-enheter](configure-endpoints-non-windows.md)  |

## <a name="run-a-detection-test"></a>Köra ett identifieringstest

Om du vill kontrollera att dina onboarded-enheter är korrekt anslutna till Microsoft Defender för Endpoint kan du köra ett identifieringstest.


|Operativsystem  |Vägledning  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server, version 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |Se [Köra ett identifieringstest](run-detection-test.md). <p>Besök webbplatsen microsoft Defender för slutpunktsdemonstration [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) och prova en eller flera av scenarierna. Prova till exempel **demoscenariot Moln levererat skydd.**         |
|macOS<br/>- 11.3.1 (Big Sur)<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)     |Ladda ned och använd APPEN GÖR-själv-programmet på [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) . <p>Mer information finns i [Microsoft Defender för slutpunkt på Mac.](microsoft-defender-endpoint-mac.md)        |
|Linux:<br/>- RHEL 7,2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS, eller senare LTS<br/>- SLES 12+<br/>- Till och med 9+<br/>- Oracle Linux 7.2 |1. Kör följande kommando och leta efter resultatet **1:** <br/>`mdatp health --field real_time_protection_enabled`. <p>2. Öppna ett terminalfönster och kör följande kommando: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <p>3. Kör följande kommando för att lista identifierade hot: <br/>`mdatp threat list`. <p>Mer information finns i [Microsoft Defender för Slutpunkt i Linux.](microsoft-defender-endpoint-linux.md) |

## <a name="uninstall-mcafee"></a>Avinstallera McAfee

Nu när du har introducerat din organisations enheter i Microsoft Defender för Endpoint är nästa steg att avinstallera McAfee.

Om du vill ha hjälp med det här steget går du till din McAfee ServicePortal ( [http://mysupport.mcafee.com](http://mysupport.mcafee.com) ).

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Kontrollera att Microsoft Defender för Slutpunkt är i aktivt läge

Nu när du har avinstallerat McAfee är nästa steg att se till att Microsoft Defender Antivirus samt identifiering och svar av slutpunkter är aktiverade och i aktivt läge.

Om du vill göra detta går du till webbplatsen för microsoft Defender för endpoint-demoscenarier ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Prova en eller flera demoscenarier på den sidan, inklusive minst följande:
- Molnbaserat skydd
- Potentiellt oönskade program (PUA)
- Network Protection (NP)

> [!IMPORTANT]
> Om du använder Windows Server 2016 kan du behöva starta Microsoft Defender Antivirus manuellt. Det kan du göra med hjälp av PowerShell-cmdleten `mpcmdrun.exe -wdenable` på enheten.

## <a name="next-steps"></a>Nästa steg

**Grattis!** Du har slutfört [migreringen från McAfee till Microsoft Defender för Slutpunkt](mcafee-to-microsoft-defender-migration.md#the-migration-process)! 

- [Besök instrumentpanelen för säkerhetsåtgärder](security-operations-dashboard.md) i Microsoft Defender Säkerhetscenter ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Hantera Microsoft Defender för Slutpunkt efter migreringen.](manage-atp-post-migration.md)
