---
title: Skydda information som omfattas av datasekretess
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
description: Distribuera Microsoft 365 säkerhets- och efterlevnadsfunktioner och skydda din personliga information.
ms.openlocfilehash: 7325aad0392d559703199c81f2544a582d7eadcb
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287753"
---
# <a name="protect-information-subject-to-data-privacy-regulation"></a>Skydda information som omfattas av datasekretess

Ett antal kontroller för informationsskydd kan användas i din prenumeration för att uppfylla krav och bestämmelser gällande datasekretess. Dessa omfattar Allmän dataskyddsförordning (GDPR), HIPAA-HITECH (United States Health Care Privacy Act), California Consumer Protection Act (CCPA) och Brazil Data Protection Act (LGPD).

Dessa kontroller finns inom följande lösningsområden:

- Känslighetsetiketter
- Skydd mot dataförlust (DLP)
- Meddelandekryptering i Office (OME)
- Teams och åtkomstkontroller för webbplatser

![Viktiga tjänster för att skydda personlig information som omfattas av datasekretessförordningen](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-grid.png)

> [!NOTE]
> Den här lösningen beskriver säkerhets- och efterlevnadsfunktioner för att skydda information som omfattas av bestämmelser om datasekretess. En fullständig lista över säkerhetsfunktioner i Microsoft 365 finns Microsoft 365 [säkerhetsdokumentation.](../security/index.yml) En fullständig lista över efterlevnadsfunktioner i Microsoft 365 finns Microsoft 365 [kompatibilitetsdokumentation.](../compliance/index.yml)

## <a name="data-privacy-regulations-that-impact-information-protection-controls"></a>Bestämmelser om datasekretess som påverkar informationsskyddskontrollerna

Här är en exempellista över bestämmelser om datasekretess som kan gälla informationsskyddskontroller:

- GDPR, artikel 5(1)(f))
- GDPR-artikel (32)(1)(a)
- LGPD, artikel 46
- HIPAA-HITECH (45 CFR 164.312(e)(1))
- HIPAA-HITECH (45 C.F.R. 164.312(e)(2)(ii))

Mer information [om dessa finns i bedöma risker för datasekretess](information-protection-deploy-assess.md) och identifiera känsliga objekt.

Bestämmelser om datasekretess för informationsskydd rekommenderas:

- Skydd mot förlust eller obehörig åtkomst, användning och/eller överföring.
- Riskbaserad tillämpning av skyddsmekanismer.
- Användning av kryptering där det är lämpligt.

Din organisation kan också vilja skydda innehåll Microsoft 365 andra syften, till exempel för andra efterlevnadsbehov eller av företagsskäl. Etablering av ditt informationsskyddssystem för datasekretess bör göras som en del av den övergripande planeringen, implementeringen och hanteringen av informationsskydd.

För att hjälpa dig att komma igång med ett informationsskyddsschema i Microsoft 365 innehåller följande avsnitt en kort lista med relaterade funktioner och förbättringsåtgärder för Microsoft 365. Listan innehåller funktioner och förbättringsåtgärder som är tillämpliga i datasekretessbestämmelser. Listan innehåller emellertid inte äldre tekniker om det finns en nyare funktion som till stor del ersätter den äldre. Information Rights Management (IRM) för SharePoint och OneDrive inte ingår i listan men känslighetsetiketter ingår.

## <a name="managing-information-protection-in-microsoft-365"></a>Hantera informationsskydd i Microsoft 365

Microsofts [informationsskyddslösningar](../compliance/information-protection.md) omfattar ett antal integrerade funktioner i Microsoft 365, Microsoft Azure och Microsoft Windows. I Microsoft 365 omfattar informationsskyddslösningar:

- [Typer av känslig information](../compliance/sensitive-information-type-entity-definitions.md) (beskrivs i utvärdera [datasekretessrisker och identifiera känsliga objekt)](information-protection-deploy-assess.md)
- [Känslighetsetiketter](../compliance/sensitivity-labels.md)
  - Service/container-nivå
  - Klient/innehållsnivå
  - Automatiserat för data i vila i SharePoint och OneDrive
