---
title: ASF-inställningar i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan lära sig mer om asf-inställningarna (Advanced Spam Filter) som är tillgängliga i anti-spam-policyer i Exchange Online Protection (EOP).
ms.openlocfilehash: 691539b8abd4fcd2e749c71d7fd337b0105d66ae
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352482"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>Inställningar för avancerat spamfilter (ASF) i EOP

> [!NOTE]
> ASF-inställningar som för närvarande är tillgängliga i anti-spam-policyer håller på att vara inaktuella. Vi rekommenderar att du inte använder dessa inställningar i anti-spam-policyer. Funktionerna i dessa ASF-inställningar införlivas i andra delar av filtreringstacken. Mer information finns i [EOP:s policyinställningar för skräppost](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings).

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor tillåter asf-inställningarna (Advanced Spam Filter) i anti-spam-principer (kallas även principer för skräppostfilter eller innehållsfilterprinciper) administratörer att markera meddelanden som skräppost baserat på specifika meddelandeegenskaper. ASF riktar sig specifikt till dessa egenskaper eftersom de är vanligt förekommande i skräppost. Beroende på egenskapen, ASF upptäckter kommer antingen markera meddelandet som **spam** eller **hög förtroende spam**.

> [!NOTE]
> Att aktivera en eller flera av ASF-inställningarna är en aggressiv metod för skräppostfiltrering. Du kan inte rapportera meddelanden som filtreras av ASF som falska positiva identifieringar. Du kan identifiera meddelanden som filtrerats efter ASF genom att: <ul><li>Periodiska meddelanden om skräppost för slutanvändare.</li><li>Förekomsten av filtrerade meddelanden i karantän.</li><li>De specifika `X-CustomSpam:` X-header-fält som läggs till i meddelanden enligt beskrivningen i det här avsnittet.</li></ul>

I följande avsnitt beskrivs ASF-inställningarna och alternativen som är tillgängliga i anti-spam-principer i Security & Compliance Center och i Exchange Online PowerShell eller fristående EOP PowerShell ([New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy) och [Set-HostedConfilterFason ).](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy) Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

## <a name="enable-disable-or-test-asf-settings"></a>Aktivera, inaktivera eller testa ASF-inställningar

För varje ASF-inställning finns följande alternativ i policyer mot skräppost:

