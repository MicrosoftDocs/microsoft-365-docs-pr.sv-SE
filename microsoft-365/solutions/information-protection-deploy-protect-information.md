---
title: Skydda information som omfattas av dataskyddsförordningen
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Distribuera säkerhets- och efterlevnadsfunktioner i Microsoft 365 och skydda din personliga information.
ms.openlocfilehash: a5bba79f8ab382707b6fd5e448003a0271d690c6
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597244"
---
# <a name="protect-information-subject-to-data-privacy-regulation"></a>Skydda information som omfattas av dataskyddsförordningen

Ett antal kontroller för informationsskydd kan användas i prenumerationen för att tillgodose efterlevnadsbehov och föreskrifter om datasekretess. Dessa omfattar allmän dataskyddsförordning (GDPR), HIPAA-HITECH (united states health care privacy act), California Consumer Protection Act (CCPA) och Brazil Data Protection Act (LGPD).

Dessa kontroller finns inom följande lösningsområden:

- Känslighetsetiketter
- Skydd mot dataförlust (DLP)
- Meddelandekryptering i Office (OME)
- Åtkomstkontroller för Teams och webbplatser

![Viktiga tjänster för att skydda personlig information som omfattas av datasekretessförordningen](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-grid.png)

>[!Note]
>Den här lösningen beskriver säkerhets- och efterlevnadsfunktioner för att skydda information som omfattas av sekretessregler för data. En fullständig lista över säkerhetsfunktioner i Microsoft 365 finns i säkerhetsdokumentationen [för Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/) En fullständig lista över efterlevnadsfunktioner i Microsoft 365 finns i dokumentationen [för Microsoft 365-efterlevnad.](https://docs.microsoft.com/microsoft-365/compliance/)
>

## <a name="data-privacy-regulations-that-impact-information-protection-controls"></a>Bestämmelser om datasekretess som påverkar kontroller för informationsskydd

Här är en exempellista över regler om datasekretess som kan ha att göra med informationsskyddskontroller:

- GDPR, artikel 5(1)(f))
- GDPR-artikel (32)(1)(a)
- LGPD, artikel 46
- HIPAA-HITECH (45 CFR 164.312(e)(1))
- HIPAA-HITECH (45 C.F.R. 164,312(e)(2)(ii))

Läs mer [om riskerna med datasekretess och identifiera](information-protection-deploy-assess.md) känsliga objekt för mer information om vart och ett av ovanstående.

Datasekretessföreskrifter för informationsskydd rekommenderar följande:

- Skydd mot förlust eller obehörig åtkomst, användning och/eller överföring.
- Riskbaserad tillämpning av skyddsmekanismer.
- Kryptering används där det är lämpligt.

Din organisation kanske också vill skydda Microsoft 365-innehåll för andra ändamål, till exempel för andra efterlevnadsbehov eller av affärsskäl. Att upprätta ett informationsskyddssystem för datasekretess bör ske som en del av den övergripande planeringen, implementeringen och hanteringen av informationsskydd.

För att hjälpa dig att komma igång med ett informationsskyddsschema i Microsoft 365 innehåller följande avsnitt en kort lista med relaterade funktioner och förbättringsåtgärder för Microsoft 365. Listan innehåller funktioner och förbättringsåtgärder som är tillämpliga i datasekretessbestämmelser. Men listan innehåller inte äldre tekniker om det finns en nyare funktion som till stor del ersätter den äldre. Information Rights Management (IRM) för SharePoint och OneDrive ingår till exempel inte i listan men känslighetsetiketter ingår.

## <a name="managing-information-protection-in-microsoft-365"></a>Hantera informationsskydd i Microsoft 365

Microsofts [informationsskyddslösningar](../compliance/information-protection.md) omfattar ett antal integrerade funktioner i Microsoft 365, Microsoft Azure och Microsoft Windows. Informationsskyddslösningarna i Microsoft 365 omfattar:

- [Tjänstkryptering med kundnyckel](../compliance/customer-key-overview.md)
- [Typer av känslig information](../compliance/what-the-sensitive-information-types-look-for.md) (beskrivs i utvärdering [av datasekretessrisker och identifiera känsliga objekt)](information-protection-deploy-assess.md)
- [Känslighetsetiketter](../compliance/sensitivity-labels.md) 
  - Service/container-level
  - Klient-sida/innehållsnivå
  - Automatiserat för data-at-rest i SharePoint och OneDrive
