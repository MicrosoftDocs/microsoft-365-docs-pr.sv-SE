---
title: Skydd av Hot mot Microsoft
description: Microsoft Threat Protection är en samordnad lösning för hotskydd som utformats för att skydda enheter, identitet, data och applikationer
keywords: introduktion till Microsoft Threat Protection, it-säkerhet, avancerat beständigt hot, företagssäkerhet, enheter, enhet, identitet, användare, data, applikationer, incidenter, automatiserad undersökning och sanering, avancerad jakt
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 62901a08b8e040266a94967170674336eb1035c8
ms.sourcegitcommit: 45ee610a380db113c2a50f6ea82d30137498babb
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/27/2020
ms.locfileid: "42808626"
---
# <a name="microsoft-threat-protection"></a>Skydd av Hot mot Microsoft

**Gäller:**
- Skydd av Hot mot Microsoft



Microsoft Threat Protection är en enhetlig försvarssvit före och efter intrång som integreras i inbyggt över slutpunkt, identitet, e-post och program för att upptäcka, förebygga, undersöka och automatiskt svara på sofistikerade attacker.  

Med den integrerade Lösningen för Microsoft Threat Protection kan säkerhetsexperter sy ihop de hotsignaler som var och en av dessa produkter tar emot och bestämma hotets fulla omfattning och effekter. hur den kom in i miljön, vad den påverkas och hur den för närvarande påverkar organisationen. Microsoft Threat Protection vidtar automatiska åtgärder för att förhindra eller stoppa attacken och självläka berörda postlådor, slutpunkter och användaridentiteter.  


<center><h2>Microsofts tjänster för skydd av hot</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender avancerat hotskydd</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Office 365 Avancerat hotskydd</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Azure avancerat hotskydd</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Säkerhet för Microsoft Cloud-appar</b></a></center></td>
</tr>
</table>
<br>



Microsoft Threat Protection suite skyddar: 
- **Slutpunkter med Microsoft Defender ATP** - Microsoft Defender ATP är en enhetlig slutpunktsplattform för förebyggande skydd, identifiering efter intrång, automatiserad undersökning och svar. 
- **E-post och samarbete med Office 365 ATP** – Office 365 ATP skyddar din organisation mot skadliga hot från e-postmeddelanden, länkar (URL:er) och samarbetsverktyg. 
- **Identiteter med Azure ATP och Azure AD Identity Protection** – Azure ATP använder Active Directory-signaler för att identifiera, identifiera och undersöka avancerade hot, komprometterade identiteter och skadliga insideråtgärder riktade mot din organisation. 
- **Program med Microsoft Cloud App-säkerhet** – Microsoft Cloud App-säkerhet är en omfattande saas-lösning som ger djup synlighet, starka datakontroller och förbättrat hotskydd för dina molnappar. 

Microsoft Threat Protections unika korsproduktslager förstärker de enskilda svitkomponenterna till:
- Skydda mot attacker och samordna defensiva svar över hela sviten genom signaldelning och automatiserade åtgärder
- Berätta hela historien om attacken över produktvarningar, beteenden och sammanhang för säkerhetsteam genom att gå med data om aviseringar, misstänkta händelser och påverkade tillgångar till "incidenter"
- Automatisera svaret på kompromissen genom att utlösa självläkning för påverkade tillgångar genom automatiserad sanering
- Göra det möjligt för säkerhetsteam att utföra detaljerad och effektiv hotjakt över slutpunkt soch Office-data

![Bild av incidentöversiktssidan](../../media/overview-incident.png) <br>
Incident över flera produkter (översikt)

![Bild av varningskö](../../media/incident-list.png)<br>
Alla relaterade varningar i svitens produkter korrelerade till en enda incident (varningsvy)

![Bild av incidentkön](../../media/advanced-hunting.png)<br>
Frågebaserad jakt ovanpå e-post- och slutpunktsrådata


Microsoft Threat Protection cross-product funktioner inkluderar: 
- **Gemensam produktruta med glas** – Centralvy all information för upptäckter, påverkade tillgångar, automatiserade åtgärder som vidtagits och relaterade bevis i en enda kö och en enda ruta i [security.microsoft.com](https://security.microsoft.com). 
- **Kombinerad incidentkö** – För att hjälpa säkerhetspersonal att fokusera på det som är avgörande genom att säkerställa hela attackomfattningen grupperas påverkade tillgångar och automatiserade saneringsåtgärder tillsammans och visas i tid. 
- **Automatiskt svar på hot** - Information om kritiskt hot delas i realtid mellan Microsoft Threat Protection-produkterna för att stoppa utvecklingen av en attack. Om till exempel en skadlig fil upptäcks på en slutpunkt som skyddas av Microsoft Defender ATP instrueras Office 365 ATP att skanna och ta bort filen från alla e-postmeddelanden. Filen kommer att blockeras på plats av hela Microsoft 365-säkerhetspaketet.
- **Självläkning för komprometterade enheter, användaridentiteter och postlådor** – Microsoft Threat Protection använder AI-drivna automatiska åtgärder och spelböcker för att åtgärda påverkade tillgångar tillbaka till ett säkert tillstånd. Microsoft Threat Protection utnyttjar automatiskreparationsfunktioner för svitprodukterna för att säkerställa att alla påverkade tillgångar som är relaterade till en incident automatiskt åtgärdas där det är möjligt.
- **Cross-product hot jakt** - Säkerhetsteam kan utnyttja sin unika organisatoriska kunskap för att jaga tecken på kompromisser genom att skapa sina egna anpassade frågor över rådata som samlats in av de olika skyddsprodukter. Microsoft Threat Protection ger frågebaserad åtkomst till 30 dagar av historiska råsignaler och varningsdata över slutpunkt och Office 365 ATP-data. 


## <a name="get-started"></a>Komma igång
Licenskraven för Microsoft Threat Protection måste uppfyllas innan du kan aktivera tjänsten i Microsoft 365-säkerhetscentret på [security.microsoft.com](https://security.microsoft.com). För mer information, läs:
- [Licenskrav](prerequisites.md#licensing-requirements)
- [Aktivera Microsoft Threat Protection](mtp-enable.md)
