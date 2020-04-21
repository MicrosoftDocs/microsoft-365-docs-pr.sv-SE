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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Lär dig hur du laddar upp enheter med AutoPilot i Microsoft 365 Business Premium. Du kan tilldela en profil till en enhet eller en grupp enheter.
ms.openlocfilehash: f2a7f801ae471352595a36b355a874b2de653326
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627403"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="37ff3-104">Skapa och redigera AutoPilot-enheter</span><span class="sxs-lookup"><span data-stu-id="37ff3-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="37ff3-105">Ladda upp en lista med enheter</span><span class="sxs-lookup"><span data-stu-id="37ff3-105">Upload a list of devices</span></span>

<span data-ttu-id="37ff3-106">Du kan använda [steg-för-steg-guiden](add-autopilot-devices-and-profile.md) för att ladda upp enheter, men du kan också ladda upp enheter på fliken **Enheter.**</span><span class="sxs-lookup"><span data-stu-id="37ff3-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="37ff3-107">Produkterna måste uppfylla dessa krav:</span><span class="sxs-lookup"><span data-stu-id="37ff3-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="37ff3-108">Windows 10, version 1703 eller senare</span><span class="sxs-lookup"><span data-stu-id="37ff3-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="37ff3-109">Nya enheter som inte har gått via Windows-direktupplevelse</span><span class="sxs-lookup"><span data-stu-id="37ff3-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="37ff3-110">I administrationscentret för Microsoft 365 väljer du **Autopilot för** **enheter** \> .</span><span class="sxs-lookup"><span data-stu-id="37ff3-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="37ff3-111">På sidan **Autopilot** väljer du \> fliken **Enheter** **Lägg till enheter**.</span><span class="sxs-lookup"><span data-stu-id="37ff3-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="37ff3-113">På panelen **Lägg** till enheter bläddrar du till en [CSV-fil för enhetslistan](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) som du har förberett \> **Spara** \> **stäng**.</span><span class="sxs-lookup"><span data-stu-id="37ff3-113">On the **Add devices** panel, browse to a [Device list CSV file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="37ff3-114">Du kan hämta den här informationen från maskinvaruleverantören eller använda [Get-WindowsAutoPilotInfo PowerShell-skriptet](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) för att generera en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="37ff3-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="37ff3-115">Tilldela en profil till en enhet eller en grupp enheter</span><span class="sxs-lookup"><span data-stu-id="37ff3-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="37ff3-116">På sidan **Förbered Windows** väljer du fliken **Enheter** och markerar kryssrutan bredvid en eller flera enheter.</span><span class="sxs-lookup"><span data-stu-id="37ff3-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="37ff3-117">På panelen **Enhet**, väljer du en profil från listrutan **Tilldelad profil**.</span><span class="sxs-lookup"><span data-stu-id="37ff3-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="37ff3-118">Om du inte redan har profiler hittar du anvisningar i [Skapa och redigera AutoPilot-profiler](create-and-edit-autopilot-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="37ff3-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
