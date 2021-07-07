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
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 07/06/2021
ms.openlocfilehash: aac84d2e957809d1c9579f25c01006798af2c0a9
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322419"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Microsoft Defender Antivirus kompatibilitet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="summary"></a>Sammanfattning

Microsoft Defender Antivirus aktiveras och installeras automatiskt på slutpunkter och enheter som kör Windows 10. Men vad händer när en annan (icke-Microsoft)antivirus-/antimalware-lösning används? Kan du köra Microsoft Defender Antivirus bredvid en annan antivirusprodukt? Svaren beror på flera faktorer, till exempel operativsystemet och om du använder Microsoft Defender för [Endpoint tillsammans](microsoft-defender-endpoint.md) med ditt antivirusprogram. 

## <a name="important-points-to-keep-in-mind"></a>Viktiga saker att tänka på

- I aktivt läge Microsoft Defender Antivirus antivirusappen på datorn. Inställningar konfigureras med konfigurationshanteraren, grupprincip, Microsoft Intune eller andra hanteringsprodukter används. Filer genomsöks, hot åtgärdas och information om identifiering rapporteras i konfigurationsverktyget (till exempel Konfigurationshanteraren eller Microsoft Defender Antivirus-appen på själva slutpunkten).

- I passiv form Microsoft Defender Antivirus inte som antivirusapp och hoten *av* den Microsoft Defender Antivirus. Filer skannas och rapporter tillhandahålls för identifiering av hot som delas med Microsoft Defender för slutpunkt-tjänsten. Du kan se aviseringar i [säkerhetscentret som](microsoft-defender-security-center.md) visar Microsoft Defender Antivirus som källa, även när Microsoft Defender Antivirus är i passivt läge.

- När Identifiering och åtgärd på slutpunkt i [blockläge](edr-in-block-mode.md) är aktiverat och Microsoft Defender Antivirus inte är den primära antiviruslösningen identifierar och åtgärdar Identifiering och åtgärd på slutpunkt i blockeringsläge skadliga objekt som hittas på enheten (efter intrång). Identifiering och åtgärd på slutpunkt i blockeringsläge måste Microsoft Defender Antivirus vara aktiverat i antingen aktivt läge eller passivt läge.

- När det är Microsoft Defender Antivirus att den inte används som antivirusapp. Filer genomsöks inte och hot åtgärdas inte. Att inaktivera eller avinstallera Microsoft Defender Antivirus rekommenderas inte i allmänhet. Om möjligt bör du Microsoft Defender Antivirus i passiv form om du använder en lösning som inte är ett Microsoft-program mot skadlig programvara/antivirusprogram.

- Om du är registrerad i Microsoft Defender för Endpoint och du använder en produkt som inte är en Microsoft-antivirus-/antimalware är Microsoft Defender Antivirus aktiverat i passivt läge. Defender för Endpoint kräver vanlig informationsdelning från Microsoft Defender Antivirus för att kunna övervaka enheterna och nätverket korrekt för intrångsförsök och attacker. Mer information finns i [Microsoft Defender Antivirus kompatibilitet med Microsoft Defender för Slutpunkt.](defender-compatibility.md) 

- När Microsoft Defender Antivirus i passiv form kan du fortfarande [hantera uppdateringar för Microsoft Defender Antivirus](manage-updates-baselines-microsoft-defender-antivirus.md). Du kan dock inte flytta Microsoft Defender Antivirus till aktivt läge om dina enheter har en antivirusprodukt som inte är en Microsoft-antivirusprodukt som ger skydd mot skadlig programvara i realtid. För optimal skydd och identifiering av säkerhet i lager, se till att få dina uppdateringar för antivirus och antimwalware, även om Microsoft Defender Antivirus körs i passivt läge. Se [Hantera Microsoft Defender Antivirus uppdateringar och använda baslinjer.](manage-updates-baselines-microsoft-defender-antivirus.md)

- När Microsoft Defender Antivirus inaktiveras automatiskt kan den återaktiveras automatiskt om produkten som inte är ett Microsoft-antivirus-/antimalware-program upphör att gälla eller på annat sätt slutar ge realtidsskydd mot virus, skadlig programvara eller andra hot. Den automatiska återaktiveringen av Microsoft Defender Antivirus hjälper till att säkerställa att antivirusskyddet bibehålls på dina slutpunkter. Du kan också aktivera [begränsad regelbunden](limited-periodic-scanning-microsoft-defender-antivirus.md)genomsökning , som använder Microsoft Defender Antivirus för att regelbundet söka efter hot om du använder en antivirusapp som inte är en Microsoft-app.

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>Microsoft Defender Antivirus antivirus- och antimalwarelösningar från Microsoft

