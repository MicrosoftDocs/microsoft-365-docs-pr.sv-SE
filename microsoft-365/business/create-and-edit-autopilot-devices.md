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
description: Lär dig hur du laddar upp enheter med AutoPilot i Microsoft 365 Business Premium. Du kan tilldela en profil till en enhet eller en grupp av enheter.
ms.openlocfilehash: 910abb98b94b749177b04cd12c766f82d348e379
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913407"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="066cb-104">Skapa och redigera AutoPilot-enheter</span><span class="sxs-lookup"><span data-stu-id="066cb-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="066cb-105">Ladda upp en lista med enheter</span><span class="sxs-lookup"><span data-stu-id="066cb-105">Upload a list of devices</span></span>

<span data-ttu-id="066cb-106">Du kan använda [guiden med stegvisa instruktioner för att](add-autopilot-devices-and-profile.md) ladda upp enheter, men du kan också ladda upp enheter på **fliken** Enheter.</span><span class="sxs-lookup"><span data-stu-id="066cb-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="066cb-107">Enheter måste uppfylla följande krav:</span><span class="sxs-lookup"><span data-stu-id="066cb-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="066cb-108">Windows 10, version 1703 eller senare</span><span class="sxs-lookup"><span data-stu-id="066cb-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="066cb-109">Nya enheter som inte redan är via Windows</span><span class="sxs-lookup"><span data-stu-id="066cb-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="066cb-110">I administrationscentret för Microsoft 365 väljer du **Devices** \> **AutoPilot.**</span><span class="sxs-lookup"><span data-stu-id="066cb-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="066cb-111">På sidan **AutoPilot** väljer du fliken **Enheter** Lägg \> **till enheter.**</span><span class="sxs-lookup"><span data-stu-id="066cb-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="066cb-113">På panelen **Lägg till enheter** bläddrar du till en [CSV-fil med](../admin/misc/device-list.md) enhetslistan som du har förberett \> **Spara** \> **stäng.**</span><span class="sxs-lookup"><span data-stu-id="066cb-113">On the **Add devices** panel, browse to a [Device list CSV file](../admin/misc/device-list.md) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="066cb-114">Du kan få den här informationen från din maskinvaruleverantör eller använda [PowerShell-skriptet Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) för att generera en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="066cb-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="066cb-115">Tilldela en profil till en enhet eller en grupp enheter</span><span class="sxs-lookup"><span data-stu-id="066cb-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="066cb-116">På sidan **Förbereder Windows** väljer **du fliken** Enheter och markerar kryssrutan bredvid en eller flera enheter.</span><span class="sxs-lookup"><span data-stu-id="066cb-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="066cb-117">På panelen **Enhet**, väljer du en profil från listrutan **Tilldelad profil**.</span><span class="sxs-lookup"><span data-stu-id="066cb-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="066cb-118">Om du inte redan har profiler hittar du anvisningar i [Skapa och redigera AutoPilot-profiler](create-and-edit-autopilot-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="066cb-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
