---
title: Steg för partner för att registrera enheter
description: Hur partners kan registrera enheter så att de kan hanteras av Microsoft Managed Desktop
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
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
ms.openlocfilehash: baf15ca4b83052af84d2b22b3d2604c6022ac900
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445596"
---
# <a name="steps-for-partners-to-register-devices"></a><span data-ttu-id="6735c-104">Steg för partner för att registrera enheter</span><span class="sxs-lookup"><span data-stu-id="6735c-104">Steps for Partners to register devices</span></span>


<span data-ttu-id="6735c-105">I det här avsnittet beskrivs stegen som partner kan följa för att registrera enheter.</span><span class="sxs-lookup"><span data-stu-id="6735c-105">This topic describes the steps for Partners to follow to register devices.</span></span> <span data-ttu-id="6735c-106">Hur du registrerar enheter själv finns i Registrera [enheter i Microsoft Managed Desktop själv.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="6735c-106">The process for registering devices yourself is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>



## <a name="prepare-for-registration"></a><span data-ttu-id="6735c-107">Förbereda för registrering</span><span class="sxs-lookup"><span data-stu-id="6735c-107">Prepare for registration</span></span> 
<span data-ttu-id="6735c-108">Innan du kan slutföra registreringen för en kund måste du först upprätta en relation med kunden i [Partnercenter.](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="6735c-108">Before completing registration for a customer, you must first establish a relationship with them at the [Partner Center](https://partner.microsoft.com/dashboard).</span></span> <span data-ttu-id="6735c-109">Mer information [om processen](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) finns i dokumentationen till medgivandet.</span><span class="sxs-lookup"><span data-stu-id="6735c-109">See the [consent documentation](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) for more details on that process.</span></span> <span data-ttu-id="6735c-110">Partner som är partner för CSP kan lägga till enheter åt en kund, så länge kunden har gett sitt samtycke.</span><span class="sxs-lookup"><span data-stu-id="6735c-110">Any CSP partner can add devices on behalf of any customer, as long as the customer consents.</span></span> <span data-ttu-id="6735c-111">Du kan också läsa mer om partnerrelationer och Autopilot-behörigheter i [Hjälp om Partnercenter.](/partner-center/customers_revoke_admin_privileges#windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="6735c-111">You can also learn more about partner relationships and Autopilot permissions at [Partner Center help](/partner-center/customers_revoke_admin_privileges#windows-autopilot).</span></span>


> [!NOTE]
> <span data-ttu-id="6735c-112">Den här dokumentationen gäller endast partner och OEM-maskiner.</span><span class="sxs-lookup"><span data-stu-id="6735c-112">This documentation is only for Partners and OEMs.</span></span> <span data-ttu-id="6735c-113">Processen för självregistrering har dokumenterats i Registrera [enheter i Microsoft Managed Desktop själv.](register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="6735c-113">The process for self-registration is documented in [Register devices in Microsoft Managed Desktop yourself](register-devices-self.md).</span></span>


## <a name="register-devices-by-using-partner-center"></a><span data-ttu-id="6735c-114">Registrera enheter med hjälp av Partnercenter</span><span class="sxs-lookup"><span data-stu-id="6735c-114">Register devices by using Partner Center</span></span>

<span data-ttu-id="6735c-115">När du har upprättat relationen med dina kunder kan du använda PartnerCenter för att lägga till enheter på Autopilot för alla kunder som du har en relation med genom att följa de här stegen:</span><span class="sxs-lookup"><span data-stu-id="6735c-115">Once you have established the relationship with your customers, you can leverage Partner Center to add devices to Autopilot for any of the customers that you have a relationship with by following these steps:</span></span>

1. <span data-ttu-id="6735c-116">Gå till [Partnercenter](https://partner.microsoft.com/dashboard)</span><span class="sxs-lookup"><span data-stu-id="6735c-116">Navigate to [Partner Center](https://partner.microsoft.com/dashboard)</span></span>
2. <span data-ttu-id="6735c-117">Välj **Kunder** på Menyn Partnercenter och välj sedan den kund vars enheter du vill hantera.</span><span class="sxs-lookup"><span data-stu-id="6735c-117">Select **Customers** from the Partner Center menu and then select the customer whose devices you want to manage.</span></span>
3. <span data-ttu-id="6735c-118">Välj Enheter på kundens **informationssida.**</span><span class="sxs-lookup"><span data-stu-id="6735c-118">On the customer's detail page, select **Devices**.</span></span>
4. <span data-ttu-id="6735c-119">Under **Använd profiler på** enheter väljer du Lägg till **enheter**.</span><span class="sxs-lookup"><span data-stu-id="6735c-119">Under **Apply profiles** to devices, select **Add devices**.</span></span>
5. <span data-ttu-id="6735c-120">Ange **Microsoft365Managed_Autopilot** för gruppnamnet och välj  sedan Bläddra för att ladda upp kundens lista (i CSV-filformat) till Partner Center.</span><span class="sxs-lookup"><span data-stu-id="6735c-120">Enter **Microsoft365Managed_Autopilot** for the Group Name and then select **Browse** to upload the customer's list (in .csv file format) to Partner Center.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="6735c-121">Gruppnamnet måste matcha **Microsoft365Managed_Autopilot** exakt, inklusive versaler och specialtecken.</span><span class="sxs-lookup"><span data-stu-id="6735c-121">The Group Name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="6735c-122">Då kan de nyligen registrerade enheterna tilldelas med Microsoft Managed Desktop Autopilot-profilen.</span><span class="sxs-lookup"><span data-stu-id="6735c-122">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>

>[!NOTE]
> <span data-ttu-id="6735c-123">Du borde ha fått den här CSV-filen med ditt enhetsköp.</span><span class="sxs-lookup"><span data-stu-id="6735c-123">You should have received this .csv file with your device purchase.</span></span> <span data-ttu-id="6735c-124">Om du inte har fått någon CSV-fil kan du skapa en själv genom att följa stegen i Lägga till [enheter i Windows Autopilot.](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="6735c-124">If you didn't receive a .csv file, you can create one yourself by following the steps in [Adding devices to Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell).</span></span> <span data-ttu-id="6735c-125">Windows PowerShell-skriptet är inte samma som det som används för [Microsoft Managed Desktop Admin-portalen.](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash)</span><span class="sxs-lookup"><span data-stu-id="6735c-125">The Windows PowerShell script is different from the one used for the [Microsoft Managed Desktop Admin portal](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash).</span></span> <span data-ttu-id="6735c-126">Partners bör använda [Get-WindowsAutoPilotInfo för](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) att registrera enheter för Microsoft Managed Desktop-enheter i Partner Center.</span><span class="sxs-lookup"><span data-stu-id="6735c-126">Partners should use [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to register devices for Microsoft Managed Desktop devices in Partner Center.</span></span>

<span data-ttu-id="6735c-127">Om du får ett felmeddelande när du försöker ladda upp CSV-filen kontrollerar du formatet på filen.</span><span class="sxs-lookup"><span data-stu-id="6735c-127">If you get an error message while trying to upload the .csv file, check the format of the file.</span></span> <span data-ttu-id="6735c-128">Se till att kolumnordningen stämmer överens med vad som beskrivs i Använda [Windows Autopilot-profiler](/partner-center/autopilot#add-devices-to-a-customers-account)på nya enheter för att anpassa en kunds användning.</span><span class="sxs-lookup"><span data-stu-id="6735c-128">Make sure the column order matches what is described in [Use Windows Autopilot profiles on new devices to customize a customer's out-of-box experience](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span> <span data-ttu-id="6735c-129">Du kan också använda csv-exempelfilen från länken bredvid Lägg **till enheter för** att skapa en enhetslista.</span><span class="sxs-lookup"><span data-stu-id="6735c-129">You can also use the sample .csv file provided from the link next to **Add devices** to create a device list.</span></span> 

<span data-ttu-id="6735c-130">Mer information om Autopilot i partnerscenarier finns i [Lägga till enheter till en kunds konto.](/partner-center/autopilot#add-devices-to-a-customers-account)</span><span class="sxs-lookup"><span data-stu-id="6735c-130">For more information about Autopilot in Partner scenarios, see [Add devices to a customer’s account](/partner-center/autopilot#add-devices-to-a-customers-account).</span></span>


## <a name="register-devices-by-using-the-oem-api"></a><span data-ttu-id="6735c-131">Registrera enheter med hjälp av OEM API</span><span class="sxs-lookup"><span data-stu-id="6735c-131">Register devices by using the OEM API</span></span>

<span data-ttu-id="6735c-132">Innan du slutför registreringen för en kund måste du först upprätta en relation med kunden.</span><span class="sxs-lookup"><span data-stu-id="6735c-132">Before completing registration for a customer, you must first establish a relationship with them.</span></span> <span data-ttu-id="6735c-133">Du bör ha en unik länk som du kan ge till dina respektive kunder.</span><span class="sxs-lookup"><span data-stu-id="6735c-133">You should have a unique link to provide to your respective customers.</span></span> <span data-ttu-id="6735c-134">Se [Så här upprättar du EN OEM-relation.](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)</span><span class="sxs-lookup"><span data-stu-id="6735c-134">See [How to establish OEM relationship](/windows/deployment/windows-autopilot/registration-auth#oem-authorization).</span></span>

<span data-ttu-id="6735c-135">När du har upprättat relationen kan du börja registrera enheter för kunder med group **tag-Microsoft365Managed_Autopilot.**</span><span class="sxs-lookup"><span data-stu-id="6735c-135">Once you've established the relationship, you can start registering devices for customers using the Group Tag **Microsoft365Managed_Autopilot**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6735c-136">Gruppnamnet måste matcha **Microsoft365Managed_Autopilot** exakt, inklusive versaler och specialtecken.</span><span class="sxs-lookup"><span data-stu-id="6735c-136">The group name must match **Microsoft365Managed_Autopilot** exactly, including capitalization and special characters.</span></span> <span data-ttu-id="6735c-137">Då kan de nyligen registrerade enheterna tilldelas med Microsoft Managed Desktop Autopilot-profilen.</span><span class="sxs-lookup"><span data-stu-id="6735c-137">This will allow the newly registered devices to be assigned with the Microsoft Managed Desktop Autopilot profile.</span></span>