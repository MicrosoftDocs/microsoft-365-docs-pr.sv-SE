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
ms.openlocfilehash: f8dd666c41863192d866693c6860a64064f846e6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904858"
---
# <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="f45c7-104">Microsoft 365-appar för företag</span><span class="sxs-lookup"><span data-stu-id="f45c7-104">Microsoft 365 Apps for enterprise</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="f45c7-105">Inledande distribution</span><span class="sxs-lookup"><span data-stu-id="f45c7-105">Initial deployment</span></span>

<span data-ttu-id="f45c7-106">Microsoft Managed Desktop ser till att Microsoft 365-appar för företag (64-bitar) installeras som en del av bilden på alla [programenheter.](../service-description/device-list.md)</span><span class="sxs-lookup"><span data-stu-id="f45c7-106">Microsoft Managed Desktop ensures that Microsoft 365 Apps for enterprise (64-bit) are installed as a part of the image on all [program devices](../service-description/device-list.md).</span></span> <span data-ttu-id="f45c7-107">Alla följande program bör finnas på enheten när den levereras:</span><span class="sxs-lookup"><span data-stu-id="f45c7-107">All of the following applications should be present on the device when it's delivered:</span></span>

- <span data-ttu-id="f45c7-108">Word</span><span class="sxs-lookup"><span data-stu-id="f45c7-108">Word</span></span>
- <span data-ttu-id="f45c7-109">Excel</span><span class="sxs-lookup"><span data-stu-id="f45c7-109">Excel</span></span>
- <span data-ttu-id="f45c7-110">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f45c7-110">PowerPoint</span></span>
- <span data-ttu-id="f45c7-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="f45c7-111">Outlook</span></span>
- <span data-ttu-id="f45c7-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="f45c7-112">Publisher</span></span>
- <span data-ttu-id="f45c7-113">Åtkomst</span><span class="sxs-lookup"><span data-stu-id="f45c7-113">Access</span></span>
- <span data-ttu-id="f45c7-114">Skype för företag</span><span class="sxs-lookup"><span data-stu-id="f45c7-114">Skype for Business</span></span>
- <span data-ttu-id="f45c7-115">OneNote</span><span class="sxs-lookup"><span data-stu-id="f45c7-115">OneNote</span></span>

<span data-ttu-id="f45c7-116">Den här metoden minimerar nätverkets påverkan och ser till att användarna kan vara produktiva så fort de får sin enhet.</span><span class="sxs-lookup"><span data-stu-id="f45c7-116">This approach minimizes network impact and ensures that users can be productive as soon as they receive their device.</span></span> <span data-ttu-id="f45c7-117">Sedan distribuerar vi fler principer till hanterade enheter för att konfigurera programmen för användning.</span><span class="sxs-lookup"><span data-stu-id="f45c7-117">We then deploy more policies to managed devices to set up the applications for use.</span></span>

> [!NOTE]
> <span data-ttu-id="f45c7-118">Microsoft Teams distribueras separat från Microsoft 365-program för företag och ingår inte i basbilden.</span><span class="sxs-lookup"><span data-stu-id="f45c7-118">Microsoft Teams is deployed separately from Microsoft 365 Apps for enterprise and is not included in the base image.</span></span> 

### <a name="available-deployment-to-users"></a><span data-ttu-id="f45c7-119">Tillgänglig distribution för användare</span><span class="sxs-lookup"><span data-stu-id="f45c7-119">Available deployment to users</span></span>

<span data-ttu-id="f45c7-120">Om en användare av någon anledning inte har Microsoft 365-appar på sin enhet kan du använda ett paket för att returnera enheten till det förväntade läget.</span><span class="sxs-lookup"><span data-stu-id="f45c7-120">If a user does not have Microsoft 365 Apps on their device for any reason, you can use a package to return the device to its expected state.</span></span> <span data-ttu-id="f45c7-121">Lägg till användaren i **gruppen Modern workplace-office-Office365_Install** så blir apparna tillgängliga i företagsportalen.</span><span class="sxs-lookup"><span data-stu-id="f45c7-121">Add the user to the **Modern Workplace-Office-Office365_Install** group and the apps will become available to them in the Company Portal.</span></span>

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a><span data-ttu-id="f45c7-122">Microsoft 365-appar för företag (32-bitars)</span><span class="sxs-lookup"><span data-stu-id="f45c7-122">Microsoft 365 Apps for enterprise (32-bit)</span></span>

