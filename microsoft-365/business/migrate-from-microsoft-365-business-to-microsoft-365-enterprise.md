---
title: Migrera från Microsoft 365 Business till Microsoft 365 E3
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Lär dig hur du flyttar företaget från Microsoft 365 Business Premium till Microsoft 365 E3.
ms.openlocfilehash: 10630671f3deb7eff0ad0f601d301b90743ee35f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164522"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a><span data-ttu-id="4f88b-103">Migrera från Microsoft 365 Business Premium till Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="4f88b-103">Migrate from Microsoft 365 Business Premium to Microsoft 365 E3</span></span>

<span data-ttu-id="4f88b-104">Microsoft 365 Business Premium har allt du behöver för ditt småföretag. Kombinera de förstklassiga molnbaserade produktivitetsapparna med enkel enhetshantering och säkerhet som gör det möjligt för dina anställda att arbeta på bästa sätt.</span><span class="sxs-lookup"><span data-stu-id="4f88b-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="4f88b-105">I vissa fall kan du emellertid behöva migrera din prenumeration Microsoft 365 Business Premium till Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="4f88b-105">In some cases, however, you may need to migrate your Microsoft 365 Business Premium subscription to Microsoft 365 E3.</span></span> 

<span data-ttu-id="4f88b-106">Företaget har till exempel vuxit och behöver fler än 300 licenser (grattis).</span><span class="sxs-lookup"><span data-stu-id="4f88b-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="4f88b-107">Eller, ditt företag behöver företagsfunktioner, som Microsoft 365-appar för företag, Windows 10 Enterprise E3 eller CALs (Enterprise Client Access Licenses).</span><span class="sxs-lookup"><span data-stu-id="4f88b-107">Or, your business needs enterprise features, such as Microsoft 365 Apps for enterprise, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="4f88b-108">Det är enkelt att uppgradera: du kan [starta uppgraderingen från administrationscentret.](../commerce/subscriptions/upgrade-to-different-plan.md)</span><span class="sxs-lookup"><span data-stu-id="4f88b-108">Upgrading is easy: you can start the upgrade [from the Admin center](../commerce/subscriptions/upgrade-to-different-plan.md).</span></span> <span data-ttu-id="4f88b-109">Alla data och konfigurationer i din nuvarande prenumeration behålls.</span><span class="sxs-lookup"><span data-stu-id="4f88b-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="4f88b-110">Du behöver inte förbereda dig för migreringen utan att göra något efteråt, förutom att dra nytta av de nya funktionerna.</span><span class="sxs-lookup"><span data-stu-id="4f88b-110">There's nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span>

>[!Note]
><span data-ttu-id="4f88b-111">Du kan också använda en Microsoft 365 Business Premium-prenumeration för upp till 300 platser och få en Microsoft 365 E3-prenumeration för fler än 300 platser.</span><span class="sxs-lookup"><span data-stu-id="4f88b-111">You can also use a Microsoft 365 Business Premium subscription for up to 300 seats and get a Microsoft 365 E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="4f88b-112">Men Microsoft Defender för Office 365 ingår inte i Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="4f88b-112">However, Microsoft Defender for Office 365 is not included with Microsoft 365 E3.</span></span> <span data-ttu-id="4f88b-113">För fortsatt skydd mot hot bör du lägga till ytterligare Defender för Office 365-licenser så att alla användare som omfattas av Defender för Office 365-säkerhet är licensierade.</span><span class="sxs-lookup"><span data-stu-id="4f88b-113">For continued threat protection, you should add additional Defender for Office 365 licenses so that all of the users in scope of your Defender for Office 365 polices are licensed.</span></span>
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a><span data-ttu-id="4f88b-114">Skillnader mellan Microsoft 365 Business Premium och Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4f88b-114">Differences between Microsoft 365 Business Premium and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="4f88b-115">I den här tabellen visas skillnaderna mellan Microsoft 365 Business Premium och Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="4f88b-115">This table shows the differences between Microsoft 365 Business Premium and Microsoft 365 E3.</span></span>

