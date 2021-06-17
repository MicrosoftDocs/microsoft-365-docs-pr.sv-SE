---
title: Utvärdera regler för minskning av attackytan
description: Se hur minskning av attackytor blockerar och förhindrar attacker med det anpassade demoverktyget.
keywords: Minskning av attackytan, hips, skyddssystem mot värdintrång, skyddsregler, anti-sårbarhet, antiutforskning, sårbarhet, smitta, utvärdera, testa, demo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.topic: article
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a5fa8e46de0a6561d3377ce77e38bd59aa97f3c4
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984730"
---
# <a name="evaluate-attack-surface-reduction-rules"></a>Utvärdera regler för minskning av attackytan

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Minskningsregler för attackytan hjälper till att förhindra åtgärder som vanligtvis används av skadlig programvara för att avslöja enheter eller nätverk. Minskningsregler för attackytor hjälper till att stänga av många av de vanliga instickspunkter som används av skadlig programvara och utpressningstrojaner.

Ange minskningsregler för attackytan för enheter som kör någon av följande utgåvor och versioner av Windows:

- Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) eller senare
- Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) eller senare
- Windows Server, [version 1803 (Halvårskanal)](/windows-server/get-started/whats-new-in-windows-server-1803) eller senare
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

> [!WARNING]
> Att aktivera regler för att minska attacktjänster i Windows Server 2016 kan leda till oväntade resultat och påverka serverprestandan. Vi rekommenderar inte att du aktiverar eller distribuerar minskningsregler för attackytan på plattformar som inte stöds.

Lär dig hur du utvärderar regler för att minska attackytan [genom att aktivera granskningsläge](audit-windows-defender.md) för att testa funktionen direkt i organisationen.

> [!TIP]
> Du kan också besöka webbplatsen med microsoft Defender för slutpunktsdemonstration på [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att funktionen fungerar och se hur den fungerar.

## <a name="use-audit-mode-to-measure-impact"></a>Använd granskningsläge för att mäta påverkan

Aktivera minskningsregler för attackytor i granskningsläge för att visa en post med appar som skulle ha blockerats om funktionen var helt aktiverad. Testa hur funktionen fungerar i din organisation för att säkerställa att den inte påverkar dina verksamhetsbaserade appar. Du kan även få en uppfattning om hur ofta reglerna kommer att branda under normal användning.

Om du vill aktivera en minskningsregel för attackytor i granskningsläge använder du följande PowerShell-cmdlet:

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

Var `<rule ID>` finns ett [GUID-värde för minskningsregeln för attackytan](attack-surface-reduction.md#attack-surface-reduction-rules).

Använd följande PowerShell-cmdlet för att aktivera alla tillagda minskningsregler för attackytor i granskningsläge:

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> Om du vill granska hur minskningsregler för attackytor fungerar i organisationen måste du använda ett hanteringsverktyg för att distribuera den här inställningen till enheter i dina nätverk.

Du kan också använda grupprincip-, Intune- eller MDM-konfigurationstjänstleverantörer (MDM) för att konfigurera och distribuera inställningen. Läs mer i huvudartikeln [om minskning av attackytor.](attack-surface-reduction.md)

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Granska händelser för att minska attackytan i Windows Loggboken

Om du vill granska appar som skulle ha blockerats öppnar du Loggboken och filtrerar efter Händelse-ID 1121 i Microsoft-Windows-Windows Defender/driftloggen. I följande tabell visas alla nätverksskyddshändelser.

Händelse-ID | Beskrivning
-|-
 5007 | Händelse när inställningar ändras
 1121 | Händelse när en minskningsregel för attackytan av fires i blockläge
 1122 | Händelse när en minskningsregel för attackytan i granskningsläge

## <a name="customize-attack-surface-reduction-rules"></a>Anpassa regler för minskning av attackytan

Under utvärderingen kanske du vill konfigurera varje regel individuellt eller exkludera vissa filer och processer från att utvärderas av funktionen.

Mer [information om hur du konfigurerar funktionen](customize-attack-surface-reduction.md) med hanteringsverktyg, bland annat Grupprincip och MDM-CSP-principer, finns i Anpassa minskningsregler för attackytor.

## <a name="see-also"></a>Se även

- [Minska attackytor med minskningsregler för attackytan](attack-surface-reduction.md)
- [Använda granskningsläge för att utvärdera Windows Defender](audit-windows-defender.md)
- [Vanliga frågor och svar för minskning av attackytan](attack-surface-reduction.md)
