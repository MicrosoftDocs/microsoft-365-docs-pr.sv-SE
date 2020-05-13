---
title: Regler för e-postflöde i EOP
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
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: Du kan använda regler för e-postflöde (transportregler) för att identifiera och vidta åtgärder för meddelanden som flödar genom organisationen.
ms.openlocfilehash: 8eb4b805065ef1e279c5bbdab17a86b29aacc17b
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209697"
---
# <a name="mail-flow-rules-transport-rules-in-standalone-eop"></a>Regler för e-postflöde (transportregler) i fristående EOP

I fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor kan du använda e-postflödesregler (kallas även transportregler) för att identifiera och vidta åtgärder för meddelanden som flödar genom din organisation.

I det här avsnittet beskrivs komponenterna i reglerna för e-postflöde och hur de fungerar.

Steg om hur du skapar, kopierar och hanterar regler för e-postflöde finns [i Hantera regler för e-postflöde i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules). För varje regel har du möjlighet att verkställa den, testa den eller testa den och meddela avsändaren. Mer information om testningsalternativen finns i Testa regler för [e-postflöde](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/test-mail-flow-rules) och [principtips i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips).

Sammanfattande och detaljerade rapporter om meddelanden som matchade regler för e-postflöde finns i [Använda e-postskyddsrapporter för att visa data om skadlig kod, skräppost och regelidentifieringar](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports).

Information om hur du implementerar specifika meddelandeprinciper med hjälp av regler för e-postflöde finns i följande avsnitt:

