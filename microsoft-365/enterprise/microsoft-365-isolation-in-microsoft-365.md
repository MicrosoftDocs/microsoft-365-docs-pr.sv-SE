---
title: Isolering och åtkomst kontroll i Microsoft 365
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
- SPO_Content
f1.keywords:
- NOCSH
description: 'Sammanfattning: en förklaring om isolering och åtkomst kontroll i de olika programmen i Microsoft 365.'
ms.openlocfilehash: 40a1f1d93fe34333366e456cc006ab2d1c700a83
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694648"
---
# <a name="isolation-and-access-control-in-microsoft-365"></a>Isolering och åtkomst kontroll i Microsoft 365

Azure Active Directory (Azure AD) och Microsoft 365 använder en mycket komplicerad data modell som innehåller många olika tjänster, hundratals enheter, tusentals relationer och många tusen attribut. På en hög nivå, Azure AD och tjänste katalogerna är behållarna för klient organisationer och mottagare synkroniserade med tillståndbaserade replikeringspartners. Utöver katalog informationen som lagras i Azure AD har alla tjänste arbets belastningarna sin egen infrastruktur för katalog tjänster.
 
![Microsoft 365 klient organisations data](../media/office-365-isolation-tenant-data-sync.png)

I den här modellen finns det ingen källa med katalog data. Särskilda system äger enskilda data, men inget enskilt system innehåller alla data. Microsoft 365 Services samarbetar med Azure AD i den här data modellen. Azure AD är "system för faktum" för delade data, som vanligt vis är små och statiska data som används av varje tjänst. Den federerade modellen som används i Microsoft 365 och Azure AD tillhandahåller den delade vyn av data.

Microsoft 365 använder både fysisk lagring och Azure Cloud Storage. Exchange Online (inklusive Exchange Online Protection) och Skype för företag använder sin egen lagring för kunddata. I SharePoint Online används både SQL Server Storage och Azure Storage, och därför behövs det ytterligare isolering av kunddata på lagrings nivån.

## <a name="exchange-online"></a>Exchange Online

I Exchange Online sparas kund data i post lådor. Post lådor finns i ESE-databaser (Extensible Storage Engine) som kallas post lådor. Detta inkluderar användar post lådor, länkade post lådor, delade post lådor och post lådor i offentliga mappar. Användar post lådor inkluderar sparat Skype för företag-innehåll, till exempel konversations historik.

Innehållet i användar post lådan inkluderar:

- E-postmeddelanden och bifogade filer
- Kalender-och ledig/upptagen-information
- Kontakter
- Uppgifter
- Kommentarer
- Grupper
- Data för härledning

Varje Mailbox-databas i Exchange Online innehåller post lådor från flera klient organisationer. En auktoriseringskod säkrar varje post låda, inklusive ett innehav. Som standard har bara den tilldelade användaren åtkomst till en post låda. Åtkomst kontrol listan (ACL) som skyddar en post låda innehåller en identitet som autentiserats av Azure AD på klient organisations nivå. Post lådorna för varje klient organisation begränsas till identiteter som autentiseras mot klient organisationens autentiseringsprovider, vilket endast inkluderar användare från denna klient organisation. Innehåll i klient organisationen A kan inte på något sätt erhållas av användare i klient organisationen B, såvida inte uttryckligen godkänd av klient organisationen A.

## <a name="skype-for-business"></a>Skype för företag

Skype för företag lagrar data på olika platser:

- Användar-och konto information, som inkluderar anslutnings slut punkter, klient-ID, uppringnings inställningar, närvaro status, kontakt listor, etc., lagras i Skype för företag Active Directory-servrar och i olika Skype för företag-databas servrar. Kontakt listor lagras i användarens Exchange Online-postlåda om användaren är aktive rad för både produkter eller Skype för företag-servrar om användaren inte gör det. Servrar för Skype för företag-databaser är inte partitionerade per klient organisation, men flera organisationers isolerade data upprätthålls via en rollbaserad åtkomst kontroll (RBAC).
- Mötes innehåll och uppladdade data lagras i DFS-resurser (Distributed File System). Det här innehållet kan även arkiveras i Exchange Online om det är aktiverat. DFS-resurserna är inte partitionerade per klient organisation. Innehållet skyddas med ACL: er och flera organisationer är tvingande via RBAC.
- Samtals detalj poster, som är aktivitets historik, till exempel samtals historik, IM-session, program delning, snabb meddelande historik, etc., kan även lagras i Exchange Online, men de flesta samtals detalj posterna lagras tillfälligt på post (CDR)-servrar. Innehållet har inte partitionerats per klient organisation, men flera organisationer används via RBAC.

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online innehåller flera oberoende mekanismer som ger data isolering. Den lagrar objekt som en uppen uppkopplings kod i program databaser. När en användare till exempel laddar upp en fil till SharePoint Online assembleras den, översätts till program kod och lagras i flera tabeller i flera databaser.

Om en användare kan få direkt åtkomst till lagrings utrymmet som innehåller data går det inte att tolka innehållet till en person eller något annat system än SharePoint Online. Dessa mekanismer inkluderar säkerhets åtkomst kontroll och egenskaper. Alla SharePoint online-resurser skyddas av auktoriseringsprincipen och RBAC-policy, inklusive inom ett innehav. Åtkomst kontrol listan (ACL) som säkrar en resurs innehåller en identitet som autentiseras på klient organisations nivå. SharePoint Online-data för en klient organisation är begränsade till identiteter som autentiseras av autentiseringsprovidern för innehavaren.

