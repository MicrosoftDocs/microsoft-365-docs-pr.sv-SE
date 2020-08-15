---
title: Översikt över supporten som upphör för SharePoint Server 2007
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 01/28/2019
audience: ITPro
ms.topic: conceptual
f1.keywords:
- CSH
ms.custom:
- vsemail
- MS_WSS_DirectoryManagement
- MS_WSS_ConfigEmail
- globalemailconfig
- configssc
- AppDefToBDC
- seo-marvel-apr2020
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- OFU120
- SPS150
- OSU140
- WSU120
- OSR120
- SPO160
- PJW120
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: ba124775-d5c0-4d68-b88d-8458ad4c3717
description: Den 10 oktober 2017 stöd för SharePoint Server 2007. I den här artikeln lär du dig mer om alternativen för uppgradering, migrering och support.
ms.openlocfilehash: c89f150618150e352de476e0a0982fd2d98348e2
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694874"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>Översikt över supporten som upphör för SharePoint Server 2007

*Den här artikeln gäller både Microsoft 365 Enterprise och Office 365 Enterprise.*

Den **10 oktober 2017**nådde Microsoft Office SharePoint Server 2007 Supportens slut. Om du inte har börjat migrera från SharePoint Server 2007 till Microsoft 365 eller en nyare version av SharePoint Server lokalt är det dags att börja planera. Den här artikeln visar resurser för att hjälpa personer att migrera data till SharePoint Online eller uppgradera din SharePoint-Server lokalt. 
  
## <a name="what-does-end-of-support-mean"></a>Vad innebär slut på support?

SharePoint Server, till exempel nästan alla Microsoft-produkter, har en support livs cykel under vilken Microsoft tillhandahåller nya funktioner, korrigeringar, säkerhets korrigeringar och så vidare. Denna livs cykel räcker normalt i 10 år från datumet för produktens första utgivning och slutet av den här livs cykeln kallas produkt Supportens slut. I slutet av supporten tillhandahåller Microsoft inte längre:
  
- Teknisk support för problem som kan uppstå;
    
- Program korrigeringar för problem som upptäcks och som kan påverka serverns stabilitet och användbarhet.
    
- Säkerhets korrigeringar för säkerhets problem som upptäcks och som kan göra servern sårbar för säkerhets brott; och 
    
- Tids zons uppdateringar.
    
Även om din SharePoint Server 2007-server fungerar efter den 10 oktober 2017 kommer inga ytterligare uppdateringar, korrigeringar eller korrigeringar att levereras för produkten (inklusive säkerhets korrigeringar/korrigeringar) och Microsoft Support kommer att helt och hållet flytta sin support till nyare versioner av produkten. Eftersom din installation inte längre stöds eller görs efter support, kan du uppgradera produkten eller migrera viktiga data.
  
