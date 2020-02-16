---
title: Skapa och redigera AutoPilot-profiler
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
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Lär dig att skapa, redigera, ta bort eller ta bort Profiler för Autopilot.
ms.openlocfilehash: 28f5b679d58711d11d9af26dffb7022024b72c79
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065922"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="21e4f-103">Skapa och redigera AutoPilot-profiler</span><span class="sxs-lookup"><span data-stu-id="21e4f-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="21e4f-104">Skapa en profil</span><span class="sxs-lookup"><span data-stu-id="21e4f-104">Create a profile</span></span>

<span data-ttu-id="21e4f-105">En profil gäller för en enhet eller en grupp enheter.</span><span class="sxs-lookup"><span data-stu-id="21e4f-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="21e4f-106">Välj **Autopilot**för **enheter** \> i Administrationscentret för Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="21e4f-106">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="21e4f-107">På sidan **AutoPilot** väljer \*\*\*\* du \> fliken **Profiler Skapa profil**.</span><span class="sxs-lookup"><span data-stu-id="21e4f-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="21e4f-108">Ange ett namn på profilen som hjälper dig att identifiera den på **sidan Skapa profil.**</span><span class="sxs-lookup"><span data-stu-id="21e4f-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing.</span></span> <span data-ttu-id="21e4f-109">Aktivera den inställning du vill använda och välj sedan **Spara**.</span><span class="sxs-lookup"><span data-stu-id="21e4f-109">Turn on the setting you want, and then choose **Save**.</span></span> <span data-ttu-id="21e4f-110">Mer information om AutoPilot-profilinställningar finns [i Om autopilotprofilinställningar](autopilot-profile-settings.md).</span><span class="sxs-lookup"><span data-stu-id="21e4f-110">For more information about AutoPilot profile settings, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="21e4f-112">Använda profil på en enhet</span><span class="sxs-lookup"><span data-stu-id="21e4f-112">Apply profile to a device</span></span>

<span data-ttu-id="21e4f-113">När du har skapat en profil kan du använda den på en enhet eller en grupp enheter.</span><span class="sxs-lookup"><span data-stu-id="21e4f-113">After you create a profile, you can apply it to a device or a group of devices.</span></span> <span data-ttu-id="21e4f-114">Du kan välja en befintlig profil i [steg-för-steg-guiden](add-autopilot-devices-and-profile.md) och använda den på nya enheter eller ersätta en befintlig profil för en enhet eller grupp av enheter.</span><span class="sxs-lookup"><span data-stu-id="21e4f-114">You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md) and apply it to new devices, or replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="21e4f-115">På sidan för att **förbereda Windows** väljer du fliken **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="21e4f-115">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="21e4f-116">Markera kryssrutan bredvid ett enhetsnamn och \*\*\*\* välj en profil i listrutan \> **Tilldelad profil** **Spara**.</span><span class="sxs-lookup"><span data-stu-id="21e4f-116">Select the check box next to a device name, and in the **Device** panel, choose a profile from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="21e4f-118">Redigera eller ta bort en profil</span><span class="sxs-lookup"><span data-stu-id="21e4f-118">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="21e4f-p103">När du har tilldelat en profil till en enhet kan du uppdatera den, även om du redan har gett enheten till en användare. När enheten ansluts till internet laddar den ned den senaste versionen av profilen under installationen. Om användaren återställer enheten till de förvalda inställningarna hämtar enheten på nytt de senaste uppdateringarna av profilen.</span><span class="sxs-lookup"><span data-stu-id="21e4f-p103">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="21e4f-122">Redigera en profil</span><span class="sxs-lookup"><span data-stu-id="21e4f-122">Edit a profile</span></span>

1. <span data-ttu-id="21e4f-123">På sidan för att **förbereda Windows** väljer du fliken **Profiler**.</span><span class="sxs-lookup"><span data-stu-id="21e4f-123">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="21e4f-124">Markera kryssrutan bredvid ett enhetsnamn och uppdatera alla tillgängliga inställningar \> **Spara**på **profilpanelen.**</span><span class="sxs-lookup"><span data-stu-id="21e4f-124">Select the check box next to a device name, and in the **Profile** panel, update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="21e4f-125">Om du gör detta innan någon användare ansluter enheten till internet används profilen för installationen.</span><span class="sxs-lookup"><span data-stu-id="21e4f-125">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="21e4f-126">Radera en profil</span><span class="sxs-lookup"><span data-stu-id="21e4f-126">Delete a profile</span></span>

1. <span data-ttu-id="21e4f-127">På sidan för att **förbereda Windows** väljer du fliken **Profiler**.</span><span class="sxs-lookup"><span data-stu-id="21e4f-127">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="21e4f-128">Markera kryssrutan bredvid ett enhetsnamn och välj **Ta bort profilspara** \> \*\*\*\* på **profilpanelen.**</span><span class="sxs-lookup"><span data-stu-id="21e4f-128">Select the check box next to a device name, and in the **Profile** panel, select **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="21e4f-129">När du raderar en profil tas den bort från en enhet eller en grupp av enheter som den var tilldelad till.</span><span class="sxs-lookup"><span data-stu-id="21e4f-129">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="21e4f-130">Ta bort en profil</span><span class="sxs-lookup"><span data-stu-id="21e4f-130">Remove a profile</span></span>

1. <span data-ttu-id="21e4f-131">På sidan för att **förbereda Windows** väljer du fliken **Enheter**.</span><span class="sxs-lookup"><span data-stu-id="21e4f-131">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="21e4f-132">Markera kryssrutan bredvid ett enhetsnamn och \*\*\*\* välj **Ingen** i listrutan \> **Tilldelad profil** **Spara**.</span><span class="sxs-lookup"><span data-stu-id="21e4f-132">Select the check box next to a device name, and in the **Device** panel, choose **None** from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
