---
title: Använd avlistningsportalen för att ta bort dig själv från listan blockerade avsändare i Office 365
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
description: Får du ett felmeddelande när du försöker skicka ett e-postmeddelande till en mottagare vars e-postadress finns i Office 365? Om du anser att du inte ska ta emot felmeddelandet kan du använda avlistningsportalen för att ta bort dig själv från listan med blockerade avsändare i Office 365.
ms.openlocfilehash: 3e131addb391ecbf90d74ad4fdfa65b802c5e1ac
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808982"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-list"></a>Använd avlistningsportalen för att ta bort dig själv från listan blockerade avsändare i Office 365

Får du ett felmeddelande när du försöker skicka ett e-postmeddelande till en mottagare vars e-postadress finns i Office 365? Om du anser att du inte ska ta emot felmeddelandet kan du använda avlistningsportalen för att ta bort dig själv från listan med blockerade avsändare i Office 365.

## <a name="what-is-the-office-365-blocked-senders-list"></a>Vad är listan över blockerade avsändare i Office 365?

Microsoft använder listan blockerade avsändare för att skydda sina kunder från skräppost, förfalskning och nätfiskeattacker. E-postserverns IP-adress, det vill fram till att den adress som e-postservern använder för att identifiera sig på Internet, har taggats som ett potentiellt hot mot Office 365 av en mängd olika orsaker. När Office 365 lägger till IP-adressen i listan förhindrar den all ytterligare kommunikation mellan IP-adressen och någon av våra kunder via våra datacenter.

Du vet att du har lagts till i listan när du får ett svar på ett e-postmeddelande som innehåller ett fel som ser ut ungefär så här:

> 550 5.7.606-649 Access nekas, förbjuden att skicka IP [_IP-adress_]; För att begära borttagning https://sender.office.com/ från denna lista besök och följ anvisningarna. Mer information finns i [Rapporter om utebliven leverans via e-post i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

där _IP-adress_ är IP-adressen för den dator där e-postservern körs.

### <a name="to-use-the-office-365-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Så här använder du avlistningsportalen för Office 365 för att ta bort dig själv från listan blockerade avsändare

1. I en webbläsare går [https://sender.office.com](https://sender.office.com)du till .

2. Följ instruktionerna på sidan. Kontrollera att du använder den e-postadress som felmeddelandet skickades till och ip-adressen som anges i felmeddelandet. Du kan bara ange en e-postadress och en IP-adress per besök.

3. Klicka på **Skicka**.

    Portalen skickar ett e-postmeddelande till den e-postadress som du anger. E-postmeddelandet kommer att se ![ut ungefär så här: Skärmdump av e-post som tas emot när du skickar en begäran via avlistningsportalen](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. Klicka på bekräftelselänken i e-postmeddelandet som skickas till dig av avlistningsportalen.

    Detta tar dig tillbaka till avlistportalen.

5. Klicka på **Avlista IP**i avlistningsportalen .

    När IP-adressen har tagits bort från listan blockerade avsändare levereras e-postmeddelanden från den IP-adressen till mottagare som använder Office 365. Så, se till att du är säker på att e-post som skickas från den IP-adressen inte kommer att vara kränkande eller skadligt; Annars kan IP-adressen blockeras igen.

    > [!NOTE]
    > Det kan ta upp till 24 timmar eller resultaten kan variera kraftigt innan begränsningar tas bort.

Läs om [Hur du förhindrar att riktiga e-postmeddelanden markeras som skräppost i Office 365](prevent-email-from-being-marked-as-spam.md ) och Styra [utgående skräppost i Office 365](outbound-spam-controls.md) för att förhindra att IP svartlistas.
