---
title: Arbeta med en partner för att arkivera data från tredje part
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Lär dig konfigurera en anpassad anslutare för att importera data från tredje part från datakällor som Salesforce Chatter, Yahoo Messenger eller Yammer.
ms.openlocfilehash: 6e93ff765129296f62b43c93937701169bbf4b03
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/24/2021
ms.locfileid: "52162452"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a>Arbeta med en partner för att arkivera data från tredje part

Du kan arbeta med en Microsoft-partner för att importera och arkivera data från en tredjepartsdatakälla till Microsoft 365. En partner kan tillhandahålla en anpassad koppling som är konfigurerad för att extrahera objekt från tredjepartsdatakällan (regelbundet) och sedan importera dessa objekt. Partnerkopplingen konverterar innehållet i ett objekt från datakällan till ett e-postmeddelandeformat och lagrar sedan objekten i postlådor. När data från tredje part har importerats kan du tillämpa Microsoft 365-efterlevnadsfunktioner som Bevarande av juridiska skäl, eDiscovery, In-Place arkivering, granskning och Microsoft 365 för bevarandeprinciper för dessa data.

>[!IMPORTANT]
>Lösningen [för kommunikationsefterlevnad](communication-compliance.md) i Microsoft 365 kan inte tillämpas på data från tredje part som importerats av partnerkopplingar som nämns i den här artikeln. 

Här är en översikt över processen och de steg som krävs för att arbeta med en Microsoft-partner för att importera data från tredje part.

