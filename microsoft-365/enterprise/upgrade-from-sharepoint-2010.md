---
title: Uppgradera från SharePoint 2010
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
description: Hitta information och resurser att uppgradera från SharePoint 2010 och Sharepoint Server 2010. Support för båda upphör den 13 april 2021.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4fa82fb0e382a244cdc126609ac62d17280b9702
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925338"
---
# <a name="upgrading-from-sharepoint-2010"></a>Uppgradera från SharePoint 2010

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Supporten för Microsoft SharePoint 2010 och SharePoint Server 2010 avslutas **den 13 april 2021.** Den här artikeln innehåller resurser som hjälper dig att migrera befintliga SharePoint Server 2010-data till SharePoint Online i Microsoft 365 eller uppgradera din lokala SharePoint Server 2010-miljö.

## <a name="what-is-end-of-support"></a>Vad är *slutet på supporten?*

De flesta Microsoft-produkter har en supportlivscykel under vilken de får nya funktioner, programkorrigeringar, säkerhetskorrigeringar och så vidare. Efter supportens slutdatum slutar produkten inte att fungera, men Microsoft tillhandahåller inte längre:

- Teknisk support för problem som kan uppstå.

- Programkorrigeringar för problem som kan påverka servrars stabilitet och användbarhet.

- Säkerhetskorrigeringar för säkerhetsproblem som kan göra servern sårbar för säkerhetsbrister.

- Tidszonsuppdateringar.

Det innebär att det inte finns några ytterligare uppdateringar, korrigeringar eller korrigeringar för produkten (inklusive säkerhetskorrigeringar/korrigeringar). Microsoft Support kommer helt att ha gått över till att stödja nyare versioner.

När supporten för SharePoint Server 2010 närmar sig tar du bort data du inte längre behöver innan du uppgraderar produkten och migrerar viktiga data.

