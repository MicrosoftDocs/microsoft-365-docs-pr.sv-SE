---
title: Microsoft Defender för slutpunkt på statisk proxyidentifiering i Linux
ms.reviewer: ''
description: Här beskrivs hur du konfigurerar Microsoft Defender för slutpunkt på Linux för statisk proxyidentifiering.
keywords: microsoft, defender, Microsoft Defender för slutpunkt, linux, installation, proxy
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
ms.openlocfilehash: 5a8e1cbda5f4361532c7fac0892be7ffe72f64ca
ms.sourcegitcommit: 8b79d276f71f22bcaeb150e78e35101cb1ae0375
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53114746"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a>Konfigurera Microsoft Defender för slutpunkt på Linux för statisk proxyidentifiering

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft Defender för Endpoint kan identifiera en proxyserver med `HTTPS_PROXY` miljövariabeln. Den här inställningen måste **konfigureras både** vid installationen och efter att produkten har installerats.

## <a name="installation-time-configuration"></a>Konfiguration av installationstid

Under installationen måste `HTTPS_PROXY` miljövariabeln skickas till pakethanteraren. Pakethanteraren kan läsa den här variabeln på något av följande sätt:

- Variabeln `HTTPS_PROXY` definieras `/etc/environment` i med följande rad:

  ```bash
  HTTPS_PROXY="http://proxy.server:port/"
  ```

- Variabeln `HTTPS_PROXY` definieras i den globala konfigurationen av package manager. I Ubuntu 18.04 kan du till exempel lägga till följande rad för `/etc/apt/apt.conf.d/proxy.conf` att:
  
  ```bash
  Acquire::https::Proxy "http://proxy.server:port/";
  ```

  > [!CAUTION]
  > Observera att två metoder ovan kan definiera proxyn som ska användas för andra program i systemet. Använd den här metoden med försiktighet eller bara om det är tänkt att vara en global konfiguration.
  
- Variabeln `HTTPS_PROXY` förberedas för installations- eller avinstallationskommandona. Med APT-pakethanteraren ska variabeln till exempel förberedas så här när du installerar Microsoft Defender för slutpunkt: 

  ```bash  
  HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
  ```

  > [!NOTE]
  > Lägg inte till sudo mellan miljövariabeldefinitionen och snabel, annars sprids inte variabeln.

`HTTPS_PROXY`Miljövariabeln kan på liknande sätt definieras vid avinstallation.

Observera att installationen och avinstallationen inte nödvändigtvis misslyckas om en proxy krävs men inte konfigureras. Telemetri skickas dock inte och åtgärden kan ta mycket längre tid på grund av timeout för nätverk.

## <a name="post-installation-configuration"></a>Efter installation
  
Efter installationen måste `HTTPS_PROXY` miljövariabeln definieras i Defender för slutpunktstjänstfilen. Det gör du genom att öppna `/lib/systemd/system/mdatp.service` den i en textredigerare medan du kör rotanvändaren. Du kan sedan sprida variabeln till tjänsten på ett av två sätt:

> [!NOTE]
> I CentOS eller RedHat Linux distributionss platsen för Endpoint-tjänstfilen är `/usr/lib/systemd/system/mdatp.service` .

- Ta bort från raden och `#Environment="HTTPS_PROXY=http://address:port"` ange din statiska proxyadress.

- Lägg till en linje `EnvironmentFile=/path/to/env/file` . Den här sökvägen kan `/etc/environment` peka på eller en anpassad fil, som alla måste lägga till följande rad:
  
  ```bash
  HTTPS_PROXY="http://proxy.server:port/"
  ```

Spara och stäng `mdatp.service` filen när du har redigerat den. Starta om tjänsten så att ändringarna kan tillämpas. I Ubuntu innefattar detta två kommandon:  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
