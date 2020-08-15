---
title: Nätverks begär anden i Office för Mac
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
description: I den här artikeln beskrivs vilka slut punkter och URL-adresser för Office för Mac som försöker nås och tjänsterna tillhandahålls.
ms.openlocfilehash: b777b4ea7e03495cb6389be8fe05e96a26fd9664
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694635"
---
# <a name="network-requests-in-office-for-mac"></a>Nätverks begär anden i Office för Mac

Office för Mac-program ger en inbyggd program upplevelse på macOS-plattformen. Varje app är utformat för att fungera i flera olika scenarier, inklusive lägen när ingen nätverks åtkomst är tillgänglig. När en dator är ansluten till ett nätverk ansluter programmen automatiskt till en serie webbaserade tjänster för att tillhandahålla förbättrade funktioner. Här beskrivs vilka slut punkter och URL-adresser som programmen försöker nå, och tjänsterna tillhandahålls. Den här informationen är användbar när du felsöker problem med nätverks konfiguration och anger principer för fjärrinstallationsservrar. Informationen i den här artikeln är avsedd att komplettera [Office 365 URL-och adress områden](urls-and-ip-address-ranges.md), som inkluderar slut punkter för datorer med Microsoft Windows. Om inget annat anges gäller informationen i den här artikeln också för Office 2019 för Mac och Office 2016 för Mac, som är tillgänglig som Engångs köp från en butik eller via ett volym licens avtal. 

  
De flesta av den här artikeln är tabeller med URL: er, typ och beskrivning av tjänst eller funktion som tillhandahålls av slut punkten. Varje Office-program kan skilja sig från deras tjänst och slut punkts användning. Följande appar är definierade i tabellerna nedan:
  
- W: Word
- P: PowerPoint
- X: Excel
- O: Outlook
- N: OneNote
   
URL-typen definieras på följande sätt:
  
- S:T: statisk – URL-adressen är hårdkodad i klient programmet.
    
- SS: halv statisk – URL-adressen kodas som en del av en webb sida eller omdirigerare.
    
- CS: config service-URL-adressen returneras som en del av Office Configuration service.

    
## <a name="office-for-mac-default-configuration"></a>Standard konfiguration för Office för Mac

 **Installation och uppdateringar**
  
Följande nätverks slut punkter används för att ladda ned installations programmet för Office för Mac från Microsofts innehålls leverans nätverk (CDN).
  
|**:**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |A  <br/> |Microsoft 365-installationsmappen vidarekopplar till de senaste installations paketen.  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |BLAD  <br/> |Plats för installations paket i nätverket med innehålls leverans.  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |BLAD  <br/> |Plats för installations paket i nätverket med innehålls leverans.  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |A  <br/> |Hanterings kontroll slut punkt för Microsoft AutoUpdate  <br/> |
   
 **Starta första app**
  
Följande nätverks slut punkter kontaktas vid första starten av en Office-app. Dessa slut punkter tillhandahåller förbättrade Office-funktioner för användare och URL-adressen kontaktas oavsett licens typ (inklusive volym licens installationer).
  
|**:**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |A  <br/> |"Flygning"-konfigurationen – gör det möjligt för funktioner att lyser och pröva.  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |A  <br/> |Test av nätverks konfiguration för "flygning"  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |A  <br/> |Test av nätverks konfiguration för "flygning"  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |A  <br/> |Office Configuration service – huvud lista över tjänste slut punkter.  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |A  <br/> |Office-regler för telemetri laddas ner-informerar klienten om vilka data och händelser som ska överföras till telemetri-tjänsten.  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |Saknas  <br/> |Guide  <br/> |OneNote Telemetriprocessor  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |A  <br/> |Uppladdnings rapportering för Office-telemetri-"Heartbeart" och fel händelser som inträffar på klienten laddas upp till telemetri-tjänsten.  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |Guide  <br/> |Office-mall – innehåller användare med mallar för onlinedokument.  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |Guide  <br/> |Office-mallar Ladda ned – lagra PNG-mallfiler.  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |Guide  <br/> |Lagra konfiguration för Office-program.  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |Guide  <br/> |Office Document Integration Services-katalog (lista över tjänster och slut punkter) och identifiering av start sfär.  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |Guide  <br/> |Resurser för start sfär identifiering v2 (15,40 och senare)  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |A  <br/> |Microsoft AutoUpdate-manifest-kontrollerar om det finns tillgängliga uppdateringar  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |BLAD  <br/> |Microsoft Ajax JavaScript-bibliotek  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |Y  <br/> |BLAD  <br/> |Wikipedia-app för Office-konfiguration och-resurser.  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |Kryss  <br/> |BLAD  <br/> |Bing Map-app för Office-konfiguration och-resurser.  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |Kryss  <br/> |BLAD  <br/> |Programmet Graph för Office-konfiguration och-resurser.  <br/> |
|```https://www.onenote.com/```  <br/> |Saknas  <br/> |A  <br/> |Nyheter i OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |Saknas  <br/> |A  <br/> |Nytt innehåll i OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |Saknas  <br/> |BLAD  <br/> |Nyheter för OneNote.  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |A  <br/> |Support tjänst via app.  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |O  <br/> |A  <br/> |Identifierings tjänst för e-postkonto.  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |A  <br/> |Outlook-upptäckning automatiskt  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |A  <br/> |Outlook-slutpunkt för Microsoft 365-tjänst.  <br/> |
|```https://r1.res.office365.com/```  <br/> |O  <br/> |A  <br/> |Ikoner för Outlook-tillägg.  <br/> |
   
