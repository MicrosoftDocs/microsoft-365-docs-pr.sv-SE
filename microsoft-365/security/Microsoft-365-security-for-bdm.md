---
title: Microsoft 365-säkerhet för företags besluts fattare (BDMs)
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: de vanligaste hot-och attack scenarierna för organisationer för sina Microsoft 365-miljöer och rekommenderade åtgärder för att minska riskerna.
ms.openlocfilehash: 2f7de328edbd0220e5627612430fca24641ace11
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47548004"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>Microsoft 365-säkerhet för företags besluts fattare (BDMs)

I den här artikeln beskrivs några av de vanligaste hot-och attack scenarierna för organisationer för sina Microsoft 365-miljöer och rekommenderade åtgärder för att minska riskerna. Medan Microsoft 365 kommer med en bred matris med förkonfigurerade säkerhetsfunktioner kräver den också att du är kund ansvarig för att skydda dina egna identiteter, data och enheter som används för att komma åt moln tjänster. Den här vägledningen har utvecklats av Kozetay (Microsoft Cloud Security Architect) och Thiagaraj Sundararajan (Microsoft erfaren konsult).

Den här artikeln är ordnad efter arbets prioritet, med början från att skydda de konton som används för att administrera de mest kritiska tjänsterna och till gångarna, till exempel din klient organisation, e-post och SharePoint. Det är ett metodiskt sätt att nå säkerhet och samar beta med följande kalkyl blad så att du kan följa upp dina framsteg med intressenter och team i hela organisationen: [Microsoft 365 Security för BDMs kalkyl blad](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx). 