> [!NOTE]
> En programlivscykel varar vanligtvis i tio år från den första versionen. [Microsoft-lösningsleverantörer](https://go.microsoft.com/fwlink/?linkid=841249) kan hjälpa dig att uppgradera till nästa version av programvaran eller migrera till Microsoft 365-migrering (eller båda). Kontrollera även att du känner till supportdatum för viktiga underliggande tekniker, särskilt för den version av Microsoft SQL Server som du använder med SharePoint. Mer information finns i Fast [livscykelpolicy.](https://support.microsoft.com/help/14085)

## <a name="plan-ahead"></a>Planera i förväg

Kontrollera datum då supporten upphör på webbplatsen [För produktens livscykel.](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010) Planera uppgraderingar eller migreringar med dessa datum i åtanke. Kom ihåg att *din produkt inte slutar fungera på* det datum som anges. Men eftersom din installation inte längre kommer att korrigeras efter det datumet är det bra om du planerar en smidig övergång till nästa version av produkten.

I den här matrisen ritas en kurs mellan migreringsalternativen:

|Supporten för produkten avslutas|Bra |Bäst|
|---|---|---|
|SharePoint Server 2010|SharePoint Server 2013 (lokalt)|SharePoint Online|
||SharePoint Server 2013-hybrid med SharePoint Online|SharePoint Server 2016 (lokalt)|
|||SharePoint Cloud-hybridsökning|

Om du väljer ett alternativ i den lägre skalan (bra) måste du börja planera för ytterligare en uppgradering strax efter migreringen från SharePoint Server 2010.

Här är de tre sätt du kan gå för att undvika att supporten för SharePoint Server 2010 tar slut.

![Uppgraderingsvägar för SharePoint Server 2010](../media/upgrade-from-sharepoint-2010/upgrade-from-sharepoint-2010-paths.png)

> [!NOTE]
> Supporten för SharePoint Server 2010 och SharePoint Foundation 2010 har för närvarande schemalagts för den 13 april 2021. Men kontrollera att du har de [senaste datumen på](https://support.microsoft.com/lifecycle) webbplatsen för Produktlivscykel.

## <a name="whats-next"></a>Hur går jag vidare?

SharePoint Server 2013 och SharePoint Foundation 2013 kan installeras lokalt på dina egna servrar. Du kan också använda SharePoint Online, som är en onlinetjänst som ingår i Microsoft 365. Du kan välja att:

- Migrera till SharePoint Online.

- Uppgradera SharePoint Server eller SharePoint Foundation lokalt.

- Gör båda ovanstående.

- Implementera en [SharePoint-hybridlösning.](/sharepoint/hybrid/hybrid)

Överväg de dolda kostnaderna för att underhålla en servergrupp, inklusive underhåll eller migrering av anpassningar och uppgradering av maskinvara. Om du redovisat dessa faktorer blir det enklare att uppgradera lokalt. Om du kör servergruppen på äldre SharePoint-servrar utan tung anpassning kan du dra nytta av en planerad migrering till SharePoint Online. För en lokal SharePoint Server-miljö kan du även flytta vissa data i SharePoint Online för att minska maskinvaruhanteringen.

> [!NOTE]
> SharePoint-administratörer kan skapa en Microsoft 365-prenumeration, konfigurera nya SharePoint Online-webbplatser och sedan rensa SharePoint Server 2010 och ta endast viktiga dokument till nya webbplatser. Därefter kan alla återstående data tas bort från SharePoint Server 2010-webbplatsen till de lokala arkiven.

|SharePoint Online|SharePoint Server lokalt|
|---|---|
|Hög kostnad i tid (plan/körning/verifiering)|Hög kostnad i tid (plan/körning/verifiering)|
|Lägre kostnad i pengar (inga maskinvaruinköp)|Högre kostnad i pengar (maskinvaruinköp)|
|One-time cost in migration|Upprepad kostnad vid framtida migreringar|
|Låg total kostnad för ägande/underhåll|Hög total kostnad för ägande/underhåll|

Om du flyttar över till Microsoft 365 en gång blir kostnaden högre när du organiserar data och bestämmer vad som ska flyttas till molnet och vad som ska bli kvar. Men när dina data har migrerats kommer framtida uppgraderingar att ske automatiskt, eftersom du inte längre behöver hantera maskinvaru- och programvaruuppdateringar. Drifttiden för servergruppen backas upp genom ett [Microsoft-serviceavtal (SLA).](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)

### <a name="migrate-to-sharepoint-online"></a>Migrera till SharePoint Online

Se till att SharePoint Online erbjuder alla funktioner du behöver. Se [Beskrivning av SharePoint-tjänst](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description).

Du kan inte migrera direkt från SharePoint Server 2010 (eller SharePoint Foundation 2010) till SharePoint Online. Så mycket av migreringen är manuellt. Men i det här steget får du möjlighet att använda data och webbplatser som inte längre behövs innan flytten. Du kan arkivera andra data till lagring. 

Kom ihåg att SharePoint Server 2010 och SharePoint Foundation 2010 inte slutar fungera när supporten är slut. Administratörer kan alltså ha en period när SharePoint fortfarande körs om kunderna glömmer att flytta vissa data.

Om du uppgraderar till SharePoint Server 2013 eller SharePoint Server 2016 och bestämmer dig för att placera data i SharePoint Online kan du använda migrerings-API:t för [SharePoint](https://support.office.com/article/Upload-on-premises-content-to-SharePoint-Online-using-PowerShell-cmdlets-555049c6-15ef-45a6-9a1f-a1ef673b867c?ui=en-US&amp;rs=en-US&amp;ad=US) för att migrera information till OneDrive för företag.

|SharePoint Online-fördelar|SharePoint Online-nackdelar|
|---|---|
|Microsoft tillhandahåller SPO-maskinvara och all maskinvaruadministration.|Tillgängliga funktioner kan skilja sig mellan SharePoint Server lokalt och SPO.|
|Du är global administratör för prenumerationen och kan tilldela administratörer till SPO-webbplatser.|Vissa åtgärder som är tillgängliga för en servergruppsadministratör i SharePoint Server lokalt finns inte (eller är inte nödvändiga) i rollen SharePoint-administratör i Microsoft 365. Men SharePoint-administration, administration av webbplatssamling och webbplatsägarskap är lokala för din organisation.|
|Microsoft tillämpar korrigeringar, korrigeringar och uppdateringar för underliggande maskinvara och programvara, inklusive SQL-servrar som SharePoint Online körs på.|Eftersom det inte finns åtkomst till det underliggande filsystemet i tjänsten är anpassningen begränsad.|
|Microsoft publicerar [serviceavtal och flyttar](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) snabbt för att lösa incidenter på tjänstnivå.|Säkerhetskopiering och återställning och andra återställningsalternativ automatiseras av tjänsten i SharePoint Online. Säkerhetskopior skrivs över om de inte används.|
|Säkerhetstestning och serverprestandajustering utförs kontinuerligt i tjänsten av Microsoft.|Ändringar av användargränssnittet och andra SharePoint-funktioner installeras av tjänsten och kan behöva vara på eller av.|
|Microsoft 365 uppfyller många branschstandarder: [Microsofts efterlevnadserbjudanden](/compliance/regulatory/offering-home).|[FastTrack-hjälp](https://go.microsoft.com/fwlink/?linkid=518597) för migrering är begränsad.  <br/> Mycket av uppgraderingen sker manuellt eller via SPO-migrerings-API:t som beskrivs i översikten över innehållsmigrering i [SharePoint Online och OneDrive.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)|
|Microsofts supporttekniker och anställda på datacenter har inte obegränsad administratörsåtkomst till din prenumeration.|Det kan till exempel bli ytterligare kostnader om maskinvaruinfrastrukturen måste uppgraderas för att stödja den nyare versionen av SharePoint eller om en sekundär servergrupp krävs för uppgraderingen.|
|Lösningsleverantörer kan hjälpa dig med det lediga jobbet med att migrera data till SharePoint Online.|Du kan inte styra över alla ändringar i SharePoint Online. Efter migreringen kan designskillnaderna i menyer, bibliotek och andra funktioner tillfälligt påverka användbarheten.|
|Onlineprodukter uppdateras automatiskt i tjänsten. Funktioner kanske förfasas, men det finns ingen livscykel för support.|Supporten för SharePoint Server eller SharePoint Foundation och underliggande SQL-servrar måste upphöra.|

Om du har bestämt dig för att skapa en ny Microsoft 365-webbplats och manuellt migrerar data till den efter behov, kontrollerar du dina [Microsoft 365-alternativ.](https://www.microsoft.com/microsoft-365/)

### <a name="upgrade-sharepoint-server-on-premises"></a>Uppgradera SharePoint Server lokalt

Från och med SharePoint Server 2019 måste uppgraderingarna gå *serien igenom.* Det går inte att direkt uppgradera från SharePoint Server 2010 till SharePoint Server 2016 eller till SharePoint 2019. Serieuppgraderingsväg:

- SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Det tar tid och planering att följa hela vägen från SharePoint 2010 till SharePoint Server 2016. Uppgraderingar innebär kostnader för maskinvara (SQL-servrar måste också uppgraderas), programvara och administration. Dessutom kan anpassningar behöva uppgraderas eller till och med tas bort. Se till att dokumentera viktiga anpassningar innan du uppgraderar SharePoint Server-servergruppen.

> [!NOTE]
> Det är möjligt att behålla den SharePoint 2010-servergrupp som du inte stöder, installera en SharePoint Server 2016-servergrupp på ny maskinvara (så att de separata servergruppen körs sida vid sida) och sedan planera och utföra en manuell migrering av innehåll (till exempel för att ladda ned och ladda upp innehåll på nytt). Men det finns potentiella fallgropar i de här manuella flytterna, till exempel dokument från 2010 med ett aktuellt konto som senast ändrades och alias för det konto som flyttar manuellt. Och en del arbete måste göras i förväg, till exempel återskapa webbplatser, underwebbplatser, behörigheter och liststrukturer. Se till att rensa miljön innan du uppgraderar. Fundera på vilka data du kan flytta till lagring eller inte längre behöver. Det kan minska konsekvenserna av migreringen. Se till att din befintliga servergrupp fungerar innan du uppgraderar, och (verkligen) innan du inaktiverar den!

Kom ihåg att granska *de uppgraderingsvägar som stöds och inte stöds:*

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

Om du *har anpassningar är* det viktigt att du planerar för varje steg i migreringsprocessen:

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|Lokal fördel|Lokal nackdel|
|---|---|
|Fullständig kontroll över alla aspekter av SharePoint-servergruppen (och dess SQL), från servermaskinvara och uppåt.|Alla avbrott och korrigeringar ansvarar ditt företag för. Men du kan använda dig av betald Microsoft-support om din produkt inte har gått ut och supporten har gått ut.|
|Fullständig funktionsuppsättning i SharePoint Server lokalt med alternativet att ansluta den lokala servergruppen till en SharePoint Online-prenumeration via hybrid.|Uppgraderingar, korrigeringar, säkerhetskorrigeringar, maskinvaruuppgraderingar och allt underhåll av SharePoint Server och dess SQL-servergrupp hanteras lokalt.|
|Fullständig åtkomst för fler anpassningsalternativ än för SharePoint Online.|[Microsofts efterlevnadserbjudanden](/compliance/regulatory/offering-home) måste konfigureras manuellt lokalt.|
|Säkerhetstestning och serverprestandajustering utförs lokalt under din kontroll.|Microsoft 365 kan göra funktioner tillgängliga för SharePoint Online som inte fungerar tillsammans med SharePoint Server lokalt.|
|Lösningsleverantörer kan hjälpa dig att migrera data till nästa version av SharePoint Server (och därefter).|Dina SharePoint Server-webbplatser använder inte [automatiskt SSL-/TLS-certifikat](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) som visas i SharePoint Online.|
|Fullständig kontroll över namnkonventioner, säkerhetskopiering och återställning och andra återställningsalternativ i SharePoint Server lokalt.|SharePoint Server lokalt är känsligt för produkternas livscykler.|

### <a name="upgrade-resources"></a>Uppgradera resurser

Börja med att jämföra maskin- och programvarukrav. Om din aktuella miljö inte uppfyller grundläggande krav kan du behöva uppgradera maskinvaran i servergruppen eller SQL-servrarna först. 

Du kanske bestämmer dig för att flytta vissa av dina webbplatser till den "evighet"-maskinvara som finns i SharePoint Online. När du har gjort din utvärdering följer du de uppgraderingsvägar och metoder som stöds.

- *Maskin-/programvarukrav för:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *Programvarubegränsningar för:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *En översikt över uppgraderingsprocessen för:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-hybrid-solution-with-sharepoint-online-and-sharepoint-server-on-premises"></a>Skapa en hybridlösning med SharePoint Online och SharePoint Server lokalt

En hybridkonfiguration ger det bästa av både lokalt och online för vissa migreringsbehov. Du kan ansluta SharePoint Server 2013-, 2016- eller 2019-servergrupper till SharePoint Online för att skapa en SharePoint-hybrid: Läs mer om [SharePoint-hybridlösningar.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Om en SharePoint Server-hybridservergrupp är ditt migreringsmål kan du ta reda på vilka webbplatser och användare som ska flytta online och vilka som måste vara lokala. Att rangordna servergruppsinnehållet i SharePoint Server till högt, medelstort eller lågt påverkan på ditt företag kan vara till hjälp med det här beslutet. Du kanske bara behöver dela användarkonton för inloggning och SharePoint Server-sökindexet med SharePoint Online. Men den här faktorn kanske inte är helt klar förrän du tittar på hur webbplatserna används. Om ditt företag senare bestämmer sig för att migrera allt innehåll till SharePoint Online kan du flytta alla återstående konton och data online och inaktivera din lokala servergrupp. Hantering/administration av SharePoint-servergruppen utförs via Microsoft 365-konsoler från och med då.

Bekanta dig med de befintliga typerna av hybrider och hur du konfigurerar anslutningen mellan den lokala SharePoint-servergruppen och Microsoft 365-prenumerationen.

|Alternativ|Beskrivning|
|---|---|
|[Microsofts efterlevnadserbjudanden.](/compliance/regulatory/offering-home)|[FastTrack-hjälp](https://www.microsoft.com/fasttrack/microsoft-365) för migrering är begränsad.<br/><br/> Mycket av uppgraderingen sker manuellt eller via SPO-migrerings-API:t som beskrivs i översikten över innehållsmigrering i [SharePoint Online och OneDrive.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)|
|Microsofts supporttekniker och anställda på datacenter har inte obegränsad administratörsåtkomst till din prenumeration.|Det kan bli ytterligare kostnader om maskinvaruinfrastrukturen måste uppgraderas för att stödja den nyare versionen av SharePoint, eller om en sekundär servergrupp krävs.|
|Partner kan hjälpa till med det lediga jobbet att migrera dina data till SharePoint Online.||
|Onlineprodukter uppdateras automatiskt i tjänsten. Funktionerna kanske förfasas, men det finns inget stöd för det.||

Om du har bestämt dig för att skapa en ny Microsoft 365-webbplats och manuellt migrera data till den efter behov, kontrollerar du dina [Microsoft 365-alternativ.](https://www.microsoft.com/microsoft-365/)

### <a name="upgrade-sharepoint-server-on-premises"></a>Uppgradera SharePoint Server lokalt

Det går inte att hoppa över versioner i SharePoint-uppgraderingar. Det innebär att uppgraderingarna går igenom:

- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016

Om du ska gå hela vägen från SharePoint 2007 till SharePoint Server 2016 innebär det betydande investeringar i tid och maskinvara (SQL-servrar måste också uppgraderas), programvara och administrationskostnader. Anpassningar måste uppgraderas eller tas bort beroende på hur kritisk funktionen är.

> [!NOTE]
> Det är möjligt att behålla din livscykel för SharePoint 2007-servergruppen, installera en SharePoint Server 2016-servergrupp på ny maskinvara (så att de separata servergruppen körs sida vid sida) och sedan planera och utföra en manuell migrering av innehåll (till exempel för att ladda ned och ladda upp innehåll på nytt). Det finns dock vissa nackdelar med de här manuella flyttarna, till exempel att flytta dokument och ersätta kontot med senast ändrad med alias för det konto som flyttar manuellt. Och mycket arbete måste göras i förväg, till exempel återskapa webbplatser, underwebbplatser, behörigheter och liststrukturer. Fundera i alla fall på vilka data du kan flytta till lagringen eller inte längre behöver minska konsekvenserna av migreringen.

Se till att rensa miljön innan du uppgraderar. Se till att din befintliga servergrupp fungerar innan du uppgraderar, och absolut innan du inaktiverar den!

Kom ihåg att granska *de uppgraderingsvägar som stöds och inte stöds:*

- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)

Om du *har anpassningar är* det viktigt att planera uppgraderingen för varje steg i migreringsprocessen:

- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))

- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))

- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)

|Lokalt proffs|Lokal con|
|---|---|
|Fullständig kontroll över alla aspekter av SharePoint-servergruppen, allt från servermaskinvara och uppåt.|Alla avbrott och korrigeringar ansvarar ditt företag för. (Men du kan kontakta betald Microsoft Support om din produkt inte har gått ut och supporten har gått ut.)|
|Fullständig funktionsuppsättning i SharePoint Server lokalt med alternativet att ansluta den lokala servergruppen till en SharePoint Online-prenumeration via hybrid.|Uppgraderingar, korrigeringar, säkerhetskorrigeringar och allt underhåll av SharePoint Server hanteras lokalt.|
|Fullständig åtkomst för större anpassning.|[Microsofts efterlevnadserbjudanden](/compliance/regulatory/offering-home) måste konfigureras manuellt lokalt.|
|Säkerhetstestning och serverprestandajustering utförs lokalt under din kontroll.|Microsoft 365 kan göra funktioner tillgängliga för SharePoint Online som inte fungerar tillsammans med SharePoint Server lokalt.|
|Partner kan hjälpa till att migrera data till nästa version av SharePoint Server (och därefter).|Dina SharePoint Server-webbplatser använder inte [automatiskt SSL-/TLS-certifikat](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) som visas i SharePoint Online.|
|Fullständig kontroll över namnkonventioner, säkerhetskopiering och återställning och andra återställningsalternativ i SharePoint Server lokalt.|SharePoint Server lokalt är känsligt för produkternas livscykler.|

### <a name="upgrade-resources"></a>Uppgradera resurser

Börja med att veta att du uppfyller maskinvaru- och programvarukraven och följ sedan de uppgraderingsmetoder som stöds.

- *Maskin-/programvarukrav för:*

    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)

- *Programvarubegränsningar för:*

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)

