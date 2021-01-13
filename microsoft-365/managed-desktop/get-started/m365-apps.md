---
title: Microsoft 365 Apps för företag
description: Distribuera Microsoft 365-appar, hur de uppdateras och hur inställningar hanteras
keywords: ändrings historik
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 98995084fb7de9ecb434b70b5d38793a20675f19
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840355"
---
# <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="71a53-104"> Microsoft 365 Apps för företag</span><span class="sxs-lookup"><span data-stu-id="71a53-104">Microsoft 365 Apps for enterprise</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="71a53-105">Inledande distribution</span><span class="sxs-lookup"><span data-stu-id="71a53-105">Initial deployment</span></span>

<span data-ttu-id="71a53-106">Microsoft Managed Desktop garanterar att Microsoft 365-programmen för Enterprise (64-bitars) installeras som en del av bilden på alla [program enheter](../service-description/device-list.md).</span><span class="sxs-lookup"><span data-stu-id="71a53-106">Microsoft Managed Desktop ensures that Microsoft 365 Apps for enterprise (64-bit) are installed as a part of the image on all [program devices](../service-description/device-list.md).</span></span> <span data-ttu-id="71a53-107">Alla följande program bör finnas med på enheten när den levereras:</span><span class="sxs-lookup"><span data-stu-id="71a53-107">All of the following applications should be present on the device when it's delivered:</span></span>

- <span data-ttu-id="71a53-108">Word</span><span class="sxs-lookup"><span data-stu-id="71a53-108">Word</span></span>
- <span data-ttu-id="71a53-109">Excel</span><span class="sxs-lookup"><span data-stu-id="71a53-109">Excel</span></span>
- <span data-ttu-id="71a53-110">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="71a53-110">PowerPoint</span></span>
- <span data-ttu-id="71a53-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="71a53-111">Outlook</span></span>
- <span data-ttu-id="71a53-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="71a53-112">Publisher</span></span>
- <span data-ttu-id="71a53-113">Åtkomst</span><span class="sxs-lookup"><span data-stu-id="71a53-113">Access</span></span>
- <span data-ttu-id="71a53-114">Skype för företag</span><span class="sxs-lookup"><span data-stu-id="71a53-114">Skype for Business</span></span>
- <span data-ttu-id="71a53-115">OneNote</span><span class="sxs-lookup"><span data-stu-id="71a53-115">OneNote</span></span>

<span data-ttu-id="71a53-116">Den här metoden minimerar nätverks påverkan och säkerställer att användarna kan vara produktiva när de tar emot sina enheter.</span><span class="sxs-lookup"><span data-stu-id="71a53-116">This approach minimizes network impact and ensures that users can be productive as soon as they receive their device.</span></span> <span data-ttu-id="71a53-117">Vi distribuerar sedan fler principer till hanterade enheter för att konfigurera programmen för användning.</span><span class="sxs-lookup"><span data-stu-id="71a53-117">We then deploy more policies to managed devices to set up the applications for use.</span></span>

> [!NOTE]
> <span data-ttu-id="71a53-118">Microsoft Teams distribueras separat från Microsoft 365-appar för företag och ingår inte i bas bilden.</span><span class="sxs-lookup"><span data-stu-id="71a53-118">Microsoft Teams is deployed separately from Microsoft 365 Apps for enterprise and is not included in the base image.</span></span> 

### <a name="available-deployment-to-users"></a><span data-ttu-id="71a53-119">Tillgänglig distribution för användare</span><span class="sxs-lookup"><span data-stu-id="71a53-119">Available deployment to users</span></span>

<span data-ttu-id="71a53-120">Om en användare inte har Microsoft 365-appar på sin enhet av någon anledning kan du använda ett paket för att återställa enheten till förväntat tillstånd.</span><span class="sxs-lookup"><span data-stu-id="71a53-120">If a user does not have Microsoft 365 Apps on their device for any reason, you can use a package to return the device to its expected state.</span></span> <span data-ttu-id="71a53-121">Lägga till användaren i den **moderna arbets platsen – Office-Office365_Install-** gruppen och programmen blir tillgängliga för dem i företags portalen.</span><span class="sxs-lookup"><span data-stu-id="71a53-121">Add the user to the **Modern Workplace-Office-Office365_Install** group and the apps will become available to them in the Company Portal.</span></span>

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a><span data-ttu-id="71a53-122">Microsoft 365-appar för Enterprise (32-bitar)</span><span class="sxs-lookup"><span data-stu-id="71a53-122">Microsoft 365 Apps for enterprise (32-bit)</span></span>

