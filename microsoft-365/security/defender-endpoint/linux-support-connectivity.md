---
title: Felsöka molnanslutningsproblem för Microsoft Defender ATP för Linux
ms.reviewer: ''
description: Felsöka molnanslutningsproblem för Microsoft Defender ATP för Linux
keywords: microsoft, defender, atp, linux, moln, anslutning, kommunikation
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d698eb78f354d624d9ab115a8ecd2e0862e607e3
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688867"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="174ad-104">Felsöka problem med molnanslutning för Microsoft Defender för Slutpunkt i Linux</span><span class="sxs-lookup"><span data-stu-id="174ad-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="174ad-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="174ad-105">**Applies to:**</span></span>
- [<span data-ttu-id="174ad-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="174ad-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="174ad-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="174ad-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="174ad-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="174ad-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="174ad-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="174ad-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a><span data-ttu-id="174ad-110">Köra anslutningstestet</span><span class="sxs-lookup"><span data-stu-id="174ad-110">Run the connectivity test</span></span>

<span data-ttu-id="174ad-111">Om du vill testa om Defender för Slutpunkt för Linux kan kommunicera till molnet med de aktuella nätverksinställningarna kör du ett anslutningstest från kommandoraden:</span><span class="sxs-lookup"><span data-stu-id="174ad-111">To test if Defender for Endpoint for Linux can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="174ad-112">förväntat utdata:</span><span class="sxs-lookup"><span data-stu-id="174ad-112">expected output:</span></span>

```output
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

<span data-ttu-id="174ad-113">Om anslutningstestet misslyckas kontrollerar du om enheten har Internetanslutning och om någon av slutpunkterna som krävs av produkten [blockeras](microsoft-defender-endpoint-linux.md#network-connections) av en proxy eller brandvägg.</span><span class="sxs-lookup"><span data-stu-id="174ad-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-linux.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="174ad-114">Fel med avkodningsfel 35 eller 60 anger avslag på certifikatkod.</span><span class="sxs-lookup"><span data-stu-id="174ad-114">Failures with curl error 35 or 60, indicate certificate pinning rejection.</span></span> <span data-ttu-id="174ad-115">Kontrollera om anslutningen är under SSL- eller HTTPS-kontroll.</span><span class="sxs-lookup"><span data-stu-id="174ad-115">Please check if the connection is under SSL or HTTPS inspection.</span></span> <span data-ttu-id="174ad-116">I så fall lägger du till Microsoft Defender för Endpoint i listan över tillåtna slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="174ad-116">If so, add Microsoft Defender for Endpoint to the allow list.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a><span data-ttu-id="174ad-117">Felsökningssteg för miljöer utan proxy eller med transparent proxy</span><span class="sxs-lookup"><span data-stu-id="174ad-117">Troubleshooting steps for environments without proxy or with transparent proxy</span></span>

<span data-ttu-id="174ad-118">Testa att en anslutning inte är blockerad i en miljö utan proxy eller med en transparent proxy genom att köra följande kommando i terminalen:</span><span class="sxs-lookup"><span data-stu-id="174ad-118">To test that a connection is not blocked in an environment without a proxy or with a transparent proxy, run the following command in the terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="174ad-119">Utdata från det här kommandot bör se ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="174ad-119">The output from this command should be similar to:</span></span>

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a><span data-ttu-id="174ad-120">Felsökningssteg för miljöer med statisk proxy</span><span class="sxs-lookup"><span data-stu-id="174ad-120">Troubleshooting steps for environments with static proxy</span></span>

> [!WARNING]
> <span data-ttu-id="174ad-121">PAC, WPAD och autentiserad proxy går inte att använda.</span><span class="sxs-lookup"><span data-stu-id="174ad-121">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="174ad-122">Se till att bara en statisk proxy eller transparent proxy används.</span><span class="sxs-lookup"><span data-stu-id="174ad-122">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="174ad-123">SSL-proxy proxy och skärningspunkt stöds inte heller av säkerhetsskäl.</span><span class="sxs-lookup"><span data-stu-id="174ad-123">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="174ad-124">Konfigurera ett undantag för SSL-kontroll och din proxyserver för att direkt överföra data från Defender för Endpoint för Linux till relevanta URL:er utan avlyssning.</span><span class="sxs-lookup"><span data-stu-id="174ad-124">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint for Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="174ad-125">Om du lägger till ditt certifikat för avlyssning i det globala lagret tillåts inte avlyssning.</span><span class="sxs-lookup"><span data-stu-id="174ad-125">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="174ad-126">Om en statisk proxy krävs lägger du till en proxyparameter till kommandot ovan, `proxy_address:port` där det motsvarar proxyadressen och port:</span><span class="sxs-lookup"><span data-stu-id="174ad-126">If a static proxy is required, add a proxy parameter to the above command, where `proxy_address:port` correspond to the proxy address and port:</span></span>

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="174ad-127">Kontrollera att du använder samma proxyadress och port som konfigurerats i `/lib/system/system/mdatp.service` filen.</span><span class="sxs-lookup"><span data-stu-id="174ad-127">Ensure that you use the same proxy address and port as configured in the `/lib/system/system/mdatp.service` file.</span></span> <span data-ttu-id="174ad-128">Kontrollera proxykonfigurationen om det finns fel från kommandona ovan.</span><span class="sxs-lookup"><span data-stu-id="174ad-128">Check your proxy configuration if there are errors from the above commands.</span></span>

> [!WARNING]
> <span data-ttu-id="174ad-129">Den statiska proxyn kan inte konfigureras via en `HTTPS_PROXY` miljövariabel som gäller hela systemet.</span><span class="sxs-lookup"><span data-stu-id="174ad-129">The static proxy cannot be configured through a system-wide `HTTPS_PROXY` environment variable.</span></span> <span data-ttu-id="174ad-130">Kontrollera i stället att `HTTPS_PROXY` filen är rätt `/lib/system/system/mdatp.service` inställd.</span><span class="sxs-lookup"><span data-stu-id="174ad-130">Instead, ensure that `HTTPS_PROXY` is properly set in the `/lib/system/system/mdatp.service` file.</span></span>

<span data-ttu-id="174ad-131">Om du vill använda en statisk `mdatp.service` proxyserver måste filen ändras.</span><span class="sxs-lookup"><span data-stu-id="174ad-131">To use a static proxy, the `mdatp.service` file must be modified.</span></span> <span data-ttu-id="174ad-132">Se till att `#` inledningen tas bort för att ta bort den rad som följer `/lib/systemd/system/mdatp.service` från:</span><span class="sxs-lookup"><span data-stu-id="174ad-132">Ensure the leading `#` is removed to uncomment the following line from `/lib/systemd/system/mdatp.service`:</span></span>

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

<span data-ttu-id="174ad-133">Se också till att rätt statisk proxyadress fylls i för att ersätta `address:port` .</span><span class="sxs-lookup"><span data-stu-id="174ad-133">Also ensure that the correct static proxy address is filled in to replace `address:port`.</span></span>

<span data-ttu-id="174ad-134">Om filen är korrekt kan du prova att köra följande kommando i terminalen för att läsa in Defender för Endpoint för Linux på nytt och sprida inställningen:</span><span class="sxs-lookup"><span data-stu-id="174ad-134">If this file is correct, try running the following command in the terminal to reload Defender for Endpoint for Linux and propagate the setting:</span></span>

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

<span data-ttu-id="174ad-135">När anslutningstestet lyckas försöker du med ett annat anslutningstest från kommandoraden:</span><span class="sxs-lookup"><span data-stu-id="174ad-135">Upon success, attempt another connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="174ad-136">Kontakta kundsupport om problemet kvarstår.</span><span class="sxs-lookup"><span data-stu-id="174ad-136">If the problem persists, contact customer support.</span></span>

## <a name="resources"></a><span data-ttu-id="174ad-137">Resurser</span><span class="sxs-lookup"><span data-stu-id="174ad-137">Resources</span></span>

- <span data-ttu-id="174ad-138">Mer information om hur du konfigurerar produkten för att använda en statisk proxy finns i Konfigurera Microsoft Defender för [slutpunkt för statisk proxyidentifiering.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="174ad-138">For more information about how to configure the product to use a static proxy, see [Configure Microsoft Defender for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).</span></span>
