---
title: Visa katalogsynkroniseringsstatus i Microsoft 365
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
description: I den här artikeln lär du dig hur du kontrollerar status för katalogsynkroniseringen i Office 365.
ms.openlocfilehash: cbaae8bbd31f6124c2b0f4984b9a625ffbde538f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924666"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a>Visa katalogsynkroniseringsstatus i Microsoft 365

Om du har integrerat din lokala Active Directory Domain Services (AD DS) med Azure Active Directory (Azure AD) genom att synkronisera din lokala miljö med Microsoft 365 kan du även kontrollera status för synkroniseringen.
  
## <a name="view-directory-synchronization-status"></a>Visa katalogsynkroniseringsstatus

- Logga in Microsoft 365 [administrationscentret](https://admin.microsoft.com) och välj **DirSync-status** på startsidan.
- Alternativt kan du gå till Användare **aktiva användare** och på \> sidan Aktiva **användare** väljer du Mer **katalogsynkronisering.** \>  I fönstret **Katalogsynkronisering** väljer du **Gå till DirSync-hantering**.

## <a name="information-on-the-manage-directory-synchronization-page"></a>Information på sidan Hantera katalogsynkronisering

I följande tabell visas de funktioner du kan få information om på sidan.
  
Om det är problem med katalogsynkroniseringen visas även felen på den här sidan. Mer information om olika fel som kan uppstå finns i [Identifiera katalogsynkroniseringsfel i Microsoft 365](identify-directory-synchronization-errors.md).
  
|Objekt|Vad det används till|
|:-----|:-----|
|**Verifierade domäner** | Antalet domäner i klientorganisationen Microsoft 365 som du har verifierat att du äger. |
|**Domäner som inte har verifierats** | Domäner som du har lagt till, men inte verifierat. |
|**Katalogsynkronisering aktiverad** |Sant eller falskt. Anger om du har aktiverat katalogsynkronisering. |
|**Senaste katalogsynkronisering** | Senaste gången katalogsynkronisering kördes. Visar en varning och en länk till ett felsökningsverktyg, om den senaste synkroniseringen gjordes för mer än tre dagar sedan. |
|**Lösenordssynkronisering aktiverad** | Sant eller falskt. Anger om du har hash-synkronisering av lösenord mellan vår lokala och din Microsoft 365 klientorganisation. |
|**Senaste lösenordssynkronisering** | Senaste gången hash-synkronisering av lösenord kördes. Visar en varning och en länk till ett felsökningsverktyg, om den senaste synkroniseringen gjordes för mer än tre dagar sedan. |
|**Version av katalogsynkroniseringsklient** | Innehåller en nedladdningslänk om en ny version av Azure AD Anslut har släppts. |
|**Katalogsynkroniseringstjänstkonto** | Visar namnet på ditt Microsoft 365 katalogsynkroniseringstjänstkonto. |
|||

## <a name="monitor-synchronization-health"></a>Övervaka synkroniseringshälsa

I det här avsnittet installerar du en Azure AD Connect Health-agent på var och en av dina lokala AD DS-domänkontrollanter för att övervaka din identitetsinfrastruktur och de synkroniseringstjänster som tillhandahålls av Azure AD Connect. Övervakningsinformationen visas i en Azure AD Connect Health-portal, där du kan se varningar, prestandaövervakning, användningsanalys och annan information.

Det viktiga beslutet för hur du ska använda Azure AD Connect Health, baseras på hur du använder Azure AD Connect:

- Om du använder **hanterad autentisering** börjar du med [Använda Azure AD Connect Health med synkronisering](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) för att förstå och konfigurera Azure AD Connect Health.
- Om du bara synkroniserar namnen på de konton och grupper som använder **federerad autentisering** med Active Directory Federation Services (AD FS), börjar du med [Använda Azure AD Connect Health med AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) för att förstå och konfigurera Azure AD Connect Health.

När det är klart har du:

- Azure AD Connect Health-agenten installerad på dina lokala identitetsproviderservrar.
- Azure AD Connect Health-portalen visar aktuell status för lokal infrastruktur och synkronisering med Azure AD-klientorganisationen för din Microsoft 365-prenumeration.