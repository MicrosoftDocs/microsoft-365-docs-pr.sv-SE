---
title: Konfigurerbar inställningsreferens för Microsoft Managed Desktop
description: Ange kategorier för konfigurerbara inställningar i Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9a405f96ee7a113197fbc9c237779db3e3e5e5ca
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42812935"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>Konfigurerbar inställningsreferens - Microsoft Managed Desktop

I det här avsnittet visas de inställningskategorier som kunder kan konfigurera med Microsoft Managed Desktop. Varje inställningskategori innehåller information om krav, metodtips och hur du anpassar inställningskategorin. 

## <a name="desktop-background-picture"></a>Bakgrundsbild på skrivbordet
Du kan anpassa skrivbordsbakgrundsbilden för Microsoft Hanterade stationära enheter i organisationen. Du kan använda detta för att tillämpa ett företags varumärke eller marknadsföringsmaterial. 

### <a name="requirements"></a>Krav

Dessa krav måste uppfyllas för en skrivbordsbakgrundsbild:
- Bildfilformat - .jpg, jpeg eller .png
- Filplats - Värd på en betrodd säker http-plats (https). 
- Tillåts inte - Http- och fildelningsplatser (unc) stöds inte. 

### <a name="customize-and-deploy-desktop-background-picture"></a>Anpassa och distribuera skrivbordsbakgrundsbild