- *En översikt över uppgraderingsprocessen för:*

    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)

### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Skapa en SharePoint-hybridlösning mellan SharePoint Online och en lokal miljö

Om svaret på dina behov för migrering ligger någonstans mellan den kontroll som erbjuds av lokala och den lägre ägandekostnaden som erbjuds av SharePoint Online, kan du ansluta SharePoint Server 2013- eller 2016-servergrupper till SharePoint Online via hybrider. [Läs mer om SharePoint-hybridlösningar](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)

Om du anser att en SharePoint Server-hybridservergrupp kan dra nytta av ditt företag bör du läsa mer om de befintliga hybridtyperna och hur du konfigurerar anslutningen mellan den lokala SharePoint-servergruppen och Microsoft 365-prenumerationen.

Du kanske vill skapa en utvecklings-/testmiljö för Microsoft 365 som du kan konfigurera med [testlabbguider.](m365-enterprise-test-lab-guides.md) När du har fått en utvärderingsversion eller har köpt en Microsoft 365-prenumeration kan du skapa webbplatssamlingar, webbplatser och dokumentbibliotek i SharePoint Online som du kan migrera data till. Du kan migrera manuellt med hjälp av migrerings-API:t eller, om du vill migrera Innehållet på Min webbplats till OneDrive för företag, via hybridguiden.

