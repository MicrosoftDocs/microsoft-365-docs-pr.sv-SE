---
title: Microsoft 365 Defender
description: Microsoft 365 Defender är en koordinerad skydds lösning som är utformad för att skydda enheter, identiteter, data och program
keywords: Introduktion till skydd mot Microsoft Threat, cyberterrorism säkerhet, Avancerat beständigt hot, företags säkerhet, enheter, enhet, identitet, användare, data, program, händelser, automatiserad undersökning och reparation, avancerad jakt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 1884f0dae87bf068d134430ada78e44d713fd4d9
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780526"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera det i en labb miljö](https://aka.ms/mtp-trial-lab) eller [köra ett pilot projekt i produktionen](https://aka.ms/m365d-pilotplaybook).
>

Microsoft 365 Defender är ett enhetligt för hands versions paket för företag som interagerar med identifiering, förebyggande, undersökning och svar för slut punkter, identiteter, e-postmeddelanden och program för att ge integrerat skydd mot sofistikerade attacker.

Med den integrerade Microsoft 365 Defender-lösningen kan säkerhetsexperterna häfta ihop hotet så att dessa produkter får och fastställer den fulla omfattningen och påverkan av hotet; hur den har kommit till miljön, vad den påverkar och hur den för närvarande påverkar organisationen. Microsoft 365 Defender vidtar automatisk åtgärd för att förhindra eller stoppa angreppet och själv läka berörda post lådor, slut punkter och användar identiteter.  


<center><h2>Microsoft 365 Defender-tjänster</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender för slut punkt</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender för Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Microsoft Defender för identitet</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Säkerhet för Microsoft Cloud App</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Microsoft 365 Defender interaktiv guide

I den här interaktiva guiden får du lära dig hur du skyddar din organisation med Microsoft 365 Defender. Du kommer att se hur Microsoft 365 Defender kan hjälpa dig att upptäcka säkerhets risker, undersöka angrepp till din organisation och förhindra skadliga aktiviteter automatiskt.

> [!VIDEO https://aka.ms/M365Defender-InteractiveGuide]



Microsoft 365 Defender Suite skyddar: 
- **Slut punkter med Microsoft Defender för slut** punkt – Microsoft Defender för slut punkt är en plattform för att skydda dig, efter överträdelse, automatisk undersökning och svar. 
- **E-post och samarbete med Microsoft Defender för office 365** – Defender för Office 365 skyddar din organisation mot hot via e-postmeddelanden, länkar (URL: er) och samarbets verktyg. 
- **Identiteter med Microsoft Defender för identitets-och Azure AD-identitets skydd** – Microsoft Defender för identitet använder Active Directory-signaler för att identifiera, upptäcka och undersöka avancerade hot, kompromissade identiteter och illasinnade Insider-åtgärder på din organisation. 
- **Program med Microsoft Cloud App-säkerhet** – Microsoft Cloud App Security är en omfattande SaaS lösning som ger en djup insyn, starka data kontroller och förbättrat skydd för dina molnappar. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Microsoft 365 Defender unika Cross-Product-lager förstärker de enskilda Suite-komponenterna till:
- Skydda mot attacker och koordinera försvars frågor i serien via signal delning och automatiska åtgärder
- En berättarröst är den fullständiga artikeln i angreppet över produkt aviseringar, funktioner och kontext för säkerhets grupper genom att koppla data om aviseringar, misstänkta händelser och stötande till gångar till "incidenter"
- Automatisera svar från kompromiss genom att utlösa själv återställning för använda till gångar genom automatisk reparation
- Gör det möjligt för säkerhets teamerna att genomföra detaljerad och effektiv hotet mot slut punkter och Office-data

![Bild av översikts sidan för incidenter](../../media/overview-incident.png) <br>
Kors produkts incident (översikt)

![Bild av kön med aviseringar](../../media/incident-list.png)<br>
Alla relaterade aviseringar mellan de olika serie produkterna i en enda olycka (vyn aviseringar)

![Bild av incident kön](../../media/advanced-hunting.png)<br>
Query-baserad jakt ovanpå e-post och slut punkts rå data


Microsoft 365 Defender kors produkt funktioner: 
- **Kors produkt ett fönster i glas** Central Visa all information om identifieringar, påverkade till gångar, automatiserade åtgärder som är vidtagna och närliggande bevis i en enda kö och en enda fönster ruta i [Security.Microsoft.com](https://security.microsoft.com). 
- Sammanslagna **händelse köer** – för att hjälpa säkerhetsutövarna att fokusera på vad som är kritiskt genom att säkerställa hela attackens omfattning, förvissaade till gångar och automatiska reparations åtgärder grupperas tillsammans och på ett säkert sätt. 
- **Automatiskt svar** -kritiskt Hot-information delas i real tid mellan Microsoft 365 Defender-produkterna för att förhindra en attack. Om till exempel en skadlig fil identifieras på en slut punkt som skyddas av Microsoft Defender för slut punkt instruerar den Defender för Office 365 att söka och ta bort filen från alla e-postmeddelanden. Filen blockeras på sikt från hela Microsoft 365-säkerhetssviten.
- **Själv återställning för angripna enheter, användar identiteter och post lådor** – Microsoft 365 Defender använder AI-drivna automatiska åtgärder och playbooks för att återställa berörda till gångar till ett säkert tillstånd. Microsoft 365 Defender utnyttjar automatisk reparations kapacitet för Suite-produkterna för att säkerställa att alla berörda till gångar som är relaterade till en olycka löses automatiskt om möjligt.
- Stöldskydd med **olika produkter** -säkerhets team kan utnyttja sin unika organisatoriska kunskap för att hitta inloggnings problem genom att skapa egna anpassade frågor via rå data som samlas in av de olika skydds produkterna. Med Microsoft 365 Defender får Query-baserad åtkomst till 30 dagars historik RAW-signaler och aviserings data över slut punkter och Microsoft Defender för Office 365-data. 


## <a name="get-started"></a>Komma igång
Licensierings kraven för Microsoft 365 Defender måste uppfyllas innan du kan aktivera tjänsten i Microsoft 365 säkerhets Center på [Security.Microsoft.com](https://security.microsoft.com). Mer information finns i:
- [Licens krav](prerequisites.md#licensing-requirements)
- [Aktivera Microsoft 365 Defender](mtp-enable.md)
