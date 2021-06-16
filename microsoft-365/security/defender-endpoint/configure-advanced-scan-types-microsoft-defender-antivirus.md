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
ms.date: 05/26/2021
ms.topic: how-to
ms.openlocfilehash: 96e4dab96f8ceb149916c908991079bb2dfa866f
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964903"
---
# <a name="configure-microsoft-defender-antivirus-scanning-options"></a>Konfigurera alternativ för genomsökning i Microsoft Defender Antivirus

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="use-microsoft-intune-to-configure-scanning-options"></a>Använda Microsoft Intune för att konfigurera skanningsalternativ

Mer information finns i [Konfigurera inställningar för](/intune/device-restrictions-configure) enhetsbegränsningar i Microsoft Intune och Microsoft Defender Antivirus för enhetsbegränsningar för Windows 10 i [Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus). 

## <a name="use-microsoft-endpoint-manager-to-configure-scanning-options"></a>Använda Microsoft Endpoint Manager för att konfigurera skanningsalternativ

Mer information om konfigurering av Microsoft Endpoint Manager (current branch) finns i Skapa och distribuera principer för program mot skadlig [programvara: Genomsökningsinställningar](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scan-settings).

## <a name="use-group-policy-to-configure-scanning-options"></a>Konfigurera genomsökningsalternativ med grupprinciper

1. Öppna [Konsolen för grupprinciphantering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)) på datorn för grupprinciphantering.

2. Högerklicka på det grupprincipobjekt du vill konfigurera och välj sedan **Redigera**.

3. I **redigeraren för grupprinciphantering går** du till **Datorkonfiguration och** klickar på **Administrativa mallar**.

4. Expandera trädet till **Windows komponenter** Microsoft Defender Antivirus och välj sedan en plats (referera till  >  Inställningar och [platser](#settings-and-locations) i den här artikeln).


5. Redigera principobjektet. 

6. Klicka **på OK** och upprepa för alla andra inställningar.

### <a name="settings-and-locations"></a>Inställningar och platser

| Principobjekt och plats | Standardinställning (om den inte konfigurerats) | `Set-MpPreference`PowerShell-parameter eller WMI-egenskap för `MSFT_MpPreference` klass |
|---|---|---|
| Skanning av e-post <p> **Skanna**  >  **Aktivera genomsökning av e-post**<p>Se Begränsningar [av e-postskanning](#email-scanning-limitations) (i den här artikeln) | Inaktiverad | `-DisableEmailScanning` |
|Skanna [genom att göra genomläsningspunkter](/windows/win32/fileio/reparse-points) <p> **Skanna**  >  **Aktivera genomsökning avparsningspunkt** | Inaktiverad | Kan inte användas <p>Se [Punkter som du kan separera](/windows/win32/fileio/reparse-points)  |
| Skanna mappade nätverksenheter <p> **Skanna**  >  **Kör fullständig sökning på mappade nätverksenheter** | Inaktiverad | `-DisableScanningMappedNetworkDrivesForFullScan`|
| Skanna arkivfiler (till exempel .zip filer .rar filer).  <p> **Skanna**  >  **Skanna arkivfiler** | Aktiverad | `-DisableArchiveScanning` <p>[Undantagslistan för tillägg](configure-extension-file-exclusions-microsoft-defender-antivirus.md) har företräde framför den här inställningen.|
| Genomsöka filer i nätverket <p> **Skanna**  >  **Skanna nätverksfiler** | Inaktiverad | `-DisableScanningNetworkFiles` |
| Skanna packade körbara filer <p> **Skanna**  >  **Skanna packade körbara filer** | Aktiverad | Kan inte användas |
| Sök efter flyttbara enheter endast vid fullständiga skanningar <p> **Skanna**  >  **Skanna flyttbara enheter** | Inaktiverad | `-DisableRemovableDriveScanning` |
| Ange nivån för undermappar i en arkivmapp som ska genomsökas <p>**Skanna**  >  **Ange maximalt djup för att söka igenom arkivfiler** | 0 | Kan inte användas |
| Ange maximal processorbelastning (i procent) under en genomsökning. <p> **Skanna**  >  **Ange maximal procentandel av belastningen på processorerna vid en genomsökning** | 50 |  `-ScanAvgCPULoadFactor` <p>**OBS!** Maxbelastningen på processorerna är inte en svår gräns, men det är bra att se till att sökmotorn inte överskrider det högsta medelvärdet. Genomsökningar som körs manuellt ignorerar den här inställningen och körs utan några CPU-gränser. |
| Ange den maximala storleken (i kilobyte) för arkivfiler som ska skannas. <p> **Skanna**  >  **Ange den maximala storleken på de arkivfiler som ska genomsökas** | Ingen gräns | Kan inte användas <p>Standardvärdet 0 gäller ingen gräns |
| Konfigurera låg CPU-prioritet för schemalagda genomsökningar <p> **Skanna**  >  **Konfigurera låg CPU-prioritet för schemalagda genomsökningar** | Inaktiverad | Kan inte användas |

 
> [!NOTE]
> Om realtidsskydd är aktiverat genomsöks filer innan de används och körs. Skanningsomfånget inkluderar alla filer, inklusive filer påmonterade flyttbara media, t.ex. USB-enheter. Om enheten som utför genomsökningen har realtidsskydd eller skydd vid åtkomst aktiverat inkluderar genomsökningen även nätverksresurser.

## <a name="use-powershell-to-configure-scanning-options"></a>Använda PowerShell för att konfigurera skanningsalternativ


Mer information om hur du använder PowerShell med Microsoft Defender Antivirus finns i

- [Hantera Microsoft Defender Antivirus med PowerShell-cmdlets](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Defender-cmdlets](/powershell/module/defender/)

## <a name="use-wmi-to-configure-scanning-options"></a>Använda WMI för att konfigurera skanningsalternativ

Se [Windows Defender WMIv2-API:er](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).

## <a name="email-scanning-limitations"></a>Begränsningar av e-postskanning

Genomsökning av e-post möjliggör genomsökning av e-postfiler som Outlook och andra e-postklienter vid sökning på begäran och schemalagda genomsökningar. Inbäddade objekt i e-post (t.ex. bifogade filer och arkiverade filer) skannas också. Du kan skanna och åtgärda följande filformat:

- DBX
- MBX
- MIME

PST-filer som används av Outlook 2003 eller äldre (där arkivtypen är inställd på icke-unicode) genomsöks också, men Microsoft Defender Antivirus kan inte åtgärda hot som identifieras i PST-filer.

Om Microsoft Defender Antivirus upptäcker ett hot i ett e-postmeddelande visas följande information som hjälper dig att identifiera det komprometterade e-postmeddelandet, så att du kan åtgärda risken manuellt:

- Ämne för e-post
- Namn på bifogad fil


## <a name="scanning-mapped-network-drives"></a>Skanna mappade nätverksenheter

I alla operativsystem skannas endast de nätverksenheter som mappas på systemnivå. Mappade nätverksenheter på användarnivå genomsöks inte. Mappade nätverksenheter på användarnivå är de enheter som en användare mappar i sessionen manuellt och med sina egna autentiseringsuppgifter.

## <a name="see-also"></a>Se även


- [Anpassa, initiera och granska resultaten av Microsoft Defender Antivirus genomsökningar och åtgärder](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Konfigurera och kör genomsökningar på begäran för Microsoft Defender Antivirus](run-scan-microsoft-defender-antivirus.md)
- [Konfigurera schemalagda Microsoft Defender Antivirus genomsökningar](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
