---
title: Så här hanteras uppdateringar på Microsoft Managed Desktop
description: Att hålla Microsoft Managed Desktop uppdaterat är en balans mellan hastighet och stabilitet.
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 02e6eb5914af9ad72971029913d31b214ebbd190
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011941"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Så här hanteras uppdateringar på Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop ansluter alla enheter till en modern molnbaserad infrastruktur. Att hålla Windows, Office, drivrutiner, inbyggd programvara och Microsoft Store för företag-program uppdaterade är en balans mellan hastighet och stabilitet. Distributionsgrupper används för att säkerställa att uppdateringar och principer för operativsystemet distribueras på ett säkert sätt. Mer information om detta finns i videon [Microsoft Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP).

Uppdateringar som släpps av Microsoft är kumulativa och kategoriseras som kvalitets- eller funktionsuppdateringar.
Mer information finns i [Windows Update för företag: Uppdateringstyper](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types). 

## <a name="update-groups"></a>Uppdatera grupper

Microsoft Managed Desktop använder fyra Azure AD-grupper för att hantera uppdateringar:

- **Test:** Används för att validera ändringar av Microsoft Managed Desktop-princip, uppdateringar av operativsystem, funktionsuppdateringar och andra ändringar som har pressats till klienten. Det bör inte finnas några slutanvändare placerade i testgruppen. Testgruppen är undantagen från alla etablerade servicenivåavtal och slutanvändarsupport. Den här gruppen är tillgänglig för användning för att verifiera kompatibilitet för program med nya princip- eller operativsystemändringar.  
- **Första**: Innehåller tidiga programantörer och enheter som kan vara föremål för uppdateringar i förhandsversionen. Enheter i den här gruppen kan drabbas av avbrott om det finns scenarier som inte täcktes under testningen i testringen.
- **Snabb**: Prioriterar hastighet framför stabilitet. Användbart för att upptäcka kvalitetsproblem innan de erbjuds till broad-gruppen. Den här gruppen fungerar som nästa verifieringslager men är i allmänhet stabilare än test- och förstagrupperna. 
- **Bred:** Sista gruppen att ha funktions- och kvalitetsuppdateringar tillgängliga. Den här gruppen innehåller majoriteten av användarna i klienten och gynnar därför stabilitet framför hastighet i distributionen. Testning av appar bör göras här eftersom miljön är mest stabil. 

> [!NOTE]
> Om du behöver flytta en användare till en annan uppdateringsgrupp skickar du en supportbegäran. Mer information om hur du skickar supportbegäranden finns i [Support för Microsoft Managed Desktop.](support.md) Om du flyttar en användare själv återställs flytten.

Mer information om roller och ansvarsområden med dessa distributionsgrupper finns i [Microsoft Hanterade skrivbordsroller och ansvarsområden](../intro/roles-and-responsibilities.md)

Så här fungerar uppdateringsdistribution:
- Microsoft Managed Desktop distribuerar en ny funktion eller kvalitetsuppdatering enligt det schema som anges nedan.
- Under distributionen övervakar Microsoft Hanterade skrivbord tecken på fel eller avbrott (baserat på diagnostikdata och slutanvändarens supportsystem). Om någon identifieras pausas distributionen till alla aktuella och framtida grupper omedelbart.
    - Exempel: Om ett problem upptäcks när en kvalitetsuppdatering distribueras till den första gruppen, pausas alla distributioner till Först, Snabb och Bred tills problemet är löst.
    - Kompatibilitetsproblem kan rapporteras genom att du skickar en biljett i Microsoft Managed Desktop Admin-portalen.
- Funktions- och kvalitetsuppdateringar pausas oberoende av dem. Paus är i kraft i 35 dagar som standard, men kan minskas eller förlängas beroende på om problemet åtgärdas.
- När grupperna inte har pausats återupptas distributionen enligt schemat nedan.
- Den här distributionsprocessen gäller både funktions- och kvalitetsuppdateringar, även om tidslinjen varierar för varje.




<table>
<tr><th colspan="5">Uppdatera distributionsinställningar</th></tr>
<tr><th>Typ av uppdatering</th><th>Test</th><th>Första</th><th>Snabb</th><th>Bred</th></tr>
<tr><td>Kvalitetsuppdateringar för operativsystemet</td><td>0 dagar</td><td>0 dagar</td><td>0 dagar</td><td>3 dagar</td></tr>
<tr><td>Funktionsuppdateringar för operativsystem</td><td>0 dagar</td><td>30 dagar</td><td>60 dagar</td><td>90 dagar</td></tr>
<tr><td>Drivrutiner/inbyggd programvara</td><td colspan="4">Följer schemat för kvalitetsuppdateringar</td></tr>
<tr><td>Definition av virusskydd</td><td colspan="4">Uppdaterad med varje genomsökning</td></tr>
<tr><td>Microsoft 365-applikationer för företag</td><td colspan="4">Följer Office månadskanal
</table>

Mer information om månadskanalen för Microsoft 365 Apps för företag finns i [Översikt över uppdateringskanaler för Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/overview-update-channels).

>[!NOTE]
>Dessa uppskovsperioder är avsiktligt utformade för att säkerställa höga säkerhets- och prestandastandarder för alla användare. Dessutom, baserat på data som samlats in på alla Microsoft Managed Desktop-enheter och den varierande omfattningen och effekten av uppdateringar, förbehåller sig Microsoft Managed Desktop flexibilitet att ändra längden på ovanstående uppskovsperioder för alla distributionsgrupper på ad hoc-basis.
>
>Microsoft Managed Desktop gör en oberoende bedömning av varje Windows-funktionsutgåva för att utvärdera dess nödvändighet och användbarhet för sina hanterade klienter. Microsoft Managed Desktop kanske eller kanske inte distribuerar alla Windows-funktionsuppdateringar. 

## <a name="windows-insider-program"></a>Windows Insider-program

Microsoft Managed Desktop stöder inte enheter som ingår i Windows Insider-programmet. Windows Insider-programmet används för att validera förversion av Windows-programvara och är avsett för enheter som inte är verksamhetskritiska. Detta är ett viktigt Microsoft-initiativ, men det är inte avsett för bred distribution i produktionsmiljöer. 

Alla enheter som hittas med Windows Insider-versioner kan placeras i testgruppen och undantas från uppdateringsservicenivåavtal och slutanvändarsupport från Microsoft Managed Desktop.

## <a name="bandwidth-management"></a>Bandbreddshantering

Vi använder [leveransoptimering](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) för alla operativsystem och drivrutinsuppdateringar. Detta minimerar nedladdningsstorleken från Windows Update-tjänsten genom att söka efter uppdateringar från peer-datorer i företagsnätverket.


