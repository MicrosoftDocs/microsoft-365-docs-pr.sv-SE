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
description: Läs mer om alternativen efter Exchange Server supporten för Exchange Server 2007 och börja planera migreringen till Microsoft 365, Office 365 eller Exchange 2016.
ms.openlocfilehash: d7e8f50118dab6fcb618273f5c28497c80d4a549
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924206"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Översikt över supporten som upphör för Exchange 2007

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Exchange Server support för 2007 nåddes i april 2017. Om du inte har påbörjat migreringen från Exchange 2007 till Microsoft 365, Office 365 eller Exchange 2016 är det dags att börja planera.
  
## <a name="what-does-end-of-support-mean"></a>Vad innebär *slutet av supporten?*

Exchange Server, som nästan alla Microsoft-produkter, har en supportlivscykel under vilken vi tillhandahåller nya funktioner, programkorrigeringar, säkerhetskorrigeringar med mer. En livscykel varar vanligtvis i tio år från produktens första version. Slutet av perioden kallas för slutet av supporten för produkten. Eftersom Exchange 2007 tog slut på support den 11 april 2017 tillhandahåller Microsoft inte längre:
  
- Teknisk support för problem som kan uppstå.
    
- Programkorrigeringar för problem som kan påverka servrars stabilitet och användbarhet.
    
- Säkerhetskorrigeringar för säkerhetsproblem som kan göra servern sårbar för säkerhetsbrister.
    
- Tidszonsuppdateringar.
    
Din installation av Exchange 2007 fortsätter att köras efter supportens slutdatum. Men eftersom det inte finns några nya uppdateringar eller support rekommenderar vi starkt att du migrerar från Exchange 2007 så snart som möjligt.
  
