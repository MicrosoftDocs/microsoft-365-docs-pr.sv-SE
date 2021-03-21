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
description: Stöd för SharePoint Server 2007 upphörde i oktober 2017. I den här artikeln kan du läsa mer om uppgraderings-, migrerings- och supportalternativ.
ms.openlocfilehash: 224b0af90d6a314aa15a2c0dab7b60626e5abde8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924874"
---
# <a name="sharepoint-server-2007-end-of-support-roadmap"></a>Översikt över supporten som upphör för SharePoint Server 2007

*Denna artikel gäller för både Microsoft 365 Enterprise och Office 365 Enterprise.*

Supporten för Microsoft Office SharePoint Server **2007** tog slut den 10 oktober 2017. Om du inte har migrerat från SharePoint Server 2007 till Microsoft 365 eller en nyare version av SharePoint Server lokalt, är det dags att börja planera nu. Den här artikeln innehåller resurser som hjälper dig att migrera data till SharePoint Online eller uppgradera SharePoint Server lokalt.
  
## <a name="what-does-end-of-support-mean"></a>Vad innebär *slutet av supporten?*

SharePoint Server har, som de flesta Microsoft-produkter, en supportlivscykel under vilken Microsoft tillhandahåller nya funktioner, programkorrigeringar, säkerhetskorrigeringar med mer. En livscykel varar vanligtvis i tio år från produktens första version. Slutet av perioden kallas för slutet av supporten för produkten. Efter supportens slut tillhandahåller Microsoft inte längre:
  
- Teknisk support för problem som kan uppstå.
    
- Programkorrigeringar för problem som kan påverka servrars stabilitet och användbarhet.
    
- Säkerhetskorrigeringar för säkerhetsproblem som kan göra servern sårbar för säkerhetsbrister.
    
- Tidszonsuppdateringar.
    
SharePoint Server 2007-servergruppen kommer fortfarande att fungera efter 10 oktober 2017, men inga ytterligare uppdateringar, korrigeringar eller korrigeringar kommer att släppas för produkten, inklusive säkerhetskorrigeringar/korrigeringar. Microsoft Support har helt gått över till att stödja nyare versioner av produkten. Eftersom installationen inte längre stöds eller korrigeras bör du uppgradera produkten eller migrera viktiga data.
  
