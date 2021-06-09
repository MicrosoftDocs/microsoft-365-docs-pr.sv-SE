---
title: Felsöka AutoPilot-enhetsfel
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Lär dig hur du felsöker fel som kan visas när du arbetar med AutoPilot-enhetsfiler i Microsoft 365 Business Premium.
ms.openlocfilehash: 1078ab74b07952e4bb565555a081b98ecce9db5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578096"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Felsöka AutoPilot-enhetsfel

## <a name="device-file-error-messages"></a>Felmeddelanden om enhetsfil

Här finns information om några av de fel som kan visas när du arbetar med AutoPilot-enhetsfiler i Microsoft 365 Business Premium. 
  
|**Felkod**|**Prova genom att åtgärda**|
|:-----|:-----|
|Ogiltig begärans brödtext  <br/> |Det här felet bör sällan inträffa om du ser det här felet och prova åtgärden igen.  <br/> |
|Maskinvaruhashvärdet för en enhet är inte rätt.  <br/> |Om du ser det här felet innebär det att värdet du angav i CSV-filen för maskinvaruhash för en enhet inte är rätt. Kontrollera först att värdet har skrivits in korrekt. Om du tror att värdet är rätt, men det här felet kvarstår, ber du din maskinvaruleverantör om hjälp.  <br/> |
|Enhet tilldelad till en annan klientorganisation  <br/> |Om du ser det här felet innebär det att värdet som du angav i CSV-filen för antingen serienumret eller produktnyckeln för en eller flera enheter inte är korrekt. Kontrollera först att värdet har skrivits in korrekt. Om du tror att värdet är rätt, men det här felet kvarstår, ber du din maskinvaruleverantör om hjälp.  <br/> |
|CSV-filen innehåller ett ogiltigt serienummer eller produktnyckel  <br/> |Om du ser det här felet innebär det att enheten som du försöker registrera redan är registrerad av en annan organisation. Om du vill åtgärda det här felet ber du din maskinvaruleverantör om hjälp.  <br/> |
|Den här enheten stöds inte för konfiguration med hjälp av AutoPilot  <br/> | Det här felet innebär att enheten inte uppfyller AutoPilot-distributionskraven. Enheter måste uppfylla följande krav:  <br/>  Windows 10, version 1703 eller senare.  <br/>  Nya enheter som inte redan Windows kommer att vara helt nya.  <br/> |
|Enheten hittades inte  <br/> |Det här felet innebär att en eller flera enheter i CSV-filen inte är registrerade i din organisation. Om du vill lösa detta ber du din maskinvaruleverantör om hjälp.  <br/> |
