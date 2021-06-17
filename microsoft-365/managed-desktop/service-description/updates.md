---
title: Hur uppdateringar hanteras i Microsoft Managed Desktop
description: Att hålla Microsoft Managed Desktop uppdaterat är en balans mellan hastighet och stabilitet.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5d78f695785cd81b51e20b90cdefbb3790cf6197
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984742"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Hur uppdateringar hanteras i Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop ansluter alla enheter till en modern molnbaserad infrastruktur. Att hålla Windows, Office, drivrutiner, inbyggd programvara och Microsoft Store för företag-program uppdaterade är en balans mellan hastighet och stabilitet. Vi använder uppdateringsgrupper för att säkerställa att uppdateringar och principer distribueras i operativsystemet på ett säkert sätt. Mer information finns i videon Microsoft [Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP). 

Uppdateringar som släppts av Microsoft är kumulativa och kategoriseras som kvalitets- eller funktionsuppdateringar.
Mer information finns i [Windows Update för företag: Uppdateringstyper.](/windows/deployment/update/waas-manage-updates-wufb#update-types) 

## <a name="update-groups"></a>Uppdatera grupper


Microsoft Managed Desktop använder fyra Azure AD-grupper för att hantera uppdateringar:

- **Test:** Används för att verifiera ändringar i principen för Microsoft Managed Desktop, operativsystemuppdateringar, funktionsuppdateringar och andra ändringar som skickas till Azure AD-organisationen ("klientorganisation"). Passar bäst för tester eller användare som kan ge tidig feedback. Testgruppen är undantagen från alla fastställda servicenivåavtal och användarsupport. Den här gruppen kan användas för att verifiera kompatibiliteten för program med nya princip- eller operativsystemändringar.  
- **First**: Contains early software adopters and devices that could be subject to pre-release updates. Enheter i den här gruppen kan uppleva avbrott om det finns scenarier som inte täcks under testningen i testgruppen.
- **Snabbt:** Prioriterar hastigheten framför stabilitet. Användbart för att identifiera kvalitetsproblem innan de erbjuds till den breda gruppen. Den här gruppen fungerar som ett nästa lager med validering men är vanligtvis stabilare än test- och första grupperna. 
- **Bred:** Sista gruppen för att få tillgängliga funktioner och kvalitetsuppdateringar. Den här gruppen innehåller de flesta användare i Azure AD-organisationen och ger därför stabilitet över hastigheten i distributionen. Testning av appar bör göras här eftersom miljön är mest stabil.

### <a name="moving-devices-between-update-groups"></a>Flytta enheter mellan uppdateringsgrupper
Du kanske vill att vissa enheter ska få uppdateringar senast och andra som du vill gå först. Om du vill flytta de här enheterna till lämplig uppdateringsgrupp går [du till Tilldela enheter till en distributionsgrupp.](../working-with-managed-desktop/assign-deployment-group.md)

Mer information om roller och ansvarsområden i dessa distributionsgrupper finns i Microsoft [Hanterade skrivbordsroller och ansvarsområden](../intro/roles-and-responsibilities.md)

### <a name="using-microsoft-managed-desktop-update-groups"></a>Använda uppdateringsgrupper för Microsoft Managed Desktop 
Det finns delar av tjänsten som du hanterar, till exempel programdistribution, där det kan vara nödvändigt att rikta alla hanterade enheter.

## <a name="how-update-deployment-works"></a>Så här fungerar uppdateringsdistribution:
1. Microsoft Managed Desktop distribuerar en ny funktion eller kvalitetsuppdatering enligt schemat i följande tabell.
2. Under distributionen övervakar Microsoft Managed Desktop för tecken på fel eller störningar baserat på diagnostikdata och användarens supportsystem. Om några identifieras pausar vi direkt distributionen till alla nuvarande och framtida grupper.
    - Exempel: om ett problem upptäcks när du distribuerar en kvalitetsuppdatering till första gruppen och sedan uppdaterar distributionerna till Första, Snabbt och Breda pausas tills problemet är löst.
    - Du kan rapportera kompatibilitetsproblem genom att arkivera ett ärende i administrationsportalen för Microsoft Managed Desktop.
    - Funktions- och kvalitetsuppdateringar pausas oberoende av varandra. Pausa gäller i 35 dagar som standard, men kan minskas eller utökas beroende på om problemet åtgärdas.
3. När grupperna inte har distribuerats återupptas distributionen enligt schemat i tabellen.

Den här distributionsprocessen gäller för både funktions- och kvalitetsuppdateringar, men tidslinjen varierar för var och en.


<table>
    <tr><th colspan="5">Uppdatera distributionsinställningar</th></tr>
    <tr><th>Uppdateringstyp</th><th>Test</th><th>Första</th><th>Snabbt</th><th>Bred</th></tr>
    <tr><td>Kvalitetsuppdateringar för operativsystem</td><td>0 dagar</td><td>0 dagar</td><td>0 dagar</td><td>3 dagar</td></tr>
    <tr><td>Funktionsuppdateringar för operativsystem</td><td>0 dagar</td><td>30 dagar</td><td>60 dagar</td><td>90 dagar</td></tr>
    <tr><td>Drivrutiner/inbyggd programvara</td><td colspan="4">Följer schemat för kvalitetsuppdateringar</td></tr>
    <tr><td>Antivirusdefinition</td><td colspan="4">Uppdateras med varje genomsökning</td></tr>
    <tr><td> Microsoft 365 Apps för företag</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">Läs mer</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">Läs mer</a></td></tr>
    <tr><td>Microsoft Teams</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/teams#updates">Läs mer</a></td></tr>
</table>

>[!NOTE]
>Upp skjuta upp perioder är avsiktligt utformade för att säkerställa hög säkerhet och prestanda för alla användare. Baserat på data som har samlats på alla Microsoft Managed Desktop-enheter och olika omfattning och påverkan på uppdateringar reserveras dessutom flexibilitet i Microsoft Managed Desktop för att på ad hoc-basis ändra längden på uppslagsperioderna ovan för alla distributionsgrupper.
>
>Microsoft Hanterat skrivbord genomför en oberoende utvärdering av varje Windows-funktionsutgåra för att utvärdera dess behov och användbarhet för de hanterade klientdatorerna. Med andra sätt kan microsoft Hanterat skrivbord kanske eller kanske inte distribuera alla uppdateringar av Windows-funktioner. 

## <a name="windows-insider-program"></a>Windows Insider Program

Microsoft Managed Desktop stöder inte enheter som ingår i Windows Insider-programmet. Windows Insider-programmet används för att validera Windows-förhandsprogramvara och är avsett för enheter som inte är verksamhetskritiska. Även om det är ett viktigt Microsoft-initiativ är det inte avsett för bred distribution i produktionsmiljöer. 

Alla enheter som kan användas med Windows Insider-versioner kan läggas i testgruppen och undantas från uppdateringsavtal på tjänstnivå och användarsupport från Microsoft Managed Desktop.

## <a name="bandwidth-management"></a>Bandbreddshantering

Vi använder [Leveransoptimering](/windows/deployment/update/waas-delivery-optimization) för alla uppdateringar av operativsystem och drivrutiner. Leveransoptimering minimerar nedladdningsstorleken från Windows Update-tjänsten genom att söka efter uppdateringar från kollegor inom företagsnätverket.