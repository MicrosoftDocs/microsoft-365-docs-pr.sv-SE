---
title: Kompatibilitet med Microsoft Defender Antivirus med andra säkerhetsprodukter
description: Vad du kan förvänta dig från Microsoft Defender Antivirus med andra säkerhetsprodukter och de operativsystem som du använder.
keywords: windows defender, nästa generations antivirus, kompatibilitet, passivt läge
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 131b9970572b1034ba5c9907a001f0497d450339
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765449"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Kompatibilitet med Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="overview"></a>Översikt

Microsoft Defender Antivirus aktiveras och installeras automatiskt på slutpunkter och enheter med Windows 10. Men vad händer när en annan antivirus-/antimalware-lösning används? Det beror på om du använder [Microsoft Defender för Endpoint tillsammans](microsoft-defender-endpoint.md) med ditt antivirusprogram.
- Om din organisations slutpunkter och enheter är skyddade med en lösning som inte är en Microsoft-antivirus-/antimalware-lösning och Microsoft Defender för Endpoint inte används, inaktiveras Microsoft Defender Antivirus automatiskt i inaktivt läge.
- Om din organisation använder Microsoft Defender för Endpoint tillsammans med en lösning som inte är en Microsoft-antivirus-/antimalwarelösning hamnar Microsoft Defender Antivirus automatiskt i passiv form. (Realtidsskydd och hot åtgärdas inte av Microsoft Defender Antivirus.)
- Om din organisation använder Microsoft Defender för Endpoint tillsammans med en lösning som inte är en Microsoft-antivirus-/antimalware-lösning och du har [EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode) i blockeringsläge aktiverat, vidtar Microsoft Defender för Slutpunkt åtgärder för att blockera och åtgärda artefakten när en skadlig artefakt upptäcks.

## <a name="antivirus-and-microsoft-defender-for-endpoint"></a>Antivirus och Microsoft Defender för Slutpunkt

I följande tabell sammanfattas vad som händer med Microsoft Defender Antivirus när antivirusprodukter från tredje part används tillsammans eller utan Microsoft Defender för Slutpunkt. 


