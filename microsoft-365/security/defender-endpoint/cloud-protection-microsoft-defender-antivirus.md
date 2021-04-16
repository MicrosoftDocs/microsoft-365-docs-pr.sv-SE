---
title: Moln levererat skydd och Microsoft Defender Antivirus
description: Läs mer om molnskydd och Microsoft Defender Antivirus
keywords: Microsoft Defender Antivirus, nästa generations teknik, nästa generations av, maskininlärning, program mot skadlig programvara, säkerhet, defender, moln, molnskydd
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: shwjha
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: e967cb9efe03fc180bda531f192f3143c311796d
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764765"
---
# <a name="use-next-generation-technologies-in-microsoft-defender-antivirus-through-cloud-delivered-protection"></a>Använda nästa generations teknik i Microsoft Defender Antivirus via molnskydd

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender Antivirus

Nästa generations Microsoft-teknik i Microsoft Defender Antivirus ger ett nästan omedelbart, automatiserat skydd mot nya och nya hot. Dessa tekniker kan dynamiskt identifiera nya hot genom att använda stora mängder sammankopplade data i Microsoft Intelligent Security Graph och kraftfulla AI-system (artificiell intelligens) som drivs av avancerade maskininlärningsmodeller.  

Microsoft Defender Antivirus använder flera identifierings- och skyddstekniker för att ge korrekt, realtids- och intelligent skydd. [Lär känna de avancerade teknikerna som ligger till grund för nästa](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)generations skydd för Microsoft Defender för slutpunkt.
![Lista över Microsoft Defender AV-motorer](images/microsoft-defender-atp-next-generation-protection-engines.png)  

För att utnyttja kraften och hastigheten hos dessa nästa generations tekniker fungerar Microsoft Defender Antivirus smidigt med Microsofts molntjänster. De här molnskyddstjänster, som även kallas MICROSOFT Advanced Protection Service (MAPS), förbättrar standard realtidsskydd, vilket ger ett bra skydd mot antivirus. 

>[!NOTE]
>Microsoft Defender Antivirus-molntjänsten är en mekanism för att tillhandahålla uppdaterat skydd till nätverket och slutpunkterna. Trots att det kallas för molntjänst är det inte bara skydd för filer som lagras i molnet utan använder distribuerade resurser och maskininlärning för att ge skydd till slutpunkterna i en takt som är mycket snabbare än traditionella säkerhetsintelligensuppdateringar.

Med moln levererat skydd ger nästa generations teknik snabb identifiering av nya hot, ibland även innan en enda dator smittas. Se följande video om Microsoft AI och Microsoft Defender Antivirus i praktiken: 
 
<iframe 
src="https://www.microsoft.com/videoplayer/embed/RE1Yu4B" width="768" height="432" allowFullScreen="true" frameBorder="0" scrolling="no"></iframe>

Se följande video för att förstå hur nästa generations tekniker förkortar tiden för skydd genom molnet: 
 
<iframe 
src="https://videoplayercdn.osi.office.net/embed/c2f20f59-ca56-4a7b-ba23-44c60bc62c59" width="768" height="432" allowFullScreen="true" frameBorder="0" scrolling="no"></iframe>

Läs följande blogginlägg för detaljerade skyddsberättelser som innefattar molnskydd och Microsoft AI: 

