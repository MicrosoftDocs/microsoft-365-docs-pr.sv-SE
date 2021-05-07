---
title: Villkor, undantag och åtgärder för DLP-princip
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
recommendations: false
description: läs mer om DLP-policyvillkor och undantag
ms.openlocfilehash: 54c66f36e6a4b59147461ad154a4012f62bda77f
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52163025"
---
# <a name="dlp-policy-conditions-exceptions-and-actions"></a>Villkor, undantag och åtgärder för DLP-princip

Villkor och undantag i DLP-principer identifierar känsliga objekt som principen tillämpas på. Åtgärder definierar vad som händer som en förutsättning för att ett undantag uppfylls.

- Villkor definierar vad som ska inkluderas
- Undantag definierar vad som ska undantas.
- Åtgärder definierar vad som händer som en förutsättning för att villkor eller undantag uppfylls
 
De flesta villkor och undantag har en egenskap som stöder ett eller flera värden. Om DLP-principen till exempel tillämpas på Exchange-e-postmeddelanden, kräver avsändaren villkoret Avsändaren är avsändaren av meddelandet.  Vissa villkor har två egenskaper. Till exempel så innehåller **meddelanderubriken** något av dessa ord villkor som kräver en egenskap för att ange fältet för meddelanderubriken, och en andra egenskap som anger vilken text som ska sökas efter i rubrikfältet. Vissa villkor eller undantag har inga egenskaper. Den bifogade filen är **till exempel lösenordsskyddad** och söker bara efter bifogade filer i meddelanden som är lösenordsskyddade.

Åtgärder kräver vanligtvis ytterligare egenskaper. När DLP-principen till exempel omdirigerar ett meddelande måste du ange vart meddelandet omdirigeras. 
<!-- Some actions have multiple properties that are available or required. For example, when the rule adds a header field to the message header, you need to specify both the name and value of the header. When the rule adds a disclaimer to messages, you need to specify the disclaimer text, but you can also specify where to insert the text, or what to do if the disclaimer can't be added to the message. Typically, you can configure multiple actions in a rule, but some actions are exclusive. For example, one rule can't reject and redirect the same message.-->

## <a name="conditions-and-exceptions-for-dlp-policies"></a>Villkor och undantag för DLP-principer

I tabellerna i följande avsnitt beskrivs de villkor och undantag som är tillgängliga i DLP.

