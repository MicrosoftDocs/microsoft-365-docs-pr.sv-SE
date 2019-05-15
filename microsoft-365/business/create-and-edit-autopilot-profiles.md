---
title: Skapa och redigera AutoPilot-profiler
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
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 'Lär dig att skapa, redigera, ta bort eller ta bort AutoPilot profiler. '
ms.openlocfilehash: 7987cafb3ea234d81be72c79aee8e584a3770875
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073499"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="2e7a1-103">Skapa och redigera AutoPilot-profiler</span><span class="sxs-lookup"><span data-stu-id="2e7a1-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="2e7a1-104">Skapa en profil</span><span class="sxs-lookup"><span data-stu-id="2e7a1-104">Create a profile</span></span>

<span data-ttu-id="2e7a1-105">En profil gäller för en enhet eller en grupp enheter.</span><span class="sxs-lookup"><span data-stu-id="2e7a1-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="2e7a1-106">Välj **enheter** i Microsoft 365 Business Admin center, \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="2e7a1-106">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="2e7a1-107">Välj fliken **profiler** på sidan **AutoPilot** \> **Skapa profil**.</span><span class="sxs-lookup"><span data-stu-id="2e7a1-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="2e7a1-108">På sidan **Skapa profil** anger du ett namn för profilen som kan hjälpa dig att identifiera den, till exempel Marknadsföring. Aktivera inställningen som du vill använda (mer information finns i [Om AutoPilot-profilinställningar](autopilot-profile-settings.md)) och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2e7a1-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing, turn on the setting you want (see [About AutoPilot Profile settings](autopilot-profile-settings.md) for more information), and choose **Save**.</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="2e7a1-110">Använda profil på en enhet</span><span class="sxs-lookup"><span data-stu-id="2e7a1-110">Apply profile to a device</span></span>

<span data-ttu-id="2e7a1-p101">När du har skapat en profil kan du använda den på en enhet eller en grupp av enheter. Du kan välja en befintlig profil i [guiden med stegvisa anvisningar](add-autopilot-devices-and-profile.md) och använda den på nya enheter, eller så kan du ersätta en befintlig profil för en enhet eller en grupp av enheter.</span><span class="sxs-lookup"><span data-stu-id="2e7a1-p101">After you create a profile you can apply it to a device or a group of devices. You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md), you can apply it to new devices, or you can replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="2e7a1-113">På sidan för att **förbereda Windows** väljer du fliken **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="2e7a1-113">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="2e7a1-114">Klicka på kryssrutan bredvid en enhets namn. På panelen **Enhet** väljer du sedan en profil i listrutan **Tilldelad profil** \> **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2e7a1-114">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="2e7a1-116">Redigera eller ta bort en profil</span><span class="sxs-lookup"><span data-stu-id="2e7a1-116">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="2e7a1-p102">När du har tilldelat en profil till en enhet kan du uppdatera den, även om du redan har gett enheten till en användare. När enheten ansluts till internet laddar den ned den senaste versionen av profilen under installationen. Om användaren återställer enheten till de förvalda inställningarna hämtar enheten på nytt de senaste uppdateringarna av profilen.</span><span class="sxs-lookup"><span data-stu-id="2e7a1-p102">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="2e7a1-120">Redigera en profil</span><span class="sxs-lookup"><span data-stu-id="2e7a1-120">Edit a profile</span></span>

1. <span data-ttu-id="2e7a1-121">På sidan för att **förbereda Windows** väljer du fliken **Profiler**.</span><span class="sxs-lookup"><span data-stu-id="2e7a1-121">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="2e7a1-122">Klicka på kryssrutan bredvid enhetens namn. På panelen **Profil** uppdaterar du någon av de tillgängliga inställningarna \> **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2e7a1-122">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="2e7a1-123">Om du gör detta innan någon användare ansluter enheten till internet används profilen för installationen.</span><span class="sxs-lookup"><span data-stu-id="2e7a1-123">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="2e7a1-124">Radera en profil</span><span class="sxs-lookup"><span data-stu-id="2e7a1-124">Delete a profile</span></span>

1. <span data-ttu-id="2e7a1-125">På sidan för att **förbereda Windows** väljer du fliken **Profiler**.</span><span class="sxs-lookup"><span data-stu-id="2e7a1-125">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="2e7a1-126">Klicka på kryssrutan bredvid enhetens namn. På panelen **Profil** klickar du på **Ta bort profil** \> **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2e7a1-126">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="2e7a1-127">När du raderar en profil tas den bort från en enhet eller en grupp av enheter som den var tilldelad till.</span><span class="sxs-lookup"><span data-stu-id="2e7a1-127">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="2e7a1-128">Ta bort en profil</span><span class="sxs-lookup"><span data-stu-id="2e7a1-128">Remove a profile</span></span>

1. <span data-ttu-id="2e7a1-129">På sidan för att **förbereda Windows** väljer du fliken **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="2e7a1-129">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="2e7a1-130">Klicka på kryssrutan bredvid en enhets namn. På panelen **Enhet** väljer du sedan **Ingen** i listrutan **Tilldelad profil** \> **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2e7a1-130">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span></span>
    
