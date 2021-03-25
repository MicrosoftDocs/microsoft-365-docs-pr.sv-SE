---
title: Distribuera uppdateringar för Microsoft Defender ATP för Linux
ms.reviewer: ''
description: Här beskrivs hur du distribuerar uppdateringar för Microsoft Defender ATP för Linux i företagsmiljöer.
keywords: microsoft, defender, atp, linux, uppdateringar, distribuera
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ad37427e8134c574690c3b3553d7fb9b8507593c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187727"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-linux"></a>Distribuera uppdateringar för Microsoft Defender för Endpoint för Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft publicerar regelbundet programuppdateringar för att förbättra prestanda, säkerhet och för att leverera nya funktioner.

> [!WARNING]
> Varje version av Defender för Endpoint för Linux har ett utgångsdatum, därefter fortsätter den inte att skydda din enhet. Du måste uppdatera produkten före detta datum. Kör följande kommando för att kontrollera utgångsdatumet:
> ```bash
> mdatp health --field product_expiration
> ```

Om du vill uppdatera Defender för Slutpunkt för Linux manuellt kör du något av följande kommandon:

## <a name="rhel-and-variants-centos-and-oracle-linux"></a>RHEL och varianter (CentOS och Oracle Linux)

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a>SLES och varianter

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a>Ubuntu och Ubuntu systems

```bash
sudo apt-get install --only-upgrade mdatp
```
