---
title: Statusvärden för enheter
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Läs mer om olika enhets tillstånd i listan Enhetsåtgärder i administrationscentret i Microsoft 365 för företag.
ms.openlocfilehash: e6f1b428413d094e0a1ce3afb026528074038736
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578476"
---
# <a name="device-states"></a><span data-ttu-id="4513c-103">Statusvärden för enheter</span><span class="sxs-lookup"><span data-stu-id="4513c-103">Device states</span></span>

<span data-ttu-id="4513c-104">Den här artikeln gäller Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="4513c-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="4513c-105">Enheter i listan **Enhetsåtgärder** (Administratörshemsida \> **Enhetsåtgärder**) kan ha följande statusar.</span><span class="sxs-lookup"><span data-stu-id="4513c-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="4513c-107">**Status**</span><span class="sxs-lookup"><span data-stu-id="4513c-107">**Status**</span></span>|<span data-ttu-id="4513c-108">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="4513c-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4513c-109">Managed by Intune (Hanteras av Intune)</span><span class="sxs-lookup"><span data-stu-id="4513c-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="4513c-110">Hanteras av Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="4513c-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="4513c-111">Retire pending (Väntar på att tas ur bruk)</span><span class="sxs-lookup"><span data-stu-id="4513c-111">Retire pending</span></span>  <br/> |<span data-ttu-id="4513c-112">Microsoft 365 Business Premium för förbereda för att ta bort företagsdata från enheten.</span><span class="sxs-lookup"><span data-stu-id="4513c-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="4513c-113">Retire in progress (Tas nu ur bruk)</span><span class="sxs-lookup"><span data-stu-id="4513c-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="4513c-114">Microsoft 365 Business Premium tar för närvarande bort företagsdata från enheten.</span><span class="sxs-lookup"><span data-stu-id="4513c-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="4513c-115">Retire failed (Det gick inte att ta ur bruk)</span><span class="sxs-lookup"><span data-stu-id="4513c-115">Retire failed</span></span>  <br/> | <span data-ttu-id="4513c-116">Åtgärden att ta bort företagsdata misslyckades.</span><span class="sxs-lookup"><span data-stu-id="4513c-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="4513c-117">Retire canceled (Dra tillbaka) har avbrutits</span><span class="sxs-lookup"><span data-stu-id="4513c-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="4513c-118">Åtgärden för att ta ur verksamhet har avbrutits.</span><span class="sxs-lookup"><span data-stu-id="4513c-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="4513c-119">Wipe pending (Rensning väntar)</span><span class="sxs-lookup"><span data-stu-id="4513c-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="4513c-120">Väntar på att fabriksåterställning ska starta.</span><span class="sxs-lookup"><span data-stu-id="4513c-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="4513c-121">Wipe in progress (Rensning pågår)</span><span class="sxs-lookup"><span data-stu-id="4513c-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="4513c-122">Fabriksinställning har skickats.</span><span class="sxs-lookup"><span data-stu-id="4513c-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="4513c-123">Wipe failed (Det gick inte att rensa)</span><span class="sxs-lookup"><span data-stu-id="4513c-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="4513c-124">Det gick inte göra fabriksåterställning.</span><span class="sxs-lookup"><span data-stu-id="4513c-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="4513c-125">Rensningen har avbrutits</span><span class="sxs-lookup"><span data-stu-id="4513c-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="4513c-126">Fabriksåterställningen avbröts.</span><span class="sxs-lookup"><span data-stu-id="4513c-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="4513c-127">Unhealthy (Ej felfri)</span><span class="sxs-lookup"><span data-stu-id="4513c-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="4513c-128">En åtgärd väntar (eller pågår), men enheten har inte checkats in på mer än 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="4513c-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="4513c-129">Delete pending (Väntar på att tas bort)</span><span class="sxs-lookup"><span data-stu-id="4513c-129">Delete pending</span></span>  <br/> |<span data-ttu-id="4513c-130">Ta bort-åtgärd som väntar.</span><span class="sxs-lookup"><span data-stu-id="4513c-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="4513c-131">Discovered (Identifierad)</span><span class="sxs-lookup"><span data-stu-id="4513c-131">Discovered</span></span>  <br/> |<span data-ttu-id="4513c-132">Microsoft 365 Business Premium har upptäckt enheten.</span><span class="sxs-lookup"><span data-stu-id="4513c-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
