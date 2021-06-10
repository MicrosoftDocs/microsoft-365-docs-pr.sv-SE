---
title: Microsoft Azure Arkitekturer för SharePoint 2013
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Architecture
- seo-marvel-apr2020
ms.assetid: 98fc1006-9399-4ff0-a216-c7c05820d822
description: Lär dig vilka typer av SharePoint 2013-lösningar som kan lagras i Microsoft Azure virtuella maskiner och hur du ställer in Azure så att det fungerar som värd för ett.
ms.openlocfilehash: eed74e2dcbe383f0f63e7f6ea2fc70fe7b51b1b3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924182"
---
# <a name="microsoft-azure-architectures-for-sharepoint-2013"></a>Microsoft Azure Arkitekturer för SharePoint 2013

Azure är en bra miljö för värd för en SharePoint Server 2013-lösning. I de flesta fall rekommenderar vi Microsoft 365, men en SharePoint servergrupp som finns i Azure kan vara ett bra alternativ för specifika lösningar. I den här artikeln beskrivs hur du SharePoint arkitekturlösningar så att de passar bra i Azure-plattformen. Följande två specifika lösningar används som exempel:
  
- [SharePoint Server 2013 katastrofåterställning i Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)
    
- [Webbplatser i Microsoft Azure med SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
    
## <a name="recommended-sharepoint-solutions-for-azure-infrastructure-services"></a>Rekommenderade SharePoint för Azure-infrastrukturtjänster

Azure-infrastrukturtjänster är ett tilltalande alternativ för värdtjänster SharePoint lösningar. Vissa lösningar är bättre lämpliga för den här plattformen än andra. I följande tabell visas rekommenderade lösningar.
  
|**Lösning**|**Därför rekommenderas den här lösningen för Azure**|
|:-----|:-----|
|Utvecklings- och testmiljöer  <br/> |Det är enkelt att skapa och hantera dessa miljöer.  <br/> |
|Katastrofåterställning av lokala SharePoint till Azure  <br/> |**Värdbaserad sekundär datacenter** Använd Azure i stället för att investera i ett sekundärt datacenter i en annan region. <br/> **Låg kostnad för katastrofåterställningsmiljöer** Underhålla och betala för färre resurser än en lokal katastrofåterställningsmiljö. Antalet resurser beror på vilken katastrofåterställningsmiljö du väljer: vänteläge för kallt tid, vänteläge för varmt eller vänteläge. <br/> **Mer plattform för elasticitet** Vid en katastrof kan du enkelt skala ut återställningsfarmen så SharePoint att uppfylla belastningskraven. Skala in när du inte längre behöver resurserna. <br/> Se [SharePoint Server 2013 Katastrofåterställning i Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md).  <br/> |
|Webbplatser på Internet som använder funktioner och skalning som inte är tillgängliga i Microsoft 365  <br/> |**Fokusera ditt arbete** Koncentrera dig på att skapa en bra webbplats i stället för att skapa infrastruktur. <br/> **Dra nytta av flexibiliteten i Azure** Ändra storleken på servergruppen för begäran genom att lägga till nya servrar och betala endast för resurser du behöver. Dynamisk maskintilldelning stöds inte (automatisk skalning). <br/> **Använda Azure Active Directory (AD)** Dra nytta av Azure AD för kundkonton. <br/> **Lägga SharePoint funktioner som inte är tillgängliga i Microsoft 365** Lägg till djuprapportering och webbanalys. <br/> Se [Webbplatser i Microsoft Azure med SharePoint Server 2013.](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)  <br/> |
|Programgrupper som stöder Microsoft 365 eller lokala miljöer  <br/> |**Skapa, testa och vara värd för** appar i Azure med stöd för både lokala miljöer och molnmiljöer. <br/> **Hantera den här** rollen i Azure i stället för att köpa ny maskinvara för lokala miljöer. <br/> |
   
För lösningar och arbetsbelastningar på intranät och samarbete bör du tänka på följande alternativ:
  
- Avgör om Microsoft 365 uppfyller dina affärskrav eller kan vara en del av lösningen. Microsoft 365 innehåller en omfattande funktionsuppsättning som alltid är uppdaterad.
    
- Om Microsoft 365 uppfyller inte alla affärskrav bör du överväga att göra en standardimplementering av den lokala SharePoint 2013 från Microsoft Consulting Services (MCS). En standardarkitektur kan vara en snabbare, billigare och enklare lösning för dig att stödja än en anpassad. 
    
- Om en standardimplementering inte uppfyller dina affärskrav kan du överväga en anpassad lokal lösning.
    
- Om det är viktigt att använda en molnplattform för dina affärskrav bör du överväga en standard eller anpassad implementering av SharePoint 2013 som finns i Azure-infrastrukturtjänster. SharePoint är mycket enklare att ge stöd i Azure än andra offentliga Microsoft-molnplattformar som inte är inbyggda.
    
## <a name="before-you-design-the-azure-environment"></a>Innan du utformar Azure-miljön

Den här artikeln använder exempel SharePoint topologier, men du kan använda dessa designkoncept med valfri SharePoint servergruppstopologi. Innan du utformar Azure-miljön bör du använda följande topologi, arkitektur, kapacitet och prestandavägledning för att utforma SharePoint servergruppen:
  
- [Arkitekturdesign för IT SharePoint 2013-proffs](/SharePoint/technical-reference/technical-diagrams)
    
- [Planera för prestanda- och kapacitetshantering i SharePoint Server 2013](/SharePoint/administration/performance-planning-in-sharepoint-server-2013)
    
## <a name="determine-the-active-directory-domain-type"></a>Fastställa Active Directory-domäntypen

Varje SharePoint förlitar sig på Active Directory för att tillhandahålla administrativa konton för servergruppskonfigurationen. För stunden finns det två alternativ för SharePoint lösningar i Azure. Dessa beskrivs i följande tabell.
  
|**Alternativ**|**Beskrivning**|
|:-----|:-----|
|Dedikerad domän  <br/> |Du kan distribuera en dedikerad och isolerad Active Directory-domän till Azure för att stödja SharePoint servergruppen. Det här är ett bra val för offentliga webbplatser.  <br/> |
|Utöka den lokala domänen genom en lokal anslutning  <br/> |När du utökar den lokala domänen genom en tvärlokal anslutning får användarna åtkomst till SharePoint-servergruppen via ditt intranät som om den vore värd lokal. Du kan dra nytta av din lokala Active Directory- och DNS-implementering.  <br/> En tvärlokal anslutning krävs för att bygga en katastrofåterställningsmiljö i Azure för att växla till från den lokala servergruppen.  <br/> |
   
Den här artikeln innehåller designbegrepp för utökning av den lokala domänen via en tvärlokal anslutning. Om lösningen använder en dedikerad domän behöver du inte en tvärlokal anslutning.
  
## <a name="design-the-virtual-network"></a>Designa det virtuella nätverket

Först behöver du ett virtuellt nätverk i Azure, som innehåller undernät där du ska placera dina virtuella datorer. Det virtuella nätverket behöver ett privat IP-adressutrymme, som du tilldelar undernäten till delar av.
  
Om du utökar det lokala nätverket till Azure via en tvärlokal anslutning (krävs för en katastrofåterställningsmiljö) måste du välja ett privat adressutrymme som inte redan används någon annanstans i organisationsnätverket, vilket kan inkludera din lokala miljö och andra virtuella Azure-nätverk. 
  
**Bild 1: Lokal miljö med ett virtuellt nätverk i Azure**

![Microsoft Azure nätverksdesign för en SharePoint lösning. Ett undernät för Azure Gateway. Ett undernät för virtuella datorer.](../media/OPrrasconWA-AZarch.png)
  
I det här diagrammet:
  
- Ett virtuellt nätverk i Azure illustreras sida vid sida med den lokala miljön. De två miljöerna är ännu inte anslutna med en tvärlokal anslutning, som kan vara en VPN-anslutning mellan webbplatser eller ExpressRoute.
    
- I det här läget innehåller det virtuella nätverket bara undernäten och inga andra arkitekturelement. Ett undernät är värd för Azure Gateway och andra undernät är värd för nivåerna för SharePoint-servergruppen, med ytterligare ett för Active Directory och DNS.
    
## <a name="add-cross-premises-connectivity"></a>Lägga till en tvärlokal anslutning

Nästa steg i distributionen är att skapa den tvärlokala anslutningen (om det här gäller din lösning). För tvärlokala anslutningar finns en Azure Gateway i ett separat gatewayundernät som du måste skapa och tilldela ett adressutrymme. 
  
När du planerar för en tvärlokal anslutning definierar och skapar du en Azure-gateway och anslutning till en lokal gatewayenhet.
  
**Bild 2: Använda en Azure-gateway och en lokal gatewayenhet för att tillhandahålla anslutning mellan den lokala miljön och Azure**

![Lokal miljö som är ansluten till ett virtuellt Azure-nätverk via en lokal anslutning, som kan vara en VPN-anslutning mellan webbplatser eller ExpressRoute](../media/AZarch-VPNgtwyconnct.png)
  
I det här diagrammet:
  
- Om du lägger till föregående diagram är den lokala miljön ansluten till det virtuella Azure-nätverket via en lokal anslutning, som kan vara en VPN-anslutning mellan webbplatser eller ExpressRoute.
    
- En Azure-gateway finns på ett gatewayundernät.
    
- I den lokala miljön ingår en gatewayenhet, till exempel en router eller VPN-server.
    
Mer information om hur du planerar för och skapar ett virtuellt korslokalt nätverk finns Anslut ett lokalt nätverk i [ett Microsoft Azure virtuellt nätverk.](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)
  
## <a name="add-active-directory-domain-services-ad-ds-and-dns"></a>Lägga till AD DS (Active Directory Domain Services) och DNS

För katastrofåterställning i Azure distribuerar du Windows Server AD och DNS i ett hybridscenario där Windows Server AD distribueras både lokalt och på virtuella Azure-datorer.
  
**Bild 3: Hybridkonfiguration av Active Directory-domän**

![STvå virtuella datorer som distribuerats till det virtuella Azure-nätverket och SharePoint Farm-undernätet är replikdomänkontroller och DNS-servrar](../media/AZarch-HyADdomainConfig.png)
  
Det här diagrammet bygger på de tidigare diagrammen genom att lägga till två virtuella datorer till ett Windows Server AD- och DNS-undernät. Dessa virtuella datorer är replikdomänkontrollanter och DNS-servrar. De är ett tillägg till den lokala Windows AD-miljön. 
  
Följande tabell innehåller konfigurationsrekommendationer för dessa virtuella datorer i Azure. Använd dem som utgångspunkt för att utforma din egen miljö, även för en dedikerad domän där Azure-miljön inte kommunicerar med din lokala miljö.
  
|**Objekt**|**Konfiguration**|
|:-----|:-----|
|Storlek på virtuell dator i Azure  <br/> |A1- eller A2-storlek på standardnivån  <br/> |
|Operativsystem  <br/> |Windows Server 2012 R2  <br/> |
|Active Directory-roll  <br/> |AD DS-domänkontrollant som angetts som global katalogserver. Den här konfigurationen minskar den utgående trafiken genom den tvärlokala anslutningen.  <br/> I en miljö med flera domäner med höga förändringshastigheter (detta är inte vanligt) konfigurerar du domänkontrollanter lokalt så att de inte synkroniseras med de globala katalogservrarna i Azure, för att minska replikeringstrafiken.  <br/> |
|DNS-roll  <br/> |Installera och konfigurera DNS-servertjänsten på domänkontrollanterna.  <br/> |
|Datadiskar  <br/> |Placera Active Directory-databasen, loggarna och SYSVOL på ytterligare Azure-datadiskar. Placera inte dessa på operativsystemets disk eller de tillfälliga diskar som tillhandahålls av Azure.  <br/> |
|IP-adresser  <br/> |Använd statiska IP-adresser och konfigurera det virtuella nätverket för att tilldela de här adresserna till virtuella datorer i det virtuella nätverket efter att domänkontrollanterna har konfigurerats.  <br/> |
   
> [!IMPORTANT]
> Innan du distribuerar Active Directory i Azure bör du [läsa Riktlinjer för Windows på Server Active Directory på virtuella Azure-datorer.](/windows-server/identity/ad-ds/introduction-to-active-directory-domain-services-ad-ds-virtualization-level-100) Det här hjälper dig att avgöra om en annan arkitektur eller olika konfigurationsinställningar krävs för din lösning. 
  
## <a name="add-the-sharepoint-farm"></a>Lägga till SharePoint servergrupp

Placera virtuella datorer i SharePoint servergruppen i nivåer på lämpliga undernät.
  
**Bild 4: Placering av SharePoint virtuella datorer**

![Databasservrar och SharePoint serverroller som lagts till i det virtuella Azure-nätverket SharePoint Servergruppsundernät](../media/AZarch-SPVMsinCloudSer.png)
  
Det här diagrammet bygger på de tidigare diagrammen genom att lägga SharePoint servergruppsroller i respektive nivå.
  
- Två virtuella databasdatorer som kör SQL Server skapa databasnivån.
    
- Två virtuella datorer med SharePoint Server 2013 för var och en av följande nivåer: frontend-servrar, distribuerade cacheservrar och serverserverservrar.
    
## <a name="design-and-fine-tune-server-roles-for-availability-sets-and-fault-domains"></a>Designa och finjustera serverroller för tillgänglighetsuppsättningar och feldomäner

En feldomän är en gruppering av maskinvara där rollinstanser körs. Virtuella datorer inom samma feldomän kan uppdateras samtidigt av Azure-infrastrukturen. Eller så kan de misslyckas på samma gång eftersom de har samma rack. Du kan undvika risken att ha två virtuella datorer på samma feldomän genom att konfigurera dina virtuella datorer som en tillgänglighetsuppsättning som säkerställer att varje virtuell dator ligger i en annan feldomän. Om tre virtuella datorer konfigureras som en tillgänglighetsuppsättning garanterar Azure att inte fler än två av de virtuella maskinerna finns i samma feldomän.
  
När du utformar Azure-arkitekturen för en SharePoint servergrupp konfigurerar du identiska serverroller som en del av en tillgänglighetsuppsättning. Det säkerställer att dina virtuella datorer är utspridda över flera feldomäner.
  
**Bild 5: Använd Azure-tillgänglighetsuppsättningar för att ge hög tillgänglighet SharePoint servergruppsnivåer**

![Konfiguration av tillgänglighetsuppsättningar i Azure-infrastrukturen för en SharePoint 2013-lösning](../media/AZenv-WinAzureAvailSetsHA.png)
  
Det här diagrammet beskriver konfiguration av tillgänglighetsuppsättningar i Azure-infrastrukturen. Var och en av följande roller har en separat tillgänglighetsuppsättning:
  
- Active Directory och DNS
    
- Databas
    
- Backend
    
- Distribuera cache
    
- Frontend
    
Servergruppen SharePoint kanske måste finjusteras på Azure-plattformen. För att säkerställa hög tillgänglighet för alla komponenter, se till att alla serverroller är konfigurerade identiskt.
  
Här är ett exempel som visar en standardarkitektur för Internetwebbplatser som uppfyller specifika kapacitets- och prestandamål. Det här exemplet presenteras i följande arkitekturmodell: [Sökarkitekturer för Internetwebbplatser SharePoint Server 2013.](https://go.microsoft.com/fwlink/p/?LinkId=261519)
  
**Bild 6: Exempel på planering för kapacitets- och prestandamål i en servergrupp på tre nivåer**

![Standard SharePoint 2013-arkitekturen för Internetwebbplatser med komponenttilldelningar som uppfyller specifika kapacitets- och prestandamål](../media/AZarch-CapPerfexmpArch.png)
  
I det här diagrammet:
  
- En servergrupp på tre nivåer representeras: webbservrar, programservrar och databasservrar.
    
- De tre webbservrarna är konfigurerade identiskt med flera komponenter.
    
- De två databasservrarna är konfigurerade identiskt.
    
- De tre programservrarna är inte konfigurerade identiskt. De här serverrollerna kräver finjustering för tillgänglighetsuppsättningar i Azure.
    
Vi tittar närmare på programservernivån.
  
**Bild 7: Programservernivån innan du finslipar**

![Exempel SharePoint servernivån för Server 2013 innan du Microsoft Azure för tillgänglighetsuppsättningar](../media/AZarch-AppServtierBefore.png)
  
I det här diagrammet:
  
- Tre servrar ingår i programnivån.
    
- Den första servern innehåller fyra komponenter.
    
- Den andra servern innehåller tre komponenter.
    
- Den tredje servern består av två komponenter.
    
Du fastställer antalet komponenter genom prestanda- och kapacitetsmålen för servergruppen. För att anpassa den här arkitekturen för Azure replikerar vi de fyra komponenterna över alla tre servrarna. Då ökar antalet komponenter utöver vad som krävs för prestanda och kapacitet. Kompromissen är att den här designen säkerställer hög tillgänglighet för alla fyra komponenterna i Azure-plattformen när dessa tre virtuella maskiner tilldelas till en tillgänglighetsuppsättning.
  
**Bild 8: Programservernivån efter finjustering**

![Exempel SharePoint Server 2013-programservernivån efter justering för Microsoft Azure för tillgänglighetsuppsättningar](../media/AZarch-AppServtierAfter.png)
  
I diagrammet visas alla tre programservrar som konfigurerats identiskt med samma fyra komponenter.
  
När vi lägger till tillgänglighetsuppsättningar till nivåerna SharePoint servergruppen är implementeringen klar.
  
**Bild 9: Den slutförda SharePoint servergruppen i Azure-infrastrukturtjänster**

![Exempel SharePoint 2013-servergrupp i Azure-infrastrukturtjänster med virtuella nätverk, tvärlokala anslutningar, undernät, virtuella maskiner och tillgänglighetsuppsättningar](../media/7256292f-bf11-485b-8917-41ba206153ee.png)
  
Det här diagrammet visar SharePoint servergrupp som implementeras i Azure-infrastrukturtjänster, med tillgänglighetsuppsättningar som tillhandahåller feldomäner för servrarna på varje nivå.
  
## <a name="see-also"></a>Se även

[Microsoft 365-lösning och arkitekturcenter](../solutions/index.yml)
  
[Webbplatser i Microsoft Azure med SharePoint Server 2013](internet-sites-in-microsoft-azure-using-sharepoint-server-2013.md)
  
[SharePoint Server 2013 katastrofåterställning i Microsoft Azure](sharepoint-server-2013-disaster-recovery-in-microsoft-azure.md)