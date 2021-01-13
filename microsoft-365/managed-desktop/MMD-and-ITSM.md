---
title: Microsoft Hanterat skrivbord och ITIL
description: Korrelerar ITIL-faser med Microsoft hanterad Skriv bords information och artiklar
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation, ITISM
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: e545b64670bb92c40465f1c50b2cb46b9fd7a8d8
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841441"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft Hanterat skrivbord och ITIL

Många organisationer tycker att det är värdefullt att strukturera sina IT-tjänster utmed linjerna i en formaliserad IT-ITSM, till exempel [ITIL](https://www.axelos.com/best-practice-solutions/itil). 

Microsoft Managed Desktop gör att organisationen kan uppfylla många viktiga aspekter av sådana formaliserade ITSM-modeller. Genom att använda ITIL som ett exempel hjälper den här artikeln dig att se anslutningar mellan vanliga ITIL-faser och processer samt motsvarande Microsoft hanterade Skriv bords funktioner, där så är tillämpligt. Den här informationen gäller endast Microsoft Managed Desktop-delen av din organisation.

Mer omfattande information om ITIL och dess faser och processer finns i [dokumentationen](https://www.axelos.com/best-practice-solutions/itil).


## <a name="service-design"></a>Tjänst design

I den här tabellen hör viktiga ITIL-faser och processer till Microsoft Managed Desktop-funktioner, med länkar till vår dokumentation för mer information:



|ITIL-process |Beskrivning  |Dokumentation |
|---------|---------|---------|
|Tjänst nivå hantering     | Svars tider är definierade för förfrågningar och händelser för administratörs support.  |  [Admin-support för Microsoft Hanterat skrivbord](working-with-managed-desktop/admin-support.md)  |
|Tjänst katalog hantering     | Tjänste beskrivningens detalj komponenter i tjänsten behålls enligt tjänstens status som tillgängliga för alla aktuella och intresserade kunder.<br><br>Förutsättningar för att förstå vad som behövs för att driva tjänsten.  | - [Beskrivning av tjänsten Microsoft Managed Desktop](service-description/index.md)<br><br>- [Förbered dig för registrering på Microsoft Managed Desktop](get-ready/index.md)  |
|Informations säkerhets hantering     | Säkerhets information, inklusive information om tjänsten.<br><br> Säkerhetsrelaterade principer och annan information om hur enheter har kon figurer ATS.   | - [Säkerhet på Microsoft Managed Desktop](service-description/security.md)<br><br>- [Enhets konfiguration](service-description/device-policies.md)  |
|Tillgänglighets hantering     |  Microsoft Managed Desktop-saldon med din organisation för att säkerställa tillgänglighet för tjänsten.<br><br>Administratörer och användare har vägar till respektive support om det finns tjänst-eller tillgänglighets problem. | - [Microsoft Managed Station ära datorer och övervakning](service-description/operations-and-monitoring.md)<br><br>- [Administratörs support för Microsoft Managed Desktop](working-with-managed-desktop/admin-support.md)<br>- [Få hjälp för användare](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>Service över gång


|ITIL-process |Beskrivning  |Dokumentation |
|---------|---------|---------|
|Ändrings hantering     | Definierad betalnings ansvar, process översikt och typer relaterade till ändrings hantering.  | [Microsoft Managed Station ära datorer och övervakning](service-description/operations-and-monitoring.md#change-management) |
|Hantering och distribution     |  Microsoft Managed Desktop hanterar uppdateringar för enheter som är registrerade i tjänsten.  | [Hur uppdateringar hanteras på Microsoft Managed Desktop](service-description/updates.md)        |
|Tjänst till gång och konfigurations hantering     | Information om organisationens distribution av Microsoft Managed Desktop är tillgänglig på portalen för IT-administratörer.  | [Admin-support för Microsoft Hanterat skrivbord](working-with-managed-desktop/admin-support.md) |
|Kunskaps hantering     | Information om Microsoft Managed Desktop-tjänsten hålls uppdaterad på den här webbplatsen.   | [Ändringshistorik för dokumentationen om Microsoft Hanterat skrivbord](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>Tjänst åtgärd


|ITIL-process |Beskrivning  |Dokumentation  |
|---------|---------|---------|
|Händelse hantering     |  Information om övervakning av enheter tillhandahålls.<br><br>De vanliga rutinerna för Microsoft Managed Desktop-tjänsten är detaljerade. |  - [Säkerhet på Microsoft Managed Desktop](service-description/security.md)<br>- [Microsoft Managed Station ära datorer och övervakning](service-description/operations-and-monitoring.md)       |
|Ärende hantering  | Microsoft Managed Desktop undersöker och åtgärdar händelser i enlighet med definierade allvarlighets definitioner.  |  [Support ärende definitioner för allvarlighets grad](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|Hantering av begäran     |  Processen för begäran om information och ändrings förfrågningar relaterade till Microsoft Managed Desktop-tjänsten har definierats.         |[Admin-support för Microsoft Hanterat skrivbord](working-with-managed-desktop/admin-support.md)         |
|Problem hantering     | Eventuella problem med tjänsten ska riktas till ditt lokala konto team. | Dokumentation i utveckling |
|Åtkomst hantering     | Åtkomst hanterings komponenter och ansvars områden för kunden för att säkerställa att funktionerna är detaljerade.  | [Identitets- och åtkomsthantering](service-description/security.md#identity-and-access-management)        |
