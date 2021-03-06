---
title: Testa hur Microsoft Defender för slutpunktsfunktioner fungerar i granskningsläge
description: I granskningsläget kan du se hur Microsoft Defender för Slutpunkt skyddar dina enheter om det var aktiverat.
keywords: sårbarhetsskydd, granskning, granskning, läge, aktiverat, inaktiverat, testa, demo, utvärdera, lab
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 23de13e9a2b0fb02b95c9bb367c3fd99e11e89c8
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985102"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a>Minska testytans attackyta i Microsoft Defender för Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Som en del av organisationens säkerhetsteam kan du konfigurera funktioner för att minska attackytan i granskningsläge och se hur de kommer att fungera. I granskningsläge kan du aktivera:

- Regler för minskning av attackytan
- Exploateringsskydd
- Nätverksskydd
- Och kontrollerad mappåtkomst i granskningsläge

I granskningsläget kan du se vad som *skulle* ha hänt om du hade aktiverat funktionen.

Du kan aktivera granskningsläge när du testar hur funktionerna fungerar. Det här hjälper till att säkerställa att dina verksamhetsbaserade appar inte påverkas. Du kan också få en uppfattning om hur många misstänkta filändringsförsök som görs under en viss tidsperiod.

Funktionerna blockerar eller förhindrar inte att appar, skript eller filer ändras. Men i Windows händelseloggen visas händelser som om funktionerna är helt aktiverade. Med granskningsläge kan du granska händelseloggen och se vilken effekt funktionen skulle ha haft om den var aktiverad.

Du hittar de granskade posterna genom att gå till **Program och tjänster som**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Drift.**

Använd Defender för Slutpunkt för att få mer information om varje händelse, särskilt för att undersöka regler för att minska attackytan. Med Defender för slutpunktskonsolen kan du undersöka problem som en del av [scenarierna för aviseringstid och undersökning.](investigate-alerts.md)

Du kan aktivera granskningsläge med grupprincip-, PowerShell- och konfigurationstjänstleverantörer (CSP).

> [!TIP]
> Du kan också besöka webbplatsen Windows Defender Testground på [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att funktionerna fungerar och se hur de fungerar.

| Granskningsalternativ | Så här aktiverar du granskningsläge | Så här visar du händelser |
|---------|---------|---------|
| Granskning gäller för alla händelser | [Aktivera kontrollerad mappåtkomst](enable-controlled-folders.md) | [Kontrollerade mappåtkomsthändelser](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| Granskningen gäller för enskilda regler | [Aktivera regler för minskning av attackytan](enable-attack-surface-reduction.md) | [Händelser för att minska attackytan](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| Granskning gäller för alla händelser | [Aktivera nätverksskydd](enable-network-protection.md) | [Nätverksskyddshändelser](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| Granskning gäller för enskilda åtgärder | [Aktivera exploateringsskydd](enable-exploit-protection.md) | [Sårbarhetsskyddshändelser](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
