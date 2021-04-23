---
title: Vidta åtgärder för avancerade frågeresultat för sökning i Microsoft 365 Defender
description: Hantera snabbt hot och påverkade tillgångar i dina avancerade frågeresultat för sökning
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, take action
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 15eebbba102640a92f9c7712194aaef685a96cfb
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952614"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Vidta åtgärder för avancerade frågeresultat för sökning

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender
- Microsoft Defender för Endpoint

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Du kan snabbt innehålla hot eller adresser komprometterade tillgångar som du hittar i [avancerad sökning](advanced-hunting-overview.md) med hjälp av kraftfulla och omfattande åtgärdsalternativ. Med de här alternativen kan du:

- Vidta olika åtgärder på enheter
- Sätt filer i karantän

## <a name="required-permissions"></a>Behörighet som krävs
För att kunna vidta åtgärder via avancerad sökning behöver du en roll i Microsoft Defender för Endpoint med behörighet att skicka [åtgärder på enheter.](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options) Om du inte kan vidta någon åtgärd kontaktar du en global administratör för att få följande behörighet:

*Aktiva åtgärdsåtgärder > hantering av hot och sårbarhet – åtgärdshantering*

## <a name="take-various-actions-on-devices"></a>Vidta olika åtgärder på enheter
Du kan vidta följande åtgärder på enheter som identifieras av `DeviceId` kolumnen i frågeresultatet:

- Isolera påverkade enheter för att isolera en smitta eller förhindra attacker från att röra sig fritt
- Samla in undersökningspaket för att få mer teknisk information
- Kör en antivirussökning för att hitta och ta bort hot med de senaste säkerhetsintelligensuppdateringarna
- Initiera en automatiserad undersökning för att kontrollera och åtgärda hot på enheten och eventuellt andra enheter som påverkas
- Begränsa programkörningen till endast Microsoft-signerade körbara filer, förhindra efterföljande aktivitet med hot genom skadlig programvara eller andra körbara filer som inte är betrodda

Mer information om hur dessa svarsåtgärder utförs via Microsoft Defender för Slutpunkt finns [i om svarsåtgärder på enheter.](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
   
## <a name="quarantine-files"></a>Sätt filer i karantän
Du kan distribuera *karantänåtgärden* på filer så att de automatiskt sätts i karantän när de påträffas. När du väljer den här åtgärden kan du välja mellan följande kolumner för att identifiera vilka filer i frågan som ska sätts i karantän:

- `SHA1` — I de flesta avancerade tabeller för sökning är det SHA-1 i filen som påverkades av den inspelade åtgärden. Om en fil till exempel kopierades är det den kopierade filen.
- `InitiatingProcessSHA1` — I de flesta avancerade söktabeller är det här filen som ansvarar för att initiera den inspelade åtgärden. Om till exempel en underordnad process startades skulle det här vara den överordnade processen. 
- `SHA256` — Det här är SHA-256-motsvarigheten till filen som identifieras av `SHA1` kolumnen.
- `InitiatingProcessSHA256` — Det här är SHA-256-motsvarigheten till filen som identifieras av `InitiatingProcessSHA1` kolumnen.

Mer information om hur åtgärder i karantän vidtas och hur filer kan återställas finns [i svarsåtgärder på filer.](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)

>[!NOTE]
>För att hitta filer och sätta dem i karantän bör frågeresultatet även `DeviceId` innehålla värden som enhetsidentifierare.  

## <a name="take-action"></a>Vidta åtgärder
Om du vill utföra någon av de åtgärder som beskrivs markerar du en eller flera poster i frågeresultatet och väljer **sedan Vidta åtgärder**. En guide vägleder dig genom processen med att välja och sedan skicka dina föredragna åtgärder.

![Bild av markerad post med panel för att kontrollera posten](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>Granska åtgärder som har vidtagits
Varje åtgärd registreras individuellt i [åtgärdscenter](m365d-action-center.md) under **Historik för åtgärdscenter**  >   [(security.microsoft.com/action-center/history).](https://security.microsoft.com/action-center/history) Gå till åtgärdscenter för att kontrollera status för varje åtgärd.
 
>[!NOTE]
>Vissa tabeller i den här artikeln kanske inte är tillgängliga i Microsoft Defender för Endpoint. [Aktivera Microsoft 365 Defender för](m365d-enable.md) att leta efter hot med hjälp av fler datakällor. Du kan flytta dina avancerade arbetsflöden för sökning från Microsoft Defender för Slutpunkt till Microsoft 365 Defender genom att följa stegen i Migrera avancerade sökfrågor från [Microsoft Defender för Slutpunkt.](advanced-hunting-migrate-from-mde.md)

## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Översikt över Åtgärdscenter](m365d-action-center.md)
