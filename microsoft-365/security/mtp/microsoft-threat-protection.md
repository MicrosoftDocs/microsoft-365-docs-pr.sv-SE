---
title: Microsoft Hotskydd
description: Microsoft Threat Protection är en samordnad hotskyddslösning som utformats för att skydda enheter, identitet, data och program
keywords: introduktion till Microsoft Threat Protection, cybersäkerhet, avancerat ihållande hot, företagssäkerhet, enheter, enhet, identitet, användare, data, applikationer, incidenter, automatiserad utredning och reparation, avancerad jakt
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
ms.openlocfilehash: 0e51e52db4e569716954aada1c5cea35ddc6dd0a
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528375"
---
# <a name="microsoft-threat-protection"></a>Microsoft Hotskydd

**Gäller:**
- Microsoft Hotskydd



Microsoft Threat Protection är en enhetlig företagsförsvarssvit före och efter överträdelse som samordnar identifiering, förebyggande, utredning och svar över slutpunkter, identiteter, e-post och program för att ge integrerat skydd mot avancerade attacker.

Med den integrerade Microsoft Threat Protection-lösningen kan säkerhetspersonal sy ihop de hotsignaler som var och en av dessa produkter tar emot och avgöra hotets fulla omfattning och inverkan. hur den kom in i miljön, vad den påverkas och hur den för närvarande påverkar organisationen. Microsoft Threat Protection vidtar automatiska åtgärder för att förhindra eller stoppa angrepp och självläker affected postlådor, slutpunkter och användaridentiteter.  


<center><h2>Microsofts tjänster för skydd av hot</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Avancerat hotskydd för Microsoft Defender</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Avancerat hotskydd i Office 365</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Azure avancerat skydd mot hot</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Säkerhet i Microsoft Cloud-appar</b></a></center></td>
</tr>
</table>
<br>



Microsoft Threat Protection suite skyddar: 
- **Slutpunkter med Microsoft Defender ATP** - Microsoft Defender ATP är en enhetlig slutpunktsplattform för förebyggande skydd, identifiering efter överträdelse, automatisk undersökning och svar. 
- **E-post och samarbete med Office 365 ATP** – Office 365 ATP skyddar organisationen mot skadliga hot som orsakas av e-postmeddelanden, länkar (webbadresser) och samarbetsverktyg. 
- **Identiteter med Azure ATP och Azure AD Identity Protection** – Azure ATP använder Active Directory-signaler för att identifiera, identifiera och undersöka avancerade hot, komprometterade identiteter och skadliga insideråtgärder som riktas mot din organisation. 
- **Program med Microsoft Cloud App-säkerhet** – Microsoft Cloud App security är en omfattande cross-SaaS-lösning som ger djup synlighet, starka datakontroller och förbättrat hotskydd för dina molnappar. 

Microsoft Threat Protections unika lager över flera produkter förstärker de enskilda svitkomponenterna till:
- Skydda dig mot attacker och samordna defensiva svar över hela sviten genom signaldelning och automatiserade åtgärder
- Berätta hela historien om attacken över produktvarningar, beteenden och sammanhang för säkerhetsteam genom att gå med i data på varningar, misstänkta händelser och påverkade tillgångar till "incidenter"
- Automatisera svar på kompromisser genom att utlösa självläkning för påverkade tillgångar genom automatisk reparation
- Gör det möjligt för säkerhetsteam att utföra detaljerad och effektiv hotjakt över slutpunkts- och Office-data

![Bild av incidentöversiktssida](../../media/overview-incident.png) <br>
Incident mellan produkter (översikt)

![Bild av larmkö](../../media/incident-list.png)<br>
Alla relaterade aviseringar i svitprodukterna korrelerade samman till en enda incident (varningsvy)

![Bild av incidentkö](../../media/advanced-hunting.png)<br>
Frågebaserad jakt ovanpå rådata för e-post och slutpunkt


Funktioner för flera produkter från Microsoft Threat Protection inkluderar: 
- **En enda fönsterruta för flera produkter** – Centralvy all information för identifiering, påverkade tillgångar, automatiserade åtgärder som vidtagits och relaterade bevis i en enda kö och en enda ruta i [security.microsoft.com](https://security.microsoft.com). 
- **Kombinerad incidentkö** – För att hjälpa säkerhetspersonal att fokusera på det som är kritiskt genom att säkerställa att hela angreppsomfattningen, påverkade tillgångar och automatiserade åtgärder för reparation grupperas tillsammans och visas i tid. 
- **Automatisk reaktion på hot** – Information om kritiska hot delas i realtid mellan Microsoft Threat Protection-produkterna för att stoppa utvecklingen av en attack. Om till exempel en skadlig fil identifieras på en slutpunkt som skyddas av Microsoft Defender ATP, instrueras Office 365 ATP att skanna och ta bort filen från alla e-postmeddelanden. Filen kommer att blockeras på sikt av hela Microsoft 365 säkerhetssvit.
- **Självläkande för komprometterade enheter, användaridentiteter och postlådor** – Microsoft Threat Protection använder AI-drivna automatiska åtgärder och spelböcker för att åtgärda påverkade tillgångar tillbaka till ett säkert tillstånd. Microsoft Threat Protection utnyttjar automatiska reparationsfunktioner för svitprodukterna för att säkerställa att alla påverkade tillgångar som är relaterade till en incident automatiskt åtgärdas där det är möjligt.
- **Cross-produkt hot jakt** - Säkerhetsteam kan utnyttja sin unika organisatoriska kunskap för att jaga efter tecken på kompromiss genom att skapa sina egna anpassade frågor över rådata som samlats in av de olika skyddsprodukter. Microsoft Threat Protection ger frågebaserad åtkomst till 30 dagar med historiska råsignaler och varningsdata över slutpunkts- och Office 365 ATP-data. 


## <a name="get-started"></a>Komma igång
Licenskraven för Microsoft Threat Protection måste uppfyllas innan du kan aktivera tjänsten i Microsoft 365-säkerhetscentret på [security.microsoft.com](https://security.microsoft.com). För mer information, läs:
- [Licenskrav](prerequisites.md#licensing-requirements)
- [Aktivera Microsoft Hotskydd](mtp-enable.md)
