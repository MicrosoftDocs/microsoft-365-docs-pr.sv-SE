---
title: Konfigurera funktioner i Microsoft Defender ATP för iOS
description: Här beskrivs hur du distribuerar Microsoft Defender ATP för iOS-funktioner
keywords: microsoft, defender, atp, ios, konfigurera, funktioner, ios
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 90e65c57321fa05a62bc94f4f56d92062d0826a1
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186707"
---
# <a name="configure-microsoft-defender-for-endpoint-for-ios-features"></a><span data-ttu-id="b08c8-104">Konfigurera Microsoft Defender för slutpunkt för iOS-funktioner</span><span class="sxs-lookup"><span data-stu-id="b08c8-104">Configure Microsoft Defender for Endpoint for iOS features</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b08c8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="b08c8-105">**Applies to:**</span></span>
- [<span data-ttu-id="b08c8-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="b08c8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b08c8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b08c8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b08c8-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="b08c8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b08c8-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="b08c8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

> [!NOTE]
> <span data-ttu-id="b08c8-110">Defender för Endpoint för iOS skulle använda en VPN för att tillhandahålla webskyddsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="b08c8-110">Defender for Endpoint for iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="b08c8-111">Det här är inte en vanlig VPN och är en lokal/självslingande VPN som inte tar trafik utanför enheten.</span><span class="sxs-lookup"><span data-stu-id="b08c8-111">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="conditional-access-with-defender-for-endpoint-for-ios"></a><span data-ttu-id="b08c8-112">Villkorsstyrd åtkomst med Defender för Slutpunkt för iOS</span><span class="sxs-lookup"><span data-stu-id="b08c8-112">Conditional Access with Defender for Endpoint for iOS</span></span>  
<span data-ttu-id="b08c8-113">Microsoft Defender för Slutpunkt för iOS tillsammans med Microsoft Intune och Azure Active Directory gör det möjligt att tillämpa enhetsefterlevnad och villkorsstyrd åtkomstprincip baserat på risknivåer för enheter.</span><span class="sxs-lookup"><span data-stu-id="b08c8-113">Microsoft Defender for Endpoint for iOS along with Microsoft Intune and Azure Active Directory enables enforcing Device compliance and Conditional Access policies based on device risk levels.</span></span> <span data-ttu-id="b08c8-114">Defender för Endpoint är en MTD-lösning (Mobile Threat Defense) som du kan distribuera för att utnyttja den här funktionen via Intune.</span><span class="sxs-lookup"><span data-stu-id="b08c8-114">Defender for Endpoint is a Mobile Threat Defense (MTD) solution that you can deploy to leverage this capability via Intune.</span></span>

<span data-ttu-id="b08c8-115">Mer information om hur du konfigurera villkorsstyrd åtkomst med Defender för slutpunkt för iOS finns [i Defender för Endpoint och Intune.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="b08c8-115">For more information about how to set up Conditional Access with Defender for Endpoint for iOS, see [Defender for Endpoint and Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection).</span></span>

## <a name="web-protection-and-vpn"></a><span data-ttu-id="b08c8-116">Web Protection och VPN</span><span class="sxs-lookup"><span data-stu-id="b08c8-116">Web Protection and VPN</span></span>

<span data-ttu-id="b08c8-117">Som standard innehåller och aktiverar Defender för Slutpunkt för iOS webbskyddsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="b08c8-117">By default, Defender for Endpoint for iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="b08c8-118">[Webbskydd](web-protection-overview.md) hjälper till att skydda enheter mot webbhot och skyddar användare mot nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="b08c8-118">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="b08c8-119">Defender för Endpoint för iOS använder en VPN för att tillhandahålla detta skydd.</span><span class="sxs-lookup"><span data-stu-id="b08c8-119">Defender for Endpoint for iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="b08c8-120">Observera att det här är en lokal VPN och till skillnad från traditionell VPN skickas inte nätverkstrafik utanför enheten.</span><span class="sxs-lookup"><span data-stu-id="b08c8-120">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="b08c8-121">När den är aktiverad som standard kan det finnas fall där du måste inaktivera VPN.</span><span class="sxs-lookup"><span data-stu-id="b08c8-121">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="b08c8-122">Du kanske till exempel vill köra vissa appar som inte fungerar när en VPN konfigureras.</span><span class="sxs-lookup"><span data-stu-id="b08c8-122">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="b08c8-123">I sådana fall kan du välja att inaktivera VPN från appen på enheten genom att följa stegen nedan:</span><span class="sxs-lookup"><span data-stu-id="b08c8-123">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="b08c8-124">På din iOS-enhet öppnar du **appen Inställningar,** klickar eller trycker på **Allmänt** och sedan **VPN.**</span><span class="sxs-lookup"><span data-stu-id="b08c8-124">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="b08c8-125">Klicka eller tryck på i-knappen för Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="b08c8-125">Click or tap the "i" button for Microsoft Defender ATP.</span></span>
1. <span data-ttu-id="b08c8-126">Inaktivera VPN **genom att stänga av** Anslut på begäran.</span><span class="sxs-lookup"><span data-stu-id="b08c8-126">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b08c8-127">![VPN-konfiguration ansluter på begäran](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="b08c8-127">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="b08c8-128">Web Protection är inte tillgängligt när VPN inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="b08c8-128">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="b08c8-129">Om du vill återaktivera Web Protection öppnar du appen Microsoft Defender för Endpoint på enheten och klickar eller trycker på **Starta VPN.**</span><span class="sxs-lookup"><span data-stu-id="b08c8-129">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-of-multiple-vpn-profiles"></a><span data-ttu-id="b08c8-130">Det finns flera VPN-profiler</span><span class="sxs-lookup"><span data-stu-id="b08c8-130">Co-existence of multiple VPN profiles</span></span>

<span data-ttu-id="b08c8-131">Apple iOS stöder inte flera vpn som gäller hela enheten för att vara aktiva samtidigt.</span><span class="sxs-lookup"><span data-stu-id="b08c8-131">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="b08c8-132">Även om flera VPN-profiler kan finnas på enheten kan bara ett VPN vara aktivt i taget.</span><span class="sxs-lookup"><span data-stu-id="b08c8-132">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="configure-compliance-policy-against-jailbroken-devices"></a><span data-ttu-id="b08c8-133">Konfigurera efterlevnadsprincip mot jailbroken enheter</span><span class="sxs-lookup"><span data-stu-id="b08c8-133">Configure compliance policy against jailbroken devices</span></span>

<span data-ttu-id="b08c8-134">För att skydda företagsdata från att kommas åt på jailbroken iOS-enheter rekommenderar vi att du konfigurerar följande efterlevnadsprincip på Intune.</span><span class="sxs-lookup"><span data-stu-id="b08c8-134">To protect corporate data from being accessed on jailbroken iOS devices, we recommend that you set up the following compliance policy on Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="b08c8-135">För stunden ger Inte Microsoft Defender för Endpoint för iOS skydd mot scenarier.</span><span class="sxs-lookup"><span data-stu-id="b08c8-135">At this time Microsoft Defender for Endpoint for iOS does not provide protection against jailbreak scenarios.</span></span> <span data-ttu-id="b08c8-136">Om den används på en jailbroken enhet kan data som används av programmet i vissa fall som ditt företags-e-post-ID och företagsprofilbild (om tillgängligt) visas lokalt</span><span class="sxs-lookup"><span data-stu-id="b08c8-136">If used on a jailbroken device, then in specific scenarios data that is used by the application like your corporate email id and corporate profile picture (if available) can be exposed locally</span></span>

<span data-ttu-id="b08c8-137">Följ stegen nedan för att skapa en efterlevnadsprincip mot jailbroken enheter.</span><span class="sxs-lookup"><span data-stu-id="b08c8-137">Follow the steps below to create a compliance policy against jailbroken devices.</span></span>

1. <span data-ttu-id="b08c8-138">Gå [till Principer för enhetsefterlevnad](https://go.microsoft.com/fwlink/?linkid=2109431)i **Administrationscenter för** Microsoft Endpoint  ->    ->  Manager.</span><span class="sxs-lookup"><span data-stu-id="b08c8-138">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Compliance policies** -> **Create Policy**.</span></span> <span data-ttu-id="b08c8-139">Välj "iOS/iPadOS" som plattform och klicka på **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="b08c8-139">Select "iOS/iPadOS" as platform and click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b08c8-140">![Skapa princip](images/ios-jb-policy.png)</span><span class="sxs-lookup"><span data-stu-id="b08c8-140">![Create Policy](images/ios-jb-policy.png)</span></span>

2. <span data-ttu-id="b08c8-141">Ange ett namn på principen, till exempel "Efterlevnadsprincip för Företag".</span><span class="sxs-lookup"><span data-stu-id="b08c8-141">Specify a name of the policy, for example "Compliance Policy for Jailbreak".</span></span>
3. <span data-ttu-id="b08c8-142">På sidan inställningar för efterlevnad klickar du för att expandera **avsnittet Enhetshälsa** och klickar på **Spärra för** **Jailbroken-enheter.**</span><span class="sxs-lookup"><span data-stu-id="b08c8-142">In the compliance settings page, click to expand **Device Health** section and click **Block** for **Jailbroken devices** field.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b08c8-143">![Principinställningar](images/ios-jb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="b08c8-143">![Policy Settings](images/ios-jb-settings.png)</span></span>

4. <span data-ttu-id="b08c8-144">I avsnittet *Åtgärd för icke-efterlevnad* väljer du åtgärderna enligt dina krav och väljer **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="b08c8-144">In the *Action for noncompliance* section, select the actions as per your requirements and select **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b08c8-145">![Principåtgärder](images/ios-jb-actions.png)</span><span class="sxs-lookup"><span data-stu-id="b08c8-145">![Policy Actions](images/ios-jb-actions.png)</span></span>

5. <span data-ttu-id="b08c8-146">I avsnittet *Tilldelningar* väljer du de användargrupper som du vill inkludera för den här principen och väljer sedan **Nästa.**</span><span class="sxs-lookup"><span data-stu-id="b08c8-146">In the *Assignments* section, select the user groups that you want to include for this policy and then select **Next**.</span></span>
6. <span data-ttu-id="b08c8-147">I avsnittet **Granska+Skapa** kontrollerar du att all information som angetts är korrekt och väljer sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="b08c8-147">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="configure-custom-indicators"></a><span data-ttu-id="b08c8-148">Konfigurera anpassade indikatorer</span><span class="sxs-lookup"><span data-stu-id="b08c8-148">Configure custom indicators</span></span>

<span data-ttu-id="b08c8-149">Med Defender för Endpoint för iOS kan administratörer även konfigurera anpassade indikatorer på iOS-enheter.</span><span class="sxs-lookup"><span data-stu-id="b08c8-149">Defender for Endpoint for iOS enables admins to configure custom indicators on iOS devices as well.</span></span> <span data-ttu-id="b08c8-150">Mer information om hur du konfigurerar anpassade indikatorer finns [i Hantera indikatorer.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="b08c8-150">For more information on how to configure custom indicators, see [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).</span></span>

> [!NOTE]
> <span data-ttu-id="b08c8-151">Defender för Endpoint för iOS har stöd för att endast skapa anpassade indikatorer för IP-adresser och URL:er/domäner.</span><span class="sxs-lookup"><span data-stu-id="b08c8-151">Defender for Endpoint for iOS supports creating custom indicators only for IP addresses and URLs/domains.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="b08c8-152">Rapportera osäker webbplats</span><span class="sxs-lookup"><span data-stu-id="b08c8-152">Report unsafe site</span></span>

<span data-ttu-id="b08c8-153">Nätfiskewebbplatser utger sig för att vara betrodda webbplatser i syfte att skaffa personlig eller ekonomisk information.</span><span class="sxs-lookup"><span data-stu-id="b08c8-153">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="b08c8-154">Gå till [sidan Ge feedback om nätverksskydd](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) om du vill rapportera en webbplats som kan vara en nätfiskewebbplats.</span><span class="sxs-lookup"><span data-stu-id="b08c8-154">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page if you want to report a website that could be a phishing site.</span></span>