> [!NOTE]
> Office Configuration service är en tjänst för automatisk identifiering för alla Microsoft Office-klienter, inte bara för Mac. Slut punkterna som returneras i svaret är halv statiska för den ändringen är väldigt sällan, men det är ändå möjligt. 
  
 **Logga in**
  
Följande nätverks slut punkter kontaktas när du loggar in på Cloud-baserad lagring. Beroende på vilken kontotyp det är kan olika tjänster kontaktas. Till exempel:
  
- **MSA: Microsoft-konto** – används vanligt vis för konsumenter och detalj handeln 
    
- **OrgID: organisations konto** – används vanligt vis för kommersiella scenarier 
    
|**:**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |A  <br/> |Windows Authorization service  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |A  <br/> |Microsoft 365 inloggnings tjänst (OrgID)  <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |A  <br/> |Inloggnings tjänst för Microsoft-konto (MSA)  <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |Guide  <br/> |Hjälp för inloggnings tjänsten för Microsoft-konto (MSA)  <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |BLAD  <br/> |Microsoft 365 inloggnings märkning (OrgID)  <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |Guide  <br/> |Dokument och platser lagrings plats  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |Guide  <br/> |Den senast använda dokument tjänsten  <br/> |
   
> [!NOTE]
> För prenumerations-och detalj handels licenser loggar du in båda med produkten och aktiverar åtkomst till moln resurser som OneDrive. För volym licens installationer uppmanas användare fortfarande att logga in (som standard), men det är bara nödvändigt för åtkomst till moln resurser eftersom produkten redan är aktive rad. 
  
 **Produkt aktivering**
  
Följande nätverks slut punkter gäller för Microsoft 365-prenumeration och aktivering av åter försäljare. Detta gäller särskilt för volym licens installationer.
  
|**:**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |Guide  <br/> |Office-Klientlicensieringstjänsten  <br/> |
   
 **Nyheter**
  
Följande nätverks slut punkter gäller endast för Microsoft 365-abonnemanget.
  
|**:**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |BLAD  <br/> |Nyheter.  <br/> |
   
 **Researcher**
  
Följande nätverks slut punkter gäller endast för Microsoft 365-abonnemanget.
  
|**:**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |Y  <br/> |Guide  <br/> |Webb tjänst för forskare  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |Y  <br/> |Guide  <br/> |Statiskt innehåll i forskare  <br/> |
|```https://www.bing.com/```  <br/> |Y  <br/> |Guide  <br/> |Innehålls leverantör för forskare  <br/> |
   
 **Smart sökning**
  
Följande nätverks slut punkter gäller för både Microsoft 365-prenumerationer och aktiveringar av återförsäljar-och volym licenser.
  
|**:**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |Guide  <br/> |Webb tjänsten insikter  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |Guide  <br/> |JQuery-bibliotek  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |Guide  <br/> |Stöd JavaScript-bibliotek  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |Guide  <br/> |Innehålls leverantör för insikter  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |Guide  <br/> |Innehålls leverantör för insikter  <br/> |
   
 **PowerPoint Designer**
  
Följande nätverks slut punkter gäller endast för Microsoft 365-abonnemanget.
  
|**:**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |E  <br/> |Guide  <br/> |PowerPoint designer-webbtjänst  <br/> |
   
 **PowerPoint Snabbstart**
  
Följande nätverks slut punkter gäller endast för Microsoft 365-abonnemanget.
  
