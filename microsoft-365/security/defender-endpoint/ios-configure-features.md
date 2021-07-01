---
title: Konfigurera Microsoft Defender för slutpunkt för iOS-funktioner
description: Här beskrivs hur du distribuerar Microsoft Defender för Slutpunkt i iOS-funktioner
keywords: microsoft, defender, Microsoft Defender för Slutpunkt, ios, konfigurera, funktioner, ios
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 749e03cb9d14476245baea82c21d322d4d726aad
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230013"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="0991d-104">Konfigurera Microsoft Defender för slutpunkt för iOS-funktioner</span><span class="sxs-lookup"><span data-stu-id="0991d-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0991d-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="0991d-105">**Applies to:**</span></span>
- [<span data-ttu-id="0991d-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="0991d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0991d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0991d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0991d-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="0991d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0991d-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="0991d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="0991d-110">Defender för Endpoint i iOS skulle använda ett VPN för att tillhandahålla webskyddsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="0991d-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="0991d-111">Det här är inte en vanlig VPN och är en lokal/självslingande VPN som inte tar trafik utanför enheten.</span><span class="sxs-lookup"><span data-stu-id="0991d-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="0991d-112">Villkorsstyrd åtkomst med Defender för slutpunkt i iOS</span><span class="sxs-lookup"><span data-stu-id="0991d-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="0991d-113">Microsoft Defender för slutpunkt på iOS tillsammans med Microsoft Intune och Azure Active Directory aktiverar tvingande enhetsefterlevnad och villkorsstyrd åtkomstprincip baserat på enhetens riskresultat.</span><span class="sxs-lookup"><span data-stu-id="0991d-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk score.</span></span> <span data-ttu-id="0991d-114">Defender för Endpoint är en MTD-lösning (Mobile Threat Defense) som du kan distribuera för att utnyttja den här funktionen via Intune.</span><span class="sxs-lookup"><span data-stu-id="0991d-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="0991d-115">Mer information om hur du konfigurera villkorsstyrd åtkomst med Defender för slutpunkt i iOS finns [i Defender för Endpoint och Intune.](/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="0991d-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](/mem/intune/protect/advanced-threat-protection).</span></span>

### <a name="jailbreak-detection-by-microsoft-defender-for-endpoint"></a><span data-ttu-id="0991d-116">Identifiering av identifiering av Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="0991d-116">Jailbreak detection by Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="0991d-117">I Microsoft Defender för Endpoint går det att identifiera ohanterade och hanterade enheter som är jailbroken.</span><span class="sxs-lookup"><span data-stu-id="0991d-117">Microsoft Defender for Endpoint has the capability of detecting unmanaged and managed devices that are jailbroken.</span></span> <span data-ttu-id="0991d-118">Om en enhet identifieras som jailbroken kommer en varning med hög risk att rapporteras till Säkerhetscenter, och om villkorsstyrd åtkomst konfigureras baserat på enhetsriskresultat blockeras enheten från att komma åt företagsdata.</span><span class="sxs-lookup"><span data-stu-id="0991d-118">If a device is detected to be jailbroken, a **High**-risk alert will be reported to Security Center and if Conditional Access is setup based on device risk score, then the device will be blocked from accessing corporate data.</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="0991d-119">Web Protection och VPN</span><span class="sxs-lookup"><span data-stu-id="0991d-119">Web Protection and VPN</span></span>

