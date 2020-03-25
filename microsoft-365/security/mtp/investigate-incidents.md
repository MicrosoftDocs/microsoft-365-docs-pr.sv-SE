---
title: Undersöka incidenter i Microsofts hotskydd
description: Analysera incidenter relaterade till enheter, användare och postlådor.
keywords: incident, incidenter, maskiner, enheter, användare, identiteter, e-post, e-post, brevlåda, undersökning, diagram, bevis
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
ms.openlocfilehash: 1883f61f50dad9b601329369bf180ddecba70138
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928968"
---
# <a name="investigate-incidents-in-microsoft-threat-protection"></a>Undersöka incidenter i Microsofts hotskydd

**Gäller:**

- Microsofts hotskydd

Microsoft Threat Protection sammanställer alla relaterade aviseringar, tillgångar, undersökningar och bevis från alla dina enheter, användare och postlådor för att ge dig en omfattande titt på hela bredden av en attack.

Undersök aviseringar som påverkar ditt nätverk, förstå vad de betyder och samla bevis i samband med incidenter så att du kan utforma en effektiv reparationsplan.

## <a name="investigate-an-incident"></a>Utreda en incident

1. Välj en incident från incidentkön. <BR> Detta öppnar en sidopanel och ger en förhandsgranskning av viktig information som status, allvarlighetsgrad, kategorier och påverkade entiteter.

    ![Bild av sidopanelen för incidenten](../../media/incident-side-panel.png)

2. Välj **Öppna incidentsida**. <BR> Då öppnas incidentsidan där du hittar mer information om incidentinformation, kommentarer och åtgärder, flikar (översikt, aviseringar, enheter, användare, undersökningar, bevis).

3. Granska aviseringar, enheter, användare, andra enheter som är inblandade i incidenten.

## <a name="incident-overview"></a>Översikt över incidenter

Översiktssidan ger dig en ögonblicksbild blick i de översta sakerna att märka om händelsen.

![Bild av översiktssidan för incidenter](../../media/incidents-overview.png)

Attackkategorierna ger dig visuell och numerisk bild av hur avancerad attacken har utvecklats mot dödskedjan. Precis som med andra Microsoft-säkerhetsprodukter är Microsoft Threat Protection anpassat till [MITRE ATT-&&trade; CK-ramverket.](https://attack.mitre.org/)

Avsnittet Omfång ger dig en lista över de mest påverkade tillgångarna som ingår i den här incidenten. Om det finns specifik information om denna tillgång, såsom risknivå, undersökningsprioritet samt eventuell märkning på tillgångarna kommer detta också att dyka upp i detta avsnitt.

Tidslinjen för aviseringar ger en smygtitt på den kronologiska ordning i vilken aviseringarna inträffade, liksom orsakerna till att dessa aviseringar kopplade till den här incidenten.

Och sist - bevisavsnittet ger en sammanfattning av hur många olika artefakter som ingick i incidenten och deras reparationsstatus, så att du omedelbart kan identifiera om någon åtgärd behövs på din sida.

Denna översikt kan hjälpa till i den första triage av händelsen genom att ge insikt i de bästa egenskaperna hos händelsen som du bör vara medveten om.

## <a name="alerts"></a>Varningar

Du kan visa alla aviseringar som är relaterade till incidenten och annan information om dem, till exempel allvarlighetsgrad, entiteter som var inblandade i aviseringen, källan till aviseringarna (Azure ATP, Microsoft Defender ATP , Office 365 ATP) och anledningen till att de var sammankopplade.

![Bild på sidan incidentvarningar](../../media/incident-alerts.png)

Som standard ordnas aviseringarna kronologiskt så att du först kan se hur attacken utspelade sig över tid. Om du klickar på varje avisering leder du till den relevanta aviseringssidan där du kan göra en fördjupad undersökning av den aviseringen.

## <a name="devices"></a>Enheter

På fliken Enheter visas alla enheter där aviseringar relaterade till incidenten visas.

Om du klickar på namnet på den dator där attacken utfördes navigerar du till dess maskinsida där du kan se aviseringar som utlöstes på den och relaterade händelser som tillhandahålls för att underlätta undersökningen.

![Bild av datorer fliken för en incident](../../media/incident-machines.png)

Om du väljer fliken Tidslinje kan du bläddra igenom maskinens tidslinje och visa alla händelser och beteenden som observerats på datorn i kronologisk ordning, varvat med aviseringarna upp.

## <a name="users"></a>Användare

Se användare som har identifierats vara en del av eller relaterade till en viss incident.

Om du klickar på användarnamnet navigeras du till användarens Cloud App Security-sida där ytterligare undersökningar kan utföras.

![Bild på fliken användare i en incident](../../media/incident-users.png)

## <a name="mailboxes"></a>Postlådor

Undersök postlådor som har identifierats för att vara en del av eller relaterade till en incident. Om du vill utföra ytterligare utredningsarbete öppnas Office 365 Advanced Threat Protection där du kan vidta åtgärder för att upptäcka e-postrelaterade åtgärder.

![Bild på fliken postlåda för en incident](../../media/incident-mailboxes.png)

## <a name="investigations"></a>Utredningar

Välj **Undersökningar om** du vill se alla automatiserade undersökningar som utlöses av varningar i den här incidenten. Undersökningarna utför reparationsåtgärder eller väntar på analytikergodkännande av åtgärder, beroende på hur du konfigurerade dina automatiska undersökningar för att köras i Microsoft Defender ATP och Office 365 Advanced Threat Protection.

![Bild av utredningar fliken av en incident](../../media/incident-investigations.png)

Välj en undersökning för att navigera till sidan Undersökningsinformation för att få fullständig information om undersöknings- och reparationsstatus. Om det finns några åtgärder som väntar på godkännande som en del av undersökningen visas de på fliken Väntande åtgärder. Vidta åtgärder som en del av incidentens reparation.

## <a name="evidence"></a>Bevis

Microsoft Threat Protection undersöker automatiskt alla incidenters händelser som stöds och misstänkta entiteter i aviseringarna, vilket ger dig automatisk respons och information om viktiga filer, processer, tjänster, e-postmeddelanden med mera. Detta hjälper till att snabbt upptäcka och blockera potentiella hot i incidenten.

![Bild på fliken bevis för en incident](../../media/incident-evidence.png)

Var och en av de analyserade entiteterna markeras med en dom (Skadlig, Misstänkt, Ren) samt en reparationsstatus. Detta hjälper dig att förstå saneringsstatus för hela incidenten och vilka är de nästa steg som kan vidtas för att ytterligare åtgärda.

## <a name="related-topics"></a>Relaterade ämnen

- [Översikt över incidenter](incidents-overview.md)
- [Prioritera incidenter](incident-queue.md)
- [Hantera incidenter](manage-incidents.md)

