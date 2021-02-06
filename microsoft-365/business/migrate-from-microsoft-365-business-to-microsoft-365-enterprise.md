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
description: Lär dig hur du flyttar över ditt företag från Microsoft 365 Business Premium till Microsoft 365 E3.
ms.openlocfilehash: 019a422bb879389f42a32cf30f9a8094f776078a
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126210"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a><span data-ttu-id="506c6-103">Migrera från Microsoft 365 Business Premium till Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="506c6-103">Migrate from Microsoft 365 Business Premium to Microsoft 365 E3</span></span>

<span data-ttu-id="506c6-104">Microsoft 365 Business Premium har allt du behöver för ditt småföretag och kombinerar de förstklassiga molnbaserade produktivitetsapparna med enkel enhetshantering och säkerhet som gör det möjligt för dina anställda att göra sitt bästa arbete.</span><span class="sxs-lookup"><span data-stu-id="506c6-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="506c6-105">Men i vissa fall kan du behöva migrera din Microsoft 365 Business Premium-prenumeration till Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="506c6-105">In some cases, however, you may need to migrate your Microsoft 365 Business Premium subscription to Microsoft 365 E3.</span></span> 

<span data-ttu-id="506c6-106">Till exempel har företaget vuxit och behöver fler än 300 licenser (grattis).</span><span class="sxs-lookup"><span data-stu-id="506c6-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="506c6-107">Eller så behöver ditt företag företag funktioner, till exempel Microsoft 365-appar för företag, Windows 10 Enterprise, E3 eller klientåtkomstlicenser för företag (CA:er).</span><span class="sxs-lookup"><span data-stu-id="506c6-107">Or, your business needs enterprise features, such as Microsoft 365 Apps for enterprise, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="506c6-108">Det är enkelt att uppgradera: du kan [starta uppgraderingen från administrationscentret.](../commerce/subscriptions/upgrade-to-different-plan.md)</span><span class="sxs-lookup"><span data-stu-id="506c6-108">Upgrading is easy: you can start the upgrade [from the Admin center](../commerce/subscriptions/upgrade-to-different-plan.md).</span></span> <span data-ttu-id="506c6-109">Alla data och konfigurationer i din nuvarande prenumeration bibehålls.</span><span class="sxs-lookup"><span data-stu-id="506c6-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="506c6-110">Det finns inget du kan göra för att förbereda migreringen och inget att göra efteråt, förutom att dra nytta av de nya funktionerna.</span><span class="sxs-lookup"><span data-stu-id="506c6-110">There's nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span>

>[!Note]
><span data-ttu-id="506c6-111">Du kan också använda en Microsoft 365 Business Premium-prenumeration för upp till 300 platser och få en Microsoft 365 E3-prenumeration för fler än 300 platser.</span><span class="sxs-lookup"><span data-stu-id="506c6-111">You can also use a Microsoft 365 Business Premium subscription for up to 300 seats and get a Microsoft 365 E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="506c6-112">Men Microsoft Defender för Office 365 ingår inte i Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="506c6-112">However, Microsoft Defender for Office 365 is not included with Microsoft 365 E3.</span></span> <span data-ttu-id="506c6-113">För att få fortsatt skydd mot hot bör du lägga till ytterligare Defender för Office 365-licenser så att alla användare som omfattas av Defender för Office 365-säkerhet är licensierade.</span><span class="sxs-lookup"><span data-stu-id="506c6-113">For continued threat protection, you should add additional Defender for Office 365 licenses so that all of the users in scope of your Defender for Office 365 polices are licensed.</span></span>
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a><span data-ttu-id="506c6-114">Skillnader mellan Microsoft 365 Business Premium och Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="506c6-114">Differences between Microsoft 365 Business Premium and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="506c6-115">I den här tabellen visas skillnaderna mellan Microsoft 365 Business Premium och Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="506c6-115">This table shows the differences between Microsoft 365 Business Premium and Microsoft 365 E3.</span></span>

