---
title: Skapa och redigera AutoPilot-enheter
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Lär dig hur du laddar upp enheter med AutoPilot i Microsoft 365 Business Premium. Du kan tilldela en profil till en enhet eller en grupp enheter.
ms.openlocfilehash: 8c3d029d682ae30444bdc7d30a4790a8f982e0e0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401003"
---
# <a name="create-and-edit-autopilot-devices"></a>Skapa och redigera AutoPilot-enheter

## <a name="upload-a-list-of-devices"></a>Ladda upp en lista med enheter

Du kan använda [steg-för-steg-guiden](add-autopilot-devices-and-profile.md) för att ladda upp enheter, men du kan också ladda upp enheter på fliken **Enheter.** 
  
Produkterna måste uppfylla dessa krav:
  
- Windows 10, version 1703 eller senare
    
- Nya enheter som inte har gått via Windows-direktupplevelse

1. I administrationscentret för Microsoft 365 väljer du **Devices** \> **Autopilot för**enheter .
  
2. På sidan **Autopilot** väljer du fliken **Enheter** \> **Lägg till enheter**.
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. På panelen Lägg till **enheter** bläddrar du till en [CSV-fil för enhetslistan](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) som du har förberett \> **Spara** \> **stäng**.
    
    Du kan hämta den här informationen från maskinvaruleverantören eller använda [Get-WindowsAutoPilotInfo PowerShell-skriptet](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) för att generera en CSV-fil. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Tilldela en profil till en enhet eller en grupp enheter

1. På sidan **Förbered Windows** väljer du fliken **Enheter** och markerar kryssrutan bredvid en eller flera enheter. 
    
2. På panelen **Enhet**, väljer du en profil från listrutan **Tilldelad profil**. 
    
    Om du inte redan har profiler hittar du anvisningar i [Skapa och redigera AutoPilot-profiler](create-and-edit-autopilot-profiles.md). 
    
