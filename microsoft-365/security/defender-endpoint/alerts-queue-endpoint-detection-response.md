---
title: Aviseringskö i Microsoft 365 Defender
ms.reviewer: ''
description: Visa och hantera aviseringarna som visas i Microsoft 365 Defender
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
ms.openlocfilehash: ed65c836e74d5394d3b291ca3ebb5e781e37afa8
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339568"
---
# <a name="alerts-queue-in-microsoft-365-defender"></a><span data-ttu-id="21523-103">Aviseringskö i Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="21523-103">Alerts queue in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="21523-104">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="21523-104">**Applies to:**</span></span>
- [<span data-ttu-id="21523-105">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="21523-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="21523-106">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="21523-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="21523-107">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="21523-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="21523-108">Lär dig hur du kan visa och hantera kön så att du effektivt kan undersöka hot som visas för enheter, filer eller användarkonton.</span><span class="sxs-lookup"><span data-stu-id="21523-108">Learn how you can view and manage the queue so that you can effectively investigate threats seen on entities such as devices, files, or user accounts.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="21523-109">I det här avsnittet</span><span class="sxs-lookup"><span data-stu-id="21523-109">In this section</span></span>
<span data-ttu-id="21523-110">Ämne</span><span class="sxs-lookup"><span data-stu-id="21523-110">Topic</span></span> | <span data-ttu-id="21523-111">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="21523-111">Description</span></span> 
:---|:---
[<span data-ttu-id="21523-112">Visa och ordna varningskö</span><span class="sxs-lookup"><span data-stu-id="21523-112">View and organize the Alerts queue</span></span>](alerts-queue.md) | <span data-ttu-id="21523-113">Visar en lista med aviseringar som har flaggats i nätverket.</span><span class="sxs-lookup"><span data-stu-id="21523-113">Shows a list of alerts that were flagged in your network.</span></span>
[<span data-ttu-id="21523-114">Hantera varningar</span><span class="sxs-lookup"><span data-stu-id="21523-114">Manage alerts</span></span>](manage-alerts.md) | <span data-ttu-id="21523-115">Lär dig mer om hur du kan hantera aviseringar, till exempel ändra status, tilldela den till en medlem i säkerhetsåtgärder och se historiken för en avisering.</span><span class="sxs-lookup"><span data-stu-id="21523-115">Learn about how you can manage alerts such as change its status, assign it to a security operations member, and see the history of an alert.</span></span>
[<span data-ttu-id="21523-116">Undersöka varningar</span><span class="sxs-lookup"><span data-stu-id="21523-116">Investigate alerts</span></span>](investigate-alerts.md)| <span data-ttu-id="21523-117">Undersök aviseringar som påverkar nätverket, förstå vad de betyder och hur du löser dem.</span><span class="sxs-lookup"><span data-stu-id="21523-117">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>
[<span data-ttu-id="21523-118">Undersöka filer</span><span class="sxs-lookup"><span data-stu-id="21523-118">Investigate files</span></span>](investigate-files.md)| <span data-ttu-id="21523-119">Undersöka information om en fil som är kopplad till en viss avisering, ett visst beteende eller en viss händelse.</span><span class="sxs-lookup"><span data-stu-id="21523-119">Investigate the details of a file associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="21523-120">Undersöka enheter</span><span class="sxs-lookup"><span data-stu-id="21523-120">Investigate devices</span></span>](investigate-machines.md)| <span data-ttu-id="21523-121">Undersök informationen om en enhet som är kopplad till en viss avisering, ett visst beteende eller en viss händelse.</span><span class="sxs-lookup"><span data-stu-id="21523-121">Investigate the details of a device associated with a specific alert, behavior, or event.</span></span> 
[<span data-ttu-id="21523-122">Undersöka en IP-adress</span><span class="sxs-lookup"><span data-stu-id="21523-122">Investigate an IP address</span></span>](investigate-ip.md) | <span data-ttu-id="21523-123">Undersök möjlig kommunikation mellan enheter i nätverket och IP-adresser (External Internet Protocol).</span><span class="sxs-lookup"><span data-stu-id="21523-123">Examine possible communication between devices in your network and external internet protocol (IP) addresses.</span></span>
[<span data-ttu-id="21523-124">Undersöka en domän</span><span class="sxs-lookup"><span data-stu-id="21523-124">Investigate a domain</span></span>](investigate-domain.md) | <span data-ttu-id="21523-125">Undersök en domän för att se om enheter och servrar i nätverket har kommunicerat med en känd skadlig domän.</span><span class="sxs-lookup"><span data-stu-id="21523-125">Investigate a domain to see if devices and servers in your network have been communicating with a known malicious domain.</span></span> 
[<span data-ttu-id="21523-126">Undersöka ett användarkonto</span><span class="sxs-lookup"><span data-stu-id="21523-126">Investigate a user account</span></span>](investigate-user.md) | <span data-ttu-id="21523-127">Identifiera användarkonton med de mest aktiva aviseringarna och undersök möjliga komprometterade autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="21523-127">Identify user accounts with the most active alerts and investigate cases of potential compromised credentials.</span></span>  


