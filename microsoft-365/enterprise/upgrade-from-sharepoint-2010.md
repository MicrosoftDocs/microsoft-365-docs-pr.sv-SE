---
title: Uppgraderar från SharePoint 2010
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 04/13/2020
audience: ITPro
ms.topic: conceptual
ms.prod: office-online-server
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- WSU140
- OSU140
ms.assetid: 985a357f-6db7-401f-bf7a-1bafdf1f312c
f1.keywords:
- NOCSH
description: Hitta information och resurser att uppgradera från SharePoint 2010 och SharePoint Server 2010 som support för båda ändarna den 13 oktober 2020.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 88970c83f2497f029635cb987b6b613ea662dc07
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948026"
---
# <a name="upgrading-from-sharepoint-2010"></a>Uppgraderar från SharePoint 2010

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Microsoft SharePoint 2010 och SharePoint Server 2010 når supporten den **13 April 2021**. Den här artikeln visar hur du kan migrera dina befintliga SharePoint Server 2010-data till SharePoint Online i Microsoft 365 eller uppgradera din lokala SharePoint Server 2010-miljö.

## <a name="what-is-end-of-support"></a>Vad är support slut?

När SharePoint Server 2010 och SharePoint Foundation 2010-programmet når slutet av dess support livs cykel (den tid då Microsoft tillhandahåller nya funktioner, korrigeringar, säkerhets korrigeringar och så vidare), kallas detta program varans "slut på support" eller, ibland, deras "Pension". I slutet av supporten (eller EOS) av en produkt är inget slut eller upphör att fungera; i slutet av program support tillhandahåller Microsoft inte längre:

- Teknisk support för problem som kan uppstå;

- Program korrigeringar för problem som upptäcks och som kan påverka serverns stabilitet och användbarhet.

- Säkerhets korrigeringar för säkerhets problem som upptäcks och som kan göra servern sårbar för säkerhets brott;

- Tids zons uppdateringar.

Det innebär att inga ytterligare uppdateringar, korrigeringar eller korrigeringar kommer att levereras för produkten (inklusive säkerhets korrigeringar/korrigeringar) och Microsoft Support kommer att helt och hållet flytta sin support till nyare versioner. I slutet av stöd för SharePoint Server 2010-metoder bör du utnyttja möjligheter att rensa data som du inte längre behöver innan du uppgraderar produkten och/eller migrerar viktiga data.

