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
ms.openlocfilehash: 6502d79dbb283db37b00e4fccf89b15ab4291ce5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227628"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a><span data-ttu-id="78058-103">Migrera från Microsoft 365 Business Premium till Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="78058-103">Migrate from Microsoft 365 Business Premium to Microsoft 365 E3</span></span>

<span data-ttu-id="78058-104">Microsoft 365 Business Premium har allt du behöver för ditt småföretag. Kombinera de förstklassiga molnbaserade produktivitetsapparna med enkel enhetshantering och säkerhet som gör det möjligt för dina anställda att arbeta på bästa sätt.</span><span class="sxs-lookup"><span data-stu-id="78058-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security that enable your employees to do their best work.</span></span> <span data-ttu-id="78058-105">I vissa fall kan du emellertid behöva migrera din prenumeration Microsoft 365 Business Premium till Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="78058-105">In some cases, however, you may need to migrate your Microsoft 365 Business Premium subscription to Microsoft 365 E3.</span></span>

<span data-ttu-id="78058-106">Företaget har till exempel vuxit och behöver fler än 300 licenser (grattis).</span><span class="sxs-lookup"><span data-stu-id="78058-106">For example, your business has grown and needs more than 300 licenses (congratulations, by the way).</span></span>

<span data-ttu-id="78058-107">Eller, ditt företag behöver företagsfunktioner, som Microsoft 365-appar för företag, Windows 10 Enterprise E3 eller CALs (Enterprise Client Access Licenses).</span><span class="sxs-lookup"><span data-stu-id="78058-107">Or, your business needs enterprise features, such as Microsoft 365 Apps for enterprise, Windows 10 Enterprise E3, or Enterprise Client Access Licenses (CALs).</span></span>

<span data-ttu-id="78058-108">Det är enkelt att uppgradera: du kan [starta uppgraderingen från administrationscentret.](../commerce/subscriptions/upgrade-to-different-plan.md)</span><span class="sxs-lookup"><span data-stu-id="78058-108">Upgrading is easy: you can start the upgrade [from the Admin center](../commerce/subscriptions/upgrade-to-different-plan.md).</span></span> <span data-ttu-id="78058-109">Alla data och konfigurationer i din nuvarande prenumeration behålls.</span><span class="sxs-lookup"><span data-stu-id="78058-109">All your data and configuration in your current subscription is maintained.</span></span> <span data-ttu-id="78058-110">Du behöver inte förbereda dig för migreringen utan att göra något efteråt, förutom att dra nytta av de nya funktionerna.</span><span class="sxs-lookup"><span data-stu-id="78058-110">There's nothing for you to do to prepare for the migration and nothing to do afterward, except take advantage of the new features.</span></span>

> [!NOTE]
> <span data-ttu-id="78058-111">Du kan också använda en Microsoft 365 Business Premium-prenumeration för upp till 300 platser och få en Microsoft 365 E3-prenumeration för fler än 300 platser.</span><span class="sxs-lookup"><span data-stu-id="78058-111">You can also use a Microsoft 365 Business Premium subscription for up to 300 seats and get a Microsoft 365 E3 subscription for more than 300 seats.</span></span> <span data-ttu-id="78058-112">Men Microsoft Defender för Office 365 ingår inte i Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="78058-112">However, Microsoft Defender for Office 365 is not included with Microsoft 365 E3.</span></span> <span data-ttu-id="78058-113">För fortsatt skydd mot hot bör du lägga till ytterligare Defender för Office 365-licenser så att alla användare som omfattas av Defender för Office 365-säkerhet är licensierade.</span><span class="sxs-lookup"><span data-stu-id="78058-113">For continued threat protection, you should add additional Defender for Office 365 licenses so that all of the users in scope of your Defender for Office 365 polices are licensed.</span></span>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a><span data-ttu-id="78058-114">Skillnader mellan Microsoft 365 Business Premium och Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="78058-114">Differences between Microsoft 365 Business Premium and Microsoft 365 Enterprise</span></span>

<span data-ttu-id="78058-115">I den här tabellen visas skillnaderna mellan Microsoft 365 Business Premium och Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="78058-115">This table shows the differences between Microsoft 365 Business Premium and Microsoft 365 E3.</span></span>

