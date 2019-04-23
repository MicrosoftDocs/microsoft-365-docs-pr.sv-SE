---
title: Statusvärden för enheter
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
ms.openlocfilehash: 15114835a5014f5bfac600eac79bcdffdaec481a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276999"
---
# <a name="device-states"></a><span data-ttu-id="0e452-103">Statusvärden för enheter</span><span class="sxs-lookup"><span data-stu-id="0e452-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="0e452-104">Statusvärden för enheter</span><span class="sxs-lookup"><span data-stu-id="0e452-104">Device states</span></span>

<span data-ttu-id="0e452-105">Enheter i listan **Enhetsåtgärder** (Administratörshemsida \> **Enhetsåtgärder**) kan ha följande statusar.</span><span class="sxs-lookup"><span data-stu-id="0e452-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="0e452-107">**Status**</span><span class="sxs-lookup"><span data-stu-id="0e452-107">**Status**</span></span>|<span data-ttu-id="0e452-108">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="0e452-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0e452-109">Managed by Intune (Hanteras av Intune)</span><span class="sxs-lookup"><span data-stu-id="0e452-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="0e452-110">Hanterad av Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="0e452-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="0e452-111">Retire pending (Väntar på att tas ur bruk)</span><span class="sxs-lookup"><span data-stu-id="0e452-111">Retire pending</span></span>  <br/> |<span data-ttu-id="0e452-112">Microsoft 365 Business förbereds för att ta bort företagsdata från enheten.</span><span class="sxs-lookup"><span data-stu-id="0e452-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="0e452-113">Retire in progress (Tas nu ur bruk)</span><span class="sxs-lookup"><span data-stu-id="0e452-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="0e452-114">Microsoft 365 Business tar för närvarande bort företagsdata från enheten.</span><span class="sxs-lookup"><span data-stu-id="0e452-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="0e452-115">Retire failed (Det gick inte att ta ur bruk)</span><span class="sxs-lookup"><span data-stu-id="0e452-115">Retire failed</span></span>  <br/> | <span data-ttu-id="0e452-116">Åtgärden att ta bort företagsdata misslyckades.</span><span class="sxs-lookup"><span data-stu-id="0e452-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="0e452-117">Retire cancelled (Borttagningen har avbrutits)</span><span class="sxs-lookup"><span data-stu-id="0e452-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="0e452-118">Åtgärden för att ta ur bruk avbröts.</span><span class="sxs-lookup"><span data-stu-id="0e452-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="0e452-119">Wipe pending (Rensning väntar)</span><span class="sxs-lookup"><span data-stu-id="0e452-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="0e452-120">Väntar på att fabriksåterställning ska starta.</span><span class="sxs-lookup"><span data-stu-id="0e452-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="0e452-121">Wipe in progress (Rensning pågår)</span><span class="sxs-lookup"><span data-stu-id="0e452-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="0e452-122">Fabriksinställning har skickats.</span><span class="sxs-lookup"><span data-stu-id="0e452-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="0e452-123">Wipe failed (Det gick inte att rensa)</span><span class="sxs-lookup"><span data-stu-id="0e452-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="0e452-124">Det gick inte utföra fabriksåterställning.</span><span class="sxs-lookup"><span data-stu-id="0e452-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="0e452-125">Wipe cancelled (Rensningen har avbrutits)</span><span class="sxs-lookup"><span data-stu-id="0e452-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="0e452-126">Fabriksåterställningen avbröts.</span><span class="sxs-lookup"><span data-stu-id="0e452-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="0e452-127">Unhealthy (Ej felfri)</span><span class="sxs-lookup"><span data-stu-id="0e452-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="0e452-128">Detta innebär att en åtgärd är väntande (eller pågår), men att enheten inte har checkats in på mer än 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="0e452-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="0e452-129">Delete pending (Väntar på att tas bort)</span><span class="sxs-lookup"><span data-stu-id="0e452-129">Delete pending</span></span>  <br/> |<span data-ttu-id="0e452-130">Ta bort-åtgärd som väntar.</span><span class="sxs-lookup"><span data-stu-id="0e452-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="0e452-131">Discovered (Identifierad)</span><span class="sxs-lookup"><span data-stu-id="0e452-131">Discovered</span></span>  <br/> |<span data-ttu-id="0e452-132">Microsoft 365 Business har upptäckt enheten.</span><span class="sxs-lookup"><span data-stu-id="0e452-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
