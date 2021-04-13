---
title: Konfigurera skanningsalternativ för Microsoft Defender AV
description: Du kan konfigurera Microsoft Defender AV för att söka igenom lagringsfiler för e-post, kopierings- eller omparseringspunkter, nätverksfiler och arkiverade filer (till exempel ZIP-filer).
keywords: avancerade skanningar, skanning, e-post, arkiv, zip, rar, arkivera, skanna igen
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 625c84e79efe53cae2bc8f511726ad3f384ea505
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691067"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Konfigurera sökalternativ för Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Använda Microsoft Intune för att konfigurera skanningsalternativ

Mer information finns i Konfigurera inställningar för enhetsbegränsningar i [Microsoft Intune](/intune/device-restrictions-configure) och Microsoft Defender Antivirus för [Windows 10 i Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Använda Microsoft Endpoint Manager för att konfigurera skanningsalternativ

Se [Skapa och distribuera principer för program mot skadlig programvara: Genomsökningsinställningar för](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) information om hur du konfigurerar Microsoft Endpoint Manager (current branch).

## <a name="use-group-policy-to-configure-scanning-options"></a>Konfigurera genomsökningsalternativ med grupprinciper

Så här konfigurerar du grupprincipinställningarna som beskrivs i följande tabell:

1. På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. I **redigeraren för grupprinciphantering går** du till **Datorkonfiguration och** klickar på **Administrativa mallar**.

3. Expandera trädet till **Windows-komponenter > Microsoft Defender Antivirus** och sedan den **plats** som anges i tabellen nedan.

4. Dubbelklicka på den **principinställning** som anges i tabellen nedan och ange önskat alternativ. Klicka **på OK** och upprepa för alla andra inställningar.

Beskrivning | Plats och inställning | Standardinställning (om den inte konfigurerats) | `Set-MpPreference`PowerShell-parameter eller WMI-egenskap för `MSFT_MpPreference` klass
---|---|---|---
E-postskanning Se [begränsningar av e-postskanning](#ref1)| Skanna > Aktivera genomsökning av e-post | Inaktiverad | `-DisableEmailScanning`
Skanna [genom att göra genomläsningspunkter](/windows/win32/fileio/reparse-points) | Skanna > Aktivera skanning avparsningspunkt | Inaktiverad | Kan inte användas
Skanna mappade nätverksenheter | Skanna > kör fullständig sökning på mappade nätverksenheter | Inaktiverad | `-DisableScanningMappedNetworkDrivesForFullScan`
 Skanna arkivfiler (till exempel .zip- eller .rar-filer). [Undantagslistan för tillägg](configure-extension-file-exclusions-microsoft-defender-antivirus.md) har företräde framför den här inställningen. | Skanna > arkivfiler | Aktiverad | `-DisableArchiveScanning`
Genomsöka filer i nätverket | Skanna > genomsöka nätverksfiler | Inaktiverad | `-DisableScanningNetworkFiles`
Skanna packade körbara filer | Skanna > fullpackade körbara filer | Aktiverad | Kan inte användas
Sök efter flyttbara enheter endast vid fullständiga skanningar | Skanna > flyttbara enheter med Skanna | Inaktiverad | `-DisableRemovableDriveScanning`
Ange nivån för undermappar i en arkivmapp som ska genomsökas | Skanna > Ange maximalt djup för att söka igenom arkivfiler | 0 | Kan inte användas
 Ange maximal processorbelastning (i procent) under en genomsökning. Obs! Det här är inte en fast gräns, utan snarare en vägledning för att sökmotorn inte ska överskrida det här maxvärdet i genomsnitt. | Sökning > Ange den högsta procentandelen processorutnyttjande vid en genomsökning | 50 |  `-ScanAvgCPULoadFactor`
 Ange den maximala storleken (i kilobyte) för arkivfiler som ska skannas. Standardvärdet **(0)** gäller ingen gräns | Skanna > Ange den maximala storleken på arkivfilerna som ska genomsökas | Ingen gräns | Kan inte användas
 Konfigurera låg CPU-prioritet för schemalagda genomsökningar | Skanna > Konfigurera låg CPU-prioritet för schemalagda genomsökningar | Inaktiverad | Kan inte användas
 
> [!NOTE]
> Om realtidsskydd är aktiverat genomsöks filer innan de används och körs. Skanningsomfånget inkluderar alla filer, inklusive filer påmonterade flyttbara media, t.ex. USB-enheter. Om enheten som utför genomsökningen har realtidsskydd eller skydd vid åtkomst aktiverat inkluderar genomsökningen även nätverksresurser.

## <a name="use-powershell-to-configure-scanning-options"></a>Använda PowerShell för att konfigurera skanningsalternativ

Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i Hantera Microsoft Defender Antivirus med [PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) och [Defender-cmdlets.](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a>Använda WMI för att konfigurera skanningsalternativ

Information om hur du använder WMI-klasser finns [i Windows Defender WMIv2 API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="ref1"></a>

## <a name="email-scanning-limitations"></a>Begränsningar av e-postskanning

Genomsökning av e-post möjliggör genomsökning av e-postfiler som används av Outlook och andra e-postklienter vid sökning på begäran och schemalagda genomsökningar. Inbäddade objekt i en e-postfil (t.ex. bifogade filer och arkiverade filer) skannas också. Du kan skanna och åtgärda följande filformat:

- DBX
- MBX
- MIME

PST-filer som används av Outlook 2003 eller äldre (där arkivtypen är inställd på icke-unicode) genomsöks också, men Windows Defender kan inte åtgärda hot som upptäckts i PST-filer.

Om Microsoft Defender Antivirus identifierar ett hot i ett e-postmeddelande visas följande information som hjälper dig att identifiera det komprometterade e-postmeddelandet, så att du kan åtgärda risken manuellt:

- Ämne för e-post
- Namn på bifogad fil

## <a name="related-topics"></a>Relaterade ämnen

- [Anpassa, initiera och granska resultatet av genomsökningar och åtgärder i Microsoft Defender Antivirus](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Konfigurera och köra genomsökningar för Microsoft Defender Antivirus på begäran](run-scan-microsoft-defender-antivirus.md)
- [Konfigurera schemalagda genomsökningar för Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)