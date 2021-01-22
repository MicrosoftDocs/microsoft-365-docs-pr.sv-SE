---
title: Undersöka incidenter i Microsoft 365 Defender
description: Analysera incidenter relaterade till enheter, användare och postlådor.
keywords: incidenter, incidenter, datorer, enheter, användare, identiteter, e-post, e-post, postlåda, undersökning, diagram, bevis
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 6a3bd6be81b4ea4ef11a366267d7a36d45e622b9
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926900"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Undersöka incidenter i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**

- Microsoft 365 Defender

Microsoft 365 Defender sammanställer alla relaterade varningar, tillgångar, undersökningar och bevis från dina enheter, användare och postlådor för att ge dig en fullständig översikt över hela bredden på en attack.

Undersök aviseringarna som påverkar nätverket, förstå vad de betyder och samla in bevis som är associerade med incidenterna så att du kan skapa en effektiv åtgärdsplan.

## <a name="investigate-an-incident"></a>Undersöka en händelse

1. Välj en incident från incidentkön. <BR> En sidopanel öppnas och visar en förhandsgranskning av viktig information, till exempel status, allvarlighetsgrad, kategorier och berörda enheter.

    ![Bild av sidopanelen för incidenter](../../media/incident-side-panel.png)

2. Välj **Sidan Öppna incident.** <BR> Då öppnas incidentsidan där du hittar mer information om incidenter, kommentarer och åtgärder, flikar (översikt, aviseringar, enheter, användare, undersökningar, bevis).

3. Granska aviseringar, enheter, användare och andra enheter som är inblandade i händelsen.

## <a name="incident-overview"></a>Incidentöversikt

Översiktssidan ger en ögonblicksbild av de viktigaste sakerna att lägga märke till om händelsen.

![Bild av sidan med en översikt över incidenter](../../media/incidents-overview.png)

Attackkategorierna ger dig en visuell och numerisk bild av hur avancerad attacken har fortskridt mot avvisningskedjan. Precis som andra Microsoft-säkerhetsprodukter är Microsoft 365 Defender i linje med [MITRE ATT&&trade; CK-ramverket.](https://attack.mitre.org/)

I omfattningsavsnittet visas en lista över de mest påverkade tillgångarna som är en del av den här händelsen. Om det finns specifik information om den här tillgången, t.ex. risknivå, undersökningsprioritet och taggning av tillgångarna, visas detta även i det här avsnittet.

Tidslinjen för aviseringar ger en förhandstitt på den kronologiska ordningen som aviseringarna inträffade i, samt orsakerna till att dessa aviseringar är kopplade till den här händelsen.

Och sista - bevisavsnittet ger en sammanfattning av hur många olika artefakter som inkluderades i händelsen och deras åtgärdsstatus, så att du direkt kan se om någon åtgärd behövs på din slutpunkt.

Den här översikten kan hjälpa dig med den initiala triangeln av incidenten genom att ge information om de viktigaste egenskaperna för incidenten som du bör känna till.

## <a name="alerts"></a>Varningar

Du kan visa alla aviseringar som rör incidenten och annan information om dem, till exempel allvarlighetsgrad, enheter som var inblandade i aviseringen, källan till aviseringarna (Microsoft Defender för identitet, Microsoft Defender för slutpunkt, Microsoft Defender för Office 365) och orsaken till att de länkades ihop.

![Bild på sidan incidentaviseringar](../../media/incident-alerts.png)

Som standard ordnas aviseringarna kronologiskt så att du först kan se hur attacken utspelas med tiden. Om du klickar på varje avisering kommer du till den relevanta aviseringssidan där du kan göra en detaljerad undersökning av den aviseringen.

## <a name="devices"></a>Enheter

På fliken enheter visas alla enheter där aviseringar om händelsen visas.

Om du klickar på namnet på den dator där attacken utfördes kommer du till sidan Dator där du kan se aviseringar som utlösts för den och relaterade händelser för att underlätta undersökning.

![Bild på fliken Datorer för ett incident](../../media/incident-machines.png)

Om du väljer fliken Tidslinje kan du bläddra igenom datorns tidslinje och visa alla händelser och beteenden som observerats på datorn i kronologisk ordning, uppkopplade med aviseringarna upphöjda.

## <a name="users"></a>Användare

Se användare som har identifierats vara en del av eller relaterade till en viss händelse.

Om du klickar på användarnamnet kommer du till sidan Molnappsäkerhet där ytterligare undersökning kan utföras.

![Bild på fliken Användare för ett incident](../../media/incident-users.png)

## <a name="mailboxes"></a>Postlådor

Undersök postlådor som har identifierats som en del av eller som är relaterade till en händelse. För att det ska fungera ytterligare kan du välja den e-postrelaterade aviseringen och öppna Microsoft Defender för Office 365 där du kan vidta åtgärder.

![Bild av fliken Postlåda för ett incident](../../media/incident-mailboxes.png)

## <a name="investigations"></a>Undersökningar

Välj **Undersökningar** för att se alla automatiserade undersökningar som utlösts av varningar i den här incidenten. Undersökningarna utförs åtgärdsåtgärder eller väntar på analytikers godkännande av åtgärder, beroende på hur du konfigurerat dina automatiserade undersökningar att köras i Microsoft Defender för Endpoint och Defender för Office 365.

![Bild av fliken undersökningar för en incident](../../media/incident-investigations.png)

Välj en undersökning för att navigera till sidan Undersökningsinformation för att få fullständig information om undersöknings- och åtgärdsstatus. Om det finns åtgärder som väntar på godkännande som en del av undersökningen visas de på fliken Väntande åtgärder. Vidta åtgärder som en del av åtgärder för incidenter.

## <a name="evidence"></a>Bevis

Microsoft 365 Defender undersöker automatiskt alla händelser som stöds och misstänkta enheter i aviseringarna, vilket ger dig autosvar samt information om viktiga filer, processer, tjänster, e-postmeddelanden med mera. Det här hjälper snabbt till att identifiera och blockera potentiella hot i incidenten.

![Bild av bevisfliken för en händelse](../../media/incident-evidence.png)

Var och en av de analyserade enheterna markeras med en bedömning (skadlig, misstänkt, ren) samt en åtgärdsstatus. På så sätt får du en bättre förståelse för åtgärdsstatusen för hela händelsen och vilka nästa steg du kan vidta för att åtgärda ytterligare.

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över incidenter](incidents-overview.md)
- [Prioritera incidenter](incident-queue.md)
- [Hantera incidenter](manage-incidents.md)

