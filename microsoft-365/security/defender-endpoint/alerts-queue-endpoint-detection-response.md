---
title: Kön Aviseringar i Microsoft Defender Säkerhetscenter
ms.reviewer: ''
description: Visa och hantera aviseringarna i Microsoft Defender Säkerhetscenter
keywords: ''
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
ms.date: 09/03/2018
ms.technology: mde
ms.openlocfilehash: d40fc887f26dfe62e05f7ee6ac7bbbb8ac45a402
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075441"
---
# <a name="alerts-queue-in-microsoft-defender-security-center"></a><span data-ttu-id="178ec-103">Kön Aviseringar i Microsoft Defender Säkerhetscenter</span><span class="sxs-lookup"><span data-stu-id="178ec-103">Alerts queue in Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="178ec-104">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="178ec-104">**Applies to:**</span></span>
- [<span data-ttu-id="178ec-105">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="178ec-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="178ec-106">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="178ec-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="178ec-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="178ec-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="178ec-108">Lär dig hur du kan visa och hantera kön så att du effektivt kan undersöka hot som visas för enheter, filer eller användarkonton.</span><span class="sxs-lookup"><span data-stu-id="178ec-108">Learn how you can view and manage the queue so that you can effectively investigate threats seen on entities such as devices, files, or user accounts.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="178ec-109">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="178ec-109">In this section</span></span>
<span data-ttu-id="178ec-110">Ämne</span><span class="sxs-lookup"><span data-stu-id="178ec-110">Topic</span></span> | <span data-ttu-id="178ec-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="178ec-111">Description</span></span> 
:---|:---
[<span data-ttu-id="178ec-112">Visa och ordna kön Aviseringar</span><span class="sxs-lookup"><span data-stu-id="178ec-112">View and organize the Alerts queue</span></span>](alerts-queue.md) | <span data-ttu-id="178ec-113">Visar en lista med aviseringar som har flaggats i nätverket.</span><span class="sxs-lookup"><span data-stu-id="178ec-113">Shows a list of alerts that were flagged in your network.</span></span>
[<span data-ttu-id="178ec-114">Hantera aviseringar</span><span class="sxs-lookup"><span data-stu-id="178ec-114">Manage alerts</span></span>](manage-alerts.md) | <span data-ttu-id="178ec-115">Lär dig mer om hur du kan hantera aviseringar, till exempel ändra status, tilldela den till en medlem i säkerhetsåtgärder och se historiken för en avisering.</span><span class="sxs-lookup"><span data-stu-id="178ec-115">Learn about how you can manage alerts such as change its status, assign it to a security operations member, and see the history of an alert.</span></span>
[<span data-ttu-id="178ec-116">Undersöka aviseringar</span><span class="sxs-lookup"><span data-stu-id="178ec-116">Investigate alerts</span></span>](investigate-alerts.md)| <span data-ttu-id="178ec-117">Undersök aviseringar som påverkar nätverket, förstå vad de betyder och hur du löser dem.</span><span class="sxs-lookup"><span data-stu-id="178ec-117">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>
[<span data-ttu-id="178ec-118">Undersöka filer</span><span class="sxs-lookup"><span data-stu-id="178ec-118">Investigate files</span></span>](investigate-files.md)| <span data-ttu-id="178ec-119">Undersöka information om en fil som är kopplad till en viss avisering, ett visst beteende eller en viss händelse.</span><span class="sxs-lookup"><span data-stu-id="178ec-119">Investigate the details of a file associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="178ec-120">Undersöka enheter</span><span class="sxs-lookup"><span data-stu-id="178ec-120">Investigate devices</span></span>](investigate-machines.md)| <span data-ttu-id="178ec-121">Undersök informationen om en enhet som är kopplad till en viss avisering, ett visst beteende eller en viss händelse.</span><span class="sxs-lookup"><span data-stu-id="178ec-121">Investigate the details of a device associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="178ec-122">Undersöka en IP-adress</span><span class="sxs-lookup"><span data-stu-id="178ec-122">Investigate an IP address</span></span>](investigate-ip.md) | <span data-ttu-id="178ec-123">Undersök möjlig kommunikation mellan enheter i nätverket och IP-adresser (External Internet Protocol).</span><span class="sxs-lookup"><span data-stu-id="178ec-123">Examine possible communication between devices in your network and external internet protocol (IP) addresses.</span></span>
[<span data-ttu-id="178ec-124">Undersöka en domän</span><span class="sxs-lookup"><span data-stu-id="178ec-124">Investigate a domain</span></span>](investigate-domain.md) | <span data-ttu-id="178ec-125">Undersök en domän för att se om enheter och servrar i nätverket har kommunicerat med en känd skadlig domän.</span><span class="sxs-lookup"><span data-stu-id="178ec-125">Investigate a domain to see if devices and servers in your network have been communicating with a known malicious domain.</span></span> 
[<span data-ttu-id="178ec-126">Undersöka ett användarkonto</span><span class="sxs-lookup"><span data-stu-id="178ec-126">Investigate a user account</span></span>](investigate-user.md) | <span data-ttu-id="178ec-127">Identifiera användarkonton med de mest aktiva aviseringarna och undersök möjliga komprometterade autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="178ec-127">Identify user accounts with the most active alerts and investigate cases of potential compromised credentials.</span></span>  


