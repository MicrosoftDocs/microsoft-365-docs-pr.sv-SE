---
title: Regler för e-postflöde i EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9c2cf227-eff7-48ef-87fb-487186e47363
description: Du kan använda regler för e-postflöde för att identifiera och vidta åtgärder för meddelanden som flödar i din organisation.
ms.openlocfilehash: 6bbf50b1a99b6691e959f6dcd4cfce33686a0014
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659210"
---
# <a name="mail-flow-rules-transport-rules-in-standalone-eop"></a>E-postflödesregler (transportregler) i fristående EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


I fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor kan du använda regler för e-postflöde (kallas även transport regler) för att identifiera och vidta åtgärder för meddelanden som flödar i organisationen.

I det här avsnittet förklaras komponenterna i regler för e-postflöde och hur de fungerar.

Anvisningar för hur du skapar, kopierar och hanterar regler för e-postflöden finns i [Hantera regler för e-postflöde i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules). För varje regel kan du välja att tvinga fram, testa den eller testa den och meddela avsändaren. Mer information om test alternativen finns i [testa regler för e-postflöden](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/test-mail-flow-rules) och [policy tips i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/policy-tips).

Information om vilka meddelanden som matchas med regler för e-postflöde finns i [använda e-postskydds rapporter för att visa information om skadlig program vara, skräp post och identifiering av regler](https://docs.microsoft.com/exchange/monitoring/use-mail-protection-reports).

Information om hur du implementerar specifika meddelande principer genom att använda e-postflödes regler finns i följande avsnitt:

- [Använda regler för e-postflöde för att inspektera bifogade filer i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

- [Konfigurera kryptering i Office 365 Enterprise](../../compliance/set-up-encryption.md)

- [Meddelande fri skrivningar för hela organisationen, signaturer, sid fötter eller rubriker i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)

- [Använda regler för e-postflöde för att ange konfidensnivå för skräp post (SCL) i meddelanden](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

- [Skapa block avsändare i EOP](create-block-sender-lists-in-office-365.md)

- [Minska risken mot skadlig kod genom blockering av bifogade filer i Exchange Online Protection](reducing-malware-threats-through-file-attachment-blocking-in-exchange-online-pro.md)

- [Definiera regler för att kryptera eller dekryptera e-postmeddelanden i Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

Följande video visar en demonstration av hur du konfigurerar regler för e-postflöde i fristående EOP.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/7cdcd2cb-9382-4065-98e1-81257b32a189?autoplay=false]

## <a name="mail-flow-rule-components"></a>Komponent för e-postflöde

En regel för e-postflöden består av villkor, undantag, åtgärder och egenskaper:

- **Villkor**: identifiera de meddelanden som du vill tillämpa åtgärderna på. Vissa villkor undersöker meddelande rubrik fälten (till exempel fälten till, från eller kopia). Andra villkor kontrollerar meddelande egenskaper (till exempel meddelandets ämne, brödtext, bifogade filer, meddelande storlek eller meddelande klassificering). De flesta villkor kräver att du anger en jämförelse operator (till exempel lika med, inte lika med eller innehåller) och ett värde att matcha. Om det inte finns några villkor eller undantag tillämpas regeln på alla meddelanden.

Mer information om villkor för regel för e-postflöde i fristående EOP finns i [villkor och undantag för e-postflödes regler (predikat) i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).

- **Undantag**: Ange eventuellt vilka meddelanden som åtgärderna ska tillämpas på. Samma meddelande identifierare som är tillgängliga under förhållanden är också tillgängliga i undantag. Undantag åsidosätta villkor och förhindra att regel åtgärderna tillämpas på ett meddelande, även om meddelandet matchar alla konfigurerade villkor.

- **Åtgärder**: ange vad du vill göra för meddelanden som uppfyller villkoren i regeln och inte matchar något av undantagen. Det finns många tillgängliga åtgärder, till exempel avvisa, ta bort eller omdirigera meddelanden, lägga till fler mottagare, lägga till prefix i meddelandets ämne eller infoga fri skrivningar i meddelande texten.

Mer information om åtgärder för regel för e-postflöde som är tillgängliga i fristående EOP finns i [åtgärder för e-postflödes regler i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).

- **Egenskaper**: ange andra regel inställningar som inte är villkor, undantag eller åtgärder. Till exempel när regeln ska användas, om regeln ska tillämpas eller testas, samt tids perioden då regeln är aktiv.

  Mer information finns i avsnittet [Egenskaper för regel för e-postflöde](#mail-flow-rule-properties) i den här artikeln.

### <a name="multiple-conditions-exceptions-and-actions"></a>Flera villkor, undantag och åtgärder

I följande tabell visas hur flera villkor, villkors värden, undantag och åtgärder hanteras i en regel.

****

|Komponent|Logik|Anteckningar|
|---|---|---|
|Flera villkor|OCH|Ett meddelande måste matcha alla villkor i regeln. Om du behöver matcha ett villkor eller ett annat, Använd separata regler för varje villkor. Om du till exempel vill lägga till samma ansvars friskrivning för meddelanden med bifogade filer och meddelanden som innehåller viss text skapar du en regel för varje villkor. I UK kan du enkelt kopiera en regel.|
|Ett villkor med flera värden|ELLER|Med vissa villkor kan du ange mer än ett värde. Meddelandet måste matcha alla (inte alla) värden. Om till exempel ett e-postmeddelande har aktie pris informationen och **ämnet inkluderar något av dessa** villkor är det konfigurerat att matcha orden contoso eller stock, att villkoret är uppfyllt eftersom ämnet innehåller minst ett av de angivna värdena.|
|Flera undantag|ELLER|Om ett meddelande matchar någon av undantagen, tillämpas inte åtgärderna på meddelandet. Meddelandet behöver inte matcha alla undantagen.|
|Flera åtgärder|OCH|Meddelanden som uppfyller villkoren för en regel får alla åtgärder som anges i regeln. Om åtgärderna **före meddelandets ämne med** och **Lägg till mottagare i rutan hemlig kopia** är markerade, tillämpas båda åtgärderna på meddelandet. <p> Tänk på att vissa åtgärder, till exempel **ta bort meddelandet utan att meddela någon** åtgärd, hindrar efterföljande regler från att tillämpas på ett meddelande. Andra åtgärder som **vidarebefordra meddelandet** tillåter inte ytterligare åtgärder. <p> Du kan också ange en åtgärd för en regel så att efterföljande regler inte tillämpas på meddelandet när den regeln tillämpas.|
|

### <a name="mail-flow-rule-properties"></a>Egenskaper för regel för e-postflöde

I följande tabell beskrivs de regel egenskaper som är tillgängliga i regler för e-postflöde.

****

|Egenskaps namn i UK|Parameter namn i PowerShell|Beskrivning|
|---|---|---|
|**Priority**|_Priority_|Anger i vilken ordning reglerna tillämpas på meddelanden. Standard prioriteten baseras på när regeln skapas (äldre regler har högre prioritet än nyare regler och högre prioritets regler bearbetas före lägre prioritets regler). <p> Du ändrar regel prioriteten i UK genom att flytta regeln uppåt eller nedåt i listan med regler. I PowerShell anger du prioritets nummer (0 är högsta prioritet). <p> Om du till exempel har en regel för att avvisa meddelanden som innehåller ett kreditkorts nummer och en annan som kräver godkännande, vill du att regeln för avslagning ska ske först och sluta tillämpa andra regler.  |
|**Autentiseringsläget**|_Autentiseringsläget_|Du kan ange om du vill att regeln ska börja bearbeta meddelanden direkt, eller om du vill testa regler utan att påverka leveransen av meddelandet (med eller utan hinder för data förlust eller DLP-princip). <p> Princip Tips visar en kort anteckning i Outlook eller Outlook på webben som innehåller information om eventuella policy överträdelser till den person som skapar meddelandet. Mer information finns i **princip Tips**. <p> Mer information om lägen finns i **testa en regel för e-postflöde**.|
|**Aktivera den här regeln på följande datum** <p> **Inaktivera den här regeln på följande datum**|_ActivationDate_ <p> _ExpiryDate_|Anger det datum intervall då regeln är aktiv.|
|Kryss rutan **på** markerad eller inte markerad|Nya regler: _aktive rad_ parameter i **New-TransportRule** cmdlet. <p> Befintliga regler: Använd cmdletarna **Enable-TransportRule** eller **disable-TransportRule** . <p> Värdet visas i egenskapen **State** för regeln.|Du kan skapa en inaktive rad regel och aktivera den när du är redo att testa den. Du kan också inaktivera en regel utan att ta bort den för att behålla inställningarna.|
|**Skjuta upp meddelandet om regel bearbetning inte slutförts**|_RuleErrorAction_|Du kan ange hur meddelandet ska hanteras om regel bearbetningen inte kan slutföras. Regeln ignoreras som standard, men du kan välja att skicka meddelandet igen för bearbetning.|
|**Matcha avsändar adress i meddelande**|_SenderAddressLocation_|Om regeln använder villkor eller undantag som undersöker avsändarens e-postadress kan du leta efter värdet i meddelande huvudet, meddelandets kuvert eller bådadera.|
|**Sluta bearbeta fler regler**|_SenderAddressLocation_|Det här är en åtgärd för regeln men den ser ut som en egenskap i UK. Du kan välja att sluta använda ytterligare regler till ett meddelande när en regel bearbetar ett meddelande.|
|**Anteckningar**|_Anteckningar_|Du kan ange en kommentar om regeln.|
|

## <a name="how-mail-flow-rules-are-applied-to-messages"></a>Hur regler för e-postflöde tillämpas på meddelanden

Alla meddelanden som flödar genom organisationen utvärderas mot de aktiverade reglerna för e-postflöde i organisationen. Regler bearbetas i den ordning som visas på sidan regler för **e-postflöde** \>  i UK, eller  baserat på motsvarande egenskaps värde i PowerShell.

Varje regel erbjuder också alternativet att stoppa bearbetningen av fler regler när regeln matchas. Den här inställningen är viktig för meddelanden som uppfyller villkoren i flera regler för e-postflöde (vilken regel vill du använda i meddelandet? Alla? Bara en?).

### <a name="differences-in-processing-based-on-message-type"></a>Skillnader i bearbetning baserat på meddelande typ

Det finns flera typer av meddelanden som passerar genom en organisation. Följande tabell visar vilka meddelanden som kan bearbetas i regler för e-postflöde.

****

|Typ av meddelande|Kan en regel användas?|
|---|---|
|**Vanliga meddelanden**: meddelanden som innehåller en RTF-, HTML-eller oformaterad textmeddelande text eller en grupp eller en alternativ uppsättning med meddelande texter.|Ja|
|**Office 365 meddelande kryptering**: meddelanden krypterade av Office 365 meddelande kryptering i Office 365. Mer information finns i [kryptering i Office 365](https://docs.microsoft.com/microsoft-365/compliance/encryption).|Regler kan alltid komma åt kuvert rubriker och bearbeta meddelanden baserat på villkor som inspekterar dessa huvuden. <p> Om du vill ha en regel för att kontrol lera eller ändra innehållet i ett krypterat meddelande måste du kontrol lera att transport avkryptering är aktiverat (obligatoriskt eller frivilligt), Standardinställningen är valfri. Mer information finns i [definiera regler för att kryptera eller dekryptera e-postmeddelanden i Office 365](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).|
|**S/MIME-krypterade meddelanden**|Regler kan bara komma åt kuvert rubriker och bearbeta meddelanden baserat på villkor som inspekterar dessa huvuden. <p> Regler med villkor som kräver kontroll av meddelandets innehåll, eller åtgärder som ändrar meddelandets innehåll kan inte behandlas.|
|**RMS-skyddade meddelanden**: meddelanden som hade en AD RMS-(Active Directory Rights Management Services) eller en RMS-princip (Azure Rights Management).|Regler kan alltid komma åt kuvert rubriker och bearbeta meddelanden baserat på villkor som inspekterar dessa huvuden. <p> Om du vill ha en regel för att kontrol lera eller ändra innehållet i ett RMS-skyddat meddelande måste du kontrol lera att transport avkryptering är aktiverat (obligatoriskt eller frivilligt). standardvärdet är inte obligatoriskt).|
|**Rensade meddelanden**: meddelanden som har signerats men inte krypterats.|Ja|
|**UM-meddelanden**: meddelanden som skapas eller bearbetas av Unified Messaging-tjänsten, till exempel röst brev låda, Fax, missade samtals aviseringar och meddelanden som har skapats eller vidarebefordrats med hjälp av Microsoft Outlook Voice Access.|Ja|
|**Anonyma meddelanden**: meddelanden som skickas av anonyma avsändare.|Ja|
|**Läs rapporter**: rapporter som skapas som svar på begäran om Läs kvitton per avsändare. Läs rapporter har en meddelande klass av `IPM.Note*.MdnRead` eller `IPM.Note*.MdnNotRead` .|Ja|
|

## <a name="what-else-should-i-know"></a>Vad mer bör jag veta?

- Egenskapen **version** eller **RuleVersion** för en regel är inte viktig i Exchange Online Protection.

- När du har skapat eller ändrat en regel för e-postflöde kan det ta upp till 30 minuter innan den nya eller uppdaterade regeln läggs till för meddelanden.

## <a name="for-more-information"></a>Mer information

[Använda regler för e-postflöde för att inspektera bifogade filer i Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)

[E-postkryptering i Office 365](../../compliance/email-encryption.md)

[Regel begränsningar för journal, transport och Inkorgen](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#journal-transport-and-inbox-rule-limits)
