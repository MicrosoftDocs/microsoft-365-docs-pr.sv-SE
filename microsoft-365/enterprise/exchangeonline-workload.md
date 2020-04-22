---
title: Distribuera Exchange Online för Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-email-calendar
ms.custom:
- Strat_O365_Enterprise
description: Gå igenom processen att planera för, distribuera och driva värdet av Exchange Online i Microsoft 365 Enterprise i hela organisationen.
ms.openlocfilehash: 9214796c37e9cb5ca9fcb07ced5db7efd8e0f7d0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634152"
---
# <a name="deploy-exchange-online-for-microsoft-365-enterprise"></a>Distribuera Exchange Online för Microsoft 365 Enterprise

*Den här arbetsbelastningen ingår i både version E3 och E5 av Microsoft 365 Enterprise*

Exchange Online är din primära molntjänst för e-post och kalender som hjälper användarna att samarbeta på ett sätt som inte kräver chatt eller centraliserad dokumentlagring i realtid. Exchange Online är en viktig del av värdet Built for Teamwork för Microsoft 365 Enterprise. Med Exchange Online kan du åstadkomma mer och arbeta mer effektivt med det välkända Outlook-programmet, oavsett vilken enhet du använder.

Exchange Online har också avancerade säkerhetsfunktioner, inklusive anti-malware och anti-spam filtrering för att skydda postlådor och dataförlust förebyggande funktioner som hindrar användare från att av misstag skicka känslig information till obehöriga. Exchange Online-säkerhet är en viktig del av värdet för intelligent säkerhet i Microsoft 365 Enterprise.