<span data-ttu-id="0991d-120">Som standard inkluderar och aktiverar Defender för Slutpunkt i iOS webbskyddsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="0991d-120">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="0991d-121">[Webbskydd](web-protection-overview.md) hjälper till att skydda enheter mot webbhot och skyddar användare mot nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="0991d-121">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="0991d-122">Defender för Endpoint på iOS använder en VPN för att tillhandahålla detta skydd.</span><span class="sxs-lookup"><span data-stu-id="0991d-122">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="0991d-123">Observera att det här är en lokal VPN och till skillnad från traditionell VPN skickas inte nätverkstrafik utanför enheten.</span><span class="sxs-lookup"><span data-stu-id="0991d-123">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="0991d-124">När den är aktiverad som standard kan det finnas fall där du måste inaktivera VPN.</span><span class="sxs-lookup"><span data-stu-id="0991d-124">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="0991d-125">Du kanske till exempel vill köra vissa appar som inte fungerar när en VPN konfigureras.</span><span class="sxs-lookup"><span data-stu-id="0991d-125">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="0991d-126">I sådana fall kan du välja att inaktivera VPN från appen på enheten genom att följa stegen nedan:</span><span class="sxs-lookup"><span data-stu-id="0991d-126">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="0991d-127">På din iOS-enhet öppnar du **Inställningar,** klickar eller trycker på **Allmänt** och sedan **VPN.**</span><span class="sxs-lookup"><span data-stu-id="0991d-127">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="0991d-128">Klicka eller tryck på i-knappen för Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="0991d-128">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="0991d-129">Inaktivera ANSLUT **för att** inaktivera VPN.</span><span class="sxs-lookup"><span data-stu-id="0991d-129">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0991d-130">![VPN-konfiguration ansluter på begäran](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="0991d-130">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="0991d-131">Web Protection är inte tillgängligt när VPN inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="0991d-131">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="0991d-132">Om du vill återaktivera Web Protection öppnar du appen Microsoft Defender för Endpoint på enheten och klickar eller trycker på **Starta VPN.**</span><span class="sxs-lookup"><span data-stu-id="0991d-132">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="0991d-133">Det finns flera VPN-profiler</span><span class="sxs-lookup"><span data-stu-id="0991d-133">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="0991d-134">Apple iOS stöder inte flera vpn som gäller hela enheten för att vara aktiva samtidigt.</span><span class="sxs-lookup"><span data-stu-id="0991d-134">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="0991d-135">Även om flera VPN-profiler kan finnas på enheten kan bara ett VPN vara aktivt i taget.</span><span class="sxs-lookup"><span data-stu-id="0991d-135">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>

## <a name="configure-microsoft-defender-for-endpoint-risk-signal-in-app-protection-policy-mam"></a><span data-ttu-id="0991d-136">Konfigurera Microsoft Defender för Slutpunktsrisk signal i programskyddsprincip (MAM)</span><span class="sxs-lookup"><span data-stu-id="0991d-136">Configure Microsoft Defender for Endpoint risk signal in app protection policy (MAM)</span></span>

<span data-ttu-id="0991d-137">Microsoft Defender för Endpoint kan konfigureras för att skicka hotsignaler som ska användas i appskyddsprinciper (APP, som även kallas MAM) på iOS/iPadOS.</span><span class="sxs-lookup"><span data-stu-id="0991d-137">Microsoft Defender for Endpoint can be configured to send threat signals to be used in App Protection Policies (APP, also known as MAM) on iOS/iPadOS.</span></span> <span data-ttu-id="0991d-138">Med den här funktionen kan du även använda Microsoft Defender för Endpoint för att skydda åtkomsten till företagsdata från oregistrerade enheter.</span><span class="sxs-lookup"><span data-stu-id="0991d-138">With this capability, you can use Microsoft Defender for Endpoint to protect access to corporate data from unenrolled devices as well.</span></span>

<span data-ttu-id="0991d-139">Steg för att konfigurera principer för programskydd med Microsoft Defender för Slutpunkt är enligt nedan:</span><span class="sxs-lookup"><span data-stu-id="0991d-139">Steps to setup app protection policies with Microsoft Defender for Endpoint are as below:</span></span>

