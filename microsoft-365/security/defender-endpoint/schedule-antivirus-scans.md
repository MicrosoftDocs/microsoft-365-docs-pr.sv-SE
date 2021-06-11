---
title: Schemalägg vanliga snabba och fullständiga skanningar med Microsoft Defender Antivirus
description: Konfigurera återkommande (schemalagda) genomsökningar, inklusive när de ska köras och om de körs som fullständiga eller snabba genomsökningar
keywords: snabbsökning, fullständig sökning, snabb jämfört med full, schemasökning, dagligen, veckovis, tid, schemalagd, återkommande, vanlig
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 5566050e4a64713f6f8b4ac2cb4a7188d3a241c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879784"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Konfigurera schemalagda snabb- eller fullständiga genomsökningar för Microsoft Defender Antivirus

**Gäller för:**

- [Microsoft Defender för Endpoint](/microsoft-365/security/defender-endpoint/)

Förutom att alltid ha realtidsskydd och [](run-scan-microsoft-defender-antivirus.md) antivirussökningar på begäran kan du konfigurera vanliga, schemalagda antivirussökningar. Du kan konfigurera typ av genomsökning, när genomsökningen ska ske [](manage-protection-updates-microsoft-defender-antivirus.md) och om genomsökningen ska ske efter en skyddsuppdatering eller när en slutpunkt inte används. Du kan också ställa in särskilda genomsökningar för att slutföra åtgärder om det behövs.

## <a name="what-do-you-want-to-do"></a>Vad vill du göra?

- [Läs mer om snabba skanningar, fullständiga skanningar och anpassade skanningar](#quick-scan-full-scan-and-custom-scan)
- [Använda grupprinciper för att schemalägga antivirussökningar](schedule-antivirus-scans-group-policy.md)
- [Använda Windows PowerShell för att schemalägga antivirussökningar](schedule-antivirus-scans-powershell.md)
- [Använda Windows Management Instrumentation för att schemalägga antivirussökningar](schedule-antivirus-scans-wmi.md)

## <a name="keep-the-following-points-in-mind"></a>Tänk på följande

- Som standard söker Microsoft Defender Antivirus efter en uppdatering 15 minuter före tiden för schemalagda sökningar. Du kan [Hantera schemat för när skyddsuppdateringar ska laddas ned och användas för att åsidosätta](manage-protection-update-schedule-microsoft-defender-antivirus.md) den här standardinställningen. 

- Om en enhet är urkopplad och körs på batteriet vid en schemalagd fullständig genomsökning stoppas den schemalagda skanningen med händelse 1002, vilket innebär att skanningen stoppades innan den slutförddes. Microsoft Defender Antivirus en fullständig sökning vid nästa schemalagda tid.

## <a name="quick-scan-full-scan-and-custom-scan"></a>Snabbsökning, fullständig sökning och anpassad sökning

När du ställer in schemalagda genomsökningar kan du ange om den ska vara en fullständig eller snabb genomsökning. I de flesta fall rekommenderas en snabbsökning. 

| Snabbsökning  | Fullständig sökning  | Anpassad sökning |
|---------|---------|---------|
| (Rekommenderas) En snabb genomsökning av alla platser där skadlig programvara kan registreras för att börja med systemet, till exempel registernycklar och kända Windows startmappar. <p>I kombination med ständigt realtidsskydd som granskar filer när de öppnas och stängs, och när en användare navigerar till en mapp ger en snabb genomsökning ett starkt skydd mot skadlig programvara som börjar med system- och kernel-nivå-skadlig programvara. <p>I de flesta fall är en snabbsökning tillräcklig och är det rekommenderade alternativet för schemalagda skanningar. | En fullständig genomsökning påbörjas genom att köra en snabb genomsökning, och sedan fortsätter den med en sekventiell genomsökning av alla fasta diskmonter och flyttbara/nätverksenheter (om den fullständiga genomsökningen är konfigurerad att göra det). <p>En fullständig genomsökning kan ta några timmar eller dagar att slutföra, beroende på hur mycket och vilken typ av data som behöver skannas.<p>När den fullständiga genomsökningen är klar är ny säkerhetsinformation tillgänglig och en ny genomsökning krävs sedan för att se till att inga andra hot upptäcks med den nya säkerhetsintelligensen. <p>På grund av den tid och de resurser som ingår i en fullständig genomsökning rekommenderar Microsoft i allmänhet inte att du schemalägger fullständiga genomsökningar.  | En anpassad genomsökning är en snabbsökning som körs på de filer och mappar som du anger. Du kan till exempel välja att skanna en USB-enhet eller en särskild mapp på enhetens lokala enhet. <p> | 

> [!NOTE]
> Som standard körs snabbsökningar påmonterade flyttbara enheter, till exempel USB-enheter.

## <a name="how-do-i-know-which-scan-type-to-choose"></a>Hur vet jag vilken skanningstyp jag ska välja?

Använd följande tabell för att välja en genomsökningstyp.

| Scenario  | Rekommenderad genomsökningstyp  |
|---------|---------|
| Du vill ställa in vanliga, schemalagda genomsökningar     | Snabbsökning <p>En snabb genomsökning kontrollerar processer, minne, profiler och vissa platser på enheten. I kombination [med realtidsskydd ger](configure-real-time-protection-microsoft-defender-antivirus.md)en snabb genomsökning stark täckning både för skadlig programvara som börjar med skadlig programvara på system- och kernel-nivå. Realtidsskydd granskar filer när de öppnas och stängs, och när en användare navigerar till en mapp.         |
| Hot, till exempel skadlig kod, upptäcks på en enskild enhet     | Snabbsökning <p>I de flesta fall fångar och rensar en snabbsökning efter skadlig programvara.   |
| Du vill köra en [sökning på begäran](run-scan-microsoft-defender-antivirus.md)     | Snabbsökning       |
| Du vill kontrollera att en bärbar enhet, till exempel en USB-enhet, inte innehåller skadlig programvara | Anpassad sökning <p>Med en anpassad genomsökning kan du välja specifika platser, mappar eller filer och göra en snabbsökning. |

## <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>Vad mer behöver jag veta om snabba och fullständiga skanningar?

- Skadliga filer kan lagras på platser som inte ingår i en snabbsökning. Skydd i realtid granskar emellertid alla filer som öppnas och stängs och alla filer som finns i mappar som en användare har åtkomst till. Kombinationen av realtidsskydd och en snabb genomsökning ger ett starkt skydd mot skadlig programvara.

- Skydd vid åtkomst med moln levererat [skydd](cloud-protection-microsoft-defender-antivirus.md) hjälper till att säkerställa att alla filer som används i systemet genomsöks med de senaste säkerhetsintelligens- och maskininlärningsmodellerna.

- När realtidsskyddet identifierar skadlig programvara och omfattningen av de berörda filerna inte fastställts först initierar Microsoft Defender Antivirus en fullständig genomsökning som en del av åtgärdsprocessen.

- En fullständig genomsökning kan identifiera skadliga filer som inte identifierats av andra genomsökningar, till exempel en snabbsökning. Men en fullständig genomsökning kan ta en stund och använda värdefulla systemresurser för att slutföra.

- Om en enhet är offline under en längre tid kan en fullständig genomsökning ta längre tid att slutföra. 

