---
title: Använda innehållssökning för att söka efter importerade data från tredje part
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: Använd verktyget eDiscovery för innehållssökning för att söka efter objekt som importerats till postlådor i Microsoft 365 från en datakälla från tredje part genom att skapa frågor.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 24ca63cf78b85f7b8b5181d5babd16058b641128
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "52161593"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a>Använda innehållssökning för att söka efter data från tredje part som importerats med en anpassad partnerkoppling

Du kan använda [verktyget eDiscovery](content-search.md) för innehållssökning i Säkerhets- och efterlevnadscenter för & för att söka efter objekt som importerats till postlådor i Microsoft 365 från en datakälla från tredje part. Du kan skapa en fråga för att söka i alla importerade dataobjekt från tredje part eller så kan du skapa en fråga för att söka efter specifika dataobjekt från tredje part. Du kan också skapa en frågebaserad bevarandeprincip eller ett frågebaserat eDiscovery-bevarande för att bevara data från tredje part.
  
Mer information om hur du arbetar med en partner för att importera data från tredje part och en lista över de datatyper från tredje part som du kan importera till Microsoft 365 finns i Arbeta med en partner för att arkivera data från tredje part [i Office 365.](work-with-partner-to-archive-third-party-data.md)

> [!IMPORTANT]
> Vägledningen i den här artikeln gäller endast data från tredje part som importerats av en anpassad partnerkoppling. Den här artikeln gäller inte för data från tredje part som importeras med hjälp av datakopplingar från tredje part i [Microsofts efterlevnadscenter.](archiving-third-party-data.md#third-party-data-connectors)
  
## <a name="creating-a-query-to-search-all-third-party-data"></a>Skapa en fråga för att söka i alla data från tredje part

Om du vill söka efter (eller välja att behålla) alla typer av data från tredje part som du har importerat till Office 365 kan du använda värdeparet för meddelanden i nyckelordsrutan för en innehållssökning eller när du skapar ett frågebaserat `kind:externaldata` håll. Om du till exempel vill söka efter objekt som importerats från en datakälla från tredje part och innehåller ordet "contoso" i egenskapen Ämne för det importerade objektet använder du följande fråga: 
  
```powershell
kind:externaldata AND subject:contoso
```

Exemplet med föregående nyckelordsfråga innehåller ämnesegenskapen. En lista med andra egenskaper för dataobjekt från tredje part som kan ingå i en nyckelordsfråga finns i avsnittet "Mer information" i Arbeta med en partner för att arkivera data från tredje part [i Office 365](work-with-partner-to-archive-third-party-data.md#more-information).
  
När du skapar frågor för att söka och lagra data från tredje part kan du också använda villkor för att begränsa sökresultatet. Mer information om hur du skapar innehållssökningsfrågor finns [i Nyckelordsfrågor och sökvillkor för innehållssökning.](keyword-queries-and-search-conditions.md)
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a>Skapa en fråga för att söka efter specifika typer av data från tredje part

I stället för att söka efter alla typer av data från tredje part kan du skapa frågor som bara söker efter en viss typ av data från tredje part med hjälp av följande meddelandeegenskap: *värdepar* i nyckelordsrutan för en innehållssökning:
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

Om du till exempel vill söka efter Facebook-data som innehåller ordet "contoso" i egenskapen Ämne använder du följande fråga:
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

I följande tabell visas de datatyper från tredje part som du kan söka i, och värdet som ska användas för meddelandeegenskapen för att specifikt söka efter den typen av  `itemclass:` data från tredje part. Frågesyntaxen är inte fallkänslig. 
  
|**Datatyp från tredje part**|**Värde för  `itemclass:` egenskap**|
|:-----|:-----|
|AIM  <br/> | `ipm.externaldata.AIM*` <br/> |
|American Sådd  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|AOL med pivotklient  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|Apple Juice  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|Ares  <br/> | `ipm.externaldata.Ares*` <br/> |
|Axs Encrypted  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|Axs Exchange  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|Axs Local Archive  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|Platshållare för Axs  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|Axs signerade  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|Voice  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|Bearshare  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|Bit Ent  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|Blackberry  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|BlackBerry-samtalsloggar  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|BlackBerry Messenger  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|BlackBerry PIN  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|BlackBerry-SMS  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|Bloomberg  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|Bloomberg-meddelande  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|Bloomberg Messaging  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|Ruta  <br/> | `ipm.externaldata.Box*` <br/> |
|Cisco IM &amp; Presence Server  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|Cisco Jabber  <br/> | `ipm.externaldata.Jabber*` <br/> |
|CipherCloud för Salesforce Chatter  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|Direkt Anslut  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|Facebook  <br/> | `ipm.externaldata.Facebook*` <br/> |
|FastTrack  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|FXConnect  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|Flickr  <br/> | `ipm.externaldata.Flickr*` <br/> |
|Så här ser det ut  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|Google+  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|Google Talk  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|GoToMyPC  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|HipChat  <br/> | `ipm.externaldata.HipChat*` <br/> |
|Hoppster  <br/> | `ipm.externaldata.Hopster*` <br/> |
|HubConnex  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|IBM Connections  <br/> | `ipm.externaldata.Connections*` <br/> |
|IBM SameTime  <br/> | `ipm.externaldata.Sametime*` <br/> |
|ICE-chatt  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|Indii Messenger  <br/> | `ipm.externaldata.Indii*` <br/> |
|Så här ser det ut  <br/> | `ipm.externaldata.Instagram*` <br/> |
|Instant Bloomberg  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|InvestEdge  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|IRC  <br/> | `ipm.externaldata.IRC*` <br/> |
|Jive  <br/> | `ipm.externaldata.Jive*` <br/> |
|JiveApiRetention  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|JXTA  <br/> | `ipm.externaldata.JXTA*` <br/> |
|LinkedIn  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|MFTP  <br/> | `ipm.externaldata.MFTP*` <br/> |
|Microsoft UC  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|Mind Align  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|Mobile Guard  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|MSN  <br/> | `ipm.externaldata.MSN*` <br/> |
|MySpace  <br/> | `ipm.externaldata.MySpace*` <br/> |
|NEONetwork  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|OpenNap  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|Pinterest  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|Pivot  <br/> | `ipm.externaldata.Pivot*` <br/> |
|QQ  <br/> | `ipm.externaldata.QQ*` <br/> |
|Microsoft SharePoint  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|Salesforce Chatter  <br/> | `ipm.externaldata.Chatter*` <br/> |
|Skype för företag  <br/> | `ipm.externaldata.Skype*` <br/> |
|Slack för företagsrutnät  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|SoftEther  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|Squawker  <br/> | `ipm.externaldata.Squawker*` <br/> |
|Symphony  <br/> | `ipm.externaldata.Symphony*` <br/> |
|Thomson Reuters  <br/> | `ipm.externaldata.Reuters*` <br/> |
| Thomson Reuters Eikon Messenger  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|Tor  <br/> | `ipm.externaldata.Tor*` <br/> |
|TTT  <br/> | `ipm.externaldata.TTT*` <br/> |
|Twitter  <br/> | `ipm.externaldata.Twitter*` <br/> |
|UBS Chat  <br/> | `ipm.externaldata.UBS*` <br/> |
|Vimeo  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|WinMX  <br/> | `ipm.externaldata.WinMX*` <br/> |
|Winny  <br/> | `ipm.externaldata.Winny*` <br/> |
|Yahoo!  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|Yammer  <br/> | `ipm.externaldata.Yammer*` <br/> |
|Yellow Entitet  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|YouTube  <br/> | `ipm.externaldata.YouTube*` <br/> |
