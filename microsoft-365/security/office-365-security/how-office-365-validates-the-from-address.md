---
title: Så här verifierar EOP från-adressen för att förhindra nätfiske
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
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa om vilka typer av e-postadresser som accepteras eller nekas av Exchange Online Protection (EOP) och Outlook.com för att förhindra nätfiske.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e0afd05c80bb4de665d23b17c7089631dad93c78
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196065"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>Så här verifierar EOP från-adressen för att förhindra nätfiske

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Nät fiske attacker är ett konstant hot mot alla e-postorganisationer. Utöver [falska e-postadresser som inte är förfalskade](anti-spoofing-protection.md)använder angripare ofta värden i från-adressen som bryter mot Internet-standarden. För att förhindra den här typen av nätfiske måste du nu använda Exchange Online Protection (EOP) och Outlook.com för att inkludera en RFC-kompatibel adress enligt beskrivningen i det här avsnittet. Denna tillämpning har Aktiver ATS i november 2017.

**Anmärkningar**:

- Om du regelbundet får e-post från organisationer som har fel format från adresser enligt beskrivningen i det här avsnittet kan du uppmuntra dessa organisationer att uppdatera sina e-postservrar så att de uppfyller moderna säkerhets standarder.

- Motsvarande avsändare (används i skicka-och distributions listor) påverkas inte av de här kraven. Mer information finns i följande blogg inlägg: [Vad innebär det när vi hänvisar till "avsändaren" i ett e-postmeddelande?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).

## <a name="an-overview-of-email-message-standards"></a>En översikt över e-poststandarder

