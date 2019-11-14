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
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Lär dig hur du laddar upp enheter med AutoPilot i Microsoft 365 Business. Du kan tilldela en profil till en enhet eller en grupp av enheter.
ms.openlocfilehash: 1dd6b1a574166379e29465bf3699e47e3b155e0b
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38320267"
---
# <a name="create-and-edit-autopilot-devices"></a>Skapa och redigera AutoPilot-enheter

## <a name="upload-a-list-of-devices"></a>Ladda upp en lista med enheter

Du kan använda [steg-för-steg-guiden](add-autopilot-devices-and-profile.md) för att överföra enheter, men du kan också ladda upp enheter på fliken **enheter** . 
  
Enheter måste uppfylla följande krav:
  
- Windows 10, version 1703 eller senare
    
- Nya enheter som inte har gått igenom Windows out-of-Box-upplevelse

1. I Microsoft 365 Business administratörscenter väljer du **enheter** \> **autopilot**.
  
2. På sidan **autopilot** väljer du \> fliken **enheter** **Lägg till enheter**.
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. På panelen **Lägg till enheter** bläddrar du till en [Enhetslista CSV-fil](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) som du \> har förberett **Spara** \> **Stäng**.
    
    Du kan hämta den här informationen från maskinvaruleverantören, eller så kan du använda [PowerShell-skriptet get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) för att generera en CSV-fil. 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a>Tilldela en profil till en enhet eller en grupp enheter

1. På sidan **Förbered Windows** väljer du fliken **enheter** och markerar kryssrutan bredvid en eller flera enheter. 
    
2. På panelen **Enhet**, väljer du en profil från listrutan **Tilldelad profil**. 
    
    Om du inte redan har profiler hittar du anvisningar i [Skapa och redigera AutoPilot-profiler](create-and-edit-autopilot-profiles.md). 
    
