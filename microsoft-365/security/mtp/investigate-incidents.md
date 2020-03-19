---
title: Undersöka incidenter i Microsoft Threat Protection
description: Analysera incidenter relaterade till enheter, användare och postlådor.
keywords: incident, incidenter, maskiner, enheter, användare, identiteter, e-post, e-post, brevlåda, utredning, graf, bevis
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 82069224a3f38357e52c2772c984d20d6597342d
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857493"
---
# <a name="investigate-incidents-in-microsoft-threat-protection"></a>Undersöka incidenter i Microsoft Threat Protection

**Gäller:**

- Skydd av Hot mot Microsoft

Microsoft Threat Protection sammanställer alla relaterade varningar, tillgångar, undersökningar och bevis från alla dina enheter, användare och postlådor för att ge dig en omfattande titt på hela bredden av en attack.

Undersök aviseringarna som påverkar nätverket, förstå vad de betyder och samla bevis som är associerade med incidenterna så att du kan utforma en effektiv reparationsplan.

## <a name="investigate-an-incident"></a>Utreda en incident

1. Välj en incident i incidentkön. <BR> Detta öppnar en sidopanel och ger en förhandsgranskning av viktig information som status, allvarlighetsgrad, kategorier och de enheter som påverkas.

    ![Bild av panelen incidentsida](../../media/incident-side-panel.png)

2. Välj **Öppna incidentsida**. <BR> Detta öppnar incidentsidan där du hittar mer information om information om information om information, kommentarer och åtgärder, flikar (översikt, aviseringar, enheter, användare, utredningar, bevis).

3. Granska aviseringar, enheter, användare, andra enheter som är inblandade i incidenten.

## <a name="incident-overview"></a>Översikt över incidenter

Översiktssidan ger dig en ögonblicksbild blick i de bästa sakerna att märka om händelsen.

![Bild av översiktssidan för incidenter](../../media/incidents-overview.png)

Attackkategorierna ger dig visuell och numerisk bild av hur avancerad attacken har utvecklats mot dödskedjan. Precis som med andra Microsoft-säkerhetsprodukter är Microsoft Threat Protection anpassat till [MITRE&trade; ATT-ramverket för&CK.](https://attack.mitre.org/)

I scopeavsnittet visas en lista över högst påverkade tillgångar som ingår i den här incidenten. Om det finns specifik information om denna tillgång, till exempel risknivå, undersökningsprioritet samt eventuella märkning på tillgångarna kommer detta också att visas i det här avsnittet.

Varningstidslinjen ger en smygtitt på den kronologiska ordning i vilken aviseringarna inträffade, samt skälen till att dessa varningar kopplade till den här incidenten.

Och sist - bevisavsnittet ger en sammanfattning av hur många olika artefakter som ingick i incidenten och deras saneringsstatus, så att du omedelbart kan identifiera om någon åtgärd behövs i slutet.

Denna översikt kan hjälpa till i den första triage av händelsen genom att ge insikt i de bästa egenskaperna hos den incident som du bör vara medveten om.

## <a name="alerts"></a>Varningar

Du kan visa alla aviseringar som är relaterade till incidenten och annan information om dem, till exempel allvarlighetsgrad, entiteter som var inblandade i aviseringen, källan till aviseringarna (Azure ATP, Microsoft Defender ATP , Office 365 ATP) och anledningen till att de länkades samman.

![Bild av sidan för incidentaviseringar](../../media/incident-alerts.png)

Som standard ordnas aviseringarna kronologiskt, så att du först kan se hur attacken utspelade sig över tid. Om du klickar på varje avisering leder du till den relevanta varningssidan där du kan göra en fördjupad undersökning av aviseringen.

## <a name="devices"></a>Enheter

På fliken Enheter visas alla enheter där aviseringar som är relaterade till incidenten visas.

Om du klickar på namnet på den maskin där attacken utfördes navigerar du till dess maskinsida där du kan se aviseringar som utlöstes på den och relaterade händelser som tillhandahålls för att underlätta undersökningen.

![Bild av fliken datorer för en incident](../../media/incident-machines.png)

Genom att välja fliken Tidslinje kan du bläddra igenom maskinens tidslinje och visa alla händelser och beteenden som observerats på datorn i kronologisk ordning, varvat med aviseringarna uppfällda.

## <a name="users"></a>Användare

Se användare som har identifierats som en del av eller relaterade till en viss incident.

Om du klickar på användarnamnet navigeras dig till användarens cloud app-säkerhetssida där ytterligare undersökningar kan genomföras.

![Bild av fliken användare i en incident](../../media/incident-users.png)

## <a name="mailboxes"></a>Postlådor

Undersök postlådor som har identifierats som en del av eller relaterade till en incident. Om du vill utföra ytterligare undersökande öppnas Office 365 Advanced Threat Protection där du kan vidta åtgärder för reparation genom att välja e-postrelaterad avisering.

![Bild av fliken postlåda för en incident](../../media/incident-mailboxes.png)

## <a name="investigations"></a>Utredningar

Välj **Undersökningar** om du vill visa alla automatiska undersökningar som utlöses av aviseringar i den här incidenten. Undersökningarna kommer att utföra reparationsåtgärder eller vänta på analytikergodkännande av åtgärder, beroende på hur du konfigurerade dina automatiserade undersökningar för att köra i Microsoft Defender ATP och Office 365 Advanced Threat Protection.

![Bild av fliken utredningar av en incident](../../media/incident-investigations.png)

Välj en undersökning för att navigera till sidan Utredningsinformation för att få fullständig information om undersöknings- och reparationsstatusen. Om det finns några åtgärder som väntar på godkännande som en del av undersökningen visas de på fliken Väntande åtgärder. Vidta åtgärder som en del av förmedlingen.

## <a name="evidence"></a>Bevis

Microsoft Threat Protection undersöker automatiskt alla incidenters händelser som stöds och misstänkta entiteter i aviseringarna, vilket ger dig automatiskt svar och information om viktiga filer, processer, tjänster, e-postmeddelanden med mera. Detta hjälper snabbt upptäcka och blockera potentiella hot i händelsen.

![Bild av bevis fliken för en incident](../../media/incident-evidence.png)

Var och en av de analyserade entiteterna markeras med en dom (Skadlig, misstänkt, ren) samt en reparationsstatus. Detta hjälper dig att förstå reparationsstatus för hela incidenten och vilka är nästa steg som kan vidtas för att ytterligare åtgärda.

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över incidenter](incidents-overview.md)
- [Prioritera incidenter](incident-queue.md)
- [Hantera incidenter](manage-incidents.md)
- [Granska händelser och aviseringar på en viss dator](machine-profile.md)