<span data-ttu-id="f45c7-123">Microsoft Managed Desktop stöder inte distribution av 32-bitarsversionen av M365-program för företag.</span><span class="sxs-lookup"><span data-stu-id="f45c7-123">Microsoft Managed Desktop doesn't support the deployment of the 32-bit version of M365 Apps for enterprise.</span></span>

## <a name="updates-to-microsoft-365-apps"></a><span data-ttu-id="f45c7-124">Uppdateringar till Microsoft 365-appar</span><span class="sxs-lookup"><span data-stu-id="f45c7-124">Updates to Microsoft 365 Apps</span></span>

<span data-ttu-id="f45c7-125">Microsoft 365 Apps är inställda på att uppdateras i [månadskanal för företag.](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)</span><span class="sxs-lookup"><span data-stu-id="f45c7-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span></span> <span data-ttu-id="f45c7-126">Den här övningen ger användarna nya Office-funktioner varje månad, men de får bara en uppdatering per månad på ett förutsägbart versionsschema.</span><span class="sxs-lookup"><span data-stu-id="f45c7-126">This practice provides your users with new Office features each month, but they'll receive just one update per month on a predictable release schedule.</span></span> <span data-ttu-id="f45c7-127">Uppdateringar släpps den andra tisdagen i månaden. dessa uppdateringar kan innehålla funktions-, säkerhets- och kvalitetsuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="f45c7-127">Updates are released on the second Tuesday of the month; these updates can include feature, security, and quality updates.</span></span> <span data-ttu-id="f45c7-128">Dessa uppdateringar görs automatiskt och hämtas direkt från Office CDN för den specifika kanalen.</span><span class="sxs-lookup"><span data-stu-id="f45c7-128">These updates occur automatically and are pulled directly from the Office CDN for that specific channel.</span></span>

<span data-ttu-id="f45c7-129">Varje version av Microsoft Hanterat skrivbord sprids för att identifiera potentiella problem i din miljö.</span><span class="sxs-lookup"><span data-stu-id="f45c7-129">Microsoft Managed Desktop staggers each release to identify any potential issues in your environment.</span></span> <span data-ttu-id="f45c7-130">Vi slutför lanseringen 28 dagar efter lanseringen från Microsoft 365 App-produktgruppen.</span><span class="sxs-lookup"><span data-stu-id="f45c7-130">We complete the rollout 28 days after the release from the Microsoft 365 App product group.</span></span> <span data-ttu-id="f45c7-131">Microsoft Hanterad dator schemalägger uppdaterings versioner för olika grupper för att ge tid för validering och testning enligt följande:</span><span class="sxs-lookup"><span data-stu-id="f45c7-131">Microsoft Managed Desktop schedules update releases to different groups to allow time for validation and testing as follows:</span></span> 

- <span data-ttu-id="f45c7-132">Test: noll dagar</span><span class="sxs-lookup"><span data-stu-id="f45c7-132">Test: zero days</span></span>
- <span data-ttu-id="f45c7-133">Första: noll dagar</span><span class="sxs-lookup"><span data-stu-id="f45c7-133">First: zero days</span></span>
- <span data-ttu-id="f45c7-134">Snabbt: 3 dagar</span><span class="sxs-lookup"><span data-stu-id="f45c7-134">Fast: 3 days</span></span>
- <span data-ttu-id="f45c7-135">Bred: 7 dagar</span><span class="sxs-lookup"><span data-stu-id="f45c7-135">Broad: 7 days</span></span>

