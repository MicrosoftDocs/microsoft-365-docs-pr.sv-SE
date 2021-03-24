---
title: Felsöka problem med saknade händelser eller aviseringar för Microsoft Defender ATP för Linux
description: Felsöka problem med saknade händelser eller aviseringar i Microsoft Defender ATP för Linux.
keywords: microsoft, defender, atp, linux, events
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
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e489d5bece292065ad2e82a7eb9011747733b4f6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073745"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-for-linux"></a>Felsöka händelser eller aviseringar som saknas för Microsoft Defender för Endpoint för Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint för Linux](microsoft-defender-endpoint-linux.md)

Den här artikeln innehåller några allmänna steg för att minimera saknade händelser eller varningar i [säkerhetscenterportalen.](https://securitycenter.windows.com/)

När **Microsoft Defender för slutpunkt** har installerats korrekt på en enhet genereras _en_ enhetssida i portalen. Du kan granska alla inspelade händelser på tidslinjefliken på enhetens sida eller på en avancerad sida för sök. Det här avsnittet felsöker eventuella eller alla förväntade händelser saknas.
Till exempel om alla _CreatedFile-händelser_ saknas.

## <a name="missing-network-and-login-events"></a>Nätverks- och inloggningshändelser saknas

Microsoft Defender för Endpoint används ramverk `audit` från linux för att spåra nätverks- och inloggningsaktivitet.

1. Kontrollera att granskningsramverket fungerar.

    ```bash
    service auditd status
    ```

    förväntat utdata:

    ```output
    ● auditd.service - Security Auditing Service
    Loaded: loaded (/usr/lib/systemd/system/auditd.service; enabled; vendor preset: enabled)
    Active: active (running) since Mon 2020-12-21 10:48:02 IST; 2 weeks 0 days ago
        Docs: man:auditd(8)
            https://github.com/linux-audit/audit-documentation
    Process: 16689 ExecStartPost=/sbin/augenrules --load (code=exited, status=1/FAILURE)
    Process: 16665 ExecStart=/sbin/auditd (code=exited, status=0/SUCCESS)
    Main PID: 16666 (auditd)
        Tasks: 25
    CGroup: /system.slice/auditd.service
            ├─16666 /sbin/auditd
            ├─16668 /sbin/audispd
            ├─16670 /usr/sbin/sedispatch
            └─16671 /opt/microsoft/mdatp/sbin/mdatp_audisp_plugin -d
    ```

2. Starta `auditd` om den har markerats som stoppad.

    ```bash
    service auditd start
    ```

**På SLES-system** kan SYSCALL-granskning i `auditd` vara inaktiverad som standard och kan redovisas för saknade händelser.

1. Verifiera att SYSCALL-granskning inte är inaktiverat genom att lista de aktuella granskningsreglerna:

    ```bash
    sudo auditctl -l
    ```

    Om följande rad finns tar du bort den eller redigerar den för att aktivera Microsoft Defender för Endpoint för att spåra specifika SYSCALLs.

    ```output
    -a task, never
    ```

    finns på `/etc/audit/rules.d/audit.rules` .

## <a name="missing-file-events"></a>Filhändelser som saknas

Filhändelser samlas in med `fanotify` framework. Om vissa eller alla filhändelser saknas kontrollerar du att `fanotify` är aktiverat på enheten och att filsystemet [stöds.](microsoft-defender-endpoint-linux.md#system-requirements)

Ange filsystemen på datorn med:

```bash
df -Th
```
