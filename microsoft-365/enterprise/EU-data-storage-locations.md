---
title: Dataplatser för Europeiska unionen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Bestäm var dina Microsoft 365-kunddata lagras inom Europeiska unionen
ms.openlocfilehash: 5a50600c123dad1a0e4d14fd8f47283f951d3edc
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376736"
---
# <a name="data-locations-for-the-european-union"></a>Dataplatser för Europeiska unionen



## <a name="your-data-is-your-business"></a>Dina uppgifter tillhör dig

Microsoft erkänner vikten av att upprätthålla sekretessen och konfidentialitet för dina affärsdata. Dina data tillhör dig och du kan när som helst komma åt, ändra eller ta bort den. Microsoft använder inte dina data utan ditt medgivande och när vi har ditt medgivande använder vi dina data för att endast tillhandahålla de tjänster du har valt. Om du lämnar en av våra tjänster, ser vi till att du fortsätter att äga dina data, enligt strikta standarder och processer för att ta bort data från våra system. 

>[!Note]
>Kunddata (även kallad "dina data" eller "dina affärsdata") betyder all information, inklusive text-, ljud-, video- eller bildfiler och programvara som du tillhandahåller Microsoft eller som tillhandahålls för dina räkning genom din användning av Microsoft företagstjänster online, exklusive Microsoft Professionella tjänster. Det inkluderar kundinnehåll, vilket är de data du laddar upp för lagring eller bearbetning och appar du laddar upp för distribution via en Microsoft-molntjänst för företag. Till exempel inkluderar kundinnehåll Exchange Online-e-post och bilagor, SharePoint Online-webbplatsinnehåll eller konversationer med snabbmeddelanden. 
>

## <a name="data-storage-and-processing"></a>Datalagring och bearbetning

När du använder Microsoft 365-tjänster börjar vi med antagandet att våra företagskunder vill ha sin affärsdata lagrad och bearbetad nära hemmet. När det är möjligt gör vi just det. Om du vill förvara dina data i datacenter närmast dig lagrar vi dina data baserat på den företagsplats du anger när du skapar din klientorganisation. För att välja lagringsplatser som är relevanta för din organisations företag kan du skapa så många klientorganisationer för din organisation som du vill.  

### <a name="where-eu-data-is-stored"></a>Där kunddata lagras

Vi har datacenter i Tyskland och Frankrike som gör att du kan lagra data i ditt land om ditt företag finns där. Våra regionala EU-datacenter finns i Österrike, Finland, Frankrike, Irland och Nederländerna. Dina data för följande tjänster kommer att vara värd på följande platser baserat på vilken faktureringsadress du väljer: 

| Tjänstnamn | Plats för klientorganisationer skapade med en faktureringsadress i Frankrike | Plats för klientorganisationer skapade med faktureringsadress i Tyskland | Plats för klientorganisationer skapade med en faktureringsadress i alla andra EU-länder |
|:-------|:-----|:-------|:-------|
| Exchange online | Frankrike | Tyskland | EU |
| OneDrive för företag | Frankrike | Tyskland | EU |
| SharePoint online | Frankrike | Tyskland | EU |
| Skype för företag | EU | EU | EU |
| Microsoft Teams | Frankrike | Tyskland | EU |
| Office online och mobile | Frankrike | Tyskland | EU |
| Exchange Online Protection | Frankrike | Tyskland | EU |
| Intune | EU | EU | EU |
| MyAnalytics | Frankrike | Tyskland | EU |
| Planner | EU | EU | EU |
| Yammer | EU | EU | EU |
| OneNote-tjänster | Frankrike | Tyskland | EU |
| Strömma | EU | EU | EU |
| Whiteboard | EU | EU | EU |
| Formulär | EU | EU | EU |
||||| 

>[!Note]
>Om du har en Office 365 Education-prenumeration med en faktureringsadress i Frankrike eller Tyskland kan dina data lagras i våra regionala EU-datacenter. 
>

### <a name="where-eu-data-is-computed"></a>Där EU-data beräknas

När du initierar användningen av någon av ovanstående tjänster kommer beräkningarna som behövs för att tillhandahålla tjänsten för dina data lagrade i ett av våra regionala europeiska datacenter (eller i ditt land) att ske inom samma geografiska gräns om inte en tillfällig dataöverföring sker behövs för att utföra beräkningen i ett Microsoft-datacenter som ligger längre bort. 

Om en tillfällig överföring krävs kommer vi alltid att använda avancerad kryptering i överföringen och vi kommer alltid att returnera dina data till din valda datalagringsplats omedelbart. Vi förlitar oss på att vi följer europeisk lagstiftning genom standardavtalsklausuler (SCCs) för dessa tillfälliga transfereringar, tillsammans med våra kompletterande åtgärder för att säkerställa att data skyddas. 