Utöver ACL-listor är en egenskap för innehavaradministration som anger autentiseringsprovidern (som är den klient organisationens specifika Azure AD) skriven en gång och kan inte ändras när den väl har angetts. När klient organisations egenskapen för autentiseringsprovider har angetts för en klient organisation kan den inte ändras via API: er som exponeras för en klient organisation.

Ett unikt *SubscriptionId* används för varje klient organisation. Alla kund webbplatser ägs av en klient organisation och tilldelas ett *SubscriptionId* som är unikt för innehavaren. Egenskapen *SubscriptionId* på en webbplats är skriven en gång och är permanent. När en webbplats har tilldelats till en klient organisation kan den inte flyttas till en annan klient organisation. *SubscriptionId* är den som används för att skapa säkerhets omfattningen för autentiseringsprovidern och är knuten till innehavaren.

SharePoint Online använder SQL Server och Azure Storage för lagring av innehåll. Partitionsnyckel för innehålls *arkivet är plats* för SQL. När du kör en SQL-fråga använder SharePoint Online ett under- *ID* som verifierats som en del av ett *SubscriptionId* -kontroll på klient nivå.

I SharePoint Online lagras krypterade fil innehåll i Microsoft Azure-blobs. Varje SharePoint Online-servergrupp har sitt eget Microsoft Azure-konto och alla BLOB-objekt som sparas i Azure är krypterade individuellt med en nycklar som lagras i SQL-innehållet. Krypterings nycklar som skyddas i kod av auktoriseringsarkivet och inte exponeras direkt för slutanvändaren. SharePoint Online har övervakning i real tid för att upptäcka när en HTTP-begäran läser eller skriver data för fler än en innehavare. Identitets-ID: *till subscriptionId* spåras mot *SubscriptionId* för den resurs som används. Begäran om åtkomst till resurser för fler än en klient organisation får aldrig hända av slutanvändare. Tjänst förfrågningar i en miljö med flera innehavare är det enda undantaget. Till exempel hämtar Sök roboten innehålls ändringar för en hel databas samtidigt. Det innebär vanligt vis att få en fråga till fler än en klient organisations webbplatser i en enda tjänst förfrågan som görs av effektivitets skäl.

## <a name="teams"></a>Teams

Dina team data lagras på olika sätt beroende på innehålls typen. 

Ta en titt på [översikten-sessionen i Microsoft Teams-arkitekturen](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) för att få en ingående diskussion.

### <a name="core-teams-customer-data"></a>Grundläggande kund data för team

Om din klient organisation har etablerats i Australien, Kanada, Europeiska unionen, Frankrike, Tyskland, Indien, Japan, Sydafrika, Sydkorea, Schweiz (som innehåller Liechtenstein), Förenade Arabemiraten, Storbritannien eller Sverige, lagrar Microsoft endast följande kunddata på den platsen:

- Teams-och grupp-och kanal samtal, bilder, röst meddelanden och kontakter.
- SharePoint Online-webbinnehåll och filer som lagras på webbplatsen.
- Filer som laddats upp till OneDrive för arbete eller skola.

#### <a name="chat-channel-messages-team-structure"></a>Chatta, kanal meddelanden, team struktur

Alla team i Teams hanteras av en Microsoft 365-grupp och dess SharePoint-webbplats och Exchange-postlåda. Privata chattar (inklusive gruppchattar), meddelanden som skickas som en del av en konversation i en kanal och strukturen på team och kanaler lagras i en chatt-tjänst som körs i Azure. Data lagras också i en dold mapp i användarens och gruppens post lådor för att aktivera informations skydds funktioner.

#### <a name="voicemail-and-contacts"></a>Röst brev låda och kontakter

Röst meddelanden lagras i Exchange. Kontakter lagras i Exchange-baserad moln data lagring. Exchange och det Exchange-baserade moln arkivet tillhandahåller redan data de i alla geos i hela världen. För alla team sparas röst brev låda och kontakter i land för Australien, Kanada, Frankrike, Tyskland, Indien, Japan, Förenade Arabemiraten, Storbritannien, Sydafrika, Sydkorea, Schweiz (inklusive Liechtenstein) och USA. För alla andra länder lagras filer på platsen för USA, Europa och Asien, baserat på klient tillhörighet.

#### <a name="images-and-media"></a>Bilder och media

Media som används i chatt (med undantag för GIPHY GIF-filer som inte lagras men som är en referens länk till den ursprungliga GIPHY-tjänst-URL: en, GIPHY är inte Microsoft-tjänst) lagras i en Azure-baserad medie tjänst som distribueras till samma platser som chatt tjänsten.

#### <a name="files"></a>Hjälpfiler

Filer (inklusive OneNote och wiki) som någon delar av en kanal lagras på teamets SharePoint-webbplats. Filer som delas i en privat chatt eller en chatt under ett möte eller ett samtal laddas upp och lagras i OneDrive för arbets-eller skol kontot för den användare som delar filen. Exchange, SharePoint och OneDrive tillhandahåller redan data de i alla världen geos. För befintliga kunder är alla filer, OneNote-anteckningsböcker, teams-wiki-innehåll och post lådor som är en del av Teams erfarenheten lagrat på den plats som är baserad på klient tillhörigheten. Filer lagras i land för Australien, Kanada, Frankrike, Tyskland, Indien, Japan, Förenade Arabemiraten, Storbritannien, Sydafrika, Sydkorea och Schweiz (som innehåller Liechtenstein). För alla andra länder lagras filer på Stilla havet för USA, Europa och Asien baserat på klient tillhörighet.
