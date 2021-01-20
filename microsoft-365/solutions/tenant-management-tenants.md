---
title: Steg 1. Din Microsoft 365 för företags innehavare
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
ms.custom:
- Ent_Solutions
description: Distribuera och hantera en eller flera Microsoft 365-klient organisationer med alternativ för multi-Geo och flytt av platser.
ms.openlocfilehash: 567a2cb46e715ec560bf973a33ab83cfa63d403b
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908721"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a>Steg 1. Din Microsoft 365 för företags innehavare

Ett av dina första besluts fattare är hur många som ska vara med. Varje Microsoft 365-klient organisation är distinkt, unikt och åtskilt från alla andra Microsoft 365-klient organisationer. Det motsvarande Azure AD-klient organisationen är också distinkt, unikt och åtskilt från alla andra Microsoft 365-klient organisationer.

## <a name="single-tenant"></a>En enda klient organisation
Om du har en enda klient organisation blir det enklare för många olika sätt att använda Microsoft 365. En enskild klient organisation betyder en enda Azure AD-klient organisation med en enda uppsättning konton, grupper och principer. Behörigheter och delning av resurser i organisationen kan göras via den här centrala identitets leverantören.

En enda klient organisation tillhandahåller den mest omfattande och förenklade samarbets-och produktivitets upplevelsen för dina användare.

Här är ett exempel som visar standard platsen och Azure AD-klient organisationen för en Microsoft 365-klient organisation.

