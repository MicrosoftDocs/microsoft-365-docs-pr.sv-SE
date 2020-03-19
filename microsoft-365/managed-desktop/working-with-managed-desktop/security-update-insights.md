---
title: Insikter om Windows-säkerhetsuppdateringar
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: ef2d5c897709e7f7d2484d032b7471031be77d74
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/29/2020
ms.locfileid: "42809457"
---
# <a name="windows-security-update-insights"></a>Insikter om Windows-säkerhetsuppdateringar
Den här vyn innehåller en översikt över statusen för säkerhetsuppdateringar för dina Microsoft Managed Desktop-enheter. 

Om du vill visa användningsdata väljer du fliken Säkerhetsuppdateringar i <strong>Windows.</strong>

![Fönstret Windows säkerhetsuppdateringar: stapeldiagram över enhetsstatus och uppdateringsversion i vänster kolumn, uppdatera distributionsförloppet över tid i mittkolumnen och procentandel av aktiva enheter efter distributionsgrupp, samt antalet dagar som har gjorts för att nå 95%-distributionen mål i höger kolumn.](../../media/update-insights.jpg)

## <a name="device-status"></a>Enhetsstatus

För att enheter ska kunna uppdateras av Windows Update måste de vara anslutna till Internet och inte vara i viloläge i minst sex timmar, varav två måste vara kontinuerliga. Så länge en enhet är ansluten och inte övervintrar, anses den vara "i bruk". Även om det är möjligt att en enhet som inte uppfyller dessa krav kommer att uppdateras, har enheter som uppfyller dem den största sannolikheten för att uppdateras. 

Vi kategoriserar enhetsaktivitet i samband med Windows Update med följande villkor:

- <strong>Aktiv:</strong> Enheter som har uppfyllt minimianvändningskriterierna (sex timmar, två kontinuerliga) för den senaste säkerhetsuppdateringsversionen och har checkat in med Microsoft Intune minst var femte dag
- <strong>Synkroniserad:</strong> Enheter som har checkat in med Intune under de senaste 28 dagarna
- <strong>Osynkroniserad:</strong> Enheter som <i>inte</i> har checkat in med Intune under de senaste 28 dagarna




## <a name="update-version-status"></a>Status för uppdateringsversionen

Microsoft släpper säkerhetsuppdateringar varannan tisdag i månaden. Varje utgåva lägger till viktiga uppdateringar för kända säkerhetsproblem. Microsoft Managed Desktop säkerställer att 95 % av dess hanterade enheter uppdateras med den senaste tillgängliga säkerhetsuppdateringen varje månad. Säkerhetsuppdateringar släpps ibland vid andra tillfällen för att snabbt ta itu med nya hot. Microsoft Managed Desktop distribuerar dessa uppdateringar på ett liknande sätt.

Vi kategoriserar status för säkerhetsuppdateringsversioner med följande villkor:

- <strong>Aktuell:</strong> Enheter som kör uppdateringen som släpps under den aktuella månaden
- <strong>Föregående:</strong> Enheter som kör uppdateringen som släpptes föregående månad
- <strong>Äldre:</strong> Enheter som kör någon säkerhetsuppdatering som släpptes före föregående månad

Du bör se få enheter i kategorin <strong>Äldre</strong> – en stor eller växande population indikerar förmodligen ett systemproblem som du bör rapportera till Microsoft Managed Desktop så att vi kan undersöka.


## <a name="deployment-progress"></a>Förloppet för distribution

I början av varje startcykel för säkerhetsuppdateringar tar Microsoft Managed Desktop en ögonblicksbild av enhetspopulationen och anger sitt distributionsmål till 95 % av den populationen. <strong>Området Förlopp för distribution</strong> visar en historisk trend, uppdaterad dagligen, som spårar hur nära uppdateringsdistributionen uppfyller det här målet för varje version. Det här diagrammet visar bara enheter med aktiv status.

Du kan visa dessa data för tidigare uppdateringscykler med hjälp av rullgardinsmenyn längst upp till höger. Den period du väljer i den här menyn gäller för all information på hela sidan.

Det <strong>uppdaterade aktiva enheterna efter distributionsgruppsområdet</strong> ger en annan vy genom att visa förloppet för uppdateringsinstallationen för var och en av distributionsgrupperna för Microsoft Managed Desktop.

Området <strong>Dagar för att nå mål</strong> visar hur lång tid det tog för 95 % av det totala antalet enheter som ska uppdateras med den aktuella säkerhetsuppdateringen. När distributionen pågår visas <strong>stilluppdatering</strong> fortfarande tills 95% målet har uppnåtts för den valda uppdateringen.

## <a name="device-details-area"></a>Området för enhetsinformation

Längst ned på instrumentpanelen finns en tabell som visar detaljerad information för dina enheter, inklusive [enhetsstatus](#device-status) och status för [uppdateringsversionen](#update-version-status). Du kan söka i den här listan eller filtrera den efter valfritt värde i listan.


![Enhetsinformationstabell som visar kolumner för enhetsnamn, tilldelad användare, enhetsstatus, uppdateringsversion, operativsystemversion och det datum då enheten senast synkroniserades.](../../media/security-update-insights-device-table-sterile.png)
