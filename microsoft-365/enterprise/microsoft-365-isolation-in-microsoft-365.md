---
title: Isolerings- och åtkomstkontroll i Microsoft 365
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
- SPO_Content
f1.keywords:
- NOCSH
description: 'Sammanfattning: En förklaring av avgränsning och åtkomstkontroll i de olika programmen i Microsoft 365.'
ms.openlocfilehash: 53f60c09b94bdcc2515bcc5ff70dfbcd47f42bb4
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332334"
---
# <a name="isolation-and-access-control-in-microsoft-365"></a>Isolerings- och åtkomstkontroll i Microsoft 365

Azure Active Directory (Azure AD) och Microsoft 365 använder en mycket komplex datamodell som innehåller tiotals tjänster, hundratals enheter, tusentals relationer och tusentals attribut. På en hög nivå är Azure AD och tjänstekatalogerna behållare för klientorganisationen och mottagare som hålls synkroniserade med hjälp av tillståndsbaserade replikeringsprotokoll. Utöver kataloginformationen i Azure AD har var och en av tjänstearbetsbelastningarna en egen infrastruktur för katalogtjänster.
 
![Microsoft 365 datasynkronisering för klientorganisation](../media/office-365-isolation-tenant-data-sync.png)

Det finns ingen enda katalogdatakälla i den här modellen. Vissa system har egna data, men inget enskilt system innehåller alla data. Microsoft 365 samarbetar med Azure AD i den här datamodellen. Azure AD är "informationssystemet" för delade data, som vanligtvis är små och statiska data som används av varje tjänst. Den externa modellen som används i Microsoft 365 och Azure AD ger den delade datavyn.

Microsoft 365 använder både fysisk lagring och Azure-molnlagring. Exchange Online (inklusive Exchange Online Protection) och Skype för företag använder eget lagringsutrymme för kunddata. SharePoint Online använder både SQL Server och Azure Storage, vilket därmed behöver ytterligare avgränsning av kunddata på lagringsnivån.

## <a name="exchange-online"></a>Exchange Online

Exchange Online lagrar kunddata i postlådor. Postlådor finns i Extensible Storage Engine -databaser (ESE) som kallas postlådedatabaser. Det omfattar användarpostlådor, länkade postlådor, delade postlådor och postlådor för gemensamma mappar. Användarpostlådor innehåller sparat Skype för företag innehåll, till exempel konversationshistorik.

Postlådeinnehållet omfattar:

- E-postmeddelanden och e-postbilagor
- Kalenderinformation och ledig/upptagen-information
- Kontakter
- Uppgifter
- Kommentar
- Grupper
- Slutledningsdata

Varje postlådedatabas i Exchange Online innehåller postlådor från flera klientorganisationar. En auktoriseringskod säkrar varje postlåda, inklusive inom ett innehavare. Som standard har endast den tilldelade användaren åtkomst till en postlåda. Åtkomstkontrollista (ACL) som skyddar en postlåda innehåller en identitet som autentiseras av Azure AD på innehavarnivå. Postlådorna för varje klientorganisation är begränsade till identiteter som autentiseras mot klientorganisationens autentiseringsleverantör, som endast omfattar användare från den klientorganisationen. Innehållet i klientorganisation A kan inte på något sätt erhållas av användare i klientorganisation B, såvida det inte uttryckligen godkänts av klientorganisation A.

## <a name="skype-for-business"></a>Skype för företag

Skype för företag lagrar data på olika platser:

- Användar- och kontoinformation, som omfattar anslutningsslutpunkter, klient-IDn, uppringningsplaner, inställningar för roaming, närvarotillstånd, kontaktlistor osv. lagras i Skype för företag Active Directory-servrar och i olika Skype för företag-databasservrar. Kontaktlistor lagras i användarens e Exchange Online postlåda om användaren är aktiverad för båda produkterna eller på Skype för företag-servrar om användaren inte är det. Skype för företag av databasservrar partitioneras inte per klientorganisation, men data i flera innehavare isoleras genom rollbaserad åtkomstkontroll (RBAC).
- Mötesinnehåll och uppladdade data lagras i resurser för Distributed File System (SÅS). Det här innehållet kan också arkiveras i Exchange Online om det är aktiverat. PARTITION-delningarna partitioneras inte per klientorganisation. Innehållet skyddas med ACL och flera innehavare tillämpas via RBAC.
- Samtalsdetaljposter, som är aktivitetshistoriken, till exempel samtalshistorik, snabbmeddelandesessioner, programdelning, snabbmeddelandehistorik osv., kan också lagras i Exchange Online, men de flesta samtalsposter lagras tillfälligt på samtalsdetaljposter (CDR-servrar). Innehållet partitioneras inte per innehavare, men flera innehavare tillämpas via RBAC.

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online har flera oberoende mekanismer som ger dataisolering. Det lagrar objekt som abstrakt kod i programdatabaser. När en användare till exempel laddar upp en fil till SharePoint Online delas filen upp automatiskt, översätts till programkod och lagras i flera tabeller över flera databaser.

Om en användare kan få direkt åtkomst till det lagringsutrymme som innehåller data kan innehållet inte tolkas av en person eller något annat system än SharePoint Online. Dessa mekanismer inkluderar säkerhetsåtkomstkontroll och egenskaper. Alla SharePoint Online-resurser skyddas med auktoriseringskoden och RBAC-principen, även under ett innehavare. Åtkomstkontrollista (ACL) som skyddar en resurs innehåller en identitet som autentiseras på innehavarnivå. SharePoint Onlinedata för en klient är begränsade till identiteter som autentiseras av klientorganisationens autentiseringsleverantör.

