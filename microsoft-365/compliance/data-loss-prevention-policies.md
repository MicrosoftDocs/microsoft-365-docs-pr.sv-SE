---
title: Referens för förebyggande av dataförlust
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: low
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: referensmaterial för förebyggande av dataförlust
ms.openlocfilehash: a6dc0b2702899e05f78c54331fb33b87495672d8
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572567"
---
# <a name="data-loss-prevention-reference"></a>Referens för förebyggande av dataförlust
 
> [!IMPORTANT]
> Det här är referensavsnittet är inte längre den viktigaste resursen Microsoft 365 DLP-information (Data Loss Prevention). DLP-innehållsuppsättningen uppdateras och omstruktureras. De ämnen som behandlas i den här artikeln kommer att gå över till nya, uppdaterade artiklar. Mer information om DLP finns i Lär [dig mer om förebyggande av dataförlust](dlp-learn-about-dlp.md).

<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
<!-- move this note to a more appropriate place, no topic should start with a note -->
> [!NOTE]
> Funktioner för att förebygga dataförlust lades nyligen till i Microsoft Teams chatt- och kanalmeddelanden för användare som licensierats för Office 365 Advanced Compliance, vilket är tillgängligt som ett fristående alternativ och ingår i Office 365 E5 och Microsoft 365 E5 Compliance. Mer information om licenskrav finns i [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).



<!-- MOVED TO LEARN ABOUT To comply with business standards and industry regulations, organizations must protect sensitive information and prevent its inadvertent disclosure. Sensitive information can include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records. With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.
  
With a DLP policy, you can:
  
- **Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.**
    
    For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.
    
- **Prevent the accidental sharing of sensitive information**. 
    
    For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.
    
- **Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.**
    
    Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office desktop programs include the same capabilities to identify sensitive information and apply DLP policies. DLP provides continuous monitoring when people share content in these Office programs.
    
- **Help users learn how to stay compliant without interrupting their workflow.**
    
    You can educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification. The same policy tips also appear in Outlook on the web, Outlook, Excel, PowerPoint, and Word.
    
- **View DLP alerts and reports showing content that matches your organization’s DLP policies.**
    
    To view alerts and metadata related to your DLP policies you can use the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md). You can also view policy match reports to assess how your organization is complying with a DLP policy. If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported

-->    
## <a name="create-and-manage-dlp-policies"></a>Skapa och hantera DLP-principer

Du skapar och hanterar DLP-principer på sidan Dataförlustförebyggande i Microsoft 365 Compliance Center.
  
