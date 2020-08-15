---
title: Uppgraderings alternativ för SharePoint 2007 för att överväga
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPS150
- OSU140
- SPO160
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: 66325a43-5816-4f8e-81ba-c11b71345b7c
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: Den här artikeln innehåller information för användare som använder SharePoint Server 2007 för att hjälpa dem planera sin uppgradering.
ms.openlocfilehash: 3e37a01f1a2d387cda6723a8df1f73734fa3ba9d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694960"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>Uppgraderings alternativ för SharePoint 2007 för att överväga

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Microsoft SharePoint 2007 och SharePoint Server 2007 har nått Supportens slut. Det är dags att uppgradera! Den här artikeln innehåller information om alternativen för migrering.
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>Vanliga uppgraderings strategier för SharePoint

Det finns flera metoder för att uppgradera en SharePoint Server-miljö. Om du har en Microsoft Office SharePoint Server 2007-servergrupp finns här några exempel på uppgraderings metoderna:
  
- Databas koppling
    
- Sida vid sida-uppgradering
    
- På-plats-uppgradering
    
- Hybrid uppgradering (på plats med frånkopplade databaser/separera databas koppling)
    
- SharePoint-hybrider (Anslut online till lokala SharePoint)
    
- Manuellt flytta data mellan webbplats samlingar eller bibliotek
    
