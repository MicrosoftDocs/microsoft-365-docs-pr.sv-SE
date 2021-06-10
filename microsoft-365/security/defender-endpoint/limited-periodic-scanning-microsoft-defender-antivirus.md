---
title: Aktivera den begränsade regelbunden Microsoft Defender Antivirus genomsökningsfunktionen
description: Med begränsad regelbunden genomsökning kan du Microsoft Defender Antivirus förutom dina andra installerade AV-leverantörer
keywords: lps, limited, periodic, scan, scanning, compatibility, 3rd party, other av, disable
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: b2ae56c0f67501eb8603d5d28c4ed0c4af01a8c9
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274607"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>Använd begränsad periodisk genomsökning i Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Begränsad regelbunden genomsökning är en särskild typ av identifiering och åtgärd av hot som kan aktiveras när du har installerat en annan antivirusprodukt på en annan Windows 10 enhet.

Det kan bara aktiveras i vissa situationer. Mer information om begränsad regelbunden genomsökning och hur Microsoft Defender Antivirus fungerar med andra antivirusprogram finns [i Microsoft Defender Antivirus kompatibilitet.](microsoft-defender-antivirus-compatibility.md)

**Microsoft rekommenderar inte att du använder den här funktionen i företagsmiljöer. Det här är en funktion som främst är avsedd för konsumenter.** Den här funktionen använder endast en begränsad delmängd av Microsoft Defender Antivirus-funktionerna för att identifiera skadlig programvara och kommer inte att kunna identifiera den största delen av skadlig programvara och potentiellt oönskad programvara. Dessutom är hanterings- och rapporteringsfunktionerna begränsade. Microsoft rekommenderar företag att välja sin primära antiviruslösning och använda den exklusivt.

## <a name="how-to-enable-limited-periodic-scanning"></a>Aktivera begränsad regelbunden genomsökning

Som standard aktiveras Microsoft Defender Antivirus på en Windows 10-enhet om det inte finns någon annan antivirusprodukt installerad, eller om den andra produkten är inaktiv, har gått ut eller inte fungerar som den ska.

Om Microsoft Defender Antivirus har aktiverats visas de vanliga alternativen för att konfigurera den på den enheten:

![Windows-säkerhet-app som visar Microsoft Defender AV-alternativ, inklusive alternativ för genomsökning, inställningar och uppdateringsalternativ](images/vtp-wdav.png)

Om ett annat antivirusprogram är installerat och fungerar som det ska Microsoft Defender Antivirus av sig själv. Appen Windows-säkerhet ändrar avsnittet **Skydd mot &** virus för att visa status om av-produkten, och ge en länk till produktens konfigurationsalternativ.

Under eventuella avI-produkter från tredje part visas en ny länk **Microsoft Defender Antivirus alternativ**. Om du klickar på länken expanderas växlingsknappen som aktiverar begränsad regelbunden genomsökning. Observera att det begränsade periodiska alternativet är en växlingsknapp för att aktivera eller inaktivera regelbunden genomsökning. 

Om du för skjut **reglaget** till På visas standardalternativen för Microsoft Defender AV under tredje parts AV-produkt. Det begränsade alternativet för regelbunden genomsökning visas längst ned på sidan.

## <a name="related-articles"></a>Relaterade artiklar

- [Konfigurera skydd för beteende, heuristisk och realtid](configure-protection-features-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus i Windows 10](microsoft-defender-antivirus-in-windows-10.md)