---
title: Introducera icke-Windows-enheter till Microsoft Defender för slutpunktstjänsten
description: Konfigurera enheter som Windows enheter så att de kan skicka sensordata till Microsoft Defender för slutpunktstjänsten.
keywords: onboard non-Windows-enheter, macos, linux, enhetshantering, konfigurera Microsoft Defender för slutpunktsenheter
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 777f5f63c4739f277ec24f826bc8a61a226fb65f
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339676"
---
# <a name="onboard-non-windows-devices"></a>Introducera icke-Windows-enheter

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**Plattformar**
- macOS
- Linux

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

Defender för Endpoint tillhandahåller en centraliserad säkerhetsoperationer för både Windows och icke-Windows plattformar. Du kan se aviseringar från olika operativsystem som stöds (OS) i Microsoft 365 Defender och bättre skydda organisationens nätverk. 

Du måste känna till exakt vilka Linux-distributioner och macOS-versioner som är kompatibla med Defender för Endpoint för att integreringen ska fungera. Mer information finns i:
- [Systemkrav för Microsoft Defender för Slutpunkt på Linux](microsoft-defender-endpoint-linux.md#system-requirements)  
- [Microsoft Defender för Slutpunkt på systemkrav för macOS](microsoft-defender-endpoint-mac.md#system-requirements).

## <a name="onboarding-non-windows-devices"></a>Onboarding non-Windows-enheter
Du måste vidta följande steg för att registrera icke-Windows enheter:
1. Välj önskad onboardingmetod:

   - För macOS-enheter kan du välja att registrera dig via Microsoft Defender för Endpoint eller via en tredjepartslösning. Mer information finns i [Microsoft Defender för slutpunkt på Mac.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)

   - För andra enheter som Windows enheter väljer **du Onboard icke-Windows-enheter via tredjepartsintegrering.**   
    1. Välj Partner med **interoperabilitet i**  >  **navigeringsfönstret.** Kontrollera att tredjepartslösningen visas.
    2. På fliken **Partnerprogram** väljer du den partner som stöder dina icke-Windows enheter.
    3. Välj **Öppna partnersida** för att öppna partnerns sida. Följ instruktionerna på sidan.
    4. När du har skapat ett konto eller prenumererat på partnerlösningen bör du komma till ett steg där en global administratör för klientorganisationen i organisationen uppmanas att acceptera en begäran om behörighet från partnerprogrammet. Läs begäran om behörighet noga så att den stämmer överens med den tjänst du kräver. 

        
2. Kör ett identifieringstest genom att följa anvisningarna för tredjepartslösningen.

## <a name="offboard-non-windows-devices"></a>Offboard-enheter som Windows enheter

1. Följ dokumentationen från tredje part för att koppla bort tredjepartslösningen från Microsoft Defender för Endpoint.

2. Ta bort behörigheter för tredjepartslösningen i Azure AD-klientorganisationen.
   1. Logga in på [Azure-portalen](https://portal.azure.com).
   2. Välj **Azure Active Directory > Företagsprogram**.
   3. Välj det program du vill ta bort.
   4. Välj knappen **Ta** bort.


## <a name="related-topics"></a>Relaterade ämnen
- [Registrera Windows 10-enheter](configure-endpoints.md)
- [Onboard servers](configure-server-endpoints.md)
- [Konfigurera inställningar för proxy- och Internetanslutning](configure-proxy-internet.md)
- [Felsökning av problem med introduktion till Microsoft Defender för slutpunkt](troubleshoot-onboarding.md)
