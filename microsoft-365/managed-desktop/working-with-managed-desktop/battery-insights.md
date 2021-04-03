---
title: Batteriinsikter
description: En rapport som visar data om förutsagd batterilivslängd och toppkraftskonsumenter
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579716"
---
# <a name="battery-insights"></a>Batteriinsikter
Den här vyn ger mått för energi, batteri och appanvändning för dina Microsoft Managed Desktop-enheter. För dessa ändamål anses en app vara "i bruk" om den körs och är i fokus.

Om du vill visa användningsdata väljer **du fliken** Batteri.

![Batterifönstret: prognostterat batterilivslängd per enhetsmodell i övre vänstra hörnet, de främsta energikonsumenterna (efter app) i det övre högra hörnet, insights-tabellen längst ned. Länken Dokumentation uppe till höger](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a>Förutsagd batteritid

I området **prognostiserade batteritiden** tillhandahåller vi prognoser för den förväntade batterilivslängden för dina enheter, ordnade efter enhetsmodell.

> [!NOTE]
> Dessa data härleds från sampling av energianvändning, <em></em> användningstid och batterikapacitet från ett slumpmässigt urval av enheter i distributionen av Microsoft Managed Desktop som även rapporterar data.

Tabellen ger förutsägelser om batterilivslängd (i timmar), genomsnittlig batteritid för samma modeller i andra distributioner av Microsoft Managed Desktop och antalet enheter som rapporterar dessa data i din miljö. Sortera data genom att markera kolumnrubrikerna.



## <a name="top-energy-consumers"></a>De främsta energikonsumenterna

I **området De största** energikonsumenterna hittar du de appar i din miljö som använder mest energi i snavaWatt-timmar (mWh). Apparna som visas visas per specifik enhet, som du väljer i **avsnittet Prognosterad batteritid** till vänster. Om du till exempel vill visa förbrukning per app för Microsoft Surface Book 2-enheter markerar du den raden i batterilivslängdsområdet. Om du inte väljer någon modell visas data om appanvändningen för alla appar som vi har data för gemensamt.

 För varje app visar färgade segment fördelningen av appens energianvändning bland dessa kategorier:

- CPU
- Visning
- Nätverk
- Annat

"Andra" kan inkludera energiförbrukning från olika källor, till exempel diskaktivitet, mobil bredbandsanvändning och energi som går förlorad till internt arbete. 

Du kan filtrera vyn så att den bara visar förgrundsappar, bakgrundsappar eller både och med hjälp av menyn längst upp till höger. Förgrundsappar är sådana som interagerat med användare under de senaste 28 dagarna, till exempel genom att markera något med en mus.

## <a name="insights"></a>Insikter

I **området** Insikter visas de tre främsta energikonsumenterna i cpu- och nätverkskategorierna. De här objekten använder en energi som är högre än genomsnittet jämfört med alla distributioner av Hanterad microsoft-dator. Vi visar inte visningsresursen eftersom den är beroende av enhetens användningstid och ljusstyrka. 

Välj listerna i kolumnen **Information** för mer information.

## <a name="battery-optimization"></a>Batterioptimering

I Windows 10 finns [flera olika enhetsinställningar](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) som förbättrar strömförsörjningen och ökar batterilivslängden för dina Microsoft Managed Desktop-enheter. Vissa av de här inställningarna kan minska andra Windows-funktioner, så du måste också tänka på andra faktorer, till exempel enhetens roll i organisationen. Windows-supporten har en lista över de här [tipsen för att spara batteri](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).

Användare kan justera vissa inställningar på egen hand utan att behöva höjd för administratör eller support. Andra inställningar kräver stöd från din organisations IT-administratör.
