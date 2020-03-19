---
title: Om delade postlådor
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
description: Delade postlådor används när flera personer behöver åtkomst till samma postlåda. Läs om vad du behöver veta innan du skapar en delad postlåda.
ms.openlocfilehash: 3bb78cc272a1920d9eab92aff50a14e345dce2e1
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2020
ms.locfileid: "42811222"
---
# <a name="about-shared-mailboxes"></a>Om delade postlådor

Delade postlådor används när flera personer behöver åtkomst till samma postlåda, t. ex. företagsinformation eller supportens e-postadress, receptionen eller andra funktioner som kan delas av flera personer.

Användare som har behörighet till gruppens postlåda kan skicka som eller skicka för postlådans e-postadress om administratören har gett dig behörighet att göra det. Detta är särskilt användbart för hjälp och support postlådor eftersom användarna kan skicka e-post från "Contoso Support" eller "Building A Reception Desk.

Innan du [skapar en delad postlåda](create-a-shared-mailbox.md)finns det några saker du bör veta.

- **Licenser:** Din delade postlåda kan lagra upp till 50 GB data utan att du tilldelar den en licens. Därefter måste du tilldela postlådan en licens för att kunna lagra mer data. Mer information om licensiering av delad postlåda finns i [Exchange Online Limits](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits). När en delad postlåda når lagringsgränsen kommer du att kunna ta emot e-post ett tag till, men du kommer inte att kunna skicka ny e-post. Därefter slutar den att ta emot e-post. De som skickar e-post till postlådan får ett meddelande om utebliven leverans.

- **Användarbehörigheter:** Du måste ge användarna behörighet (medlemskap) för att kunna använda den delade postlådan. Det är bara personer i organisationen som kan använda en delad postlåda.

- **Externa användare:** Du kan inte ge personer utanför ditt företag (till exempel personer med ett Gmail-konto) åtkomst till din delade postlåda. Om du vill göra detta kan du överväga att skapa en grupp för Outlook i stället. Mer information finns i [Skapa en Office 365-grupp i administrationscentret](../create-groups/create-groups.md).

-  **Använd med Outlook:** Förutom att använda Outlook på webben från webbläsaren för att komma åt delade postlådor kan du också använda Outlook för iOS-appen eller Outlook för Android-appen. Mer information finns i <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Lägga till en delad postlåda i Outlook mobile</a>. Ett annat alternativ är att skapa en grupp för din delade postlåda. Mer information finns i [Jämför grupper](../create-groups/compare-groups.md).  

- **Kryptering:** Du kan inte kryptera e-post som skickas från en delad postlåda. Detta beror på att en delad postlåda inte har en egen säkerhetskontext (användarnamn/lösenord) så att den inte kan tilldelas en nyckel. Om fler än en person är medlem, och de skickar / ta emot e-postmeddelanden som de krypterade med sina egna nycklar, kanske andra medlemmar kan läsa e-postmeddelandet och andra kanske inte, beroende på vilken offentlig nyckel e-postmeddelandet krypterades med.

- **Konvertering av postlådefiler:** Du kan konvertera användarpostlådor till delade postlådor. Se [Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md).

- **Administratörsroller:** Användare med globala administratörs- eller Exchange-administratörsroller kan skapa delade postlådor.

- **Abonnemangskrav:** Om du vill skapa en delad postlåda måste du prenumerera på en Office 365 för-affärsplan som innehåller e-post (Exchange Online-tjänsten). Office 365 Business-prenumerationen innehåller inte e-post. Office 365 Business Premium gör det.

- **Logga in:** En delad postlåda är inte avsedd för direkt inloggning av det associerade användarkontot. Du bör alltid blockera inloggning för det delade postlådekontot och hålla det blockerat.

- **För många användare:** När det finns för många utsedda användare samtidigt som de kommer åt en delad postlåda kan de ibland misslyckas med att ansluta till den här postlådan. I det här fallet kan du överväga att minska antalet användare eller använda en annan arbetsbelastning, till exempel Office 365-gruppen eller den gemensamma mappen.

- **Borttagning av meddelanden:** Tyvärr kan du inte hindra andra från att ta bort meddelanden i en delad postlåda. Det enda sättet runt det här är att skapa en Office 365-grupp i stället för en delad postlåda. En grupp i Outlook är som en delad postlåda. En jämförelse mellan de två finns i [Jämföra grupper](../create-groups/compare-groups.md). Mer information om grupper finns i [Läs mer om Grupper](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2.aspx)

## <a name="related-articles"></a>Relaterade artiklar

[Skapa en delad postlåda](create-a-shared-mailbox.md)

[Konfigurera en delad postlåda](configure-a-shared-mailbox.md)

[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md)

[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md)

[Lösa problem med delade postlådor](resolve-issues-with-shared-mailboxes.md)
