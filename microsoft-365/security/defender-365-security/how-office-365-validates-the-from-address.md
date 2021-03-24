---
title: Hur EOP verifierar från-adressen för att förhindra nätfiske
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
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Administratörer kan läsa mer om vilka typer av e-postadresser som godkänns eller avvisas av Exchange Online Protection (EOP) och Outlook.com för att förhindra nätfiske.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5a02313bf8c36fe0be91340e421c69a8dc5c0842
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071394"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>Hur EOP verifierar från-adressen för att förhindra nätfiske

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nätfiskeattacker är ett konstant hot mot e-postorganisation. Förutom att använda [förfalskade (förfalskade)](anti-spoofing-protection.md)avsändares e-postadresser använder attacker ofta värden i från-adressen som bryter mot Internetstandarder. För att förhindra den här typen av nätfiske kräver nu Exchange Online Protection (EOP) och Outlook.com inkommande meddelanden en RFC-kompatibel från-adress enligt beskrivningen i den här artikeln. Tillämpning av den här funktionen aktiverades i november 2017.

**Anmärkningar**:

- Om du regelbundet får e-post från organisationer som har felaktigt använda från-adresser enligt beskrivningen i den här artikeln bör du uppmuntra dessa organisationer att uppdatera sina e-postservrar så att de uppfyller moderna säkerhetsstandarder.

- Det relaterade avsändarfältet (som används av Skicka för och distributionslistor) påverkas inte av dessa krav. Mer information finns i följande blogginlägg: Vad betyder vi när vi refererar till avsändaren av ett [e-postmeddelande?](/archive/blogs/tzink/what-do-we-mean-when-we-refer-to-the-sender-of-an-email).

## <a name="an-overview-of-email-message-standards"></a>En översikt över standarder för e-postmeddelanden

