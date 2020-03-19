---
title: Batteriinsikter
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 434f62d5ddfc8bc75c54de422aafc8c6325c4086
ms.sourcegitcommit: 1c445d68e54ca4249024ca4bb72460dd6fac0a2d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42810766"
---
# <a name="battery-insights"></a>Batteriinsikter
Den här vyn innehåller energi-, batteri- och appanvändningsmått för dina Microsoft Managed Desktop-enheter. För dessa ändamål anses en app vara "i bruk" om den körs och i fokus.

Om du vill visa användningsdata väljer du fliken **Batteri.**

![Batteriruta: förväntad batteritid per enhetsmodell i övre vänstra, övre energikonsumenter (efter app) i övre högra, insikter tabell över botten. Dokumentationslänk längst upp till höger.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>Förväntad batteritid

I området **Förväntad batteritid** ger vi förutsägelser om den förväntade batteritiden för dina enheter, ordnade efter enhetsmodell.

> [!NOTE]
> Dessa data härleds från samplingsenergianvändning, användningstid och batterikapacitet från ett slumpmässigt <em>urval</em> av enheterna i microsofts hanterade skrivbordsdistribution som också rapporterar data.

Tabellen ger den förväntade batteritiden (i timmar), genomsnittlig batteritid för samma modeller i andra Microsoft Managed Desktop-distributioner och antalet enheter som rapporterar dessa data i din miljö. Sortera data genom att markera kolumnrubrikerna.



## <a name="top-energy-consumers"></a>De främsta energikonsumenterna

I området **Bästa energikonsumenter** hittar du de appar i din miljö som förbrukar mest energi under milliWatt-timmar (mWh). Apparna som visas är per specifik enhet, som du väljer i avsnittet **Förväntad batteritid** till vänster. Om du till exempel vill se förbrukningen per app för dina Microsoft Surface Book 2-enheter väljer du den raden i batteritidsområdet. Om du inte väljer någon modell är appförbrukningsdata som visas för alla appar som vi har data för gemensamt.

 För varje app visar färgade segment fördelningen av appens energianvändning mellan dessa kategorier:

- Cpu
- Visa
- Nätverk
- Andra

"Andra" kan omfatta energiförbrukning av en mängd olika källor, såsom diskaktivitet, mobilt bredband och energi som går förlorad för internt motstånd. 

Du kan filtrera den här vyn så att endast förgrundsappar, bakgrundsappar eller båda visas med hjälp av menyn längst upp till höger. Förgrundsappar är de som har haft användarinteraktion under de senaste 28 dagarna, till exempel att välja något med en mus.

## <a name="insights"></a>Insikter

**Insights-området** visar de tre största energikonsumenterna i CPU- och nätverkskategorierna. Dessa objekt förbrukar högre energi än genomsnittet jämfört med alla Microsoft Managed Desktop-distributioner. Vi visar inte visningsresursen eftersom den är starkt beroende av enhetens användningstid och skärmens inställningar för ljusstyrka. 

Välj listorna i kolumnen **Information** om du vill ha mer information.

## <a name="battery-optimization"></a>Batterioptimering

Windows 10 erbjuder många [enhetsinställningar](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) för att förbättra energiförbrukningen och öka batteritiden för dina Microsoft Managed Desktop-enheter. Vissa av dessa inställningar kan minska andra Windows-funktioner, så du måste också ta hänsyn till andra faktorer, till exempel enhetens roll i organisationen. Windows-stöd upprätthåller en lista över dessa [batteribesparingstips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).

Användare kan justera vissa inställningar på egen hand utan att behöva administratörshöjd eller stöd. Andra inställningar kräver support från organisationens IT-administratör.