- [Använda regler för e-postflöde för att granska bifogade filer i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

- [Konfigurera kryptering i Office 365 Enterprise](../../compliance/set-up-encryption.md)

- [Ansvarsfriskrivningar för hela organisationen, signaturer, sidfötter eller sidhuvuden i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

- [Använd regler för e-postflöde för att ställa in scl (Spam Confidence Level) i meddelanden](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- [Skapa blockavsändare i EOP](create-block-sender-lists-in-office-365.md)

- [Minska hot mot skadlig kod genom blockering av bifogade filer i Exchange Online Protection](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)

- [Definiera regler för att kryptera eller dekryptera e-postmeddelanden i Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

Följande video ger en demonstration av att ställa in regler för e-postflöde i fristående EOP.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]

## <a name="mail-flow-rule-components"></a>Komponenter i regelkomponenter för e-postflöde

En regel för e-postflöde består av villkor, undantag, åtgärder och egenskaper:

- **Villkor**: Identifiera de meddelanden som du vill använda åtgärderna på. Vissa villkor undersöker fälten meddelandehuvud (till exempel fälten Till, Från eller Kopia). Andra villkor undersöker meddelandeegenskaper (till exempel meddelandeämne, brödtext, bilagor, meddelandestorlek eller meddelandeklassificering). De flesta villkor kräver att du anger en jämförelseoperator (till exempel lika med, inte är lika med eller innehåller) och ett värde som ska matchas. Om det inte finns några villkor eller undantag tillämpas regeln på alla meddelanden.

Mer information om regelvillkor för e-postflöde i fristående EOP finns i [Villkor och undantag för E-postflödesregel (predikat) i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

- **Undantag**: Du kan också identifiera de meddelanden som åtgärderna inte ska gälla för. Samma meddelandeidentifierare som är tillgängliga i villkor är också tillgängliga i undantag. Undantag åsidosätter villkoren och förhindrar att regelåtgärderna tillämpas på ett meddelande, även om meddelandet matchar alla konfigurerade villkor.

- **Åtgärder**: Ange vad du ska göra med meddelanden som matchar villkoren i regeln och matchar inte något av undantagen. Det finns många tillgängliga åtgärder, till exempel att avvisa, ta bort eller omdirigera meddelanden, lägga till ytterligare mottagare, lägga till prefix i meddelandeämnet eller infoga ansvarsfriskrivningar i meddelandetexten.

Mer information om regelåtgärder för e-postflöde som är tillgängliga i fristående EOP finns [i Regelåtgärder för e-postflöde i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).

- **Egenskaper**: Ange andra regelinställningar som inte är villkor, undantag eller åtgärder. Till exempel när regeln ska tillämpas, om regeln ska tillämpas eller testas och tidsperioden när regeln är aktiv.

  Mer information finns i avsnittet Egenskaper för [e-postflödesregel](#mail-flow-rule-properties) i det här avsnittet.

### <a name="multiple-conditions-exceptions-and-actions"></a>Flera villkor, undantag och åtgärder

Följande tabell visar hur flera villkor, villkorsvärden, undantag och åtgärder hanteras i en regel.

|**Komponent**|**Logik**|**Kommentarer**|
|:-----|:-----|:-----|
|Flera villkor|Och|Ett meddelande måste matcha alla villkor i regeln. Om du behöver matcha ett eller annat villkor använder du separata regler för varje villkor. Om du till exempel vill lägga till samma ansvarsfriskrivning i meddelanden med bifogade filer och meddelanden som innehåller specifik text skapar du en regel för varje villkor. I EAC kan du enkelt kopiera en regel.|
|Ett villkor med flera värden|ELLER|Med vissa villkor kan du ange mer än ett värde. Meddelandet måste matcha alla (inte alla) av de angivna värdena. Om ett e-postmeddelande till exempel har ämnesinformationen Lagerpris och **ämnet innehåller något av dessa ordvillkor** är konfigurerat för att matcha orden Contoso eller lager, är villkoret uppfyllt eftersom ämnet innehåller minst ett av de angivna värdena.|
|Flera undantag|ELLER|Om ett meddelande matchar något av undantagen tillämpas inte åtgärderna på meddelandet. Meddelandet behöver inte matcha alla undantag.|
|Flera åtgärder|Och|Meddelanden som matchar en regels villkor får alla åtgärder som anges i regeln. Om åtgärderna till exempel **Förbered ämnet för meddelandet med** och Lägg till mottagare i rutan Hemlig **kopia** är markerade, tillämpas båda åtgärderna på meddelandet. <br/><br/> Tänk på att vissa åtgärder, till exempel **Ta bort meddelandet utan att meddela någon** åtgärd, förhindrar att efterföljande regler tillämpas på ett meddelande. Andra åtgärder, till exempel **Vidarebefordra meddelandet** tillåter inte ytterligare åtgärder. <br/><br/> Du kan också ange en åtgärd för en regel så att efterföljande regler inte tillämpas på meddelandet när regeln tillämpas.|

### <a name="mail-flow-rule-properties"></a>Egenskaper för regelegenskaper för e-postflöde

I följande tabell beskrivs de regelegenskaper som är tillgängliga i regler för e-postflöde.

|**Egenskapsnamn i EAC**|**Parameternamn i PowerShell**|**Beskrivning**|
|:-----|:-----|:-----|
|**Prioritet**|_Prioritet_|Anger den ordning som reglerna tillämpas på meddelanden. Standardprioriteten baseras på när regeln skapas (äldre regler har högre prioritet än nyare regler och regler med högre prioritet bearbetas före regler med lägre prioritet). <br/><br/> Du ändrar regelprioriteten i EAC genom att flytta regeln uppåt eller nedåt i regellistan. I PowerShell anger du prioritetsnumret (0 har högsta prioritet). <br/><br/> Om du till exempel har en regel för att avvisa meddelanden som innehåller ett kreditkortsnummer och en annan som kräver godkännande, vill du att avvisningsregeln ska ske först och sluta tillämpa andra regler.  |
|**Läge**|_Läge_|Du kan ange om du vill att regeln ska börja bearbeta meddelanden omedelbart eller om du vill testa regler utan att påverka leveransen av meddelandet (med eller utan dataförlustskydd eller DLP-principtips). <br/><br/> Principtipsen visar en kort anteckning i Outlook eller Outlook på webben som innehåller information om möjliga policyöverträdelser till den person som skapar meddelandet. Mer information finns i **Policytips**. <br/><br/> Mer information om lägena finns i **Testa en regel för e-postflöde**.|
|**Aktivera den här regeln på följande datum** <br/><br/> **Inaktivera den här regeln på följande datum**|_ActivationDate_ <br/> _UtgångsdatumDatum_|Anger datumintervallet när regeln är aktiv.|
|**Markerad** eller inte markerad i kryssrutan markerad eller inte markerad|Nya regler: _Aktiverad_ parameter på cmdleten **New-TransportRule.** <br/><br/> Befintliga regler: Använd cmdlets **enable-transportRule** eller **Disable-TransportRule.** <br/><br/> Värdet visas i egenskapen **State** för regeln.|Du kan skapa en inaktiverad regel och aktivera den när du är redo att testa den. Du kan också inaktivera en regel utan att ta bort den för att bevara inställningarna.|
|**Skjuta upp meddelandet om regelbearbetningen inte slutförs**|_RuleErrorAction (RuleErrorAction)_|Du kan ange hur meddelandet ska hanteras om regelbearbetningen inte kan slutföras. Som standard ignoreras regeln, men du kan välja att skicka meddelandet igen för bearbetning.|
|**Matcha avsändaradress i meddelande**|_AvsändareAdressPlats_|Om regeln använder villkor eller undantag som undersöker avsändarens e-postadress kan du söka efter värdet i meddelandehuvudet, meddelandekuvertet eller båda.|
|**Sluta bearbeta fler regler**|_AvsändareAdressPlats_|Detta är en åtgärd för regeln, men det ser ut som en egenskap i EAC. Du kan välja att sluta tillämpa ytterligare regler på ett meddelande när en regel har bearbetat ett meddelande.|
|**Kommentarer**|_Kommentarer_|Du kan skriva beskrivande kommentarer om regeln.|

## <a name="how-mail-flow-rules-are-applied-to-messages"></a>Så här tillämpas regler för e-postflöde på meddelanden

Alla meddelanden som flödar genom din organisation utvärderas mot de aktiverade reglerna för e-postflöde i organisationen. Regler bearbetas i den ordning som anges på sidan **E-postflödesregler** \> **Rules** i EAC eller baserat på motsvarande _prioritetsparametervärde_ i PowerShell.

Varje regel erbjuder också möjligheten att sluta bearbeta fler regler när regeln matchas. Den här inställningen är viktig för meddelanden som matchar villkoren i flera regler för e-postflöde (vilken regel vill du ha tillämpad på meddelandet? Alla? Bara en?).

### <a name="differences-in-processing-based-on-message-type"></a>Skillnader i bearbetning baserat på meddelandetyp

Det finns flera typer av meddelanden som passerar genom en organisation. I följande tabell visas vilka meddelandetyper som kan bearbetas av regler för e-postflöde.

|**Typ av meddelande**|**Kan en regel tillämpas?**|
|:-----|:-----|
|**Vanliga meddelanden**: Meddelanden som innehåller ett enda RTF-format (RTF), HTML eller vanlig textmeddelandetext eller en flerdelad eller alternativ uppsättning meddelandekroppar.|Ja|
|**Meddelandekryptering för Office 365:** Meddelanden krypterade med Office 365-meddelandekryptering i Office 365. Mer information finns [i Kryptering i Office 365](https://docs.microsoft.com/microsoft-365/compliance/encryption).|Regler kan alltid komma åt kuvertrubriker och processmeddelanden baserat på villkor som granskar dessa rubriker. <br/><br/> För att en regel ska kunna granska eller ändra innehållet i ett krypterat meddelande måste du kontrollera att transportdekrypning är aktiverat (Obligatoriskt eller Valfritt, standard är valfritt). Mer information finns i [Definiera regler för att kryptera eller dekryptera e-postmeddelanden i Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).|
|**S/MIME-krypterade meddelanden**|Regler kan bara komma åt kuvertrubriker och processmeddelanden baserat på villkor som granskar dessa rubriker. <br/><br/> Regler med villkor som kräver granskning av meddelandets innehåll eller åtgärder som ändrar meddelandets innehåll kan inte bearbetas.|
|**RMS-skyddade meddelanden:** Meddelanden som hade en AD RMS-princip (Active Directory Rights Management Services) eller RMS -principen (Azure Rights Management) tillämpad.|Regler kan alltid komma åt kuvertrubriker och processmeddelanden baserat på villkor som granskar dessa rubriker. <br/><br/> För att en regel ska kunna granska eller ändra innehållet i ett RMS-skyddat meddelande måste du kontrollera att transportdekrypning är aktiverat (Obligatoriskt eller Valfritt, standard är valfritt).|
|**Rensa signerade meddelanden**: Meddelanden som har signerats men inte krypterats.|Ja|
|**UM-meddelanden:** Meddelanden som skapas eller bearbetas av tjänsten Unified Messaging, till exempel röstmeddelanden, fax, meddelanden om missade samtal och meddelanden som skapas eller vidarebefordras med hjälp av Microsoft Outlook Voice Access.|Ja|
|**Anonyma meddelanden**: Meddelanden som skickas av anonyma avsändare.|Ja|
|**Läs rapporter**: Rapporter som genereras som svar på begäran om läskvitto från avsändare. Läsrapporter har en meddelandeklass `IPM.Note*.MdnRead` eller `IPM.Note*.MdnNotRead` .|Ja|

## <a name="what-else-should-i-know"></a>Vad mer ska jag veta?

- Egenskapsvärdet **version** eller **RuleVersion** för en regel är inte viktigt i Exchange Online Protection.

- När du har skapat eller ändrat en regel för e-postflöde kan det ta upp till 30 minuter innan den nya eller uppdaterade regeln tillämpas på meddelanden.

## <a name="for-more-information"></a>Mer information

[Använda regler för e-postflöde för att granska bifogade filer i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

[Kryptering av e-post i Office 365](../../compliance/email-encryption.md)

[Regelgränser för journal, transport och inkorg](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#journal-transport-and-inbox-rule-limits)
