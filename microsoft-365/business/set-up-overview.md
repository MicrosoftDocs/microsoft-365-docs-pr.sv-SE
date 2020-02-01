---
title: Översikt över inställningar
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Översikt över installationsstegen för Microsoft 365 Business.
ms.openlocfilehash: 07cbd4fd187f78474783db848ac9b69068d2b44a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595074"
---
# <a name="overview-of-setup"></a><span data-ttu-id="33e31-103">Översikt över inställningar</span><span class="sxs-lookup"><span data-stu-id="33e31-103">Overview of setup</span></span>

<span data-ttu-id="33e31-104">Titta på en kort video om microsoft 365 Business-installationen.</span><span class="sxs-lookup"><span data-stu-id="33e31-104">Watch a short video about Microsoft 365 Business setup.</span></span><br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

<span data-ttu-id="33e31-105">Om den här videon har hjälp dig kan du ta en titt på den[fullständiga utbildningsserien för småföretag och de som är nya för Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span><span class="sxs-lookup"><span data-stu-id="33e31-105">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).</span></span>

<span data-ttu-id="33e31-106">De flesta installationsstegen kan göras i installationsguiden, men de andra alternativen visas också.</span><span class="sxs-lookup"><span data-stu-id="33e31-106">Most of the setup steps can be done in the setup wizard, but the other options are also listed.</span></span>

## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="33e31-107">Steg 1: Lägg till din domän och användare</span><span class="sxs-lookup"><span data-stu-id="33e31-107">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="33e31-108">**[Lägg till din domän](set-up.md#add-your-domain-to-personalize-sign-in)** (om du har köpt domänen under [registreringen](sign-up.md)är det här steget redan klart.)</span><span class="sxs-lookup"><span data-stu-id="33e31-108">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="33e31-109">**Lägg till användare**.</span><span class="sxs-lookup"><span data-stu-id="33e31-109">**Add users**.</span></span> <span data-ttu-id="33e31-110">Du kan lägga till användare på något av de tre sätten:</span><span class="sxs-lookup"><span data-stu-id="33e31-110">You can add users in any of the three ways:</span></span>
        - <span data-ttu-id="33e31-111">I [guiden](set-up.md#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="33e31-111">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="33e31-112">Använd katalogsynkronisering för att [lägga till användare med hjälp av Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) om du har en lokal Active-katalog.Use directory synchronization to add users by using Azure AD Connect if you have an on-premises Active directory.</span><span class="sxs-lookup"><span data-stu-id="33e31-112">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="33e31-113">Du kan också [lägga till användare senare](add-users-m365b.md) i administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="33e31-113">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="33e31-114">Steg 2: Konfigurera säkerhetsprinciper och konfigurera enheterStep 2: Set up security policies and configure devices</span><span class="sxs-lookup"><span data-stu-id="33e31-114">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="33e31-115">Använd [installationsguiden](set-up.md#protect-your-organization) för att konfigurera enhetsprinciper.</span><span class="sxs-lookup"><span data-stu-id="33e31-115">Use the [Setup wizard](set-up.md#protect-your-organization) to configure device policies.</span></span> 
  - <span data-ttu-id="33e31-116">Du kan också lägga till fler eller redigera dem senare i [administrationscentret](view-policies-and-devices.md) och i [Intune-portalen](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span><span class="sxs-lookup"><span data-stu-id="33e31-116">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="33e31-117">Installationsguiden ställer också in grundläggande hotskydd och inställningar för dataförlustförebyggande.</span><span class="sxs-lookup"><span data-stu-id="33e31-117">The setup wizard will also set up basic threat protection and data loss prevention settings.</span></span>
  
  <span data-ttu-id="33e31-118">Förutom säkerhetsinställningarna i installationsguiden kan du öka säkerheten genom att lägga till följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="33e31-118">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

- <span data-ttu-id="33e31-119">**Skydd av skadlig e-post**</span><span class="sxs-lookup"><span data-stu-id="33e31-119">**Email malware protection**</span></span>
- <span data-ttu-id="33e31-120">**ATP anti-phishing ATP anti-phishing ATP anti-phishing ATP**</span><span class="sxs-lookup"><span data-stu-id="33e31-120">**ATP anti-phishing**</span></span>
- <span data-ttu-id="33e31-121">**Exchange Online - arkivering**</span><span class="sxs-lookup"><span data-stu-id="33e31-121">**Exchange Online Archiving**</span></span>
- <span data-ttu-id="33e31-122">**Skydd för Azure-information (plan1)**</span><span class="sxs-lookup"><span data-stu-id="33e31-122">**Azure Information Protection (Plan1**)</span></span>

<span data-ttu-id="33e31-123">Kom igång genom att se [öka hotskyddet](increase-threat-protection.md) och [ställa in kompatibilitetsfunktioner](set-up-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="33e31-123">To get started, see [increase threat protection](increase-threat-protection.md) and [set up compliance features](set-up-compliance.md).</span></span>

<span data-ttu-id="33e31-124">Se även [de 10 bästa sätten att skydda Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) för en översikt över bästa säkerhetspraxis.</span><span class="sxs-lookup"><span data-stu-id="33e31-124">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="33e31-125">Steg 3: Konfigurera och hantera Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="33e31-125">Step 3: Set up and manage Windows 10 devices</span></span>

<span data-ttu-id="33e31-126">När du har kört installationsguiden vill du proctect alla Windwos 10-datorer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="33e31-126">After you run the set up wizard, you will want to proctect all the Windwos 10 computers in your organization.</span></span>
  
- <span data-ttu-id="33e31-127">Windows 10 Pro är en [förutsättning](pre-requisites-for-data-protection.md) för Microsoft 365 Business, men om du har Windows 7 Pro, Windows 8 Pro eller Windows 8.1 Pro berättigar prenumerationen dig till en [uppgradering till Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span><span class="sxs-lookup"><span data-stu-id="33e31-127">Windows 10 Pro is a [prerequisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
- <span data-ttu-id="33e31-128">Följ stegen i [säkra Windows 10-datorer](secure-win-10-pcs.md) för att konfigurera principer för Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="33e31-128">Follow the steps in [secure Windows 10 PCs](secure-win-10-pcs.md) to set up policies for Windows 10 devices.</span></span>

<span data-ttu-id="33e31-129">När du ansluter till en Windows 10-enhet till Azure AD tillämpas de principer som du har angett för Windows 10-datorer på den.</span><span class="sxs-lookup"><span data-stu-id="33e31-129">When you join a Windows 10 device to Azure AD, the policies you set for Windows 10 computers get applied to it.</span></span> <span data-ttu-id="33e31-130">Mer information finns i [Konfigurera Windows-enheter för Microsoft 365 Business-användare](set-up-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="33e31-130">For more information, see [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md).</span></span>

## <a name="step-4-install-office-365-business"></a><span data-ttu-id="33e31-131">Steg 4: Installera Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="33e31-131">Step 4: Install Office 365 Business</span></span>
- <span data-ttu-id="33e31-132">Du kan installera Office automatiskt i Windows-enheterna med hjälp av [installationsguiden](set-up.md#deploy-office-365-client-apps).</span><span class="sxs-lookup"><span data-stu-id="33e31-132">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="33e31-133">Låt användare [installera Office-appar](https://docs.microsoft.com/office365/admin/setup/install-applications) för Windows och enheter.</span><span class="sxs-lookup"><span data-stu-id="33e31-133">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="33e31-134">Avancerade</span><span class="sxs-lookup"><span data-stu-id="33e31-134">Advanced</span></span>
- <span data-ttu-id="33e31-135">**Använda Autopilot för att konfigurera nya enheter**</span><span class="sxs-lookup"><span data-stu-id="33e31-135">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="33e31-136">Du kan använda [Windows Autopilot](add-autopilot-devices-and-profile.md) för att automatiskt förkonfigurera **nya** Windows 10-enheter för en användare, men det kan vara enklare att få en [partner](https://www.microsoft.com/solution-providers/search) som kan göra detta åt dig.</span><span class="sxs-lookup"><span data-stu-id="33e31-136">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="33e31-137">Du kan också gå till [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)och be en molnteknikexpert att konfigurera nya enheter som du köper.</span><span class="sxs-lookup"><span data-stu-id="33e31-137">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598), and ask a cloud technology expert to set up new devices that you purchase.</span></span>

- <span data-ttu-id="33e31-138">**Komma åt lokala resurserAccess on-premises resources**</span><span class="sxs-lookup"><span data-stu-id="33e31-138">**Access on-premises resources**</span></span>

     - <span data-ttu-id="33e31-139">Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering.</span><span class="sxs-lookup"><span data-stu-id="33e31-139">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="33e31-140">Följ stegen i [Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business](manage-windows-devices.md) för att konfigurera detta.</span><span class="sxs-lookup"><span data-stu-id="33e31-140">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="33e31-141">Det här är den metod som föredras och enheter i det här tillståndet kallas Hybrid Azure AD-anslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="33e31-141">This is the preferred method, and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="33e31-142">Om ditt företag har en lokal Active Directory som innehåller vissa lokala resurser (till exempel filresurser och skrivare) kan du ge dina Azure AD-anslutna enheter åtkomst till dessa resurser genom att följa stegen här: [Få åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="33e31-142">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers), you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="33e31-143">Se även</span><span class="sxs-lookup"><span data-stu-id="33e31-143">See also</span></span>

[<span data-ttu-id="33e31-144">Utbildningsvideor för Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="33e31-144">Microsoft 365 Business training videos</span></span>](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
