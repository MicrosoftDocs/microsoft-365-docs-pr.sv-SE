---
title: Konfigurations bara referens inställningar för Microsoft Managed Desktop
description: Ställa in kategorier för konfigurerbara inställningar på Microsoft Managed Desktop
keywords: Microsoft Hanterat skrivbord, Microsoft 365, tjänst, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2c7c7d75fad58cab0cd6d19a16a97667ea3641a1
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104494"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>Referens för konfigurerbara inställningar – Microsoft Managed Desktop

I det här avsnittet visas de inställnings kategorier som kunder kan konfigurera med Microsoft Managed Desktop. Alla inställnings kategorier innehåller information om krav, metod tips och hur du anpassar inställnings kategorin. 

## <a name="desktop-background-picture"></a>Skriv bords bakgrund
Du kan anpassa Skriv bords bakgrund för Microsoft Managed Station ära enheter i din organisation. Du kan använda det här om du vill använda ett företags varumärkes-eller marknadsförings material. 

### <a name="requirements"></a>Krav

Dessa krav måste uppfyllas för en Skriv bords bakgrund:
- Bild fil format-. jpg, JPEG eller. png
- Fil Sök väg-värd på en betrodd säker http-plats (https). 
- Ej tillåtna-http-och fildelnings platser (UNC) stöds inte. 

### <a name="customize-and-deploy-desktop-background-picture"></a>Anpassa och distribuera Skriv bords bakgrund

**Så här lägger du till en egen Skriv bords bakgrund**
1. Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till menyn **enheter**
2. Leta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.
3. I arbets ytan **Inställningar** väljer du **Skriv bords bakgrund**. 
4. Ange platsen för den bild du vill använda. 
5. Välj **fas distribution** för att spara ändringarna och distribuera dem till test gruppen. 

## <a name="browser-start-pages"></a>Webbläsarens start sidor
Webbläsarens start sidor öppnas på enskilda flikar när användarna startar Microsoft Edge. Om du vill göra det lättare för dina användare att öppna en uppsättning webbplatser som de använder ofta, kan du lägga till en webb läsar start sida för varje webbplats. 

### <a name="requirements"></a>Krav

Du måste ange det fullständigt kvalificerade domän namnet (FQDN) för intranät-eller Internet-webbplatser för webbläsarens start sidor. Om interna webbplatser är konfigurerade kan användarna veta att åtkomsten till dessa webbplatser endast tillåts när du är ansluten till det interna nätverket när du befinner dig på kontoret eller när du är ansluten till en VPN-anslutning. 

### <a name="customize-and-deploy-browser-start-pages"></a>Anpassa och distribuera webbläsarens start sidor

**Så här lägger du till en webbläsares start sida**
1. Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till menyn **enheter**
2. Leta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.
3. I arbets ytan **Inställningar** väljer du **webbläsarens start sidor**. 
4. Välj **Lägg till start sidan**.
5. På **sidan Lägg till Start sida**anger du webb adressen till den webbplats som du vill använda och väljer sedan **Lägg till Start sida**. 
6. Upprepa steg 1-5 för ytterligare start sidor i webbläsare. 
7. Välj **fas distribution** för att spara ändringarna och distribuera dem till test gruppen.

## <a name="enterprise-mode-site-list-location"></a>Plats för webbplats lista för företags läge

Om du har särskilda webbplatser och program som du vet har kompatibilitetsproblem med Microsoft Edge kan du använda webbplats listan för företags läge så att webbplatserna öppnas automatiskt med Internet Explorer 11. Om du vet att dina intranät platser inte fungerar korrekt med Microsoft Edge kan du också ställa in alla intranät webbplatser att öppna via Internet Explorer 11 automatiskt. Om du använder företags läget kan du fortsätta att använda Microsoft Edge som standard webbläsare, samtidigt som du ser till att dina appar fortsätter fungera med Internet Explorer 11. Mer information om webbplats listor för företags läge finns i avsnittet [företags läge och webbplats listor för företags](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)läge. 

Du kan ange en https://-plats eller platsen för en intern resurs där du har en värd lista för webbplats listan. 

### <a name="requirements"></a>Krav

