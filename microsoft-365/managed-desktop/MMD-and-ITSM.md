---
title: Microsoft Managed Desktop och ITIL
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation, ITISM
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: bd03331bc27b68017ced179627ec02cb95616611
ms.sourcegitcommit: c6ee468b4aeb3684d332cb79f5cd121f60f32d3e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/18/2019
ms.locfileid: "42805858"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft Managed Desktop och ITIL

Många organisationer tycker att det är värdefullt att strukturera sina IT-tjänster i linje med en formaliserad IT Service Model (ITSM), såsom [ITIL](https://www.axelos.com/best-practice-solutions/itil). 

Med Microsoft Managed Desktop kan din organisation följa många viktiga aspekter av sådana formaliserade ITSM-modeller. Med ITIL som exempel hjälper det här avsnittet dig att se anslutningarna mellan vanliga ITIL-faser och processer och motsvarande Microsoft Managed Desktop-funktioner, där så är tillämpligt. Detta gäller endast för delen Microsoft Managed Desktop i organisationen.

För mer omfattande om ITIL och dess faser och process se deras [dokumentation](https://www.axelos.com/best-practice-solutions/itil).


## <a name="service-design"></a>Design av tjänster

Den här tabellen relaterar viktiga ITIL-faser och processer till Microsoft Managed Desktop-funktioner, med länkar till vår dokumentation för mer information:



|ITIL-processen |Beskrivning  |Dokumentation |
|---------|---------|---------|
|Hantering på servicenivå     | Svarstider har definierats för administratörssupportförfrågningar och incidenter.  |  [Administratörsstöd för Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)  |
|Hantering av tjänstkataloger     | Servicebeskrivning med uppgifter om komponenter i tjänsten hålls trogen tjänstens tillstånd, tillgängligt för alla aktuella och intresserade kunder.<br><br>Förutsättningar detaljerade för att förstå vad som behövs för att driva tjänsten.  | - [Microsoft Managed Desktop-tjänstbeskrivning](service-description/index.md)<br><br>- [Gör dig redo för registrering på Microsoft Managed Desktop](get-ready/index.md)  |
|Hantering av informationssäkerhet     | Säkerhetsinformation, inklusive informationssäkerhet för tjänsten.<br><br> Säkerhetsrelaterade principer och annan information om hur enheter konfigureras.   | - [Säkerhet på Microsoft Managed Desktop](service-description/security.md)<br><br>- [Enhetskonfiguration](service-description/device-policies.md)  |
|Hantering av tillgänglighet     |  Microsoft Managed Desktop balanserar ansvaret med din organisation för att säkerställa tillgängligheten av tjänsten.<br><br>Administratörer och slutanvändare har vägar till respektive support vid service- eller tillgänglighetsproblem. | - [Microsoft Managed Desktop-åtgärder och övervakning](service-description/operations-and-monitoring.md)<br><br>- [Administratörsstöd för Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)<br>- [Få hjälp för slutanvändare](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>Övergång till tjänsten


|ITIL-processen |Beskrivning  |Dokumentation |
|---------|---------|---------|
|Ändra hantering     | Definierad ansvarsfördelning, processöversikt och typer relaterade till tillgänglig ändringshantering.  | [Microsoft Managed Desktop-åtgärder och övervakning](service-description/operations-and-monitoring.md#change-management) |
|Hantering av utgivning och distribution     |  Microsoft Managed Desktop hanterar uppdateringar för enheter som är registrerade i tjänsten.  | [Så här hanteras uppdateringar på Microsoft Managed Desktop](service-description/updates.md)        |
|Hantering av servicetillgångar och konfiguration     | Information om organisationens Microsoft Managed Desktop-distribution finns på IT-administratörsportalen.  | [Administratörsstöd för Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md) |
|Kunskapshantering     | Informationen om Microsoft Managed Desktop-tjänsten hålls uppdaterad på den här webbplatsen.   | [Ändra historik för dokumentationen för Microsoft Managed Desktop](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>Servicedrift


|ITIL-processen |Beskrivning  |Dokumentation  |
|---------|---------|---------|
|Händelsehantering     |  Information om övervakning av enheter finns.<br><br>Standardrutiner för Microsoft Managed Desktop-tjänsten beskrivs. |  - [Säkerhet på Microsoft Managed Desktop](service-description/security.md)<br>- [Microsoft Managed Desktop-åtgärder och övervakning](service-description/operations-and-monitoring.md)       |
|Hantering av incidenter  | Microsoft Managed Desktop undersöker och agerar på incidenter enligt definierade allvarlighetsgrader.  |  [Allvarlighetsdefinitioner för supportbegäran](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|Begäran uppfyllelse förvaltning     |  Process för begäranden om information och ändringsbegäranden som är relaterade till Microsoft Managed Desktop-tjänsten definieras.         |[Administratörsstöd för Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)         |
|Problemhantering     | Eventuella problem med tjänsten ska riktas till ditt lokala kontoteam just nu. | Dokumentation i utveckling |
|Åtkomsthantering     | Åtkomsthanteringskomponenter och ansvar för kunden för att säkerställa att funktionaliteten är detaljerad.  | [Identitets- och åtkomsthantering](service-description/security.md#identity-and-access-management)        |
