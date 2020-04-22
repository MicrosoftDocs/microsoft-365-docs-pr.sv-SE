---
title: Använd avlistningsportalen för att ta bort dig själv från listan över blockerade avsändare
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
description: Får du ett felmeddelande när du försöker skicka ett e-postmeddelande till en mottagare vars e-postadress finns i Microsoft 365? Om du tycker att du inte ska få felmeddelandet kan du använda avlistningsportalen för att ta bort dig själv från listan blockerade avsändare.
ms.openlocfilehash: 39f2c9335f162f26e8bf07a213236e0e0eefef2a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636410"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Använd avlistningsportalen för att ta bort dig själv från listan över blockerade avsändare

Får du ett felmeddelande när du försöker skicka ett e-postmeddelande till en mottagare vars e-postadress finns i Microsoft 365? Om du tycker att du inte ska få felmeddelandet kan du använda avlistningsportalen för att ta bort dig själv från listan blockerade avsändare.

## <a name="what-is-the-blocked-senders-list"></a>Vad är listan med blockerade avsändare?

Microsoft använder listan blockerade avsändare för att skydda sina kunder från skräppost, förfalskning och nätfiskeattacker. Din e-postservers IP-adress, det villa om den adress som e-postservern använder för att identifiera sig på Internet, har taggats som ett potentiellt hot mot Microsoft 365 av olika anledningar. När Microsoft 365 lägger till IP-adressen i listan förhindrar det all ytterligare kommunikation mellan IP-adressen och någon av våra kunder via våra datacenter.

Du vet att du har lagts till i listan när du får ett svar på ett e-postmeddelande som innehåller ett felmeddelande som ser ut ungefär så här:

> 550 5.7.606-649 Tillträde nekad, förbjuden att skicka IP [_IP-adress_]; För att begära borttagning https://sender.office.com/ från denna lista besök och följ anvisningarna. Mer information finns i [Rapporter om utebliven post i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

där _IP-adressen_ är IP-adressen för den dator där e-postservern körs.

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Så här använder du avlistningsportalen för att ta bort dig själv från listan över blockerade avsändare

1. Gå till [https://sender.office.com](https://sender.office.com)i en webbläsare .

2. Följ instruktionerna på sidan. Se till att du använder den e-postadress som felmeddelandet skickades till och den IP-adress som anges i felmeddelandet. Du kan bara ange en e-postadress och en IP-adress per besök.

3. Klicka på **Skicka**.

    Portalen skickar ett e-postmeddelande till den e-postadress som du anger. E-postmeddelandet ser ut ![ungefär så här: Skärmdump av e-post som tas emot när du skickar en begäran via avlisteportalen](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. Klicka på bekräftelselänken i e-postmeddelandet som skickas till dig av avlistningsportalen.

    Detta tar dig tillbaka till avlisteportalen.

5. Klicka på **Avlistnings-IP**i avlistningsportalen .

    När IP-adressen har tagits bort från listan över blockerade avsändare levereras e-postmeddelanden från den IP-adressen till mottagare som använder Microsoft 365. Se därför till att du är säker på att e-post som skickas från den IP-adressen inte kommer att vara stötande eller skadligt. Annars kan IP-adressen blockeras igen.

    > [!NOTE]
    > Det kan ta upp till 24 timmar eller resultaten kan variera kraftigt innan begränsningar tas bort.

Se [Skapa listor över betrodda avsändare i Office 365](create-safe-sender-lists-in-office-365.md) och Skydd för skräppost från [utgående information i Office 365](outbound-spam-controls.md) för att förhindra att IP-åtkomst blir svartlistat.
