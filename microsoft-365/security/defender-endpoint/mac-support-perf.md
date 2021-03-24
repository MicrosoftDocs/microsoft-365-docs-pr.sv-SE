---
title: Felsöka prestandaproblem för Microsoft Defender ATP för Mac
description: Felsöka prestandaproblem i Microsoft Defender ATP för Mac.
keywords: microsoft, defender, atp, mac, performance
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
ms.openlocfilehash: dbd82bae86ac4181497ecc87bc74181f7a502e15
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070258"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Felsöka prestandaproblem för Microsoft Defender för Slutpunkt för Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Slutpunkt för Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Det här avsnittet innehåller några allmänna steg som kan användas för att begränsa prestandaproblem som rör Microsoft Defender för Slutpunkt för Mac.

Realtidsskydd (RTP) är en funktion i Microsoft Defender för Endpoint för Mac som kontinuerligt övervakar och skyddar din enhet mot hot. Den består av fil- och processövervakning och annan heuristics.

Beroende på vilka program du kör och enhetens egenskaper kan du uppleva underoptimal prestanda när du kör Microsoft Defender för Endpoint för Mac. Särskilt program eller systemprocesser som har åtkomst till många resurser under ett kort tidspann kan leda till prestandaproblem i Microsoft Defender för Slutpunkt för Mac.

Följande steg kan användas för att felsöka och minimera dessa problem:

1. Inaktivera realtidsskyddet med någon av följande metoder och se om prestandan förbättras. Den här metoden begränsar om Microsoft Defender för Endpoint för Mac bidrar till prestandaproblemen.

    Om din enhet inte hanteras av din organisation kan realtidsskydd inaktiveras med något av följande alternativ:

    - Från användargränssnittet. Öppna Microsoft Defender för Slutpunkt för Mac och gå till **Hantera inställningar.**

      ![Skärmbild på Hantera realtidsskydd](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-36-rtp)

    - Från terminalen. Av säkerhetsskäl kräver den här åtgärden höjd.

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    Om enheten hanteras av din organisation kan realtidsskydd inaktiveras av administratören genom att följa anvisningarna i Ange inställningar för Microsoft Defender för [Slutpunkt för Mac.](mac-preferences.md)

2. Öppna Finder och gå **till**  >  **Programverktyg.** Öppna **Aktivitetsrapporter** och analysera vilka program som använder resurserna på ditt system. Vanliga exempel är programuppdateringsprogram och kompilatorer.

3. Konfigurera Microsoft Defender för slutpunkt för Mac med undantag för de processer eller diskutrymmen som bidrar till prestandaproblemen och återaktivera realtidsskydd.

    Mer [information finns i Konfigurera och validera undantag för Microsoft Defender för Slutpunkt](mac-exclusions.md) för Mac.