- Skydd mot dataförlust (DLP)
- [Microsoft 365 Dataförlustskydd i slutpunkt](../compliance/endpoint-dlp-learn-about.md)
- [Meddelandekryptering i Office 365 funktioner (OME) och](../compliance/ome.md) avancerad [meddelandekryptering](../compliance/ome-advanced-message-encryption.md) i OME

Dessutom är skydd på webbplats- och biblioteksnivå viktiga mekanismer som ska ingå i alla skyddsscheman.

Information om andra funktioner för informationsskydd utanför Microsoft 365 finns i:

- [Microsoft Cloud Application Security (MCAS)](/cloud-app-security/)
- [Azure Information Protection](/azure/information-protection/what-is-information-protection)
- [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)
- [Windows Information Protection](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)

## <a name="sensitivity-labels"></a>Känslighetsetiketter

Med känslighetsetiketter från Microsoft Information Protection kan du klassificera och skydda organisationens data utan att hindra användarnas produktivitet och deras förmåga att samarbeta.

> [!div class="mx-imgBorder"]
> ![Känslighetsetiketter i Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-labels.png)

### <a name="prerequisites-for-sensitivity-labels"></a>Förutsättningar för känslighetsetiketter

Utför de här aktiviteterna innan du implementerar någon av de känslighetsetikettsbaserade funktionerna som är markerade nedan:

1. Förstå följande:
   - **Affärskrav.** Etablera affärsorsaker till att använda känslighetsetiketter i ditt företag. Till exempel dina datasekretesskrav för informationsskydd.
   - **Funktioner för känslighetsetikett.** Känslighetsetiketter kan bli komplexa, så läs dokumentationen för [känslighetsetiketter innan](../compliance/sensitivity-labels.md) du börjar.
   - **Viktiga saker att komma ihåg** Känslighetsetiketter hanteras i administrationscentret för Microsofts efterlevnad, men alternativen för mål och program varierar avsevärt.
      - Det finns känslighetsetiketter för webbplatser, grupper och Teams på behållarnivån (inställningarna gäller inte för innehåll i behållaren). Dessa publiceras för användare och grupper som använder dem när en webbplats, grupp eller team etableras.
      - Det finns känslighetsetiketter för aktivt innehåll. Dessa publiceras även för användare eller grupper, som antingen tillämpar dem manuellt eller så används de automatiskt när:
        - Filen öppnas/redigeras/sparas, antingen på användarens skrivbord eller på en SharePoint webbplats.
        - Ett e-postmeddelande utkast och skickas.
      - Det finns känslighetsetiketter för automatisk tillämpning till filer i vila i SharePoint och OneDrive utöver e-postmeddelanden som överförs via Exchange. De riktar sig antingen till alla webbplatser eller specifika och gäller automatiskt för filerna som finns vi i dessa miljöer.