| <span data-ttu-id="506c6-116">Funktion</span><span class="sxs-lookup"><span data-stu-id="506c6-116">Feature</span></span>    | <span data-ttu-id="506c6-117">Support i Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="506c6-117">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="506c6-118">Support i Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="506c6-118">Support in Microsoft 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="506c6-119">**Lokal**</span><span class="sxs-lookup"><span data-stu-id="506c6-119">**On-premises**</span></span>        | | | 
| <span data-ttu-id="506c6-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="506c6-120">Windows 10</span></span>    | <span data-ttu-id="506c6-121">Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="506c6-121">Windows 10 Business</span></span>  |     <span data-ttu-id="506c6-122">Windows 10 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="506c6-122">Windows 10 Enterprise E3</span></span>| 
| <span data-ttu-id="506c6-123">Office-appar\*</span><span class="sxs-lookup"><span data-stu-id="506c6-123">Office apps\*</span></span>    | [<span data-ttu-id="506c6-124">Microsoft 365-applikationer för affärsverksamhet</span><span class="sxs-lookup"><span data-stu-id="506c6-124">Microsoft 365 Apps for business</span></span>](#office-365-business)    | <span data-ttu-id="506c6-125"> Microsoft 365 Apps för företag</span><span class="sxs-lookup"><span data-stu-id="506c6-125">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="506c6-126">**Produktivitetsprogram för molnet**</span><span class="sxs-lookup"><span data-stu-id="506c6-126">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="506c6-127">Exchange Online och Outlook</span><span class="sxs-lookup"><span data-stu-id="506c6-127">Exchange Online and Outlook</span></span>    | <span data-ttu-id="506c6-128">50 GB lagringsutrymme per postlåda och obegränsad Exchange Online-arkivering</span><span class="sxs-lookup"><span data-stu-id="506c6-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>    | <span data-ttu-id="506c6-129">100 GB lagringsutrymme per postlåda och obegränsad Exchange Online-arkivering</span><span class="sxs-lookup"><span data-stu-id="506c6-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="506c6-130">Teams</span><span class="sxs-lookup"><span data-stu-id="506c6-130">Teams</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="506c6-133">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="506c6-133">OneDrive for Business</span></span>    | <span data-ttu-id="506c6-134">1 TB lagringsutrymme per användare</span><span class="sxs-lookup"><span data-stu-id="506c6-134">1 TB storage limit per user</span></span>    | <span data-ttu-id="506c6-135">Obegränsat</span><span class="sxs-lookup"><span data-stu-id="506c6-135">Unlimited</span></span> | 
| <span data-ttu-id="506c6-136">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="506c6-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="506c6-139">MileIQ</span><span class="sxs-lookup"><span data-stu-id="506c6-139">MileIQ</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| <span data-ttu-id="506c6-141">**Skydd mot hot**</span><span class="sxs-lookup"><span data-stu-id="506c6-141">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="506c6-142">Funktioner för att minska attackytan</span><span class="sxs-lookup"><span data-stu-id="506c6-142">Attack surface reduction capabilities</span></span>    | [<span data-ttu-id="506c6-143">Se den här listan</span><span class="sxs-lookup"><span data-stu-id="506c6-143">See this list</span></span>](#threat-protection) | <span data-ttu-id="506c6-144">Företagshantering av maskinvarubaserad avgränsning för Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="506c6-144">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> | 
| <span data-ttu-id="506c6-145">Defender för Office 365 abonnemang 1</span><span class="sxs-lookup"><span data-stu-id="506c6-145">Defender for Office 365 Plan 1</span></span> | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | <span data-ttu-id="506c6-147">Ingår inte, men kan läggas till på</span><span class="sxs-lookup"><span data-stu-id="506c6-147">Not included, but can be added on</span></span> | 
| <span data-ttu-id="506c6-148">**Identitetshantering**</span><span class="sxs-lookup"><span data-stu-id="506c6-148">**Identity management**</span></span>        | | | 
| <span data-ttu-id="506c6-149">Självbetjäning för återställning av lösenord för Azure Active Directory-hybridkonton (Azure AD), Azure AD-multifaktorautentisering (MFA), villkorsstyrd åtkomst, lösenordsåterställning för lokala identiteter</span><span class="sxs-lookup"><span data-stu-id="506c6-149">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="506c6-152">Identifiering av molnapp, Azure AD Connect Health</span><span class="sxs-lookup"><span data-stu-id="506c6-152">Cloud App Discovery, Azure AD Connect Health</span></span>    |     | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="506c6-154">Azure AD Office 365-appar – enkel Sign-On (SSO): 10 appar per användare (SaaS-galleriprogram, till exempel Salesforce)\*</span><span class="sxs-lookup"><span data-stu-id="506c6-154">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="506c6-157">Azure AD Premium 1 SSO: ingen gräns (lokala appar via Azure AD-programproxy och icke-galleriappar med hjälp Self-Service mallar för appintegrering)</span><span class="sxs-lookup"><span data-stu-id="506c6-157">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>    |     | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="506c6-159">**Enhets- och apphantering**</span><span class="sxs-lookup"><span data-stu-id="506c6-159">**Device and app management**</span></span>        | | | 
| <span data-ttu-id="506c6-160">Microsoft Intune, Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="506c6-160">Microsoft Intune, Windows Autopilot</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
|<span data-ttu-id="506c6-163">Virtual Desktop Access (VDA)</span><span class="sxs-lookup"><span data-stu-id="506c6-163">Virtual Desktop Access (VDA)</span></span>    |  |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
|<span data-ttu-id="506c6-165">Windows Virtual Desktop (WVD)</span><span class="sxs-lookup"><span data-stu-id="506c6-165">Windows Virtual Desktop (WVD)</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png) |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
|<span data-ttu-id="506c6-168">SCA (Shared Computer Activation)</span><span class="sxs-lookup"><span data-stu-id="506c6-168">Shared Computer Activation (SCA)</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png) |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="506c6-171">Microsofts paket för skrivbordsoptimering</span><span class="sxs-lookup"><span data-stu-id="506c6-171">Microsoft Desktop Optimization Package</span></span>    | |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="506c6-173">**Informationsskydd**</span><span class="sxs-lookup"><span data-stu-id="506c6-173">**Information protection**</span></span>        | | | 
| <span data-ttu-id="506c6-174">Dataförlustskydd i Office 365, Azure Information Protection Plan 1</span><span class="sxs-lookup"><span data-stu-id="506c6-174">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="506c6-177">Fönsterinformationsskydd för slutpunkt DLP</span><span class="sxs-lookup"><span data-stu-id="506c6-177">Window Information Protection for endpoint DLP</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="506c6-180">**Klientåtkomstlicens (CAL-rättigheter)**</span><span class="sxs-lookup"><span data-stu-id="506c6-180">**Client Access License (CAL rights)**</span></span>    | | |     
| <span data-ttu-id="506c6-181">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Konfigurationshanteraren, Windows Rights Management)</span><span class="sxs-lookup"><span data-stu-id="506c6-181">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span></span>| |         ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="506c6-183">**Efterlevnad**</span><span class="sxs-lookup"><span data-stu-id="506c6-183">**Compliance**</span></span>        | | | 
| <span data-ttu-id="506c6-184">Obegränsad e-postarkivering</span><span class="sxs-lookup"><span data-stu-id="506c6-184">Unlimited email archiving</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="506c6-187">Efterlevnadshanteraren</span><span class="sxs-lookup"><span data-stu-id="506c6-187">Compliance Manager</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="506c6-190">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="506c6-190">eDiscovery</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="506c6-193">Bevarande av juridiska skäl på plats och bevarande av juridiska skäl</span><span class="sxs-lookup"><span data-stu-id="506c6-193">In-place hold and litigation hold</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="506c6-196">Bevarandetaggar (MRM) för hantering av meddelandeposter och bevarandeprinciper</span><span class="sxs-lookup"><span data-stu-id="506c6-196">Messaging Records Management (MRM) retention tags and retention policies</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
||||

