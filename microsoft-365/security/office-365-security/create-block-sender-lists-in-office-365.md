---
title: Skapa listor med spärrade avsändare
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150s
description: Administratörer kan läsa mer om tillgängliga och rekommenderade alternativ för att blockera inkommande meddelanden i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a9ee0a026e33bf07bb929607b8eed9078d0b6e4c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207195"
---
# <a name="create-blocked-sender-lists-in-eop"></a>Skapa spärrade avsändarlistor i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor finns det flera sätt att blockera e-post från oönskade avsändare. De här alternativen omfattar Spärrade avsändare i Outlook, listor över spärrade avsändare eller spärrade domäner i principer för skydd mot skräppost, Exchange-e-postflödesregler (kallas även transportregler) och IP-blockeringslistan (anslutningsfiltrering). Sammantaget kan du tänka på de här alternativen som _spärrade avsändarlistor._

Den bästa metoden för att blockera avsändare varierar beroende på hur omfattande den är. För en enskild användare kan rätt lösning vara Spärrade avsändare i Outlook. För många användare är ett av de andra alternativen mer lämpligt. Följande alternativ rangordnas både efter påverkansomfång och bredd. Listan går från smal till bred, men läs *mer för fullständiga* rekommendationer.

1. Spärrade avsändare i Outlook (listan Spärrade avsändare som lagras i varje postlåda)

2. Listor över spärrade avsändare eller blockerade domäner (principer mot skräppost)

3. E-postflödesregler

4. IP-blockeringslistan (anslutningsfiltrering)

> [!NOTE]
> Du kan använda blockeringsinställningar för hela organisationen för att hantera falska negativa meddelanden (missad skräppost), men du bör också skicka dessa meddelanden till Microsoft för analys. Hanteringen av falska negativa resultat genom att använda blockeringslistor ökar avsevärt det administrativa arbetet. Om du använder blockeringslistor för att undvika missad skräppost måste du ha ämnet [Rapportera meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md) när du är redo.

Du har däremot flera alternativ för att alltid tillåta e-post från vissa källor med _hjälp av listor över betrodda avsändare._ Mer information finns i [Skapa listor över betrodda avsändare](create-safe-sender-lists-in-office-365.md).

## <a name="email-message-basics"></a>Grundläggande information om e-postmeddelanden

Ett vanligt SMTP-e-postmeddelande består av ett *meddelandekuvert* och meddelandeinnehåll. Meddelandekuvertet innehåller information som behövs för att överföra och leverera meddelandet mellan SMTP-servrarna. Meddelandeinnehållet innehåller fält för meddelanderubriker (kallas gemensamt *för meddelanderubriken)* och meddelandets brödtext. Meddelandekuvertet beskrivs i RFC 5321 och meddelanderubriken beskrivs i RFC 5322. Mottagarna ser aldrig det faktiska meddelandekuvertet eftersom det genereras vid meddelandeöverföringen och det är faktiskt inte en del av meddelandet.

- Adressen (kallas även MAIL FROM address, P1 sender, or envelope sender) är den e-postadress som används vid `5321.MailFrom` SMTP-överföringen  av meddelandet. Den här **e-postadressen** registreras vanligtvis i huvudfältet Retursökväg i meddelandehuvudet (även om det är möjligt för avsändaren att ange en annan **e-postadress** för retursökväg). Om meddelandet inte kan levereras är det mottagaren för rapporten om utebliven leverans (kallas även för NDR- eller icke-leveransmeddelande).

- (Kallas även från-adressen eller P2-avsändaren) är e-postadressen i fältet Från rubrik och är avsändarens e-postadress som visas i `5322.From` e-postklienter.  

Ofta är `5321.MailFrom` `5322.From` adresserna och desamma (kommunikation mellan två personer). Men när e-post skickas åt någon annan kan adresserna vara annorlunda.

Listor över spärrade avsändare och listor över blockerade domäner i principer mot skräppost i EOP kontrollerar både `5321.MailFrom` `5322.From` adresserna och. Spärrade avsändare i Outlook använder bara `5322.From` adressen.

## <a name="use-outlook-blocked-senders"></a>Använda spärrade avsändare i Outlook

När bara ett litet antal användare har fått oönskad e-post kan användare eller administratörer lägga till avsändaradresserna i listan Spärrade avsändare i postlådan. Instruktioner finns i Konfigurera [inställningar för skräppost i Exchange Online-postlådor.](configure-junk-email-settings-on-exo-mailboxes.md)

När meddelanden blockeras på grund av en användares lista med spärrade avsändare innehåller rubrikfältet **X-Forefront-Antispam-Report** `SFV:BLK` värdet.

> [!NOTE]
> Om de oönskade meddelandena är nyhetsbrev från en känd och igenkännbar källa, är ett annat alternativ att sluta prenumerera på e-postmeddelandet för att hindra användaren från att ta emot meddelandena.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Använda listor över spärrade avsändare eller spärrade domäner

När flera användare påverkas är omfattningen bredare, så nästa bästa alternativ är listor över spärrade avsändare eller blockerade domäner i principer som är skräppostskyddade. Meddelanden från avsändare i listorna markeras som Skräppost och åtgärden som  du har konfigurerat för skräppostfiltrets bedömning vidtas på meddelandet. Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).

Maxgränsen för dessa listor är cirka 1 000 poster.

## <a name="use-mail-flow-rules"></a>Använda e-postflödesregler

Om du behöver blockera meddelanden som skickas till specifika användare eller i hela organisationen kan du använda e-postflödesregler. E-postflödesregler är mer flexibla än blockeringslistor för avsändarlistor och spärrade avsändardomänlistor eftersom de även kan söka efter nyckelord eller andra egenskaper i oönskade meddelanden.

Oavsett de villkor eller undantag som du använder för att identifiera meddelanden kan du konfigurera åtgärden för att ange SCL (Spam Confidence Level) för meddelandet till 9, vilket markerar meddelandet som skräppost med hög **konfidens.** Mer information finns i Använda [e-postflödesregler för att ange SCL i meddelanden.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

> [!IMPORTANT]
> Det är enkelt att skapa  regler som är alltför aggressiva, så det är viktigt att du bara identifierar de meddelanden som du vill blockera med mycket specifika villkor. Se även till att aktivera granskning av regeln och testa resultatet av regeln så att allt fungerar som förväntat.

## <a name="use-the-ip-block-list"></a>Använda blockeringslistan för IP-adresser

När det inte går att använda något av de  andra alternativen för att spärra en avsändare bör du bara använda IP-blockeringslistan i principen för anslutningsfilter. Mer information finns i [konfigurera policy för anslutningsfilter](configure-the-connection-filter-policy.md). Det är viktigt att ha så många blockerade IP-adresser som möjligt, så vi rekommenderar inte att du blockerar hela *IP-adressintervall.*

Du *bör* särskilt undvika att lägga till IP-adressintervall som tillhör konsumenttjänster (till exempel outlook.com) eller delad infrastruktur och även kontrollera att du granskar listan över blockerade IP-adresser som en del av regelbundet underhåll.