|**:**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |E  <br/> |Guide  <br/> |Webb tjänst för PowerPoint-snabb start  <br/> |
   
 **Skicka ett leende/en bister min**
  
Följande nätverks slut punkter gäller för både Microsoft 365-prenumerationer och aktiveringar av återförsäljar-och volym licenser.
  
|**:**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |Guide  <br/> |Skicka en leende tjänst  <br/> |
   
 **Kontakta support**
  
Följande nätverks slut punkter gäller för både Microsoft 365-prenumerationer och aktiveringar av återförsäljar-och volym licenser.
  
|**:**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |O  <br/> |Guide  <br/> |Kontakta supporten  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |Guide  <br/> |Support tjänst via app  <br/> |
   
 **Spara som PDF**
  
Följande nätverks slut punkter gäller för både Microsoft 365-prenumerationer och aktiveringar av återförsäljar-och volym licenser.
  
|**:**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |Y  <br/> |Guide  <br/> |Word-dokumentbibliotek (PDF)  <br/> |
   
 **Office-program (aka tillägg)**
  
Följande nätverks slut punkter gäller för både Microsoft 365-prenumeration och Retail/Volume Licensing activationes när Office app-tillägg är betrodda.
  
|**:**|**Appar**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |Guide  <br/> |Office App Store-konfiguration  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |Y  <br/> |BLAD  <br/> |Wikipedia-app-resurser  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |Kryss  <br/> |BLAD  <br/> |Bing kartprogram-resurser  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |Kryss  <br/> |BLAD  <br/> |Kontakter i Graph  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |BLAD  <br/> |Office-omdirigeringstyp  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |BLAD  <br/> |Office JavaScript-bibliotek  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |WX  <br/> |BLAD  <br/> |Telemetri och rapporterings tjänst för Office-program  <br/> |
|```https://ajax.microsoft.com/```  <br/> |Y  <br/> |BLAD  <br/> |Microsoft Ajax JavaScript-bibliotek  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |Kryss  <br/> |BLAD  <br/> |Microsoft Ajax JavaScript-bibliotek  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |BLAD  <br/> |Office JavaScript-bibliotek  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |BLAD  <br/> |Support resurser  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |BLAD  <br/> |Support resurser  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |BLAD  <br/> |Support resurser  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |BLAD  <br/> |JavaScript-bibliotek  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |BLAD  <br/> |Fel rapportering  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |BLAD  <br/> |Teckensnitts resurser  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |BLAD  <br/> |Telemetriprocessor  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |BLAD  <br/> |Telemetridata  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |BLAD  <br/> |Microsoft Store Asset Library  <br/> |
|```https://*.wikipedia.org/```  <br/> |Y  <br/> |BLAD  <br/> |Sidor med Wikipedia-Sidan  <br/> |
|```https://upload.wikimedia.org/```  <br/> |Y  <br/> |BLAD  <br/> |Wikipedia-medie resurser  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |Y  <br/> |BLAD  <br/> |Wikipedia sand Box ram  <br/> |
|```https://*.virtualearth.net/```  <br/> |Kryss  <br/> |BLAD  <br/> |Map-mallar  <br/> |
   
 **Säkra länkar**
  
Följande nätverks slut punkt gäller endast för alla Office-program för Microsoft 365-prenumerationen.
  
|**:**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |Guide  <br/> |Microsoft-tjänsten för säker länk  <br/> |
   
 **Krasch rapportering**
  
Följande nätverks slut punkt gäller för alla Office-program för både Microsoft 365-prenumeration och aktivering av volym licenser. När en process oväntat kraschar skapas en rapport till Watson-tjänsten.
  
|**:**|**Typ**|**Beskrivning**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |A  <br/> |Microsoft fel rapporterings tjänst  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |A  <br/> |Office samarbetar  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>Alternativ för att minska nätverks förfrågningar och trafik

Standard konfigurationen för Office för Mac ger den bästa användar upplevelsen, både i funktionalitet och hålla datorn uppdaterad. I vissa fall kanske du vill förhindra att program kontaktar nätverks slut punkter. I det här avsnittet beskrivs hur du gör det.
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>Inaktivera moln inloggning och Office-tillägg
  
Volym licens kunder kan ha strikta principer för att spara dokument på Cloud-baserad lagring. Följande inställningar per program kan anges för att inaktivera MSA/OrgID-inloggning och åtkomst till Office-tillägg.
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

