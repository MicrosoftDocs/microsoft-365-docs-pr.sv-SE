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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Lär dig mer om de olika enhetstillstånden i listan Enhetsåtgärder i Admin home i Microsoft 365 Business.
ms.openlocfilehash: 878050fbe11acca1d5d434a5d2ab0b5b48510e45
ms.sourcegitcommit: ab916c216053999c9c4ef4838217e82cd861f23f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2020
ms.locfileid: "42415674"
---
# <a name="device-states"></a><span data-ttu-id="ef814-103">Statusvärden för enheter</span><span class="sxs-lookup"><span data-stu-id="ef814-103">Device states</span></span>

<span data-ttu-id="ef814-104">Enheter i listan **Enhetsåtgärder** (Administratörshemsida \> **Enhetsåtgärder**) kan ha följande statusar.</span><span class="sxs-lookup"><span data-stu-id="ef814-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="ef814-106">**Status**</span><span class="sxs-lookup"><span data-stu-id="ef814-106">**Status**</span></span>|<span data-ttu-id="ef814-107">**Beskrivning**</span><span class="sxs-lookup"><span data-stu-id="ef814-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ef814-108">Managed by Intune (Hanteras av Intune)</span><span class="sxs-lookup"><span data-stu-id="ef814-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="ef814-109">Hanterad av Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="ef814-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="ef814-110">Retire pending (Väntar på att tas ur bruk)</span><span class="sxs-lookup"><span data-stu-id="ef814-110">Retire pending</span></span>  <br/> |<span data-ttu-id="ef814-111">Microsoft 365 Business förbereds för att ta bort företagsdata från enheten.</span><span class="sxs-lookup"><span data-stu-id="ef814-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="ef814-112">Retire in progress (Tas nu ur bruk)</span><span class="sxs-lookup"><span data-stu-id="ef814-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="ef814-113">Microsoft 365 Business tar för närvarande bort företagsdata från enheten.</span><span class="sxs-lookup"><span data-stu-id="ef814-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="ef814-114">Retire failed (Det gick inte att ta ur bruk)</span><span class="sxs-lookup"><span data-stu-id="ef814-114">Retire failed</span></span>  <br/> | <span data-ttu-id="ef814-115">Åtgärden att ta bort företagsdata misslyckades.</span><span class="sxs-lookup"><span data-stu-id="ef814-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="ef814-116">Dra tillbaka avbruten</span><span class="sxs-lookup"><span data-stu-id="ef814-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="ef814-117">Åtgärden Dra tillbaka avbröts.</span><span class="sxs-lookup"><span data-stu-id="ef814-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="ef814-118">Wipe pending (Rensning väntar)</span><span class="sxs-lookup"><span data-stu-id="ef814-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="ef814-119">Väntar på att fabriksåterställning ska starta.</span><span class="sxs-lookup"><span data-stu-id="ef814-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="ef814-120">Wipe in progress (Rensning pågår)</span><span class="sxs-lookup"><span data-stu-id="ef814-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="ef814-121">Fabriksinställning har skickats.</span><span class="sxs-lookup"><span data-stu-id="ef814-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="ef814-122">Wipe failed (Det gick inte att rensa)</span><span class="sxs-lookup"><span data-stu-id="ef814-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="ef814-123">Det gick inte att återställa fabriksåterställningen.</span><span class="sxs-lookup"><span data-stu-id="ef814-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="ef814-124">Rensa avbruten</span><span class="sxs-lookup"><span data-stu-id="ef814-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="ef814-125">Fabriksrensning en inställd.</span><span class="sxs-lookup"><span data-stu-id="ef814-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="ef814-126">Unhealthy (Ej felfri)</span><span class="sxs-lookup"><span data-stu-id="ef814-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="ef814-127">En åtgärd väntar (eller pågår), men enheten har inte checkat in på 30+ dagar.</span><span class="sxs-lookup"><span data-stu-id="ef814-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="ef814-128">Delete pending (Väntar på att tas bort)</span><span class="sxs-lookup"><span data-stu-id="ef814-128">Delete pending</span></span>  <br/> |<span data-ttu-id="ef814-129">Ta bort-åtgärd som väntar.</span><span class="sxs-lookup"><span data-stu-id="ef814-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="ef814-130">Discovered (Identifierad)</span><span class="sxs-lookup"><span data-stu-id="ef814-130">Discovered</span></span>  <br/> |<span data-ttu-id="ef814-131">Microsoft 365 Business har upptäckt enheten.</span><span class="sxs-lookup"><span data-stu-id="ef814-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
