---
title: Utvärdera nätverksskydd
description: Se hur nätverksskyddet fungerar genom att testa vanliga scenarier som det skyddar mot.
keywords: Nätverksskydd, sårbarheter, skadlig webbplats, ip, domän, domäner, utvärdera, testa, demo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 41d1c9400720e20185922a97463e776c3ce0d80a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072233"
---
# <a name="evaluate-network-protection"></a><span data-ttu-id="fb760-104">Utvärdera nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="fb760-104">Evaluate network protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fb760-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="fb760-105">**Applies to:**</span></span>
- [<span data-ttu-id="fb760-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="fb760-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- - [<span data-ttu-id="fb760-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fb760-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="fb760-108">[Nätverksskydd](network-protection.md) förhindrar anställda från att använda ett program för att komma åt skadliga domäner som kan vara värdar för nätfiske, sårbarheter och annat skadligt innehåll på Internet.</span><span class="sxs-lookup"><span data-stu-id="fb760-108">[Network protection](network-protection.md) helps prevent employees from using any application to access dangerous domains that may host phishing scams, exploits, and other malicious content on the Internet.</span></span>

<span data-ttu-id="fb760-109">Den här artikeln hjälper dig att utvärdera nätverksskydd genom att aktivera funktionen och vägleda dig till en testwebbplats.</span><span class="sxs-lookup"><span data-stu-id="fb760-109">This article helps you evaluate network protection by enabling the feature and guiding you to a testing site.</span></span> <span data-ttu-id="fb760-110">Webbplatserna i den här utvärderingsartikeln är inte skadliga.</span><span class="sxs-lookup"><span data-stu-id="fb760-110">The sites in this evaluation article aren't malicious.</span></span> <span data-ttu-id="fb760-111">De är särskilt skapade webbplatser som utger sig för att vara skadliga.</span><span class="sxs-lookup"><span data-stu-id="fb760-111">They're specially created websites that pretend to be malicious.</span></span> <span data-ttu-id="fb760-112">Webbplatsen replikerar beteendet som skulle inträffa om en användare besökte en skadlig webbplats eller domän.</span><span class="sxs-lookup"><span data-stu-id="fb760-112">The site will replicate the behavior that would happen if a user visited a malicious site or domain.</span></span>

> [!TIP]
> <span data-ttu-id="fb760-113">Du kan också besöka webbplatsen för Microsoft Defender Testground på [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) om du vill se hur andra skyddsfunktioner fungerar.</span><span class="sxs-lookup"><span data-stu-id="fb760-113">You can also visit the Microsoft Defender Testground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how other protection features work.</span></span>

## <a name="enable-network-protection-in-audit-mode"></a><span data-ttu-id="fb760-114">Aktivera nätverksskydd i granskningsläge</span><span class="sxs-lookup"><span data-stu-id="fb760-114">Enable network protection in audit mode</span></span>

<span data-ttu-id="fb760-115">Aktivera nätverksskydd i granskningsläge för att se vilka IP-adresser och domäner som skulle ha blockerats.</span><span class="sxs-lookup"><span data-stu-id="fb760-115">Enable network protection in audit mode to see which IP addresses and domains would have been blocked.</span></span> <span data-ttu-id="fb760-116">Du kan kontrollera att det inte påverkar verksamhetsbaserade appar eller få en uppfattning om hur ofta block uppstår.</span><span class="sxs-lookup"><span data-stu-id="fb760-116">You can make sure it doesn't affect line-of-business apps, or get an idea of how often blocks occur.</span></span>

1. <span data-ttu-id="fb760-117">Skriv **powershell** på Start-menyn, högerklicka på **Windows PowerShell och** välj Kör som **administratör**</span><span class="sxs-lookup"><span data-stu-id="fb760-117">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="fb760-118">Ange följande cmdlet:</span><span class="sxs-lookup"><span data-stu-id="fb760-118">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a><span data-ttu-id="fb760-119">Besök en (falsk) skadlig domän</span><span class="sxs-lookup"><span data-stu-id="fb760-119">Visit a (fake) malicious domain</span></span>

1. <span data-ttu-id="fb760-120">Öppna Internet Explorer, Google Chrome eller valfri webbläsare.</span><span class="sxs-lookup"><span data-stu-id="fb760-120">Open Internet Explorer, Google Chrome, or any other browser of your choice.</span></span>

1. <span data-ttu-id="fb760-121">Gå till [https://smartscreentestratings2.net](https://smartscreentestratings2.net).</span><span class="sxs-lookup"><span data-stu-id="fb760-121">Go to [https://smartscreentestratings2.net](https://smartscreentestratings2.net).</span></span>

<span data-ttu-id="fb760-122">Nätverksanslutningen tillåts och ett testmeddelande visas.</span><span class="sxs-lookup"><span data-stu-id="fb760-122">The network connection will be allowed and a test message will be displayed.</span></span>

![Exempelmeddelande om att anslutningen är blockerad: IT-administratören orsakade att Windows-säkerhet blockerade den här nätverksanslutningen.](/microsoft-365/security/defender-endpoint/images/np-notif)

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="fb760-125">Granska nätverksskyddshändelser i Windows Loggboken</span><span class="sxs-lookup"><span data-stu-id="fb760-125">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="fb760-126">Om du vill granska appar som skulle ha blockerats öppnar du Loggboken och filtrerar efter Händelse-ID 1125 i Microsoft-Windows-Windows-Defender/Drift-loggen.</span><span class="sxs-lookup"><span data-stu-id="fb760-126">To review apps that would have been blocked, open Event Viewer and filter for Event ID 1125 in the Microsoft-Windows-Windows-Defender/Operational log.</span></span> <span data-ttu-id="fb760-127">I följande tabell visas alla nätverksskyddshändelser.</span><span class="sxs-lookup"><span data-stu-id="fb760-127">The following table lists all network protection events.</span></span>

| <span data-ttu-id="fb760-128">Händelse-ID</span><span class="sxs-lookup"><span data-stu-id="fb760-128">Event ID</span></span> | <span data-ttu-id="fb760-129">Ange/källa</span><span class="sxs-lookup"><span data-stu-id="fb760-129">Provide/Source</span></span> | <span data-ttu-id="fb760-130">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="fb760-130">Description</span></span> |
|-|-|-|
|<span data-ttu-id="fb760-131">5007</span><span class="sxs-lookup"><span data-stu-id="fb760-131">5007</span></span> | <span data-ttu-id="fb760-132">Windows Defender (drift)</span><span class="sxs-lookup"><span data-stu-id="fb760-132">Windows Defender (Operational)</span></span> | <span data-ttu-id="fb760-133">Händelse när inställningar ändras</span><span class="sxs-lookup"><span data-stu-id="fb760-133">Event when settings are changed</span></span> |
|<span data-ttu-id="fb760-134">1125</span><span class="sxs-lookup"><span data-stu-id="fb760-134">1125</span></span> | <span data-ttu-id="fb760-135">Windows Defender (drift)</span><span class="sxs-lookup"><span data-stu-id="fb760-135">Windows Defender (Operational)</span></span> | <span data-ttu-id="fb760-136">Händelse när en nätverksanslutning granskas</span><span class="sxs-lookup"><span data-stu-id="fb760-136">Event when a network connection is audited</span></span> |
|<span data-ttu-id="fb760-137">1126</span><span class="sxs-lookup"><span data-stu-id="fb760-137">1126</span></span> | <span data-ttu-id="fb760-138">Windows Defender (drift)</span><span class="sxs-lookup"><span data-stu-id="fb760-138">Windows Defender (Operational)</span></span> | <span data-ttu-id="fb760-139">Händelse när en nätverksanslutning blockeras</span><span class="sxs-lookup"><span data-stu-id="fb760-139">Event when a network connection is blocked</span></span> |

## <a name="see-also"></a><span data-ttu-id="fb760-140">Se även</span><span class="sxs-lookup"><span data-stu-id="fb760-140">See also</span></span>

* [<span data-ttu-id="fb760-141">Nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="fb760-141">Network protection</span></span>](network-protection.md)
* [<span data-ttu-id="fb760-142">Aktivera nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="fb760-142">Enable network protection</span></span>](enable-network-protection.md)
* [<span data-ttu-id="fb760-143">Felsöka nätverksskydd</span><span class="sxs-lookup"><span data-stu-id="fb760-143">Troubleshoot network protection</span></span>](troubleshoot-np.md)
