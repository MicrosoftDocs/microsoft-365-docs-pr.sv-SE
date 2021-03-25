---
title: Visa och ordna listan med Microsoft Defender ATP-enheter
description: Läs mer om de tillgängliga funktioner som du kan använda i listan Enheter, till exempel sortering, filtrering och export av listan för att förbättra undersökningar.
keywords: sortera, filtrera, exportera, CSV, enhetsnamn, domän, senast sedd, intern IP, hälsotillstånd, aktiva varningar, aktiv identifiering av skadlig kod, hotkategori, granska varningar, nätverk, anslutning, skadlig programvara, typ, lösenords stjäla, utpressningstrojan, sårbarhet, hot, allmän skadlig kod, oönskad programvara
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 01ad9f92299cd9d1b4a723bdec54f86f32ca8274
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076585"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a>Visa och ordna listan Microsoft Defender för slutpunktsenheter

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


I **listan Enheter** visas en lista med de enheter i nätverket där aviseringar har genererats. Som standard visar kön enheter som har setts de senaste 30 dagarna.  

Du får snabbt tillgång till information som domän, risknivå, OS-plattform och annan information för enkel identifiering av enheter som är mest riskfyllda.

Du kan välja mellan flera olika alternativ om du vill anpassa enheternas listvy. I det övre navigeringsfältet kan du:

- Lägga till eller ta bort kolumner
- Exportera hela listan i CSV-format
- Välj hur många objekt som ska visas per sida
- Använda filter

Under registreringsprocessen fylls **listan Enheter gradvis i** med enheter när de börjar rapportera sensordata. Använd den här vyn för att spåra dina inbyggda slutpunkter när de publiceras online, eller ladda ned hela slutpunktslistan som en CSV-fil för offlineanalys.

>[!NOTE]
> Om du exporterar enhetslistan innehåller den alla enheter i organisationen. Det kan ta mycket tid att ladda ned, beroende på hur stor organisationen är. När du exporterar listan i CSV-format visas data på ett ofiltrerat sätt. CSV-filen innehåller alla enheter i organisationen, oavsett filtrering som används i själva vyn.

![Bild på listan över enheter med lista över enheter](images/device-list.png)

## <a name="sort-and-filter-the-device-list"></a>Sortera och filtrera enhetslistan

Du kan använda följande filter för att begränsa listan med aviseringar och få en mer fokuserad vy.

### <a name="risk-level"></a>Risknivå

Risknivån återspeglar den övergripande riskbedömningen av enheten baserat på en kombination av faktorer, inklusive typer och allvarlighetsgrad för aktiva varningar på enheten. Att lösa aktiva aviseringar, godkänna åtgärdsaktiviteter och dölja efterföljande aviseringar kan sänka risknivån.

### <a name="exposure-level"></a>Exponeringsnivå

Exponeringsnivån återspeglar enhetens aktuella exponering baserat på den kumulativa effekten av de väntande säkerhetsrekommendationerna. De möjliga nivåerna är låga, medelhöga och höga. Låg exponering innebär att enheterna är mindre sårbara för användning.

Om exponeringsnivån säger "Inga data tillgängliga" finns det några anledningar till varför det kan vara så:

- Enheten slutade rapportera i mer än 30 dagar – i så fall anses den vara inaktiv och exponering beräknas inte
- Enhetens operativsystem stöds inte – se [minimikraven för Microsoft Defender för Slutpunkt](minimum-requirements.md)
- Enhet med inaktuell agent (mycket osannolikt)

### <a name="os-platform"></a>OS-plattform

Välj bara de OS-plattformar som du är intresserad av att undersöka.

### <a name="health-state"></a>Hälsotillstånd

Filtrera efter följande tillstånd för enhetshälsa:

- **Aktiv** – Enheter som aktivt rapporterar sensordata till tjänsten.
- **Inaktiv** – Enheter som helt slutat skicka signaler i mer än 7 dagar.
- **Felkonfigurerad** – Enheter som har nedsatt kommunikation med tjänsten eller inte kan skicka sensordata. Felkonfigurerade enheter kan klassificeras ytterligare till:
  - Inga sensordata
  - Nedsatt kommunikation

  Mer information om hur du åtgärdar problem på felkonfigurerade enheter finns i [Åtgärda defekta sensor .](fix-unhealthy-sensors.md)

### <a name="antivirus-status"></a>Antivirusstatus

Filtrera enheter efter antivirusstatus. Gäller endast aktiva Windows 10-enheter.

- **Inaktiverad** – & skydd mot virus är inaktiverat.
- **Rapportering inte** – & skydd mot virushot rapporterar inte.
- **Inte uppdaterat** – & skydd mot virus är inte uppdaterat.

Mer information finns i View [the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).

### <a name="threat-mitigation-status"></a>Status för åtgärder mot hot

Om du vill visa enheter som kan påverkas av ett visst hot väljer du hot i listmenyn och väljer sedan vilken säkerhetsrisk som behöver minimeras.

Mer information om vissa hot finns i [Hotanalyser.](threat-analytics.md) Information om åtgärder finns i [& sårbarhetshantering.](next-gen-threat-and-vuln-mgt.md)

### <a name="windows-10-version"></a>Windows 10-version

Välj bara de Versioner av Windows 10 som du vill undersöka.

### <a name="tags--groups"></a>Taggar & grupper

Filtrera listan baserat på de gruppering och taggning som du har lagt till på enskilda enheter. Se [Skapa och hantera enhetstaggar](machine-tags.md) och Skapa och hantera [enhetsgrupper.](machine-groups.md)

## <a name="related-topics"></a>Relaterade ämnen

- [Undersöka enheter i listan Microsoft Defender för slutpunktsenheter](investigate-machines.md)