Dessa krav måste uppfyllas för webbplats listan för företags läget:
- Fil format-XML-fil som uppfyller [fil kraven](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- Fil Sök väg – värd fil på en intern https-plats. 
- Inte tillåten-värd på en intern fil resurs, till exempel *//ShareName*, är inte tillåten

### <a name="best-practices"></a>Metodtips

De här bästa metoderna är att hjälpa kunder att modernisera sin IT-infrastruktur:
- **Välj ett begränsat antal webbplatser** – Microsoft Managed Desktop använder Microsoft Edge som standard webbläsare för att förbättra den övergripande säkerheten för din organisation och användbarhet för dina användare. De flesta webbplatser i den här listan är för gamla webb program som behöver en äldre version av en webbläsare som inte innehåller några säkerhetsfunktioner. 
- **Överväg** att överväga en annan webbplats eller webbprogram som inte kräver en äldre webbläsare. Eller Överväg att uppdatera webbplatsen så att den kan använda nyare webbläsare. Nyare webbläsare använder den senaste tekniken och förbättrar säkerheten.

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>Sidan anpassa och distribuera listans plats med företagets webbplats läge

**Så här lägger du till en plats för en lista med företagets webbplats lägen**

1. Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till menyn **enheter**
2. Leta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.
3. I arbets ytan **Inställningar** väljer du **platsen för webbplats listan för företags läget**. 
4. Ange https-platsen för din webbplats lista. 
5. Välj **fas distribution** för att spara ändringarna och distribuera dem till test gruppen.

## <a name="trusted-sites"></a>Tillförlitliga platser

Med tillförlitliga webbplatser kan du anpassa säkerhets zoner eller var en webbplats ska användas, för olika webbplatser. Säkerhets zoner inkluderar: 
- Zon 1 – zonen Lokalt intranät
- Zone 2 – zonen Tillförlitliga platser
- Zon 3 – zonen Internet
- Zone 4 – zonen Ej tillförlitliga platser

### <a name="requirements"></a>Krav

Ange det fullständigt kvalificerade domän namnet (FQDN) för intranät-eller Internet webbplatser för varje betrodd webbplats. 

### <a name="customize-and-deploy-trusted-sites"></a>Anpassa och distribuera tillförlitliga webbplatser

**Så här lägger du till en betrodd webbplats**

1. Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till menyn **enheter**
2. Leta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.
3. I **inställnings** arbets ytan väljer du **tillförlitliga platser**och väljer sedan **Lägg till betrodd webbplats**. 
4. På **Lägg till betrodd webbplats**anger du webb adressen, väljer en säkerhets zon och väljer sedan **Lägg till betrodd webbplats**. 
5. Upprepa steg 1-4 för varje betrodd webbplats du vill lägga till. 
6. Välj **fas distribution** för att spara ändringarna och distribuera dem till test gruppen.

**Så här tar du bort en betrodd webbplats**

1. Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till menyn **enheter**
2. Leta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.
3. Välj **tillförlitliga platser**i arbets ytan **Inställningar** . 
4. Markera den webbplats du vill ta bort och välj sedan **ta bort**. 
5. Upprepa steg 1-4 för varje betrodd webbplats du vill ta bort. 
6. Välj **fas distribution** för att spara ändringarna och distribuera dem till test gruppen.

## <a name="proxy"></a>Identifiera
Du kan hantera nätverks-proxyinställningar för din organisation. Lägg till proxyserver och port nummer och Lägg sedan till dina webbplats undantag. Microsoft Managed Desktop innehåller en uppsättning standardproxy-undantag som krävs för att tjänsten ska fungera. Standard uteslutnings listan kan bara ändras av Microsoft Managed Desktop-tjänsten.  Mer information finns i [nätverks konfiguration för Microsoft Managed Desktop](../get-ready/network.md). 

De undantag som du lägger till i Microsoft Managed Desktop-portalen läggs till i standardvärden för proxy-undantag som ingår i Microsoft Managed Desktop-tjänsten. 

> [!NOTE]
> Uppdatering av standard listan över undantag är alltid prioriterad över kund distributioner. Det innebär att din stegvisa distribution kommer att pausas om det finns en distribution för standard listan över undantag.  

### <a name="requirements"></a>Krav

De här kraven måste uppfyllas för proxy server-och proxy webbplats undantag:
- Måste vara en giltig server adress och port nummer
- URL: er måste vara en giltig http-webbplats 

### <a name="customize-and-deploy-proxies"></a>Anpassa och distribuera proxyservrar

**Lägga till ett enskilt fel i en webbplats**

1. Logga in på [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) och gå till menyn **enheter**
2. Leta efter avsnittet Microsoft Managed Desktop och välj **Inställningar**.
3. Välj **proxy**i arbets ytan **Inställningar** . 
4. Ange **adress** och **port nummer** för din proxyserver och välj sedan **Lägg till ett proxy-undantag**. 
5. Ange URL: en till en giltig http-plats och välj sedan **Lägg till ett proxy-undantag**. 
6. Upprepa steg 1-5 för varje betrodd webbplats du vill lägga till. 
7. Välj **fas distribution** för att spara ändringarna och distribuera dem till test gruppen.

## <a name="additional-resources"></a>Ytterligare resurser
- [Inställningar för konfigurerings bara översikt](config-setting-overview.md) 
- [Distribuera inställningar som kan konfigureras](config-setting-deploy.md)
