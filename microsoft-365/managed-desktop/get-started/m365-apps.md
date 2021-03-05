---
title: Microsoft 365 Apps för företag
description: Distribuera Microsoft 365-program, hur de uppdateras och hur inställningar hanteras
keywords: ändringshistorik
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 26e62d6e59f1f90e35d9e18e6eed917a66876645
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453927"
---
# <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="f6cda-104"> Microsoft 365 Apps för företag</span><span class="sxs-lookup"><span data-stu-id="f6cda-104">Microsoft 365 Apps for enterprise</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="f6cda-105">Första distributionen</span><span class="sxs-lookup"><span data-stu-id="f6cda-105">Initial deployment</span></span>

<span data-ttu-id="f6cda-106">Microsoft Hanterat skrivbord ser till att Microsoft 365-appar för företag (64-bitars) installeras som en del av bilden på alla [programenheter.](../service-description/device-list.md)</span><span class="sxs-lookup"><span data-stu-id="f6cda-106">Microsoft Managed Desktop ensures that Microsoft 365 Apps for enterprise (64-bit) are installed as a part of the image on all [program devices](../service-description/device-list.md).</span></span> <span data-ttu-id="f6cda-107">Följande program bör finnas på enheten när den levereras:</span><span class="sxs-lookup"><span data-stu-id="f6cda-107">All of the following applications should be present on the device when it's delivered:</span></span>

- <span data-ttu-id="f6cda-108">Word</span><span class="sxs-lookup"><span data-stu-id="f6cda-108">Word</span></span>
- <span data-ttu-id="f6cda-109">Excel</span><span class="sxs-lookup"><span data-stu-id="f6cda-109">Excel</span></span>
- <span data-ttu-id="f6cda-110">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f6cda-110">PowerPoint</span></span>
- <span data-ttu-id="f6cda-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="f6cda-111">Outlook</span></span>
- <span data-ttu-id="f6cda-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="f6cda-112">Publisher</span></span>
- <span data-ttu-id="f6cda-113">Åtkomst</span><span class="sxs-lookup"><span data-stu-id="f6cda-113">Access</span></span>
- <span data-ttu-id="f6cda-114">Skype för företag</span><span class="sxs-lookup"><span data-stu-id="f6cda-114">Skype for Business</span></span>
- <span data-ttu-id="f6cda-115">OneNote</span><span class="sxs-lookup"><span data-stu-id="f6cda-115">OneNote</span></span>

<span data-ttu-id="f6cda-116">Den här metoden minimerar nätverks påverkan och ser till att användarna kan vara produktiva så snart de får sin enhet.</span><span class="sxs-lookup"><span data-stu-id="f6cda-116">This approach minimizes network impact and ensures that users can be productive as soon as they receive their device.</span></span> <span data-ttu-id="f6cda-117">Sedan distribuerar vi fler principer till hanterade enheter för att konfigurera programmen för användning.</span><span class="sxs-lookup"><span data-stu-id="f6cda-117">We then deploy more policies to managed devices to set up the applications for use.</span></span>

> [!NOTE]
> <span data-ttu-id="f6cda-118">Microsoft Teams distribueras separat från Microsoft 365-appar för företag och ingår inte i basbilden.</span><span class="sxs-lookup"><span data-stu-id="f6cda-118">Microsoft Teams is deployed separately from Microsoft 365 Apps for enterprise and is not included in the base image.</span></span> 

### <a name="available-deployment-to-users"></a><span data-ttu-id="f6cda-119">Tillgänglig distribution för användare</span><span class="sxs-lookup"><span data-stu-id="f6cda-119">Available deployment to users</span></span>

<span data-ttu-id="f6cda-120">Om en användare av någon anledning inte har Microsoft 365-appar på sin enhet kan du använda ett paket för att returnera enheten till det förväntade läget.</span><span class="sxs-lookup"><span data-stu-id="f6cda-120">If a user does not have Microsoft 365 Apps on their device for any reason, you can use a package to return the device to its expected state.</span></span> <span data-ttu-id="f6cda-121">Lägg till användaren i **gruppen Modern workplace-Office-Office365_Install** så blir apparna tillgängliga för dem i företagsportalen.</span><span class="sxs-lookup"><span data-stu-id="f6cda-121">Add the user to the **Modern Workplace-Office-Office365_Install** group and the apps will become available to them in the Company Portal.</span></span>

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a><span data-ttu-id="f6cda-122">Microsoft 365-appar för företag (32-bitar)</span><span class="sxs-lookup"><span data-stu-id="f6cda-122">Microsoft 365 Apps for enterprise (32-bit)</span></span>

