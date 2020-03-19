---
title: Avancerade alternativ för skräppostfiltrering
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/09/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
description: Avancerade alternativ för skräppostfiltrering ger administratörer möjlighet att granska olika innehållsattribut för ett meddelande. Förekomsten av dessa attribut i ett meddelande antingen ökar spam poäng av meddelandet (vilket ökar risken för att det ska identifieras som spam) eller markerar meddelandet som spam. ASF-alternativen är inriktade på specifika meddelandeegenskaper, till exempel HTML-taggar och URL-omdirigering, som ofta finns i skräppostmeddelanden.
ms.openlocfilehash: 07f2b32dac6ba4a04fbccac5f015be399f62e254
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812252"
---
# <a name="advanced-spam-filtering-options"></a>Avancerade alternativ för skräppostfiltrering

> [!NOTE]
> Inställningarna för avancerat skräppostfilter i anti-spam-policyn är för närvarande inaktuella. Våra rekommenderade inställningar för dessa är att stänga **av**dem. De funktioner som var tillgängliga i filtret Avancerat skräppost införlivas i andra delar av filtreringstacken.

Avancerade alternativ för skräppostfiltrering ger administratörer möjlighet att granska olika innehållsattribut för ett meddelande. Förekomsten av dessa attribut i ett meddelande antingen ökar spam poäng av meddelandet (vilket ökar risken för att det ska identifieras som spam) eller markerar meddelandet som spam. ASF-alternativen är inriktade på specifika meddelandeegenskaper, till exempel HTML-taggar och URL-omdirigering, som ofta finns i skräppostmeddelanden.
  
Aktivera ASF-alternativ är en aggressiv metod för skräppostfiltrering, och alla meddelanden som filtreras efter dessa alternativ kan inte rapporteras som falska positiva. Dessa meddelanden kan identifieras genom periodiska skräppostmeddelanden för slutanvändare och räddas från skräppostkarantänen. De kan också identifieras via X-header-texten som är specifik för varje ASF-alternativ och som visas i Internet-huvudet på meddelanden där ett ASF-alternativ har matchats. Mer information finns i [Rubriker för skräppostmeddelande](anti-spam-message-headers.md).
  
ASF-alternativ kan ställas in på, stängas av eller testläge när du redigerar innehållsfilterprinciper. Mer information finns i [Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md). Testläget är inte tillgängligt för **NDR-backscatter**, **SPF-post: hårddisk misslyckas**, **Villkorlig avsändande ID-filtrering: hårddisk misslyckas**och **Massutskicksalternativ.** 
  
I följande tabell beskrivs varje avancerat skräppostfiltreringsalternativ.
  
