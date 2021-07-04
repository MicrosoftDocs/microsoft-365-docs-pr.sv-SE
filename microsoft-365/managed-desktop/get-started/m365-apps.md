---
title: Microsoft 365 Apps för företag
description: Hur du distribuerar Microsoft 365-applikationer, hur de uppdateras och hur inställningar hanteras
keywords: ändringshistorik
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 7b1178312178865face58748a37228f60643d5fc
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287981"
---
# <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="1680f-104"> Microsoft 365 Apps för företag</span><span class="sxs-lookup"><span data-stu-id="1680f-104">Microsoft 365 Apps for enterprise</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="1680f-105">Inledande distribution</span><span class="sxs-lookup"><span data-stu-id="1680f-105">Initial deployment</span></span>

<span data-ttu-id="1680f-106">Microsoft Hanterat skrivbord ser till Microsoft 365-appar för företag (64-bitar) är installerade som en del av bilden på alla [programenheter.](../service-description/device-list.md)</span><span class="sxs-lookup"><span data-stu-id="1680f-106">Microsoft Managed Desktop ensures that Microsoft 365 Apps for enterprise (64-bit) are installed as a part of the image on all [program devices](../service-description/device-list.md).</span></span> <span data-ttu-id="1680f-107">Alla följande program bör finnas på enheten när den levereras:</span><span class="sxs-lookup"><span data-stu-id="1680f-107">All of the following applications should be present on the device when it's delivered:</span></span>

- <span data-ttu-id="1680f-108">Word</span><span class="sxs-lookup"><span data-stu-id="1680f-108">Word</span></span>
- <span data-ttu-id="1680f-109">Excel</span><span class="sxs-lookup"><span data-stu-id="1680f-109">Excel</span></span>
- <span data-ttu-id="1680f-110">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="1680f-110">PowerPoint</span></span>
- <span data-ttu-id="1680f-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="1680f-111">Outlook</span></span>
- <span data-ttu-id="1680f-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="1680f-112">Publisher</span></span>
- <span data-ttu-id="1680f-113">Åtkomst</span><span class="sxs-lookup"><span data-stu-id="1680f-113">Access</span></span>
- <span data-ttu-id="1680f-114">Skype för företag</span><span class="sxs-lookup"><span data-stu-id="1680f-114">Skype for Business</span></span>
- <span data-ttu-id="1680f-115">OneNote</span><span class="sxs-lookup"><span data-stu-id="1680f-115">OneNote</span></span>

<span data-ttu-id="1680f-116">Den här metoden minimerar nätverkets påverkan och ser till att användarna kan vara produktiva så fort de får sin enhet.</span><span class="sxs-lookup"><span data-stu-id="1680f-116">This approach minimizes network impact and ensures that users can be productive as soon as they receive their device.</span></span> <span data-ttu-id="1680f-117">Sedan distribuerar vi fler principer till hanterade enheter för att konfigurera programmen för användning.</span><span class="sxs-lookup"><span data-stu-id="1680f-117">We then deploy more policies to managed devices to set up the applications for use.</span></span>

> [!NOTE]
> <span data-ttu-id="1680f-118">Microsoft Teams distribueras separat från Microsoft 365-appar för företag och tas inte med i basbilden.</span><span class="sxs-lookup"><span data-stu-id="1680f-118">Microsoft Teams is deployed separately from Microsoft 365 Apps for enterprise and is not included in the base image.</span></span> 

### <a name="available-deployment-to-users"></a><span data-ttu-id="1680f-119">Tillgänglig distribution för användare</span><span class="sxs-lookup"><span data-stu-id="1680f-119">Available deployment to users</span></span>

<span data-ttu-id="1680f-120">Om en användare av någon Microsoft 365-applikationer på sin enhet kan du använda ett paket för att returnera enheten till det förväntade läget.</span><span class="sxs-lookup"><span data-stu-id="1680f-120">If a user does not have Microsoft 365 Apps on their device for any reason, you can use a package to return the device to its expected state.</span></span> <span data-ttu-id="1680f-121">Lägg till användaren i **gruppen Office-Office365_Install** och apparna blir tillgängliga för dem i Företagsportal.</span><span class="sxs-lookup"><span data-stu-id="1680f-121">Add the user to the **Modern Workplace-Office-Office365_Install** group and the apps will become available to them in the Company Portal.</span></span>

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a><span data-ttu-id="1680f-122">Microsoft 365-appar för företag (32-bitars)</span><span class="sxs-lookup"><span data-stu-id="1680f-122">Microsoft 365 Apps for enterprise (32-bit)</span></span>

