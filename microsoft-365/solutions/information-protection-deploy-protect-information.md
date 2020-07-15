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
- M365solutions
ms.custom: ''
description: Distribuera säkerhets- och efterlevnadsfunktioner för Microsoft 365 och skydda din personliga information.
ms.openlocfilehash: 99ac0f9e29c161ffa26362976f83584c9b168026
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126460"
---
# <a name="protect-information-subject-to-data-privacy-regulation"></a>Skydda information som omfattas av dataskyddsförordningen

Ett antal kontroller för informationsskydd kan användas i din prenumeration för att tillgodose behov och bestämmelser om efterlevnad av datasekretess. Dessa inkluderar General Data Protection Regulation (GDPR), HIPAA-HITECH (United States health care privacy act), California Consumer Protection Act (CCPA) och Brazil Data Protection Act (LGPD).

Dessa kontroller finns inom följande lösningsområden:

- Känslighetsetiketter
- Skydd mot dataförlust (DLP)
- Kryptering av Office-meddelanden (OME)
- Team och webbplatser får åtkomst till kontroller

![Viktiga tjänster för att skydda personuppgifter som omfattas av dataskyddsförordningen](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-grid.png)

>[!Note]
>Den här lösningen beskriver säkerhets- och efterlevnadsfunktioner för att skydda information som omfattas av datasekretessbestämmelser. En fullständig lista över säkerhetsfunktioner i Microsoft 365 finns i [Microsoft 365-säkerhetsdokumentationen](https://docs.microsoft.com/microsoft-365/security/). En fullständig lista över efterlevnadsfunktioner i Microsoft 365 finns i [Microsoft 365-dokumentation för efterlevnad](https://docs.microsoft.com/microsoft-365/compliance/).
>

## <a name="data-privacy-regulations-that-impact-information-protection-controls"></a>Regler för datasekretess som påverkar informationsskyddskontroller

Här är ett exempel på datasekretessregler som kan relatera till informationsskyddskontroller:

- GDPR Artikel 5.1 f)
- GDPR Artikel 32.1 a
- LGPD Artikel 46
- HIPAA-HITECH (45 CFR 164.312(e)(1))
- HIPAA-HITECH (45 C.F.R. 164.312 e.2 ii)

Se [bedömningen av datasekretessrisker och identifiera artikel om känsliga objekt](information-protection-deploy-assess.md) för mer information om vart och ett av ovanstående.

Dataskyddsbestämmelser för informationsskydd rekommenderar:

- Skydd mot förlust eller obehörig åtkomst, användning och/eller överföring.
- Riskbaserad tillämpning av skyddsmekanismer.
- Användning av kryptering där så är lämpligt.

Din organisation kanske också vill skydda Microsoft 365-innehåll för andra ändamål, till exempel andra efterlevnadsbehov eller av affärsskäl. Upprätta ditt informationsskyddssystem för datasekretess bör göras som en del av övergripande planering, implementering och hantering av informationsskydd.

För att hjälpa dig att komma igång med ett informationsskyddsschema i Microsoft 365 innehåller följande avsnitt en kort lista över relaterade funktioner och förbättringsåtgärder för Microsoft 365. Listan innehåller funktioner och förbättringsåtgärder som är tillämpliga på datasekretessbestämmelser. Listan innehåller dock inte äldre tekniker om det finns en nyare kapacitet som till stor del ersätter den äldre. IRM (Information Rights Management) för SharePoint och OneDrive ingår till exempel inte i listan, men känslighetsetiketter ingår.

## <a name="managing-information-protection-in-microsoft-365"></a>Hantera informationsskydd i Microsoft 365

Microsofts [informationsskyddslösningar](../compliance/protect-information.md) innehåller ett antal integrerade funktioner i Microsoft 365, Microsoft Azure och Microsoft Windows. I Microsoft 365 omfattar informationsskyddslösningar:

- [Tjänstkryptering med kundnyckel](../compliance/customer-key-overview.md)
- [Känsliga informationstyper](../compliance/what-the-sensitive-information-types-look-for.md) (beskrivs i [bedömningen av datasekretessrisker och identifiera artiklar om känsliga objekt)](information-protection-deploy-assess.md)
- [Känslighetsetiketter](../compliance/sensitivity-labels.md) 
  - Service-/containernivå
  - Nivå på klientsidan/innehåll
  - Automatiserat för data-at-rest i SharePoint och OneDrive
