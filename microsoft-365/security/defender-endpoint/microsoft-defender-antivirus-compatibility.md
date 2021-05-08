---
title: Microsoft Defender Antivirus kompatibilitet med andra säkerhetsprodukter
description: Läs mer Microsoft Defender Antivirus om hur du använder andra säkerhetsprodukter och operativsystem.
keywords: windows defender, defender för slutpunkt, nästa generations, antivirus, kompatibilitet, passivt läge
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
ms.topic: article
manager: dansimp
ms.technology: mde
ms.date: 05/05/2021
ms.openlocfilehash: 99ed714939161347dea71f1cbd53a56c628ce0a1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246495"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Microsoft Defender Antivirus kompatibilitet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="overview"></a>Översikt

Microsoft Defender Antivirus aktiveras och installeras automatiskt på slutpunkter och enheter som kör Windows 10. Men vad händer när en annan (icke-Microsoft)antivirus-/antimalware-lösning används? Det beror på om du använder [Microsoft Defender för Endpoint tillsammans](microsoft-defender-endpoint.md) med ditt antivirusprogram.

- Om din organisations klientenheter skyddas av en lösning som inte är en Microsoft-antivirus-/antimwalware-lösning och dessa enheter introduceras till Defender för Endpoint Microsoft Defender Antivirus in i passiv form automatiskt. I det här fallet sker identifiering av hot, men realtidsskyddet och hoten åtgärdas inte av Microsoft Defender Antivirus. **Obs!** Det här scenariot gäller inte för slutpunkter som kör Windows Server.

- Om din organisations klientenheter skyddas av en lösning som inte är ett Microsoft-antivirusprogram eller en antimalware-lösning och dessa enheter inte är onboarded to Microsoft Defender för Endpoint inaktiveras Microsoft Defender Antivirus automatiskt i inaktivt läge. I det här fallet identifieras eller åtgärdas inte hoten av Microsoft Defender Antivirus. **Obs!** Det här scenariot gäller inte för slutpunkter som kör Windows Server.

- Om din organisations slutpunkter kör Windows Server och dessa slutpunkter skyddas av en lösning som inte är en Microsoft-antivirus-/antimalware-lösning så kommer Microsoft Defender Antivirus inte automatiskt att gå in i antingen passivt läge eller inaktiverat läge för Defender för slutpunkt. I det här scenariot måste du konfigurera Windows serverslutpunkter på rätt sätt. 

   - I Windows Server, version 1803 eller senare och Windows Server 2019 kan du ställa in Microsoft Defender Antivirus att köras i passivt läge. 
   - På Windows Server 2016 måste Microsoft Defender Antivirus inaktiveras (passivt läge stöds inte Windows Server 2016).

- Om din organisations slutpunkter skyddas av en lösning som inte är en Microsoft-antivirus-/antimalware-lösning och dessa enheter introduceras till Defender för Slutpunkt med Identifiering och åtgärd på slutpunkt i [blockeringsläge](/microsoft-365/security/defender-endpoint/edr-in-block-mode) aktiverat, blockerar Defender för slutpunktsblock och åtgärdar skadliga artefakter. **OBS!** Det här scenariot gäller inte för Windows Server 2016. Identifiering och åtgärd på slutpunkt i blockeringsläge måste Microsoft Defender Antivirus vara aktiverat i antingen aktivt läge eller passivt läge.

## <a name="antivirus-and-microsoft-defender-for-endpoint"></a>Antivirus och Microsoft Defender för Slutpunkt

I följande tabell sammanfattas vad som händer Microsoft Defender Antivirus när antivirusprodukter från tredje part används tillsammans eller utan Microsoft Defender för Slutpunkt. 