> [!TIP]
> Om du inte redan har planerat för uppgradering eller migrering kan du läsa: [alternativ för migrering av SharePoint 2007](sharepoint-2007-migration-options.md)för att ta reda på några exempel på var du ska starta. Du kan också söka efter [Microsoft-partners](https://go.microsoft.com/fwlink/?linkid=841249) som kan hjälpa dig med uppgradering eller Microsoft 365-migrering (eller båda). 
  
Mer information om Office 2007-servrar som når slutet av support finns i [resurser som hjälper dig att uppgradera från Office 2007-servrar och-klienter](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>Vilka alternativ har jag?

Ditt första stopp ska vara [Product Lifecycle-webbplatsen](https://go.microsoft.com/fwlink/?linkid=843148). Om du har en lokal Microsoft-produkt som är åldrande bör du kontrol lera slutdatumet för supporten så att ett år eller så länge det behövs – du kan schemalägga uppgradering eller migreringar. När du väljer nästa steg kan det vara bra att tänka på vad som skulle vara tillräckligt, bättre och bäst när det gäller produkt funktioner. Här är ett exempel:
  
|**Bra**|**Förbättrat**|**Metod**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||SharePoint-hybrid  <br/> |SharePoint Server 2016  <br/> |
| | |SharePoint-hybrid  <br/> |
   
Kom ihåg att om du väljer alternativ på kortets slut (tillräckligt god) måste du börja planera för uppgraderingen väldigt snart när migreringen från SharePoint Server 2007 är klar. (slut på support för SharePoint Server 2007 är den 10 oktober 2017. Observera att dessa datum kan ändras och kontrol lera [produktens livs cykel webbplats](https://support.microsoft.com/lifecycle).)
  
## <a name="where-can-i-go-next"></a>Var kan jag gå vidare?

SharePoint Server kan installeras lokalt på dina egna servrar, eller så kan du använda SharePoint Online, som är en online-tjänst som är en del av Microsoft 365. Du kan välja att:
  
- Migrera till SharePoint Online
    
- Uppgradera SharePoint Server lokalt
    
- Gör båda ovanstående
    
- Implementera en [SharePoint-hybrid](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx) lösning 
    
Observera dolda kostnader som är kopplade till att underhålla en Server grupp som skickas, upprätthåller eller migrerar anpassningar samt att uppgradera den maskin vara som SharePoint Server är beroende av. Att ha en lokal SharePoint Server-grupp som kan belönas om det är nödvändigt; Om du kör Server gruppen på äldre SharePoint-servrar utan omfattande anpassning kan du till och med använda en planerad migrering till SharePoint Online.
  
> [!IMPORTANT]
> Det finns ett annat alternativ om innehållet i SharePoint 2007 inte används ofta. Vissa SharePoint-administratörer kan välja att skapa en Microsoft 365-prenumeration, konfigurera en helt ny SharePoint Online-webbplats och sedan klippa bort den från SharePoint 2007, utan bara de viktigaste dokumenten till de nya SharePoint Online-webbplatserna. Därifrån kan data tömmas från SharePoint 2007-webbplatsen till Arkiv. Tänk på hur användarna kan arbeta med data i din SharePoint 2007-installation. Det kan finnas kreativa sätt att lösa det här problemet! 
  
|**SharePoint Online (SPO)**|**SharePoint Server lokalt**|
|:-----|:-----|
|Hög kostnad i tid (planering/körning/verifiering)  <br/> |Hög kostnad i tid (planering/körning/verifiering)  <br/> |
|Lägre kostnad i pengar (inga maskin varu köp)  <br/> |Högre kostnad i pengar (maskin vara + utvecklare/administratörer)  <br/> |
|Engångs kostnad i migration  <br/> |Upprepad engångs kostnad per framtida migrering  <br/> |
|Låga totala kostnader för ägande/underhåll  <br/> |Hög total kostnad för ägande/underhåll  <br/> |
   
När du migrerar till Microsoft 365 kommer flytten till en kraftig kostnad att hållas högre medan du strukturerar data och bestämmer vad som ska tas till molnet och vad du ska lämna. Men uppgraderingar kommer att vara automatiska från den punkten, du behöver inte längre hantera maskinvaru-och program varu uppdateringar, och tiden för Server gruppen kommer att säkerhets kopie ras av Microsoft Service Agreement ([SLA](https://go.microsoft.com/fwlink/?linkid=843153)).
  
### <a name="migrate-to-sharepoint-online"></a>Migrera till SharePoint Online

Kontrol lera att SharePoint Online innehåller alla funktioner du behöver genom att granska den associerade tjänst beskrivningen. Se [Microsoft 365 och Office 365 service beskrivningar](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library).
  
Det finns inget direkt sätt att migrera från SharePoint 2007 till SharePoint Online. din flytt till SharePoint Online utförs manuellt. Om du uppgraderar till SharePoint Server 2013 eller SharePoint Server 2016 kan du även använda SharePoint Migration API (för att migrera information till OneDrive för företag).
  
|**Online Pro**|**Online-con**|
|:-----|:-----|
|Microsoft tillhandahåller SPO maskin vara och all maskin varu administration.  <br/> |Tillgängliga funktioner kan skilja sig mellan SharePoint Server lokalt och SPO.  <br/> |
|Du är global administratör för din prenumeration och kan tilldela administratörer till SPO webbplatser.  <br/> |Vissa åtgärder som är tillgängliga för en server grupps administratör i SharePoint Server lokalt finns inte (eller är inte nödvändiga) ingår i administratörs rollen för SharePoint i Microsoft 365.  <br/> |
|Microsoft tillämpar korrigeringsfiler, korrigeringar och uppdateringar för underliggande maskin vara och program vara.  <br/> |Eftersom det inte finns någon åtkomst till underliggande fil system i tjänsten begränsas vissa anpassningar.  <br/> |
|Microsoft publicerar [service nivå avtal](https://go.microsoft.com/fwlink/?linkid=843153) och går snabbt för att lösa service nivå problem.  <br/> |Säkerhets kopiering och återställning och andra återställnings alternativ automatiseras av tjänsten i SharePoint Online-säkerhets kopieringarna skrivs över om de inte används.  <br/> |
|Säkerhets testning och Server prestanda justering utförs kontinuerligt i tjänsten av Microsoft.  <br/> |Ändringar i användar gränssnittet och andra SharePoint-funktioner installeras av tjänsten och kan behöva sättas på eller av.  <br/> |
|Microsoft 365 uppfyller många bransch standarder: [Microsoft Compliance](https://go.microsoft.com/fwlink/?linkid=843165)-support.  <br/> |[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) hjälp för migrering är begränsad.  <br/> Mycket av uppgraderingen kommer att vara manuell eller via SPO Migration API som beskrivs i Översikt över [SharePoint Online och OneDrive migration](https://go.microsoft.com/fwlink/?linkid=843184).  <br/> |
|Varken Microsofts support tekniker eller anställda i data centret har obegränsad administratörs åtkomst till din prenumeration.  <br/> |Det kan finnas extra kostnader om maskin varu infrastrukturen måste uppgraderas för att stödja den nyare versionen av SharePoint, eller om en sekundär server grupp krävs för uppgradering.  <br/> |
|Partners kan hjälpa till med att migrera dina data till SharePoint Online med engångs arbetet.  <br/> ||
|Online-produkter uppdateras automatiskt i tjänsten, vilket innebär att om funktionerna kan bli gamla finns det inget slut på supporten.  <br/> ||
   
Om du har bestämt dig för att skapa en ny Microsoft 365-webbplats och manuellt migrera data till den, kan du titta på dina [Microsoft 365-alternativ](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Uppgradera SharePoint Server lokalt

Det finns inte något sätt för att hoppa över versioner i SharePoint-uppgraderingar, minst den version av SharePoint Server 2016. Det innebär att uppgraderingarna går seriellt:
  
- SharePoint 2007 \> SharePoint server 2010 \> sharepoint Server 2013 \> SharePoint Server 2016
   
Om du vill ta hela vägen från SharePoint 2007 till SharePoint Server 2016 beräknas en betydande tid och inkluderar en kostnad i termer av uppgraderad maskin vara (Tänk på att SQL-servrar måste också vara uppgraderade), program vara och administration. Anpassningar måste uppgraderas eller överlåtas, beroende på funktionens viktighets grad.
  
> [!NOTE]
> Det är möjligt att behålla ditt slut på SharePoint 2007-servergrupper, installera en SharePoint Server 2016-servergrupp på ny maskin vara (så att de enskilda Server grupperna körs sida vid sida) och sedan planera och utföra en manuell migrering av innehåll (för att till exempel Ladda ner och överföra innehåll). Observera vissa fall GRO par av manuella flyttningar (till exempel flyttningar av dokument som ersätter det senast ändrade kontot med aliaset för det konto som gör den manuella flytten) och det arbete som måste göras i förväg (till exempel återskapa webbplatser, under webbplatser, behörigheter och list strukturer). Det här är det dags att överväga vilka data du kan flytta till lagring eller inte längre behöver, en åtgärd som kan minska påverkan på migreringen.
  
Du kan antingen rensa miljön innan du uppgraderar. Var säker på att den befintliga Server gruppen fungerar innan du uppgraderar och (för se) innan du inaktiverar! 
  
Kom ihåg att granska de **uppgraderings vägar som stöds och inte stöds**: 
  
- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Om du har **anpassningar**är det viktigt att du planerar uppgraderingen för varje steg i sökvägen: 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Lokal Pro**|**Lokal con**|
|:-----|:-----|
|Fullständig kontroll över alla aspekter av SharePoint-servergruppen från server maskin varan.  <br/> |Alla raster och korrigeringar är företagets ansvar (kan hantera Microsoft support om din produkt saknar stöd):  <br/> |
|Fullständig uppsättning funktioner i SharePoint Server lokalt med alternativet att ansluta den lokala server gruppen till en SharePoint Online-prenumeration via hybrid.  <br/> |Uppgradering, korrigeringsfiler, säkerhets korrigeringar och alla underhåll av SharePoint Server som hanteras lokalt.  <br/> |
|Fullständig åtkomst för större anpassning.  <br/> |[Microsoft-efterföljandekrav](https://go.microsoft.com/fwlink/?linkid=843165) måste konfigureras manuellt lokalt.  <br/> |
|Säkerhets testning och Server prestanda justering som utförs på dina lokaler (är under din kontroll).  <br/> |Microsoft 365 kan göra funktioner tillgängliga för SharePoint Online som inte fungerar tillsammans med SharePoint Server lokalt  <br/> |
|Partners kan hjälpa till att migrera data till nästa version av SharePoint Server (och senare).  <br/> |Dina SharePoint Server-webbplatser använder inte automatiskt [SSL/TLS-](https://go.microsoft.com/fwlink/?linkid=843167) certifikat som visas i SharePoint Online.  <br/> |
|Fullständig kontroll över namn konventioner, säkerhets kopiering och återställning och andra återställnings alternativ i SharePoint Server lokalt.  <br/> |SharePoint Server lokalt är känsligt för produktens livscykler.  <br/> |
   
### <a name="upgrade-resources"></a>Uppgradera resurser

Börja med att veta att du uppfyller maskinvaru-och program varu krav och följ sedan de uppgraderings metoder som stöds.
  
- **Maskinvaru-/program varu krav för**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **Program varu begränsningar och begränsningar för**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **Uppgraderings processen översikt för**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Skapa en SharePoint-hybrid lösning mellan SharePoint Online och lokalt

Om svaret på dina migreringar är någonstans mellan själv kontroll som tillhandahålls av lokala och den lägre ägande kostnaden som erbjuds av SharePoint Online, kan du ansluta SharePoint Server 2013-eller 2016-anläggningar till SharePoint Online, via hybrider. [Läs mer om hybrid lösningar för SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Om du bestämmer dig för att en fjärran sluten SharePoint Server-grupp ska vara till ditt företag kan du bekanta dig med de befintliga typerna av hybrid och hur du konfigurerar anslutningen mellan den lokala SharePoint-servergruppen och Microsoft 365-prenumerationen.
  
| Alternativ | Beskrivning |
|:-----|:-----|
[Microsoft Compliance](https://go.microsoft.com/fwlink/?linkid=843165)-funktioner.  <br/> |[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) hjälp för migrering är begränsad.  <br/> Mycket av uppgraderingen kommer att vara manuell eller via SPO Migration API som beskrivs i Översikt över [SharePoint Online och OneDrive migration](https://go.microsoft.com/fwlink/?linkid=843184).  <br/> |
|Varken Microsofts support tekniker eller anställda i data centret har obegränsad administratörs åtkomst till din prenumeration.  <br/> |Det kan finnas extra kostnader om maskin varu infrastrukturen måste uppgraderas för att stödja den nyare versionen av SharePoint, eller om en sekundär server grupp krävs för uppgradering.  <br/> |
|Partners kan hjälpa till med att migrera dina data till SharePoint Online med engångs arbetet.  <br/> ||
|Online-produkter uppdateras automatiskt i tjänsten, vilket innebär att om funktionerna kan bli gamla finns det inget slut på supporten.  <br/> ||
   
Om du har bestämt dig för att skapa en ny Microsoft 365-webbplats och manuellt migrera data till den, kan du titta på dina [Microsoft 365-alternativ](https://www.microsoft.com/microsoft-365/).
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Uppgradera SharePoint Server lokalt

Det finns inte något sätt för att hoppa över versioner i SharePoint-uppgraderingar, minst den version av SharePoint Server 2016. Det innebär att uppgraderingarna går seriellt:
  
- SharePoint 2007 \> SharePoint server 2010 \> sharepoint Server 2013 \> SharePoint Server 2016
   
Om du vill ta hela vägen från SharePoint 2007 till SharePoint Server 2016 beräknas en betydande tid och inkluderar en kostnad i termer av uppgraderad maskin vara (Tänk på att SQL-servrar måste också vara uppgraderade), program vara och administration. Anpassningar måste uppgraderas eller överlåtas, beroende på funktionens viktighets grad.
  
> [!NOTE]
> Det är möjligt att behålla ditt slut på SharePoint 2007-servergrupper, installera en SharePoint Server 2016-servergrupp på ny maskin vara (så att de enskilda Server grupperna körs sida vid sida) och sedan planera och utföra en manuell migrering av innehåll (för att till exempel Ladda ner och överföra innehåll). Observera vissa fall GRO par av manuella flyttningar (till exempel flyttningar av dokument som ersätter det senast ändrade kontot med aliaset för det konto som gör den manuella flytten) och det arbete som måste göras i förväg (till exempel återskapa webbplatser, under webbplatser, behörigheter och list strukturer). Det här är det dags att överväga vilka data du kan flytta till lagring eller inte längre behöver, en åtgärd som kan minska påverkan på migreringen.
  
Du kan antingen rensa miljön innan du uppgraderar. Var säker på att den befintliga Server gruppen fungerar innan du uppgraderar och (för se) innan du inaktiverar! 
  
Kom ihåg att granska de **uppgraderings vägar som stöds och inte stöds**: 
  
- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)
    
Om du har **anpassningar**är det viktigt att du planerar uppgraderingen för varje steg i sökvägen: 
  
- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)
    
- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)
    
- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)
    
|**Lokal Pro**|**Lokal con**|
|:-----|:-----|
|Fullständig kontroll över alla aspekter av SharePoint-servergruppen från server maskin varan.  <br/> |Alla raster och korrigeringar är företagets ansvar (kan hantera Microsoft support om din produkt saknar stöd):  <br/> |
|Fullständig uppsättning funktioner i SharePoint Server lokalt med alternativet att ansluta den lokala server gruppen till en SharePoint Online-prenumeration via hybrid.  <br/> |Uppgradering, korrigeringsfiler, säkerhets korrigeringar och alla underhåll av SharePoint Server som hanteras lokalt.  <br/> |
|Fullständig åtkomst för större anpassning.  <br/> |[Microsoft-efterföljandekrav](https://go.microsoft.com/fwlink/?linkid=843165) måste konfigureras manuellt lokalt.  <br/> |
|Säkerhets testning och Server prestanda justering som utförs på dina lokaler (är under din kontroll).  <br/> |Microsoft 365 kan göra funktioner tillgängliga för SharePoint Online som inte fungerar tillsammans med SharePoint Server lokalt  <br/> |
|Partners kan hjälpa till att migrera data till nästa version av SharePoint Server (och senare).  <br/> |Dina SharePoint Server-webbplatser använder inte automatiskt [SSL/TLS-](https://go.microsoft.com/fwlink/?linkid=843167) certifikat som visas i SharePoint Online.  <br/> |
|Fullständig kontroll över namn konventioner, säkerhets kopiering och återställning och andra återställnings alternativ i SharePoint Server lokalt.  <br/> |SharePoint Server lokalt är känsligt för produktens livscykler.  <br/> |
   
### <a name="upgrade-resources"></a>Uppgradera resurser

Börja med att veta att du uppfyller maskinvaru-och program varu krav och följ sedan de uppgraderings metoder som stöds.
  
- **Maskinvaru-/program varu krav för**: 
    
    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)
    
- **Program varu begränsningar och begränsningar för**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)
    
- **Uppgraderings processen översikt för**: 
    
    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Skapa en SharePoint-hybrid lösning mellan SharePoint Online och lokalt

Om svaret på dina migreringar är någonstans mellan själv kontroll som tillhandahålls av lokala och den lägre ägande kostnaden som erbjuds av SharePoint Online, kan du ansluta SharePoint Server 2013-eller 2016-anläggningar till SharePoint Online, via hybrider. [Läs mer om hybrid lösningar för SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Om du bestämmer dig för att en fjärran sluten SharePoint Server-grupp ska vara till ditt företag kan du bekanta dig med de befintliga typerna av hybrid och hur du konfigurerar anslutningen mellan den lokala SharePoint-servergruppen och Microsoft 365-prenumerationen.
  
Ett bra sätt att se hur det här fungerar är genom att skapa en Microsoft 365 dev/test-miljö, som du kan ställa in med [testlabb guider](m365-enterprise-test-lab-guides.md). När du har en utvärderings version eller Microsoft 365-prenumeration är du på väg att skapa webbplats samlingar, webbplatser och dokument bibliotek i SharePoint Online som du kan migrera data från (antingen manuellt, med hjälp av migrerings-API: t), eller om du vill migrera mitt webbplats innehåll till OneDrive för företag – via Hybrid guiden).
  
> [!NOTE]
> Kom ihåg att SharePoint 2007-gruppen måste uppgraderas lokalt, till antingen SharePoint Server 2013 eller SharePoint Server 2016 för att använda hybrid alternativet 
  
## <a name="related-topics"></a>Relaterade ämnen

[Felsöka och återuppta uppgraderingen (Office SharePoint Server 2007)](https://go.microsoft.com/fwlink/?linkid=843192)
  
[Felsöka uppgraderings problem (SharePoint Server 2010)](https://go.microsoft.com/fwlink/?linkid=843194)
  
[Felsöka problem med databas uppgradering i SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)
  
[Sök efter Microsoft-partners för att få hjälp med uppgraderingen](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Resurser som hjälper dig att uppgradera från Office 2007-servrar och-klienter](upgrade-from-office-2007-servers-and-products.md)
  

