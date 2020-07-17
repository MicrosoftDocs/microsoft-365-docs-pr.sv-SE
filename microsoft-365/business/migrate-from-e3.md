---
title: Migrera till Microsoft 365 Business från Office 365 E3
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
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
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Läs om hur du flyttar ditt företag till Microsoft 365 Business Premium från Office 365 E3.
ms.openlocfilehash: d72f0c52a745ff973868b6fdaa95efa1a37a3dbd
ms.sourcegitcommit: e5bc49f0a25954d008b6cc09c2b98bb7bfe1aa2f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785934"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="440fb-103">Migrera från Office 365 E3 till Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="440fb-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span> 

<span data-ttu-id="440fb-104">Microsoft 365 Business Premium har allt du behöver för ditt småföretag och kombinerar de förstklassiga molnbaserade produktivitetsapparna med enkel enhetshantering och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="440fb-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="440fb-105">Om du för närvarande har en Office 365 E3-prenumeration, men inte har fler än 300 anställda, kan du överväga att byta till Microsoft 365 Business Premium för extra säkerhetsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="440fb-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="440fb-106">Migrering är enkelt: Först byter du licenser och all data- och användarinformation i din aktuella prenumeration upprätthålls.</span><span class="sxs-lookup"><span data-stu-id="440fb-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="440fb-107">Efter migreringen måste du konfigurera de funktioner som läggs till i Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="440fb-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="440fb-108">Skillnader mellan Office 365 E3 och Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="440fb-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="440fb-109">I den här tabellen visas skillnaderna mellan Microsoft 365 Business Premium och Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="440fb-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="440fb-110">Funktion</span><span class="sxs-lookup"><span data-stu-id="440fb-110">Feature</span></span>    | <span data-ttu-id="440fb-111">Stöd i Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="440fb-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="440fb-112">Stöd i Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="440fb-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="440fb-113">**Lokalt**</span><span class="sxs-lookup"><span data-stu-id="440fb-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="440fb-114">Office-appar<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="440fb-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="440fb-115">Microsoft 365-applikationer för affärsverksamhet</span><span class="sxs-lookup"><span data-stu-id="440fb-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="440fb-116">Microsoft 365-applikationer för företag</span><span class="sxs-lookup"><span data-stu-id="440fb-116">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="440fb-117">**Molnproduktivitetsappar**</span><span class="sxs-lookup"><span data-stu-id="440fb-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="440fb-118">Exchange Online och Outlook</span><span class="sxs-lookup"><span data-stu-id="440fb-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="440fb-119">Lagringsgräns på 50 GB per postlåda och obegränsad Exchange Online-arkivering</span><span class="sxs-lookup"><span data-stu-id="440fb-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="440fb-120">Lagringsgräns på 100 GB per postlåda och obegränsad Exchange Online-arkivering</span><span class="sxs-lookup"><span data-stu-id="440fb-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="440fb-121">Teams</span><span class="sxs-lookup"><span data-stu-id="440fb-121">Teams</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="440fb-124">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="440fb-124">OneDrive for Business</span></span>    | <span data-ttu-id="440fb-125">1 TB lagringsgräns per användare</span><span class="sxs-lookup"><span data-stu-id="440fb-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="440fb-126">Obegränsad</span><span class="sxs-lookup"><span data-stu-id="440fb-126">Unlimited</span></span> | 
| <span data-ttu-id="440fb-127">Yammer, SharePoint Online, Planerare, Stream</span><span class="sxs-lookup"><span data-stu-id="440fb-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="440fb-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="440fb-130">StaffHub</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="440fb-133">Outlook kundansvarig, MileIQ</span><span class="sxs-lookup"><span data-stu-id="440fb-133">Outlook Customer Manager, MileIQ</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| <span data-ttu-id="440fb-135">**Skydd mot hot**</span><span class="sxs-lookup"><span data-stu-id="440fb-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="440fb-136">Office 365 Advanced Threat Protection (ATP) Plan 1</span><span class="sxs-lookup"><span data-stu-id="440fb-136">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | <span data-ttu-id="440fb-138">Ingår inte, men kan läggas till på</span><span class="sxs-lookup"><span data-stu-id="440fb-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="440fb-139">**Identitetshantering**</span><span class="sxs-lookup"><span data-stu-id="440fb-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="440fb-140">Återställning av lösenord för självbetjäning för hybridkonton i Azure Active Directory (Azure AD), Azure Multi-Factor Authentication (MFA), Villkorlig åtkomst, återställning av lösenord för lokala identiteter</span><span class="sxs-lookup"><span data-stu-id="440fb-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| <span data-ttu-id="440fb-142">**Enhets- och apphantering**</span><span class="sxs-lookup"><span data-stu-id="440fb-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="440fb-143">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="440fb-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="440fb-145">Aktivering av delad dator</span><span class="sxs-lookup"><span data-stu-id="440fb-145">Shared computer activation</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="440fb-148">Uppgradera rättigheter till Windows 10 Pro från Win 7/8.1 Pro-licenser</span><span class="sxs-lookup"><span data-stu-id="440fb-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    || 
| <span data-ttu-id="440fb-150">**Informationsskydd**</span><span class="sxs-lookup"><span data-stu-id="440fb-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="440fb-151">Förebyggande av dataförlust i Office 365</span><span class="sxs-lookup"><span data-stu-id="440fb-151">Office 365 Data Loss Prevention</span></span>|    ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)|![Ingår i Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="440fb-154">Azure Information Protection Plan 1, Bitlocker verkställighet</span><span class="sxs-lookup"><span data-stu-id="440fb-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="440fb-156">Azure Information Protection Plan 1, känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="440fb-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="440fb-158">**Licens för klientåtkomst (CAL-rättigheter)**</span><span class="sxs-lookup"><span data-stu-id="440fb-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="440fb-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="440fb-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Ingår i Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="440fb-161"><sup>1</sup> Microsoft 365 Business Premium-versionen av Office-apparna innehåller inte volymaktivering via grupprincip, programtelemetri, uppdateringskontroller, kalkylbladsjämförelser och förfrågningar eller business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="440fb-161"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="440fb-162">Migrering</span><span class="sxs-lookup"><span data-stu-id="440fb-162">Migration</span></span>

