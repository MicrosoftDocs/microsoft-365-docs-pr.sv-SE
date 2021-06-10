---
title: Konfigurerbara inställningsreferenser för Microsoft Hanterat skrivbord
description: Ange kategorier för konfigurerbara inställningar i Microsoft Hanterat skrivbord
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 1245268b6128aa022a972fd0282009573558ec47
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917710"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>Referens för konfigurerbara inställningar – Microsoft Hanterat skrivbord

Det här avsnittet innehåller de inställningskategorier som kunderna kan konfigurera med Microsoft Hanterat skrivbord. Varje inställningskategori innehåller information om krav, metodtips och hur du anpassar inställningskategorin. 

## <a name="desktop-background-picture"></a>Bild av skrivbordsbakgrund
Du kan anpassa skrivbordsbakgrunden för Microsoft Hanterat skrivbord enheter i organisationen. Du kan använda detta för att tillämpa ett företags varumärke eller marknadsföringsmaterial. 

### <a name="requirements"></a>Krav

Dessa krav måste vara uppfyllda för en bakgrundsbild på skrivbordet:
- Bildfilformat – .jpg, jpeg eller .png
- Filplats – värd för en betrodd säker http (https)-plats. 
- Tillåts inte – Http- och filresursplatser (unc) stöds inte. 

### <a name="customize-and-deploy-desktop-background-picture"></a>Anpassa och distribuera skrivbordsbakgrund

**Så här lägger du till en egen bakgrundsbild på skrivbordet**
1. Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till **menyn** Enheter
2. Titta efter avsnittet Microsoft Hanterat skrivbord, välj **Inställningar**.
3. I **Inställningar** väljer du **Skrivbordsbakgrundsbild**. 
4. Ange platsen för den bild du vill använda. 
5. Välj **Fasdistribution** för att spara ändringarna och distribuera dem till testgruppen. 

## <a name="browser-start-pages"></a>Startsidor för webbläsare
Webbläsaren startar sidor öppna på enskilda flikar när användarna börjar Microsoft Edge. Om du vill göra det enkelt för användarna att öppna en uppsättning webbplatser som de använder ofta kan du lägga till en startsida för webbläsaren för varje webbplats. 

### <a name="requirements"></a>Krav

Du måste ange det fullständigt kvalificerade domännamnet (FQDN) för intranätwebbplatser eller internetwebbplatser för webbläsarens startsidor. Om interna webbplatser konfigureras bör du meddela användarna att åtkomst till dessa webbplatser endast är tillåten när de är anslutna till det interna nätverket på kontoret, eller när de är anslutna till en VPN-anslutning. 

### <a name="customize-and-deploy-browser-start-pages"></a>Anpassa och distribuera startsidor i webbläsare

**Så här lägger du till en startsida för en webbläsare**
1. Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till **menyn** Enheter
2. Titta efter avsnittet Microsoft Hanterat skrivbord, välj **Inställningar**.
3. I **Inställningar** väljer du **Webbläsarens startsidor**. 
4. Välj **Lägg till startsida.**
5. På **startsidan för Lägg till webbläsare** anger du URL-adressen för den webbplats du vill använda och väljer sedan Lägg till **startsida.** 
6. Upprepa steg 1–5 för ytterligare startsidor i webbläsaren. 
7. Välj **Fasdistribution** för att spara ändringarna och distribuera dem till testgruppen.

## <a name="enterprise-mode-site-list-location"></a>Plats för webbplatslista i företagsläge

Om du har specifika webbplatser och program som du vet har kompatibilitetsproblem med Microsoft Edge kan du använda webbplatslistan i Företagsläge så att webbplatserna öppnas automatiskt med hjälp av Internet Explorer 11. Om du vet att intranätwebbplatserna inte fungerar korrekt med Microsoft Edge kan du ange att alla intranätwebbplatser ska öppnas med hjälp av Internet Explorer 11 automatiskt. Om du använder Företagsläge kan du fortsätta att använda Microsoft Edge som standardwebbläsare, samtidigt som du ser till att dina program fortsätter att arbeta med Internet Explorer 11. Mer information om webbplatslistor för företagsläge finns i [Webbplatslistor för företagsläge och Företagsläge.](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode) 

Du kan ange https:// plats eller plats för en intern delning där du har lagrat webbplatslistan i företagsläget. 

### <a name="requirements"></a>Krav