- **På**: ASF lägger till motsvarande X-header-fält i meddelandet, och antingen markerar meddelandet som **spam** (SCL 5 eller 6 för [Öka spam poäng inställningar)](#increase-spam-score-settings)eller **Hög förtroende spam** (SCL 9 för Mark som [spam inställningar](#mark-as-spam-settings)).

- **Av**: ASF-inställningen är inaktiverad. Detta är standardvärdet och vi rekommenderar att du inte ändrar det.

- **Test**: ASF lägger till motsvarande X-header-fält i meddelandet. Vad som händer med meddelandet bestäms av värdet **testläge** (*TestModeAction)*

  - **Ingen**: Meddelanderoutning och leverans påverkas inte av ASF-identifieringen. Meddelandet är fortfarande föremål för andra typer av filtrering och regler i EOP.

  - **Lägg till standardtext för X-header *(AddXHeader)***: X-header-värdet `X-CustomSpam: This message was filtered by the custom spam filter option` läggs till i meddelandet. Du kan använda det här värdet i inkorgsregler eller regler för e-postflöde (kallas även transportregler) för att påverka flödet och leveransen av meddelandet.

  - **Skicka hemligt meddelande *(Hemlig kopia)***: De angivna e-postadresserna (parametervärdet *TestModeBccToRecipients* i PowerShell) läggs till i fältet Hemlig kopia i meddelandet och meddelandet levereras till mottagarna av hemlig kopia. I Security & Compliance Center separerar du flera e-postadresser efter semikolon ( ; ). I PowerShell separerar du flera e-postadresser med kommatecken.

  **Anmärkningar**:

  - Testläget är inte tillgängligt för följande ASF-inställningar:

    - **Filtrering av villkorlig avsändare: hårddiskmisslykning** (*MarkAsSpamFromAddressAuthFail*)

    - **NDR backscatter**(*MarkAsSpamNdrBackscatter*)

    - **SPF-post: hårt fel** *(MarkAsSpamSpfRecordHardFail)*

  - Samma testlägesåtgärd tillämpas på *alla* ASF-inställningar som är inställda på **Test**. Du kan inte konfigurera olika testlägesåtgärder för olika ASF-inställningar.

## <a name="increase-spam-score-settings"></a>Öka inställningarna för skräppostpoäng

Följande ASF-inställningar ställer in säkerhetsnivån för skräppost (SCL) för upptäckta meddelanden **Spam** till 5 eller 6, vilket motsvarar spam-filterdomen och motsvarande åtgärder i anti-spam-policyer.

||||
|---|---|---|
|**Inställning av policy för skräppost**|**Beskrivning**|**X-header har lagts till**|
|**Bildlänkar till fjärrplatser** <br/><br/> *ÖkaScoreWithImageLinks*|Meddelanden som innehåller `<Img>` HTML-tagglänkar till fjärrplatser (till exempel med http) markeras som skräppost.|`X-CustomSpam: Image links to remote sites`|
|**URL-omdirigering till annan port** <br/><br/> *ÖkascoreMedRedirectTootherPort*|Meddelande som innehåller hyperlänkar som omdirigerar till andra TCP-portar än 80 (HTTP), 8080 (alternativ HTTP) eller 443 (HTTPS) markeras som skräppost.|`X-CustomSpam: URL redirect to other port`|
|**Numerisk IP-adress i URL** <br/><br/> *ÖkaScoreWithNumericIps*|Meddelanden som innehåller numeriska webbadresser (vanligtvis IP-adresser) markeras som skräppost.|`X-CustomSpam: Numeric IP in URL`|
|**URL till .biz- eller .info-webbplatser** <br/><br/> *ÖkaScoreMedBizOrInfoUrls*|Meddelanden som innehåller .biz- eller .info-länkar i meddelandets brödtext markeras som skräppost.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>Markera som skräppostinställningar

Följande ASF-inställningar ställer in SCL för upptäckta meddelanden till 9, vilket motsvarar **hög förtroende spam** filter dom och motsvarande åtgärder i anti-spam politik.

||||
|---|---|---|
|**Inställning av policy för skräppost**|**Beskrivning**|**X-header har lagts till**|
|**Tomma meddelanden** <br/><br/> *MarkAsSpamEmptyMessages*|Meddelanden utan ämne, inget innehåll i meddelandetexten och inga bilagor markeras som skräppost med högt förtroende.|`X-CustomSpam: Empty Message`|
|**JavaScript eller VBScript i HTML** <br/><br/> *MarkAsSpamJavaScriptInHtml*|Meddelanden som använder JavaScript eller Visual Basic Script Edition i HTML markeras som skräppost med högt förtroende. <br/><br/> Dessa skriptspråk används i e-postmeddelanden för att orsaka att specifika åtgärder automatiskt utförs.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Frame- eller IFrame-taggar i HTML** <br><br/> *MarkAsSpamFramesInHtml*|Meddelanden som innehåller `<frame>` eller `<iframe>` HTML-taggar markeras som skräppost med högt förtroende. <br/><br/> Dessa taggar används i e-postmeddelanden för att formatera sidan för att visa text eller grafik.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Objekttaggar i HTML** <br><br/> *MarkAsSpamObjectTagsInHtml*|Meddelanden som innehåller `<object>` HTML-taggar markeras som skräppost med högt förtroende. <br/><br/> Med den här taggen kan plugin-program eller program köras i ett HTML-fönster.|`X-CustomSpam: Object tag in html`|
|**Bädda in taggar i HTML** <br><br/> *MarkAsSpamEmbedTagsInHtml*|Meddelande som innehåller `<embed>` HTML-taggar markeras som skräppost med högt förtroende. <br/><br/> Med den här taggen kan du bädda in olika typer av dokument av olika datatyper i ett HTML-dokument (till exempel ljud, filmer eller bilder).|`X-CustomSpam: Embed tag in html`|
|**Formulärtaggar i HTML** <br><br/> *MarkAsSpamFormTagsInHtml*|Meddelanden som innehåller `<form>` HTML-taggar markeras som skräppost med högt förtroende. <br/><br/> Den här taggen används för att skapa webbplatsformulär. E-postannonser innehåller ofta den här taggen för att begära information från mottagaren.|`X-CustomSpam: Form tag in html`|
|**Webbfel i HTML** <br><br/> *MarkAsSpamWebBugsInHtml*|Ett *webbfel* (kallas även *en webbfyr)* är ett grafiskt element (ofta så litet som en pixel med en pixel) som används i e-postmeddelanden för att avgöra om meddelandet lästes. <br/><br/> Meddelanden som innehåller webbbuggar markeras som skräppost med högt förtroende. <br/><br/> Legitima nyhetsbrev kan använda webbbuggar, även om många anser att detta är en integritetskränkning. |`X-CustomSpam: Web bug`|
|**Använda känslig ordlista** <br><br/> *MarkAsSpamSensitiveWordList*|Microsoft har en dynamisk men icke-redigerbar lista med ord som är associerade med potentiellt stötande meddelanden. <br/><br/> Meddelanden som innehåller ord från den känsliga ordlistan i ämnes- eller meddelandetexten markeras som skräppost med högt förtroende.|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF-rekord: hårt misslyckas** <br><br/> *MarkAsSpamSpfRecordHardFail*|Meddelanden som skickas från en IP-adress som inte anges i SPF Sender Policy Framework (SPF) i DNS för käll-e-postdomänen markeras som skräppost med högt förtroende. <br/><br/> Testläget är inte tillgängligt för den här inställningen.|`X-CustomSpam: SPF Record Fail`|
|**Filtrering av villkorlig avsändare: hårddisk utan fel** <br><br/> *MarkAsSpamFrånAdressAuthFail*|Meddelanden om att det inte fungerar som ett villkorligt avsänar-ID markeras som skräppost. <br/><br/> Den här inställningen kombinerar en SPF-kontroll med en avsänd-ID-kontroll för att skydda mot meddelandehuvuden som innehåller förfalskade avsändare. <br/><br/> Testläget är inte tillgängligt för den här inställningen.|`X-CustomSpam: SPF From Record Fail`|
|**NDR backscatter** <br><br/> *MarkAsSpamNdrBackscatter*|*Backscatter* är värdelös icke-leverans rapporter (även känd som NDRs eller studsa meddelanden) som orsakas av förfalskade avsändare i e-postmeddelanden. Mer information finns i [Backscatter-meddelanden och EOP](backscatter-messages-and-eop.md). <br/><br/> Du behöver inte konfigurera den här inställningen i följande miljöer, eftersom legitima NDR levereras och backscatter markeras som skräppost: <ul><li>Microsoft 365-organisationer med Exchange Online-postlådor.</li><li>Lokala e-postorganisationer där du dirigerar *utgående* e-post via EOP.</li></ul><br/> I fristående EOP-miljöer som skyddar inkommande e-post till lokala postlådor har du följande resultat om du aktiverar eller inaktiverar den här inställningen: <ul><li> **På**: Legitima NDR levereras och backscatter är markerad som skräppost.</li><li>**Av:** Legitima NDRs och backscatter gå igenom normal spam filtrering. De flesta legitima NDR kommer att levereras till den ursprungliga meddelandet avsändaren. Vissa, men inte alla, backscatter är markerade som hög förtroende spam. Per definition kan backscatter endast levereras till förfalskad avsändare, inte till den ursprungliga avsändaren.</li></ul><br/> Testläget är inte tillgängligt för den här inställningen.|`X-CustomSpam: Backscatter NDR`|
|