| Windows-version   | Skydd mot skadlig programvara  | Microsoft Defender för slutpunktsregistrering | Status för Microsoft Defender Antivirus     |
|------|------|-------|-------|
| Windows 10  | En produkt från tredje part som inte erbjuds eller utvecklas av Microsoft | Ja  | Passivt läge  |
| Windows 10  | En produkt från tredje part som inte erbjuds eller utvecklas av Microsoft | Nej   | Inaktiverat läge automatiskt     |
| Windows 10  | Microsoft Defender Antivirus | Ja  | Aktivt läge | 
| Windows 10  | Microsoft Defender Antivirus | Nej   | Aktivt läge |
| Windows Server, version 1803 eller senare eller Windows Server 2019 | En produkt från tredje part som inte erbjuds eller utvecklas av Microsoft | Ja  | Måste vara inställt på passivt läge (manuellt) <sup> [[1](#fn1)]<sup>  | 
| Windows Server, version 1803 eller senare eller Windows Server 2019 | En produkt från tredje part som inte erbjuds eller utvecklas av Microsoft | Nej  | Måste vara inaktiverat (manuellt) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server, version 1803 eller senare eller Windows Server 2019 | Microsoft Defender Antivirus  | Ja |         Aktivt läge  |
| Windows Server, version 1803 eller senare eller Windows Server 2019 | Microsoft Defender Antivirus | Nej  | Aktivt läge |
| Windows Server 2016 | Microsoft Defender Antivirus | Ja | Aktivt läge |
| Windows Server 2016 | Microsoft Defender Antivirus | Nej | Aktivt läge |
| Windows Server 2016 | En produkt från tredje part som inte erbjuds eller utvecklas av Microsoft | Ja | Måste vara inaktiverat (manuellt) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | En produkt från tredje part som inte erbjuds eller utvecklas av Microsoft | Nej | Måste vara inaktiverat (manuellt) <sup> [[2](#fn2)]<sup> |

(<a id="fn1">1</a>) På Windows Server, version 1803 eller senare eller Windows Server 2019 går Microsoft Defender Antivirus inte in i passiv form automatiskt när du installerar ett antivirusprogram som inte är ett Microsoft-antivirusprogram. I så fall ställer [du in Microsoft Defender Antivirus på passivt läge](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) för att förhindra problem som orsakas av att flera antivirusprogram är installerade på en server.

Om du använder Windows Server, version 1803 eller senare eller Windows Server 2019 kan du ställa in Microsoft Defender Antivirus till passivt läge genom att ange följande registernyckel:
- Sökväg: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Namn: `ForcePassiveMode`
- Typ: `REG_DWORD`
- Värde: `1`

> [!NOTE]
> Registernyckeln `ForcePassiveMode` stöds inte i Windows Server 2016.

(<a id="fn2">2</a>) I Windows Server 2016 förs inte Microsoft Defender Antivirus in i passiv form automatiskt när du installerar en antivirusprodukt som inte är en Microsoft-antivirusprodukt. Dessutom stöds inte Microsoft Defender Antivirus i passiv form. I så fall kan [du inaktivera/avinstallera Microsoft Defender Antivirus manuellt](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) för att förhindra problem som orsakas av att flera antivirusprogram är installerade på en server.

Se [Microsoft Defender Antivirus på Windows Server för](microsoft-defender-antivirus-on-windows-server.md) viktiga skillnader och hanteringsalternativ för Windows Server-installationer.

> [!IMPORTANT]
> Microsoft Defender Antivirus är endast tillgängligt på enheter med Windows 10, Windows Server 2016, Windows Server, version 1803 eller senare och Windows Server 2019.
>
> I Windows 8.1 och Windows Server 2012 erbjuds antivirusskydd på företagsnivå som [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10)), som hanteras via Microsoft Endpoint Configuration Manager.
>
> Windows Defender erbjuds även för konsumentenheter på [Windows 8.1 och Windows Server 2012,](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)även om det inte ger hantering på företagsnivå (eller ett gränssnitt på kärninstallationer av Windows Server 2012 Server).

## <a name="functionality-and-features-available-in-each-state"></a>Funktioner som är tillgängliga i varje tillstånd

Tabellen i det här avsnittet sammanfattar de funktioner som är tillgängliga i varje tillstånd. Tabellen är utformad för att bara vara informationssam. Den är avsedd för att beskriva de & funktioner som aktivt arbetar eller inte, beroende på om Microsoft Defender Antivirus är i aktivt läge, i passiv form eller är inaktiverat/avinstallerat. 

> [!IMPORTANT]
> Inaktivera inte funktioner som realtidsskydd, molnskydd eller begränsad regelbunden genomsökning om du använder Microsoft Defender Antivirus i passiv form eller om du använder EDR i blockläge. 

|Skydd |Aktivt läge |Passivt läge |EDR i blockläge |Inaktiverat eller avinstallerat |
|:---|:---|:---|:---|:---|
| [Realtidsskydd och](./configure-real-time-protection-microsoft-defender-antivirus.md) [moln levererat skydd](./enable-cloud-protection-microsoft-defender-antivirus.md) | Ja | Nej <sup> [[3](#fn3)]<sup> | Nej | Nej |
| [Begränsad tillgänglighet för regelbunden genomsökning](./limited-periodic-scanning-microsoft-defender-antivirus.md) | Nej | Nej | Nej | Ja |
| [Information om genomsökning och identifiering av filer](./customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | Ja | Ja | Ja | Nej |
|  [Åtgärder för hot](./configure-remediation-microsoft-defender-antivirus.md) | Ja | Se <sup> anteckningen [[4](#fn4)]<sup> | Ja | Nej |
| [Säkerhetsintelligensuppdateringar](./manage-updates-baselines-microsoft-defender-antivirus.md) | Ja | Ja | Ja | Nej |

(<a id="fn3">3</a>) När Microsoft Defender Antivirus är i passivt läge tillhandahåller i allmänhet inget skydd i realtid, trots att det är aktiverat och inaktivt. 

(<a id="fn4">4</a>) När Microsoft Defender Antivirus är i passivt läge är åtgärdsfunktioner bara aktiva under schemalagda genomsökningar eller sökningar på begäran.

> [!NOTE]
> [Microsoft 365 Endpoint skydd mot dataförlust](/microsoft-365/compliance/endpoint-dlp-learn-about) fortsätter fungera normalt när Microsoft Defender Antivirus är i aktivt eller passivt läge.

## <a name="keep-the-following-points-in-mind"></a>Tänk på följande

- I aktivt läge används Microsoft Defender Antivirus som antivirusapp på datorn. Alla konfigurationer som gjorts med Konfigurationshanteraren, Grupprincip, Intune eller andra hanteringsprodukter tillämpas. Filer söks igenom och hot åtgärdas, och information om identifiering rapporteras i konfigurationsverktyget (till exempel Configuration Manager eller appen Microsoft Defender Antivirus på själva datorn).

- I passiv form används inte Microsoft Defender Antivirus som antivirusapp, och hoten åtgärdas inte av Microsoft Defender Antivirus. Filer skannas och rapporter tillhandahålls för identifiering av hot som delas med Microsoft Defender för slutpunkt-tjänsten. Därför kan det uppstå aviseringar i säkerhetscenterkonsolen med Microsoft Defender Antivirus som källa, även när Microsoft Defender Antivirus är i passivt läge.

- När [EDR i blockläge](/microsoft-365/security/defender-endpoint/edr-in-block-mode) är aktiverat och Microsoft Defender Antivirus inte är den primära antiviruslösningen kan programmet fortfarande identifiera och åtgärda skadliga objekt.

- När antivirusprogrammet inaktiveras används inte Microsoft Defender Antivirus som antivirusapp. Filer genomsöks inte och hot åtgärdas inte. Att inaktivera/avinstallera Microsoft Defender Antivirus rekommenderas inte i allmänhet. Om möjligt bör du behålla Microsoft Defender Antivirus i passiv form om du använder en lösning som inte är en Microsoft-antiviruslösning.

- Om du är registrerad i Microsoft Defender för Endpoint och du använder en program mot skadlig kod från tredje part aktiveras passivt läge. [Tjänsten kräver vanlig informationsdelning från Microsoft Defender Antivirus-tjänsten](/microsoft-365/security/defender-endpoint/defender-compatibility) för att kunna övervaka enheterna och nätverket korrekt för intrångsförsök och attacker.

- När Microsoft Defender Antivirus inaktiveras automatiskt kan det återaktiveras automatiskt om skyddet som erbjuds av en produkt som inte är en Microsoft-antivirusprodukt upphör att gälla eller på annat sätt slutar ge realtidsskydd mot virus, skadlig programvara eller andra hot. Automatisk återaktivering säkerställer att antivirusskyddet bibehålls på dina enheter. Du kan också aktivera begränsad [regelbunden](limited-periodic-scanning-microsoft-defender-antivirus.md)genomsökning , som använder Microsoft Defender Antivirus-motorn för att regelbundet söka efter hot utöver din huvudantivirusprogram.

- När Microsoft Defender Antivirus är i passivt läge kan du fortfarande [hantera uppdateringar för Microsoft Defender Antivirus](manage-updates-baselines-microsoft-defender-antivirus.md). Men du kan inte flytta Microsoft Defender Antivirus till aktivt läge om dina enheter har ett uppdaterat antivirusprogram som inte är en Microsoft Antivirus-produkt som ger realtidsskydd mot skadlig programvara. Om du vill ha bästa möjliga skydd för säkerhetslager och identifieringsanalys bör du uppdatera Microsoft Defender Antivirus protection [(säkerhetsintelligensuppdatering,](./manage-updates-baselines-microsoft-defender-antivirus.md) motor och plattform) även om Microsoft Defender Antivirus körs i passiv form.

   Om du avinstallerar antivirusprogrammet från Microsoft och använder Microsoft Defender Antivirus för att skydda dina enheter återgår Microsoft Defender Antivirus automatiskt till normalt aktivt läge.

> [!WARNING]
> Inaktivera inte, stoppa eller ändra inga av de associerade tjänster som används av Microsoft Defender Antivirus, Microsoft Defender för Slutpunkt eller Windows-säkerhetsappen. Denna rekommendation omfattar tjänster och processer för *wscsvc*, *SecurityHealthService,* *MsSense,* *Sense,* *WinDefend* och *MsMpEng.* Om du ändrar de här tjänsterna manuellt kan det orsaka allvarlig instabilitet på dina enheter, vilket kan göra nätverket sårbart. Om du inaktiverar, stoppar eller ändrar de tjänsterna kan det också orsaka problem när du använder antiviruslösningar som inte är från Microsoft och hur informationen visas [i Windows-säkerhetsappen.](microsoft-defender-security-center-antivirus.md)


## <a name="see-also"></a>Se även

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus på Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [EDR i blockläge](edr-in-block-mode.md)
- [Konfigurera slutpunktsskydd](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Åtgärda falska positiva/negativa i Microsoft Defender för Endpoint](defender-endpoint-false-positives-negatives.md)
- [Läs mer om dataförlustskydd i Microsoft 365 Endpoint](/microsoft-365/compliance/endpoint-dlp-learn-about)