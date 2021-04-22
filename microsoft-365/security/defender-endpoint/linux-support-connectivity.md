---
title: Felsöka problem med molnanslutning för Microsoft Defender för Slutpunkt i Linux
ms.reviewer: ''
description: Felsöka problem med molnanslutning för Microsoft Defender för Slutpunkt i Linux
keywords: microsoft, defender, Microsoft Defender för slutpunkt, linux, moln, anslutning, kommunikation
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
ms.openlocfilehash: 0345d7f88d147abb750e66a5e61f516abf38d553
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933115"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="95899-104">Felsöka problem med molnanslutning för Microsoft Defender för Slutpunkt i Linux</span><span class="sxs-lookup"><span data-stu-id="95899-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="95899-105">**Gäller för:**</span><span class="sxs-lookup"><span data-stu-id="95899-105">**Applies to:**</span></span>
- [<span data-ttu-id="95899-106">Microsoft Defender för Endpoint</span><span class="sxs-lookup"><span data-stu-id="95899-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="95899-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="95899-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="95899-108">Vill du använda Defender för Slutpunkt?</span><span class="sxs-lookup"><span data-stu-id="95899-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="95899-109">Registrera dig för en kostnadsfri utvärderingsversion.</span><span class="sxs-lookup"><span data-stu-id="95899-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a><span data-ttu-id="95899-110">Köra anslutningstestet</span><span class="sxs-lookup"><span data-stu-id="95899-110">Run the connectivity test</span></span>

<span data-ttu-id="95899-111">Testa om Defender för Slutpunkt i Linux kan kommunicera till molnet med de aktuella nätverksinställningarna genom att köra ett anslutningstest från kommandoraden:</span><span class="sxs-lookup"><span data-stu-id="95899-111">To test if Defender for Endpoint on Linux can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="95899-112">förväntat utdata:</span><span class="sxs-lookup"><span data-stu-id="95899-112">expected output:</span></span>

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

<span data-ttu-id="95899-113">Om anslutningstestet misslyckas kontrollerar du om enheten har Internetanslutning och om någon av slutpunkterna som krävs av produkten [blockeras](microsoft-defender-endpoint-linux.md#network-connections) av en proxy eller brandvägg.</span><span class="sxs-lookup"><span data-stu-id="95899-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-linux.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="95899-114">Fel med avkodningsfel 35 eller 60 anger avslag på certifikatkod.</span><span class="sxs-lookup"><span data-stu-id="95899-114">Failures with curl error 35 or 60, indicate certificate pinning rejection.</span></span> <span data-ttu-id="95899-115">Kontrollera om anslutningen är under SSL- eller HTTPS-kontroll.</span><span class="sxs-lookup"><span data-stu-id="95899-115">Please check if the connection is under SSL or HTTPS inspection.</span></span> <span data-ttu-id="95899-116">I så fall lägger du till Microsoft Defender för Endpoint i listan över tillåtna slutpunkter.</span><span class="sxs-lookup"><span data-stu-id="95899-116">If so, add Microsoft Defender for Endpoint to the allow list.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a><span data-ttu-id="95899-117">Felsökningssteg för miljöer utan proxy eller med transparent proxy</span><span class="sxs-lookup"><span data-stu-id="95899-117">Troubleshooting steps for environments without proxy or with transparent proxy</span></span>

<span data-ttu-id="95899-118">Testa att en anslutning inte är blockerad i en miljö utan proxy eller med en transparent proxy genom att köra följande kommando i terminalen:</span><span class="sxs-lookup"><span data-stu-id="95899-118">To test that a connection is not blocked in an environment without a proxy or with a transparent proxy, run the following command in the terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="95899-119">Utdata från det här kommandot bör se ut ungefär så här:</span><span class="sxs-lookup"><span data-stu-id="95899-119">The output from this command should be similar to:</span></span>

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a><span data-ttu-id="95899-120">Felsökningssteg för miljöer med statisk proxy</span><span class="sxs-lookup"><span data-stu-id="95899-120">Troubleshooting steps for environments with static proxy</span></span>

> [!WARNING]
> <span data-ttu-id="95899-121">PAC, WPAD och autentiserad proxy går inte att använda.</span><span class="sxs-lookup"><span data-stu-id="95899-121">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="95899-122">Se till att bara en statisk proxy eller transparent proxy används.</span><span class="sxs-lookup"><span data-stu-id="95899-122">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="95899-123">SSL-proxy proxy och skärningspunkt stöds inte heller av säkerhetsskäl.</span><span class="sxs-lookup"><span data-stu-id="95899-123">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="95899-124">Konfigurera ett undantag för SSL-kontrollen och proxyservern för att direkt överföra data från Defender för Slutpunkt i Linux till relevanta URL:er utan avlyssning.</span><span class="sxs-lookup"><span data-stu-id="95899-124">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="95899-125">Om du lägger till ditt certifikat för avlyssning i det globala lagret tillåts inte avlyssning.</span><span class="sxs-lookup"><span data-stu-id="95899-125">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="95899-126">Om en statisk proxy krävs lägger du till en proxyparameter till kommandot ovan, `proxy_address:port` där det motsvarar proxyadressen och port:</span><span class="sxs-lookup"><span data-stu-id="95899-126">If a static proxy is required, add a proxy parameter to the above command, where `proxy_address:port` correspond to the proxy address and port:</span></span>

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="95899-127">Kontrollera att du använder samma proxyadress och port som konfigurerats i `/lib/system/system/mdatp.service` filen.</span><span class="sxs-lookup"><span data-stu-id="95899-127">Ensure that you use the same proxy address and port as configured in the `/lib/system/system/mdatp.service` file.</span></span> <span data-ttu-id="95899-128">Kontrollera proxykonfigurationen om det finns fel från kommandona ovan.</span><span class="sxs-lookup"><span data-stu-id="95899-128">Check your proxy configuration if there are errors from the above commands.</span></span>

> [!WARNING]
> <span data-ttu-id="95899-129">Den statiska proxyn kan inte konfigureras via en `HTTPS_PROXY` miljövariabel som gäller hela systemet.</span><span class="sxs-lookup"><span data-stu-id="95899-129">The static proxy cannot be configured through a system-wide `HTTPS_PROXY` environment variable.</span></span> <span data-ttu-id="95899-130">Kontrollera i stället att `HTTPS_PROXY` filen är rätt `/lib/system/system/mdatp.service` inställd.</span><span class="sxs-lookup"><span data-stu-id="95899-130">Instead, ensure that `HTTPS_PROXY` is properly set in the `/lib/system/system/mdatp.service` file.</span></span>

<span data-ttu-id="95899-131">Om du vill använda en statisk `mdatp.service` proxyserver måste filen ändras.</span><span class="sxs-lookup"><span data-stu-id="95899-131">To use a static proxy, the `mdatp.service` file must be modified.</span></span> <span data-ttu-id="95899-132">Se till att `#` inledningen tas bort för att ta bort den rad som följer `/lib/systemd/system/mdatp.service` från:</span><span class="sxs-lookup"><span data-stu-id="95899-132">Ensure the leading `#` is removed to uncomment the following line from `/lib/systemd/system/mdatp.service`:</span></span>

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

<span data-ttu-id="95899-133">Se också till att rätt statisk proxyadress fylls i för att ersätta `address:port` .</span><span class="sxs-lookup"><span data-stu-id="95899-133">Also ensure that the correct static proxy address is filled in to replace `address:port`.</span></span>

<span data-ttu-id="95899-134">Om filen är korrekt kan du prova att köra följande kommando i terminalen för att läsa in Defender för Endpoint på Linux och sprida inställningen:</span><span class="sxs-lookup"><span data-stu-id="95899-134">If this file is correct, try running the following command in the terminal to reload Defender for Endpoint on Linux and propagate the setting:</span></span>

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

<span data-ttu-id="95899-135">När anslutningstestet lyckas försöker du med ett annat anslutningstest från kommandoraden:</span><span class="sxs-lookup"><span data-stu-id="95899-135">Upon success, attempt another connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="95899-136">Kontakta kundsupport om problemet kvarstår.</span><span class="sxs-lookup"><span data-stu-id="95899-136">If the problem persists, contact customer support.</span></span>

## <a name="resources"></a><span data-ttu-id="95899-137">Resurser</span><span class="sxs-lookup"><span data-stu-id="95899-137">Resources</span></span>

- <span data-ttu-id="95899-138">Mer information om hur du konfigurerar produkten för att använda en statisk proxy finns i Konfigurera Microsoft Defender för [slutpunkt för statisk proxyidentifiering.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="95899-138">For more information about how to configure the product to use a static proxy, see [Configure Microsoft Defender for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).</span></span>
