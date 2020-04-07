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
search.appverid:
- BCS160
- MET150
description: Läs om hur du flyttar ditt företag till Microsoft 365 Business från Office 365 E3.
ms.openlocfilehash: cff6166529df2e56ba948a9bd3ea4594fb295b08
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153538"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business"></a><span data-ttu-id="3d124-103">Migrera från Office 365 E3 till Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="3d124-103">Migrating from Office 365 E3 to Microsoft 365 Business</span></span> 

<span data-ttu-id="3d124-104">Microsoft 365 Business har allt du behöver för ditt småföretag och kombinerar de förstklassiga molnbaserade produktivitetsapparna med enkel enhetshantering och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="3d124-104">Microsoft 365 Business has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="3d124-105">Om du för närvarande har en Office 365 E3-prenumeration, men inte har fler än 300 anställda, kan du överväga att byta till Microsoft 365 Business för extra säkerhetsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="3d124-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business for added security features.</span></span>

<span data-ttu-id="3d124-106">Migrering är enkelt: Först byter du licenser och all data- och användarinformation i din nuvarande prenumeration bibehålls.</span><span class="sxs-lookup"><span data-stu-id="3d124-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="3d124-107">Efter migreringen måste du konfigurera de funktioner som läggs till i Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="3d124-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business"></a><span data-ttu-id="3d124-108">Skillnader mellan Office 365 E3 och Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="3d124-108">Differences between Office 365 E3 and Microsoft 365 Business</span></span>

<span data-ttu-id="3d124-109">I den här tabellen visas skillnaderna mellan Microsoft 365 Business och Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="3d124-109">This table shows the differences between Microsoft 365 Business and Office 365 E3.</span></span>

| <span data-ttu-id="3d124-110">Funktion</span><span class="sxs-lookup"><span data-stu-id="3d124-110">Feature</span></span>    | <span data-ttu-id="3d124-111">Stöd i Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="3d124-111">Support in Microsoft 365 Business</span></span>    | <span data-ttu-id="3d124-112">Stöd i Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="3d124-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="3d124-113">**Lokalt**</span><span class="sxs-lookup"><span data-stu-id="3d124-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="3d124-114">Office-appar<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3d124-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="3d124-115">Office 365 Business</span><span class="sxs-lookup"><span data-stu-id="3d124-115">Office 365 Business</span></span>    | <span data-ttu-id="3d124-116">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="3d124-116">Office 365 ProPlus</span></span> | 
| <span data-ttu-id="3d124-117">**Molnproduktivitetsappar**</span><span class="sxs-lookup"><span data-stu-id="3d124-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="3d124-118">Exchange Online och Outlook</span><span class="sxs-lookup"><span data-stu-id="3d124-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="3d124-119">Lagringsgräns på 50 GB per postlåda och obegränsad Exchange Online-arkivering</span><span class="sxs-lookup"><span data-stu-id="3d124-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="3d124-120">Lagringsgräns på 100 GB per postlåda och obegränsad Exchange Online-arkivering</span><span class="sxs-lookup"><span data-stu-id="3d124-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="3d124-121">Teams</span><span class="sxs-lookup"><span data-stu-id="3d124-121">Teams</span></span>    | ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="3d124-124">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="3d124-124">OneDrive for Business</span></span>    | <span data-ttu-id="3d124-125">1 TB lagringsgräns per användare</span><span class="sxs-lookup"><span data-stu-id="3d124-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="3d124-126">Obegränsad</span><span class="sxs-lookup"><span data-stu-id="3d124-126">Unlimited</span></span> | 
| <span data-ttu-id="3d124-127">Yammer, SharePoint Online, Planerare, Stream</span><span class="sxs-lookup"><span data-stu-id="3d124-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="3d124-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="3d124-130">StaffHub</span></span>    | ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="3d124-133">Outlook kundansvarig, MileIQ</span><span class="sxs-lookup"><span data-stu-id="3d124-133">Outlook Customer Manager, MileIQ</span></span>    | ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | | 
| <span data-ttu-id="3d124-135">**Skydd mot hot**</span><span class="sxs-lookup"><span data-stu-id="3d124-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="3d124-136">Office 365 Advanced Threat Protection (ATP) Plan 1</span><span class="sxs-lookup"><span data-stu-id="3d124-136">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | <span data-ttu-id="3d124-138">Ingår inte, men kan läggas till på</span><span class="sxs-lookup"><span data-stu-id="3d124-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="3d124-139">**Identitetshantering**</span><span class="sxs-lookup"><span data-stu-id="3d124-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="3d124-140">Återställning av lösenord för självbetjäning för hybridkonton i Azure Active Directory (Azure AD), Azure Multi-Factor Authentication, Villkorlig åtkomst, återställning av lösenord för lokala identiteter</span><span class="sxs-lookup"><span data-stu-id="3d124-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure Multi-Factor Authentication, Conditional Access, password writeback for on-premises identities</span></span>|     ![Ingår i Microsoft 365 Business](../media/check-mark.png)    |  | 
| <span data-ttu-id="3d124-142">**Enhets- och apphantering**</span><span class="sxs-lookup"><span data-stu-id="3d124-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="3d124-143">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="3d124-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![Ingår i Microsoft 365 Business](../media/check-mark.png)    |  |
| <span data-ttu-id="3d124-145">Aktivering av delad dator</span><span class="sxs-lookup"><span data-stu-id="3d124-145">Shared computer activation</span></span>|     ![Ingår i Microsoft 365 Business](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="3d124-148">Uppgradera rättigheter till Windows 10 Pro från Win 7/8.1 Pro-licenser</span><span class="sxs-lookup"><span data-stu-id="3d124-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Ingår i Microsoft 365 Business](../media/check-mark.png)    || 
| <span data-ttu-id="3d124-150">**Informationsskydd**</span><span class="sxs-lookup"><span data-stu-id="3d124-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="3d124-151">Förebyggande av dataförlust i Office 365</span><span class="sxs-lookup"><span data-stu-id="3d124-151">Office 365 Data Loss Prevention</span></span>|    ![Ingår i Microsoft 365 Business](../media/check-mark.png)|![Ingår i Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="3d124-154">Azure Information Protection Plan 1, Bitlocker verkställighet</span><span class="sxs-lookup"><span data-stu-id="3d124-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Ingår i Microsoft 365 Business](../media/check-mark.png)||
|<span data-ttu-id="3d124-156">Azure Information Protection Plan 1, känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="3d124-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Ingår i Microsoft 365 Business](../media/check-mark.png)||
|<span data-ttu-id="3d124-158">**Licens för klientåtkomst (CAL-rättigheter)**</span><span class="sxs-lookup"><span data-stu-id="3d124-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="3d124-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="3d124-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Ingår i Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="3d124-161"><sup>1</sup> Microsoft 365 Business-versionen av Office-apparna innehåller inte volymaktivering via grupprincip, programtelemetri, uppdateringskontroller, kalkylbladsjämförelser och förfrågningar eller Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="3d124-161"><sup>1</sup> The Microsoft 365 Business version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="3d124-162">Migration</span><span class="sxs-lookup"><span data-stu-id="3d124-162">Migration</span></span>