| <span data-ttu-id="78058-116">Funktion</span><span class="sxs-lookup"><span data-stu-id="78058-116">Feature</span></span>    | <span data-ttu-id="78058-117">Support i Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="78058-117">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="78058-118">Support i Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="78058-118">Support in Microsoft 365 E3</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="78058-119">**Lokalt**</span><span class="sxs-lookup"><span data-stu-id="78058-119">**On-premises**</span></span>        | | |
| <span data-ttu-id="78058-120">Windows 10</span><span class="sxs-lookup"><span data-stu-id="78058-120">Windows 10</span></span>    | <span data-ttu-id="78058-121">Windows 10 Business</span><span class="sxs-lookup"><span data-stu-id="78058-121">Windows 10 Business</span></span>  |     <span data-ttu-id="78058-122">Windows 10 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="78058-122">Windows 10 Enterprise E3</span></span>|
| <span data-ttu-id="78058-123">Office appar\*</span><span class="sxs-lookup"><span data-stu-id="78058-123">Office apps\*</span></span>    | [<span data-ttu-id="78058-124">Microsoft 365-applikationer för affärsverksamhet</span><span class="sxs-lookup"><span data-stu-id="78058-124">Microsoft 365 Apps for business</span></span>](#office-365-business)    | <span data-ttu-id="78058-125"> Microsoft 365 Apps för företag</span><span class="sxs-lookup"><span data-stu-id="78058-125">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="78058-126">**Produktivitetsprogram för molnet**</span><span class="sxs-lookup"><span data-stu-id="78058-126">**Cloud productivity apps**</span></span>        | | |
| <span data-ttu-id="78058-127">Exchange Online och Outlook</span><span class="sxs-lookup"><span data-stu-id="78058-127">Exchange Online and Outlook</span></span>    | <span data-ttu-id="78058-128">50 GB lagringsutrymme per postlåda och obegränsat Exchange Online arkivering</span><span class="sxs-lookup"><span data-stu-id="78058-128">50 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span>    | <span data-ttu-id="78058-129">100 GB lagringsutrymme per postlåda och obegränsat Exchange Online arkivering</span><span class="sxs-lookup"><span data-stu-id="78058-129">100 GB storage limit per mailbox and unlimited Exchange Online archiving</span></span> |
| <span data-ttu-id="78058-130">Teams</span><span class="sxs-lookup"><span data-stu-id="78058-130">Teams</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="78058-133">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="78058-133">OneDrive for Business</span></span>    | <span data-ttu-id="78058-134">1 TB lagringsgräns per användare</span><span class="sxs-lookup"><span data-stu-id="78058-134">1 TB storage limit per user</span></span>    | <span data-ttu-id="78058-135">Obegränsat</span><span class="sxs-lookup"><span data-stu-id="78058-135">Unlimited</span></span> |
| <span data-ttu-id="78058-136">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="78058-136">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="78058-139">**Skydd mot hot**</span><span class="sxs-lookup"><span data-stu-id="78058-139">**Threat Protection**</span></span>        | | |
| <span data-ttu-id="78058-140">Funktioner för att minska attackytan</span><span class="sxs-lookup"><span data-stu-id="78058-140">Attack surface reduction capabilities</span></span>    | [<span data-ttu-id="78058-141">Visa den här listan</span><span class="sxs-lookup"><span data-stu-id="78058-141">See this list</span></span>](#threat-protection) | <span data-ttu-id="78058-142">Företagshantering av maskinvarubaserad avgränsning för Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="78058-142">Enterprise management of hardware-based isolation for Microsoft Edge</span></span> |
| <span data-ttu-id="78058-143">Microsoft Defender för Office 365 Abonnemang 1</span><span class="sxs-lookup"><span data-stu-id="78058-143">Defender for Office 365 Plan 1</span></span> | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | <span data-ttu-id="78058-145">Ingår inte men kan läggas till på</span><span class="sxs-lookup"><span data-stu-id="78058-145">Not included, but can be added on</span></span> |
| <span data-ttu-id="78058-146">**Identitetshantering**</span><span class="sxs-lookup"><span data-stu-id="78058-146">**Identity management**</span></span>        | | |
| <span data-ttu-id="78058-147">Självbetjäning för återställning av lösenord för hybridkonton för Azure Active Directory (Azure AD), Azure AD-multifaktorautentisering (MFA), villkorsstyrd åtkomst, tillbakaskrivning av lösenord för lokala identiteter</span><span class="sxs-lookup"><span data-stu-id="78058-147">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="78058-150">Identifiering av molnapp, Azure AD Anslut hälsa</span><span class="sxs-lookup"><span data-stu-id="78058-150">Cloud App Discovery, Azure AD Connect Health</span></span>    |     | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="78058-152">Azure AD Office 365-appar Enkel inloggning Sign-On (SSO): 10 program per användare (SaaS-galleriappar som Salesforce)\*</span><span class="sxs-lookup"><span data-stu-id="78058-152">Azure AD Office 365 apps Single Sign-On (SSO): 10 apps per user (Gallery SaaS apps such as Salesforce)\*</span></span> | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="78058-155">Azure AD Premium 1 SSO: ingen gräns (lokala appar via Azure AD-programproxy och icke-galleriappar med hjälp Self-Service mallar för appintegrering)</span><span class="sxs-lookup"><span data-stu-id="78058-155">Azure AD Premium 1 SSO: no limit (On-premises apps through Azure AD Application Proxy and non-gallery apps using Self-Service App Integration templates)</span></span>    |     | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="78058-157">**Enhets- och apphantering**</span><span class="sxs-lookup"><span data-stu-id="78058-157">**Device and app management**</span></span>        | | |
| <span data-ttu-id="78058-158">Microsoft Intune, Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="78058-158">Microsoft Intune, Windows Autopilot</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
|<span data-ttu-id="78058-161">Virtual Desktop Access (VDA)</span><span class="sxs-lookup"><span data-stu-id="78058-161">Virtual Desktop Access (VDA)</span></span>    |  |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
|<span data-ttu-id="78058-163">Windows Virtuellt skrivbord (WVD)</span><span class="sxs-lookup"><span data-stu-id="78058-163">Windows Virtual Desktop (WVD)</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png) |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
|<span data-ttu-id="78058-166">Aktivering av delad dator (SCA)</span><span class="sxs-lookup"><span data-stu-id="78058-166">Shared Computer Activation (SCA)</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png) |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="78058-169">Microsofts paket för skrivbordsoptimering</span><span class="sxs-lookup"><span data-stu-id="78058-169">Microsoft Desktop Optimization Package</span></span>    | |     ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="78058-171">**Informationsskydd**</span><span class="sxs-lookup"><span data-stu-id="78058-171">**Information protection**</span></span>        | | |
| <span data-ttu-id="78058-172">Office 365 Dataförlustskydd, Azure Information Protection Plan 1</span><span class="sxs-lookup"><span data-stu-id="78058-172">Office 365 Data Loss Prevention, Azure Information Protection Plan 1</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="78058-175">Fönsterinformationsskydd för slutpunkt DLP</span><span class="sxs-lookup"><span data-stu-id="78058-175">Window Information Protection for endpoint DLP</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="78058-178">**Klientåtkomstlicens (CAL-rättigheter)**</span><span class="sxs-lookup"><span data-stu-id="78058-178">**Client Access License (CAL rights)**</span></span>    | | |
| <span data-ttu-id="78058-179">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span><span class="sxs-lookup"><span data-stu-id="78058-179">Enterprise CAL Suite (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)</span></span>| |         ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="78058-181">**Efterlevnad**</span><span class="sxs-lookup"><span data-stu-id="78058-181">**Compliance**</span></span>        | | |
| <span data-ttu-id="78058-182">Obegränsad e-postarkivering</span><span class="sxs-lookup"><span data-stu-id="78058-182">Unlimited email archiving</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="78058-185">Efterlevnadshanteraren</span><span class="sxs-lookup"><span data-stu-id="78058-185">Compliance Manager</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="78058-188">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="78058-188">eDiscovery</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="78058-191">Bevarande av juridiska skäl på plats och bevarande av juridiska skäl</span><span class="sxs-lookup"><span data-stu-id="78058-191">In-place hold and litigation hold</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
| <span data-ttu-id="78058-194">Bevarandetaggar (MRM) för hantering av meddelandeposter (MRM) och bevarandeprinciper</span><span class="sxs-lookup"><span data-stu-id="78058-194">Messaging Records Management (MRM) retention tags and retention policies</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Microsoft 365 E3](../media/check-mark.png) |
||||

