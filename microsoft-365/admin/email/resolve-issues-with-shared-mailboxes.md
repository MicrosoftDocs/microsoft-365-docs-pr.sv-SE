---
title: Lösa problem med delade postlådor
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
description: Prova de här lösningarna om du upplever problem med delade postlådor.
ms.openlocfilehash: ba62db76edff6e4ab3d738ed0af8db2a40c18394
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926492"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Lösa problem med delade postlådor

Om du får felmeddelanden när du skapar eller använder en delad postlåda kan du prova de här lösningarna. 

## <a name="error-when-creating-shared-mailboxes"></a>Fel när delade postlådor skapas
<a name="bkmk_Fix"> </a>

Om du ser felmeddelandet används proxyadressen "smtp:<namn på delad postlåda " redan av proxyadresserna eller **\> LegacyExchangeDN för " \<name> ". Välj en annan proxyadress,** vilket innebär att du försöker ge den delade postlådan ett namn som redan används. Anta att du vill ha delade postlådor med namnen info@domän1 och info@domän2. Du kan göra det på två sätt:

  - Använd Windows PowerShell. Anvisningar finns i det här blogginlägget: [Skapa delade postlådor med samma alias på olika domäner](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Ge den andra delade postlådan ett annat namn från början för att komma runt felet. Byt sedan namn på den delade postlådan till det du vill i administrationscentret.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Fel om att du inte har skickat behörigheter när du använder en delad postlåda

Om du har skapat en delad postlåda och sedan försöker skicka ett meddelande från den kan följande hända:

**Det här meddelandet kunde inte skickas. Du har inte behörighet att skicka meddelandet åt den angivna användaren.**

Det här meddelandet visas när Microsoft 365 har problem med replikeringssvarstid. Den bör försvinna om någon timme, när informationen om den nya delade postlådan (eller den nya användaren) replikeras över alla våra datacenter. Vänta en timme och försök sedan igen för att skicka ett meddelande.

## <a name="related-articles"></a>Relaterade artiklar

[Om delade postlådor](about-shared-mailboxes.md)

[Skapa en delad postlåda](create-a-shared-mailbox.md)

[Konfigurera en delad postlåda](configure-a-shared-mailbox.md)

[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md)

[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md)


    

