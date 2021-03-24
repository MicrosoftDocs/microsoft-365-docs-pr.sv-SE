---
title: Information om Microsoft Defender för Endpoint API
description: Information om uppdateringar av Microsoft Defender för slutpunktsuppsättningen API:er.
keywords: Microsoft Defender för viktiga kommentarer till endpoint api, mde, apis, mdatp api, uppdateringar, anteckningar, utgivning
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
ms.technology: mde
ms.openlocfilehash: e37841fa17a5998c431c6a76b878f20ef1b06d10
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069842"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a>Information om Microsoft Defender för Endpoint API

**Gäller för:** [Microsoft Defender för slutpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Följande information innehåller uppdateringar av Microsoft Defender för slutpunkts-API:er och datum då de gjordes.


> [!TIP]
> RSS-feed: Få ett meddelande när sidan uppdateras genom att kopiera och klistra in följande URL i din feedläsare: 
>```
>https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
>```


### <a name="10022021"></a>10.02.2021
<hr>

- Nytt API har lagts till: [Batchuppdateringsaviseringar](batch-update-alerts.md). 

<br>

### <a name="25012021"></a>25.01.2021
<hr>

- Uppdaterade räntebegränsningar [för Advanced Hunting API](run-advanced-query-api.md) från 15 till 45 förfrågningar per minut. 

<br>

### <a name="21012021"></a>21.01.2021
<hr>

- Nytt API har lagts till: [Hitta enheter efter tagg.](machine-tags.md) 
- Nytt API har lagts till: [Importindikatorer](import-ti-indicators.md). 

<br>

### <a name="03012021"></a>03.01.2021
<hr>

- Uppdaterade aviserings bevis: lade till ***detectionStatus** _, _*_parentProcessFilePath_*_ och _ *_parentProcessFileName_** egenskaper.
- Uppdaterad [avisering entitet:](alerts.md)lade ***till egenskapen id-egenskap.***

<br>

### <a name="15122020"></a>15.12.2020
<hr>

- Uppdaterad [](machine.md) enhetsentitet: ***IpInterfaces-lista*** tillagd. Se [Listenheter](get-machines.md).

<br>

### <a name="04112020"></a>04.11.2020
<hr>

- Nytt API har lagts till: [Ange enhetsvärde](set-device-value.md).
- Uppdaterade [enhetsentitet:](machine.md) egenskapen ***deviceValue*** tillagd.

<br>

### <a name="01092020"></a>01.09.2020
<hr>

- Lade till alternativ för att expandera aviseringsenheten med tillhörande bevis. Visa [listaviseringar](get-alerts.md).

<br>
<br>