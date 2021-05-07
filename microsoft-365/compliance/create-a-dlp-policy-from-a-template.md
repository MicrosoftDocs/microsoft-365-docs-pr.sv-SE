---
title: Skapa en DLP-princip från en mall
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-mar2020
description: I den här artikeln får du lära dig hur du skapar DLP-principer med hjälp av någon av mallarna som ingår i Office 365.
ms.openlocfilehash: 0088381698b47b2451f52fde32716a2436e8c073
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162944"
---
# <a name="create-a-dlp-policy-from-a-template"></a>Skapa en DLP-princip från en mall

Det enklaste sättet att komma igång med DLP-principer är att använda någon av mallarna som ingår i Office 365. Du kan använda någon av mallarna som den är eller anpassa reglerna så att de uppfyller organisationens specifika efterlevnadskrav.
  
Microsoft 365 finns fler än 40 färdiga mallar som kan hjälpa dig att uppfylla en mängd vanliga regel- och affärspolicybehov. Det finns till exempel DLP-principmallar för:
  
- Gramm-Leach-Bliley Act (GLBA)
    
- Datasäkerhetsstandard för betalningskort (SÄTT-DSS)
    
- Personlig information i USA (PII)
    
- United States Health Insurance Act (HIPAA)
    
Du kan finjustera en mall genom att ändra någon av de befintliga reglerna eller lägga till nya. Du kan till exempel lägga till nya typer av känslig information i en regel, ändra antalet i en regel för att göra det svårare eller enklare att utlösa, tillåta personer att åsidosätta åtgärder i en regel genom att ange en justering för verksamheten eller ändra vem aviseringar och incidentrapporter skickas till. En DLP-principmall är en flexibel utgångspunkt för många vanliga scenarier för efterlevnad.
  
Du kan också välja mallen Anpassad, som inte har några standardregler, och konfigurera din DLP-princip från grunden för att uppfylla organisationens specifika efterlevnadskrav.
  
## <a name="example-identify-sensitive-information-across-all-onedrive-for-business-sites-and-restrict-access-for-people-outside-your-organization"></a>Exempel: Identifiera känslig information på alla OneDrive för företag och begränsa åtkomsten för personer utanför organisationen

OneDrive för företag-konton gör det enkelt för personer i organisationen att samarbeta och dela dokument. Men ett vanligt problem för efterlevnadsansvariga är att känslig information som lagras i OneDrive för företag-konton kan oavsiktligt delas med personer utanför organisationen. En DLP-princip kan minska den här risken.
  
I det här exemplet skapar du en DLP-princip som identifierar amerikanska PII-data, som omfattar INDIVIDUAL Taxpayer Identification Numbers (ITIN), personnummer och amerikanska passnummer. Du börjar med att använda en mall och sedan ändrar du mallen så att den uppfyller organisationens efterlevnadskrav, och mer specifikt:
  
- Lägg till ett par olika typer av känslig information – bankkontonummer och amerikanska körkort – så att DLP-policyn skyddar ännu mer av dina känsliga data.
    
- Gör principen mer känslig, så att en enda förekomst av känslig information räcker för att begränsa åtkomsten för externa användare.
    
- Tillåt att användare åsidosätter åtgärderna genom att ange en justering för ett företag eller rapportera en felaktig positiv inställning. På så sätt hindrar inte DLP-principen användare i organisationen från att få jobbet gjort, förutsatt att de har en giltig affärsorsak för att dela känslig information.
    
### <a name="create-a-dlp-policy-from-a-template"></a>Skapa en DLP-princip från en mall