<span data-ttu-id="78058-197">\* Användare som har tilldelats åtkomst till SaaS-appar kan få SSO-åtkomst till upp till 10 appar.</span><span class="sxs-lookup"><span data-stu-id="78058-197">\* Users who have been assigned access to SaaS apps can get SSO access to up to 10 apps.</span></span> <span data-ttu-id="78058-198">Administratörer kan konfigurera SSO och ändra användaråtkomst till olika SaaS-appar, men SSO-åtkomst är endast tillåten för 10 appar per användare i taget.</span><span class="sxs-lookup"><span data-stu-id="78058-198">Admins can configure SSO and change user access to different SaaS apps, but SSO access is only allowed for 10 apps per user at a time.</span></span> <span data-ttu-id="78058-199">Alla Office 365 räknas som en enskild app.</span><span class="sxs-lookup"><span data-stu-id="78058-199">All Office 365 apps are counted as a single app.</span></span>

## <a name="migration"></a><span data-ttu-id="78058-200">Migrering</span><span class="sxs-lookup"><span data-stu-id="78058-200">Migration</span></span>

<span data-ttu-id="78058-201">Migrera genom att samarbeta med din partner för att flytta din Microsoft 365 Business Premium-prenumeration och licenser till ett lämpligt Microsoft 365 E3-abonnemang med dess licenser.</span><span class="sxs-lookup"><span data-stu-id="78058-201">To migrate, work with your partner to move your Microsoft 365 Business Premium subscription and licenses to a suitable Microsoft 365 E3 subscription with its licenses.</span></span>