De här kraven måste uppfyllas för listfilen för företagswebbplatser:
- Filformat – XML-fil som uppfyller [filkraven](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- Filplats – värdfil på en intern https-plats. 
- Tillåts inte – Värd för en intern filresurs, t.ex. *//sharename,* är inte tillåtet

### <a name="best-practices"></a>Metodtips

Dessa metodtips erbjuds för att hjälpa kunder fatta beslut om att modernisera IT-infrastrukturen:
- **Välj ett begränsat antal webbplatser** – Microsoft Hanterat skrivbord använder Microsoft Edge som standardwebbläsare för att förbättra organisationens säkerhet och användbarhet för användarna. De flesta webbplatser i den här listan gäller äldre webbappar som behöver en äldre version av en webbläsare som inte innehåller lika många säkerhetsfunktioner. 
- **Det kan vara** en alternativ metod – du kan överväga en annan webbplats eller ett annat webbapp som inte kräver en äldre webbläsare. Du kan även uppdatera webbplatsen så att den kan använda nyare webbläsare. Nyare webbläsare använder den senaste tekniken och förbättrar säkerheten.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>Anpassa och distribuera listplats för webbplatsläge för företag

**Så här lägger du till en plats för en företagswebbplatslista**

1. Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till **menyn** Enheter
2. Titta efter avsnittet Microsoft Hanterat skrivbord, välj **Inställningar**.
3. I **Inställningar** väljer du Plats **för webbplatslista i företagsläge.** 
4. Ange webbplatslistans https-plats. 
5. Välj **Fasdistribution** för att spara ändringarna och distribuera dem till testgruppen.

## <a name="trusted-sites"></a>Betrodda platser

Med betrodda platser kan du anpassa säkerhetszoner eller var en webbplats kan användas för olika webbplatser. Säkerhetszoner omfattar: 
- Zon 1 – Lokalt intranät
- Zon 2 – Betrodda platser
- Zon 3 – Internetzon
- Zon 4 – zonen Begränsade platser

### <a name="requirements"></a>Krav

Ange det fullständigt kvalificerade domännamnet (FQDN) för intranätwebbplatser eller Internetwebbplatser för varje betrodd webbplats. 

### <a name="customize-and-deploy-trusted-sites"></a>Anpassa och distribuera betrodda webbplatser

**Lägga till en betrodd webbplats**

1. Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till **menyn** Enheter
2. Titta efter avsnittet Microsoft Hanterat skrivbord, välj **Inställningar**.
3. I **Inställningar** väljer du **Betrodda platser** och sedan Lägg till **betrodd webbplats**. 
4. På **Lägg till betrodd** webbplats anger du URL-adressen, väljer en säkerhetszon och väljer sedan Lägg till betrodd **webbplats.** 
5. Upprepa steg 1–4 för varje betrodd webbplats som du vill lägga till. 
6. Välj **Fasdistribution** för att spara ändringarna och distribuera dem till testgruppen.

**Ta bort en betrodd webbplats**

1. Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till **menyn** Enheter
2. Titta efter avsnittet Microsoft Hanterat skrivbord, välj **Inställningar**.
3. I **Inställningar** väljer du **Betrodda platser**. 
4. Markera den webbplats du vill ta bort och välj sedan Ta **bort**. 
5. Upprepa steg 1–4 för varje betrodd webbplats som du vill ta bort. 
6. Välj **Fasdistribution** för att spara ändringarna och distribuera dem till testgruppen.

## <a name="proxy"></a>Proxy
Du kan hantera nätverkets proxyinställningar för din organisation. Lägg till din proxyserver och portnummer och lägg sedan till undantag för din proxywebbplats. Microsoft Hanterat skrivbord innehåller en uppsättning standardproxyundantag som krävs för att tjänsten ska fungera. Standard undantagslistan kan bara ändras av den Microsoft Hanterat skrivbord tjänsten.  Mer information finns i [Nätverkskonfiguration för Microsoft Hanterat skrivbord](../get-ready/network.md). 

Proxywebbplatsundantag som du lägger till Microsoft Hanterat skrivbord-portalen läggs till i standardproxyundantagen som ingår i Microsoft Hanterat skrivbord tjänsten. 

> [!NOTE]
> Uppdatering av standardlistan över proxyservrar prioriteras alltid före kunddistributioner. Det innebär att den fasade distributionen pausas om det finns en distribution för standardlistan med proxy-undantag.  

### <a name="requirements"></a>Krav

De här kraven måste vara uppfyllda för proxyserver- och proxywebbplatsundantag:
- Måste vara en giltig serveradress och ett giltigt portnummer
- URL-adresser måste vara giltiga på http-webbplatsen 

### <a name="customize-and-deploy-proxies"></a>Anpassa och distribuera proxy proxy

**Lägga till ett enskilt proxywebbplatsantag**

1. Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till **menyn** Enheter
2. Titta efter avsnittet Microsoft Hanterat skrivbord, välj **Inställningar**.
3. Välj **Inställningar** i **arbetsytan.** 
4. Ange **adress-** och **portnumret för** proxyservern och välj sedan Lägg **till proxy-undantag**. 
5. Ange URL-adressen till en giltig http-webbplats och välj sedan **Lägg till proxy-undantag**. 
6. Upprepa steg 1–5 för varje betrodd webbplats som du vill lägga till. 
7. Välj **Fasdistribution** för att spara ändringarna och distribuera dem till testgruppen.

## <a name="additional-resources"></a>Ytterligare resurser
- [Översikt över konfigurerbara inställningar](config-setting-overview.md) 
- [Distribuera inställningar som kan konfigureras](config-setting-deploy.md)