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
description: Exchange 2010 har nått Supportens slut. Använd den här planerings översikten för att förbereda uppgraderingen till Exchange Online eller en nyare version av Exchange Server lokalt.
ms.openlocfilehash: 23384d93c4e65fb25a66ca6f2f0bcbe46b34ee18
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519708"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Stöd översikt för Exchange 2010

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Exchange Server 2010 har nått Supportens slut den **13 oktober 2020**. Om du inte redan har börjat migrera från Exchange 2010 till Microsoft 365, Office 365 eller Exchange 2016 är det dags att börja planera.

## <a name="what-does-end-of-support-mean"></a>Vad innebär *slut på support* ?

De flesta Microsoft-produkter har en support livs cykel under vilken de får nya funktioner, korrigeringar, säkerhets korrigeringar och så vidare. Denna livs cykel räcker vanligt vis i 10 år från produkten första gången. Slutet av livs cykeln kallas produkt Supportens slut. Eftersom Exchange 2010 nådde Supportens slut den 13 oktober 2020, erbjuder Microsoft inte längre:

- Teknisk support för problem som kan uppstå.
- Program korrigeringar för problem som kan påverka serverns stabilitet och användbarhet.
- Säkerhets korrigeringar för säkerhets problem som kan göra servern sårbar för säkerhets brott.
- Tids zons uppdateringar.

Din installation av Exchange 2010 fortsätter att köras efter detta datum. Men på grund av ändringarna ovan rekommenderar vi starkt att du migrerar från Exchange 2010 så snart som möjligt.

Mer information om hur du nära Supportens slut finns i [resurser som hjälper dig att uppgradera från Office 2010-servrar och-klienter](upgrade-from-office-2010-servers-and-products.md).

## <a name="what-are-my-options"></a>Vilka alternativ har jag?

Det är en bra tidpunkt för att utforska dina alternativ och förbereda ett flytt abonnemang. Du kan:

- Migrera helt till Microsoft 365. Migrera post lådor med snabbmigrering, minimal hybrid eller fullständig hybrid migrering. Ta sedan bort lokala Exchange-servrar och Active Directory.
- Migrera dina Exchange 2010-servrar till Exchange 2016 på dina lokala servrar.

> [!IMPORTANT]
> Om organisationen väljer att migrera post lådor till Microsoft 365 men planerar att hålla DirSync eller Azure AD Connect för att fortsätta att hantera användar konton från lokala Active Directory måste du behålla minst en Microsoft Exchange-Server lokalt. Om du tar bort alla Exchange-servrar kan du inte göra ändringar i Exchange-mottagare i Exchange Online eftersom auktoritets källan förblir i din lokala Active Directory. Ändringar måste göras där. I det här scenariot har du följande alternativ:
>
>- *Rekommenderas:* Om du har migrerat dina post lådor till Microsoft 365 och uppgraderat dina servrar senast den 13 oktober 2020 kan du använda Exchange 2010 för att ansluta till Microsoft 365 och migrera post lådor. Migrera Exchange 2010 till Exchange 2016 och inaktivera alla återstående Exchange 2010-servrar.
>- Om du inte slutförde migrering av post lådor och lokal server uppgradering senast den 13 oktober 2020 uppgraderar du först dina lokala Exchange 2010-servrar till Exchange 2016. Använd sedan Exchange 2016 för att ansluta till Microsoft 365 och migrera post lådor.

> [!NOTE]
> Det är lite mer komplicerat, men du kan även migrera post lådor till Microsoft 365 när du migrerar dina lokala Exchange 2010-servrar till Exchange 2016.

Här är de tre vägarna som du kan vidta för att undvika slut på stöd för Exchange Server 2010.

