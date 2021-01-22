---
title: Kör ditt pilotprojekt i Microsoft 365 Defender
description: Kör ditt pilotprojekt i Microsoft 365 Defender i produktionen för att effektivt avgöra vilka fördelar och införande av Microsoft 365 Defender är.
keywords: Microsoft Threat Protection-pilot, kör pilottestning av Microsoft Threat Protection-projektet, utvärdera Microsoft Threat Protection i produktionen, Microsoft Threat Protection-pilotprojekt, cybersäkerhet, avancerade beständiga hot, företagssäkerhet, enheter, enheter, identitet, användare, data, program, incidenter, automatiserad undersökning och åtgärd, avancerad sökning
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 9c0635058539e464a76f1720f041c205a05fa9b2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933036"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Kör ditt pilotprojekt i Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender


Den här guiden hjälper dig att köra ett pilotprojekt genom att lägga till pekare för att säkerställa att du har en välstrukturerad plan som hjälper dig genom att använda attackattackfunktionen, och slutligen drar in piloten med viktiga take-aways så att du kan reflektera över och dokumentera resultaten.

![Faser i körning av en Microsoft 365 Defender-pilot](../../media/pilotphases.png)


Genom att köra en pilot kan du effektivt avgöra fördelarna med att använda Microsoft 365 Defender. Innan du aktiverar Microsoft 365 Defender i produktionsmiljön och startar dina användningsfall är det bäst att planera för att avgöra vilka uppgifter som ska utföras för pilotprojektet och ange kriterier för framgång. 


## <a name="how-to-use-this-pilot-playbook"></a>Hur du använder den här pilotspelboken

I den här guiden får du en översikt över Microsoft 365 Defender och stegvisa instruktioner om hur du ställer in ditt pilotprojekt. 

Microsoft 365 Defender är en enhetlig företagsskyddssvit efter intrång som inbyggt koordinerar skydd, identifiering, skydd, undersökning och svar mellan slutpunkter, identiteter, e-post och program för att ge integrerat skydd mot avancerade attacker. Det gör det genom att kombinera och avde olika funktioner till en enda säkerhetslösning:
  - Microsoft Defender för Endpoint, det nya namnet för Microsoft Defender Advanced Threat Protection (slutpunkter)
  - Microsoft Defender för Office 365, det nya namnet för Office 365 ATP (e-post) 
  - Microsoft Defender för identitet, det nya namnet för Azure ATP (identitet) 
  - Microsoft Cloud App Security (appar)

![Bild of_Microsoft 365 Defender-lösning för användare, Microsoft Defender för identitet, för slutpunkter Microsoft Defender för Slutpunkt, för molnappar, Microsoft Cloud App Security och för data, Microsoft Defender för Office 365](../../media/mtp/m365pillars.png)

Med den integrerade Microsoft 365 Defender-lösningen kan säkerhetsexperter hantera hoten som Microsoft Defender för Endpoint, Microsoft Defender för Office 365, Microsoft Defender för identitet och Microsoft Cloud App-säkerhet tar emot och fastställa hotens fullständiga omfattning och påverkan, hur det tog sig in i miljön, vad det påverkades och hur det för närvarande påverkar organisationen. Microsoft 365 Defender vidtar automatisk åtgärd för att förhindra eller stoppa attacken och självdådande postlådor, slutpunkter och användaridentiteter. Mer information [finns i översikten för Microsoft 365 Defender.](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)



Följande exempel på tidslinje varierar beroende på om rätt resurser finns i din miljö. Vissa identifieringar och arbetsflöden kan behöva mer utbildningstid än de andra.

![Exempel på tidslinjen i körningen av en Microsoft 365 Defender-pilot](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>För bästa resultat följer du pilotinstruktionerna så nära som möjligt.


### <a name="pilot-playbook-phases"></a>Pilotspelboksfaser 

Det finns fyra faser i körningen av en Microsoft 365 Defender-pilot:

|Fas | Beskrivning | 
|:-------|:-----|
| [Planering](mtp-pilot-plan.md)<br> ~ 1 dag| Läs om vad du behöver tänka på innan du kör pilotprojektet i Microsoft 365 Defender: <br><br>- Omfattning <br> - Användningsfall <br>- Krav <br>- Testplan <br> - Kriterier för framgång <br> - Styrkort 
| [Förberedelse](mtp-evaluation.md) <br>~2 dagar|  I Access Microsoft 365 Säkerhetscenter kan du konfigurera pilotmiljön Microsoft 365 Defender. Du vägleds till:<br><br>– Identifiera intressenter och sök efter att bli signerad för piloten <br> - Att tänka på när det gäller miljön <br>- Access <br>- Azure Active Directory-konfiguration <br> - Konfigurationsordning <br> - Registrera dig för utvärderingsversionen av Microsoft 365 E5 <br> - Konfigurera domän <br>- Tilldela Microsoft 365 E5-licenser <br> - Slutför installationsguiden i portalen|
| [Attacksimulering](mtp-pilot-simulate.md) <br>~2 dagar| Om du vill simulera en attack vägleds du till:<br><br>- Kontrollera testmiljökraven <br>- Köra simuleringen <br>- Undersöka en händelse <br>- lösa incidenten 
| [Avslutnings- och sammanfattningskurs](mtp-pilot-close.md) <br>~ 1 dag| När du har kommit till slutet av processen vägleds du till:<br><br>- Gå igenom dina slutliga utdata<br>- Presentera resultaten för dina intressenter <br>- Ge feedback <br>- Gör nästa steg 

## <a name="next-step"></a>Nästa steg
|[Planeringsfas](mtp-pilot-plan.md) | Planera ditt pilotprojekt i Microsoft 365 Defender 
|:-------|:-----|
