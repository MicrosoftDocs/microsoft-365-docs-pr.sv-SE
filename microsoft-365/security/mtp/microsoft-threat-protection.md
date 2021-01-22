---
title: Microsoft 365 Defender
description: Microsoft 365 Defender är en koordinerad lösning för skydd mot hot som utformats för att skydda enheter, identiteter, data och program
keywords: introduktion till Microsoft Threat Protection, cybersäkerhet, avancerade beständiga hot, företagssäkerhet, enheter, enhet, identitet, användare, data, program, incidenter, automatiserad undersökning och åtgärd, avancerad sökning
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: e80a3d094ac8f5724bbe7daf72a0ded7d30091ba
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930576"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera det i en labbmiljö](https://aka.ms/mtp-trial-lab) eller köra [pilotprojektet i produktion.](https://aka.ms/m365d-pilotplaybook)
>

Microsoft 365 Defender är en enhetlig företagsskyddssvit som inbyggt koordinerar identifiering, förebyggande, undersökning och svar mellan slutpunkter, identiteter, e-post och program för att ge integrerat skydd mot avancerade attacker.

Med den integrerade Microsoft 365 Defender-lösningen kan säkerhetspersonal samlas ihop de hotsignaler som var och en av dessa produkter får och fastställa hotens fullständiga omfattning och påverkan. hur den angavs i miljön, vad den påverkades och hur den för närvarande påverkar organisationen. Microsoft 365 Defender vidtar automatisk åtgärd för att förhindra eller stoppa attacken och självdådande postlådor, slutpunkter och användaridentiteter.  


<center><h2>Microsoft 365 Defender-tjänster</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender för Slutpunkt</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Microsoft Defender för Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Microsoft Defender för identitet</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Microsoft Cloud App-säkerhet</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Interaktiv guide för Microsoft 365 Defender

I den här interaktiva guiden får du lära dig hur du skyddar din organisation med Microsoft 365 Defender. Du ser hur Microsoft 365 Defender kan hjälpa dig att identifiera säkerhetsrisker, undersöka attacker mot organisationen och förhindra skadliga aktiviteter automatiskt.

> [!VIDEO https://aka.ms/M365Defender-InteractiveGuide]



Microsoft 365 Defender-paketet skyddar: 
- **Slutpunkter med Microsoft Defender** för Slutpunkt – Microsoft Defender för Slutpunkt är en enhetlig slutpunktsplattform för förebyggande skydd, identifiering efter intrång, automatiserad undersökning och svar. 
- E-post och samarbete med Microsoft Defender för **Office 365** – Defender för Office 365 skyddar organisationen mot skadliga hot mot e-postmeddelanden, länkar (URL:er) och samarbetsverktyg. 
- **Identiteter med Microsoft Defender för** identitet och Azure AD Identity Protection – Microsoft Defender för identitet använder Active Directory-signaler för att identifiera, identifiera och undersöka avancerade hot, komprometterade identiteter och skadliga Insider-åtgärder riktade till organisationen. 
- **Program med Microsoft Cloud App-säkerhet** – Microsoft Cloud App-säkerhet är en omfattande SaaS-lösning som ger djup synlighet, starka datakontroller och bättre skydd mot hot i dina molnappar. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

I Det unika produktlagret i Microsoft 365 Defender utökas enskilda programsvitens komponenter så att de:
- Skydda mot attacker och koordinera de trådlösa svaren i programsviten genom signaldelning och automatiserade åtgärder
- Berätta en fullständig berättelse om attackerna med produktvarningar, beteenden och sammanhang för säkerhetsteam genom att ansluta data i aviseringar, misstänkta händelser och påverkade tillgångar till "incidenter"
- Automatisera svar på kompromettering genom att utlösa självbetjäning för påverkade tillgångar genom automatiserad åtgärd
- Gör det möjligt för säkerhetsteam att utföra detaljerade och effektiva hot i hela slutpunkten och Office-data

![Bild på översiktssidan för incidenter](../../media/overview-incident.png) <br>
Incident mellan produkter (Översikt)

![Bild på aviseringskö](../../media/incident-list.png)<br>
Alla relaterade varningar för de produktsviter som är korrelerade till ett enskilt incident (vyn Aviseringar)

![Bild på incidentkö](../../media/advanced-hunting.png)<br>
Frågebaserad sökning ovanpå e-post- och slutpunkts rådata


Exempel på funktioner för flera produkter i Microsoft 365 Defender: 
- **En fönsterruta med** flera produkter – Central vy med all information för identifieringar, påverkade tillgångar, automatiserade åtgärder och relaterade bevis i en enda kö och en enda ruta [i security.microsoft.com.](https://security.microsoft.com) 
- **Kombinerad incidentkö** – För att hjälpa säkerhetsexperter att fokusera på vad som är viktigt genom att säkerställa hela attackomfånget grupperas påverkade tillgångar och automatiserade åtgärdsåtgärder tillsammans och visas i tid. 
- **Automatisk respons på hot** – Viktig information om hot delas i realtid mellan Microsoft 365 Defender-produkterna för att stoppa attackförloppet. Om till exempel en skadlig fil identifieras på en slutpunkt som skyddas av Microsoft Defender för Endpoint instrueras Defender för Office 365 att söka igenom och ta bort filen från alla e-postmeddelanden. Filen blockeras av hela Microsoft 365 säkerhetssviten.
- **Självbetjäning** för komprometterade enheter, användaridentiteter och postlådor – Microsoft 365 Defender använder AI-baserade automatiska åtgärder och spelböcker för att åtgärda påverkade tillgångar tillbaka till ett säkert tillstånd. Microsoft 365 Defender använder automatiska åtgärdsfunktioner i paketprodukterna för att se till att alla påverkade tillgångar relaterade till ett incidenter åtgärdas automatiskt om det är möjligt.
- **Produkter** med flera hot på vis – säkerhetsteam kan utnyttja sin unika organisationskunskap för att leta efter kompromisstecken genom att skapa egna anpassade frågor över rådata som samlas in av olika skyddsprodukter. Microsoft 365 Defender ger frågebaserad åtkomst till 30 dagars historiska rådata och aviseringsdata över slutpunkt och Microsoft Defender för Office 365-data. 


## <a name="get-started"></a>Komma igång
Licenskraven för Microsoft 365 Defender måste uppfyllas innan du kan aktivera tjänsten i Säkerhetscenter för Microsoft 365 [på security.microsoft.com.](https://security.microsoft.com) Mer information finns i:
- [Licenskrav](prerequisites.md#licensing-requirements)
- [Aktivera Microsoft 365 Defender](mtp-enable.md)
