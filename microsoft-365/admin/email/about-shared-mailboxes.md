---
title: Om delade postlådor
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Delade post lådor används när flera personer behöver ha åtkomst till samma post låda. Läs mer om vad du behöver veta innan du skapar en delad post låda.
ms.openlocfilehash: cc94ae30edcc7a8307328230989dc4a883732b0e
ms.sourcegitcommit: 7e003ee0a06f61bfb9f80441c3479fa3148afafe
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2020
ms.locfileid: "49568300"
---
# <a name="about-shared-mailboxes"></a>Om delade postlådor

Delade postlådor används när flera personer behöver åtkomst till samma postlåda, t. ex. företagsinformation eller supportens e-postadress, receptionen eller andra funktioner som kan delas av flera personer.

Användare som har behörighet till gruppens postlåda kan skicka som eller skicka för postlådans e-postadress om administratören har gett dig behörighet att göra det. Det här är särskilt användbart för postlådor i hjälp och support eftersom användare kan skicka e-post från "contoso support" eller "Byggnad As reception".

Här är några saker du bör känna till innan du [skapar en delad post låda](create-a-shared-mailbox.md):

- **Licenser:** Den delade post lådan kan lagra upp till 50 GB data utan att du tilldelar en licens till den. Därefter måste du tilldela postlådan en licens för att kunna lagra mer data. Mer information om licensiering för delade post lådor finns i [Exchange Online-begränsningar](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits). När en delad postlåda når lagringsgränsen kommer du att kunna ta emot e-post ett tag till, men du kommer inte att kunna skicka ny e-post. Därefter slutar den att ta emot e-post. De som skickar e-post till postlådan får ett meddelande om utebliven leverans.

- **Användar behörigheter:** Du måste ge användarna behörighet att använda den delade post lådan. Det är bara personer i organisationen som kan använda en delad postlåda.

- **Externa användare:** Du kan inte ge personer utanför företaget (till exempel personer med ett Gmail-konto) åtkomst till din delade post låda. Om du vill kan du också skapa en grupp för Outlook i stället. Mer information finns i [skapa en Microsoft 365-grupp i administrations centret](../create-groups/create-groups.md).

- **Använda med Outlook:** Förutom att använda Outlook på webben från webbläsaren för att komma åt delade post lådor kan du även använda Outlook för iOS-appen eller Outlook för Android-appen. Mer information finns i [lägga till en delad post låda i Outlook Mobile](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f). Ett annat alternativ är att skapa en grupp för den delade post lådan. Mer information finns i [jämföra grupper](../create-groups/compare-groups.md).

- **Kryptering:** Det går inte att kryptera e-post som skickas från en delad post låda. Detta beror på att en delad post låda inte har en egen säkerhets kontext (username/Password), så den kan inte tilldelas en. Om fler än en person är en medlem och de skickar/tar emot e-post som har krypterats med sina egna nycklar kanske andra medlemmar kan läsa e-postmeddelandet och andra kanske inte, beroende på vilken offentlig nyckel e-postmeddelandet krypterades med.

- **Konvertering av post låda:** Du kan konvertera användar post lådor till delade post lådor. Se [Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md).

- **Administratörs roller:** Användare med rollen som global administratör eller Exchange-administratör kan skapa delade post lådor.

- **Abonnemangs krav:** För att skapa en delad post låda måste du prenumerera på ett Microsoft 365 för företag-abonnemang som innehåller e-post (Exchange Online-tjänsten). Microsoft 365-programmen för företag-prenumeration inkluderar inte e-post. Microsoft 365 Business standard inkluderar e-post.

- **Loggar in:** En delad post låda är inte avsedd för direkt inloggning med tillhör ande användar konto. Du bör alltid blockera inloggning för det delade post lådan och behålla det blockerat.

- **För många användare:** När du har för många angivna användare samtidigt åtkomst till en delad post låda kan de ibland inte ansluta till post lådan. I det här fallet kan du överväga att minska antalet användare eller använda olika arbets belastningar, till exempel en Microsoft 365-grupp eller en gemensam mapp.

- **Borttagning av meddelande:** Tyvärr kan du inte förhindra att personer tar bort meddelanden i en delad post låda. Det enda sättet är att skapa en Microsoft 365-grupp i stället för en delad post låda. En grupp i Outlook är som en delad post låda. En jämförelse av de två finns i [jämföra grupper](../create-groups/compare-groups.md). Mer information om grupper finns i [Läs mer om grupper](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).

## <a name="related-articles"></a>Relaterade artiklar

[Skapa en delad postlåda](create-a-shared-mailbox.md)

[Konfigurera en delad postlåda](configure-a-shared-mailbox.md)

[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md)

[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md)

[Lösa problem med delade postlådor](resolve-issues-with-shared-mailboxes.md)