<span data-ttu-id="506c6-199">\* Användare som har tilldelats åtkomst till SaaS-appar kan få SSO-åtkomst till upp till 10 program.</span><span class="sxs-lookup"><span data-stu-id="506c6-199">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="506c6-200">Administratörer kan konfigurera SSO och ändra användaråtkomst till olika SaaS-appar, men SSO-åtkomst är endast tillåten för 10 appar per användare i taget.</span><span class="sxs-lookup"><span data-stu-id="506c6-200">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="506c6-201">Alla Office 365-appar räknas som en enskild app.</span><span class="sxs-lookup"><span data-stu-id="506c6-201">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="506c6-202">Migrering</span><span class="sxs-lookup"><span data-stu-id="506c6-202">Migration</span></span>

<span data-ttu-id="506c6-203">Migrera genom att samarbeta med din partner för att flytta din Microsoft 365 Business Premium-prenumeration och licenser till en lämplig Microsoft 365 E3-prenumeration med dess licenser.</span><span class="sxs-lookup"><span data-stu-id="506c6-203">To migrate, work with your partner to move your Microsoft 365 Business Premium subscription and licenses to a suitable Microsoft 365 E3 subscription with its licenses.</span></span>

<span data-ttu-id="506c6-204">I följande avsnitt beskrivs vilka ändringar du behöver göra, om det finns några, och vad du kan göra efter migreringen.</span><span class="sxs-lookup"><span data-stu-id="506c6-204">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="506c6-205">Konfiguration och data för Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="506c6-205">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="506c6-206">Du behöver inte göra några ändringar i din nuvarande prenumeration eller dina aktuella data innan du migrerar, vilket omfattar:</span><span class="sxs-lookup"><span data-stu-id="506c6-206">You don't need to make any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="506c6-207">Prenumerationskonfiguration, till exempel DNS-domännamn.</span><span class="sxs-lookup"><span data-stu-id="506c6-207">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="506c6-208">Användar- och gruppkonton och autentiseringsinställningar, till exempel principer för multifaktorautentisering eller villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="506c6-208">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="506c6-209">Produktivitetstjänstkonfigurationer och deras data, till exempel Teams, Exchange Online-postlådor, SharePoint Online-webbplatser, OneDrive för företag-mappar och OneNote-anteckningsböcker.</span><span class="sxs-lookup"><span data-stu-id="506c6-209">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="506c6-210">Användarna kan nu använda obegränsat lagringsutrymme i Exchange Online-postlådorna och OneDrive för företag-mapparna.</span><span class="sxs-lookup"><span data-stu-id="506c6-210">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="506c6-211">Du kan börja använda Cloud App Discovery, Azure AD Connect Health och SSO för fler än 10 appar.</span><span class="sxs-lookup"><span data-stu-id="506c6-211">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

