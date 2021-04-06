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
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
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
ms.openlocfilehash: a6c7e7e920d18d9d8bf29d71d317008ea0c37bbf
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592102"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Undersöka incidenter i Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**

- Microsoft 365 Defender

Microsoft 365 Defender sammanställer alla relaterade aviseringar, tillgångar, undersökningar och bevis från olika enheter, användare och postlådor för att ge dig en fullständig översikt över hela attacken.

Undersök aviseringarna som påverkar nätverket, förstå vad de betyder och samla bevis som är associerade med incidenterna så att du kan skapa en gällande åtgärdsplan.

## <a name="investigate-an-incident"></a>Undersöka en händelse

1. Välj en incident i incidentkön. <BR> En sidopanel öppnas och visar en förhandsgranskning av viktig information, till exempel status, allvarlighetsgrad, kategorier och berörda enheter.

    ![Bild på sidopanelen för incidenter](../../media/incident-side-panel.png)

2. Välj **Öppna incidentsida**. <BR> Då öppnas incidentsidan där du hittar mer information om incidenter, kommentarer och åtgärder, flikar (översikt, aviseringar, enheter, användare, undersökningar, bevis).

3. Granska aviseringar, enheter, användare och andra enheter som är inblandade i händelsen.

## <a name="incident-overview"></a>Incidentöversikt

På översiktssidan får du en ögonblicksbild av de viktigaste sakerna att lägga märke till om händelsen.

![Bild på översiktssidan för incidenter](../../media/incidents-overview.png)

Attackkategorierna ger dig en visuell och numerisk vy av hur avancerat attacken har fortskridt mot kill chain. Precis som andra Microsoft-säkerhetsprodukter är Microsoft 365 Defender i linje med [MITRE ATT&&trade; CK-ramverket.](https://attack.mitre.org/)

I omfattningsavsnittet visas en lista över de viktigaste tillgångar som är en del av den här händelsen. Om det finns specifik information om den här tillgången, till exempel risknivå, undersökningsprioritering och taggning av tillgångarna, visas detta även i det här avsnittet.

På tidslinjen med aviseringar får du en förhandstitt på den kronologiska ordningen som aviseringarna uppstod i, samt orsakerna till att aviseringarna är kopplade till den här händelsen.

Och sist – bevisavsnittet innehåller en sammanfattning av hur många olika artefakter som inkluderades i händelsen och deras åtgärdsstatus, så att du genast kan se om någon åtgärd behövs på din slutpunkt.

Den här översikten kan hjälpa dig med den initiala genomgången av incidenten genom att ge information om de viktigaste egenskaperna för incidenten som du bör känna till.

## <a name="alerts"></a>Varningar

Du kan visa alla aviseringar som rör händelsen och annan information om dem, till exempel allvarlighetsgrad, enheter som var inblandade i aviseringen, källan till aviseringarna (Microsoft Defender för identitet, Microsoft Defender för slutpunkt, Microsoft Defender för Office 365) och orsaken till att de länkades ihop.

![Bild på sidan incidentaviseringar](../../media/incident-alerts.png)

Som standard sorteras aviseringarna kronologiskt så att du först kan se hur attacken utspelas med tiden. Om du klickar på varje avisering kommer du till den relevanta aviseringssidan där du kan undersöka den aviseringen på djupet. Lär dig hur du använder aviseringssidor och den enhetliga aviseringskön i [Undersöka aviseringar](investigate-alerts.md)

## <a name="devices"></a>Enheter

På fliken Enheter visas alla enheter där aviseringar om händelsen visas.

Om du klickar på namnet på den dator där attacken utfördes navigeras du till sidan Dator där du kan se aviseringar som utlöstes på den och relaterade händelser för att underlätta undersökning.

![Bild på fliken datorer för ett incident](../../media/incident-machines.png)

Genom att välja fliken Tidslinje kan du bläddra igenom datorns tidslinje och visa alla händelser och beteenden som observerats på datorn i kronologisk ordning, uppkopplade med aviseringarna upphöjda.

> [!TIP]
> Du kan göra genomsökningar på begäran på en enhet. I Säkerhetscenter för Microsoft 365 väljer du **Enhetsinventering**. Välj en enhet med aviseringar och kör sedan en antivirussökning. Åtgärder, till exempel antivirusskanningar, spåras och visas på sidan **Enhetsinventering.** Mer information finns i Kör [sökning efter Microsoft Defender Antivirus på enheter.](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)


## <a name="users"></a>Användare

Se användare som har identifierats vara en del av eller relaterade till en viss händelse.

När du klickar på användarnamnet navigeras du till sidan Säkerhet i Molnappen där vidare undersökning kan genomföras.

![Bild på fliken Användare för ett incident](../../media/incident-users.png)

## <a name="mailboxes"></a>Postlådor

Undersök postlådor som har identifierats som en del av eller relaterade till ett problem. Om du vill utföra ytterligare åtgärder kan du välja den e-postrelaterade aviseringen för att öppna Microsoft Defender för Office 365, där du kan vidta åtgärder.

![Bild av postlådefliken för ett incident](../../media/incident-mailboxes.png)

## <a name="investigations"></a>Undersökningar

Välj **Undersökningar** om du vill se alla automatiserade undersökningar som utlösts av aviseringar om den här händelsen. Undersökningarna utför åtgärder eller väntar på analytikernas godkännande av åtgärder, beroende på hur du konfigurerat dina automatiska undersökningar att köras i Microsoft Defender för Endpoint och Defender för Office 365.

![Bild på fliken för undersökningar för ett incident](../../media/incident-investigations.png)

Välj en undersökning för att gå till sidan Undersökningsinformation för att få fullständig information om undersöknings- och åtgärdsstatus. Om det finns åtgärder som väntar på godkännande som en del av undersökningen visas de på fliken Väntande åtgärder. Vidta åtgärder som en del av åtgärder för incidenter.

## <a name="evidence"></a>Bevis

Microsoft 365 Defender undersöker automatiskt alla händelser som stöds och misstänkta enheter i aviseringarna, vilket ger dig information om viktiga filer, processer, tjänster, e-postmeddelanden med mera. Det här hjälper dig att snabbt identifiera och blockera potentiella hot i händelsen.

![Bild av bevisfliken för en händelse](../../media/incident-evidence.png)

Var och en av de analyserade enheterna markeras med en bedömning (skadlig, misstänkt, ren) samt en åtgärdsstatus. På så sätt får du en bättre förståelse för statusen för hela händelsen och vad som är nästa steg som kan åtgärdas ytterligare.

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över incidenter](incidents-overview.md)
- [Prioritera incidenter](incident-queue.md)
- [Hantera incidenter](manage-incidents.md)

