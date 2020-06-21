---
title: Microsoft 365 Beslutsfattare för säkerhet för företag (BDM)
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: o365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: de vanligaste hot- och attackscenarierna som för närvarande möter organisationer för sina Microsoft 365-miljöer och rekommenderade åtgärder för att minska dessa risker.
ms.openlocfilehash: 894486951deac7e9c157409af8da5e813b53343b
ms.sourcegitcommit: 9ea67fd2e02af760d4fb62e3d09c93b446173f9d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/15/2020
ms.locfileid: "44739232"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>Microsoft 365 Beslutsfattare för säkerhet för företag (BDM)

I den här artikeln beskrivs några av de vanligaste hot- och attackscenarierna som organisationer för närvarande befinner sig i för sina Microsoft 365-miljöer och rekommenderade åtgärder för att minska dessa risker. Microsoft 365 levereras med ett brett utbud av förkonfigurerade säkerhetsfunktioner, men det kräver också att du som kund tar ansvar för att skydda dina egna identiteter, data och enheter som används för att komma åt molntjänster. Denna vägledning har utvecklats av Kozeta Beam (Microsoft Cloud Security Architect) och Thiagaraj Sundararajan (Microsoft Senior Consultant).

Den här artikeln är ordnad efter prioritet för arbete, som börjar med att skydda de konton som används för att administrera de mest kritiska tjänster och tillgångar, till exempel din klient, e-post och SharePoint. Det är ett metodiskt sätt att närma sig säkerhet och fungerar tillsammans med följande kalkylblad så att du kan spåra dina framsteg med intressenter och team i hela organisationen: [Microsoft 365 security for BDMs-kalkylblad](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx). 

