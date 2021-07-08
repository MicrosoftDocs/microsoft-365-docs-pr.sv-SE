---
title: Microsoft Defender Antivirus
description: Lär dig att hantera, konfigurera och använda Microsoft Defender Antivirus, inbyggt skydd mot skadlig programvara och antivirusskydd.
keywords: Microsoft Defender Antivirus, windows defender, skydd mot skadlig kod, scep, system center endpoint protection, system center configuration manager, virus, skadlig programvara, hot, identifiering, skydd, säkerhet
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: ceaf694d8b81e6b06ffe74efc4ad3d4d73471752
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323050"
---
# <a name="microsoft-defender-antivirus-in-windows"></a>Microsoft Defender Antivirus i Windows

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus är en viktig komponent i nästa generations skydd i Microsoft Defender för Endpoint. Det här skyddet sammanför maskininlärning, stordataanalys, djupgående forskning om hotresistens och Microsofts molninfrastruktur för att skydda enheter (eller slutpunkter) i din organisation. Microsoft Defender Antivirus är inbyggt i Windows och fungerar med Microsoft Defender för Endpoint för att ge skydd på din enhet och i molnet. 

## <a name="compatibility-with-other-antivirus-products"></a>Kompatibilitet med andra antivirusprodukter

Om du använder en antivirusprodukt som inte kommer från Microsoft på enheten kan du eventuellt köra Microsoft Defender Antivirus i passivt läge tillsammans med antiviruslösningen som inte kommer från Microsoft. Det beror på vilket operativsystem som används och om enheten är registrerad på Defender för Endpoint. Mer information finns i [Kompatibilitet för Microsoft Defender Antivirus](microsoft-defender-antivirus-compatibility.md).

## <a name="comparing-active-mode-passive-mode-and-disabled-mode"></a>Jämföra aktivt läge, passivt läge och inaktiverat läge

I följande tabell beskrivs vad du kan förvänta dig när Microsoft Defender Antivirus är i aktivt läge, passivt läge eller inaktiverat.

| Mode  | Vad som händer  |
|---------|---------|
| Aktivt läge | I aktivt läge används Microsoft Defender Antivirus som den primära antivirusappen på enheten. Filer genomsöks, hot åtgärdas och identifierade hot visas i organisationens säkerhetsrapporter och i din app Windows-säkerhet. |
| Passivt läge | I passivt läge används inte Microsoft Defender Antivirus som den primära antivirusappen på enheten. Filer genomsöks och identifierade hot rapporteras, men hot åtgärdas inte av Microsoft Defender Antivirus.   |
| Inaktiverad eller avinstallerad  | När Microsoft Defender Antivirus inaktiveras eller avinstalleras används den inte. Filer genomsöks inte och hot åtgärdas inte. I allmänhet rekommenderar vi inte att du inaktiverar eller avinstallerar Microsoft Defender Antivirus.  |

Mer information finns i [Kompatibilitet för Microsoft Defender Antivirus](microsoft-defender-antivirus-compatibility.md).

## <a name="check-the-state-of-microsoft-defender-antivirus-on-your-device"></a>Kontrollera tillståndet för Microsoft Defender Antivirus på enheten

Om du vill kontrollera tillståndet för Microsoft Defender Antivirus på enheten kan du använda en av flera metoder, till exempel appen Windows-säkerhet eller Windows PowerShell.

### <a name="use-the-windows-security-app-to-check-status-of-microsoft-defender-antivirus"></a>Använd appen Windows-säkerhet för att kontrollera status för Microsoft Defender Antivirus

1. Välj Start-menyn på din Windows-enhet och börja skriva `Security`. Öppna sedan appen Windows-säkerhet i resultaten.

2. Välj **Skydd mot virus och hot**.

3. Under **Inställningar för skydd mot virus och hot** väljer du **Hantera inställningar**.

Namnet på din antiviruslösning visas på inställningssidan.

### <a name="use-powershell-to-check-status-of-microsoft-defender-antivirus"></a>Använd PowerShell för att kontrollera status för Microsoft Defender Antivirus

1. Välj Start-menyn och börja skriva `PowerShell`. Öppna sedan Windows PowerShell i resultaten.

2. Skriv `Get-MpComputerStatus`.

3. I resultatlistan tittar du på raden **AMRunningMode**.

   - **Normal** innebär att Microsoft Defender Antivirus körs i aktivt läge.
   - **Passivt läge** innebär att Microsoft Defender Antivirus körs, men är inte den primära antivirusprodukten på enheten.
   - **EDR-blockeringsläge** innebär att Microsoft Defender Antivirus körs och en funktion i Microsoft Defender för Endpoint som kallas "EDR i blockeringsläge" är aktiverad. (Gå till [Identifiering och åtgärd på slutpunkt (EDR) i blockeringsläge](edr-in-block-mode.md).)
   - **Passivt SxS-läge** innebär att Microsoft Defender Antivirus körs i passivt läge tillsammans med ett annat antivirusprogram och att enheten inte har registrerats i Microsoft Defender för Endpoint. I det här fallet används begränsad regelbunden genomsökning för Microsoft Defender Antivirus. Mer information finns i [Använda begränsad regelbunden genomsökning i Microsoft Defender Antivirus](limited-periodic-scanning-microsoft-defender-antivirus.md).

Mer information om PowerShell-cmdleten Get-MpComputerStatus finns i referensartikeln [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).

## <a name="get-your-antivirusantimalware-platform-updates"></a>Hämta uppdateringar för plattformen för antivirusprogrammet

Det är viktigt att hålla Microsoft Defender Antivirus eller annat antivirusprogram uppdaterade. Microsoft släpper regelbundna uppdateringar för att säkerställa att dina enheter har den senaste tekniken för att skydda mot ny skadlig kod och attacktekniker. Mer information finns i [Hantera uppdateringar för Microsoft Defender Antivirus och tillämpa baslinjer](manage-updates-baselines-microsoft-defender-antivirus.md). 

## <a name="see-also"></a>Mer information finns även i

- [Microsoft Defender Antivirus på Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [Hantering och konfiguration av Microsoft Defender Antivirus](configuration-management-reference-microsoft-defender-antivirus.md)
- [Utvärdera Microsoft Defender Antivirus skydd](evaluate-microsoft-defender-antivirus.md)