| <span data-ttu-id="4f88b-116">Funktion</span><span class="sxs-lookup"><span data-stu-id="4f88b-116">Feature</span></span>    | <span data-ttu-id="4f88b-117">Support i Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="4f88b-117">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="4f88b-118">Support i Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="4f88b-118">Support in Microsoft 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="4f88b-119">**Lokalt**</span><span class="sxs-lookup"><span data-stu-id="4f88b-119">**On-premises**</span></span>        | | | 
| <span data-ttu-id="4f88b-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="4f88b-120">Windows 10</span></span>    | <span data-ttu-id="4f88b-121">Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="4f88b-121">Windows 10 Business</span></span>  |     <span data-ttu-id="4f88b-122">Windows 10 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="4f88b-122">Windows 10 Enterprise E3</span></span>| 
| <span data-ttu-id="4f88b-123">Office appar\*</span><span class="sxs-lookup"><span data-stu-id="4f88b-123">Office apps\*</span></span>    | [<span data-ttu-id="4f88b-124">Microsoft 365-applikationer för affärsverksamhet</span><span class="sxs-lookup"><span data-stu-id="4f88b-124">Microsoft 365 Apps for business</span></span>](#office-365-business)    | <span data-ttu-id="4f88b-125"> Microsoft 365 Apps för företag</span><span class="sxs-lookup"><span data-stu-id="4f88b-125">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="4f88b-126">**Produktivitetsprogram för molnet**</span><span class="sxs-lookup"><span data-stu-id="4f88b-126">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="4f88b-127">Exchange Online och Outlook</span><span class="sxs-lookup"><span data-stu-id="4f88b-127">Exchange Online and Outlook</span></span>    | <span data-ttu-id="4f88b-128">50 GB lagringsutrymme per postlåda och obegränsat Exchange Online arkivering</span><span class="sxs-lookup"><span data-stu-id="4f88b-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>    | <span data-ttu-id="4f88b-129">100 GB lagringsutrymme per postlåda och obegränsat Exchange Online arkivering</span><span class="sxs-lookup"><span data-stu-id="4f88b-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="4f88b-130">Teams</span><span class="sxs-lookup"><span data-stu-id="4f88b-130">Teams</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="4f88b-133">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="4f88b-133">OneDrive for Business</span></span>    | <span data-ttu-id="4f88b-134">1 TB lagringsgräns per användare</span><span class="sxs-lookup"><span data-stu-id="4f88b-134">1 TB storage limit per user</span></span>    | <span data-ttu-id="4f88b-135">Obegränsat</span><span class="sxs-lookup"><span data-stu-id="4f88b-135">Unlimited</span></span> | 
| <span data-ttu-id="4f88b-136">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="4f88b-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="4f88b-139">**Skydd mot hot**</span><span class="sxs-lookup"><span data-stu-id="4f88b-139">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="4f88b-140">Funktioner för att minska attackytan</span><span class="sxs-lookup"><span data-stu-id="4f88b-140">Attack surface reduction capabilities</span></span>    | [<span data-ttu-id="4f88b-141">Visa den här listan</span><span class="sxs-lookup"><span data-stu-id="4f88b-141">See this list</span></span>](#threat-protection) | <span data-ttu-id="4f88b-142">Företagshantering av maskinvarubaserad avgränsning för Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4f88b-142">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> | 
| <span data-ttu-id="4f88b-143">Microsoft Defender för Office 365 Abonnemang 1</span><span class="sxs-lookup"><span data-stu-id="4f88b-143">Defender for Office 365 Plan 1</span></span> | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | <span data-ttu-id="4f88b-145">Ingår inte men kan läggas till på</span><span class="sxs-lookup"><span data-stu-id="4f88b-145">Not included, but can be added on</span></span> | 
| <span data-ttu-id="4f88b-146">**Identitetshantering**</span><span class="sxs-lookup"><span data-stu-id="4f88b-146">**Identity management**</span></span>        | | | 
| <span data-ttu-id="4f88b-147">Självbetjäning för återställning av lösenord för hybridkonton för Azure Active Directory (Azure AD), Azure AD-multifaktorautentisering (MFA), villkorsstyrd åtkomst, tillbakaskrivning av lösenord för lokala identiteter</span><span class="sxs-lookup"><span data-stu-id="4f88b-147">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="4f88b-150">Identifiering av molnapp, Azure AD Anslut hälsa</span><span class="sxs-lookup"><span data-stu-id="4f88b-150">Cloud App Discovery, Azure AD Connect Health</span></span>    |     | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="4f88b-152">Azure AD Office 365-appar Enkel inloggning Sign-On (SSO): 10 program per användare (SaaS-galleriappar som Salesforce)\*</span><span class="sxs-lookup"><span data-stu-id="4f88b-152">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="4f88b-155">Azure AD Premium 1 SSO: ingen gräns (lokala appar via Azure AD-programproxy och appar som inte är galleribaserade med hjälp Self-Service mallar för appintegrering)</span><span class="sxs-lookup"><span data-stu-id="4f88b-155">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>    |     | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="4f88b-157">**Enhets- och apphantering**</span><span class="sxs-lookup"><span data-stu-id="4f88b-157">**Device and app management**</span></span>        | | | 
| <span data-ttu-id="4f88b-158">Microsoft Intune, Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="4f88b-158">Microsoft Intune, Windows Autopilot</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
|<span data-ttu-id="4f88b-161">Virtual Desktop Access (VDA)</span><span class="sxs-lookup"><span data-stu-id="4f88b-161">Virtual Desktop Access (VDA)</span></span>    |  |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
|<span data-ttu-id="4f88b-163">Windows Virtuellt skrivbord (WVD)</span><span class="sxs-lookup"><span data-stu-id="4f88b-163">Windows Virtual Desktop (WVD)</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png) |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
|<span data-ttu-id="4f88b-166">Aktivering av delad dator (SCA)</span><span class="sxs-lookup"><span data-stu-id="4f88b-166">Shared Computer Activation (SCA)</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png) |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="4f88b-169">Microsofts paket för skrivbordsoptimering</span><span class="sxs-lookup"><span data-stu-id="4f88b-169">Microsoft Desktop Optimization Package</span></span>    | |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="4f88b-171">**Informationsskydd**</span><span class="sxs-lookup"><span data-stu-id="4f88b-171">**Information protection**</span></span>        | | | 
| <span data-ttu-id="4f88b-172">Office 365 Dataförlustskydd, Azure Information Protection Plan 1</span><span class="sxs-lookup"><span data-stu-id="4f88b-172">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="4f88b-175">Fönsterinformationsskydd för slutpunkt DLP</span><span class="sxs-lookup"><span data-stu-id="4f88b-175">Window Information Protection for endpoint DLP</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="4f88b-178">**Klientåtkomstlicens (CAL-rättigheter)**</span><span class="sxs-lookup"><span data-stu-id="4f88b-178">**Client Access License (CAL rights)**</span></span>    | | |     
| <span data-ttu-id="4f88b-179">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span><span class="sxs-lookup"><span data-stu-id="4f88b-179">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span></span>| |         ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="4f88b-181">**Efterlevnad**</span><span class="sxs-lookup"><span data-stu-id="4f88b-181">**Compliance**</span></span>        | | | 
| <span data-ttu-id="4f88b-182">Obegränsad e-postarkivering</span><span class="sxs-lookup"><span data-stu-id="4f88b-182">Unlimited email archiving</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="4f88b-185">Efterlevnadshanteraren</span><span class="sxs-lookup"><span data-stu-id="4f88b-185">Compliance Manager</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="4f88b-188">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="4f88b-188">eDiscovery</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="4f88b-191">Bevarande av juridiska skäl på plats och bevarande av juridiska skäl</span><span class="sxs-lookup"><span data-stu-id="4f88b-191">In-place hold and litigation hold</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="4f88b-194">Bevarandetaggar (MRM) för hantering av meddelandeposter (MRM) och bevarandeprinciper</span><span class="sxs-lookup"><span data-stu-id="4f88b-194">Messaging Records Management (MRM) retention tags and retention policies</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
||||

