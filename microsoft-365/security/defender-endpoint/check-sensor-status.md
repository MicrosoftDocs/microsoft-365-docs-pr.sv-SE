---
title: Kontrollera sensorns hälsotillstånd i Microsoft Defender ATP
description: Kontrollera sensorhälsan på enheter för att identifiera vilka som är felkonfigurerade, inaktiva eller inte rapporterar sensordata.
keywords: sensor, sensorhälsa, felkonfigurerad, inaktiv, inga sensordata, sensordata, nedsatt kommunikation, kommunikation
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 21313463519383f4bf052465a0d907d2df293ec8
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165279"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a>Kontrollera sensorhälsan i Microsoft Defender för Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-checksensor-abovefoldlink)

Panelen **Enheter med sensorproblem** finns på instrumentpanelen Säkerhetsåtgärder. Den här panelen ger information om den enskilda enhetens möjlighet att tillhandahålla sensordata och kommunicera med Defender för slutpunkt-tjänsten. Den rapporterar hur många enheter som kräver uppmärksamhet och hjälper dig att identifiera problematiska enheter och vidta åtgärder för att korrigera kända problem.

Det finns två statusindikatorer på panelen som tillhandahåller information om antalet enheter som inte rapporterar korrekt till tjänsten:
- **Felkonfigurerad** – De här enheterna kan delvis rapportera sensordata till Defender för Slutpunkt-tjänsten och kan ha konfigurationsfel som behöver korrigeras.
- **Inaktiva** – Enheter som har slutat rapportera till Defender för slutpunktstjänsten under mer än sju dagar den senaste månaden.

Om du klickar på någon av grupperna dirigeras du **till listan Enheter**, filtrerad efter ditt val.

![Skärmbild av panelen Enheter med sensorproblem](images/atp-devices-with-sensor-issues-tile.png)

I **listan Enheter** kan du filtrera hälsostatuslistan efter följande status:
- **Aktiv** – Enheter som aktivt rapporterar till Defender för slutpunktstjänsten.
- **Felkonfigurerad** – De här enheterna kan delvis rapportera sensordata till Defender för Slutpunkt-tjänsten men har konfigurationsfel som behöver korrigeras. Felkonfigurerade enheter kan ha en eller en kombination av följande problem:
  - **Inga sensordata** – Enheterna har slutat skicka sensordata. Begränsade aviseringar kan utlösas från enheten.
  - **Nedsatt kommunikation –** Möjligheten att kommunicera med en enhet är försämrad. Det kan hända att det inte fungerar att skicka filer för djupanalys, blockera filer, isolera enheten från nätverket och andra åtgärder som kräver kommunikation med enheten.
- **Inaktiv** – Enheter som har stoppat rapporteringen till Defender för slutpunktstjänsten.

Du kan också ladda ned hela listan i CSV-format med **hjälp av funktionen** Exportera. Mer information om filter finns i [Visa och ordna listan Enheter.](machines-view-overview.md)

>[!NOTE]
>Exportera listan i CSV-format om du vill visa ofiltrerade data. CSV-filen innehåller alla enheter i organisationen, oavsett vilken filtrering som används i vyn och kan ta mycket tid att ladda ned, beroende på hur stor din organisation är.

![Skärmbild av listsidan Enheter](images/atp-devices-list-page.png)

Du kan visa enhetsinformationen när du klickar på en felkonfigurerad eller inaktiv enhet.

## <a name="related-topic"></a>Relaterade ämnen
- [Åtgärda defekta sensorer i Defender för Endpoint](fix-unhealthy-sensors.md)
