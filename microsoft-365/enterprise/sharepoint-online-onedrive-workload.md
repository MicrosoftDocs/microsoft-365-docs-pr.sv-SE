---
title: Distribuera SharePoint och OneDrive för Microsoft 365 Enterprise
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/11/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
- SPO_Content
ms.custom: ''
description: Gå igenom processen med planering, distribution och användning av SharePoint i hela organisationen.
ms.openlocfilehash: ee2c5592015361a678785cb8e4aaad9074c5d804
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636922"
---
# <a name="deploy-sharepoint-and-onedrive-for-microsoft-365-enterprise"></a>Distribuera SharePoint och OneDrive för Microsoft 365 Enterprise

*Den här arbetsbelastningen ingår i både version E3 och E5 av Microsoft 365 Enterprise*

SharePoint och Microsoft Teams används för lagring och delning av filer, innehållshantering och samarbete, och är viktiga delar i Skapat för samarbete-värdet i Microsoft 365 Enterprise. 

SharePoint har också avancerade säkerhetsfunktioner som åtkomstkontroll med behörigheter och kryptering i vila och under överföring. SharePoint-säkerhet är en viktig del av Intelligent säkerhet-värdet i Microsoft 365 Enterprise.

Om SharePoint är helt nytt för dig kan du läsa [SharePoint](https://products.office.com/sharepoint/collaboration) och [Kom igång med SharePoint](https://support.office.com/article/video-what-is-sharepoint-online-c17b6824-cc22-478f-8757-497cc6b57121).

Följande faser och steg vägleder dig genom processen med att bestämma hur SharePoint ska användas i din organisation, att implementera programmet i organisationen genom en serie progressiva distributioner och att få slutanvändarna att använda programmet och förstå nyttan med det. Innan du börjar kontrollerar du att du har konfigurerat rätt faser för [grundläggande infrastruktur](deploy-workloads.md#foundation-infrastructure-prerequisites) så att dina SharePoint-webbplatser har de säkerhetsfunktioner som behövs. 

Information om hur du distribuerar OneDrive för Microsoft 365 för företag finns i [OneDrive-guide för företag](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise).

## <a name="phase-1-envision"></a>Fas 1: Skapa en behovsbild
I det här steget samlar du intressenter för SharePoint-distributionen och fastställer hur SharePoint ska användas för att uppfylla behoven i företaget.

### <a name="step-1-gather-your-sharepoint-deployment-members"></a>Steg 1: Samla de som ska ansvara för SharePoint-distributionen

För att få en lyckad distribution av SharePoint ovanpå den [grundläggande infrastrukturen för Microsoft 365 Enterprise](deploy-foundation-infrastructure.md) behöver du få synpunkter och feedback från rätt personer. Viktiga personer kan vara beslutsfattare, IT-personal (till exempel arkitekter och implementerare) och representanter för slutanvändarna. 

Dessa tre grupper ser till att företagets behov och de tekniska aspekterna av migrering och säkerhet för mappar och filer övervägs före distributionen, och att resultatet blir något som vanliga användare faktiskt kommer att använda. 

#### <a name="result"></a>Resultat

En lista med personer som representerar olika perspektiv i företaget: företagsledning, teknisk personal och slutanvändare.

### <a name="step-2-determine-and-prioritize-your-sharepoint-business-scenarios"></a>Steg 2: Bestäm och prioritera SharePoint-affärsscenarier

SharePoint kan användas för olika ändamål. Du måste ta reda på vilka behoven är i ert företag. Du kan använda SharePoint till att uppfylla behoven av lagring och delning av dokument, innehållshantering och samarbete i dina team, din avdelning eller i hela företaget. 

Visa en lista med scenarier och funktioner i [SharePoint](https://products.office.com/sharepoint/collaboration ).

Pelare för att uppfylla företagets behov:

|||
|:-----|:-----|
| Dela och samarbeta | Utnyttja gruppwebbplatser, kommunikationswebbplatser och synkronisering. |
| Informera och engagera | Kommande information. |
| Omvandla | Använd Flow till att skapa automatiserade arbetsflöden mellan program och tjänster. |
| Utnyttja kollektiv kunskap | Använd Search till att få önskade resultat inom organisationen. |
| Skydda | Se till att din organisation är skyddad och följer rätt efterlevnadskrav. |
|||

På webbplatsen för [SharePoint-administration](https://docs.microsoft.com/sharepoint/sharepoint-online) finns resurser för hur du konfigurerar SharePoint efter dina behov.

Ett sätt att ta reda på hur SharePoint kan användas på bästa sätt är att undersöka hur enskilda personer, grupper, avdelningar eller hela organisationen interagerar med varandra idag, och sedan hitta ett lämpligt scenario som ger ett enklare sätt att lagra och dela filer. Tänk på att [Microsoft Teams](teams-workload.md) kan vara ett bättre val för vissa av dina scenarier.

#### <a name="sharepoint-site-for-highly-regulated-data"></a>SharePoint-webbplats för strikt reglerade data

Strikt reglerade data kan vara data som måste följa regionala föreskrifter, eller så kan de vara data som är särskilt värdefulla för din organisation, till exempel affärshemligheter, ekonomisk information och personalinformation samt organisationens strategi. Du kan konfigurera en SharePoint-webbplats för begränsad åtkomst, dataklassificering, dataförlustskydd och kryptering för den här typen av data. Mer information finns i [Microsoft Teams- och SharePoint-webbplatser för strikt reglerade data](teams-sharepoint-online-sites-highly-regulated-data.md).

#### <a name="result"></a>Resultat
En lista med SharePoint-scenarier som uppfyller din organisations behov av lagring och delning av dokument, innehållshantering, samarbete och säkerhet.

## <a name="phase-2-onboard"></a>Fas 2: Implementering

I den här fasen planerar du för de tekniska aspekterna av SharePoint-distributionen och påbörjar distributionen till utvalda grupper av användare.

### <a name="prerequisites-identity-and-device-access-configuration"></a>Förutsättningar: Konfiguration av identiteter och enhetsåtkomst

Försäkra dig om att du har konfigurerat [principer för identitet och enhetsåtkomst](identity-access-policies.md) och de rekommenderade [principerna för SharePoint-åtkomst](sharepoint-file-access-policies.md) så att åtkomsten till SharePoint-webbplatserna är skyddad.

### <a name="step-1-complete-your-technical-planning"></a>Steg 1: Utför teknisk planering

Innan du börjar med den tekniska planeringen ska du bestämma om du vill använda FastTrack. Om din organisation har fler än 50 licenser och en [berättigad plan](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365) kan du utnyttja fördelarna med FastTrack. Tjänsten är kostnadsfri och vägleder dig genom planering, migrering, distribution och tjänstinförande. Du kan också göra detta själv med hjälp av FastTrack-integreringsguider som är tillgängliga från [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview) när du har loggat in med ditt Microsoft 365-konto.

Om du gör en egen planering eller i samverkan med FastTrack måste du ta reda på om ditt nätverk och din organisation är redo för SharePoint. Det är särskilt viktigt att du uppfyller [avslutsvillkoren för nätverk](networking-exit-criteria.md) i din grundläggande infrastruktur. Var extra noggrann med att se över Internetbandbredden, dataflödet och trafikfördröjningar så att du får bästa möjliga prestanda när det tillkommer ytterligare trafik för SharePoint-baserade dokument.

Förbered för din SharePoint-distribution med hjälp av [Migrera till SharePoint](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online): 

Om du vill lära dig mer om säkerhet i SharePoint kan du se följande resurser:

-     [Hur SharePoint och OneDrive skyddar dina data i molnet](https://docs.microsoft.com/sharepoint/safeguarding-your-data)
-     [Datakryptering i OneDrive och SharePoint](https://docs.microsoft.com/microsoft-365/compliance/data-encryption-in-odb-and-spo)

#### <a name="result"></a>Resultat

Du förstår hur SharePoint-webbplatser och lokal migrering och säkerhet för mappar och dokument fungerar, och är redo att påbörja distributionen av SharePoint till utvalda grupper i organisationen.

### <a name="step-2-run-an-it-pilot"></a>Steg 2: Kör ett IT-pilottest

I de flesta medelstora och stora organisationer skulle du köra ett IT-pilottest med intressenterna från fas 1, tidiga användare och teknikentusiaster. Under IT-pilottestet:

- Välj ett SharePoint-affärsscenario som deltagarna i IT-pilottestet kan öva på.
- Ge testdeltagarna en uppsättning övningar för att testa lagring, delning och samarbete med dokument och andra funktioner i SharePoint.
- Välj strategi för förändringshantering och skapa material som hjälper användare i hela organisationen att börja använda SharePoint. Material för förändringshantering kan vara information via e-post, interna utbildningsplaner, affischer och presentationer. Målet med materialet är att öka medvetenheten om SharePoint och dess fördelar i organisationen, och att få personalen att börja använda programmet. Information och resurser som hjälper dig att komma igång finns i [SharePoint Adoption Resources](https://resources.techcommunity.microsoft.com/resources/SharePoint-adoption/).
- Be deltagarna i pilottestet granska materialet för förändringshantering utifrån deras erfarenheter. De kan ge tips och råd om hur du kan beskriva fördelarna med SharePoint och hur du använder programmet på bästa sätt.

#### <a name="result"></a>Resultat

IT-pilottestningen av SharePoint är slutförd och materialet för förändringshantering har utvecklats, granskats och justerats.

### <a name="step-3-roll-out-to-a-business-group"></a>Steg 3: Distribuera till en grupp i företaget

När IT-pilottestet är klart distribuerar du SharePoint till en grupp eller avdelning i företaget. Distributionen ska innehålla:

- Identifiering av viktiga affärsscenarier för SharePoint i gruppen.
- Meddelandeaktiviteter som informerar användarna om vilka förväntningar och tidslinjer som gäller för SharePoint-användning för avdelningar, arbetsgrupper och projektteam.
- Migrering av gruppmedlemmars lokala mappar och dokument till SharePoint.
- Utbildning, eller länkar till resurser, som ger användarna en introduktion till SharePoint och hur det används. Se videoutbildning för [SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23).
- En feedbackfunktion, till exempel ett centralt Microsoft Teams-team som består av alla i gruppen, för att samla in kommentarer och problem som behöver lösas från användarna i gruppen.
 
Under distributionen kan du finjustera materialet för förändringshantering före distributionen i hela organisationen.

#### <a name="result"></a>Resultat

En grupp har börjat använda SharePoint och materialet för förändringshantering har testats och justerats.

## <a name="phase-3-drive-value"></a>Fas 3: Driva värdet

I den här fasen slutför du distributionen av SharePoint och hjälper användarna att utnyttja dess fördelar.

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a>Steg 1: Distribuera till hela organisationen

Distributionen till övriga användare i organisationen ska omfatta:

- Identifiering av viktiga affärsscenarier för SharePoint i varje specifik grupp i företaget.
- Använd ditt finjusterade material för förändringshantering för att informera alla i organisationen om vilka förväntningar och tidslinjer som gäller för användningen.
- Flytta mappar och dokument för övriga användare i organisationen till SharePoint.
- Ge användarna utbildning eller länkar till resurser som ger en introduktion till SharePoint och hur det används.
- En feedbackfunktion, till exempel ett centralt team som alla är med i, för att samla in kommentarer och problem från användarna i organisationen. Om din organisation består av färre än 2 500 personer använder du en offentlig kanal i Teams. I annat fall använder du en offentlig grupp i Yammer.

#### <a name="result"></a>Resultat
Din organisation har kommit igång och du har en strategi på plats för att informera och utbilda användarna och ge dem möjlighet att använda SharePoint. 

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>Steg 2: Mäta användning, hantera nöjdhet och främja användning

När distributionen till hela organisationen är klar måste du fortsätta att tillämpa din strategi för förändringshantering på följande sätt:

- Se till att ledningen marknadsför SharePoint som primärt verktyg för lagring och delning av dokument.
- Uppmana användarna att använda SharePoint för lagring och delning av dokument inom företagsgrupper, avdelningar, arbetsgrupper och projektteam.

Här är några förslag på aktiviteter:

- Allmänna metodtips för användning av molntjänster finns i [Framgångsfaktorer för Microsoft 365](https://aka.ms/successfactors). 
- Information om användning av tjänsten i organisationen finns i [Microsoft 365-rapporter i administrationscentret](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports). Om du inte är global administratör i din organisation ber du någon som är global administratör att ge ditt användarkonto behörighet som Rapportläsare så att du kan komma åt aktivitetsrapporterna.
- Övervaka feedback (via din offentliga kanal i ett centralt Teams-team eller Yammer) om problem eller synpunkter från SharePoint-användarna. Besvara frågor och åtgärda problem så snabbt du kan för att undvika frustrerade användare och visa att du finns där för att hjälpa till med distributionen.
- Identifiera och stötta duktiga användare och framhäv deras framgångar och föredömliga sätt att använda SharePoint. Visa upp den lyckade användningen som ett gott exempel för övrig personal i organisationen.  Att få bekräftelse av tekniska ledare i en företagsgrupp kan ha ett stort inflytande på ledning och kollegor.

#### <a name="result"></a>Resultat

Din organisation har börjat använda SharePoint i Microsoft 365 Enterprise för lagring av dokument och samarbete.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Hur Microsoft använder Microsoft 365 Enterprise

Om du vill få en inblick i hur vi har distribuerat SharePoint på Microsoft kan du läsa [SharePoint to the cloud: Learn how Microsoft ran its own migration](https://www.microsoft.com/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration) (SharePoint i molnet: Läs om hur Microsoft utförde sin migrering).

## <a name="next-steps"></a>Nästa steg

Se följande resurser för löpande underhåll av SharePoint: 

- [Förstå behörighetsnivåer i SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels)
- [Anpassa behörigheter för SharePoint-webbplatser](https://docs.microsoft.com/sharepoint/customize-sharepoint-site-permissions)
- [Aktivera eller inaktivera extern delning för SharePoint](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)
- [Konfigurera och hantera åtkomstförfrågningar](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)
