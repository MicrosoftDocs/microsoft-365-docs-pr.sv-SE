---
title: Microsoft Hanterat skrivbord och ITIL
description: Korrelerar ITIL-faser Microsoft Hanterat skrivbord information och artiklar
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation, ITISM
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: f51c99ed39e9f647f3e069c22eb3e37441f57be5
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924485"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft Hanterat skrivbord och ITIL

Många organisationer tycker att det är värdefullt att strukturera sina IT-tjänster i linje med en formaliserad IT-tjänstmodell (ITSM), till exempel [ITIL.](https://www.axelos.com/best-practice-solutions/itil) 

Microsoft Hanterat skrivbord organisationen att efterleva många viktiga aspekter av sådana formaliserade ITSM-modeller. Med ITIL som exempel kan du i den här artikeln se kopplingarna mellan vanliga ITIL-faser och -processer och motsvarande Microsoft Hanterat skrivbord, om tillämpligt. Den här informationen gäller Microsoft Hanterat skrivbord delen av organisationen.

Mer omfattande information om ITIL och dess faser och processer finns i dokumentationen [till itilen.](https://www.axelos.com/best-practice-solutions/itil)


## <a name="service-design"></a>Tjänstedesign

Den här tabellen relaterar viktiga ITIL-faser och -processer till Microsoft Hanterat skrivbord, med länkar till vår dokumentation för mer information:



|ITIL-process |Beskrivning  |Dokumentation |
|---------|---------|---------|
|Tjänstnivåhantering     | Svarstider definieras för administrationssupportbegäranden och -incidenter.  |  [Admin-support för Microsoft Hanterat skrivbord](working-with-managed-desktop/admin-support.md)  |
|Tjänstkatalogshantering     | Tjänstbeskrivning med information om komponenter i tjänsten hålls sanna status för tjänsten, tillgänglig för alla aktuella och intresserade kunder.<br><br>Förutsättningar som är detaljerade för att förstå vad som krävs för att tjänsten ska fungera.  | - [Microsoft Hanterat skrivbord tjänstbeskrivning](service-description/index.md)<br><br>- [Gör dig redo för registrering i Microsoft Hanterat skrivbord](get-ready/index.md)  |
|Informationssäkerhetshantering     | Säkerhetsinformation, inklusive informationssäkerhet för tjänsten.<br><br> Säkerhetsrelaterade principer och annan information om hur enheter konfigureras.   | - [Säkerhet i Microsoft Hanterat skrivbord](service-description/security.md)<br><br>- [Enhetskonfiguration](service-description/device-policies.md)  |
|Tillgänglighetshantering     |  Microsoft Hanterat skrivbord med din organisation för att säkerställa tillgängligheten för tjänsten.<br><br>Administratörer och användare har routes till respektive support om det finns problem med tjänsten eller tillgänglighet. | - [Microsoft Hanterat skrivbord åtgärder och övervakning](service-description/operations-and-monitoring.md)<br><br>- [Administratörssupport för Microsoft Hanterat skrivbord](working-with-managed-desktop/admin-support.md)<br>- [Få hjälp för användare](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>Tjänstövergång


|ITIL-process |Beskrivning  |Dokumentation |
|---------|---------|---------|
|Ändringshantering     | Definierad ansvarsfördelning, processöversikt och typer relaterade till ändringshantering.  | [Microsoft Hanterat skrivbord åtgärder och övervakning](service-description/operations-and-monitoring.md#change-management) |
|Hantering av lansering och distribution     |  Microsoft Hanterat skrivbord hanterar uppdateringar för enheter som är registrerade i tjänsten.  | [Hur uppdateringar hanteras i Microsoft Hanterat skrivbord](service-description/updates.md)        |
|Hantering av tjänstestillgångar och konfiguration     | Information om organisationens distribution Microsoft Hanterat skrivbord i IT-administrationsportalen.  | [Admin-support för Microsoft Hanterat skrivbord](working-with-managed-desktop/admin-support.md) |
|Kunskapshantering     | Information om Microsoft Hanterat skrivbord-tjänsten hålls uppdaterad på den här webbplatsen.   | [Ändringshistorik för dokumentationen om Microsoft Hanterat skrivbord](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>Tjänståtgärd


|ITIL-process |Beskrivning  |Dokumentation  |
|---------|---------|---------|
|Händelsehantering     |  Information om övervakning av enheter finns.<br><br>Standardoperativsystemets procedurer för Microsoft Hanterat skrivbord tjänst är detaljerade. |  - [Säkerhet i Microsoft Hanterat skrivbord](service-description/security.md)<br>- [Microsoft Hanterat skrivbord åtgärder och övervakning](service-description/operations-and-monitoring.md)       |
|Incidenthantering  | Microsoft Hanterat skrivbord undersöker och agerar incidenter i definitionerna för allvarlighetsgrad.  |  [Definitioner av allvarlighetsgrad för supportbegäran](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|Hantering av begäran om uppfyllelse     |  Processen för begäranden om information och ändringsförfrågningar som är Microsoft Hanterat skrivbord tjänsten har definierats.         |[Admin-support för Microsoft Hanterat skrivbord](working-with-managed-desktop/admin-support.md)         |
|Problemhantering     | Eventuella problem med tjänsten bör dirigeras till ditt lokala kontoteam. | Dokumentation under utveckling |
|Åtkomsthantering     | Åtkomsthanteringskomponenter och kundansvar för att säkerställa att funktionaliteten är detaljerad.  | [Identitets- och åtkomsthantering](service-description/security.md#identity-and-access-management)        |
