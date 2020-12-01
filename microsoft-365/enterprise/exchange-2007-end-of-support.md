---
title: Översikt över supporten som upphör för Exchange 2007
ms.author: dstrome
author: dstrome
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: c3024358-326b-404e-9fe6-b618e54d977d
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Lär dig mer om alternativen efter Exchange Server 2007-supporten och börja planera migrering till Microsoft 365, Office 365 eller Exchange 2016.
ms.openlocfilehash: 3f0a5c8ef9765a184358b932548eaa2ae7c59adc
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519851"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Översikt över supporten som upphör för Exchange 2007

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Exchange Server 2007 nådde Supportens slut i april 2017. Om du inte har startat migreringen från Exchange 2007 till Microsoft 365, Office 365 eller Exchange 2016 är det dags att börja planera.
  
## <a name="what-does-end-of-support-mean"></a>Vad innebär *slut på support* ?

Exchange Server, till exempel nästan alla Microsoft-produkter, har en support livs cykel under vilken vi tillhandahåller nya funktioner, korrigeringar, säkerhets korrigeringar och så vidare. Denna livs cykel räcker vanligt vis i 10 år från produkten första gången. Slutet av livs cykeln kallas produkt Supportens slut. Eftersom Exchange 2007 nådde Supportens slut den 11 april 2017, erbjuder Microsoft inte längre:
  
- Teknisk support för problem som kan uppstå.
    
- Program korrigeringar för problem som kan påverka serverns stabilitet och användbarhet.
    
- Säkerhets korrigeringar för säkerhets problem som kan göra servern sårbar för säkerhets brott.
    
- Tids zons uppdateringar.
    
Din installation av Exchange 2007 fortsätter att köras efter slutdatumet för supporten. Men eftersom det inte finns några nya uppdateringar eller support rekommenderar vi starkt att du migrerar från Exchange 2007 så snart som möjligt.
  
