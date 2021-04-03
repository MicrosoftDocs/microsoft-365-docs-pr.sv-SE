---
title: Poängmetoder och egenskaper
description: Hämtar organisationens exponeringsresultat, enhet säkra poäng och exponeringsresultat per enhetsgrupp
keywords: apis, graph api, api som stöds, poäng, exponeringspoäng, enhet säker poäng, exponeringsresultat efter enhetsgrupp
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1c287a72318cfb2e6e4e3860ac90a90e561040fe
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500946"
---
# <a name="score-resource-type"></a><span data-ttu-id="6073b-104">Resurstyp för poäng</span><span class="sxs-lookup"><span data-stu-id="6073b-104">Score resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6073b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="6073b-105">**Applies to:**</span></span>
- [<span data-ttu-id="6073b-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="6073b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6073b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6073b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6073b-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="6073b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6073b-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="6073b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a><span data-ttu-id="6073b-110">Metoder</span><span class="sxs-lookup"><span data-stu-id="6073b-110">Methods</span></span>

<span data-ttu-id="6073b-111">Metod</span><span class="sxs-lookup"><span data-stu-id="6073b-111">Method</span></span> |<span data-ttu-id="6073b-112">Returtyp</span><span class="sxs-lookup"><span data-stu-id="6073b-112">Return Type</span></span> |<span data-ttu-id="6073b-113">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6073b-113">Description</span></span>
:---|:---|:---
[<span data-ttu-id="6073b-114">Hämta exponeringsvärde</span><span class="sxs-lookup"><span data-stu-id="6073b-114">Get exposure score</span></span>](get-exposure-score.md) | [<span data-ttu-id="6073b-115">Poäng</span><span class="sxs-lookup"><span data-stu-id="6073b-115">Score</span></span>](score.md) | <span data-ttu-id="6073b-116">Få exponeringsresultatet för organisationen.</span><span class="sxs-lookup"><span data-stu-id="6073b-116">Get the organizational exposure score.</span></span>
[<span data-ttu-id="6073b-117">Hämta enhetens säkerhetspoäng</span><span class="sxs-lookup"><span data-stu-id="6073b-117">Get device secure score</span></span>](get-device-secure-score.md) | [<span data-ttu-id="6073b-118">Poäng</span><span class="sxs-lookup"><span data-stu-id="6073b-118">Score</span></span>](score.md) | <span data-ttu-id="6073b-119">Skaffa organisationens enhets säkra poäng.</span><span class="sxs-lookup"><span data-stu-id="6073b-119">Get the organizational device secure score.</span></span>
[<span data-ttu-id="6073b-120">Lista över exponeringsresultat per enhetsgrupp</span><span class="sxs-lookup"><span data-stu-id="6073b-120">List exposure score by device group</span></span>](get-machine-group-exposure-score.md)| [<span data-ttu-id="6073b-121">Poäng</span><span class="sxs-lookup"><span data-stu-id="6073b-121">Score</span></span>](score.md) | <span data-ttu-id="6073b-122">Lista resultat efter enhetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="6073b-122">List scores by device group.</span></span>

## <a name="properties"></a><span data-ttu-id="6073b-123">Egenskaper</span><span class="sxs-lookup"><span data-stu-id="6073b-123">Properties</span></span>

<span data-ttu-id="6073b-124">Egenskap</span><span class="sxs-lookup"><span data-stu-id="6073b-124">Property</span></span> |  <span data-ttu-id="6073b-125">Skriv</span><span class="sxs-lookup"><span data-stu-id="6073b-125">Type</span></span>    |   <span data-ttu-id="6073b-126">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="6073b-126">Description</span></span>
:---|:---|:---
<span data-ttu-id="6073b-127">Poäng</span><span class="sxs-lookup"><span data-stu-id="6073b-127">Score</span></span> | <span data-ttu-id="6073b-128">Double</span><span class="sxs-lookup"><span data-stu-id="6073b-128">Double</span></span> | <span data-ttu-id="6073b-129">Det aktuella resultatet.</span><span class="sxs-lookup"><span data-stu-id="6073b-129">The current score.</span></span>
<span data-ttu-id="6073b-130">Tid</span><span class="sxs-lookup"><span data-stu-id="6073b-130">Time</span></span> | <span data-ttu-id="6073b-131">DateTime</span><span class="sxs-lookup"><span data-stu-id="6073b-131">DateTime</span></span> | <span data-ttu-id="6073b-132">Datum och tid då anropet till API:et gjordes.</span><span class="sxs-lookup"><span data-stu-id="6073b-132">The date and time in which the call for this API was made.</span></span>
<span data-ttu-id="6073b-133">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="6073b-133">RbacGroupName</span></span> | <span data-ttu-id="6073b-134">Sträng</span><span class="sxs-lookup"><span data-stu-id="6073b-134">String</span></span> | <span data-ttu-id="6073b-135">Enhetens gruppnamn.</span><span class="sxs-lookup"><span data-stu-id="6073b-135">The device group name.</span></span>
