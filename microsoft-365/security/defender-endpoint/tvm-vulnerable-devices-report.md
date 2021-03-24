---
title: Rapport om sårbara enheter – hantering av hot och sårbarhet
description: En rapport som visar sårbar enhetstrender och aktuell statistik. Målet är att du förstår andan och omfattningen av din enhets exponering.
keywords: mdatp-tvm sårbara enheter, mdatp, tvm, minska & exponering av risken, minska risken och risken, övervaka säkerhetskonfiguration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 92866addbcdae2bde3dd8de55f63b03414878fd7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072817"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a>Rapport om sårbara enheter – hantering av hot och sårbarhet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Hantering av hot och sårbarhet](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Rapporten visar diagram och stapeldiagram med sårbar enhetstrender och aktuell statistik. Målet är att du förstår andan och omfattningen av din enhets exponering. 

Öppna rapporten i Microsoft Defender Säkerhetscenter genom att gå till **Rapporter för > sårbara enheter**

Det finns två kolumner:

- Trender (över tid). Kan visa de senaste 30 dagarna, 3 månader, 6 månader eller ett anpassat datumintervall.
- I dag (aktuell information)

**Filter:** Du kan filtrera data efter allvarlighetsnivåer, sårbarhet, sårbarhet, ålder, operativsystemsplattform, Windows 10-version eller enhetsgrupp.

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

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a>Sårbara enheter i Windows 10-versionsdiagram

Antalet enheter i varje Windows 10-version som exponeras på grund av sårbara program eller operativsystem.

![Ett diagram över aktuella sårbara enheter med Windows 10-versionen och ett diagram som visar sårbara enheter med windows 10-version över tid.](images/tvm-report-version.png)

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över hot- och sårbarhetshantering](next-gen-threat-and-vuln-mgt.md)
- [Säkerhetsrekommendationer](tvm-security-recommendation.md)
