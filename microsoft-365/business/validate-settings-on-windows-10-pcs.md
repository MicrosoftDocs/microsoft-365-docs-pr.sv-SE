---
title: Bekräfta programskyddsinställningar på PC-datorer med Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Lär dig hur du validerar Microsoft 365 Business app inställningar i Windows 10 enheter.
ms.openlocfilehash: db05c86bd75cc30e22e025034a3dab478d0f5365
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26982709"
---
# <a name="validate-device-protection-settings-on-windows-10-pcs"></a>Validera inställningar för enhetsskydd på PC-datorer med Windows 10

## <a name="verify-that-windows-10-device-policies-are-set"></a>Kontrollera att principer för Windows 10-enheter har angetts

När du [konfigurerat principer för enheter](protection-settings-for-windows-10-pcs.md) kan det ta några timmar innan principen börjar gälla på användarnas enheter. Du kan bekräfta att principerna har verkställts genom att titta på olika skärmar för Windows-inställningar på användarnas enheter. Eftersom användarna inte kan ändra inställningarna för Windows Update och Windows Defender Antivirus på sina Windows 10-enheter kommer många av de här alternativen vara nedtonade.
  
1. Gå till **Inställningar** \> **uppdatering &amp; säkerhet** \> **Windows Update** \> **Starta om alternativ** och bekräfta att alla inställningar är nedtonade. 
    
    ![All the Restart options are greyed out.](media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. Gå till **Inställningar** \> **uppdatering &amp; säkerhet** \> **Windows Update** \> **Avancerade alternativ** och kontrollera att alla inställningar är nedtonade. 
    
    ![Windows Advanced updates options are all greyed out.](media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. Gå till **Inställningar** \> **uppdatering &amp; säkerhet** \> **Windows Update** \> **Avancerade alternativ** \> **Välj hur uppdateringar levereras**.
    
    Bekräfta att du kan se meddelandet (i rött) om att vissa inställningar är dolda eller hanteras av din organisation och att alla alternativ är nedtonade.
    
    ![Choose how updates are delivered page indicates settings are hidden or managed by your organization.](media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Om du vill öppna Säkerhetscenter för Windows Defender går du till **Inställningar** \> **uppdatering &amp; säkerhet** \> **Windows Defender** \> Klicka på **Öppna Säkerhetscenter i Windows Defender** \> **Virus &amp; tråd skydd** \> **Virus &amp; hot skyddsinställningar**. 
    
5. Kontrollera att alla alternativ är nedtonade. 
    
    ![The Virus and threat protection settings are greyed out.](media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-topics"></a>Närliggande avsnitt

[Microsoft 365 Business dokumentation och resurser](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Komma igång med Microsoft 365 för företag](microsoft-365-business-overview.md)
  
[Hantera Microsoft 365 Business](manage.md)
  
[Ange enhetskonfigurationer för Windows 10-datorer](protection-settings-for-windows-10-pcs.md)
  

