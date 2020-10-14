---
title: Stöd översikt för Exchange 2010
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
description: Exchange 2010 närmar sig Supportens slut. Använd den här planerings översikten som vägledning för att förbereda uppgraderingen till Exchange Online eller en nyare version av Exchange Server lokalt.
ms.openlocfilehash: dbae3fba3ddbff016e0e9434db4af6ca0a046b0d
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464258"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Stöd översikt för Exchange 2010

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Exchange Server 2010 har nått Supportens slut den **13 oktober 2020**. Om du inte redan har börjat migrera från Exchange 2010 till Microsoft 365, Office 365 eller Exchange 2016 är det dags att börja planera.

## <a name="what-does-end-of-support-mean"></a>Vad innebär slut på support?

Exchange Server, till exempel nästan alla Microsoft-produkter, har en support livs cykel under vilken vi tillhandahåller nya funktioner, korrigeringar, säkerhets korrigeringar och så vidare. Denna livs cykel räcker normalt i 10 år från datumet för produktens första utgivning och slutet av den här livs cykeln kallas produkt Supportens slut. Eftersom Exchange 2010 nådde Supportens slut den 13 oktober 2020, ger Microsoft inte längre ut:

- Teknisk support för problem som kan uppstå.
- Program korrigeringar för problem som upptäcks och som kan påverka serverns stabilitet och användbarhet.
- Säkerhets korrigeringar för säkerhets problem som upptäcks och som kan göra servern sårbar för säkerhets brott.
- Tids zons uppdateringar.

Din installation av Exchange 2010 fortsätter att köras efter detta datum. Därför rekommenderar vi att du migrerar från Exchange 2010 så snart som möjligt.

Mer information om Office 2010-servrar med nära Supportens slut finns i [resurser som hjälper dig att uppgradera från Office 2010-servrar och-klienter](upgrade-from-office-2010-servers-and-products.md).

## <a name="what-are-my-options"></a>Vilka alternativ har jag?

Med Exchange 2010 med att nå Supportens slut är det bra att utforska dina alternativ och förbereda ett abonnemang. Du kan:

- Migrera helt till Microsoft 365. Migrera post lådor med snabbmigrering, minimal hybrid eller fullständig hybrid migrering och ta sedan bort lokala Exchange-servrar och Active Directory.
- Migrera dina Exchange 2010-servrar till Exchange 2016 på dina lokala servrar.

> [!IMPORTANT]
> Om din organisation väljer att migrera post lådor till Microsoft 365, men om du vill fortsätta att ha DirSync eller Azure AD Connect-ansluta på plats för att hantera användar konton från lokala Active Directory måste du ha minst en Exchange-Server lokalt. Om den senaste Exchange-servern tas bort kan du inte ändra Exchange-mottagarna i Exchange Online. Detta beror på att källan till auktoritet kvarstår i din lokala Active Directory och ändringar måste göras där. I det här scenariot har du följande alternativ:

- (**Rekommenderas**) Om du kan migrera dina post lådor till Microsoft 365 och uppgradera dina servrar senast den 13 oktober 2020 kan du använda Exchange 2010 för att ansluta till Microsoft 365 och migrera post lådor. Migrera sedan Exchange 2010 till Exchange 2016 och inaktivera alla återstående Exchange 2010-servrar.
- Om du inte kunde slutföra migrering av post lådor och lokal server uppgradering senast den 13 oktober 2020 uppgraderar du först den lokala Exchange 2010-servern till Exchange 2016 och sedan använder du Exchange 2016 för att ansluta till Microsoft 365 och migrera post lådor.

> [!NOTE]
> Men lite mer komplicerat kan du även migrera post lådor till Microsoft 365 när du migrerar dina lokala Exchange 2010-servrar till Exchange 2016.

Här är de tre vägarna som du kan vidta för att undvika slut på stöd för Exchange Server 2010.