<span data-ttu-id="4f88b-197">\* Användare som har tilldelats åtkomst till SaaS-appar kan få SSO-åtkomst till upp till 10 appar.</span><span class="sxs-lookup"><span data-stu-id="4f88b-197">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="4f88b-198">Administratörer kan konfigurera SSO och ändra användaråtkomst till olika SaaS-appar, men SSO-åtkomst är endast tillåten för 10 appar per användare i taget.</span><span class="sxs-lookup"><span data-stu-id="4f88b-198">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="4f88b-199">Alla Office 365 räknas som en enskild app.</span><span class="sxs-lookup"><span data-stu-id="4f88b-199">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="4f88b-200">Migrering</span><span class="sxs-lookup"><span data-stu-id="4f88b-200">Migration</span></span>

<span data-ttu-id="4f88b-201">Migrera genom att samarbeta med din partner för att flytta din Microsoft 365 Business Premium-prenumeration och licenser till ett lämpligt Microsoft 365 E3-abonnemang med dess licenser.</span><span class="sxs-lookup"><span data-stu-id="4f88b-201">To migrate, work with your partner to move your Microsoft 365 Business Premium subscription and licenses to a suitable Microsoft 365 E3 subscription with its licenses.</span></span>

<span data-ttu-id="4f88b-202">I följande avsnitt beskrivs vilka ändringar du behöver göra, om det finns några, och vad du kan göra efter migreringen.</span><span class="sxs-lookup"><span data-stu-id="4f88b-202">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="4f88b-203">Microsoft 365 prenumerationskonfiguration och data</span><span class="sxs-lookup"><span data-stu-id="4f88b-203">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="4f88b-204">Du behöver inte göra några ändringar i din nuvarande prenumeration eller dina data innan du migrerar, vilket omfattar:</span><span class="sxs-lookup"><span data-stu-id="4f88b-204">You don't need to make any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="4f88b-205">Prenumerationskonfiguration, till exempel DNS-domännamn.</span><span class="sxs-lookup"><span data-stu-id="4f88b-205">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="4f88b-206">Användar- och gruppkonton och autentiseringsinställningar, till exempel principer för multifaktorautentisering eller villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="4f88b-206">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="4f88b-207">Produktivitetstjänstkonfigurationer och deras data, till exempel Teams, Exchange Online postlådor, SharePoint Online-webbplatser, OneDrive för företag-mappar och OneNote-anteckningsböcker.</span><span class="sxs-lookup"><span data-stu-id="4f88b-207">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="4f88b-208">Användarna kan nu använda obegränsat lagringsutrymme i Exchange Online postlådor och OneDrive för företag mappar.</span><span class="sxs-lookup"><span data-stu-id="4f88b-208">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="4f88b-209">Du kan börja använda Cloud App Discovery, Azure AD Anslut Health och SSO för fler än 10 appar.</span><span class="sxs-lookup"><span data-stu-id="4f88b-209">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="4f88b-210">Skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="4f88b-210">Threat protection</span></span>

