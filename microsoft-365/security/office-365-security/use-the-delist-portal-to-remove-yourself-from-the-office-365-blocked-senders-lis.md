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
description: I den här artikeln får du lära dig hur du använder delist-portalen för att ta bort dig själv från listan Microsoft 365 med spärrade avsändare.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c4488f5e5607d71da35b2921e863fb02195467e2
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207207"
---
# <a name="use-the-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Använda avlistningsportalen för att ta bort dig själv från listan med spärrade avsändare

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gäller för**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender för Office 365 Abonnemang 1 och Abonnemang 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Får du ett felmeddelande när du försöker skicka ett e-postmeddelande till en mottagare vars e-postadress ligger Microsoft 365? Om du anser att du inte borde få felmeddelandet kan du använda delist-portalen för att ta bort dig själv från listan med spärrade avsändare.

## <a name="what-is-the-blocked-senders-list"></a>Vad är listan med spärrade avsändare?

Microsoft använder listan med spärrade avsändare för att skydda sina kunder mot skräppost, förfalskning och nätfiske. E-postserverns IP-adress, det vill säga den adress som din e-postserver använder för att identifiera sig på Internet, har märkts som ett potentiellt hot mot Microsoft 365 av en av flera olika orsaker. När Microsoft 365 lägger till IP-adressen i listan förhindrar det all vidare kommunikation mellan IP-adressen och någon av våra kunder via våra datacenter.

Du vet att du har lagts till i listan när du får ett svar på ett e-postmeddelande som innehåller ett fel som ser ut ungefär så här:

> 550 5.7.606-649 Access denied, banned sending IP [_IP address_]; Om du vill begära borttagning från listan besöker <https://sender.office.com/> du den och följer anvisningarna. Mer information finns i [E-postrapporter om utebliven leverans i Exchange Online.](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

där  _IP-adress_ är IP-adressen för den dator där e-postservern körs.

### <a name="to-use-delist-portal-to-remove-yourself-from-the-blocked-senders-list"></a>Så här tar du bort dig själv från listan med spärrade avsändare med hjälp av delist-portalen

1. Öppna en webbläsare och gå till <https://sender.office.com> .

2. Följ instruktionerna på sidan. Kontrollera att du använder den e-postadress som felmeddelandet skickades till och den IP-adress som anges i felmeddelandet. Du kan bara ange en e-postadress och en IP-adress per besök.

3. Klicka **på Skicka**.

    Portalen skickar ett e-postmeddelande till den e-postadress som du skickar. E-postmeddelandet ser ut ungefär så här: Skärmbild av e-postmeddelandet som tas ![ emot när du skickar en begäran via delist-portalen](../../media/bf13e4f7-f68c-4e46-baa7-b6ab4cfc13f3.png)

4. Klicka på bekräftelselänken i det e-postmeddelande som delisteringsportalen skickar till dig.

    Då kommer du tillbaka till delist-portalen.

5. Klicka på Delist IP i **delist-portalen.**

    När IP-adressen tas bort från listan med spärrade avsändare levereras e-postmeddelanden från IP-adressen till mottagare som använder Microsoft 365. Se därför till att du är säker på att e-post som skickas från den IP-adressen inte är olämplig eller skadlig. Annars kan IP-adressen vara blockerad igen.

    > [!NOTE]
    > Det kan ta upp till 24 timmar eller resultaten kan variera kraftigt innan begränsningarna tas bort.

Se [Skapa listor över betrodda avsändare i EOP-](create-safe-sender-lists-in-office-365.md) och [utgående skräppostskydd](outbound-spam-controls.md) i EOP om du vill förhindra att en IP blockeras.