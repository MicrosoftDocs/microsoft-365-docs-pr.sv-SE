---
title: ASF-inställningar i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b286f853-b484-4af0-b01f-281fffd85e7a
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratörer kan läsa mer om avancerade asf-inställningar (Spam Filter) som är tillgängliga i principer mot skräppost i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5ade36086d1503b89b506730b98ac7965845e86b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51073681"
---
# <a name="advanced-spam-filter-asf-settings-in-eop"></a>Avancerade inställningar för skräppostfilter (ASF) i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> ASF-inställningar som för närvarande är tillgängliga i principer för skydd mot skräppost håller på att bli inaktuella. Vi rekommenderar att du inte använder de här inställningarna i principer mot skräppost. Funktionerna i de här ASF-inställningarna införlivas i andra delar av filtreringsstacken. Mer information finns i [Principinställningar för skydd mot skräppost med EOP.](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

I alla Microsoft 365-organisationer tillåter ASF-inställningarna (Advanced Spam Filter) i principer för skräppostskydd i EOP att administratörer kan markera meddelanden som skräppost baserat på specifika meddelandeegenskaper. ASF riktar sig specifikt mot dessa egenskaper eftersom de ofta förekommer i skräppost. Beroende på egenskapen så markerar ASF-identifieringar antingen meddelandet **som** skräppost eller skräppost med **högt förtroende.**

> [!NOTE]
> Att aktivera en eller flera av ASF-inställningarna är en mer aggressiv metod för filtrering av skräppost. Du kan inte rapportera meddelanden som filtreras av ASF som falska positiva resultat. Du kan identifiera meddelanden som filtrerats av ASF genom att:
>
> - Periodiska meddelanden från slutanvändaren om karantän för skräppost.
>
> - Förekomsten av filtrerade meddelanden i karantän.
>
> - De specifika `X-CustomSpam:` X-sidhuvudfälten som läggs till i meddelanden enligt beskrivningen i den här artikeln.

I följande avsnitt beskrivs ASF-inställningarna och -alternativen som är tillgängliga i principer mot skräppost i säkerhets- och efterlevnadscentret för & och i Exchange Online PowerShell eller fristående EOP PowerShell[(New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy) och [Set-HostedContentFilterPolicy).](/powershell/module/exchange/set-hostedcontentfilterpolicy) Mer information finns i [Konfigurera principer för skräppostskydd i EOP](configure-your-spam-filter-policies.md).

## <a name="enable-disable-or-test-asf-settings"></a>Aktivera, inaktivera eller testa ASF-inställningar

För varje ASF-inställning finns följande alternativ i principer mot skräppost:

