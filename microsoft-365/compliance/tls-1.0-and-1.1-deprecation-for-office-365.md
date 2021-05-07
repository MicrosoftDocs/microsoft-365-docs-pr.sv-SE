---
title: Inaktivera TLS 1.0 och 1.1 för Microsoft 365
description: Beskriver utfasningen av TLS 1.0 och 1.1 för Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 3d44e178d351942b4a178ddc1954ddd839665639
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162031"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a><span data-ttu-id="da2e7-103">Inaktivera TLS 1.0 och 1.1 för Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="da2e7-103">Disabling TLS 1.0 and 1.1 for Microsoft 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="da2e7-104">Vi har tillfälligt stoppat inaktiveringen av TLS 1.0 och 1.1 för kommersiella kunder på grund av COVID-19.</span><span class="sxs-lookup"><span data-stu-id="da2e7-104">We temporarily halted disablement of TLS 1.0 and 1.1 for commercial customers due to COVID-19.</span></span> <span data-ttu-id="da2e7-105">När leveranskedjor har justerats och vissa länder öppnats igen startade vi om distributionen av TLS 1.2 den 15 oktober 2020.</span><span class="sxs-lookup"><span data-stu-id="da2e7-105">As supply chains have adjusted and certain countries open back up, we restarted the TLS 1.2 enforcement rollout on October 15, 2020.</span></span> <span data-ttu-id="da2e7-106">Utrullningen fortsätter under de kommande veckorna och månaderna.</span><span class="sxs-lookup"><span data-stu-id="da2e7-106">Rollout will continue over the following weeks and months.</span></span>

<span data-ttu-id="da2e7-107">Efter den 31 oktober 2018 är TLS (Transport Layer Security) 1.0- och 1.1-protokoll inaktuella för Microsoft 365 tjänsten.</span><span class="sxs-lookup"><span data-stu-id="da2e7-107">As of October 31, 2018, the Transport Layer Security (TLS) 1.0 and 1.1 protocols are deprecated for the Microsoft 365 service.</span></span> <span data-ttu-id="da2e7-108">Effekten för slutanvändarna är minimal.</span><span class="sxs-lookup"><span data-stu-id="da2e7-108">The effect for end-users is minimal.</span></span> <span data-ttu-id="da2e7-109">Den här ändringen har gjorts i över två år med det första offentliga meddelandet i december 2017.</span><span class="sxs-lookup"><span data-stu-id="da2e7-109">This change has been publicized for over two years, with the first public announcement made in December 2017.</span></span> <span data-ttu-id="da2e7-110">Den här artikeln är endast avsedd för den lokala Office 365-klienten i relation till Office 365-tjänsten, men kan även gälla för lokala TLS-problem med Office och Office Online Server/Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="da2e7-110">This article is only intended to cover the Office 365 local client in relation to the Office 365 service but can also apply to on-premises TLS issues with Office and Office Online Server/Office Web Apps.</span></span>

<span data-ttu-id="da2e7-111">För SharePoint och OneDrive måste du uppdatera och konfigurera .NET med stöd för TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="da2e7-111">For SharePoint and OneDrive, you'll need to update and configure .NET to support TLS 1.2.</span></span> <span data-ttu-id="da2e7-112">Mer information finns i [Aktivera TLS 1.2 på klienter.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="da2e7-112">For information, see [How to enable TLS 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="office-365-and-tls-overview"></a><span data-ttu-id="da2e7-113">Office 365 och TLS – översikt</span><span class="sxs-lookup"><span data-stu-id="da2e7-113">Office 365 and TLS overview</span></span>

<span data-ttu-id="da2e7-114">Den Office är beroende av win-Windows (Windows) för att skicka och ta emot trafik via TLS-protokoll.</span><span class="sxs-lookup"><span data-stu-id="da2e7-114">The Office client relies on the Windows web service (WINHTTP) to send and receive traffic over TLS protocols.</span></span> <span data-ttu-id="da2e7-115">Klient Office använda TLS 1.2 om webbtjänsten på den lokala datorn kan använda TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="da2e7-115">The Office client can use TLS 1.2 if the web service of the local computer can use TLS 1.2.</span></span> <span data-ttu-id="da2e7-116">Alla Office kan använda TLS-protokoll eftersom TLS- och SSL-protokoll är en del av operativsystemet och inte är specifika för Office klienten.</span><span class="sxs-lookup"><span data-stu-id="da2e7-116">All Office clients can use TLS protocols, as TLS and SSL protocols are part of the operating system and not specific to the Office client.</span></span>

