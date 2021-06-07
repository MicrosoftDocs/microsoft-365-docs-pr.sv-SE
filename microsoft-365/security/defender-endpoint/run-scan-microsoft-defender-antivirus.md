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
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: fdca059633ab0993e07b5b1be0c6f33cfe327fcf
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789177"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Konfigurera och kör genomsökningar på begäran för Microsoft Defender Antivirus

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan köra en sökning på begäran på enskilda slutpunkter. Dessa genomsökningar startar omedelbart och du kan definiera parametrar för skanningen, till exempel plats eller typ.

## <a name="quick-scan-versus-full-scan"></a>Snabbsökning jämfört med fullständig sökning

Snabbsökning söker igenom alla platser där skadlig programvara kan registreras för att börja med systemet, till exempel registernycklar och kända Windows startmappar.

> [!IMPORTANT]
> Microsoft Defender Antivirus körs i kontexten för [LocalSystem-kontot](/windows/win32/services/localsystem-account) när du utför en lokal genomsökning. För nätverkssökningar används enhetskontots kontext. Om domänenhetskontot inte har tillräcklig behörighet för att komma åt resursen fungerar inte genomsökningen. Kontrollera att enheten har behörigheter till den åtkomstnätverksresurs som används.

I kombination [med ständigt realtidsskydd](configure-real-time-protection-microsoft-defender-antivirus.md)ger en snabb genomsökning bra täckning både för skadlig programvara som börjar med system- och kernel-nivå-skadlig programvara. Skydd i realtid granskar alltid filer när de öppnas och stängs, och när en användare navigerar till en mapp. Som standard körs snabbsökningar påmonterade flyttbara enheter, till exempel USB-enheter. I de flesta fall är en snabb genomsökning lämplig för att hitta skadlig programvara som inte hämtades med realtidsskydd.

En fullständig genomsökning kan vara användbar när ett skadlig kodhot rapporteras på en slutpunkt. Sökningen kan identifiera om det finns inaktiva komponenter som kräver en mer omfattande rensning. Microsoft rekommenderar dock att snabbskanningar används i stället för fullständiga skanningar i stället för att göra sökningar i allmänhet. En fullständig genomsökning kan ta några timmar eller dagar att slutföra, beroende på hur mycket och vilken typ av data som behöver skannas. 

> [!TIP]
> Mer information om skillnaderna mellan snabba och fullständiga skanningar finns i Snabbsökning jämfört med [fullständig genomsökning och anpassad sökning.](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan)

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Använda Microsoft Endpoint Manager för att köra en sökning

1. Gå till Microsoft Endpoint Manager administrationscenter ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.
2. Välj **Endpoint Security**  >  **Antivirus**.
3. I listan över flikar väljer du Windows 10 **slutpunkter som inte är fel**.
4. I listan med åtgärder väljer du **Snabbsökning eller** **Fullständig sökning.**

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
2. I sidofältet väljer du **Enheter > Alla enheter och** väljer den enhet du vill skanna.
3. Välj **... Mer**. Välj Snabbsökning eller **Fullständig sökning bland** **alternativen.**

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

## <a name="related-articles"></a>Relaterade artiklar

- [Konfigurera alternativ för genomsökning i Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Konfigurera schemalagda Microsoft Defender Antivirus genomsökningar](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)