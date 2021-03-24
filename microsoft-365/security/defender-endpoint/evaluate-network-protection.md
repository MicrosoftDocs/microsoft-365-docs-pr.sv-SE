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
# <a name="evaluate-network-protection"></a>Utvärdera nätverksskydd

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- - [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[Nätverksskydd](network-protection.md) förhindrar anställda från att använda ett program för att komma åt skadliga domäner som kan vara värdar för nätfiske, sårbarheter och annat skadligt innehåll på Internet.

Den här artikeln hjälper dig att utvärdera nätverksskydd genom att aktivera funktionen och vägleda dig till en testwebbplats. Webbplatserna i den här utvärderingsartikeln är inte skadliga. De är särskilt skapade webbplatser som utger sig för att vara skadliga. Webbplatsen replikerar beteendet som skulle inträffa om en användare besökte en skadlig webbplats eller domän.

> [!TIP]
> Du kan också besöka webbplatsen för Microsoft Defender Testground på [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) om du vill se hur andra skyddsfunktioner fungerar.

## <a name="enable-network-protection-in-audit-mode"></a>Aktivera nätverksskydd i granskningsläge

Aktivera nätverksskydd i granskningsläge för att se vilka IP-adresser och domäner som skulle ha blockerats. Du kan kontrollera att det inte påverkar verksamhetsbaserade appar eller få en uppfattning om hur ofta block uppstår.

1. Skriv **powershell** på Start-menyn, högerklicka på **Windows PowerShell och** välj Kör som **administratör**
2. Ange följande cmdlet:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a>Besök en (falsk) skadlig domän

1. Öppna Internet Explorer, Google Chrome eller valfri webbläsare.

1. Gå till [https://smartscreentestratings2.net](https://smartscreentestratings2.net).

Nätverksanslutningen tillåts och ett testmeddelande visas.

![Exempelmeddelande om att anslutningen är blockerad: IT-administratören orsakade att Windows-säkerhet blockerade den här nätverksanslutningen. Kontakta din IT-support.](/microsoft-365/security/defender-endpoint/images/np-notif)

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Granska nätverksskyddshändelser i Windows Loggboken

Om du vill granska appar som skulle ha blockerats öppnar du Loggboken och filtrerar efter Händelse-ID 1125 i Microsoft-Windows-Windows-Defender/Drift-loggen. I följande tabell visas alla nätverksskyddshändelser.

| Händelse-ID | Ange/källa | Beskrivning |
|-|-|-|
|5007 | Windows Defender (drift) | Händelse när inställningar ändras |
|1125 | Windows Defender (drift) | Händelse när en nätverksanslutning granskas |
|1126 | Windows Defender (drift) | Händelse när en nätverksanslutning blockeras |

## <a name="see-also"></a>Se även

* [Nätverksskydd](network-protection.md)
* [Aktivera nätverksskydd](enable-network-protection.md)
* [Felsöka nätverksskydd](troubleshoot-np.md)