<span data-ttu-id="440fb-163">Information om hur du migrerar prenumerationen finns i [Ändra abonnemang manuellt](../commerce/subscriptions/change-plans-manually.md) för instruktioner om du bara vill flytta några personer till Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="440fb-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="440fb-164">Du kan också [uppgradera alla automatiskt](../commerce/subscriptions/upgrade-to-different-plan.md)eller arbeta med en partner för att flytta din E3-prenumeration och dina licenser till en Microsoft 365 Business Premium-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="440fb-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="440fb-165">I följande avsnitt beskrivs de ändringar du behöver göra, om några, och vad du kan göra efter migreringen.</span><span class="sxs-lookup"><span data-stu-id="440fb-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="440fb-166">Konfiguration och data för Office 365 E3-prenumerationer</span><span class="sxs-lookup"><span data-stu-id="440fb-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="440fb-167">Du behöver inte göra några ändringar i din aktuella prenumeration eller data innan du migrerar, vilket inkluderar:</span><span class="sxs-lookup"><span data-stu-id="440fb-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="440fb-168">Prenumerationskonfiguration, till exempel DNS-poster och domännamn.</span><span class="sxs-lookup"><span data-stu-id="440fb-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="440fb-169">Användar- och gruppkonton och autentiseringsinställningar, till exempel multifaktorautentisering eller principer för villkorlig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="440fb-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="440fb-170">Produktivitetstjänstkonfigurationer och deras data, till exempel Teams, Exchange Online-postlådor, SharePoint Online-webbplatser, OneDrive för företag-mappar och OneNote-anteckningsböcker.</span><span class="sxs-lookup"><span data-stu-id="440fb-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="440fb-171">Office-program skalas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="440fb-171">Office applications will scale automatically.</span></span> <span data-ttu-id="440fb-172">Office 365 modern licensiering kontrollerar användarens licenstilldelning var 72:e timme och konverterar Office-program till den version som matchar användarprenumerationen.</span><span class="sxs-lookup"><span data-stu-id="440fb-172">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="440fb-173">Windows 10</span><span class="sxs-lookup"><span data-stu-id="440fb-173">Windows 10</span></span>

