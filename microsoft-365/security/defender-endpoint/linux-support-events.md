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
ms.openlocfilehash: 5981cb75b4c835390e27d902b5950e3c68305200
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687460"
---
# <a name="troubleshoot-missing-events-or-alerts-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="c835c-104">Felsöka händelser eller aviseringar som saknas för Microsoft Defender för Slutpunkt i Linux</span><span class="sxs-lookup"><span data-stu-id="c835c-104">Troubleshoot missing events or alerts issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c835c-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="c835c-105">**Applies to:**</span></span>

- [<span data-ttu-id="c835c-106">Microsoft Defender för Endpoint i Linux</span><span class="sxs-lookup"><span data-stu-id="c835c-106">Microsoft Defender for Endpoint on Linux</span></span>](microsoft-defender-endpoint-linux.md)

<span data-ttu-id="c835c-107">Den här artikeln innehåller några allmänna steg för att minimera saknade händelser eller varningar i [säkerhetscenterportalen.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="c835c-107">This article provides some general steps to mitigate missing events or alerts in the [security center](https://securitycenter.windows.com/) portal.</span></span>

<span data-ttu-id="c835c-108">När **Microsoft Defender för slutpunkt** har installerats korrekt på en enhet genereras _en_ enhetssida i portalen.</span><span class="sxs-lookup"><span data-stu-id="c835c-108">Once **Microsoft Defender for Endpoint** has been installed properly on a device, a _device page_ will be generated in the portal.</span></span> <span data-ttu-id="c835c-109">Du kan granska alla inspelade händelser på tidslinjefliken på enhetens sida eller på en avancerad sida för sök.</span><span class="sxs-lookup"><span data-stu-id="c835c-109">You can review all recorded events in the timeline tab in the device page, or in advanced hunting page.</span></span> <span data-ttu-id="c835c-110">Det här avsnittet felsöker eventuella eller alla förväntade händelser saknas.</span><span class="sxs-lookup"><span data-stu-id="c835c-110">This section troubleshoots the case of some or all expected events are missing.</span></span>
<span data-ttu-id="c835c-111">Till exempel om alla _CreatedFile-händelser_ saknas.</span><span class="sxs-lookup"><span data-stu-id="c835c-111">For instance, if all _CreatedFile_ events are missing.</span></span>

## <a name="missing-network-and-login-events"></a><span data-ttu-id="c835c-112">Nätverks- och inloggningshändelser saknas</span><span class="sxs-lookup"><span data-stu-id="c835c-112">Missing network and login events</span></span>

<span data-ttu-id="c835c-113">Microsoft Defender för Endpoint används ramverk `audit` från linux för att spåra nätverks- och inloggningsaktivitet.</span><span class="sxs-lookup"><span data-stu-id="c835c-113">Microsoft Defender for Endpoint utilized `audit` framework from linux to track network and login activity.</span></span>

1. <span data-ttu-id="c835c-114">Kontrollera att granskningsramverket fungerar.</span><span class="sxs-lookup"><span data-stu-id="c835c-114">Make sure audit framework is working.</span></span>

    ```bash
    service auditd status
    ```

    <span data-ttu-id="c835c-115">förväntat utdata:</span><span class="sxs-lookup"><span data-stu-id="c835c-115">expected output:</span></span>

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

2. <span data-ttu-id="c835c-116">Starta `auditd` om den har markerats som stoppad.</span><span class="sxs-lookup"><span data-stu-id="c835c-116">If `auditd` is marked as stopped, start it.</span></span>

    ```bash
    service auditd start
    ```

<span data-ttu-id="c835c-117">**På SLES-system** kan SYSCALL-granskning i `auditd` vara inaktiverad som standard och kan redovisas för saknade händelser.</span><span class="sxs-lookup"><span data-stu-id="c835c-117">**On SLES** systems, SYSCALL auditing in `auditd` might be disabled by default and can be accounted for missing events.</span></span>

1. <span data-ttu-id="c835c-118">Verifiera att SYSCALL-granskning inte är inaktiverat genom att lista de aktuella granskningsreglerna:</span><span class="sxs-lookup"><span data-stu-id="c835c-118">To validate that SYSCALL auditing is not disabled, list the current audit rules:</span></span>

    ```bash
    sudo auditctl -l
    ```

    <span data-ttu-id="c835c-119">Om följande rad finns tar du bort den eller redigerar den för att aktivera Microsoft Defender för Endpoint för att spåra specifika SYSCALLs.</span><span class="sxs-lookup"><span data-stu-id="c835c-119">if the following line is present, remove it or edit it to enable Microsoft Defender for Endpoint to track specific SYSCALLs.</span></span>

    ```output
    -a task, never
    ```

    <span data-ttu-id="c835c-120">finns på `/etc/audit/rules.d/audit.rules` .</span><span class="sxs-lookup"><span data-stu-id="c835c-120">audit rules are located at `/etc/audit/rules.d/audit.rules`.</span></span>

## <a name="missing-file-events"></a><span data-ttu-id="c835c-121">Filhändelser som saknas</span><span class="sxs-lookup"><span data-stu-id="c835c-121">Missing file events</span></span>

<span data-ttu-id="c835c-122">Filhändelser samlas in med `fanotify` framework.</span><span class="sxs-lookup"><span data-stu-id="c835c-122">File events are collected with `fanotify` framework.</span></span> <span data-ttu-id="c835c-123">Om vissa eller alla filhändelser saknas kontrollerar du att `fanotify` är aktiverat på enheten och att filsystemet [stöds.](microsoft-defender-endpoint-linux.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="c835c-123">In case some or all file events are missing, make sure `fanotify` is enabled on the device and that the file system is [supported](microsoft-defender-endpoint-linux.md#system-requirements).</span></span>

<span data-ttu-id="c835c-124">Ange filsystemen på datorn med:</span><span class="sxs-lookup"><span data-stu-id="c835c-124">List the filesystems on the machine with:</span></span>

```bash
df -Th
```
