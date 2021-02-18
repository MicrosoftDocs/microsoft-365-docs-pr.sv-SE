---
title: Ta bort dig själv från listan med spärrade avsändare
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/18/2016
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0bcecdd4-3343-4cc0-9e58-e19d4de515e8
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: I den här artikeln får du lära dig hur du använder delist-portalen för att ta bort dig själv från listan med spärrade avsändare i Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c11fced30ef52315ecb44dda51e6825d36b57c7e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287527"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Använda avlistningsportalen för att ta bort dig själv från listan med spärrade avsändare

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Får du ett felmeddelande när du försöker skicka ett e-postmeddelande till en mottagare vars e-postadress finns i Microsoft 365? Om du tror att du inte bör få felmeddelandet kan du använda delist-portalen för att ta bort dig själv från listan med spärrade avsändare.

## <a name="what-is-the-blocked-senders-list"></a>Vad är listan med spärrade avsändare?

Microsoft använder listan med spärrade avsändare för att skydda sina kunder mot skräppost, förfalskning och nätfiske. E-postserverns IP-adress, det vill säga den adress som e-postservern använder för att identifiera sig själv på Internet, har märkts som ett potentiellt hot mot Microsoft 365 av en mängd olika orsaker. När Microsoft 365 lägger till IP-adressen i listan förhindrar det all vidare kommunikation mellan IP-adressen och någon av våra kunder via våra datacenter.

Du vet att du har lagts till i listan när du får ett svar på ett e-postmeddelande som innehåller ett fel som ser ut ungefär så här:

> 550 5.7.606-649 Access denied, banned sending IP [_IP address_]; Om du vill begära borttagning från den här listan går <https://sender.office.com/> du till och följer anvisningarna. Mer information finns i [e-postrapporter om utebliven leverans i Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

där  _IP-adressen_ är IP-adressen för den dator där e-postservern körs.

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Så här använder du delist-portalen för att ta bort dig själv från listan över spärrade avsändare

1. Öppna en webbläsare och gå till <https://sender.office.com> .

2. Följ instruktionerna på sidan. Kontrollera att du använder e-postadressen som felmeddelandet skickades till och den IP-adress som anges i felmeddelandet. Du kan bara ange en e-postadress och en IP-adress per besök.

3. Klicka **på Skicka.**

    Portalen skickar ett e-postmeddelande till den e-postadress som du uppser. E-postmeddelandet ser ut ungefär så här: Skärmbild av e-postmeddelandet som tas emot ![ när du skickar en begäran via delist-portalen](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. Klicka på bekräftelselänken i e-postmeddelandet som delistingportalen skickar till dig.

    Då kommer du tillbaka till delist-portalen.

5. Klicka på Delist IP i **delist-portalen.**

    När IP-adressen tas bort från listan med spärrade avsändare levereras e-postmeddelanden från IP-adressen till mottagare som använder Microsoft 365. Kontrollera därför att du är säker på att e-post som skickas från IP-adressen inte är olämplig eller skadlig. Annars kan IP-adressen blockeras igen.

    > [!NOTE]
    > Det kan ta upp till 24 timmar, eller resultaten kan variera kraftigt innan begränsningarna tas bort.

Se [Skapa listor över betrodda avsändare i EOP](create-safe-sender-lists-in-office-365.md) och skydd mot utgående skräppost i [EOP](outbound-spam-controls.md) för att förhindra att en IP blockeras.