<span data-ttu-id="f45c7-136">Tidsgränsen för uppdateringar för enheter fastställs sju [dagar](/deployoffice/configure-update-settings-microsoft-365-apps) i Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f45c7-136">Microsoft Managed Desktop sets a seven-day [update deadline](/deployoffice/configure-update-settings-microsoft-365-apps) for devices.</span></span> <span data-ttu-id="f45c7-137">När uppdateringen är tillgänglig måste den installeras inom sju dagar.</span><span class="sxs-lookup"><span data-stu-id="f45c7-137">Once the update is available, it must be installed within seven days.</span></span> <span data-ttu-id="f45c7-138">Användarna [meddelas](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) om att uppdateringar krävs på flera olika platser: programmet, i systemfältet 12 timmar före tidsgränsen, och de får en 15-minutersvarning före tidsgränsen.</span><span class="sxs-lookup"><span data-stu-id="f45c7-138">Users are [notified](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) that updates are required in several locations: the application, in the system tray 12 hours prior to the deadline, and they receive a 15-minute warning prior to the deadline.</span></span> <span data-ttu-id="f45c7-139">Alla Microsoft 365-appar måste vara stängda för att uppdateringen ska kunna slutföras.</span><span class="sxs-lookup"><span data-stu-id="f45c7-139">All Microsoft 365 Apps must be closed for the update to complete.</span></span>

### <a name="pausing-or-rolling-back-an-update"></a><span data-ttu-id="f45c7-140">Pausa eller distribuera en uppdatering</span><span class="sxs-lookup"><span data-stu-id="f45c7-140">Pausing or rolling back an update</span></span>

<span data-ttu-id="f45c7-141">Om du av någon anledning behöver pausa eller återställa programuppdateringen för Microsoft 365 arkiverar du en [administratörssupportbegäran](../working-with-managed-desktop/admin-support.md) via Microsoft Managed Desktop-portalen.</span><span class="sxs-lookup"><span data-stu-id="f45c7-141">If you need to pause or roll back Microsoft 365 App update for any reason, file an [admin support request](../working-with-managed-desktop/admin-support.md) through the Microsoft Managed Desktop portal.</span></span>

<span data-ttu-id="f45c7-142">Under en version övervakar Microsoft Managed Desktop felfrekvensen för alla Microsoft 365-appar.</span><span class="sxs-lookup"><span data-stu-id="f45c7-142">During a release, Microsoft Managed Desktop monitors the error rates of all Microsoft 365 Apps.</span></span> <span data-ttu-id="f45c7-143">Om vi ser en betydande kvalitetsskillnad mellan den nya versionen och den föregående versionen kan vi kontakta dig via administrationsportalen för Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f45c7-143">If we note a significant difference in quality between the new release and its predecessor, we might contact you through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="f45c7-144">Beroende på hur allvarligt det är frågar vi dig om du vill pausa utgivningen eller informera dig om att vi har vidtagit åtgärder för att minimera ett problem.</span><span class="sxs-lookup"><span data-stu-id="f45c7-144">Depending on the severity, we will either ask if you want to pause the release or inform you that we have taken action to mitigate an issue.</span></span> 

### <a name="delivery-optimization"></a><span data-ttu-id="f45c7-145">Leveransoptimering</span><span class="sxs-lookup"><span data-stu-id="f45c7-145">Delivery optimization</span></span>

<span data-ttu-id="f45c7-146">Leveransoptimering är en peer-to-peer-distributionsteknik i Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f45c7-146">Delivery Optimization is a peer-to-peer distribution technology available in Windows 10.</span></span> <span data-ttu-id="f45c7-147">Det gör att enheter kan dela innehåll, till exempel uppdateringar, som enheterna har laddat ned från Microsoft via Internet.</span><span class="sxs-lookup"><span data-stu-id="f45c7-147">It allows devices to share content, such as updates, that the devices have downloaded from Microsoft over the internet.</span></span> <span data-ttu-id="f45c7-148">Användning av den kan minska nätverkets bandbredd eftersom en enhet kan få delar av uppdateringen från en annan enhet på dess lokala nätverk i stället för att behöva ladda ned uppdateringen helt från Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f45c7-148">Using it can help reduce network bandwidth because a device can get portions of the update from another device on its local network instead of having to download the update completely from Microsoft.</span></span>

