---
title: Felsöka licensproblem för Microsoft Defender ATP för Mac
description: Felsöka licensproblem i Microsoft Defender ATP för Mac.
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
ms.openlocfilehash: 44105ae8d1872c3ecefcf84a5e2efef122849b8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074466"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Felsöka licensproblem för Microsoft Defender för Slutpunkt för Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Slutpunkt för Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

När du går igenom [Microsoft Defender](microsoft-defender-endpoint-mac.md) för Endpoint för Mac och testa [manuell](mac-install-manually.md) distribution eller använder PoC (Proof Of Concept) kan du få följande felmeddelande:

![Bild på licensfel](images/no-license-found.png)

**Meddelande:** 

Ingen licens hittades

Det verkar som att din organisation inte har någon licens för Microsoft 365 Enterprise-prenumeration.

Kontakta administratören om du behöver hjälp.

**Orsak:** 

Du har distribuerat och/eller installerat Microsoft Defender för slutpunkt för macOS-paketet ("Ladda ned installationspaket") men du kanske har kört konfigurationsskriptet ("Hämta registreringspaket").

**Lösning:**

Följ de MicrosoftDefenderATPOnboardingMacOs.py som beskrivs här: [Klientkonfiguration](mac-install-manually.md#client-configuration)

