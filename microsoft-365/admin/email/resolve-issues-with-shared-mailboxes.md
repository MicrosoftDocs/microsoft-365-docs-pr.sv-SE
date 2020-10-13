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
search.appverid:
- BCS160
- MET150
- MOE150
description: Prova de här lösningarna om du får problem med delade post lådor.
ms.openlocfilehash: c889d3aa2fab8c2dce4cc2a8a00ef49a905363a1
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445513"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Lösa problem med delade postlådor

Om du ser fel meddelanden när du skapar eller använder en delad post låda kan du försöka med följande. 

## <a name="error-when-creating-shared-mailboxes"></a>Fel när delade post lådor skapades
<a name="bkmk_Fix"> </a>

Om du får fel meddelandet " **" SMTP: <delade post lådans namn \> "används redan av proxyadresser eller LegacyExchangeDN av" \<name> ". Välj en annan proxyadress**, det innebär att du försöker ge den delade post lådan ett namn som redan används. Anta att du vill ha delade postlådor med namnen info@domän1 och info@domän2. Du kan göra det på två sätt:

  - Använd Windows PowerShell. Anvisningar finns i det här blogg inlägget: [skapa delade post lådor med samma alias på olika domäner](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Ge den andra delade post lådan något annat från början för att få veta mer om felet. I Admin Center byter du namn på den delade post lådan till det du vill ha.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Fel om att inte ha behörighet att skicka när du använder en delad post låda

Om du har skapat en delad post låda och sedan försöker skicka ett meddelande från den kan du få följande:

**Det gick inte att skicka meddelandet. Du har inte behörighet att skicka meddelandet å angiven användares vägnar.**

Det här meddelandet visas när Microsoft 365 drabbas av ett problem med replikeringsfördröjning. Det ska gå längre tid än en timme, eller så när informationen om den nya delade post lådan (eller tillagd användare) replikeras i alla data Center. Vänta en timme och försök sedan igen för att skicka ett meddelande.

## <a name="related-articles"></a>Relaterade artiklar

[Om delade postlådor](about-shared-mailboxes.md)

[Skapa en delad postlåda](create-a-shared-mailbox.md)

[Konfigurera en delad postlåda](configure-a-shared-mailbox.md)

[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md)

[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md)


    

