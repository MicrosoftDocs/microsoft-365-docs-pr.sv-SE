---
title: Skapa och redigera AutoPilot-enheter
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Lär dig hur du överför enheter med AutoPilot i Microsoft 365 Business. Du kan tilldela en profil till en enhet eller grupp enheter.
ms.openlocfilehash: dee77a014ef519f3487a082edc3cf81058ec1c00
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071649"
---
# <a name="create-and-edit-autopilot-devices"></a>Skapa och redigera AutoPilot-enheter

## <a name="upload-a-list-of-devices"></a>Ladda upp en lista med enheter

Du kan använda [guiden med stegvisa anvisningar](add-autopilot-devices-and-profile.md) för att ladda upp enheter, men du kan även ladda upp dem på fliken **Enheter**. 
  
Enheter måste uppfylla följande krav:
  
- Windows 10, version 1703 eller senare.
    
- Nya enheter som inte har genomgått Windows välkomstprogram.

1. Välj **enheter** i Microsoft 365 Business Admin center, \> **AutoPilot**.
  
2. Välj fliken **enheter** på sidan **AutoPilot** \> **Lägg till enheter**.
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. På panelen **Lägg till enheter** går du till [listan över enheter CSV-fil](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) som du har förberett \> **Spara** \> **Stäng**.
    
    Du kan få den här informationen från din maskinvaruleverantör eller använda [PowerShell-skriptet Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) som skapar en CSV-fil. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Tilldela en profil till en enhet eller en grupp enheter

1. På sidan för att **förbereda Windows** väljer du fliken **Enheter** och markerar kryssrutan bredvid en eller flera enheter. 
    
2. På panelen **Enhet**, väljer du en profil från listrutan **Tilldelad profil**. 
    
    Om du inte redan har profiler hittar du anvisningar i [Skapa och redigera AutoPilot-profiler](create-and-edit-autopilot-profiles.md). 
    
