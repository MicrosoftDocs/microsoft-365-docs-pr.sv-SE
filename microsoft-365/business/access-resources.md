---
title: Få åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Lär dig hur du får tillgång till lokala resurser som line of Business-appar, filresurser och skrivare från en Azure Active Directory-ansluten Windows 10-enhet.
ms.openlocfilehash: fdc1eca6913ba6af4f6b65691fdee2165e7c827e
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/14/2019
ms.locfileid: "38323404"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="791b8-103">Få åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="791b8-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="791b8-104">Alla Windows 10-enheter som är anslutna till Azure Active Directory har åtkomst till alla molnbaserade resurser, till exempel Office 365-apparna, och kan skyddas av Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="791b8-104">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Office 365 apps, and can be protected by Microsoft 365 Business.</span></span> <span data-ttu-id="791b8-105">Du kan också tillåta åtkomst till lokala resurser som line of Business (LOB) appar, filresurser och skrivare.</span><span class="sxs-lookup"><span data-stu-id="791b8-105">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="791b8-106">Om du vill tillåta åtkomst använder [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) för att synkronisera din lokala Active Directory med Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="791b8-106">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="791b8-107">Mer information finns [i Introduktion till enhetshantering i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span><span class="sxs-lookup"><span data-stu-id="791b8-107">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="791b8-108">Stegen sammanfattas också i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="791b8-108">The steps are also summarized in the following sections.</span></span>

## <a name="run-azure-ad-connect"></a><span data-ttu-id="791b8-109">Kör Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="791b8-109">Run Azure AD Connect</span></span>

<span data-ttu-id="791b8-110">Slutför följande steg för att aktivera organisationens Azure AD-anslutna enheter för att komma åt lokala resurser.</span><span class="sxs-lookup"><span data-stu-id="791b8-110">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="791b8-111">Om du vill synkronisera dina användare, grupper och kontakter från lokala Active Directory till Azure Active Directory, kör guiden katalogsynkronisering och Azure AD Connect som beskrivs i [Konfigurera katalogsynkronisering för Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="791b8-111">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="791b8-112">När katalogsynkroniseringen är klar kontrollerar du att organisationens Windows 10-enheter är Azure AD-anslutna.</span><span class="sxs-lookup"><span data-stu-id="791b8-112">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="791b8-113">Det här steget görs individuellt på varje Windows 10-enhet.</span><span class="sxs-lookup"><span data-stu-id="791b8-113">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="791b8-114">Mer information finns [i Konfigurera Windows-enheter för Microsoft 365 företagsanvändare](set-up-windows-devices.md) .</span><span class="sxs-lookup"><span data-stu-id="791b8-114">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="791b8-115">När Windows 10-enheter är Azure AD-anslutna, måste varje användare starta om sina enheter och logga in med sina autentiseringsuppgifter för Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="791b8-115">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business credentials.</span></span> <span data-ttu-id="791b8-116">Alla enheter har nu även tillgång till lokala resurser.</span><span class="sxs-lookup"><span data-stu-id="791b8-116">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="791b8-117">Inga ytterligare steg krävs för att få åtkomst till lokala resurser för Azure AD-anslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="791b8-117">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="791b8-118">Den här funktionen är inbyggd i Windows 10.</span><span class="sxs-lookup"><span data-stu-id="791b8-118">This functionality is built into Windows 10.</span></span> 
  
<span data-ttu-id="791b8-119">Om din organisation inte är redo att distribuera i Azure AD-anslutna enhetskonfigurationen som beskrivs ovan, Överväg att konfigurera [hybrid Azure AD-ansluten enhetskonfiguration](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="791b8-119">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="791b8-120">Överväganden när du ansluter Windows-enheter till Azure AD</span><span class="sxs-lookup"><span data-stu-id="791b8-120">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="791b8-121">Om den Windows-enhet som du anslöt till Azure-AD tidigare var domänansluten eller i en arbetsgrupp bör du tänka på följande begränsningar:</span><span class="sxs-lookup"><span data-stu-id="791b8-121">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="791b8-122">När en enhet Azure AD ansluts skapar den en ny användare utan att referera till en befintlig profil.</span><span class="sxs-lookup"><span data-stu-id="791b8-122">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="791b8-123">Profiler måste migreras manuellt.</span><span class="sxs-lookup"><span data-stu-id="791b8-123">Profiles must be manually migrated.</span></span> <span data-ttu-id="791b8-124">En användarprofil innehåller information som favoriter, lokala filer, webbläsarinställningar och start-menyinställningar.</span><span class="sxs-lookup"><span data-stu-id="791b8-124">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="791b8-125">Ett bra sätt är att hitta ett verktyg från tredje part för att mappa befintliga filer och inställningar till den nya profilen.</span><span class="sxs-lookup"><span data-stu-id="791b8-125">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="791b8-126">Om enheten använder Grupprincip-objekt (GPO), kanske vissa grupprincipobjekt inte har en jämförbar [konfiguration tjänstprovider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) i Intune.</span><span class="sxs-lookup"><span data-stu-id="791b8-126">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="791b8-127">Kör [verktyget MMAT](https://www.microsoft.com/download/details.aspx?id=45520) för att hitta jämförbara kryptografiproviders för befintliga grupprincipobjekt.</span><span class="sxs-lookup"><span data-stu-id="791b8-127">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="791b8-128">Användare kan inte autentisera till program som är beroende av Active Directory-autentisering.</span><span class="sxs-lookup"><span data-stu-id="791b8-128">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="791b8-129">Utvärdera äldre app och Överväg att uppdatera till en app som använder modern auth, om möjligt.</span><span class="sxs-lookup"><span data-stu-id="791b8-129">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="791b8-130">Identifiering av Active Directory-skrivare fungerar inte.</span><span class="sxs-lookup"><span data-stu-id="791b8-130">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="791b8-131">Du kan ange direkta skrivar Sök vägar för alla användare eller använda [hybrid molnutskrift](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span><span class="sxs-lookup"><span data-stu-id="791b8-131">You can provide direct printer paths for all users or use [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