- [Varför är Microsoft Defender Antivirus den mest distribuerade i företaget](https://www.microsoft.com/security/blog/2018/03/22/why-windows-defender-antivirus-is-the-most-deployed-in-the-enterprise) 
- [Funktionsövervakning i kombination med maskininlärning kan förstöra en enorm Dofoil-slantsinglingskampanj](https://www.microsoft.com/security/blog/2018/03/07/behavior-monitoring-combined-with-machine-learning-spoils-a-massive-dofoil-coin-mining-campaign)
- [Hur artificiell intelligens stoppade ett utbrott av uttryckssymbolen](https://www.microsoft.com/security/blog/2018/02/14/how-artificial-intelligence-stopped-an-emotet-outbreak)
- [Detonerar en dålig dator: Microsoft Defender Antivirus och maskininlärningsbackar i lager](https://www.microsoft.com/security/blog/2017/12/11/detonating-a-bad-rabbit-windows-defender-antivirus-and-layered-machine-learning-defenses)
- [Molnskyddstjänst för Microsoft Defender Antivirus: Avancerat realtidsskydd mot skadlig programvara som aldrig tidigare har setts](https://www.microsoft.com/security/blog/2017/07/18/windows-defender-antivirus-cloud-protection-service-advanced-real-time-defense-against-never-before-seen-malware) 
 
## <a name="get-cloud-delivered-protection"></a>Få moln levererat skydd 

Moln levererat skydd är aktiverat som standard. Du kan dock behöva återaktivera den om den har inaktiverats som en del av tidigare organisationspolicyer.

Organisationer som kör Windows 10 E5 kan också dra nytta av dynamiska säkerhetsuppdateringar som ger snabbt skydd mot nya hot i realtid. När du aktiverar moln levererat skydd kan lösningar på problem med skadlig programvara levereras via molnet inom några minuter, i stället för att vänta på nästa uppdatering.

>[!TIP]
>Du kan också gå till Windows Defender Testground-webbplatsen [på demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att funktionen fungerar och se hur den fungerar.

I följande tabell beskrivs skillnaderna i moln levererat skydd mellan de senaste versionerna av Windows och Configuration Manager.

|OS-version eller -tjänstprogram |Tjänstetikett för molnskydd  |Rapporteringsnivå (KARTOR- medlemskapsnivå)  |Timeout-period för molnblockering  |
|---------|---------|---------|---------|
|Windows 8.1 (Grupprincip)     |Microsoft Advanced Protection Service   |Grundläggande, avancerat   |Nej         |
|Windows 10 – version 1607 – (Grupprincip)  |Microsoft Advanced Protection Service      |Avancerat         |Nej         |
|Windows 10 , version 1703 eller senare (Grupprincip)      |Molnbaserat skydd      |Avancerat         |Konfigurerbart         |
|System Center 2012 Configuration Manager  |      Uppgift saknas         |Beroende på Windows-version         |Kan inte konfigureras |
|Microsoft Endpoint Manager (Current Branch)         |Molnskyddstjänst         |Beroende på Windows-version          |Konfigurerbart         |
|Microsoft Intune     |Microsoft Advanced Protection Service         |Beroende på Windows-version         |Konfigurerbart         |

Du kan också [konfigurera Microsoft Defender Antivirus så att det automatiskt får nya skyddsuppdateringar baserat på rapporter från vår molntjänst.](manage-event-based-updates-microsoft-defender-antivirus.md#cloud-report-updates)


## <a name="tasks"></a>Uppgifter

- [Aktivera moln levererat skydd.](enable-cloud-protection-microsoft-defender-antivirus.md) Du kan aktivera moln levererat skydd med Microsoft Endpoint Configuration Manager, Grupprincip, Microsoft Intune och PowerShell-cmdlets.

- [Ange skyddsnivån som levereras i molnet.](specify-cloud-protection-level-microsoft-defender-antivirus.md) Du kan ange vilken skyddsnivå som erbjuds av molnet med Grupprincip och Konfigurationshanteraren för Microsoft Endpoint. Skyddsnivån påverkar mängden information som delas med molnet och hur aggressiva nya filer blockeras.

- [Konfigurera och validera nätverksanslutningar för Microsoft Defender Antivirus.](configure-network-connections-microsoft-defender-antivirus.md) Det finns vissa Microsoft-URL:er som ditt nätverk och slutpunkter måste kunna ansluta till för moln levererat skydd för att fungera effektivt. Den här artikeln innehåller webbadresser som ska tillåtas via brandväggs- eller nätverksfiltreringsregler och instruktioner för att bekräfta att nätverket är korrekt registrerat i moln levererat skydd.

- [Konfigurera funktionen för blocket vid första synen](configure-block-at-first-sight-microsoft-defender-antivirus.md). Funktionen "blockera vid första synen" kan blockera ny skadlig programvara inom några sekunder utan att behöva vänta flera timmar på traditionell säkerhetsinformation. Du kan aktivera och konfigurera den med Microsoft Endpoint Manager och Grupprincip.

- [Konfigurera tidsgränsen för molnblockering](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md). Microsoft Defender Antivirus kan blockera misstänkta filer från att köras medan de frågar om vår moln levererad skyddstjänst. Du kan konfigurera hur lång tid filen hindras från att köras med Microsoft Endpoint Manager och Grupprincip.