---
title: Felsöka AutoPilot-enhetsfel
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
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
ms.openlocfilehash: 9b8d8ab424dd3189ff5c228dab8f5c513ff5dafc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26982749"
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
|Den här enheten stöds inte för installation med hjälp av AutoPilot  <br/> | Detta fel innebär att enheten inte uppfyller kraven för distribution av AutoPilot. Enheter måste uppfylla dessa krav:  <br/>  Windows 10, version 1703 eller senare.  <br/>  Nya enheter som inte har genomgått Windows välkomstprogram.  <br/> |
|Enheten hittades inte  <br/> |Detta fel innebär att en eller flera enheter i CSV-filen inte har registrerats för din organisation. Lös problemet genom att be maskinvaruleverantören om hjälp.  <br/> |
   
