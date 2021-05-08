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
ms.openlocfilehash: dab72da02927c3fff6025eb2d0fa9ed0fdf1d0d7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245282"
---
# <a name="configure-microsoft-defender-for-endpoint-on-ios-features"></a><span data-ttu-id="41d1b-104">Konfigurera Microsoft Defender för slutpunkt för iOS-funktioner</span><span class="sxs-lookup"><span data-stu-id="41d1b-104">Configure Microsoft Defender for Endpoint on iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="41d1b-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="41d1b-105">**Applies to:**</span></span>
- [<span data-ttu-id="41d1b-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="41d1b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="41d1b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41d1b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="41d1b-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="41d1b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="41d1b-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="41d1b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="41d1b-110">Defender för Endpoint i iOS skulle använda ett VPN för att tillhandahålla webskyddsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="41d1b-110">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="41d1b-111">Det här är inte en vanlig VPN och är en lokal/självslingande VPN som inte tar trafik utanför enheten.</span><span class="sxs-lookup"><span data-stu-id="41d1b-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-on-ios"></a><span data-ttu-id="41d1b-112">Villkorsstyrd åtkomst med Defender för slutpunkt i iOS</span><span class="sxs-lookup"><span data-stu-id="41d1b-112">Conditional Access with Defender for Endpoint on iOS</span></span>  
<span data-ttu-id="41d1b-113">Microsoft Defender för slutpunkt på iOS tillsammans med Microsoft Intune och Azure Active Directory aktiverar tvingande enhetsefterlevnad och villkorsstyrd åtkomstprincip baserat på enhetens riskresultat.</span><span class="sxs-lookup"><span data-stu-id="41d1b-113">Microsoft Defender for Endpoint on iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk score.</span></span> <span data-ttu-id="41d1b-114">Defender för Endpoint är en MTD-lösning (Mobile Threat Defense) som du kan distribuera för att utnyttja den här funktionen via Intune.</span><span class="sxs-lookup"><span data-stu-id="41d1b-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="41d1b-115">Mer information om hur du konfigurera villkorsstyrd åtkomst med Defender för slutpunkt i iOS finns [i Defender för Endpoint och Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="41d1b-115">For more information about how to set up Conditional Access with Defender for Endpoint on iOS, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="41d1b-116">**Identifiering av identifiering av Microsoft Defender för slutpunkt i iOS är för närvarande i förhandsversion.**</span><span class="sxs-lookup"><span data-stu-id="41d1b-116">**Jailbreak detection by Microsoft Defender for Endpoint on iOS is currently in preview**.</span></span> <span data-ttu-id="41d1b-117">Om en enhet identifieras som jailbroken av Microsoft Defender för Endpoint rapporteras en avisering med hög risk till Säkerhetscenter, och om villkorlig åtkomst konfigureras baserat på enhetsriskresultat blockeras enheten från att komma åt företagets data.</span><span class="sxs-lookup"><span data-stu-id="41d1b-117">If a device is detected to be jailbroken by Microsoft Defender for Endpoint, a **High**-risk alert will be reported to Security Center and if Conditional Access is setup based on device risk score, then the device will be blocked from accessing corporate data.</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="41d1b-118">Web Protection och VPN</span><span class="sxs-lookup"><span data-stu-id="41d1b-118">Web Protection and VPN</span></span>

<span data-ttu-id="41d1b-119">Som standard inkluderar och aktiverar Defender för Slutpunkt i iOS webbskyddsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="41d1b-119">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="41d1b-120">[Webbskydd](web-protection-overview.md) hjälper till att skydda enheter mot webbhot och skyddar användare mot nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="41d1b-120">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="41d1b-121">Defender för Endpoint på iOS använder en VPN för att tillhandahålla detta skydd.</span><span class="sxs-lookup"><span data-stu-id="41d1b-121">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="41d1b-122">Observera att det här är en lokal VPN och till skillnad från traditionell VPN skickas inte nätverkstrafik utanför enheten.</span><span class="sxs-lookup"><span data-stu-id="41d1b-122">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="41d1b-123">När den är aktiverad som standard kan det finnas fall där du måste inaktivera VPN.</span><span class="sxs-lookup"><span data-stu-id="41d1b-123">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="41d1b-124">Du kanske till exempel vill köra vissa appar som inte fungerar när en VPN konfigureras.</span><span class="sxs-lookup"><span data-stu-id="41d1b-124">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="41d1b-125">I sådana fall kan du välja att inaktivera VPN från appen på enheten genom att följa stegen nedan:</span><span class="sxs-lookup"><span data-stu-id="41d1b-125">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="41d1b-126">På din iOS-enhet öppnar du **Inställningar,** klickar eller trycker på **Allmänt** och sedan **VPN.**</span><span class="sxs-lookup"><span data-stu-id="41d1b-126">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="41d1b-127">Klicka eller tryck på i-knappen för Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="41d1b-127">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="41d1b-128">Inaktivera ANSLUT **för att** inaktivera VPN.</span><span class="sxs-lookup"><span data-stu-id="41d1b-128">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="41d1b-129">![VPN-konfiguration ansluter på begäran](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="41d1b-129">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="41d1b-130">Web Protection är inte tillgängligt när VPN inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="41d1b-130">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="41d1b-131">Om du vill återaktivera Web Protection öppnar du appen Microsoft Defender för Endpoint på enheten och klickar eller trycker på **Starta VPN.**</span><span class="sxs-lookup"><span data-stu-id="41d1b-131">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="41d1b-132">Det finns flera VPN-profiler</span><span class="sxs-lookup"><span data-stu-id="41d1b-132">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="41d1b-133">Apple iOS stöder inte flera vpn som gäller hela enheten för att vara aktiva samtidigt.</span><span class="sxs-lookup"><span data-stu-id="41d1b-133">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="41d1b-134">Även om flera VPN-profiler kan finnas på enheten kan bara ett VPN vara aktivt i taget.</span><span class="sxs-lookup"><span data-stu-id="41d1b-134">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="41d1b-135">Konfigurera efterlevnadsprincip mot jailbroken enheter</span><span class="sxs-lookup"><span data-stu-id="41d1b-135">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="41d1b-136">För att skydda företagsdata från att kommas åt på jailbroken iOS-enheter rekommenderar vi att du konfigurerar följande efterlevnadsprincip på Intune.</span><span class="sxs-lookup"><span data-stu-id="41d1b-136">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="41d1b-137">Nu finns det en förhandsversion för identifiering av Microsoft Defender för Slutpunkt i iOS.</span><span class="sxs-lookup"><span data-stu-id="41d1b-137">At this time jailbreak detection by Microsoft Defender for Endpoint on iOS is in preview.</span></span> <span data-ttu-id="41d1b-138">Vi rekommenderar att du inställningar den här principen som ett ytterligare skyddslager mot scenarier.</span><span class="sxs-lookup"><span data-stu-id="41d1b-138">We recommend that you setup this policy as an additional layer of defense against jailbreak scenarios.</span></span>

<span data-ttu-id="41d1b-139">Följ stegen nedan för att skapa en efterlevnadsprincip mot jailbroken enheter.</span><span class="sxs-lookup"><span data-stu-id="41d1b-139">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="41d1b-140">I [Microsoft Endpoint Manager administrationscenter går](https://go.microsoft.com/fwlink/?linkid=2109431)du till Principer för efterlevnad av **enheter**  ->  **Skapa**  ->  **princip.**</span><span class="sxs-lookup"><span data-stu-id="41d1b-140">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="41d1b-141">Välj "iOS/iPadOS" som plattform och klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="41d1b-141">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="41d1b-142">![Skapa princip](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="41d1b-142">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="41d1b-143">Ange ett namn på principen, till exempel "Efterlevnadsprincip för Företag".</span><span class="sxs-lookup"><span data-stu-id="41d1b-143">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="41d1b-144">På sidan inställningar för efterlevnad klickar du för att expandera **avsnittet Enhetshälsa** och klickar på **Spärra för** **Jailbroken-enheter.**</span><span class="sxs-lookup"><span data-stu-id="41d1b-144">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="41d1b-145">![Princip Inställningar](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="41d1b-145">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="41d1b-146">I avsnittet *Åtgärd för icke-efterlevnad* väljer du åtgärderna enligt dina krav och väljer **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="41d1b-146">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="41d1b-147">![Principåtgärder](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="41d1b-147">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="41d1b-148">I avsnittet *Tilldelningar* väljer du de användargrupper som du vill inkludera för den här principen och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="41d1b-148">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="41d1b-149">I avsnittet **Granska+Skapa** kontrollerar du att all information som angetts är korrekt och väljer sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="41d1b-149">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="41d1b-150">Konfigurera anpassade indikatorer</span><span class="sxs-lookup"><span data-stu-id="41d1b-150">Configure custom indicators</span></span>

<span data-ttu-id="41d1b-151">Med Defender för Slutpunkt i iOS kan administratörer även konfigurera anpassade indikatorer på iOS-enheter.</span><span class="sxs-lookup"><span data-stu-id="41d1b-151">Defender for Endpoint on iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="41d1b-152">Mer information om hur du konfigurerar anpassade indikatorer finns [i Hantera indikatorer.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="41d1b-152">For more information on how to configure custom indicators, see [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="41d1b-153">Defender för Slutpunkt i iOS har stöd för att endast skapa anpassade indikatorer för IP-adresser och URL:er/domäner.</span><span class="sxs-lookup"><span data-stu-id="41d1b-153">Defender for Endpoint on iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="41d1b-154">Rapportera osäker webbplats</span><span class="sxs-lookup"><span data-stu-id="41d1b-154">Report unsafe site</span></span>

<span data-ttu-id="41d1b-155">Nätfiskewebbplatser utger sig för att vara betrodda webbplatser i syfte att skaffa personlig eller ekonomisk information.</span><span class="sxs-lookup"><span data-stu-id="41d1b-155">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="41d1b-156">Gå till [sidan Ge feedback om nätverksskydd](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) om du vill rapportera en webbplats som kan vara en nätfiskewebbplats.</span><span class="sxs-lookup"><span data-stu-id="41d1b-156">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>

## <a name="battery-consumption-issues-on-ios-when-microsoft-defender-for-endpoint-is-installed"></a><span data-ttu-id="41d1b-157">Problem med batterianvändning i iOS när Microsoft Defender för Slutpunkt är installerat</span><span class="sxs-lookup"><span data-stu-id="41d1b-157">Battery Consumption issues on iOS when Microsoft Defender for Endpoint is installed</span></span>

<span data-ttu-id="41d1b-158">Batterianvändningen från en app beräknas av Apple baserat på en mängd faktorer, bland annat PROCESSOR- och nätverksanvändning.</span><span class="sxs-lookup"><span data-stu-id="41d1b-158">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="41d1b-159">Microsoft Defender för Endpoint använder en lokal/loop-back VPN i bakgrunden för att kontrollera webbtrafiken efter skadliga webbplatser eller anslutningar.</span><span class="sxs-lookup"><span data-stu-id="41d1b-159">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="41d1b-160">Nätverkspaket från alla appar går igenom den här kontrollen och det gör att batterianvändningen av Microsoft Defender för Endpoint beräknas felaktigt.</span><span class="sxs-lookup"><span data-stu-id="41d1b-160">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="41d1b-161">Det ger användaren ett falskt intryck.</span><span class="sxs-lookup"><span data-stu-id="41d1b-161">This gives a false impression to the user.</span></span> <span data-ttu-id="41d1b-162">Den faktiska batteriförbrukningen i Microsoft Defender för Endpoint är mindre än vad som visas på Inställningar batteri på enheten.</span><span class="sxs-lookup"><span data-stu-id="41d1b-162">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="41d1b-163">Det här baseras på utförda tester som utförts i appen Microsoft Defender för Slutpunkt för att förstå batterianvändningen.</span><span class="sxs-lookup"><span data-stu-id="41d1b-163">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="41d1b-164">Dessutom är VPN som används en lokal VPN och till skillnad från traditionella VPN så skickas inte nätverkstrafik utanför enheten.</span><span class="sxs-lookup"><span data-stu-id="41d1b-164">Also the VPN used is a local VPN and unlike traditional VPNs, network traffic is not sent outside the device.</span></span>