<span data-ttu-id="1680f-123">Microsoft Hanterat skrivbord stöder inte distributionen av 32-bitarsversionen av M365-program för företag.</span><span class="sxs-lookup"><span data-stu-id="1680f-123">Microsoft Managed Desktop doesn't support the deployment of the 32-bit version of M365 Apps for enterprise.</span></span>

## <a name="updates-to-microsoft-365-apps"></a><span data-ttu-id="1680f-124">Uppdateringar av Microsoft 365-applikationer</span><span class="sxs-lookup"><span data-stu-id="1680f-124">Updates to Microsoft 365 Apps</span></span>

<span data-ttu-id="1680f-125">Microsoft 365-applikationer är inställt på uppdatering i [Månatlig Enterprise-kanal.](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)</span><span class="sxs-lookup"><span data-stu-id="1680f-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span></span> <span data-ttu-id="1680f-126">Den här övningen ger användarna nya Office funktioner varje månad, men de får bara en uppdatering per månad på ett förutsägbart versionsschema.</span><span class="sxs-lookup"><span data-stu-id="1680f-126">This practice provides your users with new Office features each month, but they'll receive just one update per month on a predictable release schedule.</span></span> <span data-ttu-id="1680f-127">Uppdateringar släpps den andra tisdagen i månaden. dessa uppdateringar kan innehålla funktions-, säkerhets- och kvalitetsuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="1680f-127">Updates are released on the second Tuesday of the month; these updates can include feature, security, and quality updates.</span></span> <span data-ttu-id="1680f-128">Dessa uppdateringar görs automatiskt och hämtas direkt från Office CDN för den specifika kanalen.</span><span class="sxs-lookup"><span data-stu-id="1680f-128">These updates occur automatically and are pulled directly from the Office CDN for that specific channel.</span></span>

<span data-ttu-id="1680f-129">Microsoft Hanterat skrivbord för varje version så att du kan identifiera potentiella problem i din miljö.</span><span class="sxs-lookup"><span data-stu-id="1680f-129">Microsoft Managed Desktop staggers each release to identify any potential issues in your environment.</span></span> <span data-ttu-id="1680f-130">Lanseringen slutförs 28 dagar efter lanseringen från produktgruppen Microsoft 365 App.</span><span class="sxs-lookup"><span data-stu-id="1680f-130">We complete the rollout 28 days after the release from the Microsoft 365 App product group.</span></span> <span data-ttu-id="1680f-131">Microsoft Hanterat skrivbord schemalägger uppdaterings versioner till olika grupper för att ge tid för validering och testning enligt följande:</span><span class="sxs-lookup"><span data-stu-id="1680f-131">Microsoft Managed Desktop schedules update releases to different groups to allow time for validation and testing as follows:</span></span> 

- <span data-ttu-id="1680f-132">Test: noll dagar</span><span class="sxs-lookup"><span data-stu-id="1680f-132">Test: zero days</span></span>
- <span data-ttu-id="1680f-133">Första: noll dagar</span><span class="sxs-lookup"><span data-stu-id="1680f-133">First: zero days</span></span>
- <span data-ttu-id="1680f-134">Snabbt: 3 dagar</span><span class="sxs-lookup"><span data-stu-id="1680f-134">Fast: 3 days</span></span>
- <span data-ttu-id="1680f-135">Bred: 7 dagar</span><span class="sxs-lookup"><span data-stu-id="1680f-135">Broad: 7 days</span></span>

