---
title: E-postflödesregler i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: Du kan använda e-postflödesregler (transportregler) för att identifiera och vidta åtgärder på meddelanden som skickas genom organisationen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3f873d4e46c9e3b7f085e03a9fbb19e5914317fa
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167041"
---
# <a name="mail-flow-rules-transport-rules-in-standalone-eop"></a>E-postflödesregler (transportregler) i fristående EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

I fristående Exchange Online Protection-organisationer (EOP) utan Exchange Online-postlådor kan du använda e-postflödesregler (kallas även transportregler) för att identifiera och vidta åtgärder på meddelanden som flödar genom organisationen.

I det här avsnittet beskrivs komponenterna i e-postflödesregler och hur de fungerar.

Information om hur du skapar, kopierar och hanterar e-postflödesregler finns i [Hantera e-postflödesregler i Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules) För varje regel kan du välja att tillämpa den, testa den eller testa den och meddela avsändaren. Mer information om testalternativ finns i Testa [e-postflödesregler och](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/test-mail-flow-rules) [principtips i Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips)

Sammanfattnings- och detaljrapporter om meddelanden som matchade e-postflödesregler finns i Använda rapporter för e-postskydd för att visa data om skadlig programvara, skräppost och [regelidentifiering.](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports)

Information om hur du implementerar specifika meddelandeprinciper med hjälp av e-postflödesregler finns i följande avsnitt:

