---
title: Skapa, testa och justera en DLP-princip
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
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
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: I den här artikeln får du lära dig hur du skapar, testar och justerar en DLP-princip enligt dina organisatoriska behov.
ms.openlocfilehash: 3b7f74605c8a825bb03244f3a861ad3cca8f550d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572579"
---
# <a name="create-test-and-tune-a-dlp-policy"></a>Skapa, testa och justera en DLP-princip

DLP (Data Loss Prevention) hjälper dig att förhindra oavsiktlig eller oavsiktlig delning av känslig information.

DLP undersöker e-postmeddelanden och filer efter känslig information, till exempel ett kreditkortsnummer. Med DLP kan du identifiera känslig information och vidta åtgärder som:

- Logga händelsen för granskningsändamål
- Visa en varning till slutanvändaren som skickar e-postmeddelandet eller delar filen
- Blockera aktivt e-post- eller fildelningen från att äga rum

## <a name="permissions"></a>Behörigheter

Medlemmar i ditt efterlevnadsteam som skapar DLP-principer behöver behörighet till Compliance Center. Som standard har din klient administratör åtkomst kan ge efterlevnads tjänstemän och andra personer åtkomst. Gör så här:
  
1. Skapa en grupp i Microsoft 365 lägga till efterlevnadsansvariga i den.
    
2. Skapa en rollgrupp på sidan **Behörigheter** i Security &amp; Compliance Center. 

3. När du skapar rollgruppen använder du avsnittet **Välj roller för** att lägga till följande roll i rollgruppen: **DLP Compliance Management**.
    
4. Använd avsnittet **Välj medlemmar om** du vill lägga Microsoft 365 den grupp som du har skapat tidigare i rollgruppen.

Använd rollen **Endast visa DLP-efterlevnad för** att skapa rollgrupp med skrivbehörighet till DLP-principerna och DLP-rapporterna.

