---
title: Skydda Windows 10-enheter
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
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
description: Lär dig hur du konfigurerar inställningarna för den standard enhets princip som en Windows 10-enhet kommer att få när du loggar in på sitt arbets-eller skol konto.
ms.openlocfilehash: 85448507835b6310ca4136849be6a40caf6bb919
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289086"
---
# <a name="secure-windows-10-devices"></a>Skydda Windows 10-enheter

Den här artikeln gäller Microsoft 365 Business Premium.

De inställningar som du konfigurerar här är en del av standardprincipen för Windows 10-enheter. Alla användare som ansluter en Windows 10-enhet, inklusive mobila enheter och datorer, genom att logga in med sitt arbets konto får automatiskt dessa inställningar. Vi rekommenderar att du godkänner standardprincipen under installationen och senare lägger till principer som är riktad mot särskilda grupper av användare.
  
## <a name="settings-to-secure-windows-10-devices"></a>Inställningar som skyddar Windows 10-enheter

Som standard är alla inställningar **På**. Följande inställningar är tillgängliga:
  
|||
|:-----|:-----|
|Inställning  <br/> |Beskrivning  <br/> |
|Skydda PC-datorer mot virus och andra hot med Windows Defender Antivirus  <br/> |Kräver att antivirusprogrammet Windows Defender är aktiverat för att skydda datorer från fara vid uppkoppling till internet.  <br/> |
|Skydda datorer från webbaserade hot i Microsoft Edge  <br/> |Aktiverar inställningarna Microsoft i Edge som hjälper till att skydda användare från skadliga webbplatser och nedladdningar.  <br/> |
|Skydda filer och mappar på PC-datorer från obehörig åtkomst med BitLocker  <br/> |BitLocker skyddar data genom att kryptera datorhårddiskar samt skyddar mot exponering av data om en dator försvinner eller blir stulen. Mer information finns i [vanliga frågor och svar om BitLocker](https://go.microsoft.com/fwlink/?linkid=871000).  <br/> |
|Stäng av enhetens skärm efter en viss tids inaktivitet  <br/> |Säkerställer att företagsdata skyddas om en användare är inaktiv. En användare som befinner sig på en offentlig plats, till exempel ett café, kan göra ett ärende eller låter sig distraheras för ett ögonblick, vilket gör att obehöriga kan få tillgång till enheten. Med den här inställningen kan du bestämma hur länge användaren kan vara inaktiv innan skärmen stängs av.  <br/> |
|