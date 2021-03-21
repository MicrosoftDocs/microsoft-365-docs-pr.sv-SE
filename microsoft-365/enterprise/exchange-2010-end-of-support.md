---
title: Exchange 2010 – översikt över slutet av supporten
ms.author: dstrome
author: dstrome
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: e150e7b9-c432-4c8d-a0ae-c11847129a7d
f1.keywords:
- NOCSH
description: Supporten för Exchange 2010 har nu gått ut. Använd den här planeringsöversikten för att förbereda uppgraderingen till Exchange Online eller en nyare version av Exchange Server lokalt.
ms.openlocfilehash: f3531802283368e533ba6646415d4acc019687bd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927000"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Exchange 2010 – översikt över slutet av supporten

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Supporten för Exchange Server 2010 tog slut **den 13 oktober 2020.** Om du inte redan påbörjat migreringen från Exchange 2010 till Microsoft 365, Office 365 eller Exchange 2016 är det dags att börja planera.

## <a name="what-does-end-of-support-mean"></a>Vad innebär *slutet av supporten?*

De flesta Microsoft-produkter har en supportlivscykel under vilken de får nya funktioner, programkorrigeringar, säkerhetskorrigeringar och så vidare. En livscykel varar vanligtvis i tio år från produktens första version. Slutet av perioden kallas för slutet av supporten för produkten. Eftersom supporten för Exchange 2010 tog slut den 13 oktober 2020 tillhandahåller Microsoft inte längre:

- Teknisk support för problem som kan uppstå.
- Programkorrigeringar för problem som kan påverka servrars stabilitet och användbarhet.
- Säkerhetskorrigeringar för säkerhetsproblem som kan göra servern sårbar för säkerhetsbrister.
- Tidszonsuppdateringar.

Din installation av Exchange 2010 fortsätter att köras efter detta datum. På grund av ändringarna ovan rekommenderar vi dock starkt att du migrerar från Exchange 2010 så snart som möjligt.

Mer information om hur du närmar dig slutet av supporten finns i Resurser som hjälper dig att uppgradera från [Office 2010-servrar och -klienter.](upgrade-from-office-2010-servers-and-products.md)

## <a name="what-are-my-options"></a>Vilka alternativ har jag?

Det är ett bra tillfälle att utforska dina alternativ och förbereda en migreringsplan. Du kan:

- Migrera helt till Microsoft 365. Migrera postlådor med hjälp av minimal hybridmigrering eller fullständig hybridmigrering. Ta sedan bort lokala Exchange-servrar och Active Directory.
- Migrera dina Exchange 2010-servrar till Exchange 2016 på dina lokala servrar.

> [!IMPORTANT]
> Om din organisation väljer att migrera postlådor till Microsoft 365 men planerar att behålla DirSync eller Azure AD Connect för att fortsätta att hantera användarkonton från lokalt Active Directory måste du ha minst en Microsoft Exchange-server lokalt. Om du tar bort alla Exchange-servrar kan du inte göra ändringar för Exchange-mottagare i Exchange Online eftersom källan till behörighet finns kvar i din lokala Active Directory. Ändringar måste göras där. I det här scenariot har du följande alternativ:
>
>- *Rekommenderas:* Om du har migrerat dina postlådor till Microsoft 365 och uppgraderat dina servrar senast den 13 oktober 2020 ska du använda Exchange 2010 för att ansluta till Microsoft 365 och migrera postlådor. Migrera sedan Exchange 2010 till Exchange 2016 och inaktivera eventuella återstående Exchange 2010-servrar.
>- Om du inte slutförde postlådemigreringen och den lokala serveruppgraderingen senast den 13 oktober 2020 uppgraderar du först dina lokala Exchange 2010-servrar till Exchange 2016. Använd sedan Exchange 2016 för att ansluta till Microsoft 365 och migrera postlådor.

> [!NOTE]
> Det är lite mer komplicerat, men du kan också migrera postlådor till Microsoft 365 medan du migrerar dina lokala Exchange 2010-servrar till Exchange 2016.

Här är de tre sätt du kan gå till för att undvika att supporten för Exchange Server 2010 tar slut.

