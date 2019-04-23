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
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="bcf52-104">Skapa och redigera AutoPilot-enheter</span><span class="sxs-lookup"><span data-stu-id="bcf52-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="bcf52-105">Ladda upp en lista med enheter</span><span class="sxs-lookup"><span data-stu-id="bcf52-105">Upload a list of devices</span></span>

<span data-ttu-id="bcf52-106">Du kan använda [guiden med stegvisa anvisningar](add-autopilot-devices-and-profile.md) för att ladda upp enheter, men du kan även ladda upp dem på fliken **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="bcf52-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="bcf52-107">Enheter måste uppfylla följande krav:</span><span class="sxs-lookup"><span data-stu-id="bcf52-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="bcf52-108">Windows 10, version 1703 eller senare.</span><span class="sxs-lookup"><span data-stu-id="bcf52-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="bcf52-109">Nya enheter som inte har genomgått Windows välkomstprogram.</span><span class="sxs-lookup"><span data-stu-id="bcf52-109">New devices that have not been through Windows out-of-box experience.</span></span>

1. <span data-ttu-id="bcf52-110">Välj **enheter** i Microsoft 365 Business Admin center, \> **AutoPilot** \> **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="bcf52-110">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot** \> **Add**.</span></span>
  
2. <span data-ttu-id="bcf52-111">På sidan för att **förbereda Windows** väljer du fliken **Enheter** \> **Lägg till enheter**.</span><span class="sxs-lookup"><span data-stu-id="bcf52-111">On the **Prepare Windows** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="bcf52-113">På panelen **Lägg till enheter** går du till [listan över enheter CSV-fil](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) som du har förberett \> **Spara** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="bcf52-113">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="bcf52-114">Du kan få den här informationen från din maskinvaruleverantör eller använda [PowerShell-skriptet Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) som skapar en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="bcf52-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="bcf52-115">Tilldela en profil till en enhet eller en grupp enheter</span><span class="sxs-lookup"><span data-stu-id="bcf52-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="bcf52-116">På sidan för att **förbereda Windows** väljer du fliken **Enheter** och markerar kryssrutan bredvid en eller flera enheter.</span><span class="sxs-lookup"><span data-stu-id="bcf52-116">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="bcf52-117">På panelen **Enhet**, väljer du en profil från listrutan **Tilldelad profil**.</span><span class="sxs-lookup"><span data-stu-id="bcf52-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="bcf52-118">Om du inte redan har profiler hittar du anvisningar i [Skapa och redigera AutoPilot-profiler](create-and-edit-autopilot-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="bcf52-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
