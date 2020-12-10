---
title: Vad är samarbets styrning?
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
description: Lär dig mer om hur du styr relaterade funktioner i Microsoft 365 Groups, teams, SharePoint och Yammer.
ms.openlocfilehash: 2319a0f5b8c74925569d00eb781d247fe61a5a76
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613038"
---
# <a name="what-is-collaboration-governance"></a>Vad är samarbets styrning?

Samarbete hantering är hur du hanterar användares åtkomst till resurser, efterlevnad av dina företags standarder och säkerställer säkerheten för dina data.

Organisationer i dag använder en mängd olika verktygs uppsättningar. Det finns en grupp med utvecklare som använder gruppchatt, chefer som skickar e-post och hela organisationen som ansluter via företags social. Flera samarbets verktyg används eftersom alla grupper är unika och har sina egna funktioner och arbets format. Vissa kommer bara att använda e-post medan andra bor i chatten. 

Om användarna tycker att de verktyg som tillhandahålls inte passar deras behov kommer de sannolikt att ladda ner sin favorit-Consumer-app som stöder deras scenarier. Även om den här processen gör det möjligt för användare att komma igång snabbt, leder den till en frustrerande användar upplevelse i hela organisationen med flera inloggningar, svårt att dela och ingen plats för att visa innehåll. Det här begreppet kallas "skuggat" och innebär en betydande risk för organisationer. Det reducerar förmågan att enhetligt hantera användar åtkomst, kontrol lera säkerheten och behovet av tjänst.

Tjänster som Microsoft 365 Groups, teams och Yammer gör det möjligt för användarna att minska risken för att skugga den genom att tillhandahålla de verktyg som behövs för att samar beta. Microsoft 365 har en mängd olika verktyg för att implementera styr funktioner som din organisation kan behöva. 

![Diagram som visar alternativ för samarbets styrning i Microsoft 365](../media/collaboration-governance-overview.png)

Den här artikeln hjälper dig att förstå hur grupper, team och SharePoint-inställningar interagerar, vilka styr funktioner som är tillgängliga och hur du skapar och implementerar en plan ritning för samarbets funktionerna i Microsoft 365.

## <a name="what-are-microsoft-365-groups"></a>Vad är Microsoft 365-grupper?

Med Microsoft 365-grupper kan du välja en uppsättning personer som du vill samar beta med och enkelt skapa en samling resurser för de personer som ska dela. Om du lägger till medlemmar i gruppen beviljar du automatiskt de behörigheter som krävs för alla till gångar som tillhandahålls av gruppen. Både team och Yammer använder Microsoft 365 Groups för att hantera deras medlemskap.

Microsoft 365-grupper innehåller en uppsättning länkade resurser som användarna kan använda för kommunikation och samarbete. Grupper inkluderar alltid en SharePoint-webbplats, Planner, en Power BI-arbetsyta, en post låda och en kalender samt direkt uppspelning. Beroende på hur du skapar gruppen kan du lägga till andra tjänster som team, Yammer och projekt.

![Diagram som visar Microsoft 365-grupper och tillhör ande tjänster](../media/microsoft-365-groups-hub-spoke.png)

