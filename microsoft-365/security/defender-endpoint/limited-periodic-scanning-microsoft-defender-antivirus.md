---
title: Aktivera den begränsade, periodiska genomsökningsfunktionen i Microsoft Defender Antivirus
description: Med begränsad regelbunden genomsökning kan du använda Microsoft Defender Antivirus förutom dina andra installerade AV-leverantörer
keywords: lps, limited, periodic, scan, scanning, compatibility, 3rd party, other av, disable
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 82c4bc1feec1556dc864558a843ed5e911c3ef3d
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764489"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>Använd begränsad regelbunden genomsökning i Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Begränsad regelbunden genomsökning är en särskild typ av identifiering och åtgärd av hot som kan aktiveras när du har installerat ett annat antivirusprogram på en Windows 10-enhet.

Det kan bara aktiveras i vissa situationer. Mer information om begränsad regelbunden genomsökning och hur Microsoft Defender Antivirus fungerar med andra antivirusprogram finns i [Kompatibilitet för Microsoft Defender Antivirus.](microsoft-defender-antivirus-compatibility.md)

**Microsoft rekommenderar inte att du använder den här funktionen i företagsmiljöer. Det här är en funktion som främst är avsedd för konsumenter.** Den här funktionen använder endast en begränsad delmängd av funktionerna i Microsoft Defender Antivirus för att identifiera skadlig programvara och kommer inte att kunna identifiera den största delen av skadlig programvara och eventuellt oönskad programvara. Dessutom är hanterings- och rapporteringsfunktionerna begränsade. Microsoft rekommenderar företag att välja sin primära antiviruslösning och använda den exklusivt.

## <a name="how-to-enable-limited-periodic-scanning"></a>Aktivera begränsad regelbunden genomsökning

Som standard aktiveras antivirusprogrammet Microsoft Defender på en Windows 10-enhet om det inte finns något annat antivirusprogram installerat, eller om den andra produkten är inaktiv, har gått ut eller inte fungerar korrekt.

Om Microsoft Defender Antivirus är aktiverat visas de vanliga alternativen för att konfigurera det på enheten:

![Windows-säkerhetsappen visar Microsoft Defender AV-alternativ, inklusive alternativ för genomsökning, inställningar och uppdateringsalternativ](images/vtp-wdav.png)

Om ett annat antivirusprogram är installerat och fungerar korrekt inaktiveras antivirusprogrammet Microsoft Defender. Windows-säkerhetsappen ändrar **avsnittet Skydd mot &** virus för att visa status om AV-produkten, och ge en länk till produktens konfigurationsalternativ.

Under en tredje parts AV-produkter visas en ny länk som **Microsoft Defender Antivirus-alternativ**. Om du klickar på länken expanderas växlingsknappen som aktiverar begränsad regelbunden genomsökning. Observera att det begränsade periodiska alternativet är en växlingsknapp för att aktivera eller inaktivera regelbunden genomsökning. 

Om du för skjut **reglaget** till På visas standardalternativen för Microsoft Defender AV under tredje parts AV-produkt. Det begränsade alternativet för regelbunden genomsökning visas längst ned på sidan.

## <a name="related-articles"></a>Relaterade artiklar

- [Konfigurera behavioruellt, heuristiskt och realtidsskydd](configure-protection-features-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)