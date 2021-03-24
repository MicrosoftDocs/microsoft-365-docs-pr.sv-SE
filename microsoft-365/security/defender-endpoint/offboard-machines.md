---
title: Offboard-enheter från Microsoft Defender ATP-tjänsten
description: Introducera Windows 10-enheter, servrar, icke-Windows-enheter från Microsoft Defender ATP-tjänsten
keywords: offboarding, microsoft defender för slutpunkt offboarding, fönster atp offboarding
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: db22a19da58ba70ff09af781ca56e0b3c0d88dfd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069217"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="28458-104">Offboard-enheter från Microsoft Defender för Slutpunkt-tjänsten</span><span class="sxs-lookup"><span data-stu-id="28458-104">Offboard devices from the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="28458-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="28458-105">**Applies to:**</span></span>
- [<span data-ttu-id="28458-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="28458-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="28458-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="28458-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="28458-108">**Plattformar**</span><span class="sxs-lookup"><span data-stu-id="28458-108">**Platforms**</span></span>
- <span data-ttu-id="28458-109">macOS</span><span class="sxs-lookup"><span data-stu-id="28458-109">macOS</span></span>
- <span data-ttu-id="28458-110">Linux</span><span class="sxs-lookup"><span data-stu-id="28458-110">Linux</span></span>
- <span data-ttu-id="28458-111">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="28458-111">Windows Server 2012 R2</span></span>
- <span data-ttu-id="28458-112">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="28458-112">Windows Server 2016</span></span>

><span data-ttu-id="28458-113">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="28458-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="28458-114">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="28458-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

<span data-ttu-id="28458-115">Följ motsvarande instruktioner beroende på vilken distributionsmetod du föredrar.</span><span class="sxs-lookup"><span data-stu-id="28458-115">Follow the corresponding instructions depending on your preferred deployment method.</span></span>

>[!NOTE]
> <span data-ttu-id="28458-116">Status för en enhet växlas till [Inaktiv](fix-unhealthy-sensors.md#inactive-devices) 7 dagar efter offboarding.</span><span class="sxs-lookup"><span data-stu-id="28458-116">The status of a device will be switched to [Inactive](fix-unhealthy-sensors.md#inactive-devices) 7 days after offboarding.</span></span> <br> <span data-ttu-id="28458-117">Data för offboarded-enheter (till exempel tidslinje, varningar, säkerhetsproblem och så vidare) kommer att finnas kvar i portalen tills den konfigurerade [lagringstiden](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) löper ut.</span><span class="sxs-lookup"><span data-stu-id="28458-117">Offboarded devices' data (such as Timeline, Alerts, Vulnerabilities, etc.) will remain in the portal until the configured [retention period](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) expires.</span></span> <br>
> <span data-ttu-id="28458-118">Enhetens profil (utan data) finns kvar i [enhetslistan](machines-view-overview.md) i högst 180 dagar.</span><span class="sxs-lookup"><span data-stu-id="28458-118">The device's profile (without data) will remain in the [Devices List](machines-view-overview.md) for no longer than 180 days.</span></span>
> <span data-ttu-id="28458-119">Dessutom har enheter som inte är aktiva de senaste 30 dagarna inte tagit hänsyn till de [](tvm-exposure-score.md) data som återspeglar organisationens exponeringsresultat för hot och sårbarhetshantering och Microsoft Secure Score för enheter.</span><span class="sxs-lookup"><span data-stu-id="28458-119">In addition, devices that are not active in the last 30 days are not factored in on the data that reflects your organization's threat and vulnerability management [exposure score](tvm-exposure-score.md) and Microsoft Secure Score for Devices.</span></span> <br>
> <span data-ttu-id="28458-120">Om du bara vill visa aktiva enheter kan du filtrera [efter status,](machines-view-overview.md#health-state) [enhetstaggar](machine-tags.md) eller [datorgrupper.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="28458-120">To view only active devices, you can filter by [health state](machines-view-overview.md#health-state), [device tags](machine-tags.md) or [machine groups](machine-groups.md).</span></span> 

## <a name="offboard-windows-10-devices"></a><span data-ttu-id="28458-121">Offboard Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="28458-121">Offboard Windows 10 devices</span></span>
- [<span data-ttu-id="28458-122">Offboard-enheter med ett lokalt skript</span><span class="sxs-lookup"><span data-stu-id="28458-122">Offboard devices using a local script</span></span>](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [<span data-ttu-id="28458-123">Offboard-enheter med grupprincip</span><span class="sxs-lookup"><span data-stu-id="28458-123">Offboard devices using Group Policy</span></span>](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [<span data-ttu-id="28458-124">Offboard-enheter med mobila enhetshanteringsverktyg</span><span class="sxs-lookup"><span data-stu-id="28458-124">Offboard devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a><span data-ttu-id="28458-125">Offboard-servrar</span><span class="sxs-lookup"><span data-stu-id="28458-125">Offboard Servers</span></span>
- [<span data-ttu-id="28458-126">Offboard-servrar</span><span class="sxs-lookup"><span data-stu-id="28458-126">Offboard servers</span></span>](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="28458-127">Offboard-enheter som inte är Windows-enheter</span><span class="sxs-lookup"><span data-stu-id="28458-127">Offboard non-Windows devices</span></span>
- [<span data-ttu-id="28458-128">Offboard-enheter som inte är Windows-enheter</span><span class="sxs-lookup"><span data-stu-id="28458-128">Offboard non-Windows devices</span></span>](configure-endpoints-non-windows.md#offboard-non-windows-devices)

