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
description: Administratörer kan läsa mer om vilka typer av e-postadresser som godkänns eller avvisas av Exchange Online Protection (EOP) och e Outlook.com för att förhindra nätfiske.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7c2cbec49082fbded857dde13f73516fd3e0fd5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167521"
---
# <a name="how-eop-validates-the-from-address-to-prevent-phishing"></a>Hur EOP verifierar från-adressen för att förhindra nätfiske

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Nätfiskeattacker är ett konstant hot mot e-postorganisationen. Förutom att använda falska [(förfalskade)](anti-spoofing-protection.md)avsändaradresser använder attacker ofta värden i från-adressen som bryter mot Internetstandarder. För att förhindra den här typen av nätfiske kräver Exchange Online Protection (EOP) och Outlook.com nu att inkommande meddelanden inkluderar en RFC-kompatibel från-adress enligt beskrivningen i den här artikeln. Den här tillämpning aktiverades i november 2017.

**Anmärkningar**:

- Om du regelbundet får e-post från organisationer som har felformulär från adresser enligt beskrivningen i den här artikeln bör du uppmuntra dessa organisationer att uppdatera sina e-postservrar så att de uppfyller moderna säkerhetsstandarder.

- Det relaterade avsändarfältet (som används av Skicka för och distributionslistor) påverkas inte av dessa krav. Mer information finns i följande blogginlägg: Vad innebär det när vi [refererar till "avsändaren" av ett e-postmeddelande?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/).

## <a name="an-overview-of-email-message-standards"></a>En översikt över standarder för e-postmeddelanden

