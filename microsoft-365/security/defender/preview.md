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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8ad5ffe2b175a8f7a42b2fad353fcde13a60cfec
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730530"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Förhandsgranskningsfunktioner i Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> Förhandsversionerna tillhandahålls utan ett servicenivåavtal och det rekommenderas inte för produktionsarbetsbelastningar. Vissa funktioner kanske inte stöds eller kan ha begränsade funktioner.

**Gäller för:**
- Microsoft 365 Defender

Tjänsten Microsoft 365 Defender uppdateras hela tiden med nya funktionsförbättringar och funktioner.

Lär dig mer om de nya funktionerna i Microsoft 365 Defender förhandsversion och bli bland de första att prova kommande funktioner genom att aktivera förhandsgranskningen.

Mer information om nya funktioner som är allmänt tillgängliga finns i [Vad är nytt](whats-new.md)i Microsoft 365 Defender .

## <a name="required-permissions"></a>Behörighet som krävs

Konton som tilldelats Azure Active Directory (Azure AD) roller kan aktivera Microsoft 365 Defender Preview-funktioner:

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

- **[Direktuppspelnings-API](../defender-endpoint/raw-data-export.md)** – Microsoft 365 Defender har stöd för direktuppspelning av alla händelser som är tillgängliga via Avancerad sökning till ett evenemangsnav och/eller Azure-lagringskonto.
- **[Microsoft 365 Defender-API:er](api-overview.md)** – Defender-API:er på den översta nivån Microsoft 365 i Defender-API:er kan du automatisera arbetsflöden baserat på delade incidenter och avancerade tabeller för sökning. 
- **[Vidta åtgärder inom avancerad sökning](advanced-hunting-take-action.md)** – innehåller snabbt hot eller hantera komprometterade tillgångar som du hittar vid avancerad [sökning.](advanced-hunting-overview.md)
- **[Schemareferens i portalen](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** – Få information om avancerade schematabeller för sökning direkt i säkerhetscentret. Förutom tabell- och kolumnbeskrivningar innehåller den här referensen händelsetyper `ActionType` (värden) och exempelfrågor som stöds.
- **[Funktionen DeviceFromIP()](advanced-hunting-devicefromip-function.md)** – Få information om vilka enheter som har tilldelats en specifik IP-adress eller adresser vid ett visst tidsintervall.
