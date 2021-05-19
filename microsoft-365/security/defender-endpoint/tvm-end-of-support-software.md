---
title: Planera för programvara och programvaruversioner som slutar på grund av support
description: Upptäck och planera för program- och programvaruversioner som inte längre stöds och inte får säkerhetsuppdateringar.
keywords: Hantering av hot och säkerhetsrisker, Microsoft Defender för Endpoint tvm-säkerhetsrekommendationer, rekommendation om cybersäkerhet och rekommendation om säkerhet på åtgärd
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
ms.openlocfilehash: bb436cbd2d0fa453872760c1d2656585e02d1767
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538873"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a>Planera för slut på support av programvara och programvaruversioner med Hantering av hot och säkerhetsrisker

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Hot och hantering av säkerhetsrisker](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Supporten för programvara eller programversioner (EOS, kallas även slutet på livscykeln, EOL), innebär att de inte längre kommer att få support eller service, och att de inte får säkerhetsuppdateringar. När du använder programvara eller programvaruversioner utan att ha avslutat supporten utser du organisationen för att skapa säkerhetsbrister, juridiska och finansiella risker.

Det är centralt för säkerhet- och IT-administratörer att samarbeta och se till att organisationens programvaruinventering har konfigurerats för optimala resultat, efterlevnad och ett hälsosamt nätverks-ekosystem. De bör granska alternativen för att ta bort eller ersätta program som stöds i slutet av supporten och uppdateringsversionerna som inte längre stöds. Det är bäst att skapa och implementera en plan **innan supportdatumen** är slut.

>[!NOTE]
> EOS-funktionen är för närvarande inte tillgänglig för Windows -produkter (Mac, Linux). den läggs dock till i framtiden.

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a>Hitta program- och programvaruversioner som inte längre stöds

1. Från menyn Hantering av hot och säkerhetsrisker navigerar du till [**Säkerhetsrekommendationer**](tvm-security-recommendation.md).
2. Gå till **panelen Filter** och leta efter avsnittet med taggar. Markera ett eller flera av EOS-taggalternativen. Använd **sedan**.

    ![Skärmbildstaggar som säger EOS-programvara, EOS-versioner och kommande EOS-versioner.](images/tvm-eos-tag.png)

3. Du ser en lista med rekommendationer relaterade till programvara med upphört med support, programvaruversioner som upphör och versioner med kommande support upphör. De här taggarna visas också på [sidan för programvaruinventering.](tvm-software-inventory.md)

    ![Rekommendationer med EOS-tagg.](images/tvm-eos-tags-column.png)

## <a name="list-of-versions-and-dates"></a>Lista över versioner och datum

Om du vill visa en lista över versioner som snart har supporten har gått ut, eller snart har supporten, och dessa datum, följer du stegen nedan:

1. Ett meddelande visas i den utfällliga säkerhetsrekommendationerna för programvara med versioner där supporten har gått ut, eller snart kommer att upphöra med support.

    ![Skärmbild av länken för versionsdistribution.](images/eos-upcoming-eos.png)

2. Välj länken **för versionsdistribution** för att gå till sidan för programvarugranskning. Där visas en filtrerad lista med versioner med taggar som identifierar dem som supporten är slut eller kommande support avslutas.

    ![Skärmbild av sidan för software drilldown med slutet av supportprogramvaran.](images/software-drilldown-eos.png)

3. Välj någon av versionerna i tabellen som ska öppnas. Till exempel version 10.0.18362.1. En utfälling visas när supportdatumet är slut.

    ![Skärmbild av supportens datum.](images/version-eos-date.png)

När du har identifierat vilka program- och programvaruversioner som är sårbara på grund av deras status vid slutet av supporten måste du bestämma dig för om du vill uppdatera eller ta bort dem från organisationen. Om du gör det minskar risken för risker för organisationer och avancerade fortlöpande hot.

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över hantering av säkerhetsrisker hot och hot](next-gen-threat-and-vuln-mgt.md)
- [Säkerhetsrekommendationer](tvm-security-recommendation.md)
- [Programvaruinventering](tvm-software-inventory.md)