![En enda Microsoft 365-klient organisation med sin Azure AD-klient organisation](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a>Flera klientorganisationer

Det finns många anledningar till att organisationen kan ha flera klient organisationer:

- Administratörs isolering
- Decentralisera det
- Historiska beslut
- Fusioner, förvärv eller divestitures
- Tydligt separering av varumärkes märkning för konglomerat organisationer
- För produktions-, test-eller sand lådor

Här är ett exempel på en organisation med två klient organisationer (klient organisation A och Tenant B) i samma standard Data Center. Varje klient organisation som en separat Azure AD-klient.

![Flera Microsoft 365-klient organisationer med deras egna Azure AD-klient organisationer](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

När du har flera klient organisationer finns det restriktioner och andra överväganden när du hanterar dem och tillhandahåller tjänster till användarna.

### <a name="inter-tenant-collaboration"></a>Samarbete mellan klientorganisationer

Om du vill att användarna ska samar beta mer effektivt över olika Microsoft 365-klient organisationer på ett säkert sätt kan du använda en central plats för filer och konversationer, dela kalendrar med snabb meddelanden, ljud/video samtal och skydda åtkomsten till resurser och program.

Mer information finns i [Microsoft 365 samarbete mellan innehavare](../enterprise/microsoft-365-inter-tenant-collaboration.md).

### <a name="cross-tenant-mailbox-migration-preview"></a>Migrera mellan innehavare (för hands version)

Innan migrering av post låda från flera innehavare (i för hands version), när Exchange Online-postlådor flyttas mellan klient organisationer måste du helt ta bort en användar post låda från den aktuella klient organisationen (käll klient organisationen) till lokalt och sedan till en ny klient organisation (mål klient organisationen). Med den nya Överflyttnings funktionen för post lådor för flera innehavare kan klient organisationer i både käll-och mål klient organisationer flytta post lådor mellan klient organisationerna och deras lokala system. Detta tar bort behovet av andra och andra-postlådor.

Här är två exempel klient organisationer och deras post lådor innan migrering mellan innehavare av post lådor.

![Flera Microsoft 365-klient organisationer och deras post lådor](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

I den här bilden har två separata klient organisationer sina egna domäner och en uppsättning Exchange-postlådor.

Här är mål klient organisationen (klient organisation A) efter migrering av post låda mellan innehavare.

![Mål klient organisationen efter migrering av post låda mellan innehavare](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

I den här bilden har en enskild klient organisation både domäner och båda uppsättningarna med Exchange-postlådor.

Mer information finns i [migrering av post lådor mellan innehavare](../enterprise/cross-tenant-mailbox-migration.md).

### <a name="tenant-to-tenant-migrations"></a>Migrering mellan klientorganisationer

Det finns flera arkitektur metoder för fusioner, förvärv, divestitures och andra scenarier som kan leda till att du migrerar en befintlig Microsoft 365-klient organisation till en ny klient organisation. 

Detaljerad information finns i [Microsoft 365-migreringar för klient organisationer](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).

## <a name="multi-geo-for-a-tenant"></a>Multi-geo för en innehavare

Med Microsoft 365 multi-geo kan du tillhandahålla och lagra data på andra platser i Data Center som du har valt att uppfylla data de kraven och samtidigt låsa upp din globala installation av moderna produktivitets upplevelser till dina anställda.

I en multi-geo-miljö består din Microsoft 365-klient av en standard-eller central plats där ditt Microsoft 365-abonnemang ursprungligen skapades och en eller flera satellit platser. I en multi-geo-klient organisation ska informationen om geo-platser, grupper och användar information hanteras i en global Azure AD-klient. Eftersom klient informationen hanteras centralt och synkroniseras på varje Geo-plats delas samarbets upplevelser med alla från ditt företag på alla platser.

Här är ett exempel på en organisation med standard platsen i Europa och en satellit plats i Nord Amerika. Båda platserna delar samma globala Azure AD-klient organisation för den enda Microsoft 365-klienten.

![Exempel på en multigeo Microsoft 365-klient organisation](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

Mer information finns i [Microsoft 365 multi-geo](../enterprise/microsoft-365-multi-geo.md).

## <a name="moving-core-data-to-a-new-datacenter-geo"></a>Flytta grundläggande data till ett nytt Data Center geo

Microsoft fortsätter att öppna nya data Center-geos för Microsoft 365-tjänster. De här nya datacenter-geos lägga till kapacitet och beräkna resurser för att stödja vår pågående kund efter frågan och förbruknings tillväxt. Dessutom ger det nya data Center geos in-Geo data de för grundläggande kunddata.

Trots att en ny datacenter-geo inte påverkar dig och dina grundläggande data som lagras i ett befintligt Data Center, kan du använda Microsoft för att begära en tidig migrering av organisationens grundläggande kund data på en ny data Center-geo.

Här är ett exempel där en Microsoft 365-klient har flyttats från Europeiska unionen (EU) Data Center till den som befinner sig i Storbritannien (UK).

![Exempel på att flytta en Microsoft 365-klient organisation mellan data Center geos](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

Mer information finns i [Flytta grundläggande data till nya Microsoft 365 Data Center-geos](../enterprise/moving-data-to-new-datacenter-geos.md).

## <a name="products-and-licenses-for-a-tenant"></a>Produkter och licenser för en klient organisation

Din Microsoft 365-klient organisation skapas när du köper din första produkt, till exempel Microsoft 365 E3. Tillsammans med produkten är licenser, som debiteras per månad eller årlig avgift. En administratör tilldelar sedan en tillgänglig licens från en av dina produkter till ett användar konto, antingen direkt eller via grupp medlemskap. Beroende på organisationens affärs behov kan du ha en uppsättning produkter, var och en med sina egna licenser. 

Det krävs lite planering för att fastställa produkterna och antalet licenser för var och en av dem:

- Se till att du har tillräckligt med licenser för de användar konton som behöver avancerade funktioner.
- Förhindra att licenser tar slut eller att du inte har till gång till för många otilldelade licenser, baserat på ändringar i Personalen på din organisation.


## <a name="results-of-step-1"></a>Resultat i steg 1

För din Microsoft 365 för företags klient organisationer har du fastställt:

- Hur många klient organisationer du har eller behöver.
- Vilka produkter och licenser som måste köpas för varje klient organisation.
- Om en innehavare måste vara Multi-geo för att uppfylla data de kraven.
- Om du behöver konfigurera samarbete mellan klienter.
- Om du behöver migrera en klient organisation till en annan.
- Om du behöver flytta grundläggande data från ett Data Center geo till New.

Här är ett exempel på en ny klient organisation.

![Exempel på en ny klient organisation](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

I den här bilden har klient organisationen:

- En standard plats för ett Microsoft 365-datacenter geo.
- En uppsättning produkter och licenser.
- Uppsättningen Cloud Productivity-appar, varav vissa är specifika för produkterna.
- En Azure AD-klient som innehåller globala administratörs konton och ett ursprungligt DNS-domännamn.

När vi går igenom de ytterligare stegen i den här lösningen kommer vi att bygga upp den här uppgiften.

## <a name="ongoing-maintenance-for-tenants"></a>Pågående underhåll för klient organisationer

Kontinuerligt måste du kanske:

- Lägg till en ny klient organisation.
- Lägg till nya produkter till en klient organisation med ett inledande antal licenser.
- Ändra uppsättningen med licenser för en produkt i en klient organisation för att justera personal kraven.
- Flytta dina grundläggande data från en klient organisation till en ny data Center Geo-plats.
- Lägg till villkor för multi-geo för data de.
- Konfigurera samarbete mellan innehavare.

## <a name="next-step"></a>Nästa steg

[![Steg 2. Optimera klient organisationen för nätverk för åtkomst](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)

Fortsätt med [nätverk](tenant-management-networking.md) för att erbjuda optimala nätverksfunktioner från dina arbetare till Microsoft 365-moln tjänster.
