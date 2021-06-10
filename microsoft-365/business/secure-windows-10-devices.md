---
title: Skydda Windows 10-enheter
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4WindowsConfig
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 21e5551f-fa35-4f13-9418-f80d668b6a2b
description: Läs mer om hur du konfigurerar inställningarna för standardprincipen för enheter som Windows 10 enhet får när de loggar in på sitt arbets- eller skolkonto.
ms.openlocfilehash: 86db1c152f9f6ac1fe6093b4a55a74b69fbd8b0f
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579983"
---
# <a name="secure-windows-10-devices"></a>Skydda Windows 10-enheter

Den här artikeln gäller för Microsoft 365 Business Premium.

De inställningar som du konfigurerar här är en del av standardprincipen för Windows 10-enheter. Alla användare som ansluter en Windows 10 enhet, inklusive mobila enheter och datorer, genom att logga in med sitt arbetskonto får automatiskt de här inställningarna. Vi rekommenderar att du godkänner standardprincipen under installationen och senare lägger till principer som är riktad mot särskilda grupper av användare.
  
## <a name="settings-to-secure-windows-10-devices"></a>Inställningar som skyddar Windows 10-enheter

Som standard är alla inställningar **På**. Följande inställningar är tillgängliga:
  
|||
|:-----|:-----|
|Inställning  <br/> |Beskrivning  <br/> |
|Skydda PC-datorer mot virus och andra hot med Windows Defender Antivirus  <br/> |Kräver att antivirusprogrammet Windows Defender är aktiverat för att skydda datorer från fara vid uppkoppling till internet.  <br/> |
|Skydda datorer från webbaserade hot i Microsoft Edge  <br/> |Aktiverar inställningarna Microsoft i Edge som hjälper till att skydda användare från skadliga webbplatser och nedladdningar.  <br/> |
|Skydda filer och mappar på PC-datorer från obehörig åtkomst med BitLocker  <br/> |BitLocker skyddar data genom att kryptera datorhårddiskar samt skyddar mot exponering av data om en dator försvinner eller blir stulen. Mer information finns i Vanliga [frågor och svar om Bitlocker.](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions)  <br/> |
|Stäng av enhetens skärm efter en viss tids inaktivitet  <br/> |Säkerställer att företagsdata skyddas om en användare är inaktiv. En användare som befinner sig på en offentlig plats, till exempel ett café, kan göra ett ärende eller låter sig distraheras för ett ögonblick, vilket gör att obehöriga kan få tillgång till enheten. Med den här inställningen kan du bestämma hur länge användaren kan vara inaktiv innan skärmen stängs av.  <br/> |
|