---
title: Kör ditt pilot Microsoft Threat Protection Project
description: Kör ditt pilot Microsoft Threat Protection-projekt i produktionen för att effektivt fastställa fördelarna och antagandet av Microsoft Threat Protection (MTP).
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
ms.openlocfilehash: f49f1afe5461a4f2eff0a3049f1d14d1892f70ce
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477032"
---
# <a name="run-your-pilot-microsoft-threat-protection-project"></a>Kör ditt pilot Microsoft Threat Protection Project 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection

För att effektivt fastställa fördelarna och antagandet av Microsoft Threat Protection (MTP) kan du köra ett pilot projekt. Innan du aktiverar Microsoft Threat Protection i produktions miljön och startar dina användnings fall är det bäst att planera för att bestämma vilka uppgifter som ska utföras för pilot projektet och hur du ställer in framgång. 


## <a name="how-to-use-this-pilot-playbook"></a>Så här använder du pilot Playbook

I den här guiden får du en översikt över Microsoft Threat Protection och stegvisa instruktioner om hur du konfigurerar pilot projektet. 

Skydd mot Microsoft Threat är ett enhetligt för hands versions paket med för-och efter intrång som enhetligt koordinerar skydd, identifiering, förebyggande, undersökning och svar för slut punkter, identiteter, e-postmeddelanden och program för att erbjuda ett integrerat skydd mot sofistikerade attacker. Det gör det genom att kombinera och dirigera följande funktioner till en enda säkerhets lösning:
  - Microsoft Defender för slut punkt, det nya namnet på Microsoft Defender Avancerat skydd (slut punkter)
  - Microsoft Defender för Office 365, det nya namnet på Office 365 ATP (e-post) 
  - Microsoft Defender för identitet, det nya namnet på Azure ATP (identitet) 
  - Säkerhet för Microsoft Cloud App (appar)

![Of_Microsoft hot skydds lösning för användare, Azure Avancerat skydd för slut punkter Microsoft Defender Avancerat skydd, för Cloud-appar, Microsoft Cloud App-säkerhet och för data, Office 365 Avancerat skydd  ](../../media/mtp/m365pillars.png)

Med den integrerade Microsoft Threat Protection-lösningen kan säkerhets experter samla ihop hot signalerna som Microsoft Defender Avancerat skyddar, Office 365 ATP, Azure ATP och Microsoft Cloud App Security och fastställa det fulla omfattningen och effekten av hotet, hur det kommer att påverkas och hur det används för närvarande. Microsoft Threat Protection vidtar automatisk åtgärd för att förhindra eller stoppa angreppet och själv åtgärdade post lådor, slut punkter och användar identiteter. Mer information finns i [Microsoft Threat Protection-översikten](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) .

![Faser i en Microsoft Threat Protection pilot](../../media/pilotphases.png)

Följande exempel tids linje varierar beroende på om du har rätt resurser i din miljö. Vissa identifieringar och arbets flöden kan behöva mer inlärnings tid än de andra.

![Exempel på tids linje i att köra ett Microsoft Threat Protection pilot](../../media/pilotimeline.png)

>[!IMPORTANT]
>För optimalt resultat följer du pilot instruktionerna så nära som möjligt.


### <a name="pilot-playbook-phases"></a>Pilot Playbook faser 

Det finns fyra faser för att köra ett Microsoft Threat Protection pilot:

|Fas | Beskrivning | 
|:-------|:-----|
| ![Planering](../../media/mtp/plan.png)<br>[Planering](mtp-pilot-plan.md)| Läs mer om vad du behöver tänka på innan du kör ett Microsoft Threat Protection Pilot-projekt: <br><br>-Omfattning <br> -Användnings fall <br>-Krav <br>-Test plan <br> -Villkor <br> -Styrkort 
| ![Förberedelse](../../media/mtp/prep.png) <br>[Förberedelse](mtp-evaluation.md)|  Få åtkomst till Microsoft 365 säkerhets Center för att konfigurera pilot miljön för Microsoft Threat Protection. Du är guidad att:<br><br>-Identifiera intressenter och inhämta en uppsägning för din pilot <br> -Miljö överväganden <br>-Åtkomst <br>-Konfigurera Azure Active Directory <br> -Konfigurations beställning <br> -Registrera dig för Microsoft 365 E5-utvärderings version <br> -Konfigurera domän <br>-Tilldela Microsoft 365 E5-licenser <br> -Slutför installations guiden i portalen|
| ![Simulering av attacker](../../media/mtp/run-sim.png) <br>[Simulering av attacker](mtp-pilot-simulate.md) | För att simulera en attack ska du vägleda dig till:<br><br>-Kontrol lera test miljö kraven <br>-Kör simuleringen <br>-Undersök en olycka <br>-Lös problemet 
| ![Stänga och sammanfatta](../../media/mtp/close.png) <br>[Stänga och sammanfatta](mtp-pilot-close.md) | När du har nått slutet av processen är du guidad att:<br><br>-Gå igenom dina slutliga utdata<br>-Presentera dina synpunkter för dina intressenter <br>-Ge feedback <br>-Ta nästa steg 

## <a name="next-step"></a>Nästa steg
|![Planerings fas](../../media/mtp/plan.png) <br>[Planerings fas](mtp-pilot-plan.md) | Planera ditt Microsoft Threat Protection Pilot projekt 
|:-------|:-----|