Mer information finns i [Europeiska unionens modellklausuler](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses).

>[!Note]
>Kunddata för Sway och Workplace Analytics lagras och beräknas i USA om du väljer att använda dessa tjänster.
>

>[!Note]
>Microsoft 365-tjänster kan fråga och lagra delar av klient- / identitetsdatainformation i andra regioner än EU vid behov för att underlätta vissa scenarier. I scenarier av gränsöverskridande e-postdirigering, samtalsdirigering och autentisering kan Microsoft 365-system behöva viss information om EU:s mottagare för att dirigera begäran korrekt. Microsoft 365-system är också beroende av Azure Active Directory för identitets- och autentiseringsfunktioner. Mer information finns i  [Identitetsdatalagring för europeiska kunder i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-data-storage-eu).
>

## <a name="how-microsoft-protects-your-data"></a>Så skyddar Microsoft dina data

### <a name="security-measures"></a>Säkerhetsåtgärder

Microsoft skyddar dina data med flera lager av säkerhets- och krypteringsprotokoll. Få en översikt över Microsofts datasäkerhetsfunktioner i [Microsoft 365-krypteringsartikel](../compliance/encryption.md).

Som standard skyddar Microsoft Managed Keys dina kunddata. Data som kvarstår på fysiska medier krypteras alltid med hjälp av FIPS 140-2-kompatibla krypteringsprotokoll. Du kan också använda kundhanterade nycklar (CMK), [dubbel kryptering](../compliance/double-key-encryption.md)och/eller hårdvarusäkerhetsmoduler (HSM) för ökat dataskydd.

All datatrafik som rör sig mellan datacenter skyddas också med IEEE 802.1AE MAC-säkerhetsstandarder, vilket förhindrar fysiska "man-in-the-middle" -attacker.

För att förhindra obehörig fysisk åtkomst till datacenter använder vi rigorösa operativa kontroller och processer som inkluderar 24×7 videoövervakning, utbildad säkerhetspersonal och processer och smartkort eller biometrisk multifaktor åtkomst kontroller. Vid livslängden strimlas dataskivorna och förstörs. Om en hårddisk som används för lagring drabbas av maskinvarufel eller når slutet på dess livslängd, raderas på ett säkert sätt. Data på enheten är helt överskrivna för att säkerställa att data inte kan återställas på något sätt. När sådana enheter avvecklas, de strimlas och förstöras i linje med NIST SP 800-88 R1, riktlinjer för mediarensning. Poster i destruktion behålls och granskas som en del av Microsoft gransknings- och efterlevnadsprocess. Alla Microsoft 365-tjänster använder godkända mediehanteringstjänster för medielagring och radering.

### <a name="technical-controls"></a>Tekniska kontroller

Förutom det fysiska och tekniska skyddet vidtar Microsoft starka åtgärder för att skydda dina kunddata från obehörig åtkomst av Microsofts personal och underleverantörer. Åtkomst till kunddata från Microsoft-verksamhet och supportpersonal nekas som standard. Nästan all serviceverksamhet som utförs av Microsoft är helt automatiserad och mänskligt engagemang styrs och abstraheras från kunddata. 

Endast i sällsynta fall behöver en Microsoft-tekniker åtkomst till kunddata. Vanligtvis är detta bara nödvändigt om du begär Microsoft hjälp för att lösa ett kundproblem. Åtkomst till kunddata är mycket begränsad av rollbaserade åtkomstkontroller, multifaktorautentisering, dataminimering och andra kontroller. All åtkomst till kunddata loggas strikt, och både Microsoft och tredje part utför regelbundna revisioner (samt provgranskningar) för att intyga att någon åtkomst är lämplig.

Kunder kan använda kundhanterade nycklar för att förhindra att deras data kan läsas vid obehörig åtkomst. Både kryptering på serversidan och på klientsidan kan förlita sig på kundhanterade nycklar eller nycklar från kunden. I båda fallen skulle Microsoft inte ha åtkomst till krypteringsnycklar och kan inte dekryptera data. En SOC-granskning av en AICPA-ackrediterad revisor två gånger om året för att verifiera effektiviteten av våra säkerhetskontroller inom granskningsomfattning. SOC 2 typ 2-intygsrapporten som publiceras av revisorn förklarar under vilka omständigheter åtkomst till kunddata kan uppstå och hur. 

