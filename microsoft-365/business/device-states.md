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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Läs mer om de olika enhetslägena i listan Enhetsåtgärder i hemtjänsten i Microsoft 365 Business.
ms.openlocfilehash: cb1e5172a6e2d0bfc5748fe982024ead26e8cd62
ms.sourcegitcommit: d6c871bf3f94d9299d22695f5dbaf25dc1bd6ff9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/05/2020
ms.locfileid: "42417325"
---
# <a name="device-states"></a><span data-ttu-id="d2d7d-103">Statusvärden för enheter</span><span class="sxs-lookup"><span data-stu-id="d2d7d-103">Device states</span></span>

<span data-ttu-id="d2d7d-104">Enheter i listan **Enhetsåtgärder** (Administratörshemsida \> **Enhetsåtgärder**) kan ha följande statusar.</span><span class="sxs-lookup"><span data-stu-id="d2d7d-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="d2d7d-106">**Status**</span><span class="sxs-lookup"><span data-stu-id="d2d7d-106">**Status**</span></span>|<span data-ttu-id="d2d7d-107">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="d2d7d-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d2d7d-108">Managed by Intune (Hanteras av Intune)</span><span class="sxs-lookup"><span data-stu-id="d2d7d-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="d2d7d-109">Hanterad av Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="d2d7d-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="d2d7d-110">Retire pending (Väntar på att tas ur bruk)</span><span class="sxs-lookup"><span data-stu-id="d2d7d-110">Retire pending</span></span>  <br/> |<span data-ttu-id="d2d7d-111">Microsoft 365 Business förbereds för att ta bort företagsdata från enheten.</span><span class="sxs-lookup"><span data-stu-id="d2d7d-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="d2d7d-112">Retire in progress (Tas nu ur bruk)</span><span class="sxs-lookup"><span data-stu-id="d2d7d-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="d2d7d-113">Microsoft 365 Business tar för närvarande bort företagsdata från enheten.</span><span class="sxs-lookup"><span data-stu-id="d2d7d-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="d2d7d-114">Retire failed (Det gick inte att ta ur bruk)</span><span class="sxs-lookup"><span data-stu-id="d2d7d-114">Retire failed</span></span>  <br/> | <span data-ttu-id="d2d7d-115">Åtgärden att ta bort företagsdata misslyckades.</span><span class="sxs-lookup"><span data-stu-id="d2d7d-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="d2d7d-116">Pensionerad avbruten</span><span class="sxs-lookup"><span data-stu-id="d2d7d-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="d2d7d-117">Åtgärden för pensionering avbröts.</span><span class="sxs-lookup"><span data-stu-id="d2d7d-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="d2d7d-118">Wipe pending (Rensning väntar)</span><span class="sxs-lookup"><span data-stu-id="d2d7d-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="d2d7d-119">Väntar på att fabriksåterställning ska starta.</span><span class="sxs-lookup"><span data-stu-id="d2d7d-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="d2d7d-120">Wipe in progress (Rensning pågår)</span><span class="sxs-lookup"><span data-stu-id="d2d7d-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="d2d7d-121">Fabriksinställning har skickats.</span><span class="sxs-lookup"><span data-stu-id="d2d7d-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="d2d7d-122">Wipe failed (Det gick inte att rensa)</span><span class="sxs-lookup"><span data-stu-id="d2d7d-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="d2d7d-123">Det gick inte att återställa fabriksåterställningen.</span><span class="sxs-lookup"><span data-stu-id="d2d7d-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="d2d7d-124">Wipe avbröts</span><span class="sxs-lookup"><span data-stu-id="d2d7d-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="d2d7d-125">Fabriksrensningen avbröts.</span><span class="sxs-lookup"><span data-stu-id="d2d7d-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="d2d7d-126">Unhealthy (Ej felfri)</span><span class="sxs-lookup"><span data-stu-id="d2d7d-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="d2d7d-127">En åtgärd väntar (eller pågår), men enheten har inte checkat in på 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="d2d7d-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="d2d7d-128">Delete pending (Väntar på att tas bort)</span><span class="sxs-lookup"><span data-stu-id="d2d7d-128">Delete pending</span></span>  <br/> |<span data-ttu-id="d2d7d-129">Ta bort-åtgärd som väntar.</span><span class="sxs-lookup"><span data-stu-id="d2d7d-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="d2d7d-130">Discovered (Identifierad)</span><span class="sxs-lookup"><span data-stu-id="d2d7d-130">Discovered</span></span>  <br/> |<span data-ttu-id="d2d7d-131">Microsoft 365 Business har upptäckt enheten.</span><span class="sxs-lookup"><span data-stu-id="d2d7d-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