<span data-ttu-id="3d124-163">Information om hur du migrerar prenumerationen finns i [Ändra abonnemang manuellt](../commerce/subscriptions/change-plans-manually.md) för instruktioner om du bara vill flytta några personer till Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="3d124-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business.</span></span> <span data-ttu-id="3d124-164">Du kan också [uppgradera alla automatiskt](../commerce/subscriptions/upgrade-to-different-plan.md)eller arbeta med en partner för att flytta din E3-prenumeration och dina licenser till en Microsoft 365 Business-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="3d124-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business subscription.</span></span>
<span data-ttu-id="3d124-165">I följande avsnitt beskrivs de ändringar du behöver göra, om några, och vad du kan göra efter migreringen.</span><span class="sxs-lookup"><span data-stu-id="3d124-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="3d124-166">Konfiguration och data för Office 365 E3-prenumeration</span><span class="sxs-lookup"><span data-stu-id="3d124-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="3d124-167">Du behöver inte göra några ändringar i din aktuella prenumeration eller dina data innan du migrerar, vilket inkluderar:</span><span class="sxs-lookup"><span data-stu-id="3d124-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="3d124-168">Prenumerationskonfiguration, till exempel DNS-poster och domännamn.</span><span class="sxs-lookup"><span data-stu-id="3d124-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="3d124-169">Användar- och gruppkonton och autentiseringsinställningar, till exempel multifaktorautentisering eller principer för villkorlig åtkomst.</span><span class="sxs-lookup"><span data-stu-id="3d124-169">User and group accounts and authentication settings, such as multi factor authentication or Conditional Access policies.</span></span>
- <span data-ttu-id="3d124-170">Produktivitetstjänstkonfigurationer och deras data, till exempel Teams, Exchange Online-postlådor, SharePoint Online-webbplatser, OneDrive för företag-mappar och OneNote-anteckningsböcker.</span><span class="sxs-lookup"><span data-stu-id="3d124-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>

### <a name="windows-10"></a><span data-ttu-id="3d124-171">Windows 10</span><span class="sxs-lookup"><span data-stu-id="3d124-171">Windows 10</span></span>