<span data-ttu-id="4f88b-211">Windows 10 Business omfattar följande skydd:</span><span class="sxs-lookup"><span data-stu-id="4f88b-211">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="4f88b-212">Tvingande integritet för operativsystemets uppstartsprocess</span><span class="sxs-lookup"><span data-stu-id="4f88b-212">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="4f88b-213">Tvingande integritet för känsliga operativsystemkomponenter</span><span class="sxs-lookup"><span data-stu-id="4f88b-213">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="4f88b-214">Avancerade sårbarheter och nolldagars minskningar av sårbarheter</span><span class="sxs-lookup"><span data-stu-id="4f88b-214">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="4f88b-215">Ryktesbaserat nätverksskydd för Microsoft Edge, Internet Explorer och Chrome</span><span class="sxs-lookup"><span data-stu-id="4f88b-215">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="4f88b-216">Värdbaserad brandvägg</span><span class="sxs-lookup"><span data-stu-id="4f88b-216">Host-based firewall</span></span>
- <span data-ttu-id="4f88b-217">Minskning av utpressningstrojaner</span><span class="sxs-lookup"><span data-stu-id="4f88b-217">Ransomware mitigations</span></span>
- <span data-ttu-id="4f88b-218">Maskinvarubaserad avgränsning för Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4f88b-218">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="4f88b-219">Programkontroll som drivs av intelligent Graph</span><span class="sxs-lookup"><span data-stu-id="4f88b-219">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="4f88b-220">Enhetskontroll (USB)</span><span class="sxs-lookup"><span data-stu-id="4f88b-220">Device control (USB)</span></span>
- <span data-ttu-id="4f88b-221">Nätverksskydd för webbaserade hot</span><span class="sxs-lookup"><span data-stu-id="4f88b-221">Network protection for web-based threats</span></span>
- <span data-ttu-id="4f88b-222">Skydd mot intrång i värden</span><span class="sxs-lookup"><span data-stu-id="4f88b-222">Host intrusion prevention rules</span></span>