Mer information om Office 2007-servrar som närmar sig slutet av supporten finns i Planera uppgraderingen från [Office 2007-servrar och -produkter.](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-are-my-options"></a>Vilka alternativ har jag?

Du kan:
  
- Migrera till Microsoft 365 med hjälp av cutover-, staged- eller hybridmigrering.
    
- Migrera dina Exchange 2007-servrar till en nyare version Exchange version på dina lokala servrar.
    
I följande avsnitt utforskar vi de olika alternativen i detalj.
  
### <a name="migrate-to-microsoft-365"></a>Migrera till Microsoft 365

Att migrera din e-post Microsoft 365 det bästa och enklaste alternativet för att dra tillbaka din Exchange 2007-distribution. Med en migrering till Microsoft 365 kan du ta ett enkelt hopp från 10 år gammal teknik till de senaste funktionerna, till exempel:
  
- Efterlevnadsfunktioner, till exempel bevarandeprinciper, In-Place bevarande av juridiska skäl, på plats för eDiscovery och mycket mer
    
- Microsoft 365-grupper
    
- Prioriterad inkorg
    
- MyAnalytics
    
- REST API:er för programmeringsåtkomst till e-post, kalendrar, kontakter och så vidare
    
Microsoft 365 är också först med att få nya funktioner och upplevelser, så att du och dina användare i regel kan börja använda dem direkt. Och du behöver inte tänka på följande:
  
- Köpa och underhålla maskinvara.
    
- Betala för att få värme och värm servrarna.
    
- Hålla dig uppdaterad om säkerhets-, produkt- och tidszonskorrigeringar.
    
- Underhålla lagring och programvara för att uppfylla efterlevnadskraven.
    
- Uppgradera till en ny version av Exchange. Med Microsoft 365 har du alltid den senaste versionen av Exchange.
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>Hur ska jag migrera till Microsoft 365?

Du har några migreringsalternativ. Du behöver tänka på några saker, bland annat:

- Antalet platser eller postlådor som du behöver flytta.
- Hur länge du vill att migreringen ska pågå.
- Om du behöver smidig integrering mellan din lokala installation och dina Microsoft 365 under migreringen.

I den här tabellen visas migreringsalternativen och de viktigaste faktorerna som avgör vilken metod du ska använda:
  

|**Migreringsalternativ**|**Organisationens storlek**|**Varaktighet**|
|:-----|:-----|:-----|
|Snabb migrering  <br/> |Färre än 150 platser  <br/> |En vecka eller mindre  <br/> |
|Stegvis migrering  <br/> |Fler än 150 platser  <br/> |Ett par veckor  <br/> |
|Fullständig hybridmigrering  <br/> |Flera hundra till tusentals platser  <br/> |Några månader eller mer  <br/> |
   
I följande avsnitt ges en översikt över de här metoderna. Mer information finns i [Bestämma en migreringsväg](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27). 
  
#### <a name="cutover-migration"></a>Snabb migrering

I en ominskad migrering kan du migrera alla dina postlådor, distributionsgrupper, kontakter och så vidare till Microsoft 365 med ett förvalt datum och tid. När migreringen är klar stänger du av dina lokala e Exchange servrar och börjar använda Microsoft 365 exklusivt.
  
Snabb migrering är perfekt för små organisationer som inte har många postlådor, som snabbt vill komma åt Microsoft 365 och inte vill ta itu med de andra metodernas komplexitet. Men det bör slutföras om en vecka eller mindre och användarna måste konfigurera om sina Outlook profiler. En flytt av data kan hantera upp till 2 000 postlådor, men vi rekommenderar starkt att du använder den för att migrera högst 150 postlådor. Om du försöker migrera fler kan du få slut på tid för att överföra alla postlådor före deadline, och din IT-supportpersonal kan bli överväldigad av förfrågningar för att hjälpa användarna att konfigurera om Outlook.
  
Om du funderar på att göra en cutover-migrering finns det några saker att tänka på:
  
- Microsoft 365 måste du ansluta till dina Exchange 2007-servrar med hjälp Outlook Allt över TCP-port 443.
    
- Alla lokala postlådor flyttas till den Microsoft 365.
    
- Du behöver ett lokalt administratörskonto med läsbehörighet till användarnas postlådor.
    
- De Exchange godkända domäner från 2007 som du vill använda i Microsoft 365 måste läggas till som verifierade domäner i tjänsten.
    
- Från det att du startar migreringen tills du påbörjar kompletteringsfasen kommer Microsoft 365 med jämna mellanrum att synkronisera Microsoft 365 postlådorna och de lokala postlådorna. På så sätt kan du utföra migreringen utan att behöva oroa dig för att e-post ska bli kvar i dina lokala postlådor.
    
- Användarna får nya tillfälliga lösenord för sina Microsoft 365 konton. De måste ändra sitt lösenord när de loggar in på postlådan för första gången.
    
- Du behöver en licens för Microsoft 365 innehåller en Exchange Online för varje användarpostlåda som du migrerar.
    
- Användarna måste konfigurera en ny profil Outlook sina enheter och ladda ned sin e-post igen. Mängden e-Outlook kan variera. Mer information finns i Ändra [hur mycket e-post som ska behållas offline.](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)
    
Mer information om cutover-migrering finns i:
  
- [Vad du behöver veta om en e-postmigrering med försent tid](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [Utföra en cutover-migrering av e-post](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>Stegvis migrering

I en genomförd migrering har du några hundra eller ett par tusen postlådor som du vill migrera till Microsoft 365, behöver en vecka eller mer för att slutföra migreringen och inte behöver några avancerade hybridmigreringsfunktioner som delad kalenderinformation om ledig/upptagen.
  
En sådan migrering är bra för organisationer som behöver mer tid för att migrera sina postlådor till Microsoft 365 men fortfarande planerar att slutföra migreringen inom några veckor. Du kan migrera postlådor i grupper. Du styr hur många och vilka postlådor som migreras vid en viss tidpunkt. Du kanske grupperar postlådor för användare på samma avdelning för att vara säker på att alla flyttas samtidigt. Eller så kanske du vill vänta med chefpostlådorna till den sista batchen. Precis som vid en cutover-migrering måste användarna återskapa sina Outlook profiler.
  
Om du funderar på att göra en sådan här migrering finns det några saker att tänka på:
  
- Microsoft 365 måste du ansluta till dina Exchange 2007-servrar med hjälp av Outlook Anywhere över TCP-port 443.
    
- Du behöver ett lokalt administratörskonto med läsbehörighet till användarnas postlådor.
    
- De godkända Exchange 2007 som du planerar att använda i Microsoft 365 måste läggas till som verifierade domäner i tjänsten.
    
- Du måste skapa en CSV-fil med det fullständiga namnet och e-postadressen för varje postlåda som du planerar att migrera i en batch. Du måste också lägga till ett nytt lösenord för varje postlåda som du migrerar, och skicka lösenordet till alla användare. Användaren uppmanas att ändra lösenord första gången de loggar in på sin nya e-Microsoft 365 postlåda.
    
- Från det att du startar migreringsbatchen tills du påbörjar kompletteringsfasen kommer Microsoft 365 med jämna mellanrum att synkronisera Microsoft 365-postlådorna och de lokala postlådorna som ingår i batchen. På så sätt kan du utföra migreringen utan att behöva oroa dig för att e-post ska bli kvar i dina lokala postlådor.
    
- Du behöver en licens för Microsoft 365 innehåller en Exchange Online för varje användarpostlåda som du migrerar.
    
- Användarna måste konfigurera en ny profil Outlook sina enheter och ladda ned sin e-post igen. Mängden e-Outlook kan variera. Mer information finns i Ändra [hur mycket e-post som ska behållas offline.](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)
    
Mer information om stegad migrering finns i:
  
- [Vad du behöver veta om en sådan e-postmigrering](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [Utföra en stegad migrering av e-post](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>Fullständig hybrid

Under en fullständig hybridmigrering har organisationen många hundra eller tio tusentals postlådor och du vill flytta vissa av dem eller alla till Microsoft 365. Eftersom dessa migreringar i regel är mer långsiktiga gör hybridmigreringarna det möjligt att:
  
- Visa lokala användare kalenderinformation om ledig/upptagen för användarna i Microsoft 365 och tvärtom.
    
- Visa en enhetlig global adresslista som innehåller mottagare både lokalt och i Microsoft 365.
    
- Visa fullständiga Outlook för alla användare, oavsett om de är lokala eller i Microsoft 365.
    
- Skydda e-postkommunikationen mellan lokala Exchange och e Microsoft 365 med TLS och certifikat.
    
- Behandla meddelanden som skickas mellan lokala Exchange och Microsoft 365 som interna, så att de kan:
    
  - Utvärderas och bearbetas på rätt sätt av transport- och efterlevnadsagenter som är inriktade på interna meddelanden.
    
  - Kringgå skräppostfilter.
    
Fullständig hybridmigrering är bäst för organisationer som förväntar sig att ha en hybridkonfiguration under flera månader eller ännu längre. Du får de funktioner som beskrivs tidigare i det här avsnittet plus katalogsynkronisering, bättre integrerade efterlevnadsfunktioner och möjligheten att flytta postlådor till och från Microsoft 365 med hjälp av flyttningar av postlådor online. Microsoft 365 blir ett tillägg till din lokala organisation.
  
Om du funderar på att göra en fullständig hybridmigrering finns det några saker att tänka på:
  
- Fullständig hybridmigrering är inte passar för alla typer av organisationer. På grund av komplexiteten hos fullständiga hybridmigreringar ser i regel inte organisationer med färre än några hundra postlådor några fördelar med en fullständig hybridmigrering som gör det möjligt att skapa en sådan. Om det här låter som din organisation rekommenderar vi att du i stället överväger en cutover- eller stegmigrering.
    
- Du måste distribuera minst en Exchange 2013-server i din Exchange 2007-organisation för att fungera som "hybridserver". Den här servern kommunicerar Microsoft 365 åt dina Exchange 2007-servrar.
    
- Microsoft 365 måste du ansluta till "hybridservern" med hjälp Outlook Över TCP-port 443.
    
- Du måste konfigurera katalogsynkronisering med hjälp av Azure Active Directory (Azure AD) Anslut mellan dina lokala Active Directory-servrar och Microsoft 365.
    
- Användarna kan logga in på sin e Microsoft 365 postlåda med samma användarnamn och lösenord som när de loggar in på det lokala nätverket. (Den här funktionen kräver Azure AD Anslut med lösenordssynkronisering och/eller Active Directory Federation Services.)
    
- Du behöver en licens för Microsoft 365 innehåller en Exchange Online för varje användarpostlåda som du migrerar.
    
- Användarna behöver inte konfigurera en ny profil Outlook sina enheter, men vissa äldre Android-telefoner kan behöva en ny profil. Användarna behöver inte ladda ned sin e-post på nytt.
    
Om fullständig hybridmigrering låter rätt för dig kan du få hjälp med migreringen i följande resurser:
  
- [Exchange Distributionsassistenten](/exchange/exchange-deployment-assistant)
    
- [Exchange Server Hybriddistributioner](/exchange/exchange-hybrid)
    
- [Hybridkonfigurationsguiden](/exchange/hybrid-configuration-wizard)
    
- [Vanliga frågor och svar om hybridkonfigurationsguiden](/exchange/hybrid-configuration-wizard-faqs)
    
- [Förutsättningar för hybriddistribution](/exchange/hybrid-deployment-prerequisites)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>Migrera till en nyare version av Exchange Server

Vi tror att du får ut mer och en bättre upplevelse genom att migrera till Microsoft 365. Men vi förstår också att vissa organisationer måste ha sin e-post lokalt. Detta kan vara på grund av lagstadgade krav, för att garantera att data inte lagras i ett datacenter i ett annat land eller liknande. Om du väljer att behålla din lokala e-post kan du migrera din Exchange 2007-miljö till Exchange 2010, Exchange 2013 eller Exchange 2016.
  
Om du inte kan migrera till Microsoft 365 rekommenderar vi att du migrerar till Exchange 2016. Exchange 2016 innehåller alla funktioner i tidigare versioner av Exchange. Det motsvarar också bäst den upplevelse som finns med Microsoft 365, även om vissa funktioner endast är tillgängliga i Microsoft 365. Ta bara en titta på några av de saker som du har missat:
  
|**Exchange version**|**Funktioner**|
|:-----|:-----|
|Exchange 2010  <br/> | Role-Based (behörigheter utan åtkomstkontrollistor)  <br/>  Outlook Web App postlådeprinciper  <br/>  Möjlighet att dela ledig/upptagen och att delegera kalendrar mellan organisationer  <br/> |
|Exchange 2013  <br/> | *Funktioner från Exchange 2010 och ...*  <br/>  Förenklad arkitektur som minskade antalet serverroller till tre (postlåda, klientåtkomst, gränstransport)  <br/>  Principer för dataförlustskydd som hjälper till att förhindra att känslig information läcker ut  <br/>  Förbättrad Outlook Web App upplevelse  <br/> |
|Exchange 2016  <br/> | *Funktioner från Exchange 2013 och ...*  <br/>  Ytterligare förenklade serverroller till bara postlåda och gränstransport  <br/>  Förbättrad DLP tillsammans med integrering med SharePoint  <br/>  Förbättrad motståndskraft hos databaser  <br/>  Dokumentsamarbete online |
   
#### <a name="which-version-should-i-migrate-to"></a>Vilken version bör jag migrera till?

Vi rekommenderar att du först utgår ifrån att du bör migrera till Exchange 2016. Använd sedan följande information för att bekräfta ditt antagande eller för att utesluta Exchange 2016. Om du av någon anledning inte kan migrera till Exchange 2016 gör du samma process med Exchange 2013 och så vidare.
  
|**Att tänka på**|**Mer information**|
|:-----|:-----|
|Supportdatum avslutas  <br/> | Precis som Exchange 2007 har varje version Exchange sitt eget supportdatum:  <br/> *Exchange 2010* – januari 2020  <br/> *Exchange 2013–* april 2023  <br/> *Exchange 2016* – oktober 2025  <br/>  Ju tidigare supporten upphöra, desto tidigare måste du utföra ytterligare en migrering.<br/> |
|Migreringsväg till Exchange 2010 och 2013.  <br/> |Här är de allmänna faserna för migrering till Exchange 2010 Exchange 2013:  <br/> – installera Exchange 2010 eller 2013 i din befintliga Exchange 2007-organisation. <br/>– Flytta tjänster och annan infrastruktur till Exchange 2010 eller 2013.<br/>– Flytta postlådor och gemensamma mappar till Exchange 2010 eller 2013.<br/>- Inaktivera återstående Exchange 2007-servrar. |
|Migreringsväg till Exchange 2016  <br/> |Här är de allmänna faserna för migrering till Exchange 2016:  <br/> – installera Exchange 2013 i din befintliga Exchange 2007-organisation.<br/>– Flytta tjänster och annan infrastruktur till Exchange 2013.<br/>– Flytta postlådor och gemensamma mappar till Exchange 2013.<br/>- Inaktivera återstående Exchange 2007-servrar.<br/>– installera Exchange 2016 i din befintliga Exchange 2013-organisation.<br/>- Flytta postlådor, gemensamma mappar, tjänster och annan infrastruktur till Exchange 2016 (ordningen spelar ingen roll). Inaktivera återstående Exchange 2013-servrar.<br/><br/> **Obs!** Det är enkelt att Exchange från 2013 Exchange 2016. De två versionerna har nästan samma maskinvarukrav och de här versionerna är mycket kompatibla. Så att du kan återskapa en server som du har köpt Exchange 2013 och installera Exchange 2016 på den. Vid flytt av onlinepostlådor märker de flesta användare inte ens att deras postlåda har flyttats från servern och sedan tillbaka när du återskapat den med Exchange 2016.           |
|Versionsexistens  <br/> | Vid migrering till ...  <br/> **Exchange 2016:** Exchange 2016 kan inte installeras i en organisation som innehåller en Exchange 2007-server. Du måste först migrera till Exchange 2010 eller 2013 (vi rekommenderar Exchange 2013), ta bort alla Exchange 2007-servrar och sedan migrera till Exchange 2016.  <br/> **Exchange 2010 eller Exchange 2013:** Du kan installera Exchange 2010 eller Exchange 2013 i en befintlig Exchange 2007-organisation. På så sätt kan du installera en eller flera Exchange 2010- eller 2013-servrar och utföra migreringen.  <br/> |
|Servermaskinvara  <br/> | Maskinvarukraven för servrar har ändrats från Exchange 2007. Kontrollera att maskinvaran är kompatibel. Mer information finns i:  <br/> [Exchange systemkraven för 2016](/Exchange/plan-and-deploy/system-requirements) <br/> [Exchange systemkrav för 2013](/exchange/exchange-2013-system-requirements-exchange-2013-help) <br/> [Exchange systemkraven för 2010](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141)) <br/>  Du kommer att se de betydande förbättringarna av Exchange-prestanda och den ökade datorkraften och lagringskapaciteten i nyare servrar innebär att du förmodligen behöver färre servrar för att stödja samma antal postlådor.  <br/> |
|Operativsystemsversion  <br/> | De lägsta operativsystemsversionerna som stöds för varje version är:  <br/> **Exchange 2016** – Windows Server 2012  <br/> **Exchange 2013** – Windows Server 2008 R2 SP1  <br/> **Exchange 2010** – Windows Server 2008 SP2  <br/>  Mer information om operativsystemssupport finns på [Exchange supportmatris.](/Exchange/plan-and-deploy/supportability-matrix)  <br/> |
|Active Directory-skogsfunktionsnivån  <br/> | De lägsta funktionsnivåerna för Active Directory-skogar som stöds för varje version är följande:  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  Mer information om support för skogsfunktionsnivån finns på [Exchange supportmatris.](/Exchange/plan-and-deploy/supportability-matrix)  <br/> |
|Office klientversioner  <br/> | Det lägsta antalet Office klientversionerna för varje version är:  <br/> **Exchange 2016** – Office 2010 (med de senaste uppdateringarna)  <br/> **Exchange 2013** – Office 2007 SP3  <br/> **Exchange 2010** – Office 2003  <br/>  Mer information om hur du Office klientsupport finns [Exchange matris med support.](/Exchange/plan-and-deploy/supportability-matrix)  <br/> |
   
#### <a name="how-do-i-migrate"></a>Hur migrerar jag?

Om du har bestämt dig för att behålla din e-post lokalt kan du använda följande resurser för att hjälpa till med migreringen:
  
- [Exchange Distributionsassistenten](/exchange/exchange-deployment-assistant)
    
- Ändringar i Active Directory-schemat Exchange [2016](/Exchange/plan-and-deploy/active-directory/ad-schema-changes), [2013,](/exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help) [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)
    
- Systemkrav för Exchange [2016,](/Exchange/plan-and-deploy/system-requirements) [2013,](/exchange/exchange-2013-system-requirements-exchange-2013-help) [2010](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141))
    
- Krav för Exchange [2016](/Exchange/plan-and-deploy/prerequisites), [2013](/exchange/exchange-2013-prerequisites-exchange-2013-help), [2010](/previous-versions/office/exchange-server-2010/bb691354(v=exchg.141))
    
## <a name="get-help"></a>Få hjälp

Om du migrerar till Microsoft 365 kan du vara berättigad att använda vår Microsoft FastTrack-tjänst. FastTrack ger bästa praxis, verktyg och resurser för att göra din migrering till Microsoft 365 så smidig som möjligt. Bäst av allt är att en supporttekniker går igenom migreringen, från att planera och utforma hela vägen till att migrera den sista postlådan. Mer information om FastTrack finns [i Microsoft FastTrack.](https://fasttrack.microsoft.com/)
  
Om du har problem under migreringen till Microsoft 365 och du inte använder FastTrack, eller under migreringen till en nyare version av Exchange Server, finns vi här för att hjälpa dig. Här är några resurser som du kan använda:
  
- [Teknisk community](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [Kundsupport](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>Relaterade ämnen

[Resurser som hjälper dig att uppgradera dina Office 2007-servrar och -klienter](upgrade-from-office-2007-servers-and-products.md)