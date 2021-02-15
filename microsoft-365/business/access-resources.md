---
title: Få åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business
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
description: Lär dig hur du får åtkomst till lokala resurser som verksamhetsappar, filresurser och skrivare från en Azure Active Directory-ansluten Windows 10-enhet.
ms.openlocfilehash: fc02fd30f41f25f52e653e750a6bdfd1bd7f800e
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233849"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="99c94-103">Få åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="99c94-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="99c94-104">Den här artikeln gäller Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="99c94-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="99c94-105">Alla Windows 10-enheter som är Azure Active Directory-medlemmar har tillgång till alla molnbaserade resurser, till exempel Microsoft 365-appar, och kan skyddas av Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="99c94-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="99c94-106">Du kan också ge åtkomst till lokala resurser som verksamhetsbaserade appar, filresurser och skrivare.</span><span class="sxs-lookup"><span data-stu-id="99c94-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="99c94-107">Om du vill tillåta åtkomst [använder du Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) för att synkronisera din lokala Active Directory med Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="99c94-107">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="99c94-108">Mer information finns i [introduktionen till enhetshantering i Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/device-management-introduction)</span><span class="sxs-lookup"><span data-stu-id="99c94-108">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="99c94-109">Stegen sammanfattas även i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="99c94-109">The steps are also summarized in the following sections.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="99c94-110">Kör Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="99c94-110">Run Azure AD Connect</span></span>

<span data-ttu-id="99c94-111">Utför följande steg för att aktivera din organisations Azure AD-anslutna enheter för åtkomst till lokala resurser.</span><span class="sxs-lookup"><span data-stu-id="99c94-111">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="99c94-112">Om du vill synkronisera användare, grupper och kontakter från lokal Active Directory till Azure Active Directory kör du katalogsynkroniseringsguiden och Azure AD Connect enligt beskrivningen i Konfigurera katalogsynkronisering för [Office 365.](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</span><span class="sxs-lookup"><span data-stu-id="99c94-112">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).</span></span>
    
2. <span data-ttu-id="99c94-113">När katalogsynkroniseringen är klar kontrollerar du att organisationens Windows 10-enheter är Azure AD-anslutna.</span><span class="sxs-lookup"><span data-stu-id="99c94-113">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="99c94-114">Det här steget utförs individuellt på varje Windows 10-enhet.</span><span class="sxs-lookup"><span data-stu-id="99c94-114">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="99c94-115">Mer [information finns i Konfigurera Windows-enheter för Microsoft 365 Business Premium-användare.](set-up-windows-devices.md)</span><span class="sxs-lookup"><span data-stu-id="99c94-115">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="99c94-116">När Windows 10-enheterna har anslutits till Azure AD måste alla användare starta om sina enheter och logga in med sina Microsoft 365 Business Premium-autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="99c94-116">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="99c94-117">Alla enheter har nu även åtkomst till lokala resurser.</span><span class="sxs-lookup"><span data-stu-id="99c94-117">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="99c94-118">Inga ytterligare steg krävs för att få åtkomst till lokala resurser för Azure AD-anslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="99c94-118">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="99c94-119">Den här funktionen är inbyggd i Windows 10.</span><span class="sxs-lookup"><span data-stu-id="99c94-119">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="99c94-120">Om du har planer på att logga in på AADJ-enheten på något annat sätt än lösenordsmetoden Som PIN/Bio-metric via VAFB-inloggning med autentiseringsuppgifter och sedan åtkomst till lokala resurser (resurser,skrivare.). o.s.v.), följ https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="99c94-120">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="99c94-121">Om din organisation inte är redo att distribuera i konfigurationen av azure AD-ansluten enhet som beskrivs ovan kan det vara bra att konfigurera konfiguration av [Azure AD-ansluten hybridenhet.](manage-windows-devices.md)</span><span class="sxs-lookup"><span data-stu-id="99c94-121">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="99c94-122">Att tänka på när du ansluter Windows-enheter till Azure AD</span><span class="sxs-lookup"><span data-stu-id="99c94-122">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="99c94-123">Om den Windows-enhet som du Azure-AD-ansluten till tidigare var domän ansluten eller i en arbetsgrupp ska du ta hänsyn till följande begränsningar:</span><span class="sxs-lookup"><span data-stu-id="99c94-123">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="99c94-124">När en enhet Azure AD ansluts, skapas en ny användare utan att referera till en befintlig profil.</span><span class="sxs-lookup"><span data-stu-id="99c94-124">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="99c94-125">Profiler måste migreras manuellt.</span><span class="sxs-lookup"><span data-stu-id="99c94-125">Profiles must be manually migrated.</span></span> <span data-ttu-id="99c94-126">En användarprofil innehåller information som favoriter, lokala filer, webbläsarinställningar och inställningar för Start-menyn.</span><span class="sxs-lookup"><span data-stu-id="99c94-126">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="99c94-127">Det bästa sättet är att hitta ett verktyg från tredje part för att mappa befintliga filer och inställningar till den nya profilen.</span><span class="sxs-lookup"><span data-stu-id="99c94-127">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="99c94-128">Om enheten använder en grupprincip GPO kanske vissa GPOs inte [](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) har en jämförlig leverantör av konfigurationstjänster (CSP) i Intune.</span><span class="sxs-lookup"><span data-stu-id="99c94-128">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="99c94-129">Kör [MMAT-verktyget för att](https://www.microsoft.com/download/details.aspx?id=45520) hitta liknande csps för befintliga GPOs.</span><span class="sxs-lookup"><span data-stu-id="99c94-129">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="99c94-130">Användare kanske inte kan autentisera till program som är beroende av Active Directory-autentisering.</span><span class="sxs-lookup"><span data-stu-id="99c94-130">Users might not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="99c94-131">Utvärdera den äldre appen och överväg att uppdatera till en app som använder modern autentisering, om möjligt.</span><span class="sxs-lookup"><span data-stu-id="99c94-131">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="99c94-132">Identifiering av Active Directory-skrivare fungerar inte.</span><span class="sxs-lookup"><span data-stu-id="99c94-132">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="99c94-133">Du kan ange direkt skrivarsökvägar för alla användare eller använda [Universal Print.](https://aka.ms/UPDocs)</span><span class="sxs-lookup"><span data-stu-id="99c94-133">You can provide direct printer paths for all users or use [Universal Print](https://aka.ms/UPDocs).</span></span>
