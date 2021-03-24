---
title: Felsöka installationsproblem för Microsoft Defender ATP för Mac
description: Felsöka installationsproblem i Microsoft Defender ATP för Mac.
keywords: microsoft, defender, atp, mac, installera
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
ms.openlocfilehash: 60b50f3944a2cdd995b4877e22123018267ff044
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070274"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Felsöka installationsproblem för Microsoft Defender för Slutpunkt för Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Slutpunkt för Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a>Installationen misslyckades

För manuell installation står det "Ett fel inträffade under installationen" på sidan Sammanfattning i installationsguiden. Installationsprogrammet påträffade ett fel som orsakade att installationen misslyckades. Kontakta programvarutillverkaren för att få hjälp." För MDM-distributioner visas det också som ett allmänt installationsfel.

Även om vi inte visar ett exakt fel för slutanvändaren så sparar vi en loggfil med installationsförloppet i `/Library/Logs/Microsoft/mdatp/install.log` . Varje installationssession läggs till i den här loggfilen. Du kan endast `sed` använda följande för att mata ut den senaste installationen:

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

I det här exemplet föregås den faktiska orsaken av `[ERROR]` .
Installationen misslyckades eftersom det inte går att nedgradera mellan dessa versioner.

## <a name="mdatp-install-log-missing-or-not-updated"></a>MDATP-installationslogg saknas eller har inte uppdaterats

I sällsynta fall lämnar installationen ingen spårning i filen /Library/Logs/Microsoft/mdatp/install.log.
Du kan kontrollera att en installation har hänt och analysera möjliga fel genom att fråga macOS-loggar (det här är användbart i MDM-distribution när det inte finns något klientgränssnitt). Vi rekommenderar att du använder ett smalt tidsfönster för att köra en fråga och att du filtrerar efter loggningsprocessens namn eftersom det kommer att finnas en stor mängd information.

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
