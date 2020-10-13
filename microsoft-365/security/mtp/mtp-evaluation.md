---
title: Utvärdera Microsoft Hotskydd
description: Ställ in ett utvärderings labb för Microsoft Threat-skydd eller pilot miljö för att pröva och upplev säkerhets lösningen för att skydda enheter, identiteter, data och program i din organisation.
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
ms.openlocfilehash: d3f63c8ac4ba82a80c365dce564bbd8d3dd4da4b
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447125"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-or-pilot-environment"></a>Skapa ett test labb eller pilot miljö för Microsoft Threat Protection 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection

Syftet med att skapa den här test laboratoriet eller pilot miljön är att illustrera de omfattande och integrerade hot Protection funktionerna i Microsoft. Upplev hur den här intelligenta säkerhets lösningen identifierar, hindrar, automatiskt undersöker och svarar på avancerade hot som din organisation har. 

Den här guiden leder dig genom stegen för att starta utvärderings versionen av Microsoft Threat med de rekommenderade distributions vägarna. Målet är att hjälpa dig att konfigurera säkerhets lösningen antingen i en labb miljö med ett utvärderings konto eller i en pilot miljö i en produktion med fullständig licens. Att förbereda utvärderings labbet eller pilot miljön hjälper dig att presentera ärenden för besluts fattare i organisationen. När du är klar med dina antecknings simuleringar och är nöjd med resultatet kan du distribuera och operationalize dem i organisationen med hjälp av Microsofts tekniska Sälj experter eller experter i din organisation. 

Den här guiden hjälper dig:
- Konfigurera labb Server och datorer
- Konfigurera Active Directory med användare och grupper
- Konfigurera och konfigurera Azure ATP, Office ATP, Microsoft Defender ATP och Microsoft Cloud App Security
- Konfigurera lokala principer för servern och datorerna
- Imiterar en hot attack för att skapa en test incident eller-varning i Microsoft Threat Protection

>[!IMPORTANT]
>Bäst resultat får du om du följer installations anvisningarna så nära som möjligt.


## <a name="deployment-phases"></a>Distributions faser

Det finns tre faser i att skapa en test laboratorie miljö för Microsoft Threat Protection och distribuera det:

|Fas | Beskrivning | 
|:-------|:-----|
| ![Fas 1: förbereda](../../media/prepare.png)<br>[Fas 1: förbereda](prepare-mtpeval.md)| Lär dig vad du behöver tänka på när du distribuerar Microsoft Threat Protection i en utvärderings labb-eller pilot miljö: <br><br>-Intressenter och utloggning <br> -Miljö överväganden <br>-Åtkomst <br>-Konfigurera Azure Active Directory <br> -Konfigurations beställning
|  ![Fas 2: konfiguration](../../media/setup.png) <br>[Fas 2: konfiguration](setup-mtpeval.md)|  Vidta de första stegen för att komma åt Microsoft 365 säkerhets Center för att konfigurera ett test labb för Microsoft Threat Protection eller pilot miljö. Du är guidad att:<br><br>-Registrera dig för Microsoft 365 E5-utvärderings version <br>  -Konfigurera domän<br>-Tilldela Microsoft 365 E5-licenser<br>-Slutför installations guiden i portalen|
|  ![Steg 3: Konfigurera & inbyggt](../../media/config-onboard.png) <br>[Steg 3: Konfigurera & inbyggt](config-mtpeval.md) | Konfigurera varje slut punkter för skydd mot Microsoft Threat-och-inbyggt. Du är guidad att:<br><br>-Konfigurera Office 365 Avancerat skydd<br>-Konfigurera säkerhet för Microsoft Cloud App<br>-Konfigurera Avancerat skydd för Azure<br>-Konfigurera Microsoft Defender Avancerat skydd 


## <a name="in-scope"></a>I omfattning

Följande aktiviteter är omfång för den här guiden:
-   Konfigurera Azure Active Directory
-   Konfigurera skydd mot Microsoft Threat
    -   Registrera dig för Microsoft 365 E5-utvärdering eller Använd din fullständiga licens om du kör en pilot
    -   Konfigurera domän
    -   Tilldela Microsoft 365 E5-licenser
    -   Slutföra installations guiden i portalen
-   Konfigurera alla Microsoft Threat Protection-pelare baserat på bästa praxis
    -   Office 365 Avancerat skydd
    -   Azure Advanced Threat Protection
    -   Microsoft Cloud App Security
    -   Microsoft Defender Avancerat skydd

## <a name="out-of-scope"></a>Utanför omfattning

Den här distributions guiden följer inte med:

-   Konfiguration av lösningar från tredje part som kan integreras med Microsoft Threat Protection
-   Test av inträngda i produktions miljön

## <a name="next-step"></a>Nästa steg
![Fas 1: förbereda](../../media/prepare.png) <br>[Fas 1: förbereda](prepare-mtpeval.md) 
<br> Förbereda ett utvärderings labb för Microsoft Threat Protection eller pilot miljö
