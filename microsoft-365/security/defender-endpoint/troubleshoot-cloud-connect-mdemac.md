---
title: Felsöka problem med molnanslutning för Microsoft Defender för Endpoint för Mac
description: I det här avsnittet beskrivs hur du felsöker molnanslutningsproblem för Microsoft Defender för Endpoint för Mac
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
ms.openlocfilehash: e522495fa86b5a71faa9f25cc863c29cc5d124c0
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476719"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Felsöka problem med molnanslutning för Microsoft Defender för Endpoint för Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plattform** macOS

I det här avsnittet beskrivs hur du felsöker molnanslutningsproblem för Microsoft Defender för Endpoint för Mac.

## <a name="run-the-connectivity-test"></a>Köra anslutningstestet
Testa om Defender för Slutpunkt för Mac kan kommunicera till molnet med de aktuella nätverksinställningarna genom att köra ett anslutningstest från kommandoraden:

```Bash
mdatp connectivity test
```

förväntat utdata:
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

Om anslutningstestet misslyckas kontrollerar du om enheten har Internetanslutning och om någon av slutpunkterna som krävs av produkten [blockeras](microsoft-defender-endpoint-mac.md#network-connections) av en proxy eller brandvägg.

Fel med avrullningsfel 35 eller 60 anger avvisning av certifikat som anger ett potentiellt problem med SSL- eller HTTPS-kontrollen. Se anvisningarna nedan om KONFIGURATION av SSL-kontroll.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a>Felsökningssteg för miljöer utan proxy eller med autoconfig (PAC) eller med Web Proxy Autodiscovery Protocol (WPAD)
Använd följande procedur för att testa att en anslutning inte blockeras i en miljö utan proxy eller med autoconfig proxy (PAC) eller med WPAD (Web Proxy Autodiscovery Protocol).

Om en proxy eller brandvägg blockerar anonym trafik kontrollerar du att anonym trafik tillåts i tidigare angivna URL:er.

> [!WARNING]
> Autentiserad proxy. Se till att endast PAC, WPAD eller en statisk proxy används. SSL-proxy proxy och skärningspunkt stöds inte heller av säkerhetsskäl. Konfigurera ett undantag för SSL-kontroll och proxyservern för att direkt överföra data från Microsoft Defender för Endpoint för Mac till relevanta URL:er utan avlyssning. Om du lägger till ditt certifikat för avlyssning i det globala lagret tillåts inte avlyssning.
Så här testar du att en anslutning inte är blockerad: Öppna en webbläsare som Microsoft Edge för Mac eller Safari och https://x.cp.wd.microsoft.com/api/report https://cdn.x.cp.wd.microsoft.com/ping .

Du kan också köra följande kommando i Terminal:

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

Utdata från det här kommandot bör se ut ungefär så här:
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