1. Gå till [https://protection.office.com](https://protection.office.com).
    
2. Logga in med ditt arbets- eller skolkonto. Nu är du i &amp; säkerhetsefterlevnadscentret.
    
3. I det vänstra &amp; \> navigeringscentret för \> **säkerhetsefterlevnad finns Policy för** \> **dataförlustskydd** + Skapa en \> **princip.**
    
    ![Knappen Skapa en princip](../media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. Välj den DLP-principmall som skyddar de typer av känslig information som du behöver \> **.**
    
    I det här exemplet  väljer du Personligt identifierbar information \> **(PII),** eftersom den redan innehåller de flesta typer av känslig information som du vill skydda, och lägger till några senare. 
    
    När du väljer en mall kan du läsa beskrivningen till höger om du vill veta vilka typer av känslig information som mallen skyddar.
    
    ![Sida för att välja en DLP-principmall](../media/775266f6-ad87-4080-8d7c-97f2e7403b30.png)
  
5. Namnge principen \> **Nästa.**
    
6. Välj platser som du vill att DLP-principen ska skydda genom att göra något av följande:
    
  - Välj **Alla platser i Office 365** \> **Nästa.**
    
  - Välj **Let me choose specific locations** \> **Next**. I det här exemplet väljer du det här.
    
    Om du vill inkludera eller exkludera en hel plats, till exempel all e Exchange post eller alla OneDrive-konton, ska du slå på eller stänga av **statusen** för den platsen. 
    
    Om du bara vill SharePoint specifika webbplatser eller OneDrive för företag-konton, växlar du status till på och klickar sedan på länkarna **under** Inkludera för att välja specifika webbplatser eller konton.  När du tillämpar en princip på en webbplats tillämpas reglerna som konfigurerats i den principen automatiskt på alla underwebbplatser till den webbplatsen. 
    
    ![Alternativ för platser där en DLP-princip kan tillämpas](../media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
    I det här exemplet ska du inaktivera **Status** för både Exchange-e-post och SharePoint-webbplatser för att skydda känslig information som lagras i alla OneDrive för företag-konton och lämna **Status** på för  **OneDrive-konton.** 
    
7. Välj **Använd avancerade inställningar** \> **Nästa.**
    
8. En DLP-principmall innehåller fördefinierade regler med villkor och åtgärder som identifierar och agerar på vissa typer av känslig information. Du kan redigera, ta bort eller inaktivera befintliga regler eller lägga till nya. Klicka på Nästa när du är **klar.**
    
    ![Regler som expanderats i mallen FÖR PII-policy i USA](../media/3bc9f1b6-f8ad-4334-863a-24448bb87687.png)
  
    I det här exemplet innehåller mallen U.S. PII Data två fördefinierade regler:
    
  - **Låg volym av upptäckt U.S. PII** Den här regeln söker efter filer som innehåller mellan 1 och 10 förekomster av var och en av tre typer av känslig information (ITIN, SSN och amerikanska passnummer), där filerna delas med personer utanför organisationen. Om den hittas skickar regeln ett e-postmeddelande till den primära administratören för webbplatssamlingen, dokumentägaren och personen som senast ändrade dokumentet. 
    
  - **Hög volym av upptäckt U.S. PII** Den här regeln söker efter filer som innehåller 10 eller fler förekomster av samma tre typer av känslig information, där filerna delas med personer utanför organisationen. Om den hittas skickas även ett e-postmeddelande med den här åtgärden, och åtkomsten till filen begränsas. För innehåll i ett OneDrive för företag-konto innebär det att behörigheterna för dokumentet är begränsade för alla utom den primära administratören för webbplatssamlingen, dokumentägaren och den person som senast ändrade dokumentet. 
    
    För att uppfylla organisationens specifika krav kanske du vill göra reglerna lättare att utlösa, så att en enda förekomst av känslig information räcker för att blockera åtkomst för externa användare. När du har tittat på dessa regler förstår du att du inte behöver regler för lågt och högt antal – du behöver bara en enda regel som blockerar åtkomst om du hittar någon förekomst av känslig information.
    
    Du expanderar alltså regeln Låg **volym innehåll som identifierats av U.S. PII** \> **Delete-regeln**.
    
    ![Knappen Ta bort regel](../media/bc36f7d2-0fae-4af1-92e8-95ba51077b12.png)
  
9. I det här exemplet behöver du nu lägga till två typer av känslig information (bankkontonummer och amerikanska körkort), tillåta personer att åsidosätta en regel och ändra antalet till förekomster. Du kan göra allt detta genom att redigera en regel, så välj Hög volym innehåll som upptäckts i **U.S.** \> **PII-redigeringsregel**.
    
    ![Knappen Redigera regel](../media/eaf54067-4945-4c98-8dd6-fb2c5d6de075.png)
  
10. Om du vill lägga till en typ av känslig information går **du till avsnittet Villkor** Lägga till eller ändra \> **typer**. Under Lägg **till eller ändra typer** väljer du Lägg till välj \>  \> **U.S. Bank Account Number** och **U.S. Driver's License Number** \> **Add** \> **Done.**
    
    ![Alternativ för att lägga till eller ändra typer](../media/c6c3ae86-f7db-40a8-a6e4-db11692024be.png)
  
    ![Fönstret Lägg till eller ändra typer](../media/fdbb96af-b914-4a6c-a97b-bbd014689965.png)
  
11. Om du vill ändra antalet (antalet förekomster av känslig information som krävs för att utlösa regeln) **väljer** du min-värdet för varje typ under Antal instanser \> för varje typ genom att ange  \> 1. Minimiantalet kan inte vara tomt. Maxantalet kan vara tomt. ett tomt **maxvärde** konverteras till **ett**.
    
    När det är klart ska det minsta antalet för alla typer av känslig information vara **1** och maxantalet ska vara **vilket som helst.** Alla förekomster av den här typen av känslig information uppfyller med andra ord detta villkor.
    
    ![Antal förekomster för typer av känslig information](../media/5c6e08cb-59a9-4558-b54b-d899836d4737.png)
  
12. För den slutliga anpassningen vill du inte att DLP-principerna ska blockera personer från att göra sitt arbete när de har en giltig affärs motivering eller stöter på en felaktig positiv inställning, så du vill att användarmeddelandet ska innehålla alternativ för att åsidosätta blockeringen.
    
    I avsnittet **Användarmeddelanden** ser du att e-postmeddelanden och principtips är aktiverat som standard för den här regeln i mallen. 
    
    I avsnittet **Åsidosättningar för** användare kan du se att åsidosättningar för en justering för företag är aktiverat, men åsidosättningar för att rapportera falska positiva resultat är inte aktiverat. Välj **Åsidosätt regeln automatiskt om de rapporterar den som en felaktig positiv inställning.**
    
    ![Avsnittet Användarmeddelanden och avsnittet Åsidosätter användare](../media/62720e7a-a939-4c03-b414-67748f3d64a0.png)
  
13. Högst upp i regelredigeraren ändrar du namnet på  regeln från standardvolymen Hög innehåll som upptäckts i USA till Allt innehåll som upptäckts med **amerikanskT PII** eftersom det nu utlöses av alla förekomster av känslig information. 
    
14. Längst ned i regelredigeraren \> **Spara**.
    
15. Granska villkoren och åtgärderna för den här regeln \> **Nästa.**
    
    Observera växeln **Status till** höger för regeln. Om du inaktiverar en hel princip inaktiveras även alla regler som finns i principen. Här kan du inaktivera en viss regel utan att inaktivera hela principen. Det kan vara användbart när du behöver undersöka en regel som genererar ett stort antal falska positiva resultat. 
    
16. På nästa sida läser och förstår du följande och väljer sedan om du vill aktivera regeln eller testa den först \> **Nästa.**
    
     Innan du skapar DLP-principerna bör du överväga att lansera dem gradvis för att bedöma deras påverkan och testa deras effektivitet innan du tillämpar dem helt. Du kanske till exempel inte vill att en ny DLP-princip oavsiktligt ska blockera åtkomst till tusentals dokument som personer behöver för att få jobbet gjort. 
    
    Om du skapar DLP-principer med stor potential rekommenderar vi att du följer den här ordningen:
    
17. Börja i testläge utan Tips och använd sedan DLP-rapporterna för att bedöma påverkan. Du kan använda DLP-rapporter för att visa antal, plats, typ och allvarlighetsgrad för principmatchningar. Baserat på resultatet kan du finjustera reglerna efter behov. I testläge påverkar inte DLP-principerna produktiviteten för personer som arbetar i organisationen. 
    
18. Flytta till testläget med meddelanden och princip Tips så att du kan börja lära användarna om dina efterlevnadsprinciper och förbereda dem för de regler som kommer att tillämpas. I det här läget kan du också be användarna att rapportera falska positiva resultat så att du kan ytterligare förfina reglerna.
    
19. Aktivera principerna så att reglerna tillämpas och innehållet skyddas. Fortsätt att övervaka DLP-rapporterna och eventuella incidentrapporter och -aviseringar för att se till att du får de resultat du vill ha. 
    
    ![Alternativ för att använda testläge och aktivera princip](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
20. Granska inställningarna för den här principen \> genom att välja **Skapa**.
    
När du har skapat och aktiverar en DLP-princip distribueras den till alla innehållskällor som den innehåller, till exempel SharePoint Online-webbplatser eller OneDrive för företag-konton, där principen börjar tillämpa regler automatiskt på innehållet.
  
## <a name="view-the-status-of-a-dlp-policy"></a>Visa status för en DLP-princip

Du kan när som helst visa status för  DLP-principerna på sidan Princip i avsnittet Skydd mot **dataförlust** i &amp; Säkerhetsefterlevnad. Här hittar du viktig information, till exempel om en princip har aktiverats eller inaktiverats eller om principen är i testläge. 
  
Här är de olika statusarna och vad de betyder.
  
|**Status**|**Förklaring**|
|:-----|:-----|
|**Aktivera...** <br/> |Principen distribueras till de innehållskällor som den innehåller. Principen tillämpas ännu inte på alla källor.  <br/> |
|**Testa, med meddelanden** <br/> |Principen är i testläge. Åtgärderna i en regel tillämpas inte, men principmatchningar samlas in och kan visas med hjälp av DLP-rapporterna. Meddelanden om principmatchningar skickas till de angivna mottagarna.  <br/> |
|**Testar, utan aviseringar** <br/> |Principen är i testläge. Åtgärderna i en regel tillämpas inte, men principmatchningar samlas in och kan visas med hjälp av DLP-rapporterna. Meddelanden om principmatchningar skickas inte till de angivna mottagarna.  <br/> |
|**På** <br/> |Principen är aktiv och används. Principen har distribuerats till alla dess innehållskällor.  <br/> |
|**Stänger av...** <br/> |Principen tas bort från de innehållskällor som den innehåller. Principen kan fortfarande vara aktiv och tillämpad på vissa källor. Det kan ta upp till 45 minuter att inaktivera en princip.  <br/> |
|**Av** <br/> |Principen är inte aktiv och tillämpas inte. Inställningarna för principen (källor, nyckelord, varaktighet osv.) sparas.  <br/> |
|**Tar bort...** <br/> |Principen håller på att tas bort. Principen är inte aktiv och tillämpas inte. Det tar normalt en timme för en princip att delet <br/> |
   
## <a name="turn-off-a-dlp-policy"></a>Inaktivera en DLP-princip

Du kan redigera eller inaktivera en DLP-princip när som helst. Om du stänger av en princip inaktiveras alla regler i principen.
  
Om du vill redigera eller inaktivera en DLP-princip markerar du **principen** Redigera \> princip på sidan \> **Princip.**
  
![Knappen Redigera princip](../media/ce319e92-0519-44fe-9507-45a409eaefe4.png)
  
Du kan dessutom inaktivera varje regel individuellt genom att redigera principen och sedan inaktivera **status** för den regeln, enligt beskrivningen ovan. 
  
## <a name="more-information"></a>Mer information

- [Mer information om skydd mot dataförlust](dlp-learn-about-dlp.md)
- [Skicka meddelanden och visa principtips för DLP-principer](use-notifications-and-policy-tips.md)
- [Skapa en DLP-princip för att skydda dokument med FCI eller andra egenskaper](protect-documents-that-have-fci-or-other-properties.md)
- [Det här innehåller DLP-principmallarna](what-the-dlp-policy-templates-include.md)
- [Entitetsdefinitioner för typer av känslig information](sensitive-information-type-entity-definitions.md)
