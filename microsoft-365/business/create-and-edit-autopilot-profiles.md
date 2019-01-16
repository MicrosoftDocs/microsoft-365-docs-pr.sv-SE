---
title: Skapa och redigera AutoPilot-profiler
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
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 'Lär dig att skapa, redigera, ta bort eller ta bort AutoPilot profiler. '
ms.openlocfilehash: 4658a27e5f2c64a52f8a7d08b3fc13df5e239dc3
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26983139"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="54d17-103">Skapa och redigera AutoPilot-profiler</span><span class="sxs-lookup"><span data-stu-id="54d17-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="54d17-104">Skapa en profil</span><span class="sxs-lookup"><span data-stu-id="54d17-104">Create a profile</span></span>

<span data-ttu-id="54d17-105">En profil gäller för en enhet eller en grupp enheter.</span><span class="sxs-lookup"><span data-stu-id="54d17-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="54d17-106">I administrationscentret för Microsoft 365 Business väljer du **Distribuera Windows med AutoPilot** på kortet **Enhetsåtgärder**</span><span class="sxs-lookup"><span data-stu-id="54d17-106">In the Microsoft 365 Business Admin center, choose **Deploy Windows with AutoPilot** on the **Device actions** card.</span></span> 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="54d17-108">På sidan för att **förbereda Windows** väljer du fliken **Profiler** \> **Skapa profil**.</span><span class="sxs-lookup"><span data-stu-id="54d17-108">On the **Prepare Windows** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="54d17-109">På sidan **Skapa profil** anger du ett namn för profilen som kan hjälpa dig att identifiera den, till exempel Marknadsföring. Aktivera inställningen som du vill använda (mer information finns i [Om AutoPilot-profilinställningar](autopilot-profile-settings.md)) och välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="54d17-109">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing, turn on the setting you want (see [About AutoPilot Profile settings](autopilot-profile-settings.md) for more information), and choose **Save**.</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="54d17-111">Använda profil på en enhet</span><span class="sxs-lookup"><span data-stu-id="54d17-111">Apply profile to a device</span></span>

<span data-ttu-id="54d17-p101">När du har skapat en profil kan du använda den på en enhet eller en grupp av enheter. Du kan välja en befintlig profil i [guiden med stegvisa anvisningar](add-autopilot-devices-and-profile.md) och använda den på nya enheter, eller så kan du ersätta en befintlig profil för en enhet eller en grupp av enheter.</span><span class="sxs-lookup"><span data-stu-id="54d17-p101">After you create a profile you can apply it to a device or a group of devices. You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md), you can apply it to new devices, or you can replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="54d17-114">På sidan för att **förbereda Windows** väljer du fliken **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="54d17-114">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="54d17-115">Klicka på kryssrutan bredvid en enhets namn. På panelen **Enhet** väljer du sedan en profil i listrutan **Tilldelad profil** \> **Spara**.</span><span class="sxs-lookup"><span data-stu-id="54d17-115">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="54d17-117">Redigera eller ta bort en profil</span><span class="sxs-lookup"><span data-stu-id="54d17-117">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="54d17-p102">När du har tilldelat en profil till en enhet kan du uppdatera den, även om du redan har gett enheten till en användare. När enheten ansluts till internet laddar den ned den senaste versionen av profilen under installationen. Om användaren återställer enheten till de förvalda inställningarna hämtar enheten på nytt de senaste uppdateringarna av profilen.</span><span class="sxs-lookup"><span data-stu-id="54d17-p102">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="54d17-121">Redigera en profil</span><span class="sxs-lookup"><span data-stu-id="54d17-121">Edit a profile</span></span>

1. <span data-ttu-id="54d17-122">På sidan för att **förbereda Windows** väljer du fliken **Profiler**.</span><span class="sxs-lookup"><span data-stu-id="54d17-122">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="54d17-123">Klicka på kryssrutan bredvid enhetens namn. På panelen **Profil** uppdaterar du någon av de tillgängliga inställningarna \> **Spara**.</span><span class="sxs-lookup"><span data-stu-id="54d17-123">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="54d17-124">Om du gör detta innan någon användare ansluter enheten till internet används profilen för installationen.</span><span class="sxs-lookup"><span data-stu-id="54d17-124">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="54d17-125">Radera en profil</span><span class="sxs-lookup"><span data-stu-id="54d17-125">Delete a profile</span></span>

1. <span data-ttu-id="54d17-126">På sidan för att **förbereda Windows** väljer du fliken **Profiler**.</span><span class="sxs-lookup"><span data-stu-id="54d17-126">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="54d17-127">Klicka på kryssrutan bredvid enhetens namn. På panelen **Profil** klickar du på **Ta bort profil** \> **Spara**.</span><span class="sxs-lookup"><span data-stu-id="54d17-127">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="54d17-128">När du raderar en profil tas den bort från en enhet eller en grupp av enheter som den var tilldelad till.</span><span class="sxs-lookup"><span data-stu-id="54d17-128">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="54d17-129">Ta bort en profil</span><span class="sxs-lookup"><span data-stu-id="54d17-129">Remove a profile</span></span>

1. <span data-ttu-id="54d17-130">På sidan för att **förbereda Windows** väljer du fliken **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="54d17-130">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="54d17-131">Klicka på kryssrutan bredvid en enhets namn. På panelen **Enhet** väljer du sedan **Ingen** i listrutan **Tilldelad profil** \> **Spara**.</span><span class="sxs-lookup"><span data-stu-id="54d17-131">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span></span>
    
