---
title: Konfigurera Microsoft Defender Antivirus med Microsoft Endpoint Manager
description: Använd Microsoft Endpoint Manager och Microsoft Intune för att konfigurera Microsoft Defender AV och Endpoint Protection
keywords: s den, intune, slutpunktsskydd, konfiguration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: ab77f3ab5ac9385d1ce049061730d2192e3bcb0c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683757"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a>Använda Microsoft Endpoint Manager för att konfigurera och hantera Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan använda [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) för att konfigurera Microsoft Defender Antivirus genomsökningar. [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) och [Konfigurationshanteraren](/mem/configmgr/core/understand/introduction) är nu en del av Endpoint Manager.  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a>Konfigurera Microsoft Defender Antivirus skanningar i Endpoint Manager

1. Gå till Microsoft Endpoint Manager ( ) [https://endpoint.microsoft.com](https://endpoint.microsoft.com) och logga in.

2. Gå till **Slutpunktssäkerhet**.

3. Välj **Antivirus** under **Hantera.**

4. Välj Microsoft Defender Antivirus princip. 

5. Under **Hantera** väljer du **Egenskaper**.

6. Välj **Redigera** bredvid **Konfigurationsinställningar**.

7. Expandera avsnittet **Skanna** och granska eller redigera inställningarna för skanning.

8. Välj **Granska + spara**


> [!TIP]
> Behöver du hjälp? Se [Hantera slutpunktssäkerhet i Microsoft Intune](/mem/intune/protect/endpoint-security).


## <a name="related-articles"></a>Relaterade artiklar

- [Referensartiklar för hantering och konfigurationsverktyg](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)