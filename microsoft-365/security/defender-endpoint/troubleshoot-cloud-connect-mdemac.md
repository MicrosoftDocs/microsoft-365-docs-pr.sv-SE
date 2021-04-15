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
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Felsöka molnanslutningsproblem för Microsoft Defender för slutpunkt i macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plattform** macOS

I det här avsnittet beskrivs hur du felsöker molnanslutningsproblem för Microsoft Defender för slutpunkt på macOS.

## <a name="run-the-connectivity-test"></a>Köra anslutningstestet
Testa om Defender för slutpunkt på Mac kan kommunicera till molnet med de aktuella nätverksinställningarna genom att köra ett anslutningstest från kommandoraden:

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
> Autentiserad proxy. Se till att endast PAC, WPAD eller en statisk proxy används. SSL-proxy proxy och skärningspunkt stöds inte heller av säkerhetsskäl. Konfigurera ett undantag för SSL-kontroll och proxyservern för att direkt överföra data från Microsoft Defender för Slutpunkt i macOS till relevanta URL:er utan avlyssning. Om du lägger till ditt certifikat för avlyssning i det globala lagret tillåts inte avlyssning.
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