**Så här lägger du till en anpassad skrivbordsbakgrundsbild**
1. Logga in på [Microsofts administratörsportal för hanterade skrivbord](https://aka.ms/mwaasportal)
2. Under **Inställningar**väljer du **Konfigurera .**
3. I **Konfigurerbar** arbetsyta väljer du **Skrivbordsbakgrundsbild**. 
4. Ange platsen för den bild som du vill använda. 
5. Välj **Scendistribution** för att spara ändringarna och distribuera dem till testgruppen. 

## <a name="browser-start-pages"></a>Startsidor för webbläsare
Startsidor i webbläsaren öppnas på enskilda flikar när användarna startar Microsoft Edge. Om du vill göra det enkelt för användarna att öppna en uppsättning webbplatser som de använder ofta lägger du till en startsida för webbläsaren för varje webbplats. 

### <a name="requirements"></a>Krav

Du måste ange det fullständigt kvalificerade domännamnet (FQDN) för intranät eller webbplatser för din webbläsares startsidor. Om interna platser är konfigurerade meddelar du användarna att åtkomst till dessa platser endast är tillåten när den är ansluten till det interna nätverket när de är på kontoret eller när de är anslutna till en VPN-anslutning. 

### <a name="customize-and-deploy-browser-start-pages"></a>Anpassa och distribuera startsidor för webbläsare

**Så här lägger du till en startsida för webbläsaren**
1. Logga in på [Microsofts administratörsportal för hanterade skrivbord](https://aka.ms/mwaasportal)
2. Under **Inställningar**väljer du **Konfigurera .**
3. I **Konfigurerbar** arbetsyta väljer du **Startsidor för webbläsare**. 
4. Välj **Lägg till startsida**.
5. På **Startsidan För Lägg till webbläsare**anger du URL:en för den webbplats som du vill använda och väljer sedan Lägg till **startsida**. 
6. Upprepa steg 1-5 för ytterligare startsidor i webbläsaren. 
7. Välj **Scendistribution** för att spara ändringarna och distribuera dem till testgruppen.

## <a name="enterprise-mode-site-list-location"></a>Plats för plats i företagslägeslistan

Om du har specifika webbplatser och appar som du vet har kompatibilitetsproblem med Microsoft Edge kan du använda webbplatslistan för Företagsläge så att webbplatserna öppnas automatiskt med Internet Explorer 11. Om du vet att intranätplatserna inte fungerar korrekt med Microsoft Edge kan du dessutom ställa in alla intranätplatser så att de öppnas automatiskt med Internet Explorer 11. Att använda Företagsläge innebär att du kan fortsätta att använda Microsoft Edge som standardwebbläsare, samtidigt som du ser till att dina appar fortsätter att fungera i Internet Explorer 11. Mer information om webbplatslistor för företagsläge finns i [Platslistor för företagsläge och företagsläge](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode). 

Du kan ange en https:// plats eller platsen för en intern resurs där du har varit värd för webbplatslistan för företagsläge. 

### <a name="requirements"></a>Krav

Dessa krav måste uppfyllas för platsfilen för företagsläge:
- Filformat - XML-fil som uppfyller [filkraven](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- Filplats - Värdfil på en intern https-plats. 
- Inte tillåtet - Hosting på en intern filresurs, till *exempel //sharename*, är inte tillåtet

### <a name="best-practices"></a>Metodtips

Dessa bästa metoder erbjuds för att hjälpa kunderna att fatta beslut om att modernisera sin IT-infrastruktur:
- **Välj ett begränsat antal webbplatser** – Microsoft Managed Desktop använder Microsoft Edge som den webbläsare som föredras för att förbättra den övergripande säkerheten för din organisation och användbarheten för användarna. De flesta webbplatser i den här listan är för äldre webbappar som behöver en äldre version av en webbläsare som inte innehåller så många säkerhetsfunktioner. 
- **Överväg en alternativ** – Överväg en annan webbplats eller en annan webbapp som inte kräver en äldre webbläsare. Du kan också uppdatera webbplatsen så att den kan använda nyare webbläsare. Nyare webbläsare använder den senaste tekniken och förbättrar säkerheten.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>Anpassa och distribuera plats för plats för företagsplatsläge

**Så här lägger du till en plats för en företagsplatsplatslista**

1.  Logga in på [Microsofts administratörsportal för hanterade skrivbord](https://aka.ms/mwaasportal)
2.  Under **Inställningar**väljer du **Konfigurera .**
3.  I **Konfigurerbar** arbetsyta väljer du **Plats för webbplats i företagsläge**. 
4.  Ange https-platsen för din webbplatslista. 
5.  Välj **Scendistribution** för att spara ändringarna och distribuera dem till testgruppen.

## <a name="trusted-sites"></a>Betrodda platser

Med betrodda platser kan du anpassa säkerhetszoner eller där en plats kan användas för olika platser. Säkerhetszoner inkluderar: 
- Zon 1 – Zonen Lokalt intranät
- Zon 2 – Zonen Betrodda platser
- Zon 3 – Zonen Internet
- Zon 4 – Zon restriktion

### <a name="requirements"></a>Krav

Ange fullständigt kvalificerat domännamn (FQDN) för intranät eller Internet-platser för varje betrodd plats. 

### <a name="customize-and-deploy-trusted-sites"></a>Anpassa och distribuera betrodda platser

**Så här lägger du till en betrodd plats**

1. Logga in på [Microsofts administratörsportal för hanterade skrivbord](https://aka.ms/mwaasportal)
2. Under **Inställningar**väljer du **Konfigurera .**
3. I **Konfigurerbar** arbetsyta väljer du **Betrodda platser**och väljer sedan **Lägg till betrodd plats**. 
4. På **Lägg till betrodd plats**anger du URL:en, väljer en säkerhetszon och väljer sedan Lägg till betrodd **plats**. 
5. Upprepa steg 1-4 för varje betrodd plats som du vill lägga till. 
6. Välj **Scendistribution** för att spara ändringarna och distribuera dem till testgruppen.

**Så här tar du bort en betrodd plats**

1. Logga in på [Microsofts administratörsportal för hanterade skrivbord](https://aka.ms/mwaasportal)
2. Under **Inställningar**väljer du **Konfigurera .**
3. I **Konfigurerbar** arbetsyta väljer du **Betrodda platser**. 
4. Markera den webbplats som du vill ta bort och välj sedan **Ta bort**. 
5. Upprepa steg 1-4 för varje betrodd plats som du vill ta bort. 
6. Välj **Scendistribution** för att spara ändringarna och distribuera dem till testgruppen.

## <a name="proxy"></a>Proxy
Du kan hantera nätverksproxyinställningar för din organisation. Lägg till proxyservern och portnumret och lägg sedan till undantag från proxywebbplatsen. Microsoft Managed Desktop innehåller en uppsättning standardproxyundantag som krävs för att tjänsten ska fungera. Standardundansuteskapslistan får endast ändras av tjänsten Microsoft Managed Desktop.  Mer information finns i [Nätverkskonfiguration för Microsoft Managed Desktop](../get-ready/network.md). 

De proxywebbplatsundantag som du lägger till i Microsoft Managed Desktop-portalen läggs till i standardproxyundantagen som ingår i Microsoft Managed Desktop-tjänsten. 

> [!NOTE]
> Att uppdatera standardundantagslistan för proxy prioriteras alltid framför kunddistributioner. Det innebär att den stegvisa distributionen pausas om det finns en distribution för standardundantagslistan för proxy.  

### <a name="requirements"></a>Krav

Dessa krav måste uppfyllas för proxyserver- och proxyplatsundantag:
- Måste vara en giltig serveradress och portnummer
- Webbadresser måste vara en giltig http-webbplats 

### <a name="customize-and-deploy-proxies"></a>Anpassa och distribuera proxyservrar

**Så här lägger du till ett enskilt proxyplatsundantag**

1. Logga in på [Microsofts administratörsportal för hanterade skrivbord](https://aka.ms/mwaasportal)
2. Under **Inställningar**väljer du **Konfigurera .**
3. I **Konfigurerbar** arbetsyta väljer du **Proxy**. 
4. Ange **adress-** och **portnumret** för din proxyserver och välj sedan **Lägg till proxyundantag**. 
5. Ange URL:en för en giltig http-webbplats och välj sedan **Lägg till proxyundantag**. 
6. Upprepa steg 1-5 för varje betrodd plats som du vill lägga till. 
7. Välj **Scendistribution** för att spara ändringarna och distribuera dem till testgruppen.

## <a name="additional-resources"></a>Ytterligare resurser
- [Översikt över konfigurerbara inställningar](config-setting-overview.md) 
- [Distribuera konfigurerbara inställningar](config-setting-deploy.md)
