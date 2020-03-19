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
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Läs om hur du flyttar ditt företag från Microsoft 365 Business till Microsoft 365 E3.
ms.openlocfilehash: 9e9cfcf2212faa69f600267e4f9bfd2391e3f4e5
ms.sourcegitcommit: 9c335d110e0b499501edc8a31b987641819118a1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2020
ms.locfileid: "42808126"
---
# <a name="migrate-from-microsoft-365-business-to-microsoft-365-e3"></a><span data-ttu-id="e68c3-103">Migrera från Microsoft 365 Business till Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="e68c3-103">Migrate from Microsoft 365 Business to Microsoft 365 E3</span></span>

<span data-ttu-id="e68c3-104">Microsoft 365 Business har allt du behöver för ditt småföretag och kombinerar de förstklassiga molnbaserade produktivitetsapparna med enkel enhetshantering och säkerhet som gör det möjligt för dina anställda att göra sitt bästa arbete.</span><span class="sxs-lookup"><span data-stu-id="e68c3-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="e68c3-105">I vissa fall kan du dock behöva migrera din Microsoft 365 Business-prenumeration till Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="e68c3-105">In some cases, however, you may need to migrate your Microsoft 365 Business subscription to Microsoft 365 E3.</span></span> 

<span data-ttu-id="e68c3-106">Ditt företag har till exempel vuxit och behöver mer än 300 licenser (grattis, förresten).</span><span class="sxs-lookup"><span data-stu-id="e68c3-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="e68c3-107">Eller så behöver ditt företag företagsfunktioner, till exempel Office 365 ProPlus, Windows 10 Enterprise E3 eller Klientåtkomstlicenser för företag (CAL).</span><span class="sxs-lookup"><span data-stu-id="e68c3-107">Or, your business needs enterprise features, such as Office 365 ProPlus, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="e68c3-108">Uppgradering är enkelt: du kan starta [uppgraderingen från administrationscentret](../commerce/subscriptions/upgrade-to-different-plan.md).</span><span class="sxs-lookup"><span data-stu-id="e68c3-108">Upgrading is easy: you can start the upgrade [from the Admin center](../commerce/subscriptions/upgrade-to-different-plan.md).</span></span> <span data-ttu-id="e68c3-109">Alla dina data och konfiguration i din nuvarande prenumeration underhålls.</span><span class="sxs-lookup"><span data-stu-id="e68c3-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="e68c3-110">Det finns inget för dig att göra för att förbereda migreringen och inget att göra efteråt, förutom att dra nytta av de nya funktionerna.</span><span class="sxs-lookup"><span data-stu-id="e68c3-110">There's nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span>

>[!Note]
><span data-ttu-id="e68c3-111">Du kan också använda en Microsoft 365 Business-prenumeration på upp till 300 platser och få en Microsoft 365 E3-prenumeration på mer än 300 platser.</span><span class="sxs-lookup"><span data-stu-id="e68c3-111">You can also use a Microsoft 365 Business subscription for up to 300 seats and get a Microsoft 365 E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="e68c3-112">Office 365 ATP ingår dock inte i Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="e68c3-112">However, Office 365 ATP is not included with Microsoft 365 E3.</span></span> <span data-ttu-id="e68c3-113">För fortsatt skydd av hot bör du lägga till ytterligare Office 365 ATP-licenser så att alla användare i office 365 ATP-polisen är licensierade.</span><span class="sxs-lookup"><span data-stu-id="e68c3-113">For continued threat protection, you should add additional Office 365 ATP licenses so that all of the users in scope of your Office 365 ATP polices are licensed.</span></span>
>

## <a name="differences-between-microsoft-365-business-and-microsoft-365-enterprise"></a><span data-ttu-id="e68c3-114">Skillnader mellan Microsoft 365 Business och Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e68c3-114">Differences between Microsoft 365 Business and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="e68c3-115">I den här tabellen visas skillnaderna mellan Microsoft 365 Business och Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="e68c3-115">This table shows the differences between Microsoft 365 Business and Microsoft 365 E3.</span></span>

