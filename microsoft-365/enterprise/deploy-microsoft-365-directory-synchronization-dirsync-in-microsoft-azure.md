---
title: Distribuera Microsoft 365-profilsynkronisering i Microsoft Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/05/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: b8464818-4325-4a56-b022-5af1dad2aa8b
description: Lär dig hur du distribuerar Azure AD Connect på en virtuell dator i Azure för att synkronisera konton mellan den lokala katalogen och Azure AD-klienten.
ms.openlocfilehash: 8db78d20ee4c2186918a0b3b433f8f0ae056816e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694681"
---
# <a name="deploy-microsoft-365-directory-synchronization-in-microsoft-azure"></a>Distribuera Microsoft 365-profilsynkronisering i Microsoft Azure

Azure Active Directory (Azure AD) Connect (kallades tidigare verktyg för katalog, katalog eller DirSync.exe) är ett program som du installerar på en domänansluten Server för att synkronisera dina lokala Active Directory Domain Services-användare i din Microsoft 365-prenumeration. Microsoft 365 använder Azure AD för sin katalog tjänst. Ditt Microsoft 365-abonnemang inkluderar en Azure AD-klient. Denna klient organisation kan även användas för att hantera din företags identitet med andra moln arbets belastningar, inklusive andra SaaS-program och appar i Azure.

Du kan installera Azure AD Connect på en lokal server, men du kan även installera den på en virtuell dator i Azure av följande anledningar:
  
- Du kan etablera och konfigurera molnbaserade servrar snabbare, vilket gör tjänsterna tillgängliga för dina användare fortare.
- Azure erbjuder bättre tillgänglighet för webbplatsen med mindre ansträngning.
- Du kan minska antalet lokala servrar i organisationen.

Denna lösning kräver anslutning mellan det lokala nätverket och det virtuella Azure-nätverket. Mer information finns i [ansluta ett lokalt nätverk till ett Microsoft Azure-nätverk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md). 
  
