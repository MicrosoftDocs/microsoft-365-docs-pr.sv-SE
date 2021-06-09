---
title: Steg 1. Din Microsoft 365 för företagsklienter
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Distribuera och hantera en eller Microsoft 365 klientorganisation, med alternativ för multi-geo- och flyttningsplatser.
ms.openlocfilehash: 4d9bd685fce6fb2f11b8e17bebae6460e0c10bd2
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406390"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a>Steg 1. Din Microsoft 365 för företagsklienter

Ett av dina första klientbeslut är hur många du har. Varje Microsoft 365 är distinkt, unik och skiljer sig från alla Microsoft 365 klientorganisationen. Den motsvarande Azure AD-klientorganisationen är också distinkt, unik och separat från alla Microsoft 365 klientorganisation.

## <a name="single-tenant"></a>Enskild klient
Om du har en enda klientorganisation förenklas många aspekter av organisationens användning av Microsoft 365. En enskild klient innebär en enda Azure AD-klientorganisation med en enda uppsättning konton, grupper och principer. Behörigheter och delning av resurser i organisationen kan göras via den här centrala identitetsleverantören.

En enskild klientorganisation erbjuder de mest funktionsrika och förenklade samarbets- och produktivitetsupplevelsen för användarna.

Här är ett exempel som visar standardplatsen och Azure AD-klientorganisationen för Microsoft 365 klientorganisation.

