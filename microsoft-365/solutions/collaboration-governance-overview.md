---
title: Vad är styrning av samarbete?
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-overview
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Läs mer om hur du styr relaterade funktioner i Microsoft 365-grupper, Teams, SharePoint och Yammer.
ms.openlocfilehash: b31e9bf1cd46f94343a489497fb5eb00e138ce60
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916448"
---
# <a name="what-is-collaboration-governance"></a>Vad är styrning av samarbete?

Med samarbetsstyrning hanterar du användarnas åtkomst till resurser, följer dina affärsstandarder och säkerställer säkerheten för dina data.

Organisationer använder i dag en rad olika verktyg. Det finns en grupp utvecklare som använder gruppchatt, cheferna som skickar e-post och hela organisationen som ansluter via företagets sociala nätverk. Flera samarbetsverktyg används eftersom varje grupp är unik och har sina egna funktionella behov och arbetsstil. Vissa använder endast e-post medan andra främst finns i chatten. 

Om användarna anser att de VERKTYG som tillhandahålls av IT inte passar deras behov kommer de antagligen att ladda ned sin favoritapp som stöder deras scenarier. Även om den här processen gör att användarna snabbt kan komma igång, ger det en frustrerande användarupplevelse i hela organisationen med flera inloggningar, problem med att dela och ingen enda plats för att visa innehåll. Det här begreppet kallas "Skuggning IT" och utgör en betydande risk för organisationer. Det minskar möjligheten att hantera användarnas åtkomst, säkerställa säkerhet och tjänstefterlevnad.

Tjänster som Microsoft 365-grupper, Teams och Yammer ger användarna möjlighet och minskar risken för skugg-IT genom att tillhandahålla de verktyg som krävs för att samarbeta. Microsoft 365 har en omfattande uppsättning verktyg för att implementera alla hanteringsfunktioner som din organisation kan behöva. 

![Diagram som visar alternativ för samarbetsstyrning i Microsoft 365](../media/collaboration-governance-overview.png)

Den här serien med artiklar hjälper dig att förstå hur grupper, team och SharePoint-inställningar interagerar, vilka hanteringsfunktioner som är tillgängliga och hur du skapar och implementerar en hanteringsplan för samarbetsfunktionerna i Microsoft 365.

### <a name="setting-up-secure-collaboration-with-microsoft-365"></a>Konfigurera säkert samarbete med Microsoft 365

Det finns många alternativ för distribution av Microsoft 365-grupper och Teams för säkert samarbete i organisationen. Vi rekommenderar att du använder det här styrningsinnehållet tillsammans med Konfigurera säkert samarbete med [Microsoft 365](setup-secure-collaboration-with-teams.md) och tillhörande artiklar för att skapa den bästa samarbetslösningen för din organisation.

### <a name="data-residency"></a>Datahem

Om din organisation är multinationell och du har krav för datalagring för olika platser, ska du ta med [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo) som en del av samarbetsstyrningsplanen.

## <a name="why-microsoft-365-groups-are-important"></a>Varför microsoft 365-grupper är viktiga

Med Microsoft 365-grupper kan du välja en grupp personer som du vill samarbeta med och enkelt skapa en samling med resurser som personerna kan dela. När medlemmar läggs till i gruppen tilldelas automatiskt nödvändiga behörigheter till alla tillgångar som tillhandahålls av gruppen. Både Teams och Yammer använder Microsoft 365-grupper för att hantera medlemskap.

Microsoft 365-grupper innehåller en uppsättning länkade resurser som användarna kan använda för kommunikation och samarbete. Grupper inkluderar alltid en SharePoint-webbplats, Planner, en Power BI-arbetsyta, en postlåda och kalender samt Stream. Beroende på hur du skapar gruppen kan du lägga till andra tjänster som Teams, Yammer och Project.

![Diagram som visar Microsoft 365-grupper och relaterade tjänster](../media/microsoft-365-groups-hub-spoke.png)