Mer information om Office 2007-servrar som är nära slutet av support finns i [Planera uppgraderingen från Office 2007-servrar och-produkter](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>Vilka alternativ har jag?

Du kan:
  
- Migrera till Microsoft 365 genom att använda snabbmigrering, mellanliggande eller HYBRIDS ökning.
    
- Migrera dina Exchange 2007-servrar till en nyare version av Exchange på dina lokala servrar.
    
I följande avsnitt förklaras alla alternativ i detalj.
  
### <a name="migrate-to-microsoft-365"></a>Migrera till Microsoft 365

Migrering av e-post till Microsoft 365 är det bästa och enklaste alternativet för att ta bort din Exchange 2007-distribution. Med en migrering till Microsoft 365 kan du skapa ett enkelt hopp från 10 år-gammal teknik till de senaste funktionerna, till exempel:
  
- Funktioner för efterlevnad, till exempel bevarande principer, In-Place och rättsliga undantag, pågående eDiscovery och mer
    
- Microsoft 365-grupper
    
- Prioriterad inkorg
    
- MyAnalytics
    
- REST API: er för åtkomst till e-post, kalendrar, kontakter och så vidare
    
Microsoft 365 får också nya funktioner först, så du och användarna kan vanligt vis börja använda dem direkt. Men du behöver inte oroa dig över:
  
- Köpa och underhålla maskin vara.
    
- Betala till hetta och låt dina servrar svalna.
    
- Hålla dig uppdaterad om säkerhets-, produkt-och tids zoner.
    
- Bevara lagring och program vara för att stödja kraven på efterlevnad.
    
- Uppgradera till en ny version av Exchange. Med Microsoft 365 är du alltid med den senaste versionen av Exchange.
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>Hur ska jag migrera till Microsoft 365?

Du har några alternativ för migrering. Du måste överväga några saker, till exempel:

- Antalet säten eller post lådor som du måste flytta.
- Hur länge du vill att migreringen ska pågå.
- Om du behöver sömlös integrering mellan din lokala installation och Microsoft 365 under migreringen.

I den här tabellen visas migreringsåtgärder och de viktigaste faktorer som avgör vilken metod som ska användas:
  

|**Flyttnings alternativ**|**Organisationens storlek**|**Repetition**|
|:-----|:-----|:-----|
|Snabb migrering  <br/> |Färre än 150 platser  <br/> |En vecka eller mindre  <br/> |
|Stegvis migrering  <br/> |Fler än 150 platser  <br/> |Några veckor  <br/> |
|Fullständig hybrid migration  <br/> |Flera hundra till tusentals platser  <br/> |Några månader eller mer  <br/> |
   
I följande avsnitt får du en översikt över de här metoderna. Mer information finns i [bestämma en mappsökväg](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27). 
  
#### <a name="cutover-migration"></a>Snabb migrering

I en snabbmigrering-migrering migrerar du alla dina post lådor, distributions grupper, kontakter och så vidare till Microsoft 365 på ett förvalt datum och en tid. När migreringen är klar stänger du av dina lokala Exchange-servrar och börjar använda Microsoft 365 exklusivt.
  
Snabbmigrering migration är perfekt för små organisationer som inte har många post lådor, vill komma till Microsoft 365 snabbt och inte vill hantera vissa av de andra metoderna. Men det bör göras om en vecka eller mindre och det kräver att användare konfigurerar om sina Outlook-profiler. Snabbmigrering migration kan hantera upp till 2 000-postlådor, men vi rekommenderar starkt att du använder den för att migrera högst 150-postlådor. Om du försöker migrera mer kan det ta slut på dig att överföra alla post lådorna före din tids gräns och din IT-supportavdelning kan bli mycket roligare med att hjälpa användarna att konfigurera om Outlook.
  
Om du funderar på att göra en snabbmigrering migrering är det bra att tänka på:
  
- Microsoft 365 måste ansluta till dina Exchange 2007-servrar med hjälp av Outlook överallt via TCP-port 443.
    
- Alla lokala post lådor flyttas till Microsoft 365.
    
- Du behöver ett lokalt administratörs konto med Läs åtkomst till användarnas post lådor.
    
- Exchange 2007 accepterade domäner som du vill använda i Microsoft 365 måste läggas till som verifierade domäner i tjänsten.
    
- Mellan den tid som du börjar med migreringen synkroniserar Microsoft 365 regelbundet Microsoft 365-och lokala post lådorna. Då kan du slutföra migreringen utan att oroa dig för att e-post kvars i dina lokala post lådor.
    
- Användarna får nya tillfälliga lösen ord för sina Microsoft 365-konton. De måste ändra sitt lösen ord när de loggar in i sin post låda första gången.
    
- Du behöver en Microsoft 365-licens som innehåller Exchange Online för varje användar post låda du migrerar.
    
- Användarna måste konfigurera en ny Outlook-profil på var och en av deras enheter och hämta e-postmeddelandet igen. Hur mycket e-post som kommer att hämtas kan variera. Mer information finns i [ändra hur mycket e-post som ska behållas offline](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Mer information om snabbmigrering migrering finns i:
  
- [Det här behöver du veta om en snabbmigrering-e-postmigrering](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [Utföra en snabbmigrering migrering av e-post](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>Stegvis migrering

I en stegvis migrering har du några hundra eller några tusen post lådor som du vill migrera till Microsoft 365, du måste ta en vecka eller mer för att slutföra migreringen och behöver inte någon av de avancerade hybrid funktionerna för att dela ledig/upptagen-kalendern.
  
Stegvis migrering är perfekt för organisationer som behöver ta mer tid att migrera sina post lådor till Microsoft 365 men ändå planera för att slutföra migreringen inom några veckor. Du kan migrera post lådor i grupper. Du bestämmer hur många och vilka post lådor som ska migreras vid en given tidpunkt. Du kan skapa en post lådor för användare på samma avdelning, till exempel om du vill att de ska flyttas samtidigt. Du kan också lämna Executive-postlådor till den sista satsen. Precis som med snabbmigrering-migreringar måste användarna återskapa sin Outlook-profil.
  
Om du funderar på att göra en stegvis migrering kan du tänka på följande:
  
- Microsoft 365 måste ansluta till dina Exchange 2007-servrar med hjälp av Outlook överallt via TCP-port 443.
    
- Du behöver ett lokalt administratörs konto med Läs åtkomst till användarnas post lådor.
    
- Exchange 2007 accepterade domäner som du planerar att använda i Microsoft 365 måste läggas till som verifierade domäner i tjänsten.
    
- Du måste skapa en CSV-fil med fullständigt namn och e-postadress för varje post låda som du planerar att migrera i en grupp. Du måste också ha ett nytt lösen ord för varje post låda som du migrerar och skicka lösen ordet till varje användare. Användaren uppmanas att ändra lösen ordet första gången de loggar in i sin nya Microsoft 365-postlåda.
    
- Mellan den tidpunkt då du startar migreringsarkivet och när du påbörjar fasen kommer Microsoft 365 regelbundet att synkronisera Microsoft 365-och lokala post lådor som ingår i gruppen. Då kan du slutföra migreringen utan att oroa dig för att e-post kvars i dina lokala post lådor.
    
- Du behöver en Microsoft 365-licens som innehåller Exchange Online för varje användar post låda du migrerar.
    
- Användarna måste konfigurera en ny Outlook-profil på var och en av deras enheter och hämta e-postmeddelandet igen. Hur mycket e-post som kommer att hämtas kan variera. Mer information finns i [ändra hur mycket e-post som ska behållas offline](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Mer information om stegvis migrering finns i:
  
- [Vad du behöver veta om en stegvis migrering av e-post](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [Utföra en stegvis migrering av e-post](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>Fullständig hybrid

I en fullständig hybrid migrering har din organisation många hundra, upp till tusentals brev lådor, och du vill flytta några eller alla av dem till Microsoft 365. Eftersom de här migreringarna normalt är längre tid gör hybrid migrering det möjligt att:
  
- Visa lokala användare den lediga/upptagna kalender informationen för användare i Microsoft 365 och vice versa.
    
- Se en Unified Global Address-lista som innehåller mottagare i både lokala och Microsoft 365.
    
- Visa fullständiga egenskaper för Outlook-mottagare för alla användare, oavsett om de är lokalt eller i Microsoft 365.
    
- Säker e-postkommunikation mellan lokala Exchange-servrar och Microsoft 365 med hjälp av TLS och certifikat.
    
- Behandla meddelanden som skickas mellan lokala Exchange-servrar och Microsoft 365 som interna, så att de kan:
    
  - Utvärderas och behandlas korrekt av transport-och efterföljandekrav riktade mot interna meddelanden.
    
  - Kringgå skydd mot skräp post.
    
Fullständig hybrid migration är bäst för organisationer som förväntar sig att vara i en hybrid konfiguration för många månader eller mer. Du får de funktioner som anges ovan i det här avsnittet, plus katalog-synkronisering, bättre integrerade kompatibilitet och möjligheten att flytta post lådor till och från Microsoft 365 genom att använda Online-postlåda. Microsoft 365 blir en förlängning av din lokala organisation.
  
Om du funderar på att göra en fullständig hybrid migrering är det bra att tänka på:
  
- Fullständig hybrid migration är inte passar alla typer av organisationer. På grund av komplexiteten hos fullständiga hybrid migreringar kan organisationer med färre än ett fåtal hundra post lådor normalt sett inte utnyttja fördelarna som motiverar att det kostar något. Om det låter som din organisation, rekommenderar vi att du tar en snabbmigrering eller stegvis migrering i stället.
    
- Du måste distribuera minst en Exchange 2013-server i din Exchange 2007-organisation för att fungera som en "hybrid server". Den här servern kommunicerar med Microsoft 365 åt dina Exchange 2007-servrar.
    
- Microsoft 365 måste ansluta till "hybrid server" via Outlook överallt via TCP-port 443.
    
- Du måste konfigurera profilsynkronisering med Azure Active Directory (Azure AD) Connect mellan lokala Active Directory-servrar och Microsoft 365.
    
- Användarna kan logga in på sin Microsoft 365-postlåda med samma användar namn och lösen ord som när de loggar in i det lokala nätverket. (Den här funktionen kräver Azure AD Connect med Lösenordssynkronisering och/eller Active Directory Federation Services.)
    
- Du behöver en Microsoft 365-licens som innehåller Exchange Online för varje användar post låda du migrerar.
    
- Användarna behöver inte konfigurera en ny Outlook-profil på de flesta enheter, även om vissa äldre Android-telefoner kanske behöver en ny profil. Användarna behöver inte ladda ner e-postmeddelandet igen.
    
Om fullständig hybrid migration låter dig se följande resurser för att hjälpa dig med migreringen:
  
- [Distributions assistent för Exchange](https://aka.ms/exdeploy)
    
- [Hybrid distributioner av Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx)
    
- [Hybrid konfigurations guiden](https://technet.microsoft.com/library/hh529921%28v=exchg.150%29.aspx)
    
- [Vanliga frågor om konfigurations guiden](https://technet.microsoft.com/library/mt488940%28v=exchg.150%29.aspx)
    
- [Förutsättningar för hybrid distribution](https://technet.microsoft.com/library/hh534377%28v=exchg.150%29.aspx)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>Migrera till en nyare version av Exchange Server

Vi tror att du kan nå det bästa värde-och användar upplevelsen genom att migrera till Microsoft 365. Men vi förstår också att vissa organisationer måste hålla sin e-post lokalt. Detta kan bero på reglernas krav, för att säkerställa att data inte lagras i ett Data Center i ett annat land eller liknande. Om du väljer att behålla din e-post lokalt kan du migrera din Exchange 2007-miljö till Exchange 2010, Exchange 2013 eller Exchange 2016.
  
Om du inte kan migrera till Microsoft 365 rekommenderar vi att du migrerar till Exchange 2016. Exchange 2016 innehåller alla funktioner i tidigare versioner av Exchange. Det stämmer också bäst med Microsoft 365, även om vissa funktioner endast är tillgängliga i Microsoft 365. Kolla in några av de saker du har saknatt:
  
|**Exchange-version**|**Funktioner**|
|:-----|:-----|
|Exchange 2010  <br/> | Role-Based åtkomst kontroll (behörigheter utan ACL)  <br/>  Principer för Outlook Web App-postlådan  <br/>  Möjlighet att dela ledig/upptagen och delegera kalendrar mellan organisationer  <br/> |
|Exchange 2013  <br/> | *Funktioner från Exchange 2010 och...*  <br/>  Förenklad arkitektur som reducerar antalet Server roller till tre (post låda, klient åtkomst, Edge Transport)  <br/>  Principer för skydd mot data förlust (DLP) som hjälper till att förhindra känslig information  <br/>  Förbättrad Outlook Web App-upplevelse  <br/> |
|Exchange 2016  <br/> | *Funktioner från Exchange 2013 och...*  <br/>  Ytterligare förenklade Server roller för just post lådan och Edge-Transport  <br/>  Förbättrat DLP tillsammans med integrering med SharePoint  <br/>  Förbättrad databas återhämtning  <br/>  Samarbete online |
   
#### <a name="which-version-should-i-migrate-to"></a>Vilken version ska jag migrera till?

Vi rekommenderar att du först utgår från att du kommer att migrera till Exchange 2016. Använd sedan följande information för att bekräfta ditt antagande eller för att utesluta Exchange 2016. Om det inte går att migrera till Exchange 2016 gör du samma sak med Exchange 2013 och så vidare.
  
|**Bedömning**|**Mer information**|
|:-----|:-----|
|Slut på support datum  <br/> | Precis som Exchange 2007 har varje version av Exchange sitt eget eget support datum:  <br/> *Exchange 2010* -januari 2020  <br/> *Exchange 2013* – april 2023  <br/> *Exchange 2016* -oktober 2025  <br/>  Den tidigare slut delen av supporten, desto förr måste du göra en ny migrering.<br/> |
|Migrering till Exchange 2010 och 2013.  <br/> |Här är de allmänna faserna för migrering till Exchange 2010 eller Exchange 2013:  <br/> -Installera Exchange 2010 eller 2013 i din befintliga Exchange 2007-organisation. <br/>-Flytta tjänster och annan infrastruktur till Exchange 2010 eller 2013.<br/>-Flytta post lådor och gemensamma mappar till Exchange 2010 eller 2013.<br/>-Avprovision återstående Exchange 2007-servrar. |
|Sökväg till migrering till Exchange 2016  <br/> |Här är de allmänna faserna för migrering till Exchange 2016:  <br/> -Installera Exchange 2013 i din befintliga Exchange 2007-organisation.<br/>-Flytta tjänster och annan infrastruktur till Exchange 2013.<br/>-Flytta post lådor och gemensamma mappar till Exchange 2013.<br/>-Avprovision återstående Exchange 2007-servrar.<br/>-Installera Exchange 2016 i din befintliga Exchange 2013-organisation.<br/>-Flytta post lådor, gemensamma mappar, tjänster och annan infrastruktur till Exchange 2016 (det spelar ingen roll). Avprovisiona återstående Exchange 2013-servrar.<br/><br/> **Obs!** Det är enkelt att migrera från Exchange 2013 till Exchange 2016. De två versionerna har nästan samma maskin varu krav och de här versionerna är mycket kompatibla. Så att du kan återskapa en server du köpte för Exchange 2013 och installera Exchange 2016 på den. För de flesta användare ser du inte ens att post lådan har flyttats bort från servern och sedan tillbaka när du har byggt upp den med Exchange 2016.           |
|Versions samexistens  <br/> | När du migrerar till...  <br/> **Exchange 2016:** Exchange 2016 kan inte installeras i en organisation som innehåller en Exchange 2007-server. Du måste först migrera till Exchange 2010 eller 2013 (vi rekommenderar Exchange 2013), ta bort alla Exchange 2007-servrar och sedan migrera till Exchange 2016.  <br/> **Exchange 2010 eller exchange 2013:** Du kan installera Exchange 2010 eller Exchange 2013 i en befintlig Exchange 2007-organisation. Då kan du installera en eller flera Exchange 2010-eller 2013-servrar och utföra migreringen.  <br/> |
|Server maskin vara  <br/> | Serverns maskin varu krav har ändrats från Exchange 2007. Kontrol lera att din maskin vara är kompatibel. Mer information finns i:  <br/> [System krav för Exchange 2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx) <br/> [System krav för Exchange 2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx) <br/> [System krav för Exchange 2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx) <br/>  Du kommer att upptäcka att viktiga förbättringar av Exchange-prestanda och den ökade dator kraft och lagrings kapaciteten på nyare servrar innebär att du troligen behöver färre servrar för att stöda samma antal post lådor.  <br/> |
|Operativ system version  <br/> | De lägsta operativ system versionerna som stöds för varje version är:  <br/> **Exchange 2016** – Windows Server 2012  <br/> **Exchange 2013** – Windows Server 2008 R2 SP1  <br/> **Exchange 2010** – Windows Server 2008 SP2  <br/>  Mer information om stöd för operativ system finns i [matrisen med stöd för Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
|Funktionalitetsnivå för Active Directory-skogar  <br/> | De lägsta funktions nivåerna för Active Directory-skogar som stöds för varje version är:  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  Få reda på mer om stöd för skogens funktionalitetsnivå i [matrisen med stöd för Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
|Office-klient versioner  <br/> | De lägsta Office-klient versionerna som stöds för varje version är:  <br/> **Exchange 2016** – Office 2010 (med de senaste uppdateringarna)  <br/> **Exchange 2013** – Office 2007 SP3  <br/> **Exchange 2010** – Office 2003  <br/>  Mer information om support för Office-klienter finns i [matrisen med stöd för Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
   
#### <a name="how-do-i-migrate"></a>Hur migrerar jag?

Om du vill behålla lokal e-post kan du använda följande resurser för att hjälpa dig med migreringen:
  
- [Distributions assistent för Exchange](https://aka.ms/exdeploy)
    
- Active Directory-schema-ändringar för Exchange [2016](https://technet.microsoft.com/library/bb738144%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb738144%28v=exchg.150%29.aspx), [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)
    
- System krav för Exchange [2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx)
    
- Förutsättningar för Exchange [2016](https://technet.microsoft.com/library/bb691354%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb691354%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/bb691354%28v=exchg.141%29.aspx)
    
## <a name="get-help"></a>Få hjälp

Om du migrerar till Microsoft 365 kanske du är berättigad att använda vår Microsoft FastTrack-tjänst. FastTrack ger metod tips, verktyg och resurser som gör migreringen till Microsoft 365 så sömlös som möjligt. Det bästa av allt är att en support tekniker vägleder dig genom migreringen, från planering och design så att du kan migrera den senaste post lådan. Mer information om FastTrack finns i [Microsoft FastTrack](https://fasttrack.microsoft.com/).
  
Om du stöter på problem under migreringen till Microsoft 365 och du inte använder FastTrack, eller din migrering till en nyare version av Exchange Server, kan vi hjälpa dig. Här är några resurser som du kan använda:
  
- [Teknisk community](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [Kund support](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>Relaterade ämnen

[Resurser som hjälper dig att uppgradera dina Office 2007-servrar och-klienter](upgrade-from-office-2007-servers-and-products.md)
