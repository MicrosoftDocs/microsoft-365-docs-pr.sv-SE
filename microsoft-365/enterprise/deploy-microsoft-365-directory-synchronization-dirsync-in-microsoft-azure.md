---
title: Distribuera Microsoft 365-katalogsynkronisering i Microsoft Azure
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
description: Lär dig hur du distribuerar Azure AD Connect på en virtuell dator i Azure för att synkronisera konton mellan din lokala katalog och Azure AD-klientorganisationen.
ms.openlocfilehash: 52c1bb2eb53cc4e6753d528e0d82822b2a0eebc5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919092"
---
# <a name="deploy-microsoft-365-directory-synchronization-in-microsoft-azure"></a>Distribuera Microsoft 365-katalogsynkronisering i Microsoft Azure

Azure Active Directory (Azure AD) Connect (kallades tidigare för katalogsynkroniseringsverktyget, katalogsynkroniseringsverktyget eller DirSync.exe-verktyget) är ett program som du installerar på en domän ansluten server för att synkronisera dina lokala AD DS-användare (Active Directory Domain Services) med Azure AD-klientorganisationen för din Microsoft 365-prenumeration. Microsoft 365 använder Azure AD för sin katalogtjänst. I din Microsoft 365-prenumeration ingår en Azure AD-klientorganisation. Den här klientorganisationen kan också användas för hantering av organisationens identiteter med andra molnarbetsbelastningar, inklusive andra SaaS-program och -appar i Azure.

Du kan installera Azure AD Connect på en lokal server, men du kan också installera det på en virtuell dator i Azure av följande anledningar:
  
- Du kan tillhandahålla och konfigurera molnbaserade servrar snabbare, vilket gör tjänsterna tillgängliga för användarna snabbare.
- Azure erbjuder bättre webbplatstillgänglighet med mindre ansträngning.
- Du kan minska antalet lokala servrar i organisationen.

Den här lösningen kräver anslutning mellan ditt lokala nätverk och ditt virtuella Azure-nätverk. Mer information finns i [Ansluta ett lokalt nätverk till ett virtuellt Microsoft Azure-nätverk.](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md) 
  
> [!NOTE]
> I den här artikeln beskrivs synkronisering av en enda domän i en enda skog. Azure AD Connect synkroniserar alla AD DS-domäner i Active Directory-skogen med Microsoft 365. Om du har flera Active [Directory-skogar](/azure/active-directory/hybrid/whatis-hybrid-identity)att synkronisera med Microsoft 365 kan du gå till Scenario med katalogsynkronisering med Sign-On med flera skogar. 
  
## <a name="overview-of-deploying-microsoft-365-directory-synchronization-in-azure"></a>Översikt över distribution av Microsoft 365-katalogsynkronisering i Azure

Följande diagram visar Azure AD Connect som körs på en virtuell dator i Azure (katalogsynkroniseringsservern) som synkroniserar en lokal AD DS-skog med en Microsoft 365-prenumeration.
  
![Verktyget Azure AD Connect på en virtuell dator i Azure-synkronisering av lokala konton till Azure AD-klientorganisationen för en Microsoft 365-prenumeration med trafikflöde](../media/CP-DirSyncOverview.png)
  