<span data-ttu-id="f6cda-123">Microsoft Hanterat skrivbord stöder inte distribution av 32-bitarsversionen av M365-program för företag.</span><span class="sxs-lookup"><span data-stu-id="f6cda-123">Microsoft Managed Desktop doesn't support the deployment of the 32-bit version of M365 Apps for enterprise.</span></span>

## <a name="updates-to-microsoft-365-apps"></a><span data-ttu-id="f6cda-124">Uppdateringar av Microsoft 365-appar</span><span class="sxs-lookup"><span data-stu-id="f6cda-124">Updates to Microsoft 365 Apps</span></span>

<span data-ttu-id="f6cda-125">Microsoft 365-appar är inställda på att uppdateras i [månatlig företagskanal.](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)</span><span class="sxs-lookup"><span data-stu-id="f6cda-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span></span> <span data-ttu-id="f6cda-126">Den här övningen ger användarna nya Office-funktioner varje månad, men de får bara en uppdatering per månad med ett förutsägbart versionsschema.</span><span class="sxs-lookup"><span data-stu-id="f6cda-126">This practice provides your users with new Office features each month, but they'll receive just one update per month on a predictable release schedule.</span></span> <span data-ttu-id="f6cda-127">Uppdateringar släpps den andra tisdagen i månaden. Dessa uppdateringar kan innehålla funktions-, säkerhets- och kvalitetsuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="f6cda-127">Updates are released on the second Tuesday of the month; these updates can include feature, security, and quality updates.</span></span> <span data-ttu-id="f6cda-128">De här uppdateringarna görs automatiskt och hämtas direkt från Office CDN för den specifika kanalen.</span><span class="sxs-lookup"><span data-stu-id="f6cda-128">These updates occur automatically and are pulled directly from the Office CDN for that specific channel.</span></span>

<span data-ttu-id="f6cda-129">Microsoft Hanterade skrivbord förser varje version med att identifiera potentiella problem i din miljö.</span><span class="sxs-lookup"><span data-stu-id="f6cda-129">Microsoft Managed Desktop staggers each release to identify any potential issues in your environment.</span></span> <span data-ttu-id="f6cda-130">Vi har slutfört lanseringen 28 dagar efter lanseringen från Microsoft 365 App-produktgruppen.</span><span class="sxs-lookup"><span data-stu-id="f6cda-130">We complete the rollout 28 days after the release from the Microsoft 365 App product group.</span></span> <span data-ttu-id="f6cda-131">Microsoft Hanterad dator schemalägger uppdateringsutgåvan till olika grupper för att ge tid för validering och testning enligt följande:</span><span class="sxs-lookup"><span data-stu-id="f6cda-131">Microsoft Managed Desktop schedules update releases to different groups to allow time for validation and testing as follows:</span></span> 

- <span data-ttu-id="f6cda-132">Test: noll dagar</span><span class="sxs-lookup"><span data-stu-id="f6cda-132">Test: zero days</span></span>
- <span data-ttu-id="f6cda-133">Första: noll dagar</span><span class="sxs-lookup"><span data-stu-id="f6cda-133">First: zero days</span></span>
- <span data-ttu-id="f6cda-134">Snabbt: 3 dagar</span><span class="sxs-lookup"><span data-stu-id="f6cda-134">Fast: 3 days</span></span>
- <span data-ttu-id="f6cda-135">Bred: 7 dagar</span><span class="sxs-lookup"><span data-stu-id="f6cda-135">Broad: 7 days</span></span>

