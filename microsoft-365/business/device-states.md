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
# <a name="device-states"></a>Statusvärden för enheter

Enheter i listan **Enhetsåtgärder** (Administratörshemsida \> **Enhetsåtgärder**) kan ha följande statusar.
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|**Status**|**Beskrivning**|
|:-----|:-----|
|Managed by Intune (Hanteras av Intune)  <br/> |Hanterad av Microsoft 365 Business.  <br/> |
|Retire pending (Väntar på att tas ur bruk)  <br/> |Microsoft 365 Business förbereds för att ta bort företagsdata från enheten.  <br/> |
|Retire in progress (Tas nu ur bruk)  <br/> |Microsoft 365 Business tar för närvarande bort företagsdata från enheten.  <br/> |
|Retire failed (Det gick inte att ta ur bruk)  <br/> | Åtgärden att ta bort företagsdata misslyckades.  <br/> |
|Pensionerad avbruten  <br/> |Åtgärden för pensionering avbröts.  <br/> |
|Wipe pending (Rensning väntar)  <br/> |Väntar på att fabriksåterställning ska starta.  <br/> |
|Wipe in progress (Rensning pågår)  <br/> |Fabriksinställning har skickats.  <br/> |
|Wipe failed (Det gick inte att rensa)  <br/> |Det gick inte att återställa fabriksåterställningen.  <br/> |
|Wipe avbröts  <br/> |Fabriksrensningen avbröts.  <br/> |
|Unhealthy (Ej felfri)  <br/> |En åtgärd väntar (eller pågår), men enheten har inte checkat in på 30 dagar.  <br/> |
|Delete pending (Väntar på att tas bort)  <br/> |Ta bort-åtgärd som väntar.  <br/> |
|Discovered (Identifierad)  <br/> |Microsoft 365 Business har upptäckt enheten.  <br/> |
   
