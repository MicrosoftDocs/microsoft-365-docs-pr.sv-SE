---
title: Använda stegvisa anvisningar för att lägga till AutoPilot-enheter och -profiler
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Lär dig hur du använder Windows AutoPilot för att konfigurera nya Windows 10-enheter för företaget så att de är redo att användas av de anställda.
ms.openlocfilehash: e178e7df220e89605502d9ed400265bcd963e57e
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636115"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="7cddf-103">Använda stegvisa anvisningar för att lägga till AutoPilot-enheter och -profiler</span><span class="sxs-lookup"><span data-stu-id="7cddf-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="7cddf-104">Du kan använda Windows AutoPilot  för att konfigurera nya Windows 10-enheter för företaget så att de är redo att användas när du ger dem till dina anställda.</span><span class="sxs-lookup"><span data-stu-id="7cddf-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="7cddf-105">Enhetskrav</span><span class="sxs-lookup"><span data-stu-id="7cddf-105">Device requirements</span></span>

<span data-ttu-id="7cddf-106">Enheter måste uppfylla följande krav:</span><span class="sxs-lookup"><span data-stu-id="7cddf-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="7cddf-107">Windows 10, version 1703 eller senare</span><span class="sxs-lookup"><span data-stu-id="7cddf-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="7cddf-108">Nya enheter som inte har Windows utan att ha erfarenhet</span><span class="sxs-lookup"><span data-stu-id="7cddf-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="7cddf-109">Använda installationsguiden för att skapa enheter och profiler</span><span class="sxs-lookup"><span data-stu-id="7cddf-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="7cddf-110">Om du inte har skapat enhetsgrupper eller profiler ännu är det bästa sättet att komma igång genom att använda steg-för-steg-guiden.</span><span class="sxs-lookup"><span data-stu-id="7cddf-110">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="7cddf-111">Du kan också [lägga till enheter](create-and-edit-autopilot-devices.md) och tilldela [profiler](create-and-edit-autopilot-profiles.md) till dem utan att använda guiden.</span><span class="sxs-lookup"><span data-stu-id="7cddf-111">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="7cddf-112">Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="7cddf-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="7cddf-113">Välj Devices AutoPilot i det **vänstra** \> **navigeringsfönstret.**</span><span class="sxs-lookup"><span data-stu-id="7cddf-113">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![I administrationscentret väljer du enheter och sedan AutoPilot.](../media/AutoPilot.png)
  
2. <span data-ttu-id="7cddf-115">På sidan **AutoPilot klickar** eller trycker du på **Starta guiden**.</span><span class="sxs-lookup"><span data-stu-id="7cddf-115">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="7cddf-117">På sidan **Upload .csv med lista** över enheter bläddrar du till en plats där du har den förberedda .CSV och sedan **Öppna** \> **nästa.**</span><span class="sxs-lookup"><span data-stu-id="7cddf-117">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="7cddf-118">Filen måste ha tre rubriker:</span><span class="sxs-lookup"><span data-stu-id="7cddf-118">The file must have three headers:</span></span>
    
    - <span data-ttu-id="7cddf-119">Kolumn A: Enhetsserienummer</span><span class="sxs-lookup"><span data-stu-id="7cddf-119">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="7cddf-120">Kolumn B: Produkt-ID för Windows</span><span class="sxs-lookup"><span data-stu-id="7cddf-120">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="7cddf-121">Kolumn C: Maskinvaruhash</span><span class="sxs-lookup"><span data-stu-id="7cddf-121">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="7cddf-122">Du kan få den här informationen från din maskinvaruleverantör eller använda [PowerShell-skriptet Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) för att generera en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="7cddf-122">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="7cddf-p103">Mer information finns i [CSV-filen med enhetslistan](../admin/misc/device-list.md). Du kan också ladda ned en exempelfil på sidan för **uppladdning av CSV-fil med lista över enheter**.</span><span class="sxs-lookup"><span data-stu-id="7cddf-p103">For more information, see [Device list CSV-file](../admin/misc/device-list.md). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="7cddf-125">Det här skriptet använder WMI för att hämta egenskaper som behövs för att en kund ska registrera en enhet Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="7cddf-125">This script uses WMI to retrieve properties needed for a customer to register a device with Windows Autopilot.</span></span> <span data-ttu-id="7cddf-126">Observera att det är normalt att den resulterande CSV-filen inte samlar in ett PKID-värde (Windows Product ID) eftersom detta inte krävs för att registrera en enhet och PKID är NULL i CSV-utdata är helt ok.</span><span class="sxs-lookup"><span data-stu-id="7cddf-126">Note that it is normal for the resulting CSV file to not collect a Windows Product ID (PKID) value since this is not required to register a device and PKID being NULL in the output CSV is totally fine.</span></span> <span data-ttu-id="7cddf-127">Endast serienumret och maskinvaruhashen fylls i.</span><span class="sxs-lookup"><span data-stu-id="7cddf-127">Only the serial number and hardware hash will be populated.</span></span>
    
