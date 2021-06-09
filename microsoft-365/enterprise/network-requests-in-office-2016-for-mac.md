---
title: Nätverksbegäranden i Office för Mac
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/9/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOM160
ms.assetid: afdae969-4046-44b9-9adb-f1bab216414b
description: I den här artikeln beskrivs vilka slutpunkter och URL:Office för Mac som programmen försöker nå och vilka tjänster som tillhandahålls.
ms.openlocfilehash: b777b4ea7e03495cb6389be8fe05e96a26fd9664
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694635"
---
# <a name="network-requests-in-office-for-mac"></a>Nätverksbegäranden i Office för Mac

Office för Mac-program ger samma upplevelse som de ursprungliga apparna på macOS-plattformen. Varje app har utformats för att fungera i en mängd olika scenarier, inklusive tillstånd när ingen nätverksåtkomst är tillgänglig. När en dator är ansluten till ett nätverk kan programmen automatiskt ansluta till flera olika webbaserade tjänster som ger förbättrade funktioner. I följande information beskrivs vilka slutpunkter och URL:er programmen försöker komma åt och vilka tjänster som tillhandahålls. Den här informationen är användbar när du felsöker nätverkskonfigurationsproblem och ställer in principer för proxyservrar i nätverket. Informationen i den här artikeln är tänkt som ett komplement till artikeln [Office 365-](urls-and-ip-address-ranges.md)och adressintervall, som omfattar slutpunkter för datorer med Microsoft Windows. Om inget anges gäller informationen i den här artikeln även Office 2019 för Mac och Office 2016 för Mac, som är tillgängliga som ett köp i butik eller via ett volymlicensieringsavtal. 

  
Det mesta i den här artikeln är tabeller med information om nätverks-URL:er, typ och beskrivning av tjänsten eller funktionen som tillhandahålls av den slutpunkten. Var och en Office sin tjänst- och slutpunktsanvändning. Följande program definieras i tabellerna nedan:
  
- W: Word
- P: PowerPoint
- X: Excel
- O: Outlook
- N: OneNote
   
Url-typen definieras på följande sätt:
  
- ST: Statisk – URL:en är hårdkodad i klientprogrammet.
    
- SS: Semi-Static – URL:en kodas som en del av en webbsida eller omdirigerare.
    
- CS: Konfigurationstjänst – URL:en returneras som en del Office konfigurationstjänsten.

    
## <a name="office-for-mac-default-configuration"></a>Office för Mac standardkonfiguration

 **Installation och uppdateringar**
  
Följande nätverksslutpunkter används för att ladda ned Office för Mac-installationsprogrammet från Microsoft Content Delivery Network (CDN).
  
|**URL**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |ST  <br/> |Microsoft 365 Tjänsten vidarebefordran av installationsportal till de senaste installationspaketen.  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |SS  <br/> |Platsen för installationspaketen på Content Delivery Network.  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |SS  <br/> |Platsen för installationspaketen på Content Delivery Network.  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |ST  <br/> |Slutpunkt för hanteringskontroll för Microsoft AutoUpdate  <br/> |
   
 **Första appstarten**
  
Följande nätverksslutpunkter kontaktas vid första lanseringen av en Office-appen. Dessa slutpunkter ger Office funktioner för användare, och URL:erna kontaktas oavsett licenstyp (inklusive volymlicensinstallationer).
  
