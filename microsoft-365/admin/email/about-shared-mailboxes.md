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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Delade postlådor används när flera personer behöver åtkomst till samma postlåda. Lär dig vad du behöver veta innan du skapar en delad postlåda.
ms.openlocfilehash: c8d29ac2dfe8670181064e61a7fba145ae00fed1
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058453"
---
# <a name="about-shared-mailboxes"></a>Om delade postlådor

Delade postlådor används när flera personer behöver åtkomst till samma postlåda, t. ex. företagsinformation eller supportens e-postadress, receptionen eller andra funktioner som kan delas av flera personer.

Användare som har behörighet till gruppens postlåda kan skicka som eller skicka för postlådans e-postadress om administratören har gett dig behörighet att göra det. Det här är särskilt användbart för postlådor i hjälp och support eftersom användare kan skicka e-post från "contoso support" eller "Byggnad As reception".

Innan du [skapar en delad postlåda](create-a-shared-mailbox.md)finns det några saker du bör känna till:

- **Licenser:** Den delade postlådan kan lagra upp till 50 GB data utan att du behöver tilldela en licens till den. Därefter måste du tilldela postlådan en licens för att kunna lagra mer data. Mer information om licensiering av delade postlådor finns i Begränsningar för [Exchange Online.](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits) När en delad postlåda når lagringsgränsen kommer du att kunna ta emot e-post ett tag till, men du kommer inte att kunna skicka ny e-post. Därefter slutar den att ta emot e-post. De som skickar e-post till postlådan får ett meddelande om utebliven leverans.

- **Användarbehörigheter:** Du måste ge användare behörighet (medlemskap) att använda den delade postlådan. Det är bara personer i organisationen som kan använda en delad postlåda.

- **Externa användare:** Du kan inte ge personer utanför företaget (t.ex. har ett Gmail-konto) åtkomst till den delade postlådan. Om du vill göra det kan du skapa en grupp för Outlook i stället. Mer information finns i [Skapa en Microsoft 365-grupp i administrationscentret.](../create-groups/create-groups.md)

- **Använd med Outlook:** Förutom att använda Outlook på webben från webbläsaren för att komma åt delade postlådor kan du också använda Outlook för iOS-appen eller Outlook för Android-appen. Mer information finns i Lägga [till en delad postlåda i Outlook Mobile.](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f) Ett annat alternativ är att skapa en grupp för den delade postlådan. Mer information finns i [Jämför grupper.](../create-groups/compare-groups.md)

- **Kryptering:** Du kan inte kryptera e-post som skickas från en delad postlåda. Det beror på att en delad postlåda inte har ett eget säkerhetssammanhang (användarnamn/lösenord) och kan därför inte tilldelas en nyckel. Om fler än en person är medlem och de skickar/tar emot e-postmeddelanden som de har krypterat med sina egna nycklar, kan andra medlemmar kanske inte läsa e-postmeddelandet och andra kanske inte, beroende på vilken offentlig nyckel e-postmeddelandet har krypterats med.

- **Postlådekonvertering:** Du kan konvertera användarpostlådor till delade postlådor. Se [Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md).

- **Administratörsroller:** Användare med globala administratörs- eller Exchange-administratörsroller kan skapa delade postlådor.

- **Prenumerationskrav:** Om du vill skapa en delad postlåda måste du prenumerera på ett Microsoft 365 för företag-abonnemang som innehåller e-post (Exchange Online-tjänsten). E-post ingår inte i prenumerationen på Microsoft 365-appar för företag. Microsoft 365 Business Standard innehåller e-post.

- **Logga in:** En delad postlåda är inte avsedd för direkt inloggning av det associerade användarkontot. Du bör alltid blockera inloggning för kontot för den delade postlådan och behålla den blockerad.

- **För många användare:** Om det finns för många användare som samtidigt ansluter till en delad postlåda kan det hända att de inte kan ansluta till den här postlådan. I det här fallet kan du minska antalet användare eller använda en annan arbetsbelastning, till exempel en Microsoft 365-grupp eller offentlig mapp.

- **Meddelandeborttagning:** Tyvärr kan du inte hindra andra från att ta bort meddelanden i en delad postlåda. Det enda sättet runt det här är att skapa en Microsoft 365-grupp i stället för en delad postlåda. En grupp i Outlook är som en delad postlåda. En jämförelse av de två finns i [Jämför grupper.](../create-groups/compare-groups.md) Mer information om grupper finns i [Läs mer om grupper.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)


> [!NOTE]
> För att komma åt en delad postlåda måste en användare ha en Exchange Online-licens, men den delade postlådan kräver ingen separat licens. Utan licens är delade postlådor begränsade till 50 GB. Om du vill öka storleksgränsen till 100 GB måste den delade postlådan tilldelas en licens för Exchange Online abonnemang 2 eller en Licens för Exchange Online abonnemang 1 med en tilläggslicens för Exchange Online Arkivering. På så sätt kan du också aktivera automatisk expandering av arkivering med obegränsad lagringskapacitet. Om du vill skapa bevarande av juridiska skäl för en delad postlåda måste den delade postlådan ha en licens för Exchange Online abonnemang 2 eller en Exchange Online abonnemang 1-licens med en tilläggslicens för Exchange Online Arkivering. Om du vill använda avancerade funktioner som Microsoft Defender för Office 365, Advanced eDiscovery eller automatiska bevarandeprinciper måste den delade postlådan vara licensierad för dessa funktioner.

## <a name="related-articles"></a>Relaterade artiklar

[Skapa en delad postlåda](create-a-shared-mailbox.md)

[Konfigurera en delad postlåda](configure-a-shared-mailbox.md)

[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md)

[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md)

[Lösa problem med delade postlådor](resolve-issues-with-shared-mailboxes.md)