1. <span data-ttu-id="0991d-140">Konfigurera anslutningen från din klientorganisation Microsoft Endpoint Manager Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="0991d-140">Set up the connection from your Microsoft Endpoint Manager tenant to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="0991d-141">I [Administrationscenter](https://go.microsoft.com/fwlink/?linkid=2109431)för Microsoft Endpoint Manager går du till Kopplingar för klientorganisationsadministration och tokens Microsoft Defender för slutpunkt (under flera plattformar) eller  >  **Slutpunktssäkerhet** Microsoft Defender för Slutpunkt (under Installation) och aktiverar  >     >   växlingsknapparna under Programskyddsprincip Inställningar för **iOS.**</span><span class="sxs-lookup"><span data-stu-id="0991d-141">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Tenant Administration** > **Connectors and tokens** > **Microsoft Defender for Endpoint** (under Cross platform) or **Endpoint Security** > **Microsoft Defender for Endpoint** (under Setup) and turn on the toggles under **App Protection Policy Settings for iOS**.</span></span>
1. <span data-ttu-id="0991d-142">Välj Spara.</span><span class="sxs-lookup"><span data-stu-id="0991d-142">Select Save.</span></span> <span data-ttu-id="0991d-143">Anslutningsstatus **visas nu** som **Aktiverad.**</span><span class="sxs-lookup"><span data-stu-id="0991d-143">You should see **Connection status** is now set to **Enabled**.</span></span>
1. <span data-ttu-id="0991d-144">Skapa programskyddsprincip: När konfigurationen av Microsoft Defender för Endpoint-kopplingen är klar går du till  >  **Programskyddsprinciper** (under Princip) för att skapa en ny princip eller uppdatera en befintlig.</span><span class="sxs-lookup"><span data-stu-id="0991d-144">Create app protection policy: After your Microsoft Defender for Endpoint connector setup is complete, navigate to **Apps** > **App protection policies** (under Policy) to create a new policy or update an existing one.</span></span>
1. <span data-ttu-id="0991d-145">Välj den plattform, **appar, dataskydd, åtkomstkravinställningar** som din organisation kräver för principen.</span><span class="sxs-lookup"><span data-stu-id="0991d-145">Select the platform, **Apps, Data protection, Access requirements** settings that your organization requires for your policy.</span></span>
1. <span data-ttu-id="0991d-146">Under **Villkor för**  >  **villkorsstyrd** start av enhet hittar du inställningen **Max hotnivå för tillåtna enheter.**</span><span class="sxs-lookup"><span data-stu-id="0991d-146">Under **Conditional launch** > **Device conditions**, you will find the setting **Max allowed device threat level**.</span></span> <span data-ttu-id="0991d-147">Det här måste konfigureras för antingen Låg, Medel, Hög eller Skyddad.</span><span class="sxs-lookup"><span data-stu-id="0991d-147">This will need to be configured to either Low, Medium, High, or Secured.</span></span> <span data-ttu-id="0991d-148">De tillgängliga åtgärderna blir Blockera åtkomst **eller** **Rensa data.**</span><span class="sxs-lookup"><span data-stu-id="0991d-148">The actions available to you will be **Block access** or **Wipe data**.</span></span> <span data-ttu-id="0991d-149">Det kan visas en informationsdialogruta för att kontrollera att du har angett kopplingen innan den här inställningen används.</span><span class="sxs-lookup"><span data-stu-id="0991d-149">You may see an informational dialog to make sure you have your connector set up prior to this setting take effect.</span></span> <span data-ttu-id="0991d-150">Om kopplingen redan är konfigurerad kan du ignorera den här dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="0991d-150">If your connector is already set up, you may ignore this dialog.</span></span>
1. <span data-ttu-id="0991d-151">Slutför med Uppgifter och spara principen.</span><span class="sxs-lookup"><span data-stu-id="0991d-151">Finish with Assignments and save your policy.</span></span>

<span data-ttu-id="0991d-152">Mer information om MAM- eller appskyddsprincip finns i [principinställningar för iOS-programskydd.](/mem/intune/apps/app-protection-policy-settings-ios)</span><span class="sxs-lookup"><span data-stu-id="0991d-152">For more details on MAM or app protection policy, see [iOS app protection policy settings](/mem/intune/apps/app-protection-policy-settings-ios).</span></span>

### <a name="deploying-microsoft-defender-for-endpoint-for-mam-or-on-unenrolled-devices"></a><span data-ttu-id="0991d-153">Distribuera Microsoft Defender för slutpunkt för MAM eller på oregistrerade enheter</span><span class="sxs-lookup"><span data-stu-id="0991d-153">Deploying Microsoft Defender for Endpoint for MAM or on unenrolled devices</span></span>

<span data-ttu-id="0991d-154">Microsoft Defender för slutpunkt i iOS aktiverar Scenariot för programskyddsprincip och är tillgängligt i Apple App Store.</span><span class="sxs-lookup"><span data-stu-id="0991d-154">Microsoft Defender for Endpoint on iOS enables the App Protection Policy scenario and is available in the Apple app store.</span></span>

<span data-ttu-id="0991d-155">Slutanvändarna bör installera den senaste versionen av programmet direkt från Apple App Store.</span><span class="sxs-lookup"><span data-stu-id="0991d-155">End-users should install the latest version of the app directly from the Apple app store.</span></span>

## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="0991d-156">Konfigurera efterlevnadsprincip mot jailbroken enheter</span><span class="sxs-lookup"><span data-stu-id="0991d-156">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="0991d-157">För att skydda företagsdata från att kommas åt på jailbroken iOS-enheter rekommenderar vi att du konfigurerar följande efterlevnadsprincip på Intune.</span><span class="sxs-lookup"><span data-stu-id="0991d-157">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="0991d-158">Identifiering av identifiering av objekt är en funktion som tillhandahålls av Microsoft Defender för Endpoint i iOS.</span><span class="sxs-lookup"><span data-stu-id="0991d-158">Jailbreak detection is a capability provided by Microsoft Defender for Endpoint on iOS.</span></span> <span data-ttu-id="0991d-159">Vi rekommenderar dock att du inställningar den här principen som ytterligare skydd mot scenarier.</span><span class="sxs-lookup"><span data-stu-id="0991d-159">However, we recommend that you setup this policy as an additional layer of defense against jailbreak scenarios.</span></span>

<span data-ttu-id="0991d-160">Följ stegen nedan för att skapa en efterlevnadsprincip mot jailbroken enheter.</span><span class="sxs-lookup"><span data-stu-id="0991d-160">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="0991d-161">I [Microsoft Endpoint Manager administrationscenter går](https://go.microsoft.com/fwlink/?linkid=2109431)du till Principer för efterlevnad av **enheter**  ->  **Skapa**  ->  **princip.**</span><span class="sxs-lookup"><span data-stu-id="0991d-161">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="0991d-162">Välj "iOS/iPadOS" som plattform och klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="0991d-162">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0991d-163">![Skapa princip](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="0991d-163">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="0991d-164">Ange ett namn på principen, till exempel "Efterlevnadsprincip för Företag".</span><span class="sxs-lookup"><span data-stu-id="0991d-164">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="0991d-165">På sidan inställningar för efterlevnad klickar du för att expandera **avsnittet Enhetshälsa** och klickar på **Spärra för** **Jailbroken-enheter.**</span><span class="sxs-lookup"><span data-stu-id="0991d-165">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0991d-166">![Princip Inställningar](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="0991d-166">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="0991d-167">I avsnittet **Åtgärd för icke-efterlevnad** väljer du åtgärderna enligt dina krav och väljer **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="0991d-167">In the **Action for noncompliance** section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0991d-168">![Principåtgärder](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="0991d-168">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="0991d-169">I avsnittet **Tilldelningar** väljer du de användargrupper som du vill inkludera för den här principen och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="0991d-169">In the **Assignments** section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="0991d-170">I avsnittet **Granska+Skapa** kontrollerar du att all information som angetts är korrekt och väljer sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="0991d-170">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="0991d-171">Konfigurera anpassade indikatorer</span><span class="sxs-lookup"><span data-stu-id="0991d-171">Configure custom indicators</span></span>

<span data-ttu-id="0991d-172">Med Defender för Slutpunkt i iOS kan administratörer även konfigurera anpassade indikatorer på iOS-enheter.</span><span class="sxs-lookup"><span data-stu-id="0991d-172">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="0991d-173">Mer information om hur du konfigurerar anpassade indikatorer finns [i Hantera indikatorer.](/microsoft-365/security/defender-endpoint/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="0991d-173">For more information on how to configure custom indicators, see [Manage indicators](/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="0991d-174">Defender för Slutpunkt i iOS har stöd för att endast skapa anpassade indikatorer för IP-adresser och URL:er/domäner.</span><span class="sxs-lookup"><span data-stu-id="0991d-174">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="0991d-175">Rapportera osäker webbplats</span><span class="sxs-lookup"><span data-stu-id="0991d-175">Report unsafe site</span></span>

<span data-ttu-id="0991d-176">Nätfiskewebbplatser utger sig för att vara betrodda webbplatser i syfte att skaffa personlig eller ekonomisk information.</span><span class="sxs-lookup"><span data-stu-id="0991d-176">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="0991d-177">Gå till [sidan Ge feedback om nätverksskydd](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) om du vill rapportera en webbplats som kan vara en nätfiskewebbplats.</span><span class="sxs-lookup"><span data-stu-id="0991d-177">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