<span data-ttu-id="78058-202">I följande avsnitt beskrivs vilka ändringar du behöver göra, om det finns några, och vad du kan göra efter migreringen.</span><span class="sxs-lookup"><span data-stu-id="78058-202">The following sections describe what changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="microsoft-365-subscription-configuration-and-data"></a><span data-ttu-id="78058-203">Microsoft 365 prenumerationskonfiguration och data</span><span class="sxs-lookup"><span data-stu-id="78058-203">Microsoft 365 subscription configuration and data</span></span>

<span data-ttu-id="78058-204">Du behöver inte göra några ändringar i din nuvarande prenumeration eller dina data innan du migrerar, vilket omfattar:</span><span class="sxs-lookup"><span data-stu-id="78058-204">You don't need to make any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="78058-205">Prenumerationskonfiguration, till exempel DNS-domännamn.</span><span class="sxs-lookup"><span data-stu-id="78058-205">Subscription configuration, such as DNS domain names.</span></span>
- <span data-ttu-id="78058-206">Användar- och gruppkonton och autentiseringsinställningar, till exempel principer för multifaktorautentisering eller villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="78058-206">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="78058-207">Produktivitetstjänstkonfigurationer och deras data, till exempel Teams, Exchange Online postlådor, SharePoint Online-webbplatser, OneDrive för företag-mappar och OneNote-anteckningsböcker.</span><span class="sxs-lookup"><span data-stu-id="78058-207">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

<span data-ttu-id="78058-208">Användarna kan nu använda obegränsat lagringsutrymme i Exchange Online postlådor och OneDrive för företag mappar.</span><span class="sxs-lookup"><span data-stu-id="78058-208">Your users can now enjoy unlimited storage in the Exchange Online mailboxes and OneDrive for Business folders.</span></span>

<span data-ttu-id="78058-209">Du kan börja använda Cloud App Discovery, Azure AD Anslut Health och SSO för fler än 10 appar.</span><span class="sxs-lookup"><span data-stu-id="78058-209">You can begin using Cloud App Discovery, Azure AD Connect Health, and SSO for more than 10 apps.</span></span>

<a name="threat-protection"></a>
### <a name="threat-protection"></a><span data-ttu-id="78058-210">Skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="78058-210">Threat protection</span></span>

<span data-ttu-id="78058-211">Windows 10 Business omfattar följande skydd:</span><span class="sxs-lookup"><span data-stu-id="78058-211">Windows 10 Business includes these protections:</span></span>

- <span data-ttu-id="78058-212">Tvingande integritet för operativsystemets uppstartsprocess</span><span class="sxs-lookup"><span data-stu-id="78058-212">Integrity enforcement of operating system boot up process</span></span>
- <span data-ttu-id="78058-213">Tvingande integritet för känsliga operativsystemkomponenter</span><span class="sxs-lookup"><span data-stu-id="78058-213">Integrity enforcement of sensitive operating components</span></span>
- <span data-ttu-id="78058-214">Avancerade sårbarheter och nolldagars minskningar av sårbarheter</span><span class="sxs-lookup"><span data-stu-id="78058-214">Advanced vulnerability and zero-day exploit mitigations</span></span>
- <span data-ttu-id="78058-215">Ryktesbaserat nätverksskydd för Microsoft Edge, Internet Explorer och Chrome</span><span class="sxs-lookup"><span data-stu-id="78058-215">Reputation-based network protection for Microsoft Edge, Internet Explorer, and Chrome</span></span>
- <span data-ttu-id="78058-216">Värdbaserad brandvägg</span><span class="sxs-lookup"><span data-stu-id="78058-216">Host-based firewall</span></span>
- <span data-ttu-id="78058-217">Minskning av utpressningstrojaner</span><span class="sxs-lookup"><span data-stu-id="78058-217">Ransomware mitigations</span></span>
- <span data-ttu-id="78058-218">Maskinvarubaserad avgränsning för Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="78058-218">Hardware-based isolation for Microsoft Edge</span></span>
- <span data-ttu-id="78058-219">Programkontroll som drivs av intelligent Graph</span><span class="sxs-lookup"><span data-stu-id="78058-219">Application control powered by the Intelligent Security Graph</span></span>
- <span data-ttu-id="78058-220">Enhetskontroll (USB)</span><span class="sxs-lookup"><span data-stu-id="78058-220">Device control (USB)</span></span>
- <span data-ttu-id="78058-221">Nätverksskydd för webbaserade hot</span><span class="sxs-lookup"><span data-stu-id="78058-221">Network protection for web-based threats</span></span>
- <span data-ttu-id="78058-222">Skydd mot intrång i värden</span><span class="sxs-lookup"><span data-stu-id="78058-222">Host intrusion prevention rules</span></span>

