---
title: Konfigurera enhetsgrupper i Jamf Pro
description: Lär dig konfigurera enhetsgrupper i Jamf Pro för Microsoft Defender ATP för macOS
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
ms.openlocfilehash: 6c1d6ae5d4635186bf0a1cbb55c7f906e8584f01
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689695"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a><span data-ttu-id="654bb-104">Konfigurera Microsoft Defender för Slutpunkt på macOS-enhetsgrupper i Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="654bb-104">Set up Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="654bb-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="654bb-105">**Applies to:**</span></span>
- [<span data-ttu-id="654bb-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="654bb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="654bb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="654bb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="654bb-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="654bb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="654bb-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="654bb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="654bb-110">Konfigurera enhetsgrupper som liknar organisationsgrupper för grupprinciper, Enhetssamling för Microsoft Endpoint Configuration Manager och Intune-enhetsgrupperna i Intune.</span><span class="sxs-lookup"><span data-stu-id="654bb-110">Set up the device groups similar to Group policy  organizational unite (OUs), Microsoft Endpoint Configuration Manager's device collection, and Intune's device groups.</span></span>

1. <span data-ttu-id="654bb-111">Gå till **statiska datorgrupper.**</span><span class="sxs-lookup"><span data-stu-id="654bb-111">Navigate to **Static Computer Groups**.</span></span>

2. <span data-ttu-id="654bb-112">Välj **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="654bb-112">Select **New**.</span></span> 

    ![Bild på Jamf Pro1](images/jamf-pro-static-group.png)

3. <span data-ttu-id="654bb-114">Ange ett visningsnamn och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="654bb-114">Provide a display name and select **Save**.</span></span>

    ![Bild på Jamf Pro2](images/jamfpro-machine-group.png)

4. <span data-ttu-id="654bb-116">Nu kommer du att se **Contosos datorgrupp under Statiska** **datorgrupper.**</span><span class="sxs-lookup"><span data-stu-id="654bb-116">Now you will see the **Contoso's Machine Group** under **Static Computer Groups**.</span></span>

    ![Bild på Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a><span data-ttu-id="654bb-118">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="654bb-118">Next step</span></span>
- [<span data-ttu-id="654bb-119">Konfigurera Microsoft Defender för Slutpunkt på macOS-principer i Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="654bb-119">Set up Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
