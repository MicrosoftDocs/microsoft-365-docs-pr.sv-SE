---
title: Resurser för Microsoft Defender ATP för Mac
description: Resurser för Microsoft Defender ATP för Mac, inklusive hur du avinstallerar det, hur du samlar in diagnostikloggar, CLI-kommandon och kända problem med produkten.
keywords: microsoft, defender, atp, mac, installation, distribuera, avinstallation, intune, jamf, macos, catalina, mojave, high sierra
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 336f85b41884a441d0967c7f242b69c4d0e4941f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072153"
---
# <a name="resources-for-microsoft-defender-for-endpoint-for-mac"></a>Resurser för Microsoft Defender för Slutpunkt för Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a>Samla in diagnostikinformation

Om du kan återskapa ett problem ökar du loggningsnivån, kör systemet ett tag och återställer loggningsnivån till standardvärdet.

1. Öka loggningsnivån:

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. Återskapa problemet

3. Kör `sudo mdatp diagnostic create` för att backa Microsoft Defender för slutpunktsloggar. Filerna lagras i ett ZIP-arkiv. Det här kommandot skriver också ut filsökvägen till säkerhetskopian när åtgärden har lyckats.

   > [!TIP]
   > Som standard sparas diagnostikloggar i `/Library/Application Support/Microsoft/Defender/wdavdiag/` . Om du vill ändra katalogen där diagnostikloggar sparas skickar du `--path [directory]` till kommandot nedan och `[directory]` ersätter med önskad katalog.

   ```bash
   sudo mdatp diagnostic create
   ```
   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. Återställa loggningsnivån:

   ```bash
   mdatp log level set --level info
   ```
   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a>Loggningsinstallationsproblem

Om ett fel uppstår under installationen rapporterar installationsprogrammet bara ett allmänt fel.

Den detaljerade loggen sparas i `/Library/Logs/Microsoft/mdatp/install.log` . Om du upplever problem under installationen kan du skicka den här filen till oss så att vi kan hjälpa till att diagnostisera orsaken.

## <a name="uninstalling"></a>Avinstallera

Det finns flera sätt att avinstallera Microsoft Defender för Endpoint för Mac. Observera att även om det finns centralt hanterad avinstallation på JAMF är det ännu inte tillgängligt för Microsoft Intune.

### <a name="interactive-uninstallation"></a>Interaktiv avinstallation

- Öppna **Finder > Program**. Högerklicka på **Microsoft Defender ATP-> flytta till papperskorgen**.

### <a name="from-the-command-line"></a>Från kommandoraden

- ```sudo rm -rf '/Applications/Microsoft Defender ATP.app'```
- ```sudo rm -rf '/Library/Application Support/Microsoft/Defender/'```

## <a name="configuring-from-the-command-line"></a>Konfigurera från kommandoraden

Viktiga uppgifter, som att kontrollera produktinställningar och utlösa skanningar på begäran, kan utföras från kommandoraden:

|Grupp        |Scenario                                   |Kommando                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|Konfiguration|Aktivera/inaktivera realtidsskydd           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|Konfiguration|Aktivera/inaktivera molnskydd               |`mdatp config cloud --value [enabled/disabled]`                                   |
|Konfiguration|Aktivera/inaktivera produktdiagnostik            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|Konfiguration|Aktivera/inaktivera automatisk exempelinskickning    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|Konfiguration|Lägga till ett namn på ett hot i listan över tillåtna hot      |`mdatp threat allowed add --name [threat-name]`                                   |
|Konfiguration|Ta bort ett namn på ett hot från listan över tillåtna hot |`mdatp threat allowed remove --name [threat-name]`                                |
|Konfiguration|Lista alla tillåtna hotnamn              |`mdatp threat allowed list`                                                       |
|Konfiguration|Aktivera PUA-skydd                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|Konfiguration|Inaktivera PUA-skydd                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|Konfiguration|Aktivera granskningsläge för PUA-skydd      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|Konfiguration|Aktivera/inaktivera passivläge                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|Diagnostik  |Ändra loggnivån                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|Diagnostik  |Generera diagnostikloggar                   |`mdatp diagnostic create --path [directory]`                                      |
|Hälsa       |Kontrollera produktens hälsa                 |`mdatp health`                                                                    |
|Hälsa       |Söka efter ett spefic produktattribut       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|Skydd   |Genomsöka en sökväg                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|Skydd   |Gör en snabbsökning                            |`mdatp scan quick`                                                                |
|Skydd   |Gör en fullständig genomsökning                             |`mdatp scan full`                                                                 |
|Skydd   |Avbryta en pågående sökning på begäran           |`mdatp scan cancel`                                                               |
|Skydd   |Begära en säkerhetsintelligensuppdatering     |`mdatp definitions update`                                                        |
|EDR          |Lägg till grupptagg till enhet. EDR-taggar används för att hantera enhetsgrupper. Mer information finns på https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups |`mdatp edr tag set --name GROUP --value [name]` |
|EDR          |Ta bort grupptagg från enhet               |`mdatp edr tag remove --tag-name [name]`                                          |
|EDR          |Lägg till grupp-ID                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a>Så här aktiverar du Komplettera automatiskt

Du aktiverar Komplettera automatiskt i bash genom att köra följande kommando och starta om Terminal-sessionen:

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

Så här aktiverar du Komplettera automatiskt i zsh:

- Kontrollera om Komplettera automatiskt är aktiverat på enheten:

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- Om föregående kommando inte ger några utdata kan du aktivera Komplettera automatiskt med följande kommando:

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- Kör följande kommandon för att aktivera automatisk komplettering för Microsoft Defender för Slutpunkt för Mac och starta om terminalsessionen:

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a>Klientkatalogen Microsoft Defender för karantän för slutpunkt

`/Library/Application Support/Microsoft/Defender/quarantine/` innehåller de filer som har satts i karantän av `mdatp` . Filerna namnges efter hotspårnings-ID:t. De aktuella uppföljningsid:erna visas med `mdatp threat list` .

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Information om Microsoft Defender för slutpunktsportalen

[Nu har EDR-funktioner](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)för macOS anlänt – på Microsoft Defender för Endpoint-bloggen – detaljerade anvisningar om vad du kan förvänta dig i Microsoft Defender för Endpoint Security Center.