<span data-ttu-id="440fb-174">Om windows inte redan finns på Windows Pro Creator-uppdateringen [uppgraderar du dem till Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="440fb-174">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="440fb-175">Konfigurera principer för att skydda användarenheter och filer</span><span class="sxs-lookup"><span data-stu-id="440fb-175">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="440fb-176">Om du ställer in Office 365 MDM-principer och -enheter visas dessa enheter på sidan **Enheter** i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="440fb-176">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="440fb-177">Alla principer som du ställer in visas i listan över klassiska principer i [Intune-portalen](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span><span class="sxs-lookup"><span data-stu-id="440fb-177">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="440fb-178">När du har tilldelat licenser till Microsoft 365 Business Premium kan du börja skydda användarnas enheter och filer.</span><span class="sxs-lookup"><span data-stu-id="440fb-178">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="440fb-179">Om du har uppgraderat alla i organisationen till Microsoft 365 Business Premium visas installationsguiden på startsidan och kan följa [installationsstegen Microsoft 365 Business Premium i installationsguiden](set-up.md) för att skydda filer och mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="440fb-179">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="440fb-180">Du kan också utföra de här stegen på sidan Enheter:</span><span class="sxs-lookup"><span data-stu-id="440fb-180">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="440fb-181">I administrationscentret, i den vänstra navigeringscentralen, går du till **Enhetsprinciper** \> **Policies**.</span><span class="sxs-lookup"><span data-stu-id="440fb-181">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="440fb-182">På sidan **Enhetsprinciper** väljer du **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="440fb-182">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="440fb-183">I fönstret **Lägg till princip** ger du principen ett namn och väljer sedan en **principtyp** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="440fb-183">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="440fb-184">Du kan ställa in programprinciper för att skydda filer på Android- och iPhone-enheter samt Windows 10, och du kan ställa in enhetskonfigurationsprinciper för företagsägda Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="440fb-184">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="440fb-185">Mer information finns i följande länkar:</span><span class="sxs-lookup"><span data-stu-id="440fb-185">See the following links for details:</span></span>
    
  - [<span data-ttu-id="440fb-186">Ange inställningar för appskydd för Android- eller iOS-enheter</span><span class="sxs-lookup"><span data-stu-id="440fb-186">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="440fb-187">Ange programskyddsinställningar för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="440fb-187">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="440fb-188">Ange inställningar för enhetsskydd för Windows 10-datorer</span><span class="sxs-lookup"><span data-stu-id="440fb-188">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="440fb-189">När du har ställt in principer kan du och dina anställda konfigurera enheter:</span><span class="sxs-lookup"><span data-stu-id="440fb-189">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="440fb-190">Se [Konfigurera Windows-enheter för Microsoft 365 Business Premium-användare](set-up-windows-devices.md) för steg för Windows-enheter.</span><span class="sxs-lookup"><span data-stu-id="440fb-190">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="440fb-191">Se [Konfigurera mobila enheter för Microsoft 365 Business Premium-användare](set-up-mobile-devices.md) för steg för Android-telefoner och iPhone.</span><span class="sxs-lookup"><span data-stu-id="440fb-191">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 

### <a name="threat-protection"></a><span data-ttu-id="440fb-192">Skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="440fb-192">Threat protection</span></span>

<span data-ttu-id="440fb-193">När du har migrerat till Microsoft 365 Business Premium har du Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="440fb-193">After migrating to Microsoft 365 Business Premium, you have Office 365 ATP.</span></span> <span data-ttu-id="440fb-194">Mer om du vill ha en översikt över [Office 365 ATP.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)</span><span class="sxs-lookup"><span data-stu-id="440fb-194">See [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) for an overview.</span></span> <span data-ttu-id="440fb-195">Information om hur du konfigurerar finns [i konfigurera ATP-säkra länkar,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa) [konfigurera ATP-säkra bilagor](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)och konfigurera [ATP-anti-nätfiske](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span><span class="sxs-lookup"><span data-stu-id="440fb-195">To set up, see [set up ATP safe links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up ATP safe attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up ATP anti-phishing](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="440fb-196">Känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="440fb-196">Sensitivity labels</span></span>

<span data-ttu-id="440fb-197">Om du vill börja använda känslighetsetiketter läser du [Översikt över känslighetsetiketter](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) och [skapar och hanterar känslighetsetiketter](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span><span class="sxs-lookup"><span data-stu-id="440fb-197">To start using sensitivity labels, see [Overview of sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) and [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
