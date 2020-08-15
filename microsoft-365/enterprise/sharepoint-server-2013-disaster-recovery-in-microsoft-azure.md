---
title: SharePoint Server 2013 katastrof återställning i Microsoft Azure
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
description: I den här artikeln beskrivs hur du använder Azure för att skapa en katastrof återställnings miljö för den lokala SharePoint-servergruppen.
ms.openlocfilehash: d1643f3fa0275ef9fbb01372869ca551b9fed495
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694445"
---
# <a name="sharepoint-server-2013-disaster-recovery-in-microsoft-azure"></a>SharePoint Server 2013 katastrof återställning i Microsoft Azure

 Med Azure kan du skapa en katastrof återställnings miljö för den lokala SharePoint-servergruppen. I den här artikeln beskrivs hur du utformar och implementerar den här lösningen.

 **Titta på videon om återställning av Disaster Recovery-funktioner i SharePoint Server 2013**
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1b73ec8f-29bd-44eb-aa3a-f7932784bfd9?autoplay=false]
  
 När en katastrof träffar den lokala SharePoint-miljön är din bästa prioritet att snabbt komma igång med systemet. En katastrof återställning med SharePoint är snabbare och enklare när du redan har en säkerhets kopierings miljö i Microsoft Azure. I det här videoklippet lär du dig de viktigaste begreppen i en SharePoint varm failover-miljö och kompletterar alla uppgifter som är tillgängliga i den här artikeln.
  
Använd den här artikeln med följande lösnings modell: **katastrof återställning för SharePoint i Microsoft Azure**.
  
