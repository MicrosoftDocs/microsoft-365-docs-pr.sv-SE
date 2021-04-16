---
title: Distribuera Microsoft Defender för Slutpunkt för macOS med Jamf Pro
description: Distribuera Microsoft Defender för Slutpunkt för macOS med Jamf Pro
keywords: microsoft, defender, atp, mac, installation, distribuera, avinstallation, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: e49a56b138e792f06229345d19a5867c9f6438af
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862265"
---
# <a name="deploying-microsoft-defender-for-endpoint-on-macos-with-jamf-pro"></a><span data-ttu-id="232c3-104">Distribuera Microsoft Defender för slutpunkt på macOS med Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="232c3-104">Deploying Microsoft Defender for Endpoint on macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="232c3-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="232c3-105">**Applies to:**</span></span>
- [<span data-ttu-id="232c3-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="232c3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="232c3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="232c3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="232c3-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="232c3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="232c3-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="232c3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="232c3-110">Lär dig hur du distribuerar Microsoft Defender för slutpunkt på macOS med Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="232c3-110">Learn how to deploy Microsoft Defender for Endpoint on macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="232c3-111">Om du använder macOS Catalina (10.15.4) eller senare versioner av macOS, se Nya konfigurationsprofiler för [macOS Catalina](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies)och nyare versioner av macOS.</span><span class="sxs-lookup"><span data-stu-id="232c3-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="232c3-112">Det här innebär en process i flera steg.</span><span class="sxs-lookup"><span data-stu-id="232c3-112">This is a multi step process.</span></span> <span data-ttu-id="232c3-113">Du måste slutföra alla följande steg:</span><span class="sxs-lookup"><span data-stu-id="232c3-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="232c3-114">Logga in på Portal För att logga in på Jamf</span><span class="sxs-lookup"><span data-stu-id="232c3-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="232c3-115">Konfigurera Microsoft Defender för slutpunkt på macOS-enhetsgrupper i Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="232c3-115">Setup the Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="232c3-116">Konfigurera Principer för Microsoft Defender för slutpunkt på macOS i Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="232c3-116">Setup the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="232c3-117">Registrera Microsoft Defender för Slutpunkt på macOS-enheter till Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="232c3-117">Enroll the Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