>[!Note]
><span data-ttu-id="506c6-212">Användare som migrerat till Microsoft 365 E3 kan inte längre använda MileIQ.</span><span class="sxs-lookup"><span data-stu-id="506c6-212">Users migrated to Microsoft 365 E3 can no longer use MileIQ.</span></span>
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="506c6-213">Skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="506c6-213">Threat protection</span></span>

<span data-ttu-id="506c6-214">Windows 10 Business har följande skydd:</span><span class="sxs-lookup"><span data-stu-id="506c6-214">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="506c6-215">Tvingande integritet vid uppstart av operativsystem</span><span class="sxs-lookup"><span data-stu-id="506c6-215">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="506c6-216">Tvingande integritet för känsliga operativsystemskomponenter</span><span class="sxs-lookup"><span data-stu-id="506c6-216">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="506c6-217">Avancerade sårbarhets- och nolldagarsbegränsningar för sårbarheter</span><span class="sxs-lookup"><span data-stu-id="506c6-217">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="506c6-218">Reputation-baserat nätverksskydd för Microsoft Edge, Internet Explorer och Chrome</span><span class="sxs-lookup"><span data-stu-id="506c6-218">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="506c6-219">Värdbaserad brandvägg</span><span class="sxs-lookup"><span data-stu-id="506c6-219">Host-based firewall</span></span>
- <span data-ttu-id="506c6-220">Minskning av utpressningstrojaner</span><span class="sxs-lookup"><span data-stu-id="506c6-220">Ransomware mitigations</span></span>
- <span data-ttu-id="506c6-221">Maskinvarubaserad avgränsning för Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="506c6-221">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="506c6-222">Programkontroll som drivs av Intelligent Security Graph</span><span class="sxs-lookup"><span data-stu-id="506c6-222">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="506c6-223">Enhetskontroll (USB)</span><span class="sxs-lookup"><span data-stu-id="506c6-223">Device control (USB)</span></span>
- <span data-ttu-id="506c6-224">Nätverksskydd för webbaserade hot</span><span class="sxs-lookup"><span data-stu-id="506c6-224">Network protection for web-based threats</span></span>
- <span data-ttu-id="506c6-225">Regler för skydd mot intrång i värden</span><span class="sxs-lookup"><span data-stu-id="506c6-225">Host intrusion prevention rules</span></span>

