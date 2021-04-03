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
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ce652d58be2d9ff28d82c088d5471a7bffdf6dc
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570978"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a>Testa hur Microsoft Defender för slutpunktsfunktioner fungerar i granskningsläge

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Du kan aktivera minskningsregler för attackytan, sårbarhetsskydd, nätverksskydd och kontrollerad mappåtkomst i granskningsläge. I granskningsläget kan du se vad som *skulle* ha hänt om du hade aktiverat funktionen.

Du kanske vill aktivera granskningsläge när du testar hur funktionerna fungerar i organisationen. Det här hjälper till att säkerställa att dina verksamhetsbaserade appar inte påverkas. Du kan också få en uppfattning om hur många misstänkta filändringsförsök som görs under en viss tidsperiod.

Funktionerna blockerar eller förhindrar inte att appar, skript eller filer ändras. Men i Windows-händelseloggen spelar du in händelser som om funktionerna var helt aktiverade. Med granskningsläge kan du granska händelseloggen och se vilken effekt funktionen skulle ha haft om den var aktiverad.

Du hittar de granskade posterna genom att gå till **Program och tjänster**  >  **Microsoft**  >  **Windows**  >  **Defender**  >  **Drift.**

Du kan använda Defender för Slutpunkt för att få mer information om varje händelse, särskilt för att undersöka regler för att minska attackytan. Med Defender för slutpunktskonsolen kan du undersöka problem som en del av [scenarierna för aviseringstid och undersökning.](investigate-alerts.md)

Du kan använda grupprinciper, PowerShell och konfigurationstjänster för att aktivera granskningsläge.

> [!TIP]
> Du kan också gå till Windows Defender Testground-webbplatsen [på demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att funktionerna fungerar och se hur de fungerar.

 **Granskningsalternativ** | **Så här aktiverar du granskningsläge** | **Så här visar du händelser**
|---------|---------|---------|
| Granskning gäller för alla händelser | [Aktivera kontrollerad mappåtkomst](enable-controlled-folders.md) | [Kontrollerade mappåtkomsthändelser](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| Granskningen gäller för enskilda regler | [Aktivera regler för minskning av attackytan](enable-attack-surface-reduction.md) | [Händelser för att minska attackytan](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| Granskning gäller för alla händelser | [Aktivera nätverksskydd](enable-network-protection.md) | [Nätverksskyddshändelser](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| Granskning gäller för enskilda åtgärder | [Aktivera exploateringsskydd](enable-exploit-protection.md) | [Sårbarhetsskyddshändelser](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a>Relaterade ämnen

* [Skydda enheter från exploatering](exploit-protection.md)
* [Minska attackytor med minskningsregler för attackytan](attack-surface-reduction.md)
* [Skydda ditt nätverk](network-protection.md)
* [Skydda viktiga mappar](controlled-folders.md)
