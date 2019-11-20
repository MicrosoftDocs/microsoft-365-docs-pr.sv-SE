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
description: Läs om hur du felsöker fel i Autopilotenhetsfiler.
ms.openlocfilehash: 1b5358bd6686c2548e82ec5297ac0ad675835718
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/19/2019
ms.locfileid: "38718708"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Felsöka AutoPilot-enhetsfel

## <a name="device-file-error-messages"></a>Felmeddelanden för enhetsfil

Här är information om några av de fel som du kan se när du arbetar med AutoPilot-enhetsfiler i Microsoft 365 Business. 
  
|**Felkod**|**Fix för att försöka**|
|:-----|:-----|
|Ogiltigt begäranbrödtext  <br/> |Det här felet bör inträffa sällan, om du ser det här felet, försök igen.  <br/> |
|Maskinvaru-hash-värde för en enhet är inte korrekt.  <br/> |Om du ser det här felet innebär det att värdet som du angav i CSV-filen för maskinvaru-hash för en enhet inte är korrekt. Kontrollera först att värdet har skrivits korrekt. Om du tror att värdet är korrekt, men det här felet fortfarande händer, be maskinvaruleverantören om hjälp.  <br/> |
|Enhet tilldelad till en annan klientorganisation  <br/> |Om du ser det här felet betyder det att värdet som du angav i CSV-filen för antingen serienumret eller produktnyckeln för en eller flera enheter inte är korrekt. Kontrollera först att värdet har skrivits korrekt. Om du tror att värdet är korrekt, men det här felet fortfarande händer, be maskinvaruleverantören om hjälp.  <br/> |
|CSV-filen innehåller ett ogiltigt serienummer eller produkt nyckel  <br/> |Om du ser det här felet innebär det att enheten som du försöker registrera redan har registrerats av en annan organisation. Om du vill åtgärda det här felet kan du be maskinvaruleverantören om hjälp.  <br/> |
|Den här enheten stöds inte för installation med hjälp av AutoPilot  <br/> | Det här felet innebär att enheten inte uppfyller Autopilotdistributionskrav. Enheter måste uppfylla följande krav:  <br/>  Windows 10, version 1703 eller senare.  <br/>  Nya enheter som inte har gått igenom Windows out-of-Box-upplevelse.  <br/> |
|Enheten hittades inte  <br/> |Det här felet innebär att en eller flera enheter i CSV-filen inte är registrerade i din organisation. Du åtgärdar detta genom att be maskinvaruleverantören om hjälp.  <br/> |