<span data-ttu-id="f6cda-136">Microsoft Hanterat skrivbord anger en tidsgräns på sju dagar [för](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) uppdateringar för enheter.</span><span class="sxs-lookup"><span data-stu-id="f6cda-136">Microsoft Managed Desktop sets a seven-day [update deadline](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for devices.</span></span> <span data-ttu-id="f6cda-137">När uppdateringen är tillgänglig måste den installeras inom sju dagar.</span><span class="sxs-lookup"><span data-stu-id="f6cda-137">Once the update is available, it must be installed within seven days.</span></span> <span data-ttu-id="f6cda-138">Användarna [](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) meddelas om att uppdateringar krävs på flera olika platser: i systemfältet 12 timmar före tidsgränsen, och de får en 15-minutersvarning före tidsgränsen.</span><span class="sxs-lookup"><span data-stu-id="f6cda-138">Users are [notified](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) that updates are required in several locations: the application, in the system tray 12 hours prior to the deadline, and they receive a 15-minute warning prior to the deadline.</span></span> <span data-ttu-id="f6cda-139">Alla Microsoft 365-appar måste stängas för att uppdateringen ska kunna slutföras.</span><span class="sxs-lookup"><span data-stu-id="f6cda-139">All Microsoft 365 Apps must be closed for the update to complete.</span></span>

### <a name="pausing-or-rolling-back-an-update"></a><span data-ttu-id="f6cda-140">Pausa eller distribuera en uppdatering</span><span class="sxs-lookup"><span data-stu-id="f6cda-140">Pausing or rolling back an update</span></span>

<span data-ttu-id="f6cda-141">Om du av någon anledning behöver pausa eller återställa programuppdateringen för Microsoft 365 arkiverar du en [administratörssupportbegäran](../working-with-managed-desktop/admin-support.md) via Microsoft Managed Desktop-portalen.</span><span class="sxs-lookup"><span data-stu-id="f6cda-141">If you need to pause or roll back Microsoft 365 App update for any reason, file an [admin support request](../working-with-managed-desktop/admin-support.md) through the Microsoft Managed Desktop portal.</span></span>

<span data-ttu-id="f6cda-142">Under en version övervakar Microsoft Hanterat skrivbord felfrekvenserna för alla Microsoft 365-appar.</span><span class="sxs-lookup"><span data-stu-id="f6cda-142">During a release, Microsoft Managed Desktop monitors the error rates of all Microsoft 365 Apps.</span></span> <span data-ttu-id="f6cda-143">Om vi ser en betydande kvalitetsskillnad mellan den nya versionen och den föregående versionen kan vi kontakta dig via Microsofts administrationsportal för hanterade datorer.</span><span class="sxs-lookup"><span data-stu-id="f6cda-143">If we note a significant difference in quality between the new release and its predecessor, we might contact you through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="f6cda-144">Beroende på hur allvarligt det är frågar vi dig om du vill pausa utgivningen eller informera dig om att vi har vidtagit åtgärder för att minimera ett problem.</span><span class="sxs-lookup"><span data-stu-id="f6cda-144">Depending on the severity, we will either ask if you want to pause the release or inform you that we have taken action to mitigate an issue.</span></span> 

### <a name="delivery-optimization"></a><span data-ttu-id="f6cda-145">Leveransoptimering</span><span class="sxs-lookup"><span data-stu-id="f6cda-145">Delivery optimization</span></span>

<span data-ttu-id="f6cda-146">Leveransoptimering är en peer-to-peer-distributionsteknik som finns i Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f6cda-146">Delivery Optimization is a peer-to-peer distribution technology available in Windows 10.</span></span> <span data-ttu-id="f6cda-147">Det gör att enheter kan dela innehåll, till exempel uppdateringar, som enheterna har laddat ned från Microsoft via Internet.</span><span class="sxs-lookup"><span data-stu-id="f6cda-147">It allows devices to share content, such as updates, that the devices have downloaded from Microsoft over the internet.</span></span> <span data-ttu-id="f6cda-148">Användning av den kan minska nätverkets bandbredd eftersom en enhet kan hämta delar av uppdateringen från en annan enhet på dess lokala nätverk i stället för att behöva ladda ned uppdateringen helt från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f6cda-148">Using it can help reduce network bandwidth because a device can get portions of the update from another device on its local network instead of having to download the update completely from Microsoft.</span></span>

<span data-ttu-id="f6cda-149">[Leveransoptimering](https://docs.microsoft.com/deployoffice/delivery-optimization) aktiveras som standard på enheter som kör versionerna Windows 10 Enterprise eller Windows 10 Education.</span><span class="sxs-lookup"><span data-stu-id="f6cda-149">[Delivery Optimization](https://docs.microsoft.com/deployoffice/delivery-optimization) is enabled by default on devices running the Windows 10 Enterprise or Windows 10 Education editions.</span></span> 

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="f6cda-150">Inställningar som hanteras av Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="f6cda-150">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="f6cda-151">Microsoft hanterar vissa inställningar som en del av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f6cda-151">Microsoft manages some settings as a part of the service.</span></span> <span data-ttu-id="f6cda-152">Microsoft Hanterat skrivbord hanterar inte en baslinje för Office-säkerhet men du kan ange en själv genom att följa linjerna i [avsnittet Inställningar som du hanterar.](#settings-you-manage)</span><span class="sxs-lookup"><span data-stu-id="f6cda-152">Microsoft Managed Desktop doesn't manage an Office Security baseline but you can set one yourself by following the guidance in the [Settings you manage](#settings-you-manage) section.</span></span>

### <a name="update-settings"></a><span data-ttu-id="f6cda-153">Uppdatera inställningar</span><span class="sxs-lookup"><span data-stu-id="f6cda-153">Update settings</span></span>

<span data-ttu-id="f6cda-154">Microsoft Hanterat skrivbord har alla [uppdateringsinställningar](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) för hanterade enheter och du bör ändra de här inställningarna.</span><span class="sxs-lookup"><span data-stu-id="f6cda-154">Microsoft Managed Desktop maintains all [update settings](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for managed devices and you should modify these settings.</span></span>

### <a name="set-updates-to-occur-automatically"></a><span data-ttu-id="f6cda-155">Konfigurera uppdateringar så att de sker automatiskt</span><span class="sxs-lookup"><span data-stu-id="f6cda-155">Set updates to occur automatically</span></span>

<span data-ttu-id="f6cda-156">**Standardvärde:** Aktiverad</span><span class="sxs-lookup"><span data-stu-id="f6cda-156">**Default value**: Enabled</span></span>

<span data-ttu-id="f6cda-157">Den här principen har konfigurerats för att säkerställa att alla Office-enheter kan hållas uppdaterade från molnet.</span><span class="sxs-lookup"><span data-stu-id="f6cda-157">This policy is configured in order to ensure that all Office devices can be kept up to date from the cloud.</span></span> 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a><span data-ttu-id="f6cda-158">Ange en tidsgräns när uppdateringar ska tillämpas</span><span class="sxs-lookup"><span data-stu-id="f6cda-158">Set a deadline when updates have to be applied</span></span>

<span data-ttu-id="f6cda-159">**Standardvärde:** 7 dagar</span><span class="sxs-lookup"><span data-stu-id="f6cda-159">**Default value**: 7 days</span></span>

<span data-ttu-id="f6cda-160">Principen **UpdateDeadline** används för att konfigurera respitperioden som användarna har innan en uppdatering tillämpas på enheten.</span><span class="sxs-lookup"><span data-stu-id="f6cda-160">The **UpdateDeadline** policy is used to configure the grace period which users have before an update is enforced on the device.</span></span> <span data-ttu-id="f6cda-161">Den här tidsgränsprincipen [utlöser även aviseringar](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) till användaren om de ändringar som krävs på enheten.</span><span class="sxs-lookup"><span data-stu-id="f6cda-161">This deadline policy also triggers [notifications](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) to the user to inform them of the changes required on their device.</span></span>  

### <a name="defer-updates-on-a-device-for-a-period"></a><span data-ttu-id="f6cda-162">Skjuta upp uppdateringar på en enhet under en period</span><span class="sxs-lookup"><span data-stu-id="f6cda-162">Defer updates on a device for a period</span></span>

<span data-ttu-id="f6cda-163">Den här principen har konfigurerats på olika sätt för varje enhetsgrupp för uppdateringshantering och krävs för att Microsoft Managed Desktop ska uppfylla sina uppdateringsmål:</span><span class="sxs-lookup"><span data-stu-id="f6cda-163">This policy is configured differently for each update management device group and is required for Microsoft Managed Desktop to meet its update targets:</span></span>  

- <span data-ttu-id="f6cda-164">Test: noll dagar</span><span class="sxs-lookup"><span data-stu-id="f6cda-164">Test: zero days</span></span>
- <span data-ttu-id="f6cda-165">Första: noll dagar</span><span class="sxs-lookup"><span data-stu-id="f6cda-165">First: zero days</span></span>
- <span data-ttu-id="f6cda-166">Snabb 7 dagar</span><span class="sxs-lookup"><span data-stu-id="f6cda-166">Fast 7 days</span></span>
- <span data-ttu-id="f6cda-167">Bred: 21 dagar</span><span class="sxs-lookup"><span data-stu-id="f6cda-167">Broad: 21 days</span></span>

### <a name="update-notifications-settings"></a><span data-ttu-id="f6cda-168">Uppdatera meddelandeinställningar</span><span class="sxs-lookup"><span data-stu-id="f6cda-168">Update notifications settings</span></span>

<span data-ttu-id="f6cda-169">**Standardvärde:** Falskt</span><span class="sxs-lookup"><span data-stu-id="f6cda-169">**Default value**: False</span></span>

<span data-ttu-id="f6cda-170">Inställningen "Dölj uppdateringsmeddelanden" är inställd på **False** på Microsoft Managed Desktop-enheter för att ge bästa möjliga uppdateringsupplevelse för användare genom att meddela [dem](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) när uppdateringar krävs.</span><span class="sxs-lookup"><span data-stu-id="f6cda-170">The "hide update notifications" setting is set to **False** on Microsoft Managed Desktop devices to provide the best update experience for users by [notifying](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) them when updates are required.</span></span>

### <a name="specify-a-location-to-look-for-updates"></a><span data-ttu-id="f6cda-171">Ange en plats där du vill söka efter uppdateringar</span><span class="sxs-lookup"><span data-stu-id="f6cda-171">Specify a location to look for updates</span></span>

<span data-ttu-id="f6cda-172">**Standardvärde:** Månadskanal för företag</span><span class="sxs-lookup"><span data-stu-id="f6cda-172">**Default value**: Monthly Enterprise Channel</span></span>

<span data-ttu-id="f6cda-173">En kombination av **principerna UpdatePath** och **UpdateChannel** används vid behov för att uppnå uppdateringsschemat.</span><span class="sxs-lookup"><span data-stu-id="f6cda-173">A combination of the **UpdatePath** and **UpdateChannel** policies is used as needed to achieve the update schedule.</span></span> <span data-ttu-id="f6cda-174">De här principerna är inställda på att säkerställa att alla Office-enheter får uppdateringar direkt från CDN för månatlig företagskanal.</span><span class="sxs-lookup"><span data-stu-id="f6cda-174">These policies are set to ensure that all Office devices receive updates directly from the CDN for the Monthly Enterprise Channel.</span></span>

### <a name="specify-the-target-version-of-microsoft-365-apps"></a><span data-ttu-id="f6cda-175">Ange målversionen av Microsoft 365-appar</span><span class="sxs-lookup"><span data-stu-id="f6cda-175">Specify the Target Version of Microsoft 365 Apps</span></span>

<span data-ttu-id="f6cda-176">Principen för målversionen används ibland av Microsoft Managed Desktop för att återställa eller fästa en viss version av Office.</span><span class="sxs-lookup"><span data-stu-id="f6cda-176">The Target Version policy is sometimes used by Microsoft Managed Desktop in order to roll back or pin a specific version of Office.</span></span> 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a><span data-ttu-id="f6cda-177">Dölja alternativet för att aktivera eller inaktivera automatiska uppdateringar i Office</span><span class="sxs-lookup"><span data-stu-id="f6cda-177">Hide the option to enable or disable Office automatic updates</span></span>

<span data-ttu-id="f6cda-178">**Standardvärde:** Aktiverad</span><span class="sxs-lookup"><span data-stu-id="f6cda-178">**Default value**: Enabled</span></span>

<span data-ttu-id="f6cda-179">Den här inställningen krävs för att Microsoft Hanterat skrivbord ska uppfylla uppdateringsmålen för Microsoft 365-program.</span><span class="sxs-lookup"><span data-stu-id="f6cda-179">This setting is required for Microsoft Managed Desktop to meet its update targets for Microsoft 365 Applications.</span></span> 

### <a name="first-run-settings"></a><span data-ttu-id="f6cda-180">Inställningar för första körningen</span><span class="sxs-lookup"><span data-stu-id="f6cda-180">First run settings</span></span> 

<span data-ttu-id="f6cda-181">Det finns flera inställningar som påverkar beteendet första gången Office körs.</span><span class="sxs-lookup"><span data-stu-id="f6cda-181">There are several settings that affect the behavior the first time Office is run.</span></span>

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a><span data-ttu-id="f6cda-182">Godkänn licensvillkoren åt slutanvändaren</span><span class="sxs-lookup"><span data-stu-id="f6cda-182">Accept the license terms on behalf of the end user</span></span>

<span data-ttu-id="f6cda-183">**Standardvärde:** Inaktiverat</span><span class="sxs-lookup"><span data-stu-id="f6cda-183">**Default value**: Disabled</span></span>

<span data-ttu-id="f6cda-184">Första gången en användare öppnar en Microsoft 365-app uppmanas de att godkänna licensvillkoren.</span><span class="sxs-lookup"><span data-stu-id="f6cda-184">The first time a user opens a Microsoft 365 App, they are prompted to accept the license terms.</span></span> <span data-ttu-id="f6cda-185">Om du vill godkänna licensvillkoren åt dina användare arkiverar du en tjänstbegäran till Microsoft Managed Desktop Operations-teamet och ber om att den här inställningen aktiveras.</span><span class="sxs-lookup"><span data-stu-id="f6cda-185">If you want to accept the license terms on behalf of your users, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

### <a name="suppress-outlook-mobile-check-box"></a><span data-ttu-id="f6cda-186">Kryssrutan Ignorera Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="f6cda-186">Suppress Outlook mobile check box</span></span>

<span data-ttu-id="f6cda-187">**Standardvärde:** Inaktiverat</span><span class="sxs-lookup"><span data-stu-id="f6cda-187">**Default value**: Disabled</span></span>

<span data-ttu-id="f6cda-188">Första gången outlook öppnas uppmanas användaren att installera Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="f6cda-188">The first time a user opens Outlook they are prompted to install Outlook Mobile.</span></span> <span data-ttu-id="f6cda-189">Om du inte vill att användarna ska se den kryssrutan arkiverar du en tjänstbegäran till Microsoft Managed Desktop Operations-teamet och ber om att den här inställningen aktiveras för dina enheter.</span><span class="sxs-lookup"><span data-stu-id="f6cda-189">If you don’t want your users to see that check box, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled for your devices.</span></span> 

## <a name="other-settings"></a><span data-ttu-id="f6cda-190">Andra inställningar</span><span class="sxs-lookup"><span data-stu-id="f6cda-190">Other settings</span></span>

<span data-ttu-id="f6cda-191">Det finns andra Microsoft 365-appinställningar som Microsoft Hanterat skrivbord kan konfigurera åt dig.</span><span class="sxs-lookup"><span data-stu-id="f6cda-191">There are other Microsoft 365 App settings which Microsoft Managed Desktop can optionally configure on your behalf.</span></span> 

### <a name="disable-personal-onedrive"></a><span data-ttu-id="f6cda-192">Inaktivera personlig OneDrive</span><span class="sxs-lookup"><span data-stu-id="f6cda-192">Disable Personal OneDrive</span></span>

<span data-ttu-id="f6cda-193">**Standardvärde:** Inaktiverat</span><span class="sxs-lookup"><span data-stu-id="f6cda-193">**Default value**: Disabled</span></span>

<span data-ttu-id="f6cda-194">Vissa organisationer är oroliga för att användare ska ha åtkomst till både företagsfiler och personliga filer på sina enheter.</span><span class="sxs-lookup"><span data-stu-id="f6cda-194">Some organizations are concerned about users having access to both corporate and personal files on their devices.</span></span> <span data-ttu-id="f6cda-195">Du kan arkivera en tjänstbegäran med Microsoft Managed Desktop Operations-teamet och begära att den här inställningen aktiveras.</span><span class="sxs-lookup"><span data-stu-id="f6cda-195">You can file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

## <a name="settings-you-manage"></a><span data-ttu-id="f6cda-196">Inställningar som du hanterar</span><span class="sxs-lookup"><span data-stu-id="f6cda-196">Settings you manage</span></span>

<span data-ttu-id="f6cda-197">Det finns många andra principer som Microsoft Hanterade skrivbord ännu inte har angett som en del av vår tjänst.</span><span class="sxs-lookup"><span data-stu-id="f6cda-197">There are many other policies which Microsoft Managed Desktop does not yet set as a part of our service.</span></span> <span data-ttu-id="f6cda-198">Du kan konfigurera de här principerna med hjälp av Microsoft Intune, som använder [molnprinciptjänsten för Office.](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied)</span><span class="sxs-lookup"><span data-stu-id="f6cda-198">You can configure these policies by using Microsoft Intune, which uses the [Office Cloud Policy](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service.</span></span> <span data-ttu-id="f6cda-199">Följ de här stegen om du vill ange dessa principer:</span><span class="sxs-lookup"><span data-stu-id="f6cda-199">To set these policies, follow these steps:</span></span>

1.  <span data-ttu-id="f6cda-200">Logga in på administrationscentret för Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="f6cda-200">Sign in to the Microsoft Endpoint Manager admin center.</span></span>
2.  <span data-ttu-id="f6cda-201">Välj **program > principer för Office-program > Skapa**</span><span class="sxs-lookup"><span data-stu-id="f6cda-201">Select **Apps > Policies for Office apps > Create**</span></span>
3.  <span data-ttu-id="f6cda-202">Gör **följande på** konfigurationssidan Skapa princip:</span><span class="sxs-lookup"><span data-stu-id="f6cda-202">On the **Create policy** configuration page, do the following:</span></span>
    - <span data-ttu-id="f6cda-203">Ange ett namn.</span><span class="sxs-lookup"><span data-stu-id="f6cda-203">Enter a name.</span></span>
    - <span data-ttu-id="f6cda-204">Ange en beskrivning (valfritt).</span><span class="sxs-lookup"><span data-stu-id="f6cda-204">Provide a description (optional).</span></span>
    - <span data-ttu-id="f6cda-205">I **tilldelningar** väljer du om den här principen ska gälla för alla användare av Microsoft 365-program för företag eller bara för användare som har anonym åtkomst till dokument via Office för webben.</span><span class="sxs-lookup"><span data-stu-id="f6cda-205">In **assignments**, choose whether this policy applies to all users of Microsoft 365 Apps for enterprise, or just to users who anonymously access documents using Office for the web.</span></span>
    - <span data-ttu-id="f6cda-206">Markera den AAD-baserade säkerhetsgrupp som har tilldelats principkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="f6cda-206">Select the AAD-based security group that is assigned to the policy configuration.</span></span> <span data-ttu-id="f6cda-207">Varje principkonfiguration kan bara tilldelas en grupp och varje grupp kan bara tilldelas en principkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="f6cda-207">Each policy configuration can only be assigned to one group, and each group can only be assigned one policy configuration.</span></span>
    - <span data-ttu-id="f6cda-208">Konfigurera principinställningarna så att de inkluderas i principkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="f6cda-208">Configure the policy settings to be included in the policy configuration.</span></span> <span data-ttu-id="f6cda-209">Du kan söka på principinställningsnamnet för att hitta den principinställning som du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="f6cda-209">You can search on the policy setting name to find the policy setting that you want to configure.</span></span> <span data-ttu-id="f6cda-210">Du kan också filtrera på programmet, på om principen är en rekommenderad säkerhetsbaslinje och på om principen har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="f6cda-210">You can also filter on the application, on whether the policy is a recommended security baseline, and on whether the policy has been configured.</span></span> <span data-ttu-id="f6cda-211">I plattformskolumnen anges om principen tillämpas på Microsoft 365-appar för företag för Windows-enheter, Office för webben eller alla.</span><span class="sxs-lookup"><span data-stu-id="f6cda-211">The platform column indicates whether the policy is applied to Microsoft 365 Apps for enterprise for Windows devices, Office for the web, or all.</span></span>
4.  <span data-ttu-id="f6cda-212">När du har gjort dina val väljer du **Skapa.**</span><span class="sxs-lookup"><span data-stu-id="f6cda-212">After you have made your selections, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="f6cda-213">Konfigurationsprinciper för Office stöder endast användarbaserad distribution</span><span class="sxs-lookup"><span data-stu-id="f6cda-213">Office Configuration Policies only support user-based deployment</span></span>
