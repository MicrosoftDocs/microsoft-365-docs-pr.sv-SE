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
ms.openlocfilehash: 13c0a575fd2614f58eb6a2163cda04118c2a391d
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636284"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="f96d0-104">Felsöka problem och hitta svar på vanliga frågor och svar i Microsoft Defender för Endpoint i iOS</span><span class="sxs-lookup"><span data-stu-id="f96d0-104">Troubleshoot issues and find answers to FAQs on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f96d0-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="f96d0-105">**Applies to:**</span></span>
- [<span data-ttu-id="f96d0-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="f96d0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f96d0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f96d0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f96d0-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="f96d0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f96d0-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="f96d0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="f96d0-110">Det här avsnittet innehåller felsökningsinformation som hjälper dig att lösa problem som kan uppstå när du använder Microsoft Defender för Endpoint i iOS.</span><span class="sxs-lookup"><span data-stu-id="f96d0-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="f96d0-111">Defender för Endpoint i iOS skulle använda ett VPN för att tillhandahålla webskyddsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="f96d0-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="f96d0-112">Det här är inte en vanlig VPN och är en lokal/självslingande VPN som inte tar trafik utanför enheten.</span><span class="sxs-lookup"><span data-stu-id="f96d0-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="f96d0-113">Appar fungerar inte när VPN är aktiverat</span><span class="sxs-lookup"><span data-stu-id="f96d0-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="f96d0-114">Det finns vissa appar som slutar fungera när ett aktivt VPN upptäcks.</span><span class="sxs-lookup"><span data-stu-id="f96d0-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="f96d0-115">Du kan inaktivera VPN under tiden du använder sådana appar.</span><span class="sxs-lookup"><span data-stu-id="f96d0-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="f96d0-116">Som standard inkluderar och aktiverar Defender för Slutpunkt i iOS webbskyddsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="f96d0-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="f96d0-117">[Webbskydd](web-protection-overview.md) hjälper till att skydda enheter mot webbhot och skyddar användare mot nätfiskeattacker.</span><span class="sxs-lookup"><span data-stu-id="f96d0-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="f96d0-118">Defender för Endpoint på iOS använder en VPN för att tillhandahålla detta skydd.</span><span class="sxs-lookup"><span data-stu-id="f96d0-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="f96d0-119">Observera att det här är en lokal VPN och till skillnad från traditionell VPN skickas inte nätverkstrafik utanför enheten.</span><span class="sxs-lookup"><span data-stu-id="f96d0-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="f96d0-120">När den är aktiverad som standard kan det finnas fall där du måste inaktivera VPN.</span><span class="sxs-lookup"><span data-stu-id="f96d0-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="f96d0-121">Du kanske till exempel vill köra vissa appar som inte fungerar när en VPN konfigureras.</span><span class="sxs-lookup"><span data-stu-id="f96d0-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="f96d0-122">I sådana fall kan du välja att inaktivera VPN från appen på enheten genom att följa stegen nedan:</span><span class="sxs-lookup"><span data-stu-id="f96d0-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="f96d0-123">På din iOS-enhet öppnar du **Inställningar,** klickar eller trycker på **Allmänt** och sedan **VPN.**</span><span class="sxs-lookup"><span data-stu-id="f96d0-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="f96d0-124">Klicka eller tryck på i-knappen för Microsoft Defender för Slutpunkt.</span><span class="sxs-lookup"><span data-stu-id="f96d0-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="f96d0-125">Inaktivera ANSLUT **för att** inaktivera VPN.</span><span class="sxs-lookup"><span data-stu-id="f96d0-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f96d0-126">![VPN-konfiguration ansluter på begäran](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="f96d0-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="f96d0-127">Web Protection är inte tillgängligt när VPN inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="f96d0-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="f96d0-128">Om du vill återaktivera Web Protection öppnar du appen Microsoft Defender för Endpoint på enheten och klickar eller trycker på **Starta VPN.**</span><span class="sxs-lookup"><span data-stu-id="f96d0-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="issues-with-multiple-vpn-profiles"></a><span data-ttu-id="f96d0-129">Problem med flera VPN-profiler</span><span class="sxs-lookup"><span data-stu-id="f96d0-129">Issues with multiple VPN profiles</span></span>

<span data-ttu-id="f96d0-130">Apple iOS stöder inte flera vpn som gäller hela enheten för att vara aktiva samtidigt.</span><span class="sxs-lookup"><span data-stu-id="f96d0-130">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="f96d0-131">Även om flera VPN-profiler kan finnas på enheten kan bara ett VPN vara aktivt i taget.</span><span class="sxs-lookup"><span data-stu-id="f96d0-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="battery-consumption"></a><span data-ttu-id="f96d0-132">Batteriförbrukning</span><span class="sxs-lookup"><span data-stu-id="f96d0-132">Battery consumption</span></span>

<span data-ttu-id="f96d0-133">Batterianvändningen från en app beräknas av Apple baserat på en mängd faktorer, bland annat PROCESSOR- och nätverksanvändning.</span><span class="sxs-lookup"><span data-stu-id="f96d0-133">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="f96d0-134">Microsoft Defender för Endpoint använder en lokal/loop-back VPN i bakgrunden för att kontrollera webbtrafiken efter skadliga webbplatser eller anslutningar.</span><span class="sxs-lookup"><span data-stu-id="f96d0-134">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="f96d0-135">Nätverkspaket från alla appar går igenom den här kontrollen och det gör att batterianvändningen av Microsoft Defender för Endpoint beräknas felaktigt.</span><span class="sxs-lookup"><span data-stu-id="f96d0-135">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="f96d0-136">Det ger användaren ett falskt intryck.</span><span class="sxs-lookup"><span data-stu-id="f96d0-136">This gives a false impression to the user.</span></span> <span data-ttu-id="f96d0-137">Den faktiska batteriförbrukningen i Microsoft Defender för Endpoint är mindre än vad som visas på Inställningar batteri på enheten.</span><span class="sxs-lookup"><span data-stu-id="f96d0-137">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="f96d0-138">Det här baseras på utförda tester som utförts i appen Microsoft Defender för Slutpunkt för att förstå batterianvändningen.</span><span class="sxs-lookup"><span data-stu-id="f96d0-138">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="f96d0-139">Dessutom är VPN som används en lokal VPN och till skillnad från en traditionell VPN skickas inte nätverkstrafik utanför enheten.</span><span class="sxs-lookup"><span data-stu-id="f96d0-139">Also the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="f96d0-140">Dataanvändning</span><span class="sxs-lookup"><span data-stu-id="f96d0-140">Data usage</span></span>

<span data-ttu-id="f96d0-141">Microsoft Defender för Endpoint använder ett vpn som ger lokal/loopback för att kontrollera webbtrafik efter skadliga webbplatser eller anslutningar.</span><span class="sxs-lookup"><span data-stu-id="f96d0-141">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="f96d0-142">På grund av den här orsaken konton Apple dataanvändning till Microsoft Defender för slutpunkt felaktigt.</span><span class="sxs-lookup"><span data-stu-id="f96d0-142">Due to this reason Apple accounts data usage to Microsoft Defender for Endpoint inaccurately.</span></span> <span data-ttu-id="f96d0-143">Den faktiska dataanvändningen av Microsoft Defender för Endpoint är inte signifikant och mycket mindre än vad som visas på Inställningar på enheten.</span><span class="sxs-lookup"><span data-stu-id="f96d0-143">The actual data usage by Microsoft Defender for Endpoint is not significant and much less than what is shown on the Data Usage Settings on the device.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="f96d0-144">Rapportera osäker webbplats</span><span class="sxs-lookup"><span data-stu-id="f96d0-144">Report unsafe site</span></span>

<span data-ttu-id="f96d0-145">Nätfiskewebbplatser utger sig för att vara betrodda webbplatser i syfte att skaffa personlig eller ekonomisk information.</span><span class="sxs-lookup"><span data-stu-id="f96d0-145">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="f96d0-146">Gå till [sidan Ge feedback om nätverksskydd](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) om du vill rapportera en webbplats som kan vara en nätfiskewebbplats.</span><span class="sxs-lookup"><span data-stu-id="f96d0-146">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="f96d0-147">Skadlig webbplats har upptäckts</span><span class="sxs-lookup"><span data-stu-id="f96d0-147">Malicious site detected</span></span>

<span data-ttu-id="f96d0-148">Microsoft Defender för slutpunkt skyddar dig mot nätfiske eller andra webbaserade attacker.</span><span class="sxs-lookup"><span data-stu-id="f96d0-148">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="f96d0-149">Om en skadlig webbplats upptäcks blockeras anslutningen och en avisering skickas till organisationens säkerhetscenterportal.</span><span class="sxs-lookup"><span data-stu-id="f96d0-149">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="f96d0-150">Aviseringen omfattar domännamnet för anslutningen, fjärr-IP-adressen och enhetsinformationen.</span><span class="sxs-lookup"><span data-stu-id="f96d0-150">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="f96d0-151">Dessutom visas ett meddelande på iOS-enheten.</span><span class="sxs-lookup"><span data-stu-id="f96d0-151">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="f96d0-152">När användaren trycker på meddelandet öppnas följande skärm för att granska informationen.</span><span class="sxs-lookup"><span data-stu-id="f96d0-152">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f96d0-153">![Bild på webbplatsen som rapporterats som osäker](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="f96d0-153">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="f96d0-154">Data och sekretess</span><span class="sxs-lookup"><span data-stu-id="f96d0-154">Data and Privacy</span></span>

<span data-ttu-id="f96d0-155">Mer information om data som samlas in och sekretess finns i [Sekretessinformation – Microsoft Defender för Endpoint på iOS.](ios-privacy.md)</span><span class="sxs-lookup"><span data-stu-id="f96d0-155">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

