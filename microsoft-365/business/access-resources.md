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
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Lär dig hur du får tillgång till lokala resurser som line of Business-appar, filresurser och skrivare från en Azure Active Directory-ansluten Windows 10-enhet.
ms.openlocfilehash: ab9049e78617372463b8446dc8f8bc0089d8c117
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981670"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="81f77-103">Få åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="81f77-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="81f77-104">Alla Windows 10-enheter som är anslutna till Azure Active Directory har åtkomst till alla molnbaserade resurser som dina Office 365-appar och kan skyddas av Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="81f77-104">Any Windows 10 device that is Azure Active Directory joined will have access to all cloud-based resources such as your Office 365 apps and can be protected by Microsoft 365 Business.</span></span> <span data-ttu-id="81f77-105">Om du även vill tillåta åtkomst till lokala resurser som line of Business (LOB) appar, filresurser och skrivare, måste du synkronisera din lokala Active Directory med Azure Active Directory med hjälp av [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="81f77-105">To also allow access to on-premises resources like Line Of Business (LOB) apps, file shares, and printers, you must synchronize your on-premises Active Directory with Azure Active Directory by using [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span></span> <span data-ttu-id="81f77-106">I följande video beskrivs stegen för hur du ställer in detta för det vanligaste scenariot.</span><span class="sxs-lookup"><span data-stu-id="81f77-106">The following video details the steps for how to set this up for the most common scenario.</span></span>
 
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]

<span data-ttu-id="81f77-107">Mer information finns [i Introduktion till enhetshantering i Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) .</span><span class="sxs-lookup"><span data-stu-id="81f77-107">See [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) to learn more.</span></span>
<span data-ttu-id="81f77-108">Stegen sammanfattas också i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="81f77-108">The steps are also summarized in the following sections.</span></span>

## <a name="run-azure-ad-connect"></a><span data-ttu-id="81f77-109">Kör Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="81f77-109">Run Azure AD Connect</span></span>

<span data-ttu-id="81f77-110">Slutför följande steg för att aktivera organisationens Azure AD-anslutna enheter för att komma åt lokala resurser.</span><span class="sxs-lookup"><span data-stu-id="81f77-110">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="81f77-111">Om du vill synkronisera dina användare, grupper och kontakter från lokala Active Directory till Azure Active Directory, kör guiden katalogsynkronisering och Azure AD Connect som beskrivs i [Konfigurera katalogsynkronisering för Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="81f77-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="81f77-112">När katalogsynkroniseringen har slutförts kontrollerar du att organisationens Windows 10-enheter är Azure AD-anslutna.</span><span class="sxs-lookup"><span data-stu-id="81f77-112">After the directory synchronization has completed, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="81f77-113">Det här steget görs individuellt på varje Windows 10-enhet.</span><span class="sxs-lookup"><span data-stu-id="81f77-113">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="81f77-114">Mer information finns [i Konfigurera Windows-enheter för Microsoft 365 företagsanvändare](set-up-windows-devices.md) .</span><span class="sxs-lookup"><span data-stu-id="81f77-114">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="81f77-115">När Windows 10-enheter är Azure AD-anslutna, bör varje användare starta om sina enheter och logga in med sina Microsoft 365 Business autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="81f77-115">Once the Windows 10 devices are Azure AD joined, each user should reboot their devices and login with their Microsoft 365 Business credentials.</span></span> <span data-ttu-id="81f77-116">Alla enheter har nu även tillgång till lokala resurser.</span><span class="sxs-lookup"><span data-stu-id="81f77-116">All devices will now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="81f77-117">Inga ytterligare steg krävs för att få åtkomst till lokala resurser för Azure AD-anslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="81f77-117">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="81f77-118">Detta är inbyggda funktioner som är tillgängliga i Windows 10.</span><span class="sxs-lookup"><span data-stu-id="81f77-118">This is built-in functionality available in Windows 10.</span></span> 
  
<span data-ttu-id="81f77-119">Om din organisation inte är redo att distribuera i Azure AD-anslutna enhetskonfigurationen som beskrivs ovan, Överväg att konfigurera [hybrid Azure AD-ansluten enhetskonfiguration](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="81f77-119">If your organization is not ready to deploy in the Azure AD Joined Device Configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a><span data-ttu-id="81f77-120">Överväganden när du ansluter dina Windows-enheter till Azure AD</span><span class="sxs-lookup"><span data-stu-id="81f77-120">Considerations when joining your Windows devices to Azure AD</span></span>

<span data-ttu-id="81f77-121">Om du är Azure AD som ansluter till en Windows-enhet som tidigare har domänanslutna eller i en arbetsgrupp, måste du överväga följande begränsningar:</span><span class="sxs-lookup"><span data-stu-id="81f77-121">If you are Azure AD joining a Windows device that has previously been domain-joined or in a workgroup, you need to consider the following limitations:</span></span>
  
- <span data-ttu-id="81f77-122">När en enhet Azure AD ansluts skapar den en ny användare utan att referera till en befintlig profil.</span><span class="sxs-lookup"><span data-stu-id="81f77-122">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="81f77-123">För att åtgärda detta måste profilerna migreras manuellt.</span><span class="sxs-lookup"><span data-stu-id="81f77-123">To fix this, profiles need to be manually migrated.</span></span> <span data-ttu-id="81f77-124">En användarprofil innehåller information som favoriter, lokala filer, webbläsarinställningar, start-menyinställningar osv. Ett bra sätt är att hitta ett verktyg från tredje part för att mappa befintliga filer och inställningar till den nya profilen</span><span class="sxs-lookup"><span data-stu-id="81f77-124">A user profile contains information like favorites, local files, browser settings, Start menu settings, etc. A best approach is to find a third-party tool to map existing files and settings to the new profile</span></span>

- <span data-ttu-id="81f77-125">Om enheten använder Grupprincip-objekt (GPO), kanske vissa grupprincipobjekt inte har en jämförbar [konfiguration tjänstprovider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) i Intune.</span><span class="sxs-lookup"><span data-stu-id="81f77-125">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="81f77-126">Kör [verktyget MMAT](https://www.microsoft.com/download/details.aspx?id=45520) för att hitta jämförbara kryptografiproviders för befintliga grupprincipobjekt.</span><span class="sxs-lookup"><span data-stu-id="81f77-126">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="81f77-127">Användare kommer inte att kunna autentisera till program som är beroende av Active Directory-autentisering.</span><span class="sxs-lookup"><span data-stu-id="81f77-127">Users will not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="81f77-128">För att hantera den här utvärderingen med hjälp av en äldre app och Överväg att uppdatera till en app som använder modern auth om möjligt.</span><span class="sxs-lookup"><span data-stu-id="81f77-128">To deal with this evaluate using a legacy app and consider updating to an app that uses modern Auth if possible.</span></span>

- <span data-ttu-id="81f77-129">Identifiering av Active Directory-skrivare fungerar inte.</span><span class="sxs-lookup"><span data-stu-id="81f77-129">Active Directory printer discovery will not work.</span></span> <span data-ttu-id="81f77-130">Åtgärda detta genom att tillhandahålla direkta skrivar Sök vägar för alla användare eller utnyttja [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span><span class="sxs-lookup"><span data-stu-id="81f77-130">To fix this, provide direct printer paths for all users or leverage [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