[Steg 1: Hitta en datapartner från tredje part](#step-1-find-a-third-party-data-partner)

[Steg 2: Skapa och konfigurera en datapostlåda från tredje part](#step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365)

[Steg 3: Konfigurera användarpostlådor för data från tredje part](#step-3-configure-user-mailboxes-for-third-party-data)

[Steg 4: Ge din partner information](#step-4-provide-your-partner-with-information)

[Steg 5: Registrera tredjepartsdatakopplingen i Azure Active Directory](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>Så här fungerar dataimportprocessen från tredje part

I följande illustration och beskrivning förklaras hur dataimportprocessen från tredje part fungerar när du arbetar med en partner.
  
![Så här fungerar dataimportprocessen från tredje part](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. Kunden arbetar med sin partner för att konfigurera en koppling som extraherar objekt från tredje parts datakälla och sedan importera dessa objekt till Microsoft 365.
    
2. Partnerkopplingen ansluter till datakällor från tredje part via ett API från tredje part (schemalagt eller konfigurerat) och extraherar objekt från datakällan. Partnerkopplingen omvandlar innehållet i ett objekt till ett e-postmeddelandeformat. I avsnittet [Mer information](#more-information) finns en beskrivning av schemat för meddelandeformat. 
    
3. Partnerkopplingen ansluter till Azure-tjänsten i Microsoft 365 med hjälp Exchange webbtjänst (EWS) via en känd ändpunkt.
    
4. Objekt importeras till en viss användares postlåda eller till en datapostlåda från en "catch all" från tredje part. Huruvida ett objekt importeras till en viss användarpostlåda eller till tredjepartsdatapostlådan baseras på följande villkor:
    
   1. **Objekt som har ett användar-ID som motsvarar ett användarkonto:** Om partnerkopplingen kan mappa användar-ID:t för objektet i datakällan från tredje part till ett visst  användar-ID i Microsoft 365 kopieras objektet till mappen Rensningar i användarens Återställningsbara objekt-mapp. Användare kan inte komma åt objekt i mappen Rensningar. Du kan emellertid använda eDiscovery-verktyg för att söka efter objekt i mappen Rensningar.
    
   1. **Objekt som inte har ett användar-ID som motsvarar ett användarkonto:** Om partnerkopplingen inte kan mappa användar-ID:t för ett objekt till  ett visst användar-ID kopieras objektet till mappen Inkorg i datapostlådan från tredje part. Genom att importera objekt till Inkorgen kan du eller någon annan i organisationen logga in på postlådan från tredje part för att visa och hantera de här objekten och se om några justeringar behöver göras i konfigurationen av partnerkopplingen.
 
## <a name="step-1-find-a-third-party-data-partner"></a>Steg 1: Hitta en datapartner från tredje part

En viktig komponent i arkivering av data från tredje part i Microsoft 365 är att hitta och arbeta med en Microsoft-partner som samlar in data från en datakälla från tredje part och importerar dem till Microsoft 365. När data har importerats kan de arkiveras och bevaras tillsammans med organisationens andra Microsoft-data, till exempel e-post från Exchange och dokument från SharePoint och OneDrive för företag. En partner skapar en koppling som hämtar data från organisationens datakällor från tredje part (till exempel BlackBerry, Facebook, Google+, Reuters, Twitter och YouTube) och skickar dessa data till ett Microsoft 365 API som importerar objekt till Exchange-postlådor som e-postmeddelanden.
  
Följande avsnitt innehåller de Microsoft-partner (och datakällor från tredje part som de stöder) som deltar i programmet för arkivering av data från tredje part i Microsoft 365.

[17a-4 LLC](#17a-4-llc)
  
[ArchiveSocial](#archivesocial)
  
[Veritas](#veritas)
  
[OpenText](#opentext)
  
[Smarsh](#smarsh)

[Verba](#verba)
  
### <a name="17a-4-llc"></a>17a-4 LLC

[17a-4 LLC](https://www.17a-4.com) har stöd för följande datakällor från tredje part:
  
- BlackBerry
    
- Bloomberg Data Flöden
    
- Cisco Jabber
    
- FactSet
    
- HipChat
    
- InvestEdge
    
- LivePerson
    
- MessageLabs Data Flöden
    
- OpenText
    
- Oracle/ATG "klicka-och-ring"-hjälp i Live Help
    
- Pivot-IMTRADER
    
- Microsoft SharePoint
    
- MindAlign
    
- Sitrion One (Newsgator)
    
- Skype för företag (Lync/OCS)
    
- Skype för företag Online (Lync Online)
    
- SQL Databaser
    
- Squawker
    
- Thomson Reuters Eikon Messenger
  

  
### <a name="archivesocial"></a>ArchiveSocial

[ArchiveSocial ](https://www.archivesocial.com) har stöd för följande datakällor från tredje part: 
  
- Facebook
    
- Flickr
    
- Så här ser det ut
    
- LinkedIn
    
- Pinterest
    
- Twitter
    
- YouTube
    
- Vimeo
  
### <a name="veritas"></a>Veritas

[Veritas](https://www.globanet.com) stöder följande datakällor från tredje part: 
  
- AOL med pivotklient 
    
- BlackBerry Call Logs (v5, v10, v12)
    
- BlackBerry Messenger (v5, v10, v12)
    
- BlackBerry PIN (v5, v10, v12)
    
- BlackBerry SMS (v5, v10, v12)
    
- Bloomberg Chat
    
- Bloomberg Mail
    
- Ruta
    
- CipherCloud för Salesforce Chatter
    
- Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)

- Cisco Webex Teams

- Citrix Workspace &amp; ShareFile

- CrowdCompass

- Anpassade avgränsade textfiler
    
- Anpassade XML-filer
    
- Facebook (sidor)
    
- Factset
    
- FXConnect
    
- ICE-chatt/YellowSessionet
    
- Jive
    
- Macgregor XIP

- Microsoft Exchange Server
    
- Microsoft OneDrive för företag

- Microsoft Teams
       
- Microsoft Yammer
    
- Mobile Guard
    
- Pivot
    
- Salesforce Chatter

- Skype för företag – Online
    
- Skype för företag, versionerna 2007 R2–2016 (lokalt)
    
- Slack för företagsrutnät
    
- Symphony
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Reuters Dealings 3000 / FX Handels
    
- Twitter
    
- UBS Chat
    
- YouTube
  
### <a name="opentext"></a>OpenText

[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) har stöd för följande datakällor från tredje part: 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs Local Archive
    
- Axs PlaceHolder
    
- Axs signerade
    
- Bloomberg
    
- Thomson Reuters
  
### <a name="smarsh"></a>Smarsh

[Smarsh](https://www.smarsh.com) har stöd för följande datakällor från tredje part: 
  
- AIM
    
- American Sådd
    
- Apple Juice
    
- AOL med pivotklient
    
- Ares
    
- Röst rösten i Rösten
    
- Dela med dig
    
- Bit Störtflod
    
- BlackBerry Call Logs (v5, v10, v12)
    
- BlackBerry Messenger (v5, v10, v12)
    
- BlackBerry PIN (v5, v10, v12)
    
- BlackBerry SMS (v5, v10, v12)
    
- Bloomberg Mail
    
- CellTrust
    
- Importera chatt
    
- Loggning och policy för chatt i realtid
    
- Chattar
    
- Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)
    
- Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)
    
- Import av samarbete
    
- Loggning av samarbete i realtid
    
- Direkt Anslut
    
- Facebook
    
- FactSet
    
- FastTrack
    
- Så här ser det ut
    
- Google+
    
- GoToMyPC
    
- Hoppster
    
- HubConnex
    
- IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)
    
- IBM Connections Chat Cloud
    
- IBM Connections Social Cloud
    
- IBM SameTime Advanced 8.5.2 IFR1
    
- IBM SameTime Communicate 9.0
    
- IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)
    
- IBM SameTime Complete 9.0
    
- IBM SameTime Conference 9.0
    
- IBM SameTime Meeting 8.5.2 IFR1
    
- ICE/Yellow Entitet
    
- Import av snabbmeddelanden
    
- Loggning och policy för snabbmeddelanden i realtid
    
- Indii Messenger
    
- Instant Bloomberg
    
- IRC
    
- Jive
    
- Jive 6 realtidsloggning (v6, v7)
    
- Jive-import
    
- JXTA
    
- LinkedIn
    
- Microsoft Lync (2010, 2013)
    
- MFTP
    
- Microsoft Lync 2013 Voice
    
- Microsoft SharePoint (2010, 2013)
    
- Microsoft SharePoint Online
    
- Microsoft UC (Unified Communications)
    
- MindAlign
    
- Mobile Guard
    
- MSN
    
- Mitt utrymme
    
- NEONetwork
    
- Microsoft 365 Lync Dedicated
    
- Microsoft 365 Delade snabbmeddelanden
    
- Pinterest
    
- Pivot
    
- QQ
    
- Skype för företag 2015
    
- SoftEther
    
- Symphony
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Tor
    
- TTT
    
- Twitter
    
- WinMX
    
- Winny
    
- Yahoo
    
- Yammer
    
- YouTube
    

### <a name="verba"></a>Verba

[Verba](https://www.verba.com) stöder följande datakällor från tredje part: 
  
- Avaya Aura Video
    
- Avaya Aura Voice
    
- Avtec Radio
    
- Varg/Telex Radio
    
- BroadSoft Video
    
- BroadSoft Voice
    
- Centile Voice
    
- Cisco Jabber-snabbmeddelande
    
- Cisco UC Video
    
- Cisco UC Voice
    
- Cisco UCCX/UCCE Video
    
- Cisco UCCX/UCCE Voice
    
- ESChat Radio
    
- Geoman Contact Expert
    
- IP Trade Voice
    
- Luware LUCS Kontaktcenter
    
- Microsoft UC (Unified Communications)
    
- Mitel MiContact Center för Lync (prairieFyre)
    
- Oracle / Acme Packet Session Border Controller Video
    
- Oracle /Acme Packet Border Controller Voice
    
- Singtel Mobile Voice
    
- SIPREC-video
    
-  SIPREC-röst 
    
- Skype för företag/Lync-snabbmeddelanden
    
- Skype för företag/Lync Video
    
- Skype för företag/Lync Voice
    
- Speakerbus Voice
    
- Standard-SIP/H.323-video
    
- Standard-SIP/H.323-röst
    
- Truphone Voice
    
- Pair Radio
    
- Windows Skärm på stationär dator
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365"></a>Steg 2: Skapa och konfigurera en datapostlåda från tredje part i Microsoft 365

Här är stegen för att skapa och konfigurera en datapostlåda från tredje part för att importera data till Microsoft 365. Som tidigare förklarats importeras objekt till den här postlådan om partnerkopplingen inte kan mappa användar-ID:t för objektet till ett användarkonto.
  
 **Utför de här uppgifterna Microsoft 365 administrationscentret**
  
1. Skapa ett användarkonto och tilldela det en licens Exchange Online Abonnemang 2. se [Lägga till användare i Microsoft 365](../admin/add-users/add-users.md). En abonnemang 2-licens krävs för att placera postlådan i bevarande av juridiska skäl eller aktivera en arkivpostlåda som har en obegränsad lagringskvot.
    
2. Lägg till användarkontot för tredje parts datapostlåda i **administratörsrollen Exchange** i Microsoft 365. se [Tilldela administratörsroller i Microsoft 365](../admin/add-users/assign-admin-roles.md).
    
    > [!TIP]
    > Skriv ned autentiseringsuppgifterna för det här användarkontot. Du måste ge dem till din partner, enligt beskrivningen i steg 4. 
  
 **Utför de här uppgifterna Exchange administrationscentret**
  
1. Dölja tredje parts datapostlåda från adressboken och andra adresslistor i organisationen. se [Hantera användarpostlådor.](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes) Alternativt kan du köra följande PowerShell-kommando:
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. Tilldela **behörigheten FullAccess** till tredje parts datapostlåda så att administratörer eller efterlevnadsansvariga kan öppna tredjepartsdatapostlådan i Outlook klienten. se [Hantera behörigheter för mottagare.](https://go.microsoft.com/fwlink/p/?LinkId=692104)
    
3. Aktivera följande efterlevnadsrelaterade funktioner för tredjepartsdatapostlådan:
    
    - Aktivera arkivpostlådan. se [Aktivera arkivpostlådor](enable-archive-mailboxes.md) [och Aktivera obegränsad arkivering.](enable-unlimited-archiving.md) På så sätt kan du frigöra utrymme i den primära postlådan genom att konfigurera en arkivprincip som flyttar dataobjekt från tredje part till arkivpostlådan. Det ger dig obegränsad lagring för data från tredje part.
    
    - Placera tredjepartspostlådan i Bevarande av juridiska skäl. Du kan också Microsoft 365 bevarandeprincip i säkerhets- och efterlevnadscentret. Om postlådan är på plats behåller du dataobjekt från tredje part (ett obegränsat antal objekt eller under en angiven tidsperiod) och hindrar dem från att rensas från postlådan. Se något av följande avsnitt:
    
      - [Placera en postlåda i Bevarande av juridiska skäl](./create-a-litigation-hold.md)
    
      - [Mer information om kvarhållningsprinciper och kvarhållningsetiketter](retention.md)
    
    - Aktivera granskningsloggning för postlådor för ägare, ombud och administratörsåtkomst till tredjepartsdatapostlådan. se [Aktivera granskning av postlåda.](enable-mailbox-auditing.md) Det här gör att du kan granska all aktivitet som utförts av en användare som har åtkomst till tredje parts datapostlåda.

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>Steg 3: Konfigurera användarpostlådor för data från tredje part

Nästa steg är att konfigurera användarnas postlådor så att data från tredje part får stöd. Utför de här uppgifterna med Exchange administrationscenter eller med hjälp av Windows PowerShell cmdlets.
  
1. Aktivera arkivpostlådan för varje användare. se [Aktivera arkivpostlådor](enable-archive-mailboxes.md) [och Aktivera obegränsad arkivering.](enable-unlimited-archiving.md)
    
2. Placera användarpostlådor i bevarande av juridiska skäl eller Microsoft 365 bevarandeprincip. se något av följande avsnitt: 
    
    - [Placera en postlåda i Bevarande av juridiska skäl](./create-a-litigation-hold.md)
    
    - [Mer information om kvarhållningsprinciper och kvarhållningsetiketter](retention.md)
    
    Som tidigare nämnts kan du ange en varaktighet för hur länge objekt från den tredje partens datakälla ska behållas när du placerar postlådor på en plats, eller så kan du välja att behålla objekt på obestämd tid.

## <a name="step-4-provide-your-partner-with-information"></a>Steg 4: Ge din partner information

Det sista steget är att ge din partner följande information så att de kan konfigurera anslutningen för att ansluta till din organisation för att importera data till användarnas postlådor och till tredjepartsdatapostlådan. 
  
- Slutpunkten som används för att ansluta till Azure-tjänsten i Microsoft 365:

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- Inloggningsuppgifterna (Microsoft 365 användar-ID och lösenord) för den datapostlåda från tredje part som du skapade i steg 2. Dessa autentiseringsuppgifter krävs för att partnerkopplingen ska kunna komma åt och importera objekt till användarpostlådor och till tredjepartsdatapostlådan.
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>Steg 5: Registrera tredjepartsdatakopplingen i Azure Active Directory

Från och med den 30 september 2018 börjar Azure-tjänsten i Microsoft 365 använda modern autentisering i Exchange Online för att autentisera dataanslutningar från tredje part som försöker ansluta till organisationen för att importera data. Orsaken till den här ändringen är att modern autentisering ger högre säkerhet än den aktuella metoden, som baseras på en lista över tillåtna för kopplingar från tredje part som använder den tidigare beskrivna slutpunkten för att ansluta till Azure-tjänsten.

Om du vill aktivera en datakoppling från tredje part för att ansluta till Microsoft 365 med den nya moderna autentiseringsmetoden måste en administratör i organisationen godkänna att anslutaren registreras som ett betrott tjänstprogram i Azure Active Directory. Detta görs genom att godkänna en begäran om tillstånd för att tillåta anslutningen att komma åt din organisations data i Azure Active Directory. När du har accepterat begäran läggs datakopplingen från tredje part till som ett företagsprogram i Azure Active Directory tjänst och representeras som en tjänsts huvudnamn. Mer information om medgivandeprocessen finns i [Innehavaradministratörens medgivande.](/skype-sdk/trusted-application-api/docs/tenantadminconsent)

Här är stegen för att komma åt och acceptera begäran om att registrera anslutningen:

1. Gå till [den här sidan](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) och logga in med en global administratörs autentiseringsuppgifter.

   Följande dialogruta visas. Du kan expandera carets för att granska de behörigheter som ska tilldelas till kopplingen.

   ![Dialogrutan för behörighetsbegäran visas](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. Klicka **på Acceptera.**

När du har accepterat begäran visas [Azure Portal.](https://portal.azure.com) Om du vill visa en lista över program för organisationen klickar du på **Azure Active Directory**  >  **Enterprise-program**. Kopplingen Microsoft 365 från tredje part visas i bladet **Företagsprogram.**

> [!IMPORTANT]
> Efter den 30 september 2018 importeras data från tredje part inte längre till postlådor i din organisation om du inte registrerar en datakoppling från tredje part i Azure Active Directory. Observera att befintliga datakopplingar från tredje part (de som skapades före den 30 september 2018) också måste registreras i Azure Active Directory enligt proceduren i steg 5.

### <a name="revoking-consent-for-a-third-party-data-connector"></a>Återkalla medgivande för en datakoppling från tredje part

När din organisation har samtyckt till behörighetsbegäran att registrera en dataanslutning från tredje Azure Active Directory kan organisationen återkalla medgivandet när som helst. Om du återkallar medgivandet för en koppling kommer data från tredjepartsdatakällan dock inte längre att importeras till Microsoft 365.

Om du vill återkalla medgivandet för en datakoppling från tredje part kan du ta bort programmet (genom att ta bort motsvarande tjänsts huvudnamn) från Azure Active Directory med hjälp av bladet **för Enterprise-program** i Azure-portalen eller med hjälp av [Remove-MsolServicePrincipal](/powershell/module/msonline/remove-msolserviceprincipal) i Microsoft 365 PowerShell. Du kan också använda [cmdleten Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal) i Azure Active Directory PowerShell.
  
## <a name="more-information"></a>Mer information

- Som tidigare förklarats importeras objekt från datakällor från tredje part till Exchange som e-postmeddelanden. Partnerkopplingen importerar objektet med ett schema som krävs av Microsoft 365 API. I följande tabell beskrivs meddelandeegenskaperna för ett objekt från en datakälla från tredje part när det importerats till en e-Exchange postlåda som ett e-postmeddelande. Tabellen anger också om meddelandeegenskapen är obligatorisk. Obligatoriska egenskaper måste fyllas i. Om ett objekt saknar en obligatorisk egenskap importeras den inte till den Microsoft 365. Importen returnerar ett felmeddelande som förklarar varför ett objekt inte importerades och vilken egenskap som saknas.<br/><br/>
    
    |**Meddelandeegenskap**|**Obligatoriskt?**|**Beskrivning**|**Exempelvärde**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |Ja  <br/> |Användaren som ursprungligen skapade eller skickade objektet i datakällan från tredje part. Partnerkopplingen försöker mappa användar-ID:t från källobjektet (till exempel ett Twitter-handtag) till ett användarkonto för alla deltagare (användare i fälten FRÅN och TILL). En kopia av meddelandet importeras till varje deltagares postlåda. Om ingen av deltagarna i objektet kan mappas till ett användarkonto importeras objektet till tredje parts arkiveringspostlåda i Microsoft 365.  <br/> <br/> Deltagaren som identifieras som avsändare av objektet måste ha en aktiv postlåda i organisationen som objektet importeras till. Om avsändaren inte har en aktiv postlåda returneras följande fel:<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |Ja  <br/> |Användaren som har fått ett objekt, om tillämpligt för ett objekt i datakällan.  <br/> | `bob@contoso.com` <br/> |
    |**SUBJECT** <br/> |Nej  <br/> |Ämnet från källobjektet.  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**DATE** <br/> |Ja  <br/> |Det datum då objektet ursprungligen skapades eller publicerades i kundens datakälla. Till exempel datumet då ett Twitter-meddelande twittades.  <br/> | `01 NOV 2015` <br/> |
    |**BODY** <br/> |Nej  <br/> |Innehållet i meddelandet eller inlägget. För vissa datakällor kan innehållet i den här egenskapen vara detsamma som innehållet för egenskapen **SUBJECT.** Under importen försöker partnerkopplingen bevara fullständig återgivning från innehållskällan som möjligt. Om möjliga filer, bilder eller annat innehåll från källobjektets brödtext ingår i den här egenskapen. Annars inkluderas innehåll från källobjektet i egenskapen **ATTACHMENT.** Innehållet i den här egenskapen beror på partneranslutningen och på källplattformens funktion.  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**BIFOGAD FIL** <br/> |Nej  <br/> |Om ett objekt i datakällan (t.ex. en tweet på Twitter eller en snabbmeddelandekonversation) har en bifogad fil eller bilder, försöker partnern ansluta först att inkludera bifogade filer i **egenskapen** BODY. Om det inte är möjligt läggs det till i egenskapen ** ATTACHMENT ** . Andra exempel på bifogade filer är Gilla-meddelanden på Facebook, metadata från innehållskällan och svar på ett meddelande eller inlägg.  <br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |Ja  <br/> | Den här egenskapen har flera värden, som skapas och fylls i av partnerkopplingen. Den här egenskapens format är  `IPM.NOTE.Source.Event` . (Den här egenskapen måste börja med  `IPM.NOTE` . Det här formatet liknar det som gäller för  `IPM.NOTE.X` meddelandeklassen.) Den här egenskapen innehåller följande information:  <br/><br/>`Source`: Anger tredje parts datakälla. till exempel Twitter, Facebook eller BlackBerry.  <br/> <br/>  `Event`: Anger vilken typ av aktivitet som utfördes i datakällan från tredje part som producera objekten. Till exempel en tweet på Twitter eller ett inlägg på Facebook. Händelser är specifika för datakällan.  <br/> <br/>  Ett syfte med den här egenskapen är att filtrera specifika objekt baserat på den datakälla där ett objekt har sitt ursprung eller baserat på typen av händelse. I en eDiscovery-sökning kan du till exempel skapa en sökfråga för att hitta alla tweets som publicerats av en viss användare.  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- När objekt har importerats till postlådor i Microsoft 365 returneras en unik identifierare till uppringaren som en del av HTTP-svaret. Den här identifieraren, som kallas, kan användas för efterföljande felsökningssyften av partners för att spåra objekt  `x-IngestionCorrelationID` från slutet till slut. Vi rekommenderar att partner samlar in den här informationen och loggar in den i enlighet med detta. Här är ett exempel på ett HTTP-svar som visar den här identifieraren:

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- Du kan använda verktyget Innehållssökning i säkerhets- och efterlevnadscentret för att söka efter objekt som har importerats till postlådor från en datakälla från tredje part. Om du vill söka specifikt efter dessa importerade objekt kan du använda följande par med meddelandeegenskap i nyckelordsrutan för en innehållssökning.
    
  - **`kind:externaldata`**: Använd det här egenskapsvärdet för att söka igenom alla datatyper från tredje part. Om du till exempel vill söka efter objekt som importerats från en datakälla från tredje part och som innehåller ordet "contoso" i egenskapen Ämne för det importerade objektet använder du nyckelordsfrågan  `kind:externaldata AND subject:contoso` .
    
  - **`itemclass:ipm.externaldata.<third-party data type>`**: Använd det här egenskapsvärdet för att bara söka efter data från tredje part. Om du till exempel bara vill söka efter Facebook-data som innehåller ordet "contoso" i egenskapen Ämne använder du nyckelordsfrågan  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` . 

  En fullständig lista med värden som ska användas för datatyper från tredje part för egenskapen finns i Använda innehållssökning för att söka efter data från tredje part som har importerats `itemclass` [till Microsoft 365.](use-content-search-to-search-third-party-data-that-was-imported.md)
    
   Mer information om hur du använder innehållssökning och skapar nyckelordssökningsfrågor finns i:
    
  - [Innehållssökning](content-search.md)
    
  - [Nyckelordsfrågor och sökvillkor för innehållssökning](keyword-queries-and-search-conditions.md)