![Sidan dataförlustförebyggande i Office 365 Security &amp; Compliance Center](../media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
<!-- MOVED TO LEARN ABOUT ## What a DLP policy contains

A DLP policy contains a few basic things:
  
- Where to protect the content: **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chat and channel messages. 
    
- When and how to protect the content by enforcing **rules** comprised of: 
    
  - **Conditions** the content must match before the rule is enforced. For example, a rule might be configured to look only for content containing Social Security numbers that's been shared with people outside your organization. 
    
  - **Actions** that you want the rule to take automatically when content matching the conditions is found. For example, a rule might be configured to block access to a document and send both the user and compliance officer an email notification. -->
    
Du kan använda en regel för att uppfylla ett specifikt skyddskrav och sedan använda en DLP-policy för att gruppera gemensamma skyddskrav, till exempel alla regler som behövs för att följa en viss förordning.
  
Du kan till exempel ha en DLP-policy som hjälper dig att upptäcka förekomsten av information som omfattas av Hipaa (Health Insurance Portability and Accountability Act). Den här DLP-principen kan hjälpa till att skydda HIPAA-data (vad) på alla SharePoint Online-webbplatser och alla OneDrive för företag-webbplatser (var) genom att hitta alla dokument som innehåller den här känsliga informationen som delas med personer utanför organisationen (villkoren) och sedan blockera åtkomst till dokumentet och skicka ett meddelande (åtgärderna). Dessa krav lagras som individuella regler och grupperas tillsammans som en DLP-policy för att förenkla hantering och rapportering.
  
![Diagrammet visar att DLP-principen innehåller platser och regler](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
<!-- MOVED TO LEARN ABOUT ### Locations

DLP policies are applied to sensitive items across Microsoft 365 locations and can be further scoped as detailed in this table.


|Location | Include/exclude by|
|---------|---------|
|Exchange email| distribution groups|
|SharePoint sites |sites |
|OneDrive accounts |accounts |
|Teams chat and channel messages |accounts |
|Windows 10 devices |user or group |
|Microsoft Cloud App Security |instance |
 -->

Om du väljer att inkludera specifika distributionsgrupper Exchange kommer DLP-principen endast att omfatta medlemmarna i den gruppen. Om du utesluter en distributionsgrupp utesluts inte heller alla medlemmar i distributionsgruppen från principutvärderingen. Du kan välja att omfånga en princip till medlemmarna i distributionslistor, dynamiska distributionsgrupper och säkerhetsgrupper. En DLP-policy får inte innehålla mer än 50 sådana införanden och undantag.

Om du väljer att inkludera eller utesluta SharePoint vissa webbplatser kan en DLP-princip innehålla högst 100 sådana inkluderingar och undantag. Även om den här gränsen finns kan du överskrida den här gränsen genom att tillämpa antingen en organisationsomfattande princip eller en princip som gäller för hela platser.

Om du väljer att inkludera eller utesluta specifika OneDrive-konton eller grupper kan en DLP-princip innehålla högst 100 användarkonton eller 50 grupper som inkludering eller undantag.

> [!NOTE]
> OneDrive för affärsprincip omfång med konton eller grupper är i offentlig förhandsgranskning. Under den här fasen kan du antingen inkludera eller utesluta användarkonton och grupper som en del av en DLP-princip. Både inkludering och uteslutning som en del av samma politik stöds inte.
  
### <a name="rules"></a>Regler

> [!NOTE]
> Standardbeteendet för en DLP-princip, när ingen avisering är konfigurerad, är inte att varna eller utlösa. Detta gäller endast standardinformationstyper. För anpassade informations typer kommer systemet att varna även om det inte finns någon åtgärd definierad i principen.

Regler är vad som upprätthåller dina affärskrav på organisationens innehåll. En princip innehåller en eller flera regler, och varje regel består av villkor och åtgärder. För varje regel, när villkoren är uppfyllda, vidtas åtgärderna automatiskt. Regler körs sekventiellt, med början med regeln med högst prioritet i varje princip.
  
En regel innehåller också alternativ för att meddela användare (med principtips och e-postaviseringar) och administratörer (med e-postincidentrapporter) att innehållet har matchat regeln.
  
Här är komponenterna i en regel, var och en förklaras nedan.
  
![Avsnitt i DLP-regelredigeraren](../media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a>Villkor

Villkor är viktiga eftersom de bestämmer vilka typer av information du letar efter och när du ska vidta en åtgärd. Du kan till exempel välja att ignorera innehåll som innehåller passnummer om inte innehållet innehåller fler än 10 sådana nummer och delas med personer utanför organisationen.
  
Villkoren fokuserar på **innehållet**, till exempel vilka typer av känslig information du letar efter och även på **sammanhanget**, till exempel vem dokumentet delas med. Du kan använda villkor för att tilldela olika åtgärder till olika risknivåer. Känsligt innehåll som delas internt kan till exempel vara lägre risk och kräver färre åtgärder än känsligt innehåll som delas med personer utanför organisationen. 
  
![Lista som visar tillgängliga DLP-villkor](../media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
De villkor som nu är tillgängliga kan avgöra om:
  
- Innehållet innehåller en typ av känslig information.
    
- Innehållet innehåller en etikett. Mer information finns i avsnittet nedan använda en [lagringsetikett som ett villkor i en DLP-princip](#using-a-retention-label-as-a-condition-in-a-dlp-policy).
    
- Innehållet delas med personer utanför eller inom organisationen.

  > [!NOTE]
  > Användare som har konton som inte är gästar i en värdorganisations Active Directory eller Azure Active Directory-klient betraktas som personer inom organisationen.
    
#### <a name="types-of-sensitive-information"></a>Typer av känslig information

Med en DLP-princip skyddar du känslig information som har definierats med en **typ av känslig information**. Microsoft 365 innehåller definitioner för många vanliga känsliga informationstyper i många olika regioner som är redo för dig att använda, till exempel ett kreditkortsnummer, bankkontonummer, nationella ID-nummer och passnummer. 
  
![Lista över tillgängliga känsliga informationstyper](../media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
När en DLP-princip söker efter en känslig informationstyp, till exempel ett kreditkortsnummer, letar den inte bara efter ett 16-siffrigt nummer. Varje känslig informationstyp definieras och identifieras med hjälp av en kombination av:
  
- nyckelord.
    
- Interna funktioner för att validera kontrollsummar eller sammansättning.
    
- Utvärdering av reguljära uttryck för att hitta mönstermatchningar.
    
- Annan innehållsundersökning.
    
Detta hjälper DLP-identifiering att uppnå en hög grad av noggrannhet samtidigt som antalet falska positiva identifieringar som kan avbryta människors arbete minskar.
  
#### <a name="actions"></a>Åtgärder

När innehåll matchar ett villkor i en regel kan du tillämpa åtgärder för att automatiskt skydda innehållet.
  
![Lista över tillgängliga DLP-åtgärder](../media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
Med de åtgärder som nu är tillgängliga kan du:
  
- **Begränsa åtkomsten till innehållet** Beroende på ditt behov kan du begränsa åtkomsten till innehåll på tre sätt:

  1. Begränsa åtkomsten till innehåll för alla.
  2. Begränsa åtkomsten till innehåll för personer utanför organisationen.
  3. Begränsa åtkomsten till "Alla med länken".

  För webbplatsinnehåll innebär detta att behörigheterna för dokumentet är begränsade för alla utom den primära webbplatssamlingsadministratören, dokumentägaren och personen som senast ändrade dokumentet. Dessa personer kan ta bort känslig information från dokumentet eller vidta andra åtgärdsåtgärder. När dokumentet är i överensstämmelse återställs de ursprungliga behörigheterna automatiskt. När åtkomsten till ett dokument är blockerad visas dokumentet med en särskild principtipsikon i biblioteket på webbplatsen. 
    
  ![Principtips som visar åtkomst till dokument är blockerat](../media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
  För e-postinnehåll blockerar den här åtgärden meddelandet från att skickas. Beroende på hur DLP-regeln är konfigurerad ser avsändaren en NDR eller (om regeln använder ett meddelande) ett principtips och/eller e-postmeddelande.
    
  ![Varning om att obehöriga mottagare måste tas bort från meddelandet](../media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a>Användarmeddelanden och användaråsidosättning

Du kan använda aviseringar och åsidosättningar för att utbilda användarna om DLP-principer och hjälpa dem att förbli kompatibla utan att blockera deras arbete. Om en användare till exempel försöker dela ett dokument som innehåller känslig information kan en DLP-princip både skicka dem ett e-postmeddelande och visa dem ett principtips i samband med dokumentbiblioteket som gör att de kan åsidosätta principen om de har en affärs motivering.
  
![Användarmeddelanden och användare åsidosätter avsnitt i DLP-regelredigeraren](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
E-postmeddelandet kan meddela den person som skickade, delade eller senast ändrade innehållet och, för webbplatsinnehåll, den primära administratören för webbplatssamlingen och dokumentägaren. Dessutom kan du lägga till eller ta bort vem du vill från e-postmeddelandet.
  
Förutom att skicka ett e-postmeddelande visas ett principtips i ett användarmeddelande:
  
- I Outlook och Outlook på webben.
    
- För dokumentet på en SharePoint Online eller OneDrive för företag webbplats.
    
- I Excel PowerPoint word när dokumentet lagras på en webbplats som ingår i en DLP-princip.
    
E-postmeddelandet och principtipset förklarar varför innehåll strider mot en DLP-policy. Om du väljer kan e-postmeddelandet och principtipset tillåta användare att åsidosätta en regel genom att rapportera ett falskt positivt eller tillhandahålla en affärs motivering. Detta kan hjälpa dig att utbilda användare om dina DLP-principer och genomdriva dem utan att hindra människor från att göra sitt arbete. Information om åsidosättningar och falska positiva identifieringar loggas också för rapportering (se nedan om DLP-rapporterna) och ingår i incidentrapporterna (nästa avsnitt), så att efterlevnadsansvarige regelbundet kan granska denna information.
  
Så här ser ett principtips ut på ett OneDrive för företag konto.
  
![Principtips för ett dokument i ett OneDrive konto](../media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 Mer information om användaraviseringar och principtips i DLP-principer finns i [Använda aviseringar och principtips](use-notifications-and-policy-tips.md).

#### <a name="alerts-and-incident-reports"></a>Aviseringar och incidentrapporter

När en regel matchas kan du skicka ett e-postmeddelande till din compliance officer (eller någon person du väljer) med information om aviseringen. Det här e-postmeddelandet kommer att ha en länk [till DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md) som efterlevnadsansvarigen kan gå för att visa information om aviseringar och händelser. Instrumentpanelen innehåller information om händelsen som utlöste aviseringen tillsammans med information om DLP-principen som matchades och det känsliga innehållet som identifierades.

Dessutom kan du också skicka en incidentrapport med information om händelsen. Den här rapporten innehåller information om det objekt som matchades, det faktiska innehållet som matchade regeln och namnet på den person som senast ändrade innehållet. För e-postmeddelanden innehåller rapporten också som en bifogad fil det ursprungliga meddelandet som matchar en DLP-princip.

> [!div class="mx-imgBorder"]
> ![Sida för konfigurering av incidentrapporter](../media/Alerts-and-incident-report.png)

DLP skannar e-post på ett annat sätt än objekt i SharePoint Online eller OneDrive för företag. I SharePoint Online och OneDrive för företag DLP befintliga objekt samt nya och genererar en aviserings- och incidentrapport när en matchning hittas. I Exchange Online DLP bara nya e-postmeddelanden och genererar en rapport om det finns en principmatchning. DLP ***söker inte igenom*** eller matchar tidigare befintliga e-postobjekt som lagras i en postlåda eller ett arkiv.
  
## <a name="grouping-and-logical-operators"></a>Gruppering och logiska operatorer

Ofta har din DLP-policy ett enkelt krav, till exempel att identifiera allt innehåll som innehåller ett amerikanskt personnummer. I andra scenarier kan dock DLP-principen behöva identifiera mer löst definierade data.
  
Om du till exempel vill identifiera innehåll som omfattas av U.S. Health Insurance Act (HIPAA) måste du leta efter:
  
- Innehåll som innehåller specifika typer av känslig information, till exempel ett amerikanskt personnummer eller DEA-nummer (Drug Enforcement Agency).
    
    och
    
- Innehåll som är svårare att identifiera, till exempel kommunikation om en patients vård eller beskrivningar av medicinska tjänster som tillhandahålls. För att identifiera det här innehållet krävs matchande nyckelord från mycket stora sökordslistor, till exempel international classification of diseases (ICD-9-CM eller ICD-10-CM).
    
Du kan enkelt identifiera sådana löst definierade data med hjälp av gruppering och logiska operatorer (AND, OR). När du skapar en DLP-princip kan du:
  
- Gruppera känsliga informationstyper.
    
- Välj den logiska operatorn mellan de känsliga informationstyperna i en grupp och mellan grupperna själva.
    
### <a name="choosing-the-operator-within-a-group"></a>Välja operator inom en grupp

I en grupp kan du välja om något eller alla villkor i den gruppen måste vara uppfyllda för att innehållet ska matcha regeln.
  
![Grupp som visar operatorerna inom koncernen](../media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a>Lägga till en grupp

Du kan snabbt lägga till en grupp som kan ha sina egna villkor och en operator inom den gruppen.
  
![Knappen Lägg till grupp](../media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a>Välja operator mellan grupper

Mellan grupper kan du välja om villkoren i bara en grupp eller alla grupper måste uppfyllas för att innehållet ska matcha regeln.
  
Den inbyggda **HIPAA-principen** i USA har till exempel en regel som använder en **AND-operator** mellan grupperna så att den identifierar innehåll som innehåller: 
  
- från gruppen **PII-identifierare (minst** ett SSN-nummer ELLER DEA-nummer)  
    
    **och**
    
- från gruppen Medicinska **termer** (minst ett ICD-9-CM nyckelord **ELLER** ICD-10-CM nyckelord) 
    
![Grupper som visar operatorn mellan grupper](../media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a>Den prioritet genom vilken regler behandlas

När du skapar regler i en princip tilldelas varje regel en prioritet i den ordning den skapas, vilket innebär att regeln som skapas först har första prioritet, regeln som skapas andra prioritet och så vidare.

> [!div class="mx-imgBorder"]
> ![Regler i prioritetsordning](../media/dlp-rules-in-priority-order.png)
  
När du har konfigurerat mer än en DLP-princip kan du ändra prioriteten för en eller flera principer. Om du vill göra det väljer du en princip, **väljer Redigera princip** och använder **prioritetslistan** för att ange dess prioritet.

> [!div class="mx-imgBorder"]
> ![Ange prioritet för en princip](../media/dlp-set-policy-priority.png)

När innehåll utvärderas mot regler bearbetas reglerna i prioritetsordning. Om innehållet matchar flera regler bearbetas reglerna i prioritetsordning och den mest restriktiva åtgärden tillämpas. Om innehållet till exempel matchar alla följande regler tillämpas regel 3 eftersom det är den högst prioriterade och mest restriktiva regeln:
  
- Regel 1: meddelar endast användare
    
- Regel 2: meddelar användare, begränsar åtkomsten och tillåter användaråsidosättning
    
- Regel 3: meddelar användare, begränsar åtkomsten och tillåter inte åsidosättningar av användare
    
- Regel 4: meddelar endast användare
    
- Regel 5: begränsar tillgången
    
- Regel 6: meddelar användare, begränsar åtkomsten och tillåter inte åsidosättningar av användare
    
Observera i det här exemplet att matchningar för alla regler registreras i granskningsloggarna och visas i DLP-rapporterna, även om endast den mest restriktiva regeln tillämpas.
  
När det gäller policytips bör du notera att:
  
- Endast principtipset från den högst prioriterade, mest restriktiva regeln visas. Ett principtips från en regel som blockerar åtkomst till innehåll visas till exempel över ett principtips från en regel som helt enkelt skickar ett meddelande. Detta förhindrar att människor ser en kaskad av principtips.
    
- Om principtipsen i den mest restriktiva regeln tillåter personer att åsidosätta regeln åsidosätter åsidosätter du också alla andra regler som innehållet matchade.
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a>Justeringsregler för att göra dem enklare eller svårare att matcha

När personer har skapat och aktiverar sina DLP-principer stöter de ibland på följande problem:
  
- För mycket innehåll **som inte är** känslig information matchar reglerna – med andra ord för många falska positiva identifieringar. 
    
- För lite innehåll **som är** känslig information matchar reglerna. Med andra ord tillämpas inte skyddsåtgärderna på känslig information. 
    
För att åtgärda dessa problem kan du justera dina regler genom att justera antalet instanser och matcha noggrannheten så att det blir svårare eller enklare för innehåll att matcha reglerna. Varje känslig informationstyp som används i en regel har både antal instanser och matchningsnoggrannhet.
  
### <a name="instance-count"></a>Antal instanser

Antalet instanser innebär helt enkelt hur många förekomster av en viss typ av känslig information som måste finnas för att innehållet ska matcha regeln. Innehållet matchar till exempel regeln nedan om mellan 1 och 9 unika amerikanska eller brittiska passnummer identifieras.

> [!NOTE]
> Antalet instanser innehåller endast **unika** matchningar för känsliga informationstyper och nyckelord. Om ett e-postmeddelande till exempel innehåller 10 förekomster av samma kreditkortsnummer räknas dessa 10 händelser som en enda instans av ett kreditkortsnummer.
  
Om du vill använda antalet instanser för att finjustera regler är vägledningen enkel:
  
- Om du vill göra regeln enklare att matcha minskar du **antalet minuter** och/eller ökar **det maximala** antalet. Du kan också ange **max till** **valfri genom** att ta bort det numeriska värdet. 
    
- Om du vill göra regeln svårare att matcha ökar du **antalet minuter.** 
    
Vanligtvis använder du mindre restriktiva åtgärder, till exempel att skicka användarmeddelanden, i en regel med lägre antal instanser (till exempel 1-9). Och du använder mer restriktiva åtgärder, till exempel att begränsa åtkomsten till innehåll utan att tillåta användar åsidosättningar, i en regel med ett högre instans antal (till exempel 10-any).
  
![Antalet instanser i regelredigeraren](../media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a>Matcha noggrannhet

Som beskrivits ovan definieras och upptäcks en känslig informationstyp med hjälp av en kombination av olika typer av bevis. Vanligtvis definieras en känslig informationstyp av flera sådana kombinationer, så kallade mönster. Ett mönster som kräver mindre bevis har en lägre matchningsnoggrannhet (eller konfidensnivå), medan ett mönster som kräver mer bevis har en högre matchningsnoggrannhet (eller konfidensnivå). Mer information om de faktiska mönster och konfidensnivåer som används av alla känsliga informationstyper finns i [Definitioner av känsliga informationstyper](sensitive-information-type-entity-definitions.md).
  
Den känsliga informationstypen kreditkortsnummer definieras till exempel av två mönster:
  
- Ett mönster med 65% förtroende som kräver:
    
  - Ett nummer i formatet på ett kreditkortsnummer.
    
  - Ett nummer som passerar kontrollsumman.
    
- Ett mönster med 85% förtroende som kräver:
    
  - Ett nummer i formatet på ett kreditkortsnummer.
    
  - Ett nummer som passerar kontrollsumman.
    
  - Ett nyckelord eller ett utgångsdatum i rätt format.
    
Du kan använda dessa förtroendenivåer (eller matcha noggrannhet) i dina regler. Vanligtvis använder du mindre restriktiva åtgärder, till exempel att skicka användaraviseringar, i en regel med lägre matchningsnoggrannhet. Och du använder mer restriktiva åtgärder, till exempel att begränsa åtkomsten till innehåll utan att tillåta användaråsidosättning, i en regel med högre matchningsnoggrannhet.
  
Det är viktigt att förstå att när en viss typ av känslig information, till exempel ett kreditkortsnummer, identifieras i innehåll returneras endast en enda konfidensnivå:
  
- Om alla matchningar är för ett enda mönster returneras konfidensnivån för det mönstret.
    
- Om det finns matchningar för mer än ett mönster (det vill säga det finns matchningar med två olika konfidensnivåer) returneras en konfidensnivå som är högre än något av de enskilda mönstren ensam. Det här är den svåra delen. För ett kreditkort, om till exempel både 65% och 85% mönster matchas, är konfidensnivån som returneras för den känsliga informationstypen större än 90% eftersom mer bevis betyder mer förtroende.
    
Så om du vill skapa två ömsesidigt uteslutande regler för kreditkort, en för 65% matchnoggrannhet och en för 85% matchnoggrannhet, skulle intervallen för matchnoggrannhet se ut så här. Den första regeln plockar bara upp matchningar av 65% -mönstret. Den andra regeln plockar upp matcher med **minst en matchning på** 85% och kan potentiellt ha **andra** matcher med lägre självförtroende. 
  
![Två regler med olika intervall för matchnoggrannhet](../media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
Av dessa skäl är vägledningen för att skapa regler med olika matchningsnoggrannhet:
  
- Den lägsta konfidensnivån använder vanligtvis samma värde för **min** och **max** (inte ett intervall). 
    
- Den högsta konfidensnivån är vanligtvis ett intervall från strax över den lägre konfidensnivån till 100.
    
- Eventuella mellannivåer varierar vanligtvis från strax över den lägre konfidensnivån till strax under den högre konfidensnivån.
    
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>Använda en kvarhållningsetikett som ett villkor i en DLP-princip

När du använder en tidigare skapad och publicerad [kvarhållningsetikett](retention.md#retention-labels) som ett villkor i en DLP-princip finns det några saker att vara medveten om:

- Kvarhållningsetiketten måste skapas och publiceras innan du försöker använda den som ett villkor i en DLP-princip.
- Publicerade lagringsetiketter kan ta från en till sju dagar att synkronisera. Mer information finns i När [lagringsetiketter blir tillgängliga för](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) lagringsetiketter som publiceras i en bevarandeprincip och [Hur lång tid det tar för lagringsetiketter att träda i kraft](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect) för lagringsetiketter som publiceras automatiskt.
- Att använda en kvarhållningsetikett i en princip **stöds bara för objekt i SharePoint och OneDrive***.

  ![Etiketter som ett villkor](../media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

  Du kanske vill använda en kvarhållningsetikett i en DLP-princip om du har objekt som är under kvarhållning och disposition, och du också vill tillämpa andra kontroller på dem, till exempel:

  - Du publicerade en lagringsetikett **med namnet skatteår 2018**, som när den tillämpas på skattedokument från 2018 som lagras i SharePoint behåller dem i 10 år och sedan kasserar dem. Du vill inte heller att dessa objekt ska delas utanför organisationen, vilket du kan göra med en DLP-princip.

  > [!IMPORTANT]
  > Det här felet visas om du anger en lagringsetikett som ett villkor i en DLP-princip och du även inkluderar Exchange och/eller Teams som plats: **"Skydda märkt innehåll i e-postmeddelanden och teammeddelanden stöds inte. Ta antingen bort etiketten nedan eller stäng Exchange och Teams som en plats.".** Detta beror på Exchange transporten inte utvärderar etikettmetadata under meddelandeöverföring och leverans. 

### <a name="using-a-sensitivity-label-as-a-condition-in-a-dlp-policy"></a>Använda en känslighetsetikett som ett villkor i en DLP-princip

[Läs mer om](./dlp-sensitivity-label-as-condition.md) hur du använder känslighetsetiketten som ett villkor i DLP-principer.
  
### <a name="how-this-feature-relates-to-other-features"></a>Hur den här funktionen relaterar till andra funktioner

Flera funktioner kan tillämpas på innehåll som innehåller känslig information:
  
- En [lagringsetikett och en bevarande princip kan](retention.md) båda genomdriva **kvarhållningsåtgärder** för det här innehållet. 
    
- En DLP-princip kan genomdriva **skyddsåtgärder** för det här innehållet. Och innan dessa åtgärder verkställs kan en DLP-policy kräva att andra villkor uppfylls utöver innehållet som innehåller en etikett. 
    
![Diagram över funktioner som kan tillämpas på känslig information](../media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
Observera att en DLP-princip har en rikare identifierings funktion än en etikett eller bevarande princip som tillämpas på känslig information. En DLP-princip kan genomdriva skyddsåtgärder på innehåll som innehåller känslig information, och om känslig information tas bort från innehållet ångras dessa skyddsåtgärder nästa gång innehållet skannas. Men om en bevarande princip eller etikett tillämpas på innehåll som innehåller känslig information är det en engångs åtgärd som inte ångras även om känslig information tas bort.
  
Genom att använda en etikett som ett villkor i en DLP-princip kan du genomdriva både kvarhållnings- och skyddsåtgärder på innehåll med den etiketten. Du kan tänka på innehåll som innehåller en etikett exakt som innehåll som innehåller känslig information - både en etikett och en känslig informationstyp är egenskaper som används för att klassificera innehåll, så att du kan genomdriva åtgärder för det innehållet.
  
![Diagram över DLP-principen med etiketten som villkor](../media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a>Enkla inställningar kontra avancerade inställningar

När du skapar en DLP-princip väljer du mellan enkla eller avancerade inställningar:
  
- **Enkla inställningar** gör det enkelt att skapa den vanligaste typen av DLP-princip utan att använda regelredigeraren för att skapa eller ändra regler. 
    
- **Avancerade inställningar använder** regelredigeraren för att ge dig fullständig kontroll över varje inställning för din DLP-princip. 
    
Oroa dig inte, under täcket fungerar enkla inställningar och avancerade inställningar exakt likadant, genom att genomdriva regler som består av villkor och åtgärder – bara med enkla inställningar ser du inte regelredigeraren. Det är ett snabbt sätt att skapa en DLP-princip.
  
### <a name="simple-settings"></a>Enkla inställningar

Det överlägset vanligaste DLP-scenariot är att skapa en princip för att skydda innehåll som innehåller känslig information från att delas med personer utanför organisationen och vidta en automatisk åtgärd för att åtgärda åtgärder som att begränsa vem som kan komma åt innehållet, skicka slutanvändar- eller administratörsmeddelanden och granska händelsen för senare granskning. Personer använder DLP för att förhindra oavsiktligt utlämnande av känslig information.
  
Om du vill förenkla uppnåendet av det här målet kan du välja Använd enkla inställningar när du **skapar en DLP-princip**. Dessa inställningar ger allt du behöver för att implementera den vanligaste DLP-principen, utan att behöva gå in i regelredigeraren.
  
![DLP-alternativ för enkla och avancerade inställningar](../media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a>Avancerade inställningar

Om du behöver skapa mer anpassade DLP-principer kan du välja **Använd avancerade inställningar**.
  
De avancerade inställningarna ger dig regelredigeraren, där du har full kontroll över alla möjliga alternativ, inklusive antalet instanser och matchningsnoggrannheten (konfidensnivå) för varje regel.
  
Om du snabbt vill gå till ett avsnitt klickar du på ett objekt i regelredigerarens övre navigering för att gå till det avsnittet nedan.
  
![Den översta navigeringsmenyn för DLP-regelredigeraren](../media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a>DLP-principmallar

Det första steget i att skapa en DLP-princip är att välja vilken information som ska skyddas. Genom att börja med en DLP-mall sparar du arbetet med att skapa en ny uppsättning regler från grunden och ta reda på vilka typer av information som ska inkluderas som standard. Du kan sedan lägga till eller ändra dessa krav för att finjustera regeln så att den uppfyller organisationens specifika krav.
  
En förkonfigurerad DLP-principmall kan hjälpa dig att identifiera specifika typer av känslig information, till exempel HIPAA-data, PCI-DSS-data, Gramm-Leach-Bliley Act-data eller till och med språkspecifik personligt identifierbar information (P.I.). För att göra det enkelt för dig att hitta och skydda vanliga typer av känslig information innehåller de principmallar som ingår i Microsoft 365 redan de vanligaste känsliga informationstyperna som krävs för att du ska komma igång.
  
![Lista över mallar för policyer för förebyggande av dataförluster med fokus på mall för U.S. Patriot Act](../media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
Din organisation kan också ha sina egna specifika krav, i vilket fall du kan skapa en DLP-princip från grunden genom att välja **alternativet Anpassad princip.** En anpassad princip är tom och innehåller inga färdiga regler. 
  
<!-- ## Roll out DLP policies gradually with test mode

rehomed to Plan for DLP

When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.
  
If you're creating DLP policies with a large potential impact, we recommend following this sequence:
  
1. **Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization. 
    
2. **Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules. 
    
3. **Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend. 

    ![Options for using test mode and turning on policy](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    You can turn off a DLP policy at any time, which affects all rules in the policy. However, each rule can also be turned off individually by toggling its status in the rule editor.

    ![Options for turning off a rule in a policy](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    You can also change the priority of multiple rules in a policy. To do that, open a policy for editing. In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.

    > [!div class="mx-imgBorder"]
    > ![Set rule priority](../media/dlp-set-rule-priority.png)-->
  
## <a name="dlp-reports"></a>DLP-rapporter

När du har skapat och aktiverar dina DLP-principer vill du verifiera att de fungerar som du tänkt och hjälper dig att hålla dig kompatibel. Med DLP-rapporter kan du snabbt visa antalet DLP-principer och regelmatchningar över tid och antalet falska positiva identifieringar och åsidosättningar. För varje rapport kan du filtrera dessa matchningar efter plats, tidsram och till och med begränsa den till en viss princip, regel eller åtgärd.
  
Med DLP-rapporterna kan du få affärsinsikter och:
  
- Fokusera på vissa tidsperioder och förstå orsakerna till toppar och trender.
    
- Upptäck affärsprocesser som bryter mot organisationens efterlevnadspolicyer.
    
- Förstå alla affärseffekter i DLP-principerna.
    
Dessutom kan du använda DLP-rapporterna för att finjustera dina DLP-principer när du kör dem.
  
![Instrumentpanel för rapporter i Säkerhets- och efterlevnadscenter](../media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a>Så här fungerar DLP-principer

DLP upptäcker känslig information med hjälp av djup innehållsanalys (inte bara en enkel textsökning). Den här djupinnehållsanalysen använder nyckelordsmatchningar, ordlistematchningar, utvärdering av reguljära uttryck, interna funktioner och andra metoder för att identifiera innehåll som matchar dina DLP-principer. Potentiellt anses endast en liten andel av dina data vara känsliga. En DLP-princip kan identifiera, övervaka och automatiskt skydda just dessa data, utan att inverka på eller påverka personer som arbetar med resten av ditt innehåll.
  
### <a name="policies-are-synced"></a>Principer synkroniseras

När du har skapat en DLP-princip i Security &amp; Compliance Center lagras den i ett centralt principarkiv och synkroniseras sedan med de olika innehållskällorna, inklusive:
  
- Exchange Online, och därifrån till Outlook på webben och Outlook.
    
- OneDrive för företag platser.
    
- SharePoint Online-webbplatser.
    
- Office skrivbordsprogram (Excel, PowerPoint och Word).

- Microsoft Teams kanaler och chattmeddelanden.
    
När principen har synkroniserats till rätt platser börjar den utvärdera innehåll och genomdriva åtgärder.
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a>Policyutvärdering på OneDrive för företag och SharePoint onlinewebbplatser

På alla dina SharePoint Online-webbplatser och OneDrive för företag-webbplatser ändras dokument ständigt – de skapas, redigeras, delas och så vidare. Detta innebär att dokument kan komma i konflikt med eller bli kompatibla med en DLP-princip när som helst. En person kan till exempel ladda upp ett dokument som inte innehåller känslig information till gruppwebbplatsen, men senare kan en annan person redigera samma dokument och lägga till känslig information i det.
  
Därför kontrollerar DLP-principer dokument för principmatchningar ofta i bakgrunden. Du kan se detta som asynkron politisk utvärdering.
<!-- what is the frequency? looks like it is tied to the search crawl schedule -->
  
#### <a name="how-it-works"></a>Så här fungerar det
 
När personer lägger till eller ändrar dokument på sina webbplatser skannar sökmotorn innehållet så att du kan söka efter det senare. Medan detta händer genomsöks innehållet också efter känslig information och för att kontrollera om det delas. All känslig information som hittas lagras säkert i sökindexet, så att endast efterlevnadsteamet kan komma åt den, men inte typiska användare. Varje DLP-princip som du har aktiverat körs i bakgrunden (asynkront), söker ofta efter innehåll som matchar en princip och tillämpar åtgärder för att skydda den från oavsiktliga läckor.
  
![Diagram som visar hur DLP-principen utvärderar innehållet asynkront](../media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<!-- conflict with a DLP policy is bad wording -->
Slutligen kan dokument stå i konflikt med en DLP-princip, men de kan också bli kompatibla med en DLP-princip. Om en person till exempel lägger till kreditkortsnummer i ett dokument kan det leda till att en DLP-princip blockerar åtkomsten till dokumentet automatiskt. Men om personen senare tar bort känslig information ångras åtgärden (i det här fallet blockering) automatiskt nästa gång dokumentet utvärderas mot principen.
  
DLP utvärderar allt innehåll som kan indexeras. Mer information om vilka filtyper som genomsöks som standard finns i [Standardtillägg för crawlade filnamn och tosparade filtyper i SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).

> [!NOTE]
> För att förhindra att dokument delas innan DLP-principer hade möjlighet att analysera dem kan delning av nya filer i SharePoint blockeras tills innehållet har indexerats. Se Markera [nya filer som känsliga som standard](/sharepoint/sensitive-by-default) för detaljerad information. 
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a>Policyutvärdering i Exchange Online, Outlook och Outlook på webben

När du skapar en DLP-princip som innehåller Exchange Online som plats synkroniseras principen från Office 365 Security &amp; Compliance Center till Exchange Online och sedan från Exchange Online till Outlook på webben och Outlook.
  
När ett meddelande skrivs i Outlook kan användaren se principtips när innehållet som skapas utvärderas mot DLP-principer. Och när ett meddelande har skickats utvärderas det mot DLP-principer som en normal del av e-postflödet, tillsammans med Exchange-e-postflödesregler (även kallade transportregler) och DLP-principer som skapats i administrationscentret för Exchange. DLP-principer söker igenom både meddelandet och eventuella bifogade filer.
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a>Principutvärdering i Office skrivbordsprogram

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
Excel, PowerPoint och Word samma funktion för att identifiera känslig information och tillämpa DLP-principer som SharePoint Online och OneDrive för företag. Dessa Office-program synkroniserar sina DLP-principer direkt från det centrala principarkivet och utvärderar sedan kontinuerligt innehållet mot DLP-principerna när personer arbetar med dokument som öppnas från en webbplats som ingår i en DLP-princip.
  
DLP-policyutvärdering Office är utformad för att inte påverka programmens prestanda eller produktiviteten hos personer som arbetar med innehåll. Om de arbetar med ett stort dokument, eller om användarens dator är upptagen, kan det ta några sekunder innan ett principtips visas.

### <a name="policy-evaluation-in-microsoft-teams"></a>Politisk utvärdering i Microsoft Teams
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

När du skapar en DLP-princip som innehåller Microsoft Teams som plats synkroniseras principen från Office 365 Security &amp; Compliance Center till användarkonton och Microsoft Teams-kanaler och chattmeddelanden. Beroende på hur DLP-principer konfigureras kan meddelandet blockeras eller återkallas när någon försöker dela känslig information i en Microsoft Teams-chatt eller kanalmeddelande. Och dokument som innehåller känslig information och som delas med gäster (externa användare) öppnas inte för dessa användare. Mer information finns i [Dataförlustförebyggande och Microsoft Teams](dlp-microsoft-teams.md).
 
## <a name="permissions"></a>Behörigheter

Medlemmar i ditt efterlevnadsteam som skapar DLP-principer behöver behörighet till Security &amp; Compliance Center. Som standard har din klient administratör åtkomst till den här platsen och kan ge efterlevnadsansvariga och andra personer åtkomst till Security Compliance Center, utan att ge dem &amp; alla behörigheter för en klient administratör. För att göra detta rekommenderar vi att du:
  
1. Skapa en grupp i Microsoft 365 lägga till efterlevnadsansvariga i den.
    
2. Skapa en rollgrupp på sidan **Behörigheter** i Security &amp; Compliance Center. 

3. När du skapar rollgruppen använder du avsnittet **Välj roller för** att lägga till följande roll i rollgruppen: **DLP Compliance Management**.
    
4. Använd avsnittet **Välj medlemmar om** du vill lägga Microsoft 365 den grupp som du har skapat tidigare i rollgruppen.

Du kan också skapa en rollgrupp med skrivbehörighet till DLP-principerna och DLP-rapporterna genom att bevilja **rollen Endast visning av DLP-efterlevnad.**

Mer information finns i [Ge användarna åtkomst till Office 365 Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
Dessa behörigheter krävs bara för att skapa och tillämpa en DLP-princip. Tvingande princip kräver inte åtkomst till innehållet.
  
## <a name="find-the-dlp-cmdlets"></a>Hitta DLP-cmdlets

Om du vill använda de flesta cmdletar för Security &amp; Compliance Center måste du:
  
1. [Anslut till Office 365 Security &amp; Compliance Center med fjärr-PowerShell](/powershell/exchange/connect-to-scc-powershell).
    
2. Använd någon av dessa [policy-and-compliance-dlp cmdlets](/powershell/module/exchange/export-dlppolicycollection).
    
DLP-rapporter behöver dock hämta data från Microsoft 365, inklusive Exchange Online. Därför är **cmdlets för DLP-rapporterna tillgängliga i Exchange Online Powershell – inte i Security &amp; Compliance Center Powershell**. För att använda cmdlets för DLP-rapporterna måste du därför:
  
1. [Ansluta till Exchange Online med fjärr-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
    
2. Använd någon av dessa cmdletar för DLP-rapporterna:
    
    - [Hämta-DlpDetectionsRapport](/powershell/module/exchange/Get-DlpDetectionsReport)

    - [Get-DlpDetailRapport](/powershell/module/exchange/Get-DlpDetailReport)
    
## <a name="more-information"></a>Mer information

- [Skapa en DLP-princip från en mall](create-a-dlp-policy-from-a-template.md)
    
- [Skicka meddelanden och visa principtips för DLP-principer](use-notifications-and-policy-tips.md)
    
- [Skapa en DLP-princip för att skydda dokument med FCI eller andra egenskaper](protect-documents-that-have-fci-or-other-properties.md)
    
- [Det här innehåller DLP-principmallarna](what-the-dlp-policy-templates-include.md)
    
- [Entitetsdefinitioner för typer av känslig information](sensitive-information-type-entity-definitions.md)
    
- [Vad DLP-funktionerna letar efter](what-the-dlp-functions-look-for.md)
    
- [Skapa en anpassad känslig informationstyp](create-a-custom-sensitive-information-type.md)