||||
|:-----|:-----|:-----|
|**Alternativ för avancerat skräppostfiltrering** <br/> |**Beskrivning** <br/> |**X-sidhuvudstext** <br/> |
|**Avsnittet Öka avsnittet Om resultat av skräppost** <br/> |När det är aktiverat anger dessa alternativ åtkomstnivån för skräppost (SCL) för ett matchat meddelande till 5 eller 6, vilket anses vara misstänkt skräppost. Åtgärden som utförs i meddelandet matchar inställningen **Skräppost** i innehållsfilterprincipen.  <br/> ||
|Bildlänkar till fjärrplatser  <br/> |När den här inställningen är aktiverad får alla meddelanden med HTML-innehåll som har en IMG-tagg som länkar på distans (till exempel med http) en ökad spampoäng.  <br/> |X-CustomSpam: Bildlänkar till fjärrplatser  <br/> |
|Numerisk IP-adress i URL  <br/> |När den här inställningen är aktiverad får alla meddelanden som har numeriska webbadresser (oftast i form av en IP-adress) en ökad spampoäng.  <br/> |X-CustomSpam: Numerisk IP i URL  <br/> |
|URL-omdirigering till annan port  <br/> |När den här inställningen är aktiverad får alla meddelanden som innehåller en hyperlänk som omdirigerar användaren till andra portar än port 80 (vanlig HTTP-protokollport), 8080 (ALTERNATIV HTTP-port) eller 443 (HTTPS-port) en ökad spampoäng.  <br/> |X-CustomSpam: URL omdirigera till andra portar  <br/> |
|URL till .biz- eller .info-webbplatser  <br/> |När den här inställningen är aktiverad får alla meddelanden som innehåller ett .biz- eller .info-tillägg i brödtexten i ett meddelande en ökad skräppostpoäng.  <br/> |X-CustomSpam: URL till .biz- eller .info-webbplatser  <br/> |
|**Markera som skräppostavsnitt** <br/> |När det är aktiverat anger dessa alternativ spam-konfidensnivån (SCL) för ett matchat meddelande till 9, vilket anses vara säkert skräppost. Åtgärden som utförs i meddelandet matchar inställningen **Skräppost med högt förtroende** i innehållsfilterprincipen.  <br/> ||
|Tomma meddelanden  <br/> |När den här inställningen är aktiverad markeras alla meddelanden där både brödtexten och ämnesraden är tomma och som inte heller har någon bifogad fil som skräppost.  <br/> |X-CustomSpam: Tomt meddelande  <br/> |
|JavaScript eller VBScript i HTML  <br/> |När den här inställningen är aktiverad markeras alla meddelanden som använder JavaScript eller Visual Basic Script Edition i HTML som skräppost. Båda dessa skriptspråk används i ett HTML-meddelande för att automatiskt orsaka att en viss åtgärd inträffar. Webbläsaren tolkar och bearbetar skriptet tillsammans med resten av dokumentet.  <br/> |X-CustomSpam: Javascript- eller VBscript-taggar i HTML  <br/> |
|Frame- eller IFrame-taggar i HTML  <br/> |När den här inställningen är aktiverad \<markeras \<alla\> meddelanden som innehåller HTML-taggen Frame\> eller IFrame som skräppost. Dessa taggar används på webbplatser eller i HTML-meddelanden för att formatera sidan för att visa text eller grafik.  <br/> |X-CustomSpam: IFRAME eller FRAME i HTML  <br/> |
|Objekttaggar i HTML  <br/> |När den här inställningen är aktiverad \<markeras alla meddelanden som innehåller HTML-taggen Object\> som skräppost. Med den här HTML-taggen kan plugin-program eller program köras i ett HTML-fönster.  <br/> |X-CustomSpam: Objekttagg i html  <br/> |
|Bädda in taggar i HTML  <br/> |När den här inställningen är aktiverad \<markeras alla meddelanden som innehåller HTML-taggen Bädda in\> som skräppost. Med den här HTML-taggen kan olika typer av dokument av olika datatyper bäddas in i ett HTML-dokument. Exempel är ljud, filmer eller bilder.  <br/> |X-CustomSpam: Bädda in taggen i html  <br/> |
|Formulärtaggar i HTML  <br/> |När den här inställningen är aktiverad \<markeras alla meddelanden som innehåller HTML-taggen Formulär\> som skräppost. Den här HTML-taggen används för att skapa webbplatsformulär. E-postannonser innehåller ofta den här taggen för att begära information från mottagaren.  <br/> |X-CustomSpam: Form tagg i html  <br/> |
|Webbfel i HTML  <br/> |När den här inställningen är aktiverad markeras alla meddelanden som innehåller ett webbfel som skräppost. Ett webbfel är en bild som är utformad för att avgöra om en webbsida eller ett e-postmeddelande har lästs. Webbbuggar är ofta osynliga för mottagaren eftersom de vanligtvis läggs till i ett meddelande som en bild som är så liten som en pixel med en pixel. Legitima nyhetsbrev kan också använda denna teknik, även om många anser att detta är en kränkning av privatlivet.  <br/> |X-CustomSpam: Webb bugg  <br/> |
|Använda känslig ordlista  <br/> |När den här inställningen är aktiverad markeras alla meddelanden som innehåller ett ord från den känsliga ordlistan som skräppost. Med hjälp av den känsliga ordlistan kan enkelt blockera ord som är associerade med potentiellt stötande meddelanden. Några av dessa ord är skiftlägeskänsliga. Som administratör kan du inte redigera den här listan. Filtrering mot den känsliga ordlistan används både på ett meddelandes ämne och meddelande.  <br/> |X-CustomSpam: Känsligt ord i ämne/kropp  <br/> |
|SPF-rekord: hårt misslyckas|När den här inställningen är aktiverad markeras meddelanden som misslyckas med en SPF-kontroll (vilket innebär att de skickades från en IP-adress som inte har angetts i SPF-posten) som skräppost. Om du aktiverar den här inställningen rekommenderas för organisationer som är oroliga för att ta emot nätfiskemeddelanden.  <br/> <br/> Testläget är inte tillgängligt för det här alternativet.  <br/> |X-CustomSpam: SPF-post misslyckas  <br/> |
|Filtrering av villkorlig avsändare: hårddisk utan fel  <br/> |När den här inställningen är aktiverad markeras alla meddelanden som misslyckas med ett villkorligt avsänar-ID som skräppost. Det här alternativet kombinerar en SPF-kontroll med en avsänd-ID-kontroll för att skydda mot meddelandehuvuden som innehåller förfalskade avsändare.  <br/> <br/> Testläget är inte tillgängligt för det här alternativet.  <br/> |X-CustomSpam: SPF från record fail  <br/> |
|NDR backscatter  <br/> |Om du använder EOP för att skydda lokala postlådor, när den här inställningen är aktiverad, levereras alla legitima NDR-meddelanden (non-delivery report) till den ursprungliga avsändaren och alla meddelanden från bakåtsträvande (illegitima NDR) markeras som skräppost. Om du inte aktiverar den här inställningen går alla NDR fortfarande igenom skräppostfiltrering. I det här fallet kommer de flesta legitima meddelanden att levereras till den ursprungliga avsändaren medan vissa, men inte alla, backscatter meddelanden kommer att få markeras som spam. Backscatter-meddelanden som inte är markerade som skräppost går dock inte till den ursprungliga avsändaren eftersom de kommer att gå till den falska avsändaren. <br/> <br/> Om du använder tjänsten för att skydda Exchange Online-molnbaserade postlådor behöver du inte konfigurera den här inställningen.  <br/><br/> För båda scenarierna (lokala och molnbaserade postlådor) är det inte heller nödvändigt att aktivera den här inställningen för utgående e-post som skickas via tjänsten, eftersom NDR:er som är legitima avvisningsmeddelanden automatiskt identifieras och levereras till den ursprungliga avsändaren . > testläge är inte tillgängligt för det här alternativet.           <br/><br/>TIPS: Mer information om backscatter-meddelanden och EOP finns i [Backscatter-meddelanden och EOP](backscatter-messages-and-eop.md).           |X-CustomSpam: Backscatter NDR  <br/> |
|Massutskick|Filtrering av massutskick av skräppost har dragits tillbaka och ersatts med tröskelinställningarna för bulk och e-post. Kolla in Vad är skillnaden mellan skräppost och [Configure your spam filter policies](configure-your-spam-filter-policies.md) [massutskick av e-post?](what-s-the-difference-between-junk-email-and-bulk-email.md)|X-CustomSpam: Massutskick | Massutskick av e-post  <br/> |
|
