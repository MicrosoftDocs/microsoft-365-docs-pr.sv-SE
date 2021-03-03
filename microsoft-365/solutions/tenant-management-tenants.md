---
title: Steg 1. Dina klientorganisationar i Microsoft 365 för företag
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
description: Distribuera och hantera en eller flera Microsoft 365-klientorganisationar, med alternativ för multigeobaserade och rörliga platser.
ms.openlocfilehash: 4d9bd685fce6fb2f11b8e17bebae6460e0c10bd2
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406390"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a>Steg 1. Dina klientorganisationar i Microsoft 365 för företag

Ett av dina första klientbeslut är hur många som ska ha. Varje Microsoft 365-innehavare är distinkt, unik och separat från alla andra Microsoft 365-klientorganisationar. Det är motsvarande Azure AD-klientorganisation som också är distinkt, unik och separat från alla andra Microsoft 365-klientorganisationar.

## <a name="single-tenant"></a>Enskild klient
Om du har en enda klientorganisation förenklas många aspekter av organisationens användning av Microsoft 365. En enda klient innebär en enda Azure AD-klientorganisation med en enda uppsättning konton, grupper och principer. Behörigheter och delning av resurser i organisationen kan göras via den centrala identitetsleverantören.

En enda klientorganisation erbjuder mest funktionsrika och förenklade samarbets- och produktivitetsupplevelser för användarna.

Här är ett exempel som visar standardplatsen och Azure AD-klientorganisationen för en Microsoft 365-klientorganisation.

