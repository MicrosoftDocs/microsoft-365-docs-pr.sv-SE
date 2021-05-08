---
title: Felsöka problem med Microsoft Defender för slutpunkt på Android
description: Felsöka problem med Microsoft Defender för slutpunkt på Android
keywords: microsoft, defender, Microsoft Defender för slutpunkt, mde, android, molnet, anslutningar, kommunikation
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 18afd4aa160ec345839d23719d1b3fcce21654ec
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246362"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a>Felsöka problem med Microsoft Defender för slutpunkt på Android

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

Installera den senaste versionen och [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) från Google Play Store och försök igen

## <a name="sign-in-failed---invalid-license"></a>Inloggningen misslyckades – ogiltig licens

**Inloggningen misslyckades:** *Ogiltig licens. Kontakta administratören*

![Bild på inloggningen misslyckades, kontakta administratören](images/920e433f440fa1d3d298e6a2a43d4811.png)

**Meddelande:** *Ogiltig licens, kontakta administratören*

**Orsak:**

Du har inte Microsoft 365 licens kopplad, eller så har organisationen ingen licens för Microsoft 365 Enterprise prenumeration.

**Lösning:**

Kontakta administratören om du behöver hjälp.

## <a name="report-unsafe-site"></a>Rapportera osäker webbplats

Nätfiskewebbplatser utger sig för att vara betrodda webbplatser i syfte att skaffa personlig eller ekonomisk information. Gå till [sidan Ge feedback om nätverksskydd](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) om du vill rapportera en webbplats som kan vara en nätfiskewebbplats.

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
