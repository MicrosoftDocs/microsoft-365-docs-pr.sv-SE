---
title: Konfigurera skanningsalternativ för Microsoft Defender Antivirus
description: Du kan konfigurera Microsoft Defender AV för att söka igenom lagringsfiler för e-post, back-up eller omparse-punkter, nätverksfiler och arkiverade filer (till exempel .zip filer).
keywords: avancerade skanningar, skanning, e-post, arkiv, zip, rar, arkivera, skanna igen
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 1efa72d5b8d204b6aec1cef05fe3c8afe1ca82f7
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275316"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Konfigurera alternativ för genomsökning i Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Använda Microsoft Intune för att konfigurera skanningsalternativ

Mer [information finns i Konfigurera inställningar Microsoft Intune](/intune/device-restrictions-configure) enhet Microsoft Defender Antivirus enhetbegränsningar för Windows 10 i [Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Använda Microsoft Endpoint Manager för att konfigurera skanningsalternativ

Se [Skapa och distribuera principer för program mot skadlig programvara: Genomsökningsinställningar](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings) för information om konfigurering av Microsoft Endpoint Manager (current branch).

## <a name="use-group-policy-to-configure-scanning-options"></a>Konfigurera genomsökningsalternativ med grupprinciper

Så här konfigurerar du grupprincipinställningarna som beskrivs i följande tabell:

1. På datorn för grupprinciphantering öppnar du [Konsolen för](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))grupprinciphantering, högerklickar på det grupprincipobjekt du vill konfigurera och klickar på **Redigera.**

2. I **redigeraren för grupprinciphantering går** du till **Datorkonfiguration och** klickar på **Administrativa mallar**.

3. Expandera trädet för **att Windows delar > Microsoft Defender Antivirus** och sedan den **Plats** som anges i tabellen nedan.

4. Dubbelklicka på den **principinställning** som anges i tabellen nedan och ange önskat alternativ. Klicka **på OK** och upprepa för alla andra inställningar.

Beskrivning | Plats och inställning | Standardinställning (om den inte konfigurerats) | `Set-MpPreference`PowerShell-parameter eller WMI-egenskap för `MSFT_MpPreference` klass
---|---|---|---
E-postskanning Se [begränsningar av e-postskanning](#ref1)| Skanna > Aktivera genomsökning av e-post | Inaktiverad | `-DisableEmailScanning`
Skanna [genom att göra genomläsningspunkter](/windows/win32/fileio/reparse-points) | Skanna > Aktivera skanning avparsningspunkt | Inaktiverad | Kan inte användas
Skanna mappade nätverksenheter | Skanna > kör fullständig sökning på mappade nätverksenheter | Inaktiverad | `-DisableScanningMappedNetworkDrivesForFullScan`
 Skanna arkivfiler (till exempel .zip filer .rar filer). [Undantagslistan för tillägg](configure-extension-file-exclusions-microsoft-defender-antivirus.md) har företräde framför den här inställningen. | Skanna > arkivfiler | Aktiverad | `-DisableArchiveScanning`
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

Se [Hantera Microsoft Defender Antivirus med PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md) och [Defender-cmdlets för](/powershell/module/defender/) mer information om hur du använder PowerShell med Microsoft Defender Antivirus.

## <a name="use-wmi-to-configure-scanning-options"></a>Använda WMI för att konfigurera skanningsalternativ

Information om hur du använder WMI-klasser [finns Windows Defender WMIv2-API:er.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="ref1"></a>

## <a name="email-scanning-limitations"></a>Begränsningar av e-postskanning

Genomsökning av e-post möjliggör genomsökning av e-postfiler som Outlook och andra e-postklienter vid sökning på begäran och schemalagda genomsökningar. Inbäddade objekt i en e-postfil (t.ex. bifogade filer och arkiverade filer) skannas också. Du kan skanna och åtgärda följande filformat:

- DBX
- MBX
- MIME

PST-filer som används av Outlook 2003 eller äldre (där arkivtypen är inställd på icke-unicode) genomsöks också, men Windows Defender kan inte åtgärda hot som upptäckts i PST-filer.

Om Microsoft Defender Antivirus upptäcker ett hot i ett e-postmeddelande visas följande information som hjälper dig att identifiera det komprometterade e-postmeddelandet, så att du kan åtgärda risken manuellt:

- Ämne för e-post
- Namn på bifogad fil

## <a name="related-topics"></a>Relaterade ämnen

- [Anpassa, initiera och granska resultaten av Microsoft Defender Antivirus genomsökningar och åtgärder](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Konfigurera och kör genomsökningar på begäran för Microsoft Defender Antivirus](run-scan-microsoft-defender-antivirus.md)
- [Konfigurera schemalagda Microsoft Defender Antivirus genomsökningar](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)