| <span data-ttu-id="e68c3-116">Funktion</span><span class="sxs-lookup"><span data-stu-id="e68c3-116">Feature</span></span>    | <span data-ttu-id="e68c3-117">Stöd i Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="e68c3-117">Support in Microsoft 365 Business</span></span>    | <span data-ttu-id="e68c3-118">Stöd i Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="e68c3-118">Support in Microsoft 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="e68c3-119">**Lokalt**</span><span class="sxs-lookup"><span data-stu-id="e68c3-119">**On-premises**</span></span>        | | | 
| <span data-ttu-id="e68c3-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="e68c3-120">Windows 10</span></span>    | <span data-ttu-id="e68c3-121">Windows 10 Företag</span><span class="sxs-lookup"><span data-stu-id="e68c3-121">Windows 10 Business</span></span>  |     <span data-ttu-id="e68c3-122">Windows 10 Företag E3</span><span class="sxs-lookup"><span data-stu-id="e68c3-122">Windows 10 Enterprise E3</span></span>| 
| <span data-ttu-id="e68c3-123">Office-appar\*</span><span class="sxs-lookup"><span data-stu-id="e68c3-123">Office apps\*</span></span>    | [<span data-ttu-id="e68c3-124">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="e68c3-124">Office 365 Business</span></span>](#office-365-business)    | <span data-ttu-id="e68c3-125">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="e68c3-125">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="e68c3-126">**Molnproduktivitetsappar**</span><span class="sxs-lookup"><span data-stu-id="e68c3-126">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="e68c3-127">Exchange Online och Outlook</span><span class="sxs-lookup"><span data-stu-id="e68c3-127">Exchange Online and Outlook</span></span>    | <span data-ttu-id="e68c3-128">Lagringsgräns på 50 GB per postlåda och obegränsad Exchange Online-arkivering</span><span class="sxs-lookup"><span data-stu-id="e68c3-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>    | <span data-ttu-id="e68c3-129">Lagringsgräns på 100 GB per postlåda och obegränsad Exchange Online-arkivering</span><span class="sxs-lookup"><span data-stu-id="e68c3-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> | 
| <span data-ttu-id="e68c3-130">Lag</span><span class="sxs-lookup"><span data-stu-id="e68c3-130">Teams</span></span>    | ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="e68c3-133">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="e68c3-133">OneDrive for Business</span></span>    | <span data-ttu-id="e68c3-134">1 TB lagringsgräns per användare</span><span class="sxs-lookup"><span data-stu-id="e68c3-134">1 TB storage limit per user</span></span>    | <span data-ttu-id="e68c3-135">Obegränsad</span><span class="sxs-lookup"><span data-stu-id="e68c3-135">Unlimited</span></span> | 
| <span data-ttu-id="e68c3-136">Yammer, SharePoint Online, Planerare, Stream</span><span class="sxs-lookup"><span data-stu-id="e68c3-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="e68c3-139">Outlook kundansvarig, MileIQ</span><span class="sxs-lookup"><span data-stu-id="e68c3-139">Outlook Customer Manager, MileIQ</span></span>    | ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | | 
| <span data-ttu-id="e68c3-141">**Skydd mot hot**</span><span class="sxs-lookup"><span data-stu-id="e68c3-141">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="e68c3-142">Angripa ytreduceringsfunktioner</span><span class="sxs-lookup"><span data-stu-id="e68c3-142">Attack surface reduction capabilities</span></span>    | [<span data-ttu-id="e68c3-143">Se den här listan</span><span class="sxs-lookup"><span data-stu-id="e68c3-143">See this list</span></span>](#threat-protection) | <span data-ttu-id="e68c3-144">Företagshantering av maskinvarubaserad isolering för Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e68c3-144">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> | 
| <span data-ttu-id="e68c3-145">Office 365 Advanced Threat Protection (ATP) Plan 1</span><span class="sxs-lookup"><span data-stu-id="e68c3-145">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | <span data-ttu-id="e68c3-147">Ingår inte, men kan läggas till på</span><span class="sxs-lookup"><span data-stu-id="e68c3-147">Not included, but can be added on</span></span> | 
| <span data-ttu-id="e68c3-148">**Identitetshantering**</span><span class="sxs-lookup"><span data-stu-id="e68c3-148">**Identity management**</span></span>        | | | 
| <span data-ttu-id="e68c3-149">Återställning av lösenord för självbetjäning för hybridkonton i Azure Active Directory (Azure AD), Azure Multi-Factor Authentication (MFA), Villkorlig åtkomst, återställning av lösenord för lokala identiteter</span><span class="sxs-lookup"><span data-stu-id="e68c3-149">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="e68c3-152">Identifiering av molnapp, Azure AD Connect-hälsotillstånd</span><span class="sxs-lookup"><span data-stu-id="e68c3-152">Cloud App Discovery, Azure AD Connect Health</span></span>    |     | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="e68c3-154">Azure AD Office 365-appar Enkel inloggning (SSO): 10 appar per användare (Galleri SaaS-appar som Salesforce)\*</span><span class="sxs-lookup"><span data-stu-id="e68c3-154">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="e68c3-157">SSO för Azure AD Premium 1: ingen gräns (Lokala appar via Azure AD Application Proxy och appar som inte är gallerier med självbetjäningsmallar för appintegrering)</span><span class="sxs-lookup"><span data-stu-id="e68c3-157">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>    |     | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="e68c3-159">**Enhets- och apphantering**</span><span class="sxs-lookup"><span data-stu-id="e68c3-159">**Device and app management**</span></span>        | | | 
| <span data-ttu-id="e68c3-160">Microsoft Intune, Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="e68c3-160">Microsoft Intune, Windows Autopilot</span></span>|     ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
|<span data-ttu-id="e68c3-163">Virtuell skrivbordsåtkomst (VDA)</span><span class="sxs-lookup"><span data-stu-id="e68c3-163">Virtual Desktop Access (VDA)</span></span>    |  |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
|<span data-ttu-id="e68c3-165">Virtuellt windows-skrivbord (WVD)</span><span class="sxs-lookup"><span data-stu-id="e68c3-165">Windows Virtual Desktop (WVD)</span></span>    | ![Ingår i Microsoft 365 Business](../media/check-mark.png) |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
|<span data-ttu-id="e68c3-168">Delad datoraktivering (SCA)</span><span class="sxs-lookup"><span data-stu-id="e68c3-168">Shared Computer Activation (SCA)</span></span>    | ![Ingår i Microsoft 365 Business](../media/check-mark.png) |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="e68c3-171">Optimeringspaket för Microsoft Desktop</span><span class="sxs-lookup"><span data-stu-id="e68c3-171">Microsoft Desktop Optimization Package</span></span>    | |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="e68c3-173">**Informationsskydd**</span><span class="sxs-lookup"><span data-stu-id="e68c3-173">**Information protection**</span></span>        | | | 
| <span data-ttu-id="e68c3-174">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span><span class="sxs-lookup"><span data-stu-id="e68c3-174">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>    | ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="e68c3-177">Windows-informationsskydd för slutpunktS-DLP</span><span class="sxs-lookup"><span data-stu-id="e68c3-177">Window Information Protection for endpoint DLP</span></span>    | ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="e68c3-180">**Licens för klientåtkomst (CAL-rättigheter)**</span><span class="sxs-lookup"><span data-stu-id="e68c3-180">**Client Access License (CAL rights)**</span></span>    | | |     
| <span data-ttu-id="e68c3-181">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span><span class="sxs-lookup"><span data-stu-id="e68c3-181">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span></span>| |         ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="e68c3-183">**Överensstämmelse**</span><span class="sxs-lookup"><span data-stu-id="e68c3-183">**Compliance**</span></span>        | | | 
| <span data-ttu-id="e68c3-184">Obegränsad e-postarkivering</span><span class="sxs-lookup"><span data-stu-id="e68c3-184">Unlimited email archiving</span></span>    | ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="e68c3-187">Efterlevnadspoäng/efterlevnadshanterare</span><span class="sxs-lookup"><span data-stu-id="e68c3-187">Compliance Score/Compliance Manager</span></span>    | ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="e68c3-190">Ediscovery</span><span class="sxs-lookup"><span data-stu-id="e68c3-190">eDiscovery</span></span>    | ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="e68c3-193">På plats och tvistemål</span><span class="sxs-lookup"><span data-stu-id="e68c3-193">In-place hold and litigation hold</span></span>    | ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="e68c3-196">BEVARANDETAGGAR och bevarandeprinciper för meddelandehandlingar (MESSAGING Records Management) och bevarandeprinciper</span><span class="sxs-lookup"><span data-stu-id="e68c3-196">Messaging Records Management (MRM) retention tags and retention policies</span></span>    | ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) | 
||||

<span data-ttu-id="e68c3-199">\*Användare som har tilldelats åtkomst till SaaS-appar kan få SSO-åtkomst till upp till 10 appar.</span><span class="sxs-lookup"><span data-stu-id="e68c3-199">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="e68c3-200">Administratörer kan konfigurera SSO och ändra användaråtkomst till olika SaaS-appar, men SSO-åtkomst tillåts endast för 10 appar per användare åt gången.</span><span class="sxs-lookup"><span data-stu-id="e68c3-200">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="e68c3-201">Alla Office 365-appar räknas som ett enda program.</span><span class="sxs-lookup"><span data-stu-id="e68c3-201">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="e68c3-202">Migration</span><span class="sxs-lookup"><span data-stu-id="e68c3-202">Migration</span></span>

<span data-ttu-id="e68c3-203">Om du vill migrera kan du arbeta med din partner för att flytta din Microsoft 365 Business-prenumeration och dina licenser till en lämplig Microsoft 365 E3-prenumeration med sina licenser.</span><span class="sxs-lookup"><span data-stu-id="e68c3-203">To migrate, work with your partner to move your Microsoft 365 Business subscription and licenses to a suitable Microsoft 365 E3 subscription with its licenses.</span></span>

<span data-ttu-id="e68c3-204">I följande avsnitt beskrivs vilka ändringar du behöver göra, om några, och vad du kan göra efter migreringen.</span><span class="sxs-lookup"><span data-stu-id="e68c3-204">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="e68c3-205">Konfiguration och data för Microsoft 365-prenumeration</span><span class="sxs-lookup"><span data-stu-id="e68c3-205">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="e68c3-206">Du behöver inte göra några ändringar i din aktuella prenumeration eller dina data innan du migrerar, vilket inkluderar:</span><span class="sxs-lookup"><span data-stu-id="e68c3-206">You don't need to make any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="e68c3-207">Prenumerationskonfiguration, till exempel DNS-domännamn.</span><span class="sxs-lookup"><span data-stu-id="e68c3-207">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="e68c3-208">Användar- och gruppkonton och autentiseringsinställningar, till exempel multifaktorautentisering eller principer för villkorlig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="e68c3-208">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="e68c3-209">Produktivitetstjänstkonfigurationer och deras data, till exempel Teams, Exchange Online-postlådor, SharePoint Online-webbplatser, OneDrive för företag-mappar och OneNote-anteckningsböcker.</span><span class="sxs-lookup"><span data-stu-id="e68c3-209">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="e68c3-210">Användarna kan nu njuta av obegränsat lagringsutrymme i Exchange Online-postlådorna och OneDrive för företag-mapparna.</span><span class="sxs-lookup"><span data-stu-id="e68c3-210">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="e68c3-211">Du kan börja använda Cloud App Discovery, Azure AD Connect Health och SSO för mer än 10 appar.</span><span class="sxs-lookup"><span data-stu-id="e68c3-211">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

>[!Note]
><span data-ttu-id="e68c3-212">Användare som migreras till Microsoft 365 E3 kan inte längre använda Outlook Customer Manager och MileIQ.</span><span class="sxs-lookup"><span data-stu-id="e68c3-212">Users migrated to Microsoft 365 E3 can no longer use Outlook Customer Manager and MileIQ.</span></span>
>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="e68c3-213">Skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="e68c3-213">Threat protection</span></span>

<span data-ttu-id="e68c3-214">Windows 10 Business innehåller följande skydd:</span><span class="sxs-lookup"><span data-stu-id="e68c3-214">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="e68c3-215">Integritet verkställighet av operativsystemet starta upp processen</span><span class="sxs-lookup"><span data-stu-id="e68c3-215">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="e68c3-216">Integritetstillverkning av känsliga driftkomponenter</span><span class="sxs-lookup"><span data-stu-id="e68c3-216">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="e68c3-217">Avancerad sårbarhet och zero-day utnyttja mildrande åtgärder</span><span class="sxs-lookup"><span data-stu-id="e68c3-217">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="e68c3-218">Ryktesbaserat nätverksskydd för Microsoft Edge, Internet Explorer och Chrome</span><span class="sxs-lookup"><span data-stu-id="e68c3-218">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="e68c3-219">Värdbaserad brandvägg</span><span class="sxs-lookup"><span data-stu-id="e68c3-219">Host-based firewall</span></span>
- <span data-ttu-id="e68c3-220">Reduceringar av ransomware</span><span class="sxs-lookup"><span data-stu-id="e68c3-220">Ransomware mitigations</span></span>
- <span data-ttu-id="e68c3-221">Maskinvarubaserad isolering för Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e68c3-221">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="e68c3-222">Programstyrning som drivs av Intelligent Security Graph</span><span class="sxs-lookup"><span data-stu-id="e68c3-222">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="e68c3-223">Enhetskontroll (USB)</span><span class="sxs-lookup"><span data-stu-id="e68c3-223">Device control (USB)</span></span>
- <span data-ttu-id="e68c3-224">Nätverksskydd för webbaserade hot</span><span class="sxs-lookup"><span data-stu-id="e68c3-224">Network protection for web-based threats</span></span>
- <span data-ttu-id="e68c3-225">Regler för intrångsskydd för värdbrott</span><span class="sxs-lookup"><span data-stu-id="e68c3-225">Host intrusion prevention rules</span></span>

<span data-ttu-id="e68c3-226">Windows 10 Enterprise E3 innehåller även företagshantering av maskinvarubaserad isolering för Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="e68c3-226">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

>[!Note]
><span data-ttu-id="e68c3-227">Användare som migreras till Microsoft 365 E3 kräver var och en en Office 365 ATP-licens för fortsatt hotskydd.</span><span class="sxs-lookup"><span data-stu-id="e68c3-227">Users migrated to Microsoft 365 E3 will each require an Office 365 ATP license for continued threat protection.</span></span> <span data-ttu-id="e68c3-228">Var noga med att köpa ytterligare Office 365 ATP-licenser så att alla användare i office 365 ATP-polisen har licens.</span><span class="sxs-lookup"><span data-stu-id="e68c3-228">Be sure to purchase additional Office 365 ATP licenses so that all of the users in scope of your Office 365 ATP polices are licensed.</span></span> 
>

### <a name="device-management-with-intune"></a><span data-ttu-id="e68c3-229">Enhetshantering med Intune</span><span class="sxs-lookup"><span data-stu-id="e68c3-229">Device management with Intune</span></span>

<span data-ttu-id="e68c3-230">Du behöver inte göra några ändringar i din aktuella Intune-konfiguration innan du migrerar, vilket inkluderar registrerade enheter och enhets- och appinställningar.</span><span class="sxs-lookup"><span data-stu-id="e68c3-230">You don't need to make any changes to your current Intune configuration before migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="e68c3-231">Windows 10</span><span class="sxs-lookup"><span data-stu-id="e68c3-231">Windows 10</span></span>

<span data-ttu-id="e68c3-232">Microsoft 365 Business innehåller Windows 10 Business, som du kan installera med Windows AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="e68c3-232">Microsoft 365 Business includes Windows 10 Business, which you can install with Windows AutoPilot.</span></span> <span data-ttu-id="e68c3-233">När du migrerar till Microsoft 365 E3 innehåller varje användarlicens Windows 10 Enterprise E3, som du också kan installera med Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="e68c3-233">When you migrate to Microsoft 365 E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
### <a name="office-365-business"></a><span data-ttu-id="e68c3-234">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="e68c3-234">Office 365 Business</span></span>

<span data-ttu-id="e68c3-235">Din Office 365 Business-klient som är installerad på dina enheter börjar automatiskt använda funktionerna i Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="e68c3-235">Your Office 365 Business client installed on your devices will automatically begin to use the features of Office 365 ProPlus.</span></span> <span data-ttu-id="e68c3-236">Efter migreringen kan du nu använda:</span><span class="sxs-lookup"><span data-stu-id="e68c3-236">After migration, you can now use:</span></span>

 - <span data-ttu-id="e68c3-237">Volymaktivering via grupprincip</span><span class="sxs-lookup"><span data-stu-id="e68c3-237">Volume activation through Group Policy</span></span>
 - <span data-ttu-id="e68c3-238">App telemetri</span><span class="sxs-lookup"><span data-stu-id="e68c3-238">App telemetry</span></span>
 - <span data-ttu-id="e68c3-239">Uppdatera kontroller</span><span class="sxs-lookup"><span data-stu-id="e68c3-239">Update controls</span></span>
 - <span data-ttu-id="e68c3-240">Kalkylblad jämföra och fråga</span><span class="sxs-lookup"><span data-stu-id="e68c3-240">Spreadsheet compare and inquire</span></span>
 - <span data-ttu-id="e68c3-241">Business intelligens</span><span class="sxs-lookup"><span data-stu-id="e68c3-241">Business intelligence</span></span>