![En enskild Microsoft 365-klientorganisation med Azure AD-klientorganisationen](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a>Flera klientorganisationer

Det finns många anledningar till varför organisationen kan ha flera klientorganisationar:

- Administrativ avgränsning
- Decentraliserad IT
- Historiska beslut
- Sammanslagningar, förvärv eller divestitures
- Tydlig avgränsning av varumärken för organisationer med grattis till ett företag
- Klientorganisation för förhands produktions-, test- eller sandbox-miljö

Här är ett exempel på en organisation som har två klientorganisationar (klientorganisation A och klientorganisation B) i samma standarddatacenter. Varje klientorganisation som en separat Azure AD-klientorganisation.

![Flera Microsoft 365-klientorganisationar med sina egna Azure AD-klientorganisationar](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

När du har flera klientorganisationar finns det begränsningar och ytterligare överväganden när du hanterar dem och tillhandahåller tjänster till användarna.

### <a name="inter-tenant-collaboration"></a>Samarbete mellan klientorganisationer

Om du vill att användarna ska samarbeta mer effektivt i olika Microsoft 365-klientprogram på ett säkert sätt kan du använda samarbetsalternativen mellan klientorganisationen genom att använda en central plats för filer och konversationer, dela kalendrar, använda snabbmeddelanden, ljud-/videosamtal för kommunikation och säkerställa åtkomst till resurser och program.

Mer information finns i Samarbete mellan klientorganisationen i [Microsoft 365.](../enterprise/microsoft-365-inter-tenant-collaboration.md)

### <a name="cross-tenant-mailbox-migration-preview"></a>Migrering av postlådor mellan klientorganisationen (förhandsversion)

Innan du migrerar flera klientlådor (i förhandsversionen) måste du när du flyttar Exchange Online-postlådor mellan klientorganisationen helt ta bort en användarpostlåda från den aktuella klientorganisationen (källklientorganisationen) till den lokala och sedan registrera dem för en ny klientorganisation (målklientorganisationen). Med den nya funktionen för postlådemigrering mellan klientorganisationen kan innehavaradministratörer i både käll- och målklientorganisationen flytta postlådor mellan klientorganisationen med minimalt beroende av infrastrukturen i sina lokala system. Det här tar bort behovet av postlådor för off-board och onboard.

Här är två exempel på klientorganisationsklienter och deras postlådor före postlådemigrering mellan klientorganisationen.

![Flera Microsoft 365-klientorganisationar och deras postlådor](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

I den här bilden har två separata klientorganisationsdomäner och en uppsättning Exchange-postlådor.

Här är målklientorganisationen (klientorganisation A) efter postlådemigrering mellan klientorganisationen.

![Målklientorganisationen efter postlådemigrering mellan klientorganisationen](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

I den här bilden har en enda klientorganisation både domäner och båda uppsättningar av Exchange-postlådor.

Mer information finns i migrering av [postlådor mellan klientorganisationen.](../enterprise/cross-tenant-mailbox-migration.md)

### <a name="tenant-to-tenant-migrations"></a>Migrering mellan klientorganisationer

Det finns flera arkitekturer för sammanslagningar, förvärv, divestitures och andra scenarier som kan leda till att du migrerar en befintlig Microsoft 365-klientorganisation till en ny klientorganisation. 

Detaljerad information finns i [Microsoft 365-migreringar från klientorganisation till klientorganisation.](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)

## <a name="multi-geo-for-a-tenant"></a>Multi-Geo för en klientorganisation

Med Microsoft 365 Multi-Geo kan du tillhandahålla och lagra data i vila på andra datacenters geoplatser som du har valt att uppfylla datalagringskraven och samtidigt låsa upp din globala distribution av moderna produktivitetsupplevelser till dina medarbetare.

I en Multi-Geo-miljö består Microsoft 365-innehavaren av en standard- eller central plats där Microsoft 365-prenumerationen ursprungligen skapades och en eller flera satellitplatser. I en flera geoklientorganisation hanteras information om geoplatser, grupper och användarinformation i en global Azure AD-klientorganisation. Eftersom information om klientorganisationen är centraliserad och synkroniserad till varje geoplats delas samarbetsupplevelser för alla från ditt företag mellan platserna.

Här är ett exempel på en organisation som har sin standardplats i Europa och en satellitplats i Nordamerika. Båda platserna har samma globala Azure AD-klientorganisation för den enda Microsoft 365-klientorganisationen.

![Exempel på en Microsoft 365-klientorganisation med flera geoklienter](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

Mer information finns i [Microsoft 365 Multi-Geo.](../enterprise/microsoft-365-multi-geo.md)

## <a name="moving-core-data-to-a-new-datacenter-geo"></a>Flytta basdata till ett nytt datacenter geo

Microsoft fortsätter att öppna nya datacenter geos för Microsoft 365-tjänster. Dessa nya datacenter geos lägger till kapacitet och beräknar resurser för att stödja vår pågående kundbehov och användnings tillväxt. Det nya datacentrets geodata erbjuder dessutom geodata som lagras för basdata från kunder.

Även om geoinvigning av ett nytt datacenter inte påverkar dig och dina basdata som lagras i ett befintligt datacenter geo gör Microsoft att du kan begära en tidig migrering av organisationens baskunddata i vila till ett nytt datacenter geo.

Här är ett exempel där en Microsoft 365-klientorganisation har flyttats från eu:s datacenter (EU) geo till det som finns i Storbritannien.

![Exempel på flytt av Microsoft 365-klientorganisation mellan geodatadata](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

Mer information finns i Flytta [basdata till nya geodata i Microsoft 365-datacentret.](../enterprise/moving-data-to-new-datacenter-geos.md)

## <a name="products-and-licenses-for-a-tenant"></a>Produkter och licenser för en klientorganisation

Din Microsoft 365-klientorganisation skapas när du köper din första produkt, till exempel Microsoft 365 E3. Tillsammans med produkten ingår licenser som debiteras en månatlig avgift eller årsavgift. En administratör tilldelar sedan en tillgänglig licens från en av dina produkter till ett användarkonto, antingen direkt eller via gruppmedlemskap. Beroende på organisationens affärsbehov kanske du har en uppsättning produkter, som var och en har en egen licenspool. 

För att fastställa produktuppsättningen och antalet licenser för var och en krävs en del planering för att:

- Se till att du har tillräckligt med licenser för användarkonton som behöver avancerade funktioner.
- Förhindra att licenser tar slut eller att du har för många licenser som inte tilldelats, baserat på ändringar av personalen i din organisation.


## <a name="results-of-step-1"></a>Resultat i steg 1

För dina Klientorganisationar i Microsoft 365 för företag har du fastställt:

- Hur många klientorganisationar du har eller behöver.
- Vilka produkter och licenser som måste köpas för varje klientorganisation.
- Om en klientorganisation måste vara multi-geo för att uppfylla kraven för datalagring.
- Om du behöver konfigurera samarbete mellan klientorganisationen.
- Om du behöver migrera en klientorganisation till en annan.
- Oavsett om du behöver flytta basdata från ett datacenter geo till ett nytt.

Här är ett exempel på en ny klientorganisation.

![Exempel på en ny klientorganisation](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

I den här bilden har klientorganisationen:

- En standardplats som motsvarar ett geodatacenter i Microsoft 365.
- En uppsättning produkter och licenser.
- Uppsättningen appar för molntjänster, varav en del är specifika för produkter.
- En Azure AD-klient som innehåller globala administratörskonton och ett initialt DNS-domännamn.

När vi går igenom de ytterligare stegen i den här lösningen kommer vi att bygga ut den här siffran.

## <a name="ongoing-maintenance-for-tenants"></a>Löpande underhåll för klientorganisationen

Du kan kontinuerligt behöva:

- Lägg till en ny klientorganisation.
- Lägg till nya produkter i en klientorganisation med ett första antal licenser.
- Ändra licensuppsättningen för en produkt i en klientorganisation för att justera för att ändra personalkrav.
- Flytta dina kärndata från en klientorganisation till en ny geoplats i datacentret.
- Lägg till Krav för Multi-Geo för datalagring.
- Konfigurera samarbete mellan klientorganisationen.

## <a name="next-step"></a>Nästa steg

[![Steg 2. Optimera klientorganisationen för nätverk för åtkomst](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)

Fortsätt med [nätverk](tenant-management-networking.md) för att tillhandahålla optimala nätverk från dina medarbetare till Microsoft 365-molntjänster.