Om användare försöker få till gång till inloggnings funktionen visas ett fel meddelande om att nätverks anslutningen inte är tillgänglig. Eftersom den här inställningen även blockerar produkt aktivering online bör den endast användas för volym licens installationer. Med den här inställningen hindras Office-program från att få åtkomst till följande slut punkter:
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- Alla slut punkter som listas i avsnittet "logga in" ovan.
    
- Alla slut punkter som listas i avsnittet "smart sökning" ovan.
    
- Alla slut punkter som listas i "produkt aktivering" ovan.
    
- Alla slut punkter som listas i "Office-program (aka tillägg)" ovan.
    
För att återupprätta alla funktioner för användaren, ange antingen inställningen till "2" eller ta bort den.
  
> [!NOTE]
> För den här inställningen krävs Office för Mac version 15,25 [160726] eller senare. 
  
### <a name="telemetry"></a>Telemetri 
  
Office för Mac skickar telemetridata tillbaka till Microsoft med jämna mellanrum. Data laddas upp till slut punkten ' Nexus '. Med hjälp av telemetridata kan teknik gruppen bedöma hälsa och eventuella oväntade beteenden hos varje Office-program. Det finns två kategorier av telemetri:
  
- **Pulsslag** innehåller information om version och licens. Dessa data skickas omedelbart när programmet startas. 
    
- **Användning** innehåller information om hur appar används och icke-allvarliga fel. Dessa data skickas var 60 minut. 
    
Microsoft tar integriteten på allvar. Du kan läsa mer om Microsofts policy för data insamling på [https://privacy.microsoft.com](https://privacy.microsoft.com) . För att förhindra program från att skicka ' användning '-telemetri kan **SendAllTelemetryEnabled** -preferensen justeras. Inställningen är per program och kan ställas in via konfigurations profilerna i macOS, eller manuellt från Terminal: 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

Heartbeat-telemetri skickas alltid och kan inte inaktive ras.
  
### <a name="crash-reporting"></a>Krasch rapportering
  
När ett oåterkalleligt program fel inträffar kommer programmet att avslutas oväntat och överföra en krasch rapport till "Watson"-tjänsten. Crash-rapporten består av en samtals stack, som är en lista med steg som programmet bearbetade fram till kraschen. Dessa steg hjälper teknik gruppen att identifiera den exakta funktion som misslyckades och varför.
  
I vissa fall kan innehållet i ett dokument orsaka att programmet kraschar. Om programmet identifierar dokumentet som orsak kommer det att fråga användaren om det inte går att skicka dokumentet tillsammans med samtals stacken. Användare kan göra ett välgrundat val för den här frågan. IT-administratörer kan ha strikta krav på överföring av dokument och göra det möjligt för användaren att aldrig skicka dokument. Följande preferenser kan ställas in så att det inte går att skicka dokument till användaren:
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> Om **SendAllTelemetryEnabled** är inställt på **false**är alla krasch rapporter för processen inaktiverade. För att aktivera krasch rapportering utan att skicka användnings telemetri kan följande inställning ställas in: ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>Uppdateringar
  
Microsoft släpper Office för Mac-uppdateringar med jämna mellanrum (vanligt vis en gång i månaden). Vi uppmuntrar användare och IT-administratörer att hålla datorer uppdaterade så att de senaste säkerhets korrigeringarna är installerade. Om IT-administratörer vill kontrol lera och hantera dator uppdateringar kan följande preferenser ställas in så att automatisk uppdatering inte identifieras och erbjuds produkt uppdateringar automatiskt:
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>Blockera förfrågningar med en brand vägg/proxy
  
Om din organisation blockerar förfrågningar till URL-adresser via en brand vägg eller proxyserver, måste du konfigurera URL-adresserna i det här dokumentet som antingen tillåtna eller blockerade med ett 40X-svar (t. 403 eller 404). Ett 40X-svar gör att Office-programmen kan acceptera oförmåga att få åtkomst till resursen och ger en snabbare användar upplevelse än att helt enkelt släppa anslutningen, vilket gör att klienten kan försöka igen.
  
Om din proxyserver kräver en autentiseringsbegäran returneras ett 407-svar till klienten. För att det ska fungera så bra som möjligt bör du kontrol lera att du använder Office för Mac version 15,27 eller senare, eftersom de innehåller specifika korrigeringar för att arbeta med NTLM-och Kerberos-servrar.
  
  
## <a name="see-also"></a>Se även

[URL-adresser och IP-adressintervall för Office 365](urls-and-ip-address-ranges.md)

