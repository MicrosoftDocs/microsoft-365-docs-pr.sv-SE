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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150s
description: Administratörer kan läsa om tillgängliga och önskade alternativ för att blockera inkommande meddelanden i Exchange Online Protection (EOP).
ms.openlocfilehash: 9b676f96ccdff8be1fa49841a9e0ce44bb59964c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827319"
---
# <a name="create-blocked-sender-lists-in-eop"></a>Skapa listor spärrade avsändare i EOP

I Microsoft 365-organisationer med post lådor i Exchange Online eller fristående Exchange Online Protection (EOP)-organisationer utan Exchange Online-postlådor kan EOP blockera e-post från oönskade avsändare. De här alternativen inkluderar Outlook-blockerade avsändare, spärrade avsändare eller blockerade domän listor i principer för skräp post, Exchange mail flöde-regler (kallas även transport regler) och IP-blockeringslistan (anslutnings filter). Tillsammans kan du se dessa alternativ som _spärrade avsändare_.

Den bästa metoden för att blockera avsändare beror på islagsnas omfattning. För en enskild användare kan rätt lösning vara blockerade Outlook-avsändare. För många användare är ett av de andra alternativen mer lämpligt. Följande alternativ rangordnas efter omfattning och bredd. Listan går från smal till bred, men *läser de specifika* rekommendationerna.

1. Outlook blockerade avsändare (listan med spärrade avsändare som lagras i varje post låda)

2. Spärrade avsändare eller blockerade domän listor (principer för skräp post)

3. Regler för e-postflöde

4. IP-blockeringslistan (anslutnings filter)

> [!NOTE]
> Du kan använda spärr inställningar för hela organisationen för att adressera falska negativa (missade skräp post), men du bör även skicka dessa meddelanden till Microsoft för analys. Om du hanterar falska Negatives genom att använda blockerade listor blir administrationen betydligt bättre. Om du använder blockeringslistan för att sätta på missade skräp post måste du hålla informationen om [meddelanden och filer till Microsoft](report-junk-email-messages-to-microsoft.md) när du är klar.

I motsats till det finns flera alternativ som gör att e-post alltid tillåts från specifika källor med _säkra avsändar listor_. Mer information finns i [Skapa listor över betrodda avsändare](create-safe-sender-lists-in-office-365.md).

## <a name="email-message-basics"></a>Grunderna i e-postmeddelanden

Ett SMTP-standard-e-postmeddelande består av ett *meddelandes kuvert* och meddelande innehåll. Meddelandets kuvert innehåller information som krävs för överföring och leverans av meddelandet mellan SMTP-servrar. Meddelandets innehåll innehåller fält för meddelande rubrik (gemensamt kallat *meddelande huvudet*) och meddelande texten. Meddelandets kuvert beskrivs i RFC 5321 och meddelande huvudet beskrivs i RFC 5322. Mottagarna kan aldrig se det faktiska meddelandets kuvert eftersom det är genererat av meddelande överföringen och egentligen inte ingår i meddelandet.

- `5321.MailFrom`Adressen (kallas även för **e-post från** adress, P1 avsändare eller kuvert avsändare) är den e-postadress som används i SMTP-överföringen av meddelandet. Den här e-postadressen lagras normalt i huvud fältet för **RETUR-sökväg** i meddelande huvudet (även om det är möjligt för avsändaren att ange en annan e-postadress för **RETUR-sökvägen** ). Om det inte går att leverera meddelandet är det mottagaren för rapporten om utebliven leverans (kallas även för en NDR eller ett studs meddelande).

- `5322.From`(Kallas även **från** -adressen eller P2-avsändaren) är e-postadressen i fältet **från** huvud och är avsändarens e-postadress som visas i e-postklienter.

Ofta är de `5321.MailFrom` och `5322.From` adresserna samma (person-till-person-kommunikation). Men när e-post skickas åt någon annan kan adresser vara olika.

Blockerade avsändare och blockerade domän listor i en policy för borttagning av skräp post i EOP inspektera både `5321.MailFrom` `5322.From` adresserna och. Spärrade avsändare i Outlook använder endast `5322.From` adressen.

## <a name="use-outlook-blocked-senders"></a>Använda spärrade avsändare i Outlook

När bara ett fåtal användare får oönskad e-post kan användare eller administratörer lägga till avsändarens e-postadresser i listan Spärrade avsändare i post lådan. Anvisningar finns i [Konfigurera inställningar för skräp post i Exchange Online-postlådor](configure-junk-email-settings-on-exo-mailboxes.md).

När meddelanden blockeras på grund av en användares lista med spärrade avsändare, innehåller fältet **X-antispam – rapport** huvud värdet `SFV:BLK` .

> [!NOTE]
> Om de oönskade meddelandena är nyhets brev från en seriös och igenkännlig källa är det ett annat alternativ att avbryta användaren från att ta emot meddelanden.

## <a name="use-blocked-sender-lists-or-blocked-domain-lists"></a>Använda spärrade avsändare listor eller blockerade domän listor

När flera användare påverkas är omfattningen bredare, så det bästa alternativet är blockerade avsändare listor eller blockerade domän listor i principer för skräp post. Meddelanden från avsändare i listorna markeras som **skräp post**och åtgärden som du har konfigurerat för **skräp post** filtret Verdict tas med i meddelandet. Mer information finns i [Konfigurera principer för skräppostskydd](configure-your-spam-filter-policies.md).

Högsta tillåtna gräns för dessa listor är ungefär 1000 poster.

## <a name="use-mail-flow-rules"></a>Använda regler för e-postflöde

Om du behöver spärra meddelanden som skickas till specifika användare eller i hela organisationen kan du använda regler för e-postflöde. Regler för e-postflöde är mer flexibla än spärrade avsändare eller spärrade avsändare domän listor eftersom de också kan leta efter nyckelord eller andra egenskaper i de oönskade meddelandena.

Oavsett vilka villkor eller undantag som du använder för att identifiera meddelanden kan du konfigurera åtgärden för att ställa in meddelandets säkerhets nivå (SCL) för meddelandet till 9, vilket markerar meddelandet som **skräp post**. Mer information finns i [använda regler för e-postflöde för att ange SCL i meddelanden](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

> [!IMPORTANT]
> Det är enkelt att skapa regler *som är mycket* aggressiva, så det är viktigt att du bara identifierar de meddelanden som du vill blockera genom att använda specifika villkor. Kontrol lera också att du aktiverar granskning för regeln och testar resultatet av regeln för att se till att allting fungerar som förväntat.

## <a name="use-the-ip-block-list"></a>Använd IP-blockeringslistan

När det inte går att använda något av de andra alternativen för att blockera en avsändare ska du *bara* använda IP-blockeringslistan i princip för anslutnings filter. Mer information finns i [konfigurera policy för anslutningsfilter](configure-the-connection-filter-policy.md). Det är viktigt att du behåller det minsta antalet blockerade IP-adresser så att hela IP-adressintervall *inte* rekommenderas.

Du bör *särskilt* undvika att lägga till IP-adressintervall som tillhör konsument tjänster (till exempel Outlook.com) eller delade infrastrukturer, samt att se till att du granskar listan med blockerade IP-adresser som en del av vanligt underhåll.