<span data-ttu-id="3d124-172">Om windows inte redan finns på Windows Pro Creator-uppdateringen [uppgraderar du dem till Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="3d124-172">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="3d124-173">Konfigurera principer för att skydda användarenheter och filer</span><span class="sxs-lookup"><span data-stu-id="3d124-173">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="3d124-174">Om du konfigurerar Office 365 MDM-principer och -enheter visas dessa enheter på sidan **Enheter** i administrationscentret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3d124-174">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3d124-175">Alla principer som du har ställt in visas i listan över klassiska principer i [Intune-portalen](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span><span class="sxs-lookup"><span data-stu-id="3d124-175">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="3d124-176">När du har tilldelat licenser till Microsoft 365 Business kan du börja skydda användarnas enheter och filer.</span><span class="sxs-lookup"><span data-stu-id="3d124-176">After you have assigned licenses to Microsoft 365 Business, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="3d124-177">Om du har uppgraderat alla i organisationen till Microsoft 365 Business visas installationsguiden på startsidan och kan följa stegen [Konfigurera Microsoft 365 Business i installationsguiden](set-up.md) för att skydda filer och mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="3d124-177">If you upgraded everyone in your organization to Microsoft 365 Business, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="3d124-178">Du kan också utföra de här stegen på sidan Enheter:</span><span class="sxs-lookup"><span data-stu-id="3d124-178">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="3d124-179">I administrationscentret, i den vänstra navigeringscentralen, går du till **Enhetsprinciper** \> **Policies**.</span><span class="sxs-lookup"><span data-stu-id="3d124-179">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="3d124-180">På sidan **Enhetsprinciper** väljer du **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="3d124-180">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="3d124-181">I fönstret **Lägg till princip** ger du principen ett namn och väljer sedan en **principtyp** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="3d124-181">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="3d124-182">Du kan ställa in programprinciper för att skydda filer på Android- och iPhone-enheter samt Windows 10, och du kan ställa in enhetskonfigurationsprinciper för företagsägda Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="3d124-182">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="3d124-183">Mer information finns i följande länkar:</span><span class="sxs-lookup"><span data-stu-id="3d124-183">See the following links for details:</span></span>
    
  - [<span data-ttu-id="3d124-184">Ange inställningar för appskydd för Android- eller iOS-enheter</span><span class="sxs-lookup"><span data-stu-id="3d124-184">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="3d124-185">Ange programskyddsinställningar för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="3d124-185">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="3d124-186">Ange inställningar för enhetsskydd för Windows 10-datorer</span><span class="sxs-lookup"><span data-stu-id="3d124-186">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="3d124-187">När du har ställt in principer kan du och dina anställda konfigurera enheter:</span><span class="sxs-lookup"><span data-stu-id="3d124-187">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="3d124-188">Se [Konfigurera Windows-enheter för Microsoft 365 Business-användare](set-up-windows-devices.md) för steg för Windows-enheter.</span><span class="sxs-lookup"><span data-stu-id="3d124-188">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="3d124-189">Se [Konfigurera mobila enheter för Microsoft 365 Business-användare](set-up-mobile-devices.md) för steg för Android-telefoner och iPhone.</span><span class="sxs-lookup"><span data-stu-id="3d124-189">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 

### <a name="threat-protection"></a><span data-ttu-id="3d124-190">Skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="3d124-190">Threat protection</span></span>

<span data-ttu-id="3d124-191">När du har migrerat till Microsoft 365 Business har du Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="3d124-191">After migrating to Microsoft 365 Business, you have Office 365 ATP.</span></span> <span data-ttu-id="3d124-192">Mer om du vill ha en översikt i [Office 365 ATP.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)</span><span class="sxs-lookup"><span data-stu-id="3d124-192">See [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) for an overview.</span></span> <span data-ttu-id="3d124-193">Information om hur du konfigurerar finns [i konfigurera ATP-säkra länkar,](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa) [konfigurera ATP-säkra bilagor](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)och konfigurera [ATP-anti-nätfiske](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span><span class="sxs-lookup"><span data-stu-id="3d124-193">To set up, see [set up ATP safe links](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [set up ATP safe attachments](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up ATP anti-phishing](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="3d124-194">Känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="3d124-194">Sensitivity labels</span></span>

<span data-ttu-id="3d124-195">Om du vill börja använda känslighetsetiketter läser du [Översikt över känslighetsetiketter](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) och [skapar och hanterar video för känslighetsetiketter.](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)</span><span class="sxs-lookup"><span data-stu-id="3d124-195">To start using sensitivity labels, see [Overview of sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) and [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
