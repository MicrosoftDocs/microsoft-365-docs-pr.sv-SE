---
title: Åtgärda säkerhetsproblem med Hantering av hot och säkerhetsrisker
description: Åtgärda säkerhetsbrister som upptäcks genom säkerhetsrekommendationer och skapa undantag vid behov, i Hantering av hot och säkerhetsrisker.
keywords: Microsoft Defender för Endpoint tvm-åtgärd, Microsoft Defender för Endpoint tvm, Hantering av hot och säkerhetsrisker, threat & hantering av säkerhetsrisker, threat & hantering av säkerhetsrisker remediation, tvm remediation intune, tvm remediation sccm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 602a38d8ad27505e81628db265681ac89218e593
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840917"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a>Åtgärda säkerhetsproblem med Hantering av hot och säkerhetsrisker

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Hot och hantering av säkerhetsrisker](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a>Begära åtgärd

Med Hantering av hot och säkerhetsrisker kompatibilitetsfunktionerna i Microsoft Defender för Endpoint överbrygger du mellanrummet mellan säkerhet och IT-administratörer via arbetsflödet för åtgärdsförfrågningar. Som säkerhetsadministratörer kan du begära att IT-administratören åtgärdar problemet från sidorna med säkerhetsrekommendationer till Intune. 

### <a name="enable-microsoft-intune-connection"></a>Aktivera Microsoft Intune anslutning

Om du vill använda den här funktionen måste du Microsoft Intune nätverksanslutningar. I Microsoft Defender Säkerhetscenter navigerar du till **Inställningar**  >    >  **Avancerade funktioner.** Rulla nedåt och leta efter **Microsoft Intune anslutning**. Växlingsknappen är inaktiverad som standard. Aktivera **Microsoft Intune växlingsknappen** **.**

**Obs!** Om Intune-anslutningen är aktiverad får du ett alternativ för att skapa en Intune-säkerhetsaktivitet när du skapar en åtgärdsbegäran. Det här alternativet visas inte om anslutningen inte har angetts.

Mer [information finns i Använda Intune för att](/intune/atp-manage-vulnerabilities) åtgärda säkerhetsproblem som identifieras av Microsoft Defender.

### <a name="remediation-request-steps"></a>Steg för åtgärdsförfrågan

1. Gå till Hantering av hot och säkerhetsrisker navigeringsmenyn i Microsoft Defender Säkerhetscenter och välj [**Säkerhetsrekommendationer**](tvm-security-recommendation.md).

2. Välj en säkerhetsrekommendationer som du vill begära åtgärd för och välj sedan **Åtgärdsalternativ.**

3. Fyll i formuläret, inklusive vad du begär åtgärd för, tillämpliga enhetsgrupper, prioritet, förfallodatum och valfria anteckningar.
    1. Om du väljer åtgärdsalternativet "åtgärd krävs" är det inte tillgängligt att välja ett förfallodatum eftersom det inte finns någon särskild åtgärd.

4. Välj **Skicka begäran**. När du skickar en åtgärdsförfrågan skapas ett åtgärdsaktivitetsobjekt i Hantering av hot och säkerhetsrisker, som kan användas för att övervaka åtgärdsförloppet för den här rekommendationen. Det här utlöser inte någon åtgärd eller tillämpar ändringar på enheter.

5. Meddela IT-administratören om den nya begäran och be dem logga in i Intune för att godkänna eller avvisa begäran och starta en paketdistribution.

6. Gå till [**sidan Åtgärd för**](tvm-remediation.md) att visa status för din begäran om åtgärd.

Om du vill kontrollera hur biljetten visas i Intune hittar du mer information i Använd [Intune](/intune/atp-manage-vulnerabilities) för att åtgärda säkerhetsproblem som identifieras av Microsoft Defender för Endpoint.

>[!NOTE]
>Om din begäran kräver åtgärd av fler än 10 000 enheter kan vi bara skicka 10 000 enheter för åtgärd till Intune.

När du har identifierat och mappat organisationens cybersäkerhet till åtgärdsbara [säkerhetsrekommendationer börjar](tvm-security-recommendation.md)du med att skapa säkerhetsuppgifter. Du kan skapa uppgifter genom integreringen Microsoft Intune där åtgärdsärenden skapas.

Minska exponeringen från svagheter i organisationen och öka säkerhetskonfigurationen genom att åtgärda säkerhetsrekommendationerna.

## <a name="view-your-remediation-activities"></a>Visa åtgärder

När du skickar en begäran om åtgärd från sidan Säkerhetsrekommendationer startar den en åtgärdsaktivitet. En säkerhetsuppgift skapas som kan spåras på  sidan Hantering av hot och säkerhetsrisker Åtgärd och en åtgärdsuppgift skapas i Microsoft Intune.

Om du väljer åtgärdsalternativet "åtgärd krävs" finns det ingen förloppsstapel, status för biljett eller förfallodatum eftersom det inte finns någon verklig åtgärd vi kan övervaka.

När du är på sidan Åtgärd väljer du den åtgärdsaktivitet som du vill visa. Du kan följa åtgärdsstegen, spåra förloppet, visa relaterad rekommendation, exportera till CSV eller markera som slutförd.
![Exempel på sidan Åtgärd, med en vald åtgärdsaktivitet, och den aktivitetens utfällsida med en lista över beskrivningen, IT-tjänster och verktyg för enhetshantering samt status för enhetsreparation.](images/remediation_flyouteolsw.png)

>[!NOTE]
> Det finns en 180-dagars kvarhållningstid för slutförda åtgärder. För att åtgärdssidan ska fungera optimalt tas åtgärdsaktiviteten bort 6 månader efter att den har slutförts.

### <a name="completed-by-column"></a>Kolumnen Slutförd efter

Spåra vem som har stängt åtgärdsaktiviteten med kolumnen "Slutförd av" på sidan Åtgärd.

- **E-postadress:** E-postadressen till den person som slutförde uppgiften manuellt
- **Systembekräftelse:** Uppgiften slutfördes automatiskt (alla enheter har åtgärdats)
- **Ej tillgänglig:** Informationen är inte tillgänglig eftersom vi inte vet hur den äldre uppgiften slutfördes

![Skapad av och slutförd av kolumner med två rader. En rad för slutförda har exempel på ett e-postmeddelande, den andra raden säger systembekräftelse.](images/tvm-completed-by.png)

### <a name="top-remediation-activities-in-the-dashboard"></a>De viktigaste åtgärdsaktiviteterna på instrumentpanelen

Visa **de viktigaste åtgärdsaktiviteterna** på [Hantering av hot och säkerhetsrisker instrumentpanel](tvm-dashboard-insights.md). Markera någon av posterna för att gå **till sidan** Åtgärd. Du kan markera åtgärdsaktiviteten som slutförd när IT-administratörteamet har åtgärdat uppgiften.

![Exempel på kortet Toppåtgärder-aktiviteter med en tabell som visar de aktiviteter som har genererats från säkerhetsrekommendationer.](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över hantering av säkerhetsrisker hot och hot](next-gen-threat-and-vuln-mgt.md)
- [Instrumentpanelen](tvm-dashboard-insights.md)
- [Säkerhetsrekommendationer](tvm-security-recommendation.md)