Ett vanligt SMTP-e-postmeddelande består av ett *meddelandekuvert* och meddelandeinnehåll. Meddelandekuvertet innehåller information som behövs för att överföra och leverera meddelandet mellan SMTP-servrarna. Meddelandeinnehållet innehåller fält för meddelanderubriker (kallas gemensamt *för meddelanderubriken)* och meddelandets brödtext. Meddelandekuvertet beskrivs i [RFC 5321](https://tools.ietf.org/html/rfc5321)och meddelanderubriken beskrivs i [RFC 5322.](https://tools.ietf.org/html/rfc5322) Mottagarna ser aldrig det faktiska meddelandekuvertet eftersom det genereras vid meddelandeöverföringen och det är faktiskt inte en del av meddelandet.

- Adressen (kallas även MAIL FROM address, P1 sender, or envelope sender) är den e-postadress som används vid `5321.MailFrom` SMTP-överföringen  av meddelandet. Den här **e-postadressen** registreras vanligtvis i huvudfältet Retursökväg i meddelandehuvudet (även om det är möjligt för avsändaren att ange en annan **e-postadress** för retursökväg).

- (Kallas även från-adressen eller P2-avsändaren) är e-postadressen i fältet Från rubrik och är avsändarens e-postadress som visas i `5322.From` e-postklienter.  Från-adressen är fokus på kraven i den här artikeln.

Från-adressen definieras i detalj på flera offertförfrågningar (till exempel avsnitten 3.2.3, 3.4, 3.4 och 3.4.1 och [RFC 3696)](https://tools.ietf.org/html/rfc3696)i från. Det finns många varianter på adressering och vad som anses vara giltigt eller ogiltigt. För att göra det enkelt rekommenderar vi följande format och definitioner:

`From: "Display Name" <EmailAddress>`

- **Visningsnamn:** En valfri fras som beskriver e-postadressens ägare.

  - Vi rekommenderar att du alltid omsluter visningsnamnet med dubbla citattecken (") enligt bilden. Om visningsnamnet innehåller ett kommatecken måste du _omge_ strängen med dubbla citattecken per RFC 5322.
  - Om från-adressen innehåller ett visningsnamn måste värdet e-postadress omges av vinkelparenteser (< >) på det sätt som visas.
  - Microsoft rekommenderar starkt att du infogar ett blanksteg mellan visningsnamnet och e-postadressen.

- **EmailAddress:** En e-postadress har följande `local-part@domain` format:

  - **lokaldel:** En sträng som identifierar postlådan som är kopplad till adressen. Det här värdet är unikt inom domänen. Ofta används postlådans ägares användarnamn eller GUID.
  - **domän:** Det fullständigt kvalificerade domännamnet (FQDN) för e-postservern som är värd för postlådan som identifieras av den lokala delen av e-postadressen.

  Det här är ytterligare saker att tänka på när det gäller värdet för EmailAddress:

  - Endast en e-postadress.
  - Vi rekommenderar att du inte avgränsar vinkelparenteserna med blanksteg.
  - Inkludera inte ytterligare text efter e-postadressen.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>Exempel på giltiga och ogiltiga från adresser

Följande Från e-postadresser är giltiga:

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (Rekommenderas inte eftersom det finns blanksteg mellan vinkelparenteserna och e-postadressen.)

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (Rekommenderas inte eftersom visningsnamnet inte omges av dubbla citattecken.)

Följande Från e-postadresser är ogiltiga:

- **Ingen av från-adress:** Vissa automatiska meddelanden innehåller inte en Från-adress. Tidigare när Microsoft 365 eller Outlook.com fick ett meddelande utan en Från-adress lade tjänsten till följande standardadress från: så att meddelandet kan levereras:

  `From: <>`

  Nu accepteras inte längre meddelanden med en tom Från-adress.

- `From: Microsoft 365 sender@contoso.com` (Visningsnamnet finns, men e-postadressen omges inte av vinkelparenteser.)

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text efter e-postadressen.)

- `From: Sender, Example <sender.example@contoso.com>` (Visningsnamnet innehåller ett kommatecken, men omges inte av dubbla citattecken.)

- `From: "Microsoft 365 <sender@contoso.com>"` (Hela värdet omges felaktigt av dubbla citattecken.)

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (Visningsnamnet finns, men e-postadressen omges inte av vinkelparenteser.)

- `From: Microsoft 365<sender@contoso.com>` (Inget blanksteg mellan visningsnamnet och den vänstra vinkelparentesen.)

- `From: "Microsoft 365"<sender@contoso.com>` (Inget blanksteg mellan det avslutande dubbla citattecknet och den vänstra vinkelparentesen.)

## <a name="suppress-auto-replies-to-your-custom-domain"></a>Ignorera autosvar i din egen domän

Du kan inte använda värdet för `From: <>` att ignorera autosvar. I stället måste du konfigurera en null MX-post för din anpassade domän. Autosvar (och alla svar) utelämnas naturligt eftersom det inte finns någon publicerad adress som svarsservern kan skicka meddelanden till.

- Välj en e-postdomän som inte kan ta emot e-post. Om din primära domän till exempel är contoso.com kan du välja noreply.contoso.com.

- MX-posten för den här domänen består av en enda punkt.

Ett exempel:

```text
noreply.contoso.com IN MX .
```

Mer information om hur du konfigurerar MX-poster finns i [Skapa DNS-poster på vilken DNS-värd som helst för Microsoft 365.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)

Mer information om hur du publicerar en null MX finns [i RFC 7505.](https://tools.ietf.org/html/rfc7505)

## <a name="override-from-address-enforcement"></a>Åsidosätt från tillämpning av adress

Om du vill åsidosätta kraven för från-adress för inkommande e-post kan du använda listan över tillåtna IP-adresser (anslutningsfiltrering) eller e-postflödesregler (kallas även transportregler) enligt beskrivningen i Skapa listor över betrodda avsändare i [Microsoft 365.](create-safe-sender-lists-in-office-365.md)

Du kan inte åsidosätta kraven för Från-adress för utgående e-post som du skickar från Microsoft 365. Dessutom kan Outlook.com åsidosättningar av något slag, även via support.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Andra sätt att förhindra och skydda mot cyberbrott i Microsoft 365

Mer information om hur du kan stärka organisationen mot nätfiske, skräppost, databrott och andra hot finns i De 10 bästa sätten att skydda [Microsoft 365 för företag-abonnemang.](../../admin/security-and-compliance/secure-your-business-data.md)