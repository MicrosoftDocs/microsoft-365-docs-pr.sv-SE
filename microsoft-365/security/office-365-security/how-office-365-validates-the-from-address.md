---
title: Så här validerar EOP Från-adressen för att förhindra nätfiske
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
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: Administratörer kan lära sig om vilka typer av e-postadresser som accepteras eller avvisas av Exchange Online Protection (EOP) och Outlook.com för att förhindra nätfiske.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f16bb9b0af1ca5481437ef253c6d36dd519ff9e2
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209457"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>Så här validerar EOP Från-adressen för att förhindra nätfiske

Nätfiskeattacker är ett ständigt hot mot alla e-postorganisationer. Förutom att använda [falska (förfalskade) avsändar-e-postadresser](anti-spoofing-protection.md)använder angripare ofta värden i den Från-adress som bryter mot internetstandarder. För att förhindra den här typen av nätfiske kräver Exchange Online Protection (EOP) och Outlook.com nu inkommande meddelanden för att inkludera en RFC-kompatibel från-adress enligt beskrivningen i det här avsnittet. Denna verkställighet aktiverades i november 2017.

**Anmärkningar**:

- Om du regelbundet får e-post från organisationer som har felformaterat från-adresser enligt beskrivningen i det här avsnittet uppmuntrar du dessa organisationer att uppdatera sina e-postservrar så att de uppfyller moderna säkerhetsstandarder.

- Det relaterade fältet Avsändare (som används av Skicka för räkning och e-postlistor) påverkas inte av dessa krav. För mer information, se följande blogginlägg: [Vad menar vi när vi hänvisar till "avsändaren" av ett e-postmeddelande?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).

## <a name="an-overview-of-email-message-standards"></a>En översikt över e-postmeddelanden standarder