I diagrammet finns det två nätverk anslutna med VPN-anslutning mellan webbplatser eller ExpressRoute-anslutning. Det finns ett lokalt nätverk där AD DS-domänkontrollanter finns och det finns ett virtuellt Azure-nätverk med en katalogsynkroniseringsserver, som är en virtuell dator med [Azure AD Connect.](https://www.microsoft.com/download/details.aspx?id=47594) Det finns två huvudsakliga trafikflöden som kommer från katalogsynkroniseringsservern:
  
-  Azure AD Connect frågar en domänkontrollant i det lokala nätverket efter ändringar av konton och lösenord.
-  Azure AD Connect skickar ändringarna till konton och lösenord till Azure AD-instansen av Microsoft 365-prenumerationen. Eftersom katalogsynkroniseringsservern ligger i en utökad del av det lokala nätverket skickas ändringarna via det lokala nätverkets proxyserver.
    
> [!NOTE]
> I den här lösningen beskrivs synkronisering av en enda Active Directory-domän i en enda Active Directory-skog. Azure AD Connect synkroniserar alla Active Directory-domäner i din Active Directory-skog med Microsoft 365. Om du har flera Active [Directory-skogar](/azure/active-directory/hybrid/whatis-hybrid-identity)att synkronisera med Microsoft 365 kan du gå till Scenario med katalogsynkronisering med Sign-On med flera skogar. 
  
Det finns två huvudsteg när du distribuerar den här lösningen:
  
1. Skapa ett virtuellt Azure-nätverk och upprätta en VPN-anslutning mellan webbplatser till ditt lokala nätverk. Mer information finns i [Ansluta ett lokalt nätverk till ett virtuellt Microsoft Azure-nätverk.](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)
    
2. Installera [Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594) på en domän ansluten virtuell dator i Azure och synkronisera sedan den lokala AD DS till Microsoft 365. Detta omfattar:
    
    Skapa en virtuell Azure-dator för att köra Azure AD Connect.
    
    Installera och konfigurera [Azure AD Connect.](https://www.microsoft.com/download/details.aspx?id=47594)
    
    För konfiguration av Azure AD Connect krävs autentiseringsuppgifter (användarnamn och lösenord) för ett Azure AD-administratörskonto och ett AD DS-företagsadministratörskonto. Azure AD Connect körs direkt och kontinuerligt för att synkronisera den lokala AD DS-skogen till Microsoft 365.
    
Innan du distribuerar den här lösningen i [](simulated-ent-base-configuration-microsoft-365-enterprise.md) produktionen kan du använda instruktionerna i Den simulerade företagskonfigurationen för att konfigurera den här konfigurationen som ett konceptbevis, för demonstrationer eller för experiment.
  
> [!IMPORTANT]
> När Azure AD Connect-konfigurationen har slutförts sparas inte autentiseringsuppgifterna för AD DS-företagsadministratörens konto. 
  
> [!NOTE]
> I den här lösningen beskrivs synkronisering av en enda AD DS-skog till Microsoft 365. Topologin som beskrivs i den här artikeln representerar bara ett sätt att implementera den här lösningen. Organisationens topologi kan skilja sig åt beroende på dina unika nätverkskrav och säkerhetsöverväganden. 
  
## <a name="plan-for-hosting-a-directory-sync-server-for-microsoft-365-in-azure"></a>Planera värd för en katalogsynkroniseringsserver för Microsoft 365 i Azure
<a name="PlanningVirtual"> </a>

### <a name="prerequisites"></a>Förutsättningar

Innan du börjar granskar du följande krav för den här lösningen:
  
- Granska relaterat planeringsinnehåll i [Planera ditt virtuella Azure-nätverk.](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#plan-your-azure-virtual-network)
    
- Se till att du uppfyller [alla krav för](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#prerequisites) att konfigurera det virtuella Azure-nätverket.
    
- Har en Microsoft 365-prenumeration som omfattar Active Directory-integreringsfunktionen. Mer information om Microsoft 365-prenumerationer finns på prenumerationssidan [för Microsoft 365.](https://products.office.com/compare-all-microsoft-office-products?tab=2)
    
- Tillhandahålla en Virtuell Azure-dator som kör Azure AD Connect för att synkronisera din lokala AD DS-skog med Microsoft 365.
    
    Du måste ha autentiseringsuppgifterna (namn och lösenord) för ett AD DS-företagsadministratörskonto och ett Azure AD-administratörskonto.
    
### <a name="solution-architecture-design-assumptions"></a>Antaganden om design av lösningsarkitektur

I följande lista beskrivs de designval som gjorts för den här lösningen.
  
- Den här lösningen använder ett enda virtuellt Azure-nätverk med en VPN-anslutning mellan webbplatser. Det virtuella Azure-nätverket är värd för ett enda undernät som har en server, den katalogsynkroniseringsserver som kör Azure AD Connect. 
    
- I det lokala nätverket finns en domänkontrollant och DNS-servrar.
    
- Azure AD Connect utför synkronisering av lösenordshashar i stället för enkel inloggning. Du behöver inte distribuera en AD FS-infrastruktur (Active Directory Federation Services). Mer information om synkronisering av lösenordshashar och alternativ för enkel inloggning finns i Välja rätt autentiseringsmetod för [din Azure Active Directory-hybrididentitetslösning.](/azure/active-directory/hybrid/choose-ad-authn)
    
Det finns ytterligare designalternativ som du kan tänka på när du distribuerar den här lösningen i din miljö. Det kan till exempel vara:
  
- Om det finns befintliga DNS-servrar i ett befintligt virtuellt Azure-nätverk ska du avgöra om du vill att katalogsynkroniseringsservern ska använda dem för namnmatchning i stället för DNS-servrar i det lokala nätverket.
    
- Om det finns domänkontrollanter i ett befintligt virtuellt Azure-nätverk avgör du om konfigurering av Active Directory -webbplatser och -tjänster kan vara ett bättre alternativ för dig. Katalogsynkroniseringsservern kan fråga domänkontrollanterna i det virtuella Azure-nätverket efter ändringar i konton och lösenord i stället för domänkontrollanter på det lokala nätverket.
    
## <a name="deployment-roadmap"></a>Distributionsöversikt

Distribution av Azure AD Connect på en virtuell dator i Azure består av tre faser:
  
- Fas 1: Skapa och konfigurera det virtuella Azure-nätverket
    
- Fas 2: Skapa och konfigurera den virtuella Azure-datorn
    
- Fas 3: Installera och konfigurera Azure AD Connect
    
Efter distributionen måste du också tilldela platser och licenser för de nya användarkontona i Microsoft 365.


### <a name="phase-1-create-and-configure-the-azure-virtual-network"></a>Fas 1: Skapa och konfigurera det virtuella Azure-nätverket

Slutför fas 1 för att skapa och konfigurera det virtuella [Azure-nätverket:](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-1-prepare-your-on-premises-network) Förbered ditt lokala nätverk och fas [2:](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md#phase-2-create-the-cross-premises-virtual-network-in-azure) Skapa det virtuella korslokala nätverket i Azure i översikten över distributionen av Ansluta ett lokalt nätverk till ett virtuellt [Microsoft](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)Azure-nätverk.
  
Det här är den resulterande konfigurationen.
  
![Fas 1 av katalogsynkroniseringsservern för Microsoft 365 som finns i Azure](../media/aab6a9a4-eb78-4d85-9b96-711e6de420d7.png)
  
På den här bilden visas ett lokalt nätverk som är anslutet till ett virtuellt Azure-nätverk via en VPN-anslutning mellan webbplatser eller ExpressRoute-anslutning.
  
### <a name="phase-2-create-and-configure-the-azure-virtual-machine"></a>Fas 2: Skapa och konfigurera den virtuella Azure-datorn

Skapa den virtuella datorn i Azure med hjälp av [anvisningarna Skapa din första virtuella Windows-dator i Azure-portalen.](https://go.microsoft.com/fwlink/p/?LinkId=393098) Använd följande inställningar:
  
- I fönstret **Grunder** väljer du samma prenumeration, plats och resursgrupp som ditt virtuella nätverk. Registrera användarnamnet och lösenordet på en säker plats. Du behöver dem senare för att ansluta till den virtuella datorn.
    
- I fönstret **Välj en storlek** väljer du **A2 Standardstorlek.**
    
- Välj **Standardlagringstyp** i **avsnittet** Lagring i **fönstret** Inställningar. I avsnittet **Nätverk** väljer du namnet på det virtuella nätverket och undernätet för värd för katalogsynkroniseringsservern (inte GatewaySubnet). Lämna alla andra inställningar för standardvärdena.
    
Kontrollera att din katalogsynkroniseringsserver använder DNS korrekt genom att kontrollera din interna DNS för att se till att en adresspost (A) har lagts till för den virtuella datorn med dess IP-adress. 
  
Följ anvisningarna i [Ansluta till den virtuella datorn och logga in för](/azure/virtual-machines/windows/connect-logon) att ansluta till katalogsynkroniseringsservern med en Fjärrskrivbordsanslutning. När du har loggat in ansluter du den virtuella datorn till den lokala AD DS-domänen.
  
För att Azure AD Connect ska få åtkomst till Internetresurser måste du konfigurera katalogsynkroniseringsservern så att den använder det lokala nätverkets proxyserver. Kontakta nätverksadministratören för ytterligare konfigurationssteg.
  
Det här är den resulterande konfigurationen.
  
![Fas 2 av katalogsynkroniseringsservern för Microsoft 365 som finns i Azure](../media/9d8c9349-a207-4828-9b2b-826fe9c06af3.png)
  
I den här bilden visas den virtuella katalogsynkroniseringsservern i det virtuella Azure-nätverket.
  
### <a name="phase-3-install-and-configure-azure-ad-connect"></a>Fas 3: Installera och konfigurera Azure AD Connect

Slutför följande procedur:
  
1. Anslut till katalogsynkroniseringsservern med en Anslutning till fjärrskrivbord med ett AD DS-domänkonto med lokal administratörsbehörighet. Se [Ansluta till den virtuella datorn och logga in på](/azure/virtual-machines/windows/connect-logon).
    
2. Från katalogsynkroniseringsservern öppnar du artikeln Konfigurera katalogsynkronisering för [Microsoft 365](set-up-directory-synchronization.md) och följer anvisningarna för katalogsynkronisering med synkronisering av lösenordshashar.
    
> [!CAUTION]
> Vid installationen **AAD_xxxxxxxxxxxx** kontot i organisationsenheten Lokala användare (OU). Flytta inte eller ta inte bort det här kontot, annars misslyckas synkroniseringen.
  
Det här är den resulterande konfigurationen.
  
![Fas 3 av katalogsynkroniseringsservern för Microsoft 365 med Azure som värd](../media/3f692b62-b77c-4877-abee-83c7edffa922.png)
  
I den här bilden visas katalogsynkroniseringsservern med Azure AD Connect i det virtuella Azure-nätverket på plats.
  
### <a name="assign-locations-and-licenses-to-users-in-microsoft-365"></a>Tilldela platser och licenser till användare i Microsoft 365

Azure AD Connect lägger till konton till Din Microsoft 365-prenumeration från den lokala AD DS, men för att användare ska kunna logga in på Microsoft 365 och använda tjänsterna måste kontona konfigureras med en plats och licenser. Gör så här för att lägga till platsen och aktivera licenser för lämpliga användarkonton:
  
1. Logga in på [administrationscentret för Microsoft 365](https://admin.microsoft.com)och klicka sedan på **Admin**.
    
2. Klicka på **Användare > Aktiva användare** i det vänstra navigeringsfönstret.
    
3. Markera kryssrutan bredvid den användare du vill aktivera i listan med användarkonton.
    
4. På sidan för användaren klickar du på **Redigera för** **produktlicenser.**
    
5. På sidan **Produktlicenser** väljer du en plats för användaren **för Plats** och aktiverar sedan lämpliga licenser för användaren.
    
6. När det är klart klickar **du på** Spara och sedan på **Stäng två** gånger.
    
7. Gå tillbaka till steg 3 för ytterligare användare.
    
## <a name="see-also"></a>Se även

[Microsoft 365-lösning och arkitekturcenter](../solutions/index.yml)
  
[Ansluta ett lokalt nätverk till ett virtuellt Microsoft Azure-nätverk](connect-an-on-premises-network-to-a-microsoft-azure-virtual-network.md)

[Ladda ned Azure AD Connect](https://www.microsoft.com/download/details.aspx?id=47594)
  
[Konfigurera katalogsynkronisering för Microsoft 365](set-up-directory-synchronization.md)
