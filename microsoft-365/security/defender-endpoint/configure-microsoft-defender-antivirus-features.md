---
title: Konfigurera funktioner för Microsoft Defender Antivirus
description: Du kan konfigurera antivirusfunktionerna i Microsoft Defender med Intune, Microsoft Endpoint Configuration Manager, Grupprincip och PowerShell.
keywords: Microsoft Defender Antivirus, antimalware, säkerhet, defender, konfigurera, konfiguration, konfigurationshanteraren, Microsoft Endpoint Configuration Manager, SCCM, Intune, MDM, hantering av mobila enheter, GP, grupprincip, PowerShell
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/18/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8503bb5bdd6337ec60390ef1d8e59f6f506fbce2
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765173"
---
# <a name="configure-microsoft-defender-antivirus-features"></a>Konfigurera funktioner för Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Du kan konfigurera Microsoft Defender Antivirus med ett antal verktyg, till exempel:

- Microsoft Intune
- Microsoft Endpoint Configuration Manager
- Grupprincip
- PowerShell-cmdlets
- Windows Management Instrumentation (WMI)

Du kan konfigurera följande breda kategorier av funktioner:

- Moln levererat skydd
- Ständigt realtidsskydd, inklusive beteende, heuristiskt och maskininlärningsbaserat skydd
- Hur slutanvändare interagerar med klienten i enskilda slutpunkter

I följande artiklar beskrivs hur du utför viktiga uppgifter när du konfigurerar Microsoft Defender Antivirus. Varje artikel innehåller instruktioner för det tillämpliga konfigurationsverktyget (eller verktygen).

|Artikel  |Beskrivning  |
|---------|---------|
|[Använd Microsofts molnskydd med Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)     | Använd moln levererat skydd för avancerad, snabb och robust antivirusidentifiering.        |
|[Konfigurera behavioruellt, heuristiskt och realtidsskydd](configure-protection-features-microsoft-defender-antivirus.md)     |Aktivera funktionsbaserat, heuristiskt och realtidsskydd för antivirus.         |
|[Konfigurera interaktion med slutanvändare med Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) | Konfigurera hur slutanvändarna i organisationen interagerar med Microsoft Defender Antivirus, vilka meddelanden de ser och om de kan åsidosätta inställningar. |

> [!TIP]
> Du kan också läsa avsnittet [Referensavsnitt för hanterings- och konfigurationsverktyg,](configuration-management-reference-microsoft-defender-antivirus.md) där det finns en översikt över de olika verktygen samt länkar till ytterligare hjälp.