|**URL**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |ST  <br/> |Konfiguration för flygning – gör det möjligt att använda lätt och experimenterande funktioner.  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |Nätverkskonfigurationstest för flygtestning  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |Nätverkskonfigurationstest för flygtestning  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Konfigurationstjänst – huvudlista över tjänstslutpunkter.  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Ladda ned telemetriregler – Informerar klienten om vilka data och händelser som ska överföras till den telemetriska tjänsten.  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |N  <br/> |CS  <br/> |OneNote Telemetritjänst  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Telemetri Upload rapportering – "Hjärtart" och felhändelser som inträffar i klienten laddas upp till telemetritjänsten.  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Office Malltjänst – förser användarna med onlinedokumentmallar.  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |CS  <br/> |Office Nedladdningar av mallar – Storage av PNG-mallbilder.  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Lagra konfiguration för Office appar.  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Office Katalog över dokumentintegreringstjänster (lista över tjänster och slutpunkter) och identifiering av hemsfär.  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Resurser för identifiering av startsfär v2 (15.40 och senare)  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Manifest för Microsoft AutoUpdate – kontrollerar om det finns tillgängliga uppdateringar  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |SS  <br/> |Microsoft Ajax JavaScript-bibliotek  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia-app för Office konfiguration och resurser.  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing Mappa program för Office konfiguration och resurser.  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |People Graph app för Office konfiguration och resurser.  <br/> |
|```https://www.onenote.com/```  <br/> |N  <br/> |ST  <br/> |Vad är nytt innehåll för OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |ST  <br/> |Nytt innehåll för OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |SS  <br/> |Bilder av nya funktioner i OneNote.  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |ST  <br/> |Support i programmet.  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |O  <br/> |ST  <br/> |Tjänst för identifiering av e-postkonto.  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook AutoDiscovery  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook slutpunkt för Microsoft 365 tjänst.  <br/> |
|```https://r1.res.office365.com/```  <br/> |O  <br/> |ST  <br/> |Ikoner Outlook tillägg.  <br/> |
   
> [!NOTE]
> Konfigurationstjänsten Office fungerar som en tjänst för automatisk identifiering för alla Microsoft Office, inte bara för Mac. Slutpunkterna som returneras i svaret är semi-statiska om ändringen är mycket oregelregelen, men fortfarande möjligt. 
  
 **Logga in**
  
Följande nätverksslutpunkter kontaktas när du loggar in på molnbaserad lagring. Olika tjänster kan kontaktas beroende på din kontotyp. Till exempel:
  
- **MSA: Microsoft-konto –** används vanligtvis för konsument- och återförsäljarscenarier 
    
- **OrgID: Organisationskonto** – används vanligtvis för kommersiella scenarier 
    
|**URL**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |ST  <br/> |Windows Auktoriseringstjänst  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft 365 Inloggningstjänst (OrgID)  <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Inloggningstjänst för Microsoft-konto (MSA)  <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |CS  <br/> |Hjälp för Inloggningstjänst för Microsoft-konto (MSA)  <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |SS  <br/> |Microsoft 365 Inloggningsmärke (OrgID)  <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Dokument och platser Storage Locator  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Dokumenttjänsten Senast använda (MRU)  <br/> |
   
> [!NOTE]
> Om du har en prenumerationsbaserad licens eller en återförsäljarlicens aktiveras produkten om du loggar in och du får även tillgång till molnresurser som OneDrive. För volymlicensinstallationer uppmanas användarna fortfarande att logga in (som standard), men det krävs bara för åtkomst till molnresurser eftersom produkten redan är aktiverad. 
  
 **Produktaktivering**
  
Följande nätverksslutpunkter gäller endast Microsoft 365 prenumerationsaktiveringar och återförsäljarlicensaktiveringar. De gäller specifikt INTE för volymlicensinstallationer.
  
|**URL**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Office Licensieringstjänst  <br/> |
   
 **Innehåll i Nytt**
  
Följande nätverksslutpunkter gäller endast Microsoft 365 prenumeration.
  
|**URL**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |SS  <br/> |Nytt JSON-sidinnehåll.  <br/> |
   
 **Researcher**
  
Följande nätverksslutpunkter gäller endast Microsoft 365 prenumeration.
  
|**URL**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Researcher webbtjänst  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Researcher statiskt innehåll  <br/> |
|```https://www.bing.com/```  <br/> |W  <br/> |CS  <br/> |Innehållsleverantör för Researcher  <br/> |
   
 **Smart sökning**
  
Följande nätverksslutpunkter gäller både för Microsoft 365- och återförsäljar-/volymlicensaktiveringar.
  
|**URL**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Webbtjänst för Insikter  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |CS  <br/> |JQuery-bibliotek  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |CS  <br/> |Stöd för JavaScript-bibliotek  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |CS  <br/> |Innehållsleverantör för Insikter  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |CS  <br/> |Innehållsleverantör för Insikter  <br/> |
   
 **PowerPoint Designer**
  
Följande nätverksslutpunkter gäller endast Microsoft 365 prenumeration.
  
|**URL**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPoint Designer webbtjänst  <br/> |
   
 **PowerPoint Snabbstart**
  
Följande nätverksslutpunkter gäller endast Microsoft 365 prenumeration.
  