<span data-ttu-id="71a53-123">Microsoft Managed Desktop stöder inte distribution av 32-bitars versionen av M365-appar för företag.</span><span class="sxs-lookup"><span data-stu-id="71a53-123">Microsoft Managed Desktop doesn't support the deployment of the 32-bit version of M365 Apps for enterprise.</span></span>

## <a name="updates-to-microsoft-365-apps"></a><span data-ttu-id="71a53-124">Uppdateringar av Microsoft 365-appar</span><span class="sxs-lookup"><span data-stu-id="71a53-124">Updates to Microsoft 365 Apps</span></span>

<span data-ttu-id="71a53-125">Microsoft 365-apparna är inställda på att uppdatera [månadens Enterprise-kanal](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span><span class="sxs-lookup"><span data-stu-id="71a53-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span></span> <span data-ttu-id="71a53-126">I den här övningen får användarna nya Office-funktioner varje månad, men de får bara en uppdatering per månad på ett förutsägbart sätt.</span><span class="sxs-lookup"><span data-stu-id="71a53-126">This practice provides your users with new Office features each month, but they'll receive just one update per month on a predictable release schedule.</span></span> <span data-ttu-id="71a53-127">Uppdateringar publiceras den andra tisdagen i månaden; dessa uppdateringar kan omfatta uppdateringar av funktioner, säkerhet och kvalitet.</span><span class="sxs-lookup"><span data-stu-id="71a53-127">Updates are released on the second Tuesday of the month; these updates can include feature, security, and quality updates.</span></span> <span data-ttu-id="71a53-128">Dessa uppdateringar sker automatiskt och hämtas direkt från Office CDN för den specifika kanalen.</span><span class="sxs-lookup"><span data-stu-id="71a53-128">These updates occur automatically and are pulled directly from the Office CDN for that specific channel.</span></span>

<span data-ttu-id="71a53-129">Microsoft Managed Desktop-förskjutningar för att identifiera eventuella problem i miljön.</span><span class="sxs-lookup"><span data-stu-id="71a53-129">Microsoft Managed Desktop staggers each release to identify any potential issues in your environment.</span></span> <span data-ttu-id="71a53-130">Vi slutförde lanseringen av de 28 dagarna efter utgivningen från Microsoft 365 program produkt gruppen.</span><span class="sxs-lookup"><span data-stu-id="71a53-130">We complete the rollout 28 days after the release from the Microsoft 365 App product group.</span></span> <span data-ttu-id="71a53-131">Microsoft-hanterade Skriv bords scheman uppdaterar utgåvor till olika grupper för att tillåta tid för validering och testning:</span><span class="sxs-lookup"><span data-stu-id="71a53-131">Microsoft Managed Desktop schedules update releases to different groups to allow time for validation and testing as follows:</span></span> 

- <span data-ttu-id="71a53-132">Test: noll dagar</span><span class="sxs-lookup"><span data-stu-id="71a53-132">Test: zero days</span></span>
- <span data-ttu-id="71a53-133">Först: noll dagar</span><span class="sxs-lookup"><span data-stu-id="71a53-133">First: zero days</span></span>
- <span data-ttu-id="71a53-134">Snabbt: 7 dagar</span><span class="sxs-lookup"><span data-stu-id="71a53-134">Fast: 7 days</span></span>
- <span data-ttu-id="71a53-135">Brett: 21 dagar</span><span class="sxs-lookup"><span data-stu-id="71a53-135">Broad: 21 days</span></span>

<span data-ttu-id="71a53-136">Microsoft Managed Desktop set en [tids gräns](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) på sju dagar för enheter.</span><span class="sxs-lookup"><span data-stu-id="71a53-136">Microsoft Managed Desktop sets a seven-day [update deadline](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for devices.</span></span> <span data-ttu-id="71a53-137">När uppdateringen är tillgänglig måste den installeras inom sju dagar.</span><span class="sxs-lookup"><span data-stu-id="71a53-137">Once the update is available, it must be installed within seven days.</span></span> <span data-ttu-id="71a53-138">Användare [meddelas](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) om att uppdateringar krävs på flera platser: programmet, i system fältet 12 timmar före deadline och får en 15-minuters varning före tids gränsen.</span><span class="sxs-lookup"><span data-stu-id="71a53-138">Users are [notified](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) that updates are required in several locations: the application, in the system tray 12 hours prior to the deadline, and they receive a 15-minute warning prior to the deadline.</span></span> <span data-ttu-id="71a53-139">Alla Microsoft 365-appar måste vara stängda för att uppdateringen ska slutföras.</span><span class="sxs-lookup"><span data-stu-id="71a53-139">All Microsoft 365 Apps must be closed for the update to complete.</span></span>

### <a name="pausing-or-rolling-back-an-update"></a><span data-ttu-id="71a53-140">Pausa eller återställa en uppdatering</span><span class="sxs-lookup"><span data-stu-id="71a53-140">Pausing or rolling back an update</span></span>

<span data-ttu-id="71a53-141">Om du behöver pausa eller återställa Microsoft 365-programmet av någon anledning kan du arkivera en [support förfrågan för administratörer](../working-with-managed-desktop/admin-support.md) via Microsofts hanterade Skriv bords Portal.</span><span class="sxs-lookup"><span data-stu-id="71a53-141">If you need to pause or roll back Microsoft 365 App update for any reason, file an [admin support request](../working-with-managed-desktop/admin-support.md) through the Microsoft Managed Desktop portal.</span></span>

<span data-ttu-id="71a53-142">Under en version övervakar Microsoft Managed Desktop dator fel frekvenserna för alla Microsoft 365-appar.</span><span class="sxs-lookup"><span data-stu-id="71a53-142">During a release, Microsoft Managed Desktop monitors the error rates of all Microsoft 365 Apps.</span></span> <span data-ttu-id="71a53-143">Om vi antecknar en betydande bild av kvaliteten mellan den nya versionen och dess föregångare, kan vi kontakta dig via administrations portalen för Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="71a53-143">If we note a significant difference in quality between the new release and its predecessor, we might contact you through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="71a53-144">Beroende på allvarlighets graden frågar vi dig om du vill pausa versionen eller informera dig om att vi har åtgärdat ett problem.</span><span class="sxs-lookup"><span data-stu-id="71a53-144">Depending on the severity, we will either ask if you want to pause the release or inform you that we have taken action to mitigate an issue.</span></span> 

### <a name="delivery-optimization"></a><span data-ttu-id="71a53-145">Leverans optimering</span><span class="sxs-lookup"><span data-stu-id="71a53-145">Delivery optimization</span></span>

<span data-ttu-id="71a53-146">Leverans optimering är en peer-to-peer-postdistributionsgrupp som är tillgänglig i Windows 10.</span><span class="sxs-lookup"><span data-stu-id="71a53-146">Delivery Optimization is a peer-to-peer distribution technology available in Windows 10.</span></span> <span data-ttu-id="71a53-147">Det gör att enheter kan dela innehåll, till exempel uppdateringar, som enheterna har laddat ner från Microsoft via Internet.</span><span class="sxs-lookup"><span data-stu-id="71a53-147">It allows devices to share content, such as updates, that the devices have downloaded from Microsoft over the internet.</span></span> <span data-ttu-id="71a53-148">Genom att använda den kan minska nätverks bandbredden eftersom en enhet kan få delar av uppdateringen från en annan enhet i det lokala nätverket i stället för att behöva ladda ner uppdateringen helt från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71a53-148">Using it can help reduce network bandwidth because a device can get portions of the update from another device on its local network instead of having to download the update completely from Microsoft.</span></span>

<span data-ttu-id="71a53-149">[Leverans optimering](https://docs.microsoft.com/deployoffice/delivery-optimization) är aktive rad som standard på enheter med utbildnings utgåvor för Windows 10 Enterprise eller Windows 10.</span><span class="sxs-lookup"><span data-stu-id="71a53-149">[Delivery Optimization](https://docs.microsoft.com/deployoffice/delivery-optimization) is enabled by default on devices running the Windows 10 Enterprise or Windows 10 Education editions.</span></span> 

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="71a53-150">Inställningar som hanteras av Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="71a53-150">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="71a53-151">Microsoft hanterar vissa inställningar som en del av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="71a53-151">Microsoft manages some settings as a part of the service.</span></span> <span data-ttu-id="71a53-152">Microsoft Managed Desktop hanterar inte en Office Security-original plan, men du kan ställa in ett själv genom att följa anvisningarna i avsnittet [inställningar som hanteras](#settings-you-manage) .</span><span class="sxs-lookup"><span data-stu-id="71a53-152">Microsoft Managed Desktop doesn't manage an Office Security baseline but you can set one yourself by following the guidance in the [Settings you manage](#settings-you-manage) section.</span></span>

### <a name="update-settings"></a><span data-ttu-id="71a53-153">Uppdaterings inställningar</span><span class="sxs-lookup"><span data-stu-id="71a53-153">Update settings</span></span>

<span data-ttu-id="71a53-154">Microsoft Managed Desktop behåller alla [uppdaterings inställningar](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) för hanterade enheter och du bör ändra de här inställningarna.</span><span class="sxs-lookup"><span data-stu-id="71a53-154">Microsoft Managed Desktop maintains all [update settings](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for managed devices and you should modify these settings.</span></span>

### <a name="set-updates-to-occur-automatically"></a><span data-ttu-id="71a53-155">Ange att uppdateringar ska ske automatiskt</span><span class="sxs-lookup"><span data-stu-id="71a53-155">Set updates to occur automatically</span></span>

<span data-ttu-id="71a53-156">**Standardvärde**: aktive rad</span><span class="sxs-lookup"><span data-stu-id="71a53-156">**Default value**: Enabled</span></span>

<span data-ttu-id="71a53-157">Den här principen är konfigurerad för att säkerställa att alla Office-enheter kan hållas uppdaterade från molnet.</span><span class="sxs-lookup"><span data-stu-id="71a53-157">This policy is configured in order to ensure that all Office devices can be kept up to date from the cloud.</span></span> 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a><span data-ttu-id="71a53-158">Ange en tids gräns när uppdateringar måste tillämpas</span><span class="sxs-lookup"><span data-stu-id="71a53-158">Set a deadline when updates have to be applied</span></span>

<span data-ttu-id="71a53-159">**Standardvärde**: 7 dagar</span><span class="sxs-lookup"><span data-stu-id="71a53-159">**Default value**: 7 days</span></span>

<span data-ttu-id="71a53-160">**UpdateDeadline** policy används för att konfigurera Grace-perioden som användare har innan en uppdatering genomdrivs på enheten.</span><span class="sxs-lookup"><span data-stu-id="71a53-160">The **UpdateDeadline** policy is used to configure the grace period which users have before an update is enforced on the device.</span></span> <span data-ttu-id="71a53-161">Denna tids gräns princip utlöser också [meddelanden](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) till användaren för att informera dem om de ändringar som krävs på deras enheter.</span><span class="sxs-lookup"><span data-stu-id="71a53-161">This deadline policy also triggers [notifications](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) to the user to inform them of the changes required on their device.</span></span>  

### <a name="defer-updates-on-a-device-for-a-period"></a><span data-ttu-id="71a53-162">Skjuta upp uppdateringar för en enhet för en period</span><span class="sxs-lookup"><span data-stu-id="71a53-162">Defer updates on a device for a period</span></span>

<span data-ttu-id="71a53-163">Den här principen konfigureras olika för varje enhets grupp för uppdaterings hantering och krävs för Microsoft Managed Desktop för att uppfylla sina uppdaterings mål:</span><span class="sxs-lookup"><span data-stu-id="71a53-163">This policy is configured differently for each update management device group and is required for Microsoft Managed Desktop to meet its update targets:</span></span>  

- <span data-ttu-id="71a53-164">Test: noll dagar</span><span class="sxs-lookup"><span data-stu-id="71a53-164">Test: zero days</span></span>
- <span data-ttu-id="71a53-165">Först: noll dagar</span><span class="sxs-lookup"><span data-stu-id="71a53-165">First: zero days</span></span>
- <span data-ttu-id="71a53-166">Snabb sju dagar</span><span class="sxs-lookup"><span data-stu-id="71a53-166">Fast 7 days</span></span>
- <span data-ttu-id="71a53-167">Brett: 21 dagar</span><span class="sxs-lookup"><span data-stu-id="71a53-167">Broad: 21 days</span></span>

### <a name="update-notifications-settings"></a><span data-ttu-id="71a53-168">Uppdatera aviserings inställningar</span><span class="sxs-lookup"><span data-stu-id="71a53-168">Update notifications settings</span></span>

<span data-ttu-id="71a53-169">**Standardvärde**: falskt</span><span class="sxs-lookup"><span data-stu-id="71a53-169">**Default value**: False</span></span>

<span data-ttu-id="71a53-170">Inställningen "Dölj uppdaterings aviseringar" är inställd på **false** på Microsoft Managed Station ära enheter för att tillhandahålla den bästa uppdateringen för användare genom att [meddela](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) dem när uppdateringar behövs.</span><span class="sxs-lookup"><span data-stu-id="71a53-170">The "hide update notifications" setting is set to **False** on Microsoft Managed Desktop devices to provide the best update experience for users by [notifying](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) them when updates are required.</span></span>

### <a name="specify-a-location-to-look-for-updates"></a><span data-ttu-id="71a53-171">Ange en plats att söka efter uppdateringar för</span><span class="sxs-lookup"><span data-stu-id="71a53-171">Specify a location to look for updates</span></span>

<span data-ttu-id="71a53-172">**Standardvärde**: månatlig företags kanal</span><span class="sxs-lookup"><span data-stu-id="71a53-172">**Default value**: Monthly Enterprise Channel</span></span>

<span data-ttu-id="71a53-173">En kombination av **UpdatePath** -och **UpdateChannel** -principer används för att uppnå uppdaterings schema.</span><span class="sxs-lookup"><span data-stu-id="71a53-173">A combination of the **UpdatePath** and **UpdateChannel** policies is used as needed to achieve the update schedule.</span></span> <span data-ttu-id="71a53-174">Dessa principer är inställda på att säkerställa att alla Office-enheter tar emot uppdateringar direkt från CDN för den månads Visa företags kanalen.</span><span class="sxs-lookup"><span data-stu-id="71a53-174">These policies are set to ensure that all Office devices receive updates directly from the CDN for the Monthly Enterprise Channel.</span></span>

### <a name="specify-the-target-version-of-microsoft-365-apps"></a><span data-ttu-id="71a53-175">Ange mål versionen av Microsoft 365-appar</span><span class="sxs-lookup"><span data-stu-id="71a53-175">Specify the Target Version of Microsoft 365 Apps</span></span>

<span data-ttu-id="71a53-176">Mål versions principen används ibland av Microsoft Managed Desktop för att återställa eller fästa en viss version av Office.</span><span class="sxs-lookup"><span data-stu-id="71a53-176">The Target Version policy is sometimes used by Microsoft Managed Desktop in order to roll back or pin a specific version of Office.</span></span> 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a><span data-ttu-id="71a53-177">Dölj alternativet för att aktivera eller inaktivera automatiska uppdateringar av Office</span><span class="sxs-lookup"><span data-stu-id="71a53-177">Hide the option to enable or disable Office automatic updates</span></span>

<span data-ttu-id="71a53-178">**Standardvärde**: aktive rad</span><span class="sxs-lookup"><span data-stu-id="71a53-178">**Default value**: Enabled</span></span>

<span data-ttu-id="71a53-179">Den här inställningen krävs för Microsoft Managed Desktop för att uppfylla sina uppdaterings mål för Microsoft 365-program.</span><span class="sxs-lookup"><span data-stu-id="71a53-179">This setting is required for Microsoft Managed Desktop to meet its update targets for Microsoft 365 Applications.</span></span> 

### <a name="first-run-settings"></a><span data-ttu-id="71a53-180">Inställningar för första körningen</span><span class="sxs-lookup"><span data-stu-id="71a53-180">First run settings</span></span> 

<span data-ttu-id="71a53-181">Det finns flera inställningar som påverkar beteendet för första gången Office körs.</span><span class="sxs-lookup"><span data-stu-id="71a53-181">There are several settings that affect the behavior the first time Office is run.</span></span>

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a><span data-ttu-id="71a53-182">Godkänn licens villkoren åt slutanvändaren</span><span class="sxs-lookup"><span data-stu-id="71a53-182">Accept the license terms on behalf of the end user</span></span>

<span data-ttu-id="71a53-183">**Standardvärde**: inaktiverat</span><span class="sxs-lookup"><span data-stu-id="71a53-183">**Default value**: Disabled</span></span>

<span data-ttu-id="71a53-184">Första gången en användare öppnar en Microsoft 365-App uppmanas de att acceptera licens villkoren.</span><span class="sxs-lookup"><span data-stu-id="71a53-184">The first time a user opens a Microsoft 365 App, they are prompted to accept the license terms.</span></span> <span data-ttu-id="71a53-185">Om du vill acceptera licens villkoren åt användarna kan du spara en tjänstbegäran med Microsoft Managed Desktop-teamet och ange att inställningen ska aktive ras.</span><span class="sxs-lookup"><span data-stu-id="71a53-185">If you want to accept the license terms on behalf of your users, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

### <a name="suppress-outlook-mobile-check-box"></a><span data-ttu-id="71a53-186">Kryss rutan Inaktivera Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="71a53-186">Suppress Outlook mobile check box</span></span>

<span data-ttu-id="71a53-187">**Standardvärde**: inaktiverat</span><span class="sxs-lookup"><span data-stu-id="71a53-187">**Default value**: Disabled</span></span>

<span data-ttu-id="71a53-188">Första gången en användare öppnar Outlook uppmanas de att installera Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="71a53-188">The first time a user opens Outlook they are prompted to install Outlook Mobile.</span></span> <span data-ttu-id="71a53-189">Om du inte vill att användarna ska kunna se den här kryss rutan kan du spara en tjänstbegäran med Microsoft Managed Desktop-teamet och ange att den här inställningen ska vara aktive rad för dina enheter.</span><span class="sxs-lookup"><span data-stu-id="71a53-189">If you don’t want your users to see that check box, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled for your devices.</span></span> 

## <a name="other-settings"></a><span data-ttu-id="71a53-190">Andra inställningar</span><span class="sxs-lookup"><span data-stu-id="71a53-190">Other settings</span></span>

<span data-ttu-id="71a53-191">Det finns andra Microsoft 365-inställningar som Microsoft Managed Desktop kan konfigurera åt dig.</span><span class="sxs-lookup"><span data-stu-id="71a53-191">There are other Microsoft 365 App settings which Microsoft Managed Desktop can optionally configure on your behalf.</span></span> 

### <a name="disable-personal-onedrive"></a><span data-ttu-id="71a53-192">Inaktivera personligt OneDrive</span><span class="sxs-lookup"><span data-stu-id="71a53-192">Disable Personal OneDrive</span></span>

<span data-ttu-id="71a53-193">**Standardvärde**: inaktiverat</span><span class="sxs-lookup"><span data-stu-id="71a53-193">**Default value**: Disabled</span></span>

<span data-ttu-id="71a53-194">Vissa organisationer är bekymrade över användare som har till gång till både företags-och privata filer på sina enheter.</span><span class="sxs-lookup"><span data-stu-id="71a53-194">Some organizations are concerned about users having access to both corporate and personal files on their devices.</span></span> <span data-ttu-id="71a53-195">Du kan spara en tjänstbegäran med Microsoft Managed Desktop-gruppanvändare där den här inställningen aktive ras.</span><span class="sxs-lookup"><span data-stu-id="71a53-195">You can file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

## <a name="settings-you-manage"></a><span data-ttu-id="71a53-196">Inställningar som du hanterar</span><span class="sxs-lookup"><span data-stu-id="71a53-196">Settings you manage</span></span>

<span data-ttu-id="71a53-197">Det finns många andra principer som Microsoft Managed Desktop ännu inte har angett som en del av vår tjänst.</span><span class="sxs-lookup"><span data-stu-id="71a53-197">There are many other policies which Microsoft Managed Desktop does not yet set as a part of our service.</span></span> <span data-ttu-id="71a53-198">Dessa principer kan konfigureras med hjälp av Microsoft Intune som använder princip tjänsten för [Office-moln](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) .</span><span class="sxs-lookup"><span data-stu-id="71a53-198">You can configure these policies by using Microsoft Intune, which uses the [Office Cloud Policy](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service.</span></span> <span data-ttu-id="71a53-199">Gör så här för att ange dessa principer:</span><span class="sxs-lookup"><span data-stu-id="71a53-199">To set these policies, follow these steps:</span></span>

1.  <span data-ttu-id="71a53-200">Logga in i administrations centret för Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="71a53-200">Sign in to the Microsoft Endpoint Manager admin center.</span></span>
2.  <span data-ttu-id="71a53-201">Välj **program > principer för Office-program > Skapa**</span><span class="sxs-lookup"><span data-stu-id="71a53-201">Select **Apps > Policies for Office apps > Create**</span></span>
3.  <span data-ttu-id="71a53-202">Gör följande på sidan **Skapa princip** konfiguration:</span><span class="sxs-lookup"><span data-stu-id="71a53-202">On the **Create policy** configuration page, do the following:</span></span>
    - <span data-ttu-id="71a53-203">Ange ett namn.</span><span class="sxs-lookup"><span data-stu-id="71a53-203">Enter a name.</span></span>
    - <span data-ttu-id="71a53-204">Ange en beskrivning (valfritt).</span><span class="sxs-lookup"><span data-stu-id="71a53-204">Provide a description (optional).</span></span>
    - <span data-ttu-id="71a53-205">I **uppgifter** väljer du om den här policyn gäller för alla användare av Microsoft 365-appar för företag, eller bara för användare som anonymt får åtkomst till dokument med Office för webben.</span><span class="sxs-lookup"><span data-stu-id="71a53-205">In **assignments**, choose whether this policy applies to all users of Microsoft 365 Apps for enterprise, or just to users who anonymously access documents using Office for the web.</span></span>
    - <span data-ttu-id="71a53-206">Välj den AAD-baserade säkerhets grupp som är tilldelad till princip konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="71a53-206">Select the AAD-based security group that is assigned to the policy configuration.</span></span> <span data-ttu-id="71a53-207">Varje princip konfiguration kan bara tilldelas en grupp, och varje grupp kan bara tilldelas en princip konfiguration.</span><span class="sxs-lookup"><span data-stu-id="71a53-207">Each policy configuration can only be assigned to one group, and each group can only be assigned one policy configuration.</span></span>
    - <span data-ttu-id="71a53-208">Konfigurera princip inställningarna så att de tas med i princip konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="71a53-208">Configure the policy settings to be included in the policy configuration.</span></span> <span data-ttu-id="71a53-209">Du kan söka i princip inställnings namnet för att hitta den princip inställning som du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="71a53-209">You can search on the policy setting name to find the policy setting that you want to configure.</span></span> <span data-ttu-id="71a53-210">Du kan också filtrera efter programmet, på om principen är en rekommenderad säkerhets bas linje och om policyn har kon figurer ATS.</span><span class="sxs-lookup"><span data-stu-id="71a53-210">You can also filter on the application, on whether the policy is a recommended security baseline, and on whether the policy has been configured.</span></span> <span data-ttu-id="71a53-211">I kolumnen Platform visas om policyn används för Microsoft 365-appar för Enterprise för Windows-enheter, Office för webben eller alla.</span><span class="sxs-lookup"><span data-stu-id="71a53-211">The platform column indicates whether the policy is applied to Microsoft 365 Apps for enterprise for Windows devices, Office for the web, or all.</span></span>
4.  <span data-ttu-id="71a53-212">När du har gjort dina val väljer du **skapa**.</span><span class="sxs-lookup"><span data-stu-id="71a53-212">After you have made your selections, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="71a53-213">Konfigurations principer för Office stöder endast användarspecifik distribution</span><span class="sxs-lookup"><span data-stu-id="71a53-213">Office Configuration Policies only support user-based deployment</span></span>
