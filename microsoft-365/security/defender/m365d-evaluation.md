---
title: Microsoft 365 Defender
description: Konfigurera testlabb eller pilotmiljö i Microsoft 365 Defender för att prova och upplev säkerhetslösningen som utformats för att skydda enheter, identitet, data och program i organisationen.
keywords: Microsoft 365 Utvärderingsversion av Defender, prova Microsoft 365 Defender, utvärdera Microsoft 365 Defender, Microsoft 365 Defender utvärderingslabb, Microsoft 365 Defender pilot, cybersäkerhet, avancerade beständiga hot, företagssäkerhet, enheter, enheter, identitet, användare, data, program, incidenter, automatisk undersökning och åtgärd, avancerad sökning
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c260588b80d8325567b74148a7a62586cfbc707
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933175"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Skapa en Microsoft 365 Defender-testlabb eller pilotmiljö 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender


Den här guiden hjälper dig att arbeta i en labbmiljö med användare och grupper och hjälper dig sedan genom konfigurationen av funktionerna i Microsoft 365 Defender så att du kan efterlikna en hotattack och få ett meningsfullt utvärderingsresultat. 

Syftet med att skapa den här testlabb- eller pilotmiljön är att illustrera de omfattande och integrerade Microsoft 365 Defender-funktionerna. Upplev hur den här intelligenta säkerhetslösningen identifierar, förhindrar, automatiskt undersöker och svarar på avancerade hot som din organisation använder. 


Du vägleds genom stegen för att starta din utvärdering Microsoft 365 Defender baserat på de rekommenderade distributionssökvägarna. Målet är att hjälpa dig att konfigurera säkerhetslösningen i en labmiljö med ett testkonto eller i en pilotmiljö i produktion med en fullständig licens. Förberedelse av utvärderingslabb eller pilotmiljö kan hjälpa dig att presentera säkerhetsåtgärdsanvändningsfall för beslutsfattare i organisationen. När du har kört attack simuleringar och är nöjd med resultatet kan du helt distribuera och driftsätta det i organisationen med hjälp av Microsofts tekniska försäljare eller experter i organisationen. 

I den här guiden får du hjälp med att:
- Konfigurera din labserver och dina datorer
- Konfigurera Active Directory med användare och grupper
- Konfigurera och konfigurera Microsoft Defender för identitet, Microsoft Defender för Office 365, Microsoft Defender för slutpunkt och Microsoft Cloud App Security
- Konfigurera lokala principer för server och datorer
- Imitera en hotattack för att generera en testhändelse eller avisering i Microsoft 365 Defender

>[!IMPORTANT]
>För bästa resultat följer du labinstallationsanvisningarna så nära som möjligt.


## <a name="deployment-phases"></a>Distributionsfaser

Det finns tre faser i att skapa en Microsoft 365 Defender testlabbmiljö.

![Distributionsfaser: förbereda, konfigurera, registrera](../../media/evaluation-guide-phases.png)

|Fas | Beskrivning | 
|:-------|:-----|
|[Fas 1: Förbereda](prepare-m365d-eval.md)| Lär dig vad du behöver tänka på när du distribuerar Microsoft 365 Defender i ett testlabb eller pilotmiljö: <br><br>- Intressenter och av inloggning <br> - Att tänka på när det gäller miljön <br>- Access <br>- Azure Active Directory konfiguration <br> - Konfigurationsordning
|[Fas 2: Installation](setup-m365deval.md)|  Ta de första stegen för att komma Microsoft 365 Säkerhetscenter för att konfigurera testlabb eller pilotmiljö Microsoft 365 Defender. Du vägleds till:<br><br>- Registrera dig för Microsoft 365 E5 utvärderingsversion <br>  - Konfigurera domän<br>- Tilldela Microsoft 365 E5 licenser<br>- Slutför installationsguiden i portalen|
|[Fas 3: Konfigurera & onboard](config-m365d-eval.md) | Konfigurera varje Microsoft 365 Defender-klient och slutpunkter för onboard. Du vägleds till:<br><br>- Konfigurera Microsoft Defender för Office 365<br>- Konfigurera Microsoft Cloud App Security<br>- Konfigurera Microsoft Defender för identitet<br>- Konfigurera Microsoft Defender för Slutpunkt


När du har slutfört den här guiden skulle du ha identifierat de berörda intressenterna och de godkännanden som krävs, ha rätt åtkomstbehörighet, registrerat dig för utvärderingsversion, konfigurerade domäner och var och en av Microsoft 365 Defender-pelarna, och slutpunkterna kommer att introduceras till tjänsten.

## <a name="key-capabilities"></a>Viktiga funktioner

Även Microsoft 365 Defender har många funktioner är det primära syftet med den här distributionsguiden att komma igång med att registrera enheter. Förutom introduktionen får du i den här vägledningen även hjälp att komma igång med följande funktioner.


Funktion | Beskrivning 
:---|:---
Microsoft Defender för Office 365 | Hjälper till att Office 365 hela ditt liv mot dagens hot
Microsoft Defender for Identity | Identifierar och identifierar hot på komprometterade identiteter och skadliga Insider-åtgärder.
Microsoft Cloud App Security | Ger full insyn, styr dataresa och känner av cyberhot i molntjänster.
Microsoft Defender för Endpoint | Förhindrar, identifierar och tillhandahåller svarsfunktioner för avancerade hot med omfattande slutpunktssäkerhet.


## <a name="in-scope"></a>I omfattning

Följande uppgifter omfattas av den här guiden:
-   Konfigurera Azure Active Directory
-   Konfigurera Microsoft 365 Defender
    -   Registrera dig för Microsoft 365 E5 eller använd din fullständiga licens om du kör ett pilottest
    -   Konfigurera domän
    -   Tilldela Microsoft 365 E5 licenser
    -   Slutföra installationsguiden i portalen
-   Konfigurera alla Microsoft 365 Defender-pelarna baserat på metodtips
    -   Microsoft Defender för Office 365
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App Security
    -   Microsoft Defender för Endpoint

## <a name="out-of-scope"></a>Inte begränsad

Följande ingår inte i den här distributionsguiden:

-   Konfiguration av tredjepartslösningar som kan integreras med Microsoft 365 Defender
-   Test av test vid test i produktionsmiljö

## <a name="next-step"></a>Nästa steg
[Fas 1: Förbereda](prepare-m365d-eval.md) 
<br> Förbereda din Microsoft 365 Defender-testlabb eller pilotmiljö