[![Tumbild Microsoft 365 BDM-säkerhetsrekommendationer kalkylblad](../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)

Microsoft ger dig verktyget Säker poäng i din klientorganisation för att automatiskt analysera din säkerhetsposition baserat på dina vanliga aktiviteter, tilldela en poäng och ge rekommendationer för säkerhetsförbättringar. Innan du vidtar de åtgärder som rekommenderas i den här artikeln bör du ta del av din aktuella poäng och dina rekommendationer. De åtgärder som rekommenderas i den här artikeln kommer att öka din poäng. Målet är inte att uppnå maxpoäng, utan att vara medveten om möjligheterna att skydda din miljö på ett sätt som inte negativt påverkar produktiviteten för användarna. Se [Microsoft Secure Score](mtp/microsoft-secure-score.md).

En sak till innan vi börjar. . . se till att [aktivera granskningsloggen](../compliance/search-the-audit-log-in-security-and-compliance.md). Du behöver dessa data senare, i händelse av att du behöver undersöka en incident eller ett brott. 

## <a name="protect-privileged-accounts"></a>Skydda privilegierade konton

Som ett första steg rekommenderar vi att du ser till att kritiska konton i miljön får ett extra skyddslager eftersom dessa konton har åtkomst och behörighet att hantera och ändra kritiska tjänster och resurser som kan påverka hela organisationen negativt om de äventyras. Att skydda privilegierade konton är ett av de mest effektiva sätten att skydda mot en angripare som försöker höja behörigheterna för ett komprometterat konto till ett administrativt konto. 

|Rekommendation  |E3 |E5  |
|---------|---------|---------|
|Framtvinga MFA (Multi Factor Authentication) för alla administrativa konton.|![grön bock](../media/green-check-mark.png)|![grön bock](../media/green-check-mark.png)| 
|Implementera Azure Active Directory (Azure AD) Privilegierad identitetshantering (PIM) för att tillämpa privilegierad åtkomst till Azure AD- och Azure-resurser. Du kan också upptäcka vem som har åtkomst och granskning av privilegierad åtkomst.|         | ![grön bock](../media/green-check-mark.png)|
|Implementera hantering av privilegierad åtkomst för att hantera detaljerad åtkomstkontroll över privilegierade administratörsuppgifter i Office 365. |         | ![grön bock](../media/green-check-mark.png)|
|Konfigurera och använd PAW (Privileged Access Workstations) för att administrera tjänster. Använd inte samma arbetsstationer för att surfa på Internet och kontrollera e-post som inte är relaterade till ditt administrativa konto.|  ![grön bock](../media/green-check-mark.png)|![grön bock](../media/green-check-mark.png) | 

Följande diagram illustrerar dessa funktioner.
![Rekommenderade funktioner för att skydda privilegierade konton](../media/m365-security-bdm-illustrations-privileged-accounts.png)

Ytterligare rekommendationer:
- Kontrollera att konton som synkroniseras från lokala inte tilldelas administratörsroller för molntjänster. Detta hjälper till att förhindra att en angripare utnyttjar lokala konton för att få administrativ åtkomst till molntjänster. 
- Kontrollera att tjänstkonton inte har tilldelats administratörsroller. Dessa konton övervakas ofta inte och ställs in med lösenord som inte upphör att gälla. Börja med att se till att AADConnect- och ADFS-tjänstkontona inte är globala administratörer som standard.
- Ta bort licenser från administratörskonton. Om det inte finns ett specifikt användningsfall för att tilldela licenser till specifika administratörskonton tar du bort licenser från dessa konton. 

## <a name="reduce-the-surface-of-attack"></a>Minska angreppsytan

Nästa fokusområde är att minska angreppsytan. Detta kan åstadkommas med minimal ansträngning och inverkan på dina användare och tjänster. Genom att minska angreppsytan har angripare färre sätt att starta en attack mot din organisation.

Här är några exempel:
- Inaktivera POP3-, IMAP- och SMTP-protokoll. De flesta moderna organisationer använder inte längre dessa äldre protokoll. Du kan på ett säkert sätt inaktivera dessa och endast tillåta undantag efter behov. 
- Minska och hålla antalet globala administratörer i klienten till det absolut minsta som krävs. Detta minskar direkt angreppsytan för alla molnprogram. 
- Dra tillbaka servrar och program som inte längre används i din miljö. 
- Implementera en process för att inaktivera och ta bort konton som inte längre används. 

## <a name="protect-against-known-threats"></a>Skydda mot kända hot

Kända hot är skadlig kod, komprometterade konton och nätfiske. Vissa skydd mot dessa hot kan implementeras snabbt utan direkt påverkan på användarna, medan andra kräver mer planering och användarutbildning. 

|Rekommendation  |E3  |E5  |
|---------|---------|---------|
|**Konfigurera flerfaktorsautentisering och använda rekommenderade principer för villkorlig åtkomst, inklusive principer för inloggningsrisk**. Microsoft rekommenderar och har testat en uppsättning principer som fungerar tillsammans för att skydda alla molnappar, inklusive Office 365- och Microsoft 365-tjänster. Se [Konfigurationer för identitets- och enhetsåtkomst](../enterprise/microsoft-365-policies-configurations.md). | |![grön bock](../media/green-check-mark.png)|
|**Kräv multifaktorautentisering för alla användare**. Om du inte har den licensiering som krävs för att implementera de rekommenderade principerna för villkorlig åtkomst kräver du minst multifaktorautentisering för alla användare.|![grön bock](../media/green-check-mark.png)|![grön bock](../media/green-check-mark.png)|
|**Höj skyddsnivån mot skadlig kod i post**. Office 365- eller Microsoft 365-miljön innehåller skydd mot skadlig kod, men du kan öka det här skyddet genom att blockera bifogade filer med filtyper som ofta används för skadlig kod.|![grön bock](../media/green-check-mark.png)|![grön bock](../media/green-check-mark.png)|
|**Skydda din e-post från riktade nätfiskeattacker**. Om du har konfigurerat en eller flera anpassade domäner för din Office 365- eller Microsoft 365-miljö kan du konfigurera riktat skydd mot nätfiske. ATP:s skydd mot nätfiske, som är en del av det avancerade skydd mot office 365, kan skydda din organisation från skadliga identitetsbaserade nätfiskeattacker och andra nätfiskeattacker. Om du inte har konfigurerat en anpassad domän behöver du inte göra detta.| |![grön bock](../media/green-check-mark.png)|
|**Skydda mot ransomware-attacker i e-post**. Ransomware tar bort åtkomsten till dina data genom att kryptera filer eller låsa datorskärmar. Det försöker sedan att pressa pengar från offer genom att be om "lösen", vanligtvis i form av kryptokurner som Bitcoin, i utbyte mot att returnera tillgång till dina data. Du kan hjälpa till att försvara mot ransomware genom att skapa en eller flera regler för e-postflöde för att blockera filnamnstillägg som ofta används för ransomware, eller för att varna användare som tar emot dessa bilagor via e-post.|![grön bock](../media/green-check-mark.png)|![grön bock](../media/green-check-mark.png)|
|**Blockera anslutningar från länder som du inte gör affärer med**. Skapa en Azure AD-princip för villkorlig åtkomst för att blockera alla anslutningar som kommer från dessa länder, vilket effektivt skapar en geobrandvägg runt din klientorganisation.| |![grön bock](../media/green-check-mark.png)|

Följande diagram illustrerar dessa funktioner.
![Rekommenderade funktioner för att skydda mot kända hot](../media/m365-security-bdm-illustrations-known-threats.png)

## <a name="protect-against-unknown-threats"></a>Skydda mot okända hot

När du har lagt till extra skydd i dina privilegierade konton och skyddat mot kända attacker kan du flytta din uppmärksamhet till att skydda mot okända hot. De mer beslutsamma och avancerade motståndarna använder innovativa och nya, okända metoder för att attackera organisationer. Med Microsofts stora telemetri med data som samlats in över miljarder enheter, program och tjänster kan vi utföra avancerat skydd mot hot i Windows, Office 365 och Azure för att förhindra mot Zero Day-attacker, använda sandlådemiljöer och kontrollera giltigheten innan du tillåter åtkomst till ditt innehåll. 


|Rekommendation  |E3  |E5  |
|---------|---------|---------|
|**Konfigurera Office 365 Advanced Threat Protection (ATP):**<br>* ATP säkra bilagor<br>* ATP säkra länkar<br>* ATP för SharePoint, OneDrive och Microsoft Teams<br>* ATP anti-phishing skydd|         |![grön bock](../media/green-check-mark.png) |
|Konfigurera funktioner för **avancerat hotskydd för Microsoft Defender:**<br>* Windows Defender Antivirus <br>* Utnyttja skydd <br> * Attack yta minskning <br> * Hårdvarubaserad isolering <br>* Kontrollerad mappåtkomst     |         |![grön bock](../media/green-check-mark.png) |
|**Använd Microsoft Cloud App Security** för att identifiera SaaS-appar och börja använda beteendeanalys och avvikelseidentifiering. |         |![grön bock](../media/green-check-mark.png) |

Följande diagram illustrerar dessa funktioner.
![Rekommenderade funktioner för att skydda mot okända hot](../media/m365-security-bdm-illustrations-unknown-threats.png)

Ytterligare rekommendationer:
- Säker partnerkanalkommunikation som e-post med TLS.
- Öppna Teams Federation endast till partners som du kommunicerar med.
- Lägg inte till avsändare domäner, enskilda avsändare eller käll-IP-adresser till din tillåt lista eftersom detta gör att dessa kan kringgå spam och malware kontroller - En vanlig praxis med kunder är att lägga till sina egna accepterade domäner eller ett antal andra domäner där e-postflödesproblem kan ha rapporterats till listan över tillåta. Lägg inte till domäner i listan Skräppost- och anslutningsfiltrering eftersom detta potentiellt kringgår alla skräppostkontroller. 
- Aktivera meddelanden om skräppost för utgående skräppost – Aktivera utgående skräppostmeddelanden till en distributionslista internt till helpdesken eller IT-administratörsteamet för att rapportera om någon av de interna användarna skickar ut skräppost externt. Detta kan vara en indikator på att kontot har komprometterats.
- Inaktivera Remote PowerShell för alla användare – Remote PowerShell används huvudsakligen av administratörer för att komma åt tjänster för administrativa ändamål eller programmatisk API-åtkomst. Vi rekommenderar att du inaktiverar det här alternativet för användare som inte är administratörer för att undvika spaning om de inte har ett affärskrav för att komma åt det. 
- Blockera åtkomst till Microsoft Azure Management-portalen för alla icke-administratörer. Du kan åstadkomma detta genom att skapa en villkorlig åtkomstregel för att blockera alla användare, med undantag för administratörer. 


## <a name="assume-breach"></a>Anta brott

Microsoft vidtar alla tänkbara åtgärder för att förhindra hot och attacker, men vi rekommenderar att du alltid arbetar under tänkesättet "Anta intrång". Även om en angripare har lyckats tränga in i miljön måste vi se till att de inte kan exfiltrate data eller identitetsinformation från miljön. Därför rekommenderar vi att du aktiverar skydd mot känsliga dataläckor som personnummer, kreditkortsnummer, ytterligare personlig information och annan konfidentiell information på organisationsnivå. 

Inställningen "Anta intrång" kräver att implementera en nollförtroendenätverksstrategi, vilket innebär att användarna inte är helt betrodda bara för att de är interna i nätverket. I stället, som en del av auktoriseringen av vad användarna kan göra, anges uppsättningar villkor och när sådana villkor är uppfyllda tillämpas vissa kontroller. Villkor kan omfatta enhetens hälsostatus, program som används, åtgärder som utförs och användarrisk. En enhetsregistreringsåtgärd bör till exempel alltid utlösa MFA-autentisering för att säkerställa att inga rouge-enheter läggs till i din miljö. 

En noll förtroendenätverksstrategi kräver också att du vet var din information lagras och tillämpa lämpliga kontroller för klassificering, skydd och lagring. För att effektivt skydda dina mest kritiska och känsliga tillgångar måste du först identifiera var dessa finns och inventera, vilket kan vara utmanande. Därefter arbetar du med din organisation för att definiera en styrningsstrategi. Definiera ett klassificeringsschema för en organisation och konfigurera principer, etiketter och villkor kräver noggrann planering och förberedelse. Det är viktigt att inse att detta inte är en IT-driven process. Var noga med att arbeta med ditt juridiska team och efterlevnadsteam för att utveckla ett lämpligt klassificerings- och märkningsschema för organisationens data.

Microsoft 365-funktioner för informationsskydd kan hjälpa dig att ta reda på vilken information du har, var den lagras och vilken information som kräver ytterligare skydd. Informationsskydd är en kontinuerlig process och Microsoft 365-funktionerna ger dig insyn i hur användare använder och distribuerar känslig information, var din information lagras och var den flödar. Du kan också se hur användare som hanterar information som är reglerad för att vara säker på att lämpliga etiketter och skydd tillämpas.


|Rekommendation |E3|E5 |
|---------|---------|---------|
|**Granska och optimera din villkorliga åtkomst och relaterade principer så att de överensstämmer med dina mål för ett nätverk med noll förtroende**. Att skydda mot kända hot omfattar att implementera en uppsättning [rekommenderade principer](../enterprise/microsoft-365-policies-configurations.md). Granska implementeringen av dessa policyer för att se till att du skyddar dina appar och data mot hackare som har fått åtkomst till nätverket. Observera att den rekommenderade Intune-appskyddsprincipen för Windows 10 aktiverar Pågående arbete med Windows-informationsskydd. Pia skyddar mot oavsiktliga läckor av organisationens data via appar och tjänster, som e-post, sociala medier och det offentliga molnet. |         |![grön bock](../media/green-check-mark.png)|
|**Inaktivera extern vidarebefordran av e-post**. Hackare som får tillgång till en användares postlåda kan stjäla din e-post genom att ställa in postlådan för att automatiskt vidarebefordra e-post. Detta kan hända även utan användarens medvetenhet. Du kan förhindra att detta händer genom att konfigurera en regel för e-postflöde.|![grön bock](../media/green-check-mark.png) |![grön bock](../media/green-check-mark.png)|
|**Inaktivera anonym extern kalenderdelning**. Som standard tillåts extern anonym kalenderdelning. [Inaktivera kalenderdelning](https://docs.microsoft.com/exchange/sharing/sharing-policies/modify-a-sharing-policy) för att minska potentiella läckor av känslig information.|![grön bock](../media/green-check-mark.png) |![grön bock](../media/green-check-mark.png)|
|**Konfigurera principer för att förhindra dataförlust för känsliga data**. Skapa en policy för att förhindra dataförlust i center för &amp; säkerhetsefterlevnad för att identifiera och skydda känsliga data som kreditkortsnummer, personnummer och bankkontonummer. Microsoft 365 innehåller många fördefinierade känsliga informationstyper som du kan använda i principer för att förhindra dataförlust. Du kan också skapa egna känsliga informationstyper för känsliga data som är anpassade till din miljö. |![grön bock](../media/green-check-mark.png)|![grön bock](../media/green-check-mark.png)|
|**Implementera principer för dataklassificering och informationsskydd**. Implementera känslighetsetiketter och använd dessa för att klassificera och tillämpa skydd för känsliga data. Du kan också använda dessa etiketter i principer för att förebygga dataförlust. Om du använder Azure Information Protection-etiketter rekommenderar vi att du undviker att skapa nya etiketter i andra administrationscenter.|         |![grön bock](../media/green-check-mark.png)|
|**Skydda data i appar och tjänster från tredje part med hjälp av Cloud App Security**. Konfigurera säkerhetsprinciper för molnappar för att skydda känslig information i molnappar från tredje part, till exempel Salesforce, Box eller Dropbox. Du kan använda känsliga informationstyper och känslighetsetiketter som du har skapat i Cloud App Security-principer och tillämpa dessa i dina SaaS-appar. <br><br>Med Microsoft Cloud App Security kan du tillämpa ett brett spektrum av automatiserade processer. Principer kan ställas in för att tillhandahålla kontinuerliga efterlevnadssökningar, juridiska eDiscovery-uppgifter, DLP för känsligt innehåll som delas offentligt med mera. Cloud App Security kan övervaka alla filtyper baserat på mer än 20 metadatafilter (till exempel åtkomstnivå, filtyp). |         |![grön bock](../media/green-check-mark.png)|
|**Använd [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview) för att identifiera om användare lagrar känslig information på sina Windows-enheter**. |         |![grön bock](../media/green-check-mark.png)|
|**Använd [AIP Scanner](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner) för att identifiera och klassificera information mellan servrar och filresurser**. Använd AIP-rapporteringsverktyget för att visa resultaten och vidta lämpliga åtgärder.|         |![grön bock](../media/green-check-mark.png)|

Följande diagram illustrerar dessa funktioner.
![Rekommenderade funktioner för att skydda mot intrång](../media/m365-security-bdm-illustrations-assume-breach.png)

## <a name="continuous-monitoring-and-auditing"></a>Kontinuerlig övervakning och revision

Sist men inte minst Kontinuerlig övervakning och granskning av Microsoft 365-miljön tillsammans med Windows och enheter är avgörande för att du snabbt ska kunna upptäcka och åtgärda eventuella intrång. Verktyg som Secure Score, Security Center och Microsoft Intelligent Graph avancerade analyser ger ovärderlig information till din klientorganisation och länkar enorma mängder hotinformation och säkerhetsdata för att ge dig oöverträffad hotskydd och upptäckt.


|Rekommendation |E3 |E5 |
|---------|---------|---------|
|Kontrollera att **granskningsloggen** är aktiverad.|![grön bock](../media/green-check-mark.png)|![grön bock](../media/green-check-mark.png)|
|**Granska secure score varje vecka** – Secure score är en central plats för att komma åt säkerhetsstatus för ditt företag och vidta åtgärder baserat på rekommendationer om säkra poäng. Vi rekommenderar att du utför denna kontroll varje vecka.|![grön bock](../media/green-check-mark.png)|![grön bock](../media/green-check-mark.png)|
|Använda **Office 365 ATP-verktyg:**<br>* Hot utredning och svar kapacitet<br> * Automatiserad utredning och svar |         |![grön bock](../media/green-check-mark.png)|
|Använd **Microsoft Defender ATP:**<br> *    [Identifiering och svar för slutpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br> * Automatiserad undersökning och sanering Säker poäng <br>*    [Avancerad jakt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![grön bock](../media/green-check-mark.png)|
|Använd **Microsoft Cloud App Security** för att identifiera ovanliga beteenden i molnappar för att identifiera ransomware, komprometterade användare eller oseriösa program, analysera högriskanvändning och åtgärda automatiskt för att begränsa risken för din organisation.|         |![grön bock](../media/green-check-mark.png)|
|Använd **Microsoft Azure Sentinel** eller ditt nuvarande SIEM-verktyg för att övervaka hot i hela din miljö. |         |![grön bock](../media/green-check-mark.png)|
|**Distribuera [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) ** för att övervaka och skydda mot hot som är riktade mot din lokala Active Directory-miljö.   |         |![grön bock](../media/green-check-mark.png) |
|Använd **Azure Security Center** för att övervaka hot över hybrid- och molnarbetsbelastningar. Azure Security Center innehåller en kostnadsfri nivå av funktioner och en standardnivå av funktioner som betalas baserat på resurstimmar eller transaktioner.|         |         |

Följande diagram illustrerar dessa funktioner.
![Rekommenderade funktioner för kontinuerlig övervakning och granskning](../media/m365-security-bdm-illustrations-monitoring-auditing.png)

De vanligaste rekommenderade övervakningsåtgärderna:
- **Granska Microsoft Secure Score varje vecka** – Secure-poängen är en central plats för att komma åt din klientklientes säkerhetsstatus och vidta åtgärder baserat på de bästa rekommendationerna. Vi rekommenderar att du utför denna kontroll varje vecka. Secure Score innehåller rekommendationer från hela Azure AD, Intune, Cloud App Security och Microsoft Defender Advanced Threat Protection samt Office 365. 
- **Granska riskfyllda inloggningar varje vecka** – Använd Azure AD-administrationscentret för att granska riskfyllda inloggningar varje vecka. Den rekommenderade identitets- och enhetsåtkomstregleruppsättningen innehåller en princip för att tillämpa lösenordsändring vid riskfyllda inloggningar.  
- **Granska topp malware och phished användare varje vecka** - Använd Office Advanced Threat Protection Threat Explorer för att granska de bästa användarna riktade med skadlig kod och phish och ta reda på orsaken till varför dessa användare påverkas.
