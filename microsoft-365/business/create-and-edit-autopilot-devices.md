---
title: Skapa och redigera AutoPilot-enheter
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
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Lär dig hur du överför enheter med AutoPilot i Microsoft 365 Business. Du kan tilldela en profil till en enhet eller grupp enheter.
ms.openlocfilehash: cc1f81e9efd9b16e27b8abfbb0927d241535077e
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982939"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="bf4d4-104">Skapa och redigera AutoPilot-enheter</span><span class="sxs-lookup"><span data-stu-id="bf4d4-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="bf4d4-105">Ladda upp en lista med enheter</span><span class="sxs-lookup"><span data-stu-id="bf4d4-105">Upload a list of devices</span></span>

<span data-ttu-id="bf4d4-106">Du kan använda [guiden med stegvisa anvisningar](add-autopilot-devices-and-profile.md) för att ladda upp enheter, men du kan även ladda upp dem på fliken **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="bf4d4-107">Enheter måste uppfylla följande krav:</span><span class="sxs-lookup"><span data-stu-id="bf4d4-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="bf4d4-108">Windows 10, version 1703 eller senare.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="bf4d4-109">Nya enheter som inte har genomgått Windows välkomstprogram.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-109">New devices that have not been through Windows out-of-box experience.</span></span>
    
1. <span data-ttu-id="bf4d4-110">I administrationscentret för Microsoft 365 Business väljer du **Distribuera Windows med AutoPilot** på kortet **Enhetsåtgärder**</span><span class="sxs-lookup"><span data-stu-id="bf4d4-110">In the Microsoft 365 Business Admin center, choose **Deploy Windows with AutoPilot** on the **Device actions** card.</span></span> 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="bf4d4-112">På sidan för att **förbereda Windows** väljer du fliken **Enheter** \> **Lägg till enheter**.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-112">On the **Prepare Windows** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="bf4d4-114">På panelen **Lägg till enheter** går du till [listan över enheter CSV-fil](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) som du har förberett \> **Spara** \> **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-114">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="bf4d4-115">Du kan få den här informationen från din maskinvaruleverantör eller använda [PowerShell-skriptet Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) som skapar en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-115">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="bf4d4-116">Tilldela en profil till en enhet eller en grupp enheter</span><span class="sxs-lookup"><span data-stu-id="bf4d4-116">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="bf4d4-117">På sidan för att **förbereda Windows** väljer du fliken **Enheter** och markerar kryssrutan bredvid en eller flera enheter.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-117">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="bf4d4-118">På panelen **Enhet**, väljer du en profil från listrutan **Tilldelad profil**.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-118">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="bf4d4-119">Om du inte redan har profiler hittar du anvisningar i [Skapa och redigera AutoPilot-profiler](create-and-edit-autopilot-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="bf4d4-119">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