- [Kontrollera bifogade filer i meddelanden i Exchange Online med hjälp av e-postflödesregler](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

- [Konfigurera kryptering i Office 365 Enterprise](../../compliance/set-up-encryption.md)

- [Ansvarsfriskrivningar, signaturer, sidfötter och sidhuvuden i hela organisationen i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

- [Använda e-postflödesregler för att ange konfidensnivå för skräppost (SCL) i meddelanden](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- [Skapa listor med spärrade avsändare i EOP](create-block-sender-lists-in-office-365.md)

- [Minska hot mot skadlig programvara genom blockering av bifogade filer i Exchange Online Protection](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)

- [Definiera regler för att kryptera eller dekryptera e-postmeddelanden i Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

I följande video får du en demonstration av hur du skapar e-postflödesregler i fristående EOP.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]

## <a name="mail-flow-rule-components"></a>Komponenter i e-postflödesregel

En e-postflödesregel består av villkor, undantag, åtgärder och egenskaper:

- **Villkor:** Identifiera de meddelanden som du vill tillämpa åtgärderna på. Vissa villkor kan granska fälten i meddelanderubriken (till exempel fälten Till, Från eller Kopia). Andra villkor kan undersöka meddelandeegenskaper (till exempel meddelandets ämne, brödtext, bifogade filer, meddelandestorlek eller klassificering av meddelanden). För de flesta villkor måste du ange en jämförelseoperator (till exempel lika med, inte lika med eller innehåller) och ett värde som ska matchas. Om det inte finns några villkor eller undantag tillämpas regeln på alla meddelanden.

Mer information om villkoren för e-postflödesregel i fristående EOP finns i Villkoren för e-postflödesregel och undantag [(predikat) i Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

- **Undantag:** Identifiera eventuellt meddelanden som åtgärderna inte ska gälla för. Samma meddelandeidentifierare som är tillgängliga i villkoren är också tillgängliga i undantag. Undantag åsidosätter villkor och förhindrar att regelåtgärder tillämpas på ett meddelande, även om meddelandet matchar alla konfigurerade villkor.

- **Åtgärder:** Ange vad du vill göra för meddelanden som matchar villkoren i regeln, och inte matchar något av undantagen. Det finns många tillgängliga åtgärder, till exempel för att avvisa, ta bort eller omdirigera meddelanden, lägga till ytterligare mottagare, lägga till prefix i meddelandets ämne eller infoga ansvarsfriskrivningar i meddelandets brödtext.

Mer information om åtgärder för e-postflödesregel som är tillgängliga i fristående EOP finns i [E-postflödesregelåtgärder i Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- **Egenskaper**: Ange andra regelinställningar som inte är villkor, undantag eller åtgärder. Till exempel när regeln ska tillämpas, oavsett om regeln ska användas eller testas, samt tidsperioden då regeln är aktiv.

  Mer information finns i avsnittet egenskaper [för e-postflödesregel](#mail-flow-rule-properties) i den här artikeln.

### <a name="multiple-conditions-exceptions-and-actions"></a>Flera villkor, undantag och åtgärder

I följande tabell visas hur flera villkor, villkorsvärden, undantag och åtgärder hanteras i en regel.

****

|Komponent|Logik|Kommentarer|
|---|---|---|
|Flera villkor|OCH|Ett meddelande måste matcha alla villkor i regeln. Om du behöver matcha ett eller ett annat villkor använder du separata regler för varje villkor. Om du till exempel vill lägga till samma ansvarsfriskrivning i meddelanden med bifogade filer och meddelanden som innehåller specifik text, skapar du en regel för varje villkor. I EAC kan du enkelt kopiera en regel.|
|Ett villkor med flera värden|ELLER|Vissa villkor tillåter att du anger mer än ett värde. Meddelandet måste matcha ett (inte alla) av de angivna värdena. Om ett e-postmeddelande till exempel innehåller aktieprisinformation och ämnet innehåller något av dessa ord villkor är konfigurerat att matcha orden Contoso eller aktie, är villkoret uppfyllt eftersom ämnet innehåller minst ett av de angivna värdena. |
|Flera undantag|ELLER|Om ett meddelande matchar något av undantagen tillämpas inte åtgärderna på meddelandet. Meddelandet behöver inte matcha alla undantag.|
|Flera åtgärder|OCH|Meddelanden som matchar villkoren för en regel hämtar alla åtgärder som anges i regeln. Om till exempel åtgärderna **Som lägger till** ämnet  för meddelandet tillsammans med och Lägg till mottagare i rutan Hemlig kopia är markerade tillämpas båda åtgärderna på meddelandet. <p> Tänk på att vissa åtgärder,  till exempel att ta bort meddelandet utan att meddela någon åtgärd, förhindrar att efterföljande regler tillämpas på ett meddelande. Andra åtgärder, till **exempel Vidarebefordra meddelandet,** tillåter inte ytterligare åtgärder. <p> Du kan också ange en åtgärd för en regel så att efterföljande regler inte tillämpas på meddelandet när den regeln används.|
|

### <a name="mail-flow-rule-properties"></a>Egenskaper för e-postflödesregel

I följande tabell beskrivs de regelegenskaper som är tillgängliga i e-postflödesregler.

****

|Egenskapsnamn i EAC|Parameternamn i PowerShell|Beskrivning|
|---|---|---|
|**Priority**|_Priority_|Anger i vilken ordning reglerna tillämpas på meddelanden. Standardprioritet baseras på när regeln skapas (äldre regler har högre prioritet än nyare regler och regler med högre prioritet bearbetas före regler med lägre prioritet). <p> Du ändrar regelprioritet i EAC genom att flytta regeln uppåt eller nedåt i listan med regler. I PowerShell anger du prioritetsnumret (0 är högsta prioritet). <p> Om du till exempel har en regel för att avvisa meddelanden som innehåller ett kreditkortsnummer och en annan som kräver godkännande, vill du att regeln om avvisande ska ske först och sluta använda andra regler.  |
|**Läge**|_Läge_|Du kan ange om du vill att regeln ska börja bearbeta meddelanden direkt eller om du vill testa regler utan att påverka leveransen av meddelandet (med eller utan dataförlustskydd eller DLP-principtips). <p> Principtips presenterar en kort anteckning i Outlook eller Outlook på webben som tillhandahåller information om möjliga principbrott för den person som skapar meddelandet. Mer information finns i **policytipsen.** <p> Mer information om lägena finns i Testa **en e-postflödesregel.**|
|**Aktivera den här regeln följande datum** <p> **Inaktivera den här regeln följande datum**|_ActivationDate_ <p> _ExpiryDate_|Anger datumintervallet när regeln är aktiv.|
|**Markerad** eller inte markerad i kryssrutan|Nya regler: _Aktiverad_ parameter i **cmdleten New-TransportRule.** <p> Befintliga regler: Använd **cmdletarna Enable-TransportRule** **eller Disable-TransportRule.** <p> Värdet visas i egenskapen **Delstat** för regeln.|Du kan skapa en inaktiverad regel och aktivera den när du är redo att testa den. Du kan också inaktivera en regel utan att ta bort den om du vill behålla inställningarna.|
|**Skjuta upp meddelandet om regelbearbetningen inte slutförs**|_RuleErrorAction_|Du kan ange hur meddelandet ska hanteras om regelbearbetningen inte kan slutföras. Som standard ignoreras regeln, men du kan välja att skicka meddelandet igen för bearbetning.|
|**Matcha avsändaradress i meddelande**|_SenderAddressLocation_|Om regeln använder villkor eller undantag som undersöker avsändarens e-postadress kan du leta efter värdet i meddelandehuvudet, meddelandekuvertet eller båda.|
|**Sluta bearbeta fler regler**|_SenderAddressLocation_|Det här är en åtgärd för regeln, men den ser ut som en egenskap i EAC. Du kan välja att sluta tillämpa ytterligare regler på ett meddelande när en regel har bearbetar ett meddelande.|
|**Kommentarer**|_Kommentarer_|Du kan ange beskrivande kommentarer om regeln.|
|

## <a name="how-mail-flow-rules-are-applied-to-messages"></a>Hur e-postflödesregler tillämpas på meddelanden

Alla meddelanden som flödar genom organisationen utvärderas mot de aktiverade e-postflödesreglerna i organisationen. Regler bearbetas i den  ordning som visas på sidan E-postflödesregler i EAC, eller baserat på motsvarande värde för \>  prioritetsparameter i PowerShell. 

Varje regel ger också möjlighet att stoppa bearbetningen av fler regler när regeln matchas. Den här inställningen är viktig för meddelanden som matchar villkoren i flera e-postflödesregler (vilken regel vill du tillämpa på meddelandet? Alla? Bara ett?).

### <a name="differences-in-processing-based-on-message-type"></a>Skillnader i bearbetning baserat på meddelandetyp

Det finns flera typer av meddelanden som passerar genom en organisation. I följande tabell visas vilka meddelandetyper som kan bearbetas av e-postflödesregler.

****

|Typ av meddelande|Kan en regel användas?|
|---|---|
|**Vanliga meddelanden:** Meddelanden som innehåller ett enda RTF-format, HTML eller oformaterad text i meddelandetexten eller en brödtext med flera delar eller en alternativ uppsättning meddelandetext.|Ja|
|**Meddelandekryptering i Office 365:** Meddelanden som krypteras med meddelandekryptering i Office 365 i Office 365. Mer information finns i Kryptering [i Office 365.](https://docs.microsoft.com/microsoft-365/compliance/encryption)|Regler kan alltid komma åt kuverthuvuden och bearbeta meddelanden utifrån villkor som inspekterar dessa sidhuvuden. <p> Om du vill kontrollera eller ändra en regel i ett krypterat meddelande måste du kontrollera att transportdekryptering är aktiverat (Obligatoriskt eller valfritt. Standardvärdet är Valfritt). Mer information finns i Definiera [regler för att kryptera eller dekryptera e-postmeddelanden i Office 365.](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)|
|**S/MIME-krypterade meddelanden**|Regler kan bara komma åt kuverthuvuden och bearbeta meddelanden utifrån villkor som inspekterar dessa sidhuvuden. <p> Regler med villkor som kräver kontroll av meddelandets innehåll eller åtgärder som ändrar meddelandets innehåll kan inte bearbetas.|
|**RMS-skyddade meddelanden:** Meddelanden som har en AD RMS-princip (Active Directory Rights Management Services) eller Azure Rights Management (RMS).|Regler kan alltid komma åt kuverthuvuden och bearbeta meddelanden utifrån villkor som inspekterar dessa sidhuvuden. <p> Om du vill kontrollera eller ändra innehållet i ett RMS-skyddat meddelande måste du kontrollera att transportdekryptering är aktiverat (Obligatoriskt eller valfritt, standard är valfritt).|
|**Avmarkerade meddelanden:** Meddelanden som har signerats men inte krypterats.|Ja|
|**UM-meddelanden:** Meddelanden som skapas eller bearbetas av Unified Messaging-tjänsten, t.ex. röstmeddelanden, fax, aviseringar om missade samtal och meddelanden som skapas eller vidarebefordras med Microsoft Outlook Voice Access.|Ja|
|**Anonyma meddelanden:** Meddelanden som skickas av anonyma avsändare.|Ja|
|**Läs rapporter:** Rapporter som genereras som svar på begäran om läskvitto av avsändare. Läs rapporter har en meddelandeklass av `IPM.Note*.MdnRead` eller `IPM.Note*.MdnNotRead` .|Ja|
|

## <a name="what-else-should-i-know"></a>Vad mer bör jag veta?

- Värdet **för** egenskapen **Version eller RuleVersion** för en regel är inte viktigt i Exchange Online Protection.

- När du har skapat eller redigerat en e-postflödesregel kan det ta upp till 30 minuter innan den nya eller uppdaterade regeln tillämpas på meddelanden.

## <a name="for-more-information"></a>Mer information

[Kontrollera bifogade filer i meddelanden i Exchange Online med hjälp av e-postflödesregler](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

[E-postkryptering i Office 365](../../compliance/email-encryption.md)

[Begränsningar av journal-, transport- och inkorgsregel](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#journal-transport-and-inbox-rule-limits)