Operativsystemet, antivirusprodukten och Defender för Endpoint påverkar om Microsoft Defender Antivirus aktivt läge, passivt läge eller inaktiverat. Följande tabell sammanfattar vad som händer med Microsoft Defender Antivirus när icke-Microsoft antivirus-/antimalware-lösningar används tillsammans eller utan Microsoft Defender för Endpoint. 

| Windows version   | Antivirus-/antimalware-lösning  | Introduktion till <br/> Defender för Endpoint? | Microsoft Defender Antivirus status     |
|------|------|-------|-------|
| Windows 10  | Microsoft Defender Antivirus | Ja  | Aktivt läge | 
| Windows 10  | Microsoft Defender Antivirus | Nej   | Aktivt läge |
| Windows 10  | En lösning som inte är en Microsoft antivirus-/antimalwarelösning | Ja  | Passivt läge (automatiskt) |
| Windows 10  | En lösning som inte är en Microsoft antivirus-/antimalwarelösning | Nej   | Inaktiverat läge (automatiskt)    |
| Windows Server, version 1803 eller senare <p> Windows Server 2019 | Microsoft Defender Antivirus  | Ja |         Aktivt läge  |
| Windows Server, version 1803 eller senare <p> Windows Server 2019 | Microsoft Defender Antivirus | Nej  | Aktivt läge |
| Windows Server, version 1803 eller senare <p> Windows Server 2019 | En lösning som inte är en Microsoft antivirus-/antimalwarelösning | Ja  | Microsoft Defender Antivirus måste vara inställt på passivt läge (manuellt) <sup> [[1](#fn1)]<sup>  | 
| Windows Server, version 1803 eller senare <p> Windows Server 2019 | En lösning som inte är en Microsoft antivirus-/antimalwarelösning | Nej  | Microsoft Defender Antivirus måste vara inaktiverat (manuellt) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server 2016 | Microsoft Defender Antivirus | Ja | Aktivt läge |
| Windows Server 2016 | Microsoft Defender Antivirus | Nej | Aktivt läge |
| Windows Server 2016 | En lösning som inte är en Microsoft antivirus-/antimalwarelösning | Ja | Microsoft Defender Antivirus måste vara inaktiverat (manuellt) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | En lösning som inte är en Microsoft antivirus-/antimalwarelösning | Nej | Microsoft Defender Antivirus måste vara inaktiverat (manuellt) <sup> [[2](#fn2)]<sup> |

(<a id="fn1">1</a>) På Windows Server, version 1803 eller senare, eller Windows Server 2019, går Microsoft Defender Antivirus inte in i passiv form automatiskt när du installerar en antivirusprodukt som inte är en Microsoft-antivirusprodukt. I sådana fall bör [du Microsoft Defender Antivirus passivt läge för](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) att förhindra problem som orsakas av att flera antivirusprogram är installerade på en server. Du kan Microsoft Defender Antivirus till passivt läge med Hjälp av PowerShell, Grupprincip eller en registernyckel.

Om du använder Windows Server, version 1803 eller senare eller Windows Server 2019 kan du ställa in Microsoft Defender Antivirus till passivt läge genom att ange följande registernyckel:
- Sökväg: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Namn: `ForceDefenderPassiveMode`
- Typ: `REG_DWORD`
- Värde: `1`

> [!NOTE]
> Passiv form stöds inte i Windows Server 2016. Registernyckeln `ForceDefenderPassiveMode` kan användas på Windows Server, version 1803 eller senare eller i Windows Server 2019, men inte Windows Server 2016. 

(<a id="fn2">2</a>) På Windows Server 2016 gäller att om du använder ett antivirusprogram som inte är ett Microsoft-antivirusprogram kan du inte Microsoft Defender Antivirus i antingen passivt läge eller aktivt läge. I sådana fall [inaktiverar/avinstallerar du Microsoft Defender Antivirus för](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) att förhindra problem som orsakas av att flera antivirusprogram är installerade på en server.

I [Microsoft Defender Antivirus på Windows Server finns](microsoft-defender-antivirus-on-windows-server.md) viktiga skillnader och hanteringsalternativ för Windows Server-installationer.

> [!IMPORTANT]
> Microsoft Defender Antivirus är endast tillgängligt på enheter med Windows 10, Windows Server 2016, Windows Server, version 1803 eller senare och Windows Server 2019.
>
> I Windows 8.1 och Windows Server 2012 erbjuds antivirusskydd på företagsnivå som [System Center Endpoint Protection](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10)), som hanteras via Microsoft Endpoint Configuration Manager.
>
> Windows Defender erbjuds även för konsumentenheter på [Windows 8.1](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)och Windows Server 2012 , även om det inte ger bättre hantering på företagsnivå (eller ett gränssnitt på grund av Windows Server 2012 Server Core-installationer).

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Hur Microsoft Defender Antivirus Defender för Slutpunkt-funktioner påverkas

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

## <a name="why-defender-for-endpoint-matters"></a>Varför Defender för Endpoint är viktigt

Överväg att introducera dina slutpunkter i Defender för Endpoint, även om du använder en lösning som inte är en antivirus-/antimalwarelösning från Microsoft. När du skyddar dina enheter i Defender för Slutpunkt kan du i de flesta fall använda Microsoft Defender Antivirus tillsammans med din antiviruslösning som inte är en Microsoft-lösning. Du kan till exempel använda Identifiering och åtgärd på slutpunkt i [blockläge,](edr-in-block-mode.md)som blockerar och åtgärdar skadliga artefakter som din primära antiviruslösning kan ha missat. 

Så här fungerar det:

- Om din organisations klientenheter skyddas av en lösning som inte är en Microsoft-antivirus-/antimwalware-lösning och dessa enheter introduceras till Defender för Endpoint Microsoft Defender Antivirus in i passiv form automatiskt. I det här fallet sker identifiering av hot, men realtidsskyddet och hoten åtgärdas inte av Microsoft Defender Antivirus.
   
   > [!NOTE]
   > Det här scenariot gäller inte för slutpunkter som kör Windows Server.

- Om din organisations klientenheter skyddas av en lösning som inte är ett Microsoft-antivirusprogram eller en antimalware-lösning och dessa enheter inte är onboarded to Microsoft Defender för Endpoint inaktiveras Microsoft Defender Antivirus automatiskt i inaktivt läge. I det här fallet identifieras eller åtgärdas inte hoten av Microsoft Defender Antivirus.
   
   > [!NOTE]
   > Det här scenariot gäller inte för slutpunkter som kör Windows Server.

- Om din organisations slutpunkter kör Windows Server och dessa slutpunkter skyddas av en lösning som inte är en Microsoft-antivirus-/antimalware-lösning så kommer Microsoft Defender Antivirus inte automatiskt att gå in i antingen passivt läge eller inaktiverat läge för Defender för slutpunkt. I det här scenariot måste du konfigurera Windows serverslutpunkter på rätt sätt. 

   - I Windows Server, version 1803 eller senare och Windows Server 2019 kan du ställa in Microsoft Defender Antivirus att köras i passivt läge. 
   - På Windows Server 2016 måste Microsoft Defender Antivirus inaktiveras (passivt läge stöds inte Windows Server 2016).

- Om din organisations slutpunkter skyddas av en lösning som inte är en Microsoft-antivirus-/antimalware-lösning och dessa enheter introduceras till Defender för Slutpunkt med Identifiering och åtgärd på slutpunkt i [blockeringsläge](/microsoft-365/security/defender-endpoint/edr-in-block-mode) aktiverat, blockerar Defender för slutpunktsblock och åtgärdar skadliga artefakter.
   
   > [!NOTE]
   > Just det här scenariot gäller inte för Windows Server 2016. Identifiering och åtgärd på slutpunkt i blockeringsläge måste Microsoft Defender Antivirus vara aktiverat i antingen aktivt läge eller passivt läge.


> [!WARNING]
> Inaktivera inte, stoppa eller ändra inga av de associerade tjänster som används av Microsoft Defender Antivirus, Microsoft Defender för Endpoint eller Windows-säkerhet appen. Denna rekommendation omfattar tjänster och processer för *wscsvc*, *SecurityHealthService,* *MsSense,* *Sense,* *WinDefend* och *MsMpEng.* Om du ändrar de här tjänsterna manuellt kan det orsaka allvarlig instabilitet på dina enheter, vilket kan göra nätverket sårbart. Om du inaktiverar, stoppar eller ändrar de tjänsterna kan det också orsaka problem när du använder antiviruslösningar som inte är från Microsoft och hur informationen visas i [Windows-säkerhet-appen.](microsoft-defender-security-center-antivirus.md)


## <a name="see-also"></a>Se även

- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus på Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [EDR i blockläge](edr-in-block-mode.md)
- [Konfigurera Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Åtgärda falska positiva/negativa i Microsoft Defender för Endpoint](defender-endpoint-false-positives-negatives.md)
- [Läs mer om dataförlustskydd för slutpunkt i Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)
