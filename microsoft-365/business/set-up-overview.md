---
title: Översikt över ställs in
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Översikt av stegen för Microsoft 365 Business.
ms.openlocfilehash: ae7ed0aab36a6e759e0f0c1fbc3d3183273a284e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "35086396"
---
# <a name="overview-of-setup"></a><span data-ttu-id="ffa31-103">Översikt över inställningar</span><span class="sxs-lookup"><span data-stu-id="ffa31-103">Overview of setup</span></span>

<span data-ttu-id="ffa31-104">Kan du göra de flesta av stegen i guiden, men andra alternativ finns.</span><span class="sxs-lookup"><span data-stu-id="ffa31-104">Most of the set up steps can be done in the setup wizard, but the other options are also listed.</span></span>


## <a name="step-1-add-your-domain-and-users"></a><span data-ttu-id="ffa31-105">Steg 1: Lägg till din domän och användare</span><span class="sxs-lookup"><span data-stu-id="ffa31-105">Step 1: Add your domain and users</span></span>

   - <span data-ttu-id="ffa31-106">**[Lägg till din domän](set-up.md#add-your-domain-to-personalize-sign-in)** (om du har köpt din domän under [registrera](sign-up.md)görs redan det här steget.)</span><span class="sxs-lookup"><span data-stu-id="ffa31-106">**[Add your domain](set-up.md#add-your-domain-to-personalize-sign-in)** (if you bought your domain during [sign up](sign-up.md), this step is already done.)</span></span>

    - <span data-ttu-id="ffa31-107">**Lägga till användare**.</span><span class="sxs-lookup"><span data-stu-id="ffa31-107">**Add users**.</span></span> <span data-ttu-id="ffa31-108">Du kan göra detta på något av tre sätt:</span><span class="sxs-lookup"><span data-stu-id="ffa31-108">You can do this in any of the three ways:</span></span>
        - <span data-ttu-id="ffa31-109">I [guiden](set-up.md#add-users-in-the-wizard).</span><span class="sxs-lookup"><span data-stu-id="ffa31-109">In the [wizard](set-up.md#add-users-in-the-wizard).</span></span>
        - <span data-ttu-id="ffa31-110">Använda katalogsynkronisering för att [lägga till användare med hjälp av Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) om du har en lokal Active directory.</span><span class="sxs-lookup"><span data-stu-id="ffa31-110">Use directory synchronization to [add users by using Azure AD Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) if you have an on-premises Active directory.</span></span>
        - <span data-ttu-id="ffa31-111">Du kan också [lägga till användare senare](add-users-m365b.md) i administratörscenter.</span><span class="sxs-lookup"><span data-stu-id="ffa31-111">You can also [add users later](add-users-m365b.md) in the admin center.</span></span>
## <a name="step-2-set-up-security-policies-and-configure-devices"></a><span data-ttu-id="ffa31-112">Steg 2: Ställa in IPSec-principer och konfigurera enheter</span><span class="sxs-lookup"><span data-stu-id="ffa31-112">Step 2: Set up security policies and configure devices</span></span> 

  - <span data-ttu-id="ffa31-113">Använd [installationsguiden för](set-up.md#set-up-security-policies-and-device-configurations) att konfigurera enheten och säkerhetsprinciper.</span><span class="sxs-lookup"><span data-stu-id="ffa31-113">Use the [Setup wizard](set-up.md#set-up-security-policies-and-device-configurations) to configure device and security policies.</span></span> 
  - <span data-ttu-id="ffa31-114">Du kan också lägga till fler eller redigera dem senare i [administratörscenter](view-policies-and-devices.md) och [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span><span class="sxs-lookup"><span data-stu-id="ffa31-114">You can also add more or edit them later in the [admin center](view-policies-and-devices.md) and in the [Intune portal](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).</span></span>
  - <span data-ttu-id="ffa31-115">Förutom att säkerhetsinställningarna i installationsguiden kan du öka säkerheten genom att lägga till följande inställningar:</span><span class="sxs-lookup"><span data-stu-id="ffa31-115">In addition to the security settings in the setup wizard, you can increase your security by adding the following settings:</span></span>

      - <span data-ttu-id="ffa31-116">**Skydd mot skadlig programvara för e-post**</span><span class="sxs-lookup"><span data-stu-id="ffa31-116">**Email malware protection**</span></span>
      - <span data-ttu-id="ffa31-117">**Avancerade hot skydd (ATP) Safe länkar**</span><span class="sxs-lookup"><span data-stu-id="ffa31-117">**Advanced Threat Protection (ATP) Safe links**</span></span>
      - <span data-ttu-id="ffa31-118">**ATP-säkra bifogade filer**</span><span class="sxs-lookup"><span data-stu-id="ffa31-118">**ATP Safe Attachments**</span></span>
      - <span data-ttu-id="ffa31-119">**ATP anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="ffa31-119">**ATP anti-phishing**</span></span>
      - <span data-ttu-id="ffa31-120">**Exchange Online - arkivering**</span><span class="sxs-lookup"><span data-stu-id="ffa31-120">**Exchange Online Archiving**</span></span>
      - <span data-ttu-id="ffa31-121">**Förhindra dataförlust (DLP)**</span><span class="sxs-lookup"><span data-stu-id="ffa31-121">**Data Loss Prevention (DLP)**</span></span>
      - <span data-ttu-id="ffa31-122">**Azure informationsskydd (Plan1**)</span><span class="sxs-lookup"><span data-stu-id="ffa31-122">**Azure Information Protection (Plan1**)</span></span>

          <span data-ttu-id="ffa31-123">Att komma igång finns i [ställa in avancerade IPSec-principer](set-up-advanced-security.md).</span><span class="sxs-lookup"><span data-stu-id="ffa31-123">To get started see, [set up advanced security policies](set-up-advanced-security.md).</span></span>

        <span data-ttu-id="ffa31-124">Se även [top 10 sätt att skydda verksamheten Microsoft 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) för en översikt av bästa säkerhetspraxis.</span><span class="sxs-lookup"><span data-stu-id="ffa31-124">See also [top 10 ways to secure your Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) for a roadmap of best security practices.</span></span>

## <a name="step-3-set-up-and-manage-windows-10-devices"></a><span data-ttu-id="ffa31-125">Steg 3: Konfigurera och hantera Windows 10 enheter</span><span class="sxs-lookup"><span data-stu-id="ffa31-125">Step 3: Set up and manage Windows 10 devices</span></span>

   <span data-ttu-id="ffa31-126">När du ansluter en enhet med Windows 10 till Azure AD tillämpas principer som angetts i [steg 2](#step-2-set-up-security-policies-and-configure-devices) till den.</span><span class="sxs-lookup"><span data-stu-id="ffa31-126">When you join a Windows 10 device to Azure AD, the policies you set up in [Step 2](#step-2-set-up-security-policies-and-configure-devices) get applied to it.</span></span>

   - <span data-ttu-id="ffa31-127">Windows 10 Pro är en [nödvändig förutsättning](pre-requisites-for-data-protection.md) för Microsoft 365 företag, men om du har Windows 7 Pro, Windows 8 Pro eller Windows 8.1 Pro din prenumeration ger dig rätt att [Uppgradera till Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span><span class="sxs-lookup"><span data-stu-id="ffa31-127">Windows 10 Pro is a [pre-requisite](pre-requisites-for-data-protection.md) for Microsoft 365 Business, but if you have Windows 7 Pro, Windows 8 Pro, or Windows 8.1 Pro, your subscription entitles you to an [upgrade to  Windows 10 Pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).</span></span>
    - <span data-ttu-id="ffa31-128">Använd [installationsguiden för](set-up.md#set-up-security-policies-and-device-configurations) att konfigurera principer för Windows 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="ffa31-128">Use the [setup wizard](set-up.md#set-up-security-policies-and-device-configurations) to configure policies for Windows 10 devices.</span></span>

## <a name="stes-4-install-office-365-business"></a><span data-ttu-id="ffa31-129">Stes 4: Installera Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="ffa31-129">Stes 4: Install Office 365 Business</span></span>
- <span data-ttu-id="ffa31-130">Du kan automatiskt installera Office i Windows-enheter med hjälp av [installationsguiden](set-up.md#deploy-office-365-client-apps).</span><span class="sxs-lookup"><span data-stu-id="ffa31-130">You can automatically install Office in the Windows devices by using the [setup wizard](set-up.md#deploy-office-365-client-apps).</span></span>
- <span data-ttu-id="ffa31-131">Automatiskt [installera Office](auto-install-or-uninstall-office.md) admin Center.</span><span class="sxs-lookup"><span data-stu-id="ffa31-131">Automatically [install Office](auto-install-or-uninstall-office.md) from the admin center.</span></span>
- <span data-ttu-id="ffa31-132">Låt användarna [installera Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) för Windows och enheter.</span><span class="sxs-lookup"><span data-stu-id="ffa31-132">Let users [install Office apps](https://docs.microsoft.com/office365/admin/setup/install-applications) for Windows and devices.</span></span>
     
## <a name="advanced"></a><span data-ttu-id="ffa31-133">Avancerad</span><span class="sxs-lookup"><span data-stu-id="ffa31-133">Advanced</span></span>
- <span data-ttu-id="ffa31-134">**Använda Autopilot för att skapa nya enheter**</span><span class="sxs-lookup"><span data-stu-id="ffa31-134">**Use Autopilot to set up new devices**</span></span>
            
     <span data-ttu-id="ffa31-135">Du kan använda [Windows Autopilot](add-autopilot-devices-and-profile.md) före automatiskt konfigurera **nya** Windows 10-enheter för en användare, men kan det vara enklare att få en [partner](https://www.microsoft.com/solution-providers/search) som kan göra detta åt dig.</span><span class="sxs-lookup"><span data-stu-id="ffa31-135">You can use [Windows Autopilot](add-autopilot-devices-and-profile.md) to automatically pre-configure **new** Windows 10 devices for a user, but it might be easier to get a [partner](https://www.microsoft.com/solution-providers/search) who can do this for you.</span></span> <span data-ttu-id="ffa31-136">Du kan också gå till [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) och be en expert moln teknik skapa nya enheter du köper du.</span><span class="sxs-lookup"><span data-stu-id="ffa31-136">You can also go to [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) and ask a cloud technology expert set up new devices you purchase for you.</span></span>

- <span data-ttu-id="ffa31-137">**Komma åt lokala resurser**</span><span class="sxs-lookup"><span data-stu-id="ffa31-137">**Access on-premises resources**</span></span>

     - <span data-ttu-id="ffa31-138">Om organisationen använder Windows Server Active Directory på lokaler, kan du ställa in Microsoft 365 Business att skydda din Windows 10-enheter, men fortfarande åtkomst till lokala resurser som kräver autentisering med lokala.</span><span class="sxs-lookup"><span data-stu-id="ffa31-138">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="ffa31-139">Följ stegen i [Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business](manage-windows-devices.md) att ställa in.</span><span class="sxs-lookup"><span data-stu-id="ffa31-139">Follow the steps in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business](manage-windows-devices.md) to set this up.</span></span> <span data-ttu-id="ffa31-140">Detta är den bästa metoden och enheter i det här tillståndet kallas Hybrid Azure AD anslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="ffa31-140">This is the preferred method and devices in this state are called Hybrid Azure AD joined devices.</span></span>

    - <span data-ttu-id="ffa31-141">Om ditt företag har en lokal Active Directory som innehåller vissa lokala resurser (till exempel filresurser och skrivare), du kan ge din Azure AD-anslutna enheter åtkomst till dessa resurser genom att följa instruktionerna här: [Access lokal resurser från en Azure AD-ansluten enhet i Microsoft 365 Business](access-resources.md).</span><span class="sxs-lookup"><span data-stu-id="ffa31-141">If your business has a local Active Directory that contains some on-premises resources (such as file shares and printers) , you can give your Azure AD-joined devices access to these resources by following the steps here: [Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business](access-resources.md).</span></span>

  