Förutom ACL:er skrivs en egenskap på klientorganisationsnivå som anger autentiseringsleverantören (som är den klientspecifika Azure AD) en gång och kan inte ändras när den har angetts. När egenskapen för autentiseringsleverantörens klientorganisation har angetts för en klientorganisation kan den inte ändras med hjälp av API:er som exponeras för en klientorganisation.

Ett unikt *SubscriptionId* används för varje klientorganisation. Alla kundwebbplatser ägs av en klientorganisation och tilldelas *ett SubscriptionId* som är unikt för innehavaren. Egenskapen *SubscriptionId* på en webbplats skrivs en gång och är permanent. När en klientorganisation har tilldelats kan en webbplats inte flyttas till en annan klientorganisation. *SubscriptionId är* nyckeln som används för att skapa säkerhetsomfånget för autentiseringsleverantören och är knuten till klientorganisationen.

SharePoint Online använder SQL Server och Azure Storage för lagring av innehållsmetadata. Partitionsnyckeln för innehållsarkivet är *SiteId* i SQL. När du kör en SQL fråga använder SharePoint Online ett *SiteId* som verifierats som en del av en *prenumerations-ID-kontroll på innehavarnivå.*

SharePoint Online lagrar krypterat filinnehåll i Microsoft Azure blobbar. Varje SharePoint Online-servergrupp har ett eget Microsoft Azure-konto och alla blobbar som sparas i Azure krypteras individuellt med en nyckel som lagras i SQL-innehållslagringsbutiken. Krypteringsnyckeln som skyddas i koden av auktoriseringslagret och visas inte direkt för slutanvändaren. SharePoint Online har övervakning i realtid för att identifiera när en HTTP-begäran läser eller skriver data för mer än en klientorganisation. Prenumerationsidentitet *för begäran* spåras mot *prenumerations-ID för* den använda resursen. Förfrågningar om åtkomst till resurser i fler än en klientorganisation ska aldrig göras av slutanvändare. Tjänstförfrågningar i en miljö med flera klientorganisationen är det enda undantaget. Sök crawlern hämtar till exempel innehållsändringar för en hel databas på en gång. Det omfattar vanligtvis fråga webbplatser för fler än en klientorganisation i en enda tjänstbegäran, vilket görs av effektivitetsskäl.

## <a name="teams"></a>Teams

Data Teams lagras på olika sätt beroende på innehållstyp. 

Ta en titt [på pausen av Ignite Microsoft Teams lite arkitektur](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) för en ingående diskussion.

### <a name="core-teams-customer-data"></a>Basdata Teams kunddata

Om klientorganisationen finns i Australien, Kanada, EUROPEISKA UNIONEN, Frankrike, Tyskland, Indien, Japan, Sydafrika, Sydkorea, Schweiz (som omfattar Liechtenstein), Förenade Arabemiraten, Storbritannien eller USA, lagrar Microsoft följande kunddata endast på den platsen:

- Teams chattar, team- och kanalkonversationer, bilder, röstmeddelanden och kontakter.
- SharePoint Onlinewebbplatsinnehåll och filer som lagrats på webbplatsen.
- Filer som laddats upp OneDrive för arbete eller skola.

#### <a name="chat-channel-messages-team-structure"></a>Chatt, kanalmeddelanden, teamstruktur

Alla team i Teams backas upp av en Microsoft 365 grupp och dess SharePoint webbplats och Exchange postlåda. Privata chattar (inklusive gruppchattar), meddelanden som skickas som en del av en konversation i en kanal och strukturen för team och kanaler lagras i en chatttjänst som körs i Azure. Data lagras också i en dold mapp i postlådorna för användare och grupper för att aktivera informationsskyddsfunktioner.

#### <a name="voicemail-and-contacts"></a>Röstbrevlåda och kontakter

Röstmeddelanden lagras i Exchange. Kontakter lagras i Exchange molnbaserad datalagring. Exchange och Exchange-baserade molnlagringscentret tillhandahåller redan data som lagras i vart och ett av de globala datacenter geosna. För alla team lagras röstmeddelanden och kontakter i landet för Australien, Kanada, Frankrike, Tyskland, Indien, Japan, Förenade Arabemiraten, Storbritannien, Sydafrika, Sydkorea, Schweiz (som inkluderar Liechtenstein) och USA. För alla andra länder lagras filer i USA, Europa eller en Asia-Pacific baserat på tillhörighet till en klientorganisation.

#### <a name="images-and-media"></a>Bilder och media

Media som används i chattar (utom GIPHY GIF-filer som inte lagras men är en referenslänk till den ursprungliga GIPHY-tjänst-URL:en, Giphy är en icke-Microsoft-tjänst) lagras i en Azure-baserad medietjänst som är distribuerad till samma platser som chatttjänsten.

#### <a name="files"></a>Filer

Filer (inklusive OneNote och Wiki) som någon delar i en kanal lagras på teamets SharePoint webbplats. Filer som delas i en privat chatt eller en chatt under ett möte eller samtal laddas upp och lagras i OneDrive för arbets- eller skolkontot för den användare som delar filen. Exchange, SharePoint och OneDrive tillhandahåller redan data som lagras i varje globalt datacenter geos. Så för befintliga kunder är alla filer, OneNote-anteckningsböcker, Teams wiki-innehåll och postlådor som ingår i Teams-upplevelsen redan lagrade på platsen baserat på tillhörighet till en klientorganisation. Filer lagras i landet för Australien, Kanada, Frankrike, Tyskland, Indien, Japan, Förenade Arabemiraten, Storbritannien, Sydafrika, Sydkorea och Schweiz (som inkluderar Liechtenstein). För alla andra länder lagras filer i USA, Europa eller Asien, baserat på tillhörighet till en klientorganisation.
