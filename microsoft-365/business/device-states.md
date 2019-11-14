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
ms.openlocfilehash: b55e6a5d538ec28d195225e93797cea27afd2e8b
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38320217"
---
# <a name="device-states"></a>Statusvärden för enheter

Enheter i listan **Enhetsåtgärder** (Administratörshemsida \> **Enhetsåtgärder**) kan ha följande statusar.
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|**Status**|**Beskrivning**|
|:-----|:-----|
|Managed by Intune (Hanteras av Intune)  <br/> |Hanterad av Microsoft 365 Business.  <br/> |
|Retire pending (Väntar på att tas ur bruk)  <br/> |Microsoft 365 Business förbereds för att ta bort företagsdata från enheten.  <br/> |
|Retire in progress (Tas nu ur bruk)  <br/> |Microsoft 365 Business tar för närvarande bort företagsdata från enheten.  <br/> |
|Retire failed (Det gick inte att ta ur bruk)  <br/> | Åtgärden att ta bort företagsdata misslyckades.  <br/> |
|Pensionerad annullerad  <br/> |Tillbakadragen åtgärd avbröts.  <br/> |
|Wipe pending (Rensning väntar)  <br/> |Väntar på att fabriksåterställning ska starta.  <br/> |
|Wipe in progress (Rensning pågår)  <br/> |Fabriksinställning har skickats.  <br/> |
|Wipe failed (Det gick inte att rensa)  <br/> |Det gick inte att återställa standardinställningarna.  <br/> |
|Rensa annullerad  <br/> |Fabriks rensning avbröts.  <br/> |
|Unhealthy (Ej felfri)  <br/> |En åtgärd pågår (eller pågår), men enheten har inte checkats in i 30 + dagar.  <br/> |
|Delete pending (Väntar på att tas bort)  <br/> |Ta bort-åtgärd som väntar.  <br/> |
|Discovered (Identifierad)  <br/> |Microsoft 365 Business har upptäckt enheten.  <br/> |
   