<span data-ttu-id="78058-223">Windows 10 Enterprise E3 innehåller även företagshantering av maskinvarubaserad avgränsning för Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="78058-223">Windows 10 Enterprise E3 also includes enterprise management of hardware-based isolation for Microsoft Edge.</span></span>

> [!NOTE]
> <span data-ttu-id="78058-224">Användare som migreras till Microsoft 365 E3 måste ha en Microsoft Defender för Office 365 licens för fortsatt skydd mot hot.</span><span class="sxs-lookup"><span data-stu-id="78058-224">Users migrated to Microsoft 365 E3 will each require a Microsoft Defender for Office 365 license for continued threat protection.</span></span> <span data-ttu-id="78058-225">Se till att köpa ytterligare Defender Office 365 licens så att alla användare som omfattas av Defender för Office 365 licensieras.</span><span class="sxs-lookup"><span data-stu-id="78058-225">Be sure to purchase additional Defender for Office 365 licenses so that all of the users in scope of your Defender for Office 365 polices are licensed.</span></span>

### <a name="device-management-with-intune"></a><span data-ttu-id="78058-226">Enhetshantering med Intune</span><span class="sxs-lookup"><span data-stu-id="78058-226">Device management with Intune</span></span>

<span data-ttu-id="78058-227">Du behöver inte göra några ändringar i din aktuella Intune-konfiguration innan du migrerar, vilket omfattar registrerade enheter och enhets- och appinställningar.</span><span class="sxs-lookup"><span data-stu-id="78058-227">You don't need to make any changes to your current Intune configuration before migrating, which includes enrolled devices and device and app settings.</span></span>

### <a name="windows-10"></a><span data-ttu-id="78058-228">Windows 10</span><span class="sxs-lookup"><span data-stu-id="78058-228">Windows 10</span></span>

<span data-ttu-id="78058-229">Microsoft 365 Business Premium innehåller Windows 10 Business, som du kan installera med Windows AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="78058-229">Microsoft 365 Business Premium includes Windows 10 Business, which you can install with Windows AutoPilot.</span></span> <span data-ttu-id="78058-230">När du migrerar till Microsoft 365 E3 inkluderar varje användarlicens Windows 10 Enterprise E3, som du även kan installera med Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="78058-230">When you migrate to Microsoft 365 E3, each user license includes Windows 10 Enterprise E3, which you can also install with Windows Autopilot.</span></span>

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a><span data-ttu-id="78058-231">Microsoft 365-applikationer för affärsverksamhet</span><span class="sxs-lookup"><span data-stu-id="78058-231">Microsoft 365 Apps for business</span></span>

<span data-ttu-id="78058-232">Din Microsoft 365-applikationer för affärsverksamhet klient som är installerad på dina enheter börjar automatiskt använda funktionerna i Microsoft 365-appar för företag.</span><span class="sxs-lookup"><span data-stu-id="78058-232">Your Microsoft 365 Apps for business client installed on your devices will automatically begin to use the features of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="78058-233">Efter migreringen kan du nu använda:</span><span class="sxs-lookup"><span data-stu-id="78058-233">After migration, you can now use:</span></span>

- <span data-ttu-id="78058-234">Grupprincipstöd</span><span class="sxs-lookup"><span data-stu-id="78058-234">Group Policy support</span></span>
- <span data-ttu-id="78058-235">Spreadsheet compare and inquire</span><span class="sxs-lookup"><span data-stu-id="78058-235">Spreadsheet compare and inquire</span></span>
- <span data-ttu-id="78058-236">Business Intelligence</span><span class="sxs-lookup"><span data-stu-id="78058-236">Business intelligence</span></span>
