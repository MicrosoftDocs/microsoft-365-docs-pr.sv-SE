---
title: Statusvärden för enheter
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
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
ms.openlocfilehash: bd6f1ad7f7671d9616fd14d477dfcfb164ff6bd0
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982909"
---
# <a name="device-states"></a><span data-ttu-id="633d7-103">Statusvärden för enheter</span><span class="sxs-lookup"><span data-stu-id="633d7-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="633d7-104">Statusvärden för enheter</span><span class="sxs-lookup"><span data-stu-id="633d7-104">Device states</span></span>

<span data-ttu-id="633d7-105">Enheter i listan **Enhetsåtgärder** (Administratörshemsida \> **Enhetsåtgärder**) kan ha följande statusar.</span><span class="sxs-lookup"><span data-stu-id="633d7-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="633d7-107">**Status**</span><span class="sxs-lookup"><span data-stu-id="633d7-107">**Status**</span></span>|<span data-ttu-id="633d7-108">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="633d7-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="633d7-109">Managed by Intune (Hanteras av Intune)</span><span class="sxs-lookup"><span data-stu-id="633d7-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="633d7-110">Hanterad av Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="633d7-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="633d7-111">Retire pending (Väntar på att tas ur bruk)</span><span class="sxs-lookup"><span data-stu-id="633d7-111">Retire pending</span></span>  <br/> |<span data-ttu-id="633d7-112">Microsoft 365 Business förbereds för att ta bort företagsdata från enheten.</span><span class="sxs-lookup"><span data-stu-id="633d7-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="633d7-113">Retire in progress (Tas nu ur bruk)</span><span class="sxs-lookup"><span data-stu-id="633d7-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="633d7-114">Microsoft 365 Business tar för närvarande bort företagsdata från enheten.</span><span class="sxs-lookup"><span data-stu-id="633d7-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="633d7-115">Retire failed (Det gick inte att ta ur bruk)</span><span class="sxs-lookup"><span data-stu-id="633d7-115">Retire failed</span></span>  <br/> | <span data-ttu-id="633d7-116">Åtgärden att ta bort företagsdata misslyckades.</span><span class="sxs-lookup"><span data-stu-id="633d7-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="633d7-117">Retire cancelled (Borttagningen har avbrutits)</span><span class="sxs-lookup"><span data-stu-id="633d7-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="633d7-118">Åtgärden för att ta ur bruk avbröts.</span><span class="sxs-lookup"><span data-stu-id="633d7-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="633d7-119">Wipe pending (Rensning väntar)</span><span class="sxs-lookup"><span data-stu-id="633d7-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="633d7-120">Väntar på att fabriksåterställning ska starta.</span><span class="sxs-lookup"><span data-stu-id="633d7-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="633d7-121">Wipe in progress (Rensning pågår)</span><span class="sxs-lookup"><span data-stu-id="633d7-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="633d7-122">Fabriksinställning har skickats.</span><span class="sxs-lookup"><span data-stu-id="633d7-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="633d7-123">Wipe failed (Det gick inte att rensa)</span><span class="sxs-lookup"><span data-stu-id="633d7-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="633d7-124">Det gick inte utföra fabriksåterställning.</span><span class="sxs-lookup"><span data-stu-id="633d7-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="633d7-125">Wipe cancelled (Rensningen har avbrutits)</span><span class="sxs-lookup"><span data-stu-id="633d7-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="633d7-126">Fabriksåterställningen avbröts.</span><span class="sxs-lookup"><span data-stu-id="633d7-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="633d7-127">Unhealthy (Ej felfri)</span><span class="sxs-lookup"><span data-stu-id="633d7-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="633d7-128">Detta innebär att en åtgärd är väntande (eller pågår), men att enheten inte har checkats in på mer än 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="633d7-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="633d7-129">Delete pending (Väntar på att tas bort)</span><span class="sxs-lookup"><span data-stu-id="633d7-129">Delete pending</span></span>  <br/> |<span data-ttu-id="633d7-130">Ta bort-åtgärd som väntar.</span><span class="sxs-lookup"><span data-stu-id="633d7-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="633d7-131">Discovered (Identifierad)</span><span class="sxs-lookup"><span data-stu-id="633d7-131">Discovered</span></span>  <br/> |<span data-ttu-id="633d7-132">Microsoft 365 Business har upptäckt enheten.</span><span class="sxs-lookup"><span data-stu-id="633d7-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