[![365 bild av knapp](../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)

Microsoft tillhandahåller dig det säkra Poäng verktyget i klient organisationen för att automatiskt analysera dina Posture utifrån dina vanliga aktiviteter, tilldela Poäng och ge rekommendationer för säkerhets förbättring. Observera dina aktuella poäng och rekommendationer innan du vidtar åtgärderna i den här artikeln. Åtgärderna som rekommenderas i den här artikeln ökar din poäng. Målet är inte att uppnå det högsta antalet poäng, men att vara medveten om att möjligheter är att skydda miljön på ett sätt som inte negativt påverkar användarnas produktivitet. Se [Microsofts säkra Poäng](mtp/microsoft-secure-score.md).

Ett mer bra sätt innan vi sätter igång. . . Se till att [Aktivera gransknings loggen](../compliance/search-the-audit-log-in-security-and-compliance.md). Du behöver dessa data senare för att kunna undersöka en olycka eller en överträdelse. 

## <a name="protect-privileged-accounts"></a>Skydda privilegierade konton

Det första steget är att se till att kritiska konton i miljön ges ett extra skydd eftersom dessa konton har åtkomst och behörighet att hantera och ändra kritiska tjänster och resurser som kan påverka hela organisationen, om det äventyras. Att skydda privilegierade konton är ett av de effektivaste sätten för att skydda mot en angripare som vill göra en administratörs behörighet. 

|Rekommendation  |E3 |E5  |
|---------|---------|---------|
|Påtvinga multifaktorautentisering (MFA) för alla administratörs konton.|![grön bock markering](../media/green-check-mark.png)|![grön bock markering](../media/green-check-mark.png)| 
|Implementera Azure Active Directory (Azure AD) privilegierad identitets hantering (PIM) för att tillämpa just nu hemlig åtkomst för Azure AD och Azure-resurser. Du kan också upptäcka vem som har åtkomst och granska privilegie rad åtkomst.|         | ![grön bock markering](../media/green-check-mark.png)|
|Implementera hantering av privilegie rad åtkomst för att hantera detaljerad åtkomst kontroll för administrativa uppgifter i Office 365. |         | ![grön bock markering](../media/green-check-mark.png)|
|Konfigurera och Använd behöriga åtkomst arbets stationer (PAW) för att administrera tjänster. Använd inte samma arbets stationer för att surfa på Internet och kontrol lera e-post som inte är relaterat till ditt administratörs konto.|  ![grön bock markering](../media/green-check-mark.png)|![grön bock markering](../media/green-check-mark.png) | 

I följande diagram visas dessa funktioner.
![Rekommenderade funktioner för att skydda privilegierade konton](../media/m365-security-bdm-illustrations-privileged-accounts.png)

Ytterligare rekommendationer:
- Kontrol lera att konton som synkroniseras från lokala platser inte är tilldelade administratörs roller för moln tjänster. Detta gör att angriparen inte kan använda lokala konton för att få administrativ åtkomst till moln tjänster. 
- Se till att tjänst konton inte är tilldelade administratörs roller. Dessa konton övervakas ofta inte och anges med lösen ord som inte upphör att gälla. Börja med att kontrol lera att AADConnect-och ADFS-tjänsterna inte är globala administratörer som standard.
- Ta bort licenser från administratörs konton. Om det inte finns något specifikt användnings fall för att tilldela licenser till specifika administratörs konton tar du bort licenser från dessa konton. 

## <a name="reduce-the-surface-of-attack"></a>Minska attackens yta

Nästa fokus område minskar angrepps området. Detta kan utföras med minimal ansträngning och påverkan på användarna och tjänsterna. Genom att minska Angreppets yta har angripare färre möjligheter att starta en attack mot din organisation.

Här är några exempel:
- Inaktivera POP3-, IMAP-och SMTP-protokoll. De flesta moderna organisationer använder inte längre dessa äldre protokoll. Du kan stänga av dessa och bara tillåta undantag om det behövs. 
- Minska och behåll antalet globala administratörer i klient organisationen till det absolut minimum som krävs. Detta minskar direkt anslags området för angrepp för alla moln tillämpningar. 
- Dra tillbaka servrar och program som inte längre används i din miljö. 
- Implementera en process för inaktive ring och borttagning av konton som inte längre används. 

## <a name="protect-against-known-threats"></a>Skydda mot kända hot

Kända hot inkluderar skadlig kod, kompromissade konton och nätfiske. Vissa skydd mot dessa hot kan implementeras snabbt utan direkt påverkan till användarna, medan andra kräver mer planerings-och användar utbildning. 

|Rekommendation  |E3  |E5  |
|---------|---------|---------|
|**Ställ in multifaktorautentisering och Använd rekommenderade principer för villkorsstyrd åtkomst, inklusive principer för inloggnings risker**. Microsoft rekommenderar och har testat en uppsättning principer som samarbetar för att skydda alla molnappar, inklusive Office 365 och Microsoft 365 Services. Se [konfigurationer för identitets-och enhets åtkomst](../enterprise/microsoft-365-policies-configurations.md). | |![grön bock markering](../media/green-check-mark.png)|
|**Kräv multifaktorautentisering för alla användare**. Om du inte har den licens som krävs för att implementera rekommenderade principer för villkorsstyrd åtkomst, måste minst multifaktorautentisering användas för alla användare.|![grön bock markering](../media/green-check-mark.png)|![grön bock markering](../media/green-check-mark.png)|
|**Höj skyddet mot skadlig program vara i e-post**. Din Office 365-eller Microsoft 365-miljö inkluderar skydd mot skadlig program vara, men du kan öka detta genom att blockera bifogade filer med filtyper som ofta används för skadlig program vara.|![grön bock markering](../media/green-check-mark.png)|![grön bock markering](../media/green-check-mark.png)|
|**Skydda din e-post från riktade nät fiske attacker**. Om du har konfigurerat en eller flera egna domäner för Office 365 eller Microsoft 365-miljön kan du konfigurera riktat mot nätfiske-skydd. ATP-skydd mot nätfiske, en del av Office 365 Avancerat skydd mot obehöriga attacker och andra nät fiske attacker. Om du inte har konfigurerat en egen domän behöver du inte göra detta.| |![grön bock markering](../media/green-check-mark.png)|
|**Skydda mot utpressnings tro Jan attack via e-post**. Utpressnings tro vara tar åtkomst till dina data via kryptering av filer eller Lås dator skärmar. Sedan försöker extort pengar från offer genom att be om "utpressning", vanligt vis i form av cryptocurrencies som Bitcoin, i Exchange för att returnera åtkomst till dina data. Du kan skydda dig mot utpressnings tro Jan genom att skapa en eller flera e-postflödes regler för att blockera fil namns tillägg som ofta används för utpressnings tro Jan program vara, eller för att varna användare som får dessa bilagor|![grön bock markering](../media/green-check-mark.png)|![grön bock markering](../media/green-check-mark.png)|
|**Blockera anslutningar från länder som du inte gör affärer med**. Skapa en princip policy för villkorsstyrd åtkomst för Azure-AD för att blockera alla anslutningar som kommer från dessa länder, och skapa en geo Firewall runt din klient organisation.| |![grön bock markering](../media/green-check-mark.png)|

I följande diagram visas dessa funktioner.
![Rekommenderade funktioner för att skydda mot kända hot](../media/m365-security-bdm-illustrations-known-threats.png)

## <a name="protect-against-unknown-threats"></a>Skydda mot okända hot

När du har lagt till ytterligare skydd till dina privilegierade konton och skyddar mot kända attacker kan du ändra din uppmärksamhet för att skydda mot okända hot. Det mer bestämt och avancerade adversaries använder innovativa och nya, okända metoder för att attackera organisationer. Med Microsofts omfattande telemetridata för data som samlats in över miljarder enheter, program och tjänster kan vi utföra Avancerat hot mot Windows, Office 365 och Azure för att förhindra mot noll dagars attacker, använda sand Box miljöer och kontrol lera giltighet innan du tillåter åtkomst till innehållet. 


|Rekommendation  |E3  |E5  |
|---------|---------|---------|
|**Konfigurera Office 365 Avancerat skydd (ATP)**:<br>* Säkerhet för säkerhets ATP<br>* Säkerhet för ATP<br>* ATP för SharePoint, OneDrive och Microsoft Teams<br>* ATP-skydd mot nätfiske|         |![grön bock markering](../media/green-check-mark.png) |
|**Konfigurera funktioner i Microsoft Defender Avancerat skydd**:<br>* Windows Defender Antivirus <br>* Sårbarhets skydd <br> * Reducering av attack ytan <br> * Maskinvarubaserad isolering <br>* Reglerad mappåtkomst     |         |![grön bock markering](../media/green-check-mark.png) |
|**Använd säkerhet för Microsoft Cloud App** för att Upptäck SaaS-appar och börja använda beteende analyser och avvikelse identifiering. |         |![grön bock markering](../media/green-check-mark.png) |

I följande diagram visas dessa funktioner.
![Rekommenderade funktioner för att skydda mot okända hot](../media/m365-security-bdm-illustrations-unknown-threats.png)

Ytterligare rekommendationer:
- Säker partner kanal kommunikation som e-post med hjälp av TLS.
- Öppna Teams-federationen endast för partner som du kommunicerar med.
- Lägg inte till avsändare-domäner, enskilda avsändare eller käll-IP-adresser i din lista över tillåtna som gör det möjligt för dig att kringgå skräp post och kontrol lera skadlig program vara, att en vanlig metod med kunder lägger till sina egna godkända domäner eller ett antal andra domäner där e-postflöden kan ha rapporter ATS till listan över tillåtna. Lägg inte till domäner i listan skräp post och anslutnings filter eftersom detta kan kringgå alla kontroller för skräp post. 
- Aktivera utgående skräp post meddelanden – aktivera utgående skräp post meddelanden till en distributions lista internt i supportavdelningen eller IT-administratören för att rapportera om någon av de interna användarna skickar skräp post meddelanden externt. Detta kan bero på att kontot har angripits.
- Inaktivera fjärr-PowerShell för alla användare – Remote PowerShell används främst av administratörer för att få åtkomst till tjänster för administrativa ändamål eller programmatisk API-åtkomst. Vi rekommenderar att du inaktiverar det här alternativet för användare som inte är administratörer att undvika Reconnaissance såvida de inte har ett företags behov för att komma åt det. 
- Blockera åtkomst till Microsoft Azure-hanteringskonsolen till alla icke-administratörer. Du kan göra detta genom att skapa en regel för villkorsstyrd åtkomst för att blockera alla användare, med undantag för administratörer. 


## <a name="assume-breach"></a>Antag intrång

Även om Microsoft vidtar åtgärder för att förhindra mot hot och attacker rekommenderar vi att du alltid arbetar under "anta intrång" Mindset. Även om angriparen har hanterat för intrång i miljön måste vi kontrol lera att de inte kan exfiltrate data eller identitets information från miljön. Av den anledningen rekommenderar vi att du aktiverar skydd mot känsliga data läckor som person nummer, kreditkorts nummer, ytterligare person uppgifter och annan organisationsinformation. 

För Mindset "väntande intrång" krävs en icke tillförlitlig nätverks strategi, vilket innebär att användare inte är fullständigt betrodda just nu eftersom de är interna för nätverket. I stället, i enlighet med godkännandet av vad användarna kan göra, och när sådana villkor uppfylls tillämpas vissa kontroller. Villkoren kan omfatta status för enhetens hälsa, program åtkomst, operationer som utförs och användar risker. En åtgärd för enhets registrering ska till exempel alltid utlösa MULTIFAKTORAUTENTISERING för att säkerställa att inga Rouge-enheter läggs till i din miljö. 

En tom säkerhets strategi för nollor kräver också att du vet var informationen lagras och använder lämpliga kontroller för klassificering, skydd och bevarande. För att effektivt skydda de viktigaste och känsliga till gångarna måste du först identifiera var de finns och ta lager, vilket kan vara utmanande. Sedan samarbetar du med din organisation för att definiera en styr strategi. Det är viktigt att planera och förbereda ett klassificerings schema för en organisation och konfigurering av principer, etiketter och villkor. Det är viktigt att inse att det inte är en IT-driven process. Se till att arbeta med den juridiska gruppen och efterlevnaden för att utveckla ett lämpligt klassificerings-och etikett schema för organisationens data.

Microsoft 365 informations skydds funktioner kan hjälpa dig att upptäcka vilken information du har, var den lagras och vilken information som kräver ytterligare skydd. Informations skydd är en kontinuerlig process och Microsoft 365-funktioner ger dig insyn i hur användare använder och distribuerar känslig information, där informationen är lagrad och att den ska flöda. Du kan också se hur användare hanterar information som regleras för att kontrol lera att lämpliga etiketter och skydd tillämpas.


|Rekommendation |E3|E5 |
|---------|---------|---------|
|**Granska och optimera dina villkor för villkorsstyrd åtkomst och relaterade principer för att justera efter dina mål för ett betroende nätverk**. Att skydda mot kända hot är att implementera en uppsättning [rekommenderade principer](../enterprise/microsoft-365-policies-configurations.md). Granska din implementering av dessa principer för att säkerställa att du skyddar dina appar och data mot hackare som har fått åtkomst till nätverket. Observera att den rekommenderade policyn för Intune App för Windows 10 gör det möjligt för Windows informations skydd (Pia). Pia skyddar mot oavsiktliga läckage av organisationens data via appar och tjänster, som e-post, sociala medier och det offentliga molnet. |         |![grön bock markering](../media/green-check-mark.png)|
|**Inaktivera extern e-postvidarekoppling**. Hackare som får åtkomst till en användares post låda kan stjäla din e-post genom att ange brev lådan för automatisk vidarebefordran av e-post. Detta kan inträffa även om användarens kännedom inte är medvetenhet. Du kan förhindra detta genom att konfigurera en regel för e-postflöde.|![grön bock markering](../media/green-check-mark.png) |![grön bock markering](../media/green-check-mark.png)|
|**Inaktivera anonym extern kalender delning**. Som standard tillåts extern anonym kalender delning. [Inaktivera kalender delning](https://docs.microsoft.com/exchange/sharing/sharing-policies/modify-a-sharing-policy) om du vill minska känslig information.|![grön bock markering](../media/green-check-mark.png) |![grön bock markering](../media/green-check-mark.png)|
|**Konfigurera principer för skydd mot data förlust för känslig information**. Skapa en princip för skydd mot data förlust i &amp; Center för säkerhets kontroll för att upptäcka och skydda känslig information som kreditkorts nummer, person nummer och bankkonto nummer. Microsoft 365 innehåller många fördefinierade typer av känslig information som du kan använda för principer för skydd mot data förlust. Du kan också skapa egna känsliga informations typer för känsliga data som är anpassade för din miljö. |![grön bock markering](../media/green-check-mark.png)|![grön bock markering](../media/green-check-mark.png)|
|**Implementera data klassificering och policyer för informations skydd**. Implementera känslighets etiketter och Använd dessa för att klassificera och skydda känslig information. Du kan också använda de här etiketterna för principer för skydd mot data förlust. Om du använder Azure information Protection-etiketter rekommenderar vi att du inte skapar nya etiketter i andra administrations Center.|         |![grön bock markering](../media/green-check-mark.png)|
|**Skydda data i program och tjänster från tredje part med moln program säkerhet**. Konfigurera säkerhets principer för Cloud App för att skydda känslig information för andra partens moln program, till exempel Salesforce, Box eller Dropbox. Du kan använda känslig information och känslighets etiketter som du skapade i Cloud App-säkerhetsprinciper och tillämpa dessa i dina SaaS-appar. <br><br>Med säkerhet för Microsoft Cloud App kan du tvinga fram en rad automatiserade processer. Principer kan anges för att tillhandahålla kontinuerliga kontroll genomsökningar, juridiska eDiscovery-uppgifter, DLP för känsligt innehåll som delas offentligt och mer. Cloud App Security kan övervaka alla filtyper som baseras på fler än 20 metadata-filter (till exempel åtkomst nivå, filtyp). |         |![grön bock markering](../media/green-check-mark.png)|
|**Använd [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview) för att kontrol lera om användare lagrar känslig information på sina Windows-enheter**. |         |![grön bock markering](../media/green-check-mark.png)|
|**Använd [AIP-skanner](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner) för att identifiera och klassificera information mellan servrar och fil resurser**. Använd verktyget AIP repor ting för att visa resultatet och vidta lämpliga åtgärder.|         |![grön bock markering](../media/green-check-mark.png)|

I följande diagram visas dessa funktioner.
![Rekommenderade funktioner för att skydda mot intrång](../media/m365-security-bdm-illustrations-assume-breach.png)

## <a name="continuous-monitoring-and-auditing"></a>Kontinuerlig övervakning och granskning

Senaste, men inte minst kontinuerlig övervakning och granskning av Microsoft 365-miljön tillsammans med Windows och enheter är avgörande för att se till att du snabbt kan upptäcka och åtgärda intrång. Verktyg som säker poäng, säkerhets Center och Microsoft Intelligent Graph Advanced Analytics ger värdefull information i din klient organisation och länkar enorma mängder hot intelligens och säkerhets data för att ge dig ett oskyddat skydd och upptäckt.


|Rekommendation |E3 |E5 |
|---------|---------|---------|
|Kontrol lera att **gransknings loggen** är aktive rad.|![grön bock markering](../media/green-check-mark.png)|![grön bock markering](../media/green-check-mark.png)|
|**Granska säkra poäng varje vecka** – säkra poäng är en central plats för att komma åt säkerhets statusen för ditt företag och utföra åtgärder baserat på säkra Poäng rekommendationer. Vi rekommenderar att du utför denna kontroll varje vecka.|![grön bock markering](../media/green-check-mark.png)|![grön bock markering](../media/green-check-mark.png)|
|Använda **Office 365 ATP** -verktyg:<br>* Hot undersökningar och svars funktioner<br> * Automatisk undersökning och svar |         |![grön bock markering](../media/green-check-mark.png)|
|Använd **Microsoft Defender ATP**:<br> *    [Slut punkts avkänning och svar](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br> * Automatisk undersökning och reparation säkra Poäng <br>*    [Avancerad jakt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![grön bock markering](../media/green-check-mark.png)|
|Använd **säkerhet för Microsoft Cloud App** för att upptäcka ovanliga saker i moln program för att identifiera utpressnings tro Jan program vara, utsatta användare eller icke-falska applikationer, analysera högrisk funktioner och åtgärda automatiskt för att begränsa risken till din organisation.|         |![grön bock markering](../media/green-check-mark.png)|
|Använd **Microsoft Azure Sentinel** eller det aktuella Siem tyget för att övervaka dina problem i miljön. |         |![grön bock markering](../media/green-check-mark.png)|
|**Distribuera [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) ** för att övervaka och skydda mot hot riktade mot din lokala Active Directory-miljö.   |         |![grön bock markering](../media/green-check-mark.png) |
|Använd **Azure Security Center** för att övervaka för hot kring hybrid-och moln arbets belastningar. I Azure Security Center ingår en kostnads fri kapacitets nivå och en standard uppsättning funktioner som betalas utifrån resurs timmar eller transaktioner.|         |         |

I följande diagram visas dessa funktioner.
![Rekommenderade möjligheter för kontinuerlig övervakning och granskning](../media/m365-security-bdm-illustrations-monitoring-auditing.png)

Rekommenderade övervaknings åtgärder:
- **Granska Microsofts säkra poäng varje vecka** – säkra poäng är en central plats för att få åtkomst till klient organisationens säkerhets status och utföra åtgärder baserat på de bästa rekommendationerna. Vi rekommenderar att du utför denna kontroll varje vecka. Säker Poäng inkluderar rekommendationer från över Azure AD, Intune, Cloud App Security och Microsoft Defender Avancerat skydd samt Office 365. 
- **Granska riskfrågor varje vecka** – Använd administrations centret för Azure AD för att granska varje vecka. Den rekommenderade ruleset för identitet och enheter inkluderar en policy för att påtvinga lösen ords ändring vid riskfyllda inloggningar.  
- **Granska Top malware och phished användare varje vecka** – Använd skydds Utforskaren för Office Avancerat skydd för att granska de vanligaste användarna riktade mot skadlig program vara och Phish och för att ta reda på orsaken till varför dessa användare påverkas.
