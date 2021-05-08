---
title: Felsöka licensproblem för Microsoft Defender för slutpunkt på Mac
description: Felsöka licensproblem i Microsoft Defender för slutpunkt på Mac.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, mac, prestanda
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
ms.openlocfilehash: 1f8428c2995eec2dece290049eda67a3683b4c1e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244986"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Felsöka licensproblem för Microsoft Defender för slutpunkt i macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint för macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

När du går igenom Microsoft Defender för Slutpunkt på [macOS](microsoft-defender-endpoint-mac.md) och [testa manuell](mac-install-manually.md) distribution eller ett PoC (Proof Of Concept) kan du få följande felmeddelande:

![Bild på licensfel](images/no-license-found.png)

**Meddelande:** 

Ingen licens hittades

Det verkar som att din organisation inte har någon licens för Microsoft 365 Enterprise prenumeration.

Kontakta administratören om du behöver hjälp.

**Orsak:** 

Du har distribuerat och/eller installerat Microsoft Defender för Slutpunkt för macOS-paketet ("Ladda ned installationspaket"), men du kanske har kört konfigurationsskriptet ("Hämta onboarding-paket") eller så har du inte tilldelat någon licens till användaren.

**Lösning:**

Följ de MicrosoftDefenderATPOnboardingMacOs.py som beskrivs här: [Klientkonfiguration](mac-install-manually.md#client-configuration)