> [!NOTE]
> Om du vill använda hybridalternativet måste SharePoint Server 2010-servergruppen först uppgraderas lokalt till SharePoint Server 2013 eller 2016. SharePoint Foundation 2010 och SharePoint Foundation 2013 har inte stöd för hybridanslutningar till SharePoint Online.

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Sammanfattning av alternativ för Office 2010 klient och servrar och Windows 7

En visuell sammanfattning av alternativen för uppgradering, migrering och flytt till molnet för Office 2010-klienter och -servrar och Windows 7 finns på [supportaffischens](../downloads/Office2010Windows7EndOfSupport.pdf)slut.

[![Supporten för Office 2010-klienter och -servrar och affischen för Windows 7 har upphöra](../media/upgrade-from-office-2010-servers-and-products/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Den här affischen illustrerar de olika sätt du kan gå för att undvika Office 2010 klient- och serverprodukter och supporten i Windows 7, med föredragna sökvägar och alternativ som stöds i Microsoft 365 Enterprise markerat.

Du kan också [ladda ned](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) den här affischen och skriva ut den i letter-, legal- eller tabloidformat (11 x 17).

## <a name="related-articles"></a>Relaterade artiklar

[Resurser som hjälper dig att uppgradera från Office 2007- eller 2010-servrar och -klienter](upgrade-from-office-2010-servers-and-products.md)

[Översikt över uppgraderingsprocessen från SharePoint 2010 till SharePoint 2013](/SharePoint/upgrade-and-update/overview-of-the-upgrade-process-from-sharepoint-2010-to-sharepoint-2013)

[Metodtips för uppgradering från SharePoint 2010 till SharePoint 2013](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)

[Felsöka problem med databasuppgradering i SharePoint 2013](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)

[Sök efter leverantörer av Microsoft-lösningar som kan hjälpa dig med uppgraderingen](https://go.microsoft.com/fwlink/?linkid=841249)

[Uppdaterad serviceprincip för produkter för SharePoint 2013](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-2013)

[Uppdaterad princip för produktunderhåll för SharePoint Server 2016](/SharePoint/product-servicing-policy/updated-product-servicing-policy-for-sharepoint-server-2016)