---
title: Skapa och redigera AutoPilot-enheter
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Lär dig hur du överför enheter med AutoPilot i Microsoft 365 Business. Du kan tilldela en profil till en enhet eller grupp enheter.
ms.openlocfilehash: fff2dbc6af45ef9d4189f23849d638172c19dfb2
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277075"
---
# <a name="create-and-edit-autopilot-devices"></a>Skapa och redigera AutoPilot-enheter

## <a name="upload-a-list-of-devices"></a>Ladda upp en lista med enheter

Du kan använda [guiden med stegvisa anvisningar](add-autopilot-devices-and-profile.md) för att ladda upp enheter, men du kan även ladda upp dem på fliken **Enheter**. 
  
Enheter måste uppfylla följande krav:
  
- Windows 10, version 1703 eller senare.
    
- Nya enheter som inte har genomgått Windows välkomstprogram.

1. Välj **enheter** i Microsoft 365 Business Admin center, \> **AutoPilot** \> **Lägg till**.
  
2. På sidan för att **förbereda Windows** väljer du fliken **Enheter** \> **Lägg till enheter**.
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. På panelen **Lägg till enheter** går du till [listan över enheter CSV-fil](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) som du har förberett \> **Spara** \> **Stäng**.
    
    Du kan få den här informationen från din maskinvaruleverantör eller använda [PowerShell-skriptet Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) som skapar en CSV-fil. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Tilldela en profil till en enhet eller en grupp enheter

1. På sidan för att **förbereda Windows** väljer du fliken **Enheter** och markerar kryssrutan bredvid en eller flera enheter. 
    
2. På panelen **Enhet**, väljer du en profil från listrutan **Tilldelad profil**. 
    
    Om du inte redan har profiler hittar du anvisningar i [Skapa och redigera AutoPilot-profiler](create-and-edit-autopilot-profiles.md). 
    