Förutom att lagra och bearbeta dina data när du använder onlinetjänsterna genererar Microsoft tjänstedata för att övervaka systemhälsan och för att utföra serviceåtgärder som felsökning. Som en integritetsskyddsåtgärd genererar och förlitar sig Microsoft på pseudonyma identifierare i denna tjänstgenererade data för att kunna skilja en användare från en annan utan att identifiera de faktiska användarna. Pseudonyma identifierare identifierar inte en person direkt, och informationen som möjliggör mappning av pseudonyma identifierare till faktiska användare skyddas som en del av dina data.

Mer information finns i [Vem kan komma åt dina data](https://www.microsoft.com/trust-center/privacy/data-access) och på vilka villkor och [underprocessorer och datasekretess](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4qVL2).

## <a name="how-microsoft-handles-government-requests"></a>Hur Microsoft hanterar myndighetsförfrågningar

Om en myndighet vill ha kunddata måste den följa tillämpliga juridiska processer. Microsoft måste delges en teckningsoption eller domstolsbeslut om innehåll, eller en stämning för abonnentinformation eller annan icke-innehållsdata. 

- Alla förfrågningar måste vara inriktade på specifika konton och identifierare.  
- Microsofts lagliga efterlevnadsteam granskar alla förfrågningar för att säkerställa att de är giltiga, avvisar dem som inte är giltiga och tillhandahåller endast de angivna uppgifterna.  
- Om Microsoft tvingas enligt lag att avslöja kunduppgifter kommer du omedelbart att meddelas och få en kopia av begäran, såvida inte Microsoft är lagligt förbjudet att göra det.
- Microsoft gör en lokal juridisk granskning av varje begäran som den mottar mot lokala lagar och standarder. Microsoft granskar också regelbundet sina screeningprocesser runt om i världen för att säkerställa att lokala rättsliga förfaranden följs och dess globala uttalande om mänskliga rättigheter tillämpas.

Om du vill ha mer information om Microsofts åtagande att utmana order i enlighet med EU: s GDPR, se [nya steg för att försvara dina data](https://blogs.microsoft.com/on-the-issues/2020/11/19/defending-your-data-edpb-gdpr/). 

När myndigheter eller brottsbekämpande myndigheter gör en laglig begäran om kunddata är Microsoft engagerat i öppenhet och begränsar vad det avslöjar. Två gånger om året publicerar vi antalet juridiska krav på kunddata som vi får från brottsbekämpande myndigheter runt om i världen. Mer information finns i [rapporten om brottsbekämpning](https://www.microsoft.com/corporate-responsibility/law-enforcement-requests-report). Denna rapport avslöjar inte specifikationerna för någon särskild efterfrågan, inklusive kunden i fråga. Två gånger om året publicerar vi också data om de juridiska krav som vi får från den amerikanska myndigheter. Se [USA: s nationella säkerhetsorderrapport](https://www.microsoft.com/corporate-responsibility/us-national-security-orders-report) för den senaste rapporten.  

Om du vill ha mer information, se [vanliga frågor](https://blogs.microsoft.com/datalaw/our-practices/) angående begäranden från myndigheter och brottsbekämpning, inklusive frågor om molnlagen.

## <a name="additional-resources"></a>Ytterligare resurser
 
- [Pålitligt dataskydd](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4FhZn) ger en översikt över hur Microsoft skyddar dina data när du använder Microsoft Online Services och Professional Services. Rekommenderas också att du läser [Microsoft Online Services Terms (OST) och Data Protection Addendum (DPA)](https://www.microsoft.com/licensing/product-licensing/products) som reglerar din användning av dessa tjänster.
- [Office 365-registrerade begäranden om GDPR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365) hjälper dig att hitta och agera på personuppgifter eller personlig information för att svara på DSR med hjälp av Microsoft 365-produkter, tjänster och administrativa verktyg. 
- [Konsekvensbedömningar av dataskydd: vägledning för datakontrollanter som använder Microsoft Office 365](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365) hjälper dig att avgöra om din organisation behöver utarbeta en DPIA, tillhandahåller vägledning, innehåller ett anpassningsbart DPIA-malldokument och tillhandahåller en DPIA Service Elements Matrix för många Microsoft 365-tjänster.
- [Lär dig hur modulerna](https://docs.microsoft.com/learn/paths/audit-safeguard-customer-data/) är utformade för personer inom granskning, efterlevnad, risk och juridiska roller som söker en övergripande förståelse ger en djupgående granskning av hur Microsoft 365: s grundläggande säkerhets- och sekretesspraxis för att skydda kunddata.
- [Microsofts erbjudande om efterlevnad](https://docs.microsoft.com/microsoft-365/compliance/offering-home) visar hur Microsoft 365-tjänster hjälper din organisation att uppfylla regelefterlevnadsstandarder. 

