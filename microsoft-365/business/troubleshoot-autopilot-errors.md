---
title: Felsöka AutoPilot-enhetsfel
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Lär dig felsöka AutoPilot enhet filfel.
ms.openlocfilehash: 88b59ec20ddda401c1dac45ff729ac38497a767e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074369"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Felsöka AutoPilot-enhetsfel

## <a name="device-file-error-messages"></a>Meddelanden om filfel enhet

Här är info om fel visas när du arbetar med filer i Microsoft 365 Business AutoPilot. 
  
|**Felkod**|**Att försöka åtgärda**|
|:-----|:-----|
|Ogiltig begäran brödtext  <br/> |Detta fel bör inträffa sällan, om du ser felet, försök igen.  <br/> |
|Maskinvaru-hashvärdet för en enhet inte är korrekt.  <br/> |Om det här felet visas innebär det att det värde som du angav i CSV-filen för maskinvaru-hash av en enhet inte är korrekt. Kontrollera först att värdet är korrekt. Om du tror att värdet är korrekt, men det här felet sker fortfarande fråga maskinvaruleverantören för hjälp.  <br/> |
|Enhet som är tilldelad till en annan innehavare  <br/> |Om det här felet visas innebär det att värdet som anges i CSV-filen för serienumret eller produktnyckeln för en eller flera enheter inte är korrekt. Kontrollera först att värdet är korrekt. Om du tror att värdet är korrekt, men det här felet sker fortfarande fråga maskinvaruleverantören för hjälp.  <br/> |
|CSV-filen innehåller ett ogiltigt serienummer eller produktnyckel  <br/> |Om du ser felet innebär det att enheten som uppstod när du registrerar redan registrerats av en annan organisation. Lös problemet genom att be maskinvaruleverantören om hjälp.  <br/> |
|Den här enheten stöds inte för installation med hjälp av AutoPilot  <br/> | Detta fel innebär att enheten inte uppfyller kraven för distribution av AutoPilot. Enheter måste uppfylla följande krav:  <br/>  Windows 10, version 1703 eller senare.  <br/>  Nya enheter som inte har genomgått Windows välkomstprogram.  <br/> |
|Enheten hittades inte  <br/> |Detta fel innebär att en eller flera enheter i CSV-filen inte har registrerats för din organisation. Lös problemet genom att be maskinvaruleverantören om hjälp.  <br/> |
   