|Resurs|Beskrivning|
|:------|:----------|
|[Kalender](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a)|För schemaläggning av händelser relaterade till gruppen|
|[Inkorgen](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22)|För e-postkonversationer mellan gruppmedlemmar. Den här inkorgen har en e-postadress och kan ställas in för att ta emot meddelanden från personer utanför gruppen och även utanför organisationen, ungefär som en traditionell distributionslista.|
|[OneNote-anteckningsbok](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97)|Samla idéer, forskning och information|
|[Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc)|Tilldela och hantera projektuppgifter bland gruppmedlemmarna|
|[Power BI-arbetsyta](/power-bi/collaborate-share/service-new-workspaces)|Ett samarbetsutrymme för data med instrumentpaneler och rapporter|
|[Projekt och översikt](https://support.microsoft.com/project)|Webbaserade projekthanteringsverktyg|
|[SharePoint-gruppwebbplats](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e)|En central lagringsplats för information, länkar och innehåll som rör gruppen|
|[Strömma](https://support.microsoft.com/microsoft-stream)|En tjänst för direktuppspelning av video|
|[Teams](https://support.microsoft.com/teams)|En chattbaserad arbetsyta i Microsoft 365|
|[Yammer-grupp](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)|En gemensam plats för konversationer och för att dela information|

Microsoft 365 Groups innehåller en mängd olika hanteringskontroller, till exempel en förfalloprincip, namnkonventioner och en princip för blockerade ord som hjälper dig att hantera grupper i organisationen. Eftersom grupper styr medlemskapet och åtkomsten till den här resurssviten är hanteringen av grupper en viktig del av samarbetet i Microsoft 365.

## <a name="define-a-collaboration-strategy-for-your-organization"></a>Definiera en samarbetsstrategi för organisationen

Det finns flera platser där ni kan samarbeta och föra konversationer inom Microsoft 365. Att förstå var användare kan starta konversationer kan hjälpa dig att definiera en strategi för kommunikation.

Det finns tre huvudsakliga kommunikationsmetoder som stöds av Microsoft 365:

- Outlook: samarbete via e-post med en delad gruppinkorg och kalender
- Microsoft Teams: En fortlöpande chattbaserad arbetsyta där du kan ha informella konversationer i realtid om olika ämnen, ordnade efter specifika undergrupper
- Yammer: företagets sociala nätverk för samarbete

![Diagram som visar när du kan använda Teams, Yammer och Outlook](../media/inner-loop-outer-loop.png)

- Teams: chattbaserad arbetsyta (samarbete med hög hastighet) – inre slinga
  - Skapat för samarbete med de personer som dina användare arbetar med varje dag
  - Gör att information är lättillgänglig för alla användare på ett och samma sätt
  - Lägga till flikar, kopplingar och robotar
  - Livechatt, ljud-/videokonferens, inspelade möten

- Yammer: ansluta i hela organisationen (företagets sociala nätverk) – yttre slinga
  - Användargrupper – Tvärfunktionella grupper med personer som delar ett gemensamt intresse eller expertis, men som inte nödvändigtvis arbetar tillsammans i det dagliga arbetet
  - Ledningsanslutning, utbildningsgemenskaper, rollbaserade communities

- Postlåda och kalender (e-postbaserat samarbete)
  - Används för riktad kommunikation med en grupp personer
  - Delad kalender för möten med andra gruppmedlemmar
 
När du bestämmer hur du vill använda samarbetsfunktionerna i Microsoft 365 bör du tänka på de här kommunikationsmetoderna och vilka användare som förmodligen kommer att använda dem i olika scenarier.

> [!NOTE]
> När en ny Office 365-grupp skapas via Yammer eller Teams visas inte gruppen i Outlook eller adressboken eftersom den primära kommunikationen mellan dessa användare sker i respektive klienter. Yammer-grupper kan inte anslutas till Teams.


## <a name="best-practices"></a>Metodtips

När du börjar din planeringsprocess för styrning bör du tänka på följande metodtips:

- **Prata med dina användare** – identifiera dina största användare av samarbetsfunktioner och träffa dem för att förstå deras grundläggande affärskrav och använda fallscenarier.

- **Balansera risker och fördelar** – granska dina affärs-, regel-, juridiska och efterlevnadsbehov och planera en lösning som optimerar för alla resultat.

- **Anpassa till olika** organisationer och olika typer av innehåll och scenarier – ta hänsyn till olika behov för olika grupper eller avdelningar och olika typer av innehåll, t.ex. intranätinnehåll eller OneDrive-innehåll för en användare.

- **Justera affärsprioriteringar** – affärsmål hjälper dig att definiera hur mycket tid och energi du behöver för att investera i styrning.

- **Bädda in styrningsbeslut direkt i de lösningar du** skapar – många styrningsbeslut kan implementeras genom att funktioner i Microsoft 365 inaktiveras.


- **Använd en fasad metod** – Först distribuerar du samarbetsfunktionerna till en liten grupp användare. Få feedback från dem, titta efter supportärenden och uppdatera alla nödvändiga inställningar eller processer innan du går vidare till en större grupp.

- **Förstärker med** utbildning – anpassa lösningar som [Microsoft 365](/office365/customlearning) utbildningsvägar för att säkerställa att dina organisationsspecifika förväntningar förstärkers med utbildning från Microsoft.

- **Ha en strategi för att förmedla** principer och riktlinjer för styrning i din organisation – skapa ett Införandecenter för Microsoft 365 i en SharePoint-kommunikationswebbplats för att kommunicera principer och procedurer.

- **Definiera roller och ansvarsområden** – identifiera ditt huvudteam för styrning och arbeta med viktiga styrningsbeslut om etablering och namngivning och extern åtkomst först, och sedan gå igenom de återstående besluten.

- **Gå tillbaka till dina beslut när företaget och tekniken förändras** – möte regelbundet för att granska nya funktioner och nya affärsförväntningar.

Om du vill titta närmare på de här metoderna kan du [läsa Skapa en plan för styrning av samarbete](collaboration-governance-first.md).

## <a name="end-user-impact-and-change-management"></a>Slutanvändareffekter och ändringshantering

Eftersom grupper och team kan skapas på flera sätt rekommenderar vi att du utbildar användarna för att använda den metod som passar bäst för din organisation:

- Om din organisation kommunicerar mest via e-post, instruerar du användarna att skapa grupper i Outlook.
- Om din organisation använder SharePoint mer eller om ni migrerar från SharePoint lokalt, instruerar du användarna att skapa SharePoint-gruppwebbplatser för samarbete.
- Om din organisation har distribuerat Teams, instruerar du användarna att skapa ett team när de behöver ett samarbetsutrymme.

På så sätt undviker du förvirring om användarna inte känner till hur grupper relaterar till sina relaterade tjänster. Mer information om hur du talar om grupper för användarna finns i [Förklara Microsoft 365-grupper för användarna.](../admin/create-groups/explain-groups-knowledge-worker.md)

## <a name="key-governance-capabilities-and-licensing-requirements"></a>Viktiga hanteringsfunktioner och licenskrav

Hanteringsfunktioner för samarbete i Microsoft 365 omfattar funktioner i Microsoft 365, Teams, SharePoint och Azure Active Directory.

| Resurs eller funktion | Beskrivning | Licensiering |
|:----------------------|:------------|:----------|
|Grupp- och webbplatsdelning|Kontrollera om grupper, grupper och webbplatser kan delas med personer utanför organisationen.|Microsoft 365 E5 eller E3|
|Tillåt/blockera domän|Begränsa delning med personer utanför organisationen till personer från specifika domäner.|Microsoft 365 E5 eller E3|
|Skapa webbplatser med självbetjäning|Tillåta eller förhindra användare från att skapa egna SharePoint-webbplatser.|Microsoft 365 E5 eller E3|
|Begränsad webbplats- och fildelning|Begränsa webbplats-, fil- och mappdelning till medlemmar i en viss säkerhetsgrupp.|Microsoft 365 E5 eller E3|
|Skapa begränsade grupper|Begränsa skapande av team och grupper till medlemmar i en viss säkerhetsgrupp.|Microsoft 365 E5 eller E3 med Azure AD Premium- eller Azure AD Basic EDU-licenser|
|Gruppnamnprincip|Framtvinga prefix och suffix för grupp- och gruppnamn.|Microsoft 365 E5 eller E3 med Azure AD Premium- eller Azure AD Basic EDU-licenser|
|Förfalloprincip för grupp|Ställ in inaktiva grupper och team så att de upphör att gälla och tas bort efter en angiven tidsperiod.|Microsoft 365 E5 eller E3 med Azure AD Premium-licenser|
|Gäståtkomst per grupp|Tillåta eller förhindra grupp- och gruppdelning med personer utanför organisationen per grupp.|Microsoft 365 E5 eller E3|

## <a name="collaboration-governance-planning-step-by-step"></a>Planering av samarbetsstyrning steg för steg

Följ de här grundläggande stegen för att skapa en styrningsplan:

1. Överväg viktiga affärsmål och -processer [– skapa en styrningsplan](collaboration-governance-first.md) för att uppfylla behoven i din verksamhet.
2. Förstå inställningar i tjänster – inställningar i grupper och [SharePoint](groups-sharepoint-governance.md) interagerar med varandra, liksom i inställningar i [grupper, SharePoint och Teams](groups-sharepoint-teams-governance.md) och [andra tjänster.](groups-services-interactions.md) Se till att förstå dessa interaktioner när du planerar din strategi för styrning.
3. Planera att hantera användaråtkomst – [planera åtkomstnivån som du vill bevilja användare i grupper, SharePoint och Teams.](groups-teams-access-governance.md)
4. Planera att hantera efterlevnadsinställningar – granska tillgängliga [efterlevnadsalternativ för Microsoft 365-grupper, Teams och SharePoint-samarbeten.](groups-teams-compliance-governance.md)
5. Planera för hantering av kommunikation – granska tillgängliga alternativ [för kommunikationsstyrning för samarbetsscenarier.](groups-teams-communication-governance.md)
6. Planera för styrning av organisation och livscykel – välj vilka principer du vill använda för att skapa grupper [och team, namn, förfallotid och arkivering.](plan-organization-lifecycle-governance.md) Förstå även slutet [av livscykelalternativen för grupper, team och Yammer](end-life-cycle-groups-teams-sites-yammer.md)

![Illustration av rekommenderade styrningssteg](../media/collaboration-governance-steps.png)

## <a name="training-for-administrators"></a>Utbildning för administratörer

Dessa utbildningsmoduler från Microsoft Learn kan hjälpa dig att lära dig mer om styrningsfunktioner i Microsoft 365.

#### <a name="information-protection"></a>Informationsskydd

|Utbildning:|Hantera informationsskydd och styrning|
|:---|:---|
|![Utbildningsikon för informationsskydd](../media/information-protection-governance.svg)|Mängden data som skapas i dag ökar snabbare än någonsin, anställda vill få jobbet gjort överallt och liggande regelverken förändras hela tiden. Microsofts lösningar för informationsskydd och styrning hjälper organisationer att skapa rätt balans mellan att skydda sina data och deras personer produktivt. Den här utbildningsvägen kan hjälpa dig att förbereda för Microsoft 365 Certified: Security Administrator Associate och Microsoft 365 Certified: Enterprise Administration Expert-certifieringar.<br><br>5 t 13 min - Utbildningsväg - 7 moduler|

> [!div class="nextstepaction"]
> [Starta >](/learn/modules/m365-compliance-information-governance/introduction/)

<br><br>

|Utbildning:|Skydda företagsinformation med Microsoft 365|
|:---|:---|
|![Utbildningsikon för Teams](../media/protect-enterprise-information-microsoft-365.svg)|Det är svårare än någonsin att skydda och skydda organisationens information. I utbildningsvägen Skydda företagsinformation med Microsoft 365 diskuteras hur du skyddar känslig information från att oavsiktligt skriva över eller felaktigt använda data, hur du identifierar och klassificerar data, hur du skyddar dem med känslighetsetiketter och hur du både övervakar och analyserar din känsliga information för att skydda mot förlust. Den här utbildningsvägen kan hjälpa dig att förbereda för Microsoft 365 Certified: Security Administrator Associate och Microsoft 365 Certified: Enterprise Administration Expert-certifieringar.<br><br>1 t - Utbildningsväg - 5 moduler|

> [!div class="nextstepaction"]
> [Starta >](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="security-and-compliance"></a>Säkerhet och efterlevnad

|Utbildning:|Visa grundläggande kunskap om säkerhets- och efterlevnadsfunktioner i Microsoft 365|
|:---|:---|
|![Ikon för utbildning om säkerhet och efterlevnad](../media/microsoft-365-security-and-compliance-capabilities.svg)|Läs mer om områdena för säkerhets- och efterlevnadslösningar i Microsoft 365 och vilka funktioner som finns tillgängliga för att hjälpa företag att skydda sitt företag och uppfylla kraven i regelverken. Om du inte är bekant med grundläggande molnberäkningskoncept rekommenderar vi att du använder [molnbegreppen – principer för molnbaserad databehandling.](/learn/modules/principles-cloud-computing/index)<br><br>3 t 11 min - Utbildningsväg - 8 moduler|

> [!div class="nextstepaction"]
> [Starta >](/learn/modules/what-is-m365/1-introduction/)

## <a name="illustrations"></a>Illustrationer

De här illustrationerna hjälper dig att förstå hur grupper och team interagerar med andra tjänster i Microsoft 365 och vilka styrnings- och efterlevnadsfunktioner som är tillgängliga för att hjälpa dig att hantera de här tjänsterna i organisationen.

### <a name="groups-in-microsoft-365-for-it-architects"></a>Grupper i Microsoft 365 för IT-arkitekter
Det IT-arkitekter behöver veta om grupper i Microsoft 365

|**Objekt**|**Beskrivning**|
|:-----|:-----|
|[![Miniatyrbild av infografiken för grupper](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> Uppdaterad i juni 2019|De här illustrationerna beskriver de olika typerna av grupper, hur de skapas och hanteras samt några rekommendationer för styrning.|

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>Microsoft Teams och relaterade produktivitetstjänster i Microsoft 365 för IT-arkitekter
Den logiska arkitekturen för produktivitetstjänster i Microsoft 365, med Microsoft Teams i spetsen.

|**Objekt**|**Beskrivning**|
|:-----|:-----|
|[![Miniatyrbild av affischen för Teams logiska arkitektur](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>Uppdaterad i april 2019   |Microsoft erbjuder ett utbud av produktivitetstjänster som samverkar för att tillhandahålla samarbetsupplevelser med funktioner för datastyrning, säkerhet och efterlevnad. <br/> <br/>Den här serien med illustrationer ger en översikt över produktivitetstjänsternas logiska arkitektur för företagsarkitekter, med Microsoft Teams i spetsen.|

### <a name="microsoft-365-information-protection-and-compliance-capabilities"></a>Funktioner för informationsskydd och efterlevnad för Microsoft 365

Microsoft 365 innehåller en omfattande uppsättning funktioner för informationsskydd och efterlevnad. Tillsammans med Microsofts produktivitetsverktyg är dessa funktioner utformade för att hjälpa organisationer att samarbeta i realtid samtidigt som de följer strikt reglerande ramverk för efterlevnad. 

I den här uppsättningen illustrationer används en av de mest reglerade branscherna och finansiella tjänsterna för att visa hur dessa funktioner kan tillämpas för att uppfylla vanliga regleringskrav. Du kan anpassa illustrationerna för eget bruk. 


| Objekt | Beskrivning |
|:-----|:-----|
|[![Modellaffisch: Microsoft 365 illustrationer för informationsskydd och efterlevnadsfunktioner](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/> Engelska:[Ladda ned som PDF](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)\| [Hämta som Visio](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> Japanska[Ladda ned som PDF](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)\| [Hämta som Visio](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx) <br/> Uppdaterad i november 2020|Innehåller: <ul><li>  Microsoft Informationsskydd och dataförlustskydd </li><li>Kvarhållningsprinciper och -etiketter </li><li>Informationsbarriärer</li><li>Kommunikationsefterlevnad</li><li>Intern risk</li><li>Datainmatning för tredje part</li>|

## <a name="conference-sessions"></a>Konferenssessioner

Titta på de här konferenssessionerna om du vill veta mer om styrning för Microsoft 365-grupper och Teams.

**Grunderna**

Lär dig grunderna och nya innovationer i Microsoft 365-grupper, inklusive hantering och styrning på skala, metodtips för att driva användningen och införandet och självbetjäning.

- [Microsoft 365-grupper](https://www.youtube.com/watch?v=dAamBF1gb7M)

**Styrning**

Lär dig hur du ställer in livscykeln för gruppers giltighetstid, namnprinciper, klassificeringsetiketter, samarbete med externa gäster och hur du hanterar behörigheter för att skapa grupper.

- [Transformera samarbete och skapa skugga för IT med Office 365-grupper](https://www.youtube.com/watch?v=Bhf_bKx3lAg)

**Kundexempel**

Se ett bakom kulisserna-exempel på hur Microsoft 365 Grupper, SharePoint, Teams och Yammer samarbetar för att tillhandahålla en global samarbetsplattform.

- [Hitta samarbete med Office 365-grupper, SharePoint, Teams och Yammer](https://www.youtube.com/watch?v=Rx9eVwqXeQk)

## <a name="see-also"></a>Se även

[Dokumentation för Microsoft 365 Säkerhetscenter](../security/index.yml)

[Dokumentation för Microsoft 365 Efterlevnadscenter](../compliance/index.yml)