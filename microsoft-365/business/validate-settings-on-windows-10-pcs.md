---
title: Bekräfta programskyddsinställningar på PC-datorer med Windows 10
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
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
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Lär dig att kontrollera att Microsoft 365 för företag-programskyddsinställningarna verkställde på dina användares Windows 10 enheter.
ms.openlocfilehash: fcb463fd98f692f7d4802689e0c03fe4e3e648a1
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579851"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Validera inställningar för enhetsskydd på PC-datorer med Windows 10

## <a name="verify-that-windows-10-device-policies-are-set"></a>Kontrollera att principer för Windows 10-enheter har angetts

När du [konfigurerat principer för enheter](protection-settings-for-windows-10-pcs.md) kan det ta några timmar innan principen börjar gälla på användarnas enheter. Du kan bekräfta att principerna har verkställts genom att titta på olika skärmar för Windows-inställningar på användarnas enheter. Eftersom användarna inte kan ändra inställningarna för Windows Update och Windows Defender Antivirus på sina Windows 10-enheter är många alternativ nedtonade.
  
1. Gå till **Inställningar** \> **&amp; säkerhetsalternativ Windows** omstart av uppdatering och kontrollera att alla inställningar är \>  \>  nedtonade. 
    
    ![Alla alternativ för omstart är nedtonade.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Gå till **Inställningar** \> **i &amp; Windows** \> **uppdatera** \> **avancerade alternativ** och kontrollera att alla inställningar är nedtonade. 
    
    ![Windows Alternativen för avancerade uppdateringar är nedtonade.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.
    
    Bekräfta att du kan se meddelandet (i rött) om att vissa inställningar är dolda eller hanteras av din organisation och att alla alternativ är nedtonade.
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**. 
    
5. Kontrollera att alla alternativ är nedtonade. 
    
    ![Inställningarna för skydd mot virus och hot är nedtonade.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Relaterade ämnen

[Microsoft 365 dokumentation och resurser för företag](./index.yml)
  
[Komma igång med Microsoft 365 för företag](microsoft-365-business-overview.md)
  
[Hantera Microsoft 365 för företag](manage.md)
  
[Ange enhetskonfigurationer för Windows 10-datorer](protection-settings-for-windows-10-pcs.md)
