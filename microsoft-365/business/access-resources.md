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
description: Lär dig hur du får åtkomst till lokala resurser som affärsappar, filresurser och skrivare från en Azure Active Directory-ansluten till Windows 10-enhet.
ms.openlocfilehash: 9615ecc9469992d3e5a7479f4799c610db11fb41
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471260"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="c3a15-103">Få åtkomst till lokala resurser från en Azure AD-ansluten enhet i Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="c3a15-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="c3a15-104">Den här artikeln gäller Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="c3a15-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="c3a15-105">Alla Windows 10-enheter som är Azure Active Directory-anslutna har åtkomst till alla molnbaserade resurser, till exempel dina Microsoft 365-appar, och kan skyddas av Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="c3a15-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="c3a15-106">Du kan också tillåta åtkomst till lokala resurser som LOB-appar (line of business), filresurser och skrivare.</span><span class="sxs-lookup"><span data-stu-id="c3a15-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="c3a15-107">Om du vill tillåta åtkomst använder du [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) för att synkronisera din lokala Active Directory med Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c3a15-107">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="c3a15-108">Mer information finns [i Introduktion till enhetshantering i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span><span class="sxs-lookup"><span data-stu-id="c3a15-108">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="c3a15-109">Stegen sammanfattas också i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="c3a15-109">The steps are also summarized in the following sections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3a15-110">Den här proceduren är endast tillämplig på OAuth och NTLM.</span><span class="sxs-lookup"><span data-stu-id="c3a15-110">This procedure is only applicable to OAuth and NTLM.</span></span> <span data-ttu-id="c3a15-111">Kerberos stöds inte.</span><span class="sxs-lookup"><span data-stu-id="c3a15-111">Kerberos is not supported.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="c3a15-112">Kör Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="c3a15-112">Run Azure AD Connect</span></span>

<span data-ttu-id="c3a15-113">Slutför följande steg för att aktivera organisationens Azure AD-anslutna enheter för åtkomst till lokala resurser.</span><span class="sxs-lookup"><span data-stu-id="c3a15-113">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="c3a15-114">Om du vill synkronisera användare, grupper och kontakter från lokal Active Directory till Azure Active Directory kör du katalogsynkroniseringsguiden och Azure AD Connect enligt beskrivningen i [Konfigurera katalogsynkronisering för Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="c3a15-114">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span>
    
2. <span data-ttu-id="c3a15-115">När katalogsynkroniseringen är klar kontrollerar du att organisationens Windows 10-enheter är Azure AD-anslutna.</span><span class="sxs-lookup"><span data-stu-id="c3a15-115">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="c3a15-116">Det här steget görs individuellt på varje Windows 10-enhet.</span><span class="sxs-lookup"><span data-stu-id="c3a15-116">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="c3a15-117">Mer information finns [i Konfigurera Windows-enheter för Microsoft 365 Business Premium-användare.](set-up-windows-devices.md)</span><span class="sxs-lookup"><span data-stu-id="c3a15-117">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="c3a15-118">När Windows 10-enheterna är Azure AD-anslutna måste varje användare starta om sina enheter och logga in med sina Microsoft 365 Business Premium-autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="c3a15-118">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="c3a15-119">Alla enheter har nu också tillgång till lokala resurser.</span><span class="sxs-lookup"><span data-stu-id="c3a15-119">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="c3a15-120">Inga ytterligare steg krävs för att få åtkomst till lokala resurser för Azure AD-anslutna enheter.</span><span class="sxs-lookup"><span data-stu-id="c3a15-120">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="c3a15-121">Den här funktionen är inbyggd i Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c3a15-121">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="c3a15-122">Om du har planer på att logga in på AADJ-enheten än lösenordsmetod som PIN/Bio-metriska via WHFB-inloggning och sedan komma åt lokala resurser (resurser, skrivare.. etc.), följhttps://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="c3a15-122">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="c3a15-123">Om din organisation inte är redo att distribuera i azure AD-anslutna enhetskonfiguration som beskrivs ovan kan du överväga att konfigurera [hybrid Azure AD-enhetskonfiguration](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="c3a15-123">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="c3a15-124">Överväganden när du ansluter till Windows-enheter till Azure AD</span><span class="sxs-lookup"><span data-stu-id="c3a15-124">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="c3a15-125">Om Windows-enheten som du Azure-AD gick med i tidigare var domänansluten eller i en arbetsgrupp bör du tänka på följande begränsningar:</span><span class="sxs-lookup"><span data-stu-id="c3a15-125">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="c3a15-126">När en enhet Som Azure AD ansluter skapas en ny användare utan att referera till en befintlig profil.</span><span class="sxs-lookup"><span data-stu-id="c3a15-126">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="c3a15-127">Profiler måste migreras manuellt.</span><span class="sxs-lookup"><span data-stu-id="c3a15-127">Profiles must be manually migrated.</span></span> <span data-ttu-id="c3a15-128">En användarprofil innehåller information som favoriter, lokala filer, webbläsarinställningar och Inställningar för Start-menyn.</span><span class="sxs-lookup"><span data-stu-id="c3a15-128">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="c3a15-129">Ett bra sätt är att hitta ett verktyg från tredje part för att mappa befintliga filer och inställningar till den nya profilen.</span><span class="sxs-lookup"><span data-stu-id="c3a15-129">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="c3a15-130">Om enheten använder grupprincipobjekt (GPO) kanske vissa grupprincipobjekt inte har en jämförbar [CSP (Configuration Service Provider)](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) i Intune.</span><span class="sxs-lookup"><span data-stu-id="c3a15-130">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="c3a15-131">Kör [MMAT-verktyget](https://www.microsoft.com/download/details.aspx?id=45520) för att hitta jämförbara CSP:er för befintliga grupprincipobjekt.</span><span class="sxs-lookup"><span data-stu-id="c3a15-131">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="c3a15-132">Användare kan inte autentisera till program som är beroende av Active Directory-autentisering.</span><span class="sxs-lookup"><span data-stu-id="c3a15-132">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="c3a15-133">Utvärdera den äldre appen och överväg att uppdatera till en app som använder moderna Auth, om möjligt.</span><span class="sxs-lookup"><span data-stu-id="c3a15-133">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="c3a15-134">Identifiering av Active Directory-skrivare fungerar inte.</span><span class="sxs-lookup"><span data-stu-id="c3a15-134">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="c3a15-135">Du kan ange direkta skrivarsökvägar för alla användare eller använda [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span><span class="sxs-lookup"><span data-stu-id="c3a15-135">You can provide direct printer paths for all users or use [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
