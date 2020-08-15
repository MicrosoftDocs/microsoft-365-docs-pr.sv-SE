---
title: Visa synkroniseringsstatus för katalog i Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: I den här artikeln lär du dig hur du kan kontrol lera status för din katalog-synkronisering i Office 365.
ms.openlocfilehash: c77898b58b58c6ae91492debd7ad66f395d80d52
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694660"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>Visa synkroniseringsstatus för katalog i Microsoft 365

Om du har integrerat din lokala Active Directory med Azure AD genom att synkronisera den lokala miljön med Microsoft 365 kan du också kontrol lera statusen för din synkronisering.
  
## <a name="view-directory-synchronization-status"></a>Visa synkroniseringsstatus för katalog

- Logga in på [administrations centret för Microsoft 365](https://admin.microsoft.com) och välj **DirSync-status** på Start sidan.
- Du kan också gå till **användare** \> **aktiva användare**och på sidan **aktiva användare** väljer du **mer** \> **katalog synkronisering**. I fönstret **Directory-synkronisering** väljer du **gå till DirSync-hanteringen**.

## <a name="information-on-the-manage-directory-synchronization-page"></a>Information om sidan Hantera katalog synkronisering

I följande tabell visas de funktioner du kan hämta information om på sidan.
  
Om det uppstår problem med din katalog-synkronisering visas felen på den här sidan också. Mer information om olika fel som kan uppstå finns i avsnittet [identifiera synkroniseringsfel i Microsoft 365](identify-directory-synchronization-errors.md).
  
|**Objekt**|**Vad det används till**|
|:-----|:-----|
|**Domäner verifierade** | Antal domäner i din Microsoft 365-klient som du har verifierat. |
|**Domäner är inte verifierade** | Domäner som du har lagt till men inte verifierats. |
|**Katalog synkronisering aktive rad** |Sant eller falskt. Anger om du har aktiverat katalog synkronisering. |
|**Senaste katalog synkronisering** | Förra gången katalog synkronisering kördes. Visar en varning och en länk till ett fel söknings verktyg om den senaste synkroniseringen var för mer än tre dagar sedan. |
|**Lösenordssynkronisering aktive rad** | Sant eller falskt. Anger om du har ett lösen ord-hash-synkronisering mellan vår lokala och din Microsoft 365-klient. |
|**Senaste lösen ords synkronisering** | Senaste gången lösen ordet för hash-synkronisering kördes. Visar en varning och en länk till ett fel söknings verktyg om den senaste synkroniseringen var för mer än tre dagar sedan. |
|**Katalog-synkroniseringsklient** | Innehåller en nedladdnings länk om en ny version av Azure AD Connect har frisläppts. |
|**Katalog-Sync-tjänstkonto** | Visar namnet på ditt Microsoft 365 Directory Sync Service-konto. |