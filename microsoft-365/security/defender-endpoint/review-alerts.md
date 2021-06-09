---
title: Granska aviseringar i Microsoft Defender för Slutpunkt
description: Granska aviseringsinformation, inklusive en visualiserad aviseringsartikel och information för varje steg i kedjan.
keywords: incidenter, incidenter, datorer, enheter, användare, aviseringar, avisering, undersökning, diagram, bevis
ms.prod: m365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: daniha
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.date: 5/1/2020
ms.technology: mde
ms.openlocfilehash: b17af7931b181a5fa30271a3eee07c7abf10a010
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844028"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a>Granska aviseringar i Microsoft Defender för Slutpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gäller för:**
- [Microsoft Defender för Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Vill du använda Defender för Slutpunkt? [Registrera dig för en kostnadsfri utvärderingsversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

Aviseringssidan i Microsoft Defender för Slutpunkt ger full kontext för aviseringen genom att kombinera attacksignaler och aviseringar relaterade till den valda aviseringen för att skapa en detaljerad aviseringsartikel.

Du kan snabbt organisera, undersöka och vidta effektiva åtgärder på aviseringar som påverkar organisationen. Förstå varför de utlöstes och deras påverkan från en plats. Läs mer i den här översikten.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a>Komma igång med en avisering

Om du väljer namnet på en avisering i Defender för Endpoint hamnar du på aviseringssidan. På aviseringssidan visas all information i samband med den valda aviseringen. Varje aviseringssida består av 4 avsnitt:

1. **Aviseringsrubriken** visar aviseringens namn och finns där för att påminna dig om vilken avisering som startade den aktuella undersökningen oavsett vad du valde på sidan.
2. [**Berörda tillgångar**](#review-affected-assets) visar korten för enheter och användare som påverkas av den här aviseringen som kan klickas för ytterligare information och åtgärder.
3. I **aviseringsartikeln** visas alla enheter som är relaterade till aviseringen, sammankopplade med en trädvy. Aviseringen i rubriken kommer att vara den som är i fokus när du först kommer till den valda aviseringens sida. Enheter i aviseringsinformationen är expanderbara och klickbara, för att ge ytterligare information och underlätta svar genom att göra det möjligt att vidta åtgärder direkt i kontexten för aviseringssidan. Använd aviseringsartikeln för att starta din undersökning. Läs mer i [Undersöka aviseringar i Microsoft Defender för Slutpunkt.](/microsoft-365/security/defender-endpoint/investigate-alerts)
4. I **informationsfönstret** visas först information om den valda aviseringen med information och åtgärder relaterade till den här aviseringen. Om du väljer någon av de berörda tillgångarna eller enheterna i aviseringsinformationen ändras informationsfönstret för att ge sammanhangsberoende information och åtgärder för det valda objektet.

Observera identifieringsstatus för din avisering. 
- Förhindrades – Den misstänkta åtgärden som du försökte undvika. Till exempel har en fil antingen inte skrivits på disken eller körts.
![En aviseringssida som visar att hot har förhindrats](images/detstat-prevented.png)
- Blockerad – Misstänkt beteende utfördes och blockerades sedan. En process utfördes till exempel, men eftersom misstänkt beteende därefter visades i den, avslutas processen.
![En aviseringssida som visar att hot blockerades](images/detstat-blocked.png)
- Upptäckt – En attack identifierades och är eventuellt fortfarande aktiv.
![En aviseringssida som visar att hot har upptäckts](images/detstat-detected.png)




Du kan sedan  också granska automatisk undersökningsinformation i aviseringens informationsfönster för att se vilka åtgärder som redan har vidtagits samt läsa beskrivningen av aviseringen för rekommenderade åtgärder.

![Ett avsnitt av informationsfönstret med aviseringsbeskrivningen och avsnitten för automatisk undersökning markerade](images/alert-air-and-alert-description.png)

Annan information som är tillgänglig i informationsfönstret när aviseringen öppnas innehåller MITRE-tekniker, källa och ytterligare kontextinformation.




## <a name="review-affected-assets"></a>Granska påverkade tillgångar

Om du väljer en enhet eller ett användarkort i avsnitten för de berörda tillgångarna växlas du till informationen om enheten eller användaren i informationsfönstret.

- **För enheter** visar informationsfönstret information om själva enheten, som Domän, Operativsystem och IP. Aktiva aviseringar och inloggade användare på enheten är också tillgängliga. Du kan vidta åtgärder omedelbart genom att isolera enheten, begränsa appkörningen eller köra en antivirussökning. Alternativt kan du samla in ett undersökningspaket, initiera en automatisk undersökning eller gå till enhetssidan för att undersöka ur enhetens perspektiv.

   ![Ett avsnitt av informationsfönstret när en enhet väljs](images/device-page-details.png)

- **För användare** visar informationsfönstret detaljerad användarinformation, till exempel användarens SAM-namn och SID, samt inloggningstyper som utförs av användaren och eventuella aviseringar och incidenter relaterade till den. Du kan välja *Öppna användarsida* för att fortsätta undersökningen från användarens perspektiv.

   ![Ett avsnitt av informationsfönstret när en användare väljs](images/user-page-details.png)


## <a name="related-topics"></a>Relaterade ämnen

- [Visa och ordna incidentkön](view-incidents-queue.md)
- [Undersöka incidenter](investigate-incidents.md)
- [Hantera incidenter](manage-incidents.md)
