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
description: Lär dig hur du flyttar ditt företag till Microsoft 365 Business Premium från Office 365 E3.
ms.openlocfilehash: f3f3894a2a5cb69f9f91825d89db4f4b857fac5c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295299"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a><span data-ttu-id="bc0fd-103">Migrera från Office 365 E3 till Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="bc0fd-103">Migrating from Office 365 E3 to Microsoft 365 Business Premium</span></span> 

<span data-ttu-id="bc0fd-104">Microsoft 365 Business Premium innehåller allt du behöver för ditt småföretag och kombinerar de bästa molnbaserade Cloud-baserade produktivitets appar med enkel enhets hantering och säkerhet.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-104">Microsoft 365 Business Premium has everything you need for your small business, combining the best-in-class cloud-based productivity apps with simple device management and security.</span></span> <span data-ttu-id="bc0fd-105">Om du för närvarande har ett Office 365 E3-abonnemang men inte har fler än 300 anställda bör du överväga att byta till Microsoft 365 Business Premium för ytterligare säkerhetsfunktioner.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-105">If you currently have an Office 365 E3 subscription, but don't have more than 300 employees, consider switching to Microsoft 365 Business Premium for added security features.</span></span>

<span data-ttu-id="bc0fd-106">Det är enkelt: först kan du byta licenser och alla dina data och din användar information i ditt nuvarande abonnemang underhålls.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-106">Migrating is easy: First you switch licenses and all your data and user information in your current subscription is maintained.</span></span> <span data-ttu-id="bc0fd-107">Efter migreringen måste du konfigurera funktionerna som läggs till i Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-107">After the migration, you'll need to set up the features that are added in Microsoft 365 Business Premium.</span></span>

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a><span data-ttu-id="bc0fd-108">Skillnader mellan Office 365 E3 och Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="bc0fd-108">Differences between Office 365 E3 and Microsoft 365 Business Premium</span></span>

<span data-ttu-id="bc0fd-109">I den här tabellen visas skillnaderna mellan Microsoft 365 Business Premium och Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-109">This table shows the differences between Microsoft 365 Business Premium and Office 365 E3.</span></span>