![Uppgraderings vägar för Exchange Server 2010](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

I följande avsnitt förklaras alla alternativ i detalj.

## <a name="migrate-to-microsoft-365"></a>Migrera till Microsoft 365

Migrering av e-post till Microsoft 365 är det bästa och enklaste alternativet att hjälpa dig att ta bort din Exchange 2010-distribution. Med en migrering till Microsoft 365 kan du skapa ett enkelt hopp från gammal teknik till aktuella funktioner, bland annat:

- Funktioner för efterlevnad, som bevarande principer, In-Place och rättsliga undantag, pågående eDiscovery och mycket mer.
- Microsoft Teams.
- Power BI.
- Prioriterad inkorg.
- MyAnalytics.

Microsoft 365 får också nya funktioner först, så din organisation kan börja använda dem direkt. Dessutom behöver du inte oroa dig över:

- Köpa och underhålla maskin vara.
- Betala till hetta och låt dina servrar svalna.
- Hålla dig uppdaterad om säkerhets-, produkt-och tids zoner.
- Bevara lagring och program vara för att stödja kraven på efterlevnad.
- Uppgradera till en ny version av Exchange. Du är alltid med den senaste versionen av Exchange i Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>Hur ska jag migrera till Microsoft 365?

Beroende på din organisation har du några alternativ för att komma till Microsoft 365. Först måste du fundera på några saker, till exempel:
- Antalet säten eller post lådor som du måste flytta.
- Hur länge du vill att migreringen ska pågå.
- Om du behöver en sömlös integrering mellan din lokala installation och Microsoft 365 under migreringen.
 
I den här tabellen visas migreringsåtgärder och de viktigaste faktorer som avgör vilken metod som ska användas.

|Flyttnings alternativ|Organisationens storlek|Repetition|
|---|---|---|
|Snabb migrering|Färre än 150 platser|En vecka eller mindre|
|Minimal hybrid migration|Färre än 150 platser|Några veckor eller färre|
|Fullständig hybrid migration|Fler än 150 platser|Några veckor eller mer|

I följande avsnitt får du en översikt över de här metoderna. Mer information finns i [välja en sökväg för migrering](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27).

### <a name="cutover-migration"></a>Snabb migrering

I en snabbmigrering-migrering migrerar du alla dina post lådor, distributions grupper, kontakter och så vidare till Office 365 vid en uppsättning datum och tid. När du är klar stänger du av dina lokala Exchange-servrar och börjar använda Microsoft 365 exklusivt.

Snabbmigrering migration är perfekt för små organisationer som inte har många post lådor, vill komma till Microsoft 365 snabbt och inte vill hantera de andra metodernas komplexitet. Men det bör göras i en vecka eller mindre. Och det kräver att användare konfigurerar om sina Outlook-profiler. Snabbmigrering migration kan migrera upp till 2 000-postlådor, men vi rekommenderar att du använder den för maximalt 150. Om du försöker migrera mer kan det ta slut på dig att överföra alla post lådorna före din tids gräns och din IT-supportavdelning kan bli mycket roligare med att hjälpa användarna att konfigurera om Outlook.

Här är några saker du bör tänka på när du snabbmigrering migrering:

- Microsoft 365 måste ansluta till dina Exchange 2010-servrar med hjälp av Outlook överallt via TCP-port 443.
- Alla lokala post lådor flyttas till Microsoft 365.
- Du behöver ett lokalt administratörs konto med Läs åtkomst till användarnas post lådor.
- Exchange 2010 accepterade domäner som du vill använda i Microsoft 365 måste läggas till som verifierade domäner i tjänsten.
- Mellan när du startar migreringen och när du påbörjar fasen kommer Microsoft 365 regelbundet att synkronisera Microsoft 365-och lokala post lådor. Då kan du slutföra migreringen utan att oroa dig för att e-post kvars i dina lokala post lådor.
- Användarna får nya tillfälliga lösen ord för sitt Microsoft 365-konto. De måste ändra dem när de loggar in på sina post lådor för första gången.
- Du behöver en Microsoft 365-licens som innehåller Exchange Online för varje användar post låda du migrerar.
- Användarna måste konfigurera en ny Outlook-profil på var och en av deras enheter och hämta e-postmeddelandet igen. Hur mycket e-post som kommer att hämtas kan variera. Mer information finns i [arbeta offline i Outlook](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

Mer information om snabbmigrering migrering finns i:

- [Det här behöver du veta om en snabbmigrering-e-postmigrering](https://docs.microsoft.com/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Utföra en snabbmigrering migrering av e-post till Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Minimal hybrid migration

I en minimal hybrid eller snabb migrering flyttar du några hundra post lådor till Microsoft 365 inom några veckor. Den här metoden stöder inte avancerade Hybrid funktioner som delade ledig/upptagen kalender information.

Minimal hybrid migration är perfekt för organisationer som behöver ta mer tid att migrera sina post lådor till Microsoft 365, men ändå planera för att slutföra migreringen inom några veckor. Du får några av fördelarna med den mer avancerade *fullständiga fullständig hybrid migreringen* utan mycket komplexitet. Du kan styra hur många och vilka post lådor som ska migreras vid en given tidpunkt. Microsoft 365-postlådor skapas med användar namn och lösen ord för lokala konton. Och till skillnad från snabbmigrering-migreringar behöver dina användare inte återskapa sin Outlook-profil.

Här är några saker att tänka på för minimal hybrid migrering:

- Du måste göra en synkronisering mellan lokala Active Directory-servrar och Microsoft 365.
- Användarna kan logga in på sin Microsoft 365-postlåda med samma användar namn och lösen ord som före sin post låda.
- Du behöver en Microsoft 365-licens som innehåller Exchange Online för varje användar post låda som du migrerar.
- Användarna behöver inte konfigurera en ny Outlook-profil på de flesta enheter, men vissa äldre Android-telefoner kan behöva en ny profil. Användarna behöver inte hämta e-postmeddelandet igen.

Mer information finns i [använda minimal hybrid för att snabbt migrera Exchange-postlådor till Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate).

### <a name="full-hybrid"></a>Fullständig hybrid

I en fullständig hybrid migrering har du många hundra, upp till tusentals post lådor, och du flyttar några eller alla till Microsoft 365. Eftersom de här migreringarna normalt är längre tid gör hybrid migrering det möjligt att:

- Visa lokala användare den lediga/upptagna kalender informationen för användare i Microsoft 365 och vice versa.
- Se en Unified Global Address-lista som innehåller mottagare i både lokala och Microsoft 365.
- Visa fullständiga egenskaper för Outlook-mottagare för alla användare, oavsett om de är lokalt eller i Microsoft 365.
- Säker e-postkommunikation mellan lokala Exchange-servrar och Office 365 via TLS och certifikat.
- Behandla meddelanden som skickas mellan lokala Exchange-servrar och Microsoft 365 som interna, så att de kan:
  - Utvärderas och behandlas korrekt av transport-och efterföljandekrav riktade mot interna meddelanden.
  - Kringgå skydd mot skräp post.

Fullständiga hybrid migreringar passar bäst för organisationer som förväntar sig i en hybrid konfiguration för många månader eller mer. Du får de funktioner som beskrivs tidigare i det här avsnittet, plus katalog-synkronisering, bättre integrerade funktioner och möjligheten att flytta post lådor till och från Microsoft 365 med hjälp av Online-postlådor. Microsoft 365 blir en förlängning av din lokala organisation.

Saker du bör tänka på om fullständig hybrid migrering:

- De är inte anpassade för alla organisationer. På grund av komplexiteten hos fullständiga hybrid migreringar kan organisationer med färre än ett fåtal hundra post lådor vanligt vis inte utnyttja fördelarna som motiverar och kostar. I sådana fall rekommenderar vi att du tar med snabbmigrering eller en minimal hybrid migrering i stället.
- Du måste konfigurera profilsynkronisering med Azure Active Directory (Azure AD) Connect mellan lokala Active Directory-servrar och Microsoft 365.
- Användare kan logga in i sin Microsoft 365-postlåda med samma användar namn och lösen ord som de använder när de loggar in i det lokala nätverket. (Den här funktionen kräver Azure AD Connect med Lösenordssynkronisering och/eller Active Directory Federation Services).
- Du behöver en Microsoft 365-licens som innehåller Exchange Online för varje användar post låda du migrerar.
- Användarna behöver inte konfigurera en ny Outlook-profil på de flesta enheter, även om vissa äldre Android-telefoner kanske behöver en ny profil. Användarna behöver inte hämta e-postmeddelandet igen.

> [!IMPORTANT]
> Om din organisation väljer att migrera post lådor till Microsoft 365 men planerar att hålla DirSync eller Azure AD Connect på plats för att fortsätta att hantera användar konton från lokala Active Directory måste du ha minst en Exchange-Server lokalt. Om alla Exchange-servrar tas bort kan du inte ändra Exchange-mottagarna i Exchange Online. Detta beror på att källan till auktoritet kvarstår i din lokala Active Directory och ändringar måste göras där.

Om en fullständig hybrid migrering låter rätt för dig kan du läsa följande resurser:

- [Distributions assistent för Exchange](https://aka.ms/exdeploy)
- [Hybrid distributioner av Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid)
- [Hybrid konfigurations guiden](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)
- [Vanliga frågor om konfigurations guiden](https://docs.microsoft.com/exchange/hybrid-configuration-wizard-faqs)
- [Förutsättningar för hybrid distribution](https://docs.microsoft.com/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Uppgradera till en nyare version av Exchange Server lokalt

Vi tror att du kommer att få det bästa värdet och användar upplevelsen genom att migrera fullständigt till Microsoft 365. Men vi förstår att vissa organisationer måste ha lokala Exchange-servrar. Detta kan bero på reglernas krav, för att säkerställa att data inte lagras i ett externt Data Center, eftersom du har unika inställningar eller krav som inte kan uppfyllas i molnet, eller på grund av att du inte har använt Active Directory lokalt. Om du behåller lokal kommunikation bör du under alla omständigheter se till att din Exchange 2010-miljö uppgraderas till minst Exchange 2013 eller till Exchange 2016.

För att det ska fungera så bra som möjligt rekommenderar vi att du uppgraderar din återstående lokala miljö till Exchange 2016. Du behöver inte installera Exchange Server 2013 om du vill gå direkt från Exchange Server 2010 till Exchange Server 2016.

Exchange 2016 innehåller alla funktioner i tidigare versioner av Exchange. Det stämmer bäst med Microsoft 365, även om vissa funktioner endast är tillgängliga i Microsoft 365. Kolla in några av de saker du har saknatt:

|Exchange-version|Funktioner|
|---|---|
|**Exchange 2013**|Förenklad arkitektur minskar antalet Server roller till tre (post låda, klient åtkomst, Edge Transport)|
||Principer för skydd mot data förlust (DLP) som hjälper till att förhindra känslig information|
||Förbättrad Outlook Web App-upplevelse|
|**Exchange 2016**|*Funktioner från Exchange 2013 och...*|
||Ytterligare förenklade Server roller för just post lådan och Edge-Transport|
||Förbättrat DLP tillsammans med integrering med SharePoint|
||Förbättrad databas återhämtning|
||Samarbete online|

|Bedömning|Mer information|
|---|---|
|Slut på support datum|Precis som Exchange 2010 har varje version av Exchange sitt eget eget support datum:<br/><br/>Exchange 2013 – april 2023<br/>Exchange 2016-oktober 2025<br/><br/>Den tidigare slutdatumet för slutanvändaren måste du göra en ny migrering. April 2023 är lite närmare än du tror!|
|Sökväg till migrering till Exchange 2013 eller 2016|Migreringen från Exchange 2010 till en nyare version är detsamma oavsett om du väljer Exchange 2013 eller Exchange 2016:<br/><br/>Installera Exchange 2013 eller 2016 i din befintliga Exchange 2010-organisation.<br/>Flytta tjänster och annan infrastruktur till Exchange 2013 eller 2016.<br/>Flytta post lådor och gemensamma mappar till Exchange 2013 eller 2016 avprovision återstående Exchange 2010-servrar.|
|Versions samexistens|När du migrerar till Exchange 2013 eller Exchange 2016 kan du installera antingen version i en befintlig Exchange 2010-organisation. Det gör att du kan installera en eller flera Exchange 2013-eller Exchange 2016-servrar och göra migreringen.|
|Server maskin vara|Serverns maskin varu krav har ändrats från Exchange 2010. Kontrol lera att din maskin vara är kompatibel. Få reda på mer om maskin varu kraven för varje version här:<br/><br/>[System krav för Exchange 2016](https://docs.microsoft.com/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016)<br/>[System krav för Exchange 2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)<br/><br/>Med de signifikanta förbättringarna i Exchange-prestandan och den ökade dator kraft och lagrings kapaciteten i nyare servrar behöver du troligt vis färre servrar för att stödja samma antal post lådor.|
|Operativ system version|De lägsta operativ system versionerna som stöds för varje version är:<br/><br/>Exchange 2016 – Windows Server 2012<br/>Exchange 2013 – Windows Server 2008 R2 SP1<br/><br/>Du hittar mer information om stöd för operativ system i [matrisen med stöd för Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).|
|Funktionalitetsnivå för Active Directory-skogar|De lägsta funktions nivåerna för Active Directory-skogar som stöds för varje version är:<br/><br/>Exchange 2016 – Windows Server 2008 R2 SP1<br/>Exchange 2013 – Windows Server 2003<br/><br/>Du hittar mer information om stöd för skogens funktionalitetsnivå i [matrisen med stöd för Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).|
|Office-klient versioner|De lägsta Office-klient versionerna som stöds för varje version är:<br/><br/>Exchange 2016 – Office 2010 (med de senaste uppdateringarna)<br/>Exchange 2013 – Office 2007 SP3<br/><br/>Mer information om support för Office-klienter finns i [matrisen med stöd för Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).||| 


Använd följande resurser för att få hjälp med migreringen:

- [Distributions assistent för Exchange](https://aka.ms/exdeploy)
- Ändringar i Active Directory-schema för Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- System krav för Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/system-requirements?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Förutsättningar för Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/prerequisites?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Översikt över alternativ för Office 2010-klient och servrar och Windows 7

En visuell Sammanfattning av alternativen uppgradera, migrera och flytta till moln för Office 2010-klienter och-servrar och Windows 7 finns i avsnittet [support affisch](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Slut på support för Office 2010-klienter och-servrar och Windows 7-affisch](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Den här affischen med en sida illustrerar olika sökvägar som du kan vidta för att svara på Office 2010-klient och Server produkter och Windows 7 med stöd för support, med önskade sökvägar och alternativ support i Microsoft 365 Enterprise markerat.

Du kan också [Ladda ned](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) den här affischen och skriva ut den i Letter-, Legal-och Tabloid-format (11 x 17).

## <a name="what-if-i-need-help"></a>Vad gör jag om jag behöver hjälp?

Om du migrerar till Microsoft 365 kanske du är berättigad att använda vår Microsoft FastTrack-tjänst. FastTrack ger metod tips, verktyg och resurser som gör migreringen till Microsoft 365 så sömlös som möjligt. Det bästa av allt är att du får en support tekniker från planering och design för att migrera din sista post låda. Mer information om FastTrack finns i [Microsoft FastTrack](https://fasttrack.microsoft.com/).

Om du stöter på problem under migreringen till Microsoft 365 och du inte använder FastTrack, eller om du migrerar till en nyare version av Exchange Server, kan du använda följande resurser:

- [Teknisk community](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Kund support](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>Relaterade artiklar

[Resurser som hjälper dig att uppgradera från Office 2010-servrar och-klienter](upgrade-from-office-2010-servers-and-products.md)
