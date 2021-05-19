---
title: Minimera svagheter utan dag – Hantering av hot och säkerhetsrisker
description: Lär dig hur du kan hitta och minimera svagheter under nolldagar i din miljö Hantering av hot och säkerhetsrisker.
keywords: Microsoft Defender för slutpunkt tvm noll dagars säkerhetsproblem, tvm, hot & hantering av säkerhetsrisker, noll dag, 0-dagars, minimera 0 dagars säkerhetsproblem, sårbar CVE
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2c746a74899a34827e089f4c9c2f6ecc396bb69c
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538777"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a>Minimera svagheter utan dag – Hantering av hot och säkerhetsrisker

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Hot och hantering av säkerhetsrisker](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Ett nolldagarshål är ett offentligt avslöjat säkerhetshål där inga officiella korrigeringar eller säkerhetsuppdateringar har släppts. Nolldagarsbrister har ofta hög allvarlighetsnivå och utnyttjas aktivt.

Hot och hantering av säkerhetsrisker bara visar svagheter som inte har någon dag.

## <a name="find-information-about-zero-day-vulnerabilities"></a>Hitta information om svagheter utan dag

När en nolldagarsrisk har hittats kommer information om den att förmedlas genom följande upplevelser i Microsoft Defender Säkerhetscenter.

>[!NOTE]
> Funktionen 0 dagar är för närvarande inte tillgänglig för produkter som Windows (Mac, Linux). den läggs dock till i framtiden.

### <a name="threat-and-vulnerability-management-dashboard"></a>Hot och hantering av säkerhetsrisker instrumentpanel

Leta efter rekommendationer med en nolldagarstagg i kortet "Bästa säkerhetsrekommendationer".

![Bästa rekommendationerna med en nolldagarstagg.](images/tvm-zero-day-top-security-recommendations.png)

Hitta den bästa programvaran med nolldagarstaggen på kortet "Mest sårbar programvara".

![Mest sårbar programvara med en nolldagarstagg.](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a>Sida för svagheter

Leta efter det namngivna nolldagarsproblemet tillsammans med en beskrivning och information.

- Om problemet har ett CVE-ID tilldelat ser du nolldagarsetiketten bredvid CVE-namnet.

- Om det här problemet inte har något CVE-ID tilldelat hittar du det under ett internt, tillfälligt namn som ser ut som "TVM-XXXX-XXXX". Namnet uppdateras när en officiell CVE-ID har tilldelats, men det tidigare interna namnet är fortfarande sökbart och finns i sidopanelen.

![Exempel på nolldag för CVE-2020-17087 i svagheter.](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a>Sidan För programvaruinventering

Leta efter programvara med nolldagarstaggen. Filtrera efter "nolldagars"-taggen för att endast se säkerhetsproblem med programvara utan dag.

![Noll dagars exempel på Windows Server 2016 visas på sidan för programvaruinventering.](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a>Sidan Programvara

Leta efter en nolldagarstagg för varje programvara som har påverkats av den nolldagars sårbarheten.

![Exempel på nolldag för Windows Server 2016 programvara.](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a>Sidan Säkerhetsrekommendationer

Visa tydliga förslag om åtgärder och åtgärder, inklusive lösningar om de finns. Filtrera efter "nolldagars"-taggen för att endast se säkerhetsrekommendationer om svagheter utan dag.

Om det finns programvara med ett nolldagars sårbarhet och ytterligare säkerhetsproblem att ta itu med får du en rekommendation om alla säkerhetsproblem.

![Nolldagarsexempel för Windows Server 2016 på sidan med säkerhetsrekommendationer.](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a>Åtgärda svagheter utan dag

Gå till sidan med säkerhetsrekommendationer och välj en rekommendation om en nolldag. En utfällbarhet öppnas med information om nolldagar och andra säkerhetsproblem för programvaran.

Om det finns en länk till åtgärder och lösningar finns det en länk. Lösningar kan minska risken som kan uppstå med den här nolldagarsproblemet tills en korrigering eller säkerhetsuppdatering kan distribueras.

Öppna alternativ för åtgärder och välj åtgärdstyp. Åtgärdsalternativet "åtgärd krävs" rekommenderas för säkerhetsproblem med nolldagar, eftersom ingen uppdatering har släppts än. Du kan inte välja ett förfallodatum eftersom det inte finns någon specifik åtgärd att utföra. Om det finns äldre säkerhetsproblem för den här programvaran som du vill åtgärda kan du åsidosätta alternativet "åtgärd som krävs" och välja "uppdatera".

![Utfällfingrigt nolldag Windows Server 2016 på sidan med säkerhetsrekommendationer.](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a>Spåra aktiviteter för nolldagarsreparation

Gå till Hantering av hot och säkerhetsrisker [åtgärdssidan](tvm-remediation.md) för att visa objektet för åtgärdsaktiviteten. Om du väljer åtgärdsalternativet "åtgärd krävs" finns det ingen förloppsstapel, status för biljett eller förfallodatum eftersom det inte finns någon verklig åtgärd vi kan övervaka. Du kan filtrera efter åtgärdstyp, till exempel "programuppdatering" eller "åtgärd krävs", för att se alla aktivitetsobjekt i samma kategori.

## <a name="patching-zero-day-vulnerabilities"></a>Korrigera säkerhetsproblem med nolldagar

När en korrigering släpps för nolldagen ändras rekommendationen till "Uppdatering" och en blå etikett bredvid den där det står "Ny säkerhetsuppdatering för noll dag". Den kommer inte längre att ses som en nolldag, nolldagarstaggen tas bort från alla sidor.

![Rekommendation för "Uppdatera Microsoft Windows 10" med ny korrigeringsetikett.](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a>Relaterade artiklar

- [Översikt över hantering av säkerhetsrisker hot och hot](next-gen-threat-and-vuln-mgt.md)
- [Instrumentpanelen](tvm-dashboard-insights.md)
- [Säkerhetsrekommendationer](tvm-security-recommendation.md)
- [Programvaruinventering](tvm-software-inventory.md)
- [Sårbarhet i min organisation](tvm-weaknesses.md)