| <span data-ttu-id="bc0fd-110">Funktion</span><span class="sxs-lookup"><span data-stu-id="bc0fd-110">Feature</span></span>    | <span data-ttu-id="bc0fd-111">Stöd i Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="bc0fd-111">Support in Microsoft 365 Business Premium</span></span>    | <span data-ttu-id="bc0fd-112">Stöd i Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="bc0fd-112">Support in Office 365 E3</span></span> | 
|:-------|:-----|:-----|
| <span data-ttu-id="bc0fd-113">**Lokalt**</span><span class="sxs-lookup"><span data-stu-id="bc0fd-113">**On-premises**</span></span>        | | | 
| <span data-ttu-id="bc0fd-114">Office-program<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="bc0fd-114">Office apps<sup>1</sup></span></span>    | <span data-ttu-id="bc0fd-115">Microsoft 365-applikationer för affärsverksamhet</span><span class="sxs-lookup"><span data-stu-id="bc0fd-115">Microsoft 365 Apps for business</span></span>    | <span data-ttu-id="bc0fd-116"> Microsoft 365 Apps för företag</span><span class="sxs-lookup"><span data-stu-id="bc0fd-116">Microsoft 365 Apps for enterprise</span></span> | 
| <span data-ttu-id="bc0fd-117">**Cloud Productivity-appar**</span><span class="sxs-lookup"><span data-stu-id="bc0fd-117">**Cloud productivity apps**</span></span>        | | | 
| <span data-ttu-id="bc0fd-118">Exchange Online och Outlook</span><span class="sxs-lookup"><span data-stu-id="bc0fd-118">Exchange Online and Outlook</span></span>    | <span data-ttu-id="bc0fd-119">50 GB lagrings gräns per post låda och obegränsad Exchange Online-arkivering</span><span class="sxs-lookup"><span data-stu-id="bc0fd-119">50 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span>    | <span data-ttu-id="bc0fd-120">100 GB lagrings gräns per post låda och obegränsad Exchange Online-arkivering</span><span class="sxs-lookup"><span data-stu-id="bc0fd-120">100 GB storage limit per mailbox and unlimited Exchange Online Archiving</span></span> | 
| <span data-ttu-id="bc0fd-121">Teams</span><span class="sxs-lookup"><span data-stu-id="bc0fd-121">Teams</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="bc0fd-124">OneDrive för företag</span><span class="sxs-lookup"><span data-stu-id="bc0fd-124">OneDrive for Business</span></span>    | <span data-ttu-id="bc0fd-125">1 TB lagrings gräns per användare</span><span class="sxs-lookup"><span data-stu-id="bc0fd-125">1 TB storage limit per user</span></span>    | <span data-ttu-id="bc0fd-126">Oinskränk</span><span class="sxs-lookup"><span data-stu-id="bc0fd-126">Unlimited</span></span> | 
| <span data-ttu-id="bc0fd-127">Yammer, SharePoint Online, Planner, Stream</span><span class="sxs-lookup"><span data-stu-id="bc0fd-127">Yammer, SharePoint Online, Planner, Stream</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="bc0fd-130">StaffHub</span><span class="sxs-lookup"><span data-stu-id="bc0fd-130">StaffHub</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png) | 
| <span data-ttu-id="bc0fd-133">Kund ansvarig för Outlook, MileIQ</span><span class="sxs-lookup"><span data-stu-id="bc0fd-133">Outlook Customer Manager, MileIQ</span></span>    | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | | 
| <span data-ttu-id="bc0fd-135">**Skydd för hotet**</span><span class="sxs-lookup"><span data-stu-id="bc0fd-135">**Threat Protection**</span></span>        | | | 
| <span data-ttu-id="bc0fd-136">Office 365 Avancerat skydd (ATP) abonnemang 1</span><span class="sxs-lookup"><span data-stu-id="bc0fd-136">Office 365 Advanced Threat Protection (ATP) Plan 1</span></span> | ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | <span data-ttu-id="bc0fd-138">Ingår inte, men kan läggas till på</span><span class="sxs-lookup"><span data-stu-id="bc0fd-138">Not included, but can be added on</span></span> | 
| <span data-ttu-id="bc0fd-139">**Identitets hantering**</span><span class="sxs-lookup"><span data-stu-id="bc0fd-139">**Identity management**</span></span>        | | | 
| <span data-ttu-id="bc0fd-140">Self-Service lösen ords återställning för Hybrid Azure Active Directory-konton (Azure AD), Azure Multi-factority (MFA), villkorsstyrd åtkomst, tillbakaskrivning för lösen ord för lokala identiteter</span><span class="sxs-lookup"><span data-stu-id="bc0fd-140">Self-service password reset for hybrid Azure Active Directory (Azure AD) accounts, Azure multi-factor authentication (MFA), Conditional Access, password writeback for on-premises identities</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    |  | 
| <span data-ttu-id="bc0fd-142">**Hantera enheter och appar**</span><span class="sxs-lookup"><span data-stu-id="bc0fd-142">**Device and app management**</span></span>        | | |
| <span data-ttu-id="bc0fd-143">Microsoft Intune, Windows autopilot</span><span class="sxs-lookup"><span data-stu-id="bc0fd-143">Microsoft Intune, Windows AutoPilot</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    |  |
| <span data-ttu-id="bc0fd-145">Aktivering av delad dator</span><span class="sxs-lookup"><span data-stu-id="bc0fd-145">Shared computer activation</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    | ![Ingår i Office 365 E3](../media/check-mark.png)| 
| <span data-ttu-id="bc0fd-148">Uppgraderings rättigheter till Windows 10 Pro från Win 7/8.1 Pro-licenser</span><span class="sxs-lookup"><span data-stu-id="bc0fd-148">Upgrade rights to Windows 10 Pro from Win 7/8.1 Pro licenses</span></span>|     ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)    || 
| <span data-ttu-id="bc0fd-150">**Informationsskydd**</span><span class="sxs-lookup"><span data-stu-id="bc0fd-150">**Information protection**</span></span>        | | |
|<span data-ttu-id="bc0fd-151">Office 365 skydd mot data förlust</span><span class="sxs-lookup"><span data-stu-id="bc0fd-151">Office 365 Data Loss Prevention</span></span>|    ![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)|![Ingår i Office 365 E3](../media/check-mark.png)|
|<span data-ttu-id="bc0fd-154">Azure information Protection Plan 1, tvingande för BitLocker</span><span class="sxs-lookup"><span data-stu-id="bc0fd-154">Azure Information Protection Plan 1, Bitlocker enforcement</span></span>|![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="bc0fd-156">Azure information Protection Plan 1, känslighets etiketter</span><span class="sxs-lookup"><span data-stu-id="bc0fd-156">Azure Information Protection Plan 1, Sensitivity labels</span></span>|![Ingår i Microsoft 365 Business Premium](../media/check-mark.png)||
|<span data-ttu-id="bc0fd-158">**Klient åtkomst licens (CAL-rättigheter)**</span><span class="sxs-lookup"><span data-stu-id="bc0fd-158">**Client Access License (CAL rights)**</span></span>|||
|<span data-ttu-id="bc0fd-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span><span class="sxs-lookup"><span data-stu-id="bc0fd-159">Enterprise CAL Suite (Exchange, SharePoint, Skype)</span></span>||![Ingår i Office 365 E3](../media/check-mark.png)|

<span data-ttu-id="bc0fd-161"><sup>1</sup> Microsoft 365 Business Premium-versionen av Office-programmen inkluderar inte volym aktivering via grup princip, app-telemetri, uppdaterings kontroller, kalkyl blads jämförelse och-frågor eller Business Intelligence.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-161"><sup>1</sup> The Microsoft 365 Business Premium version of the Office apps doesn't include volume activation through Group Policy, app telemetry, update controls, spreadsheet compare and inquire, or business Intelligence.</span></span>

## <a name="migration"></a><span data-ttu-id="bc0fd-162">Migrering</span><span class="sxs-lookup"><span data-stu-id="bc0fd-162">Migration</span></span>

<span data-ttu-id="bc0fd-163">Om du vill migrera prenumerationen kan du läsa [ändra abonnemang manuellt](../commerce/subscriptions/change-plans-manually.md) för anvisningar om du vill flytta några personer till Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-163">To migrate your subscription, see [Change plans manually](../commerce/subscriptions/change-plans-manually.md) for instructions if you want to move just a few people to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="bc0fd-164">Du kan också [Uppgradera alla automatiskt](../commerce/subscriptions/upgrade-to-different-plan.md)eller arbeta med en partner för att flytta ditt E3-abonnemang och-licenser till en Microsoft 365 Business Premium-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-164">You can also [upgrade everyone automatically](../commerce/subscriptions/upgrade-to-different-plan.md), or work with a partner to move your E3 subscription and licenses to a Microsoft 365 Business Premium subscription.</span></span>
<span data-ttu-id="bc0fd-165">I följande avsnitt beskrivs de ändringar du behöver göra, om så är fallet och vad du kan göra efter migreringen.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-165">The following sections describe the changes you need to make, if any, and what you can do after the migration.</span></span>

### <a name="office-365-e3-subscription-configuration-and-data"></a><span data-ttu-id="bc0fd-166">Office 365 E3 prenumerations konfiguration och data</span><span class="sxs-lookup"><span data-stu-id="bc0fd-166">Office 365 E3 subscription configuration and data</span></span>
<span data-ttu-id="bc0fd-167">Du behöver inte göra några ändringar i ditt nuvarande abonnemang eller data före migreringen, vilket inkluderar:</span><span class="sxs-lookup"><span data-stu-id="bc0fd-167">You don't need to do any changes to your current subscription or data before migrating, which includes:</span></span>

- <span data-ttu-id="bc0fd-168">Prenumerations konfiguration, till exempel DNS-poster och domän namn.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-168">Subscription configuration, such as DNS records and domain names.</span></span>
- <span data-ttu-id="bc0fd-169">Inställningar för användare och grupper, till exempel multifaktorautentisering eller villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-169">User and group accounts and authentication settings, such as multi factor authentication or conditional access policies.</span></span>
- <span data-ttu-id="bc0fd-170">Produktivitets tjänst konfiguration och deras data, till exempel team, Exchange Online-postlådor, SharePoint Online-webbplatser, OneDrive för företag-mappar och OneNote-anteckningsböcker.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-170">Productivity service configurations and their data, such as Teams, Exchange Online mailboxes, SharePoint Online sites, OneDrive for Business folders, and OneNote notebooks.</span></span>
- <span data-ttu-id="bc0fd-171">Office-programmen skalas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-171">Office applications will scale automatically.</span></span> <span data-ttu-id="bc0fd-172">Office 365 moderna licenser kontrollerar användarens licens tilldelning varje 72 timmar och konverterar Office-program till den version som matchar användar abonnemanget.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-172">Office 365 modern licensing will check the user’s license assignment every 72 hours and will convert Office applications to the version that matches the user subscription.</span></span>

### <a name="windows-10"></a><span data-ttu-id="bc0fd-173">Windows 10</span><span class="sxs-lookup"><span data-stu-id="bc0fd-173">Windows 10</span></span>

<span data-ttu-id="bc0fd-174">Om Windows inte redan är aktiverat i Windows Pro Creator kan [du uppgradera dem till Windows Pro Creator Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="bc0fd-174">If your Windows aren't already on Windows Pro Creator update, [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

### <a name="set-up-policies-to-protect-user-devices-and-files"></a><span data-ttu-id="bc0fd-175">Konfigurera principer för att skydda användar enheter och filer</span><span class="sxs-lookup"><span data-stu-id="bc0fd-175">Set up policies to protect user devices and files</span></span>

> [!NOTE]
> <span data-ttu-id="bc0fd-176">Om du konfigurerar principer och enheter för Office 365 MDM visas dessa enheter på sidan **enheter** i administrations centret för Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-176">If you set up Office 365 MDM policies and devices, those devices will be listed on the **Devices** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="bc0fd-177">Alla principer du konfigurerar visas i listan över klassiska principer i [Intune-portalen](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span><span class="sxs-lookup"><span data-stu-id="bc0fd-177">Any policies you set up will show up in the list of classic policies in the [Intune portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).</span></span>

<span data-ttu-id="bc0fd-178">När du har tilldelat licenser till Microsoft 365 Business Premium kan du börja skydda användarnas enheter och filer.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-178">After you have assigned licenses to Microsoft 365 Business Premium, you can start protecting the users' devices and files.</span></span>

<span data-ttu-id="bc0fd-179">Om du har uppgraderat alla i organisationen till Microsoft 365 Business Premium ser du installations guiden på Start sidan och kan [365](set-up.md) följa anvisningarna för att skydda filer och mobila enheter.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-179">If you upgraded everyone in your organization to Microsoft 365 Business Premium, you'll see the setup wizard on the Home page, and can follow the [Set up Microsoft 365 Business Premium in the setup wizard](set-up.md) steps to protect files and mobile devices.</span></span>

<span data-ttu-id="bc0fd-180">Du kan också slutföra dessa steg på sidan enheter:</span><span class="sxs-lookup"><span data-stu-id="bc0fd-180">You can also complete these steps on the Devices page:</span></span>
  
1. <span data-ttu-id="bc0fd-181">Gå till **enhets** principer i administrations centret i det vänstra navigerings fältet \> **Policies**.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-181">In the admin center, in the left nav, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="bc0fd-182">På sidan **enhets principer** väljer du **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-182">On the **Device policies** page, choose **Add**.</span></span>
    
3. <span data-ttu-id="bc0fd-183">Ge principen ett namn i rutan **Lägg till princip** och välj sedan en **princip typ** i list rutan.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-183">In the **Add policy** pane give the policy a name, and then choose a **Policy type** from the drop-down.</span></span> 
    
     <span data-ttu-id="bc0fd-184">Du kan ställa in program principer för att skydda filer på Android-och iPhone-enheter samt i Windows 10, och du kan konfigurera enhets konfigurations principer för företagsspecifika Windows 10-enheter.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-184">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="bc0fd-185">Se följande länkar för information:</span><span class="sxs-lookup"><span data-stu-id="bc0fd-185">See the following links for details:</span></span>
    
  - [<span data-ttu-id="bc0fd-186">Ange inställningar för appskydd för Android- eller iOS-enheter</span><span class="sxs-lookup"><span data-stu-id="bc0fd-186">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="bc0fd-187">Ange programskyddsinställningar för Windows 10-enheter</span><span class="sxs-lookup"><span data-stu-id="bc0fd-187">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="bc0fd-188">Ange inställningar för enhets skydd för Windows 10-datorer</span><span class="sxs-lookup"><span data-stu-id="bc0fd-188">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
  
4. <span data-ttu-id="bc0fd-189">När du har konfigurerat en policy kan du och dina anställda konfigurera enheter:</span><span class="sxs-lookup"><span data-stu-id="bc0fd-189">Once you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="bc0fd-190">Se [Konfigurera Windows-enheter för Microsoft 365 Business Premium-användare](set-up-windows-devices.md) för instruktioner för Windows-enheter.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-190">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="bc0fd-191">Se [Konfigurera mobila enheter för Microsoft 365 Business Premium-användare](set-up-mobile-devices.md) för att få anvisningar för Android-telefoner och iPhone.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-191">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
  
### <a name="mailbox-size"></a><span data-ttu-id="bc0fd-192">Post lådans storlek</span><span class="sxs-lookup"><span data-stu-id="bc0fd-192">Mailbox Size</span></span>

<span data-ttu-id="bc0fd-193">Microsoft 365 Business Premium har en lagrings gräns på 50 GB eftersom den använder Exchange Online plan 1.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-193">Microsoft 365 Business Premium has a 50 GB storage limit as it uses Exchange Online Plan 1.</span></span> <span data-ttu-id="bc0fd-194">När du migrerar till Microsoft 365 Business Premium är det lämpligt att tilldela en Exchange Online-plan 2 och ta bort Exchange Online-abonnemanget 1 om någon av dina användare har fler än 50 GB lagrings utrymme.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-194">While migrating to Microsoft 365 Business Premium, if any of your users exceed 50 GB of mailbox storage, it is recommended that you assign this user an Exchange Online Plan 2 and remove the Exchange Online Plan 1 as it's not feasible to assign both.</span></span>


### <a name="threat-protection"></a><span data-ttu-id="bc0fd-195">Skydd mot hot</span><span class="sxs-lookup"><span data-stu-id="bc0fd-195">Threat protection</span></span>

<span data-ttu-id="bc0fd-196">När du har migrerat till Microsoft 365 Business Premium har du Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-196">After migrating to Microsoft 365 Business Premium, you have Office 365 ATP.</span></span> <span data-ttu-id="bc0fd-197">Se [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) för en översikt.</span><span class="sxs-lookup"><span data-stu-id="bc0fd-197">See [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) for an overview.</span></span> <span data-ttu-id="bc0fd-198">Om du vill konfigurera läser du [Konfigurera säkra säkerhets](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)meddelanden för ATP, [Konfigurera säkerhet för säkert säkerhets](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)läge för ATP och [Konfigurera anti-nätfiske](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span><span class="sxs-lookup"><span data-stu-id="bc0fd-198">To set up, see [set up ATP safe links](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa), [set up ATP safe attachments](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5), and [set up ATP anti-phishing](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c).</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="bc0fd-199">Känslighetsetiketter</span><span class="sxs-lookup"><span data-stu-id="bc0fd-199">Sensitivity labels</span></span>

<span data-ttu-id="bc0fd-200">Om du vill börja använda känslighets etiketter kan du läsa [Översikt över känslighets etiketter](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) och [skapa och hantera känslighets etiketter](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) .</span><span class="sxs-lookup"><span data-stu-id="bc0fd-200">To start using sensitivity labels, see [Overview of sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) and [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>
