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
# <a name="device-states"></a>Statusvärden för enheter

Den här artikeln gäller Microsoft 365 Business Premium.

Enheter i listan **Enhetsåtgärder** (Administratörshemsida \> **Enhetsåtgärder**) kan ha följande statusar.
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|**Status**|**Beskrivning**|
|:-----|:-----|
|Managed by Intune (Hanteras av Intune)  <br/> |Hanteras av Microsoft 365 Business Premium.  <br/> |
|Retire pending (Väntar på att tas ur bruk)  <br/> |Microsoft 365 Business Premium för förbereda för att ta bort företagsdata från enheten.  <br/> |
|Retire in progress (Tas nu ur bruk)  <br/> |Microsoft 365 Business Premium tar för närvarande bort företagsdata från enheten.  <br/> |
|Retire failed (Det gick inte att ta ur bruk)  <br/> | Åtgärden att ta bort företagsdata misslyckades.  <br/> |
|Retire canceled (Dra tillbaka) har avbrutits  <br/> |Åtgärden för att ta ur verksamhet har avbrutits.  <br/> |
|Wipe pending (Rensning väntar)  <br/> |Väntar på att fabriksåterställning ska starta.  <br/> |
|Wipe in progress (Rensning pågår)  <br/> |Fabriksinställning har skickats.  <br/> |
|Wipe failed (Det gick inte att rensa)  <br/> |Det gick inte göra fabriksåterställning.  <br/> |
|Rensningen har avbrutits  <br/> |Fabriksåterställningen avbröts.  <br/> |
|Unhealthy (Ej felfri)  <br/> |En åtgärd väntar (eller pågår), men enheten har inte checkats in på mer än 30 dagar.  <br/> |
|Delete pending (Väntar på att tas bort)  <br/> |Ta bort-åtgärd som väntar.  <br/> |
|Discovered (Identifierad)  <br/> |Microsoft 365 Business Premium har upptäckt enheten.  <br/> |
   