Ett SMTP-standard-e-postmeddelande består av ett *meddelandes kuvert* och meddelande innehåll. Meddelandets kuvert innehåller information som krävs för överföring och leverans av meddelandet mellan SMTP-servrar. Meddelandets innehåll innehåller fält för meddelande rubrik (gemensamt kallat *meddelande huvudet*) och meddelande texten. Meddelandets kuvert beskrivs i [rfc 5321](https://tools.ietf.org/html/rfc5321)och meddelande huvudet beskrivs i [RFC 5322](https://tools.ietf.org/html/rfc5322). Mottagarna kan aldrig se det faktiska meddelandets kuvert eftersom det är genererat av meddelande överföringen och egentligen inte ingår i meddelandet.

- `5321.MailFrom`Adressen (kallas även för **e-post från** adress, P1 avsändare eller kuvert avsändare) är den e-postadress som används i SMTP-överföringen av meddelandet. Den här e-postadressen lagras normalt i huvud fältet för **RETUR-sökväg** i meddelande huvudet (även om det är möjligt för avsändaren att ange en annan e-postadress för **RETUR-sökvägen** ).

- `5322.From`(Kallas även från-adressen eller P2-avsändaren) är e-postadressen i fältet **från** huvud och är avsändarens e-postadress som visas i e-postklienter. Från-adressen är fokus på kraven i det här avsnittet.

Från-adressen definieras i detalj bland flera RFC: er (till exempel RFC 5322 Section 3.2.3, 3,4 och 3.4.1 och [RFC 3696](https://tools.ietf.org/html/rfc3696)). Det finns många variationer för adressering och vad som anses vara giltigt eller ogiltigt. För att det ska vara enkelt rekommenderar vi följande format och definitioner:

`From: "Display Name" <EmailAddress>`

- **Visnings namn**: en valfri fras som beskriver ägaren till e-postadressen.

  - Vi rekommenderar att du alltid omger visnings namnet med citat tecken (") som visas. Om visnings namnet innehåller ett kommatecken _måste_ du omge strängen med dubbla citat tecken enligt RFC 5322.
  - Om from-adressen innehåller ett visnings namn måste EmailAddress-värdet omges av vinkelparenteser (< >) som visas.
  - Microsoft rekommenderar att du infogar ett blank steg mellan visnings namnet och e-postadressen.

- **EmailAddress**: en e-postadress använder formatet `local-part@domain` :

  - **Local-part**: en sträng som identifierar post lådan som är kopplad till adressen. Det här värdet är unikt i domänen. Post lådans användar namn eller GUID används ofta.
  - **domän**: det fullständigt kvalificerade domän namnet (FQDN) för e-postservern som är värd för post lådan som identifieras av den lokala delen av e-postadressen.

  Det här är några ytterligare överväganden för värdet EmailAddress:

  - Endast en e-postadress.
  - Vi rekommenderar att du inte avgränsar vinkelparenteser med blank steg.
  - Ta inte med ytterligare text efter e-postadressen.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>Exempel på giltiga och ogiltiga från adresser

Följande från e-post adresser är giltiga:

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (Rekommenderas inte eftersom det finns blank steg mellan vinkelparenteser och e-postadressen.)

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (Rekommenderas inte eftersom visnings namnet inte omges av dubbla citat tecken.)

Följande från e-postadresser är ogiltiga:

- **Nej från adress**: vissa automatiska meddelanden innehåller inte en adress från. Tidigare, när Microsoft 365 eller Outlook.com tog emot ett meddelande utan en from-adress, lades tjänsten till följande standard från: adress för att göra meddelandets slut produkt:

  `From: <>`

  Meddelanden med en tom adress är nu inte längre godkända.

- `From: Microsoft 365 sender@contoso.com` (Visnings namnet visas, men e-postadressen är inte omgiven av vinkelparenteser.)

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text efter e-postadressen.)

- `From: Sender, Example <sender.example@contoso.com>` (Visnings namnet innehåller ett kommatecken, men omges inte av dubbla citat tecken.)

- `From: "Microsoft 365 <sender@contoso.com>"` (Hela värdet är felaktigt omslutet med dubbla citat tecken.)

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (Visnings namnet visas, men e-postadressen är inte omgiven av vinkelparenteser.)

- `From: Microsoft 365<sender@contoso.com>` (Inget blank steg mellan visnings namnet och vänster vinkel paren tes.)

- `From: "Microsoft 365"<sender@contoso.com>` (Inget blank steg mellan det avslutande dubbla citat tecknet och vänster vinkel paren tes.)

## <a name="suppress-auto-replies-to-your-custom-domain"></a>Förhindra autosvar till din egen domän

Du kan inte använda värdet `From: <>` för att dölja autosvar. Istället måste du skapa en null MX-post för din egen domän. Autosvar (och alla svar) är naturligt undertryckta eftersom det inte finns någon publicerad adress som den svarande servern kan skicka meddelanden till.

- Välj en e-postdomän som inte kan ta emot e-post. Om din primära domän är contoso.com kan du till exempel välja noreply.contoso.com.

- Null MX-posten för den här domänen består av en enda period.

Till exempel:

```text
noreply.contoso.com IN MX .
```

Mer information om hur du konfigurerar MX-poster finns i [Skapa DNS-poster hos en DNS-värd för Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

Mer information om hur du publicerar ett null MX finns i [RFC 7505](https://tools.ietf.org/html/rfc7505).

## <a name="override-from-address-enforcement"></a>Åsidosätt från tvingande adress

Om du vill hoppa över från adress kraven för inkommande e-post kan du använda listan IP-tillåtelse (filtrering) eller regler för e-postflöde (kallas även transport regler) enligt beskrivningen i [skapa säkra avsändare i Microsoft 365](create-safe-sender-lists-in-office-365.md).

Du kan inte åsidosätta adress kraven från Microsoft 365 för utgående e-post. Dessutom tillåter inte Outlook.com åsidosättning av något slag, till och med support.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Andra sätt att förhindra och skydda mot cybercrimes i Microsoft 365

Mer information om hur du kan förstärka din organisation mot nätfiske, skräp post, data brott och andra hot finns i [de 10 viktigaste sätten att skydda Microsoft 365 för företag-abonnemang](../../admin/security-and-compliance/secure-your-business-data.md).
