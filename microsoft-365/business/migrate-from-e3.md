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
description: Om du har en Office 365 E3-prenumeration men inte har fler än 300 anställda kan du överväga att byta till Microsoft 365 Business Premium.
ms.openlocfilehash: d139d07c946ff3efed3db3a73eb5e1a4ae66c190
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623614"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="b5ee9-103">Migrera från E3 Office 365 till Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="b5ee9-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span>

<span data-ttu-id="b5ee9-104">Microsoft 365 Business Premium finns allt du behöver för ditt småföretag. Kombinera de förstklassiga molnbaserade produktivitetsapparna med enkel enhetshantering och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="b5ee9-105">Om du för närvarande har en Office 365 E3-prenumeration, men inte har fler än 300 anställda, kan du överväga att byta till Microsoft 365 Business Premium för ytterligare säkerhetsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="b5ee9-106">Det är enkelt att migrera: Först byter du licens och alla data och användarinformation i den aktuella prenumerationen bevaras.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="b5ee9-107">Efter migreringen måste du konfigurera de funktioner som läggs till i Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="b5ee9-108">Skillnader mellan Office 365 E3 och Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="b5ee9-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="b5ee9-109">I den här tabellen visas skillnaderna mellan Microsoft 365 Business Premium och Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="b5ee9-110">Funktion</span><span class="sxs-lookup"><span data-stu-id="b5ee9-110">Feature</span></span>    | <span data-ttu-id="b5ee9-111">Support i Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="b5ee9-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="b5ee9-112">Support i Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="b5ee9-112">Support in Office 365 E3</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="b5ee9-113">**Lokalt**</span><span class="sxs-lookup"><span data-stu-id="b5ee9-113">**On-premises**</span></span>        | | |
| <span data-ttu-id="b5ee9-114">Office appar<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b5ee9-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="b5ee9-115">Microsoft 365-applikationer för affärsverksamhet</span><span class="sxs-lookup"><span data-stu-id="b5ee9-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="b5ee9-116">Microsoft 365-applikationer för företag</span><span class="sxs-lookup"><span data-stu-id="b5ee9-116">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="b5ee9-117">**Produktivitetsprogram för molnet**</span><span class="sxs-lookup"><span data-stu-id="b5ee9-117">**Cloud productivity apps**</span></span>        | | |
| <span data-ttu-id="b5ee9-118">Exchange Online och Outlook</span><span class="sxs-lookup"><span data-stu-id="b5ee9-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="b5ee9-119">50 GB lagringsutrymme per postlåda och obegränsat antal Exchange Online - arkivering</span><span class="sxs-lookup"><span data-stu-id="b5ee9-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="b5ee9-120">100 GB lagringsutrymme per postlåda och obegränsat antal Exchange Online - arkivering</span><span class="sxs-lookup"><span data-stu-id="b5ee9-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> |
| <span data-ttu-id="b5ee9-121">Teams</span><span class="sxs-lookup"><span data-stu-id="b5ee9-121">Teams</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="b5ee9-124">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="b5ee9-124">OneDrive for Business</span></span>    | <span data-ttu-id="b5ee9-125">1 TB lagringsgräns per användare</span><span class="sxs-lookup"><span data-stu-id="b5ee9-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="b5ee9-126">Obegränsat</span><span class="sxs-lookup"><span data-stu-id="b5ee9-126">Unlimited</span></span> | 
| <span data-ttu-id="b5ee9-127">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="b5ee9-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="b5ee9-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="b5ee9-130">StaffHub</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) |
| <span data-ttu-id="b5ee9-133">**Skydd mot hot**</span><span class="sxs-lookup"><span data-stu-id="b5ee9-133">**Threat Protection**</span></span>        | | |
| <span data-ttu-id="b5ee9-134">Microsoft Defender för Office 365 Abonnemang 1</span><span class="sxs-lookup"><span data-stu-id="b5ee9-134">Defender for Office 365 Plan 1</span></span> | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | <span data-ttu-id="b5ee9-136">Ingår inte men kan läggas till på</span><span class="sxs-lookup"><span data-stu-id="b5ee9-136">Not included, but can be added on</span></span> |
| <span data-ttu-id="b5ee9-137">**Identitetshantering**</span><span class="sxs-lookup"><span data-stu-id="b5ee9-137">**Identity management**</span></span>        | | |
| <span data-ttu-id="b5ee9-138">Självbetjäning för återställning av lösenord för hybridkonton för Azure Active Directory (Azure AD), Azure AD-multifaktorautentisering (MFA), villkorsstyrd åtkomst, tillbakaskrivning av lösenord för lokala identiteter</span><span class="sxs-lookup"><span data-stu-id="b5ee9-138">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure AD multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="b5ee9-140">**Enhets- och apphantering**</span><span class="sxs-lookup"><span data-stu-id="b5ee9-140">**Device and app management**</span></span>        | | |
| <span data-ttu-id="b5ee9-141">Microsoft Intune, Windows AutoPilot</span><span class="sxs-lookup"><span data-stu-id="b5ee9-141">Microsoft Intune, Windows AutoPilot</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="b5ee9-143">Aktivering på delad dator</span><span class="sxs-lookup"><span data-stu-id="b5ee9-143">Shared computer activation</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="b5ee9-146">Uppgraderingsrättigheter till Windows 10 Pro från Win 7/8.1 Pro licenser</span><span class="sxs-lookup"><span data-stu-id="b5ee9-146">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    ||
| <span data-ttu-id="b5ee9-148">**Informationsskydd**</span><span class="sxs-lookup"><span data-stu-id="b5ee9-148">**Information protection**</span></span>        | | |
|<span data-ttu-id="b5ee9-149">Office 365 Dataförlustskydd</span><span class="sxs-lookup"><span data-stu-id="b5ee9-149">Office 365 Data Loss Prevention</span></span>|    ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)|![Ingår i Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="b5ee9-152">Azure Information Protection plan 1, BitLocker verkställande</span><span class="sxs-lookup"><span data-stu-id="b5ee9-152">Azure Information Protection Plan 1, BitLocker enforcement</span></span>|![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="b5ee9-154">Azure Information Protection plan 1, känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="b5ee9-154">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="b5ee9-156">**Klientåtkomstlicens (CAL-rättigheter)**</span><span class="sxs-lookup"><span data-stu-id="b5ee9-156">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="b5ee9-157">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="b5ee9-157">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Ingår i Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="b5ee9-159"><sup>1</sup> Microsoft 365 Business Premium-versionen av Office-apparna omfattar inte volymaktivering via grupprinciper, app telemetri, uppdateringskontroller, kalkylbladsjämförelse och inquire samt Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-159"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="b5ee9-160">Migrering</span><span class="sxs-lookup"><span data-stu-id="b5ee9-160">Migration</span></span>

<span data-ttu-id="b5ee9-161">Anvisningar om hur du migrerar [din prenumeration finns i](../commerce/subscriptions/change-plans-manually.md) Ändra abonnemang manuellt om du bara vill flytta några få Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-161">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="b5ee9-162">Du kan också [uppgradera alla automatiskt](../commerce/subscriptions/upgrade-to-different-plan.md), eller samarbeta med en partner för att flytta din E3-prenumeration och dina licenser till en Microsoft 365 Business Premium prenumeration.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-162">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="b5ee9-163">I följande avsnitt beskrivs de ändringar du behöver göra, om det finns några, och vad du kan göra efter migreringen.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-163">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="b5ee9-164">Office 365 Konfiguration och data för E3-prenumeration</span><span class="sxs-lookup"><span data-stu-id="b5ee9-164">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="b5ee9-165">Du behöver inte göra några ändringar i din nuvarande prenumeration eller dina data innan du migrerar, vilket omfattar:</span><span class="sxs-lookup"><span data-stu-id="b5ee9-165">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="b5ee9-166">Prenumerationskonfiguration, till exempel DNS-poster och domännamn.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-166">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="b5ee9-167">Användar- och gruppkonton och autentiseringsinställningar, till exempel principer för multifaktorautentisering eller villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-167">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="b5ee9-168">Produktivitetstjänstkonfigurationer och deras data, till exempel Teams, Exchange Online postlådor, SharePoint Online-webbplatser, OneDrive för företag-mappar och OneNote-anteckningsböcker.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-168">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="b5ee9-169">Office skalas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-169">Office applications will scale automatically.</span></span> <span data-ttu-id="b5ee9-170">Office 365 modern licensiering kommer att kontrollera användarens licenstilldelning var 72:e timme och konverterar Office-program till den version som överensstämmer med användarprenumerationen.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-170">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="b5ee9-171">Windows 10</span><span class="sxs-lookup"><span data-stu-id="b5ee9-171">Windows 10</span></span>

<span data-ttu-id="b5ee9-172">Om din Windows inte redan är på Windows Pro,uppgradera dem till [Creators Update Windows Pro dem.](upgrade-to-windows-pro-creators-update.md)</span><span class="sxs-lookup"><span data-stu-id="b5ee9-172">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="b5ee9-173">Konfigurera principer för att skydda användares enheter och filer</span><span class="sxs-lookup"><span data-stu-id="b5ee9-173">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="b5ee9-174">Om du inställningar Office 365 MDM-principer och -enheter visas  de enheterna på sidan Enheter Microsoft 365 administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-174">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="b5ee9-175">Alla principer som du har angett visas i listan med klassiska principer i [Intune-portalen.](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)</span><span class="sxs-lookup"><span data-stu-id="b5ee9-175">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="b5ee9-176">När du har tilldelat licenser Microsoft 365 Business Premium kan du börja skydda användarnas enheter och filer.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-176">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="b5ee9-177">Om du har uppgraderat alla i organisationen till Microsoft 365 Business Premium visas installationsguiden på startsidan och du kan följa Konfigurera [Microsoft 365 Business Premium](set-up.md) i installationsguiden för att skydda filer och mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-177">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="b5ee9-178">Du kan också utföra de här stegen på sidan Enheter:</span><span class="sxs-lookup"><span data-stu-id="b5ee9-178">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="b5ee9-179">I det vänstra navigeringsfältet i administrationscentret går du till **Principer för** \> **enheter.**</span><span class="sxs-lookup"><span data-stu-id="b5ee9-179">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>

2. <span data-ttu-id="b5ee9-180">På sidan **Enhetsprinciper** väljer du Lägg **till**.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-180">On the **Device policies** page, choose **Add**.</span></span>

3. <span data-ttu-id="b5ee9-181">I fönstret **Lägg till** princip ger du principen ett namn och väljer sedan **en principtyp** i listrutan.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-181">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span>

     <span data-ttu-id="b5ee9-182">Du kan konfigurera programprinciper för att skydda filer på Android och iPhone-enheter, samt Windows 10, och du kan konfigurera principer för enhetskonfiguration för företagsägda Windows 10 enheter.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-182">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="b5ee9-183">Se följande länkar för mer information:</span><span class="sxs-lookup"><span data-stu-id="b5ee9-183">See the following links for details:</span></span>

  - [<span data-ttu-id="b5ee9-184">Ange inställningar för appskydd för Android- eller iOS-enheter</span><span class="sxs-lookup"><span data-stu-id="b5ee9-184">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)

  - [<span data-ttu-id="b5ee9-185">Ange programskyddsinställningar för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="b5ee9-185">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)

  - [<span data-ttu-id="b5ee9-186">Ange inställningar för enhetsskydd för Windows 10-datorer</span><span class="sxs-lookup"><span data-stu-id="b5ee9-186">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="b5ee9-187">När du har angett principer kan du och dina anställda konfigurera enheter:</span><span class="sxs-lookup"><span data-stu-id="b5ee9-187">Once you set up policies, you and your employees can set up devices:</span></span>

  - <span data-ttu-id="b5ee9-188">Se [Konfigurera Windows enheter för Microsoft 365 Business Premium för](set-up-windows-devices.md) anvisningar för Windows enheter.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-188">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 

  - <span data-ttu-id="b5ee9-189">Se [Konfigurera mobila enheter för Microsoft 365 Business Premium för anvisningar](set-up-mobile-devices.md) för Android-telefoner och iPhone.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-189">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="b5ee9-190">Postlådans storlek</span><span class="sxs-lookup"><span data-stu-id="b5ee9-190">Mailbox Size</span></span>

<span data-ttu-id="b5ee9-191">Microsoft 365 Business Premium har en lagringsgräns på 50 GB eftersom den använder Exchange Online abonnemang 1.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-191">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="b5ee9-192">När du migrerar till Microsoft 365 Business Premium rekommenderar vi att du tilldelar användaren ett Exchange Online abonnemang 2 och tar bort Exchange Online abonnemang 1 eftersom det inte är möjligt att tilldela båda.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-192">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>

### <a name="threat-protection"></a><span data-ttu-id="b5ee9-193">Skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="b5ee9-193">Threat protection</span></span>

<span data-ttu-id="b5ee9-194">När du har migrerat till Microsoft 365 Business Premium har du Defender för Office 365.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-194">After migrating to Microsoft 365 Business Premium, you have Defender for Office 365.</span></span> <span data-ttu-id="b5ee9-195">Se [Microsoft Defender för Office 365](../security/office-365-security/defender-for-office-365.md) en översikt.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-195">See [Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for an overview.</span></span> <span data-ttu-id="b5ee9-196">Konfigurera genom att gå till [Konfigurera Valv,](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)konfigurera [Valv](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)och konfigurera Skydd mot nätfiske [i Defender för Office 365.](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)</span><span class="sxs-lookup"><span data-stu-id="b5ee9-196">To set up, see [set up Safe Links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up Safe Attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up Anti-phishing in Defender for Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="b5ee9-197">Känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="b5ee9-197">Sensitivity labels</span></span>

<span data-ttu-id="b5ee9-198">Om du vill börja använda känslighetsetiketter kan [du gå till Översikt över känslighetsetiketter](../compliance/sensitivity-labels.md) och skapa och hantera [känslighetsetiketter](../business-video/create-sensitivity-labels.md) video.</span><span class="sxs-lookup"><span data-stu-id="b5ee9-198">To start using sensitivity labels, see [Overview of sensitivity labels](../compliance/sensitivity-labels.md) and [create and manage sensitivity labels](../business-video/create-sensitivity-labels.md) video.</span></span>

## <a name="related-content"></a><span data-ttu-id="b5ee9-199">Relaterat innehåll</span><span class="sxs-lookup"><span data-stu-id="b5ee9-199">Related content</span></span>

<span data-ttu-id="b5ee9-200">[Ändra abonnemang manuellt](../commerce/subscriptions/change-plans-manually.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="b5ee9-200">[Change plans manually](../commerce/subscriptions/change-plans-manually.md) (article)</span></span>\
<span data-ttu-id="b5ee9-201">[Uppgradera Windows enheter till Windows 10 Pro](upgrade-to-windows-pro-creators-update.md) (video)</span><span class="sxs-lookup"><span data-stu-id="b5ee9-201">[Upgrade Windows devices to Windows 10 Pro](upgrade-to-windows-pro-creators-update.md) (video)</span></span>\
<span data-ttu-id="b5ee9-202">[Ange programskyddsinställningar för Android- eller iOS-enheter](app-protection-settings-for-android-and-ios.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="b5ee9-202">[Set app protection settings for Android or iOS devices](app-protection-settings-for-android-and-ios.md) (article)</span></span>\
<span data-ttu-id="b5ee9-203">[Ange eller redigera programskyddsinställningar för Windows 10](protection-settings-for-windows-10-devices.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="b5ee9-203">[Set or edit application protection settings for Windows 10 devices](protection-settings-for-windows-10-devices.md) (article)</span></span>\
<span data-ttu-id="b5ee9-204">[]</span><span class="sxs-lookup"><span data-stu-id="b5ee9-204">[]</span></span>

