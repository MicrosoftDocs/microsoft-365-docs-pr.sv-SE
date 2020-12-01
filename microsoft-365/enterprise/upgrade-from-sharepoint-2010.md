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
description: Hitta information och resurser att uppgradera från SharePoint 2010 och SharePoint Server 2010. Stöd för båda ändarna 13 april 2021.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fba095a15164f8a09ce1e0a1cbd5ee9cd298aa74
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519769"
---
# <a name="upgrading-from-sharepoint-2010"></a>Uppgraderar från SharePoint 2010

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Microsoft SharePoint 2010 och SharePoint Server 2010 når supporten den **13 April 2021**. Den här artikeln innehåller resurser som hjälper dig att migrera dina befintliga SharePoint Server 2010-data till SharePoint Online i Microsoft 365 eller uppgradera din lokala SharePoint Server 2010-miljö.

## <a name="what-is-end-of-support"></a>Vad är *support slut*?

De flesta Microsoft-produkter har en support livs cykel, under vilken de har nya funktioner, korrigeringar, säkerhets korrigeringar och så vidare. Efter slutdatumet upphör inte produkten att fungera, men Microsoft tillhandahåller inte längre:

- Teknisk support för problem som kan uppstå.

- Program korrigeringar för problem som kan påverka serverns stabilitet och användbarhet.

- Säkerhets korrigeringar för säkerhets problem som kan göra servern sårbar för säkerhets brott.

- Tids zons uppdateringar.

Det innebär att det inte kommer att finnas fler uppdateringar, korrigeringar eller korrigeringar för produkten (inklusive säkerhets korrigeringar/korrigeringar). Microsoft Support kommer att helt och hållet flytta sina support ansträngningar till nyare versioner.

I slutet av stöd för SharePoint Server 2010-metoder kan du ta bort data som du inte längre behöver innan du uppgraderar produkten och migrerar viktiga data.

