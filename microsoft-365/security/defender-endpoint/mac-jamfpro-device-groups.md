---
title: Konfigurera enhetsgrupper i Jamf Pro
description: Lär dig konfigurera enhetsgrupper i Jamf Pro för Microsoft Defender för Endpoint för macOS
keywords: enhet, grupp, microsoft, defender, atp, mac, installation, distribuera, avinstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 80dcb4ff73edd5e95603b15e097232a43dc0e05e
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861617"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>Konfigurera Microsoft Defender för Slutpunkt på macOS-enhetsgrupper i Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Konfigurera enhetsgrupper som liknar organisationsgrupper för grupprinciper, Enhetssamling för Microsoft Endpoint Configuration Manager och Intune-enhetsgrupperna i Intune.

1. Gå till **statiska datorgrupper.**

2. Välj **Nytt**. 

    ![Bild på Jamf Pro1](images/jamf-pro-static-group.png)

3. Ange ett visningsnamn och välj **Spara**.

    ![Bild på Jamf Pro2](images/jamfpro-machine-group.png)

4. Nu kommer du att se **Contosos datorgrupp under Statiska** **datorgrupper.**

    ![Bild på Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a>Nästa steg
- [Konfigurera Microsoft Defender för Slutpunkt på macOS-principer i Jamf Pro](mac-jamfpro-policies.md)