![En enskild Microsoft 365 med sin Azure AD-klientorganisation](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a>Flera klientorganisationer

Det finns många anledningar till att organisationen kan ha flera klientorganisationar:

- Administrativ avgränsning
- Decentraliserad IT
- Historiska beslut
- Sammanslagningar, förvärv eller företag
- En tydlig åtskillnad mellan företags profilering för storkongruens
- Klientorganisationen före produktion, test eller sandbox-miljö

Här är ett exempel på en organisation som har två klientorganisationar (klientorganisation A och klientorganisation B) i samma standarddatacenter geo. Varje klientorganisation som en separat Azure AD-klientorganisation.

![Flera Microsoft 365 med sina egna Azure AD-klientorganisationen](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

När du har flera klientorganisationen finns det restriktioner och ytterligare överväganden när du hanterar dem och tillhandahåller tjänster till användarna.

### <a name="inter-tenant-collaboration"></a>Samarbete mellan klientorganisationer

Om du vill att användarna ska samarbeta mer effektivt i olika Microsoft 365-klientorganisationar på ett säkert sätt, kan du använda en central plats för filer och konversationer, dela kalendrar, använda snabbmeddelanden, ljud-/videosamtal för kommunikation och skydda åtkomst till resurser och program.

Mer information finns i Microsoft 365 [samarbete mellan klientorganisationen.](../enterprise/microsoft-365-inter-tenant-collaboration.md)

### <a name="cross-tenant-mailbox-migration-preview"></a>Postlådemigrering mellan klientorganisationen (förhandsversion)

Innan postlådemigrering mellan klientorganisationen (i förhandsversion) måste du ta bort en användarpostlåda helt från den aktuella klientorganisationen (källklientorganisationen) till den lokala och sedan registrera dem i en ny klientorganisation (målklientorganisationen) när du flyttar Exchange Online postlådor mellan klientorganisationen. Med den nya funktionen för postlådemigrering mellan klientorganisationen kan innehavaradministratörer i både käll- och målklientorganisationen flytta postlådor mellan klientorganisationen med minimala infrastrukturberoenden i sina lokala system. Det här tar bort behovet av postlådor för off-board och onboard.

Här är två exempel på klientorganisationar och deras postlådor före postlådemigrering mellan klientorganisationen.

![Flera Microsoft 365 och deras postlådor](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

I den här bilden har två separata klienter sina egna domäner och en uppsättning Exchange postlådor.

Här är målklientorganisationen (klientorganisation A) efter postlådemigrering mellan klientorganisationen.

![Målklientorganisationen efter postlådemigrering mellan klientorganisationen](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

I den här illustrationen har en enda innehavare både domäner och båda uppsättningarna Exchange postlådor.

Mer information finns i Migrering av [postlådor i flera klientorganisationen.](../enterprise/cross-tenant-mailbox-migration.md)

### <a name="tenant-to-tenant-migrations"></a>Migrering mellan klientorganisationer

Det finns flera arkitekturscenarier för samgåenden, förvärv, företag och andra scenarier som kan leda till att du migrerar en befintlig Microsoft 365-klientorganisation till en ny klientorganisation. 

Detaljerade instruktioner finns i [Microsoft 365 migreringar från klientorganisation till klientorganisation.](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)

## <a name="multi-geo-for-a-tenant"></a>Multi-Geo för en klientorganisation

Med Microsoft 365 Multi-Geo kan du tillhandahålla och lagra data i vila på andra datacenters geoplatser som du har valt att uppfylla datalagringskraven och samtidigt låsa upp din globala distribution av moderna produktivitetsupplevelser till dina medarbetare.

I en Multi-Geo-miljö består Microsoft 365-klientorganisationen av en standardplats eller central plats där Microsoft 365-prenumerationen ursprungligen skapades och en eller flera satellitplatser. I en flera geoklientorganisation hanteras information om geografiska platser, grupper och användarinformation i en global Azure AD-klient. Eftersom din klientorganisationsinformation är centraliserad och synkroniserad till varje geoplats delas samarbetsupplevelser för alla från ditt företag över platserna.

Här är ett exempel på en organisation som har sin standardplats i Europa och en satellitplats i Nordamerika. Båda platserna har samma globala Azure AD-klientorganisation för den Microsoft 365 klientorganisationen.

![Exempel på en multi-geo Microsoft 365 klientorganisation](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

Mer information finns i [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).

## <a name="moving-core-data-to-a-new-datacenter-geo"></a>Flytta basdata till ett nytt datacenter geo

Microsoft fortsätter att öppna nya datacenter geos för Microsoft 365 tjänster. Dessa nya datacenter geos lägger till kapacitet och beräknar resurser för att stödja vår pågående kundbehov och användningstillväxt. Det nya datacentret geos erbjuder dessutom geodata som används för basdata.

Även om en geoinvigering av ett nytt datacenter inte påverkar dig och dina basdata som lagras i ett befintligt datacenter geo kan du med Microsoft begära en tidig migrering av organisationens basdata för kunder i vila till ett nytt datacenter geo.

Här är ett exempel där en Microsoft 365-klientorganisation har flyttats från EU-datacentret geo till det som finns i Storbritannien.

![Exempel på flytt av Microsoft 365 klientorganisation mellan geodatadata](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

Mer information finns i Flytta [basdata till det nya Microsoft 365 datacentrets geos.](../enterprise/moving-data-to-new-datacenter-geos.md)

## <a name="products-and-licenses-for-a-tenant"></a>Produkter och licenser för en klientorganisation

Din Microsoft 365 skapas när du köper din första produkt, till exempel Microsoft 365 E3. Tillsammans med produkten ingår licenser som debiteras en månatlig eller årlig avgift. En administratör tilldelar sedan en tillgänglig licens från en av dina produkter till ett användarkonto, antingen direkt eller via gruppmedlemskap. Beroende på organisationens affärsbehov kan du ha en uppsättning produkter, som var och en har sin egen licenspool. 

För att fastställa produktuppsättningen och antalet licenser för var och en krävs en del planering för att:

- Se till att du har tillräckligt med licenser för användarkonton som behöver avancerade funktioner.
- Förhindra att licenser tar slut eller att du har för många licenser som inte tilldelats, baserat på ändringar av personalen i din organisation.


## <a name="results-of-step-1"></a>Resultat i steg 1

För din Microsoft 365 för företagsklienter har du beslutat följande:

- Hur många klientorganisationar du har eller behöver.
- Vilka produkter och licenser som måste köpas för varje klientorganisation.
- Om en klientorganisation måste vara en multi-geoklient för att uppfylla datalagringskraven.
- Om du behöver konfigurera samarbete mellan klientorganisationen.
- Om du behöver migrera en klientorganisation till en annan.
- Om du behöver flytta basdata från ett geodatadatacenter till ett nytt.

Här är ett exempel på en ny klientorganisation.

![Exempel på en ny klientorganisation](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

I den här illustrationen har klientorganisationen:

- En standardplats som motsvarar en geoplats Microsoft 365 datacentret.
- En uppsättning produkter och licenser.
- Uppsättningen molnproduktivitetsprogram, av vilka vissa är specifika för produkter.
- En Azure AD-klient som innehåller globala administratörskonton och ett initialt DNS-domännamn.

När vi går igenom de ytterligare stegen i den här lösningen kommer vi att bygga ut den här siffran.

## <a name="ongoing-maintenance-for-tenants"></a>Löpande underhåll för klientorganisation

Du kan behöva:

- Lägg till en ny klientorganisation.
- Lägg till nya produkter i en klientorganisation med ett första antal licenser.
- Ändra licensuppsättningen för en produkt i en klientorganisation för att justera för att ändra personalkrav.
- Flytta dina kärndata från en klientorganisation till en ny geoplats i datacentret.
- Lägg till Krav för Multi-Geo för datalagring.
- Konfigurera samarbete mellan klientorganisationen.

## <a name="next-step"></a>Nästa steg

[![Steg 2. Optimera klientorganisationen för nätverk för åtkomst](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)

Fortsätt med [nätverk för](tenant-management-networking.md) att tillhandahålla optimala nätverk från dina medarbetare till Microsoft 365 molntjänster.
