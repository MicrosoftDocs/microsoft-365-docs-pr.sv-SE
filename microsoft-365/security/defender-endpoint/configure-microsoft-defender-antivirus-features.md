---
title: Konfigurera funktionerna i Microsoft Defender Antivirus
description: Du kan Microsoft Defender Antivirus funktioner med Intune, Microsoft Endpoint Configuration Manager, Grupprincip och PowerShell.
keywords: Microsoft Defender Antivirus, antimalware, säkerhet, defender, konfigurera, konfiguration, konfiguration, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, hantering av mobila enheter, GP, grupprincip, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4408d5e788449c0d094008261f5e7db9bfe38758
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275114"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>Konfigurera funktionerna i Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan Microsoft Defender Antivirus med ett antal verktyg, bland annat:

- Microsoft Intune
- Microsoft Endpoint Configuration Manager
- Grupprincip
- PowerShell-cmdlets
- Windows Management Instrumentation (WMI)

Du kan konfigurera följande breda kategorier av funktioner:

- Molnbaserat skydd
- Ständigt realtidsskydd, inklusive beteende, heuristiskt och maskininlärningsbaserat skydd
- Hur slutanvändare interagerar med klienten i enskilda slutpunkter

I följande artiklar beskrivs hur du utför viktiga uppgifter när du konfigurerar Microsoft Defender Antivirus. Varje artikel innehåller instruktioner för det tillämpliga konfigurationsverktyget (eller verktygen).

|Artikel  |Beskrivning  |
|---------|---------|
|[Använd Microsofts molnbaserade Microsoft Defender Antivirus skydd](cloud-protection-microsoft-defender-antivirus.md)     | Använd moln levererat skydd för avancerad, snabb och robust antivirusidentifiering.        |
|[Konfigurera skydd för beteende, heuristisk och realtid](configure-protection-features-microsoft-defender-antivirus.md)     |Aktivera funktionsbaserat, heuristiskt och realtidsskydd för antivirus.         |
|[Konfigurera slutanvändares interaktion med Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) | Konfigurera hur slutanvändarna i organisationen interagerar med Microsoft Defender Antivirus, vilka meddelanden de ser och om de kan åsidosätta inställningar. |

> [!TIP]
> Du kan också läsa avsnittet [Referensavsnitt för hanterings- och konfigurationsverktyg,](configuration-management-reference-microsoft-defender-antivirus.md) där det finns en översikt över de olika verktygen samt länkar till ytterligare hjälp.