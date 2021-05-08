---
title: Återställa filer i karantän i Microsoft Defender AV
description: Du kan återställa filer och mappar som har satts i karantän av Microsoft Defender AV.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/20/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: e0253c4ac7d92c91e3fda45681568d721645f2b0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275390"
---
# <a name="restore-quarantined-files-in-microsoft-defender-av"></a>Återställa filer i karantän i Microsoft Defender AV

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Om Microsoft Defender Antivirus har konfigurerats för att identifiera och åtgärda hot på din enhet Microsoft Defender Antivirus du misstänkta filer i karantän. Om du har en fil i karantän som inte är ett hot kan du återställa den.

1. Öppna **Windows-säkerhet**.
2. Välj **Virus & skydd mot hot och** klicka sedan på **Säkerhetshistorik**.
3. I listan över de senaste objekten filtrerar du på **Objekt i karantän.**
4. Markera ett objekt som du vill behålla och vidta en åtgärd, till exempel återställa.

> [!TIP]
> Återställning av en fil från karantän kan också göras med kommandotolken. Se [Återställa en fil från karantän](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts#restore-file-from-quarantine). 

## <a name="related-articles"></a>Relaterade artiklar

- [Konfigurera åtgärd för genomsökningar](configure-remediation-microsoft-defender-antivirus.md)
- [Granska genomsökningsresultat](review-scan-results-microsoft-defender-antivirus.md)
- [Konfigurera och validera undantag baserat på filnamn, filnamnstillägg och mappplats](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Konfigurera och validera undantag för filer som öppnas i processer](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Konfigurera Microsoft Defender Antivirus undantag på Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md)