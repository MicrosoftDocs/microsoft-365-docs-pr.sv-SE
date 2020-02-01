---
title: Använda stegvisa anvisningar för att lägga till AutoPilot-enheter och -profiler
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Lär dig hur du använder Windows AutoPilot för att konfigurera nya Windows 10-enheter för ditt företag.
ms.openlocfilehash: 1fd0abb76d16b79dd11ef27b6b27a87894d89ef9
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593282"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="0ba02-103">Använda stegvisa anvisningar för att lägga till AutoPilot-enheter och -profiler</span><span class="sxs-lookup"><span data-stu-id="0ba02-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="0ba02-104">Du kan använda Windows AutoPilot för att konfigurera **nya** Windows 10-enheter för ditt företag så att de är redo att användas när du ger dem till dina anställda.</span><span class="sxs-lookup"><span data-stu-id="0ba02-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="0ba02-105">Enhetskrav</span><span class="sxs-lookup"><span data-stu-id="0ba02-105">Device requirements</span></span>

<span data-ttu-id="0ba02-106">Anordningar måste uppfylla dessa krav:</span><span class="sxs-lookup"><span data-stu-id="0ba02-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="0ba02-107">Windows 10, version 1703 eller senare</span><span class="sxs-lookup"><span data-stu-id="0ba02-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="0ba02-108">Nya enheter som inte har gått igenom Windows out-of-box-upplevelse</span><span class="sxs-lookup"><span data-stu-id="0ba02-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="0ba02-109">Använda installationsguiden för att skapa enheter och profiler</span><span class="sxs-lookup"><span data-stu-id="0ba02-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="0ba02-110">[![Etikett som gör att du kan se att administrationscentret ändras och mer information finns på aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="0ba02-110">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="0ba02-111">Om du inte har skapat enhetsgrupper eller profiler ännu är det bästa sättet att komma igång genom att använda steg-för-steg-guiden.</span><span class="sxs-lookup"><span data-stu-id="0ba02-111">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="0ba02-112">Du kan också [lägga till enheter](create-and-edit-autopilot-devices.md) och tilldela [profiler](create-and-edit-autopilot-profiles.md) till dem utan att använda guiden.</span><span class="sxs-lookup"><span data-stu-id="0ba02-112">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="0ba02-113">Gå till admin <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>center på .</span><span class="sxs-lookup"><span data-stu-id="0ba02-113">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="0ba02-114">Välj **Devices** \> **AutoPilot**i det vänstra navigeringsfönstret .</span><span class="sxs-lookup"><span data-stu-id="0ba02-114">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![Välj enheter i administrationscentret och sedan AutoPilot.](media/AutoPilot.png)
  
2. <span data-ttu-id="0ba02-116">Klicka eller tryck på **Startguide**på sidan **AutoPilot** .</span><span class="sxs-lookup"><span data-stu-id="0ba02-116">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="0ba02-118">Bläddra till en plats där du har förberett på **sidan Ladda upp CSV med listan över enheter.** CSV-fil och **öppna** \> **nästa**.</span><span class="sxs-lookup"><span data-stu-id="0ba02-118">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="0ba02-119">Filen måste ha tre rubriker:</span><span class="sxs-lookup"><span data-stu-id="0ba02-119">The file must have three headers:</span></span>
    
    - <span data-ttu-id="0ba02-120">Kolumn A: Enhetsserienummer</span><span class="sxs-lookup"><span data-stu-id="0ba02-120">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="0ba02-121">Kolumn B: Produkt-ID för Windows</span><span class="sxs-lookup"><span data-stu-id="0ba02-121">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="0ba02-122">Kolumn C: Maskinvaruhash</span><span class="sxs-lookup"><span data-stu-id="0ba02-122">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="0ba02-123">Du kan hämta den här informationen från maskinvaruleverantören eller använda [PowerShell-skriptet Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) för att generera en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="0ba02-123">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="0ba02-p103">Mer information finns i [CSV-filen med enhetslistan](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). Du kan också ladda ned en exempelfil på sidan för **uppladdning av CSV-fil med lista över enheter**.</span><span class="sxs-lookup"><span data-stu-id="0ba02-p103">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="0ba02-126">På sidan **Tilldela en profil** kan du antingen välja en befintlig profil eller skapa en ny.</span><span class="sxs-lookup"><span data-stu-id="0ba02-126">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="0ba02-127">Om du inte har en ännu uppmanas du att skapa en.</span><span class="sxs-lookup"><span data-stu-id="0ba02-127">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="0ba02-128">En proﬁl är en samling inställningar som kan tillämpas på en enskild enhet eller en grupp av enheter.</span><span class="sxs-lookup"><span data-stu-id="0ba02-128">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="0ba02-129">Standardfunktionerna krävs och ställs in automatiskt.</span><span class="sxs-lookup"><span data-stu-id="0ba02-129">The default features are required and are set automatically.</span></span> <span data-ttu-id="0ba02-130">Standardfunktionerna är följande:</span><span class="sxs-lookup"><span data-stu-id="0ba02-130">The default features are:</span></span>
    
    - <span data-ttu-id="0ba02-131">Hoppa över Cortana-, OneDrive- och OEM-registrering.</span><span class="sxs-lookup"><span data-stu-id="0ba02-131">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="0ba02-132">Skapa inloggning med företagets varumärke.</span><span class="sxs-lookup"><span data-stu-id="0ba02-132">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="0ba02-133">Anslut dina enheter till Azure Active Directory-konton och registrera dem automatiskt för att hanteras av Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="0ba02-133">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="0ba02-134">Mer information finns i [Om Inställningar för AutoPilot-profil](autopilot-profile-settings.md).</span><span class="sxs-lookup"><span data-stu-id="0ba02-134">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="0ba02-135">Andra inställningar som används **Skip privacy settings** (Hoppa över sekretessinställningar) och **Don't allow user to become the local admin** (Tillåt inte användare att bli lokal administratör). Båda är inställda på **Av** som standard.</span><span class="sxs-lookup"><span data-stu-id="0ba02-135">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="0ba02-136">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="0ba02-136">Choose **Next**.</span></span>
    
6. <span data-ttu-id="0ba02-137">**Du är klar** anger att profilen du skapade (eller valde) kommer att tillämpas på den enhetsgrupp som du skapade genom att ladda upp listan över enheter.</span><span class="sxs-lookup"><span data-stu-id="0ba02-137">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="0ba02-138">Inställningarna gäller när enhetsanvändarna loggar in nästa.</span><span class="sxs-lookup"><span data-stu-id="0ba02-138">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="0ba02-139">Välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="0ba02-139">Choose **Close**.</span></span>
    