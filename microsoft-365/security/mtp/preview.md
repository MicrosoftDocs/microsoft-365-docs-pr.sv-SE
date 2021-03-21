---
title: Förhandsgranskningsfunktioner i Microsoft 365 Defender
description: Läs mer om nya funktioner för Microsoft 365-säkerhet
keywords: förhandsgranska, nytt, m365 säkerhet, säkerhet, 365, funktioner
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2f5b1a289f55b7237606782afb8e8f5acf6788a2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918864"
---
# <a name="microsoft-365-defender-preview-features"></a>Förhandsgranskningsfunktioner i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> Förhandsversionerna tillhandahålls utan ett servicenivåavtal och det rekommenderas inte för produktionsarbetsbelastningar. Vissa funktioner kanske inte stöds eller kan ha begränsade funktioner.

**Gäller för:**
- Microsoft 365 Defender

Microsoft 365 Defender-tjänsten uppdateras hela tiden med nya funktionsförbättringar och funktioner.

Läs om nya funktioner i förhandsversionen av Microsoft 365 Defender och bli bland de första som kan prova kommande funktioner genom att aktivera förhandsversionen.

Mer information om nya funktioner som är allmänt tillgängliga finns i [Vad är nytt i Microsoft 365 Defender.](whats-new.md)

## <a name="required-permissions"></a>Behörighet som krävs

Konton som tilldelats följande Azure Active Directory-roller (Azure AD) kan aktivera förhandsversionen av Microsoft 365 Defender:

- Global administratör
- Säkerhetsadministratör
- Säkerhetsoperatör

## <a name="turn-on-preview-features"></a>Aktivera förhandsgranskningsfunktioner

Du har tillgång till kommande funktioner som du kan lämna feedback på för att förbättra den övergripande upplevelsen innan funktionerna blir tillgängliga i allmänhet.

Aktivera inställningen för förhandsversionen och var bland de första att prova kommande funktioner.

1. Välj **Inställningar** i navigeringsfönstret.
2. Välj **Microsoft 365 Defender**.
3. Välj **Förhandsgranskningsfunktioner** > **Aktivera förhandsgranskningsfunktioner**. 
4. Välj **Spara**.

Du vet att du har aktiverat förhandsgranskningsfunktionerna när kryssrutan **Aktivera förhandsgranskningsfunktioner** är markerad. 

## <a name="preview-features"></a>Förhandsgranskningsfunktioner

Följande funktioner och förbättringar är för närvarande tillgängliga för förhandsgranskning:

### <a name="improved-microsoft-365-security-center"></a>Förbättrat Microsoft 365 säkerhetscenter
Det förbättrade [Microsoft 365 Säkerhetscenter](https://security.microsoft.com) är nu tillgänglig i allmänt tillgänglig förhandsversion. Med den här nya upplevelsen kommer Defender för Endpoint, Defender för Office, 365 Microsoft 365 Defender och annat till Microsoft 365 säkerhetscenter. Det här är det nya hemmet för att hantera dina säkerhetskontroller. [Läs om de senaste](./overview-security-center.md).

- **[Microsoft 365 Defender rapport om hotanalyser](threat-analytics.md)** – Hotanalyser hjälper dig att svara på och minimera påverkan på aktiva attacker. Du kan också lära dig mer om attackförsök som blockeras av Microsoft 365 Defender-lösningar och vidta förebyggande åtgärder som minskar risken för ytterligare exponering och ökar motståndskraft. Som en del av den enhetliga säkerhetsupplevelsen finns nu hotanalyser tillgängliga för Microsoft Defender för Endpoint och Microsoft Defender för Office E5-licensinnehavare.
- **[Microsoft 365 Defender-API:er](api-overview.md)** – Microsoft 365 Defender-API:er på toppnivån gör att du kan automatisera arbetsflöden baserat på delade incidenter och avancerade tabeller för sökning. 
- **[Vidta åtgärder inom avancerad sökning](advanced-hunting-take-action.md)**– Innehåller snabbt hot eller hantera komprometterade tillgångar som du hittar vid avancerad [sökning.](advanced-hunting-overview.md)
- **[Schemareferens på portalen](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)**– Få information om avancerade schematabeller för sökning direkt i säkerhetscentret. Förutom tabell- och kolumnbeskrivningar innehåller den här referensen händelsetyper `ActionType` (värden) och exempelfrågor som stöds.
- **[Funktionen DeviceFromIP()](advanced-hunting-devicefromip-function.md)**– Få information om vilka enheter som har tilldelats en specifik IP-adress eller adresser vid ett visst tidsintervall.