<span data-ttu-id="1680f-136">Microsoft Hanterat skrivbord anger en tidsgräns på sju [dagar för uppdateringar](/deployoffice/configure-update-settings-microsoft-365-apps) för enheter.</span><span class="sxs-lookup"><span data-stu-id="1680f-136">Microsoft Managed Desktop sets a seven-day [update deadline](/deployoffice/configure-update-settings-microsoft-365-apps) for devices.</span></span> <span data-ttu-id="1680f-137">När uppdateringen är tillgänglig måste den installeras inom sju dagar.</span><span class="sxs-lookup"><span data-stu-id="1680f-137">Once the update is available, it must be installed within seven days.</span></span> <span data-ttu-id="1680f-138">Användarna [meddelas](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) om att uppdateringar krävs på flera olika platser: programmet, i systemfältet 12 timmar före tidsgränsen, och de får en 15-minutersvarning före tidsgränsen.</span><span class="sxs-lookup"><span data-stu-id="1680f-138">Users are [notified](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) that updates are required in several locations: the application, in the system tray 12 hours prior to the deadline, and they receive a 15-minute warning prior to the deadline.</span></span> <span data-ttu-id="1680f-139">Alla Microsoft 365-applikationer måste vara stängda för att uppdateringen ska kunna slutföras.</span><span class="sxs-lookup"><span data-stu-id="1680f-139">All Microsoft 365 Apps must be closed for the update to complete.</span></span>

### <a name="pausing-or-rolling-back-an-update"></a><span data-ttu-id="1680f-140">Pausa eller distribuera en uppdatering</span><span class="sxs-lookup"><span data-stu-id="1680f-140">Pausing or rolling back an update</span></span>

<span data-ttu-id="1680f-141">Om du av någon anledning behöver pausa eller återställa Microsoft 365 programuppdateringen kan du arkivera en [administratörssupportbegäran](../working-with-managed-desktop/admin-support.md) via Microsoft Hanterat skrivbord portalen.</span><span class="sxs-lookup"><span data-stu-id="1680f-141">If you need to pause or roll back Microsoft 365 App update for any reason, file an [admin support request](../working-with-managed-desktop/admin-support.md) through the Microsoft Managed Desktop portal.</span></span>

<span data-ttu-id="1680f-142">Under en version Microsoft Hanterat skrivbord vi felfrekvensen för alla Microsoft 365-applikationer.</span><span class="sxs-lookup"><span data-stu-id="1680f-142">During a release, Microsoft Managed Desktop monitors the error rates of all Microsoft 365 Apps.</span></span> <span data-ttu-id="1680f-143">Om vi ser en betydande kvalitetsskillnad mellan den nya versionen och den föregående versionen kan vi kontakta dig via Microsoft Hanterat skrivbord-administratörsportalen.</span><span class="sxs-lookup"><span data-stu-id="1680f-143">If we note a significant difference in quality between the new release and its predecessor, we might contact you through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="1680f-144">Beroende på hur allvarligt det är frågar vi dig om du vill pausa utgivningen eller informera dig om att vi har vidtagit åtgärder för att minimera ett problem.</span><span class="sxs-lookup"><span data-stu-id="1680f-144">Depending on the severity, we will either ask if you want to pause the release or inform you that we have taken action to mitigate an issue.</span></span> 

### <a name="delivery-optimization"></a><span data-ttu-id="1680f-145">Leveransoptimering</span><span class="sxs-lookup"><span data-stu-id="1680f-145">Delivery optimization</span></span>

<span data-ttu-id="1680f-146">Leveransoptimering är en peer-to-peer-distributionsteknik som finns i Windows 10.</span><span class="sxs-lookup"><span data-stu-id="1680f-146">Delivery Optimization is a peer-to-peer distribution technology available in Windows 10.</span></span> <span data-ttu-id="1680f-147">Det gör att enheter kan dela innehåll, till exempel uppdateringar, som enheterna har laddat ned från Microsoft via Internet.</span><span class="sxs-lookup"><span data-stu-id="1680f-147">It allows devices to share content, such as updates, that the devices have downloaded from Microsoft over the internet.</span></span> <span data-ttu-id="1680f-148">Användning av den kan minska nätverkets bandbredd eftersom en enhet kan få delar av uppdateringen från en annan enhet på dess lokala nätverk i stället för att behöva ladda ned uppdateringen helt från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1680f-148">Using it can help reduce network bandwidth because a device can get portions of the update from another device on its local network instead of having to download the update completely from Microsoft.</span></span>

