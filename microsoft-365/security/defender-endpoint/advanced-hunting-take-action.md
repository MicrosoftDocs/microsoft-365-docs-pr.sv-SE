---
title: Vidta åtgärder för avancerade frågeresultat efter sökning i Microsoft Threat Protection
description: Hantera snabbt hot och påverkade tillgångar i dina avancerade frågeresultat för sökning
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, custom detections, schema, kusto, avoid timeout, command lines, process id
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: d1dbe226cef5e94b36fcd6c35b839118b200f85e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500538"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Vidta åtgärder för avancerade frågeresultat för sökning

**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Du kan snabbt innehålla hot eller adresser komprometterade tillgångar som du hittar i [avancerad sökning](advanced-hunting-overview.md) med hjälp av kraftfulla och omfattande åtgärdsalternativ. Med de här alternativen kan du:

- Vidta olika åtgärder på enheter
- Sätt filer i karantän

## <a name="required-permissions"></a>Behörighet som krävs

För att kunna vidta åtgärder via avancerad sökning måste du ha en roll i Defender för Endpoint med behörighet att skicka [åtgärder på enheter](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options). Om du inte kan vidta någon åtgärd kontaktar du en global administratör för att få följande behörighet:

*Aktiva åtgärdsåtgärder > hantering av hot och sårbarhet – åtgärdshantering*

## <a name="take-various-actions-on-devices"></a>Vidta olika åtgärder på enheter

Du kan utföra följande åtgärder på enheter som identifieras av `DeviceId` kolumnen i frågeresultatet:

- Isolera påverkade enheter för att isolera en smitta eller förhindra attacker från att röra sig fritt
- Samla in undersökningspaket för att få mer teknisk information
- Kör en antivirussökning för att hitta och ta bort hot med de senaste säkerhetsintelligensuppdateringarna
- Initiera en automatiserad undersökning för att kontrollera och åtgärda hot på enheten och eventuellt andra enheter som påverkas
- Begränsa programkörningen till endast Microsoft-signerade körbara filer, förhindra efterföljande aktivitet med hot genom skadlig programvara eller andra körbara filer som inte är betrodda

Mer information om hur de här svarsåtgärderna utförs via Defender för Slutpunkt finns [i om svarsåtgärder på enheter.](respond-machine-alerts.md)

## <a name="quarantine-files"></a>Sätt filer i karantän

Du kan distribuera *karantänåtgärden* på filer så att de automatiskt sätts i karantän när de påträffas. När du väljer den här åtgärden kan du välja mellan följande kolumner för att identifiera vilka filer i frågan som ska sätts i karantän:

- `SHA1` — I de flesta avancerade tabeller för sökning är det SHA-1 i filen som påverkades av den inspelade åtgärden. Om en fil till exempel kopierades är det den kopierade filen.
- `InitiatingProcessSHA1` — I de flesta avancerade söktabeller är det här filen som ansvarar för att initiera den inspelade åtgärden. Om till exempel en underordnad process startades skulle det här vara den överordnade processen. 
- `SHA256` — Det här är SHA-256-motsvarigheten till filen som identifieras av `SHA1` kolumnen.
- `InitiatingProcessSHA256` — Det här är SHA-256-motsvarigheten till filen som identifieras av `InitiatingProcessSHA1` kolumnen.

Mer information om hur åtgärder i karantän vidtas och hur filer kan återställas finns [i svarsåtgärder på filer.](respond-file-alerts.md)

>[!NOTE]
>För att hitta filer och sätta dem i karantän bör frågeresultatet även `DeviceId` innehålla värden som enhetsidentifierare.  

## <a name="take-action"></a>Vidta åtgärder

Om du vill utföra någon av de åtgärder som beskrivs markerar du en eller flera poster i frågeresultatet och väljer **sedan Vidta åtgärder**. En guide vägleder dig genom processen med att välja och sedan skicka dina föredragna åtgärder.

![Bild av markerad post med panel för att kontrollera posten](images/ah-take-actions.png)

## <a name="review-actions-taken"></a>Granska åtgärder som har vidtagits

Varje åtgärd registreras individuellt i åtgärdscenter, under **Historik för åtgärdscenter**  >   ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)). Gå till åtgärdscenter för att kontrollera status för varje åtgärd.
 
## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Förstå schemat](advanced-hunting-schema-reference.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Använda metodtips för frågor](advanced-hunting-best-practices.md)
- [Översikt över anpassade identifieringar](overview-custom-detections.md)
