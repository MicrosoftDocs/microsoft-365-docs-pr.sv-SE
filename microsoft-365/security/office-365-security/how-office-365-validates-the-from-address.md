---
title: Så här validerar Office 365 från-adressen för att förhindra nätfiske
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 10/11/2017
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
description: För att förhindra nätfiske kräver Office 365 och Outlook.com nu RFC-efterlevnad för Från:-adresser.
ms.openlocfilehash: 6459faa22f29017568747b84bbd2935aad6763d1
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812239"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a>Så här validerar Office 365 från-adressen för att förhindra nätfiske

Office 365- och Outlook.com e-postkonton får allt fler nätfiskeattacker. En teknik phishers användning är att skicka meddelanden som har värden för Från: adress som inte är kompatibla med [RFC 5322](https://tools.ietf.org/html/rfc5322). Från: adressen kallas också adressen 5322.From. För att förhindra den här typen av nätfiske kräver Office 365 och Outlook.com meddelanden som tas emot av tjänsten för att inkludera en RFC-kompatibel Från:-adress enligt beskrivningen i den här artikeln.

> [!NOTE]
> Informationen i den här artikeln kräver att du har en grundläggande förståelse för det allmänna formatet för e-postadresser. Mer information finns i [RFC 5322](https://tools.ietf.org/html/rfc5322) (särskilt avsnitten 3.2.3, 3.4 och 3.4.1), [RFC 5321](https://tools.ietf.org/html/rfc5321), samt [RFC 3696](https://tools.ietf.org/html/rfc3696). Den här artikeln handlar om policyverkställighet för adressen 5322.From. Den här artikeln handlar inte om adressen 5321.MailFrom.

Tyvärr finns det fortfarande några äldre e-postservrar på Internet som fortsätter att skicka "legitima" e-postmeddelanden som har en saknad eller felaktig från: adress. Om du regelbundet får e-post från organisationer som använder dessa äldre system, uppmuntra dessa organisationer att uppdatera sina e-postservrar för att följa moderna säkerhetsstandarder.

Microsoft kommer att börja rulla ut efterlevnaden av de principer som beskrivs i den här artikeln den 9 november 2017.

## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a>Så här tillämpar Office 365 användningen av en giltig Från:-adress för att förhindra nätfiskeattacker

Office 365 gör ändringar i hur den tillämpar användningen av från:-adressen i meddelanden som den tar emot för att bättre skydda dig från nätfiskeattacker. I den här artikeln:

- [Alla meddelanden måste innehålla en giltig Från:-adress](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)

- [Format för från: adressen om du inte inkluderar ett visningsnamn](how-office-365-validates-the-from-address.md#FormatNoDisplayName)

- [Format för från: adressen om du inkluderar ett visningsnamn](how-office-365-validates-the-from-address.md#FormatDisplayName)

- [Ytterligare exempel på giltiga och ogiltiga Från: adresser](how-office-365-validates-the-from-address.md#Examples)

- [Undertryck automatiskt svar på din anpassade domän utan att bryta från: -principen](how-office-365-validates-the-from-address.md#SuppressAutoReply)

- [Åsidosättoffice 365 från: ta itu med tvingande principer](how-office-365-validates-the-from-address.md#Override)

- [Andra sätt att förebygga och skydda mot it-brott i Office 365](how-office-365-validates-the-from-address.md#OtherProtection)

Skicka på uppdrag av en annan användare påverkas inte av denna förändring, för mer information, läs Terry Zink blogg "[Vad menar vi när vi hänvisar till "avsändare" av ett mail?](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)".

### <a name="all-messages-must-include-a-valid-from-address"></a>Alla meddelanden måste innehålla en giltig Från:-adress
<a name="MustIncludeFromAddress"> </a>

Vissa automatiska meddelanden innehåller inte en från:-adress när de skickas. Tidigare har tjänsten Outlook.com lagt till följande standardadress Från: adress till meddelandet för att göra det sluten:

```
From: <>
```

Från och med den 9 november 2017 kommer Office 365 att distribuera ändringar i sina datacenter och e-postservrar som kommer att tillämpa en ny regel där meddelanden utan från: adress inte längre accepteras av Office 365 eller Outlook.com. I stället måste alla meddelanden som tas emot av Office 365 redan innehålla en giltig Från:-adress. Annars skickas meddelandet till mapparna Skräppost eller Borttaget i Outlook.com och Office 365.

### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a>Syntaxöversikt: Giltigt format för adressen Från: för Office 365
<a name="SyntaxOverviewFromAddress"> </a>

Formatet för värdet för från:-adressen definieras i detalj över flera rFC:er. Det finns många varianter på adressering och vad som kan anses giltigt eller ogiltigt. För att hålla det enkelt rekommenderar Microsoft att du använder följande format och definitioner:

```
From: "displayname " <emailaddress >
```

Där:

- (Valfritt)  *visningsnamn* är en fras som beskriver ägaren till e-postadressen. Detta kan till exempel vara ett mer användarvänligt namn för att beskriva avsändaren än namnet på postlådan. Det är valfritt att använda ett visningsnamn. Om du väljer att använda ett visningsnamn rekommenderar Microsoft dock att du alltid omger det inom citattecken enligt bilden.

- (Obligatoriskt)  *e-postadressen* består av:

  ```
  local-part @domain
  ```

    Där:

  - (Obligatoriskt)  *lokal del* är en sträng som identifierar postlådan som är associerad med adressen. Detta är unikt inom domänen. Ofta används postlådans ägares användarnamn eller GUID som värde för den lokala delen.

  - (Obligatoriskt)  *domänär* det fullständigt kvalificerade domännamnet (FQDN) för e-postservern som är värd för den postlåda som identifieras av den lokala delen av e-postadressen.

### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a>Format för från: adressen om du inte inkluderar ett visningsnamn
<a name="FormatNoDisplayName"> </a>

En korrekt formaterad från: adress som inte innehåller ett visningsnamn innehåller bara en enda e-postadress med eller utan vinkelfästen. Microsoft rekommenderar att du inte separerar vinkelfästena med blanksteg. Dessutom ska du inte inkludera något efter e-postadressen.

Följande exempel är giltiga:

```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

Följande exempel är giltigt men rekommenderas inte eftersom det innehåller blanksteg mellan vinkelfästena och e-postadressen:

```
From: < sender@contoso.com >
```

Följande exempel är ogiltigt eftersom det innehåller text efter e-postadressen:

```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a>Format för från: adressen om du inkluderar ett visningsnamn
<a name="FormatDisplayName"> </a>

För Från: adresser som innehåller ett värde för visningsnamnet gäller följande regler:

- Om avsändarens adress innehåller ett visningsnamn och visningsnamnet innehåller ett kommatecken måste visningsnamnet bifogas inom citattecken. Till exempel:

    Följande exempel är giltigt:

  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    Följande exempel är ogiltigt:

  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    Om du inte omsluter visningsnamnet med citattecken om visningsnamnet innehåller ett kommatecken är ogiltigt enligt RFC 5322.

    Som bästa praxis, sätta citattecken runt visningsnamnet oavsett om det finns ett kommatecken i visningsnamnet eller inte.

- Om avsändarens adress innehåller ett visningsnamn måste e-postadressen bifogas inom vinkelparentes.

    Som bäst är att Microsoft rekommenderar att du infogar ett mellanslag mellan visningsnamnet och e-postadressen.

### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a>Ytterligare exempel på giltiga och ogiltiga Från: adresser
<a name="Examples"> </a>

- Giltig:

  ```
  From: "Office 365" <sender@contoso.com>
  ```

- Ogiltig. E-postadressen är inte innesluten med vinkelfästen:

  ```
  From: Office 365 sender@contoso.com
  ```

- Giltig, men rekommenderas inte. Visningsnamnet är inte citattecken. Som bästa praxis, alltid sätta citattecken runt visningsnamnet:

  ```
  From: Office 365 <sender@contoso.com>
  ```

- Ogiltig. Allt omges inom citattecken, inte bara visningsnamnet:

  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- Ogiltig. Det finns inga vinkelfästen runt e-postadressen:

  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- Ogiltig. Det finns inget utrymme mellan visningsnamnet och vänster vinkelfäste:

  ```
  From: Office 365<sender@contoso.com>
  ```

- Ogiltig. Det finns inget utrymme mellan det avslutande citattecknet runt visningsnamnet och den vänstra vinkelfästet.

  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a>Undertryck automatiskt svar på din anpassade domän utan att bryta från: -principen
<a name="SuppressAutoReply"> </a>

Med den nya Från: principverkställighet, kan \< \> du inte längre använda Från: för att undertrycka auto-svar. I stället måste du ställa in en null MX-post för din anpassade domän.

Posten e-postväxlare (MX) är en resurspost i DNS som identifierar e-postservern som tar emot e-post för domänen. Autosvar (och alla svar) undertrycks naturligt eftersom det inte finns någon publicerad adress som svarsservern kan skicka meddelanden till.

När du konfigurerar en null MX-post för din anpassade domän:

- Välj en domän som meddelanden ska skickas från och som inte accepterar (tar emot) e-post. Om din primära domän till exempel är contoso.com kan du välja noreply.contoso.com.

- Ställ in null MX-posten för domänen. En null MX-post består till exempel av en enda punkt:

  ```
  noreply.contoso.com IN MX .
  ```

Mer information om hur du publicerar en null MX finns i [RFC 7505](https://tools.ietf.org/html/rfc7505).

### <a name="overriding-the-office-365-from-address-enforcement-policy"></a>Åsidosättoffice 365 från: ta itu med tvingande principer
<a name="Override"> </a>

När lanseringen av den nya principen är klar kan du bara kringgå den här principen för inkommande e-post som du får från Office 365 med någon av följande metoder:

- IP tillåter listor

- Regler för e-postflöde online

Microsoft rekommenderar starkt att man åsidosätter tillämpningen av från:-principen. Genom att åsidosätta den här policyn kan din organisations risk för exponering för skräppost, nätfiske och andra it-brott ökas.

Du kan inte åsidosätta den här principen för utgående e-post som du skickar i Office 365. Dessutom tillåter Outlook.com inte åsidosättningar av något slag, inte ens genom stöd.

### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a>Andra sätt att förebygga och skydda mot it-brott i Office 365
<a name="OtherProtection"> </a>

Mer information om hur du kan stärka din organisation mot nätbrott som nätfiske, skräppost, dataintrång och andra hot finns i [Metodtips för säkerhet för Office 365](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data).

## <a name="related-topics"></a>Relaterade ämnen

[Meddelanden på grund av bakåtspridning och EOP](backscatter-messages-and-eop.md)
