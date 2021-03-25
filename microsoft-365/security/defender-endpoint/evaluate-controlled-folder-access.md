---
title: Utvärdera kontrollerad mappåtkomst
description: Se hur reglerad mappåtkomst kan skydda filer från att ändras av skadliga program.
keywords: Sårbarhetsskydd, windows 10, windows defender, utpressningstrojaner, skydda, utvärdera, testa, demo, prova
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: e965e1a882dadfb565231074165507a6727b45c1
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218754"
---
# <a name="evaluate-controlled-folder-access"></a>Utvärdera kontrollerad mappåtkomst

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


[Kontrollerad mappåtkomst](controlled-folders.md) är en funktion som skyddar dokument och filer från att ändras av misstänkta eller skadliga program. Reglerad mappåtkomst stöds i Windows Server 2019- och Windows 10-klienter.

Det är särskilt användbart för att skydda mot [utpressningstrojaner](https://www.microsoft.com/wdsi/threats/ransomware) som försöker kryptera dina filer och hålla kvar dem.

I den här artikeln får du hjälp att utvärdera kontrollerad mappåtkomst. Här förklaras hur du aktiverar granskningsläge så att du kan testa funktionen direkt i organisationen.

> [!TIP]
> Du kan också besöka webbplatsen med microsoft Defender för slutpunktsdemonstration på [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) för att bekräfta att funktionen fungerar och se hur den fungerar.

## <a name="use-audit-mode-to-measure-impact"></a>Använd granskningsläge för att mäta påverkan

Aktivera kontrollerad mappåtkomst i granskningsläge för att se en post över vad *som skulle* ha hänt om det var helt aktiverat. Testa hur funktionen fungerar i din organisation för att säkerställa att den inte påverkar dina verksamhetsbaserade appar. Du kan också få en uppfattning om hur många misstänkta filändringsförsök som vanligtvis görs under en viss tidsperiod.

Om du vill aktivera granskningsläge använder du följande PowerShell-cmdlet:

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> Om du vill granska hur kontrollerad mappåtkomst fungerar i organisationen måste du använda ett hanteringsverktyg för att distribuera den här inställningen till enheter i dina nätverk.
Du kan också använda Grupprincip, Intune, MDM (Mobile Device Management) eller Microsoft Endpoint Manager för att konfigurera och distribuera inställningen enligt beskrivningen i avsnittet huvudkontrollerad [mappåtkomst.](controlled-folders.md)

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Granska styrda mappåtkomsthändelser i Windows Loggboken

Följande mappåtkomsthändelser som kontrolleras visas i Windows Loggboken under mappen Microsoft/Windows/Windows Defender/Drift.

Händelse-ID | Beskrivning
-|-
 5007 | Händelse när inställningar ändras
 1124 | Granskad kontrollerad mappåtkomsthändelse
 1123 | Blockerad reglerad mappåtkomsthändelse

> [!TIP]
> Du kan konfigurera en prenumeration [på vidarebefordran av händelser så](https://docs.microsoft.com/windows/win32/wec/setting-up-a-source-initiated-subscription) att loggarna samlas in centralt. 

## <a name="customize-protected-folders-and-apps"></a>Anpassa skyddade mappar och appar

Under utvärderingen kanske du vill lägga till i listan med skyddade mappar eller tillåta att vissa appar ändrar filer.

Se [Skydda viktiga mappar med kontrollerad mappåtkomst](controlled-folders.md) för att konfigurera funktionen med hanteringsverktyg, inklusive grupprinciper, PowerShell- och MDM-konfigurationstjänstleverantörer (CSP).

## <a name="see-also"></a>Se även

* [Skydda viktiga mappar med kontrollerad mappåtkomst](controlled-folders.md)
* [Utvärdera Microsoft Defender för slutpunkt](evaluate-mde.md)
* [Använda granskningsläge](audit-windows-defender.md)
