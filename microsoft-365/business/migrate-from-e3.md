---
title: Migrera till Microsoft 365 Business från Office 365 E3
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
description: Lär dig hur du flyttar över företaget till Microsoft 365 Business Premium från Office 365 E3.
ms.openlocfilehash: f08b054473fdd63ec2372e81c776a1b64f89fe9d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244845"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="78c1b-103">Migrera från E3 Office 365 till Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="78c1b-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span>

<span data-ttu-id="78c1b-104">Microsoft 365 Business Premium finns allt du behöver för ditt småföretag. Kombinera de förstklassiga molnbaserade produktivitetsapparna med enkel enhetshantering och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="78c1b-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="78c1b-105">Om du för närvarande har en Office 365 E3-prenumeration, men inte har fler än 300 anställda, kan du överväga att byta till Microsoft 365 Business Premium för ytterligare säkerhetsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="78c1b-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="78c1b-106">Det är enkelt att migrera: Först byter du licens och alla data och användarinformation i den aktuella prenumerationen bevaras.</span><span class="sxs-lookup"><span data-stu-id="78c1b-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="78c1b-107">Efter migreringen måste du konfigurera de funktioner som läggs till i Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="78c1b-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="78c1b-108">Skillnader mellan Office 365 E3 och Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="78c1b-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="78c1b-109">I den här tabellen visas skillnaderna mellan Microsoft 365 Business Premium och Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="78c1b-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="78c1b-110">Funktion</span><span class="sxs-lookup"><span data-stu-id="78c1b-110">Feature</span></span>    | <span data-ttu-id="78c1b-111">Support i Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="78c1b-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="78c1b-112">Support i Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="78c1b-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="78c1b-113">**Lokalt**</span><span class="sxs-lookup"><span data-stu-id="78c1b-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="78c1b-114">Office appar<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="78c1b-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="78c1b-115">Microsoft 365-applikationer för affärsverksamhet</span><span class="sxs-lookup"><span data-stu-id="78c1b-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="78c1b-116">Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="78c1b-116">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="78c1b-117">**Produktivitetsprogram för molnet**</span><span class="sxs-lookup"><span data-stu-id="78c1b-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="78c1b-118">Exchange Online och Outlook</span><span class="sxs-lookup"><span data-stu-id="78c1b-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="78c1b-119">50 GB lagringsutrymme per postlåda och obegränsat antal Exchange Online - arkivering</span><span class="sxs-lookup"><span data-stu-id="78c1b-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="78c1b-120">100 GB lagringsutrymme per postlåda och obegränsat antal Exchange Online - arkivering</span><span class="sxs-lookup"><span data-stu-id="78c1b-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="78c1b-121">Teams</span><span class="sxs-lookup"><span data-stu-id="78c1b-121">Teams</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="78c1b-124">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="78c1b-124">OneDrive for Business</span></span>    | <span data-ttu-id="78c1b-125">1 TB lagringsgräns per användare</span><span class="sxs-lookup"><span data-stu-id="78c1b-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="78c1b-126">Obegränsat</span><span class="sxs-lookup"><span data-stu-id="78c1b-126">Unlimited</span></span> | 
| <span data-ttu-id="78c1b-127">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="78c1b-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="78c1b-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="78c1b-130">StaffHub</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="78c1b-133">MileIQ</span><span class="sxs-lookup"><span data-stu-id="78c1b-133">MileIQ</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| <span data-ttu-id="78c1b-135">**Skydd mot hot**</span><span class="sxs-lookup"><span data-stu-id="78c1b-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="78c1b-136">Microsoft Defender för Office 365 Abonnemang 1</span><span class="sxs-lookup"><span data-stu-id="78c1b-136">Defender for Office 365 Plan 1</span></span> | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | <span data-ttu-id="78c1b-138">Ingår inte men kan läggas till på</span><span class="sxs-lookup"><span data-stu-id="78c1b-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="78c1b-139">**Identitetshantering**</span><span class="sxs-lookup"><span data-stu-id="78c1b-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="78c1b-140">Självbetjäning för återställning av lösenord för hybridkonton för Azure Active Directory (Azure AD), Azure AD-multifaktorautentisering (MFA), villkorsstyrd åtkomst, tillbakaskrivning av lösenord för lokala identiteter</span><span class="sxs-lookup"><span data-stu-id="78c1b-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| <span data-ttu-id="78c1b-142">**Enhets- och apphantering**</span><span class="sxs-lookup"><span data-stu-id="78c1b-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="78c1b-143">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="78c1b-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="78c1b-145">Aktivering på delad dator</span><span class="sxs-lookup"><span data-stu-id="78c1b-145">Shared computer activation</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="78c1b-148">Uppgraderingsrättigheter till Windows 10 Pro från Win 7/8.1 Pro licenser</span><span class="sxs-lookup"><span data-stu-id="78c1b-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    || 
| <span data-ttu-id="78c1b-150">**Informationsskydd**</span><span class="sxs-lookup"><span data-stu-id="78c1b-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="78c1b-151">Office 365 Dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="78c1b-151">Office 365 Data Loss Prevention</span></span>|    ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)|![Ingår i Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="78c1b-154">Azure Information Protection plan 1, BitLocker verkställande</span><span class="sxs-lookup"><span data-stu-id="78c1b-154">Azure Information Protection Plan 1, BitLocker enforcement</span></span>|![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="78c1b-156">Azure Information Protection plan 1, känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="78c1b-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="78c1b-158">**Klientåtkomstlicens (CAL-rättigheter)**</span><span class="sxs-lookup"><span data-stu-id="78c1b-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="78c1b-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="78c1b-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Ingår i Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="78c1b-161"><sup>1</sup> Microsoft 365 Business Premium-versionen av Office-apparna omfattar inte volymaktivering via grupprinciper, app telemetri, uppdateringskontroller, kalkylbladsjämförelse och inquire samt Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="78c1b-161"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="78c1b-162">Migrering</span><span class="sxs-lookup"><span data-stu-id="78c1b-162">Migration</span></span>