| Windows version   | Antivirus-/antimalware-produkt  | Defender för slutpunktsregistrering | Microsoft Defender Antivirus status     |
|------|------|-------|-------|
| Windows 10  | Microsoft Defender Antivirus | Ja  | Aktivt läge | 
| Windows 10  | Microsoft Defender Antivirus | Nej   | Aktivt läge |
| Windows 10  | En produkt från tredje part som inte erbjuds eller utvecklas av Microsoft | Ja  | Passivt läge (automatiskt) |
| Windows 10  | En produkt från tredje part som inte erbjuds eller utvecklas av Microsoft | Nej   | Inaktiverat läge (automatiskt)    |
| Windows Server, version 1803 eller senare <p> Windows Server 2019 | Microsoft Defender Antivirus  | Ja |         Aktivt läge  |
| Windows Server, version 1803 eller senare <p> Windows Server 2019 | Microsoft Defender Antivirus | Nej  | Aktivt läge |
| Windows Server, version 1803 eller senare <p> Windows Server 2019 | En produkt från tredje part som inte erbjuds eller utvecklas av Microsoft | Ja  | Microsoft Defender Antivirus måste vara inställt på passivt läge (manuellt) <sup> [[1](#fn1)]<sup>  | 
| Windows Server, version 1803 eller senare <p> Windows Server 2019 | En produkt från tredje part som inte erbjuds eller utvecklas av Microsoft | Nej  | Microsoft Defender Antivirus måste vara inaktiverat (manuellt) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server 2016 | Microsoft Defender Antivirus | Ja | Aktivt läge |
| Windows Server 2016 | Microsoft Defender Antivirus | Nej | Aktivt läge |
| Windows Server 2016 | En produkt från tredje part som inte erbjuds eller utvecklas av Microsoft | Ja | Microsoft Defender Antivirus måste vara inaktiverat (manuellt) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | En produkt från tredje part som inte erbjuds eller utvecklas av Microsoft | Nej | Microsoft Defender Antivirus måste vara inaktiverat (manuellt) <sup> [[2](#fn2)]<sup> |

(<a id="fn1">1</a>) På Windows Server, version 1803 eller senare, eller Windows Server 2019, går Microsoft Defender Antivirus inte in i passiv form automatiskt när du installerar en antivirusprodukt som inte är en Microsoft-antivirusprodukt. I sådana fall bör [du Microsoft Defender Antivirus passivt läge för](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) att förhindra problem som orsakas av att flera antivirusprogram är installerade på en server. Du kan ange Microsoft Defender Antivirus passivt läge med Hjälp av PowerShell, Grupprincip eller en registernyckel.

Om du använder Windows Server, version 1803 eller senare eller Windows Server 2019 kan du ställa in Microsoft Defender Antivirus till passivt läge genom att ange följande registernyckel:
- Sökväg: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Namn: `ForceDefenderPassiveMode`
- Typ: `REG_DWORD`
- Värde: `1`

> [!NOTE]
> Registernyckeln `ForcePassiveMode` stöds inte på Windows Server 2016.

(<a id="fn2">2</a>) På Windows Server 2016 gäller att om du använder ett antivirusprogram som inte är ett Microsoft-antivirusprogram kan du inte Microsoft Defender Antivirus i antingen passivt läge eller aktivt läge. I sådana fall [inaktiverar/avinstallerar du Microsoft Defender Antivirus för](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) att förhindra problem som orsakas av att flera antivirusprogram är installerade på en server.

I [Microsoft Defender Antivirus på Windows Server finns](microsoft-defender-antivirus-on-windows-server.md) viktiga skillnader och hanteringsalternativ för Windows Server-installationer.

> [!IMPORTANT]
> Microsoft Defender Antivirus är endast tillgängligt på enheter med Windows 10, Windows Server 2016, Windows Server, version 1803 eller senare och Windows Server 2019.
>
> I Windows 8.1 och Windows Server 2012 erbjuds antivirusskydd på företagsnivå som [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10)), som hanteras via Microsoft Endpoint Configuration Manager.
>
> Windows Defender erbjuds även för konsumentenheter på [Windows 8.1](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)och Windows Server 2012 , även om det inte ger bättre hantering på företagsnivå (eller ett gränssnitt på grund av Windows Server 2012 Server Core-installationer).

## <a name="functionality-and-features-available-in-each-state"></a>Funktioner som är tillgängliga i varje tillstånd

Tabellen i det här avsnittet sammanfattar de funktioner som är tillgängliga i varje tillstånd. Tabellen är utformad för att bara vara informationssam. Den är avsedd för att beskriva de & funktioner som aktivt arbetar eller inte, beroende på om Microsoft Defender Antivirus är i aktivt läge, i passiv form eller inaktiveras/avinstalleras. 

> [!IMPORTANT]
> Inaktivera inte funktioner som realtidsskydd, molnskydd eller begränsad regelbunden genomsökning om du använder Microsoft Defender Antivirus i passiv form eller om du använder Identifiering och åtgärd på slutpunkt i blockläge. 

|Skydd |Aktivt läge |Passivt läge |EDR i blockläge |Inaktiverat eller avinstallerat |
|:---|:---|:---|:---|:---|
| [Realtidsskydd och](configure-real-time-protection-microsoft-defender-antivirus.md) [moln levererat skydd](enable-cloud-protection-microsoft-defender-antivirus.md) | Ja | Nej <sup> [[3](#fn3)]<sup> | Nej | Nej |
| [Begränsad tillgänglighet för regelbunden genomsökning](limited-periodic-scanning-microsoft-defender-antivirus.md) | Nej | Nej | Nej | Ja |
| [Information om genomsökning och identifiering av filer](customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | Ja | Ja | Ja | Nej |
|  [Åtgärder för hot](configure-remediation-microsoft-defender-antivirus.md) | Ja | Se <sup> anteckningen [[4](#fn4)]<sup> | Ja | Nej |
| [Säkerhetsintelligensuppdateringar](manage-updates-baselines-microsoft-defender-antivirus.md) | Ja | Ja | Ja | Nej |

(<a id="fn3">3</a>) När Microsoft Defender Antivirus är i passivt läge tillhandahåller i allmänhet inget skydd i realtid, trots att det är aktiverat och inaktivt. 

(<a id="fn4">4</a>) Microsoft Defender Antivirus i passiv form är åtgärdsfunktioner bara aktiva under schemalagda genomsökningar eller på begäran.

> [!NOTE]
> [Microsoft 365 Skydd mot dataförlust fortsätter](/microsoft-365/compliance/endpoint-dlp-learn-about) att fungera normalt när Microsoft Defender Antivirus i aktivt eller passivt läge.

## <a name="keep-the-following-points-in-mind"></a>Tänk på följande

- I aktivt läge Microsoft Defender Antivirus antivirusappen på datorn. Alla konfigurationer som gjorts med Konfigurationshanteraren, Grupprincip, Intune eller andra hanteringsprodukter tillämpas. Filer söks igenom och hot har åtgärdats, och information om identifiering rapporteras i konfigurationsverktyget (till exempel Configuration Manager eller Microsoft Defender Antivirus-appen på själva datorn).

- I passiv form Microsoft Defender Antivirus inte som antivirusprogram, och hoten åtgärdas inte av Microsoft Defender Antivirus. Filer skannas och rapporter tillhandahålls för identifiering av hot som delas med Microsoft Defender för slutpunkt-tjänsten. Du kan se aviseringar i [säkerhetscentret som](microsoft-defender-security-center.md) visar Microsoft Defender Antivirus som källa, även när Microsoft Defender Antivirus är i passivt läge.

- När [Identifiering och åtgärd på slutpunkt i blockläge](edr-in-block-mode.md) är aktiverat och Microsoft Defender Antivirus inte är den primära antiviruslösningen identifierar och åtgärdar skadliga objekt. Identifiering och åtgärd på slutpunkt i blockeringsläge måste Microsoft Defender Antivirus vara aktiverat i antingen aktivt läge eller passivt läge.

- När det är Microsoft Defender Antivirus att den inte används som antivirusapp. Filer genomsöks inte och hot åtgärdas inte. Att inaktivera/avinstallera Microsoft Defender Antivirus rekommenderar inte i allmänhet. Om möjligt bör du Microsoft Defender Antivirus i passiv form om du använder en lösning som inte är ett Microsoft-program mot skadlig programvara/antivirusprogram.

- Om du är registrerad i Microsoft Defender för Endpoint och du använder en program mot skadlig kod från tredje part aktiveras passivt läge. Tjänsten kräver vanlig informationsdelning från Microsoft Defender Antivirus för att kunna övervaka enheterna och nätverket för intrångsförsök och attacker. Mer information finns i [Microsoft Defender Antivirus kompatibilitet med Microsoft Defender för Slutpunkt.](defender-compatibility.md) 

- När Microsoft Defender Antivirus i passiv form kan du fortfarande [hantera uppdateringar för Microsoft Defender Antivirus](manage-updates-baselines-microsoft-defender-antivirus.md). Du kan dock inte flytta Microsoft Defender Antivirus till aktivt läge om dina enheter har ett uppdaterat antivirusprogram som inte är ett Microsoft-antivirusprogram som ger realtidsskydd mot skadlig programvara. För optimal skydd och identifiering av säkerhetslager, se till att uppdatera [Microsoft Defender Antivirus-skyddet](manage-updates-baselines-microsoft-defender-antivirus.md) (säkerhetsintelligensuppdatering, motor och plattform) även om Microsoft Defender Antivirus körs i passivt läge.

- När Microsoft Defender Antivirus inaktiveras automatiskt kan det aktiveras på nytt om skyddet som erbjuds av en produkt som inte är en Microsoft-antivirusprodukt upphör att gälla eller på annat sätt slutar ge realtidsskydd mot virus, skadlig programvara eller andra hot. Automatisk återaktivering säkerställer att antivirusskyddet bibehålls på dina enheter. Du kan också aktivera begränsad regelbunden genomsökning [,](limited-periodic-scanning-microsoft-defender-antivirus.md)som använder Microsoft Defender Antivirus för att regelbundet söka efter hot utöver din huvudantivirusprogram.


> [!WARNING]
> Inaktivera inte, stoppa eller ändra inga av de associerade tjänster som används av Microsoft Defender Antivirus, Microsoft Defender för Endpoint eller Windows-säkerhet appen. Denna rekommendation omfattar tjänster och processer för *wscsvc*, *SecurityHealthService,* *MsSense,* *Sense,* *WinDefend* och *MsMpEng.* Om du ändrar de här tjänsterna manuellt kan det orsaka allvarlig instabilitet på dina enheter, vilket kan göra nätverket sårbart. Om du inaktiverar, stoppar eller ändrar de tjänsterna kan det också orsaka problem när du använder antiviruslösningar som inte är från Microsoft och hur informationen visas i [Windows-säkerhet-appen.](microsoft-defender-security-center-antivirus.md)


## <a name="see-also"></a>Se även

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus på Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [EDR i blockläge](edr-in-block-mode.md)
- [Konfigurera Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Åtgärda falska positiva/negativa i Microsoft Defender för Endpoint](defender-endpoint-false-positives-negatives.md)
- [Läs mer om dataförlustskydd för slutpunkt i Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)
