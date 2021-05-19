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
ms.openlocfilehash: 156ba100cb2c51d1e54a2ee82c45db20845931f9
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535860"
---
# <a name="about-shared-mailboxes"></a>Om delade postlådor

Delade postlådor används när flera personer behöver åtkomst till samma postlåda, t. ex. företagsinformation eller supportens e-postadress, receptionen eller andra funktioner som kan delas av flera personer.

Användare som har behörighet till gruppens postlåda kan skicka som eller skicka för postlådans e-postadress om administratören har gett dig behörighet att göra det. Det här är särskilt användbart för postlådor i hjälp och support eftersom användare kan skicka e-post från "contoso support" eller "Byggnad As reception".

## <a name="before-you-begin"></a>Innan du börjar

Innan du [skapar en delad postlåda](create-a-shared-mailbox.md)finns det några saker du bör känna till:

- **Licenser:** Den delade postlådan kan lagra upp till 50 GB data utan att du behöver tilldela en licens till den. Därefter måste du tilldela postlådan en licens för att kunna lagra mer data. Mer information om licensiering av delade postlådor finns i [Exchange Online Begränsningar](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#StorageLimits). När en delad postlåda når lagringsgränsen kommer du att kunna ta emot e-post ett tag till, men du kommer inte att kunna skicka ny e-post. Därefter slutar den att ta emot e-post. De som skickar e-post till postlådan får ett meddelande om utebliven leverans.

- **Användarbehörigheter:** Du måste ge användare behörighet (medlemskap) att använda den delade postlådan. Det är bara personer i organisationen som kan använda en delad postlåda.

- **Externa användare:** Du kan inte ge personer utanför företaget (t.ex. har ett Gmail-konto) åtkomst till den delade postlådan. Om du vill göra det kan du skapa en grupp för Outlook stället. Mer information finns i [Skapa en Microsoft 365 grupp i administrationscentret](../create-groups/create-groups.md).

- **Används tillsammans med Outlook:** Förutom att använda Outlook på webben från webbläsaren för att komma åt delade postlådor kan du också använda appen Outlook för iOS eller Outlook för Android. Mer information finns i Lägga [till en delad postlåda på en Outlook mobil](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f). Ett annat alternativ är att skapa en grupp för den delade postlådan. Mer information finns i [Jämföra grupper.](../create-groups/compare-groups.md)

- **Kryptering:** Du kan inte kryptera e-post som skickas från en delad postlåda. Det beror på att en delad postlåda inte har ett eget säkerhetssammanhang (användarnamn/lösenord) och kan därför inte tilldelas en nyckel. Om fler än en person är medlem och de skickar/tar emot e-postmeddelanden som de krypterat med sina egna nycklar kanske andra medlemmar kan läsa e-postmeddelandet och andra kanske inte, beroende på vilken offentlig nyckel e-postmeddelandet krypterades med.

- **Konvertering av postlåda:** Du kan konvertera användarpostlådor till delade postlådor. Se [Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md).

- **Administratörsroller:** Användare med globala administratörs- Exchange administratörsroller kan skapa delade postlådor.

- **Prenumerationskrav:** Om du vill skapa en delad postlåda måste du prenumerera på ett Microsoft 365 för företag-abonnemang som innehåller e-Exchange Online posttjänsten. E Microsoft 365-applikationer för affärsverksamhet prenumerationen inkluderar inte e-post. Microsoft 365 Business Standard även e-post.

- **Logga in:** En delad postlåda är inte avsedd för direkt inloggning via det associerade användarkontot. Du bör alltid blockera inloggning för det delade postlådekontot och behålla det blockerat.

- **För många användare:** Om det finns för många användare som samtidigt ansluter till en delad postlåda kan det hända att de inte kan ansluta till den här postlådan. I det här fallet kan du minska antalet användare eller använda en annan arbetsbelastning, t.ex. Microsoft 365 grupp eller Offentlig mapp.

- **Meddelandeborttagning:** Det går tyvärr inte att hindra andra från att ta bort meddelanden i en delad postlåda. Det enda sättet runt det här är att skapa en Microsoft 365 grupp i stället för en delad postlåda. En grupp i Outlook är som en delad postlåda. En jämförelse mellan de två finns i [Jämföra grupper.](../create-groups/compare-groups.md) Mer information om grupper finns i [Läs mer om grupper.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)


> [!NOTE]
> För att komma åt en delad postlåda måste en användare Exchange Online en licens, men den delade postlådan kräver ingen separat licens. Alla delade postlådor har ett motsvarande användarkonto. Lade du märke till att du inte behövde ange något lösenord när du skapade den delade postlådan? Kontot har ett lösenord, men det genereras av systemet (okänt). Du bör inte använda kontot för att logga in på den delade postlådan. Utan licens är delade postlådor begränsade till 50 GB. För att storleksgränsen ska höjas till 100 GB måste den delade postlådan tilldelas en licens från Exchange Online abonnemang 2 eller en Exchange Online abonnemang 1-licens med en Exchange Online - arkivering-tilläggslicens. Det här gör det också möjligt att aktivera automatiskt expanderande arkivering för en obegränsad mängd arkivlagringskapacitet. Om du vill skapa bevarande av juridiska skäl för en delad postlåda måste den delade postlådan ha en Exchange Online abonnemang 2-licens eller en Exchange Online abonnemang 1-licens med en Exchange Online - arkivering-tilläggslicens. Om du vill använda avancerade funktioner som Microsoft Defender för Office 365, Advanced eDiscovery eller automatiska bevarandeprinciper måste den delade postlådan vara licensierad för dessa funktioner.

## <a name="related-content"></a>Relaterat innehåll

[Skapa en delad postlåda](create-a-shared-mailbox.md) (artikel)

[Konfigurera en delad postlåda](configure-a-shared-mailbox.md) (artikel)

[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md) (artikel)

[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md) (artikel)

[Lösa problem med delade postlådor](resolve-issues-with-shared-mailboxes.md) (artikel)