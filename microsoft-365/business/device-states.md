---
title: Statusvärden för enheter
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Lär dig mer om enhetstillstånd i Microsoft 365 Business.
ms.openlocfilehash: 06e5c800e6a104785c1fd0724223e05d7729722e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072729"
---
# <a name="device-states"></a><span data-ttu-id="a90c3-103">Statusvärden för enheter</span><span class="sxs-lookup"><span data-stu-id="a90c3-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="a90c3-104">Statusvärden för enheter</span><span class="sxs-lookup"><span data-stu-id="a90c3-104">Device states</span></span>

<span data-ttu-id="a90c3-105">Enheter i listan **Enhetsåtgärder** (Administratörshemsida \> **Enhetsåtgärder**) kan ha följande statusar.</span><span class="sxs-lookup"><span data-stu-id="a90c3-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="a90c3-107">**Status**</span><span class="sxs-lookup"><span data-stu-id="a90c3-107">**Status**</span></span>|<span data-ttu-id="a90c3-108">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="a90c3-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a90c3-109">Managed by Intune (Hanteras av Intune)</span><span class="sxs-lookup"><span data-stu-id="a90c3-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="a90c3-110">Hanterad av Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="a90c3-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="a90c3-111">Retire pending (Väntar på att tas ur bruk)</span><span class="sxs-lookup"><span data-stu-id="a90c3-111">Retire pending</span></span>  <br/> |<span data-ttu-id="a90c3-112">Microsoft 365 Business förbereds för att ta bort företagsdata från enheten.</span><span class="sxs-lookup"><span data-stu-id="a90c3-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="a90c3-113">Retire in progress (Tas nu ur bruk)</span><span class="sxs-lookup"><span data-stu-id="a90c3-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="a90c3-114">Microsoft 365 Business tar för närvarande bort företagsdata från enheten.</span><span class="sxs-lookup"><span data-stu-id="a90c3-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="a90c3-115">Retire failed (Det gick inte att ta ur bruk)</span><span class="sxs-lookup"><span data-stu-id="a90c3-115">Retire failed</span></span>  <br/> | <span data-ttu-id="a90c3-116">Åtgärden att ta bort företagsdata misslyckades.</span><span class="sxs-lookup"><span data-stu-id="a90c3-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="a90c3-117">Retire cancelled (Borttagningen har avbrutits)</span><span class="sxs-lookup"><span data-stu-id="a90c3-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="a90c3-118">Åtgärden för att ta ur bruk avbröts.</span><span class="sxs-lookup"><span data-stu-id="a90c3-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="a90c3-119">Wipe pending (Rensning väntar)</span><span class="sxs-lookup"><span data-stu-id="a90c3-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="a90c3-120">Väntar på att fabriksåterställning ska starta.</span><span class="sxs-lookup"><span data-stu-id="a90c3-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="a90c3-121">Wipe in progress (Rensning pågår)</span><span class="sxs-lookup"><span data-stu-id="a90c3-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="a90c3-122">Fabriksinställning har skickats.</span><span class="sxs-lookup"><span data-stu-id="a90c3-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="a90c3-123">Wipe failed (Det gick inte att rensa)</span><span class="sxs-lookup"><span data-stu-id="a90c3-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="a90c3-124">Det gick inte utföra fabriksåterställning.</span><span class="sxs-lookup"><span data-stu-id="a90c3-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="a90c3-125">Wipe cancelled (Rensningen har avbrutits)</span><span class="sxs-lookup"><span data-stu-id="a90c3-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="a90c3-126">Fabriksåterställningen avbröts.</span><span class="sxs-lookup"><span data-stu-id="a90c3-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="a90c3-127">Unhealthy (Ej felfri)</span><span class="sxs-lookup"><span data-stu-id="a90c3-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="a90c3-128">Detta innebär att en åtgärd är väntande (eller pågår), men att enheten inte har checkats in på mer än 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="a90c3-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="a90c3-129">Delete pending (Väntar på att tas bort)</span><span class="sxs-lookup"><span data-stu-id="a90c3-129">Delete pending</span></span>  <br/> |<span data-ttu-id="a90c3-130">Ta bort-åtgärd som väntar.</span><span class="sxs-lookup"><span data-stu-id="a90c3-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="a90c3-131">Discovered (Identifierad)</span><span class="sxs-lookup"><span data-stu-id="a90c3-131">Discovered</span></span>  <br/> |<span data-ttu-id="a90c3-132">Microsoft 365 Business har upptäckt enheten.</span><span class="sxs-lookup"><span data-stu-id="a90c3-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
