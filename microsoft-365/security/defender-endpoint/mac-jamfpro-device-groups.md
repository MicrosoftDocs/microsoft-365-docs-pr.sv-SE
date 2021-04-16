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
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a><span data-ttu-id="99141-104">Konfigurera Microsoft Defender för Slutpunkt på macOS-enhetsgrupper i Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="99141-104">Set up Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="99141-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="99141-105">**Applies to:**</span></span>
- [<span data-ttu-id="99141-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="99141-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="99141-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="99141-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="99141-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="99141-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="99141-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="99141-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="99141-110">Konfigurera enhetsgrupper som liknar organisationsgrupper för grupprinciper, Enhetssamling för Microsoft Endpoint Configuration Manager och Intune-enhetsgrupperna i Intune.</span><span class="sxs-lookup"><span data-stu-id="99141-110">Set up the device groups similar to Group policy  organizational unite (OUs), Microsoft Endpoint Configuration Manager's device collection, and Intune's device groups.</span></span>

1. <span data-ttu-id="99141-111">Gå till **statiska datorgrupper.**</span><span class="sxs-lookup"><span data-stu-id="99141-111">Navigate to **Static Computer Groups**.</span></span>

2. <span data-ttu-id="99141-112">Välj **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="99141-112">Select **New**.</span></span> 

    ![Bild på Jamf Pro1](images/jamf-pro-static-group.png)

3. <span data-ttu-id="99141-114">Ange ett visningsnamn och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="99141-114">Provide a display name and select **Save**.</span></span>

    ![Bild på Jamf Pro2](images/jamfpro-machine-group.png)

4. <span data-ttu-id="99141-116">Nu kommer du att se **Contosos datorgrupp under Statiska** **datorgrupper.**</span><span class="sxs-lookup"><span data-stu-id="99141-116">Now you will see the **Contoso's Machine Group** under **Static Computer Groups**.</span></span>

    ![Bild på Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a><span data-ttu-id="99141-118">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="99141-118">Next step</span></span>
- [<span data-ttu-id="99141-119">Konfigurera Microsoft Defender för Slutpunkt på macOS-principer i Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="99141-119">Set up Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