<span data-ttu-id="78c1b-163">Anvisningar om hur du migrerar [din prenumeration finns i](../commerce/subscriptions/change-plans-manually.md) Ändra abonnemang manuellt om du bara vill flytta några få Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="78c1b-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="78c1b-164">Du kan också [uppgradera alla automatiskt](../commerce/subscriptions/upgrade-to-different-plan.md), eller samarbeta med en partner för att flytta din E3-prenumeration och dina licenser till en Microsoft 365 Business Premium prenumeration.</span><span class="sxs-lookup"><span data-stu-id="78c1b-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="78c1b-165">I följande avsnitt beskrivs de ändringar du behöver göra, om det finns några, och vad du kan göra efter migreringen.</span><span class="sxs-lookup"><span data-stu-id="78c1b-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="78c1b-166">Office 365 Konfiguration och data för E3-prenumeration</span><span class="sxs-lookup"><span data-stu-id="78c1b-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="78c1b-167">Du behöver inte göra några ändringar i din nuvarande prenumeration eller dina data innan du migrerar, vilket omfattar:</span><span class="sxs-lookup"><span data-stu-id="78c1b-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="78c1b-168">Prenumerationskonfiguration, till exempel DNS-poster och domännamn.</span><span class="sxs-lookup"><span data-stu-id="78c1b-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="78c1b-169">Användar- och gruppkonton och autentiseringsinställningar, till exempel principer för multifaktorautentisering eller villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="78c1b-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="78c1b-170">Produktivitetstjänstkonfigurationer och deras data, till exempel Teams, Exchange Online postlådor, SharePoint Online-webbplatser, OneDrive för företag-mappar och OneNote-anteckningsböcker.</span><span class="sxs-lookup"><span data-stu-id="78c1b-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="78c1b-171">Office skalas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="78c1b-171">Office applications will scale automatically.</span></span> <span data-ttu-id="78c1b-172">Office 365 modern licensiering kommer att kontrollera användarens licenstilldelning var 72:e timme och konverterar Office-program till den version som överensstämmer med användarprenumerationen.</span><span class="sxs-lookup"><span data-stu-id="78c1b-172">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="78c1b-173">Windows 10</span><span class="sxs-lookup"><span data-stu-id="78c1b-173">Windows 10</span></span>