> [!NOTE]
> En program livs cykel räcker normalt för tio år från den första versionen. [Microsoft Solution providers](https://go.microsoft.com/fwlink/?linkid=841249) kan hjälpa dig att uppgradera till nästa version av program varan eller migrera till Microsoft 365 migration (eller båda två). Se till att du är medveten om slutgiltigt stöd för de grundläggande underliggande teknikerna, särskilt för den version av Microsoft SQL Server du använder med SharePoint. Mer information finns i [policyn för fast livs cykel](https://support.microsoft.com/help/14085).

## <a name="plan-ahead"></a>Planera framåt

Kontrol lera datumen som har stöd för att sluta på [produktens livs cykel webbplats](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010). Planera dina uppgraderingar eller migreringar med dessa datum i åtanke. Kom ihåg att produkten *inte upphör att fungera* vid det datum som visas. Men eftersom installationen inte längre kommer att göras efter detta datum bör du planera en smidig över gång till nästa version av produkten.

Den här matrisen hjälper till att rita en kurs mellan olika migrations alternativ:

|Slut på support produkt|Bra |Metod|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (lokal)|SharePoint online|
||SharePoint Server 2013 hybrid med SharePoint Online|SharePoint Server 2016 (lokal)|
|||SharePoint-moln HYBRIDS ökning|

Om du väljer ett alternativ på den nedre delen av skalan (bra) måste du börja planera för en annan uppgradering strax efter migreringen från SharePoint Server 2010.

Här är de tre vägarna som du kan vidta för att undvika slut på stöd för SharePoint Server 2010.

![SharePoint Server 2010-uppgraderings Sök vägar](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> Slut på supporten för SharePoint Server 2010 och SharePoint Foundation 2010 är för närvarande schemalagd för den 13 april 2021. Men se till att du kontrollerar [produktens livscykel webbplats](https://support.microsoft.com/lifecycle) för de mest aktuella datumen.

## <a name="whats-next"></a>Hur går jag vidare?

SharePoint Server 2013 och SharePoint Foundation 2013 kan installeras lokalt på dina egna servrar. Eller så kan du använda SharePoint Online, som är en online tjänst som är en del av Microsoft 365. Du kan välja att:

- Migrera till SharePoint Online.

- Uppgradera SharePoint Server eller SharePoint Foundation lokalt.

- Gör båda ovanstående.

- Implementera en [SharePoint-hybrid](https://docs.microsoft.com/sharepoint/hybrid/hybrid) lösning.

Överväg de dolda kostnaderna för att underhålla en Server grupp, inklusive underhåll och migrering och uppgradering av maskin vara. Om du har använt dessa faktorer är det enklare att uppgradera lokalt. Om du kör Server gruppen på äldre SharePoint-servrar utan omfattande anpassning kan du dra nytta av en planerad migrering till SharePoint Online. Om du har en lokal SharePoint Server-miljö kan du också överväga att flytta vissa data i SharePoint Online för att minska maskin varu hanteringen.

> [!NOTE]
> SharePoint-administratörer kan skapa en Microsoft 365-prenumeration, konfigurera nya SharePoint Online-webbplatser och sedan klipps ut från SharePoint Server 2010 på ett städat sätt, med nödvändiga dokument till de nya webbplatserna. Sedan kan återstående data tömmas från SharePoint Server 2010-webbplatsen till lokala arkiv.

|SharePoint online|SharePoint Server lokalt|
|---|---|
|Hög kostnad i tid (planering/körning/verifiering)|Hög kostnad i tid (planering/körning/verifiering)|
|Lägre kostnad i pengar (inga maskin varu köp)|Högre kostnad i pengar (maskin varu köp)|
|Engångs kostnad i migration|Upprepad engångs kostnad per framtida migrering|
|Låga totala kostnader för ägande/underhåll|Hög total kostnad för ägande/underhåll|

En engångs flytt till Microsoft 365 kommer att ha högre kostnad när du strukturerar data och bestämmer vad som ska tas till molnet och vad du ska lämna. Men efter att dina data har migrerats kommer framtida uppgraderingar att fungera som de ska, eftersom du inte längre behöver hantera maskinvaru-och program varu uppdateringar. Och Server gruppens drift tid kommer att säkerhets kopie ras av ett [Microsoft service avtal (SLA)](https://go.microsoft.com/fwlink/?linkid=843153).

### <a name="migrate-to-sharepoint-online"></a>Migrera till SharePoint Online

Se till att SharePoint online erbjuder alla funktioner du behöver. Se [SharePoint Service Description](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description).

Du kan inte migrera direkt från SharePoint Server 2010 (eller SharePoint Foundation 2010) till SharePoint Online. Så mycket av migreringen är manuell. I det här steget får du möjlighet att rensa data och webbplatser som inte längre behövs innan flytten. Du kan arkivera andra data i lagrings utrymmet. 

Kom ihåg att SharePoint Server 2010 och SharePoint Foundation 2010 inte upphör att fungera vid Supportens slut. Administratörer kan dock ha en period då SharePoint fortfarande körs om deras kunder glömmer att flytta en del av sina data.

Om du uppgraderar till SharePoint Server 2013 eller SharePoint Server 2016 och bestämmer dig för att lägga till data i SharePoint Online, kan du använda [SharePoint Migration API](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) för att migrera information till OneDrive för företag.

|Fördel med SharePoint Online|Nackdel med SharePoint Online|
|---|---|
|Microsoft tillhandahåller SPO maskin vara och all maskin varu administration.|Tillgängliga funktioner kan skilja sig mellan SharePoint Server lokalt och SPO.|
|Du är global administratör för din prenumeration och kan tilldela administratörer till SPO webbplatser.|Vissa åtgärder som är tillgängliga för en server grupps administratör i SharePoint Server lokalt finns inte (eller är inte nödvändiga) i administratörs rollen för SharePoint i Microsoft 365. Men administration av webbplats samling och webbplats ägarskap är lokala för din organisation.|
|Microsoft tillämpar korrigeringsfiler, korrigeringar och uppdateringar för underliggande maskin vara och program vara, inklusive SQL-servrar där SharePoint Online körs.|Eftersom det inte finns någon åtkomst till underliggande fil system i tjänsten är anpassningen begränsad.|
|Microsoft publicerar [service nivå avtal](https://go.microsoft.com/fwlink/?linkid=843153) och går snabbt för att lösa händelser på tjänst nivå.|Säkerhets kopiering och återställning och andra återställnings alternativ automatiseras av tjänsten i SharePoint Online. Säkerhets kopior skrivs över om den inte används.|
|Säkerhets testning och Server prestanda justering utförs kontinuerligt i tjänsten av Microsoft.|Ändringar i användar gränssnittet och andra SharePoint-funktioner installeras av tjänsten och kan behöva sättas på eller av.|
|Microsoft 365 uppfyller många bransch standarder: [Microsoft Compliance](https://go.microsoft.com/fwlink/?linkid=843165)-support.|[FastTrack](https://go.microsoft.com/fwlink/?linkid=518597) hjälp för migrering är begränsad.  <br/> Mycket av uppgraderingen kommer att vara manuell eller via SPO Migration API som beskrivs i [Översikt över SharePoint Online och OneDrive migration](https://go.microsoft.com/fwlink/?linkid=843184).|
|Microsofts support tekniker och data Center-anställda har inte obegränsade administratörs åtkomst till din prenumeration.|Det kan finnas extra kostnader om maskin varu infrastrukturen måste uppgraderas för att stödja den nyare versionen av SharePoint eller om en sekundär server grupp krävs för uppgradering.|
|Lösnings leverantörer kan hjälpa dig med ett engångs jobb för migrering av data till SharePoint Online.|Alla ändringar av SharePoint Online ligger inte inom din kontroll. Efter migreringen kan det påverka användbarheten tillfälligt.|
|Online-produkter uppdateras automatiskt i tjänsten. Funktioner kanske föråldrade, men det finns inget slut på support livs cykeln.|Det finns en slut livs cykel för SharePoint Server eller SharePoint Foundation samt underliggande SQL-servrar.|

Om du har bestämt dig för att skapa en ny Microsoft 365-webbplats och manuellt migrera data till den, kan du kontrol lera dina [Microsoft 365-alternativ](https://www.microsoft.com/microsoft-365/).

### <a name="upgrade-sharepoint-server-on-premises"></a>Uppgradera SharePoint Server lokalt

Från och med SharePoint Server 2019 måste uppgraderingar vara  *seriellt*. Det finns inget sätt att uppgradera från SharePoint Server 2010 till SharePoint Server 2016 eller till SharePoint 2019 direkt. Sökväg för seriell uppgradering:

- SharePoint Server 2010 \> SharePoint server 2013 \> sharepoint server 2016

Det tar tid och planerar att följa hela vägen från SharePoint 2010 till SharePoint Server 2016. Uppgraderingar inkluderar kostnader för hård vara (SQL-servrar måste också uppgraderas), program vara och administration. Dessutom kan anpassningar behöva uppgraderas eller till och med överges. Se till att dokumentera viktiga anpassningar innan du uppgraderar din SharePoint Server-servergrupp.

> [!NOTE]
> Det är möjligt att behålla ditt slut på SharePoint 2010-servergrupper, installera en SharePoint Server 2016-servergrupp på ny maskin vara (så att de enskilda Server grupperna körs sida vid sida) och sedan planera och utföra en manuell migrering av innehåll (för att till exempel Ladda ner och överföra innehåll). Men det finns potentiella fall GRO par till dessa manuella flyttningar, till exempel dokument som kommer från 2010 med ett uppdaterat konto med senaste ändringar och alias för det konto som gör den manuella flytten. Och viss åtgärd måste utföras i förväg, till exempel återskapa webbplatser, under webbplatser, behörigheter och list strukturer. Se till att rensa miljön innan du uppgraderar. Överväg vilka data du kan flytta till lagring eller inte längre behöver. Det här kan minska migrationens påverkan. Var säker på att den befintliga Server gruppen fungerar innan du uppgraderar och att du är (verkligen) innan du avvecklar!

Kom ihåg att granska de *uppgraderings vägar som stöds och inte stöds*:

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

Om du har *anpassningar* är det viktigt att du planerar för varje steg i sökvägen:

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|Lokal fördel|Lokal nackdel|
|---|---|
|Fullständig kontroll över alla aspekter av SharePoint-servergruppen (och dess SQL), från server maskin varan.|Alla raster och korrigeringar är företagets ansvar. Men du kan engagera Microsoft support om din produkt inte har gått med i supporten.|
|Fullständig uppsättning funktioner i SharePoint Server lokalt med alternativet att ansluta den lokala server gruppen till en SharePoint Online-prenumeration via hybrid.|Uppgradering, korrigeringsfiler, säkerhets korrigeringar, hård varu uppgraderingar och alla underhåll av SharePoint Server och dess SQL-servergrupp hanteras lokalt.|
|Fullständig åtkomst för fler anpassnings alternativ än med SharePoint Online.|[Microsoft-efterföljandekrav](https://go.microsoft.com/fwlink/?linkid=843165) måste konfigureras manuellt lokalt.|
|Säkerhets testning och Server prestanda justering utförs på dina lokaler under din kontroll.|Microsoft 365 kan göra funktioner tillgängliga för SharePoint Online som inte fungerar tillsammans med SharePoint Server lokalt.|
|Lösnings leverantörer kan hjälpa till att migrera data till nästa version av SharePoint Server (och senare).|Dina SharePoint Server-webbplatser använder inte automatiskt [SSL/TLS-](https://go.microsoft.com/fwlink/?linkid=843167) certifikat som visas i SharePoint Online.|
|Fullständig kontroll över namn konventioner och säkerhets kopiering och återställning och andra återställnings alternativ i SharePoint Server lokalt.|SharePoint Server lokalt är känsligt för produktens livscykler.|

### <a name="upgrade-resources"></a>Uppgradera resurser

Börja med att jämföra maskinvaru-och program varu krav. Om din nuvarande miljö inte uppfyller grundläggande krav kan du behöva uppgradera maskin varan i Server gruppen eller SQL-servrarna först. 

Du kan välja att flytta några av dina webbplatser till "Evergreen"-maskin varan för SharePoint Online. När du har gjort din utvärdering följer du de uppgraderings banor och-metoder som stöds.

- *Maskinvaru-/program varu krav för:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- *Program varu begränsningar och begränsningar för:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *Uppgraderings processen översikt för:*

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>Skapa en hybrid lösning med SharePoint Online och SharePoint Server lokalt

En hybrid konfiguration ger det bästa av både lokalt och online för vissa migreringsåtgärder. Du kan ansluta SharePoint Server 2013-, 2016-eller 2019-grupper till SharePoint Online för att skapa en SharePoint-hybrid: [Lär dig mer om hybrid lösningar för SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx).

Om en fjärran sluten SharePoint Server-grupp är ditt mål för migrering kan du ta reda på vilka webbplatser och användare du vill flytta online och vilka som måste vara lokala. Du kan få hjälp med detta beslut genom att rangordna innehållet i SharePoint Server-gruppen som hög, medel eller nedsatt effekt för ditt företag. Du behöver kanske bara dela användar konton för inloggning och SharePoint Server Search index med SharePoint Online. Men det kan hända att den här faktorn inte är klar förrän du ser hur dina webbplatser används. Om ditt företag senare bestämmer dig för att migrera allt innehåll till SharePoint Online kan du flytta alla återstående konton och data online och inaktivera den lokala server gruppen. Hanteringen/administrationen av SharePoint-servergruppen görs via Microsoft 365-konsoler från den punkten.

Bekanta dig med befintliga typer av hybrider och hur du konfigurerar anslutningen mellan den lokala SharePoint-servergruppen och Microsoft 365-prenumerationen.

|Alternativ|Beskrivning|
|---|---|
|[Microsoft Compliance](https://go.microsoft.com/fwlink/?linkid=843165)-funktioner.|[FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) hjälp för migrering är begränsad.<br/><br/> Mycket av uppgraderingen kommer att vara manuell eller via SPO Migration API som beskrivs i [Översikt över SharePoint Online och OneDrive migration](https://go.microsoft.com/fwlink/?linkid=843184).|
|Microsofts support tekniker och data Center-anställda har inte obegränsade administratörs åtkomst till din prenumeration.|Det kan finnas extra kostnader om maskin varu infrastrukturen måste uppgraderas för att stödja den nyare versionen av SharePoint, eller om en sekundär server grupp krävs.|
|Partners kan hjälpa till med att migrera dina data till SharePoint Online med engångs arbetet.||
|Online-produkter uppdateras automatiskt i tjänsten. Funktioner kan vara inaktuella, men det finns inget slut på support.||

Om du har bestämt dig för att skapa en ny Microsoft 365-webbplats och manuellt migrera data till den som behövs läser du [Microsoft 365-alternativen](https://www.microsoft.com/microsoft-365/).

### <a name="upgrade-sharepoint-server-on-premises"></a>Uppgradera SharePoint Server lokalt

Du kan inte hoppa över versioner i SharePoint-uppgraderingar. Det innebär att uppgraderingarna går seriellt:

- SharePoint 2007 \> SharePoint server 2010 \> sharepoint Server 2013 \> SharePoint Server 2016

Om du vill ta hela vägen från SharePoint 2007 till SharePoint Server 2016 avses en betydande tid och inbegriper maskin vara (SQL-servrar måste också uppgraderas), program vara och administrativa kostnader. Anpassningar måste uppgraderas eller överlåtas, beroende på funktionens viktighets grad.

> [!NOTE]
> Det är möjligt att behålla ditt slut på SharePoint 2007-servergrupper, installera en SharePoint Server 2016-servergrupp på ny maskin vara (så att de enskilda Server grupperna körs sida vid sida) och sedan planera och utföra en manuell migrering av innehåll (för att till exempel Ladda ner och överföra innehåll). Men det finns vissa nack delar med dessa manuella flyttningar, till exempel flyttningar av dokument, som ersätter det senast ändrade kontot med aliaset för den manuella flytten. Och mycket arbete måste utföras i förväg, till exempel återskapa webbplatser, under webbplatser, behörigheter och list strukturer. I alla händelser kan du överväga vilka data du kan flytta till lagring eller inte längre behöver minska migrationens påverkan.

Se till att rensa miljön innan du uppgraderar. Var säker på att den befintliga Server gruppen fungerar innan du uppgraderar och verkligen innan du avvecklar!

Kom ihåg att granska de *uppgraderings vägar som stöds och inte stöds*:

- [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843156)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843157)

Om du har *anpassningar* är det viktigt att planera din uppgradering för varje steg i sökvägen:

- [SharePoint 2007](https://go.microsoft.com/fwlink/?linkid=843158)

- [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843160)

- [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843162)

|Lokal Pro|Lokal con|
|---|---|
|Fullständig kontroll över alla aspekter av SharePoint-servergruppen från server maskin varan.|Alla raster och korrigeringar är företagets ansvar. (Men du kan engagera Microsoft support om din produkt inte har gått med i supporten.)|
|Fullständig uppsättning funktioner i SharePoint Server lokalt med alternativet att ansluta den lokala server gruppen till en SharePoint Online-prenumeration via hybrid.|Uppgradering, korrigeringsfiler, säkerhets korrigeringar och alla underhåll av SharePoint Server som hanteras lokalt.|
|Fullständig åtkomst för större anpassning.|[Microsoft-efterföljandekrav](https://go.microsoft.com/fwlink/?linkid=843165) måste konfigureras manuellt lokalt.|
|Säkerhets testning och Server prestanda justering utförs på dina lokaler under din kontroll.|Microsoft 365 kan göra funktioner tillgängliga för SharePoint Online som inte fungerar tillsammans med SharePoint Server lokalt.|
|Partners kan hjälpa till att migrera data till nästa version av SharePoint Server (och senare).|Dina SharePoint Server-webbplatser använder inte automatiskt [SSL/TLS-](https://go.microsoft.com/fwlink/?linkid=843167) certifikat som visas i SharePoint Online.|
|Fullständig kontroll över namn konventioner och säkerhets kopiering och återställning och andra återställnings alternativ i SharePoint Server lokalt.|SharePoint Server lokalt är känsligt för produktens livscykler.|

### <a name="upgrade-resources"></a>Uppgradera resurser

Börja med att veta att du uppfyller maskinvaru-och program varu krav och följ sedan de uppgraderings metoder som stöds.

- *Maskinvaru-/program varu krav för*:

    [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843204)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843206)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843207)

- *Program varu begränsningar och begränsningar för*:

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843245)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843247)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843248)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843249)

- *Uppgraderings processen översikt för*:

    [SharePoint Server 2007](https://go.microsoft.com/fwlink/?linkid=843250)  |  [SharePoint Server 2010](https://go.microsoft.com/fwlink/?linkid=843251)  |  [SharePoint Server 2013](https://go.microsoft.com/fwlink/?linkid=843252)  |  [SharePoint Server 2016](https://go.microsoft.com/fwlink/?linkid=843359)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Skapa en SharePoint-hybrid lösning mellan SharePoint Online och lokalt

Om svaret på dina migreringar är någonstans mellan den kontroll som tillhandahålls av lokala och den lägre ägande kostnaden som erbjuds av SharePoint Online, kan du ansluta SharePoint Server 2013-eller 2016-servergrupper till SharePoint Online via hybrider. [Läs mer om hybrid lösningar för SharePoint](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Om du bestämmer dig för att en fjärran sluten SharePoint Server-grupp ska vara till ditt företag kan du bekanta dig med befintliga typer av hybrider och hur du konfigurerar anslutningen mellan den lokala SharePoint-servergruppen och Microsoft 365-prenumerationen.

Du kanske vill skapa en Microsoft 365 dev/test-miljö som du kan ställa in med [testlabb guider](m365-enterprise-test-lab-guides.md). När du har skaffat en utvärderings version eller Microsoft 365-prenumeration kan du skapa webbplats samlingar, webbplatser och dokument bibliotek i SharePoint Online som du kan migrera data till. Du kan migrera manuellt, med hjälp av migration API, eller om du vill migrera mitt webbplats innehåll till OneDrive för företag med hjälp av Hybrid guiden.

> [!NOTE]
> För att använda hybrid alternativet måste SharePoint Server 2010-gruppen först uppgraderas lokalt till SharePoint Server 2013 eller 2016. SharePoint Foundation 2010 och SharePoint Foundation 2013 har inte stöd för Hybrid anslutningar med SharePoint Online.

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Översikt över alternativ för Office 2010-klient och servrar och Windows 7

En visuell Sammanfattning av alternativen uppgradera, migrera och flytta till moln för Office 2010-klienter och-servrar och Windows 7 finns i avsnittet [support affisch](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Slut på support för Office 2010-klienter och-servrar och Windows 7-affisch](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Denna affisch illustrerar olika sökvägar som du kan vidta för att undvika Office 2010-klient-och Server produkter och Windows 7-supporten, med önskade sökvägar och alternativ som stöds i Microsoft 365 Enterprise markerat.

Du kan också [Ladda ned](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) den här affischen och skriva ut den i Letter-, Legal-och Tabloid-format (11 x 17).

## <a name="related-articles"></a>Relaterade artiklar

[Resurser som hjälper dig att uppgradera från Office 2007 eller 2010 servrar och klienter](upgrade-from-office-2010-servers-and-products.md)

[Översikt över uppgraderings processen från SharePoint 2010 till SharePoint 2013](https://technet.microsoft.com/library/mt493301%28v=office.16%29.aspx)

[Metod tips för uppgradering från SharePoint 2010 till SharePoint 2013](https://technet.microsoft.com/library/mt493305%28v=office.16%29.aspx)

[Felsöka problem med databas uppgradering i SharePoint 2013](https://go.microsoft.com/fwlink/?linkid=843195)

[Sök efter Microsoft Solution providers för att hjälpa dig med uppgraderingen](https://go.microsoft.com/fwlink/?linkid=841249)

[Uppdaterad policy för produkt underhåll för SharePoint 2013](https://technet.microsoft.com/library/mt493253%28v=office.16%29.aspx)

[Uppdaterad policy för produkt underhåll för SharePoint Server 2016](https://technet.microsoft.com/library/mt782882%28v=office.16%29.aspx)
