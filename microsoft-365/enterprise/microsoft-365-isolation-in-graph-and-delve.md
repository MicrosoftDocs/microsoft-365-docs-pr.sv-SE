---
title: Microsoft 365 Klientisolering i Microsoft-Graph och Delve
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: I den här artikeln finns en förklaring av hur Microsoft 365 av innehavarisolering fungerar i Office Graph och i Delve.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 966f02726a2cce18e30e4d5bc7ab0beb5db51a29
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332394"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Microsoft 365 Klientisolering i Microsoft-Graph och Delve

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Klientisolering i Microsoft Graph

[Microsoft](https://developer.microsoft.com/graph) Graph-modellers aktiviteter i Microsoft 365-tjänster, inklusive Exchange Online, SharePoint Online, Yammer, Skype för företag, Azure Active Directory och annat, och i externa tjänster, till exempel andra Microsoft-tjänster- eller tredjepartstjänster. Microsoft Graph komponenter används i Microsoft 365. Microsoft Graph en samling innehåll och aktiviteter, och relationerna mellan dem som inträffar i hela Office programpaketet. Den använder avancerade maskininlärningstekniker för att koppla samman människor till relevant innehåll, konversationer och människor i deras miljö. Till exempel har klientindexet i SharePoint Online ett Microsoft Graph-index som används för att hantera Delve-frågor. Analysbearbetningsmotorn i SharePoint Online används för att lagra signaler och beräkna insikter, och Exchange Online beräknar varje användares mottagarcache som indata i analys av klientorganisationen.

Microsoft Graph information om företagsobjekt, till exempel personer och dokument, samt relationer och interaktioner mellan dessa objekt. Relationerna och interaktionen representeras som *kanter.* Microsoft Graph är segmenterat efter klientorganisation så att kanter bara kan finnas *mellan* noder i samma innehav. En *nod* är en enhet med en URI (Uniform Resource Identifier), nodtyp, åtkomstkontrolllista och en uppsättning fasetter som innehåller *metadata* och kanter. Varje nod har associerade metadata och kanter, ordnade *i fasetter* som i Common Knowledge Model. *Metadata* är namngivna egenskaper som lagras på en nod som kan användas för sökning, filtrering eller analys inom Microsoft Graph. En *fasett* är en logisk samling metadata och kanter på en nod. Varje fasett beskriver en aspekt av en nod. 

Microsoft Graph tar inte med alla data till en enda lagringsplats. Istället lagras metadata och relationer om data som finns någon annanstans. Microsoft-Graph består av flera datakällor och komponenter som bearbetas:

- Klientorganisationen Graph-butiken ger masslagring optimerad för effektiv analys.
- Active Content Cache ger snabb åtkomst till aktiva noden och kanter för att ge användaren en upplevelse.
- Indataroutern meddelar komponenter internt och externt om ändringar i klientorganisationens diagram.

Analyser inom varje arbetslast kan härleda insikter som är relevanta för beräkningar för hela klientorganisationen och skicka dem till klientorganisationens diagram. Klientorganisationens analysorsaker till all aktivitet i ett innehav för att ge insikter i funktionsmönster. Till exempel Exchange Online beräknas mottagarcachen för varje användare med analyser som effektivt beror på varje användares postlåda. Dessa analyser per användare ger en uppsättning *RecipientCache Edges* på varje person som i sin tur push-trycks till diagrammet för klientorganisationen. Det här håller så mycket av analysbearbetningen som möjligt nära källdata.

## <a name="tenant-isolation-in-delve"></a>Tenant Isolation i Delve

Som vi nämnt tidigare är Microsoft Graph en överkraft för upplevelser som hjälper människor att upptäcka och samarbeta kring aktuella aktiviteter i företaget, och som tillhandahåller en enhetscentrerad plattform för analys av innehåll och aktivitet i arbetsbelastningar och vidare Microsoft 365. Delve är den första sådana upplevelse som drivs av Microsoft Graph.
Delve är en Microsoft 365 webbupplevelse som visar innehåll från Microsoft 365 och Yammer Enterprise till Microsoft 365 användare via Microsoft Graph. I webbgränssnittet visas data som olika anslagstavlor, var och en med ett visst ämne, till exempel Trender *runt mig* eller *Ändrad av mig.* Varje tavla består av flera dokumentkort som visar sammanfattningstext och en bild från dokumentet. Med kortet kan användare göra saker som att öppna dokumentet Yammer en sida för dokumentet. Det finns en sida för varje person i en Microsoft 365-klientorganisation som visar de mest relevanta dokumenten för den här personen, och ikoner som kan anropa Exchange Online eller Skype för företag för att interagera med den personen. Eftersom Delve är baserat på Microsofts Graph API är det bundet av den klientbaserade avgränsningen av det API:t.