[![SharePoint – katastrof-återställning till Azure](../media/SP-DR-Azure.png)](https://go.microsoft.com/fwlink/p/?LinkId=392555)
  
 [PDF](https://go.microsoft.com/fwlink/p/?LinkId=392555) |  [Visio](https://go.microsoft.com/fwlink/p/?LinkId=392554)
  
## <a name="use-azure-infrastructure-services-for-disaster-recovery"></a>Använd Azure Infrastructure Services för katastrof återställning

Många organisationer har ingen katastrof återställnings miljö för SharePoint, vilket kan vara dyrt att bygga och underhålla lokalt. Azure Infrastructure Services tillhandahåller övertygande alternativ för katastrof återställnings miljöer som är mer flexibla och billigare än de lokala alternativen.
  
Fördelarna med att använda Azure Infrastructure-tjänsterna är:
  
- **Färre dyra resurser** Underhåll och betala för färre resurser än lokal katastrof återställnings miljö. Antalet resurser beror på vilken katastrof-återställning du väljer: kall standby, varm standby eller snabb standby.
    
- **Bättre flexibilitet för resurser** I händelse av en katastrof kan du enkelt utöka din återställning av SharePoint-servergruppen för att uppfylla laddnings kraven. Skala in när du inte längre behöver resurserna.
    
- **Mindre data Center engagemang** Använd Azure Infrastructure Services i stället för att investera i ett sekundärt Data Center i en annan region.
    
Det finns mindre komplexa alternativ för organisationer som bara kommer igång med katastrof återställning och avancerade alternativ för organisationer med hög återhämtnings krav. Definitionerna för miljöer med kall, varm och hot standby är lite annorlunda när miljön är värd för en moln plattform. I följande tabell beskrivs dessa miljöer för att skapa en SharePoint-återställnings grupp i Azure.
  
**Tabell: återställnings miljöer**

|**Typ av återställnings miljö**|**Beskrivning**|
|:-----|:-----|
|Hot  <br/> |En Server grupp är etablerad, uppdaterad och körs i standby.  <br/> |
|Bränn  <br/> |Server gruppen är byggd och virtuella datorer körs och uppdateras.  <br/> Med återställning kan du bifoga innehålls databaser, tjänst program och Crawla innehåll.  <br/> Server gruppen kan vara en mindre version av produktions gruppen och sedan byggas ut för att hantera hela användar basen.  <br/> |
|Huset  <br/> |Server gruppen är helt inbyggd men de virtuella datorerna stoppas.  <br/> Att underhålla miljön inkluderar att starta de virtuella datorerna, då och då, korrigera, uppdatera och verifiera miljön.  <br/> Starta hela miljön i händelse av en katastrof.  <br/> |
   
Det är viktigt att utvärdera organisationens återställnings tids mål (RTOs) och återställnings punkt mål (RPOs). Dessa krav avgör vilken miljö som är den mest lämpliga investeringen för din organisation.
  
I den här artikeln beskrivs hur du implementerar en miljö för varma vänte läge. Du kan också anpassa den till en kall standby-miljö, men du måste följa ytterligare procedurer för att kunna använda den här typen av miljö. I den här artikeln beskrivs inte hur du implementerar en miljö för snabb växling.
  
Mer information om lösningar för katastrof återställning finns i [koncept för hög tillgänglighet och katastrof återställning i sharepoint 2013](https://go.microsoft.com/fwlink/p/?LinkID=393114) och [välja en strategi för katastrof återställning för SharePoint 2013](https://go.microsoft.com/fwlink/p/?linkid=203228).
  
## <a name="solution-description"></a>Lösnings Beskrivning

Katastrof för nöd situationer med återställning kräver följande miljö:
  
- En lokal SharePoint-servergrupp
    
- En återställnings-SharePoint-servergrupp i Azure
    
- En VPN-anslutning mellan två miljöer
    
Följande bild illustrerar dessa tre element.
  
**Bild: element i en lösning för varm standby i Azure**

![Element i en lösning för varm standby i SharePoint i Azure](../media/AZarch-AZWarmStndby.png)
  
SQL Server-loggning med Distributed File System Replication (DFSR) används för att kopiera databas säkerhets kopior och transaktions loggar till återställnings gruppen i Azure: 
  
- DFSR överför loggar från produktions miljön till återställnings miljön. I ett WAN-scenario är DFSR effektivare än att leverera loggarna direkt till den sekundära servern i Azure.
    
- Loggar spelas upp på SQL-servern i återställnings miljön i Azure.
    
- Du lägger inte till en uppringd databas för SharePoint-innehåll i återställnings miljön förrän en återställnings övning utförs.
    
Återställ Server gruppen genom att utföra följande steg:
  
1. Avbryt leverans.
    
2. Sluta acceptera trafik till den primära server gruppen.
    
3. Repetera de slutliga transaktions loggarna igen.
    
4. Bifoga innehålls databaserna till Server gruppen.
    
5. Återställ tjänst program från replikerade tjänst databaser.
    
6. Uppdatera DNS-poster (Domain Name System) så att de pekar på återställnings gruppen.
    
7. Starta en fullständig crawlning.
    
Vi rekommenderar att du regelbundet upprepar de här stegen och kan dokumentera dem för att säkerställa att din Live-återställning fungerar smidigt. Det kan ta en stund att bifoga innehålls databaser och återställa tjänst program och det innebär normalt en del manuell konfiguration.
  
När en återställning har utförts tillhandahåller den här lösningen objekten som visas i följande tabell.
  
**Tabell: mål för lösnings återställning**

|**Objekt**|**Beskrivning**|
|:-----|:-----|
|Webbplatser och innehåll  <br/> |Webbplatser och innehåll är tillgängliga i återställnings miljön.  <br/> |
|En ny instans av sökning  <br/> |I denna varm standby-lösning återställs inte sökningen från Sök databaser. Sök komponenter i återställnings gruppen är konfigurerade så lika som möjligt till produktions gruppen. När webbplatserna och innehållet har återställts startas en fullständig crawlning för att återskapa Sök indexet. Du behöver inte vänta på att crawlningen ska slutföras för att webbplatser och innehåll ska vara tillgängligt.  <br/> |
|Uthyrning  <br/> | Tjänster som lagrar data i databaser återställs från den loggade databasen. Tjänster som inte lagrar data i databaser startas helt enkelt. <br/>  Alla tjänster med databaser behöver inte återställas. Följande tjänster behöver inte återställas från databaser och kan bara startas efter redundans: <br/>  Insamling av användnings-och hälso data <br/>  Tillstånds tjänst <br/>  Word-automatisering <br/>  Alla andra tjänster som inte använder en databas <br/> |
   
Du kan arbeta med Microsoft Consulting Services (MCS) eller en partner för att adressera mer-komplexa återställnings mål. Dessa sammanfattas i följande tabell.
  
**Tabell: andra objekt som kan adresseras av MCS eller en partner**

|**Objekt**|**Beskrivning**|
|:-----|:-----|
|Synkronisera anpassade Server grupps lösningar  <br/> |Det bästa är att återställnings gruppens konfiguration är identisk med produktions gruppen. Du kan arbeta med en konsult eller partner för att utvärdera om anpassade Server grupps lösningar har repliker ATS och om processen finns för att hålla ned de båda miljöerna.  <br/> |
|Anslutningar till data källor lokalt  <br/> |Det är kanske inte möjligt att replikera anslutningar till backend-datasystem, till exempel BDC-anslutningar (reservdomänkontrollant) och Sök innehålls källor.  <br/> |
|Scenarier för Sök återställning  <br/> |Eftersom distributioner av företags sökningar tenderar att vara ganska unikt och komplicerat kräver en större investering att du kan återställa sökning från databaser. Du kan arbeta med en konsult eller partner för att identifiera och implementera scenarier för Sök återställning som din organisation kan behöva.  <br/> |
   
Vägledningarna i den här artikeln förutsätter att den lokala server gruppen redan är utformad och distribuerad.
  
## <a name="detailed-architecture"></a>Detaljerad arkitektur

Det bästa är att konfiguration av återställnings grupp i Azure är identiskt med den lokala tillverknings gruppen, inklusive följande:
  
- Samma representation av Server roller
    
- Samma konfiguration av anpassningar
    
- Samma konfiguration för Sök komponenter
    
Miljön i Azure kan vara en mindre version av produktions gruppen. Om du planerar att bygga ut återställnings gruppen efter redundans är det viktigt att varje typ av server roll först visas.
  
Vissa konfigurationer kanske inte är praktiska att replikera i failover-miljön. Se till att testa rutiner och miljön för växling vid fel för att säkerställa att failover-serverns tjänst nivå tillhandahålls.
  
Denna lösning föreskriver inte en speciell topologi för en SharePoint-grupp. Fokus för den här lösningen är att använda Azure för failover-gruppen och implementera logg överföring och DFSR mellan de båda miljöerna.
  
### <a name="warm-standby-environments"></a>Miljöer för varm standby

I en miljö med varmt standby körs alla virtuella datorer i Azure-miljön. Miljön är klar för en träningsverksamhet eller händelse.
  
Följande bild illustrerar en katastrof återställnings lösning från en lokal SharePoint-servergrupp till en Azure-baserad SharePoint-servergrupp som är konfigurerad som en miljö för varmt standby.
  
**Bild: topologi och viktiga element i en produktions grupp och en återställnings Server för varm vänte tid**

![Topologi för en SharePoint-servergrupp och en återställnings grupp för varm vänte tid](../media/AZarch-AZWarmStndby.png)
  
I det här diagrammet:
  
- Två miljöer illustreras sida vid sida: den lokala SharePoint-servergruppen och varm standby-servergruppen i Azure.
    
- Varje miljö inkluderar en fil resurs.
    
- Varje server grupp innehåller fyra nivåer. För att få hög tillgänglighet inkluderar varje nivå två servrar eller virtuella datorer som är konfigurerade identiskt för en viss roll, till exempel frontend-tjänster, distribuerad cache, backend-tjänster och databaser. Det är inte viktigt i den här bilden för att ringa ut specifika komponenter. De två Server grupperna är identiska.
    
- Den fjärde nivån är databas nivån. Logg överföring används för att kopiera loggar från den sekundära databas servern i den lokala miljön till fil resursen i samma miljö.
    
- DFSR kopierar filer från fil resursen i den lokala miljön till fil resursen i Azure-miljön.
    
- Med loggning kan du spela upp loggar från fil resursen i Azure-miljön till den primära repliken i SQL Server AlwaysOn-tillgänglighetsgruppen i återställnings miljön.
    
### <a name="cold-standby-environments"></a>Miljöer med kall vilo läge

I en kall standby-miljö kan de flesta av de virtuella SharePoint-gruppdatorerna vara avstängda. (Vi rekommenderar att starta de virtuella datorerna ibland, till exempel varannan vecka eller en gång i månaden, så att varje virtuell dator kan synkroniseras med domänen.) Följande virtuella datorer i Azure Recovery Environment måste fortsätta att fungera för att det ska gå att säkerställa kontinuerliga operationer med att logga in och DFSR:
  
- Fil resursen
    
- Den primära databas servern
    
- Minst en virtuell dator med Windows Server Active Directory Domain Services och DNS
    
I bilden nedan visas en Azure failover-miljö där den virtuella dator resursen och den primära SharePoint-databasen körs. Alla andra virtuella SharePoint-datorer stoppas. Den virtuella datorn som kör Windows Server Active Directory och DNS visas inte.
  
**Bild: återställnings Server för kall återställning med aktiva virtuella datorer**

![Element i en lösning för kall standby i SharePoint i Azure](../media/AZarch-AZColdStndby.png)
  
Efter redundans till en kall vilo miljö startas alla virtuella datorer, och metoden för att uppnå en hög tillgänglighet för databas servrar måste vara konfigurerad, till exempel SQL Server AlwaysOn-tillgänglighetsgruppen.
  
Om flera lagrings grupper implementeras (databaserna sprids över fler än en SQL Server-uppsättning med hög tillgänglighet) måste den primära databasen för varje lagrings grupp vara igång för att acceptera de loggar som är kopplade till lagrings gruppen.
  
### <a name="skills-and-experience"></a>Färdigheter och erfarenheter

Flera tekniker används i denna lösning för katastrof återställning. För att säkerställa att dessa tekniker interagerar som förväntat måste varje komponent i lokala och Azure-miljö vara installerad och korrekt konfigurerad. Vi rekommenderar att den person eller det team som konfigurerar denna lösning har ett starkt arbets kunnande med de tekniker som beskrivs i följande artiklar:
  
- [DFS-replikeringstjänsten (Distributed File System)](https://go.microsoft.com/fwlink/p/?LinkId=392698)
    
- [Windows Server Failover Clustering (WSFC) med SQL Server](https://go.microsoft.com/fwlink/p/?LinkId=392701)
    
- [AlwaysOn-tillgänglighetsgruppen (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=392725)
    
- [Säkerhetskopiera och återställa SQL Server-databaser](https://go.microsoft.com/fwlink/p/?LinkId=392728)
    
- [SharePoint Server 2013-installation och Server grupp distribution](https://go.microsoft.com/fwlink/p/?LinkId=393119)
    
- [Microsoft Azure](https://go.microsoft.com/fwlink/p/?LinkId=392729)
    
Slutligen rekommenderar vi skript kunskaper som du kan använda för att automatisera uppgifter som är kopplade till dessa tekniker. Det går att använda de tillgängliga gränssnitten för att slutföra alla aktiviteter som beskrivs i den här lösningen. Men en manuell metod kan vara tidsödande och vara fel känslig och ger inkonsekventa resultat.
  
Utöver Windows PowerShell finns det också Windows PowerShell-bibliotek för SQL Server, SharePoint Server och Azure. Glöm inte T-SQL, vilket kan bidra till att minska tiden för att konfigurera och underhålla din katastrof-återställning.
  
## <a name="disaster-recovery-roadmap"></a>Översikt över katastrof återställning

![Visuell representation av översikt över SharePoint-återställning.](../media/Azure-DRroadmap.png)
  
Denna översikt förutsätter att du redan har en SharePoint Server 2013-servergrupp distribuerad i produktion.
  
**Tabell: översikt för katastrof återställning**

|**Fas**|**Beskrivning**|
|:-----|:-----|
|Fas 1  <br/> |Designa en katastrof återställnings miljö.  <br/> |
|Fas 2  <br/> |Skapa ett Azure Virtual Network-och VPN-anslutning.  <br/> |
|Fas 3  <br/> |Distribuera Windows Active Directory och domän namn tjänster till det virtuella Azure-nätverket.  <br/> |
|Fas 4  <br/> |Distribuera SharePoint-återställnings gruppen i Azure.  <br/> |
|Fas 5  <br/> |Konfigurera DFSR mellan Server grupperna.  <br/> |
|Fas 6  <br/> |Konfigurera logg överföring till återställnings gruppen.  <br/> |
|Fas 7  <br/> | Validera lösningar för redundans och återställning. Detta inkluderar följande procedurer och tekniker: <br/>  Avbryt leverans. <br/>  Återställ säkerhets kopiorna. <br/>  Crawlar innehåll. <br/>  Återställ tjänster. <br/>  Hantera DNS-poster. <br/> |
   
## <a name="phase-1-design-the-disaster-recovery-environment"></a>Fas 1: designa katastrof återställnings miljön

Använd vägledningen i [Microsoft Azure-arkitekturer för SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) för att designa katastrof-och återställnings miljön, inklusive SharePoint Recovery-gruppen. Du kan använda grafiken i lösningen för [katastrof återställning för SharePoint i Azure](https://go.microsoft.com/fwlink/p/?LinkId=392554) Visio-filen för att starta design processen. Vi rekommenderar att du utformar hela miljön innan du påbörjar något arbete i Azure-miljön.
  
Utöver vägledningen i [Microsoft Azure-arkitekturer för SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) för att designa det virtuella nätverket, VPN-anslutning, Active Directory och SharePoint-servergruppen bör du lägga till en fil resurs roll i Azure-miljön.
  
För att du ska kunna använda logg överföring i en katastrof lösning för återställning, läggs en virtuell dator för fil delning till under nätet där databas roller lagras. Fil resursen fungerar också som den tredje noden i Node majoritet för SQL Server AlwaysOn-tillgänglighetsgruppen. Det här är den rekommenderade konfigurationen för en standard-SharePoint-servergrupp som använder SQL Server AlwaysOn-tillgänglighetsgruppen. 
  
> [!NOTE]
> Det är viktigt att kontrol lera förutsättningarna för att en databas ska ingå i en SQL Server AlwaysOn-tillgänglighetsgruppen. Mer information finns i [förutsättningar, begränsningar och rekommendationer för grupper med AlwaysOn-tillgänglighet](https://go.microsoft.com/fwlink/p/?LinkId=510870). 
  
**Bild: placering av en fil server som används för en katastrof återställnings lösning**

![Visar en fil resurs som har lagts till i en moln tjänst som innehåller SharePoint-databasens Server roller.](../media/AZenv-FSforDFSRandWSFC.png)
  
I det här diagrammet läggs en virtuell dator för fil resurs till i samma undernät i Azure som innehåller databas server rollerna. Lägg inte till den virtuella datorn för fil delning i en tillgänglighets uppsättning med andra Server roller, till exempel SQL Server-roller.
  
Om du är orolig för att loggarna är mer lättillgängliga kan du överväga att använda [säkerhets kopiering och återställning i SQL Server med Azure Blob Storage-tjänsten](https://go.microsoft.com/fwlink/p/?LinkId=393113). Det här är en ny funktion i Azure som sparar loggar direkt i en BLOB-lagringsenhet. Den här lösningen innehåller ingen vägledning om hur du använder den här funktionen.
  
När du utformar återställnings gruppen bör du tänka på att en lyckad katastrof återställnings miljö exakt återspeglar den produktions grupp som du vill återställa. Storleken på återställnings gruppen är inte det viktigaste i återställnings gruppens design, distribution och testning. Server gruppens skala varierar från organisation till organisation baserat på företagets behov. Det kan vara möjligt att använda en skalad upphöjd Server för ett kort avbrott eller till att prestanda-och kapacitets kraven kräver att du skalar Server gruppen.
  
Konfigurera återställnings gruppen så exakt som möjligt till produktions gruppen så att den uppfyller villkoren för service nivå avtalet (SLA) och ger de funktioner som behövs för ditt företag. När du utformar en katastrof återställnings miljö kan du även titta på processen för ändrings hantering för din produktions miljö. Vi rekommenderar att du utökar processen för ändrings hantering till återställnings miljön genom att uppdatera återställnings miljön till samma intervall som produktions miljön. Som en del av processen för ändrings hantering rekommenderar vi att du underhåller en detaljerad inventering av din konfiguration, dina program och användare. 
  
## <a name="phase-2-create-the-azure-virtual-network-and-vpn-connection"></a>Fas 2: skapa ett Azure Virtual Network-och VPN-anslutning

[Ansluta ett lokalt nätverk till ett Microsoft Azure-nätverk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md) visar dig hur du planerar och distribuerar det virtuella nätverket i Azure och hur du skapar VPN-anslutningen. Följ anvisningarna i avsnittet för att utföra följande procedurer:
  
- Planera det privata IP-adressutrymmet för det virtuella nätverket.
    
- Planera ändringar i infrastrukturen för routning för det virtuella nätverket.
    
- Planera brand Väggs regler för trafik till och från den lokala VPN-enheten.
    
- Skapa det korslänkade virtuella nätverket i Azure.
    
- Konfigurera routning mellan det lokala nätverket och det virtuella nätverket.
    
## <a name="phase-3-deploy-active-directory-and-domain-name-services-to-the-azure-virtual-network"></a>Fas 3: distribuera Active Directory och domän namn tjänster till det virtuella Azure-nätverket

I den här fasen kan du distribuera både Windows Server Active Directory och DNS till det virtuella nätverket i ett hybrid scenario som beskrivs i [Microsoft Azure-arkitekturer för SharePoint 2013](microsoft-azure-architectures-for-sharepoint-2013.md) och som illustreras i följande bild.
  
**Bild: konfiguration av hybrid Active Directory-domäner**

![Två virtuella datorer distribueras till det virtuella Azure-nätverket och SharePoint-servergruppen är replik domän kontrol Lanterna och DNS-servrar](../media/AZarch-HyADdomainConfig.png)
  
I bilden distribueras två virtuella datorer till samma undernät. De här virtuella datorerna är båda roller: Active Directory och DNS.
  
Innan du distribuerar Active Directory i Azure läser du [rikt linjer för distribution av Windows Server Active Directory på virtuella Azure-datorer](https://go.microsoft.com/fwlink/p/?linkid=392681). Dessa rikt linjer hjälper dig att avgöra om du behöver en annan arkitektur eller olika konfigurations inställningar för din lösning.
  
Utförlig information om hur du konfigurerar en domänkontrollant i Azure finns i [installera en Active Directory-domänkontrollant i Azure Virtual Networks](https://go.microsoft.com/fwlink/p/?LinkId=392687).
  
Före den här fasen distribuerades inte virtuella datorer till det virtuella nätverket. De virtuella datorerna för att vara värd för Active Directory och DNS är förmodligen inte de största virtuella datorerna som behövs för lösningen. Innan du distribuerar de här virtuella datorerna måste du först skapa den största virtuella dator som du planerar att använda i ditt virtuella nätverk. På så sätt ser du till att lösningen hamnar på en tagg i Azure som gör den största storleken du behöver. Du behöver inte konfigurera den här virtuella datorn för närvarande. Det är bara att skapa det och sätta undan det. Om du inte gör det kanske du stöter på en begränsning när du försöker att skapa större virtuella datorer senare, vilket var ett problem när den här artikeln skrevs. 
  
## <a name="phase-4-deploy-the-sharepoint-recovery-farm-in-azure"></a>Fas 4: Distribuera återställnings gruppen för SharePoint i Azure

Distribuera SharePoint-servergruppen i ditt virtuella nätverk enligt dina design planer. Det kan vara bra att granska [planering för sharepoint 2013 i Azure Infrastructure Services](https://go.microsoft.com/fwlink/p/?LinkId=400984) innan du distribuerar SharePoint-roller i Azure.
  
Tänk på följande saker som vi lärt dig genom att bygga vår proof of Concept-miljön:
  
- Skapa virtuella datorer med Azure-portalen eller PowerShell.
    
- Azure och Hyper-V stöder inte dynamiskt minne. Se till att det här är en faktor för dina prestanda-och kapacitets planer.
    
- Starta om virtuella datorer via Azure-gränssnittet, inte från den virtuella dator inloggningen. Att använda Azure-gränssnittet fungerar bättre och kan förutsägbart.
    
- Om du vill stänga av en virtuell dator för att spara kostnaderna använder du Azure-gränssnittet. Om du stänger av den virtuella dator inloggningen fortsätter avgifterna att påföras.
    
- Använd en namngivnings konvention för de virtuella datorerna.
    
- Observera att den data Center plats som de virtuella datorerna distribueras till är uppmärksam.
    
- Funktionen för automatisk skalning i Azure stöds inte för SharePoint-roller.
    
- Konfigurera inte objekt i Server gruppen som ska återställas, till exempel webbplats samlingar. 
    
## <a name="phase-5-set-up-dfsr-between-the-farms"></a>Fas 5: Konfigurera DFSR mellan Server grupperna

Om du vill konfigurera filreplikering med hjälp av DFSR använder du snapin-modulen DNS-hantering. Men innan DFSR-installationen loggar du in på lokal fil server och Azure-filserver och aktiverar tjänsten i Windows.
  
Utför följande steg från instrument panelen i Server hanteraren:
  
- Konfigurera den lokala servern.
    
- Starta **guiden Lägg till roller och funktioner**.
    
- Öppna noden **fil-och lagrings tjänster** .
    
- Välj **DFS-namnområden** och **DFS-replikering**.
    
- Avsluta guiden genom att klicka på **Nästa** .
    
Följande tabell innehåller länkar till DFSR-referenser och blogg inlägg.
  
**Tabell: referens artiklar för DFSR**

|**Title**|**Beskrivning**|
|:-----|:-----|
|[Replikeringsgrupp](https://go.microsoft.com/fwlink/p/?LinkId=392732) <br/> |DFS-hantering TechNet-ämne med länkar för replikering  <br/> |
|[DFS-replikering: livräddnings guide](https://go.microsoft.com/fwlink/p/?LinkId=392737) <br/> |Wiki med länkar till DFS-information  <br/> |
|[DFS-replikering: vanliga frågor och svar](https://go.microsoft.com/fwlink/p/?LinkId=392738) <br/> |DFS-replikering, TechNet-ämne  <br/> |
|[Jose Barretos blogg](https://go.microsoft.com/fwlink/p/?LinkId=392739) <br/> |Blogg skriven av en huvudsaklig program chef i fil Server gruppen på Microsoft  <br/> |
|[Lagrings gruppen på bloggen Microsoft-Arkiv skåp](https://go.microsoft.com/fwlink/p/?LinkId=392740) <br/> |Blogg om fil tjänster och lagrings funktioner i Windows Server  <br/> |
   
## <a name="phase-6-set-up-log-shipping-to-the-recovery-farm"></a>Fas 6: Konfigurera en logg överföring till återställnings gruppen

Logg överföring är den kritiska komponenten för att konfigurera en katastrof återställning i den här miljön. Du kan använda logg överföring för att automatiskt skicka transaktionsloggfiler för databaser från en primär databas Server instans till en sekundär databas Server instans. Information om hur du ställer in logg överföring finns i [Konfigurera logg överföring i SharePoint 2013](https://docs.microsoft.com/sharepoint/administration/configure-log-shipping). 
  
> [!IMPORTANT]
> Stöd för loggnings leverans i SharePoint Server är begränsat till vissa databaser. Mer information finns i [alternativ för hög tillgänglighet och katastrof återställning för SharePoint-databaser (sharepoint 2013)](https://go.microsoft.com/fwlink/p/?LinkId=393121). 
  
## <a name="phase-7-validate-failover-and-recovery"></a>Fas 7: verifiera redundans och återställning

Målet med den här sista fasen är att kontrol lera att lösningen för katastrof återställning fungerar som planerat. Det gör du genom att skapa en redundansrelation som stänger av produktions gruppen och startar återställnings gruppen som en ersättning. Du kan starta ett failover-scenario manuellt eller med hjälp av skript.
  
Det första steget är att stoppa inkommande användar förfrågningar för Server gruppen eller innehållet. Du kan göra detta genom att inaktivera DNS-poster eller stänga av front webb servrarna. Efter att Server gruppen är "ner" kan du växla över till återställnings gruppen.
  
### <a name="stop-log-shipping"></a>Stoppa logg överföring

Du måste stoppa logg överföring innan Server återställning. Stoppa loggning på den sekundära servern i Azure först och stoppa den sedan på den primära lokala servern. Använd följande skript för att avsluta loggning på den sekundära servern först och sedan på den primära servern. Databas namnen i skriptet kan variera beroende på din miljö.
  
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

### <a name="restore-the-backups"></a>Återställa säkerhets kopiorna

Säkerhets kopior måste återställas i den ordning som de skapades. Innan du kan återställa en särskild säkerhets kopia av en transaktions logg måste du först återställa följande tidigare säkerhets kopior utan att ångra en obekräftad transaktion (d.v.s. genom att använda  `WITH NORECOVERY` ):
  
- Den fullständiga säkerhets kopieringen av databasen och den senaste differentiella säkerhets kopian – återställer dessa säkerhets kopior, om sådana finns, före den aktuella säkerhets kopieringen av transaktions logg. Innan den senaste fullständiga eller differentiella databas säkerhets kopian skapades användes den fullständiga återställnings modellen eller återställnings modellen för Mass utloggning.
    
- Alla säkerhets kopior av transaktions loggar – Återställ eventuella säkerhets kopior av transaktions loggar som gjorts efter den fullständiga säkerhets kopieringen av databasen eller den differentiella säkerhets kopian (om du återställer en) och före den specifika säkerhets kopiering Logg säkerhets kopior måste tillämpas i den ordning som de skapades, utan luckor i logg kedjan.
    
Om du vill återställa innehålls databasen på den sekundära servern så att webbplatserna renderas tar du bort alla databas anslutningar innan återställning. Om du vill återställa databasen kör du följande SQL-uttryck.
  
```
restore database WSS_Content with recovery

```

> [!IMPORTANT]
> När du använder T-SQL explicit kan du ange antingen **med NORECOVERY** eller **med återställning** i varje Restore-sats för att undvika tvetydighet – det här är mycket viktigt när du skriver skript. När alla säkerhets kopior har återställts kan transaktions loggar återställas i SQL Server Management Studio. Eftersom logg överföring redan har stoppats är innehålls databasen i vänte läge, så du måste ändra tillståndet till full åtkomst.
  
I SQL Server Management Studio högerklickar du på **WSS_Content** databasen, pekar på **uppgifter**  >  **Återställ**och klickar sedan på **transaktions logg** (om du inte har återställt den fullständiga säkerhets kopian är det inte tillgängligt). Mer information finns i[återställa en säkerhets kopia av en transaktions logg (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=392778).
  
### <a name="crawl-the-content-source"></a>Crawla innehålls källan

Du måste påbörja en fullständig crawlning för varje innehålls källa för att återställa Sök tjänsten. Observera att du förlorar lite analys information från den lokala server gruppen, till exempel Sök rekommendationer. Innan du börjar med fullständig crawlning kan du använda Windows PowerShell cmdlet **restore-SPEnterpriseSearchServiceApplication** och ange den loggade och replikerade Sök administrations databasen **, <GUID> Search_Service__DB_**. Denna cmdlet ger Sök konfiguration, schema, hanterade egenskaper, regler och källor och skapar en standard uppsättning med andra komponenter.
  
Gör så här om du vill starta en fullständig crawlning:
  
1. Gå till **program hanterings**  >  **tjänst program**  >  **Hantera tjänst program**i SharePoint 2013 Central administration och klicka sedan på det Sök tjänst program som du vill crawla.
    
2. Klicka på **innehålls källor**på sidan **Sök administration** , peka på den innehålls källa som du vill använda, klicka på pilen och klicka sedan på **Starta fullständig crawlning**.
    
### <a name="recover-farm-services"></a>Återställa Server grupps tjänster

I följande tabell visas hur du återställer tjänster som har en databas som har loggats fram, tjänster som har databaser men inte rekommenderas att återställa med logg överföring och de tjänster som inte har databaser.
  
> [!IMPORTANT]
> Återställning av en lokal SharePoint-databas till Azure-miljön återställer inte några SharePoint-tjänster som du inte redan har installerat i Azure manuellt. 
  
**Tabell: databas referens för tjänst program**

|**Återställ dessa tjänster från en log-skeppade databaser**|**De här tjänsterna har databaser, men vi rekommenderar att du startar dessa tjänster utan att återställa sina databaser**|**Dessa tjänster lagrar inte data i databaser; starta de här tjänsterna efter redundans**|
|:-----|:-----|:-----|
| Maskin översättnings tjänst <br/>  Hanterad metadatatjänst <br/>  Säker lagrings tjänst <br/>  Användar profil. (Det går bara att använda databaserna profil och sociala taggar. Databasen synkronisering stöds inte.) <br/>  Tjänst för prenumerations inställningar för Microsoft SharePoint Foundation <br/> | Insamling av användnings-och hälso data <br/>  Tillstånds tjänst <br/>  Word-automatisering <br/> | Excel-tjänster <br/>  PerformancePoint-tjänster <br/>  PowerPoint-konvertering <br/>  Visio-grafiktjänsten <br/>  Arbets hantering <br/> |
   
I följande exempel visas hur du återställer den hanterade metadatatjänsten från en databas.
  
Då används den befintliga Managed_Metadata_DB-databasen. Denna databas är loggad, men det finns inget aktivt tjänst program i den sekundära Server gruppen, så den måste anslutas efter att tjänst programmet är på plats.
  
Använd först  `New-SPMetadataServiceApplication` och ange  `DatabaseName` namnet på den återställda databasen.
  
Konfigurera sedan den nya hanterade metadatatjänsten på den sekundära servern så här:
  
- Namn: hanterad metadatatjänst
    
- Databas server: databas namnet från den skickade transaktions loggen
    
- Databas namn: Managed_Metadata_DB
    
- Programpool: SharePoint-tjänstprogram 
    
### <a name="manage-dns-records"></a>Hantera DNS-poster

Du måste manuellt skapa DNS-poster för att kunna peka på SharePoint-servergruppen.
  
I de flesta fall där du har flera front webb servrar är det lämpligt att utnyttja funktionen Utjämning av nätverks belastning i Windows Server 2012 eller en maskinvarubaserad belastnings fördelning för att distribuera förfrågningar mellan webb frontend-servrarna i Server gruppen. Belastnings utjämning kan minska risken genom att distribuera förfrågningar till de andra servrarna om en av dina webb servrar Miss lyckas. 
  
När du konfigurerar utjämning av nätverks belastning är ditt kluster till en enda IP-adress. Du skapar sedan en DNS-värd för det nätverk som pekar på klustret. (För det här projektet lägger vi till en DNS-server i Azure för återhämtning i händelse av ett lokalt Data Center fel.) Du kan t ex skapa en DNS-post i DNS Manager i Active Directory, till exempel called  `https://sharepoint.contoso.com` , som pekar mot IP-adressen för ditt belastningsutjämnade kluster.
  
För extern åtkomst till SharePoint-servergruppen kan du skapa en värd post på en extern DNS-server med samma URL som klienterna använder på intranätet (till exempel `https://sharepoint.contoso.com` ) som pekar på en extern IP-adress i brand väggen. (Det här exemplet är ett bra sätt att konfigurera delad DNS så att den interna DNS-servern är auktoritär för `contoso.com` och dirigerar begär Anden direkt till SharePoint-servergruppen, i stället för att dirigera DNS-begäranden till din externa DNS-server.) Du kan sedan mappa den externa IP-adressen till det lokala klustrets interna IP-adress så att klienter hittar de resurser de letar efter.
  
Härifrån kan du stöta på ett par olika katastrof-återställning:
  
 **Exempel på scenario: den lokala SharePoint-servergruppen är inte tillgänglig på grund av maskin varu fel i den lokala SharePoint-servergruppen.** I det här fallet när du har slutfört stegen för redundans till Azure SharePoint-servergruppen kan du konfigurera utjämning av nätverks belastning på återställnings Server gruppens front servrar på samma sätt som du använde den lokala server gruppen. Du kan sedan omdirigera värd posten i den interna DNS-leverantören så att den pekar på återställnings gruppens kluster-IP-adress. Observera att det kan ta en stund innan cachade DNS-poster på klienter uppdateras och peka på återställnings gruppen.
  
 **Exempel på scenario: det lokala data centret försvinner helt.** Det här scenariot kan uppstå på grund av en natur katastrof, till exempel en brand eller översvämning. I det här fallet är det troligt att ett sekundärt Data Center hanteras i en annan region samt ditt Azure-undernät som har sina egna katalog tjänster och DNS. Precis som i föregående katastrof scenario kan du omdirigera de interna och externa DNS-posterna så att de pekar på Azure SharePoint-servergruppen. Observera att DNS-postdistribution kan ta lite tid.
  
Om du använder en webbplats samling med värden som heter värd, som rekommenderas i en [arkitektur och distribution (SharePoint 2013) av värd-namn](https://docs.microsoft.com/SharePoint/administration/host-named-site-collection-architecture-and-deployment), kan du ha flera webbplats samlingar som hanteras av samma webb program i SharePoint-servergruppen, med unika DNS-namn (till exempel `https://sales.contoso.com` och `https://marketing.contoso.com` ). I det här fallet kan du skapa DNS-poster för varje webbplats samling som pekar på klustrets IP-adress. När en begäran når dina SharePoint-webbservrar kan de cirkulera varje begäran till en lämplig webbplats samling.
  
## <a name="microsoft-proof-of-concept-environment"></a>Microsoft proof-of-Concept-miljö

Vi har utformat och testat en miljö för koncept bevis för den här lösningen. Design målet för vår test miljö var att distribuera och återställa en SharePoint-servergrupp som vi kan hitta i en kund miljö. Vi har gjort flera antaganden, men vi visste att Server gruppen behövde tillhandahålla alla infärdiga funktioner utan några anpassningar. Topologin är utformad för hög tillgänglighet genom att använda vägledning från fältet och produkt gruppen.
  
I följande tabell beskrivs de virtuella Hyper-V-datorer som vi har skapat och konfigurerat för den lokala test miljön.
  
**Tabell: virtuella datorer för lokalt test**

|**Server namn**|**Roll**|**Konfiguration**|
|:-----|:-----|:-----|
|DC1  <br/> |Domänkontrollant med Active Directory.  <br/> |Två processorer  <br/> Från 512 MB till 4 GB RAM-minne  <br/> 1 x 127-GB hård disk  <br/> |
|TJÄNSTEN  <br/> |Server som konfigureras med RRAS-rollen (Routing and Remote Access Service).  <br/> |Två processorer  <br/> 2-8 GB RAM  <br/> 1 x 127-GB hård disk  <br/> |
|FS1  <br/> |Fil server med resurser för säkerhets kopior och en slut punkt för DFSR.  <br/> |Fyra processorer  <br/> 2-12 GB RAM  <br/> 1 x 127-GB hård disk  <br/> 1 x 1-TB hård disk (SAN)  <br/> 1 x 750-GB hård disk  <br/> |
|SP-WFE1, SP-WFE2  <br/> |Front webb servrar.  <br/> |Fyra processorer  <br/> 16 GB RAM  <br/> |
|SP-APP1, SP-APP2, SP-APP3  <br/> |Program servrar.  <br/> |Fyra processorer  <br/> 2-16 GB RAM  <br/> |
|SP-SQL-HA1, SP-SQL-HA2  <br/> |Databas servrar, konfigurerade med SQL Server 2012 AlwaysOn-tillgänglighetsgruppen för att ge hög tillgänglighet. Denna konfiguration använder SP-SQL-HA1 och SP-SQL-HA2 som primär-och sekundär repliker.  <br/> |Fyra processorer  <br/> 2-16 GB RAM  <br/> |
   
I följande tabell beskrivs de olika poolinställningarna för de virtuella Hyper-V-datorerna som vi har skapat och konfigurerat för front webb-och program servrar för den lokala test miljön.
  
**Tabell: enhets krav för virtuell dator för front webb och program servrar för det lokala testet**

|**Enhets beteckning**|**Storlek**|**Katalog namn**|**Bana**|
|:-----|:-----|:-----|:-----|
|F  <br/> |80  <br/> |Systemen het  <br/> |<DriveLetter>: \\ Program \\ Microsoft SQL Server\\  <br/> |
|Tomé  <br/> |80  <br/> |Loggen het (40 GB)  <br/> |<DriveLetter>: \\ Program \\ Microsoft SQL Server \\ MSSQL10_50. MSSQLSERVER \\ MSSQL- \\ data  <br/> |
|D  <br/> |80  <br/> |Sida (36 GB)  <br/> |<DriveLetter>: \\ Program \\ data för Microsoft SQL Server \\ MSSQL \\  <br/> |
   
I följande tabell beskrivs poolinställningarna för de virtuella Hyper-V-datorer som skapas och konfigureras för att fungera som lokala databas servrar. På sidan **databas motor konfiguration** går du till fliken **data kataloger** för att ange och bekräfta inställningarna i följande tabell.
  
**Tabell: enhets krav för virtuell dator för databas servern för det lokala testet**

|**Enhets beteckning**|**Storlek**|**Katalog namn**|**Bana**|
|:-----|:-----|:-----|:-----|
|F  <br/> |80  <br/> |Data rot Katalog  <br/> |<DriveLetter>: \\ Program \\ Microsoft SQL Server\\  <br/> |
|Tomé  <br/> |500  <br/> |Katalog för användar databas  <br/> |<DriveLetter>: \\ Program \\ Microsoft SQL Server \\ MSSQL10_50. MSSQLSERVER \\ MSSQL- \\ data  <br/> |
|D  <br/> |500  <br/> |Katalog för användar databas logg  <br/> |<DriveLetter>: \\ Program \\ Microsoft SQL Server \\ MSSQL10_50. MSSQLSERVER \\ MSSQL- \\ data  <br/> |
|Gram  <br/> |500  <br/> |Tillfällig DB-katalog  <br/> |<DriveLetter>: \\ Program \\ Microsoft SQL Server \\ MSSQL10_50. MSSQLSERVER \\ MSSQL- \\ data  <br/> |
|T  <br/> |500  <br/> |Temp DB log-katalog  <br/> |<DriveLetter>: \\ Program \\ Microsoft SQL Server \\ MSSQL10_50. MSSQLSERVER \\ MSSQL- \\ data  <br/> |
   
### <a name="setting-up-the-test-environment"></a>Ställa in test miljön

Under de olika distributions faserna fungerade test gruppen normalt på den lokala arkitekturen och sedan i motsvarande Azure-miljö. Detta återspeglar de allmänna reella ärenden där anläggnings anläggningar redan körs. Vad är ännu viktigare är att du bör känna till aktuell arbets belastning, kapacitet och typisk prestanda. Förutom att skapa en katastrof återställnings modell som kan uppfylla företags krav bör du ställa in en storlek på Server för återställnings servrar för att tillhandahålla en minimal tjänste nivå. I en miljö med kall och varm-standby är en återställnings Server normalt mindre än en produktions grupp. När återställnings gruppen är stabil och i produktion kan Server gruppen skalas upp och ut för att uppfylla arbets belastnings kraven.
  
Vi har distribuerat vår test miljö i följande tre faser:
  
- Konfigurera hybrid infrastrukturen
    
- Etablera servrar
    
- Distribuera SharePoint-servergrupperna
    
#### <a name="set-up-the-hybrid-infrastructure"></a>Konfigurera hybrid infrastrukturen

Den här fasen berör konfiguration av en domän miljö för den lokala server gruppen och för återställnings gruppen i Azure. Utöver de vanliga uppgifter som är kopplade till att konfigurera Active Directory implementerar test gruppen en lösning för Routning och en VPN-anslutning mellan de båda miljöerna.
  
#### <a name="provision-the-servers"></a>Etablera servrar

Utöver Server grupperna är det nödvändigt att etablera servrar för domän kontrol Lanterna och konfigurera en server för att hantera RRAS samt webbplats-till-plats-VPN. Två fil servrar etablerades för DFSR-tjänsten och flera klient datorer etablerades för testare.
  
#### <a name="deploy-the-sharepoint-farms"></a>Distribuera SharePoint-servergrupperna

SharePoint-servergrupperna distribuerades i två steg för att förenkla miljö stabilisering och fel sökning, om så behövs. Under det första steget distribuerades varje server grupp på det minsta antalet servrar för varje nivå i topologin som stöd för de nödvändiga funktionerna.
  
Vi har skapat databas servrar med SQL Server installerat innan du skapar SharePoint 2013-servrarna. Eftersom det var en ny distribution skapade vi tillgänglighets grupperna innan du distribuerade SharePoint. Vi har skapat tre grupper baserat på MCS-vägledningen för bästa praxis. 
  
> [!NOTE]
> Skapa databas plats hållare så att du kan skapa tillgänglighets grupper före SharePoint-installationen. Mer information finns i [Konfigurera SQL Server 2012 AlwaysOn-tillgänglighetsgruppen för SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=517626)
  
Vi skapade Server gruppen och anslöt till ytterligare servrar i följande ordning:
  
- Tillhandahålla SP-SQL-HA1 och SP-SQL-HA2.
    
- Konfigurera AlwaysOn och skapa de tre tillgänglighets grupperna för Server gruppen. 
    
- Etablerar SP-APP1 som värd Central administration.
    
- Etablerar SP-WFE1 och SP-WFE2 som värd för det distribuerade cacheminnet. 
    
Vi använde  _skipRegisterAsDistributedCachehost_ -parametern när vi körde **psconfig.exe** på kommando raden. Mer information finns i [Planera för feeds och tjänsten distribuerad cache i SharePoint Server 2013](https://docs.microsoft.com/sharepoint/administration/plan-for-feeds-and-the-distributed-cache-service). 
  
Vi har upprepat följande steg i återställnings miljön:
  
- Tillhandahåll AZ-SQL-HA1 och AZ-SQL-HA2.
    
- Konfigurera AlwaysOn och skapa de tre tillgänglighets grupperna för Server gruppen.
    
- Tillhandahåll AZ-APP1 till Central administration.
    
- Etablera AZ-WFE1 och AZ-WFE2 för att vara värd för det distribuerade cacheminnet.
    
När vi har konfigurerat det distribuerade cacheminnet och lagt till test användare och test innehåll startade vi steg två av distributionen. Detta erfordrar en skalning av nivåerna och konfigurering av Server gruppens servrar för att stödja topologi med hög tillgänglighet som beskrivs i Server gruppen.
  
I följande tabell beskrivs de virtuella datorerna, undernät och tillgänglighets uppsättningar som vi har konfigurerat för vår återställnings Server.
  
**Tabell: återställnings infrastruktur för grupp**

|**Server namn**|**Roll**|**Konfiguration**|**Under**|**Tillgänglighets uppsättning**|
|:-----|:-----|:-----|:-----|:-----|
|spDRAD  <br/> |Domänkontrollant med Active Directory  <br/> |Två processorer  <br/> Från 512 MB till 4 GB RAM-minne  <br/> 1 x 127-GB hård disk  <br/> |SP-ADservers  <br/> ||
|AZ-SP-FS  <br/> |Fil server med resurser för säkerhets kopior och en slut punkt för DFSR  <br/> | A5-konfiguration: <br/>  Två processorer <br/>  14 GB RAM <br/>  1 x 127-GB hård disk <br/>  1 x 135-GB hård disk <br/>  1 x 127-GB hård disk <br/>  1 x 150-GB hård disk <br/> |SP-databaseservers  <br/> |DATA_SET  <br/> |
|AZ-WFE1, AZ-WFE2  <br/> |Front webb servrar  <br/> | A5-konfiguration: <br/>  Två processorer <br/>  14 GB RAM <br/>  1 x 127-GB hård disk <br/> |SP-webserver  <br/> |WFE_SET  <br/> |
|AZ-APP1, AZ-APP2, AZ-APP3  <br/> |Program servrar  <br/> | A5-konfiguration: <br/>  Två processorer <br/>  14 GB RAM <br/>  1 x 127-GB hård disk <br/> |SP-applicationservers  <br/> |APP_SET  <br/> |
|AZ-SQL-HA1, AZ-SQL-HA2  <br/> |Databas servrar och primära och sekundära repliker för grupp för AlwaysOn-tillgänglighet  <br/> | A5-konfiguration: <br/>  Två processorer <br/>  14 GB RAM <br/> |SP-databaseservers  <br/> |DATA_SET  <br/> |
   
### <a name="operations"></a>Åtgärder

Efter att test gruppen stabiliserat Server grupps miljö och utförde funktionell testning startade de följande åtgärder som krävs för att konfigurera den lokala återställnings miljön:
  
- Konfigurera fullständig och differentiell säkerhets kopiering.
    
- Konfigurera DFSR på fil servrar som överför transaktions loggar mellan den lokala miljön och Azure-miljön.
    
- Konfigurera logg överföring på den primära databas servern.
    
- Stabilisera, validera och Felsök logg överföring, efter behov. Detta gäller identifiering och dokumenterar alla funktioner som kan orsaka problem, till exempel nätverks svars tid, som orsakar misslyckade loggningar av överförings-eller DFSR-filer.
    
### <a name="databases"></a>Samling

Våra failover-test involverade följande databaser: 
  
- WSS_Content
    
- ManagedMetadata
    
- Profil databas
    
- Synkronisera DB
    
- Social DB
    
- Innehålls typs nav (en databas för dedikerade innehålls typs syndikering)
    
## <a name="troubleshooting-tips"></a>Fel söknings tips

I avsnittet förklaras de problem som vi påträffade när vi testar och deras lösningar. 
  
### <a name="using-the-term-store-management-tool-caused-the-error-the-managed-metadata-store-or-connection-is-currently-not-available"></a>Om du använder verktyget för hantering av term lagrings plats uppstod felet "den hanterade metadatalagret eller anslutningen är för tillfället inte tillgänglig."

Kontrol lera att programpoolskontot som används av webb programmet har Läs behörighet för term lagrings platsen.
  
### <a name="custom-term-sets-are-not-available-in-the-site-collection"></a>Anpassade term uppsättningar är inte tillgängliga i webbplats samlingen

Sök efter en tjänst program Association saknas mellan innehålls webbplats samlingen och innehålls typs navet. Under sidan Egenskaper för **hanterade metadata kan <site collection name> ** du dessutom kontrol lera att det här alternativet är aktiverat: **det här tjänst programmet är standard lagrings platsen för kolumn specifika term uppsättningar.**
  
### <a name="the-get-adforest-windows-powershell-command-generates-the-error-the-term-get-adforest-is-not-recognized-as-the-name-of-a-cmdlet-function-script-file-or-operable-program"></a>Kommandot Get-ADForest Windows PowerShell genererar felet "termen ' Get-ADForest ' känns inte igen som namnet på en cmdlet, funktion, skript fil eller program."

När du konfigurerar användar profiler behöver du Active Directory-skogens namn. I guiden Lägg till roller och funktioner ser du till att du har aktiverat Active Directory-modulen för Windows PowerShell (under verktyg för **>fjärrserveradministration>AD DS och AD LDS-verktyg** ). Kör dessutom följande kommandon innan du använder **Get-ADForest** för att säkerställa att program varan är inläst.
  
```
Import-module servermanager
Import-module activedirectory

```

### <a name="availability-group-creation-fails-at-starting-the-alwayson_health-xevent-session-on-server-name"></a>Det går inte att skapa tillgänglighets gruppen genom att starta AlwaysOn_health XEvent-session på ' <server name> '

Se till att båda noderna i ditt failover-kluster har statusen "upp" och inte "pausad" eller "stoppad". 
  
### <a name="sql-server-log-shipping-job-fails-with-access-denied-error-trying-to-connect-to-the-file-share"></a>SQL Server log-leveransen Miss lyckas med åtkomst nekad vid försök att ansluta till fil resursen

Kontrol lera att din SQL Server-Agent körs under nätverks referenser, i stället för standardinställningarna.
  
### <a name="sql-server-log-shipping-job-indicates-success-but-no-files-are-copied"></a>Överförings jobbet för SQL Server-loggning anger att det lyckades, men inga filer har kopierats

Det här beror på att standard säkerhets kopierings inställningen för en tillgänglighets grupp **föredrar sekundärt**. Se till att du kör logg leverans jobbet från den sekundära servern för tillgänglighets gruppen istället för den primära; annars kommer jobbet att Miss lyckas. 
  
### <a name="managed-metadata-service-or-other-sharepoint-service-fails-to-start-automatically-after-installation"></a>Hanterad metadatatjänst (eller annan SharePoint-tjänst) kan inte starta automatiskt efter installationen

Det kan ta flera minuter att starta tjänster beroende på prestanda och aktuell belastning på SharePoint-servern. Klicka på **Starta** för tjänsten manuellt och ange lämplig tid för att starta och uppdatera sedan dess status med en gång. Om tjänsten förblir stoppad kan du aktivera SharePoint-diagnostikloggning, försöka starta tjänsten igen och sedan kontrol lera om det finns fel i loggen. Mer information finns i [Konfigurera diagnostikloggning i SharePoint 2013](https://docs.microsoft.com/sharepoint/administration/configure-diagnostic-logging)
  
### <a name="after-changing-dns-to-the-azure-failover-environment-client-browsers-continue-to-use-the-old-ip-address-for-the-sharepoint-site"></a>När du har ändrat DNS till Azure failover-miljön fortsätter klient webbläsarna att använda den gamla IP-adressen för SharePoint-webbplatsen

Din DNS-ändring kanske inte syns för alla klienter omedelbart. Utför följande kommando i en test klient med en upphöjd kommando tolk och försök att komma åt webbplatsen igen.
  
```
Ipconfig /flushdns
```

## <a name="additional-resources"></a>Ytterligare resurser

[Stöd för hög tillgänglighet och katastrof återställning för SharePoint-databaser](https://docs.microsoft.com/sharepoint/administration/supported-high-availability-and-disaster-recovery-options-for-sharepoint-databas)
  
[Konfigurera SQL Server 2012 AlwaysOn-tillgänglighetsgruppen för SharePoint 2013](https://go.microsoft.com/fwlink/p/?LinkId=393122)
  
## <a name="see-also"></a>Se även

[Microsoft 365-center för lösningar och arkitektur](../solutions/solution-architecture-center.md)