- **På:** ASF lägger till motsvarande X-sidhuvudfält i meddelandet  och markerar antingen meddelandet som skräppost (SCL 5 eller 6 för Öka [inställningarna för skräppostresultat)](#increase-spam-score-settings)eller SCL 9 **(Hög** konfidens för Inställningarna för [skräppost).](#mark-as-spam-settings)

- **Av:** ASF-inställningen är inaktiverad. Det här är standardvärdet och vi rekommenderar att du inte ändrar det.

- **Test:** ASF lägger till motsvarande X-sidhuvudfält i meddelandet. Vad som händer med meddelandet bestäms av värdet **för Testläge** *(TestModeAction):*

  - **Ingen**: Leverans av meddelanden påverkas inte av ASF-identifieringen. Meddelandet omfattas fortfarande av andra typer av filtrering och regler i EOP.

  - **Lägga till X-sidhuvudtext *(AddXHeader)***: X-sidhuvudvärdet `X-CustomSpam: This message was filtered by the custom spam filter option` läggs till i meddelandet. Du kan använda det här värdet i Inkorgsregler eller e-postflödesregler (kallas även transportregler) för att påverka leveransen av meddelandet.

  - **Send Bcc message (*BccMessage*)**: The specified email addresses (the *TestModeBccToRecipients* parameter value in PowerShell) are added to the Bcc field of the message, and the message is delivered to the additional Bcc recipients. I Säkerhets- & efterlevnadscenter avgränsar du flera e-postadresser med semikolon (;). I PowerShell avgränsar du flera e-postadresser med kommatecken.

  **Anmärkningar**:

  - Testläget är inte tillgängligt för följande ASF-inställningar:

    - **Filtrering av villkorsstyrd avsändar-ID: hard fail** (*MarkAsSpamFromAddressAuthFail*)
    - **NDR backscatter**(*MarkAsSpamNdrBackscatter*)
    - **SPF-post: hard fail** (*MarkAsSpamSpfRecordHardFail*)

  - Samma testlägesåtgärd används på *alla* ASF-inställningar som är inställda på **Testa**. Du kan inte konfigurera olika testlägesåtgärder för olika ASF-inställningar.

## <a name="increase-spam-score-settings"></a>Öka inställningarna för poäng för skräppost

Följande ASF-inställningar anger konfidensnivån för skräppost (SCL) för identifierade meddelanden till  5 eller 6, vilket motsvarar skräppostfiltrets bedömning och motsvarande åtgärd i skräppostprinciperna.

****

|Inställning för principen mot skräppost|Beskrivning|X-sidhuvud tillagt|
|---|---|---|
|**Bildlänkar till fjärrwebbplatser** <p> *IncreaseScoreWithImageLinks*|Meddelanden som innehåller `<Img>` HTML-tagglänkar till fjärrwebbplatser (t.ex. genom att använda http) markeras som skräppost.|`X-CustomSpam: Image links to remote sites`|
|**URL-omdirigering till annan port** <p> *IncreaseScoreWithRedirectToOtherPort*|Meddelande som innehåller hyperlänkar som omdirigerar till TCP-portar som inte är 80 (HTTP), 8080 (alternativ HTTP) eller 443 (HTTPS) markeras som skräppost.|`X-CustomSpam: URL redirect to other port`|
|**Numerisk IP-adress i URL** <p> *IncreaseScoreWithNumericIps*|Meddelanden som innehåller numeriska URL:er (vanligtvis IP-adresser) markeras som skräppost.|`X-CustomSpam: Numeric IP in URL`|
|**URL-adress till .biz- eller .info-webbplatser** <p> *IncreaseScoreWithBizOrInfoUrls*|Meddelanden som `.biz` innehåller eller länkar i `.info` brödtexten i meddelandet markeras som skräppost.|`X-CustomSpam: URL to .biz or .info websites`|
|

## <a name="mark-as-spam-settings"></a>Markera som skräppost

Följande ASF-inställningar anger SCL för identifierade meddelanden till 9, vilket motsvarar skräppostfiltrets bedömning av hög konfidens och motsvarande åtgärd i principer för skräppostskydd. 

****

|Inställning för principen mot skräppost|Beskrivning|X-sidhuvud tillagt|
|---|---|---|
|**Tomma meddelanden** <p> *MarkAsSpamEmptyMessages*|Meddelanden utan ämne, inget innehåll i meddelandets brödtext och inga bifogade filer markeras som skräppost med högt förtroende.|`X-CustomSpam: Empty Message`|
|**JavaScript eller VBScript i HTML** <p> *MarkAsSpamJavaScriptInHtml*|Meddelanden som använder JavaScript eller Visual Basic Script Edition i HTML markeras som skräppost med hög säkerhet. <p> Dessa skriptspråk används i e-postmeddelanden för att orsaka att särskilda åtgärder vidtas automatiskt.|`X-CustomSpam: Javascript or VBscript tags in HTML`|
|**Ram- eller IFrame-taggar i HTML** <p> *MarkAsSpamFramesInHtml*|Meddelanden som innehåller `<frame>` eller `<iframe>` HTML-taggar markeras som skräppost med hög säkerhet. <p> De här taggarna används i e-postmeddelanden för att formatera sidan för visning av text eller grafik.|`X-CustomSpam: IFRAME or FRAME in HTML`|
|**Objekttaggar i HTML** <p> *MarkAsSpamObjectTagsInHtml*|Meddelanden som innehåller `<object>` HTML-taggar markeras som skräppost med hög säkerhet. <p> Med den här taggen kan plugin-program och plugin-program köras i ett HTML-fönster.|`X-CustomSpam: Object tag in html`|
|**Bädda in taggar i HTML** <p> *MarkAsSpamEmbedTagsInHtml*|Meddelanden som innehåller `<embed>` HTML-taggar markeras som skräppost med hög konfidens. <p> Med den här taggen kan du bädda in olika typer av dokument i ett HTML-dokument (till exempel ljud, videor eller bilder).|`X-CustomSpam: Embed tag in html`|
|**Formulärtaggar i HTML** <p> *MarkAsSpamFormTagsInHtml*|Meddelanden som innehåller `<form>` HTML-taggar markeras som skräppost med hög säkerhet. <p> Den här taggen används för att skapa webbplatsformulär. E-postannonser innehåller ofta den här taggen för att begära information från mottagaren.|`X-CustomSpam: Form tag in html`|
|**Webbbuggar i HTML** <p> *MarkAsSpamWebBugsInHtml*|En *webbfel* (som även kallas *webb-beacon*) är ett grafiskt element (ofta en bildpunkt i varje bildpunkt) som används i e-postmeddelanden för att avgöra om meddelandet har lästs av mottagaren. <p> Meddelanden som innehåller webbbuggar markeras som skräppost med hög säkerhet. <p> Legitima nyhetsbrev kan använda webbbuggar, även om många anser att detta är en sekretesskydd. |`X-CustomSpam: Web bug`|
|**Använda listan känsliga ord** <p> *MarkAsSpamSensitiveWordList*|Microsoft har en dynamisk men icke-redigerbar lista över ord som är associerade med potentiellt stötande meddelanden. <p> Meddelanden som innehåller ord från listan med känsliga ord i ämnet eller meddelandetexten markeras som skräppost med hög konfidens.|`X-CustomSpam: Sensitive word in subject/body`|
|**SPF-post: svårt fel** <p> *MarkAsSpamSpfRecordHardFail*|Meddelanden som skickas från en IP-adress som inte angetts i SPF Sender Policy Framework -posten (SPF) i DNS för käll-e-postdomänen markeras som skräppost med hög konfidens. <p> Testläge är inte tillgängligt för den här inställningen.|`X-CustomSpam: SPF Record Fail`|
|**Filtrering av villkorsstyrda avsändare-ID: hårt fel** <p> *MarkAsSpamFromAddressAuthFail*|Meddelanden som gör att en kontroll av villkorsstyrd avsändar-ID misslyckas markeras som skräppost. <p> Den här inställningen kombinerar en SPF-kontroll med en Sender ID-kontroll för att skydda mot meddelanderubriker som innehåller förfalskade avsändare. <p> Testläge är inte tillgängligt för den här inställningen.|`X-CustomSpam: SPF From Record Fail`|
|**NDR bakåtcatter** <p> *MarkAsSpamNdrBackscatter*|*Bakåtcatter är bara* skräp i rapporter om utebliven leverans (kallas även NDR-rapporter eller icke-leveranskavsändare) som orsakas av förfalskade avsändare i e-postmeddelanden. Mer information finns i [Meddelanden på grund av bakåtmeddelande och EOP.](backscatter-messages-and-eop.md) <p> Du behöver inte konfigurera den här inställningen i följande miljöer, eftersom legitima NDR-meddelanden levereras och bakåtcatter markeras som skräppost: <ul><li>Microsoft 365-organisationer med Exchange Online-postlådor.</li><li>Lokala e-postorganisationer där du dirigerar *utgående e-post* via EOP.</li></ul> <p> I fristående EOP-miljöer som skyddar inkommande e-post till lokala postlådor får följande resultat om du slår på eller av den här inställningen: <ul><li> **På:** Legitima NDR-meddelanden levereras och bakåtcatter markeras som skräppost.</li><li>**Av:** Legitima NDR-meddelanden och bakåtcatter går igenom vanlig skräppostfiltrering. De flesta legitima NDR-meddelanden levereras till det ursprungliga meddelandets avsändare. Vissa, men inte alla, bakåtcatter markeras som skräppost med hög konfidens. Per definition kan bakåtcatter bara levereras till den falska avsändaren, inte till den ursprungliga avsändaren.</li></ul> <p> Testläge är inte tillgängligt för den här inställningen.|`X-CustomSpam: Backscatter NDR`|
|