Ett standardmeddelande för SMTP-meddelanden består av ett *meddelandekuvert* och meddelandeinnehåll. Meddelandekuvertet innehåller information som krävs för att överföra och leverera meddelandet mellan SMTP-servrar. Meddelandeinnehållet innehåller fält för meddelandehuvud (kallas gemensamt *meddelandehuvudet)* och meddelandetexten. Meddelandekuvertet beskrivs i [RFC 5321](https://tools.ietf.org/html/rfc5321)och meddelandehuvudet beskrivs i [RFC 5322](https://tools.ietf.org/html/rfc5322). Mottagarna ser aldrig det faktiska meddelandekuvertet eftersom det genereras av meddelandeöverföringsprocessen och det är faktiskt inte en del av meddelandet.

- `5321.MailFrom`Adressen (kallas även **MAIL FROM-adressen,** P1-avsändaren eller kuvertavsändaren) är den e-postadress som används i SMTP-överföringen av meddelandet. Den här e-postadressen registreras vanligtvis i fältet **Retursökväg** i meddelandehuvudet (även om avsändaren kan ange en annan **e-postadress för retursökväg).**

- `5322.From`(även känd som Från-adressen eller P2-avsändaren) är e-postadressen i fältet **Från-huvud** och är avsändarens e-postadress som visas i e-postklienter. Från-adressen är i fokus för kraven i det här avsnittet.

Från-adressen definieras i detalj i flera RFC (till exempel RFC 5322-avsnitten 3.2.3, 3.4 och 3.4.1 och [RFC 3696](https://tools.ietf.org/html/rfc3696)). Det finns många varianter på adressering och vad som anses giltigt eller ogiltigt. För att hålla det enkelt rekommenderar vi följande format och definitioner:

`From: "Display Name" <EmailAddress>`

- **Visningsnamn**: En valfri fras som beskriver e-postadressens ägare.

  - Vi rekommenderar att du alltid omsluter visningsnamnet med dubbla citattecken (") som visas. Om visningsnamnet innehåller ett kommatecken _måste_ du omge strängen med dubbla citattecken per RFC 5322.
  - Om från-adressen innehåller ett visningsnamn måste värdet e-postadress omges av vinkelparenteser (< >) enligt bilden.
  - Microsoft rekommenderar starkt att du infogar ett mellanslag mellan visningsnamnet och e-postadressen.

- **EmailAddress**: En e-postadress använder `local-part@domain` formatet:

  - **lokal del**: En sträng som identifierar postlådan som är associerad med adressen. Det här värdet är unikt inom domänen. Ofta används postlådeägarens användarnamn eller GUID.
  - **domän:** Det fullständigt kvalificerade domännamnet (FQDN) för e-postservern som är värd för postlådan som identifieras av den lokala delen av e-postadressen.

  Dessa är några ytterligare överväganden för emailAddress värde:

  - Endast en e-postadress.
  - Vi rekommenderar att du inte separerar vinkelfästena med mellanslag.
  - Ta inte med ytterligare text efter e-postadressen.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>Exempel på giltiga och ogiltiga Från-adresser

Följande Från e-postadresser är giltiga:

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >`(Rekommenderas inte eftersom det finns mellanrum mellan vinkelparenteserna och e-postadressen.)

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>`(Rekommenderas inte eftersom visningsnamnet inte omges av dubbla citattecken.)

Följande Från-e-postadresser är ogiltiga:

- **Nej från-adress**: Vissa automatiska meddelanden innehåller inte en Från-adress. När Microsoft 365 eller Outlook.com fått ett meddelande utan Från-adress har tjänsten tidigare lagt till följande standard från: adress för att göra meddelandet slutprodukt:

  `From: <>`

  Meddelanden med en tom Från-adress accepteras inte längre.

- `From: Microsoft 365 sender@contoso.com`(Visningsnamnet finns, men e-postadressen omges inte av vinkelparenteser.)

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)`(Text efter e-postadressen.)

- `From: Sender, Example <sender.example@contoso.com>`(Visningsnamnet innehåller ett kommatecken, men omges inte av dubbla citattecken.)

- `From: "Microsoft 365 <sender@contoso.com>"`(Hela värdet omges felaktigt av dubbla citattecken.)

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com`(Visningsnamnet finns, men e-postadressen omges inte av vinkelparenteser.)

- `From: Microsoft 365<sender@contoso.com>`(Inget blanksteg mellan visningsnamnet och det vänstra vinkelfästet.)

- `From: "Microsoft 365"<sender@contoso.com>`(Inget blanksteg mellan det avslutande dubbla citattecknet och det vänstra vinkelfästet.)

## <a name="suppress-auto-replies-to-your-custom-domain"></a>Undertrycka autosvar på din anpassade domän

Du kan inte använda värdet `From: <>` för att undertrycka autosvar. I stället måste du ställa in en null MX-post för din anpassade domän. Autosvar (och alla svar) undertrycks naturligtvis eftersom det inte finns någon publicerad adress som den svarande servern kan skicka meddelanden till.

- Välj en e-postdomän som inte kan ta emot e-post. Om din primära domän till exempel är contoso.com kan du välja noreply.contoso.com.

- Null MX-posten för den här domänen består av en enda period.

Till exempel:

```text
noreply.contoso.com IN MX .
```

Mer information om hur du konfigurerar MX-poster finns i [Skapa DNS-poster hos alla DNS-värdar för Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

Mer information om hur du publicerar ett null MX finns i [RFC 7505](https://tools.ietf.org/html/rfc7505).

## <a name="override-from-address-enforcement"></a>Åsidosätt från adresskontroll

Om du vill kringgå kraven på från-adress för inkommande e-post kan du använda IP Allow List (anslutningsfiltrering) eller regler för e-postflöde (kallas även transportregler) enligt beskrivningen i [Skapa listor över betrodda avsändare i Microsoft 365](create-safe-sender-lists-in-office-365.md).

Du kan inte åsidosätta kraven på från-adress för utgående e-post som du skickar från Microsoft 365. Dessutom kommer Outlook.com inte tillåta åsidosättningar av något slag, även genom stöd.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Andra sätt att förebygga och skydda mot it-brott i Microsoft 365

Mer information om hur du kan stärka din organisation mot nätfiske, skräppost, dataintrång och andra hot finns på [topp 10 sätt att skydda Microsoft 365 för affärsplaner](../../admin/security-and-compliance/secure-your-business-data.md).
