---
title: SharePoint Server 2013 katastrofåterställning i Microsoft Azure
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 04/17/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Deployment
- seo-marvel-apr2020
ms.assetid: e9d14cb2-ff28-4a18-a444-cebf891880ea
description: I den här artikeln beskrivs hur du använder Azure för att skapa en katastrofåterställningsmiljö för den lokala SharePoint-servergruppen.
ms.openlocfilehash: 01a49cfa19711caa36190a795792635431dd7d04
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907438"
---
# <a name="sharepoint-server-2013-disaster-recovery-in-microsoft-azure"></a>SharePoint Server 2013 katastrofåterställning i Microsoft Azure

 Med Azure kan du skapa en katastrofåterställningsmiljö för den lokala SharePoint-servergruppen. I den här artikeln beskrivs hur du utformar och implementerar den här lösningen.

 **Titta på översiktsvideon om katastrofåterställning i SharePoint Server 2013**
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1b73ec8f-29bd-44eb-aa3a-f7932784bfd9?autoplay=false]
  
 När katastrofen slår till i din lokala SharePoint-miljö är din högsta prioritet att få igång systemet snabbt igen. Katastrofåterställning med SharePoint går snabbare och enklare när du har en säkerhetskopieringsmiljö som redan körs i Microsoft Azure. Den här videon förklarar huvudbegreppen i en varmt redundansmiljö i SharePoint och kompletterar den fullständiga informationen som finns i den här artikeln.
  
Använd den här artikeln med följande lösningsmodell: **SharePoint Katastrofåterställning i Microsoft Azure**.
  