|Resurspool|Beskrivning|
|:------|:----------|
|[Kalender](https://support.office.com/article/schedule-a-meeting-on-a-group-calendar-in-outlook-0cf1ad68-1034-4306-b367-d75e9818376a)|För schemaläggning av händelser relaterade till gruppen|
|[Brevlåda](https://support.office.com/article/have-a-group-conversation-in-outlook-a0482e24-a769-4e39-a5ba-a7c56e828b22)|För e-postkonversationer mellan grupp medlemmar. Denna inkorg har en e-postadress och kan anges för att acceptera meddelanden från personer utanför gruppen, till och med utanför organisationen, ungefär som en traditionell distributions lista.|
|[OneNote-anteckningsbok](https://support.office.com/article/get-started-with-onenote-e768fafa-8f9b-4eac-8600-65aa10b2fe97)|För att samla idéer, forskning och information|
|[Planner](https://support.office.com/article/microsoft-planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc)|För att tilldela och hantera projektuppgifter bland grupp medlemmarna|
|[Power BI-arbetsyta](https://docs.microsoft.com/power-bi/collaborate-share/service-new-workspaces)|Ett data samarbets utrymme med instrument paneler och rapporter|
|[Projekt och översikt](https://support.microsoft.com/project)|Webbaserade verktyg för projektledning|
|[SharePoint-gruppwebbplats](https://support.office.com/article/what-is-a-sharepoint-team-site-75545757-36c3-46a7-beed-0aaa74f0401e)|En central lagrings plats för information, länkar och innehåll som rör din grupp|
|[Strömma](https://support.microsoft.com/microsoft-stream)|En video direkt uppspelnings tjänst|
|[Teams](https://support.microsoft.com/teams)|En chatt-baserad arbets yta i Microsoft 365|
|[Yammer-grupp](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)|En gemensam plats för konversationer och informations delning|

Microsoft 365-grupper innehåller flera olika styrnings kontroller, inklusive en policy för utgångs datum, namn regler och en blockerad ord policy som hjälper dig att hantera grupper i din organisation. Eftersom grupp kontroll medlemskap och åtkomst till den här sviten är en viktig del i hur du hanterar samarbete i Microsoft 365.

## <a name="define-a-collaboration-strategy-for-your-organization"></a>Definiera en samarbets strategi för din organisation

Det finns flera ställen att samar beta och ha konversationer i Microsoft 365. Förstå var användarna kan starta konversationer kan hjälpa dig att definiera en strategi för kommunikation.

Det finns tre huvudsakliga kommunikations metoder i Microsoft 365:

- Outlook: samarbete via e-post med en delad gruppinkorg och kalender
- Microsoft Teams: en beständig chatt-baserad arbets yta där du kan ha informella samtal i real tid med olika ämnen, ordnade efter specifika under grupper
- Yammer: social erfarenhet för företag

![Diagram som visar när du ska använda Teams, Yammer och Outlook](../media/inner-loop-outer-loop.png)

- Teams: chatt-baserad arbets yta (höghastighets samarbete) – inre loop
  - Byggd för samarbete med de personer användarna samarbetar med varje dag
  - Placerar information lättillgängligt för användarna i en enda upplevelse
  - Lägga till flikar, kopplingar och robotar
  - Live chatt, ljud-och video konferens, registrerade möten

- Yammer: ansluta i organisationsschemat (företags social) – yttre loop
  - Communitys med övning – kors funktionella grupper av personer som delar ett gemensamt intresse eller kunnande, men som inte nödvändigt vis arbetar tillsammans i dag-till-dags basis
  - Ledarskaps förbindelse, utbildnings grupper, rollbaserade samhällen

- Post låda och kalender (e-postbaserad samarbete)
  - Används för riktad kommunikation med en grupp personer
  - Delad kalender för möten med andra grupp medlemmar
 
När du bestämmer dig för hur du vill använda samarbets funktioner i Microsoft 365 bör du överväga de här kommunikations metoderna och vilka användarna sannolikt kommer att använda i olika situationer.

> [!NOTE]
> När en ny Office 365-grupp skapas via Yammer eller teams visas den inte i Outlook eller adress boken eftersom den primära kommunikationen mellan dessa användare sker i sina respektive klienter. Yammer-grupper kan inte anslutas till team.


## <a name="best-practices"></a>Metodtips

När du startar planerings processen för styrning bör du tänka på följande:

- **Prata med användarna** – identifiera dina största användare av samarbets funktioner och träffa dem för att förstå deras grundläggande företags behov och användnings fall.

- **Utjämna risker och fördelar** – granska dina affärer, regler, juridik-och efterföljandekrav och planera en lösning som optimerar för alla resultat.

- **Anpassa sig till olika organisationer och olika typer av innehåll och scenarier** -titta på de olika behoven för olika grupper eller avdelningar och olika typer av innehåll, till exempel intranät innehåll och en användares OneDrive-innehåll.

- **Justera till företags prioriteringar** -företags mål hjälper dig att definiera hur lång tid och energi du behöver för att investera i styrning.

- Med funktioner för **att bädda in styr beslut direkt i de lösningar du skapar** -många styrnings beslut kan implementeras genom att aktivera eller inaktivera funktionerna i Microsoft 365.

- **Stärk dig med utbildning** -anpassningsbara lösningar som [Microsoft 365 Learning-vägar](https://docs.microsoft.com/office365/customlearning) för att säkerställa att dina organisations specifika förväntningar är förstärkta med utbildning från Microsoft.

- **Ha en strategi för att kommunicera styrnings politik och rikt linjer i din organisation** – skapa ett Microsoft 365 Adoption Center på en SharePoint-kommunikations webbplats för att kommunicera principer och procedurer.

- **Definiera roller och ansvars områden** -identifiera din styrelse grupp och arbeta via viktiga styr beslut om etablering och namngivning och extern åtkomst och gå sedan igenom de återstående besluten.

- Gå igenom **dina beslut när företags-och teknik ändringar** -uppfyller regelbundet för att granska nya funktioner och nya förväntningar.

Om du vill veta mer om de här metoderna läser [du skapa din plan för hantering av samarbete](collaboration-governance-first.md).

## <a name="end-user-impact-and-change-management"></a>Slutanvändarens effekt och ändrings hantering

Eftersom grupper och team kan skapas på flera olika sätt rekommenderar vi att du använder den metod som passar din organisation bäst:

- Om din organisation utför större delen av sin kommunikation via e-post kan du be användarna att skapa grupper i Outlook.
- Om din organisation använder SharePoint eller om du migrerar från lokala SharePoint-användare kan du be användarna att skapa SharePoint-gruppwebbplatser för samarbete.
- Om din organisation har distribuerat Teams kan du be användarna att skapa ett team när de behöver ett samarbets utrymme.

Det gör det lättare för användarna att undvika förvirring om hur grupper relaterar till deras relaterade tjänster. Mer information om hur du pratar med användare om grupper finns i avsnittet [förklara Microsoft 365-grupper till användarna](../admin/create-groups/explain-groups-knowledge-worker.md).

## <a name="key-governance-capabilities-and-licensing-requirements"></a>Viktiga styr funktioner och licens krav

Styr funktioner för samarbete i Microsoft 365 inkluderar funktioner i Microsoft 365, team, SharePoint och Azure Active Directory.

| Resurs eller funktion | Beskrivning | Licensiering |
|:----------------------|:------------|:----------|
|Grupp-och webbplats delning|Kontrol lera om team, grupper och webbplatser kan delas med personer utanför organisationen.|Microsoft 365 E5 eller E3|
|Tillåt/blockera domän|Begränsa delning med personer utanför din organisation till personer från specifika domäner.|Microsoft 365 E5 eller E3|
|Standard sidan för att skapa webbplatser|Tillåta eller hindra användare från att skapa sina egna SharePoint-webbplatser.|Microsoft 365 E5 eller E3|
|Begränsad webbplats-och fildelning|Begränsa webbplats-, fil-och mappdelning till medlemmar i en viss säkerhets grupp.|Microsoft 365 E5 eller E3|
|Begränsad grupp skapande|Begränsa grupp-och grupp skapande till medlemmar i en viss säkerhets grupp.|Microsoft 365 E5 eller E3 med Azure AD Premium-eller Azure AD-EDU-licenser|
|Namn princip för grupper|Tillämpa prefix eller suffix på grupp-och team namn.|Microsoft 365 E5 eller E3 med Azure AD Premium-eller Azure AD-EDU-licenser|
|Policy för giltighets tid för grupp|Ange att inaktiva grupper och team ska upphöra och tas bort efter en viss tids period.|Microsoft 365 E5 eller E3 med Azure AD Premium-licenser|
|Gäståtkomst per grupp|Tillåt eller förhindra grupp-och grupp delning med personer utanför organisationen per grupp.|Microsoft 365 E5 eller E3|

## <a name="collaboration-governance-planning-step-by-step"></a>Planerings steg-för-steg-samarbete för samarbets styrning

Följ de här grundläggande stegen för att skapa din plan ritning:

1. Tänk på viktiga företags mål och processer- [skapa din plan ritning](collaboration-governance-first.md) för att uppfylla behoven hos ditt företag.
2. Förstå inställningar i tjänster – [Inställningar i grupper och SharePoint](groups-sharepoint-governance.md) interagerar med varandra, som gör [Inställningar i grupper, SharePoint och team](groups-sharepoint-teams-governance.md) och [andra tjänster](groups-services-interactions.md). Se till att du förstår dessa interaktioner när du planerar din styrnings strategi.
3. Planera för att hantera användar åtkomst-planera [vilken behörighets nivå du vill tilldela användare i grupper, SharePoint och team](groups-teams-access-governance.md).
4. Planera inställningar för efterlevnad-granska tillgängliga [alternativ för kompatibilitet för Microsoft 365-grupper,-team och SharePoint-samarbete](groups-teams-compliance-governance.md).
5. Planera för kommunikation-granska de tillgängliga [kommunikations alternativen för kommunikation under samarbete](groups-teams-communication-governance.md).
6. Planera för organisationen och livs cykel styrelserna – Välj [de principer du vill använda för grupp-och grupp skapande, namn, förfallo datum och arkivering](plan-organization-lifecycle-governance.md). Förstå även [slutet av livs cykel alternativen för grupper, team och Yammer](end-life-cycle-groups-teams-sites-yammer.md)

![Bild av rekommenderade styr steg](../media/collaboration-governance-steps.png)

## <a name="training-for-administrators"></a>Utbildning för administratörer

Med de här utbildnings modulerna kan du lära dig hur du samarbetar i team och SharePoint.

#### <a name="teams"></a>Teams

|Höjd|Hantera grupp samarbete med Microsoft Teams|
|:---|:---|
|![Utbildnings ikonen Teams](../media/manage-team-collaboration-with-microsoft-teams.svg)|Hantera grupp samarbete med Microsoft Teams introducerar dig funktioner och funktioner i Microsoft Teams, det centrala navet för grupp samarbete i Microsoft 365. Du får lära dig hur du kan använda Teams för att under lätta samarbete och kommunikation inom din organisation, både på och av lokalt, på en mängd olika enheter — från Station ära datorer till surfplattor till telefoner – samtidigt som du utnyttjar alla funktioner i Office 365-program. Du får mer information om hur Teams erbjuder en omfattande och flexibel miljö för samarbete mellan program och enheter. Den här utbildnings vägen kan hjälpa dig att förbereda Microsoft 365 Certified: Teams-administratören för att koppla ett certifikat.<br><br>2 HR 17 min-Learning Path-5 moduler|

> [!div class="nextstepaction"]
> [Starta >](https://docs.microsoft.com/learn/modules/m365-teams-collab-prepare-deployment/introduction/)

#### <a name="sharepoint"></a>SharePoint

|Höjd|Samar beta med SharePoint i Microsoft 365|
|:---|:---|
|![Utbildnings ikon för SharePoint](../media/collaborate-with-sharepoint-in-microsoft-365.svg)|Med hantera delat innehåll i Microsoft SharePoint får du en introduktion till funktioner och funktioner i SharePoint, och hur det fungerar med Microsoft 365. Du får mer information om de olika typerna av SharePoint-webbplatser, inklusive nav webbplatser, samt informations skydd, rapportering och övervakning. Du får också lära dig hur du kan använda fil-och mappdelning för SharePoint för att optimera samarbetet, hur du delar filer externt och hur du hanterar SharePoint-webbplatser i administrations centret för SharePoint. Med den här utbildnings vägen kan du förbereda Microsoft 365 Certified: lag för certifierings administratören.<br><br>1 timme 14 min-Learning Path-4 moduler|

> [!div class="nextstepaction"]
> [Starta >](https://docs.microsoft.com/learn/modules/m365-teams-sharepoint-plan-sharepoint/introduction/)

## <a name="training-for-end-users"></a>Utbildning för slutanvändare

Med dessa utbildnings funktioner kan användarna använda team, grupper och SharePoint för samarbete i Microsoft 365.

|Teams|SharePoint|
|:---|:---|
|![Konfigurera och anpassa din grupp utbildnings ikon](../media/set-up-customize-team-training.png)<br>**[Konfigurera och anpassa ditt team](https://support.microsoft.com/office/702a2977-e662-4038-bef5-bdf8ee47b17b)**|![Ikonen för SharePoint-resurstjänsten och-synkronisering](../media/sharepoint-share-sync-training.png)<br>**[Dela och synkronisera](https://support.microsoft.com/office/98cb2ff2-c27e-42ea-b055-c2d895f8a5de)**|
|![Ikonen för att ladda upp och hitta filer](../media/smc-teams-upload-find-files-training.png)<br>**[Ladda upp och hitta filer](https://support.microsoft.com/office/57b669db-678e-424e-b0a0-15d19215cb12)**||
|![Ikonen samar beta i team och kanaler](../media/teams-collaborate-channels-training.png)<br>**[Samar beta i team och kanaler](https://support.microsoft.com/office/c3d63c10-77d5-4204-a566-53ddcf723b46)**|||

## <a name="illustrations"></a>Illustrationer

De här illustrationerna hjälper dig att förstå hur grupper och team interagerar med andra tjänster i Microsoft 365 och vilka funktioner för styrning och kompatibilitet som hjälper dig att hantera de här tjänsterna i din organisation.

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

### <a name="microsoft-365-information-protection-and-compliance-capabilities"></a>Microsoft 365 informations skydd och funktioner för efterlevnad

Microsoft 365 innehåller en mängd olika funktioner för informations skydd och efterlevnad. Tillsammans med Microsofts produktivitets verktyg är de här funktionerna utformade för att hjälpa organisationer att samar beta i real tid, samtidigt som de uppfyller stränga villkor för efterlevnad. 

Denna uppsättning illustrationer använder en av de mest reglerade industrierna, finans tjänsterna, för att demonstrera hur dessa funktioner kan användas för att åtgärda gemensamma reglerings krav. Du kan anpassa illustrationerna för eget bruk. 


| Objekt | Beskrivning |
|:-----|:-----|
|[![Modellaffisch: Microsoft 365 illustrationer för informationsskydd och efterlevnadsfunktioner](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/> Engelska:[Ladda ned som PDF](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)\| [Hämta som Visio](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> Japanska[Ladda ned som PDF](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)\| [Hämta som Visio](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx) <br/> Uppdaterad i november 2020|Innehåller: <ul><li>  Microsoft Informationsskydd och dataförlustskydd </li><li>Bevarande principer och bevarande etiketter </li><li>Informationsbarriärer</li><li>Efterlevnad av kommunikation</li><li>Intern risk</li><li>Datainmatning för tredje part</li>|

## <a name="conference-sessions"></a>Konferens-sessioner

Se dessa konferens samtal för att lära dig mer om styrning för Microsoft 365-grupper och-team.

**Programmering**

Lär dig grunderna och nya innovationer i Microsoft 365-grupper, inklusive ledning och styrelse trafik, metod tips för att driva användning och antagande samt själv service.

- [Ta med Microsoft 365-grupper](https://www.youtube.com/watch?v=dAamBF1gb7M)

**Styrning**

Lär dig hur du konfigurerar gruppernas livs cykel, namngivnings principer, klassificerings etiketter, samarbete med externa gäster och hanterar behörighet för att skapa grupper.

- [Omvandla samarbete och bekämpa skuggat med Office 365-grupper](https://www.youtube.com/watch?v=Bhf_bKx3lAg)

**Kund exempel**

Se ett exempel på hur Microsoft 365 Groups, SharePoint, teams och Yammer samarbetar för att tillhandahålla en global samarbets plattform.

- [Hitta ditt samarbete på en plats med Office 365-grupper, SharePoint, teams och Yammer](https://www.youtube.com/watch?v=Rx9eVwqXeQk)