### <a name="on-windows-8-and-later-versions"></a><span data-ttu-id="da2e7-117">I Windows 8 och senare versioner</span><span class="sxs-lookup"><span data-stu-id="da2e7-117">On Windows 8 and later versions</span></span>

<span data-ttu-id="da2e7-118">Som standard är protokollen TLS 1.2 och 1.1 tillgängliga om inga nätverksenheter är konfigurerade att avvisa TLS 1.2-trafik.</span><span class="sxs-lookup"><span data-stu-id="da2e7-118">By default, the TLS 1.2 and 1.1 protocols are available if no network devices are configured to reject TLS 1.2 traffic.</span></span>

### <a name="on-windows-7"></a><span data-ttu-id="da2e7-119">På Windows 7</span><span class="sxs-lookup"><span data-stu-id="da2e7-119">On Windows 7</span></span>

<span data-ttu-id="da2e7-120">TLS 1.1- och 1.2-protokoll är inte tillgängliga utan [UPPDATERINGEN KB 3140245.](https://support.microsoft.com/help/3140245)</span><span class="sxs-lookup"><span data-stu-id="da2e7-120">TLS 1.1 and 1.2 protocols are not available without the [KB 3140245](https://support.microsoft.com/help/3140245) update.</span></span> <span data-ttu-id="da2e7-121">Uppdateringen åtgärdar problemet och lägger till följande registerundernyckel:</span><span class="sxs-lookup"><span data-stu-id="da2e7-121">The update addresses this issue and adds the following registry sub key:</span></span>

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> <span data-ttu-id="da2e7-122">Windows 7 användare som inte har den här uppdateringen påverkas efter den 31 oktober 2018.</span><span class="sxs-lookup"><span data-stu-id="da2e7-122">Windows 7 users who do not have this update are affected as of October 31, 2018.</span></span> <span data-ttu-id="da2e7-123">[KB 3140245](https://support.microsoft.com/help/3140245) innehåller information om hur du ändrar WINHTTP-inställningar för att aktivera TLS-protokoll.</span><span class="sxs-lookup"><span data-stu-id="da2e7-123">[KB 3140245](https://support.microsoft.com/help/3140245) has details about how to change WINHTTP settings to enable TLS protocols.</span></span>

#### <a name="more-information"></a><span data-ttu-id="da2e7-124">Mer information</span><span class="sxs-lookup"><span data-stu-id="da2e7-124">More information</span></span>

<span data-ttu-id="da2e7-125">Värdet för registernyckeln **DefaultSecureProtocols** som kb-artikeln beskriver avgör vilka nätverksprotokoll som kan användas:</span><span class="sxs-lookup"><span data-stu-id="da2e7-125">The value of the **DefaultSecureProtocols** registry key that the KB article describes determines which network protocols can be used:</span></span>

|<span data-ttu-id="da2e7-126">DefaultSecureProtocols-värde</span><span class="sxs-lookup"><span data-stu-id="da2e7-126">DefaultSecureProtocols Value</span></span>|<span data-ttu-id="da2e7-127">Protokoll aktiverat</span><span class="sxs-lookup"><span data-stu-id="da2e7-127">Protocol enabled</span></span>|
|-|-|
|<span data-ttu-id="da2e7-128">0x00000008</span><span class="sxs-lookup"><span data-stu-id="da2e7-128">0x00000008</span></span>|<span data-ttu-id="da2e7-129">Aktivera SSL 2.0 som standard</span><span class="sxs-lookup"><span data-stu-id="da2e7-129">Enable SSL 2.0 by default</span></span>|
|<span data-ttu-id="da2e7-130">0x00000020</span><span class="sxs-lookup"><span data-stu-id="da2e7-130">0x00000020</span></span>|<span data-ttu-id="da2e7-131">Aktivera SSL 3.0 som standard</span><span class="sxs-lookup"><span data-stu-id="da2e7-131">Enable SSL 3.0 by default</span></span>|
|<span data-ttu-id="da2e7-132">0x00000080</span><span class="sxs-lookup"><span data-stu-id="da2e7-132">0x00000080</span></span>|<span data-ttu-id="da2e7-133">Aktivera TLS 1.0 som standard</span><span class="sxs-lookup"><span data-stu-id="da2e7-133">Enable TLS 1.0 by default</span></span>|
|<span data-ttu-id="da2e7-134">0x00000200</span><span class="sxs-lookup"><span data-stu-id="da2e7-134">0x00000200</span></span>|<span data-ttu-id="da2e7-135">Aktivera TLS 1.1 som standard</span><span class="sxs-lookup"><span data-stu-id="da2e7-135">Enable TLS 1.1 by default</span></span>|
|<span data-ttu-id="da2e7-136">0x00000800</span><span class="sxs-lookup"><span data-stu-id="da2e7-136">0x00000800</span></span>|<span data-ttu-id="da2e7-137">Aktivera TLS 1.2 som standard</span><span class="sxs-lookup"><span data-stu-id="da2e7-137">Enable TLS 1.2 by default</span></span>|

## <a name="office-clients-and-tls-registry-keys"></a><span data-ttu-id="da2e7-138">Office klienter och TLS-registernycklar</span><span class="sxs-lookup"><span data-stu-id="da2e7-138">Office clients and TLS registry keys</span></span>

<span data-ttu-id="da2e7-139">Läs KB [4057306](https://support.microsoft.com/help/4057306)Förbereda för obligatorisk användning av TLS 1.2 i Office 365.</span><span class="sxs-lookup"><span data-stu-id="da2e7-139">You can refer to [KB 4057306 Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306).</span></span> <span data-ttu-id="da2e7-140">Det här är en allmän artikel för IT-administratörer och är officiell dokumentation om ändringen TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="da2e7-140">This is a general article for IT administrators, and it's official documentation about the TLS 1.2 change.</span></span>

<span data-ttu-id="da2e7-141">I följande tabell visas lämpliga registernyckelvärden i Office 365 klienter efter den 31 oktober 2018.</span><span class="sxs-lookup"><span data-stu-id="da2e7-141">The following table shows the appropriate registry key values in Office 365 clients after October 31, 2018.</span></span>

|<span data-ttu-id="da2e7-142">Protokoll som är Office 365 tjänst efter den 31 oktober 2018</span><span class="sxs-lookup"><span data-stu-id="da2e7-142">Enabled protocols for Office 365 service after October 31, 2018</span></span>|<span data-ttu-id="da2e7-143">Hexadecimalt värde</span><span class="sxs-lookup"><span data-stu-id="da2e7-143">Hexadecimal value</span></span>|
|-|-|
|<span data-ttu-id="da2e7-144">TLS 1,0 + 1,1 + 1,2</span><span class="sxs-lookup"><span data-stu-id="da2e7-144">TLS 1.0 + 1.1 + 1.2</span></span>|<span data-ttu-id="da2e7-145">0x00000A80</span><span class="sxs-lookup"><span data-stu-id="da2e7-145">0x00000A80</span></span>|
|<span data-ttu-id="da2e7-146">TLS 1.1 + 1.2</span><span class="sxs-lookup"><span data-stu-id="da2e7-146">TLS 1.1 + 1.2</span></span>|<span data-ttu-id="da2e7-147">0x00000A00</span><span class="sxs-lookup"><span data-stu-id="da2e7-147">0x00000A00</span></span>|
|<span data-ttu-id="da2e7-148">TLS 1,0 + 1,2</span><span class="sxs-lookup"><span data-stu-id="da2e7-148">TLS 1.0 + 1.2</span></span>|<span data-ttu-id="da2e7-149">0x00000880</span><span class="sxs-lookup"><span data-stu-id="da2e7-149">0x00000880</span></span>|
|<span data-ttu-id="da2e7-150">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="da2e7-150">TLS 1.2</span></span>|<span data-ttu-id="da2e7-151">0x00000800</span><span class="sxs-lookup"><span data-stu-id="da2e7-151">0x00000800</span></span>|

> [!IMPORTANT]
> <span data-ttu-id="da2e7-152">Använd inte SSL 2.0- och 3.0-protokoll, som också kan ställas in med hjälp av **nyckeln DefaultSecureProtocols.**</span><span class="sxs-lookup"><span data-stu-id="da2e7-152">Don't use the SSL 2.0 and 3.0 protocols, which can also be set by using the **DefaultSecureProtocols** key.</span></span> <span data-ttu-id="da2e7-153">SSL 2.0 och 3.0 anses vara inaktuella och osäkra protokoll.</span><span class="sxs-lookup"><span data-stu-id="da2e7-153">SSL 2.0 and 3.0 are considered outdated and insecure protocols.</span></span> <span data-ttu-id="da2e7-154">Det bästa är att sluta använda SSL 2.0 och SSL 3.0, även om beslutet att göra det i slutänden beror på vad som bäst uppfyller dina produktbehov.</span><span class="sxs-lookup"><span data-stu-id="da2e7-154">The best practice is to end the use of SSL 2.0 and SSL 3.0, although the decision to do this ultimately depends on what best meets your product needs.</span></span> <span data-ttu-id="da2e7-155">Mer information om säkerhetsproblem med SSL 3.0 finns i [KB 3009008.](https://support.microsoft.com/help/3009008)</span><span class="sxs-lookup"><span data-stu-id="da2e7-155">For more information about SSL 3.0 vulnerabilities, refer to [KB 3009008](https://support.microsoft.com/help/3009008).</span></span>

<span data-ttu-id="da2e7-156">Du kan använda standardkalkylatorn Windows i programmerarläge till att konfigurera samma registernyckelvärden för referens.</span><span class="sxs-lookup"><span data-stu-id="da2e7-156">You can use the default Windows Calculator in Programmer mode to set up the same reference registry key values.</span></span> <span data-ttu-id="da2e7-157">Mer information finns i KB 3140245 Uppdatering för att aktivera [TLS 1.1 och TLS 1.2](https://support.microsoft.com/help/3140245)som en standard säker protokoll i WinHTTP i Windows.</span><span class="sxs-lookup"><span data-stu-id="da2e7-157">For more information, see [KB 3140245 Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245).</span></span>

<span data-ttu-id="da2e7-158">Oavsett om Windows 7-uppdateringen ([KB 3140245)](https://support.microsoft.com/help/3140245)är installerad eller inte finns inte registerundernyckeln DefaultSecureProtocols och måste läggas till manuellt eller via ett grupprincipobjekt (GPO).</span><span class="sxs-lookup"><span data-stu-id="da2e7-158">Regardless if the Windows 7 update ([KB 3140245](https://support.microsoft.com/help/3140245)) is installed or not, the DefaultSecureProtocols registry sub key isn't present and must be added manually or through a group policy object (GPO).</span></span> <span data-ttu-id="da2e7-159">Den här nyckeln krävs inte, såvida du inte behöver anpassa vilka säkra protokoll som är aktiverade eller begränsade.</span><span class="sxs-lookup"><span data-stu-id="da2e7-159">That is, unless you have to customize what secure protocols are enabled or restricted, this key is not required.</span></span> <span data-ttu-id="da2e7-160">Du behöver bara Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) uppdatering.</span><span class="sxs-lookup"><span data-stu-id="da2e7-160">You only need the Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) update.</span></span>

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a><span data-ttu-id="da2e7-161">Uppdatera och konfigurera .NET Framework TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="da2e7-161">Update and configure the .NET Framework to support TLS 1.2</span></span>

<span data-ttu-id="da2e7-162">Du måste uppdatera program som anropar Microsoft 365 API:er via TLS 1.0 eller TLS 1.1 för att använda TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="da2e7-162">You'll need to update applications that call Microsoft 365 APIs over TLS 1.0 or TLS 1.1 to use TLS 1.2.</span></span> <span data-ttu-id="da2e7-163">.NET 4.5 blir TLS 1.1 som standard.</span><span class="sxs-lookup"><span data-stu-id="da2e7-163">.NET 4.5 defaults to TLS 1.1.</span></span> <span data-ttu-id="da2e7-164">Om du vill uppdatera .NET-konfigurationen går du till [Aktivera TLS (Transport Layer Security) 1.2 på klienter.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)</span><span class="sxs-lookup"><span data-stu-id="da2e7-164">To update your .NET configuration, see [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client).</span></span>

## <a name="more-information"></a><span data-ttu-id="da2e7-165">Mer information</span><span class="sxs-lookup"><span data-stu-id="da2e7-165">More information</span></span>

<span data-ttu-id="da2e7-166">Mer information finns i Förbereda [för obligatorisk användning av TLS 1.2 i Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="da2e7-166">For more information, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>