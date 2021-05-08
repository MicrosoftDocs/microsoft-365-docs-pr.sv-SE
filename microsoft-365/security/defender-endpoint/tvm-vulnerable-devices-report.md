---
title: Rapport om sårbara enheter – Hantering av hot och säkerhetsrisker
description: En rapport som visar sårbar enhetstrender och aktuell statistik. Målet är att du förstår andan och omfattningen av din enhets exponering.
keywords: Microsoft Defender för slutpunkts-TVm-sårbara enheter, Microsoft Defender för slutpunkt, tvm, minska risken & exponering för sårbarhet, minska risken och risken, övervaka säkerhetskonfiguration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 355561936642b1fa38228bfa07ad59269c48d817
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245486"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a>Rapport om sårbara enheter – Hantering av hot och säkerhetsrisker

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Hot och hantering av säkerhetsrisker](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Rapporten visar diagram och stapeldiagram med sårbar enhetstrender och aktuell statistik. Målet är att du förstår andan och omfattningen av din enhets exponering.

Få tillgång till rapporten i Microsoft Defender Säkerhetscenter genom att **gå till Rapporter > sårbara enheter**

Det finns två kolumner:

- Trender (över tid). Kan visa de senaste 30 dagarna, 3 månader, 6 månader eller ett anpassat datumintervall.
- I dag (aktuell information)

**Filter:** Du kan filtrera data efter allvarlighetsnivåer, sårbarhet, sårbarhet, ålder, operativsystemsplattform, Windows 10 version eller enhetsgrupp.

**Öka detaljnivån**: Om det finns en insikt som du vill utforska ytterligare väljer du relevant stapeldiagram för att visa en filtrerad lista med enheter på sidan Enhetslager. Därifrån kan du exportera listan.

## <a name="severity-level-graphs"></a>Diagram för allvarlighetsnivå

Varje enhet räknas bara en gång enligt det mest allvarliga problemet på enheten.

![Ett diagram över olika allvarlighetsnivåer för enheter och ett diagram som visar nivåer över tid.](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a>Utnyttja tillgänglighetsdiagram

Varje enhet räknas bara en gång baserat på den högsta nivån av känd sårbarhet.

![Ett diagram över aktuell enhets sårbarhetstillgänglighet och ett diagram som visar tillgänglighet över tid.](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a>Diagram över sårbarhetsåldern

Varje enhet räknas bara en gång under datumet för den äldsta sårbarhetspublikationen. Äldre säkerhetsproblem har större risk att utnyttjas.

![Ett diagram över den aktuella enhetens sårbarhets ålder och ett diagram som visar ålder över tid.](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a>Sårbara enheter efter operativsystemsplattformsgrafer

Antalet enheter i varje operativsystem som exponeras på grund av säkerhetsproblem med programvara.

![Ett diagram över aktuella sårbara enheter efter operativsystemplattform och ett diagram som visar sårbara enheter för os-plattformar över tid.](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a>Sårbara enheter som kan Windows 10 av versionsdiagram

Antalet enheter på varje version Windows 10 exponeras på grund av sårbara program eller operativsystem.

![Ett diagram över aktuella sårbara enheter i Windows 10 version, och ett diagram som visar sårbara enheter Windows 10 version över tid.](images/tvm-report-version.png)

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över hantering av säkerhetsrisker hot och hot](next-gen-threat-and-vuln-mgt.md)
- [Säkerhetsrekommendationer](tvm-security-recommendation.md)
