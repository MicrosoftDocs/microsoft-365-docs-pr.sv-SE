---
title: Microsoft 365-klient isolering i Microsoft Graph och Delve
ms.author: josephd
author: JoeDavies-MSFT
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
description: I den här artikeln finns en förklaring av hur Microsoft 365-klient isolering fungerar i Office Graph och i Delve.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ab9b216656e076cc3ba02a4ef6c75b25b94547fe
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694651"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Microsoft 365-klient isolering i Microsoft Graph och Delve

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Klient isolering i Microsoft Graph

[Microsoft Graph](https://developer.microsoft.com/graph) -aktiviteterna i Microsoft 365-tjänster, till exempel Exchange Online, SharePoint Online, Yammer, Skype för företag, Azure Active Directory och mycket mer och i externa tjänster, till exempel andra Microsoft-tjänster eller tredje parts tjänster. Microsoft Graph-komponenter används i Microsoft 365. Microsoft Graph representerar en samling innehåll och aktiviteter och relationerna mellan dem som sker i hela Office-sviten. Den använder avancerade maskin inlärnings tekniker för att koppla personer till relevant innehåll, konversationer och personer runt dem. Klient organisations indexet i SharePoint Online har till exempel ett Microsoft Graph-index som används för att hantera Delve-frågor, analys bearbetnings motorn i SharePoint Online används för att lagra signaler och beräkna insikter, och Exchange Online beräknar varje användares mottagar cache som indata till klient analys.

Microsoft Graph innehåller information om företags objekt, till exempel personer och dokument, samt relationer och samverkan mellan dessa objekt. Relationerna och interaktionerna representeras som *kanter*. Microsoft Graph är segmenterat av en klient organisation, så att beställningar endast kan finnas mellan *noder* i samma innehav. En *nod* är en enhet med en URI (Uniform Resource Identifier), nodtyp, åtkomst kontrol lista och en uppsättning ansikte som innehåller *metadata* och kanter. Varje nod har tillhör ande metadata och kanter, ordnade i *Faces* som i den gemensamma kunskaps modellen. *Metadata* är namngivna egenskaper som lagras på en nod som kan användas för sökning, filtrering och analys i Microsoft Graph. En *aspekt* är en logisk uppsättning metadata och kanter på en nod. Varje aspekt beskriver en aspekt av en nod. 

I Microsoft Graph hämtas inte alla data till en enda databas; i stället lagras metadata och relationer om data som finns någon annan stans. Microsoft Graph består av flera data lager och bearbetnings komponenter:

- Klient organisations butiken tillhandahåller Mass lagring optimerad för effektiv analys.
- Cacheminnet för aktiva innehåll ger snabb åtkomst till aktiva noder och kanter för att driva användar upplevelsen.
- Indatabufferten meddelar komponenter internt och externt av ändringar i klient organisations diagrammet.

Analys inom varje arbets börda som härleder insikter om de olika distributionerna och skickar dem till klient organisations diagrammet. Klient organisations analyser för alla aktiviteter i ett innehav för att framställa insikter i beteende mönster. Till exempel beräknar Exchange Online automatiskt mottagar-cacheminnet för varje användare med analys som är effektivt via varje användares post låda. Dessa per användare tillverkar en uppsättning *RecipientCache kanter* på varje person, som i sin tur skickas till klient organisations diagrammet. Det här håller hela analys bearbetningen så nära källdata som möjligt.

## <a name="tenant-isolation-in-delve"></a>Klient isolering i Delve

Som tidigare nämnts har Microsoft graphs användar funktioner som hjälper folk att upptäcka och samar beta på befintliga aktiviteter i sin företags organisation och tillhandahåller en Entity-inriktad plattform för analys till anledning av innehåll och aktivitet på olika arbets belastningar och bortom Microsoft 365. Delve är den första upplevelsen av Microsoft Graph.
Delve är en Microsoft 365 webb upplevelse som hämtar innehåll från Microsoft 365 och Yammer Enterprise till Microsoft 365-användare via Microsoft Graph. Webb upplevelsen visar data som olika anslags tavlor, var och en med ett visst ämne, till exempel att *trender kring mig* eller *ändrat av mig*. Varje bräde består av flera dokument kort som visar sammanfattnings text och en bild från dokumentet. Kortet gör det möjligt för användare att öppna dokumentet eller en Yammer-sida för dokumentet. Det finns en sida för varje person i en Microsoft 365-klient organisation som visar de mest relevanta dokumenten för den personen och ikoner som kan starta Exchange Online eller Skype för företag för att interagera med den personen. Eftersom Delve baseras på Microsoft Graph API är det bundet av den klientbaserade isoleringen av detta API.