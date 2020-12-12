---
title: Kör ditt pilot Microsoft 365 Defender Project
description: Kör piloten Microsoft 365 Defender Project in the Production för att effektivt fastställa fördelarna och antagandet av Microsoft 365 Defender.
keywords: Microsoft Threat Protection pilot, kör pilot Microsoft Threat Protection Project, utvärdera Microsoft Threat Protection i Production, Microsoft Threat Protection Pilot-projekt, cyberterrorism-säkerhet, Avancerat hot, företags säkerhet, enheter, enhet, identitet, användare, data, program, tillbud, automatiserad undersökning och reparation, avancerad jakt
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
- m365solution-pilotmtpproject
ms.topic: conceptual
ms.openlocfilehash: f01e918d35ce77d9239c200355c7b4c48c9e2b84
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659327"
---
# <a name="run-your-pilot-microsoft-365-defender-project"></a>Kör ditt pilot Microsoft 365 Defender Project 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender


Med den här guiden får du hjälp att köra ett pilot projekt genom att ange att du har ett välstrukturerat abonnemang och du kan använda funktionen för att hantera anslags verktyget och slutligen ingå piloten med de viktiga anvisningarna.

![Faser i en Microsoft 365 Defender pilot](../../media/pilotphases.png)


Genom att använda en pilot kan du effektivt bestämma fördelarna med adoptiing Microsoft 365 Defender. Innan du aktiverar Microsoft 365 Defender i produktions miljön och startar dina användnings fall är det bäst att planera för att bestämma vilka uppgifter som ska utföras för pilot projektet och hur du ställer in framgång. 


## <a name="how-to-use-this-pilot-playbook"></a>Så här använder du pilot Playbook

I den här guiden får du en översikt över Microsoft 365 Defender och stegvisa instruktioner för hur du konfigurerar pilot projektet. 

Microsoft 365 Defender är ett enhetligt för hands versions paket med för-och efter intrång som enhetligt koordinerar skydd, identifiering, förebyggande, undersökning och svar för slut punkter, identiteter, e-postmeddelanden och program för att ge ett integrerat skydd mot sofistikerade attacker. Det gör det genom att kombinera och dirigera följande funktioner till en enda säkerhets lösning:
  - Microsoft Defender för slut punkt, det nya namnet på Microsoft Defender Avancerat skydd (slut punkter)
  - Microsoft Defender för Office 365, det nya namnet på Office 365 ATP (e-post) 
  - Microsoft Defender för identitet, det nya namnet på Azure ATP (identitet) 
  - Säkerhet för Microsoft Cloud App (appar)

![Bild of_Microsoft 365 Defender-lösning för användare, Microsoft Defender för identitet för slut punkter Microsoft Defender för slut punkter, moln program, Microsoft Cloud App-säkerhet och för data, Microsoft Defender för Office 365](../../media/mtp/m365pillars.png)

Med den integrerade Microsoft 365 Defender-lösningen kan säkerhets experter koppla ihop hotet om att Microsoft Defender för slut punkt, Microsoft Defender för Office 365, Microsoft Defender för identitet och Microsoft Cloud App Security tar emot och fastställer det fulla scopet och effekten av hotet, hur det kommer att påverkas och hur det påverkar organisationen. Microsoft 365 Defender vidtar automatisk åtgärd för att förhindra eller stoppa angreppet och själv läka berörda post lådor, slut punkter och användar identiteter. Mer information finns i [Microsoft 365 Defender-översikten](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) .



Följande exempel tids linje varierar beroende på om du har rätt resurser i din miljö. Vissa identifieringar och arbets flöden kan behöva mer inlärnings tid än de andra.

![Exempel på tids linje i en Microsoft 365 Defender pilot](../../media/phase-diagrams/pilot-phases.png)

>[!IMPORTANT]
>För optimalt resultat följer du pilot instruktionerna så nära som möjligt.


### <a name="pilot-playbook-phases"></a>Pilot Playbook faser 

Det finns fyra faser i en Microsoft 365 Defender pilot:

|Fas | Beskrivning | 
|:-------|:-----|
| [Planering](mtp-pilot-plan.md)<br> ~ 1 dag| Läs mer om vad du behöver tänka på innan du kör Microsoft 365 Defender pilot-projektet: <br><br>-Omfattning <br> -Användnings fall <br>-Krav <br>-Test plan <br> -Villkor <br> -Styrkort 
| [Förberedelse](mtp-evaluation.md) <br>~ 2 dagar|  Få åtkomst till Microsoft 365 säkerhets Center för att konfigurera pilot miljön för Microsoft 365 Defender. Du är guidad att:<br><br>-Identifiera intressenter och inhämta en uppsägning för din pilot <br> -Miljö överväganden <br>-Åtkomst <br>-Konfigurera Azure Active Directory <br> -Konfigurations beställning <br> -Registrera dig för Microsoft 365 E5-utvärderings version <br> -Konfigurera domän <br>-Tilldela Microsoft 365 E5-licenser <br> -Slutför installations guiden i portalen|
| [Simulering av attacker](mtp-pilot-simulate.md) <br>~ 2 dagar| För att simulera en attack ska du vägleda dig till:<br><br>-Kontrol lera test miljö kraven <br>-Kör simuleringen <br>-Undersök en olycka <br>-Lös problemet 
| [Stänga och sammanfatta](mtp-pilot-close.md) <br>~ 1 dag| När du har nått slutet av processen är du guidad att:<br><br>-Gå igenom dina slutliga utdata<br>-Presentera dina synpunkter för dina intressenter <br>-Ge feedback <br>-Ta nästa steg 

## <a name="next-step"></a>Nästa steg
|[Planerings fas](mtp-pilot-plan.md) | Planera ditt Microsoft 365 Defender Pilot projekt 
|:-------|:-----|
