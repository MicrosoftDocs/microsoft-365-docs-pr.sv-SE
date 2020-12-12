---
title: Utvärdera Microsoft 365 Defender
description: Ställ in utvärderings labb eller pilot miljö för Microsoft 365 Defender för att pröva och upplev säkerhets lösningen för att skydda enheter, identiteter, data och program i organisationen.
keywords: Utvärderings version av Microsoft Threat Protection, prova Microsoft Threat Protection, utvärdera Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab, Microsoft Threat Protection pilot, cyberterrorism Security, Avancerat, beständigt hot, företags säkerhet, enheter, enhet, identitet, användare, data, program, händelser, automatiserad undersökning och reparation, avancerad jakt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 8504b036203e1f73dc9e0a0d79a228425fb88bfa
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659646"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Skapa en test labb-eller pilot miljö för Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender


Med den här guiden får du hjälp att arbeta i en labb miljö med användare och grupper och vägleder dig genom konfigureringen av funktionerna i Microsoft 365 Defender så att du kan efterlikna en hotet-attack och få ett meningsfullt prov. 

Syftet med att skapa test laboratoriet eller pilot miljön är att illustrera de omfattande och integrerade Microsoft 365 Defender-funktionerna. Upplev hur den här intelligenta säkerhets lösningen identifierar, hindrar, automatiskt undersöker och svarar på avancerade hot som din organisation har. 


Du vägleds genom stegen för att starta utvärderings versionen av Microsoft 365 Defender baserat på de rekommenderade distributions vägarna. Målet är att hjälpa dig att konfigurera säkerhets lösningen antingen i en labb miljö med ett utvärderings konto eller i en pilot miljö i en produktion med fullständig licens. Att förbereda utvärderings labbet eller pilot miljön hjälper dig att presentera ärenden för besluts fattare i organisationen. När du är klar med dina antecknings simuleringar och är nöjd med resultatet kan du distribuera och operationalize dem i organisationen med hjälp av Microsofts tekniska Sälj experter eller experter i din organisation. 

Den här guiden hjälper dig:
- Konfigurera labb Server och datorer
- Konfigurera Active Directory med användare och grupper
- Konfigurera och konfigurera Microsoft Defender för identitet, Microsoft Defender för Office 365, Microsoft Defender för slut punkt och säkerhet för Microsoft Cloud App
- Konfigurera lokala principer för servern och datorerna
- Imiterar en hot attack för att skapa en test incident eller-varning i Microsoft 365 Defender

>[!IMPORTANT]
>Bäst resultat får du om du följer installations anvisningarna så nära som möjligt.


## <a name="deployment-phases"></a>Distributions faser

Det finns tre faser i att skapa en test laboratorie miljö för Microsoft 365 Defender.

![Distributions faser: förbereda, konfigurera, inbyggt](../../media/evaluation-guide-phases.png)

|Fas | Beskrivning | 
|:-------|:-----|
|[Fas 1: förbereda](prepare-mtpeval.md)| Läs om vad du behöver tänka på när du distribuerar Microsoft 365 Defender i ett prov labb eller en pilot miljö: <br><br>-Intressenter och utloggning <br> -Miljö överväganden <br>-Åtkomst <br>-Konfigurera Azure Active Directory <br> -Konfigurations beställning
|[Fas 2: konfiguration](setup-mtpeval.md)|  Vidta de första stegen för att komma åt Microsoft 365 säkerhets Center för att konfigurera utvärderings labb för Microsoft 365 Defender eller pilot miljö. Du är guidad att:<br><br>-Registrera dig för Microsoft 365 E5-utvärderings version <br>  -Konfigurera domän<br>-Tilldela Microsoft 365 E5-licenser<br>-Slutför installations guiden i portalen|
|[Steg 3: Konfigurera & inbyggt](config-mtpeval.md) | Konfigurera varje slut punkter för Microsoft 365 Defender pelare och inbyggda. Du är guidad att:<br><br>-Konfigurera Microsoft Defender för Office 365<br>-Konfigurera säkerhet för Microsoft Cloud App<br>-Konfigurera Microsoft Defender för identitet<br>-Konfigurera Microsoft Defender för slut punkt


När du har fyllt i den här guiden hade du identifierat berörda intressenter och godkännanden, som krävs för att få rätt åtkomst behörighet, registrerat dig för utvärderings versionen, konfigurerade domäner och alla Microsoft 365 Defender-träd och dina slut punkter i tjänsten.

## <a name="key-capabilities"></a>Viktiga funktioner

Även om Microsoft 365 Defender tillhandahåller många funktioner är det primära syftet med den här distributions guiden att komma igång med att starta enheter. Förutom att börja använda den här vägledningen får du följande funktioner.


Funktion | Beskrivning 
:---|:---
Microsoft Defender för Office 365 | Skyddar hela din Office 365-envrionment från dagens hot
Microsoft Defender for Identity | Identifierar och identifierar hot om komprometterade identiteter och skadliga Insider-åtgärder.
Microsoft Cloud App Security | Ger omfattande synlighet, styr data resor och upptäck Cyberthreats i moln tjänster.
Microsoft Defender för Endpoint | Skyddar, identifierar och ger svar på avancerade hot med omfattande slut punkts säkerhet.


## <a name="in-scope"></a>I omfattning

Följande aktiviteter är omfång för den här guiden:
-   Konfigurera Azure Active Directory
-   Konfigurera Microsoft 365 Defender
    -   Registrera dig för Microsoft 365 E5-utvärdering eller Använd din fullständiga licens om du kör en pilot
    -   Konfigurera domän
    -   Tilldela Microsoft 365 E5-licenser
    -   Slutföra installations guiden i portalen
-   Konfigurera alla Microsoft 365 Defender-pelare baserat på metod tips
    -   Microsoft Defender för Office 365
    -   Microsoft Defender for Identity
    -   Microsoft Cloud App Security
    -   Microsoft Defender för Endpoint

## <a name="out-of-scope"></a>Utanför omfattning

Den här distributions guiden följer inte med:

-   Konfiguration av lösningar från tredje part som kan integreras med Microsoft 365 Defender
-   Test av inträngda i produktions miljön

## <a name="next-step"></a>Nästa steg
[Fas 1: förbereda](prepare-mtpeval.md) 
<br> Förbereda utvärderings labb eller pilot miljö för Microsoft 365 Defender
