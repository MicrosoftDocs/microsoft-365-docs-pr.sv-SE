---
title: Microsoft 365 Defender
description: Microsoft 365 Defender är en koordinerad lösning för skydd mot hot som utformats för att skydda enheter, identiteter, data och program
keywords: introduktion till MMicrosoft 365 Defender, cybersäkerhet, avancerade hot, företagssäkerhet, enheter, enheter, identitet, användare, data, program, incidenter, automatisk undersökning och åtgärd, avancerad sökning
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 21a80abd36fd8e7e33f0ccf9b145d409119205ec
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842656"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft 365 Defender

> Vill du uppleva Microsoft 365 Defender? Du kan [utvärdera det i en laboratoriemiljö](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) eller [köra ett pilotprojekt i produktionen](m365d-pilot.md?ocid=cx-evalpilot).
>

Microsoft 365 Defender är en enhetlig företagsskyddssvit före och efter intrång som inbyggt koordinerar identifiering, skydd, undersökning och svar mellan slutpunkter, identiteter, e-post och program för att tillhandahålla integrerat skydd mot avancerade attacker.

Med den integrerade Microsoft 365 Defender-lösningen kan säkerhetsexperter samarbeta om hoten som signalerar att var och en av dessa produkter får och fastställa hotens fullständiga omfattning och påverkan. hur det angavs i miljön, vad det påverkades och hur det för närvarande påverkar organisationen. Microsoft 365 Defender vidtar automatisk åtgärd för att förhindra eller stoppa attacken och själv berörda postlådor, slutpunkter och användaridentiteter.  


<center><h2>Microsoft 365 Defender-tjänster</center></h2>
<table><tr><td><center><b><a href="/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender för Slutpunkt</b></center></a></td>
<td><center><b><a href="/office365/securitycompliance/office-365-atp"><b>Microsoft Defender för Office 365</b></center></a></td>
<td><center><b><a href="/azure-advanced-threat-protection/"><b>Microsoft Defender för identitet</b></a></center></td>
<td><center><b><a href="/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Microsoft 365 Interaktiv guide för Defender

I den här interaktiva guiden får du lära dig hur du skyddar organisationen med Microsoft 365 Defender. Du ser hur Microsoft 365 Defender kan hjälpa dig att identifiera säkerhetsrisker, undersöka attacker mot din organisation och förhindra skadliga aktiviteter automatiskt.

[Ta del av den interaktiva guiden](https://aka.ms/M365Defender-InteractiveGuide)



Microsoft 365 Defender Suite skyddar: 
- **Slutpunkter med Microsoft Defender** för slutpunkt – Microsoft Defender för Slutpunkt är en enhetlig slutpunktsplattform för förebyggande skydd, identifiering efter intrång, automatisk undersökning och svar. 
- **E-post** och samarbete med Microsoft Defender för Office 365 – Defender för Office 365 skyddar organisationen mot skadliga hot som kan orsakas av e-postmeddelanden, länkar (URL:er) och samarbetsverktyg. 
- **Identiteter** med Microsoft Defender för identitet och Azure AD-identitetsskydd – Microsoft Defender för identitet använder Active Directory-signaler för att identifiera, identifiera och undersöka avancerade hot, komprometterade identiteter och skadliga Insider-åtgärder som vidtas i organisationen. 
- **Program med Microsoft Cloud App-säkerhet** – Microsoft Cloud App-säkerhet är en omfattande SaaS-lösning som ger djup synlighet, starka datakontroller och förbättrat skydd av hot i dina molnappar. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Microsoft 365 I Defenders unika lager utökas de enskilda programsvitens komponenter så att de:
- Skydda mot attacker och koordinera skydd av skydd i hela programsviten med signaldelning och automatiserade åtgärder
- Berätta en fullständig historia om attackerna för produktaviseringar, beteenden och sammanhang för säkerhetsteam genom att sammanfoga data om aviseringar, misstänkta händelser och påverkade tillgångar till "incidenter"
- Automatisera svar på kompromett genom att självutlösa självbetjäning för påverkade tillgångar genom automatiserad åtgärd
- Gör det möjligt för säkerhetsteam att utföra detaljerade och effektiva hot efter hot i endpoint och Office data

![Bild på översiktssidan för incidenter](../../media/overview-incident.png) <br>
Incident med flera produkter (översikt)

![Bild på aviseringskö](../../media/incident-list.png)<br>
Alla relaterade aviseringar i programsvitens produkter korreleras till ett enskilt incident (vyn Aviseringar)

![Bild på incidentkö](../../media/advanced-hunting.png)<br>
Frågebaserad sökning ovanpå e-post- och slutpunktens rådata


Microsoft 365 Defenders funktioner för flera produkter omfattar: 
- **Enstaka fönsterruta** med flera produkter – central vy med all information för identifieringar, påverkade tillgångar, automatiserade åtgärder och relaterade bevis i en enda kö och ett enda fönster [i security.microsoft.com](https://security.microsoft.com). 
- **Kö för kombinerade** incidenter – För att hjälpa säkerhetspersonal att fokusera på vad som är viktigt genom att säkerställa hela attackomfånget grupperas påverkade tillgångar och automatiserade åtgärdsåtgärder tillsammans och visas i tid. 
- **Automatiskt svar på hot** – Viktig information om hot delas i realtid mellan Microsoft 365 Defender-produkterna för att stoppa attackens förlopp. Om till exempel en skadlig fil upptäcks på en slutpunkt som skyddas av Microsoft Defender för Endpoint, instrueras Defender för Office 365 att söka igenom och ta bort filen från alla e-postmeddelanden. Filen blockeras av hela säkerhetspaketet i Microsoft 365 synhåll.
- **Självhjälp** för komprometterade enheter, användaridentiteter och postlådor – Microsoft 365 Defender använder automatiska åtgärder och spelböcker med AI-drivna medel för att åtgärda påverkade tillgångar i ett säkert tillstånd. Microsoft 365 Defender utnyttjar de automatiska åtgärdsfunktionerna i programsvitens produkter för att säkerställa att alla påverkade tillgångar relaterade till ett incidenter åtgärdas automatiskt om det är möjligt.
- **Produkter** med hot på flera platser – Säkerhetsteam kan utnyttja sin unika kunskap om organisationen för att leta efter tecken på kompromisser genom att skapa egna anpassade frågor över rådata som samlas in av olika skyddsprodukter. Microsoft 365 Defender ger frågebaserad åtkomst till 30 dagars historiska rådata och aviseringsdata över slutpunkten och Microsoft Defender för Office 365 data. 


## <a name="get-started"></a>Komma igång
Microsoft 365 Licenskraven för Defender måste vara uppfyllda innan du kan aktivera tjänsten i Microsoft 365 säkerhetscenter [på security.microsoft.com](https://security.microsoft.com). Mer information finns i:
- [Licensieringskrav](prerequisites.md#licensing-requirements)
- [Aktivera Microsoft 365 Defender](m365d-enable.md)


## <a name="see-also"></a>Se även
- [Distribuera skyddsfunktioner för hot i hela Microsoft 365 E5](/microsoft-365/solutions/deploy-threat-protection)