|**URL**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPoint Snabbstartwebbtjänst  <br/> |
   
 **Skicka ett leende/en bägare**
  
Följande nätverksslutpunkter gäller både för Microsoft 365- och återförsäljar-/volymlicensaktiveringar.
  
|**URL**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |CS  <br/> |Tjänsten Skicka ett leende  <br/> |
   
 **Kontakta support**
  
Följande nätverksslutpunkter gäller både för Microsoft 365- och återförsäljar-/volymlicensaktiveringar.
  
|**URL**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |O  <br/> |CS  <br/> |Kontakta support  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |CS  <br/> |Support i programmet  <br/> |
   
 **Spara som PDF**
  
Följande nätverksslutpunkter gäller både för Microsoft 365- och återförsäljar-/volymlicensaktiveringar.
  
|**URL**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |W  <br/> |CS  <br/> |Konverteringstjänst för Word-dokument (PDF)  <br/> |
   
 **Office Appar (även kallat tillägg)**
  
Följande nätverksslutpunkter gäller både för Microsoft 365-prenumerationsaktiveringar och återförsäljar-/volymlicensaktiveringar Office tillägg är betrodda.
  
|**URL**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |CS  <br/> |Office-appen store-konfiguration  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia-appresurser  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing Mappa appresurser  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |X  <br/> |SS  <br/> |Kontakter Graph programresurser  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |SS  <br/> |Office Omdirigeringstjänst  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |SS  <br/> |Office JavaScript-bibliotek  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |WX  <br/> |SS  <br/> |Telemetri- och rapporteringstjänst för Office program  <br/> |
|```https://ajax.microsoft.com/```  <br/> |W  <br/> |SS  <br/> |Microsoft Ajax JavaScript-bibliotek  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |X  <br/> |SS  <br/> |Microsoft Ajax JavaScript-bibliotek  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Office JavaScript-bibliotek  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Supportresurser  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Supportresurser  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |SS  <br/> |Supportresurser  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |SS  <br/> |JavaScript-bibliotek  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |SS  <br/> |Felrapportering  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |SS  <br/> |Teckensnittsresurser  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |SS  <br/> |Telemetritjänst  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Telemetrirapportering  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |SS  <br/> |Microsoft Store Resursbibliotek  <br/> |
|```https://*.wikipedia.org/```  <br/> |W  <br/> |SS  <br/> |Wikipedia-sidresurser  <br/> |
|```https://upload.wikimedia.org/```  <br/> |W  <br/> |SS  <br/> |Wikipedia-medieresurser  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |W  <br/> |SS  <br/> |Ram för Wikipedia i begränsat läge  <br/> |
|```https://*.virtualearth.net/```  <br/> |X  <br/> |SS  <br/> |Kartmallar  <br/> |
   
 **Säkra länkar**
  
Följande nätverksslutpunkt gäller endast för Office-program för Microsoft 365 prenumeration.
  
|**URL**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |CS  <br/> |Microsoft Valv Link Service  <br/> |
   
 **Kraschrapportering**
  
Följande nätverksslutpunkt gäller för alla Office-program för Microsoft 365 prenumerationsaktiveringar och återförsäljar-/volymlicensaktiveringar. När en process oväntat kraschar skapas en rapport och skickas till tjänsten Watson.
  
|**URL**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |ST  <br/> |Microsofts felrapporteringstjänst  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |ST  <br/> |Office Tjänst för samarbetsinsikter  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>Alternativ för att minska nätverksbegäranden och trafik

Standardkonfigurationen av Office för Mac ger en bra användarupplevelse, både vad gäller funktioner och att hålla datorn uppdaterad. I vissa fall kanske du vill förhindra att program kontaktar nätverksslutpunkter. I det här avsnittet beskrivs olika alternativ för att göra detta.
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>Inaktivera molntjänster Sign-In och Office Add-Ins
  
Volymlicenskunder kan ha strikta principer om att spara dokument i molnbaserad lagring. Följande inställning per program kan ställas in för att inaktivera MSA/OrgID-inloggning och åtkomst Office tillägg.
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

Om användarna försöker komma Sign-In funktionen ser de ett felmeddelande om att det inte finns någon nätverksanslutning. Eftersom den här inställningen även blockerar produktaktivering online bör den bara användas för volymlicensinstallationer. Med hjälp av den här inställningen hindras Office program från att komma åt följande slutpunkter:
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- Alla slutpunkter som visas i avsnittet "Logga in" ovan.
    
