---
title: Distribuera uppdateringar för Microsoft Defender ATP för Linux
ms.reviewer: ''
description: Här beskrivs hur du distribuerar uppdateringar för Microsoft Defender ATP för Linux i företagsmiljöer.
keywords: microsoft, defender, atp, linux, uppdateringar, distribuera
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
ms.openlocfilehash: adc19192764e8c57a20f14cc908be23e8d9bdbc8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51070490"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="e4bd3-104">Distribuera uppdateringar för Microsoft Defender för Endpoint för Linux</span><span class="sxs-lookup"><span data-stu-id="e4bd3-104">Deploy updates for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e4bd3-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="e4bd3-105">**Applies to:**</span></span>
- [<span data-ttu-id="e4bd3-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="e4bd3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="e4bd3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e4bd3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e4bd3-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="e4bd3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e4bd3-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="e4bd3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="e4bd3-110">Microsoft publicerar regelbundet programuppdateringar för att förbättra prestanda, säkerhet och för att leverera nya funktioner.</span><span class="sxs-lookup"><span data-stu-id="e4bd3-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="e4bd3-111">Varje version av Defender för Endpoint för Linux har ett utgångsdatum, därefter fortsätter den inte att skydda din enhet.</span><span class="sxs-lookup"><span data-stu-id="e4bd3-111">Each version of Defender for Endpoint for Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="e4bd3-112">Du måste uppdatera produkten före detta datum.</span><span class="sxs-lookup"><span data-stu-id="e4bd3-112">You must update the product prior to this date.</span></span> <span data-ttu-id="e4bd3-113">Kör följande kommando för att kontrollera utgångsdatumet:</span><span class="sxs-lookup"><span data-stu-id="e4bd3-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```

<span data-ttu-id="e4bd3-114">Om du vill uppdatera Defender för Slutpunkt för Linux manuellt kör du något av följande kommandon:</span><span class="sxs-lookup"><span data-stu-id="e4bd3-114">To update Defender for Endpoint for Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="e4bd3-115">RHEL och varianter (CentOS och Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="e4bd3-115">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="e4bd3-116">SLES och varianter</span><span class="sxs-lookup"><span data-stu-id="e4bd3-116">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="e4bd3-117">Ubuntu och Ubuntu systems</span><span class="sxs-lookup"><span data-stu-id="e4bd3-117">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
