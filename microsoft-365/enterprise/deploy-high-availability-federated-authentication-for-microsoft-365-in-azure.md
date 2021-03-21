---
title: Distribuera federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150s
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
ms.assetid: 34b1ab9c-814c-434d-8fd0-e5a82cd9bff6
description: Sammanfattning Konfigurera federerad autentisering med hög tillgänglighet för din Microsoft 365-prenumeration i Microsoft Azure.
ms.openlocfilehash: 3989ebb06b4ac5dfa1cded5e07c086c4778f94e7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919158"
---
# <a name="deploy-high-availability-federated-authentication-for-microsoft-365-in-azure"></a>Distribuera federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure

Den här artikeln innehåller länkar till stegvisa instruktioner för distribution av federerad autentisering med hög tillgänglighet för Microsoft Microsoft 365 i Azure-infrastrukturtjänster med dessa virtuella datorer:
  
- Två proxyservrar för webbprogram
    
- Två AD FS-servrar (Active Directory Federation Services)
    
- Två replika domänkontrollanter
    
- En katalogsynkroniseringsserver som kör Azure AD Connect
    
Här är konfigurationen med platshållarnamn för varje server.
  
**En hög tillgänglighet federerad autentisering för Microsoft 365-infrastruktur i Azure**

![Den slutliga konfigurationen av microsoft 365-infrastrukturen för federerad autentisering med hög tillgänglighet i Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
Alla virtuella maskiner finns i ett enda virtuellt Azure-nätverk (VNet). 
  
> [!NOTE]
> Federerad autentisering av enskilda användare är inte beroende av några lokala resurser. Men om den tvärlokala anslutningen blir otillgänglig kommer domänkontrollanterna i det virtuella nätverket inte att få uppdateringar för användarkonton och grupper som gjorts i ad ds (Active Directory Domain Services) lokalt. Du kan se till att det inte sker genom att konfigurera hög tillgänglighet för den lokala anslutningen. Mer information finns i [Mycket tillgänglig, tvärlokal anslutning och VNet-till-VNet-anslutning](/azure/vpn-gateway/vpn-gateway-highlyavailable)
  
Varje par virtuella maskiner för en viss roll är i en egen undernät och tillgänglighetsuppsättning.
  
> [!NOTE]
> Eftersom det här VNet är anslutet till det lokala nätverket inkluderar den här konfigurationen inte jumpbox eller övervakning av virtuella maskiner på ett hanteringsundernät. Mer information finns i Köra [Windows VMs för en N-nivåarkitektur.](/azure/guidance/guidance-compute-n-tier-vm) 
  
Resultatet av den här konfigurationen är att du har federerad autentisering för alla dina Microsoft 365-användare där de kan använda sina AD DS-autentiseringsuppgifter för att logga in i stället för sitt Microsoft 365-konto. Den externa autentiseringsinfrastrukturen använder en redundant uppsättning servrar som enklare distribueras i Azure-infrastrukturtjänster, i stället för i ditt lokala gränsnätverk.
  
## <a name="bill-of-materials"></a>Strukturlista

Den här baslinjekonfigurationen kräver följande uppsättning Azure-tjänster och -komponenter:
  
- Sju virtuella datorer
    
- Ett virtuellt korslokalt nätverk med fyra undernät
    
- Fyra resursgrupper
    
- Tre tillgänglighetsuppsättningar
    
- En Azure-prenumeration
    
Här är de virtuella maskinerna och deras standardstorlekar för den här konfigurationen.
  
|**Objekt**|**Beskrivning av virtuell dator**|**Azure-galleribild**|**Standardstorlek**|
|:-----|:-----|:-----|:-----|
|1.  <br/> |Första domänkontrollanten  <br/> |Windows Server 2016-datacenter  <br/> |D2  <br/> |
|2.  <br/> |Andra domänkontrollanten  <br/> |Windows Server 2016-datacenter  <br/> |D2  <br/> |
|3.  <br/> |Azure AD Connect-server  <br/> |Windows Server 2016-datacenter  <br/> |D2  <br/> |
|4.  <br/> |First AD FS server  <br/> |Windows Server 2016-datacenter  <br/> |D2  <br/> |
|5.  <br/> |Second AD FS server  <br/> |Windows Server 2016-datacenter  <br/> |D2  <br/> |
|6.  <br/> |First web application proxy server  <br/> |Windows Server 2016-datacenter  <br/> |D2  <br/> |
|7.  <br/> |Andra webbprogramproxyservern  <br/> |Windows Server 2016-datacenter  <br/> |D2  <br/> |
   
Information om beräknade kostnader för den här konfigurationen finns i [Azure-priskalkylatorn](https://azure.microsoft.com/pricing/calculator/)
  
## <a name="phases-of-deployment"></a>Faser i distributionen

Du distribuerar arbetsbelastningen i följande faser:
  
- [Fas 1: Konfigurera Azure.](high-availability-federated-authentication-phase-1-configure-azure.md) Skapa resursgrupper, lagringskonton, tillgänglighetsuppsättningar och ett virtuellt nätverk på flera platser.
    
- [Fas 2: Konfigurera domänkontrollanter](high-availability-federated-authentication-phase-2-configure-domain-controllers.md). Skapa och konfigurera replika AD DS-domänkontrollanter och katalogsynkroniseringsservern.
    
- [Fas 3: Konfigurera AD FS-servrar.](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md) Skapa och konfigurera de två AD FS-servrarna.
    
- [Fas 4: Konfigurera proxyprogram för webbprogram.](high-availability-federated-authentication-phase-4-configure-web-application-pro.md) Skapa och konfigurera de två proxyservrarna för webbprogram.
    
- [Fas 5: Konfigurera federerad autentisering för Microsoft 365.](high-availability-federated-authentication-phase-5-configure-federated-authentic.md) Konfigurera federerad autentisering för Microsoft 365-prenumerationen.
    
I de här artiklarna finns en fördefinierad, fas för fas-guide för en fördefinierad arkitektur för att skapa en funktionell, federerad autentisering med hög tillgänglighet för Microsoft 365 i Azure-infrastrukturtjänster. Tänk på följande:
  
- Om du är en erfaren AD FS-implementerare kan du anpassa instruktionerna i fas 3 och 4 och bygga den uppsättning servrar som bäst passar dina behov.
    
- Om du redan har en befintlig Azure-hybridmolndistribution med ett befintligt virtuellt korslokalt nätverk kan du anpassa eller hoppa över instruktionerna i faserna 1 och 2 och placera AD FS- och webbprogramproxyservrarna på lämpliga undernät.
    
Information om hur du skapar en utvecklings-/testmiljö eller ett koncepttest för den här konfigurationen finns i Federerad identitet för [utvecklings-/testmiljön för Microsoft 365.](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
## <a name="next-step"></a>Nästa steg

Börja konfigurationen av den här arbetsbelastningen [med steg 1: Konfigurera Azure.](high-availability-federated-authentication-phase-1-configure-azure.md) 
