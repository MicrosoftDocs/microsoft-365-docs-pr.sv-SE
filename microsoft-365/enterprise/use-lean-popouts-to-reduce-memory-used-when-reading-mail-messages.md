---
title: Använd Lean popouts för att minska mängden minne som används för att läsa e-postmeddelanden
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
description: Den här artikeln innehåller information om hur du använder Lean-popouts för att förbättra nedladdnings prestanda för meddelanden i Outlook på webben.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bf53464ac6b2783fbbfc335fd4ff73dbe4435fb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694808"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>Använd Lean popouts för att minska mängden minne som används för att läsa e-postmeddelanden

Den här artikeln innehåller information om hur du förbättrar prestanda för nedladdning av meddelanden i Outlook på webben. Den här artikeln är en del av [nätverks planering och prestanda justering för Office 365](https://aka.ms/tune) Project.
  
Som en global administratör för Office 365 kan du konfigurera Outlook på webben så att det ger _Lean popouts_, en mindre, mindre minnes krävande version av vissa e-postmeddelanden i Microsoft Edge eller Internet Explorer. När Lean-popouts konfigureras för Outlook på webben laddas serverbaserade åter givnings komponenter som optimerar prestanda.
  
> [!NOTE]
> Från och med mars 2018 är Lean popouts inte tillgängliga för meddelanden som anger restriktioner för användnings rättigheter, till exempel IRM (Information Rights Management).
  
Dessa funktioner fortsätter att fungera i huvud fönstret men är inte tillgängliga i Lean-popouts:
  
- Outlook-tillägg
  
- Skype för företag – närvaro
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>Konfigurera Lean-popouts för alla användare i din Office 365-organisation
  
1. [Ansluta till Exchange Online med fjärr-PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx ).
  
2. Kör cmdleten [set-OrganizationConfig](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) med parametern LeanPopoutEnabled så här:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  Om du till exempel vill aktivera Lean-popouts för alla användare i organisationen:
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  Så här inaktiverar du Lean-popouts för alla användare i organisationen:

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
