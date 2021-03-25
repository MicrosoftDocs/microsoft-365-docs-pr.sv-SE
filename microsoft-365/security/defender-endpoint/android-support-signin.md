---
title: Felsöka problem med Microsoft Defender ATP för Android
description: Felsöka problem med Microsoft Defender ATP för Android
keywords: microsoft, defender, atp, android, moln, anslutning, kommunikation
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 444541c85f8f4416288dcebf4bbee2c65a33d3d2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164875"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-for-android"></a>Felsöka problem i Microsoft Defender för slutpunkt för Android

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

Vid registrering av en enhet kan du eventuellt se inloggningsproblem när appen har installerats.

Under introduktionen kan du stöta på inloggningsproblem när appen är installerad på din enhet.

I den här artikeln finns lösningar på inloggningsproblem.  

## <a name="sign-in-failed---unexpected-error"></a>Inloggningen misslyckades – oväntat fel
**Inloggningen misslyckades:** *Oväntat fel, försök senare*

![Bild på inloggningsfelet Oväntat fel](images/f9c3bad127d636c1f150d79814f35d4c.png)

**Meddelande:**

Oväntat fel, försök senare

**Orsak:**

Du har en äldre version av appen "Microsoft Authenticator" installerad på enheten.

**Lösning:**

Installera den senaste versionen och [av Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) från Google Play Store och försök igen

## <a name="sign-in-failed---invalid-license"></a>Inloggningen misslyckades – ogiltig licens

**Inloggningen misslyckades:** *Ogiltig licens. Kontakta administratören*

![Bild på inloggningen misslyckades, kontakta administratören](images/920e433f440fa1d3d298e6a2a43d4811.png)

**Meddelande:** *Ogiltig licens, kontakta administratören*

**Orsak:**

Du har inte tilldelats någon Microsoft 365-licens eller organisationen har ingen licens för Microsoft 365 Enterprise-prenumeration.

**Lösning:**

Kontakta administratören om du behöver hjälp.

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a>Nätfiskesidor blockeras inte på vissa OEM-enheter

**Gäller för:** Endast vissa OEM-maskiner

-   **Xiaomi**

Nätfiske och skadliga webbhot som upptäcks av Defender för Endpoint för Android blockeras inte på vissa Xiaomi-enheter. Följande funktioner fungerar inte på de här enheterna.

![Bild på webbplatsen som rapporterats som osäker](images/0c04975c74746a5cdb085e1d9386e713.png)


**Orsak:**

Xiaomi-enheter har en ny behörighetsmodell. Det förhindrar att Defender för Slutpunkt för Android visar popup-fönster medan det körs i bakgrunden.

Behörighet för Xiaomi-enheter: "Visa popup-fönster när de körs i bakgrunden".

![Bild på popup-inställning](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

**Lösning:**

Aktivera den behörighet som krävs på Xiaomi-enheter.

- Visa popup-fönster när du körs i bakgrunden.
