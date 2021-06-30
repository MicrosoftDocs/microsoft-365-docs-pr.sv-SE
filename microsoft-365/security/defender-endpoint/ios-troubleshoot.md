---
title: Felsöka problem och hitta svar på vanliga frågor och svar som rör Microsoft Defender för Slutpunkt i iOS
description: Felsökning och vanliga frågor och svar – Microsoft Defender för slutpunkt i iOS
keywords: microsoft, defender, Microsoft Defender för Slutpunkt, ios, felsökning, vanliga frågor och svar, så gör du, så här gör du
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
ms.openlocfilehash: b82b6993ce9ed5a3f0f3e6e13e8a260a185c9730
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194979"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="0aea8-104">Felsöka problem och hitta svar på vanliga frågor och svar i Microsoft Defender för Endpoint i iOS</span><span class="sxs-lookup"><span data-stu-id="0aea8-104">Troubleshoot issues and find answers to FAQs on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0aea8-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="0aea8-105">**Applies to:**</span></span>
- [<span data-ttu-id="0aea8-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="0aea8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0aea8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0aea8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0aea8-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="0aea8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0aea8-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="0aea8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="0aea8-110">Det här avsnittet innehåller felsökningsinformation som hjälper dig att lösa problem som kan uppstå när du använder Microsoft Defender för Endpoint i iOS.</span><span class="sxs-lookup"><span data-stu-id="0aea8-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="0aea8-111">Defender för Endpoint i iOS skulle använda ett VPN för att tillhandahålla webskyddsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="0aea8-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="0aea8-112">Det här är inte en vanlig VPN och är en lokal/självslingande VPN som inte tar trafik utanför enheten.</span><span class="sxs-lookup"><span data-stu-id="0aea8-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="0aea8-113">Appar fungerar inte när VPN är aktiverat</span><span class="sxs-lookup"><span data-stu-id="0aea8-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="0aea8-114">Det finns vissa appar som slutar fungera när ett aktivt VPN upptäcks.</span><span class="sxs-lookup"><span data-stu-id="0aea8-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="0aea8-115">Du kan inaktivera VPN under tiden du använder sådana appar.</span><span class="sxs-lookup"><span data-stu-id="0aea8-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="0aea8-116">Som standard inkluderar och aktiverar Defender för Slutpunkt i iOS webbskyddsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="0aea8-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="0aea8-117">[Webbskydd](web-protection-overview.md) hjälper till att skydda enheter mot webbhot och skyddar användare mot nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="0aea8-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="0aea8-118">Defender för Endpoint på iOS använder en VPN för att tillhandahålla detta skydd.</span><span class="sxs-lookup"><span data-stu-id="0aea8-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="0aea8-119">Observera att det här är en lokal VPN och till skillnad från traditionell VPN skickas inte nätverkstrafik utanför enheten.</span><span class="sxs-lookup"><span data-stu-id="0aea8-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="0aea8-120">När den är aktiverad som standard kan det finnas fall där du måste inaktivera VPN.</span><span class="sxs-lookup"><span data-stu-id="0aea8-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="0aea8-121">Du kanske till exempel vill köra vissa appar som inte fungerar när en VPN konfigureras.</span><span class="sxs-lookup"><span data-stu-id="0aea8-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="0aea8-122">I sådana fall kan du välja att inaktivera VPN från appen på enheten genom att följa stegen nedan:</span><span class="sxs-lookup"><span data-stu-id="0aea8-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="0aea8-123">På din iOS-enhet öppnar du **Inställningar,** klickar eller trycker på **Allmänt** och sedan **VPN.**</span><span class="sxs-lookup"><span data-stu-id="0aea8-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="0aea8-124">Klicka eller tryck på i-knappen för Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="0aea8-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="0aea8-125">Inaktivera ANSLUT **för att** inaktivera VPN.</span><span class="sxs-lookup"><span data-stu-id="0aea8-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="0aea8-126">![VPN-konfiguration ansluter på begäran](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="0aea8-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="0aea8-127">Web Protection är inte tillgängligt när VPN inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="0aea8-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="0aea8-128">Om du vill återaktivera Web Protection öppnar du appen Microsoft Defender för Endpoint på enheten och klickar eller trycker på **Starta VPN.**</span><span class="sxs-lookup"><span data-stu-id="0aea8-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="co-existence-with-multiple-vpn-profiles"></a><span data-ttu-id="0aea8-129">Same-existence with multiple VPN profiles</span><span class="sxs-lookup"><span data-stu-id="0aea8-129">Co-existence with multiple VPN profiles</span></span>

<span data-ttu-id="0aea8-130">Apple iOS stöder inte flera **vpn som gäller hela enheten** för att vara aktiva samtidigt.</span><span class="sxs-lookup"><span data-stu-id="0aea8-130">Apple iOS does not support multiple **device-wide** VPNs to be active simultaneously.</span></span> <span data-ttu-id="0aea8-131">Även om flera VPN-profiler kan finnas på enheten kan bara ett VPN vara aktivt i taget.</span><span class="sxs-lookup"><span data-stu-id="0aea8-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>

<span data-ttu-id="0aea8-132">Microsoft Defender för endpoint VPN kan finnas tillsammans med andra VPN som är konfigurerade *som per app* eller *"Personligt".*</span><span class="sxs-lookup"><span data-stu-id="0aea8-132">Microsoft Defender for Endpoint VPN can co-exist with other VPNs that are configured as *per-app* or *"Personal"*.</span></span>

## <a name="battery-consumption"></a><span data-ttu-id="0aea8-133">Batteriförbrukning</span><span class="sxs-lookup"><span data-stu-id="0aea8-133">Battery consumption</span></span>

<span data-ttu-id="0aea8-134">I Inställningar visar iOS endast batterianvändningen av appar som är synliga för användaren under en viss tid.</span><span class="sxs-lookup"><span data-stu-id="0aea8-134">In the Settings app, iOS only shows battery usage of apps that are visible to the user for a specific duration of time.</span></span> <span data-ttu-id="0aea8-135">Batterianvändningen från appar som visas på skärmen gäller bara under den tiden och beräknas av iOS baserat på en mängd faktorer, till exempel CPU och nätverksanvändning.</span><span class="sxs-lookup"><span data-stu-id="0aea8-135">The battery usage by apps shown on the screen are only for that time duration and is computed by iOS based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="0aea8-136">Microsoft Defender för Endpoint använder en lokal/loop-back VPN i bakgrunden för att kontrollera webbtrafiken efter skadliga webbplatser eller anslutningar.</span><span class="sxs-lookup"><span data-stu-id="0aea8-136">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="0aea8-137">Nätverkspaket från alla appar går igenom den här kontrollen och det gör att batterianvändningen av Microsoft Defender för Endpoint beräknas felaktigt.</span><span class="sxs-lookup"><span data-stu-id="0aea8-137">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="0aea8-138">Den faktiska batteriförbrukningen i Microsoft Defender för Endpoint är mycket mindre än vad som visas på sidan Inställningar batteri på enheten.</span><span class="sxs-lookup"><span data-stu-id="0aea8-138">The actual battery consumption of Microsoft Defender for Endpoint is much less than what is shown on the Battery Settings page on the device.</span></span>

<span data-ttu-id="0aea8-139">Batterianvändning per dag av Microsoft Defender för Slutpunkt som körs i bakgrunden är cirka **8,81**% av det totala batteriet som använts den dagen.</span><span class="sxs-lookup"><span data-stu-id="0aea8-139">On an average, per-day battery usage by Microsoft Defender for Endpoint running on the background is **approximately 8.81% of overall battery consumed in that day**.</span></span> <span data-ttu-id="0aea8-140">Det här måttet rapporteras av Apple baserat på faktisk användning av Microsoft Defender för Endpoint på slutanvändareenheter och på grund av orsaker som nämns ovan kan även redovisas för andra appar som har nätverksaktivitet.</span><span class="sxs-lookup"><span data-stu-id="0aea8-140">This metric is reported by Apple based on actual usage of Microsoft Defender for Endpoint on end-user devices and due to reasons mentioned above can also be accounted to other apps that have network activity.</span></span>

<span data-ttu-id="0aea8-141">Vpn som används är också en lokal VPN och till skillnad från en traditionell VPN skickas inte nätverkstrafik utanför enheten.</span><span class="sxs-lookup"><span data-stu-id="0aea8-141">Also, the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="0aea8-142">Dataanvändning</span><span class="sxs-lookup"><span data-stu-id="0aea8-142">Data usage</span></span>

<span data-ttu-id="0aea8-143">Microsoft Defender för Endpoint använder ett vpn som ger lokal/loopback för att kontrollera webbtrafik efter skadliga webbplatser eller anslutningar.</span><span class="sxs-lookup"><span data-stu-id="0aea8-143">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="0aea8-144">På grund av den här orsaken kan Microsoft Defender för Slutpunktsdataanvändning redovisas felaktigt.</span><span class="sxs-lookup"><span data-stu-id="0aea8-144">Due to this reason, Microsoft Defender for Endpoint data usage can be inaccurately accounted for.</span></span> <span data-ttu-id="0aea8-145">Vi har också observerat att om enheten endast finns på mobilnät så ligger den dataanvändning som rapporterats av tjänsteleverantören mycket nära den faktiska förbrukning, medan i Inställningar-appen visar Apple cirka 1,5x till 2x av de verkliga data som används.</span><span class="sxs-lookup"><span data-stu-id="0aea8-145">We have also observed that if the device is on cellular network only, the data usage reported by service provider is very close to the actual consumption whereas in the Settings app, Apple shows about 1.5x to 2x of actual data consumed.</span></span>

<span data-ttu-id="0aea8-146">Vi har liknande observationer med andra VPN-tjänster och har rapporterat detta till Apple.</span><span class="sxs-lookup"><span data-stu-id="0aea8-146">We have similar observations with other VPN services as well and have reported this to Apple.</span></span>

<span data-ttu-id="0aea8-147">Det är dessutom viktigt att Microsoft Defender för Endpoint är uppdaterad med våra backend-tjänster för att ge bättre skydd.</span><span class="sxs-lookup"><span data-stu-id="0aea8-147">In addition, it is critical for Microsoft Defender for Endpoint to be up to date with our backend services to provide better protection.</span></span> <span data-ttu-id="0aea8-148">Vi arbetar dock med att optimera dataanvändningen av Microsoft Defender för Endpoint.</span><span class="sxs-lookup"><span data-stu-id="0aea8-148">However, we are working on optimizing the data usage by Microsoft Defender for Endpoint.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="0aea8-149">Rapportera osäker webbplats</span><span class="sxs-lookup"><span data-stu-id="0aea8-149">Report unsafe site</span></span>

<span data-ttu-id="0aea8-150">Nätfiskewebbplatser utger sig för att vara betrodda webbplatser i syfte att skaffa personlig eller ekonomisk information.</span><span class="sxs-lookup"><span data-stu-id="0aea8-150">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="0aea8-151">Gå till [sidan Ge feedback om nätverksskydd](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) om du vill rapportera en webbplats som kan vara en nätfiskewebbplats.</span><span class="sxs-lookup"><span data-stu-id="0aea8-151">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="0aea8-152">Skadlig webbplats har upptäckts</span><span class="sxs-lookup"><span data-stu-id="0aea8-152">Malicious site detected</span></span>

<span data-ttu-id="0aea8-153">Microsoft Defender för slutpunkt skyddar dig mot nätfiske eller andra webbaserade attacker.</span><span class="sxs-lookup"><span data-stu-id="0aea8-153">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="0aea8-154">Om en skadlig webbplats upptäcks blockeras anslutningen och en avisering skickas till organisationens säkerhetscenterportal.</span><span class="sxs-lookup"><span data-stu-id="0aea8-154">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="0aea8-155">Aviseringen omfattar domännamnet för anslutningen, fjärr-IP-adressen och enhetsinformationen.</span><span class="sxs-lookup"><span data-stu-id="0aea8-155">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="0aea8-156">Dessutom visas ett meddelande på iOS-enheten.</span><span class="sxs-lookup"><span data-stu-id="0aea8-156">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="0aea8-157">När användaren trycker på meddelandet öppnas följande skärm för att granska informationen.</span><span class="sxs-lookup"><span data-stu-id="0aea8-157">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0aea8-158">![Bild på webbplatsen som rapporterats som osäker](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="0aea8-158">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="0aea8-159">Data och sekretess</span><span class="sxs-lookup"><span data-stu-id="0aea8-159">Data and Privacy</span></span>

<span data-ttu-id="0aea8-160">Mer information om data som samlas in och sekretess finns i [Sekretessinformation – Microsoft Defender för Endpoint på iOS.](ios-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="0aea8-160">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

