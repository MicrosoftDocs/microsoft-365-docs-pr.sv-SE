---
title: Felsöka licensproblem för Microsoft Defender för Slutpunkt för Mac
description: Felsöka licensproblem i Microsoft Defender för Slutpunkt för Mac.
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
ms.openlocfilehash: 3fb351d9ce8e9beef812e6aaa7d463161a6af8df
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862193"
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

Det verkar som att din organisation inte har någon licens för Microsoft 365 Enterprise-prenumeration.

Kontakta administratören om du behöver hjälp.

**Orsak:** 

Du har distribuerat och/eller installerat Microsoft Defender för slutpunkt på macOS-paket ("Ladda ned installationspaket") men du kanske har kört konfigurationsskriptet ("Hämta onboarding package").

**Lösning:**

Följ de MicrosoftDefenderATPOnboardingMacOs.py som beskrivs här: [Klientkonfiguration](mac-install-manually.md#client-configuration)