- Alla slutpunkter som visas i avsnittet "Smart sökning" ovan.
    
- Alla slutpunkter som visas i avsnittet "Produktaktivering" ovan.
    
- Alla slutpunkter som visas i avsnittet Office (även kallat tillägg) ovan.
    
Om du vill återställa alla funktioner för användaren anger du antingen inställningen till "2" eller tar bort den.
  
> [!NOTE]
> Den här inställningen Office för Mac version 15.25 [160726] eller senare. 
  
### <a name="telemetry"></a>Telemetri 
  
Office för Mac skickar regelbundet telemetriinformation till Microsoft. Data överförs till Nexus-slutpunkten. Med hjälp av telemetridata bedömer teknikteamet de olika teknikteamens hälsotillstånd och eventuella oväntade beteenden Office-appen. Det finns två kategorier av telemetri:
  
- **Hjärtslag** innehåller information om version och licens. Den här informationen skickas direkt när programmet startas. 
    
- **Användning** innehåller information om hur olika appar används och allvarliga fel. Dessa data skickas var 60:e minut. 
    
Microsoft ser mycket allvarligt på din integritet. Du kan läsa om Microsofts policy för datainsamling på [https://privacy.microsoft.com](https://privacy.microsoft.com) . För att förhindra att program skickar telemetriska data om användning kan **inställningen SendAllTelemetryEnabled** justeras. Inställningen är per program och kan ställas in via macOS-konfigurationsprofiler eller manuellt från terminalen: 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

Telemetri för hjärtslag skickas alltid och kan inte inaktiveras.
  
### <a name="crash-reporting"></a>Kraschrapportering
  
När ett allvarligt programfel uppstår kommer programmet oväntat att avslutas och en kraschrapport laddas upp till tjänsten Watson. Kraschrapporten består av en anropsstack, som är en lista över de steg programmet bearbetar som lett fram till kraschen. Med hjälp av de här stegen kan teknikteamet identifiera exakt vilken funktion som inte fungerade som den skulle och varför.
  
I vissa fall leder innehållet i ett dokument till att programmet kraschar. Om programmet identifierar dokumentet som orsaken får användaren frågan om det går bra att skicka dokumentet tillsammans med anropsstacken. Användarna kan fatta ett välgrundat beslut om den här frågan. IT-administratörer kan ha strikta krav på överföring av dokument och kan fatta beslut om att användaren aldrig får skicka dokument. Följande inställning kan göras för att förhindra att dokument skickas och för att användaren inte ska tillfrågas:
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> Om **SendAllTelemetryEnabled** är inställt på **FALSKT** inaktiveras all kraschrapportering för processen. Om du vill aktivera kraschrapportering utan att skicka användning telemetri kan du göra följande inställning: ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>Uppdateringar
  
Microsoft släpper Office för Mac uppdateras med jämna mellanrum (vanligtvis en gång i månaden). Vi vill verkligen uppmana både användare och IT-administratörer att hålla alla maskiner uppdaterade och se till att de senaste säkerhetskorrigeringarna installeras. I de fall då IT-administratörer noga vill kontrollera och hantera uppdateringarna kan du göra följande inställning för att förhindra att AutoUpdate-processen automatiskt identifierar och erbjuder produktuppdateringar:
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>Blockera förfrågningar med en brandvägg/proxy
  
Om organisationen blockerar förfrågningar till URL-adresser via en brandvägg eller proxyserver måste du konfigurera URL-adresserna som listas i det här dokumentet som antingen tillåtna eller blockering som visas med ett 40X-svar (t.ex. 403 eller 404). Ett 40X-svar gör att Office-programmen accepterar att det inte går att komma åt resursen, och det ger en snabbare användarupplevelse än att bara släppa anslutningen, vilket i sin tur gör att klienten försöker igen.
  
Om din proxyserver kräver autentisering returneras ett 407-svar till klienten. För bästa upplevelse bör du kontrollera att du använder Office för Mac version 15.27 eller senare, eftersom de innehåller specifika korrigeringar för att arbeta med NTLM- och Kerberos-servrar.
  
  
## <a name="see-also"></a>Se även

[URL-adresser och IP-adressintervall för Office 365](urls-and-ip-address-ranges.md)