> [!TIP]
> Om du inte redan har planerat för uppgradering eller migrering kan du gå till: [SharePoint 2007](sharepoint-2007-migration-options.md) – Migreringsalternativ för att ta hänsyn till några exempel på var du kan börja. Du kan också söka efter [Microsoft-partner som](https://go.microsoft.com/fwlink/?linkid=841249) kan hjälpa dig med uppgraderingen eller Migrering till Microsoft 365 (eller båda).
  
Mer information om Office 2007-servrar och slutet på supporten finns i Resurser som hjälper dig att uppgradera från [Office 2007-servrar och -klienter.](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-are-my-options"></a>Vilka alternativ har jag?

Ditt första stopp bör vara webbplatsen [för produktens livscykel.](/lifecycle/products/?alpha=Microsoft+Office+SharePoint+Server+2007) Om du har en lokal Microsoft-produkt som är föråldrings, kontrollera dess slutdatum för supporten så att du har ett år eller så för att schemalägga en uppgradering eller migrering. När du väljer nästa steg bör du fundera över vilka produktfunktioner som skulle vara tillräckligt bra, bättre och bästa. Här är ett exempel: 
  
|**Bra**|**Bättre**|**Bäst**|
|:-----|:-----|:-----|
|SharePoint Server 2010  <br/> |SharePoint Server 2013  <br/> |SharePoint Online  <br/> |
||SharePoint Hybrid  <br/> |SharePoint Server 2016  <br/> |
| | |SharePoint Hybrid  <br/> |
   
Om du väljer ett alternativ som "tillräckligt bra" kommer du snart att behöva börja planera för en ny uppgradering efter att migreringen från SharePoint Server 2007 har slutförts. 

>[!NOTE] 
>Datum för slutet på supporten kan komma att ändras. Kontrollera webbplatsen [för produktens livscykel.](https://support.microsoft.com/lifecycle)
  
## <a name="where-can-i-go-next"></a>Var hittar jag nästa steg?

SharePoint Server kan installeras lokalt på dina egna servrar. Du kan också använda SharePoint Online, som är en onlinetjänst som ingår i Microsoft 365. Alternativen är:
  
- Migrera till SharePoint Online.
    
- Uppgradera SharePoint Server lokalt.
    
- Gör båda ovanstående.
    
- Implementera en [SharePoint-hybridlösning.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
    
Tänk på dolda kostnader som gäller underhåll av en servergrupp, underhåll eller migrering av anpassningar och uppgradering av maskinvara som krävs för SharePoint Server. Att ha en lokal SharePoint-servergrupp är bra om det behövs. Men om du kör servergruppen på äldre SharePoint-servrar utan tung anpassning kan du dra nytta av migreringen till SharePoint Online.
  
> [!IMPORTANT]
> Det finns ett annat alternativ om innehållet i SharePoint 2007 används sällan. Vissa SharePoint-administratörer väljer att skapa en Microsoft 365-prenumeration, konfigurera en ny SharePoint Online-webbplats och sedan rensa SharePoint 2007 och ta endast viktiga dokument till de nya SharePoint Online-webbplatserna. Data kan sedan tömmas från SharePoint 2007-webbplatsen till arkiven. Fundera över hur användarna arbetar med data från din SharePoint 2007-installation. Det kan finnas kreativa sätt att hantera dina behov.
  
|**SharePoint Online (SPO)**|**SharePoint Server lokalt**|
|:-----|:-----|
|Hög kostnad i tid (plan/körning/verifiering)  <br/> |Hög kostnad i tid (plan/körning/verifiering)  <br/> |
|Lägre kostnad i pengar (inga maskinvaruinköp)  <br/> |Högre kostnad i pengar (maskinvara + devs/admins)  <br/> |
|One-time cost in migration  <br/> |Upprepad kostnad vid framtida migreringar  <br/> |
|Låg total kostnad för ägande/underhåll  <br/> |Hög total kostnad för ägande/underhåll  <br/> |
   
När du migrerar till Microsoft 365 får du en högre kostnad vid flytten, medan du organiserar data och bestämmer vad som ska flyttas till molnet och vad som ska bli kvar. Men framtida uppgraderingar kommer att ske automatiskt och du behöver inte längre hantera maskinvaru- och programvaruuppdateringar. Drifttiden för servergruppen backas också upp genom ett[SLA](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)(Microsoft Service Level Agreement).
  
### <a name="migrate-to-sharepoint-online"></a>Migrera till SharePoint Online

Kontrollera att SharePoint Online har alla de funktioner du behöver. Se [Tjänstbeskrivningar för Microsoft 365 och Office 365.](/office365/servicedescriptions/office-365-service-descriptions-technet-library)
  
Du kan inte migrera direkt från SharePoint 2007 till SharePoint Online. Flytten till SharePoint Online gjordes manuellt. Om du uppgraderar till SharePoint Server 2013 eller SharePoint Server 2016 kan du använda migrerings-API:t för SharePoint (till exempel för att migrera information till OneDrive för företag).
  
|**Online-proffs**|**Online-con**|
|:-----|:-----|
|Microsoft tillhandahåller SPO-maskinvara och all maskinvaruadministration.  <br/> |Tillgängliga funktioner kan skilja sig mellan SharePoint Server lokalt och SPO.  <br/> |
|Du är global administratör för prenumerationen och kan tilldela administratörer till SPO-webbplatser.  <br/> |Vissa åtgärder som är tillgängliga för en servergruppsadministratör i SharePoint Server lokalt finns inte eller ingår inte nödvändigtvis i administratörsrollen för SharePoint i Microsoft 365.  <br/> |
|Microsoft tillämpar korrigeringar, korrigeringar och uppdateringar för underliggande maskinvara och programvara. <br/> |Eftersom det inte finns åtkomst till det underliggande filsystemet i tjänsten är anpassningen begränsad.  <br/> |
|Microsoft publicerar [serviceavtal och flyttar](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement) snabbt för att lösa problem på tjänstnivå. <br/> |Säkerhetskopiering och återställning och andra återställningsalternativ automatiseras av tjänsten i SharePoint Online. Säkerhetskopior skrivs över om de inte används. <br/> |
|Säkerhetstestning och serverprestandajustering utförs kontinuerligt i tjänsten av Microsoft. <br/> |Ändringar av användargränssnittet och andra SharePoint-funktioner installeras av tjänsten och kan behöva vara på eller av. <br/> |
|Microsoft 365 uppfyller många branschstandarder: [Microsofts efterlevnadserbjudanden](/compliance/regulatory/offering-home).  <br/> |[FastTrack-hjälp](https://www.microsoft.com/fasttrack/microsoft-365) för migrering är begränsad.  <br/> Mycket av uppgraderingen sker manuellt eller via SPO-migrerings-API:t som beskrivs i översikten över innehållsmigrering i [SharePoint Online och OneDrive.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)  <br/> |
|Microsofts supporttekniker och anställda på datacenter har inte obegränsad administratörsåtkomst till prenumerationen. <br/> |Det kan till exempel bli ytterligare kostnader om maskinvaran behöver uppgraderas för att stödja den nyare versionen av SharePoint, eller om en sekundär servergrupp krävs för uppgraderingen.  <br/> |
|Partner kan hjälpa till med det lediga jobbet att migrera dina data till SharePoint Online.  <br/> ||
|Onlineprodukter uppdateras automatiskt. Även om funktionerna kanske förfasas finns det inget verkligt stöd. <br/> ||
   
Om du har bestämt dig för att skapa en ny Microsoft 365-webbplats och manuellt migrerar data till den efter behov, kontrollerar du dina [Microsoft 365-alternativ.](https://www.microsoft.com/microsoft-365/)
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Uppgradera SharePoint Server lokalt

Det går inte att hoppa över versioner i SharePoint-uppgraderingar. Uppgraderingarna går serien igenom:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Om du går över från SharePoint 2007 till SharePoint Server 2016 innebär det betydande investeringar i tid och kostnader inom maskinvara (SQL-servrar måste också uppgraderas), programvara och administration. Anpassningar måste uppgraderas eller tas bort.
  
> [!NOTE]
> Det är möjligt att behålla din livscykel för SharePoint 2007-servergruppen, installera en SharePoint Server 2016-servergrupp på ny maskinvara (så att de separata servergruppen körs sida vid sida) och sedan planera och utföra en manuell migrering av innehåll (till exempel för att ladda ned och ladda upp innehåll på nytt). Men var försiktig med vissa fallgropar vid manuella flyttningar, till exempel att dokument flyttas och att kontot för senaste ändring ersätts med alias för kontot som utför den manuella flytten. Tänk också på det arbete som måste göras i förväg, t.ex. att återskapa webbplatser, underwebbplatser, behörigheter och liststrukturer. Fundera på i förväg vilka data du kan flytta till lagring eller ta bort för att minska påverkan på migreringen.
  
Det är viktigt att rensa miljön innan du uppgraderar. Se till att din befintliga servergrupp fungerar innan du uppgraderar, och absolut innan du inaktiverar den!
  
Kom ihåg att granska *de uppgraderingsvägar som stöds och inte stöds:* 
  
- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
Om du har anpassningar är det viktigt att ha en plan för varje steg i migreringsprocessen: 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**Lokalt proffs**|**Lokal con**|
|:-----|:-----|
|Fullständig kontroll över alla aspekter av SharePoint-servergruppen, allt från servermaskinvara och uppåt.  <br/> |Alla avbrott och korrigeringar ansvarar ditt företag för (du kan kontakta betald Microsoft-support om din produkt inte har gått ut).  <br/> |
|Fullständig funktionsuppsättning i SharePoint Server lokalt med alternativet att ansluta den lokala servergruppen till en SharePoint Online-prenumeration via hybrid.  <br/> |Uppgraderingar, korrigeringar, säkerhetskorrigeringar och allt underhåll av SharePoint Server hanteras lokalt.  <br/> |
|Fullständig åtkomst för större anpassning.  <br/> |[Microsofts efterlevnadserbjudanden](/compliance/regulatory/offering-home) måste konfigureras manuellt lokalt.  <br/> |
|Säkerhetstestning och serverprestandajustering utförs lokalt (under din kontroll).  <br/> |Microsoft 365 kan göra funktioner tillgängliga för SharePoint Online som inte fungerar tillsammans med SharePoint Server lokalt.  <br/> |
|Partner kan hjälpa till med migreringen av data till nästa version av SharePoint Server (och vidare till nästa).  <br/> |Dina SharePoint Server-webbplatser använder inte automatiskt [SSL-/TLS-certifikat](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) som visas i SharePoint Online.  <br/> |
|Fullständig kontroll över namnkonventioner, återställning och andra återställningsalternativ i SharePoint Server lokalt.  <br/> |SharePoint Server lokalt är känsligt för produkternas livscykler.  <br/> |
   
### <a name="upgrade-resources"></a>Uppgradera resurser

Kontrollera att din miljö uppfyller maskinvaru- och programvarukrav och följ sedan uppgraderingsmetoder som stöds.
  
- **Maskin-/programvarukrav för:** 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **Programvarubegränsningar för:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **En översikt över uppgraderingsprocessen för:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Skapa en SharePoint-hybridlösning mellan SharePoint Online och en lokal miljö

Om svaret på dina behov för migrering ligger någonstans mitt emellan den lokala datorns självkontroll och den lägre ägandekostnaden som erbjuds med SharePoint Online, kan du ansluta SharePoint Server 2013- eller 2016-servergrupper till SharePoint Online via hybrider. [Läs mer om SharePoint-hybridlösningar.](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Om du anser att en SharePoint Server-hybridservergrupp kan dra nytta av ditt företag bör du läsa mer om de befintliga hybridtyperna och hur du konfigurerar anslutningen mellan den lokala SharePoint-servergruppen och Microsoft 365-prenumerationen.
  
| Alternativ | Beskrivning |
|:-----|:-----|
[Efterlevnadserbjudanden från Microsoft](/compliance/regulatory/offering-home)  <br/> |[FastTrack-hjälp](https://www.microsoft.com/fasttrack/microsoft-365) för migrering är begränsad.  <br/> Mycket av uppgraderingen sker manuellt eller via SPO-migrerings-API:t som beskrivs i översikten över innehållsmigrering i [SharePoint Online och OneDrive.](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)  <br/> |
|Microsofts supporttekniker och anställda på datacentret har inte obegränsad administratörsåtkomst till din prenumeration.<br/> |Det kan till exempel bli ytterligare kostnader om maskinvaruinfrastrukturen måste uppgraderas för att stödja den nyare versionen av SharePoint, eller om en sekundär servergrupp krävs för uppgraderingen.  <br/> |
|Partner kan hjälpa till med det lediga jobbet att migrera dina data till SharePoint Online.  <br/> ||
|Onlineprodukter uppdateras automatiskt i tjänsten. Funktionerna kanske förfasas, men det finns inget verkligt stöd.<br/> ||
   
Om du har bestämt dig för att skapa en ny Microsoft 365-webbplats och manuellt migrerar data till den efter behov, kontrollerar du dina [Microsoft 365-alternativ.](https://www.microsoft.com/microsoft-365/)
  
### <a name="upgrade-sharepoint-server-on-premises"></a>Uppgradera SharePoint Server lokalt

Det går inte att hoppa över versioner i SharePoint-uppgraderingar. Uppgraderingarna går serien igenom:
  
- SharePoint 2007 \> SharePoint Server 2010 \> SharePoint Server 2013 \> SharePoint Server 2016
   
Om du går över från SharePoint 2007 till SharePoint Server 2016 innebär det betydande investeringar i tid och kostnader för maskinvara (SQL-servrar måste också uppgraderas), programvara och administration. Anpassningar måste uppgraderas eller tas bort.
  
> [!NOTE]
> Det är möjligt att behålla din livscykel för SharePoint 2007-servergruppen, installera en SharePoint Server 2016-servergrupp på ny maskinvara (så att de separata servergruppen körs sida vid sida) och sedan planera och utföra en manuell migrering av innehåll (till exempel för att ladda ned och ladda upp innehåll på nytt). Men var uppmärksam på potentiella fallgropar vid manuella flyttningar, t.ex. att flytta dokument och ersätta kontot med alias för det konto som utför den manuella flytten, och det arbete som måste göras i förväg, till exempel återskapa webbplatser, underwebbplatser, behörigheter och liststrukturer. Fundera på vilka data du kan flytta till lagring eller ta bort för att minska påverkan på migreringen.
  
Rensa miljön innan du uppgraderar. Se till att din befintliga servergrupp fungerar innan du uppgraderar och verkligen innan du inaktiverar den! 
  
Kom ihåg att granska *de uppgraderingsvägar som stöds och inte stöds:* 
  
- [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262747(v=office.12))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/review-supported-editions-and-products-for-upgrading-to-sharepoint-2013)
    
Om du *har anpassningar är* det viktigt att du har en plan för uppgraderingen för varje steg i migreringsprocessen: 
  
- [SharePoint 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc263203(v=office.12))
    
- [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc263203(v=office.14))
    
- [SharePoint Server 2013](/SharePoint/upgrade-and-update/create-a-communication-plan-for-the-upgrade-to-sharepoint-2013)
    
|**Lokalt pro**|**Lokal con**|
|:-----|:-----|
|Fullständig kontroll över alla aspekter av SharePoint-servergruppen, allt från servermaskinvara och uppåt.  <br/> |Alla avbrott och korrigeringar ansvarar ditt företag för. (Du kan delta i betald Microsoft Support om din produkt inte har supporten gått ut.)  <br/> |
|Fullständig funktionsuppsättning i SharePoint Server lokalt med alternativet att ansluta den lokala servergruppen till en SharePoint Online-prenumeration via hybrid.  <br/> |Uppgraderingar, korrigeringar, säkerhetskorrigeringar och allt underhåll av SharePoint Server hanteras lokalt.  <br/> |
|Fullständig åtkomst för större anpassning.  <br/> |[Microsofts efterlevnadserbjudanden](/compliance/regulatory/offering-home) måste konfigureras manuellt lokalt.  <br/> |
|Säkerhetstestning och serverprestandajustering utförs lokalt under din kontroll.  <br/> |Microsoft 365 kan göra funktioner tillgängliga för SharePoint Online som inte fungerar tillsammans med SharePoint Server lokalt  <br/> |
|Partner kan hjälpa till att migrera data till nästa version av SharePoint Server (och därefter).  <br/> |Dina SharePoint Server-webbplatser använder inte [automatiskt SSL-/TLS-certifikat](/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016) som visas i SharePoint Online.  <br/> |
|Fullständig kontroll över namnkonventioner, återställning och andra återställningsalternativ i SharePoint Server lokalt.  <br/> |SharePoint Server lokalt är känsligt för produkternas livscykler.  <br/> |
   
### <a name="upgrade-resources"></a>Uppgradera resurser

Kontrollera att miljön uppfyller maskinvaru- och programvarukraven. Följ sedan de uppgraderingsmetoder som stöds.
  
- **Maskin-/programvarukrav för:** 
    
    [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262485(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/hardware-and-software-requirements-0)  |  [SharePoint Server 2016](/SharePoint/install/hardware-and-software-requirements)
    
- **Programvarubegränsningar för:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262787(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc262787(v=office.14))  |  [SharePoint Server 2013](/SharePoint/install/software-boundaries-and-limits)  |  [SharePoint Server 2016](/SharePoint/install/software-boundaries-and-limits-0)
    
- **En översikt över uppgraderingsprocessen för:** 
    
    [SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc303420(v=office.12))  |  [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc303420(v=office.14))  |  [SharePoint Server 2013](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)  |  [SharePoint Server 2016](/SharePoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
    
### <a name="create-a-sharepoint-hybrid-solution-between-sharepoint-online-and-on-premises"></a>Skapa en SharePoint-hybridlösning mellan SharePoint Online och en lokal miljö

Om svaret på dina behov för migrering ligger någonstans mitt emellan den lokala datorns självkontroll och den lägre ägandekostnaden som erbjuds med SharePoint Online, kan du ansluta SharePoint Server 2013- eller 2016-servergrupper till SharePoint Online via hybrider. [Läs mer om SharePoint-hybridlösningar](https://support.office.com/article/4c89a95a-a58c-4fc1-974a-389d4f195383.aspx)
  
Om du anser att en SharePoint Server-hybridservergrupp kan dra nytta av ditt företag bör du läsa mer om de befintliga hybridtyperna och hur du konfigurerar anslutningen mellan den lokala SharePoint-servergruppen och Microsoft 365-prenumerationen.
  
Ett bra sätt att se hur det fungerar är att skapa en utvecklings-/testmiljö för Microsoft 365 som du kan konfigurera med [testlabbguider.](m365-enterprise-test-lab-guides.md) När du har fått en utvärderingsversion eller har köpt en Microsoft 365-prenumeration kan du skapa webbplatssamlingar, webbplatser och dokumentbibliotek i SharePoint Online som du kan migrera data till. Du kan migrera manuellt med hjälp av migrerings-API:t eller, om du vill migrera Innehållet på Min webbplats till OneDrive för företag, via hybridguiden.
  
> [!NOTE]
> Kom ihåg att om du vill använda hybridalternativet måste SharePoint 2007-servergruppen uppgraderas, lokalt, till antingen SharePoint Server 2013 eller SharePoint Server 2016.
  
## <a name="related-topics"></a>Relaterade ämnen

[Felsöka och återuppta uppgradering (Office SharePoint Server 2007)](/previous-versions/office/sharepoint-2007-products-and-technologies/cc262967(v=office.12))
  
[Felsöka uppgraderingsproblem (SharePoint Server 2010)](/previous-versions/office/sharepoint-server-2010/cc262967(v=office.14))
  
[Felsöka problem med databasuppgradering i SharePoint 2013](/SharePoint/upgrade-and-update/troubleshoot-database-upgrade-issues-in-sharepoint-2013)
  
[Sök efter Microsoft-partner som kan hjälpa dig med uppgraderingen](https://go.microsoft.com/fwlink/?linkid=841249)
  
[Resurser som hjälper dig att uppgradera från Office 2007-servrar och -klienter](upgrade-from-office-2007-servers-and-products.md)
