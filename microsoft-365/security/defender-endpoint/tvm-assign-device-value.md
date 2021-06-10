---
title: Tilldela enhetsvärde – Hantering av hot och säkerhetsrisker
description: Lär dig hur du tilldelar ett lågt, normalt eller högt värde till en enhet så att du kan skilja mellan resursprioriteringar.
keywords: Microsoft Defender för Endpoint-enhetsvärdet, Hantering av hot och säkerhetsrisker enhetvärde, enheter med hög värde, exponeringsresultat för enhetsvärde
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
ms.openlocfilehash: ca6c88b08b331eb65035387a9c070d0914b1651d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935203"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a>Tilldela enhetsvärde – Hantering av hot och säkerhetsrisker

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gäller för:**

- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Hot och hantering av säkerhetsrisker](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vill du uppleva Microsoft Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Genom att definiera en enhets värde kan du skilja på resursprioriteringar. Enhetsvärdet används för att införliva risk nyare för en enskild tillgång i beräkningen Hantering av hot och säkerhetsrisker av exponeringsresultatet. Enheter som tilldelas som "höga värden" får större vikt.

Du kan också använda [API:t för enhetsvärde.](set-device-value.md)

Alternativ för enhetsvärde:

- Låg
- Normal (standard)
- Högsta

Exempel på enheter som bör tilldelas ett högt värde:

- Domänkontrollanter, Active Directory
- Internet-enheter
- VIP-enheter
- Enheter som fungerar som värd för interna/externa produktionstjänster

## <a name="choose-device-value"></a>Välj enhetsvärde

1. Gå till valfri enhetssida, den enklaste platsen är från enhetsinventeringen.

2. Välj **Enhetsvärde** från tre punkter bredvid åtgärdsfältet högst upp på sidan.

    ![Exempel på listrutan för enhetsvärde.](images/tvm-device-value-dropdown.png)

3. En utfäll kan visas med enhetens aktuella värde och vad det innebär. Granska enhetens värde och välj det som passar bäst för din enhet.
![Exempel på utfällvärde för enheten.](images/tvm-device-value-flyout.png)

## <a name="how-device-value-impacts-your-exposure-score"></a>Hur enhetsvärde påverkar exponeringsresultatet

Exponeringsresultatet är ett viktat medelvärde för alla enheter. Om du har enhetsgrupper kan du också filtrera poängen efter enhetsgrupp.

- Normal enheter har en vikt på 1
- Enheter med låg värde har en vikt på 0,75
- Enheter med höga värden har vikten NumberOfAssets / 10.
    - Om du har 100 enheter har varje enhet med höga värden 10 (100/10)

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över hantering av säkerhetsrisker hot och hot](next-gen-threat-and-vuln-mgt.md)
- [Exponeringsresultat](tvm-exposure-score.md)
- [API:er](next-gen-threat-and-vuln-mgt.md#apis)