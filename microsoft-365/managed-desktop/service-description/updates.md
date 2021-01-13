---
title: Hur uppdateringar hanteras på Microsoft Managed Desktop
description: Att hålla Microsoft Managed Desktop uppdaterat är en balans mellan hastighet och stabilitet.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 53a21c4126e59861200df405ffe365b2ccef08f8
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840295"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Hur uppdateringar hanteras på Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop ansluter alla enheter till en modern molnbaserade infrastruktur. Att hålla Windows, Office, driv rutiner, fast program vara och Microsoft Store för företag-program uppdaterade är en balans mellan hastighet och stabilitet. Distributions grupper används för att säkerställa att uppdateringar och policyer för operativ systemet distribueras på ett säkert sätt. Mer information finns i avsnittet om att [hantera ändringar och versioner av Microsoft Managed Desktop](https://www.microsoft.com/videoplayer/embed/RE4mWqP).

Uppdateringar som släpps av Microsoft är kumulativa och kategoriseras som kvalitet eller funktions uppdateringar.
Mer information finns i [Windows Update för företag: uppdaterings typer](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types). 

## <a name="update-groups"></a>Uppdatera grupper

Microsoft Managed Desktop använder fyra Azure AD-grupper för att hantera uppdateringar:

- **Test**: används för att validera ändringar i Microsoft hanterade Skriv bords principer, operativ system uppdateringar, funktions uppdateringar och andra ändringar som skickas till innehavaren. Det ska inte finnas några användare i test gruppen. Test gruppen är undantagen från alla etablerade service nivå avtal och användar support. Den här gruppen kan användas för att verifiera kompatibiliteten för program med nya princip-eller operativ Systems ändringar.  
- **Först**: innehåller tidiga program vara och enheter som kan vara föremål för för hands uppdateringar. Enheter i den här gruppen kan uppleva avbrott om det finns scenarier som inte täcktes under testningen i test ringen.
- **Snabb**: prioriterar fortare. Användbart för att upptäcka kvalitets problem innan de erbjuds till den breda gruppen. Den här gruppen fungerar som ett Next-verifiering, men är ofta mer stabil än test och första grupp. 
- **Brett**: senaste gruppen för att få funktioner och kvalitets uppdateringar tillgängliga. Den här gruppen innehåller de flesta användare i klient organisationen och förökade stabilitet i distributionen. Test av program bör göras här eftersom miljön är stabilare. 

> [!NOTE]
> Om du behöver flytta en användare till en annan uppdaterings grupp ska du skicka en supportbegäran. Se [Support för Microsoft Managed Desktop](support.md) om du vill ha mer information om att skicka support förfrågningar. Om du flyttar en användare själv återställs flytten.

Mer information om roller och ansvars områden med de här distributions grupperna finns i [Microsoft hanterade Skriv bords roller och ansvar](../intro/roles-and-responsibilities.md)

Så här fungerar uppdaterings distribution:
- Microsoft Managed Desktop distribuerar en ny funktion eller kvalitets uppdatering enligt det schema som anges i tabellen.
- Under distributionen är Microsoft Managed Desktop Monitors för tecken på misslyckanden eller avbrott (baserat på diagnostikdata och användar support systemet). Om det finns en sådan hittas distributionen till alla aktuella och framtida grupper omedelbart.
    - Exempel: om ett problem upptäcks när du distribuerar en kvalitets uppdatering till den första gruppen pausas alla distributioner till första, snabba och breda tills problemet löses.
    - Kompatibilitetsproblem kan rapporteras genom att en biljett skickas till Microsoft Managed Desktop admin-portalen.
- Uppdateringar av funktioner och kvalitet pausas oberoende av varandra. Paus gäller för 35 dagar som standard, men kan minskas eller utökas beroende på om problemet är åtgärdat.
- När grupperna har pausats fortsätter distributionen enligt schemat i tabellen.
- Den här distributions processen gäller både funktions-och kvalitets uppdateringar, även om tids linjen varierar beroende på var och en av dem.




<table>
    <tr><th colspan="5">Inställningar för uppdaterings distribution</th></tr>
    <tr><th>Uppdaterings typ</th><th>Tävlingar</th><th>Skapas</th><th>Snabbspola</th><th>Personer</th></tr>
    <tr><td>Kvalitets uppdateringar för operativ systemet</td><td>0 dagar</td><td>0 dagar</td><td>0 dagar</td><td>3 dagar</td></tr>
    <tr><td>Funktions uppdateringar för operativ system</td><td>0 dagar</td><td>30 dagar</td><td>60 dagar</td><td>90 dagar</td></tr>
    <tr><td>Driv rutiner/inbyggd program vara</td><td colspan="4">Följer schemat för kvalitets uppdateringar</td></tr>
    <tr><td>Antivirus definition</td><td colspan="4">Uppdaterat med varje genomsökning</td></tr>
    <tr><td> Microsoft 365 Apps för företag</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">Läs mer</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">Läs mer</a></td></tr>
</table>

>[!NOTE]
>Dessa avstängnings perioder är avsiktligt utformade för att säkerställa hög säkerhet och prestanda för alla användare. Baserat på data som samlats in på alla Microsoft-hanterade Skriv bords enheter och omfattningen av olika uppdateringar, förbehåller sig Microsoft Managed Station ära datorer flexibilitet att ändra längden på de ovanstående avstängnings perioderna för alla och alla distributions grupper på ett ad hoc-basis.
>
>Microsoft Managed Desktop sköter en oberoende utvärdering av varje version av Windows-funktioner för att utvärdera deras nödvändighet och användbarhet på sina hanterade klient organisationer. Därför kan Microsoft Managed Desktop eller kanske inte distribuera alla uppdateringar av Windows-funktioner. 

## <a name="windows-insider-program"></a>Windows Insider program

Microsoft Managed Desktop stöder inte enheter som ingår i Windows Insider-programmet. Windows Insider-programmet används för att validera för hands versionen av Windows-programvaran och är avsedd för enheter som inte är verksamhets kritiska. Även om det är ett viktigt Microsoft-initiativ är den inte avsedd för allmän distribution i produktions miljöer. 

Alla enheter som hittas med Windows Insider-versioner kan ingå i test gruppen och undantas från uppdatering av service nivå avtal och användar stöd från Microsoft Managed Desktop.

## <a name="bandwidth-management"></a>Bandbredds hantering

Vi använder [leverans optimering](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) för alla operativ system och driv rutiner. Den här funktionen minimerar nedladdnings storleken från Windows Update-tjänsten genom att söka efter uppdateringar från peers i företags nätverket.


