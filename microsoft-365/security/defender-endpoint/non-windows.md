---
title: Microsoft Defender för Endpoint för icke-Windows-plattformar
description: Läs mer om Funktionerna i Microsoft Defender för slutpunkt för plattformar som inte är Windows
keywords: icke windows, mac, macos, linux, android
search.product: eADQiWindows 10XVcnh
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
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: dc5710a73685c67eff17c0f281bd14e48707e60f
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964794"
---
# <a name="microsoft-defender-for-endpoint-for-non-windows-platforms"></a><span data-ttu-id="bd7d4-104">Microsoft Defender för Endpoint för icke-Windows-plattformar</span><span class="sxs-lookup"><span data-stu-id="bd7d4-104">Microsoft Defender for Endpoint for non-Windows platforms</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bd7d4-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="bd7d4-105">**Applies to:**</span></span>
- [<span data-ttu-id="bd7d4-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="bd7d4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bd7d4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd7d4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="bd7d4-108">Vill du uppleva Microsoft Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="bd7d4-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bd7d4-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="bd7d4-110">Microsoft har varit på en resa mot att utöka sina branschledande slutpunktssäkerhetsfunktioner utöver Windows och Windows Server till macOS, Linux, Android och snart iOS.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-110">Microsoft has been on a journey to extend its industry leading endpoint security capabilities beyond Windows and Windows Server to macOS, Linux, Android, and soon iOS.</span></span>

<span data-ttu-id="bd7d4-111">Organisationer står inför hot på olika plattformar och enheter.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-111">Organizations face threats across a variety of platforms and devices.</span></span> <span data-ttu-id="bd7d4-112">Våra team har strävar efter att skapa säkerhetslösningar inte bara för *Microsoft* utan även från *Microsoft* för att våra kunder ska kunna skydda och säkra sina heteriga miljöer.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-112">Our teams have committed to building security solutions not just *for* Microsoft, but also *from* Microsoft to enable our customers to protect and secure their heterogenous environments.</span></span> <span data-ttu-id="bd7d4-113">Vi lyssnar på kundernas feedback och samarbetar tätt med våra kunder för att ta fram lösningar som uppfyller deras behov.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-113">We're listening to customer feedback and partnering closely with our customers to build solutions that meet their needs.</span></span>

<span data-ttu-id="bd7d4-114">Med Microsoft Defender för slutpunkt drar kunder nytta av en enhetlig vy över alla hot och varningar i Microsoft Defender Säkerhetscenter på Windows- och icke-Windows-plattformarna, så att de får en fullständig bild av vad som händer i miljön, vilket gör det möjligt för dem att snabbare utvärdera och reagera på hot.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-114">With Microsoft Defender for Endpoint, customers benefit from a unified view of all threats and alerts in the Microsoft Defender Security Center, across Windows and non-Windows platforms, enabling them to get a full picture of what's happening in their environment, which empowers them to more quickly assess and respond to threats.</span></span>

## <a name="microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="bd7d4-115">Microsoft Defender för Endpoint för macOS</span><span class="sxs-lookup"><span data-stu-id="bd7d4-115">Microsoft Defender for Endpoint on macOS</span></span> 

<span data-ttu-id="bd7d4-116">Microsoft Defender för slutpunkt på macOS erbjuder funktioner för identifiering och svar av antivirus och slutpunkt (EDR) för de tre senaste släppta versionerna av macOS.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-116">Microsoft Defender for Endpoint on macOS offers antivirus and endpoint detection and response (EDR) capabilities for the three latest released versions of macOS.</span></span> <span data-ttu-id="bd7d4-117">Kunder kan distribuera och hantera lösningen via Microsoft Endpoint Manager och Jamf.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-117">Customers can deploy and manage the solution through Microsoft Endpoint Manager and Jamf.</span></span> <span data-ttu-id="bd7d4-118">Precis som för Microsoft Office-program i macOS används Microsoft Auto Update för att hantera Microsoft Defender för slutpunkt på Mac-uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-118">Just like with Microsoft Office applications on macOS, Microsoft Auto Update is used to manage Microsoft Defender for Endpoint on Mac updates.</span></span> <span data-ttu-id="bd7d4-119">Mer information om viktiga funktioner och fördelar finns i [våra meddelanden.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS)</span><span class="sxs-lookup"><span data-stu-id="bd7d4-119">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS).</span></span>

<span data-ttu-id="bd7d4-120">Mer information om hur du kommer igång finns i dokumentationen för Defender för slutpunkt på [macOS.](microsoft-defender-endpoint-mac.md)</span><span class="sxs-lookup"><span data-stu-id="bd7d4-120">For more details on how to get started, visit the Defender for Endpoint on macOS [documentation](microsoft-defender-endpoint-mac.md).</span></span>

>[!NOTE]
><span data-ttu-id="bd7d4-121">Följande funktioner stöds för närvarande inte på macOS-slutpunkter:</span><span class="sxs-lookup"><span data-stu-id="bd7d4-121">The following capabilities are not currently supported on macOS endpoints:</span></span>
>- <span data-ttu-id="bd7d4-122">Skydd mot dataförlust</span><span class="sxs-lookup"><span data-stu-id="bd7d4-122">Data loss prevention</span></span>
>- <span data-ttu-id="bd7d4-123">Livesvar</span><span class="sxs-lookup"><span data-stu-id="bd7d4-123">Live response</span></span>
>- <span data-ttu-id="bd7d4-124">SIEM</span><span class="sxs-lookup"><span data-stu-id="bd7d4-124">SIEM</span></span>


## <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="bd7d4-125">Microsoft Defender för Endpoint för Linux</span><span class="sxs-lookup"><span data-stu-id="bd7d4-125">Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="bd7d4-126">Microsoft Defender för Slutpunkt på Linux erbjuder preventativa funktioner (AV) för Linux-servrar.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-126">Microsoft Defender for Endpoint on Linux offers preventative (AV) capabilities for Linux servers.</span></span> <span data-ttu-id="bd7d4-127">Detta inkluderar en fullständig kommandoradsupplevelse för att konfigurera och hantera agenten, initiera genomsökningar och hantera hot.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-127">This includes a full command line experience to configure and manage the agent, initiate scans, and manage threats.</span></span> <span data-ttu-id="bd7d4-128">Vi stöder de senaste versionerna av de sex vanligaste Linux Server-distributionerna: RHEL 7.2+, CentOS Linux 7.2+, Ubuntu 16 LTS eller senare LTS, SLES 12+, Liter 9+och Oracle Linux 7.2.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-128">We support recent versions of the six most common Linux Server distributions: RHEL 7.2+, CentOS Linux 7.2+, Ubuntu 16 LTS, or higher LTS, SLES 12+, Debian 9+, and Oracle Linux 7.2.</span></span> <span data-ttu-id="bd7d4-129">Microsoft Defender för slutpunkt på Linux kan distribueras och konfigureras med hjälp av Klient, Ansible eller ditt befintliga konfigurationsverktyg för Linux.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-129">Microsoft Defender for Endpoint on Linux can be deployed and configured using Puppet, Ansible, or using your existing Linux configuration management tool.</span></span> <span data-ttu-id="bd7d4-130">Mer information om viktiga funktioner och fördelar finns i [våra meddelanden.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux)</span><span class="sxs-lookup"><span data-stu-id="bd7d4-130">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux).</span></span>

<span data-ttu-id="bd7d4-131">Mer information om hur du kommer igång finns i dokumentationen för Microsoft Defender för Endpoint [på](microsoft-defender-endpoint-linux.md)Linux.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-131">For more details on how to get started, visit the Microsoft Defender for Endpoint on Linux [documentation](microsoft-defender-endpoint-linux.md).</span></span>

>[!NOTE]
><span data-ttu-id="bd7d4-132">Följande funktioner stöds för närvarande inte på Linux-slutpunkter:</span><span class="sxs-lookup"><span data-stu-id="bd7d4-132">The following capabilities are not currently supported on Linux endpoints:</span></span>
>- <span data-ttu-id="bd7d4-133">Skydd mot dataförlust</span><span class="sxs-lookup"><span data-stu-id="bd7d4-133">Data loss prevention</span></span>
>- <span data-ttu-id="bd7d4-134">Livesvar</span><span class="sxs-lookup"><span data-stu-id="bd7d4-134">Live response</span></span>
>- <span data-ttu-id="bd7d4-135">SIEM</span><span class="sxs-lookup"><span data-stu-id="bd7d4-135">SIEM</span></span>



## <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="bd7d4-136">Microsoft Defender för Endpoint för Android</span><span class="sxs-lookup"><span data-stu-id="bd7d4-136">Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="bd7d4-137">Microsoft Defender för slutpunkt på Android är vår lösning för skydd mot mobila hot för enheter med Android 6.0 och senare.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-137">Microsoft Defender for Endpoint on Android is our mobile threat defense solution for devices running Android 6.0 and higher.</span></span> <span data-ttu-id="bd7d4-138">Både lägena Android Enterprise (arbetsprofil) och Enhetsadministratör stöds.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-138">Both Android Enterprise (Work Profile) and Device Administrator modes are supported.</span></span> <span data-ttu-id="bd7d4-139">I Android erbjuder vi webbskydd, som omfattar skydd mot nätfiske, blockering av osäkra anslutningar och inställning av anpassade indikatorer.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-139">On Android, we offer web protection, which includes anti-phishing, blocking of unsafe connections, and setting of custom indicators.</span></span> <span data-ttu-id="bd7d4-140">Lösningen söker efter skadlig kod och potentiellt oönskade program (PUA) och erbjuder ytterligare skyddsfunktioner mot intrång genom integrering med Microsoft Endpoint Manager och Villkorsstyrd åtkomst.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-140">The solution scans for malware and potentially unwanted applications (PUA) and offers additional breach prevention capabilities through integration with Microsoft Endpoint Manager and Conditional Access.</span></span> <span data-ttu-id="bd7d4-141">Mer information om viktiga funktioner och fördelar finns i [våra meddelanden.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android)</span><span class="sxs-lookup"><span data-stu-id="bd7d4-141">For information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android).</span></span>

<span data-ttu-id="bd7d4-142">Mer information om hur du kommer igång finns i dokumentationen för Microsoft Defender för slutpunkt [på](microsoft-defender-endpoint-android.md)Android.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-142">For more details on how to get started, visit the Microsoft Defender for Endpoint on Android [documentation](microsoft-defender-endpoint-android.md).</span></span>

## <a name="microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="bd7d4-143">Microsoft Defender för Endpoint för iOS</span><span class="sxs-lookup"><span data-stu-id="bd7d4-143">Microsoft Defender for Endpoint on iOS</span></span>

<span data-ttu-id="bd7d4-144">Microsoft Defender för Endpoint på iOS är vår lösning för mobilt skydd mot hot för enheter med iOS 11.0 och senare.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-144">Microsoft Defender for Endpoint on iOS is our mobile threat defense solution for devices running iOS 11.0 and higher.</span></span> <span data-ttu-id="bd7d4-145">Både övervakade och ej övervakade enheter stöds.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-145">Both Supervised and Unsupervised devices are supported.</span></span> <span data-ttu-id="bd7d4-146">I iOS erbjuder vi webbskydd som omfattar skydd mot nätfiske, blockering av osäkra anslutningar och inställning av anpassade indikatorer.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-146">On iOS, we offer web protection which includes anti-phishing, blocking unsafe connections, and setting custom indicators.</span></span> <span data-ttu-id="bd7d4-147">Mer information om viktiga funktioner och fördelar finns i [våra meddelanden.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)</span><span class="sxs-lookup"><span data-stu-id="bd7d4-147">For more information about the key features and benefits, read our [announcements](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS).</span></span> 

<span data-ttu-id="bd7d4-148">Mer information om hur du kommer igång finns i dokumentationen för Microsoft Defender för Slutpunkt på [iOS.](microsoft-defender-endpoint-ios.md)</span><span class="sxs-lookup"><span data-stu-id="bd7d4-148">For more details on how to get started, visit the Microsoft Defender for Endpoint on iOS [documentation](microsoft-defender-endpoint-ios.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="bd7d4-149">Licensieringskrav</span><span class="sxs-lookup"><span data-stu-id="bd7d4-149">Licensing requirements</span></span> 

<span data-ttu-id="bd7d4-150">Kvalificerade licensierade användare kan använda Microsoft Defender för Slutpunkt på upp till fem samtidiga enheter.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-150">Eligible Licensed Users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span> <span data-ttu-id="bd7d4-151">Microsoft Defender för Endpoint kan också köpas från en leverantör av molnlösningar (CSP).</span><span class="sxs-lookup"><span data-stu-id="bd7d4-151">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>

<span data-ttu-id="bd7d4-152">Kunder kan erhålla Microsoft Defender för Slutpunkt i macOS genom en fristående Microsoft Defender för slutpunktslicens som en del av Microsoft 365 A5/E5 eller Microsoft 365-säkerhet.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-152">Customers can obtain Microsoft Defender for Endpoint on macOS through a standalone Microsoft Defender for Endpoint license, as part of Microsoft 365 A5/E5, or Microsoft 365 Security.</span></span>

<span data-ttu-id="bd7d4-153">Nyligen meddelade vi funktionerna i Microsoft Defender för Endpoint på Android och iOS ingår i ovanstående erbjudanden som en del av de fem kvalificerade enheterna för berättigade licensierade användare.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-153">Recently announced capabilities of Microsoft Defender for Endpoint on Android and iOS are included in the above mentioned offers as part of the five qualified devices for eligible licensed users.</span></span>

<span data-ttu-id="bd7d4-154">Defender för slutpunkt på Linux är tillgänglig via Defender för Endpoint Server SKU som är tillgänglig för både kommersiella kunder och utbildningskunder.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-154">Defender for Endpoint on Linux is available through the Defender for Endpoint Server SKU that is available for both commercial and education customers.</span></span>

<span data-ttu-id="bd7d4-155">Kontakta ditt kontoteam eller din microsoft-konto-microsoft-sp för prisuppgifter och ytterligare kvalificeringskrav.</span><span class="sxs-lookup"><span data-stu-id="bd7d4-155">Please contact your account team or CSP for pricing and additional eligibility requirements.</span></span>