4. <span data-ttu-id="7cddf-128">På sidan **Tilldela en profil** kan du välja en befintlig profil eller skapa en ny.</span><span class="sxs-lookup"><span data-stu-id="7cddf-128">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="7cddf-129">Om du inte redan har en uppmanas du att skapa en.</span><span class="sxs-lookup"><span data-stu-id="7cddf-129">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="7cddf-130">En proﬁl är en samling inställningar som kan tillämpas på en enskild enhet eller en grupp av enheter.</span><span class="sxs-lookup"><span data-stu-id="7cddf-130">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="7cddf-131">Standardfunktionerna är obligatoriska och ställs in automatiskt.</span><span class="sxs-lookup"><span data-stu-id="7cddf-131">The default features are required and are set automatically.</span></span> <span data-ttu-id="7cddf-132">Standardfunktionerna är följande:</span><span class="sxs-lookup"><span data-stu-id="7cddf-132">The default features are:</span></span>
    
    - <span data-ttu-id="7cddf-133">Hoppa över Cortana OneDrive och OEM-registrering.</span><span class="sxs-lookup"><span data-stu-id="7cddf-133">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="7cddf-134">Skapa inloggning med företagets varumärke.</span><span class="sxs-lookup"><span data-stu-id="7cddf-134">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="7cddf-135">Anslut dina enheter för Azure Active Directory-konton och registrera dem automatiskt för att hanteras av Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="7cddf-135">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business Premium.</span></span>
    
    <span data-ttu-id="7cddf-136">Mer information finns i Om [AutoPilot-profilinställningar.](autopilot-profile-settings.md)</span><span class="sxs-lookup"><span data-stu-id="7cddf-136">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="7cddf-137">Andra inställningar som används **Skip privacy settings** (Hoppa över sekretessinställningar) och **Don't allow user to become the local admin** (Tillåt inte användare att bli lokal administratör). Båda är inställda på **Av** som standard.</span><span class="sxs-lookup"><span data-stu-id="7cddf-137">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="7cddf-138">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="7cddf-138">Choose **Next**.</span></span>
    
6. <span data-ttu-id="7cddf-139">**Du är klar anger** att profilen du skapade (eller valde) kommer att tillämpas på enhetsgruppen du skapade genom att ladda upp listan med enheter.</span><span class="sxs-lookup"><span data-stu-id="7cddf-139">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="7cddf-140">Inställningarna börjar gälla nästa gång enhetsanvändarna loggar in.</span><span class="sxs-lookup"><span data-stu-id="7cddf-140">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="7cddf-141">Välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="7cddf-141">Choose **Close**.</span></span>

## <a name="related-content"></a><span data-ttu-id="7cddf-142">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="7cddf-142">Related content</span></span>

<span data-ttu-id="7cddf-143">[Om AutoPilot-profilinställningar](autopilot-profile-settings.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="7cddf-143">[About AutoPilot Profile settings](autopilot-profile-settings.md) (article)</span></span>\
<span data-ttu-id="7cddf-144">[Alternativ för att skydda dina enheter och appdata](../admin/devices/choose-device-security.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="7cddf-144">[Options for protecting your devices and app data](../admin/devices/choose-device-security.md) (article)</span></span>