<span data-ttu-id="1680f-149">[Leveransoptimering](/deployoffice/delivery-optimization) är som standard aktiverad på enheter som kör Windows 10 Enterprise- Windows 10 Education versionerna.</span><span class="sxs-lookup"><span data-stu-id="1680f-149">[Delivery Optimization](/deployoffice/delivery-optimization) is enabled by default on devices running the Windows 10 Enterprise or Windows 10 Education editions.</span></span> 

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="1680f-150">Inställningar hanteras av Microsoft Hanterat skrivbord</span><span class="sxs-lookup"><span data-stu-id="1680f-150">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="1680f-151">Microsoft hanterar vissa inställningar som en del av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="1680f-151">Microsoft manages some settings as a part of the service.</span></span> <span data-ttu-id="1680f-152">Microsoft Hanterat skrivbord hanterar inte en baslinje för Office säkerhet men du kan ange en själv genom att följa linjerna [i Inställningar du hanterar.](#settings-you-manage)</span><span class="sxs-lookup"><span data-stu-id="1680f-152">Microsoft Managed Desktop doesn't manage an Office Security baseline but you can set one yourself by following the guidance in the [Settings you manage](#settings-you-manage) section.</span></span>

### <a name="update-settings"></a><span data-ttu-id="1680f-153">Uppdatera inställningar</span><span class="sxs-lookup"><span data-stu-id="1680f-153">Update settings</span></span>

<span data-ttu-id="1680f-154">Microsoft Hanterat skrivbord alla [uppdateringsinställningar för hanterade](/deployoffice/configure-update-settings-microsoft-365-apps) enheter och du bör ändra de här inställningarna.</span><span class="sxs-lookup"><span data-stu-id="1680f-154">Microsoft Managed Desktop maintains all [update settings](/deployoffice/configure-update-settings-microsoft-365-apps) for managed devices and you should modify these settings.</span></span>

### <a name="set-updates-to-occur-automatically"></a><span data-ttu-id="1680f-155">Konfigurera uppdateringar så att de sker automatiskt</span><span class="sxs-lookup"><span data-stu-id="1680f-155">Set updates to occur automatically</span></span>

<span data-ttu-id="1680f-156">**Standardvärde:** Aktiverat</span><span class="sxs-lookup"><span data-stu-id="1680f-156">**Default value**: Enabled</span></span>

<span data-ttu-id="1680f-157">Den här principen har konfigurerats för att säkerställa att alla Office-enheter kan hållas uppdaterade från molnet.</span><span class="sxs-lookup"><span data-stu-id="1680f-157">This policy is configured in order to ensure that all Office devices can be kept up to date from the cloud.</span></span> 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a><span data-ttu-id="1680f-158">Ange en tidsgräns när uppdateringar ska tillämpas</span><span class="sxs-lookup"><span data-stu-id="1680f-158">Set a deadline when updates have to be applied</span></span>

<span data-ttu-id="1680f-159">**Standardvärde:** 7 dagar</span><span class="sxs-lookup"><span data-stu-id="1680f-159">**Default value**: 7 days</span></span>

<span data-ttu-id="1680f-160">Principen **UpdateDeadline** används för att konfigurera respitperioden som användarna har innan en uppdatering tillämpas på enheten.</span><span class="sxs-lookup"><span data-stu-id="1680f-160">The **UpdateDeadline** policy is used to configure the grace period which users have before an update is enforced on the device.</span></span> <span data-ttu-id="1680f-161">Den här tidsgränsprincipen utlöser [även meddelanden](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) till användaren om de ändringar som krävs på deras enhet.</span><span class="sxs-lookup"><span data-stu-id="1680f-161">This deadline policy also triggers [notifications](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) to the user to inform them of the changes required on their device.</span></span>  

### <a name="defer-updates-on-a-device-for-a-period"></a><span data-ttu-id="1680f-162">Skjuta upp uppdateringar på en enhet under en period</span><span class="sxs-lookup"><span data-stu-id="1680f-162">Defer updates on a device for a period</span></span>

<span data-ttu-id="1680f-163">Den här principen har konfigurerats på olika sätt för varje enhetsgrupp för uppdateringshantering och krävs Microsoft Hanterat skrivbord kunna uppfylla uppdateringsmålen:</span><span class="sxs-lookup"><span data-stu-id="1680f-163">This policy is configured differently for each update management device group and is required for Microsoft Managed Desktop to meet its update targets:</span></span>  

- <span data-ttu-id="1680f-164">Test: noll dagar</span><span class="sxs-lookup"><span data-stu-id="1680f-164">Test: zero days</span></span>
- <span data-ttu-id="1680f-165">Första: noll dagar</span><span class="sxs-lookup"><span data-stu-id="1680f-165">First: zero days</span></span>
- <span data-ttu-id="1680f-166">Fast 7 dagar</span><span class="sxs-lookup"><span data-stu-id="1680f-166">Fast 7 days</span></span>
- <span data-ttu-id="1680f-167">Bred: 21 dagar</span><span class="sxs-lookup"><span data-stu-id="1680f-167">Broad: 21 days</span></span>

### <a name="update-notifications-settings"></a><span data-ttu-id="1680f-168">Uppdatera meddelandeinställningar</span><span class="sxs-lookup"><span data-stu-id="1680f-168">Update notifications settings</span></span>

<span data-ttu-id="1680f-169">**Standardvärde:** Falskt</span><span class="sxs-lookup"><span data-stu-id="1680f-169">**Default value**: False</span></span>

<span data-ttu-id="1680f-170">Inställningen "Dölj meddelanden om uppdateringar" är inställd på **Falskt** på Microsoft Hanterat skrivbord enheter för att ge den bästa uppdateringsupplevelsen för användare genom att meddela [dem](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) när uppdateringar krävs.</span><span class="sxs-lookup"><span data-stu-id="1680f-170">The "hide update notifications" setting is set to **False** on Microsoft Managed Desktop devices to provide the best update experience for users by [notifying](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) them when updates are required.</span></span>

### <a name="specify-a-location-to-look-for-updates"></a><span data-ttu-id="1680f-171">Ange en plats där du vill söka efter uppdateringar</span><span class="sxs-lookup"><span data-stu-id="1680f-171">Specify a location to look for updates</span></span>

<span data-ttu-id="1680f-172">**Standardvärde:** Månatlig Enterprise-kanal</span><span class="sxs-lookup"><span data-stu-id="1680f-172">**Default value**: Monthly Enterprise Channel</span></span>

<span data-ttu-id="1680f-173">En kombination av **UpdatePath- och** **UpdateChannel-principerna** används vid behov för att uppnå uppdateringsschemat.</span><span class="sxs-lookup"><span data-stu-id="1680f-173">A combination of the **UpdatePath** and **UpdateChannel** policies is used as needed to achieve the update schedule.</span></span> <span data-ttu-id="1680f-174">De här principerna är inställda för att säkerställa att Office alla enheter får uppdateringar direkt från CDN för Månatlig Enterprise-kanal.</span><span class="sxs-lookup"><span data-stu-id="1680f-174">These policies are set to ensure that all Office devices receive updates directly from the CDN for the Monthly Enterprise Channel.</span></span>

### <a name="specify-the-target-version-of-microsoft-365-apps"></a><span data-ttu-id="1680f-175">Ange målversionen av Microsoft 365-applikationer</span><span class="sxs-lookup"><span data-stu-id="1680f-175">Specify the Target Version of Microsoft 365 Apps</span></span>

<span data-ttu-id="1680f-176">Principen målversion används ibland av Microsoft Hanterat skrivbord för att återställa eller fästa en viss version av Office.</span><span class="sxs-lookup"><span data-stu-id="1680f-176">The Target Version policy is sometimes used by Microsoft Managed Desktop in order to roll back or pin a specific version of Office.</span></span> 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a><span data-ttu-id="1680f-177">Dölja alternativet för att aktivera eller inaktivera Office automatiska uppdateringar</span><span class="sxs-lookup"><span data-stu-id="1680f-177">Hide the option to enable or disable Office automatic updates</span></span>

<span data-ttu-id="1680f-178">**Standardvärde:** Aktiverat</span><span class="sxs-lookup"><span data-stu-id="1680f-178">**Default value**: Enabled</span></span>

<span data-ttu-id="1680f-179">Den här inställningen krävs för Microsoft Hanterat skrivbord ska uppfylla uppdateringsmålen för Microsoft 365 program.</span><span class="sxs-lookup"><span data-stu-id="1680f-179">This setting is required for Microsoft Managed Desktop to meet its update targets for Microsoft 365 Applications.</span></span> 

### <a name="first-run-settings"></a><span data-ttu-id="1680f-180">Inställningar för första körningen</span><span class="sxs-lookup"><span data-stu-id="1680f-180">First run settings</span></span> 

<span data-ttu-id="1680f-181">Det finns flera inställningar som påverkar beteendet första gången Office körs.</span><span class="sxs-lookup"><span data-stu-id="1680f-181">There are several settings that affect the behavior the first time Office is run.</span></span>

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a><span data-ttu-id="1680f-182">Acceptera licensvillkoren åt slutanvändaren</span><span class="sxs-lookup"><span data-stu-id="1680f-182">Accept the license terms on behalf of the end user</span></span>

<span data-ttu-id="1680f-183">**Standardvärde:** Inaktiverad</span><span class="sxs-lookup"><span data-stu-id="1680f-183">**Default value**: Disabled</span></span>

<span data-ttu-id="1680f-184">Första gången en användare öppnar Microsoft 365 app uppmanas de att godkänna licensvillkoren.</span><span class="sxs-lookup"><span data-stu-id="1680f-184">The first time a user opens a Microsoft 365 App, they are prompted to accept the license terms.</span></span> <span data-ttu-id="1680f-185">Om du vill godkänna licensvillkoren åt dina användare arkiverar du en tjänstbegäran till Microsoft Hanterat skrivbord Operations-teamet där du begär att den här inställningen ska aktiveras.</span><span class="sxs-lookup"><span data-stu-id="1680f-185">If you want to accept the license terms on behalf of your users, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

### <a name="suppress-outlook-mobile-check-box"></a><span data-ttu-id="1680f-186">Kryssrutan Hindra Outlook mobil</span><span class="sxs-lookup"><span data-stu-id="1680f-186">Suppress Outlook mobile check box</span></span>

<span data-ttu-id="1680f-187">**Standardvärde:** Inaktiverad</span><span class="sxs-lookup"><span data-stu-id="1680f-187">**Default value**: Disabled</span></span>

<span data-ttu-id="1680f-188">Första gången en användare öppnar Outlook uppmanas de att installera Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="1680f-188">The first time a user opens Outlook they are prompted to install Outlook Mobile.</span></span> <span data-ttu-id="1680f-189">Om du inte vill att användarna ska se den kryssrutan arkiverar du en tjänstbegäran med Microsoft Hanterat skrivbord Operations-teamet som frågar om den här inställningen ska aktiveras för dina enheter.</span><span class="sxs-lookup"><span data-stu-id="1680f-189">If you don’t want your users to see that check box, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled for your devices.</span></span> 

## <a name="other-settings"></a><span data-ttu-id="1680f-190">Andra inställningar</span><span class="sxs-lookup"><span data-stu-id="1680f-190">Other settings</span></span>

<span data-ttu-id="1680f-191">Det finns andra Microsoft 365 appinställningar som Microsoft Hanterat skrivbord kan konfigurera åt dig.</span><span class="sxs-lookup"><span data-stu-id="1680f-191">There are other Microsoft 365 App settings which Microsoft Managed Desktop can optionally configure on your behalf.</span></span> 

### <a name="disable-personal-onedrive"></a><span data-ttu-id="1680f-192">Inaktivera personliga OneDrive</span><span class="sxs-lookup"><span data-stu-id="1680f-192">Disable Personal OneDrive</span></span>

<span data-ttu-id="1680f-193">**Standardvärde:** Inaktiverad</span><span class="sxs-lookup"><span data-stu-id="1680f-193">**Default value**: Disabled</span></span>

<span data-ttu-id="1680f-194">Vissa organisationer är bekymrade över att användare ska ha åtkomst till både företagsfiler och personliga filer på sina enheter.</span><span class="sxs-lookup"><span data-stu-id="1680f-194">Some organizations are concerned about users having access to both corporate and personal files on their devices.</span></span> <span data-ttu-id="1680f-195">Du kan arkivera en tjänstförfrågan med Microsoft Hanterat skrivbord operations-teamet som ber om att den här inställningen aktiveras.</span><span class="sxs-lookup"><span data-stu-id="1680f-195">You can file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

## <a name="settings-you-manage"></a><span data-ttu-id="1680f-196">Inställningar hanterar du</span><span class="sxs-lookup"><span data-stu-id="1680f-196">Settings you manage</span></span>

<span data-ttu-id="1680f-197">Det finns många andra principer Microsoft Hanterat skrivbord ännu inte angett som en del av vår tjänst.</span><span class="sxs-lookup"><span data-stu-id="1680f-197">There are many other policies which Microsoft Managed Desktop does not yet set as a part of our service.</span></span> <span data-ttu-id="1680f-198">Du kan konfigurera de här Microsoft Intune med hjälp av tjänsten [Office Molnprincip.](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied)</span><span class="sxs-lookup"><span data-stu-id="1680f-198">You can configure these policies by using Microsoft Intune, which uses the [Office Cloud Policy](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service.</span></span> <span data-ttu-id="1680f-199">Följ de här anvisningarna om du vill ange dessa principer:</span><span class="sxs-lookup"><span data-stu-id="1680f-199">To set these policies, follow these steps:</span></span>

1. <span data-ttu-id="1680f-200">Logga in Microsoft Endpoint Manager administrationscentret.</span><span class="sxs-lookup"><span data-stu-id="1680f-200">Sign in to the Microsoft Endpoint Manager admin center.</span></span>
2. <span data-ttu-id="1680f-201">Välj **Program > Principer för Office appar > Skapa**</span><span class="sxs-lookup"><span data-stu-id="1680f-201">Select **Apps > Policies for Office apps > Create**</span></span>
3. <span data-ttu-id="1680f-202">Gör **följande på** sidan Skapa principkonfiguration:</span><span class="sxs-lookup"><span data-stu-id="1680f-202">On the **Create policy** configuration page, do the following:</span></span>
    - <span data-ttu-id="1680f-203">Ange ett namn.</span><span class="sxs-lookup"><span data-stu-id="1680f-203">Enter a name.</span></span>
    - <span data-ttu-id="1680f-204">Ange en beskrivning (valfritt).</span><span class="sxs-lookup"><span data-stu-id="1680f-204">Provide a description (optional).</span></span>
    - <span data-ttu-id="1680f-205">I **tilldelningar** väljer du om den här principen gäller för alla användare av Microsoft 365-appar för företag eller bara för användare som har anonym åtkomst till dokument med Office för webben.</span><span class="sxs-lookup"><span data-stu-id="1680f-205">In **assignments**, choose whether this policy applies to all users of Microsoft 365 Apps for enterprise, or just to users who anonymously access documents using Office for the web.</span></span>
    - <span data-ttu-id="1680f-206">Markera den AAD-baserade säkerhetsgrupp som har tilldelats till principkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="1680f-206">Select the AAD-based security group that is assigned to the policy configuration.</span></span> <span data-ttu-id="1680f-207">Varje principkonfiguration kan bara tilldelas en grupp och varje grupp kan bara tilldelas en principkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="1680f-207">Each policy configuration can only be assigned to one group, and each group can only be assigned one policy configuration.</span></span>
    - <span data-ttu-id="1680f-208">Konfigurera principinställningarna så att de inkluderas i principkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="1680f-208">Configure the policy settings to be included in the policy configuration.</span></span> <span data-ttu-id="1680f-209">Du kan söka efter principinställningsnamnet och hitta den principinställning som du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="1680f-209">You can search on the policy setting name to find the policy setting that you want to configure.</span></span> <span data-ttu-id="1680f-210">Du kan också filtrera på programmet, på om principen är en rekommenderad säkerhetsbaslinje och på om principen har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="1680f-210">You can also filter on the application, on whether the policy is a recommended security baseline, and on whether the policy has been configured.</span></span> <span data-ttu-id="1680f-211">Plattformskolumnen anger om principen tillämpas på Microsoft 365-appar för företag för Windows-enheter, Office för webben eller alla.</span><span class="sxs-lookup"><span data-stu-id="1680f-211">The platform column indicates whether the policy is applied to Microsoft 365 Apps for enterprise for Windows devices, Office for the web, or all.</span></span>
4. <span data-ttu-id="1680f-212">När du har gjort dina val väljer du **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="1680f-212">After you have made your selections, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="1680f-213">Office Konfigurationsprinciper stöder endast användarbaserad distribution</span><span class="sxs-lookup"><span data-stu-id="1680f-213">Office Configuration Policies only support user-based deployment</span></span>