- Skydd mot dataförlust (DLP)
- [Office 365 Message Encryption nya funktioner (OME)](../compliance/ome.md) och OME [Advanced Message Encryption](../compliance/ome-advanced-message-encryption.md)

Dessutom är skydd på plats- och biblioteksnivå viktiga mekanismer för att inkludera i alla skyddssystem.

Information om andra funktioner för informationsskydd utanför Microsoft 365 finns i:

- [Microsoft Cloud Application Security (MCAS)](https://docs.microsoft.com/cloud-app-security/)
- [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)
- [Microsoft Slutpunktshanteraren](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)
- [Windows Information Protection](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)

## <a name="sensitivity-labels"></a>Känslighetsetiketter

Med känslighetsetiketter från Microsofts ramverk för informationsskydd kan du klassificera och skydda organisationens data utan att hindra användarnas produktivitet och deras samarbetsförmåga.

![Känslighetsetiketter i Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-labels.png)

### <a name="prerequisites-for-sensitivity-labels"></a>Förutsättningar för känslighetsetiketter

Slutför dessa aktiviteter innan du implementerar någon av de känslighetsetikettbaserade funktioner som markeras nedan:

1. Förstå följande:
   - **Affärskrav.** Fastställa affärsskäl för att tillämpa känslighetsetiketter i företaget. Till exempel dina krav på datasekretess för informationsskydd.
   - **Känslighetsetikettfunktioner.** Känslighetsetikettering kan bli komplex, så se till att läsa dokumentationen för [känslighetsetiketter](../compliance/sensitivity-labels.md) innan du börjar.
   - **Viktiga saker att komma ihåg** Känslighetsetiketter hanteras i administrationscentret för Microsoft Compliance, men inriktnings- och programalternativen varierar avsevärt.
      - Det finns känslighetsetiketter för webbplatser, grupper och Teams på behållarnivå (inställningarna gäller inte för innehåll i behållaren). Dessa publiceras för användare och grupper som tillämpar dem när en webbplats, grupp eller ett team etableras.
      - Det finns känslighetsetiketter för aktivt innehåll. Dessa publiceras också för användare eller grupper, som antingen tillämpar dem manuellt eller så tillämpas de automatiskt när:
        - Filen öppnas/redigeras/sparas, antingen på användarens skrivbord eller på en SharePoint-webbplats.
        - Ett e-postmeddelande utarbetas och skickas.
      - Det finns känslighetsetiketter för automatiskt program till filer i vila i SharePoint och OneDrive förutom e-postmeddelanden under överföring via Exchange. Dessa är inriktade på antingen alla webbplatser eller specifika och gäller automatiskt för filerna i vila i dessa miljöer.

2. Rationalisera aktuell känslighetsmärkning med tidigare eller alternativa metoder

   - Azure Information Protection

      Det aktuella känslighetsetikettschemat kan behöva stämmas av med alla befintliga [implementeringar](../compliance/sensitivity-labels.md#sensitivity-labels-and-azure-information-protection) av Azure Information Protection-märkning.
   - Ome

      Om du planerar att använda modern känslighetsmärkning för e-postskydd och befintliga e-postkrypteringsmetoder som OME finns på plats, kan de samexistera, men du bör förstå de scenarier där antingen bör tillämpas. Se [nya funktioner för office 365-meddelandekryptering (OME),](#office-365-message-encryption-ome-new-capabilities)som innehåller en tabell som jämför det moderna känslighetsetikettskyddet med OME-baserat skydd.

3. Planera för integrering i ett bredare system för informationsskydd. Utöver samexistens med OME kan aktuella känslighetsetiketter användas längs sidan funktioner som Microsoft 365 dataförlustförebyggande (DLP) och Microsoft Cloud App Security. Se [Känslighetsetiketter och Microsoft Cloud App Security](../compliance/sensitivity-labels.md#sensitivity-labels-and-microsoft-cloud-app-security) för att uppnå dina mål för datasekretessrelaterad informationsskydd.

4. Utveckla ett klassificerings- och kontrollschema för känslighetsetikett. Se [Taxonomi för dataklassificering och känslighetsetikett](https://aka.ms/dataclassificationwhitepaper).

### <a name="general-guidance"></a>Allmän vägledning

1. **Schemadefinition.** Innan du använder tekniska funktioner för att använda etiketter och skydd, arbeta i hela organisationen för att definiera ett klassificeringsschema. Du kanske redan har ett klassificeringsschema, vilket gör det enklare att lägga till personuppgifter. 
2. **Jag har börjat.** Börja med att bestämma numret och namnen på etiketterna som ska implementeras. Gör denna aktivitet utan att oroa dig för vilken teknik som ska användas och hur etiketter kommer att tillämpas. Tillämpa det här schemat universellt i hela organisationen, inklusive data som finns lokalt och i andra molntjänster.
3. **Ytterligare rekommendationer** När du utformar och implementerar principer, etiketter och villkor bör du överväga att följa dessa rekommendationer:

   - **Använd befintligt klassificeringsschema (om det finns något).** Många organisationer använder redan dataklassificering i någon form. Utvärdera noggrant det befintliga etikettschemat och använd det om möjligt som det är. Om du använder välbekanta etiketter som känns igen för slutanvändarna skapas det.
   - **Börja i liten skala.** Det finns praktiskt taget ingen gräns för hur många etiketter som du kan skapa. Ett stort antal etiketter och underetiketter kan dock göra det långsammare att anta dem.
   - **Använd scenarier och användningsfall.** Identifiera vanliga användningsfall inom organisationen och använda scenarier som härleds från de datasekretessbestämmelser som du omfattas av. Kontrollera om den tänkta etikett- och klassificeringskonfigurationen fungerar i praktiken.
   - **Ifrågasätt varje begäran om en ny etikett.** Har varje scenario eller användningsfall verkligen behöver en ny etikett eller kan du använda vad du redan har? Att hålla antalet etiketter till ett minimum förbättrar antagandet.
   - **Använd underetiketter för nyckelavdelningar.** Vissa avdelningar har särskilda behov som kräver specifika etiketter. Definiera dessa etiketter som underetiketter till en befintlig etikett och överväg att använda begränsade principer som har tilldelats användargrupper i stället för globalt.
   - **Överväg begränsade principer.** Principer som är inriktade på delmängder av användare förhindrar överbelastning av etiketter. En begränsad princip gör det möjligt att tilldela roll- eller avdelningsspecifika etiketter eller underetiketter till bara medarbetare som arbetar för den specifika avdelningen. 
   - **Använd meningsfulla etikettnamn.** Försök att inte använda jargong, standarder eller förkortningar som etikettnamn. Försök att använda namn som genljuder med slutanvändaren för att förbättra användningen. Istället för att använda etiketter som PII, PCI, HIPAA, LBI, MBI och HBI, överväga namn som icke-business, public, general, konfidentiell och mycket konfidentiell.

### <a name="create-and-deploy-sensitivity-labels-for-sites-groups-and-teams"></a>Skapa och distribuera känslighetsetiketter för webbplatser, grupper och team

När du skapar [känslighetsetiketter](../compliance/sensitivity-labels-teams-groups-sites.md) i Microsoft 365-efterlevnadscentret kan du nu använda dem på följande behållare:

- Microsoft Teams-webbplatser
- Microsoft 365-grupper (tidigare Office 365-grupper)
- SharePoint-webbplatser

Använd följande etikettinställningar för att skydda innehållet i dessa behållare:

- Sekretess (offentlig eller privat) för Microsoft 365 gruppanslutna Teams-webbplatser
- Extern användaråtkomst
- Åtkomst från ohanterade enheter

För datasekretess, för att förhindra extern delning för behållare som kommer att användas för att lagra innehåll med känsliga personuppgifter, markera de filer som innehåller data som privata och kräver hanterade enheter.

### <a name="create-and-deploy-sensitivity-labels-for-content"></a>Skapa och distribuera känslighetsetiketter för innehåll

Med känslighetsetiketter som tillämpas på filer kan du kryptera deras innehåll, vattenstämpel innehållet och definiera andra kontroller för Office-programinnehåll, inklusive Outlook och Office på webben.

När du är redo att börja skydda organisationens data med känslighetsetiketter:

1. **Skapa etiketterna.** Skapa och namnge dina känslighetsetiketter enligt organisationens klassificeringstaxonomi för olika känslighetsnivåer av innehåll. Mer information om hur du utvecklar en klassificeringstaxonomi finns i [faktabladets taxonomi för dataklassificering och känslighetsetikett](https://aka.ms/dataclassificationwhitepaper).
2. **Definiera vad varje etikett kan göra.** Konfigurera de skyddsinställningar som du vill ska associeras med varje etikett. Du kanske till exempel vill att innehåll med lägre känslighet (till exempel en "allmän"-etikett) bara ska ha ett sidhuvud eller en sidfot tillämpat, medan högre känslighetsinnehåll (till exempel en "Konfidentiell" etikett) ska ha en vattenstämpel och ha kryptering aktiverad.
3. **Publicera etiketterna.** När känslighetsetiketterna har konfigurerats publicerar du dem med hjälp av en etikettprincip. Bestäm vilka användare och grupper som ska ha etiketterna och vilka principinställningar som ska användas. En enda etikett kan återanvändas. Du definierar det en gång och sedan kan du inkludera det i flera etikettprinciper som tilldelats olika användare.

När du har publicerat känslighetsetiketter från Microsoft 365-efterlevnadscentret börjar de visas i [Office-appar](../compliance/sensitivity-labels-office-apps.md) så att användarna kan klassificera och skydda innehåll när det skapas eller redigeras.

![Distributionsflöde för känslighetsetikett i Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-label-flow.png)

För datasekretess tillämpar du manuellt en känslighetsetikett med kryptering och andra regler för e-post eller innehåll som innehåller känslig personlig information.

>[!Note]
>Känslighetsetiketter med kryptering aktiverad på e-post har vissa överlappande funktioner med OME. Se [Jämförelse av säkra e-postscenarier med OME- och känslighetsetiketter](#secure-email-scenarios-comparison-with-ome-and-sensitivity-labels).

### <a name="client-side-auto-labeling-when-users-edit-documents-or-compose-emails"></a>Automatisk märkning på klientsidan när användare redigerar dokument eller skriver e-postmeddelanden

När du skapar en känslighetsetikett kan du [automatiskt tilldela den etiketten](../compliance/apply-sensitivity-label-automatically.md) till innehåll, inklusive e-post när den matchar villkor som du anger.

Möjligheten att automatiskt använda känslighetsetiketter på innehåll är viktigt eftersom:

- Du behöver inte träna användarna när du ska använda var och en av dina klassificeringar.
- Du behöver inte förlita dig på att användarna klassificerar allt innehåll korrekt.
- Användarna behöver inte längre känna till dina policyer – de kan i stället fokusera på sitt arbete.

Automatisk märkning stöder att rekommendera en etikett till användare, samt att automatiskt använda en etikett. Men i båda fallen bestämmer användaren om han vill acceptera eller avvisa etiketten för att säkerställa korrekt märkning av innehåll.

Den här etiketten på klientsidan har minimal fördröjning för dokument eftersom etiketten kan användas redan innan dokumentet sparas. Alla klientappar stöder dock inte automatisk märkning. Den här funktionen stöds av azure informationsskydd enhetlig märkning klient, och [vissa versioner av Office-program](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

Konfigurationsinstruktioner finns i [Konfigurera automatisk märkning för Office-appar](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps).

För datasekretess använder du känslighetsetiketter automatiskt för innehåll som innehåller känslig personlig information.

### <a name="service-side-auto-labeling-when-content-is-already-saved"></a>Automatisk etikett på servicesidan när innehållet redan har sparats

Den här metoden kallas automatisk klassificering med känslighetsetiketter. Du kan också höra det kallas automatisk märkning för data i vila (för dokument i SharePoint och OneDrive) och data under överföring (för e-post som skickas eller tas emot av Exchange). För Exchange innehåller den inte e-postmeddelanden i postlådor i vila.
 
Eftersom den här märkningen tillämpas av själva tjänsten i stället för av användarprogrammet behöver du inte oroa dig för vilka appar användarna har och vilken version. Därför är den här funktionen omedelbart tillgänglig i hela organisationen och lämplig för märkning i stor skala. Principer för automatisk märkning stöder inte rekommenderad märkning eftersom användaren inte interagerar med märkningsprocessen. I stället kör administratören principerna i simuleringsläge för att säkerställa korrekt märkning av innehåll innan du faktiskt använder etiketten.

Konfigurationsinstruktioner finns i [Konfigurera principer för automatisk märkning för SharePoint, OneDrive och Exchange](../compliance/apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange).

För datasekretess på webbplatser som berörs, tryck på känslighetsetiketter för automatisk kryptering av innehåll som innehåller känslig personlig information.

## <a name="data-loss-prevention"></a>Förebyggande av dataförlust 

Du kan använda [dataförlustskydd (DLP)](../compliance/data-loss-prevention-policies.md) i Microsoft 365 för att identifiera, varna och blockera riskfylld, oavsiktlig eller olämplig delning, till exempel delning av data som innehåller personlig information, både internt och externt.

Med DLP kan du:

- Identifiera och övervaka riskfyllda delningsaktiviteter.
- Utbilda användarna med vägledning i kontext för att fatta rätt beslut.
- Framtvinga dataanvändningsprinciper på innehåll utan att hämma produktiviteten.
- Integrera med klassificering och märkning för att identifiera och skydda data när de delas.

### <a name="supported-workloads-for-dlp"></a>Arbetsbelastningar som stöds för DLP

Med en DLP-princip i Microsoft 365-efterlevnadscentret kan du identifiera, övervaka och automatiskt skydda känsliga objekt på många platser i Microsoft 365, till exempel Exchange Online, SharePoint, OneDrive och Microsoft Teams.

Du kan till exempel identifiera alla dokument som innehåller ett kreditkortsnummer som lagras på valfri OneDrive-webbplats, eller så kan du bara övervaka OneDrive-webbplatserna för specifika personer.

Du kan också övervaka och skydda känsliga objekt i de lokalt installerade versionerna av Excel, PowerPoint och Word, som innehåller möjligheten att identifiera känsliga objekt och tillämpa DLP-principer. DLP ger kontinuerlig övervakning när personer delar innehåll från dessa Office-appar.

![Arbetsbelastningar som stöds för DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-supported-workloads.png)

Den här bilden visar ett exempel på DLP som skyddar personuppgifter.

![Exempel på att skydda personuppgifter med hjälp av DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-use.png)

DLP används för att identifiera ett dokument eller e-postmeddelande som innehåller en hälsojournal och blockerar sedan automatiskt åtkomsten till dokumentet eller blockerar e-postmeddelandet från att skickas. DLP meddelar sedan mottagaren med ett principtips och skickar en avisering till slutanvändaren och administratören.

### <a name="planning-for-dlp"></a>Planering för DLP

Planera dina DLP-principer för: 

- Dina affärskrav.

- En riskbaserad bedömning av organisationen enligt beskrivningen i [bedömningen av datasekretessrisker och identifiera känsliga objekt artikel](information-protection-deploy-assess.md).

- Andra mekanismer för informationsskydd och styrning finns eller planerar datasekretess.

- De känsliga informationstyper som du har identifierat för personuppgifter baserat på ditt bedömningsarbete enligt beskrivningen i [artikeln bedöm datasekretess och identifiera känsliga objekt.](information-protection-deploy-assess.md) DLP-principvillkor kan baseras på både känsliga informationstyper och lagringsetiketter.

- Behållaniketterna måste du ange DLP-villkor. Mer information [finns i den härskande informationen som omfattas av dataskyddsförordningen i din organisationsartikel.](information-protection-deploy-govern.md)

- Pågående DLP-principhantering, som kräver att någon i organisationen använder och ställer in principer för ändringar i känsliga informationstyper, lagringsetiketter, föreskrifter och efterlevnadsprinciper.

Även om känslighetsetiketter inte kan användas i DLP-principvillkor kan vissa skyddsscenarier för att förhindra åtkomst uppnås med bara känslighetsetiketter som kan tillämpas automatiskt baserat på känsliga informationstyper. Om det finns en robust känslighetsmärkning bör du överväga om DLP ska användas för att öka skyddet eftersom:

  - DLP kan förhindra delning av filer. Känslighetsetiketter kan bara förhindra åtkomst.

  - DLP har mer detaljerade kontrollnivåer när det gäller regler, villkor och åtgärder.

  - DLP-principer kan tillämpas på Teams chatt- och kanalmeddelanden. Känslighetsetiketter kan bara tillämpas på dokument och e-post.


### <a name="dlp-policies"></a>DLP-principer

DLP-principer konfigureras i administrationscentret för Microsoft Compliance och anger skyddsnivån, den känsliga informationstyp som principen söker efter och målarbetsbelastningarna. Deras grundläggande komponenter består i att identifiera skyddet och typerna av uppgifter.

![Konfiguration av DLP-princip i Microsoft 365](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-config.png)

Här är ett exempel DLP politik för medvetenhet om GDPR.

![Exempel på DLP:s policy för att öka GDPR](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-policy.png)

Mer information om hur du skapar och tillämpar DLP-principer finns i [den här artikeln.](../compliance/create-test-tune-dlp-policy.md)

### <a name="protection-levels-for-data-privacy"></a>Skyddsnivåer för datasekretess

I följande tabell visas tre konfigurationer för att öka skyddet med DLP.

![Skyddsnivå för datasekretess med DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-protection-levels.png)

Den första konfigurationen, Medvetenhet, kan användas som utgångspunkt och miniminivå av skydd för att tillgodose efterlevnadsbehov för datasekretessbestämmelser.

>[!Note]
>I takt med att skyddsnivåerna ökar minskar användarnas förmåga att dela och få tillgång till information i vissa fall och kan potentiellt påverka deras produktivitet eller förmåga att utföra dagliga uppgifter.
>

För att hjälpa dina anställda att fortsätta att vara produktiva i en säkrare miljö när du ökar skyddsnivåerna, ta dig tid att utbilda och utbilda dem om nya säkerhetspolicyer och säkerhetsrutiner.

### <a name="example-of-using-sensitivity-labels-with-dlp"></a>Exempel på hur du använder känslighetsetiketter med DLP

Känslighetsetiketter kan arbeta tillsammans med DLP för att tillhandahålla datasekretess i en starkt reglerad miljö. Här är de viktigaste stegen i den integrerade distributionen:

1. Regulatoriska och i övrigt affärskrav för datasekretess dokumenteras.
2. Måldatakällor, typer och ägarskap kännetecknas i förhållande till datasekretessproblem.
3. En övergripande strategi för att ta itu med krav och skydda och styra hotspots för datasekretess upprättas.
4. En stegvis handlingsplan för att ta itu med strategin för kontroll av datasekretess införs.

När dessa element har bestämts kan du använda känsliga informationstyper, din känslighetsmärkningstaxonomi och DLP-principer tillsammans. Den här bilden visar ett exempel.

![Exempel på känslighetsetiketter som arbetar med DLP](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

[Se en större version av den här bilden](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

Här är några dataskyddsscenarier som använder DLP och känslighetsetiketter tillsammans som visas i figuren.

| Scenario | Process |
|:-------|:-----|
| A | <ol><li>Känslighetsetiketter för innehåll publiceras av en administratör till användare och grupper för manuell eller automatisk tillämpning till innehåll och e-post. </li><li>Användare A använder etiketterna manuellt eller automatiskt när de interagerar med innehåll, med kryptering eller andra inställningar. </li><li>Användare A skickar ett skyddat e-postmeddelande eller en skyddad fil till användare B, en gästanvändare. </li></ol> |
| B | DLP-princip som publicerats av en administratör till Användare A blockerar användare A från att skicka e-postmeddelandet och/eller filen till användare B. |
| C |  Känslighetsetikett med inställningen "Ägare kan inte bjuda in gäster" publiceras för Användare A, som etablerar ett Teams-team eller SharePoint-webbplats. En annan användare av webbplatsen försöker selektivt dela en fil med användare B, men DLP blockerar den. |
| D | Känslighetsetikett för automatiskt program till webbplatsinnehåll publiceras på en eller flera platser, vilket ger ett annat skyddslager, vilket resulterar i en skyddad plats. |
|||

## <a name="office-365-message-encryption-ome-new-capabilities"></a>Ome-kryptering (Office 365 Message Encryption) nya funktioner

Människor använder ofta e-post för att utbyta känsliga objekt, till exempel patienthälsoinformation eller kund- och medarbetarinformation. Kryptering av e-postmeddelanden säkerställer att endast avsedda mottagare kan visa meddelandeinnehåll.

Med [OME](../compliance/ome.md)kan du skicka och ta emot krypterade meddelanden mellan personer inom och utanför organisationen. OME fungerar med Outlook.com, Yahoo!, Gmail och andra e-posttjänster. OME hjälper till att säkerställa att endast avsedda mottagare kan visa meddelandeinnehåll.

För datasekretess använder du OME för att skydda interna meddelanden som innehåller känsliga objekt. Office 365 Message Encryption är en onlinetjänst som bygger på Microsoft Azure Rights Management (Azure RMS) som är en del av Azure Information Protection. Detta inkluderar principer för kryptering, identitet och auktorisering för att skydda din e-post. Du kan kryptera meddelanden med hjälp av rättighetshanteringsmallar, alternativet Vidarebefordra inte och alternativet endast kryptera.

Du kan också definiera regler för e-postflöde för att tillämpa det här skyddet. Du kan till exempel skapa en regel som kräver kryptering av alla meddelanden som är adresserade till en viss mottagare, eller som innehåller specifika nyckelordsord på ämnesraden, och även ange att mottagarna inte kan kopiera eller skriva ut innehållet i meddelandet.

Dessutom hjälper OME [Advanced Message Encryption](../compliance/ome-advanced-message-encryption.md) dig att uppfylla efterlevnadsskyldigheter som kräver mer flexibla kontroller över externa mottagare och deras åtkomst till krypterade e-postmeddelanden. Med OME Advanced Message Encryption i Microsoft 365 kan du styra känsliga e-postmeddelanden som delas utanför organisationen med automatiska principer som identifierar känsliga informationstyper. 

Om du behöver dela e-post med en extern part kan du ange ett utgångsdatum och återkalla meddelanden om du behöver dela e-post med en extern part. Du kan bara återkalla och ange ett utgångsdatum för meddelanden som skickas till externa mottagare.

### <a name="secure-email-scenarios-comparison-with-ome-and-sensitivity-labels"></a>Säker jämförelse av e-postscenarier med OME- och känslighetsetiketter

OME och känslighetsetiketter som tillämpas på e-post med kryptering har viss överlappning, så det är viktigt att förstå vilka scenarier som antingen kan gälla för, som visas i den här tabellen.

| Scenario | Känslighetsetiketter | Ome |
|:-------|:-----|:-------|
| Interna + partners <br> Kommunicera och samarbeta säkert mellan interna användare och betrodda partner | Rekommendera – etiketter med helt anpassad klassificering och skydd | Ja – Kryptera endast eller Vidarebefordra inte skydd utan klassificering |
| Externa parter <br> Kommunicera och samarbeta säkert med externa/konsumentanvändare | Ja – fördefiniera mottagare i etikett | Rekommendera – just-in-time skydd baserat på mottagare |
| Internt + partners, med förfallodatum/återkallande <br> Kontrollera åtkomsten för e-post och innehåll med interna användare och betrodda partner med förfallodatum och återkallande | Rekommendera - helt anpassat skydd med åtkomstvaraktighet, kan användaren manuellt spåra och återkalla filer | Nej – ingen återkallning eller förfallodatum för intern post |
| Externa parter med förfallodatum/återkallande <br> Kontrollera åtkomsten till e-post och innehåll med externa/konsumentanvändare med förfallodatum och återkallande | Ja – användaren kan spåra filer manuellt | Rekommendera (E5) – admin kan återkalla e-post från Security & Compliance Center |
| Automatisk märkning <br> Organisationen vill automatiskt skydda e-post/bilagor med specifikt känsligt innehåll och/eller specifika mottagare | Rekommendera (E5) - Automatisk märkning i Exchange- och Outlook-klienter, utökar reglerna för e-postflöde och DLP-princip | Ja - regler för e-postflöde och DLP-princip med Endast kryptera eller Vidarebefordra inte skydd |
||||

Det kommer också att finnas skillnader i slutanvändare och admin erfarenheter mellan dessa två metoder.

## <a name="teams-with-protection-for-highly-sensitive-data"></a>Team med skydd för mycket känsliga data

För organisationer som planerar att lagra personliga data som omfattas av datasekretessbestämmelser i Teams finns [i Konfigurera ett team med säkerhetsisolering](secure-teams-security-isolation.md), som ger detaljerad vägledning och konfigurationssteg för:

- Identitets- och enhetsåtkomst
- Inrättande av ett privat team
- Låsning av underliggande behörigheter för gruppwebbplatser
- En gruppbaserad känslighetsetikett med kryptering
