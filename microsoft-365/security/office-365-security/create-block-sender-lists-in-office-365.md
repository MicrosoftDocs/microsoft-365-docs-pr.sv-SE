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
description: Administratörer kan läsa mer om de tillgängliga och rekommenderade alternativen för att blockera inkommande meddelanden i Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5c95b49db811807a0cb46dce5363b8ae2dbe5602
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287287"
---
# <a name="create-blocked-sender-lists-in-eop"></a>Skapa listor med spärrade avsändare i EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I Microsoft 365-organisationer med postlådor i Exchange Online eller fristående EOP-organisationer (Exchange Online Protection) utan Exchange Online-postlådor erbjuder EOP flera sätt att blockera e-post från oönskade avsändare. De här alternativen omfattar Spärrade avsändare i Outlook, listor över spärrade avsändare och spärrade domäner i principer för skydd mot skräppost, e-postflödesregler i Exchange (kallas även transportregler) och IP-blockeringslistan (anslutningsfiltrering). Sammantaget kan du se de här alternativen som _listor över spärrade avsändare._

Den bästa metoden för att blockera avsändare varierar beroende på omfattningen av påverkan. För en enskild användare kan rätt lösning vara Spärrade avsändare i Outlook. För många användare är ett av de andra alternativen mer lämpligt. Följande alternativ rangordnas både efter påverkansomfång och bredd. Listan går från smal till bred, men *läs mer om fullständiga* rekommendationer.

1. Spärrade avsändare i Outlook (listan Spärrade avsändare som lagras i varje postlåda)

2. Listor över spärrade avsändare och domänlistor (principer mot skräppost)

3. E-postflödesregler

4. IP-blockeringslistan (anslutningsfiltrering)

> [!NOTE]
> Du kan använda blockeringsinställningar för hela organisationen för att hantera falska negativa tal (missad skräppost), men du bör också skicka dessa meddelanden till Microsoft för analys. Om du hanterar falska negativa resultat med hjälp av blockeringslistor ökar det administrativa arbetet avsevärt. Om du använder blockeringslistor för att undvika missad skräppost måste du ha ämnet Rapportera [meddelanden och filer](report-junk-email-messages-to-microsoft.md) på Microsoft redo.

Du har däremot flera alternativ för att alltid tillåta e-post från vissa källor med hjälp _av listor över betrodda avsändare._ Mer information finns i [Skapa listor över betrodda avsändare](create-safe-sender-lists-in-office-365.md).

## <a name="email-message-basics"></a>Grundläggande information om e-postmeddelanden

Ett vanligt SMTP-e-postmeddelande består av ett *meddelandekuvert* och meddelandeinnehåll. Meddelandekuvertet innehåller information som behövs för att överföra och leverera meddelandet mellan SMTP-servrar. Meddelandeinnehållet innehåller fält för meddelanderubriker (kallas gemensamt *för meddelanderubriken)* och meddelandets brödtext. Meddelandekuvertet beskrivs i RFC 5321 och meddelanderubriken beskrivs i RFC 5322. Mottagarna ser aldrig det faktiska meddelandekuvertet eftersom det genereras av meddelandeöverföringsprocessen och det är faktiskt inte en del av meddelandet.

- Adressen (kallas även MAIL `5321.MailFrom` **FROM-adress,** P1-avsändare eller kuvertavsändare) är den e-postadress som används vid meddelandets SMTP-överföring. Den här **e-postadressen** registreras vanligtvis i huvudfältet för retursökväg i meddelandehuvudet (även om det är möjligt för avsändaren att ange en annan **e-postadress** för retursökväg). Om meddelandet inte kan levereras är det mottagaren för rapporten om utebliven leverans (kallas även NDR-rapport eller icke-leveransk leverans).

- Den (kallas även från-adress eller P2-avsändare) är e-postadressen i fältet Från rubrik och är avsändarens e-postadress som visas i `5322.From` e-postklienter.  

Ofta är `5321.MailFrom` `5322.From` adresserna och adresserna desamma (kommunikation mellan två personer). Men när e-post skickas åt någon annan kan adresserna vara olika.

Listor över spärrade avsändare och listor över blockerade domäner i principer mot skräppost i EOP kontrollerar både `5321.MailFrom` adresserna och `5322.From` adresserna. Spärrade avsändare i Outlook använder bara `5322.From` adressen.

## <a name="use-outlook-blocked-senders"></a>Använda spärrade avsändare i Outlook

När bara ett litet antal användare har fått oönskad e-post kan användare eller administratörer lägga till avsändaradresserna i listan Spärrade avsändare i postlådan. Instruktioner finns i Konfigurera [skräppostinställningar för Exchange Online-postlådor.](configure-junk-email-settings-on-exo-mailboxes.md)

Om meddelanden blockeras på grund av en användares lista över spärrade avsändare innehåller **rubrikfältet X-Forefront-Antispam-Report** `SFV:BLK` värdet.

> [!NOTE]
> Om de oönskade meddelandena är nyhetsbrev från en känd och igenkännbar källa är ett annat alternativ att avsluta prenumerationen från e-postmeddelandet för att hindra användaren från att ta emot meddelandena.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Använda listor över spärrade avsändare eller domänlistor som är blockerade

När flera användare påverkas är omfattningen bredare, så det nästa bästa alternativet är listor över spärrade avsändare eller listor över blockerade domäner i principer som är skräppostskyddade. Meddelanden från avsändare i listorna markeras som skräppost och den åtgärd  som du har konfigurerat för skräppostfiltrets bedömning tas på meddelandet. Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).

Maxgränsen för dessa listor är ungefär 1 000 poster.

## <a name="use-mail-flow-rules"></a>Använda e-postflödesregler

Om du behöver blockera meddelanden som skickas till specifika användare eller i hela organisationen kan du använda e-postflödesregler. E-postflödesregler är mer flexibla än blockeringslistor för avsändarlistor eller domänlistor för spärrade avsändare eftersom de även kan söka efter nyckelord eller andra egenskaper i oönskade meddelanden.

Oavsett vilka villkor eller undantag du använder för att identifiera meddelandena kan du konfigurera åtgärden för att ställa in SCL (Spam Confidence Level) för meddelandet till 9, vilket markerar meddelandet som skräppost med hög **konfidens.** Mer information finns i Använda [e-postflödesregler för att ange SCL i meddelanden.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

> [!IMPORTANT]
> Det är enkelt att skapa  regler som är alltför aggressiva, så det är viktigt att du bara identifierar de meddelanden som du vill blockera med mycket specifika villkor. Se också till att aktivera granskning av regeln och testa resultatet av regeln för att säkerställa att allt fungerar som förväntat.

## <a name="use-the-ip-block-list"></a>Använda ip-blockeringslistan

När det inte går att använda något av de  andra alternativen för att spärra en avsändare bör du bara använda IP-blockeringslistan i principen för anslutningsfilter. Mer information finns i [konfigurera policy för anslutningsfilter](configure-the-connection-filter-policy.md). Det är viktigt att ha så få blockerade IP-adresser som möjligt,  så du bör inte blockera hela IP-adressintervallen.

Du bör *särskilt* undvika att lägga till IP-adressintervall som tillhör konsumenttjänster (till exempel outlook.com) eller delad infrastruktur och även kontrollera att du granskar listan över blockerade IP-adresser som en del av regelbundet underhåll.
