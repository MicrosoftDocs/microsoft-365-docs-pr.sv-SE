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
description: Du kan få felmeddelanden när du konfigurerade delade postlådor. Prova de här lösningarna om du upplever problem med delade postlådor.
ms.openlocfilehash: 89cdfbe29ab035b1eb6c3a0183629eef59d67477
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706136"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Lösa problem med delade postlådor

Om du ser felmeddelanden när du skapar eller använder en delad postlåda kan du prova de här möjliga lösningarna. 

## <a name="error-when-creating-shared-mailboxes"></a>Fel när delade postlådor skapas
<a name="bkmk_Fix"> </a>

Om du ser felmeddelandet används proxyadressen "smtp:<namn på delad postlåda " redan av proxyadresserna eller **\> LegacyExchangeDN för " \<name> ". Välj en annan proxyadress**, det innebär att du försöker ge den delade postlådan ett namn som redan används. Anta att du vill ha delade postlådor med namnen info@domän1 och info@domän2. Du kan göra det på två sätt:

  - Använd Windows PowerShell. Anvisningar finns i det här blogginlägget: [Skapa delade postlådor med samma alias på olika domäner](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Ge den andra delade postlådan ett annat namn på en gång för att komma runt felet. I administrationscentret byter du sedan namn på den delade postlådan till det du vill.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Felmeddelande om att du inte har skicka behörigheter när du använder en delad postlåda

Om du har skapat en delad postlåda och sedan försöker skicka ett meddelande från den, kan du få följande:

**Det här meddelandet kunde inte skickas. Du har inte behörighet att skicka meddelandet åt den angivna användaren.**

Det här meddelandet visas Microsoft 365 har problem med replikeringssvarstid. Den bör försvinna om någon timme, när informationen om din nya delade postlåda (eller användare som lagts till) replikeras i alla våra datacenter. Vänta en timme och försök sedan igen för att skicka ett meddelande.

## <a name="related-content"></a>Relaterat innehåll

[Om delade postlådor](about-shared-mailboxes.md) (artikel)\
[Skapa en delad postlåda](create-a-shared-mailbox.md) (artikel)\
[Konfigurera en delad postlåda](configure-a-shared-mailbox.md) (artikel)\
[Konvertera en användarpostlåda till en delad postlåda](convert-user-mailbox-to-shared-mailbox.md) (artikel)\
[Ta bort en licens från en delad postlåda](remove-license-from-shared-mailbox.md) (artikel)


    

