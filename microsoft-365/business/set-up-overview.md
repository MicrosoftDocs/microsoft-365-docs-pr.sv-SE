---
title: Översikt över konfiguration
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Lär dig hur du konfigurerar de olika installations stegen för Microsoft 365 Business Premium, från prenumeration, att lägga till en domän och användare, för att konfigurera säkerhets principer och mycket mer.
ms.openlocfilehash: 8ec01a58d1a15d5c4aa1cef8b81518b474630d8b
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841150"
---
# <a name="overview-of-setup"></a><span data-ttu-id="1339c-103">Översikt över konfiguration</span><span class="sxs-lookup"><span data-stu-id="1339c-103">Overview of setup</span></span>

<span data-ttu-id="1339c-104">Titta på en kort video om Microsoft 365 Business Premium-inställningar.</span><span class="sxs-lookup"><span data-stu-id="1339c-104">Watch a short video about Microsoft 365 Business Premium setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

<span data-ttu-id="1339c-105">Om den här videon har hjälpt dig kan du ta en titt på den [fullständiga utbildningsserien för småföretag och nya användare av Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="1339c-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

<span data-ttu-id="1339c-106">De flesta installations anvisningarna kan göras i den interaktiva installationen, men de andra alternativen visas också.</span><span class="sxs-lookup"><span data-stu-id="1339c-106">Most of the setup steps can be done in the guided setup, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="1339c-107">Steg 1: Lägg till domänen och användarna</span><span class="sxs-lookup"><span data-stu-id="1339c-107">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="1339c-108">**[Lägga till din domän](set-up.md#add-your-domain-to-personalize-sign-in)** (om du har köpt din domän under [registreringen](sign-up.md)är det här steget redan klart.)</span><span class="sxs-lookup"><span data-stu-id="1339c-108">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

   - <span data-ttu-id="1339c-109">**Lägga till användare** .</span><span class="sxs-lookup"><span data-stu-id="1339c-109">**Add users** .</span></span> <span data-ttu-id="1339c-110">Du kan lägga till användare på något av de tre sätten:</span><span class="sxs-lookup"><span data-stu-id="1339c-110">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="1339c-111">I den [guidade installationen](set-up.md#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="1339c-111">In the [guided setup](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="1339c-112">Använd katalog-synkronisering för att [lägga till användare med Azure AD Connect](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) om du har en lokal Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1339c-112">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="1339c-113">Du kan också [lägga till användare](add-users-m365b.md) i administrations centret.</span><span class="sxs-lookup"><span data-stu-id="1339c-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="1339c-114">Steg 2: Konfigurera säkerhets principer och konfigurera enheter</span><span class="sxs-lookup"><span data-stu-id="1339c-114">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="1339c-115">Använd den [guidade installationen](set-up.md#protect-your-organization) för att konfigurera enhets principer.</span><span class="sxs-lookup"><span data-stu-id="1339c-115">Use the [guided setup](set-up.md#protect-your-organization) to configure device policies.</span></span> 
  - <span data-ttu-id="1339c-116">Du kan också lägga till fler eller redigera dem senare i [administrations centret](view-policies-and-devices.md) och i [Intune-portalen](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span><span class="sxs-lookup"><span data-stu-id="1339c-116">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="1339c-117">Installations guiden kommer även att konfigurera inställningar för skydd mot grundläggande hotet och förhindra data förlust.</span><span class="sxs-lookup"><span data-stu-id="1339c-117">The setup wizard will also set up basic threat protection and data loss prevention settings.</span></span>
  
  <span data-ttu-id="1339c-118">Utöver säkerhets inställningarna i installations guiden kan du öka säkerheten genom att lägga till följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="1339c-118">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

- <span data-ttu-id="1339c-119">**Skydd mot skadlig program vara**</span><span class="sxs-lookup"><span data-stu-id="1339c-119">**Email malware protection**</span></span>
- <span data-ttu-id="1339c-120">**Stöldskydd med ATP**</span><span class="sxs-lookup"><span data-stu-id="1339c-120">**ATP anti-phishing**</span></span>
- <span data-ttu-id="1339c-121">**Exchange Online - arkivering**</span><span class="sxs-lookup"><span data-stu-id="1339c-121">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="1339c-122">**Azure information Protection (Plan1** )</span><span class="sxs-lookup"><span data-stu-id="1339c-122">**Azure Information Protection (Plan1** )</span></span>

<span data-ttu-id="1339c-123">För att komma igång, se [öka hotets skydd](increase-threat-protection.md) och [Konfigurera funktioner för efterlevnad](set-up-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="1339c-123">To get started, see [increase threat protection](increase-threat-protection.md) and [set up compliance features](set-up-compliance.md).</span></span>

<span data-ttu-id="1339c-124">Se även [de 10 bästa sätten att skydda din Microsoft 365 Business Premium](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) för en Road-karta över bästa säkerhets praxis.</span><span class="sxs-lookup"><span data-stu-id="1339c-124">See also [top 10 ways to secure your Microsoft 365 Business Premium](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a road-map of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="1339c-125">Steg 3: Konfigurera och hantera Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="1339c-125">Step 3: Set up and manage Windows 10 devices</span></span>

<span data-ttu-id="1339c-126">När du är klar med den interaktiva installationen ska du skydda alla Windows 10-datorer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="1339c-126">After you complete the guided setup, you will want to protect all the Windows 10 computers in your organization.</span></span>
  
- <span data-ttu-id="1339c-127">Windows 10 Pro är en [förutsättning](pre-requisites-for-data-protection.md) för Microsoft 365 Business Premium, men om du har Windows 7 Pro, Windows 8 Pro eller Windows 8,1 Pro kan ditt abonnemang ge dig en [uppgradering till Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span><span class="sxs-lookup"><span data-stu-id="1339c-127">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business Premium, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
- <span data-ttu-id="1339c-128">Följ anvisningarna i [skydda Windows 10-datorer](secure-win-10-pcs.md) för att konfigurera principer för Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="1339c-128">Follow the steps in [secure Windows 10 PCs](secure-win-10-pcs.md) to set up policies for Windows 10 devices.</span></span>

<span data-ttu-id="1339c-129">När du ansluter till en Windows 10-enhet till Azure AD tillämpas de principer som du angav för Windows 10-datorer.</span><span class="sxs-lookup"><span data-stu-id="1339c-129">When you join a Windows 10 device to Azure AD, the policies you set for Windows 10 computers get applied to it.</span></span> <span data-ttu-id="1339c-130">Mer information finns i [Konfigurera Windows-enheter för Microsoft 365-användare](set-up-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="1339c-130">For more information, see [Set up Windows devices for Microsoft 365 users](set-up-windows-devices.md).</span></span>

## <a name="step-4-install-microsoft-365-apps-for-business"></a><span data-ttu-id="1339c-131">Steg 4: installera Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="1339c-131">Step 4: Install Microsoft 365 Apps for business</span></span>
- <span data-ttu-id="1339c-132">Du kan installera Office automatiskt på Windows-enheter med hjälp av [installations guiden](set-up.md#deploy-office-365-client-apps).</span><span class="sxs-lookup"><span data-stu-id="1339c-132">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="1339c-133">Låt användare [installera Office-program](https://docs.microsoft.com/office365/admin/setup/install-applications) för Windows och enheter.</span><span class="sxs-lookup"><span data-stu-id="1339c-133">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="1339c-134">Avancerat</span><span class="sxs-lookup"><span data-stu-id="1339c-134">Advanced</span></span>
- <span data-ttu-id="1339c-135">**Använda autopilot för att konfigurera nya enheter**</span><span class="sxs-lookup"><span data-stu-id="1339c-135">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="1339c-136">Du kan använda [autopilot för Windows](add-autopilot-devices-and-profile.md) för att automatiskt konfigurera **nya** Windows 10-enheter för en användare, men det kan vara lättare att skaffa en [partner](https://www.microsoft.com/solution-providers/search) som kan göra detta åt dig.</span><span class="sxs-lookup"><span data-stu-id="1339c-136">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="1339c-137">Du kan också gå till [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)och be en moln teknologi expert att konfigurera nya enheter som du köper.</span><span class="sxs-lookup"><span data-stu-id="1339c-137">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="1339c-138">**Åtkomst till lokala resurser**</span><span class="sxs-lookup"><span data-stu-id="1339c-138">**Access on-premises resources**</span></span>

     - <span data-ttu-id="1339c-139">Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business Premium för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal inloggning.</span><span class="sxs-lookup"><span data-stu-id="1339c-139">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="1339c-140">Följ stegen i [Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business Premium](manage-windows-devices.md) för att konfigurera detta.</span><span class="sxs-lookup"><span data-stu-id="1339c-140">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="1339c-141">Det här är den bästa metoden och enheter i det här läget kallas hybrid Azure AD-anslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="1339c-141">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="1339c-142">Om ditt företag har en lokal Active Directory-resurs (till exempel fil resurser och skrivare) kan du ge Azure AD-anslutna enheter åtkomst till dessa resurser genom att följa anvisningarna här: [komma åt lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business Premium](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="1339c-142">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium](access-resources.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1339c-143">Se även</span><span class="sxs-lookup"><span data-stu-id="1339c-143">See also</span></span>

[<span data-ttu-id="1339c-144">Utbildningsvideor för Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="1339c-144">Microsoft 365 for business training videos</span></span>](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
