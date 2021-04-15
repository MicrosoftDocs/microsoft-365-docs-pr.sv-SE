---
title: Köra och anpassa genomsökningar på begäran i Microsoft Defender AV
description: Köra och konfigurera genomsökningar på begäran med Hjälp av PowerShell, Windows Management Instrumentation eller individuellt på slutpunkter med Windows-säkerhetsappen
keywords: skanna, på begäran, dos, intune, snabbsökning
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 976531e1b7e1b87c4cd2dd2af66f294f68c5d4f1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764405"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a>Konfigurera och köra genomsökningar för Microsoft Defender Antivirus på begäran

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan köra en sökning på begäran på enskilda slutpunkter. Dessa genomsökningar startar omedelbart och du kan definiera parametrar för skanningen, till exempel plats eller typ.

## <a name="quick-scan-versus-full-scan"></a>Snabbsökning jämfört med fullständig sökning

Snabbsökning söker igenom alla platser där skadlig programvara kan registreras för att börja med systemet, till exempel registernycklar och kända startmappar i Windows.

> [!IMPORTANT]
> Microsoft Defender Antivirus körs i kontexten för [LocalSystem-kontot](/windows/win32/services/localsystem-account) när du gör en lokal genomsökning. För nätverkssökningar används enhetskontots kontext. Om domänenhetskontot inte har tillräcklig behörighet för att komma åt resursen fungerar inte genomsökningen. Kontrollera att enheten har behörigheter till den åtkomstnätverksresurs som används.

I [](configure-real-time-protection-microsoft-defender-antivirus.md)kombination med ständigt realtidsskydd – som granskar filer när de öppnas och stängs, och när en användare navigerar till en mapp – ger en snabb genomsökning stark täckning både för skadlig programvara som börjar med systemet och kernel-nivå-skadlig programvara.  

I de flesta fall är en snabb genomsökning lämplig för att hitta skadlig programvara som inte hämtades med realtidsskydd.

En fullständig genomsökning kan vara användbar på slutpunkter som har rapporterat ett hot mot skadlig programvara. Genomsökningen kan identifiera om det finns inaktiva komponenter som kräver en mer omfattande rensning. Det här är bra om din organisation kör genomsökningar på begäran.

> [!NOTE]
> Som standard körs snabbsökningar påmonterade flyttbara enheter, till exempel USB-enheter.

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a>Använda Microsoft Endpoint Manager för att köra en genomsökning

1. Gå till administrationscentret för Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.
2. Välj **Endpoint Security**  >  **Antivirus**.
3. I listan med flikar väljer du **Slutpunkter som inte är fel i Windows 10**.
4. I listan med åtgärder väljer du **Snabbsökning eller** **Fullständig sökning.**

[![BILD ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)

> [!TIP]
> Mer information om hur du använder Microsoft Endpoint Manager för att köra en genomsökning finns i Åtgärder mot skadlig programvara och brandvägg: Så här gör du [en sökning på begäran.](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a>Använd mpcmdrun.exe för att köra en genomsökning

Använd följande `-scan` parameter:

```console
mpcmdrun.exe -scan -scantype 1
```

Mer information om hur du använder verktyget och ytterligare parametrar, t.ex. hur du startar en fullständig genomsökning eller definierar sökvägar, finns i Använda kommandoradsverktyget mpcmdrun.exe för att konfigurera och hantera [Microsoft Defender Antivirus.](command-line-arguments-microsoft-defender-antivirus.md)

## <a name="use-microsoft-intune-to-run-a-scan"></a>Använda Microsoft Intune för att köra en genomsökning

1. Gå till administrationscentret för Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) och logga in.
2. I sidofältet väljer du **Enheter > Alla enheter och** väljer den enhet du vill skanna.
3. Välj **... Mer**. Välj Snabbsökning eller **Fullständig sökning bland** **alternativen.**

## <a name="use-the-windows-security-app-to-run-a-scan"></a>Använda appen Windows-säkerhet för att köra en genomsökning

Se [Köra en genomsökning i Windows-säkerhetsappen](microsoft-defender-security-center-antivirus.md) för anvisningar om hur du kör en genomsökning av enskilda slutpunkter.

## <a name="use-powershell-cmdlets-to-run-a-scan"></a>Använda PowerShell-cmdlets för att köra en genomsökning

Använd följande cmdlet:

```PowerShell
Start-MpScan
```

Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Använda [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) för att konfigurera och köra [cmdlets](/powershell/module/defender/)för Microsoft Defender Antivirus och Defender.

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a>Använd WMI (Windows Management Instruction) för att köra en genomsökning

Använd [ **metoden Start** för](/previous-versions/windows/desktop/defender/start-msft-mpscan) MSFT_MpScan klassen. 

Mer information om vilka parametrar som tillåts finns i [API:er för Windows Defender WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="related-articles"></a>Relaterade artiklar

- [Konfigurera sökalternativ för Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Konfigurera schemalagda genomsökningar för Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)