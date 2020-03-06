---
title: Felsöka AutoPilot-enhetsfel
f1.keywords:
- NOCSH
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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Läs om hur du felsöker fel som kan visas när du arbetar med AutoPilot-enhetsfiler i Microsoft 365 Business.
ms.openlocfilehash: 7569f18097a1f5959b3dd491958c78886e1e05d6
ms.sourcegitcommit: 41c0bc5cf50f4ca63b4286d1ea0f58ab82984b7a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/05/2020
ms.locfileid: "42547480"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Felsöka AutoPilot-enhetsfel

## <a name="device-file-error-messages"></a>Felmeddelanden i enhetsfiler

Här är information om några av de fel du kan se när du arbetar med AutoPilot-enhetsfiler i Microsoft 365 Business. 
  
|**Felkod**|**Fix för att prova**|
|:-----|:-----|
|Ogiltigt begärandeorgan  <br/> |Det här felet bör inträffa sällan, om du ser det här felet, försök åtgärden igen.  <br/> |
|Maskinvaruhash-värdet för en enhet är inte korrekt.  <br/> |Om det här felet visas betyder det att värdet du angav i CSV-filen för maskinvaruhash för en enhet inte är korrekt. Kontrollera först att värdet har skrivits korrekt. Om du tror att värdet är korrekt, men det här felet fortfarande pågår, ber du maskinvaruleverantören om hjälp.  <br/> |
|Enhet som tilldelats en annan klient  <br/> |Om det här felet visas betyder det att värdet du angav i CSV-filen för antingen serienumret eller produktnyckeln för en eller flera enheter inte är korrekt. Kontrollera först att värdet har skrivits korrekt. Om du tror att värdet är korrekt, men det här felet fortfarande pågår, ber du maskinvaruleverantören om hjälp.  <br/> |
|CSV-filen innehåller ett ogiltigt serienummer eller produktnyckel  <br/> |Om felet visas betyder det att enheten som du försöker registrera redan är registrerad av en annan organisation. Om du vill åtgärda det här felet ber du maskinvaruleverantören om hjälp.  <br/> |
|Den här enheten stöds inte för installation med hjälp av AutoPilot  <br/> | Det här felet innebär att enheten inte uppfyller AutoPilot-distributionskraven. Enheter måste uppfylla följande krav:  <br/>  Windows 10, version 1703 eller senare.  <br/>  Nya enheter som inte har gått igenom Windows out-of-box-upplevelse.  <br/> |
|Enheten hittades inte  <br/> |Det här felet innebär att en eller flera enheter i CSV-filen inte är registrerad i din organisation. Om du vill åtgärda detta ber du maskinvaruleverantören om hjälp.  <br/> |