![Uppgraderings vägar för Exchange Server 2010](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

I följande avsnitt förklaras alla alternativ i detalj.

## <a name="migrate-to-microsoft-365"></a>Migrera till Microsoft 365

Migrering av e-post till Microsoft 365 är ditt bästa och enklaste alternativ för att hjälpa dig att ta bort din Exchange 2010-distribution. Med en migrering till Microsoft 365 kan du skapa ett enkelt hopp från gammal teknik till de här funktionerna, till exempel:

- Funktioner för efterlevnad, som bevarande principer, In-Place och rättsliga undantag, pågående eDiscovery och mycket mer.
- Microsoft Teams
- Power BI
- Prioriterad inkorg
- MyAnalytics

Microsoft 365 får också nya funktioner först och du och användarna kan vanligt vis börja använda dem direkt. Förutom nya funktioner behöver du inte oroa dig för:

- Köpa och underhålla maskin vara.
- Betala för uppvärmning och kylning av dina servrar.
- Hålla dig uppdaterad om säkerhets-, produkt-och tids zons korrigeringar
- Bevara lagring och program vara för att stödja efterföljandekrav
- Uppgradera till en ny version av Exchange – du får alltid den senaste versionen av Exchange i Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>Hur ska jag migrera till Microsoft 365?

Beroende på din organisation har du några alternativ som hjälper dig att komma till Microsoft 365. När du väljer ett alternativ för migrering måste du fundera på några saker, till exempel hur många säten eller post lådor du behöver flytta, hur länge du vill ha migreringen och om du behöver en sömlös integrering mellan din lokala installation och Microsoft 365 under migreringen. Den här tabellen visar dina migreringsåtgärder och de viktigaste faktorer som avgör vilken metod som ska användas.

|Flyttnings alternativ|Organisationens storlek|Repetition|
|---|---|---|
|Snabb migrering|Färre än 150 platser|En vecka eller mindre|
|Minimal hybrid migration|Färre än 150 platser|Några veckor eller färre|
|Fullständig hybrid migration|Fler än 150 platser|Några veckor eller mer|

I följande avsnitt får du en översikt över de här metoderna. Ta [en titt på](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27) om du vill veta mer om varje metod.

### <a name="cutover-migration"></a>Snabb migrering

En snabbmigrering-migrering är en plats där du vid ett förvalt datum och tid migrerar alla dina post lådor, distributions grupper, kontakter o.s.v. till Office 365. När du är klar stänger du av dina lokala Exchange-servrar och börjar använda Microsoft 365 exklusivt.

Snabbmigrering är perfekt för små organisationer som inte har mycket många post lådor, och som inte vill komma till Microsoft 365 snabbt och inte att hantera vissa av de andra metoderna. Men det är också lite begränsat eftersom det bör genomföras i en vecka eller mindre och eftersom det kräver att användare konfigurerar om sina Outlook-profiler. När snabbmigrering migration kan hantera upp till 2 000-postlådor rekommenderar vi starkt att du migrerar maximalt 150-postlådor med den här metoden. Om du försöker migrera fler än 150 post lådor kan du få slut på tid att överföra alla post lådor före din tids gräns och din IT-supportavdelning kan bli mer utsatt för att hjälpa användarna att konfigurera om Outlook.

Om du funderar på att göra en snabbmigrering migrering är det några saker du bör tänka på:

- Microsoft 365 måste ansluta till dina Exchange 2010-servrar med hjälp av Outlook överallt via TCP-port 443.
- Alla lokala post lådor flyttas till Microsoft 365.
- Du behöver ett lokalt administratörs konto som har behörighet att läsa innehållet i användarnas post lådor.
- Exchange 2010 accepterade domäner som du vill använda i Microsoft 365 måste läggas till som verifierade domäner i tjänsten.
- Mellan den tid som du börjar med migreringen synkroniserar Microsoft 365 regelbundet Microsoft 365-och lokala post lådorna. Då kan du slutföra migreringen utan att oroa dig för att e-post kvars i dina lokala post lådor.
- Användarna får nya tillfälliga lösen ord för Microsoft 365-kontot som de måste ändra när de loggar in på sina post lådor för första gången.
- Du behöver en Microsoft 365-licens som innehåller Exchange Online för varje användar post låda du migrerar.
- Användarna måste konfigurera en ny Outlook-profil på var och en av deras enheter och hämta e-postmeddelandet igen. Hur mycket e-post som kommer att hämtas kan variera. Om du vill ha mer information kan du ta en titt på [arbeta offline i Outlook](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

Om du vill veta mer om snabbmigrering migrering kan du ta en titt på:

- [Det här behöver du veta om en snabbmigrering-e-postmigrering](https://docs.microsoft.com/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Utföra en snabbmigrering migrering av e-post till Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Minimal hybrid migration

En minimal hybrid, eller Express, migrering är ett ställe där du har några hundra post lådor som du vill migrera till Microsoft 365, kan slutföra migreringen inom några veckor, och behöver inte några av de avancerade funktionerna för Hybrid migrering som delat ledig/upptagen kalender information.

Minimal hybrid migration är perfekt för organisationer som behöver ta mer tid att migrera sina post lådor till Microsoft 365, men ändå planera för att slutföra migreringen inom några veckor. Du får några fördelar med den mer avancerade fullständiga hybridens migrering utan många av de komplexa funktionerna. Du kan styra hur många och vilka post lådor som ska migreras vid en given tidpunkt. Microsoft 365-postlådor skapas med användar namnet och lösen ordet till deras lokala konton. Och till skillnad från snabbmigrering-migreringar behöver användarna inte återskapa sina Outlook-profiler.

Om du funderar på att göra minimal hybrid migrering är det några saker du bör tänka på:

- Du måste utföra en synkronisering mellan lokala Active Directory-servrar och Microsoft 365.
- Användare kan logga in i sin Microsoft 365-postlåda med samma användar namn och lösen ord som de använde när deras post låda migrerades.
- Du behöver en Microsoft 365-licens som innehåller Exchange Online för varje användar post låda du migrerar.
- Användarna behöver inte konfigurera en ny Outlook-profil på de flesta enheter (vissa äldre Android-telefoner kan behöva en ny profil) och behöver inte ladda ner sin e-post igen.

Om du vill ha mer information om minimal hybrid migrering kan du ta en titt på [Använd minimal hybrid för att snabbt migrera Exchange-postlådor till Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate).

### <a name="full-hybrid"></a>Fullständig hybrid

En fullständig hybrid migration är en plats där din organisation har många hundra, upp till tusentals avgränsare, och du vill flytta några eller alla av dem till Microsoft 365. Eftersom de här migreringarna normalt är längre tid gör hybrid migrering det möjligt att:

- Visa lokala användare den lediga/upptagna kalender informationen för användare i Microsoft 365 och vice versa.
- Se en Unified Global Address-lista som innehåller mottagare i både lokala och Microsoft 365.
- Visa fullständiga Outlook-egenskaper för mottagare för alla användare, oavsett om de är lokalt eller i Microsoft 365.
- Säker e-postkommunikation mellan lokala Exchange-servrar och Office 365 via TLS och certifikat.
- Behandla meddelanden som skickas mellan lokala Exchange-servrar och Microsoft 365 som interna, så att de kan:
  - Utvärderas och behandlas korrekt av transport-och efterföljandekrav riktade mot interna meddelanden.
  - Kringgå skydd mot skräp post.

Fullständiga hybrid migreringar passar bäst för organisationer som förväntar sig i en hybrid konfiguration för många månader eller mer. Du får de funktioner som anges ovan i det här avsnittet, plus katalog-synkronisering, bättre integrerade funktioner och möjligheten att flytta post lådor till och från Microsoft 365 med hjälp av Online-postlådor. Microsoft 365 blir en förlängning av din lokala organisation.

Om du funderar på att göra en fullständig hybrid migrering är det några saker du bör tänka på:

- Fullständiga hybrider är inte anpassade för alla typer av organisationer. På grund av komplexiteten hos fullständiga hybrid migreringar kan organisationer med färre än ett fåtal hundra post lådor normalt sett inte utnyttja fördelarna som motiverar att det kostar något. Om det låter som din organisation, rekommenderar vi starkt att du betraktar snabbmigrering eller minimala hybrider i stället.
- Du måste konfigurera profilsynkronisering med Azure Active Directory (Azure AD) Connect mellan lokala Active Directory-servrar och Microsoft 365.
- Användare kan logga in i sin Microsoft 365-postlåda med samma användar namn och lösen ord som de använder när de loggar in på det lokala nätverket (kräver Azure AD Connect med Lösenordssynkronisering och/eller Active Directory Federation Services).
- Du behöver en Microsoft 365-licens som innehåller Exchange Online för varje användar post låda du migrerar.
- Användarna behöver inte konfigurera en ny Outlook-profil på de flesta enheter (vissa äldre Android-telefoner kan behöva en ny profil) och behöver inte ladda ner sin e-post igen.

> [!IMPORTANT]
> Om din organisation väljer att migrera post lådor till Microsoft 365, men om du vill fortsätta att ha DirSync eller Azure AD Connect-ansluta på plats för att hantera användar konton från lokala Active Directory måste du ha minst en Exchange-Server lokalt. Om den senaste Exchange-servern tas bort kan du inte ändra Exchange-mottagarna i Exchange Online. Detta beror på att källan till auktoritet kvarstår i din lokala Active Directory och ändringar måste göras där.

Om en fullständig hybrid migrering låter rätt för dig kan du ta en titt på följande resurser för att hjälpa dig med migreringen:

- [Distributions assistent för Exchange](https://aka.ms/exdeploy)
- [Hybrid distributioner av Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid)
- [Hybrid konfigurations guiden](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)
- [Vanliga frågor om konfigurations guiden](https://docs.microsoft.com/exchange/hybrid-configuration-wizard-faqs)
- [Förutsättningar för hybrid distribution](https://docs.microsoft.com/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Uppgradera till en nyare version av Exchange Server lokalt

Även om vi tror att du kan nå det bästa värde-och användar gränssnittet genom att migrera fullständigt till Microsoft 365, förstår vi att vissa organisationer måste ha lokala Exchange-servrar. Detta kan bero på att gällande regler för information inte lagras i ett Data Center i ett annat land, eller så kan det bero på att du har unika inställningar eller krav som inte kan uppfyllas i molnet, eller så kan det vara att du behöver utbyta Skype-postlådor för att kunna använda Active Directory lokalt. I alla händelser där du väljer eller behöver behålla lokal kommunikation bör du se till att din Exchange 2010-miljö uppgraderas till minst Exchange 2013 eller till Exchange 2016 och Exchange 2010 tas bort före slutdatum för support.

För att det ska fungera så bra som möjligt rekommenderar vi att du uppgraderar din återstående lokala miljö till Exchange 2016. Du behöver inte installera Exchange Server 2013 om du vill gå direkt från Exchange Server 2010 till Exchange Server 2016.

Exchange 2016 innehåller alla de funktioner och framsteg som ingår i tidigare versioner av Exchange och det stämmer närmast den funktion som är tillgänglig med Microsoft 365 (även om vissa funktioner endast är tillgängliga i Microsoft 365). Kolla in några av de saker du har saknatt:

|Exchange-version|Funktioner|
|---|---|
|**Exchange 2013**|Förenklad arkitektur som reducerar antalet Server roller till tre (post låda, klient åtkomst, Edge Transport)|
||Principer för skydd mot data förlust (DLP) som hjälper till att förhindra känslig information|
||Betydligt förbättrad Outlook Web App-upplevelse|
|**Exchange 2016**|*Funktioner från Exchange 2013 och...*|
||Ytterligare förenklade Server roller för just post lådan och Edge-Transport|
||Förbättrat DLP tillsammans med integrering med SharePoint|
||Förbättrad databas återhämtning|
||Samarbete online|

|Bedömning|Mer information|
|---|---|
|Slut på support datum|Precis som Exchange 2010 har varje version av Exchange sitt eget support datum:|
||**Exchange 2013** – april 2023|
||**Exchange 2016** -oktober 2025|
||Den tidigare slutdatumet för supporten var du än är. April 2023 är lite närmare än du tror!|
|Sökväg till migrering till Exchange 2013 eller 2016|Migreringen från Exchange 2010 till en nyare version är detsamma oavsett om du väljer Exchange 2013 eller Exchange 2016:|
||Installera Exchange 2013 eller 2016 i din befintliga Exchange 2010-organisation flytta tjänster och annan infrastruktur till Exchange 2013 eller 2016 flytta post lådor och gemensamma mappar till Exchange 2013 eller 2016 avprovision återstående Exchange-2010-servrar|
|Versions samexistens|När du migrerar till Exchange 2013 eller Exchange 2016 kan du installera antingen version i en befintlig Exchange 2010-organisation. Det gör att du kan installera en eller flera Exchange 2013-eller Exchange 2016-servrar och utföra migreringen.|
|Server maskin vara|Serverns maskin varu krav har ändrats från Exchange 2010. Du måste kontrol lera att den maskin vara du använder är kompatibel. Du kan ta reda på mer om maskin varu kraven för varje version här:|
||[System krav för Exchange 2016](https://docs.microsoft.com/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016)|
||[System krav för Exchange 2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)|
||Du kommer att märka att med de signifikanta förbättringarna av Exchange-prestanda och den ökade dator kraft och lagrings kapaciteten på nyare servrar, behöver du troligen färre servrar för att stöda samma antal post lådor.|
|Operativ system version|De lägsta operativ system versionerna som stöds för varje version är:|
||**Exchange 2016** Windows Server 2012|
||**Exchange 2013** Windows Server 2008 R2 SP1|
||Du hittar mer information om stöd för operativ system i [matrisen med stöd för Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).|
|Funktionalitetsnivå för Active Directory-skogar|De lägsta funktions nivåerna för Active Directory-skogar som stöds för varje version är:|
||**Exchange 2016** Windows Server 2008 R2 SP1|
||**Exchange 2013** Windows Server 2003|
||Du hittar mer information om stöd för skogens funktionalitetsnivå i [matrisen med stöd för Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).|
|Office-klient versioner|De lägsta Office-klient versionerna som stöds för varje version är:|
||**Exchange 2016** Office 2010 (med de senaste uppdateringarna)|
||**Exchange 2013** Office 2007 SP3|
||Du hittar mer information om support för Office-klienter på [matrisen med stöd för Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).|

Du kan använda följande resurser för att hjälpa dig med migreringen:

- [Distributions assistent för Exchange](https://aka.ms/exdeploy)
- Ändringar i Active Directory-schema för Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- System krav för Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/system-requirements?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Förutsättningar för Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/prerequisites?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Översikt över alternativ för Office 2010-klient och servrar och Windows 7

En visuell Sammanfattning av alternativen uppgradera, migrera och flytta till moln för Office 2010-klienter och-servrar och Windows 7 finns i avsnittet [support affisch](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Bild på affischen för supportens upphörande för Office 2010-klienter/servrar och Windows 7](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Den här affischen är ett snabbt sätt att förstå de olika vägarna som du kan vidta för att förhindra att Office 2010-klient och Server produkter och Windows 7 når supporten, med önskade sökvägar och alternativ support i Microsoft 365 Enterprise markerat.

Du kan också [Ladda ned](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) den här affischen och skriva ut den i Letter-, Legal-och Tabloid-format (11 x 17).

## <a name="what-if-i-need-help"></a>Vad gör jag om jag behöver hjälp?

Om du migrerar till Microsoft 365 kanske du är berättigad att använda vår Microsoft FastTrack-tjänst. FastTrack ger metod tips, verktyg och resurser som gör migreringen till Microsoft 365 så sömlös som möjligt. Det bästa av allt är att du har en verklig support tekniker som vägleder dig genom migreringen, från planering och design för att migrera din sista post låda. Om du vill veta mer om FastTrack kan du titta på [Microsoft FastTrack](https://fasttrack.microsoft.com/).

Om du stöter på problem under migreringen till Microsoft 365 och du inte använder FastTrack, eller din migrering till en nyare version av Exchange Server, kan vi hjälpa dig. Här är några resurser som du kan använda:

- [Teknisk community](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Kund support](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-topics"></a>Relaterade ämnen

[Resurser som hjälper dig att uppgradera från Office 2010-servrar och-klienter](upgrade-from-office-2010-servers-and-products.md)
