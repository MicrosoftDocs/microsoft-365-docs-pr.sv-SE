---
title: Insikter om Windows-säkerhetsuppdateringar
description: ''
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 772d1d52e977a067ff9bc3517de9cb2ae6c8c9a3
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950373"
---
# <a name="windows-security-update-insights"></a>Insikter om Windows-säkerhetsuppdateringar
Den här vyn innehåller en översikt över status för säkerhets uppdateringar för Microsoft Managed Station ära datorer. 

Om du vill visa användnings data väljer du fliken <strong>Windows säkerhets uppdateringar</strong> .

![Windows säkerhets uppdaterings fönster: stapel-grafer med enhets status och uppdatera version i vänster kolumn, uppdatera distributions förloppet över tid i mitten och procent av aktiva enheter efter distributions grupp, samt antalet dagar för att nå distributions mål för 95% i höger kolumn.](../../media/update-insights.jpg)

## <a name="device-status"></a>Enhets status

För att enheter ska uppdateras av Windows Update måste de vara anslutna till Internet och inte försätts i vilo läge i minst sex timmar, två av dessa måste vara löpande. Så länge en enhet är ansluten och inte är i vilo läge anses den vara "används". Även om det är möjligt att en enhet som inte uppfyller dessa krav kommer att uppdateras, att enheter som uppfyller dem har högsta sannolikhet för att uppdateras. 

Vi kategoriserar enhets aktivitet i Windows Update med följande villkor:

- <strong>Aktivt:</strong> Enheter som har uppnått de lägsta användnings villkoren (sex timmar, två forts) för den senaste säkerhets uppdateringen och har checkats in med Microsoft Intune minst var femte dag
- <strong>Synkroniserat:</strong> Enheter som har checkat in med Intune under de senaste 28 dagarna
- Inte <strong>synkroniserat:</strong> Enheter som <i>inte</i> har checkats in med Intune under de senaste 28 dagarna




## <a name="update-version-status"></a>Uppdatera versions status

Microsoft publicerar säkerhets uppdateringar varannan tisdag i månaden. Varje utgåva innehåller viktiga uppdateringar för kända säkerhets problem. Microsoft Managed Desktop säkerställer att 95% av dess hanterade enheter uppdateras med de senaste tillgängliga säkerhets uppdateringarna varje månad. Säkerhets uppdateringar släpps ibland vid andra tillfällen för att snarast adressera nya hot. Microsoft Managed Desktop distribuerar dessa uppdateringar på liknande sätt.

Vi kategoriserar statusen för säkerhets uppdaterings versioner med dessa villkor:

- <strong>Nuvarande:</strong> Enheter som kör uppdateringen släpptes under den aktuella månaden
- <strong>Föregående:</strong> Enheter som kör uppdateringen som släpptes under den föregående månaden
- <strong>Äldre:</strong> Enheter med säkerhets uppdateringar som släpps före den föregående månaden

Du bör se få enheter i den <strong>äldre</strong> kategorin – en stor eller växande population indikerar antagligen ett systemfel som du bör rapportera till Microsoft Managed Desktop så att vi kan undersöka det.


## <a name="deployment-progress"></a>Distributions förlopp

I början av varje version för säkerhets uppdatering tar Microsoft Managed Desktop en ögonblicks bild av enhets populationen och anger dess drift sättnings mål till 95% av populationen. I området <strong>distributions förlopp</strong> visas en historisk trend, uppdaterad varje dag, och här följer en genom gång av hur nära uppdaterings distributionen uppfyller detta mål för varje utgåva. I det här diagrammet visas endast enheter med aktiv status.

Du kan visa dessa data för föregående uppdaterings cykler genom att använda den nedrullningsbara menyn i det övre högra hörnet. Den period som du väljer i den här menyn gäller för all information på hela sidan.

I området för <strong>uppdaterade aktiva enheter efter distributions grupp</strong> kan du se hur uppdateringen fortskrider för var och en av de olika distributions grupperna för Microsoft Managed Station.

I <strong>mål</strong> området visas hur lång tid det tog för 95% av totalt antal enheter att uppdateras med den aktuella säkerhets uppdateringen. När distributionen pågår visas det <strong>fortfarande</strong> i det här området tills 95%-målet nås för den valda uppdateringen.

## <a name="device-details-area"></a>Området enhets information

Instrument panelens nederkant är en tabell med detaljerad information för dina enheter, inklusive [enhets status](#device-status) och status för [uppdaterings version](#update-version-status). Du kan söka i den här listan eller filtrera den med något av de angivna värdena.


![Enhets informations tabell med kolumner för enhets namn, tilldelad användare, enhets status, uppdatering version, operativ system version och datum då enheten senast synkroniserades.](../../media/security-update-insights-device-table-sterile.png)