![Uppgraderingsvägar för Exchange Server 2010](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

I följande avsnitt utforskar vi de olika alternativen i detalj.

## <a name="migrate-to-microsoft-365"></a>Migrera till Microsoft 365

Att migrera din e-post till Microsoft 365 är det bästa och enklaste alternativet för att dra tillbaka din Exchange 2010-distribution. Med en migrering till Microsoft 365 kan du ta ett enkelt hopp från gammal teknik till aktuella funktioner, till exempel:

- Efterlevnadsfunktioner, till exempel bevarandeprinciper, In-Place bevarande av juridiska skäl, på plats för eDiscovery och mycket mer.
- Microsoft Teams.
- Power BI.
- Prioriterad inkorg.
- MyAnalytics.

Microsoft 365 är också först med att få nya funktioner och upplevelser, så att din organisation kan börja använda dem direkt. Du behöver inte heller tänka på följande:

- Köpa och underhålla maskinvara.
- Betala för att få värme och värm servrarna.
- Hålla dig uppdaterad om säkerhets-, produkt- och tidszonskorrigeringar.
- Underhålla lagring och programvara för att uppfylla efterlevnadskraven.
- Uppgradera till en ny version av Exchange. Du har alltid den senaste versionen av Exchange i Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>Hur ska jag migrera till Microsoft 365?

Beroende på din organisation finns det några alternativ för att komma åt Microsoft 365. Först måste du tänka på några saker, till exempel:
- Antalet platser eller postlådor som du behöver flytta.
- Hur länge du vill att migreringen ska pågå.
- Oavsett om du behöver en smidig integrering mellan din lokala installation och Microsoft 365 under migreringen.
 
I den här tabellen visas migreringsalternativen och de viktigaste faktorerna som avgör vilken metod du bör använda.

|Migreringsalternativ|Organisationens storlek|Varaktighet|
|---|---|---|
|Snabb migrering|Färre än 150 platser|En vecka eller mindre|
|Minimal hybridmigrering|Färre än 150 platser|Några veckor eller mindre|
|Fullständig hybridmigrering|Fler än 150 platser|Ett par veckor eller mer|

I följande avsnitt får du en översikt över de här metoderna. Mer information finns i [Bestämma en migreringsväg](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27).

### <a name="cutover-migration"></a>Snabb migrering

Vid en cutover-migrering kan du migrera alla dina postlådor, distributionsgrupper, kontakter och så vidare till Office 365 vid ett fast datum och tid. När du är klar stänger du av dina lokala Exchange-servrar och börjar använda Microsoft 365 exklusivt.

Snabb migrering är perfekt för små organisationer som inte har många postlådor, som snabbt vill komma åt Microsoft 365 och inte vill hantera komplexiteten med de andra metoderna. Men den bör vara klar om en vecka eller mindre. Och det kräver att användarna konfigurerar om sina Outlook-profiler. En migrering kan migrera upp till 2 000 postlådor, men vi rekommenderar att du använder den till högst 150. Om du försöker migrera fler kan du få slut på tid för att överföra alla postlådor före deadline, och din IT-supportpersonal kan bli överväldigad av förfrågningar för att hjälpa användarna att konfigurera om Outlook.

Här är några saker att tänka på när du migrerar:

- Microsoft 365 måste ansluta till dina Exchange 2010-servrar med hjälp av Outlook Anywhere över TCP-port 443.
- Alla lokala postlådor flyttas till Microsoft 365.
- Du behöver ett lokalt administratörskonto med läsbehörighet till användarnas postlådor.
- De godkända domäner för Exchange 2010 som du vill använda i Microsoft 365 måste läggas till som verifierade domäner i tjänsten.
- Från det att du startar migreringen tills du påbörjar kompletteringsfasen kommer Microsoft 365 med jämna mellanrum att synkronisera Microsoft 365-postlådorna och de lokala postlådorna. På så sätt kan du utföra migreringen utan att behöva oroa dig för att e-post ska bli kvar i dina lokala postlådor.
- Användarna får nya tillfälliga lösenord för sina Microsoft 365-konton. De måste ändra dem när de loggar in på sina postlådor för första gången.
- Du behöver en Microsoft 365-licens som innehåller Exchange Online för varje användarpostlåda som du migrerar.
- Användarna måste konfigurera en ny Outlook-profil på var och en av sina enheter och ladda ned sin e-post igen. Mängden e-post som Outlook laddar ned kan variera. Mer information finns i [Arbeta offline i Outlook](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

Mer information om cutover-migrering finns i:

- [Vad du behöver veta om en e-postmigrering med försent tid](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Utföra en cutover-migrering av e-post till Office 365](/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Minimal hybridmigrering

I en minimal hybridmigrering, eller expressmigrering, flyttar du några hundra postlådor till Microsoft 365 under några veckor. Den här metoden stöder inte avancerade hybridmigreringsfunktioner som delad kalenderinformation om ledig/upptagen tid.

Minimal hybridmigrering är bra för organisationer som behöver mer tid till att migrera sina postlådor till Microsoft 365, men fortfarande planerar att slutföra migreringen inom några veckor. Du får några av fördelarna med en mer avancerad *fullständig hybridmigrering* utan mycket av komplexiteten. Du kan styra hur många och vilka postlådor som ska migreras vid en viss tidpunkt. Microsoft 365-postlådor skapas med användarnamn och lösenord för de lokala kontona. Och till skillnad från en cutover-migrering behöver användarna inte återskapa sina Outlook-profiler.

Här är några saker att tänka på när det gäller minimal hybridmigrering:

- Du behöver göra en enda gång för katalogsynkronisering mellan dina lokala Active Directory-servrar och Microsoft 365.
- Användare kan logga in på sin Microsoft 365-postlåda med samma användarnamn och lösenord som innan postlådan.
- Du behöver en Microsoft 365-licens som innehåller Exchange Online för varje användarpostlåda som du migrerar.
- Användarna behöver inte konfigurera en ny Outlook-profil på de flesta av sina enheter, men vissa äldre Android-telefoner kan behöva en ny profil. Användarna behöver inte ladda ned sin e-post på nytt.

Mer information finns i Använda [minimal hybrid för att snabbt migrera Exchange-postlådor till Office 365.](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)

### <a name="full-hybrid"></a>Fullständig hybrid

I en fullständig hybridmigrering har du många hundra, upp till tio tusentals postlådor och du flyttar några av dem eller alla till Microsoft 365. Eftersom dessa migreringar i regel är mer långsiktiga gör hybridmigreringarna det möjligt att:

- Visa lokala användare kalenderinformation om ledig/upptagen för användare i Microsoft 365, och vice versa.
- Visa en enhetlig global adresslista som innehåller mottagare både lokalt och i Microsoft 365.
- Visa fullständiga egenskaper för Outlook-mottagare för alla användare, oavsett om de finns lokalt eller i Microsoft 365.
- Skydda e-postkommunikationen mellan lokala Exchange-servrar och Office 365 med TLS och certifikat.
- Behandla meddelanden som skickas mellan lokala Exchange-servrar och Microsoft 365 som interna, så att de kan:
  - Utvärderas och bearbetas på rätt sätt av transport- och efterlevnadsagenter som är inriktade på interna meddelanden.
  - Kringgå skräppostfilter.

Fullständiga hybridmigreringar är bäst för organisationer som förväntar sig att ha en hybridkonfiguration under flera månader eller ännu längre. Du får de funktioner som beskrivs tidigare i det här avsnittet plus katalogsynkronisering, bättre integrerade efterlevnadsfunktioner och möjligheten att flytta postlådor till och från Microsoft 365 med hjälp av flyttningar av postlådor online. Microsoft 365 blir ett tillägg till din lokala organisation.

Saker att tänka på om fullständig hybridmigrering:

- De är inte lämpliga för alla organisationer. På grund av komplexiteten hos fullständiga hybridmigreringar ser i regel inte organisationer med färre än några hundra postlådor några fördelar med en fullständig hybridmigrering som marginaljusterar arbetet och kostnaden. I sådana fall rekommenderar vi att du i stället överväger en kort eller minimal hybridmigrering.
- Du måste konfigurera katalogsynkronisering med hjälp av Azure Active Directory (Azure AD) Anslut mellan dina lokala Active Directory-servrar och Microsoft 365.
- Användare kan logga in på sin Microsoft 365-postlåda med samma användarnamn och lösenord som de använder när de loggar in på det lokala nätverket. (Den här funktionen kräver Azure AD Connect med lösenordssynkronisering och/eller Active Directory Federation Services).
- Du behöver en Microsoft 365-licens som innehåller Exchange Online för varje användarpostlåda som du migrerar.
- Användarna behöver inte konfigurera en ny Outlook-profil på de flesta av sina enheter, även om vissa äldre Android-telefoner kan behöva en ny profil. Användarna behöver inte ladda ned sin e-post på nytt.

> [!IMPORTANT]
> Om din organisation väljer att migrera postlådor till Microsoft 365 men planerar att behålla DirSync eller Azure AD Connect för att fortsätta att hantera användarkonton från lokal Active Directory måste du ha minst en Exchange-server lokalt. Om alla Exchange-servrar tas bort kan du inte göra ändringar för Exchange-mottagare i Exchange Online. Det beror på att källan till behörigheten finns kvar i din lokala Active Directory och ändringar måste göras där.

Om en fullständig hybridmigrering låter rätt för dig kan du se följande användbara resurser:

- [Distributionsassistenten för Exchange](/exchange/exchange-deployment-assistant)
- [Exchange Server-hybriddistributioner](/exchange/exchange-hybrid)
- [Hybridkonfigurationsguiden](/exchange/hybrid-configuration-wizard)
- [Vanliga frågor och svar om hybridkonfigurationsguiden](/exchange/hybrid-configuration-wizard-faqs)
- [Förutsättningar för hybriddistribution](/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Uppgradera till en nyare version av Exchange Server lokalt

Vi tror starkt att du får ut mer och en bättre upplevelse genom att migrera helt till Microsoft 365. Men vi förstår att vissa organisationer måste ha vissa Exchange-servrar lokalt. Detta kan vara på grund av lagstadgade krav, för att garantera att data inte lagras i ett utländskt datacenter, eftersom du har unika inställningar eller krav som inte kan uppfyllas i molnet, eller för att du behöver Exchange för att hantera molnbaserade postlådor eftersom du fortfarande använder Active Directory lokalt. Om du har Exchange lokalt bör du i alla fall se till att Exchange 2010-miljön uppgraderas till minst Exchange 2013 eller Exchange 2016.

För bästa upplevelse rekommenderar vi att du uppgraderar din återstående lokala miljö till Exchange 2016. Du behöver inte installera Exchange Server 2013 om du vill gå direkt från Exchange Server 2010 till Exchange Server 2016.

Exchange 2016 innehåller alla funktioner från tidigare versioner av Exchange. Det motsvarar bäst den upplevelse som är tillgänglig med Microsoft 365, även om vissa funktioner endast är tillgängliga i Microsoft 365. Ta bara en titta på några av de saker som du har missat:

|Exchange-version|Funktioner|
|---|---|
|**Exchange 2013**|Förenklad arkitektur minskar antalet serverroller till tre (postlåda, klientåtkomst, gränstransport)|
||Principer för dataförlustskydd som hjälper till att förhindra att känslig information läcker ut|
||Förbättrad Outlook Web App-upplevelse|
|**Exchange 2016**|*Funktioner från Exchange 2013 och ...*|
||Ytterligare förenklade serverroller till bara postlåda och gränstransport|
||Förbättrad DLP tillsammans med integrering med SharePoint|
||Förbättrad motståndskraft hos databaser|
||Dokumentsamarbete online|

|Att beakta|Mer information|
|---|---|
|Supportdatum avslutas|Precis som Exchange 2010 har varje version av Exchange sitt eget supportdatum för support:<br/><br/>Exchange 2013 – april 2023<br/>Exchange 2016 – oktober 2025<br/><br/>Ju tidigare supportdatumet för slutet av supporten in desto tidigare måste du utföra ytterligare en migrering. April 2023 är mycket närmare i tid än du tror!|
|Migreringsväg till Exchange 2013 eller 2016|Migreringsvägen från Exchange 2010 till en nyare version är densamma oavsett om du väljer Exchange 2013 eller Exchange 2016:<br/><br/>Installera Exchange 2013 eller 2016 i din befintliga Exchange 2010-organisation.<br/>Flytta tjänster och annan infrastruktur till Exchange 2013 eller 2016.<br/>Flytta postlådor och gemensamma mappar till Exchange 2013 eller 2016 Inaktivera återstående Exchange 2010-servrar.|
|Versionsexistens|När du migrerar till Exchange 2013 eller Exchange 2016 kan du installera båda versionerna i en befintlig Exchange 2010-organisation. På så sätt kan du installera en eller flera Exchange 2013- eller Exchange 2016-servrar och göra migreringen.|
|Servermaskinvara|Maskinvarukraven för servrar har ändrats från Exchange 2010. Kontrollera att maskinvaran är kompatibel. Mer information om maskinvarukraven för varje version finns här:<br/><br/>[Systemkrav för Exchange 2016](/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016)<br/>[Systemkrav för Exchange 2013](/Exchange/exchange-2013-system-requirements-exchange-2013-help)<br/><br/>Med de betydande förbättringarna av Exchange-prestandan och den ökade datorkraften och lagringskapaciteten i nyare servrar behöver du förmodligen färre servrar för att stödja samma antal postlådor.|
|Operativsystemsversion|De lägsta operativsystemsversionerna som stöds för varje version är:<br/><br/>Exchange 2016 – Windows Server 2012<br/>Exchange 2013 – Windows Server 2008 R2 SP1<br/><br/>Mer information om operativsystemssupport finns i Supportmatris [för Exchange.](/exchange/plan-and-deploy/supportability-matrix)|
|Active Directory-skogsfunktionsnivån|De lägsta funktionsnivåerna för Active Directory-skogar som stöds för varje version är följande:<br/><br/>Exchange 2016 – Windows Server 2008 R2 SP1<br/>Exchange 2013 – Windows Server 2003<br/><br/>Mer information om support för skogsfunktionsnivån finns i Supportmatris [för Exchange.](/exchange/plan-and-deploy/supportability-matrix)|
|Office-klientversioner|De lägsta Office-klientversionerna som stöds för varje version är:<br/><br/>Exchange 2016 – Office 2010 (med de senaste uppdateringarna)<br/>Exchange 2013 – Office 2007 SP3<br/><br/>Mer information om Office-klientsupport finns i [Supportmatris för Exchange.](/exchange/plan-and-deploy/supportability-matrix)||| 


Använd följande resurser för att hjälpa dig med migreringen:

- [Distributionsassistenten för Exchange](/exchange/exchange-deployment-assistant)
- Ändringar i Active Directory-schemat för Exchange [2016](/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016), [2013](/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- Systemkrav för Exchange [2016](/exchange/plan-and-deploy/system-requirements?view=exchserver-2016), [2013](/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Krav för Exchange [2016](/exchange/plan-and-deploy/prerequisites?view=exchserver-2016), [2013](/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Sammanfattning av alternativ för Office 2010 klient och servrar och Windows 7

En visuell sammanfattning av alternativen för uppgradering, migrering och flytt till molnet för Office 2010-klienter och -servrar och Windows 7 finns på [supportaffischens](../downloads/Office2010Windows7EndOfSupport.pdf)slut.

[![Supporten för Office 2010-klienter och -servrar och affischen för Windows 7 har upphöra](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Den här affischen på en sida illustrerar de olika sätt du kan ta för att svara på Office 2010-klient- och serverprodukter och när supporten för Windows 7 tar slut, med föredragen väg och alternativsupport i Microsoft 365 Enterprise markerat.

Du kan också [ladda ned](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) den här affischen och skriva ut den i letter-, legal- eller tabloidformat (11 x 17).

## <a name="what-if-i-need-help"></a>Vad gör jag om jag behöver hjälp?

Om du migrerar till Microsoft 365 kanske du är berättigad att använda vår Microsoft FastTrack-tjänst. FastTrack ger bästa praxis, verktyg och resurser för att göra din migrering till Microsoft 365 så smidig som möjligt. Bäst av allt är att du har en supporttekniker som går igenom allt från planering och design till migrering av din senaste postlåda. Mer information om FastTrack finns [i Microsoft FastTrack.](https://fasttrack.microsoft.com/)

Om du har problem under migreringen till Microsoft 365 och du inte använder FastTrack, eller om du migrerar till en nyare version av Exchange Server, finns det några resurser du kan använda:

- [Teknisk community](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Kundsupport](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>Relaterade artiklar

[Resurser som hjälper dig att uppgradera från Office 2010-servrar och -klienter](upgrade-from-office-2010-servers-and-products.md)