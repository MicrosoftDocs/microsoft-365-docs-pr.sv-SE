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
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="ca394-104">Skapa och redigera AutoPilot-enheter</span><span class="sxs-lookup"><span data-stu-id="ca394-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="ca394-105">Ladda upp en lista med enheter</span><span class="sxs-lookup"><span data-stu-id="ca394-105">Upload a list of devices</span></span>

<span data-ttu-id="ca394-106">Du kan använda [steg-för-steg-guiden](add-autopilot-devices-and-profile.md) för att ladda upp enheter, men du kan också ladda upp enheter på fliken **Enheter.**</span><span class="sxs-lookup"><span data-stu-id="ca394-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="ca394-107">Produkterna måste uppfylla dessa krav:</span><span class="sxs-lookup"><span data-stu-id="ca394-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="ca394-108">Windows 10, version 1703 eller senare</span><span class="sxs-lookup"><span data-stu-id="ca394-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="ca394-109">Nya enheter som inte har gått via Windows-direktupplevelse</span><span class="sxs-lookup"><span data-stu-id="ca394-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="ca394-110">I administrationscentret för Microsoft 365 väljer du **Devices** \> **Autopilot för**enheter .</span><span class="sxs-lookup"><span data-stu-id="ca394-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="ca394-111">På sidan **Autopilot** väljer du fliken **Enheter** \> **Lägg till enheter**.</span><span class="sxs-lookup"><span data-stu-id="ca394-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="ca394-113">På panelen Lägg till **enheter** bläddrar du till en [CSV-fil för enhetslistan](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) som du har förberett \> **Spara** \> **stäng**.</span><span class="sxs-lookup"><span data-stu-id="ca394-113">On the **Add devices** panel, browse to a [Device list CSV file](https://docs.microsoft.com/microsoft-365/admin/misc/device-list) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="ca394-114">Du kan hämta den här informationen från maskinvaruleverantören eller använda [Get-WindowsAutoPilotInfo PowerShell-skriptet](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) för att generera en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="ca394-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="ca394-115">Tilldela en profil till en enhet eller en grupp enheter</span><span class="sxs-lookup"><span data-stu-id="ca394-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="ca394-116">På sidan **Förbered Windows** väljer du fliken **Enheter** och markerar kryssrutan bredvid en eller flera enheter.</span><span class="sxs-lookup"><span data-stu-id="ca394-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="ca394-117">På panelen **Enhet**, väljer du en profil från listrutan **Tilldelad profil**.</span><span class="sxs-lookup"><span data-stu-id="ca394-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="ca394-118">Om du inte redan har profiler hittar du anvisningar i [Skapa och redigera AutoPilot-profiler](create-and-edit-autopilot-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ca394-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
