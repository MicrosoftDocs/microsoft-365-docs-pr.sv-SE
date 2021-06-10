---
title: Hur uppdateringar hanteras i Microsoft Hanterat skrivbord
description: Att Microsoft Hanterat skrivbord är uppdaterad är en balans mellan hastighet och stabilitet.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5961ac4eb16928754849f5f32ecd06d4d2e4650d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917722"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Hur uppdateringar hanteras i Microsoft Hanterat skrivbord


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Hanterat skrivbord alla enheter till en modern molnbaserad infrastruktur. Att Windows, Office, drivrutiner, inbyggd programvara och Microsoft Store för företag-program är uppdaterade är en balans mellan hastighet och stabilitet. Distributionsgrupper används för att säkerställa att operativsystemuppdateringar och principer distribueras på ett säkert sätt. Mer information finns i videon Microsoft Hanterat skrivbord [Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP).

Uppdateringar som släppts av Microsoft är kumulativa och kategoriseras som kvalitets- eller funktionsuppdateringar.
Mer information finns i [Windows för företag: Uppdateringstyper.](/windows/deployment/update/waas-manage-updates-wufb#update-types) 

## <a name="update-groups"></a>Uppdatera grupper

Microsoft Hanterat skrivbord använder fyra Azure AD-grupper för att hantera uppdateringar:

- **Test:** Används för Microsoft Hanterat skrivbord principändringar, operativsystemuppdateringar, funktionsuppdateringar och andra ändringar till klientorganisationen. Det bör inte finnas några användare i testgruppen. Testgruppen är undantagen från alla fastställda servicenivåavtal och användarsupport. Den här gruppen kan användas för att verifiera kompatibiliteten för program med nya princip- eller operativsystemändringar.  
- **First**: Contains early software adopters and devices that could be subject to pre-release updates. Enheter i den här gruppen kan uppleva avbrott om det finns scenarier som inte täcks under testningen i testgruppen.
- **Snabbt:** Prioriterar hastigheten framför stabilitet. Användbart för att identifiera kvalitetsproblem innan de erbjuds till den breda gruppen. Den här gruppen fungerar som ett nästa lager med validering men är vanligtvis stabilare än test- och första grupperna. 
- **Bred:** Sista gruppen för att få tillgängliga funktioner och kvalitetsuppdateringar. Den här gruppen innehåller de flesta användare i klientorganisationen och gör därför stabilitet över hastigheten i distributionen. Testning av appar bör göras här eftersom miljön är mest stabil. 

### <a name="moving-devices-between-update-groups"></a>Flytta enheter mellan uppdateringsgrupper
Du kanske vill att vissa enheter ska få uppdateringar senast och andra som du vill gå först. Om du vill flytta de här enheterna till lämplig uppdateringsgrupp skickar du en [supportbegäran](../working-with-managed-desktop/admin-support.md?view=o365-worldwide) till administratören så flyttar vi enheterna åt dig. 

> [!NOTE]
> Om du behöver flytta en användare till en annan uppdateringsgrupp skickar du en supportbegäran. Flytta inte enheter mellan uppdatera grupper själv. Det finns allvarliga konsekvenser om en enhet flyttas felaktigt. Enheten kan uppdateras oväntat och principer kan vara i konflikt och enhetskonfigurationen ändras.

Mer information om roller och ansvarsområden inom dessa distributionsgrupper finns i Microsoft Hanterat skrivbord [Roller och ansvarsområden](../intro/roles-and-responsibilities.md)

### <a name="using-microsoft-managed-desktop-update-groups"></a>Använda Microsoft Hanterat skrivbord uppdatera grupper 
Det finns delar av tjänsten som du hanterar, till exempel programdistribution, där det kan vara nödvändigt att rikta alla hanterade enheter. I de här instanserna är det vettigt att använda uppdateringsgrupper för att nå fram till de användarna med förståelse för att du inte kan lägga till, ta bort eller ändra medlemskap i de grupperna. 

## <a name="how-update-deployment-works"></a>Så här fungerar uppdateringsdistribution:
1. Microsoft Hanterat skrivbord distribuerar en ny funktion eller kvalitetsuppdatering enligt schemat som anges i följande tabell.
2. Under distributionen Microsoft Hanterat skrivbord övervakas för tecken på fel eller störningar baserat på diagnostikdata och användarens supportsystem. Om några identifieras pausar vi direkt distributionen till alla nuvarande och framtida grupper.
    - Exempel: om ett problem upptäcks när du distribuerar en kvalitetsuppdatering till första gruppen och sedan uppdaterar distributionerna till Första, Snabbt och Breda pausas tills problemet är löst.
    - Du kan rapportera kompatibilitetsproblem genom att spara ett ärende i Microsoft Hanterat skrivbord administrationsportalen.
    - Funktions- och kvalitetsuppdateringar pausas oberoende av varandra. Pausa gäller i 35 dagar som standard, men kan minskas eller utökas beroende på om problemet åtgärdas.
3. När grupperna har pausats återupptas distributionen enligt schemat i tabellen.

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
>Upp skjuta upp perioder är avsiktligt utformade för att säkerställa hög säkerhet och prestanda för alla användare. Vidare, baserat på data som har samlats på alla Microsoft Hanterat skrivbord-enheter och olika omfattning och påverkan på uppdateringar, reserverar Microsoft Hanterat skrivbord flexibilitet att ändra längden på uppslagsperioderna ovan för alla distributionsgrupper vid behov.
>
>Microsoft Hanterat skrivbord en oberoende utvärdering av varje version av Windows för att utvärdera dess behov och användbarhet för de hanterade innehavarna. Därför kan Microsoft Hanterat skrivbord distribuera alla uppdateringar Windows funktioner. 

## <a name="windows-insider-program"></a>Windows Insider Program

Microsoft Hanterat skrivbord stöder inte enheter som ingår i Windows Insider-programmet. Programmet Windows Insider används för att validera förhandsutgågår av Windows och är avsett för enheter som inte är verksamhetskritiska. Även om det är ett viktigt Microsoft-initiativ är det inte avsett för bred distribution i produktionsmiljöer. 

Alla enheter som hittas med Windows Insider-versionerna kan läggas i testgruppen och undantas från uppdatering av servicenivåavtal och användarsupport från Microsoft Hanterat skrivbord.

## <a name="bandwidth-management"></a>Bandbreddshantering

Vi använder [Leveransoptimering](/windows/deployment/update/waas-delivery-optimization) för alla uppdateringar av operativsystem och drivrutiner. Det minimerar nedladdningsstorleken från tjänsten Windows genom att söka efter uppdateringar från kollegor inom företagsnätverket.