<span data-ttu-id="f45c7-149">[Leveransoptimering](/deployoffice/delivery-optimization) aktiveras som standard på enheter som kör versionerna Windows 10 Enterprise eller Windows 10 Education.</span><span class="sxs-lookup"><span data-stu-id="f45c7-149">[Delivery Optimization](/deployoffice/delivery-optimization) is enabled by default on devices running the Windows 10 Enterprise or Windows 10 Education editions.</span></span> 

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="f45c7-150">Inställningar som hanteras av Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="f45c7-150">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="f45c7-151">Microsoft hanterar vissa inställningar som en del av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="f45c7-151">Microsoft manages some settings as a part of the service.</span></span> <span data-ttu-id="f45c7-152">Microsoft Hanterat skrivbord hanterar inte en baslinje för Office-säkerhet men du kan ange en själv genom att följa linjerna i [avsnittet Inställningar du hanterar.](#settings-you-manage)</span><span class="sxs-lookup"><span data-stu-id="f45c7-152">Microsoft Managed Desktop doesn't manage an Office Security baseline but you can set one yourself by following the guidance in the [Settings you manage](#settings-you-manage) section.</span></span>

### <a name="update-settings"></a><span data-ttu-id="f45c7-153">Uppdatera inställningar</span><span class="sxs-lookup"><span data-stu-id="f45c7-153">Update settings</span></span>

<span data-ttu-id="f45c7-154">Microsoft Managed Desktop har alla [uppdateringsinställningar för](/deployoffice/configure-update-settings-microsoft-365-apps) hanterade enheter och du bör ändra de här inställningarna.</span><span class="sxs-lookup"><span data-stu-id="f45c7-154">Microsoft Managed Desktop maintains all [update settings](/deployoffice/configure-update-settings-microsoft-365-apps) for managed devices and you should modify these settings.</span></span>

### <a name="set-updates-to-occur-automatically"></a><span data-ttu-id="f45c7-155">Konfigurera uppdateringar så att de sker automatiskt</span><span class="sxs-lookup"><span data-stu-id="f45c7-155">Set updates to occur automatically</span></span>

<span data-ttu-id="f45c7-156">**Standardvärde:** Aktiverat</span><span class="sxs-lookup"><span data-stu-id="f45c7-156">**Default value**: Enabled</span></span>

<span data-ttu-id="f45c7-157">Den här principen har konfigurerats för att säkerställa att alla Office-enheter kan hållas uppdaterade från molnet.</span><span class="sxs-lookup"><span data-stu-id="f45c7-157">This policy is configured in order to ensure that all Office devices can be kept up to date from the cloud.</span></span> 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a><span data-ttu-id="f45c7-158">Ange en tidsgräns när uppdateringar ska tillämpas</span><span class="sxs-lookup"><span data-stu-id="f45c7-158">Set a deadline when updates have to be applied</span></span>

<span data-ttu-id="f45c7-159">**Standardvärde:** 7 dagar</span><span class="sxs-lookup"><span data-stu-id="f45c7-159">**Default value**: 7 days</span></span>

<span data-ttu-id="f45c7-160">Principen **UpdateDeadline** används för att konfigurera respitperioden som användarna har innan en uppdatering tillämpas på enheten.</span><span class="sxs-lookup"><span data-stu-id="f45c7-160">The **UpdateDeadline** policy is used to configure the grace period which users have before an update is enforced on the device.</span></span> <span data-ttu-id="f45c7-161">Den här tidsgränsprincipen utlöser [även meddelanden](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) till användaren om de ändringar som krävs på deras enhet.</span><span class="sxs-lookup"><span data-stu-id="f45c7-161">This deadline policy also triggers [notifications](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) to the user to inform them of the changes required on their device.</span></span>  

### <a name="defer-updates-on-a-device-for-a-period"></a><span data-ttu-id="f45c7-162">Skjuta upp uppdateringar på en enhet under en period</span><span class="sxs-lookup"><span data-stu-id="f45c7-162">Defer updates on a device for a period</span></span>

<span data-ttu-id="f45c7-163">Den här principen har konfigurerats på olika sätt för varje enhetsgrupp för uppdateringshantering och krävs för att Microsoft Managed Desktop ska uppfylla sina uppdateringsmål:</span><span class="sxs-lookup"><span data-stu-id="f45c7-163">This policy is configured differently for each update management device group and is required for Microsoft Managed Desktop to meet its update targets:</span></span>  

- <span data-ttu-id="f45c7-164">Test: noll dagar</span><span class="sxs-lookup"><span data-stu-id="f45c7-164">Test: zero days</span></span>
- <span data-ttu-id="f45c7-165">Första: noll dagar</span><span class="sxs-lookup"><span data-stu-id="f45c7-165">First: zero days</span></span>
- <span data-ttu-id="f45c7-166">Fast 7 dagar</span><span class="sxs-lookup"><span data-stu-id="f45c7-166">Fast 7 days</span></span>
- <span data-ttu-id="f45c7-167">Bred: 21 dagar</span><span class="sxs-lookup"><span data-stu-id="f45c7-167">Broad: 21 days</span></span>

### <a name="update-notifications-settings"></a><span data-ttu-id="f45c7-168">Uppdatera meddelandeinställningar</span><span class="sxs-lookup"><span data-stu-id="f45c7-168">Update notifications settings</span></span>

<span data-ttu-id="f45c7-169">**Standardvärde:** Falskt</span><span class="sxs-lookup"><span data-stu-id="f45c7-169">**Default value**: False</span></span>

<span data-ttu-id="f45c7-170">Inställningen "Dölj uppdateringsmeddelanden" är inställd på **False** på Microsoft Managed Desktop-enheter för att ge bästa möjliga uppdateringsupplevelse för användare genom att meddela [dem](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) när uppdateringar krävs.</span><span class="sxs-lookup"><span data-stu-id="f45c7-170">The "hide update notifications" setting is set to **False** on Microsoft Managed Desktop devices to provide the best update experience for users by [notifying](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) them when updates are required.</span></span>

### <a name="specify-a-location-to-look-for-updates"></a><span data-ttu-id="f45c7-171">Ange en plats där du vill söka efter uppdateringar</span><span class="sxs-lookup"><span data-stu-id="f45c7-171">Specify a location to look for updates</span></span>

<span data-ttu-id="f45c7-172">**Standardvärde:** Månatlig Enterprise-kanal</span><span class="sxs-lookup"><span data-stu-id="f45c7-172">**Default value**: Monthly Enterprise Channel</span></span>

<span data-ttu-id="f45c7-173">En kombination av **UpdatePath- och** **UpdateChannel-principerna** används vid behov för att uppnå uppdateringsschemat.</span><span class="sxs-lookup"><span data-stu-id="f45c7-173">A combination of the **UpdatePath** and **UpdateChannel** policies is used as needed to achieve the update schedule.</span></span> <span data-ttu-id="f45c7-174">De här principerna är inställda på att säkerställa att alla Office-enheter får uppdateringar direkt från CDN för månatlig enterprise-kanal.</span><span class="sxs-lookup"><span data-stu-id="f45c7-174">These policies are set to ensure that all Office devices receive updates directly from the CDN for the Monthly Enterprise Channel.</span></span>

### <a name="specify-the-target-version-of-microsoft-365-apps"></a><span data-ttu-id="f45c7-175">Ange målversionen av Microsoft 365-appar</span><span class="sxs-lookup"><span data-stu-id="f45c7-175">Specify the Target Version of Microsoft 365 Apps</span></span>

<span data-ttu-id="f45c7-176">Principen målversion används ibland av Microsoft Managed Desktop för att återställa eller fästa en viss version av Office.</span><span class="sxs-lookup"><span data-stu-id="f45c7-176">The Target Version policy is sometimes used by Microsoft Managed Desktop in order to roll back or pin a specific version of Office.</span></span> 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a><span data-ttu-id="f45c7-177">Dölja alternativet för att aktivera eller inaktivera automatiska uppdateringar i Office</span><span class="sxs-lookup"><span data-stu-id="f45c7-177">Hide the option to enable or disable Office automatic updates</span></span>

<span data-ttu-id="f45c7-178">**Standardvärde:** Aktiverat</span><span class="sxs-lookup"><span data-stu-id="f45c7-178">**Default value**: Enabled</span></span>

<span data-ttu-id="f45c7-179">Den här inställningen krävs för att Microsoft Managed Desktop ska uppfylla uppdateringsmålen för Microsoft 365-program.</span><span class="sxs-lookup"><span data-stu-id="f45c7-179">This setting is required for Microsoft Managed Desktop to meet its update targets for Microsoft 365 Applications.</span></span> 

### <a name="first-run-settings"></a><span data-ttu-id="f45c7-180">Inställningar för första körningen</span><span class="sxs-lookup"><span data-stu-id="f45c7-180">First run settings</span></span> 

<span data-ttu-id="f45c7-181">Det finns flera inställningar som påverkar beteendet första gången Office körs.</span><span class="sxs-lookup"><span data-stu-id="f45c7-181">There are several settings that affect the behavior the first time Office is run.</span></span>

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a><span data-ttu-id="f45c7-182">Acceptera licensvillkoren åt slutanvändaren</span><span class="sxs-lookup"><span data-stu-id="f45c7-182">Accept the license terms on behalf of the end user</span></span>

<span data-ttu-id="f45c7-183">**Standardvärde:** Inaktiverad</span><span class="sxs-lookup"><span data-stu-id="f45c7-183">**Default value**: Disabled</span></span>

<span data-ttu-id="f45c7-184">Första gången en användare öppnar en Microsoft 365-app uppmanas de att godkänna licensvillkoren.</span><span class="sxs-lookup"><span data-stu-id="f45c7-184">The first time a user opens a Microsoft 365 App, they are prompted to accept the license terms.</span></span> <span data-ttu-id="f45c7-185">Om du vill godkänna licensvillkoren åt dina användare arkiverar du en tjänstbegäran till Microsoft Managed Desktop Operations-teamet och ber om att den här inställningen aktiveras.</span><span class="sxs-lookup"><span data-stu-id="f45c7-185">If you want to accept the license terms on behalf of your users, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

### <a name="suppress-outlook-mobile-check-box"></a><span data-ttu-id="f45c7-186">Kryssrutan Ignorera Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="f45c7-186">Suppress Outlook mobile check box</span></span>

<span data-ttu-id="f45c7-187">**Standardvärde:** Inaktiverad</span><span class="sxs-lookup"><span data-stu-id="f45c7-187">**Default value**: Disabled</span></span>

<span data-ttu-id="f45c7-188">Första gången outlook öppnas uppmanas användaren att installera Outlook Mobile.</span><span class="sxs-lookup"><span data-stu-id="f45c7-188">The first time a user opens Outlook they are prompted to install Outlook Mobile.</span></span> <span data-ttu-id="f45c7-189">Om du inte vill att användarna ska se den kryssrutan arkiverar du en tjänstbegäran till Microsoft Managed Desktop Operations-teamet och frågar om den här inställningen ska aktiveras för dina enheter.</span><span class="sxs-lookup"><span data-stu-id="f45c7-189">If you don’t want your users to see that check box, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled for your devices.</span></span> 

## <a name="other-settings"></a><span data-ttu-id="f45c7-190">Andra inställningar</span><span class="sxs-lookup"><span data-stu-id="f45c7-190">Other settings</span></span>

<span data-ttu-id="f45c7-191">Det finns andra Inställningar för Microsoft 365-appen som Microsoft Hanterat skrivbord kan du konfigurera åt dig.</span><span class="sxs-lookup"><span data-stu-id="f45c7-191">There are other Microsoft 365 App settings which Microsoft Managed Desktop can optionally configure on your behalf.</span></span> 

### <a name="disable-personal-onedrive"></a><span data-ttu-id="f45c7-192">Inaktivera personlig OneDrive</span><span class="sxs-lookup"><span data-stu-id="f45c7-192">Disable Personal OneDrive</span></span>

<span data-ttu-id="f45c7-193">**Standardvärde:** Inaktiverad</span><span class="sxs-lookup"><span data-stu-id="f45c7-193">**Default value**: Disabled</span></span>

<span data-ttu-id="f45c7-194">Vissa organisationer är bekymrade över att användare ska ha åtkomst till både företagsfiler och personliga filer på sina enheter.</span><span class="sxs-lookup"><span data-stu-id="f45c7-194">Some organizations are concerned about users having access to both corporate and personal files on their devices.</span></span> <span data-ttu-id="f45c7-195">Du kan skicka en tjänstbegäran till Microsoft Managed Desktop Operations-teamet och begära att den här inställningen aktiveras.</span><span class="sxs-lookup"><span data-stu-id="f45c7-195">You can file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

## <a name="settings-you-manage"></a><span data-ttu-id="f45c7-196">Inställningar som du hanterar</span><span class="sxs-lookup"><span data-stu-id="f45c7-196">Settings you manage</span></span>

<span data-ttu-id="f45c7-197">Det finns många andra principer som Ännu inte angetts som en del av vår tjänst av Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f45c7-197">There are many other policies which Microsoft Managed Desktop does not yet set as a part of our service.</span></span> <span data-ttu-id="f45c7-198">Du kan konfigurera de här principerna med hjälp av Microsoft Intune, som använder [molnprinciptjänsten för Office.](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied)</span><span class="sxs-lookup"><span data-stu-id="f45c7-198">You can configure these policies by using Microsoft Intune, which uses the [Office Cloud Policy](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service.</span></span> <span data-ttu-id="f45c7-199">Följ de här anvisningarna om du vill ange dessa principer:</span><span class="sxs-lookup"><span data-stu-id="f45c7-199">To set these policies, follow these steps:</span></span>

1.  <span data-ttu-id="f45c7-200">Logga in på administrationscentret för Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="f45c7-200">Sign in to the Microsoft Endpoint Manager admin center.</span></span>
2.  <span data-ttu-id="f45c7-201">Välj **Program > Principer för Office-> Skapa**</span><span class="sxs-lookup"><span data-stu-id="f45c7-201">Select **Apps > Policies for Office apps > Create**</span></span>
3.  <span data-ttu-id="f45c7-202">Gör **följande på** sidan Skapa principkonfiguration:</span><span class="sxs-lookup"><span data-stu-id="f45c7-202">On the **Create policy** configuration page, do the following:</span></span>
    - <span data-ttu-id="f45c7-203">Ange ett namn.</span><span class="sxs-lookup"><span data-stu-id="f45c7-203">Enter a name.</span></span>
    - <span data-ttu-id="f45c7-204">Ange en beskrivning (valfritt).</span><span class="sxs-lookup"><span data-stu-id="f45c7-204">Provide a description (optional).</span></span>
    - <span data-ttu-id="f45c7-205">I **tilldelningar** väljer du om den här principen ska gälla för alla användare av Microsoft 365-appar för företag eller bara för användare som har anonym åtkomst till dokument med Office för webben.</span><span class="sxs-lookup"><span data-stu-id="f45c7-205">In **assignments**, choose whether this policy applies to all users of Microsoft 365 Apps for enterprise, or just to users who anonymously access documents using Office for the web.</span></span>
    - <span data-ttu-id="f45c7-206">Markera den AAD-baserade säkerhetsgrupp som har tilldelats till principkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="f45c7-206">Select the AAD-based security group that is assigned to the policy configuration.</span></span> <span data-ttu-id="f45c7-207">Varje principkonfiguration kan bara tilldelas en grupp och varje grupp kan bara tilldelas en principkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="f45c7-207">Each policy configuration can only be assigned to one group, and each group can only be assigned one policy configuration.</span></span>
    - <span data-ttu-id="f45c7-208">Konfigurera principinställningarna så att de inkluderas i principkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="f45c7-208">Configure the policy settings to be included in the policy configuration.</span></span> <span data-ttu-id="f45c7-209">Du kan söka efter principinställningsnamnet och hitta den principinställning som du vill konfigurera.</span><span class="sxs-lookup"><span data-stu-id="f45c7-209">You can search on the policy setting name to find the policy setting that you want to configure.</span></span> <span data-ttu-id="f45c7-210">Du kan också filtrera på programmet, på om principen är en rekommenderad säkerhetsbaslinje och på om principen har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="f45c7-210">You can also filter on the application, on whether the policy is a recommended security baseline, and on whether the policy has been configured.</span></span> <span data-ttu-id="f45c7-211">Plattformskolumnen anger om principen tillämpas på Microsoft 365-appar för företag för Windows-enheter, Office för webben eller alla.</span><span class="sxs-lookup"><span data-stu-id="f45c7-211">The platform column indicates whether the policy is applied to Microsoft 365 Apps for enterprise for Windows devices, Office for the web, or all.</span></span>
4.  <span data-ttu-id="f45c7-212">När du har gjort dina val väljer du **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="f45c7-212">After you have made your selections, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="f45c7-213">Konfigurationsprinciper för Office stöder endast användarbaserad distribution</span><span class="sxs-lookup"><span data-stu-id="f45c7-213">Office Configuration Policies only support user-based deployment</span></span>