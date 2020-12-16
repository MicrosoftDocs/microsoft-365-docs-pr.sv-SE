---
title: Åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Lär dig hur du får till gång till lokala resurser som affärs program, fil resurser och skrivare från en Windows 10-enhet med Azure Active Directory.
ms.openlocfilehash: 22edf0c23d6318e1f70bcb21b2cd697ea0a75da4
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688242"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="3ba24-103">Åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="3ba24-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="3ba24-104">Den här artikeln gäller Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="3ba24-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="3ba24-105">Alla Windows 10-enheter som är anslutna till Azure Active Directory har åtkomst till alla molnbaserade resurser, till exempel Microsoft 365-appar och kan skyddas av Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="3ba24-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="3ba24-106">Du kan även tillåta åtkomst till lokala resurser som LOB-appar (Line of Business), fil resurser och skrivare.</span><span class="sxs-lookup"><span data-stu-id="3ba24-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="3ba24-107">För att tillåta åtkomst kan du använda [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) för att synkronisera din lokala Active Directory med Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3ba24-107">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="3ba24-108">Mer information finns i [Introduktion till enhets hantering i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span><span class="sxs-lookup"><span data-stu-id="3ba24-108">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="3ba24-109">Stegen sammanfattas i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="3ba24-109">The steps are also summarized in the following sections.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="3ba24-110">Kör Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="3ba24-110">Run Azure AD Connect</span></span>

<span data-ttu-id="3ba24-111">Utför följande steg för att aktivera organisationens Azure AD-anslutna enheter för att komma åt lokala resurser.</span><span class="sxs-lookup"><span data-stu-id="3ba24-111">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="3ba24-112">Om du vill synkronisera användare, grupper och kontakter från lokala Active Directory i Azure Active Directory kör du guiden för profilsynkronisering och Azure AD Connect enligt beskrivningen i [Konfigurera katalog-synkronisering för Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="3ba24-112">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).</span></span>
    
2. <span data-ttu-id="3ba24-113">När Active Directory-synkroniseringen är klar kontrollerar du att organisationens Windows 10-enheter är Azure AD-ansluten.</span><span class="sxs-lookup"><span data-stu-id="3ba24-113">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="3ba24-114">Det här steget utförs individuellt på varje Windows 10-enhet.</span><span class="sxs-lookup"><span data-stu-id="3ba24-114">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="3ba24-115">Mer information finns i [Konfigurera Windows-enheter för Microsoft 365 Business Premium-användare](set-up-windows-devices.md) .</span><span class="sxs-lookup"><span data-stu-id="3ba24-115">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="3ba24-116">När Windows 10-enheter är anslutna till Azure AD måste alla användare starta om sina enheter och logga in med sina Microsoft 365 Business Premium-autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="3ba24-116">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="3ba24-117">Alla enheter har nu till gång till lokala resurser.</span><span class="sxs-lookup"><span data-stu-id="3ba24-117">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="3ba24-118">Inga ytterligare åtgärder krävs för att få åtkomst till lokala resurser för Azure AD-anslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="3ba24-118">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="3ba24-119">Den här funktionen är inbyggd i Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3ba24-119">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="3ba24-120">Om du har planer på att logga in på AADJ-enheten annat än lösen ords metod som PIN/bio-metriskt via WHFB-inloggnings uppgifter och sedan åtkomst till lokala resurser (resurser, skrivare. etc), Följ https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="3ba24-120">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="3ba24-121">Om din organisation inte kan distribueras i konfigurationen för Azure AD med anslutna enheter enligt beskrivningen ovan kan du överväga att konfigurera [hybrid Azure AD-anslutande enhets konfiguration](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="3ba24-121">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="3ba24-122">Att tänka på när du ansluter Windows-enheter till Azure AD</span><span class="sxs-lookup"><span data-stu-id="3ba24-122">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="3ba24-123">Om Windows-enheten som du Azure-AD anslöt till fungerade tidigare i domänen eller i en arbets grupp bör du tänka på följande:</span><span class="sxs-lookup"><span data-stu-id="3ba24-123">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="3ba24-124">När en enhet som använder Azure AD ansluter till skapas en ny användare utan att någon befintlig profil refereras.</span><span class="sxs-lookup"><span data-stu-id="3ba24-124">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="3ba24-125">Profiler måste migreras manuellt.</span><span class="sxs-lookup"><span data-stu-id="3ba24-125">Profiles must be manually migrated.</span></span> <span data-ttu-id="3ba24-126">En användar profil innehåller information som favoriter, lokala filer, webb läsar inställningar och inställningar för Start-menyn.</span><span class="sxs-lookup"><span data-stu-id="3ba24-126">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="3ba24-127">Ett bra sätt att hitta ett verktyg från tredje part för att mappa befintliga filer och inställningar till den nya profilen.</span><span class="sxs-lookup"><span data-stu-id="3ba24-127">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="3ba24-128">Om enheten använder grupprincipobjekten (GPO) kanske vissa grup princip objekt inte har någon jämförbar [konfigurations tjänst leverantör](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) i Intune.</span><span class="sxs-lookup"><span data-stu-id="3ba24-128">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="3ba24-129">Kör [verktyget MMAT](https://www.microsoft.com/download/details.aspx?id=45520) för att hitta jämförbara kryptografiproviders för befintliga grup princip objekt.</span><span class="sxs-lookup"><span data-stu-id="3ba24-129">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="3ba24-130">Användarna kan inte autentisera till program som är beroende av Active Directory-autentisering.</span><span class="sxs-lookup"><span data-stu-id="3ba24-130">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="3ba24-131">Utvärdera det äldre programmet och Överväg att uppdatera till ett program som använder modern autentisering, om möjligt.</span><span class="sxs-lookup"><span data-stu-id="3ba24-131">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="3ba24-132">Active Directory-skrivaren fungerar inte.</span><span class="sxs-lookup"><span data-stu-id="3ba24-132">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="3ba24-133">Du kan tillhandahålla direkta skrivar vägar för alla användare eller använda [universell utskrift](https://aka.ms/UPDocs).</span><span class="sxs-lookup"><span data-stu-id="3ba24-133">You can provide direct printer paths for all users or use [Universal Print](https://aka.ms/UPDocs).</span></span>