<span data-ttu-id="78c1b-174">Om din Windows inte redan är på Windows Pro,uppgradera dem till [Creators Update Windows Pro dem.](upgrade-to-windows-pro-creators-update.md)</span><span class="sxs-lookup"><span data-stu-id="78c1b-174">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="78c1b-175">Konfigurera principer för att skydda användares enheter och filer</span><span class="sxs-lookup"><span data-stu-id="78c1b-175">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="78c1b-176">Om du inställningar Office 365 MDM-principer och -enheter visas  de enheterna på sidan Enheter Microsoft 365 administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="78c1b-176">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="78c1b-177">Alla principer som du har angett visas i listan med klassiska principer i [Intune-portalen.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)</span><span class="sxs-lookup"><span data-stu-id="78c1b-177">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="78c1b-178">När du har tilldelat licenser Microsoft 365 Business Premium kan du börja skydda användarnas enheter och filer.</span><span class="sxs-lookup"><span data-stu-id="78c1b-178">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="78c1b-179">Om du har uppgraderat alla i organisationen till Microsoft 365 Business Premium visas installationsguiden på startsidan och du kan följa Konfigurera [Microsoft 365 Business Premium](set-up.md) i installationsguiden för att skydda filer och mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="78c1b-179">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="78c1b-180">Du kan också utföra de här stegen på sidan Enheter:</span><span class="sxs-lookup"><span data-stu-id="78c1b-180">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="78c1b-181">I det vänstra navigeringsfältet i administrationscentret går du till **Principer för** \> **enheter.**</span><span class="sxs-lookup"><span data-stu-id="78c1b-181">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="78c1b-182">På sidan **Enhetsprinciper** väljer du Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="78c1b-182">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="78c1b-183">I fönstret **Lägg till** princip ger du principen ett namn och väljer sedan **en principtyp** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="78c1b-183">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="78c1b-184">Du kan konfigurera programprinciper för att skydda filer på Android och iPhone-enheter, samt Windows 10, och du kan konfigurera principer för enhetskonfiguration för företagsägda Windows 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="78c1b-184">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="78c1b-185">Se följande länkar för mer information:</span><span class="sxs-lookup"><span data-stu-id="78c1b-185">See the following links for details:</span></span>
    
  - [<span data-ttu-id="78c1b-186">Ange inställningar för appskydd för Android- eller iOS-enheter</span><span class="sxs-lookup"><span data-stu-id="78c1b-186">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="78c1b-187">Ange programskyddsinställningar för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="78c1b-187">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="78c1b-188">Ange inställningar för enhetsskydd för Windows 10-datorer</span><span class="sxs-lookup"><span data-stu-id="78c1b-188">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="78c1b-189">När du har angett principer kan du och dina anställda konfigurera enheter:</span><span class="sxs-lookup"><span data-stu-id="78c1b-189">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="78c1b-190">Se [Konfigurera Windows enheter för Microsoft 365 Business Premium för](set-up-windows-devices.md) anvisningar för Windows enheter.</span><span class="sxs-lookup"><span data-stu-id="78c1b-190">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="78c1b-191">Se [Konfigurera mobila enheter för Microsoft 365 Business Premium för anvisningar](set-up-mobile-devices.md) för Android-telefoner och iPhone.</span><span class="sxs-lookup"><span data-stu-id="78c1b-191">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="78c1b-192">Postlådans storlek</span><span class="sxs-lookup"><span data-stu-id="78c1b-192">Mailbox Size</span></span>

<span data-ttu-id="78c1b-193">Microsoft 365 Business Premium har en lagringsgräns på 50 GB eftersom den använder Exchange Online abonnemang 1.</span><span class="sxs-lookup"><span data-stu-id="78c1b-193">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="78c1b-194">När du migrerar till Microsoft 365 Business Premium rekommenderar vi att du tilldelar användaren ett Exchange Online abonnemang 2 och tar bort Exchange Online abonnemang 1 eftersom det inte är möjligt att tilldela båda.</span><span class="sxs-lookup"><span data-stu-id="78c1b-194">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>


### <a name="threat-protection"></a><span data-ttu-id="78c1b-195">Skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="78c1b-195">Threat protection</span></span>

<span data-ttu-id="78c1b-196">När du har migrerat till Microsoft 365 Business Premium har du Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="78c1b-196">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="78c1b-197">Se [Microsoft Defender för Office 365](../security/office-365-security/defender-for-office-365.md) en översikt.</span><span class="sxs-lookup"><span data-stu-id="78c1b-197">See [Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for an overview.</span></span> <span data-ttu-id="78c1b-198">Konfigurera genom att gå till [Konfigurera Valv,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)konfigurera [Valv](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)och konfigurera Skydd mot nätfiske [i Defender för Office 365.](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)</span><span class="sxs-lookup"><span data-stu-id="78c1b-198">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="78c1b-199">Känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="78c1b-199">Sensitivity labels</span></span>

<span data-ttu-id="78c1b-200">Om du vill börja använda känslighetsetiketter kan [du gå till Översikt över känslighetsetiketter](../compliance/sensitivity-labels.md) och skapa och hantera [känslighetsetiketter](../business-video/create-sensitivity-labels.md) video.</span><span class="sxs-lookup"><span data-stu-id="78c1b-200">To start using sensitivity labels, see [Overview of sensitivity labels](../compliance/sensitivity-labels.md) and [create and manage sensitivity labels](../business-video/create-sensitivity-labels.md) video.</span></span>