<span data-ttu-id="4f88b-223">Windows 10 Enterprise E3 innehåller även företagshantering av maskinvarubaserad avgränsning för Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="4f88b-223">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

>[!Note]
><span data-ttu-id="4f88b-224">Användare som migreras till Microsoft 365 E3 måste ha en Microsoft Defender för Office 365 licens för fortsatt skydd mot hot.</span><span class="sxs-lookup"><span data-stu-id="4f88b-224">Users migrated to Microsoft 365 E3 will each require a Microsoft Defender for Office 365 license for continued threat protection.</span></span> <span data-ttu-id="4f88b-225">Se till att köpa ytterligare Defender Office 365 licens så att alla användare som omfattas av Defender för Office 365 licensieras.</span><span class="sxs-lookup"><span data-stu-id="4f88b-225">Be sure to purchase additional Defender for Office 365 licenses so that all of the users in scope of your Defender for Office 365 polices are licensed.</span></span> 
>

### <a name="device-management-with-intune"></a><span data-ttu-id="4f88b-226">Enhetshantering med Intune</span><span class="sxs-lookup"><span data-stu-id="4f88b-226">Device management with Intune</span></span>

<span data-ttu-id="4f88b-227">Du behöver inte göra några ändringar i din aktuella Intune-konfiguration innan du migrerar, vilket omfattar registrerade enheter och enhets- och appinställningar.</span><span class="sxs-lookup"><span data-stu-id="4f88b-227">You don't need to make any changes to your current Intune configuration before migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="4f88b-228">Windows 10</span><span class="sxs-lookup"><span data-stu-id="4f88b-228">Windows 10</span></span>

<span data-ttu-id="4f88b-229">Microsoft 365 Business Premium innehåller Windows 10 Business, som du kan installera med Windows AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="4f88b-229">Microsoft 365 Business Premium includes Windows 10 Business, which you can install with Windows AutoPilot.</span></span> <span data-ttu-id="4f88b-230">När du migrerar till Microsoft 365 E3 inkluderar varje användarlicens Windows 10 Enterprise E3, som du även kan installera med Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4f88b-230">When you migrate to Microsoft 365 E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a><span data-ttu-id="4f88b-231">Microsoft 365-applikationer för affärsverksamhet</span><span class="sxs-lookup"><span data-stu-id="4f88b-231">Microsoft 365 Apps for business</span></span>

<span data-ttu-id="4f88b-232">Din Microsoft 365-applikationer för affärsverksamhet klient som är installerad på dina enheter börjar automatiskt använda funktionerna i Microsoft 365-appar för företag.</span><span class="sxs-lookup"><span data-stu-id="4f88b-232">Your Microsoft 365 Apps for business client installed on your devices will automatically begin to use the features of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="4f88b-233">Efter migreringen kan du nu använda:</span><span class="sxs-lookup"><span data-stu-id="4f88b-233">After migration, you can now use:</span></span>

 - <span data-ttu-id="4f88b-234">Grupprincipstöd</span><span class="sxs-lookup"><span data-stu-id="4f88b-234">Group Policy support</span></span>
 - <span data-ttu-id="4f88b-235">Spreadsheet compare and inquire</span><span class="sxs-lookup"><span data-stu-id="4f88b-235">Spreadsheet compare and inquire</span></span>
 - <span data-ttu-id="4f88b-236">Business Intelligence</span><span class="sxs-lookup"><span data-stu-id="4f88b-236">Business intelligence</span></span>

