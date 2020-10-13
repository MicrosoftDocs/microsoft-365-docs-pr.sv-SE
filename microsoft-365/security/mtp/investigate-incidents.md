---
title: Undersök incidenter i skydd mot Microsoft Threat
description: Analysera händelser relaterade till enheter, användare och post lådor.
keywords: incident, händelser, datorer, enheter, användare, identiteter, e-post, e-post, brev låda, undersökning, Graf, bevis
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 7a4e901c016d55115eb79001ff2fc42d2340f8f2
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430603"
---
# <a name="investigate-incidents-in-microsoft-threat-protection"></a>Undersök incidenter i skydd mot Microsoft Threat

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**

- Microsoft Threat Protection

Microsoft Threat Protection aggregerar alla relaterade aviseringar, till gångar, undersökningar och fakta från enheter, användare och post lådor för att ge dig en omfattande titt på hela bredden på en attack.

Undersök vilka aviseringar som påverkar ditt nätverk, förstå vad de betyder och samla in bevis som är kopplade till incidenterna så att du kan utforma en effektiv reparations plan.

## <a name="investigate-an-incident"></a>Undersök en olycka

1. Välj en incident från incident kön. <BR> Då öppnas en sido panel med en förhands granskning av viktig information som status, allvarlighets grad, kategorier och berörda enheter.

    ![Bild av panelen tillbud](../../media/incident-side-panel.png)

2. Välj **Open incident-sida**. <BR> Då öppnas sidan incident där du hittar mer information om incidenter, kommentarer och åtgärder, flikar (översikt, notifieringar, enheter, användare, undersökningar, bevis).

3. Granska aviseringar, enheter, användare, andra enheter inblandade i incidenten.

## <a name="incident-overview"></a>Incident översikt

Med översikts sidan kan du snabbt och enkelt se en ögonblicks bild.

![Bild av översikts sidan för incidenter](../../media/incidents-overview.png)

I angrepps kategorierna får du visuell och numerisk vy av hur Avancerat angreppet har framskridit mot Kill-kedjan. Precis som med andra Microsoft-säkerhetsprodukter är skydd mot Microsoft Threat det [Mitre för&CK &trade; ](https://attack.mitre.org/) -ramverk.

I avsnittet omfattning får du en lista över de mest berörda till gångarna som är en del av den här incidenten. Om det finns specifik information om den här till gången, till exempel risk nivå, undersöknings prioritet och eventuella taggning på till gångar, visas även i det här avsnittet.

Tids linjen för påminnelser ger en förhandstitt på den kronologiska ordning i vilken aviseringarna inträffade, samt orsakerna till att dessa varningar är länkade till denna incident.

Och sist-beviset visar en sammanfattning av hur många olika artefakter som ingår i incidenten och deras reparations status, så att du omedelbart kan avgöra om en åtgärd krävs för ditt slut.

Denna översikt kan hjälpa till med den inledande postsortering av incidenten genom att ge insyn i de viktigaste egenskaperna hos den olycka som du bör vara medveten om.

## <a name="alerts"></a>Varningar

Du kan visa alla aviseringar som rör incidenten och annan information om dem, till exempel allvarlighets grad, enheter som ingick i aviseringen, källan till aviseringarna (Azure ATP, Microsoft Defender ATP, Office 365 ATP) och anledningen till att de sammanlänkade.

![Bild av sidan incident aviseringar](../../media/incident-alerts.png)

Som standard ordnas aviseringarna kronologiskt, så att du kan se hur angreppet spelas upp med tiden. Om du klickar på varje varning kommer du till relevant aviserings sida där du kan genomföra en djupgående undersökning av den aviseringen.

## <a name="devices"></a>Anordningar

På fliken enheter visas alla enheter där aviseringar som rör händelsen är synliga.

Om du klickar på namnet på den dator där angreppet har gjorts navigerar du till dess dator sida där du kan se de meddelanden som utlöstes med den och relaterade händelser för att under lätta undersökningen.

![Fliken dator med en olycka](../../media/incident-machines.png)

Om du väljer fliken tids linje kan du bläddra igenom datorns tids linje och Visa alla händelser och funktioner som observerats på datorn i kronologisk ordning, direkt med aviseringar.

## <a name="users"></a>Användare

Se vilka användare som har identifierats som en del av eller är relaterade till en viss olycka.

Om du klickar på användar namnet navigerar du till användarens moln program säkerhets sida där ytterligare undersökningar kan genomföras.

![Bild av fliken användare i en händelse](../../media/incident-users.png)

## <a name="mailboxes"></a>Post lådor

Undersök brev lådor som har identifierats som en del av eller är relaterade till en olycka. Om du vill göra ytterligare utrednings arbete genom att välja e-postrelaterad varning öppnas Office 365 Avancerat skydd där du kan utföra reparations åtgärder.

![Bild av fliken post låda med en olycka](../../media/incident-mailboxes.png)

## <a name="investigations"></a>Utredningar

Välj **undersökningar** för att se alla automatiserade utredningar som utlöstes av notifieringar under den här incidenten. Undersökningen utför reparations åtgärder eller väntar på att godkänna godkännande av åtgärder, beroende på hur du har konfigurerat dina automatiserade utredningar att köra i Microsoft Defender ATP och Office 365 Avancerat skydd.

![Bild av fliken undersökningar under en olycka](../../media/incident-investigations.png)

Välj en undersökning för att gå till sidan med gransknings informationen för att få fullständig information om undersökningen och reparations status. Om det finns några åtgärder som väntar på godkännande som en del av undersökningen kommer de att synas på fliken väntande åtgärder. Vidta en åtgärd som en del av incident åtgärden.

## <a name="evidence"></a>Läggs

Microsoft Threat Protection undersöker automatiskt alla händelser och misstänkta enheter som stöds av incidenter och ger dig automatiskt svar och information om viktiga filer, processer, tjänster, e-postmeddelanden och annat. Det gör det enkelt att upptäcka och blockera potentiella hot i olyckan.

![Bild av fliken bevis för en olycka](../../media/incident-evidence.png)

Alla analyserade enheter markeras med en Verdict (skadlig, misstänkt, ren) och en reparations status. Det här hjälper dig att förstå reparations status för hela incidenten och vilka som är nästa steg som kan åtgärdas.

## <a name="related-topics"></a>Relaterade ämnen

- [Incident översikt](incidents-overview.md)
- [Prioritera incidenter](incident-queue.md)
- [Hantera incidenter](manage-incidents.md)

