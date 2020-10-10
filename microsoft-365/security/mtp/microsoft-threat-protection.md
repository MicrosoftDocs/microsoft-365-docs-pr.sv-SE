---
title: Microsoft Hotskydd
description: Skydd mot Microsoft Threat är en koordinerad skydds lösning som är utformad för att skydda enheter, identiteter, data och program
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
- m365-initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: 16dd0ffa6ac07832196e6672e811c64902d96cf4
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48414352"
---
# <a name="microsoft-threat-protection"></a>Microsoft Hotskydd

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gäller för:**
- Microsoft Threat Protection



Skydd mot Microsoft Threat är en enhetlig för hands version av företagets för-och efter intrång som interagerar med identifiering, förebyggande, undersökning och svar på slut punkter, identiteter, e-postmeddelanden och program för att ge integrerat skydd mot sofistikerade attacker.

Med den integrerade Microsoft Threat Protection-lösningen kan säkerhetsexperterna häfta ihop hotet så att dessa produkter får och fastställer den fulla omfattningen och påverkan av hotet; hur den har kommit till miljön, vad den påverkar och hur den för närvarande påverkar organisationen. Microsoft Threat Protection vidtar automatisk åtgärd för att förhindra eller stoppa angreppet och själv åtgärdade post lådor, slut punkter och användar identiteter.  


<center><h2>Skydds tjänster för Microsoft Threat</center></h2>
<table><tr><td><center><b><a href="https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection"><b>Microsoft Defender Avancerat skydd</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/office365/securitycompliance/office-365-atp"><b>Office 365 Avancerat skydd</b></center></a></td>
<td><center><b><a href="https://docs.microsoft.com/azure-advanced-threat-protection/"><b>Azure Avancerat skydd</b></a></center></td>
<td><center><b><a href="https://docs.microsoft.com/cloud-app-security/"><b>Säkerhet för Microsoft Cloud App</b></a></center></td>
</tr>
</table>
<br>


>[!TIP]
>Kolla den här [interaktiva guiden för Microsoft Threat Protection](https://aka.ms/MTP-Interactive-Guide).


Microsoft Threat Protection Suite skyddar: 
- **Slut punkter med Microsoft Defender ATP** – Microsoft Defender ATP är en plattform för att skydda dig, efter överträdelse, automatisk undersökning och svar. 
- **E-post och samarbete med office 365 ATP** -Office 365 ATP skyddar din organisation mot illasinnade hot via e-postmeddelanden, länkar (URL: er) och samarbets verktyg. 
- **Identiteter med Azure ATP och Azure AD Identity Protection** – Azure ATP använder Active Directory-signaler för att identifiera, upptäcka och undersöka avancerade hot, kompromissade identiteter och illasinnade Insider-åtgärder på din organisation. 
- **Program med Microsoft Cloud App-säkerhet** – Microsoft Cloud App Security är en omfattande SaaS lösning som ger en djup insyn, starka data kontroller och förbättrat skydd för dina molnappar. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Microsofts unika Cross-Product-lager förstärker de enskilda Suite-komponenterna till:
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


Funktioner för Microsofts hot Protection kors produkt inkluderar: 
- **Kors produkt ett fönster i glas** Central Visa all information om identifieringar, påverkade till gångar, automatiserade åtgärder som är vidtagna och närliggande bevis i en enda kö och en enda fönster ruta i [Security.Microsoft.com](https://security.microsoft.com). 
- Sammanslagna **händelse köer** – för att hjälpa säkerhetsutövarna att fokusera på vad som är kritiskt genom att säkerställa hela attackens omfattning, förvissaade till gångar och automatiska reparations åtgärder grupperas tillsammans och på ett säkert sätt. 
- **Autosvar** – kritiskt Hot-information delas i real tid mellan Microsofts hot skydds produkter för att förhindra att en attack fortskrider. Om till exempel en skadlig fil identifieras på en slut punkt som skyddas av Microsoft Defender ATP, instruerar den Office 365 ATP att skanna och ta bort filen från alla e-postmeddelanden. Filen blockeras på sikt från hela Microsoft 365-säkerhetssviten.
- **Själv återställning för angripna enheter, användar identiteter och post lådor** – Microsoft Threat Protection använder AI-drivna automatiska åtgärder och playbooks för att åtgärda berörda till gångar i ett säkert tillstånd. Microsoft Threat Protection utnyttjar automatisk reparations kapacitet för Suite-produkterna för att säkerställa att alla berörda till gångar som är relaterade till en olycka automatiskt åtgärdas om möjligt.
- Stöldskydd med **olika produkter** -säkerhets team kan utnyttja sin unika organisatoriska kunskap för att hitta inloggnings problem genom att skapa egna anpassade frågor via rå data som samlas in av de olika skydds produkterna. Microsoft Threat Protection ger Query-baserad till gång till 30 dagar med historiskt RAW-signaler och aviserings data över slut punkter och Office 365 ATP-data. 


## <a name="get-started"></a>Komma igång
Licensierings kraven för Microsoft Threat Protection måste nås innan du kan aktivera tjänsten i Microsoft 365 Security Center på [Security.Microsoft.com](https://security.microsoft.com). Mer information finns i:
- [Licens krav](prerequisites.md#licensing-requirements)
- [Aktivera Microsoft Hotskydd](mtp-enable.md)
