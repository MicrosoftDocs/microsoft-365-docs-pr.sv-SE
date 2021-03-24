---
title: Vad är nytt i Microsoft Defender för Endpoint för Linux
description: Lista över större ändringar för Microsoft Defender ATP för Linux.
keywords: microsoft, defender, atp, linux, whatsnew, release
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: 43324b0f3a0d5d351d7164bb05415899bf7d181c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070489"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a>Vad är nytt i Microsoft Defender för Endpoint för Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1011853"></a>101.18.53

- EDR för Linux är nu [tillgängligt i allmänhet](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)
- Lade till en ny kommandoradsväxel ( `--ignore-exclusions` ) för att ignorera AV-undantag vid anpassade genomsökningar ( `mdatp scan custom` )
- Utökad `mdatp diagnostic create` med en ny parameter `--path [directory]` () som gör att diagnostikloggarna kan sparas i en annan katalog
- Prestandaförbättringar & felkorrigeringar

## <a name="1011299"></a>101.12.99

- Prestandaförbättringar & felkorrigeringar

## <a name="1010476"></a>101.04.76

- Felkorrigeringar

## <a name="1010348"></a>101.03.48

- Felkorrigeringar

## <a name="1010255"></a>101.02.55

- Åtgärdat ett problem där produkten ibland inte startar efter en omstart/uppgradering
- Åtgärdat ett problem där proxyinställningarna inte beständiga under produktuppgraderingar

## <a name="1010075"></a>101.00.75

- Lade till stöd för följande filsystemtyper: `ecryptfs` , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` och `vfat`
- Ny syntax för [kommandoradsverktyget](linux-resources.md#configure-from-the-command-line).
- Prestandaförbättringar & felkorrigeringar

## <a name="1009070"></a>100.90.70

> [!WARNING]
> När du uppgraderar det installerade paketet från en tidigare produktversion än 100.90.70 kan uppdateringen misslyckas på Red Hat-baserade distributions- och SLES-distributioner. Det beror på en stor förändring i en filsökväg. En tillfällig lösning är att ta bort det äldre paketet och sedan installera det nyare. Det här problemet finns inte i nyare versioner.

- Undantag [från antivirus har nu stöd för jokertecken](linux-exclusions.md#supported-exclusion-types)
- Möjligheten att felsöka [prestandaproblem med](linux-support-perf.md) kommandoradsverktyget `mdatp` har lagts till
- Förbättringar för att göra paketinstallationen robustare
- Prestandaförbättringar & felkorrigeringar
