---
title: Vidta åtgärder för avancerade frågor i jakt i Microsoft 365 Defender
description: Adressera hot och berörda till gångar snabbt och påverkas av dina frågor
keywords: Avancerad jakt, Hot jakt, cyberterrorism hotet om Microsoft Threat Protection, Microsoft 365, MTP, m365, sökning, frågor, telemetri, åtgärd
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 506af82ec08ad6cd8dbeece5c1c2741e09e4817a
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842470"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Vidta åtgärder för avancerade frågor

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Du kan snabbt ta med hot eller adresser som äventyrade till gångar som du hittar i [Avancerad jakt](advanced-hunting-overview.md) med kraftfulla och omfattande åtgärds alternativ. Med dessa alternativ kan du:

- Utföra olika åtgärder på enheter
- Quarantine-filer

## <a name="required-permissions"></a>Nödvändiga behörigheter
För att kunna vidta åtgärder genom avancerad jakt måste du ha en roll i Microsoft Defender för att få en slut punkt med [behörigheter att skicka reparations åtgärder på enheter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options). Om du inte kan vidta en åtgärd kontaktar du en global administratör för att få följande behörighet:

*Aktiva reparations åtgärder > hot och sårbarhet hantering – reparations hantering*

## <a name="take-various-actions-on-devices"></a>Utföra olika åtgärder på enheter
Du kan utföra följande åtgärder på enheter som identifieras av `DeviceId` kolumnen i frågans resultat:

- Isolera berörda enheter för att innehålla en infektion eller förhindra att attacker kan flyttas senare
- Samla in ett Forensic-paket för att få mer information
- Kör en Antivirus sökning för att hitta och ta bort hot med de senaste säkerhets uppdateringarna
- Starta en automatiserad undersökning för att kontrol lera och åtgärda hot på enheten och möjligen andra berörda enheter
- Begränsa program körning till endast Microsoft-signerade körbara filer, förhindra efterföljande hot-aktiviteter genom att använda skadlig program vara eller andra obetrodda program

Om du vill veta mer om hur de här svars åtgärderna utförs via Microsoft Defender för slut punkter [läser du om svars åtgärder på enheter](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).
   
## <a name="quarantine-files"></a>Quarantine-filer
Du kan distribuera *karantän* åtgärden på filer så att de automatiskt satts i karantän när de påträffas. När du väljer den här åtgärden kan du välja mellan följande kolumner för att identifiera vilka filer i frågeresultatet som ska visas:

- `SHA1` – I de flesta avancerade jakt tabeller är detta SHA-1 för filen som påverkades av den registrerade åtgärden. Om du till exempel kopierar en fil, blir detta den kopierade filen.
- `InitiatingProcessSHA1` – I de flesta avancerade jakt tabeller är detta den fil som är ansvarig för att inleda den inspelade åtgärden. Om till exempel en underordnad process är det den överordnade processen. 
- `SHA256` — Det här är SHA-256-motsvarigheten till filen som identifieras av `SHA1` kolumnen.
- `InitiatingProcessSHA256` — Det här är SHA-256-motsvarigheten till filen som identifieras av `InitiatingProcessSHA1` kolumnen.

Läs mer om hur du gör för att få mer information om hur karantäns åtgärder vidtas och hur filer kan återställas [med svars åtgärder på filer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).

>[!NOTE]
>Om du vill söka efter filer och karantän kan frågeresultatet innehålla `DeviceId` värden som enhets identifierare.  

## <a name="take-action"></a>Utför åtgärd
Om du vill använda någon av de beskrivna åtgärderna markerar du en eller flera poster i frågeresultatet och väljer sedan **vidta åtgärder**. En guide vägleder dig genom processen att välja och sedan skicka dina önskade åtgärder.

![Bild av den valda posten med panelen för kontroll av posten](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>Gransknings åtgärder som utförs
Varje åtgärd registreras individuellt i [Åtgärds centret](mtp-action-center.md) under **Åtgärds Center**  >  **Historik** ( [Security.Microsoft.com/Action-Center/History](https://security.microsoft.com/action-center/history)). Gå till åtgärds centret för att kontrol lera status för varje åtgärd.
 
## <a name="related-topics"></a>Relaterade ämnen
- [Översikt över avancerad jakt](advanced-hunting-overview.md)
- [Lär dig frågespråket](advanced-hunting-query-language.md)
- [Arbeta med frågeresultat](advanced-hunting-query-results.md)
- [Förstå schemat](advanced-hunting-schema-tables.md)
- [Översikt över åtgärds centret](mtp-action-center.md)