- Skydd mot dataförlust (DLP)
- [Dataförlustskydd i Microsoft 365 Endpoint](../compliance/endpoint-dlp-learn-about.md)
- [Nya funktioner för meddelandekryptering i Office 365 (OME)](../compliance/ome.md) och avancerad [meddelandekryptering i](../compliance/ome-advanced-message-encryption.md) OME

Dessutom är skydd på webbplats- och biblioteksnivå viktiga mekanismer som ska ingå i alla skyddsscheman.

Information om andra funktioner för informationsskydd utanför Microsoft 365 finns i:

- [Microsoft Cloud Application Security (MCAS)](https://docs.microsoft.com/cloud-app-security/)
- [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)
- [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)
- [Windows Information Protection](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)

## <a name="sensitivity-labels"></a>Känslighetsetiketter

Känslighetsetiketter från Microsofts informationsskyddsramverk låter dig klassificera och skydda organisationens data utan att hindra användarnas produktivitet och möjligheten att samarbeta.

![Känslighetsetiketter i Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-labels.png)

### <a name="prerequisites-for-sensitivity-labels"></a>Förutsättningar för känslighetsetiketter

Utför de här aktiviteterna innan du implementerar någon av de känslighetsetikettbaserade funktionerna som beskrivs nedan:

1. Förstå följande:
   - **Verksamhetskrav.** Upprätta affärsorsaker till att använda känslighetsetiketter i ditt företag. Till exempel dina datasekretesskrav för informationsskydd.
   - **Funktioner för känslighetsetikett.** Känslighetsetiketter kan bli komplexa, så se till att läsa dokumentationen [för känslighetsetiketter innan](../compliance/sensitivity-labels.md) du börjar.
   - **Viktiga saker att tänka på** Känslighetsetiketter hanteras i administrationscentret för Microsofts efterlevnad, men alternativen för inställningar och program varierar avsevärt.
      - Det finns känslighetsetiketter för webbplatser, grupper och Teams på behållarnivå (inställningarna gäller inte för innehåll i behållaren). De publiceras för användare och grupper som använder dem när en webbplats, grupp eller team etableras.
      - Det finns känslighetsetiketter för aktivt innehåll. De publiceras också till användare eller grupper, som antingen tillämpar dem manuellt eller så tillämpas de automatiskt i följande fall:
        - Filen öppnas/redigeras/sparas, antingen på användarens skrivbord eller på en SharePoint-webbplats.
        - Ett e-postmeddelande utkast tills det skickas.
      - Det finns känslighetsetiketter för automatisk app till filer vilan i SharePoint och OneDrive utöver e-postmeddelanden som överförs via Exchange. De är avsedda för antingen alla webbplatser eller specifika och gäller automatiskt för filerna i de här miljöerna.

2. Effektivisera den aktuella känslighetsetiketten med tidigare eller alternativa metoder

   - Azure Information Protection

      Det aktuella känslighetsetikettsschemat kan behöva förenas med en befintlig implementering av [Azure Information Protection-märkning.](../compliance/sensitivity-labels.md#sensitivity-labels-and-azure-information-protection)
   - OME

      Om du planerar att använda modern känslighetsetikett för e-postskydd och befintliga metoder för e-postkryptering som OME finns kan de finnas tillsammans, men du bör förstå scenarierna där antingen ska tillämpas. Se nya funktioner för meddelandekryptering [i Office 365 (OME),](#office-365-message-encryption-ome-new-capabilities)som innehåller en tabell som jämför modern känslighetsetiketttypsskydd med OME-baserat skydd.

3. Planera för integrering med ett bredare informationsskyddssystem. Utöver samexistens med OME kan aktuella känslighetsetiketter användas längs sidan funktioner som Microsoft 365 dataförlustskydd (DLP) och Microsoft Cloud App Security. Läs [känslighetsetiketter och Microsoft Cloud App Security för](../compliance/sensitivity-labels.md#sensitivity-labels-and-microsoft-cloud-app-security) att uppnå dina sekretessrelaterade informationsskyddsmål.

4. Utveckla en känslighetsetikettklassificering och ett kontrollschema. Se [taxonomi för dataklassificering och känslighetsetikett.](https://aka.ms/dataclassificationwhitepaper)

### <a name="general-guidance"></a>Allmän vägledning

1. **Schemadefinition.** Innan du använder tekniska funktioner för att tillämpa etiketter och skydd bör du arbeta med att definiera ett klassificeringsschema i hela organisationen. Du kanske redan har ett klassificeringsschema, vilket gör det enklare att lägga till personliga data. 
2. **Komma igång.** Börja med att bestämma antalet och namnen på etiketterna som ska implementeras. Du kan göra den här aktiviteten utan att bekymra dig om vilken teknik som ska användas och hur etiketter ska användas. Tillämpa det här schemat universellt i hela organisationen, inklusive data som finns lokalt och i andra molntjänster.
3. **Ytterligare rekommendationer** När du utformar och implementerar principer, etiketter och villkor bör du överväga att följa de här rekommendationerna:

   - **Använd befintligt klassificeringsschema (om det finns något).** Många organisationer använder redan dataklassificering i någon form. Utvärdera noga det befintliga etikettschemat och använd det som det är om möjligt. Användning av välbekanta etiketter som känns igen för slutanvändarna kommer att öka införandet.
   - **Börja i liten storlek.** Det finns praktiskt taget ingen gräns för antalet etiketter du kan skapa. Ett stort antal etiketter och underetiketter kan emellertid ta lång tid.
   - **Använd scenarier och användningsfall.** Identifiera vanliga användningsfall inom organisationen och använd scenarier som härleds från de datasekretessföreskrifter som du är ämnet för. Kontrollera om konfigurationen av denvisionerade etiketten och klassificeringen fungerar i praktiken.
   - **Fråga alla förfrågningar om en ny etikett.** Behöver varje scenario eller användningsfall en ny etikett eller kan du använda det du redan har? Om du håller antalet etiketter på ett minimum förbättras införandet.
   - **Använda underetiketter för huvudavdelningar.** Vissa avdelningar kommer att ha särskilda behov som kräver särskilda etiketter. Definiera de här etiketterna som underetiketter för en befintlig etikett och överväg att använda omfattningsprinciper som tilldelas till användargrupper i stället för globalt.
   - **Överväg principer med begränsad omfattning.** Principer som är riktade till delmängder av användare förhindrar att etiketter överbelastas. Med en begränsad princip kan du tilldela roll- eller avdelningsspecifika etiketter eller underetiketter till bara anställda som arbetar för den specifika avdelningen. 
   - **Använd beskrivande etikettnamn.** Försök att inte använda jargong, standarder eller förkortningar som etikettnamn. Försök att använda namn som får användaren att använda bättre. I stället för att använda etiketter som PII, HIPAA, LBI, MBI och HBI bör du överväga namn som Non-Business, Public, General, Confidential och Highly Confidential.

### <a name="create-and-deploy-sensitivity-labels-for-sites-groups-and-teams"></a>Skapa och distribuera känslighetsetiketter för webbplatser, grupper och team

När du skapar [känslighetsetiketter](../compliance/sensitivity-labels-teams-groups-sites.md) i Microsoft 365 efterlevnadscenter kan du nu använda dem på dessa behållare:

- Microsoft Teams-webbplatser
- Microsoft 365-grupper (tidigare Office 365-grupper)
- SharePoint-webbplatser

Använd följande etikettinställningar för att skydda innehållet i de här behållarna:

- Sekretess (offentlig eller privat) för Microsoft 365 gruppanslutna Teams-webbplatser
- Åtkomst för externa användare
- Åtkomst från ohanterade enheter

För datasekretess: för att förhindra extern delning för behållare som ska användas för lagring av innehåll med känslig personlig information, markerar du filerna som innehåller data som privata och kräver hanterade enheter.

### <a name="create-and-deploy-sensitivity-labels-for-content"></a>Skapa och distribuera känslighetsetiketter för innehåll

Med känslighetsetiketter som tillämpas på filer kan du kryptera deras innehåll, vattenstämpla innehållet och definiera andra kontroller för Office-programinnehåll, inklusive Outlook och Office på webben.

När du är redo att börja skydda organisationens data med känslighetsetiketter:

1. **Skapa etiketterna.** Skapa och namnge dina känslighetsetiketter enligt organisationens klassificerings taxonomi för olika känslighetsnivåer i innehåll. Mer information om hur du utvecklar en klassificerings taxonomi finns i informationsbladet Taxonomi för dataklassificering och [känslighetsetikett.](https://aka.ms/dataclassificationwhitepaper)
2. **Definiera vad varje etikett kan göra.** Konfigurera de skyddsinställningar som du vill använda kopplade till varje etikett. Du kanske till exempel vill att innehåll med lägre känslighet (t.ex. en "Allmänt"-etikett) bara ska ha ett sidhuvud eller en sidfot, medan innehåll med högre känslighet (t.ex. etiketten "Konfidentiellt" ska ha en vattenstämpel och ha kryptering aktiverad.
3. **Publicera etiketterna.** När känslighetsetiketterna är konfigurerade publicerar du dem med hjälp av en etikettprincip. Bestäm vilka användare och grupper som ska ha etiketterna och vilka principinställningar som ska användas. En enstaka etikett kan återanvändas. Du definierar den en gång och sedan kan du ta med den i flera etikettprinciper som tilldelats olika användare.

När du publicerar känslighetsetiketter från Efterlevnadscenter för Microsoft 365 börjar de visas i [Office-program](../compliance/sensitivity-labels-office-apps.md) för användare att klassificera och skydda innehåll när det skapas eller redigeras.

![Distributionsflöde för känslighetsetikett i Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-label-flow.png)

För datasekretess lägger du manuellt till en känslighetsetikett med kryptering och andra regler för e-post eller innehåll som innehåller känslig personlig information.

>[!Note]
>Känslighetsetiketter med aktiverad kryptering för e-post har vissa överlappande funktioner med OME. Se [jämförelse av säkra e-postscenarier med OME och känslighetsetiketter.](#secure-email-scenarios-comparison-with-ome-and-sensitivity-labels)

### <a name="client-side-auto-labeling-when-users-edit-documents-or-compose-emails"></a>Automatisk etikett på klientsidan när användare redigerar dokument eller skriver e-postmeddelanden

När du skapar en känslighetsetikett kan du automatiskt tilldela etiketten till innehåll, inklusive [](../compliance/apply-sensitivity-label-automatically.md) e-post, när den matchar de villkor du anger.

Det är viktigt att kunna använda känslighetsetiketter i innehåll automatiskt eftersom:

- Du behöver inte utbilda användarna när de ska använda var och en av dina klassificeringar.
- Du behöver inte förlita dig på att användare klassificerar allt innehåll korrekt.
- Användarna behöver inte längre känna till dina principer – de kan i stället fokusera på sitt arbete.

Automatisk märkning ger stöd för att rekommendera en etikett till användare och att automatiskt använda en etikett. Men i båda fallen bestämmer användaren om han eller hon ska godkänna eller avvisa etiketten för att säkerställa rätt innehållsetikett.

Den här klientetiketten har minimal fördröjning för dokument eftersom etiketten kan användas även innan dokumentet sparas. Men alla klientappar har inte stöd för automatisk etikettering. Den här funktionen stöds av den enhetliga etiketteringsklienten för Azure Information Protection och [vissa versioner av Office-appar.](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)

Konfigurationsinstruktioner finns i [Konfigurera automatisk etikettering för Office-program.](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)

För datasekretess tillämpar du känslighetsetiketter automatiskt för innehåll som innehåller känslig personlig information.

### <a name="service-side-auto-labeling-when-content-is-already-saved"></a>Automatisk etikett på tjänstsidan när innehåll redan har sparats

Den här metoden kallas automatisk klassificering med känslighetsetiketter. Du kanske också hör det som automatisk märkning för data i vila (för dokument i SharePoint och OneDrive) och data som överförs (för e-post som skickas eller tas emot av Exchange). För Exchange ingår inte e-postmeddelanden i postlådor i vila.
 
Eftersom den här etiketten används av själva tjänsten i stället för av användarprogram behöver du inte oroa dig för vilka appar användarna har och vilken version. Den här funktionen är därför omedelbart tillgänglig i hela organisationen och lämplig för att märka med skalan. Principer för automatisk etiketter stöder inte rekommenderad märkning eftersom användaren inte interagerar med märkningsprocessen. Administratören kör i stället principerna i simuleringsläge för att säkerställa korrekt märkning av innehåll innan etiketten faktiskt används.

Konfigurationsinstruktioner finns [i Konfigurera principer för automatisk etikettering för SharePoint, OneDrive och Exchange.](../compliance/apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)

För datasekretess på webbplatser av intresse kan du skicka känslighetsetiketter för automatisk kryptering av innehåll som innehåller känslig personlig information.

## <a name="data-loss-prevention"></a>Skydd mot dataförlust 

Du kan använda skydd mot [dataförlust (DLP)](../compliance/data-loss-prevention-policies.md) i Microsoft 365 för att identifiera, varna och blockera riskabel, oavsiktlig eller olämplig delning, t.ex. delning av data som innehåller personlig information, både internt och externt.

Med DLP kan du:

- Identifiera och övervaka riskfyllda delningsaktiviteter.
- Utbilda användare med sammanhangsbaserade riktlinjer för att fatta rätt beslut.
- Tillämpa dataanvändningsprinciper på innehåll utan att hindra produktiviteten.
- Integrera med klassificering och märkning för att identifiera och skydda data när de delas.

### <a name="supported-workloads-for-dlp"></a>Arbetsbelastningar som stöds för DLP

Med en DLP-princip i Microsoft 365 efterlevnadscenter kan du identifiera, övervaka och automatiskt skydda känsliga objekt på många platser i Microsoft 365, till exempel Exchange Online, SharePoint, OneDrive och Microsoft Teams.

Du kan till exempel identifiera alla dokument som innehåller ett kreditkortsnummer som lagras på en OneDrive-webbplats, eller så kan du övervaka bara OneDrive-webbplatserna för vissa personer.

Du kan också övervaka och skydda känsliga objekt i lokalt installerade versioner av Excel, PowerPoint och Word, som omfattar möjligheten att identifiera känsliga objekt och tillämpa DLP-principer. DLP ger kontinuerlig övervakning när personer delar innehåll från dessa Office-program.

![Arbetsbelastningar som stöds för DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-supported-workloads.png)

I den här bilden visas ett exempel på hur DLP skyddar personliga data.

![Exempel på skydd av personuppgifter med DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-use.png)

DLP används för att identifiera ett dokument eller e-postmeddelande som innehåller en hälsopost och blockerar sedan automatiskt åtkomsten till dokumentet eller blockerar e-post från att skickas. DLP meddelar sedan mottagaren med ett principtips och skickar en avisering till slutanvändaren och administratören.

### <a name="planning-for-dlp"></a>Planering för DLP

Planera DLP-principerna för: 

- Dina affärskrav.

- En riskbaserad bedömning av företaget enligt beskrivningen i utvärdering av [datasekretessrisker och identifiera känsliga objekt.](information-protection-deploy-assess.md)

- Andra mekanismer för informationsskydd och styrning på plats eller vid planering av datasekretess.

- De typer av känslig information som du har identifierat för personliga data baserat på ditt utvärderingsarbete enligt beskrivningen i bedömningen av sekretessrisker för data och [identifiera känsliga objekt.](information-protection-deploy-assess.md) Villkoren för DLP-principen kan baseras på både känsliga informationstyper och bevarandeetiketter.

- De bevarandeetiketter du måste ange DLP-villkor för. Mer information [finns i artikeln om reglerad datasekretess](information-protection-deploy-govern.md) i din organisation.

- Löpande hantering av DLP-principer, som kräver att någon i organisationen driver och finjusterar principer för ändringar i typer av känslig information, bevarandeetiketter, föreskrifter och efterlevnadsprinciper.

Även om känslighetsetiketter inte kan användas under DLP-principvillkor kan vissa skyddsscenarier för att förhindra åtkomst vara uppnåbara med bara känslighetsetiketter som kan tillämpas automatiskt baserat på typer av känslig information. Om det finns robust känslighetsetiketter bör du överväga om DLP ska användas för att förstärka skyddet eftersom:

  - DLP kan förhindra delning av filer. Känslighetsetiketter kan bara förhindra åtkomst.

  - DLP har mer detaljerade nivåer av kontroll när det gäller regler, villkor och åtgärder.

  - DLP-principer kan tillämpas på chatt- och kanalmeddelanden i Teams. Känslighetsetiketter kan bara användas i dokument och e-post.


### <a name="dlp-policies"></a>DLP-principer

DLP-principer konfigureras i administrationscentret för Microsoft-efterlevnad och anger skyddsnivå, vilken typ av känslig information som principen letar efter och målarbetsbelastningen. Grundkomponenterna består av att identifiera skyddet och typerna av data.

![DLP-principkonfiguration i Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-config.png)

Här är en DLP-exempelprincip för information om GDPR.

![Exempel på DLP-policy för information om GDPR](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-policy.png)

I [den här artikeln](../compliance/create-test-tune-dlp-policy.md) finns mer information om hur du skapar och tillämpar DLP-principer.

### <a name="protection-levels-for-data-privacy"></a>Skyddsnivåer för datasekretess

I följande tabell finns tre konfigurationer av att öka skyddet med DLP.

![Skyddsnivåer för datasekretess med DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-protection-levels.png)

Den första konfigurationen, information, kan användas som en utgångspunkt för och en lägsta nivå av skydd för att tillgodose efterlevnadsbehoven för bestämmelser om datasekretess.

>[!Note]
>I och med att skyddsnivån ökar kommer möjligheten för användare att dela och få åtkomst till information att minska i vissa fall och potentiellt kan påverka deras produktivitet eller förmåga att slutföra dagliga uppgifter.
>

För att hjälpa dina anställda att fortsätta vara produktiva i en säkrare miljö när de ökar skyddsnivåerna, bör du ta dig tid att utbilda dem om nya säkerhetsprinciper och -metoder.

### <a name="example-of-using-sensitivity-labels-with-dlp"></a>Exempel på användning av känslighetsetiketter med DLP

Känslighetsetiketter kan fungera tillsammans med DLP för att tillhandahålla datasekretess i en miljö med mycket hög sekretess. Här är de viktigaste stegen i den integrerade distributionen:

1. Föreskrifter och andra affärskrav för datasekretess har dokumenterats.
2. Måldatakällor, typer och ägarskap karaktäriseras i förhållande till problem med datasekretess.
3. En övergripande strategi för att hantera krav samt skydda och reglera surfpunkter för datasekretess upprättas.
4. En fasad handlingsplan för att ta itu med strategi för datasekretesskontroller har satts i kraft.

När de här elementen har fastställts kan du använda typer av känslig information, känslighetsetiketter för taxonomi och DLP-principer tillsammans. I den här bilden visas ett exempel.

![Exempel på känslighetsetiketter som fungerar med DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

[Visa en större version av den här bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

Här är några scenarier för dataskydd som använder DLP- och känslighetsetiketter tillsammans enligt bilden.

| Scenario | Process |
|:-------|:-----|
| A | <ol><li>Känslighetsetiketter för innehåll publiceras av en administratör för användare och grupper för manuell eller automatisk programning av innehåll och e-post. </li><li>Användare A tillämpar etiketterna manuellt eller automatiskt när de interagerar med innehåll, med kryptering eller andra inställningar. </li><li>Användare A skickar ett skyddat e-postmeddelande eller en fil till användare B, en gästanvändare. </li></ol> |
| B | DLP-princip som publicerats av en administratör för användare A blockerar användare A från att skicka e-post och/eller fil till användare B. |
| C |  Känslighetsetikett med inställningen "ägaren kan inte bjuda in gäster" publiceras till Användare A, som upprättar ett Teams-team eller en SharePoint-webbplats. En annan användare på webbplatsen försöker dela en fil med användare B, men DLP blockerar den. |
| D | Känslighetsetikett för automatiskt program på webbplatsinnehåll publiceras på en eller flera webbplatser, vilket ger ytterligare en skyddsnivå, vilket resulterar i en skyddad webbplats. |
|||

## <a name="office-365-message-encryption-ome-new-capabilities"></a>Nya funktioner för meddelandekryptering (OME) i Office 365

Personer använder ofta e-post för att utbyta känsliga objekt, till exempel patientinformation eller kund- och personalinformation. Kryptering av e-postmeddelanden säkerställer att endast tilltänkta mottagare kan visa meddelandeinnehållet.

Med [OME](../compliance/ome.md)kan du skicka och ta emot krypterade meddelanden mellan personer inom och utanför organisationen. OME fungerar med Outlook.com, Yahoo!, Gmail och andra e-posttjänster. OME ser till att endast tilltänkta mottagare kan visa meddelandeinnehållet.

För datasekretess använder du OME för att skydda interna meddelanden som innehåller känsliga objekt. Meddelandekryptering i Office 365 är en onlinetjänst som bygger på Microsoft Azure Rights Management (Azure RMS) som är en del av Azure Information Protection. Det omfattar principer för kryptering, identitet och auktorisering för att skydda din e-post. Du kan kryptera meddelanden med hjälp av rättighetshanteringsmallar, alternativet Vidarebefordra inte och alternativet endast kryptera.

Du kan också definiera e-postflödesregler för att tillämpa det här skyddet. Du kan till exempel skapa en regel som kräver kryptering av alla meddelanden som är adresserade till en viss mottagare, eller som innehåller specifika nyckelord ord i ämnesraden, och även ange att mottagarna inte kan kopiera eller skriva ut innehållet i meddelandet.

Dessutom hjälper [OME](../compliance/ome-advanced-message-encryption.md) Avancerad meddelandekryptering dig att uppfylla efterlevnadskrav som kräver mer flexibla kontroller över externa mottagare och deras åtkomst till krypterade e-postmeddelanden. Med OME-avancerad meddelandekryptering i Microsoft 365 kan du styra känsliga e-postmeddelanden som delas utanför organisationen med automatiska principer som identifierar typer av känslig information. 

För datasekretess kan du ange ett utgångsdatum och återkalla meddelanden om du behöver dela e-post med en extern part. Du kan bara återkalla och ange ett utgångsdatum för meddelanden som skickas till externa mottagare.

### <a name="secure-email-scenarios-comparison-with-ome-and-sensitivity-labels"></a>Säker jämförelse av e-postscenarier med OME och känslighetsetiketter

OME- och känslighetsetiketter som används för e-post med kryptering har viss överlappning, så det är viktigt att förstå vilka scenarier som antingen kan gälla för, som visas i den här tabellen.

| Scenario | Känslighetsetiketter | OME |
|:-------|:-----|:-------|
| Internt + partners <br> Kommunicera och samarbeta säkert mellan interna användare och betrodda partner | Rekommendera – etiketter med helt anpassad klassificering och skydd | Ja – Endast kryptera eller vidarebefordra inte skydd utan klassificering |
| Externa parter <br> Kommunicera och samarbeta säkert med externa/konsumentanvändare | Ja – fördefiniera mottagare i etiketten | Rekommendera – realtidsskydd baserat på mottagare |
| Internt + partners, med utgångs-/återkallelse <br> Kontrollera åtkomst till e-post och innehåll med interna användare och betrodda partner med utgångs- och återkallelse | Rekommendera – helt anpassat skydd med åtkomstlängd och användaren kan manuellt spåra och återkalla filer | Nej – ingen återkallelse eller utgång för intern e-post |
| Externa parter med utgång/återkallelse <br> Kontrollera åtkomst till e-post och innehåll med externa/konsumentanvändare med utgångsdatum och återkallelse | Ja – användaren kan spåra filer manuellt | Rekommenderade (E5) – administratören kan återkalla e-post & Säkerhets- och efterlevnadscenter |
| Automatisk etikettering <br> Organisationen vill automatiskt skydda e-post/bifogade filer med känsligt innehåll och/eller specifika mottagare | Rekommenderade (E5) – automatisk märkning i Exchange- och Outlook-klienter, förstärker e-postflödesregler och DLP-principen | Ja – e-postflödesregler och DLP-princip med endast Kryptera eller Vidarebefordra inte |
||||

Det kommer också att finnas skillnader mellan de här två metoderna för slutanvändare och administratörer.

## <a name="teams-with-protection-for-highly-sensitive-data"></a>Team med skydd för mycket känsliga data

Organisationer som planerar att lagra personuppgifter som omfattas av sekretessregler för data i Teams finns i Konfigurera ett [team](secure-teams-security-isolation.md)med säkerhetsisolering, som ger detaljerad vägledning och konfigurationssteg för:

- Identitets- och enhetsåtkomst
- Skapa ett privat team
- Nedlåst behörighet för underliggande gruppwebbplatser
- En gruppbaserad känslighetsetikett med kryptering