- [Avsändare](#senders)
- [Mottagare](#recipients)
- [Meddelandets ämne eller brödtext](#message-subject-or-body)
- [Bifogade filer](#attachments)
- [Meddelanderubriker](#message-headers)
- [Meddelandeegenskaper](#message-properties)

### <a name="senders"></a>Avsändare


|**villkor eller undantag i DLP**  |**villkors-/undantagsparametrar i Microsoft 365 PowerShell** |**egenskapstyp**  |**beskrivning**|
|---------|---------|---------|---------|
|Avsändaren är |villkor: *Från* <br/> undantag: *ExceptIfFrom*      |Adresser |     Meddelanden som skickas av angivna postlådor, e-postanvändare, e-postkontakter Microsoft 365 postgrupper i organisationen.|
|Avsändarens IP-adress är     |villkor: *SenderIPRanges*<br/> undantag: *ExceptIfSenderIPRanges*         |  IPAddressRanges       | Meddelanden där avsändarens IP-adress matchar den angivna IP-adressen eller hamnar inom det angivna IP-adressintervallet.       |
|Avsändaradressen innehåller ord   | villkor: *FromAddressContainsWords* <br/> undantag: *ExceptIfFromAddressContainsWords*        |   Ord      |   Meddelanden som innehåller de angivna orden i avsändarens e-postadress.|
| Avsändaradressen matchar mönster    | villkor: *FromAddressMatchesPatterns* <br/> undantag: *ExceptFromAddressMatchesPatterns*       |      Mönster   |  Meddelanden där avsändarens e-postadress innehåller textmönster som matchar de angivna reguljära uttrycken.  |
|Sender domain is  |  villkor: *SenderDomainIs* <br/> undantag: *ExceptIfSenderDomainIs*       |DomainName         |     Meddelanden där domänen för avsändarens e-postadress matchar det angivna värdet. Om du behöver hitta  avsändardomäner som innehåller den angivna domänen (till exempel en underdomän för en domän) använder du villkoret *FrånAdressmatchningMatchesPatterns*(Avsändare och Avsändare) och anger domänen med syntaxen: ' domain  \. \. com$'.    |
|Avsändaromfattning    | villkor: *FromScope* <br/> undantag: *ExceptIfFromScope*    | UserScopeFrom    |    Meddelanden som skickas av interna eller externa avsändare.    |
|Avsändarens angivna egenskaper omfattar något av dessa ord|villkor: *SenderADAttributeContainsWords* <br/> undantag: *ExceptIfSenderADAttributeContainsWords*|Första egenskapen: `ADAttribute` <p> Andra egenskapen: `Words`|Meddelanden där det angivna Active Directory-attributet för avsändaren innehåller något av de angivna orden.|
|Avsändarens angivna egenskaper matchar dessa textmönster|villkor: *SenderADAttributeMatchesPatterns* <br/> undantag: *ExceptIfSenderADAttributeMatchesPatterns*|Första egenskapen: `ADAttribute` <p> Andra egenskapen: `Patterns`|Meddelanden där det angivna Active Directory-attributet för avsändaren innehåller textmönster som matchar de angivna reguljära uttrycken.|

### <a name="recipients"></a>Mottagare

|**villkor eller undantag i DLP**| **villkors-/undantagsparametrar i Microsoft 365 PowerShell** |    **egenskapstyp** | **beskrivning**|
|---------|---------|---------|---------|
|Mottagaren|  villkor: *SkickatTill* <br/> undantag: *ExceptIfSentTo* | Adresser | Meddelanden där en av mottagarna är den angivna postlådan, e-postanvändaren eller e-postkontakten i organisationen. Mottagarna kan finnas i fälten **Till,** **Kopia** och **Hemlig kopia** i meddelandet.|
|Mottagarens domän är|   villkor: *RecipientDomainIs* <br/> undantag: *ExceptIfRecipientDomainIs* |   DomainName |    Meddelanden där domänen för mottagarens e-postadress matchar det angivna värdet.|
|Mottagaradressen innehåller ord|  villkor: *AnyOfRecipientAddressContainsWords* <br/> undantag: *ExceptIfAnyOfRecipientAddressContainsWords*|  Ord|  Meddelanden som innehåller de angivna orden i mottagarens e-postadress. <br/>**Obs!** Det här villkoret överväger inte meddelanden som skickas till mottagarens proxyadresser. Den matchar bara meddelanden som skickas till mottagarens primära e-postadress.|
|Mottagaradressen matchar mönster| villkor: *AnyOfRecipientAddressMatchesPatterns* <br/> undantag: *ExceptIfAnyOfRecipientAddressMatchesPatterns*| Mönster    |Meddelanden där en mottagares e-postadress innehåller textmönster som matchar de angivna reguljära uttrycken. <br/> **Obs!** Det här villkoret överväger inte meddelanden som skickas till mottagarens proxyadresser. Den matchar bara meddelanden som skickas till mottagarens primära e-postadress.|
|Skickat till medlem av| villkor: *SentToMemberOf* <br/> undantag: *ExceptIfSentToMemberOf*|  Adresser|  Meddelanden som innehåller mottagare som är medlemmar i den angivna distributionsgruppen, e-postaktiverad säkerhetsgrupp eller Microsoft 365 distributionsgrupp. Gruppen kan vara i fälten **Till,** **Kopia** eller **Hemlig kopia** i meddelandet.|

### <a name="message-subject-or-body"></a>Meddelandets ämne eller brödtext

|**villkor eller undantag i DLP** | **villkors-/undantagsparametrar i Microsoft 365 PowerShell** |**egenskapstyp**| **beskrivning**|
|---------|---------|---------|---------|
|Ämne innehåller ord eller fraser| villkor: *SubjectContainsWords* <br/> undantag: *ExceptIf SubjectContainsWords*| Ord   |Meddelanden som innehåller de angivna orden i fältet Ämne.|
|Mönster för ämnesmatchningar|villkor: *SubjectMatchesPatterns* <br/> undantag: *ExceptIf SubjectMatchesPatterns*|Mönster   |Meddelanden där ämnesfältet innehåller textmönster som matchar de angivna reguljära uttrycken.|
|Innehållet innehåller|  villkor: *ContentContainsSensitiveInformation* <br/> undantag *ExceptIfContentContainsSensitiveInformation*| SensitiveInformationTypes|  Meddelanden eller dokument som innehåller känslig information som definierats av DLP-principer (dataförlustskydd).|
| Mönster för matchningar av ämne eller brödtext    | villkor: *SubjectOr AdapterMatchesPatterns* <br/> undantag: *ExceptIfSubjectOrTrappMatchesPatterns*    | Mönster    | Meddelanden där ämnesfältet eller meddelandetexten innehåller textmönster som matchar de angivna reguljära uttrycken.    |
| Ämne eller brödtext innehåller ord    | condition: *SubjectOrWordsContainsWords* <br/> undantag: *ExceptIfSubjectOrWordsContainsWords*    | Ord    | Meddelanden som innehåller angivna ord i ämnesfältet eller meddelandetexten    |


### <a name="attachments"></a>Bifogade filer

|**villkor eller undantag i DLP**| **villkors-/undantagsparametrar i Microsoft 365 PowerShell**| **egenskapstyp**   |**beskrivning**|
|---------|---------|---------|---------|
|Bifogad fil är lösenordsskyddad|villkor: *DocumentIsPasswordProtected* <br/> undantag: *ExceptIfDocumentIsPasswordProtected*|none (ingen)| Meddelanden där en bifogad fil är lösenordsskyddad (och därför inte kan genomsökas). Lösenordsidentifiering fungerar bara Office dokument, .zip och .7z-filer.|
|Filnamnstillägget för den bifogade filen är|villkor: *ContentExtensionMatchesWords* <br/> undantag: *ExceptIfContentExtensionMatchesWords*|  Ord   |Meddelanden där en bifogad fil matchar något av de angivna orden.|
|Det gick inte att skanna innehållet i en e-postbilaga|villkor: *DocumentIsUnsupported* <br/>undantag: *ExceptIf DocumentIsUnsupported*|   Ej a|    Meddelanden där en bifogad fil inte känns igen Exchange Online.|
|Det gick inte att slutföra genomsökning av innehållet i en e-postbilaga|   villkor: *ProcessingLimitExceeded* <br/> undantag: *ExceptIfProcessingLimitExceeded*|    Ej a |Meddelanden där regelmotorn inte kunde slutföra genomsökningen av bifogade filer. Du kan använda detta villkor för att skapa regler som fungerar tillsammans för att identifiera och bearbeta meddelanden där det inte gick att skanna innehållet helt.|
|Dokumentnamnet innehåller ord|villkor: *DocumentNameMatchesWords* <br/> undantag: *ExceptIfDocumentNameMatchesWords* |Ord  |Meddelanden där en bifogad fil matchar något av de angivna orden.|
|Matchningsmönster för dokumentnamn|villkor: *DocumentNameMatchesPatterns* <br/> undantag: *ExceptIfDocumentNameMatchesPatterns*|    Mönster    |Meddelanden där en bifogad fil namn innehåller textmönster som matchar de angivna reguljära uttrycken.|
|Dokumentegenskapen är|villkor: *ContentPropertyContainsWords* <br/> undantag: *ExceptIfContentPropertyContainsWords* |Ord| Meddelanden eller dokument där filtillägget för en bifogad fil matchar något av de angivna orden.|
|Dokumentstorlek är lika med eller större än| villkor: *DocumentSizeOver* <br/> undantag: *ExceptIfDocumentSizeOver*|    Storlek    |Meddelanden där en bifogad fil är större än eller lika med det angivna värdet.|
|Innehållet i en bifogad fil innehåller något av dessa ord| villkor: *DocumentContainsWords* <br/> undantag: *ExceptIfDocumentContainsWords* |`Words`|Meddelanden där en bifogad fil innehåller de angivna orden.|
|Eventuella bifogade filer matchar dessa textmönster|villkor: *DocumentMatchesPatterns* <br/> undantag: *ExceptIfDocumentMatchesPatterns* |`Patterns`|Meddelanden där en bifogad fil innehåller textmönster som matchar de angivna reguljära uttrycken. |

### <a name="message-headers"></a>Meddelanderubriker

|**villkor eller undantag i DLP**| **villkors-/undantagsparametrar i Microsoft 365 PowerShell**| **egenskapstyp**|  **beskrivning**|
|---------|---------|---------|---------|
|Sidhuvudet innehåller ord eller fraser|villkor: *HeaderContainsWords* <br/> undantag: *ExceptIfHeaderContainsWords*|  Hash-tabell  |Meddelanden som innehåller det angivna rubrikfältet och värdet i det rubrikfältet innehåller de angivna orden.|
|Sidhuvud matchar mönster|   villkor: *HeaderMatchesPatterns* <br/> undantag: *ExceptIfHeaderMatchesPatterns*|    Hash-tabell  |Meddelanden som innehåller det angivna rubrikfältet och värdet i det rubrikfältet innehåller de angivna reguljära uttrycken.|

### <a name="message-properties"></a>Meddelandeegenskaper

|**villkor eller undantag i DLP**| **villkors-/undantagsparametrar i Microsoft 365 PowerShell**| **egenskapstyp**   |**beskrivning**|
|---------|---------|---------|---------|
| Med prioritet    | villkor: *WithImportance* <br/> undantag: *ExceptIfWithImportance*    | Prioritet    | Meddelanden som är markerade med angiven prioritetsnivå.    |
| Innehållsteckenuppsättning innehåller ord    | villkor: *ContentCharacterSetContainsWords* <br/> *ExceptIfContentCharacterSetContainsWords*    | CharacterSets    | Meddelanden som har något av de angivna namnen på teckenuppsättningen.    |
| Har avsändarens åsidosättning    | villkor: *HasSenderOverride* <br/> undantag: *ExceptIfHasSenderOverride*    | Ej a    | Meddelanden där avsändaren har valt att åsidosätta en DLP-princip (Data Loss Prevention). Mer information om DLP-principer finns [i Läs mer om skydd mot dataförlust](./dlp-learn-about-dlp.md) |
| Matchningar av meddelandetyper    | villkor: *MessageTypeMatches* <br/> undantag: *ExceptIfMessageTypeMatches*    | MessageType    | Meddelanden av angiven typ.    |
|Meddelandestorleken är större än eller lika med| villkor: *MessageSizeOver* <br/> undantag: *ExceptIfMessageSizeOver* |`Size`|Meddelanden där den totala storleken (meddelande plus bifogade filer) är större än eller lika med det angivna värdet. **Obs!** Storleksbegränsningar för meddelanden för postlådor utvärderas före e-postflödesregler. Ett meddelande som är för stort för en postlåda avvisas innan en regel med detta villkor kan agera på meddelandet.|

## <a name="actions-for-dlp-policies"></a>Åtgärder för DLP-principer

I den här tabellen beskrivs de åtgärder som är tillgängliga i DLP.


|**i DLP**|**åtgärdsparametrar i Microsoft 365 PowerShell**|**egenskapstyp**|**beskrivning**|
|---------|---------|---------|---------|
|Ange sidhuvud|SetHeader|Första egenskapen: *Rubriknamn* </br> Andra egenskapen: *Header Value*|Parametern SetHeader anger en åtgärd för DLP-regeln som lägger till eller ändrar ett rubrikfält och värde i meddelandehuvudet. Den här parametern använder syntaxen "HeaderName:HeaderValue". Du kan ange flera sidhuvudnamn och värdepar avgränsade med kommatecken|
|Ta bort sidhuvud| RemoveHeader| Första egenskapen: *MessageHeaderField*</br> Andra egenskapen: *Sträng*|  Parametern RemoveHeader anger en åtgärd för DLP-regeln som tar bort ett huvudfält från meddelandehuvudet. Den här parametern använder syntaxen "HeaderName" eller "HeaderName:HeaderValue". Du kan ange flera rubriknamn eller sidhuvudnamn och värdepar avgränsade med kommatecken|
|Omdirigera meddelandet till specifika användare|*RedirectMessageTo*|Adresser| Omdirigerar meddelandet till de angivna mottagarna. Meddelandet levereras inte till de ursprungliga mottagarna och inget meddelande skickas till avsändaren eller de ursprungliga mottagarna.|
|Vidarebefordra meddelandet för godkännande till avsändarens chef| Måttlig|Första egenskapen: *ModerateMessageByManager*</br> Andra egenskapen: *Boolesk*|Parametern Måttlig anger en åtgärd för DLP-regeln som skickar e-postmeddelandet till en moderator. Den här parametern använder syntaxen: @{ModerateMessageByManager = <$true \| $false>;|
|Vidarebefordra meddelandet för godkännande till vissa godkännare| Måttlig|Första egenskapen: *ModerateMessageByUser*</br>Andra egenskapen: *Adresser*|Parametern Måttlig anger en åtgärd för DLP-regeln som skickar e-postmeddelandet till en moderator. Den här parametern använder syntaxen: @{ ModerateMessageByUser = @("emailaddress1","emailaddress2",..."emailaddressN")}|
|Lägg till mottagare|AddRecipients|Första egenskapen: *Fält*</br>Andra egenskapen: *Adresser*| Lägger till en eller flera mottagare i fältet Till/Kopia/Hemlig kopia i meddelandet. Den här parametern använder syntaxen: @{<AddToRecipients \| CopyTo \| BlindCopyTo> = "emailaddress"}|
|Lägga till avsändarens chef som mottagare|AddRecipients | Första egenskapen: *AddedManagerAction*</br>Andra egenskapen: *Fält* | Lägger till avsändarens chef i meddelandet som angiven mottagartyp (Till, Kopia, Hemlig kopia) eller omdirigerar meddelandet till avsändarens chef utan att meddela avsändaren eller mottagaren. Den här åtgärden fungerar bara om avsändarens Manager-attribut har definierats i Active Directory. Den här parametern använder syntaxen: @{AddManagerAsRecipientType = "<To \| Cc \| Bcc>"}|    
Lägg till ämne    |PrependSubject    |Sträng    |Lägger till den angivna texten i början av meddelandets ämnesfält. Överväg att använda ett blanksteg eller ett kolon (:) som det sista tecknet i den angivna texten för att skilja det från den ursprungliga ämnestexten.</br>Om du vill förhindra att samma sträng läggs till i meddelanden som redan innehåller texten i ämnet (till exempel svar), lägger du till undantaget "Ämnet innehåller ord" (ExceptIfSubjectContainsWords) till regeln.    
|Använda HTML-ansvarsfriskrivning    |ApplyHtmlDisclaimer    |Första egenskapen: *Text*</br>Andra egenskapen: *Location*</br>Tredje egenskapen: *Reservåtgärd*    |Tillämpar den angivna HTML-ansvarsfriskrivningen på den plats i meddelandet som krävs.</br>Den här parametern använder syntaxen: @{ Text = " " ; Location = <Append \| Prepend>; FallbackAction = <ignorera \| radbyte \|> }
|Ta Meddelandekryptering i Office 365 och rättighetsskydd    | RemoveRMSTemplate | Ej a| Tar bort Office 365 tillämpad på ett e-postmeddelande|
