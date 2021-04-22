---
title: Undersök Microsoft Defender för slutpunktsdomäner
description: Använd undersökningsalternativen för att se om enheter och servrar har kommunicerat med skadliga domäner.
keywords: undersöker domän, domän, skadlig domän, Microsoft Defender för slutpunkt, avisering, URL
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 7826229ba67384137c033745a5b85e557fc9c4a7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933475"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Undersöka en domän som är kopplad till en Microsoft Defender för slutpunktsavisering

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink) 

Undersök en domän för att se om enheter och servrar i företagsnätverket har kommunicerat med en känd skadlig domän.

Du kan undersöka en domän med hjälp av sökfunktionen eller genom att klicka på en domänlänk från **enhetens tidslinje.**

Du kan se information från följande avsnitt i URL-vyn:

- URL-information, Kontakter, Namnservrar
- Aviseringar relaterade till url:en 
- URL i organisationen
- Senaste observerade enheter med URL

## <a name="url-worldwide"></a>URL globalt

I **det globala** avsnittet finns url-adressen, en länk till mer information om Whois, antalet relaterade öppna incidenter och antalet aktiva aviseringar.

## <a name="incident"></a>Incident

På **incidentkortet** visas ett stapeldiagram med alla aktiva aviseringar för incidenter under de senaste 180 dagarna.

## <a name="prevalence"></a>Endeprenad

Kortet **Visitkort** innehåller information om hur URL:en inom organisationen ska ut specificeras, under en angiven tidsperiod.

Även om standardtiden är de senaste 30 dagarna kan du anpassa intervallet genom att välja nedåtpilen i hörnet av kortet. Det kortaste tillgängliga intervallet är för den senaste dagen, medan det längsta intervallet är under de senaste 6 månaderna.

## <a name="alerts"></a>Varningar

Fliken **Aviseringar** ger en lista med aviseringar som är associerade med URL:en. Tabellen som visas här är en filtrerad version av aviseringarna som visas på skärmen Aviseringskö, med endast aviseringar kopplade till domänen, deras allvarlighetsgrad, status, tillhörande incident, klassificering, undersökningstillstånd med mera.

Fliken Aviseringar kan justeras för att visa mer eller mindre information genom att välja **Anpassa** kolumner på åtgärdsmenyn ovanför kolumnrubrikerna. Du kan också justera antalet objekt som visas genom att välja **objekt per sida** på samma meny.

## <a name="observed-in-organization"></a>Observerad i organisationen

På **fliken Observerad i** organisationen finns en kronologisk vy över händelser och tillhörande aviseringar som har observerats på WEBBADRESSen. Den här fliken innehåller en tidslinje och en anpassningsbar tabell med händelseinformation, till exempel tid, enhet och en kort beskrivning av vad som har hänt. 

Du kan visa händelser från olika tidsperioder genom att ange datumen i textfälten ovanför tabellrubrikerna. Du kan också anpassa tidsperioden genom att markera olika områden på tidslinjen.

**Undersöka en domän:**

1. Välj **URL** i **sökfältets** nedrullningsbar meny.
2. Ange URL-adressen i **sökfältet.**
3. Klicka på sökikonen eller tryck på **Retur.** Information om URL:en visas. Obs! Sökresultat returneras bara för URL:er som observeras i kommunikation från enheter i organisationen.
4. Använd sökfiltren för att definiera sökvillkoren. Du kan också använda sökrutan för tidslinjen för att filtrera sökresultaten för alla enheter i organisationen som observerats för kommunikation med URL-adressen, filen som är kopplad till kommunikationen och det senaste observerade datumet.
5. Om du klickar på något av enhetsnamnen visas enhetens vy, där du kan fortsätta undersöka rapporterade aviseringar, beteenden och händelser.

## <a name="related-topics"></a>Relaterade ämnen
- [Visa och ordna kön Microsoft Defender för slutpunktsaviseringar](alerts-queue.md)
- [Hantera Microsoft Defender för slutpunktsaviseringar](manage-alerts.md)
- [Undersöka Microsoft Defender för slutpunktsaviseringar](investigate-alerts.md)
- [Undersöka en fil som är kopplad till en Microsoft Defender för slutpunktsavisering](investigate-files.md)
- [Undersöka enheter i listan Microsoft Defender för slutpunktsenheter](investigate-machines.md)
- [Undersöka en IP-adress som är kopplad till en Microsoft Defender för Slutpunktsavisering](investigate-ip.md)
- [Undersöka ett användarkonto i Microsoft Defender för Endpoint](investigate-user.md)
