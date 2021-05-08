---
title: Distribuera uppdateringar för Microsoft Defender för Slutpunkt i Linux
ms.reviewer: ''
description: Här beskrivs hur du distribuerar uppdateringar för Microsoft Defender för Endpoint på Linux i företagsmiljöer.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, linux, uppdateringar, distribuera
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
ms.openlocfilehash: fc5a64f4be1b782c423c2ae9e2222a1424be97e0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274730"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a>Distribuera uppdateringar för Microsoft Defender för Slutpunkt i Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft publicerar regelbundet programuppdateringar för att förbättra prestanda, säkerhet och för att leverera nya funktioner.

> [!WARNING]
> Varje version av Defender för Slutpunkt på Linux har ett utgångsdatum. Därefter kommer den inte längre att fortsätta att skydda din enhet. Du måste uppdatera produkten före detta datum. Kör följande kommando för att kontrollera utgångsdatumet:
> ```bash
> mdatp health --field product_expiration
> ```


Allmänt tillgängliga Microsoft Defender för slutpunktsfunktioner är motsvarande oavsett uppdateringskanal som används för en distribution (Beta (Insider), Förhandsversion (extern), Aktuell (Produktion)).


Om du vill uppdatera Defender för slutpunkt i Linux manuellt kör du något av följande kommandon:

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
