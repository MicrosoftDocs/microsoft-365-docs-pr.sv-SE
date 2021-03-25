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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c9f8f78f4b3574bfc9848fe8d75f5077427d722b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187439"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-for-linux"></a>Felsöka molnanslutningsproblem för Microsoft Defender för Endpoint för Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a>Köra anslutningstestet

Om du vill testa om Defender för Slutpunkt för Linux kan kommunicera till molnet med de aktuella nätverksinställningarna kör du ett anslutningstest från kommandoraden:

```bash
mdatp connectivity test
```

förväntat utdata:

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

Om anslutningstestet misslyckas kontrollerar du om enheten har Internetanslutning och om någon av slutpunkterna som krävs av produkten [blockeras](microsoft-defender-endpoint-linux.md#network-connections) av en proxy eller brandvägg.

Fel med avkodningsfel 35 eller 60 anger avslag på certifikatkod. Kontrollera om anslutningen är under SSL- eller HTTPS-kontroll. I så fall lägger du till Microsoft Defender för Endpoint i listan över tillåtna slutpunkter.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a>Felsökningssteg för miljöer utan proxy eller med transparent proxy

Testa att en anslutning inte är blockerad i en miljö utan proxy eller med en transparent proxy genom att köra följande kommando i terminalen:

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

Utdata från det här kommandot bör se ut ungefär så här:

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a>Felsökningssteg för miljöer med statisk proxy

> [!WARNING]
> PAC, WPAD och autentiserad proxy går inte att använda. Se till att bara en statisk proxy eller transparent proxy används.
>
> SSL-proxy proxy och skärningspunkt stöds inte heller av säkerhetsskäl. Konfigurera ett undantag för SSL-kontroll och din proxyserver för att direkt överföra data från Defender för Endpoint för Linux till relevanta URL:er utan avlyssning. Om du lägger till ditt certifikat för avlyssning i det globala lagret tillåts inte avlyssning.

Om en statisk proxy krävs lägger du till en proxyparameter till kommandot ovan, `proxy_address:port` där det motsvarar proxyadressen och port:

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

Kontrollera att du använder samma proxyadress och port som konfigurerats i `/lib/system/system/mdatp.service` filen. Kontrollera proxykonfigurationen om det finns fel från kommandona ovan.

> [!WARNING]
> Den statiska proxyn kan inte konfigureras via en `HTTPS_PROXY` miljövariabel som gäller hela systemet. Kontrollera i stället att `HTTPS_PROXY` filen är rätt `/lib/system/system/mdatp.service` inställd.

Om du vill använda en statisk `mdatp.service` proxyserver måste filen ändras. Se till att `#` inledningen tas bort för att ta bort den rad som följer `/lib/systemd/system/mdatp.service` från:

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

Se också till att rätt statisk proxyadress fylls i för att ersätta `address:port` .

Om filen är korrekt kan du prova att köra följande kommando i terminalen för att läsa in Defender för Endpoint för Linux på nytt och sprida inställningen:

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

När anslutningstestet lyckas försöker du med ett annat anslutningstest från kommandoraden:

```bash
mdatp connectivity test
```

Kontakta kundsupport om problemet kvarstår.

## <a name="resources"></a>Resurser

- Mer information om hur du konfigurerar produkten för att använda en statisk proxy finns i Konfigurera Microsoft Defender för [slutpunkt för statisk proxyidentifiering.](linux-static-proxy-configuration.md)