> [!NOTE]
> I den här artikeln beskrivs synkronisering av en enda domän i en enda skog. Azure AD Connect synkroniserar alla AD DS-domäner i din Active Directory-skog med Microsoft 365. Om du har flera Active Directory-skogar att synkronisera med Microsoft 365 kan du läsa mer i [katalog för flera skogar med enkel inloggning](https://go.microsoft.com/fwlink/p/?LinkId=393091). 
  
## <a name="overview-of-deploying-microsoft-365-directory-synchronization-in-azure"></a>Översikt över distribution av synkronisering av Microsoft 365-katalog i Azure

Följande diagram visar hur Azure AD Connect körs på en virtuell dator i Azure (den katalogpartition som synkroniserar en lokal AD DS-skog till en Microsoft 365-prenumeration.
  
![Azure AD Connect-verktyg på en virtuell dator i Azure-synkronisering av lokala konton till Azure AD-klient organisationen för en Microsoft 365-prenumeration med trafikflöde](../media/CP-DirSyncOverview.png)
  
I diagrammet finns det två nätverk anslutna via plats-till-plats-ExpressRoute. Det finns ett lokalt nätverk där AD DS-domänkontrollanter finns och det finns ett Azure Virtual Network med en katalogpartition som är en virtuell dator med [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594). Det finns två huvudsakliga trafik flöden som kommer från katalogen Sync-servern:
  
-  Azure AD Connect frågar en domänkontrollant i det lokala nätverket för att ändra konto och lösen ord.
-  Azure AD Connect skickar ändringarna till konton och lösen ord till Azure AD-instansen av ditt Microsoft 365-abonnemang. Eftersom den här servern finns i en längre del av ditt lokala nätverk, skickas dessa ändringar via det lokala nätverkets proxyserver.
    
> [!NOTE]
> Den här lösningen beskriver synkronisering av en enda Active Directory-domän i en enda Active Directory-skog. Azure AD Connect synkroniserar alla Active Directory-domäner i din Active Directory-skog med Microsoft 365. Om du har flera Active Directory-skogar att synkronisera med Microsoft 365 kan du läsa mer i [katalog för flera skogar med enkel inloggning](https://go.microsoft.com/fwlink/p/?LinkId=393091). 
  
Det finns två huvudsakliga steg när du distribuerar den här lösningen:
  
1. Skapa ett Azure Virtual Network och etablera en VPN-anslutning för ett lokalt nätverk. Mer information finns i [ansluta ett lokalt nätverk till ett Microsoft Azure-nätverk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md).
    
2. Installera [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) på en domänansluten virtuell dator i Azure och synkronisera sedan den lokala AD DS till Microsoft 365. Detta gäller:
    
    Skapa en virtuell Azure-dator för att köra Azure AD Connect.
    
    Installerar och konfigurerar [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594).
    
    Konfiguration av Azure AD Connect kräver autentiseringsuppgifterna (användar namn och lösen ord) för ett Azure AD-administratörskonto och ett AD DS-konto för företags administratör. Azure AD Connect körs omedelbart och fort löp ande för att synkronisera den lokala AD DS-skogen till Microsoft 365.
    
Innan du distribuerar den här lösningen i produktion kan du använda instruktionerna i [den simulerade företags bas konfigurationen](simulated-ent-base-configuration-microsoft-365-enterprise.md) för att konfigurera denna konfiguration som ett koncept bevis, för demonstrationer eller för experiment.
  
> [!IMPORTANT]
> När Azure AD Connect-konfigurationen är klar sparas inte autentiseringsuppgifterna för AD DS-företagsprojekt för företag. 
  
> [!NOTE]
> Den här lösningen beskriver synkronisering av en enda AD DS-skog till Microsoft 365. Den topologi som diskuteras i den här artikeln är bara ett sätt att implementera den här lösningen. Din organisations topologi kan variera beroende på dina unika nätverks krav och säkerhets aspekter. 
  
## <a name="plan-for-hosting-a-directory-sync-server-for-microsoft-365-in-azure"></a>Planera för en katalog synkroniseringsklient för Microsoft 365 i Azure
<a name="PlanningVirtual"> </a>

### <a name="prerequisites"></a>Förutsättningar

Innan du börjar bör du kontrol lera följande förutsättningar för den här lösningen:
  
- Granska det relaterade planerings innehållet i [planera ditt Azure Virtual Network](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network).
    
- Se till att du uppfyller alla [förutsättningar](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites) för konfigurering av Azure Virtual Network.
    
- Ha en Microsoft 365-prenumeration som innehåller Active Directory-integrering. Om du vill veta mer om Microsoft 365-prenumerationer går du till [prenumerations sidan för microsoft 365](https://products.office.com/compare-all-microsoft-office-products?tab=2).
    
- Etablera en virtuell Azure-dator som kör Azure AD Connect för att synkronisera din lokala AD DS-skog med Microsoft 365.
    
    Du måste ha autentiseringsuppgifterna (namn och lösen ord) för ett AD DS Enterprise-administratörskonto och ett Azure AD-administratörs konto.
    
### <a name="solution-architecture-design-assumptions"></a>Utvecklings antagande för lösnings arkitektur

I följande lista beskrivs design alternativen för den här lösningen.
  
- Den här lösningen använder ett enda virtuellt Azure-nätverk med en VPN-anslutning för plats-till-plats. Det virtuella Azure-nätverket har ett enskilt undernät som har en server, den katalogpartition som kör Azure AD Connect. 
    
- I det lokala nätverket finns det en domänkontrollant och DNS-servrar.
    
- Azure AD Connect utför synkronisering av lösen ord i stället för enkel inloggning. Du behöver inte distribuera en AD FS-infrastruktur (Active Directory Federation Services). Mer information om hur du synkroniserar och använder ett lösen ord finns i [välja rätt autentiseringsmetod för din Azure Active Directory-hybrid Identity-lösning](https://aka.ms/auth-options).
    
Det finns fler design alternativ som du kanske bör tänka på när du distribuerar lösningen i din miljö. Bland annat följande:
  
- Om det finns befintliga DNS-servrar i ett befintligt Azure-nätverk bestämmer du om du vill att din katalog synkroniseringsklient ska använda dem för namn matchning i stället för DNS-servrar i det lokala nätverket.
    
- Om det finns domänkontrollanter i ett befintligt Azure-nätverk kan du bestämma om du vill konfigurera Active Directory-platser och tjänster. Med den här servern kan du söka efter domänkontrollanter i det lokala Azure-nätverket efter ändringar i konton och lösen ord i stället för domänkontrollanter på lokalt nätverk.
    
## <a name="deployment-roadmap"></a>Distributions översikt

Distributionen av Azure AD Connect på en virtuell dator i Azure består av tre faser:
  
- Fas 1: skapa och konfigurera Azure Virtual Network
    
- Fas 2: skapa och konfigurera den virtuella Azure-datorn
    
- Fas 3: installera och konfigurera Azure AD Connect
    
Efter distributionen måste du också tilldela platser och licenser för de nya användar kontona i Microsoft 365.


### <a name="phase-1-create-and-configure-the-azure-virtual-network"></a>Fas 1: skapa och konfigurera Azure Virtual Network

För att skapa och konfigurera Azure Virtual Network kompletterar du [fas 1: förbereda ditt lokala nätverk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network) och [fas 2: skapa det lokala virtuella nätverket i Azure](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure) i distributions översikten för [Anslut ett lokalt nätverk till ett Microsoft Azure-](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)nätverk.
  
Det här är din resulterande konfiguration.
  
![Fas 1 av katalogen Sync Server för Microsoft 365 som finns i Azure](../media/aab6a9a4-eb78-4d85-9b96-711e6de420d7.png)
  
Den här bilden visar ett lokalt nätverk som är kopplat till ett virtuellt Azure-nätverk via plats-till-plats-VPN eller ExpressRoute anslutning.
  
### <a name="phase-2-create-and-configure-the-azure-virtual-machine"></a>Fas 2: skapa och konfigurera den virtuella Azure-datorn

Skapa den virtuella datorn i Azure genom att använda instruktionerna [skapa din första Windows-dator i Azure-portalen](https://go.microsoft.com/fwlink/p/?LinkId=393098). Använd följande inställningar:
  
- I fönstret **grunderna** väljer du samma prenumeration, plats och resurs grupp som ditt virtuella nätverk. Spela in användar namn och lösen ord på en säker plats. Du behöver dessa senare för att ansluta till den virtuella datorn.
    
- Välj standard storleken för **a2** i fönstret **Välj en storlek** .
    
- Välj **standard** lagrings typ i avsnittet **lagring** i fönstret **Inställningar** . I avsnittet **nätverk** väljer du namnet på det virtuella nätverket och under nätet där katalogens synkroniseringstjänst (inte GatewaySubnet) finns. Lämna övriga inställningar till standardvärdena.
    
Kontrol lera att din katalog synkroniseringsklient använder DNS korrekt genom att kontrol lera den interna DNS-servern för att se till att en adress (A)-post har lagts till för den virtuella datorn med dess IP-adress. 
  
Följ instruktionerna i [ansluta till den virtuella datorn och logga in](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) för att ansluta till katalogen med en fjärr skrivbords anslutning. När du har loggat in ansluter du den virtuella datorn till den lokala AD DS-domänen.
  
För att Azure AD Connect ska få till gång till Internet resurser måste du konfigurera katalogpartitionen så att den använder det lokala nätverkets proxyserver. Kontakta nätverks administratören för att få ytterligare konfigurations steg.
  
Det här är din resulterande konfiguration.
  
![Fas 2 i katalogen med katalog servern för Microsoft 365 som finns i Azure](../media/9d8c9349-a207-4828-9b2b-826fe9c06af3.png)
  
Den här bilden visar den virtuella katalogpartitionen för katalogpartition i det korslänkade Azure Virtual Network.
  
### <a name="phase-3-install-and-configure-azure-ad-connect"></a>Fas 3: installera och konfigurera Azure AD Connect

Gör följande:
  
1. Anslut till katalogen med en fjärr skrivbords server med ett AD DS-domännamn med lokala administratörs behörigheter. Se [ansluta till den virtuella datorn och logga in](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).
    
2. Från katalogen för synkroniseringstjänst öppnar du [Microsoft 365-artikeln Konfigurera katalog synkronisering](set-up-directory-synchronization.md) och följer instruktionerna för profilsynkronisering med Lösenordssynkronisering med lösen ord.
    
> [!CAUTION]
> Installations programmet skapar **AAD_xxxxxxxxxxxx** kontot i organisationsenheten lokala användare. Det går inte att flytta eller ta bort det här kontot eller synkroniseringen.
  
Det här är din resulterande konfiguration.
  
![Fas 3 i katalogen för synkroniseringstjänst för Microsoft 365 som finns i Azure](../media/3f692b62-b77c-4877-abee-83c7edffa922.png)
  
I den här bilden visas den synkroniserade katalog servern med Azure AD Connect i det korslänkade Azure Virtual Network.
  
### <a name="assign-locations-and-licenses-to-users-in-microsoft-365"></a>Tilldela platser och licenser till användare i Microsoft 365

Azure AD Connect lägger till konton i din Microsoft 365-prenumeration från den lokala AD DS, men för att användare ska kunna logga in på Microsoft 365 och använda dess tjänster måste kontona vara konfigurerade med en plats och licenser. Följ de här anvisningarna för att lägga till platsen och aktivera licenser för lämpliga användar konton:
  
1. Logga in på [administrations centret för Microsoft 365](https://admin.microsoft.com)och klicka sedan på **admin**.
    
2. Klicka på **Användare > Aktiva användare** i det vänstra navigeringsfönstret.
    
3. Markera kryss rutan bredvid den användare du vill aktivera i listan med användar konton.
    
4. Klicka på **redigera** för **produkt licenser**på sidan för användaren.
    
5. På sidan **produkt licenser** väljer du en plats för användaren för **plats**och aktiverar sedan lämpliga licenser för användaren.
    
6. När du är klar klickar du på **Spara**och sedan på **Stäng** två gånger.
    
7. Gå tillbaka till steg 3 för ytterligare användare.
    
## <a name="see-also"></a>Se även

[Microsoft 365-center för lösningar och arkitektur](../solutions/solution-architecture-center.md)
  
[Ansluta ett lokalt nätverk till ett Microsoft Azure-nätverk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)

[Ladda ner Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594)
  
[Konfigurera profilsynkronisering för Microsoft 365](set-up-directory-synchronization.md)
  
