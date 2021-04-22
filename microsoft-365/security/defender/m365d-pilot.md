---
title: Kör ditt pilotprojekt i Microsoft 365 Defender
description: Kör ditt pilotprojekt i Microsoft 365 Defender i produktionen för att effektivt avgöra vilka fördelar och införande av Microsoft 365 Defender är.
keywords: Microsoft 365 Defender-pilot, pilottesta Microsoft 365 Defender-projektet, utvärdera Microsoft 365 Defender i produktion, Microsoft 365 Defender-pilotprojekt, cybersäkerhet, avancerade beständiga hot, företagssäkerhet, enheter, enheter, identitet, användare, data, program, incidenter, automatisk undersökning och åtgärd, avancerad sökning
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
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b1616b39597a90ff8e8f7b4c92f29f75c62fea18
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934435"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Kör ditt pilotprojekt i Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender


Den här guiden hjälper dig att köra ett pilotprojekt genom att lägga till pekare för att säkerställa att du har en välstrukturerad plan så att du kan vägleda dig genom att använda attack simuleringsfunktionen och slutligen göra en avslutande beräkning av piloten med viktiga take-aways så att du kan reflektera över och dokumentera resultaten.

![Faser i körning av en Microsoft 365 Defender-pilot](../../media/pilotphases.png)


Genom att köra ett pilottest kan du effektivt avgöra fördelarna med att använda Microsoft 365 Defender. Innan du aktiverar Microsoft 365 Defender i produktionsmiljön och startar dina användningsfall är det bäst att planera för att fastställa vilka uppgifter som ska utföras för ditt pilotprojekt och ange framgångskriterier. 


## <a name="how-to-use-this-pilot-playbook"></a>Så här använder du den här pilotspelboken

Den här guiden innehåller en översikt över Microsoft 365 Defender och stegvisa instruktioner om hur du ställer in ditt pilotprojekt. 

Microsoft 365 Defender är en enhetlig företagsskyddssvit före och efter intrång som inbyggt koordinerar skydd, identifiering, skydd, undersökning och svar mellan slutpunkter, identiteter, e-post och program för att tillhandahålla integrerat skydd mot avancerade attacker. Det gör det genom att kombinera och lösa följande funktioner till en enda säkerhetslösning:
  - Microsoft Defender för Slutpunkt (slutpunkter)
  - Microsoft Defender för Office 365 (e-post) 
  - Microsoft Defender för identitet (identitet) 
  - Microsoft Cloud App Security (appar)

![Bild of_Microsoft 365 Defender-lösning för användare, Microsoft Defender för identitet, för slutpunkter Microsoft Defender för Slutpunkt, för molnappar, Microsoft Cloud App Security och för data, Microsoft Defender för Office 365](../../media/mtp/m365pillars.png)

Med den integrerade Microsoft 365 Defender-lösningen kan säkerhetsexperter hantera hoten som Microsoft Defender för Endpoint, Microsoft Defender för Office 365, Microsoft Defender för identitet och Microsoft Cloud App-säkerhet tar emot och fastställa hotens fullständiga omfattning och påverkan, hur det kommit in i miljön, vad det påverkas och hur det för närvarande påverkar organisationen. Microsoft 365 Defender vidtar automatisk åtgärd för att förhindra eller stoppa attacken och självutmanade postlådor, slutpunkter och användaridentiteter. Mer information [finns i Översikt över Microsoft 365 Defender.](microsoft-365-defender.md)



Följande exempel på tidslinjen varierar beroende på rätt resurser i din miljö. Vissa identifieringar och arbetsflöden kan behöva mer utbildningstid än de andra.

![Exempel på tidslinje i en Microsoft 365 Defender-pilot](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>För bästa resultat bör du följa pilotinstruktionerna så nära som möjligt.


### <a name="pilot-playbook-phases"></a>Pilotspelboksfaser 

Det finns fyra faser i ett Microsoft 365 Defender-pilottest:

|Fas | Beskrivning | 
|:-------|:-----|
| [Planering](m365d-pilot-plan.md)<br> ~ 1 dag| Läs om vad du behöver tänka på innan du kör pilotprojektet i Microsoft 365 Defender: <br><br>- Omfattning <br> - Användningsfall <br>- Krav <br>- Testplan <br> - Kriterier för framgång <br> - Styrkort 
| [Förberedelse](m365d-evaluation.md) <br>~2 dagar|  Access Microsoft 365 Säkerhetscenter för att konfigurera din Microsoft 365 Defender-pilotmiljö. Du vägleds till:<br><br>– Identifiera intressenter och be om att få ett pilottecken <br> - Att tänka på när det gäller miljön <br>- Access <br>- Azure Active Directory-konfiguration <br> - Konfigurationsordning <br> - Registrera dig för utvärderingsversionen av Microsoft 365 E5 <br> - Konfigurera domän <br>- Tilldela Microsoft 365 E5-licenser <br> - Slutför installationsguiden i portalen|
| [Attack simulering](m365d-pilot-simulate.md) <br>~2 dagar| Om du vill simulera en attack får du vägledning genom att:<br><br>- Kontrollera testmiljökraven <br>- Kör simuleringen <br>- Undersöka en händelse <br>- lösa problemet 
| [Avslutande och sammanfattande](m365d-pilot-close.md) <br>~ 1 dag| När du har kommit till slutet av processen vägleds du till:<br><br>- Gå igenom dina slutliga utdata<br>- Presentera dina utdata för dina intressenter <br>- Ge feedback <br>- Gör nästa steg 

## <a name="next-step"></a>Nästa steg
|[Planeringsfas](m365d-pilot-plan.md) | Planera ditt pilotprojekt i Microsoft 365 Defender 
|:-------|:-----|
