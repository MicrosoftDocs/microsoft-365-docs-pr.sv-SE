---
title: Bekräfta programskyddsinställningar på PC-datorer med Windows 10
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Läs om hur du verifierar att inställningarna för skydd av Microsoft 365 för företag-appar trädde i kraft på användarnas Windows 10-enheter.
ms.openlocfilehash: 39aee3bc811cb0090d58f9a282de7a8162c097b3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403599"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Validera inställningar för enhetsskydd på PC-datorer med Windows 10

## <a name="verify-that-windows-10-device-policies-are-set"></a>Kontrollera att principer för Windows 10-enheter har angetts

När du [konfigurerat principer för enheter](protection-settings-for-windows-10-pcs.md) kan det ta några timmar innan principen börjar gälla på användarnas enheter. Du kan bekräfta att principerna har verkställts genom att titta på olika skärmar för Windows-inställningar på användarnas enheter. Eftersom användarna inte kan ändra inställningarna för Windows Update och Windows Defender Antivirus på sina Windows 10-enheter kommer många alternativ att vara nedtonade.
  
1. Gå till **Alternativ för** uppdatering av \> ** &amp; säkerhetsinställningar** \> **i Windows Update** och bekräfta att alla inställningar är \> **Restart options** nedtonade. 
    
    ![Alla omstartsalternativ är nedtonade.](../media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Gå **Settings** till \> **Alternativuppdatering &amp; av säkerhet** Windows \> **Update** Avancerade \> **alternativ** och bekräfta att alla inställningar är nedtonade. 
    
    ![Alternativen för avancerade uppdateringar i Windows är nedtonade.](../media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Go to **Settings** \> **Update &amp; security** \> **Windows Update** \> **Advanced options** \> **Choose how updates are delivered**.
    
    Bekräfta att du kan se meddelandet (i rött) att vissa inställningar är dolda eller hanterade av din organisation och att alla alternativ är nedtonade.
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](../media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. To open the Windows Defender Security Center, go to **Settings** \> **Update &amp; security** \> **Windows Defender** \> click **Open Windows Defender Security Center** \> **Virus &amp; thread protection** \> **Virus &amp; threat protection settings**. 
    
5. Kontrollera att alla alternativ är nedtonade. 
    
    ![Inställningarna för virus- och hotskydd är nedtonade.](../media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Relaterade ämnen

[Microsoft 365 för affärsdokumentation och resurser](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Komma igång med Microsoft 365 för företag](microsoft-365-business-overview.md)
  
[Hantera Microsoft 365 för företag](manage.md)
  
[Ange enhetskonfigurationer för Windows 10-datorer](protection-settings-for-windows-10-pcs.md)
  

