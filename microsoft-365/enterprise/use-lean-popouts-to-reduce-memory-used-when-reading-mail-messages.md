---
title: Använd mindre stödmeddelanden för att minska det minne som används när du läser e-postmeddelanden
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: Den här artikeln innehåller information om hur du kan använda smidiga popup-fönster för att förbättra prestanda för nedladdning Outlook meddelanden på webben.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925262"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>Använd mindre stödmeddelanden för att minska det minne som används när du läser e-postmeddelanden

Den här artikeln innehåller information om hur du förbättrar prestanda för nedladdning Outlook meddelanden på webben. Den här artikeln är en del [av Nätverksplanering och prestandajustering för Office 365](./network-planning-and-performance.md) projekt.
  
Som global Office 365 kan du konfigurera Outlook på webben så att du får mindre, mindre minneskrävande versioner av vissa e-postmeddelanden i Microsoft Edge eller Internet Explorer. När lutande popup-fönster konfigureras för Outlook-fönster på webben läses återgivna komponenter in på servern som optimerar prestanda.
  
> [!NOTE]
> Från och med mars 2018 går det inte att använda magera popup-fönster för meddelanden som anger begränsningar av användningsrättigheter, till exempel IRM (Information Rights Management).
  
De här funktionerna kommer att fortsätta att fungera i huvudfönstret men är inte tillgängliga i mer smidiga popup-fönster:
  
- Outlook tillägg
  
- Skype för företag närvaro
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>Konfigurera smidiga popup-fönster för alla användare i Office 365 organisation
  
1. [Anslut att Exchange Online använda Remote PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)
  
2. Kör [cmdleten Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) med parametern LeanPopoutEnabled enligt följande:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  Om du till exempel vill aktivera smidiga popup-fönster för alla användare i organisationen:
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  Så här inaktiverar du magera popup-fönster för alla användare i organisationen:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```