---
title: Identifiera och blockera potentiellt oönskade program med Microsoft Defender ATP för Mac
description: Identifiera och blockera potentiellt oönskade program (PUA) med Hjälp av Microsoft Defender ATP för Mac.
keywords: microsoft, defender, atp, mac, pua, pus
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
ms.openlocfilehash: 6e65e847403160d24eac04a553ca16a46314e33d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187427"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-mac"></a>Identifiera och blockera potentiellt oönskade program med Microsoft Defender för Slutpunkt för Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


Skyddsfunktionen för potentiellt oönskade program (PUA) i Microsoft Defender för Endpoint för Mac kan identifiera och blockera PUA-filer på slutpunkter i nätverket.

Dessa program betraktas inte som virus, skadlig programvara eller andra typer av hot, men kan utföra åtgärder på slutpunkter som negativt påverkar deras prestanda eller användning. PUA kan också hänvisa till program som anses ha dåligt rykte.

Dessa program kan öka risken för att nätverket smittas med skadlig programvara, orsaka att skadlig programvara blir svårare att identifiera och kan slösa PÅ IT-resurser i att rensa program.

## <a name="how-it-works"></a>Så här fungerar det

Microsoft Defender för Endpoint för Mac kan identifiera och rapportera PUA-filer. När PUA-filer konfigureras i blockeringsläge flyttas de till karantän.

När en PUA hittas på en slutpunkt visar Microsoft Defender för slutpunkt för Mac ett meddelande för användaren, om inte meddelanden har inaktiverats. Hotnamnet innehåller ordet "Program".

## <a name="configure-pua-protection"></a>Konfigurera PUA-skydd

PUA-skydd i Microsoft Defender för Slutpunkt för Mac kan konfigureras på något av följande sätt:

- **Av**: PUA-skydd är inaktiverat.
- **Granskning:** PUA-filer rapporteras i produktloggarna, men inte i Microsoft Defender Säkerhetscenter. Inget meddelande visas för användaren och ingen åtgärd vidtas av produkten.
- **Blockering:** PUA-filer rapporteras i produktloggarna och i Microsoft Defender Säkerhetscenter. Användaren får ett meddelande och en åtgärd vidtas av produkten.

>[!WARNING]
>Som standard konfigureras PUA-skydd i **granskningsläge.**

Du kan konfigurera hur PUA-filer hanteras från kommandoraden eller från hanteringskonsolen.

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>Använd kommandoradsverktyget för att konfigurera PUA-skydd:

I terminalen kör du följande kommando för att konfigurera PUA-skydd:

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>Använd hanteringskonsolen för att konfigurera PUA-skydd:

I ditt företag kan du konfigurera PUA-skydd från en hanteringskonsol, till exempel JAMF eller Intune, på ungefär samma sätt som andra produktinställningar konfigureras. Mer information finns i avsnittet Inställningar [för hottyp](mac-preferences.md#threat-type-settings) i avsnittet Ange [inställningar för Microsoft Defender för slutpunkt för Mac.](mac-preferences.md)

## <a name="related-topics"></a>Relaterade ämnen

- [Ange inställningar för Microsoft Defender för Slutpunkt för Mac](mac-preferences.md)