<span data-ttu-id="506c6-226">Windows 10 Enterprise, E3 innehåller även företagshantering av maskinvarubaserad avgränsning för Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="506c6-226">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

>[!Note]
><span data-ttu-id="506c6-227">Användare som migreras till Microsoft 365 E3 kräver var och en en Microsoft Defender för Office 365-licens för fortsatt skydd mot hot.</span><span class="sxs-lookup"><span data-stu-id="506c6-227">Users migrated to Microsoft 365 E3 will each require a Microsoft Defender for Office 365 license for continued threat protection.</span></span> <span data-ttu-id="506c6-228">Se till att köpa ytterligare Defender för Office 365-licenser så att alla användare som omfattas av Defender för Office 365-användarna är licensierade.</span><span class="sxs-lookup"><span data-stu-id="506c6-228">Be sure to purchase additional Defender for Office 365 licenses so that all of the users in scope of your Defender for Office 365 polices are licensed.</span></span> 
>

### <a name="device-management-with-intune"></a><span data-ttu-id="506c6-229">Enhetshantering med Intune</span><span class="sxs-lookup"><span data-stu-id="506c6-229">Device management with Intune</span></span>

<span data-ttu-id="506c6-230">Du behöver inte göra några ändringar i din aktuella Intune-konfiguration innan du migrerar, vilket omfattar registrerade enheter, enheter och appinställningar.</span><span class="sxs-lookup"><span data-stu-id="506c6-230">You don't need to make any changes to your current Intune configuration before migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="506c6-231">Windows 10</span><span class="sxs-lookup"><span data-stu-id="506c6-231">Windows 10</span></span>

<span data-ttu-id="506c6-232">Microsoft 365 Business Premium innehåller Windows 10 Business, som du kan installera med Windows AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="506c6-232">Microsoft 365 Business Premium includes Windows 10 Business, which you can install with Windows AutoPilot.</span></span> <span data-ttu-id="506c6-233">När du migrerar till Microsoft 365 E3 ingår Windows 10 Enterprise E3 i varje användarlicens, som du även kan installera med Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="506c6-233">When you migrate to Microsoft 365 E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a><span data-ttu-id="506c6-234">Microsoft 365-applikationer för affärsverksamhet</span><span class="sxs-lookup"><span data-stu-id="506c6-234">Microsoft 365 Apps for business</span></span>

<span data-ttu-id="506c6-235">Microsoft 365 Apps för företag-klienten som är installerad på dina enheter börjar automatiskt använda funktionerna i Microsoft 365-appar för företag.</span><span class="sxs-lookup"><span data-stu-id="506c6-235">Your Microsoft 365 Apps for business client installed on your devices will automatically begin to use the features of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="506c6-236">Efter migreringen kan du nu använda:</span><span class="sxs-lookup"><span data-stu-id="506c6-236">After migration, you can now use:</span></span>

 - <span data-ttu-id="506c6-237">grupprincip support</span><span class="sxs-lookup"><span data-stu-id="506c6-237">Group Policy support</span></span>
 - <span data-ttu-id="506c6-238">Spreadsheet compare and inquire</span><span class="sxs-lookup"><span data-stu-id="506c6-238">Spreadsheet compare and inquire</span></span>
 - <span data-ttu-id="506c6-239">Business Intelligence</span><span class="sxs-lookup"><span data-stu-id="506c6-239">Business intelligence</span></span>

