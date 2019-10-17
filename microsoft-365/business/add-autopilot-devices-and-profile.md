---
title: Använda stegvisa anvisningar för att lägga till AutoPilot-enheter och -profiler
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
ms.openlocfilehash: d028ea3e902965d55c445dc3b3a02aa315201b25
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37574797"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="cbc81-103">Använda stegvisa anvisningar för att lägga till AutoPilot-enheter och -profiler</span><span class="sxs-lookup"><span data-stu-id="cbc81-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="cbc81-104">Du kan använda Windows AutoPilot för att konfigurera **nya** Windows 10-enheter för ditt företag så att de är klara för produktiv användning så snart du ger dem till dina anställda.</span><span class="sxs-lookup"><span data-stu-id="cbc81-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they are ready for productive use as soon as you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="cbc81-105">Enhetskrav</span><span class="sxs-lookup"><span data-stu-id="cbc81-105">Device requirements</span></span>

<span data-ttu-id="cbc81-106">Enheter måste uppfylla följande krav:</span><span class="sxs-lookup"><span data-stu-id="cbc81-106">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="cbc81-107">Windows 10, version 1703 eller senare.</span><span class="sxs-lookup"><span data-stu-id="cbc81-107">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="cbc81-108">Nya enheter som inte har genomgått Windows välkomstprogram.</span><span class="sxs-lookup"><span data-stu-id="cbc81-108">New devices that have not been through Windows out-of-box experience.</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="cbc81-109">Använda installationsguiden för att skapa enheter och profiler</span><span class="sxs-lookup"><span data-stu-id="cbc81-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="cbc81-110">[![Etiketten så att du vet att Admin Center förändras och du kan hitta mer information på aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="cbc81-110">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="cbc81-111">Om du inte redan har skapat enhetsgrupper eller profiler kommer du enklast igång genom att använda dig av en guide med stegvisa anvisningar, men du kan även [lägga till enheter](create-and-edit-autopilot-devices.md) och [tilldela profiler](create-and-edit-autopilot-profiles.md) till dem utan att använda guiden.</span><span class="sxs-lookup"><span data-stu-id="cbc81-111">If you have no device groups or profiles created yet, the best way to get started is by using the step-by-step guide, but you can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="cbc81-112">Gå till administratörscenter på <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="cbc81-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="cbc81-113">På vänster nav väljer du **enheter** \> **autopilot**.</span><span class="sxs-lookup"><span data-stu-id="cbc81-113">On the left nav choose **Devices** \> **AutoPilot**.</span></span>

    ![I administratörscenter väljer du enheter och sedan AutoPilot.](media/AutoPilot.png)
  
2. <span data-ttu-id="cbc81-115">På **Autopilotsidan** klickar eller knackar du på **Start Guide**.</span><span class="sxs-lookup"><span data-stu-id="cbc81-115">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="cbc81-p101">På sidan för **uppladdning av CSV-fil med lista över enheter** bläddrar du till en plats där du har den förberedda CSV-filen. Klicka sedan på **Öppna** \> **Nästa**. Filen bör ha tre rubriker:</span><span class="sxs-lookup"><span data-stu-id="cbc81-p101">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**. The file should have three headers:</span></span>
    
  - <span data-ttu-id="cbc81-119">Kolumn A: Enhetsserienummer</span><span class="sxs-lookup"><span data-stu-id="cbc81-119">Column A: Device Serial Number</span></span>
    
  - <span data-ttu-id="cbc81-120">Kolumn B: Produkt-ID för Windows</span><span class="sxs-lookup"><span data-stu-id="cbc81-120">Column B: Windows Product ID</span></span>
    
  - <span data-ttu-id="cbc81-121">Kolumn C: Maskinvaruhash</span><span class="sxs-lookup"><span data-stu-id="cbc81-121">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="cbc81-122">Du kan få den här informationen från din maskinvaruleverantör eller använda [PowerShell-skriptet Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) som skapar en CSV-fil.</span><span class="sxs-lookup"><span data-stu-id="cbc81-122">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 
    
    <span data-ttu-id="cbc81-p102">Mer information finns i [CSV-filen med enhetslistan](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). Du kan också ladda ned en exempelfil på sidan för **uppladdning av CSV-fil med lista över enheter**.</span><span class="sxs-lookup"><span data-stu-id="cbc81-p102">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="cbc81-p103">På sidan **Tilldela en profil** kan du välja en befintlig profil eller skapa en ny. Om du inte redan har en uppmanas du att skapa en ny.</span><span class="sxs-lookup"><span data-stu-id="cbc81-p103">On the **Assign a profile** page, you can either pick an existing profile, or create a new one. If you don't have one yet, you will be prompted to create a new one.</span></span> 
    
    <span data-ttu-id="cbc81-127">En proﬁl är en samling inställningar som kan tillämpas på en enskild enhet eller en grupp av enheter.</span><span class="sxs-lookup"><span data-stu-id="cbc81-127">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="cbc81-p104">Standardfunktionerna är obligatoriska och ställs in automatiskt. Standardfunktionerna är följande:</span><span class="sxs-lookup"><span data-stu-id="cbc81-p104">The default features are required and will be set automatically. The default features are:</span></span>
    
  - <span data-ttu-id="cbc81-130">Cortana-, OneDrive- och OEM-registrering hoppas över.</span><span class="sxs-lookup"><span data-stu-id="cbc81-130">Cortana, OneDrive and OEM registration is skipped.</span></span>
    
  - <span data-ttu-id="cbc81-131">Skapa inloggning med företagets varumärke.</span><span class="sxs-lookup"><span data-stu-id="cbc81-131">Create sign-in experience with your company brand.</span></span>
    
  - <span data-ttu-id="cbc81-132">Enheterna ansluts till Azure Active Directory-konton och registreras automatiskt för att hanteras av Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="cbc81-132">Your devices are going to be connected to Azure Active Directory accounts and automatically enrolled to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="cbc81-133">Mer information finns i</span><span class="sxs-lookup"><span data-stu-id="cbc81-133">For more information, see</span></span>
    
    <span data-ttu-id="cbc81-134">[Om AutoPilot-profilinställningar](autopilot-profile-settings.md) .</span><span class="sxs-lookup"><span data-stu-id="cbc81-134">[About AutoPilot Profile settings](autopilot-profile-settings.md) .</span></span> 
    
5. <span data-ttu-id="cbc81-135">Andra inställningar som används **Skip privacy settings** (Hoppa över sekretessinställningar) och **Don't allow user to become the local admin** (Tillåt inte användare att bli lokal administratör). Båda är inställda på **Av** som standard.</span><span class="sxs-lookup"><span data-stu-id="cbc81-135">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="cbc81-136">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="cbc81-136">Choose **Next**.</span></span>
    
6. <span data-ttu-id="cbc81-p105">Sidan **Du är klar** visar att profilen du skapade (eller valde) kommer att användas för enhetsgruppen du skapade genom att ladda upp listan med enheter. De här inställningarna börjar gälla nästa gång enhetsanvändarna loggar in. Välj **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="cbc81-p105">**You're done** page indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices. These settings will be in effect when the device users sign in next. Choose **Close**.</span></span>
    