---
title: Ta bort från listan Spärrade avsändare
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
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig hur du använder list portalen för att ta bort dig själv från listan med spärrade avsändare i Microsoft 365.
ms.openlocfilehash: f4e7bcc13ac6c133880eb0ebe69ba3f724d0a84e
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561429"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Använda avlistningsportalen för att ta bort dig själv från listan med spärrade avsändare

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Får du ett fel meddelande när du försöker skicka ett e-postmeddelande till en mottagare vars e-postadress finns i Microsoft 365? Om du tror att du inte ska få fel meddelandet kan du ta bort dig själv från listan med spärrade avsändare genom att använda List portalen.

## <a name="what-is-the-blocked-senders-list"></a>Vad är listan med spärrade avsändare?

Microsoft använder listan Spärrade avsändare för att skydda sina kunder mot skräp post, förfalskningar och nätfiske-attacker. Din e-postservers IP-adress, det vill säga den adress som din e-postserver använder för att identifiera sig på Internet, har taggats som ett potentiellt hot mot Microsoft 365 på en av många olika anledningar. När Microsoft 365 lägger till IP-adressen i listan förhindrar den all kommunikation mellan IP-adressen och våra kunder via våra data Center.

Du vet att du har lagts till i listan när du får ett svar på ett e-postmeddelande som innehåller ett fel som ser ut ungefär så här:

> 550 5.7.606-649 åtkomst nekad, tillåts inte skickande IP [_IP-adress_]; För att begära borttagning från den här listan <https://sender.office.com/> , gå till och följ instruktionerna. Mer information finns i [rapportera om icke-postleveranser för e-post i Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online).

där  _IP-adress_ är IP-adressen för den dator där e-postservern körs.

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Så här använder du en List Portal för att ta bort dig själv från listan Spärrade avsändare

1. Gå till i en webbläsare <https://sender.office.com> .

2. Följ instruktionerna på sidan. Kontrol lera att du använder den e-postadress som fel meddelandet skickades till och den IP-adress som anges i fel meddelandet. Du kan bara ange en e-postadress och en IP-adress per besök.

3. Klicka på **Skicka**.

    Portalen skickar ett e-postmeddelande till den e-postadress som du anger. E-postmeddelandet ser ut ungefär så här: ![ skärm bild av e-post som tas emot när du skickar en begäran via List portalen](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. Klicka på bekräftelse länken i e-postmeddelandet som skickas till dig via den nedvisande portalen.

    Då kommer du tillbaka till Portal för att avlista.

5. I listan avlistas klickar du på **avlistaa IP**.

    När IP-adressen tas bort från listan med spärrade avsändare levereras e-postmeddelanden från den IP-adressen till mottagarna som använder Microsoft 365. Därför bör du kontrol lera att e-postmeddelandet som skickas från den IP-adressen inte är grovt eller skadligt. Annars kan IP-adressen blockeras igen.

    > [!NOTE]
    > Det kan ta upp till 24 timmar eller resultat kan variera innan restriktioner tas bort.

Se [skapa listor med säkra avsändare i EOP](create-safe-sender-lists-in-office-365.md) och [utgående spam i EOP](outbound-spam-controls.md) för att förhindra att IP blockeras.
