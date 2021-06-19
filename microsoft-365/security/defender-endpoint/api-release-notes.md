---
title: Information om Microsoft Defender för Endpoint API
description: Information om uppdateringar av Microsoft Defender för slutpunktsuppsättningen API:er.
keywords: Information om Microsoft Defender för endpoint API– utgivningsanteckningar, mde- och API:er, Microsoft Defender för slutpunkts-API, uppdateringar, anteckningar, utgivning
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 5e72db8d986ad096d6312f90530d9f9ff246afc3
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022300"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a>Information om Microsoft Defender för Endpoint API

**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Följande information innehåller uppdateringar av Microsoft Defender för slutpunkts-API:er och datum då de gjordes.

> [!TIP]
> RSS-feed: Få ett meddelande när sidan uppdateras genom att kopiera och klistra in följande URL i din feedläsare:
>
> ```http
> /api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a>Utgivningsanteckningar – nyaste till äldsta (dd.mm.yyyy)

### <a name="06102021"></a>06.10.2021

- Ny exportutvärderings-API-metod – säkerhetsbedömning av deltaexportprogramvara _(JSON-svar) Exportera_ [utvärderingsmetoder och egenskaper per enhet.](get-assessment-methods-properties.md)

### <a name="05252021"></a>05.25.2021

- Nya API Exportera [utvärderingsmetoder och egenskaper per enhet](get-assessment-methods-properties.md)har lagts till.

### <a name="03052021"></a>03.05.2021

- Nytt API har lagts till: [Metoder och egenskaper för åtgärdsaktivitet.](get-remediation-methods-properties.md)

### <a name="10022021"></a>10.02.2021

- Nytt API har lagts till: [Batchuppdateringsaviseringar](batch-update-alerts.md).

### <a name="25012021"></a>25.01.2021

- Uppdaterade räntebegränsningar [för Advanced Hunting API](run-advanced-query-api.md) från 15 till 45 förfrågningar per minut.

### <a name="21012021"></a>21.01.2021

- Nytt API har lagts till: [Hitta enheter efter tagg.](machine-tags.md)
- Nytt API har lagts till: [Importindikatorer](import-ti-indicators.md).

### <a name="03012021"></a>03.01.2021

- Uppdaterade aviserings bevis: lade till ***detectionStatus** _, _*_parentProcessFilePath_*_ och _ *_parentProcessFileName_** egenskaper.
- Uppdaterad [avisering entitet:](alerts.md)lade ***till egenskapen id-egenskap.***

### <a name="15122020"></a>15.12.2020

- Uppdaterad [](machine.md) enhetsentitet: ***IpInterfaces-lista*** tillagd. Se [Listenheter](get-machines.md).

### <a name="04112020"></a>04.11.2020

- Nytt API har lagts till: [Ange enhetsvärde](set-device-value.md).
- Uppdaterade [enhetsentitet:](machine.md) egenskapen ***deviceValue*** tillagd.

### <a name="01092020"></a>01.09.2020

- Lade till alternativ för att expandera aviseringsenheten med tillhörande bevis. Visa [listaviseringar](get-alerts.md).