> [!NOTE]
> En program varu livs cykel räcker ofta i tio år efter produktens första utgivning. Du kan söka efter [Microsoft Solution providers](https://go.microsoft.com/fwlink/?linkid=841249) som kan hjälpa till med att uppgradera till nästa version av program varan eller med Microsoft 365-migrering (eller båda). Det är viktigt att du är medveten om att du har slut på support datum för kritiska underliggande tekniker, särskilt den version av SQL Server du använder med SharePoint. Se [policy för fast livs cykel](https://support.microsoft.com/help/14085) för att förstå produktens livs cykel.

## <a name="what-are-my-options"></a>Vilka alternativ har jag?

Börja med att kontrol lera datumet då supporten upphör på [produktens livs cykel webbplats](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010). Se sedan till att planera uppgraderings-eller uppflyttnings tiden med information om detta datum. Kom ihåg att produkten  *inte upphör att fungera*  vid det datum som anges och att du kan fortsätta använda den, men eftersom din installation inte längre kommer att korrigeras efter detta datum bör du ha en strategi som gör det enklare att gå över till nästa version av produkten.

Denna matris gör det enklare att rita en kurs när det gäller att migrera produkt funktioner och användar data:

|Slut på support produkt|Bra |Metod|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (lokal)|SharePoint Online|
||SharePoint Server 2013 hybrid med SharePoint Online|SharePoint Server 2016 (lokal)|
|||SharePoint-moln HYBRIDS ökning|

Om du väljer alternativ på den nedre delen av skalan (bra alternativ) måste du börja planera för en annan uppgradering snart när migreringen från SharePoint Server 2010 har slutförts.

Här är de tre vägarna som du kan vidta för att undvika slut på stöd för SharePoint Server 2010.

![SharePoint Server 2010-uppgraderings Sök vägar](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> Slutet av supporten för SharePoint Server 2010 och SharePoint Foundation 2010 har schemalagts för 13 april 2021, *men Observera att du* alltid bör kontrol lera [produktens livscykel webbplats](https://support.microsoft.com/lifecycle) för de senaste datumen.

## <a name="where-should-i-go-next"></a>Var ska jag gå vidare?

SharePoint Server 2013 och SharePoint Foundation 2013 kan installeras lokalt på dina egna servrar. I annat fall kan du använda SharePoint Online, som är en online-tjänst som är en del av Microsoft Microsoft 365. Du kan välja att:

- Migrera till SharePoint Online

- Uppgradera SharePoint Server eller SharePoint Foundation lokalt

- Gör båda ovanstående

- Implementera en [SharePoint-hybrid](https://docs.microsoft.com/sharepoint/hybrid/hybrid) lösning

Observera dolda kostnader som är kopplade till att underhålla en Server grupp som skickas, upprätthåller eller migrerar anpassningar samt att uppgradera den maskin vara som SharePoint Server är beroende av. Om du känner till och har fått ett konto för alla dessa är det enklare att fortsätta att uppgradera lokalt. Om du kör Server gruppen på äldre SharePoint-servrar utan omfattande anpassning kan du till exempel dra nytta av en planerad migrering till SharePoint Online. Det är också möjligt att för den lokala SharePoint Server-miljön kanske du vill lägga till vissa data i SharePoint Online för att minska mängden maskin varu hantering som hindrar all lokal data anslutning. Det kan vara mer ekonomiskt att flytta vissa av dina data till SharePoint Online.

> [!NOTE]
> SharePoint-administratörer kan skapa en Microsoft 365-prenumeration, konfigurera en helt ny SharePoint Online-webbplats och sedan klipps ut från SharePoint Server 2010, utan bara de viktigaste dokumenten till de nya SharePoint Online-webbplatserna. Därifrån kan återstående data vara rensade från SharePoint Server 2010-webbplatsen till lokala arkiv.

|SharePoint Online|SharePoint Server lokalt|
|---|---|
|Hög kostnad i tid (planering/körning/verifiering)|Hög kostnad i tid (planering/körning/verifiering)|
|Lägre kostnad i pengar (inga maskin varu köp)|Högre kostnad i pengar (maskin varu köp)|
|Engångs kostnad i migration|Upprepad engångs kostnad per framtida migrering|
|Låga totala kostnader för ägande/underhåll|Hög total kostnad för ägande/underhåll|

När du migrerar till Microsoft 365 har flytten till en kraftig kostnad i tid med att planera, upp och ned (medan du strukturerar data och bestämmer vad som ska tas till molnet och vad du ska lämna för dig). När dina data har migrerats kommer dock uppgraderingarna automatiskt från det tillfället att se precis som om du inte längre behöver hantera maskinvaru-och program varu uppdateringar och tiden för Server gruppen skyddas av ett Microsoft Service Agreement ([SLA](https://go.microsoft.com/fwlink/?linkid=843153)).

### <a name="migrate-to-sharepoint-online"></a>Migrera till SharePoint Online

Se till att SharePoint online erbjuder alla funktioner du behöver genom att granska [tjänst beskrivningen](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description).

Det är för närvarande inget sätt genom vilket du kan migrera från SharePoint Server 2010 (eller SharePoint Foundation 2010) till SharePoint Online, så mycket av arbetet är manuellt. Det ger dig möjlighet att arkivera och rensa data och webbplatser som inte längre behövs, innan flytten. Du kan arkivera andra data i lagrings utrymmet. Kom ihåg att varken SharePoint Server 2010 eller SharePoint Foundation 2010 upphör att fungera efter Supportens slut, så att administratörer kan få en period under vilken SharePoint fortfarande körs om deras kunder glömmer att flytta en del av sina data.

Om du uppgraderar till SharePoint Server 2013 eller SharePoint Server 2016 och bestämmer dig för att lägga till data i SharePoint Online, kan flytten även omfatta att använda [SharePoint Migration API](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) (för att migrera information till OneDrive för företag).

|Fördel med SharePoint Online|Nackdel med SharePoint Online|
|---|---|
|Microsoft tillhandahåller SPO maskin vara och all maskin varu administration.|Tillgängliga funktioner kan skilja sig mellan SharePoint Server lokalt och SPO.|
|Du är global administratör för din prenumeration och kan tilldela administratörer till SPO webbplatser.|Vissa åtgärder som är tillgängliga för en server grupps administratör i SharePoint Server lokalt finns inte (eller behövs inte) i administratörs rollen för SharePoint i Microsoft 365, men SharePoint-administrationen, webbplats samlingens administration och webbplats ägarskap är lokala för din organisation.|
|Microsoft tillämpar korrigeringsfiler, korrigeringar och uppdateringar för underliggande maskin vara och program vara (inklusive SQL-servrar som körs i SharePoint Online).|Eftersom det inte finns någon åtkomst till underliggande fil system i tjänsten begränsas vissa anpassningar.|
|Microsoft publicerar [service nivå avtal](https://go.microsoft.com/fwlink/?linkid=843153) och går snabbt för att lösa service nivå problem.|Säkerhets kopiering och återställning och andra återställnings alternativ automatiseras av tjänsten i SharePoint Online-säkerhets kopieringarna skrivs över om de inte används.|
|Säkerhets testning och Server prestanda justering utförs kontinuerligt i tjänsten av Microsoft.|Ändringar i användar gränssnittet och andra SharePoint-funktioner installeras av tjänsten och kan behöva sättas på eller av.|
|Microsoft 365 uppfyller många bransch standarder: [Microsoft Compliance](https://go.microsoft.com/fwlink/?linkid=843165)-support.|[FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) hjälp för migrering är begränsad.  <br/> Mycket av uppgraderingen kommer att vara manuell eller via SPO Migration API som beskrivs i Översikt över [SharePoint Online och OneDrive migration](https://go.microsoft.com/fwlink/?linkid=843184).|
|Varken Microsofts support tekniker eller anställda i data centret har obegränsad administratörs åtkomst till din prenumeration.|Det kan finnas extra kostnader om maskin varu infrastrukturen måste uppgraderas för att stödja den nyare versionen av SharePoint, eller om en sekundär server grupp krävs för uppgradering.|
|Lösnings leverantörer kan hjälpa med engångs jobbet att migrera dina data till SharePoint Online.|Alla ändringar av SharePoint Online ligger inte inom din kontroll. Efter migreringen kan det påverka användbarheten tillfälligt.|
|Online-produkter uppdateras automatiskt i tjänsten, vilket innebär att om funktionerna kan bli gamla finns det inget slut på support livs cykeln.|Det finns ett slut på support livs cykeln för SharePoint Server (eller SharePoint Foundation) samt underliggande SQL-servrar.|

Om du har bestämt dig för att skapa en ny Microsoft 365-webbplats och manuellt migrera data till den, kan du titta på dina [Microsoft 365-alternativ](https://www.microsoft.com/microsoft-365/).

### <a name="upgrade-sharepoint-server-on-premises"></a>Uppgradera SharePoint Server lokalt

Från och med den senaste versionen av den lokala SharePoint-produkten (SharePoint Server 2019) måste SharePoint Server-uppgraderingarna vara  *seriellt*, vilket innebär att det inte finns något sätt att uppgradera från sharepoint Server 2010 till sharepoint server 2016 eller till SharePoint 2019 direkt.

Sökväg för seriell uppgradering:

- SharePoint Server 2010 \> SharePoint server 2013 \> sharepoint server 2016

Om du väljer att följa hela sökvägen från SharePoint 2010 till SharePoint Server 2016 tar detta tid och planering. Uppgraderingar innebär en kostnad i termer för uppgraderad maskin vara (Observera att SQL-servrar måste också uppgraderas), program vara och administration. Dessutom kan anpassningar behöva uppgraderas, eller till och med överges. Se till att du samlar in anteckningar om alla viktiga anpassningar innan du uppgraderar SharePoint server-servergruppen.

> [!NOTE]
> Du kan behålla ditt slut på supporten i SharePoint 2010-servergruppen, installera en SharePoint Server 2016-servergrupp på ny maskin vara (så att de enskilda Server grupperna körs sida vid sida) och sedan planera och utföra en manuell migrering av innehåll (för att ladda ned och överföra innehåll). Det finns potentiella fall GRO par till de här manuella flytterna (till exempel dokument som kommer från 2010 som har ett uppdaterat senast ändrat konto med aliaset för det konto som gör den manuella flytten), och en del arbete måste utföras i förväg (återskapa webbplatser, under webbplatser, behörigheter och list strukturer). Det är en bra tidpunkt att överväga vilka data du kan flytta till lagring eller inte längre behöver. Det här kan minska migrationens påverkan. Du kan antingen rensa miljön innan du uppgraderar. Var säker på att den befintliga Server gruppen fungerar innan du uppgraderar och (för se) innan du inaktiverar!

Kom ihåg att granska de **uppgraderings vägar som stöds och inte stöds**:

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

Om du har **anpassningar**är det viktigt att du planerar uppgraderingen för varje steg i sökvägen:

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|Lokal fördel|Lokal nackdel|
|---|---|
|Fullständig kontroll över alla aspekter av SharePoint-servergruppen (och det är SQL), från server maskin varan.|Alla raster och korrigeringar är företagets ansvar (men du kan ansvara för Microsoft support om din produkt inte är i slutet av supporten):|
|Fullständig uppsättning funktioner i SharePoint Server lokalt med alternativet att ansluta den lokala server gruppen till en SharePoint Online-prenumeration via hybrid.|Uppgradering, korrigeringsfiler, säkerhets korrigeringar, hård varu uppgraderingar och alla underhåll av SharePoint Server och den SQL-servergruppen hanteras lokalt.|
|Fullständig åtkomst för fler anpassnings alternativ än med SharePoint Online.|[Microsoft-efterföljandekrav](https://go.microsoft.com/fwlink/?linkid=843165) måste konfigureras manuellt lokalt.|
|Säkerhets testning och Server prestanda justering som utförs på dina lokaler (under din kontroll).|Microsoft 365 kan göra funktioner tillgängliga för SharePoint Online som inte fungerar tillsammans med SharePoint Server lokalt|
|Lösnings leverantörer kan hjälpa till att migrera data till nästa version av SharePoint Server (och senare).|Dina SharePoint Server-webbplatser använder inte automatiskt [SSL/TLS-](https://go.microsoft.com/fwlink/?linkid=843167) certifikat som visas i SharePoint Online.|
|Fullständig kontroll över namn konventioner, säkerhets kopiering och återställning och andra återställnings alternativ i SharePoint Server lokalt.|SharePoint Server lokalt är känsligt för produktens livscykler.|

### <a name="upgrade-resources"></a>Uppgradera resurser

Börja med att jämföra maskinvaru-och program varu krav. Om du inte uppfyller grundläggande krav för uppgraderingen på den aktuella maskin varan kan det vara nödvändigt att uppgradera maskin varan i Server gruppen eller SQL-servrarna först, eller så kan du välja att flytta vissa procent av dina webbplatser till "Evergreen"-maskin varan för SharePoint Online. När du har gjort din utvärdering följer du de uppgraderings banor och-metoder som stöds.

- **Maskinvaru-/program varu krav för**:

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- **Program varu begränsningar och begränsningar för**:

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- **Uppgraderings processen översikt för**:

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-sharepoint-server-on-premises"></a>Skapa en SharePoint-hybrid lösning mellan SharePoint Online och SharePoint Server lokalt

Ett annat alternativ (ett som kan vara det bästa av både lokalt och online-världar för vissa migreringsåtgärder) är en hybrid, du kan ansluta SharePoint Server 2013-eller 2016-eller 2019-anläggningar till SharePoint Online för att skapa en SharePoint-hybrid: [Lär dig mer om SharePoint-hybrid lösningar](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).

Om du bestämmer dig för att använda en fjärran sluten SharePoint Server-servergrupp är det viktigt att du planerar vilka webbplatser och användare du bör flytta till online och som du måste hålla lokala. En recension och rangordning av SharePoint Server-gruppens innehåll (för att avgöra vilka data som är hög, medium eller low) kan vara till hjälp för att fatta detta beslut. Det kan vara att det enda du behöver dela med SharePoint Online är (a) användar konton för inloggning och (b) SharePoint Server Search-indexet – detta kan vara oklart tills du ser hur dina webbplatser används. Om ditt företag senare bestämmer dig för att migrera allt innehåll till SharePoint Online kan du flytta alla återstående konton och data online och ta bort den lokala server gruppen och hantering/administration av SharePoint-servergruppen via Microsoft 365-konsoler från den punkten.

Bekanta dig med de befintliga typerna av hybrid och hur du konfigurerar anslutningen mellan den lokala SharePoint-servergruppen och Microsoft 365-prenumerationen.

|Alternativ|Beskrivning|
|---|---|
|[Microsoft Compliance](https://go.microsoft.com/fwlink/?linkid=843165)-funktioner.|[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) hjälp för migrering är begränsad.  <br/> Mycket av uppgraderingen kommer att vara manuell eller via SPO Migration API som beskrivs i Översikt över [SharePoint Online och OneDrive migration](https://go.microsoft.com/fwlink/?linkid=843184).|
|Varken Microsofts support tekniker eller anställda i data centret har obegränsad administratörs åtkomst till din prenumeration.|Det kan finnas extra kostnader om maskin varu infrastrukturen måste uppgraderas för att stödja den nyare versionen av SharePoint, eller om en sekundär server grupp krävs för uppgradering.|
|Partners kan hjälpa till med att migrera dina data till SharePoint Online med engångs arbetet.||
|Online-produkter uppdateras automatiskt i tjänsten, vilket innebär att om funktionerna kan bli gamla finns det inget slut på supporten.||

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

|Lokal Pro|Lokal con|
|---|---|
|Fullständig kontroll över alla aspekter av SharePoint-servergruppen från server maskin varan.|Alla raster och korrigeringar är företagets ansvar (kan hantera Microsoft support om din produkt saknar stöd):|
|Fullständig uppsättning funktioner i SharePoint Server lokalt med alternativet att ansluta den lokala server gruppen till en SharePoint Online-prenumeration via hybrid.|Uppgradering, korrigeringsfiler, säkerhets korrigeringar och alla underhåll av SharePoint Server som hanteras lokalt.|
|Fullständig åtkomst för större anpassning.|[Microsoft-efterföljandekrav](https://go.microsoft.com/fwlink/?linkid=843165) måste konfigureras manuellt lokalt.|
|Säkerhets testning och Server prestanda justering som utförs på dina lokaler (är under din kontroll).|Microsoft 365 kan göra funktioner tillgängliga för SharePoint Online som inte fungerar tillsammans med SharePoint Server lokalt|
|Partners kan hjälpa till att migrera data till nästa version av SharePoint Server (och senare).|Dina SharePoint Server-webbplatser använder inte automatiskt [SSL/TLS-](https://go.microsoft.com/fwlink/?linkid=843167) certifikat som visas i SharePoint Online.|
|Fullständig kontroll över namn konventioner, säkerhets kopiering och återställning och andra återställnings alternativ i SharePoint Server lokalt.|SharePoint Server lokalt är känsligt för produktens livscykler.|

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
> Kom ihåg att SharePoint Server 2010-gruppen måste först uppgraderas, lokalt, till antingen SharePoint Server 2013 eller SharePoint Server 2016 för att använda hybrid alternativet. SharePoint Foundation 2010 och SharePoint Foundation 2013 kan inte skapa hybrid anslutningar med SharePoint Online.

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Översikt över alternativ för Office 2010-klient och servrar och Windows 7

En visuell Sammanfattning av alternativen uppgradera, migrera och flytta till moln för Office 2010-klienter och-servrar och Windows 7 finns i avsnittet [support affisch](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Bild på affischen för supportens upphörande för Office 2010-klienter/servrar och Windows 7](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Den här affischen är ett snabbt sätt att förstå de olika vägarna som du kan vidta för att förhindra att Office 2010-klient och Server produkter och Windows 7 når supporten, med önskade sökvägar och alternativ support i Microsoft 365 Enterprise markerat.

Du kan också [Ladda ned](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) den här affischen och skriva ut den i Letter-, Legal-och Tabloid-format (11 x 17).

## <a name="related-topics"></a>Relaterade ämnen

[Resurser som hjälper dig att uppgradera från Office 2007 eller 2010 servrar och klienter](upgrade-from-office-2010-servers-and-products.md)

[Översikt över uppgraderings processen från SharePoint 2010 till SharePoint 2013](https://technet.microsoft.com/library/mt493301%28v=office.16%29.aspx)

[Metod tips för uppgradering från SharePoint 2010 till SharePoint 2013](https://technet.microsoft.com/library/mt493305%28v=office.16%29.aspx)

[Felsöka problem med databas uppgradering i SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)

[Sök efter Microsoft Solution providers för att hjälpa dig med uppgraderingen](https://go.microsoft.com/fwlink/?linkid=841249)

[Uppdaterad policy för produkt underhåll för SharePoint 2013](https://technet.microsoft.com/library/mt493253%28v=office.16%29.aspx)

[Uppdaterad policy för produkt underhåll för SharePoint Server 2016](https://technet.microsoft.com/library/mt782882%28v=office.16%29.aspx)