Mer information finns i [Ge användarna åtkomst till Office 365 Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
Dessa behörigheter krävs för att skapa och tillämpa en DLP-princip för att inte genomdriva principer.

## <a name="how-sensitive-information-is-detected-by-dlp"></a>Hur känslig information identifieras av DLP

DLP hittar känslig information efter regex-mönstermatchning (Regular Expression), i kombination med andra indikatorer, till exempel närheten till vissa nyckelord till matchningsmönstren. Ett VISA-kreditkortsnummer har till exempel 16 siffror. Men dessa siffror kan skrivas på olika sätt, till exempel 1111-1111-1111-1111, 1111 1111 1111 1111, eller 11111111111111111111.

Alla 16-siffriga strängar är inte nödvändigtvis ett kreditkortsnummer, det kan vara ett biljettnummer från ett helpdesksystem eller ett serienummer för en hårdvara. För att se skillnaden mellan ett kreditkortsnummer och en ofarlig 16-siffrig sträng utförs en beräkning (kontrollsumma) för att bekräfta att siffrorna matchar ett känt mönster från de olika kreditkortsmärkena.

Om DLP hittar nyckelord som "VISA" eller "AMEX", nära datumvärden som kan vara kreditkortens utgångsdatum, använder DLP också dessa data för att avgöra om strängen är ett kreditkortsnummer eller inte.

Med andra ord är DLP smart nog att känna igen skillnaden mellan dessa två textsträngar i ett e-postmeddelande:

- "Kan du beställa mig en ny bärbar dator. Använd mitt VISA-nummer 1111-1111-1111-1111, utgång 11/22, och skicka mig det beräknade leveransdatumet när du har det."
- "Mitt serienummer för bärbara datorer är 2222-2222-2222-2222 och det köptes den 11/2010. Förresten, är mitt resevisum godkänt ännu?"

Se [Definitioner av känslig informationstyp som](sensitive-information-type-entity-definitions.md) förklarar hur varje informationstyp identifieras.

## <a name="where-to-start-with-data-loss-prevention"></a>Var ska man börja med förebyggande av dataförlust

När riskerna för dataläckage inte är helt uppenbara är det svårt att räkna ut exakt var du ska börja med att implementera DLP. Lyckligtvis kan DLP-principer köras i "testläge", så att du kan mäta deras effektivitet och noggrannhet innan du slår på dem.

DLP-principer Exchange Online kan hanteras via Exchange administrationscenter. Men du kan konfigurera DLP-principer för alla arbets belastningar via Security & Compliance Center, så det är vad jag kommer att använda för demonstrationer i den här artikeln. I Security & Compliance Center hittar du DLP-principerna under Policy **för förebyggande av**  >  **dataförlust**. Välj **Skapa en princip som** ska startas.

Microsoft 365 tillhandahåller en rad [DLP-principmallar som du](what-the-dlp-policy-templates-include.md) kan använda för att skapa principer. Låt oss säga att du är ett australiskt företag. Du kan filtrera mallarna i Australien och välja Ekonomi, Medicin och Hälsa och Sekretess.

![Alternativ för att välja land eller region](../media/DLP-create-test-tune-choose-country.png)

För den här demonstrationen väljer jag australiensiska personligt identifierbara informationsdata (PII), som innehåller informationstyperna för australiensiskt skattefilnummer (TFN) och körkortsnummer.

![Alternativ för att välja en principmall](../media/DLP-create-test-tune-choose-policy-template.png)

Ge din nya DLP-policy ett namn. Standardnamnet matchar DLP-principmallen, men du bör välja ett eget beskrivande namn eftersom flera principer kan skapas från samma mall.

![Alternativ för att namnge din policy](../media/DLP-create-test-tune-name-policy.png)

Välj de platser som principen ska gälla för. DLP-principer kan gälla för Exchange Online, SharePoint Online och OneDrive för företag. Jag kommer att lämna den här principen konfigurerad för att gälla för alla platser.

![Alternativ för att välja alla platser](../media/DLP-create-test-tune-choose-locations.png)

Vid det första **Inställningar** steget, acceptera bara standardvärdena för tillfället. Du kan anpassa DLP-principer, men standardvärdena är en bra plats att börja på.

![Alternativ för att anpassa typen av innehåll för att skydda](../media/DLP-create-test-tune-default-customization-settings.png)

När du har klickat på Nästa får du en mer **princip Inställningar** sida med fler anpassningsalternativ. För en princip som du bara testar, här kan du börja göra några justeringar.

- Jag har stängt av principtips för tillfället, vilket är ett rimligt steg att ta om du bara testar saker och inte vill visa något för användarna ännu. Principtips visar varningar till användare om att de är på väg att bryta mot en DLP-policy. En användare som Outlook en varning om att filen de har bifogat innehåller kreditkortsnummer och gör att deras e-post avvisas. Målet med principtips är att stoppa det beteende som inte uppfyller kraven innan det inträffar.
- Jag har också minskat antalet instanser från 10 till 1, så att den här policyn kommer att upptäcka all delning av australiska PII-data, inte bara massdelning av data.
- Jag har också lagt till en annan mottagare i incidentrapportens e-post.

![Ytterligare principinställningar](../media/DLP-create-test-tune-more-policy-settings.png)

Slutligen har jag konfigurerat den här principen så att den körs i testläge från början. Observera att det också finns ett alternativ här för att inaktivera principtips när du är i testläge. Detta ger dig flexibiliteten att ha princip tips aktiverade i principen, men sedan bestämma om du vill visa eller undertrycka dem under testningen.

![Alternativ för att testa principen först](../media/DLP-create-test-tune-test-mode.png)

Klicka på Skapa för att slutföra **skapandet av** principen på den slutliga granskningsskärmen.

## <a name="test-a-dlp-policy"></a>Testa en DLP-princip

Din nya DLP-policy börjar gälla inom cirka 1 timme. Du kan sitta och vänta på att den utlöses av normal användaraktivitet, eller så kan du försöka utlösa den själv. Tidigare länkade jag till [känsliga entitetsdefinitioner av informationstyp](sensitive-information-type-entity-definitions.md), som ger dig information om hur du utlöser DLP-matchningar.

Som ett exempel kommer DLP-principen som jag skapade för den här artikeln att identifiera australiska skattefilnummer (TFN). Enligt dokumentationen baseras matchen på följande kriterier.

![Dokumentation om Australiens skattefilnummer](../media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
För att demonstrera TFN-identifiering på ett ganska trubbigt sätt kommer ett e-postmeddelande med orden "Skattefilnummer" och en niosiffrig sträng i närheten att segla igenom utan problem. Anledningen till att DLP-principen inte utlöses är att den niosiffriga strängen måste skicka kontrollsumman som anger att den är ett giltigt TFN och inte bara en ofarlig sträng med tal.

![Australien skattefilnummer som inte klarar kontrollsumma](../media/DLP-create-test-tune-email-test1.png)

I jämförelse utlöser ett e-postmeddelande med orden "Momsfilnummer" och ett giltigt TFN som passerar kontrollsumman principen. För posten här togs TFN jag använder från en webbplats som genererar giltiga, men inte äkta, TFNs. Sådana webbplatser är användbara eftersom ett av de vanligaste misstagen när du testar en DLP-princip är att använda ett falskt nummer som inte är giltigt och inte kommer att klara kontrollsumman (och därför inte utlöser principen).

![Australien skattefilnummer som passerar kontrollsumman](../media/DLP-create-test-tune-email-test2.png)

E-postmeddelandet med incidentrapporten innehåller den typ av känslig information som upptäcktes, hur många instanser som identifierades och identifieringens konfidensnivå.

![Incidentrapport som visar upptäckt momsfilnummer](../media/DLP-create-test-tune-email-incident-report.png)

Om du lämnar din DLP-policy i testläge och analyserar e-postmeddelandena i incidentrapporten kan du börja få en känsla för DLP-principens noggrannhet och hur effektiv den kommer att vara när den tillämpas. Förutom incident rapporterna kan du använda [DLP-rapporterna för att se](view-the-dlp-reports.md) en aggregerad vy över princip matchningar över din klient organisation.

## <a name="tune-a-dlp-policy"></a>Justera en DLP-policy

När du analyserar dina principträffar kanske du vill göra några justeringar av hur principerna beter sig. Som ett enkelt exempel kan du bestämma att en TFN i ett e-postmeddelande inte är ett problem (jag tror att det fortfarande är det, men låt oss gå med det för demonstrationens skull), men två eller flera instanser är ett problem. Flera instanser kan vara ett riskabelt scenario, till exempel en anställd som skickar en CSV-export från HR-databasen till en extern part, till exempel en extern redovisningstjänst. Definitivt något du föredrar att upptäcka och blockera.

I Compliance Center kan du redigera en befintlig princip för att justera beteendet.

![Alternativ för att redigera princip](../media/DLP-create-test-tune-edit-policy.png)
 
Du kan justera platsinställningarna så att principen endast tillämpas på specifika arbets belastningar eller på specifika webbplatser och konton.

![Alternativ för att välja specifika platser](../media/DLP-create-test-tune-edit-locations.png)

Du kan också justera principinställningarna och redigera reglerna så att de bättre passar dina behov.

![Alternativ för att redigera regel](../media/DLP-create-test-tune-edit-rule.png)

När du redigerar en regel inom en DLP-princip kan du ändra:

- Villkoren, inklusive typen och antalet instanser av känsliga data som utlöser regeln.
- De åtgärder som vidtas, till exempel att begränsa åtkomsten till innehållet.
- Användaraviseringar, som är principtips som visas för användaren i deras e-postklient eller webbläsare.
- Användaren åsidosätter avgör om användare kan välja att fortsätta med sin e-post eller fildelning ändå.
- Incidentrapporter, för att meddela administratörer.

![Alternativ för att redigera delar av en regel](../media/DLP-create-test-tune-editing-options.png)

För den här demonstrationen har jag lagt till användar aviseringar i principen (var försiktig med att göra detta utan adekvat utbildning om användar medvetenhet) och tillät användare att åsidosätta principen med en affärs motivering eller genom att flagga den som en falsk positiv. Du kan också anpassa e-post- och principtipstexten om du vill inkludera ytterligare information om organisationens principer eller uppmana användare att kontakta supporten om de har frågor.

![Alternativ för användarmeddelanden och åsidosättningar](../media/DLP-create-test-tune-user-notifications.png)

Principen innehåller två regler för hantering av hög volym och låg volym, så se till att redigera båda med de åtgärder du vill ha. Detta är en möjlighet att behandla fall olika beroende på deras egenskaper. Du kan till exempel tillåta åsidosättningar för överträdelser med låg volym, men inte tillåta åsidosättningar för överträdelser med hög volym.

![En regel för hög volym och en regel för låg volym](../media/DLP-create-test-tune-two-rules.png)

Om du faktiskt vill blockera eller begränsa åtkomsten till innehåll som strider mot principen måste du konfigurera en åtgärd på regeln för att göra det.

![Alternativ för att begränsa åtkomsten till innehåll](../media/DLP-create-test-tune-restrict-access-action.png)

När jag har sparat ändringarna i principinställningarna måste jag också gå tillbaka till huvudinrättningssidan för principen och göra det möjligt för alternativet att visa principtips för användare medan principen är i testläge. Detta är ett effektivt sätt att introducera DLP-principer för dina slutanvändare och göra utbildning i användarmedvetenhet, utan att riskera för många falska positiva effekter som påverkar deras produktivitet.

![Alternativ för att visa principtips i testläge](../media/DLP-create-test-tune-show-policy-tips.png)

På serversidan (eller molnsidan om du föredrar) kanske ändringen inte träder i kraft omedelbart på grund av olika bearbetningsintervall. Om du gör en DLP-principändring som visar nya principtips för en användare kanske användaren inte ser att ändringarna träder i kraft omedelbart i Outlook-klienten, som söker efter principändringar var 24:e timme. Om du vill påskynda testningen kan du använda den här registerkorrigeringen för att [rensa den senaste hämtningstidsstämpeln från nyckeln PolicyNudges](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451). Outlook hämtar den senaste principinformationen nästa gång du startar om den och börjar skriva ett e-postmeddelande.

Om du har aktiverat principtips börjar användaren se tipsen i Outlook och kan rapportera falska positiva identifieringar till dig när de inträffar.

![Principtips med möjlighet att rapportera falskt positivt](../media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a>Undersök falska positiva identifieringar

DLP-policymallar är inte perfekta direkt ur lådan. Det är troligt att du hittar några falska positiva identifieringar som uppstår i din miljö, varför det är så viktigt att underlätta din väg in i en DLP-distribution, vilket tar dig tid att testa och finjustera dina principer på ett adekvat sätt.

Här är ett exempel på ett falskt positivt. Det här e-postmeddelandet är ganska ofarligt. Användaren tillhandahåller sitt mobiltelefonnummer till någon och inkluderar sin e-postsignatur.

![E-post som visar falsk positiv information](../media/DLP-create-test-tune-false-positive-email.png)
 
Men användaren ser ett policytips som varnar dem om att e-postmeddelandet innehåller känslig information, specifikt ett australiskt körkortsnummer.

![Alternativ för att rapportera falskt positivt i principtips](../media/DLP-create-test-tune-policy-tip-closeup.png)

Användaren kan rapportera det falska positiva och administratören kan undersöka varför det har inträffat. I e-postmeddelandet med incidentrapporten flaggas e-postmeddelandet som falskt positivt.

![Incidentrapport som visar falskt positivt](../media/DLP-create-test-tune-false-positive-incident-report.png)

Detta körkortsärende är ett bra exempel att gräva i. Anledningen till att detta falska positiva har inträffat är att typen "Australian Driver's License" kommer att utlösas av alla 9-siffriga strängar (även en som ingår i en 10-siffrig sträng), inom 300 tecken närhet till nyckelorden "Sydney nsw" (inte fallkänslig). Så det utlöses av telefonnumret och e-postsignaturen, bara för att användaren råkar vara i Sydney.


Ett alternativ är att ta bort den australiska körkortsinformationstypen från policyn. Den finns där eftersom den är en del av DLP-policymallen, men vi är inte tvungna att använda den. Om du bara är intresserad av skattefilnummer och inte körkort kan du bara ta bort det. Du kan till exempel ta bort den från lågvolymregeln i principen, men lämna den i högvolymsregeln så att listor med flera körkort fortfarande identifieras.
 
Ett annat alternativ är att öka antalet instanser, så att en låg volym körkort bara identifieras när det finns flera instanser.

![Alternativ för att redigera antalet förekomster](../media/DLP-create-test-tune-edit-instance-count.png)

Förutom att ändra antalet förekomster kan du också justera matchningsnoggrannheten (eller konfidensnivån). Om din känsliga informationstyp har flera mönster kan du justera matchningsnoggrannheten i regeln så att regeln bara matchar specifika mönster. Om du till exempel vill minska falska positiva identifieringar kan du ställa in matchningsnoggrannheten för regeln så att den bara matchar mönstret med den högsta konfidensnivån. Mer information om förtroendenivåer finns i Så [här använder du konfidensnivå för att justera dina regler](data-loss-prevention-policies.md#match-accuracy).

Slutligen, om du vill bli ännu mer avancerad, kan du anpassa alla känsliga informationstyper - till exempel kan du ta bort "Sydney NSW" från listan över nyckelord för [Australiens körkortsnummer](sensitive-information-type-entity-definitions.md#australia-drivers-license-number), för att eliminera det falska positiva som utlöses ovan. Mer information om hur du gör detta med hjälp av XML och PowerShell finns [i anpassa en inbyggd känslig informationstyp](customize-a-built-in-sensitive-information-type.md).

## <a name="turn-on-a-dlp-policy"></a>Aktivera en DLP-princip

När du är glad över att din DLP-princip korrekt och effektivt identifierar känsliga informationstyper och att dina slutanvändare är redo att hantera de principer som finns på plats kan du aktivera principen.

![Alternativ för att aktivera principen](../media/DLP-create-test-tune-turn-on-policy.png)
 
Om du väntar på att se när principen träder i kraft [Anslut till Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) och kör [cmdleten Get-DlpCompliancePolicy för](/powershell/module/exchange/get-dlpcompliancepolicy) att se DistributionStatus.

![Kör cmdlet i PowerShell](../media/DLP-create-test-tune-PowerShell.png)

När du har aktiverat DLP-principen bör du köra några egna slutliga tester för att se till att de förväntade principåtgärderna inträffar. Om du försöker testa saker som kreditkortsdata finns det webbplatser online med information om hur du genererar exempelkreditkort eller annan personlig information som skickar checkums och utlöser dina policyer.

Principer som tillåter användar åsidosättningar presenterar det alternativet för användaren som en del av princip tipset.

![Principtips som gör att användaren kan åsidosätta](../media/DLP-create-test-tune-override-option.png)

Principer som begränsar innehållet kommer att presentera varningen för användaren som en del av principtipset och förhindra att de skickar e-postmeddelandet.

![Principtips om att innehållet är begränsat](../media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a>Sammanfattning

Principer för förebyggande av dataförlust är användbara för organisationer av alla slag. Att testa vissa DLP-principer är en lågriskövning på grund av den kontroll du har över saker som principtips, åsidosättningar av slutanvändare och incidentrapporter. Du kan tyst testa vissa DLP-principer för att se vilken typ av överträdelser som redan förekommer i din organisation och sedan skapa principer med låga falska positiva priser, utbilda dina användare om vad som är tillåtet och inte tillåtet och sedan distribuera dina DLP-principer till organisationen.