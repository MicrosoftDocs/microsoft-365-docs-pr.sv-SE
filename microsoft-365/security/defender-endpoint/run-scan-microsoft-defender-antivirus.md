---
title: Köra och anpassa genomsökningar på begäran i Microsoft Defender Antivirus
description: Köra och konfigurera genomsökningar på begäran med PowerShell, Windows Management Instrumentation eller individuellt på slutpunkter med Windows-säkerhet-appen
keywords: skanna, på begäran, dos, intune, snabbsökning
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 3ee37d7220527c9032b630e02258c684b6c860b3
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878814"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Konfigurera och kör genomsökningar på begäran för Microsoft Defender Antivirus

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan köra en sökning på begäran på enskilda slutpunkter. Dessa genomsökningar startar omedelbart och du kan definiera parametrar för skanningen, till exempel plats eller typ. När du kör en genomsökning kan du välja mellan tre typer: Snabbsökning, fullständig sökning och anpassad sökning. Använd i de flesta fall en snabbsökning. En snabb genomsökning av alla platser där skadlig programvara kan registreras för att börja med systemet, till exempel registernycklar och kända Windows startmappar. 

I kombination med ständigt realtidsskydd som granskar filer när de öppnas och stängs, och när en användare navigerar till en mapp ger en snabb genomsökning ett starkt skydd mot skadlig programvara som börjar med system- och kernel-nivå-skadlig programvara. I de flesta fall är en snabbsökning tillräcklig och är det rekommenderade alternativet för schemalagda skanningar eller sökningar på begäran.  [Läs mer om genomsökningstyper](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan).

> [!IMPORTANT]
> Microsoft Defender Antivirus körs i kontexten för [LocalSystem-kontot](/windows/win32/services/localsystem-account) när du utför en lokal genomsökning. För nätverkssökningar används enhetskontots kontext. Om domänenhetskontot inte har tillräcklig behörighet för att komma åt resursen fungerar inte genomsökningen. Kontrollera att enheten har behörigheter till den åtkomstnätverksresurs som används.

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Använda Microsoft Endpoint Manager för att köra en sökning

1. Gå till Microsoft Endpoint Manager administrationscenter ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.

2. Välj **Endpoint Security**  >  **Antivirus**.

3. I listan över flikar väljer du Windows 10 **slutpunkter som inte är fel**.

4. I listan med åtgärder väljer du **Snabbsökning** (rekommenderas) eller **Fullständig sökning**.

[![BILD ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> Mer information om hur du använder Microsoft Endpoint Manager att köra en genomsökning finns i Program mot skadlig programvara och [brandväggsåtgärder:](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)Så här gör du en sökning på begäran.

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>Använd mpcmdrun.exe för att köra en genomsökning

Använd följande `-scan` parameter:

```console
mpcmdrun.exe -scan -scantype 1
```

Mer information om hur du använder verktyget och ytterligare parametrar, inklusive hur du påbörjar en fullständig genomsökning eller definierar sökvägar, finns i använda kommandoradsverktyget mpcmdrun.exe för att konfigurera och hantera [Microsoft Defender Antivirus.](command-line-arguments-microsoft-defender-antivirus.md)

## <a name="use-microsoft-intune-to-run-a-scan"></a>Använda Microsoft Intune för att köra en sökning

1. Gå till Microsoft Endpoint Manager administrationscenter ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.

2. I sidofältet väljer du **Enheter**  >  **alla enheter** och väljer den enhet du vill skanna.

3. Välj **... Mer**. Välj Snabbsökning **(rekommenderas) eller** Fullständig sökning bland **alternativen.**

## <a name="use-the-windows-security-app-to-run-a-scan"></a>Använd appen Windows-säkerhet för att köra en genomsökning

Se [Köra en genomsökning i Windows-säkerhet-appen](microsoft-defender-security-center-antivirus.md) för anvisningar om hur du kör en genomsökning av enskilda slutpunkter.

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>Använda PowerShell-cmdlets för att köra en genomsökning

Använd följande cmdlet:

```PowerShell
Start-MpScan
```

Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra Microsoft Defender Antivirus- och [Defender-cmdlets.](/powershell/module/defender/)

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>Använd Windows Instruktionerna för hantering (WMI) för att köra en genomsökning

Använd [ **metoden Start** för](/previous-versions/windows/desktop/defender/start-msft-mpscan) MSFT_MpScan klassen. 

Mer information om vilka parametrar som tillåts finns i Windows Defender [WMIv2-API:er](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