[![SharePoint-process för katastrofåterställning till Azure](../media/SP-DR-Azure.png)](https://go.microsoft.com/fwlink/p/?LinkId=392555)
  
 [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555) |  [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)
  
## <a name="use-azure-infrastructure-services-for-disaster-recovery"></a>Använda Azure-infrastrukturtjänster för katastrofåterställning

Många organisationer har inte en katastrofåterställningsmiljö för SharePoint, vilket kan vara dyrt att skapa och underhålla lokalt. Azure-infrastrukturtjänsterna tillhandahåller lockande alternativ för katastrofåterställningsmiljöer som är mer flexibla och billigare än de lokala alternativen.
  
Fördelarna med att använda Azure-infrastrukturtjänster är:
  
- **Färre dyrbara resurser** Underhålla och betala för färre resurser än lokala katastrofåterställningsmiljöer. Antalet resurser beror på vilken katastrofåterställningsmiljö du väljer: kall vänteläge, varmt vänteläge eller vänteläge.
    
- **Bättre flexibilitet för resurser** Vid en katastrof kan du enkelt skala ut din SharePoint-servergrupp för återställning så att den uppfyller inläsningskraven. Skala in när du inte längre behöver resurserna.
    
- **Lägre datacenteråtagande** Använd Azure Infrastructure Services i stället för att investera i ett sekundärt datacenter i en annan region.
    
Det finns mindre komplexa alternativ för organisationer som precis har börjat med katastrofåterställning och avancerade alternativ för organisationer med krav på hög motståndskraft. Definitionerna för kalla, varmt och varmt väntemiljöer är lite annorlunda när miljön är värd för en molnplattform. I följande tabell beskrivs de här miljöerna för att skapa en SharePoint-återställningsfarm i Azure.
  
**Tabell: Återställningsmiljöer**

|**Typ av återställningsmiljö**|**Beskrivning**|
|:-----|:-----|
|Hot  <br/> |En servergrupp i fullständig storlek är etablerat, uppdaterat och körs i vänteläge.  <br/> |
|Uppvärmning  <br/> |Servergruppen är uppbyggd och virtuella datorer körs och uppdateras.  <br/> Återställning omfattar att bifoga innehållsdatabaser, etablera tjänstprogram och crawla innehåll.  <br/> Servergruppen kan vara en mindre version av produktionsfarmen och sedan skalas ut så att den används i hela användarbasen.  <br/> |
|Kall  <br/> |Servergruppen är helt inbyggd, men de virtuella maskinerna stoppas.  <br/> Underhåll av miljön omfattar att starta virtuella maskiner då och då, korrigera, uppdatera och verifiera miljön.  <br/> Starta hela miljön vid en katastrof.  <br/> |
   
Det är viktigt att utvärdera organisationens mål för återställningstid (RTOs) och återställningspunktmål (RPOs). De här kraven avgör vilken miljö som är bäst för investeringen i organisationen.
  
I vägledning i den här artikeln beskrivs hur du implementerar en vänteläge för uppvärmning. Du kan även anpassa den till en miljö med isigt vänteläge, även om du måste följa ytterligare procedurer för att stödja den här typen av miljö. I den här artikeln beskrivs inte hur du implementerar snabb vänteläge.
  
Mer information om lösningar för katastrofåterställning finns i Begrepp för hög tillgänglighet och katastrofåterställning i [SharePoint 2013](/SharePoint/administration/high-availability-and-disaster-recovery-concepts) och Välj en katastrofåterställningsstrategi för [SharePoint 2013.](/SharePoint/administration/plan-for-disaster-recovery)
  
## <a name="solution-description"></a>Lösningsbeskrivning

Lösningen för katastrofåterställning av varmt vänteläge kräver följande miljö:
  
- En lokal SharePoint-produktionsgrupp
    
- En SharePoint-återställningsfarm i Azure
    
- En VPN-anslutning mellan de två miljöerna
    
Följande bild illustrerar dessa tre element.
  
**Bild: Element i en väntelösning för varmt vänteläge i Azure**

![Element i en lösning för varmt vänteläge i SharePoint i Azure](../media/AZarch-AZWarmStndby.png)
  
SQL Server-loggleverans med Distributed File System Replication (REPLICATION) används för att kopiera databasbackuper och transaktionsloggar till återställningsfarmen i Azure: 
  
- TIDFJÄR överför loggar från produktionsmiljön till återställningsmiljön. I ett WAN-scenario är DET mer effektivt att SKICKA LOGGARna direkt till den sekundära servern i Azure än att skicka dem.
    
- Loggar spelas upp till SQL Server i återställningsmiljön i Azure.
    
- Du bifogar inte sharePoint-innehållsdatabaser med logg som levererats i återställningsmiljön förrän en återställningsövning utförs.
    
Så här återställer du servergruppen:
  
1. Stoppa loggleveransen.
    
2. Sluta att acceptera trafik till den primära servergruppen.
    
3. Spela upp de slutliga transaktionsloggarna.
    
4. Koppla innehållsdatabaserna till servergruppen.
    
5. Återställa tjänstprogram från replikerade tjänstdatabaser.
    
6. Uppdatera DNS-poster (Domain Name System) så att de pekar på återställningsfarmen.
    
7. Påbörja en fullständig crawlning.
    
Vi rekommenderar att du provar de här stegen regelbundet och dokumenterar dem för att säkerställa att live-återställningen körs smidigt. Det kan ta lite tid att bifoga innehållsdatabaser och återställa tjänstprogram, vilket vanligtvis omfattar en del manuell konfiguration.
  
När en återställning har utförts innehåller den här lösningen de objekt som anges i följande tabell.
  
**Tabell: Lösningsåterställningsmål**

|**Objekt**|**Beskrivning**|
|:-----|:-----|
|Webbplatser och innehåll  <br/> |Webbplatser och innehåll är tillgängliga i återställningsmiljön.  <br/> |
|En ny förekomst av sökning  <br/> |I den här lösningen för varmt vänteläge återställs inte sökningen från sökdatabaser. Sökkomponenter i återställningsfarmen konfigureras så som möjligt till produktionsfarmen. När webbplatserna och innehållet har återställts har en fullständig crawlning påbörjats för att återskapa sökindexet. Du behöver inte vänta på att crawlningen ska slutföras för att göra webbplatser och innehåll tillgängliga.  <br/> |
|Tjänster  <br/> | Tjänster som lagrar data i databaser återställs från log-shipped-databaserna. Tjänster som inte lagrar data i databaser startas bara. <br/>  Alla tjänster med databaser behöver inte återställas. Följande tjänster behöver inte återställas från databaser och kan bara startas efter redundans: <br/>  Insamling av användnings- och hälsodata <br/>  Delstatstjänst <br/>  Word-automation <br/>  Andra tjänster som inte använder en databas <br/> |
   
Du kan samarbeta med Microsoft Consulting Services (MCS) eller en partner för att ta itu med mer komplexa återställningsmål. Dessa sammanfattas i följande tabell.
  
**Tabell: Andra objekt som kan adresseras av MCS eller en partner**

|**Objekt**|**Beskrivning**|
|:-----|:-----|
|Synkronisera anpassade servergruppslösningar  <br/> |Under idealiska idealiska är konfigurationen av återställningsfarmen identisk med produktionsfarmen. Du kan samarbeta med en konsult eller partner för att utvärdera om anpassade servergruppslösningar replikeras och om processen finns för att synkronisera de två miljöerna.  <br/> |
|Anslutningar till datakällor lokalt  <br/> |Det kanske inte är praktiskt att replikera anslutningar till backend-datasystem, till exempel anslutningar för säkerhetskopieringsdomänkontrollant (BDC) och söka i innehållskällor.  <br/> |
|Sökåterställningsscenarier  <br/> |Eftersom företagssökningsdistributioner brukar vara relativt unika och komplexa krävs det större investeringar i återställning av sökning från databaser. Du kan arbeta med en konsult eller partner för att identifiera och implementera sökåterställningsscenarier som din organisation kan behöva.  <br/> |
   
Vägledningen i den här artikeln förutsätter att den lokala servergruppen redan är utformad och distribuerad.
  
## <a name="detailed-architecture"></a>Detaljerad arkitektur

Under idealiska förutsättningar är konfigurationen av återställningsfarmen i Azure identisk med den lokala produktionsfarmen, inklusive följande:
  
- Samma representation av serverroller
    
- Samma konfiguration av anpassningar
    
- Samma konfiguration av sökkomponenter
    
Miljön i Azure kan vara en mindre version av produktionsfarmen. Om du planerar att skala ut återställningsfarmen efter redundans är det viktigt att varje typ av serverroll först representeras.
  
Vissa konfigurationer kanske inte är praktiska att replikera i redundansmiljön. Se till att testa redundansprocedurerna och miljön för att säkerställa att redundansfarmen tillhandahåller den förväntade tjänstnivån.
  
Den här lösningen kräver inte en viss topologi för en SharePoint-servergrupp. Fokus för den här lösningen är att använda Azure för redundansfarmen och att implementera loggleverans och TIDER mellan de två miljöerna.
  
### <a name="warm-standby-environments"></a>Uppvärmningsmiljöer för vänteläge

I en varma väntelägesmiljö körs alla virtuella datorer i Azure-miljön. Miljön är redo för en redundansövning eller händelse.
  
På följande bild visas en katastrofåterställningslösning från en lokal SharePoint-servergrupp till en Azure-baserad SharePoint-servergrupp som är konfigurerad som en uppvärmningsmiljö för vänteläge.
  
**Bild: Topologi och viktiga element i en produktionsfarm och en servergrupp för uppvärmningsåterställning**

![Topologi för En SharePoint-servergrupp och en servergrupp för vänteläge för uppvärmning](../media/AZarch-AZWarmStndby.png)
  
I det här diagrammet:
  
- Två miljöer illustreras sida vid sida: den lokala SharePoint-servergruppen och servergruppen för uppvärmning i Azure.
    
- Varje miljö innehåller en filresurs.
    
- Varje servergrupp innehåller fyra nivåer. För att uppnå hög tillgänglighet inkluderar varje nivå två servrar eller virtuella datorer som är konfigurerade identiskt för en viss roll, till exempel frontend-tjänster, distribuerad cache, backend-tjänster och databaser. I den här illustrationen är det inte viktigt att visa upp specifika komponenter. De två grupper är konfigurerade identiskt.
    
- Den fjärde nivån är databasnivån. Loggleverans används för att kopiera loggar från den sekundära databasservern i den lokala miljön till filresursen i samma miljö.
    
- INFILTR kopierar filer från filresursen i den lokala miljön till filresursen i Azure-miljön.
    
- Loggleveransen spelar upp loggarna från filresursen i Azure-miljön till den primära kopian i tillgänglighetsgruppen för SQL Server AlwaysOn i återställningsmiljön.
    
### <a name="cold-standby-environments"></a>Miljöer för vänteläge vid kalla miljöer

I en miljö med kalla vänteläge kan de flesta virtuella SharePoint-servergruppens maskiner stängas av. (Vi rekommenderar att du ibland startar virtuella maskiner, till exempel varannan vecka eller en gång i månaden, så att varje virtuell dator kan synkronisera med domänen.) Följande virtuella datorer i Azure-återställningsmiljön måste fortsätta köras för att säkerställa kontinuerlig leverans av logg och SÅ ATT::
  
- Filresursen
    
- Primär databasserver
    
- Minst en virtuell dator med Windows Server Active Directory Domain Services och DNS
    
På följande bild visas en Azure-redundansmiljö där filresursen virtuella datorn och den primära virtuella SharePoint-databasen körs. Alla andra virtuella SharePoint-datorer stoppas. Den virtuella datorn med Windows Server Active Directory och DNS visas inte.
  
**Bild: Servergrupp för återställning av isigt vänteläge med virtuella maskiner**

![Element i en SharePoint-lösning för isigt vänteläge i Azure](../media/AZarch-AZColdStndby.png)
  
Efter redundans i en miljö med kalla vänteläge startas alla virtuella maskiner och metoden för att få hög tillgänglighet till databasservrarna måste konfigureras, till exempel SQL Server AlwaysOn-tillgänglighetsgrupper.
  
Om flera lagringsgrupper implementeras (databaser är utspridda över mer än en uppsättning med hög tillgänglighet i SQL Server) måste den primära databasen för varje lagringsgrupp köras för att acceptera loggarna som är kopplade till dess lagringsgrupp.
  
### <a name="skills-and-experience"></a>Kunskaper och erfarenhet

Flera tekniker används i den här katastrofåterställningslösningen. För att säkerställa att dessa tekniker interagerar som förväntat måste varje komponent i den lokala miljön och Azure-miljön installeras och konfigureras korrekt. Vi rekommenderar att den person eller det team som skapar den här lösningen har starka kunskaper om och praktiska kunskaper med de tekniker som beskrivs i följande artiklar:
  
- [Distributed File System (REPLICATION) Replication Services](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11))
    
