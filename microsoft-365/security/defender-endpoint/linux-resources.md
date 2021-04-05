---
title: Microsoft Defender ATP för Linux-resurser
ms.reviewer: ''
description: Här beskrivs resurser för Microsoft Defender ATP för Linux, bland annat hur du avinstallerar det, hur du samlar in diagnostikloggar, CLI-kommandon och kända problem med produkten.
keywords: microsoft, defender, atp, linux, installation, distribuera, avinstallation, enkel, ansible, linux, redhat, ubuntu, ubuntu, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a4f2324bc47bdee38e1cdeed1e21b5f9063e9a5c
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587072"
---
# <a name="resources"></a>Resurser

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a>Samla in diagnostikinformation

Om du kan återskapa ett problem ökar du först loggningsnivån, kör systemet ett tag och återställer sedan loggningsnivån till standardvärdet.

1. Öka loggningsnivån:

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. Återskapa problemet.

3. Kör följande kommando för att backa upp Defender för Endpoints loggar. Filerna lagras i ett ZIP-arkiv.

   ```bash
   sudo mdatp diagnostic create
   ```

    Det här kommandot skriver också ut filsökvägen till säkerhetskopian när åtgärden har lyckats:

   ```Output
   Diagnostic file created: <path to file>
   ```

4. Återställa loggningsnivån:

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a>Logga installationsproblem

Om ett fel uppstår under installationen rapporterar installationsprogrammet bara ett allmänt fel.

Den detaljerade loggen sparas i `/var/log/microsoft/mdatp_install.log` . Om du upplever problem under installationen kan du skicka den här filen till oss så att vi kan hjälpa till att diagnostisera orsaken.

## <a name="uninstall"></a>Avinstallera

Det finns flera sätt att avinstallera Defender för Endpoint för Linux. Om du använder ett konfigurationsverktyg, till exempel Beser, följer du paketinstallationsanvisningarna för konfigurationsverktyget.

### <a name="manual-uninstallation"></a>Manuell avinstallation

- `sudo yum remove mdatp` för RHEL och varianter(CentOS och Oracle Linux).
- `sudo zypper remove mdatp` för SLES och varianter.
- `sudo apt-get purge mdatp` för Ubuntu och Ubuntu systems.

## <a name="configure-from-the-command-line"></a>Konfigurera från kommandoraden

Viktiga uppgifter, som att kontrollera produktinställningar och utlösa skanningar på begäran, kan utföras från kommandoraden.

### <a name="global-options"></a>Globala alternativ

Som standard matar kommandoradsverktyget ut resultatet i läsbart format. Dessutom har verktyget stöd för att mata ut resultatet som JSON, vilket är användbart för automatiseringsscenarier. Om du vill ändra utdata till JSON skickar `--output json` du till något av kommandona nedan.

### <a name="supported-commands"></a>Kommandon som stöds

I följande tabell visas kommandon för några av de vanligaste scenarierna. Kör `mdatp help` från Terminalen för att visa en fullständig lista över kommandon som stöds.