- FastTrack guiden Uppgradera till Microsoft 365 ([SharePoint Online Deployment Advisor](https://aka.ms/spoguidance))
    
- Migrerings-API till SharePoint Online (SPO) i Microsoft 365
    
Vad passar bäst för dig?
  
Dina kunskaper om din server grupp och att den används av är en Tactical styrka när det gäller att uppgradera. På vilket sätt folk använder SharePoint-gruppen kan du välja bland alternativen.
  
> [!TIP]
> Microsoft Office SharePoint Server 2007 har också en gradvis uppgradering som inte täcks här. För att se en lista över stegvisa uppgraderings artiklar, se [SharePoint Server 2007-översikten med support](sharepoint-2007-end-of-support.md). 
  
Kom ihåg att kontrol lera [produkt livs cykeln](https://support.microsoft.com/lifecycle/search) och system kraven för den version av SharePoint som du uppgraderar till. Det här kan du vara medveten om när nästa uppgradering blir nödvändig (om du till exempel pausar på en äldre produkt som SharePoint Server 2010 för att planera för fler uppgraderingar, se till att du vet dess slut punkt för support datumet) och att du är säker på att du har maskin vara som stöder din plan. 
  
Om du planerar att överföra vissa eller alla av dina SharePoint-webbplatser till Microsoft 365 i molnet, är det dags att skapa ett bok märke för en länk till [microsoft 365-och Office 365-tjänste beskrivningarna](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library). Du behöver tjänste beskrivningarna för att lära dig mer om funktionerna i SharePoint Online och hur de kan skilja sig från lokala SharePoint-servrar. Uppgradera funktions dugliga Microsoft Office SharePoint Server 2007-grupper. Om installationen har skadade webbplatser kan du åtgärda dem innan du uppgraderar.
  
## <a name="a-note-about-managing-risk"></a>En kommentar om att hantera risker

Metoderna "sida vid sida" är viktiga i det program som gäller för uppgradering. När du uppgraderar sida vid sida upprätthåller du din Microsoft Office SharePoint Server 2007-grupp, men skapar en Server grupp nästa version (SharePoint Server 2010) för ny maskin vara. Det gör det på tre sätt:
  
1. Du kan säkerhetskopiera dina Microsoft Office SharePoint Server 2007-databaser och uppgradera dem separat genom att använda databas koppling.
    
2. Om du tar reda på att det bara finns ett litet antal viktiga dokument bibliotek och annan information som används i Microsoft Office SharePoint Server 2007-gruppen kan du välja att manuellt flytta data från Microsoft Office SharePoint Server 2007 till SharePoint Server 2010, eller bara ta vissa webbplatser och webbplatser till nästa version (vilket gör jobbet enklare).
    
3. Det mindre du gör i Microsoft Office SharePoint Server 2007-servergruppen, direkt, det säkrare data som server gruppen innehåller när du uppgraderar.
    
Metoder som uppgradering på plats fungerar direkt i Microsoft Office SharePoint Server 2007-gruppen, vilket ger dig färre enkla alternativ för att överge en sökväg och börja igen med din pristine-miljö. Så mycket som möjligt kan du bygga upp säkerhets åtgärder (som att skapa och testa säkerhets kopior av den ursprungliga miljön). Om din Microsoft Office SharePoint Server 2007-servergrupp är virtuell och en dubblett för säkerhets kopiering och återställning är det bara att säkerhetskopiera och återställa de senaste databaserna före tjänste fönstret för uppgraderingen. Om du vet att du kan återställa databas säkerhets kopior får du inte bara en Failsafe, det kan ge dig sinnesro.
  
> [!TIP]
> Metod tips dokument för uppgradering finns för [Microsoft Office SharePoint server 2007](https://technet.microsoft.com/library/cc261992%28v=office.12%29.aspx), [SharePoint Server 2010](https://technet.microsoft.com/library/cc261992%28v=office.14%29.aspx), [SharePoint server 2013](https://technet.microsoft.com/library/cc261992%28v=office.15%29.aspx)och [SharePoint Server 2016](https://technet.microsoft.com/library/cc261992%28v=office.16%29.aspx). Du kan också söka efter [Microsoft-partners](https://partnercenter.microsoft.com/pcv/search) som har erfarenhet av uppgraderingar eller Microsoft 365-migreringar. 
  
## <a name="make-your-plan"></a>Gör ditt abonnemang

Om du behöver uppgradera måste du ha en plan och en-storlek som inte passar alla i de här fallen. Ditt abonnemang kan vara så enkelt som "skapa en Microsoft 365-prenumeration med SharePoint Online, registrera en domän och omdirigera dem till sina filer där. Och det kanske inte är det. Det beslutet är ditt och det är det du och dina användare verkligen behöver.
  
> [!NOTE]
> Det är riskabelt att köras på program vara vars livs cykel är slut. Produkter som saknar stöd åtgärdas inte längre när du hittar problem. Det innebär också att om nya säkerhetshot uppstår finns inga säkerhets korrigeringar eller korrigeringar eftersom slut punkts produkterna inte längre stöds. Undvik det här! 
  
### <a name="first-know-your-farm"></a>Börja med att ta reda på Server gruppen

När du uppgraderar bör besluts fattandet baseras på vad din grupp gör för din organisation. Vad behöver du göra? Vad är dess roll? Varje server grupp i ditt företag kan ha en annan roll. Vissa av dina SharePoint-servergrupper kan vara  *kritiska*  , vissa kan vara filarkiv--där det är säkert. Om din server grupp ofta fyller många roller samtidigt kan du behöva veta vilka webbplats samlingar, webb sidor och till och med dokument bibliotek som gör det. Att analysera dina data på den här nivån kan verka som en hel del arbete, men det sparar tid och ansträngning för att hantera din domän innan du uppgraderar eller migrerar. När du känner till alla rörliga delar och de viktigaste bitarna vet du också vad du har utökat och kan lämna. Denna kunskap kommer bara att under rättas. 
  
Vad innebär användarna att det är viktigast för din SharePoint Server-servergrupp?
  
- Inbyggda SharePoint-funktioner
    
- Den stora data mängden (till exempel en arkivering av filer)
    
- Tillgänglighet
    
- Kritiska appar, webb delar eller dokument i Server gruppen (uppdrags kritisk Server)
    
- Överensstämmelse standarden uppfylls
    
- Anpassningar
    
Om du kör något som är väsentligt för ditt företag från SharePoint-servergruppen fungerar det som en stor katalog med viktiga data om klient tjänst krav, du kan ange en markering bredvid "kritiska appar", men också "tillgänglighet" – det vill säga att ditt företag påverkas om du inte kan använda SharePoint på ett tag. På samma sätt kan du kontrol lera ' anpassningar ' eftersom de kritiska tjänster som gruppens erbjudande är baserade på anpassade koder, webbplats definitioner eller ett antal anpassningar som fungerar tillsammans.
  
Om SharePoint uppfyller de här behoven utan att behöva göra något utanför användning av vad som är inbyggt i program varan och du uppdaterar det och utför normalt administration och underhåll, kan du ha valt "inbyggt SharePoint" – Detta kan vara din orsak till att du sitter i en äldre version av SharePoint. Med andra ord gör det allt du behöver, och du behöver inte uppgradera förrän nu, på Microsoft Office SharePoint Server 2007-supporten.
  
När du punkt lista de här sakerna skapar du villkor för uppgraderingen. Med andra ord måste eventuell uppgradering uppfylla detta fält. Det gör att du kan utesluta metoder som inte passar dina behov.
  
### <a name="a-simple-sample-plan"></a>Ett enkelt exempel på abonnemang

Det kan behöva bli mer enhälligt med ledarskap och andra administratörer på den sökväg som din SharePoint-uppgradering kommer att vidta. SharePoint Server-administratörer samarbetar ofta med Microsoft SQL Server-administratörer, fungerar med nätverks-och säkerhets team och mycket mer. Om det finns många intressenter kan du behöva bygga ett avtal för, eller justera, din uppgradering och migrering. Om du till exempel migrerar data så att en del av ditt företag använder SharePoint Online i Microsoft 365 måste det troligt vis bli prestanda justering eller testning i ditt nätverk. Berörda grupper bör vara informerade när som helst.
  
I det enkla exemplet visar jag en SharePoint-administratörs förslag och visar sedan ett abonnemang som alla intressenter har kommit överens om. För tydlighet, dokumenterar du dina avtal och beslut.
  
Planen inleds efter en djupgående analys av en Server grupp och försöker identifiera Server gruppens roll, målar Poäng och annan viktig information som leder till att vissa uppgraderings alternativ begränsas. Därefter görs ett uppgraderings förslag av SharePoint-administratör och intressenterna samtycker till en åtgärds plan.
  
Min viktigaste "punkt lista:
  
- Tillgänglighet, inbyggda funktioner för SharePoint och efterlevnadsprinciper.
    
- De flesta data finns på tre webbplats samlingar, med en Mötes arbets yta som används av en dev-grupp, särskilt viktig och mest omfattande användning i flera olika tids zoner världen över.
    
- Det finns Seventeen andra webbplatser som används ofta.
    
- Två dokument bibliotek (Mötes arbets ytor och dokument på rot webbplats samlingen) är de största (över 8000 dokument var och en). Det finns ett stort antal arkiverade dokument och listor med bifogade filer i kalkyl blad.
    
- Det finns fjorton listor över bibliotek med känsliga data som måste hållas i överensstämmelse.
    
- Vi måste ha möjlighet att göra undantag och e-identifiering var vi än är.
    
- Vissa av dessa uppgifter måste vara lokalt, på grund av regler för informations säkerhet.
    
 **Mina alternativ för uppgradering och migrering:**
  
| Ja | Nej |
|:-----|:-----|
|Uppgradera databaser med databas koppling  <br/> |På-plats-uppgradering  <br/> |
|Uppgradera med grupper sida vid sida  <br/> |Hybrid uppgradering  <br/> |
|Migrerings-API till SPO i Microsoft 365 (för personliga webbplats data)  <br/> |SharePoint-hybrid (behövs ännu)  <br/> |
|Vissa manuella datamigreringar till SharePoint Online för viktiga data  <br/> |FastTrack guiden Uppgradera till Microsoft 365  <br/> |
   
 **Mitt föreslagna abonnemang:**
  
Uppgradera lokalt med olika versioner av SharePoint sida vid sida, så att vi kan uppgradera databaserna först. Gå från SharePoint 2007 till SharePoint 2010. Administratörer och utvecklare testar den resulterande Server gruppen. Användare testar den resulterande Server gruppen. Åtgärda eventuella stopp problem under tiden. Nästa gång du uppgraderar till 2013 SharePoint 2010-databaser. Tävlingar. Användar test/pilot. Åtgärda eventuella stopp problem under tiden.
  
- Överväg om en extern sökning med SPO uppfyller dina behov.
    
- Överväg [FastTrack hjälp](https://fasttrack.microsoft.com) om du vill uppgradera till SharePoint Online härifrån. 
    
- Avgöra om en webbplats samling kan avlastas till en Microsoft 365-prenumeration. (Microsoft 365 uppfyller många [krav på efterlevnad](https://technet.microsoft.com/library/office-365-compliance.aspx). Microsoft 365 har en [eDiscovery](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) och kan göra [undantag](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) genom efterlevnaden.) 
    
I annat fall fortsätter du med en uppgradering sida vid sida till SharePoint Server 2016.
  
> [!NOTE]
> Mellan rekommendationer gjorda av administratörer som planerar uppgraderingen och den faktiska processen är de konversationer som sker med andra intressenter där uppgraderingen är. Till exempel, ekonomi kraft administratörer att ändra sina planer. Det slutgiltiga beslutet är att du ska dokumentera vad det överenskomna abonnemanget är, gå vidare. Det kan se ut ungefär så här: 
  
 **Mitt åtgärds abonnemang:**
  
Lokalt använder vi en virtuell miljö för att bygga SharePoint Server 2010 och 2013. SharePoint Server 2016 skapas på ny maskin vara som uppfyller system kraven för 2016. Vi kommer att göra databas bilagor för att uppgradera databaser från SharePoint 2007 till alla versioner mellan den och SharePoint Server 2016. Grundläggande anpassningar återskapas för och testas i SharePoint Server 2016-miljön just nu, om inhemska funktioner inte redan uppfyller våra behov. Om vi lyckas har vi en lokal server grupp för ny maskin vara med uppgraderade databaser och färre anpassningar. Vi kopplar de uppgraderade innehålls databaserna till nya webbplats samlingar i SharePoint Server 2013, test, användar test/pilot och gör sedan en DNS-skärning till den nya SharePoint Server 2016-miljön för Live-användning.
  
- Vi kommer inte att betrakta en federerad hybrid mellan SharePoint Server 2016 och SharePoint online just nu.
    
- En uppskattad 35% av våra webbplatser kan omvandlas till nya SPO-webbplatser med alternativa-domäner eller till sist blir OneDrive för företag-lagring. Leta efter andra möjligheter att konvertera webbplatser eller dirigera nya webbplatser till SPO.
    
- En del av den här delen av migreringen är manuell, genom att dra och släppa till personliga webbplatser för OneDrive för företag och vissa av migration API.
    
Mer detaljerade anvisningar eller ett antal länkar till specifika uppgraderings anvisningar bör följa en plan. MOSS 2007-datorn ska inte avaktiveras och virtuella miljöer bör bibehållas för jämförelsen; uppgraderingen kommer att slutföras när användare omdirigeras till SharePoint Server 2016.
  
Ofta är huvud faktorer att välja en metod är den totala kostnaden för uppgraderingen och kostnaden i tiden (du får mer information om detta i artikeln om artikel i SharePoint migrations översikt). Genom att planera i förväg kan du emellertid ställa in förväntningarna och välja hur bra de ska se ut.
  
## <a name="related-links"></a>Relaterade länkar

[Resurser som hjälper dig att uppgradera från Office 2007-servrar och-klienter](upgrade-from-office-2007-servers-and-products.md)
  
[Microsoft Lifecycle-policy och livscykel sökning](https://support.microsoft.com/lifecycle)
  
[Sök efter Microsoft-partners som kan hjälpa dig med uppgradering eller migrering](https://partnercenter.microsoft.com/pcv/search)
  

