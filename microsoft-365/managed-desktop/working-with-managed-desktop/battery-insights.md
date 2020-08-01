---
title: Batteriinsikter
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f339fc98ea94c291c533045e9906f626f4b74e2a
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529845"
---
# <a name="battery-insights"></a>Batteriinsikter
Den här vyn innehåller energi-, batteri- och appanvändningsmått för dina Microsoft Managed Desktop-enheter. För dessa ändamål anses en app vara "i bruk" om den körs och i fokus.

Om du vill visa användningsdata väljer du fliken **Batteri.**

![Batteriruta: förväntad batteritid per enhetsmodell i övre vänstra, övre energikonsumenter (per app) i övre högra, statistiktabellen längst ned. Dokumentationslänk längst upp till höger.](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>Förväntad batteritid

I området **Förväntad batteritid** ger vi förutsägelser om den förväntade batteritiden för dina enheter, ordnade efter enhetsmodell.

> [!NOTE]
> Dessa data härleds från samplingsenergianvändning, användningstid och batterikapacitet från ett slumpmässigt <em>urval</em> av enheterna i microsoft managed desktop-distributionen som också rapporterar data.

Tabellen ger den förväntade batteritiden (i timmar), genomsnittlig batteritid för samma modeller i andra Microsoft Managed Desktop-distributioner och antalet enheter som rapporterar dessa data i din miljö. Sortera data genom att markera kolumnrubrikerna.



## <a name="top-energy-consumers"></a>De främsta energikonsumenterna

I området **Bästa energikonsumenter** hittar du de appar i din miljö som förbrukar mest energi under milliWatt-timmar (mWh). Apparna som visas är per specifik enhet, som du väljer i avsnittet **Förväntad batteritid** till vänster. Om du till exempel vill se förbrukningen per app för dina Microsoft Surface Book 2-enheter väljer du den raden i batteritidsområdet. Om du inte väljer någon modell är appförbrukningsdata som visas för alla appar som vi har data för tillsammans.

 För varje app visar färgade segment fördelningen av appens energianvändning mellan dessa kategorier:

- Cpu
- Visning
- Nätverk
- Annat

"Övrigt" kan omfatta energiförbrukning av en mängd olika källor, såsom diskaktivitet, mobilt bredband och energi som går förlorad för internt motstånd. 

Du kan filtrera den här vyn så att endast förgrundsappar, bakgrundsappar eller båda visas med hjälp av menyn längst upp till höger. Förgrundsappar är de som har haft användarinteraktion under de senaste 28 dagarna, till exempel att välja något med en mus.

## <a name="insights"></a>Insikter

**Insights-området** visar de tre största energikonsumenterna i CPU- och nätverkskategorierna. Dessa objekt förbrukar högre energi än genomsnittet jämfört med alla Microsoft Managed Desktop-distributioner. Vi visar inte visningsresursen eftersom den är starkt beroende av enhetsanvändningstid och skärmens inställningar för ljusstyrka. 

Välj listorna i kolumnen **Information** om du vill ha mer information.

## <a name="battery-optimization"></a>Batterioptimering

Windows 10 erbjuder många [enhetsinställningar](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) för att förbättra energiförbrukningen och öka batteritiden för dina Microsoft Managed Desktop-enheter. Vissa av dessa inställningar kan minska andra Windows-funktioner, så du måste också ta hänsyn till andra faktorer, till exempel enhetens roll i organisationen. Windows-stöd upprätthåller en lista över dessa [batteribesparingstips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).

Användare kan justera vissa inställningar på egen hand utan att behöva administratörshöjd eller stöd. Andra inställningar kräver support från organisationens IT-administratör.
