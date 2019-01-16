---
title: Åtkomst på lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Lär dig att få åtkomst till lokala resurser som Line Of Business apps, filresurser och skrivare från en Azure Active Directory ingår Windows 10-enhet.
ms.openlocfilehash: 0a5d4b0828888fcb99676223000c446479f84ddc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982259"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="76762-103">Åtkomst på lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="76762-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="76762-p101">Alla Windows 10-enheter som är Azure Active Directory ansluten ska ha tillgång till alla cloud-baserade resurser som Office 365-appar och kan vara skyddat av Microsoft 365 Business. Också att få åtkomst till lokala resurser som raden av Business (LOB) apps, filresurser och skrivare måste du synkronisera lokal Active Directory med Azure Active Directory med [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). Finns i [Introduktion till hantering av enheter i Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) mer.</span><span class="sxs-lookup"><span data-stu-id="76762-p101">Any Windows 10 device that is Azure Active Directory joined will have access to all cloud-based resources such as your Office 365 apps and can be protected by Microsoft 365 Business. To also allow access to on-premises resources like Line Of Business (LOB) apps, file shares, and printers, you must synchronize your on-premises Active Directory with Azure Active Directory by using [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). See [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) to learn more.</span></span> 
  
## <a name="run-azure-ad-connect"></a><span data-ttu-id="76762-107">Kör Azure AD Anslut</span><span class="sxs-lookup"><span data-stu-id="76762-107">Run Azure AD Connect</span></span>

<span data-ttu-id="76762-108">Utför följande steg om du vill aktivera organisationen Azure AD anslutna enheter åtkomst till lokala resurser.</span><span class="sxs-lookup"><span data-stu-id="76762-108">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="76762-109">Om du vill synkronisera dina användare, grupper och kontakter från lokal Active Directory till Azure Active Directory, kör du guiden för Directory-synkroniseringen och Azure AD Anslut som beskrivs i [Konfigurera katalogsynkronisering för Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="76762-109">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="76762-p102">När directory-synkroniseringen har slutförts kontrollera företagets Windows 10-enheter Azure AD ansluten. Detta görs individuellt på varje Windows 10-enhet. Mer information finns i [ställa in Windows-enheter för Microsoft 365 företagsanvändare](set-up-windows-devices.md) .</span><span class="sxs-lookup"><span data-stu-id="76762-p102">After the directory synchronization has completed, make sure your organization's Windows 10 devices are Azure AD joined. This step is done individually on each Windows 10 device. See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="76762-p103">När Windows 10-enheter Azure AD ansluten, bör varje användare starta om sina enheter och loggar in med sina Microsoft 365 Business-autentiseringsuppgifter. Alla enheter har nu åtkomst till lokala resurser samt.</span><span class="sxs-lookup"><span data-stu-id="76762-p103">Once the Windows 10 devices are Azure AD joined, each user should reboot their devices and login with their Microsoft 365 Business credentials. All devices will now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="76762-p104">Inga ytterligare åtgärder krävs för att få åtkomst till lokala resurser för Azure AD anslutna enheter. Detta är inbyggda funktioner som är tillgängliga i Windows 10.</span><span class="sxs-lookup"><span data-stu-id="76762-p104">No additional steps are required to get access to on-premise resources for Azure AD joined devices. This is built-in functionality available in Windows 10.</span></span> 
  
<span data-ttu-id="76762-117">Om din organisation inte är redo att distribuera i Azure AD anslutna enhetens konfiguration ovan nätverksdrivrutinernas [konfiguration av Hybrid Azure AD ansluten enhet](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="76762-117">If your organization is not ready to deploy in the Azure AD Joined Device Configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a><span data-ttu-id="76762-118">Att tänka på när du ansluter till Windows-enheter till Azure AD</span><span class="sxs-lookup"><span data-stu-id="76762-118">Considerations when joining your Windows devices to Azure AD</span></span>

<span data-ttu-id="76762-119">Om du är Azure AD ansluta till en Windows-enhet som tidigare har anslutit till domänen eller i en arbetsgrupp måste du beakta följande begränsningar:</span><span class="sxs-lookup"><span data-stu-id="76762-119">If you are Azure AD joining a Windows device that has previously been domain-joined or in a workgroup, you need to consider the following limitations:</span></span>
  
- <span data-ttu-id="76762-p105">När en enhet Azure AD ansluter till, skapar en ny användare utan hänvisar till en befintlig profil. Lös problemet behöver profiler migreras manuellt. En användarprofil innehåller information, till exempel Favoriter, lokala filer, webbläsarinställningar, inställningar för Start-menyn, etc. Bästa metoden är att hitta ett tredjepartsverktyg för att mappa befintliga filer och inställningar till den nya profilen</span><span class="sxs-lookup"><span data-stu-id="76762-p105">When a device Azure AD joins, it creates a new user without referencing an existing profile. To fix this, profiles need to be manually migrated. A user profile contains information like favorites, local files, browser settings, Start menu settings, etc. A best approach is to find a third-party tool to map existing files and settings to the new profile</span></span>
    
- <span data-ttu-id="76762-p106">Om enheten använder grupprincip-objekt (GPO), kan vissa grupprincipobjekt inte har en jämförbar [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) i Intune. Kör [verktyget MMAT](https://www.microsoft.com/download/details.aspx?id=45520) för att hitta jämförbara kryptografiproviders för befintliga grupprincipobjekt.</span><span class="sxs-lookup"><span data-stu-id="76762-p106">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune. Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span> 
    
- <span data-ttu-id="76762-p107">Användare kommer inte att kunna autentisera till program som bygger på Active Directory-autentisering. För att bekämpa utvärdera med hjälp av en äldre app och överväga en uppdatering till en app som använder moderna autentisering om det är möjligt.</span><span class="sxs-lookup"><span data-stu-id="76762-p107">Users will not be able to authenticate to applications that depend on Active Directory authentication. To deal with this evaluate using a legacy app and consider updating to an app that uses modern Auth if possible.</span></span>
    
- <span data-ttu-id="76762-p108">Identifiering av Active Directory skrivaren fungerar inte. Ge alla användare direkt Skrivarsökvägar eller utnyttja [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)åtgärda detta.</span><span class="sxs-lookup"><span data-stu-id="76762-p108">Active Directory printer discovery will not work. To fix this, provide direct printer paths for all users or leverage [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
    