- [Windows Server Failover Clustering (WSFC) med SQL Server](/sql/sql-server/failover-clusters/windows/windows-server-failover-clustering-wsfc-with-sql-server)
    
- [AlwaysOn-tillgänglighetsgrupper (SQL Server)](/sql/database-engine/availability-groups/windows/always-on-availability-groups-sql-server)
    
- [Bakåt och återställning av SQL Server-databaser](/sql/relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases)
    
- [Installation och servergruppsdistribution av SharePoint Server 2013](/SharePoint/install/installation-and-configuration-overview)
    
- [Microsoft Azure](/azure/)
    
Slutligen rekommenderar vi skriptfärdigheter som du kan använda för att automatisera uppgifter som associeras med dessa tekniker. Det går att använda de tillgängliga användargränssnitten för att slutföra alla uppgifter som beskrivs i den här lösningen. En manuell metod kan dock vara tidskrävande och felbenägen och ger inkonsekventa resultat.
  
Utöver Windows PowerShell finns även Windows PowerShell-bibliotek för SQL Server, SharePoint Server och Azure. Kom ihåg T-SQL, som också kan hjälpa dig att minska tiden för att konfigurera och underhålla din katastrofåterställningsmiljö.
  
## <a name="disaster-recovery-roadmap"></a>Översikt över katastrofåterställning

![Visuell representation av översikt över katastrofåterställning i SharePoint.](../media/Azure-DRroadmap.png)
  
Den här översikten förutsätter att du redan har en SharePoint Server 2013-servergrupp distribuerad i produktion.
  
**Tabell: Översikt över katastrofåterställning**

|**Fas**|**Beskrivning**|
|:-----|:-----|
|Fas 1  <br/> |Utforma katastrofåterställningsmiljön.  <br/> |
|Fas 2  <br/> |Skapa det virtuella Azure-nätverket och VPN-anslutningen.  <br/> |
|Fas 3  <br/> |Distribuera Windows Active Directory och Domain Name Services till det virtuella Azure-nätverket.  <br/> |
|Fas 4  <br/> |Distribuera SharePoint-återställningsfarmen i Azure.  <br/> |
|Fas 5  <br/> |Konfigurera TIDER mellan olika farmar.  <br/> |
|Fas 6  <br/> |Konfigurera loggleveransen till återställningsfarmen.  <br/> |
|Fas 7  <br/> | Verifiera redundans- och återställningslösningar. Detta omfattar följande metoder och tekniker: <br/>  Stoppa loggleveransen. <br/>  Återställ säkerhetskopiorna. <br/>  Crawla innehåll. <br/>  Återställ tjänster. <br/>  Hantera DNS-poster. <br/> |
   
## <a name="phase-1-design-the-disaster-recovery-environment"></a>Fas 1: Utforma katastrofåterställningsmiljön

