---
title: Använda stegvisa anvisningar för att lägga till AutoPilot-enheter och -profiler
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Lär dig använda Windows AutoPilot för att konfigurera nya Windows 10-enheter för ditt företag.
ms.openlocfilehash: 56225424125e9eed9f46867837c564aa5d1c4adc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982169"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="52e52-103">Använda stegvisa anvisningar för att lägga till AutoPilot-enheter och -profiler</span><span class="sxs-lookup"><span data-stu-id="52e52-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="52e52-104">Du kan använda Windows AutoPilot för att konfigurera nya Windows 10-enheter för företaget så att de är redo för produktiv användning när dina anställda får dem.</span><span class="sxs-lookup"><span data-stu-id="52e52-104">You can use Windows AutoPilot to set up new Windows 10 devices for your business so they are ready for productive use as soon as you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="52e52-105">Enhetskrav</span><span class="sxs-lookup"><span data-stu-id="52e52-105">Device requirements</span></span>

<span data-ttu-id="52e52-106">Enheter måste uppfylla följande krav:</span><span class="sxs-lookup"><span data-stu-id="52e52-106">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="52e52-107">Windows 10, version 1703 eller senare.</span><span class="sxs-lookup"><span data-stu-id="52e52-107">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="52e52-108">Nya enheter som inte har genomgått Windows välkomstprogram.</span><span class="sxs-lookup"><span data-stu-id="52e52-108">New devices that have not been through Windows out-of-box experience.</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="52e52-109">Använda installationsguiden för att skapa enheter och profiler</span><span class="sxs-lookup"><span data-stu-id="52e52-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="52e52-110">Om du inte redan har skapat enhetsgrupper eller profiler kommer du enklast igång genom att använda dig av en guide med stegvisa anvisningar, men du kan även [lägga till enheter](create-and-edit-autopilot-devices.md) och [tilldela profiler](create-and-edit-autopilot-profiles.md) till dem utan att använda guiden.</span><span class="sxs-lookup"><span data-stu-id="52e52-110">If you have no device groups or profiles created yet, the best way to get started is by using the step-by-step guide, but you can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="52e52-111">I administrationscentret för Microsoft 365 Business letar du upp kortet **Enhetsåtgärder** och väljer **Distribuera Windows med AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="52e52-111">In the Microsoft 365 Business admin center, locate the **Device actions** card, and choose **Deploy Windows with Autopilot**.</span></span>
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="52e52-113">På sidan **Förbered Windows** klickar eller trycker du på **Start guide** (Starta guiden).</span><span class="sxs-lookup"><span data-stu-id="52e52-113">On the **Prepare Windows** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="52e52-p101">På sidan för **uppladdning av CSV-fil med lista över enheter** bläddrar du till en plats där du har den förberedda CSV-filen. Klicka sedan på **Öppna** \> **Nästa**. Filen bör ha tre rubriker:</span><span class="sxs-lookup"><span data-stu-id="52e52-p101">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**. The file should have three headers:</span></span>
    
  - <span data-ttu-id="52e52-117">Kolumn A: Enhetsserienummer</span><span class="sxs-lookup"><span data-stu-id="52e52-117">Column A: Device Serial Number</span></span>
    
  - <span data-ttu-id="52e52-118">Kolumn B: Produkt-ID för Windows</span><span class="sxs-lookup"><span data-stu-id="52e52-118">Column B: Windows Product ID</span></span>
    
  - <span data-ttu-id="52e52-119">Kolumn C: Maskinvaruhash</span><span class="sxs-lookup"><span data-stu-id="52e52-119">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="52e52-120">Du kan få den här informationen från din maskinvaruleverantör eller använda [PowerShell-skriptet Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) som skapar en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="52e52-120">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 
    
    <span data-ttu-id="52e52-p102">Mer information finns i [CSV-filen med enhetslistan](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). Du kan också ladda ned en exempelfil på sidan för **uppladdning av CSV-fil med lista över enheter**.</span><span class="sxs-lookup"><span data-stu-id="52e52-p102">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="52e52-p103">På sidan **Tilldela en profil** kan du välja en befintlig profil eller skapa en ny. Om du inte redan har en uppmanas du att skapa en ny.</span><span class="sxs-lookup"><span data-stu-id="52e52-p103">On the **Assign a profile** page, you can either pick an existing profile, or create a new one. If you don't have one yet, you will be prompted to create a new one.</span></span> 
    
    <span data-ttu-id="52e52-125">En proﬁl är en samling inställningar som kan tillämpas på en enskild enhet eller en grupp av enheter.</span><span class="sxs-lookup"><span data-stu-id="52e52-125">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="52e52-p104">Standardfunktionerna är obligatoriska och ställs in automatiskt. Standardfunktionerna är följande:</span><span class="sxs-lookup"><span data-stu-id="52e52-p104">The default features are required and will be set automatically. The default features are:</span></span>
    
  - <span data-ttu-id="52e52-128">Cortana-, OneDrive- och OEM-registrering hoppas över.</span><span class="sxs-lookup"><span data-stu-id="52e52-128">Cortana, OneDrive and OEM registration is skipped.</span></span>
    
  - <span data-ttu-id="52e52-129">Skapa inloggning med företagets varumärke.</span><span class="sxs-lookup"><span data-stu-id="52e52-129">Create sign-in experience with your company brand.</span></span>
    
  - <span data-ttu-id="52e52-130">Enheterna ansluts till Azure Active Directory-konton och registreras automatiskt för att hanteras av Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="52e52-130">Your devices are going to be connected to Azure Active Directory accounts and automatically enrolled to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="52e52-131">Mer information finns i</span><span class="sxs-lookup"><span data-stu-id="52e52-131">For more information, see</span></span>
    
    <span data-ttu-id="52e52-132">[Om AutoPilot-profilinställningar](autopilot-profile-settings.md) .</span><span class="sxs-lookup"><span data-stu-id="52e52-132">[About AutoPilot Profile settings](autopilot-profile-settings.md) .</span></span> 
    
5. <span data-ttu-id="52e52-133">Andra inställningar som används **Skip privacy settings** (Hoppa över sekretessinställningar) och **Don't allow user to become the local admin** (Tillåt inte användare att bli lokal administratör). Båda är inställda på **Av** som standard.</span><span class="sxs-lookup"><span data-stu-id="52e52-133">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="52e52-134">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="52e52-134">Choose **Next**.</span></span>
    
6. <span data-ttu-id="52e52-p105">Sidan **Du är klar** visar att profilen du skapade (eller valde) kommer att användas för enhetsgruppen du skapade genom att ladda upp listan med enheter. De här inställningarna börjar gälla nästa gång enhetsanvändarna loggar in. Välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="52e52-p105">**You're done** page indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices. These settings will be in effect when the device users sign in next. Choose **Close**.</span></span>
    