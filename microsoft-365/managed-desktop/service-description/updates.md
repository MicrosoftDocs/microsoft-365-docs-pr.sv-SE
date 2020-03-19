---
title: Så här hanteras uppdateringar på Microsoft Managed Desktop
description: Att hålla Microsoft Managed Desktop uppdaterat är en balans mellan hastighet och stabilitet.
keywords: Microsoft Managed Desktop, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0acbb82001d8856639f5b67daa99323f333e26ad
ms.sourcegitcommit: 213b33cbf14e35e6dc563e0b700a4eed5e42e91d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/26/2020
ms.locfileid: "42811450"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Så här hanteras uppdateringar på Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop ansluter alla enheter till en modern molnbaserad infrastruktur. Att hålla Windows-, Office-, drivrutiner, inbyggd programvara och Microsoft Store för företag uppdaterade är en balans mellan hastighet och stabilitet. Distributionsgrupper används för att säkerställa att uppdateringar och principer för operativsystemet distribueras på ett säkert sätt. Mer information om detta finns i videon [Microsoft Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP).

Uppdateringar som publiceras av Microsoft är kumulativa och kategoriseras som kvalitets- eller funktionsuppdateringar.
Mer information finns i [Windows Update för företag: Uppdatera typer](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types). 

## <a name="update-groups"></a>Uppdatera grupper

Microsoft Managed Desktop använder fyra Azure AD-grupper för att hantera uppdateringar:

- **Test**: Används för att validera microsoftmanaged desktop-principändringar, operativsystemuppdateringar, funktionsuppdateringar och andra ändringar som skickas till klienten. Det bör inte finnas några slutanvändare placerade i testgruppen. Testgruppen är undantagen från etablerade servicenivåavtal och slutanvändarsupport. Den här gruppen är tillgänglig för att validera kompatibilitet för program med nya princip- eller operativsystemändringar.  
- **Först**: Innehåller tidiga programvaruanvändare och enheter som kan bli föremål för förhandsuppdateringar. Enheter i den här gruppen kan uppleva avbrott om det finns scenarier som inte täcktes under testningen i testringen.
- **Snabb**: Prioriterar hastighet över stabilitet. Användbart för att upptäcka kvalitetsproblem innan de erbjuds till den breda gruppen. Den här gruppen fungerar som ett nästa lager av validering men är i allmänhet stabilare än test- och första grupperna. 
- **Bred:** Senaste gruppen att ha funktions- och kvalitetsuppdateringar tillgängliga. Den här gruppen innehåller majoriteten av användarna i klienten och gynnar därför stabilitet över hastigheten i distributionen. Testning av appar bör göras här eftersom miljön är mest stabil. 

> [!NOTE]
> Om du behöver flytta en användare till en annan uppdateringsgrupp skickar du en supportbegäran. Mer information om hur du skickar supportförfrågningar finns i [Support för Microsoft Managed Desktop.](support.md) Om du flyttar en användare själv återställs flytten.

Mer informationsroller och ansvarsområden med dessa distributionsgrupper finns i [Microsoft hanterade skrivbordsroller och ansvarsområden](../intro/roles-and-responsibilities.md)

Så här fungerar uppdateringsdistribution:
- Microsoft Managed Desktop distribuerar en ny funktions- eller kvalitetsuppdatering enligt det schema som anges nedan.
- Under distributionen övervakar Microsoft Managed Desktop efter tecken på fel eller störningar (baserat på diagnostikdata och supportsystemet för slutanvändare). Om någon identifieras pausas distributionen till alla aktuella och framtida grupper omedelbart.
    - Exempel: Om ett problem upptäcks när du distribuerar en kvalitetsuppdatering till den första gruppen, uppdaterasedan distributionerna till Först, Snabb och Bred pausas tills problemet är löst.
    - Kompatibilitetsproblem kan rapporteras genom att en biljett lämnas in i Microsoft Managed Desktop Admin-portalen.
- Funktions- och kvalitetsuppdateringar pausas oberoende av dem. Paus en paus gäller i 35 dagar som standard, men kan minskas eller förlängas beroende på om problemet åtgärdas.
- När grupperna har avbrutits återupptas distributionen enligt schemat nedan.
- Den här distributionsprocessen gäller både funktions- och kvalitetsuppdateringar, även om tidslinjen varierar för varje.




<table>
<tr><th colspan="5">Uppdatera distributionsinställningar</th></tr>
<tr><th>Typ av uppdatering</th><th>Test</th><th>Första</th><th>Snabb</th><th>Bred</th></tr>
<tr><td>Kvalitetsuppdateringar för operativsystemet</td><td>0 dagar</td><td>0 dagar</td><td>0 dagar</td><td>3 dagar</td></tr>
<tr><td>Funktionsuppdateringar för operativsystemet</td><td>0 dagar</td><td>30 dagar</td><td>60 dagar</td><td>90 dagar</td></tr>
<tr><td>Drivrutiner/inbyggd programvara</td><td colspan="4">Följer schemat för kvalitetsuppdateringar</td></tr>
<tr><td>Definition av antivirus</td><td colspan="4">Uppdaterad med varje genomsökning</td></tr>
<tr><td>Office 365 ProPlus</td><td colspan="4">Följer Office månadskanal
</table>

Mer information om månadskanalen för Office 365 ProPlus finns i [Översikt över uppdateringskanaler för Office 365 ProPlus](https://docs.microsoft.com/deployoffice/overview-of-update-channels-for-office-365-proplus).

>[!NOTE]
>Dessa uppskovsperioder är avsiktligt utformade för att säkerställa höga säkerhets- och prestandastandarder för alla användare. Baserat på data som samlats in på alla Microsoft Managed Desktop-enheter och uppdateringarnas varierande omfattning och inverkan, förbehåller sig Microsoft Managed Desktop flexibilitet för att ändra längden på ovanstående uppskovsperioder för alla distributionsgrupper på en annons särskild grund.
>
>Microsoft Managed Desktop gör en oberoende bedömning av varje Windows-funktionsutgåva för att utvärdera dess nödvändighet och användbarhet för dess hanterade klienter. Därför kan Microsoft Managed Desktop distribuera alla Windows-funktionsuppdateringar. 

## <a name="windows-insider-program"></a>Windows Insider Program

Microsoft Managed Desktop stöder inte enheter som ingår i Windows Insider-programmet. Windows Insider-programmet används för att validera windows-programvara före lanseringen och är avsett för enheter som inte är verksamhetskritiska enheter. Även om detta är ett viktigt Microsoft-initiativ är det inte avsett för bred distribution i produktionsmiljöer. 

Alla enheter som hittas med Windows Insider-versioner kan placeras i testgruppen och kommer att undantas från avtal på uppdateringstjänstnivå och slutanvändarsupport från Microsoft Managed Desktop.

## <a name="bandwidth-management"></a>Bandbreddshantering

Vi använder [leveransoptimering](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) för alla operativsystem och drivrutinsuppdateringar. Detta minimerar hämtningsstorleken från Windows Update-tjänsten genom att söka uppdateringar från peer-datorer i företagsnätverket.