Använd vägledning [i Microsoft Azure-arkitekturer för SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) för att utforma katastrofåterställningsmiljön, inklusive SharePoint-återställningsfarmen. Du kan starta designprocessen med hjälp av grafiken i [SharePoint Disaster Recovery Solution i Azure](https://go.microsoft.com/fwlink/p/?LinkId=392554) Visio-filen. Vi rekommenderar att du utformar hela miljön innan du börjar arbeta i Azure-miljön.
  
Förutom vägledningen i [Microsoft Azure-arkitekturer för SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) om utformning av virtuellt nätverk, VPN-anslutning, Active Directory och SharePoint-servergruppen är det bra om du lägger till en filresursroll i Azure-miljön.
  
För att det ska gå att skicka loggen i en katastrofåterställningslösning läggs en filresurs virtuella dator till i undernätet där databasrollerna finns. Filresursen fungerar också som den tredje noden i en nodmaitet för tillgänglighetsgruppen SQL Server AlwaysOn. Det här är den rekommenderade konfigurationen för en vanlig SharePoint-servergrupp som använder tillgänglighetsgrupper i SQL Server AlwaysOn. 
  
> [!NOTE]
> Det är viktigt att granska förutsättningarna för en databas att delta i en tillgänglighetsgrupp för SQL Server AlwaysOn. Mer information finns i [Krav, Begränsningar och rekommendationer för AlwaysOn-tillgänglighetsgrupper.](/sql/database-engine/availability-groups/windows/prereqs-restrictions-recommendations-always-on-availability) 
  
**Bild: Placering av en filserver som används för en katastrofåterställningslösning**

![Visar en filresurs vm som lagts till i samma molntjänst som innehåller SharePoint-databasserverrollerna.](../media/AZenv-FSforDFSRandWSFC.png)
  
I det här diagrammet läggs en filresurs virtuell dator till i samma undernät i Azure som innehåller databasserverrollerna. Lägg inte till den virtuella filresursen till en tillgänglighetsuppsättning med andra serverroller, till exempel SQL Server-roller.
  
Om du är orolig för den höga tillgängligheten för loggarna bör du överväga att använda en annan metod genom att använda säkerhetskopiering och återställning i [SQL Server med Blob Storage Service för Azure.](/sql/relational-databases/backup-restore/sql-server-backup-and-restore-with-microsoft-azure-blob-storage-service) Det här är en ny funktion i Azure som sparar loggar direkt till en URL för blob-lagring. Den här lösningen innehåller inte vägledning om hur du använder den här funktionen.
  
När du utformar en återställningsfarm ska du tänka på att en lyckad katastrofåterställningsmiljö återspeglar den produktionsgrupp som du vill återställa. Storleken på återställningsfarmen är inte det viktigaste i återställningsfarmens design, distribution och testning. Servergruppsskalan varierar från organisation till organisation baserat på företagskrav. Det kan vara möjligt att använda en nedskalade servergrupp för ett kort avbrott eller tills prestanda- och kapacitetskrav kräver att du skalar servergruppen.
  
Konfigurera återställningsfarmen så att den är identisk som möjligt för produktionsfarmen så att den uppfyller tjänstnivåkraven (SLA) och ger de funktioner du behöver för att stödja verksamheten. När du utformar en katastrofåterställningsmiljö kan du också titta på ändringshanteringsprocessen för produktionsmiljön. Vi rekommenderar att du utökar ändringshanteringsprocessen till återställningsmiljön genom att uppdatera återställningsmiljön med samma intervall som produktionsmiljön. Som en del av ändringshanteringsprocessen rekommenderar vi att du underhåller ett detaljerat lager av servergruppskonfigurationer, program och användare. 
  
## <a name="phase-2-create-the-azure-virtual-network-and-vpn-connection"></a>Fas 2: Skapa det virtuella Azure-nätverket och VPN-anslutningen

Anslut ett lokalt nätverk till ett virtuellt [Microsoft Azure-nätverk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md) som visar hur du planerar och distribuerar det virtuella nätverket i Azure och hur du skapar VPN-anslutningen. Följ vägledning i avsnittet för att slutföra följande procedurer:
  
- Planera det privata IP-adressutrymmet för det virtuella nätverket.
    
- Planera ändringar i routningsinfrastrukturen för det virtuella nätverket.
    
- Planera brandväggsregler för trafik till och från den lokala VPN-enheten.
    
- Skapa det virtuella korslokala nätverket i Azure.
    
- Konfigurera dirigering mellan ditt lokala nätverk och det virtuella nätverket.
    
## <a name="phase-3-deploy-active-directory-and-domain-name-services-to-the-azure-virtual-network"></a>Fas 3: Distribuera Active Directory och Domain Name Services till det virtuella Azure-nätverket

Den här fasen omfattar distribution av både Windows Server Active Directory och DNS till det virtuella nätverket i ett hybridscenario enligt beskrivningen i [Microsoft Azure Architectures for SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) och enligt följande bild.
  
**Bild: Hybridkonfiguration av Active Directory-domän**

![Två virtuella datorer som distribuerats till det virtuella Azure-nätverket och SharePoint-servergruppsundernätet är replikdomänkontroller och DNS-servrar](../media/AZarch-HyADdomainConfig.png)
  
I illustrationen distribueras två virtuella datorer till samma undernät. De här virtuella maskinerna har två roller: Active Directory och DNS.
  
Innan du distribuerar Active Directory i Azure bör [du läsa Riktlinjer för distribution av Windows Server Active Directory på virtuella Azure-datorer.](/windows-server/identity/ad-ds/introduction-to-active-directory-domain-services-ad-ds-virtualization-level-100) De här riktlinjerna hjälper dig att avgöra om du behöver en annan arkitektur eller olika konfigurationsinställningar för din lösning.
  
Detaljerad information om hur du installerar en domänkontrollant i Azure finns i [Installera en replica Active Directory-domänkontrollant i Virtuella Azure-nätverk.](/windows-server/identity/ad-ds/introduction-to-active-directory-domain-services-ad-ds-virtualization-level-100)
  
Före den här fasen distribuerade du inte virtuella maskiner till det virtuella nätverket. Virtuella datorer för värd för Active Directory och DNS är förmodligen inte de största virtuella maskinerna du behöver för lösningen. Innan du distribuerar de här virtuella maskinerna måste du skapa den största virtuella datorn som du planerar att använda i ditt virtuella nätverk. Det här säkerställer att din lösning hamnar på en tagg i Azure som har den största storlek du behöver. Du behöver inte konfigurera den här virtuella datorn för stunden. Skapa den och lägg undan den. Om du inte gör det kan du få en begränsning när du försöker skapa större virtuella maskiner senare, vilket var ett problem när den här artikeln skrevs. 
  
## <a name="phase-4-deploy-the-sharepoint-recovery-farm-in-azure"></a>Fas 4: Distribuera SharePoint-återställningsfarmen i Azure

Distribuera SharePoint-servergruppen i ditt virtuella nätverk enligt dina designplaner. Det kan vara bra att läsa [Planering för SharePoint 2013 på Azure-infrastrukturtjänster](/previous-versions/azure/dn275958(v=azure.100)) innan du distribuerar SharePoint-roller i Azure.
  
Tänk på följande metoder som vi lärde oss genom att bygga vår koncept konceptmiljö:
  
- Skapa virtuella datorer med hjälp av Azure-portalen eller PowerShell.
    
- Azure och Hyper-V stöder inte dynamiskt minne. Se till att detta tas med i dina prestanda- och kapacitetsplaner.
    
- Starta om virtuella datorer via Azure-gränssnittet, inte från den virtuella datorns inloggning. Användningen av Azure-gränssnittet fungerar bättre och blir mer förutsägbart.
    
- Om du vill stänga av en virtuell dator för att spara kostnader använder du Azure-gränssnittet. Om du stänger av inloggningen från den virtuella datorn fortsätter kostnaderna att påföras.
    
- Använd namnkonventioner för virtuella datorer.
    
- Var uppmärksam på vilken datacenterplats de virtuella maskinerna håller på att distribuera.
    
- Den automatiska skalningsfunktionen i Azure stöds inte för SharePoint-roller.
    
- Konfigurera inte objekt i servergruppen som ska återställas, till exempel webbplatssamlingar. 
    
## <a name="phase-5-set-up-dfsr-between-the-farms"></a>Fas 5: Konfigurera SÅ ATT DET BLIR EN 80:e dag mellan våra farmar

Om du vill konfigurera filreplikering med hjälp av TIDER använder du snapin-modulen DNS Management. Men innan SETUPR-installationen loggar du in på den lokala filservern och Azure-filservern och aktiverar tjänsten i Windows.
  
Slutför följande steg från instrumentpanelen för Serverhanteraren:
  
- Konfigurera den lokala servern.
    
- Starta guiden **Lägg till roller och funktioner.**
    
- Öppna **noden Fil- och lagringstjänster.**
    
- Välj **TIDErymd och** **REPLICATION-replikering**.
    
- Slutför **stegen i** guiden genom att klicka på Nästa.
    
Följande tabell innehåller länkar till REFERENSartiklar om TIDER och blogginlägg.
  
**Tabell: Referensartiklar för TIDER**

|**Title**|**Beskrivning**|
|:-----|:-----|
|[Replikering](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc770278(v=ws.11)) <br/> |IT-hantering – TechNet-ämne med länkar för replikering  <br/> |
|[REPLICATION Replication: Survival Guide](https://go.microsoft.com/fwlink/p/?LinkId=392737) <br/> |Wiki med länkar till WIKI-information  <br/> |
|[REPLICATION Replication: Frequently Asked Questions](/previous-versions/windows/it-pro/windows-server-2003/cc773238(v=ws.10)) <br/> |TECHNet-ämne för REPLICATION Replication  <br/> |
|[Jose Barretos blogg](/archive/blogs/josebda/) <br/> |Blogg som skrivits av en Principal Program Manager i File Server-teamet på Microsoft  <br/> |
|[Lagringsteamet på Microsoft – Blogg för arkivskåp](https://go.microsoft.com/fwlink/p/?LinkId=392740) <br/> |Blogg om filtjänster och lagringsfunktioner i Windows Server  <br/> |
   
## <a name="phase-6-set-up-log-shipping-to-the-recovery-farm"></a>Fas 6: Konfigurera loggleverans till återställningsfarmen

Loggleverans är den kritiska komponenten för att konfigurera katastrofåterställning i den här miljön. Du kan använda loggleverans för att automatiskt skicka transaktionsloggfiler för databaser från en primär databasserverinstans till en sekundär databasserverinstans. Information om hur du konfigurerar loggleverans [finns i Konfigurera loggleverans i SharePoint 2013.](/sharepoint/administration/configure-log-shipping) 
  
> [!IMPORTANT]
> Stöd för loggleverans i SharePoint Server är begränsat till vissa databaser. Mer information finns i Alternativ [för hög tillgänglighet och katastrofåterställning för SharePoint-databaser (SharePoint 2013).](/SharePoint/administration/supported-high-availability-and-disaster-recovery-options-for-sharepoint-databas) 
  
## <a name="phase-7-validate-failover-and-recovery"></a>Fas 7: Verifiera redundans och återställning

Syftet med den här sista fasen är att verifiera att katastrofåterställningslösningen fungerar som planerat. Det gör du genom att skapa en redundanshändelse som stänger produktionsfarmen och startar återställningsfarmen som en ersättning. Du kan starta ett redundansscenario manuellt eller med hjälp av skript.
  
Det första steget är att stoppa inkommande användarförfrågningar för servergruppstjänster eller -innehåll. Det kan du göra genom att inaktivera DNS-poster eller genom att stänga av frontend-webbservrarna. När servergruppen är "nere" kan du växla till återställningsfarmen.
  
### <a name="stop-log-shipping"></a>Sluta skicka loggen

Du måste stoppa loggleveransen före servergruppsåterställningen. Stoppa loggleveransen på den sekundära servern i Azure först och stoppa den sedan på den primära servern lokalt. Använd följande skript för att stoppa loggleveransen på den sekundära servern först och sedan på den primära servern. Databasnamnen i skriptet kan vara olika beroende på din miljö.
  
```
-- This script removes log shipping from the server.
-- Commands must be executed on the secondary server first and then on the primary server.

SET NOCOUNT ON
DECLARE  @PriDB nvarchar(max)
,@SecDB nvarchar(250)
,@PriSrv nvarchar(250)
,@SecSrv nvarchar(250)

Set @PriDB= ''
SET @PriDB = UPPER(@PriDB)
SET @PriDB = REPLACE(@PriDB, ' ', '')
SET @PriDB = '''' + REPLACE(@PriDB, ',', ''', ''') + ''''

Set @SecDB = @PriDB

Exec ( 'Select  ''exec master..sp_delete_log_shipping_secondary_database '' + '''''''' + prm.primary_database +  ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

Exec ( 'Select  ''exec master..sp_delete_log_shipping_primary_secondary '' + '''''''' + prm.Primary_Database + '''''', '''''' + sec.Secondary_Server + '''''', '''''' + sec.Secondary_database + ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

Exec ( 'Select  ''exec master..sp_delete_log_shipping_primary_database '' + '''''''' + prm.primary_database +  ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

Exec ( 'Select  ''exec master..sp_delete_log_shipping_secondary_primary '' + '''''''' + prm.primary_server + '''''', '''''' + prm.primary_database +  ''''''''   
from msdb.dbo.log_shipping_monitor_primary prm INNER JOIN msdb.dbo.log_shipping_primary_secondaries sec  ON  prm.primary_database=sec.secondary_database
where prm.primary_database in ( ' + @PriDB + ' )')

```

### <a name="restore-the-backups"></a>Återställa säkerhetskopiorna

Säkerhetskopior måste återställas i den ordning som de skapades. Innan du kan återställa en viss säkerhetskopia av transaktionsloggen måste du först återställa följande tidigare säkerhetskopior utan att återställa ogenomsagda transaktioner (d.v.s. genom att använda  `WITH NORECOVERY` ):
  
- Fullständig databassäkerhetskopia och den sista differensen av säkerhetskopiering – Återställ dessa säkerhetskopior, om det finns några, före den specifika säkerhetskopieringen i transaktionsloggen. Innan den senaste säkerhetskopiering av fullständiga databaser eller differens-databaser skapades använde databasen fullständig återställningsmodell eller massloggad återställningsmodell.
    
- Alla säkerhetskopior av transaktionsloggar – Återställ alla säkerhetskopior av transaktionsloggar som har tagits efter den fullständiga säkerhetskopian i databasen eller differensen av säkerhetskopiering (om du återställer en) och före den specifika säkerhetskopieringen av transaktionsloggen. Säkerhetskopior av loggar måste tillämpas i den ordning som de skapades, utan några luckor i loggkedja.
    
Om du vill återställa innehållsdatabasen på den sekundära servern så att webbplatserna återges tar du bort alla databasanslutningar före återställningen. Kör följande SQL-instruktion om du vill återställa databasen.
  
```
restore database WSS_Content with recovery

```

> [!IMPORTANT]
> När du använder T-SQL uttryckligen anger du antingen **WITH NORECOVERY** eller **WITH RECOVERY** i varje RESTORE-instruktion för att eliminera oklarheter – detta är mycket viktigt när du skriver skript. När alla säkerhetskopieringar och differenser har återställts kan transaktionsloggarna återställas i SQL Server Management Studio. Eftersom loggleverans redan stoppas är innehållsdatabasen i vänteläge, så du måste ändra statusen till fullständig åtkomst.
  
I SQL Server Management Studio  högerklickar du på WSS_Content-databasen, pekar på **Uppgiftsåterställning** och klickar sedan på Transaktionslogg (om du inte har återställt den fullständiga säkerhetskopian är detta inte  >  tillgängligt).  Mer information finns i Återställa[säkerhetskopiering av transaktionsloggar (SQL Server).](/sql/relational-databases/backup-restore/restore-a-transaction-log-backup-sql-server)
  
### <a name="crawl-the-content-source"></a>Crawla innehållskällan

Du måste starta en fullständig crawlning för varje innehållskälla för att återställa söktjänsten. Observera att du förlorar viss analysinformation från den lokala servergruppen, till exempel sökrekommendationer. Innan du startar alla crawlningar använder du Windows PowerShell-cmdleten **Restore-SPEnterpriseSearchServiceApplication** och anger den log-shipped och replikerade Search Administration-databasen **Search_Service__DB_ <GUID>**. Den här cmdleten ger dig sökkonfiguration, schema, hanterade egenskaper, regler och källor och skapar en standarduppsättning med de andra komponenterna.
  
Om du vill starta en fullständig crawlning slutför du följande steg:
  
1. I Central administration av SharePoint 2013 går du till Programhanteringstjänstprogram Hantera tjänstprogram och klickar sedan på det söktjänstprogram som du vill  >    >  crawla.
    
2. På sidan **Sökadministration** klickar du på **Innehållskällor,** pekar på den innehållskälla som du vill använda, klickar på pilen och klickar sedan på **Starta fullständig crawlning.**
    
### <a name="recover-farm-services"></a>Återställa servergruppstjänster

I följande tabell visas hur du återställer tjänster som har log-shipped databases, de tjänster som har databaser men inte rekommenderas att återställa med loggleverans och de tjänster som inte har databaser.
  
> [!IMPORTANT]
> Om du återställer en lokal SharePoint-databas i Azure-miljön återställs inte några SharePoint-tjänster som du inte redan har installerat i Azure manuellt. 
  
**Tabell: Databasreferens för tjänstprogram**

|**Återställa de här tjänsterna från log-shipped databases**|**De här tjänsterna har databaser, men vi rekommenderar att du startar de här tjänsterna utan att återställa deras databaser**|**Dessa tjänster lagrar inte data i databaser. starta de här tjänsterna efter redundans**|
|:-----|:-----|:-----|
| Maskinöversättningstjänst <br/>  Tjänst för hanterade metadata <br/>  Säker lagringstjänst <br/>  Användarprofil. (Endast databaserna för profil och social märkning stöds. Synkroniseringsdatabasen stöds inte.) <br/>  Inställningstjänst för Microsoft SharePoint Foundation-prenumeration <br/> | Insamling av användnings- och hälsodata <br/>  Delstatstjänst <br/>  Word-automation <br/> | Excel Services <br/>  PerformancePoint-tjänster <br/>  PowerPoint-konvertering <br/>  Visio-grafiktjänst <br/>  Arbetshantering <br/> |
   
I följande exempel visas hur du återställer tjänsten hanterade metadata från en databas.
  
Då används den befintliga Managed_Metadata_DB databasen. Den här databasen har levererats med en logg, men det finns inget aktivt tjänstprogram i den sekundära servergruppen, så den måste anslutas när tjänstprogrammet är på plats.
  
Använd först  `New-SPMetadataServiceApplication` och ange  `DatabaseName` växeln med namnet på den återställda databasen.
  
Konfigurera sedan det nya tjänstprogrammet för hanterade metadata på den sekundära servern enligt följande:
  
- Namn: Hanterad metadatatjänst
    
- Databasserver: Databasnamnet från den skickade transaktionsloggen
    
- Databasnamn: Managed_Metadata_DB
    
- Programpool: SharePoint Service-program 
    
### <a name="manage-dns-records"></a>Hantera DNS-poster

Du måste manuellt skapa DNS-poster så att de pekar på SharePoint-servergruppen.
  
I de flesta fall där du har flera frontend-webbservrar är det bra att använda funktionen Utjämning av nätverksbelastning i Windows Server 2012 eller en maskinvarufördelning för att distribuera förfrågningar mellan webb-frontend-servrarna i servergruppen. Utjämning av nätverksbelastningen kan också minska risken genom att distribuera förfrågningar till andra servrar om en av dina webbservrar misslyckas. 
  
När du ställer in belastningsutjämning för nätverket tilldelas ditt kluster vanligtvis en enda IP-adress. Sedan skapar du en DNS-värdpost i DNS-leverantören för nätverket som pekar på klustret. (För det här projektet lade vi till en DNS-server i Azure för motståndskraft vid ett lokalt datacenterfel.) Du kan till exempel skapa en DNS-post i DNS-hanteraren i Active Directory som pekar på IP-adressen för ett  `https://sharepoint.contoso.com` belastningsutjämnat kluster.
  
För extern åtkomst till SharePoint-servergruppen kan du skapa en värdpost på en extern DNS-server med samma URL som klienter använder på intranätet (till exempel) som pekar på en extern IP-adress i `https://sharepoint.contoso.com` brandväggen. (Vi använder det här exemplet som metod om du vill konfigurera delad DNS så att den interna DNS-servern är auktoritativ för och dirigerar förfrågningar direkt till SharePoint-servergruppskluster, i stället för att dirigera DNS-begäranden till den externa `contoso.com` DNS-servern.) Sedan kan du mappa den externa IP-adressen till den interna IP-adressen för ditt lokala kluster så att klienterna hittar de resurser de söker.
  
Härifrån kan du få olika scenarier för katastrofåterställning:
  
 **Exempelscenario: Den lokala SharePoint-servergruppen är inte tillgänglig på grund av maskinvarufel i den lokala SharePoint-servergruppen.** När du har utfört stegen för redundans för Azure SharePoint-servergruppen kan du i det här fallet konfigurera utjämning av nätverksbelastningen på SharePoint-servergruppens webbservrar, på samma sätt som du gjorde med den lokala servergruppen. Du kan sedan omdirigera värdposten i den interna DNS-leverantören så att den pekar på IP-adressen för återställningsfarmens kluster. Observera att det kan ta lite tid innan cachelagrade DNS-poster i klienter uppdateras och pekar på återställningsservern.
  
 **Exempelscenario: Det lokala datacentret förloras helt.** Det här scenariot kan uppstå på grund av en naturåterställning, till exempel en brand eller en flod. I det här fallet skulle du för ett företag sannolikt ha ett sekundärt datacenter i en annan region samt ditt Azure-undernät som har sina egna katalogtjänster och DNS. Precis som vid föregående katastrofscenario kan du omdirigera dina interna och externa DNS-poster så att de pekar på Azure SharePoint-servergruppen. Observera att det kan ta lite tid att sprida DNS-poster.
  
Om du använder värdbaserade webbplatssamlingar, som rekommenderas i Värdnamnad webbplatssamlingsarkitektur och distribution [(SharePoint 2013)](/SharePoint/administration/host-named-site-collection-architecture-and-deployment)kan du ha flera webbplatssamlingar som lagras av samma webbprogram i SharePoint-servergruppen, med unika DNS-namn (till exempel `https://sales.contoso.com` och `https://marketing.contoso.com` ). I det här fallet kan du skapa DNS-poster för varje webbplatssamling som pekar på kluster-IP-adressen. När en begäran når SharePoint web front-end-servrar hanterar de varje begäran till rätt webbplatssamling.
  
## <a name="microsoft-proof-of-concept-environment"></a>Microsoft Proof-of-concept-miljö

Vi har utformat och testat en koncepttestmiljö för den här lösningen. Designmålet för testmiljön var att distribuera och återställa en SharePoint-servergrupp som kan finnas i en kundmiljö. Vi gjorde flera antaganden, men vi visste att servergruppen behövde kunna tillhandahålla alla inbehövliga funktioner utan några anpassningar. Topologin utformades för hög tillgänglighet med hjälp av metodvägledning från fältet och produktgruppen.
  
I följande tabell beskrivs de virtuella Hyper-V-maskinerna som vi skapat och konfigurerat för den lokala testmiljön.
  
**Tabell: Virtuella maskiner för lokalt test**

|**Servernamn**|**Roll**|**Konfiguration**|
|:-----|:-----|:-----|
|DC1  <br/> |Domänkontrollant med Active Directory.  <br/> |Två processorer  <br/> Från 512 MB till 4 GB RAM-minne  <br/> 1 x 127 GB-hårddisk  <br/> |
|RRAS  <br/> |Server som konfigurerats med rollerna Routing och Remote Access Service (RRAS).  <br/> |Två processorer  <br/> 2–8 GB RAM-minne  <br/> 1 x 127 GB-hårddisk  <br/> |
|FS1  <br/> |Filserver med resurser för säkerhetskopior och en ändpunkt för TIDER.  <br/> |Fyra processorer  <br/> 2–12 GB RAM-minne  <br/> 1 x 127 GB-hårddisk  <br/> 1 x 1 TB hårddisk (SAN)  <br/> 1 x 750 GB-hårddisk  <br/> |
|SP-WFE1, SP-WFE2  <br/> |Frontend-webbservrar.  <br/> |Fyra processorer  <br/> 16 GB RAM-minne  <br/> |
|SP-APP1, SP-APP2, SP-APP3  <br/> |Application servers.  <br/> |Fyra processorer  <br/> 2–16 GB RAM-minne  <br/> |
|SP-SQL-HA1, SP-SQL-HA2  <br/> |Databasservrar, konfigurerade med tillgänglighetsgrupper i SQL Server 2012 AlwaysOn för att ge hög tillgänglighet. I den här konfigurationen används SP-SQL-HA1 och SP-SQL-HA2 som primära och sekundära repliker.  <br/> |Fyra processorer  <br/> 2–16 GB RAM-minne  <br/> |
   
I följande tabell beskrivs enhetskonfigurationer för de virtuella Hyper-V-maskiner som vi har skapat och konfigurerat för frontend-webb- och programservrarna för den lokala testmiljön.
  
**Tabell: Krav för virtuell datorenhet för frontendwebb- och programservrarna för det lokala testet**

|**Enhetsbeteckning**|**Storlek**|**Katalognamn**|**Sökväg**|
|:-----|:-----|:-----|:-----|
|C  <br/> |80  <br/> |Systemenhet  <br/> |<DriveLetter>: \\ Program Files Microsoft SQL \\ Server\\  <br/> |
|E  <br/> |80  <br/> |Loggenhet (40 GB)  <br/> |<DriveLetter>: \\ Program Files Microsoft SQL Server \\ \\ MSSQL10_50.MSSQLSERVER \\ MSSQL \\ DATA  <br/> |
|F  <br/> |80  <br/> |Sida (36 GB)  <br/> |<DriveLetter>: \\ Program Files Microsoft SQL Server \\ \\ MSSQL \\ DATA  <br/> |
   
I följande tabell beskrivs enhetskonfigurationer för virtuella Hyper-V-maskiner som skapats och konfigurerats för att fungera som lokala databasservrar. På sidan **Database Engine Configuration** går du till fliken **Datakataloger** och anger och bekräftar inställningarna som visas i följande tabell.
  
**Tabell: Krav för virtuell datorenhet för databasservern för det lokala testet**

|**Enhetsbeteckning**|**Storlek**|**Katalognamn**|**Sökväg**|
|:-----|:-----|:-----|:-----|
|C  <br/> |80  <br/> |Datarotkatalog  <br/> |<DriveLetter>: \\ Program Files Microsoft SQL \\ Server\\  <br/> |
|E  <br/> |500  <br/> |Användardatabaskatalog  <br/> |<DriveLetter>: \\ Program Files Microsoft SQL Server \\ \\ MSSQL10_50.MSSQLSERVER \\ MSSQL \\ DATA  <br/> |
|F  <br/> |500  <br/> |Användardatabasloggkatalog  <br/> |<DriveLetter>: \\ Program Files Microsoft SQL Server \\ \\ MSSQL10_50.MSSQLSERVER \\ MSSQL \\ DATA  <br/> |
|G  <br/> |500  <br/> |Temp DB-katalog  <br/> |<DriveLetter>: \\ Program Files Microsoft SQL Server \\ \\ MSSQL10_50.MSSQLSERVER \\ MSSQL \\ DATA  <br/> |
|H  <br/> |500  <br/> |Temp DB-loggkatalog  <br/> |<DriveLetter>: \\ Program Files Microsoft SQL Server \\ \\ MSSQL10_50.MSSQLSERVER \\ MSSQL \\ DATA  <br/> |
   
### <a name="setting-up-the-test-environment"></a>Konfigurera testmiljön

Under de olika distributionsfaserna arbetade testteamet vanligtvis med den lokala arkitekturen först och sedan på motsvarande Azure-miljö. Det återspeglar de verkliga ärendena där de lokala produktionsenheterna redan körs. Ännu viktigare är att du känner till aktuell produktionsarbetsbelastning, kapacitet och vanliga prestanda. Förutom att skapa en katastrofåterställningsmodell som kan uppfylla företagskrav bör du ändra storlek på servergruppsservrarna för återställning så att en lägsta servicenivå levereras. I en kalla eller varmt vänteläge är en återställningsfarm vanligtvis mindre än en produktionsfarm. När återställningsfarmen är stabil och i produktion kan servergruppen skalas upp och ut för att uppfylla kraven på arbetsbelastning.
  
Vi har distribuerat testmiljön i följande tre faser:
  
- Konfigurera hybridinfrastrukturen
    
- Etablera servrarna
    
- Distribuera SharePoint-farms
    
#### <a name="set-up-the-hybrid-infrastructure"></a>Konfigurera hybridinfrastrukturen

Den här fasen innebär att konfigurera en domänmiljö för den lokala servergruppen och för återställningsfarmen i Azure. Förutom de vanliga uppgifterna som är associerade med att konfigurera Active Directory har testteamet implementerat en routningslösning och en VPN-anslutning mellan de två miljöerna.
  
#### <a name="provision-the-servers"></a>Etablera servrarna

Utöver servergruppsservrarna var det nödvändigt att tillhandahålla servrar för domänkontrollanterna och konfigurera en server för att hantera RRAS samt VPN för webbplats till webbplats. Två filservrar har etablerats för TJÄNSTEN BRANR och flera klientdatorer har etablerats för testare.
  
#### <a name="deploy-the-sharepoint-farms"></a>Distribuera SharePoint-farms

SharePoint-farmen har distribuerats i två steg för att förenkla stabilitet och felsökning vid behov. Under det första steget distribuerades varje servergrupp på det lägsta antalet servrar för varje nivå i topologin för att stödja de nödvändiga funktionerna.
  
Vi skapade databasservrarna med SQL Server installerat innan SharePoint 2013-servrarna skapades. Eftersom det var en ny distribution skapade vi tillgänglighetsgrupper innan SharePoint distribuerades. Vi har skapat tre grupper baserade på vägledning för bästa praxis för MCS. 
  
> [!NOTE]
> Skapa platshållardatabaser så att du kan skapa tillgänglighetsgrupper innan SharePoint-installationen. Mer information finns i [Konfigurera SQL Server 2012 AlwaysOn-tillgänglighetsgrupper för SharePoint 2013](/SharePoint/administration/configure-an-alwayson-availability-group)
  
Vi skapade servergruppen och anslöt till ytterligare servrar i följande ordning:
  
- Etablera SP-SQL-HA1 och SP-SQL-HA2.
    
- Konfigurera AlwaysOn och skapa de tre tillgänglighetsgrupperna för servergruppen. 
    
- Tillhandahålla SP-APP1 som värd för Central administration.
    
- Tillhandahålla SP-WFE1 och SP-WFE2 som värd för det distribuerade cacheminnet. 
    
Vi använde  _parametern skipRegisterAsDistributedCachehost_ när **vipsconfig.exe** på kommandoraden. Mer information finns i [Planera för feeds och tjänsten Distribuerad cache i SharePoint Server 2013.](/sharepoint/administration/plan-for-feeds-and-the-distributed-cache-service) 
  
Vi upprepade följande steg i återställningsmiljön:
  
- Tillhandahålla AZ-SQL-HA1 och AZ-SQL-HA2.
    
- Konfigurera AlwaysOn och skapa de tre tillgänglighetsgrupperna för servergruppen.
    
- Tillhandahålla AZ-APP1 som värd för Central Administration.
    
- Tillhandahålla AZ-WFE1 och AZ-WFE2 som värd för det distribuerade cacheminnet.
    
När vi konfigurerat den distribuerade cachen och lagt till testanvändare och testinnehåll startade vi steg två i distributionen. Detta kräver skalning av nivåerna och konfiguration av servergruppsservrarna för att stödja den toppologi med hög tillgänglighet som beskrivs i servergruppsarkitekturen.
  
I följande tabell beskrivs de virtuella datorer, undernät och tillgänglighetsuppsättningar vi uppsättningar för återställningsfarmen.
  
**Tabell: Infrastruktur för återställningsfarm**

|**Servernamn**|**Roll**|**Konfiguration**|**Undernät**|**Tillgänglighetsuppsättning**|
|:-----|:-----|:-----|:-----|:-----|
|spDRAD  <br/> |Domänkontrollant med Active Directory  <br/> |Två processorer  <br/> Från 512 MB till 4 GB RAM-minne  <br/> 1 x 127 GB-hårddisk  <br/> |sp-ADservers  <br/> ||
|AZ-SP-FS  <br/> |Filserver med resurser för säkerhetskopior och en slutpunkt för TIDER  <br/> | A5-konfiguration: <br/>  Två processorer <br/>  14 GB RAM-minne <br/>  1 x 127 GB-hårddisk <br/>  1 x 135 GB-hårddisk <br/>  1 x 127 GB-hårddisk <br/>  1 x 150 GB-hårddisk <br/> |sp-databaseservers  <br/> |DATA_SET  <br/> |
|AZ-WFE1, AZ -WFE2  <br/> |Front End-webbservrar  <br/> | A5-konfiguration: <br/>  Två processorer <br/>  14 GB RAM-minne <br/>  1 x 127 GB-hårddisk <br/> |sp-webservers  <br/> |WFE_SET  <br/> |
|AZ -APP1, AZ -APP2, AZ -APP3  <br/> |Application servers  <br/> | A5-konfiguration: <br/>  Två processorer <br/>  14 GB RAM-minne <br/>  1 x 127 GB-hårddisk <br/> |sp-applicationservers  <br/> |APP_SET  <br/> |
|AZ -SQL-HA1, AZ -SQL-HA2  <br/> |Databasservrar och primära och sekundära repliker för AlwaysOn-tillgänglighetsgrupper  <br/> | A5-konfiguration: <br/>  Två processorer <br/>  14 GB RAM-minne <br/> |sp-databaseservers  <br/> |DATA_SET  <br/> |
   
### <a name="operations"></a>Drift

När testgruppen tog bort servergruppsmiljöerna och slutförde funktionstestningen startade de följande åtgärder som krävs för att konfigurera den lokala återställningsmiljön:
  
- Konfigurera fullständiga och differentiella säkerhetskopior.
    
- Konfigurera TIDER på filservrarna som överför transaktionsloggar mellan den lokala miljön och Azure-miljön.
    
- Konfigurera loggleverans på den primära databasservern.
    
- Validera, validera och felsök loggleverans efter behov. Detta inkluderade att identifiera och dokumentera något beteende som kan orsaka problem, till exempel nätverksfördröjning, som skulle orsaka loggleverans eller TIDE(ER) filsynkroniseringsfel.
    
### <a name="databases"></a>Databaser

Våra redundanstester involverar följande databaser: 
  
- WSS_Content
    
- ManagedMetadata
    
- Profile DB
    
- Synkronisera DB
    
- Social DB
    
- Innehållstypnav (en databas för ett dedikerat innehållstypssyndikeringsnav)
    
## <a name="troubleshooting-tips"></a>Felsökningstips

I det här avsnittet beskrivs de problem som uppstod under testningen och deras lösningar. 
  
### <a name="using-the-term-store-management-tool-caused-the-error-the-managed-metadata-store-or-connection-is-currently-not-available"></a>När du använde verktyget för hantering av termlager orsakade felet "Hanterad metadataarkiv eller anslutning är för närvarande inte tillgänglig".

Kontrollera att det programpoolkonto som används av webbprogrammet har behörigheten Läsåtkomst till termlager.
  
### <a name="custom-term-sets-are-not-available-in-the-site-collection"></a>Anpassade termuppsättningar är inte tillgängliga i webbplatssamlingen

Kontrollera om det saknas en tjänstprogramsassociat relation mellan innehållswebbplatssamlingen och innehållstypen navet. Kontrollera att det här alternativet är aktiverat på skärmen Hanterade **metadata <site collection name>** – anslutningsegenskaper: Det här tjänstprogrammet är standardlagringsplatsen för **kolumnspecifika termuppsättningar.**
  
### <a name="the-get-adforest-windows-powershell-command-generates-the-error-the-term-get-adforest-is-not-recognized-as-the-name-of-a-cmdlet-function-script-file-or-operable-program"></a>Med Get-ADForest Windows PowerShell-kommandot genererar du felet: "Termen "Get-ADForest" kan inte identifieras som namn på en cmdlet, en funktion, en skriptfil eller ett operabelt program.

När du ska konfigurera användarprofiler behöver du Active Directory-skogens namn. I guiden Lägg till roller och funktioner ser du till att du har aktiverat Active Directory-modulen för Windows PowerShell (under avsnittet Verktyg för fjärrserveradministration **>Rolladministration>AD DS- och AD LDS-verktyg).** Kör dessutom följande kommandon innan du använder **Get-AD För** att säkerställa att dina programvaruberoenden läses in.
  
```
Import-module servermanager
Import-module activedirectory

```

### <a name="availability-group-creation-fails-at-starting-the-alwayson_health-xevent-session-on-server-name"></a>Det går inte att skapa en tillgänglighetsgrupp vid AlwaysOn_health XEvent-session i <server name> '

Kontrollera att båda noderna i redundansklustret finns i statusen "Upp" och inte i "Pausad" eller "Stoppad". 
  
### <a name="sql-server-log-shipping-job-fails-with-access-denied-error-trying-to-connect-to-the-file-share"></a>SQL Server-leveransjobbet misslyckas med felmeddelande om nekad åtkomst vid försök att ansluta till filresursen

Kontrollera att din SQL Server-agent körs med nätverksautentiseringsuppgifter i stället för standardautentiseringsuppgifterna.
  
### <a name="sql-server-log-shipping-job-indicates-success-but-no-files-are-copied"></a>SQL Server-leveransjobbet visar att det är lyckat, men inga filer kopieras

Detta inträffar eftersom standardinställningen för säkerhetskopiering för en tillgänglighetsgrupp **är Prefer Secondary**. Kontrollera att du kör loggleveransjobbet från den sekundära servern för tillgänglighetsgruppen i stället för den primära servern. Annars kommer jobbet att misslyckas utan att du blir tyst. 
  
### <a name="managed-metadata-service-or-other-sharepoint-service-fails-to-start-automatically-after-installation"></a>Hanterad metadatatjänst (eller annan SharePoint-tjänst) startar inte automatiskt efter installationen

Tjänster kan ta flera minuter att starta, beroende på prestanda och aktuell inläsning av SharePoint Server. Klicka manuellt **på Starta** för tjänsten och ge tillräcklig tid för att starta tjänsten när tjänsten på serverskärmen uppdateras manuellt för att övervaka dess status. Om tjänsten förblir stoppad aktiverar du SharePoint-diagnostikloggning, försöker starta tjänsten igen och kontrollerar sedan loggen efter fel. Mer information finns i Konfigurera [diagnostikloggning i SharePoint 2013](/sharepoint/administration/configure-diagnostic-logging)
  
### <a name="after-changing-dns-to-the-azure-failover-environment-client-browsers-continue-to-use-the-old-ip-address-for-the-sharepoint-site"></a>När DNS har ändrats till Azure-redundansmiljön fortsätter klientwebbläsare att använda den gamla IP-adressen för SharePoint-webbplatsen

Dns-ändringen kanske inte visas för alla klienter direkt. Utför följande kommando från en upphöjd kommandotolk på en testklient och försök att komma åt webbplatsen igen.
  
```
Ipconfig /flushdns
```

## <a name="additional-resources"></a>Ytterligare resurser

[Hög tillgänglighet och alternativ för katastrofåterställning stöds för SharePoint-databaser](/sharepoint/administration/supported-high-availability-and-disaster-recovery-options-for-sharepoint-databas)
  
[Konfigurera SQL Server 2012 AlwaysOn-tillgänglighetsgrupper för SharePoint 2013](/SharePoint/administration/configure-an-alwayson-availability-group)
  
## <a name="see-also"></a>Se även

[Microsoft 365-lösning och arkitekturcenter](../solutions/index.yml)