Ett vanligt SMTP-e-postmeddelande består av ett *meddelandekuvert* och meddelandeinnehåll. Meddelandekuvertet innehåller information som behövs för att överföra och leverera meddelandet mellan SMTP-servrar. Meddelandeinnehållet innehåller fält för meddelanderubriker (kallas gemensamt *för meddelanderubriken)* och meddelandets brödtext. Meddelandekuvertet beskrivs i [RFC 5321](https://tools.ietf.org/html/rfc5321)och meddelanderubriken beskrivs i [RFC 5322.](https://tools.ietf.org/html/rfc5322) Mottagarna ser aldrig det faktiska meddelandekuvertet eftersom det genereras av meddelandeöverföringsprocessen och det är faktiskt inte en del av meddelandet.

- Adressen (kallas även MAIL `5321.MailFrom` **FROM-adress,** P1-avsändare eller kuvertavsändare) är den e-postadress som används vid meddelandets SMTP-överföring. Den här **e-postadressen** registreras vanligtvis i huvudfältet för retursökväg i meddelandehuvudet (även om avsändaren kan ange en annan **e-postadress** för retursökvägen).

- Den (kallas även från-adress eller P2-avsändare) är e-postadressen i fältet Från rubrik och är avsändarens e-postadress som visas i `5322.From` e-postklienter.  Från-adressen är fokus på kraven i den här artikeln.

Från-adressen definieras i detalj i flera offertförfrågningar (till exempel avsnitten 3.2.3, 3.4 och 3.4.1 och [RFC 3696).](https://tools.ietf.org/html/rfc3696) Det finns många varianter på adressering och vad som anses vara giltigt eller ogiltigt. För att hålla det enkelt rekommenderar vi följande format och definitioner:

`From: "Display Name" <EmailAddress>`

- **Visningsnamn:** En valfri fras som beskriver e-postadressens ägare.

  - Vi rekommenderar att du alltid omsluter visningsnamnet med dubbla citattecken (") som på bilden. Om visningsnamnet innehåller ett kommatecken måste _strängen_ omges med dubbla citattecken per RFC 5322.
  - Om från-adressen innehåller ett visningsnamn måste värdet för E-postadress omges av vinkelparenteser (< >) som visas.
  - Microsoft rekommenderar starkt att du infogar ett blanksteg mellan visningsnamnet och e-postadressen.

- **EmailAddress:** En e-postadress har `local-part@domain` formatet:

  - **lokaldel:** En sträng som identifierar postlådan som är kopplad till adressen. Det här värdet är unikt inom domänen. Ofta används postlådans ägares användarnamn eller GUID.
  - **domän:** Det fullständigt kvalificerade domännamnet (FQDN) för e-postservern som är värd för postlådan som identifieras av den lokala delen av e-postadressen.

  Det här är ytterligare saker att tänka på när det gäller värdet för EmailAddress:

  - Endast en e-postadress.
  - Vi rekommenderar att du inte avgränsar vinkelparenteserna med blanksteg.
  - Inkludera inte ytterligare text efter e-postadressen.

## <a name="examples-of-valid-and-invalid-from-addresses"></a>Exempel på giltiga och ogiltiga från-adresser

Följande från e-postadresser är giltiga:

- `From: sender@contoso.com`

- `From: <sender@contoso.com>`

- `From: < sender@contoso.com >` (Rekommenderas inte eftersom det finns blanksteg mellan vinkelparenteserna och e-postadressen.)

- `From: "Sender, Example" <sender.example@contoso.com>`

- `From: "Microsoft 365" <sender@contoso.com>`

- `From: Microsoft 365 <sender@contoso.com>` (Rekommenderas inte eftersom visningsnamnet inte omges av dubbla citattecken.)

Följande från e-postadresser är ogiltiga:

- **Ingen av från-adress:** Vissa automatiska meddelanden innehåller inte en från-adress. Tidigare när Microsoft 365 eller Outlook.com fick ett meddelande utan från-adress lade tjänsten till följande standardadress från: så att meddelandet kan levereras:

  `From: <>`

  Nu accepteras inte längre meddelanden med en tom från-adress.

- `From: Microsoft 365 sender@contoso.com` (Visningsnamnet finns, men e-postadressen omges inte av vinkelparenteser.)

- `From: "Microsoft 365" <sender@contoso.com> (Sent by a process)` (Text efter e-postadressen.)

- `From: Sender, Example <sender.example@contoso.com>` (Visningsnamnet innehåller ett kommatecken, men omges inte av dubbla citattecken.)

- `From: "Microsoft 365 <sender@contoso.com>"` (Hela värdet omges felaktigt av dubbla citattecken.)

- `From: "Microsoft 365 <sender@contoso.com>" sender@contoso.com` (Visningsnamnet finns, men e-postadressen omges inte av vinkelparenteser.)

- `From: Microsoft 365<sender@contoso.com>` (Inget blanksteg mellan visningsnamnet och den vänstra vinkelparentesen.)

- `From: "Microsoft 365"<sender@contoso.com>` (Inget blanksteg mellan det avslutande dubbla citattecknet och den vänstra vinkelparentesen.)

## <a name="suppress-auto-replies-to-your-custom-domain"></a>Ignorera automatiska svar på din anpassade domän

Du kan inte använda värdet för `From: <>` att ignorera automatiska svar. I stället måste du konfigurera en null MX-post för din anpassade domän. Autosvar (och alla svar) utelämnas naturligt eftersom det inte finns någon publicerad adress som svarsservern kan skicka meddelanden till.

- Välj en e-postdomän som inte kan ta emot e-post. Om din primära domän till exempel är contoso.com kan du välja noreply.contoso.com.

- NULL MX-posten för den här domänen består av en enda punkt.

Till exempel:

```text
noreply.contoso.com IN MX .
```

Mer information om hur du inställningar för MX-poster finns i [Skapa DNS-poster hos valfri DNS-värd för Microsoft 365.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)

Mer information om hur du publicerar en null MX finns [i RFC 7505.](https://tools.ietf.org/html/rfc7505)

## <a name="override-from-address-enforcement"></a>Åsidosätt tillämpning av från adress

Om du vill åsidosätta kraven för från-adress för inkommande e-post kan du använda IP-listan över tillåtna adresser (anslutningsfiltrering) eller e-postflödesregler (kallas även transportregler) enligt beskrivningen i Skapa listor över betrodda avsändare i [Microsoft 365.](create-safe-sender-lists-in-office-365.md)

Du kan inte åsidosätta kraven för från-adress för utgående e-post som du skickar från Microsoft 365. Dessutom kommer Outlook.com att inte tillåta åsidosättningar av något slag, även via support.

## <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-microsoft-365"></a>Andra sätt att förhindra och skydda mot cyberbrott i Microsoft 365

Mer information om hur du kan stärka din organisation mot nätfiske, skräppost, databrott och andra hot finns i de 10 främsta sätten att skydda [Microsoft 365 för företag-abonnemang.](../../admin/security-and-compliance/secure-your-business-data.md)