2. Rationalisera aktuell känslighet med tidigare eller alternativa metoder

   - Azure Information Protection

      Det aktuella känslighetsetikettsschemat kan behöva förenas med eventuell befintlig Azure Information Protection-märkningsimplementering. [](../compliance/sensitivity-labels.md#sensitivity-labels-and-azure-information-protection)
   - OME

      Om du planerar att använda moderna känslighetsetiketter för e-postskydd och befintliga metoder för e-postkryptering som OME finns kan de finnas tillsammans, men du bör förstå scenarier som antingen ska användas. Se Meddelandekryptering i Office 365 nya funktioner [(OME),](#office-365-message-encryption-ome-new-capabilities)som innehåller en tabell som jämför skydd av modern känslighetsetiketttyp med OME-baserat skydd.

3. Planera för integration i ett bredare informationsskyddsschema. Utöver samexistens med OME kan känslighetsetiketter användas längs med sidan funktioner som Microsoft 365 skydd mot dataförlust (DLP) och Microsoft Cloud App Security. Läs [Microsoft Information Protection i Microsoft 365](../compliance/information-protection.md) för att uppnå sekretessrelaterade informationsskyddsmål.

4. Utveckla en känslighetsetikettklassificering och ett kontrollschema. Se [Taxonomi för dataklassificering och känslighetsetikett.](https://aka.ms/dataclassificationwhitepaper)

### <a name="general-guidance"></a>Allmän vägledning

1. **Schemadefinition.** Innan du använder tekniska funktioner för att tillämpa etiketter och skydd bör du arbeta i hela organisationen för att definiera ett klassificeringsschema. Du kanske redan har ett klassificeringsschema, vilket gör det enklare att lägga till personliga data.
2. **Komma igång.** Börja med att bestämma antalet och namnen på etiketterna som ska implementeras. Gör den här aktiviteten utan att bekymra dig om vilken teknik som ska användas och hur etiketter används. Använd det här schemat globalt i hela organisationen, inklusive data som finns lokalt och i andra molntjänster.
3. **Ytterligare rekommendationer** När du utformar och implementerar principer, etiketter och villkor bör du överväga att följa de här rekommendationerna:

   - **Använd befintligt klassificeringsschema (om det finns något).** Många organisationer använder redan dataklassificering i någon form. Utvärdera det befintliga etikettschemat noggrant och använd om möjligt det som det är. Användning av välbekanta etiketter som känns igen för slutanvändarna kommer att vara ett sätt att öka införandet.
   - **Börja liten.** Det finns praktiskt taget ingen gräns för antalet etiketter du kan skapa. Införande av stora mängder etiketter och underetiketter kan emellertid ta lång tid.
   - **Använd scenarier och användningsfall.** Identifiera vanliga användningsfall inom organisationen och använd scenarier som härleds från de datasekretessföreskrifter som du är ämne för. Kontrollera att konfigurationen av denvisionerade etiketten och klassificeringen fungerar i praktiken.
   - **Fråga alla förfrågningar om en ny etikett.** Behöver varje scenario eller användningsfall en ny etikett eller kan du använda det du redan har? Om du behåller så få etiketter som möjligt blir det bättre om du använder dem.
   - **Använd underetiketter för huvudavdelningar.** Vissa avdelningar kommer att ha särskilda behov som kräver särskilda etiketter. Definiera de här etiketterna som underetiketter för en befintlig etikett och överväg att använda omfattningsprinciper som är tilldelade till användargrupper istället för globalt.
   - **Överväg principer med begränsad omfattning.** Principer som riktar sig till delmängder av användare förhindrar att etiketter överbelastas. Med en begränsad princip kan du tilldela roll- eller avdelningsspecifika etiketter eller underetiketter till bara anställda som arbetar för den specifika avdelningen.
   - **Använd beskrivande etikettnamn.** Försök att inte använda jargong, standarder eller förkortningar som etikettnamn. Försök att använda namn som får användaren att använda för att förbättra införandet. I stället för att använda etiketter som PII, HIPAA, LBI, MBI och HBI bör du överväga namn som Icke-företag, Offentlig, Allmänt, Konfidentiellt och Konfidentiellt.

### <a name="create-and-deploy-sensitivity-labels-for-sites-groups-and-teams"></a>Skapa och distribuera känslighetsetiketter för webbplatser, grupper och team

När du skapar [känslighetsetiketter](../compliance/sensitivity-labels-teams-groups-sites.md) i Microsoft 365 Efterlevnadscenter kan du nu använda dem på följande behållare:

- Microsoft Teams webbplatser
- Microsoft 365 grupper (tidigare Office 365)
- SharePoint webbplatser

Använd följande etikettinställningar för att skydda innehållet i de här behållarna:

- Sekretess (offentlig eller privat) Microsoft 365 gruppanslutna Teams webbplatser
- Åtkomst för externa användare
- Åtkomst från ohanterade enheter

För datasekretess: För att förhindra extern delning för behållare som ska användas för lagring av innehåll med känsliga personuppgifter markerar du filer som innehåller data som privata och kräver hanterade enheter.

### <a name="create-and-deploy-sensitivity-labels-for-content"></a>Skapa och distribuera känslighetsetiketter för innehåll

Med känslighetsetiketter för filer kan du kryptera innehåll, vattenstämpla innehållet och definiera andra kontroller för innehåll i Office-program, till exempel innehåll Outlook och Office på webben.

När du är redo att börja skydda organisationens data med känslighetsetiketter:

1. **Skapa etiketterna.** Skapa och namnge känslighetsetiketterna enligt organisationens klassificeringstaxonomi för olika känslighetsnivåer i innehållet. Mer information om hur du utvecklar en klassificerings taxonomi finns i informationsbladet [Taxonomi för dataklassificering och känslighetsetikett](https://aka.ms/dataclassificationwhitepaper).
2. **Definiera vad varje etikett kan göra.** Konfigurera de skyddsinställningar du vill koppla till varje etikett. Du kanske till exempel vill att innehåll med lägre känslighet (t.ex. en Allmänt-etikett) bara ska ha ett sidhuvud eller en sidfot, medan innehåll med högre känslighet (t.ex. en "Konfidentiellt"-etikett) ska ha en vattenstämpel och ha kryptering aktiverad.
3. **Publicera etiketterna.** När du har konfigurerat känsliga etiketter kan du publicera dem med hjälp av en etikett policy. Bestäm vilka användare och grupper som ska ha etiketterna och vilka principinställningar som ska användas. En enstaka etikett kan återanvändas. Du definierar det en gång och sedan kan du inkludera det i flera etikettprinciper som tilldelats olika användare.

När du publicerar känslighetsetiketter från Microsoft 365 Efterlevnadscenter börjar de visas i [Office-appar](../compliance/sensitivity-labels-office-apps.md) för att användare ska klassificera och skydda innehåll när det skapas eller redigeras.

![Distributionsflöde för känslighetsetikett i Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-label-flow.png)

För datasekretess kan du manuellt tillämpa en känslighetsetikett med kryptering och andra regler för e-post eller innehåll som innehåller känslig personlig information.

> [!NOTE]
> Känslighetsetiketter med aktiverad kryptering för e-post har en del överlappande funktioner med OME. Se [Jämförelse av säkra e-postscenarier med OME och känslighetsetiketter.](#secure-email-scenarios-comparison-with-ome-and-sensitivity-labels)

### <a name="client-side-auto-labeling-when-users-edit-documents-or-compose-emails"></a>Automatisk etikett på klientsidan när användare redigerar dokument eller skriver e-postmeddelanden

När du skapar en känslighetsetikett kan du [automatiskt](../compliance/apply-sensitivity-label-automatically.md) tilldela etiketten till innehåll, inklusive e-post när den matchar villkor som du anger.

Det är viktigt att kunna använda känslighetsetiketter på innehåll automatiskt eftersom:

- Du behöver inte träna dina användare när de använder var och en av dina klassificeringar.
- Du behöver inte förlita dig på att användare ska klassificera allt innehåll på rätt sätt.
- Användarna behöver inte längre veta om dina principer – de kan istället fokusera på sitt arbete.

Automatisk märkning stöder rekommendation av en etikett för användarna samt att automatiskt använda en etikett. I båda fallen bestämmer användaren om du vill acceptera eller avvisa etiketten för att säkerställa rätt etikettering av innehållet.

På den här sidan i klienten finns det minimalt med dokument. det innebär att du inte kan använda etiketter. Det är dock inga klient program som har stöd för automatisk etikettering. Den här funktionen stöds av den enhetliga azure Information Protection-märkningsklienten och vissa [versioner av Office program.](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)

Konfigurationsinstruktioner finns [i Konfigurera automatisk märkning för Office appar](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

För datasekretess tillämpar du automatiskt känslighetsetiketter för innehåll som innehåller känslig personlig information.

### <a name="service-side-auto-labeling-when-content-is-already-saved"></a>Automatisk etikett på tjänstsidan när innehåll redan har sparats

Den här metoden kallas för automatisk klassificering med känslighetsetiketter. Du kan även höra det som kallas automatisk märkning för data i vila (för dokument i SharePoint och OneDrive) och data som överförs (för e-post som skickas eller tas emot av Exchange). Till Exchange inkluderas inte e-postmeddelanden i postlådor i vila.

Eftersom den här etiketten används av själva tjänsten i stället för av användarprogram behöver du inte oroa dig för vilka appar användarna har och vilken version. Därför är den här funktionen omedelbart tillgänglig i hela organisationen och lämpar sig för etikettering vid skalan. Automatiskt märkta principer har inte stöd för Rekommenderad etikett eftersom användaren inte interagerar med namngivnings processen. I stället körs principerna i simuleringsläge för att säkerställa rätt etikettering av innehållet innan etiketten tillämpas.

Konfigurationsinstruktioner finns i Konfigurera principer för automatisk märkning [för SharePoint, OneDrive och Exchange.](../compliance/apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)

För datasekretess på webbplatser som är av intresse kan du trycka på känslighetsetiketter för automatisk kryptering av innehåll som innehåller känslig personlig information.

## <a name="data-loss-prevention"></a>Dataförlustskydd

Du kan använda skydd mot [dataförlust i Microsoft 365](../compliance/dlp-learn-about-dlp.md) för att upptäcka, varna och blockera riskabel, oavsiktlig eller olämplig delning, t.ex. delning av data som innehåller personlig information, både internt och externt.

Med DLP kan du:

- Identifiera och övervaka riskfyllda delningsaktiviteter.
- Utbilda användare med sammanhangsbaserade vägledning för att fatta rätt beslut.
- Tillämpa dataanvändningsprinciper på innehåll utan att hindra produktiviteten.
- Integrera med klassificering och märkning för att identifiera och skydda data när de delas.

### <a name="supported-workloads-for-dlp"></a>Arbetsbelastningar som stöds för DLP

Med en DLP-princip i Microsoft 365 Efterlevnadscenter kan du identifiera, övervaka och automatiskt skydda känsliga objekt på många platser i Microsoft 365, till exempel Exchange Online, SharePoint, OneDrive och Microsoft Teams.

Du kan till exempel identifiera alla dokument som innehåller kreditkortsnummer som lagras på alla OneDrive-webbplatser eller så kan du övervaka endast OneDrive av specifika personer.

Du kan även övervaka och skydda känsliga objekt i lokalt installerade versioner av Excel, PowerPoint och Word, som omfattar möjligheten att identifiera känsliga objekt och tillämpa DLP-principer. DLP ger kontinuerlig övervakning när personer delar innehåll från dessa Office program.

> [!div class="mx-imgBorder"]
> ![Arbetsbelastningar som stöds för DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-supported-workloads.png)

I den här bilden visas ett exempel på hur DLP skyddar personliga data.

> [!div class="mx-imgBorder"]
> ![Exempel på skydd av personuppgifter med DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-use.png)

DLP används för att identifiera ett dokument eller e-postmeddelande som innehåller en hälsopost och blockerar sedan automatiskt åtkomsten till dokumentet eller blockerar e-post från att skickas. DLP skickar sedan ett principtips till mottagaren och skickar en avisering till slutanvändaren och administratören.

### <a name="planning-for-dlp"></a>Planering för DLP

Planera DLP-principerna för:

- Dina affärskrav.

- En riskbaserad bedömning av organisationen enligt beskrivningen i utvärdera [datasekretessrisker och identifiera känsliga objekt.](information-protection-deploy-assess.md)

- Andra mekanismer för informationsskydd och styrning på plats eller vid planering av datasekretess.

- De typer av känslig information som du har identifierat för personuppgifter baserat på ditt utvärderingsarbete enligt beskrivningen i utvärdera datasekretessrisker [och identifiera känsliga objekt.](information-protection-deploy-assess.md) Villkoren för DLP-principen kan baseras på både känslig information och bevarandeetiketter.

- De bevarandeetiketter du måste ange DLP-villkor för. Mer information [finns i den reglerad information som omfattas](information-protection-deploy-govern.md) av sekretessförordningen för data i din organisation.

- Löpande hantering av DLP-principer, vilket kräver att någon i organisationen sköter och finjusterar principer för ändringar i typer av känslig information, bevarandeetiketter, föreskrifter och efterlevnadsprinciper.

Även om känslighetsetiketter inte kan användas i DLP-principvillkor kan vissa skyddsscenarier för att förhindra åtkomst vara uppnåbara med bara känslighetsetiketter som kan tillämpas automatiskt baserat på typer av känslig information. Om robust känslighetsetikett finns bör du överväga om DLP ska användas för att förstärka skyddet eftersom:

  - DLP kan förhindra fildelning. Känslighetsetiketter kan bara förhindra åtkomst.

  - DLP har mer detaljerad kontrollnivå när det gäller regler, villkor och åtgärder.

  - DLP-principer kan tillämpas på Teams chatt- och kanalmeddelanden. Känslighetsetiketter kan endast tillämpas på dokument och e-post.


### <a name="dlp-policies"></a>DLP-principer

DLP-principer konfigureras i administrationscentret för Microsoft-efterlevnad och anger skyddsnivån, vilken typ av känslig information som principen letar efter och målarbetsbelastningen. Deras grundläggande komponenter består av att identifiera skyddet och typerna av data.

> [!div class="mx-imgBorder"]
> ![DLP-principkonfiguration i Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-config.png)

Här är ett exempel på en DLP-policy för information om GDPR.

![Exempel på DLP-policy för information om GDPR](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-policy.png)

I [den här artikeln](../compliance/create-test-tune-dlp-policy.md) finns mer information om hur du skapar och tillämpar DLP-principer.

### <a name="protection-levels-for-data-privacy"></a>Skyddsnivåer för datasekretess

I följande tabell finns tre konfigurationer av ökande skydd med DLP.

![Skyddsnivå för datasekretess med DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-protection-levels.png)

Den första konfigurationen, information, kan användas som en utgångspunkt för och en lägsta skyddsnivå för att uppfylla efterlevnadsbehoven gällande sekretessregler för data.

> [!NOTE]
> I och med att skyddsnivån ökar kommer möjligheten för användare att dela och få åtkomst till information att minska i vissa fall och potentiellt påverka deras produktivitet och möjligheten att slutföra dagliga uppgifter.

För att hjälpa dina anställda att fortsätta vara produktiva i en säkrare miljö när de ökar skyddsnivåerna, bör du ta dig tid att utbilda dem om nya säkerhetsprinciper och -procedurer.

### <a name="example-of-using-sensitivity-labels-with-dlp"></a>Exempel på användning av känslighetsetiketter med DLP

Känslighetsetiketter kan fungera tillsammans med DLP för att tillhandahålla datasekretess i en miljö med hög sekretess. Det här är huvudstegen i den integrerade distributionen:

1. Föreskrifter och andra affärskrav för datasekretess har dokumenterats.
2. Måldatakällor, typer och ägarskap karaktäriseras i förhållande till datasekretessproblem.
3. En övergripande strategi för att uppfylla kraven och skydda och styra surfpunkter för datasekretess upprättas.
4. En fasad handlingsplan för att hantera sekretesskontrollstrategin för data finns på plats.

När de här elementen har fastställts kan du använda känsliga informationstyper, känslighetsetiketter för taxonomi och DLP-principer tillsammans. I den här bilden visas ett exempel.

> [!div class="mx-imgBorder"]
> ![Exempel på känslighetsetiketter som fungerar med DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

[Visa en större version av den här bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

Här är några scenarier för dataskydd som använder DLP och känslighetsetiketter tillsammans enligt bilden.

| Scenario | Process |
|:-------|:-----|
| A | <ol><li>Känslighetsetiketter för innehåll publiceras av en administratör för användare och grupper för manuell eller automatisk programning i innehåll och e-post. </li><li>Användare A tillämpar etiketterna manuellt eller automatiskt när du interagerar med innehåll, med kryptering eller andra inställningar. </li><li>Användare A skickar ett skyddat e-postmeddelande eller en skyddad fil till användare B, en gästanvändare. </li></ol> |
| B | DLP-princip som publicerats av en administratör till Användare A blockerar användare A från att skicka e-post och/eller filen till användare B. |
| C |  Känslighetsetikett med inställningen "ägaren kan inte bjuda in gäster" publiceras till användare A, som anger en Teams grupp eller SharePoint webbplats. En annan användare på webbplatsen försöker dela en fil med användare B, men DLP blockerar den. |
| D | Känslighetsetikett för automatiskt program till webbplatsinnehåll publiceras på en eller flera webbplatser, vilket ger ytterligare ett skyddslager, vilket resulterar i en skyddad webbplats. |
|||

## <a name="office-365-message-encryption-ome-new-capabilities"></a>Meddelandekryptering i Office 365 nya funktioner (OME)

Personer använder ofta e-post för att utbyta känsliga objekt, till exempel patientinformation eller kund- och personalinformation. Kryptering av e-postmeddelanden säkerställer att endast tilltänkta mottagare kan visa meddelandeinnehållet.

Med [OME](../compliance/ome.md)kan du skicka och ta emot krypterade meddelanden mellan personer inom och utanför organisationen. OME fungerar med Outlook.com, Yahoo!, Gmail och andra e-posttjänster. OME ser till att endast tilltänkta mottagare kan visa meddelandeinnehållet.

För datasekretess använder du OME för att skydda interna meddelanden som innehåller känsliga objekt. Meddelandekryptering i Office 365 är en onlinetjänst som bygger på Microsoft Azure Rights Management (Azure RMS) som ingår i Azure Information Protection. Det inkluderar principer för kryptering, identitet och auktorisering för att skydda din e-post. Du kan kryptera meddelanden med hjälp av rättighetshanteringsmallar, alternativet Vidarebefordra inte och alternativet för endast kryptering.

Du kan också definiera e-postflödesregler för att tillämpa det här skyddet. Du kan till exempel skapa en regel som kräver kryptering av alla meddelanden som är adresserade till en viss mottagare, eller som innehåller specifika nyckelord ord i ämnesraden, och även ange att mottagare inte kan kopiera eller skriva ut innehållet i meddelandet.

Dessutom hjälper OME avancerad [meddelandekryptering](../compliance/ome-advanced-message-encryption.md) dig att uppfylla efterlevnadsskyldigheter som kräver mer flexibel kontroll över externa mottagare och deras åtkomst till krypterade e-postmeddelanden. Med OME avancerad meddelandekryptering i Microsoft 365 kan du styra känsliga e-postmeddelanden som delas utanför organisationen med automatiska principer som identifierar typer av känslig information.

Om du vill dela e-post med en extern part kan du ange ett utgångsdatum och återkalla meddelanden om du vill ha datasekretess. Du kan bara återkalla och ange ett utgångsdatum för meddelanden som skickas till externa mottagare.

### <a name="secure-email-scenarios-comparison-with-ome-and-sensitivity-labels"></a>Jämförelse av säkra e-postscenarier med OME och känslighetsetiketter

OME-etiketter och känslighetsetiketter som används för e-post med kryptering har viss överlappning, så det är viktigt att förstå vilka scenarier som antingen kan gälla för, som visas i den här tabellen.

| Scenario | Känslighetsetiketter | OME |
|:-------|:-----|:-------|
| Internal + partners <br> Kommunicera och samarbeta säkert mellan interna användare och betrodda partner | Rekommendera – etiketter med helt anpassad klassificering och skydd | Ja – kryptera endast eller vidarebefordra inte skydd utan klassificering |
| Externa parter <br> Kommunicera och samarbeta säkert med externa/konsumentanvändare | Ja – fördefiniera mottagare i etiketten | Rekommendera – precis i tid-skydd baserat på mottagare |
| Interna + partners, med utgångs-/återkallelse <br> Kontrollera åtkomsten till e-post och innehåll med interna användare och betrodda partner med utgångs- och återkallelse | Rekommendera – fullständigt anpassat skydd med åtkomstlängd och användaren kan manuellt spåra och återkalla filer | Nej – ingen återkallelse eller utgång för intern e-post |
| Externa parter med utgång/återkallelse <br> Kontrollera åtkomsten till e-post och innehåll med externa/konsumentanvändare med utgångsdatum och återkallelse | Ja – användaren kan spåra filer manuellt | Rekommendera (E5) – administratören kan återkalla e-post från & Säkerhets- och efterlevnadscenter |
| Automatisk märkning <br> Organisationen vill automatiskt skydda e-post/bilagor med specifikt känsligt innehåll och/eller specifika mottagare | Recommend (E5) – Automatisk märkning i Exchange och Outlook, förstärker e-postflödesregler och DLP-princip | Ja – e-postflödesregler och DLP-princip med endast krypterande eller vidarebefordra inte-skydd |
||||

Det kommer också att finnas skillnader mellan de här två metoderna för slutanvändare och administratörer.

## <a name="teams-with-protection-for-highly-sensitive-data"></a>Teams skydd för mycket känsliga data

Organisationer som planerar att lagra personliga data som omfattas av sekretessregler i Teams finns i Konfigurera ett [team](secure-teams-security-isolation.md)med säkerhetsisolering , med detaljerade anvisningar och konfigurationssteg för:

- Identitets- och enhetsåtkomst
- Skapa ett privat team
- Nedlåst behörighet för underliggande gruppwebbplatser
- En gruppbaserad känslighetsetikett med kryptering