|Grupp                 |Scenario                                                |Kommando                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|Konfiguration         |Aktivera/inaktivera realtidsskydd                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|Konfiguration         |Aktivera/inaktivera beteendeövervakning                         |`mdatp config behavior-monitoring --value [enabled\|disabled]` 
|Konfiguration         |Aktivera/inaktivera molnskydd                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|Konfiguration         |Aktivera/inaktivera produktdiagnostik                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|Konfiguration         |Aktivera/inaktivera automatisk exempelinskickning                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|Konfiguration         |Aktivera/inaktivera AV-passivt läge                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|Konfiguration         |Lägga till/ta bort ett antivirusskydd för ett filnamnstillägg  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|Konfiguration         |Lägga till/ta bort ett antivirusskydd för en fil            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|Konfiguration         |Lägga till/ta bort ett antivirusskydd för en katalog       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|Konfiguration         |Lägga till/ta bort ett antivirusskydd för en process         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|Konfiguration         |Lista alla undantag för antivirus                           |`mdatp exclusion list`                                                 |
|Konfiguration         |Lägga till ett namn på ett hot i listan över tillåtna hot                   |`mdatp threat allowed add --name [threat-name]`                        |
|Konfiguration         |Ta bort ett namn på ett hot från listan över tillåtna hot              |`mdatp threat allowed remove --name [threat-name]`                     |
|Konfiguration         |Lista alla tillåtna hotnamn                           |`mdatp threat allowed list`                                            |
|Konfiguration         |Aktivera PUA-skydd                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|Konfiguration         |Inaktivera PUA-skydd                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|Konfiguration         |Aktivera granskningsläge för PUA-skydd                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|Diagnostik           |Ändra loggnivån                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|Diagnostik           |Generera diagnostikloggar                                |`mdatp diagnostic create --path [directory]`                           |
|Hälsa                |Kontrollera produktens hälsa                              |`mdatp health`                                                         |
|Skydd            |Genomsöka en sökväg                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|Skydd            |Gör en snabbsökning                                         |`mdatp scan quick`                                                     |
|Skydd            |Gör en fullständig genomsökning                                          |`mdatp scan full`                                                      |
|Skydd            |Avbryta en pågående sökning på begäran                        |`mdatp scan cancel`                                                    |
|Skydd            |Begära en säkerhetsintelligensuppdatering                  |`mdatp definitions update`                                             |
|Skyddshistorik    |Skriva ut hela historiken för skydd                       |`mdatp threat list`                                                    |
|Skyddshistorik    |Hämta information om hot                                      |`mdatp threat get --id [threat-id]`                                    |
|Hantering av karantän |Lista alla filer i karantän                              |`mdatp threat quarantine list`                                         |
|Hantering av karantän |Ta bort alla filer från karantän                    |`mdatp threat quarantine remove-all`                                   |
|Hantering av karantän |Lägga till en fil som upptäckts som ett hot i karantänen       |`mdatp threat quarantine add --id [threat-id]`                         |
|Hantering av karantän |Ta bort en fil som upptäckts som ett hot från karantänen  |`mdatp threat quarantine remove --id [threat-id]`                      |
|Hantering av karantän |Återställa en fil från karantän                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|Identifiering och svar av slutpunkt |Ange tidig förhandsgranskning (oanvänd)                    |`mdatp edr early-preview [enable|disable]`                             |
|Identifiering och svar av slutpunkt |Ange grupp-ID                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|Identifiering och svar av slutpunkt |Ange/ta bort tagg, stöds `GROUP` endast        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|Identifiering och svar av slutpunkt |Undantag för listor (rot)                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Information om Microsoft Defender för slutpunktsportalen

I Defender för slutpunktsportalen visas två kategorier med information:

- Antivirusvarningar, inklusive:
  - Allvarlighetsgrad
  - Skanningstyp
  - Enhetsinformation (värdnamn, enhetsidentifierare, klientorganisationsidentifierare, appversion och OS-typ)
  - Filinformation (namn, sökväg, storlek och hash)
  - Hotinformation (namn, typ och delstat)
- Enhetsinformation, inklusive:
  - Enhetsidentifierare
  - Klientorganisationsidentifierare
  - Appversion
  - Hostname
  - OS-typ
  - OS-version
  - Datormodell
  - Processorarkitektur
  - Om enheten är en virtuell dator

### <a name="known-issues"></a>Kända problem

- "Inga sensordata, nedsatt kommunikation" visas på sidan med maskininformation på Microsoft Defender Säkerhetscenter-portalen, trots att produkten fungerar som förväntat. Vi arbetar med att lösa det här problemet.
- Inloggade användare visas inte i Microsoft Defender Säkerhetscenter-portalen.
- Om installationen av *libmic1* misslyckas i SUSE-distributionsfördelningar bör du kontrollera att operativsystemet är registrerat:

   ```bash
   sudo SUSEConnect --status-text
   ```
