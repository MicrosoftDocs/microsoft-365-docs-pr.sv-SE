---
title: Utvärdera Microsoft Hotskydd
description: Ställ in din miljö för utvärderings labb för Microsoft Threat Protection för att testa hur den koordinerade hotets skydds lösningen som är avsedd att skydda enheter, identitet, data och program kan hjälpa din organisation
keywords: Utvärderings version av Microsoft Threat Protection, prova Microsoft Threat Protection, utvärdera Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab, cyberterrorism Security, Avancerat hot, företags säkerhet, enheter, enhet, identitet, användare, data, program, tillbud, automatiserad undersökning och reparation, avancerad jakt
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: a9d7b514aac8d1a769c0dabf6dcdb54f4bcb447b
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2020
ms.locfileid: "47649967"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a>Skapa en test laboratorie miljö för Microsoft Threat Protection 

**Gäller för:**
- Microsoft Hotskydd

Syftet med att skapa den här test laboratorie miljön är att illustrera de omfattande, integrerade och smarta funktionerna i Microsoft Threat Protection i identifiering, förebyggande åtgärder och svar som du kan använda i din organisation. 

Den här guiden leder dig genom stegen för att starta utvärderings versionen av Microsoft Threat med de rekommenderade distributions vägarna. Målet är att hjälpa dig att konfigurera de integrerade tjänsterna för Microsoft Threat Protection i en labb miljö eller som ett POC (proof of Concept) när du presenterar besluts fattarna hos säkerhets lösningen i din organisation. När du är klar med dina attacker, automatiserade undersökningar och svar och är nöjd med resultatet kan du distribuera det i produktions miljön med hjälp av Microsofts tekniska Sälj experter eller experter i din organisation. 

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
| ![Fas 1: förbereda](../../media/prepare.png)<br>[Fas 1: förbereda](prepare-mtpeval.md)| Lär dig vad du behöver tänka på när du distribuerar Microsoft Threat Protection i en test laboratorie miljö: <br><br>-Intressenter och utloggning <br> -Miljö överväganden <br>-Åtkomst <br>-Konfigurera Azure Active Directory <br> -Konfigurations beställning
|  ![Fas 2: konfiguration](../../media/setup.png) <br>[Fas 2: konfiguration](setup-mtpeval.md)|  Vidta de första stegen för att komma åt Microsoft 365 säkerhets Center för att konfigurera utvärderings labb miljön för Microsoft Threat Protection. Du ska vägleda dig till:<br><br>-Registrera dig för Microsoft 365 E5-utvärderings version <br>  -Konfigurera domän<br>-Tilldela Microsoft 365 E5-licenser<br>-Slutför installations guiden i portalen|
|  ![Steg 3: Konfigurera & inbyggt](../../media/config-onboard.png) <br>[Steg 3: Konfigurera & inbyggt](config-mtpeval.md) | Konfigurera varje slut punkter för skydd mot Microsoft Threat-och-inbyggt. Du ska vägleda dig till:<br><br>-Konfigurera Office 365 Avancerat skydd<br>-Konfigurera säkerhet för Microsoft Cloud App<br>-Konfigurera Avancerat skydd för Azure<br>-Konfigurera Microsoft Defender Avancerat skydd 


## <a name="in-scope"></a>I omfattning

Följande är i omfattning för utvärderings versionen av test laboratoriet:
-   Konfigurera Azure Active Directory
-   Konfigurera skydd mot Microsoft Threat
    -   Registrera dig för Microsoft 365 E5-utvärderings versionen
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

-   Konfiguration av lösningar från tredje part som kan integreras med Microsoft Defender ATP
-   Test av inträngda i produktions miljön

## <a name="next-step"></a>Nästa steg
![Fas 1: förbereda](../../media/prepare.png) <br>[Fas 1: förbereda](prepare-mtpeval.md) 
<br> Förbereda en miljö för utvärderings labb för Microsoft Threat Protection
