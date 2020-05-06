---
title: Utvärdera Microsofts hotskydd
description: Konfigurera testlabbetamiljön för Microsoft Threat Protection för att prova hur den samordnade hotskyddslösningen som utformats för att skydda enheter, identitet, data och program kan hjälpa din organisation
keywords: Microsoft Threat Protection rättegång, prova Microsoft Threat Protection, utvärdera Microsoft Threat Protection, Microsoft Threat Protection utvärdering lab, cybersäkerhet, avancerade ihållande hot, företagssäkerhet, enheter, enhet, identitet, användare, data, applikationer, incidenter, automatiserad undersökning och reparation, avancerad jakt
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
ms.openlocfilehash: f6ee8147965a29b87d84690535116f096e4c6006
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049645"
---
# <a name="create-a-microsoft-threat-protection-trial-lab-environment"></a>Skapa en testlabbmiljö för Microsoft Threat Protection 

**Gäller:**
- Microsoft Hotskydd

Syftet med att skapa den här testlabbetsmiljön är att illustrera de omfattande, integrerade och intelligenta funktionerna i Microsoft Threat Protection i identifiering, förebyggande, undersökning och svar som du kan använda i din organisation. 

Den här guiden tar dig igenom stegen för att starta microsoft threat protection-utvärderingen baserat på de rekommenderade distributionsvägarna. Målet är att hjälpa dig att konfigurera integrerade Microsoft Threat Protection-tjänster i en labbmiljö eller som ett proof of concept (POC) när du presenterar för beslutsfattare för säkerhetslösningar i din organisation. När du är klar med att köra dina attacksimuleringar, automatisk undersökning och svar och är nöjda med resultaten kan du distribuera den i din produktionsmiljö med hjälp av Microsoft Technical Sales Professionals eller experter i din organisation. 

Den här guiden hjälper dig:
- Konfigurera labbservern och datorerna
- Konfigurera Active Directory med användare och grupper
- Konfigurera Azure ATP, Office ATP, Microsoft Defender ATP och Microsoft Cloud App Security
- Konfigurera lokala principer för servern och datorerna
- Härma en hotattack för att generera en testincident eller en varning i Microsoft Threat Protection

>[!IMPORTANT]
>För bästa resultat, följ instruktionerna för labbinställningar så nära som möjligt.


## <a name="deployment-phases"></a>Distributionsfaser

Det finns tre faser i att skapa en testlabbmiljö för Microsoft Threat Protection och distribuera den:

|Fas | Beskrivning | 
|:-------|:-----|
| ![Fas 1: Förbered](../../media/prepare.png)<br>[Fas 1: Förbered](prepare-mtpeval.md)| Läs om vad du behöver tänka på när du distribuerar Microsoft Threat Protection i en testlabbetamiljö: <br><br>- Intressenter och signering <br> - Miljöhänsyn <br>- Tillgång <br>- Azure Active Directory-konfiguration <br> - Konfigurationsordning
|  ![Fas 2: Installation](../../media/setup.png) <br>[Fas 2: Installation](setup-mtpeval.md)|  Gör de första stegen för att komma åt Microsoft 365 Security Center för att konfigurera testlabbeta Microsoft Threat Protection. Du kommer att guidas till:<br><br>- Registrera dig för Testversionen av Microsoft 365 E5 <br>  - Konfigurera domän<br>- Tilldela Microsoft 365 E5 licenser<br>- Slutför installationsguiden i portalen|
|  ![Fas 3: Konfigurera & ombord](../../media/config-onboard.png) <br>[Fas 3: Konfigurera & ombord](config-mtpeval.md) | Konfigurera varje Microsoft Threat Protection-pelare och inbyggda slutpunkter. Du kommer att guidas till:<br><br>- Konfigurera avancerat hotskydd för Office 365<br>- Konfigurera Säkerhet för Microsoft Cloud-appar<br>- Konfigurera Azure Advanced Threat Protection<br>- Konfigurera Microsoft Defender avancerat hotskydd 


## <a name="in-scope"></a>I omfattning

Följande är i omfattning för den här testlabbets miljöguide:
-   Konfigurera Azure Active Directory
-   Konfigurera Microsofts hotskydd
    -   Registrera dig för Testversionen av Microsoft 365 E5
    -   Konfigurera domän
    -   Tilldela Microsoft 365 E5-licenser
    -   Slutföra installationsguiden i portalen
-   Konfigurera alla Microsoft Threat Protection-pelare baserat på metodtips
    -   Office 365 Avancerat skydd
    -   Azure Advanced Threat Protection
    -   Microsoft Cloud App Security
    -   Microsoft Defender Avancerat skydd

## <a name="out-of-scope"></a>Utanför räckvidden

Följande är utanför omfattningen av den här distributionsguiden:

-   Konfiguration av tredjepartslösningar som kan integreras med Microsoft Defender ATP
-   Penetrationstestning i produktionsmiljö

## <a name="next-step"></a>Nästa steg
|||
|:-------|:-----|
|![Fas 1: Förbered](../../media/prepare.png) <br>[Fas 1: Förbered](prepare-mtpeval.md) | Förbereda microsofts labbmiljö för utvärdering av hotskydd
