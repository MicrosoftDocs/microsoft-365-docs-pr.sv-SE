---
title: Köra ditt Microsoft 365 Defender projekt
description: Kör ditt pilotprojekt Microsoft 365 Defender produktion för att effektivt avgöra vilka fördelar och införande av Microsoft 365 Defender.
keywords: Microsoft 365 Defender pilottest, kör Microsoft 365 Defender-pilotprojekt, utvärdera Microsoft 365 Defender i produktion, Microsoft 365 Defender-pilotprojekt, cybersäkerhet, avancerade beständiga hot, företagssäkerhet, enheter, enheter, identitet, användare, data, program, incidenter, automatiserad undersökning och åtgärd, avancerad sökning
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
ms.openlocfilehash: fd84ef93d679be6e1e42f823dcac1f2d5181f1e9
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289961"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Köra ditt Microsoft 365 Defender projekt 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender


Den här guiden hjälper dig att köra ett pilotprojekt genom att lägga till pekare för att säkerställa att du har en välstrukturerad plan så att du kan vägleda dig genom att använda attack simuleringsfunktionen och slutligen göra en avslutande beräkning av piloten med viktiga take-aways så att du kan reflektera över och dokumentera resultaten.

![Faser i körningen av Microsoft 365 Defender pilot](../../media/pilotphases.png)


Genom att köra ett pilottest kan du effektivt avgöra fördelarna med att Microsoft 365 Defender. Innan du Microsoft 365 Defender i produktionsmiljön och startar användningsfallen är det bäst att planera för att fastställa vilka uppgifter som ska utföras för pilotprojektet och ange framgångskriterier. 


## <a name="how-to-use-this-pilot-playbook"></a>Så här använder du den här pilotspelboken

I den här guiden får du Microsoft 365 Defender en översikt över hur du olika pilotprojekt kan konfigureras. 

Microsoft 365 Defender är en enhetlig företagsskyddssvit efter intrång som inbyggt koordinerar skydd, identifiering, skydd, undersökning och svar mellan slutpunkter, identiteter, e-post och program för att ge integrerat skydd mot avancerade attacker. Det gör det genom att kombinera och lösa följande funktioner till en enda säkerhetslösning:

- Microsoft Defender för Slutpunkt (slutpunkter)
- Microsoft Defender för Office 365 (e-post)
- Microsoft Defender för identitet (identitet)
- Microsoft Cloud App Security (appar)

![Bild of_Microsoft 365 Defender-lösning för användare, Microsoft Defender för identitet, för slutpunkter Microsoft Defender för slutpunkt, för molnappar, Microsoft Cloud App Security och för data, Microsoft Defender för Office 365](../../media/mtp/m365pillars.png)

Med den integrerade Microsoft 365 Defender-lösningen kan säkerhetsexperter samarbeta med hoten, som visar att Microsoft Defender för Endpoint, Microsoft Defender för Office 365, Microsoft Defender för identitet och Microsoft Cloud App Security tar emot och fastställer hotens fullständiga omfattning och påverkan, hur det kommit in i miljön, vad det påverkas av och hur det för närvarande påverkar organisationen. Microsoft 365 Defender åtgärder vidtas automatiskt för att förhindra eller stoppa attacken och postlådor, slutpunkter och användaridentiteter som påverkas själv. Se Microsoft 365 Defender [översikt](microsoft-365-defender.md) för mer information.

Följande exempel på tidslinjen varierar beroende på rätt resurser i din miljö. Vissa identifieringar och arbetsflöden kan behöva mer utbildningstid än de andra.

![Exempel på tidslinje i en Microsoft 365 Defender pilot](../../media/phase-diagrams/pilot-phases.png)

> [!IMPORTANT]
> För bästa resultat bör du följa pilotinstruktionerna så nära som möjligt.

### <a name="pilot-playbook-phases"></a>Pilotspelboksfaser

Det finns fyra faser i ett Microsoft 365 Defender pilottest:

|Fas | Beskrivning |
|:-------|:-----|
| [Planering](m365d-pilot-plan.md)<br> ~ 1 dag| Läs om vad du behöver tänka på innan du kör Microsoft 365 Defender pilotprojekt: <br><br>- Omfattning <br> - Användningsfall <br>- Krav <br>- Testplan <br> - Kriterier för framgång <br> - Styrkort 
| [Förberedelse](m365d-evaluation.md) <br>~2 dagar|  Access Microsoft 365 Säkerhetscenter för att konfigurera din Microsoft 365 Defender pilotmiljö. Du vägleds till:<br><br>– Identifiera intressenter och be om att få ett pilottecken <br> - Att tänka på när det gäller miljön <br>- Access <br>- Azure Active Directory konfiguration <br> - Konfigurationsordning <br> - Registrera dig för Microsoft 365 E5 utvärderingsversion <br> - Konfigurera domän <br>- Tilldela Microsoft 365 E5 licenser <br> - Slutför installationsguiden i portalen|
| [Attack simulering](m365d-pilot-simulate.md) <br>~2 dagar| Om du vill simulera en attack får du vägledning genom att:<br><br>- Kontrollera testmiljökraven <br>- Kör simuleringen <br>- Undersöka en händelse <br>- lösa problemet 
| [Avslutande och sammanfattande](m365d-pilot-close.md) <br>~ 1 dag| När du har kommit till slutet av processen vägleds du till:<br><br>- Gå igenom dina slutliga utdata<br>- Presentera dina utdata för dina intressenter <br>- Ge feedback <br>- Gör nästa steg 

## <a name="next-step"></a>Nästa steg

|[Planeringsfas](m365d-pilot-plan.md) | Planera ditt Microsoft 365 Defender pilotprojekt 
|:-------|:-----|
