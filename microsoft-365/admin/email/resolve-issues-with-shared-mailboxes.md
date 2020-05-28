---
title: Lösa problem med delade postlådor
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: Prova de här lösningarna om du får problem med delade postlådor.
ms.openlocfilehash: 5d6de9ac66b11f0e50b259cdca0b1bb50b8326ee
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400022"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Lösa problem med delade postlådor

Om felmeddelanden visas när du skapar eller använder en delad postlåda kan du prova de här möjliga lösningarna. 

## <a name="error-when-creating-shared-mailboxes"></a>Fel vid skapande av delade postlådor
<a name="bkmk_Fix"> </a>

Om felmeddelandet visas **används proxyadressen "smtp:<delat postlådenamn \> " redan av proxyadresserna eller LegacyExchangeDN för " \<name> ". Välj en annan proxyadress**betyder det att du försöker ge den delade postlådan ett namn som redan används. Anta att du vill ha delade postlådor med namnen info@domän1 och info@domän2. Du kan göra det på två sätt:

  - Använd Windows PowerShell. Se det här blogginlägget för instruktioner: [Skapa delade postlådor med samma alias på olika domäner](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Ge den andra delade postlådan namnet något annat än början för att komma runt felet. Byt sedan namn på den delade postlådan till det du vill att den ska vara i administrationscentret.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Fel om att inte ha skicka behörigheter när du använder en delad postlåda

Om du har skapat en delad postlåda och sedan försöker skicka ett meddelande från den kan du få följande:

**Det gick inte att skicka det här meddelandet. Du har inte behörighet att skicka meddelandet för den angivna användarens räkning.**

Det här meddelandet visas när Microsoft 365 har ett replikeringsfördröjningsproblem. Det bör försvinna inom en timme eller så, när informationen om din nya delade postlåda (eller tillagd användare) replikeras över alla våra datacenter. Vänta en timme och försök sedan igen för att skicka ett meddelande.

## <a name="related-articles"></a>Relaterade artiklar

[Om delade postlådor](about-shared-mailboxes.md)

[Skapa en delad postlåda](create-a-shared-mailbox.md)

[Konfigurera en delad postlåda](configure-a-shared-mailbox.md)

[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md)

[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md)


    

