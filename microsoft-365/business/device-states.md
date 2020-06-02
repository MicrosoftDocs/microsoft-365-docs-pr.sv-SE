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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Lär dig mer om de olika enhetstillstånden i listan Enhetsåtgärder i Administrationshem i Microsoft 365 för företag.
ms.openlocfilehash: 64138e2b6ae73c067709cde1912a96615d08ebf1
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471188"
---
# <a name="device-states"></a><span data-ttu-id="99df4-103">Statusvärden för enheter</span><span class="sxs-lookup"><span data-stu-id="99df4-103">Device states</span></span>

<span data-ttu-id="99df4-104">Den här artikeln gäller Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="99df4-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="99df4-105">Enheter i listan **Enhetsåtgärder** (Administratörshemsida \> **Enhetsåtgärder**) kan ha följande statusar.</span><span class="sxs-lookup"><span data-stu-id="99df4-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="99df4-107">**Status**</span><span class="sxs-lookup"><span data-stu-id="99df4-107">**Status**</span></span>|<span data-ttu-id="99df4-108">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="99df4-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="99df4-109">Managed by Intune (Hanteras av Intune)</span><span class="sxs-lookup"><span data-stu-id="99df4-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="99df4-110">Hanteras av Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="99df4-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="99df4-111">Retire pending (Väntar på att tas ur bruk)</span><span class="sxs-lookup"><span data-stu-id="99df4-111">Retire pending</span></span>  <br/> |<span data-ttu-id="99df4-112">Microsoft 365 Business Premium gör sig redo att ta bort företagsdata från enheten.</span><span class="sxs-lookup"><span data-stu-id="99df4-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="99df4-113">Retire in progress (Tas nu ur bruk)</span><span class="sxs-lookup"><span data-stu-id="99df4-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="99df4-114">Microsoft 365 Business Premium tar för närvarande bort företagsdata från enheten.</span><span class="sxs-lookup"><span data-stu-id="99df4-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="99df4-115">Retire failed (Det gick inte att ta ur bruk)</span><span class="sxs-lookup"><span data-stu-id="99df4-115">Retire failed</span></span>  <br/> | <span data-ttu-id="99df4-116">Åtgärden att ta bort företagsdata misslyckades.</span><span class="sxs-lookup"><span data-stu-id="99df4-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="99df4-117">Dra tillbaka avbrutet</span><span class="sxs-lookup"><span data-stu-id="99df4-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="99df4-118">Åtgärden För att dra tillbaka avbröts.</span><span class="sxs-lookup"><span data-stu-id="99df4-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="99df4-119">Wipe pending (Rensning väntar)</span><span class="sxs-lookup"><span data-stu-id="99df4-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="99df4-120">Väntar på att fabriksåterställning ska starta.</span><span class="sxs-lookup"><span data-stu-id="99df4-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="99df4-121">Wipe in progress (Rensning pågår)</span><span class="sxs-lookup"><span data-stu-id="99df4-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="99df4-122">Fabriksinställning har skickats.</span><span class="sxs-lookup"><span data-stu-id="99df4-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="99df4-123">Wipe failed (Det gick inte att rensa)</span><span class="sxs-lookup"><span data-stu-id="99df4-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="99df4-124">Kunde inte göra fabriksåterställning.</span><span class="sxs-lookup"><span data-stu-id="99df4-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="99df4-125">Rensningen har avbrutits</span><span class="sxs-lookup"><span data-stu-id="99df4-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="99df4-126">Fabriksrensningen avbröts.</span><span class="sxs-lookup"><span data-stu-id="99df4-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="99df4-127">Unhealthy (Ej felfri)</span><span class="sxs-lookup"><span data-stu-id="99df4-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="99df4-128">En åtgärd väntar (eller pågår), men enheten har inte checkat in på över 30 dagar.</span><span class="sxs-lookup"><span data-stu-id="99df4-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="99df4-129">Delete pending (Väntar på att tas bort)</span><span class="sxs-lookup"><span data-stu-id="99df4-129">Delete pending</span></span>  <br/> |<span data-ttu-id="99df4-130">Ta bort-åtgärd som väntar.</span><span class="sxs-lookup"><span data-stu-id="99df4-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="99df4-131">Discovered (Identifierad)</span><span class="sxs-lookup"><span data-stu-id="99df4-131">Discovered</span></span>  <br/> |<span data-ttu-id="99df4-132">Microsoft 365 Business Premium har upptäckt enheten.</span><span class="sxs-lookup"><span data-stu-id="99df4-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
