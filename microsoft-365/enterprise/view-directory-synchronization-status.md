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
ms.openlocfilehash: 7577ed358a262d5b0ef2932bc73cf61941bec31b
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326955"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>Visa synkroniseringsstatus för katalog i Microsoft 365

Om du har integrerat din lokala Active Directory Domain Services (AD DS) med Azure Active Directory (Azure AD) genom att synkronisera den lokala miljön med Microsoft 365 kan du också kontrol lera statusen för din synkronisering.
  
## <a name="view-directory-synchronization-status"></a>Visa katalogsynkroniseringsstatus

- Logga in på [administrations centret för Microsoft 365](https://admin.microsoft.com) och välj **DirSync-status** på Start sidan.
- Du kan också gå till **användare** \> **aktiva användare**och på sidan **aktiva användare** väljer du **mer** \> **katalog synkronisering**. I fönstret **Directory-synkronisering** väljer du **gå till DirSync-hanteringen**.

## <a name="information-on-the-manage-directory-synchronization-page"></a>Information om sidan Hantera katalog synkronisering

I följande tabell visas de funktioner du kan hämta information om på sidan.
  
Om det uppstår problem med din katalog-synkronisering visas felen på den här sidan också. Mer information om olika fel som kan uppstå finns i avsnittet [identifiera synkroniseringsfel i Microsoft 365](identify-directory-synchronization-errors.md).
  
|Objekt|Vad det används till|
|:-----|:-----|
|**Domäner verifierade** | Antal domäner i din Microsoft 365-klient som du har verifierat. |
|**Domäner är inte verifierade** | Domäner som du har lagt till men inte verifierats. |
|**Katalog synkronisering aktive rad** |Sant eller falskt. Anger om du har aktiverat katalog synkronisering. |
|**Senaste katalog synkronisering** | Förra gången katalog synkronisering kördes. Visar en varning och en länk till ett fel söknings verktyg om den senaste synkroniseringen var för mer än tre dagar sedan. |
|**Lösenordssynkronisering aktive rad** | Sant eller falskt. Anger om du har ett lösen ord-hash-synkronisering mellan vår lokala och din Microsoft 365-klient. |
|**Senaste lösen ords synkronisering** | Senaste gången lösen ordet för hash-synkronisering kördes. Visar en varning och en länk till ett fel söknings verktyg om den senaste synkroniseringen var för mer än tre dagar sedan. |
|**Katalog-synkroniseringsklient** | Innehåller en nedladdnings länk om en ny version av Azure AD Connect har frisläppts. |
|**Katalog-Sync-tjänstkonto** | Visar namnet på ditt Microsoft 365 Directory Sync Service-konto. |
|||

## <a name="monitor-synchronization-health"></a>Övervaka synkroniseringshälsa

I det här avsnittet installerar du en Azure AD Connect Health-agent på var och en av dina lokala AD DS-domänkontrollanter för att övervaka din identitetsinfrastruktur och de synkroniseringstjänster som tillhandahålls av Azure AD Connect. Övervakningsinformationen visas i en Azure AD Connect Health-portal, där du kan se varningar, prestandaövervakning, användningsanalys och annan information.

Det viktiga beslutet för hur du ska använda Azure AD Connect Health, baseras på hur du använder Azure AD Connect:

- Om du använder **hanterad autentisering** börjar du med [Använda Azure AD Connect Health med synkronisering](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) för att förstå och konfigurera Azure AD Connect Health.
- Om du bara synkroniserar namnen på de konton och grupper som använder **federerad autentisering** med Active Directory Federation Services (AD FS), börjar du med [Använda Azure AD Connect Health med AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) för att förstå och konfigurera Azure AD Connect Health.

När du är klar har du:

- Azure AD Connect Health-agenten installerad på dina lokala identitetsproviderservrar.
- Azure AD Connect Health-portalen visar aktuell status för lokal infrastruktur och synkronisering med Azure AD-klientorganisationen för din Microsoft 365-prenumeration.

