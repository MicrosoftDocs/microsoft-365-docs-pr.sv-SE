---
title: Vidta åtgärder för avancerade frågeresultat för sökning i Microsoft 365 Defender
description: Hantera snabbt hot och påverkade tillgångar i dina avancerade frågeresultat för sökfrågor
keywords: avancerad sökning, hotsökning, cyberhot, microsoft threat protection, microsoft 365, mtp, m365, sökning, fråga, telemetri, vidta åtgärder
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e8ad544cfe17d0d8e5c895e208b42ec56555565
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932184"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Vidta åtgärder för avancerade frågeresultat för sökning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Du kan snabbt innehålla hot eller hantera komprometterade tillgångar som du hittar på [avancerad](advanced-hunting-overview.md) sökning med hjälp av kraftfulla och omfattande åtgärdsalternativ. Med dessa alternativ kan du:

- Vidta olika åtgärder på enheter
- Sätt filer i karantän

## <a name="required-permissions"></a>Behörighet som krävs
För att kunna vidta åtgärder via avancerad sökning behöver du en roll i Microsoft Defender för Endpoint med behörighet att skicka [åtgärder på enheter.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options) Om du inte kan vidta någon åtgärd kan du kontakta en global administratör om att få följande behörighet:

*Aktiva åtgärder för > hantering av hot och sårbarhet – åtgärdshantering*

## <a name="take-various-actions-on-devices"></a>Vidta olika åtgärder på enheter
Du kan vidta följande åtgärder på enheter som identifieras av `DeviceId` kolumnen i frågeresultat:

- Isolera påverkade enheter som innehåller en smitta eller förhindra attacker från att röra sig fritt
- Samla in undersökningspaket för att få mer teknisk information
- Kör en antivirussökning för att hitta och ta bort hot med de senaste säkerhetsintelligensuppdateringarna
- Initiera en automatiserad undersökning för att kontrollera och åtgärda hot på enheten och eventuellt andra enheter som påverkas
- Begränsa programkörningen till endast Microsoft-signerade körbara filer, förhindra efterföljande hotaktivitet genom skadlig kod eller andra körbara filer som inte är betrodda

Mer information om hur dessa svarsåtgärder utförs via Microsoft Defender för Slutpunkt finns [i artikeln om svarsåtgärder på enheter.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
   
## <a name="quarantine-files"></a>Sätt filer i karantän
Du kan distribuera *karantänåtgärden* för filer så att de sätts i karantän automatiskt när de påträffas. När du väljer den här åtgärden kan du välja mellan följande kolumner för att identifiera vilka filer i frågan som ska karantäns:

- `SHA1` — I de flesta avancerade söktabeller är det SHA-1 i filen som påverkades av den inspelade åtgärden. Om en fil till exempel kopierades är det här den kopierade filen.
- `InitiatingProcessSHA1` – I de flesta avancerade söktabeller är det den fil som ansvarar för att initiera den inspelade åtgärden. Om till exempel en underordnad process startades, skulle detta vara den överordnade processen. 
- `SHA256` — Det här är SHA-256-motsvarigheten till filen som identifieras av `SHA1` kolumnen.
- `InitiatingProcessSHA256` — Det här är SHA-256-motsvarigheten till filen som identifieras av `InitiatingProcessSHA1` kolumnen.

Mer information om hur åtgärder i karantän vidtas och hur filer kan återställas finns [i svarsåtgärder för filer.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)

>[!NOTE]
>För att hitta filer och sätta dem i karantän bör frågeresultaten också `DeviceId` innehålla värden som enhetsidentifierare.  

## <a name="take-action"></a>Vidta åtgärder
Om du vill utföra någon av de åtgärder som beskrivs markerar du en eller flera poster i frågeresultatet och väljer **sedan Vidta åtgärder.** En guide vägleder dig genom processen att välja och sedan skicka dina föredragna åtgärder.

![Bild på markerad post med panel för att kontrollera posten](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>Granska åtgärder som har vidtagits
Varje åtgärd registreras individuellt i [åtgärdscenter](mtp-action-center.md) under **Historik för åtgärdscenter**  >   [(security.microsoft.com/action-center/history).](https://security.microsoft.com/action-center/history) Gå till åtgärdscenter och kontrollera status för varje åtgärd.
 
## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Översikt över Åtgärdscenter](mtp-action-center.md)
