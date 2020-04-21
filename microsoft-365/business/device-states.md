---
title: Statusvärden för enheter
f1.keywords:
- NOCSH
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
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Lär dig mer om de olika enhetstillstånden i listan Enhetsåtgärder i Administrationshem i Microsoft 365 för företag.
ms.openlocfilehash: 1a66e76dd3a74428923292427b01551db2449e48
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627255"
---
# <a name="device-states"></a><span data-ttu-id="a3f9b-103">Statusvärden för enheter</span><span class="sxs-lookup"><span data-stu-id="a3f9b-103">Device states</span></span>

<span data-ttu-id="a3f9b-104">Enheter i listan **Enhetsåtgärder** (Administratörshemsida \> **Enhetsåtgärder**) kan ha följande statusar.</span><span class="sxs-lookup"><span data-stu-id="a3f9b-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="a3f9b-106">**Status**</span><span class="sxs-lookup"><span data-stu-id="a3f9b-106">**Status**</span></span>|<span data-ttu-id="a3f9b-107">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="a3f9b-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a3f9b-108">Managed by Intune (Hanteras av Intune)</span><span class="sxs-lookup"><span data-stu-id="a3f9b-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="a3f9b-109">Hanteras av Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="a3f9b-109">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="a3f9b-110">Retire pending (Väntar på att tas ur bruk)</span><span class="sxs-lookup"><span data-stu-id="a3f9b-110">Retire pending</span></span>  <br/> |<span data-ttu-id="a3f9b-111">Microsoft 365 Business Premium gör sig redo att ta bort företagsdata från enheten.</span><span class="sxs-lookup"><span data-stu-id="a3f9b-111">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="a3f9b-112">Retire in progress (Tas nu ur bruk)</span><span class="sxs-lookup"><span data-stu-id="a3f9b-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="a3f9b-113">Microsoft 365 Business Premium tar för närvarande bort företagsdata från enheten.</span><span class="sxs-lookup"><span data-stu-id="a3f9b-113">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="a3f9b-114">Retire failed (Det gick inte att ta ur bruk)</span><span class="sxs-lookup"><span data-stu-id="a3f9b-114">Retire failed</span></span>  <br/> | <span data-ttu-id="a3f9b-115">Åtgärden att ta bort företagsdata misslyckades.</span><span class="sxs-lookup"><span data-stu-id="a3f9b-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="a3f9b-116">Dra tillbaka avbrutet</span><span class="sxs-lookup"><span data-stu-id="a3f9b-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="a3f9b-117">Åtgärden För att dra tillbaka avbröts.</span><span class="sxs-lookup"><span data-stu-id="a3f9b-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="a3f9b-118">Wipe pending (Rensning väntar)</span><span class="sxs-lookup"><span data-stu-id="a3f9b-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="a3f9b-119">Väntar på att fabriksåterställning ska starta.</span><span class="sxs-lookup"><span data-stu-id="a3f9b-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="a3f9b-120">Wipe in progress (Rensning pågår)</span><span class="sxs-lookup"><span data-stu-id="a3f9b-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="a3f9b-121">Fabriksinställning har skickats.</span><span class="sxs-lookup"><span data-stu-id="a3f9b-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="a3f9b-122">Wipe failed (Det gick inte att rensa)</span><span class="sxs-lookup"><span data-stu-id="a3f9b-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="a3f9b-123">Kunde inte göra fabriksåterställning.</span><span class="sxs-lookup"><span data-stu-id="a3f9b-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="a3f9b-124">Rensningen har avbrutits</span><span class="sxs-lookup"><span data-stu-id="a3f9b-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="a3f9b-125">Fabriksrensningen avbröts.</span><span class="sxs-lookup"><span data-stu-id="a3f9b-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="a3f9b-126">Unhealthy (Ej felfri)</span><span class="sxs-lookup"><span data-stu-id="a3f9b-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="a3f9b-127">En åtgärd väntar (eller pågår), men enheten har inte checkat in på över 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="a3f9b-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="a3f9b-128">Delete pending (Väntar på att tas bort)</span><span class="sxs-lookup"><span data-stu-id="a3f9b-128">Delete pending</span></span>  <br/> |<span data-ttu-id="a3f9b-129">Ta bort-åtgärd som väntar.</span><span class="sxs-lookup"><span data-stu-id="a3f9b-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="a3f9b-130">Discovered (Identifierad)</span><span class="sxs-lookup"><span data-stu-id="a3f9b-130">Discovered</span></span>  <br/> |<span data-ttu-id="a3f9b-131">Microsoft 365 Business Premium har upptäckt enheten.</span><span class="sxs-lookup"><span data-stu-id="a3f9b-131">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
