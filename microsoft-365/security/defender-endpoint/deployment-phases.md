---
title: Distributionsfaser
description: Lär dig hur du distribuerar Microsoft Defender för Slutpunkt genom att förbereda, konfigurera och registrera slutpunkter för den tjänsten
keywords: distribuera, förbereda, konfigurera, registrera, fas, distribution, distribuera, införa, konfigurera
search.product: eADQiWindows 10XVcnh
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
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3f0527192a55d67df7e23507bed46df446f8b2b7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165171"
---
# <a name="deployment-phases"></a>Distributionsfaser

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Lär dig hur du distribuerar Microsoft Defender för Endpoint så att ditt företag kan dra nytta av förebyggande skydd, identifiering efter intrång, automatisk undersökning och svar. 


Den här guiden hjälper dig att arbeta med intressenter för att förbereda miljön och sedan introducera enheter på ett metodiskt sätt, flytta från utvärdering till ett meningsfullt pilottest till en fullständig distribution.

Varje avsnitt motsvarar en separat artikel i den här lösningen.

![Bild av distributionsfaser med information från tabell](images/deployment-guide-phases.png)


![Sammanfattning av distributionsfaser: förbereda, konfigurera, registrera](images/phase-diagrams/deployment-phases.png)

|Fas | Beskrivning | 
|:-------|:-----|
| [Fas 1: Förbereda](prepare-deployment.md)| Läs mer om vad du behöver tänka på när du distribuerar Defender för Endpoint, till exempel godkännanden från intressenter, miljööverväganden, åtkomstbehörigheter och införandeordningen för funktioner. 
| [Fas 2: Installation](production-deployment.md)|  Få vägledning om de inledande åtgärder du behöver vidta så att du kan komma åt portalen, till exempel validera licensiering, slutföra installationsguiden och nätverkskonfiguration. 
| [Fas 3: Introduktion](onboarding.md) | Lär dig hur du använder distributionsringar, onboarding-verktyg som stöds baserat på typen av slutpunkt och hur du konfigurerar tillgängliga funktioner. 


När du har slutfört den här guiden konfigureras du med rätt åtkomstbehörighet, dina slutpunkter kommer att introduceras och rapportera sensordata till tjänsten, och funktioner som nästa generations skydd och minskning av attackytan kommer att finnas.



Oavsett vilken miljöarkitektur och distributionsmetod du väljer i distributionsvägledning för [Abonnemang](deployment-strategy.md) får du stöd för den här guiden i slutpunkter för onboarding. 








## <a name="key-capabilities"></a>Viktiga funktioner

Även om Microsoft Defender för Slutpunkt innehåller många funktioner är det primära syftet med den här distributionsguiden att komma igång med att registrera enheter. Förutom introduktionen får du i den här vägledningen även hjälp att komma igång med följande funktioner.



Funktion | Beskrivning 
:---|:---
Identifiering och svar av slutpunkt | Funktioner för identifiering och svar av slutpunkter används för att identifiera, undersöka och svara på intrångsförsök och aktiva intrång.
Nästa generations skydd | För att ytterligare förstärka nätverkets säkerhets perimeter använder Microsoft Defender för Endpoint nästa generations skydd som är utformat för att fånga upp alla typer av nya hot.
Minska attackytan |  Tillhandahåll den första försvarslinjen i högen. Genom att säkerställa att konfigurationsinställningarna är korrekt inställda och utnyttja tekniker för minskningar tillämpas, kommer dessa uppsättning funktioner att motarbeta attacker och användning.

Alla dessa funktioner är tillgängliga för Microsoft Defender för Endpoint-licensinnehavare. Mer information finns i [Licenskrav](minimum-requirements.md#licensing-requirements).

## <a name="scope"></a>Omfattning

### <a name="in-scope"></a>I omfattning

-   Användning av Microsoft Endpoint Manager och Microsoft Endpoint Manager för att introducera slutpunkter i tjänsten och konfigurera funktioner

-   Aktivera Defender för identifiering och åtgärd på slutpunkt (Identifiering och åtgärd på slutpunkt)

-   Aktivera Defender för funktioner för Slutpunktsskyddsplattform (DEFENDER)

    -   Nästa generations skydd

    -   Minska attackytan


### <a name="out-of-scope"></a>Inte begränsad

Följande ingår inte i den här distributionsguiden:

-   Konfiguration av lösningar från tredje part som kan integreras med Defender för Endpoint

-   Test av test vid test i produktionsmiljö




## <a name="see-also"></a>Se även
- [Fas 1: Förbereda](prepare-deployment.md)
- [Fas 2: Konfigurera](production-deployment.md)
- [Fas 3: Introduktion](onboarding.md)
- [Planera distribution](deployment-strategy.md)