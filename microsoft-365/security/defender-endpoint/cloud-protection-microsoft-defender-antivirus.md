---
title: Molnbaserat skydd och Microsoft Defender Antivirus
description: Läs mer om molnskydd och Microsoft Defender Antivirus
keywords: Microsoft Defender Antivirus, nästa generations teknik, nästa generations av, maskininlärning, program mot skadlig programvara, säkerhet, defender, moln, molnskydd
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 06/03/2021
ms.openlocfilehash: ce54f8205e62b953022fd2518caac058f4f9bab2
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788805"
---
# <a name="cloud-delivered-protection-and-microsoft-defender-antivirus"></a>Molnbaserat skydd och Microsoft Defender Antivirus

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender Antivirus

Nästa generations teknik i Microsoft Defender Antivirus ger omedelbar, automatiserad säkerhet mot nya och nya hot. För att identifiera nya hot dynamiskt fungerar nästa generations teknik med stora mängder sammankopplade data i Microsoft Intelligent Security Graph och kraftfulla AI-system som drivs av avancerade maskininlärningsmodeller. Microsoft Defender Antivirus använder flera identifierings- och skyddstekniker för att ge korrekt, realtids- och intelligent skydd. 

> [!TIP]
> Vill du veta mer? Se blogginlägget Lär känna den avancerade tekniken som ligger i grunden för nästa generations [skydd för Microsoft Defender för Slutpunkt.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

Microsoft Defender Antivirus fungerar smidigt med Microsofts molntjänster. De här molnskyddstjänster, som även kallas MICROSOFT Advanced Protection Service (MAPS), förbättrar standard realtidsskydd, vilket ger ett bra skydd mot antivirus. 

> [!NOTE]
> Den Microsoft Defender Antivirus molntjänsten är en mekanism för att tillhandahålla uppdaterat skydd till nätverket och slutpunkterna. Som molntjänst är den inte bara skydd för filer som lagras i molnet. Istället använder molntjänsten distribuerade resurser och maskininlärning för att ge skydd till slutpunkterna i en takt som är mycket snabbare än traditionella säkerhetsintelligensuppdateringar.

Med moln levererat skydd ger nästa generations teknik snabb identifiering av nya hot, ibland även innan en enda dator smittas. Följande blogginlägg visar hur moln levererat skydd fungerar:

- [Varför Microsoft Defender Antivirus är den mest distribuerade i företaget](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 
- [Funktionsövervakning i kombination med maskininlärning kan förstöra en enorm slantsinglingskampanj](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)
- [Hur artificiell intelligens stoppade ett "emotet"-utbrott](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)
- [Detonerar en dålig dator: Microsoft Defender Antivirus och lagerutbildnings försvar för maskininlärning](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)
- [Microsoft Defender Antivirus molnskyddstjänst: Avancerat realtidsskydd mot skadlig programvara som aldrig tidigare har setts](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 
 
## <a name="how-to-get-cloud-delivered-protection"></a>Så här får du moln levererat skydd 

Moln levererat skydd är aktiverat som standard. Du kan dock behöva återaktivera den om den har inaktiverats som en del av tidigare organisationspolicyer. Mer information finns i [Aktivera moln levererat skydd](enable-cloud-protection-microsoft-defender-antivirus.md).

Organisationer som kör Windows 10 E5 kan också dra nytta av dynamiska säkerhetsuppdateringar som ger snabbt skydd mot nya hot i realtid. När du aktiverar moln levererat skydd kan lösningar på problem med skadlig programvara levereras via molnet inom några minuter, i stället för att vänta på nästa uppdatering. [Konfigurera Microsoft Defender Antivirus att automatiskt få nya skyddsuppdateringar baserat på rapporter från vår molntjänst.](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)

> [!TIP]
> Besök webbplatsen Windows Defender Testground på [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att funktionen fungerar och se hur den fungerar.

## <a name="next-steps"></a>Nästa steg

1. [Aktivera moln levererat skydd.](enable-cloud-protection-microsoft-defender-antivirus.md) Du kan aktivera moln levererat skydd med Microsoft Endpoint Manager (som nu innehåller Microsoft Endpoint Configuration Manager och Microsoft Intune), Grupprincip eller PowerShell-cmdlets.

2. [Ange skyddsnivån som levereras i molnet.](specify-cloud-protection-level-microsoft-defender-antivirus.md) Du kan ange vilken skyddsnivå som molnet ger med hjälp av Microsoft Endpoint Manager eller grupprincip. Skyddsnivån påverkar mängden information som delas med molnet och hur aggressiva nya filer blockeras.

3. [Konfigurera och validera nätverksanslutningar för Microsoft Defender Antivirus](configure-network-connections-microsoft-defender-antivirus.md). Det finns vissa Microsoft-URL:er som ditt nätverk och slutpunkter måste kunna ansluta till för moln levererat skydd för att fungera effektivt. Den här artikeln innehåller webbadresser som ska tillåtas via brandväggs- eller nätverksfiltreringsregler och instruktioner för att bekräfta att nätverket är korrekt registrerat i moln levererat skydd.

4. [Konfigurera funktionen "block vid första synen".](configure-block-at-first-sight-microsoft-defender-antivirus.md) Funktionen "blockera vid första synen" kan blockera ny skadlig programvara inom några sekunder utan att behöva vänta flera timmar på traditionell säkerhetsinformation. Du kan aktivera och konfigurera den med hjälp Microsoft Endpoint Manager grupprincip.

5. [Konfigurera tidsgränsen för molnblockering](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md). Microsoft Defender Antivirus kan blockera misstänkta filer från att köras medan den frågar om vår moln leveransskyddstjänst. Du kan konfigurera hur lång tid filen förhindras från att köras med hjälp av Microsoft Endpoint Manager eller grupprincip.