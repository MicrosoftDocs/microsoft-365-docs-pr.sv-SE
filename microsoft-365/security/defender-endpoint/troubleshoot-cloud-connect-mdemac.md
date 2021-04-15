---
title: Felsöka molnanslutningsproblem för Microsoft Defender för slutpunkt i macOS
description: I det här avsnittet beskrivs hur du felsöker problem med molnanslutningen för Microsoft Defender för slutpunkt på macOS
keywords: microsoft, defender, atp, mac, installation, distribuera, avinstallation, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fbe9d0006a2f1779e1bad60dc283a5a40429dbdd
ms.sourcegitcommit: 07dea2aa98daf0c4086f8590375167830027c802
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51750022"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="1ddab-104">Felsöka molnanslutningsproblem för Microsoft Defender för slutpunkt i macOS</span><span class="sxs-lookup"><span data-stu-id="1ddab-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1ddab-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="1ddab-105">**Applies to:**</span></span>
- [<span data-ttu-id="1ddab-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="1ddab-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1ddab-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1ddab-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="1ddab-108">**Plattform** macOS</span><span class="sxs-lookup"><span data-stu-id="1ddab-108">**Platform** macOS</span></span>

<span data-ttu-id="1ddab-109">I det här avsnittet beskrivs hur du felsöker molnanslutningsproblem för Microsoft Defender för slutpunkt på macOS.</span><span class="sxs-lookup"><span data-stu-id="1ddab-109">This topic describes how to Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on macOS.</span></span>

## <a name="run-the-connectivity-test"></a><span data-ttu-id="1ddab-110">Köra anslutningstestet</span><span class="sxs-lookup"><span data-stu-id="1ddab-110">Run the connectivity test</span></span>
<span data-ttu-id="1ddab-111">Testa om Defender för slutpunkt på Mac kan kommunicera till molnet med de aktuella nätverksinställningarna genom att köra ett anslutningstest från kommandoraden:</span><span class="sxs-lookup"><span data-stu-id="1ddab-111">To test if Defender for Endpoint on Mac can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```Bash
mdatp connectivity test
```

<span data-ttu-id="1ddab-112">förväntat utdata:</span><span class="sxs-lookup"><span data-stu-id="1ddab-112">expected output:</span></span>
```Bash
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

<span data-ttu-id="1ddab-113">Om anslutningstestet misslyckas kontrollerar du om enheten har Internetanslutning och om någon av slutpunkterna som krävs av produkten [blockeras](microsoft-defender-endpoint-mac.md#network-connections) av en proxy eller brandvägg.</span><span class="sxs-lookup"><span data-stu-id="1ddab-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-mac.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="1ddab-114">Fel med avrullningsfel 35 eller 60 anger avvisning av certifikat som anger ett potentiellt problem med SSL- eller HTTPS-kontrollen.</span><span class="sxs-lookup"><span data-stu-id="1ddab-114">Failures with curl error 35 or 60 indicate certificate pinning rejection, which indicates a potential issue with SSL or HTTPS inspection.</span></span> <span data-ttu-id="1ddab-115">Se anvisningarna nedan om KONFIGURATION av SSL-kontroll.</span><span class="sxs-lookup"><span data-stu-id="1ddab-115">See instructions below regarding SSL inspection configuration.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a><span data-ttu-id="1ddab-116">Felsökningssteg för miljöer utan proxy eller med autoconfig (PAC) eller med Web Proxy Autodiscovery Protocol (WPAD)</span><span class="sxs-lookup"><span data-stu-id="1ddab-116">Troubleshooting steps for environments without proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD)</span></span>
<span data-ttu-id="1ddab-117">Använd följande procedur för att testa att en anslutning inte blockeras i en miljö utan proxy eller med autoconfig proxy (PAC) eller med WPAD (Web Proxy Autodiscovery Protocol).</span><span class="sxs-lookup"><span data-stu-id="1ddab-117">Use the following procedure to test that a connection is not blocked in an environment without a proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD).</span></span>

<span data-ttu-id="1ddab-118">Om en proxy eller brandvägg blockerar anonym trafik kontrollerar du att anonym trafik tillåts i tidigare angivna URL:er.</span><span class="sxs-lookup"><span data-stu-id="1ddab-118">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="1ddab-119">Autentiserad proxy.</span><span class="sxs-lookup"><span data-stu-id="1ddab-119">Authenticated proxies are not supported.</span></span> <span data-ttu-id="1ddab-120">Se till att endast PAC, WPAD eller en statisk proxy används.</span><span class="sxs-lookup"><span data-stu-id="1ddab-120">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span> <span data-ttu-id="1ddab-121">SSL-proxy proxy och skärningspunkt stöds inte heller av säkerhetsskäl.</span><span class="sxs-lookup"><span data-stu-id="1ddab-121">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="1ddab-122">Konfigurera ett undantag för SSL-kontroll och proxyservern för att direkt överföra data från Microsoft Defender för Slutpunkt i macOS till relevanta URL:er utan avlyssning.</span><span class="sxs-lookup"><span data-stu-id="1ddab-122">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint on macOS to the relevant URLs without interception.</span></span> <span data-ttu-id="1ddab-123">Om du lägger till ditt certifikat för avlyssning i det globala lagret tillåts inte avlyssning.</span><span class="sxs-lookup"><span data-stu-id="1ddab-123">Adding your interception certificate to the global store will not allow for interception.</span></span>
<span data-ttu-id="1ddab-124">Så här testar du att en anslutning inte är blockerad: Öppna en webbläsare som Microsoft Edge för Mac eller Safari och https://x.cp.wd.microsoft.com/api/report https://cdn.x.cp.wd.microsoft.com/ping .</span><span class="sxs-lookup"><span data-stu-id="1ddab-124">To test that a connection is not blocked: In a browser such as Microsoft Edge for Mac or Safari open https://x.cp.wd.microsoft.com/api/report and https://cdn.x.cp.wd.microsoft.com/ping.</span></span>

<span data-ttu-id="1ddab-125">Du kan också köra följande kommando i Terminal:</span><span class="sxs-lookup"><span data-stu-id="1ddab-125">Optionally, in Terminal, run the following command:</span></span>

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

<span data-ttu-id="1ddab-126">Utdata från det här kommandot bör se ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="1ddab-126">The output from this command should be similar to:</span></span>
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
