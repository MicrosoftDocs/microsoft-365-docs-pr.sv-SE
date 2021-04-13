---
title: Identifiera och blockera potentiellt oönskade program med Microsoft Defender ATP för Linux
description: Identifiera och blockera potentiellt oönskade program (PUA) med Microsoft Defender ATP för Linux.
keywords: microsoft, defender, atp, linux, pua, pus
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
ms.openlocfilehash: e7ac620896bad9adb73308223e28976e219d36d0
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687871"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-linux"></a>Identifiera och blockera potentiellt oönskade program med Microsoft Defender för Endpoint på Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Skyddsfunktionen för potentiellt oönskade program (PUA) i Defender för Endpoint för Linux kan identifiera och blockera PUA-filer på slutpunkter i nätverket.

Dessa program betraktas inte som virus, skadlig programvara eller andra typer av hot, men kan utföra åtgärder på slutpunkter som negativt påverkar deras prestanda eller användning. PUA kan också hänvisa till program som anses ha dåligt rykte.

Dessa program kan öka risken för att nätverket smittas med skadlig programvara, orsaka att skadlig programvara blir svårare att identifiera och kan slösa PÅ IT-resurser i att rensa program.

## <a name="how-it-works"></a>Så här fungerar det

Defender för Endpoint för Linux kan identifiera och rapportera PUA-filer. När PUA-filer konfigureras i blockeringsläge flyttas de till karantän.

När en PUA upptäcks på en slutpunkt behåller Defender för Endpoint för Linux ett register över smittan i hothistoriken. Historiken kan visualiseras från Microsoft Defender Säkerhetscenter-portalen eller `mdatp` kommandoradsverktyget. Hotnamnet innehåller ordet "Program".

## <a name="configure-pua-protection"></a>Konfigurera PUA-skydd

PUA-skydd i Defender för Slutpunkt för Linux kan konfigureras på något av följande sätt:

- **Av**: PUA-skydd är inaktiverat.
- **Granskning:** PUA-filer rapporteras i produktloggarna, men inte i Microsoft Defender Säkerhetscenter. Ingen information om smittan lagras i hothistoriken och ingen åtgärd vidtas av produkten.
- **Blockering:** PUA-filer rapporteras i produktloggarna och i Microsoft Defender Säkerhetscenter. En inspelning av smittan lagras i produktens hothistorik och åtgärder vidtas.

>[!WARNING]
>Som standard konfigureras PUA-skydd i **granskningsläge.**

Du kan konfigurera hur PUA-filer hanteras från kommandoraden eller från hanteringskonsolen.

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>Använd kommandoradsverktyget för att konfigurera PUA-skydd:

I terminalen kör du följande kommando för att konfigurera PUA-skydd:

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>Använd hanteringskonsolen för att konfigurera PUA-skydd:

I ditt företag kan du konfigurera PUA-skydd från en hanteringskonsol, till exempel a6 eller Ansible, på ungefär samma sätt som andra produktinställningar konfigureras. Mer information finns i avsnittet Inställningar [för hottyp](linux-preferences.md#threat-type-settings) i artikeln [Ange inställningar för Defender för slutpunkt för Linux.](linux-preferences.md)

## <a name="related-articles"></a>Relaterade artiklar

- [Ange inställningar för Defender för Endpoint för Linux](linux-preferences.md)