Om du är helt ny på Exchange Online läser du [Microsoft Exchange Online](https://products.office.com/exchange/exchange-online).

Följande faser och steg vägleder dig genom processen att föreställa dig rollen som Exchange Online i din organisation, onboarding din organisation till Exchange Online genom en rad progressiva distributioner, och drivande användning av Exchange Online och dess värde för dina slutanvändare.

>[!Note]
>Dessa distributionsinstruktioner bör endast följas när du har slutfört [fas 2-identitet för Microsoft 365 Enterprise foundation-infrastrukturen](identity-infrastructure.md).
>

## <a name="phase-1-envision-your-exchange-online-deployment"></a>Fas 1: Föreställ dig din Exchange Online-distribution

I den här fasen samlar du personerna för exchange online-distributionen och bestämmer hur din organisation ska använda Exchange Online för att tillgodose företagets affärsbehov.

### <a name="step-1-gather-your-exchange-online-deployment-members"></a>Steg 1: Samla in dina Exchange Online-distributionsmedlemmar

För en lyckad distribution av Exchange Online utöver [fas 2-identitet](identity-infrastructure.md) för Microsoft 365 Enterprise foundation-infrastrukturen måste du samla rätt personer för input och feedback. Viktiga personer kan vara beslutsfattare, IT-personal (till exempel arkitekter och implementerare) och representanter för slutanvändarna. 

Dessa tre grupper säkerställer att exchange online-distributionen innehåller överväganden som tillgodoser affärsbehov, tekniska aspekter av postlådemigrering och säkerhet och att resultatet är något som vanliga användare använder.

#### <a name="result"></a>Resultat

En lista över personer som representerar företagets, tekniska och slutanvändarens aspekter i din organisation.

### <a name="step-2-determine-and-prioritize-your-exchange-online-business-scenarios"></a>Steg 2: Bestäm och prioritera dina Affärsscenarier för Exchange Online

Exchange Online kan användas för olika ändamål. Du måste ta reda på vilka syften som mappas till dina affärsbehov på de olika nivåerna i organisationen, dina företagsgrupper, dina avdelningar eller enskilda arbets- och projektteam. Du bör inrikta dig på Exchange Online för att hantera dina individuella och små gruppkortlivade kommunikations- och schemaläggningsbehov. 

Ett sätt att se fördelarna med Exchange Online är att undersöka hur individer, ett team eller ett v-team interagerar idag och sedan hitta ett lämpligt scenario som ger enklare sätt att kommunicera, schemalägga möten och samarbeta. Tänk på att [Microsoft Teams](teams-workload.md) kan vara ett bättre val för vissa av dina samarbetsscenarier.

#### <a name="result"></a>Resultat
En lista över Exchange Online-scenarier som tillgodoser organisationens behov av kommunikation, schemaläggning och kortlivade samarbete.

## <a name="phase-2-onboard"></a>Fas 2: Implementering

I den här fasen planerar du för de tekniska aspekterna av en Exchange Online-distribution och börjar distribuera den till valda grupper av användare.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Förutsättningar: Konfiguration av identiteter och enhetsåtkomst

Skydda åtkomsten till Exchange Online-postlådor genom att se till att du har konfigurerat [principer för identitets- och enhetsåtkomst](identity-access-policies.md) och de [rekommenderade Exchange Online-åtkomstprinciperna](secure-email-recommended-policies.md).

### <a name="step-1-complete-your-technical-planning"></a>Steg 1: Utför teknisk planering

Innan du börjar med den tekniska planeringen ska du bestämma om du vill använda FastTrack. Om din organisation har över 50 platser och deltar i en [kvalificerad plan](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)kan du använda [FastTrack för Microsoft 365,](https://fasttrack.microsoft.com/microsoft365) *som är tillgängligt utan extra kostnad* för att guida dig genom planering, distribution och tjänstanvändning. Du kan också göra detta själv med hjälp av FastTrack-integreringsguider som är tillgängliga från [FastTrack](https://fasttrack.microsoft.com/) när du har loggat in med ditt Microsoft 365-konto.

Om du gör din egen planering, eller tillsammans med FastTrack, måste du avgöra om ditt nätverk och din organisation är redo för Exchange Online. Det är särskilt viktigt att du uppfyller avslutningskriterierna för [nätverk](networking-infrastructure.md) i din grundinfrastruktur för användare som är anslutna till ditt organisationsnätverk. Var särskilt uppmärksam på Internetbandbredd, dataflöde och trafikförseningar för att maximera prestanda för ytterligare trafik för Exchange Online-baserad e-post och bilagor.

Använd dessa resurser för att förbereda för de tekniska aspekterna av en Exchange Online-distribution: 

- [Olika sätt att migrera flera e-postkonton till Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)
- [Migrera gemensamma Exchange Server-mappar till Exchange Online](https://docs.microsoft.com/Exchange/collaboration/public-folders/migrate-to-exchange-online?view=exchserver-2019)
- [Migrera gemensamma Exchange Server-mappar till Microsoft 365-grupper](https://docs.microsoft.com/Exchange/collaboration/public-folders/batch-migration-to-office-365-groups?view=exchserver-2019)
- [Samarbete i Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/collaboration-exo)
- [Mottagare i Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/recipients-in-exchange-online)
- [Outlook för iOS och Android](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-for-ios-and-android/outlook-for-ios-and-android)

För en bättre förståelse av säkerheten i Exchange Online kan du läsa följande resurser:

- [Behörigheter i Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- [Säkerhet och efterlevnad för Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/security-and-compliance) 
- [Skydd mot skräppost och skadlig programvara](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-and-anti-malware-protection)

Använd sedan dessa resurser för att förstå hantering av Exchange Online-postlådor:

- [Skapa användarpostlådor i Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/create-user-mailboxes)
- [Hantera användares postlådor](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes) 
- [Skapa och hantera distributionsgrupper](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)

#### <a name="result"></a>Resultat

Du förstår postlådemigrering, säkerhet och hantering och är redo att börja distribuera Exchange Online till valda grupper i organisationen.

### <a name="step-2-run-an-it-pilot"></a>Steg 2: Kör ett IT-pilottest

För de flesta medelstora och stora organisationer bör du köra en IT-pilot med dina intressenter från fas 1, tidiga användare och tekniska entusiaster. Under IT-pilottestet:

- Ge dina pilotdeltagare Microsoft 365-licenser och migrera deras lokala postlådor till Exchange Online.
- Ge dina pilotdeltagare en uppsättning övningar för att testa Exchange Online-e-post, schemaläggning och andra funktioner.
- Bestäm din ändringshanteringsstrategi och ta fram material för att driva användarnas användaranvändning i hela organisationen av Outlook och Exchange Online. 
 
  Material för förändringshantering kan vara information via e-post, interna utbildningsplaner, affischer och presentationer. Dessa material kommer att informera din organisation om Exchange Online och dess fördelar med målen att öka medvetenheten och köranvändning. Mer information finns i artikeln [för ändringshantering för Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)

- Be deltagarna i pilottestet granska materialet för förändringshantering utifrån deras erfarenheter. De kan ge tips om bästa praxis och råd om hur du bäst beskriver fördelarna med Outlook och Exchange Online och hur du använder den för kommunikation och schemaläggning.

#### <a name="result"></a>Resultat

Din Exchange Online IT-pilot är komplett och det ursprungliga förändringshanteringsmaterialet har utvecklats, granskats och förfinats.

### <a name="step-3-roll-out-to-a-business-group"></a>Steg 3: Distribuera till en grupp i företaget

När du har slutfört IT-piloten distribuerar du Exchange Online till en företagsgrupp eller avdelning i organisationen. Om din organisation använder en lokal e-posttjänst, till exempel Exchange Server, består den här distributionen av postlådemigrering. Distributionen ska innehålla:

- Identifiering av viktiga affärsscenarier för Exchange Online inom företagsgruppen.
- Meddelandeaktiviteter för att informera användarna om förväntningar och tidslinjer för Exchange Online-användning för avdelningar och arbets- eller projektteam.
- Migrering av lokala postlådor för dina företagsgruppsmedlemmar till Exchange Online.
- Leverera [användarutbildning](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) i Outlook eller länkar till resurser för att introducera Outlook och hur du använder den.
- En feedbackfunktion, till exempel ett centralt Microsoft Teams-team som består av alla i gruppen, för att samla in kommentarer och problem som behöver lösas från användarna i gruppen.

Under distributionen kan du finjustera materialet för förändringshantering före distributionen i hela organisationen.

#### <a name="result"></a>Resultat

En företagsgrupp är igång med Outlook och Exchange Online och förändringshanteringsmaterialet har testats och förfinats.

## <a name="phase-3-drive-value"></a>Fas 3: Driva värdet

I den här fasen slutför du distributionen av Exchange Online och stöder användarna för att hjälpa dem att förverkliga dess fördelar.

### <a name="step-1-roll-out-exchange-online-to-the-rest-of-your-organization"></a>Steg 1: Rulla ut Exchange Online till resten av organisationen

Distributionen till övriga användare i organisationen ska omfatta:

- Identifiering av viktiga affärsscenarier för Exchange Online inom separata företagsgrupper.
- Användning av ditt förfinade ändringshanteringsmaterial för meddelandeaktiviteter för att informera din organisation om förväntningar och tidslinjer för Exchange Online-användning.
- Migrering av postlådorna för resten av organisationen till Exchange Online.
- Leverera [användarutbildning](https://support.office.com/article/outlook-training-8a5b816d-9052-4190-a5eb-494512343cca) i Outlook eller tillhandahålla länkar till resurser för att introducera Outlook och hur du använder den.
- En feedbackfunktion, till exempel ett centralt team som alla är med i, för att samla in kommentarer och problem från användarna i organisationen. Om din organisation består av färre än 2 500 personer använder du en offentlig kanal i Teams. I annat fall använder du en offentlig grupp i Yammer.

#### <a name="result"></a>Resultat

Din organisation är igång och din strategi för ändringshantering finns på plats för att informera, träna och göra det möjligt för användare att använda Exchange Online.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Steg 2: Mäta användning, hantera nöjdhet och främja användning

När du har distribuerat Exchange Online till hela organisationen måste du fortsätta att använda din strategi för ändringshantering för att:

- Låt ditt ledarskap marknadsföra Exchange Online som det primära verktyget för individuell och kortlivad kommunikation och schemaläggning.
- Uppmuntra enskilda personer att använda den för affärsgrupp, avdelning, arbete och projektgruppskommunikation, kalender och samarbete.

Här är några förslag på aktiviteter:

- Se [Framgångsfaktorer för Microsoft 365 om](https://aka.ms/successfactors) du vill veta mer om allmänna metodtips för införande av molntjänster. 
- Se [Microsoft 365-rapporter i administrationscentret](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports) för att förstå tjänstens användning i hela organisationen. Om du inte är global administratör för din organisation ber du någon som är global administratör att bevilja rapporterläsare behörighet till ditt användarkonto så att du kan komma åt aktivitetsrapporter.
- Övervaka din feedbackplats (en offentlig kanal i ett centralt Teams-team eller Yammer) för problem och feedback från personer om deras erfarenheter av Exchange Online. Besvara frågor och åtgärda problem så snabbt du kan för att undvika frustrerade användare och visa att du finns där för att hjälpa till med distributionen.
- Identifiera och vårda mästare i varje företagsgrupp och markera deras bästa metoder med hjälp av Outlook. Visa upp den lyckade användningen som ett gott exempel för övrig personal i organisationen.  Stöd från tekniska ledare inom en företagsgrupp kan utöva ett kraftfullt inflytande över ledare och kamrater.

#### <a name="result"></a>Resultat

Din organisation har antagit Exchange Online och Outlook som sin primära individuella och små grupp kortlivade kommunikations- och schemaläggningsverktyg.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Hur Microsoft använder Microsoft 365 Enterprise

Om du vill titta in i Microsoft och lära oss hur vi migrerade till Exchange Online och använder Exchange Online Protection för att skydda mot cyberattacker läser du:

- [Microsoft migrerar 150 000 postlådor till Exchange Online](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [Microsoft använder hotinformation för att skydda, upptäcka och reagera på hot](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [Microsoft omintetgör nätfiskeförsök med Office 365](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

## <a name="next-steps"></a>Nästa steg

Se dessa resurser för löpande underhåll av Exchange Online:

- [Administrationscenter för Exchange i Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center) 
- [Övervakning, rapportering och meddelandespårning i Exchange Online](https://docs.microsoft.com/exchange/monitoring/monitoring)
- [Säkerhetskopiera e-post i Exchange Online](https://docs.microsoft.com/exchange/back-up-email) 
