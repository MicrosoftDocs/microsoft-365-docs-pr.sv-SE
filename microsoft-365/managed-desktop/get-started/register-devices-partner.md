---
title: Steg för partner för att registrera enheter
description: Hur partners kan registrera enheter så att de kan hanteras av Microsoft Managed Desktop
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 227786fdcf1e490be1e3ce74bbc1be1c5f21acfe
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689239"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="5609f-103">Steg för partner för att registrera enheter</span><span class="sxs-lookup"><span data-stu-id="5609f-103">Steps for Partners to register devices</span></span>


<span data-ttu-id="5609f-104">I den här artikeln beskrivs stegen som partner kan följa för att registrera enheter.</span><span class="sxs-lookup"><span data-stu-id="5609f-104">This article describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="5609f-105">Hur du registrerar enheter själv finns i Registrera [enheter i Microsoft Managed Desktop själv.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="5609f-105">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="5609f-106">Förbereda för registrering</span><span class="sxs-lookup"><span data-stu-id="5609f-106">Prepare for registration</span></span> 
<span data-ttu-id="5609f-107">Innan du kan slutföra registreringen för en kund måste du först upprätta en relation med kunden i [Partnercenter.](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="5609f-107">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="5609f-108">Mer information [om processen](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) finns i dokumentationen till medgivandet.</span><span class="sxs-lookup"><span data-stu-id="5609f-108">See the [consent documentation](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="5609f-109">Partner som är partner för CSP kan lägga till enheter åt en kund, så länge kunden har gett sitt samtycke.</span><span class="sxs-lookup"><span data-stu-id="5609f-109">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="5609f-110">Du kan också läsa mer om partnerrelationer och Autopilot-behörigheter i [Hjälp om Partnercenter.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="5609f-110">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="5609f-111">Den här dokumentationen gäller endast partner och OEM-maskiner.</span><span class="sxs-lookup"><span data-stu-id="5609f-111">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="5609f-112">Processen för självregistrering har dokumenterats i Registrera [enheter i Microsoft Managed Desktop själv.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="5609f-112">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="5609f-113">Registrera enheter med hjälp av Partnercenter</span><span class="sxs-lookup"><span data-stu-id="5609f-113">Register devices by using Partner Center</span></span>

<span data-ttu-id="5609f-114">När du har upprättat relationen med dina kunder kan du använda Partnercenter och lägga till enheter på Autopilot för alla kunder som du har en relation med genom att följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="5609f-114">Once you have established the relationship with your customers, you can use Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="5609f-115">Gå till [Partnercenter](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="5609f-115">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="5609f-116">Välj **Kunder** på Menyn Partnercenter och välj sedan den kund vars enheter du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="5609f-116">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="5609f-117">Välj Enheter på kundens **informationssida.**</span><span class="sxs-lookup"><span data-stu-id="5609f-117">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="5609f-118">Under **Använd profiler på** enheter väljer du Lägg till **enheter**.</span><span class="sxs-lookup"><span data-stu-id="5609f-118">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="5609f-119">Ange rätt grupptagg för den enhetsprofil du har valt (enligt följande  tabell) och välj sedan Bläddra för att ladda upp kundens lista (i CSV-filformat) till Partner Center.</span><span class="sxs-lookup"><span data-stu-id="5609f-119">Enter the appropriate Group Tag for the device profile you've selected (as shown in the following table) and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>

|[<span data-ttu-id="5609f-120">Enhetsprofil</span><span class="sxs-lookup"><span data-stu-id="5609f-120">Device profile</span></span>](../service-description/profiles.md)  |<span data-ttu-id="5609f-121">Grupptagg</span><span class="sxs-lookup"><span data-stu-id="5609f-121">Group Tag</span></span>  |
|---------|---------|
|<span data-ttu-id="5609f-122">Känsliga data</span><span class="sxs-lookup"><span data-stu-id="5609f-122">Sensitive data</span></span>     |<span data-ttu-id="5609f-123">**Microsoft365Managed \_ SensitiveData**</span><span class="sxs-lookup"><span data-stu-id="5609f-123">**Microsoft365Managed\_SensitiveData**</span></span>    |
|<span data-ttu-id="5609f-124">Power user</span><span class="sxs-lookup"><span data-stu-id="5609f-124">Power user</span></span>     | <span data-ttu-id="5609f-125">**Microsoft365Managed \_ PowerUser**</span><span class="sxs-lookup"><span data-stu-id="5609f-125">**Microsoft365Managed\_PowerUser**</span></span>          |
|<span data-ttu-id="5609f-126">Standard</span><span class="sxs-lookup"><span data-stu-id="5609f-126">Standard</span></span>     | <span data-ttu-id="5609f-127">**Microsoft365Managed \_ Standard**</span><span class="sxs-lookup"><span data-stu-id="5609f-127">**Microsoft365Managed\_Standard**</span></span>        |

> [!IMPORTANT]
> <span data-ttu-id="5609f-128">Gruppnamnet måste matcha de som anges i tabellen exakt, inklusive versaler och specialtecken.</span><span class="sxs-lookup"><span data-stu-id="5609f-128">The Group Name must match those listed in the table exactly, including capitalization and special characters.</span></span> <span data-ttu-id="5609f-129">Då kan de nyligen registrerade enheterna tilldelas med Microsoft Managed Desktop Autopilot-profilen.</span><span class="sxs-lookup"><span data-stu-id="5609f-129">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="5609f-130">Du borde ha fått den här CSV-filen med ditt enhetsköp.</span><span class="sxs-lookup"><span data-stu-id="5609f-130">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="5609f-131">Om du inte har fått någon CSV-fil kan du skapa en själv genom att följa stegen i Lägga till [enheter i Windows Autopilot.](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="5609f-131">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="5609f-132">Windows PowerShell-skriptet är inte samma som det som används för [Microsoft Managed Desktop Admin-portalen.](./register-devices-self.md#obtain-the-hardware-hash)</span><span class="sxs-lookup"><span data-stu-id="5609f-132">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md#obtain-the-hardware-hash).</span></span> <span data-ttu-id="5609f-133">Partners bör använda [Get-WindowsAutoPilotInfo för](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) att registrera enheter för Microsoft Managed Desktop-enheter i Partner Center.</span><span class="sxs-lookup"><span data-stu-id="5609f-133">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="5609f-134">Om du får ett felmeddelande när du försöker ladda upp CSV-filen kontrollerar du formatet på filen.</span><span class="sxs-lookup"><span data-stu-id="5609f-134">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="5609f-135">Se till att kolumnordningen stämmer överens med vad som beskrivs i Använda [Windows Autopilot-profiler](/partner-center/autopilot#add-devices-to-a-customers-account)på nya enheter för att anpassa en kunds användning.</span><span class="sxs-lookup"><span data-stu-id="5609f-135">Make sure the column order matches what is described in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span> <span data-ttu-id="5609f-136">Du kan också använda csv-exempelfilen från länken bredvid Lägg **till enheter för** att skapa en enhetslista.</span><span class="sxs-lookup"><span data-stu-id="5609f-136">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="5609f-137">Mer information om Autopilot i partnerscenarier finns i [Lägga till enheter till en kunds konto.](/partner-center/autopilot#add-devices-to-a-customers-account)</span><span class="sxs-lookup"><span data-stu-id="5609f-137">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="5609f-138">Registrera enheter med hjälp av OEM API</span><span class="sxs-lookup"><span data-stu-id="5609f-138">Register devices by using the OEM API</span></span>

<span data-ttu-id="5609f-139">Innan du slutför registreringen för en kund måste du först upprätta en relation med kunden.</span><span class="sxs-lookup"><span data-stu-id="5609f-139">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="5609f-140">Du bör ha en unik länk som du kan ge till dina respektive kunder.</span><span class="sxs-lookup"><span data-stu-id="5609f-140">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="5609f-141">Se [Så här upprättar du EN OEM-relation.](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)</span><span class="sxs-lookup"><span data-stu-id="5609f-141">See [How to establish OEM relationship](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="5609f-142">När du har upprättat relationen kan du börja registrera enheter för kunder med hjälp av rätt grupptagg för varje enhetsprofil som de har valt:</span><span class="sxs-lookup"><span data-stu-id="5609f-142">Once you've established the relationship, you can start registering devices for customers using the appropriate Group Tag for each device profile they've selected:</span></span>


|<span data-ttu-id="5609f-143">Enhetsprofil</span><span class="sxs-lookup"><span data-stu-id="5609f-143">Device profile</span></span>  |<span data-ttu-id="5609f-144">Grupptagg</span><span class="sxs-lookup"><span data-stu-id="5609f-144">Group Tag</span></span>  |
|---------|---------|
|<span data-ttu-id="5609f-145">Känsliga data</span><span class="sxs-lookup"><span data-stu-id="5609f-145">Sensitive data</span></span>     | <span data-ttu-id="5609f-146">**Microsoft365Managed \_ SensitiveData**</span><span class="sxs-lookup"><span data-stu-id="5609f-146">**Microsoft365Managed\_SensitiveData**</span></span>     |
|<span data-ttu-id="5609f-147">Power user</span><span class="sxs-lookup"><span data-stu-id="5609f-147">Power user</span></span>     | <span data-ttu-id="5609f-148">**Microsoft365Managed \_ PowerUser**</span><span class="sxs-lookup"><span data-stu-id="5609f-148">**Microsoft365Managed\_PowerUser**</span></span>          |
|<span data-ttu-id="5609f-149">Standard</span><span class="sxs-lookup"><span data-stu-id="5609f-149">Standard</span></span>     | <span data-ttu-id="5609f-150">**Microsoft365Managed \_ Standard**</span><span class="sxs-lookup"><span data-stu-id="5609f-150">**Microsoft365Managed\_Standard**</span></span>      |

> [!IMPORTANT]
> <span data-ttu-id="5609f-151">Grupptaggarna måste matcha de som anges i tabellen exakt, inklusive versaler och specialtecken.</span><span class="sxs-lookup"><span data-stu-id="5609f-151">The Group Tags must match those listed in the table exactly, including capitalization and special characters.</span></span> <span data-ttu-id="5609f-152">Då kan de nyligen registrerade enheterna tilldelas med Microsoft Managed Desktop Autopilot-profilen.</span><span class="sxs-lookup"><span data-stu-id="5609f-152">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>